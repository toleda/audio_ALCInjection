audio_kext_enabler
============
OS X Realtek ALC885 through ALC1150 Onboard Audio

HDAEnabler1.kext installed with a Patched AppleHDA.kext enables OS X Realtek ALC onboard audio on Intel based motherboards with a bootable clean install of OS X. HDAEnabler1.kext injects Audio_ID = 1 for non-DSDT systems.

HDAEnabler1.kext supports 
1. Audio_ID: 1 for 3,  5 and 6 port Realtek ALC onboard audio
2. Realtek audio codecs: ALC885, ALC887, ALC888, ALC889, ALC892, ALC898, ALC1150

HDAEnabler2.kext supports 
1. Audio_ID: 2 for 3 port (5.1) Realtek ALC onboard audio
2. Realtek audio codecs: ALC887, ALC888, ALC889, ALC892, ALC898, ALC1150

HDAEnabler12.kext supports 
1. Audio_ID: 12 for other IM AppleHDA.kext solutions using layout12

Download
1. https://github.com/toleda/audio_kext_enabler
2. Select: HDAEnabler1.kext.zip or HDAEnabler2.kext.zip
3. Select: View Raw
4. Select: Save as .zip

Installation
Install Downloads HDAEnabler1.kext or HDAEnabler2.kext (not both) with Terminal, DPCIManager, Kext Wizard, Kext Utility, etc.

Troubleshooting
1. See https://github.com/toleda/audio_ALCInjection/README.txt

Credit
Kabyl

toleda
https://github.com/toleda/audio_kext_enabler
HDAEnabler1.kext.zip
HDAEnabler2.kext.zip
HDAEnabler12.kext.zip
README.txt