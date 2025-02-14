# Steps from https://keyhive.xyz/shop/sofle

BUILD GUIDE HERE: https://github.com/keyhive/build_guides/blob/master/docs/keyboards/sofle-rgb.md
    
    --> !! LOOK HERE TO SOLDER LEDS (?) !!



Firmware can be found here in QMK fork:
https://github.com/keyhive/qmk_firmware **does not work, old**
    --> fork original https://github.com/qmk/qmk_firmware **this repo**
        --> copied keybord to sofle_keyhive, deleted all non-sofle
         
You will want to use rev2 and keyhive_via
    --> COPIED TO THIS REPO (sofle_keyhive)
        --> rev2: folder in this repo 
            - **dont know** for what
        --> keyhive_via: folder in this repo
            - **KEYMAP**
                --> **Layout Editor at** https://github.com/keyhive/qmk_firmware/blob/master/keyboards/sofle/keymaps/keyhive_via/readme.md
            - OLED - Display
            --> **README** in this folder for Sofle for **flash**
            - **RGB_UNDERGLOW** in config.h
            
    

The following command should work:
qmk compile -kb sofle_keyhive/rev2 -km keyhive_via


**--> not working, see ERRORS, nicht mehr up-to-date --> andere sofle testen und anpassen ?**
    --> qmk compile -kb sofle/rev1 -km default 
            **is working !!! HIER WEITER !!!**
