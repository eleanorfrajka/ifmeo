---
title: Bkennung problems
summary: 
subtitle: 
date: 2024-03-20

reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
show_related: true

lastmod: 2023-11-19
authors: []
tags: ["computing"]
private: true

weight: 500

# Optional header image (relative to `assets/media/` folder).
header:
  caption: ""
  image: ""

# Instructions for floating sidebar TOC: http://ericfong.ca/post/floatingtoc/
# Some problem with partials: https://thisdwhitley.com/post/024-hugo-toc/
toc: true
---


**B-kennung problems**

<!--{{< toc >}}-->

On 19 March 2024, I was unable to login to my e-mail.  Thinking there was a password expiry problem, I updated my password.

This was a mistake.

Shortly, I was unable to use anything on the University system that required my b-kennung login.

Help desk explained that there is something on my computer (or phone, or other device) which is trying to login using the b-kennung, but using the old password.  This triggers a hacker lock which locks me out for a specified period of time.

So, I stopped testing whether the old password was still working.

After stepping away from my computer for a while, I was occasionally able to check e-mail (presumably after the hacker lock wore off).  At home, e-mail worked on my phone on Safari until I plugged in my computer.  Then everything was blocked again.  

So, the problem is on my computer.

I proceeded to remove my university logins everywhere I could think of: basically anything using the Exchange login.  No mail. No calendars.  Then on 20th March (problem still going), no eduroam and no VPN.

Still getting locked out.

Proceeded to run 'TripMode' app on my computer which monitors the network usage and allows me to selectively block or permit individual applications from accessing the internet.

16:53 After uninstalling Cisco AnyConnect, I restarted the computer.  TripMode didn't start immediately, so I found there was still something running (and connecting to the internet) called 'com.cisco.anyconnect.macos.acsocket'.  I googled how to uninstall Cisco AnyConnect since clearly it hadn't uninstalled everything.  Here are some instructions [from MIT to uninstall](https://kb.mit.edu/confluence/display/mitcontrib/Cisco+Anyconnect+Manual+uninstall+Mac+OS).  I didn't execute the instructions, but instead looked through the directories to see whether any of these files were present.

I found in `~/Library/Preferences/` that there were some cisco things--at least one called anyconnect (webex is probably unrelated), but why is there a "com.cisco.anyconnect.gui.plist"?  Anyway, didn't touch it, but instead googled for the specific `com.cisco.anyconnect.macos.acsocket` and found other people have had an issue with it (running their computer hot). Here's some informat about how to kill it: [https://apple.stackexchange.com/questions/420773/the-process-com-cisco-anyconnect-macos-acsockext-hogs-mac-cpu-but-cannot-be-kill](https://apple.stackexchange.com/questions/420773/the-process-com-cisco-anyconnect-macos-acsockext-hogs-mac-cpu-but-cannot-be-kill).  Of course it shouldn't have been running if I uninstalled Cisco AnyConnect?  (Note my plan was to reinstall Cisco AnyConnect, but I need to login with my B-Kennung to download the software from the University website [here](https://www.rrz.uni-hamburg.de/services/netz/vpn.html).)  So no joy on reinstalling Cisco AnyConnect, but instead i removed all the instances of it in my Mac's VPN.

17:03 - still no email.  Only things that have connected on my mac to the internet are iCloud, Safari, CloudSync and Dropbox. My iPad is in flight mode.  My phone is still connecting to the internet, but hopefully since it was OK yesterday, it's not the source of problems.  Wifi is disabled on my computer so I am only using the network cable.

17:07 - still no joy. 

17:10 - OWA works on my computer.  Let's download the VPN client again, so I can potentially follow up at home.  Note that we are using version 4.10.06090.  Unable to download.

17:11 - Tried to download and got a login failure.  Nothing new was problematic.  Activity Monitor says these are running:
- Safari networking
- mDNSResponder
- nsurlsessiond - [https://discussions.apple.com/thread/7525492?sortBy=best](https://discussions.apple.com/thread/7525492?sortBy=best) "used by iCloud to sync your iCloud Drive/Photos/Contacts/etc between your machine(s) and the iCloud server".  Could also be a problem? https://macpaw.com/how-to/remove-nsurlsessiond-from-mac
- translationd (since the RRZ website for the VPN is in German)
- cloudd - see [https://macpaw.com/how-to/cloudd-process-mac](https://macpaw.com/how-to/cloudd-process-mac). "a daemon. That just means it runs in the background performing system tasks. In the case of Cloudd, as its name suggests, those tasks are related to CloudKit."
- netbiosd - [https://discussions.apple.com/thread/252815552?sortBy=best](https://discussions.apple.com/thread/252815552?sortBy=best) Possibly shouldn't exist. obsolete.
- Dropbox
- com.apple.Safari.SafeBrowsing.Service

17:25 - Cannot login to RRZ portal.  BUT I can log in to OWA?  Tried RRZ portal using a private Safari window (no cache/cookies) but this still didn't work.  I guess I'll try again in an hour or so.

20:30 - Could log in to OWA on Mac.  Could not login to download from RRZ the VPN.

21:04 - Ran CleanMyMac X.  Identified some system junk (and the trash), but appears to not run since TripMode is still blocking things on the internet..  the com...cisco anyconnect. is not trying to connect to the internet anymore. 

21:07 - Ran CleanMyMac X and deleted the "System Junk", 4.87 gb of it. - 3.52GB of user cache files, screenshotted.

21:15 - Unable to login with B-kennung for RRZ download of VPN at [https://login.uni-hamburg.de/idp/profile/SAML2/Redirect/SSO?execution=e1s2](https://login.uni-hamburg.de/idp/profile/SAML2/Redirect/SSO?execution=e1s2).  "Anmeldung fehlgeschlagen".  BUT, OWA e-mail access still works.

21:18 - CleanMyMac X: Removed hamburg passwords in Chrome. Removed hamburg cookies in Chrome.  Removed hamburg cookines in Safari.

21:21 - CleanMyMac X: Remove OneDrive application.  Not necessary - it's not logged in.

21:22 - CleanMyMac X: Flush DNS cache.

21:23 - CleanMyMac X: Speed up mail. 

21:31 - Ran CleanMyMac X: Malware blaanced scan. Nothing to remove.

21:26 - Unable to login with B-kennung for RRZ download of VPN.

22:37 - RRZ worked!  2 factor authentication worked.  Enabled "icdd" in Tripmode.  Also "Microsoft update assistant".  As far as I can tell, nothing much new has popped in.

22:41 - Installed Cisco Anyconnect (ONLY VPN, deselected other options and TURNED OFF FILTER network content since this created that daemon that persisted even after uninstall.)

22:43 - To connect, I needed to allow both "Cisco AnyConnect Secur" and "vpnagentd" in TripMode.  Then in the check for updates, allowed "chronod and webprivacyd", and maybe remotepairingd.  Seemed to time out.

22:48 - Could still connect to OWA.

22:50 - Reconencted and VPN worked.  try again after turning off "vpnagend" "webprivacyd" and "icdd.".

!!! 22:52 - Enabled more things and connected to VPN, and outlook doesn't work.  Messages???  Microsoft update assistant? remotepairingd, control center.

??? Is the VPN the problem?

22:55 - OWA email is back on.  Messages/Facetime are enabled.Cisco enabled but not connected.  Internet accounts enabled.  Microsoft update assistant not enabled.  webprivacyd and icdd are enabled. As is vpnagentd and remotepairingd and control center.

22:57 - OWA email still works.  Try reconnecting VPN (didn't require reauth with 2fa).  Ok.  And reconnecting OWA.  Ok.

22:58 - Closed Safari (quit browswer).  Tried to reconnect VPN, and failed at login.
22:59 - Same Safari browswer, OWA still working. 
23:01 - 2fa connection with VPN not working.  OWA still working. Min Moodle NOT working.
23:02 - 2fa connection with VPN not working.  lgin error at UHH-login.
? Try when turning off internet accounts?

23:05 - OWA still working even after formal signout.  Mail Apple is running with new messages downloading. (Enabled internet accounts and Mail)/ looks like only need access on Mail, not internet cacounts. 

23:07 - 2fa connection with VPN not working.

23:08 - quit out of VPN entirely, then tried UHH-login (no joy).

23:09 - Disabled TripMode.  Checeked OWA immediately, worked. 
23:10 - Tried VPN with disabled TripMode.  Didn't work.
23:10 - Signed out and into OWA. Worked.

23:11 - That cisco.anyconnect. acsocket thing is back??

23:13 - VPN connection worked!  Trip mode is off.

23:14 - VPN is connected, Tripmode is on, and login to MIN moodle failed.

?Repeat test when turning off icloud and cloudsync network connections on Mac"

07:00 - VPN is connected.  Try logging into MIN moodle. 2 factor prompt comes up. (cpnagentd, chronod, icdd, webprivacyd are allowed, remotepairingd, ). Cancelled. 

07:02 - Resent the Activity monitor and tripmode.  Only Safari and vpnagentd. !! Doesn't need much.  Sign in with 2fa worked.
Activity monitor network shows: mDNSReponder, Cisco AnyConnect, vpnagendt, netbioisd, rapportd, Safari Networking, apsd and com.apple.Safari.Safebrowsing.service, trustd.

07:05 - RRZ portal worked.

07:10 - **OWA didn't work.  Is the VPN the problem?**  Processing running since 07:02 connected to internet are mDNSResponder, Cisco AnyConnect Secure Mobility Client, vpnagentd, Safari Networking, netbiosd, rapportd, translationd, apsd, com.Safari.SafeBrowsing.Service, trustd, networkserviceproxy. Options are.

  - VPN is a problem
  - Safari has some cookie that is a problem?  Password should be fine
  - Something else in one of these daemons is a problem.

07:11 - disconnected VPN. OWA still doesn't work.

07:12 - Log back into Moodle.  Anmeldung fehlgeschlagen.

07:16 - Noted that apple General Settings has a red bubble against "update apple ID settings". It's not happy that I'm not allowing it to connect to the internet.  In TripMode, "Apple ID Settings" is now allowed.

- Also blocked:
- icdd: for photo shares
- iCloud 
- CloudSync (part of Synology for NAS)

07:24 - enabled iCloud in TripMode but the person bubble doesn't go away. Try family sharing pref pane and webprivacyd.  Still have the red bubble.  Added icdd.  Allowed "internet accounts" and it went away.  Turned off icloud, webprivacy, icdd, Familysharing prefpane, to see if the red bubble comes back.  (Still on is Internet accounts and appleIDsettings)

07:33 - OWA works

08:43 - Login to MIN moodle.  Error.  I haven't done anything on my computer (besides OWA) for a while.  But vpnagentd is still running.  There is some information about this.  Even though I'm not connected to the VPN, Cisco is still running.  Is this the problem? https://macsecurity.net/view/514-vpnagentd-will-damage-your-computer-mac-error.  Probably not - this website is about a virus which was called something like vpnagentd.

08:51 - Longin to MIN moodle.  After having stopped vpnagentd from connecting to the internet a few minutes ago.

10:45 - OWA on phone didn't work.

11:01 - MIN moodle on computer didn't work.  Turned vpnagentd back on.  Still didn't work

12:33 - MIN moodle on computer didn't work.  With vpnagentd off.  Turned vpnagentd on.  Didn't work.  Put phone in airplane mode.  

12:37 Email not working.

12:59 - Email working. Safari, vpnagentd, Mattermost and messages are on.

14:37 - Min moodle not working. Eduroam is connected.  Could eduroam be a problem?  Zoom, dropbox, safari, mattermost, vpnagendt, icloud are running.
