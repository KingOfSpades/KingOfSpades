---
title: This could save your day(ta)
date: 2024-09-11
toc: true
mermaid: true
categories:
  - Life Hacks
tags:
  - "macos"
  - "backups"
---

Ever found out at the wrong moment that your TimeMachine backup is not working any more? That the last backup was from two weeks ago? Or you're on the road, and you can't get that backup because it's a thousand miles from your current location? Then I got something **for you**

# TimeMachine

Let's take a step back. If you have a Mac and have never used or heard of [TimeMachine](https://support.apple.com/en-us/104984), then let's have a look at that first. [TimeMachine](https://support.apple.com/en-us/104984) is a backup utility bundled with your Mac. You can use it to restore files that you have deleted, recover older versions of files, or set up an empty Mac from a backup. This makes it a no-brainer to use for simple backups of your system. You can set up Time Machine to make backups to an external drive or a network-mounted location (like on a NAS). It won't cover advanced use cases like [Carbon Copy Cloner](https://bombich.com/), but it will give you a first line of backups if you ever need them. The best part is, it's pretty much fire-and-forget after you set it up.

# The JetDrive 330

Years ago [Nifty released a tiny SD card](https://www.theverge.com/2012/7/6/3140320/nifty-minidrive-kickstarter-macbook-microsd-card) that could transform the SD slot of a MacBook in to permanent storage. The main issue back then was that on every sleep macOS would eject the card. Not great but it was eventually fixed in a later macOS release. Nowadays, you can keep a SD card connected and mounted to your Mac without having to worry about it.

The Nifty Drive is no more, but there are other options on the market. We will be having a look at the [JetDrive 330](https://amzn.to/47hmkMP)

The [JetDrive](https://amzn.to/47hmkMP) is a mini SD card that you can keep plugged in to your machine. This gives a few awesome options like extending the amount of storage of our mac, or in this case, having a mobile TimeMachine backup ready to go.

# The setup

The setup is pretty easy, actuallyy. Once you have a JetDrive orequivalent you can:

- insert disk
- setup/format disk
- setup TimeMachine with password
- ???
- profit

In all seriousnesss. You can follow the [instructions from Apple](https://support.apple.com/en-us/104984#:~:text=From%20the%20Apple%20menu%20%EF%A3%BF,and%20click%20Set%20Up%20Disk.) on this one

**Please Please PLEASE!!!** Set up your TimeMachine backup with a password. If you do not do this someone could just yank out your backup drive and have copy of all your data
{:.error}

![JetDrive as backup](/assets/images/JetDrive-AsTimeMachine.png)
_Using the JetDrive as TimeMachine Backup Drive_

![TimeMachine](/assets/images/TimeMachine.png)
_Overview of TimeMachine Settings_

# Alternatives

There are a lot of alternatives for TimeMachine backups on the go, you could:

- Use a mobile or small hard drive. The main drawback is having to carry another thing with you and that you'll need to remember plugin it in and making backups blog post, these take a lot to set up and require you
- If you already have a TimeMachine target on a NAS at home you can VPN in to your home. The main caveat is the same as the mobile hard drive. You will need to remember connecting to your VPN, and you'll have to keep an eye on you're backup to see if they complete. It can also take a long time to complete backups depending on the connection you have.
- I tried using Cloud Storage (`s3` and `Azure Storage`) as a TimeMachine. This works but it also eats trough credits. This is because the TimeMachine backup us not only a _write_, but it also does a lot of checking of files. I configured a `Azure Storage Account` to test this. Thinking I was smart I set it up as **Cold Storage**. The result was $80 a day of storage usage :') . The main disadvantages are the costs and (once again) the bottleneck of your internet connection.

# Caviats

This setup has some caveats, but I think they are worth the tradeoff

- It only works with MacBooks that have SD card slot (so older models or newer MacBook Pro's)
- In the past I tried to have multiple partitions on the same disk. I did this, so I could also use the same drive for other data and backups. This seemed to _break_ the drive every ~4 months resulting in needing to reformat the disk and starting the TimeMachine backup anew. Now that I only use it for TimeMachine it seems a lot more stable.
- The first backup takes forever. The SD card is **not** fast
- That means that browsing backups is also slow

All in all I'm very happy with this setup and the ease of mind it gives me.
