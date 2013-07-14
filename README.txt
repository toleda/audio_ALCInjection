audio_ALCInjection
============
OS X Realtek ALC885 through ALC898 Onboard Audio

This guide enables OS X Realtek ALC onboard audio on Intel based motherboards with a bootable clean install of OS X. The Patched AppleHDA.kext only works with the codec the kext was edited for and replaces the native AppleHDA.kext.

Patched ALC AppleHDA Guides:
[Guide] Add or Edit dsdt/HDEF.pdf
ML-Clover Patched ALC AppleHDA Injection.pdf
ML-Patched ALC AppleHDA Capabilities.pdf
ML-Patched ALC AppleHDA Screenshots.pdf
ML-Customizing the Patched AppleHDA.pdf

In ML, The Patched ALC AppleHDA.kext supports 6 Realtek audio codecs:
ALC885, ALC887, ALC888, ALC889, ALC892, ALC898

For each supported codec, the Patched ALC AppleHDA.kext supports 3 Audio_IDs:
Audio_ID: 1 supports 5 and 6 port ALC8xx onboard and/or AMD/Nvidia HDMI audio  
Audio_ID: 2 supports 3 port ALC8xx onboard and/or AMD/Nvidia HDMI audio
Audio_ID: 3 supports 3, 5 and 6 port ALC8xx onboard, HD4K/HD3K and AMD/Nvidia HDMI 	audio

Note: The native AppleHDA.kext supports HDMI audio (dsdt edits required) even with an unsupported onboard audio codec using Audio ID: 1. 

The are three techniques to enable the Patched ALC AppleHDA.kext:
1. No dsdt/audio enabler = Audio_ID, install either enabler (use 1a or 1b, not both)
1a. Audio_ID = 1, HDAEnabler1.kext 
1b. Audio_ID = 2, HDAEnabler2.kext
2. dsdt/HDEF/layout-id = Audio_ID, see {Guide} Add or Edit dsdt/HDEF.pdf
2a. Audio_ID = 1, 0x01, 0x00, 0x00, 0x00, 0x00
2b. Audio_ID = 2, 0x02, 0x00, 0x00, 0x00, 0x00
2c. Audio_ID = 3, 0x03, 0x00, 0x00, 0x00, 0x00
3. Clover/Config.plist/PCI/HDAInjection, see ML-Clover Patched ALC AppleHDA Injection.pdf
3a. Audio_ID = 1, HDAInjection=1
3b. Audio_ID = 2, HDAInjection=2
3c. Audio_ID = 3, HDAInjection=3

Once the Patched ALC AppleHDA audio is enabled, select the appropriate codec
1. https://github.com/toleda/audio_ALC885 Download ZIP
2. https://github.com/toleda/audio_ALC887 Download ZIP
3. https://github.com/toleda/audio_ALC888 Download ZIP
4. https://github.com/toleda/audio_ALC889 Download ZIP
5. https://github.com/toleda/audio_ALC892 Download ZIP
6. https://github.com/toleda/audio_ALC898 Download ZIP 

Installation
Install Patched ALC898 AppleHDA.kext with Terminal, DPCIManager, Kext Wizard, etc.

Troubleshooting
1. ML-Patched ALC AppleHDA Capabilities.pdf
2. Post to http://www.insanelymac.com
3. Post to http://www.tonymacx86.com/audio/76309-mountain-lion-multibeast-no-audio-solutions-problem-reporting.html

Credit
THe KiNG 
VHC888
.:ErmaC:.
RevoGirl

toleda
https://github.com/toleda/audio_ALCInjection
Patches
[Guide] Add or Edit dsdt/HDEF.pdf
ML-Clover Patched ALC AppleHDA Injection.pdf
ML-Patched ALC AppleHDA Capabilities.pdf
ML-Patched ALC AppleHDA Screenshots.pdf
ML-Customizing the Patched AppleHDA.pdf
zlib_terminal
README.txt