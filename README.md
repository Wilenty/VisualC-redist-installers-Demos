# VC++ redistributable runtimes installers - Demos

Changes in the program:

	v21.09.25 (2021-09-25):

Updated VC++ 2022 to the latest version.

	v21.09.15 (2021-09-15):

Command line parameter /Portable skips checking for the First Full Uninstall and skips creating uninstall entry in the OS registry.
Please remember that the Auto-Update option does not remove all old runtimes installed, only the last one.
So, to remove all doubled entries in the Uninstall section, you need to Uninstall all of them and Install again.

From now you can use it as standard InnoSetup installer with standard InnoSetup parameters (/TYPE=type name & /COMPONENTS="comma separated list of component names"), or you can use predefined parameters, which can be found in the: "Menu" (button on the Components page) -> "Parameters?" (and click on this button few more times).

And, the installer returns the amount of operations done in the Uninstallation/Installation process as return-code/exit-code. But because InnoSetup internal error-codes are above zero (and I can't change it without recompiling the source code), it returns the amount of operations done below zero.
For example the exit-code 0 in Update (Auto-Update) means that nothing has to be updated, all runtime libraries are in current versions.
And the exit-code -1 means that one operation was done in the Uninstallation and/or Installation process (depends of your choices), and so on...

If your computer has low resources, or weak graphics card, or you are not interested about the MSI log messages. You can add the /Silent command line parameter, which informs the InnoSetup installer to not display the "Microsoft Software Installer" (MSI) log messages on the installing page, which should speed up (a bit) the installing time.

	v21.09.09 (2021-09-09):

I completely rebuilt the entire installer and added VC++ runtimes 2022.

If you select VC++ version 2022 for install, or you use command line parameter /SelectVcVersion="2022", and you will specify components to install in the /COMPONENTS="x64\2015\additional,x86\2017\minimum" (for example), the installer will replace the "2015" and "2017" for selected VC++ version, i.e. "2022", and will select correct components for install.
The same if you select another VC++ version for install and you select different components to install than the selected VC++, in the group of 2015, 2017, 2019 and 2022.
