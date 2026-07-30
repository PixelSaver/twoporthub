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
