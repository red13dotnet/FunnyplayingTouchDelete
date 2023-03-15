# FunnyplayingTouchDelete
Completely Deleting The Touch sensor from Funnyplaying ITA and similar kits.
You can remove the touch sensor from the Funnyplaying ITA and likely other Funnyplaying screen kits.


I, like many others, have experienced problems with the touch sensor on my Funnyplaying ITA kit. 
In my case, everything would work normally for 30-40 minutes but then the brightness would start changing on its own or the OSD menu would pop up and change settings around.

I had considered just cutting off the touch pad from the ribbon cable but I have read posts by others indicating that the strange behavior persisted.
I can only surmise that this is due to electrical interference causing a change in the measured capacitance of the circuit itself.
 
The initial idea for the fix was inspired by a tweet by '@tailchao' https://twitter.com/tailchao/status/1482774836200058882?cxt=HHwWhMC9mfD275MpAAAA
They described the touch control circuit on a Funnyplaying Gameboy Color Retropixel 2.1  kit. and had found  that the touch sensor was controlled by a TC233A touch control chip. 

Datasheet: https://github.com/red13dotnet/FunnyplayingTouchDelete/blob/e22346c71116e0eb99eca2700e2262e65421ffef/2202251530_Shenzhen-Fuman-Elec-TC233A_C2798022.pdf

Eng Translated Datasheet: https://github.com/red13dotnet/FunnyplayingTouchDelete/blob/a8f151cd3c60040361b5ef63581afe3d4881f6b5/ENG_TRANSLATED_2202251530_Shenzhen-Fuman-Elec-TC233A_C2798022.pdf

On a hunch, I checked the V3.2 PCB that came with my ITA kit and found the same TC233A chip.

I proceeded to remove the chip after tracing out the schematic and verifying that there was a pullup resistor on the output pin: 



This can be done with a fine point soldering iron if you are careful.  Kapton, flux, solder wick and ceramic tweezers are your friend.

Don't forget to solder the L R and Select wires if you still want control of brightness and the OSD, otherwise all menu options will be stuck as you last had them set.


I have tested the system out after the fix and have had no further issues with brightness changing or the OSD activating on its own. 

I am guessing that this fix would apply to any Funnyplaying kit that has that chip but I don't have any other kits to check myself, so I created a github repo for anyone to contribute their own findings.  I am especially interested in which other kits are using the same touch controller.


