# How To

Tested with qmk 0.16.9

## Install Python

You'll need python >= 3.7. Since I was using ubuntu 18.04 at the time, I
elected to use a venv.

## Install qmk

```
python -m pip install qmk
qmk setup
```
Make sure the udev rules get copied over correctly and pay attention to the
warnings. You will not be able to flash if the microcontroller can't be
detected.

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
