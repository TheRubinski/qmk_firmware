# Steps from https://keyhive.xyz/shop/sofle

BUILD GUIDE HERE: https://github.com/keyhive/build_guides/blob/master/docs/keyboards/sofle-rgb.md
    
    --> !! LOOK HERE TO SOLDER LEDS (?) !!



# Firmware QMK: fork
https://github.com/keyhive/qmk_firmware **does not work, old**
fork original https://github.com/qmk/qmk_firmware **use this repo**
        --> copied keybord to sofle_keyhive (from keyhive/qmk_firmware ?? ...), deleted all non-sofle 
         
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
            
            

# Compile in QMK MSYS
whitch to use?
qmk compile -kb sofle/rev1 -km rgb_default
    --> compiling fine
qmk compile -kb sofle/keyhive -km rgb_default
    --> compiling fine


dont use:
qmk compile -kb sofle_keyhive/rev2 -km keyhive_via
    --> not working, see ERRORS, nicht mehr up-to-date 
qmk compile -kb sofle/rev1 -km default 
    --> working, DONT use




# Flash 
https://docs.qmk.fm/newbs_flashing
- **indicator working, party, party**
-> connect7bridge both reset shortly and quickly klick flash in QMK Toolbox, else you will get a device disconnected. Probably because PCB will leave Bootloader Mode (DFU)

- used hex: C:\Users\ruben\OneDrive\qmk_firmware\sofle_keyhive_rgb_default.hex 
- MCU is: ATmega32U4
    -> works, but wrong hand ... 

- used hex: C:\Users\ruben\OneDrive\qmk_firmware\sofle_rev1_rgb_default.hex
- MCU is: ATmega32U4
    -> also works, but correct hand ... 
    
**YOU MAY HAVE TO ADAPT LED NUMBER IN CODE !!!**
    -> config.h
        -> RGBLIGHT_LED_COUNT 35 -> 36
        -> RGBLED_SPLIT { 35, 35 } -> { 36, 36 }
        
        
**maybe follow readme.md in sofle folder ...**

**Problems? -> Check out QMK Discord**
