# ZX48K-AllInOne

## Introduction

This is an upgraded version of previous [ZX48K-Essentials](https://github.com/tomekszafranski/ZX48K-Essentials) project (ZX Spectrum 48K clone based on vLA82S+ ULA replacement). It adds couple of useful modifications you would like to see in nowadays ZX Spectrum.

Again, it has to be said that this is not by any means revoluotinary work. There are similar projects out there, this is simply my take on the subject.

## Modifications

Compared to ZX48K-Essentials, following modification have been added.

**Turbo Sound Interface**

Turbo Sound extension is based on original work of [NedoPC](http://www.nedopc.com/TURBOSOUND/ts.php) however, no output amplifier is used. It gives you 6 channels stereo outpout. Yamaha YM2149F or AY-3-8910 chips can be used. Channel mapping is ABC. Stereo output is always available through additional jack connector. Mono TV sound can be selected by jumper. This can be tested with AYtest_0.2.tap program.

**Kempston joystick interface**

Commonly used version of Kempston joystick interface. It can be disabled by jumper in case you connect other extension with joystick interface. Test it with IN 31 command.

**80KB of RAM**

This is based on East London Robotics SP80 Memory Extension that uses remaing 32KB of Upper RAM (while using fully working 4164 chips) for simple bank switching. However, activaton address 65407/49023 has been changed to 7FFDh (32765) as it interfered with my divMMC interface. OUT 7FFDh,x command switches upper 32KB of RAM (for the first time that resets computer as the stack is cleared). If not needed you can use jumper to come back to original 32KB version. See how it works in [HappyLittleDiodes video](https://www.youtube.com/watch?v=CDxwBFpwiEk). 

**EEPROM selector**

Since W27C512 EEPROM (64KB) is used you have the possibility to have four different ROMS configurable with two jumpers for EEPROM's A15 and A14 lines.

**External Keyboard connector**

There is IDC16 connector for external keyboard. I don't know about any standard so I followed pin assignment described in [ZX81 Keybord Adventure](https://www.zx81keyboardadventure.com/p/zx-key-keyboard-guide-book.html). 
You can use original ZX Spectrum or ZX Spectrum+ keyboard, ZX81 keyboard or keyboards designed for Harlequin – one with tactile switches or one with mechanical switches using Keyboard adpater from ZX48K-RC2014 project.


## Board

Fully asembled ZX48K-AllInOne PCB in purple. 

Tested with [Diagnostic ROM](https://blog.retroleum.co.uk/electronics-articles/a-diagnostic-rom-image-for-the-zx-spectrum/), [divMMC Future](https://www.tfw8b.com/product/divmmc-future-sinclair-zx-spectrum/), ZX Interface 2 and [MaxDuino](https://lotharek.pl/productdetail.php?id=409).

## Remarks

* Decoupling 100nF capacitors are unmarked and located near most of the ICs.

* vLA82S+ is equiped with write-only AY-3-8910 Sound emulator so if not needed Turbo sound section can be ommited.


Have fun!

Tomek

> [!NOTE]
> Disclaimer: This is my project that I’ve built and it works for me. You can do it as well but remember, you’re responsible for your doings and the consequences, not me.

