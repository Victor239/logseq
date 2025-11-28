- Overview
  id:: 62d4471d-d5c6-4d88-9fb8-737c7163a761
  collapsed:: true
	- https://puri.sm/learn/freedom-roadmap/
	- Security levels
	  https://puri.sm/posts/what-the-cia-vault-7-documents-mean/
		- web access
		- networking
		- applications
		- operating system
		- kernel
		- bootloader
		- BIOS/UEFI
		- firmware
		- chips
		- hardware
		- schematics
- PC Software
  collapsed:: true
  id:: 635037c4-f2c3-467d-8207-85d75da4a899
	- Desktop Operating System
	  id:: 635037c4-879c-42c0-81a8-fa34b30bd202
		- [Windows](https://www.microsoft.com/en-gb/windows)
		  id:: 66a98a52-9772-4779-9956-4684637041b1
		  collapsed:: true
			- Pros/Cons
				- Cons
					- Hostile to freedom and open-source
					  collapsed:: true
						- Won't release Windows, DirectX, MS Office under GPL
						- Uses NTFS filesystem which is incompatible with Linux when ext4 is superior
						  https://en.wikipedia.org/wiki/Ext4#Features
							- Though they have made exFAT open-source or something similar
								- exFAT
								  collapsed:: true
									- Pros/Cons
										- Pros
											- THE difference between FAT32 and exFAT is that exFAT will also support files larger than 4GB and FAT32 will not.
											- Supports all platforms, like FAT32
										- Cons
											- Doesn't support POSIX permissions
												- e.g. chown/chmod
												- May prevent it from being backed up via CrashPlan
												- Can't create symlinks
											- Seems to have an issue of limited filename length, which makes it hard to copy folders which have deeply nested files
												- Even turning these into an archive doesn't prevent this issue
									- Related:
										- ext4
											- Pros/Cons
												- Pros
												- Cons
													- Poor support on Windows and Mac
											- The primary reasons I chose EXT4 are because 1) EXT4 will preserve my file permissions and 2) EXT4 better manages the storage of the data on it (e.g., it doesn't need to be constantly defragged and "coddled" like NTFS does). EXT4 is a more self-reliant file system than NTFS.
						- Next gen Xbox will use a Windows-like OS and will run games compatible with Windows
						  source:: https://www.theguardian.com/technology/2016/mar/01/microsoft-to-unify-pc-and-xbox-one-platforms-ending-fixed-console-hardware?CMP=twt_gu
						- Windows 10 forced updates
						- MS were completely against open source software and actively interfered with it.
						- Over and over they would pretend to embrace a standard and then try to inject MS only extensions.
					- Anticompetitive
					  collapsed:: true
						- Windows 95, from memory, has IE embedded. You couldn't uninstall it, but if you tried to forcefully remove it, you bluescreened.
					- Hostile to privacy
					  collapsed:: true
						- Windows 10
						  #PC https://workflowy.com/#/b193a27e543f
						- Telemetry
					- Bad user experience
					  collapsed:: true
						- Due to NTFS file locking it requires those long Windows Update during boot/shutdown
					- _More_
					  collapsed:: true
						- MS was incredibly late on the need for PC security in a connected world.
						- https://www.reddit.com/r/windowssucks
			- Sorted by version
				- Windows 12
				  collapsed:: true
					- Pros/Cons
						- Pros
							- Windows Subsystem for Android
							  collapsed:: true
								- [https://docs.microsoft.com/en-us/windows/android/wsa/](https://docs.microsoft.com/en-us/windows/android/wsa/)
								- [https://github.com/LSPosed/MagiskOnWSA](https://github.com/LSPosed/MagiskOnWSA)
								- [https://github.com/WSA-Community/WSAGAScript](https://github.com/WSA-Community/WSAGAScript)
						- Cons
							- Requires a TPM chip
							  collapsed:: true
								- This can be used to implement a corollary to ((649b13d2-3bf6-43ed-b52c-7bbcf094ca3c)) - mark a device as untrusted if you install Linux on it
								  [https://secret.club/2021/06/28/windows11-tpms.html](https://secret.club/2021/06/28/windows11-tpms.html)
									- Stuff like Netflix and YouTube may show degraded quality
							- No 4rd-party kernel drivers work unless signed by Microsoft
							  collapsed:: true
								- Process Explorer refuses to be signed by Microsoft, anti-competitive
								  [archived] [https://borncity.com/win/2021/10/23/microsoft-signiert-windows-treiber-fr-process-hacker-nicht-mehr/](https://borncity.com/win/2021/10/23/microsoft-signiert-windows-treiber-fr-process-hacker-nicht-mehr/)
				- Windows 11
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Windows 10 ships with a whole arsenal of exploit mitigations, trusted boot (sort of), content integrity levels (e.g AppContainer), hypervisor isolated code integrity checking, signed binaries, the ability to enforce code signing policies, etc.
						- Cons
							- Forced auto-upgrade from previous Windows OS to W10
							- Many, many privacy issues
							  collapsed:: true
								- Data syncing is by default enabled.
								  collapsed:: true
									- Browsing history and open websites.
									- Apps settings.
									- WiFi hotspot names and passwords.
								- Your device is by default tagged with a unique advertising ID.
								  collapsed:: true
									- Used to serve you with personalized advertisements by third-party advertisers and ad networks.
								- Cortana can collect any of your data.
								  collapsed:: true
									- Your keystrokes, searches and mic input.
									- Calendar data.
									- Music you listen to.
									- Credit Card information.
									- Purchases.
								- Microsoft can collect any personal data.
								  collapsed:: true
									- Your identity.
									- Passwords.
									- Demographics.
									- Interests and habits.
									- Usage data.
									- Contacts and relationships.
									- Location data.
									- Content like emails, instant messages, caller list, audio and video recordings.
								- Your data can be shared.
								  collapsed:: true
									- When downloading Windows 10, you are authorizing Microsoft to share any of above mentioned data with any third-party, with or without your consent.
								- It monitors and collects voice, keystrokes, name, e-mail address, preferences, interests, browsing, search and file history, phone call and SMS data, device configuration and sensor data, location, application installation and usage - this is as stated in Microsoft's privacy policy.
								- It sends this information to Microsoft. (Read somewhere that voice-related stuff is used/sent only if you are in the USA, as determined by geoip location - is this correct?)
								- It might send it to third parties. (Source? I know that Apple sends to third parties what you tell Siri - is something similar known for sure about Microsoft?)
								- Some of the data is sent over unencrypted links.
								- Each device is assigned an "advertising ID" that can be used for targeted advertising, by the app developers to identify your device, etc.
								- It could be scanning your files for DMCA-violating contents. (Source? Or is this just a rumor?)
								- It reports this "telemetry data" to a very large list of Microsoft sites.
								- The reporting ignores the contents of the HOSTS file; you must disable access to these sites from the router or a firewall.
								- Turning off all the privacy-violating settings requires you to go through 13 pages of settings.
								- Some privacy-violating settings cannot be turned off unless you are running the Enterprise edition. (Does anyone know which ones?)
								- Even if you turn the privacy-violating settings off, the first update will turn them back on.
								- You can't disable/configure Windows Update from the GUI as a user - you have to stop the service if you want to prevent updating.
								- If you have registered accounts for you and for your child, indicating age, relationship, etc., you'll be receiving by e-mail weekly reports about your child's browsing history.
								- It shares access to your WiFi network (but not the password itself) with all your direct Outlook, Skype and Facebook contacts.
								- Some of the "telemetry patches" have been back-ported to Windows 8.1 and Windows 7 and are being pushed there under the guise of "Recommended" updates by Windows Update.
								- Even if you have not indicated that you wish to upgrade to Windows 10, one of these "backported" patches is downloading it to your Windows 8.1 or Windows 7 machine "just in case", wasting your bandwidth and disk space.
								- Windows 10-related updates are being distributed from your machine to others, torrent-like, wasting your bandwidth.
								- There are hard-coded outgoing connections which ignore the firewall and require hosts file tuning
								- It even goes as far as capturing your keystrokes (keylogger) and uploading your bitlocker encryption key to Microsoft.
							- Windows Defender blocks many torrent clients
							  [https://news.ycombinator.com/item?id=27958432](https://news.ycombinator.com/item?id=27958432)
							- Windows 10 blocks Potentially Unwanted Apps by default now
							  https://news.ycombinator.com/item?id=28071180
							- _See _[Debloat and removing tracking](https://workflowy.com/#/0151ede65e59)
					- Windows 11 product key
					  id:: 65494796-e73d-4312-85d2-78f0c5719b25
					  collapsed:: true
					  `6NC9P-V94DH-6B7QG-RX33C-PGYK4`
					- Windows 11 LTSC is the lighter, less tracking, auto-update controllable version. get via torrent
					  collapsed:: true
					  [[Buy Cheap  Antivirus Software, PC game cd keys, Xbox ONE Membership Deal and PSN Gift card on G2deal.com](https://www.g2deal.com/windows-10-enterprise-2019-ltsc-microsoft-cd-key-1-pc.html](https://www.g2deal.com/windows-10-enterprise-2019-ltsc-microsoft-cd-key-1-pc.html))
						- Both XP and 7, I remember how everyone hated them at the beginning, and only came to love them at the end.
						- ME on the other hand...****
						- **Edit**: Using this comment to do a Public Service Announcement. Win10 LTSC is a wayyyyy better version than all other versions of Win10. Way less aggressive auto update, able to TRULY turn off tracking, way more stable, way less update items, no in windows ads, no cortana, way less bloat functions, way lighter to run, faster and more responsive.<b></b>
						- **Edit2**: Answering a few common questions.<b></b>
						- 1. LTSC is meant for mission-critical systems (ATM, medical devices, military systems, scientific research, Medical Devices, ATM, Frigate Fire Control System, or Vending Machines.etc.) ****
						- So most consumers cannot purchase this through Microsoft, and therefore there is no support (not like MS had any support for consumers in the first place.) For most people, torrent is the only way to acquire LTSC.   ****[](https://github.com/kkkgo/LTSC-Add-MicrosoftStore)
						- **Edit3**: BUT TORRENTING THIS IS ILLEGAL, SO DO NOT DO THIS. THAT WOULD BE TERRIBLE. YOU WOULDN'T DOWNLOAD A CAR. YOU CAN ONLY DOWNLOAD MORE RAM.[](https://github.com/kkkgo/LTSC-Add-MicrosoftStore)
						- 2. Biggest downside is no company test their product in LTSC environment since there are so few users of LTSC, so your hardware/software is not guaranteed to work. But LTSC and Win10 is almost exactly the same that I haven't run into any problems except this one MIDI controller from 1992.[](https://github.com/kkkgo/LTSC-Add-MicrosoftStore)
						- 3. It doesn't come with Windows store, which can be good or bad depending on your use case. You can however unofficially add it through GitHub ([https://github.com/kkkgo/LTSC-Add-MicrosoftStore](https://github.com/kkkgo/LTSC-Add-MicrosoftStore))
						- 4. There is no support for HEIC, but you can get 3rd party support for it.
						- 5. Just FYI, LTSC is sooo light, it is pretty responsive even on a 2 core Atom.
					- Debloat and removing tracking
					  collapsed:: true
						- [https://github.com/builtbybel/privatezilla](https://github.com/builtbybel/privatezilla)
						- [https://github.com/10se1ucgo/DisableWinTracking](https://github.com/10se1ucgo/DisableWinTracking)
						- [https://github.com/Sycnex/Windows10Debloater](https://github.com/Sycnex/Windows10Debloater)
						- [https://github.com/W4RH4WK/Debloat-Windows-10](https://github.com/W4RH4WK/Debloat-Windows-10)
						- Removing Cortana
						  [https://www.techradar.com/how-to/how-to-disable-cortana-in-windows-10](https://www.techradar.com/how-to/how-to-disable-cortana-in-windows-10)
						- 1 Backlink
							- _See _[Debloat and removing tracking](https://workflowy.com/#/0151ede65e59)
					- Troubleshooting
						- Changing sleep and hibernate times to above 5 hours
							- Command Prompt
								- `powercfg /change standby-timeout-ac 1440` (minutes) = 24h until Sleep whilst plugged in
								- `powercfg /change standby-timeout-dc 1440` = 24h until Sleep whilst on battery
								- `powercfg /change hibernate-timeout-ac 2160` = 36h until Hibernate whilst plugged in
						- Can test whether you are administrator by going to C:/Windows/System32/ and right-clicking `calc.exe` to see if Run as Administrator pop-up works with your login
						- Bypass Windows 11 S mode Out of Box Experience (OOBE) networking step
						  collapsed:: true
							- Bypassing the networking step of the Windows 11 OOBE on an offline PC is usually achieved by pressing Shift + F10 to launch Command Prompt, followed by running the command `OOBE\BYPASSNRO`
							- Windows S mode is a version of Windows that is streamlined for security and performance. Because of this, applications such as Command Prompt and Registry Editor are disabled by default.
							- On machines running Windows 11 S mode, therefore, the process to bypass the networking step of the OOBE comprises:
								- Launch into Recovery Mode (this may require successive restarts before Windows has finished booting)
								- Select Troubleshoot > Advanced options > Startup Settings
								- Select option 7
								- Allow the PC to restart into the Windows OOBE
							- Now the familiar Shift + F10 combination may be used to launch Command Prompt and the usual command used to bypass network selection
							- Note that this method does not disable S mode; this requires a full reinstall of Windows with a non-S mode image
					- {Archive}
					  collapsed:: true
						- https://www.privacytools.io/#win10
				- Windows 10
				  id:: 66bcab7d-832c-419b-a6fa-7b14ff73ddc5
					- [those that are on the Windows 10 IoT LTSC builds will enjoy updates until 2032.](https://learn.microsoft.com/en-us/lifecycle/products/windows-10-iot-enterprise-ltsc-2021)
			- Ecosystem
				- Alternative installers
					- 1
						- there's a thing called an autounattend.xml file that will automate the installation of Windows 11. You can do some really cool customization like remove all bloatware, set the taskbar behavior, etc. but the coolest feature is the automatic creation of a local admin account so you don't need to connect a Windows account to the OS.
						- Here is the one I like to use: [https://schneegans.de/windows/unattend-generator/](https://schneegans.de/windows/unattend-generator/)
						- Make your selections, click generate, and simply drop the file on the root of the installation USB drive. Boot the computer up from the USB drive, sit back, crack a beer, and watch the magic happen. Then you will have your OS cleanly installed and have your offline account ready to go.
					- You can make your own using NTLite, no need to download random ISOs.
			- Related: ((65a98a52-b28c-43ea-b26b-7068a4421552))
			- ((63208fd2-1a0c-41a1-b013-49a8ccef23e1))
		- [MacOS](https://www.apple.com/uk/macos)
		  id:: 63734d16-48e6-44c2-a290-2e41a5927244
		  collapsed:: true
		  by ((63208fd2-65bc-4405-a355-1239401f84ab))
			- Pros/Cons
				- Cons
					- Sends a hash identifier and your IP address every time you open an app [https://reddit.com/r/apple/comments/oykemh/apple_plans_to_scan_us_iphones_for_child_abuse/h7u3vw5?context=3](https://reddit.com/r/apple/comments/oykemh/apple_plans_to_scan_us_iphones_for_child_abuse/h7u3vw5?context=3)
					- See client-side content scanning
					- *Compared to Linux*
						- Window management - tiling options are slow and less featureful, maximising takes several clicks, it hides apps dock/task manager, no thumbnails in ALT-TAB switcher
						- Software installation - no package manager so it's the same Windows approach of downloading random binaries instead of all on an app store/repo
						- Limited hardware support
						- Compatible hardware is expensive
						- Security and Privacy - MacOS is targeted far more by hackers, plus Apple collect a lot of analytics,
						- Customisation - MacOS pales compared to KDE
					- 1
						- [
						- ](https://news.ycombinator.com/item?id=45339137vote?id=45339137&how=up&auth=7afb6a76970db045c5474e46bd712226430c23c9&goto=item%3Fid%3D45339137#45339137)
						- [trueismywork](https://news.ycombinator.com/item?id=45339137user?id=trueismywork) [53 days ago](https://news.ycombinator.com/item?id=45339137item?id=45339137) | [parent](https://news.ycombinator.com/item?id=45339137item?id=45333097) | [context](https://news.ycombinator.com/item?id=45339137context?id=45339137) | [favorite](https://news.ycombinator.com/item?id=45339137fave?id=45339137&auth=7afb6a76970db045c5474e46bd712226430c23c9) | on: [I'm spoiled by Apple Silicon but still love Framew...](https://news.ycombinator.com/item?id=45339137item?id=45332859 "I'm spoiled by Apple Silicon but still love Framework") | [toggle all comments](javascript:void(0))
						-
						- I just got a work Mac and I have spent around 20 years now on linux before it. I was making a list compared to KDE (not pros/cons just differences) It is still a work in progress since its only a couple of days since im using it.
						- 1\. No delete button. I know you can do Fn delete but It is more problematic. And I do use delete often.
						- 2\. System keeps important system stuff in Library directory in home. Do not do remove any directories.
						- 4\. Os x doesnt quit apps and then expects me to go through all apps in windows switcher.
						- 5\. The spaces dont wrap around.
						- 6\. Finder is always in your alt +tab? Causes issues with switching.
						- 7\. Corners are round. How to Disable it control the roundedness
						- 8\. Alt +Tab doesnt automatically restore minimized windows.
						- 9\. App store is quite weak compared to archlinux
						- 10\. There is no spaces pager (a small bar at top where I can immediately see which desktop im in)
						- 11\. It seems that I cannot have windows of same app in multiple spaces.
						- 12\. Same app has only one window. Apple mail for example. Cannot copy text from email to settings.
						- 13\. How to Disable HTML display in apple mail.
						- 14\. Kmail has much better interface for signing
						- Both for viewing rhe signed emails and for deciding which key to use
						- 15\. Opening a new windows from spotlight is not possible
						- 16\. Download multiple wallpapers at same time is not possible
						- 17\. All operations related to an app should be inside an app. Alt+w for tab and ctrl+tab for switching makes me move two fingers instead of one.
						- 18\. Spectacle is so much better than screen shot on MAC os
						- 19\. Ramdisk on mac os x
						- 21\. Threads view in emails isnot possible in apple mail
						- 22\. Application specific power optimization (for good battery life) on OS X
						- 23\. Better security and access on OSX for apps.
						- 23\. Switching between apps of same windows on OSX does not bring up a visual aid..
						- 24\. Long press leads to accents which is very cool but also I didn't use it.
						- 25\. Left-clicking in a window to raise it \_sometimes\_ performs actions in the app (e.g. clicking a button or scrolling the window) and \_sometimes\_ only raises the window. It seems to depend on the app.
						- 26\. No ability to use focus-follows-mouse.
						- 27\. Home/End keys send you to the top/bottom of the whole document instead of the start/end of a line. The latter is much more useful to me and I use it all the time. You can change this behavior with a terminal command followed by rebooting, but some programs still do whatever they want.
						- 28\. Automatic text replacements change the text you entered into the text that Apple thinks you mean. (Can also be disabled.)
						- 29\. Holding down an alphanumeric key brings up an accept/symbol selector, as on iPhone. This isn't compatible with many terminal applications like vim.
						- 30\. The dock has a tendency to move automatically to another display when there is a maximized window on that display. (I know how to move the dock by going bottom of the display and moving the mouse down, this isn't that.)
						- 31\. The camera notch can hide icons and you have no way to get to them without either connecting and external display or a workaround like [https://github.com/dwarvesf/hidden](https://github.com/dwarvesf/hidden).
		- ## ((65a98a52-b28c-43ea-b26b-7068a4421552))-based alternatives
		  collapsed:: true
			- ## [Linux](https://kernel.org/)
			  id:: 65a98a52-b28c-43ea-b26b-7068a4421552
			  collapsed:: true
				- Pros/Cons
				  collapsed:: true
					- Pros
						- Free as in beer
						  collapsed:: true
							- Price of Windows license is built into PC hardware costs
							- Lots of free [[Open-Source Software]]
						- Freedom
						  collapsed:: true
							- Have you ever tried to disable something that windows insists you use? Like all the telemetry? Just try to stay on top of that. Impossible because you're not in charge of your machine, Microsoft is. You change it, they just change it back. Frustrating.
							  collapsed:: true
								- On Linux? Its yours. Change anything you want.
								- All arguments of convenience go out the window when you are not in control.
							- Lots of [[Open-Source Software]]
						- Privacy
						  collapsed:: true
							- No 10 screens of agreeing to limited data collection at best during setup of Windows
							- Required Microsoft account on Windows
						- Lightweight
						  collapsed:: true
							- 20GB storage space for Windows, Linux usually uses 10GB max
							- Far less RAM on many distros e.g. 300MB for Puppy, similar for xfce
						- Near virus-invulnerable
						- Large community who will pressure OEMs to open-source their drivers, and shame proprietary userspace software
						- Software management is far better
						  collapsed:: true
							- Flatpaks and Snaps for sandboxing by default
							- Package managers by default. Windows has Chocolatey but most apps not present on it
							- App store equivalents e.g. Discover. Windows now has Microsoft Store but most apps not available on it
							- Windows involves downloading random EXEs
							- Forced operating system updates and forced restarts
							-
						- Customisation
						  collapsed:: true
							- KDE is far more configurable than Windows
							- [/r/unixporn](https://reddit.com/r/unixporn)
								- [Making sure you're not a bot!](https://redlib.northboot.xyz/r/unixporn/comments/1l5ll27/comment/mwhp1mu/)
								-
							-
						- Lots of software that is exclusive or runs better on Linux
						  collapsed:: true
							- https://www.reddit.com/r/linux/comments/1eru8xy/what_linux_software_you_cant_live_without/
						- Experimental FOSS is usually Linux-only
					- Cons
						- [[2024-08-14 Wednesday]] Putting my laptop into sleep causes it to crash on wake, bluetooth sometimes doesn't connect, my AMD laptop is overheating
						- Moderate learning curve compared to Windows
						- Many ((66a98a52-9772-4779-9956-4684637041b1)) programs unavailable or compatibility with Windows programs can be hit-and-miss, though it's pretty good already
						  collapsed:: true
							- See Linux gaming for Proton/Steam Play improvements
							  [[Videogames]]
							- Many games can be played through GPU passthrough insteadA
						- ((631fa93e-1087-4996-91b8-7526842b4ba8)) likely has a superior security model ((631fa93d-9604-49fd-b8d3-2731d6dc41bb))
						- ((65a98a50-cabf-42dc-9a06-413b96e93ae7)) GPUs require their proprietary drivers to get the best performance
						  collapsed:: true
							- Nouveau are the open-source drivers but they're still working on GTX 1050 support (Feb 2019) i.e. NV130 for GTX 1030-1080Ti and Titan X
							  https://nouveau.freedesktop.org/wiki/FeatureMatrix/
						- Usability issues (see ((62e11d87-874f-4112-8bd5-a0a8f6651248)) experience)
						- Replacing Linux with a microkernel is a goal of some entities like Android and GrapheneOS
						  collapsed:: true
							- GrapheneOS - [Roadmap includes hypervisor + VMs, then switching to a microkernel + containers for Linux, then not needing containers since all software runs natively ](https://workflowy.com/#/a86d25f96f3b)
							- Flutter being Google's cross-platform mobile+desktop framework also means they'll have desktop apps ready to replace Linux ones
							- 2 Backlinks
								- See [Replacing Linux with a microkernel is a goal of some entities like Android and GrapheneOS](https://workflowy.com/#/7840d536acbd)
								  #PC-Linux
								- See [Replacing Linux with a microkernel is a goal of some entities like Android and GrapheneOS](https://workflowy.com/#/7840d536acbd)
						- ((663b24fb-7a2d-45e5-aa2b-8882fea439e3))
						- ### Distro marketshare
						  collapsed:: true
							- Meta
								- Mint, Debian and ((66bcb5ff-7b0f-4883-81e2-3456743c0fc8)) look like viable alternatives if Kubuntu ever goes immutable and forces ((63ad9567-8df0-4f60-ab52-545451251156))
							- August 2024
								- lunduke's graph
									- ![image.png](../assets/image_1723640652747_0.png)
								- [Desktop Linux Market Share: August 2024](https://itsfoss.com/linux-market-share/)
									- ![image.png](../assets/image_1723645425660_0.png)
								- [Linux Statistics 2024 - TrueList](https://truelist.co/blog/linux-statistics/)
									- ![image.png](../assets/image_1723645497840_0.png)
								- [DistroWatch.com: Put the fun back into computing. Use Linux, BSD.](https://distrowatch.com/dwres.php?resource=popularity)
									- ![image.png](../assets/image_1723645579389_0.png)
						- [[2024-10-24 Thursday]] [Several maintainers aligned with sanctioned Russian companies were removed](https://www.reddit.com/r/linux/comments/1g9seh9/several_linux_kernel_driver_maintainers_removed/)
						  id:: 671a155e-4649-4ab2-a46b-c3b197c795be
						  collapsed:: true
							- Sanctions only apply to certain people and companies, not national origin. What Greg Kroah-Hartman did is in fact in violation with the U.S law.
							- [[2024-10-24 Thursday]] [Update: it's for companies wich are under US sanctions](https://www.phoronix.com/news/Linux-Compliance-Requirements)
								- If your company is on the U.S. OFAC SDN lists, subject to an OFAC sanctions program, or owned/controlled by a company on the list, our ability to collaborate with you will be subject to restrictions, and you cannot be in the MAINTAINERS file.
								- Anyone who wishes to can query the list here:
								- https://sanctionssearch.ofac.treas.gov/
								- In your specific case, the problem is your employer is on that list. If there's been a mistake and your employer isn't on the list, that's the documentation Greg is looking for.
								- I would also like to thank you for all your past contributions and if you (or anyone else) would like an entry in the credit file, I'm happy to shepherd it for you if you send me what you'd like.
								- Again, we're really sorry it's come to this, but all of the Linux infrastructure and a lot of its maintainers are in the US and we can't ignore the requirements of US law. We are hoping that this action alone will be sufficient to satisfy the US Treasury department in charge of sanctions and we won't also have to remove any existing patches."
					- Unsorted
						- 1
						  collapsed:: true
							- sergeykish:
							- As Linux user the article does not resonate with me. The actual points are discarded points
							- Linux is more stable and reliable.
							- I've reinstalled Windows so many times, never reinstalled Linux. System is separate from the user, I can remove all user configurations and it would work like new.
							- Linux is more secure and private.
							- I have so many packages, they are free and safe. I've tried Windows recently, have to install software from the web. It is scary.
							- No telemetry by default. I send package statistics, have install it myself:
							- pacman -S pkgstats  Linux is faster and less bloated
							- There are many communities, some run Destkop Environments, I run quite minimal setup, boot to graphical environment takes 100MB RAM. Old netbook is router/NAS, 1GB is plenty.
							- Linux is more flexible and customizable.
							- Primary reason I've switched. So many options, it is awesome! GNOME, KDE, XFCE, OpenBox, wmii, dwm, xmonad. Entire distributions — Ubuntu, Arch, Nix and many more.
							- Linux gives you more control over your computer.
							- There was liberating feeling — my computer is just a hardware. Never felt it with Windows, it always had its own way. You know, some people kick their computers in rage. That has gone.
							- Linux has a great driver support for supported hardware, it is like complaining about hackintosh. Windows adopting command line and package management tools. Yes, had to stop gaming, that's changing with Proton. I find Windows UI atrocious, my desktop for comparison:
							- http://sergeykish.com/side-by-side-no-decorations.png
							- multiple workspaces, no decorations, not even browser scroll bar. I'd like to have universal solution for sticky headers.
							- And, maybe, the most valuable — Linux is getting better while Windows and macOS getting worse. Telemetry, advertisement, walled garden, executable restrictions, firewall bypass, proprietary hardware — scandal after scandal. While on the Linux side — AMD GPU, Wayland, Flatpak, Steam Proton, web applications, better than ever laptops support.
						- 2
						  collapsed:: true
							- Linux runs better on both new and older hardware. Better as in programs open faster, the file manager opens faster, the task manager opens faster. Everything uses less memory and less CPU cycles. Everything is snappier.
							- Linux users don't have to worry nearly as much about malware, trojans, viruses, exploits. It's more secure.
							- Linux distros generally don't annoy users with stealthy automatic forced updates.
							- Linux distros have a better app store experience than Windows, plus most of whatever there is free without much if any risk.
							- Linux doesn't have any phone home telemetry type "features" built into the OS.
							- Linux user experience is much more customizable. There are a much greater variety of tools at your disposal to customize how you want your desktop to look and operate.
							- Linux is free.
						- Free, near virus-invulnerable, lightweight, with no backdoors or spyware - but has a learning curve
						  collapsed:: true
							- The choice of operating systems are:
								- Expensive, virus-prone, bloated, with built-in backdoors and spyware - but has no learning curve
								- VS
								- Free, near virus-invulnerable, lightweight, with no backdoors or spyware - but has a learning curve
							- It's hardly a choice these days.
						- [https://github.com/nbeaver/why-linux-is-better](https://github.com/nbeaver/why-linux-is-better)
						- [https://reddit.com/comments/bddq5u/comment/ekxifpa](https://reddit.com/comments/bddq5u/comment/ekxifpa)
						- [Main Linux problems on the desktop, 2023 edition or why Linux sucks on the desktop](https://itvision.altervista.org/why.linux.is.not.ready.for.the.desktop.current.html)
						- [Shared post - Linux Sucks 2024](https://lunduke.locals.com/post/5243803/linux-sucks-2024)
						  collapsed:: true
							- Red Hat restricting source code
							- Ubuntu going to immutable and Snaps-only
							- There's no news outlets except him covering the anti-white discrimination and other woke controversy
							- Linux Foundation only spends 2% of it's funding on the kernel itself, and kernel LTS support is now deprecated. It spends 6x as much on AI
							- 31:20: They spent their $200M a year on blockchain, AI, vaccine passports, green energy, COVID contract tracing, medical industry analytics, farm management, power grid management, D&I "Badging"
							- 70% of Linux Foundation board member companies are GPL violators
							- The funding of open-source projects and foundations in 2021
							  collapsed:: true
								- Mozilla, The Linux Foundation and Wikimedia get an order of magnitude more than the rest, so have been removed in the following graph
								  collapsed:: true
									- ![image.png](../assets/image_1723642825227_0.png)
								- ![image.png](../assets/image_1723642782916_0.png)
									- KDE and GNOME each get only about $250k
									- The Linux Foundation could spend 1% of their income which would immediately increase theirs by $2M/year. Instead they spend on stuff like 6% on AI, and lots on blockchain, contact tracing etc
								-
							- Related: [Shared post - Every "Linux Sucks".  In order.  Free for all to watch.](https://lunduke.locals.com/post/4633552/every-linux-sucks-in-order-free-for-all-to-watch)
					- Unclear
						- Unstable ABI (Application Binary Interface)
						  collapsed:: true
							- What
							  collapsed:: true
								- Drivers require a stable ABI otherwise when the kernel binary changes, their drivers do not work properly anymore with the kernel
								- An API for drivers to plug into could provide the necessary functionality, and the closest thing to this being kernel modules, however
							- Pros/Cons
							  collapsed:: true
								- Pros
									- Unstable ABI incentivises OEMs to open-source and upstream their drivers
										- It's a lot less work than them having to keep updating their drivers to stay compatible
									- Disincentivises using potentially harmful closed-source firmware
										- E.g. modem, secure enclave chip, WiFi, Bluetooth
								- Cons
									- See [Replacing Linux with a microkernel is a goal of some entities like Android and GrapheneOS](https://workflowy.com/#/7840d536acbd)
							- Workarounds
							  collapsed:: true
								- See Android Common Kernel
									-
								- See microkernels
						- ((649b13cf-a825-48f5-ae83-b47b6ad6bff9))
					- _Related:_
						- ((66a98a52-9772-4779-9956-4684637041b1))
						- ((649b13cf-a825-48f5-ae83-b47b6ad6bff9))
				- FAQ
				  collapsed:: true
					- Linux is the kernel, but most people are referring to kernel + operating system + desktop environment (AKA GNU/Linux)
					- Distribution differences
					  collapsed:: true
						- Packaging schemes
						  id:: 63a88eb7-4bbe-4ecc-a7a3-8293dba06bb7
							- Will apps run on any Linux distro?
								- There are two major packaging schemes - RedHat's RPM and Debian's DEB. Those are incompatible - you cannot install an RPM on a Debian-based distro (Ubuntu etc.) or vice-versa. But chances are, programs are available for both so you just install with your package manager and don't worry about the details.
								- RedHat/CentOS produce good stable distros for commercial use, with guaranteed support for years, But they are very strict about licensing and won't include anything that is not open-source. Ubuntu is not so fussy and are more likely to include things like media players that have patented codecs. They also have a "stable" version with extended support.
							- With the help of openSuse Build System software gets continously delivered with the good old standard repo mechanism to multiple distros
							  e.g. https://software.opensuse.org/download.html?project=home:manuelschneid3r&package=albert
							- Alternative there are distribution-agnostic packaging schemes - AppImage, Flatpak and Snap
							- ((6313455f-8855-4849-8ac2-8012e198774c))
						- Desktop Environment (usually KDE or GNOME 3)
						  See Ubuntu-based for various DEs https://workflowy.com/#/e24d1054a342
					- History
					  collapsed:: true
						- ![image.png](../assets/image_1700824160202_0.png)
				- [[Linux setup SOP]]
				- Apps
				  collapsed:: true
					- ((649b1413-97fc-4415-a8d7-40423f92c363)) : Sandboxing
					- CLI-only workflow
					  id:: 65a98a51-fd0e-48d2-a3af-9d7897c1a103
					  collapsed:: true
					  AKA terminal-based workflow
						- Applications
							- Emacs
							- Yakuake (full-screen terminal with tabs) - fountain for all these apps?
							- NeoMutt (email client)
							  collapsed:: true
								- [https://neomutt.org/](https://neomutt.org/)
								- New version of mutt
								- Review 1
									- dm319:
									- Just in case anyone is curious as to why someone would use mutt, here are a few:
									- 1. I can edit and compose emails in my favourite editor
									- 2. Near instantaneous launch
									- 3. Can launch multiple instances, allowing for viewing/searching to happen concurrently
									- 4. Rapid search with advanced searching features - i.e. find all emails that have 1 or more attachments sent to me from within a month of 1/1/2019 from someone with a "csu" email - would be l ~f csu ~X > 0 ~d 1/1/2019*1m
									- 5. Deal rapidly with emails - I have 'd' for delete and move to next and 'y' for archive and move to next, I can zip through emails quicker than on any other email client I have used
									- 6. I can work effectively when I'm offline or have patchy internet/signal (i.e. on a train) using mbsync or similar to store emails locally and sync up with my gmail account when I have internet.
									- 7. Highly configurable - custom set-up for what data I want to see in my inbox, and what colours to use and what to highlight
									- 8. Intelligent reply-all - it knows I have several email aliases that belong to me so I don't reply to myself
								- Use shift-F to mark the email as “flag”. It's exactly the same functionality as Gmail's starring, and maps to it over IMAP.
								- CTRL-G to exit actions
								- Get isync for IMAP email providers
								- For sending I use msmtp
							- ((644c0b17-00c6-4352-bf6d-1c09ebfc157b))
							- [A terminal-based workflow for research, writing, and programming | Hacker News](https://news.ycombinator.com/item?id=25297268)
							-
						- Related: [[Videogames]] : ((638e80ea-8e3c-48f6-9ee6-e0587b410113))
				- **To Do**
				  collapsed:: true
					- Windows dual boot
					- Use GPU passthrough via VirtualBox/KVM (works best with 2 GPUs e.g. iGPU + eGPU)
					  collapsed:: true
						- https://www.reddit.com/r/linux/comments/9y82b1/im_not_going_back_to_windows/e9zg8fu
					- Maps
					  collapsed:: true
						- GNOME Maps
						  https://www.ghacks.net/wp-content/uploads/2018/04/GNOME_Maps.jpg
							- gnome-maps
						- Marble for KDE
						  https://marble.kde.org/
						-
					- FocusWriter
					  collapsed:: true
						- https://www.ghacks.net/2018/05/06/a-look-at-focuswriter-distraction-free-text-editor-on-gnu-linux/
					- Setup yakuake-session
					  collapsed:: true
						- Why - better integration with Dolphin in order to replace Konsole
						- Requires wmctrl to change focus if yakuake is already open
						  sudo apt install wmctrl
						- Get into Dolphin context menu
							- sudo cp ServiceMenus/yakuakehere.desktop /usr/share/kservices5/ServiceMenus/
							- Edit the desktop file - replace exec with:
							  /usr/bin/yakuake-session/yakuake-session --workdir %f
					- Setup PGP for Git
					  collapsed:: true
						- https://github.com/lfit/itpol/blob/master/protecting-code-integrity.md
					- AppArmor
					  collapsed:: true
						- https://www.reddit.com/r/privacy/comments/5nztld/finally_going_for_linux_some_questions/dchq1m8/
					- ((67375db8-174c-4081-9b1e-6cbea5cd3fd6))
					- Database manager
					  collapsed:: true
						- HeidiSQL
							- Running on Wine requires to override Wine's builtin Direct2D library with the native one.
							  https://github.com/HeidiSQL/HeidiSQL/issues/83#issuecomment-375969129
						- https://alternativeto.net/software/dbeaver/about/
						- https://teamsql.io/
					- https://nims11.wordpress.com/2012/04/27/hostapd-the-linux-way-to-create-virtual-wifi-access-point/
					- Use WINE for some software, and a Windows VM for others
					- sudo apt install vrms to check what non-free packages are on PC
					  collapsed:: true
						- https://askubuntu.com/questions/1093752/how-to-make-sure-im-not-using-any-proprietary-software-after-installation
				- # Documentation
					- How to Create Launchers (Shortcuts in Windows)
					  id:: 65a98a51-1a77-4340-959e-8cb1b5051535
					  collapsed:: true
						- Right-click > Create New > Link to Application
						- Change the name and pick an icon
						- Applications tab
							- Description: KDE Terminal Application
							  i.e. longer description
							- Comment: Konsole
							  i.e. app name
							- Command: /usr/bin/konsole
							  i.e. file path
						- _Notable ones_
							- ((63134593-906c-43b5-96fe-33dc2c34fda4)) launchers
								- Native
								  `firefox -P "default"`
								- MASTER
								  id:: 65a98a51-3ba2-43ed-9d89-1bc32990dae8
								  `/home/boss/Downloads/MASTER_Firefox/firefox/firefox -new-instance -P "MASTER1"`
								- LEISURE
								  `/home/boss/Downloads/LEISURE_Firefox/firefox/firefox -new-instance -P LEISURE`
							- ((6539869d-fa8c-45f0-ad49-7d30ef190557))
					- Click on exe > remember this application > type in 'wine'
					- Task manager corollary - The ctrl-esc method essentially brings forth a "minimal" ksysguard. Minimal meaning that, for all intents and purposes, the only thing missing is the "System load" tab.
					- Programs which don't run in WINE - ManicTime
					- Edit the menu
					  collapsed:: true
						- https://docs.kde.org/trunk5/en/kde-workspace/kmenuedit/quickstart.html
					- SOPs
						- Migrating from Windows to Linux
						  collapsed:: true
							- [I made an app for Windows to automatically check Linux compatibility with all installed Windows programs, games, etc](https://teleportsite.pages.dev/)
							- AlternativeTo.net
						- Upgrading to next distro release
						  collapsed:: true
						  id:: 635037c3-a9a8-42d4-b2a6-236db1e2c86d
							- TL,DR
							- Full
								- `apt-get upgrade` vs. `apt-get dist-upgrade`
									- Let's first look at the difference between apt-get upgrade and apt-get dist-upgrade (as that is where much of the confusion lies). When you run apt-get upgrade, it only upgrades that which has a new release available to the platform, as defined in /etc/apt/sources.list or in /etc/apt/sources.list.d/.
									- However, when you run apt-get dist-upgrade, it will intelligently install or remove packages as needed, in order to complete the upgrade. Apt-get dist-upgrade has a smart conflict resolution system, so it will attempt to upgrade the most important packages, at the expense of those deemed less important.
									- Apt-get upgrade does not remove packages, it only upgrades. Can you use sudo apt-get dist-upgrade as your regular upgrade tool? Certainly. Just remember, it will delete software--if it is required to complete the process.
								- ```bash
								  do-release-upgrade
								  ```
									- The do-release-upgrade command, on the other hand, is responsible for upgrading from one release to another. So if you want to upgrade from Ubuntu 18.10 to 19.04, you use do-release-upgrade.
									- However, in order to use this command, the system must first be fully upgraded. To do that, you should first run `sudo apt-get upgrade`, followed by `sudo apt-get dist-upgrade`. When those two complete, you can then run `sudo do-release-upgrade` and wait for the magic to complete.
							- Related: ((635037c3-6032-4f23-9ba6-288274d6e473))
						- Opening a terminal to the current directory in Dolphin
						  collapsed:: true
							- Pressing F4 while in Dolphin will show an embedded terminal that changes directory as you browse + you can drag names down to the shell.
							  https://www.reddit.com/r/kde/comments/9e4p6p/daily_tip_pressing_f4_while_in_dolphin_will_show/
								- Pressing F3 will split the view vertically. Pressing F2 will rename the current file. Pressing F1 will open the help. Pressing F5 will re-load the current directory.
								- F10 for new folder. Very useful when you need to split up a bunch of files into directories.
								- having the terminal enabled by default in settings. Using F4 to hide it if it's in the way.
							- Most Midnight Commander style file managers have at least a command line run box that follows the current folder, some have a full terminal such as Krusader.
							- Shift+F4 you open an independent konsole window, starting in the current directory you are on.
					- _Troubleshooting_
					  collapsed:: true
						- Recovering files from a borked internal SSD
						  collapsed:: true
							- Boot from a Kubuntu live USB
								- Likely have to use a persistent live USB (involves using mkusb)
							- sudo rsync -r --info=progress2 /media/kubuntu/xxxx/home/ home 1/
							  Assuming this is being run in Dolphin terminal whilst looking at the intended target directory
						- Fixing no audio from laptop speakers
						  collapsed:: true
							- Followed these steps
							  source:: [https://askubuntu.com/a/117892](https://askubuntu.com/a/117892)
								- sudo apt-get update
								- sudo apt-get upgrade
								- sudo apt-get purge linux-sound-base alsa-base alsa-utils
								- sudo apt-get install linux-sound-base alsa-base alsa-utils
								- Reboo, wait for BIOS to update
						- ((65a98a51-f005-464b-b741-f1f4ca7eb39e))
						  id:: 65a98a51-cc02-4bf3-aae4-3fcda8480530
						  collapsed:: true
						- Shortcuts to restart KDE GUI or X or Wayland
						  intralink2:: https://workflowy.com/#/67de5130e57b
						- Check if a particular package is already installed
						  collapsed:: true
							- To check whether a package is installed or not:
								- dpkg -l {package_name}
								- dpkg -l vlc
							- To use Grep to search:
								- dpkg -l | grep {keywords}
								- dpkg -l | grep pdf
						- Swapping repo to older package source?
						  collapsed:: true
							- Mainly if you're using an older distro that you don't want to upgrade yet
							- sudo nano /etc/apt/sources.list
								- Modify your sources.list to point to
								- http://old-releases.ubuntu.com/
								- instead of the current
								- http://<country-code>.ubuntu.com/
						- Finding packages for older Ubuntu distros
						  collapsed:: true
							- https://packages.ubuntu.com/
							- http://old-releases.ubuntu.com/
							- http://archive.ubuntu.com/ubuntu/
						- How to install the dependencies + DEB file
						  collapsed:: true
							- Code
							  $ sudo dpkg -i package.deb
							  $ sudo apt-get -f install
							- [source] https://askubuntu.com/a/40050
						- tty = text-only/virtual console
						  collapsed:: true
							- https://askubuntu.com/questions/481906/what-does-tty-stand-for
							- Bug - ALT+F2 to enter tty2; ALT+F1 to exit back to GUI
								- Solution
								  sudo kbd_mode -s
						- https://askubuntu.com/questions/128524/how-to-list-dependent-packages-reverse-dependencies
						- [[2025-04-27 Sunday]] Long boot time (has been like this for months though)
						  id:: 680df87e-d353-4276-b2f6-29ee554899cd
						  collapsed:: true
							- `systemd-analyze`- see how long boot takes
							- `systemd-analyze blame`- see what services are slowing down boot
							- [[2025-04-27 Sunday]] Attempted to disable using `sudo systemctl disable plocate-updatedb.service`
					- `#` - requires given linux commands to be executed with root privileges either directly as a root user or by use of sudo command
					- $ - requires given linux commands to be executed as a regular non-privileged user
					- [Systems Administration](https://workflowy.com/#/2588926a4e8a)
					  #SysAdmin
					- System Sleep State
					  id:: 65a98a51-73de-4150-be84-186c2c2b6a83
					  collapsed:: true
						- _Sleep states_
						  id:: 63734d15-b6e6-42b1-9f2d-2f3199d4d222
							- S0 - Working State
							  collapsed:: true
								- In this state, your PC is awake and working
							- S0ix - Modern Standby
							  id:: 6306a76f-8b03-4f9b-b958-bc22f546ed4d
							  collapsed:: true
							  AKA Windows Modern Standby
								- Pros/Cons
									- Pros
										- Allows background network activity e.g. updates
										- Faster resume from a low power state
									- Cons
										- uses much more battery
								- On any Modern Standby system, the system remains in S0 while in standby
								- On many modern laptop this has replaced ((63734d15-b4d4-4c85-8087-b02150a85f59))
								- {Archive}
									- [Microsoft is Forcing me to Buy MacBooks - Windows Modern Standby - YouTube](https://youtu.be/OHKKcd3sx2c)
							- S1- CPU Stopped
							  collapsed:: true
							  AKA Standby
								- In this state, your PC is technically in standby and this is the default standby state if S3 is not supported. Power consumption is 5-30 Watts
							- S2 - Suspend-to-idle
							  id:: 65a98a51-3c68-4866-8f78-d7fec684f7b0
							  collapsed:: true
								- Processor is off?
								- [https://www.kernel.org/doc/html/v4.18/admin-guide/pm/sleep-states.html#s2idle](https://www.kernel.org/doc/html/v4.18/admin-guide/pm/sleep-states.html#s2idle)
								- Consumes a lot of power in my experience (Dell XPS 13, it's been the default for months or longer Sat, Oct 16, 2021). Now swapping to ((63734d15-b4d4-4c85-8087-b02150a85f59))
							- S3 - Suspend to RAM (context saved to RAM)
							  id:: 63734d15-b4d4-4c85-8087-b02150a85f59
							  collapsed:: true
							  AKA Deep Sleep
								- In this state, your PC in standby and all fans, hard drivers and other devices are powered down into a sleep state. Power consumption is less than Five Watts.
								- Related: ((6306a76d-4ea8-470c-a1d7-c0500025b016))
							- S4 - Suspend to Disk (Context saved to hard drive)
							  id:: 65a98a51-b70f-4593-8e37-20938de20589
							  collapsed:: true
							  AKA Hibernate
								- Your PC has saved the contents of RAM to the hard disk and is pretty much tuned off. Power consumption is less than Five Watts. This isn’t very useful for desktop PCees and is mostly used in Laptops where battery drainage is far better than if you are in S3.
								- ## How to enable
						- Documentation
						  collapsed:: true
							- Checking what sleep states are being used
								- Show available sleep states, with selected one being [highlighted]
								  cat /sys/power/mem_sleep
								- Check what sleep mode was used on recent suspends
								  sudo dmesg | grep "suspend entry"
								- _Windows-only_
								  powercfg -a
							- How to enable S3
								- Now, as I mentioned there are some requirements before you can use S3.
								  collapsed:: true
									- Motherboard must support S3
										- Latest Intel CPU that supports S3 is 10th generation - i.e. Tiger Lake doesn't have it, instead has s0ix Modern Standby
										- [Framework Laptop (2021)](https://workflowy.com/#/8d6278d3c42c) uses 11th gen Intel CPU, thus doesn't support S3 sleep for power saving
											- Complaints about high battery usage of S0 standby. S2 might be supported but S3 definitely isn't
											  [https://community.frame.work/t/high-battery-drain-during-suspend-windows-edition/4421/140](https://community.frame.work/t/high-battery-drain-during-suspend-windows-edition/4421/140)
											- 1 Backlink
												- See [Framework laptop uses 11th gen Intel CPU, thus doesn't support S3 sleep for power saving](https://workflowy.com/#/c61c1f0e51b1)
									- S3 support must be enabled in the BIOS (many motherboards do not do this and default to S1)
										- See [S3 sleep/standby no longer in BIOS](((6306a76d-4ea8-470c-a1d7-c0500025b016))) for Dell laptops, even on older Intel CPU
									- OS must support S3 (Windows XP does)
								- How to enable deep sleep (temporarily) on Ubuntu 21.04
								  collapsed:: true
									- Switch to root user (since sudo with this command below doesn't work)
									  sudo su root
									- Verify the current [selected] sleep mode
									  cat /sys/power/mem_sleep
									- Change sleep mode to [deep]
									  echo deep > /sys/power/mem_sleep
									- Verify the current [selected] sleep mode
									  cat /sys/power/mem_sleep
								- How to enable deep sleep (permanently) on Ubuntu 21.04
								  source:: [https://community.frame.work/t/ubuntu-21-04-on-the-framework-laptop/2722/8](https://community.frame.work/t/ubuntu-21-04-on-the-framework-laptop/2722/8)
								  collapsed:: true
									- See [Enable IOMMU in grub bootloader config](https://workflowy.com/#/7db7cbaed4c1)
										- Open GRUB in a text editor
										  sudo nano /etc/default/grub
									- Find the following line in the /etc/default/grub file:
									  GRUB_CMDLINE_LINUX_DEFAULT=“quiet splash"
									- Change it to:
									  GRUB_CMDLINE_LINUX_DEFAULT=“quiet splash mem_sleep_default=deep”
									- sudo update-grub
									- Reboot
									- a. To verify, run the following from the terminal:
										- cat /sys/power/mem_sleep
									- b. If the output is s2idle [deep] then deep sleep is enabled (note the brackets are on “deep”)
							- Bug report - on Ubuntu for Dell XPS 13 it defaults to [s2idle] rather than [deep]
							  [https://bugs.launchpad.net/ubuntu/+source/linux/+bug/1808957](https://bugs.launchpad.net/ubuntu/+source/linux/+bug/1808957)
							- [S3 sleep no longer in modern Intel processors (e.g. Tigerlake)](https://community.frame.work/t/linux-deep-sleep/2491/5), instead uses's Microsoft's ((6306a76f-8b03-4f9b-b958-bc22f546ed4d))
						- Related: ((65a98a50-4b57-4816-931f-24253c6bc8b7)) [Doesn't support S3 sleep/standby?](((6306a76d-4ea8-470c-a1d7-c0500025b016)))
					- Running commands on startup/login
					  collapsed:: true
						- Running commands on login
							- Pros/Cons
								- Pros
									- Reliable since additional services only start on login, so they're guaranteed to be running already
							- See [nano ~/.profile](https://workflowy.com/#/02fefe6ede3e)
					- Keys to use when system freezes
					  id:: 67e81ad8-1e2c-487c-aba7-e3e00dfc8e5e
					  collapsed:: true
						- You should be able to press Ctrl+Alt+F4 (choose any number between 1 and 6, excluding the ones that have a GUI. On Ubuntu, both F1 and F2 have a GUI; it might be the same on Mint). This is effective if it's only the desktop that froze. This will allow you to manually investigate and kill frozen programs, and restart the desktop. Doing this is more advanced than my level of expertise, so I just do to the next step instead.
						- REISUB
							- Otherwise, look up REISUB (that's "busier" spelled backwards). You need the SysRq key; see the note below.
								- Press SysRq+R. Wait a second.
								- Press SysRq+E. Wait 3 or 4 seconds.
								- Press SysRq+I. Wait 3 or 4 seconds.
								- Press SysRq+S. Wait 3 or 4 seconds.
								- Press SysRq+U. Wait a second.
								- Press SysRq+B. This reboots the computer. (You can use O instead of B to turn off the computer.)
								  
								  This closes all files cleanly, so that the hard drive isn't corrupted (although you might lose some work). It's an emergency shut-down, which is better than killing your machine (holding down your computer's power key for several seconds or unplugging it).
								  
								  On Ubuntu, and therefore possibly Mint, REI are disabled, so those keys will do nothing.
								  
								  Note about SysRq: The SysRq button depends on both your distribution and your keyboard. On most systems with an English Windows keyboard, it's Alt+PrintScreen, so SysRq+R would actually be Alt+PrintScreen+R.
						- CRTL ALT BK SPACE that restarts screen on some distros
						- Use Ctrl+Alt+Fn (F2 or F3...) it start a tty terminal and login with username and password and use pkill or htop with F9 to kill the process. Usually Ctrl+Alt+F1 will send back to your gui Mint session if not try the other Fn keys one of them will be that session.
						- Some distros will let you do a safe shutdown by holding ALT_GR + PRINT SCREEN and press O
					- ## Internals
						- Directories
						  collapsed:: true
							- [Filesystem Hierarchy Standard - Wikipedia](https://en.m.wikipedia.org/wiki/Filesystem_Hierarchy_Standard)
							- [Why Linux has a scattered file system: a deep dive ](https://www.reddit.com/r/linux/comments/1nc40h2/why_linux_has_a_scattered_file_system_a_deep_dive/)
								- **Chapter I -- what's in** `/`
								- **Chapter Ia -- system file directories**
								- These are directories where system files live.
								- In the traditional Linux view, the "system" basically means "your package manager". So this includes the core system components and programs installed through your package manager (be it apt on Debian/Ubuntu, dnf on RHEL/Fedora or pacman on Arch). There is no difference real between "system files" and "program files" on Linux when the programs are installed as packages. The "base" system, the one you get right after install, is just a bunch of packages, with many "spins" (Fedora KDE, Xubuntu etc.) basically being just different sets of packages to install as base.
								- Users do not generally do not write files here, but they read or execute them all the time -- programs, fonts, etc.
								- The directories are:
								- `/usr` -- static files (binaries, libraries, resources, fonts, etc.)
								- `/var` -- dynamic files (logs, databases, etc.)
								- `/etc` -- configuration files
								- `/boot` -- boot files
								- For example, you may want to mount `/usr` and/or `/etc` as read only after configuring your system to harden it. You may want to share `/etc` around multiple systems that should be configured identically. You may want to only backup `/etc` and `/var` since `/usr` and `/boot` can be easily recreated by the package manager.
								- These are not only theoretical use cases. The desktop distro I use is a version of Fedora Immutable, in which `/usr` is mounted as read-only, `/var` is mounted as read-write and `/etc` is mounted as an overlay filesystem, allowing me to modify it, but also allowing me to view what changes I made to system configuration and easily revert if needed.
								- `/boot` is kept separate because it sometimes needs to be separate, but not always. A use case for this (not the only one) is what I use: most of my disk is encrypted, so `/boot` is a separate, unencrypted partition, so the kernel can launch from there and decrypt the rest of my disk after asking me for the password.
								- **Chapter Ib -- user file directories**
								- These are the directories where users can store files and the package manager will not touch (but other system utilities may touch).
								- These directories are:
								- `/home` -- the home directories of users
								- `/root` -- the home directory of the root user (the administrator account)
								- `/srv` -- files to be served
								- Moreover, if you have a bunch of Linux servers that share user lists and have `/home` mounted on the network (allowing the user to log into any server and see their files), the `/root` home should still be per-server.
								- `/srv` is just a convenient place to store files, such as those shared via FTP, HTTP, or any other files you need to store that is not just "a user's files". It's entirely unstructured. No tools that I know of create directories here without being told to, so it's a nice place to just put stuff on a server. Not very useful on a desktop.
								- **Chapter Ic -- temporary mount points**
								- These are mostly empty directories (or directories of empty directories) made for mounting partitions, removable drives, .ios's etc. that would not make sense anywhere else in a filesystem -- usually temporarily
								- These directories are:
								- `/mnt` -- for manual mounting
								- `/media` -- for automatic mounting of removable media
								- **Chapter Id -- virtual file systems**
								- These are directories who's contents don't "actually exist" (on disk). One of Linux's great strengths, especially from a developer perspective, is that everything is a file, be it a real one on disk, or a virtual one. Programs that can write to a file, can also write to virtual files, be they disks, terminal windows or device control files.
								- These directories are:
								- `/run` and `/tmp` -- temporary files stored in RAM
								- `/proc` and `/sys` -- low level process and system information respectively
								- `/dev` -- device files
								  
								  Now, you can safely ignore `/proc` and `/sys` as a regular user. When you open the GUI ~Task Manager~ System Monitor, the GUI System Monitor will read from these places, but you don't need to do so manually.
								  
								  The `/run` and `/tmp` files are in-RAM places for temporary files. The reason there are two is historical and I won't go into it.
								  
								  `/dev` is where all of the devices are represented. You will be exposed to this when you, for example, flash a USB stick, and the flashing utility will allow you to select `/dev/sdb` (SATA drive B) to flash to. Hopefully, you will also get a user-friendly name ("Kingston DataTraveller 32GB) next to it.
								  
								  **Chapter Ie -- the** `/opt` **directory**
								  
								  There are some cases where programs do want to be installed in a Program Files manner with a huge directory of stuff. This is either stuff that was lazily ported, or stuff with a lot of data (100GB Vivado installs).
								  
								  This is what the `/opt` directory is for.
								  
								  The package manager will generally not touch it, but graphical installers of proprietary software may default to this place.
								  
								  In the case of large installs, it also makes it easier to put some of the sub-directories of `/opt`, or the entire thing, on a separate drive/partition. It also allows large installs to be networked mounted, in the case of many small computers using proprietary software from a local NFS server.
								  
								  **Chapter II -- the structure of** `/usr`
								  
								  **Chapter IIa -- the useful sub-directories of** `/usr` **that will always be there**
								  
								  These directories are:
								- `/usr/bin` -- executable meant to be run by users
								- `/usr/lib` -- shared libraries (dll's) (see bellow)
								- `/usr/share` -- non-executable resource files
								  
								  The reason libraries are all together is that each binary is generally dynamically linked, so if the same library is used by 10 different executables, it exists only once in the system.
								  
								  The reason binaries are all together is so that the shell can search in one place for all of them.
								  
								  **Chapter IIb -- the less useful or situational sub-directories of** `/usr` **that will usually always be there**
								  
								  These directories are:
								- `/usr/src` -- sources for packages on the system, generally installed by special `*-src` packages, usually empty or almost empty
								- `/usr/include` -- stuff for C programming. Should arguably be a sub-directory to `/usr/share`, but hey, C is the big daddy and gets special privileges
								- `/usr/games` -- name is self explanatory. No, this directory is not used today. It's a relic.
								  
								  **Chapter IIc -- the** `/usr/lib` **debacle**
								  
								  `/usr/lib` is meant to hold shared libraries (32-bit and 64-bit if multilib is supported) and also "executable resources" of packages. The major distros do not agree on where to put each of these things.
								  
								  On Debian/Ubuntu we have:
								- `/usr/lib/<package>` -- executable resources not meant to be run directly by users
								- `/usr/lib/x86_64-linux-gnu` -- 64-bit libraries
								- `/usr/lib/i686-linunx-gnu` -- 32-bit libraries
								  
								  On Red Hat/Fedora we have:
								- `/usr/lib` -- 32-bit libraries
								- `/usr/lib64` -- 64-bit libraries
								- `/usr/libexec` -- executable resources not meant to be run directly by users
								  
								  On Arch we have:
								- `/usr/lib` -- 64-bit libraries
								- `/usr/lib32` -- 32-bit libraries
								- `/usr/libexec` -- executable resources not meant to be run directly by users
								  
								  **Chapter IId -- the** `/usr/sbin` **debacle**
								  
								  `/usr/sbin` is a directory meant for binaries that are not meant to be run by users, but only by administrators and such. It's kind of a relic of the past, and Fedora has moved to replace `/usr/sbin` with a link to `/usr/bin` (it's that way on my system)
								  
								  **Chapter IIe -- the** `/bin`/`/lib` **debacle**
								  
								  Back in the olden days, there used to be a difference between the core system that lived on `/` and the fat system that lived on `/usr`. This is a relic of the past. For backwards compatibility, the following links exist:
								- `/bin -> /usr/bin`
								- `/sbin -> /usr/sbin`
								- `/lib -> /usr/lib`
								- `/libexec -> /usr/libexec` (on Red Hat/Fedora and Arch)
								- `/lib64 -> /usr/lib64` (on Red Hat/Fedora)
								- `/lib32 -> /usr/lib32` (on Arch)
								  
								  **Chapter IIf --** `/usr/local`
								  
								  A copy of all the directories described above exist under `/usr/local` (eg. `/usr/local/bin`, `/usr/local/lib`). This exists for packages that maintain the standard bin, lib, share structure, so would not fit in /opt. but are installed by the admin user manually and not through the package manager.
								  
								  This is to avoid conflicts and unwanted overwrites. Most source packages (eg. what you find on GitHub) default to installing here after compilation.
								  
								  **Chapter III -- the structure of** `~`
								  
								  **Chapter IIIa -- the wild wild** `.west`
								  
								  Programs need to store per-user data and they will generally do this in the user's home. This is `/home/bob`, `$HOME` or just `~`.
								  
								  Now, back in the olden days they did this with no real structure. In Linux, directories that start with a dot are "hidden", so they would just throw some directory in the home and store everything there: `~/.vim`, `~/.steam`, `~/.ssh`, etc.
								  
								  **Chapter IIIb -- the XDG directory system**
								  
								  Recently, an effort has been made to standardize the places programs put user files. This system mirrors the system hierarchy, but uses more modern naming for things.
								- `~/.local/share` -- equivalent to `/usr/share`
								- `~/.local/state` -- partially equivalent to `/var`; for program state
								- `~/.local/bin` -- equivalent to `/usr/bin`
								- `~/.config` -- equivalent to `/etc`
								- `~/.cache` -- partially equivalent to `/var`; for temporary files too big to store in RAM
								- `/run/user/<uid>` -- in RAM temporary files
								  
								  More details [here](https://specifications.freedesktop.org/basedir-spec/latest/).
								  
								  **Chapter IIIc -- flatpaks**
								  
								  Flatpaks are containerized desktop apps. Flatpak stores it's data in `~/.var`
						- D-Bus
						  collapsed:: true
							- [Install D-Spy on Linux | Flathub](https://flathub.org/apps/org.gnome.dspy)
							-
						- Networking
							- SOCKS5
							  collapsed:: true
								- SSH
									- Setup ssh server at your parents house (raspberry pi or something). Connect to it remotely with the -D flag. Ex:
									- `ssh myuser@parents.ip.address -D 3199`
									- While that connection is open, your local computer is now hosting a socks proxy on localhost / 127.0.0.1 port 3199. If you connect to that proxy in a web browser or otherwise, all your traffic going through that proxy will be encrypted and routed through your parents ip.
									- Now, configuring an application other than a web browser to use that proxy is another story…
									- No password required for the proxy settings in the application, you just have to get the ssh connection running and then host: localhost port: 3199
								- https://hub.docker.com/r/serjs/go-socks5-proxy/
								-
					- [Learning Resources]
					  collapsed:: true
						- Daily Tip: You can browse remote servers using Dolphin and modify files with other KDE applications
						  https://www.reddit.com/r/kde/comments/9er7iv/daily_tip_you_can_browse_remote_servers_using/
						- Daily Tip: Holding Alt and pressing your middle mouse button cycles through windows that are stacked above each other
						  https://www.reddit.com/r/kde/comments/9f2mt0/daily_tip_holding_alt_and_pressing_your_middle/
						- Linux extra security configs
						  collapsed:: true
							- SELinux/AppArmor
							- Secure Boot
							  collapsed:: true
								-
							- SSD/HDD Encryption (like Luks)
							- Firewall (like firewalld)
							- libressl as the system library instead of openssl -- or the ability to set it as the system library -- which e.g. Gentoo allows
							- kernel mitigations (grsec/pax)
							- EVM (extended verification module) or AEM (anti-evil-maid) -- uses TPM so that the owner can know if their system has been tampered with.
							- ********* BIOS 101
								- Set individual passwords for BIOS modification, system boot, boot drive selection and anything else your particular BIOS version allows.
								- Mix it up a little. Also enable your TPM (Trusted Platform Module) chip. When you do this you also
								- need to ‘own’ your TPM so it is not the same chip config as when it left the factory.
								- ********** Flash your BIOS
									- the BIOS is the first thing that runs when you turn on your computer, if you have a virus in your BIOS, there is no antivirus that can remove
									- it, you would need to flash your BIOS and install a new firmware. Make sure the firmware is 100% trustworthy as infected firmware is the most common way to get a BIOS virus.
							- ********* Multiboot/multi system drive with truecrypt
								- http://www.digitalcitizen.life/how-encrypt-your-system-drive-truecrypt-multi-boot-configuration
							- ********* Hidden Partition
								- First OS on 1 partition
								- 2 partition with files + hidden 2nd OS
							- ********* Hidden OS
								- hidden OS as well (or wait til I move onto Linux or til new laptop)
							- Full Disk Encryption
								- Either two-factor (LUKS + LUKS Header on USB https://superuser.com/a/935626)
								- LUKS
								  intralink2:: https://workflowy.com/#/79c9b4b09fdd
								- OR normal VeraCrypt that's TPM-based
								- VeraCrypt FDE
									- Trustworthy, audited
									- Tools > Backup Volume Header >
								- FDE
									- Or setup VeraCrypt
							- ********* https://github.com/lfit/itpol/blob/master/linux-workstation-security.md
							- Proximity Unlock & Lockdown (alternative to locking screen after 1-2 mins inactivity)
								- via Bluetooth
									- Associate mobile via bluetooth with laptop so it pings regualrly and locks laptop when out of range
									- Linux - http://blueproximity.sourceforge.net/
									- However bluetooth is long-range
								- NFC - very near (basically touching laptop)
								- RFID
							- Inbuilt Laptop Hardware
								- Opaque tape over camera]
								- Physically remove inbuilt camera + microphone
							- Change default system DNS servers
							- Reset your boot sector on your hard drive regularly
								- from time to time that would be a good idea as well, because you can get master boot sector viruses
							- Setup firewall
						- KDE setup
							- http://linuxbsdos.com/2015/09/02/kde-5-application-dashboard-a-fullscreen-app-launcher-that-beats-the-competition/
							- https://www.makeuseof.com/tag/kde-plasma-tweaks/
						- https://itsfoss.com/apt-get-linux-guide/
				- # Ecosystem
					- Linux-style portable apps
					  id:: 6313455f-8855-4849-8ac2-8012e198774c
					  collapsed:: true
						- Why
						  collapsed:: true
							- undamental problems with Linux as a desktop operating system and that problem is package availability and package distribution
							- In Linux, packages are distro specific for the most part (it's possible to make one DEB that runs in all various different Debian based systems but that limits you in some ways) but not only that packages are distro version specific.
								- If I create a deb package for Ubuntu 16.04 then that package won't work on any version of Ubuntu. I also have to make a 14.04, 15.04, 15.10, and so on. These are JUST Ubuntu debs. I also need to make one for Debian. Then you need to make RPMs for Fedora 21, 22, 23, etc and those RPMs don't even cover openSUSE.
								- This means if I want to release a new version of an application and not wait on distro maintainers to include it in a repository (which usually takes an absurd amount of time) then I have to provide over 20 packages to cover the majority of Linux distros and still that's not going to be covering everything.
						- Types
							- Snappy
							  id:: 63ad9567-8df0-4f60-ab52-545451251156
							  collapsed:: true
								- Pros/Cons
								  collapsed:: true
									- Cons
										- Proprietary backend
										- Can only connect to one backend at once (ie Snap's proprietary backend only)
										- Some APT packages in the Ubuntu repositories not only install snap as a dependency but also run snap commands as root without your knowledge or consent
										- Linux Mint drops Ubuntu Snap packages - [https://news.ycombinator.com/item?id=23771847](https://news.ycombinator.com/item?id=23771847)
											- >  Applications in this store cannot be patched, or pinned. You can’t audit them, hold them, modify them or even point snap to a different store. You’ve as much empowerment with this as if you were using proprietary software, i.e. none. This is in effect similar to a commercial proprietary solution, but with two major differences: It runs as root, and it installs itself without asking you.
											  From the linked announcement: [https://blog.linuxmint.com/?p=3906](https://blog.linuxmint.com/?p=3906)
										- Assorted
											- Much heavier than native packages also noticeably slower to start.
											- Creates an obtrusive "Snap" directory in your home folder that you cannot change.
											- Clutters df output with a whole bunch of loopback devices.
											- The packaging of all dependencies by each developer, while consistent for execution across different computers, can create security problems for lack of update of these dependencies.
											- Ignores system theme (it seems they have worked around it with GTK themes, but it still needs tweaking afaik).
											- It has a daemon (was that really necessary for a package manager?)
											- Centralized and proprietary back-end.
											- Strong ties to Canonical.
									- {Archive}
										- https://linuxmint-user-guide.readthedocs.io/en/latest/snap.html
								- Snappy package contains all the required files, where .deb packages have dependecies to other packages. The negative side is that snappy is bigger, because it contains all the files. But the big advantage is that you don't get in troubble with other packages and if you remove this package, no other will be affected by missing dependencies.
								- Documentation
									- ## Removing
									  id:: 66a89254-7186-4e5d-9d18-d5579908955f
										- `sudo snap list | awk '!/^Name|^core/ {print $1}' | xargs -n 1 sudo snap remove`
										  Remove existing Snap packages
											- ### Removing Firefox
												- `snap disconnect firefox:host-hunspell`
												- `sudo snap remove firefox`
										- `sudo apt remove --purge snapd* -y && sudo apt-mark hold snapd -y`
										  id:: 63a9adc7-d1e5-409a-9bb2-aee74e4ff843
										  How to remove snapd (daemon)
										- `sudo apt purge plasma-discover-backend-snap`
										  This can otherwise cause Discover to not be able to update packages [[2024-08-08 Thursday]]
									- List all snap packages
									  `snap list`
										- Also see [Install software](https://workflowy.com/#/d139fd463a51)
										  #PC-Linux
									- Replacing Snap packages
										- ((649b140b-1732-4689-9331-10b5b97e5e5e)) package
										  id:: 64e094d0-b154-41be-adcc-f91acbb3d703
											- Maybe try using Linux Mint's Chromium repo? I know they compile a Deb package. Or try Brave
											- There's a repo called Savoury1 for Ubuntu LTS builds.
												- I believe it has Chromium that isn't snap-dependant. I strongly recommend using it if you use the oibaf graphics drivers because oibaf drivers won't support the outdated FFMPEG builds for VAAPI that stock Ubuntu LTS comes with, and Savoury1 does provide an updated FFMPEG build that the oibaf drivers support.
											- [Download `.deb` from Debian](https://packages.debian.org/sid/amd64/chromium/download)
											- [Best answer ](https://askubuntu.com/a/1206502) [[2023-10-05 Thursday]]
											  collapsed:: true
												- ```
												  umask 22
												  ```
													- makes sure that the files I create will be readable by everyone, including the system.
												- `sudo nano /etc/apt/sources.list.d/debian-stable.list`
													- ```
													  deb [signed-by=/usr/share/keyrings/debian-archive-keyring.gpg] [Index of /debian](http://deb.debian.org/debian) stable main
													  deb-src [signed-by=/usr/share/keyrings/debian-archive-keyring.gpg] [Index of /debian](http://deb.debian.org/debian) stable main
													  
													  deb [signed-by=/usr/share/keyrings/debian-archive-keyring.gpg] [Index of /debian-security](http://deb.debian.org/debian-security/) stable-security main
													  deb-src [signed-by=/usr/share/keyrings/debian-archive-keyring.gpg] [Index of /debian-security](http://deb.debian.org/debian-security/) stable-security main
													  
													  deb [signed-by=/usr/share/keyrings/debian-archive-keyring.gpg] [Index of /debian](http://deb.debian.org/debian) stable-updates main
													  deb-src [signed-by=/usr/share/keyrings/debian-archive-keyring.gpg] [Index of /debian](http://deb.debian.org/debian) stable-updates main
													  ```
												- `sudo nano /etc/apt/preferences.d/debian-chromium`
													- ```
													  Explanation: Allow installing chromium from the debian repo.
													  Package: chromium*
													  Pin: origin "*.debian.org"
													  Pin-Priority: 100
													  
													  Explanation: Avoid other packages from the debian repo.
													  Package: *
													  Pin: origin "*.debian.org"
													  Pin-Priority: 1
													  ```
												- `sudo apt update` - check for new packages, should be 0 usually
													- If it's one or two, use ``apt policy package-name` to check where they're from. If it's Debian archives, then there's an error
												- `apt upgrade --simulate`
												- `sudo apt install chromium`
										- Firefox
								- Install Snapcraft
								  collapsed:: true
									- Install snapd (unnecessary if on Ubuntu)
									  https://docs.snapcraft.io/core/install
									- _Unnecessary in 21.10?_
										- Install snapcraft and lxd
										  source:: https://docs.snapcraft.io/build-snaps/get-started-snapcraft
											- Install snapcraft
											  snap install snapcraft --classic
											  snap --version
											- _Setup lxd - default is 6GB_
												- snap install lxd
												- _LXD requires that your user is in the lxd group._
													- sudo groupadd lxd
													- sudo usermod -aG lxd ${USER}
													  sudo usermod -aG lxd boss
													- newgrp lxd
												- Configuration of the LXD defaults can be done via the init option. Typically accepting the default prompts is sufficient to get a working LXD configuration, usable by snapcraft on the same host:
												  lxd init
												- Test that LXD (and the lxc client) are correctly installed by starting a container:
												  lxc launch ubuntu:18.04 test
									- How to uninstall
										- snap list
										- sudo apt purge snapd
									- 1 Backlink
										- See [Install Snapcraft](https://workflowy.com/#/a648cab32d28)
								-
							- [Flatpak](http://flatpak.org)
							  id:: 63a873fd-893d-4ed7-ae5b-e27945e68230
							  collapsed:: true
								- Pros/Cons
								  id:: 65a98a51-6d04-4840-bab1-9e761759869a
									- Pros
										- [Reuses libraries in an efficient way](https://teddit.net/r/linux/comments/n2tt5b/linus_torvalds_shared_libraries_are_not_a_good/gwlqra5/#c)
										- [Can connect to multiple remotes, unlike Snap](https://teddit.net/r/linux/comments/n2tt5b/linus_torvalds_shared_libraries_are_not_a_good/gwmgzw0/#c)
									- Cons
										- Doesn't support non-GUI apps?
										- Some software I choose to install as portable with the binaries and config files all in encrypted storage
											- ((649b1412-793f-4972-b3a0-338c319b3e88))
										- Some apps are buggy or have limitations
										  id:: 671d6a82-75a6-4382-8c60-425cba85ec76
											- ((63134593-906c-43b5-96fe-33dc2c34fda4)) : ((67829245-7660-438a-b181-4b0936de292d))
											- ((65a98a51-b5c3-4329-a1c7-321ce408e6f8))
											- ((63209272-1088-4824-a762-4ac7ded04b0a))
											- ((644c0bb5-76e1-4489-9fa4-22a803fa3c9d))
											- ((649b140b-e8b8-400f-9c44-ce2a5945295d)) : [Google Chrome doesn't have access to gamepad API if in a Flatpak](https://github.com/flathub/org.chromium.Chromium/issues/40#issuecomment-2326573458)
										- [Plugin support is poor](https://github.com/nurupo/vlc-pause-click-plugin?tab=readme-ov-file#flatpak)
										- Some software isn't available in this packaging format
								- GUI - (permissions)mostly done via GNOME Software Centre and KDE Discover
								- Have requested changelogs for
								  id:: 6513c49d-aa60-43c9-bb4e-4e01ed206509
								  collapsed:: true
									- Template
										- Changelogs can be displayed on Flathub and within distro app updaters, all that's needed is an `.appdata`/[.metainfo.xml](https://docs.flatpak.org/en/latest/conventions.html#appdata-files) file. 
										  
										  See these examples of another app's [appdata.xml](https://github.com/flathub/io.github.trigg.discover_overlay/blob/master/io.github.trigg.discover_overlay.appdata.xml), and how their changelog is [displayed on Flathub](https://flathub.org/en-GB/apps/io.github.trigg.discover_overlay).
									- To add:
										- Anki
										- Arianna
										- Dolphin
										- GitKraken
										- Kodi
										- Kontact
										- Mission Center
										- Musicbrainz
										- Slack
										- Steam
										- Postman
										- Prism Launcher
										- Tor browser
										- VLC
										- Zoom
									- [Alexandria](https://github.com/flathub/io.github.btpf.alexandria/issues/3)
									- [AppFlowy](https://github.com/flathub/io.appflowy.AppFlowy/issues/60)
									- [Brave](https://github.com/flathub/com.brave.Browser/issues/446)
									- [Briar](https://github.com/flathub/org.briarproject.Briar/issues/24)
									- [Calibre](https://github.com/flathub/com.calibre_ebook.calibre/issues/192) / [Bug #2037671 “Provide a `.metainfo.xml` file” : Bugs : calibre](https://bugs.launchpad.net/calibre/+bug/2037671)
									  id:: 65a98a51-99d3-4433-a01d-b391f49f6ffb
									- [Chromium](https://github.com/flathub/org.chromium.Chromium/issues/324)
									  id:: 65a98a51-8ba0-4ab6-b053-2654aa622a98
									- [DBeaver Community](https://github.com/flathub/io.dbeaver.DBeaverCommunity/issues/191)
									- [Discord](https://github.com/flathub/com.discordapp.Discord/issues/329)
									- [Discover Overlay](https://github.com/flathub/io.github.trigg.discover_overlay/issues/12)
									- [Element](https://github.com/flathub/im.riot.Riot/issues/408)
									- [Flatseal](https://github.com/flathub/com.github.tchx84.Flatseal/issues/53)
									- [Firefox](https://bugzilla.mozilla.org/show_bug.cgi?id=1855365)
									- ((6313458c-20f9-43f5-be52-44845eb02203))
									- [Geforce Now](https://github.com/flathub/io.github.hmlendea.geforcenow-electron/issues/45)
									- [Kdenlive](https://github.com/flathub/org.kde.kdenlive/issues/282)
									- [Komikku](https://github.com/flathub/info.febvre.Komikku/issues/124)
									- [Librewolf](https://github.com/flathub/io.gitlab.librewolf-community/issues/71)
									- [Librum](https://github.com/flathub/com.librumreader.librum/issues/14)
									- [Lutris](https://github.com/flathub/net.lutris.Lutris/issues/370) ( ((65a98a51-b5c3-4329-a1c7-321ce408e6f8)) )
									- [mpv](https://github.com/flathub/io.mpv.Mpv/issues/273)
									- [Mullvad](https://github.com/flathub/net.mullvad.MullvadBrowser/issues/22)
									- [Obsidian](https://github.com/flathub/md.obsidian.Obsidian/issues/207)
									- [PDF Arranger](https://github.com/flathub/com.github.jeromerobert.pdfarranger/issues/189)
									- [Penpot Desktop](https://github.com/flathub/com.sudovanilla.penpot-desktop/issues/5)
									- [Rider](https://github.com/flathub/com.jetbrains.Rider/issues/80)
									- [Session Desktop](https://github.com/oxen-io/session-desktop/issues/2935)
									- [Signal Desktop](https://github.com/flathub/org.signal.Signal/issues/520)
									- [Spotify](https://github.com/flathub/com.spotify.Client/issues/256)
										- Related: ((64f5d195-048b-4532-86da-5e3fa35b3d2c))
									- [Spotube](https://github.com/flathub/com.github.KRTirtho.Spotube/issues/26)
									- [Stremio](https://github.com/flathub/com.stremio.Stremio/issues/15)
									- [Thunderbird](https://bugzilla.mozilla.org/show_bug.cgi?id=1855365)
									- [Vorta](https://github.com/flathub/com.borgbase.Vorta/issues/140)
									- Resolved
										- [Telegram Desktop](https://github.com/telegramdesktop/tdesktop/issues/26865)
								- # Documentation
									- Installation
									  collapsed:: true
										- _Official installation info_
											- _Install Flatpak_
											  `sudo apt install flatpak`
											- _Install the Software Flatpak plugin_
												- The Flatpak plugin for the Software app makes it possible to install apps without needing the command line. To install, run:
												  `sudo apt install gnome-software-plugin-flatpak -y`
											- Add the Flathub repository
											  `flatpak remote-add --if-not-exists flathub [404 Not Found](https://flathub.org/repo/flathub.flatpakrepo`)
											- Restart your system
										- Flatpak apps in Discover (alongside existing Snaps)
										  `sudo apt install plasma-discover-backend-flatpak -y`
										- Ubuntu
										  https://flatpak.org/setup/Ubuntu/
										- Fedora
											- `sudo dnf install flatpak`
											- Add the gnome-apps repo
												- `wget https://sdk.gnome.org/keys/gnome-sdk.gpg`
												- `$ flatpak remote-add --gpg-import=gnome-sdk.gpg gnome-apps https://sdk.gnome.org/repo-apps/`
											- `flatpak remote-ls gnome-apps --app`
											  List available apps
											- Download the Flathub repo
												- https://flathub.org/repo/flathub.flatpakrepo
											- Or/then go to https://flathub.org/apps
									- Guides
										- [How to sandbox](https://discuss.privacyguides.net/t/sandboxing-applications-on-desktop-linux/27362)
										  id:: 6856fa40-de22-40e0-8f04-c96deb1a9cfe
									- Troubleshooting
										- [Downgrading](https://docs.flatpak.org/en/latest/tips-and-tricks.html#downgrading)
										  id:: 65a98a51-72f2-4e93-81fe-58756b9a9e5c
										  collapsed:: true
											- First you look for the commit you are interested in:
											  ```bash
											  flatpak remote-info --log flathub org.mozilla.Thunderbird
											  ```
												- e.g. 
												  ```bash
												  Commit: 94d0793c4ecb1768aaf5f8eb8f0788171a1ea9ae69df2531b8d2acad488c7af8
												  Subject: Update 0.8.11.tar.gz to 0.8.12 (82fe78af)
												  Date: 2022-12-02 22:29:58 +0000
												  ```
											- Then you deploy the commit:
											  ```bash
											  sudo flatpak update \
											  --commit=fcb0a2ed90321b75b9b4a0fc21911bef2de2ab4e5d36d96031909a28c7e6c10e \
											  org.mozilla.Thunderbird
											  ```
												- Other examples
													- ```bash
													  sudo flatpak update \
													  --commit=8cd562cb3c226348431e3ff8f75d79426c40031579215c319801be533a567b93 \
													  org.mozilla.firefox
													  ```
										- File locations
										  collapsed:: true
											- Objects under `~/.local/share/flatpaks`?
											- Config files under `~/.var/app/`
											- Binaries symlinked from
												- `~/.local/share/flatpak/exports/bin`
												  If installed for current user
												- `/var/lib/flatpak/exports/bin`
												  If installed system-wide
											- `.desktop` files
												- `/var/lib/flatpak/app/com.logseq.Logseq/current/active/files/share/applications` (on ((671b6e25-ba39-4d7d-b20e-1f12303488ca)) )
												- `/var/lib/flatpak/app/com.logseq.Logseq/current/active/export/share/applications`
										- `flatpak upgrade` stuck
											- Instead use `sudo flatpak upgrade`
										- Theming not applying to GTK apps
											- `flatpak install org.gtk.Gtk3theme.Breeze-Dark`
										- System vs user-installed applications
										  id:: 677f9fb3-a825-490a-8a60-4973bb846841
										  collapsed:: true
											- ## System
												- `flatpak list --system`
												- `flatpak install --system com.dec05eba.gpu_screen_recorder`
											- ## User
												- `flatpak list --user`
												- `/usr/bin/flatpak run --branch=stable --arch=x86_64 --command=gpu-screen-recorder-gtk com.dec05eba.gpu_screen_recorder`
											- How to remove `system` remote
												- `sudo flatpak remote-delete --system flathub`
												- `sudo flatpak remote-delete --system --force flathub` will remove them without removing the runtimes or applications
													- If you want to ensure that all applications and runtimes from the remote are uninstalled before removing the remote, you can uninstall them first: `flatpak uninstall --system --delete-data --all`
									- ((65a98a51-9dbe-47fd-a0c1-fcef13cdb1ef))
								- Flathub
									- [Forum](https://discourse.flathub.org/)
									- [GitHub](https://github.com/flathub-infra/website)
								- {Archive}
									- Removed apps
							- [AppImage](https://appimage.org/)
							  id:: 63a9adc7-31c0-4b63-b01f-8b73185dadbf
							  collapsed:: true
								- Pros/Cons
									- Pros
										- Better suited than Flatpaks if it requires good system integration (as Flatpak has limited APIs still)
									- Cons
										-
									- Unclear
									- Comparisons
								- Get AppImages
									- https://appimage.github.io/apps/
									- https://github.com/AppImage/AppImageUpdate
									- ....
									- https://appimage.github.io/LibreOfficeFresh/
								- Cons
									- Ubuntu AppArmor issue
										- Run with `--no-sandbox`
										- [Logseq on Ubuntu 24.04 · Issue #11240 · logseq/logseq · GitHub](https://github.com/logseq/logseq/issues/11240#issuecomment-2437725097)
								- SOPs
									- [[2025-05-27 Tuesday]] Kubuntu 25.04 and earlier `The SUID sandbox helper binary was found, but is not configured correctly`
									  id:: 6835dd34-0955-461f-9135-2726f33051d7
									  collapsed:: true
										- [Solution](https://askubuntu.com.stackexchange.com/questions/1512287/obsidian-appimage-the-suid-sandbox-helper-binary-was-found-but-is-not-configu)
											- `sudo nano /etc/apparmor.d/freetubeappimage`
												- ```
												  # This profile allows everything and only exists to give the
												  # application a name instead of having the label "unconfined"
												  
												  abi <abi/4.0>,
												  include <tunables/global>
												  
												  profile freetubeappimage /home/boss/AppImages/freetube.appimage flags=(default_allow) {
												    userns,
												  
												    # Site-specific additions and overrides. See local/README for details.
												    include if exists <local/freetubeappimage>
												  }
												  ```
											- `sudo systemctl reload apparmor.service`
											- Troubleshooting
												- `systemctl status apparmor.service`
									- How to make executable
										- e.g.
											- `sudo chmod +x KeePassXC.AppImage`
								- [Using portable mode](https://docs.appimage.org/user-guide/portable-mode.html)
								  id:: 6655da8b-ada1-41c0-922c-9d751ba4760a
								  collapsed:: true
									- If there is a directory with the same name as the AppImage plus `.home`, then `$HOME` will automatically be set to it before executing the payload application
									- If there is a directory with the same name as the AppImage plus `.config`, then `$XDG_CONFIG_HOME` will automatically be set to it before executing the payload application
									- Example
										- ```bash
										  # Download Leafpad AppImage and make it executable
										  $ wget -c "https://bintray.com/probono/AppImages/download_file?file_path=Leafpad-0.8.18.1.glibc2.4-x86_64.AppImage" -O Leafpad-0.8.18.1.glibc2.4-x86_64.AppImage
										  $ chmod a+x Leafpad-0.8.18.1.glibc2.4-x86_64.AppImage
										  
										  # Create a directory with the same name as the AppImage plus the ".config" extension
										  # in the same directory as the AppImage
										  $ mkdir Leafpad-0.8.18.1.glibc2.4-x86_64.AppImage.config
										  
										  # Run Leafpad, change some setting (e.g., change the default font size) then close Leafpad
										  $ ./Leafpad-0.8.18.1.glibc2.4-x86_64.AppImage
										  
										  # Now, check where the settings were written:
										  $ find Leafpad-0.8.18.1.glibc2.4-x86_64.AppImage.config
										  (...)
										  Leafpad-0.8.18.1.glibc2.4-x86_64.AppImage.config/leafpad/leafpadrc
										  ```
								- [GearLever](https://github.com/mijorus/gearlever)
									- [Install Gear Lever on Linux | Flathub](https://flathub.org/apps/details/it.mijorus.gearlever)
									- Can handle updates for AppImages (like ((644c0acd-59dd-4065-a2e9-41351725caf8)) )
									- ### My AppImages
									  [[2025-02-07 Friday]]
										- ((649b1407-36a5-447b-ba05-aa7a96f80a1b))
										- Nexus Mods App
										- Cursor
										- Heynote
										- ((677d753b-7f2e-489f-bd87-305ae1afc510))
										- ((676fd6a4-ab29-4ad9-b7c3-7dac4b47f0f4))
										- Ledger Live
										- [Chatbox](https://github.com/chatboxai/chatbox)
										  id:: 67a8e0d5-c7e0-43e9-af3b-b728b37bb220
											- [[Feature] Customisable keybinding for show/hide to system tray · Issue #2286 · chatboxai/chatbox · GitHub](https://github.com/chatboxai/chatbox/issues/2286)
										- ActivityWatch
										- Redact
										- Spacedrive
										- Streamlink Twitch GUI
										- TagSpaces
								- Troubleshooting
									- [[2024-05-23 Thursday]] Logseq AppImage wouldn't launch after upgrading to Kubuntu 24.04
									  collapsed:: true
										- Check this setting using `sysctl kernel.unprivileged_userns_clone`
											- To enable it (until next reboot)
												- `sudo sysctl -w kernel.unprivileged_userns_clone=1`
										- [source] [Appimage cant be run due to permissions · Issue #2246 · laurent22/joplin · GitHub](https://github.com/laurent22/joplin/issues/2246#issuecomment-577315584)
											- ```bash
											  cd /home/boss/AppImages
											  ./gearlever_logseq_bd9783.appimage --appimage-extract
											  cd squashfs-root
											  sudo chown root chrome-sandbox
											  sudo chmod 4755 chrome-sandbox
											  ```
											- To repack:
												- ```bash
												  cd /home/boss/AppImages
												  # (if it's not downloaded already, get the AppImage of appimagetool from https://github.com/AppImage/AppImageKit/releases)
												  ARCH=x86_64 ./appimagetool.appimage squashfs-root
												  ```
										- Still didn't work, had to use:
											- `screen -d -m /home/boss/AppImages/logseq.appimage --no-sandbox`
						- Comparison between others
						  collapsed:: true
							- Best comparison
							  https://github.com/AppImage/AppImageKit/wiki/Similar-projects#comparison
							- So there are a couple of different projects trying to be distro-agnostic/sandboxed/multi-version package managers:
								- Snappy
								- FlatPak
								- AppImage
								- Nix
							- comparison
								- Snappy is an Ubuntu/Canonical project and FlatPak is a Fedora/RedHat/FreeDesktop project. Snappy and FlatPak are remarkably similar and kind of mirror the DEB/RPM spit. Nix and AppImage are independent.
									- AppImages resemble macOS's app bundles in that they can be run directly without installation. Snappy, FlatPak, and Nix need to install to a root directory, /snap, /var/lib/flatpak/, and /nix respectively. FlatPak and Snappy need a runtime daemon but Nix and AppImage don't.
									- AppImage, Snappy, and FlatPak include all of the dependencies in one package. Nix packages just include hash names and install as needed.
								- So to say, ordered according to difficulty.
									- AppImage: Relatively simple - click, runs.
									- Snap: You have to install something, you have to login somehow to Ubuntu One, but then you can install something, runs.
									- Flatpak: I need to get Flatpak first, then I have to add the repositories there, then I have to get the GPG keys, then I have to download Runtimes, and then I can somehow get the Flats out of there, install and start the programs.
							- Flatpak
								- Pros/Cons
									- Pros
										- Sandboxing, better dependencies system, not controlled by canonical (Snappy), Install multiple versions of the same app
										- What makes flatpak different from both Snapcraft and AppImage is that is brings shared, constantly updated runtimes (e.g. the kind of libraries that make Steam a mess to install on distros that are not Ubuntu) into the picture. Unlike AppImage, libraries/runtimes do not need to be bundled, reducing file size of apps and providing a much cleaner, auto updating experience. (Also, it's integrated into gnome-software already...)
										- Sandboxing custom, with SELinux support.
									- Cons
										- There is no central repo. For every new app from a different developer, you have to add a new repo.
										- Some Flatpak apps have issues
											- Chromium and Brave browser Flatpaks don't come with the flags set to allow hardware video acceleration
												- Related:
													- ((635037e6-35b4-4a36-bf5f-8fe23cce6f47))
													- ((635037e8-67ca-44ac-b04a-e3928ed1d146))
													- ((63567ca0-a57f-4976-9104-2d8ecd6ca428))
											- Librewolf as a Flatpak when updating overwrites `user-overrides.js` so you can customise the Arkenfox settings
											-
								- Documentation
									- App updates are done automatically by the flatpak updater service triggered 10m after boot
									  source:: [https://www.linux.org/threads/do-flatpak-apps-get-updated-automatically-or-do-i-have-to-update-them-manually.30429/post-100206](https://www.linux.org/threads/do-flatpak-apps-get-updated-automatically-or-do-i-have-to-update-them-manually.30429/post-100206)
									- Updating Flatpak apps can be triggered manually via `flatpak update`
									  source:: [https://docs.flatpak.org/en/latest/using-flatpak.html#updating](https://docs.flatpak.org/en/latest/using-flatpak.html#updating)
									- `flatpak remotes`
									  See what, if any, remotes you have configured
									- `flatpak list`
									  Check what Flatpaks you have installed
						- ((635036c9-08c9-47d6-ad33-98c1fc61a0dd)) : ((6312a079-ed4b-4377-ba3a-4edce7119230))
						- ((63a88eb7-4bbe-4ecc-a7a3-8293dba06bb7))
					- Package Managers
						- Using apt-cache commands to search for packages
						  collapsed:: true
						  `$ apt-cache search <search term>`
							- You don’t need to know the exact name of the package. It searches in package name and their short description and shows result based on that.
							- If you just want to search the packages with specific package names, you can use the command below:
							  apt-cache pkgnames <search_term>
								- This gives you the list of all the packages starting with your search term.
							- Once you know the exact package name, you can get more information about it such as version, dependencies etc by using the command below:
							  apt-cache showpkg <package_name>
					- Distribution-Agnostic Package Managers
					  collapsed:: true
						- ((63a873fd-893d-4ed7-ae5b-e27945e68230))
						- ((63a9adc7-f569-4cfb-833e-aedf16f75606))
						- [Homebrew](https://brew.sh/)
						- ((63a9adc7-c031-4dc6-a162-c91f04da953c))
				- Linux-on-ARM
				  id:: 63577332-55c8-4f3e-af71-3dddba173c4a
				  collapsed:: true
					- Aspects
						- [Asahi Linux](https://asahilinux.org/)
						  id:: 65a98a51-37bd-4253-b4ab-8437dc26f765
						  for ((67cae86d-70be-4444-9267-e537acdd241e))
							- [Feature Support · AsahiLinux/docs Wiki · GitHub](https://github.com/AsahiLinux/docs/wiki/Feature-Support)
								- [[2024-11-25 Monday]] Lacks Thunderbolt/USB4, USB-C Displays, Microphone, Touch ID
									- Also it's ((670be101-bc11-4dd5-a571-13eb92d8edf3)) is alpha
									- Only supports M1 and M2 series currently
							- ((670be101-bc11-4dd5-a571-13eb92d8edf3)) implementation
							  id:: 677d752a-e2a1-4528-8573-0f4a52071146
								- [Running x86/x86-64 applications on Fedora Asahi Remix :: Fedora Docs](https://docs.fedoraproject.org/en-US/fedora-asahi-remix/x86-support)
								- Uses ((670be21c-1864-4317-a12a-b912c738e737))
								- [muvm](https://github.com/AsahiLinux/muvm)
							- Related: ((67cae906-3d56-4c08-9cd5-3d28b32f0e43))
						- [Mac Rosetta](https://en.wikipedia.org/wiki/Rosetta_(software)) 
						  id:: 65a98a51-83ea-4050-b57f-79da79369760
						  binary translator/emulator which allows running x86 applications on ARM
							- in 2021 virtualisation is supported, but only ARM virtual machines. x86 emulation not yet
						- Electron and similar apps don't work usually
							- Electron and apps built with it are missing from most ARM64 Linux distributions.
							  
							  Once you've built Electron (or downloaded their binaries), many of the builds fail because they download something that requires x86_64, and then you get to troubleshoot that.
							  
							  Flathub doesn't have aarch64 builds of most of these apps either, so I'm assuming it is not just me having issues.
							  
							  So much for cross platform. It is doable for the open source apps if you want to get your hands dirty though.
							  
							  It did motivate me to look for non-Electron replacements (to Electron apps, not Slack and Spotify specifically), so I've got that going for me.
				- [Learning Resources]
				  collapsed:: true
					- YouTube channels
						- Learning Linux
							- [Learn Linux TV - YouTube](https://www.youtube.com/c/LearnLinuxtv)
							- [Veronica Explains - YouTube](https://www.youtube.com/@VeronicaExplains)
							- [Michael Tunnell - YouTube](https://m.youtube.com/@michael_tunnell/videos)
							- [Practical IT with Jeremy Leik - YouTube](https://youtube.com/@practical-it?si=a355_wBS3HFJIiNq)
							- Maple Circuit
							-
				- Related: ((649b13cf-a825-48f5-ae83-b47b6ad6bff9))
			- ## Distributions
			  id:: 65a98a51-de4f-447e-86bb-06f2f7f5d7e6
				- ### Priority
					- Meta
						- ((62e11d87-874f-4112-8bd5-a0a8f6651248)) : ((65a98a51-494b-4c54-9f8a-bde6c0d0eea1))
					- ((671b6e25-ba39-4d7d-b20e-1f12303488ca))
					- ((67827678-0a4e-43e2-81bd-f21f6609b8ee))
					- ((671d6a81-1dc1-4cce-934b-8e8786d9bcef))
					- ((671d6a81-feca-42b1-b68c-30c58d4c6f84))
					- ((678269ef-8192-4e6a-99f5-18f2707c0072))
					- ((67826b0d-8952-4cd4-8281-7c2dcae1cf7a)) : ((67c074c4-a262-43f4-a8a8-216c39d62680))
					- ((63a9adc7-fc79-4fa3-8ca5-925a17291c26))
				- ### ((65a98a51-38a0-4772-9fbb-0fffadc84dfd))-based
					- [Debian](https://www.debian.org/)
					  id:: 65a98a51-38a0-4772-9fbb-0fffadc84dfd
					  collapsed:: true
						- Pros/Cons
							- Unclear
								- [systemd](https://systemd.io/)
								  id:: 6550215b-10a2-4ffa-96bd-ce4dd905c403
								  collapsed:: true
									- Pros/Cons
										- Pros
											- [[Reddit - Dive into anything](https://reddit.com/r/archlinux/comments/4lzxs3/why_did_archlinux_embrace_systemd/d3rhxlc?context=3](https://reddit.com/r/archlinux/comments/4lzxs3/why_did_archlinux_embrace_systemd/d3rhxlc?context=3))
											-
										- Cons
											- https://www.without-systemd.org/wiki/index_php/Arguments_against_systemd/
											-
										- Unclear
										- Comparisons
									- ![image.png](../assets/image_1703085193275_0.png)
									- [Linux in 2020: 27.8 million lines of code in the kernel, 1.3 million in systemd - Linux.com](https://www.linux.com/news/linux-in-2020-27-8-million-lines-of-code-in-the-kernel-1-3-million-in-systemd/)
									- ((6581601b-a5cd-4d5e-83e4-77dd49750f3c))
						- `apt` package manager
							- If `sudo apt install something` isn't working, then `sudo apt update` first because the cache clears after some time and can cause installs to fail
					- [Ubuntu](https://ubuntu.com/)
					  id:: 65a98a51-575b-460b-8931-8850224f04ed
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Cons
								- Not suitable for long-term support
								  [https://www.nitrokey.com/news/2021/nextbox-why-we-decided-and-against-ubuntu-core](https://www.nitrokey.com/news/2021/nextbox-why-we-decided-and-against-ubuntu-core)
						- Tech stack
							- GNOME
							  collapsed:: true
								- Cons
									- User and developer hostile frequently
									  [https://news.ycombinator.com/item?id=27075304](https://news.ycombinator.com/item?id=27075304)
							- See Snappy
						- Communities
							- [Ask Ubuntu](https://askubuntu.com/)
							  id:: 6651af6c-e028-4246-8e20-f3b79ab53fdf
							- [Bugs : Ubuntu](https://bugs.launchpad.net/ubuntu/)
							  id:: 6651b395-0abb-4c45-826c-ab572b3807b5
							  collapsed:: true
								- How to report a bug
									- `ubuntu-bug buggy-package-name` then click `Send` to open a web browser window which includes metadata about your system version info
									- [How to manually file a bug](https://bugs.launchpad.net/ubuntu/+filebug/?no-redirect), without using `ubuntu-bug`
						- ((65a98a51-575b-460b-8931-8850224f04ed))-based
							- _Ubuntu official flavours_
								- [Kubuntu](https://kubuntu.org/)
								  id:: 62e11d87-874f-4112-8bd5-a0a8f6651248
								  collapsed:: true
								  Windows-like
									- Pros/Cons
									  id:: 65a98a51-494b-4c54-9f8a-bde6c0d0eea1
									  collapsed:: true
										- Pros
											- Ubuntu base so high software compatibility, big community
											- ((65f58f8e-1860-4087-b0f5-a9ef34dbb9b7)) is light and user friendly compared to GNOME
										- Cons
										  id:: 65a98a51-6890-4b8c-8f5d-2b7a7ab0d3b0
											- Issues
												- [[2025-10-30 Thursday]] [Ansible doesn't have support for sudo-rs yet](https://github.com/ansible/ansible/issues/85837#issuecomment-3397154415) - used `sudo update-alternatives --config sudo` to change from 0 to 1
													- ```
													    Selection    Path                     Priority   Status
													  ------------------------------------------------------------
													    0            /usr/lib/cargo/bin/sudo   50        auto mode
													  * 1            /usr/bin/sudo.ws          40        manual mode
													    2            /usr/lib/cargo/bin/sudo   50        manual mode
													  ```
												- _Lacks_
													- [Ability to set default drag-and-drop behaviour for Dolphin](https://bugs.kde.org/show_bug.cgi?id=154804#c31)
											- Has user hostile stuff
												- Snap instead of Flatpak
											- proposed by PrivacyGuides as better because Ubuntu is harmful with initiatives like Snap, plus they're slow to integrate new software e.g. Wayland, Pipewire
											- Linux touchpad like a Macbook
											  collapsed:: true
												- Tracked via Notion
												- Initiative repo
												  https://gitlab.freedesktop.org/wbharding/libinput
												- Text updates (subscribe)
												  collapsed:: true
												  [[Page not found – Relentless Simplicity](https://bill.harding.blog/](https://bill.harding.blog/))
													- Dec 2021 update
													  [https://www.gitclear.com/blog/linux_touchpad_update_december_2021](https://www.gitclear.com/blog/linux_touchpad_update_december_2021)
														- Milestones
															- Touchpad gesture implementation in X server has been released in version 21.1
															- Wayland touchpad gesture implementation in Qt widget framework has been released in version 6.2.0
															- X11 touchpad gesture implementation in Gtk widget framework has been released in version 4.5.0
															- X11 touchpad gesture implementation it Qt widget framework will be released in version 6.3.0 (March 2022)
															- Touchpad gesture implementation for XWayland will be released in version 22.1 (early 2022)
														- So let's look into how this translates into touchpad gesture support across the Linux ecosystem...
															- Low-level input driver. Works, handled by libinput ✅
															- Display server. Works on X Server ✅, Wayland ✅, Mutter ✅ and most other Wayland display servers ✅.
															- Widget toolkits. Works on Gtk ✅, Qt ✅. Does not work on other less known widget toolkits ❌.
															- Applications. Works on Firefox ✅, GIMP ✅, GNOME Image Viewer ✅ , does not work on many other applications ❌❌❌...❌.
														- Next step: application support
															- Current support
																- [Firefox (77 votes)]()
																- ✅ Pinch zoom works already, on X server MOZ_USE_XINPUT2=1 environment variable needs to be enabled (some distributions enable this by default).
																- [Mutter (30 votes)]()
																- ✅ Works on Wayland, ❌ does not work on X server. We became aware of [plans](https://gitlab.gnome.org/GNOME/mutter/-/issues/1989) to migrate Mutter to GTK4 which now supports touchpad gestures on X server too. Therefore we have decided to not work on improving mutter as our contribution is likely to be thrown away soon.
																- [Kwin/Plasma (26 votes) 🔥]()
																- We will start investigating gesture support on this compositor.
																- [Chrome/Chromium (22 votes) 🔥]()
																- We will start investigating what's required to implement touchpad gesture functionality in this browser.
																- [Gimp (17 votes) 🔥]()
																- We have implemented canvas zooming ✅, we will work on canvas rotation and other places where gestures may be useful.
																- [Evince/gnome document viewer (12 votes)]()
																- ✅ Works fine already.
															- Future applications
																- The application popularity list - notable being KWin/Plasma, Dolphin, Thunderbird, Brave, VsCode, Kate
																	- The list below shows the top 30 applications from the poll we've organized in the October 2020 status update. We mention if an application uses a custom or no GUI toolkit instead of just Gtk or Qt because this means that the application would require significantly more effort.
																	- Firefox, 77 votes
																	- Mutter, 30 votes
																	- KWin/Plasma, 26 votes
																	- chrome/chromium, 22 votes
																	- Gimp, 17 votes
																	- Evince/gnome document viewer, 12 votes
																	- Sway, 10 votes, no toolkit
																	- Libreoffice, 9 votes, custom toolkit
																	- Inkscape, 7 votes
																	- Nautilus, 6 votes
																	- Okular, 6 votes
																	- Blender, 5 votes, custom toolkit
																	- Alacritty, 4 votes, custom toolkit
																	- Digikam, 4 votes
																	- Dolphin, 4 votes
																	- Emacs, 4 votes
																	- Eog/gnome image viewer, 4 votes
																	- Enome terminal, 4 votes
																	- Krita, 4 votes
																	- Thunderbird , 4 votes
																	- Vscode, 4 votes
																	- Compiz, 3 votes
																	- Qutebrowser, 3 votes
																	- Brave, 2 votes
																	- Darktabl, 2 votes
																	- Gnome-maps, 2 votes
																	- Gwenview, 2 votes
																	- I3wm, 2 votes, no toolkit
																	- Kate, 2 votes
																	- Mpv, 2 votes, custom toolkit
																	- The rest of applications got a total of 34 votes.
															- Future feature: better acceleration curve
																- _Related: _
																	- syngesture
																		- I wrote a (userland) general purpose and driver/hardware-agnostic multitouch daemon w/ gesture support for Linux that works with the existing input stack (i.e. doesn’t require switching to libinputy but also supports it), if anyone is interested:
																		- [https://neosmart.net/blog/2020/multi-touch-gestures-on-linux/](https://neosmart.net/blog/2020/multi-touch-gestures-on-linux/)
																		- [https://github.com/mqudsi/syngesture](https://github.com/mqudsi/syngesture)
																		- The biggest benefit is that you can use drivers with actually correct acceleration curves like xf86-input-synaptics (if you’re on X11) instead of the offensively bad, NIH reimplementation that ships with libinput.
																		- 1 Backlink
																			- _Related:_ [syngesture](https://workflowy.com/#/83761174f62b)
												- Discussions
													- [https://news.ycombinator.com/item?id=19485178](https://news.ycombinator.com/item?id=19485178)
												- _Related:_ [Increase touchpad acceleration](https://workflowy.com/#/7ec06d086926)
											- Related: ((65f58f8e-1860-4087-b0f5-a9ef34dbb9b7)) : ((68d1c13e-0046-4baa-9c51-574091b58365))
										- Comparisons
											- ((62e11d87-874f-4112-8bd5-a0a8f6651248)) vs ((67827678-0a4e-43e2-81bd-f21f6609b8ee))
												- For ((62e11d87-874f-4112-8bd5-a0a8f6651248))
												- For ((67827678-0a4e-43e2-81bd-f21f6609b8ee))
													- [[2025-02-26 Wednesday]] I can't seem to get rootless Podman to allow use of ((63a9adc7-c031-4dc6-a162-c91f04da953c))
													- ((63c2a256-30fe-4cd5-a827-2f269b98b0c0)) : ((65a98a50-154c-4108-a916-a64b699d639f))
													- ((65a98a50-6f25-453a-b065-d694201ff01d)) : ((65a98a50-67d9-4877-aafe-a830118d8233))
												- Similarities
													- ((65f58f8e-1860-4087-b0f5-a9ef34dbb9b7))
												- Differences
										- Alternative OS
											- [NixOS](https://workflowy.com/#/362a9bd963f1) has declarative configuration, which makes backup and recovery much easier
											- [Fedora (Immutable) Silverblue/Kinoite](https://workflowy.com/#/32f4ecd6b591) has similar advantages to NixOS
											- Immutable distros like ((671b6e25-ba39-4d7d-b20e-1f12303488ca)), NixOS
												- [https://www.privacyguides.org/linux-desktop/#immutable-distributions](https://www.privacyguides.org/linux-desktop/#immutable-distributions)
												- Nix and Guix
											- Rolling release?
											  [https://www.privacyguides.org/linux-desktop/overview/#release-cycle](https://www.privacyguides.org/linux-desktop/overview/#release-cycle)
												- Pros
												- Cons
													- Distros like Fedora and Ubuntu swap over to newer technologies like Wayland and Pipewire when the time is right, otherwise you have to research which packages to get? then again KDE manages part of this
												- Fedora has a semi-rolling release cycle. While some packages like [GNOME](https://www.gnome.org/) are frozen until the next Fedora release, most packages (including the kernel) are updated frequently throughout the lifespan of the release. Each Fedora release is supported for one year, with a new version released every 6 months.
											- [https://www.privacyguides.org/linux-desktop/overview/#traditional-vs-atomic-updates](https://www.privacyguides.org/linux-desktop/overview/#traditional-vs-atomic-updates)
									- Communities
										- [Kubuntu Forums](https://www.kubuntuforums.net/forum.php)
										- [/r/Kubuntu](https://www.reddit.com/r/Kubuntu/)
										- ((6651af13-7fcb-4ad8-a9fe-f5324d6a70a0))
										- ((6651af6c-e028-4246-8e20-f3b79ab53fdf))
										- [Kubuntu/Bugs](https://wiki.ubuntu.com/Kubuntu/Bugs) : ((6651b395-0abb-4c45-826c-ab572b3807b5))
									- Features expected in next version [[2024-11-26 Tuesday]]
										- [Hakuna - play/pause by clicking on video player itself](https://invent.kde.org/multimedia/haruna/-/merge_requests/49)
										- [Plasma - clone panel](https://invent.kde.org/plasma/plasma-workspace/-/merge_requests/4623#note_1080445) (to copy bottom bar to multiple monitors)
									- Desktop environment
										- [KDE](https://kde.org/)
										  id:: 65f58f8e-1860-4087-b0f5-a9ef34dbb9b7
										  collapsed:: true
											- Pros/Cons
												- Pros
													-
												- Cons
												  id:: 68d1c13e-0046-4baa-9c51-574091b58365
													- Few ((65a98a51-de4f-447e-86bb-06f2f7f5d7e6)) support it. ((671d6a81-1dc1-4cce-934b-8e8786d9bcef)) is one upcoming one in 2025
													- Slow bug fixing rate
														- Existing bugs
															- ((6836b323-5e97-4f77-b34b-be5b45202c77))
															- [509705 – Play/pause button on bluetooth headphones doesn't affect the expected app](https://bugs.kde.org/show_bug.cgi?id=509705)
															- [510752 – Screen locking unaffected by power mode](https://bugs.kde.org/show_bug.cgi?id=510752)
													- Related: Kubuntu : ((65a98a51-6890-4b8c-8f5d-2b7a7ab0d3b0))
												- Unclear
													- Upcoming changes
														- 6.6
															- [Spectable gains OCR](https://blogs.kde.org/2025/11/15/this-week-in-plasma-ocr-in-spectacle-and-many-ui-improvements/), allows deprecating Normcap
												- Comparisons
											- _Initiatives_
												- [Privacy software (much of current Q1 2019 focus on improving KMail)](https://phabricator.kde.org/T7050)
												- [Usability and Productivity](https://community.kde.org/Goals/Usability_%26_Productivity)
											- Communities
												- [KDE Forum](https://forum.kde.org/)
												  id:: 6651af13-7fcb-4ad8-a9fe-f5324d6a70a0
												- [KDE Bugtracking System Main Page](https://bugs.kde.org/)
												- [Invent](https://invent.kde.org/explore/groups?sort=name_asc)
											- Software
												- ((63a9ade4-acd5-44f9-9166-2c1393865f7a))
												- KAlarm
												  collapsed:: true
													- Fri, Jan 22, 2021 test - can't create an 1:00 countdown timer and have it be recurrable
												- ((651d714a-c80a-4289-a919-478910c779da))
												- [Plasma Vault](https://invent.kde.org/plasma/plasma-vault)
												  id:: 670e4c5e-a0d2-4775-b62f-be7d0c3e32b8
												  collapsed:: true
													- [There are two CLI-only commands that the Vault supports that were introduced for nice integration with](https://cukic.co/2018/04/14/plasma-vault-with-kde-connect-and-more/) ((63a9ade4-acd5-44f9-9166-2c1393865f7a))
														- ```
														  qdbus org.kde.kded5 /modules/plasmavault closeAllVaults
														  qdbus org.kde.kded5 /modules/plasmavault forceCloseAllVaults
														  qdbus org.kde.kded5 /modules/plasmavault closeVault
														  qdbus org.kde.kded5 /modules/plasmavault forceCloseVault
														  ```
													- [Thumbnails aren't stored. Some argue it should be stored in HOME, some in the vault itself](https://bugs.kde.org/show_bug.cgi?id=411919)
													  id:: 670e5581-5ed5-4de8-b69c-890b233ac0f7
														- [494805 – Previews not being displayed in Plasma Vaults - it's now being wrongly controlled by the "Remote storage" option](https://bugs.kde.org/show_bug.cgi?id=494805)
														  id:: 67118786-74a5-4abc-8db3-2380dfce2e47
														- Workaround: Configure Dolphin > Previews > Remote Storage > change from 10MB to 10000MB
												- [Spectacle](https://apps.kde.org/en-gb/spectacle/)
												  id:: 680a0c08-1869-4290-8c40-e86c21d5f579
												  collapsed:: true
													- Keybindings
													  id:: 680a0ba5-a9a2-4ea0-b529-7ff1ef55769f
														- `Meta + PrintScreen` = Capture Active Window
														  collapsed:: true
														- `SHIFT + PrintScreen` = Capture Entire Desktop
														- `SHIFT + Meta + S`/`PrintScreen` = [Open Spectacle](https://bugs.kde.org/show_bug.cgi?id=447550)
														- `Meta + ALT + R` = Record Screen (Spectacle)
														- `CTRL + Meta + R` = Record Window (Spectacle)
												- New changes
												  collapsed:: true
													- [[2025-03-29 Saturday]] You can now also use Meta+Tab and Meta+Shift+Tab to switch between windows, in addition to the current shortcuts. This supports our push to have all global actions include the Meta key for at least one of their shortcuts. (Vlad Zahorodnii, [link](https://invent.kde.org/plasma/kwin/-/merge_requests/6964))
											- Associated OS
												- ((62e11d87-874f-4112-8bd5-a0a8f6651248))
												- ((6735f955-d80b-43f6-9bcb-648c61d7920c))
												- ((65a98a50-43eb-4865-b8d4-3b9ba7b7f6e0))
												- ((671b6e25-ba39-4d7d-b20e-1f12303488ca))
												- ((67827678-0a4e-43e2-81bd-f21f6609b8ee))
												- ((65a98a50-68e7-4c00-8f07-2b3a7ffdbcf9)) Tumbleweed
											- Documentation
												- ((6347106c-d3b8-45fa-af5d-9593dcfe427f))
												- How to emulate KDE Neon (getting latest KDE)
												  collapsed:: true
													- On Kubuntu 18.04 LTS? Good news: you will be able to upgrade to Plasma 5.13 shortly after it is released by adding the Kubuntu Backports PPA to your software sources.
													- This personal package archive contains the latest release of the KDE Plasma desktop, KDE Frameworks and select KDE apps.
													- sudo add-apt-repository ppa:kubuntu-ppa/backports
													- sudo apt update && sudo apt full-upgrade -y
													- Do keep in mind that using this PPA on an LTS release comes with caveats.
													- Although Kubuntu developers maintain the PPA the packages in this PPA are not supported in the same manner as packages in the repo. New releases of Plasma are tested prior to upload but may introduce bugs.
											- Troubleshooting
											  id:: 63a9adc7-b38b-4994-b83f-439b1c2217e3
												- [[2023-07-01 Saturday]] Needed to reset KDE's display monitor settings for my Deux external monitor
												  collapsed:: true
													- It was trying to set it to duplicate screens each time on boot, and I wasn't able to arrange the screens using the Display Configuration setting
													- [How to reset displays (monitors) settings for KDE Plasma and GNOME | Just Some Techie Notes!](https://techienotes.blog/2020/03/24/how-to-reset-display-settings-for-kde-plasma/)
													  collapsed:: true
														- ```
														  rm -rf .local/share/kscreen
														  ```
												- [[2022-10-22 Saturday]] Unable to upgrade because `/boot` partition didn't have enough free space
												  collapsed:: true
													- Show how much space `/boot` partition has
													  ```bash
													  ncdu /boot
													  ```
													- Check what the current kernel I'm using
													  ```bash
													  uname -r
													  ```
													- Open Muon Package Manager, search for "linux-image" and remove some of the kernels. Keep 3 ideally
												- Plasmashell crashing on login, and when browsing Application Launcher
												  collapsed:: true
													- Reported here
													  [https://bugs.kde.org/show_bug.cgi?id=455313](https://bugs.kde.org/show_bug.cgi?id=455313)
													-
												- Upgrading to next version had an error which broke the install (April 2022)
												  collapsed:: true
													- See [Update to Kubuntu 22.04 in order to have access to latest scrcpy package which is compatible with Android 12](https://workflowy.com/#/9dadc3ee8721)
													- ((635037c3-6032-4f23-9ba6-288274d6e473))
													- Issue
													  collapsed:: true
														- `sudo dpkg --configure -a` error
														  boss@boss-XPS:~$ sudo dpkg --configure -a
														  Setting up initramfs-tools (0.140ubuntu13) ...
														  update-initramfs: deferring update (trigger activated)
														  Setting up linux-firmware (20220329.git681281e4-0ubuntu1) ...
														  update-initramfs: Generating /boot/initrd.img-5.13.0-40-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.13.0-40-generic with 1.
														  dpkg: error processing package linux-firmware (--configure):
														   installed linux-firmware package post-installation script subprocess returned error exit status 1
														  Setting up linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  dpkg: dependency problems prevent configuration of linux-image-generic:
														   linux-image-generic depends on linux-firmware; however:
														    Package linux-firmware is not configured yet.
														  
														  dpkg: error processing package linux-image-generic (--configure):
														   dependency problems - leaving unconfigured
														  dpkg: dependency problems prevent configuration of linux-generic:
														   linux-generic depends on linux-image-generic (= 5.15.0.27.30); however:
														    Package linux-image-generic is not configured yet.
														  
														  dpkg: error processing package linux-generic (--configure):
														   dependency problems - leaving unconfigured
														  dpkg: dependency problems prevent configuration of wireguard:
														   wireguard depends on wireguard-dkms (>= 0.0.20200121-2) | wireguard-modules (>= 0.0.20191219); however:
														    Package wireguard-dkms is not installed.
														    Package wireguard-modules is not installed.
														    Package linux-image-generic which provides wireguard-modules is not configured yet.
														  
														  dpkg: error processing package wireguard (--configure):
														   dependency problems - leaving unconfigured
														  Processing triggers for initramfs-tools (0.140ubuntu13) ...
														  update-initramfs: Generating /boot/initrd.img-5.13.0-40-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.13.0-40-generic with 1.
														  dpkg: error processing package initramfs-tools (--configure):
														   installed initramfs-tools package post-installation script subprocess returned error exit status 1
														  Processing triggers for linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  /etc/kernel/postinst.d/dkms:
														   * dkms: running auto installation service for kernel 5.15.0-27-generic
														     ...done.
														  /etc/kernel/postinst.d/initramfs-tools:
														  update-initramfs: Generating /boot/initrd.img-5.15.0-27-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.15.0-27-generic with 1.
														  run-parts: /etc/kernel/postinst.d/initramfs-tools exited with return code 1
														  dpkg: error processing package linux-image-5.15.0-27-generic (--configure):
														   installed linux-image-5.15.0-27-generic package post-installation script subprocess returned error exit status 1
														  Errors were encountered while processing:
														   linux-firmware
														   linux-image-generic
														   linux-generic
														   wireguard
														   initramfs-tools
														   linux-image-5.15.0-27-generic
														- `sudo apt-get install -f` error
														  boss@boss-XPS:~$ sudo apt-get install -f
														  Reading package lists... Done
														  Building dependency tree... Done
														  Reading state information... Done
														  The following packages were automatically installed and are no longer required:
														    cryptsetup-run gcc-11-base:i386 gir1.2-gnomebluetooth-1.0 gjs libabsl20200923 libaom0 libavif9 libcamel-1.2-62 libcbor0.6 libcmis-0.5-5v5
														    libcodec2-0.9 libcurl3-gnutls:i386 libdav1d4 libextutils-pkgconfig-perl libfluidsynth2 libgdbm-compat4:i386 libgdbm6:i386
														    libgdk-pixbuf-xlib-2.0-0 libgdk-pixbuf2.0-0 libglu1-mesa:i386 libgupnp-1.2-0 libicu67 libicu67:i386 libidn11 libieee1284-3:i386 libigdgmm11
														    libkf5pulseaudioqt2 libllvm13:i386 libmbedcrypto3 libmbedtls12 libmbedx509-0 libmms0 libmozjs-78-0 libnspr4:i386 libnss3:i386 libntfs-3g883
														    libodbc1:i386 libodbccr2:i386 libofa0 libopenaptx0 libopengl0:i386 libopenjp2-7:i386 liborcus-0.16-0 liborcus-parser-0.16-0 libpango-perl
														    libpci3:i386 libperl5.32 libperl5.32:i386 libperl5.34:i386 libplacebo72 libpoppler-glib8:i386 libpoppler111 libpoppler111:i386
														    libpoppler118:i386 libpython3.9 libpython3.9-dev libpython3.9-minimal libpython3.9-stdlib libreadonly-perl libref-util-perl
														    libref-util-xs-perl libsane1:i386 libsnmp40:i386 libssl1.1:i386 libtinyxml2-8 libtype-tiny-perl libtype-tiny-xs-perl liburing1 libvpx6
														    libvpx6:i386 libwebp6 libwebp6:i386 libwrap0:i386 libx264-160 libx265-192 libxmlb1 linux-headers-5.13.0-40 linux-headers-5.13.0-40-generic
														    linux-image-5.13.0-40-generic linux-modules-5.13.0-40-generic linux-modules-extra-5.13.0-40-generic ltrace perl-modules-5.32 pkg-config
														    plasma-workspace-wayland python-pip-whl python3-ecdsa python3-simplejson python3.9 python3.9-dev python3.9-minimal swtpm-libs
														  Use 'sudo apt autoremove' to remove them.
														  0 to upgrade, 0 to newly install, 0 to remove and 0 not to upgrade.
														  6 not fully installed or removed.
														  After this operation, 0 B of additional disk space will be used.
														  Setting up initramfs-tools (0.140ubuntu13) ...
														  update-initramfs: deferring update (trigger activated)
														  Setting up linux-firmware (20220329.git681281e4-0ubuntu1) ...
														  update-initramfs: Generating /boot/initrd.img-5.13.0-40-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.13.0-40-generic with 1.
														  dpkg: error processing package linux-firmware (--configure):
														   installed linux-firmware package post-installation script subprocess returned error exit status 1
														  Setting up linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  dpkg: dependency problems prevent configuration of linux-image-generic:
														   linux-image-generic depends on linux-firmware; however:
														    Package linux-firmware is not configured yet.
														  
														  dpkg: error processing package linux-image-generic (--configure):
														   dependency problems - leaving unconfigured
														  dpkg: dependency problems prevent configuration of linux-generic:
														   linux-generic depends on linux-image-generic (= 5.15.0.27.30); however:
														    Package linux-image-generic is not configured yet.
														  
														  dpkg: error processing package linux-generic (--configure):
														   dependency problems - leaving unconfigured
														  dpkg: dependency problems prevent configuration of wireguard:
														   wireguard depends on wireguard-dkms (>= 0.0.20200121-2) | wireguard-modules (>= 0.0.20191219); however:
														    Package wireguard-dkms is not installed.
														    Package wireguard-modules is not installed.
														    Package linux-image-generic which provides wireguard-modules is not configured yet.
														  
														  No apport report written because the error message indicates it's a follow-up error from a previous failure.
														                                                                                                              No apport report written because the error message indicates it's a follow-up error from a previous failure.
														                                                                         No apport report written because MaxReports has already been reached
														                                                                                                                                             dpkg: error processing package wireguard (--configure):
														   dependency problems - leaving unconfigured
														  Processing triggers for initramfs-tools (0.140ubuntu13) ...
														  update-initramfs: Generating /boot/initrd.img-5.13.0-40-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.13.0-40-generic with 1.
														  dpkg: error processing package initramfs-tools (--configure):
														   installed initramfs-tools package post-installation script subprocess returned error exit status 1
														  No apport report written because MaxReports has already been reached
														                                                                      Processing triggers for linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  /etc/kernel/postinst.d/dkms:
														   * dkms: running auto installation service for kernel 5.15.0-27-generic
														     ...done.
														  /etc/kernel/postinst.d/initramfs-tools:
														  update-initramfs: Generating /boot/initrd.img-5.15.0-27-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.15.0-27-generic with 1.
														  run-parts: /etc/kernel/postinst.d/initramfs-tools exited with return code 1
														  dpkg: error processing package linux-image-5.15.0-27-generic (--configure):
														   installed linux-image-5.15.0-27-generic package post-installation script subprocess returned error exit status 1
														  No apport report written because MaxReports has already been reached
														                                                                      Errors were encountered while processing:
														   linux-firmware
														   linux-image-generic
														   linux-generic
														   wireguard
														   initramfs-tools
														   linux-image-5.15.0-27-generic
														  E: Sub-process /usr/bin/dpkg returned an error code (1)
														- sudo apt-get install -y linux-firmware
														  boss@boss-XPS:~$ sudo apt-get install -y linux-firmware
														  Reading package lists... Done
														  Building dependency tree... Done
														  Reading state information... Done
														  linux-firmware is already the newest version (20220329.git681281e4-0ubuntu1).
														  The following packages were automatically installed and are no longer required:
														    cryptsetup-run gcc-11-base:i386 gir1.2-gnomebluetooth-1.0 gjs libabsl20200923 libaom0 libavif9 libcamel-1.2-62 libcbor0.6 libcmis-0.5-5v5
														    libcodec2-0.9 libcurl3-gnutls:i386 libdav1d4 libextutils-pkgconfig-perl libfluidsynth2 libgdbm-compat4:i386 libgdbm6:i386
														    libgdk-pixbuf-xlib-2.0-0 libgdk-pixbuf2.0-0 libglu1-mesa:i386 libgupnp-1.2-0 libicu67 libicu67:i386 libidn11 libieee1284-3:i386 libigdgmm11
														    libkf5pulseaudioqt2 libllvm13:i386 libmbedcrypto3 libmbedtls12 libmbedx509-0 libmms0 libmozjs-78-0 libnspr4:i386 libnss3:i386 libntfs-3g883
														    libodbc1:i386 libodbccr2:i386 libofa0 libopenaptx0 libopengl0:i386 libopenjp2-7:i386 liborcus-0.16-0 liborcus-parser-0.16-0 libpango-perl
														    libpci3:i386 libperl5.32 libperl5.32:i386 libperl5.34:i386 libplacebo72 libpoppler-glib8:i386 libpoppler111 libpoppler111:i386
														    libpoppler118:i386 libpython3.9 libpython3.9-dev libpython3.9-minimal libpython3.9-stdlib libreadonly-perl libref-util-perl
														    libref-util-xs-perl libsane1:i386 libsnmp40:i386 libssl1.1:i386 libtinyxml2-8 libtype-tiny-perl libtype-tiny-xs-perl liburing1 libvpx6
														    libvpx6:i386 libwebp6 libwebp6:i386 libwrap0:i386 libx264-160 libx265-192 libxmlb1 linux-headers-5.13.0-40 linux-headers-5.13.0-40-generic
														    linux-image-5.13.0-40-generic linux-modules-5.13.0-40-generic linux-modules-extra-5.13.0-40-generic ltrace perl-modules-5.32 pkg-config
														    plasma-workspace-wayland python-pip-whl python3-ecdsa python3-simplejson python3.9 python3.9-dev python3.9-minimal swtpm-libs
														  Use 'sudo apt autoremove' to remove them.
														  0 to upgrade, 0 to newly install, 0 to remove and 0 not to upgrade.
														  6 not fully installed or removed.
														  After this operation, 0 B of additional disk space will be used.
														  Setting up initramfs-tools (0.140ubuntu13) ...
														  update-initramfs: deferring update (trigger activated)
														  Setting up linux-firmware (20220329.git681281e4-0ubuntu1) ...
														  update-initramfs: Generating /boot/initrd.img-5.13.0-40-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.13.0-40-generic with 1.
														  dpkg: error processing package linux-firmware (--configure):
														   installed linux-firmware package post-installation script subprocess returned error exit status 1
														  Setting up linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  dpkg: dependency problems prevent configuration of linux-image-generic:
														   linux-image-generic depends on linux-firmware; however:
														    Package linux-firmware is not configured yet.
														  
														  dpkg: error processing package linux-image-generic (--configure):
														   dependency problems - leaving unconfigured
														  dpkg: dependency problems prevent configuration of linux-generic:
														   linux-generic depends on linux-image-generic (= 5.15.0.27.30); however:
														    Package linux-image-generic is not configured yet.
														  
														  dpkg: error processing package linux-generic (--configure):
														   dependency problems - leaving unconfigured
														  dpkg: dependency problems prevent configuration of wireguard:
														   wireguard depends on wireguard-dkms (>= 0.0.20200121-2) | wireguard-modules (>= 0.0.20191219); however:
														    Package wireguard-dkms is not installed.
														    Package wireguard-modules is not installed.
														    Package linux-image-generic which provides wireguard-modules is not configured yet.
														  
														  dpkg: error processing package wireguard (--configure):
														   dependency problems No apport report written because the error message indicates it's a follow-up error from a previous failure.
														                                                                                                                                   No apport report written because the error message indicates it's a follow-up error from a previous failure.
														                                                                                              No apport report written because MaxReports has already been reached
														                 - leaving unconfigured
														  Processing triggers for initramfs-tools (0.140ubuntu13) ...
														  update-initramfs: Generating /boot/initrd.img-5.13.0-40-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.13.0-40-generic with 1.
														  dpkg: error processing package initramfs-tools (--configure):
														   installed initramfs-tools package post-installation script subprocess returned error exit status 1
														  No apport report written because MaxReports has already been reached
														                                                                      Processing triggers for linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  /etc/kernel/postinst.d/dkms:
														   * dkms: running auto installation service for kernel 5.15.0-27-generic
														     ...done.
														  /etc/kernel/postinst.d/initramfs-tools:
														  update-initramfs: Generating /boot/initrd.img-5.15.0-27-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.15.0-27-generic with 1.
														  run-parts: /etc/kernel/postinst.d/initramfs-tools exited with return code 1
														  dpkg: error processing package linux-image-5.15.0-27-generic (--configure):
														   installed linux-image-5.15.0-27-generic package post-installation script subprocess returned error exit status 1
														  No apport report written because MaxReports has already been reached
														                                                                      Errors were encountered while processing:
														   linux-firmware
														   linux-image-generic
														   linux-generic
														   wireguard
														   initramfs-tools
														   linux-image-5.15.0-27-generic
														  E: Sub-process /usr/bin/dpkg returned an error code (1)
													- Progress 1
													  collapsed:: true
														- sudo apt autoremove
														  collapsed:: true
														  boss@boss-XPS:~$ sudo apt autoremove
														  Reading package lists... Done
														  Building dependency tree... Done
														  Reading state information... Done
														  The following packages will be REMOVED
														    cryptsetup-run gcc-11-base:i386 gir1.2-gnomebluetooth-1.0 gjs libabsl20200923 libaom0 libavif9 libcamel-1.2-62 libcbor0.6 libcmis-0.5-5v5
														    libcodec2-0.9 libcurl3-gnutls:i386 libdav1d4 libextutils-pkgconfig-perl libfluidsynth2 libgdbm-compat4:i386 libgdbm6:i386
														    libgdk-pixbuf-xlib-2.0-0 libgdk-pixbuf2.0-0 libglu1-mesa:i386 libgupnp-1.2-0 libicu67 libicu67:i386 libidn11 libieee1284-3:i386 libigdgmm11
														    libkf5kipi-data libkf5kipi32.0.0 libkf5pulseaudioqt2 libllvm13:i386 libmbedcrypto3 libmbedtls12 libmbedx509-0 libmms0 libmozjs-78-0
														    libnspr4:i386 libnss3:i386 libntfs-3g883 libodbc1:i386 libodbccr2:i386 libofa0 libokular5core9 libopenaptx0 libopengl0:i386 libopenjp2-7:i386
														    liborcus-0.16-0 liborcus-parser-0.16-0 libpango-perl libpci3:i386 libperl5.32 libperl5.32:i386 libperl5.34:i386 libplacebo72
														    libpoppler-glib8:i386 libpoppler111 libpoppler111:i386 libpoppler118:i386 libpython3.9 libpython3.9-dev libpython3.9-minimal
														    libpython3.9-stdlib libreadonly-perl libref-util-perl libref-util-xs-perl libsane1:i386 libsnmp40:i386 libssl1.1:i386 libtinyxml2-8
														    libtype-tiny-perl libtype-tiny-xs-perl liburing1 libvpx6 libvpx6:i386 libwebp6 libwebp6:i386 libwrap0:i386 libx264-160 libx265-192 libxmlb1
														    linux-headers-5.13.0-40 linux-headers-5.13.0-40-generic linux-image-5.13.0-40-generic linux-modules-5.13.0-40-generic
														    linux-modules-extra-5.13.0-40-generic ltrace perl-modules-5.32 pkg-config plasma-workspace-wayland python-pip-whl python3-ecdsa
														    python3-simplejson python3.9 python3.9-dev python3.9-minimal swtpm-libs
														  0 to upgrade, 0 to newly install, 95 to remove and 1 not to upgrade.
														  6 not fully installed or removed.
														  After this operation, 943 MB disk space will be freed.
														  Do you want to continue? [Y/n]  (Reading database ... 457166 files and directories currently installed.)
														  Removing cryptsetup-run (2:2.4.3-1ubuntu1) ...
														  Removing gcc-11-base:i386 (11.2.0-19ubuntu1) ...
														  Removing gir1.2-gnomebluetooth-1.0:amd64 (3.34.5-3) ...
														  Removing gjs (1.72.0-1) ...
														  Removing libabsl20200923:amd64 (0~20200923.3-3ubuntu1) ...
														  Removing libaom0:amd64 (1.0.0.errata1-3build1) ...
														  Removing libavif9:amd64 (0.8.4-2) ...
														  Removing libcamel-1.2-62:amd64 (3.40.4-1ubuntu1) ...
														  Removing libcbor0.6:amd64 (0.6.0-0ubuntu3) ...
														  Removing libcmis-0.5-5v5 (0.5.2-3build1) ...
														  Removing libcodec2-0.9:amd64 (0.9.2-4) ...
														  Removing libsane1:i386 (1.1.1-5) ...
														  Removing libcurl3-gnutls:i386 (7.81.0-1) ...
														  Removing libdav1d4:amd64 (0.7.1-3) ...
														  Removing libextutils-pkgconfig-perl (1.16-1.1) ...
														  Removing libfluidsynth2:amd64 (2.1.7-1.1) ...
														  Removing libperl5.32:i386 (5.32.1-3ubuntu3) ...
														  Removing libsnmp40:i386 (5.9.1+dfsg-1ubuntu2) ...
														  Removing libperl5.34:i386 (5.34.0-3ubuntu1) ...
														  Removing libgdbm-compat4:i386 (1.23-1) ...
														  Removing libgdbm6:i386 (1.23-1) ...
														  Removing libgdk-pixbuf2.0-0:amd64 (2.40.2-2build4) ...
														  Removing libgdk-pixbuf-xlib-2.0-0:amd64 (2.40.2-2build4) ...
														  Removing libglu1-mesa:i386 (9.0.2-1) ...
														  Removing libgupnp-1.2-0:amd64 (1.2.7-1) ...
														  Removing libicu67:amd64 (67.1-7ubuntu1) ...
														  Removing libicu67:i386 (67.1-7ubuntu1) ...
														  Removing libidn11:amd64 (1.33-3) ...
														  Removing libieee1284-3:i386 (0.2.11-14build2) ...
														  Removing libigdgmm11:amd64 (21.2.2+ds1-1) ...
														  Removing libkf5kipi32.0.0:amd64 (4:22.04.0-0ubuntu1~ubuntu22.04~ppa10) ...
														  Removing libkf5kipi-data (4:22.04.0-0ubuntu1~ubuntu22.04~ppa10) ...
														  Removing libkf5pulseaudioqt2:amd64 (1.2-2build1) ...
														  Removing libllvm13:i386 (1:13.0.1-2ubuntu2) ...
														  Removing libmbedtls12:amd64 (2.16.9-0.1ubuntu1) ...
														  Removing libmbedx509-0:amd64 (2.16.9-0.1ubuntu1) ...
														  Removing libmbedcrypto3:amd64 (2.16.9-0.1ubuntu1) ...
														  Removing libmms0:amd64 (0.6.4-3) ...
														  Removing libmozjs-78-0:amd64 (78.15.0-4ubuntu1) ...
														  Removing libpoppler111:i386 (21.06.1-1) ...
														  Removing libpoppler-glib8:i386 (22.02.0-2) ...
														  Removing libpoppler118:i386 (22.02.0-2) ...
														  Removing libnss3:i386 (2:3.68.2-0ubuntu1) ...
														  Removing libnspr4:i386 (2:4.32-3build1) ...
														  Removing libntfs-3g883 (1:2017.3.23AR.3-3ubuntu5) ...
														  Removing libodbc1:i386 (2.3.9-5) ...
														  Removing libodbccr2:i386 (2.3.9-5) ...
														  Removing libofa0:amd64 (0.9.3-21) ...
														  Removing libokular5core9 (4:21.12.3-0ubuntu1) ...
														  Removing libopenaptx0:amd64 (0.2.0-6) ...
														  Removing libopengl0:i386 (1.4.0-1) ...
														  Removing libopenjp2-7:i386 (2.4.0-6) ...
														  Removing liborcus-0.16-0:amd64 (0.16.1-3ubuntu1) ...
														  Removing liborcus-parser-0.16-0:amd64 (0.16.1-3ubuntu1) ...
														  Removing libpango-perl (1.227-3build3) ...
														  Removing libpci3:i386 (1:3.7.0-6) ...
														  Removing libperl5.32:amd64 (5.32.1-3ubuntu3) ...
														  Removing libplacebo72:amd64 (2.72.2-1) ...
														  Removing libpoppler111:amd64 (21.06.1-1) ...
														  Removing python3.9-dev (3.9.7-2build1) ...
														  Removing libpython3.9-dev:amd64 (3.9.7-2build1) ...
														  Removing libpython3.9:amd64 (3.9.7-2build1) ...
														  Removing python3.9 (3.9.7-2build1) ...
														  Removing libpython3.9-stdlib:amd64 (3.9.7-2build1) ...
														  Removing python3.9-minimal (3.9.7-2build1) ...
														  Unlinking and removing bytecode for runtime python3.9
														  Removing libpython3.9-minimal:amd64 (3.9.7-2build1) ...
														  Removing libreadonly-perl (2.050-3) ...
														  Removing libref-util-perl (0.204-1) ...
														  Removing libref-util-xs-perl (0.117-1build5) ...
														  Removing libssl1.1:i386 (1.1.1l-1ubuntu1.2) ...
														  Removing libtinyxml2-8:amd64 (8.1.0+really8.0.0+dfsg-1) ...
														  Removing libtype-tiny-perl (1.012004-1) ...
														  Removing libtype-tiny-xs-perl (0.022-1build2) ...
														  Removing liburing1:amd64 (0.7-3ubuntu3) ...
														  Removing libvpx6:amd64 (1.9.0-1ubuntu1) ...
														  Removing libvpx6:i386 (1.9.0-1ubuntu1) ...
														  Removing libwebp6:i386 (0.6.1-2.1) ...
														  Removing libwebp6:amd64 (0.6.1-2.1) ...
														  Removing libwrap0:i386 (7.6.q-31build2) ...
														  Removing libx264-160:amd64 (2:0.160.3011+gitcde9a93-2.1) ...
														  Removing libx265-192:amd64 (3.4-2) ...
														  Removing libxmlb1:amd64 (0.1.15-2ubuntu1) ...
														  Removing linux-headers-5.13.0-40-generic (5.13.0-40.45) ...
														  Removing linux-headers-5.13.0-40 (5.13.0-40.45) ...
														  Removing linux-modules-extra-5.13.0-40-generic (5.13.0-40.45) ...
														  Removing ltrace (0.7.3-6.1ubuntu6) ...
														  Removing perl-modules-5.32 (5.32.1-3ubuntu3) ...
														  Removing pkg-config (0.29.2-1ubuntu3) ...
														  Removing plasma-workspace-wayland (4:5.24.4-0ubuntu1) ...
														  Removing python-pip-whl (20.3.4-4) ...
														  Removing python3-ecdsa (0.18.0~b1-1) ...
														  Removing python3-simplejson (3.17.6-1build1) ...
														  Removing swtpm-libs:amd64 (0.6.0-1~impish1.2) ...
														  Removing linux-modules-5.13.0-40-generic (5.13.0-40.45) ...
														  Removing linux-image-5.13.0-40-generic (5.13.0-40.45) ...
														  /etc/kernel/prerm.d/dkms:
														  dkms: removing: hid-xpadneo v0.9-83-g45fef91 (5.13.0-40-generic) (x86_64)
														  Module hid-xpadneo-v0.9-83-g45fef91 for kernel 5.13.0-40-generic (x86_64).
														  Before uninstall, this module version was ACTIVE on this kernel.
														  
														  hid-xpadneo.ko:
															- Uninstallation
															  collapsed:: true
																- Deleting from: /lib/modules/5.13.0-40-generic/updates/dkms/
															- Original module
															  collapsed:: true
																- No original module was found for this module on this kernel.
																- Use the dkms install command to reinstall any previous module version.
																  
																  
																  																  Running the post_remove script:
																  																  Uninstalling ERTM override...
																  																  Uninstalling modalias database...
																  																  Uninstalling udev rules...
																  																  Reloading udev...
																  																  depmod...
																  
																  																  update-initramfs...
																  																  I: /boot/vmlinuz.old is now a symlink to vmlinuz-5.13.0-28-generic
																  																  I: /boot/initrd.img.old is now a symlink to initrd.img-5.13.0-28-generic
																  																  /etc/kernel/postrm.d/initramfs-tools:
																  																  update-initramfs: Deleting /boot/initrd.img-5.13.0-40-generic
																  																  /etc/kernel/postrm.d/zz-update-grub:
																  																  Sourcing file `/etc/default/grub'
																  																  Sourcing file `/etc/default/grub.d/init-select.cfg'
																  																  Generating grub configuration file ...
																  																  Found linux image: /boot/vmlinuz-5.15.0-27-generic
																  																  Found linux image: /boot/vmlinuz-5.13.0-28-generic
																  																  Found initrd image: /boot/initrd.img-5.13.0-28-generic
																  																  Found linux image: /boot/vmlinuz-5.13.0-27-generic
																  																  Found initrd image: /boot/initrd.img-5.13.0-27-generic
																  																  Found linux image: /boot/vmlinuz-5.13.0-25-generic
																  																  Found initrd image: /boot/initrd.img-5.13.0-25-generic
																  																  Found linux image: /boot/vmlinuz-5.13.0-23-generic
																  																  Found initrd image: /boot/initrd.img-5.13.0-23-generic
																  																  Found linux image: /boot/vmlinuz-5.13.0-22-generic
																  																  Found initrd image: /boot/initrd.img-5.13.0-22-generic
																  																  Memtest86+ needs a 16-bit boot, that is not available on EFI, exiting
																  																  Warning: os-prober will not be executed to detect other bootable partitions.
																  																  Systems on them will not be added to the GRUB boot configuration.
																  																  Check GRUB_DISABLE_OS_PROBER documentation entry.
																  																  Adding boot menu entry for UEFI Firmware Settings ...
																  																  done
																  																  Setting up initramfs-tools (0.140ubuntu13) ...
																  																  update-initramfs: deferring update (trigger activated)
																  																  Setting up linux-firmware (20220329.git681281e4-0ubuntu1) ...
																  																  update-initramfs: Generating /boot/initrd.img-5.13.0-28-generic
																  																  I: The initramfs will attempt to resume from /dev/dm-2
																  																  I: (/dev/mapper/vgkubuntu-swap_1)
																  																  I: Set the RESUME variable to override this.
																  																  update-initramfs: Generating /boot/initrd.img-5.13.0-27-generic
																  																  I: The initramfs will attempt to resume from /dev/dm-2
																  																  I: (/dev/mapper/vgkubuntu-swap_1)
																  																  I: Set the RESUME variable to override this.
																  																  update-initramfs: Generating /boot/initrd.img-5.13.0-25-generic
																  																  I: The initramfs will attempt to resume from /dev/dm-2
																  																  I: (/dev/mapper/vgkubuntu-swap_1)
																  																  I: Set the RESUME variable to override this.
																  																  update-initramfs: Generating /boot/initrd.img-5.13.0-23-generic
																  																  I: The initramfs will attempt to resume from /dev/dm-2
																  																  I: (/dev/mapper/vgkubuntu-swap_1)
																  																  I: Set the RESUME variable to override this.
																  																  update-initramfs: Generating /boot/initrd.img-5.13.0-22-generic
																  																  I: The initramfs will attempt to resume from /dev/dm-2
																  																  I: (/dev/mapper/vgkubuntu-swap_1)
																  																  I: Set the RESUME variable to override this.
																  																  Setting up linux-image-5.15.0-27-generic (5.15.0-27.28) ...
																  																  I: /boot/initrd.img is now a symlink to initrd.img-5.15.0-27-generic
																  																  Setting up linux-image-generic (5.15.0.27.30) ...
																  																  Setting up linux-generic (5.15.0.27.30) ...
																  																  Setting up wireguard (1.0.20210914-1ubuntu2) ...
																  																  Processing triggers for hicolor-icon-theme (0.17-2) ...
																  																  Processing triggers for gnome-menus (3.36.0-1ubuntu3) ...
																  																  Processing triggers for libc-bin (2.35-0ubuntu3) ...
																  																  Processing triggers for man-db (2.10.2-1) ...
																  																  Processing triggers for mailcap (3.70+nmu1ubuntu1) ...
																  																  Processing triggers for desktop-file-utils (0.26-1ubuntu3) ...
																  																  Processing triggers for initramfs-tools (0.140ubuntu13) ...
																  																  update-initramfs: Generating /boot/initrd.img-5.13.0-28-generic
																  																  I: The initramfs will attempt to resume from /dev/dm-2
																  																  I: (/dev/mapper/vgkubuntu-swap_1)
																  																  I: Set the RESUME variable to override this.
																  																  Processing triggers for linux-image-5.15.0-27-generic (5.15.0-27.28) ...
																  																  /etc/kernel/postinst.d/dkms:
																  																   * dkms: running auto installation service for kernel 5.15.0-27-generic
																  																			  ...done.
																  																  /etc/kernel/postinst.d/initramfs-tools:
																  																  update-initramfs: Generating /boot/initrd.img-5.15.0-27-generic
																  																  I: The initramfs will attempt to resume from /dev/dm-2
																  																  I: (/dev/mapper/vgkubuntu-swap_1)
																  																  I: Set the RESUME variable to override this.
																  																  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
																  																  update-initramfs: failed for /boot/initrd.img-5.15.0-27-generic with 1.
																  																  run-parts: /etc/kernel/postinst.d/initramfs-tools exited with return code 1
																  																  dpkg: error processing package linux-image-5.15.0-27-generic (--configure):
																  																   installed linux-image-5.15.0-27-generic package post-installation script subprocess returned error exit status 1
																  																  Errors were encountered while processing:
																  																   linux-image-5.15.0-27-generic
																  																  E: Sub-process /usr/bin/dpkg returned an error code (1)
														- Reduced `sudo dpkg --configure -a` errors down to 1 package (linux-image-5.15.0-27-generic)
														  boss@boss-XPS:~$ sudo dpkg --configure -a
														  [sudo] password for boss:  Setting up linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  Processing triggers for linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  /etc/kernel/postinst.d/dkms:
														   * dkms: running auto installation service for kernel 5.15.0-27-generic
														     ...done.
														  /etc/kernel/postinst.d/initramfs-tools:
														  update-initramfs: Generating /boot/initrd.img-5.15.0-27-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.15.0-27-generic with 1.
														  run-parts: /etc/kernel/postinst.d/initramfs-tools exited with return code 1
														  dpkg: error processing package linux-image-5.15.0-27-generic (--configure):
														   installed linux-image-5.15.0-27-generic package post-installation script subprocess returned error exit status 1
														  Errors were encountered while processing:
														   linux-image-5.15.0-27-generic
													- Issue 2
													  collapsed:: true
														- sudo apt --fix-broken install
														  boss@boss-XPS:~$ sudo apt --fix-broken install
														  Reading package lists... Done
														  Building dependency tree... Done
														  Reading state information... Done
														  0 to upgrade, 0 to newly install, 0 to remove and 0 not to upgrade.
														  1 not fully installed or removed.
														  After this operation, 0 B of additional disk space will be used.
														  Setting up linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  Processing triggers for linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  /etc/kernel/postinst.d/dkms:
														   * dkms: running auto installation service for kernel 5.15.0-27-generic
														     ...done.
														  /etc/kernel/postinst.d/initramfs-tools:
														  update-initramfs: Generating /boot/initrd.img-5.15.0-27-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.15.0-27-generic with 1.
														  run-parts: /etc/kernel/postinst.d/initramfs-tools exited with return code 1
														  dpkg: error processing package linux-image-5.15.0-27-generic (--configure):
														   installed linux-image-5.15.0-27-generic package post-installation script subprocess returned error exit status 1
														  Errors were encountered while processing:
														   linux-image-5.15.0-27-generic
														  E: Sub-process /usr/bin/dpkg returned an error code (1)
														- sudo apt dist-upgrade
														  boss@boss-XPS:~$ sudo apt dist-upgrade
														  Reading package lists... Done
														  Building dependency tree... Done
														  Reading state information... Done
														  Calculating upgrade... Done
														  0 to upgrade, 0 to newly install, 0 to remove and 0 not to upgrade.
														  1 not fully installed or removed.
														  After this operation, 0 B of additional disk space will be used.
														  Do you want to continue? [Y/n]
														  Setting up linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  Processing triggers for linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  /etc/kernel/postinst.d/dkms:
														   * dkms: running auto installation service for kernel 5.15.0-27-generic
														     ...done.
														  /etc/kernel/postinst.d/initramfs-tools:
														  update-initramfs: Generating /boot/initrd.img-5.15.0-27-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)
														  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.15.0-27-generic with 1.
														  run-parts: /etc/kernel/postinst.d/initramfs-tools exited with return code 1
														  dpkg: error processing package linux-image-5.15.0-27-generic (--configure):
														   installed linux-image-5.15.0-27-generic package post-installation script subprocess returned error exit status 1
														  Errors were encountered while processing:
														   linux-image-5.15.0-27-generic
														  E: Sub-process /usr/bin/dpkg returned an error code (1)
														- sudo apt install --reinstall linux-image-5.15.0-27-generic
														  boss@boss-XPS:~$ sudo apt install --reinstall linux-image-5.15.0-27-generic
														  Reading package lists... Done
														  Building dependency tree... Done
														  Reading state information... Done
														  0 to upgrade, 0 to newly install, 1 reinstalled, 0 to remove and 0 not to upgrade.
														  1 not fully installed or removed.
														  After this operation, 0 B of additional disk space will be used.
														  E: Internal Error, No file name for linux-image-5.15.0-27-generic:amd64
														- `sudo dpkg -C` revealed the package name
														  boss@boss-XPS:~$ sudo dpkg -C
														  The following packages are only half configured, probably due to problems
														  configuring them the first time. The configuration should be retried using
														  dpkg --configure <package> or the configure menu option in dselect:
														   linux-image-5.15.0-27-generic Signed kernel image generic
														- sudo dpkg --configure linux-image-5.15.0-27-generic
														  boss@boss-XPS:~$ sudo dpkg --configure linux-image-5.15.0-27-generic
														  Setting up linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  Processing triggers for linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  /etc/kernel/postinst.d/dkms:
														   * dkms: running auto installation service for kernel 5.15.0-27-generic
														     ...done.
														  /etc/kernel/postinst.d/initramfs-tools:
														  update-initramfs: Generating /boot/initrd.img-5.15.0-27-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)
														  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.15.0-27-generic with 1.
														  run-parts: /etc/kernel/postinst.d/initramfs-tools exited with return code 1
														  dpkg: error processing package linux-image-5.15.0-27-generic (--configure):
														   installed linux-image-5.15.0-27-generic package post-installation script subprocess returned error exit status 1
														  Errors were encountered while processing:
														   linux-image-5.15.0-27-generic
														- sudo apt autoremove
														  boss@boss-XPS:~$ sudo apt autoremove
														  Reading package lists... Done
														  Building dependency tree... Done
														  Reading state information... Done
														  0 to upgrade, 0 to newly install, 0 to remove and 0 not to upgrade.
														  1 not fully installed or removed.
														  After this operation, 0 B of additional disk space will be used.
														  Setting up linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  Processing triggers for linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  /etc/kernel/postinst.d/dkms:
														   * dkms: running auto installation service for kernel 5.15.0-27-generic
														     ...done.
														  /etc/kernel/postinst.d/initramfs-tools:
														  update-initramfs: Generating /boot/initrd.img-5.15.0-27-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.15.0-27-generic with 1.
														  run-parts: /etc/kernel/postinst.d/initramfs-tools exited with return code 1
														  dpkg: error processing package linux-image-5.15.0-27-generic (--configure):
														   installed linux-image-5.15.0-27-generic package post-installation script subprocess returned error exit status 1
														  Errors were encountered while processing:
														   linux-image-5.15.0-27-generic
														  E: Sub-process /usr/bin/dpkg returned an error code (1)
														- sudo apt full-upgrade
														  boss@boss-XPS:~$ sudo apt full-upgrade
														  Reading package lists... Done
														  Building dependency tree... Done
														  Reading state information... Done
														  Calculating upgrade... Done
														  0 to upgrade, 0 to newly install, 0 to remove and 0 not to upgrade.
														  1 not fully installed or removed.
														  After this operation, 0 B of additional disk space will be used.
														  Do you want to continue? [Y/n]
														  Setting up linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  Processing triggers for linux-image-5.15.0-27-generic (5.15.0-27.28) ...
														  /etc/kernel/postinst.d/dkms:
														   * dkms: running auto installation service for kernel 5.15.0-27-generic
														     ...done.
														  /etc/kernel/postinst.d/initramfs-tools:
														  update-initramfs: Generating /boot/initrd.img-5.15.0-27-generic
														  I: The initramfs will attempt to resume from /dev/dm-2
														  I: (/dev/mapper/vgkubuntu-swap_1)
														  I: Set the RESUME variable to override this.
														  zstd: error 25 : Write error : No space left on device (cannot write compressed block)
														  E: mkinitramfs failure zstd -q -1 -T0 25
														  update-initramfs: failed for /boot/initrd.img-5.15.0-27-generic with 1.
														  run-parts: /etc/kernel/postinst.d/initramfs-tools exited with return code 1
														  dpkg: error processing package linux-image-5.15.0-27-generic (--configure):
														   installed linux-image-5.15.0-27-generic package post-installation script subprocess returned error exit status 1
														  Errors were encountered while processing:
														   linux-image-5.15.0-27-generic
														  E: Sub-process /usr/bin/dpkg returned an error code (1)
														- sudo dpkg --purge linux-image-5.15.0-27-generic
														  boss@boss-XPS:~$ sudo dpkg --purge linux-image-5.15.0-27-generic
														  dpkg: dependency problems prevent removal of linux-image-5.15.0-27-generic:
														   linux-modules-extra-5.15.0-27-generic depends on linux-image-5.15.0-27-generic | linux-image-unsigned-5.15.0-27-generic; however:
														    Package linux-image-5.15.0-27-generic is to be removed.
														    Package linux-image-unsigned-5.15.0-27-generic is not installed.
														   linux-modules-5.15.0-27-generic depends on linux-image-5.15.0-27-generic | linux-image-unsigned-5.15.0-27-generic; however:
														    Package linux-image-5.15.0-27-generic is to be removed.
														    Package linux-image-unsigned-5.15.0-27-generic is not installed.
														   linux-image-generic depends on linux-image-5.15.0-27-generic.
														  
														  dpkg: error processing package linux-image-5.15.0-27-generic (--purge):
														   dependency problems - not removing
														  Errors were encountered while processing:
														   linux-image-5.15.0-27-generic
														- sudo update-initramfs -u
														- sudo apt remove linux-image-5.15.0-27-generic
												- Black icons after upgrading Kubuntu Fri, Apr 30, 2021
												  collapsed:: true
													- Replacing libqt5quick5-gles with libqt5quick5 solved my problem
													- `sudo apt install libqt5quick5` + rebooting was sufficient
												- Related:
													- ((63a9adc8-c0c0-4a67-a2f6-c19473da1a99)) : ((63a9adc7-4cc4-4ecc-933c-82c3163cfe29))
									- Troubleshooting
										- [[2024-10-16 Wednesday]] `tracker-miner-fs-3` using high CPU
										  collapsed:: true
											- Appears to be a GNOME file indexing package? Not sure what's triggering it
											- ((65f59162-16e9-4df4-a8e6-50d55588063a)) -e
												- showed errors regarding the package, database corrupt
											- `tracker3 reset -s` to reset the db
										- `qdbus` package not installed
										  collapsed:: true
											- [Bug #2084278 “On Kubuntu 24.10 qdbus command is not in PATH” : Bugs : qt6-tools package : Ubuntu](https://bugs.launchpad.net/ubuntu/+source/qt6-tools/+bug/2084278)
											-
											- `sudo apt install qtchooser`
											- Check installed qt version
												- ```
												  sudo apt-cache search qmake
												  sudo apt install qmake6
												  qmake6 --version
												  ```
											- `sudo apt install qdbus-qt6`
										- https://redlib.catsarch.com/r/linuxquestions/comments/1ofp1on/why_does_my_linux_laptop_suddenly_freeze_for_1020/
										-
									- ((635037c3-6032-4f23-9ba6-288274d6e473))
									- Related:
										- ((62d4471d-2ebd-46b8-b700-3b6362e06c80))
										- ((659d093f-bf67-444a-b2a1-ec0a28907583))
								- Ubuntu Budgie (Budgie)
								  collapsed:: true
								  MacOS+GNOME-like
									- Ubuntu Budgie provides the Budgie desktop environment which focuses on simplicity and elegance. It provides a traditional desktop metaphor based interface utilising a customisable panel based menu driven system.
								- Ubuntu MATE (MATE/GNOME2)
								  collapsed:: true
								  Windows/GNOME-like
									- https://ubuntu-mate.org
									- MATE is the continuation of GNOME2
									  https://ubuntu-mate.org/what-is-ubuntu-mate/
								- Xubuntu (Xfce)
								  collapsed:: true
								  Lightweight, GNOME-like
									- Xubuntu is an elegant and easy to use operating system. Xubuntu comes with Xfce, which is a stable, light and configurable desktop environment.
								- Lubuntu (LXQt)
								  Ultra-lightweight, Windows XP-like
								- Ubuntu Studio
								  collapsed:: true
								  multimedia creation
									- Ubuntu Studio is a multimedia content creation flavor of Ubuntu, aimed at the audio, video and graphic enthusiast or professional.
								- Ubuntu Kylin
								  for Chinese
							- _Ubuntu-based derivatives_
								- [Vanilla OS](https://vanillaos.org/)
								  id:: 67af5558-12df-49f2-b5f8-195e7236fe75
								  collapsed:: true
									- Powered by ((65a98a50-83c1-4846-a887-24b8d60e0d14))
									- Built on Ubuntu
								- elementary OS (Pantheon)
								  collapsed:: true
								  Very MacOS-like | GNOME fork
									- Cons
										- System tray - how would my many icons fit? Is there a KDocker alternative?
										- Taskbar - much of my apps are adhoc since they're in a container
										  https://elementary.io/images/responsive-images/notebook.jpg
									- v5 Juno in Oct 2018
									  https://medium.com/elementaryos/elementary-os-5-juno-is-here-471dfdedc7b3
										- Lots of great looking apps: AppCenter, Code (IDE), Files, Music, Terminal, Photos (file browser and simple editor), Camera, Epiphany (browser)
										- Desktop features: Night Light (like Redshift),
									- elementary apps
										- https://quassy.github.io/elementary-apps/
									- Pantheon desktop environment
									  https://en.wikipedia.org/wiki/Elementary_OS
								- [KDE Neon](https://neon.kde.org/)
								  id:: 65a98a50-43eb-4865-b8d4-3b9ba7b7f6e0
								  collapsed:: true
								  Ubuntu LTS but latest KDE
									- KDE Neon vs Kubuntu
										- The KDE Neon project (it doesn’t call itself a distribution) provides the latest officially released KDE software, including the Plasma desktop, on top of a dependable Ubuntu long-term support (LTS) foundation.
											- Kubuntu provides a frozen snapshot of KDE technologies often on top of a newer Ubuntu base, while KDE Neon provides the latest KDE technologies on top of a frozen Ubuntu LTS base.
										- **However - **this can also be emulated on Kubuntu by using Kubuntu LTS + KDE backports PPA
										  intralink2:: https://workflowy.com/#/ae6be8b310d5
									- Related: ((62e11d87-874f-4112-8bd5-a0a8f6651248))
								- Trisquel
								  collapsed:: true
								  FSF and GNU-approved 100% libre
									- https://trisquel.info/
								- Linux Mint (Cinanmon)
								  More user-friendly
								- Zorin OS
								  More user-friendly. Windows-like
								- [Pop!_OS](https://pop.system76.com/)
								  id:: 66bcb5ff-7b0f-4883-81e2-3456743c0fc8
								  collapsed:: true
								  by System76
									- [COSMIC](https://system76.com/cosmic) desktop environment
									  Rust-based
							- _Lists_
								- https://wiki.ubuntu.com/DerivativeTeam/Derivatives#Knownv
				- ### ((63c2a256-30fe-4cd5-a827-2f269b98b0c0))-based (RPM)
				  id:: 65a98a50-6f25-453a-b065-d694201ff01d
					- Meta
						- Red Hat
						  id:: 663b7b14-819d-4cd1-b92f-b87eea75f1be
						  collapsed:: true
							- [Red Hat cutting back RHEL source availability [LWN.net]](https://lwn.net/Articles/935592/)
								- [Openela releases Red Hat source code on GitHub](https://github.com/orgs/openela-main/repositories)
							- More consumer-friendly alternative to Canonical
								- They made pioneering work on Flatpak, OSTree, Toolbox, Wayland, PipeWire
								  source:: [https://blogs.gnome.org/uraeus/2021/09/24/fedora-workstation-our-vision-for-linux-desktop/](https://blogs.gnome.org/uraeus/2021/09/24/fedora-workstation-our-vision-for-linux-desktop/)
								- Canonical are pushing Snaps with Ubuntu, including Firefox and Chromium
					- Pros/Cons
					  id:: 65a98a50-67d9-4877-aafe-a830118d8233
					  collapsed:: true
						- Pros
							- First-class support for ((63a9adc7-c031-4dc6-a162-c91f04da953c)) and ((63a9adc7-b9eb-401b-be40-5f8836b86618))
							- They use a semi-rolling release model, which means they get only freeze core packages like GNOME whereas other packages get rolling release
							- They integrate newer useful technology faster than Ubuntu
								- Flatpak, Pipewire, Wayland, BTRFS, fs-verity are all defaults unlike ((65a98a51-575b-460b-8931-8850224f04ed))
								- They also pioneered systemd, PulseAudio
								- BTRFS
								  collapsed:: true
									- [https://teddit.ggc-project.de/r/Fedora/comments/qv35js/btrfs_doesnt_make_any_sense_on_silverblue_does_it/](https://teddit.ggc-project.de/r/Fedora/comments/qv35js/btrfs_doesnt_make_any_sense_on_silverblue_does_it/)
									- [https://fedoraproject.org/wiki/Features/SystemRollbackWithBtrfs](https://fedoraproject.org/wiki/Features/SystemRollbackWithBtrfs)
									- Works well with Timeshift
								- ((63a9adc7-c031-4dc6-a162-c91f04da953c))
						- Cons
							- ((65a98a50-0731-4784-800c-6d449b3ab3cb)) - security and gaming enhancements
							- GNOME is a Red Hat project foremost, so it may have worse support for KDE
						- Unclear
							- ((663b7b14-819d-4cd1-b92f-b87eea75f1be))
					- [Fedora](https://fedoraproject.org/)
					  id:: 63c2a256-30fe-4cd5-a827-2f269b98b0c0
					  collapsed:: true
						- Pros/Cons
						  id:: 65a98a50-154c-4108-a916-a64b699d639f
							- Pros
							- Cons
								- Fedora repo for some Flatpaks
									- `flatpak list|grep fedora`
										- ```
										  Breeze org.fedoraproject.Gtk3theme.Breeze 3.22 fedora system
										  Fedora Platform org.fedoraproject.Platform 41 f41 fedora system
										  default org.fedoraproject.Platform.GL.default f41 fedora system
										  fedoraproject platform translations org.fedoraproject.Platform.Locale f41 fedora system
										  Evolution org.gnome.Evolution 3.54.3 stable fedora system
										  Extensions org.gnome.Extensions 47.2 stable fedora system
										  ```
									- The below command will replace Fedora Flatpaks with their Flathub versions.
										- `flatpak install --reinstall flathub $(flatpak list --app-runtime=org.fedoraproject.Platform --columns=application)`
										- Then delete the fedora repo: flatpak remote-delete fedora. You may have some stragglers left in flatpak list so delete them manually with remove
							- ((65a98a50-6f25-453a-b065-d694201ff01d)) : ((65a98a50-67d9-4877-aafe-a830118d8233))
						- Fedora live USB
							- https://fedoraproject.org/wiki/How_to_create_and_use_Live_USB#Quickstart:_Using_Fedora_Media_Writer
						- [Differences to Ubuntu - Fedora Project Wiki](https://fedoraproject.org/wiki/Differences_to_Ubuntu)
						- Spins
							- [Fedora KDE Plasma Desktop](https://fedoraproject.org/spins/kde)
							  id:: 67827678-0a4e-43e2-81bd-f21f6609b8ee
					- [Fedora Atomic Desktops](https://fedoraproject.org/atomic-desktops/)
					  id:: 65a98a50-c3d9-4680-9f69-f7c723cc6a21
					  collapsed:: true
					  AKA Immutable | Silverblue/Kinoite
						- Pros/Cons
							- Pros
								- First class support for Flatpak and containers (podman-based, but also docker)
								- You can still install normal packages, which are layered via ((65a98a50-2591-4e33-8199-6549819f8422))
							- Cons
								- apps installed through ((65a98a50-10c8-441b-9b7a-65be37e7c70b)) must reboot to be usable since it'll then point to a different tree
							- Upstream Pros/Cons
								- ((65a98a50-6f25-453a-b065-d694201ff01d))
								- ((63a873fd-893d-4ed7-ae5b-e27945e68230)) : ((65a98a51-6d04-4840-bab1-9e761759869a))
							- _Comparisons_
								- Comparison to ((63a9adc7-fc79-4fa3-8ca5-925a17291c26))
								  collapsed:: true
									- Silverblue Pros
									  collapsed:: true
										- Uses standard UNIX Filesystem Hierarchy Standard (FHS)
											- which maintains backwards-compatibility with the huge amount of existing Linux software
										- Immutable distribution
											- approach also used by Steam Deck
											- OS itself can't break
												- like unrooted Android the core can't be affected and is the same on every device
										- Opinionated distribution - they'll add and replace newer technologies
											- I don't want to have to setup newer better technology like Pipewire, Wayland, etc myself
									- Silverblue Cons
										- Incompatible with [Home Manager](https://workflowy.com/#/4994da8d7862), though Flatpak makes more sense for managing /home/ state
											- Existing /home/ files
												- .local/
													- share (99%)
														- plasma-vault (77%)
														- Steam (9%) - 10GB
													- lib - mostly 1GB of python versions
												- .wine/ - 30GB of a few games
												- .cache/ - 20GB
												- .var/ - 20GB of Flatpak config files
										- Nix is fully reproducible
									- _OSTree comparison to [Nix](https://workflowy.com/#/362a9bd963f1)_
								- Related: ((663a5790-1384-4fe1-8d26-7f5facd72520))
							- Unclear
								- ((63a9adc7-b9eb-401b-be40-5f8836b86618)) or ((63a9adc7-c031-4dc6-a162-c91f04da953c)) can be used for installing normal packages
								- ((65a98a50-10c8-441b-9b7a-65be37e7c70b)) used as the package manager
								- Some apps unsure if they'll work
								  collapsed:: true
									- Does it support Docker well?
									- ((63a9adf9-dcc0-4caa-a0da-f495b1d63abc))
								- Does AppImage work well? Many apps I have only distribute as that
								  collapsed:: true
									- Athens Research
									- Ledger Live Desktop
									- Rotki
									- Logseq
									- Syncthing? Think I'm using native package for that
									- TagSpaces
									- WorkFlowy
								- Do binaries work well? Many apps I have only distribute as that
								  collapsed:: true
									- See [Some software I choose to install as portable with the binaries and config files all in encrypted storage](https://workflowy.com/#/b74746cf1679)
									  collapsed:: true
										- Some software I choose to install as portable with the binaries and config files all in encrypted storage
									- Focalboard
									- Dynalist
									- Telegram - using it portably for multi-user. Note: there is a Flatpak
								- ((65a98a51-c0aa-4c29-9f88-e87c95d389ba))
						- # Official Flavours
						  id:: 671d6a82-3b61-4768-bc3f-6e57b9362565
							- Meta
								- Firefox installed is native, not a Flatpak. [Plans to change it in the future](https://gitlab.com/fedora/ostree/sig/-/issues/3) once ((67829245-7660-438a-b181-4b0936de292d)) addressed
								  collapsed:: true
									- [Firefox Flatpak limitations](https://gitlab.com/fedora/sigs/flatpak/fedora-flatpaks/-/issues/13)
									  id:: 67829245-7660-438a-b181-4b0936de292d
									- Can be removed by `rpm-ostree override remove`
									  id:: 67829180-e165-45a0-b29b-79424c33b4a0
								- Commands cheatsheet ![silverblue-cheatsheet.pdf](../assets/silverblue-cheatsheet_1736609356099_0.pdf)
							- [Fedora Kinoite](https://fedoraproject.org/atomic-desktops/kinoite/)
							  id:: 671b6e25-ba39-4d7d-b20e-1f12303488ca
							  Uses ((65f58f8e-1860-4087-b0f5-a9ef34dbb9b7))
							- [Fedora Silverblue](https://fedoraproject.org/atomic-desktops/silverblue/)
							  id:: 671b6e2e-3a05-4ba8-9abf-9fc0d616209e
							  Uses GNOME
							- Related:
								- ((67828cfe-6e00-41de-9942-f4b7db4562ed))
								- [Kicksecure](https://www.kicksecure.com/)
								  id:: 67826b0d-8952-4cd4-8281-7c2dcae1cf7a
								  Hardened Debian which runs inside multiple VMs on top of the host OS
									- [Verified Boot](https://www.kicksecure.com/wiki/Verified_Boot)
									  id:: 67c074c4-a262-43f4-a8a8-216c39d62680
						- # Custom Images
						  id:: 67828cfe-6e00-41de-9942-f4b7db4562ed
						  collapsed:: true
							- [Universal Blue](https://universal-blue.org/)
							  id:: 67828d01-9634-453e-a1bc-189c808e0bef
							  Custom images that work like distributions
								- Pros/Cons
									- Pros
										- Rebase back to Fedora without reinstallation
									- Cons
										-
									- Unclear
									- Comparisons
								- Meta
									- [boxkit](https://github.com/ublue-os/boxkit)
									  built on ((63a9adc7-b9eb-401b-be40-5f8836b86618))
								- [Aurora](https://getaurora.dev/)
								- ((671d6a81-feca-42b1-b68c-30c58d4c6f84))
								- [Project Bluefin](https://projectbluefin.io/)
								- [uCore](https://projectucore.io/)
							- [Community-created custom images](https://universal-blue.discourse.group/t/list-of-community-created-custom-images/340)
							- [Secureblue](https://github.com/secureblue/secureblue)
							  id:: 678269ef-8192-4e6a-99f5-18f2707c0072
							  collapsed:: true
							  Hardened fork
								- [Secureblue - Immutable Fedora Hardening - Tool Suggestions - Privacy Guides Community](https://discuss.privacyguides.net/t/secureblue-immutable-fedora-hardening/16086)
									- GrapheneOS’s hardened_malloc
										- issues with using GrapheneOS’s hardened_malloc for certain flatpaks such as Thunderbird. Albeit, the user can solve this particular issue by using flatseal to disable hardened_malloc for troublesome flatpaks such as Thunderbird
									- [Sudoless](https://github.com/secureblue/secureblue/releases/tag/v4.2.0)
									- secureblue has benefitted massively by *not* being a distro, and instead shipping as bootable OCI container images. This has meant a ton of overhead is taken care of for us by Fedora. We don’t need general repos or packaging, except for a handful of specific packages (hardened-chromium, hardened_malloc, etc). The Fedora Atomic ecosystem is also rich in tooling and automation (see: [Blue-Build](https://blue-build.org/)), plus the backdrop of robust container technology that already exists. All of this has largely enabled us to focus our energy on the hardening, and not waste time doing manual maintenance.
									-
							- Related:
								- ((671d6a82-3b61-4768-bc3f-6e57b9362565))
								- ((67af5558-12df-49f2-b5f8-195e7236fe75))
								- Chimera OS
								- ((63a9adc7-fc79-4fa3-8ca5-925a17291c26))
						- To do
							- Install Kinoite on a VM or USB
							- Try Silverblue's tools of Toolbox and any other, see how well they work for containerising non-Flatpak software like Lutris
						- What
							- Flatpak for user apps
							- ((65a98a50-10c8-441b-9b7a-65be37e7c70b)) for the OS
							  id:: 65a98a50-2591-4e33-8199-6549819f8422
							  collapsed:: true
								- OSTree
								  id:: 65a98a50-10c8-441b-9b7a-65be37e7c70b
									- Pros/Cons
										- Pros
											- Atomic upgrade/rollback 
											  id:: 65a98a50-5154-4a92-81c2-6929c03ca84b
											  AKA transactional upgrades
												- Non-atomic updates work by deleting the files underneath the running application and often breaks it, before replacing them with newer version
												- Easy rollbacks
													- [Simply select a previous version from the boot/grub menu](https://docs.fedoraproject.org/en-US/fedora-silverblue/updates-upgrades-rollbacks/#rolling-back)
												- Especially important since I experienced a broken upgrade in April 2022 trying to go from Kubuntu 21.10 to 22.04. Only solved via booting an older kernel via grub and triggering update again
											- It allows making installed packages persistent on immutable distributions by "layering" them on immutable images
										- Cons
										- Comparisons
											- ((65a98a50-10c8-441b-9b7a-65be37e7c70b)) vs ((63a9adc7-f569-4cfb-833e-aedf16f75606))
												- For ((65a98a50-10c8-441b-9b7a-65be37e7c70b))
													- Has some specific features with BTRFS, which is the default filesystem on Fedora
													- Nix never requiring shared libraries means core system packages can contain vulnerabilities due to their bundled dependencies not specifying updated versions
													- Compatible with standard Fedora packages, whereas Nix requires everything to be packaged specifically for their distro
												- For ((63a9adc7-f569-4cfb-833e-aedf16f75606))
													- Nix allows multiple versions of any package to be installed simultaneously
													- [OSTree hasn't got declarative configuration](https://github.com/coreos/rpm-ostree/issues/2326#issuecomment-1095480227)
												- Similarities
													- ((65a98a50-5154-4a92-81c2-6929c03ca84b))
									- Coomands
										- `rpm-ostree install lutris`
										- `rpm-ostree rollback`
										- `rpm-ostree status -v` can detail what layered packages you have installed
										- ((67829180-e165-45a0-b29b-79424c33b4a0))
									- Ostree is probably the best package manager (if you can call it that) that I have used. Managed to painlessly update to the latest fedora beta and then rollback to the stable release after with no issues.
									- [OSTree was built by looking at the atomic upgrades system of Nix](https://blog.verbum.org/2013/08/26/ostree-v2013-6-released)
							- Immutable system
							  id:: 65a98a50-56e1-4b11-b1ba-3b6943af6bb7
								- read-only root file system, like android, so apps work in a container or a virtualized environment, which gives additional protection against malware, since they can't access your system files
						- # Documentation
							- enable fedora rpm-fusion as a repository to allow for proprietary firmware
							  collapsed:: true
								- [https://rpmfusion.org/](https://rpmfusion.org/)
								- [https://docs.fedoraproject.org/en-US/quick-docs/setup_rpmfusion/](https://docs.fedoraproject.org/en-US/quick-docs/setup_rpmfusion/)
							- RPM Fusion (needed for proprietary packages)
							  collapsed:: true
								- https://rpmfusion.org/Configuration
								- https://discussion.fedoraproject.org/t/simplifying-updates-for-rpm-fusion-packages-and-other-packages-shipping-their-own-rpm-repos/30364/23
							- [toolbx](https://containertoolbx.org/)
							  id:: 63a9adc7-b9eb-401b-be40-5f8836b86618
							  collapsed:: true
							  Use [Toolbox](https://docs.fedoraproject.org/en-US/fedora-silverblue/toolbox/) (being renamed to toolbx) for non-Flatpak software
								- 1
								  collapsed:: true
									- You're "supposed" to use containers with the toolbox command, which is just calls podman, mounts your $HOME into the container, and sets --network=host.
									- For the last 6 months, I have only had a few packages overlayed. Libvirt/qemu and sway. You can actually run qemu in user mode in a toolbox if you dont need the fancy networking of libvirt.
									- Overlay is always last resort
								- Integration with ((63209272-1088-4824-a762-4ac7ded04b0a))
								  [https://github.com/owtaylor/toolbox-vscode](https://github.com/owtaylor/toolbox-vscode)
								- There is a simple Python tool [here](https://github.com/A6GibKm/silverblue-tools) that will automate exporting GUI apps from toolbox to your host OS.
								- Toolbox uses the following technologies:
									- [OCI container images](https://www.opencontainers.org/)
									- ((631219e3-ce87-482f-a283-a8cb0f8b23f5))
									  id:: 630f96e4-5e58-4e74-a426-28a3f13612d9
							- Alternative to ((63a9adc7-b9eb-401b-be40-5f8836b86618)) with better non-Fedora support
								- [Distrobox](https://distrobox.it/)
								  id:: 63a9adc7-c031-4dc6-a162-c91f04da953c
								  collapsed:: true
									- Pros/Cons
										- Pros
											-
										- Cons
											- Lacks
												- [Option to not use HOME](https://github.com/89luca89/distrobox/issues/1067)
												- [Distrobox snapshot](https://github.com/89luca89/distrobox/issues/1339)
												- [NixOS containers](https://github.com/89luca89/distrobox/issues/1604)
												- [[Suggestion] Integrate .desktop files in a more standard manner, similar to snaps, flatpak, nix etc · Issue #386 · 89luca89/distrobox · GitHub](https://github.com/89luca89/distrobox/issues/386#issuecomment-1263117365)
												- [Waydroid support](https://github.com/89luca89/distrobox/issues/725)
												- [[Suggestion] Use Polkit to launch applications from rootfull containers · Issue #1483 · 89luca89/distrobox · GitHub](https://github.com/89luca89/distrobox/issues/1483)
										- Unclear
											- Each container has direct access to your `HOME`
										- Upstream/Downstream Pros/Cons
										- Comparisons
											- ((63a9adc7-c031-4dc6-a162-c91f04da953c)) vs ((63a9adc7-b9eb-401b-be40-5f8836b86618))
											  collapsed:: true
												- For ((63a9adc7-c031-4dc6-a162-c91f04da953c))
													- [Lets you use original ISOs for distributions rather than having to modify them](https://youtu.be/Q2PrISAOtbY)
												- For ((63a9adc7-b9eb-401b-be40-5f8836b86618))
													-
												- Similarities
													-
												- Unclear
													- As a project, it is inspired by Container Toolbx (all the props to them!), but it aims to have broader compatibility with hosts and containers, without having to require a dedicated image to use in Distrobox.
													-
									- [Source](https://github.com/89luca89/distrobox)
									- # Documentation
										- Can install via homebrew or apt
											- Install `distrobox` via Homebrew
												- Homebrew
													- Note: Homebrew don't have a way to request packages, instead can submit PRs here https://docs.brew.sh/How-To-Open-a-Homebrew-Pull-Request
													- Formula = CLI tools
													- Casks = GUI apps
												- Distrobox
													- Layers for immutable distros have the issue that "it makes updates take longer". Is this because whenever a base image updates, the packages are redownloaded each time?
										- [[2025-02-14 Friday]] `sudo apt install distrobox`
											- [Rootless Podman](https://github.com/containers/podman/blob/main/docs/tutorials/rootless_tutorial.md#etcsubuid-and-etcsubgid-configuration)
												- `sudo apt install passt`
												- Swap `johndoe` with your username
													- `usermod --add-subuids 100000-165535 --add-subgids 100000-165535 johndoe`
														- ```
														  grep johndoe /etc/subuid /etc/subgid
														  /etc/subuid:johndoe:100000:65536
														  /etc/subgid:johndoe:100000:65536
														  ```
												- Verify
													- `podman run -it debian bash`
										- Adding `neofetch` to run in every Bash terminal opening on the host is a good way to differentiate it from a container
											- `nano .bashrc`
											- Add `neofetch` as a newline
												- or `fastfetch` actually is better these days
											- `source .bashrc` to reload
										- `--root` flag is used instead of `sudo` for operations
									- # [Commands](https://distrobox.it/usage/usage/)
									  collapsed:: true
										- Meta
											- Priority
												- ((67af5b22-9387-436a-85e9-8ae8b0c708fc))
												- ((67af5b22-92e9-48eb-aaa2-3b022bf2dd87))
										- [Outside the distrobox](https://distrobox.it/usage/usage/#outside-the-distrobox)
											- [distrobox-assemble](https://distrobox.it/usage/distrobox-assemble/)
											- [distrobox-create](https://distrobox.it/usage/distrobox-create/)
											  id:: 67af5b22-9387-436a-85e9-8ae8b0c708fc
												- e.g. `distrobox create -i ubuntu:20:04`
												- `-n` = set name
												- `-i`
													- [Container Distros list](https://github.com/89luca89/distrobox/blob/main/docs/compatibility.md#containers-distros)
														- ((65a98a50-a111-4380-99fe-e339481a29a5)) - `quay.io/toolbx/arch-toolbox:latest`
														- ((63c2a256-30fe-4cd5-a827-2f269b98b0c0)) - e.g. `quay.io/fedora/fedora-toolbox:41`
														- ((67828d01-9634-453e-a1bc-189c808e0bef)) - e.g. `ghcr.io/ublue-os/fedora-toolbox`
											- [distrobox-enter](https://distrobox.it/usage/distrobox-enter/)
												- e.g. `distrobox enter ubuntu-20-04`
												- Allows you to then e.g. `apt install <path-to-deb>`
											- [distrobox-ephemeral](https://distrobox.it/usage/distrobox-ephemeral/)
											- [distrobox-list](https://distrobox.it/usage/distrobox-list/)
											- [distrobox-rm](https://distrobox.it/usage/distrobox-rm/)
											- [distrobox-stop](https://distrobox.it/usage/distrobox-stop/)
											- [distrobox-upgrade](https://distrobox.it/usage/distrobox-upgrade/)
												- `distrobox-upgrade -a` = upgrade all
											- [distrobox-generate-entry](https://distrobox.it/usage/distrobox-generate-entry/)
										- [Inside the distrobox](https://distrobox.it/usage/usage/#inside-the-distrobox)
											- [distrobox-export](https://distrobox.it/usage/distrobox-export/)
											  id:: 67af5b22-92e9-48eb-aaa2-3b022bf2dd87
												- `distrobox-export --app gedit`
													- Create a `.desktop` file on host desktop
														- Useful for running GUI applications
												- Distrobox has a built-in way to export apps you installed in the container to your graphical host environment, for instance distrobox-export --app texstudio will allow you to run your containerized texstudio from your graphical application dash. As far as I can tell, this needs to be done manually if using toolbox.
											- [distrobox-host-exec](https://distrobox.it/usage/distrobox-host-exec/)
											- [distrobox-init](https://distrobox.it/usage/distrobox-init/)
									- Uses [Podman](((631219e3-ce87-482f-a283-a8cb0f8b23f5))) (other Logseq) or Docker to create containers using any Linux distro
									- # Ecosystem
										- [apx package manager](https://github.com/Vanilla-OS/apx)
										  id:: 65a98a50-83c1-4846-a887-24b8d60e0d14
											- Built by ((63a9adc7-c031-4dc6-a162-c91f04da953c)) dev, and powered by ((63a9adc7-c031-4dc6-a162-c91f04da953c))
											- Can install packages from Nix, apt, dnf, yay, apk, zyppr, and xbps
										- GUIs
											- Flatpak
												- [DistroShelf](https://github.com/ranfdev/DistroShelf)
												- [GitHub - Dvlv/BoxBuddyRS: A Graphical Interface for Distrobox](https://github.com/Dvlv/BoxBuddyRS)
												- [GitHub - DenysMb/Kontainer: A Kirigami Distrobox GUI](https://github.com/DenysMb/Kontainer)
												-
									- [Learning Resources]
										- [How I use distrobox on Fedora Silverblue](https://youtu.be/Q2PrISAOtbY)
											- He has `CTRL + ALT + Y` to launch a terminal for the host system
												- Mainly for `rpm-ostree` or `flatpak`
											- He has `CTRL + ALT + T` for Fedora toolbox, which is the same OS as his host
											- `CTRL + ALT + U` for Ubuntu toolbox
											-
										- [Run Distrobox on Fedora Linux - Fedora Magazine](https://fedoramagazine.org/run-distrobox-on-fedora-linux/)
										- [Distrobox Is Basically A Linux Subsystem For Linux - YouTube](https://youtu.be/FhW-3PPldAg)
										- https://discuss.techlore.tech/t/refusing-to-use-signal-as-an-unverified-flatpak-linux/15713 example of using an Ubuntu Distrobox for one app
									- Related:
										- ((63a9adc7-fc79-4fa3-8ca5-925a17291c26))
							- [https://docs.fedoraproject.org/en-US/fedora-silverblue/_attachments/silverblue-cheatsheet.pdf](https://docs.fedoraproject.org/en-US/fedora-silverblue/_attachments/silverblue-cheatsheet.pdf)
							- you can also choose to install them in a toolbox/distrobox or just layer them over Silverblue (with ((65a98a50-10c8-441b-9b7a-65be37e7c70b)) ).
						- Reviews
							- Had to give steam some extra filesystem permissions with flatseal, which is probably fairly un-intuitive for less advanced users. Very few packages did I need to layer (latte-dock, breeze-gtk, ffmpeg, mozilla-h264, steam-devices, yakuake). I tried to play with Waydroid in a toolbox container but found that podman had no access to binderfs devices in the kernel - this was a red flag for my later attempt to try this for my Workstation.
							- Not having OSTree updates appearing in Plasma Discover is a shame, but it looks like that work is happening upstream
						- Related:
							- ((63c2a256-30fe-4cd5-a827-2f269b98b0c0))
					- Korora
					  collapsed:: true
					  GNU version
						- https://kororaproject.org/
					- Redhat
					  Commercial paid version, based on Fedora
					- CentOS
					  Community version of Redhat (without support, cost etc) | killed
					- Nobara
					  id:: 65a98a50-0731-4784-800c-6d449b3ab3cb
					  collapsed:: true
						- [https://nobaraproject.org/](https://nobaraproject.org/)
						- Currently, below is a list of fixes applied on top of Fedora 35:
							- Bug fixes and gaming-oriented updates:
								- kernel patched with futex2
								- kernel patched with fsync compatibility
								- kernel patched with winesync
								- kernel patched with cherry-picked zen patches
								- kernel patched with OpenRGB
								- kernel patched with AMD CPCC
								- kernel patched to enable amdgpu for pre-polaris cards by default instead of radeon
								- kernel patched with steam deck support
								- kernel configured with ashmem, binder, and android support for Waydroid
								- mesa-git provided for AMD/Intel drivers instead of latest release, built and updated regularly (every few weeks to a month on average)
								- glibc patched with clone3 disabled (fixes CEF compatibility in applications using outdated CEF such as Discord, Steam beta)
								- openal version updated (fixes CSGO intro video crash)
								- gst-editing-services disabled — causes WINE to hang when creating new prefixes
								- libusb fix for high CPU usage when using xow/xone wireless xbox controller service: https://github.com/medusalix/xow/issues/141
								- lspci symlink from /usr/sbin/lspci to /usr/bin/lspci for ((64e9e733-aa9c-4bda-9605-56045896e07a)) : https://www.gamingonlinux.com/forum/topic/2766/post_id=17381
								- edk2 patched to fix VFIO issue https://github.com/tianocore/edk2/commit/ee1f8262b83dd88b30091e6e81221ff299796099
								- xone xbox wireless usb dongle kernel module packages installed (the firmware requires lpf, please see notes at the bottom)
								- gamescope version regularly updated
								- goverlay version regularly updated
								- mangohud version regularly updated
								- vkbasalt version regularly updated
							- General usage improvements:
								- yumex-dnf provided as frontend GUI for managing packages
								- nvidia gpu detection and driver auto-installation
								- SELinux disabled for performance
								- rpmfusion repos enabled by default
								- 64 and 32 bit WINE dependencies including winetricks and gstreamer installed for hassle-free out of the box Lutris + WINE gaming
								- Steam installed by default
								- Lutris installed by default
								- libreoffice installed by default
								- cups/printer drivers installed by default
								- kdenlive installed by default for video editing
								- obs-studio patched with browser plugin
								- obs-studio patched with vulkan and opengl game capture support (AMD/Intel only unfortunately. Nvidia’s driver is missing the required Vulkan extension)
								- obs-studio patched with HEVC vaapi encoding support (NOTE: encoder requires mp4 container format)
								- obs-studio capable of both nvenc and H264 vaapi encoding.
								- blender built with ffmpeg support (allows H264 render output)
								- flatpak flathub repository enabled by default
								- 1 Backlink
									- See [General usage improvements:](https://workflowy.com/#/1adc276ce2a2)
						- 1 Backlink
							- See [Nobara](https://workflowy.com/#/a03d5e2f737b) - security and gaming enhancements
				- ### Immutable Distributions
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Can test it on separate PC like desktop
						- Cons
							- https://pointieststick.com/2025/10/25/kde-linux-deep-dive-package-management-is-amazing-which-is-why-we-dont-include-it/
								- Many command-line tools exist but they have to be installable via ((65a9a686-82da-428a-ae22-170fcbe25a2e)), ((63a9adc7-f569-4cfb-833e-aedf16f75606)) or containers e.g. ((63a9adc7-c031-4dc6-a162-c91f04da953c))
								- Drivers and support packages for hardware
						- Unclear
						- Comparisons
					- ((65a98a50-c3d9-4680-9f69-f7c723cc6a21))
					- ((671d6a81-1dc1-4cce-934b-8e8786d9bcef))
					- ((6735f955-d80b-43f6-9bcb-648c61d7920c))
				- ### [OpenSUSE](https://www.opensuse.org/) (RPM)
				  id:: 65a98a50-68e7-4c00-8f07-2b3a7ffdbcf9
				- ### ((65a98a50-a111-4380-99fe-e339481a29a5))-based (tar)
					- [Arch](https://archlinux.org/)
					  id:: 65a98a50-a111-4380-99fe-e339481a29a5
					  collapsed:: true
						- Arch linux etc tips
						  collapsed:: true
							- [quote='Rawmeo' pid='1565977' dateline='1494130625']
							- I am using Arch Linux for all my daily needs - the last time I touched Windows was 2 months ago when I forgot my laptop and my wife lended me hers.
							- Now for the sad part: Arch requires a tutorial for the first-time install, but it is easier than we think. This is the tutorial that I've used:
							- http://www.brandonkester.com/tech/2014/03/16/full-disk-encryption-in-arch-linux-with-uefi.html
							- If you want real privacy, here's how it works.
							- 1) Install Arch Linux with a desktop environment (KDE is the best IMO) with [b]full disk encryption[/b] (as per the above tutorial, it needs to be done at install time)
							- 2) Delete ~/.bash_history and make it a symbolic link to /dev/null
							- 3) Disable Akonadi (KDE) or Zeitgeist (GNOME)
							- 4) Install Firejail and run "sudo firecfg" to make all your apps run inside the Firejail sandbox
							  id:: 65a98a50-df5f-4985-9260-8352b7d4018a
							- 5) If using KDE, configure Klipper to limit history to 1 item (in System Settings)
							- If you want to be even more hardcore:
							- 5) Configure a VPN in NetworkManager and make it connect at startup
							- 6) Run your sensitive shit in a VM inside an encrypted LUKS / VeraCrypt / etc. volume
							- 7) Have a script validate the checksum of the files in your /boot partition every time you open your encrypted volume (easy to code)
							- 8) If your OCD kicks in, use Secure Boot, you'll need the PreLoader.efi file here:
							- https://blog.hansenpartnership.com/linux-foundation-secure-boot-system-released/
							- So in short, I think Ubuntu is good for beginners, but when you become more advanced, you realize that Ubuntu kinda sucks. Real privacy advocates use Kali, Arch, or Tails (amnesic live OS). I personally use Arch because I can save all my documents on my persistent hard drive and do all of my daily tasks without any problem.
					- Manjaro
					  collapsed:: true
					  More user-friendly version of Arch
						- Manjaro is the ideal distribution for people who like the simple, cutting edge philosophy of Arch Linux, but who would like to set up the operating system with a couple of clicks and have settings adjustable through a friendly point-n-click interface. Manjaro has most of the same capabilities of Arch, but with a friendly wrapper which makes installing and working with software packages a quick, click-and-done process."
						- Rolling Release
							- Manjaro uses a Rolling Release Development Model, whereby rather than being replaced, the same core system will instead be continually updated and upgraded. As such, it is not – nor will it ever be – necessary to re-install a later release of Manjaro in order to enjoy the very latest and most up-to-date system possible. By virtue of keeping an existing installation updated, it is already the latest release.
						- The updates are delayed by a few weeks
							- Manjaro takes most of the risk out of the rolling model by delaying the release of new applications and features for several weeks. Once they’re tested and proved safe, they’re made available, but things can slip through the net.
					- Antergos
					  collapsed:: true
					  GNU libre version of Arch
						- https://antergos.com
						- Apparently more beginner friendly too
					- Parabola
					  Libre version of Arch Linux)
					- [SteamOS](https://store.steampowered.com/steamos/)
					  id:: 671d6a81-1dc1-4cce-934b-8e8786d9bcef
					  collapsed:: true
					  v3 (2022) is an immutable distro built on ((65a98a50-a111-4380-99fe-e339481a29a5)), previously since 2013 built on ((65a98a51-38a0-4772-9fbb-0fffadc84dfd))
						- There isn't a ((65a98a50-2591-4e33-8199-6549819f8422)) equivalent to make reinstalling packages after each OS update easier?
						- Related:
							- ((67828d01-9634-453e-a1bc-189c808e0bef))
							- [Bazzite](https://bazzite.gg/)
							  id:: 671d6a81-feca-42b1-b68c-30c58d4c6f84
							  Built on ((671b6e25-ba39-4d7d-b20e-1f12303488ca)), immutable, rpm-ostree layers
							- HoloISO
					- [KDE Linux](https://community.kde.org/KDE_Linux)
					  id:: 6735f955-d80b-43f6-9bcb-648c61d7920c
					  collapsed:: true
					  Immutable. Intended to replace ((65a98a50-43eb-4865-b8d4-3b9ba7b7f6e0))
						- [KDE Linux - KDE Community Wiki](https://community.kde.org/KDE_Linux#Architecture)
						- ((65f58f8e-1860-4087-b0f5-a9ef34dbb9b7))
				- ### [ReactOS](https://reactos.org/)
				  Reimplementation of ((66a98a52-9772-4779-9956-4684637041b1))
				- ### Security-focused
					- [Qubes OS](https://www.qubes-os.org)
					  id:: 635037c3-993a-4bfc-9c65-2157fd59a626
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Pros
								- Great security and compartmentalisation
							- Cons
								- High battery usage on a laptop
								- Hardware acceleration tasks like watching video and playing games are not possible
									- [https://www.qubes-os.org/faq/#can-i-run-applications-like-games-which-require-hardware-acceleration](https://www.qubes-os.org/faq/#can-i-run-applications-like-games-which-require-hardware-acceleration)
									- basic tasks such as (non-HD) video display maxes out a single CPU core on a laptop
								- No hibernate
								  [https://github.com/QubesOS/qubes-issues/issues/2414#issuecomment-774674741](https://github.com/QubesOS/qubes-issues/issues/2414#issuecomment-774674741)
								- Slower performance compared to other distros
						- Hardware certification requirements
						  collapsed:: true
						  [https://www.qubes-os.org/doc/certified-hardware/](https://www.qubes-os.org/doc/certified-hardware/)
							- _Mandatory_
								- open-source boot firmware (aka “the BIOS”), such as coreboot
									- Another important requirement is that Qubes-certified hardware should run only open-source boot firmware (aka “the BIOS”), such as coreboot. The only exception is the use of (properly authenticated) CPU-vendor-provided blobs for silicon and memory initialization (see Intel FSP) as well as other internal operations (see Intel ME). However, we specifically require all code used for and dealing with the System Management Mode (SMM) to be open-source.
									- While we recognize the potential problems that proprietary CPU-vendor code can cause, we are also pragmatic enough to realize that we need to take smaller steps first, before we can implement even stronger countermeasures such as a stateless laptop. A switch to open source boot firmware is one such important step. To be compatible with Qubes OS, the BIOS must properly expose all the VT-x, VT-d, and SLAT functionality that the underlying hardware offers (and which we require). Among other things, this implies proper DMAR ACPI table construction.
								- No built-in USB-connected microphones, only PCIe
									- Finally, we require that Qubes-certified hardware does not have any built-in USB-connected microphones (e.g. as part of a USB-connected built-in camera) that cannot be easily physically disabled by the user, e.g. via a convenient mechanical switch. Thankfully, the majority of laptops on the market that we have seen already satisfy this condition out-of-the-box, because their built-in microphones are typically connected to the internal audio device, which itself is a type of PCIe device. This is important, because such PCIe audio devices are — by default — assigned to Qubes’ (trusted) dom0 and exposed through our carefully designed protocol only to select app qubes when the user explicitly chooses to do so. The rest of the time, they should be outside the reach of malware.
							- _Recommended_
								- While we also recommend a physical kill switch on the built-in camera (or, if possible, not to have a built-in camera), we also recognize this isn’t a critical requirement, because users who are concerned about it can easily cover it a piece of tape (something that, regrettably, is far less effective on a microphone).
								- Similarly, we don’t consider physical kill switches on Wi-Fi and Bluetooth devices to be mandatory. Users who plan on using Qubes in an air-gap scenario would do best if they manually remove all such devices persistently (as well as the builtin speakers!), rather than rely on easy-to-flip-by-mistake switches, while others should benefit from the Qubes default sandboxing of all networking devices in dedicated VMs.
						- Qubes
						  collapsed:: true
							- Qubes potential VMs
								- You might take it as far as to have every application in its own VM. Beyond the template VMs, you might have:
									-
										- sys-net for the networking drivers
										- sys-usb for USB drivers
										- sys-firewall
										- sys-whonix as your Tor gateway
										- sys-corridor as a Tor-only firewall
										- A disposable VM for browsing in Tor
										- A disposable VM for opening downloaded files
										- A VM for online accounts where you are known by name (shopping)
										- A VM for high risk accounts where you are known by name (banking, taxes)
										- A VM for anonymous online accounts (more if you have multiple pseudonymous identities)
										- A VM for working offline
										- A VM for a password manager, PGP keys, other sensitive local data
										- A VM for email, maybe several for different accounts
										- A VM for messaging friends
										- VMs for any experiments or coding, stuff you want to try out
										- A VM for games or other untrusted/proprietary code
							- Unlikely to see as much progress on the open-source version in the future as they are focusing on commercial clients/features because they've run out of funds
							- https://www.qubes-os.org/news/2016/11/30/qubes-commercialization/
							- Qubes air-gap VMs (don't assign a network interface to a domain)
						- Base OS: Qubes for security [404 Not Found | Qubes OS](https://www.qubes-os.org/doc/SimpleIntro/)
						  collapsed:: true
							- Basically it runs groups of apps/storage/USB/network etc in VMs which means that all attacks cannot affect your whole system
							- Next up: Whonix for anonymity. It runs Tor in two VMs which means DNS leaks are impossible https://www.whonix.org/wiki/Comparison_with_Others
							- Qubes+Whonix is the most secure combination against remote attacks and here's how to setup https://www.whonix.org/wiki/Qubes
							- However this means you don't get the amnesic advantage of Tails vs local attacks
							- Solution: setup the option to temporarily render your encrypted HDD inaccessible via an additional 'nuke' password https://www.kali.org/tutorials/emergency-self-destruction-luks-kali/
							- This allows you to enter a different password to deletes your keyslots rather than decrypt your device
							- You can also backup these keyslots somewhere else (in an anonymous and encrypted form) to later decrypt the HDD
							- Qubes offers better security even without the hardware requirements e.g. GUI isolation and kernel protection
						- [https://www.whonix.org/wiki/Qubes](https://www.whonix.org/wiki/Qubes)
						- Higher security through compartmentalised VMs for each group of apps
						  collapsed:: true
							- ********* Compartmentalised apps
								- http://theinvisiblethings.blogspot.com/2011/04/linux-security-circus-on-gui-isolation.html
							- ********* Different colour menu bar for each security level
								- https://www.qubes-os.org/doc/QubesScreenshots/
							- ********* http://theinvisiblethings.blogspot.com/2012/09/how-is-qubes-os-different-from.html
							- ********* Qubes+Whonix > Whonix Physical Isolation?
								- http://invisiblethingslab.com/resources/2014/Software_compartmentalization_vs_physical_separation.pdf
								- How to setup physical isolation
								- https://www.whonix.org/w/index.php?title=Dev/Build_Documentation/Physical_Isolation/11&redirect=no#Warnings
								- How to setup Whonix on Qubes
								- https://www.whonix.org/wiki/Qubes
						- Setup
						  collapsed:: true
							- http://www.rationallyparanoid.com/articles/qubes.html
							- https://thetinhat.com/blog/2014/07/24/qubes.html
						- Qubes Pros/Cons
						  collapsed:: true
							- Pros
								- Better than Tails as each VM can have a separate Tor circuit
								- Allows easy switching between OS's to test + move files
							- Cons
								- Apps which can't be used fully
									- Launchy
									- ManicTime
									- TeamViewer
									- CrashPlan
										- See [CrashPlan](https://workflowy.com/#/03f7394dbb03)
										  #Software
										- Have to turn off VMs to backup https://www.qubes-os.org/doc/BackupRestore/
										- _use rsync from within each container _**to a VPS of my own**
										- Split up Linux.iso into several VMs as I have to turn them off completely to backup to HDD
									- Clam Sentinel
									- f.lux?
									- VeraCrypt?
										- ********* Steganographic containers
											- ********** Workaround
												- *********** Have one TrueCrypt container each per VM
													- May take longer to start up PC and for backups though
								- Deniable encryption on Qubes?
									- https://www.qubes-os.org/mailing-lists/
									- tonyinfinity@tutanota.com
									- TheReality123
									- https://groups.google.com/forum/#!topic/qubes-devel/BbjHaBwDdtA
									- https://github.com/QubesOS/qubes-issues/issues/2402
						- Persistence
						- https://www.qubes-os.org/doc/software-update-vm/
						- Combat BadUSB [http://arstechnica.com/security/2014/07/this-thumbdrive-hacks-computers-badusb-exploit-makes-devices-turn-evil/](http://arstechnica.com/security/2014/07/this-thumbdrive-hacks-computers-badusb-exploit-makes-devices-turn-evil/)
						- _Related:_
						  collapsed:: true
							- See [Hardware Virtualisation](https://workflowy.com/#/1b2f8b388e7a)
							  #SysAdmin
							- [[Videogames]] : ((632d02a5-3d25-4d59-ad01-8c9e856dc060))
					- [Subgraph OS](https://subgraph.com/)
					- Spectrum OS
					  collapsed:: true
						- [https://spectrum-os.org/](https://spectrum-os.org/)
						- [https://forum.qubes-os.org/t/spectrum-os-discussion/1531](https://forum.qubes-os.org/t/spectrum-os-discussion/1531)
				- [NixOS](https://nixos.org/)
				  id:: 63a9adc7-fc79-4fa3-8ca5-925a17291c26
				  collapsed:: true
					- collapsed:: true
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Reproducible
							  collapsed:: true
								- Nix has a mechanism that ensures, that your packages are always build in the same way. This means that you can easily move your packages between different machines. So your work station and your laptop can share your customized operating system environment. Since these environments are identical, errors that only occur on one machine are prevented.
								- In June 2021 became fully reproducible
								  source:: [https://news.ycombinator.com/item?id=27573393](https://news.ycombinator.com/item?id=27573393)
							- Reliable
							  collapsed:: true
								- Nix allows you to install multiple versions of the same packages. This ensures that packages are installed without breaking other already installed packages. Also, due to the fact that Nix arranges files in a similar way to Git, you can always roll back to previous versions.
							- Up-to-date
							  collapsed:: true
								- The nixpkgs repository is the most up-to-date package repository. It has more "newest packages" than Debian unstable, Fedora and even the AUR! ([https://repology.org/repositories](https://repology.org/repositories))
							- Declarative
							  collapsed:: true
								- No more apt/dnf install. Declare your whole operating system in a single config file and Nix will install all your packages automatically. This means that you can share your riced desktop environment with your friends / community and they will have your environment up and running within minutes.
							- the functional nature of Nix leads to the possibility of multiple working environment, with each distinctive set of applications and tools, and the ability of *switching cleanly* between them. Those who use [nvm](https://github.com/nvm-sh/nvm) (for Node.js) or [virtualenv](https://virtualenv.pypa.io) (for Python) probably can appreciate this
						- Cons
							- No curated distro flavour
							  collapsed:: true
								- Is there any equivalent to a curated Fedora/Ubuntu? A NixOS-based distro or metarepo of configs perhaps?
								   [https://teddit.totaldarkness.net/r/NixOS/comments/uk9xnr/is_there_any_equivalent_to_a_curated_fedoraubuntu/](https://teddit.totaldarkness.net/r/NixOS/comments/uk9xnr/is_there_any_equivalent_to_a_curated_fedoraubuntu/)
									- I currently use Fedora because they keep on top of new trends like Pipewire, Wayland, etc and update the packages based on that.
									- I'm not particularly technical so I'd like to be able to subscribe in some way to something that'll update my config and make those changes for me, swapping to new technologies, software versions and forks when necessary without me having to read any tech news myself.
									- Failing that it'd be good to at least find a source of many peoples currently updated configs that I could use for my own.
								- Comments
									- A meta-repo is a good idea, this is the only thing I am aware of: [https://nixos.wiki/wiki/Comparison_of_NixOS_setups](https://nixos.wiki/wiki/Comparison_of_NixOS_setups)
										- Here are dots I like:
										- Xe: [https://github.com/Xe/nixos-configs](https://github.com/Xe/nixos-configs)
										- srid: [https://github.com/srid/nixos-config](https://github.com/srid/nixos-config)
										- balsoft: [https://github.com/balsoft/nixos-config](https://github.com/balsoft/nixos-config)
										- and mine, which are user agnostic, and provisioned with some management tools, and set up to template: [https://github.com/dmadisetti/.dots](https://github.com/dmadisetti/.dots)
							- Has Flatpak support, but not Snap
							  collapsed:: true
								- Flatpak
									- Enable the service by adding `services.flatpak.enable = true;` to your `configuration.nix`
								- No Snap support
								  [https://github.com/NixOS/nixpkgs/issues/30336#issuecomment-1113091385](https://github.com/NixOS/nixpkgs/issues/30336#issuecomment-1113091385)
							- 20 years old, could be rearchitected from scratch in a simpler way
							- Lacks
								- [There isn't a clear canonical way to refer to a specific package version. · Issue #93327 · NixOS/nixpkgs · GitHub](https://github.com/NixOS/nixpkgs/issues/93327#issuecomment-1644327458) though devbox seems to do it
								-
								- [nixos-assimilate - Turn currently running system into NixOS · Issue #2079 · NixOS/nixpkgs · GitHub](https://github.com/NixOS/nixpkgs/issues/2079#issuecomment-1024562765)
								- [Screensharing support in Wayland with Chromium/Chrome (tracking issue) · Issue #91218 · NixOS/nixpkgs · GitHub](https://github.com/NixOS/nixpkgs/issues/91218#issuecomment-1742371629)
								- [SteamPlay Compatibility Tools: Proton-GE, Boxtron, Roberta, Luxtorpeda · Issue #73323 · NixOS/nixpkgs · GitHub](https://github.com/NixOS/nixpkgs/issues/73323#issuecomment-1527002950)
								-
						- See [OSTree comparison to Nix](https://workflowy.com/#/014e992a22c5)
					- Documentation
						- [https://github.com/NixOS/nixpkgs/](https://github.com/NixOS/nixpkgs/)
						- *Use on non-NixOS*
							- [Determinate Nix Installer](https://determinate.systems/posts/determinate-nix-installer)
							  id:: 65494793-ebbc-4fcb-bdc8-1a31b5561502
							  collapsed:: true
								- https://github.com/DeterminateSystems/nix-installer
							- [Nix Package Manager](https://nixos.org/guides/install-nix.html)
							  id:: 63a9adc7-f569-4cfb-833e-aedf16f75606
							  collapsed:: true
							  If installing a completely different OS seems like to much pain, you can also install the nix packager manager on any Linux distro
								- Pros/Cons
								  collapsed:: true
									- Pros
										- Can easily replace native installed packages like Steam
											- Installed Nix version of Steam will have the same config, cookies, etc as installed native Ubuntu Steam
									- Cons
										- [My current backup tool Borg saves symlinks as is, and not the underlying file](https://github.com/borgbackup/borg/issues/1003#issuecomment-831275626)
										  id:: 63ab39d6-5f6f-4bf0-aed8-4f958741ae09
								- The only disadvantage is that you can only install usersland programs and not the kernel itself.
								- You should be able to mess around with the nix package manager without breaking anything on your system. And you can easliy remove it buy just running `rm -r /nix`.
								- Installation
									- `sh <(curl -L [Not found](https://nixos.org/nix/install)) --daemon` for multi-user install
									  [source] [Download Nix / NixOS](https://nixos.org/download.html#download-nix)
									- *How to install packages*
										- Either
											- [NixOS Search](https://search.nixos.org/packages)
												- Click on `nix-env` method > on non-NixOS
										- Additional steps
											- Update env so that KDE app launchers can launch the app
											  id:: 63aadd38-1048-46c2-8cf8-de73036b46eb
											  collapsed:: true
												- [source] [Solved: Nix Package manager apps not showing in Gnome Application menu - YouTube](https://youtu.be/0eLLXh__BNY)
												- A better solution would be include the ~/.nix-profile/share directory into the XDG_DATA_DIRS environment variable. That way, Gnome (and other DEs) will look for the desktop file in the ~/.nix-profile/share/applications directory and there is no need to create symbolic links for them.
												- You can do that adding this line to you ~/.profile file:
												  `export XDG_DATA_DIRS="$HOME/.nix-profile/share:$XDG_DATA_DIRS"`
												- Note: may have to reboot each time I install a new application.
											- Sidenote: enable non-FOSS packages
											  collapsed:: true
												- ```
												  boss@boss-XPS:~$ nix-env -iA nixpkgs.microsoft-edge
												  installing 'microsoft-edge-stable-107.0.1418.52'
												  error: Package ‘microsoft-edge-stable-107.0.1418.52’ in /nix/store/ppy7bhb52mp9dq71akypl9jn05msg6cp-nixpkgs/nixpkgs/pkgs/applications/networking/browsers/microsoft-edge/browser.nix:187 has an unfree license (‘unfree’), refusing to evaluate.
												  
												         a) To temporarily allow unfree packages, you can use an environment variable
												            for a single invocation of the nix tools.
												  
												              $ export NIXPKGS_ALLOW_UNFREE=1
												  
												          Note: For `nix shell`, `nix build`, `nix develop` or any other Nix 2.4+
												          (Flake) command, `--impure` must be passed in order to read this
												          environment variable.
												  
												         b) For `nixos-rebuild` you can set
												           { nixpkgs.config.allowUnfree = true; }
												         in configuration.nix to override this.
												  
												         Alternatively you can configure a predicate to allow specific packages:
												           { nixpkgs.config.allowUnfreePredicate = pkg: builtins.elem (lib.getName pkg) [
												               "microsoft-edge-stable"
												             ];
												           }
												  
												         c) For `nix-env`, `nix-build`, `nix-shell` or any other Nix command you can add
												           { allowUnfree = true; }
												         to ~/.config/nixpkgs/config.nix.
												  (use '--show-trace' to show detailed location information)
												  
												  ```
											- `nano ~/.config/nix/nix.conf`
											  collapsed:: true
											  Enable flakes
												- ```
												  experimental-features = nix-command flakes
												  ```
												- Pros
													- Less verbose commands
													- Search for packages via terminal e.g. `nix search nixpkgs librewolf`
												- Installation method is still under `nix-env`, `non-NixOS` on the nixpkgs site
													- e.g. `nix-env -iA nixpkgs.librewolf`
									- How to uninstall Nix
										- [How to remove nix · Issue #1402 · NixOS/nix · GitHub](https://github.com/NixOS/nix/issues/1402#issuecomment-312496360)
								- File locations
									- `/home/boss/.config/nixpkgs/config.nix`
									- `/home/boss/.nix-profile/`
									  id:: 63ab0ff5-2d28-4b96-9745-f1a0365f4caa
									  collapsed:: true
										- By default this symlinked directory is `/nix/var/nix/profiles/per-user/boss/profile/` but `--switch-profile` can be used to change it to other dirs
											- ((63ab111f-ef91-430c-8d68-cae9071aeebd))
										- `/nix/var/nix/profiles/per-user/boss/profile/manifest.nix` = list of packages installed in that particular profile
										- `/home/boss/.nix-profile/share/applications` = application `.desktop` files
										- Limitation: ((63ab39d6-5f6f-4bf0-aed8-4f958741ae09)) means none of it is backed up
									- `/nix/store` = packages
								- Commands
									- Most important
										-
									- `nix-env -qaP` = see every package in NixPkgs
									- `nix-env -qaP firefox` = filter for only packages with `firefox` in the name
									- `nix-env -qaPs` = see the status of available packages
									  collapsed:: true
										- The first character (I) indicates whether the package is installed in your current user environment. The second (P) indicates whether it is present on your system (in which case installing it into your user environment would be a very quick operation). The last one (S) indicates whether there is a so-called substitute for the package, which is Nix’s mechanism for doing binary deployment. It just means that Nix knows that it can fetch a pre-built package from somewhere (typically a network server) instead of building it locally.
									- `nix-env -q` = see packages installed (imperatively by your user)
										- `sudo nix-env -q` = see packages installed (imperatively by root)
									- `nix-env -iA` = install a package
										- e.g. `nix-env -iA nixpkgs.subversion`
									- `nix-env -e` = uninstall a package
										- e.g.  `nix-env -e subversion`
									- `nix-env -u` = Upgrade all packages for which there are newer versions
									  id:: 63ab0e40-d874-4b19-ac28-b3106ceba34f
									- `nix-env -uA` = Upgrade a single package to a new version
										- e.g. `nix-env -uA nixpkgs.subversion`
									- `nix-env -u --dry-run` = Do a dry run (show what it would do without executing it) of ((63ab0e40-d874-4b19-ac28-b3106ceba34f))
									- `nix-env --switch-profile /nix/var/nix/profiles/default` = switch profile to the one stored here
									  id:: 63ab111f-ef91-430c-8d68-cae9071aeebd
									  collapsed:: true
										- If the profile doesn’t exist, it will be created
										  automatically. You should be careful about storing a profile in another
										  location than the `profiles` directory, since otherwise it might not be
										  used as a root of the [garbage collector](https://nixos.org/manual/nix/stable/package-management/garbage-collection.html).
										- Related: ((63ab0ff5-2d28-4b96-9745-f1a0365f4caa))
										- All `nix-env` operations work on the profile pointed to by
										  `~/.nix-profile`, but you can override this using the `--profile` option
										  (abbreviation `-p`):
											- `nix-env -p /nix/var/nix/profiles/other-profile -iA nixpkgs.subversion`
											- This will *not* change the `~/.nix-profile` symlink.
									- `nix-env --list-generations` = shows previous snapshots (new one created when you update versions of packages
									- `nix-env --rollback` = go back to a previous snapshot
									- `which` = find where the executable for the application is
									  collapsed:: true
										- e.g.
										  ```
										  $ which chromium
										  /home/boss/.nix-profile/bin/chromium
										  ```
									- [Garbage Collection](https://nixos.org/manual/nix/stable/package-management/garbage-collection.html)
									- [Learning Resources]
									  collapsed:: true
										- [Basic Package Management](https://nixos.org/manual/nix/stable/package-management/basic-package-mgmt.html)
							- [Home Manager](https://nix-community.github.io/home-manager/index.html)
							  id:: 63a9adc7-f2d9-45a9-bef8-df1a225f5a64
							  collapsed:: true
							  if you want to have a declarative configuration file on any non-nixos distro!
								- Pros/Cons
								  collapsed:: true
									- Pros
										- Declarative configuration for any distro, NixOS not required
										- Compartmentalises the hidden folders in /home/ so I can more easily revert apps back to previous state, and delete what's no longer needed
											- However Flatpak seems much better suited for this as it's already all organised
									- Cons
										- You can only manage your userland programs and not for example the kernel itself
										- One of the major things that attracted me to Nix was the idea of being able to track changes to my home directory's config files. It was explained to me as though your home directory would be built from a "skeleton" of configuration files, which once deployed were read-only, meaning that any change to your configuration would have to be tracked and rebuilt at the top level.
											- However it actually seems like
												- All your configuration files have to be translated into the syntax defined by whoever implemented the package.
												- Each package to be managed by home-manager requires dedicated support.
													- If you work on multiple distributions, you can't easily share the config files - maybe you could build them from Nix, but then you're not really working on multiple distributions at all.
													- It seems like files generated by home-manager aren't read-only. Maybe there's an option to make them so. (or maybe it's impossible, since you might have some controlled packages and some uncontrolled ones).
													- Some files (say .bashrc) will always require extensible config, using syntax that is not a part of nix. So it seems like you will have to embed non-nix languages in a nix file, implying loss of syntax highlighting and other standard text editing tools.
										- Lacks
											- [KDE/Plasma config management](https://github.com/nix-community/home-manager/issues/607#issuecomment-1234412328)
												- [GitHub - pjones/plasma-manager: Manage KDE Plasma with Home Manager](https://github.com/pjones/plasma-manager)
											- [Firefox configuration tracking issue (+Thunderbird?) · Issue #606 · nix-community/home-manager · GitHub](https://github.com/nix-community/home-manager/issues/606)
											- [declarative configurations of firefox extensions · Issue #4618 · nix-community/home-manager · GitHub](https://github.com/nix-community/home-manager/issues/4618)
											- https://github.com/nix-community/home-manager/issues/4618
											-
								- Links
									- [GitHub - nix-community/home-manager: Manage a user environment using Nix  [maintainer=@rycee]](https://github.com/nix-community/home-manager)
									- [https://nixos.wiki/wiki/Home_Manager](https://nixos.wiki/wiki/Home_Manager)
									- [https://rycee.gitlab.io/home-manager/](https://rycee.gitlab.io/home-manager/)
								- Documentation
									- Configuration options
										- [Home Manager - Option Search](https://mipmip.github.io/home-manager-option-search/)
										- [Appendix A. Configuration Options](https://nix-community.github.io/home-manager/options.html)
										- [Home Manager Manual](https://nix-community.github.io/home-manager/index.html)
										- [Enable searching Home Manager options from search.nixos.org · Issue #2297 · nix-community/home-manager · GitHub](https://github.com/nix-community/home-manager/issues/2297#issuecomment-1079698898)
									- My `home.nix`
									  id:: 63ab465b-2840-49fa-9e73-3d327896e9c0
									  collapsed:: true
										- **Issues**
											- Steam doesn't start?
												- `programs.steam` option [unavailable here](https://nix-community.github.io/home-manager/options.html), but [it should be in NixOS](https://github.com/NixOS/nixpkgs/issues/108598)
											- ((649b1463-b077-434e-a501-df6e30d6c4fb)) flatpak doesn't launch via Lutris?
										- Additional notes
											- `pkgs.adb`
											  collapsed:: true
												- ADB & Fastboot
												  collapsed:: true
												  `sudo apt-get install adb fastboot -y`
													- What is it
													  collapsed:: true
														- ADB or Android Debug Bridge
														  collapsed:: true
															- is a command line utility that let’s us control an android device from the computer itself. It’s part of Google Android SDK & can be used to run shell commands or to copy the files to & from the device & also to install or remove the applications from device.
														- Fastboot
														  collapsed:: true
															- is basically a diagnostics mode that is used to modify the Android file system from computer when the android device is in bootloader mode. It’s an alternative to recovery mode & is normally used to perform updates or to perform installations.
													- sudo apt-get install android-tools-adb android-tools-fastboot -y
													- Start
													  collapsed:: true
													  $ sudo adb start-server
														- After installation the ADB server will start on its but if that’s not the case than you can start the ADB server using ,
													- To stop the ADB server
													  sudo adb kill-server
													- Once the USB Debugging has been enabled, connect the android device to system using the USB cable.
													  collapsed:: true
														- Now open the terminal and execute the following command,
														  adb devices
														- Upon the command execution you will get a pop-up on your Android device to allow USB Debugging, press OK to enable the debugging. Now execute the same command mentioned above & we should than see our device in list output.
														- Note : If getting any permissions regarding error after connecting the device than restart the ADB server & try again.
											- `pkgs.docker`
											  collapsed:: true
												- ((639cbbe9-520c-489d-ad23-89efe064a4a7)) - currently for ArchiveBox, Baserow (see Yakuake script for more info)
											- `pkgs.earlyoom`
											  collapsed:: true
												- earlyoom
												  `sudo apt install earlyoom`
													- [Default on Fedora](https://fedoraproject.org/wiki/Changes/EnableEarlyoom)
													- https://github.com/rfjakob/earlyoom
													- When free RAM and swap less than 10%, kills the process consuming the most memory
													- Irrelevant - swap space is sufficient
											- `pkgs.firejail`
											  collapsed:: true
												- ((638e7c16-bf56-4a7b-b7d5-fa1f8a2465ea))
											- `pkgs.git`
											  collapsed:: true
												- `git` not from APT, instead from PPA
													- Standard apt git doesn't seem to include `git subtree`
													- https://git-scm.com/download/linux
													  ```
													  sudo add-apt-repository ppa:git-core/ppa
													  ```
											- `pkgs.google-chrome`
											  collapsed:: true
												- ((649b140b-e8b8-400f-9c44-ce2a5945295d))
												  collapsed:: true
											- `pkgs.logiops`
											  collapsed:: true
												- [LogiOps](https://github.com/PixlOne/logiops)
												  id:: 6491d6ad-96b3-4fad-a680-7c854739aea6
													- [How to install and configure PixlOne's logid to program Logitech MX Master 3 buttons on Linux.  · GitHub](https://gist.github.com/johnathanmay/77e8cfefda6744dca39cb1311bdf741a)
													- Related: ((6491d46e-dd71-44cf-bbad-9acaa102bf3e))
											- `pkgs.piper`
											  collapsed:: true
												- piper
													- Controlling Logitech G502 gaming mouse
													- [https://github.com/libratbag/piper](https://github.com/libratbag/piper)
													- Comes with libratbag (backend for GUI app piper)p
													  [https://github.com/libratbag/libratbag](https://github.com/libratbag/libratbag)
											- `pkgs.puddletag`
											  collapsed:: true
												- ((639cbbe9-df12-41c2-8cea-29db96fbeda9))
												  `sudo apt install puddletag`
											- `pkgs.scrcpy`
											  collapsed:: true
												- ((63a9ade4-0cdf-4680-a839-6b6f92e57f51))
											- `pkgs.signal-desktop`
											  collapsed:: true
												- See [Signal](https://workflowy.com/#/626a051be085)
												  #EncryptedChat
											- `pkgs.simplescreenrecorder`
											  collapsed:: true
												- SimpleScreenRecorder (alternative to Camtasia for screen recording)
												  collapsed:: true
												  `sudo apt install simplescreenrecorder -y`
													- Screen recording alternatives
													  id:: 65a98a50-3f8a-4913-bf62-495110f898aa
														- Kazam
														- https://alternativeto.net/software/simplescreenrecorder/?platform=linux
														  collapsed:: true
															- Deepin
															- Green Recorder
															- ScreenStudio
															- Krut
														- ### FOSS
															- OBS Studio (Open Broadcaster Software)
															  id:: 663a5797-a9ea-4d4e-9619-01250a7ea8a6
															  collapsed:: true
																- Links
																  collapsed:: true
																	- [https://obsproject.com/](https://obsproject.com/)
																	- [[Page not found · GitHub](https://github.com/obsproject/obs-studio](https://github.com/obsproject/obs-studio))
																	- [https://opencollective.com/obsproject](https://opencollective.com/obsproject)
																- Installation
																  collapsed:: true
																  [https://obsproject.com/wiki/install-instructions#linux](https://obsproject.com/wiki/install-instructions#linux)
																	- Flatpak
																	- Old
																	  collapsed:: true
																		- `sudo apt install ffmpeg`
																		- If you want virtual camera support you need v4l2loopback-dkms installed
																		  sudo apt install v4l2loopback-dkms
																		- sudo add-apt-repository ppa:obsproject/obs-studio
																		- sudo apt update
																		- sudo apt install obs-studio
																- Documentation
																  collapsed:: true
																	- Virtual camera support requires an additional package
																	  sudo apt install v4l2loopback-dkms
																	- Noise Suppression can be activated by right-clicking the microphone > Filters > Noise Suppression > RNNoise
																	  [https://obsproject.com/wiki/Filters-Guide#noise-suppression](https://obsproject.com/wiki/Filters-Guide#noise-suppression)
																- See [General usage improvements:](https://workflowy.com/#/1adc276ce2a2)
																- [https://www.ghacks.net/2019/10/10/obs-studio-open-source-video-recorder-and-streaming-app-for-windows-linux-and-macos/](https://www.ghacks.net/2019/10/10/obs-studio-open-source-video-recorder-and-streaming-app-for-windows-linux-and-macos/)
																- Has WebRTC support now so you don't need a server in order to stream
															- [Cap](https://cap.so/)
															  collapsed:: true
																- [GitHub - CapSoftware/Cap: Effortless, instant screen sharing. Open-source and cross-platform.](https://github.com/CapSoftware/Cap)
																-
															- [GitHub - sorbayhq/sorbay: Open source asynchronous video communication](https://github.com/sorbayhq/sorbay)
															  collapsed:: true
																- [GitHub - sorbayhq/sorbay-client](https://github.com/sorbayhq/sorbay-client)
															-
														- ### Proprierary
															- Loom
																- Loom is software that, in one click, overlays your face in a bubble as you can narrate your screen recording, uploads it as it's recording, and when you press stop it copies a link to your clipboard you can share immediately with whoever you are showing. It's a very polished and complete experience.
															- [CleanShot X for Mac](https://cleanshot.com/)
													- Related: ((663b24fb-70fe-47b1-8936-aec019e9e29c))
											- `pkgs.syncthing`
											  collapsed:: true
												- ((6312a076-d503-40c4-b98f-cbdef17b1fcb))
											- `pkgs.vmware-workstation`
											  collapsed:: true
												- ((6416d896-0fd6-45f6-8a97-baf62375cbd5))
												  collapsed:: true
											- `pkgs.waydroid`
											  collapsed:: true
												- ((63a9ade4-ad80-4f73-ad36-483fb022f583))
											- [`pkgs.yakuake`](https://apps.kde.org/en-gb/yakuake/)
											  id:: 65a98a50-b4e8-41f7-9959-35465cbe3150
											  collapsed:: true
												- Pros/Cons
													- Pros
														-
													- Cons
														- [Yakuake setting for "Use Open/Retract action to focus window" disables F12 from working](https://bugs.kde.org/show_bug.cgi?id=15329#c106) on Wayland
														  id:: 65a98a51-b1d6-4645-97c5-48bf070e130b
														  collapsed:: true
															- WIP fixes
																- [Draft: Handle open/retract shortcut via DBus activation (!91) · Merge requests · Utilities / Yakuake · GitLab](https://invent.kde.org/utilities/yakuake/-/merge_requests/91)
																-
														-
													- Unclear
													- Comparisons
														- Similar to Guake for GNOME
												- `yakuake1.sh`
												  id:: 67aa0af5-3988-4d6c-a435-ca90fe40e59e
												  My start-up script
													- Being used so that when I unlock my ((670e4c5e-a0d2-4775-b62f-be7d0c3e32b8)) I can in one-click open all apps that I use on a daily basis
												- Running Guake is faster than launching a new terminal with a keyboard shortcut because the program is already loaded into memory, and so can be useful to people who frequently find themselves opening and closing terminals for odd tasks.
												- ## Keybindings
												  id:: 65a98a50-b0c3-487f-a2e6-6223543bf21a
													- `F12` = Open/Retract Yakuake
													- `CTRL + (` = Split Left/Right
													- `CTRL + )` = Split Top/Bottom
													- `CTRL + SHIFT + R` = Close Active Terminal
													- `CTRL + SHIFT + W` = Close Session
													- `CTRL + SHIFT + F11` = Full Screen Mode
													- `CTRL + SHIFT + T` = New Session (tab)
													- `SHIFT + Left` = Previous Session
													  AKA Go to the previous tab
													- `SHIFT + Right` = Next Session
													  AKA Go to the next tab
													- `CTRL + SHIFT + Left` = Move Session Left
													- `CTRL + SHIFT + Right` = Move Session Right
													- `CTRL + SHIFT + Up` = Previous Terminal
													- `CTRL + SHIFT + Down` = Next Terminal
													- ### Disabled
														- `ALT + <number>` = Switch to Session `<number>`
															- [[2025-02-11 Tuesday]] Was conflicting with `tmux` layout swapping, and it doesn't seem all that useful
												- Built on Konsole, uses Bash
												- Troubleshooting
													- If it keeps opening on a different monitor
														- `echo $DISPLAY` to see if there's a variable already set
														- `DISPLAY=:1` is what I'm using [[2025-01-09 Thursday]]
											- `pkgs.yt-dlp`
											  collapsed:: true
												- [`yt-dlp`](https://github.com/yt-dlp/yt-dlp)
												  id:: 64e094cf-c072-4502-93c8-c3e2e9795fab
												  collapsed:: true
												  AKA `youtube-dlp` for ((644c096b-7a26-4af2-a0b6-62d094da43ec))
													- Pros/Cons
														- Pros
															-
														- Cons
															- [🚨[IMPORTANT]🚨 KNOWN ISSUES/FAQ · Issue #3766 · yt-dlp/yt-dlp · GitHub](https://github.com/yt-dlp/yt-dlp/issues/3766)
																- [Age-restricted videos now always require sign-in](https://github.com/yt-dlp/yt-dlp/issues/11296)
														- Unclear
														- Comparisons
													- [Installation instructions](https://github.com/yt-dlp/yt-dlp#with-pip)
													  collapsed:: true
														- `python3 -m pip install --no-deps -U yt-dlp`
													- SOPs
														- Example usage
														  `yt-dlp [Bury A Friend - A Parahumans Animatic - YouTube](https://www.youtube.com/watch?v=J8WysbknTnE`)
														- Downloading and converting to mp3
														  collapsed:: true
														  `/home/boss/Downloads/1NEWMUSIC/0_yt-dlp_mp3_template.txt`
															- e.g.
															  yt-dlp -f 'ba' -x --audio-format mp3 [https://youtu.be/hgOyLEWUe_o](https://youtu.be/hgOyLEWUe_o)  -o '%(title)s.%(ext)s'
														- Downloading YouTube ASMR videos with preferred flags
														  id:: 642abf78-2a4e-4ba6-a12d-88951bdc68aa
															- `yt-dlp -f 'bestvideo[height<=1080]+bestaudio/best[height<=1080]' --merge-output-format mp4 --add-metadata --embed-thumbnail https://youtu.be/NuLD9ybVr30 https://youtu.be/Nu239ybVr30`
															- [`--add-metadata`/`--embed-metadata`](https://github.com/yt-dlp/yt-dlp#post-processing-options) will add video URL and metadata to file. Can be viewed using MediaInfo (via Nix [[2023-11-15 Wednesday]] ), or VLC : Tools : Media information, ((639cbbe9-df12-41c2-8cea-29db96fbeda9)), but not via ((651d714a-c80a-4289-a919-478910c779da))
														- Downloading Instagram videos
															- `yt-dlp --cookies /home/boss/Documents/ESSENTIALS/Other-files/yt-dlp/cookies.txt [Instagram](https://www.instagram.com/p/Ctq2Ov0Ig1L/?igshid=NjZiM2M3MzIxNA%3D%3D`)
															- `cookies.txt` obtained via [cookies.txt – Get this Extension for 🦊 Firefox (en-US)](https://addons.mozilla.org/en-US/firefox/addon/cookies-txt/)
													- [Supported sites](https://github.com/yt-dlp/yt-dlp/blob/master/supportedsites.md)
														- Doesn't support ((64f5d195-048b-4532-86da-5e3fa35b3d2c)) podcasts [due to DRM](https://github.com/yt-dlp/yt-dlp/issues/943#issuecomment-1689765556)
														  id:: 66508411-678c-4908-bdcf-b5818337b627
													- GUIs
														- Downloading-only
															- [GitHub - KurtBestor/Hitomi-Downloader: :cake: Desktop utility to download images/videos/music/text from various websites, and more.](https://github.com/KurtBestor/Hitomi-Downloader)
															- [GitHub - Unrud/video-downloader: Download videos from websites like YouTube and many others (based on yt-dlp)](https://github.com/Unrud/video-downloader)
															- [Parabolic](https://flathub.org/apps/org.nickvision.tubeconverter)
														- Player
															- [GitHub - vzhd1701/gridplayer: Play videos side-by-side](https://github.com/vzhd1701/gridplayer)
																- [Install GridPlayer on Linux | Flathub](https://flathub.org/apps/com.vzhd1701.gridplayer)
																-
															- ((65166ca4-1398-465a-8ff7-029210238874))?
										- File locations
											- `/home/boss/.config/home-manager/home.nix`
											- {Archive}
											  collapsed:: true
												- OLD pre [[2023-03-15 Wednesday]] `/home/boss/.config/nixpkgs/home.nix`
												  id:: 63ab2e72-6379-40aa-af06-3b82672f8781
										- {Archive}
											- [FFmpeg](https://ffmpeg.org/)
											  collapsed:: true
												- [FFmpeg - Ultimate Guide | IMG.LY Blog](https://img.ly/blog/ultimate-guide-to-ffmpeg/)
												  id:: 644c09ca-9b30-41ff-8143-4c2034dc4a42
												  collapsed:: true
													- https://news.ycombinator.com/item?id=33771445
													-
													-
												- Convert `.flac` to `.mp3`
													- `find . -name "*.flac" -exec ffmpeg -i {} -ab 160k -map_metadata 0 -id3v2_version 3 {}.mp3 \;`
												- [FFmpeg.guide - One stop solution to all things FFmpeg](https://ffmpeg.guide)
												  collapsed:: true
												- https://amiaopensource.github.io/ffmprovisr/#streaming-saving
												- ## GUIs
													- [HandBrake](https://handbrake.fr/)
													  id:: 6655e501-3e4b-4350-983a-0dce9ee99d02
													  collapsed:: true
														- [Install HandBrake on Linux | Flathub](https://flathub.org/apps/fr.handbrake.ghb)
														  collapsed:: true
														- [https://github.com/HandBrake/HandBrake](https://github.com/HandBrake/HandBrake)
														- Docs
															- [HandBrake Documentation — Quick start](https://handbrake.fr/docs/en/1.7.0/introduction/quick-start.html)
																- `Open Source` to select a video
																- `Preset`: `Fast, Official 1080p` will make a M4V file (same as MP4, except it also has support for DRM)
																- Check where it'll save to and filename it saves as (bottom)
																- `Start`
														- Comparisons of files sandbox
														  collapsed:: true
															- 1
																- {
																  "creatingLibrary":{"name":"MediaInfoLib","version":"23.07","url":"[MediaInfo](https://mediaarea.net/MediaInfo"},)
																  "media":{"@ref":"/home/boss/Videos/Untitled_video_-_Made_with_Clipchamp.mp4","track":[{"@type":"General","VideoCount":"1",
																  "AudioCount":"1",
																  "FileExtension":"mp4",
																  "Format":"MPEG-4",
																  "Format_Profile":"Base Media",
																  "CodecID":"isom",
																  "CodecID_Compatible":"isom/iso2/avc1/mp41",
																  "Format":"AVC",
																  "Format_Profile":"Constrained Baseline",
																  "Format_Level":"5",
																  "Format_Settings_CABAC":"No",
																  "Format_Settings_RefFrames":"1",
																  "CodecID":"avc1",
																  "extra":{"CodecConfigurationBox":"avcC"}},{"@type":"Audio","StreamOrder":"1",
																  "ID":"2",
																  "Format":"AAC",
																  "Format_AdditionalFeatures":"LC",
																  "CodecID":"mp4a-40-2",
																  }
															- 2
																- {
																  "creatingLibrary":{"name":"MediaInfoLib","version":"23.07","url":"[MediaInfo](https://mediaarea.net/MediaInfo"},)
																  "media":{"@ref":"/home/boss/Videos/Replay_2024-04-08_17-46-02-trimmed.m4v","track":[{"@type":"General","VideoCount":"1",
																  "AudioCount":"1",
																  "FileExtension":"m4v",
																  "Format":"MPEG-4",
																  "Format_Profile":"Base Media / Version 2",
																  "CodecID":"mp42",
																  "CodecID_Compatible":"mp42/iso2/avc1/mp41",
																  
																  "Format":"AVC",
																  "CodecID":"avc1",
																  "Encoded_Library":"x264 - core 164 r3107 a8b68ebf",
																  "Encoded_Library_Name":"x264",
																  "extra":{"CodecConfigurationBox":"avcC"}},{"@type":"Audio","StreamOrder":"1",
																  "ID":"2",
																  "Format":"AAC",
																  "Format_Settings_SBR":"No (Explicit)",
																  "Format_AdditionalFeatures":"LC",
																  "CodecID":"mp4a-40-2",
																  "Duration":"16.982",
																  "Source_Duration":"17.003",
																  "BitRate_Mode":"CBR",
																  }
													- [LosslessCut](https://flathub.org/apps/no.mifi.losslesscut)
													- [GitHub - edneyosf/Edconv: A user-friendly FFmpeg GUI](https://github.com/edneyosf/Edconv)
													- Use a LLM to write CLI statements
									- Installation
									  collapsed:: true
										- Home Manager can be used in three primary ways:
											- 1) Using the standalone home-manager tool (only method for non-NixOS or Darwin)
												- It is also recommended for people on NixOS or Darwin that want to manage their home directory independently of the system as a whole. See [Standalone installation](https://nix-community.github.io/home-manager/index.html#sec-install-standalone) in the manual for instructions on how to perform this installation.
											- As a module within a NixOS system configuration.
											  collapsed:: true
												- This allows the user profiles to be built together with the system when running nixos-rebuild. See NixOS module installation in the manual for a description of this setup.
											- As a module within a nix-darwin system configuration.
											  collapsed:: true
												- This allows the user profiles to be built together with the system when running darwin-rebuild. See nix-darwin module installation in the manual for a description of this setup.
											- Related: ((65494793-ebbc-4fcb-bdc8-1a31b5561502))
										- [*Standalone installation*](https://nix-community.github.io/home-manager/#sec-install-standalone)
											- ```
											  nix-channel --add https://github.com/nix-community/home-manager/archive/master.tar.gz home-manager
											  nix-channel --update
											  ```
											- `nano ~/.profile`
											- Add this line for non-NixOS:
											  ```
											  export NIX_PATH=$HOME/.nix-defexpr/channels:/nix/var/nix/profiles/per-user/root/channels${NIX_PATH:+:$NIX_PATH}
											  ```
											- `source ~/.profile` = reload bash to look at these new environment variables?
											  id:: 63f33f4e-f09a-4d29-87f9-6a6cc50347f9
											- `nix-shell '<home-manager>' -A install`
											  Run the Home Manager installation command and create the first Home Manager generation
										- Home Manager provides both the channel-based setup and the flake-based one. See [Nix Flakes](https://nix-community.github.io/home-manager/index.html#ch-nix-flakes) for a description of the flake-based setup.
									- Usage
										- How to upgrade packages
											- `nix-channel --update` = Update all channels
											  id:: 640e41d4-71bd-42d0-8683-338a95944304
											- `home-manager switch` = Switch into new profile
											  id:: 64ecc126-e9d3-4fdd-8a53-f9bf8c009f0f
											  Equivalent to `nixos-rebuild switch` on NixOS
											- Related: ((644c0b9b-cdd7-48ca-900d-1ae586db9309))
										- [Setup auto-upgrades](https://github.com/nix-community/home-manager/blob/master/modules/services/home-manager-auto-upgrade.nix) using `services.home-manager-auto-upgrade`
										- How to update config with new data
										  collapsed:: true
											- Edit ((63ab2e72-6379-40aa-af06-3b82672f8781))
											- `home-manager switch` = Activate the updated config
										- How to [rollback](https://nix-community.github.io/home-manager/index.html#sec-usage-rollbacks)
										  collapsed:: true
											- `home-manager generations` to determine which generation you wish to rollback to
											- Copy the Nix store path of the generation you chose, e.g.,
											- ```
											  /nix/store/mv960kl9chn2lal5q8lnqdp1ygxngcd1-home-manager-generation
											  ```
											- Run the `activate` script inside the copied store path e.g.
											- ```
											  /nix/store/mv960kl9chn2lal5q8lnqdp1ygxngcd1-home-manager-generation/activate
											  ```
										- Run `man home-configuration.nix` to see all available options or go to [Appendix A. Configuration Options](https://nix-community.github.io/home-manager/options.html)
										  collapsed:: true
											- e.g. 
											  ```
											  programs.emacs.enable = "yes";
											  ```
									- Troubleshooting
										- Newly installed applications not in KDE applications menu
										  collapsed:: true
											- Have done initial setup using this ((63aadd38-1048-46c2-8cf8-de73036b46eb)) already
											- Might require a reboot
											- `ls ~/.nix-profile/share/applications`  = shows both Home Manager and `nix-env` installed apps
								- [Learning Resoures]
								  collapsed:: true
									- [Tutorial: Getting started with Home Manager for Nix | Mattia Gheda](https://ghedam.at/24353/tutorial-getting-started-with-home-manager-for-nix)
									- [Declarative management of dotfiles with Nix and Home Manager](https://www.bekk.christmas/post/2021/16/dotfiles-with-nix-and-home-manager)
									- [Home Manager option search](https://mipmip.github.io/home-manager-option-search/)
									- New modules (discovered via `home-manager news`)
										- `programs.looking-glass-client`
										- `programs.thunderbird`
										- `programs.yt-dlp`
										- `services.recoll`
										- `programs.tealdeer` (TLDR)
										- `programs.tealdeer`
									- ((63f33f4e-186f-4e6c-bb65-588840c27da4))
							- [GitHub - numtide/system-manager: Manage system config using nix on any distro](https://github.com/numtide/system-manager)
							-
						- Nix flakes
						  collapsed:: true
							- [https://www.reddit.com/r/NixOS/comments/udvcdh/how_should_i_learn_nix_flakes/](https://www.reddit.com/r/NixOS/comments/udvcdh/how_should_i_learn_nix_flakes/)
							- [Installation (Nix From First Principles: Flake Edition #2) - Tony Finn](https://tonyfinn.com/blog/nix-from-first-principles-flake-edition/nix-2-installation/)
						- Nixlang (Nix Language)
						  id:: 63a9adc7-591d-420b-8a89-ec772f16c264
						- [Nickel](https://github.com/tweag/nickel) - replacement for ((63a9adc7-591d-420b-8a89-ec772f16c264))
						- Dotfiles
						  collapsed:: true
							- Other peoples
								- [GitHub - Mic92/dotfiles: My NixOS dotfiles](https://github.com/mic92/dotfiles)
						- [Ubuntu vs. NixOS - NixOS Wiki](https://nixos.wiki/index.php?title=Ubuntu_vs._NixOS&useskin=vector) cheatsheet
						- SOPs
							- Installing old versions of packages
							  collapsed:: true
								- [Marcelo Lazaroni](https://lazamar.co.uk)
									- Method
										-
								- [Description of how to do so](https://lazamar.github.io/download-specific-package-version-with-nix/)
									- [Searching and installing old versions of Nix packages – Marcelo Lazaroni – Developing for the Interwebs](https://lazamar.github.io/download-specific-package-version-with-nix/)
									  collapsed:: true
										- TL;DR: There is no Nix-native way of doing that. In this post I describe the process that led to the creation of [Nix Package Versions](https://lazamar.co.uk/nix-versions), the tool that provides this functionality.
										- ## The problem
										- The [Nix package manager](https://nixos.org) allows one to easily install and remove different versions of the same package. With [nix-shell](https://nixos.org/guides/nix-pills/developing-with-nix-shell.html) one can even start a shell environment with a different version of a package that is already installed.
										- ![nix-shell example](../images/2020-08-31-nix-shell-example.png)
										- This is extremely useful and one of Nix’s killer features.
										- Some time ago I noticed that my version of Neovim had a bug. This seemed like an easy fix, I just needed to install a previous version of the same package.
										- Searching locally with `nix-env -qa neovim` revealed that my revision had only one version of the package, which was the same as the one available at <https://search.nixos.org/packages>. After some more research I discovered that there is currently no Nix-native way to search through previous revisions for older versions of a package. In fact there is [a very long discussion](https://github.com/NixOS/nixpkgs/issues/9682#issuecomment-658424656) spanning multiple years about how to do that and whether it is suitable for the package manager to provide such functionality.
										- So what to do?
										- ## A first approach to a solution
										- What I really want is to look through older revisions and check what version of Neovim they have in the hope that they would have an older version of it. I could then tell Nix to install it from that old revision.
										- A revision is nothing more than a big Nix expressions that describes all the packages available and how to build them. Nix revisions are kept at [NixOS/nixpkgs-channels](https://github.com/NixOS/nixpkgs-channels). If you change anything in a revision it becomes a different revision. This means that _each commit in the repository describes a different revision_.
										- Given that one commit is equal to one revision, to find a revision containing an older version of Neovim I can look through the git history of that repository searching for changes in the `version` field of the `neovim` derivation.
										- Searching for _neovim_ at <https://search.nixos.org/packages> I can see that the nix expression describing it lives at `pkgs/applications/editors/neovim/default.nix`.
										- So I started by cloning `NixOS/nixpkgs-channels` and using `git rev-list` to find all commits that modify that file.
										- ```
										  $ git rev-list nixos-unstable -- pkgs/applications/editors/neovim/default.nix
										  0f1434cb2adb8bec6678b53510750ce7c1814263
										  7f137849e8612ffa0de59871ec95956c41c83697
										  b4c7a0b76252f4c115e36bcb6496c7a5928a9ec7
										  ...
										  ```
										- I could then use `git grep` to check if the line containing the package version was changed.
										- ```
										  $ git grep -E '^\s+version\s?=\s?"[^"]+"\s*;\s*$' 0f1434cb2adb8bec6678b53510750ce7c1814263 -- pkgs/applications/editors/neovim/default.nix
										  0f1434cb:pkgs/applications/editors/neovim/default.nix: version = "0.4.4";
										  ```
										- I can use `xargs` perform one `git grep` search per commit in `git rev-list`, this way I will effectively have a list of all commits where the version of `neovim` was changed.
										- ```
										  $ git rev-list nixos-unstable -- pkgs/applications/editors/neovim/default.nix | xargs -I{} git grep -E '^\s+version\s?=\s?"[^"]+"\s*;\s*$' {} -- pkgs/applications/editors/neovim/default.nix
										  0f1434cb:pkgs/applications/editors/neovim/default.nix: version = "0.4.4";
										  7f137849:pkgs/applications/editors/neovim/default.nix: version = "0.4.4";
										  b4c7a0b7:pkgs/applications/editors/neovim/default.nix: version = "0.4.3";
										  ...
										  2c95ce90:pkgs/applications/editors/neovim/default.nix: version = "0.2.2";
										  0f84673f:pkgs/applications/editors/neovim/default.nix: version = "2017-11-05";
										  0f84673f:pkgs/applications/editors/neovim/default.nix: version = "0.2.1";
										  ...
										  ```
										- Success!! Now I can just choose the version of `neovim` I want and open a shell with it by specifying the revision’s commit address on github.
										- `nix-shell -p neovim -I nixpkgs=https://github.com/NixOS/nixpkgs-channels/archive/92a047a6c4d46a222e9c323ea85882d0a7a13af8.tar.gz`
										- ## Automating
										- Even though this worked, it was not pleasant.
										- * I had to clone a large repository
										- * Finding out what commands would give the right answer took time
										- * Finding out how to install packages from an arbitrary revision took time
										- * This breaks if the derivation’s version is an expression instead of a string.
										- * This breaks if there is another version field somewhere else in the derivation file
										- * This breaks if the derivation file changes
										- * This requires too many steps
										- I expected a good solution to be similar to the official Nix package search website. A page with one search box where you enter the package you are interested in and get a copy-pasteable command to install it. So I started with that as the goal.
										- I initially thought of setting up a server with a clone of `nixpkgs-channels` that would perform this git search every time someone made a package query. It soon became obvious that this was too error-prone and would not scale.
										- I discovered that `nix-env -qaP --json` outputs a big json file containing information about all packages available in your default revision. You can specify a different revision by using the `-f` flag. Using this I could find out information about packages in any revision reliably. This command takes some time to complete, but I can save its result in a cache and query the cache instead.
										- But I can’t cache everything. Not only do we have one revision per commit, we also have multiple channels. Each channel is a branch in the repo. It is not feasible to store information about every single commit from every channel. To simplify things I save data for one revision from each channel for every 5 weeks period. This seemed like a reasonable interval as most packages don’t have new versions more often than that.
										- After a few hours gathering data from 2017 until now the database ended up containing information about 1,993,997 package versions spanning 1,032 revisions. This amounts to 542Mb which I store in an SQLite database to keep things simple, fast and portable.
										- With the data in place all that remained was building the UI and setting up a cron job to update the database every so often.
										- One can now search for old package versions at <https://lazamar.co.uk/nix-versions/>
										- It shows all old versions you can install for some specific channel
										- ![Screenshot of neovim versions search result from lazamar.co.uk/nix-versions](../images/2020-08-31-neovim-versions-2.png)
										- And it gives copy-pasteable installation instructions for using it in the command-line or in a nix derivation.
										- ![Screenshot of neovim versions search result from lazamar.co.uk/nix-versions](../images/2020-08-31-neovim-install-instructions.png)
										- The tool is open source and the code is available at <https://github.com/lazamar/nix-package-versions>
										- Nix revisions specify how a package is to be built, but actually building it may take a very long time, especially if you are also building everything that it depends on. To avoid that Nix servers keep the pre-compiled binaries of packages in recent revisions and make those available for download. Your system will automatically choose to download the binary if it is available instead of building the whole thing.
										- When you are installing things from older derivations you lose that benefit and your **build times may be much longer**.
										- Additionally, if a package has releases more often than every 5 weeks, **a version may be missed**.
										- Given that easily handling package versions is such an important feature of Nix I hope that in the future this functionality will be built into the package manager.
							- ((640e41d4-71bd-42d0-8683-338a95944304))
							- Immutable Nix
							  collapsed:: true
								- [1](https://news.ycombinator.com/item?id=35384347)
									- t’s much less plug-and-play than the options in the article… but I’ve had fun with a related idea, which is running Nixos on storage where root is erased on every boot.
									  
									  My home server is set up this way. At the time, I more or less followed this guide, which explains things nicely:
									  
									  [Erase your darlings: immutable infrastructure for mutable systems - Graham Christensen](https://grahamc.com/blog/erase-your-darlings/)
									  
									  Been erasing root for almost 2 years I think now. Works great!
								- 2
									- mount '/' as a tmpfs which seems saner than manually deleting. IMO.
									  > It depends on how much ephemeral data one expects to have. E.g. browser cache on tmpfs can use a fair bit of the often-more-limited RAM space.
								-
							- [Installing npm packages](https://unix.stackexchange.com/questions/379842/how-to-install-npm-packages-in-nixos)
					- Ecosystem
						- Tools
							- [GitHub - xtruder/nix-devcontainer: Swiss army knife container for vscode development environments](https://github.com/xtruder/nix-devcontainer)
							  id:: 64971377-7a63-4d90-babb-55aaea9960f7
							  collapsed:: true
								- Description
									- Nix devcontainer is an opinionated [vscode devcontainer](https://code.visualstudio.com/docs/remote/containers)
									  that uses debian image for a base system and [nix package manager](https://nixos.org/)
									  for management of your development environments. Combination
									  of a good base image and a best in class package manager, gives
									  you versatile, reproduible and deterministic development environment
									  that you can use everywhere.
								- ### Components
									- **[Debian slim](https://hub.docker.com/_/debian) docker image**
									  
									  Docker base image, which provides minimalistic environment in which both nix and
									  vscode remote extension can run without any issues.
									- **[Nix package manager](https://nixos.org/)**
									  
									  Used for providing declarative, deterministic and reporoducible development environment that
									  you can run anywhere. Imagine better [conda](https://docs.conda.io/en/latest/) alternative.
									  You write a single `shell.nix` file that describes your environment and all your tools and
									  vscode extensions will be running with same exact versions of binaries, same environment
									  variables, same libraries forever.
									- **[Nix Environment Selector](https://marketplace.visualstudio.com/items?itemName=arrterian.nix-env-selector) vscode extension**
									  
									  Used to automatically load nix development environment into your vscode and provides
									  capabilities to reload it later when environment changes, without having to rebuild
									  docker image from scratch on every change.
									- **[Direnv](https://direnv.net/) shell environment loader**
									  
									  While nix environment loader extension loads environment for vscode, you
									  want `direnv` to manage you shell environment. `Direnv` loads nix environment
									  (defined by `shell.nix` file) into your shell and reloads it automatically when it changes,
									  keeping your environment fresh.
							- [Devbox Cloud](https://www.jetpack.io/blog/announcing-devbox-cloud/): Nix powered Development environments on the edge
							  collapsed:: true
								- When you use it to spin up a cloud VM we automatically use Nix to set up the environment. For now we look for a devbox.json file generated by our OSS tool (https://github.com/jetpack-io/devbox) but we want to make the cloud service usable by the entire Nix community; whether your using our tool or using nix directly. Therefore we plan to support projects with a flake.nix very soon.
								- If you want to try out Devbox Cloud on your browser, you can prepend [http://devbox.sh](http://devbox.sh) to any github repo URL. If the repo has a `devbox.json`, then Devbox Cloud will automatically install your Nix packages and configuration. For example, you can try out the Devbox repo by visiting [[Devbox cloud | Error](https://devbox.sh/github.com/jetpack-io/devbox](https://devbox.sh/github.com/jetpack-io/devbox))
							- [flox](https://floxdev.com/blog/flox-open-beta)
							  collapsed:: true
								- [The Flox Open Beta | Hacker News](https://news.ycombinator.com/item?id=34693477)
							- [GitHub - numtide/system-manager: Manage system config using nix on any distro](https://github.com/numtide/system-manager)
							  id:: 6536ed61-4528-4ade-bca0-43e1f7b74607
							- [Nixhub](https://nixhub.io/): Search Historical Versions of Nix Packages
							- [GitHub - flox/flox: Developer environments you can take with you](https://github.com/flox/flox)
							- [GitHub - nix-community/nurl: Generate Nix fetcher calls from repository URLs maintainer=@figsoda](https://github.com/nix-community/nurl)
							- [GitHub - nix-community/trustix: Trustix: Distributed trust and reproducibility tracking for binary caches maintainer=@adisbladis](https://github.com/nix-community/trustix)
							-
						- Nix-based distributions
							- [SnowflakeOS](https://snowflakeos.org/)
							  collapsed:: true
								- [SnowflakeOS · GitHub](https://github.com/snowflakelinux)
						- [MyNixOS](https://mynixos.com/) - share environments
						- [Fast, Declarative, Reproducible, and Composable Developer Environments - devenv](https://devenv.sh/) - composable dev environments
						  id:: 6550215a-3662-477b-bc03-34f555563394
							- [Devenv: Compose a Developer Environment easily for PHP with Nix | Shyim's Brain](https://shyim.me/blog/devenv-compose-developer-environment-for-php-with-nix/)
							- Related: ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) : ((663914ec-9950-45fa-b647-a9e91775211c))
					- Other distros with declarative configuration
						- Guix
					- [Learning Resources]
					  collapsed:: true
						-
						- [NixOS package search](https://search.nixos.org/packages)
						- [NixOS option search](https://search.nixos.org/options?)
						- [NixOS wiki](https://nixos.wiki/)
						- [GitHub advanced search](https://github.com/search/advanced)
						- [Our roadmap for Nix - Aug 2022](https://news.ycombinator.com/item?id=32374113)
						- Learning Nix
							- [Flakes is what should be used now, but the docs is mostly outdated](https://news.ycombinator.com/item?id=32170716)
							- Top priority Nix resource - [Zero to Nix](https://zero-to-nix.com/)
							  id:: 644c09ca-44e7-46bc-a5e1-88f345c00744
						- [autopatchelf - allowing arbitrary binaries to run on NixOS](https://fzakaria.com/2020/12/01/autopatchelf-what-it-can-look-like.html)
						- [Manix](https://github.com/mlvzk/manix) -  - A Fast Documentation Searcher for Nix with support for Nixpkgs, NixOS Options and Home-Manager Options
						  id:: 63f33f4e-186f-4e6c-bb65-588840c27da4
						- [https://devdocs.io/nix/](https://devdocs.io/nix/)
						- [21.02 Nix | Animesh Sahu](https://animeshz.github.io/site/notes/20-29--DevEnvironment/21--Linux/21.02-Nix.html)
						-
					- Related: ((63a9adc7-c031-4dc6-a162-c91f04da953c)) containers can be used to install normal packages if using NixOS and NixPkgs is ever insufficient
						- e.g. using an Arch container for all gaming-related things
				- Gentoo
				- ### Proprietary
					- [ChromeOS](https://chromeos.google)
					  id:: 65a98a50-b19c-4fba-ab47-b3db6104166f
					  collapsed:: true
						- Cons
							- It runs Linux in a VM not a container for security reasons, but this impacts performance
					- Zorin OS Pro
					  collapsed:: true
						- [https://zorin.com/os/pro/](https://zorin.com/os/pro/) is basically what you're looking for
				- [Learning Resources]
				  collapsed:: true
					- Infographic
					  collapsed:: true
						- ![image.png](../assets/image_1716706966475_0.png)
		- Other
			- FreeBSD
			  id:: 65f9fe65-1678-4356-bff0-e42d05cfe235
			- Redox (Rust-based UNIX microkernel)
			  collapsed:: true
				- [https://www.redox-os.org/](https://www.redox-os.org/)
		- Related:
			- Convergent OS
			- ((649b13cf-a825-48f5-ae83-b47b6ad6bff9))
	- Filesystem
	  id:: 635eb108-7d76-47c7-bddb-a8a977599a39
	  collapsed:: true
		- Modern CoW snapshotting filesystems (BTRFS, ZFS)
			- ((6360e32e-29f9-4526-ac4e-59ead71baa88))
			  [[IT Systems]]
			- ((6360e32e-f263-4cdf-8473-c5b60e05cbe7))
			- being more of a thing (Fedora & OpenSUSE default to BTRFS and OpenSUSE has the great snapper tool integrated into the distro, Ubuntu has been making good progress on ZFS, encrypted ZFS, and a tool for making the most of snapshots, BTRFS + Timeshfit is also popular among Arch users.
			- Fedora uses BTRFS, but they haven't really integrated it/leveraged its features out of the box in teh same way that OpenSUSE or Ubuntu do with builtin snapshotting utilities, bootable snapshots from grub, automatic snapshots, etc.
		- Bachefs
			- [https://news.ycombinator.com/item?id=31419121](https://news.ycombinator.com/item?id=31419121)
	- Related: [[Software]]
- PC Hardware
  id:: 6313455f-8a50-4b26-b405-f536a2fa450b
  collapsed:: true
	- Current
	  id:: 65a98a50-f512-4be8-9daa-1527d79584c4
		- ((685696dd-7e04-42d1-ba07-c06d6a16574e))
		- ((659d093f-bf67-444a-b2a1-ec0a28907583)) : ((65edb146-02fa-4df0-be3b-f07e00b2f49d))
		- ((65a98a50-4b57-4816-931f-24253c6bc8b7))
			- ((65494796-e73d-4312-85d2-78f0c5719b25))
		- Hard drives
		  collapsed:: true
			- Meta
			  collapsed:: true
				- Windows 7 and 10 can only be installed on an internal drive which is formatted to NTFS, done from an external USB which contains the Rufus-installed ISO
			- My current hard drives
			  collapsed:: true
				- A500
				  collapsed:: true
					- HDD
					- Tried to install Windows 7 Home Basic on it (initially added ISO to it via Rufus). Required NTFS, then it said it couldn't install as disk may fail soon
				- B320
				  collapsed:: true
					- HDD
					- Contains 32-bit Windows 7, compatible with ThinkPad T420
				- C256
				  collapsed:: true
					-
		- Raspberry Pi (Portuguese TV for gran)
		  collapsed:: true
			- Fixing VLC being black when fullscreen
			  collapsed:: true
				- Tools > Preferences > Video > Codec > OpenGL video output
			- Open VLC to [https://iptv-org.github.io/iptv/countries/pt.m3u](https://iptv-org.github.io/iptv/countries/pt.m3u) then to RTP
			  collapsed:: true
				- See [IPTV](https://workflowy.com/#/d354294cb847)
				  #Media
		- Additional
		  collapsed:: true
			- Get gadget insurance
			  collapsed:: true
				- https://www.moneysupermarket.com/gadget-insurance/quote
				- Related: phone purchase dates
				  https://www.ebay.co.uk/myb/PurchaseHistory#PurchaseHistoryOrdersContainer?ipp=100&Period=3&cmid=2749&_trksid=p2057872.m2749.l5117
				- Related: ((64e09478-a255-404c-a722-1134b6748f8e))
	- Analyses
		- [[2025-05-16 Friday]] Carlyon Road new tech setup
		  id:: 6827b4f7-8a40-47d0-9b2f-1341509daf11
		  collapsed:: true
			- Post- ((67375e60-b98a-409e-bcd9-127b37350dd6)) passing away
				- Unlike ((67c095e2-f716-4fe8-b37e-3bfa0bf7f536)), now I'm considering a large desktop as I'll have space for it
			- # Conclusion
			  id:: 6827b540-7fac-4f9a-9063-040e3cd3aa0f
				- ((68397b4b-5d27-45a7-a60f-957146bf35ac)) : ((685696dd-7e04-42d1-ba07-c06d6a16574e))
					- Because it's well suited for being a gaming PC
					- Install Linux on it (perhaps Fedora) because ((632093dc-1fb0-4500-a4a6-fd6e7b2e7508)) is basically good enough as primary gaming nowadays
			- # Options
				- Upgrade my ((68397c08-2f2f-4d4a-8dee-ff315410d4dc)) ?
				- Create a ((68397b4b-5d27-45a7-a60f-957146bf35ac))
					- ((632093dc-ef96-4d8d-84df-aead8451b7df)) ?
						- ((64e0952c-ef9d-4766-b7ff-904d2f2442fd)) currently requires 2 GPUs but next update only 1 for non-gaming usecase
						- ((62e2844f-3eba-403e-ad55-73d00b47065e))
						- ((64e0952c-7eb4-46ad-accd-321c6713fc75)) card?
				- Create a ((6341c07c-00cf-4e45-9336-ebbcdbf8e71f))
				- Create a [[Overemployed]] : [hardware setup](((6737678e-81b5-4074-a58e-8150942dd8e3)))
				- Consider dual GPU desktop in order to use ((64e0952c-ef9d-4766-b7ff-904d2f2442fd)) and VFIO? And maybe 1 NVMe, 1 HDD
				  collapsed:: true
					- Pros
					  collapsed:: true
						-
					- Cons
						- ((64e0952c-ef9d-4766-b7ff-904d2f2442fd)) : ((683993c3-7b44-4551-8044-ef4c5f67ad4f)) would allow non-gaming usecase e.g. job interviews, plus [[SS13]]
					- See
						- {{embed ((6856a5ca-22e6-49d1-87c4-88f0f30ee201))}}
				- Related:
					- ((65a98a50-811c-4de7-8127-0919127fe8af))
			- # Favourite builds
				- ((68399f94-1c33-41ed-9895-2a4ac80a2667))
				- [[Overemployed]] : [hardware setup](((6737678e-81b5-4074-a58e-8150942dd8e3))) : 4J with laptops
			- # Future upgrades
				- ((67c1ad55-6362-4335-9375-3811a8f7efb8)) if I choose a ((68397c08-2f2f-4d4a-8dee-ff315410d4dc))
				- Steam Deckard + Immersed rather than all the screens
			- Related: ((67c095e2-f716-4fe8-b37e-3bfa0bf7f536))
		- Post- ((659d093f-bf67-444a-b2a1-ec0a28907583))
		  id:: 67c095e2-f716-4fe8-b37e-3bfa0bf7f536
		  collapsed:: true
		  [[2025-02-27 Thursday]] Started analysis
			- Pros/Cons to upgrading
				- Pros
					-
				- Cons
					-
				- Unclear
					- ((659d093f-bf67-444a-b2a1-ec0a28907583)) : ((65b16a2e-8f9b-4b45-985a-67b7861f063e))
				- Comparisons
			- # Options
				- ## For better [[Videogames]] performance, and modding (since ((651990c2-941b-45f6-83e3-0e71670fd4a7)) is taking awhile)
				  id:: 67c1d092-4528-4b33-a30d-1309d877e48c
					- Conclusion
						- [[2025-03-07 Friday]]
							- ((67c18f25-dfcf-4777-b167-df64ce8eb221)) = Decent interim solution until it's worth upgrading 13" mainboard or getting a ((65a98a50-a639-4780-878b-deb05e9261ac))
								- {{embed ((67ca1458-11bb-46ff-b258-ae7e615b4a31))}}
					- ### Usecases
						- ((675c2b82-ac3c-47c0-9878-08f1c2996360)) performance too low
						- Games which can't run via ((632093dc-1fb0-4500-a4a6-fd6e7b2e7508)) - have a Windows gaming PC?
						- Modding (since ((651990c2-941b-45f6-83e3-0e71670fd4a7)) is taking awhile)
					- ### Currently released
						- ((649b1463-90cf-40ee-b80f-cb955fc2264c)) again or another ((649b1463-f729-468b-b002-09d441f0dcb9)) solution e.g. ((67cb0bce-1315-4ee2-8917-b862cbdb4605))
						  id:: 67c18f25-dfcf-4777-b167-df64ce8eb221
						- ((67c08d46-8353-4111-9176-11f20fd10ff8)) - can fit a desktop-class motherboard + processor, as well as a GPU.  Need a decent sized case to fit my 3 fan GPU | ((65a98a50-811c-4de7-8127-0919127fe8af))
						- ((67c9b976-556b-484d-8ad8-4281f5bb3387))
						- ((67c1a6ab-9556-4e3a-85fd-b5cd5373161f)) and use M.2 slot with ((67c18f4c-711a-4b40-b1f1-8518f5d63f87)) adapter
						- Buy new ((67c18f4c-711a-4b40-b1f1-8518f5d63f87)) devices i.e. ((67c1a5ab-3c9d-4e4e-a7ec-595b58a17d07)) + ((67c1a547-3127-4edc-92a7-6a4fc19ac5c2))
						- XReal One headset + Samsung DeX + bluetooth folding keyboard
					- ### Wait for
						- Meta
							- [[2025-03-07 Friday]] It'll be 2026-2027 when a new AMD processor releases with ((67c1ad55-6362-4335-9375-3811a8f7efb8)) equivalent speeds
						- ((635037c3-27fc-4bd1-8958-5c3c8d2d46bb))
							- Check reviews against other mini-ITX sized devices. Though that does mean I won't be able to use eGPU with Linux laptop
						- Next 13" mainboard
							- Meta
								- #+BEGIN_WARNING
								  13" laptop-class CPUs may still be too limited and be a bottleneck compared to desktop
								  #+END_WARNING
								- ((67be2e4f-e0d4-4fce-b28e-892f187980e7)) : ((67cab8fc-1781-415a-8c39-281a53159630))
							- New 13" mainboard with ((67c1ad55-6362-4335-9375-3811a8f7efb8)) port speeds + a TB5 ((63ad9565-9f04-447d-b3c2-7541d47f2703)) (i.e. equivalent to ((67c18f4c-711a-4b40-b1f1-8518f5d63f87)) speeds)
							  id:: 67c1acfb-32f9-40ab-9007-39f685d3d284
								- Check ((67cacc9f-285c-4853-b89f-9279c9d8277a)) for Connectivity section - it needs to be something like "Native USB 4.0 v2 (80Gbps)". [[2025-03-07 Friday]] Not likely until early 2026
							- New 13" mainboard with a second M.2 port (for ((67c18f4c-711a-4b40-b1f1-8518f5d63f87)) adapter) or ((67c18f4c-711a-4b40-b1f1-8518f5d63f87)) port directly
						- Other Framework
							- ((67c1a6ab-9556-4e3a-85fd-b5cd5373161f)) next upgrade
							- ((635037c3-27fc-4bd1-8958-5c3c8d2d46bb))'s processor but as a 13" mainboard maybe
							  id:: 67c1abb5-0788-4fa5-a552-10be35262e2a
							- A Framework official [Expansion Bay for OcuLink](https://community.frame.work/t/oculink-expansion-bay-module/31898/596?u=stroman)
							  id:: 67c1ac90-c721-46ad-ab4b-743e937d6b6f
								- [OcuLink eGPU works with the Dual M.2 expansion bay module - Framework Laptop 16 - Framework Community](https://community.frame.work/t/oculink-egpu-works-with-the-dual-m-2-expansion-bay-module/62273)
						- ((67ca0d84-8c6a-496a-9230-43c580158d3b)) support in ((63ad9565-9f04-447d-b3c2-7541d47f2703)) + laptop motherboards (i.e. equivalent to ((67c18f4c-711a-4b40-b1f1-8518f5d63f87)) speeds)
						- ((67c9b976-556b-484d-8ad8-4281f5bb3387)) with Strix Haven APU
						- ((65a98a51-37bd-4253-b4ab-8437dc26f765)) to support all hardware features, AND for x86 emulation to get good
						  id:: 67c9f59b-33eb-4e1f-9eac-83eb60012f0d
						- ### Ideal
						  id:: 67ca1458-11bb-46ff-b258-ae7e615b4a31
							- ((67c1acfb-32f9-40ab-9007-39f685d3d284))
							- ((67c9f59b-33eb-4e1f-9eac-83eb60012f0d))
				- Related: ((659d093f-bf67-444a-b2a1-ec0a28907583)) : ((67c0e912-af58-47cb-af08-40a03edffb99))
		- Get a new laptop
		  id:: 65a98a50-3faa-4fa7-93cd-cc5cd081e1dd
		  collapsed:: true
		  Started analysis Q4 2022, last update [[2024-01-09 Tuesday]]. Ended with getting ((659d093f-bf67-444a-b2a1-ec0a28907583))
			- [[2024-01-09 Tuesday]] ((659d093f-bf67-444a-b2a1-ec0a28907583)) seems like a significant upgrade, wait until I have some more savings though and see if there is a 2024 refresh
			- Pros/Cons to upgrading
				- Pros
					- 16GB RAM is quite limited
						- Can't run even current applications all at once e.g. LEISURE + WORK browsers
						- Running ((644c09ca-07ac-4f1b-b377-da8dc0fd082e))
						- Can't use Qubes (though this may be incompatible with gaming)
						- Can't use [btrfs as filesystem](https://workflowy.com/#/f72b79ed5ddf) or <a href="https://workflowy.com/#/a1d0bddc95e6">ZFS</a> (though this can compromise deniably encrypted volumes, since there's a history of where changes in the volume takes place) with ZFS native encryption maybe
					- 2TB storage is also a bit limited
					  collapsed:: true
						- Can't store all my ASMR/adult videos
						- Haven't got my 300+ GB previous years' videos and images
					- CPU is limited - it's the bottleneck for eGPU gaming performance, and possibly [[Logseq]] freezes as well
					- Security could be better - ((65a98a50-7f84-47be-bc67-1ef4c2f5dcef)), tamperproof and/or libreboot
					- Battery life is bad
					- AMD has S3 standby support for better battery life, safety etc. My current laptop ((65a98a50-4b57-4816-931f-24253c6bc8b7)) had S3 sleep removed, S2 only available <a href="[A simpler way to organize your work - Workflowy](https://workflowy.com/#/1d1cf989f503">System) Sleep State</a>
					- Brightness is too low to allow mobile public use e.g. in the garden. 400+ nits needed. Alternatively needs anti-glare matte screen or screen protector to reduce sunlight reflection
				- Cons
					-
				- Unclear
				- Comparisons
			- _Potential hardware_
				- _Existing_
					- ((635037c3-27fc-4bd1-8958-5c3c8d2d46bb)) looks great due to it's modularity and thinness
					- ((635037c2-64f1-4e71-8d24-a106302e2036))
					  collapsed:: true
						- Librem 14 is IME disabled but not neutralised
					- ((63734d14-232e-4d9a-8354-0bbc208dd8a1))
					- ((635037c3-a289-4f58-af14-6efccdb6b003)) POWER9 is expensive but it can virtualise x86 via KVM/QEMU
					- HP ProBook 445 G8
					  collapsed:: true
						- ecently got a new laptop with Ryzen 5 5600U, 32GB RAM, and 2TB SSD. The laptop is HP ProBook 445 G8. RAM and SSD were sold separately, the upgrade only took 10 minutes and 6 screws. I paid less than €1000 including the upgrades.
						  collapsed:: true
							- he laptop is comparable to the Framework professional they offer for €2280. AMD CPU is better, 15442 versus 11036 points of [cpubenchmark.net](http://cpubenchmark.net) (that’s 6 cores versus 4). Surprisingly, Intel GPU is better, 2 versus 1.6 TFlops FP32. RAM amount is the same, AMD has twice the SSD storage.
							- he only large downside is the display, my laptop has 16x9 1080p 14” IPS, the Framework has more pixels and 3x2 aspect ratio.
					- ((633b7502-b358-45fb-95d2-5fc35ed27d3f)) + Steam Deck
					- ((633b7502-b358-45fb-95d2-5fc35ed27d3f)) + phone with [DP alt-mode](((63219e34-cda2-4a69-a2c8-b74b33cf9a91))) e.g. PinePhone Pro, Samsung DeX phones
					- [StarBook 14-inch | Hacker News](https://news.ycombinator.com/item?id=31034024)
					  CoreBoot, Linux compatibility, good specs ultrabook
				- _Future_
					- Razer Blade Stealth 13 - if they make a AMD version
					  collapsed:: true
						- [https://www.notebookcheck.net/Razer-Blade-Stealth-13-2021-in-review-Mobile-gamer-with-OLED-panel.562679.0.html](https://www.notebookcheck.net/Razer-Blade-Stealth-13-2021-in-review-Mobile-gamer-with-OLED-panel.562679.0.html)
						- Note the Razer Blade 14 (2021) has an AMD CPU for the first time, but also an Nvidia GPU
						  collapsed:: true
							- [https://www.razer.com/gb-en/gaming/laptops/razer-blade-14](https://www.razer.com/gb-en/gaming/laptops/razer-blade-14)
					- Microsoft Pluton chips for DRM are in AMD and other motherboards
					- ((63412f42-1797-4d76-9607-7351eafe4f40)) - in combination with Samsung DeX or similar
					- ((63577332-55c8-4f3e-af71-3dddba173c4a))
		- _Jan 2019 analysis_
		  collapsed:: true
			- Don't need a 2-in-1 at the moment as I don't use a ((631fa93c-fd77-4435-a292-fd9573d0242f))
			- Difficult to find reasonably priced 16GB RAM laptops, at 12"-14" screen, 1TB SSD, TB3 port
				- My requirements are high in that I want 1TB (mainly because I dual-boot currently) and Thunderbolt 3 (for eGPU)
				- Older gens of X1 Carbon and XPS 13 are available on eBay for ~£750 but lack USB-C
				- There are a few 2017 models with full TB3 support but finding them on eBay or similar they're similarly priced to current gen usually
				  https://egpu.io/build-guides/?table_filter=%2232Gbps-TB3%20%22
			- Best TB3 support ultrabooks
			  https://egpu.io/ultrabook-buyers-guide-external-gpu/
			- _Conclusion _
				- Could use NUC + Guacamole to remote desktop into powerful home workstation
				  https://www.tecmint.com/guacamole-access-remote-linux-windows-machines-via-web-browser/
				- Dell XPS 13 is what I bought in the end
				  intralink2:: https://workflowy.com/#/599e65ca7d8a
		- _Ideal gear list_
		  collapsed:: true
			- _Current_
				- High performance laptop for productivity
				  i.e. Dell XPS 13
			- _Short-term_
				- Dual monitor attachment ( ((6436adcd-9ced-41a7-8685-a4c5475906d9)) )
			- _Mid-term_
				- Higher* performance 2-in-1 for travel
				  32GB RAM for Qubes, better CPU, convertible 2-in-1
			- _Long-term_
				- Libreboot desktop with [Qubes](https://workflowy.com/#/e3b3f652ed7d)
				- ((65a98a50-7f84-47be-bc67-1ef4c2f5dcef)) (like Librem Key)
				  State/persistent data carried on a trusted device e.g. microSD or phone
			- Ideal laptop features
				- Business or enterprise class PC
				  collapsed:: true
					- easier to upgrade, come with TPM chips, extended BIOS etc
				- Finding [Qubes](https://workflowy.com/#/e3b3f652ed7d) compatible models
				  collapsed:: true
					- https://www.qubes-os.org/doc/system-requirements/#qubes-release-4x
					- Test Qubes with new laptop
						- https://www.qubes-os.org/doc/HCL/#generating-and-submitting-new-reports
					- Note: Doesn't work with Macs due to keyboard and mouse problems
						- https://www.qubes-os.org/doc/SystemRequirements/
						- https://github.com/QubesOS/qubes-issues/issues/230
				- [Qubes](https://workflowy.com/#/e3b3f652ed7d) recommended security features
				  collapsed:: true
					- CPU that supports both virtualisation technology
						- HVM - Intel VT-x or AMD-v technology
						  (required for running HVM domains, such as Windows-based AppVMs)
						- IOMMU - Intel VT-d or AMD IOMMU technology
						  (required for effective isolation of network VMs and PCI passthrough)
							- How to find a laptop with VT-d (IOMMU) support
							  https://groups.google.com/forum/#!msg/qubes-users/Sz0Nuhi4N0o/ZtpJdoc0OY8J
					- TPM - with proper BIOS support (required for Anti Evil Maid)
					  https://www.qubes-os.org/doc/anti-evil-maid/
					- Note: Run a QubesVM with Sandstorm for majority of apps inside (most secure container) and Docker for non-Sandstorm apps
					- https://theinvisiblethings.blogspot.com/2012/09/how-is-qubes-os-different-from.html
				- Libreboot
				- High portability = 11-14inch screen; weight under 3lb
				- CPU: i7 ideally, though top i5 is almost as good in tests
				- 32GB ideally, 16GB acceptable but maybe insufficient for Qubes+Firefox. Minimum 8GB RAM for Windows
				- Thunderbolt 3 ports (USB-C)
				  collapsed:: true
					- Can be used with eGPUs
					  intralink2:: https://workflowy.com/#/08e3a82de754
					- USB C shape connector
				- SSD 500GB + HDD 1TB
				  collapsed:: true
					- http://lifehacker.com/5837543/how-to-migrate-to-a-solid-state-drive-without-reinstalling-windows
				- Extended battery
		- 2016 best privacy/security options comparison
		  collapsed:: true
			- Physical security = ORWL
			- Killswitches
				- Radio, camera and microphone killswitch = Purism Librem laptops
				- Radio killswitch, no camera = FSF ThinkPads
				- Camera shutters?
			- Best performance = Libreboot D16; Purism Librem; ORWL; FSF ThinkPads
			- Most portable = USB armory or EOMA68
			- Most libre = EOMA68, USB armory
			- Also Libreboot D16, X200; Novena
			- Software security (Qubes) = Purism; ORWL.
			  https://www.qubes-os.org/compatible-hardware/
	- ## Ideal features
	  collapsed:: true
		- Best physical security / form factor
		  id:: 65a98a50-4aa2-4711-b646-b82d371d2d99
		  collapsed:: true
			- Either:
				- Stateless laptop
				  id:: 65a98a50-7f84-47be-bc67-1ef4c2f5dcef
				  collapsed:: true
				  [archived] http://blog.invisiblethings.org/papers/2015/state_harmful.pdf / ![state_harmful.pdf](../assets/state_harmful_1724743383193_0.pdf)
					- # OP
						- The main principle introduced below is the requirement for the laptop hardware to be stateless, i.e. lacking any persistent storage. This includes it having no firmware-carrying flash memory chips. All the state is to be kept on an external, trusted device.
						- Mainly involves a Trusted Stick which contains all firmware in a read-only partition and an encrypted partition for user filesystem data
						- Reasons
							- 1. The presence of persistent storage intermixed with the hardware makes it possible for the attacker to persist malware on the platform, without the user to have any simple way of learning about it, nor removing it (e.g. via OS re-installation).
							- 2. This also allows dishonest vendors, such as the OEMs or shipping agents, to deliver already infected hardware without the user being able to easily find out. This also includes Evil Maid attacks, which might be executed by other actors than vendors.
							- 3. The malware, once installed on the platform somehow, is given places where to store stolen secrets from the user. This is especially worrisome in the context of disk encryption keys, which could be exfiltrated this way even on air-gapped machines.
							- 4. Finally, these state-carrying elements make it possible to identify platforms and ultimately their users, due to various personally identifiable information, such as MAC addresses for WiFi or BT, which make the hardware unique.
							- As already mentioned several times in this paper, there are many more problems with x86 platform, and which we try to resolve with the stateless laptop, than just the physical attacks (super Evil Maid, Such other problems include: software attacks on firmware, malicious firmware (backdoored by the vendor, or somewhere during the shipment), software attacks against secure boot mechanisms.
					- # Thoughts
						- [[2024-08-27 Tuesday]] NVMe hard drives are small these days as well as USB-enabled enclosures for them. Also there are ((633b7502-b358-45fb-95d2-5fc35ed27d3f)) - which pairs well with a mobile phone
				- Secure boot with key fob or MFA authentication
				  collapsed:: true
					- Firmware
						- [safeboot](https://safeboot.dev/)
						- [Heads](http://osresearch.net/)
						  id:: 65a98a50-c7e6-4fd0-a9b0-01a6100bca7b
						  collapsed:: true
							- Free
							- Works with a mobile TOTP authenticator app so keys can be backed up e.g. andOTP
							- Compatibility
								- Librem Key only works with Librem laptops currently
								- Also compatible with Nitrokey 3 and Nitro PC
							- Tamper-evident boot protection via Trammel Hudson’s Heads security firmware
								- _How_
								  collapsed:: true
									- Heads only - if the TOTP pin fails then tampering has occurred
									- Librem Key - instead there will be a red LED showing tampering has occurred
										- > We have worked with Nitrokey to add a custom feature to our Librem Key firmware specifically for Heads. This custom firmware along with a userspace application allows us to store the shared secret from the TPM on the Librem Key instead of on a phone app. Then when Heads boots, if the BIOS hasn’t been tampered with the TPM will unlock its copy of the shared secret, and Heads will send the 6-digit code over to the Librem Key. If the code matches what the Librem Key itself generated, it flashes a green light. If the codes don’t match, it flashes a red light.
										- The implementation is basically a verified/measured boot scheme with TOTP.
											- During initialization, you generate a random TOTP key, add the key to your TOTP authentication device (e.g. Google Authenticator on mobile phone), and "seal" the key in your TPM, along with your boot "measurements". During the boot process, these "measurements", or the SHA hashes of various information/configuration about hardware, software and firmware, is being passed to the TPM. If the configuration has changed, the TPM will refuse to release the TOTP secret, otherwise, the TOTP key is released, then used to calculate a random number by a shell script in Heads.
											- If the number on your mobile phone matches with the number on the screen, then it proves the system is not being tampered.
								- https://github.com/osresearch/heads/
								- Detect BIOS tampering
								- Heads-enabled TPM
								- http://osresearch.net/
								  collapsed:: true
									- Heads is not just another Linux distribution – it combines physical hardening of specific hardware platforms and flash security features with custom coreboot firmware and a Linux boot loader in ROM. This moves the root of trust into the write-protected region of the SPI flash and prevents further software modifications to the bootup code (and on platforms that support it, Bootguard can protect against many hardware attacks as well). Controlling the first instruction the CPU executes allows Heads to measure every step of the boot firmware and configuration into the TPM, which makes it possible to attest to the user or a remote system that the machine has not been tampered with. While modern Intel CPUs require binary blobs to boot, these non-Free components are included in the measurements and are at least guaranteed to be unchanging. Once the system is in a known good state, the TPM is used as a hardware key storage to decrypt the drive.
									  Basically it prevents Evil Maid attacks or tampering
								- FAQ
								  https://trmm.net/Heads_FAQ
								- For Coreboot not UEFI
								- Comprehensive threat model FAQ
								  https://trmm.net/Heads_threat_model
					- Secure Key Fob to decrypt
						- Librem Key
						  id:: 65a98a50-ffe0-428e-988a-6640ec3fc566
						  collapsed:: true
						  Rebranded ((65a98a50-1ef5-4f2d-b006-36f4a177b339)) Pro V2
							- Librem Key v Heads alone pros/cons
							  id:: 65a98a50-60d2-4024-b15e-56e09ae9f64e
							  collapsed:: true
								- Both
								- Librem Key
									- Has the standard security features available in generic security tokens
									  collapsed:: true
										- You should use a long passphase to protect your encrypted hard drive, but typing it in each time you boot can be a hassle. With a Librem Key linked to your encrypted drive, you can boot your system, insert your key, and enter your PIN when prompted. You can always fall back to your passphrase if your Librem Key isn’t at hand.
										- The Librem Key features a tamper-resistant OpenPGP smart card that can store up to 4096-bit RSA keys and up to 512-bit ECC keys and can even securely generate them directly on the device. Ordinary GPG keys stored on your computer can be copied and used by hackers to decrypt your emails and documents, but once private keys are on the Librem Key, they stay on there and can’t be copied–encryption and decryption happens on the key itself!
										- With your GPG keys safely on the Librem Key, using encryption across multiple devices just got easier. Just insert your Librem Key whenever you want to encrypt, sign, or decrypt. Your keys are protected with a PIN so they are safe even in the hands of an attacker.
										- Can generate 4096-bit RSA keys, or copy GPG or other keys to it
										- Securely store user GPG encryption/signing keys to make it easier to use their keys in a secure way across devices
										- Store authentication GPG keys you can use for Secure Shell (SSH)
										- Using One-Time-Passwords (OTP) to login to websites or for two factor authentication (2FA)
									- Ensures no tampering occurs during delivery
									- Remove it when walking away from computer to lock it automatically
									- Eventually will also have:
									  collapsed:: true
										- Detecting tampering during shipping with tamper-evident boot enabled and configured on the laptop and Librem Key and each device shipped separately
										- Unlocking disk encryption (instead of having to enter a passphrase) when the Librem Key is inserted at boot
										- Locking the screen whenever the Librem Key is removed
										- Automatically logging the user into their desktop when the Librem Key is inserted
								- ((65a98a50-c7e6-4fd0-a9b0-01a6100bca7b))
								- Related: ((65a98a50-1b2c-445b-a236-c59a8bf037d0))
							- Librem Key assorted
							  collapsed:: true
								- Extended features that work exclusively with Purism’s Librem laptop line and other devices that support
								- Security
									- the keys include firmware developed by the company to verify its integrity, and make sure it hasn’t been tampered with.
									- It builds the firmware into a chip in a trusted environment, and then ships that off to the producer, the company said. This firmware also means you don’t necessarily have to trust the manufacturer
									- “The secure element hardware chip that we use is designed to resist physical attacks aimed at extracting firmware and secret key material,”
								- Use the Librem Key as a TPM work-alike
									- challenge response type mode that the key informs you about (based off totp?) so that you can say that the bios has validated itself to the key.
								- It’s a good practice to lock your computer whenever you step away from it but it can be tricky to remember to do it. Just remove your Librem Key and your desktop will lock automatically, protecting your system from snooping while you are gone.
							- https://puri.sm/products/librem-key/
							- Posts
							  collapsed:: true
								- [The Librem Key Makes Tamper Detection Easy – Purism](https://puri.sm/posts/the-librem-key-makes-tamper-detection-easy/)
								- https://puri.sm/posts/introducing-the-librem-key/
								- [Purism launches Librem Key, the first and only security key to offer tamper evident protection to laptop users – Purism](https://puri.sm/posts/purism-launches-librem-key-only-security-key-to-offer-tamper-evident-protection/#more-59326)
						- ORWL's Secure Key Fob
						  collapsed:: true
							- ORWL’s secure key fob works in the same way a smart card would for authentication, but with proximity detection. The key fob uses NFC and Bluetooth for authentication, but the ORWL team seems to have done this in a clever way. In general, security keys with wireless authentication either use NFC or Bluetooth to authenticate. Each scenario presents its own challenges.
							- NFC's range is too short (a few centimeters), so if you want the computer to lock itself after the key is no longer in range, that could cause some usability problems.
							- The alternative is to use Bluetooth, which typically has a range of up to 30 meters. This is also not ideal. Its long range means someone could also try to unlock it from a safe distance, which is the same reason  mobile payment systems use NFC rather than Bluetooth.
							- The ORWL team seems to have found a sweet spot by using both technologies: The device unlocks only through NFC, but it can remain unlocked as long as you’re in Bluetooth range.
						- Yubikey with ((635037c3-993a-4bfc-9c65-2157fd59a626)) 
						  collapsed:: true
						  Note: YubiKey just automatically types in a 60? digit password
							- https://github.com/adubois/qubes-app-linux-yubikey/blob/master/README.md
						- Nitrokey
						  id:: 65a98a50-1ef5-4f2d-b006-36f4a177b339
							- Nitrokey 3 supports Heads tamper detection
							  collapsed:: true
					- PureBoot
					  id:: 65a98a50-1b2c-445b-a236-c59a8bf037d0
					  collapsed:: true
						- 6 components currently
							- Neutralized and Disabled Intel Management Engine (see ((65a98a50-4556-4efc-ada0-d13c31ea6de4)) )
							- ((65a98a50-fc71-44f9-8e11-b19a5eca1c3b)) free software BIOS replacement
							- A Trusted Platform Module (TPM) chip
							- ((65a98a50-c7e6-4fd0-a9b0-01a6100bca7b)) our tamper-evident boot software that loads from within coreboot
								- ((65a98a50-60d2-4024-b15e-56e09ae9f64e))
								- Also compatible with Nitrokey 3
							- ((65a98a50-ffe0-428e-988a-6640ec3fc566)), our USB security token
							- Multi-factor authentication that unlocks disk encryption using the Librem Key
								- Strong protection against theft
								- ((65a98a50-ffe0-428e-988a-6640ec3fc566)) integrated with LUKS disk encryption
									- Once set up, you just need to boot with your Librem Key inserted, and when prompted enter the same Librem Key PIN you use for GPG encryption or signing. This means that, in order to unlock your disk, attackers need “something you have” (the Librem Key) and “something you know” (your Librem Key PIN).
									- If you lose your Librem Key you can always fall back to a recovery mode that prompts you for your old passphrase; you can set a strong fallback passphrase and store it somewhere safe, but use the Librem Key for convenience. For even more security, you can delete the recovery passphrase and only use the multi-factor authentication to unlock your disk.
								- https://docs.puri.sm/PureBoot/LibremKeyLUKS.html
								- They're upstreaming a script that enables LUKS drives to be decrypted by OpenPGP smartcards like the Librem Key (enter your GPG PIN instead of typing in your regular disk encryption passphrase)
								  https://docs.puri.sm/PureBoot/LibremKeyLUKS.html
						- [source] [PureBoot, the High Security Boot Process – Purism](https://puri.sm/posts/pureboot-the-high-security-boot-process/)
					- ORWL physical security (tamper proof)
						- Picking it up causes keys to be wiped
				- Remote attestation
					- ((644c0acf-58a1-4b82-9767-c88c65955315))
		- Overview: on degrees of freedom
		  collapsed:: true
			- Firmware (Libreboot)
			  collapsed:: true
				- Pros
				  collapsed:: true
					- What's wrong with UEFI Secure Boot?
						- Can't audit it, signing keys are controlled by vendors, doesn't handle hand off in all cases, depends on possible leaked keys.
				- Libreboot summary
				  collapsed:: true
				  means that the firmware is entirely Open-Source
					- Overview text + image
					  collapsed:: true
						- [The Purism Freedom Roadmap – Purism](https://puri.sm/learn/freedom-roadmap/) / https://puri.sm/wp-content/uploads/2015/07/purism-road-to-fsf-ryf-graphic-20150812-700x745.jpeg
						- Firmware:
							- Management Engine (ME)
							- Embedded Controller (EC)
							- Firmware Support Package (FSP)
							- Video BIOS (vBIOS)
							- BIOS & Board
						- If this stuff is freed then it gets the FSF Respects Your Freedom certification
					- Libreboot v Coreboot
					  Coreboot = open-source boot firmware
						- BIOS Firmware:
							- [coreboot](https://www.coreboot.org/)
							  id:: 65a98a50-fc71-44f9-8e11-b19a5eca1c3b
							  Still has binary blobs, like ((630f96f0-f2c4-4706-9d72-58e13201e03f))
							- [Libreboot – Free and Open Source BIOS/UEFI boot firmware](https://libreboot.org)
							  Blob free, supports a lot less devices, like ((644c0acf-e4e0-46a9-b103-ad20b97d8c09))
				- Purism progress towards Libreboot
				  collapsed:: true
				  https://puri.sm/learn/freedom-roadmap/ + https://puri.sm/posts/category/firmware/
					- we utilize Coreboot instead of a proprietary BIOS/UEFI, a huge advancement for current high-end laptops. Within Coreboot there is still some binaries, primarily the Intel Management Engine
					- ME can be neutralised and disabled
					  source:: https://puri.sm/learn/intel-me/ + https://puri.sm/posts/deep-dive-into-intel-me-disablement/
						- See [Disabling ](https://workflowy.com/#/9f284dc4783f)<a href="https://workflowy.com/#/9f284dc4783f">Intel</a><a href="https://workflowy.com/#/9f284dc4783f"> </a><a href="https://workflowy.com/#/9f284dc4783f">M</a><a href="https://workflowy.com/#/9f284dc4783f">E</a>
						- Neutralized ME: the ME is neutralized/neutered by removing the most “mission-critical” components from it, such as the kernel and network stack.
						- Disabled ME: the ME is officially “disabled” and is known to be completely stopped and non-functional
						- Removed ME: the ME is completely removed and doesn’t execute anything at any time, at all.
					- FSP not yet
				- In-depth
				  https://blog.invisiblethings.org/papers/2015/x86_harmful.pdf
				-
				- Level 1: Qubes Certified Laptop. In addition to meeting all the requirements of Level 0, this laptop will also have to conform to our updated requirements for Qubes 4.x certification.
				  https://www.qubes-os.org/news/2017/07/08/toward-a-reasonably-secure-laptop/
				- [[Libreboot – Frequently Asked Questions about Libreboot firmware](https://libreboot.org/faq.html#intel](https://libreboot.org/faq.html#intel))
				- 2021 - liberated Embedded Controller
				  [https://puri.sm/posts/librem-14-adding-librem-ec-freed-embedded-controller-firmware/](https://puri.sm/posts/librem-14-adding-librem-ec-freed-embedded-controller-firmware/)
				- AMD openSIL
				  id:: 66f330f0-17f8-4fd2-aece-e6634a4c324d
					- Basically ((65a98a50-fc71-44f9-8e11-b19a5eca1c3b)) alternative
					- [AMD Reveals Latest Plans For Open-Source openSIL With Replacing AGESA, Zen 6 Milestone - Phoronix](https://www.phoronix.com/news/AMD-openSIL-September-2024)
					- likely with [Zen 6](https://en.wikipedia.org/wiki/Zen_6) (probably 2026)
			- OR ((65a98a50-7f84-47be-bc67-1ef4c2f5dcef))
			- The War on General Purpose Computing (2015)
			  id:: 66cd7dcb-f379-4220-a85d-3f658bd940d0
			  `/home/boss/Videos/2-Complete/cory-doctorow-f2015-hq.mp4`
				- [The War on General Purpose Computing (2015) [video] | Hacker News](https://news.ycombinator.com/item?id=33854184)
				-
		- Libre hardware / Open Source Hardware (OSHW)
		  id:: 65a98a50-7abf-48cc-a42b-8f5c7a25ae7d
		  collapsed:: true
		  #IL-0011
			- Open-source Hardware
			  collapsed:: true
			  FOSH, Open Source Hardware
				- [https://www.crowdsupply.com/open-hardware](https://www.crowdsupply.com/open-hardware)
				- $1500 MNT Reform
				  collapsed:: true
					- [https://www.crowdsupply.com/mnt/reform](https://www.crowdsupply.com/mnt/reform)
					- OSHWA certified laptop
					- Features
						- ARM CPU
						- 1 TB NVMe SSD
						- With Reform, you get KiCAD design files with components that you can buy from Mouser or Digikey, and standard batteries that you can get from multiple distributors. Also, it has a backlit mechanical keyboard with OLED and an optical trackball which are fully OSHW. System software is tested and built by us. The case is milled from high quality anodized aluminum. We are trying to run a sustainable small business around quality OSHW, this is not possible with dumping prices.
						-
				- $565 Precursor (RISC-V)
				  collapsed:: true
					- [https://www.crowdsupply.com/sutajio-kosagi/precursor](https://www.crowdsupply.com/sutajio-kosagi/precursor)
					- [https://linuxsmartphones.com/precursor-open-mobile-hardware-up-for-pre-order-for-450-and-up-crowdfunding/](https://linuxsmartphones.com/precursor-open-mobile-hardware-up-for-pre-order-for-450-and-up-crowdfunding/)
				- Novena
				  collapsed:: true
				  Open hardware. 4GB RAM.
					- And Novena (weird design but has tons of connection ports too)
					- https://www.crowdsupply.com/sutajio-kosagi/novena
				- Accessories
				  collapsed:: true
					- Ultimate Hacking Keyboard
					  collapsed:: true
						- [https://www.crowdsupply.com/ugl/ultimate-hacking-keyboard](https://www.crowdsupply.com/ugl/ultimate-hacking-keyboard)
						- [https://ultimatehackingkeyboard.com/](https://ultimatehackingkeyboard.com/)
						- Features
							- Splits into two parts for improved ergonomics
							- Can be programmed with multiple modes for use with different contexts eg different key mapping for games
							- Not wide - doesn't have the number pad stuff on the right side
							- Can move the mouse via keyboard keys
						- Agent for UHK (keyboard remapper software)
							- [https://ultimatehackingkeyboard.github.io/agent](https://ultimatehackingkeyboard.github.io/agent)
							- [https://github.com/UltimateHackingKeyboard/agent](https://github.com/UltimateHackingKeyboard/agent)
			- Why
			  collapsed:: true
				- China put tiny chips in all processors to backdoor them
				  collapsed:: true
					- https://www.zerohedge.com/news/2018-10-04/explosive-report-details-chinese-infiltration-apple-amazon-and-cia
					- The Big Hack: How China Used a Tiny Chip to Infiltrate U.S. Companies
					- https://www.bloomberg.com/news/features/...nd=premium
					- https://www.zerohedge.com/news/2018-10-0...on-and-cia
					- The attack by Chinese spies reached almost 30 U.S. companies, including Amazon and Apple, by compromising America’s technology supply chain, according to extensive interviews with government and corporate sources.
					- in addition to efforts designed to sway US elections, China' intelligence community orchestrated a pervasive infiltration of servers used to power everything from MRI machines to the drones used by the CIA and army. They accomplished this using a tiny microchip no bigger than a grain of rice.
					- Nested on the servers’ motherboards, the testers found a tiny microchip, not much bigger than a grain of rice, that wasn’t part of the boards’ original design. Amazon reported the discovery to U.S. authorities, sending a shudder through the intelligence community. Elemental’s servers could be found in Department of Defense data centers, the CIA’s drone operations, and the onboard networks of Navy warships. And Elemental was just one of hundreds of Supermicro customers.
					- During the ensuing top-secret probe, which remains open more than three years later, investigators determined that the chips allowed the attackers to create a stealth doorway into any network that included the altered machines. Multiple people familiar with the matter say investigators found that the chips had been inserted at factories run by manufacturing subcontractors in China.
			- Processor Architectures
			  collapsed:: true
				- Libre
					- OpenPOWER by IBM
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Pros
								- Free processors vs proprietary current leaders
								  collapsed:: true
									- Cheaper - all firmware source code for OpenPOWER machines has been released, meaning that unlike x86 you don’t have to pay a third party to create libre firmware for POWER machines!
									- Overview of OpenPOWER and the state of libre hardware
									  [archived] https://www.crowdsupply.com/raptor-computing-systems/talos-secure-workstation/updates/a-word-on-lockdown
								- Very difficult to have a hardware backdoor since it's in a fixed state from the factory
								  collapsed:: true
									- Not unless IBM wants to deal with a scandal. The mask used for producing the CPU is fixed, takes billions to develop, and cannot be updated with arbitrary microcode. That's the beauty of the design. It's fixed from the factory. If a flaw that was purposely baked in by direction of the NSA was found... IBM would have a stupidly expensive recall on their hands.
									- The rest of the mainboard is checked over by Raptor, and given their history working with the open source community... I'm willing to trust them.
								- OpenPOWER Foundation now allows for some free implementations
								  collapsed:: true
									- Power.org is still the governing body around the Power Architecture instruction set but specific implementations are now free to use under a liberal license granted by IBM
									- http://openpowerfoundation.org/
									- https://github.com/open-power
									-
								- POWER 8/9 produces the most powerful, open-source chips
								  collapsed:: true
									- So far no desktop or even mobile-class CPUs with this architecture are available, though they will probably arrive soon.
							- Cons
								- It's nonfree despite being open-source - chips that you are not allowed to implement and publish yourself unless you have a license
								  collapsed:: true
									- Its hostile to the actual open-hardware and never really change the industry in the way we want.
									- Which is the advantage of the "benevolent dictator for life" model, in this case the "benevolent dictator" being IBM.
									- Similarly Blu Ray discs are an open standard and have their own foundation attached with multiple companies, but that doesn't mean it's GPL and free-to-use for everyone.
								- Since RISC-V is totally open, proprietary extensions may end up becoming the de-facto standard *by design*, thus killing the openness in practice
								  collapsed:: true
									- Situations where proprietary extensions became the norm
										- XMPP - many messengers derived from that like WhatsApp
										  source:: https://news.ycombinator.com/item?id=13219925
											- Though it could be because XMPP was a messy fractured standard
										- Chromium - Google Chrome is by far the most popular
											- Though this was engineered from the beginning that way, plus there are competitors like Brave and Vivaldi
									- Situations where it didn't
										- Linux - most distros are free
						- Manufacturers
						  collapsed:: true
							- Raptor Computing
							  id:: 635037c3-a289-4f58-af14-6efccdb6b003
								- [https://raptorcs.com/content/base/products.html](https://raptorcs.com/content/base/products.html)
								- $15k Talos II POWER8/9
								  collapsed:: true
									- POWER9, when released late next year, will continue this unprecedented level of open access to OpenPOWER systems, however without POWER8 based systems such as our Talos™ first, the only truly open production POWER9 systems may very well be high-end server machines with a $15,000 USD or higher retail price, as was the case for POWER8. Furthermore, as will be detailed in a future update, only Talos™ contains the novel security hardware required to not only enable fully owner-controlled secure boot, but mitigate hardware attacks and restore the TPM as a useful, owner-controlled platform integrity verification tool.
									- As such, it is vital that the libre software community, and specifically those working on large projects like Chromium, the Linux kernel, Firefox, LibreOffice, gcc, clang, GIMP, MySQL, and Xorg, rallies behind the only libre hardware powerful enough to enable development of those projects. Unless this is done, and soon, libre software will slowly fade as we slowly accept a greater level of proprietary software just to retain access to machines capable of compiling these projects, and as more and more of libre software’s core functionality is taken over by the ever-expanding, proprietary platform firmware (which is currently an operating system or at least a hypervisor in is own right!)
								- $7k Talos
								  collapsed:: true
								  Up to 256 GB RAM, Up to 96 logical cores
									- https://www.crowdsupply.com/raptor-computing-systems/talos-secure-workstation
									- CPU of your choice, 128 GB of DDR3 ECC RAM, an AMD Radeon RX 480 (8 GB VRAM) GPU, and two Western Digital WD40EFRX 4 TB SATA drives, all installed in a heavy-duty tower chassis
									- Overview of why Talos is the only possible high-spec motherboard
									- https://www.crowdsupply.com/raptor-computing-systems/talos-secure-workstation/updates/a-word-on-lockdown
								- $1.6k Talos II Lite
								- <$1.6k "Blackbird"
								  collapsed:: true
									- A new POWER9 powered mainboard for Linux desktops was just announced today at OPENPOWER Europe, codenamed Blackbird.
									  https://reddit.com/comments/9lbs0n
									- $1k POWER9 Blackbird https://reddit.com/comments/9zy8q1/comment/eacxat0?context=3
								- 1 Backlink
								  collapsed:: true
									- [Raptor Computing](https://workflowy.com/#/d35eba0a138c) POWER9 is expensive but it can virtualise x86 via KVM/QEMU
						- Background
						  collapsed:: true
							- POWER9 is the 9th generation of the POWER architecture which is mainly used for supercomputers and specialty servers and workstations. For a while Apple used a variant of the POWER architecture called PowerPC for its computers before Apple switched to Intel when IBM wasn't progressing their designs fast enough. Xbox 360 too. Nintendo too with Broadway and Gecko in GameCube, Wii and Wii-U. Also, Sony with the Cell in the PS3.
							- These days the POWER architecture is fairly open, via the OpenPOWER Foundation, which means that anyone can license the architecture and organizations besides IBM can contribute to the POWER architecture through the foundation.
						- ---
						- https://wiki.ubuntu.com/ppc64el
					- RISC-V
					  collapsed:: true
						- Overview
							- RISC-V has been described as the “Linux” of processors. RISC-V is a free, open, extensible instruction set architecture (ISA) invented by the co-founders of SiFive. The RISC-V specification is now maintained by the nonprofit RISC-V Foundation, whose membership has increased more than six-fold since 2015 and now consists of over 100 members, including some of the largest companies in the world.
						- Links
							- https://www.reddit.com/r/RISCV/
						- Pros/Cons
							- Pros
								- Simple, free and open – lower IP costs
								- Architected for security and customization
								- Established and growing software ecosystem fostered by many, not one
								- Freedom to specialize, optimize, and differentiate
								- Open-source
							- Cons
								- Needs security features implemented that eg Librem 5 doesn't have
								  #Phone https://workflowy.com/#/5b204fa12905
							- Roadmap
						- Products
							- HiFive Unleashed by SiFive
							  collapsed:: true
								- SiFive
									- Founded by the creators of RISC-V
									- Most experience in taping out RISC-V chips
									- Leadership role on RISC-V Foundation committees and specifications
								- https://www.crowdsupply.com/sifive/hifive-unleashed#products-top
								- $999, ships November 2018
								- world's first and only Linux-capable, RISC-V-based development board.
								- 64-bit, Linux-capable system-on-chip (SoC) platform.
								- Features
									- SiFive Freedom U540 SoC (CPU)
									- 8 GB DDR4 with ECC
								- Benchmarks
								  https://www.phoronix.com/scan.php?page=news_item&px=SiFive-RISC-V-Initial-Benchmark
									- Can run Quake 2
									  https://www.youtube.com/watch?v=L8jqGOgCy5M
							- $565 Precursor (phone shape)
							  collapsed:: true
								- [https://www.crowdsupply.com/sutajio-kosagi/precursor](https://www.crowdsupply.com/sutajio-kosagi/precursor)
								- Performances
									- Its RISC-V softcore is 25x as fast as a GameBoy, about 6x as fast as a GBA, and somewhere close to about par with a DS-lite, so... plenty of power for lots of people. Besides, its main chip is an FPGA meaning you can put whatever (modest) core fits your needs on it.
									- FPGA instead of a traditional CPU, allowing you to program the chip to emulate different types of processors for different applications.
									-
				- Proprietary
					- Intel (x86-64)
					  collapsed:: true
					  AKA x64, x86_64, AMD64 and Intel 64) is the 64-bit version of the x86 instruction set.
						- Cons
							- Meltdown and Spectre bugs affected billions of devices
							  https://www.zdnet.com/article/security-flaws-affect-every-intel-chip-since-1995-arm-processors-vulnerable/
					- ARM (though they license out to many manufacturers)
					  collapsed:: true
						- Qualcomm supplies the baseband processor as well as licenses its technology for others to manufacture the processor.  ARM license the design architecture for mobile processors, including Qualcomm.
			- _Consumer performance_
			  collapsed:: true
			  e.g. 64GB or less RAM
				- [Framework](https://frame.work) brand
				  id:: 646b3419-9713-4a78-9833-0e4ec0cb1c6d
				  collapsed:: true
					- Pros/Cons
						- Pros
							- ((659d093f-bf67-444a-b2a1-ec0a28907583)) modularity has been impressive
						- Cons
							- If you are happy with ((67c095e1-f226-4386-b0c2-e9c43737c6ee)) then those are more modular and better value
							- ((67be2e09-ff30-41a9-b488-7dba6e7ed7c5)) launch was a bit disappointing ((635037c3-27fc-4bd1-8958-5c3c8d2d46bb)) is not very modular, and ((67c061a9-3317-45ba-8859-b86760f2a382))'s screen could have been a Framework 13 part. Was decent though
						- Unclear
							- [Coreboot for their Chromebook model, but not others yet](https://community.frame.work/t/responded-coreboot-on-the-framework-laptop/791)
						- Comparisons
					- # Products
						- ## Priority
						  id:: 67be309f-c8e5-49dd-acd8-536f5654e32b
							- PTM7958 phase change thermal interface material or [combo heatsink + fan + paste](https://frame.work/gb/en/products/heatsink-and-fan-kit?v=FRANTC0001)
							  id:: 67be31be-7826-40a3-8668-b7b737f59d50
								- [[2025-03-11 Tuesday]] Email support request confirmed that The Heatsink for the Ryzen™ AI 300 Series is not compatible with the Ryzen™ 7040 Series mainboard. Reason being is it is physically different die sizes.
									- Also the Ryzen™ AI 300 Series Mainboards would be using ((65f5b987-b9ba-474a-937c-f2c26770de85))
							- [Framework | Hinge Kit (2nd Gen) - 3.5kg](https://frame.work/gb/en/products/hinge-kit-2nd-gen-3-5kg)
							- [£160 matte display](https://frame.work/gb/en/products/display-kit?v=FRANGX0001) - would work better in sunlight
							- ((67be2e4f-e0d4-4fce-b28e-892f187980e7)) mainboard
						- ## All
							- ### [[2025-02-25 Tuesday]] New products
							  id:: 67be2e09-ff30-41a9-b488-7dba6e7ed7c5
								- [Framework Laptop 13 powered by AMD Ryzen AI 300 series](https://community.frame.work/t/introducing-the-framework-laptop-13-powered-by-amd-ryzen-ai-300-series/65007) (2025)
								  id:: 67be306c-e648-4944-ba0d-519e57c36e36
								  collapsed:: true
									- Pros/Cons
										- Pros
											- Performance looks okay in games, mostly on Low settings [Worlds fastest iGPU: Radeon 890m in 31 Games // Ryzen AI 9 HX 370 - YouTube](https://youtu.be/wF3ANpqBZ04)
											-
										- Cons
											-
										- Unclear
										- Comparisons
									- Announcement
										- First, the biggest change is of course our move to AMD’s new Ryzen AI 300 Series processors, which bring a fantastic jump in performance. These use Zen 5 CPU cores along with Radeon RDNA 3.5 graphics. In addition to 6-core Ryzen 5 and 8-core Ryzen 7 configurations, for the first time, we also have a top-end Ryzen 9 HX 370 option that brings 12 CPU cores at up to 5.1GHz boost and 16 GPU cores. That means you can play modern game titles at a surprising framerate. Historically, this level of graphics performance would have needed a discrete GPU, and it’s amazing to see it now in an ultraportable, efficient laptop. Because this processor also has a 50 TOPS NPU, it supports Copilot+ and an increasing number of ROCm-compatible open source AI toolkits.
										- Alongside that performance, we’ve kept the system quiet and cool with a revamped thermal system. This now leverages one large 10mm heatpipe and Honeywell’s awesome PTM7958 phase change thermal interface material. Also on the Mainboard, we’ve kept support for two slots of DDR5-5600 memory, upgradeable to 96GB, and one PCIe 4 M.2 2280 storage slot, upgradeable to 8TB. We’ve additionally brought connectivity up to Wi-Fi 7 using AMD’s RZ717 module. Finally, on the four Expansion Card slots, the rear two support USB4 and both of the front two now handle USB 3.2 plus DisplayPort, enabling up to four simultaneous display outputs.
										-
									- 13" parts
										- Framework Laptop 13 Mainboard (AMD Ryzen™ AI 300 Series)
											- £699 Ryzen™ AI 7 350
												- [Review of CPU in a different PC](https://www.youtube.com/watch?v=bT4lyXoGySQ)
											- £999 Ryzen™ AI 9 HX 370
											  id:: 67be2e4f-e0d4-4fce-b28e-892f187980e7
												- [31 games test](https://youtu.be/wF3ANpqBZ04)
												- [35168](https://www.cpubenchmark.net/cpu_lookup.php?cpu=AMD+Ryzen+AI+9+HX+370&id=6143) ((67caaf64-390f-4469-a55f-a66d630fcc87)) : ((67caaf7b-8c0e-4988-856e-d843110c1177))
												  id:: 67ca0922-9429-47ba-b36c-3282172e7379
													- 40% better than ((659d093f-bf67-444a-b2a1-ec0a28907583)) : ((66705c8f-4f0c-41ba-8a41-e617c684b43d))
													  id:: 67cab8fc-1781-415a-8c39-281a53159630
													- [[2025-03-07 Friday]] Equivalent to Apple M3 Max 14 Core, or Apple M4 Pro 12 Core
														- Trails behind the M4 Pro 14 Core, M4 Max 14 Core, M3 Max 16 Core, M4 Max 16 Core
														- Best AMD CPUs are even better: AMD Ryzen 9 7940HX, whilst AMD Ryzen 7 7840HX is equally as good as M4 Max 16 Core
														- Only the single desktop class Apple CPU is better: M2 Ultra 24 Core
								- [Framework Laptop 12](https://frame.work/gb/en/laptop12) (2025)
								  id:: 67c061a9-3317-45ba-8859-b86760f2a382
								  collapsed:: true
								- [Framework Desktop](https://frame.work/gb/en/desktop) (2025)
								  id:: 635037c3-27fc-4bd1-8958-5c3c8d2d46bb
								  collapsed:: true
									- Pros/Cons
										- Pros
											- 96-120GB RAM/VRAM for relatively cheap
												- Excellent for LLM usage
												- Unlike Nvidia/AMD graphics cards which only offer low VRAM (16GB?) this offers much much more
										- Cons
											- PCIe x4 slot, not x16
											-
										- Unclear
											- Mini-ITX motherboard
											- Uses Halo Strix series APU. Can't be used on current motherboards and requires soldered lpdd RAM
												- Pros
													- Most powerful APUs i.e. CPU with iGPU
													- Comparable performance to modern GPUs whilst being smaller, only needing one fan
													- Great CPU performance
														- "AMD Strix Halo Ryzen Al MAX 385+ laptop chip matches the desktop Ryzen 9 7950X in leaked benchmark — 16-core APU rumored to power Asus' upcoming ROG Flow Z13 laptop"
													- "This APU (with integrated graphics) is faster than my existing gaming laptop, with a dedicated graphics card"
												- Cons
													- Soldered RAM
													- Non-socketed CPU (AM5 is other chips in this gen?)
													- Similar power consumption to a CPU and dGPU
												- Unclear
										- Comparisons
											- ASUS ROG Flow Z13 (2025) also uses the same APU
												- [ASUS ROG Flow Z13 (2025): AMD Strix Halo = POWERFUL tablet - YouTube](https://youtu.be/CcGuyL9MU90)
													- Tablet with magnetic attachable keyboard
													- Unsure if it's touchscreen
													- Unsure if it's got Linux support
													- Unsure if
														- Has it got any Thunderbolt or USB4 support
														- Battery life
														- "It has the extra m2 nvme port outside" - which should allow ((67c18f4c-711a-4b40-b1f1-8518f5d63f87))
									- Pricing
										- £2k - Max+ 395 - 128GB RAM
										- £1.6k - Max+ 395 - 64GB
										- £1.1k - Max 385 - 32GB
									- Very powerful iGPU, comparable to modern GPUs
										- [Ryzen Ai Max+ 395 with Radeon 8060S graphics can run Cyberpunk 2077 on Ultra](https://www.youtube.com/watch?v=W9qwQzfLN0k)
											- This isn't AM5
							- Framework 16 (2023)
							  id:: 67c1a6ab-9556-4e3a-85fd-b5cd5373161f
							- Framework Laptop 13 Intel Ultra (2024)
							  collapsed:: true
								- [Intel Ultra 7 165H](https://www.intel.com/content/www/us/en/products/sku/236851/intel-core-ultra-7-processor-165h-24m-cache-up-to-5-00-ghz/specifications.html)
									- ((67ca30ab-afb2-49e5-9797-06d60905fed8))
							- [Framework Laptop 13 AMD Ryzen 7 7840U](https://frame.work/gb/en/products/laptop-diy-13-gen-amd?q=processor) (2023)
							  id:: 659d093f-bf67-444a-b2a1-ec0a28907583
							  collapsed:: true
								- Pros/Cons
								  id:: 65b16a2e-8f9b-4b45-985a-67b7861f063e
									- Pros
										- [Similar performance to Framework 16](https://www.phoronix.com/review/framework-laptop-16)
										- [Can play](https://www.reddit.com/r/framework/comments/18kilr4/well_im_impressed_gaming_fw13_ryzen_7) ((634bc201-ab66-494b-8738-826601b04f57)) seemingly
										- Freezes with [[Logseq]] are much shorter than with ((65a98a50-4b57-4816-931f-24253c6bc8b7))
									- Cons
										- Lacks
										  id:: 67c0e912-af58-47cb-af08-40a03edffb99
											- Better CPU performance and cooling of ((67be306c-e648-4944-ba0d-519e57c36e36))
											- Better display
												- Battery life of ((666ac10e-deb2-4d3f-b8ec-ecd66b91410d)) displays
												- 360 hinge and touchscreen like ((67c061a9-3317-45ba-8859-b86760f2a382))
											- ((65a98a50-4aa2-4711-b646-b82d371d2d99)) e.g. ((65a98a50-1b2c-445b-a236-c59a8bf037d0))
											- Radio killswitch like ((635037c2-64f1-4e71-8d24-a106302e2036))
											- Standardisation of ((65a98a50-fc71-44f9-8e11-b19a5eca1c3b)) or ((66f330f0-17f8-4fd2-aece-e6634a4c324d))
												- [2025 Coreboot initial support](https://blogs.coreboot.org/blog/2024/05/23/coreboot-24-05-release/)
											- ((67c18f4c-711a-4b40-b1f1-8518f5d63f87)) port for better eGPU performance
											- Battery life of ARM chips (though reduced software compatibility)
											- [Doesn't support](https://community.frame.work/t/responded-enable-s3-sleep/48611) ((63734d15-b4d4-4c85-8087-b02150a85f59)). No modern AMD or Intel processor supports it
											  id:: 66d9a1dc-5ea7-4ea0-99cc-f0f61e208002
											  collapsed:: true
												- `cat /sys/power/mem_sleep`
													- [[2025-02-27 Thursday]] shows only s2idle available. s2 is selected `[s2idle]` ((65a98a51-3c68-4866-8f78-d7fec684f7b0))
												- [scripts/amd_s2idle.py · master · drm / amd · GitLab](https://gitlab.freedesktop.org/drm/amd/-/blob/master/scripts/amd_s2idle.py) can be used to check support
											- Related: ((67c095e2-f716-4fe8-b37e-3bfa0bf7f536))
									- Unclear
										- [CPU benchmark](https://www.cpubenchmark.net/cpu_lookup.php?cpu=AMD+Ryzen+7+7840U&id=5322) is decent but not the highest tier
										  collapsed:: true
											- [[2025-02-27 Thursday]] it's my biggest limiter with gaming
											- Zen 5 ((65ed913e-a800-4c75-9493-ec51705c63eb)) coming out in 2024, expected 20-30% performance boost. But it'll likely be a year longer until it's available in commercial laptops
											- [Gaming on the AMD Framework 13! Native, Docked & eGPU Performance. - YouTube](https://youtu.be/zo3nze33hfo)
											-
									- Comparisons
										- ((659d093f-bf67-444a-b2a1-ec0a28907583)) vs ((65a98a50-4b57-4816-931f-24253c6bc8b7))
											- For ((659d093f-bf67-444a-b2a1-ec0a28907583))
												-
											- For ((65a98a50-4b57-4816-931f-24253c6bc8b7))
												-
								- Purchased [[2024-03-10 Sunday]]
								  id:: 65edb146-02fa-4df0-be3b-f07e00b2f49d
								  collapsed:: true
									- [Framework 13.5 AMD Ryzen 7 7840U (2023)](https://www.notebookcheck.net/Framework-Laptop-13-5-Ryzen-7-7840U-review-So-much-better-than-the-Intel-version.756613.0.html#)
									  collapsed:: true
										- £1397 total price
											- £1169 System: AMD Ryzen™ 7 7840U
											- £49 Power adapter 60W
											- Expansion Cards
												- £125 1TB storage
												- £9 each for USB-A (x2), and USB-C (x4)
										- £6 [10x 15mm diameter circle magnets](https://www.amazon.co.uk/gp/product/B0BTM2T26N/ref=ox_sc_act_title_1?smid=AQUPIURIVJJDR&psc=1) (for ((64e0946d-1d0e-4824-b150-1a08f26aba23)) )
										- £243 [2x32GB RAM DDR5 5600MHz](https://www.amazon.co.uk/gp/product/B0BLTG7TN6/ref=ox_sc_act_title_2?smid=A3P5ROKL5A1OLE&psc=1) SO-DIMM
										  id:: 65edb6d4-f948-4c67-99da-3d376b9cffde
									- Cost of [just the mainboard](https://frame.work/gb/en/products/mainboard-amd-ryzen-7040-series?v=FRANGV0007): £649 [[2024-07-12 Friday]]
									  id:: 6690d275-01c1-4a3f-9f82-ae9f8d0b15e5
										- Note: [Wi-Fi module](https://frame.work/gb/en/products/amd-rz616-wi-fi-6e) is separate
									- Reasoning: ((65a98a50-3faa-4fa7-93cd-cc5cd081e1dd))
								- Old info
								  id:: 633b7502-e028-4ccf-b3b3-ce8481a5ab16
								  collapsed:: true
									- Rembrandt series (Ryzen 6000) has both USB4 and DDR5 support, Zen3+ and RDNA2 GPU under 6nm. PCIe4 minimum, possible PCIe5
									- Example laptop with 6000 series - ROG Strix G15 (2022)
									  [https://rog.asus.com/us/laptops/rog-strix/rog-strix-g15-2022-series/](https://rog.asus.com/us/laptops/rog-strix/rog-strix-g15-2022-series/)
									- [https://egpu.io/gsearch/?q=Ryzen](https://egpu.io/gsearch/?q=Ryzen)
									- AMD Ryzen 6000 + 7000
									  collapsed:: true
										- Both support USB 4
										- 6000 = for notebooks, mobile processors. Zen3+
											- https://www.xda-developers.com/amd-ryzen-6000/
										- 7000 = desktop CPUs
											- https://www.xda-developers.com/amd-ryzen-7000/
								- # Documentation
									- ## Specs
									  id:: 66705c8f-4f0c-41ba-8a41-e617c684b43d
										- ### Hardware
										  collapsed:: true
											- **Model:** Framework 13 AMD (2023)
											- **CPU:** [AMD Ryzen™ 7 7840U](https://www.amd.com/en/products/processors/laptop/ryzen/7000-series/amd-ryzen-7-7840u.html)
											  id:: 47c8fdb5-a1f7-4575-b6d8-21380d05c0e3
												- [24953](https://www.cpubenchmark.net/cpu.php?cpu=AMD+Ryzen+7+7840U&id=5322) ((67caaf64-390f-4469-a55f-a66d630fcc87)) : ((67caaf7b-8c0e-4988-856e-d843110c1177))
												- [57.5%](https://cpu.userbenchmark.com/SpeedTest/2134268/AMD-Ryzen-7-7840U-w-Radeon-780M-Graphics) ((67cab2ce-97ab-49e7-9f60-2e17788140b7)) : ((67cab2de-db8f-4c0a-b991-4b07cc88c424))
											- **SSD:** 4TB M.2 PCIe NVMe
											- **RAM:** 64B DDR5 5600MHz
												- ((65edb6d4-f948-4c67-99da-3d376b9cffde))
											- **iGPU:** AMD Radeon 780M Graphics
											- **Display:** [BOE NE135FBM-N41](https://www.panelook.com/NE135FBM-N41_BOE_13.5_LCM_overview_44979.html)
											  collapsed:: true
												- Luminance: 415 cd/m² (Typ.)
												  AKA Brightness: 415 nits
											- **Interfaces:**
												- Slot compatibility
												  collapsed:: true
													- ![image.png](../assets/image_1710405242016_0.png)
													- [Interfaces](https://frame.work/gb/en/laptop13?tab=specs&slug=laptop-diy-13-gen-amd)
														- Supporting USB4/DP for upper left and right slots, USB 3.2/DP for lower right slot and USB 3.2 only for lower left slot, along with USB-C power input on all four slots
												- According to ((47c8fdb5-a1f7-4575-b6d8-21380d05c0e3))
													- Native USB 4 (40Gbps): 2
														- i.e. equivalent to ((67ca30ab-afb2-49e5-9797-06d60905fed8))
													- Native USB 3.2 Gen 2 (10Gbps): 2
													- Native USB 2.0 (480Mbps): 4
										- ### Firmware
											- BIOS
											  collapsed:: true
												- # Framework BIOS Setup/Boot Keys
													- F2: enter BIOS
													- F12: one-time boot override
													- F10: AMT setup (i7-1185G7 only)
												- Alternatively `systemctl reboot --firmware-setup`
												- ## BIOS Shortcuts
													- F1: Help
													- Esc: Exit
													- ↑↓: Select Item
													- ←→: Select Item
													- F5F6: Change Values
													- Enter: Select / Enter SubMenu
													- F9: Setup Defaults
													- F10: Save and Exit
										- ### Software
											- **Distro:** ((62e11d87-874f-4112-8bd5-a0a8f6651248)) 24.10
											- **Kernel:** 6.11
											- **GPU Driver:** 4.6 Mesa 24.2.8
											  `glxinfo | grep "OpenGL version"`
									- ## Additional parts used
										- 2x [Crucial RAM 32GB DDR5 5600MHz](https://www.amazon.co.uk/dp/B0BLTDTD86)
										- [Crucial P3 Plus SSD 4TB M.2 NVMe PCIe Gen4 Internal SSD](https://www.amazon.co.uk/dp/B0CCNCW5QX)
									- ## Setup
										- [Check BIOS version](https://knowledgebase.frame.work/en_us/how-to-check-the-bios-version-on-windows-linux-bios-ryupu8HT3)
										  collapsed:: true
											- ```bash
											  sudo apt install lshw dmidecode -y && sudo dmidecode | grep -A3 'Vendor:\|Product:' && sudo lshw -C cpu | grep -A3 'product:\|vendor:'
											  ```
											- Initial output
												- ```
												  Vendor: INSYDE Corp.
												  Version: 03.03
												  Release Date: 10/17/2023
												  Address: 0xE0000
												  product: AMD Ryzen 7 7840U w/ Radeon  780M Graphics
												  vendor: Advanced Micro Devices [AMD]
												  physical id: 4
												  bus info: cpu@0
												  version: 25.116.1
												  ```
										- [Latest BIOS](https://knowledgebase.frame.work/framework-laptop-bios-and-driver-releases-amd-ryzen-7040-series-r1rXGVL16)
										- [Updating BIOS](https://knowledgebase.frame.work/en_us/updating-bios-on-linux-Hk4pROTn)
										  collapsed:: true
											- ```bash
											  fwupdmgr refresh --force
											  fwupdmgr get-updates
											  fwupdmgr update
											  ```
										- https://github.com/FrameworkComputer/linux-docs/blob/main/ubuntu-22.04-amd-fw13.md
										- [Ubuntu 22.04 LTS Installation on the Framework Laptop 13 - Framework Guides](https://guides.frame.work/Guide/Ubuntu+22.04+LTS+Installation+on+the+Framework+Laptop+13/109)
										- [[Announcement] Linux on your Framework Laptop 13 (AMD Ryzen 7040 Series) - Linux - Framework Community](https://community.frame.work/t/announcement-linux-on-your-framework-laptop-13-amd-ryzen-7040-series/37367)
									- ## Manuals
										- [Heatsink and Fan Replacement Guide - Framework Guides](https://guides.frame.work/Guide/Heatsink+and+Fan+Replacement+Guide/84?lang=en)
										- [Mainboard Replacement Guide - Framework Guides](https://guides.frame.work/Guide/Mainboard+Replacement+Guide/79?lang=en)
									- ## To-do
										- Consider ((6690d275-01c1-4a3f-9f82-ae9f8d0b15e5))
										- [Optimizing Ubuntu Battery Life](https://knowledgebase.frame.work/en_us/optimizing-ubuntu-battery-life-Sye_48Lg3)
										  id:: 65f58ba7-8f56-4aa1-9d1d-cd54cfbccfe1
											- [GitHub - linrunner/TLP: TLP - Optimize Linux Laptop Battery Life](https://github.com/linrunner/TLP)
									- ## Troubleshooting
									  id:: 6655e59f-8ed3-4d3c-ad5b-ce5b86e16fd6
										- [[2024-03-28 Thursday]] My issues (on ((62e11d87-874f-4112-8bd5-a0a8f6651248)) 23.10)
										  id:: 65f59503-83a9-451a-a81c-847f10cdf041
											- ## Resolved
												- [[2024-03-28 Thursday]] Laptop waking from sleep
												  collapsed:: true
												  **Conclusion:** Seems to have resolved itself with my upgrade to 24.10 [[2024-10-15 Tuesday]]
													- Random wakes from sleep
														- [[2024-04-17 Wednesday]] Gets resolved by unplugging my USB C hub prior to sleep
													- Possible culprits
														- High wakeup events according to `sudo powertop`
															- `gpu-screen-recorder`
															- Discord
															- Logseq
														- ((66050895-b586-4220-9084-8abbe1563644))
													- Failed investigations
														- `journalctl -e` wasn't very helpful, didn't have any obvious culprits
														- BIOS - nothing like "wake on keyboard" or "wake on USB" settings
														- `sudo dmidecode | grep Wake-up`
															- Says it was woken by Power Switch, which wasn't clicked
													- Related: ((65a98a51-b70f-4593-8e37-20938de20589))
												- High temperature/loud fans
												  id:: 65f55d09-db7e-4dcd-9e9f-70ab09c2a383
												  collapsed:: true
												  **Conclusion:** Actually due to ((63a9adf9-dcc0-4caa-a0da-f495b1d63abc)) using 6% CPU continuously at times, and ((6313458c-20f9-43f5-be52-44845eb02203)) linearly scaling CPU and playback speed
													- Related threads
														- [High temperature/fan constant and loud](https://community.frame.work/t/high-temperature-loud-fan-on-amd-ryzen/47078)
														- [FW ryzen idle temperature - Framework Laptop 13 - Framework Community](https://community.frame.work/t/fw-ryzen-idle-temperature/41604)
														- [[TRACKING] AMD FW13 fan speed jumps up high, drops quickly back to low / off - #29 by Prise - Linux - Framework Community](https://community.frame.work/t/tracking-amd-fw13-fan-speed-jumps-up-high-drops-quickly-back-to-low-off/39875/29)
													- *Temperature monitoring software*
														- [s-tui](https://github.com/amanusk/s-tui/)
														  collapsed:: true
															- Installation `sudo apt install s-tui`
															- Running `s-tui`
															- Results
															  collapsed:: true
																- ![image.png](../assets/image_1710445859354_0.png)
														- `sensors`
														  collapsed:: true
															- Installation `sudo apt install lm-sensors`
															- Running `sensors`
															- Results
															  collapsed:: true
																- ![image.png](../assets/image_1710446060727_0.png)
														- System Monitor
														  collapsed:: true
															- ![image.png](../assets/image_1710447054442_0.png)
													- Solutions
														- DONE Laptop stand with more airflow for fans
														  :LOGBOOK:
														  CLOCK: [2024-03-16 Sat 22:08:28]--[2024-03-16 Sat 22:08:29] =>  00:00:01
														  :END:
														- PTM7950 Thermal Pad
														  collapsed:: true
															- [Reddit told me to buy this – PTM7950 Thermal Pad - Linus Tech Tips](https://youtu.be/2BhKx0iQ4K8)
															- Relevant guide
																- [Heatsink and Fan Replacement Guide - Framework Guides](https://guides.frame.work/Guide/Heatsink+and+Fan+Replacement+Guide/84?lang=en)
																-
															- [[Honeywell PTM7950 Phase Change Thermal Pads/Sheets] Application, Tips, and Results - #101 by a4955 - Framework Laptop 13 - Framework Community](https://community.frame.work/t/honeywell-ptm7950-phase-change-thermal-pads-sheets-application-tips-and-results/20245/101)
															  id:: 65f5b987-b9ba-474a-937c-f2c26770de85
															- Ordered [Game notebook - Ptm3180 limited package (send cleaning wipes) | Iarmour](https://www.ebuy7.com/honeywell-ptm7950-phase-change-paste-thermal-silicone-grease-cpu-graphics-card-notebook-savior-game-this-phase-change-film.html)
															- Alternative purchase locations
																- [PTM7950 40x80x0.2mm Phase Change GPU Thermal Pad, JOYJOM High Conductive Silicone Grease 8.5W/mK CPU Thermal Paste for PS5 Steam Deck CPU GPU SSD M.2 Laptop : Amazon.co.uk: Computers & Accessories](https://www.amazon.co.uk/PTM7950-40x80x0-2mm-JOYJOM-Conductive-Silicone/dp/B0BRJB8JNX)
																- [Honeywell PTM 7950 Thermal Paste Pad Phase Change 8.5W/m.K for Laptop PC CPU GPU  | eBay](https://www.ebay.co.uk/itm/225323255859)
																-
														- Ensure ((63567ca0-a57f-4976-9104-2d8ecd6ca428))
														- Setup TLP or power-profiles-daemon. Check ((65f58ba7-8f56-4aa1-9d1d-cd54cfbccfe1)). KDE has `power-profiles-daemon` integrated via PowerDevil. Can set the mode to Power Saver, Balanced or Performance in the energy settigns
														- auto-cpufreq
														- some people have made scripts that use DHowett’s EC code ( [GitHub - DHowett/FrameworkHacksPkg](https://github.com/DHowett/FrameworkHacksPkg) )to make a fan curve e.g. cap fan speed as long as core temperatures are under certain thresholds
														- [Fan control software](https://github.com/TamtamHero/fw-fanctrl/pull/21)
														- In the BIOS, use the “Load custom defaults” option.
													- Benchmarking
														- [[2024-09-01 Sunday]] Temperature measurements before and after swapping mainboards
														  collapsed:: true
															- # Before swap
																- ## KDE System Monitor
																  47C low, spikes up to 75C
																- # `sensors`
																	- ```
																	  k10temp-pci-00c3
																	  Adapter: PCI adapter
																	  Tctl:         +47.4°C
																	  
																	  nvme-pci-0200
																	  Adapter: PCI adapter
																	  Composite:    +49.9°C  (low  =  -0.1°C, high = +84.8°C)
																	                       (crit = +94.8°C)
																	  Sensor 1:     +49.9°C  (low  = -273.1°C, high = +65261.8°C)
																	  Sensor 2:     +56.9°C  (low  = -273.1°C, high = +65261.8°C)
																	  Sensor 8:     +48.9°C  (low  = -273.1°C, high = +65261.8°C)
																	  ```
																- ## `s-tui`
																  summaries temp (low)
																	- ```
																	  44
																	  47
																	  50
																	  34
																	  44
																	  44
																	  50
																	  44
																	  ```
															- # AFTER
																- ## KDE System Monitor
																- ## sensors
																  collapsed:: true
																	- ```
																	  k10temp-pci-00c3
																	  Adapter: PCI adapter
																	  Tctl:         +49.8°C  
																	  
																	  nvme-pci-0200
																	  Adapter: PCI adapter
																	  Composite:    +43.9°C  (low  =  -0.1°C, high = +84.8°C)
																	                       (crit = +94.8°C)
																	  Sensor 1:     +43.9°C  (low  = -273.1°C, high = +65261.8°C)
																	  Sensor 2:     +49.9°C  (low  = -273.1°C, high = +65261.8°C)
																	  Sensor 8:     +43.9°C  (low  = -273.1°C, high = +65261.8°C)
																	  ```
																- ## s-tui
																  collapsed:: true
																	- ```
																	  47
																	  50
																	  32
																	  45
																	  45
																	  49
																	  45
																	  ```
														- Test 1
														  collapsed:: true
															- Monitor `watch -n 1 sensors`
															- Stress testing `sudo stress-ng --matrix 0 --ignite-cpu --log-brief --metrics-brief --times --tz --verify --timeout 2m`
															- Results
																- Going as high as 96% but mainly hovering around 88%
																- Fan only kicked in full blast after around 10-20 seconds of 100% CPU usage and 90C temperatures
														- Test 2
														  collapsed:: true
															- Monitor `sensors`
															- Stress testing `sudo stress-ng --matrix 0 --ignite-cpu --log-brief --metrics-brief --times --tz --verify --timeout 2m`
															- Results
																- #+BEGIN_WARNING
																  I didn't accurately measure the time, these are just guesstimates
																  #+END_WARNING
																- First 10 seconds
																	- acpitz-acpi-0
																	  Adapter: ACPI interface
																	- temp1: 52 celsius
																	  temp2: 52C
																	  48
																	  90
																- 30 seconds
																	- 54
																	  56
																	  49
																	  90
																- 1 minute
																	- 55
																	  57
																	  49
																	  89
																- 1.5
																	- 55
																	  56
																	  50
																	  93
																- 2
																	- 54
																	  54
																	  50
																	  77
																- 3 (1 min since test over)
																	- Fans slower but audible
																	- 53
																	  52
																	  50
																	  82
																- 3.5
																	- Slower still, still audible
																	- 52
																	- 50
																	- 49
																	- 88
																- 4
																	- Barely audible
																	- 52
																	  49
																	  49
																	  62
														- Test 3 (post-heat pad install)
														  collapsed:: true
															- 0m
																- 49
																  48
																  45
																  53
															- 0.5m
																- 48
																  50
																  45
																  79
															- 1m
																- 52
																  54
																  46
																  75
															- 1.5m
																- 52
																  56
																  47
																  74
															- 2m
																- 53
																  56
																  47
																  64
															- 2.5 (30 seconds post-test) (already barely audible fans)
																- 50
																  50
																  47
																  44
															- 3m (fans barely audible)
																- 48
																  47
																  46
																  49
															- 3.5
																- 0
															- 4m
																- 0
												- White artifacts on display for long-duration after turning on/off external display
												  collapsed:: true
													- Related threads
														- [[RESPONDED] AMD Ryzen 7040 (7840U) - Arch Linux amdgpu errors, blank screen on opening Steam - Linux - Framework Community](https://community.frame.work/t/responded-amd-ryzen-7040-7840u-arch-linux-amdgpu-errors-blank-screen-on-opening-steam/38387)
														- [Framework 13 Ryzen screen partially blanking white after resuming from sleep - Framework Laptop 13 - Framework Community](https://community.frame.work/t/framework-13-ryzen-screen-partially-blanking-white-after-resuming-from-sleep/38038)
														- [[TRACKING] Video hanging on a white screen on Arch Linux - Linux - Framework Community](https://community.frame.work/t/tracking-video-hanging-on-a-white-screen-on-arch-linux/41701)
														- [[TRACKING] Graphical corruption in Fedora 39 (AMD 3.03 BIOS) - Linux - Framework Community](https://community.frame.work/t/tracking-graphical-corruption-in-fedora-39-amd-3-03-bios/39073)
														- [[RESPONDED] Screen flashing partially white on Framework 13 AMD, Ubuntu 22.04 - Linux - Framework Community](https://community.frame.work/t/responded-screen-flashing-partially-white-on-framework-13-amd-ubuntu-22-04/40626)
														- https://gitlab.freedesktop.org/drm/amd/-/issues/2735
														-
													- enable UMA_GAME_OPTIMIZED in the BIOS and to disable scatter/gather as a boot option (amdgpu.sg_display=0) to defend against the white screen corruption.
													- Actions taken
														- Enable `BIOS > Advanced > iGPU Configuration > UMA Mode: UMA_GAME_OPTIMIZED`
															- BIOS > Advanced > iGPU Configuration > UMA Mode: `UMA_GAME_OPTIMIZED`
															- [[2024-03-19 Tuesday]] Enabling this after ((65f81786-d845-4f8d-94f4-d6f5288da289)) seems to have fixed things. Will try remove ((65f81786-d845-4f8d-94f4-d6f5288da289)) and see what happens
														- try the `amdgpu.sg_display=0` grub option
														  id:: 65f81786-d845-4f8d-94f4-d6f5288da289
															- [Fix 1](https://community.frame.work/t/responded-screen-flashing-partially-white-on-framework-13-amd-ubuntu-22-04/40626/14?u=stroman)
																- To address the flashing, first try [this 19](https://knowledgebase.frame.work/en_us/allocate-additional-ram-to-igpu-framework-laptop-13-amd-ryzen-7040-series-BkpPUPQa), then if after rebooting afterward it persists, you would then:
																- `sudo nano /etc/default/grub`
																- add *amdgpu.sg_display=0*
																	- `GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"`
																	- to change it to
																	- `GRUB_CMDLINE_LINUX_DEFAULT="quiet splash amdgpu.sg_display=0"`
																		- `amdgpu.sg_display=0` kernel param
																- then `sudo update-grub && reboot`
											- [Random freezing requiring a hard reboot](https://community.frame.work/t/tracking-freezing-arch-linux-amd/39495)
											  collapsed:: true
												- [Random hard freezes fw13 amd7840u win11 - #387 by crianza - DIY Edition - Framework Community](https://community.frame.work/t/random-hard-freezes-fw13-amd7840u-win11/39677/387)
												-
											- Short battery life
											  collapsed:: true
												- [[2024-03-16 Saturday]] battery: 76% at 10:34. 39% at 11:39
											- [[2024-06-14 Friday]]
												- Sometimes when waking from sleep the ethernet connection isn't present, requires a restart
												- Laptop sometimes turns off, likely connected to ((65f55d09-db7e-4dcd-9e9f-70ab09c2a383))
										- [Known issues](https://community.frame.work/t/announcement-linux-on-your-framework-laptop-13-amd-ryzen-7040-series/37367)
										- [[TRACKING] AMD: small group of kworkers keeping CPU 0 busy after suspend/resume cycle(s) - Linux - Framework Community](https://community.frame.work/t/tracking-amd-small-group-of-kworkers-keeping-cpu-0-busy-after-suspend-resume-cycle-s/45002)
										- ((65a98a51-f005-464b-b741-f1f4ca7eb39e))
								- Related:
									- ((67c095e2-f716-4fe8-b37e-3bfa0bf7f536))
							- Framework Laptop 13 (2021)
							  id:: 67c095e3-1c3d-41bc-bf6c-06a4341033c6
							  collapsed:: true
								- Pros/Cons
									- Pros
										- Thin as an XPS 13, upgradeable as a desktop PC
										- Up to 64GB DDR4 RAM
										- Up to 8TB NVMe storage
										- Hardware killswitches for mic and camera
										- 1080p webcam
										- Galium nitride laptop charger
										- Intel ME might be neutralised in future
										- Battery can be disconnected via BIOS (this can be used to extend battery life)
										  collapsed:: true
											- _What it is_
												- Convenient alternative than physically disconnecting the battery
												- By having the battery unplugged whilst the power cable is in, the laptop won't degrade the battery
											- In BIOS > Advanced > Battery Disconnect
											  [https://community.frame.work/t/bios-guide/4178#heading--advanced](https://community.frame.work/t/bios-guide/4178#heading--advanced)
											- 1 Backlink
												- Does it have this like Framework Laptop - [Battery can be disconnected via BIOS (this can be used to extend battery life)](https://workflowy.com/#/602e31b6d6ea)
										- Thunderbolt 4
										- [eGPU compatibility - has 4 PCIe dedicated to Thunderbolt](https://community.frame.work/t/upgrade-path-egpu/3009/13)
									- Cons
										- Bit expensive - £1533 for best CPU, with no storage or RAM, 6 expansion slots (4 USB-C, 2 USB-A)
										  collapsed:: true
											- Note: storage expansion cards are £70 for 250GB, £150 for 1TB. Consider one for Windows drive?
										- _Screen is average_
										  collapsed:: true
											- Screen ratio is a bit odd 3:2, though the MS Surface has it
											- Screen is 180 degree hinge, could be 360
											- Screen isn't 4K - though this would use up battery life very fast
											- Isn't touchscreen - though KDE isn't touch friendly
											- Display is reflective rather than anti-glare? Though anti-glare limits brightness
										- _CPU is Intel_
										  collapsed:: true
											- See [Framework laptop uses 11th gen Intel CPU, thus doesn't support S3 sleep for power saving](https://workflowy.com/#/c61c1f0e51b1)
											  collapsed:: true
												- Could use Hibernate instead of Sleep? Or sleep then hibernate feature
											- Intel CPU - instead probably want AMD or ARM/M1 next
											  collapsed:: true
												- Pros/Cons
													- Pros
														- Better than current CPU (it uses 11th gen Intel, my XPS uses 8th gen)
													- Cons
														- Doesn't support S3 sleep
														- Intel isn't as performant or battery efficient as AMD
												- AMD
													- Pros/Cons
														- Cons
															- AMD might be deprecating S3 sleep as well
															  [https://github.com/system76/firmware-open/issues/151#issuecomment-774524777](https://github.com/system76/firmware-open/issues/151#issuecomment-774524777)
													- CPUs are better value, slightly more performant and run cooler according to /r/linux_gaming 2021
													- Doesn't support Thunderbolt 3, but will support the superset USB4 in 2022
													- Can also eGPU via a M.2 slot
													  [https://egpu.io/2020-15-dell-g5-se-5055-rx5600m-r4k8ch-rx-5600-xt-32gbps-m2-adt-link-r43sg-win10-first-ryzen-4000-x4-m-2-egpu-build/](https://egpu.io/2020-15-dell-g5-se-5055-rx5600m-r4k8ch-rx-5600-xt-32gbps-m2-adt-link-r43sg-win10-first-ryzen-4000-x4-m-2-egpu-build/)
													- There isn't likely to be an AMD mainboard until 2022 based on USB4 mainboards not even being released yet
												- Replacing the mainboard only is almost the cost of the entire device (~$1400 for the 1st gen mainboard)
											- Coreboot not yet added, but [planned for long term](https://community.frame.work/t/becoming-qubesos-certified/321/2). Needed for <a href="https://workflowy.com/#/e3b3f652ed7d">Qubes OS</a> certification
											  #PC-Linux
										- RAM - two DDR4 DIMM slots (max 32GB per slot) are great for a laptop, but it could be better
										  collapsed:: true
											- DDR5 comes out in 2022 and will support 128GB per slot
											- LPDDR4 is faster and consumes less power, however it has to be soldered in
										- Runs hot?
										  collapsed:: true
											- Under heavy load, both surface and internal temperatures can get uncomfortably hot.
											- So, what’s the explanation for these kinds of temperatures? Well, open and accessible components certainly may be one of the culprits. Multiple fans, more heat pipes, large heatsinks, extra vents in the chassis, and other kinds of heat spreaders are all additional techniques laptops use to cool these components. The Framework Laptop is limited to just a single large fan, a couple of heat pipes, and some small openings along the bottom of the laptop for airflow. It’s certainly the weakest aspect of the Framework Laptop and one that could put some wear and tear on the internal components over time.
										- Keyboard
										  collapsed:: true
											- Split up/down arrow keys
										- [https://news.ycombinator.com/item?id=29806430](https://news.ycombinator.com/item?id=29806430)
										  collapsed:: true
											- Complaints about battery life, poor speakers, worser build quality eg hinge
										- [https://news.ycombinator.com/item?id=30430300](https://news.ycombinator.com/item?id=30430300)
										  collapsed:: true
											- Average touchpad; mediocre speakers;
									- Unclear
										- ((63734d15-b6e6-42b1-9f2d-2f3199d4d222)) -  uses 11th gen Intel CPU, thus doesn't support S3 sleep for power saving
										- Can Intel ME be neutered on it?
										- [55Wh battery](https://frame.work/gb/en/products/battery?v=FRANBBAT01) i.e. 3572mAh
										  id:: 681f102a-6f23-4087-828e-4fa743533440
								- [https://frame.work/blog/introducing-the-framework-laptop](https://frame.work/blog/introducing-the-framework-laptop)
								- [https://frame.work/products/laptop](https://frame.work/products/laptop)
								- [Hands-on video, a video blogger and the CEO](https://yewtu.be/watch?v=XFrJcjCbCA8)
								- Linus tech tips did a really positive video on it
					- # Ecosystem
						- https://github.com/Steve-Tech/YAFI
							- `sudo nano /etc/udev/rules.d/60-cros_ec_python.rules`
								- ```
								  # CrOS_EC_Python udev rules
								  
								  # LPC Access
								  KERNEL=="port", TAG+="uaccess"
								  
								  # /dev/cros_ec Access
								  KERNEL=="cros_ec", TAG+="uaccess"
								  ```
							- `sudo udevadm control --reload-rules && sudo udevadm trigger`
				- See RISC-V
				- EOMA68 Computer Cards
				  collapsed:: true
					- Overview
						- https://www.crowdsupply.com/eoma68/micro-desktop#products-top
					- Pros/Cons
						- Pros
							- Fully libre hardware and firmware
							- Easy to upgrade CPU+RAM
							- Ecologically friendly
								- Reduces waste of throwing away laptops or other hardware
							- Custom designed laptop casing possible
							- Easy repair with 3D printing replacement parts
							- Portable from laptop to desktop configuration
						- Cons
							- 2GB max ram
							- Allwinner A20 is the only libre processor available currently
							  https://www.crowdsupply.com/eoma68/micro-desktop/updates/picking-a-processor
							- An EOMA68-compatible computer card with an Allwinner A20 dual core processor, 2 GB of RAM, and 8 GB of NAND flash pre-installed
				- USB armory
				  collapsed:: true
					- https://www.crowdsupply.com/inverse-path/usb-armory
					- 512mb
					- Something similar to a TPM module
				- Libreboot-converted computers
				  collapsed:: true
					- ThinkPads
						- Libreboot X220 (release: Dec 2017)
						  16GB RAM
							- https://minifree.org/product/libreboot-x220/
						- Libreboot X200
							- Libre laptop based on 2008 ThinkPad
							- http://shop.gluglug.org.uk/product/libreboot-x200/
							- 8GB RAM max, dual hard drives Older core duo CPU Uses libreboot - free BIOS https://libreboot.org/ WiFi hardware kill switch
						- Ubiquity
						- https://libreboot.org/suppliers.html
						- https://shop.libiquity.com/
						- https://minifree.org
			- _Server performance _
			  collapsed:: true
				- £3.7K Libreboot D16
				  collapsed:: true
				  £3.7K for 32GB, 16 core CPU, 2GB GPU. Up to 128GB RAM, 32 core
					- https://minifree.org/product/libreboot-d16/
					- https://store.vikings.net/vikings-d16-workstation
					- It uses an AMD Opteron 6272 16-core 2.1GHz CPU, with the option to add a 2nd CPU, making 32 cores in total, and it supports up to 128GiB of RAM. (You can also purchase Opteron 6204/6238/6262HE for 100 GBP extra per CPU, or 6284SE for an extra 500 GBP per CPU, or Opteron 6278 2.4GHz 16-core for an extra 400 GBP per CPU. Mention in textbox on checkout). It comes with a high-end, libre-compatible NVidia GTX 660Ti or 670 with 2GiB Video RAM (we will ship the fastest one), fully supported by free software in Libreboot and the Linux kernel, using the nouveau driver. The video card will have at least 1 VGA port and at least 1 DVI port. Where possible, we will ship cards that have HDMI ports, though you can purchase an HDMI to DVI adapter inexpensively.
				- See Raptor Computing's OpenPOWER computers e.g. Talos
				  intralink2:: https://workflowy.com/#/d35eba0a138c
			- Firmware
			  collapsed:: true
				- Disabling Intel ME
				  id:: 65a98a50-4556-4efc-ada0-d13c31ea6de4
				  collapsed:: true
					- [https://www.reddit.com/r/privacy/comments/77ut68/disabling_](https://www.reddit.com/r/privacy/comments/77ut68/disabling_intel_me)<a href="https://www.reddit.com/r/privacy/comments/77ut68/disabling_intel_me">intel</a><a href="https://www.reddit.com/r/privacy/comments/77ut68/disabling_intel_me">_</a><a href="https://www.reddit.com/r/privacy/comments/77ut68/disabling_intel_me">m</a><a href="https://www.reddit.com/r/privacy/comments/77ut68/disabling_intel_me">e</a>
					- [https://github.com/ptresearch/unME11](https://github.com/ptresearch/unME11)
					- [User:Sakaki/Sakaki's EFI Install Guide/Disabling the Intel Management Engine - Gentoo Wiki](https://wiki.gentoo.org/wiki/User:Sakaki/Sakaki%27s_EFI_Install_Guide/Disabling_the_Intel_Management_Engine)
					-
				- On open-source CPUs
				  collapsed:: true
					- On open-source CPUs - A Word on Lockdown
						- Over the life of the Talos™ project, we’ve received a number of requests for a cheap, blob-free, mass-market board based on consumer devices, including calls to use Intel®, AMD Zen™, or even ARM® CPUs as the core of this new product. Unfortunately, no CPUs on the market today meet, or can ever be modified to meet, these strict criteria. In this article we attempt to explain in detail the current state of the market and why blob-free hardware is no longer available, and may never be available again, at both midrange performance and consumer pricing levels.
						- Definitions
						  collapsed:: true
							- Blob-free: Hardware that has source code available for every compiled firmware, system, or other binary required to make the system functional, from initial power application to a full operating environment. Furthermore, to qualify, the end user must be able to modify said source code, recompile it, and use it on the hardware in question. Hardware with source code available, but that requires a vendor-controlled cryptographic signature to be present, does not qualify as blob-free because the vendor has become the sole source of the compiled and signed blob(s) needed to make the hardware function.
						- Overview
						  collapsed:: true
							- A modern computer is a very complex device, requiring a great deal of initialization and setup before control can even be handed to an operating system kernel. Traditionally, this initialization was handled on x86 machines by the BIOS (essentially, standardized boot firmware for the PC architecture), which was an unsigned, closed source application located in ROM or, later, Flash memory. Most hardware at the time (x86, ARM, POWER, etc.) started execution from the processor’s reset vector immediately after power on and reset release; as such, there was nothing stopping a project such as coreboot from creating and compiling its own libre initialization code, then writing the resultant firmware binary over the prorietary BIOS stored within the mainboard’s Flash memory – the hardware would simply execute whatever machine code was present at the reset vector, regardless of origin.
							- Over time, the amount of hardware the platform firmware needed to set up grew almost exponentially, eventually including cache setup, SMP initialization, DDR DRAM training, bus configuration, and many other highly complex functions. Coreboot was eventually unable to keep up with these ever-increasing requirements due to a lack of documentation from the silicon vendors, with AMD being a notable exception due to release of the associated BKDG documentation containing the information needed to properly initialize AMD platforms. As a result of this and several other factors, AMD hardware has been relatively well supported under coreboot for much of the project’s life. On the other hand, coreboot on Intel hardware has lagged or relied heavily on vendor blobs due to the reverse engineering required to natively set up Intel platforms with libre software. Unfortunately, both AMD and Intel now provide large, precompiled binary blobs for CPU and platform setup, and no longer provide any source code or reference materials needed to implement these setup stages. Due to the complexity of modern CPU and platform setup, this lack of documentation or functional source code has created a sort of “soft lockdown”, one that, given enough time and developer effort, can still be worked around. Much of the libre software community has grown accustomed to this “soft lockdown”, and is now used to developers routinely “freeing” hardware locked to proprietary software via these methods. (This should not be conflated with the far more serious hard lockdown discussed below.)
							- In addition to the platform firmware discussed, most CPUs contain microcode, which is a small chunk of gate-level hardware configuration data (horizontal microcode) or a small program running inside the CPU (vertical microcode) that controls how the CPU responds to complex instructions. All x86 CPUs contain a copy of the microcode burned into an on-die storage device, and furthermore can accept microcode updates on the fly via special instructions. Microcode may or may not pose a lockdown and/or security risk depending on the microcode type and CPU age. In general, the fact that microcode is a blob is largely ignored by the libre software community. Some architectures, such as POWER, have unsigned and relatively open microcode, while ARM is unique in that most implementations have no microcode at all.
						- TPMs and Trusted Boot
						  collapsed:: true
							- While the hardware designs discussed above are relatively simple in relation to firmware loading, basically executing from the reset vector on power application, and while they do allow for platform firmware modification, these characteristics are highly undesireable in the context of trusted computing. Essentially, if the platform firmware and, more importantly, the Core Root of Trust and Measurement (CRTM), can be modified at will, there is no way for software further along in the secure boot chain, including sensitive applications, to determine if a particular system has been tampered with by an unauthorized party. Tamper detection and subsequent application rejection is especially important in consumer level devices to enforce unbreakable Digital Rights Management (DRM) anti-features (https://www.fsf.org/blogs/community/antifeatures).
							- For instance, the Palladium project started by Microsoft in April 2002, then renamed “Next-Generation Secure Computing Base” (NGSCB), relied on a known, trustworthy CRTM for its operation. In a nutshell, Palladium relied on hardware-enforced, application-specific (“curtained”) memory along with a Trusted Platform Module (TPM) containing the decryption key for protected content. TPMs only unseal their key if certain measurements, taken during the boot process and stored in PCRs, match the preconfigured values. Base measurements are normally taken before control is passed to the operating system by the bootblock or other suitably low-level portion of the firmware, which contains the CRTM. Tampering with the CRTM could allow the TPM to “validate” tampered firmware or operating system components, rendering the entire TPM-based security model useless. The secure boot chain currently used in most computing products also relies on the CRTM being secure and unable to be modified, as modifications could allow booting of unverified or unauthorized firmware or operating system components.
						- Lockdown!
						  collapsed:: true
							- The simplest “sledgehammer” approach to securing the CRTM is to have the vendor cryptographically sign it, then add checks in the hardware to prevent anything other than the vendor-signed CRTM from executing. Given the CRTM location in the lowest levels of the platform firmware (often, in the bootblock or even the firmware for a dedicated coprocessor), this means that any hardware with a vendor-secured CRTM can never have libre replacement firmware written for it. Ever. The hardware won’t even start executing firmware that doesn’t pass the vendor cryptographic checks, full stop. Effectively, cryptography has become a double-edged sword; it is now being used to lock physical machine owners out of the hardware they ostensibly own, forcing them to either use firmware that often comes with a license agreement or return/discard the hardware entirely.
							- We have already seen numerous instances of this lockdown being used to prevent modification of platform firmware and operating system/user space software. Some of the most famous examples are the TiVo boxes from the late 1990s, most iPhone and iPod products, and a growing number of Android devices from cell phones to tablets. If a device manufacturer enables signature checks, in most cases the only recourse is to either accept the proprietary firmware and software stack as-is, thus completely ignoring the privacy, freedom, and ethical concerns associated with that stack, or to stop using the device as anything but a source of spare parts or a doorstop!
						- Consumer Device Status
						  collapsed:: true
							- As of this writing, all currently manufactured, low- to mid-range and higher x86 devices, with the exception of two obsolete AMD CPUs, incorporate a security processor that is cryptographically signed, updateable, unauditable, and for which no source code or documentation has been made public. Worse, these security processors must load and continually execute this signed firmware for the system to either be brought online (AMD) or for it to remain operational (Intel). Intel calls this technology the “Management Engine” (ME), and ships a network-enabled firmware stack for the custom OS running on the dedicated ME CPU, while AMD calls it the “Platform Security Processor” (PSP), and won’t even release the x86 cores from reset until the PSP has been started from its signed firmware blob. AMD has also incorporated the PSP into its ARM CPUs, rendering them useless for libre hardware. On the low end, some unlocked ARM devices are available, but either their I/O options are severely lacking or they are not designed for general purpose computing in the first place, rendering performance even worse than expected when used in this role. RISC-V is behind even ARM in terms of maturity with no shipping general-purpose silicon or public, reproducible benchmark data at this time. ARM-based libre systems may allow libre computing to survive in some form as a retrocomputing hobby, but they will not allow libre computing to retain its dominant role in shaping the modern software world that we have all not only grown so accustomed to, but have benefited greatly from.
							- As we mentioned in our presentation “The World Beyond x86”, x86 is the only option available in the low to mid-range market segment. It is the only processor architecture used to manufacture CPUs that are both powerful enough to develop modern software and able to be used in systems retailing for below $1,000 USD. This is the fundamental reason that we, or anyone else, cannot offer libre systems in the price and performance class requested. Anyone claiming to be able to do so are either running a scam or severely distorting facts, and there have unfortunately been multiple public instances of this already, a result of feeding off people’s strong desire for said machines.
						- Why OpenPOWER?
						  collapsed:: true
							- POWER8, via the OpenPOWER initiative, is the only architecture currently being used to manufacture powerful CPUs that are not locked down with cryptographic signing keys or other restrictions. Furthermore, all firmware source code for OpenPOWER machines has been released, meaning that unlike x86 you don’t have to pay a third party to create libre firmware for POWER machines! POWER9, when released late next year, will continue this unprecedented level of open access to OpenPOWER systems, however without POWER8 based systems such as our Talos™ first, the only truly open production POWER9 systems may very well be high-end server machines with a $15,000 USD or higher retail price, as was the case for POWER8. Furthermore, as will be detailed in a future update, only Talos™ contains the novel security hardware required to not only enable fully owner-controlled secure boot, but mitigate hardware attacks and restore the TPM as a useful, owner-controlled platform integrity verification tool. As such, it is vital that the libre software community, and specifically those working on large projects like Chromium, the Linux kernel, Firefox, LibreOffice, gcc, clang, GIMP, MySQL, and Xorg, rallies behind the only libre hardware powerful enough to enable development of those projects. Unless this is done, and soon, libre software will slowly fade as we slowly accept a greater level of proprietary software just to retain access to machines capable of compiling these projects, and as more and more of libre software’s core functionality is taken over by the ever-expanding, proprietary platform firmware (which is currently an operating system or at least a hypervisor in is own right!).
						- Conclusion
						  collapsed:: true
							- As can be seen from the discussion above, the libre hardware situation is far more dire than commonly known. We are very much in danger of relegating libre software to execution within a sandboxed hypervisor environment or even as a set of licensed userspace tools only. Please help us avoid this future and bring Talos™ to market; even if you can’t afford a full Talos™ mainboard, please consider purchasing one of the SSH access options and help us make this powerful, truly libre system a reality!
			- _RVF post_
			  collapsed:: true
				- Nearly every computer available runs closed-source firmware (software used to initialise the hardware and you're not able to inspect the code of it). This has been discovered in the past to contain backdoors and hackers/NSA often use firmware 0days to hack your computer.
				- There are however a few completely open-source computers available (no affiliation):
					- 1) There's a few companies which have modified ThinkPads and installed open-source firmware on them
					- 2) There is also an open-source computer which has just been funded via CrowdSupply: EOMA68
						- Basically a credit-card sized computer card which you can slide into a laptop, micro desktop and soon to be tablet and phone housing.
				- The downside with all of these products is that they haven't got the latest specs. But they can go up to 8GB RAM, dual core and have dual SSD drives if desired.
				- Fortunately the more people start demanding completely open-source computers without any potential backdoors, the sooner we'll get them with better specs.
		- Non-libre hardware (closed source BIOS/firmware i.e. coreboot MAX)
		  id:: 65a98a50-076d-4e4a-8778-be27e0acdc17
		  collapsed:: true
			- _Comparisons_
			  collapsed:: true
				- X1 Carbon vs X1 Yoga
				  collapsed:: true
					- Carbon is lighter
						- The X1 Carbon is quite a bit lighter than its sibling, weighing just 2.5 pounds to the Yoga's 3.2 pounds. However, both laptops are the same 0.7 inches thick.
					- ThinkPad X1 Yoga has better screen options, but only if you're willing to pay extra.
					- X1 Yoga has one more USB port.
					- It almost goes without saying that the X1 Carbon, which is not a 2-in-1, costs several hundred dollars less.
				- X1 Carbon vs Razer Blade Stealth
				  collapsed:: true
					- The X1 Carbon easily wins. MUCH better QC/QA, vastly superior customer support, much better build quality, better and quieter cooling. Better performance due to TDP being 25W vs 15W on the Razer BS. Better battery life. Really ,the Razer BS is just not good compared to the competition. Not to mention that the i5 7200U is a massive bottleneck for anything above a 1050 so using the core is like giving 1000$ for a 1050....
						- In short - X1 is a high end business laptop whereas the Blade Stealth is a low-end ultrabook. Really, there is no place for comparison. It's just a landslide.
			- _Laptop Models_
			  collapsed:: true
				- Gaming laptops e.g. AORUS, Asus ROG
				- _Best TB3 support_
					- Dell XPS 13 9380 (2019 model)
					  id:: 65a98a50-4b57-4816-931f-24253c6bc8b7
					  collapsed:: true
						- £1850 Purchase from [Dell.co.uk](http://Dell.co.uk)
						  collapsed:: true
							- Pros/Cons
							  collapsed:: true
								- Pros
									- Best performance CPU in an ultrabook (light, thin 13" portable) form factor
									- [2 Thunderbolt 3 ports](https://www.dell.com/en-uk/shop/laptops-notebooks-and-2-in-1-laptops/new-xps-13/spd/xps-13-9380-laptop/CNX38006?view=configurations) (two 4 lane Thunderbolt 3 with Power Delivery and one USB 3.1 Gen 2 with Power Delivery/DisplayPort)
									  collapsed:: true
										- _Potential usage_
											- Use with eGPU for gaming
											  #PC https://workflowy.com/#/8aaca2a8d588
											- Use with eGPU to power a Windows VM via VFIO/[LookingGlass](https://workflowy.com/#/36fca9d8ef61) (native speeds)
											- Use with up to 4K external monitors and use grid tiling
											  #Productivity https://workflowy.com/#/51c2e91d0b80
											- USB-C Power Delivery means it would be compatible with many cables provided in airports, cafes etc if I ever don't bring a laptop charging cable with me
										- _Initial setup_
											- 1 TB3 port for eGPU/power
											- 1 TB3 port for external monitor(s)
											- 1 USB 3.1 port for USB-C hub (ethernet, mouse, keyboard, HDMI monitor)
											- Port for external SSD?
									- Full Qubes hardware compatibility
									- New 2019 models have  better webcam positioning; NVMe SSDs up to 500GB (faster than SATA 3)
									- [Supports Vulkan 1.2](https://vulkan.gpuinfo.org/listreports.php?devicename=Intel%28R%29+UHD+Graphics+620](https://vulkan.gpuinfo.org/listreports.php?devicename=Intel%28R%29+UHD+Graphics+620)
									  collapsed:: true
										- 1 Backlink
											- Note: current laptop supports Vulkan / DXVK (see [Supports Vulkan 1.2](https://workflowy.com/#/2872ed946fe9)) so that shouldn't be a blocker
											  #PC
									- [Fairly easy to replace the battery](https://www.ifixit.com/Guide/Replacement+of+the+battery+on+Dell+XPS+13+9380/125627)
									  id:: 65a98a50-b4bc-40bf-92f7-f2cf82d820c0
								- Cons
									- S3 sleep/standby no longer in BIOS. Not sure yet if GRUB option to enable [deep] s3 works
									  id:: 6306a76d-4ea8-470c-a1d7-c0500025b016
									  collapsed:: true
										- BIOS > Settings > Power Management > Sleep Mode > Force S3
										- S3 sleep mode was removed from BIOS
											- [Dell admits they removed it](https://www.dell.com/community/XPS/XPS-15-9570-BIOS-1-3-0-sleep-mode-gone/m-p/6232501/highlight/true#M21988)
											- [Since the BIOS update to 1.3.0, Dell has removed the s3 sleep option on XPS laptops.](https://www.change.org/p/craig-epstein-make-dell-bring-back-the-force-s3-sleep-option-on-xps-laptops](https://www.change.org/p/craig-epstein-make-dell-bring-back-the-force-s3-sleep-option-on-xps-laptops)
											- [Complaint here about 9370 (2018 model) having S3 sleep removed](https://www.dell.com/community/XPS/Dell-S3-sleep-mode-again/td-p/7495580)
										- ((65a98a51-73de-4150-be84-186c2c2b6a83))
										- Tests
											- `cat /sys/power/mem_sleep`
												- shows only s2idle and deep available. deep is selected `[deep]`
											- Sat, Oct 16, 2021 - deep sleep is consuming 11% of battery per hour (22% in 2 hours)
											- Mon, Dec 20, 2021 - 30% of battery used over 12 hours whilst laptop was in Sleep mode (s2idle)
										- Related: ((659d093f-bf67-444a-b2a1-ec0a28907583)) : ((66d9a1dc-5ea7-4ea0-99cc-f0f61e208002))
									- Expensive, though mitigated partly by PayPal Credit
									- Eventually I may want a 2-in-1 laptop so it's easiest to use whilst holding in my hand and with a convergent OS
									- Ultrabook-class CPU and soldered RAM means this will eventually be obselete as a workstation - may need to remote into a home workstation for heavier tasks requiring GPU/RAM/CPU
										- [[2024-03-14 Thursday]] Indeed for maybe 2 years now I've been using ((649b1463-b077-434e-a501-df6e30d6c4fb)) for even low-spec gaming like ((6306a6fd-5caa-4b20-97a2-99c8fc74fc2a)), and for several months now have been using ((649b1463-90cf-40ee-b80f-cb955fc2264c)) for even more gaming. I don't run multiple browsers open simultaneously like I'd like to, and I've found various other limitations and slowness due to the hardware limitations
									- _No advanced privacy features_
									  collapsed:: true
										- [Doesn't match certification requirements for Qubes 4.x](https://www.qubes-os.org/news/2016/07/21/new-hw-certification-for-q4/) (mainly Coreboot requirement)
										- No Heads/Librem Key compatibility for tamper-evident boot protection
										- It isn't libreboot or disabled IME
										- It isn't a ((65a98a50-7f84-47be-bc67-1ef4c2f5dcef))
										- 16GB RAM is a bit limited for Qubes
								- Unclear
									- 4K resolution display with touchscreen
									  collapsed:: true
										- Pros
											- Potentially higher productivity by having multiple windows open on small screen
											- can use with a convergent OS
										- Cons
											- Drains battery much faster
											- Gaming is at 1080p usually which can cause blurriness from the upscaling
											- Convergent OS wouldn't work well with this because
												- They're not that great yet
												- This isn't a convertible 2-in-1 - the hinge doesn't bend all the way backwards
									- NVMe SSDs only available up to 512GB, 1TB uses PCI-E
									- Does it have this like Framework Laptop - [Battery can be disconnected via BIOS (this can be used to extend battery life)](https://workflowy.com/#/602e31b6d6ea)
							- Extras - 3 year support
							  collapsed:: true
								- 3 years Accidental Damage Protection
								- 3Y Premium Support and Onsite Service
								- Dell service tag for premium support: 83P9VT2
								- Expires 13/2/22.
								- Express service code: 176-381-087-42
							- Specs
							  id:: 65a98a50-1909-412b-80ef-5acf9606884d
							  collapsed:: true
								- 8th Generation Intel® Core™ i7-8565U Processor
								  [Intel® Core™ i7-8565U Processor](https://www.intel.co.uk/content/www/uk/en/products/processors/core/i7-processors/i7-8565u.html)
									- Whiskey Lake microarchitecture
								- Intel® UHD Graphics 620 with shared graphics memory
								- 16GB LPDDR3 2133MHz
								- Intel® UHD Graphics 620 with shared graphics memory
								- 512GB M.2 PCIe NVMe Solid State Drive
								- 13.3" FHD 1920x1080 screen
								- Windows 10 Home 64-bit
								- _Specs_
									- _Hardware_
										- Model: Dell XPS 13 9380 (2019 model)
										- CPU: i7-8565U (8th gen)
											- [6135](https://www.cpubenchmark.net/cpu_lookup.php?cpu=Intel+Core+i7-8565U+%40+1.80GHz&id=3308)
											- [54.7%](https://cpu.userbenchmark.com/SpeedTest/591977/IntelR-CoreTM-i7-8565U-CPU---180GHz)
										- SSD: 512GB M.2 PCIe NVMe
										- RAM: 16GB LPDDR3 2133MHz
										- GPU: eGPU AMD Radeon 580
									- _Software_
										- Distro: Kubuntu 18.04 LTS
										- Kernel: 5.4
										- Runner: Lutris 4.20
										- DXVK version: DXVK 1.4.5
										- GPU Driver: 3.0 Mesa 19.1.2
										  `glxinfo | grep "OpenGL version"`
						- [[2025-10-11 Saturday]] Now using it by bringing it to friend's houses and playing ((64e9e731-f5b0-4864-bcb9-dfb8dbd5be7b)) on it
							- Data
								- Steam
								- Discord
								- BYOND
								- Stremio
								- ((649b1407-36a5-447b-ba05-aa7a96f80a1b))
						- ## Documentation_
							- [Service manual](https://www.dell.com/support/manuals/uk/en/ukdhs1/xps-13-9380-laptop/xps-13-9380-service-manual/procedure?guid=guid-7e6fb367-26e8-4018-b67c-0127b26a87ec&lang=en-us)
								- [Diagnostic lights](https://www.dell.com/support/manuals/en-uk/xps-13-9380-laptop/xps-13-9380-service-manual/system-diagnostic-lights?guid=guid-f7e24b39-9988-47a8-8c7b-4f85ba0cf5dd)
							- Support service webpage for my service tag
							  [https://www.dell.com/support/home/en-us/product-support/servicetag/0-SDN0eFBEcDk5ajJtdGI3ZEFBaGdCdz090/overview](https://www.dell.com/support/home/en-us/product-support/servicetag/0-SDN0eFBEcDk5ajJtdGI3ZEFBaGdCdz090/overview)
							- iFixIt
								- ((65a98a50-b4bc-40bf-92f7-f2cf82d820c0))
								- [SSD replacement](https://www.ifixit.com/Guide/SSD+replacement+on+a+Dell+XPS+13+9380/125645)
							- Ports
							  collapsed:: true
								- [Left](https://www.dell.com/support/manuals/en-uk/xps-13-9380-laptop/xps-13-9380-setupandspecs/left?guid=guid-12cd14bb-8db3-47d7-a090-15d75787517a&lang=en-us)
									- ![image.png](../assets/image_1725643187976_0.png)
										- 1) **Security-cable slot (wedge-shaped)**
										    
										    Connect a security cable to prevent unauthorized movement of your computer.
										- 2) **Thunderbolt 3 (USB Type-C) port with Power Delivery (Primary)**
										    
										    Supports USB 3.1 Gen 2 Type-C, DisplayPort 1.2, Thunderbolt 3 and also enables you to connect to an external display using a display adapter. Provides data transfer rates up to 10 Gbps for USB 3.1 Gen 2 and up to 40 Gbps for Thunderbolt 3. Supports Power Delivery that enables two-way power supply between devices. Provides up to 5 V/3 A power output that enables faster charging.
										- 3) **Thunderbolt 3 (USB Type-C) port with Power Delivery**
										- Supports USB 3.1 Gen 2 Type-C, DisplayPort 1.2, Thunderbolt 3 and also enables you to connect to an external display using a display adapter. Provides data transfer rates up to 10 Gbps for USB 3.1 Gen 2 and up to 40 Gbps for Thunderbolt 3. Supports Power Delivery that enables two-way power supply between devices. Provides up to 5 V/3 A power output that enables faster charging.
										- 4) Battery-charge status button
										  Press to check the charge remaining in the battery.
										- 5)  Battery-charge status lights (5)
										  Turns on when the battery-charge status button is pressed. Each light indicates approximately 20% charge.
										- 6) Left speaker
										  Provides audio output.
								- [Right](https://www.dell.com/support/manuals/en-uk/xps-13-9380-laptop/xps-13-9380-setupandspecs/right?guid=guid-f0efa586-1b43-447c-a299-f188f5e5c5a5&lang=en-us)
									- ![image.png](../assets/image_1725643226427_0.png)
									- 1) **Right speaker**  
									    Provides audio output.
									- 2) **microSD-card slot**
									    Reads from and writes to the microSD-card.
									- 3) **USB 3.1 Gen 2 (Type-C) port with Power Delivery/DisplayPort**
									    
									    Connect peripherals such as external storage devices, printers, and external displays.
									    
									    Supports Power Delivery that enables two-way power supply between devices. Provides up to 7.5 W power output that enables faster charging.
									- 4) **Headset port**
									- Connect headphones or a headset (headphone and microphone combo).
						- _Troubleshooting_
							- Diagnostic light flashing for power rail failure Tue, Sep 21, 2021
								- What is a power rail
								  [https://youtu.be/l0EzLnoCGmk](https://youtu.be/l0EzLnoCGmk)
						- £1850 1TB SSD
						  https://www.dell.com/en-uk/shop/laptops/new-13/spd/xps-13-9380-laptop?appliedRefinements=104
					- £1.8k Lenovo X1 Carbon 6th gen
					  collapsed:: true
						- £1.8k Lenovo X1 Carbon 6th gen - but 256GB SSD
						  https://www.lenovo.com/gb/en/laptops/thinkpad/x-series/ThinkPad-X1-Carbon-6th-Gen/p/22TP2TXX16G
						- Linus review
						  https://www.youtube.com/watch?v=yQt6Eqk5boE
						- Features
							- 2 Intel® Thunderbolt™ 3
							- 2 USB 3.0
							- MicroSD
							- MicroSIM
						- Plus, you can even output to two 4K displays with the Thunderbolt Dock.
						- Imagine walking up to your desk with your X1 Carbon and automatically connecting to your monitor and external keyboard and mouse. Or walking into a conference room and, almost instantly, your presentation is up on the display, with the speakers fully connected. With the ThinkPad WiGig Dock for WiGig-enabled laptops, there's no fumbling for cables or wired connectivity.
						  https://i.imgur.com/1ECiibs.png
						- See comparisons
						- 3M 14.0W Privacy Filter from Lenovo
					- £1k-£1,550 new - Razer Blade Stealth
					  collapsed:: true
						- Stealth is 12.5" version, Pro is 17", no modifier is 14"
						- £1550
						  https://www.amazon.co.uk/Razer-13-3-inch-Ultrabook-Touchscreen-UK-Layout/dp/B06XHFYZ75/ref=pd_sbs_147_1?_encoding=UTF8&refRID=6EN85QM7CEA0D6NCNNMH&th=1
						- Features
							- Power on USB-C
							- Screen
								- There are a couple of screen options for the Stealth, including a 12.5in 4K version and a new 13.3in QHD screen that fits in the same sized body just with smaller bezels, which is a good thing as the 12.5in versions are a bit on the small side and have very large surrounds. The 4K version is crisp, as you might expect, bright, but the new 13.3in QHD version is likely to be the one to plump for.
								- 12.5’’ or 13.3" models
								- 4K (3840 x 2160)
								- QHD (2560 x 1440)
						- https://www.razerzone.com/gb-en/c/Razer-Blade-Stealth-H2-H3/p/RZ09-01962W52-R3W1
						- At E3 2017 they've updated the line
							- Gunmetal grey or black
							- Subtle logo instead of green logo
							- The model we checked out had Chroma lighting, but Razer says the gunmetal rendition will just have white backlights — another testament to its commitment to taking Razer’s brand into the boardroom by cutting back on flashy elements.
							- The 13.3-inch model starts at $1,399 for a 256GB model and tops out at $1,999 for a 1TB version, while the 12-inch, 4K version offers a choice between a $1,599 computer with 512GB of storage and a 1TB version at $1,999.
						- 2016 version Specs
						  £1k used
							- 16GB RAM
							- £1,950 and the specification jumps to a 4K screen, 16GB of RAM and a 1TB SSD. My particular configuration had a 512GB SSD, QHD display and 16GB of memory, which will set you back £1,350.
							- £1.1k new
							  http://www.ebay.co.uk/itm/Razer-Blade-Stealth-2017-Kaby-Lake-i7-7500U-2-7GHz-16Gb-512Gb-4K-3840-x-2160-/222625869299?epid=2065858742&hash=item33d5892df3:g:j1kAAOSwTuVZmItR
						- Cons
							- Thunderbolt ports and firmware have quality control problems and non-existent customer service
							  https://news.ycombinator.com/item?id=13784521
							- Poor Linux support?
							  https://wiki.archlinux.org/index.php/razer#Razer_Blade
								- https://insider.razerzone.com/index.php?threads/razer-blade-stealth-linux.11334/page-5
								- https://www.reddit.com/r/Fedora/comments/46vwid/howto_fedora_23_winderz_10_dual_boot_on_the_razer/
						- _Related:_
							- Razor Core eGPU
							  intralink2:: https://workflowy.com/#/2902afce08a6
					- HP Spectre 13
					- £1.5k Razer Blade (14")
					  collapsed:: true
					  https://www.razerzone.com/gaming-systems/razer-blade
						- has good form factor and features but max 16GB RAM
						- Models
							- Feb 2017 is when it last got upgraded (~£2.3k)
							  https://insider.razerzone.com/index.php?threads/the-new-razer-blade-7th-gen-intel-i7.20313/
							- 4k allows higher desktop resolution
							- Can buy 2016 models on eBay for £1.2k, though may be worth waiting/paying extra for Thunderbolt 3
							  http://m.ebay.co.uk/sch/i.html?_from=R40&_trksid=m4084.l1313&_nkw=razer+blade+14+16gb
								- This model with NVIDIA® GeForce® GTX 1060 and 7th Gen Intel Core i7-7700HQ def has Thunderbolt 3
						- Stealth is 12.5" version, Pro is 17", no modifier is 14"
					- £1.5k Macbook Pro 13"
					  collapsed:: true
					  But has 8GB RAM
						- https://www.apple.com/uk/shop/buy-mac/macbook-pro
				- _Coreboot or partially libreboot_
					- Purism - Librem 13
					  id:: 635037c2-64f1-4e71-8d24-a106302e2036
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Hardware Kill Switches for wireless radio and camera/mic
								- Part of firmware is libre
									- Bootloader
								- Libre kernel and OS
							- Cons
								- Not open hardware (no schematics)
								- Closed-source firmware
								  collapsed:: true
									- Firmware privacy risks
										- software which is needed to run the hardware
										- Binary blobs
										- Major firmware risk areas are:
											- suspend/resume: power management functions tend to be unstable, particularly as we are targeting the latest release candidates of Linux
											- graphics: there are no Free Software drivers for the 3D core. There is an ongoing project to reverse engineer and develop Free Software graphics drivers. Significantly, the 3D graphics standards for Linux are in a state of active evolution, with Wayland, Mir, SurfaceFlinger, Mesa, etc. vying to replace the aging X11 standard.
											- video: there are no Free Software drivers for the hardware video accelerator DSP, but there are gstreamer libraries available.
											- UI integration of system management features: everything can be adjusted using the command-line, but some items lack UI integration.
									- The BIOS which does use free/libre and open source coreboot, does include a binary from Intel, called FSP.
								- Open-source BIOS + modern processors may not be possible
								  collapsed:: true
									- https://libreboot.org/faq/#librem
									- The Purism Librem 15 shipped with a proprietary BIOS
										- In response to all this, a Coreboot developer wrote a post named “ The truth about Purism.”
										- http://blogs.coreboot.org/blog/2015/02/23/the-truth-about-purism-why-librem-is-not-the-same-as-libre/ (+ response
										- https://puri.sm/posts/about-purism-and-librems-and-cake/ and here is an anonymous overview of Purism laptops false promises http://www.phoronix.com/scan.php?page=news_item&px=Purism-Librem-Still-Blobbed
										- “There was no way that the Intel CPU and chipset they wanted could run libre, given Intel’s tight grip on the low level boot process,” he argued.
										- And it's true. The Librem 15 eventually shipped with standard, proprietary AMI UEFI BIOS, although Intel Boot Guard was configured to allow unsigned firmware. But although it could run unsigned firmware, actually creating a free firmware is more difficult. Modern Intel CPUs and chipsets depend on a lot of closed-source code. The Intel Firmware Support Package (FSP), Intel Management Engine, CPU microcode updates, and even the video BIOS for the GPU are all closed-source binary blobs.
										- Purism responded, focusing on the wording “will be free” in its philosophical contract, stressing that it’s not a commitment about the current product but a future goal to work towards. Purism argues that although the BIOS is currently not free according to the FSF standards, it’s working towards that goal.
									- It's a scam because ThinkPenguin and Los Alamos Computers have been installing Trisquel on high-end laptops for years before Purism existed.
									- Google has tried to persuade Intel and reverse engineer it for years and been unable
						- Progress towards FSF certification
							- Progress updates
							- https://puri.sm/learn/freedom-roadmap/
							- Diagram that summarizes which components are free/libre and which aren’t.
								- https://puri.sm/posts/purism-software-freedom-deconstructed/
								- https://puri.sm/wp-content/uploads/2015/07/purism-road-to-fsf-ryf-graphic-20150812-700x745.jpeg
							- BIOS progress
								- Intel Boot Guard was configured to allow unsigned firmware
									- Librem will be the first laptop ever manufactured to ship a modern Intel CPU fused to run unsigned BIOS code, allowing for a future where free software can replace the proprietary, digitally signed BIOS binaries. This marks one of the largest hurdles to a BIOS that runs 100% free software and firmware.
						- https://puri.sm/products/
						- Purism and firmware
							- There are no parts requiring binary blobs from the bootloader, kernel, through the OS, nor any software applications. Which leaves the BIOS, and the Intel binaries. The BIOS will be Coreboot in future, which will then leave the Intel BIOS binaries included in Coreboot.
							- We are inching our way toward solving that, as you can see here:
							- https://puri.sm/road-to-fsf-ryf-endorsement-and-beyond/
							- https://puri.sm/wp-content/uploads/2015/07/purism-road-to-fsf-ryf-graphic-20150812-700x745.jpeg
						- £1.6k Librem 13
							- Pros/Cons of v4
								- Pros
									- Hardware killswitches for WiFi, camera,
									- Can buy Librem Key with it to ensure tampering is evident during delivery (or just install Heads for tamper evident post-delivery)
									  intralink2:: https://workflowy.com/#/894756550476
									- IME disabled
									  https://puri.sm/posts/purism-librem-laptops-completely-disable-intel-management-engine/
									- Coreboot enabled, next pushing towards Libreboot
									  https://puri.sm/learn/freedom-roadmap/
										- Libreboot project says Librem being free is impossible, though they were wrong about IME at least
										  https://libreboot.org/faq.html#fsp
								- Cons
									- USB C port isn't Thunderbolt 3 - ideally 4x PCIe lanes
									- Can't purchase via PayPal Credit
									- 32GB RAM would be ideal for Qubes
									- Not 4K compatible
									- Only dual core
									- No Ethernet Port
							- https://puri.sm/shop/librem-13/
						- 1 Backlink
							- See [Purism - Librem 13](https://workflowy.com/#/140e57d42da3)
					- ThinkPenguin
					  collapsed:: true
						- https://www.thinkpenguin.com/gnu-linux/catalog
					- Los Alamos Computers
					  collapsed:: true
						- http://laclinux.com/gnu/GNU_Linux_Computers
					- System76 Lemur Pro
					  collapsed:: true
						- Review 2021
							- [https://youtu.be/wTA5Vtp5e3I](https://youtu.be/wTA5Vtp5e3I)
						- Pros/Cons
							- Pros
								- Uses Coreboot
								- 180 degree hinge (totally vertical)
				- _32GB RAM_
					- System76 Lemur
					  collapsed:: true
					  32GB RAM. No Thunderbolt
						- https://system76.com/laptops/lemur
					- Alienware 13 has Thunderbolt 3 and 32GB RAM but poor battery and runs hot
				- _Lenovo ThinkPads_
					- Pros
					  collapsed:: true
						- Lightweight, cheap,durable (good as replacements)
						- Thinkpads have trackpoint - useful in whilst travelling eg plane e.g. x31, x61, t400s
						- Many have Qubes most desirable features
						  https://www.qubes-os.org/compatible-hardware/
							- Lenovo Thinkpad T410 (2522AC1) (i5-520M Arrandale HD graphics )
							- Lenovo Thinkpad T420
							- Lenovo Thinkpad T420s
							- Lenovo Thinkpad T430s (2349NL5) (i5-3320M QM77 HD Graphics )
							- Lenovo Thinkpad T440p (20AN00C1MD) (i7-4900MQ QM87 GeForce GT 730M )
							- Lenovo Thinkpad X230 (2306CTO) (i7-3520M Ivy Bridge HD Graphics )
					- Cons
					  collapsed:: true
						- Limited RAM
						  collapsed:: true
							- Max RAM list
							  https://support.lenovo.com/sg/en/documents/pd012623
						- Lenovo are shit nowadays
						  collapsed:: true
							- Undismissable ad notifications and more
							  [https://news.ycombinator.com/item?id=28382081](https://news.ycombinator.com/item?id=28382081)
							- [gentleman11](https://news.ycombinator.com/user?id=gentleman11) <a href="https://news.ycombinator.com/item?id=28186468">7 months ago</a>  | <a href="https://news.ycombinator.com/item?id=28186204">parent</a> | <a href="https://news.ycombinator.com/context?id=28186468">context</a> | <a href="https://news.ycombinator.com/fave?id=28186468&auth=92d900aebb8230df07c7d2824d2e2bafceffd325">favorite</a> |  on: <a href="https://news.ycombinator.com/item?id=28186204">Lenovo Selling Linux Laptops Directly in the US</a>
							- Can’t trust them since the multiple spyware incidents. Fool me four times, shame on meEg,>
								- But it did more than that. It injected a self-signed root HTTPS
								- certificate, which allowed them to hijack any and all encrypted traffic
								- Different incident>
									- This malware was hidden in the laptop's firmware, and abused the
								- anti-theft feature in Windows 8 and 10. Whenever the laptop booted up,
								- the executable would be extracted from the firmware at boot-up and
								- installed[https://www.makeuseof.com/tag/now-three-pre-installed-malwar...](https://www.makeuseof.com/tag/now-three-pre-installed-malwares-lenovo-laptops/)
								- Secondary source that mentions FTC fines>
									- Lenovo cannot install any bloatware on its laptops without customers'
								- express agreement, under the terms of its settlement with the Federal
								- Trade Commission (FTC) over the Superfish scandal.
								- > On top of a
									- $3.5 million fine that the company agreed to pay in September, Lenovo
								- will now be required to obtain express consent from consumers before any
									- preinstalled software is able to run on a laptop, as well as provide an
									- easy means of uninstalling any Lenovo tools.[https://www.itpro.co.uk/desktop-hardware/29396/lenovo-settle...](https://www.itpro.co.uk/desktop-hardware/29396/lenovo-settles-superfish-spyware-lawsuit-for-35m)
					- ThinkPad T430
					  collapsed:: true
					  Up to 16GB RAM, i7
						- Pros/Cons
						  collapsed:: true
							- Pros
								- Cheap to get refurbished ones
							- Cons
								- CPU is crap and it's especially noticeable on Linux Firefox since it doesn't have hardware acceleration (i5-2520 - ~3200 score)
								  https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-2520M+%40+2.50GHz&id=809
								- eGPU limited - ExpressCard 2 slot is limited to 4Gbps whereas Thunderbolt 3 is up to 32Gbps
								  intralink2:: https://workflowy.com/#/8aaca2a8d588
						- http://shop.lenovo.com/us/en/laptops/thinkpad/t-series/t430#tab-tech_specs
						- Upgrading
						  collapsed:: true
							- CPU
								- Current: Intel Core i5 3320M
								  Oct 2018
								- The T430 supports any Socket G2 CPU out of the box
								- Not massively better to upgrade and it's looking like $300 + international shipping
								  http://cpuboss.com/cpus/Intel-Core-i7-3840QM-vs-Intel-Core-i5-3320M
									- Purchase link
									  https://www.amazon.com/Intel-Core-i7-3840QM-2-80-Processor/dp/B00A8ZWH0S
								- https://www.reddit.com/r/thinkpad/comments/6mie50/cpu_upgrade_options_for_t430/
								- Upgrade video
								  https://www.youtube.com/watch?v=h7guYphKlAI
									- Possible others
										- https://www.youtube.com/watch?v=my37M6O-BVg
										- https://www.youtube.com/watch?v=UihM_2Pyme0
							- _[Learning Resources] _
								- https://medium.com/@n4ru/the-definitive-t430-modding-guide-3dff3f6a8e2e
									- https://www.ebay.co.uk/itm/New-Lenovo-IBM-ThinkPad-T430-T430i-CPU-Cooling-Fan-With-Heatsink-04W3269-04X3788-/222135782837 heatsink
									- https://www.ebay.co.uk/itm/Intel-Core-i7-3840QM-8M-Smart-Cache-2-8-3-8-GHz-rPGA-Quad-Core-SR0UT-vPro/143038428272?epid=1608178157&hash=item214dc13470:g:LfoAAOSwq2xb8Ipd:rk:1:pf:0 CPU
										- double performance
										- http://cpuboss.com/cpus/Intel-Core-i7-3840QM-vs-Intel-Core-i5-3320M
									- £160 total
					- Lenovo ThinkPad T460s
					- Libreboot X220 (16GB RAM, i7)
					  collapsed:: true
					  Libreboot | Est: Dec 2017
						- https://minifree.org/product/libreboot-x220/#libreboot_todo
					- Lenovo 500 series
					  collapsed:: true
						- http://www3.lenovo.com/gb/en/laptops/yoga/500-series/Yoga-510-14-inch/p/88YG5000682
				- MacBooks
				  id:: 65a98a50-a639-4780-878b-deb05e9261ac
				  by ((63208fd2-65bc-4405-a355-1239401f84ab))
					- M (ARM) chip-based
					  id:: 67cae86d-70be-4444-9267-e537acdd241e
						- Meta
							- M1-M5 table comparison
								- ![image.png](../assets/image_1760824625136_0.png)
								- Chip | Process | CPU       | GPU  | Neural  | Memory      | Unified | Geekbench6
								         |         | Cores     |      | Engine  | Bandwidth   | Memory  | Single / Multi 
								    -----|---------|-----------|------|---------|-------------|---------|----------------------
								    M1   | 5 nm G1 |  8: 4P+4E | 7–8  | 16-core |  68.25 GB/s |  16 GB  | 2346 / 8346          
								    M2   | 5 nm G2 |  8: 4P+4E | 8–10 | 16-core | 100    GB/s |  24 GB  | 2586 / 9672          
								    M3   | 3 nm G1 |  8: 4P+4E | 8–10 | 16-core | 100    GB/s |  24 GB  | 2965 / 11565         
								    M4   | 3 nm G2 | 10: 4P+6E | 8–10 | 16-core | 120    GB/s |  32 GB  | 3822 / 15031         
								    M5   | 3 nm G3 | 10: 4P+6E | 10   | 16-core | 153    GB/s | ≤32 GB  | 4133 / 15437 (9 core)
						- M4 Mac Mini
						  id:: 67cae961-f308-4987-ae3e-323d6cfd13d6
						- *Apple M1*
							- M1 Ultra Mac Studio
							  id:: 67cae9c0-a0fb-458d-9420-eab50f649127
							- MacBook Pro 14" (2021)
							  collapsed:: true
							  id:: 63734d14-232e-4d9a-8354-0bbc208dd8a1
								- Pros
									- Compared 2021 to 2020 version
									  id:: 63734d14-ff4b-407d-8564-cbaf8a7b5014
										- Physical function keys not a Touch Bar
										- Additional ports - MagSafe, HDMI, SD
										- Up to 64GB RAM
										- 3 Thunderbolt ports instead of just 2
										- Battery is much easier to replace
										  [https://www.ifixit.com/Device/MacBook_Pro_14%22_2021](https://www.ifixit.com/Device/MacBook_Pro_14%22_2021)
									- Compared to Framework
										- Very good battery life
										- Even better CPU
								- Cons
									- Small notch
									- MacOS software doesn't support eGPUs, but Windows does
										- https://egpu.io/forums/builds/2019-macbook-pro-16-9th-8c-h-rx-6900-xt-32gbps-tb3-razer-core-x-macos-13-windows-11-22h2/
									- Windows doesn't support Apple Silicon
							- MacBook Pro 13" (2020)
							  collapsed:: true
							  id:: 635037c2-ed7c-4d0c-9bb5-db371739b338
								- Pros/Cons
									- Pros
										- M1 silicon CPU means much better battery life and CPU performance
										- Very good trackpad
									- Cons
										- ARM-based so most software will need x86 virtualisation
										- 16GB max
										- Expensive - £2300 at least for 2TB SSD
										- Only two USB4 ports
										- 720p FaceTime HD camera
										- Touch Bar rather than hard function keys. Removed in next year's model
										  id:: 6389b86f-6127-4e2c-a9d9-51a67ddb44a4
									- Comparisons
										- ((63734d14-ff4b-407d-8564-cbaf8a7b5014))
											- {{embed ((63734d14-ff4b-407d-8564-cbaf8a7b5014))}}
								- [https://www.apple.com/macbook-pro13/](https://www.apple.com/macbook-pro13/)
						- Related:
							- ((670be101-bc11-4dd5-a571-13eb92d8edf3)) : ((67cae906-3d56-4c08-9cd5-3d28b32f0e43))
							- ((65a98a51-37bd-4253-b4ab-8437dc26f765))
					- MacBook Air 13" (2020)
					  collapsed:: true
						- Pros/Cons
							- Pros
								- M1 silicon CPU means much better battery life and CPU performance
								- Very good trackpad
								- Includes a touch bar
							- Cons
								- Poor Linux support (see Asahi Linux for development progress)
								- ARM-based so most software will need x86 virtualisation
								- 16GB max
								- Expensive - £2050 at least for 2TB SSD
								- Only two USB4 ports
								- 720p FaceTime HD camera
								- No touchscreen
						- [[Page Not Found — Apple (United Kingdom)](https://www.apple.com/uk/shop/buy-mac/macbook-air/space-grey-apple-m1-chip-with-8-core-cpu-and-8-core-gpu-512gb](https://www.apple.com/uk/shop/buy-mac/macbook-air/space-grey-apple-m1-chip-with-8-core-cpu-and-8-core-gpu-512gb))
					- _Unsorted year_
					  collapsed:: true
						- Macbook Pro 13"
							- Cons
								- Keyboard incompatible with Qubes?
							- £1800 refurb as of Dec 2016 - Apple Macbook Pro 13 Retina A1502 i7-3.1GHz,16GB,1TB SSD* 2015 *HIGHEST SPEC*
							  http://www.ebay.co.uk/itm/Apple-Macbook-Pro-13-Retina-A1502-i7-3-1GHz-16GB-1TB-SSD-2015-HIGHEST-SPEC-/142209420892?roken=cUgayN
						- Macbook Air
							- 2016 models
							  https://www.ebay.co.uk/sch/i.html?Release%2520Year=2016&_sop=12&_sacat=111422&_nkw=macbook%20air&_dcat=111422
							- £870 - 2016 model
							  http://www.ebay.co.uk/itm/Apple-MacBook-Air-13-Inch-1-6GHz-Intel-core-i5-8GB-128GB-UK-Sealed-2016-/162607444850?epid=2031220617&hash=item25dc28b372:g:iJgAAOSwFFZZejO-
							- £700 - 2015 model
							  http://www.ebay.co.uk/itm/Apple-Macbook-Air-13-A1466-i5-1-6GHz-8GB-128GB-SSD-MMGF2B-A-2015-1-YEAR-WARRANTY-/122668107591?epid=2031220617&hash=item1c8f96c747:g:87EAAOSwRqBZoKgI
			- _2-in-1 laptops_
			  collapsed:: true
			  Convertible and detachable to tablets
				- Pros/Cons
					- Pros
						- Longer battery life
						- Lighter
						- Thinner
						- Tablet > laptop
						  collapsed:: true
						  [archived] http://cedonulli.com/revelation-time-to-ditch-the-laptop/
							- my laptop is one of the most important pieces of physical stuffs i own.  it connects to my finances, revenue streams, social contacts, movie watching, time passing, researching things.  it’s also the heaviest, bulkiest thing in my bag.  even though i spent an unholy amount of money buying the lightest, slickest, and yet mil-spec-iest thing around a few years back, it’s still … big.
							- so recently i bought a new android tablet thing.  figuring, maybe it could be a compromise, of sorts.
							- 10 hours battery life, vs. 1 hour on the laptop.  600grams, instead of 1.6 kilos (or something like it).  no need for power brick, and tiny footprint.  way better screen.  promising.
							- in ten days of not having the laptop, i managed to move a bunch of sites to different hosts, ftp stuff around, fix some php crap, some database crap, use photoshop touch to work out minor image things.  pretty impressive.
							- but everything relating to input … SUCKS ASS.
							- the fucking zooming that happens every time you select a text box, is infuriating.  typing more than a paragraph on the onscreen keyboard, a nightmare.  no keyboard shortcuts.  no copy/paste.  all the small things, adding up to it just being a minor nightmare.
							- still, it was pretty neat to find replacement apps to deal with server and code things.  cloud storage.  just playing with the promise of something entirely new, in a long time.
							- still.  it looked like there’s no way around the 3.8lb of laptop lugging.
							- then, spur of the moment, i bought a bluetooth keyboard.  apple’s own fanciness.  very nice, their hardware.
							- and all of a sudden. every single one of the niggling problems are gone.  text boxes stay normal size.  THERE ARE KEYBOARD SHORTCUTS!!!  there’s alt-tab, copy/paste, highlight text via shift+arrow keys.  cycling through browser tabs, works.  most shortcuts that work on the regular pc, work on this android thing.  suddenly it is really almost entirely the same experience as the laptop.
							- it’s really a revelation.  suddenly there is 10 hour battery life, a tiny footprint, and it all just works.  the OS becomes invisible, with a little figuring of apps and changed workflows, i can do all the relatively involved and fancy tech bits, along with content creation, no problem at all.
							- and at the end of the day, if i just want to watch a movie or read some ebook, the keyboard just stays home.
							- there’s the minor bit of a 10 inch screen vs. the 14 inch screen, and no side-by-side window option stuffs.  but that’s minor, compared to the huge amount of weight and space saved, and not constantly hunting for power outlets.
							- it’s the first time in probably 10 years, that real computing stuff has significantly shifted.  finally it’s making sense why microsoft is scrambling so hard to get into the whole convertible tablet world.  i don’t even need windows anymore.  android, and probably iOS can entirely replace a pretty complex technical setup.  if more people catch on to this, it could very well fuck up microsoft’s shiz.
							- meanwhile, all my browser tabs are automatically synced between tablet, phone, and laptop.  the mightytext app syncs all my sms to the tablet, no need to even have the phone with me (via google account and internet connection – totally slick).  all e-mails, contacts, files, photos, synced.  utorrent is downloading movies, music is playing in the background, code updates are uploading via ftp, and i’m writing blog posts.  it boggles my tiny little mind that all this is possible, without traditional computer things.
							- it’s also a lot more modern, than a laptop, in many subtle ways.
							- there’s instant on, just push the button.  no lag, no booting.  wifi stays on while it’s asleep, and there is a notification light for new e-mails or messages (configurable, no less).  there’s nfc sensors, gps, barometric pressure sensor, two cameras, accelerometer, compass.  any time i use the laptop now, it just feels … old.
							- now all i have to do is shop for a much smaller backpack.  friggin awesome, these nerdy bits.
					- Cons
						- Expensive for the performance
						- OS options limited
						  collapsed:: true
						  Aug 2017
							- All (almost all?) come with Windows 10
								- Linux on 2-in-1
									- https://www.reddit.com/r/SurfaceLinux
									- https://www.reddit.com/r/linux/comments/5rukmu/whats_the_current_state_of_linux_support_for_2in1/
								- Android x86 and variants
							- Windows 10
							- Linux or Android x86 with some hardware bugs
							- Android x86 commercial forks
						- Not modular
						- Less RAM, CPU, SSD space and number of
					- Uncertain
						- Smaller
						- Mobile or convergent OS only
						- More sensors
					- Convertible-hybrid vs Detachable-hybrid
						- _Convertible_
							- More stable typing, improved battery life
						- _Detachable_
							- Lighter, thinner
				- _Best TB3 suppport_
					- £1.8k? Lenovo X1 Yoga
					  collapsed:: true
						- Touchscreen?
							- If so then all it needs is a convergent OS like Phoenix OS and then it's basically a tablet
						- £1k-2.7k 2017 (2nd gen) 14" ThinkPad X1 Yoga
							- OLED screens available
							- Has a 4G modem
							- £1k on eBay
							  https://m.ebay.co.uk/sch/i.html?_from=R40&_trksid=p2056088.m4084.l1311.R1.TR5.TRC1.A0.H0.XX1+yo.TRS0&_nkw=x1+yoga&_sacat=0
							- £1.6k brand new
							  http://www3.lenovo.com/gb/en/laptops/thinkpad/x-series/Thinkpad-X1-Yoga-2nd-Generation/p/22TP2TXX12Y
							- £2.7k with 16GB RAM
					- £1.7k HP Spectre X360
					  collapsed:: true
						- https://store.hp.com/UKStore/Merch/Offer.aspx?p=c-hp-spectrex360
					- Lenovo Yoga 920
					  collapsed:: true
						- Can't buy from here - older product?
						  https://www.lenovo.com/gb/en/laptops/yoga/900-series/Yoga-920-13/p/88YG9000859
					- £900 Lenovo Yoga 730
					  collapsed:: true
					  But 8GB RAM
						- https://www.lenovo.com/gb/en/laptops/yoga/700-series/Yoga-730-13-/p/88YG7000964
				- _Detachable-hybrid_
				  Touch-**compatible** OS + detachable physical keyboard
					- £700-1k - Microsoft Surface Pro
					  collapsed:: true
						- Hinge isn't strong by itself - needs a backrest to lean up
						- £1k new - 8GB RAM,
						  http://www.ebay.co.uk/itm/MICROSOFT-Surface-Pro-4-12-3-Tablet-256GB-SSD-8GB-RAM-Windows-10-Bluetooth-/112000247462?epid=218199101&hash=item1a13bc26a6:g:jxgAAOSwpRRWn3jC
						- £690 - used, i5, 4GB RAM, not with keyboard
						  https://www.amazon.co.uk/gp/offer-listing/B017UANA5Y/ref=olp_twister_child?ie=UTF8&mv_color_name=0&mv_size_name=1&mv_style_name=0
						- £657 used (B- grade) - i7, 8GB RAM, no keyboard (average used, some scratches)
						  http://www.ebay.co.uk/itm/Microsoft-Surface-Pro-4-M3-i5-i7-4-8-16GB-RAM-128-256-512-1TB-Windows-10/263001604237?_trkparms=aid%3D555017%26algo%3DPL.CASSINI%26ao%3D2%26asc%3D20151005190540%26meid%3Dfccc8356f7c441ad819b5b64d6e4cfe4%26pid%3D100505%26rk%3D1%26rkt%3D1%26&_trksid=p2045573.c100505.m3226#viTabs_0
						- £650 used (A+ grade) - i5, 4GB RAM, no keyboard+pen
						  http://www.ebay.co.uk/itm/MICROSOFT-Surface-Pro-4-i5-128GB-i5-6300U-12-3-Windows-10-/253094203916?epid=218350178&hash=item3aed97120c:g:eBkAAOSwruhZjJYr
						- Pro 4 vs 3
							- Up to 16GB RAM vs 8GB?
							- Up to 1TB storage vs 512
							- Slightly thinner, lighter and bigger screen
							- Better CPU
							- Improved Type Cover (keyboard) which lies flat
							  http://i.imgur.com/R2CqcXo.png
					- £1.2k pre-order Librem 11
					  collapsed:: true
						- https://puri.sm/products/librem-11/
					- $99 PineTab by Pine64
					  collapsed:: true
					  https://i.imgur.com/N30NsEM.jpg
						- Description
							- Linux-only tablet based on the Allwinner A64 SOC. The configuration of the PineTab is akin to that of the 11.6” Pinebook and we expect that most existing Linux and *BSD images for the Pinebook will work on the tablet with little to no code alterations. That said we also hope and encourage developers who are interested in the touch interface to approach us and have a chat about the PineTab.
							- The tablet is is built out of sleek black and grippy plastic and features a 720p 10.1” IPS LCD, panel, a volume rocker and ‘home’ button on one side, and a set of speakers on the back. You will also be able to purchase a magnetically attachable keyboard for the PineTab, which doubles-up as a protective sleeve. Whilst most desktop distros feature an on-screen keyboard, and mouse functionality can be duplicated using a touch-screen, very few have been designed specifically with touch in mind, so an optional keyboard is something we expect many users will appreciate. The keyboard features an inbuilt trackpad and connects to the tablet using pogo pins that use a standard USB 2.0 interface, and folds in a way that also props up the tablet when its sat on a table.
						- Specs
							- BT 4.0
							- WiFi 802.11n
							- 16GB of eMMC
							- Allwinner A64
							- 2GB of LPDDR3 RAM
							- 720p IPS 10” LCD (MiPi)
							- USB 2.0 A host
							- Micro USB 2.0 OTG
							- mSD slot
							- 2mpx front-facing camera
							- 5mpx rear camera
							- Speakers and microphone
							- Volume rocker and ‘home’ button
							- Magnetically attached keyboard + trackpad
							- Target price for PineTab + keyboard: $99 ($79 for standalone PineTab)
					- £850 ThinkPad X1 Tablet
					  collapsed:: true
					  Weak CPU though
						- £850 used - 8GB RAM, m5 CPU
						  http://www.ebay.co.uk/itm/Lenovo-ThinkPad-X1-Tablet-20GG-12-Core-m5-6Y54-8GB-256GB-FHD-Touch-4G-Win-10-/122662600155?hash=item1c8f42bddb:g:hWQAAOSwurZZLqhR
						- Review
							- https://www.gottabemobile.com/lenovo-thinkpad-x1-tablet-review/
				- _Convertible-hybrid_
				  Touch-**optimized** OS (not as touch-oriented as the "Detachable-hybrids" have to be)
					- £950 Lenovo Yoga 720
					  collapsed:: true
					  Similar specs to T420 but thinner - ideal for travel and used for Linux
						- Specs
							- 2 x USB Type-C with Thunderbolt
							- i5 base, i7 available
							- 13.3"
							- 8GB base and max
							- 512GB SSD
						- Cons
							- There's complaints about fan loudness
							- 8GB RAM max
						- £970 new
						  http://www3.lenovo.com/gb/en/laptops/yoga/700-series/Yoga-720-13/p/88YG7000827
						- £900 new
						  http://www.ebay.co.uk/itm/LENOVO-Yoga-720-14IKB-14-2-in-1-Grey-/112525137756?hash=item1a3305575c:g:VrYAAOSwjn9Zkbs~
						- 16GB RAM version available, soldered on
						- Linux
							- https://www.reddit.com/r/Lenovo/comments/6dml6i/ubuntu_1704_on_lenovo_yoga_720_15_inch/
							- Works with Ubuntu 17.04
							  https://forums.lenovo.com/t5/forums/v3_1/forumtopicpage/board-id/Special_Interest_Linux/thread-id/9235/page/3#
								- I got a Yoga 720 13", i5-7200u, 1080p display, 8 GB RAM, 256 GB SSD model from bestbuy. I can run Ubuntu 17.04, Mate desktop out of the box with almost everything working as expected. I first tried it in a LIVE USB session and then installed it to the SSD. I created a Win10/Ubuntu dual boot setup as follows.
								- (1) After booting into Windows for the first time, download and install all updates.. The pre-installed Lenovo service utility prompts to update the firmware.  I went ahead with it.
								- (2) It is necessary to change the storage setting in the BIOS from RAID to AHCI, in order for linux to recognize the internal SSD. As the pre-installed Win10 was installed in the RAID mode, chaning the mode as above will break Win10. In order to prevent this, before changing the mode, follow the steps outlined here to switch Win10 from RAID to AHCI without reinstallation.
									- http://triplescomputers.com/blog/uncategorized/solution-switch-windows-10-from-raidide-to-ahci-operation/
										- there is in fact a way to switch operation from either IDE or RAID to AHCI within Windows 10 without having to reinstall.  Here’s how.
											- Right-click the Windows Start Menu. Choose Command Prompt (Admin).
												- If you don’t see Command Prompt listed, it’s because you have already been updated to a later version of Windows.  If so, use this method instead to get to the Command Prompt:
													- Click the Start Button and type cmd
													- Right-click the result and select Run as administrator
											- Type this command and press ENTER: bcdedit /set {current} safeboot minimal
												- If this command does not work for you, try bcdedit /set safeboot minimal
											- Restart the computer and enter BIOS Setup (the key to press varies between systems).
											- Change the SATA Operation mode to AHCI from either IDE or RAID (again, the language varies).
											- Save changes and exit Setup and Windows will automatically boot to Safe Mode.
											- Right-click the Windows Start Menu once more. Choose Command Prompt (Admin).
											- Type this command and press ENTER: bcdedit /deletevalue {current} safeboot
												- If you had to try the alternate command above, you will likely need to do so here also: bcdedit /deletevalue safeboot
											- Reboot once more and Windows will automatically start with AHCI drivers enabled.
									- Alternatively, you might make a fresh installation of Win10 in the AHCI.
								- (3)  After switching Win10 to AHCI shrink the single windows partition using Disk Management utility to the desired capacity and make space for linux.
									- http://www.everydaylinuxuser.com/2015/11/how-to-shrink-windows-10-to-make-space.html
								- (4) Boot with Ubuntu Live-USB from USB 3.1 port. I installed Ubuntu in the UEFI mode.
								- (5) Using gparted, create desired partitions. I created 3 partitions. (root installation, /home and swap) and perform Ubuntu installation.
								- (6) The dual boot setup is now ready! Upon rebooting,  the UEFI boot menu shows options to boot into linux or windows. With Kernel 4.10 in Ubuntu 17.04, most of the things works out of the box as a laptop. (Wifi, sound, mic, suspend/resume, touch screen) I haven't yet fiddeled around to see if it correctly works in the tablet mode.
								- (7) Update Ubuntu using the standard commands,
									- sudo apt update
									- sudo apt upgrade
									- I am yet to test this setup thoroughly, but the command,
									- acpi -b
									- estimates the battery life  >7 hours, in the idle mode.(medium screen brightness, wifi on, browsing in Google chrome/editing documents,no videos or cpu intensive tasks) Normally I keep the AC supply plugged in while working indoors.
								- (8) It seems that the battery is discharging faster than expected in the suspend mode. 2% discharge after 10 hours of suspend. I am investigating this.
								- I hope these instructions help someone to setup dual boot in this laptop!
					- £700 YOGA 710 11"
					  collapsed:: true
						- 8GB RAM, i5, 256GB SSD
						- https://youtu.be/uDgddx-y2wo
						- Quite thin
					- £650 Lenovo Miix 510 12"
					  collapsed:: true
						- 4GB RAM, i3, 128GB SSD
						- https://www.youtube.com/watch?v=Rz__q-TFYgs
						- Looks decent
						- Type cover, not attached keyboard
					- £470 ThinkPad 13
					  collapsed:: true
						- 4GB RAM, i3, 180GB SSD
						- https://www.youtube.com/watch?v=qFnrrQCmg8k
					- £470 used Lenovo 700
					  collapsed:: true
					  Bit thick
						- Bit thick
						  https://youtu.be/izhvSPw8FcQ?t=2m57s
						- https://www.amazon.co.uk/gp/offer-listing/B017LVZFKU/ref=olp_twister_child?ie=UTF8&mv_color_name=1
					- **Undesired models**
					  collapsed:: true
						- £450 Lenovo YOGA Book (with Android/Linux/Windows)
						  No - Software keyboard
							- http://www3.lenovo.com/gb/en/tablets/android-tablets/yoga-tablet/Lenovo-Yoga-Book/p/ZZITZTOYB1F
							- Software keyboard though - not physical keys. Not good for workstation
						- £370 Lenovo YOGA 300 11-inch
						  No - poor specs and thick
							- http://www3.lenovo.com/gb/en/laptops/yoga/300-series/Yoga-300-11-inch/p/88YG3000595
							- Specs aren't great
							- Quite thick
				- Unsorted models
					- Apple macbooks
						- [https://news.ycombinator.com/item?id=25095438](https://news.ycombinator.com/item?id=25095438)
					- Samsung Notebook 9 Pro
					- HP Spectre x360
					- Microsoft Surface Book i7
					- Samsung Notebook 7 Spin
					- Asus ZenBook Flip UX360
					- HP Spectre x360 15
					- Dell Inspiron 13 7000 2-in-1
					- Lenovo Yoga 910
					- Lenovo Yoga 900S
				- Accessories
					- Laser projection keyboard
					- Projector for multi-screens
			- _Desktops_
			  id:: 65a98a50-744c-4e3c-a475-ac27ff383e10
			  collapsed:: true
				- [Steam Machine](https://store.steampowered.com/sale/steammachine)
				  id:: 6914f704-e2dd-40bf-afbe-a94d10b0108e
				  collapsed:: true
					- Images
						- ![image.png](../assets/image_1762982124989_0.png)
					- Specs
						- ![image.png](../assets/image_1762981640610_0.png)
						- ![image.png](../assets/image_1762981815637_0.png)
					- Related: ((644c0bb5-76e1-4489-9fa4-22a803fa3c9d))
				- £700 Librebox
				  collapsed:: true
					- https://libretrend.com/specs/librebox/
					- Pros
						- IME is neutralised
						- Can handle 32gb of RAM
					- Cons
						- Lacks Thunderbolt 3
						- It is a mobile CPU
				- r-10 All-in-One Qubes PC
				  collapsed:: true
					- Pros/Cons
						- Pros
							- Up to 32GB RAM
							- i7 processor
							- UHD 4k) options available
							- Qubes features
								- TPM module
								- Hardware camera/microphone switch
								- Some Qubes 4.x features
									- Having a CPU with SLAT and IOMMU)
						- Cons
							- Not open hardware
								- Manufacturing
									- Most computers in the world are made by a very small number of factories, whether they come out badged as Dell, Apple, Lenovo, or any other well-known brand. We are very happy to open up the manufacturing and procurement process for you. These machines are made for us by Foxconn in China, imported into the UK where they have the webcam cut-out modification made, which involves the addition of an extra circuit board and the switch and indicator light. Then they are shipped straight to you, the end user, wherever you are in the world.
							- Not full Qubes 3 or 4 requirements
								- For Qubes 4 certification, it would need to use open source firmware as its BIOS.
								- For it to be certified to Qubes 3 it would need to have an extra USB controller that was dedicated, and restricted, to the mouse and keyboard, which would need to be wired and not wireless.
									- We are also considering offering an additional USB controller as a half-size mPCIe card that could use the slot occupied by the wifi/bluetooth module on standard models. We would have to design and build this board specially, as none are available from other manufacturers, but if the crowdsourcing campaign for the r-10 is sufficiently successful we will do this at no extra charge for end-users.
							- Doesn't allow dual SSDs?
							- No USB C?
							- Expensive
							- Similar cost to iMac
								- Everything = $2331 / £1866
									- Base cost $1,412
									- $275 to upgrade 16GB RAM to 32GB
									- $207 to upgrade SSD from 1TB HDD to 1TB SSD
									- $55 height adjustable stand
									- $207 4K monitor
									- $175 touch screen
						- Unclear
							- Desktop, not laptop
					- Conclusion
						- High-end specs similar to Purism Librem at a lower price
						- Not enough security improvements over current ThinkPad T420 to consider spending almost £2k for a new computer
					- https://www.crowdsupply.com/r-machines/r-10-qubes-pc
					- https://r-machines.co.uk/qubesos
				- ORWL
				  collapsed:: true
					- https://www.crowdsupply.com/design-shift/orwl#products-top
					- Planned to be source-available, but not entirely libre
					- The unit’s security processor also monitors movement, and a user can select a setting that will wipe or lock down the PC’s data if it is moved to another location.
					- Qubes lead dev thinks it's not to be trusted because their secure microcontroller is another Intel Management Engine-type of unauditable firmware
					  [archived] http://blog.invisiblethings.org/2016/09/03/thoughts-about-orwl.html
					- Response
					  https://www.crowdsupply.com/design-shift/orwl/updates/invisible-things
				- £1k Intel NUC "Hades Canyon" mini PC (2018) + £300 for 1TB M2 and 16GB RAM
				  collapsed:: true
					- NUC8i7HVK
					- £930 without RAM and SSD?
					  https://amzn.to/2PTihgD
					- Features
						- Tons of slots
						  https://youtu.be/XvTBghEDXHc?t=3m22s
							- Thunderbolt 3 x2
							- USB 3.1 x5
						- Up to 32GB RAM
						- Good iGPU
						-
				- £620 Intel NUC "Skull Cannon" NUC6i7KYK Mini PC (2016)
				  collapsed:: true
					- http://i.imgur.com/kWfbuvY.png
					- Pros
						- 32GB RAM
						- 6th gen i7, Thunderbolt 3
					- Cons
						- Large power brick
					- http://amzn.to/2lUAvjj
				- https://www.qubes-os.org/hcl/#hardware-desktops
				- ((65a98a50-811c-4de7-8127-0919127fe8af))
				  id:: 65a98a50-3dfe-4ded-8716-9fb94206752f
			- Handheld gaming PC
			  id:: 67c9b976-556b-484d-8ad8-4281f5bb3387
			  collapsed:: true
				- [Steam Deck](https://store.steampowered.com/steamdeck)
				  id:: 65a98a50-22c3-4dd5-84f5-5e3cf36a4c27
					- [It's able to run HZD Remastered on Medium at 30 FPS](https://youtu.be/BN7OQUNsrt0)
						- ((675c2b82-ac3c-47c0-9878-08f1c2996360))
					- Related: ((644c0bb5-76e1-4489-9fa4-22a803fa3c9d))
				- ROG Ally
				- Lenovo Legion Go
			- _UMPC/Palmtops_
			  id:: 65a98a50-a2bd-44d0-849a-24c12fce1c0a
			  collapsed:: true
			  Ultra-mobile
				- [MNT Pocket Reform](https://mntre.com/media/reform_md/2022-06-20-introducing-mnt-pocket-reform.html)
				  collapsed:: true
				  Tiny 7" laptop
				- 750 EUR DragonBox Pyra
				  id:: 65a98a50-95e7-49ad-a0c8-56d6db8715ec
				  collapsed:: true
				  Open hardware, mini Linux computers
					- http://i.imgur.com/sh9PaRx.png
					- https://pyra-handheld.com/boards/pages/pyra/
					- Preorder stats (realtime)
					  http://p.rdw.se/pyra-preorder.html
					- https://pyra-handheld.com/wiki/index.php?title=Timeline
					- OpenPandora or soon to be released Pyra (my main device for quite some time, now secondary device):
						- Runs desktop gnu/linux
						- No baseband processor, just wifi
						- Relatively free (gpu needs binary blob)
						- 120€ used
						- Hardware slow as fuck and outdated (Pyra is going to be faster)
						- Can do mobile chat/voice/video - Yes/Yes(with usb or 3,5mm mic)/No
						- USB host for GPS/Modem/? - Yes
						- 10 hour+ battery life under full load, absolutely amazing in that regard
					- Pyra has hardware baseband isolation but Neo900 dev says it lacks sensors for detecting activity in comparison to the Neo900
					  source:: https://pyra-handheld.com/boards/threads/pyra-baseband-modem-sandbox-vs-gta04-and-neo900.75693/
					- Pros/Cons
						- Pros
							- Great specs
								- Huge storage space eg multiple terabytes
								- 4G or wifi models
								- Decent? ARM CPU
								  https://pyra-handheld.com/wiki/index.php?title=OMAP_5
							- Open hardware
							- Runs Debian
							- Would be great for travel
							- Gaming controls
							- Modular internals for upgrading
							- Hardware baseband isolation
							  https://pyra-handheld.com/wiki/index.php?title=Modem
								- Sensor for detecting modem activity
								  https://pyra-handheld.com/boards/threads/poll-vote-now-1-3g-paranoia-discussing-solutions.73805/page-7#post-1396371
								- USB interface, hardware power kill switch, current monitoring
						- Cons
							- Expensive
								- 65E shipping
						- Unclear
							- Uses resistive touch screen. Far more accurate for stylus but not for fingers
				- _GPD devices_
				  collapsed:: true
					- $249 DevTerm (cyberdeck)
					  collapsed:: true
						- [https://www.clockworkpi.com/devterm](https://www.clockworkpi.com/devterm)
						- [https://old.reddit.com/r/cyberDeck/top/?sort=top&t=year](https://old.reddit.com/r/cyberDeck/top/?sort=top&t=year)
						- Pros/Cons
						  collapsed:: true
							- Pros
							  collapsed:: true
								- Great keyboard
								- Retro gamepad and trackpad
								- Open hardware
								- Tested to work with a lot of software
								  collapsed:: true
									- Debian, Ubuntu
								- 5G modem
							- Cons
							  collapsed:: true
								- Screen doesn't tilt, bad ergonomics
								- ARM64 only at the moment
								- USB 2.0 slots only, which are slow af
					- GPD devices
					  collapsed:: true
						- [https://www.gpd.hk/](https://www.gpd.hk/)
						-
					- £300 GPD MicroPC (Q2 2019) (budget and sys-admin oriented)
					  collapsed:: true
						- Specs
						  collapsed:: true
							- 6 inch display
							- Intel Celeron N4100 quad-core “Gemini Lake” processor
							- 4GB RAM
							- 128GB M.2 2242 SSD
							- 3 USB 3.0 Type-A ports
							- 1 USB Type-C port (charging and data)
							- HDMI
							- RJ45/Ethernet
							- Serial Port
							- microSD card reader
							- Backlit keyboard
							- 6,200 mAh battery
					- GPD Pocket 2 (2018) (general use)
					  collapsed:: true
						- Linus review
						  https://www.youtube.com/watch?v=Rug26z-hy-w
					- GPD Win 2 (2019) (gaming oriented)
					  collapsed:: true
						- Differences from Win 2
						  collapsed:: true
							- No Xbox One style gamepad controls vs yes
							- 4GB vs 8GB
							-
					- $600 GPD Pocket (Q3 2017
					  collapsed:: true
					  Ubuntu or Windows 10. 8GB RAM, USB-C
						- https://www.indiegogo.com/projects/gpd-pocket-7-0-umpc-laptop-ubuntu-or-win-10-os-laptop--2#/
						- Requires external 4G network interface card
					- GPD Win (2016?)
					  collapsed:: true
						- Ability to run gnu/linux (not very practical atm), comes with Win10
						- No baseband processor, just wifi
						- Relatively free (gpu (maybe other components?) needs binary blob)
						- around 350€
						- Is pretty fast and modern
						- Can do mobile chat/voice/video - Yes/Yes/No
						- USB host for GPS/Modem/? - Yes
						- around 3 hours of battery life when browsing the web
				- Related: phones with Physical QWERTY keyboard eg Gemini PDA
			- [[Phone]] : ((649b13c9-2c58-49ad-a151-a73c49bdbc1d))
			- _Convergent PCs_
			  collapsed:: true
				- EOMA68 Computer Cards
				- Run a laptop experience powered by mobile
				  collapsed:: true
					- Monitor/keyboard combos
						- Lapdocks
						  id:: 633b7502-b358-45fb-95d2-5fc35ed27d3f
							- Pros/Cons
								- Pros
									- Way cheaper than a laptop
								- Cons
									- It can never receive firmware updates because there is no CPU
								- Unclear
								- Comparisons
									- ((633b7502-b358-45fb-95d2-5fc35ed27d3f)) vs VR glasses)
										- For ((633b7502-b358-45fb-95d2-5fc35ed27d3f))
											-
										- For Subject2blockref
											-
										- Similarities
											-
										- Unclear
									- ((633b7502-b358-45fb-95d2-5fc35ed27d3f)) vs ((65a98a50-f512-4be8-9daa-1527d79584c4)) laptop + ((63a9ade4-0cdf-4680-a839-6b6f92e57f51))
										- For ((633b7502-b358-45fb-95d2-5fc35ed27d3f))
											-
										- For ((65a98a50-f512-4be8-9daa-1527d79584c4)) laptop + ((63a9ade4-0cdf-4680-a839-6b6f92e57f51))
											-
										- Similarities
											-
										- Unclear
											-
							- [NexDock](https://nexdock.com/explore-nexdock/)
							  id:: 67cc4886-eab9-4566-81e1-46f165f08da4
							- [NexPad](https://nexdock.com/meet-nexpad/)
							- UPERFECT X Mini
							  collapsed:: true
								- https://reddit.com/r/SamsungDex/comments/xri7bi/uperfect_x_mini_full_review_dex_and_steam_deck/
							- $300 Mirabook
							  collapsed:: true
								- https://miraxess.com/
							- Openbook
							  collapsed:: true
								- https://www.kickstarter.com/projects/682864025/openbook-a-smartphone-laptop-docking-station
								- The openbook is a new 14 inch laptop shell that’s designed to connect with phones running Android 5.0 or later that have USB OTG support. Your phone plugs into the OpenBook via a USB port that supports DisplayLink technology.
								- It features a 14 inch, 1366 x 768 pixel TN LCD display (with limited viewing angles), a 10,000 mAh battery, stereo speakers, a headphone jack, a microSD card slot, a USB 3.0 port, and a full-sized keyboard and touchpad.
							- $200 11.6" Superbook powered by Sentio
							  collapsed:: true
								- https://www.sentio.com/preorder
								- Most funded hardware on kickstarter
								- https://www.reddit.com/r/Sentio
									- Some complaints about build quality, trackpad sensitivity, inability to change app window size
									- the last two should be in the settings
						- 2-in-1 portable monitors and keyboards
							- _Convertible-hybrid_
							- Detachable-hybrid
								- Samsung DeX for tablet with Galaxy Tab S4
					- Hardware
					- Software
						- Windows Continuum
						  intralink2:: https://workflowy.com/#/77ca9b35e3f3
					- DisplayLink apps
						- https://play.google.com/store/apps/details?id=com.displaylink.presenter
						- https://play.google.com/store/apps/details?id=com.displaylink.desktop.demo
					- DisplayLink-capable "mobile docking station"
					  This trusted device is envisioned to be of a small USB stick or
					  SD card form factor.
						- for my work laptop, and found out that it supports Android phones, too. So I installed DisplayLink Desktop app and got myself a USB-OTG cable, and BOOM - I can now have HDMI output, and even better, when I plug my Logitech Unifying receiver in it, also a keyboard and a mouse! So, could DisplayLink replace
					- MHL - mobile high
				- Futurism convergence
				  collapsed:: true
					- Swipe from phone to any nearby screen
					  https://youtu.be/JILAs1kLpd4
				- Chromebooks
				  Can use Android apps
				- CPUs and RAM in mobile devices have very poor real world performance compared to desktops but much better power efficiency and made to run on batteries.
				  collapsed:: true
					- huge differences in Size, Architecture and Power consumption between them
					- Qualcomm Snapdragon 835 (Google Pixel 3) vs.
				- Librem 5 and Pyra - ((649b13ca-7483-4a1d-bd90-89845f24084f))
				- Ubuntu Touch and Plasma Mobile - ((631fa93c-fd77-4435-a292-fd9573d0242f))
				- Related: ((631fa93c-fd77-4435-a292-fd9573d0242f))
			- Portable USB drive Linux
			  collapsed:: true
				- (virtualisation allows for quick portability/no restarting PC/easy sharing between the OS's/some PCs have problems booting from USB
				- BUT virtual OS's are slower and possibly persistence can't be used in virtualbox?, system updates can't/shouldn't be done,
				- http://lifehacker.com/how-to-dual-boot-and-virtualize-the-same-partition-on-y-493223329
				- No PC just USB Linux?
				  collapsed:: true
					- + Less weight to carry in backpack. Creates strong divide between Work and Leisure time + can use smartphone for urgent tasks.
					- - Dependent on frequent access to PCs I can use to either boot from USB or have admin privileges on. Unable to do work whilst away from a PC e.g. in evening, whilst travelling etc. Backups less frequent as all changes stored in a single ISO file which may be 2GB+?
				- Can use Tails instead to make sure that no data whatsoever lands on PC
				- or portable apps
				- Portable VirtualBox Linux
				  collapsed:: true
					- http://www.pendrivelinux.com/using-a-portable-virtualbox-to-run-linux-from-usb/
					- http://lifehacker.com/the-power-users-guide-to-better-virtual-machines-in-vir-1569943402
					- Run Virtualise_This_Key.exe to run virtualised Linux, but it requires local admin privileges
					- http://www.linuxliveusb.com/en/help/faq/persistence/68-persistent-do-not-do
				- Bootable Linux USB flash drive
				  collapsed:: true
					- http://www.linuxliveusb.com/
					- ((65a98a51-e0ba-4dc1-93e7-34647c9f6c0e))
					- http://www.pendrivelinux.com/linux-live-usb-creator/ or http://www.pendrivelinux.com/universal-usb-installer-easy-as-1-2-3/ creates one for you
					- Booting your PC from your LinuxLive USB key:
					- Shutdown Windows and insert your USB key in one of your PC's USB port (preferably a rear one for a desktop PC).
					- Power on your PC and quickly press the corresponding keyboard key to access the BIOS. Each BIOS has its own menu so this explanation is generic :
					- Find the boot menu and put USB devices before Hard drives/CD for the boot order. If you don't have any USB option it may mean that your PC is not able to boot from USB.
					- Save and exit the BIOS.
					- For recent PCs, directly hit the boot menu key (F8, F11, F12 depending on the PC) from the boot screen instead and select your USB device there.
					- Your LinuxLive USB key menu should appear (options may vary):
					- Persistent Mode (your data will be persistent)
					- Live Mode (all your data will be discarded after reboot)
					- Install (to install Linux on your hard drive)
					- Usually, you will boot with Persistent Mode by default.
		- On Manufacturers
		  collapsed:: true
			- Lenovo
			  collapsed:: true
				- Many privacy scandals recently
				- Warning: Microsoft Signature PC program now requires that you can't run Linux. Lenovo's recent Ultrabooks among affected systems.
				  [archived] https://www.reddit.com/r/linux/comments/53ri0m/warning_microsoft_signature_pc_program_now
		- Tablets
		  id:: 65a98a50-7ccb-4f08-bc07-ffd8a637b3f6
		  collapsed:: true
			- Meta
				- [Tablet Finder](https://www.gsmarena.com/search.php3?mode=tablet) search
					- [[2025-03-27 Thursday]] Most popular results
						- [Samsung Galaxy Tab S10 FE+ - Full tablet specifications](https://www.gsmarena.com/samsung_galaxy_tab_s10_fe+-13760.php)
						- [Samsung Galaxy Tab A9+ - Full tablet specifications](https://www.gsmarena.com/samsung_galaxy_tab_a9+-12617.php)
						- [Xiaomi Pad 7 Pro - Full tablet specifications](https://www.gsmarena.com/xiaomi_pad_7_pro-13474.php)
						- [Xiaomi Redmi Pad SE - Full tablet specifications](https://www.gsmarena.com/xiaomi_redmi_pad_se-12466.php)
						- [Apple iPad (2025) - Full tablet specifications](https://www.gsmarena.com/apple_ipad_(2025)-13702.php)
						- [Honor Pad X9a - Full tablet specifications](https://www.gsmarena.com/honor_pad_x9a-13751.php)
						- [Infinix Xpad - Full tablet specifications](https://www.gsmarena.com/infinix_xpad-13263.php)
						- [Lenovo Legion Y700 (2025) - Full tablet specifications](https://www.gsmarena.com/lenovo_legion_y700_(2025)-13438.php)
						- [Huawei MatePad SE 11 - Full tablet specifications](https://www.gsmarena.com/huawei_matepad_se_11-13135.php)
			- [Daylight Computer](https://daylightcomputer.com/product)
			  id:: 666ac0ee-bd64-4ece-9eea-01cd98d3ba46
			  collapsed:: true
			  New 60fps ((666ac10e-deb2-4d3f-b8ec-ecd66b91410d)) tablet
				- Pros/Cons
					- Pros
						- [Plans to have an unlocked bootloader](https://news.ycombinator.com/item?id=40460036)
					- Cons
						- ((666ac803-f8e2-4214-97c6-78ae19a33268)) and no ((630f96f0-f2c4-4706-9d72-58e13201e03f)) support for private, secure, FOSS
							- One person says they use [JuiceSSH](https://play.google.com/store/apps/details?id=com.sonelli.juicessh) to SSH into a home machine which they code on. The tablet doesn't have colour so lacks syntax highlighting but otherwise functional
						- [It's a transreflective LCD, not e-paper](https://youtu.be/9M6zT0mRvW0)
							- [Daylight Computer – New 60fps e-paper tablet | Hacker News](https://news.ycombinator.com/item?id=40456834)
						- Black-and-white, not colour. For coding will lack syntax highlighting therefore
					- Unclear
					- Comparisons
				- Sol:OS - custom ((631fa93e-1087-4996-91b8-7526842b4ba8)) ROM
				  id:: 666ac803-f8e2-4214-97c6-78ae19a33268
					- Custom PDF reader which allows flipping through pages and stylus writing
				- Specs
					- 10.5"
					- 8GB RAM
					- 128GB Storage
					- MicroSD slot
					- Android 13
					- LivePaper, they claim it's better than ((666ac187-a18b-46fe-b3ca-b808be184e2e))
				- [Daylight DC-1 - It'll be Good if it ... - YouTube](https://youtu.be/2KfPNoCrZrw)
					- He's skeptical it'll be as good in daylight as ((666ac10e-deb2-4d3f-b8ec-ecd66b91410d))
			- ((67bf96cf-4b46-4e26-b071-0857cc0810ba))
			- {Archive} Outdated
			  collapsed:: true
				- Google Nexus 7 (2013)
				  collapsed:: true
					- LineageOS install failed because `fastboot boot recovery.img` froze the device (attempted 2x)
		- dGPU
		  collapsed:: true
			- MUX switch
				- What is it
					- A MUX (Multiplexer) switch is a hardware component in gaming laptops that allows for switching between the integrated graphics card (iGPU) and the dedicated graphics card (dGPU). It acts as an interruptor, directing frames from the dGPU directly to the display, bypassing the iGPU, which can enhance gaming performance and reduce latency.
					- When the MUX switch is enabled, the laptop can disable Optimus, a technology that typically routes frames through the iGPU, thus improving performance in graphically intensive applications.
					  However, this comes at the cost of battery life, as the dedicated GPU consumes more power than the integrated one.
					- Some newer laptops support Advanced Optimus or similar technologies like AMD's Smart Access Graphics, which automatically switch between the iGPU and dGPU based on workload without requiring a reboot.
					  These technologies can further enhance performance and battery efficiency.
					- To check if your laptop has a MUX switch, you can look at the manufacturer's specifications or check within the Nvidia Control Panel or AMD Radeon Software.
					  For ASUS ROG laptops, you can use Armoury Crate to manage the MUX switch settings.
					- For a comprehensive list of gaming laptops with MUX switches, you can refer to specific guides or manufacturer lists.
				- [Laptops with iGPU + dGPU need a MUX switch for best performance](https://youtu.be/ruhZrv9ppJo?t=168)
					- ![image.png](../assets/image_1740660743138_0.png)
						- If you have a iGPU and dGPU then it typically routes the dGPU via the iGPU, which causes a 5-10% performance hit but saves battery life as it decides whether to render with high performance or high efficiency
					- ![image.png](../assets/image_1740660869961_0.png)
						- MUX switch bypasses the iGPU to avoid the performance hit
		- E-paper
		  id:: 666ac10e-deb2-4d3f-b8ec-ecd66b91410d
		  collapsed:: true
		  AKA Electronic paper
			- Pros/Cons
			  collapsed:: true
				- Pros
					- Battery life is usually multiple days rather than just a few hours
					- Usable in daylight outdoors unlike traditional flat screen displays
				- Cons
					-
				- Unclear
				- Comparisons
			- E Ink
			  id:: 666ac187-a18b-46fe-b3ca-b808be184e2e
				- is a trademark of E Ink Corporation
				- ~2020 they've become much more valuable due to their colour display innovation mainly
			- Info
				- E-paper uses actual ink, like what is used in pens
				- Unlike conventional flat panel displays, it doesn't emit light and instead reflects ambient light
				- Colour
			- ## Products
				- Priority
					- ((666aca5e-950e-4fb7-b93a-5c13604ea2ea)) as it supports Android with Google Play Store + sideloading apps
				- Phone
					- [Minimal Phone](https://minimalcompany.com/collections/frontpage/products/minimal-phone)
						- [This crowdfunded E Ink QWERTY phone isn’t vaporware after all | The Verge](https://www.theverge.com/news/603891/minimal-phone-company-indiegogo-e-ink-qwerty-keyboard-shipping)
					- Boox Palma
					  collapsed:: true
						- [This Phone is Bad... Which Makes it Better? - YouTube](https://youtu.be/xwTub7_we0w)
						- Lacks a SIM slot
				- Tablets
					- PineNote
					- [reMarkable](https://remarkable.com/) line - custom Linux-based OS?
					  collapsed:: true
						- [Remarkable Paper Pro](https://youtu.be/ZkEg8WLeW4Q)
						- reMarkable 2 (2023)
							- [Unboxing the reMarkable 2: The Future of Paper - YouTube](https://youtu.be/pQ9-1dOuTyU)
								- Very thin
								- Typefolio accessory is a keyboard case like Windows Surface
					- ((666ac0ee-bd64-4ece-9eea-01cd98d3ba46))
					- [ONYX BOOX electronic books](https://onyxboox.com/) - colour, supports Android
					  id:: 666aca5e-950e-4fb7-b93a-5c13604ea2ea
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Supports ((631fa93e-1087-4996-91b8-7526842b4ba8))
							- Cons
								- [Violating GPL](https://news.ycombinator.com/item?id=37667242)
							- Unclear
							- Comparisons
						- Products
							- Boox Tab Ultra C Pro
							  id:: 666ae7cc-c35a-49e0-811f-d05f9e60a8fd
							  collapsed:: true
								- Comparisons
									- ((666ae7cc-c35a-49e0-811f-d05f9e60a8fd)) vs ((666ae7d9-830d-4531-add7-9c0b1686f834))
									  id:: 666ade2f-c1d9-45f4-9a7e-3033b7419f95
										- For ((666ae7cc-c35a-49e0-811f-d05f9e60a8fd))
											-
										- For ((666ae7d9-830d-4531-add7-9c0b1686f834))
											-
										- Similarities
											-
										- Unclear
											-
										- [Boox Tab Ultra C Pro — Better than the Note Air 3 C? - YouTube](https://youtu.be/sIHVXaTP0-4)
											- Tab Ultra C Pro has Android 12, Tab Ultra C is Android 11
											- Note Air 3 C has Android 12 as well
											- ((666ae7d9-830d-4531-add7-9c0b1686f834)) keyboard case is worse - it only has 1 angle, whereas ((666ae7cc-c35a-49e0-811f-d05f9e60a8fd))'s one is adjustable. Air's one also lacks a touchpad
											- Touchpad isn't great since there's a delay. But that seems to be only on the homescreen - in Chrome it's fast, much be repainting more frequently
											- Conclusion
												- ((666ae7cc-c35a-49e0-811f-d05f9e60a8fd)) is better if you want a keyboard case. It's good for mobile productivity if you want a laptop replacement
										- [Best Onyx Boox? Note Air 3 C vs Tab Ultra C Pro - Why I’m Sticking to the Pro Model! - YouTube](https://youtu.be/Qg_Cr43a8U0)
								-
								-
							- Boox Note Air 3 C
							  id:: 666ae7d9-830d-4531-add7-9c0b1686f834
							  collapsed:: true
								- Pros/Cons
									- Pros
										-
									- Cons
										-
									- Unclear
										- [Why I'm selling the Onyx Boox Air 3C after 6 Months - YouTube](https://youtu.be/eYQrM-PW80Y)
											- Pros
												- Easy to write on
												- Android support is great for sharing files to other apps/devices, upload notes as PDF
											- Cons
												- Heavier than Kindle so it makes it more annoying as an e-reader, especially unrealistic to one-hand for long periods
												- To get colour to work the backlight has to go very bright
									- Upstream/Downstream Pros/Cons
									- Comparisons
										- ((666ade2f-c1d9-45f4-9a7e-3033b7419f95))
											- {{embed ((666ade2f-c1d9-45f4-9a7e-3033b7419f95))}}
							- Boox GO Series
								- 10.3
									- Ultrathin, black and white
								- 7
					- Supernote
					  collapsed:: true
						- modular repairable
							- [Supernote Manta – Ratta Supernote](https://supernote.com/pages/supernote-manta)
							- [Supernote Nomad – Ratta Supernote](https://supernote.com/pages/supernote-nomad)
							-
						- Supernote A5X
							- [2021: The Best 10.3" E-Ink Tablet: Remarkable 2 vs Boox Note Air vs Supernote A5X](https://youtu.be/CH1pWqY0lPs)
							  Overall best Boox Note Air, though Supernote has very good notetaking capabilities
					- Related: ((65a98a50-7ccb-4f08-bc07-ffd8a637b3f6))
				- Laptops
					- [The Modos Paper Laptop | Hacker News](https://news.ycombinator.com/item?id=31394226) (2022) - abandoned seemingly
					- Lenovo ThinkBook Plus Twist Gen 4 (2023)
					  13" | Two screens, one e-paper and one LCD
					- Related: [Laptops](((65a98a50-3faa-4fa7-93cd-cc5cd081e1dd)))
				- ## Accessories
					- Mini bluetooth keyboard
					  collapsed:: true
						- ![image.png](../assets/image_1729082568397_0.png)
				- Related: ((649b1407-36a5-447b-ba05-aa7a96f80a1b))
			- [Learning Resources]
				- [My Deep Guide](https://www.youtube.com/channel/UCUox4vsU0kP2STRyN0zUNhw)
		- TPM
		  collapsed:: true
			- Microsoft's Pluton
			  collapsed:: true
				- https://www.tomshardware.com/news/amd-zen-4-ryzen-7000-release-date-specifications-pricing-benchmarks-all-we-know-specs
				- enabling more robust security to helps prevent physical attacks and encryption key theft while protecting against firmware attacks. Pluton originally debuted in the Xbox and AMD's EPYC data center processors and is complementary to AMD’s other security features, like AMD Secure Processor and Memory Guard, among others. AMD hasn't officially confirmed that Pluton is present in Ryzen 7000, but it is expected.
				- [Meet the Microsoft Pluton processor – The security chip designed for the future of Windows PCs | Microsoft Security Blog](https://www.microsoft.com/security/blog/2020/11/17/meet-the-microsoft-pluton-processor-the-security-chip-designed-for-the-future-of-windows-pcs/)
				- The TPM was a good start for security, and according to Microsoft, it forced attackers to get more creative. Baddies started looking for weaknesses in the TPM system and they focused on one particular soft spot: the communication lines between the TPM hardware chip (typically found on the motherboard) and the CPU.
					- Pluton solves this weakness by removing the need for "outside" communication between a TPM and the CPU. Instead, Pluton and its TPM-like functionality is one more component built onto the die of the processor itself. Microsoft says this makes it harder to extract sensitive information even if the attackers have physical possession of a device.
		- Desktop PC form factors
		  id:: 67c095e1-f226-4386-b0c2-e9c43737c6ee
		  collapsed:: true
			- Comparisons
				- ![image.png](../assets/image_1740678141115_0.png)
				- [ATX vs Micro ATX vs Mini ITX vs E-ATX](https://youtu.be/QXOi0NkyvJk)
			- Mini-ITX
			  id:: 67c08d46-8353-4111-9176-11f20fd10ff8
			  Smallest\
				- WIP build
					- [Part List - AMD Ryzen 9 9900X, Radeon RX 6900 XT, Lian Li A4-H20 X4 Mini ITX Desktop - PCPartPicker](https://uk.pcpartpicker.com/list/7jR49C)
					  id:: 67cc4886-c968-4848-abe8-37a13fb98114
					-
				- [The Smallest Ryzen 9700X SFF Mini ITX Gaming PC You Can Build Right Now! - YouTube](https://youtu.be/6IsbifQs0Ms) - low profile GPU
				- [Q1 2025 Mini-ITX gaming PC build](https://youtu.be/-FYluUsPxfI)
				  collapsed:: true
					- Main parts included in the build:
					  (UK Amazon)
						- CPU: [amzn.to/4k8jvnm](https://amzn.to/4k8jvnm) £190-500
						- GPU: [amzn.to/4hO3KQL](https://amzn.to/4hO3KQL) £360
						- RAM: [amzn.to/3Xdju7E](https://amzn.to/3Xdju7E)
						- £680
							- Case: Overclockers - £100
							- MOBO: [amzn.to/3CZ4R14](https://amzn.to/3CZ4R14) - £280
							- PSU: [amzn.to/3Xc4Opg](https://amzn.to/3Xc4Opg) - £170
							- Cooler: [amzn.to/3ERsWHF](https://amzn.to/3ERsWHF) - £35
							- Fan 120mm: [amzn.to/3EQ1xWD](https://amzn.to/3EQ1xWD) - £31
							- Fan 140mm: [amzn.to/4beW5ZA](https://amzn.to/4beW5ZA) - £27
							- Cable Extensions: [amzn.to/41qwnxM](https://amzn.to/41qwnxM) - £33
						- SSD: [amzn.to/41mlixH](https://amzn.to/41mlixH)
						- Keyboard: Drop x Noctua
						- Mouse: [amzn.to/4hPrHqX](https://amzn.to/4hPrHqX)
						- Monitor: [amzn.to/4hNz41P](https://amzn.to/4hNz41P) - £230
						- Espresso Machine: [amzn.to/40lcTsK](https://amzn.to/40lcTsK)
				- ((635037c3-27fc-4bd1-8958-5c3c8d2d46bb))
				  collapsed:: true
				- Related: [Reddit - Dive into anything](https://www.reddit.com/r/sffpc)
		- [Learning Resources]
		  collapsed:: true
			- http://youbroketheinternet.org
			- Wiki of hardware that works with Libre Linux variations
			  https://h-node.org/home/index/en
			- FlexVer
				- This is a new upcoming add-on/extension for the D16, ETA some time in 2017.
				- FlexVer is a new, owner-controlled security technology designed to safeguard critical data and applications in the event of software or hardware tampering. FlexVer allows a system to be provisioned in a trusted physical environment, then deployed to an untrustworthy physical location while retaining system integrity. Provided that OS-level attack avenues are properly mitigated, for example through the use of TRESOR and similar technologies, FlexVer allows deployment of provisioned systems without concern of hardware and/or software tampering and subsequent extraction of sensitive material — a provisioned system can be guaranteed to be answering only to its previously configured owner, not the owner of the physical space in which the system resides. This is a major departure from prevailing security models, which largely assume that either the possibility of physical access by a malicious actor must result in loss of trust of the affected system, or that trust must be delegated to the system vendor in all situations.
				- Unlike existing security technologies, FlexVer™ does not depend on a fully trustworthy vendor for the root of system trust. Recent events have shown that this trustworthy vendor assumption is not valid, and in fact there is strong pressure on all vendors to compromise their root of trust for financial gain, warrant-related data extraction, industrial espionage, and related purposes.
				- Raptor Engineering, the company developing it, wrote a white paper about it. Read more about FlexVer here (it’s planned for a release on Libreboot D16):
				- https://www.raptorengineering.com/TALOS/documentation/flexver_intro.pdf
				- FlexVer is useful in all kinds of environments, including offices and datacentres, where security is critical.
			- https://fsfe.org/campaigns/android/android.en.html
	- Prebuilts
		- [Raspberry Pi 500+](https://thepihut.com/products/raspberry-pi-500-plus?src=raspberrypi)
			- https://www.raspberrypi.com/news/the-ultimate-all-in-one-pc-raspberry-pi-500-plus-on-sale-now-at-200/
			-
	- Building a PC
	  id:: 65a98a50-811c-4de7-8127-0919127fe8af
	  collapsed:: true
		- Meta
		- Websites
			- [PC Part Picker](https://uk.pcpartpicker.com/)
			  id:: 67c9bc69-f410-48ab-9d10-3cf20d9304a2
		- # Analyses
			- ((6827b4f7-8a40-47d0-9b2f-1341509daf11))
			- ((67cc4886-c968-4848-abe8-37a13fb98114))
			- ((68239af8-eec3-49f2-a0f4-108b5d0fb05f))
		- # Types
			- Laptop workstation
			  id:: 68397c08-2f2f-4d4a-8dee-ff315410d4dc
			  collapsed:: true
			  AKA [Battletop](https://www.reddit.com/r/Battletops) | i.e. laptop desk setup
				- Pros/Cons
					- Comparisons
						- ((68397c08-2f2f-4d4a-8dee-ff315410d4dc)) vs ((68397b4b-5d27-45a7-a60f-957146bf35ac))
							- For ((68397c08-2f2f-4d4a-8dee-ff315410d4dc))
								- Lower power usage and thus energy costs
							- For ((68397b4b-5d27-45a7-a60f-957146bf35ac))
								- Can be paired with a cheap mobile PC (e.g. ((65a98a50-a2bd-44d0-849a-24c12fce1c0a)), laptop) then just ((649b1407-55b9-422c-9a49-cbe295d8b257)) into it (as long as you have decent mobile data speed and caps)
								- Laptops have a much weaker CPU, so needs to be upgraded more frequently if you play [[Videogames]]
							- Similarities
								-
							- Unclear
								- Hardware differences
								  collapsed:: true
									- RAM
										- Laptops use SODIMM (small-outline DIMM) whilst desktops use DIMM
											- Laptop RAM costs more due to the miniaturisation
											- RAM adapter cards can be used e.g. [DDR5 one](https://www.amazon.co.uk/GINTOOYUN-Desktop-Laptop-Adapter-Modules/dp/B0DMVTXVZB)
									- GPU
										- Different sizes
									- CPU
										- Different form factors
											- AMD currently using AM5 for desktops,
										- Performance [[2025-03-07 Friday]]
											- Using ((67caaf64-390f-4469-a55f-a66d630fcc87)) : ((67caaf7b-8c0e-4988-856e-d843110c1177))
												- $400 new desktop CPU: AMD Ryzen 9 9900X = **55k** performance
											- Compared to ((64e09530-f479-418d-8884-b6237793da5a)) : ((67cab004-8f25-4a3d-acb9-19e12d32c5ef))
												- 9x better than ((65a98a50-4b57-4816-931f-24253c6bc8b7)) : ((65a98a50-1909-412b-80ef-5acf9606884d))
												- 2x better than ((659d093f-bf67-444a-b2a1-ec0a28907583)) : ((66705c8f-4f0c-41ba-8a41-e617c684b43d))
											- Unowned comparisons
												- ((67be306c-e648-4944-ba0d-519e57c36e36)) : ((67ca0922-9429-47ba-b36c-3282172e7379))
												- ((635037c3-27fc-4bd1-8958-5c3c8d2d46bb)) : unavailable currently
				- [[2025-05-30 Friday]] My current setup at Lynwood Road is a battletop
					- ((659d093f-bf67-444a-b2a1-ec0a28907583))
					- £23 [havit Cooling Pad 12"-17" Laptop air Cooler](https://www.amazon.co.uk/dp/B00NNMB3KS)
					- ((64e0946d-1d0e-4824-b150-1a08f26aba23))
					- ((64e09471-b7bd-48ea-943c-8da24f86a17b))
					- ((6491cef7-d83e-4aab-abef-33cbb630a02d))
					- ((6491cf16-0eb6-49fc-a49d-b395cb49fb00))
				- # Builds
					- Screenshots
						- [New sit-stand desk - r/Battletops](https://snoo.habedieeh.re/r/Battletops/comments/1gnfume/new_sitstand_desk/)
						  id:: 68399f94-1c33-41ed-9895-2a4ac80a2667
						  collapsed:: true
							- ![image.png](../assets/image_1748606856775_0.png)
						- [My laptop run game/DND station. - r/Battletops](https://snoo.habedieeh.re/r/Battletops/comments/1ggfhre/my_laptop_run_gamednd_station/#)
						  collapsed:: true
							- ![image.png](../assets/image_1748606804956_0.png)
			- Desktop PC 
			  id:: 68397b4b-5d27-45a7-a60f-957146bf35ac
			  collapsed:: true
			  AKA [Battlestation](https://www.reddit.com/r/battlestations/) / Workstation
				- [Custom PC Builder | Gaming Desktops & Laptops | CyberPowerPC](http://www.cyberpowerpc.com/)
					- You pick your parts, they build it, they ship it to you, plug it in. They are cheap and have clearance builds all the time.
				- Workstations can be gaming PCs, but often not vice versa
				  collapsed:: true
					- All a workstation needs is a decent GPU
					- Gaming PCs need better CPUs; more/better RAM
				- # Components
				  id:: 67cc4886-06b2-4997-add7-26eb6fefcf23
					- ((67c095e1-f226-4386-b0c2-e9c43737c6ee))
					- Motherboard
					  collapsed:: true
						- Quad socket CPU is impractical
						  collapsed:: true
							- 1. In order to run CPUs in a quad socket motherboard, you must use intels xeon 4000 series (the first number indicates how many CPUs can work together in tandem)
							- 2. Quad socket motherboards are all going to be very expensive, because windows cannot use more than 2 physical processors at the same time (except server editions). Therefore very few people buy them increasing the costs.
							- 3. Quad socket mobos consume power, A LOT of power. You will need two PSUs to run it.
							- 4.  scaling up CPUs to multiple sockets yields dimishing returns. Thing about returns similar to adding more GPUs to an SLI config
						- CPUS for socket 2011 will not work in a socket 2011-3 socket and vice versa
						- AMD has longer-lasting socket types for their CPUs than Intel (e.g. AM4 being supported until 2020)
						  [Reddit - The heart of the internet](https://www.reddit.com/r/Amd/comments/8bc8yv/how_future_proof_is_the_am4_socket_right_now/)
					- CPU
					  collapsed:: true
						- CPU
							- Dual CPU + score
							  collapsed:: true
								- Most CPU characteristics must match
								  http://www.tomshardware.co.uk/forum/272899-28-different-processors-dual-socket-motherboard
								- Score
								  collapsed:: true
									- 18300 - [Dual CPU] Intel Xeon E5-2670 @ 2.60GHz
									  https://www.cpubenchmark.net/cpu.php?cpu=Intel+Xeon+E5-2670+%40+2.60GHz&id=1220&cpuCount=2
									- 16800 - [Dual CPU] Intel Xeon E5-2620 v4 @ 2.10GHz
									  https://www.cpubenchmark.net/cpu.php?cpu=Intel+Xeon+E5-2620+v4+%40+2.10GHz&id=2766&cpuCount=2
							- Best value for money CPU
							  source:: Linus Tech Tips late 2018 what CPU to buy
							  collapsed:: true
								- **Cost is for whole budget, not just CPU price**
								- Intel Core i7 and Ryzen 7 processors are the most powerful processors that should be used in a gaming PC, with anything more powerful simply being overkill. But as you can see, workstations go much further beyond, making thorough use of CPUs that would never be used for gaming unless the workstation serves both as a workstation and a gaming PC.
								- _All-rounder performance_
								  collapsed:: true
									- Budget $500: Ryzen 5 2600X
									- Mid-range $1k:
									  collapsed:: true
										- _Motherboards are fairly expensive but best performance_
										  collapsed:: true
											- Intel Core i7-9700K
											- Threadripper 1920X
											  More available; better for producivity than gaming 
											  Core
										- _Cheaper motherboards, still good performance_
										  collapsed:: true
											- Core i7-8700K
											- Ryzen 7 2700X
									- High-end $2k:
									  collapsed:: true
										- Threadripper 2950X
										- Threadripper 2920X
										- Core i9-9900K
								- _Gaming performance_
								  collapsed:: true
								  Per-thread performance
									- Budget $500: Ryzen 5 2600X
									- Mid-range $1k
									  collapsed:: true
										- Core i5 8600K
										  Though you also need a Z-series board and after-market cooler
										- Core i5 8500 (recommended for sticking to $1k
										- Ryzen 5 2600X
									- High-end $2k:
									  collapsed:: true
										- Core i5 8600K
										- Core i7 9700K
								- Workstation
								  collapsed:: true
								  CPUs
									- Budget $500: Ryzen 5 2600X (£200 2018 Amazon)
									  https://www.amazon.co.uk/AMD-YD260XBCAFBOX-RYZEN5-Socket-Processor/dp/B07B428V2L/ref=sr_1_2?ie=UTF8&qid=1544591957&sr=8-2&keywords=ryzen+5+2600x
									- Mid-range $1k:
									  collapsed:: true
										- Threadripper 1920X (£400 2018 Amazon
										  collapsed:: true
										  https://www.amazon.co.uk/AMD-Ryzen-Threadripper-12-Core-Processor/dp/B074CBJHCT/ref=sr_1_4?ie=UTF8&qid=1544593947&sr=8-4&keywords=threadripper+1920x
											- X399 Mobo $300
											- $280 only leftover for cooler, RAM, storage, GPU, case, PSU
										- Core i7 9700K
										  No ECC support nor included cooler
										- Ryzen 7 2700X (£320 2018 Amazon/eBay)
										  collapsed:: true
										  Main recommendation
											- Has ECC support and included cooler
									- High-end $2k:
									  collapsed:: true
										- Threadripper 2950X
										- Theadripper 2920X
										- Theadripper 1920X
							- Related: Quad socket motherboards
							  intralink2:: https://workflowy.com/#/321e62cdc159
						- [AMD processor specs](https://www.amd.com/en/products/specifications/processors.html)
						  id:: 67cacc9f-285c-4853-b89f-9279c9d8277a
					- CPU coolers
					- ### GPU-related
					  collapsed:: true
						- GPU
						  id:: 65a98a50-185a-4092-8cb4-9679eaf032fa
						  collapsed:: true
						  AKA Graphics Card
							- Meta
								- Compatibility
									- Basically as long as it's PCIE then it'll be compatible
									- Though there are also generations (e.g. Gen 4 card) which will be backwards compatible with older slots but will be more limited
									- Also they'll only operate at the number of lanes allowed on the motehrboard
							- # Owned
								- ((675b54e8-8525-4506-aa10-a82779f66332))
								- Geforce GTX 1050Ti 
								  id:: 65a98a50-8c8c-4c6a-b4f8-3a646555df15
								  collapsed:: true
								  from Gigabyte
									- 4GB GDDR5
									- Dual-slot ?
										- PCI-E 16X slot
									- PCI-E 3.0x16
									- 3* HDMI
								- AMD Radeon RX 580 
								  id:: 65a98a50-1db2-4f58-9aa9-c4c846b0f87f
								  collapsed:: true
								  from MSI
									- Comparisons
										- ((65a98a50-1db2-4f58-9aa9-c4c846b0f87f)) vs ((65a98a50-8c8c-4c6a-b4f8-3a646555df15))
											- [UserBenchmark](https://gpu.userbenchmark.com/Compare/AMD-RX-580-vs-Nvidia-GTX-1080-Ti/3923vs3918) - 1080 is 50% better minimum on games like Minecraft and Dota
											- [[2024-11-14 Thursday]] Helldivers is actually more performant by 2 FPS on the AMD
								- https://forums.guru3d.com/threads/what-vid-cards-have-uefi-gop-support.370375/ Going by this discussion, NVidia GPUs of the 7xx Series and AMD 4xx Series or newer should support UEFI boot out of the box. Some older cards(i.e. GTX670) had enough ROM space and got updates to an UEFI compatible BIOS. So if you buy anything that's not older than those you're fine except maybe some special server cards.
							- # Models
								- [AMD](https://www.amd.com)
								  collapsed:: true
									- Pros/Cons
										- Cons
											- Poor for machine learning. AMD's ROCm is dogshit compared to CUDA
											  collapsed:: true
												- Two main issues. One is performance; on the same task, an AMD card will get absolutely bodied by a comparably priced Nvidia card. Second is ecosystem; Nvidia started giving out cards to scientists and encouraging them to use CUDA years and years ago, so basically everything forever is either compatible with CUDA, or designed with CUDA in mind, to the point that AMD would have to invest huge amounts of money on porting shit over to ROCm just to have even a fraction of the ecosystem. In my opinion, if they wanted to be competitive, what they would need to do is to have significantly superior performance at a lower price than Nvidia, and then rely on market forces to slowly increase ROCm adoption. Otherwise, frankly, the game's over, Nvidia already won.
												- You also forgot that ROCm doesn't work on Windows at all while CUDA is cross platform.
										- Unclear
											- [GitHub - vosen/ZLUDA: CUDA on non-NVIDIA GPUs](https://github.com/vosen/ZLUDA)
									- Meta
										- Naming convention
										  collapsed:: true
											- It's really quite simple and very similar to NVIDIA's naming scheme.
											  
											  First digit is the generation (currently 6XXX)
											  
											  Second digit is the relative performance (64XX < 65XX < 66XX < 67XX < 68XX < 69XX)
											  
											  "XT" suffix - similar to NVidia's "Super" designation. Non-Zero third digit is like Nvidia's "Ti" designation: 6600 < 6600 XT < 6650 XT.
										- https://github.com/vosen/ZLUDA for CUDA
									- Bought
										- £460 [AMD Radeon RX 6900 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6900-xt.c3481)
										  id:: 675b54e8-8525-4506-aa10-a82779f66332
										  collapsed:: true
											- [Specs](https://www.techpowerup.com/gpu-specs/radeon-rx-6900-xt.c3481)
												- Bus Interface: PCIe 4.0 x16
												  id:: 67ca2ea8-f65a-45a9-8171-a61f4205d402
													- ((67ca2ecf-7c79-4c0f-9d6a-50cf78f16bb8)) : ((67ca2f62-7172-4c71-bc14-6418c0e76b9a)) : ((b0a5a138-a3ee-4e12-802c-03a48a4034d2))
											- Retail board
												- [£460 purchased from Amazon](https://www.amazon.co.uk/dp/B09NQDW5VH) 
												  Gigabyte Aorus Radeon RX 6900 XT Master 16G Rev 2.0 (16GB GDDR6/PCI Express 4.0/2335MHz/16000MHz)
													- [TechPowerUp page](https://www.techpowerup.com/gpu-specs/gigabyte-aorus-rx-6900-xt-master-rev-2-0.b10396)
														- 322mm long
														- 1925 MHz | 2335 MHz  | 2000 MHz
									- RX 6950 XT
									- RX 6900 XT
									- RX 6800 XT
									- RX 6800
									- RX 6750 XT
									- RX 6700 XT
									- RX 6650 XT
									- RX 6600
									- RX 6500 XT
									- RX 6400
									- RDNA 3
									  collapsed:: true
										- [Goodbye NVIDIA. – AMD RDNA3 Announcement - YouTube](https://youtu.be/YSAismB8ju4)
										  collapsed:: true
											- AMD is back and Nvidia is about to pay for their outrageous pricing practices the rdna3 announcement just concluded and while AMD gave us very little in the way of meaningful performance data I'm really optimistic anyway and here's why immediately after the stream ended our Labs team sprang into action building up test benches as close as possible to the ones that AMD used in their performance preview that allowed us to expand on amd's rather vague slides that didn't include a single Nvidia GPU and extrapolate some actually useful comparative performance data now the bad news is that Nvidia might still be the performance King but the good news is that I can confidently say that amd's new Radeon RX 7900 XTX should come within spitting distance of nvidia's RTX 4090 for 600 dollars less the only thing with better performance per dollar is this segue to our sponsor PDQ PDQ makes device management simple secure and pretty damn quick automate your patch management and software deployment processes with PDQ deploy and inventory start your free trial now at pdq.com LTT [Music] in amds together we advance underscore gaming live event they announced the two Flagship tier gpus that will lead their rdna 3 family the Radeon RX 7900 XT and 7900 XTX with 20 and 24 gigabytes of gddr6 respectively which was my first surprise I mean why would they cheap out on the memory when they need to compete with Nvidia cards that are using faster gddr6x two reasons one to save power which fair enough given the reputation their competition is built for unreasonable power consumption in thermals and two they just don't seem to need it the most useful slide that AMD provided was this one where we see the 7900 XTX performing between one and a half to 1.7 times the outgoing Flagship 6950 XT at 4K now AMD was frustratingly vague about the exact settings that they used to achieve these results even when we probed them after the event but we managed to extract just enough information to create our own set of performance graphs by extrapolating from our own reference 6950xt let's start with cyberpunk 2077 amd's previous best managed 46 FPS not great but multiply that by 1.7 and we've got a spicy 78 frames per second that's just a single frame per second behind the RTX 4090 flood a generational Improvement in Call Of Duty Modern Warfare 2 our RX 6950xt managed a respectable 90 FPS when we multiply that by amd's 1.5 times assuming of course they're not just outright lying we can expect the 7900 XTX to lag nvidia's Flagship by only six percent pot dang finally in Watchdogs Legion the 7900 XTX takes its largest L compared to the RTX 4090 but that still only has it lagging behind by about 10 not too shabby AMD of course performance is meaningless if it'll cost you two fingers and your right butt cheek Nvidia and I have more good news the 7900 XTX is a thousand dollars while the 7900 XT comes in a hundred less at 900 which I mean I never thought I'd be happy about even a top tier GPU being only a thousand dollars but I guess that really shows just how out to lunch Nvidia has been with the pricing of the RTX 4000 series but wait a second didn't nvidia's CEO Jensen go out on stage and basically say the pricing is so high because the factors outside is control Moore's Law is dead he said well how did AMD pull it off then well first of all by not using the latest and greatest manufacturing process rdna 3 gpus at least the ones we've seen so far are made using a combination of tsmc's five nanometer and six nanometer processes making this both the very first chiplet design GPU and way cheaper to manufacture than the four nanometer monolithic dies that Nvidia uses for RTX 4000 but you'd think there'd be a downside to that right like don't all their manufacturing nodes have worse power consumption believe it or not the total board power of the 7900 XT and XTX is just 300 and 355 Watts respectively and it's delivered by two good old-fashioned eight-pin pcie power connectors I never thought I'd be adding not a fire hazard as a selling point for a GPU but here we are this also means that if you're upgrading from something like a GTX 1080 TI or an RTX 2080 you probably don't need to upgrade your system power supply and you also probably don't need to upgrade your case the reference 7900 XTX is a much more reasonable 287 millimeters wide and two and a half slots tall compared to the 304 millimeters and three and a half Slots of the RTX 4090 again I never thought a GPU physically fitting in your computer would be a major selling point but here we are how did they do this then well AMD also packed in some really cool power management Innovations for starters they decoupled the clock speed of the shaders which now run at up to 2.3 gigahertz and the front end which runs at 2.5 we've actually seen this before in Mobile products but never in a desktop GPU and the main benefit of this approach is that it allows them to prioritize the speed of one over the other depending on the workload for instance if the gain you're running doesn't hit the shaders super hard maybe those are fine just sipping power at 1.8 gigahertz while the front end runs at full speed AMD says this can reduce total power consumption by 25 percent which might not be something you care about if you have a beefy power supply and a well-cooled case already though fear not AMD says there will be aib partner cards with more Cooling and higher power consumption to enable even higher clock speeds or AMD says anyway so far we've only only found this Asus tough model with three eight pin connectors which might indicate higher power consumption but nothing to say of the clock speeds now possibly the dumbest problem with the RTX 4090 aside from the burning up 12 pin power adapters is that it only supports DisplayPort 1.4 which given how freaking fast it is could actually become a problem in the very near future as new displays become available AMD on the other hand managed to avoid this embarrassing situation by including DisplayPort 2.1 which can support ridiculous resolutions and frame rate combinations like 4K 480 Hertz or 8K 165 Hertz now obviously whether you go team green or team red your GPU won't be able to keep up with that today but with the way that upscaling and frame generation technology is progressing VP 2.1 is some massive future proofing that could make the RTX 4090 unable to take full advantage of monitors that could be releasing as early as next year AMD has also included a new media engine that has 8K 60 av1 and code and decode support this is a huge Boon for streamers who are looking to get the best image quality going forward and they announced smart access video which can share the load of encode and decode operations between AMD gpus and CPUs apparently giving a 30 uplift in 4k multi-stream transcoding though we'll have to see how well this actually works when it lands an OBS in December I'm a little skeptical but In fairness to AMD the recent software upgrades that they made to their media engine for Radeon 6000 did bring about image quality improvements to get them closer to Nvidia zenbank than I would have thought possible so with this new media engine AMD might finally be a sensible choice for people who want to stream or record their gameplay another sensible choice is signing up for floatplane.com for amazing behind the scenes and Extras like the shooting of our starforge systems review intro to be clear not everything that AMD announced today was mind-blowing in amd's own slides they show a 1.5 to 1.6 times increase in Ray tracing performance which will take you from literal slideshow to cinematic FPS at best and the RTX 4090 walked all over amd's best at nearly double the frame rate based on our cyberpunk test and these projected numbers also AMD built new AI accelerators that should allow for up to 2.7 times more AI throughput per compute unit but the way it's implemented makes this increase only matter for games at the moment it's not going to help you with general purpose Ai and actually come to think of it there was almost no mention whatsoever of non-gaming tasks and this this is a long time thorn in Radeon users sides some applications like blender or SolidWorks visualize only support Nvidia Cuda making Nvidia cards absolutely embarrass their AMD counterparts and it doesn't look like this is going to change anytime soon AMD also promised that their new fsr3 upscaling would be up to a two times increase over fsr2 but it looks like at least one of the ways they're going to achieve this is with technology similar to nvidia's dlss 3 by generating new frames and well let's just say we're currently working on a video about DLS S3 and its frame generation and it's a first gen product overall though it looks like the RX 7900 XT and XTX are going to be hacking fast gpus for the money and this might end up being the first generation of what feels like forever where AMD is positioned to grab a good chunk of market share from our green overlords which will hopefully push Nvidia to compete harder on pricing and meanwhile give amd's GPU division the cash that it needs to ramp up r d spending and come back even stronger next time I can't wait to give you guys the full review when these cards launch on December the 13th just like I can't wait to tell you about this Segway to our sponsor micro center micro center carries a wide variety of laptops computer components monitors communication devices TVs networking you name it they've got it with over 30 000 items in stock they are 25 stores across the US provide amazing selection and competitive prices so you always leave with what you're looking for and we've done multiple video projects at Micro Center locations at have always been impressed by the staff's knowledge and the stock that's available Microcenter has great deals both in-store and online so click the link in the description to check them out today if you guys enjoyed this video go check out our RTX 4090 undervolting video where the power consumption of the 4090 starts to look not that bad even if the price is still obscene
									- Related:
										- AMD CPUs
										  id:: 65ed913e-a800-4c75-9493-ec51705c63eb
										  collapsed:: true
											- Pros/Cons
											  collapsed:: true
												- Pros
													- Supports the [AM5 socket](https://en.wikipedia.org/wiki/Socket_AM5) until at least 2025
												- Cons
													- Pluton processor is likely a hardware backdoor
												- Unclear
													- Zen 5 chips coming out late 2024. Expected 20-30% performance increase over 7000 series
												- Comparisons
											- Meta
												- ![image.png](../assets/image_1710067992609_0.png)
								- [NVIDIA](https://www.nvidia.com)
								  id:: 65a98a50-cabf-42dc-9a06-413b96e93ae7
								  collapsed:: true
									- Meta
										- Use `sudo kubuntu-driver-manager` then additional drivers - select one before the latest and avoid server ones
									- Nvidia DLSS / AMD FidelityFX Super Resolution
									  collapsed:: true
										- AMD FidelityFX Super Resolution
										- Effects
										-
										- Similar
										- Related: [Candidates for DLSS](https://workflowy.com/#/2f68f1f9eb41)
									- GeForce 20 series
										- GeForce RTX 2070 (Q4 2018)
										- GeForce RTX 2080 (Q4 2018)
										- GeForce RTX 2080 Ti (Q4 2018)
									- GeForce 30 series
										- GeForce RTX 3060 Ti (Q4 2020)
										- GeForce RTX 3070 (Q4 2020)
										- GeForce RTX 3080 (Q4 2020)
										- GeForce RTX 3080 Ti (Q2 2021)
										- GeForce RTX 3090 (Q4 2020)
										- GeForce RTX 3090 Ti (Q1 2022)
								- Comparison
									- ![image.png](../assets/image_1665659367275_0.png)
								- It's so badass that every time Nvidia makes a new proprietary gimmick, AMD makes a FOSS version that everyone can use (RTX, DLSS, G-Sync, etc).
							- # Ecosystem
								- Comparisons
									- [TechPowerUp - GPU Specs Database](https://www.techpowerup.com/gpu-specs/)
									- [GPU UserBenchmark](https://gpu.userbenchmark.com/)
						- eGPU enclosure
						  id:: 63ad9565-9f04-447d-b3c2-7541d47f2703
						  collapsed:: true
						  (external graphics card)
							- Glossary
							  collapsed:: true
								- eGPU - external
								- iGPU - intergrated
								  Much weaker than dGPU or eGPU
								- dGPU - dedicated
							- **PURCHASED**
								- _eGPU docks/enclosures_
									- Razer Core X
									  id:: 65a98a50-fb13-418e-adad-222f5fdccf04
									  collapsed:: true
										- [Review](https://egpu.io/razer-core-x-review-thick-juicy/)
										- V2 vs X
											- ![image.png](../assets/image_1741303038003_0.png)
										- [32Gbps-TB4](https://egpu.io/best-external-graphics-card-builds/) according to egpu.io
										- ((67ca17fc-6cb7-4a7a-9fb0-47cb2c868918))
										- ### Compatible cards
											- 3070?
											- A RTX 3080 is the maximum performance via a TB3 you will be able to extract. So anything 4000 series at that level or a 3080 if you can get a second hand one.
											- My 3080 ti got 16000 ish in 3Dmark paired with a I7 12700H (benchmarks aren’t always a good measure though)
											- Anything above a 3080 is going to face the law of diminishing returns. You'll start seeing more and more cases of 10 percent or lower performance increases. Your enemy is thunderbolt which will be the most prominent bottleneck for most people. Therefore 3080, for the 30 series, seem s like the best option. One can argue 40 series with frame generation software. But I wouldnt go above a 4070/ ti
											- I got a 3090 external. Works great. Just as fast as internal, no bottle necks at all. Wish I had more than 24gb vram.
											- 4070 - "MSI Gaming RTX 4070 Super 12G Ventus 2X OC Graphics Card (NVIDIA RTX 4070 Super, 192-Bit, Boost Clock: 2520 MHz, 12GB GDRR6X 21 Gbps, HDMI/DP, Ada Lovelace Architecture)" model number is G4070S12V2C.
											- TLDR; I put a 4070 Super in a Razer Core X and got 73% of the average performance in Geekbench OpenCL.
									- EXP GDC dock
										- 6-pin female to male (for dock to GPU)
							- # Status
								- [[2025-05-30 Friday]] ((67c1ad55-6362-4335-9375-3811a8f7efb8)) is coming out on some devices currently, and is a significant enough upgrade from ((67ca17fc-6cb7-4a7a-9fb0-47cb2c868918)) that it'd be worth upgrading to
								- Wayland KWin now supports GPU hotplugging, but hot-unplug not supported
								  id:: 644c0aa9-31fb-43b7-bd15-0c57eb2e7204
								  collapsed:: true
									- My issue
										- [GPU hot-unplugging not possible (#151) · Issues · Plasma / KWin · GitLab](https://invent.kde.org/plasma/kwin/-/issues/151)
									- [AMD kernel WIP for usecase of a user unplugging eGPU without session crashing](https://gitlab.freedesktop.org/drm/amd/-/issues/1081#note_1064019)
									- [KWin cannot currently let go of the GPU either](https://invent.kde.org/plasma/kwin/-/merge_requests/811#note_281753)
										- [https://invent.kde.org/plasma/kwin/-/issues/46#note_282113](https://invent.kde.org/plasma/kwin/-/issues/46#note_282113)
									- Other issues
										- [RADV poor performance](https://gitlab.freedesktop.org/mesa/mesa/-/issues/7340#note_2248642)
										- [Wayland multi-GPU](https://gitlab.freedesktop.org/wayland/wayland-protocols/-/merge_requests/268#note_2413304)
									- To test
										- [[2024-10-15 Tuesday]]
											- Wayland - doesn't crash the compositor. Seems to support hot-unplug fine
											- X11 - Still immediately crashes during hot-unplug, though it at least shows a terminal error this time
							- # Documentation
								- [GitHub - hertg/egpu-switcher: 🖥🐧 Setup script for eGPUs in Linux (X.Org)](https://github.com/hertg/egpu-switcher)
									- [Limitations](https://github.com/hertg/egpu-switcher#limitations)
										- No hotplugging is possible. Users still need to reboot their computer to connect / disconnect the eGPU.
								- How is the eGPU support? I had to get a 2018 Dell XPS with 4 PCIe lane Thunderbolt 3 support since the 2017 version had only 2 PCIe lanes dedicated to TB3.
									- Doesnt matter if these lanes are used for 2 TB3 ports instead of one
								- _Linux-based_
									- ((64e0952c-f4f6-4da9-af2c-f22810f4bee9))
								- _Windows 10_
									- [[2024-09-06 Friday]] ((65a98a50-4b57-4816-931f-24253c6bc8b7)) + ((66bcab7d-832c-419b-a6fa-7b14ff73ddc5)) on internal NVME + ((65a98a50-fb13-418e-adad-222f5fdccf04)) + ((65a98a50-1db2-4f58-9aa9-c4c846b0f87f))
										- Just needed to install all the relevant critical drivers from the Dell website for my laptop (also saved to `/Documents/Optional/Windows` now) then it was plug-and-play in the top-left port (also bottom left should work)
									- Dell XPS 8380 + Windows 10 on an external SSD + Razor Core X + AMD Radeon 580 or Nvidia 1050Ti via Razer Core X
									  collapsed:: true
										- Game display resolutions for Dell external monitor
											- GTA V
												- 1280x1024, 4:3 aspect ratio
										- 30/6/20 summary
											- Must use an external display (second monitor) since AMD switchable graphics is deprecated in favour of Windows 10
												- This required HDMI connection into ((65a98a50-fb13-418e-adad-222f5fdccf04))
											- Windows 10 is on a 1TB SSD, connected via a USB C adapter
												- Tests using a Usb C hub (that also has my Blue Yeti mic) show it's power consumption is low enough for Planetside 2, but with GTA V it causes Windows to crash
												- Try with my powered SATA to USB cable. Need a longer powered cable
										- Tested 4/4/20
											- GPUs are detected as eGPUs correctly but their relevant applications can't set them to use the eGPU on the internal laptop display
												- AMD has AMD XConnect which can detect programs on eGPU but can't force them
													- AMD switchable graphics is deprecated in favour of Windows 10 'Graphics settings' menu
												- Nvidia has both detection and a force method but the force method didn't work on internal laptop display
											- However both GPUs worked plug-and-play on an external monitor
												- Note need to have the game on that monitor only or turn off laptop display completely using Windows Display Settings
												- This required HDMI connection into ((65a98a50-fb13-418e-adad-222f5fdccf04))
												- It also prevented sound from going through headphones plugged into laptop. Presumably routed to external monitor or there may be some way to retain audio output
								- EXP GDC dock
								- [eGPU fix](https://egpu.io/forums/expresscard-mpcie-m-2-adapters/script-nvidia-error43-fixer/) (for Windows 7)
								- eGPU connection
								  collapsed:: true
									- Ports: mPCIe (mini PCI Express), Expresscard, Thunderbolt1 or 2, M.2, and finally, Thunderbolt3.
										- ExpressCard 2 is max 4Gbps
										- Thunderbolt 3 is max 32Gbps (with 4 lane PCI)
								- [Switching GPU between Windows guest and Linux host without restarting xorg](https://www.youtube.com/watch?v=ssfvpLXK8po)
								- _Assorted_
								  collapsed:: true
									- [Reddit - Dive into anything](https://www.reddit.com/r/eGPU/comments/5jpf2x/diy_egpu_101_introduction_to_egpu/)
									- https://egpu.io/build-guides/
									-
									- http://forum.notebookreview.com/threads/diy-egpu-experiences.418851/
									- Intel preferred for [Qubes](https://workflowy.com/#/e3b3f652ed7d)
									  https://www.qubes-os.org/doc/system-requirements/
									- Reported to be loud and costly
									  http://appleinsider.com/articles/16/12/01/the-thunderbolt-3-equipped-macbook-pro-can-use-external-gpus----but-at-a-cost
								- Choosing to run apps via eGPU
									- If you have switcheroo-control installed (you should if you use Fedora KDE), you can enable discrete graphics by going in Edit App -> Application -> Advanced Options
								- ## OcuLink
								  id:: 67c18f4c-711a-4b40-b1f1-8518f5d63f87
								  collapsed:: true
									- Pros/Cons
										- Pros
											- Equivalent to ((67c1ad55-6362-4335-9375-3811a8f7efb8)) speed
											- It's cheaper than Thunderbolt
											- [It's much closer to native speeds](https://youtu.be/fPOgv63Yvx8) (5-20% FPS loss) than ((67ca30ab-afb2-49e5-9797-06d60905fed8)) (25-50% loss) using a high-end GPU (RTX 4090)
										- Cons
											- Limited cable length before performance affected, 60cm?
											- It's got low durability for insertions, unlike USB
											- Only transfers data, not power like USB
											- Doesn't support hotplugging
										- Unclear
										- Comparisons
											- ((67c1ad55-6362-4335-9375-3811a8f7efb8))
									- [The Best Connector You’ve Never Heard Of: OCuLink - YouTube](https://www.youtube.com/watch?v=xqXpBUNqkKs)
										- Fun Fact some VR Headsets like the Valve Index use the OCuLink connector for their main cable harness.
										- 1:55 Oculink is just a pci-e x4 slot in a different form factor, just like M.2 or U.2.
										- newer ((63ad9565-9f04-447d-b3c2-7541d47f2703)) - [it's based on the M.2 slot](https://community.frame.work/t/oculink-expansion-bay-module/31898). [Better than TB4](https://egpu.io/forums/custom-egpu-chassis/oculink-what-it-is-why-you-need-it-and-where-to-get-it/)
										- M.2 to OcuLink adapters are commonly used since OcuLink ports are non existent on laptops
										- 5-20% better FPS in videogames
									- [eGPU | Thunderbolt vs Oculink. Everything you need to know. - YouTube](https://www.youtube.com/watch?v=fPOgv63Yvx8)
									- [External GPUs Kinda Suck (But This One Doesn't) - YouTube](https://www.youtube.com/watch?v=wsmFcbWMCDU&t=928) cheap $200 OcuLink dock. Also some devices with OcuLink ports
									- 1
										- in the context of AMD’s laptop CPUs in high-end laptops like the FWL16 there’s an additional hurdle: PCIe lanes
										- PCIe lanes are the extremely fast connections between the CPU and other system components (such as discrete Thunderbolt controllers). Each discrete Thunderbolt controller needs 4 PCIe lanes. The current Framework Laptop 16 uses 17 PCIe lanes (8 for the Expansion Bay, 4 for the Primary SSD, 4 for the Secondary SSD, and 1 for the Wi-Fi card).
										- However AMD’s new Ryzen AI 300 series CPUs have only 16 PCIe lanes (4 fewer than last gen), so the PCIe lane count is already going to be a problem for Framework to deal with even without a discrete Thunderbolt 5 controller.
										- Intel’s CPUs support 28 PCIe lanes, so they could more easily have a Thunderbolt 5 controller added.
										- Regardless I expect that the next generation of CPUs from Intel and AMD (which are still a ways away) will have integrated USB4 80 Gbps controllers (Thunderbolt 5 is an Intel certification and brand name for USB4 80 Gbps ports that meet certain requirements). So eventually that will be the solution.
									- # Products
										- ## Enclosures
										  id:: 67c1a5ab-3c9d-4e4e-a7ec-595b58a17d07
											- $100 Minisforum DEG1
											- ### With embedded GPU
												- GPD G1
													- Thunderbolt 4 and OcuLink support
													- Uses AMD Radeon RX 7600M XT discrete GPU
													- [The New GPD G1 Is A Fast Compact eGPU, Oculink & USB! Hands-On First Look - YouTube](https://youtu.be/KuKKc66wrsc)
										- ## PCs with OcuLink ports
										  id:: 67c1a547-3127-4edc-92a7-6a4fc19ac5c2
											- GPD Win Max 2
											- GPD Win4
								- Related: ((65a98a50-4b22-48ab-9b4d-7dbcb54d56c2))
							- # By model
								- ### PCI
									- Thinkpad T430
									  collapsed:: true
										- https://egpu.io/forums/builds/lenovo-thinkpad-x230-t430-gtx-1050-ti-exp-gdc-beast-v8-via-expresscard-no-external-monitor/
										- Run "msinfo32" and check BIOS version. Looking for
									- [EXP GDC dock](https://www.amazon.co.uk/gp/product/B073YQHQMP)
									  collapsed:: true
										- How to connect
										  https://www.youtube.com/watch?v=FSY8huiYGhc
								- ### Thunderbolt 3
									- ((65a98a50-fb13-418e-adad-222f5fdccf04))
								- ### ((67c1ad55-6362-4335-9375-3811a8f7efb8)) support
								  id:: 67ca0d84-8c6a-496a-9230-43c580158d3b
									- [Asus ROG XG Mobile (2025)](https://go.skimresources.com?id=111346X1569483&xs=1&url=https://rog.asus.com/external-graphic-docks/rog-xg-mobile-2025/&xcust=2-1-2570787-1-0-0-0-0&sref=https://www.pcworld.com/article/2570787/why-asus-world-first-thunderbolt-5-egpu-is-on-my-gamer-wishlist.html)
								- ### ((67c18f4c-711a-4b40-b1f1-8518f5d63f87))-based
									-
							- Related: ((632093dc-ef96-4d8d-84df-aead8451b7df))
						- GPU-over-IP
						  collapsed:: true
						  AKA GPU-over-network
							- ## Solutions
								- Proprietary
									- [Thunder Compute](https://www.thundercompute.com/)
									  Hosted in AWS ECS instances
									- [Juice](https://www.juicelabs.co/)
								- FOSS
									- [GitHub - steelbrain/ffmpeg-over-ip: Connect to remote ffmpeg servers](https://github.com/steelbrain/ffmpeg-over-ip)
									- [GitHub - Juice-Labs/Juice-Labs: Juice Community Version Public Release](https://github.com/Juice-Labs/Juice-Labs)
										- with the whole project going commercial and the community edition being neglected I no longer have any interest in trying to support the project either.
										- the free community version has been discontinued, and also doesn't support a linux client with non-CUDA graphics, regardless of the server OS, which is a non-starter for me
							- ## Usecases
								- Transcoding videos
								- Encoding video
								- Games (should be better performance than GFN/Parsec streaming as the disk/CPU/RAM is local, only GPU is remote)
							- Related:
								- USB-over-IP
								  AKA USB-over-network
									- [USB-over-network](https://usbip.sourceforge.net/)
									- [VirtualHere: Allows USB devices to be used remotely over a network just as if they were | AlternativeTo](https://alternativeto.net/software/virtualhere/about/)
									-
					- RAM
					  collapsed:: true
						- Mixed RAM
						  collapsed:: true
							- It will move to the clock speed (MHz) of lowest chip.
							  collapsed:: true
							  https://www.howtogeek.com/217849/can-i-use-two-types-of-ddr3-ram-with-the-same-motherboard/
								- Clock speed is in MegaHertz and it is the number of millions of signal changes in a second
							- Check what clock speed is supported by the processor
							  https://support.lenovo.com/gb/en/solutions/pd024705
							- Check if DDR3 or DDR4 is supported by the motherboard. DDR3 RAM uses a 240-pin connector, while DDR4 RAM uses a 288-pin connector.
							- DDR3L RAM
							  collapsed:: true
								- This RAM has the same pins and works with any CPU and motherboard that works with DDR3 RAM. The difference? DDR3L RAM can function at both 1.5V and 1.35V, while DDR3 RAM is stuck at 1.5V.
								- Low voltage
							- A SO-DIMM, SODIMM
							  collapsed:: true
								- , or small outline dual in-line memory module, is a type of computer memory built using integrated circuits. SO-DIMMs are a smaller alternative to a DIMM, being roughly half the size of regular DIMMs.
						- ECC RAM - workstations also commonly rely on ECC RAM which improves system/program stability and prevents data corruption.
					- ### Hard Drive-related
					  id:: 66dc4604-c123-4908-8523-bce827e62c85
					  collapsed:: true
						- See ((66dc3a15-d559-4cec-9a56-c5e165c12b36)) for speeds
						- Hard Drives
						  id:: 68530668-9ed9-4cd9-8598-5386a197ae56
							- SATA III = 6.0 Gigabit/s
							  collapsed:: true
								- Samsung EVO
									- Test shows 280/240Mbps read/write speeds
									  https://www.amazon.co.uk/Samsung-MZ-76E500B-EU-Solid-State/dp/B078WQT6S6
							- HDD / Hard drive
							- Solid State Drives (SSDs)
							  id:: 65a98a50-4b22-48ab-9b4d-7dbcb54d56c2
								- SATA-based M.2 B key SSD - similar speeds to SATA III SSD
								  collapsed:: true
									- Samsung 860 EVO M.2
									  https://www.amazon.co.uk/Samsung-Sata-Solid-State-Drive/dp/B078WQVX9B
									- Enclosure - to USB A 3.1
									  https://www.amazon.co.uk/Enclosure-6amLifestyle-Thunderbolt-Compatible-External-USB-3-1-Black/dp/B07HCP8N1Y
								- _Next Gen_
									- NVMe capable M.2 SSDs
									  collapsed:: true
										- PCI-E (PCI-Express)-based M key SSD
										  http://i.imgur.com/BjOu0eu.png slightly diffrent from SATA-based B key
											- _SSDs_
												- Samsung EVO M.2 - sequential read/write speeds of 3,500/2,500 MB/s
												  source:: https://www.amazon.co.uk/Samsung-V-NAND-Express-Solid-State/dp/B07CGGP7SV
											- _Enclosures with USB 3.1 gen 2_
												- £29 - Showed 800Mbps R in a test
												  https://www.amazon.co.uk/XT-XINTE-USB3-1-Enclosure-External-Mobile/dp/B07FR58Z78
												- £43 - 1Gbps R/W according to manufacturer
												  https://www.amazon.co.uk/USB-NVMe-PCIe-Enclosure-PCI-M-2/dp/B07GPB1VR4
								- SOPs
							- HDD/SSD
								- £85 3TB 3.5" HDD
								  [WD Blue 3TB Desktop Hard Disk Drive - 5400 RPM SATA 6 Gb/s 64MB Cache 3.5 Inch : Amazon.co.uk: Computers & Accessories](https://www.amazon.co.uk/Blue-Desktop-Hard-Disk-Drive/dp/B013HNYV42)
								- £120 3TB 2.5" HDD
								  https://www.amazon.co.uk/Seagate-BarraCuda-Internal-Drive-Factor/dp/B01M09TPP4?th=1
								- (since I already have a spare SSD)
								- £275 2TB 2.5" SSD
								  [Crucial MX500 2TB CT2000MX500SSD1(Z)-Up to 560 MB/s, 3D NAND, SATA, 2.5 Inch, Internal SSD, Metallique, Solid State Drive : Amazon.co.uk: Computers & Accessories](https://www.amazon.co.uk/Crucial-MX500-CT2000MX500SSD1-Internal-NAND/dp/B078C515QL)
							- Related: ((685305e7-008e-475c-b967-96620fdca87a))
						- Enclosures
							- Priority
								- [[2024-09-07 Saturday]] Buy an enclosure with ((66dc3a28-a343-4d6f-957d-fc6e44bde72f))-speed USB connection so I can pair it with my second Framework mainboard. Use this as a Jellyfin server, backup location for Vorta (and possibly direct sync), and general storage server
								  collapsed:: true
									- Top choices
										- £600 [Terramaster D5 Thunderbolt 3, 5-bay](https://www.amazon.co.uk/gp/product/B07BLM72ZY) - supports RAID 5 thanks for having 3+ bays
										- £290 [Terramaster TD2 Thunderbolt 3 Plus, 2-bay](https://www.amazon.co.uk/gp/product/B08D3GDKVF) - supports RAID0 and RAID1 notably
							- ((649b12e2-23a5-4704-bdf7-adc0cfce894d))
							- Direct Attached Storage (DAS)
							  id:: 68239af8-a17b-4f34-9f7c-0704d41b2dc4
							- RAID
								- **JBOD**: Max storage, no redundancy or speed boost. 
								  AKA Just a Bunch Of Disks
								- **RAID 0**: Higher read/write speed, no redundancy.
								  AKA Striping
								- **RAID 1**: Redundancy, no speed boost.
								  AKA Mirroring
						- Related: ((63ad9565-9f04-447d-b3c2-7541d47f2703)) speeds
					- PSU
					- Ports
					  collapsed:: true
						- USB
						  collapsed:: true
							- [Version history](https://en.wikipedia.org/wiki/USB#Version_history)
								- [USB4](https://en.wikipedia.org/wiki/USB#USB4) (2019)
								  id:: 67ca35de-f7b7-404f-99aa-8b90086a58c3
									- Based on ((67ca17fc-6cb7-4a7a-9fb0-47cb2c868918)), however it's minimum specs are lower (i.e. more optional features)
									- Max rate: 40 Gbit/s
									- Optional components galore
										- 10 or 20 Gbit/s minimum mandatory
									- [USB4 is a Glorious Mess - YouTube](https://youtu.be/C6aCCp-Umcw)
										-
								- USB4 2.0 (2022)
								  id:: 68239af8-0da4-4f03-8644-f091eb5e693b
									- Max rate: 120 <-> 40 Gbit/s: asymmetric
						- Thunderbolt
						  collapsed:: true
							- Thunderbolt 3
							  id:: 67ca17fc-6cb7-4a7a-9fb0-47cb2c868918
								- Max bandwidth: 40 Gbps
								- Minimum bandwidth: 16 Gbps
								- Related: ((67ca35de-f7b7-404f-99aa-8b90086a58c3))
							- Thunderbolt 4
							  id:: 67ca30ab-afb2-49e5-9797-06d60905fed8
								- Max bandwidth: 40 Gbps
								- Minimum bandwidth: 32 Gbps
									- 4 PCIe lines 3.0 (4x8 Gbps)
								- Comparisons
									- [How much performance do we lose by connecting an eGPU with a Thunderbolt port? RTX 4090 - YouTube](https://youtu.be/R6v18s3EyD0)
										- ((67ca30ab-afb2-49e5-9797-06d60905fed8)) tests
										- 100% better FPS when using RTX 4090 natively rather than via eGPU (TB4)
										- 10-30% better FPSwhen using RTX 2060
										- Image generation is maybe 70% faster when connecting GPU via PCIe (native) rather than eGPU
									- [Thunderbolt eGPU bandwidth limit explained | RTX 4090 + 13700H - YouTube](https://youtu.be/_UE_2NyaAas)
										- Every mainstream ((63ad9565-9f04-447d-b3c2-7541d47f2703)) supports TB3 not TB4
							- Thunderbolt 5
							  id:: 67c1ad55-6362-4335-9375-3811a8f7efb8
								- Meta
									- essentially the 80Gbps version of the industry-standard ((68239af8-0da4-4f03-8644-f091eb5e693b)) (which is being branded as just “USB 80Gbps”
									- Bit better than USB4 v2 (can reach 120Gb/s rather than 80Gb/s)O
									- Only equivalent to 4 lanes, rather than 16 for native GPU slots in desktops?
									- PCIe 5.0 x16 has a [bandwidth of 63GB/s](https://en.wikipedia.org/wiki/PCI_Express#Comparison_table)
									- ((65a98a50-fb13-418e-adad-222f5fdccf04))
								- ((63ad9565-9f04-447d-b3c2-7541d47f2703)) : ((67ca0d84-8c6a-496a-9230-43c580158d3b))
								- Laptops
									- Razer Blade 18
						- PCIe
						  id:: 67ca2ecf-7c79-4c0f-9d6a-50cf78f16bb8
						  collapsed:: true
							- Lanes
								- x16 - typically amount for the graphics card slot on desktop motherboards
							- Versions
								- [Comparison table](https://en.wikipedia.org/wiki/PCI_Express#Comparison_table)
								- 4.0
								  id:: 67ca2f62-7172-4c71-bc14-6418c0e76b9a
									- 8 GB/s with x4
									- 32 GB/s with x16
									  id:: b0a5a138-a3ee-4e12-802c-03a48a4034d2
								- 5.0
									- 16 GB/s with x4
									- 64 GB/s with x16
							- My hardware
								- ((675b54e8-8525-4506-aa10-a82779f66332))
									- {{embed ((67ca2ea8-f65a-45a9-8171-a61f4205d402))}}
						- ((67c18f4c-711a-4b40-b1f1-8518f5d63f87))
					- Physical security
					  collapsed:: true
						- Box around case with padlocks
					- Related:
						- ((6341c07c-00cf-4e45-9336-ebbcdbf8e71f)) : ((68398a10-f739-431c-a8bd-48836c30b1d0))
						- ((67cc4886-1a9a-4554-afd3-a31c450845db))
				- ## Builds
					- [[2025-03-06 Thursday]]
						- GPU: ((675b54e8-8525-4506-aa10-a82779f66332))
					- Recommended Builds
					  collapsed:: true
						- £1.5k [Magnificent AMD Gaming/Streaming Build](https://uk.pcpartpicker.com/guide/377Ycf/magnificent-amd-gamingstreaming-build)
						  id:: 6856963c-61ac-4ddf-a1b5-93841d8d7f5b
						  collapsed:: true
							- One tier below £3.5k "Glorious" version
							- [[2025-06-21 Saturday]] [My customised version](https://uk.pcpartpicker.com/list/) £1.7k gaming/workstation
							  id:: 685696dd-7e04-42d1-ba07-c06d6a16574e
								- £1216 in new components
									- CPU: £346 [AMD Ryzen 7 7800X3D](https://www.amazon.co.uk/dp/B0BTZB7F88?tag=pcp0f-21)
									- CPU Cooler: £55 [Thermalright Phantom Spirit 120 EVO](https://www.amazon.co.uk/dp/B0CL96CDDB?tag=pcp0f-21#averageCustomerReviewsAnchor)
									- Motherboard: £127 [GIGABYTE B650 EAGLE](https://www.amazon.co.uk/dp/B0DBM78F2D?tag=pcp0f-21)
									- Memory: £153 [2x 32GB DDR5 6000MT/s RAM](https://www.amazon.co.uk/dp/B0D4NLY7ZY?tag=pcp0f-21)
									  collapsed:: true
										- Patriot Viper Venom DDR5 64GB (2 x 32GB) 6000MT/s UDIMM Desktop Gaming Memory KIT - PVV564G600C30K
									- Storage: £223 [4TB M.2 NVMe SSD](https://www.amazon.co.uk/dp/B0CCNCW5QX)
									  collapsed:: true
										- Crucial P3 Plus SSD 4TB M.2 NVMe PCIe Gen4 Internal SSD, Up to 4800MB/s, Laptop & Desktop (PC) Compatible, Solid State Drive - CT4000P3PSSD801
									- Case: £95 [Corsair 4000D Airflow Mid-Tower ATX Case](https://www.amazon.co.uk/dp/B08C7BGV3D)
									  collapsed:: true
										- Corsair 4000D AIRFLOW Tempered Glass Mid-Tower ATX Case - High-Airflow - Cable Management System - Spacious Interior - Two Included 120 mm Fans - Black
									- Power Supply: £132 [be quiet! Pure Power 12 M 1000W](https://www.amazon.co.uk/dp/B0BT3BHDN7?tag=pcp0f-21)
									- Wireless Network Adapter: £85 [TP-Link Archer TBE550E WiFi 7 Card BE9300](https://www.amazon.co.uk/dp/B0CYVNSDKX?tag=pcp0f-21)
									- [[2025-06-21 Saturday]] Waiting some days to order so they all arrive on Friday
								- + my ((675b54e8-8525-4506-aa10-a82779f66332))
								- Related: ((685fd245-1e57-4b7c-bae0-cb0acfdbb987))
						- [Mid-range all-rounder build](https://uk.pcpartpicker.com/guide/CGzKHx/excellent-amd-gaming-build) (home server / gaming / programming workstation)
						  id:: 68239af8-eec3-49f2-a0f4-108b5d0fb05f
						  collapsed:: true
							- CPU
								- £196 Ryzen 5 2600X CPU (or get the 3000 series with AM4 socket, up to 2020 support)
								  [AMD YD260XBCAFBOX Ryzen 5 2600X Processor with Wraith Spire Cooler : Amazon.co.uk: Computers & Accessories](https://www.amazon.co.uk/dp/B07B428V2L/?tag=pcp0f-21)
								- £330 2700X
							- £130 16GB DDR4 RAM 3000Mhz
							  https://www.amazon.co.uk/Corsair-159405-Vengeance-Performance-Desktop/dp/B0134EW7G8/ref=sr_1_1?ie=UTF8&qid=1544600846&sr=8-1&keywords=ddr4%2B16gb%2Bx%2B1%2B3000mhz&th=1
							- £170 ASUS X470 motherboard
							  https://www.amazon.co.uk/ASUS-X470-PRIME-X470-PRO-Motherboard-x/dp/B07C64R1TW/ref=sr_1_1?s=computers&ie=UTF8&qid=1544603507&sr=1-1&keywords=Asus+X470-Pro
							- £120 3TB 2.5" hard drive (since I already have a spare SSD)
							  https://www.amazon.co.uk/Seagate-BarraCuda-Internal-Drive-Factor/dp/B01M09TPP4?th=1
							- Power supply
							- Case
						- Xeon Server Build
						  collapsed:: true
							- https://www.techspot.com/review/1155-affordable-dual-xeon-pc/
							- Xeon Server Build
							  collapsed:: true
							  Dual Xeon E5-2670 https://www.techspot.com/review/1155-affordable-dual-xeon-pc/
								- unRAID OS I've seen recommended a few times
								  collapsed:: true
									- Unraid makes for easy HDD/SSD drive swaps too
									- or just use ZFS
								- https://uk.pcpartpicker.com/b/T3LD4D
								- https://uk.pcpartpicker.com/b/cjPscf
								- https://uk.pcpartpicker.com/b/9mP323
								- https://uk.pcpartpicker.com/b/pVnH99
								- https://uk.pcpartpicker.com/b/VK3bt6
								- https://uk.pcpartpicker.com/list/4pdjvV
								- https://uk.pcpartpicker.com/b/Vnm8TW
								- https://uk.pcpartpicker.com/b/8YNQzy
								- https://uk.pcpartpicker.com/b/kMbXsY
								- https://uk.pcpartpicker.com/b/GBq48d
								- Intel - Xeon E5-2670 2.6GHz 8-Core Processor
								  collapsed:: true
								  x2
									- When purchasing your Xeon E5-2670 processors online, make sure you get the C2 (SR0KX) stepping chips, especially since they don’t currently cost more than the C1 chips. Apparently, the C1 (SR0H8) doesn’t support VT-d (Intel Virtualization Technology for Directed I/O), whereas this is fixed with the C2 stepping, and this might be important for virtualization pass-through. If you ever plan to resell the Xeon chips down the track, the C2 models will likely fetch a better price as well.
									- Intel E5-2670 SR0KX
									  https://www.ebay.co.uk/sch/i.html?_from=R40&_trksid=p2380057.m570.l1313.TR0.TRC0.H0.XIntel+E5-2670+SR0KX.TRS0&_nkw=Intel+E5-2670+SR0KX&_sacat=0
							- DIY Xeon build costs
							  collapsed:: true
							  Xeon E5-2670
								- £300 motherboard
								  http://amzn.eu/d2L2HZP
								- £230 CPU -  for dual Xeon E5-2670 CPU (£115*2) SR0KX
								  collapsed:: true
								  https://www.ebay.co.uk/sch/i.html?_from=R40&_trksid=p2380057.m570.l1313.TR0.TRC0.H0.XIntel+E5-2670+SR0KX.TRS0&_nkw=Intel+E5-2670+SR0KX&_sacat=0
									- £248
									  https://m.ebay.co.uk/itm/Matched-Pair-Intel-E5-2670-2-6GHz-8GT-s-8-Core-20MB-Cache-SR0KX-CPU-Processor/142346418117?epid=16007667980&thm=1
									-
								- £112+ RAM (16GB)
								  collapsed:: true
								  Supports Quad Channel DDR3 1600 memory, 16 DIMM slots, Max. 512GB
									- £112 for 8GB*2
									  https://www.amazon.co.uk/gp/aw/d/B00EH1H86C/ref=ya_aw_od_pi?ie=UTF8&psc=1
									- for 32GB
								- £286 SSD
								  collapsed:: true
									- £286 Samsung 850 EVO 1 TB 2.5 inch Solid State Drive
									  https://www.amazon.co.uk/gp/aw/d/B00P738MUU/ref=mp_s_a_1_1?ie=UTF8&qid=1510033869&sr=8-1&pi=AC_SX236_SY340_QL65&keywords=tb+ssd&dpPl=1&dpID=41fw65-8tpL&ref=plSrch
									- £590 2TB
									- 2.5-3.5-Inch SSD/HDD Adapter
									  http://amzn.to/2Aq1BGD
								- £116 CPU coolers
								  collapsed:: true
									- 2x Noctua NH-U12DX i4 coolers ?
									  £58 each https://www.amazon.co.uk/gp/aw/d/B00DWFQ42I/ref=mp_s_a_1_1?ie=UTF8&qid=1510034173&sr=8-1&pi=AC_SX236_SY340_QL65&keywords=Noctua+NH-U12DX+i4+cooler&dpPl=1&dpID=51l75Z9-nCL&ref=plSrch
								- £160 Power supply
								  collapsed:: true
									- Corsair RM Series RM100x power supply ?
									- £125-160
									  https://uk.pcpartpicker.com/product/MfJwrH/evga-power-supply-220g20750xr
								- UPS
								  collapsed:: true
									- What
									  collapsed:: true
										- An uninterruptible power supply, also uninterruptible power source, UPS or battery/flywheel backup, is an electrical apparatus that provides emergency power to a load when the input power source or mains power fails. A UPS differs from an auxiliary or emergency power system or standby generator in that it will provide near-instantaneous protection from input power interruptions, by supplying energy stored in batteries, supercapacitors, or flywheels. The on-battery runtime of most uninterruptible power sources is relatively short (only a few minutes) but sufficient to start a standby power source or properly shut down the protected equipment.
								- GPU
								  collapsed:: true
									- RM850x ?
								- £135 case
								  http://amzn.eu/60sK2Fs
							- How to put together
							  collapsed:: true
								- https://youtu.be/3u06K_qI9cM
								- https://www.youtube.com/watch?v=PnKdVm2wmZ8
								- https://www.youtube.com/watch?v=LeaXHp11uZ0
								- Case
								  collapsed:: true
									- https://www.computershopper.com/components/howto/install-your-pc-in-a-new-case
								- I can't post you tube links here but if you search for "budget dual xeon build" and look for a guy called "TechCity", he has videos covering the build and bios setup.
						- Raspberry Pi build
						  collapsed:: true
							- [https://thepihut.com/products/raspberry-pi-400?src=raspberrypi](https://thepihut.com/products/raspberry-pi-400?src=raspberrypi)
							- Raspberry Pi heatsink
							  [https://thepihut.com/products/aluminium-armour-heatsink-case-for-raspberry-pi-4](https://thepihut.com/products/aluminium-armour-heatsink-case-for-raspberry-pi-4)
							- [Pi-Top [4] DIY Edition](https://shop.pi-top.com/products/pi-top-4-diy-edition)
							  Basically a case with a few programmable buttons and a battery
					- Battlestations screenshots
						- H
						- [How do we like this set up? - r/battlestations](https://snoo.habedieeh.re/r/battlestations/comments/1f9sjpw/how_do_we_like_this_set_up/)
						  collapsed:: true
							- ![image.png](../assets/image_1748626257238_0.png)
					- How to
						- [How to Build a PC - Full Detailed Build Guide (2025) - YouTube](https://youtu.be/Mho0M1Ns0Rw)
						  id:: 685fd245-1e57-4b7c-bae0-cb0acfdbb987
							- CPU - different guide for each type of socket
							- RAM - use A2 and B2 slots
			- Home Server 
			  id:: 6341c07c-00cf-4e45-9336-ebbcdbf8e71f
			  collapsed:: true
			  AKA [Home Lab](https://www.reddit.com/r/homelab) | Expensive, time-consuming option
				- Pros/Cons
					- Pros
						-
					- Cons
						-
					- Unclear
					- Comparisons
						- ((64e09473-3ef7-4569-acf7-3aac013f6c86))
				- # Components
				  id:: 68398a10-f739-431c-a8bd-48836c30b1d0
					- Meta
						- Note: server motherboards are different from desktop ones in terms of the position/angle of slots, to ensure airflow
					- Rack unit
						- In server racks, "U" stands for rack units, which is a standardized measurement used to determine the height and capacity of equipment that can be installed within a server rack. One rack unit (1U) is equivalent to 1.75 inches (44.45 mm) in height
					- Patch panel
					  collapsed:: true
					  i.e. connect cables to other components
						- The 3rd from top is a patch panel. This just lets you run cabling from other places (e.g. wall outlets in other rooms) into sockets inside the rack cabinet. Then you can connect a network cable from that socket to anything else in the rack very easily (e.g. the server).
					- Managed switch
					  collapsed:: true
					  i.e. network between servers or to WAN
						- The next one down (Netgear) is a managed switch. It connects computer equipment to each other so they can communicate (e.g. so the server can talk to the internet, or so a desktop can talk to the server etc).
					- Server
					  collapsed:: true
						- The top unit (Dell PowerEdge) is a server, which can be used to run just about any thing (e.g. storing files, running game servers, websites, even could be setup as a router).
					- UPS
					  collapsed:: true
					  i.e. emergency power battery
						- Sitting on the bottom is a UPS unit (Cyber power). It is basically a battery that will power things for a short time when the mains power goes out. Usually can also clean up power and provide some protection to the equipment it is plugged into.
					- Related: ((68397b4b-5d27-45a7-a60f-957146bf35ac)) : ((67cc4886-06b2-4997-add7-26eb6fefcf23))
				- # Builds
					- [Compact Homelab - r/homelab](https://snoo.habedieeh.re/r/homelab/comments/1jz92a7/compact_homelab/)
						- [Downsizing my 3U Gaming build to 2U](https://blog.seattlebubbles.com/downsizing-my-3u-gaming-build-to-2u/)
							- [Toolless Mini Rack - Ubiquiti Store](https://store.ui.com/us/en/products/toolless-mini-rack)
							-
				- # Unsorted
					- Or full high power desktop
						- Easier admin
					- Multiple Raspberry Pis?
					- Desktop PC
					  collapsed:: true
					  Getting the right balance of performance, space, power consumption and noise is expensive - get a proper server when I'm travelling
						- Uses up more power than NAS but has better CPU for transcoding (needed for streaming via Plex) and needed for streaming encrypted data
						- Guides
							- PC Master Race graphic
							  https://pf.reddit.com/r/pcmasterrace/comments/4fsfo4/tldr_from_0_to_pcmr/
						- _Amazon _
							- Desktop tower
							  collapsed:: true
								- £80 250gb 2.5ghz duo
								  http://www.amazon.co.uk/gp/aw/d/B00HABDK40/ref=mp_s_a_1_1?qid=1452242527&sr=8-1&pi=SX200_QL40&keywords=i3+desktop&dpPl=1&dpID=51QsgEYnP7L&ref=plSrch
								- £260 i3 500gb 4gb
								  http://www.amazon.co.uk/gp/aw/d/B00R0GPTDK/ref=mp_s_a_1_2?qid=1452243006&sr=8-2&pi=AC_SX220_SY330_FMwebp_QL65&keywords=i3+desktop
							- Compact, barebones (quiet but limited hard drive space and expensive)
							  collapsed:: true
								- £200 compact, silent i3
								  http://www.amazon.co.uk/gp/aw/d/B0093LINVK/ref=pd_aw_sbs_147_20?ie=UTF8&dpID=41dNeuCuU5L&dpSrc=sims&preST=_AC_UL115_SR115%2C115_&refRID=0D803VF73EGTCN7HC5Z2
								- £180 compact, bare bones i3
								  http://www.amazon.co.uk/gp/aw/d/B00GK9WMD8/ref=mp_s_a_1_1?qid=1452243873&sr=8-1&pi=SY200_QL40&keywords=i3+barebones&dpPl=1&dpID=51U3wDgssZL&ref=plSrch
							- Mobile processor quieter as geared for lower power consumption, though CPU slower
					- Network Attached Storage (NAS)
					  id:: 649b12e2-23a5-4704-bdf7-adc0cfce894d
					  collapsed:: true
						- Pros/Cons
							- Pros
								-
							- Cons
								-
							- Unclear
							- Upstream/Downstream Pros/Cons
							- Comparisons
								- ((649b12e2-23a5-4704-bdf7-adc0cfce894d)) vs ((6341c07c-00cf-4e45-9336-ebbcdbf8e71f)) / ((68239af8-a17b-4f34-9f7c-0704d41b2dc4))
								  id:: 64e09473-3ef7-4569-acf7-3aac013f6c86
								  collapsed:: true
									- For ((6341c07c-00cf-4e45-9336-ebbcdbf8e71f)) / ((68239af8-a17b-4f34-9f7c-0704d41b2dc4))
										- Functional disk encryption
										- It's a big security risk having data in an unencrypted NAS, even if it is physically locked due to UK laws
										- Allows fast HD video playback
										- Allows client-side encryption so that even live USB attacks whilst TrueCrypt is open won't compromise data
										- Deniable encryption
									- For ((649b12e2-23a5-4704-bdf7-adc0cfce894d))
										- Cheaper
										- Quicker setup
									- Similarities
										-
									- Unclear
										-
						- Software
							- Operating Systems
								- TrueNAS
								  AKA formerly FreeNAS
									- Built on ((65f9fe65-1678-4356-bff0-e42d05cfe235))
								- OpenMediaVault
									- Built on ((65a98a51-38a0-4772-9fbb-0fffadc84dfd))
						- Encryption
						  collapsed:: true
							- Software encryption not possible with NAS, use hardware eg Synology or QNAP
							  collapsed:: true
								- But NAS have shit CPU - encrypted NAS will be too slow for backups or playback
								- NAS encryption unsuitable - use desktop or just file containers
							- Encryption isn't a must-have for home setup if I'm using rsync+truecrypt containers like I will with VPS - though that means I can't stream files, which was another proposed function of local server
							- Streaming requires decryption
							  collapsed:: true
								- PC for example would be left on user locked at best whilst not in use to perform backups
								- During use is susceptible to physical access attacks
								  collapsed:: true
									- Unless I use surveillance cameras and a lockbox around case
						- Products
							- _Owned_
								- WD MyCloud 2TB
								  collapsed:: true
									- Documentation
									  #SysAdmin https://workflowy.com/#/d660d0c44a91
									- £95 WD MyCloud 2TB (unencrypted)
									  collapsed:: true
									  http://www.amazon.co.uk/WD-Cloud-Personal-Storage-NAS/dp/B00FOKN7FG/ref=sr_1_1?ie=UTF8&qid=1452640819&sr=8-1&keywords=wd+mycloud
										- look at how easy it would be to setup an rsync backup or restore files
										-
							- GnuBee Personal Cloud (FLOSS, accepts 2.5 or 3.5" drives)
							  https://www.crowdsupply.com/gnubee/personal-cloud-1#products-top
							- Synology
							  collapsed:: true
								- Software
									- [What I run on my NAS / Home Server - YouTube](https://youtu.be/DekUrSZ58fc)
									-
								- [Best at different price points](https://youtu.be/pbzi3r0chv0)
									- DS120J
									- DS223J
									- [DS423](https://www.amazon.co.uk/Synology-DS423-4-Bay-Diskstation/dp/B0BXH389D1)
										- Supports RAM upgrades
										- Can use NVMe drives
									- £550 [DS923+](https://www.amazon.co.uk/Synology-4-Bay-DiskStation-DS923-Diskless/dp/B0BM7KDN6R)
									- £700 [DS1522+](https://www.amazon.co.uk/Synology-DS1522-5-Bay-Desktop-Solution/dp/B0B2RN4SJT/)
										- Can be upgraded to 10GB networking
										- 8GB RAM
										- Great for businesses and hardcore homelabbers
									- DS1821+
								- {Archive}
									- (£165) £80 Synology + £85 3Tb (pointless unless storage space:cost beats WD MyCloud)
									  collapsed:: true
									  [Page Not Found](http://www.amazon.co.uk/gp/aw/d/B00MO6ZV52/ref=mp_s_a_1_3?qid=1452240569&sr=8-3&pi=SY200_QL40&keywords=synology&dpPl=1&dpID=31OvlWuxecL&ref=plSrch)
										- See if Plex is available through package manager (yes)
										  https://www.synology.com/en-global/dsm/app_packages/Plex_Media_Server
										- Encrypted NAS is unsuitable - poor performance for video playback and backup speed
											- Compatibility list
												- https://support.plex.tv/hc/en-us/articles/201373823-NAS-Devices-and-Limitations
												- https://docs.google.com/spreadsheets/d/1MfYoJkiwSqCXg8cm5-Ac4oOLPRtCkgUxU0jdj3tmMPc/edit?pref=2&pli=1#gid=314388488
												- Can play audio but not video
												- £500 QNAP can play video, but better off just using a desktop PC instead at that pricepoint
											- Encryption kills video playback and backup speed
												- Example performance test
												  http://www.tomshardware.com/reviews/nas-encryption-aes-ni,2873-6.html
										- Synology allows mounted folders, looks suitable
										  https://www.synology.com/en-global/knowledgebase/tutorials/455
						- Related: ((66dc4604-c123-4908-8523-bce827e62c85))
					- How to
						- Start with a Virtual Private Server, then later move to On-Premises/Home Server?
					- ((65a98a50-811c-4de7-8127-0919127fe8af))
					- Buying a prebuilt server
					  collapsed:: true
						- Xeon
							- Novatech - £1264.85
							  https://www.novatech.co.uk/server/range/towerservere5-2620v4.html
								- Motherboard has lots of room for expansion
								  https://www.asus.com/uk/Commercial-Servers-Workstations/Z10PAD8/overview/
									- Dual socket R3 (LGA 2011) supports Intel® Xeon® processor E5-2600 V4 family; QPI up to 9.6GT/s,
									- Intel® C612 chipset,
									- Up to 1TB ECC DDR4 2133MHz; 16x DIMM sockets,
									- 3 PCI-E 3.0 x16 and 3 PCI-E 3.0 x8,
									- Intel® i350 Dual port GbE LAN,
									- 10x SATA3 (6Gbps); RAID 0, 1, 5, 10,
									- Integrated IPMI 2.0 and KVM with Dedicated LAN
									- 5x USB 3.0 (2 rear, 2 via header, 1 Type A), 6x USB 2.0 (2 rear, 4 via header)
								- £1264.85
									- Intel Xeon E5-2620V4 8 Core 2.1GHz
									  can later get a second one. Comparable CPU to the dual V1 build
										- e.g. £412 (or £1630 not separately)
										  https://www.ebay.co.uk/itm/Intel-Xeon-E5-2620-v4-2-1GHz-Octa-Core-Socket-2011-v3-Processor/111988734595?epid=2254368360&hash=item1a130c7a83:g:NUAAAOSw44BYRWlP
									- 1TB HDD
									  WD Gold 1TB 3.5" Datacenter HDD (7200RPM | Sata 6Gb/s)
									- 8GB RAM (2133MHz DDR4 ECC RDIMM)
									  16 DIMM (RAM) slots, up to 32GB per slot
				- [Learning Resources]
					- [Home Lab Beginners guide](https://linuxblog.io/home-lab-beginners-guide-hardware/)
						- [Home Lab Beginners guide | Hacker News](https://news.ycombinator.com/item?id=39640992)
				- Related:
					- ((6839835e-0276-49b6-8d12-fc046f178a79)) (software side)
					- ((64e09473-ab06-46e2-a87a-30f78b49f407))
			- Entertainment System
			  collapsed:: true
				- Consider a Mac Mini as my home entertainment system [Fedora Asahi Remix - Asahi Linux](https://asahilinux.org/fedora/#device-support) once USB-C Displays and USB4 / Thunderbolt support added
				-
			- [[Overemployed]] : [hardware setup](((6737678e-81b5-4074-a58e-8150942dd8e3)))
			- [SimStation!](https://snoo.habedieeh.re/r/SimStation)
		- [Learning Resources]
			- [Log in | Tom's Hardware Forum](http://www.tomshardware.com/forum/forum-31.html)
		- Related:
			- ((6341c07c-00cf-4e45-9336-ebbcdbf8e71f))
			- ((65a98a50-076d-4e4a-8778-be27e0acdc17))
	- Benchmarking Hardware
	  collapsed:: true
		- Template
			- Examples
			  id:: 67cab004-8f25-4a3d-acb9-19e12d32c5ef
				- ((65a98a50-4b57-4816-931f-24253c6bc8b7)) : ((65a98a50-1909-412b-80ef-5acf9606884d))
				- ((659d093f-bf67-444a-b2a1-ec0a28907583)) : ((66705c8f-4f0c-41ba-8a41-e617c684b43d))
			- Specs TEMPLATE
				- _Hardware_
					- Model: Dell XPS 13 9380 (2019 model)
					- CPU: i7-8565U (8th gen)
						- [6135](https://www.cpubenchmark.net/cpu_lookup.php?cpu=Intel+Core+i7-8565U+%40+1.80GHz&id=3308)
						- [54.7%](https://cpu.userbenchmark.com/SpeedTest/591977/IntelR-CoreTM-i7-8565U-CPU---180GHz)
					- SSD: 512GB M.2 PCIe NVMe
					- RAM: 16GB LPDDR3 2133MHz
					- GPU: eGPU AMD Radeon 580
				- _Software_
					- Distro: Kubuntu 18.04 LTS
					- Kernel: 5.4
					- Runner: Lutris 4.20
					- DXVK version: DXVK 1.4.5
					- GPU Driver: 3.0 Mesa 19.1.2
					  `glxinfo | grep "OpenGL version"`
		- Benchmarking
			- Software
				- Cross-platform
					- [Phoronix Test Suite - Linux Testing & Benchmarking Platform, Automated Testing, Open-Source Benchmarking](http://www.phoronix-test-suite.com/)
					- [UNIGINE Benchmarks](http://unigine.com/en/products/benchmarks)
					- [Geekbench 6 - Cross-Platform Benchmark](https://www.geekbench.com/)
			- Publications
				- [PassMark](https://www.passmark.com/)
				  id:: 67caaf64-390f-4469-a55f-a66d630fcc87
					- [CPU Benchmarks](https://www.cpubenchmark.net/)
					  id:: 67caaf7b-8c0e-4988-856e-d843110c1177
					- [Video Card Benchmarks](https://www.videocardbenchmark.net/)
				- [UserBenchmark](https://www.userbenchmark.com)
				  id:: 67cab2ce-97ab-49e7-9f60-2e17788140b7
					- [CPU](https://cpu.userbenchmark.com/)
					  id:: 67cab2de-db8f-4c0a-b991-4b07cc88c424
					- [GPU](https://gpu.userbenchmark.com/)
	- Accessories
	  id:: 67cc4886-1a9a-4554-afd3-a31c450845db
		- Laptop charger
		  collapsed:: true
			- Laptop chargers
			  collapsed:: true
				- $90 laptop charger/USB charger/travel adapter (CARD Travel Adapter 4-Pro)
				  id:: 644c0a5f-4d80-4328-9e58-d7377584e0f6
				  [https://i.imgur.com/57UV87G.png](https://i.imgur.com/57UV87G.png)
					- [Amazon.com: CARD Travel Adapter 4-Pro (Type C+3 USB Ports) (White) : Electronics](https://www.amazon.com/gp/product/B078GP31S5?tag=tynan-20])
				- Omega GaN charger (tiny but can charge 2 laptops simultaneously)
				  [https://c1.iggcdn.com/indiegogo-media-prod-cld/image/upload/c_limit,w_695/v1602217250/kqidzw9ybohxrluttyq8.jpg](https://c1.iggcdn.com/indiegogo-media-prod-cld/image/upload/c_limit,w_695/v1602217250/kqidzw9ybohxrluttyq8.jpg)
					- [https://www.indiegogo.com/projects/omega-world-s-smallest-100w-200w-usb-c-charger#/](https://www.indiegogo.com/projects/omega-world-s-smallest-100w-200w-usb-c-charger#/)
			- FinSix Dart
			  https://www.amazon.co.uk/Smallest-Universal-Accessory-Lightweight-Portable/dp/B06W9LS9C5
		- RGB hardware
		  collapsed:: true
			- Unified Open Source RGB software.]([https://www.project-aurora.com/](https://www.project-aurora.com/))
		- Portable laptop monitors
		  id:: 644c0a5f-5470-4682-93e4-4c330782529b
		  collapsed:: true
			- [DUEX Plus](https://www.indiegogo.com/projects/duex-lite-duex-plus-portable-laptop-monitors) by [Mobile Pixels](https://www.mobilepixels.us/)
			  id:: 64e0946d-1d0e-4824-b150-1a08f26aba23
			  collapsed:: true
				- Phone needs ((63219e34-cda2-4a69-a2c8-b74b33cf9a91)) support to work
				-
			- TRIO
			  [https://www.indiegogo.com/projects/trio-portable-dual-triple-screen-laptop-monitor#/](https://www.indiegogo.com/projects/trio-portable-dual-triple-screen-laptop-monitor#/)
			- Vinpok Split
			  [https://www.indiegogo.com/projects/vinpok-split-best-on-the-go-touch-screen-monitor#/](https://www.indiegogo.com/projects/vinpok-split-best-on-the-go-touch-screen-monitor#/)
			- Sculptor
			  [[Sculptor: Auto-Rotating 4K Touchscreen Monitor | Indiegogo](https://www.indiegogo.com/projects/sculptor-auto-rotating-4k-touchscreen-monitor#/](https://www.indiegogo.com/projects/sculptor-auto-rotating-4k-touchscreen-monitor#/))
			- 349€ Slidenjoy twin monitors
			  [https://www.kickstarter.com/projects/slidenjoy/slidenjoy-double-or-triple-your-screens/rewards](https://www.kickstarter.com/projects/slidenjoy/slidenjoy-double-or-triple-your-screens/rewards)
			- https://www.rooshvforum.com/thread-63833.html
			- Related: ((644c0a60-93fe-4266-ba9a-7c772f08acd2))
		- USB cables
		  id:: 66dc3a15-d559-4cec-9a56-c5e165c12b36
		  collapsed:: true
			- Thunderbolt 3 (2015)
			  id:: 66dc3a28-a343-4d6f-957d-fc6e44bde72f
			  40 Gbps
			- Thunderbolt 4 (2020)
			  40 Gbps
			- USB 3.0 = 5.0 Gigabit/s
			- USB 3.1 Gen 1: 5 Gbps
			- USB 3.1 Gen 2: 10 Gbps
			- USB 3.2 Gen 2 x 2: 20 Gbps
			- USB 4 (using Thunderbolt 3 protocol): 40 Gbps
			- USB4 Version 2.0: 80 Gbps
		- Webcam
		  collapsed:: true
			- Meta
				- get a video capture card like an [Elgato Cam Link 4K](https://www.elgato.com/en/cam-link-4k) and connect a DSLR or mirrorless camera to it using HDMI.
				- [Why can’t you buy a good webcam? | Vsevolod Solovyov](https://vsevolod.net/good-webcams/)
				  collapsed:: true
					- Some people are not satisfied with a webcam from their notebook or an old webcam they bought many years ago.
					- My brother decided he wants to try streaming. Some people can just do a thing and other people want to research all the bits and pieces beforehand. Our chat history is comparable in length to all my other chats combined, so I learned a lot of it as well. The craft is full with small details and inconveniences.
					- He found that there are basically no good webcams. A lot of the time an image quality is meh, and the rare presence of 4k is usually not better than 1080p, because resolution is not quality. Some camera apparently does upscaling from 1080p to 4k in its driver, indicated by poor quality and high CPU load. He also has a really good camera, Fujifilm X-T1. It can't be used as a webcam when connected to a USB port. Usually it's possible to buy an HDMI-to-USB converter, but his camera can't output a live stream into HDMI, only a recorded video.
					- So we had an idea — maybe it is possible to create a good webcam ourselves. Would anybody care? Well, it’s almost 2021 now, streaming is still on the rise, pandemic is going strong and video meetings are everywhere. People are willing to spend some money, as indicated by countless videos on YouTube regarding the problem.
					- Let’s start with defining what is a good webcam.
					- A good webcam, in my opinion, is a device that provides a decent sound quality, at least on par with recent MacBooks, and an image quality on par with top smartphones, such as iPhone 11/12, Huawei P40 Pro, etc. As smartphones have a good image quality, then we could probably manufacture a webcam from smartphone parts that are cheap and easily available. How hard can it be?
					- If you’ve read at least a couple of articles on the topic of video production, you will know that to make quality content from the technical standpoint you need three things, in that particular order:
					- 1.  Sound
					- 2.  Light
					- 3.  Video quality
					- Let's discuss these properties and later how to manufacture it.
					- ### Sound
					- If you have a recent MacBook, it provides a decent sound quality with its three-mic array. I haven't researched it and don’t know much about other notebooks' audio quality. If you have a desktop PC, you have to have some external mic anyway.
					- If the web camera has shitty audio quality, you’ll have to buy additional gear. When I researched the topic, one of the recently released webcams (available from October 2020) with RRP of $180 was producing a sound as if a person sits in a big plastic barrel with a closed lid. Their voice was very muffled with lots of resonant rattles. That level of quality wasn’t acceptable 10 years ago, how this piece of gear could have been produced in 2020 escapes my understanding.
					- There are many good enough USB mics for $50+, you also can buy a great XLR microphone for $100, but then you’ll need an external sound card with phantom power supply. A decent one can easily cost you $200.
					- With almost any of these options you’ll have to install and configure some software that will provide sound level compression, noise suppression (because your notebook fans are spinning like hell) and won’t produce clicks in the process.
					- I would like my webcam to do this by itself, no rattling, minimized echo, etc.
					- ### Light
					- A lot of what makes a picture great comes from lighting the scene in a correct way.
					- The simplest thing is to sit in a room so the window is in front of you and the Sun isn’t shining into a lens from behind your shoulder.
					- Webcam cannot provide decent lighting capabilities by itself, so I won’t spend much time here. There is a [webcam by Razer](https://www.razer.com/streaming-cameras/razer-kiyo/RZ19-02320100-R3M1) with a built-in LED circle, but it’s necessarily small, always shines from a webcam direction and is mostly a gimmick.
					- We can rely somewhat on the good sensor here. If it provides good dynamic range, HDR capabilities and good low-light performance, then a patch of sunlight on the wall won't turn everything else black, or a poorly lit room won't turn into a gray noisy picture with a bleak silhouette.
					- ### Image quality
					- It’s impossible to get a good lens and image sensor into a notebook lid, because lids are very thin. They’re often something like 4 mm thick all together, and there is no escaping physics. Of course, it's possible to put a webcam into a thick part below the lid, but then it'll be useful for expressing anger at our colleagues with wide-open nostrils and not much else.
					- Maybe some crazy engineer in the future will develop an array of small sensors with an array of tiny lenses and somehow combine all that into a good image quality, but we don't have this tech yet. Any smartphone with a good camera has that camera with an ugly protruding lens as a thickest part of the phone.
					- So, if you want something better than a notebook's webcam, you can get some Logitech webcam with an image quality going back to 2012. It’s still better than a laptop, but nowhere close to current smartphones.
					- What if you want better still? The next option is to install an app on the phone and use it as a webcam. This gives a very good image quality, but it’s very inconvenient and in some applications doesn’t work at all. For some reason it isn’t always presented in applications as an option when choosing a video source.
					- I don’t want to constantly attach, detach, charge my phone and tune the position of a small tripod. What’s the next option?
					- The next option is to just buy a mirrorless photo-camera with a big fat 4/3” or even APS-C sensor. It will cost $500+ for a new one (you can buy used for cheaper). You will also need some gear to hold the camera in place, as it won’t just rest on the top of the screen like a regular webcam. You also need an HDMI-to-USB video grabber, and you need to be sure that the camera you buy can output full resolution live onto that HDMI. Also make sure that it's possible to turn off all on-screen info like `1/100s F3.5 ISO 800`, which is useful when you're shooting photos and videos through viewfinder, but not so much when you're in a video meeting. This feature is called "Clean HDMI".
					- Of course, you will have a lot of control over the whole stuff — set a diaphragm, get good bokeh, set ISO, set white balance, etc. Do you actually need it? Well, some of you do, and a lot of you do not. I learned all that stuff when I was 16, but now I’m pretty happy with how my phone chooses everything for me and just does great photos.
					- All that sounds pretty involved, isn’t it? It is a lot of time to research what you need, how to set it all up, and a lot of money too.
					- ### Manufacturing it
					- So there is a market gap between so-so webcams for $100-200 and a full-blown setup with a mirrorless camera, an external mic and lighting panels that will cost almost a grand or two, if you're so inclined.
					- I thought that it is a good idea to create an "upmarket" webcam for $250-300 that will provide good audio and video quality, on par with current smartphones, actually using the same parts. As smartphones are made in tens of millions, all relevant parts should be cheap and easily obtainable.
					- I quickly contacted some people who could help me do the project — firmware engineer, electric engineer and a company that does mechanical design.
					- What features are needed for a good webcam for streamers and video meetings? Audio: good parts (mics and ADC), good mechanical design and assembly (so nothing would rattle), and some post-processing. We certainly want some beam-forming capabilities to be able to focus on the person in front of the webcam, so we will need more than one microphone, maybe up to 4. These parts are easy to obtain, there are many in stock, it's not a problem.
					- Even if I think that 4k is not needed, I’m pretty sure it’s really a requirement to have in an upmarket webcam, as it will be really hard to sell a pricey webcam that can only do 1080p.
					- Also would be very nice to have some neural network inference on the chip, so we can run some AI stuff directly on the webcam without bothering a user’s computer that can be busy with other things.
					- I easily found a three-piece assembly for the iPhone 11 Pro for fifty bucks, two-piece from a Huawei P40 Pro for twenty five and a one-piece from P40 Lite for ten dollars. That’s with a lens, and bought in retail. Does it mean it costs peanuts (less than $5 for a sensor) to buy in bulk to produce my own webcam? Well... Maybe. I can’t just go and buy a couple thousands of these sensors. I’m pretty sure I can buy a couple thousands of replacement parts for phones, but sensors themselves are not sold freely. It's easy to buy some "random" sensor that was around for years and most certainly has "meh" quality by today's standards, but we need a good one, with good dynamic range, HDR capabilities and low-light performance.
					- I wrote to several vendors asking them what are the prices and conditions, and basically their answer is either silence or “we’ll sell it if you will buy hundreds of thousands per year”.
					- I've found suitable System-on-Chips, and it's the same — if we want to have hardware 4k encoder, it's either "sorry, it was a demo part and we don't do it", or "we have limited support capabilities, so we can only sell if you will buy hundreds of thousands, maybe you want some SoMs from our partners?". It is actually possible to buy System-on-Modules even in very small quantities, but it's going to be pretty expensive and will be good for a prototype, but for production it will blow past our budget. System-on-Module will cost almost the same as the web camera itself.
					- Oh, and a lead time (from order to shipment) is systematically 16+ weeks. It means they have no stock and will place an order at semiconductor foundry, have it produced, packaged and sent to customer. Swiftly.
					- It means I cannot just build five hundred webcams, see how good are they selling and build a couple thousand, and so on.
					- There is also a plastic injection step that requires upfront investment to manufacture molds, and of course design and engineering costs. All combined it was tens of thousands of dollars. I was willing to risk it and was pretty sure that in the worst case scenario it would be just a cost of my experience building hardware product.
					- But if I have to commit to a hundred thousand units or more, it means I would need to pour millions of dollars (that I don’t have) to manufacture an obscene amount of devices that I don’t know how to sell.
					- I thought about it for a couple of days and understood that I approached the problem from the wrong angle at the beginning.
					- The actual problem is not how to build a good web camera. The real question is how to sell it in quantity! Is it possible for me to sell hundreds of thousands of pricey webcams per year? If I know I will sell it, I can find an investment for that.
					- Let's describe my situation here. I’m a co-founder at [prophy.science](https://www.prophy.science/) which is a SaaS, and I work on it full-time. I can probably spend 20% of my time on something else, but I certainly don’t want to abandon it completely. I also have two small beautiful kids, and I really don’t want to move to Shenzhen to organize a big production there.
					- ### Going to market
					- Ok, what’s the current size of the market? Luckily, there are public companies in the market, so we can go look at their reports to see if there is anything meaningful. And there is, Logitech says they have about $130M in revenue from sales of PC webcams. I think they’re the biggest player in the market by a long shot, and they sell something like a few millions of webcams a year. That’s... not much?
					- It means that I have to sell like 10% of the Logitech shipment size, right from the start.
					- Sorry, what?
					- It’s an established player in the market with all the distribution in place, with a very recognizable brand, and here am I, knowing nothing about how to sell hardware products, and there is seemingly no way to slither into the market and scale.
					- Well, maybe there is, but I don’t see it. Maybe I could pull it off by diving deep down and going full-time on the problem for years, but it seems much more risky now.
					- Also I should mention that this market is basically indefensible. What prevents established players from doing pretty much the same, when they will see that there is a good niche? They just go to the same suppliers, get same or better parts/prices and crush a startup using their established distribution channels.
					- I remember a staple phrase from a lot of interviews, something along the lines of "If I knew how hard it would be, I wouldn't do it". Here we are, knowing how hard it will be, and not doing it.
					- I'm just going back to my SaaS, which is much more defensible, thank you very much.
					- My brother actually [started streaming](https://www.youtube.com/playlist?list=PL7gxcNpwRVlp1Xepntn5EiUFo0YjtT8ok), so you can go watch him code a [snake game in ClojureScript and React](https://www.youtube.com/watch?v=GxxGs1jA-kg&list=PL7gxcNpwRVlp1Xepntn5EiUFo0YjtT8ok&index=1).
					- Answering the question in title: you can't buy a good webcam because existing players seemingly don't think it's a good opportunity, and for newcomers the market is hard to enter.
					- We're also lucky that camera manufacturers added clean live HDMI into comparatively cheap cameras, so we don't need to spend $3000+ to set it all up.
			- ## Commercial webcams
				- Anker ProConf C200
					- Cheaper than the ((6718cb5e-e316-4072-991e-bd848222e337)) but with 2K quality, a built-in screen cover, adjustable field-of-view
					- [AnkerWork software on Linux - r/anker](https://red.artemislena.eu/r/anker/comments/v42z3c/ankerwork_software_on_linux/)
				- Logitech C920
				  id:: 6718cb5e-e316-4072-991e-bd848222e337
				  (given to mum)
					- Note: commonly recommended for Twitch streamers to get started with [[2024-10-23 Wednesday]]
			- [Learning Resources]
				- [/r/linuxhardware](https://www.reddit.com/r/linuxhardware)
				-
		- Audio
		  collapsed:: true
			- Input
				- Microphone
				  collapsed:: true
					- Blue Yeti microphone
					  id:: 678306bf-d9f5-4114-9320-8238c5f8740d
					- [Omnidirectional mic recommended by](https://youtu.be/Ux7pdWFo7hY?t=668) ((66041553-982d-4f6f-b2fd-ff8a827b17f2))
					- ## Software
						- [GitHub - teamclouday/AndroidMic: Use your Android phone as a microphone for your PC](https://github.com/teamclouday/AndroidMic)
						- [Audio Source](https://f-droid.org/packages/fr.dzx.audiosource/)
						  Linux-only? Lets you use an Android device as a USB microphone. Linux compatible
						- [NoiseTorch](https://github.com/noisetorch/NoiseTorch)
						  Background noise reduction
							- [Uses XWayland](https://github.com/noisetorch/NoiseTorch/issues/425)
						- [EasyEffects](https://github.com/wwmm/easyeffects)
						  Sound equaliser. Also limiter, compressor, etc
							- [Install Easy Effects on Linux | Flathub](https://flathub.org/apps/com.github.wwmm.easyeffects)
				- Headset
					- With microphone
						- Jabra Evolve2 Flex 65
						- Jabra Evolve 80
						- Bose Quiet Comfort Ultra
		- HDMI external capture card
		  collapsed:: true
			- This is how YouTubers capture video without recording affecting the performance
		- Desk pad
		  collapsed:: true
			- [LTT Northern Lights Desk Pad
			   – LTTStore Global](https://global.lttstore.com/products/deskpad)
			- ((632ce436-695a-419b-bffa-e172fda1c9cb)) play mats
		- Magnetic cable management
		  collapsed:: true
			- [MCM Landing
			   – LTTStore Global](https://global.lttstore.com/collections/mcm-landing)
			-
		- Related: ((65a98a50-811c-4de7-8127-0919127fe8af)) : ((67cc4886-06b2-4997-add7-26eb6fefcf23))
- Linux to-do : SOP
- {Archive}
  collapsed:: true
	- _Previous analyses_
		- Potential laptop models - early 2016 analysis and eventually got Lenovo ThinkPad T420
			- Also see NAS for compact bare bones desktops
			- $2250/$1750 i.e. £1200 Purism - Librem 13
			  collapsed:: true
				- https://www.crowdsupply.com/purism/librem-13?utm_medium=ref&utm_source=puri&utm_campaign=librem13&utm_content=referral
				- Has SSD + HDD drives
				- Hasn't got everything necessary for Qubes
					- https://www.qubes-os.org/compatible-hardware/
					- https://groups.google.com/forum/#!msg/qubes-users/WX1IXBFkUwk/M-Xg1e3kieMJ
			- £1450 MacBook Air 13in
			  collapsed:: true
				- 13in is more than big enough. With retina the 11in is looking very possible, though because it's so light going smaller isn't entirely necessary
				- £1450 with 8gb RAM, 512GB memory, 2.2 GHz i7 processor
				  http://www.apple.com/uk/shop/buy-mac/macbook-air?product=MJVG2B/A&step=cto_accessories
					- Doesn't allow both SSD and HDD drives?
			- $1000 Sony VAIO Pro 11
			  collapsed:: true
				- 1920 x 1080 resolution (same resolution of most 24-50" screens, 1920x1080, almost like dual monitor), 11", 4gb RAM, 2x USB 3.0, Core i5, 2lb. http://amzn.to/1wW1n2G -
				- WiFi issues, loud fan ////
				- New series of the old Sony Z12 Vaio - It has three hard drives, etc You can read my full review here http://tynan.net/sonyvaioz12
			- http://blog.laptopmag.com/top-10-ultrabooks
			- $514 Lenovo Thinkpad X140e 20BLS00400. 11.6in
			  collapsed:: true
				- $514 Lenovo Thinkpad X140e 20BLS00400
				- http://www.amazon.com/Lenovo-Thinkpad-20BLS00400-Business-Ultrabook/dp/B00IPIYZ3W/
				- 11.6in, 4lb, quad core 1.6ghz, upgradeable to 8gb, 8 hour battery, trackpoint and trackpad, upgradeable to SSD HDD
				- Find a local supplier or how to ship it here
				- Also an extra 4GB RAM module http://amzn.to/1pz9c9g
			- $700 Lenovo Thinkpad X230 http://amzn.to/1wp98yW 13", 2.6GHz, Intel Core i5, 4GB DDR3, 500GB HDD, Two USB 3.0
			- $480 Lenovo Thinkpad E540 http://amzn.to/1vy7Hdx 4gb RAM, 500gb, i3, 15.6", 2x USB 3.0
			- $1280 Lenovo T440 http://amzn.to/1wp8vW0 with USB 3.0, i7, 8gb RAM, 256gb, 14", 2x USB 3.0, 4lb/1.8kg
			- $600 Lenovo G500 15.6-inch Laptop - Black (Intel Core i3-3110M 2.4 GHz, 8 GB RAM, 1 TB HDD, http://www.amazon.co.uk/Lenovo-G500-15-6-inch-Laptop-Integrated/dp/B00HR6U4DS/ref=zg_mw_429886031_4 2.6kg, 52.4 x 30.8 x 7.6 cm
			- $250 ASUS http://amzn.to/1wp7BZV - 1x USB 3.0, 15.6", dual core 2.2ghz, 4gb RAM, 500gb, 2.1kg/4.7lb
			- $1040 Aspire S7-392 - 8gb RAM, 13", i5 1.6ghz, 2.9lb, 128 SSD, 2x USB 3.0
			- $380 ASUS VivoBook S500 - http://engt.co/1wVY3oc 4.6lb though
	- _Previous laptops_
		- Lenovo ThinkPad T430 - £382 (used) 16GB RAM, 1600x900
		  collapsed:: true
		  Nov 2017-Jan 2019
			- Got it because
				- Maxing out RAM on old laptop - mainly due to multiple tab Firefox sessions
				- Mum asked for a laptop since she gave her existing laptop to David
			- Main bullet
			  intralink2:: https://workflowy.com/#/6667e454a800
		- Lenovo ThinkPad T420 - £190 (used) 14", i5, 8GB RAM
		  collapsed:: true
		  Oct 2016-Nov 2017
			- Pros/Cons
				- Pros
					- Only laptop fully compatible with Qubes recommended security settings as of Jan 2016
					- Cheap used
				- Cons
					- No graphics card for video coding or parallel processing with Nvidia cuda cores
					- Limited to 8GB RAM
					- Could be thinner
					- Could be lighter
			- Specs
				- Allows both two HDD/SSDs (+£70 to add 240gb SSD)
				  collapsed:: true
					- £13 UltraBay http://www.amazon.co.uk/Ultrabay-Enhanced-Module-ThinkPad-adapter/dp/B00AQOI7GE/ref=pd_sim_147_1?ie=UTF8&dpID=41cUV4V6anL&dpSrc=sims&preST=_AC_UL160_SR160%2C160_&refRID=04WV12AQ8FTMTE3EAD7X
					- £57 240GB SSD http://www.amazon.co.uk/SanDisk-PLUS-Sata-2-5-inch-Internal/dp/B00S9Q9VS4/ref=pd_sim_147_2?ie=UTF8&dpID=41Cago76PuL&dpSrc=sims&preST=_AC_UL160_SR160%2C160_&refRID=04WV12AQ8FTMTE3EAD7X
					- https://forums.lenovo.com/t5/ThinkPad-T400-T500-and-newer-T/T420-Max-Physical-Drive-Sizes-SSD-HDD/td-p/1047593
					- https://www.youtube.com/watch?v=3XFmfFSjcQo
					- http://www.amazon.com/Caddy-Lenovo-ThinkPad-genuine-Newmodeus/dp/B00A2AWBKU
				- Up to 8GB RAM
				  collapsed:: true
					- https://superuser.com/questions/18995/how-can-i-tell-what-ram-will-fit-my-computer
					- £24 if my current one doesn't fit
					  http://www.amazon.co.uk/Memory-IBM-Lenovo-ThinkPad-T420-DDR3-12800/dp/B009BS6FDS/ref=sr_1_2?s=computers&ie=UTF8&qid=1452175539&sr=1-2&keywords=Lenovo+Thinkpad+T420+ram#customerReviews
				- £24 extended battery
				  collapsed:: true
					- http://www.amazon.co.uk/PowerSmart-ThinkPad-T410-T510-Series/dp/B00542SHBS/ref=pd_sim_147_3?ie=UTF8&dpID=41u6VZyRvjL&dpSrc=sims&preST=_AC_UL160_SR160%2C160_&refRID=04WV12AQ8FTMTE3EAD7X
				- 2.2 Kg
				- Matte, display suitable for outdoors
				- Stable metal hinges keep the screen securely in position
				- 14" Lenovo ThinkPad T420, i5
				- Connectivity
				  collapsed:: true
					- 5 USB slots: 1 powered in rear, 1 USB/eSATA combo port on right
					- Audio/microphone combo
					- 2 eSATA ports, one each side and one USB-B port on the LH side.
					- this model has a VGA & Display port connections, but no HDMI. You can however use a Display port to HDMI adaptor/cable if you wish to connect this to a HD TV set for example.
					- ExpressCard slot for wireless adapter/USB 3.0/eGPU
						- One 34-mm ExpressCard slot or 5-in-1 Media Card Reader slot
						- see local wf
						- USB 3.0 Express Card adaptor
						- SD Card reader
						- eGPU (external graphics card)
					- Ethernet port
					- ExpressCard34
					- 4in1 cardreader
					- Kensington Security slot
			- Suppliers
				- £190 i5 used (many reviews)
				  http://www.amazon.co.uk/Lenovo-Thinkpad-14-inch-i5-2520M-Professional/dp/B004WNAYS4/ref=pd_sim_sbs_147_1?ie=UTF8&dpID=41QFWOckK4L&dpSrc=sims&preST=_AC_UL160_SR143%2C160_&refRID=1VCS54MH4VNG2M990MCB
				- £345 for used i7 (no reviews though)
				  http://www.amazon.co.uk/Lenovo-ThinkPad-T420-inch-Laptop/dp/B004VL62UG/ref=sr_1_3?s=computers&ie=UTF8&qid=1452175992&sr=1-3&keywords=Lenovo+Thinkpad+T420+i7
				- https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core2+Duo+T6600+%40+2.20GHz
				- i5 is 2x better than current CPU
					- i7 2.3+ is 1.5-2x better than i5 though
		- Acer Aspire 5738g
		  collapsed:: true
			- 2.8kg/6.2lb + extended battery
			- 320gb HDD
			- 8gb RAM
			- 2.2ghz duo
			- 15.6" HD
			- 4 USB 2.0 ports
			- Dimensions: 383 (W) x 250 (D) x 26/37 (H) mm (15.1 x 9.9 x 1.03/1.5 inches)
			- Resolution: 1366x768
- _Related: _
	- [[Phone]] models
	- ((632090d7-5870-4192-af18-49244f5deb22))
	- ((6341c07c-00cf-4e45-9336-ebbcdbf8e71f))