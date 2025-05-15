# ZX48K-AllInOne

## Introduction

This is an upgraded version of previous [ZX48K-Essentials](https://github.com/tomekszafranski/ZX48K-Essentials) project (minimal ZX Spectrum 48K clone based on vLA82S+ ULA replacement). It adds couple of useful modifications you would like to see in nowadays version of ZX Spectrum.

Again, it has to be said that this is not by any means revolutionary work. There are similar projects out there, this is simply my take on the subject.

## Modifications

Compared to ZX48K-Essentials board, following modification have been added.

**Turbo Sound extension**

Turbo Sound extension is based on original work of [NedoPC](http://www.nedopc.com/TURBOSOUND/ts.php) however, no output amplifier is used. Turbo Sound gives you 6 channels output. Both Yamaha YM2149F or AY-3-8910 chips can be used. Channel mapping is ABC. Stereo output is always available through additional jack connector. Mono TV sound can be selected by jumper (instead of output from vLA82S+ that has built-in write-only AY-compatible sound generator). Turbo Sound operation can be tested with AYtest_0.2.tap program.

**Kempston joystick interface**

Commonly used version of Kempston joystick interface with on/off jumper to disable it in case you connect other extension with joystick interface. Operation can be tested using IN 31 command.

**80KB of RAM**

This is based on East London Robotics SP80 Memory Extension that using simple logic utilitizes remaining 32KB of Upper RAM (while using fully working 4164 chips) for simple bank switching. However, activation address 65407/49023 has been changed to 32765 (7FFDh) as it interfered with divMMC interface. OUT 32765,x command switches banks of upper 32KB RAM (for the first time that resets computer as the stack is cleared). If not needed can be disabled by jumper. For more info on how it works, see [HappyLittleDiodes video](https://www.youtube.com/watch?v=CDxwBFpwiEk). 

**EEPROM selector**

Since W27C512 EEPROM (64KB) is used there is the possibility to have four different ROMS configurable with two jumpers (EEPROM's A15 and A14 lines).

**External keyboard connector**

There is IDC16 connector for external keyboard. I don't know about any standard so I followed pin assignment described in [ZX81 Keyboard Adventure](https://www.zx81keyboardadventure.com/p/zx-key-keyboard-guide-book.html). You can use original ZX Spectrum or ZX Spectrum+ keyboard, ZX81 keyboard or keyboards designed for Harlequin – one with tactile switches or one with mechanical switches using Keyboard adapter from [ZX48K-RC2014](https://github.com/tomekszafranski/ZX48K-RC2014) project.


## Board

KiCad 

![ZX48K-AllInOne_board](https://github.com/user-attachments/assets/2007c883-72d8-415d-9168-c41c120f3f49)

Fully assembled ZX48K-AllInOne PCB in purple. 

Tested with [Diagnostic ROM](https://blog.retroleum.co.uk/electronics-articles/a-diagnostic-rom-image-for-the-zx-spectrum/), [divMMC Future](https://www.tfw8b.com/product/divmmc-future-sinclair-zx-spectrum/), ZX Interface 2 and [MaxDuino](https://lotharek.pl/productdetail.php?id=409).

[here]

## Remarks

* Unmarked components located near most of the ICs are 100nF decoupling capacitors.

* vLA82S+ is equipped with sound generator so if not needed Turbo Sound section can be omitted.

Have fun!

Tomek

> [!NOTE]
> Disclaimer: This is my project that I’ve built and it works for me. You can do it as well but remember, you’re responsible for your doings and the consequences, not me.

