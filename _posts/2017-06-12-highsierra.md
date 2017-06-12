---
layout: post
title:  What can I expect to break with High Sierra?
date:    2017-06-12
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

Here's an official statement from [Dashlane Support](https://twitter.com/dashlanesupport):

> We completely understand how important it is to run Dashlane on macOS 10.13 High Sierra, and we confirm that our development team has been working on Dashlane's compatibility with this system.

> However, please note that macOS 10.13 High Sierra is still in **beta** and we cannot guarantee that Dashlane always works there. We have access to the same beta updates like you, and cannot know in advance if a beta update makes Dashlane unusable or unstable. This has unfortunately happened in the past with other macOS beta updates. Keep in mind that any updates that Apple releases might break Dashlane and our team will only find out once the beta update is available to all beta testers.

> If Dashlane is critical for you, please run macOS 10.12 Sierra, which is still the latest official version of macOS.

> Please rest assured that Dashlane will be ready for macOS 10.13 High Sierra's public release this fall. If you are running macOS 10.13 High Sierra, you may want to join our own beta program to get Dashlane updates before everyone. You can sign up here: bit.ly/1nKRyPg. On this page, enter your registered e-mail address for Dashlane.

> We hope this helps. Please let us know if you have any further questions. We're always happy to help.

Bless 'em for their quick response even though I'm the one causing trouble running a Beta.

I've also sent them my crash logs and if you've got some, they'd probably appreciate you sending them through as well!

## Discord

[![A Discord window with a minor visual error][3]][3]

[3]: /assets/img/highsierra/discord.png

This entry is similar to Kitematic below where we have an application that uses a custom title bar only to find it doesn't render properly but it's no biggie.

Beyond that, everything works just as you'd expect.

## Google Drive

[![A Google Drive error message asking for an HFS+ drive][4]][4]

[4]: /assets/img/highsierra/googledrive.png

Do you like syncing your files seamlessly between your desktop and The Cloud™? Well, it looks like you're outta luck because you can't installed Google Drive on High Sierra just yet.

It seems that the installer has no idea that APFS is a thing yet and as such, freaks out demanding that you provide an HFS+ drive. You might be able to get away with formatting a USB drive to HFS+ but do you really want to carry one everywhere?

On the bright side, at least you can just download everything as one big zip file.

## Kitematic

[![The Kitematic main window with a minor visual glitch][5]][5]

[5]: /assets/img/highsierra/kitematic.png

This one isn't bad at all but it's a little annoying.

The top menu bar which is normally custom themed, glitched out visually rendering a grey bar. You can still drag the window around normally and everything else works fine so it's not really an issue.

## Paragon NTFS

I don't actually use this but if you've got a hard drive that is NTFS formatted then you're outta luck since there's no support for High Sierra yet. [Paragon](https://www.paragon-software.com/ufsdhome/ntfs-mac/) do state that development is underway but that leaves us outta luck.

You can still mount NTFS drives but they're read only meaning you can't transfer data to or from your hard drive short of manually copying the contents I suppose.

In the meantime, here's a workaround that'll do just fine.

Open up your `fstab` file with `sudo nano /etc/fstab` (or your editor of choice) and insert the following:

```sh
LABEL={DRIVENAME} none ntfs rw,auto,nobrowse
```

My external hard drive is named Macha so my `fstab` looks like so:

```
LABEL=Macha none ntfs rw,auto,nobrowse
```

The annoying part about this is that you won't see it popup in your finder sidebar but you can access it by going to `Go` under Finder and visiting `/Volumes/{DRIVENAME}`

You can then drag that drive to your `Favourites` sidebar but unfortunately, you'll have to repeat that each time you unplug it.

## StarCraft

[![The Kitematic main window with a minor visual glitch][6]][6]

[6]: /assets/img/highsierra/starcraft.png

I didn't intentionally end up testing this! I was downloading the Battle.NET client, lord knows why since I don't play anything in it, and remembered I own both this and Warcraft III.

It installs fine and then crashes on startup. Checking `Console.app` reveals the following:

```sh
/BuildRoot/Library/Caches/com.apple.xbs/Sources/AppleFSCompression/AppleFSCompression-91.0.0.1.2/Libraries/CompressData/CompressData.c:353: Error: Unknown compression scheme encountered for file '/System/Library/CoreServices/CoreTypes.bundle/Contents/Resources/Exceptions.plist'
```

I'm no debug master but I presume this `Unknown compression scheme` is to do with how compression is done with `APFS` and so Starcraft throws errors due to knowing nothing about the new file system.

## Warcraft III

[![A glitchy Warcraft 3 installer][7]][7]

[7]: /assets/img/highsierra/warcraft3.png

Same deal as above as to why I'm even trying this.

You can download the installer but you'll hit trouble once you click `Agree` on the T&Cs page. The whole Installer freezes up!

Interestingly, the menu entries are all replaced with debug text. I presume they're meant to be placeholders for localisation text and the actual text (US English in this case) isn't properly rendered.

You can't quit either or use the icons in the title bar leaving you with no option but to force quit.

Well, that about wraps up everything I've got for now. Feel free to send me a [tweet](https://twitter.com/sentreh) if you've stumbled across any more broken applications!