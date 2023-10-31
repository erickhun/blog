+++ 
draft = false
date = 2023-10-30T23:10:07+08:00
title = "Google Photos Backup"
description = ""
slug = "" 
tags = []
categories = []
externalLink = ""
series = []
images = ["/img/google-photos-backup/export-result.png"]

+++


Are you using any Google service (Gmail, Youtube, Google Maps, Google Cloud, Google Voice, [etc...](https://en.wikipedia.org/wiki/List_of_Google_products)) daily? You might want to know that Google has the really bad habit to [kill products](https://killedbygoogle.com/) and [lock you out of your own google account](https://www.androidpolice.com/2021/03/08/when-google-locks-you-out-of-your-account-begging-the-internet-for-help-is-your-first-and-last-resort/) 
- [for](https://news.ycombinator.com/item?id=34116361) 
- [any](https://news.ycombinator.com/item?id=36335975) 
- [kind](https://www.androidpolice.com/2019/01/14/the-ludicrous-google-pay-death-sentence-can-lock-your-fi-account-and-phone-number/)
- [of](https://news.ycombinator.com/item?id=33737577)
- [possible](https://www.androidpolice.com/2019/01/14/the-ludicrous-google-pay-death-sentence-can-lock-your-fi-account-and-phone-number/)
- [and](https://mailchi.mp/shwood/bamboozlers-514882?e=4be3990d97)
- [random](https://old.reddit.com/r/GMail/comments/bcdf6z/locked_out_of_google_account_endless_loop/)
- [reasons](https://www.reddit.com/r/Android/comments/5dif8j/psa_google_can_lock_your_account_forcing_you_to/)

If their AI robot determines that any of these services might lead to the closure of your entire Google account, you could lose all your photos and videos tomorrow.

I love Google Photos. It's probably the best mobile app for viewing and searching photos and videos today. You can also easily share photos and videos to your friends. Their editing tools are also great and very user-friendly. However, the risk of losing  all your cherished memories because a random bot decided so isn't something I like to think about, and you neither. Backing up Google Photos data isn't quite straightforward, which is why I've created this guide to help :) 

## 1. Export your photo with Google Takeout

Go to Google Takeout and export your Google Photos data. For the export option, I recommend selecting the 10 GB size per zip file. The first time I tried to export, I chose the 50 GB size option, but it failed after 24 hours. 😅 I retried with a smaller file size, 10 GB, and it worked. Google Takeout also offers the option to send your data to another backup provider, such as Dropbox or OneDrive.

![](/img/google-photos-backup/export-google-takeout.png)

The export finished after 72 hours. It resulted of  52 files of 10GB. (520GB of files!). After you've obtained all the backup files, extract them all by using your mouse: select all, right-click, and choose 'Extract Here' . You'll notice that the last folder contains a number that represents the total files, but be aware that this number includes a lot of files that aren't your photos. It can be a bit misleading.

![](/img/google-photos-backup/export-result.png)



## 2. Reorganize your file and metadata



You will find out JSON , video, and photo files scattered in different folders, without any discernible order. To make matters worse, the date of the last file edit and GPS location information is stripped away, which can be frustrating. Fortunately, there's a tool called  [`google-photos-exit`](https://github.com/mattwilson1024/google-photos-exif)

This tool wil help you organize all in a  nice single folder, with all the metadata in it. Just head to [this link](https://github.com/mattwilson1024/google-photos-exif) and follow the instruction.

It took approximately 17 minutes to complete. After running google-photos-exit, I ended up with precisely 95,662 photos and videos. Initially, there were 191,110 files within the original zip files.

There is also an alternative solution that allows you to preserve the album structure while offering the option to output the result in a YEAR-MONTH format:  [https://github.com/TheLastGimbus/GooglePhotosTakeoutHelper](https://github.com/TheLastGimbus/GooglePhotosTakeoutHelper). I attempted to use this alternative tool, but it didn't work well with my 50 folders


## 3. Copy the file to the other backup location

After everything has been properly sorted, export it to your other backup location. Currently, I've chosen Dropbox, but I'm also considering purchasing my own NAS so that I won't depend on a backup provider. There are many backup solutions available today:

- [oneDrive](https://www.microsoft.com/en-us/microsoft-365/onedrive/compare-onedrive-plans)
- [Dropbox](https://dropbox.com)
- [Amazon Photos](https://www.amazon.com/Amazon-Photos)
- Your own NAS, or server

## 4. Continusouly backup your new photos 

Then you'll wannt to continuously upload your new photos and video continuously to Google Photos and your other backup location.  I've found [Photosync[(https://www.photosync-app.com/home)] is a nice (paying app), that will allow you to backup file on your device to literally anywhere.  It's unfortunately the only viable option that allow you to send your medias anywhere. I didn't find a better alternative today for iOS, so if you have any suggestion, I'm all hear. 

![](/img/google-photos-backup/photosync1.png)

You are now all set. If Google decide to lock you out, or you want use an other photo backup service, you'll have all your memories ready to go with you!
