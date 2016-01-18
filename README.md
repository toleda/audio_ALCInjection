audio_ALCInjection
============
OS X/Desktop/Realtek ALC 885, 887, 888, 889, 892, 898 and 1150 and NUC/BRIX/Realtek ALC 269 and 283 audio

v4: 1/18/16 - Clover ssdt hdef v4, codecdetect v1.2

v3: 11/27/15 - ssdt_hdef supports with IOReg/HDEF, without IOReg/HDEF, AZAL, x99/ALZA and 100 Series/HDAS for all Intel Desktop motherboards.

This guide enables OS X Realtek ALC onboard audio on Intel based motherboards with OS X. The Realtek AppleHDA.kext only works with the codec the kext was edited for and works with or replaces the native AppleHDA.kext.

**A - Audio/ALC Injection Status**

1. Download: [audio_codecdetect.command](https://github.com/toleda/audio_ALCInjection/blob/master/audio_codecdetect.command.zip) (select View Raw)
2. Confirm OS X support
	1. Codec (vendor/device id)
	2. Device (HDEF)
	3. Audio ID (1, 2 or 3)
3. Installation
	1. Double click Downloads/audio_codecdetect.command
	2. Review results
		1. OK: Audio/ALC Injection working
		2. NOK: problems/fixes
			1. specific ssdt
			2. Clover injection
4. Terminal/Shell/Export Text As...
	1. [audio_codecdetect.command](https://github.com/toleda/audio_ALCInjection/blob/master/terminal-codecdetect)

**B - Audio/ALC Injection techniques** select one method

1. No dsdt/audio enabler  (use kext installer)
	See [Guide]-Add_HDEF-kext.pdf

	1. [Audio_ID = 1](https://github.com/toleda/audio_ALCInjection/blob/master/audio_kext_enabler/HDAEnabler1.kext.zip)
	2. [Audio_ID = 2](https://github.com/toleda/audio_ALCInjection/blob/master/audio_kext_enabler/HDAEnabler2.kext.zip)
	4. Audio_ID = 3 NA

2. dsdt/HDEF/layout-id = Audio_ID  
	See [Guide] Add or Edit dsdt/HDEF.pdf

	1. Audio_ID = 1/MaciASL/Patch/Enable Audio ID: 1
	2. Audio_ID = 2/MaciASL/Patch/Enable Audio ID: 2
	3. Audio_ID = 3, see
		1. [HD4000](https://github.com/toleda/audio_hdmi_hd4000)
		2. [HD3000](https://github.com/toleda/audio_hdmi_hd3000)

3. ssdt/HDEF/layout-id = Audio_ID  
	See [Guide]-OSX_ssdt-installation.pdf

	1. 100-hdas/HDAS@1F,3
		1. [Audio_ID = 1](https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-1-100-hdas.zip)
		2. [Audio_ID = 2](https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-2-100-hdas.zip)
		3. [Audio_ID = 3](https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-3-100-hdas.zip)
	2. with_ioreg/HDEF@1B
		1. [Audio_ID = 1](https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-1-with_ioreg:hdef.zip)
		2. [Audio_ID = 2](https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-2-with_ioreg:hdef.zip)
		3. [Audio_ID = 3](https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-3-with_ioreg:hdef.zip)
	3. x99-alza/ALZA@1B
		1. [Audio_ID = 1](https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-1-x99-alza.zip)
	4. with_ioreg/AZAL@1B
		1. [Audio_ID = 1](https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-1-with_ioreg:azal.zip) 
	5. no_ioreg/HDEF
		1. [Audio_ID = 1](https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-1-no_ioreg:hdef.zip)
		2. [Audio_ID = 2](https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-2-no_ioreg:hdef.zip)
		3. [Audio_ID = 3](https://github.com/toleda/audio_ALCInjection/blob/master/ssdt_hdef/ssdt_hdef-3-no_ioreg:hdef.zip)

4. Clover/Config.plist/Devices/Audio/Inject/1 
	1. Audio_ID = 1
	2. Audio_ID = 2
	3. Audio_ID = 3

5. Chameleon/org.chameleon.Boot.plist  
	1. Audio_ID = 1
		1. HDAEnabler=Yes
		2. HDEFLayoutID=01000000
	2. Audio_ID = 2
		1. HDAEnabler=Yes
		2. HDEFLayoutID=02000000
	3. Audio_ID = 3
		1. HDAEnabler=Yes
		2. HDEFLayoutID=03000000

**C - Audio ID Verification**

1. Restart
2. See A - Audio/ALC Injection Status

**D - Realtek ALC AppleHDA Audio Installation Methods**

1. [cloverALC - Clover/kext patch](https://github.com/toleda/audio_CloverALC)
2. [realtekALC - Kext/binary patch](https://github.com/toleda/audio_RealtekALC)

**E - Requirements**

1.  OS X Versions (+ all)
    1.  10.11+/El Capitan 
    2.  10.10+/Yosemite
    3.  10.9+/Mavericks
    4.  10.8+/Mountain Lion
2. Boot Flags/Boot failure may result if ignored
	1. 10.11+/Disable SIP/set, restart, install, enable SIP, restart
		1. CLOVER/config.plist/RtVariables/
			1. BooterConfig/0x28
			2. CsrActiveConfig/0x3
		2. Chameleon - Extra/org.chameleon.Boot.plist
			1. CsrActiveConfig=3
	2. 10.10+/Allow unsigned kexts/set, restart, install
		1. Clover/config.plist/
			1. Boot/Arguments/kext-dev-mode=1
		2. Chameleon/Extra/org.chameleon.Boot.plist/
			1. Kernel Flags/kext-dev-mode=1
3.  Native AppleHDA.kext
    1.  [Need native?](https://github.com/toleda/audio_ALC_guides/blob/master/Restore%20native%20AppleHDA%20%5BGuide%5D.pdf)
4.  Supported Realtek onboard audio codec
    1.  [Unknown codec?](https://github.com/toleda/audio_ALCInjection/blob/master/audio_codecdetect.command.zip)

**F - Realtek ALCxxx** (verify codec and Audio ID)

1.  Supported codecs
    1.  269 (BRIX only)
    2.  283 (BRIX Pro and NUC only)
    3.  885
    4.  887
    5.  888
    6.  889
    7.  892
    8.  898
    9.  1150
2.  Supported Audio IDs
    1. Audio ID: 1 supports 269, 283, 885, 887, 888, 889, 892, 898, 1150  
        Realtek ALC audio (default, 1/2/3/5/6 motherboard audio ports)

    2. Audio ID: 2 supports 887, 888, 889, 892, 898, 1150   
        Realtek ALC/5.1 surround sound (3 motherboard audio ports) 

    3. Audio ID: 3 supports 887, 888, 889, 892, 898, 1150  
        HD3000/HD4000 HDMI audio with Realtek ALC audio
    4. Audio_IDs: 1 and 2 support analog 5.1 surround sound, 3 does not  
    5. Audio_IDs: 1, 2 and 3 require HDMI audio dsdt edits for HDMI audio
    6.  The native AppleHDA.kext supports HDMI audio (dsdt edits required) with an unsupported onboard audio codec using Audio ID: 1. 

**G - More Information**

1. [Audio ID Injection](https://github.com/toleda/audio_ALCInjection)
2. [Details](https://github.com/toleda/audio_RealtekALC/blob/master/DETAILS.md)
    1.  Realtek ALC Audio Solutions
    2.  Requirements - Supported/Unsupported
    3.  Notes
    4.  Guides
    5.  Tools
3. [Realtek ALC guides](https://github.com/toleda/audio_ALC_guides)
	1. Capabilities
	2. Customization 
	3. No Audio After Sleep/Wake
	4. No Audio Devices
	5. No Sound
	6. Screenshots
	7. Surround Sound 
4. [Terminal Saved Output](https://github.com/toleda/audio_RealtekALC/blob/master/Terminal:audio_realtekALC-110.command_v1.0a.txt)

**H - Tools**

1. [IOReg_v2.1](https://github.com/toleda/audio_ALCInjection/blob/master/IORegistryExplorer_v2.1.zip) (select View Raw)
2. [DPCIManger](http://sourceforge.net/projects/dpcimanager/)  
3. [MaciASL](http://sourceforge.net/projects/maciasl/)
4. [audio_codecdetect.command](https://github.com/toleda/audio_ALCInjection/blob/master/audio_codecdetect.command.zip) (select View Raw)
5. Property List Editors -
	1. [Xcode](https://developer.apple.com/xcode/)  
	2. Property List Editor, PlistEdit Pro, TextEdit, etc.
	3. TextEdit, TextWrangler (last resort)

**I - Problem Reporting** (no files atached, no reply)

1.	Description of audio problem
2.	OS X version/motherboard model/BIOS version/processor/graphics
3.	Procedure/Guide used
4.	Installed S/L/E/AppleHDA.kext
5.	Copy of IOReg - IOReg_v2.1/File/Save a Copy As…, verify file (Tools 1.)
6.	Screenshot: DPCIManager/Status (Tools 2.) 
7.	DPCIManager/Misc/Boot Log, atttach text file
8.	Terminal/Shell/File/Export Text As. . . /
	1. audio_cloverALC-110...command
	2. audio_pikeralphaALC-110...command
9. Chameleon (if installed)
	1. Extra/org.chameleon.Boot.plist
	2. DPCIManager/Misc/Boot Log (Tools 2.)
	3. Extra/dsdt.aml (if installed)
	4. Extra/ssdt.aml (if installed)
10.	Clover (if installed)
	1.	EFI/CLOVER/config.plist
	2.	DPCIManager/Misc/Boot Log (Tools 2.)
	3.	EFI/CLOVER/ACPI/Patched/dsdt.aml (if installed)
	4.	EFI/CLOVER/ACPI/Patched/ssdt.aml (if installed)
11.	Post to:
	1.	[Realtek ALC Audio - InsanelyMac.com](http://www.insanelymac.com/forum/topic/308387-el-capitan-realtek-alc-applehda-audio/page-1)
	2. [Realtek ALC Audio - tonymacx86.com](http://www.tonymacx86.com/audio/143752-no-audio-devices-realtek-alc-applehda-guide.html)

Credit  
THe KiNG  
VHC888  
.:ErmaC:.  
bcc9  
RevoGirl  

toleda
https://github.com/toleda/audio_ALCInjection