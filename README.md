# VC++ redistributable runtimes installers - Demos

If this  program is to advanced/complicated for you, look at the "Simple Install" button on the information-page (where the information about the changes). After using it (in the full version), it will remove all installed VC++ runtimes and install included in the program.

It's so hard to create simple as possible program and advanced as possible at the same time, where you can change all options available, even from command-line! So, I created a batch file to show you how the command-line is parsed by the program. And, I described all of available parameters in the text files.
I added the "Simple Install" button that you don't need to have go through all the possible options.

But, please take in mind the auto-update option will not remove all doubled entries (in the uninstall section) - normal installation is designed for that. The "Simple install" button will clean all doubled entries as well. Or, you can remove manually the doubled-entries visible in the uninstall-section.

**I will share the link to the full-version of this program with latest runtimes for you after support me. I updates the program for myself, so, it will always have the latest runtimes.**

## Changes to the program (in reverse order):

**v22.03.29 (2022-03-29):**

Added support for ARM64 architecture. From now it includes VC++ 2017, 2019 and 2022 for ARM64 (and supports 2017/2019/2022 in the external version, parameter: /VC_redistARM64="X:\Full\Path (with spaces)\to\the\VC_redist.arm64.exe")

Added selective uninstall command-line parameter:
/Uninstall="comma separated list of Uninstall names, versions or reg-keys"
after choosing uninstallation in:
/COMPONENTS="un\arm64,un\x64,un\x86"
Parameters for command-line /Uninstall="12.v3r...,{AndOr-Reg-Keys...},and/or VC names or part of names..." must be separated by comma, as for other lists of parameters for InnoSetup. When you will use this parameter, all of the components on Uninstall list will be deselected, and selected only those which will match the components from the Uninstall list.

Added install command-line parameter with missing dll:
/NeedDLL="Missing.dll"
It does the same as the "Menu" (button) -> "Need a dll?" on the Components Page, but from command-line.
Above mentioned parameter can work separately or with "/COMPONENTS=" parameter.
By using only one of above mentioned command-line parameter (i.e. "/NeedDLL="), the Installer will be switched to the "CustomSetup" and all components will be deselected - it will selects only these components which it will be able to find using the given dll file.
But, with using the "/COMPONENTS=", it will adds found components by the "/NeedDLL=" command-line parameter to the install-list.

Added the "dark theme" - it depends of the theme used by you (W10/W11), if enabled - it inverts the colors, other way it uses colors of your windows.

Removed creating uninstall section in the OS registry, and removed /Portable command-line switch.

---

<details><summary>v21.10.21 (2021-10-21):</summary>

Added the "PreveiewOnTaskBarAW.isi" to show you that my solution works without any problems, so, now you can see preview of the Installer window/messages on the Task-Bar.

</details>

---

<details><summary>v21.09.25 (2021-09-25):</summary>

Updated VC++ 2022 to the latest version.

</details>

---

<details><summary>v21.09.15 (2021-09-15):</summary>

Command line parameter /Portable skips checking for the First Full Uninstall and skips creating uninstall entry in the OS registry.
Please remember that the Auto-Update option does not remove all old runtimes installed, only the last one.
So, to remove all doubled entries in the Uninstall section, you need to Uninstall all of them and Install again.

From now you can use it as standard InnoSetup installer with standard InnoSetup parameters (/TYPE=type name & /COMPONENTS="comma separated list of component names"), or you can use predefined parameters, which can be found in the: "Menu" (button on the Components page) -> "Parameters?" (and click on this button few more times).

And, the installer returns the amount of operations done in the Uninstallation/Installation process as return-code/exit-code. But because InnoSetup internal error-codes are above zero (and I can't change it without recompiling the source code), it returns the amount of operations done below zero.
For example the exit-code 0 in Update (Auto-Update) means that nothing has to be updated, all runtime libraries are in current versions.
And the exit-code -1 means that one operation was done in the Uninstallation and/or Installation process (depends of your choices), and so on...

If your computer has low resources, or weak graphics card, or you are not interested about the MSI log messages. You can add the /Silent command line parameter, which informs the InnoSetup installer to not display the "Microsoft Software Installer" (MSI) log messages on the installing page, which should speed up (a bit) the installing time.

</details>

---

<details><summary>v21.09.09 (2021-09-09):</summary>

I completely rebuilt the entire installer and added VC++ runtimes 2022.

If you select VC++ version 2022 for install, or you use command line parameter /SelectVcVersion="2022", and you will specify components to install in the /COMPONENTS="x64\2015\additional,x86\2017\minimum" (for example), the installer will replace the "2015" and "2017" for selected VC++ version, i.e. "2022", and will select correct components for install.
The same if you select another VC++ version for install and you select different components to install than the selected VC++, in the group of 2015, 2017, 2019 and 2022.
</details>

---
