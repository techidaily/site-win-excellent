---
title: Root Directory Setup with EmEditor - Text Editing Software Guide
date: 2024-11-15T17:32:15.252Z
updated: 2024-11-22T20:53:43.088Z
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
<li><a href="https://facebook-video-footage.techidaily.com/new-in-2024-automating-your-channels-youtube-subscription-link/"><u>[New] In 2024, Automating Your Channel's YouTube Subscription Link</u></a></li>
<li><a href="https://fox-glue.techidaily.com/new-unleash-the-power-of-windows-11s-media-importer-tools/"><u>[New] Unleash the Power of Windows 11'S Media Importer Tools</u></a></li>
<li><a href="https://article-tips.techidaily.com/updated-virtual-escapades-with-top-samsung-gear-vr-games/"><u>[Updated] Virtual Escapades with Top Samsung Gear VR Games</u></a></li>
<li><a href="https://win-excellent.techidaily.com/1-successful-strategies-for-repairing-0-byte-hard-drives-and-retrieving-lost-files/"><u>1. Successful Strategies for Repairing 0 Byte Hard Drives & Retrieving Lost Files</u></a></li>
<li><a href="https://win-excellent.techidaily.com/1728503211482-windows-11-asus/"><u>簡單方式修復 Windows 11 上 Asus 系統安全加密故障</u></a></li>
<li><a href="https://win-excellent.techidaily.com/windows-11-7-usb/"><u>移動設備：如何在 Windows 11-7 上複製系統檔案到 USB 隨身碟</u></a></li>
<li><a href="https://win-blog.techidaily.com/fixes-for-frequent-pc-freezes-how-to-stop-your-blender-from-crashing/"><u>Fixes for Frequent PC Freezes: How to Stop Your Blender From Crashing</u></a></li>
<li><a href="https://win-excellent.techidaily.com/guide-de-recovery-darchives-eliminees-par-ccleaner-sur-windows-et-mac-sauvegardez-vos-donnees/"><u>Guide De Recovery D'Archives Eliminees Par CCleaner Sur Windows Et Mac – Sauvegardez Vos Données!</u></a></li>
<li><a href="https://bypass-frp.techidaily.com/honor-x50iplus-adb-format-tool-for-pc-vs-other-unlocking-tools-which-one-is-the-best-by-drfone-android/"><u>Honor X50i+ ADB Format Tool for PC vs. Other Unlocking Tools Which One is the Best?</u></a></li>
<li><a href="https://screen-video-capture.techidaily.com/in-2024-voicing-it-up-how-to-save-on-iphone/"><u>In 2024, Voicing It Up How to Save on iPhone</u></a></li>
<li><a href="https://common-error.techidaily.com/1723210743255-troubleshooting-destiny-2-get-your-game-up-and-running-again/"><u>Troubleshooting Destiny 2: Get Your Game Up and Running Again</u></a></li>
<li><a href="https://solve-manuals.techidaily.com/1728464595093-excel/"><u>どこで保存されていますか? Excelの一時ファイル, なくした情報を取り戻す手順</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/gMS5pm0SQlQ?si=gasOo6p2agrVlIb7&autoplay=1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

