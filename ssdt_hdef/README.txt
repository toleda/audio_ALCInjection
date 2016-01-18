audio_ALCInjection/ssdt_hdef
============
OS X Realtek ALC885 through ALC1150 Onboard Audio with ssdt injection

ssdt_hdef-1-100-hdas
Supports Realtek ALC/Audio ID; 1 - 100 Series/all motherboard audio configurations
Replaces HDAS with HDEF, injects Audio ID: 1 (layout-id: 0x01, 0x00, 0x00, 0x00)

ssdt_hdef-1-no_ioreg/hdef
Supports Realtek ALC/Audio ID; 1 - all motherboard audio configurations
Injects Device (HDEF) and Audio ID: 1 (layout-id: 0x01, 0x00, 0x00, 0x00)

ssdt_hdef-1-with_ioreg/azal
Supports Realtek ALC audio
Injects Audio ID: 1 (layout-id: 0x01, 0x00, 0x00, 0x00)

ssdt_hdef-1-with_ioreg/hdef
Supports Realtek ALC audio
Injects Audio ID: 1 (layout-id: 0x01, 0x00, 0x00, 0x00)

ssdt_hdef-1-x99_alza
Supports Realtek ALC/Audio ID; 1 - X99 Series/all motherboard audio configurations
Replaces ALZA with HDEF, injects Audio ID: 1 (layout-id: 0x01, 0x00, 0x00, 0x00

ssdt_hdef-2-100-hdas
Supports Realtek ALC/Audio ID; 2 - 100 Series/5.1 analog surround on 3 audio ports
Replaces HDAS with HDEF, injects Audio ID: 2 (layout-id: 0x01, 0x00, 0x00, 0x00)

ssdt_hdef-2-no_ioreg/hdef
Supports Realtek ALC/Audio ID; 2 - 5.1 analog surround on 3 audio port motherboards
Injects Device (HDEF) and Audio ID: 2 (layout-id: 0x02, 0x00, 0x00, 0x00)

ssdt_hdef-2-with_ioreg/hdef
Supports Realtek ALC/Audio ID; 2 - 5.1 analog surround on 3 audio port motherboards
Injects Audio ID: 2 (layout-id: 0x02, 0x00, 0x00, 0x00)

ssdt_hdef-3-100-hdas
Supports Realtek ALC/Audio ID; 3 - 100 Series/HD5xx HDMI and motherboard audio
Replaces HDAS with HDEF, injects Audio ID: 3 (layout-id: 0x03, 0x00, 0x00, 0x00

ssdt_hdef-3-no_ioreg/hdef
Supports Realtek ALC/Audio ID; 3 - HD3000/HD4000 HDMI and motherboard audio
Injects Device (HDEF) and Audio ID: 3 (layout-id: 0x03, 0x00, 0x00, 0x00)

ssdt_hdef-3-with_ioreg/hdef
Supports Realtek ALC/Audio ID; 3 - HD3000/HD4000 HDMI and motherboard audio
Injects Audio ID: 3 (layout-id: 0x03, 0x00, 0x00, 0x00)

RealtekALC audio
1. https://github.com/toleda/audio_RealtekALC
2. https://github.com/toleda/audio_CloverALC

Installation (included in download)
1. [Guide]-OSX_ssdt-installation

toleda
https://github.com/toleda/audio_ALCInjection/ssdt_hdef
README.txt