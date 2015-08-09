audio_ALCInjection/ssdt_hdef
============
OS X Realtek ALC885 through ALC1150 Onboard Audio with ssdt injection

ssdt_hdef-1-no_ioreg/hdef
Supports Realtek ALC/Audio ID; 1 - all motherboard audio configurations
Injects Device (HDEF) and Audio ID: 1 (layout-id: 0x01, 0x00, 0x00, 0x00)

ssdt_hdef-1-with_ioreg/hdef
Supports Realtek ALC audio
Injects Audio ID: 1 (layout-id: 0x01, 0x00, 0x00, 0x00)

ssdt_hdef-2-no_ioreg/hdef
Supports Realtek ALC/Audio ID; 2 - 5.1 analog surround on 3 audio port motherboards
Injects Device (HDEF) and Audio ID: 2 (layout-id: 0x02, 0x00, 0x00, 0x00)

ssdt_hdef-2-with_ioreg/hdef
Supports Realtek ALC audio
Injects Audio ID: 2 (layout-id: 0x02, 0x00, 0x00, 0x00)

ssdt_hdef-3-no_ioreg/hdef
Supports Realtek ALC/Audio ID; 3 - HD3000/HD4000 HDMI and motherboard audio
Injects Device (HDEF) and Audio ID: 3 (layout-id: 0x03, 0x00, 0x00, 0x00)

ssdt_hdef-3-with_ioreg/hdef
Supports Realtek ALC audio
Injects Audio ID: 3 (layout-id: 0x03, 0x00, 0x00, 0x00)

hdef-1/hdef-2/hdef-3/with_ioreg/hdef/no_ioreg/hdef ???
1. [Guide]-OSX-hdmi_audio-hdef_audio-ssdt_v3, https://github.com/toleda/audio_hdmi_guides

RealtekALC audio
1. https://github.com/toleda/audio_RealtekALC
2. https://github.com/toleda/audio_CloverALC

Installation (included in download)
1. [Guide]-OSX_ssdt-installation

Problem Reporting
1. See https://github.com/toleda/audio_RealtekALC/blob/master/DETAILS.md

toleda
https://github.com/toleda/audio_ALCInjection/ssdt_hdef
README.txt