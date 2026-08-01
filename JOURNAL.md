Here's where I'll journal before submitting to macondo!

## 2026-07-29 09:13:06

Just got this journal to work :D Made an obsidian vault with the datetime thingy so that this would do automatically, and that I don't have to worry about tracking time.

Since I'm doing this on KiCad, I had to search up the [symbol and footprint](https://www.snapeda.com/parts/SL2.1A/CoreChips%20ShenZhen%20CO.,Ltd/view-part/) :(

I spent ten minutes trying to get the symbol and footprints outside of EasyEDA, but I can't... I'm considering trying this with the SL2.1A instead

Turns out!!! I just copied the symbol from an existing [github repo](https://github.com/xunker/simple_sl2.1a_usb_hub) from 2 years ago. Can't find it anywhere else...
I did find the [datasheet](https://www.graylogix.in/wp-content/uploads/2025/07/2409271302_CoreChips-SL2-1A_C192893.pdf) though! It's just a google translated version of the original D:

Anyway, I believe the SL2.1A is also internal crystal so it won't be a problem if I just ground XIN hopefully!??! [Source](https://oshwlab.com/oshwlab/USB-concentrator-Based-on-SL2.1A)
![[Pasted image 20260729214740.png]]

Tried to match the pinout to the receptacle, so that I could use the same thing. I think I need to purchase different ports though, since this will be a different everything. I doubt I can pull the footprint out of EasyEDA so I'll just look for another later (hopes and prayers)

Currently following the guide for pin layouts, but I'm not too sure how to set the resistors to 5.1 kOhms

Nevermind you just double click and you get it :D 
![[Pasted image 20260729220539.png]]

Working through the rest of the pinouts is rather easy
![[Pasted image 20260729221116.png]]

Copied it over to the other ones and cleaned it up so it fit on an A5 Paper (I do that to practice cleanliness and packing :D )
![[Pasted image 20260729222917.png]]

Just realized there were still capacitors to do 0.o

2026-07-29 10:34:06

## 2026-07-31 04:22:59
Another day, another day. 

Anyway, I had the brilliant idea (we'll see how brilliant it is) to have two upstream usbc connections, and to be able to swap all the incoming connections to either cable 1 or cable 2 with a switch. Doing research about if that's possible right now.

Got into it, and heres what I learned:
- The +5v of each device CANNOT flow into each other, so use diodes
- The VBUS connection tells the computer whether or not it's connected, so i do have to switch the power connection over
- I might be able to use a MUX / multiplexer (need more research)

Mini side quest! **Multiplexers**
- Literally just a switch operated by either a LOW or HIGH input pin.
Side quest over! Very humbling

Anyway, after half an hour of research, I've come to these conclusions!

Materials
- USB Hub like I have right now
- USB 2.0 Multiplexer
- Single Pole Double Throw (i think) toggle switch that's panel mounted
	- If I panel mount this, might want a JST-PH 3pin connector instead of three wires and three pads

Picking parts!!

Multiplexer (TS3USB221ERSER) [Datasheet](https://www.ti.com/lit/ds/symlink/ts3usb221e.pdf) 
SPDT On-On 3pin toggle switch (MTS-102) [Amazon](https://www.amazon.com/HUAREW-MTS-102-Position-Locking-Switches/dp/B09W5FP2RM) Possible needs a connector but wtvr, three pin switch footprint/symbol can js be used :P 
* I do need the cad model for modelling though :D

Now I've got some work ahead of me.
First I've gotta make the screen bigger because A5 won't hold it all anymore :P
![[Pasted image 20260731172851.png|381]]

Now, to get on with the guide's capacitors! I've been putting that off--

How did I just realize the upstream and downstream CC1 and CC2 are wired differently??

Anyway, I changed to two usba since I have a keyboard and mouse usba dongle that I want to swap between two computers. 

2026-07-31 05:57:07

Looks kind of ugly but I blame the capacitors for having such a large schematic symbol >:(
![[Pasted image 20260731180105.png|467]]

Wired up the switch and the multiplexer. I'm hoping only the multiplexer needs a decoupling capacitor while the switch doesn't...
![[Pasted image 20260731182231.png]]

Looking it over again, I think the OutputEnable pin needs to be connected to ground instead of being left hanging. I'm kind of hoping the physical switch has enough of a pause in the middle to "unplug" host 1 and "plug" into host 2...

Also, I'm reading about ESD protection? Wonder if I need that. I'm going to post in hardware and ask about my current schematic before going any further though!
![[Pasted image 20260731183033.png]]
2026-07-31 06:28:20
