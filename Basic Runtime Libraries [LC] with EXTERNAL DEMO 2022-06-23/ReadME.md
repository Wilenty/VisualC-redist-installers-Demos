    v22.05.10 (2022-05-10):

Added the "InnoSetup [Types], [Components], [Tasks], [Run] Directly In the [code]" from there: https://github.com/Wilenty/InnoSetup-Types-Components-Tasks-Run-Directly-In-the-code-

And changed the "VC++ choose window" to the "VC++ choose page" after information text.

	v22.03.29 (2022-03-29):

Added support for ARM64 architecture. From now it includes VC++ 2017, 2019 and 2022 for ARM64, and supports 2017/2019/2022 in the external version, parameter:
/VC_redistARM64="X:\Full\Path (with spaces)\to\the\VC_redist.arm64.exe"
or
/VC_redistARM64="X:\Full\Path (with spaces)\to\the\VC_redist.x64.exe"
for the VC++ 2022, because it includes the ARM64 version too.

You have to use all of the parameters beginning with /VC_redist to change all locations of the external installers to use, if they are different than installer location.

	v21.09.09 (2021-09-09):

Here you can use any of VC++ 2015/2017/2019/2022 runtimes as EXTERNAL directly from original installers, command line parameter: /SelectVcVersion="EXT".

New command-line parameters:
/VC_redistX64="X:\Full\Path (with spaces)\to\the\VC_redist.x64.exe"
and
 /VC_redistX86="X:\Full\Path (with spaces)\to\the\VC_redist.x86.exe"

You need to use both parameters above to change both locations of the installers to use, if they are different than installer location.

---

Link to the support page: https://www.patreon.com/posts/50542367

or please supprt me with this same amount on Ko-Fi.
