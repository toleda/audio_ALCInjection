![alt text](https://github.com/toleda/audio_RealtekALC/blob/master/sound.jpeg)
audio_ALCInjection
============
Realtek ALC/Desktop: 269(1), 283(1), 885, 887, 888, 892, 898 and 1150 on board audio  (1) BRIX/NUC only  
Supports OS X: 10.11, 10.10, 10.9 and 10.8  
Native AppleHDA

**OS X/Realtek ALC AppleHDA Injection**  

This guide enables OS X Realtek ALC onboard audio on Intel based motherboards with OS X. The Realtek AppleHDA.kext only works with the codec the kext was edited for and works with or replaces the native AppleHDA.kext.

**Updates**

v5: 5/10/17 - 200 Series/Kaby Lake Audio Support
v4: 1/18/16 - Clover ssdt hdef v4, codecdetect v1.2  
v3: 11/27/15 - ssdt_hdef supports with IOReg/HDEF, without IOReg/HDEF, AZAL, x99/ALZA and 100 Series/HDAS for all Intel Desktop motherboards.

**A. Audio/ALC Injection Status**

1. Download: [audio_codecdetect.command](https://github.com/toleda/audio_ALCInjection/blob/master/audio_codecdetect.command.zip) (select View Raw)
2. Confirm OS X support
	1. Codec (vendor/device id)
	2. Device (HDEF)
	3. Audio ID (1, 2 or 3)
3. Installation
	1. Double click Downloads/audio_codecdetect.command
	2. Results
		1. OK: Audio/ALC Injection
		2. NOK: problems/fixes
			1. specific ssdt
			2. Clover injection
4. Terminal/Shell/Export Text As...
	1. [audio_codecdetect.command](https://github.com/toleda/audio_ALCInjection/blob/master/terminal-codecdetect)

**B. Audio/ALC Injection techniques** select one method

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

4. Clover/Config.plist/Devices/Audio/Inject/1 (or 2, or 3)
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

**C. Audio ID Verification**

1. Restart
2. See A - Audio/ALC Injection Status

**D. Realtek ALC AppleHDA Audio Onboard Audio Solutions**

1. [Realtek ALC AppleHDA Installation Methods](https://github.com/toleda/audio_RealtekALC/blob/master/DETAILS.md)

**E. Requirements**

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

**F. Realtek ALCxxx** (verify codec and Audio ID)

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

**G. More Information**

1. [Audio ID Injection](https://github.com/toleda/audio_ALCInjection)
2. [Realtek ALC AppleHDA](https://github.com/toleda/audio_ALC_guides/blob/master/Realtek%20ALC%20AppleHDA.pdf)

    1. Installation
    2. Details/Support  
    3. Troubleshooting
2. [Realtek ALC guides](https://github.com/toleda/audio_ALC_guides)
	1. Enhancemants
		1. Customization
		2. Surround Sound
	2. Troubleshooting
		1. No Audio Devices
		2. No Sound
		3. No Audio After Sleep/Wake
	3. Utilities
		1. Identify Audio Codec
		2. Restore native AppleHDA9.  Surround Sound - Realtek ALC -  AppleHDA [Guide] 
4. [Terminal Saved Output](https://github.com/toleda/audio_RealtekALC/blob/master/Terminal:audio_realtekALC-110.command_v1.0a.txt)

**H. Tools**

1. [IOReg_v2.1](https://github.com/toleda/audio_ALCInjection/blob/master/IORegistryExplorer_v2.1.zip) (select View Raw)
2. [DPCIManger](http://sourceforge.net/projects/dpcimanager/)  
3. [MaciASL](http://sourceforge.net/projects/maciasl/)
4. [audio_codecdetect.command](https://github.com/toleda/audio_ALCInjection/blob/master/audio_codecdetect.command.zip) (select View Raw)
5. Property List Editors -
	1. [Xcode](https://developer.apple.com/xcode/)  
	2. Property List Editor, PlistEdit Pro, TextEdit, etc.
	3. TextEdit, TextWrangler (last resort)

**I. [Problem Reporting](https://github.com/toleda/audio_ALC_guides/blob/master/Problem%20Reporting.md)**

1. Problem Reporting/Post to
2. Problem Reporting/Attached requested files
	1. No files atached, reply unlikley

Credit  
THe KiNG  
VHC888  
.:ErmaC:.  
bcc9  
RevoGirl  

toleda
https://github.com/toleda/audio_ALCInjection