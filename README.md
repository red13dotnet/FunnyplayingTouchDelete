# FunnyplayingTouchDelete
Completely deleting the touch sensor from Funnyplaying ITA and similar kits to remove accidental and false positive triggers of brightness and OSD menu.
You can remove the touch sensor from the Funnyplaying ITA and likely other Funnyplaying screen kits which share a similar touch control circuit.


I, like many others, have experienced problems with the touch sensor on my Funnyplaying ITA kit. 
In my case, everything would work normally for 30-40 minutes but then the brightness would start rapidly changing on its own or the OSD menu would pop up and change settings around.  This "bug" is easy to replicate with certain scenes in games as well as certain test patterns.  In my experience, the severity can also increase if the console has been on for longer.  
See below for reference a [makho](https://www.youtube.com/@makho) ([u/Admiral_Butter_Crust](https://www.reddit.com/user/Admiral_Butter_Crust/)) video demonstrating the same problem with a 3.0 IPS kit starting at 28:22.  I am kind of hoping he will find this interesting and examine some of the other Funnyplaying kits he has on hand to see if they can also be fixed in the same way.

[![Funnyplaying 3.0 Laminated IPS Kit for Game Boy Advance FRM Update](https://img.youtube.com/vi/mWBGmjLxyK0/0.jpg)](https://www.youtube.com/watch?v=mWBGmjLxyK0&t=1702s "Funnyplaying 3.0 Laminated IPS Kit for Game Boy Advance FRM Update")


I had considered just cutting off the touch pad from the ribbon cable but I have read posts by others indicating that the strange behavior persisted.
I can only surmise that this is due to electrical interference causing a change in the measured capacitance of the circuit itself.
 
 
The initial idea for the fix was inspired by a tweet by '@tailchao' https://twitter.com/tailchao/status/1482774836200058882?cxt=HHwWhMC9mfD275MpAAAA

They described the touch control circuit on a Funnyplaying Gameboy Color Retropixel 2.1  kit. and had found  that the touch sensor was controlled by a TC233A touch control chip. 

[Datasheet](https://github.com/red13dotnet/FunnyplayingTouchDelete/blob/e22346c71116e0eb99eca2700e2262e65421ffef/2202251530_Shenzhen-Fuman-Elec-TC233A_C2798022.pdf)

[English Translated Datasheet](https://github.com/red13dotnet/FunnyplayingTouchDelete/blob/a8f151cd3c60040361b5ef63581afe3d4881f6b5/ENG_TRANSLATED_2202251530_Shenzhen-Fuman-Elec-TC233A_C2798022.pdf)

Guessing that Funnyplaying would likely reuse parts of their designs across their different products, I checked the V3.2 PCB that came with my ITA kit and found the same TC233A chip.

![Component locations](https://github.com/red13dotnet/FunnyplayingTouchDelete/blob/5900527a5ed1d702002e2a67400b6d284d87c9a4/ITA_V3.2/FP_ITA_PCB_V3.2_Touch.png?raw=true)

From my reading of the datasheet, it may be possible to lower the sensitivity of the touch sensor by changing the values of C5 and R15 but, like many others, I am in the "Buttons Good, Touch Sensor Bad!" camp.
I proceeded to remove the chip after (partially?) tracing out the schematic and verifying that there was a pullup resistor on the output pin: 

![Partial? schematic](https://github.com/red13dotnet/FunnyplayingTouchDelete/blob/0d35d96eb914a9731e33d4843586f79f27cec914/ITA_V3.2/TC233A_Partial_Pinout.png?raw=true)

This can be done with a fine point soldering iron if you are careful.  Kapton, flux, solder wick and ceramic tweezers are your friend.



Don't forget to solder the L R and Select wires if you still want control of brightness and the OSD, otherwise all menu options will be stuck as you last had them set.



I have tested the system out after the fix and have had no further issues with brightness changing or the OSD activating on its own. 

I have no pictures of it working because it works just as it did before, except the brightness and OSD menu are no longer posessed.

I am guessing that this fix would apply to any Funnyplaying kit that has that chip but I don't have any other kits to check myself, so I created this github repo so anyone can contribute their own findings.  I am especially interested in learning which other kits are using the same touch controller.


In addition to the possibility 

