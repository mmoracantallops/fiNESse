# fiNESse
Final Integrated NES Special Edition: Integration and adaptation of the best NES projects (TinyNES, NESRGB, OpenTendo and Power Module Redesign) in a single modern unit.

TinyNES: https://www.crowdsupply.com/tall-dog-electronics/tinynes

TinyNES: https://github.com/loglow/TinyNES

OpenTendo: https://github.com/Redherring32/OpenTendo

NESRGB: https://etim.net.au/nesrgb/

MerlinShaw's Power Modules: https://github.com/ShawMerlin/NES-Power-Module-Redesign

# Features (and limitations)
- Only NTSC (once you go 60Hz, there is no turning back), so RP2A03 / RP2C02, as the clock generator uses the NTSC frequency.
- Main board:
    - Similar features as the TinyNES project, although some features have been changed, simplified or adapted to my project (for instance, no USB or TRRS or clone compatibility here).
    - Modern ICs. All components are new and available.
    - Programmable clock generator (SIT2001BC-S2-33N-21.477270).
    - Reset supervisor (APX811).
    - Sockets to place the NESRGB Board wirelessly. Also taking external composite and audio from it.
    - Composite video generation and audio amplifier (internal).
    - Expansion audio connected.
- Power board:
    - Mini Din9 connector (MD/genesis 2 cable).
    - Rectifier (all polarities allowed).
    - Power load switch which provide full protection to systems and loads which may encounter large current conditions.
    - 5V step-down regulator.
    - Pseudo-stereo (separated channels CPU1 and CPU2). Mono is also mixed with both (adjustable on how much) so expansion audio is also mixed if desired.
    - Stereo audio is amplified with the same buffer as the original design.
    - Three-way switch (CVBS - mono, CSync - stereo, Csync - mono).
    - Much better routing and cleaner ground plane - although still not quite as good as Merlin Shaw's designs :)
    - Power LED (can be disabled or not populated).
    - 20 pin row to pass all the signals and ground connection between boards.
    - RCA connectors for composite video and audio.
 
# BOM
The current BOM is included here; I'm not sure whether I included everything but I did my best. If you notice some element is missing, please let me know. There are a few things that could be changed in the power board (e.g. the power regulator) for better availability, but I'll leave that for a future update. Of course, these are the components I had either because I based my design in the TinyNES or Merlin Shaw's or my own preferences and availability. Feel free to change anything if you feel like it.

# Pictures

## KiCAD
Gerbers are included. I might upload the full schematics and board once I find the time to clean them a little bit. These are the 3D models uploaded.
![FINESSE](https://github.com/mmoracantallops/fiNESse/assets/19650480/dc6eae44-6636-485a-b3d3-e4c67ce70106)
![NES_POWER_FINESSE](https://github.com/mmoracantallops/fiNESse/assets/19650480/b70ba29b-b6c7-4c67-8719-3736fa6ba0c6)

## Main board

This is the produced (prototype) board:
![PXL_20231222_171900354](https://github.com/mmoracantallops/fiNESse/assets/19650480/fa83c0c5-e9d4-4c3f-9673-916304a48d2f)
![PXL_20231222_171908056](https://github.com/mmoracantallops/fiNESse/assets/19650480/0b873b8c-1dc4-4270-8a8e-9175dc5d1398)

Now, with the components soldered in place. Only the power/reset and controller connectors are sourced from another (preferably dead) NES. The 72 pin conector and load mechanism are also taken from another dead unit.

![PXL_20240118_234944957](https://github.com/mmoracantallops/fiNESse/assets/19650480/5ff2cf66-8c33-4d7d-8b05-01080ef068da)
![PXL_20240119_065805355](https://github.com/mmoracantallops/fiNESse/assets/19650480/29c1e7a6-cab6-4591-bfca-ec18c006a6e2)
![PXL_20240119_065819091](https://github.com/mmoracantallops/fiNESse/assets/19650480/adcf6431-006b-4d76-9724-aef248d946a8)

## Power board
And this is the companion power board, with direct RGB lines, etc.
![PXL_20231222_171919818](https://github.com/mmoracantallops/fiNESse/assets/19650480/fa15a431-9733-4c96-9519-05df78bbd706)
![PXL_20231222_171925780](https://github.com/mmoracantallops/fiNESse/assets/19650480/5a356d89-5003-4e3c-9d7e-ea853bf9a649)

And here with all the components soldered except the 20 pins that connect the board to the main board.
![PXL_20240122_130042615](https://github.com/mmoracantallops/fiNESse/assets/19650480/ced9084e-a4f7-4f86-8770-a9aaa8f8b96e)

Finally, installed together with the main board and the soldered (tall - 21mm) pins:
![PXL_20240122_134008894](https://github.com/mmoracantallops/fiNESse/assets/19650480/79988480-2fc8-4138-983f-3f38a204e5b3)


## RGB Board
If the PPU is installed in the PPU slot and the switch set to internal video/audio, the console will output a (quite clean) composite video through the yellow RCA conector. But this is designed to be used with the NESRGB board, which fits perfectly and allows for a clean wireless installation and removal. In this picture, the pins are not soldered, but you get the idea. 

![PXL_20240122_134230574](https://github.com/mmoracantallops/fiNESse/assets/19650480/e7b4c03f-7c3e-4832-9d68-8703b6d20963)

## Final Unit
Here is how it looks when finished. There is a potentiometer for the Expansion Audio and a Int/Ext Video/Audio on the main board and two potentiometers for the pseudo-stereo in the daughter power board.
![PXL_20240122_134018752](https://github.com/mmoracantallops/fiNESse/assets/19650480/5de5649b-2526-427c-b0e5-bb20c8f78c4e)


## Extras: case

If you feel fancy, you can even use one of RetroGame Restore (https://retrogamerestore.com/) replacement shells and install both the MD2 type cable and the multiout one:
![PXL_20231222_110154607](https://github.com/mmoracantallops/fiNESse/assets/19650480/ad56db23-e85a-41dc-9e84-2411e466c386)
![PXL_20231222_110146651](https://github.com/mmoracantallops/fiNESse/assets/19650480/c3b650da-2eaf-47ca-8266-d5480bd9aec5)

The metal sticker for the name/logo is from an etsy shop.
![PXL_20231222_105852839](https://github.com/mmoracantallops/fiNESse/assets/19650480/ae434506-102b-40a8-8c75-e206f6e7abc8)

It works beautifully (at least in my humble opinion):
![PXL_20231222_105843751](https://github.com/mmoracantallops/fiNESse/assets/19650480/08c14af0-8dae-40b2-9833-096b3c707192)
