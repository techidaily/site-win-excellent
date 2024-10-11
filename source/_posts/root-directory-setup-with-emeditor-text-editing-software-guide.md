---
title: Root Directory Setup with EmEditor - Text Editing Software Guide
date: 2024-10-04T04:00:25.881Z
updated: 2024-10-11T05:31:27.940Z
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
<li><a href="https://youtube-sure.techidaily.com/he-faces-to-watch-top-cosmetic-creatives-for-2024/"><u>[New] The Faces to Watch Top Cosmetic Creatives for 2024</u></a></li>
<li><a href="https://article-tips.techidaily.com/2024-approved-complete-scrutiny-of-cutmatic-editor/"><u>2024 Approved Complete Scrutiny of CutMatic Editor</u></a></li>
<li><a href="https://howto.techidaily.com/7-solutions-to-fix-chrome-crashes-or-wont-open-on-itel-s23plus-drfone-by-drfone-fix-android-problems-fix-android-problems/"><u>7 Solutions to Fix Chrome Crashes or Wont Open on Itel S23+ | Dr.fone</u></a></li>
<li><a href="https://unlock-android.techidaily.com/can-i-bypass-a-forgotten-phone-password-of-infinix-hot-40-pro-by-drfone-android/"><u>Can I Bypass a Forgotten Phone Password Of Infinix Hot 40 Pro?</u></a></li>
<li><a href="https://win-excellent.techidaily.com/download-top-hollywood-blockbusters-in-hd-free-mp4movavi-formats-for-pc-and-mac/"><u>Download Top Hollywood Blockbusters in HD: Free MP4/MOV/AVI Formats for PC and Mac</u></a></li>
<li><a href="https://win-excellent.techidaily.com/download-your-favorite-izlesene-videos-as-high-quality-mp4-or-avi-files/"><u>Download Your Favorite Izlesene Videos as High-Quality MP4 or AVI Files</u></a></li>
<li><a href="https://win-excellent.techidaily.com/easy-guide-to-downloading-and-converting-snotr-videos-into-multiple-file-types-such-as-mp4-mov-avi-etc/"><u>Easy Guide to Downloading and Converting Snotr Videos Into Multiple File Types Such as MP4, MOV, AVI, Etc.</u></a></li>
<li><a href="https://win-excellent.techidaily.com/easy-movie-conversion-tools-for-macwindows-users-to-save-movies-in-various-formats-like-mp4-mov-avi/"><u>Easy Movie Conversion Tools for Mac/Windows Users to Save Movies in Various Formats Like MP4, MOV, AVI</u></a></li>
<li><a href="https://win-excellent.techidaily.com/get-the-9now-app-watch-and-save-shows-from-9nowcomau-for-free-compatible-with-mac-and-pc/"><u>Get the 9NOW App: Watch and Save Shows From 9now.com.au for Free – Compatible with Mac & PC</u></a></li>
<li><a href="https://win-excellent.techidaily.com/guide-converting-and-downloading-docmeded-tutorials-in-multiple-formats-mp4-mp3-mov-avi/"><u>Guide: Converting and Downloading DocmedEd Tutorials in Multiple Formats (MP4, MP3, MOV, AVI)</u></a></li>
<li><a href="https://win-excellent.techidaily.com/guide-downloading-all-episodes-of-the-big-bang-theory-for-personal-use-at-no-cost/"><u>Guide: Downloading All Episodes of The Big Bang Theory for Personal Use at No Cost</u></a></li>
<li><a href="https://win-excellent.techidaily.com/guide-mastering-the-art-of-downloading-igtv-content-for-offline-viewing/"><u>Guide: Mastering the Art of Downloading IGTV Content for Offline Viewing</u></a></li>
<li><a href="https://win-excellent.techidaily.com/guide-successful-downloads-from-pscfptv-and-periscope-across-macos-and-windows-systems/"><u>Guide: Successful Downloads From PSCFPTV & Periscope Across macOS & Windows Systems</u></a></li>
<li><a href="https://review-topics.techidaily.com/in-2024-how-to-fake-gps-on-lava-yuva-3-for-mobile-legends-drfone-by-drfone-virtual-android/"><u>In 2024, How To Fake GPS On Lava Yuva 3 For Mobile Legends? | Dr.fone</u></a></li>
<li><a href="https://audio-shaping.techidaily.com/mastering-the-art-of-audio-volume-transition-for-2024/"><u>Mastering the Art of Audio Volume Transition for 2024</u></a></li>
<li><a href="https://win-lab.techidaily.com/microsofts-potential-ban-on-windows-11-24h2-mod-apps-what-you-need-to-know-now/"><u>Microsoft's Potential Ban on Windows 11 24H2 Mod Apps – What You Need to Know Now</u></a></li>
<li><a href="https://win-blog.techidaily.com/pc-gaming-solutions-step-by-step-guide-to-fixing-crashes-in-robocop-legacy-rogue-city-edition/"><u>PC Gaming Solutions: Step-by-Step Guide to Fixing Crashes in RoboCop: Legacy – Rogue City Edition</u></a></li>
<li><a href="https://techidaily.com/the-easiest-methods-to-hard-reset-poco-x5-pro-drfone-by-drfone-reset-android-reset-android/"><u>The Easiest Methods to Hard Reset Poco X5 Pro | Dr.fone</u></a></li>
<li><a href="https://some-knowledge.techidaily.com/top-7-critical-accounts-for-enhanced-security-with-dual-layered-verification/"><u>Top 7 Critical Accounts for Enhanced Security with Dual-Layered Verification</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<a href="https://aligracehair.sjv.io/c/5597632/2036467/19272" target="_top" id="2036467">
  <img src="//a.impactradius-go.com/display-ad/19272-2036467" border="0" alt="https://techidaily.com" width="300" height="90"/>
</a>
<img height="0" width="0" src="https://aligracehair.sjv.io/i/5597632/2036467/19272" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

