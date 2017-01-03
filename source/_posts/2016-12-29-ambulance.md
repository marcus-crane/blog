---
layout: post
title: Ambulance WiFi Hotspot
date: 1st January, 2017
categories: networking
comments: false
---

This actually happened a few days ago but pbbt, everyone is on holiday and writing is hard!

There were two ambulances at our neighbours place and interestingly enough, they apparently emit their own WiFi networks. At first I thought it was a coincidence until the second ambulance (and SSID) appeared so I had a look.

[![Left half of a network scan][1]][1]

[1]: /assets/img/ambulance/scan-left.png

Nothing much stands out here. They're both using WPA2 Personal and 802.11b/g/n, although they're on different channels. You wouldn't want a gathering of ambulance WiFi networks interfering with each other, right?

[![Right half of a network scan][2]][2]

[2]: /assets/img/ambulance/scan-right.png

Everything else is the same but interestingly, for New Zealand ambulances, their country code is set to American! I guess they were just left using default factory settings?

[![A slightly more informative scan][3]][3]

[3]: /assets/img/ambulance/stumbler.png

I did a bit more searching around the use of wireless networks in New Zealand ambulances and it took me beyond Page 1 of Google...

The first interesting bit was from [this interview](http://www.cio.co.nz/article/557698/mission-critical-ict-st-john-nz/) by CIO back in October 2014.

> **"We’re looking at putting wireless technology into every ambulance station, so that while the ambulance is in transit it will be using the 3G network. Then, as it drives into the station, the wireless will take over."**

So, the ambulances have the ability to switch between 3G and WiFi on the fly which makes sense.

The other informative piece was from [a case study](https://www.lightwire.co.nz/case-studies/st-john-hq-thames/) by Lightwire where they detail systems upgrades they aided with in October 2015

> **"When an ambulance comes back from a call out, staff sync this information, which on the old system added to the strain."**

It isn't stated outright but I can assume from those two quotes that the WiFi network being broadcast syncs patient data back to HQ once they arrive back at their respective stations.

Well, that certainly more interesting than I expected. I didn't get a chance to gather much information when the ambulances were there. I popped on a scan and then got sidetracked with troubleshooting my parents desktop. Despite that, it looks like this was another successful round of detective work!
