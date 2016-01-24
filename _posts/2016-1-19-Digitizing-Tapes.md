---
layout: post
title: Digitizing 90's Camcorder tapes for $8
---

If your family was anything like mine, then at some point you've likely owned one of those bulky, black, rectangular Sony Handycam camcorders from the 90's.

More specifically, my dad bought this sad looking Sony Handycam Hi8 way back in 1995.

![camcorder picture] (http://i.imgur.com/4lQtgRL.jpg)
*The Sony Handycam CCD-TR70*

---

#### What the heck is Hi8?

You see back in the 80's and 90's JVC reigned supreme with their 'VHS-C' tape that was the dominating standard on camcorder market. Sony decided that for their upcoming 'Handycam' line of camcorders they were going to release their own standard which featured similar video quality but significantly better audio quality awkwardly titled 'video8' (8 stands for 8mm). 

All was good for Sony until JVC released 'S-VHS-C' a much higher quality version of VHS that featured 480i lines of resolution (vs VHS's 240i). Quick to respond, Sony released their 'Hi8' standard, a revised version of 'video8' that also featured 480i lines of resolution.

![hi8 tape](http://i.imgur.com/V9RMCuh.jpg)
*A Sony High Grade P6-120HG 8mm Hi8 tape*

---

#### Onto the point..

After going through some of my old belongings, I came across the forgotten camcorder along with 5 or 6 tapes that have not been played in over 10 years! (The tapes date from 1995 - 2006) 

Crossing my fingers hoping the tapes haven't deteriorated magnetically, I inserted the tape labeled 1995 and.. success! I guess thanks to my dad for spending the extra money to buy the genuine Sony gold quality branded tapes instead of going for a more economical option.

![success viewfinder](http://i.imgur.com/kYzhhC4.jpg)
*Success! Here's an image through the viewfinder of what appears to be my older brother opening a birthday gift*

---

I think its about time that I finally digitize these tapes to preserve them indefinitely. Digitizing 8mm tapes on these older analog only cameras is somewhat of a laborous process due to the missing firewire port available on some newer digital Hi8 camcorders. 

![composite jacks](http://i.imgur.com/c85bxU1.jpg)
*The only output option I have on this camcorder is a standard composite video jack and a single composite mono audio jack.*

---

#### Capture card

To digitize these tapes we're going to need some type of video capture device, more specifically a composite video to USB device. Having looked into reviews, it seems like the Elgato video capture card seems to be where decent video quality and simple software meet for a somewhat reasonably priced $80 price tag. I quickly changed my mind after I checked amazon.ca and realized I was looking at USD prices..

![amazon elagto capture expensive](http://i.imgur.com/GNpVsIo.png)
*$1.00 CAD = $0.69 USD :(*

---

Instead, I opted to dig through my belongings to find the EasyCap DC60 capture card I had bought from dealextreme for $8.00 + Free shipping back in 2008 when I used to stream my xbox 360 onto my laptop because my family tv was in use.

![dealextreme easycap](http://i.imgur.com/1wX3dmd.jpg)
*Haven't touched this sucker since 2008, Played Ninja Gaiden II entirely on this thing..*

---

Don't be fooled, the cheap price tag doesn't come for free. This thing is riddled with problems, more on that later. 

For starters, finding drivers for this thing is atrocious, the provided driver simply does not work because it's designed for genuine easycap devices not this knockoff. After some device manager investigation, I found the hardware ID of the EasyCap device and began googling around for a Windows 10 Driver...

![device manager no driver](http://i.imgur.com/rWS3dzI.png)

```
HardwareID: USB\VID_05E1&PID_0408&REV_0005&MI_00
```

---



I ended up finding this [blog post all about easycap drivers] (http://visser.io/2015/06/easycap-drivers-for-windows-8-1/) which linked to a driver that worked for my specific hardware [here](http://visser.io/wp-content/uploads/2015/06/EasycapDC60_STK1160Grabber_3264bit.zip).



Now that the driver is out of the way, we can finally start recording right? Well, it's not that simple, we need to find some decent recording software first. I'm going to save any readers that made it this far the trouble by quickly going through several things I've tried that either don't work at all or don't work well:


| Software | Did it work? | Issues  |
| :-------------: |:-------------------------:| :------------:|
| Pinnacle Studio | NO | Wouldn't detect EasyCap |
| Virtualdub      | Sort-of | Missing key features such as deinterlacing and audio track duplication |
| VLC Media player | Sort-of  | Not selecting the default audio device causes the video to not load |
| **OBS** | **Yes!**  | **None!** |

Before I explain what OBS is and show how I used it, I want to mention that the EasyCap also has an annoying 'crackling' noise with it's audio input. To remedy this I'm bypassing the EasyCap's audio and instead I'm using the headphone aux jack on the camcorder and hooking that directly into my line-in (Blue) jack using a male-to-male aux audio cable (Note: The microphone jack should also work just fine).


![aux audio jack](http://i.imgur.com/jM5stQS.jpg)
*The CCD-TR70 Featured a LANC port and an aux headphone jack for simultaneously syncronizing multiple cameras in the professional setting*

---

#### OBS

[Open Broadcaster Software](https://obsproject.com/), (OBS) is an open-source video streaming software used primarily by broadcasters to livestream their video feeds onto Twitch, Youtube, etc. The neat thing about OBS is that it can be configured to stream to a locally encoded file instead of broadcasting it online. Using the following settings, I was able to select the EasyCap as my video input device, and select my line-in as my audio input device: 

![OBS settings pic goes here](http://i.imgur.com/P8RqkOr.png)
*caption 1*

---

We're almost done, All thats left is to apply a deinterlacing filter (getting rid of the scan lines caused by the 480i resolution from the camcorder) and to duplicate the mono left audio track to stereo:

[OBS settings pic 2 goes here]
*caption 2*

---

That's it! We can now start recording! For the odd person or two still reading, here's a little something for making it this far:

<video id="bonus_video" width="100%" controls>
  <source src="http://haidarn2.github.io/images/digitizing-tapes/bonus.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<script>
  var video = document.getElementById("bonus_video");
  video.volume = 0.1;
</script>
*(May-11-2000) I slip and fall while celebrating my 6th birthday with my siblings*

---
