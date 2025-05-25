# How To

Tested with qmk 1.1.7

## Install qmk

Assuming `uv` is installed, this is as simple as

```
uv tool install qmk
```

## Clone this repo

```
cd <qmk_source>/keyboards/crkbd/keymaps
git clone https://github.com/DevonMorris/crkbd-devo.git
# Alternatively use ssh
```

## Flash the keyboard

Here you have to be careful to select the correct bootloader, which depends on
your selected microcontroller. [You can find more info here](https://docs.qmk.fm/#/flashing).

For DFU boards (Elite-C V4) use
```
qmk flash -kb crkbd -km devo -bl dfu-split-left
qmk flash -kb crkbd -km devo -bl dfu-split-right
```

For Caterina boards (Arduino ProMicro)

```
qmk flash -kb crkbd -km devo -bl avrdude-split-left
qmk flash -kb crkbd -km devo -bl avrdude-split-right
```
