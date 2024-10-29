---
title: Root Directory Setup with EmEditor - Text Editing Software Guide
date: 2024-10-22T03:04:07.762Z
updated: 2024-10-29T04:33:05.567Z
tags:
  - product
categories:
  - emeditor
thumbnail: https://thmb.techidaily.com/31e3ae8455d50c80842cdc2a354e8096f8d646d3db5eda647c388c8800cd490f.jpg
---

## Root Directory Setup with EmEditor - Text Editing Software Guide

Viewing 6 posts - 1 through 6 (of 6 total)

* Author  
Posts
* November 26, 2011 at 10:21 am [#9830](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/ebe87191575d8a3f3b1fb12210cba2f0?s=80&d=identicon&r=g)CaptainFlint](https://www.emeditor.com/forums/users/captainflint/ "View CaptainFlint's profile")  
Participant  
OS WinXP SP3, EmEditor 11.0.2.  
 My system drive is D:. Sometimes I discover that a new directory named **Emurasoft** appears in the root of this disk. Inside it only one empty directory is present, the full path is  
**D:EmurasoftEmEditorWorkspace**  
 Unfortunately, I cannot find out at what moment it is created. I tried restarting EmEditor, closing tray icon, reopening EE again, saving and restoring workspace (since the directory name suggests that it has something to do with workspaces), but all in vain, the directory does not appear, and the workspace is saved and restored correctly, using “Local SettingsApplication DataEmurasoft” directory in my profile. Of course, I don’t monitor the root of the drive constantly, but after some time I navigate there for something or other, and – bump! – “Emurasoft” is sitting there again.  
 I think I’m going to write a simple monitoring program that will look for appearance of this directory for me and notify with messagebox, but before that I decided to write here and ask, maybe, you have any idea how this could happen?  
November 26, 2011 at 5:21 pm [#9831](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/f29c043a3cc5c5dac8db4e62939893e9?s=80&d=identicon&r=g)Stefan](https://www.emeditor.com/forums/users/Stefan/ "View Stefan's profile")  
Participant  
Hi.  
 Same OS here and portable EmEditor version with ini instead of registry.  
 I never have seen such folder in the root.  
 That folder belongs to your \\%AppData\\% folder in your profil folder.  
 For me (as portable) i have an AppData folder in my EmEditor folder.  
 For an test:  
 what path do you get if you type **\\%appdata\\%** in the address bar of TC?  
 Because you mentioned D as system drive you should see something like  
 “D:Documents and SettingsFlintApplication Data”  
 but in your language  
 and there should be the subfolder “EmurasoftEmEditorWorkspace”  
 .  
November 26, 2011 at 6:46 pm [#9832](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/ebe87191575d8a3f3b1fb12210cba2f0?s=80&d=identicon&r=g)CaptainFlint](https://www.emeditor.com/forums/users/captainflint/ "View CaptainFlint's profile")  
Participant  
As I wrote, the AppData directory and EE workspace location are absolutely correct and always working. \\%APPDATA\\% points to “D:Documents and SettingsApplication Data”, EmEditor workspace storage is located in “D:Documents and SettingsLocal SettingsApplication DataEmurasoftEmEditorWorkspace”, it is saved when I call Save Workspace, and restored when I call Restore Workspace command.  
 But **sometimes**, for unknown reason and unknown purpose, at some unknown moment of time in the drive root an empty “D:EmurasoftEmEditorWorkspace” directory suddenly appears. I can remove it, then work for several days or even weeks without appearing of this directory, even though I use various EE functions (including saving/restoring workspaces and files). But some day it appears again.  
November 26, 2011 at 8:29 pm [#9833](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/a0a6377144ed3636f985d87303f65ed2?s=80&d=identicon&r=g)Yutaka Emura](https://www.emeditor.com/forums/users/yemura/ "View Yutaka Emura's profile")  
Keymaster  
Hi Flint,  
 Are you using INI settings (portable) or the Registry?  
November 26, 2011 at 8:33 pm [#9834](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/ebe87191575d8a3f3b1fb12210cba2f0?s=80&d=identicon&r=g)CaptainFlint](https://www.emeditor.com/forums/users/captainflint/ "View CaptainFlint's profile")  
Participant  
Registry.  
November 27, 2011 at 10:15 am [#9835](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/ebe87191575d8a3f3b1fb12210cba2f0?s=80&d=identicon&r=g)CaptainFlint](https://www.emeditor.com/forums/users/captainflint/ "View CaptainFlint's profile")  
Participant  
OK, I wrote a program for watching for the directory, and today found out what the problem was. The directory appears when I run **git commit** command, which I customized to use a separate EmEditor instance (with /sp argument) as commit message editor.  
 I compared environment variables of this instance of EmEditor with variables of EmEditor started normally (using Process Explorer), and saw that APPDATA path is invalid in the instance started by git. The problem is, my Windows account name is cyrillic, and when I start git it changes the current codepage or something like that, and cyrillic name in the path becomes gibberish.  
 So, probably, there is nothing EmEditor can do about it. :-(
    
 OK, I just wrote a simple wrapper that changes all the environment variables to their appropriate values and then starts EmEditor, and customized git to use this wrapper. So far seems to work fine, without creating the D:Emurasotf directory. :-)  
 BTW, it’s not APPDATA that caused this problem but USERPROFILE variable.
* Author  
Posts

Viewing 6 posts - 1 through 6 (of 6 total)

* You must be logged in to reply to this topic.

<ins class="adsbygoogle"
     style="display:block"
     data-ad-format="autorelaxed"
     data-ad-client="ca-pub-7571918770474297"
     data-ad-slot="1223367746"></ins>

<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-7571918770474297"
     data-ad-slot="8358498916"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>

<span class="atpl-alsoreadstyle">Also read:</span>
<div><ul>
<li><a href="https://youtube-data.techidaily.com/nhance-channel-appeal-with-free-professional-banner-designs-for-2024/"><u>[New] Enhance Channel Appeal with Free, Professional Banner Designs for 2024</u></a></li>
<li><a href="https://digital-screen-recording.techidaily.com/new-screenmasters-unite/"><u>[New] ScreenMasters Unite</u></a></li>
<li><a href="https://facebook-video-share.techidaily.com/updated-in-2024-avoiding-pitfalls-smart-strategies-for-acquiring-youtubes/"><u>[Updated] In 2024, Avoiding Pitfalls Smart Strategies for Acquiring Youtubes</u></a></li>
<li><a href="https://screen-activity-recording.techidaily.com/updated-transform-your-virtual-presence-with-google-meets-effects-features-for-2024/"><u>[Updated] Transform Your Virtual Presence with Google Meet's Effects Features for 2024</u></a></li>
<li><a href="https://win-excellent.techidaily.com/als-erstes-die-top-6-methoden-zum-verschieben-von-daten-von-einem-alteren-pc-auf-einen-neuen-unter-windows-11/"><u>Als Erstes: Die Top-6 Methoden Zum Verschieben Von Daten Von Einem Älteren PC Auf Einen Neuen Unter Windows 11</u></a></li>
<li><a href="https://driver-download.techidaily.com/download-the-latest-hp-officejet-pro-8715-drivers-for-seamless-printing-on-windows-platforms-v11-v10-and-v8/"><u>Download the Latest HP OfficeJet Pro 8715 Drivers for Seamless Printing on Windows Platforms (v11, v10, & V8)</u></a></li>
<li><a href="https://win-excellent.techidaily.com/free-expert-tutorial-upgrading-the-hard-disk-on-a-windows-7-system/"><u>Free Expert Tutorial: Upgrading the Hard Disk on a Windows 7 System</u></a></li>
<li><a href="https://fox-access.techidaily.com/from-hobbyist-to-professional-your-guide-to-design-success/"><u>From Hobbyist to Professional Your Guide to Design Success</u></a></li>
<li><a href="https://win-excellent.techidaily.com/guide-facile-et-gratuit-pour-reparer-la-partition-de-sauvegarde-sur-votre-ordinateur-portable-hp/"><u>Guide Facile Et Gratuit Pour Réparer La Partition De Sauvegarde Sur Votre Ordinateur Portable HP</u></a></li>
<li><a href="https://win-excellent.techidaily.com/szwadronowanie-windows-server-2012-r2-do-winrm-2019-bez-zgubienia-danych/"><u>Szwadronowanie Windows Server 2012 R2 Do WinRM 2019 - Bez Zgubienia Danych</u></a></li>
<li><a href="https://win-excellent.techidaily.com/the-best-methods-for-transferring-data-from-a-usb-stick-to-a-compact-disc-on-windows-os/"><u>The Best Methods for Transferring Data From a USB Stick to a Compact Disc on Windows OS</u></a></li>
<li><a href="https://win-excellent.techidaily.com/transferir-imagen-de-la-tarjeta-microsd-de-una-raspberry-pi-al-clon-en-un-disco-mas-grande-con-windows-11/"><u>Transferir Imagen De La Tarjeta MicroSD De Una Raspberry Pi Al Clon en Un Disco Más Grande Con Windows 11</u></a></li>
<li><a href="https://win-dash.techidaily.com/ultimate-guide-to-downloading-and-updating-canon-pixma-mg2522-printer-drivers-for-optimal-use/"><u>Ultimate Guide to Downloading & Updating Canon PIXMA MG2522 Printer Drivers for Optimal Use</u></a></li>
<li><a href="https://youtube-tips.techidaily.com/-variations-a-curated-list-of-the-best-15-youtube-vocals-tutorials-for-2024/"><u>Vocal Variations A Curated List of the Best 15 YouTube Vocals Tutorials for 2024</u></a></li>
<li><a href="https://win-excellent.techidaily.com/1728487008789-windows-10/"><u>Windows 10ユーザー向け｜完全なディスクバックアップ方法ガイド</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<a href="https://aligracehair.sjv.io/c/5597632/2135357/19272" target="_top" id="2135357">
  <img src="//a.impactradius-go.com/display-ad/19272-2135357" border="0" alt="https://techidaily.com" width="320" height="90"/>
</a>
<img height="0" width="0" src="https://aligracehair.sjv.io/i/5597632/2135357/19272" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

