---
layout:     post
title:      "Voiding the warranty on my keyboard"
date:       2019-07-07 14:22:00
summary:    Installing the Hasu FC660C controller.
categories: blog
---

![top: original; bottom: hasu]({{ site.images }}/controllers.jpg)
_top: stock FC660C controller; bottom: Hasu FC660C controller_

I'm the proud owner of a [Leopold
FC660C](https://mechanicalkeyboards.com/shop/index.php?l=product_detail&p=3829)
keyboard. I love the feel of the Topre switches, and it's the perfect size. The
layout, however, is not _quite_
perfect.

For instance, I prefer to use Caps Lock as an Escape key. The backtick/tilde key
on the FC660C shares a spot with Escape, which is slightly weird. I also like to
switch LCtrl and LGui. I cobbled together a software solution to get the layout
I wanted, using a combination of [Karabiner
Elements](https://pqrs.org/osx/karabiner/) and the macOS keyboard options. But
if I ever wanted to use my keyboard on a different computer, I'd have to set it
up all over again.

This weekend I switched out the keyboard's stock controller for the [Hasu FC660C
Controller](https://www.1upkeyboards.com/shop/controllers/fc660c-controller/).
Now my keyboard is fully programmable! No extra software configuration on
different computers.

I'm not well-versed in electronics, and I was terrified of screwing up my
precious keyboard or the Hasu controller. But the installation turned out to be
super straightforward. I'm really happy with the results.

## Links
* [Installation instructions from Hasu himself](https://geekhack.org/index.php?topic=90317.0)
* [Great video on installing controller (flashing steps are Windows-only, though)](https://www.youtube.com/watch?v=TYmAb8zOPWU&feature=youtu.be&t=3m6s)
* [Keymap editor to generate the hex file](http://www.tmk-kbd.com/tmk_keyboard/editor/unimap/?fc660c)

## Steps followed (macOS)
1. `brew install dfu-programmer`
1. On the back of the keyboard, remove the "OK" warranty sticker and the black
   screw underneath
1. Gently pry open the gap between the back and the front bezel; insert a few
   credit cards to keep it open
1. Slowly, carefully, pry and pop off the bezel
1. Unscrew the controller from the back (2 smaller silver screws)
1. Remove the ribbon cable from the stock controller
1. Insert the ribbon cable into the Hasu controller
1. Screw down the Hasu controller
1. Replace the screw on the back
1. Pop the front bezel back on
1. Plug the keyboard in and verify that it works
1. Use the [keymap
   editor](http://www.tmk-kbd.com/tmk_keyboard/editor/unimap/?fc660c) to set the
   desired layout and download the resulting hex file (`unimap.hex`)
1. Press the button on the back of the keyboard on the Hasu controller (where
   the dipswitches on the stock controller used to be) to put the controller in
   bootloader mode
1. Clear the current controller memory
  ```
  $ dfu-programmer atmega32u4 erase --force
  Erasing flash...  Success
  Checking memory from 0x0 to 0x6FFF...  Empty.
  ```
1. Load the new hex file
  ```
  $ dfu-programmer atmega32u4 flash ~/Downloads/unimap.hex
  Checking memory from 0x0 to 0x6FFF...  Empty.
  0%                            100%  Programming 0x7000 bytes...
  [>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]  Success
  0%                            100%  Reading 0x7000 bytes...
  [>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]  Success
  Validating...  Success
  0x7000 bytes written into 0x7000 bytes memory (100.00%).
  ```
1. Reset the controller state
  ```
  $ dfu-programmer atmega32u4 reset
  ```
