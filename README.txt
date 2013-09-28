audio_ALCInjection
============
OS X Realtek ALC885 through ALC1150 Onboard Audio

This guide enables OS X Realtek ALC onboard audio on Intel based motherboards with a bootable clean install of OS X. The Realtek AppleHDA.kext only works with the codec the kext was edited for and replaces the native AppleHDA.kext.

Realtek ALC AppleHDA Guides:
[Guide] Add or Edit dsdt-HDEF.pdf
[Guide] Add ssdt-HDEF.pdf
ML-Clover Realtek ALC AppleHDA Injection.pdf
ML-Realtek ALC AppleHDA Capabilities.pdf
ML-Realtek ALC AppleHDA Screenshots.pdf
ML-Customizing the Realtek AppleHDA.pdf

IORegistryExplorer_v2.1

In ML, The Realtek ALC AppleHDA.kext supports 7 Realtek audio codecs:
ALC885, ALC887, ALC888, ALC889, ALC892, ALC898, ALC1150/10.8.5 only

Three Realtek ALC AppleHDA.kext Audio_IDs, select one
Audio_ID: 1 supports 5 and 6 port ALC8xx onboard and/or HD5K/AMD/Nvidia HDMI audio  
Audio_ID: 2 supports 3 port ALC8xx onboard and/or HD5K/AMD/Nvidia HDMI audio
Audio_ID: 3 supports 3, 5 and 6 port ALC8xx onboard HD4K/HD3K HDMI audio
		with or without AMD/Nvidia HDMI audio
Audio_IDs: 1 and 2 support analog 5.1 surround sound, 3 does not
Audio_IDs: 1, 2 and 3 require HDMI audio dsdt edits for HDMI audio
Audio_ID: 3, not supported with ALC1150.

Note: The native AppleHDA.kext supports HDMI audio (dsdt edits required) even with an unsupported onboard audio codec using Audio ID: 1. 

Four techniques enable the Realtek ALC AppleHDA.kext, select one
http://www.insanelymac.com/forum/topic/290796-realtek-alc-applehda-audio-injection/
1. No dsdt/audio enabler = Audio_ID, install either kext (use 1a or 1b, not both)
https://github.com/toleda/audio_kext_enabler
1a. Audio_ID = 1/HDAEnabler1.kext.zip 
1b. Audio_ID = 2/HDAEnabler2.kext.zip
2. dsdt/HDEF/layout-id = Audio_ID, see {Guide} Add or Edit dsdt/HDEF.pdf
https://github.com/toleda/audio_ALCInjection
2a. Audio_ID = 1/layout-id: 0x01, 0x00, 0x00, 0x00, 0x00
2b. Audio_ID = 2/layout-id: 0x02, 0x00, 0x00, 0x00, 0x00
3. ssdt/HDEF/layout-id = Audio_ID, see {Guide} Add ssdt/HDEF.pdf
https://github.com/toleda/audio_ssdt_enabler
3a. Audio_ID = 1/audio_ssdt-hdae-1.zip
3b. Audio_ID = 2/audio_ssdt-hdae-2.zip
4. Clover/Config.plist/PCI/Devices, see ML-Clover Realtek ALC AppleHDA Injection.pdf
https://github.com/toleda/audio_ALCInjection
4a. Audio_ID = 1/Audio/Inject=1
4b. Audio_ID = 2/Audio/Inject=2

Once the Realtek ALC AppleHDA audio is enabled, select the appropriate codec
1. https://github.com/toleda/audio_ALC885
2. https://github.com/toleda/audio_ALC887
3. https://github.com/toleda/audio_ALC888
4. https://github.com/toleda/audio_ALC889
5. https://github.com/toleda/audio_ALC892
6. https://github.com/toleda/audio_ALC898
7. https://github.com/toleda/audio_ALC1150
 
Troubleshooting
1. ML-Realtek ALC AppleHDA Capabilities.pdf 
2. Post to http://www.insanelymac.com/forum/topic/290796-realtek-alc-applehda-audio-injection/
3. Post to http://www.tonymacx86.com/audio/76309-mountain-lion-multibeast-no-audio-solutions-problem-reporting.html

Credit
THe KiNG 
VHC888
.:ErmaC:.
bcc9
RevoGirl

toleda
https://github.com/toleda/audio_ALCInjection
Patches
[Guide] Add or Edit dsdt-HDEF.pdf
[Guide] Add ssdt-HDEF.pdf
IORegistryExplorer_v2.1
ML-Clover Realtek ALC AppleHDA Injection.pdf
ML-Realtek ALC AppleHDA Capabilities.pdf
ML-Realtek ALC AppleHDA Screenshots.pdf
ML-Customizing the Realtek AppleHDA.pdf
zlib_terminal
README.txt