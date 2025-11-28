- Linux setup SOP
  id:: 63a9adc8-c0c0-4a67-a2f6-c19473da1a99
	- From scratch
	  collapsed:: true
		- Download latest version of Veracrypt from X OR use an older version from [Run the GUI installer that's in /Documents/ESSENTIALS/Programs/veracrypt/](https://workflowy.com/#/cd059d459ec2)
		- Download latest version of CrashPlan from https://www.crashplanpro.com/app/#/console/app-downloads OR use an older version from X
		- Create new veracrypt1 container (100GB FAT outer volume, 95GB ext4 hidden)
	- Kubuntu setup
	  id:: 62d4471d-2ebd-46b8-b700-3b6362e06c80
		- v2 - separate partition for /home
			-
		- v1 - 1 partition
			- _Consider changing_
			  collapsed:: true
				- _Didn't install - 23/11/2021 new 2TB drive_
					- Two partitions?
					  collapsed:: true
						- Two
							- `/` - includes 8GB swap (for 16GB RAM), Docker files,
								- Setting up swap
									- See [Increase size of ](https://workflowy.com/#/180cdee369aa)<a href="https://workflowy.com/#/180cdee369aa">swap</a><a href="https://workflowy.com/#/180cdee369aa"> file to allow for full size of RAM</a>
							- `/home` -
					- **TODO**
						- Mount veracrypt1
						  collapsed:: true
							- Desc
								- An alternative to mount:
									- bindfs -n /media/veracrypt1 /home/boss/Desktop/veracrypt1
									  Doesn't work
								- sudo apt install bindfs
								  Required
								- Like with mount, this will be a (non-permanent) actual mount point, i.e. for instance not tracked as only a reference but version-control systems. But like ln -s, it does not require superuser permissions like mount does.
								- fusermount -u /home/dvad/home
								  Unmount with (or by restarting).
						- ((63a9ae52-587f-4d0f-a806-1ccd15714d1e))
						- Unofficial Galaxy Buds Client
						  /home/boss/Documents/ESSENTIALS/Portable/
							- [https://github.com/ThePBone/GalaxyBudsClient](https://github.com/ThePBone/GalaxyBudsClient)
						- _Related:_ Backup fileset
						  [My backup fileset](https://workflowy.com/#/c26d9e45355a)
					- See [WINE stuff](https://workflowy.com/#/d6fae9c3d6c4)
					- See [libstrangle - to limit FPS for CPU intensive games](https://workflowy.com/#/faa6cdf769ec)
				- To add
					- Deprecate Flameshot for Spectacle?
					  collapsed:: true
						- Tested Sat, Apr 30, 2022
							- It *is* possible to screenshot (printscreen button), screenshot custom region (printscreen twice), annotate and upload to imgur via Spectacle. However UX is not as quick, and I haven't bothered to learn how to customise hotkeys or whatnot
						- [https://teddit.net/r/kde/comments/9a766h/daily_tip_you_can_upload_a_screenshot_to_imgur/](https://teddit.net/r/kde/comments/9a766h/daily_tip_you_can_upload_a_screenshot_to_imgur/)
					- Different distribution? See ((62e11d87-874f-4112-8bd5-a0a8f6651248)) [Pros/Cons](https://workflowy.com/#/48fa1fdfed04)
					- ((635eb108-7d76-47c7-bddb-a8a977599a39)) - consider ZFS, BTRFS, etc
					  #PC
					- [xdg-ninja](https://github.com/b3nj5m1n/xdg-ninja)
					  id:: 635f87ef-7714-43e6-8705-b04a7307bfba
					  collapsed:: true
						- https://teddit.net/r/linux/comments/uouh7p/xdgninja_a_tool_to_help_you_clean_up_your_home/
						- Intro
							- This tool scans your *$HOME* directory for files that don't need to be there. When it finds a file it knows about, it tells you how you can (re)move it.
							- You can find it [here](https://github.com/b3nj5m1n/xdg-ninja). Simply clone the repository and run the script.
							- I've spent several hours porting the list from the [arch wiki](https://wiki.archlinux.org/title/XDG_Base_Directory), a lot of the programs listed there are supported by this tool out-of-the-box.
							- The basic tool is written in bash script, it just needs *jq* to parse json and optionally *[glow](https://github.com/charmbracelet/glow)* to render the markdown as rich text.
							- There's also a tool provided to help you add more files that you know
							   how to remove. If you add a configuration, please open a PR on GitHub.
							-
			- Setup
			  collapsed:: true
				- Update packages
				  `sudo apt-get update && sudo apt-get upgrade -y`
				- For adjusting screen resolution
				  collapsed:: true
					- System Settings > Hardware > Display and Monitor (AKA Display Configuration) > Scale Display > e.g. 1.2
					- [[2022-12-30 Friday]] testing with normal 100%
				- Dark theme
				  collapsed:: true
					- System Settings > Look and Feel > Breeze Dark
				- Using "Active Accent Dusk" for Window Decorations
				  collapsed:: true
					- System Settings > Appearance > Window Decorations > Get New Window Decorations
				- Change Dolphin single click behaviour
				  collapsed:: true
					- Open System Settings > Workspace > Workspace Behaviour > Double-click to open files
				- Config KRunner
				  collapsed:: true
					- Remove
						- Browser tabs
						- Command line
						- Desktop search
						- Recent documents
				- Disable KRunner from launching via ALT+SPACE shortcut
				  collapsed:: true
					- (System Settings > Shortcuts) > Global Shortcuts > KRunner > uncheck ALT+SPACE
				- Hide some icons from taskbar
				  collapsed:: true
					- Open System Tray Settings
					- _Disabled_
						- Vaults (System Services)
					- _Always hidden_
						- Bluetooth (Hardware Control)
						- Clipboard (System Services)
				- Keyboard shortcuts setup
				  id:: 6318fc57-db8a-441f-af0e-c8392241a76b
				  collapsed:: true
				  AKA keybindings
					- {{renderer :tocgen2, ((6318fc57-db8a-441f-af0e-c8392241a76b))}}
					- # Meta
						- ## Deprecate and replace list
						  id:: 63416a23-cb5b-4cc1-a648-0693b6865309
						- ## To integrate
							- `Meta + PgDown` = Switch to next desktop. then again currently used for minimise/maximise window
							- `Meta + End`? = Window to next desktop
						- ## To practice
							- ((66bccbab-69a3-43a4-83c8-0727ff165702))
							- [[Logseq]]
								- {{embed ((66bf58c0-74a1-4f7d-bd9c-331818ccc2d8))}}
							- ((63134593-906c-43b5-96fe-33dc2c34fda4))
								- {{embed ((633b7517-b91e-4b4e-a51c-450c3cdc2755))}}
							- ((634bd1ec-d116-4fef-830f-cc728e2ad066))
								- ((63c28370-6bf2-407f-9fc5-9a5f69f57b12))
							- ((641990a5-3a50-421d-a1a4-191d67bc683f))
								- {{embed ((6641f4de-7807-4993-b69d-4c8ff0310f62))}}
							- ((6320850b-1f87-4653-96d9-fedd85d0201d))
							- ((6320852a-625c-4205-b117-af91259e32f8))
							- ((65a98a52-0924-45bc-aaa8-fcb33c7f1ea2))
								- {{embed ((6402133a-58ba-436b-83ed-20e164aedb35))}}
							- ((6341843c-ac9c-413f-b157-f0b3d86a5da9))
							- See tmux
							- ((67ab586e-4166-4ec1-a6f2-af9cbc23258b))
						- ## Other high priority
							- ((634bf00a-932c-4a43-8a7c-c822f175ffed))
							- ((6347106c-d3b8-45fa-af5d-9593dcfe427f))
						- Related: ((63c3d5f0-2f7a-4a14-b3f8-b69236449056)) (after better practice with not using a mouse)
					- # KDE
						- ## Shortcuts
							- `Meta + F1` = Mute microphone (audio input)
							  collapsed:: true
							  id:: 63c2a257-452d-4027-97db-0fc9a737ce11
								- Related: ((633b7503-8c45-47ea-bf12-e46b2750b42b))
								- Audio Volume
							- ### KWin
							  id:: 65a98a52-0924-45bc-aaa8-fcb33c7f1ea2
							  collapsed:: true
								- # Switching focus
									- ## Switch focus to other windows
									  id:: 65a98a52-0a1d-40c9-af65-c166da9973bd
										- Meta
											- ((634a7b9d-bfc2-49f7-b050-66ee4796aa6b)) / Right doesn't work
											  id:: 6836b323-5e97-4f77-b34b-be5b45202c77
												- Actually it seems to not work on Virtual Desktop 1 only
												- [494413 – "Switch to Window to the Left" and "Switch to Window to the Right" only partially works on Virtual Desktop 1](https://bugs.kde.org/show_bug.cgi?id=494413)
												- [497121 – Shortcut "Switch to Screen to the Left" does not work when no open windows](https://bugs.kde.org/show_bug.cgi?id=497121)
												- [469734 – Kwin's "Switch to window to the left/right" do not work across screens that aren't the same size](https://bugs.kde.org/show_bug.cgi?id=469734)
												- See
													- ((65a98a52-0109-4224-b5bb-45c937f33085))
											- _Why_
											  Note: these are already defaults
												- When you have the windows tiled side-by-side or top-to-bottom and such, you may want to switch windows rapidly. Keep in mind, if you have a bunch of floating windows going on the same desktop, they can insert themselves on you in such a way that you may not expect.
										- `Meta + ALT + Up` = Switch to Window Above
										  id:: 634a7bc9-d2c0-4375-9cc7-f59f8c6838d9
											- It's a default. Only useful in practice if using tiling
										- `Meta + ALT + Below` = Switch to Window Above
										- `Meta + ALT + Left` = Switch to Window to the Left
										  id:: 634a7b9d-bfc2-49f7-b050-66ee4796aa6b
										- `Meta + ALT + Right` = Switch to Window to the Right
										  id:: 65a98a52-0109-4224-b5bb-45c937f33085
									- ## Switch focus to other screens
										- {Archive}
										  collapsed:: true
											- `Meta + Left` = Switch to Screen 1
											  Deprecated for ((644c0b30-7ed2-466d-8005-6206fdeea474))
												- There's no "Switch to Screen to the Left" so this is the closest approximation
											- `Meta + Right` = Switch to Screen 0
											  Deprecated for ((644c0b30-609f-4c24-a0c2-6f34de342866))
												- There's no "Switch to Screen to the Right" so this is the closest approximation
											- `Meta + ,`= Switch to Previous Screen (recommended by Bismuth). Instead now ((634aaa65-7212-4951-bb6c-303be710a87c))
											  id:: 634a932d-1712-4d1c-91d4-d9480265c193
											- `Meta + .` = Switch to Next Screen (recommended by Bismuth). Instead now ((634aaae7-d0fb-43d3-8461-51ed3eb517bc))
											  id:: f7e5cd31-0fb3-4613-b8d0-411b37852613
									- ## Switching desktops
										- `Meta + ,` = Switch to Previous Desktop
										  id:: 634aaa65-7212-4951-bb6c-303be710a87c
										- `Meta + .` = Switch to Next Desktop
										  id:: 634aaae7-d0fb-43d3-8461-51ed3eb517bc
										- ### Default but not best practice
										  collapsed:: true
											- `CTRL + F1` = Switch to desktop 1
											- `CTRL + F2` = Switch to desktop 2
											- `CTRL + F3` = Switch to desktop 3
											- `CTRL + F4` = Switch to desktop 4
										- {Archive}
										  collapsed:: true
											- `Meta + TAB` = Switch to next desktop
											  id:: 6341da6e-175a-496b-90d9-25f4525d4279
												- Note: replaces the default "Walk through activities"
												- Deprecated for ((63c10960-4515-46ee-be65-4c919b35c67b))
											- `SHIFT  + Meta + TAB` =  Switch to previous desktop
											  id:: db598f32-e760-4657-91e1-3b2161fa47ab
												- Note: replaces the default "Walk through activities (Reverse)"
												- Deprecated for ((63c10960-4515-46ee-be65-4c919b35c67b))
											- *Default*
												- `CTRL + Meta + Down` = Switch One Desktop Down
								- # Move current window
									- *Move current window to other screens*
									  id:: 63416905-718f-43bc-85d7-87f68dc38818
										- `SHIFT + Meta + Left` = Window to Previous Screen
										  id:: 63416956-b852-44a2-8bc5-d1c821405eca
										  collapsed:: true
											- Note: this is a default
											- `SHIFT + Meta + ,`(`Meta + <`) recommended by Bismuth as it matches ((634a932d-1712-4d1c-91d4-d9480265c193))
										- `SHIFT + Meta + Right` = Window to Next Screen
										  id:: 6341697e-418f-4241-aeed-66fe5fa83a4a
										  collapsed:: true
											- Note: this is a default
											- `SHIFT + Meta + .`(`Meta + >`) recommended by Bismuth as it matches ((f7e5cd31-0fb3-4613-b8d0-411b37852613))
										- {Archive}
										  collapsed:: true
											- `CTRL + SHIFT + 1` = Window to Screen 1
											  id:: 633b7503-529d-4854-9a9e-9ea7d9f284df
											  collapsed:: true
												- It's for using two monitors - swap windows to the left monitor
											- `CTRL + SHIFT + 2` = Window to Screen 0
											  id:: 633b7503-43dd-418d-8643-9ac369a50c15
											  collapsed:: true
												- It's for using two monitors - swap windows to the right monitor
									- *Move current window to other desktops*
									  id:: 6402133a-58ba-436b-83ed-20e164aedb35
										- `SHIFT + Meta + ,`(`Meta + <`) = Window to Previous Desktop
										  id:: d852e5ad-2862-4a0e-bf68-a9a0df08c0e8
										- `SHIFT + Meta + .`(`Meta + >`) = Window to Next Desktop
										  id:: 6402133a-ced2-4b85-aaab-b37336b4bbb3
										- {Archive}
										  collapsed:: true
											- `CTRL + Meta + F1` = Window to desktop 1
											- `CTRL + Meta + F2` = Window to desktop 2
											- `CTRL + Meta + F3` = Window to desktop 3
											- `CTRL + Meta + F4` = Window to desktop 4
											- `CTRL + Meta + Right` = Window to next desktop. Note: also switches me to next desktop?
											  id:: 63417bb2-a5b3-4b4c-9e7d-b8db8712ba8e
											- `CTRL + Meta + Left` = Window to previous desktop
											  id:: 63417bc9-3fb5-4a3d-8b66-df2e9e01ebf0
											- *Defaults*
												- `CTRL + SHIFT + Meta + Down` = Window One Desktop Down
								- # Tiling
									- Meta-T the quick tiling is launched allowing complete control of where your windows are placed
									- Drag windows with Shift pressed and it will stick to the tiled layout.
									- ((644c0b30-03f1-452f-b45b-4e1b5e11b990))
									  collapsed:: true
										- {{embed ((644c0b30-03f1-452f-b45b-4e1b5e11b990))}}
								- # Keep window
									- `Meta + B` = Keep window above others
									- `Meta + N` = Keep window below others
									- `Meta + M` = Keep window on all desktops
								- # Other
									- `CTRL + ALT + ESC` = Kill window
									- `Meta + W` = Toggle Overview
									  collapsed:: true
										- Overview effect in 5.24. "Desktop Grid"?
											- https://teddit.adminforge.de/r/kde/comments/so7tdi/a_button_to_activate_the_new_overview_effect_in/
											- https://www.phoronix.com/news/KDE-Overview-Effect-Like-GNOME
									- `Meta + ESC` = Opens System Monitor
									  id:: 67aa9631-b11f-4f38-9b38-fa465ae4d3d4
									- `SHIFT + F11` = Full-screen
										- Based on ((63134593-906c-43b5-96fe-33dc2c34fda4))'s ((6714dbe1-7ad3-4c8a-92cb-8c3b88fb5d8f))
									- `CTRL + Meta + MouseWheel` = Zoom/unzoom
									  id:: 6834478e-fb7c-44d9-9f26-ec27f4fcb03c
								- # Notable unused combinations
									-
								- {Archive}
									- ((6347106c-d3b8-45fa-af5d-9593dcfe427f)) related
									  collapsed:: true
										- ((634a902a-c70d-4ba4-8abd-f203d92a249e))
											- {{embed ((634a902a-c70d-4ba4-8abd-f203d92a249e))}}
										- *Quick tiling*
										  id:: 65a98a52-7a12-481d-b600-d0afba009a8d
											- *Quick tiling* - **Potentially deprecating with Bismuth**
												- `Meta + Down` = Quick tile window to the bottom
												- `Meta + Up` = Quick tile window to the top
												- `Meta + Left` = Quick tile window to the left
												- `Meta + Right` = Quick tile window to the right
								- Related:
									- ((65f58f8e-1860-4087-b0f5-a9ef34dbb9b7))
									- ((65a98a52-4d00-4f81-9247-4181cf69fcf7))
									- ((632092d8-1d88-4f97-843a-492cfbff5720))
							- ### Plasmashell
							  collapsed:: true
								- ### Disabled
									- `Meta + <number` = Activate Task Manager Entry `<number>`
										- i.e. swap to first application window
							- ### System Settings
							  collapsed:: true
								- `Meta + Insert` = Keep Window Above Others
								  id:: 67ab586e-4166-4ec1-a6f2-af9cbc23258b
									- To recreate PiP mode
							- Present Windows
							  collapsed:: true
								- System Settings > Desktop Behaviour > Screen Edges
								- `Present Windows - All Desktops`
								- ![image.png](../assets/image_1671451768353_0.png)
							- `F10` = key is now used in most KDE apps (with more being ported soon) to open the main menu or hamburger menu
							- Pressing Shift+delete to force-quit a process using SIGKILL in System Monitor now tells you that this is what will happen, rather than leaving it a secret
							- You can now open System Monitor with the Meta+Escape shortcut
						- ## Global Shortcuts
						  id:: 65a98a52-4d00-4f81-9247-4181cf69fcf7
							- Meta
								- `Meta` key for global shortcuts is ideal so it doesn't conflict with native shortcuts of focused app
							- `CTRL + ALT + A` = KWin : ((630f9511-e7c7-4bf8-9e35-3737f5537a8b)). set it to "none"
							- ((67aa9631-b11f-4f38-9b38-fa465ae4d3d4))
							- `CTRL + ALT + Spacebar` = Open/Hide to system tray ( ((67a8e0d5-c7e0-43e9-af3b-b728b37bb220)) )
							- ((67a8e14c-a404-4eba-91c9-947b99aeb521)) ( ((65b7e7af-d429-4b93-bb1a-33dc05bf5400)) )
							- ((677d750a-b70f-47dc-922d-f9e3e054f388)) ( ((63ad9567-857c-4b16-8292-abf0e85a0326)) )
							- ((680a0c08-1869-4290-8c40-e86c21d5f579)) : ((680a0ba5-a9a2-4ea0-b529-7ff1ef55769f))
								- {{embed ((680a0ba5-a9a2-4ea0-b529-7ff1ef55769f))}}
							- ((6834478e-fb7c-44d9-9f26-ec27f4fcb03c))
						- ## Defaults
							- `CTRL + ALT + ESC` = Kill window (xkill / force quit)
							  id:: 62e11d89-b548-471c-a047-17c13e04311a
							- TTY (CLI interface, no GUI)
								- `CTRL + ALT + F1` = Switch back to GUI:
								- `CTRL + ALT + F2` = Switch to TTY2:
							- `Print` = Full screen capture, with confirmation window
							- `SHIFT + Print` = Full screen capture, no confirmation except a notifcation. Saved to `~/Pictures/Screenshots`
							- `SHIFT + Meta + Print` = Rectangular Region capture
						- ## Custom Shortcuts
							- How to create
							  collapsed:: true
								- System Settings > Shortcuts > Custom Shortcuts
									- Create new shortcuts
										- Edit > New > Global Shortcut > Command/URL
							- `CTRL + ALT + PgDown` = Restart GUI
							  ```bash
							  killall plasmashell; kstart5; exit
							  ```
							- `CTRL + ALT + Backspace` = Restart Xorg
							  collapsed:: true
							  ```bash
							  sudo systemctl restart display-manager
							  ```
								- Open Yakuake and run:
								  `sudo dpkg-reconfigure keyboard-configuration`
								- You will see the keyboard configuration. Press ENTER 5 times to skip all keyboard related options except for the Kill X part. When you get to the Kill X option which looks like this:
								- Select YES and press enter. Wait a bit while everything configures and after that you should have the ability to CTRL+ALT+BCKSPC right on the current session. After saving any work you have pending, try it yourself.
								- Perfect to solve any visual issues or annoying apps.
							- `CTRL + ALT + D` = Klipper: Next History Item
							  id:: 66bccbab-69a3-43a4-83c8-0727ff165702
								- Created because of this [Logseq plugin bug](https://github.com/yoyurec/logseq-awesome-ui/issues/85) which I would run into less if I wasn't limited to only pasting one item from the clipboard easily
								  id:: 66bccb7b-d3cb-4bce-a804-aa0026bb4e20
							- `CTRL + ALT + A` = Klipper: Previous History Item
							  id:: 66bccb6b-8fa6-405b-b746-0257c463c59f
							  collapsed:: true
								- Not really relevant because if I copy a new item to the clipboard then the selection will switch to that one
								- ((66bccb7b-d3cb-4bce-a804-aa0026bb4e20))
						- See ((632092d8-bb96-4229-b363-c68b4246b234))
					- # Other KDE-managed
						- `CTRL + ALT + F1...F7` = Switch to n-th virtual console (TTY)
						- `CTRL + ALT + F2` = Switch to 2nd virtual console (TTY) - should be GUI on Wayland
						- `CTRL + ALT + DEL` = Log out (with confirmation)
						- `CTRL + ESC` = Show system activity (mini System Monitor)
						- `CTRL + F12`/`Meta + D` = Show Desktop (toggle)
						- `ALT + F2` = KRunner
						- `ALT + F4` = Close window
						- `ALT + TAB` = Walk Through Windows
						  id:: 65a98a51-0ec5-4aff-a69c-3353485d79ed
						  collapsed:: true
							- [[2025-02-11 Tuesday]] Modified this to be filtered to current screen
								- I can use ((644c0b30-5a7f-4e8d-a282-fd96c72d17f1)) to swap back and forth between one application open on each screen already
								- I'm finding it annoying to have to cycle through every single application
								- How:
									- Settings > Apps & Windows > Window Management > Task Switcher > Main
									- Filter windows by:
										- Enable `Screens`: Current screen
						- `SHIFT + ALT + BACKTAB` = Walk Through Windows (Reverse)
						- `Meta + L` = Lock session
						- `Fn + Esc` = Fn lock
						- `Fn + F1` = Mute audio output
						  id:: 633b7503-8c45-47ea-bf12-e46b2750b42b
						  collapsed:: true
							- Related: ((63c2a257-452d-4027-97db-0fc9a737ce11))
						- ((63c10960-4515-46ee-be65-4c919b35c67b))
							- {{embed ((63c10f9c-f2a7-442a-b51c-cb4eb080ae3f))}}
					- # Wayland
					  id:: 643afaae-59a0-4cec-9333-4324e3f3c991
					  collapsed:: true
						- # Pros/Cons
							- ## Pros
								- Required for
									- ((63ad9565-9f04-447d-b3c2-7541d47f2703)) : ((644c0aa9-31fb-43b7-bd15-0c57eb2e7204))
									- ((63a9ade4-ad80-4f73-ad36-483fb022f583))
									- ((63134593-906c-43b5-96fe-33dc2c34fda4))
										- ((635037e8-1155-4253-a10e-36bec5ecc740)) : ((678258eb-5373-4eaa-9714-bfd290bf0b34))
										- XWayland somehow enables my custom icons for each app to be reflected in the tray
										  collapsed:: true
											- Custom icon issues - report when I'm on Kubuntu 25.04 to KDE, as my current OS KDE is no longer supported
											  collapsed:: true
												- [Log in to KDE Bugtracking System](https://bugs.kde.org/enter_bug.cgi?product=plasmashell&component=Task%20Manager%20and%20Icons-Only%20Task%20Manager%20widgets)
												- On Wayland the Icon field used to launch an application is ignored and instead a default icon is used in the Task Manager
												- ```
												  SUMMARY
												  I use Firefox Flatpak with multiple profiles, and so to launch each of them they have a separate .desktop file and unique values for the Icon field. 
												  
												  When I launch these .desktop files on Wayland then each Firefox window has the same orange default Firefox application icon. When I use Flatseal to force Firefox to launch in XWayland then in the Task Manager I can see the unique Icon for each Firefox window in the Task Manager instead of a default being used.
												  
												  Example .desktop file:
												  #!/usr/bin/env xdg-open
												  [Desktop Entry]
												  Categories=Network;WebBrowser;
												  Comment=Browse the World Wide Web
												  # Changed
												  Exec=/usr/bin/flatpak run --branch=stable --arch=x86_64 --command=firefox --file-forwarding org.mozilla.firefox -P LEISURE --class=LEISURE @@u %u @@
												  GenericName=Web Browser
												  # Changed
												  Icon=/home/boss/Documents/ESSENTIALS/Other-files/app-icons/firefox-icon-4029.png
												  Keywords=web;browser;internet;
												  MimeType=text/html;text/xml;application/xhtml+xml;application/vnd.mozilla.xul+xml;text/mml;x-scheme-handler/http;x-scheme-handler/https;
												  # Changed
												  Name=LEISURE Flatpak-Firefox
												  StartupNotify=true
												  # Changed
												  StartupWMClass=LEISURE
												  Terminal=false
												  Type=Application
												  Version=1.0
												  X-Flatpak=org.mozilla.firefox
												  
												  STEPS TO REPRODUCE
												  1. Create a .desktop file for Firefox Flatpak with a unique icon.
												  2. Try to launch it via Wayland
												  3. Try to launch it via XWayland/X11
												  
												  OBSERVED RESULT
												  Default application icon used on Wayland
												  
												  EXPECTED RESULT
												  Icon field from .desktop file being used on Wayland
												  
												  SOFTWARE/OS VERSIONS
												  Linux/KDE Plasma: 
												  KDE Plasma Version: 
												  KDE Frameworks Version: 
												  Qt Version: 
												  
												  ADDITIONAL INFORMATION
												  ```
											- [[2025-01-11 Saturday]] I can't seem to replicate it at all. Tried VMs with clean Kubuntu, ((671b6e25-ba39-4d7d-b20e-1f12303488ca)), ((67827678-0a4e-43e2-81bd-f21f6609b8ee)) and none I could get to have XWayland app icon which matched the `Icon` field even using Flatseal to control Wayland vs XWayland. Must be some other configuration I've done but not documented
											- [Report on Bugzilla](https://bugzilla.mozilla.org/show_bug.cgi?id=1941113)
								- Better for VFIO and GPU hotplug
									- If using GPU passthrough with a VM (VFIO) don't have to restart X session to use Linux apps once you've turned off the VM
								- Works similarly to ((63134593-906c-43b5-96fe-33dc2c34fda4))'s WebRender in using the GPU rather than CPU for rendering
								- [X.Org](http://X.Org) [was designed decades ago and the updates to it are quite hacky. Wayland starts from a modern foundation](https://www.reddit.com/r/linux/comments/a5v2t8/why_is_wayland_better_for_the_future_than_x)
							- ## Cons
								- Lacks
									- Not feature complete compared to [X.Org](http://X.Org) yet
										- Note: some of these may not be an immediate issue if they can still run via XWayland
										- Some applications haven't implemented Wayland-compatible screensharing
										  collapsed:: true
											- [[2023-03-25 Saturday]] With the new XwaylandVideoBridge utility, you can now screencast native 
											  Wayland windows from Xwayland apps like Discord (Aleix Pol Gonzalez and David Edmundson, [Link](http://blog.davidedmundson.co.uk/blog/xwaylandvideobridge/))
												- With the new XwaylandVideoBridge utility, you can now screencast native Wayland windows from Xwayland apps like Discord (Aleix Pol Gonzalez and David Edmundson, [Link](http://blog.davidedmundson.co.uk/blog/xwaylandvideobridge/))
											- ((63a9adc7-fc79-4fa3-8ca5-925a17291c26)) can't do it for Chromium, but can with Firefox
											  [[Screensharing support in Wayland with Chromium/Chrome (tracking issue) · Issue #91218 · NixOS/nixpkgs · GitHub](https://github.com/NixOS/nixpkgs/issues/91218#issuecomment-1092134275](https://github.com/NixOS/nixpkgs/issues/91218#issuecomment-1092134275))
											- Apps
												- Discord doesn't support screensharing with sound (X + Wayland?)
												  [https://teddit.net/r/linux_gaming/comments/qsj5kb/sharing_screens_with_sound_is_still_not_supported/](https://teddit.net/r/linux_gaming/comments/qsj5kb/sharing_screens_with_sound_is_still_not_supported/) - may now be working in 2024 with the XWaylandVideoBridge
													- Helvum - Chromium Wayland Discord differences
														- Joining a Discord call connects Yeti `capture` to two new Chromium input boxes
														- Also creates two new Chromium output boxes, and connects them to the Combined playback box
												- Element doesn't support screensharing on it's desktop app (only web app)
												  [https://github.com/vector-im/element-web/issues/4880#issuecomment-968580564](https://github.com/vector-im/element-web/issues/4880#issuecomment-968580564)
												- ((6312a076-eb26-4bd5-a669-ea0a50d06668)) doesn't support screensharing on Wayland
												  [https://github.com/signalapp/Signal-Desktop/issues/5350#issuecomment-954272676](https://github.com/signalapp/Signal-Desktop/issues/5350#issuecomment-954272676)
												- ActivityWatch doesn't work
										- [Plasma/Wayland Known Significant Issues - KDE Community Wiki](https://community.kde.org/Plasma/Wayland_Known_Significant_Issues)
										- ((670ff7c4-cbc4-4975-b1a6-4d8d3d08635f))
									- Not implemented yet by desktop environment (KDE)
										- [Can't remember window positions](https://bugs.kde.org/show_bug.cgi?id=15329#c106)
										  id:: 674599d9-73e9-4abb-a018-aec0b467fb7d
											- [[2024-11-26 Tuesday]] Using ((649b140a-7d3a-4e3e-81ba-2629b12fc843)) to disable Wayland, and confirming it uses XWayland by checking it appears under `xlsclients`
												- Meta
													- Basically to ensure they open on my left monitor
												- ((63134593-906c-43b5-96fe-33dc2c34fda4))
												- ((6312a075-ceb2-4a57-adc5-2a27f91e865c))
												- ((65a98a51-b5c3-4329-a1c7-321ce408e6f8))
												- KeePassXC
												- Calibre
												- Stremio
												- Strawberry
												- Discord
								- For Nvidia GPUs requires an extra step to activate it
								  collapsed:: true
									- _What distros EGLStreams_
										- KDE has recently implemented EGLStreams
											- [source] [https://community.kde.org/Plasma/Wayland_Showstoppers#NVIDIA](https://community.kde.org/Plasma/Wayland_Showstoppers#NVIDIA)
											- KDE supports it with an environment variable
												- NVIDIA
												- The NVIDIA blob uses a custom EGL extension which [Plasma 5.16 added support](https://phabricator.kde.org/D18570) for. It requires setting the _KWIN_DRM_USE_EGL_STREAMS=1_ environment variable to activate.
												- Other aspects of the "Wayland experience" with NVIDIA such as XWayland compatibility are outside of our influence.****
												- **Partly fixed:** Requires manual activation.
											- NVIDIA still does not support the standard Linux solution gbm, which is supported by all vendors and nowadays even going to enter the mobile space. E.g. the purism phone is going to have a standard graphics stack with gbm. So no additional code required. But NVIDIA doesn’t support gbm. Instead it has a proprietary implementation called EGLStreams, which no other vendor implements. Due to that Plasma/Wayland cannot support OpenGL for NVIDIA users.
										- X v1.20 supports EGLStreams (Nvidia's proprietary solution for Wayland support) so XWayland can be used (compatibility layer for Wayland via X)
										  source:: https://www.phoronix.com/scan.php?page=news_item&px=Xorg-Server-Entering-2019
									- _Background on EGLStreams_
									- _Background on Nvidia being assholes to Linux_
										- Sway developer (graphics related)
										  https://drewdevault.com/2017/10/26/Fuck-you-nvidia.html
										- Linus Torvalds says "fuck you" to Nvidia (mainly because they don't offer open-source drivers for the kernel unlike Intel and AMD)
						- # Tests
							- [[2024-10-16 Wednesday]] Now going full-time use
								- # Resolved
									- ((63ad9565-9f04-447d-b3c2-7541d47f2703)) : ((644c0aa9-31fb-43b7-bd15-0c57eb2e7204))
								- # Issues
									- ActivityWatch doesn't work, AppImage crashes immediately. This may be a separate issue though
									- Firefox PiP limitations
										- seems to forget the window location, it opens in the middle of the screen
										- It also doesn't stay on top automatically
											- Wayland doesn't allow setting `always on top`
												- [PiP protocol in-progress](https://gitlab.freedesktop.org/wayland/wayland-protocols/-/merge_requests/132#note_2562588)
									- ((674599d9-73e9-4abb-a018-aec0b467fb7d))
									- Applications need to implement [xdg-activation](https://wayland.app/protocols/xdg-activation-v1) so that other applications can take focus e.g. using ((6492a114-d9c9-4fe5-ab93-f86b212ea656)) doesn't make that browser the foreground app/steal focus
									  id:: 670ff7c4-cbc4-4975-b1a6-4d8d3d08635f
										- ((6492a114-d9c9-4fe5-ab93-f86b212ea656)) : [Browsers don't go to the foreground and take focus when links are opened on Wayland · Issue #159 · sonnyp/Junction · GitHub](https://github.com/sonnyp/Junction/issues/159)
									- ((6312a076-eb26-4bd5-a669-ea0a50d06668)) : ((663b24fb-fa04-4f84-8b19-1743340928aa))
									- ## Issues from previous tests
										- ((65a98a50-b4e8-41f7-9959-35465cbe3150)) : ((65a98a51-b1d6-4645-97c5-48bf070e130b))
										- ((65a98a51-4f46-46ca-848b-2173fe34d8e2))
							- [[2023-10-08 Sunday]] Several issues
							  collapsed:: true
								- Upscaling is off - text is a big smaller on Wayland
								- ((649b1463-90cf-40ee-b80f-cb955fc2264c)) can't be full-screened without it messing up where the mouse thinks it is. Can only maximise window
								- Had a KDE crash after sleep that forced me to restart laptop
								- ((62e283e1-ebea-4ab9-9763-aa6a1b7ea0ba)) Flatpak not having a proper app icon was annoying. Think Obsidian had the same
								- Laptop woke from sleep with Night Colour still active, and it couldn't be deactivated
									- Several other parts of KDE stopped working including launching Calibre Flatpak, Vaults autoclosed, typing into ALT + F2 bar didn't work
							- [[2022-06-01 Wednesday]]
							  collapsed:: true
								- Pros
									- Waydroid is cool so far
								- Cons
									- ((65a98a50-b4e8-41f7-9959-35465cbe3150)) : ((65a98a51-b1d6-4645-97c5-48bf070e130b))
									- [syncthingtray pop-up floats in middle of screen instead of above systray](https://github.com/Martchus/syncthingtray/issues/170#issuecomment-1880059019)
									  id:: 65a98a51-4f46-46ca-848b-2173fe34d8e2
										- Author recommends using the Plasmoid install meanwhile
									- System tray issues
									  collapsed:: true
										- The protocol as a whole doesn't work well with Wayland or Flatpak
										- [KDocker doesn't work](https://github.com/user-none/KDocker/issues/95#issuecomment-945431680)
										- [AllTray doesnt work](https://bugs.launchpad.net/alltray/+bug/1947554)? (KDocker alternative)
										- KeePassXC works for me, [but not others](https://github.com/keepassxreboot/keepassxc/issues/6502#issuecomment-857690788)
							- [[2021-10-01 Friday]]
							  collapsed:: true
								- Trying to log out from Wayland then log back into X11 makes CPU usage nearly 100% from Yakuake, ((63a9ade4-acd5-44f9-9166-2c1393865f7a)) etc in X11 session
								- KDocker doesn't work on Wayland. It stays as a 12% CPU background process that can't be terminated via KSysGuard
								- GPU hot unplug not yet ready. Makes OS unresponsive after 1 plug-unplug cycle
						- # Apps which don't support native Wayland (uses XWayland)
						  id:: 67103287-1a16-4c4e-b8ac-db2ba4fa382b
						  collapsed:: true
							- ## [Electron](https://www.electronjs.org/)
							  id:: 679f816f-38d2-4544-a0b0-91fbe1e533c9
							  Powered by ((649b140b-1732-4689-9331-10b5b97e5e5e))
								- Pros/Cons
									- Pros
										-
									- Cons
										- Hardware Video Acceleration not enabled
											- Wayland: ((671036e7-2fdc-49a8-9b27-b2f3516c622d))
											- [They've disabled Chromium's video acceleration?](https://github.com/electron/electron/issues/32317#issuecomment-2111358070)
											- [Zero GPU acceleration on Wayland, but is on XWayland](https://github.com/electron/electron/issues/36633#issuecomment-2579058488)
												- Try these flags on XWayland, Electron v22
												  collapsed:: true
													- ```
													  --ignore-gpu-blocklist
													  --enable-gpu-rasterization
													  --enable-gpu
													  --enable-unsafe-webgpu
													  --enable-features=WebRTCPipeWireCapturer,Vulkan,UseSkiaRenderer,VaapiVideoDecoder,CanvasOopRasterization,VaapiVideoEncoder,RawDraw
													  --disable-features=UseSkiaRenderer,UseChromeOSDirectVideoDecoder
													  --enable-zero-copy
													  --enable-oop-rasterization
													  --enable-raw-draw
													  --enable-accelerated-mjpeg-decode
													  --enable-accelerated-video 
													  --enable-native-gpu-memory-buffers
													  --use-vulkan
													  --use-gl=egl
													  --ozone-platform-hint=auto
													  ```
														- `flatpak run --socket=wayland io.freetubeapp.FreeTube --ignore-gpu-blocklist --enable-gpu-rasterization --enable-gpu --enable-unsafe-webgpu --enable-features=WebRTCPipeWireCapturer,Vulkan,UseSkiaRenderer,VaapiVideoDecoder,CanvasOopRasterization,VaapiVideoEncoder,RawDraw,UseOzonePlatform --disable-features=UseSkiaRenderer,UseChromeOSDirectVideoDecoder --enable-zero-copy --enable-oop-rasterization --enable-raw-draw --enable-accelerated-mjpeg-decode --enable-accelerated-video --enable-native-gpu-memory-buffers --use-vulkan --use-gl=egl --ozone-platform=wayland`
														- didnt help with freetube [[2025-02-08 Saturday]]
											- ### Depends on
												- ((649b140b-1732-4689-9331-10b5b97e5e5e)) : ((6716aed4-2e44-439c-b17f-da59a637f336))
										- [Electron doesn't support Wayland by default](https://github.com/electron/electron/issues/41551#issuecomment-3260177362)
										  id:: 671036e7-2fdc-49a8-9b27-b2f3516c622d
											- [Chromium 141 and up uses Wayland/Ozone by default](https://issues.chromium.org/issues/40083534#comment593)
										- [Daniel Micay summary](https://github.com/secureblue/secureblue/issues/193#issuecomment-1953323680)
										  collapsed:: true
											- [Unlike the WebView model used in Android, Windows](https://github.com/secureblue/secureblue/issues/193#issuecomment-1953323680) the embedded browser is rarely up-to-date and secure
											- Since Android provides a standard OS WebView that's kept up-to-date, very few apps bundle their own web browser engine. That means they get an updated one that the OS is able to harden. On GrapheneOS, that allows us to use CFI, MTE, etc. for the web rendering engine used by all these apps. Chromium doesn't really use the system malloc in practice so hardened\_malloc doesn't really do much for it. Android WebView currently doesn't have fine-grained isolation but it does at least provide an overall content sandbox separate from the app itself comparable to the browser sandbox. It doesn't currently sandbox separate content used simultaneously by the app in separate OS sandboxes but it's planned upstream and we can enable it early.
											- Windows has WebView2 based on Edge (Chromium) but it's relatively new and would mainly be used by new Windows-only applications. Most of these desktop apps are using web content to be cross-platform across Windows, macOS and desktop Linux so they aren't going to use an OS specific WebView API. There's not going to be cooperation on this between Windows and macOS or even across desktop Linux distributions. Desktop Linux alone has a bunch of fragmented options, mostly badly maintained and they repeatedly get replaced in backwards incompatible ways. Android has always had the same WebView API evolving and gaining new features which became based on proper Chromium shipped with the OS browser over a decade ago.
											- Electron massively rolls back Chromium security, breaks the sandbox and is a regularly backwards incompatible library used by applications so there's a huge mess created by it. Android WebView preserves compatibility to the same extent as Chromium does for the web, which is to say that essentially nothing breaks even after a decade if you don't do anything stupid. Rare apps do stupid enough stuff to break on Chromium updates, but it's generally easy for them to fix it. It's essentially just the same as the web since the Android WebView adds very minimal API surface beyond standard Chromium. It has a tiny set of APIs for configuring it, executing JS, adding JavaScript interfaces from Java/Kotlin, intercepting network requests to replace them and do content filtering along with interoperability with APK assets (asset:), content providers (content:) and direct file access (file:). It's dramatically simpler than Electron since it makes no attempt to provide a full application API. It's only a sandboxed web content renderer with interoperability with the rest of the app code. Electron is for writing a whole application while the WebView is for putting web content in an app, although you can provide all the APIs you need to the WebView and write your whole app in it. Still, that avoids the WebView having complex APIs since the developer and the libraries they use would be defining any of that. Electron is a huge mess, as are most alternatives. WebView2 on Windows is reasonable, if only it wasn't Windows-specific and stuff actually used it.
											- Electron also breaks Content-Security-Policy and other things. Signal being an Electron app without Trusted Types turns it into a huge mess of XSS vulnerabilities.
										- [avoid](https://blog.sekoia.io/luckymouse-uses-a-backdoored-electron-app-to-target-macos/) Electron [_based_](https://www.malwarebytes.com/blog/news/2022/08/a-vulnerability-was-found-in-electron-which-is-what-drives-discord-spotify-and-microsoft-teams) [programs](https://blog.doyensec.com/2022/09/27/electron-api-default-permissions.html) from [GitHub - beerisgood/Security-link-collection: a collection of links on various security topics](https://github.com/beerisgood/Security-link-collection)
										- [Flatpak Electron App Throws Error With \`libhardened\_malloc.so\` · Issue #193 · secureblue/secureblue · GitHub](https://github.com/secureblue/secureblue/issues/193#issuecomment-1953323680) , [Flatpak Electron App Throws Error With \`libhardened\_malloc.so\` · Issue #193 · secureblue/secureblue · GitHub](https://github.com/secureblue/secureblue/issues/193#issuecomment-1953324629) by GrapheneOS dev and [Wider Implications for Electron Apps](https://blodeuweddlabs.com/news/#wider-implications-for-electron-apps).
									- Unclear
										- Can force Wayland mode with these, but they have similar bugs
									- Comparisons
								- ### My Electron apps
									- VSCode
										- [Drag and drop does not work in Wayland · Issue #156723 · microsoft/vscode · GitHub](https://github.com/microsoft/vscode/issues/156723#issuecomment-2315986971)
										- [VS Code should default to Wayland when possible · Issue #207033 · microsoft/vscode · GitHub](https://github.com/microsoft/vscode/issues/207033#issuecomment-2408592124)
										- [Crash when rebuilding application menu on wayland · Issue #184124 · microsoft/vscode · GitHub](https://github.com/microsoft/vscode/issues/184124#issuecomment-2262492936)
									- ((631fa97e-a0a9-406c-b7b9-20536d421090))
									- [Mullvad-VPN](https://github.com/mullvad/mullvadvpn-app/issues/3062#issuecomment-2106231792)
									- ((6313458c-20f9-43f5-be52-44845eb02203))
									- ((65aba288-090d-4b44-9d4a-c2caef5f97ef)) - when closing to tray forgets which window to open to
									- ((6312a076-eb26-4bd5-a669-ea0a50d06668)) : ((663b24fb-fa04-4f84-8b19-1743340928aa))
									- [[Logseq]] : embedded MP4 player the progress bar doesn't do anything when clicked
									- ((663b24fb-0338-4d42-8e5a-7febac0fe00a))
									- ((663b24fb-d7c8-4b7d-86f4-056243f4afb7))
							- ((644c0bb5-76e1-4489-9fa4-22a803fa3c9d)) : ((671035f4-7713-4ae1-af90-84419d474ea0))
							-
						- # Documentation
							- Install it on 22.04
							  `sudo apt install plasma-workspace-wayland`
							- Command to detect which running applications are using XWayland (they're X11-based)
							  `xlsclients`
								- Warning: all X11 apps have access to each other
							- [Fixing apps that have generic app icons (Wayland or Xorg logo)](https://www.reddit.com/r/kde/comments/1cil6gw/how_do_i_fix_these_generic_icons_on_the_panel/)
							  collapsed:: true
								- ![image.png](../assets/image_1715684776241_0.png)
								- With the app focused hit alt+f3 then More Actions->Configure Special Application Settings->Add Property->Desktop file name, apply initially, insert the correct .desktop file name of the app (you can look it up in `/usr/share/applications`)
									- Had the same issue for Obsidian that is a flatpak app and found the path from the main menu, right click on the icon > Edit application... and copying the path from the field Points to,
									- For Flatpak apps it uses their Flatpak codename e.g. `com.calibre_ebook.calibre`
								- Eventually [xdg_toplevel_icon](https://gitlab.freedesktop.org/wayland/wayland-protocols/-/merge_requests/269) could help with some of this but for now it's intended behaviour
									- If application does not have a .desktop file (with included path icon) attached, generic wayland icon will be used.
									- As was said before, set .desktop file for each application with such issue. Yes, for each of them.
							- Protocols
								- [Issues · wayland / wayland-protocols · GitLab](https://gitlab.freedesktop.org/wayland/wayland-protocols/-/issues/?sort=popularity&state=opened&first_page_size=20)
								- [Issues · wlroots / wlr-protocols · GitLab](https://gitlab.freedesktop.org/wlroots/wlr-protocols/-/issues)
								- [GitHub · Where software is built](https://github.com/flatpak/xdg-desktop-portal/issues?q=state%3Aopen%20label%3A%22new%20portals%22%20sort%3Areactions-desc)
								-
					- # Multi-app keybindings
						- `Home` = Go to Beginning of Line
						- `End` = Go to End of Line
						- `ALT + Left` = Go back to previous page (works in [[Logseq]], ((63134593-906c-43b5-96fe-33dc2c34fda4)), ((651d714a-c80a-4289-a919-478910c779da)) )
						- `ALT + Right` = Go forwards to next page (works in [[Logseq]], ((63134593-906c-43b5-96fe-33dc2c34fda4)), ((651d714a-c80a-4289-a919-478910c779da)) )
						- `CTRL + Left` = Go one Word to the Left
						- `CTRL + Right` = Go one Word to the Right
						- `CTRL + Backspace` = Delete Word to the Left
						  id:: 6341f570-d2a7-474e-87d6-88e519cf2c04
						- `CTRL + Del` = Delete Word to the Right
						  id:: 6341f578-6891-4713-b84a-068480b8205c
						- `CTRL + TAB` = Go to the next tab (works on ((63134593-906c-43b5-96fe-33dc2c34fda4)) + [[Logseq]] + ((651d714a-c80a-4289-a919-478910c779da)) + ((6312a076-eb26-4bd5-a669-ea0a50d06668)))
						  id:: 6320850b-1f87-4653-96d9-fedd85d0201d
						- `CTRL + SHIFT + TAB` = Go to the previous tab (works on ((63134593-906c-43b5-96fe-33dc2c34fda4)) + [[Logseq]] + ((651d714a-c80a-4289-a919-478910c779da)) + ((6312a076-eb26-4bd5-a669-ea0a50d06668)))
						  id:: 6320852a-625c-4205-b117-af91259e32f8
						- `MMB` = open link in new tab 
						  id:: 632d7e38-16db-431e-8c5d-7f9528e3c348
						  collapsed:: true
						  e.g.  ((63134593-906c-43b5-96fe-33dc2c34fda4)) + [[Logseq]] + ((651d714a-c80a-4289-a919-478910c779da)) )
							- From logseq-plugin-tabs [PR](https://github.com/pengx17/logseq-plugin-tabs/pull/57)
						- `CTRL + SHIFT + P` = Toggle command palette
						  id:: 6341d63d-cb12-465e-b936-e7efac4abf91
						- `CTRL + K` = focus the search bar 
						  id:: 63c286db-7b85-4388-a777-eece034f658e
						  collapsed:: true
						  e.g.  ((63134593-906c-43b5-96fe-33dc2c34fda4)) + [[Logseq]] + ((651d714a-c80a-4289-a919-478910c779da)) )
							- [[Logseq]] : ((6320977a-e2c4-481a-aadb-30f3aa088d8a))
						- `F1` = toggle left sidebar (works in ((63134593-906c-43b5-96fe-33dc2c34fda4)) + [[Logseq]])
						  id:: 63c70226-b36a-4c81-aad3-8bbcccd3e003
						- `F2` = toggle right sidebar (works in ((63134593-906c-43b5-96fe-33dc2c34fda4)) + [[Logseq]])
						  id:: 63c702a2-ba5c-4995-9e39-eef0339e04f6
						- ## Similar bindings
							- Moving lines up/down
								- [[Logseq]] : ((63209777-2774-4345-8a71-d508db2c73ab))
									- Related:
										- ((644c0a6f-b1f5-483d-bc22-bc8d2c4dfc6b))
										- ((67375e40-daa9-4cf0-9544-02fe5cedaa25)) / ((67375e40-c1ab-4c16-a1b4-45e1a1774ef9))
								- ((63209272-1088-4824-a762-4ac7ded04b0a)) : ((633a1738-6a4c-414b-bfda-1e537b0ba941)) : ((6341ad83-4cb3-4fca-8272-f413353faa9c))
								- ((65b7e7af-d429-4b93-bb1a-33dc05bf5400)) : ((67ea799e-1fde-4472-a12e-302fab292bba)) : ((6808e225-7ad9-4c22-8c39-6c902d23fe65))
							- Moving blocks up/down
								- [[Logseq]] : ((63209777-2774-4345-8a71-d508db2c73ab)) : ((644c0a6f-b1f5-483d-bc22-bc8d2c4dfc6b))
								- ((65b7e7af-d429-4b93-bb1a-33dc05bf5400)) : ((67ea799e-1fde-4472-a12e-302fab292bba)) : ((6808dfcf-8779-4e55-9697-f04fad11de80))
						- ## Apps with ((634d22db-89bb-432b-8dcf-776e2bd185ba)) motions
						  id:: 634bf00a-932c-4a43-8a7c-c822f175ffed
							- ### Compatible apps
								- ((63209272-1088-4824-a762-4ac7ded04b0a)) : ((663b63f5-e0ab-40c3-af11-e6d5bd63fe4a))
								- ((63134593-906c-43b5-96fe-33dc2c34fda4)) : ((633b7517-a43c-40f8-9781-22fd074423d6))
								  collapsed:: true
									- {{embed ((634bd2e2-ed05-45a7-b26e-ece8577c0ca7))}}
								- [[Logseq]] : ((634bcf60-7cb2-4efc-bc34-0c95ad9b2119))
								  collapsed:: true
									- {{embed ((634bcf60-7cb2-4efc-bc34-0c95ad9b2119))}}
								- ((634bc1d7-6c8e-4cb1-8b72-5ebdbfb847ee)) - spacemacs, evil mode
								- [[Programming]] - ((67376799-dbaf-405a-9faf-fe9780f339a2))
								- #### OS-level
									- *FOSS*
										- [GitHub - mjrusso/scoot: Keyboard-driven MacOS cursor actuator](https://github.com/mjrusso/scoot) MacOS-only
										- [GitHub - phil294/vimium-everywhere: OS-wide Keyboard navigation for Linux and Windows](https://github.com/phil294/vimium-everywhere) - Alpha
									- Proprietary
										- [Shortcat: Universal command palette for your Mac | Shortcat](https://shortcat.app/) - proprietary, MacOS
										- [Homerow — Keyboard shortcuts for every button in macOS](https://homerow.app/) - proprietary, MacOS
										- [Superkey](https://superkey.app/) - proprietary, MacOS
						- ## Divergent keybindings
							- `CTRL + L`
								- ((633b7517-4795-4b17-a404-8d3b9e8a0854)) ( ((63134593-906c-43b5-96fe-33dc2c34fda4)) )
								- ((63209272-1088-4824-a762-4ac7ded04b0a)) - Continue/GitHub Copilot. Add context to chat
								- Add `[]()` - Logseq
					- # All apps
						- [[PC]] : ((6318fc57-db8a-441f-af0e-c8392241a76b))
						- [[Terminal]] : ((6341d9ab-4595-445a-8b0b-ec20e3648122))
						  collapsed:: true
							- {{embed ((6341d9ab-4595-445a-8b0b-ec20e3648122))}}
						- ((65a98a50-b4e8-41f7-9959-35465cbe3150)) ((634204fc-aae9-418e-8112-c0353c355afe)) : ((65a98a50-b0c3-487f-a2e6-6223543bf21a))
						  id:: 6342033d-bf93-4d66-8412-c03bf137c32b
						  collapsed:: true
							- {{embed ((65a98a50-b0c3-487f-a2e6-6223543bf21a))}}
						- ((63134593-906c-43b5-96fe-33dc2c34fda4)) (and extensions) : ((62e790b7-007a-46d8-a34e-a69ef5da68bb))
						  collapsed:: true
							- {{embed ((62e790b7-007a-46d8-a34e-a69ef5da68bb))}}
							  id:: 6341c0c6-e953-4a26-ab6c-07291827ce4e
						- [[Logseq]] : ((63209777-2774-4345-8a71-d508db2c73ab))
						  id:: 6341c0c6-d780-4785-8a07-6b76942f5d7e
						  collapsed:: true
							- {{embed ((63209777-2774-4345-8a71-d508db2c73ab))}}
						- ((63209272-1088-4824-a762-4ac7ded04b0a)) : [Keybindings](((633a1738-6a4c-414b-bfda-1e537b0ba941)))
						  collapsed:: true
							- {{embed ((633a1738-6a4c-414b-bfda-1e537b0ba941))}}
							  id:: 633aed45-2db6-4ae7-aa93-06751f187c22
						- ((6313458c-20f9-43f5-be52-44845eb02203)) : ((63421410-cd54-43f0-81c0-6554f4c4f943))
						  collapsed:: true
							- {{embed ((63421410-cd54-43f0-81c0-6554f4c4f943))}}
						- ((630f9721-3e4b-42e7-a716-c0febefff0fd)) : ((63421551-f589-49bc-a334-7e0abe64af1d))
						  id:: 6341e913-8b34-44a5-92ce-61cbb79f2aac
						  collapsed:: true
							- {{embed ((63421551-f589-49bc-a334-7e0abe64af1d))}}
						- ((63c0feef-aa24-487d-93ea-be2c858e34b0)) : ((63c30002-cead-4ff1-9bf4-64d664568a22))
						  collapsed:: true
							- {{embed ((63c30002-cead-4ff1-9bf4-64d664568a22))}}
						- ((63ad9567-857c-4b16-8292-abf0e85a0326)) : ((65fc0a34-425c-40e2-a8ef-ee1aaa9f519d))
							- {{embed ((65fc0a34-425c-40e2-a8ef-ee1aaa9f519d))}}
						- [[Terminal]] : [tmux](((65c9f52b-520f-4dc8-84b0-86d5f96590a8))) : ((673767a8-951c-4fb9-83e8-33c6688a9716))
						- Game overlays
						  collapsed:: true
							- `SHIFT + TAB` = Steam
							- `CTRL + G` = ((649b1463-b077-434e-a501-df6e30d6c4fb))
							- `SHIFT + F1` = Origin (Star Wars Battlefront 2)
							- `SHIFT + F2` = Ubisoft e.g. Tom Clancy's Ghost Recon Breakpoint
						- *Notable extensions*
							- ((634bf00a-932c-4a43-8a7c-c822f175ffed))
					- [Learning Resources]
						- [GitHub - RedBearAK/toshy: Keymapper config to make Linux work like a 'Tosh!](https://github.com/RedBearAK/toshy)
						-
					- # Related:
					  id:: 633b7503-7a68-443d-854c-8fc25baba607
						- ((632092d6-c991-4442-b3dc-38ae5801eb51))
						- ((631fa957-a66f-401b-b7da-4d1545b8f298))
						  #Productivity
				- KDE desktop setup
				  collapsed:: true
				  id:: 639cbd5d-ac99-4dc2-baf6-53e0adfde5b0
					- _Bottom panel_
						- Right-click the bottom panel > Alternatives > "Icons-only Task Manager" for mini app icons
						- Right-click the taskbar > configure Task Manger > uncheck Mark applications that play audio
							- To remove the mute/audio button from taskbar applications in KDE
						- Right-click > Panel Options > Add Widget
							- System Load Viewer
							- "Show Desktop" button
							- Digital Clock right-click > Configure > Show date
						- Add a Pager applet for Workspaces (Virtual Desktops)
							- CTRL + F2 to switch to desktop 2
						- Next change the transition
							- Desktop Effect and search for the Slide effect
					- _Optional_
						- [FancyTasks](https://github.com/alexankitty/FancyTasks/)
						  collapsed:: true
							- Links
								- Here's a link to the project: https://github.com/alexankitty/FancyTasks/
								- This can be grabbed off of the KDE store as well https://store.kde.org/p/1928026
								- https://teddit.froth.zone/r/kde/comments/yggk5n/fancy_tasks_update/
							- Pros
								- ((635e3160-f082-4227-aec1-f244972cb2b3)) makes it clear when a program is in the background vs minimised
								- ((635e315c-aca4-4b89-b051-016bacd198b6)) makes it clearer when a program is selected
							- Documentation
							- To setup
								- Right-click the Task Manager applet (shows icons for open programs)
								- Configure Task Manager
								- Appearance
									- Colorize buttons
									  id:: 635e315c-aca4-4b89-b051-016bacd198b6
								- Indicators
								  id:: 635e3160-f082-4227-aec1-f244972cb2b3
									- Enabled
									- Minimize options: Desaturate
									  id:: 635e32a7-5fa9-44e0-a85a-4bb44dd89bfd
						- Use Latte Dock (MacOS-like Task Manager)
						  collapsed:: true
							- _Cons_
								- Having the system tray, clock etc moved to top looks weird with the way the new Firefox allows hiding the titlebar
								  http://i.imgur.com/wY88ep2.png
									- https://i.stack.imgur.com/a6F9W.png
							- sudo apt install latte-dock
							-
				- Dolphin sidebar setup
				  collapsed:: true
					- _Control > Configure Dolphin_
						- View > Show full path inside location bar
					- _Places sidebar_
						- Right-click "Search for" > Hide section
						- Drag-and-drop some Home folders to there - Pictures Videos, Docs
				- Night Shift Control setup
				  collapsed:: true
					- _Set to _
						- Sunrise to sunset
						- 3400K
					- {Archive}
						- Redshift
						  sudo apt install redshift-gtk
							- [https://github.com/jonls/redshift](https://github.com/jonls/redshift)
							- _{Archive}_
								- Old notes
									- $ sudo apt-get install redshift redshift-gtk plasma-applet-redshift-control
									- qml-module-qtgraphicaleffects
									- sudo apt-get install qt5-graphicaleffects
									- sudo apt-get install plasma-widget-redshift=0.6.1-0ubuntu2
								- _Colour temperature modifier to reduce blue light _
								  f.lux / Redshift (alternative to LightBulb)
									- flux for Linux
										- Doesn't work on 18.04?
										  https://github.com/xflux-gui/fluxgui/issues/102#issuecomment-423400465
										- https://github.com/xflux-gui/fluxgui
									- but http://askubuntu.com/questions/493507/flux-for-ubuntu-14-04-possible
									- LightBulb for Windows
										- https://github.com/Tyrrrz/LightBulb
										- With v4 f.lux is now collecting anonymous usage data and it's opt-out. (self.privacy)
											- No mention of it in their release change log for v4.47, seems like a shifty practice to do this: https://justgetflux.com/news/pages/v4/bigupdate/?v=4.47?v=4.47
											- By default it's checked: https://i.imgur.com/pF6S9wt.png
				- Config VLC
				  collapsed:: true
				  id:: 635037c4-5ca8-4147-965f-91bf8c03652a
					- View > select Status Bar (enables quick changing playback speed)
					- Activate extensions
						- ```bash
						  ~/.local/share/vlc/lua/extensions/
						  ```
						- [Moments tracker](https://addons.videolan.org/p/1848670/)
						  id:: 635d684c-42a4-4955-a29a-0c6f4fbceebd
						  collapsed:: true
							- Documentation
								- ```
								  ~/.local/share/vlc/lua/extensions/Moments-tracker-rev-2022-11f.lua
								  ```
								- Database here
								  ```bash
								  ~/.local/share/vlc/moments_tracker.txt
								  ```
							- Manual
								- MOMENTS TRACKER REVISITED  -  November 2022  - version 2022_11f
									- This extension is a fully reworked and extended version of the original "Moments Tracker" by ARahman Rashed (https://addons.videolan.org/p/1154020/).
									  The extension was designed to save "moments" - ie freely named bookmarks in a currently playing medium - for later reviews.
									  
									  This revisited version adds functions and displays :
									- time line ordered display of moments, exportable to a text file
									- options at medium level (Selection of medium name / New name / Rename / Duplicate / Delete)
									- freedom to close the extension window / reactivate the extension (VLC Menu/View)
									  
									  The revisited extension keeps the internal structure of the original moments_tracker.txt database file. 
									  The moments_tracker.txt file is created by the extension, as a database containing your registered media names with their moments and checkpoints.
								- At MOMENT LEVEL
									- Capturing a new moment should be done "in flight" by clicking on the "Capture Moment" button. Use your mouse on the VLC's time bar to find a position just before the target. Manually stopping VLC's display beforehand is useless in this procedure, the click on the "Capture Moment" button defines the time position of the new moment.
									- The checkpoint! button immediately stores a position in the currently playing medium without having to name it as a moment. For example, this checkpoint feature offers a convenient way to mark the position where you would tomorrow resume your watching a long video. The display shows the date and time of creation of the checkpoint, then its position in the medium, in raw value and percentage.
									- The "Export Moments to Memos.txt" button saves the current medium name and its moments into the Memos.txt file, to be found in the same directory as the moments_tracker.txt file. This output provides a workable text structure for additions of comments and other uses.
									  The extension's window may be incidentaly moved to the background by your OS, for example as a consequence of a new distribution of screen space after redimensioning operations. But the extension will remain active until you decide to close its window or uncheck it in VLC's View menu. When the extension "disappears" in the background, you can get it back on the foreground by using the right key combination of your OS to recall its window.       
									   
									  Note. The positions of moments and checkpoints are internally stored in the moments_tracker.txt file as percentages of the current medium duration but they are displayed as hours:minutes:seconds, from 00:00:00 to medium duration. An alternative display is available in "per thousands" of medium duration, from 000 to 999. You get it by modifying the first line of global variables in the extension LUA program file itself to read "minsec_display=0" instead of "minsec_display=1" and save the LUA file - this setting has absolutely no impact on the data storage, you may change it at will, the positions of moments are internally stored at much higher levels of precision anyway.
								- AT MEDIUM LEVEL
									- When a playing medium was detected by VLC, you can easily skip the medium level - the "Medium selection /change" window - by clicking on the first action button "Start with VLC detected name".
									- But why should you ignore your freedom of control at medium level ? There are good reasons for this greater freedom. The most obvious one is the medium name produced by VLC's automatic detection : this name will never be as specific as you may wish.
									- What medium name ? It is advisable to precisely identify each video or audio item, especially when it is an element in a structured set.
									  For example in DVDs of a TV series, the video item is a chapter or a bonus and its identification requires a long name : series name--season nr--dvd nr--episode nr/chapter nr (or dvd bonus nr)--episode/chapter supplement nr. In these situations, you should definitely never get on with the automatically detected medium name by VLC.
									- The available options at medium level call for some kind of self discipline when selecting a medium, even more when naming, renaming or deleting a medium. The last three options, Rename, Duplicate and Delete, do not require a currently displayed medium by VLC, they may be used in a quiet environment. But the other options do require a currently running medium in VLC to display the moments associated with the chosen medium.
									- Note. The options at medium level (possibly in combination with the alternative display of moments positions) may be used to compare media of the same kind, for example by applying the moments of a "model" medium to other similar media. You can easily create a model medium as a copy of an existing medium in the database with the Duplicate button, then rename it properly.
									- Note. When a medium or moment has the focus in a list, any input field (for a new name or a substitute name) is prefilled with the focussed name. This is meant to facilitate the input of names after existing ones.
									- Note. When no playing medium was detected by VLC, the media window opens with 3 NOP buttons replacing the actions requiring a currently playing medium.
								- MORE THAN A TOY TOOL ?
									- The revisited extension adds some key features for extended uses. You will certainly imagine more than the suggested ones in this manual.
									- Instead of stockpiling moments into one unique moments_tracker file, consider maintaining dedicated moments_tracker files per primary category in your collection of media.
									  You might envisage the creation of an index of your (virtual) collection of media, with comments, screen captures.. moments_tracker files... per category, author, year of publication - whatever - this kind of project would possibly eventually require the use of a pim or spreadsheet or database software, but starting with a regular portable word processing / publishing software would probably meet most of your needs.
								- INSTALLATION AND ACTIVATION OF THE EXTENSION
									- Windows
									  You should install the extension here : installation_directory_of_VLC\lua\extensions\moments_tracker_rev_xxx.lua (after deleting older moments_tracker_rev_xx.lua files)
									  The database file will be located here : your_personal_directory_in_Documents_and_Settings\Application Data\vlc\moments_tracker.txt aka your_personal_directory_in_Users\AppData\Roaming\vlc\moments_tracker.txt (will be created by the extension if not existing)
									- Linux
									  You should intall the extension here : ~/.local/share/vlc/lua/extensions/moments_tracker_rev_xxx.lua (after deleting older moments_tracker_rev_xx.lua files)
									  The database file will be located here : ~/.local/share/vlc/moments_tracker.txt (will be created by the extension if not existing)
									- To activate the extension, open the View submenu in the VLC menu and click on the extension name. The extension can be closed directly by closing its windows then reactivated at will.
								- LMITS OF USE
									- MEDIUM and MOMENTS
									  This extension is not for live streams, as the positions of the stored moments depend on the total duration of the medium when played by VLC at normal speed.
									  If you define moments in a medium in a view to edit it, for example to cut off / reorganize segments, the definition of moments in the original medium will be of great help in the preparation of your project. But you should consider the result of your work as a new medium, since the moments defined in the original medium will have lost their meanings : different total duration, overall reorganization after cut and paste operations, etc.
									- NEW MEDIUM. Note that a new medium will NOT be recorded in the database file (moments_tracker.txt) UNTIL you define a first checkpoint or moment. Only one checkpoint is recorded per medium, by default at the position of the first defined moment.
									  MEDIUM DELETION. The Delete button at medium level deletes a medium out of the database. There is no automatic procedure to recreate a deleted medium and recover its moments but it can be done manually. A copy of the full database entry is saved in a moments_tracker_deletelog.txt file in the same directory as the moments_tracker.txt database file, so that it remains possible to recreate a deleted medium entry by copy & paste from the log file to the database file - carefully, with no added void lines even at the end of the database file ! The names of the deleted media in the log file are automatically time stamped to avoid unsolvable conflicts in the database after such copy & paste operations.
									- NAMING RULES. A medium or moment name must have at least 2 characters (not including leading and trailing blanks, that will be cut off anyway), AND it should NEVER include any ~ (tilde) character.
									  As regards the medium file names that are automatically provided by VLC, the extension will replace all ~ characters in these names with _ characters. This is to preserve the regular access to the data in the database, as the ~ character is used to delimit the data fields. In the global variables of the LUA program file, there is a declaration of the maximum acceptable length of newly created moments names, you can easily modify this maximum value if really needed.
									- PORTABILITY. Portability issues are created by changes of language, timezone, OS. 
									  The extension program itself is more portable than the VLC program, there is only one LUA program for all VLC versions. But the data in the database file moments_tracker.txt are created as outputs of names and numbers in a text file by the LUA implementation of VLC on your current computer system. The extension takes care of the main various internal representations of fractional numbers, especially as regards the "comma" versus "point" separator, but cannot cope with the various character encoding conventions in names. At least, a direct copy of the moments_tracker.txt file from another system should be useable on the new environment.
									- VLC VERSIONS. The extension supports VLC versions 2.x, 3.x, 4.x... 
									  Version 4 comes with a new set of specific instructions to query/control the VLC status in a LUA program. The extension reads the VLC version in the VLC settings file and selects the instructions set accordingly.
									  TRANSITION TO VLC VERSIONS 4+. This paragraph addresses the specific case of a transition from version 3 (or older). The transition may fail when the VLC settings file is not upgraded by the new installation : the extension is no longer able to detect a playing medium in VLC ! This may happen if you installed the new VLC version as an upgrade of an older version AND selected or accepted the option to keep the existing VLC settings - thus NOT upgrading the version number in these settings. Solution is by manually setting the second global variable in the extension LUA program file itself to vlc_version=4 instead of vlc_version=0 (do not forget to save the modified LUA file). Another solution is by manually actualize the version number in the vlcrc settings file.
									- VLC dev 4 (June 2022) is not extension friendly. You should never quit VLC before having closed or deactivated the extension, otherwise the extension will not be able to save changes in its database. Moreover, after each creation of a new moment, you have to manually instruct VLC to resume playing. Hopefully, these awkward features will be corrected in the future.
					- ((635d818c-e7b6-4619-ac37-e00d4cf479d4))
				- Configure static IP addresses?
				  collapsed:: true
					- Why
						- Allows accessing Calibre content server on mobile through the same bookmark
						- Nah not worth the time to learn this
					- How to
						- Address (my new static one)
						  192.168.0.23
						- Netmask
						  255.255.255.0
						- Gateway (router IP)
						  192.168.0.1
				- Remove VSCode from directory file assocation
				  collapsed:: true
					- Had an issue where VSCode would try to open directories when I'd use apps like Lutris, MultiMC to "open folder"
					- Had to open `File Associations` in KDE, then search for "inode/directory" and remove VSCode as an associated app, even despite it already being lowest priority
				- Add a simultanous audio output sink for ((63a9adc8-6bc0-4ac7-8df3-f879b95211b5))
				  id:: 62e8e1bc-0aa6-4208-b544-398a84c9f9a3
				  collapsed:: true
				  AKA combined audio / combined ((63a9adc8-6bc0-4ac7-8df3-f879b95211b5))
					- Temporary
						- Run:
							- `pactl load-module module-combine-sink`
							- [source](https://askubuntu.com/questions/1379376/how-to-achieve-automated-simultaneous-outputs-with-pipewire)
					- Permanent:
						- `nano ~/.profile`
							- ```
							  #PipeWire/Pulse create simultaneous output sink
							  pactl load-module module-combine-sink
							  pactl set-default-sink combined
							  ```
						- {Archive}
							- This didn't work
							  collapsed:: true
								- 1
								  source:: [https://askubuntu.com/questions/1379376/how-to-achieve-automated-simultaneous-outputs-with-pipewire](https://askubuntu.com/questions/1379376/how-to-achieve-automated-simultaneous-outputs-with-pipewire)
									- `cp /usr/share/pipewire/pipewire-pulse.conf ~/.config/pipewire/pipewire-pulse.conf`
									- `nano ~/.config/pipewire/pipewire-pulse.conf`
									- add this to the end:
									  ```
									  context.exec = [
									      { path = "pactl"  args = "module-switch-on-connect" }
									  ]
									  ```
										- Didn't work, try this
										  ```
										  context.exec = [
										      { path = "pactl"  args = "module-combine-sink" }
										  ]
										  ```
								- 2
									- crontab (user or system)
										- `@reboot pactl load-module module-combine-sink`
										- `@reboot pactl set-default-sink combined`
				- ((63bab109-b971-4abe-a17f-cde278bd69d7))
				- ### Tasks even needed to be done if copying `/home` into a new install
					- Install Nix + Home-Manager
					- ((63a873fd-893d-4ed7-ae5b-e27945e68230))
					- Remove ((63ad9567-8df0-4f60-ab52-545451251156))
					- Setup VeraCrypt
					  collapsed:: true
						- Run the GUI installer that's in /Documents/ESSENTIALS/Programs/veracrypt/
						- VeraCrpt > Preferences > System Integration > Open Explorer window
						- Veracrypt > Settings > Mount Options > umask=022 (this changes the permissions on files within the container so that CrashPlan can actually back them up)
					- `sudo apt remove`
					  collapsed:: true
						- ```
						  sudo apt remove thunderbird
						  ```
					- Setting `kdewallet` again for Vorta
					  collapsed:: true
						- `mv ~/.local/share/kwalletd ~/.local/share/kwalletd-bak` = Move old kdewallet files to a backup dir
						  In Vorta unlink one repo,
						- Add Existing Repository >
							- then in password manager look for the repo address + borg password
							- Advanced > SSH Key > `boss-XPS-9380`
						- Create `kdewallet` with Blowfish encryption
					- Enable hibernation mode and swap space
					  collapsed:: true
						- _Note: Sleep = Suspend _
						- How to setup swap space
						  id:: 65a98a51-aea7-48dc-9fca-1e93b25c77a4
							- Creating swap space
							  id:: 65a98a51-5241-4ae6-920e-79c624ff113c
								- #+BEGIN_WARNING
								  This is unencrypted swap
								  #+END_WARNING
								- `sudo swapon --show`
								  Detect swap file. May need to run from root directory
									- Output example
										- Filename                Type        Size    Used    Priority
										- /swapfile                               file        1048572 0   -1
										- `cat /proc/swaps`
										  Alternate
								- `sudo swapoff /swapfile` = turn off any existing swapfile
								- `sudo fallocate -l 100G /swapfile`
									- Increase size of swap file to allow for 1.5x size of RAM
								- `sudo mkswap /swapfile`
									- _Output example_
										- Setting up swapspace version 1, size = 4194300 KiB
										- no label, UUID=fb0aadaf-b52f-4928-b57f-c60ef7a0bd49
								- `chmod 0600 /swapfile`
								- `sudo swapon /swapfile`
								- `sudo swapon --show`
								  /swapfile                               file            20971516        0       -2
							- Making the Swap File Permanent
								- Backup the fstab file
								  `sudo cp /etc/fstab /etc/fstab.bak`
								- Add swap file to end of /etc/fstab
								  `echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab`
							- Adjusting the swappiness property
							  collapsed:: true
								- Info
									- The swappiness parameter configures how often your system swaps data out of RAM to the swap space. This is a value between 0 and 100 that represents a percentage.
									- With values close to zero, the kernel will not swap data to the disk unless absolutely necessary. Remember, interactions with the swap file are “expensive” in that they take a lot longer than interactions with RAM and they can cause a significant reduction in performance. Telling the system not to rely on the swap much will generally make your system faster.
									- Values that are closer to 100 will try to put more data into swap in an effort to keep more RAM space free. Depending on your applications’ memory profile or what you are using your server for, this might be better in some cases.
								- `cat /proc/sys/vm/swappiness`
									- 60 is good for a desktop, server may want to be 0
								- Set the swappiness to different value (optional)
								  `sudo sysctl vm.swappiness=10`
							- How to remove a swap device
								- `sudo swapoff /dev/dm-2`
								- `sudo nano /etc/fstab`
							- {Archive}
								- [How do I add swap after system installation? - Ask Ubuntu](https://askubuntu.com/a/796997/1891741)
								- [https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-22-04](https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-22-04)
						- _Enable hibernation option in menu_
							- Create a hibernation.pkla file
							  `sudo nano /etc/polkit-1/localauthority/50-local.d/com.ubuntu.enable-hibernate.pkla`
							- Copy in the command (in notes section)
							  source:: https://websiteforstudents.com/enable-hibernation-ubuntu-17-10-desktop/
							  ```
							  [Enable hibernate by default in power]
							  Identity=unix-user:*
							  Action=org.freedesktop.upower.hibernate
							  ResultActive=yes
							  
							  [Enable hibernate by default in logind]
							  Identity=unix-user:*
							  Action=org.freedesktop.login1.hibernate;org.freedesktop.login1.handle-hibernate-key;org.freedesktop.login1;org.freedesktop.login1.hibernate-multiple-sessions;org.freedesktop.login1.hibernate-ignore-inhibit
							  ResultActive=yes
							  ```
						- Test hibernate works
						  `sudo systemctl hibernate`
				- _{Archive}_
				  collapsed:: true
					- For ((63134593-906c-43b5-96fe-33dc2c34fda4)) and Thunderbird
					  collapsed:: true
						- Deprecated? Tue, Apr 26, 2022
							- Ubuntu is no longer packaging ((63134593-906c-43b5-96fe-33dc2c34fda4)) since Mozilla requested they replace it with a Snap
								- Using a self-updating install
								  `/home/boss/Documents/ESSENTIALS/Programs/firefox/firefox -new-instance -P "default-release"`
							- Old SOP
								- `firefox -P` (runs ((63134593-906c-43b5-96fe-33dc2c34fda4)) profile picker)
									- Choose the "2021-2-4-default" profile
								- Run the Profile Picker desktop shortcuts I've setup
								- BirdTray > Settings:
									- Hiding > tick everything
									- Path of executable
									  /media/veracrypt1/Thunderbird/thunderbird/thunderbird
								- For system ((63134593-906c-43b5-96fe-33dc2c34fda4)):
									- Go to `~/.mozila/Firefox/XXX.default`
									- Go to the application menu and remove Firefox from favourites
									- Right-click the application menu > Firefox > Command >
									  `/usr/lib/firefox/firefox -new-instance -P "default"`
									- Save
								- _See_ [How to Re-Setup Firefox Profile](https://workflowy.com/#/74cef3552fba)
								  #WebBrowser
						- OLD - Create launchers
							- ((63134593-906c-43b5-96fe-33dc2c34fda4))
							  `firefox/firefox -new-instance -P "LEISURE" & disown`
								- Forgot what this is about
							- Edit native Firefox to open in default profile
								- To start off, we need to open KMenuEdit, so right mouse button on the application launcher menu, click Edit Applications... to start KMenuEdit. After KMenuEdit has started, select Internet as shown in picture below.
								- Create a new entry for Firefox, copying all the same info except
									- Set the command as
									  firefox %u -P "default"
					- Redundant because of Keyboard Indicator app in KDE
						- Caps lock indicator (Indicator-LockKeys)
							- sudo add-apt-repository ppa:tsbarnes/indicator-keylock
							- sudo apt update
							- sudo apt install indicator-keylock
				- Related: ((63ad9568-d927-46e4-8ee0-df45808fb990))
			- Install software
				- ((63a9adc7-f2d9-45a9-bef8-df1a225f5a64)) : ((63ab465b-2840-49fa-9e73-3d327896e9c0))
				- Packages
				  id:: 63ad9568-d927-46e4-8ee0-df45808fb990
				  collapsed:: true
					- `~/Documents/ESSENTIALS/ansible.yml`
					  id:: 65a98a51-176d-4a50-b509-a62b0fd4b6e0
					  for `apt` + `pip` packages
						- ((63a9ade4-fc71-46d0-9d87-5fb5873b16ad))
						- ((654cc1e2-1a60-44b1-aee2-494c8a8d4ce0))
						- _Gaming_
						  id:: 6491d46e-dd71-44cf-bbad-9acaa102bf3e
						  collapsed:: true
							- Lutris setup
								- _WINE stuff_
								  collapsed:: true
									- [WINE](https://www.winehq.org/)
									  id:: 65a98a51-5961-458f-8642-87ca783f3385
									  collapsed:: true
									  Allows running ((66a98a52-9772-4779-9956-4684637041b1)) games
										- [source] [https://github.com/lutris/docs/blob/master/WineDependencies.md](https://github.com/lutris/docs/blob/master/WineDependencies.md)
										  collapsed:: true
											- Enable 32 bit architecture (if you haven't already):
											  sudo dpkg --add-architecture i386
											- WineHQ - use their newer builds rather than distro's packages
											  [[Wine · Wiki · wine / wine · GitLab](https://wiki.winehq.org/Ubuntu](https://wiki.winehq.org/Ubuntu))
										- About WINE
											- WINE is often faster than Windows because
												- there is no theoretical reason why Wine should be slower.
												- Wine is basically an open clone of Windows that is designed to run on a Unix Kernel rather than on an NT Kernel. That's it, an open clone. Just like GNU/Linux is an open clone of Unix. There is no theoretical reason why it should be slower, it doesn't add any extra translation layer or anything. It jut translates WinAPI calls to Unix Kernel calls, like how Windows translates them to NT Kernel calls.,
										- Today I learned htop shows wine programs with their "windows file paths"
										- {Archive}
										  collapsed:: true
											- [source] [https://wiki.winehq.org/Ubuntu](https://wiki.winehq.org/Ubuntu)
											- _Other info_
												- https://help.ubuntu.com/community/Wine
												- https://wiki.winehq.org/Wine_User's_Guide
												- Can't double-click to run exe's?
												  source:: https://ubuntuforums.org/showthread.php?t=2382617
													- I used to be able to run ANY exe simply by double-clicking on it.
														- Now suddenly, I can't do this anymore. "Wine" isn't even listed as an "Open With" option.
														- It appears that Wine will now only run apps that are installed under the Wine interface ("Wine Tricks"). Is that accurate?
													- Solution 1
														- If you have already installed a Wine-compatible app with shortcut on your desktop, simply clone the shortcut (copy/paste) and rename it. If not, install something small/simple using Wine just for the shortcut. (I'm not sure how to create a null shortcut from Ubu.) Shortcuts to existing folders/apps can be created by simply holding Shift/Ctrl while dragging your icon to the Desktop.)
														- Right-click for "Properties" of your cloned shortcut and replace the path/filename to that of your own exe (ex: env WINEPREFIX="/home/MyAccountName/.wine" wine-stable C:\\Program\ Files\ \(x86\)\\Notepad\\notepad.exe). You can change the icon by clicking on the icon image (in the "Properties" dialog) and replacing it with any picture file.)
														- Now you can run your custom Windows app right from the desktop at any time (if you get the "Trusted App" dialog, just OK it.)
													- Solution B
														- Or you can just install a file manager other than nautilus/files, which seems to be stripping out more functionality and customizability with every single release.
														- I suggest nemo.
														- Solution B1
															- Then just go to an .exe file, right-click and select properties, at the bottom you will see 'Enter a custom command...', type in wine (or /usr/bin/wine), hit the "Set as default" button, and presto, even naught-of-use, er... nautilus will have wine set as the default application.
														- Solution B2
															- You can still do it by copying/linking wine.desktop to /usr/share/applications
															- Code:
															- sudo cp /usr/share/doc/wine-stable/examples/wine.desktop /usr/share/applications/
															- or
															- Code:
															- sudo ln -s /usr/share/doc/wine-stable/examples/wine.desktop /usr/share/applications/
												- Notes on other compatibility layer s/ emulation
													- Darling (MacOS)
														- Difficult but not as complicated as WINE
														  source:: https://arstechnica.com/information-technology/2013/08/os-x-apps-run-on-linux-with-wine-like-emulator-for-mac-software
														- Project status
														  https://www.darlinghq.org/project-status/
															- Currently no GUI apps
														- https://github.com/darlinghq/darling
													- Hybris for Linux (Android)
														- Linux PC. Run Android apps on Linux
														- Libhybris5 is basically an Android compatibility layer for Linux. Think of it in terms of capability it provides as "WINE for Linux" but then providing "Android for Linux".
														- https://en.wikipedia.org/wiki/Hybris_(software)
													- WINE (Windows)
									- Proton
									- [GitHub - winapps-org/winapps: Run Windows apps such as Microsoft Office/Adobe in Linux (Ubuntu/Fedora) and GNOME/KDE as if they were a part of the native OS, including Nautilus integration. Hard fork of https://github.com/Fmstrat/winapps/](https://github.com/winapps-org/winapps)
									- [GitHub - Open-Wine-Components/umu-launcher](https://github.com/Open-Wine-Components/umu-launcher)
									  This is a unified launcher for Windows games on Linux. It is essentially a copy of the Steam Runtime Tools and Steam Linux Runtime that Valve uses for Proton, with some modifications made so that it can be used outside of Steam.
									- [Mono](https://www.mono-project.com/)
									  collapsed:: true
										- [Mono / Framework Mono · GitLab](https://gitlab.winehq.org/mono/mono)
										- Do the following to install  `wine-mono` :
										  [source] [Mono Package for Wine is not installed - Ask Ubuntu](https://askubuntu.com/questions/841847/mono-package-for-wine-is-not-installed)
											- Download [wine-mono.msi](https://dl.winehq.org/wine/wine-mono/) from the official WineHQ site.
											- Type  `wine64 uninstaller` .
											- Press install from the uninstaller GUI and select the downloaded .msi package.
										- Install officially
										  source:: https://www.mono-project.com/download/stable/#download-lin
											- Add repo
												- ```
												  sudo apt install gnupg ca-certificates
												  sudo apt-key adv --keyserver [hkp://keyserver.ubuntu.com:80](hkp://keyserver.ubuntu.com:80) --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
												  echo "deb <a href="https://download.mono-project.com/repo/ubuntu">https://download.mono-project.com/repo/ubuntu</a> stable-focal main" | sudo tee /etc/apt/sources.list.d/mono-official-stable.list
												  sudo apt update
												  ```
											- Install Mono
												- `sudo apt install mono-devel`
												- OR
												- `sudo apt install mono-runtime`
									- Troubleshooting
										- When launching a game getting a WINE error that says audio output is mono not stereo
											- [[2024-12-13 Friday]] Seems to be a bug with my bluetooth headset? Checking in KDE audio the settings for my headset and changing the profile to `High Fidelity Playback` seems to fix it back to stereo
								- _Graphics drivers_
								  collapsed:: true
									- Enable 32-bit architecture:
									  `sudo dpkg --add-architecture i386`
									- Graphic drivers for Intel/AMD + Nvidia
									  collapsed:: true
									  [Source] [https://github.com/lutris/docs/blob/master/InstallingDrivers.md](https://github.com/lutris/docs/blob/master/InstallingDrivers.md)
										- Add kisak-mesa PPA for Intel/AMD mesa latest drivers
										  sudo add-apt-repository ppa:kisak/kisak-mesa
										- Add the Proprietary GPU Drivers PPA for Nvidia latest drivers
										  sudo add-apt-repository ppa:graphics-drivers/ppa
										- Install the 450 driver:
										  sudo apt install nvidia-driver-450
										- sudo apt update && sudo apt upgrade
										- Install support for 32-bit games
										  sudo apt install libgl1-mesa-dri:i386
										- Install support for Vulkan API (will be functional only if you have a [Vulkan capable GPU](https://en.wikipedia.org/wiki/Vulkan_(API)#Compatibility)):
										  sudo apt install mesa-vulkan-drivers mesa-vulkan-drivers:i386
									- `sudo apt install mesa-utils -y`
									- _{Archive}_
									  collapsed:: true
										- [source] [https://github.com/ValveSoftware/Proton/wiki/Requirements#amdintel](https://github.com/ValveSoftware/Proton/wiki/Requirements#amdintel)
										- _Alternative PPAs_
											- sudo add-apt-repository ppa:oibaf/graphics-drivers
											- https://www.epicgames.com/unrealtournament/forums/unreal-tournament-discussion/ut-development-bug-reports-qa/linux-troubleshooting/14891-how-to-update-open-source-graphic-driver-in-ubuntu
											- Add the stable Padoka PPA to Ubuntu 18.04 for Non-Vega GPUs:
											  sudo add-apt-repository ppa:paulo-miguel-dias/pkppa
												- Requested by DXVK
									- Note: check Mesa version
									  `glxinfo | grep "OpenGL version"`
									- DXVK
									  collapsed:: true
									  Already done by following the other graphics drivers steps
										- _{Archive}_
											- Follow instructions here
											  source:: [https://github.com/lutris/docs/blob/master/HowToDXVK.md](https://github.com/lutris/docs/blob/master/HowToDXVK.md)
											- Info
												- DXVK translates Dx9/10/11 API calls to Vulkan calls and allow most Windows games to run on Linux at high graphics and very good performance.
													- https://github.com/doitsujin/dxvk
								- _Related:_ ((63ad9565-9f04-447d-b3c2-7541d47f2703))
							- [Lutris](https://lutris.net/)
							  id:: 65a98a51-b5c3-4329-a1c7-321ce408e6f8
							  collapsed:: true
								- Pros/Cons
									- Cons
										- Bugs
											- [Post-exit script runs prematurely if Steam is already open · Issue #2926 · lutris/lutris · GitHub](https://github.com/lutris/lutris/issues/2926)
										- ### Lacks
											- [[Feature request] Support SteamGridDB for cover art · Issue #4024 · lutris/lutris · GitHub](https://github.com/lutris/lutris/issues/4024#issuecomment-2099509146)
											- [HowLongToBeat info](https://github.com/lutris/lutris/issues/3472)
											- [Sandboxing/containerisation for each game](https://github.com/lutris/lutris/issues/4755#issuecomment-2408695189)
											- [Ability to add categories to games which aren't currently installed](https://github.com/lutris/lutris/issues/5606)
											- [Time played calendar](https://github.com/lutris/lutris/issues/2256)
										- ### wontfix
											- [Can't open native Lutris simultaneously with Flatpak Lutris · Issue #5384 · lutris/lutris · GitHub](https://github.com/lutris/lutris/issues/5384)
											  id:: 667eab59-f4b7-4b62-b716-c5f886c94fdc
								- Installation
								  collapsed:: true
									- Native
									  id:: 667ea696-f6cf-434f-bd56-1ed42b4f04da
										- Download
										  ```bash
										  sudo add-apt-repository ppa:lutris-team/lutris
										  sudo apt install -y lutris
										  ```
										- Note: this automatically installs wine
									- [Flatpak](https://flathub.org/apps/details/net.lutris.Lutris)
									  id:: 65a98a51-4f38-4618-beb1-94b97fc0bf2c
								- Features
								  collapsed:: true
									- Can use many runners including Proton
									- Gog integration
										- https://github.com/lutris/lutris/issues/154#issuecomment-427314953
									- In terms of Features, the Lutris website lists them as:
										- Manage your Steam games, Linux games, Windows games, emulated console games and browser games
										- Community-written installers to ease up your games' installation
										- More than 20 emulators installed automatically or in a single click, providing support for most gaming systems from the late 70's to the present day
										- Download and play libre and freeware games
								- # Documentation
									- `Favourites`
									  id:: 66f330c8-b1ab-4bf8-84fa-3db21943f871
										- Choose the lowest ((658dad62-b37b-439a-ba87-3c5306168548)) in ((66cf222b-de1b-4029-828d-1401675cbebe))
									- My Categories
									  id:: 66cf8e4f-c21d-4365-ad84-29fffc61e2ab
									  collapsed:: true
										- # `Ad`
										  Adult games
											- Meta
											- ## `Ad`
												- All adult games not yet played
											- ## `Ad - Done`
												- Adult games I've completed all the released content for
											- ## `Ad - WIP`
												- Adult games I haven't completed all the released content for
										- # `Fave`
										  id:: 67cc4872-4c75-42f8-bdb7-db96869c9ffb
											- Meta
												- Each subcategory **is not** mutually exclusive
													- ((64e9e730-3133-4afb-a30f-e454885ba0a3)) both had a very good story mode as well as roguelike mode
													- ((632cd63c-fe84-44cd-bb15-85ce4c054eca)) has a good story, but also it's basically replayable because there's constant mods for it
													- ((632d02ab-14a1-4cc3-88dd-f9a66bd163e7)) both had a very good story mode and it's Long War mod makes it so that it's basically roguelike
											- ## `Fave - campaign`
											  id:: 67cc4872-f222-4af7-97bb-c8010cd96d38
												- The campaign/story mode is really fun e.g. ((644c0bb7-b3f2-4c0c-b830-5d7976985142)), ((64e9e72c-a562-400f-a494-8fe78b41fbaf))
												- In some cases it's so fun that it's replayable multiple times, for example:
													- ((634bc201-ab66-494b-8738-826601b04f57)) quests were awesome, ((632093e2-9014-4f25-8fed-cf47c045231f)) and ((632cd63c-fe84-44cd-bb15-85ce4c054eca)) has a ton of replayability thanks to choice-driven/character builds/mods
											- ## `Fave - co-op`
											- ## `Fave - replayable`
												- Not referring to the story aspects but instead it's replayable game loop e.g.
										- # `Launchers`
											- Anything that isn't a game itself but instead a hub to access others
										- # `To play`
										  id:: 66cf8e4f-9cbb-4f75-93ee-771404fe773b
											- Meta
												- For games which I haven't played at all or much, with "much" being defined as that I haven't tried out the game for long enough or in a long time for me to decide whether it should be moved to `Fave` categories or no category
												- Each `To play` subcategory is **mutually exclusive**. Prefer ((66cf222b-de1b-4029-828d-1401675cbebe)) if it's borderline
													- ((66cf222b-de1b-4029-828d-1401675cbebe)) types
													- ((66cf8e4f-db27-4cdd-b578-61afe8e00888)) games
													- Borderline games: ((630f97d8-5e75-445d-9a55-6f2c4f1e517f)), 100% Orange Juice, FTL, ((63734e80-3981-4b17-a325-d4ba7f823565)), Hand of Fate 2, Into the Breach, Nioh 2, Outriders, Paint the Town Red, Returnal, Sifu, The Division 2, ((64e9e733-b821-4f11-bb87-fb0b4ce710c1)), Fights in Tight Spaces, Genshin Impact, Gloomhaven, Hacknet, Heroes of Might and Magic 2/3, Honaki Star Rail, Remnants of the Precursors, Shadow Tactics, Starsector
											- `To play - campaign`
											  id:: 66cf222b-de1b-4029-828d-1401675cbebe
												- Definition: Has a campaign I can play through and potentially comfortably stop there
													- ((63a9ae52-54a1-45bf-b8f8-892c952d4c4a)) RPGs like ((6416d881-7184-425d-acf9-90b93098ee9d)), ((644c0bb4-9801-4ac3-a423-cf17703a148b)) because they have a main story line that can be completed
													- ((632cf072-c2c6-43b5-92f8-55eca18f42b6)) like ((630f97d8-5e75-445d-9a55-6f2c4f1e517f)) as they have a final boss
													- ((644c0bb6-cba1-41a7-a219-5c7182f9487a)) e.g. ((63503886-bb79-451d-9faa-58794efb38e7)), ((64e9e730-77ce-438d-84f0-e88e96edc2e9)), ((644c0bbc-9a44-4320-a7fc-1ad01f89ddf3)), ((6318fd52-c87b-4b6c-9ea1-fea756d1d4a8))
														- They have a several hour "campaign", although ultimately it's randomised each time and meant to be replayed. Keep it in ((66cf222b-de1b-4029-828d-1401675cbebe)) until it's been beaten once, then decide whether to put it in ((66cf8e4f-db27-4cdd-b578-61afe8e00888)) or drop it as it's a mid game
											- `To play - loop, not story`
											  id:: 66cf8e4f-db27-4cdd-b578-61afe8e00888
												- Definition:
											- Related: ((644c0bc5-c8fd-4c66-a352-d3c68842e841)) :
										- # `WIP/Early Access`
										  id:: 6737dffd-d87f-4047-be4e-a8f534f75926
											- Subset of ((687014ec-0923-49a3-bbfa-18532e5e7ffa))
												- Only the notable ones which either:
													- Aren't on Steam so can't be on the wishlist
													- I'd be very likely to want to play
											- Keep games in there at least 1 year for ((67c96910-4baa-4541-b9ae-4f086f5ab63a))
												- Keep games in there longer if they're missing notable features that are coming soon which will significantly improve my enjoyment of the game
													- If the gameplay loop for the first X hours is unlikely to change much then it's all the more reason to remove it from this category
											- Remove games from this category and either put it in a ((66cf8e4f-9cbb-4f75-93ee-771404fe773b)) category if it's looks like something I'd be interested in, else remove it from categories entirely
									- Troubleshooting
										- [TypeError: can only concatenate str (not "float") to str (self.playtime) · Issue #4289 · lutris/lutris · GitHub](https://github.com/lutris/lutris/issues/4289)
										  collapsed:: true
											- `/var/lib/flatpak/app/net.lutris.Lutris/x86_64/stable/922e35121fa8a721c8b8b651214eb71aeb9f27d58853ebf6d0525e9828945645/files/lib/python3.10/site-packages/lutris/game.py`
											- Fix: [Fix playtime no recording by GoGoOtaku · Pull Request #4650 · lutris/lutris · GitHub](https://github.com/lutris/lutris/pull/4650/files)
							- libstrangle - to limit FPS for CPU intensive games
							  collapsed:: true
								- ~/Documents/ESSENTIALS/Other-files/libstrangle-master
								  source:: [https://gitlab.com/torkel104/libstrangle](https://gitlab.com/torkel104/libstrangle)
									- sudo apt install gcc-multilib g++-multilib libx11-dev mesa-common-dev
									- make
									- sudo make install
								-
								- 1 Backlink
									- See [libstrangle - to limit FPS for CPU intensive games](https://workflowy.com/#/faa6cdf769ec)
							- Check if you have a Vulkan capable Intel iGPU
							  collapsed:: true
								- How to check
									- https://en.wikipedia.org/wiki/Vulkan_(API)#Compatibility
									- Can look up the microarchitecture of CPU here e.g. Whiskey Lake https://en.wikichip.org/wiki/intel/core_i7/i7-8565u
									- The iGPU in my Dell XPS doesn't support Vulkan (or at least not yet), likely because it's aimed towards notebooks
								- If GPU isn't Vulkan capable, then in Lutris:
									- If you cannot use Vulkan / DXVK, disable DXVK. Then enable PBA for OpenGL by setting PBA_ENABLE=1 in environment variables
										- > Right-click HOTS in Lutris >
										- > Runner Options > Disable DXVSK
										- > System Options > set PBA_ENABLE to 1 (from 0)
							- Need to use installer scripts for various Lutris-installed games in order to automatically setup the correct directories, WINE version etc
							  collapsed:: true
								- Until Lutris fixes "No 1-click add on existing games", then will also need to re-add scripts for HOTS and OW or any other Lutris-installed games
								  intralink2:: https://workflowy.com/#/68af4d50f423
								- _This wasn't actually needed on XPS initial install 21/2/19, it ran fine installing over the same HOTS directory without even deleting it_
									- Cancel when it starts to download the full game
									- Install HOTS
									  https://lutris.net/games/heroes-of-the-storm/
								- _Screenshots of what games in Lutris library_
									- All
									  http://i.imgur.com/dmphvOO.png
									- Linux - ((632d02a9-cd45-42a1-aad7-8062cc756fee))
									- Wine - BYOND, CEMU, Overwatch, Heroes of the Storm, Epic Games Store, Star Citizen, The Escapists
									  http://i.imgur.com/9SgNl9w.png
							- Shader Disk Cache
							  collapsed:: true
								- It's saved in ~/.cache/mesa
								- Notes on DXVK State Cache:
								- dxvk-cache files exist for games that use DXVK, it ensures that when drivers update you can continue to use the existing GLCache folders in each game dir which contains the shader cache. These are shareable files which can be used to quickly rebuild the cache again
								- [source] https://youtu.be/Lq4uriTLp1I
							- ((649b1463-90cf-40ee-b80f-cb955fc2264c))
							- _Troubleshooting_
							  collapsed:: true
								- Lutris can't install games e.g. Overwatch
								  collapsed:: true
								  I'm getting an error when trying to install Overwatch, anybody got some advice? (full logs here https://pastebin.com/4iajQTfG)
								  
								  I think these are the most relevant parts:
								  `error while loading shared libraries: libwine.so.1: cannot open shared object file: No such file or directory" `
								  
								  ```
								  2019-12-17 16:52:54,838: Creating a win64 prefix in /home/boss/Games/overwatch
								  2019-12-17 16:53:00,116: Wine prefix creation is taking longer than expected...
								  2019-12-17 16:53:07,381: No user.reg found after prefix creation. Prefix might not be valid
								  2019-12-17 16:53:07,412: The game doesn't have an executable
								  ```
									- **Solution: **Delete the wine runner for that game so the installer redownloads it
									  collapsed:: true
										- Find it in /home/boss/.local/share/lutris/runners/wine
										- Run `lutris` from command line so you can see what wine version it downloads/tries to use during the installer
										- _Personal experience_
										- Round 1 (October 2018)
										- Wireless keyboard all keys stop working so I can't use any abilities for a while
										- Inbuilt keyboard randomly starts listening to q again and opens the application menu and puts game in background. or starts listening to number keys which swaps me to program 1 in the takakkbar
										- Doesn't work without eGPU being used
										- Round 2 (after reboot and installing other packages)
										- Wireless keyboard becomes mostly unresponsive in a quick match directly after a normal AI match. Laptop keyboard still works though
										- After using ALT+TAB window switch to go to desktop then back it doesn't affect this behaviour
										- New install 2 months later (20/12/18)
										- Works perfectly with Overwatch and Heroes of the Storm. Some jitters at the start of matches sometimes but then plays fine
									- Steam setup
									  collapsed:: true
										- Can help prevent Steam issues
										  collapsed:: true
											- Microsoft fonts
											  sudo apt-get install msttcorefonts
										- Install Steam
										  collapsed:: true
										  sudo apt install steam
											- _Troubleshooting_
												- Possible missing 32-bit libraries
												  collapsed:: true
													- _Solutions_
														- Maybe easier to use GDEBI to install dependencies if installing the downloaded binary instead
														  https://store.steampowered.com/about/
															- Tried, didn't work
													- Launch step 1
													  libXtst.so.6
													  libXrandr.so.2
													  libXrender.so.1
													  libgobject-2.0.so.0
													  libglib-2.0.so.0
													  libgio-2.0.so.0
													  libgtk-x11-2.0.so.0
													  libpulse.so.0
													  libgdk_pixbuf-2.0.so.0
													  libva.so.2
													  libbz2.so.1.0
													  libvdpau.so.1
													  libva.so.2
													  libva-x11.so.2
														- Command
														  sudo apt install libxtst6:i386 libxrandr2:i386 librust-gobject-sys-dev:i386 libglib2.0-0:i386 libglib2.0-0:i386 libgtk2.0-0:i386 libpulse0:i386 libva2:i386 libbz2-1.0:i386 libvdpau1:i386 libva-x11-2:i386
															- libgio-cil:i386
													- Launch step 2
														- Command
														  sudo apt install libice6 libice6:i386 libopenal1 libopenal1:i386 libsm6 libsm6:i386
														- Missing
														  libopenal.so.1 => not found
														     libSM.so.6 => not found
														  libICE.so.6 => not found
													- Launch step 3
														- Missing
														          [libtier0_s.so](http://libtier0_s.so) => not found
														          <a href="http://libvstdlib_s.so">libvstdlib_s.so</a> => not found
														          <a href="http://libv8.so">libv8.so</a> => not found
														          <a href="http://libvideo.so">libvideo.so</a> => not found
														          libSDL2-2.0.so.0 => not found
												- _May get stuck trying to launch_
													- mkdir "/home/$USER/.steam/ubuntu12_32/steam-runtime"
										- Then go to Settings > Downloads > Steam Library Folders > add ~/Games/SteamLibrary/ > right-click and make that folder "default"
										- _Enable Steam Play_
										  collapsed:: true
											- Opt into Steam Client Beta (optional)
											  top-left corner Steam > Account > Settings
												- https://support.steampowered.com/kb_article.php?ref=7021-EIAH-8669
											- Enable Steam Play
											  top-left corner Steam > Account > Steam Play. Enable all options
										- _Troubleshooting_
										  collapsed:: true
											- Steam Proton games won't open
											  I've got a new Kubuntu 19.10 install and I'm having issues with launching Proton games, whilst native games launch fine. When I click Play on games like Warframe/Door Kickers/Brawlhalla nothing happens. It just changes from "Play" to "Stop" for a second, then reverts back. Had no issues when I was using a Kubuntu 18.04 LTS install
												- **Solution: **Redownload the Proton builds to here and replace existing versions (there may have been data corruption/missing files
												  /home/boss/.steam/root/compatibilitytools.d/
									- Controllers
									  collapsed:: true
										- Controllers for Steam
										  collapsed:: true
										  sudo apt-get install steam-devices
											- - this got PS4 controller detecting correctly by Steam (Xbox One controller was plug-and-play)
										- Xpadneo for wireless Xbox One controller use
										  collapsed:: true
										  See [Setting up Linux driver for Xbox controller wireless bluetooth connection](https://workflowy.com/#/4e04d529c809)
											- 1 Backlink
												- See [Xpadneo for wireless Xbox One controller use](https://workflowy.com/#/b076b53b99f1)
									- Config changes
									  collapsed:: true
										- Editing fstab to make NTFS external hard drives readable
										  collapsed:: true
										  Unneeded currently Sat, Jan 30, 2021
											- [source] [https://github.com/ValveSoftware/Proton/wiki/Using-a-NTFS-disk-with-Linux-and-Windows#editing-fstab](https://github.com/ValveSoftware/Proton/wiki/Using-a-NTFS-disk-with-Linux-and-Windows#editing-fstab)
											- Why
												- Otherwise it prevents Lutris from installing games on the external hard drive for one
												- **Wait**
													- This made Steam unable to mount folders within as Steam libaries
											- TLDR
												- Edit the fstab file to mount the partition:
												- $ sudo nano /etc/fstab
												- At the bottom of the file, add the following line (changing UUID, uid, and gid where needed):
												- UUID=38CE9483CE943AD8 /media/gamedisk ntfs uid=1000,gid=1000,rw,user,exec,umask=000 0 0
												- On Ubuntu, as long as ntfs-3g is installed using ntfs as the filesystem type will work
												- Reboot the computer for the changes to take effect:
												- $ sudo reboot
											- _Troubleshooting_
												- Fri, Dec 18, 2020 - for some reason the libraries are no longer on my Steam, and trying to add them gives the error "new steam library folder must be on a filesystem mounted with execute permissions"
												  collapsed:: true
													- sda4 appears to be the Windows partition with visible files
													  UUID="C0CAA403CAA3F3B6"
														- _Used these commands to find it_
															- sudo blkid
															- sudo fdisk -l
													- Thoughts - now that I have a Nvidia GeForce NOW subscription to play the few Windows, it might be easier to just have an ext4 drive with all these games
													- _See_ [Windows games via Wine/Proton
													  [[Videogames]]
										- Increase maximum files open limit
										  id:: 65a98a51-86a0-4b61-ac39-4efe48b9c93d
										  collapsed:: true
											- Check
											  ulimit -n
											- sudo nano /etc/sysctl.conf
											- Add this line
											  fs.inotify.max_user_watches = 1048576
											- Reload it
											  sudo sysctl -p
											- Needed for
												- CrashPlan
												  [Increase max ](https://workflowy.com/#/43393c25adb4)<a href="https://workflowy.com/#/43393c25adb4">inotify</a><a href="https://workflowy.com/#/43393c25adb4"> watches available</a>
												- Needed for GitKraken to watch files
										- Increase virtual memory limit
										  collapsed:: true
											- Why
												- Needed to prevent crashes on ((63542965-aaa8-4872-b7bb-026c76092669)) on high poly maps
												  source:: [Star Citizen - Lutris](https://lutris.net/games/star-citizen/)
											- _Temporarily raising it_
											  `sudo sysctl -w vm.max_map_count=16777216`
											- _Permanently_
												- `sudo nano /etc/sysctl.conf`
												- Add this line
												  `vm.max_map_count=16777216`
										- `sudo sysctl -p`
										  id:: 63734d16-ee7e-4f5a-8812-ba9d334e17aa
										  Reload it
									- Java (prereq for Minecraft)
									  collapsed:: true
										- Java Runtime Environment (JRE)
										  sudo apt install default-jre
										- Needed to install Minecraft
									- _See_ [RetroArch
									  [[Videogames]]
									- _{Archive}_
									  collapsed:: true
										- Esync - by default enabled now on newer distros
											- Check if value printed is equal or greater to 524288
											  ulimit -Hn
											- https://github.com/lutris/lutris/wiki/How-to:-Esync
											- Edit /etc/systemd/system.conf defaultlimitNOFILE=1048576
									- _Related:_
										- Setting up specific games on Linux
										  [[Videogames]] [Linux gaming
										- _See_ [eGPU hybrid graphics](https://workflowy.com/#/98526fce22de) (AMD/NVIDIA)
						- Homebrew
						  id:: 65a9a686-82da-428a-ae22-170fcbe25a2e
						  collapsed:: true
							- May need to adjust open files soft limit
							  e.g. `ulimit -n 5000`
						- [pip](https://pip.pypa.io/)
						  collapsed:: true
							- Meta
								- `sudo apt install python3-pip`
								- Use `--break-system-packages` to bypass Kubuntu limitation
								  collapsed:: true
									- e.g. `pip install -r requirements.txt --break-system-packages`
									- error: externally-managed-environment
										- × This environment is externally managed
										  ╰─> To install Python packages system-wide, try brew install
										      xyz, where xyz is the package you are trying to
										      install.
										      
										      If you wish to install a non-brew-packaged Python package,
										      create a virtual environment using python3 -m venv path/to/venv.
										      Then use path/to/venv/bin/python and path/to/venv/bin/pip.
										      
										      If you wish to install a non-brew packaged Python application,
										      it may be easiest to use pipx install xyz, which will manage a
										      virtual environment for you. Make sure you have pipx installed.
										  
										  note: If you believe this is a mistake, please contact your Python installation or OS distribution provider. You can override this, at the risk of breaking your Python installation or OS, by passing `--break-system-packages`.
										  hint: See PEP 668 for the detailed specification.
									- ((664f6a32-06d7-4234-bc39-7e2a3c0c91e4))
								- [pipx](https://github.com/pypa/pipx)
								  id:: 65a98d3c-7855-453a-a347-02b79e9ab6d7
								  collapsed:: true
								  Installs Python packages in an isolated environment. This bypasses Kubuntu's PEP 668 feature which prevents `pip install` system-wide
									- Troubleshooting
										- Using an Ansible playbook and it's not working to use the pipx module to inject packages
											- `pipx reinstall-all`
												- [source](https://github.com/pypa/pipx/issues/278)
									- Note: if you use `--break-system-packages` to install a package e.g. `pip3 install xlib` then `pip3 uninstall xlib` doesn't seem to work
									  id:: 664f6a32-06d7-4234-bc39-7e2a3c0c91e4
									- Resolving missing packages inside a pipx env
									  collapsed:: true
										- `pipx list` = list envs
										- `source /home/boss/.local/pipx/venvs/key-mon/bin/activate` = activate the package `- key-mon`
										  collapsed:: true
										- collapsed:: true
						- {Archive}
						  collapsed:: true
							- ((63c0feef-bc34-42b8-aaa6-4ab581f3be70)) - no longer compatible with KDE since 5.27
					- **No Nix package or doesn't work well**. Move into Ansible playbook
						- exFAT packages
						  `sudo apt install -y exfat-fuse exfat-utils`
						- Searchmonkey (grep GUI)
						  id:: 635eb109-10e0-4dd6-9757-5002dab41b9f
						  collapsed:: true
						  `sudo apt install searchmonkey -y`
							- Alternatives
								- [https://github.com/junegunn/fzf](https://github.com/junegunn/fzf)
								- [Rga: Ripgrep, but also search in PDFs, E-Books, Office documents, zip, tar.gz](https://phiresky.github.io/blog/2019/rga--ripgrep-for-zip-targz-docx-odt-epub-jpg/) (
									- [https://news.ycombinator.com/item?id=25277280](https://news.ycombinator.com/item?id=25277280)
						- `sudo apt install libssl-dev`
						  May need this in order for KeePassXC to open
						- Kubuntu Backports
						  collapsed:: true
							- [https://community.kde.org/Kubuntu/PPAs#Kubuntu_Backports](https://community.kde.org/Kubuntu/PPAs#Kubuntu_Backports)
							- `sudo add-apt-repository ppa:kubuntu-ppa/backports`
							- `sudo apt full-upgrade`
							- ..
							- https://launchpad.net/~kubuntu-ppa/+archive/ubuntu/backports
							- https://community.kde.org/Kubuntu/PPAs
							-
						- ((635eb171-c518-4825-aaaf-029c16ce1a86))
						- ((639d8989-c162-4fe4-9e51-b2899d10b4bf))
						- ((638e7c15-6b65-4f35-82c7-05460cb45d8d))
							- [Install Mullvad app on Linux | Mullvad VPN](https://mullvad.net/en/help/install-mullvad-app-linux)
						- [[Docker]] : ((63aec847-b868-47ef-84fe-eeb5a4f62113))
					- _{Archive}_
					  collapsed:: true
						- Archived [[2022-12-27 Tuesday]]
						  collapsed:: true
							- paprefs
							  collapsed:: true
							  Doesn't work with Pipewire, remove | [[2022-12-29 Thursday]] not installed yet I still have simultanous output configured
								- Allows simultaneous output to all attached sound cards/devices (ie allows you to plug in two headphones and listen to both. Useful for two people using separate headphones like I needed in Poland)
								- Docs
									- in terminal run paprefs, select "Simultaneous Output" tab, and check "Add virtual output for simultaneous output on all local sounds cards".
									- The additionally created audio output device for simultaneous output may be selected in the "Output" tab from pulseaudio sound preferences menu
								- [source] [https://askubuntu.com/questions/78174/play-sound-through-two-or-more-outputs-devices](https://askubuntu.com/questions/78174/play-sound-through-two-or-more-outputs-devices)
							- [KDocker](https://github.com/user-none/KDocker) 
							  collapsed:: true
							  (alternative to RBTray)
								- Installation
									- [[2024-08-23 Friday]]
										- `sudo apt install build-essential cmake qt6-base-dev libx11-dev libxcb1-dev libxmu-dev`
									- Old
										- /home/boss/Documents/ESSENTIALS/Programs/kdocker_5.3-1_amd64.deb
										- Download the amd64 version
										  [https://packages.debian.org/unstable/kdocker](https://packages.debian.org/unstable/kdocker)
										- _Don't use Kubuntu package, it's not kept updated. Or is it? 5.1 version available <time startYear="2021" startMonth="1" startDay="1"_
										  sudo apt install -y kdocker
								- Usage
									- ALT+F2 to open KRunner, then select KDocker and then click on the application
								- _Issues_
									- Tray icon is always a question mark
									  [https://github.com/user-none/KDocker/issues/81](https://github.com/user-none/KDocker/issues/81)
								- _Alternatives_
									- ksycmdtray
									  collapsed:: true
										- Tried to get it from here however it doesn't run without a package that I can only find for RPM systems
										  [https://packages.debian.org/jessie/kde-workspace-bin](https://packages.debian.org/jessie/kde-workspace-bin)
									- SysTray alternative APIs
									  collapsed:: true
									  AKA system tray, notification area, status icons, app indicators, tray icons, etc
										- [https://islinuxabout.xyz/systray/](https://islinuxabout.xyz/systray/)
										- I want to…
											- [Convey sync status or provide actions related to cloud storage](https://islinuxabout.xyz/systray/#cloudproviders)
											  collapsed:: true
												- If you want to communicate synchronization status or provide actions related to cloud storage devices, you can use the CloudProviders DBus API
												- On GNOME, not KDE
											- [Provide quick access to my app’s commonly used actions](https://islinuxabout.xyz/systray/#desktop-actions)
											  collapsed:: true
												- Desktop Actions - If you want to provide quick access to common actions, you can add them to your .desktop file
												- [https://www.electronjs.org/docs/tutorial/linux-desktop-actions](https://www.electronjs.org/docs/tutorial/linux-desktop-actions)
											- [Convey progress for long-running tasks](https://islinuxabout.xyz/systray/#launcher-entry)
											  collapsed:: true
												- Launcher Entry - If you want to communicate progress information for long-running background tasks or the number of items needing action in your app (such as tasks or messages) you can use the LauncherEntry DBus API
													- 1 Backlink
														- See [Launcher Entry](https://workflowy.com/#/f3819947c2a3)
												- On Pantheon and Ubuntu
											- [Display how many items need action (such as unread messages)](https://islinuxabout.xyz/systray/#launcher-entry)
											  collapsed:: true
												- See [Launcher Entry](https://workflowy.com/#/f3819947c2a3)
											- [Provide media player controls or now playing info](https://islinuxabout.xyz/systray/#mpris)
											  collapsed:: true
												- MPRIS - If you want the user to be able to access media player controls for you app, you can listen to and supply information to MPRIS
											- [Alert the user that something has changed in my app](https://islinuxabout.xyz/systray/#notifications)
											  collapsed:: true
												- Notifications - If you want to alert the user that something has changed in your app, you can send a notification bubble
											- [Inform the user that my app is accessing system functions in the background (like screen recording)](https://islinuxabout.xyz/systray/#portals)
											  collapsed:: true
												- Portals
													- XDG Desktop Portals are sandbox-compatible DBus APIs for accessing system functions. Desktop environments can use these portals to request consent from users and provide an ongoing visual indication of portal usage.
													- GNOME has full support, KDE doesn't
										- _[Learning Resources]_
											- [“Growing Beyond the System Tray”](https://www.youtube.com/watch?v=fPFdV-Z69Lo) talk by Daniel Foré at Linux App Summit (2019)
											- [“Developer Tips: Backgrounding & System Integration”](https://blog.elementary.io/developer-tips-backgrounding-system-integration/) by Cassidy James Blaede for elementary (2018)
											- [“Status Icons and GNOME”](https://blogs.gnome.org/aday/2017/08/31/status-icons-and-gnome/) by Allan Day for GNOME (2017)
											- [“Farewell to the notification area”](https://ubuntu.com/blog/notification-area) by Matthew Paul Thomas for Ubuntu (2010)
											- ...
											- [https://wiki.gnome.org/Initiatives/StatusIconMigration/Guidelines](https://wiki.gnome.org/Initiatives/StatusIconMigration/Guidelines)
											- [https://wiki.gnome.org/Initiatives/StatusIconMigration/FAQ](https://wiki.gnome.org/Initiatives/StatusIconMigration/FAQ)
											- [https://blogs.gnome.org/aday/2017/08/31/status-icons-and-gnome/](https://blogs.gnome.org/aday/2017/08/31/status-icons-and-gnome/)
											- [https://gitlab.gnome.org/GNOME/gnome-shell/-/issues/1014](https://gitlab.gnome.org/GNOME/gnome-shell/-/issues/1014)
							- Launchy (Keyboard launcher)
							  collapsed:: true
							  `sudo apt install -y launchy`
								- Launch catalog
									- Remove all folders other than VeraCrypt ones (use KRunner for native programs)
									- Add both container shortcuts folders
									- Make sure to add the filetype '*.desktop'
									- And check 'Include executables'
								- _Alternatives_
									- Cerebro
										- Download (AppImage)
										  https://cerebroapp.com/
										- Doesn't look like it's being maintained anymore (last checked Q3 2018)
										  https://github.com/KELiON/cerebro/releases
									- Albert launcher
										- Cons
											- No AppImage unless someone else wants to manage that
											  https://github.com/albertlauncher/albert/issues/407#issuecomment-318919370
										- Installation
										  https://albertlauncher.github.io/docs/installing/
										- Docs
										  https://albertlauncher.github.io/docs/
										- _Config files_
											- /home/.config/albert/
											- Hover mouse over extensions
												- Most are in /usr/
										- Extensions
											- https://alberthub.netlify.com/
									- Ulauncher
										- No AppImage fully working yet
										  https://github.com/Ulauncher/Ulauncher/issues/74#issuecomment-285663490
										- http://ulauncher.io/
									- Launchy (DEB on website or APT repo. No AppImage availabe)
								- Old notes on Launchy
									- Hidden in KeePass TrueCrypt Container
									- Makes it much easier to access all of my programs (which are all in separate folders and not in start menu as they're portable
									- and in order to hide them from others)
									- When using this, have to include file type to look for in each directory
										- Remember to include a * e.g. *lnk
								- 2 Backlinks
									- See [Launchy (Keyboard launcher)](https://workflowy.com/#/41b931fba949)
									- See [Launchy (Keyboard launcher)](https://workflowy.com/#/41b931fba949)
							- QuiteRSS
							  collapsed:: true
							  `sudo apt install quiterss`
								- Pros/Cons
									- Cons
										- Slow development
										- Currently crashes when loading HTML5 embedded videos
										  [https://github.com/QuiteRSS/quiterss/issues/839#issuecomment-828443953](https://github.com/QuiteRSS/quiterss/issues/839#issuecomment-828443953)
								- See [QuiteRSS as my RSS Reader](https://workflowy.com/#/ad35be59aa09)
								  #Productivity-Key
							- [pipewire](https://pipewire.org/)
							  id:: 63a9adc8-6bc0-4ac7-8df3-f879b95211b5
							  collapsed:: true
							  more secure version of pulseaudio
								- Commands
									- `pw-top` = see processes used by Pipewire
									- `pipewire --version`
									- `systemctl --user restart pipewire.service`
									  id:: 65a98a51-a35e-4cd4-8c57-d144aecb86b3
									  Restart Pipewire
										- `systemctl restart bluetooth` is insufficient
										- Related: https://gitlab.freedesktop.org/pipewire/pipewire/-/issues/732#note_1443791
										-
								- New SOP - April 2022
									- [[Page not found · GitHub](https://github.com/pipewire-debian/pipewire-debian/wiki](https://github.com/pipewire-debian/pipewire-debian/wiki))
								- Old SOP
								  collapsed:: true
									- Is any of ALSA or PulseAudio running?
										- Both ALSA and PulseAudio come with command line appliciations to print out the state of our sound system.
											- PulseAudio:
												- `pactl list`
											- ALSA:
												- `aplay -l`
									- On Debian it requires installing `pipewire-pulse`, copying the default config (this one is silly, it should be done by default) disabling PA's systemd unit and socket then enabling pipewire's unit file and socket.
										- [https://wiki.debian.org/PipeWire#For_PulseAudio](https://wiki.debian.org/PipeWire#For_PulseAudio)
										- It's pretty straightforward, but not quite one package and done yet.
									- In next boot, open terminal and run `pactl info` command will tell that Pipewire is in use even without any configuration.
									- How to install on 21.10
									  source:: [[PipeWire](https:/wiki.debian.org/PipeWire) - Debian Wiki](https://wiki.debian.org/PipeWire](https://wiki.debian.org/PipeWire))
									  collapsed:: true
										- sudo apt install pipewire-audio-client-libraries
										- sudo apt install pipewire-pulse
										- _Pulseaudio steps_
											- Create this empty file:
											- sudo touch /etc/pipewire/media-session.d/with-pulseaudio
											- Create a pipewire-pulse service by copying the example files:
											- cp /usr/share/doc/pipewire/examples/systemd/user/pipewire-pulse.* /etc/systemd/user/
										- _ALSA steps_
											- Create this empty file:
											  sudo touch /etc/pipewire/media-session.d/with-alsa
											- Copy a configuration file from the PipeWire examples into your ALSA configuration directory:
											  sudo cp /usr/share/doc/pipewire/examples/alsa.conf.d/99-pipewire-default.conf /etc/alsa/conf.d/
										- sudo apt install libspa-0.2-bluetooth
										- sudo apt remove pulseaudio-module-bluetooth
										- ...
										- Reboot
										- ...
										- Check it's working with Pulse
											- You can check which server is in use by, as your regular user, running:
											- LANG=C pactl info | grep '^Server Name'
								- Troubleshooting
								  id:: 63accb71-2c43-4827-b4a5-b550dfedc9ac
									- [[2025-06-15 Sunday]] High CPU usage, and `pw-top` indicates speech-dispatcher at fault
										- I believe this process is being started by ((mozilla firefox)) whenever I activate reader mode
										- `sudo nano /etc/speech-dispatcher/speechd.conf` and uncommented the line `DisableAutoSpawn`
											- Didn't work
										- `sudo apt remove speech-dispatcher`
											- CPU usage somewhat lower according to `btop`, though `pipewire-pulse` still at 3%
									- [[2024-05-15 Wednesday]] Audio stuttering
									  collapsed:: true
										- Related issues
											- [Audios crackles (#3470) · Issues · PipeWire / pipewire · GitLab](https://gitlab.freedesktop.org/pipewire/pipewire/-/issues/3470#note_2079446)
											- [Bluetooth stuttering and crackle on A2DP (#2123) · Issues · PipeWire / pipewire · GitLab](https://gitlab.freedesktop.org/pipewire/pipewire/-/issues/2123#note_2078465)
											- ..
											- [pipewire stutters under load with bluetooth headphones (#2784) · Issues · PipeWire / pipewire · GitLab](https://gitlab.freedesktop.org/pipewire/pipewire/-/issues/2784)
											- https://gitlab.freedesktop.org/pipewire/pipewire/-/issues/398#note_1423618
											- [Extreme bluetooth audio stutter (#1221) · Issues · PipeWire / pipewire · GitLab](https://gitlab.freedesktop.org/pipewire/pipewire/-/issues/1221#note_1470353)
											- [Bluetooth headphones has "hiccups" (#1582) · Issues · PipeWire / pipewire · GitLab](https://gitlab.freedesktop.org/pipewire/pipewire/-/issues/1582#note_2061981)
											- [Bluetooth audio stutters / drops out / accelerates during playback (#1726) · Issues · PipeWire / pipewire · GitLab](https://gitlab.freedesktop.org/pipewire/pipewire/-/issues/1726#note_1323067)
											- [Bluetooth stuttering and crackle on A2DP (#2123) · Issues · PipeWire / pipewire · GitLab](https://gitlab.freedesktop.org/pipewire/pipewire/-/issues/2123#note_2078465)
											-
										- Using ((65a98a51-a35e-4cd4-8c57-d144aecb86b3)) then sticking with Headset bluetooth audio device directly instead of Combined seems to have stopped it. Tested using Drake - Family Matters via ((653f7870-974a-43d5-9a09-8a85e1d94ea3))
									- [[2022-12-28 Wednesday]] No audio
									  collapsed:: true
										- Solution - I was on Kubuntu 22.04, whereas 22.10 properly uses PipeWire instead of PulseAudio
										- Wrong
											- `systemctl --user status pipewire pipewire-session-manager` = check if PipeWire is automatically running as a background service
											- `sudo apt install pipewire-pulse`
											- `sudo apt install pipewire-audio-client-libraries libspa-0.2-bluetooth libspa-0.2-jack`
											- `sudo apt install wireplumber pipewire-media-session-`
											- ...
											- Had to manually run pulseaudio via `pulseaudio`
											- `pactl info` = check if using PipeWire, PulseAudio, etc
										-
							- _Create bootable USB drives_
							  collapsed:: true
							  AKA multiboot live USB AKA burn ISO to USB
								- Not particularly relevant anymore Sat, Jan 30, 2021
								- _Purpose_
									- Creating a Windows 7 USB
									  collapsed:: true
										- ((66a239c8-f88a-4796-8134-ed7b8a21d40b))
										- WoeUSB-ng
										  id:: 65a98a51-0e63-468d-87c7-8cd501c4f31f
										  [https://github.com/WoeUSB/WoeUSB-ng](https://github.com/WoeUSB/WoeUSB-ng)
											- Install steps
												- `sudo add-apt-repository ppa:nilarimogard/webupd8`
												- `sudo apt install woeusb`
										- _Doesn't work_
											- UNetbootin
											- _Software wouldn't let me even burn the ISO_
												- YUMI (Your Universal MultBoot Installer)
												- Rufus
												- WinSetupFromUSB
								- _Types of software_
									- _Multiboot_
										- [MultiBootUSB](http://multibootusb.org/) (cross-platform)
										- [Ventoy](https://sourceforge.net/projects/ventoy/)
										  id:: 66a239c8-f88a-4796-8134-ed7b8a21d40b
										  Once installed on a USB, just copy over ISOs and it'll work
										- YUMI (Windows-based)
									- _Single boot_
										- ((65a98a51-0e63-468d-87c7-8cd501c4f31f))
										- [UNetbootin](https://github.com/gkovacs/unetbootin)
										  id:: 65a98a51-e0ba-4dc1-93e7-34647c9f6c0e
										  collapsed:: true
											- Steps
												- `sudo add-apt-repository ppa:gezakovacs/ppa`
												- `sudo apt install unetbootin -y`
									- Unsorted
										- Rufus works best (does it work on Wine?)
										- YUMI works best as a live USB tool. Unetbootin on Linux wouldn't find the USB drive sometimes
										- 5 multiboot options
										  collapsed:: true
										  [5 Apps to Create Multiboot USB - Linux & Windows ISOs Supported](https://www.linuxbabe.com/apps/create-multiboot-usb-linux-windows-iso)
											- SARDU MultiBoot USB and DVD Creator
											- MultiBootUSB
											- MultiSystem
											- YUMI (Your Universal MultBoot Installer)
								- {Archive}
									- MultiSystem is in another language and I can't find a download link
						- ClamAV
						  collapsed:: true
						  _Debatable if necessary_
							- https://help.ubuntu.com/community/ClamAV
							- https://www.vultr.com/docs/setting-up-clamfs-and-clamav-on-ubuntu
							- ClamTk - GUI. Allows for on-demand file scanning
							- clamav-daemon for realtime virus scanner
					- _Related:_
						- ((63a9ade4-acd5-44f9-9166-2c1393865f7a))
						  #Phone
				- ((63a873fd-893d-4ed7-ae5b-e27945e68230)) packages
				  id:: 65a98a51-9dbe-47fd-a0c1-fcef13cdb1ef
				  collapsed:: true
					- [Flathub setup for Ubuntu](https://flatpak.org/setup/Ubuntu)
						- ```
						  sudo apt install flatpak gnome-software-plugin-flatpak 
						  && flatpak remote-add --if-not-exists --user flathub https://flathub.org/repo/flathub.flatpakrepo
						  ```
					- Install all Flatpak packages
						- ```bash
						  flatpak install flathub com.axosoft.GitKraken com.borgbase.Vorta com.brave.Browser com.calibre_ebook.calibre com.discordapp.Discord com.getpostman.Postman com.github.alainm23.planner com.github.dynobo.normcap com.github.jeromerobert.pdfarranger com.github.marinm.songrec com.github.micahflee.torbrowser-launcher com.github.Murmele.Gittyup com.github.needleandthread.vocal com.github.PintaProject.Pinta com.github.tchx84.Flatseal com.github.unrud.VideoDownloader com.gitlab.librebob.Athenaeum com.google.Chrome com.heroicgameslauncher.hgl com.logseq.Logseq com.obsproject.Studio com.rafaelmardojai.Blanket com.slack.Slack com.ulduzsoft.Birdtray com.uploadedlobster.peek com.usebottles.bottles com.valvesoftware.Steam com.visualstudio.code eu.vcmi.VCMI fr.handbrake.ghb im.riot.Riot info.febvre.Komikku io.appflowy.AppFlowy io.dbeaver.DBeaverCommunity io.freetubeapp.FreeTube io.github.Cockatrice.cockatrice io.github.hmlendea.geforcenow-electron io.github.ihhub.Fheroes2 io.github.JaGoLi.ytdl_gui io.github.mimbrero.WhatsAppDesktop io.github.peazip.PeaZip io.github.seadve.Kooha io.github.spacingbat3.webcord io.github.trigg.discover_overlay io.github.webcamoid.Webcamoid io.gitlab.caveman250.headlines io.gitlab.librewolf-community io.lbry.lbry-app md.obsidian.Obsidian net.ankiweb.Anki net.lutris.Lutris net.sapples.LiveCaptions net.sourceforge.squirrel_sql net.veloren.airshipper org.chromium.Chromium org.coolero.Coolero org.flameshot.Flameshot org.gabmus.giara org.gpodder.gpodder org.kde.kasts org.kde.kontact org.kiwix.desktop org.mozilla.Thunderbird org.musicbrainz.Picard org.pipewire.Helvum org.polymc.PolyMC org.prismlauncher.PrismLauncher org.qbittorrent.qBittorrent org.telegram.desktop org.tribler.Tribler org.zotero.Zotero sa.sy.bluerecorder us.zoom.Zoom
						  ```
						- *How to update the list above*
							- `cd ~/.var/app && ls | xargs` = print all Flatpak package names that I've installed (and still have configs for)
					- Possibly downgrade some packages
						-
					- Notable packages
						- `com.visualstudio.code` ((63209272-1088-4824-a762-4ac7ded04b0a))
						  collapsed:: true
						  AKA Visual Studio Code
							- [Visual Studio Code](https://code.visualstudio.com)
							  id:: 63209272-1088-4824-a762-4ac7ded04b0a
							  collapsed:: true
							  AKA VS Code / VSCode / VSC
								- Pros/Cons
								  collapsed:: true
									- Pros
										-
									- Cons
										- Not fully open-source
										  id:: 5dcc13bc-fecd-4ce2-9793-c65eb22fc046
										  collapsed:: true
											- [Microsoft is introducing hidden APIs to VS Code only enabled for Copilot?](https://old.reddit.com/r/ChatGPTCoding/comments/1g8xrub/microsoft_is_introducing_hidden_apis_to_vs_code/)
											- The core is open-source, and the installable binaries with telemetry and properietary extensions are not.
											- C# support is proprietary
												- [https://news.ycombinator.com/item?id=31760684](https://news.ycombinator.com/item?id=31760684)
												- [https://github.com/dotnet/vscode-csharp/issues/5276](https://github.com/dotnet/vscode-csharp/issues/5276)
												- Other replies
													- [https://news.ycombinator.com/item?id=41891653](https://news.ycombinator.com/item?id=41891653)
													- [https://news.ycombinator.com/item?id=41884187](https://news.ycombinator.com/item?id=41884187)
													- [https://news.ycombinator.com/item?id=41809351](https://news.ycombinator.com/item?id=41809351)
													- [https://news.ycombinator.com/item?id=41639205](https://news.ycombinator.com/item?id=41639205)
													- [https://news.ycombinator.com/item?id=41384888](https://news.ycombinator.com/item?id=41384888)
										- Limited extensions API
										  collapsed:: true
											- Microsoft's own extension GitHub Copilot gets new APIs whenever it needs them, however competitor AI extensions have to create a fork of VSCode since there's no escape hatch
											- Competitors who forked
												- Cursor
										- ((6550215b-37e8-4e32-8c81-7d82e21d9091)) : ((65a10afb-7a18-4986-b447-6fb920d445bc))
									- Unclear
									- Comparisons
										- ((63209272-1088-4824-a762-4ac7ded04b0a)) vs ((663341b5-ddd5-4338-a332-195f59f96fd3))
										  id:: 17d08eab-9922-43c4-ab70-efcc65f70a87
										  collapsed:: true
											- For ((63209272-1088-4824-a762-4ac7ded04b0a))
												- It becomes more fragile if you're relying on lots of 3rd-party plugins. Whereas VSCode has first-party support for a lot of features
												- More popular so there's better first-party support and bigger ecosystem
												- First-class support for ((65a98a51-c5ee-45c7-ab5c-ea0e298dc618))
												- Many extensions, libraries and frameworks only support this editor
											- For ((663341b5-ddd5-4338-a332-195f59f96fd3))
												- Fast - it launches in ~100ms and has ultra-low typing latency. In comparison to Electron + [[JavaScript]] VSCode bloat
												- tmux panes for fast navigation
												- More customisable
											- Similarities
												- ((634d22db-89bb-432b-8dcf-776e2bd185ba)) motions are possible - either natively or via a plugin (e.g. ((66438a0f-0790-4d4c-a2e4-c86fbcf2af33)) ), and they dramatically improve efficiency
												- fast autocompletion as I type, goto definition, and automated refactor support; and a side-drawer file browser navigable with Vim motions
												- Language Server Provider (LSP) support
											- Unclear
												- ((671377eb-39eb-4971-a3cb-bdbb8c34568f))
											- {Archive}
												- [From VSCode To Vim | Prime Reacts - YouTube](https://youtu.be/-cn3MAovsN4)
												- [I Love Neovim But I WONT Use It | Prime Reacts - YouTube](https://youtu.be/h0YWSS9tfao)
												-
											- Related: ((9c059bb1-0976-45e5-b420-676c8acdad61))
										- ((2d8c7676-32a7-4432-9fdb-761bb1c1e6c3))
								- # Documentation
									- Versions
									  collapsed:: true
										- _Install a version_
											- _Current version_
												- Native
													- https://code.visualstudio.com/docs/setup/linux
													- Installing it via CLI and keeping it automatically updated is tricky. Easiest is installing the DEB then `apt` will take care of the rest [[2024-01-20 Saturday]]
													  `/home/boss/Documents/ESSENTIALS/Programs/vscode_1.85.2-1705561292_amd64.deb`
												- [Visual Studio Code - Flatpak](https://flathub.org/en-GB/apps/com.visualstudio.code)
												  id:: 6550215b-37e8-4e32-8c81-7d82e21d9091
												  collapsed:: true
													- Pros/Cons
														- Pros
															-
														- Cons
															- [Some configuration to execute commands in host system rather than isolated environment](https://github.com/flathub/com.visualstudio.code#usage)
															  id:: 65a10afb-7a18-4986-b447-6fb920d445bc
															  collapsed:: true
																- Either:
																  collapsed:: true
																	- ### Execute commands in the host system.
																	  For one-off commands
																		- To execute commands on the host system, run inside the sandbox:
																			- `$ flatpak-spawn --host <COMMAND>`
																			- or
																			- `$ host-spawn <COMMAND>`
																		- Most users seem to report a better experience with `host-spawn`
																	- ### Use host shell in the integrated terminal.
																	  collapsed:: true
																	  For permanent host shell
																		- Another option to execute commands is to use your host shell in the integrated terminal instead of the sandbox one.
																		- For that go to `File -> Preferences -> Settings` and find `Terminal > Integrated > Profiles`, then click on `Edit in settings.json` (The important thing here is to open settings.json)
																		- And make sure that you have the following lines there:
																		- `flatpak-spawn --host`
																			- ```
																			  {
																			    "terminal.integrated.defaultProfile.linux": "bash",
																			    "terminal.integrated.profiles.linux": {
																			      "bash": {
																			        "path": "/usr/bin/flatpak-spawn",
																			        "args": ["--host", "--env=TERM=xterm-256color", "bash"],
																			        "icon": "terminal-bash",
																			        "overrideName": true
																			      }
																			    }
																			  }
																			  ```
																		- `host-spawn`
																		  id:: a84ad5ae-90c8-4566-9055-58c3c144480e
																			- ```
																			  {
																			    "terminal.integrated.defaultProfile.linux": "bash",
																			    "terminal.integrated.profiles.linux": {
																			      "bash": {
																			        "path": "/app/bin/host-spawn",
																			        "args": ["bash"],
																			        "icon": "terminal-bash",
																			        "overrideName": true
																			      }
																			    }
																			  }
																			  ```
																		- You can change **bash** to any terminal you are using: zsh, fish, sh.
																		- `overrideName` allows for the 'name' (or whatever you set it to) of the shell you're using to appear (e.g. normally zsh, fish, sh).
																- [[2024-03-27 Wednesday]] Changed to ((a84ad5ae-90c8-4566-9055-58c3c144480e)) version, removed old config:
																	- ```
																	    "terminal.integrated.profiles.linux": {
																	    
																	      "bash": {
																	        "path": "bash",
																	        "icon": "terminal-bash"
																	      },
																	      "zsh": {
																	        "path": "zsh"
																	      },
																	      "fish": {
																	        "path": "fish"
																	      },
																	      "tmux": {
																	        "path": "tmux",
																	        "icon": "terminal-tmux"
																	      },
																	      "pwsh": {
																	        "path": "pwsh",
																	        "icon": "terminal-powershell"
																	      }
																	    }
																	  ```
															- Lacks
																- [Install gpg2 and forward gpg-agent · Issue #56 · flathub/com.visualstudio.code · GitHub](https://github.com/flathub/com.visualstudio.code/issues/56) - prevents code signing
																	- Related:
																		- [Git: Support prompting for GPG password · Issue #43809 · microsoft/vscode · GitHub](https://github.com/microsoft/vscode/issues/43809#issuecomment-2023360396)
																		- https://docs.github.com/en/authentication/managing-commit-signature-verification
																		-
																- [I have to login with Github on every launch for sync to work. · Issue #426 · flathub/com.visualstudio.code · GitHub](https://github.com/flathub/com.visualstudio.code/issues/426#issuecomment-1975175558)
																- [Improve default experience with Devcontainers · Issue #203 · flathub/com.visualstudio.code · GitHub](https://github.com/flathub/com.visualstudio.code/issues/203#issue-802483421)
																- [Visual Studio Code is unable to watch for file changes in this large workspace" (error ENOSPC) · Issue #29 · flathub/com.visualstudio.code · GitHub](https://github.com/flathub/com.visualstudio.code/issues/29)
																- [could you guys add toolbox to the flatpak for the ultimate sandboxed dev epereince? · Issue #264 · flathub/com.visualstudio.code · GitHub](https://github.com/flathub/com.visualstudio.code/issues/264#issuecomment-1256595190)
																	- [Toolbox and Visual Studio Code Remote Containers - Fedora Discussion](https://discussion.fedoraproject.org/t/toolbox-and-visual-studio-code-remote-containers/27987)
																- [Wayland support](https://github.com/flathub/com.visualstudio.code/issues/471)
																- [Support for Remote SSH extension as an alternative](https://github.com/flathub/com.visualstudio.code/issues/76) to ((65a10afb-7a18-4986-b447-6fb920d445bc))
														- Unclear
														- Comparisons
											- VSCodium (most frequently updated libre version)
											  collapsed:: true
												- Pros/Cons
												  collapsed:: true
													- Pros
													  collapsed:: true
														- Telemetry removed, unlike VSCode where is has to be removed
													- Cons
													  collapsed:: true
														- It stops many extensions from being installed, including FOSS ones like GitHub login and proprietary ones like remote containers
														  source:: [https://github.com/privacyguides/privacyguides.org/discussions/1394](https://github.com/privacyguides/privacyguides.org/discussions/1394)
														- VSCode allows viewing telemetry already
														  [https://code.visualstudio.com/docs/getstarted/telemetry#_viewing-all-telemetry-events](https://code.visualstudio.com/docs/getstarted/telemetry#_viewing-all-telemetry-events)
													- Unclear
													  collapsed:: true
														- Open VSX marketplace is used instead of proprietary Visual Studio Marketplace
														  collapsed:: true
														  [https://github.com/eclipse/openvsx](https://github.com/eclipse/openvsx)
															- Ideally MS would allow extension marketplace to be configured in the app's settings instead of baked-in at build time. I'm not sure if this is on their roadmap (but doubtful since they will want everyone using their proprietary marketplace).
														- product.json can be edited in order to access Microsoft's extension gallery
														  source:: [https://github.com/VSCodium/vscodium/pull/674#issuecomment-1137920704](https://github.com/VSCodium/vscodium/pull/674#issuecomment-1137920704)
														  collapsed:: true
															- e.g.
															  {
															    "extensionsGallery": {
															      "serviceUrl": "[https://marketplace.visualstudio.com/_apis/public/gallery](https://marketplace.visualstudio.com/_apis/public/gallery)",
															      "cacheUrl": "<a href="https://vscode.blob.core.windows.net/gallery/index">https://vscode.blob.core.windows.net/gallery/index</a>",
															      "itemUrl": "<a href="https://marketplace.visualstudio.com/items">https://marketplace.visualstudio.com/items</a>"
															    }
															  }
															- having to change `/var/lib/flatpak/app/com.vscodium.codium/current/active/files/share/codium/resources/app/product.json` on every update.
												- VSCodium (libre version)
												  https://github.com/VSCodium/vscodium
												- Flatpak
												  collapsed:: true
												  flatpak install flathub com.vscodium.codium
													- [https://flathub.org/apps/details/com.vscodium.codium](https://flathub.org/apps/details/com.vscodium.codium)
													- Repo
													  [https://github.com/flathub/com.vscodium.codium](https://github.com/flathub/com.vscodium.codium)
												- Snap build
												  [https://snapcraft.io/codium](https://snapcraft.io/codium)
											- OSS (libre)
											  collapsed:: true
												- flatpak install flathub com.visualstudio.code.oss
												- [https://flathub.org/apps/details/com.visualstudio.code.oss](https://flathub.org/apps/details/com.visualstudio.code-oss)
												- [https://github.com/flathub/com.visualstudio.code.oss](https://github.com/flathub/com.visualstudio.code.oss)
												- End of life?
												  [https://github.com/flathub/com.visualstudio.code.oss/issues/46#issuecomment-644656335](https://github.com/flathub/com.visualstudio.code.oss/issues/46#issuecomment-644656335)
												- _Comparison to VSCodium_
												  collapsed:: true
													- VSCodium also jumps through a couple of hoops to remove Microsoft's telemetry
											- Snap
											  collapsed:: true
											  `sudo snap install vscode --classic`
												- _Downloads_
												  collapsed:: true
													- https://code.visualstudio.com/
													- Snap
													  sudo snap install vscode --classic
													- Flatpak
													  collapsed:: true
													  flatpak install flathub com.visualstudio.code
														- https://flathub.org/apps/details/com.visualstudio.code
												- [Docs](https://code.visualstudio.com/docs)
												- _Setup_
													- Settings > Application > Telemetry > disable both options
												- Extensions
										- [Web Visual Studio Code](https://vscode.dev)
										  collapsed:: true
											- _Built on it _
												- [GitHub Dev](https://github.dev) - for exploring repos without downloading it to your machine
												- [GitHub Codespaces](https://github.com/features/codespaces)
												  id:: 6491f81a-cba0-4710-b8fc-2a0b5bd7d7af
												  collapsed:: true
													- Also supports working locally on Visual Studio Code
													  [https://visualstudio.microsoft.com/services/github-codespaces/](https://visualstudio.microsoft.com/services/github-codespaces/)
												- Gitpod
												  collapsed:: true
													- [https://www.gitpod.io/](https://www.gitpod.io/)
													- [https://github.com/gitpod-io/gitpod](https://github.com/gitpod-io/gitpod)
													- Documentation
													  collapsed:: true
														- e.g. open any repo in a web VSC
														  [https://gitpod.io/#https://github.com/jupyterlab/jupyterlab](https://gitpod.io/#https://github.com/jupyterlab/jupyterlab)
														- Look at any PR (pull request) in a full coding environment where you can edit, build, and test the PR code, by just prepending "[gitpod.io](http://gitpod.io)#" to the PR URL. Super useful for reviewing/testing stuff without having to check it out locally!
											- GistPad
											  collapsed:: true
												- VSC extension which lets you edit repos and gists without having to push
												  [https://marketplace.visualstudio.com/items?itemName=vsls-contrib.gistfs#repositories](https://marketplace.visualstudio.com/items?itemName=vsls-contrib.gistfs#repositories)
									- Language support
									  collapsed:: true
										- Built in support for JavaScript, TypeScript and Node.js. Extensive ecosystem of xtensions for other languages (e.g. C++, C#, Java, Python, PHP, Go) and runtimes (e.g. .NET, Unity)
									- [Keybindings](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf)
									  id:: 633a1738-6a4c-414b-bfda-1e537b0ba941
									  collapsed:: true
										- Keyboard shortcuts
											- Basics
											  collapsed:: true
												- Open a folder: **File** > **Open Folder** (Ctrl+K Ctrl+O)
												- File Explorer: **View** > **Explorer** (Ctrl+Shift+E)
												- Search view: **View** > **Search** (Ctrl+Shift+F)
												- Source Control
												- **View** > **Source Control (SCM)** (Ctrl+Shift+G)
												- Run and Debug
												- **View** > **Run** (Ctrl+Shift+D)
												- Extensions view
												- **View** > **Extensions** (Ctrl+Shift+X)
												- Open the Command Palette.
												- **View** > **Command Palette...** (Ctrl+Shift+P)
												- Output panel
												- **View** > **Output** (Ctrl+K Ctrl+H)
												- Debug Console
												- **View** > **Debug Console** (Ctrl+Shift+Y)
												- Problems panel
												- **View** > **Problems** (Ctrl+Shift+M)
												- Integrated Terminal
												- **View** > **Terminal** (Ctrl+`)
												- Create a new file
												- **File** > **New File** (Ctrl+N)
												- Save a file
												- **File** > **Save** (Ctrl+S)
												- Auto Save
												- **File** > **Auto Save**
												- Run
												- **Run** > **Start Debugging** (F5)
												- Programming language extensions
											- Full
											  id:: 62d69b1f-e70c-44f4-9e96-50033d4c3ca0
												- https://vscode-shortcuts.com/
										- Native
											- [Keybindings](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf) / ![keyboard-shortcuts-linux.pdf](../assets/keyboard-shortcuts-linux_1664537768592_0.pdf)
												- Learn shortcuts for
													- duplicating lines of text
														- ((6341c0c5-e269-4ec4-90c2-eec891ca4208))
													- deleting a whole line
														- ((6341ac77-ca89-44c7-8961-e862e3717abe))
													- selecting and moving a whole line at once
														- ((6341ad83-4cb3-4fca-8272-f413353faa9c))
													- multi-cursor for editing things on multiple lines simultaneously
														- ((6341af58-0702-454d-b064-b0a237f05529))
												- Priority to practice
													- ((6341c0c5-3f09-420f-833c-96b8e3b886bc))
													- CTRL + P =
													- `CTRL + '` = Show/Hide Terminal
													- ((65a98a51-d39a-4c6c-b8da-09ce5f25b855))
													- ((6341c0c5-e269-4ec4-90c2-eec891ca4208))
													- ((6341ad83-4cb3-4fca-8272-f413353faa9c))
													- ((6341ad99-9468-4b4d-9616-95cfef29b058))
													- ((6341ac77-ca89-44c7-8961-e862e3717abe))
													- ((6341af58-0702-454d-b064-b0a237f05529))
													- ((6341afef-9d8e-42ca-84ff-0a6383646167))
													- alt+shift+o to remove unused imports in current file
													- Ctrl + alt + up/down to add cursor to multiple lines. Similarly, alt + click to put cursor on multiple lines more selectively.
													- ALT + Z = Word wrap
													- vim-mode
												- Notable excerpts
													- ((63974fb1-466d-4bc3-a061-775c074f4e35))
													- *General*
														- `CTRL + SHIFT + P`/`F1` = Show Command Palette
														  id:: 6341c0c5-3f09-420f-833c-96b8e3b886bc
														- `CTRL + K` = Modifier prefix (does nothing by itself)
															- `CTRL + S` = Show keyboard shortcuts
															- `CTRL + C` = Add line comment
															- `CTRL + J` = Unfold all
															- `Z` = Toggle Zen mode
														- ((6341d63d-cb12-465e-b936-e7efac4abf91))
														- `CTRL + ALT + N` = Run Code (play button in top-right)
														  id:: 6540df86-e6fa-44aa-8a73-f1aed1f04708
													- Basic editing
														- `Home` = Go to beginning of line
														- `End` = Go to end of line
														- `CTRL + X` = Cut line (empty selection)
														  id:: 65a98a51-d39a-4c6c-b8da-09ce5f25b855
														- `CTRL + C` = Copy line (empty selection)
														  id:: 6341c0c5-e269-4ec4-90c2-eec891ca4208
														- `ALT + Up arrow` = Move line up
														  id:: 6341ad83-4cb3-4fca-8272-f413353faa9c
														- `ALT + Down arrow` = Move line down
														  id:: 6341ad99-9468-4b4d-9616-95cfef29b058
														- `CTRL + SHIFT + K` = Delete line
														  id:: 6341ac77-ca89-44c7-8961-e862e3717abe
														- `CTRL + ENTER` = Insert line below
														- `CTRL + SHIFT + ENTER` = Insert line above
														- `CTRL + Up arrow` = Scroll line up
														- `CTRL + Down arrow` = Scroll line down
														- `ALT + PgUp` = Scroll page up
														- `ALT + PgDn` = Scroll page down
														- `CTRL + /` = Toggle line comment
														- `CTRL + SHIFT + A` = Toggle block comment
													- Multi-cursor and selection
														- `ALT + LMB` = Insert cursor
														  id:: 6341af58-0702-454d-b064-b0a237f05529
														- `CTRL + L` = Select current line
														- `CTRL + SHIFT + L` = Select all occurrences of current selection
													- Search and replace
														- `CTRL + D` = Add selection to next Find match
														  id:: 6341afef-9d8e-42ca-84ff-0a6383646167
														  collapsed:: true
															- Can use it multiple times in a row to quickly select all instances of `characters` and replace them
															- Blue bar at the bottom will say how many selections there are
													- Editor management
														- `CTRL + W` = Close editor
														- `CTRL + \` = Split editor
														- `CTRL +` `1/2/3` = Focus into 1st, 2nd, 3rd editor group (up to 3 columns)
													- Integrated terminal
														- `CTRL +` ` = Show integrated terminal
											- Other
												- CTRL + click on things like `useEffect` and it'll take us to the function/docs for it
												  id:: 639cbe58-b353-4d24-9896-8fb9673e47db
										- ((663a5797-5411-4f41-803d-de09666547a9))-based
											- ((663b63f5-e0ab-40c3-af11-e6d5bd63fe4a))
												- ((66438a0f-0790-4d4c-a2e4-c86fbcf2af33))
									- Extensions
									  id:: 663a5797-5411-4f41-803d-de09666547a9
									  collapsed:: true
										- _Meta_
											- CTRL+P then `ext install
											  `ext install ritwickdey.LiveServer` to install Live Server by Ritwick Dey
											- [In Visual Studio Code go to Settings > Workspace settings > Tab size: 2 (2 is what JavaScript typically uses by convention)](((629ccb27-c9e2-4419-9e39-4b026e14abd4)))
											- Obtaining VSIX files via `wget`
											  collapsed:: true
												- `https://${publisher}.gallery.vsassets.io/_apis/public/gallery/publisher/${publisher}/extension/${extension name}/${version}/assetbyname/Microsoft.VisualStudio.Services.VSIXPackage`
												- [Bookmarklet version](https://gist.github.com/wanglf/7acc591890dc0d8ceff1e7ec9af32a55)
										- Current
											- *Deprecate?*
												- ((643fbc87-6caf-4a74-bba7-4dab9b82b2f2))
											- List
											  collapsed:: true
											  Last updated: [[2023-04-19 Wednesday]]
												- [AWS Toolkit - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.aws-toolkit-vscode)
												  collapsed:: true
													- [AWS Infrastructure Composer](https://aws.amazon.com/infrastructure-composer/)
													  id:: 663a916d-d09c-495c-a76d-8b6fc2723a4e
													  AKA [AWS Application Composer](https://aws.amazon.com/about-aws/whats-new/2024/10/aws-application-composer-infrastructure-composer/)
														- [Working with AWS Application Composer from the Toolkit - AWS Toolkit for VS Code](https://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/appcomposer-overview.html)
														- [My experience with using AWS Application Composer](https://dev.to/aws-builders/my-experience-with-using-aws-application-composer-in-visual-studio-code-143p) in ((63209272-1088-4824-a762-4ac7ded04b0a))
														- AWS Application Composer is a visual builder that enables developers to design, build, and iterate on an application architecture by dragging, grouping, and connecting AWS services on a visual canvas. It is now available as an extension for Visual Studio Code (VS Code).
														- With AWS Application Composer in VS Code, you can:
															- Visually design applications using an interactive canvas
															- Drag and drop AWS services to create an application architecture
															- Generate Infrastructure as Code (IaC) templates in real-time
															- Simplify building modern applications with a visual drag-and-drop interface
															- Use AI-generated IaC templates to speed up development
												- [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
												  collapsed:: true
													- Id: formulahendry.auto-close-tag
													  Description: Automatically add HTML/XML close tag, same as Visual Studio IDE or Sublime Text
													  Version: 0.5.14
													  Publisher: Jun Han
												- [Auto Comment](https://marketplace.visualstudio.com/items?itemName=AkvelonPrimary.autocomment)
												  collapsed:: true
													- Name: Auto Comment
													  Id: AkvelonPrimary.autocomment
													  Description: Generate code comments automatically with AI
													  Version: 1.4.10
													  Publisher: Akvelon
												- AWS Toolkit
												- [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
												  collapsed:: true
													- Name: Auto Rename Tag
													  Id: formulahendry.auto-rename-tag
													  Description: Auto rename paired HTML/XML tag
													  Version: 0.1.10
													  Publisher: Jun Han
												- [Babel JavaScript](https://marketplace.visualstudio.com/items?itemName=mgmcdermott.vscode-language-babel)
												  collapsed:: true
													- Name: Babel JavaScript
													  Id: mgmcdermott.vscode-language-babel
													  Description: VSCode syntax highlighting for today's JavaScript
													  Version: 0.0.38
													  Publisher: Michael McDermott
													  VS Marketplace Link:
												- [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments)
												  collapsed:: true
													- Name: Better Comments
													  Id: aaron-bond.better-comments
													  Description: Improve your code commenting by annotating with alert, informational, TODOs, and more!
													  Version: 3.0.2
													  Publisher: Aaron Bond
												- [Better Folding](https://marketplace.visualstudio.com/items?itemName=MohammadBaqer.better-folding)
												  collapsed:: true
													- Name: Better Folding
													  Id: MohammadBaqer.better-folding
													  Description: Improve the folding experience in VS Code
													  Version: 0.5.1
													  Publisher: Mohammad Baqer
												- [Blockman](https://marketplace.visualstudio.com/items?itemName=leodevbro.blockman)
												  collapsed:: true
													- Name: Blockman - Highlight Nested Code Blocks
													  Id: leodevbro.blockman
													  Description: Mark/Highlight code blocks
													  Version: 1.7.2
													  Publisher: leodevbro
												- [C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)
												  collapsed:: true
													- Name: C#
													  Id: ms-dotnettools.csharp
													  Description: C# for Visual Studio Code (powered by OmniSharp).
													  Version: 1.25.4
													  Publisher: Microsoft
												- [ChatGPT - Genie AI](https://marketplace.visualstudio.com/items?itemName=genieai.chatgpt-vscode)
												  id:: 643fbc87-6caf-4a74-bba7-4dab9b82b2f2
												  collapsed:: true
													- Name: ChatGPT - Genie AI
													  Id: genieai.chatgpt-vscode
													  Description: Your best AI pair programmer. Save conversations and continue any time. A Visual Studio Code - ChatGPT Integration. Supports GPT-4, GPT3.5, GPT3 and Codex models. Create new files, view diffs with one click; your copilot to learn code, add tests, find bugs and more.
													  Version: 0.0.8
													  Publisher: Genie AI
												- [CodeSnap](https://marketplace.visualstudio.com/items?itemName=adpyke.codesnap)
												  collapsed:: true
													- Name: CodeSnap
													  Id: adpyke.codesnap
													  Description: 📷 Take beautiful screenshots of your code
													  Version: 1.3.4
													  Publisher: adpyke
												- [Color Highlight](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)
												  collapsed:: true
													- Name: Color Highlight
													  Id: naumovs.color-highlight
													  Description: Highlight web colors in your editor
													  Version: 2.5.0
													  Publisher: Sergii N
												- [Console Ninja](https://marketplace.visualstudio.com/items?itemName=WallabyJs.console-ninja)
												  collapsed:: true
													- Name: Console Ninja
													  Id: WallabyJs.console-ninja
													  Description: JavaScript console.log output and runtime errors right next to your code.
													  Version: 0.0.109
													  Publisher: Wallaby.js
												- [CSS Peek](https://marketplace.visualstudio.com/items?itemName=pranaygp.vscode-css-peek)
												  collapsed:: true
													- Name: CSS Peek
													  Id: pranaygp.vscode-css-peek
													  Description: Allow peeking to css ID and class strings as definitions from html files to respective CSS. Allows peek and goto definition.
													  Version: 4.2.0
													  Publisher: Pranay Prakash
												- [CSS-in-JS](https://marketplace.visualstudio.com/items?itemName=paulmolluzzo.convert-css-in-js)
												  collapsed:: true
													- Name: CSS-in-JS
													  Id: paulmolluzzo.convert-css-in-js
													  Description: CSS-in-JS autocomplete and conversion
													  Version: 1.1.3
													  Publisher: paulmolluzzo
												- [Debugger for Firefox](https://marketplace.visualstudio.com/items?itemName=firefox-devtools.vscode-firefox-debug)
												  collapsed:: true
													- Name: Debugger for ((63134593-906c-43b5-96fe-33dc2c34fda4))
													  Id: firefox-devtools.vscode-firefox-debug
													  Description: Debug your web application or browser extension in Firefox
													  Version: 2.9.8
													  Publisher: Firefox DevTools
												- [DotENV](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv)
												  id:: 6550215b-740f-4834-ba42-591ac54df33f
												  collapsed:: true
													- Name: DotENV
													  Id: mikestead.dotenv
													  Description: Support for dotenv file syntax
													  Version: 1.0.1
													  Publisher: mikestead
													- [[2023-11-01 Wednesday]] Node.js 20.6.0 brings support for loading environment variable files. Reading directly from process.env has issues such as lack of type safety, validation, and immutability. Zod is a library used to parse and validate environment variables.
													- Related: ((63590e56-9473-4435-9a86-177587b4ddff))
												- [Draw.io Integration](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio)
												  collapsed:: true
													- Name: Draw.io Integration
													  Id: hediet.vscode-drawio
													  Description: This unofficial extension integrates Draw.io into VS Code.
													  Version: 1.6.6
													  Publisher: Henning Dieterichs
												- [EditorConfig for VS Code]( [We're sorry, the page you requested cannot be found.](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig))
												  collapsed:: true
													- Name: EditorConfig for VS Code
													  Id: EditorConfig.EditorConfig
													  Description: EditorConfig Support for Visual Studio Code
													  Version: 0.16.4
													  Publisher: EditorConfig
												- Name: Error Lens
												  Id: usernamehw.errorlens
												  Description: Improve highlighting of errors, warnings and other language diagnostics.
												  Version: 3.8.0
												  Publisher: Alexander
												  VS Marketplace Link: [Error Lens - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)
												- Name: ESLint
												  Id: dbaeumer.vscode-eslint
												  Description: Integrates ESLint JavaScript into VS Code.
												  Version: 2.4.0
												  Publisher: Microsoft
												  VS Marketplace Link: [ESLint - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
												- Name: Git Config User Profiles
												  id:: 6550215b-1c6b-42b9-8be6-c1ec20aacade
												  collapsed:: true
												  Id: onlyutkarsh.git-config-user-profiles
												  Description: Define multiple git config user profiles and switch them easily using status bar
												  Version: 1.2.0
												  Publisher: Utkarsh Shigihalli
												  VS Marketplace Link: [Git Config User Profiles - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=onlyutkarsh.git-config-user-profiles)
													- [GitHub - onlyutkarsh/git-config-user-profiles: A Visual Studio Code extension to define multiple git config user profiles and switch them easily using status bar](https://github.com/onlyutkarsh/git-config-user-profiles)
													- Troubleshooting
														- `MY_SIGNING_KEY` is your ~14 character key - ((660ddbe8-5ae0-4487-9eb9-0fef0f935347))
														- `git commit -m 'test' -S`
														  Make a commit which is signed with GPG
														- ((660e92b1-c41b-4b0e-a9ff-90d81b994008)) : ((660e929e-982b-4b5e-bc9e-14a9ff01e60a))
													- ((6463498e-c3ca-4659-94c6-4a40ec7f3743))
												- Name: Git History
												  Id: donjayamanne.githistory
												  Description: View git log, file history, compare branches or commits
												  Version: 0.6.20
												  Publisher: Don Jayamanne
												  VS Marketplace Link: [Git History - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)
												- Name: GitHub Copilot
												  id:: 65a98a51-c5ee-45c7-ab5c-ea0e298dc618
												  Id: GitHub.copilot
												  Description: Your AI pair programmer
												  Version: 1.82.15
												  Publisher: GitHub
												  VS Marketplace Link: [GitHub Copilot - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
												- Name: GitHub Copilot Labs
												  Id: GitHub.copilot-labs
												  Description: Experimental features for GitHub Copilot
												  Version: 0.12.791
												  Publisher: GitHub
												  VS Marketplace Link: [GitHub Copilot Labs - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-labs)
												- Name: GitHub Pull Requests and Issues
												  Id: GitHub.vscode-pull-request-github
												  Description: Pull Request and Issue Provider for GitHub
												  Version: 0.60.0
												  Publisher: GitHub
												  VS Marketplace Link: [GitHub Pull Requests and Issues - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)
												- Name: GitLens — Git supercharged
												  Id: eamodio.gitlens
												  Description: Supercharge Git within VS Code — Visualize code authorship at a glance via Git blame annotations and CodeLens, seamlessly navigate and explore Git repositories, gain valuable insights via rich visualizations and powerful comparison commands, and so much more
												  Version: 13.5.0
												  Publisher: GitKraken
												  VS Marketplace Link: [GitLens — Git supercharged - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
												- Name: hightlight-selections-vscode
												  Id: cliffordfajardo.hightlight-selections-vscode
												  Description: Select or double click a word to highlight it in your editor.
												  Version: 0.0.1
												  Publisher: Clifford Fajardo
												  VS Marketplace Link: [hightlight-selections-vscode - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=cliffordfajardo.hightlight-selections-vscode)
												- [Indent-Rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow)  -  is great for Python readability
												- [Indenticator - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=SirTori.indenticator)
												  collapsed:: true
													- Name: Indenticator
													  Id: SirTori.indenticator
													  Description: Highlights your current indent depth
													  Version: 0.7.0
													  Publisher: SirTori
													  VS Marketplace Link:
												- Name: JavaScript (ES6) code snippets
												  Id: xabikos.JavaScriptSnippets
												  Description: Code snippets for JavaScript in ES6 syntax
												  Version: 1.8.0
												  Publisher: charalampos karypidis
												  VS Marketplace Link: [JavaScript (ES6) code snippets - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=xabikos.JavaScriptSnippets)
												- Name: learn-markdown
												  Id: docsmsft.docs-markdown
												  Description: Learn Markdown Extension
												  Version: 1.0.1
												  Publisher: Microsoft
												  VS Marketplace Link: [learn-markdown - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown)
												- Name: learn-preview
												  Id: docsmsft.docs-preview
												  Description: Learn Markdown Preview Extension
												  Version: 1.0.1
												  Publisher: Microsoft
												  VS Marketplace Link: [learn-preview - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-preview)
												- Name: Live Server
												  Id: ritwickdey.LiveServer
												  Description: Launch a development local Server with live reload feature for static & dynamic pages
												  Version: 5.7.9
												  Publisher: Ritwick Dey
												  VS Marketplace Link: [Live Server - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
												- Name: Live Share
												  Id: ms-vsliveshare.vsliveshare
												  Description: Real-time collaborative development from the comfort of your favorite tools.
												  Version: 1.0.5862
												  Publisher: Microsoft
												  VS Marketplace Link: [Live Share - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)
												- Name: Live Share Extension Pack
												  Id: ms-vsliveshare.vsliveshare-pack
												  Description: Collection of extensions that enable real-time collaborative development with VS Live Share.
												  Version: 0.4.0
												  Publisher: Microsoft
												- Name: Markdown All in One
												  Id: yzhang.markdown-all-in-one
												  Description: All you need to write Markdown (keyboard shortcuts, table of contents, auto preview and more)
												  Version: 3.5.1
												  Publisher: Yu Zhang
												  VS Marketplace Link: [Markdown All in One - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
												- Name: Markdown Preview Github Styling
												  Id: bierner.markdown-preview-github-styles
												  Description: Changes VS Code's built-in markdown preview to match Github's style
												  Version: 2.0.0
												  Publisher: Matt Bierner
												  VS Marketplace Link: [Markdown Preview Github Styling - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-preview-github-styles)
												- Name: Nix
												  Id: bbenoist.Nix
												  Description: Nix language support for Visual Studio Code.
												  Version: 1.0.1
												  Publisher: Baptist BENOIST
												  VS Marketplace Link: [Nix - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=bbenoist.Nix)
												- Name: npm Intellisense
												  Id: christian-kohler.npm-intellisense
												  Description: Visual Studio Code plugin that autocompletes npm modules in import statements
												  Version: 1.4.4
												  Publisher: Christian Kohler
												  VS Marketplace Link: [npm Intellisense - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)
												- Name: Path Intellisense
												  Id: christian-kohler.path-intellisense
												  Description: Visual Studio Code plugin that autocompletes filenames
												  Version: 2.8.4
												  Publisher: Christian Kohler
												  VS Marketplace Link: [Path Intellisense - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
												- ((63dc1965-e60c-418a-b045-991a2def0768))
												- [Pretty TypeScript Errors - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=yoavbls.pretty-ts-errors)
												  collapsed:: true
													- Name: Pretty TypeScript Errors
													  Id: yoavbls.pretty-ts-errors
													  Description: Make TypeScript errors prettier and more human-readable in VSCode
													  Version: 0.2.8
													  Publisher: yoavbls
													  VS Marketplace Link: [Pretty TypeScript Errors - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=yoavbls.pretty-ts-errors)
												- [Reactjs code snippets](https://marketplace.visualstudio.com/items?itemName=xabikos.ReactSnippets)
												  id:: 64245c51-a2eb-47d1-8c08-c6cbd2df10e8
												  collapsed:: true
													- Name: Reactjs code snippets
													  Id: xabikos.ReactSnippets
													  Description: Code snippets for Reactjs development in ES6 syntax
													  Version: 2.4.0
													  Publisher: charalampos karypidis
													  VS Marketplace Link: [Reactjs code snippets - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=xabikos.ReactSnippets)
													- Allows you to type in a word then click TAB and it'll generate boilerplate React code
													- Snippets
														- Most important
															- `rsf`
															  id:: 642467cf-3b53-4937-bb28-423eac048fee
														- Basic
															- | Trigger | Content |
															  | `rcc→` | class component skeleton | 
															  | `rrc→` | class component skeleton with react-redux connect | 
															  | `rrdc→` | class component skeleton with react-redux connect and dispatch |
															  | `rccp→` | class component skeleton with prop types after the class | 
															  | `rcjc→` | class component skeleton without import and default export lines | 
															  | `rcfc→` | class component skeleton that contains all the lifecycle methods |
															  | `rwwd→`| class component without import statements | 
															  | `rpc→` | class pure component skeleton with prop types after the class |
															  | `rsc→` | stateless component skeleton | 
															  | `rscp→` | stateless component with prop types skeleton |
															  | `rscm→`| memoize stateless component skeleton | 
															  | `rscpm→` | memoize stateless component with prop types skeleton | 
															  | `rsf→` | stateless named function skeleton | 
															  | `rsfp→` | stateless named function with prop types skeleton | 
															  | `rsi→` | stateless component with prop types and implicit return | 
															  | `fcc→` | class component with flow types skeleton | 
															  | `fsf→` | stateless named function skeleton with flow types skeleton | 
															  | `fsc→` | stateless component with flow types skeleton | 
															  | `rpt→` | empty propTypes declaration | 
															  | `rdp→` | empty defaultProps declaration |
															  | `con→` | class default constructor with props | | 
															  | `conc→` | class default constructor with props and context | | 
															  | `est→` | empty state object | 
															  | `cwm→` | `componentWillMount method` | 
															  | `cdm→` | `componentDidMount method` | 
															  | `cwr→` | `componentWillReceiveProps method` | 
															  | `scu→` | `shouldComponentUpdate method` | 
															  | `cwup→` | `componentWillUpdate method` |
															  | `cdup→` | `componentDidUpdate method` | 
															  | `cwun→` | `componentWillUnmount method` |
															  | `gsbu→` | `getSnapshotBeforeUpdate method` |
															  | `gdsfp→` | `static getDerivedStateFromProps method` | 
															  | `cdc→` | `componentDidCatch method` || `ren→` | `render method` | | 
															  | `sst→` | `this.setState with object as parameter` | 
															  | `ssf→` | `this.setState with function as parameter` | 
															  | `props→` | `this.props` | 
															  | `state→` | `this.state` | 
															  | `bnd→` | `binds the this of method inside the constructor` |
															  | `disp→` |	MapDispatchToProps redux function |
												- [ReacTree](https://marketplace.visualstudio.com/items?itemName=ReacTreeDev.reactree)
												  id:: 63fdf51e-fd5d-4acd-9b44-bc4eebb9ae2f
												  collapsed:: true
													- Name: ReacTree
													  Id: ReacTreeDev.reactree
													  Description: React hierarchy tree visualizer and navigation tool
													  Version: 1.0.8
													  Publisher: ReacTreeDev
													  VS Marketplace Link: [ReacTree - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ReacTreeDev.reactree)
												- [REST Client - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
												  collapsed:: true
													- Name: REST Client
													  Id: humao.rest-client
													  Description: REST Client for Visual Studio Code
													  Version: 0.25.1
													  Publisher: Huachao Mao
													  VS Marketplace Link: [REST Client - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
												- [School of Code Extension Pack - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=SchoolofCode.extension-pack)
												  collapsed:: true
													- Name: School of Code Extension Pack
													  Id: schoolofcode.extension-pack
													  Description: A set of useful extensions
													  Version: 0.0.1
													  Publisher: School of Code
													  VS Marketplace Link: [School of Code Extension Pack - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=SchoolofCode.extension-pack)
												- [Tailwind CSS IntelliSense - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
												  collapsed:: true
													- Name: Tailwind CSS IntelliSense
													  Id: bradlc.vscode-tailwindcss
													  Description: Intelligent Tailwind CSS tooling for VS Code
													  Version: 0.9.11
													  Publisher: Tailwind Labs
													  VS Marketplace Link:
												- [TODO Highlight - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight)
												  collapsed:: true
													- Name: TODO Highlight
													  Id: wayou.vscode-todo-highlight
													  Description: highlight TODOs, FIXMEs, and any keywords, annotations...
													  Version: 1.0.5
													  Publisher: Wayou Liu
													  VS Marketplace Link:
												- [WordCounter - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=kirozen.wordcounter)
												  collapsed:: true
													- Name: WordCounter
													  Id: kirozen.wordcounter
													  Description: Complete word counter inspired by ST WordCount plugin
													  Version: 2.4.4
													  Publisher: Etienne Faisant
													  VS Marketplace Link:
												- Name: Vim
												  id:: 65a98a51-9b74-47ed-bd3d-9e989edd89b6
												  Id: vscodevim.vim
												  Description: Vim emulation for Visual Studio Code
												  Version: 1.25.2
												  Publisher: vscodevim
												  VS Marketplace Link: [Vim - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)
											- In Visual Studio Code, you can type `rfc` and then hit the `Enter` key to generate a React functional component. This will generate the basic structure of a functional component, including the function signature and the return statement.
											- If you prefer to generate a React class component instead, you can type `rcc` and then hit `Enter`. This will generate the basic structure of a class component, including the class declaration, the `render` method, and the `return` statement.
											- Note that this feature requires the "Reactjs code snippets" extension to be installed in ((63209272-1088-4824-a762-4ac7ded04b0a))
										- _Which ones_
											- Recommended by School of Code:
											  id:: 63c581b5-46ee-46d6-ac71-368398a20356
											  collapsed:: true
												- Live Share by Microsoft - allows easy real-time collaboration
												- Prettier - code formatter will improve code readability automatically
												- School of Code Extension Pack:
													- This extension pack will install a few extensions you'll find useful while going though School of Code.
														- [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
														- [hightlight-selections-vscode](https://marketplace.visualstudio.com/items?itemName=cliffordfajardo.hightlight-selections-vscode)
														- [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)
														- ((63dc17ea-92e0-4539-82ab-c666e686c832))
														  id:: 63c581b5-b3d7-4168-9022-64e32e82cf85
														- ((63dc1965-e60c-418a-b045-991a2def0768))
														  id:: 63c581b5-7bfa-4304-a600-4a5e123de8c4
														- [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
														- [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
														- [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
														- [Babel JavaScript](https://marketplace.visualstudio.com/items?itemName=mgmcdermott.vscode-language-babel)
														- [DotENV](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv)
														- [Color Highlight](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)
														- [CSS-in-JS](https://marketplace.visualstudio.com/items?itemName=paulmolluzzo.convert-css-in-js)
														- [CSS Peek](https://marketplace.visualstudio.com/items?itemName=pranaygp.vscode-css-peek)
														- [GraphQL](https://marketplace.vscode.pro/vscode-graphql)
														  id:: 6396fb64-dc81-439b-b014-ee6247cc7cbd
														- [vscode-icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons)
														- [Indenticator](https://marketplace.visualstudio.com/items?itemName=SirTori.indenticator)
														- [React Standard Style code snippets](https://marketplace.visualstudio.com/items?itemName=TimonVS.ReactSnippetsStandard)
														- [TODO Highlight](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight)
														- [JavaScript (ES6) code snippets](https://marketplace.visualstudio.com/items?itemName=xabikos.JavaScriptSnippets)
											- Markdown Editor by adamerose is a great WYSIWYG Markdown editor extension for VSCode, Button is in the bar with tab titles
											- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
												- https://addons.mozilla.org/en-US/firefox/addon/live-server-web-extension/
											- [JSHint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.jshint) - JavaScript linter (for checking code errors in realtime)
											- [GitHub - vscode-org-mode/vscode-org-mode: Emacs Org Mode for Visual Studio Code](https://github.com/vscode-org-mode/vscode-org-mode)
											- [GitHub - Helixform/CodeCursor: An extension for using Cursor in Visual Studio Code.](https://github.com/Helixform/CodeCursor)
											  Utilises ((663b634b-07a8-4f92-a8bd-dd9bacf85f10))?
											- ((634d22db-89bb-432b-8dcf-776e2bd185ba)) motions
											  id:: 663b63f5-e0ab-40c3-af11-e6d5bd63fe4a
												- [VSCode Neovim](https://marketplace.visualstudio.com/items?itemName=asvetliakov.vscode-neovim)
												  id:: 66438a0f-0790-4d4c-a2e4-c86fbcf2af33
												  collapsed:: true
												  Embeds ((663341b5-ddd5-4338-a332-195f59f96fd3))
													- [GitHub - vscode-neovim/vscode-neovim: Vim mode for VSCode, powered by Neovim](https://github.com/vscode-neovim/vscode-neovim)
													- Pros/Cons
														- Pros
															-
														- Cons
															- Lacks
																- [Issue Tracker: Folding · Issue #58 · vscode-neovim/vscode-neovim · GitHub](https://github.com/vscode-neovim/vscode-neovim/issues/58)
														- Unclear
															- Less downloads than ((634bd9e0-92dc-4026-a128-ef2248a266a0)) but [less buggy](https://youtu.be/h0YWSS9tfao?t=1268) because it embeds ((663341b5-ddd5-4338-a332-195f59f96fd3)) rather than trying to emulate ((634d22db-89bb-432b-8dcf-776e2bd185ba))
														- Comparisons
													- # Documentation
														- Installation
															- Settings: `Vscode-neovim` > `Neovim Executable Paths: Linux`
																- Change from `/usr/bin/nvim` to `io.neovim.nvim`, assuming Neovim is Flatpak and VSCode is native
																- ((663341b5-ddd5-4338-a332-195f59f96fd3)) : ((664cf776-5585-4bf6-80da-61172b4cb142)) setup required if installed this way
														- [Keybindings](https://github.com/vscode-neovim/vscode-neovim?tab=readme-ov-file#%EF%B8%8F-keybindings-shortcuts)
															-
														- It'll change cursor from a thin line between characters to a cursor that highlights a single character
														-
														- [You need to configure neovim path in vscode settings, the extension doesn't look into path env variable for now](https://github.com/vscode-neovim/vscode-neovim/issues/208)
															- `vscode-neovim.neovimPath`?
													- [Learning Resources]
														- [VSCode Neovim Extension playlist](https://youtube.com/playlist?list=PLXDouhCU5r6qRE46qQ2rYIPnbJ5a9jzmd)
															- Installation
																- `which nvim`
																	- e.g. prints `/usr/bin/nvim`
																	- Change the VSCode setting for `Neovim Executable Paths` to this
																	- See ((67a8e14d-078e-481d-8a76-18381f3443c6))
															- [Keyboard settings](https://youtu.be/z64gxcKQSRI?list=PLXDouhCU5r6qRE46qQ2rYIPnbJ5a9jzmd)
																- KDE settings > Keyboard > Delay/Repeat times can be reduced to make navigation using `hjkl` or others faster
																- He recommends in Mac OS settings to change CapsLock functionality to act as Escape key, then it's easier to quit Insert Mode
																- Recommends binding `jj` to quit Insert Mode
												- [VSCodeVim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)
												  id:: 634bd9e0-92dc-4026-a128-ef2248a266a0
												  collapsed:: true
													- [GitHub - VSCodeVim/Vim: :star: Vim for Visual Studio Code](https://github.com/VSCodeVim/Vim)
													- Cons
													  id:: 634bdb65-1bf3-42a7-9a26-20508bae188e
														- [May need to enable experimental setting to prevent poor performance](https://github.com/microsoft/vscode/issues/75627#issuecomment-1114048271)
														-
													- https://marketplace.visualstudio.com/items?itemName=vscodevim.vim
													- Documentation
													  id:: 634bda49-356f-4d3d-9fa7-752c35a491e6
														- [How to disable visual mode by mouse](https://github.com/VSCodeVim/Vim/issues/3372#issuecomment-573385335)
														- Configuration
															- *Changes to defaults in Settings*
																- Disable `Vim: Use Ctrl Keys`
																	- Vim Ctrl key commands override common Visual Studio Code commands
																	- Examples
																		- `CTRL + C` = Copy ( ((63209272-1088-4824-a762-4ac7ded04b0a)) )
																		- ((634be6e4-d8cc-4444-a7cd-a46401bb826f))
																		- ((634bf4e8-e39b-4255-9436-3cc44997c1d6))
																		- ((634bf508-e980-4dc6-bf92-40083c46400f))
																		- ((634bf54d-c88d-46b3-88e3-1483e748af91))
																		- ((634bf598-5dcb-41d9-b0df-3ab10bd6d4d8))
																		- ((634bf5c4-0971-468b-b226-dd61454c27ee))
																		- ((634bf5db-6b12-4077-a297-5d7ba319933e))
														- Keybindings
														  id:: 634bd9f4-b9b6-4d35-b349-c98046d7f31b
															- Most common
															- https://github.com/VSCodeVim/Vim/blob/HEAD/ROADMAP.md
																- [Inserting text](https://github.com/VSCodeVim/Vim/blob/HEAD/ROADMAP.md#inserting-text)
																	- `a` = append text after the cursor (N times)
																	- `A` = append text at the end of the line (N times)
																	- `i` = Insert text before the cursor (N times)
																	- `I` = Insert text before the first non-blank in the line (N times). i.e. start Insert as first character of the line
																- [Insert mode keys](https://github.com/VSCodeVim/Vim/blob/HEAD/ROADMAP.md#insert-mode-keys)
																	- *Leaving insert mode*
																		- `Esc` = end Insert mode, back to Normal mode
																		- `CTRL-C` = like Esc, but do not use an abbreviation
																		  id:: 634be6e4-d8cc-4444-a7cd-a46401bb826f
																		- `CTRL-O {command}` = execute {command} and return to Insert mode
																- `x` = Delete character
																- `r` = Replace character
																- [Marks and motions](https://github.com/VSCodeVim/Vim/blob/HEAD/ROADMAP.md#marks-and-motions)
																  id:: 634bf4e0-7a7e-4289-a5fc-e6ef9c396fba
																	- `CTRL + O` = Go to Nth older position in jump list
																	  id:: 634bf4e8-e39b-4255-9436-3cc44997c1d6
																	- `CTRL + I` = Go to Nth newer position in jump list
																	  id:: 634bf508-e980-4dc6-bf92-40083c46400f
																- [Using tags](https://github.com/VSCodeVim/Vim/blob/HEAD/ROADMAP.md#using-tags)
																	- `CTRL + ]` = Jump to the tag under cursor, unless changes have been made
																	  id:: 634bf54d-c88d-46b3-88e3-1483e748af91
																	- `CTRL + T` = Jump back from Nth older tag in tag list
																	  id:: 634bf598-5dcb-41d9-b0df-3ab10bd6d4d8
																	- `CTRL-W }` = like CTRL-] but show tag in preview window
																	  id:: 634bf5c4-0971-468b-b226-dd61454c27ee
																	- `CTRL-W z` = close tag preview window
																	  id:: 634bf5db-6b12-4077-a297-5d7ba319933e
																- [Scrolling](https://github.com/VSCodeVim/Vim/blob/HEAD/ROADMAP.md#scrolling)
																	- `CTRL + E` = window N lines downwards (default: 1)
																	- `CTRL + D` = window N lines Downwards (default: 1/2 window)
																	- `CTRL + F` = window N pages Forwards (downwards)
																	- `CTRL + Y` = window N lines upwards (default: 1)
																	- `CTRL + U` = window N lines Upwards (default: 1/2 window)
																	- `CTRL + B` = window N pages Backwards (upwards)
																- Special keys in Insert mode
																	- `CTRL-V {char}..` = insert character literally, or enter decimal byte value
																	- `CTRL + M`/`CTRL + J` = begin new line (not yet supported)
																	- `CTRL + E` = insert the character from below the cursor
																	- `CTRL + Y` = insert the character from above the cursor
																	- `CTRL + A` = insert previously inserted text
																	- `CTRL + @` = insert previously inserted text and stop Insert mode
																	- `CTRL-R {0-9a-z%#:.-="}` = Insert next match of identifier before the cursor
																	- `CTRL + P` = insert previous match of identifier before the cursor
																	- `CTRL + X` = complete the word before the cursor in various ways
																	- `CTRL + H` = delete the character before the cursor
																	- `CTRL + W` = delete word before the cursor
																	- `CTRL + U` = delete all entered characters in the current line
																	- `CTRL + T` = insert one shiftwidth of indent in front of the current line
																	- `CTRL + D` = delete one shiftwidth of indent in front of the current line
																- Changing text
																	- `CTRL + A` = add N to the number at or after the cursor
																	- `CTRL + X` = subtract N from the number at or after the cursor
																- Visual mode
																	- `CTRL + V` = start highlighting blockwise or stop highlighting
																- Undo/Redo commands
																	- `CTRL + R` = redo last N undone changes
															- Consider remapping `Caps Lock` to `Esc` - this allows more easily leaving insert mode. Though it does mean having to use SHIFT for writing uppercase
															- Vim modes
																- Normal mode
																  id:: 634bddff-bfb3-4bc4-8db9-1adda05d204a
																	- Keys will be used for navigation, etc. Rather than being typed into the text editor
																- `i` = Insert mode
																	- Keys will be inserted as characters in the text document. Press `ESC` to go back to ((634bddff-bfb3-4bc4-8db9-1adda05d204a))
																- `:` = Command mode
																- `v` = Visual Mode
															- Navigation
															  id:: 634bdfb6-01c3-46b3-b0c3-9a572f10b2f0
																- `h` = Move left by one character
																- `j` = Move down by one character
																- `k` = Move up by one character
																- `l` = Move right by one character
													- Related:
														- ((6318fc57-db8a-441f-af0e-c8392241a76b)) : ((634bf00a-932c-4a43-8a7c-c822f175ffed))
														  id:: 634bf1bb-67e4-452f-94aa-506f85a75ef3
														  [[PC]]
										- ### Troubleshooting
											- [Bisecting](https://code.visualstudio.com/blogs/2021/02/16/extension-bisect)
												- `Help: Start Extension Bisect` command is useful for helping find which of your extensions is causing you an issue
										- Building VSCode extensions
										  collapsed:: true
											- Exposing theme colours as Tailwind classes https://github.com/githubocto/tailwind-vscode
											- Building webviews (like interactive iframes) https://github.com/microsoft/vscode-webview-ui-toolkit
									- Using ((63a9adc7-b9eb-401b-be40-5f8836b86618)) with ((6550215b-37e8-4e32-8c81-7d82e21d9091))
									  id:: 64b0f78b-5721-4f7f-960f-739dda310321
									  collapsed:: true
										- Why
											- Otherwise you have to do a one of ((65a10afb-7a18-4986-b447-6fb920d445bc))
											  id:: 6550215b-21eb-4dc5-8c5c-f955b8410882
											- Better to use a sandboxed, disposable container
										- {Archive}
											- [Using the VSCode flatpak distribution | Medium](https://raduzaharia.medium.com/using-the-vscode-flatpak-distribution-a275d59ff1c7)
												- Steps
													- Install toolbx (and podman comes included?)
													- `toolbox create my-container-name`
													  Create a toolbx container
													- `toolbox enter my-container-name`
													  Enter the container
													- VSCode settings > search for "Docker path"
														- Change from `docker` to `/app/tools/podman/bin/podman-remote`
													- `flatpak install flathub com.visualstudio.code.tool.podman`
													  Install podman Flatpak
													- *Make the podman Flatpak accessible to VSC*
														- Flatseal > Visual Studio Code > Filesystem section > Other files > add a new path of `xdg-run/podman`
													- `systemctl --user enable podman.socket --now`
													  Enable the podman socket
													-
													- Install Remote Containers extension to enter the container
														- Alternatively can setup a SSH server in the container and use the Remote SSH extension to connect to it instead
													- Remote Explorer tab should show the available container
													- LMB the "Attach to container" icon
									- Debugger
									  id:: 663a57a0-f8f0-4913-bf6b-bc44cd33ebc6
									  collapsed:: true
										- [The New Way To Debug JavaScript in VS Code - No Extension Required - YouTube](https://www.youtube.com/watch?v=tC91t9OvVHA)
										  collapsed:: true
											- {{video https://www.youtube.com/watch?v=tC91t9OvVHA}}
											- 4th button on the left opens the Debugger
											- Use the Live Server extension or similar to start the server e.g. on localhost:5500
											- `Run and Debug` > Chrome >
											- Change the URL in the `launch.json` to be localhost:5500 (or whatever URL you're running your web app on)
											- On the left of line numbers you can mouseover and left-click to set breakpoints
											- Top-right will have `stepover` and left menu will show variables
											- Click stop in top-right, and play in top-left
										- [Debugging](https://code.visualstudio.com/docs/editor/debugging)
										- [How to Use a Debugger - Debugger Tutorial - YouTube](https://youtu.be/7qZBwhSlfOo)
										  collapsed:: true
											- {{video https://youtu.be/7qZBwhSlfOo}}
									- `.vscode/` directory per-project
									  collapsed:: true
										- Meta
										- `extensions.json`
											- Allows you to recommend specific extensions to install in your codebase
											- An example Python/JS project
											  collapsed:: true
												- ```json
												  {
												  "recommendations": [
												  "dbaeumer.vscode-eslint",
												  "esbenp.prettier-vscode",
												  "ms-python.python",
												  "ms-python.vscode-pylance",
												  "ms-python.debugpy",
												  "charliermarsh.ruff",
												  "tamasfe.even-better-toml",
												  "ms-python.vscode-python-envs"
												  ],
												  "unwantedRecommendations": [
												  "ms-python.pylint", // If you prefer ruff
												  "ms-python.black-formatter", // If you prefer ruff
												  "ms-python.flake8", // If you prefer ruff
												  "donjayamanne.python-extension-pack" // If you prefer ruff
												  ]
												  }
												  ```
										- `settings.json`
											- VSCode command palette - `Preferences: Open User Settings (JSON)` is where you can edit your user settings, rather than project level `.vscode/settings.json`
											- In VSCode enable `scm.workingSets.enabled` either via GUI settings or `.vscode/settings.json`. It means when you change branches it'll re-open the tabs you had open on that branch if you've used it before
											- An example Python/JS project
											  collapsed:: true
												- ```json
												  {
												  "editor.insertSpaces": true,
												  "editor.trimAutoWhitespace": true,
												  "[python]": {
												  "editor.defaultFormatter": "charliermarsh.ruff",
												  "editor.formatOnSave": true,
												  "editor.tabSize": 4,
												  "editor.rulers": [72, 88],
												  "editor.codeActionsOnSave": {
												   "source.fixAll": "explicit",
												   "source.organizeImports": "explicit"
												  }
												  },
												  "ruff.configuration": "${workspaceFolder}/pyproject.toml",
												  "[javascript][typescript]": {
												  "editor.defaultFormatter": "esbenp.prettier-vscode",
												  "editor.formatOnSave": true,
												  "editor.tabSize": 2,
												  "editor.rulers": [80],
												  "editor.codeActionsOnSave": {
												   "source.fixAll": "explicit",
												   "source.organizeImports": "explicit"
												  }
												  },
												  "eslint.options": {
												  "overrideconfigFile": "${workspaceFolder}/eslint.config.js"
												  },
												  "eslint.useFlatConfig": true
												  }
												  ```
											- Settings (`.vscode/settings.json`)
											  collapsed:: true
												- Tabs instead of Spaces
													- ```json
													  // The number of spaces a tab is equal to.
													  "editor.tabSize": 2,
													  
													  // Insert spaces when pressing Tab. Overridden based on file contents by `editor.detectIndentation`
													  "editor.insertSpaces": false,
													  
													  // When opening a file, `editor.tabSize` and `editor.insertSpaces` will be detected based on the file contents.
													  "editor.detectIndentation": true
													  ```
											- `"editor.formatOnSaveMode": "modificationsIfAvailable"` + `"editor.formatOnSave": true` = great with Prettier
												- Also `"editor.insertSpaces": true` and `"editor.trimAutoWhitespace": true`
										- [`tasks.json`](https://code.visualstudio.com/docs/editor/tasks)
										  collapsed:: true
											- `.vscode/tasks.json`
											  collapsed:: true
												- Example
													- ```json
													  {
													  "label": "List dir",
													  "type": "shell",
													  "command": "ls",
													  "args": [
													  "-alh",
													  "${input:dir}"
													  },
													  "problemMatcher": []
													  },
													  {
													  "id": "dir",
													  "description": "Directory path",
													  "default": "$(cwd)",
													  "type": "promptString",
													  }
													  ```
												- Problem Matcher
													- `"problemMatcher": []` is the default
													- Problem Matchers are a way to scan the output of actions for a specified regex pattern and surface that information prominently in the UI.
													- [Defining a (custom) problem matcher](https://code.visualstudio.com/docs/debugtest/tasks#_defining-a-problem-matcher)
												-
											- `options`
												- `cwd` = Current working directory
												- How to provide different options
												  collapsed:: true
													- ```json
													  "tasks": [
													    {
													      "label": "Build (scrcpy)",
													      "type": "shell",
													      "command": "${workspaceFolder}/which-craft/scrcpy/build.sh",
													      "options": {
													        "cwd": "${workspaceFolder}/which-craft/scrcpy"
													      },
													      "args": [
													        "${input:scrcpy-component}",
													        "${input:config}"
													      ],
													      "problemMatcher": []
													    },
													    {
													      "label": "Run",
													      "type": "shell",
													      "args": [
													        "compose",
													        "-f",
													        "${workspaceFolder}/which-craft/.docker/docker-compose.yml",
													        "up"
													      ],
													      "problemMatcher": []
													    }
													  ]
													  "inputs": [
													    {
													      "id": "config",
													      "description": "Build configuration",
													      "default": "debug",
													      "type": "pickString",
													      "options": [
													        "debug",
													        "release"
													      ]
													    },
													    {
													      "id": 
													      etc etc
													      "options": [
													      "client",
													      "server"
													      ]
													  }
													  ]
													  ]
													  ```
											- To run use `CTRL+SHIFT+P` to bring up the command palette > type `Tasks: Run Tasks` > select the task
											- Example `tasks.json`
												- ```json
												  {
												  "version": "1.0.0",
												  "tasks": [
												  {
												  	"label": "Flash Image",
												  	"type": "shell",
												  	"command": "sudo",
												  	"args": [
												  		"dd",
												  		"bs=100M",
												  		"status=progress",
												  	],
												  	"problemMatcher": [],
												  }
												  ]
												  }
												  ```
											- Learn how to write vscode task file which starts multiple terminals and runs several arbitrary commands each
											- Create a keybinding for Tasks menu
												- File->Preferences->Keyboard Shortcuts. `workbench.action.tasks.runTask`, I use the combo `ctrl+;`
												- Or just use ((6341d63d-cb12-465e-b936-e7efac4abf91)) ?
									- Troubleshooting
										- How to set VSCode word wrap always [Perplexity](https://www.perplexity.ai/search/explain-running-adb-reverse-lo-RxrXHLzjSRGZuOt_v8AQsQ#18) (useful if using multiple panes or a vertical monitor)
									- Search tab
									  collapsed:: true
										- To search filenames rather than file content in VSCode, click on the Explorer (files) tab then search with `CTRL+F` to find the first one. Or use `CTRL+SHIFT+P` to search through them all
										- Filter option
											- `*.js, *.map`
											- `**/*.js, **/*.map`
									- DevContainers
									  collapsed:: true
										- `.devcontainer/devcontainer.json`
										  collapsed:: true
											- `postCreateCommand` can be split into multiple objects
												- Example
												  ```json
												  "postCreateCommand": {
												  "command1": "ls ~",
												  "command2": "ls $(pwd)"
												  "command3": "ls $(pwd)/"
												  }
												  ```
											- [`postCreateCommand`](https://containers.dev/implementors/json_reference/) can be formatted as a string, array or object
										- `devcontainer.json` should probably be run with runArgs `--network=host` if using a similar DevOps setup as WC, since we're instead only trying to test whether the networking actually works via the `docker-compose.yml` setup
										- Dev workflow on WC: dev container with every dependency added to it via features (bash scripts) + tasks.json to run each service separately + docker-compose.yml for running each service in individual containers (using Dockerfiles instead) in order to test the networking works properly
									- Tips
										- `code .` = opens an instance of VSCode at the `pwd`
										- How to see all the places where an exported variable is used (e.g. imported)
											- Right-click > Find all references
									- New features
										- [MCP Servers](https://code.visualstudio.com/docs/copilot/customization/mcp-servers)
						- `com.github.micahflee.torbrowser-launcher` Tor Browser
						  collapsed:: true
							- Note: It's an unofficial Flatkpak
							  https://flathub.org/apps/details/com.github.micahflee.torbrowser-launcher
							- RE official Flatpak
							  https://trac.torproject.org/projects/tor/ticket/25578
						- `com.github.unrud.VideoDownloader` Video Downloader
						  id:: 651c9650-7aa3-4bb3-819e-54934b13cff6
						- `com.usebottles.bottles` Bottles
						  collapsed:: true
							- How to use
								- Go to Bottles data dir
								  /home/boss/.var/app/com.usebottles.bottles/data/bottles/bottles/
								- Go into Documents within the selected Bottle e.g.
								  /home/boss/.var/app/com.usebottles.bottles/data/bottles/bottles/HoMM2/drive_c/users/boss/Documents/
								- Copy and paste all folder + files in there
								- In Bottles UI, click Run Executable then navigate to Root
								- Copy and paste the full path of the executable within Documents
								- When finished, add the executable to the Programs section
							- 1 Backlink
								- See [Bottles](https://workflowy.com/#/323141453aad)
						- `io.github.pwr_solaar.solaar` Solaar
						  collapsed:: true
							- [Solaar](https://github.com/pwr-Solaar/Solaar)
							  id:: 65a98a8b-6c81-4771-af37-c49da1e608b6
							  collapsed:: true
								- Linux Device Manager for many Logitech keyboards, mice, and trackpads that connect wirelessly to a USB Unifying, Bolt, Lightspeed, or Nano receiver; connect directly via a USB cable; or connect via Bluetooth
								- Related:
									- ((6491cef7-d83e-4aab-abef-33cbb630a02d))
									- ((6491cf16-0eb6-49fc-a49d-b395cb49fb00))
									- ((6491d6ad-96b3-4fad-a680-7c854739aea6))
						- `org.tribler.Tribler` ((644c0b2c-9d77-4496-9aac-e6a7149e0aa9))
						  collapsed:: true
						- `org.flameshot.Flameshot` (alternative for ShareX)
						  collapsed:: true
							- Flameshot
								- [https://github.com/lupoDharkael/flameshot](https://github.com/lupoDharkael/flameshot)
								- Installation
									- Flatpak
									  `flatpak install flathub org.flameshot.Flameshot`
										- [https://flathub.org/apps/details/org.flameshot.Flameshot](https://flathub.org/apps/details/org.flameshot.Flameshot)
									- AppImage
									  [https://github.com/flameshot-org/flameshot/releases](https://github.com/flameshot-org/flameshot/releases)
									- Normal package
									  `sudo apt install flameshot`
								- Note:
									- flatpak run org.flameshot.Flameshot gui
									  Use this instead of the command `flameshot gui` as Flatpak doesn't put binaries in `/bin`
							- Alternatives
								- ShareX
								- KShare (inspired by ShareX)
								  collapsed:: true
									- https://gitlab.com/ArsenArsen/KShare
									- Hasn't got a proper DEB and have to compile and install dependencies manually
								- Shutter
								  collapsed:: true
									- http://shutter-project.org/
								- Others
								  collapsed:: true
									- https://alternativeto.net/software/flameshot/
									- WayRec (screen recorder for Wayland)
									  [https://invent.kde.org/bharadwaj-raju/wayrec](https://invent.kde.org/bharadwaj-raju/wayrec)
							- protip: add `/zip` to the end of an imgur album URL to download it as a zip [[various - Album on Imgur](https://imgur.com/a/various-nPAEYfU/zip](https://imgur.com/a/various-nPAEYfU/zip))
						- `org.zotero.Zotero` Zotero
						  collapsed:: true
							- /home/USER/.zotero/zotero/
							- See [Zotero](https://workflowy.com/#/935fa4d3e496)
						- `org.kde.kontact` Kontact (contains Kalendar)
						- `re.sonny.Junction` [Junction](https://github.com/sonnyp/Junction)
						  id:: 6492a114-d9c9-4fe5-ab93-f86b212ea656
						  collapsed:: true
							- Pros/Cons
								- Pros
									-
								- Cons
									- [Browsers don't go to the foreground and take focus when links are opened on Wayland · Issue #159 · sonnyp/Junction · GitHub](https://github.com/sonnyp/Junction/issues/159)
									-
								- Unclear
								- Comparisons
							- In KDE open `Default Applications` to change what opens web links
							  id:: 677f9d1e-8f3c-4f2f-b7cc-3f15fb62a32d
							- Notes
								- [Desktop Entry] must be the first section of `.desktop` files in `/home/boss/.local/share/applications/`
								- Only seems to work properly with fellow Flatpak-based browsers - TAR unzipped Firefox browsers
							- [[2023-06-21 Wednesday]] Current browsers
								- ![image.png](../assets/image_1687340857336_0.png)
							- Documentation
								- To add a new browser
									- Ensure it's present in `/home/boss/.local/share/applications/`
									- In Junction open the hamburger menu > search for the name in the application list and select it
							- # Troubleshooting
								- [[2025-01-08 Wednesday]] [Stopped working](https://github.com/sonnyp/Junction/issues/168)
									- ((677f9d1e-8f3c-4f2f-b7cc-3f15fb62a32d))
									- Tried and didn't help
										- Maybe due to ((63ad9567-857c-4b16-8292-abf0e85a0326)) : ((65fc0441-ae9f-4f88-a744-5674dd2b7faf))
											- Removing the system remote and associated applications hasn't helped. Junction pop-up opens but it doesn't do anything. Changing ((677f9d1e-8f3c-4f2f-b7cc-3f15fb62a32d)) shows the browsers still work but not Junction
										- Try ((65a98a51-72f2-4e93-81fe-58756b9a9e5c))
											- `flatpak update --commit=8b40f71fdf79f39e87861fd338b83fb5b6263f84e30ec0018a482a9c89b6e185 re.sonny.Junction`
											- Didn't help
										- Non-Flatpak browsers still don't open
											- Microsoft Edge
									- [[2025-02-10 Monday]] Swapped to use [Browsers](https://github.com/Browsers-software/browsers) instead as Junction is rarely getting commits anymore
										- `/home/boss/Documents/ESSENTIALS/Programs/browsers_amd64.deb`
										- [Too small](https://github.com/Browsers-software/browsers/issues/160)
							- Related:
								- Windows-version [BrokenURL](https://brokenevent.com/projects/brokenurl)
								- [GitHub - zhom/donutbrowser: Simple Yet Powerful Browser Orchestrator 🍩](https://github.com/zhom/donutbrowser)
								-
						- `fr.handbrake.ghb` ((6655e501-3e4b-4350-983a-0dce9ee99d02))
					- _Related:_
						- ((663a5790-1384-4fe1-8d26-7f5facd72520))
				- Programs already downloaded
				  collapsed:: true
					- AppImages (need to run them once to add to KRunner)
						- ~/Documents/ESSENTIALS/Portable/
						- [Draw.io](http://Draw.io)
						  id:: 6345ae8e-7c30-4ba9-927c-f30ebe235761
						  collapsed:: true
						  AKA Diagrams.net
							- Download latest AppImage from
							  [https://github.com/jgraph/drawio-desktop/releases](https://github.com/jgraph/drawio-desktop/releases) / <a href="http://get.diagrams.net/">http://get.diagrams.net/</a>
					- Setup ((63a9adf9-dcc0-4caa-a0da-f495b1d63abc))
					- ((635eb1a3-4222-4dee-bb4c-9e895c970a86))
					- _Portable_
					  Noteworthy; but nothing needs to be done here
						- VC container ((63a9adc7-31c0-4b63-b01f-8b73185dadbf))
							- ((649b1412-793f-4972-b3a0-338c319b3e88))
							- ((6312a075-ceb2-4a57-adc5-2a27f91e865c))
							  collapsed:: true
							- [[Zotero]]
							- ((653623ca-07a9-4ac8-9be0-16d988dab793))
							- Nyrna
							  collapsed:: true
								- [https://nyrna.merritt.codes/](https://nyrna.merritt.codes/)
								- [Nyrna 2.0-alpha.1 released, suspend games and applications](https://redd.it/lpwr2g)
								- [https://github.com/Merrit/nyrna](https://github.com/Merrit/nyrna)
								- Basically the same as `killall -STOP $game` or SIGSTOP
								- If I remember correctly, it's not possible to take a suspended program, write its RAM to storage, close it, then later restore the program from storage? I can't remember exactly why, just that it has to do with external libraries.
									- Unfortunately no. [CRIU](https://criu.org/) looks very promising to allow us to do this (on Linux), however it <a href="https://criu.org/X_applications">does not currently support suspending GUI applications</a>.
								- Related: [GitHub - checkpoint-restore/criu: Checkpoint/Restore tool](https://github.com/checkpoint-restore/criu)
								-
							- _AppImages_
								- Nextcloud
								  collapsed:: true
									- Add to 'Ignored Files' list if not already there:
										- ESSENTIALS/SB-LINUX1/*
								- MyCrypto
								- Balena Etcher (burn ISO to drive)
								  collapsed:: true
									- [https://www.balena.io/etcher/](https://www.balena.io/etcher/)
									- [https://github.com/balena-io/etcher/releases](https://github.com/balena-io/etcher/releases)
								- [Khoj](https://khoj.dev/)
								  id:: 655ab03c-836c-4364-a133-0d7140a06798
								  collapsed:: true
									- [GitHub - khoj-ai/khoj: An AI copilot for your second brain. Search and chat with your personal knowledge base, online or offline](https://github.com/khoj-ai/khoj)
									- Lacks
										- [Logseq plugin](https://github.com/khoj-ai/khoj/issues/141#issuecomment-1773905122)
										- [Support for SQLite](https://github.com/khoj-ai/khoj/issues/504#issuecomment-1771706282)
										- [Flatpak release](https://github.com/khoj-ai/khoj/issues/384#issuecomment-1818011549) (though AppImage does self-update)
						- Other portable
							- ((63ad9310-1147-443a-a36a-27f46906b0bf))
							- See [Firefox](https://workflowy.com/#/caec280c27e7)
							  #WebBrowser
							- BirdTray (MinimizeToTray-revived alternative for Thunderbird)
							  collapsed:: true
								- [https://github.com/gyunaev/birdtray](https://github.com/gyunaev/birdtray)
								- Packages
									- libqt5x11extras5-dev
									- libqt5x11extras5
									  not sure if needed
									- Install Qt
									  sudo apt-get install -y qtdeclarative5-dev qml-module-qtquick-controls
									- Sqlite3
									  libsqlite3-dev
									- sudo apt install build-essential make
								- Use `update-alternatives` to make symlinks between qt4 and qt5
								  https://askubuntu.com/a/938433
									- sudo update-alternatives --install /usr/bin/qmake qmake /usr/lib/x86_64-linux-gnu/qt5/bin/qmake 100
									- sudo update-alternatives --config qmake
								- **compile error when using 'make' (several others have same issue)**
								  https://github.com/gyunaev/birdtray/issues/25
									- In my case using kubuntu 18.04, I found out that both the latest stable package and master branch had a pre-created hidden .qmake.stash file under src/ with links to suse paths. I just deleted this file before invoking qmake, and everything worked (after I manage to install all needed packages, of course).
								- _Alternatives_
									- [https://github.com/Ximi1970/systray-x](https://github.com/Ximi1970/systray-x)
										- [https://www.linuxuprising.com/2020/11/systray-x-is-thunderbird-68-tray-icon.html](https://www.linuxuprising.com/2020/11/systray-x-is-thunderbird-68-tray-icon.html)
					- _Needs installing too_
					  id:: 65a98a51-c0aa-4c29-9f88-e87c95d389ba
					  sudo gdebi nameofpackage.deb
						- `~/Documents/ESSENTIALS/Programs/`
						- ((63ada7d4-115c-4246-b867-a85317f29b42))
						- `/home/boss/Documents/ESSENTIALS/Programs/git-credential-manger-linux_amd64.2.0.785.deb`
						- Alarm Clock (alternative to CookTimer)
						  collapsed:: true
							- DEB downloaded to My Docs
							  alarm-clock-applet_0.3.4-1_amd64.deb
							- Missing from 19.10 repo
							  sudo apt install -y alarm-clock-applet
							- _Next:_
								- Create one timer which uses the audio song in ~/Documents/ESSENTIALS/Other-files/
						- Veracrypt
						- [caffeine-minus](https://github.com/deloachcd/caffeine-minus/)
						  id:: 65cbfa25-9e2c-42ee-a37d-ae52f32ba80e
						  collapsed:: true
							- Go into edit mode on Plasma panel then add the widget to the panel
							- `/home/boss/Documents/ESSENTIALS/Programs/caffeine-minus`
							- Using this as an alternative to Flatpak `io.github.sigmasd.stimulator` which wasn't working fully
							- Issues
								- [Incompatible with Plasma 6 · Issue #1 · deloachcd/caffeine-minus · GitHub](https://github.com/deloachcd/caffeine-minus/issues/1)
					- {Archive}
						- CrashPlan
						  collapsed:: true
							- Install - Use the install.sh
							- Increase max inotify watches available
							  https://support.code42.com/CrashPlan/6/Troubleshooting/Linux_real-time_file_watching_errors
								- _Related_ ((65a98a51-86a0-4b61-ac39-4efe48b9c93d))
								- Edit the file
								  `sudo nano /etc/sysctl.conf`
									- `fs.inotify.max_user_watches = 1048576`
								- Check it
								  `sudo sysctl -p /etc/sysctl.conf`
							- How to start
							  sudo /usr/local/crashplan/bin/CrashPlanEngine start|stop
							   /usr/local/crashplan/bin/CrashPlanDesktop
							- See [CrashPlan](https://workflowy.com/#/03f7394dbb03)
							  #Software
						- ProtonVPN
						  collapsed:: true
							- /home/boss/Documents/ESSENTIALS/Programs/protonvpn-stable-release_1.0.1-1_all.deb
							- Then
								- sudo apt update
								- sudo apt install protonvpn
							- Tray indicator
								- sudo apt install gnome-shell-extension-appindicator gir1.2-appindicator3-0.1
								- Also select 'sddm' as display if prompted
						- KDocker
						- Qomui
						- Texpander (alternative to Phrase Express ie Text expander / dictionary autocomplete)
						  collapsed:: true
							- Texpander
								- https://github.com/leehblue/texpander
								- _Pros/Cons_
									- Pros
										- Useful for long abbreviations like ((632092d4-bfc8-47f7-a4bb-157aae42e14f))
									- Cons
										- The shortcut is unintuitive and wish I could just skip it
										- Works probably but requires a Launchy-like popup to type in abbreviation
								- How to setup
									- Dependencies
									  sudo apt install -y xsel xdotool zenity
									- Create a ~/.texpander directory where you store text files for expanding abbreviations
									- The text expansion files reside in your ~/.texpander directory and can be organized in subdirectories. Name the files in the format of abbreviation where the filename is the thing you want to type and the content of the file is what you want to have pasted into your document.
									- Setup keyboard shortcut
										- Custom Shortcuts
										- New > Global Shortcut > Command/URL
										- Trigger: CTRL+SPACE
										- Action:
											- /home/boss/Documents/ESSENTIALS/Portable/Texpander/texpander.sh
							- _Alternatives_
								- AutoKey
									- What
										- AutoKey is a desktop automation utility for Linux and X11. It allows you to manage collection of scripts and phrases, and assign abbreviations and hotkeys to these. This allows you to execute a script or insert text on demand in whatever program you are using.
										- AutoKey features a subset of the capabilities of the popular Windows-based AutoHotkey, but is not intended as a full replacement. For a Linux-based implementation of AutoHotkey, see IronAHK. AutoKey's GUI features a number of concepts and features inspired by the Windows program PhraseExpress.
									- Unlisted dependency? python3-pyatspi
								- Actionaz (abandoned since 2013)
									- https://github.com/niconil/actionaz
								- Snippits
				- [[Programming software setup]]
				- {Archive}
				  collapsed:: true
					- See [Snappy](https://workflowy.com/#/276cbf2d85a1)
				- **============================LAST COMPLETED============================================**
				- _Unsorted_
				  collapsed:: true
					- Nvidia Shadowplay alternative
					  collapsed:: true
						- [gpu-screen-recorder](https://git.dec05eba.com/gpu-screen-recorder/about/)
						  id:: 63ad9567-857c-4b16-8292-abf0e85a0326
						  collapsed:: true
							- Links
								- [GitHub - dec05eba/gpu-screen-recorder-issues: GPU Screen Recorder issue tracker](https://github.com/dec05eba/gpu-screen-recorder-issues)
							- Pros/Cons
								- Pros
									-
								- Cons
									- ((65fc0441-ae9f-4f88-a744-5674dd2b7faf))
									- Only supports Nvidia currently (Thu, May 5, 2022 )?
										- [[2024-03-21 Thursday]] Works fine with new ((659d093f-bf67-444a-b2a1-ec0a28907583))
									- Supports Wayland/AMD/Intel but only can record monitor using this
								- Unclear
								- Comparisons
							- This screen recorder can be used for recording your desktop offline, for live streaming and for nvidia-like instant replay, where only the last few seconds are saved.
							- Not OP here, but the big key difference between this software and OBS/ ((65a98a51-f6a4-4740-ba45-6716a08a5423)) /etc, is that it appears to pull directly from the GPUs copy of the images without any relays to the CPU and back. That's what makes Shadowplay on Windows so CPU efficient. :)
							- # Documentation
								- How to install
								  collapsed:: true
									- Has to be installed system-wide to record a monitor
									  id:: 65fc0441-ae9f-4f88-a744-5674dd2b7faf
									  collapsed:: true
										- Installation
											- `sudo flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo`
											- `flatpak install flathub --system com.dec05eba.gpu_screen_recorder`
											- Then restart the app
										- Recording a monitor requires (restricted) root access which means that you have to install GPU Screen Recorder system-wide: "flatpak install --system com.dec05eba.gpu_screen_recorder"
										- GPU Screen Recorder flatpak can install files in $HOME/.local/share/gpu-screen-recorder. If you want to uninstall GPU Screen Recorder then you will have to remove this directory manually.
										- If you tried out the new UI then a systemd service was added to ~/.local/share/systemd/user/gpu-screen-recorder-ui.service. If you want to uninstall GPU Screen Recorder then you will have to remove this file.
										- Related: ((63a873fd-893d-4ed7-ae5b-e27945e68230)) : ((677f9fb3-a825-490a-8a60-4973bb846841))
									- Flatpak
										- {{embed ((65fc0441-ae9f-4f88-a744-5674dd2b7faf))}}
									- Native
										- `cd /home/boss/Documents/ESSENTIALS/Programs`
										- `git clone https://repo.dec05eba.com/gpu-screen-recorder`
										- `cd gpu-screen-recorder`
										- `sudo ./install_ubuntu.sh`
								- Flags
									- `gpu-screen-recorder --help` / `flatpak run --command=gpu-screen-recorder com.dec05eba.gpu_screen_recorder --help`
									- Running in Replay mode from the terminal
										- `flatpak run --command=gpu-screen-recorder com.dec05eba.gpu_screen_recorder -w eDP-1 -f 60 -c mp4 -r 30 -a "$(pactl get-default-sink).monitor" -o "$HOME/Videos/Replays"`
										  collapsed:: true
											- `-w eDP-1` = window id to record, a display (monitor name), "screen", "screen-direct-force", or "focused"
											- `-f 60` = framerate `60`
											- `-c mp4` = container format for output file
											- `-r 30` = replay buffer size `30`
											- `-a "$(pactl get-default-sink).monitor"`
												- Audio device to record from (pulse audio device). Can be specified multiple times. Each time this is specified a new audio track is added for the specified audio device.
												- A name can be given to the audio input device by prefixing the audio input with <name>/, for example "dummy/alsa_output.pci-0000_00_1b.0.analog-stereo.monitor".
												- Multiple audio devices can be merged into one audio track by using "|" as a separator into one -a argument, for example: -a "alsa_output1|alsa_output2".
												- Optional, no audio track is added by default.
											- `-o "$HOME/Videos/Replays"` = output file path
								- Keybindings
								  id:: 65fc0a34-425c-40e2-a8ef-ee1aaa9f519d
									- `CTRL + Meta + Z` = Show/Hide fullscreen UI
									  id:: 677d750a-b70f-47dc-922d-f9e3e054f388
									- Modes
										- Replay
											- `ALT + F1` = Start/Stop Replay
											- `ALT + F9` = Save Replay
							- Shell command/keybind to save replay
								- In your case when running that command (replay mode), just run `killall -SIGUSR1 gpu-screen-recorder` and it will save a replay. You can bind this command to a key in your desktop environment. This option is better than using the graphical application, especially on wayland where most compositors dont have support for global hotkeys so this solution works on wayland as well. To stop replay you can bind a key to `killall -SIGINT gpu-screen-recorder`, or ctrl+c as you did.
							- [Announcement post](https://www.reddit.com/r/linux_gaming/comments/tjkvyd/i_made_a_nvidia_shadowplaylike_screen_recorder/)
								- When I switched to linux I was missing a fully hardware accelerated screen recorder such as nvidia shadowplay which allows you to record games with barely losing any fps, without having to use a capture card.
								- Neither obs with nvenc nor the obs-nvfbc plugin record the screen fully with the gpu. So I made my own screen recorder instead that records the screen 100% on the gpu and to my knowledge its the only such tool available for nvidia gpus on linux and its much faster than any other screen recorder to my knowledge. My screen recorder does not require a gpu with nvfbc support either.
								- As a performance comparison, playing breath of the wild with the cemu emulator at 4k and using obs makes the fps drop from 30 to 7 with my hardware. With my screen recorder the fps stays at 30 (fps is locked to 30 fps in the game).
								- Here are some demos of the screen recorder in action:https://www.youtube.com/watch?v=n5tm0g01n6Ahttps://www.youtube.com/watch?v=S1Hl7xyvpm8
								- The program is available at https://git.dec05eba.com/gpu-screen-recorder/about/ .There is also a gui frontend at https://git.dec05eba.com/gpu-screen-recorder-gtk/about/
								- If you are on arch then the software is available in aur.
								- The screen recorder also has a so called "replay buffer", which allows you to press a key to save the last few seconds instead of recording all the time, just like nvidia shadowplay.
							- Docs
							  collapsed:: true
								- This is a screen recorder that has minimal impact on system performance by recording your monitor using the GPU only, similar to shadowplay on windows. This is the fastest screen recording tool for Linux.
								  
								  This screen recorder can be used for recording your desktop offline, for live streaming and for nvidia shadowplay-like instant replay, where only the last few minutes are saved.
								  
								  Supported video codecs:
								- H264 (default on Intel)
								- HEVC (default on AMD and NVIDIA)
								- AV1 (not currently supported on NVIDIA if you use GPU Screen Recorder flatpak)
								  
								  Supported audio codecs:
								- Opus (default)
								- AAC
								- FLAC
								- ## Note
								  
								  This software works with x11 and wayland, but when using Wayland then only monitors can be recorded.
								- ### TEMPORARY ISSUES
								  
								  1.  screen-direct capture has been temporary disabled as it causes issues with stuttering. This might be a nvfbc bug.
								  2.  Videos are in variable framerate format. Use MPV to play such videos, otherwise you might experience stuttering in the video if you are using a buggy video player. You can try saving the video into a .mkv file instead as some software may have better support for .mkv files (such as kdenlive). You can use the "-fm cfr" option to to use constant framerate mode.
								  3.  HDR capture is supported (on wayland), but all GPU drivers have bugs that ignore HDR metadata so the HDR metadata will be missing in the video file. I will eventually patch the video file to workaround these GPU driver issues.
								- ### AMD/Intel/Wayland root permission
								  
								  When recording a window under AMD/Intel no special user permission is required, however when recording a monitor (or when using wayland) the program needs root permission (to access KMS).  
								  To make this safer, the part that needs root access has been moved to its own executable (to make it as small as possible).  
								  For you as a user this only means that if you installed GPU Screen Recorder as a flatpak then a prompt asking for root password will show up when you start recording.
								- # Performance
								  
								  On a system with a i5 4690k CPU and a GTX 1080 GPU:  
								  When recording Legend of Zelda Breath of the Wild at 4k, fps drops from 30 to 7 when using OBS Studio + nvenc, however when using this screen recorder the fps remains at 30.  
								  When recording GTA V at 4k on highest settings, fps drops from 60 to 23 when using obs-nvfbc + nvenc, however when using this screen recorder the fps only drops to 58. The quality is also much better when using gpu screen recorder.  
								  GPU Screen Recorder also produces much smoother videos than OBS when GPU utilization is close to 100%, see comparison here: [https://www.youtube.com/watch?v=zfj4sNVLLLg](https://www.youtube.com/watch?v=zfj4sNVLLLg).  
								  It is recommended to save the video to a SSD because of the large file size, which a slow HDD might not be fast enough to handle. Using variable framerate mode (-fm vfr) which is the default is also recommended as this reduces encoding load. Ultra quality is also overkill most of the time, very high (the default) or lower quality is usually enough.
								- ## Note about optimal performance on NVIDIA
								  
								  NVIDIA driver has a "feature" (read: bug) where it will downclock memory transfer rate when a program uses cuda (or nvenc, which uses cuda), such as GPU Screen Recorder. To work around this bug, GPU Screen Recorder can overclock your GPU memory transfer rate to it's normal optimal level.  
								  To enable overclocking for optimal performance use the `-oc` option when running GPU Screen Recorder. You also need to have "Coolbits" NVIDIA X setting set to "12" to enable overclocking. You can automatically add this option if you run `sudo nvidia-xconfig --cool-bits=12` and then reboot your computer.  
								  Note that this only works when Xorg server is running as root, and using this option will only give you a performance boost if the game you are recording is bottlenecked by your GPU.  
								  Note! use at your own risk!
								- # Installation
								  
								  If you are running an Arch Linux based distro, then you can find gpu screen recorder on aur under the name gpu-screen-recorder-git (`yay -S gpu-screen-recorder-git`).  
								  If you are running another distro then you can run `sudo ./install.sh`, but you need to manually install the dependencies, as described below.  
								  You can also install gpu screen recorder ([the gtk gui version](https://git.dec05eba.com/gpu-screen-recorder-gtk/)) from [flathub](https://flathub.org/apps/details/com.dec05eba.gpu_screen_recorder), which is the easiest method to install GPU Screen Recorder on non-arch based distros.  
								  The only official ways to install GPU Screen Recorder is either from source, AUR or flathub. If you install GPU Screen Recorder from somewhere else and have an issue then try installing it from one of the official sources before reporting it as an issue. If you install GPU Screen Recorder flatpak, which is the gtk gui version then you can still run GPU Screen Recorder command line by using the flatpak command option, for example `flatpak run --command=gpu-screen-recorder com.dec05eba.gpu_screen_recorder -w screen -f 60 -o video.mp4`. Note that if you want to record your monitor on AMD/Intel then you need to install the flatpak system-wide (like so: `flatpak install flathub --system com.dec05eba.gpu_screen_recorder`).
								- # Dependencies
								- ## AMD
								  
								  libglvnd (which provides libgl and libegl)  
								  mesa  
								  ffmpeg (libavcodec, libavformat, libavutil, libswresample, libavfilter)  
								  x11 (libx11, libxcomposite, libxrandr, xfixes)  
								  libpulse  
								  vaapi (libva, libva-mesa-driver)  
								  libdrm  
								  libcap  
								  wayland-client
								- ## Intel
								  
								  libglvnd (which provides libgl and libegl)  
								  mesa  
								  ffmpeg (libavcodec, libavformat, libavutil, libswresample, libavfilter)  
								  x11 (libx11, libxcomposite, libxrandr, xfixes)  
								  libpulse  
								  vaapi (libva, libva-intel-driver)  
								  libdrm  
								  libcap  
								  wayland-client
								- ## NVIDIA
								  
								  libglvnd (which provides libgl and libegl)  
								  ffmpeg (libavcodec, libavformat, libavutil, libswresample, libavfilter)  
								  x11 (libx11, libxcomposite, libxrandr, xfixes)  
								  libpulse  
								  cuda runtime (libcuda.so.1) (libnvidia-compute)  
								  nvenc (libnvidia-encode)  
								  libva  
								  libdrm  
								  libcap  
								  wayland-client  
								  nvfbc (libnvidia-fbc1, when recording the screen on x11)  
								  xnvctrl (libxnvctrl0, when using the `-oc` option)
								- # How to use
								  
								  Run `gpu-screen-recorder --help` to see all options.
								- ## Recording
								  
								  Here is an example of how to record all monitors and the default audio output: `gpu-screen-recorder -w screen -f 60 -a "$(pactl get-default-sink).monitor" -o ~/Videos/test_video.mp4` then stop the screen recorder with `Ctrl+C`, which will also save the recording. You can record a single monitor if you change `-w screen` to the name of a monitor, which you can find if you run the `xrandr`. An example of a monitor name is HDMI-1.
								- ## Streaming
								  
								  Streaming works the same as recording, but the `-o` argument should be path to the live streaming service you want to use (including your live streaming key). Take a look at scripts/twitch-stream.sh to see an example of how to stream to twitch.
								- ## Replay mode
								  
								  Run `gpu-screen-recorder` with the `-c mp4` and `-r` option, for example: `gpu-screen-recorder -w screen -f 60 -r 30 -c mp4 -o ~/Videos`. Note that in this case, `-o` should point to a directory.  
								  If `-mf yes` is set, replays are save in folders based on the date. To save a video in replay mode, you need to send signal SIGUSR1 to gpu screen recorder. You can do this by running `killall -SIGUSR1 gpu-screen-recorder`.  
								  To stop recording send SIGINT to gpu screen recorder. You can do this by running `killall -SIGINT gpu-screen-recorder` or pressing `Ctrl-C` in the terminal that runs gpu screen recorder.  
								  To pause/unpause recording send SIGUSR2 to gpu screen recorder. You can do this by running `killall -SIGUSR2 gpu-screen-recorder`. This is only applicable and useful when recording (not streaming nor replay).  
								  The file path to the saved replay is output to stdout. All other output from GPU Screen Recorder is output to stderr.  
								  The replay buffer is stored in ram (as encoded video), so don't use a too large replay time and/or video quality unless you have enough ram to store it.
								- ## Finding audio device name
								  
								  You can find the default output audio device (headset, speakers (in other words, desktop audio)) with the command `pactl get-default-sink`. Add `monitor` to the end of that to use that as an audio input in gpu screen recorder.  
								  You can find the default input audio device (microphone) with the command `pactl get-default-source`. This input should not have `monitor` added to the end when used in gpu screen recorder.  
								  Example of recording both desktop audio and microphone: `gpu-screen-recorder -w screen -f 60 -a "$(pactl get-default-sink).monitor" -a "$(pactl get-default-source)" -o ~/Videos/test_video.mp4`.  
								  A name (that is visible to pipewire) can be given to an audio input device by prefixing the audio input with `<name>/`, for example `dummy/$(pactl get-default-sink).monitor`.  
								  Note that if you use multiple audio inputs then they are each recorded into separate audio tracks in the video file. If you want to merge multiple audio inputs into one audio track then separate the audio inputs by "|" in one -a argument, for example `-a "$(pactl get-default-sink).monitor|$(pactl get-default-source)"`.
								  
								  There is also a gui for the gpu screen recorder called [gpu-screen-recorder-gtk](https://git.dec05eba.com/gpu-screen-recorder-gtk/).
								- ## Simple way to run replay without gui
								  
								  Run the script `scripts/start-replay.sh` to start replay and then `scripts/save-replay.sh` to save a replay and `scripts/stop-replay.sh` to stop the replay. The videos are saved to `$HOME/Videos`. You can use these scripts to start replay at system startup if you add `scripts/start-replay.sh` to startup (this can be done differently depending on your desktop environment / window manager) and then go into hotkey settings on your system and choose a hotkey to run the script `scripts/save-replay.sh`. Modify `scripts/start-replay.sh` if you want to use other replay options.
								- ## Run replay on system startup
								  
								  If you installed GPU Screen Recorder from AUR or from source and you are running a distro that uses systemd then you will have a systemd service installed that can be started with `systemctl enable --now --user gpu-screen-recorder`. This systemd service runs GPU Screen Recorder on system startup.  
								  It's configured with `$HOME/.config/gpu-screen-recorder.env` (create it if it doesn't exist). You can look at [extra/gpu-screen-recorder.env](https://git.dec05eba.com/gpu-screen-recorder/plain/extra/gpu-screen-recorder.env) to see an example. You can see which variables that you can use in the `gpu-screen-recorder.env` file by looking at the `extra/gpu-screen-recorder.service` file. Note that all of the variables are optional, you only have to set the ones that are you interested in. You can use the `scripts/save-replay.sh` script to save a replay and by default the systemd service saves videos in `$HOME/Videos`.  
								  If you are using a NVIDIA GPU then it's recommended to set PreserveVideoMemoryAllocations=1 as mentioned in the section below.
								- ## Examples
								  
								  Look at the [scripts](https://git.dec05eba.com/gpu-screen-recorder/tree/scripts) directory for script examples. For example if you want to automatically save a recording/replay into a folder with the same name as the game you are recording.
								- # Issues
								- ## NVIDIA
								  
								  Nvidia drivers have an issue where CUDA breaks if CUDA is running when suspend/hibernation happens, and it remains broken until you reload the nvidia driver. To fix this, either disable suspend or tell the NVIDIA driver to preserve video memory on suspend/hibernate by using the `NVreg_PreserveVideoMemoryAllocations=1` option. You can run `sudo extra/install_preserve_video_memory.sh` to automatically add that option to your system.
								- # Reporting bugs/contributing patches
								  
								  See [https://git.dec05eba.com/?p=about](https://git.dec05eba.com/?p=about)
								- # Demo
								  
								  [![Click here to watch a demo video on youtube](https://img.youtube.com/vi/n5tm0g01n6A/0.jpg)](https://www.youtube.com/watch?v=n5tm0g01n6A)
								- # FAQ
								- ## How is this different from using OBS with nvenc?
								  
								  OBS only uses the gpu for video encoding, but the window image that is encoded is copied from the GPU to the CPU and then back to the GPU (video encoding unit). These operations are very slow and causes all of the fps drops when using OBS. OBS only uses the GPU efficiently on Windows 10 and Nvidia.  
								  This gpu screen recorder keeps the window image on the GPU and sends it directly to the video encoding unit on the GPU by using CUDA. This means that CPU usage remains at around 0% when using this screen recorder.
								- ## How is this different from using OBS NvFBC plugin?
								  
								  The plugin does everything on the GPU and gives the texture to OBS, but OBS does not know how to use the texture directly on the GPU so it copies the texture to the CPU and then back to the GPU (video encoding unit). These operations are very slow and causes a lot of fps drops unless you have a fast CPU. This is especially noticable when recording at higher resolutions than 1080p.
								- ## How is this different from using FFMPEG with x11grab and nvenc?
								  
								  FFMPEG only uses the GPU with CUDA when doing transcoding from an input video to an output video, and not when recording the screen when using x11grab. So FFMPEG has the same fps drop issues that OBS has.
								- ## It tells me that my AMD/Intel GPU is not supported or that my GPU doesn't support h264/hevc, but that's not true!
								  
								  Some linux distros (such as manjaro and fedora) disable hardware accelerated h264/hevc on AMD/Intel because of "patent license issues". If you are using an arch-based distro then you can install mesa-git instead of mesa and if you are using another distro then you may have to switch to a better distro. On fedora based distros you can follow this: [Hardware Accelerated Codec](https://rpmfusion.org/Howto/Multimedia).  
								  If you installed GPU Screen Recorder flatpak then you can try installing mesa-extra freedesktop runtime by running this command: `flatpak install --system org.freedesktop.Platform.GL.default//23.08-extra`
								- ## I have an old nvidia GPU that supports nvenc but I get a cuda error when trying to record
								  
								  Newer ffmpeg versions don't support older nvidia cards. Try installing GPU Screen Recorder flatpak from [flathub](https://flathub.org/apps/details/com.dec05eba.gpu_screen_recorder) instead. It comes with an older ffmpeg version which might work for your GPU.
								- ## I get a black screen/glitches while live streaming
								  
								  It seems like ffmpeg earlier than version 6.1 has some type of bug. Install ffmpeg 6.1 and then reinstall GPU Screen Recorder to fix this issue. The flatpak version of GPU Screen Recorder comes with ffmpeg 6.1 so no extra steps are needed.
								- ## I can't play the video in my browser directly or in discord
								  
								  Browsers and discord don't support hevc video codec at the moment. Choose h264 video codec instead with the -k h264 option. Note that websites such as youtube support hevc so there is no need to choose h264 video codec if you intend to upload the video to youtube or if you want to play the video locally or if you intend to edit the video with a video editor. Hevc allows for better video quality (especially at lower file sizes) so hevc (or av1) is recommended for source videos.
								- ## I get a black bar on the right/bottom in the video
								  
								  This is mostly an issue on AMD and it's a hardware issue/ffmpeg issue. If you use HEVC video codec then it's an issue in ffmpeg and if you use AV1 then it's an issue in the video encoding unit on certain AMD gpus, see: https://gitlab.freedesktop.org/mesa/mesa/-/issues/9185. If you get black bars then the workaround is to record with h264 video codec instead (using the -k h264 option).
								- ## The video is glitched, looks like checkerboard pattern
								  
								  This is an issue on some intel integrated gpus on wayland caused by power saving option. Right now the only way to fix this is to record on X11 instead.
								- ## The video doesn't display or has a green/yellow overlay
								  
								  This can happen if your video player is missing the H264/HEVC video codecs. Either install the codecs or use mpv.
								- ## I get stutter in the video
								  
								  Try recording to an SSD and make sure it's not using NTFS file system. Also record in variable framerate format.
								- ## I get a black screen when recording
								  
								  This can happen if you use software such as prime-run to run GPU Screen Recorder. Such software should not be used to run GPU Screen Recorder. GPU Screen Recorder needs to run on the same GPU that you use to display your monitors graphics to work.
								- # Donations
								  
								  If you want to donate you can donate via bitcoin or monero.
								- Bitcoin: bc1qqvuqnwrdyppf707ge27fqz2n9y9gu7lf5ypyuf
								- Monero: 4An9kp2qW1C9Gah7ewv4JzcNFQ5TAX7ineGCqXWK6vQnhsGGcRpNgcn8r9EC3tMcgY7vqCKs3nSRXhejMHBaGvFdN2egYet
								- # TODO
								- Dynamically change bitrate/resolution to match desired fps. This would be helpful when streaming for example, where the encode output speed also depends on upload speed to the streaming service.
								- Implement opengl injection to capture texture. This fixes VRR without having to use NvFBC direct capture.
								- Always use direct capture with NvFBC once the capture issue in mpv fullscreen has been resolved (maybe detect if direct capture fails in nvfbc and switch to non-direct recording. NvFBC says if direct capture fails).
						- [ReplaySorcery](https://github.com/matanui159/ReplaySorcery)
						  id:: 65a98a51-f6a4-4740-ba45-6716a08a5423
						  collapsed:: true
							- Cons
							  collapsed:: true
								- Doesn't pull directly from the GPUs copy of the images without any relays to the CPU and back, unlike Shadowplay and ((63ad9567-857c-4b16-8292-abf0e85a0326))
						- [https://github.com/nowrep/obs-vkcapture/issues](https://github.com/nowrep/obs-vkcapture/issues)
						- Proprietary
							- Gyazo Replay
							  collapsed:: true
								- [https://blog.gyazo.com/post/185699827783/introducing-gyazo-replay-capture-the-last-30](https://blog.gyazo.com/post/185699827783/introducing-gyazo-replay-capture-the-last-30)
						-
					- Adobe Suite alternatives
					  collapsed:: true
					  id:: 635037c3-83e9-4e6e-9bf7-fc72233e1b78
						- Photoshop alternatives
							- Photopea
							  collapsed:: true
								- [https://alternativeto.net/software/photopea/reviews/](https://alternativeto.net/software/photopea/reviews/)
							- PhotoGIMP
							  collapsed:: true
								- [https://github.com/Diolinux/PhotoGIMP](https://github.com/Diolinux/PhotoGIMP)
							- Krita
						- Illustrator alternatives
							- VPaint
							  collapsed:: true
								- [https://github.com/dalboris/vpaint](https://github.com/dalboris/vpaint)
								- [http://www.vpaint.org/](http://www.vpaint.org/)
								- New versions
									- [https://www.vgc.io/](https://www.vgc.io/)
									- [https://www.kickstarter.com/projects/vgcsoftware/vgc-illustration-the-drawing-app-of-the-future](https://www.kickstarter.com/projects/vgcsoftware/vgc-illustration-the-drawing-app-of-the-future)
							- Inkscape
					- Expresso (portable file assocation manager)
					- GitHub - TheAssassin/AppImageLauncher: Helper application for Linux distributions serving as a kind of "entry point" for running and integrating AppImages
					  [https://github.com/TheAssassin/AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher)
					- _SOP for running alternatives_
					  collapsed:: true
						- Run in WINE or Darling or Hybris if necessary
						- https://help.ubuntu.com/community/SoftwareEquivalents
						- Consider Qemu (like VM app) for running Windows
						  http://www.qemu.org/
							- https://help.ubuntu.com/community/Installation/QemuEmulator?action=show&redirect=Qemu
					- Chromecast for streaming video from PC > TV (alternative to HDMI cable)
					  collapsed:: true
						- _Either_
							- VLC
								- https://www.howtogeek.com/269272/how-to-stream-from-vlc-to-your-chromecast/
							- fx_cast extension for Firefox
								- https://github.com/hensm/fx_cast
							- gnomecast
								- [https://github.com/keredson/gnomecast](https://github.com/keredson/gnomecast)
						- Chromecast alternatives
							- NymphCast
								- [https://news.ycombinator.com/item?id=27482699](https://news.ycombinator.com/item?id=27482699)
								- [https://github.com/MayaPosch/NymphCast/](https://github.com/MayaPosch/NymphCast/)
					- uswusp (implements sleep and hibernate in userspace)
					  collapsed:: true
						- [https://wiki.archlinux.org/index.php/Uswsusp](https://wiki.archlinux.org/index.php/Uswsusp)
						- [https://wiki.debian.org/Uswsusp](https://wiki.debian.org/Uswsusp)
				- Categories
					- Media Players
					  collapsed:: true
						- ((66a2459c-652b-4a8b-871b-594fc7b366a3))
						- ISRC
							- ISRC stands for International Standard Recording Code and is supposed to be the unique identifier for a sound recording. Essentially a passport number for a track. Read more on [Wikipedia](https://en.wikipedia.org/wiki/International_Standard_Recording_Code).
							- [ISRC Finder - Search the ISRC for 100+ million tracks on Spotify](https://www.isrcfinder.com/)
							- [Soundcharts API - Get song by ISRC](https://doc.api.soundcharts.com/api/v2/doc/reference/path/song/get-song-by-isrc)
							- Shazam unofficial APIs
								- [GitHub - loiccoyle/shazam-cli: 🎶 CLI music recognition using the Shazam API](https://github.com/loiccoyle/shazam-cli)
								- [Shazam APIs](https://rapidapi.com/collection/shazam-api)
								- [GitHub - shazamio/ShazamIO: 🎵 Is a free asynchronous library from reverse engineered Shazam API written in Python 3.8+ with asyncio and aiohttp.](https://github.com/shazamio/ShazamIO)
							- [MusicBrainz - the open music encyclopedia](https://musicbrainz.org/)
						- Related: ((644c0b47-f42b-4e17-9bb3-d734e6c72f5e))
				- Related:
					- [Linux-style portable apps](((6312a079-ed4b-4377-ba3a-4edce7119230)))
			- Other SOPs
			  collapsed:: true
				- How to swap from Kubuntu LTS to normal release
				  collapsed:: true
					- `sudo do-release-upgrade -d`
					- `sudo apt-get dist-upgrade -d`
					- `sudo nano /etc/update-manager/release-upgrades`
				- [How to upgrade distro version](https://help.ubuntu.com/community/HirsuteUpgrades/Kubuntu)
				  id:: 635037c3-6032-4f23-9ba6-288274d6e473
				  collapsed:: true
					- Ensure your current installation is updated: `sudo apt update && sudo apt dist-upgrade`
					- Upgrade (usually not offered until 3-4 months post-release)
						- `sudo do-release-upgrade -m desktop` to do it entirely in a terminal
						- `pkexec do-release-upgrade -m desktop -f DistUpgradeViewKDE` to do it via GUI
					- ((635037c3-a9a8-42d4-b2a6-236db1e2c86d))
					- [Essential and strongly recommended things to do directly after a Kubuntu 24.04 LTS installation](https://www.kubuntuforums.net/forum/currently-supported-releases/kubuntu-24-04-nitpick-noble-lts/post-installation-az/678534-essential-and-strongly-recommended-things-to-do-directly-after-a-kubuntu-24-04-lts-installation)
					- Check if you're on LTS channel or not
						- ((649b1287-c273-4971-aab4-dcc72fc35a14))
				- How to update kernel only
				  id:: 65a98a51-f005-464b-b741-f1f4ca7eb39e
				  collapsed:: true
					- [ubuntu-mainline-kernel.sh](https://github.com/pimlie/ubuntu-mainline-kernel.sh)
						- First step is to download the [ubuntu-mainline-kernel.sh](http://ubuntu-mainline-kernel.sh) Bash script utility
							- `git clone https://github.com/pimlie/ubuntu-mainline-kernel.sh`
								- `~/Documents/Git/Other/ubuntu-mainline-kernel.sh/`
						- `chmod +x ubuntu-mainline-kernel.sh`
						- `sudo mv ubuntu-mainline-kernel.sh /usr/local/bin/`
						- All is ready to upgrade the Ubuntu kernel to the latest version. To do so run do following command:
							- `sudo ubuntu-mainline-kernel.sh -i`
						- Other usage
							- `sudo ubuntu-mainline-kernel.sh -l`
							  List locally installed kernel versions
							- `sudo ubuntu-mainline-kernel.sh -u v6.8.0-060800`
							  Uninstall kernel [version] (v6.8.0-060800)
					- `uname -r`
					  Check your current kernel version
						- Results
							- [[2024-03-15 Friday]] `6.5.0-25-generic`
					- Reboot and it should be by default using the newer kernel
						- Though you can swap to using an older one in GRUB by using the advanced options
					-
				- How to rollback an apt-upgrade
				  collapsed:: true
					- 1
						- Get the `history.log` of what packages were updated when
							- I quickly ran [grep command](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/) as follows (replace 2016-01-17 07:56:42 date with your desired range):
							- `grep -A 2 'Start-Date: 2016-01-17 07:56:42' /var/log/apt/history.log `
					- 2
						- `find /var/lib/dpkg/info/ -name \*.list -mtime -3 | sed 's#.list$##;s#.*/##'` = Find packages installed in the last 3x24h:
						- `sudo apt-cache policy PROGRAM` = show available versions of a program
						- `sudo apt-get install PROGRAM=3.6.3` = install the 3.6.3 version of PROGRAM
						- apt-pinning, to prevent future updates:
							- Create a new file in /etc/apt/preferences.d/ (if >= 10.4) named after your program,
							- ```
							  Package: program
							  Pin: version 3.6.3*
							  Pin-Priority: 1000
							  ```
				- Moving Vaults to new locations
				  collapsed:: true
					- _Reconfiguring_
						- Calibre
							- Click on Calibre Library button > Switch Library > browse to new location
							  [https://i.imgur.com/sY8bUIQ.png](https://i.imgur.com/sY8bUIQ.png)
						- Firefox
							- Update the path to your profile
							  ~/.mozilla/firefox
							- Rename the extensions.json and compatibility.ini files in the profile folder so that when Firefox is next opened they'll regenerate again. This is required so extensions can be located
							  ~/.thunderbird/
						- Thunderbird
							- Rename the extensions.json and compatibility.ini files in the profile folder so that when Firefox is next opened they'll regenerate again. This is required so extensions can be located
				- Subscribed repos (Software Sources in launcher)
				  collapsed:: true
					- Note: remove any Source Code repos in "Other Software" that get automatically added
					- _Enabled_
						- Shiftkey (GitHub Desktop for Linux)
							- [https://github.com/shiftkey/desktop/](https://github.com/shiftkey/desktop/)
						- See [Kubuntu (/KDE Plasma)](https://workflowy.com/#/ae6be8b310d5) backports
							- Backports of new versions of KDE Platform, Plasma and Applications as well as major KDE apps for Kubuntu.
						- Lutris
						- ((663a5797-a9ea-4d4e-9619-01250a7ea8a6))
						- Vivaldi
						- Tailscale
						- Etebase
						- Libretro
					- _Currently disabled_
						- WineHQ WINE builds
						- Mono
						- Graphic drivers
					- _Recently removed_
						- Signal updates
						- UNetbootin ([https://launchpad.net/~gezakovacs/+archive/ubuntu/ppa](https://launchpad.net/~gezakovacs/+archive/ubuntu/ppa))
				- Opening GitHub repos in web-based ((63209272-1088-4824-a762-4ac7ded04b0a))
				  collapsed:: true
					- Either
						- [https://github.dev/GrapheneOS/platform_frameworks_base](https://github.dev/GrapheneOS/platform_frameworks_base) (example, just swap .com for .dev)
						- or
						- [https://gitpod.io](https://gitpod.io)
				- Streaming gameplay video
				  collapsed:: true
					- [https://teddit.net/r/linux_gaming/comments/sonc77/the_current_state_of_screen_sharing_in_linux/](https://teddit.net/r/linux_gaming/comments/sonc77/the_current_state_of_screen_sharing_in_linux/)
						- Discord, but needs workarounds to share audio.
							- [https://github.com/edisionnano/Screenshare-with-audio-on-Discord-with-Linux](https://github.com/edisionnano/Screenshare-with-audio-on-Discord-with-Linux)
						- ((644c0bb4-5d25-493b-a192-3ce2ff9229d0))
				- [FalsiScan: Make it look like a PDF has been hand signed and scanned](https://gitlab.com/edouardklein/falsisign)
				- [https://wiki.archlinux.org/title/Zswap](https://wiki.archlinux.org/title/Zswap)
				- LUKS - encrypt drive
				  collapsed:: true
				  dm-crypt / full-disk encryption (FDE)
					- Documentation
						- Setup
							- Ideal: do it during Kubuntu setup
								- Guided -use entire disk and set up encrypted lvm.
									- Everything on the hard drive is encrypted except a small /boot partition which holds the files needed to boot the machine to the state where it asks for your password.
							- If you don't want to reinstall and don't want to erase everything. The only option seems to be cryptsetup-reencrypt.
								- [https://wiki.archlinux.org/index.php/dm-crypt/Device_encryption#Re-encrypting_devices](https://wiki.archlinux.org/index.php/dm-crypt/Device_encryption#Re-encrypting_devices)
								- [https://superuser.com/questions/900881/full-disk-encryption-in-existing-linux-system-without-erasing-any-content-from-t](https://superuser.com/questions/900881/full-disk-encryption-in-existing-linux-system-without-erasing-any-content-from-t)
								- You need to reduce the size for the luks header.
						- Types
							- plain dm-crypt (one passphrase, no management, no metadata on disk)
								- Pros/Cons
									- Pros
										- Primary advantage is high resilience to damage, as one damaged encrypted sector results in exactly one damaged decrypted sector. Also, it is not readily apparent that there even is encrypted data on the device, as an overwrite with crypto-grade randomness (e.g. from /dev/urandom) looks exactly the same on disk.
											- Side-note: That has limited value against the authorities. In civilized countries, they cannot force you to give up a crypto-key anyways. In quite a few countries around the world, they can force you to give up the keys (using imprisonment or worse to pressure you, sometimes without due process), and in the worst case, they only need a nebulous "suspicion" about the presence of encrypted data. Sometimes this applies to everybody, sometimes only when you are suspected of having "illicit data" (definition subject to change) and sometimes specifically when crossing a border. Note that this is going on in countries like the US and the UK to different degrees and sometimes with courts restricting what the authorities can actually demand.
												- 1 Backlink
													- See [Side-note:](https://workflowy.com/#/20346ed4a5e3)
									- Cons
										- Disadvantages are that you do not have all the nice features that the LUKS metadata offers, like multiple passphrases that can be changed, the cipher being stored in the metadata, anti-forensic properties like key-slot diffusion and salts, etc..
							- LUKS (multiple user keys with one master key, anti-forensic features, metadata block at start of device, ...)
								- Pros/Cons
									- Pros
										- Advantages are a higher usability, automatic configuration of non-default crypto parameters, defenses against low-entropy passphrases like salting and iterated PBKDF2 or ARGON 2 passphrase hashing, the ability to change passphrases, and others.
									- Cons
										- Disadvantages are that it is readily obvious there is encrypted data on disk (but see side note above) and that damage to the header or key-slots usually results in permanent data-loss. See below under "6. Backup and Data Recovery" on how to reduce that risk. Also the sector numbers get shifted by the length of the header and key-slots and there is a loss of that size in capacity. Unless you have a specific need, use LUKS2.
											- See [Side-note:](https://workflowy.com/#/20346ed4a5e3)
					-
					- VeraCrypt can't do partition or disk (system) encryption for Linux
					- Setup LUKS + NUKE
						- Qubes+Whonix most secure option vs remote attacks
						- However this means you don't get the amnesic advantage of Tails vs local attacks
							- However hidden OS or containers achieves this on Fedora
							- for Qubes, not sure how it works yet. I get the feeling steganography is going to be quite difficult - it's more meant for combating remote attacks
						- Solution: setup the option to temporarily render your encrypted HDD inaccessible via an additional 'nuke' password [https://www.kali.org/tutorials/emergency-self-destruction-luks-kali/](https://www.kali.org/tutorials/emergency-self-destruction-luks-kali/)
						- This allows you to enter a different password to deletes your keyslots rather than decrypt your device
						- You can also backup these keyslots somewhere else (in an anonymous and encrypted form) to later decrypt the HDD
					- Linux full-disk/partition encryption with LUKS
						- (combined with filesystem encryption - can still use TrueCrypt)
						- https://en.wikipedia.org/wiki/GNOME_Disks
						- https://gitlab.com/cryptsetup/cryptsetup
						- [https://wiki.archlinux.org/index.php/Dm-crypt/Encrypting_an_entire_system](https://wiki.archlinux.org/index.php/Dm-crypt/Encrypting_an_entire_system#Simple_partition_layout_with_LUKS)
						- [http://www.cyberciti.biz/hardware/howto-linux-hard-disk-encryption-with-luks-cryptsetup-command/](http://www.cyberciti.biz/hardware/howto-linux-hard-disk-encryption-with-luks-cryptsetup-command/)
					- Plausible Deniability With LUKS | Blog
						- [https://blog.linuxbrujo.net/posts/plausible-deniability-with-luks/](https://blog.linuxbrujo.net/posts/plausible-deniability-with-luks/)
					- 2 Backlinks
						- _Intentionally last task of list:_ full disk encryption - [LUKS - encrypt drive](https://workflowy.com/#/79c9b4b09fdd)
						- See [LUKS - encrypt drive](https://workflowy.com/#/79c9b4b09fdd)
						  #PC-Linux
				- Consider disabling CPU mitigations
				  id:: 63113543-eadf-4b48-b71a-25ff73406edb
				  collapsed:: true
					- https://make-linux-fast-again.com : `noibrs noibpb nopti nospectre_v2 nospectre_v1 l1tf=off nospec_store_bypass_disable no_stf_barrier mds=off tsx=on tsx_async_abort=off mitigations=off `
						- Unless the linux system is an embedded device, the bootloader is most likely GRUB. For example, for Ubuntu the config file is found at /etc/default/grub, add the wanted parameters to the line starting with `GRUB_CMDLINE_LINUX_DEFAULT`. Save the changes and update GRUB with  `update-grub` , then reboot the system to activate the changes. More details about how to do this and also how to add temporary kernel parameters can be found in [the documentation for Ubuntu](https://web.archive.org/web/20220615110436/https://wiki.ubuntu.com/Kernel/KernelBootParameters).
						- [Explanation](https://transformingembedded.sigmatechnology.se/insight-post/make-linux-fast-again-for-mortals/)
							- Most of them can be found in the official [linux kernel documentation](https://web.archive.org/web/20220615110436/https://www.kernel.org/doc/html/latest/admin-guide/kernel-parameters.html), but interestingly not all are even documented, but let’s break down the descriptions of the different parameters:
							- `noibrs` Turns off [Indirect Branch Restricted Speculation (IBRS)](https://web.archive.org/web/20220615110436/https://software.intel.com/security-software-guidance/insights/deep-dive-indirect-branch-restricted-speculation), related to [the Spectre vulnerability](https://web.archive.org/web/20220615110436/https://www.kernel.org/doc/html/latest/admin-guide/hw-vuln/spectre.html).
							- `noibpb`Turn off [Indirect Branch Prediction Barrier (IBPB)](https://web.archive.org/web/20220615110436/https://software.intel.com/security-software-guidance/insights/deep-dive-indirect-branch-predictor-barrier), related to [the Spectre vulnerability](https://web.archive.org/web/20220615110436/https://www.kernel.org/doc/html/latest/admin-guide/hw-vuln/spectre.html).
							- `nopti` Control [Page Table Isolation](https://web.archive.org/web/20220615110436/https://meltdownattack.com/) of user and kernel address spaces.  Disabling this feature removes hardening, but improves performance of system calls and interrupts.
							- `nospectre_v2`Disable all mitigations for [the Spectre variant 2 (indirect branch prediction) vulnerability](https://web.archive.org/web/20220615110436/https://www.kernel.org/doc/html/latest/admin-guide/hw-vuln/spectre.html#spectre-variant-2-branch-target-injection). System may allow data leaks with this option.
							- `nospectre_v1` Disable mitigations for [Spectre Variant 1 (bounds check bypass)](https://web.archive.org/web/20220615110436/https://www.kernel.org/doc/html/latest/admin-guide/hw-vuln/spectre.html#spectre-variant-1-bounds-check-bypass). With this option data leaks are possible in the system.
							- `l1tf=off` Control mitigation of [the L1TF vulnerability](https://web.archive.org/web/20220615110436/https://www.kernel.org/doc/html/latest/admin-guide/hw-vuln/l1tf.html) on affected CPUs.
							- `nospec_store_bypass_disable` Disable all mitigations for [the Speculative Store Bypass vulnerability](https://web.archive.org/web/20220615110436/https://en.wikipedia.org/wiki/Speculative_Store_Bypass).
							- `no_stf_barrier` Parameter is not documented.
							- `mds=off` Control mitigation for [the Micro-architectural Data Sampling (MDS) vulnerability](https://web.archive.org/web/20220615110436/https://www.kernel.org/doc/html/latest/admin-guide/hw-vuln/mds.html).
							- `tsx=on`Control [Transactional Synchronization Extensions (TSX)](https://web.archive.org/web/20220615110436/https://en.wikipedia.org/wiki/Transactional_Synchronization_Extensions) feature in Intel processors that support TSX control. Although there are mitigations for all known security vulnerabilities, TSX has been known to be an accelerator for several previous speculation-related CVEs, and so there may be unknown security risks associated with leaving it enabled.
							- `tsx_async_abort=off`Control mitigation for [the TSX Async Abort (TAA) vulnerability](https://web.archive.org/web/20220615110436/https://www.kernel.org/doc/html/latest/admin-guide/hw-vuln/tsx_async_abort.html).
							- `mitigations=off`Disable all optional [CPU mitigations](https://web.archive.org/web/20220615110436/https://www.kernel.org/doc/html/latest/admin-guide/hw-vuln/index.html).  This improves system performance, but it may also expose users to several CPU vulnerabilities.
							- So, setting these kernel parameters will give the system a performance boost, but will also disabled a lot of mitigations and expose your system for security vulnerabilities such as [Meltdown and Spectre](https://web.archive.org/web/20220615110436/https://spectreattack.com/).
				- [Hardware Video Acceleration](https://wiki.debian.org/HardwareVideoAcceleration)
				  id:: 63567ca0-a57f-4976-9104-2d8ecd6ca428
				  collapsed:: true
					- [Testing](https://wiki.debian.org/HardwareVideoAcceleration#Checking_hardware_support)
						- [[2024-04-09 Tuesday]] On ((659d093f-bf67-444a-b2a1-ec0a28907583))
							- Seems to be working with ((6313458c-20f9-43f5-be52-44845eb02203)) playing
								- [`amdgpu_top`](https://github.com/Umio-Yasuno/amdgpu_top)
								  id:: 672b401b-3402-426f-b123-5573c7045819
								  `/home/boss/AppImages/amdgpu_top.appimage` in a terminal
									- `amdgpu_top --gui`
									- GRBM should go from near 0 to some percentage
									- Activity: GFX should go from near 0 to near 40%
									- In `fdinfo` section it's likely to say that CPU usage will be higher than GFX even still
								- [`radeontop`](https://github.com/clbr/radeontop)
								- `vainfo` - [seems correct](https://wiki.archlinux.org/title/Hardware_video_acceleration#Verifying_VA-API)
								  collapsed:: true
									- ```
									  vainfo
									  libva info: VA-API version 1.19.0
									  libva info: Trying to open /usr/lib/x86_64-linux-gnu/dri/radeonsi_drv_video.so
									  libva info: Found init function __vaDriverInit_1_19
									  libva info: va_openDriver() returns 0
									  vainfo: VA-API version: 1.19 (libva 2.12.0)
									  vainfo: Driver version: Mesa Gallium driver 23.2.1-1ubuntu3.1 for AMD Radeon Graphics (gfx1103_r1, LLVM 15.0.7, DRM 3.54, 6.5.0-28-generic)
									  vainfo: Supported profile and entrypoints
									        VAProfileH264ConstrainedBaseline: VAEntrypointVLD
									        VAProfileH264ConstrainedBaseline: VAEntrypointEncSlice
									        VAProfileH264Main               : VAEntrypointVLD
									        VAProfileH264Main               : VAEntrypointEncSlice
									        VAProfileH264High               : VAEntrypointVLD
									        VAProfileH264High               : VAEntrypointEncSlice
									        VAProfileHEVCMain               : VAEntrypointVLD
									        VAProfileHEVCMain               : VAEntrypointEncSlice
									        VAProfileHEVCMain10             : VAEntrypointVLD
									        VAProfileHEVCMain10             : VAEntrypointEncSlice
									        VAProfileJPEGBaseline           : VAEntrypointVLD
									        VAProfileVP9Profile0            : VAEntrypointVLD
									        VAProfileVP9Profile2            : VAEntrypointVLD
									        VAProfileAV1Profile0            : VAEntrypointVLD
									        VAProfileAV1Profile0            : VAEntrypointEncSlice
									        VAProfileNone                   : VAEntrypointVideoProc
									  ```
									- `VAEntrypointVLD` means that your card is capable to decode this format, `VAEntrypointEncSlice` means that you can encode to this format.
								- `glxinfo | grep OpenGL`
								  collapsed:: true
									- in the line beginning with "OpenGL renderer string", if you see the word Mesa it would mean that the Mesa stack libraries are doing the accel rather than hardware. And if you see the word llvmpipe in there that's a dead giveaway that hardware accel isn't working.
							- Appears to not be working
								- `nvtop` - see ENC/DEC
								- [Error 403 (Forbidden)!!1](https://issues.chromium.org/issues/40267998#comment24) affects FreeTube's Electron
								-
							- Not clear if the output is correct
						- [[2022-10-26 Wednesday]] on ((65a98a50-4b57-4816-931f-24253c6bc8b7)), testing with `sudo intel_gpu_top`. Several apps worked, others didn't
						  collapsed:: true
							- ```bash
							  sudo apt install intel-gpu-tools
							  sudo intel-gpu-tools
							  ```
							- *Works*
								- WORK browser - YouTube
								- MASTER browser
								- Firefox native
							- *Doesn't work*
								- ((6313458c-20f9-43f5-be52-44845eb02203))
								- Chromium Flatpak
								- Brave Flatpak
								- Brave native
								- Google Chrome
								- Zoom Flatpak
							- Untested
								- Zoom native
					- ((63134593-906c-43b5-96fe-33dc2c34fda4)) : ((635037e8-1155-4253-a10e-36bec5ecc740))
					- ((649b140b-1732-4689-9331-10b5b97e5e5e)) notes
					  collapsed:: true
						- https://wiki.debian.org/Chromium#Video_acceleration
						- ```bash
						  sudo apt install intel-media-va-driver-non-free libva-drm2 libva-x11-2
						  
						  The following packages will be REMOVED
						    intel-media-va-driver intel-media-va-driver:i386
						  The following NEW packages will be installed
						    intel-media-va-driver-non-free
						  ```
						- [[HowTo] Enable Hardware Video Acceleration / Video Decode In Google Chrome, Brave, Vivaldi And Opera Browsers - Tutorials - Manjaro Linux Forum](https://forum.manjaro.org/t/howto-enable-hardware-video-acceleration-video-decode-in-google-chrome-brave-vivaldi-and-opera-browsers/51895)
						- https://wiki.archlinux.org/title/Chromium#Hardware_video_acceleration
						- Brave doesn't recognise the two of the flags trying to use on the command line
							- ```
							  boss@boss-XPS:~$ /usr/bin/flatpak run --branch=stable --arch=x86_64 --command=brave --file-forwarding --enable-features=VaapiVideoDecoder --use-gl=egl com.brave.Browser @@u %U @@
							  error: Unknown option --enable-features=VaapiVideoDecoder
							  boss@boss-XPS:~$ /usr/bin/flatpak run --branch=stable --arch=x86_64 --command=brave --file-forwarding --use-gl=egl com.brave.Browser @@u %U @@
							  error: Unknown option --use-gl=egl
							  ```
							- g
							- hr
							- e
							-
						- Brave
							- ```
							  brave://flags/#ignore-gpu-blocklist
							  ```
							- ```
							  brave://flags/#enable-gpu-rasterization
							  ```
							- ```
							  brave://flags/#enable-zero-copy
							  ```
						- Chromium
							- ```
							  chrome://flags/#ignore-gpu-blocklist
							  ```
							- ```
							  chrome://flags/#enable-gpu-rasterization
							  ```
							- ```
							  chrome://flags/#enable-zero-copy
							  ```
						- Related: Firefox ((635037e8-1155-4253-a10e-36bec5ecc740))
					- ((6313458c-20f9-43f5-be52-44845eb02203)) : ((66433455-11d9-44c3-b1c4-5a7bf096725b))
					- ((66a2459c-5616-4c23-bb40-04367db10e0e)) : ((39f664d6-97dd-4e7e-b3cb-380d365ed747))
				- How to setup local URI / deeplink opening
				  id:: 65a98a51-0b92-4884-bdea-87e4db5ed40a
				  collapsed:: true
					- You need to create a [desktop entry](https://www.freedesktop.org/wiki/Specifications/desktop-entry-spec/) with a MimeType of "x-scheme-handler/<scheme>". For instance,  `/usr/share/applications/steam.desktop` , the default Steam desktop entry on my system, contains `MimeType=x-scheme-handler/steam;x-scheme-handler/steamlink;`
						- Test it with  `xdg-open`
					- [source] [How can I make a Steam URL entered in my browser automatically open in Steam : linux_gaming](https://teddit.namazso.eu/r/linux_gaming/comments/yh0iou/how_can_i_make_a_steam_url_entered_in_my_browser/iubo507?context=3)
				- Audio
				  collapsed:: true
					- How to record audio loopback:
						- Open Audacity and start recording
						  Open pavucontrol, then on Recording tab change it to `Monitor of Combined` or a different audio output channel
						  It'll remember this setting until closed
					- Note: to enable galaxy Buds as a microphone, open audio devices > change Profile to `Headset Head Unit (HSP/HFP, codec CVSD`
						- Note2: enabling microphone will reduce headphone/audio output quality
					- Fixing problem with Signal audio not being heard (troubleshooting) [[2023-02-01 Wednesday]]
					  id:: 640e4803-9440-4fe7-9320-cb55e7cc3ffd
					  collapsed:: true
						- ![Screenshot_20230129_211120.png](../assets/Screenshot_20230129_211120_1678657591480_0.png)
						- ![Screenshot_20230129_211311.png](../assets/Screenshot_20230129_211311_1678657598679_0.png)
			- _Launchers, autostart etc_
			  collapsed:: true
				- CTRL+SHIFT+drag to create a link to a file/folder
				- Increase touchpad acceleration
				  collapsed:: true
					- System Settings > Input Devices > Touchpad
					- Pointer Motion > Acceleration > max
					- _Related:_ [syngesture](https://workflowy.com/#/83761174f62b)
					- 1 Backlink
						- _Related:_ [Increase touchpad acceleration](https://workflowy.com/#/7ec06d086926)
				- Autostart
				  collapsed:: true
					- KDocker
					- Flameshot
					- Yakuake
					- Syncthing Tray
					- See [CrashPlan](https://workflowy.com/#/03f7394dbb03)
					  #Software
					- VeraCrypt
					- _Remove_
						- Alarm Clock
					- _These apps will open on boot naturally if not closed_
						- Yakuake
						- Launchy
						- NetWorx
				- Autostart-like for VeraCrypt container programs
				  collapsed:: true
				  Noteworthy; but nothing needs to be done here
					- Create the bash script 'deskopen'
						- `grep '^Exec' filename.desktop | tail -1 | sed 's/^Exec=//' | sed 's/%.//' | sed 's/^"//g' | sed 's/" *$//g'` &
						  source:: https://askubuntu.com/a/5174
						- Create startup.sh in VeraCrypt container
							- e.g.
							  #!/bin/bash
							  
							  deskopen Browsers/LEISURE/LEISURE.desktop
					- Qomui
					- KeePass
					- Thunderbird
				-
		- Related: ((62e11d87-874f-4112-8bd5-a0a8f6651248))
	- SOPs
		- How to clone one drive to another
		  collapsed:: true
			- [Clonezilla - About](https://clonezilla.org/)
			- dd: A command-line utility that can be used to clone an entire hard drive, including partitioning information and data. However, it’s recommended to use caution when using dd, as it can be destructive if not used correctly.
			- ### How to resize an encrypted LLVM partition
				- [1](https://code.whatever.social/exchange/unix/questions/320957/extend-a-luks-encrypted-partition-to-fill-disk#548319)
					- For those that come to the answer to find out how to simply resize a 
					  LUKS partition to the size of the resized container, the commands are as
					   follows:
					- with LUKS encrypted volume *opened* and the opened volume mapped as `opened-volume`, execute
					  
					  ```
					  sudo cryptsetup resize /dev/mapper/opened-volume
					  ```
					  
					  to resize the LUKS encrypted volume online...
					- then resize the contents.
						- E.g. if it is an **Ext4 filesystem**, you can resize it even if it is mounted with
						  
						  ```
						  sudo resize2fs /dev/mapper/opened-volume
						  ```
						- Or if you had a **LVM *physical volume*** *inside* the LUKS encrypted volume, just use `pvresize`:
						  
						  ```
						  sudo pvresize /dev/mapper/opened-volume
						  ```
						- I've done this with a mounted file system/activated PV with no 
						  interruption; it was possible to resize the container without unmounting
						  it first because the encrypted volume was on a LVM logical volume 
						  (using `lvresize`) / using `parted` to resize a GPT partition to contain the free space that immediately followed it!
				- [2](https://code.whatever.social/exchange/unix/questions/320957/extend-a-luks-encrypted-partition-to-fill-disk#322631)
					- OK! The definitive answer finally. My steps to expand a LUKS encrypted volume...
					- 1.  `cryptsetup luksOpen /dev/sda2 crypt-volume` to open the encrypted volume.
					- 2.  `parted /dev/sda` to extend the partition. `resizepart NUMBER END`.
						- On Ubuntu 20.04 I used `fdisk` instead of `parted` in step 2 because it has a resize option. And for `lvresize` the LV path changed (it's not in a subdirectory).
					- 3.  `vgchange -a n fedora_chocbar`. Stop using the VG so you can do the next step.
					- 4.  `cryptsetup luksClose crypt-volume`. Close the encrypted volume for the next steps.
					- 5.  `cryptsetup luksOpen /dev/sda2 crypt-volume`. Open it again.
					- 6.  `cryptsetup resize crypt-volume`. Will automatically resize the LUKS volume to the available space.
					- 7.  `vgchange -a y fedora_chocbar`. Activate the VG.
						- I had one step in there, let's call it step 7.5 where I had to unlock my physical volume:    `sudo pvchange -x y /dev/mapper/crypt-volume` (via ubuntu docs [help.ubuntu.com/community/ResizeEncryptedPartitions](https://help.ubuntu.com/community/ResizeEncryptedPartitions))
					- 8.  `pvresize /dev/mapper/crypt-volume`. Resize the PV.
					- 9.  `lvresize -l+100%FREE /dev/fedora_chocbar/home`. Resize the LV for /home to 100% of the free space.
					- 10.  `e2fsck -f /dev/mapper/fedora_chocbar-home`. Throw some fsck magic at the resized fs.
					- 11.  `resize2fs /dev/mapper/fedora_chocbar-home`. Resize the filesystem in /home (automatically uses 100% free space)
					- I hope someone else finds this useful. I now have 300+GB for my test VMs on my laptop!
	- Troubleshooting
	  id:: 63a9adc7-4cc4-4ecc-933c-82c3163cfe29
	  collapsed:: true
		- Process analysis
			- `ps -Ao user,uid,comm,pid,pcpu,pmem --sort=-pcpu | head -n 10`
			  Top 10 CPU using processes
			- `glances`
		- ((63567ca0-a57f-4976-9104-2d8ecd6ca428))
		- ((640e4803-9440-4fe7-9320-cb55e7cc3ffd))
		- Can't boot into OS
		  collapsed:: true
			- Steps
				- Press F2 during boot to open BIOS. Set Boot Sequence so that a USB drive is the first option
				- Boot into USB with Kubuntu installed on it (eg via Rufus)
				- Shrink partition using GParted and have 30GB spare for a new partition
				- Install Kubuntu on the new partition
		- Fix laptop sleep and hibernate
		  collapsed:: true
			- Hibernate - seems to poweroff instead
			- Sleep - it wakes up after a while
				- Fix laptop being unable to stay asleep whilst an external monitor is plugged in
					- My reported bug
					  [https://bugs.kde.org/show_bug.cgi?id=455246](https://bugs.kde.org/show_bug.cgi?id=455246)
					- This command reveals PowerDevil as the blocker
					  `sudo systemd-inhibit --list`
		- Install `/home` on a separate partition
		  collapsed:: true
			- This way upgrading and swapping OS doesn't affect my homedir, similarly to Android
		- Clearing data
		  collapsed:: true
			- Reducing size of `/var/log/journal/`
				- `journalctl --vacuum-size=200M`
				  Will reduce size of dir to ~200MB
		- Related:
			- ((62e11d87-874f-4112-8bd5-a0a8f6651248)) : ((63a9adc7-b38b-4994-b83f-439b1c2217e3))
			- ((63a9adc8-6bc0-4ac7-8df3-f879b95211b5)) : ((63accb71-2c43-4827-b4a5-b550dfedc9ac))
- Related: [[PC]]