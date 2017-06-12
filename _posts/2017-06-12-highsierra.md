---
layout: post
title:  What can I expect to break with High Sierra?
date:    2017-06-05
excerpt: What do you expect as an early adopter?
image: /assets/img/covers/highsierra.jpg
tag:
  - macOS
---

I've recently been trying out the High Sierra Developer Beta which is nice and, well, not that different than regular Sierra so far.

There are a few bugs with programs I've encountered which you may find handy to know if you're considering jumping on board.

This won't be a complete list and I'll probably update it as I continue to discover more issues.

## Brew

[![Some brew warnings for early adapters][1]][1]

[1]: /assets/img/highsierra/brew.png

This entry is mainly a reminder that Brew isn't guaranteed to work with a beta OS like High Sierra.

I've had the above issue with installing Wireshark (site binaries are fine) but Brew itself is perfectly operational with all other installations so far.

## Dashlane

[![A macOS error message saying Dashlane has crashed][2]][2]

[2]: /assets/img/highsierra/dashlane.png

Dashlane is a password manager and one of the programs I use most often. It currently just opens and closes repeatedly if you try to run it. In the meantime, there's a [web app](https://app.dashlane.com) you can use if that's your thing.

## Google Drive

[![A Google Drive error message asking for an HFS+ drive][3]][3]

[3]: /assets/img/highsierra/googledrive.png

Do you like syncing your files seamlessly between your desktop and The Cloud™? Well, it looks like you're outta luck because you can't installed Google Drive on High Sierra just yet.

It seems that the installer has no idea that APFS is a thing yet and as such, freaks out demanding that you provide an HFS+ drive. You might be able to get away with formatting a USB drive to HFS+ but do you really want to carry one everywhere?

On the bright side, at least you can just download everything as one big zip file.

## Kitematic

[![The Kitematic main window with a minor visual glitch][4]][4]

[4]: /assets/img/highsierra/kitematic.png

This one isn't bad at all but it's a little annoying.

The top menu bar which is normally custom themed, glitched out visually rendering a grey bar. You can still drag the window around normally and everything else works fine so it's not really an issue.