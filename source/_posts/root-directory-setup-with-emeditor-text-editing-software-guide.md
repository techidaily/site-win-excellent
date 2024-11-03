---
title: Root Directory Setup with EmEditor - Text Editing Software Guide
date: 2024-10-29T19:10:20.296Z
updated: 2024-11-03T18:04:46.132Z
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
<li><a href="https://extra-guidance.techidaily.com/updated-perfecting-narrative-scripts-dialogue-excellence/"><u>[Updated] Perfecting Narrative Scripts Dialogue Excellence</u></a></li>
<li><a href="https://win-excellent.techidaily.com/1-effortless-data-restoration-with-aomei-onekey-the-ultimate-one-click-solution/"><u>1. Effortless Data Restoration with AOMEI OneKey - The Ultimate One-Click Solution</u></a></li>
<li><a href="https://easy-unlock-android.techidaily.com/a-perfect-guide-to-remove-or-disable-google-smart-lock-on-realme-11-proplus-by-drfone-android/"><u>A Perfect Guide To Remove or Disable Google Smart Lock On Realme 11 Pro+</u></a></li>
<li><a href="https://article-posts.techidaily.com/drone-giants-competing-dji-mavic-meets-karma-for-2024/"><u>Drone Giants Competing DJi Mavic Meets Karma for 2024</u></a></li>
<li><a href="https://hardware-tips.techidaily.com/explore-the-best-raspberry-pi-expansion-boards-enhance-your-projects-with-our-curated-hat-list/"><u>Explore the Best Raspberry Pi Expansion Boards : Enhance Your Projects with Our Curated HAT List!</u></a></li>
<li><a href="https://techidaily.com/guide-on-how-to-erase-apple-iphone-xs-data-completely-drfone-by-drfone-ios-full-data-eraser-ios-full-data-eraser/"><u>Guide on How To Erase Apple iPhone XS Data Completely | Dr.fone</u></a></li>
<li><a href="https://novels-ebooks.techidaily.com/209904499-9781609251116-i-will-not-die-an-unlived-life/"><u>I Will Not Die an Unlived Life | Free Book</u></a></li>
<li><a href="https://extra-skills.techidaily.com/in-2024-leading-plot-coders-space/"><u>In 2024, Leading Plot Coders Space</u></a></li>
<li><a href="https://youtube-docs.techidaily.com/24-unlock-youtube-collaboration-a-guide-to-partnering-and-producing-together/"><u>In 2024, Unlock YouTube Collaboration A Guide to Partnering and Producing Together</u></a></li>
<li><a href="https://win-excellent.techidaily.com/quick-guide-backing-up-your-gmail-on-qnap-devices/"><u>Quick Guide: Backing Up Your Gmail on QNAP Devices</u></a></li>
<li><a href="https://win-excellent.techidaily.com/step-by-step-guide-to-configuring-two-way-file-transfer-using-robocopy-in-various-windows-versions-111087/"><u>Step-by-Step Guide to Configuring Two-Way File Transfer Using Robocopy in Various Windows Versions (11/10/8/7)</u></a></li>
<li><a href="https://win-excellent.techidaily.com/your-essential-aomei-backupper-faqs-for-informed-purchasing-decisions/"><u>Your Essential AOMEI Backupper FAQs for Informed Purchasing Decisions</u></a></li>
<li><a href="https://win-excellent.techidaily.com/usbwindows-1011/"><u>ブータブルUSBをWindows 10/11で使用する際のトラブルシューティング手法</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<a href="https://25home.pxf.io/c/5597632/2148635/16836" target="_top" id="2148635">
  <img src="//a.impactradius-go.com/display-ad/16836-2148635" border="0" alt="https://techidaily.com" width="120" height="90"/>
</a>
<img height="0" width="0" src="https://25home.pxf.io/i/5597632/2148635/16836" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

