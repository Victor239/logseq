- Communication
  id:: 649161c6-a0b5-4018-a8ba-911907ababda
	- File-Sharing
	  collapsed:: true
	  AKA file transfer
		- **Easiest**
		  collapsed:: true
			- Google Drive or Dropbox
			  Low privacy but already setup
			- ((63a9ade4-acd5-44f9-9166-2c1393865f7a))
			- See [Signal](https://workflowy.com/#/626a051be085)
			  #Software-Chat
			- See OnionShare
		- _Hosted, E2EE_
		  collapsed:: true
			- _Temporary_
			  collapsed:: true
				- FileSend by Standard Notes company (50mb max; download once; lifespan max 5 days)
				  https://filesend.standardnotes.org/
					- Files are deleted immediately after the recipient downloads them, or after specified duration. Extended members get some extra power-features, like email confirmation when their file is downloaded. It's also completely open-source, so feel free to self-host to get your own personal file-sharing portal.
				- Firefox Send (1GB max or 2.5GB if signed in;
				  id:: 650aae19-5fc1-4605-8fe2-5bef37439231
				  [[404: Page Not Found](https://send.firefox.com/](https://send.firefox.com/))
					- [https://github.com/timvisee/send](https://github.com/timvisee/send)
					- Instances
					  [https://github.com/timvisee/send-instances/](https://github.com/timvisee/send-instances/)
						- [https://send.vis.ee/](https://send.vis.ee/)
			- Keybase Filesystem
			  #Privacy https://workflowy.com/#/cb2cdf39737d
			- Nextcloud (once sharing is enabled)
			  https://help.nextcloud.com/t/end-to-end-encryption-on-14/37080/3
			- _Decentralised_
			  collapsed:: true
				- SkyTransfer
				  [https://skytransfer.hns.siasky.net/#/](https://skytransfer.hns.siasky.net/#/)
					- Free, Open-Source, Decentralized and Encrypted File-Sharing
					- it operates more like Dropbox/GDrive; your uploaded files are displayed on a shareable download link, rather than only supporting one-off uploads like SkySend.
					- Both services are identical in that they encrypt files before storing them (somewhere) on Sia Skynet for approximately 3 months:
		- _Self-hosted, E2EE_
		  collapsed:: true
			- ((650aae19-56a4-43ed-b1dc-b3acd07ea36e)) eg Element, Signal, Wire
		- P2P
		  collapsed:: true
			- _Best for LAN_
				- ((63a9ade4-acd5-44f9-9166-2c1393865f7a))
			- _WebRTC-based_
				- Webwormhole
				  collapsed:: true
					- [https://webwormhole.io](https://webwormhole.io)
					- [https://github.com/saljam/webwormhole](https://github.com/saljam/webwormhole)
					- Has a CLI unlike [Filepizza](https://workflowy.com/#/36edf1dab5e0)
				- Filepizza
				  collapsed:: true
					- [https://file.pizza](https://file.pizza)
					- [https://github.com/kern/filepizza](https://github.com/kern/filepizza)
					- 1 Backlink
						- Has a CLI unlike [Filepizza](https://workflowy.com/#/36edf1dab5e0)
				- Snapdrop -  AirDrop equivalent through a web browser using WebRTC
				  collapsed:: true
				  [snapdrop.net](http://snapdrop.net)
					- [https://news.ycombinator.com/item?id=25524472](https://news.ycombinator.com/item?id=25524472)
					- [https://github.com/RobinLinus/snapdrop](https://github.com/RobinLinus/snapdrop)
				- ShareDrop (supports LAN)
				  collapsed:: true
					- [https://www.sharedrop.io/](https://www.sharedrop.io/)
					- [https://github.com/szimek/sharedrop](https://github.com/szimek/sharedrop)
					- Also has QR codes
			- Magic Wormhole
				- [https://github.com/magic-wormhole/magic-wormhole](https://github.com/magic-wormhole/magic-wormhole)
				- [https://magic-wormhole.readthedocs.io/en/latest/welcome.html#development](https://magic-wormhole.readthedocs.io/en/latest/welcome.html#development)
			- [[Software]] : [Syncthing](((6312a076-d503-40c4-b98f-cbdef17b1fcb)))
			- See [File Sync & Backup ](https://workflowy.com/#/bf8aafdbcfc3)
			- With onion routing
			  Anonymity
				- OnionShare
				  collapsed:: true
					- https://onionshare.org/
					- The person who is receiving the files doesn't need OnionShare. All they need is to open the URL you send them _in Tor Browser_ to be able to download the file.
					- P2P via hosting a hidden service (Windows exe available)
				- Briar
				- Ricochet file-sending ?
				  Not sure if available yet
				- Darknet e.g. GNUnet
				- RetroShare over Tor
				  collapsed:: true
					- https://retroshare.github.io/
					- https://en.wikipedia.org/w/index.php?title=Retroshare&redirect=no
				- ((644c0b2c-9d77-4496-9aac-e6a7149e0aa9)) with 3 hop routing
	- _Chat Apps _
	  id:: 64463cc5-2aa5-4916-8686-c3f6d3c46a08
	  collapsed:: true
	  #Software-Chat
		- Text Chat
		  collapsed:: true
			- **Types**
				- Encrypted Chat
				  id:: 650aae19-56a4-43ed-b1dc-b3acd07ea36e
				  collapsed:: true
				  #EncryptedChat
					- Pros/Cons
					  collapsed:: true
						- Pros
							- ((62e8df1d-bbaf-4397-b579-8e1a58255093))
							- Dedicated Fuck Phone in future
							  ((6447c671-0b43-4a05-97b5-b742eea57575))
							- Minimal sharing unless high ROI
							  ((6320926a-f742-4c88-9f73-e6a606d61ecc))
							- Global surveillance
							  #Privacy
						- Cons
							-
						- Unclear
						- Comparisons
					- Meta
						- [Messenger Matrix](https://www.messenger-matrix.de/messenger-matrix-en.html)
						  [[2024-10-20 Sunday]] Seems maintained
					- # Non-P2P, E2EE
						- ## Centralised, but metadata minimising
						  Silo / walled garden /
							- [Signal](https://signal.org/)
							  id:: 6312a076-eb26-4bd5-a669-ea0a50d06668
							  collapsed:: true
								- Links
									- [Forum](https://whispersystems.discoursehosting.net/)
								- # Pros/Cons
									- ## Pros
										- They only retain data for account creation date + date when user last was online
										  collapsed:: true
											- [source] [https://signal.org/bigbrother/central-california-grand-jury/](https://signal.org/bigbrother/central-california-grand-jury/)
										- End-to-end encryption for 1:1, group chats and phone calls
										- _Unique privacy features which limit metadata_
										  collapsed:: true
											- [Encrypted Profiles](https://signal.org/blog/signal-profiles-beta/) (profile name, picture)
												- Your profile (avatar and name) are public to contacts, when you initiate or accept new conversations, and when you join new groups
											- [Sealed Sender](https://signal.org/blog/sealed-sender/) feature (pre-req: Encrypted Profiles)
												- hiding another piece of metadata: who is messaging whom.
												- Probably the biggest metadata issue in chat apps
											- [Private Contact Discovery](https://signal.org/blog/private-contact-discovery/)
											  id:: 663b24fb-4437-4115-83da-5f5b668989fc
											  doesn't share contacts with Signal service
												- allows Signal users to discover their social graph without revealing their contacts to the Signal service
											- [Secure Value Recovery](https://signal.org/blog/secure-value-recovery/)
											  id:: 663b24fb-4803-4e0d-81ab-13c05c081c5e
											  for securely storing minimal data (contacts, settings) on their servers
												- Basically adds up to a secure enclave that limits the number of recovery attempts that are possible against a value synchronized across nodes in hardware-encrypted RAM.
												- allows you to store an E2EE contacts list in the cloud, secured by a PIN
												- _Used for _
													- Registration Lock
														- [https://support.signal.org/hc/en-us/articles/360007059792-Registration-Lock](https://support.signal.org/hc/en-us/articles/360007059792-Registration-Lock)
														- [https://signal.org/blog/improving-registration-lock/](https://signal.org/blog/improving-registration-lock/)
												- More info
													- [https://github.com/signalapp/SecureValueRecovery](https://github.com/signalapp/SecureValueRecovery)
													- [[Signal >> 404 Page Not Found](https://signal.org/blog/secure-value-recovery/](https://signal.org/blog/secure-value-recovery/))
											- Other private features
												- _How it works_
												- [Giphy search](https://signal.org/blog/signal-and-giphy-update/)
												  id:: 663b24fb-81c6-494f-a908-24f77daf26b2
													- Connections are E2EE + proxied via Signal servers, so 3rd party thinks Signal is the viewer
													- Signal is only aware of the domain you connect to, not the webpage URL
														- Padding is used to help prevent Signal tracking what content is being accessed
												- [Link Previews](https://signal.org/blog/i-link-therefore-i-am/)
													- Uses similar proxying as their ((663b24fb-81c6-494f-a908-24f77daf26b2))
													- Signal is using sender-side link previews:
													- This approach assumes that whoever is sending the link must trust it, since it'll be the sender's app that will have to open the link.”
												- [Signals PINs](https://signal.org/blog/signal-pins)
													- Not used for opening the app
													- It's used for storing and restoring your profile, settings and contacts when you reinstall
													- based on ((663b24fb-4803-4e0d-81ab-13c05c081c5e))
													-
											- Related: Feature requests in Element
										- Security features
										  collapsed:: true
											- [Desktop app database encryption](https://github.com/signalapp/Signal-Desktop/pull/6849#issuecomment-2218845070)
										- Usability features
										  collapsed:: true
											- [Encrypted cloud backup solution](https://community.signalusers.org/t/encrypted-cloud-backups/2798/215)
											  collapsed:: true
												- Related: [No backup at all for iOS possible](https://community.signalusers.org/t/ios-backup-keeping-message-history-when-switching-phones/1736/143)
											- Group adminstration e.g. removing people
											  [https://signal.org/blog/new-groups/](https://signal.org/blog/new-groups/)
											- @ mentions
											  https://community.signalusers.org/t/mention-tagging-in-groups/2939/23
											- Pin conversations
											  [https://community.signalusers.org/t/pin-conversation-to-the-top/4127/26](https://community.signalusers.org/t/pin-conversation-to-the-top/4127/26)
											- Edit/delete sent messages
											  [https://community.signalusers.org/t/edit-or-delete-messages-after-theyre-sent/975/280](https://community.signalusers.org/t/edit-or-delete-messages-after-theyre-sent/975/280)
											- Emoji reactions
											  https://community.signalusers.org/t/emoji-reactions/2776/64
											- Typing indicators and read receipts
											- Full-text search
										- Great stickers support
										  collapsed:: true
											- [https://signalstickers.com/](https://signalstickers.com/)
											- [https://sticker201.github.io/signalstickers/](https://sticker201.github.io/signalstickers/) / <a href="https://github.com/signalstickers/signalstickers">https://github.com/signalstickers/signalstickers</a>
											- [https://signal-stickers.github.io/](https://signal-stickers.github.io/)
											- [https://www.reddit.com/r/signal/?f=flair_name%3A%22Stickers%20%3Apalette%3A%22](https://www.reddit.com/r/signal/?f=flair_name%3A%22Stickers%20%3Apalette%3A%22)
											-
										- Unofficial Linux support WIP
										  collapsed:: true
											- Whisperfish for SailfishOS
											  [https://gitlab.com/whisperfish/whisperfish](https://gitlab.com/whisperfish/whisperfish)
											- Decoupling Whisperfish from SailfishOS to allow using it on other Linux distros
											  [https://gitlab.com/whisperfish/whisperfish/-/issues/318#note_560311275](https://gitlab.com/whisperfish/whisperfish/-/issues/318#note_560311275)
											- Compiling Signal Desktop to Linux phones
											  [https://github.com/signalapp/Signal-Desktop/issues/3410#issuecomment-831223772](https://github.com/signalapp/Signal-Desktop/issues/3410#issuecomment-831223772)
										- No longer need to use your phone number as an identifier
										  collapsed:: true
											- **Note: **Pointless registering a spare SIM with Signal
												- each phone has an ID number (called "IMEI"), and carriers keep records of which IMEIs have been used with each SIM card. That makes it very easy to associate your temporary SIM with your main one (and such lines of inquiry are standard operating procedure, by the way).
													- Good point, I didn't realise that. I guess there's no way of hiding your primary Signal number then if your threat model means that carriers would share data with Gov agencies to identify you.
													- This means if you want to have encrypted group chats, you should only share your Signal number with vetted individuals. Otherwise, stick to Telegram for 1:1 secret chats.
												- Also WhatsApp can read your IMEI - means changing your verified number is pointless
												- But it's still useful for hiding your number from fellow WhatsApp users
											- Requires a phone number - strong identifier
												- Relies on phone number (like WhatsApp) so not ideal for travellers but easiest solution for short-term
													- Actually you can just change your number (like WhatsApp)
												- The Address Book is the Social graph
													- The Address Book is the Social Network
													- Open Whisper Systems uses your contacts database for contact discovery. Initially they were using a private protocol discovery protocol based on bloom filters, but they were unable to scale up as their user base grew. To preserve privacy they now offer only the claim that they don’t store any information.
													- the only thing we can do is write the server such that it doesn’t store the transmitted contact information, inform the user, and give them the choice of opting out.
														- Source: https://whispersystems.org/blog/contact-discovery/
													- In theory Open Whisper Systems is entirely capable of storing the contacts database and using it to build a detailed social network graph. Their servers receive the entire address book and can store it, although they claim not to.
												- Identifier - easy to deanonymise if you give away your phone number
												- Whisper Systems knows phone contacts list, IMEI, phone number etc
											- You need to share your phone number with any Signal contact
											- eliminating the need for user names or passwords and facilitating contact discovery
									- ## Cons
										- ((643afaae-59a0-4cec-9333-4324e3f3c991))/PipeWire issues
										  id:: 663b24fb-fa04-4f84-8b19-1743340928aa
											- Signal doesn't build with PipeWire support. Thus screensharing doesn't support PipeWire, and is therefore broken on a Wayland DE
											  [https://github.com/signalapp/Signal-Desktop/issues/5350#issuecomment-1149184730](https://github.com/signalapp/Signal-Desktop/issues/5350#issuecomment-1149184730)
											- Signal has to be launched with a flag for native Wayland mode `signal-desktop --ozone-platform=wayland`
											- [In Wayland mode on Wayland Signal forgets which monitor it was open on last when closing to tray](https://github.com/signalapp/Signal-Desktop/issues/5990)
										- Based in the ((644c0a60-ef50-4b15-9795-f3b099a25ec2))
										  collapsed:: true
											- What if their hands are tied with a gag order? Just because they dont keep prior logs doesnt mean if under legal pressure they will not hesitate to begin logging on a particular user.
											- They'd be able to
										- Discord features
											- ((650aae18-8ef3-4788-aa7b-838f8a0a4397))
										- Privacy critique posts
											- [archivebox] [https://github.com/privacytools/privacytools.io/issues/779](https://github.com/privacytools/privacytools.io/issues/779) / <a href="http://127.0.0.1:8193/archive/1623518161.772621/singlefile.html">http://127.0.0.1:8193/archive/1623518161.772621/singlefile.html</a>
											  id:: 663b24fb-808b-4427-9c56-bd33675e1721
											- Their server infrastructure uses privacy adversaries like AWS and Google
											  ((663b24fb-808b-4427-9c56-bd33675e1721))
											- Hides the key verification screen so 0.001% of users will likely use it to verify other contacts
											  collapsed:: true
												- Click on contact > scroll to bottom > View safety number
												- Threema shows the verification status for every chat (and it's FOSS now)
											- Relies on Intel SGX for part of their security, which could be backdoored
											- [The website APK will detect whether there's Play Services available during registration, and only then decide on websocket or not](https://github.com/signalapp/Signal-Android/issues/9966#issuecomment-681943985). Note the APK is self-updating also
										- They haven't taken ownership of Signal Flatpak
											- [Feature Request: Flatpak for Linux · Issue #1639 · signalapp/Signal-Desktop · GitHub](https://github.com/signalapp/Signal-Desktop/issues/1639#issuecomment-2372632613)
											- [Taking ownership of Signal Flatpak? - #45 by LucasMZ - General Discussion - Signal Community](https://community.signalusers.org/t/taking-ownership-of-signal-flatpak/53958/45)
											- #+BEGIN_NOTE
											  I've deleted the Signal Desktop native install script `/home/boss/Documents/ESSENTIALS/installs/3rd-party-packages/signal.sh` (available in git history) because I just use the Flatpak regardless as I prefer knowing where the directories are, Flatpak portals, etc
											  #+END_NOTE
										- ### Lacks
											- _Very useful_
												- [Starred/pinned/bookmarked individual messages](https://community.signalusers.org/t/bookmarks-favorites-starred-pinned-messages/6004)
												  id:: 650aae18-8ef3-4788-aa7b-838f8a0a4397
												  collapsed:: true
													- This isnt simple for Signal to 0 implement since normally old message history isn't synced to new devices for security reasons
													- [https://community.signalusers.org/t/bookmark-messages-functionality/6004/12](https://community.signalusers.org/t/bookmark-messages-functionality/6004/12)
													- https://community.signalusers.org/t/pin-a-message-in-a-group-chat/8413
											- _Somewhat useful_
												- [Message history sync for newly linked (desktop) devices](https://community.signalusers.org/t/message-history-sync-for-newly-linked-desktop-devices/2839/40)
												  collapsed:: true
													- [https://community.signalusers.org/t/allow-android-ios-devices-e-g-tablets-to-be-linked-to-the-primary-device-i-e-used-as-secondary-device-like-the-desktop-app/2884/124](https://community.signalusers.org/t/allow-android-ios-devices-e-g-tablets-to-be-linked-to-the-primary-device-i-e-used-as-secondary-device-like-the-desktop-app/2884/124)
													- “For your security, conversation history isn’t transferred to new linked devices”.
												- [Shows one person typing indicator currently, but not several people](https://community.signalusers.org/t/show-other-users-typing/2215/186)
												- [Channels](https://community.signalusers.org/t/infogroups-channels/4798/43)
												- [Lock desktop app with password](https://community.signalusers.org/t/why-cant-we-lock-the-desktop-app-with-a-password/1383/149)
											- _Minor _
												- [Group chat polls - #222 by chiwaijm - Feature Requests - Signal Community](https://community.signalusers.org/t/group-chat-polls/3474/222?u=wantnot)
												- [Multiple profiles](https://community.signalusers.org/t/multiple-separate-user-profiles-for-example-but-not-exclusive-to-dual-sim-phones/2361/17)
											- {Archive}
											  collapsed:: true
												- [Broadcast messages](https://community.signalusers.org/t/send-signal-messages-sms-mms-to-multiple-recipients/222)
												- [Stories / Status Updates](https://community.signalusers.org/t/stories-status-updates/2565/91)
												- [Minimise to tray functionality is weak](https://github.com/signalapp/Signal-Desktop/issues/3877)
												  collapsed:: true
													- `signal-desktop --start-in-tray`
													- `--use-tray-icon`
												- GIF search on desktop
												- Rich text formatting
										- MobileCoin integration
										  collapsed:: true
											- There are 250 million units of mobilecoin, and majority of them are owned by the founders. Only 37.5 million have been distributed. With current price ($65), they're worth $14B already. This makes the project a scam and impossible for it to work as a reliable money that holds value. Bitcoin had no pre-mine and has been fairly distributed from the start.
										- ### Minor limitations
											- No onion routing
											  collapsed:: true
												- Sealed Sender should mean the service is unable to track who messaged who
												- A global level adversary can
											- Isn't federated - thus they can track metadata via their centralised servers
											  collapsed:: true
												- Can't be federated - you have to use the centralised server model (also Signal is trademarked)
												- 2) Metadata tracked by a central entity i.e. who knows who, who speaks to who, how often etc. When the FBI subpoenaed them they released documents showing they didn't track user data but it could very easily be a red herring.
												- 1) Requires a phone number - which is a strong identifier
												- 2) Isn't federated thus they can track metadata via their centralised servers i.e. who knows who, who speaks to who, how often etc.
												- When the FBI subpoenaed them they released documents showing they didn't track user data but it could very easily be a red herring.
											- Some metadata leaks
											  collapsed:: true
												- Summary
												  collapsed:: true
												  https://medium.com/@thegrugq/signal-intelligence-free-for-all-5993c2f72f90#.7dc5sv9bk
													- Current metadata leaks
													  collapsed:: true
														- Your ISP knows you sent and/or received data from the Signal server. They know when and they know how much.
														- [Google](https://developers.google.com/cloud-messaging/) (and/or <a href="https://developer.apple.com/library/ios/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/Chapters/ApplePushService.html">Apple</a>) know that the Signal app on a specific device received a notification, and at what time.
														- Open Whisper Systems know which device is registered to which phone number.
														- Open Whisper Systems may be able to track which device sent and received messages via traffic correlation via timing attacks and IP address connections
													- Old metadata leaks
													  collapsed:: true
														- Open Whisper Systems doesn't know who sends messags to each other
														  This is prevented by Sealed Sender
												- _Metadata Signal still have:_
												  collapsed:: true
													- _Very minor threat_
													  collapsed:: true
														- IP address
														  However Sealed Sender + Encrypted Profile means Signal has no clue who I am or are chatting to
														- All dates and times of connection to Signal
														  At most they can tell I use Signal, but not what for or anything about me personally
														- A history of all the truncated cryptographically hashed phone numbers for contact discovery
												- _Metadata that other parties still have:_
												  collapsed:: true
													- Phone number (only contacts that I contact will have it)
											- Incompatible with Titanium Backup - have to use the native Signal backup
											  collapsed:: true
												- It uses Android hardware-based “KeyStore”
												  https://whispersystems.discoursehosting.net/t/please-provide-option-to-not-store-crypto-keys-in-hardware-it-breaks-fullbackups/4962
											- [Uses Google reCAPTCHA](https://community.signalusers.org/t/use-something-else-instead-of-google-recaptcha-for-registration/6289/25)
											- [Uses Google Maps instead of OpenStreetMap](https://community.signalusers.org/t/use-openstreetmap-instead-of-google-maps/5434/25) (unlike Molly)
									- ## Unclear
										- Link previews are not proxied, but can be turned off
										- Presence is limited (ie no online status, yes typing indicators and read receipts)
										  collapsed:: true
											- No online/offline status, nor last seen
											  [https://community.signalusers.org/t/ability-to-see-if-people-are-online/5218](https://community.signalusers.org/t/ability-to-see-if-people-are-online/5218)
											- Yes typing indicators and read receipts
										- Dependent on Google Cloud Messaging unless you use the WebSockets version
										  collapsed:: true
											- Dependent on Google Cloud Messaging if you are using vanilla Android, which is metadata
											- Uses GCM/FCM for notifications, though will use WebSockets if GMS not installed
											- Standalone APK download version has built-in updater
												- Only direct APK download or Google Play Store
												- Standalone APK
													- Yes, the standalone APK downloads updates automatically and prompts you to install once the download is complete.
														- It checks for a new version every 6 hours
												- Why no F-Droid build
												  source:: https://community.signalusers.org/t/signal-f-droid-repository/2808/21
											- Only for wakeup event, not delivery
											  https://whispersystems.org/blog/goodbye-encrypted-sms/
											- http://support.whispersystems.org/hc/en-us/articles/215843598-Why-GCM-Does-Google-see-my-messages-
											- Support question
												- Can you detail specifically which parts of the GCM architecture that you use for this 'wakeup event'?
												- https://en.m.wikipedia.org/wiki/Google_Cloud_Messaging#/media/File%3AGCM_Architecture.svg
												- Because it looks like all of it provides metadata of some sort.
											- Reply
												- You can check out the source code here: https://github.com/WhisperSystems/.
												- In order to route messages and calls it is necessary to know some information. However, external entities would not have access to any metadata at all unless the Signal servers were compromised. Even in this scenario, message and call contents would remain protected. Not having to trust an external server is a hallmark of end-to-end encryption, and it’s something that we take extremely seriously.
												- We also do our best to avoid metadata that isn’t absolutely necessary for message and call routing. When you initiate a Private Group Chat, for example, the server does not have access to any group metadata whatsoever, including the name of the group, its members, or its avatar.
												- Neither Google nor Apple has access to metadata about who you are communicating with nor can they read your messages.
										- New Signal secure cloud storage for [secure value recovery](https://signal.org/blog/secure-value-recovery)
										  collapsed:: true
											- RAM-based secure enclave (using Intel SGX) for cryptographically ensuring brute force attempts aren't made to guess your key
											- stateless frontend enclaves that are designed to be disposable for client handshake
											- traffic director that consists of a frontend enclave that simply forwards requests to backend Raft groups and re-forwards them when the group topology changes (new server or replace old ones)
											- Raft like Blockchain has distributed consensus
											- https://github.com/signalapp/SecureValueRecovery
								- No changelog for Android
								  [https://github.com/signalapp/Signal-Android/issues/9543](https://github.com/signalapp/Signal-Android/issues/9543)
								- _Installing on Linux_
									- or package
										- 1. Install our official public software signing key
										  wget -O- [https://updates.signal.org/desktop/apt/keys.asc](https://updates.signal.org/desktop/apt/keys.asc) |\
										  sudo apt-key add -
										- 2. Add our repository to your list of repositories
										  echo "deb [arch=amd64] [https://updates.signal.org/desktop/apt](https://updates.signal.org/desktop/apt) xenial main" |\
										  sudo tee -a /etc/apt/sources.list.d/signal-xenial.list
										- 3. Update your package database and install signal
										  sudo apt update && sudo apt install signal-desktop
									- Snap
									  collapsed:: true
										- `snap install signal-desktop`
										- [https://snapcraft.io/signal-desktop](https://snapcraft.io/signal-desktop)
									- Flathub (unofficial)
								- _{Archive}_
								  collapsed:: true
									- Now has typing indicators, profile pictures and read receipts (usability)
								- Related: Criptext (email which uses Signal Protocol rather than PGP)
							- [Wire](https://wire.com/en)
							  collapsed:: true
								- Wire for Teams (mostly FOSS, server in 2018)
									- Pros
									  collapsed:: true
										- End-to-end encryption default
											- Conversation content is encrypted with strong encryption on the sender’s device and only decrypted on the recipient’s device.
										- Encrypted audio, video, file transfer, group chats, group calls
										- Multi-device with history
										- Rich feature set e.g. handwriting, gif support
										- Like, video/audio messages,
										- Screen sharing on desktop client
										- Delete messages for myself only/or for everyone
										- Centralised servers in Switzerland means lowered risk of law enforcement obtaining data
									- Cons
									  collapsed:: true
										- Like Riot (as of Sep 2017) conversation history isn't visible on new devices
										- Server code isn't open-source, only clients
										  collapsed:: true
											- the server is not open-source, so if the company goes under, that's it;
										- No delivery notifications
										- Centralised metadata means company can sell or use identifying data
										- Takes contacts lists info
										  collapsed:: true
											- 2.2 Address book contacts. By uploading your address book contacts, Wire will convert your contact phone numbers and email addresses into irreversible hashed values. Wire does not collect the names in your address book, or any other information that could identify the contact, such as notes and birthdays. You can always opt out from sharing your address book, and we will no longer upload your contact data from your mobile or desktop native client. When you use the Web App client, contacts from your address book will only be uploaded when you decide to do so manually.
									- handwriting
									  collapsed:: true
										- Sketch on photos
										  https://medium.com/colorful-conversations/sketch-on-photo-ba531756ab6c#.8eaet15iw
									- Voice and video messages
									- Filters/lenses
									  collapsed:: true
										- Voice filters
										  https://medium.com/colorful-conversations/the-tune-for-this-summer-audio-filters-eca8cb0b4c57?source=latest
										- Picture - filters
										- Lenses
											- https://support.snapchat.com/en-US/a/lenses1
											- http://www.pcadvisor.co.uk/how-to/mobile-phone/how-use-new-snapchat-features-lenses-filters-trophies-replays-face-swap-chat-2-emoji-video-3515801/
									- Wire for Teams
									  https://wire.com/en/teams/
									- Is there a typing indicator?
									- New features
									  collapsed:: true
									  https://medium.com/colorful-conversations
										- https://medium.com/@wireapp
								- Pros
									- Good UX
									- E2EE voice and video conferencing
								- Cons
									- [https://github.com/privacytools/privacytools.io/pull/1489](https://github.com/privacytools/privacytools.io/pull/1489)
							- [Threema](https://threema.ch/)
							  collapsed:: true
								- clear business model (one time fee + enterprise)
								- proprietary server
								- code over wall open-source client (ie. no real commits, just dumps)
								- they rolled their own crypto library, Ibex, (again)
								- weird handling/response of the issues regarding their previous crypto library
								- FOSS apps
						- ## Federated
							- [Element](https://element.io) 
							  id:: 631fa97e-a0a9-406c-b7b9-20536d421090
							  collapsed:: true
							  AKA Riot previously | (built on Matrix)
								- Pros/Cons
									- Pros
										- Decent UX - similar UI to Discord
										- E2E-encryption
										  collapsed:: true
											- Overview
												- • End-to-end encryption using Olm (https://matrix.org/git/olm)
												- https://matrix.org/jira/browse/SPEC-162
												- Good security model vs clients that don't support E2E
													- They only see "Encrypted message" when receiving messages
													- They can send unencrypted messages. Padlock icon indicates they are sending unencrypted messages
												- Protocol
													- The E2E uses two different ratchets:
													- Olm (our implementation of the double ratchet) for 1:1 communication: https://matrix.org/docs/spec/olm.html
													- Megolm, a new ratchet expressly for handling Matrix group chats with history which can be (optionally) replayed. The novelty here is that you can select how often the ratchet is replaced, thus configuring the secrecy of the history (at one extreme, you never replace the ratchet and the room essentially has the same key throughout its existence. at the other extreme, you replace the key for every message, giving you perfect forward secrecy). https://matrix.org/docs/spec/megolm.html.
														- the ability for a user to join a group chat from a new device and (optionally) have the ability to sync in old history for the room, assuming the room's config allows it.
												- E2E announcement
												  https://matrix.org/blog/2016/11/21/matrixs-olm-end-to-end-encryption-security-assessment-released-and-implemented-cross-platform-on-riot-at-last/
										- Can bridge with other chat services e.g. Slack, IRC, XMPP etc
										  collapsed:: true
										  https://pbs.twimg.com/media/C61eEt5WcAArPk3.jpg:large
											- [https://matrix.org/docs/projects/try-matrix-now.html#application-services](https://matrix.org/docs/projects/try-matrix-now.html#application-services)
											- Bridges they desire
											  https://github.com/matrix-org/GSoC/blob/master/IDEAS.md#bridge-all-the-things
											- [https://matrix.org/bridges/](https://matrix.org/bridges/)
												- Portal rooms: these control chunks of room aliases namespace. For example, #freenode_#channelname:[matrix.org](http://matrix.org) corresponds to #channelname on Freenode. In this way, Matrix users can transparently join IRC channels on Freenode. Portal rooms are typically managed by the remote network's side of the room.
												- Plumbed rooms: these rooms are "plumbed" into one or more specific remote rooms by configuring a bridge (which can be run by anyone). For instance, #matrix:matrix.org is plumbed into #matrix on Freenode, matrixdotorg/#matrix on Slack, etc. Access control for Matrix users is necessarily managed by the Matrix side of the room. This is useful for using Matrix to link together different communities.
												- Bridgebot-style: in this case, messages in either direction are conveyed by a bot residing on the given platform. This is a sub-optimal experience because metadata is lost. For example, all messages might be sent by the same bot, but with the message text prefixed with the name of the original sender.
												- Puppeting: solves the problems of Bot-based bridging by "puppeting", meaning controlling, a user on the other side of the bridge. This means that to native users, they see messages as being sent from the correct sender. Double-puppeting means this is done in both directions of the bridge. This is the most preferred way of implementing a Matrix bridge.
										- Plans for integrations (bots) with many other services
										  collapsed:: true
											- Current
												- Bridges
													- IRC
													- Slack bridge only available in public rooms?
														- Anyone who knows the room's link, including guests
													- Gitter
													- XMPP
												- Bots
													- Github
													- GIphy
													- Guggy
													- ((644c0b2c-971e-4f9b-aca2-3ccc41397f16))
													- Twitter
												- Bridge for OpenMarket (SMS)
											- Future
											  intralink2:: https://workflowy.com/#/3f989a240fb2
										- Many useful features
										  collapsed:: true
											- Encrypted voice, video and conference calls
											- Powerful search
											- Permalinked posts
										- Several privacy features
										  collapsed:: true
											- ((663b24fb-4437-4115-83da-5f5b668989fc)) (different from Signal)
											  [https://github.com/vector-im/element-web/issues/7649](https://github.com/vector-im/element-web/issues/7649)
										- Multi-platform
										- Multiple clients
										  collapsed:: true
											- _Web_
												- Hydrogen -  verylightweight, good offline support, minimal featureset
													- [https://github.com/vector-im/hydrogen-web](https://github.com/vector-im/hydrogen-web)
													-
											- _Desktop_
												- Nheko - native desktop app, Telegram Desktop-like UI
												  [https://matrix.org/docs/projects/images/nheko.png](https://matrix.org/docs/projects/images/nheko.png)
													- [https://flathub.org/apps/details/io.github.NhekoReborn.Nheko](https://flathub.org/apps/details/io.github.NhekoReborn.Nheko)
													- [https://github.com/Nheko-Reborn/nheko](https://github.com/Nheko-Reborn/nheko)
												- Weechat - lightweight CLI client
													- [https://matrix.org/docs/projects/client/weechat-matrix](https://matrix.org/docs/projects/client/weechat-matrix)
													- [https://github.com/poljar/weechat-matrix-rs](https://github.com/poljar/weechat-matrix-rs)
													-
												- Fractal - Rust-based
													- [https://github.com/danigm/fractal](https://github.com/danigm/fractal)
													- [https://matrix.org/docs/projects/client/fractal/](https://matrix.org/docs/projects/client/fractal/)
										- Supports [UnifiedPush](https://github.com/vector-im/element-android/blob/develop/docs/unifiedpush.md)
										  id:: 631fa97e-451a-4fdf-b05b-5184648fcc81
											- Related: ((63203365-6a6f-4016-b5ac-e5f22a0e6df0))
										- Uses [LiveKit](https://livekit.io/) for 100+ participants in audio or video conference calls
										  FOSS Twilio Video / Agora alternative
									- _Status_
										- [2023 Ignition update](https://element.io/blog/element-x-ignition/) - announcing status of OIDC (OpenID Connect for auth), [Sliding Sync API](https://github.com/matrix-org/sliding-sync) for much faster start-up and sync, Element Call built on [LiveKit](https://livekit.io/) for Matrix-native voice and video conferencing, high-performance [Rust SDK](https://github.com/matrix-org/matrix-rust-sdk) for most of backend (replaces Kotlin and Swift implementations for cross-platform mobile), Rich Text Editor for message formatting, location sharing and polls20
										  collapsed:: true
											- To-do:
												- OIDC support for existing servers (e.g. matrix.org)
												- Encrypted backup support, so you can actually read your old end-to-end encrypted messages(!)
												- A new roomlist experience with better sorting, badges (including unread state) and filters.
												- A new chat timeline experience where it’s easier to catch-up with unread messages.
												- Full Encryption UI/UX (handling untrusted users/devices)
												- Fully integrated VoIP and tight OS integration
												- Voice Messages
												- Typing notifications
												- Read receipts
												- Figuring out if and how to incorporate threads, spaces and widgets.
											- [Element web/desktop is receiving the Element X updates, but will not have a rewrite from scratch](https://github.com/vector-im/element-meta/issues/1915#issuecomment-1754801103)
										- 2023 - [implementing MLS](https://arewemlsyet.com/) for E2EE, likely replacing Olm/MegaOlm
									- Cons
										- Currently the Element X Android app is [missing some features before it'll replace the original Element app](https://github.com/element-hq/element-meta/issues/1915#issue-1811457462)
											- [[2024-11-13 Wednesday]] Notably missing threads, spaces, multi-account, stickers, invisible crypto, audio-only calls, integrations, presence
										- I would miss this from Signal
											- Better GIF support
											- ((650aae18-be6c-424d-b577-a4bab37ed7f9))
										- _Lacks_
											- ## Usability
												- [GIF keyboard](https://github.com/element-hq/element-meta/issues/321#issuecomment-2228461278)
												- [Giphy bot doesn't work in E2EE rooms](https://github.com/element-hq/element-web/issues/7854#issuecomment-476256064)
												- [Custom emoji](https://github.com/element-hq/element-meta/issues/339#issuecomment-2057545661)
												- [Custom sticker packs](https://github.com/matrix-org/matrix-spec-proposals/pull/2545#commits-pushed-c429552)
												  id:: 650aae18-be6c-424d-b577-a4bab37ed7f9
												- [GUI for per-room avatar and nickname](https://github.com/element-hq/element-meta/issues/499#ref-issue-2372677266)
												  collapsed:: true
													- Aliases - different nicknames for each room
													- Possible through command box only
													- /myroomavatar
													- /myroomnick
													- You need to use an mxc:// URL. You can get one by uploading that image in some room then clicking "View Source" on the image message. Then under content->file->url there should be an mxc://... URL. Copy and use that as the value for avatar_url.
													- f you omit the mxc url it gives you a file upload dialog.
												- _Organisation enhancement_
													- Export messages
													- [Starring messages](https://github.com/element-hq/element-meta/issues/319#event-8506151392)
													- [Improve Visibility of Active Threads · Issue #2417 · element-hq/element-meta · GitHub](https://github.com/element-hq/element-meta/issues/2417#issuecomment-2397044524)
												- _Android Usability_
													- [Multiple-account support](https://github.com/element-hq/element-android/issues/26#issuecomment-2212592181)
											- ## Privacy enhancements
												- Poor metadata privacy compared to Signal
												  collapsed:: true
													- The Matrix protocol itself [theoretically supports forward secrecy](https://gitlab.matrix.org/matrix-org/olm/blob/master/docs/megolm.md#partial-forward-secrecy)[1](https://www.privacyguides.org/en/real-time-communication/?h=messe#fn:1), however this is [not currently supported in Element](https://github.com/vector-im/element-web/issues/7101) due to it breaking some aspects of the user experience such as key backups and shared message history.
													- https://anarc.at/blog/2022-06-17-matrix-notes/#metadata-handling
													- ((6312a076-eb26-4bd5-a669-ea0a50d06668)) features
														- _Privacy_
															- [Sender-side URL previews (rather than server-side)](https://github.com/element-hq/element-meta/issues/1139#event-8729228224)
															- [Encrypted Profiles (profile name, picture etc)](https://github.com/element-hq/element-meta/issues/1838#event-9773609737)
																- [WIP profiles basically as a JSON-like room with various fields](https://github.com/matrix-org/matrix-spec-proposals/issues/3795#issuecomment-2371052882)
																- https://github.com/matrix-org/matrix-spec-proposals/pull/4133#event-14689902473
															- [Sealed Sender (pre-req: Encrypted Profiles)](https://github.com/matrix-org/matrix-spec/issues/549#issuecomment-1067971447)
												- _Tor support_
												  collapsed:: true
													- 1) Tor hidden service for main Riot instance
													  https://github.com/vector-im/riot-web/issues/6463
													- 2) These Tor instances should federate via Tor hidden services
														- Ability to run homeservers as .onion hidden services and federate entirely within the Tor network
													- 3) Anonymous P2P functionality (like Pond/Ricochet)
													  collapsed:: true
														- _Pros/Cons_
															- Pros
																- 3rd party server has no metadata or users
																- Pond-style Tor connections are planned for Matrix
																	- Original spec PDF
																	  https://matrix.org/~matthew/2015-06-26%20Matrix%20Jardin%20Entropique.pdf
																		- P2P
																			- This requires a mobile, desktop or web app homeserver which can connect to a client on the same device
																		- Pond/Ricochet extension
																			- Supports bridging to other networks via existing Matrix AS API or classic Matrix Federation – at expense of privacy. Mitigated by disabling bridging/federation per-room.
																	- P2P Matrix, and eventually Ricochet/Pond-like protocol
																	  https://matrix.org/jira/plugins/servlet/mobile#issue/SPEC-455
																		- Likely available as desktop client, or web client max. Less likely for mobile
															- Cons
																- Uses more battery and data as it has to maintain a keep-alive connection to receive messages
																	- Current P2P messengers like Ring and Tox have usability as well as battery and data usage issues because they need a constantly open connection to receive messages.
																		- An alternative would be to use a decentralised, trusted service for store-and-send functionality to queue messages for offline users. This is a perfect usecase for a blockchain - since users are already incentivised to want to queue messages for offline users
																- Needs some model of holding messages until recipient is online again
														- P2P
														  collapsed:: true
															- Package homeserver and client together
																- Regarding peer-to-peer Matrix: isn't packaging Riot desktop+Synapse together sufficient to make it P2P?
																	- only if you have a static IP and open ports to the internet, unfortunately
																	- nodes actually need to be able to directly talk to each other, and they assume that all nodes are up at least most of the time.
															- _Essential_
																- Needs decentralised store-and-send functionality (for when client is offline) e.g. a blockchain
																	- where nodes have some sort of incentive to be involved in it.
																	- Research how Ring + Tox have managed it
															- Ability to communicate with another homeserver (necessary for chatting with non P2P users, and for integrations and bridges also)
														- https://github.com/matrix-org/GSoC/blob/master/IDEAS.md
												- [Encrypted database on Android](https://github.com/vector-im/riot-android/issues/746)
												- [Self-destructing/disappearing messages](https://github.com/vector-im/riot-web/issues/2497#issuecomment-450559855)
												- _Low priority_
													- [E2E encryption for bots/integrations API (like Wire)](https://github.com/matrix-org/matrix-spec/issues/1109#issuecomment-1152831846)
													- Can't use config to choose a FOSS integrations manager
													  collapsed:: true
														- Scalar (one-click integration hosting) isn't open-source
															- Tool which sets up integrations in one-click from front end
														- [Widgets, the spec by turt2live · Pull Request #2764 · matrix-org/matrix-spec-proposals · GitHub](https://github.com/matrix-org/matrix-spec-proposals/pull/2764)
														- https://github.com/element-hq/element-meta/issues/792
														- https://github.com/matrix-org/matrix-spec-proposals/pull/1956#ref-issue-1155748099
														- [Formally spec an API for interacting with integration managers · Issue #296 · matrix-org/matrix-spec · GitHub](https://github.com/matrix-org/matrix-spec/issues/296#issuecomment-1531331263)
														-
													- End-to-end encryption could be improved
													  collapsed:: true
														- Unable to decrypt messages bug - "Unable to decrypt: The sender's device has not sent us the keys for this message." (The UISI bug)
														  https://github.com/vector-im/riot-web/issues/2996
														- E2E device/key management UI improvements
														  https://github.com/vector-im/riot-web/issues/4522
														- We do not encrypt messages proactively for invited users who have yet to join.
														  https://github.com/vector-im/riot-web/issues/3821
													- ((670bdaca-259b-4639-8ad8-cf380b048772)) /2 step authentication
													  collapsed:: true
														- Two-Step Verification (from Telegram blog notes)
															- Another addition to the Privacy and Security section is Two Step Verification. It allows you to set up a password that will be required every time you log into your account from a new device – in addition to the code you get in the SMS.
															- Be careful though: if you forget this password, you won't be able to access your messages from other devices. We recommend setting up a recovery e-mail or at least a hint for your password, if you decide to turn on Two Step Verification.
													- Use an alternative to Google's reCaptcha
													  collapsed:: true
														- https://github.com/librecaptcha/lc-core
													- P2P matrix
													  [https://matrix.org/blog/2020/06/02/introducing-p-2-p-matrix](https://matrix.org/blog/2020/06/02/introducing-p-2-p-matrix)
												- GSoC ideas
												  source:: [https://github.com/matrix-org/GSoC/blob/master/IDEAS.md#extending-native-matrix-desktop-clients](https://github.com/matrix-org/GSoC/blob/master/IDEAS.md#extending-native-matrix-desktop-clients)
												  collapsed:: true
													- Peer-to-peer Matrix
													  collapsed:: true
														- Matrix currently follows a client-server architecture, where the servers federate together. This means that to host your own conversations in Matrix you have to own and maintain a server with a static IP and DNS SRV record etc. This isolates many people from running their own Matrix nodes. An interesting experiment would be to write a homeserver variant (probably in Node.js) which advertises itself via a DHT or similar (e.g. using js-libp2p) and uses WebRTC data channels for p2p synchronisation of message graph data. This could make it much easier to run homeservers - either as a standalone node daemon, or built into a desktop or even web client. Such a server would implement the basic features of today's Matrix C-S API, but obviously break compatibility with today's Matrix S-S API. An extension might be to write a bridge between the two federation protocols.
														- Expected Results: A proof-of-concept P2P Matrix homeserver in Node
														- Difficulty: Hard
														- Knowledge pre-req: P2P tech, JavaScript
														- Potential mentor: Matthew Hodgson (github)
													- Decentralised accounts
													  collapsed:: true
														- Currently Matrix accounts are stored on a single homeserver. This is far from decentralised and produces an unfortunate single point of failure and control for the user. It would be fantastic to evolve Matrix to support replicating account data across multiple servers, and let clients pick which home server they talk to. There is significant overlap in solving this with the 'Peer-to-peer Matrix' proposal.
														- Expected Results: Extend the matrix spec and homeserver to support decoupling accounts from DNS, and allowing multiple trusted servers to host the data.
														- Difficulty: Hard
														- Potential mentor: Matthew Hodgson (github), Erik Johnston (github)
													- Decentralised identity
													  collapsed:: true
														- Currently the mapping of 3rd party IDs (e.g. email addresses) through to Matrix IDs is performed by a logically centralised ID server. This project would create a decentralised datastore of ID mappings - e.g. using DataEntry objects in a stellar-core ledger, or some other distributed secure data structure, with trusted identity providers entering verified ID mappings into the store.
														- Expected Results: Replace the current sydent ID server implementation with a decentralised equivalent.
														- Difficulty: Hard
														- Knowledge pre-req: Secure distributed data-structures, Security, Cryptography
														- Potential mentor: Matthew Hodgson (github), Erik Johnston (github)
													- Decentralised reputation
													  collapsed:: true
														- Mitigating abuse is an ongoing area of research in Matrix. Tracking realtime reputation data for Matrix endpoints, such that users can report abuse and filter their communication to hide abusive content is the holy grail. There are some very early thoughts on this here. Anyone interested in researching the holy grail of abuse mitigation is welcome to experiment here!
														- Expected Results: Add upvote/downvote functionality to Matrix spec, gather the data in a secure decentralised datastructure that can be mined for cluster analysis, and publish reputation data that Matrix clients can align themselves with when filtering abusive content.
														- Difficulty: Hard
														- Knowledge pre-req: Distributed data-structures; Graph databases; Data analytics
														- Potential mentor: Matthew Hodgson (github)
													- Decentralised Search
													  collapsed:: true
														- Matrix provides a basic full-text search API and implementation in Synapse. Would be great to build a cross-Matrix search engine however, especially a decentralised one.
														- Expected results: A Matrix spider that consumes public event data from Matrix and indexes into a decentralised secure datastructure that can then be queried for rapid cross-Matrix search results.
														- Difficulty: Moderate/Hard
														- Knowledge pre-req: Familiarity with web services, the language used for implementing the application service (e.g. Python if using our reference example service framework). Basic HTML/CSS/Javascript needed to implement the search engine interface frontend.
														- Potential mentor: Matthew Hodgson (github)
												- Many metadata leaks currently
												  collapsed:: true
													- 1
														- Many leaks
														  source:: [https://serpentsec.1337.cx/matrix](https://serpentsec.1337.cx/matrix)
															- Unencrypted data
															  collapsed:: true
																- Message senders
																	- Message senders are never encrypted
																- Session/device IDs
																	- Due to Matrix's design, encrypting this would break verification
																- Message timestamps
																	- It's impossible to prevent timestamps from leaking, since the server can simply note when an event is received anyway
																- Room members (join/leave/invite events)
																	- Join/leave/invite and other room events are never encrypted
																- Message edit events
																	- While contents are not leaked, an attacker can know when messages are edited
																- Message reactions
																	- Reactions are never encrypted
																- Read receipts
																	- Read receipts are never encrypted
																- Nicknames
																	- Nicknames are never encrypted
																- Profile pictures
																	- Profile pictures are never encrypted
															- Who can view metadata?
															  collapsed:: true
																- The following metadata can be seen by any homeserver with at least 1 member in an E2EE room:
																- Message senders
																- Session/device IDs
																- Message timestamps
																- Room members (join/leave/invite events)
																- Message edit events
																	- Note: Though edit events are leaked, message contents are not.
																- Message reactions
																- Read receipts
																- Room-specific nicknames
																- Room-specific profile pictures
															- The following information is publicly available:
															  collapsed:: true
																- Global nicknames
																	- Matrix allows setting room-specific nicknames, which are less visible to attackers
																- Profile pictures
																	- Matrix allows setting room-specific profile pictures, which are less visible to attackers
															-
													- 2
													  [https://www.hackea.org/notas/matrix.html#facing-the-real-and-clear-facts](https://www.hackea.org/notas/matrix.html#facing-the-real-and-clear-facts)
														- The Matrix ID of users, usually including their username.
															- Email addresses, phone numbers of the user and their contacts.
															- Associations of Email, phone numbers with Matrix IDs.
															- Usage patterns of the user.
															- IP address of the user, which can give more or less precise geographical location information.
															- The user’s devices and system information.
															- The other servers that users talks to.
															- Room IDs, potentially identifying the Direct chat ones and the other user/server.
													- 3
													  [https://gitlab.com/libremonde-org/papers/research/privacy-matrix.org/-/blob/master/part1/README.md](https://gitlab.com/libremonde-org/papers/research/privacy-matrix.org/-/blob/master/part1/README.md)
														-
											- Other functionality
												- [Discord Activities equivalent](https://github.com/vector-im/element-meta/discussions/775)
												- Mattermost ideas
												  collapsed:: true
													- Custom notification triggers
														- Set notifications on mentions of your name, username, keywords, replies on threaded messages, and group mentions like @channel.
														- https://about.mattermost.com/mattermost-3-4/
														- Per-user notifications (e.g. notify when particular users speak)
														- Per-keyword notifications (e.g. notify for "coffee")
														- Per-room notifications (i.e. mute/unmute conversations)
													- Widescreen the right-panel
														- https://www.mattermost.org/wp-content/uploads/2015/10/widescreen_search.gif
													- Auto-highlight messages you send
														- http://www.mattermost.org/wp-content/uploads/2015/06/20150702_auto-highlight1.png
												- Integrations
												  collapsed:: true
													- Uses Scalar
													  collapsed:: true
														- https://medium.com/@RiotChat/new-irc-integrations-oftc-and-snoonet-b88883a58303#.thvzoh83n
													- Current integrations
													  intralink2:: https://workflowy.com/#/38205f5b0e70
													- [E2E encryption for bots/](https://workflowy.com/#/9e5274d35873)<a href="https://workflowy.com/#/9e5274d35873">integratio</a><a href="https://workflowy.com/#/9e5274d35873">ns API (like Wire)</a>
													- [Can't use config to choose a FOSS ](https://workflowy.com/#/c666092ec3a9)<a href="https://workflowy.com/#/c666092ec3a9">integratio</a><a href="https://workflowy.com/#/c666092ec3a9">ns manager</a>
													- Bridges
													- Bots
													- Webhooks
													  collapsed:: true
														- Mattermost
															- Slack-compatible webhooks make it easy to adapt Slack apps to Mattermost
															- Open Source integrations service give you complete control over formatting and delivery
															- Post real-time messages into Mattermost using the same webhook call you’d use to post messages into Slack.
													- Emails
													- Ideas
													  collapsed:: true
													  https://github.com/matrix-org/GSoC/blob/master/IDEAS.md#integrations-to-all-the-things
														- Bridges
															- ((663b24fb-f1f2-4dbe-ae47-d3a910654835))
															- LINE
															- Skype
															- VoIP systems
																- FaceTime
																- PSTN
															- Email systems
																- IMAP
																- SMTP
															- Messageboard systems
																- NNTP
																- VBulletin
																- phpBB
																- Simple Machines Forum
																- Discourse
															- Blog systems
																- Medium
																- Tumblr
																- Wordpress
																- RSS
																- Twitter
																- Known
															- Social networks
																- Facebook (timeline?)
																- G+ Discussions
																- Buddycloud
																- pump.io
														- Bots
															- IFTTT
															- Zapier
															- Google Image search
															- Wordpress Bot
															- Reddit Bot
															- phpBB bot
															- Discourse bot
													- Like Slack integrations
													  https://slack.com/apps
												- Restrict what homeservers can connect
												  collapsed:: true
													- Reduce metadata breach
													- Unrelated but another question: will Vector have functionality to restrict what home servers are used to connect to a room? Eg you invite someone via their 3PID and it says they can't enter the room with their current home server.
													- Would be useful for reducing metadata, because all it takes is an adversary managing to gain access to a room once eg via intercepting an email to then get the metadata for all participants.
												- OpenMarket SMS integration (like Matrix normal server)
												  collapsed:: true
													- @+441937318031:matrix.openmarket.com
												- ((632093be-af60-4fb6-835e-af5b24547eac)) integration
												  collapsed:: true
													- https://github.com/ipfs/notes/issues/42
													- https://github.com/matrix-org/GSoC/blob/master/IDEAS.md
											- Use in non-chat formats
											  collapsed:: true
												- Microblogging (twitter-like)
													- https://github.com/matrix-org/GSoC/blob/master/IDEAS.md#matrix-powered-microblogging
													- https://github.com/tjgillies/freebird
												- Live blogging
												- Blogging
													- https://github.com/lukebarnard1/j/blob/master/README.md
												- Comments
													- https://github.com/pik/Interlocutor/blob/master/README.md
												- HTML Embeddable Matrix  Rooms
												  Eg live blogging, comments alternative
													- Matrix Live
													  https://live.hello-matrix.net/
														- As of Nov 16 is
															- Read only
															- Can't sign in with own Matrix ID
															- No WordPress plugin
															- Sorted by recent like a chatroom. No option to sort by likes
															- No support for threaded messaging
											- More ideas for extension
											  collapsed:: true
												- See competitors for other ideas
													- Wire
													  intralink2:: https://workflowy.com/#/fcf3a03ff420
													- Slack
													  intralink2:: https://workflowy.com/#/3c18a8c16bd0
													- Mattermost
													  intralink2:: https://workflowy.com/#/81985dad9daf
													- Comparison
													  https://docs.google.com/spreadsheets/d/1tv5QTuoS29YwApP7i2OKe9aLrZZIwgY-f5b-d73vlI0/edit?pref=2&pli=1#gid=0
												- https://github.com/matrix-org/GSoC/blob/master/IDEAS.md
									-
								- Meta
									- Links
										- [GitHub - vector-im/element-web: A glossy Matrix collaboration client for the web.](https://github.com/vector-im/element-web)
										- [Paid hosting](https://modular.im)
										- [Blog](https://element.io/blog/)
								- Built for Matrix homeservers
								  collapsed:: true
									- https://matrix.org/
									- Homeserver = communication history and account information
									  collapsed:: true
									  http://i.imgur.com/WNmoIIY.png
										- What is a home server?
											- A user’s clients connect to a single homeserver, which stores the communication history and account information for that user
										- Where do my conversations get stored?
											- They share data with the wider Matrix ecosystem by synchronising communication history with other homeservers and their clients. Clients typically communicate with each other by emitting events in the context of a virtual room. Room data is replicated across all of the homeservers whose users are participating in a given room.
											- Distributed Group Chat
												- Fully distributed persistent chatrooms with no single points of control or failure
											- Everything in Matrix happens in a room. Rooms are distributed and do not exist on any single server. Rooms can be located using convenience aliases like  matrix:matrix.org or  test:localhost:8448.
									- Identity servers map 3PIDs to MXIDs
									  collapsed:: true
										- What is an identity server?
											- Users in Matrix are identified internally via their matrix user ID (MXID). However, existing 3rd party ID (3PID) namespaces such as email addresses or phone numbers should be used publically to identify Matrix users, at least for invitation purposes. A Matrix “Identity” describes both the user ID and any other existing IDs from third party namespaces linked to their account.
											- Matrix users can link third-party IDs (3PIDs) to their user ID. Linking 3PIDs creates a mapping from a 3PID to a user ID. This mapping can then be used by Matrix users in order to discover the MXIDs of their contacts.
											- In order to ensure that the mapping from 3PID to user ID is genuine, a globally federated cluster of trusted “Identity Servers” (IS) are used to verify the 3PID and persist and replicate the mappings. Usage of an IS is not required in order for a client application to be part of the Matrix ecosystem. However, without one clients will not be able to look up user IDs using 3PIDs.
											- The precise architecture of identity servers is currently in flux and subject to change as we work to fully decentralise them.
										- What is a 3PID?
											- Third-party IDs (3PIDs) are IDs from other systems or contexts, such as email addresses, social network accounts and phone numbers.
											- Use existing 3rd party IDs (e.g. email, phone numbers, Facebook) to authenticate, identify and discover users
										- Can I run my own identity server?
											- Yes - the reference implementation is sydent and you can run your own ID server cluster that tracks 3rd party to Matrix ID mappings. This won’t be very useful right now, though, and we don’t recommend it.
											- If you want your server to participate in the global replicated Matrix ID service then please get in touch with us. Meanwhile, we are looking at ways of decentralising the ‘official’ Matrix identity service so that identity servers are 100% decentralised and can openly federate with each other. N.B. that you can use Matrix without ever using the identity service - it exists only to map 3rd party IDs (e.g. email addresses) to matrix IDs to aid user discovery.
											- https://github.com/matrix-org/sydent
										- Matrix user IDs look like @matthew:matrix.org (although in the future you will normally refer to yourself and others using a third party identifier (3PID): email address, phone number, etc rather than manipulating Matrix user IDs)
								- Documentation
									- Setup
									  id:: 6320335e-00d8-465d-bc7e-70e08bc9a106
									  collapsed:: true
										- Settings > Notifications > ((632033c8-db1d-405f-a57a-6cd4d66cee57))
										  id:: 63203365-6a6f-4016-b5ac-e5f22a0e6df0
											- This enables battery efficient notifications (unlike background polling) but it doesn't require using ((663915c8-abda-4f12-8175-26e94f6c120d)) instead, which either can be self-hosted or the public one requires some research for how to use it
											- Related: ((631fa97e-451a-4fdf-b05b-5184648fcc81))
									- [Resetting the server-side key backup](https://element.io/blog/resetting-the-server-side-key-backup/)
									-
									- Bots
										- [t2bot.io - Homepage](https://t2bot.io/)
								- Interesting projects built on Matrix
								  collapsed:: true
									- ((644c0a7a-3e61-4b57-bff6-4f8262737198))
									- Forums
										- [GitHub - corepaper/morum: Matrix forum](https://github.com/corepaper/morum)
										- [Zo](https://zo.me/)
										  collapsed:: true
											- [Zo (10_10_2023 21_35_56).html](../assets/Zo_(10_10_2023_21_35_56)_1696970209486_0.html)
									- [Matrix Viewer - makes Matrix views as viewable webpages](https://github.com/matrix-org/matrix-viewer)
							- [SimpleX](https://simplex.chat/)
							- ((663b24fb-e901-4314-abf8-6f0c529ade12))
							- ### Anonymous
								- [Session](https://getsession.org/)
								  id:: 653f7873-aeb8-4d39-baab-04ef1ef77ceb
								  collapsed:: true
									- Pros/Cons
										- Pros
											- Usernames rather than phone numbers, unlike Signal
											- Onion requests for anonymity (but not quite Tor)
											  collapsed:: true
												- [https://getsession.org/onion-requests-session-new-message-routing-solution/](https://getsession.org/onion-requests-session-new-message-routing-solution/)
												- It uses slightly different model than Lokinet onion routing but the same nodes currently since it was an easier solution. Making them the same is the long-term goal
												  [https://github.com/privacytools/privacytools.io/issues/1940#issuecomment-643849891](https://github.com/privacytools/privacytools.io/issues/1940#issuecomment-643849891)
													- The main reason we have built two onion routers is that integrating Lokinet in mobile platforms is much trickier than integrating onion requests. Mobile platforms require we integrate with the VPN API and port parts of the C++ Lokinet code to natively on each mobile OS. This is the long term plan since it will add the ability to use Lokinet on a phone and also add the ability for Session to make voice calls, however its easier for us right now to use onion requests because of their relative simplicity.
											- PIN code to encrypt local database - does Signal have this?
											  collapsed:: true
												- Session allows users to encrypt their local Session database with a PIN code. With this feature turned on, your messages cannot be accessed without knowing your PIN code.
											- [Voice (and video) calls P2P](https://getsession.org/blog/calls-beta-release)
										- Cons
											- Lacks
												- [forward secrecy](https://getsession.org/blog/session-protocol-technical-information)
												- [Folders/Spaces to group chats](https://github.com/oxen-io/session-desktop/issues/2041#ref-issue-2485090530)
												- [Pin message in chat/room](https://github.com/oxen-io/session-desktop/issues/2010#ref-issue-1879053961)
												- [Stickers](https://github.com/oxen-io/session-desktop/issues/410#issuecomment-821761299)
												- [Video messages](https://github.com/oxen-io/session-desktop/issues/1485#issue-802592954)
												- [P2P chat](https://github.com/oxen-io/session-desktop/issues/1818#issuecomment-1782217729)
												- [Anonymous destinations - Shared Pools · Issue #676 · oxen-io/session-desktop · GitHub](https://github.com/oxen-io/session-desktop/issues/676#issue-530149400)
												  Similar to Signal's metadata minimisation technique
												- [Group display picture](https://github.com/oxen-io/session-desktop/issues/1958#issue-1016030732)
												- [Censorship resistance](https://github.com/oxen-io/session-desktop/issues/892#issuecomment-2313286198) e.g. pluggable transports
												- [ARM64 support](https://github.com/oxen-io/session-desktop/issues/1635#issuecomment-2416201651)
												- [Multiple account support](https://github.com/oxen-io/session-desktop/issues/421#issuecomment-2409098917)
												- ((6714ea51-8760-4130-8173-33b1c5fb53ce))
													- [[2024-10-20 Sunday]]
														- Onion-routed calls
														- Groups have some size limits
														- Liblokinet library (Lokinet) needs to be integrated into Session
											- _Like Signal_
												- Push notifications are deanonymising somewhat, and polling is battery intensive
											- Centralised E2EEE Loki File Server used for images and other attachments. Uses onion routing
											  collapsed:: true
												- Session can send files, images and other attachments up to 10MB in both person-to-person conversations and group chats. By default, Session uses the Loki File Server for attachment sending and storage
												- Additionally, Session used proxy routing (soon to be onion routing) to hide users' IP addresses when uploading or downloading attachments from the Loki File Server. In future, you will be able to configure the Session app to use a custom file server, such as a self-hosted server or VPS (Virtual Private Server), if you would prefer not to use a file server hosted by the Loki Foundation.
												- File uploads and open groups are now fully onion routed
												  source:: [https://getsession.org/release-roundup-7/](https://getsession.org/release-roundup-7/)
											- _Currently doesn't support_
												- Can't restore previous messages or contacts
												  collapsed:: true
													- No backups possible currently
													- Your recovery phrase is not currently able to restore your contacts or messages. For your security, your contacts and messages are stored locally, so they cannot be retrieved once you have deleted them.
												- Group chats are no longer E2EE and decentralised if there's more than 20 people, however anonymity is preserved via onion routing
												  collapsed:: true
													- [source] [https://getsession.org/session-release-roundup-9/](https://getsession.org/session-release-roundup-9/)
													- They do however always use onion routing
									- [Roadmap](https://oxen.io/roadmap)
									  id:: 6714ea51-8760-4130-8173-33b1c5fb53ce
									- Lokinet (basically Tor 2.0)
									  collapsed:: true
										- [https://lokinet.org/](https://lokinet.org/)
										- Pros
											- Better than Tor for decentralisation
											  [https://github.com/privacytools/privacytools.io/issues/1940](https://github.com/privacytools/privacytools.io/issues/1940)
											- Based on Monero
										- Cons
											- still WIP
											- Lacks exit nodes to access the clearnet
										-
									- {Archive}
										- Founded in Australia, which may be compelled to insert a backdoor if the encryption law TOLA goes through
											- In 2024 now run by a Swiss organisation
					- # E2EE P2P synchronous
						- Pros/Cons
						  collapsed:: true
							- Pros
								- No servers so can't be MITM'd or tracked by a middleman server
							- Cons
								- P2P obstacles
								  collapsed:: true
									- No decentralised conversation history
									- Offline messaging difficult
									- Group chat difficult
								- Low usability on mobile
								  collapsed:: true
									- Require Orbot or similar on always
									- Higher battery drain
										- as push isn't as simple. If there's presence (online indicator) then The battery drain is caused by the way tox works. It's a peer to peer network, meaning that a client has to have multiple network connections open at the same at all times, which is what drains the battery. So I wouldn't expect the battery drain to ever be fixed.
									- Would be difficult to implement on iOS
								- Slack is way more fully featured in comparison
								  As of April 2016
								- Low anonymity vs global surveillance
								  collapsed:: true
									- Low latency - easy to detect where data starts and finishes (traffic analysis)
									- Especially because there's an open connection always
									- _Only asynchronous chat (forum or email-like) can work_
						- **P2P-only**
							- Jami
							  collapsed:: true
							  AKA Ring previously
								- [https://jami.net/help/](https://jami.net/help/)
								- Cross-platform all major platforms
								- Multi-device support
								- Decentralized username registry via Ethereum blockchain
								- https://ring.cx
							- [Tox](https://tox.chat/)
							  collapsed:: true
							  Tox available on desktop only
								- Pros
								  collapsed:: true
									- Minimal if any metadata loss
									- Tor can be used
									  https://wiki.tox.chat/users/tox_over_tor_tot
								- Cons
								  collapsed:: true
									- lack of multi-device (carbons) though it's apparently 90% complete
									- no group chats
									- mobile battery drain
									- Lower importance
										- As of October 2015 Tox doesn’t seem to have an answer yet for decentralised conversation history storage.
								- Notes
								  collapsed:: true
									- Relies on a Distributed Hash Table (similar to bittorrent) for peer discovery
									- platform for audio, video chat, and file sharing.
									- peer-to-peer communications (including chat) encrypted between individuals and sent between IP addresses. While the encryption should make the contents private, the metadata of any communication would still be accessible. This means Bob and Alice use Tox; Bob and Alice's IP addresses are identifiable, and the fact that they are using Tox, which is evident from network payload headers.
									- Low latency so vulnerable to traffic analysis (the times and amounts of content transmitted between the two)
									- Can use Tor for anonymity (and still allows communication with non-Tor using contacts)
									  https://wiki.tox.chat/users/tox_over_tor_tot
								- Notes 2
								  collapsed:: true
									- Connections between friends are encrypted.
										- Every peer is identified by a curve25519 public key. To add someone as a friend, you add that public key.
										- http://nacl.cr.yp.to/box.html
										- is the crypto used.
										- https://github.com/irungentoo/toxcore/blob/master/docs/Tox_m...
										- describes the protocol used to connect securely to friends after they find themselves.
										- This protocol has PFS, message padding to prevent length based leaking and should be immune against replay attacks.
										- What makes it secure is that you know the long term public key of your friends making it really easy for the software to establish secure connections to them.
										- nly 799 days ago [-]
										- Are IP addresses encrypted in the DHT?
										- irungentoo 799 days ago [-]
										- Instead of doing things like encrypting ips, peers have temporary DHT public keys.
										- The only way to get the ip of someone from their Tox id is by knowing their public DHT key which they will only send you if they are your friend.
										- How this works is described in detail: https://github.com/irungentoo/toxcore/blob/master/docs/Prevent_Tracking.txt
										- Implemented/planning to use onion routing to give out your real public DHT keys to allow friend requests
										- https://github.com/irungentoo/toxcore/blob/master/docs/Prevent_Tracking.txt
									- Progress overview https://github.com/irungentoo/toxcore/blob/master/docs/TODO.md
										- https://wiki.tox.chat/users/faq
										- https://github.com/irungentoo/toxcore
										- Development looks pretty dead https://github.com/irungentoo/toxcore/graphs/contributors
											- Fork by same team but not main dev as he's busy lately https://github.com/TokTok/c-toxcore
										- In July 2016 it seems group chats and offline messaging still aren't implemented
										- Not fully distributed. https://github.com/irungentoo/toxcore/issues/1398 Relies on supernodes for directing messages and bootstrapping
										- The lack of consistent profile ended up killing it for us. Reinstall your OS? New profile. Change your phone? New profile. Reinstall the app? New profile
										- No multi device simultaneously though it's 90% there
										- https://blog.tox.chat/2016/08/update-new-client-xenial-packages-tox-in-google-play-toxcore-fork-and-more/
										- DHT is like better and decentralised DNS but still some issues
									- qTox looks like a Slack lite
									- https://github.com/qTox/qTox/blob/master/README.md
									- TokTok may be the new fork since Tox development is slow
								- I2P in development
								  https://github.com/irungentoo/toxcore/issues/942
						- **Anonymous E2E **
						  Still may be easy to deanonymise via traffic analysis of open connection
							- 2023
								- [Briar](https://briarproject.org)
								  id:: 663b24fb-6756-451e-a165-d64fa94ed60a
								  collapsed:: true
									- Pros/Cons
										- Pros
											- Several types of one-to-many comms including groups, forums and microblogs
											- Briar Mailbox
												- [Briar Mailbox released to improve connectivity -  Briar](https://briarproject.org/news/2023-briar-mailbox-released/)
												- Ability to link a Briar Mailbox to the desktop client. Briar Mailbox is a helper app that enables users to receive encrypted messages from their contacts even when Briar is offline. With this new update, users can now link their Briar Mailbox to the desktop client, providing a seamless messaging experience across devices. Intended for a mobile device you leave plugged in at home, or a VPS
												- https://news.ycombinator.com/item?id=36541798
												-
										- Lacks
											- Battery/CPU optimisation
											- UX could be better and more WhatsApp-like
									- https://code.briarproject.org/akwizgran/briar/tree/master
									- Documentation
										- https://briarproject.org/manual/
									- Briar (https://briarproject.org/) works by running a Tor hidden service on your device which has (most of) the decentralization properties of Tox/Ring while not killing your battery and not use an inordinate amount of data.
								- ((653f7873-aeb8-4d39-baab-04ef1ef77ceb))
								- [Ricochet](https://ricochet.im/)
								  collapsed:: true
								  Every user is a Tor hidden service (utilises Tor triple-encryption)
									- A peer-to-peer instant messaging system built on Tor hidden services. Your login is your hidden service address, and contacts connect to you through Tor.
									- Pros
										- Has had a security audit
										  https://github.com/ricochet-im/ricochet/releases/tag/v1.1.2
									- Cons
										- Missing features
											- Creating a mobile version
											- Inline images/files
											- Markdown support
											- Private group chat
											- Multiple Aliases
							- ((64942661-0474-4d70-980f-301888727a1b)) chat via I2P/Tor (not ready yet)
							- I2P Messenger
							  collapsed:: true
								- I2P-Messenger is a simple Qt-based, serverless, end-to-end-encrypted instant messenger for I2P.[34] No servers can log the user's conversations. No ISP can log with whom the user chats, when, or for how long. As it is serverless, it can make use of I2P's end-to-end encryption, preventing any node between two parties from having access to the plain text. I2P-Messenger can be used for fully anonymous instant communication with persons the user doesn't even know, or, alternatively, to communicate securely and untraceably with friends, family members, or colleagues. In addition to messaging, file transfer is also supported.
							- ChatSecure(?)
							  collapsed:: true
								- (dev implied he's going to implement Tor hidden services as users)
								  intralink2:: https://workflowy.com/#/f4b33fa3aee8
					- # E2EE P2P asynchronous
					  id:: 663b24fb-3d41-4d79-9a3d-319057fd1728
					  Email-like, forum
						- _Why_
							- [Traffic analysis not as effective compared to real-time best-effort types like Tor](https://secushare.org/anonymity)
							- Allows sending messages to an offline recipient without a central server
						- **P2P-only**
							- E2EE ((663b24fb-d9cc-4bff-b533-9c9cedc07adb)) via Thunderbird
							  collapsed:: true
								- [https://support.mozilla.org/en-US/kb/introduction-to-e2e-encryption](https://support.mozilla.org/en-US/kb/introduction-to-e2e-encryption)
							- pretty Easy privacy (p≡p)
							  id:: 663b24fb-c2c5-4650-929b-f56aca133bc2
							  collapsed:: true
							  AKA pEp | Will have anonymity via GNUnet in the future
								- Pros/Cons
								  collapsed:: true
									- Cons
										- Mobile apps likely drain battery faster since they're P2P
								- Supports Outlook, Thunderbird and has mobile apps
								  collapsed:: true
									- Android app
									  https://play.google.com/store/apps/details?id=security.pEp
									- ((663b24fb-c2c5-4650-929b-f56aca133bc2)) (Read and write encrypted e-mails) - [[404 Page Not Found | F-Droid - Free and Open Source Android App Repository](https://f-droid.org/packages/security.pEp](https://f-droid.org/packages/security.pEp))
								- https://www.pep.security/faq/
								- News
								  https://www.pep.security/news.html.en
								- When will p≡p be available?
								  collapsed:: true
									- Enigmail/p≡p release which includes anonymization will be available in 2019.
									- If both sides are using pEp, it automatically uses the anonymous transport provided by GNUnet. With that technology, meta data is no longer readable for an attacker. pEp is fully peer to peer itself. And only you have the keys. However it can inter-operate with legacy mail to secure that whenever applicable (if the intended recipient has a GPG key)
								- _It uses a cascading series of checks to send messags in the most secure way, based on online availability, and whether the user is using pEp or not_
								  collapsed:: true
									- When a p≡p user is communicating with another p≡p user:
										- 1. if online communication available: OTR through GNUnet.
										- 2. if online communication not available:
											- a. if anonymizing platform available, OpenPGP through anonymizing platform (i.e. Qabel),
											- b. if anonymizing platform not available, fallback to OpenPGP.
									- When a p≡p user is communicating with a non-p≡p user then depending on the capabilities of the non-p≡p user:
										- 1. if anonymizing and forward secrecy is possible, use that (i.e. OTR over GNUnet).
										- 2. if anonymizing but no forward secrecy is possible, use that (i.e. OpenPGP over Qabel).
										- 3. if forward secrecy is possible, use that (i.e. OTR).
										- 4. if hard cryptography but no forward secrecy is possible, use that (i.e. OpenPGP)
										- 5. if only weak cryptography is possible, use that (i.e. S/MIME with commercial CAs)
										- 6. send unencrypted.
								- Source code
								  https://pep.software/software-android.html
								- _Related: _
									- Email
									  #Email https://workflowy.com/#/a097fcfcb31b
									- E2EE emails via Thunderbird
									  [E2EE emails via Thunderbird](https://workflowy.com/#/c0b134bf8126)
							- Bitmessage
							  collapsed:: true
							  Though can use Tor or I2P for anonymity
								- Bitmessage
								  collapsed:: true
									- Intro
										- BitMessage creates a peer-to-peer network of its own with properties specifically designed for sending messages. As the whitepaper describes it, “objects are broadcast throughout a Bitmessage stream. We propose that nodes store all objects for two days and then delete them. Nodes joining the network request a list of objects from their peer and download the objects that they do not have. Thus they will receive all messages bound for them that were broadcast during the last two days.” “Objects” are the basic unit of the network’s operation, and are replicated throughout the network. To limit the creation of objects and avoid spam, making an object requires solving a proof-of-work computation, which takes about four minutes on an average computer – in short, a replica of Adam Back’s HashCash anti-spam scheme first proposed in 1997.
										- If both the sender and receiver are online, the process can happen within seconds, but otherwise they merely need to be online within a two day timespan of each other four times (really three times, as the acknowledgement is not crucial to sending the message) for the transmission to take place. Once two users are aware of each other’s public keys, the first and second steps do not need to be repeated, making the process even easier. Identities on BitMessage are referred to by addresses like “BM-2nijaB5b1C6HESgdqFMoMzWqNchA9w84Xmv”, which are formed from public keys in a similar way to Bitcoin addresses.
									- See whitepaper for why world wide web is insecure
									- https://github.com/mailchuck/PyBitmessage/releases
									- Permanent Encrypted Anonymous Email Service?
										- > Hello. I am looking to make the email address I sign up for a "messenger" address that will forward any incoming mail to my actual address (@protonmail)
										- > What I mean by encrypted and anonymous is that the address unencrypted would be:
										- > (chosentext)@(domain.com) would turn into → (N4JI3NJKLL878Y@(domain.com)
										- Bitmessage E-mail Gateway
										- https://bitmessage.ch/
										- the addres are like: "BM-2cSrYp694uNaZwAwjkinvdjJQj7fgnqqXT@bitmessage.ch" And you can have an alias like: "mialias@bitmessage.ch" (But you only can login with your original address). Support IMAP, POP3 and SMTP.
								- Bitmessage is a P2P communications protocol used to send encrypted messages to another person or to many subscribers. It is decentralized and trustless, meaning that you need-not inherently trust any entities like root certificate authorities. It uses strong authentication which means that the sender of a message cannot be spoofed, and it aims to hide "non-content" data.
								- https://bitmessage.org/wiki/Main_Page
								- OS: Windows, Mac, Linux.
								- Messaging lists
								  collapsed:: true
									- https://bitmessage.org/forum/index.php?topic=1689.0
								- Bitmessage is a peer-to-peer email-like communication protocol. It is totally decentralized and places no trust on any organization for services or validation.
								- Pros/Coms
								  collapsed:: true
									- Advantages:
										- resistant to metadata analysis
										- relatively easy to use
										- works and is actively used by many people.
									- Disadvantages:
										- unsolved scaling issues: all messages are broadcast to everyone
										- no forward secrecy
											- because there is no forward secrecy, it is especially problematic that anyone can grab an encrypted copy of any message in the system. This means if the private key is ever compromised, then all the past messages can be decrypted easily by anyone using the system.
										- relies on proof of work for spam prevention, which is probably not actually that preventative (spammers often steal CPU anyway).
							- See Gun
						- **Anonymous E2E **
							- ((663b24fb-d9cc-4bff-b533-9c9cedc07adb))
							- Email account acquired via Tor
							- I2P-Bote
							  collapsed:: true
							  Uses Proof of Work to limit rate limit spam. So few min delay - like email
								- https://www.reddit.com/r/i2p/comments/1m1vi6/secure_and_private_email_in_i2p/
								- Pros/Cons
									- Pros
										- Anonymous email
										  collapsed:: true
											- When emailing, choose to have a From address as your normal inbox address/spin a new address/don't have one at all
												- there's still a source address that is embedded into each message (even if it is just a random string). Again, however, I2P-Bote has various features which can help to further obfuscate this information. The first way is by simply creating a new identity (i.e. a new I2P-Bote address or destination). Identity creation in I2P-Bote takes less than 20 seconds, allowing users to simply create a new I2P-Bote address through which they can send mail. Approaching the problem this way allows you to also receive messages back from whoever you sent them to. So, if you want to send a message to your technically-apt boss named Bob to tell him he's incompetent without the source address being the same as the regular messages you send him, you can just spin up a new identity and send it to him through that. But what if you don't care about receiving anything back from Bob, you just want to tell him he's an idiot? Well, when sending a message over I2P-Bote one can simply select to not include any source information at all, making the message truly anonymous. Think of it like sending a letter without a return address.
											- Optional custom delaying setting to impair traffic analysis
												- 2P-Bote includes a system where-in the user can select a number of nodes through which the messages will be bounced around before going to the distributed hash table to be stored (more on that later). But this alone isn't much different from how I2P works in the first place, therefore I2P-Bote also integrates a delay between each node as the message is bounced around. This delay can be set to a random interval within a range (for example, a random amount of time between 1-60 minutes per bounce). Thus, not only are the emails bounced around between nodes, but the time that the email itself was sent is obfuscated by a randomized delay. This makes it possible to send a message, log off, and have it arrive some time later without any correlation between the time that you were logged onto I2P and the time the message arrived. The combination of the I2P network protocol and the way in which I2P-Bote routes messages provides a robust and redundant anonymization strategy.
										- Confidential
										  collapsed:: true
											- The main component which embeds security into I2P-Bote is the way in which it employs encryption. Like e-mail, when sending a message to someone over I2P-Bote the sender enters in the receivers address. However, unlike email where the address looks like david@thetinhat.com, I2P-Bote uses cryptographic keys as destinations, which are random numbers and letters. Essentially what this means is that when you send a message to a friend over I2P-Bote you enter in their destination (a long string of random characters), and because their destination is also their public key the email is automatically encrypted using that public key. Therefore, end-to-end encryption is the default in I2P-Bote, and no clear-text messages are ever sent or stored.
											- Moreover, unlike standard email which exposes a large amount of information in the header, mail sent over I2P-Bote sanitizes the headers, removing any gratuitous information, and encrypting whatever remains (such as the subject line).
											- Transparent encryption
										- Resilient
										  collapsed:: true
											- P2P
											- Messages are stored in DHT for 100 days
									- Cons
										- Scalability issues - uses broadcast/unicast not multicast
										  http://about.psyc.eu/Multicast
										- Social usability issues
										- Stores data on a DHT - ? (not sure of consequences)
								- Info
									- I2P-Bote is a fully decentralized and distributed email system. It supports different identities and does not expose email headers. Currently (2015), it is still in beta version and can be accessed via its web application interface or IMAP and SMTP. All bote-mails are transparently end-to-end encrypted and, optionally, signed by the sender's private key.
									- I2P-Bote is a free, fully decentralized and distributed anonymous email system with a strong focus on security.[32] It supports multiple identities and does not expose email metadata. As of 2015, it is still considered beta software. I2P-Bote is accessible via the I2P web console interface or using standard email protocols (i.e. IMAP/SMTP). All bote-mails are transparently end-to-end encrypted and signed by the sender's private key, thus removing the need for PGP or other email encryption software. I2P-Bote offers additional anonymity by allowing for the use of mail relays with variable length delays. Since it is decentralized, there is no centralized email server that could correlate different email identities as communicating with each other (i.e. profiling). Even the nodes relaying the mails do not know the sender, and apart from sender and receiver, only the end of the high-latency mail route and the storing nodes will know to whom (which I2P-Bote address – the user's IP address is still hidden by I2P) the mail is destined. The original sender could have gone offline long before the email becomes available to the recipient. No account registration is necessary, all you have to do in order to use it is create a new identity. I2P-Bote can be installed as an I2P plugin .[33]
								- I2P-Bote is a fully decentralized and distributed email system. It supports different identities and does not expose email headers. Currently (2015), it is still in beta version and can be accessed via its web application interface or IMAP and SMTP. All bote-mails are transparently end-to-end encrypted and, optionally, signed by the sender's private key.
								- Setup
									- https://thetinhat.com/tutorials/messaging/i2pbote.html
									- https://thetinhat.com/tutorials/messaging/i2p-bote-thunderbird.html
									- https://www.deepdotweb.com/2016/11/16/noobs-guide-i2p-bote/
								- http://i2pbote.i2p.us/
								- OS: Windows, Mac, Linux, Android, F-Droid.
							- secushare
							  collapsed:: true
							  GNUnet-based | AKA PSYC, PSYC2
								- Overview
									- PSYC(1) was like efficient IRC
									- [http://secushare.org/answers](http://secushare.org/answers)
										- Multicasting http://about.psyc.eu/Multicast
									- Now PSYC2 is planning to be fully P2P
									- http://secushare.org/
									- Comparison with Tor and I2P http://secushare.org/anonymity
									- Comparison with Friendica and Facebook http://secushare.org/features
									- With all best options http://secushare.org/comparison
									- Progress http://secushare.org/prototype their source code isn't available due to /transparency philosophy (global surveillance)
										- Looks like last update was around March
										- Much of it is also integrated into GNUnet directly
								- Comparisons
									- https://matrix.org/docs/guides/faq.html#what-is-the-difference-between-matrix-and-psyc
									- [http://about.psyc.eu/Matrix](http://about.psyc.eu/Matrix)
								- _Related:_
									- [https://youbroketheinternet.org/](https://youbroketheinternet.org/)
							- _Blockchain-based messengers_
								- [Steem Chat-Wallet](https://github.com/therealwolf42/Steem-Chat-Wallet)
								  collapsed:: true
									- https://steemit.com/utopian-io/@therealwolf/introducing-steem-messenger-beta
							- Whisper for Ethereum
							  collapsed:: true
								- https://github.com/ethereum/go-ethereum/wiki/Whisper-Overview
								- Plans to defeat traffic analysis
								  https://github.com/ethereum/wiki/wiki/Whisper
				- Non-P2P, not E2EE
				  collapsed:: true
				  Silos / walled garden
					- _Group-based_
						- [WhatsApp](https://play.google.com/store/apps/details?id=com.whatsapp)
						  id:: 663b24fb-f1f2-4dbe-ae47-d3a910654835
						  collapsed:: true
							- Pros/Cons
							  collapsed:: true
								- Pros
									- E2EE chat backups
									  collapsed:: true
										- Offers either HSM-based+password, or 64-digit encryption key (use the 64-digit one)
											- With the introduction of end-to-end encrypted backups, WhatsAppcreated an HSM (Hardware Security Module) based Backup Key Vaultsecurely store per-user encryption keys for user backups in tamper-resistant
											- storage, thus ensuring stronger security of users’ message history.
											- With end-to-end encrypted backups enabled, before storing backups incloud, the client encrypts the chat messages and all the messaging datatext, photos, videos, etc) that is being backed up using a random key that’s
											- generated on the user’s device.
											- The key to encrypt the backup is secured with a user-provided password.
											- The password is unknown to WhatsApp, the user’s mobile device cloud
											- partners, or any third party. The key is stored in the HSM Backup Key Vault
											- to allow the user to recover the key in the event the device is lost or stolen.
											- The HSM Backup Key Vault is responsible for enforcing password verification
											- attempts and rendering the key permanently inaccessible after a certain
											- number of unsuccessful attempts to access it. These security measures
											- provide protection against brute force attempts to retrieve the key.
											- Additionally, the users have a choice to use a 64-digit encryption key instead
											- of a password, which would require them to remember the encryptionthemselves or store it manually as in this case the key is not sent to the HSM
											- Backup Key Vault.
								- Cons
									- Lacks many privacy features Signal has e.g. encrypted profiles, ((663b24fb-4437-4115-83da-5f5b668989fc)), sealed sender
									- Chat backups aren't encrypted
									- E2EE has flaws
										- Opportunistic encryption - You have to go into settings to enable even just seeing key changes, let alone that the client stops you from sending messages when a previously verified key changes.
							- _Fake E2EE_
							  not private because the private encryption keys are held server side
							- Privacy
							  collapsed:: true
								- Profile Picture: My Contacts only
								- [[2024-11-13 Wednesday]] Tried to make a second WhatsApp instance in ((63209286-6f40-4063-9fdc-2543251d416e)) : ((6734cfe5-e8f7-4cbe-ae3a-a32c97b63717)) and ((663b24fb-831b-448c-81fb-0a8407d24408)). Couldn't seem to register with Hushed, likely because it's a VoIP number
							- Phone number
							  collapsed:: true
								- Different from main phone number
							- How to harden
							  https://medium.com/@thegrugq/operational-whatsapp-on-ios-ce9a4231a034#.uxgmdmg8g
							- Be very carefyl who I share this with - lots of identifying information
							  collapsed:: true
								- Immediately they get my phone number and my face
								- By searching my phone number he can find out:
								- 1- my social media details (Facebook, Linkedln)
								- 2- my family members
								- 3- potentially my address
								- 4- my employer
								- 5- what people are in my network
								- That kind of risk we are talking about
							- Required permissions
							  Last updated: [[2024-11-11 Monday]]
								- `Music and audio` = for backup restoring
								- `Contacts` = to see the display name of people
								- `Photos and videos` = for sending attachments
								- `Phone` = ? maybe for Google account
							- [[2024-12-17 Tuesday]] Only seem to need Contacts, Network and Notifications for daily backups to occur, possibly less
							- [[2024-11-11 Monday]] Restoring backup on GrapheneOS not working, can't seem to select my Google account
								- It only shows `Add account` instead of letting me select existing accounts (existing accounts can be viewed in `Android settings` > `Passwords, passkeys and accounts`)
								- Trying to remove the aaronsollesse@gmail.com account and add it again via WhatsApp still makes the account inaccessible to WhatsApp
								- Solution: some combination of this
									- Temporarily giving WA extra permissions
										- Call logs, camer, location, microphone, nearby devices, sensors, sms
									- Giving play services extra permissions
										- Phone
										- Contacts
						- [Telegram](https://telegram.org/)
						  id:: 646c8171-5cd2-46cb-8f97-28d8917a0461
						  collapsed:: true
							- Pros/Cons
								- Pros
									- Cross-platform - desktop, mobile and web apps
									- High usability - fast, similar UX to WhatsApp/Discord
									- Available across any platform
									- Can register any phone number with it (though you can with Signal too)
									- legal address in UAE to hide from prosecutors
								- Cons
									- Very poor E2EE implementation
									  id:: 663b24fb-6e14-4954-828f-fe22d8b9fdf8
										- Calls have E2EE but requires confirmation in every call so nobody practically uses it
										  collapsed:: true
											- Telegram calls have encryption, but every time you have to verify the emojis again and again instead of it just storing the other party's key.
										- Not E2EE by default. Only 1:1 chats can enable it and not group chats. Also official desktop application does not support e2e chat
										  collapsed:: true
											- Only Secure Chats - normal convos don't encrypt conversations from provider, allows contact verificiation and past comms are secure if keys are stolen
											  source:: https://www.eff.org/secure-messaging-scorecard
										- encrypted mode be some second-rate mode that removes most of the features you need (like Telegram's encrypted chats; I see that the announcement already mentions some unavailable features when you turn on encryption)
										- Many Cryptographers have raised concerns on their encryption protocol.
										  collapsed:: true
											- MTProto which Telegram uses to encrypt messages doesn't use a MAC and this is a fundamental flaw in Telegram's encryption. Cipher and MAC operation ordering is considered the standard for symmetric encryption but instead, Telegram tries to abuse a hash function as a pseudo-MAC. It's because of this that MTProto encryption in Telegram has been vulnerable to a number of well documented attacks, which otherwise wouldn't be case.
									- Server code is not open-source
									- Requires Phone number for registration
									- Censorship
										- They've censored [disclose.tv](https://gab.com/a/posts/106454675530482719) chats
										- In Q2 2023 for iOS Tommy Robinson's group chats were censored
							- Conclusion:
								- With their legal structure it's unlikely they can be forced to hand over user data (under typical legal routes) but they're not a zero knowledge platform. It's better to seek security by design than security by policy. All it takes is for them to hand over data in a business deal or perhaps through some type of legal strong-arming. WhatsApp is probably better since it's E2EE for chat
							- RSS
								- `[Error in RSSHub!](https://rsshub.app/telegram/channel/rooshofficial`)
								- `[Not Found](https://openrss.org/t.me/rooshofficial`)
							- 2024 [Arrest of Pavel Durov - Wikipedia](https://en.wikipedia.org/wiki/Arrest_of_Pavel_Durov)
								- [It's his fault](https://news.ycombinator.com/item?id=41376204) for ((663b24fb-6e14-4954-828f-fe22d8b9fdf8)), unlike ((6312a076-eb26-4bd5-a669-ea0a50d06668)), ((663b24fb-f1f2-4dbe-ae47-d3a910654835)), etc
									- > This analysis leaves out the fact that Pavel Durov is, with Telegram, in approximately the same position Ladar Levison was with Lavabit. Unlike Meredith Whitaker, Durov actually is in a position to furnish documents to the French government, where he has citizenship. He's in that position because he has repeatedly made deliberate product decisions, to the bafflement of cryptographers around the world, to keep himself in that position.
									  > 
									  > If you literally have plaintext documents responsive to criminal inquiries in a jurisdiction you are subject to, we don't reach the "internet censorship wars". You're in a place not dissimilar to a 1970s telephone company; the "random people can't simply declare themselves above the law wars". Don't be in that place. Encrypt end-to-end.
						- iMessage
						  collapsed:: true
							- AirMessage for Android
								- https://www.reddit.com/r/AirMessage/comments/avj2y5/how_to_use_phone_number_with_airmessage_sometimes/
							- Apple cannot decrypt
							  [https://old.reddit.com/r/privacytoolsIO/comments/en8hh1/why_not_telegram/fdxior5/](https://old.reddit.com/r/privacytoolsIO/comments/en8hh1/why_not_telegram/fdxior5/)
					- _Channel-based_
					  id:: 64463cc5-a732-4069-9ccd-d28adb8da813
						- Pros/Cons
						  collapsed:: true
							- Pros
								- Integrations with Zapier and all other apps
							- Cons
								- Not quite context-specific chat unless there's GUI task creation
								  intralink2:: https://workflowy.com/#/2522d153ea5d
								- Limited hierarchy and task management
						- **Requirements**
						  collapsed:: true
							- For me to move our PostMyMeds team from Slack, it should be a long-term platform:
								- Full-text search
								- Self-hosted
								- GUI task creation (via API/integration?)
							- _Potential_
						- _Open-source_
							- ((631fa97e-a0a9-406c-b7b9-20536d421090))
							- [Revolt](https://revolt.chat)
							  collapsed:: true
								- Pros/Cons
								  collapsed:: true
									- Pros
										-
									- Cons
										-
									- Unclear
										-
									- Comparisons
										- Comparison with ((631fa97e-a0a9-406c-b7b9-20536d421090))
											- Pros
												- Better UX
											- Cons
												- Lacks E2EE, but on roadmap
											- Same
												- Can be self-hosted
									- Related: ((63ff81fa-0c13-4db8-b744-81696a40227b))
								- [Revolt · GitHub](https://github.com/revoltchat)
							- Mattermost
							  collapsed:: true
								- Mattermost
									- Self-hosted Slack alternative https://workflowy.com/#/3c18a8c16bd0
									- Pros/Cons
									  collapsed:: true
										- Pros
											- Fantastic feature set
											- Free, no limitations
											- Open-source, self-hosted
										- Cons
											- Young product - may be still full of bugs (especially mobile apps)
											- Does it play well with being a hidden service?
											- Starting a Mattermost instance means being responsible for maintenance and debugging, unlike other solutions
											- Lacks
												- OMEMO E2E encryption
												  https://mattermost.uservoice.com/forums/306457-general/suggestions/12818799-off-the-record-messaging
												- Threaded Channels (Twist-like)
												  https://mattermost.uservoice.com/forums/306457-general/suggestions/20157766-build-a-thread-system-similar-to-twist
									- Features
									  collapsed:: true
										- Features
											- Viewing video, audio, images and animated files
											- Customizing notifications on mentions of names and keywords
											- Searching and filtering by channel, user and keywords
										- Mattermost bots
										  intralink2:: https://workflowy.com/#/d2f18f715075
										- Mattermost integrations
										  intralink2:: https://workflowy.com/#/eac83c3a90f7
										- Mattermost ideas
										  intralink2:: https://workflowy.com/#/4ef610db0133
										- Many integrations
										  http://www.mattermost.org/community-applications/
											- Forwarding Disqus comments to a channel
											  https://github.com/jonathanwiesel/matterqus
											- Forwarding emails
											  https://github.com/rodrigocorsi2/mattermail
											- RSS feeds
											  https://github.com/bitbackofen/Rss-Atom-Feed-Integration-for-Mattermost
											- Zapier (Integrate 700 apps with Markdown support using Zapier)
											  https://about.mattermost.com/mattermost-3-4/
											- **See more**
											  https://www.mattermost.org/community-applications/
										- Lots of interesting features
											- https://about.mattermost.com/mattermost-3-4/
											- https://about.mattermost.com/category/blog/
											- https://forum.mattermost.org/
											- https://mattermost.uservoice.com/
									- Setup
									  collapsed:: true
										- http://docs.mattermost.com/
										- Demo instance
											- https://gitlab.mattermost.com/community/channels/town-square
											- https://gitlab.mattermost.com/signup_user_complete/?id=fqbr3mubzjg9ty7cks5xkxr3hh
										- Platforms
											- Desktop
												- https://github.com/mattermost/desktop
												- https://github.com/HackerHappyHour/matterfront
											- Web app
											- Android
											- iOS
										- Community installers like Docker
										  http://www.mattermost.org/installation/
											- http://docs.mattermost.com/install/docker-local-machine.html#one-line-docker-install
									- _Related: _Project Management
									  #HabitLaboratory-Organisation https://workflowy.com/#/b3249da5c952
								- + Very high usability and tons of features like Slack
								- + It's self-hosted which ensures confidentiality
								- + Can access via VPN/Tor to ensure anonymity
								- + Works especially well for large groups due to having multiple chat channels
								- Self-hosted, which means there may be some web admin stuff that needs doing (though it's got a one-line Docker install option)
								- Relies on trusting the person who hosts the server
							- Rocket.Chat
							  collapsed:: true
								- Pros
									- Helpdesk popup
									  http://i.imgur.com/ITMYnur.png
										- https://github.com/RocketChat/Rocket.Chat/issues/1920
									- Video conferencing
									- Screen sharing
									- Zapier integration
									  https://rocket.chat/blog/announcing-zapier-integration
								- Cons
									- Lacks
										- Threading (most seem to want Flowdock's style)
										  https://github.com/RocketChat/Rocket.Chat/issues/1112#issuecomment-321957347
										- Encrypted chat
										  https://github.com/RocketChat/Rocket.Chat/issues/36#issuecomment-319631175
							- Gitter
							  collapsed:: true
								- https://gitter.im
								- http://i.imgur.com/1A67eCf.png
								- https://files.gitter.im/ricardobaeta/3Rm9/topics-listing-two.png
								- https://files.gitter.im/ricardobaeta/iu3m/topic.png
							- Zulip
							  collapsed:: true
								- Pros/Cons
									- Pros
										- Full text search
										- Integrations
										- Easy quoting and threading
									- Cons
										- Not great UI currently (but undergoing a refresh)
										  https://zulip.readthedocs.io/en/latest/roadmap.html
										- Can't thread within private messages
										- Lacks
											- Interactive message attachments (for integrations)
											  https://github.com/zulip/zulip/issues/6102
											- E2E encryption
											  https://github.com/zulip/zulip/issues/6096
												- There's a few open-source implementations of the Axolotl/OMEMO/Double-Ratchet protocol which allows for E2E encrypted group chats:
												- [Signal](https://www.whispersystems.org/docs/specifications/doubleratchet/)
												- [Wire](https://github.com/wireapp/proteus)
												- [SilentCircle](https://github.com/cukupupas/libsalamander)
									- Unclear
										- Every message is a thread
										  http://i.imgur.com/ZaCsroJ.png
											- Threads are basically all in-line with channel, like FlowDock or Slack's "also send to channel" feature
											  http://i.imgur.com/I4s7SUa.png
								- https://www.zulip.org/
								- https://zulip.readthedocs.io/en/latest/roadmap.html
							- Orbit
							  collapsed:: true
							  IPFS-based
								- https://github.com/orbitdb/orbit
							- Pidgin with OTR
							- XMPP (Jabber)
							  collapsed:: true
								- Jabber is the original open instant messaging (IM) technology, invented by Jeremie Miller in 1998 and formalized as the Extensible Messaging and Presence Protocol (XMPP) by the IETF as an Internet Standard for IM and presence.
								- Pros/Cons
									- Pros
										- Higher anonymity/less metadata than Signal
											- can run over federated/decentralised XMPP (Jabber) servers (i.e. recent versions of eJabberd, Prosody, etc.)
											- Require no uploading of address books, no phone number for registration
											- Can even be run anonymously over Tor
									- Cons
										- Group chat encryption only in Conversations client +  Gajim
										  April 2016
										- Group chats limited
											- Can't post pictures or audio
										- Limited functionality compared to all modern IM apps
								- Servers
									- Flavours
										- XMPP standard
										- Prosody
									- Public Hosted Servers
										- Standard
											- https://xmpp.net/directory.php
											- https://list.jabber.at/
											- https://jabber.blah.im/register_web
										- Conversations-compatible
										  https://gultsch.de/compliance_ranked.html
										- Tor hidden service
										  Requires Orbot/Whonix/T ails to access
											- https://securejabber.me/index.html
											- https://rows.io/
											- https://wtfismyip.com/jabber/
											- jabber.ccc.de
											- https://www.calyxinstitute.org/projects/public_jabber_xmpp_server
												- ijeeynrc6x2uy5ob.onion
										- But if both sides of a conversation — both Romeo and Juliet, in our example — use the same server for their Jabber accounts, they’ll leak less metadata about their conversations. Messages will stay within in the same server rather than getting sent over the internet.
									- Self-Hosted
										- Self-hosted hidden services
											- Wizard setup
											  https://github.com/glamrock/Stormy/blob/master/README.md
											- Buy VPS with Bitcoin
											- How to setup Pidgin/client for hidden service servers
											  https://www.calyxinstitute.org/education/how-to-using-jabber.calyxinstitute.org-server-via-its-tor-hidden-service-with-pidgin-and-off-the-record
								- Clients
									- Desktop
										- Pidgin
											- How to setup Pidgin/client for hidden service servers
											  https://www.calyxinstitute.org/education/how-to-using-jabber.calyxinstitute.org-server-via-its-tor-hidden-service-with-pidgin-and-off-the-record
										- Gajim
										  Has OMEMO
									- Mobile
										- Conversations
										  Android
											- Extension to XMPP using Axolotl ratchet (OTR upgrade allowing group chats and forward secrecy)
											  https://en.m.wikipedia.org/wiki/OMEMO
											- Pros
												- Higher anonymity/less metadata than Signal
													- can run over federated/decentralised XMPP (Jabber) servers (i.e. recent versions of eJabberd, Prosody, etc.) and require no uploading of address books, no phone number for registration, and indeed can even be registered fairly anonymously over Tor.
											- Other Android clients
												- ChatSecure will integrate Olm rather than Axolotl due to licencing issues, with collaboration with Conversations team
												  https://chatsecure.org/blog/chatsecure-v32-push/
													- Licencing issue due to Whisper Systems
													  https://github.com/ChatSecure/ChatSecure-iOS/issues/376#issuecomment-182015533
											- Other Platforms
												- Desktop: Gajim + OMEMO plugin
												  Replaces Pidgin + OTR
													- Jitsi maybe in the future
													  https://github.com/jitsi/jitsi/issues/199
												- Compatibility with iOS is poor
												  https://chatsecure.org/blog/chatsecure-v32-push/
											- Choose compatible Jabber server
											  https://mobile.twitter.com/ChatSecure/status/744217655993729024?p=v
										- ChatSecure
										  iOS - no longer developed for Android
											- No longer developed on Android, iOS only
												- They're focusing on Zom instead and recommend Conversations for Android
												  https://mobile.twitter.com/ChatSecure/status/780848326002429953
											- Feature request for hidden service P2P (like Ricochet)
											  https://chatsecure.uservoice.com/forums/193939-chatsecure-ios/suggestions/13622217-enable-user-logins-to-be-tor-hidden-services-like
												- Plans to create .onion addresses?
												  https://chatsecure.org/blog/using-ed25519-public-keys-as-identifiers/
												- issue ticket
												  https://github.com/ChatSecure/ChatSecure-iOS/issues/404
											- Plans to update ChatSecure ios to have OMEMO encryption
											  https://chatsecure.org/blog/chatsecure-conversations-zom/
										- Zom
										  Simplified ChatSecure. More defaults, less customisation
							- _Related:_ ((650aae19-56a4-43ed-b1dc-b3acd07ea36e))
						- _Proprietary_
							- [Discord](https://discord.com/)
							  id:: 663b24fb-0338-4d42-8e5a-7febac0fe00a
							  collapsed:: true
								- Pros/Cons
									- Pros
									- Cons
										- Bugs
											- [Push Notification Inactive Time-out setting doesn't work · Issue #575 · flathub/com.discordapp.Discord · GitHub](https://github.com/flathub/com.discordapp.Discord/issues/575)
											-
										- Discord violates privacy regularly
										  collapsed:: true
											- Desktop app violates privacy
												- I had to try and it seems like uBlock primarily kicks in for YouTube videos posted in text chat. For filtering out Google's tracking stuff and YouTube ads.
												- And, of course, running Discord in any browser makes it 100% impossible for Discord to find out anything about the host system like running apps or similar.
											- Discord doesn't delete all files you tell it to
											  source:: [Discord lies about removing deleted files. Files deleted over 1 year ago still exist.](https://old.reddit.com/r/privacy/comments/jy14qi/psa_discord_lies_about_removing_deleted_files/)
											- They decrypt audio/video
											  source:: [https://old.reddit.com/r/privacy/comments/jxpd7j/researcher_reverse_engineered_discord_and_found/](https://old.reddit.com/r/privacy/comments/jxpd7j/researcher_reverse_engineered_discord_and_found/)
										- Discord bans 3rd-party clients e.g. Cordless users
										  collapsed:: true
										  [https://news.ycombinator.com/item?id=25184751](https://news.ycombinator.com/item?id=25184751)
											- 1 Backlink
												- _See_ [Discord bans 3rd-party clients e.g. Cordless users](https://workflowy.com/#/fca98df0f46f)
										- More
										  collapsed:: true
											- [Discord causes... discord. D'oh.](https://teddit.net/r/privacy/comments/jxpd7j/researcher_reverse_engineered_discord_and_found/)
											- [Bad Discord Bad.](https://teddit.net/r/privacy/comments/eiicah/trawling_through_my_discord_data_package_after_35/)<a href="https://teddit.net/r/thehatedone/comments/fxs8am/received_an_official_message_from_discord_this/fmwszbz"></a>
											- [Baddddddd Discord.](https://teddit.net/r/thehatedone/comments/fxs8am/received_an_official_message_from_discord_this/fmwszbz)
									- Deleting messages
										- [https://github.com/victornpb/deleteDiscordMessages](https://github.com/victornpb/deleteDiscordMessages)
											- Userscript which allows deleting messages if you still have access to a particular channel
								- FOSS addons
								  collapsed:: true
									- GooseMod for Discord
										- Allows installing client-side plugins and themes, including disabling some analytics
										- [https://github.com/GooseMod/GooseMod](https://github.com/GooseMod/GooseMod)
										- Works as both browser extension and for desktop
										- Settings path
											- Flatpak
											  /home/boss/.var/app/com.discordapp.Discord/config/discord/settings.json
								- FOSS clients
								  collapsed:: true
									- _See_ [Discord bans 3rd-party clients e.g. Cordless users](https://workflowy.com/#/fca98df0f46f)
									- Cordless
									- Ripcord
										- Pros/Cons
											- Pros
												- Features
													- Not made from a web browser
													- Tabs
													- Multiple windows
													- Multiple accounts
													- Voice chat (Discord OK, Slack WIP)
													- Graphical emoji and custom emoji
													- Tab completion for user names and emoji
													- Customizable fonts, colors, and sizes
													- Custom bookmark lists for easily accessing only the channels you actually use
													- Variable DPI and multi-monitor support
													- Low CPU and memory usage
													- Zero GPU usage
													- No tracking or analytics
													- No installer or forced updates
											- Cons
												- Lacks
													- Can't hide muted channels
													  [https://dev.cancel.fm/tktview/dd643cc89af67b8d4899](https://dev.cancel.fm/tktview/dd643cc89af67b8d4899)
													- Compared to Discord
													  [https://dev.cancel.fm/service_features](https://dev.cancel.fm/service_features)
										- [https://cancel.fm/ripcord/](https://cancel.fm/ripcord/)
									- finch for pinephone
										- sseagull:
										- I'm guessing the ncurses-based IM client based on libpurple (in other words, the text-based version of pidgin).
							- [Slack](https://slack.com)
							  id:: 663b24fb-d7c8-4b7d-86f4-056243f4afb7
							  collapsed:: true
								- Pros/Cons
								  collapsed:: true
									- Pros
										- Not linked to a phone number, so it's easy for long term use
										- Less data shared than WhatsApp - no phone number, profile picture etc
									- Cons
										- Not zero knowledge - providers can see and search conversations
								- How-to
								  collapsed:: true
									- Mass-delete messages (100 at a time or delete any channel except general)
									  http://my.slack.com/archives
									- Exporting Data
									  collapsed:: true
										- Note
											- Free plan doesn't include private channels and direct messages
											  https://get.slack.help/hc/en-us/articles/204897248-Understanding-Slack-data-exports
										- Export link
											- http://my.slack.com/services/export
											- https://slack.com/archives
											- https://london-tribe.slack.com/services/export
										- Export chat to HTML
											- Original article
											  https://levels.io/slack-export-to-html/
											- GitHub
											  https://gist.github.com/levelsio/122907e95956602e5c09
												- Also downloaded to SELF-HOSTED folder as 'slack2html'
											- You’ll need to run it from your shell in the folder of your extracted (!) Slack export ZIP file. It will then make a folder called slack2html above the folder your in with all JSON and HTML files.
									- Change team ownership
									  https://london-tribe.slack.com/admin
								- Features
								  collapsed:: true
									- Integrations
										- We kept using the integrations with tools that have different functions:
										- for file storage: Google Drive and Dropbox
										- for project progress tracking: Pivotal Tracker, Trello
										- for code quality check: CircleCI, GitHub, Code Climate
										- for marketing and sales activities: HubSpot.
									- Markdown
									  https://slackhq.com/refreshing-posts-2-0-2ea803734c7f
									- Features eg /commands
									  https://productivityist.com/7-things-about-slack/
									- App directory
									  https://slackhq.com/the-slack-platform-launch-7a3feb5a423a
									- Bot creation
									  https://slackhq.com/the-slack-platform-launch-7a3feb5a423a
										- https://medium.com/@guillegette/week-1-of-my-app-in-the-slack-app-directory-a310a9ebae8#.xbrq1sz73
								- _Related: _Project Management
								  #HabitLaboratory-Organisation https://workflowy.com/#/b3249da5c952
							- Twist
							  collapsed:: true
							  Every message has to be in a thread
								- https://twistapp.com
								- Using Twist with Todoist
								  intralink2:: https://workflowy.com/#/2fd192b99f3f
								  collapsed:: true
									- How to
									  https://twist.zendesk.com/hc/en-us/articles/115003991429-How-to-use-Twist-and-Todoist-together
									- Benefits of
									  https://twist.zendesk.com/hc/en-us/articles/115003654749-How-to-use-Twist-and-Todoist-together
									- Quick Add panel
									  http://i.imgur.com/gDB430o.png
										- Just type (or dictate) all the details into a single line. The smart Quick Add will automatically recognize and highlight each piece of information and add it to your task accordingly. Particularly handy when adding tasks on your mobile device.
										- https://support.todoist.com/hc/en-us/articles/115001745265-Task-Quick-Add
								- Pics
								  collapsed:: true
									- http://i.imgur.com/dlChBEZ.png
								- Pros/Cons
								  collapsed:: true
									- Pros
										- Threaded Channels - better organisation
										  intralink2:: https://workflowy.com/#/46331e4421bd
										- Thread view
										  http://i.imgur.com/UgLWSvq.png
										- Focus mode (turns off notifications and lets others know when you're back)
									- Cons
										- Few integrations
											- Integrations are better suited towards being analysed in batches though e.g. only visible via admin dashboard app
									- Unclear
										- _Asynchronous, no presence comments vs chat - _i.e. no presence/typing indicator
										- Anti-Slack
											- Asynchronous comments > real-time chat
												- As a team, we have decided that forum-style discussion is a better fit for us than synchronous chat. We are distributed across Medellin, San Francisco, New York, London and Barcelona. Our bodies are in different time zones and, due to a variety of sleeping schedules, so are our minds.
												- Nimble start-ups scoff at the lumbering email and meeting cultures of their more traditional counterparts. But the much trendier alternative — real-time group chat — is arguably even worse.
													- Meetings consume a (theoretically) bounded amount of time. Email can (again, theoretically) be closed and only checked at certain times. Group chat, on the other hand, maintains a more or less constant presence throughout the workday (and often before and after the workday as well). One study of the most popular business chat app Slack found that people spent an average of 10 hours a day in the app (that’s 67% more than the average spent on email).
												- As we saw earlier, each additional interruption, no matter how brief, comes at a price paid by companies and employees alike in lost productivity and increased stress. The pressures to be always available — in meetings and open offices, on email and group chat — create a harried culture of constant interruption rather than a sustainable culture of meaningful productivity.
											- No presence (online indicator)
												- The presence indicator has become something of an expectation for any team communication tool, a holdover from the days when productivity was measured by hours worked rather than work accomplished. But we felt that it would ruin the asynchronous nature of Twist:
												- If you see that a teammate is online, you expect an immediate response.
												- If you see someone is offline, you’re more likely to postpone sending a message because they probably won’t get back to you right away.
												- Without the presence indicator, our team has adapted to adding comments and sending messages whenever they need to. They have no way of knowing if the person is online, so they don’t expect an immediate response.
												- Conversations may happen more slowly, but more real work gets done since we don’t have to deal with constant distractions and context-switching that come with real-time messaging.
											- https://help.twistapp.com/hc/articles/115003654569
							- Flock
							  collapsed:: true
							  + task panel
								- Task panel (flat, no hierarchy)
								  http://i.imgur.com/Jo3w8HR.png
								- https://flock.com
							- Flowdock
							  collapsed:: true
							  Every message is an in-line thread
								- https://www.flowdock.com/
								- In-line view
								  https://cloud.githubusercontent.com/assets/6485697/10518739/ca8caa82-7330-11e5-8325-b80c1679b9e6.png
								- Click on icon to see thread view
								  https://cloud.githubusercontent.com/assets/6485697/10519020/d782e2a0-7331-11e5-83a0-0eabeba0e213.png
								- https://www.flowdock.com/help/chat
							- Glip
							  collapsed:: true
							  Slack-like with basic to-do list
								- Pros
								- Cons
									- Tasks only have two levels of hierarchy per channel
									- UI is very enterprise
								- Task creator
								  http://i.imgur.com/JHWnyei.png
								- Task area appears in the right pane
								  http://i.imgur.com/jN6MChU.png
								- Task page by clicking on the 'Tasks' in the right pane
								  http://i.imgur.com/ZuWcDRd.png
						- **Other Sorting Types**
							- GUI task creation from chat app
							  collapsed:: true
								- Project management bots + web app dashboard
								  intralink2:: https://workflowy.com/#/695ecc466268
								- _Task creation from chat_
									- Twist (to Todoist)
									  collapsed:: true
									  http://i.imgur.com/gDB430o.png | https://workflowy.com/#/65d472d1e2c0
										- Quick Add panel
										  http://i.imgur.com/gDB430o.png
											- Just type (or dictate) all the details into a single line. The smart Quick Add will automatically recognize and highlight each piece of information and add it to your task accordingly. Particularly handy when adding tasks on your mobile device.
											- https://support.todoist.com/hc/en-us/articles/115001745265-Task-Quick-Add
									- Flow (within Flow)
									  collapsed:: true
									  http://i.imgur.com/bx7Jop5.png | https://workflowy.com/#/1a1dcd0fb3bc
										- https://www.getflow.com/support/chat/creating-tasks-from-chat
								- _Task linking from chat_
									- Quip
									  intralink2:: https://workflowy.com/#/088e21db0d2c
								- _Task manager within chat _
									- Flock - side panel
									  collapsed:: true
									  http://i.imgur.com/Jo3w8HR.png |
										- Cons
											- Not context-specific enough
											- Task manager hierarchy is shallow
									- Glip
									  collapsed:: true
									  http://i.imgur.com/JHWnyei.png | https://workflowy.com/#/ca3ab8c93c91
										- Cons
											- Not context-specific enough
											- Task manager hierarchy is shallow
								- **APIs for interactivity**
									- ((646c8171-5cd2-46cb-8f97-28d8917a0461))
									  https://core.telegram.org/bots/2-0-intro
									- Mattermost
									  Working on message buttons, menus later https://mattermost.atlassian.net/browse/PLT-6403
									- Zulip
									  Suggested https://github.com/zulip/zulip/issues/6102
									- Hubot for Slack
									  In-progress https://github.com/slackapi/hubot-slack/issues/316#issuecomment-321667044
							- Threaded Channels
							  collapsed:: true
								- Pros
								  collapsed:: true
									- In these channels every message must be in a thread, and it makes conversations much more organised than a continuous stream of messages.
									- It's the modern version of forum, except you get the benefits of organisation and don't miss out on integrations, mentions, presence, bots etc.
									- Every message is a thread
									- Discussions become documentation
										- As new people join the company, they are diving into a lot of new topics and learning about how we work. It is easy to skim through a few hundred specific thread titles and dive into relevant discussions. It is much more daunting to trawl through thousands of messages in a few broad channels.
								- Twist
								  http://i.imgur.com/dlChBEZ.png
								- Zulip
								  http://i.imgur.com/ZaCsroJ.png | https://workflowy.com/#/56bf1ffabef3
								- Mattermost (proposed)
								  https://mattermost.uservoice.com/forums/306457-general/suggestions/20157766-build-a-thread-system-similar-to-twist
								- Riot (proposed)
								  https://github.com/vector-im/riot-web/issues/2349#issuecomment-321921360
								- Rocket.Chat (proposed
								  https://github.com/RocketChat/Rocket.Chat/issues/1112#issuecomment-321957347
							- Chat vs Comments
							  collapsed:: true
							  Easy to turn chat into "comments"
								- _Asynchronous, no presence comments vs chat _
								  i.e. online/offline status (presence), last seen time, typing indicator, read receipts
									- _Implementation_
									  collapsed:: true
										- Last seen time
										  https://telegram.org/blog/privacy-revolution
									- [Discourse](https://www.discourse.org)
									  id:: 663b24fb-1af7-40f4-a798-78e3f1990daf
									  collapsed:: true
										- Pros/Cons
											- Pros
												- Can be used as a knowledgebase by using a box subcategory style
												  collapsed:: true
													- http://i.imgur.com/sZID7uR.png
											- Cons
												- Unlike the threads+channels approach, it's difficult to
											- https://www.discourse.org/features
									- ((649b11eb-796e-4bb3-a608-09d98867166b))
									- Twist
									  intralink2:: https://workflowy.com/#/65d472d1e2c0
									- Gitea/Gogs
									- GitLab
									- GitHub
								- _Synchronous, real-time instant chat_
								- Related: Cactus Comments (Matrix-based comments)
							- Self-Hosted
							  collapsed:: true
								- IRC
								- XMPP server
								  intralink2:: https://workflowy.com/#/2c9e58aea033
								- Riot (Matrix servers)
							- Chat platforms encryption overview
							  https://www.eff.org/secure-messaging-scorecard
							- ((650aae19-56a4-43ed-b1dc-b3acd07ea36e))
			- Multi-chat app. FOSS but last updated Dec 2020
			  [https://github.com/ramboxapp/community-edition](https://github.com/ramboxapp/community-edition)
		- Audio/Video Chat (VoIP)
		  id:: 646c8171-0696-40f9-a644-bb14c67a1591
		  collapsed:: true
		  AKA Voice chat /
			- Integrated into other apps
			  collapsed:: true
				- Riot
				  STRP? for WebRTC
				- Wire
			- Connection types
			  collapsed:: true
				- P2P
				  collapsed:: true
					- Notes
						- Skype used to use P2P for lower latency until they lost a lawsuit
						- https://arstechnica.com/gadgets/2013/04/after-200m-patent-settlement-with-microsoft-virnetx-sues-for-more/
						- this is also why Apple stopped using P2P for Facetime
						- Probably one of two reasons.
						- 1. Control. They would control the medium, an thus have full control over the communication. Maybe even apply wiretapping if needed.
						- 2. Anonymity. P2P usually means that you know the address of the other participants, with a central server you don't get to know their address. Professionals might need this extra layer of protection.
						- it's easy to get someone's IP address then DDOS them with P2P systems
				- Server-based
				- P2P + server-based
				  collapsed:: true
					- See Signal
			- SIP/ZRTP-based
			  id:: 65d8a377-1017-4ae2-9daa-8ddf76668577
			  collapsed:: true
				- Free SIP providers, that support ZRTP (E2E encryption)
				  collapsed:: true
				  Ostel.co is good
					- Ostel
					  collapsed:: true
						- server provided by the Guardian Project, ostel.co
						- Based on Open Secure Telephony Network (OSTN) standards
							- OSTN is a de-facto standard by which a voice over internet protocol service can be considered end-to-end secured, with verifiable encryption, minimal logging, and a decentralized model of deployment and use. From this standard, we will work to deploy a network of compliant server/service instances and client software, mobile and desktop, that are federated, audited and interoperable.
							- https://dev.guardianproject.info/projects/ostn/wiki/Wiki
						- Phone calls with Ostel are end-to-end encrypted using ZRTP & SRTP.
						- The first step to make encrypted voice calls over OSTN is to sign up for a free account at ostel.co. The username you choose will be the name your friends enter when they want to call you.
					- Ekiga
					- Linphone
					  collapsed:: true
						- https://www.linphone.org/free-sip-service.html
				- Clients
				  collapsed:: true
				  Linphone for mobile; Jitsi for desktop
					- Mobile
						- CSipSimple for Android, GPL v3
						- Sipdroid for Android, GPL v3
						- Linphone for Android, BlackBerry, iPhone, Windows phone; GPL v2
					- PC
						- Jitsi, a Java VoIP for Android, Windows, Linux, Mac, FreeBSD
				- Note: Text chat isn't E2E encrypted
				- [Mobile-friendly Gateway to any SIP Provider](http://blog.jmp.chat/b/mobile-friendly-sip-gateway)
				  collapsed:: true
					- We have for a long time supported the public Cheogram SIP instance, which allows easy interaction between the federated Jabber network and the federated SIP network. When it comes to connecting to the phone network via a SIP provider, however, very few of these providers choose to interact with the federated SIP network at all. It has always been possible to work around this with a self-hosted PBX, but documentation on the best way to do this is scant. We have also heard from some that they would like hosting the gateway themselves to be easier, as increasingly people are familiar with Docker and not with other packaging formats. So, we have sponsored the development of a Docker packaging solution for the full Cheogram SIP solution, including an easy ability to connect to an unfederated SIP server
					- XMPP Server
					  collapsed:: true
						- First of all, in order to self-host a gateway speaking the XMPP protocol on one side, you’ll need an XMPP server. We suggest Prosody, which is already available from many operating systems. While a full Prosody self-hosting tutorial is out of scope here, the relevant configuration to add looks like this:
						- ```
						  Component "asterisk"
						    component_secret = "some random secret 1"
						    modules_disabled = { "s2s" }
						  Component "sip"
						    component_secret = "some random secret 2"
						    modules_disabled = { "s2s" }
						  ```
						- Note that, especially if you are going to set the gateway up with access to your private SIP account at some provider, you almost certaintly do not want either of these federated. So no DNS setup is needed, nor do the component names need to be real hostnames. The rest of this guide will assume you’ve used the names here.
						- If you don’t use Prosody, configuration for most other XMPP servers should be similar.
					- Run Docker Image
					  collapsed:: true
						- You’ll need to pull the Docker image:
						- `docker pull singpolyma/cheogram-sip:latest`
						- Then run it like this:
						- ```
						  docker run -d \
						    --network=host \
						    -e COMPONENT_DOMAIN=sip \
						    -e COMPONENT_SECRET="some random secret 2" \
						    -e ASTERISK_COMPONENT_DOMAIN=asterisk \
						    -e ASTERISK_COMPONENT_SECRET="some random secret 1" \
						    -e SIP_HOST=sip.yourprovider.example.com \
						    -e SIP_USER=your_sip_username \
						    -e SIP_PASSWORD=your_sip_password \
						    -e SIP_JID=your-jabber-id@yourdomain.example.com \
						    singpolyma/cheogram-sip:latest
						  ```
						- If you just want to connect with the federated SIP network, you can leave off the SIP_HOST, SIP_USER, SIP_PASSWORD, and SIP_JID. If you are using a private SIP provider for connecting to the phone network, then fill in those values with the connection information for your provider, and also your own Jabber ID so it knows where to send calls that come in to that SIP address.
					- Make a Call
						- You can now make a call to any federated SIP address at them\40theirdomain.example.com@sip and to any phone number at +15551234567@sip which wil route via your configured SIP provider.
						- You should even be able to use the dialler in Cheogram Android:
						  Cheogram Android Dialler
						  Cheogram Android Dialler
						- Inbound calls will route to your Jabber ID automatically as well.
					- What About SMS?
						- Cheogram SIP does have some basic support for SIP MESSAGE protocol, so if your provider has that it may work, but more testing and polish is needed since this is not a very common feature at providers we have tested with.
					- Where to Learn More
						- If you have any questions or feedback of any kind, don’t hesistate to stop by the project channel which you can get on the web or using your Jabber ID.
			- VoIP
			  id:: 65f9db9a-f844-44f2-b70d-cac8db463edb
			  collapsed:: true
			  AKA Virtual Phone Number
				- Pros/Cons
				  collapsed:: true
					- Pros
						- For 2-Factor Authentification via SMS if OpenOTP not possible (most websites)
						- Allows UK number to forward to whatever local number I'm using at the time
						- And for calling/receiving calls internationally if person doesn't have VoIP software
						- Use as a proxy number to give to girls
							- Prevents them from finding my identity
							- Also easier for me to hide my polyamorous lifestyle
						- VoIP > PSTN classic telephony
							- Most telephony networks willingly give data to Gov, store logs, aren't encrypted etc
							- As long as I'm using an encrypted protocol e.g. ZRTP
						- No ((649b13cd-0859-4c2f-8ad3-28bfe496eeba)) location tracking, because it's linked to a proprietary mobile app or open SIP client, rather than SIM/eSIM
					- Cons
						- Costs money
						- If self-hosted it's long to setup
						- Not a phone mumber available to individuals, and you can't use a PAC code to transfer it out
						- Many service providers like Google(?) keep a list of VoIP numbers so you're unable to sign-up for an account using one
				- # Providers
				  id:: 663b24fb-55d6-4ced-96e5-481e4cfc01d1
					- [PrivacyGuides recs](https://github.com/privacyguides/privacyguides.org/blob/0fbb53414b0b46ba11344e82ce24b0ec301004a7/docs/phone.md#voip-providers)
					  [Phone Service - Privacy Guides](https://deploy-preview-2099--privacyguides.netlify.app/en/phone/#voip-providers)
						- ### US numbers
							- [JMP.chat](https://jmp.chat/)
							  collapsed:: true
								- full VOIP functionality fulfilled over XMPP (so use any XMPP client e.g.
									- phone ([Conversations](https://conversations.im/) and <a href="https://siskin.im/">Siskin IM</a> are our recommended apps), <a href="https://mov.im">the web</a>, and <a href="https://gajim.org/">your computer</a>.
								- outgoing and incoming calls and texts
								- allows for anonymous signup. No email needed, no phone number needed, support for crypto, etc. And all for £2.99/mo
								- Recommended here
									- [Using VoIP for phone numbers is it actually worth it? - #7 by Unlimited0536 - Privacy - Privacy Guides](https://discuss.privacyguides.net/t/using-voip-for-phone-numbers-is-it-actually-worth-it/11321/7)
							- ((671d6a65-b702-4571-8dc1-175ba7601d6a))
						- [Hushed](http://hushed.com)
						  id:: 663b24fb-831b-448c-81fb-0a8407d24408
						  collapsed:: true
							- Virtual phone numbers bought online with bitcoin > ((663b24fb-831b-448c-81fb-0a8407d24408)) for anonymity
							- Rates
								- 1 year $30 - 500m talk time or 1100 SMS messages
								- $5 30-days worldwide $3 credit
								- $3 for 30 days UK number with $1 credit
								- http://hushed.com/rates/
							- Lifetime numbers
								- Should use outbound call or SMS at least once every 6 months to ensure the number stays active
								- Once a year, on the anniversary of the date you purchased your Lifetime Number, it will be replenishing with new credits for the following year.
					- Twilio
					- [VoIP.ms](http://VoIP.ms)
					- [virtualglobalphone.com](https://my.virtualglobalphone.com)
					  collapsed:: true
						- $4/month for UK mobile number + $4-14 setup
						- https://my.virtualglobalphone.com/cart.php?a=confproduct&i=0
					- [Grasshopper](http://grasshopper.com)
					  collapsed:: true
					  $12/month
						- http://grasshopper.com/competitors/
						- Grasshopper = $12/month
					- uReach
					- https://freeswitch.org/
					- These services offer virtual phone numbers (local or 800 numbers). They are aimed at small business users, and include features like voicemail and call redirection.
					  collapsed:: true
				- Related:
					- ((649b13c9-f664-4faf-ac1e-894243f5d6cd)) : ((6652f867-b1d6-47e0-8382-b6761c5b96c1))
			- Self-Hosted SIP Servers
			  collapsed:: true
				- https://prism-break.org/en/subcategories/ios-sip-servers/
					- Kamailio
					- Ostel
					  collapsed:: true
						- https://web.archive.org/web/20160427160749/https://dev.guardianproject.info/projects/ostel/wiki/Server_Documentation
					- FreeSWITCH
					- Asterisk (PBX)
					  collapsed:: true
						- http://www.asterisk.org/get-started
						- powers IP PBX systems, VoIP gateways, conference servers and other custom solutions
						- https://en.wikipedia.org/wiki/Asterisk_%28PBX%29#Derived_products
			- [https://en.wikipedia.org/wiki/Comparison_of_VoIP_software](https://en.wikipedia.org/wiki/Comparison_of_VoIP_software)
			- _By features_
				- Video conferencing
				  collapsed:: true
					- Jitsi Meet
					  id:: 663b24fb-70fe-47b1-8936-aec019e9e29c
					- [Zoom](https://zoom.us/)
					  id:: 63ad930f-a92d-46d6-9e35-054572f339c0
						- Cons
							- Limitations on Wayland
								- Can't screenshare?
						- Installing
							- `/home/boss/Documents/ESSENTIALS/Programs/zoom_amd64.deb`
							  id:: 63ada7d4-115c-4246-b867-a85317f29b42
								- [Installing or updating Zoom on Linux – Zoom Support](https://support.zoom.us/hc/en-us/articles/204206269-Installing-or-updating-Zoom-on-Linux#h_adcc0b66-b2f4-468b-bc7a-12c182f354b7)
							- Nix package instantly crashes [[2022-12-29 Thursday]]
				- Screensharing
				  collapsed:: true
					- Note: some apps have issues with screensharing with audio on Linux
					  id:: 663b24fb-7a2d-45e5-aa2b-8882fea439e3
					  collapsed:: true
						- Works (tested)
							- OBS
						- Works (untested)
							- [https://call.element.io/](https://call.element.io/) which will later be integrated into Element
							- Jitsi
							- ((646c8171-5cd2-46cb-8f97-28d8917a0461))
							- Steam Remote Play
							- [https://screego.net](https://screego.net)
						- Workarounds
							- Discord
							  collapsed:: true
								- Steps
									- Install Gamescope. Needed because some games when minimised or if you ALT+TAB out of them they'll stop being available as a screen for Discord
									  collapsed:: true
										- [Gamescope](https://github.com/Plagman/gamescope)
											- [[2024-09-11 Wednesday]] Need to build it manually since no packaging available. Can't be bothered for that incase there's missing dependencies
											- Use this PPA to install it
											  [[Launchpad is temporarily unavailable](https://launchpad.net/%7Ear-lex/+archive/ubuntu/gamescope](https://launchpad.net/%7Ear-lex/+archive/ubuntu/gamescope))
												- `sudo add-apt-repository ppa:ar-lex/gamescope`
												- `sudo apt update`
												- `sudo apt install gamescope`
									- Join a Discord call, open the Screen sharing dialog box
									- In Lutris RMB a game > Game Options > enable Gamescope. Needed for some WINE games like ((64e9e730-3133-4afb-a30f-e454885ba0a3)), which otherwise stop sharing with Discord once they're minimised or ALT+TAB
									- Meta + F to enable/disable fullscreen
									- In Discord start screen sharing. This will enable video, but not audio because Discord hasn't updated their Linux build to use newer Electron
									- Open PipeWire-Helvum Flatpak
									  collapsed:: true
										- For audio (with FreeTube Chromium as example):
											- Drag-and-drop Chromium `output_FL` to WebRTC VoiceEngine `input_FL`
											- Drag-and-drop Chromium `output_FR` to WebRTC VoiceEngine `input_FR`
								- Alternatively - see [OBS Studio (Open Broadcaster Software)](https://workflowy.com/#/a5712cb285c2). Add a Source for Screen Capture for the game window. Use Virtual Camera somehow?
								- [Learning Resources]
									- [https://teddit.net/r/linux_gaming/comments/vh32q9/how_do_game_nights_with_or_without_discord/](https://teddit.net/r/linux_gaming/comments/vh32q9/how_do_game_nights_with_or_without_discord/)
										- qpwgraph or soundux are decent patchbay alternatives to Helvum
								- {Archive}
									- Old method1
									  collapsed:: true
										- Setup
											- Use Chromium-based browser (Electron Discord desktop app can't screenshare on Wayland)
											- Install Violent Monkey
											- Install this userscript
											  [https://greasyfork.org/en/scripts/436013-screenshare-with-audio](https://greasyfork.org/en/scripts/436013-screenshare-with-audio)
											- Download this binary, make it executable and run it
											  [https://github.com/edisionnano/Screenshare-with-audio-on-Discord-with-Linux/blob/main/virtmic](https://github.com/edisionnano/Screenshare-with-audio-on-Discord-with-Linux/blob/main/virtmic)
												- e.g.
													- wget [https://github.com/edisionnano/Screenshare-with-audio-on-Discord-with-Linux/blob/main/virtmic?raw=true](https://github.com/edisionnano/Screenshare-with-audio-on-Discord-with-Linux/blob/main/virtmic?raw=true)
													- chmod +x virtmic
													- sudo mv virtmic /usr/local/bin
											- Then you can execute it simply by typing virtmic on a terminal and hitting enter. It will ask you for a node name, to learn the node name of the app you are trying to share simple run `pw-cli ls Node|grep [node.name](http://node.name)` while the app is running.
												- In KDE clicking on Audio Volume tray icon > Applications > will show the name of the app currently outputting audio
												- e.g. for FreeTube it will say "Chromium"
											- Once you do that simply start screensharing either your whole screen or a window and it will have sound.
										- Usage
											- Open Discord webapp in Chromium browser
											- Run the virtmic app and give it the node name of the app you want to share
											- Start screensharing
									- {Archive}
									  collapsed:: true
										- [https://github.com/edisionnano/Screenshare-with-audio-on-Discord-with-Linux](https://github.com/edisionnano/Screenshare-with-audio-on-Discord-with-Linux)
										- [https://teddit.zaggy.nl/r/linux_gaming/comments/ulz56n/proper_screensharing_with_sound_on_discord_now/](https://teddit.zaggy.nl/r/linux_gaming/comments/ulz56n/proper_screensharing_with_sound_on_discord_now/)
					- _Proprietary_
						- ((663b24fb-0338-4d42-8e5a-7febac0fe00a))
					- _FOSS_
						- ((631fa97e-a0a9-406c-b7b9-20536d421090))
						- ((6312a076-eb26-4bd5-a669-ea0a50d06668))
						- [Screego](https://screego.net)
						  collapsed:: true
							- [https://github.com/screego/server](https://github.com/screego/server)
					- ((663a5797-a9ea-4d4e-9619-01250a7ea8a6))
					- [DeskPad – A virtual monitor for screen sharing](https://github.com/Stengo/DeskPad)
						- [DeskPad – A virtual monitor for screen sharing | Hacker News](https://news.ycombinator.com/item?id=41800602)
					- Related: ((649b13cf-babf-4d83-8afd-576a1869a25a))
				- Livestreaming
				  id:: 65a64297-7396-40a9-9449-b9d753dd010a
				  collapsed:: true
					- ## Proprietary
						- [Twitch](https://twitch.com)
						  id:: 65aba1c8-74c9-4596-9694-91d8e7611101
							- FOSS frontend: ((65aba288-090d-4b44-9d4a-c2caef5f97ef))
								- Related: ((644c0b14-a86e-4504-b361-f7f262fd5549))
					- ## FOSS
						- [FFmpeg merges WebRTC support | Hacker News](https://news.ycombinator.com/item?id=44182186)
						- [Owncast](https://github.com/owncast/owncast)
						- [https://github.com/GRVYDEV/Project-Lightspeed](https://github.com/GRVYDEV/Project-Lightspeed)
						- Open Streaming Platform
							- [https://gitlab.com/Deamos/flask-nginx-rtmp-manager](https://gitlab.com/Deamos/flask-nginx-rtmp-manager)
							- [https://openstreamingplatform.com/](https://openstreamingplatform.com/)
						- ### + has public instances
							- ((649b1448-8048-4d27-b420-a748fe325b38))
							- Owncast
							  collapsed:: true
								- [https://github.com/owncast/owncast](https://github.com/owncast/owncast)
								- Instances
								  [https://directory.owncast.online/](https://directory.owncast.online/)
								- [https://owncast.online/](https://owncast.online/)
							- Satyr
							  collapsed:: true
								- [https://git.waldn.net/git/knotteye/satyr](https://git.waldn.net/git/knotteye/satyr)
								- Official instance
								  [https://spacecowboy.cc/](https://spacecowboy.cc/)
					- Watching
						- [Streamlink](https://github.com/streamlink/streamlink)
						  id:: 65a64297-7b1c-4484-b432-943d75e8059c
						  collapsed:: true
						  Can be used to watch streams via VLC or other app without going through ad-heavy, bloated websites like Twitch, YouTube etc
							- [Supported sites](https://streamlink.github.io/plugins.html#plugins)
							- [Streamlink Twitch GUI](https://github.com/streamlink/streamlink-twitch-gui)
							  id:: 65aba288-090d-4b44-9d4a-c2caef5f97ef
							  FOSS desktop frontend for ((65aba1c8-74c9-4596-9694-91d8e7611101)). GUI for ((65a64297-7b1c-4484-b432-943d75e8059c))
								- Pros/Cons
									- Pros
										-
									- Cons
										- [App is in maintenance mode due to tech debt](https://github.com/streamlink/streamlink-twitch-gui/issues/1015) - uses EmberJS, uses NW.js instead of Electron
											- Streamlink Twitch GUI is an [NW.js](https://github.com/nwjs/nw.js) application, which means that it is a web application written in JavaScript ([EmberJS](http://emberjs.com/)), HTML ([Handlebars](http://handlebarsjs.com/)) and CSS ([LessCSS](http://lesscss.org/)) and is being run by a [Node.js](https://nodejs.org) powered version of [Chromium](https://www.chromium.org/).
									- Unclear
									- Comparisons
								- Configuration for Flatpak VLC
									- player path to `flatpak` or `/usr/bin/flatpak`
									- custom args to `run org.videolan.VLC`
						- ((64e094cf-c072-4502-93c8-c3e2e9795fab))
					- Filecoin is needed to provide incentive layer for multimedia apps to scale
					  collapsed:: true
						- Filecoin is needed to provide incentive layer for multimedia
						  collapsed:: true
							- Federated alternatives like Mastodon have popped up but it's hard enough getting people to switch when it's free let alone a subscription model. To overcome the network effect, lock-in and status quo bias we need something more.
							- I think people en-masse will only have the incentive to switch when
								- 1) the platforms are peer-to-peer rather than just federated (e.g. IPFS or blockchain-based)
								- and 2) content creators and curators can earn good money for participating on the platform
							- Steemit, DTube and Yours are examples of this new wave of social media platforms (blockchain-based, allows P2P payments to content creators) but one feature holding it back is that multimedia (images, videos, audio etc) *can* be hosted by IPFS but there's no incentive layer yet to do so, which means there's not nearly as much content on it compared to YouTube or Imgur. The forthcoming solution to that is Filecoin which is launching next year.
							- Once that's working effectively we'll see much more content on the decentralised web. In the meantime you can still enjoy these platforms, just be aware that there's not a massive amount of content on there yet.
						- Sia, Storj etc already have storage + incentive layer, but IPFS is much further along in storage development
					- _Possible alternatives in future_
					  collapsed:: true
						- See [DLive](https://workflowy.com/#/ec89d3329213)
						- See [LBRY](https://workflowy.com/#/6cf2eff89d4e)
					- Incidents e.g. discussion with police, etc
					- Solutions
					  collapsed:: true
						- MistServer (also in use by DTube for livestreaming)
						  https://github.com/DDVTECH/mistserver
					- https://github.com/Teaonly/android-eye
					- https://github.com/spex66/RTSP-Camera-for-Android
					- https://github.com/hypeapps/Endoscope
					- https://github.com/nus-mtp/worldscope
					- Audio
					  collapsed:: true
						- https://coolmic.net/
					- https://github.com/Kickflip/kickflip-android-sdk
					- [https://github.com/ebu/awesome-broadcasting#audio-over-ip--streaming](https://github.com/ebu/awesome-broadcasting#audio-over-ip--streaming)
				- ((649b1407-55b9-422c-9a49-cbe295d8b257)) for multiplayer gaming
				- E2EE
					- Discord
					  collapsed:: true
						- This new feature applies to audio and video calls in direct messages (DMs), group DMs, voice channels, and Go Live streams, ensuring that even Discord cannot access the content of these conversations.
						- [GitHub - discord/dave-protocol: Whitepaper for Discord's Audio & Video End-to-End Encryption (DAVE) Protocol](https://github.com/discord/dave-protocol)
						- [GitHub - discord/libdave: Libraries supporting Discord's Audio & Video End-to-End Encryption (DAVE) protocol](https://github.com/discord/libdave)
						-
			- Ecosystem
			  collapsed:: true
				- Noise suppression
				  collapsed:: true
				  AKA echo cancellation
					- _Software_
						- Krisp
						  collapsed:: true
							- [https://krisp.ai/discord/](https://krisp.ai/discord/)
							- Doesn't support Linux
						- RTX Voice
						- RNNoise
						  collapsed:: true
							- [https://antlionaudio.com/blogs/news/free-active-noise-suppression-without-rtx-voice](https://antlionaudio.com/blogs/news/free-active-noise-suppression-without-rtx-voice)
						- Cadmus (uses werman's plugin)
						  collapsed:: true
							- A GUI frontend for [@werman](https://github.com/werman)'s Pulse Audio real-time noise suppression plugin
							- Werman's
							  [https://github.com/werman/noise-suppression-for-voice](https://github.com/werman/noise-suppression-for-voice)
							- GUI
							  [https://github.com/josh-richardson/cadmus](https://github.com/josh-richardson/cadmus)
							- Documentation
								- Download AppImage from GitHub Releases
								- Open PulseAudio Volume Control (or a similar PulseAudio frontend) from Kubuntu (or apt install pavucontrol)
									- Install Pulse Audio Volume Control (pavucontrol) and make sure under "Recording"
									- "Loopback to Cadmus Raw Microphone Redirect" records from your Mic (not from Cadmus Denoised Microphone)
									- "Remapped Stream" should use "Monitor of Cadmus Microphone Sink".
						- [https://github.com/werman/noise-suppression-for-voice#pipewire](https://github.com/werman/noise-suppression-for-voice#pipewire)
						- Noise Torch
						- EasyEffects and Helvum
						  collapsed:: true
							- [https://www.reddit.com/r/linux/comments/r1a2dz/helvum_and_easyeffects_two_great_applications_for/](https://www.reddit.com/r/linux/comments/r1a2dz/helvum_and_easyeffects_two_great_applications_for/)
					- 1 Backlink
						- After upgrading to Ubuntu 22.10 (PipeWire is default) or swapping to Fedora, setup PipeWire-compatible [Noise suppression](https://workflowy.com/#/5dbec5d330b1)
			- Related: ((649b13c9-f664-4faf-ac1e-894243f5d6cd))
		- **Analysis**
		  collapsed:: true
			- Encryption Protocols
			  collapsed:: true
				- OTR-Encrypted
					- Pros
						- Forward secrecy
						  collapsed:: true
							- Messages are only encrypted with temporary per-message AES keys, negotiated using the Diffie-Hellman key exchange protocol. The compromise of any long-lived cryptographic keys does not compromise any previous conversations, even if an attacker is in possession of ciphertexts.
						- Deniable authentication
						  collapsed:: true
							- Messages in a conversation do not have digital signatures, and after a conversation is complete, anyone is able to forge a message to appear to have come from one of the participants in the conversation, assuring that it is impossible to prove that a specific message came from a specific person. Within the conversation the recipient can be sure that a message is coming from the person they have identified.
					- Cons
						- Can't do group chat
						  collapsed:: true
							- Due to limitations of the protocol, OTR does not support multi-user group chat as of 2009[11] but it may be implemented in the future
							  source:: https://en.wikipedia.org/wiki/Off-the-Record_Messaging#Limitations
					- Apps
				- Axolotl protocol based
				  Forward secrecy and group chats
					- Signal Protocol
					  collapsed:: true
						- end-to-end encrypted group, text, picture, and video messages
						- Signal Protocol
							- (previously referred to as the Axolotl protocol[44]), which combines theDouble Ratchet Algorithm, prekeys, and a 3-DH handshake.[45] It uses Curve25519, AES-256, and HMAC-SHA256 as primitives.[46] The protocol provides confidentiality, integrity,authentication, participant consistency, destination validation, forward secrecy, backward secrecy (aka future secrecy), causality preservation, message unlinkability, message repudiation, participation repudiation, and asynchronicity.[47] It does not provide anonymity preservation, and requires servers for the relaying of messages and storing of public key material.[47]
						- The group chat protocol
							- is a combination of a pairwise double ratchet and multicast encryption.[47] In addition to the properties provided by the one-to-one protocol, the group chat protocol provides speaker consistency, out-of-order resilience, dropped message resilience, computational equality, trust equality, subgroup messaging, as well as contractible and expandable membership.
					- OMEMO/Olm
					  collapsed:: true
						- Extension to XMPP using Axolotl ratchet (OTR upgrade allowing group chats and forward secrecy)
						  https://en.m.wikipedia.org/wiki/OMEMO
						- I know this post was made a while ago, but the software ecosystem hasn’t been sitting idle and now we have open protocols such as OMEMO, based on the Axolotl double-ratchet (cryptocat uses it), which can run over federated/decentralised XMPP servers (i.e. recent versions of eJabberd, Prosody, etc.) and require no uploading of address books, no phone number for registration, and indeed can even be registered fairly anonymously over Tor.
						- So far, there’s a fairly stable Android client, Conversations, and a work-in-progress plugin for the cross-platform Gajim desktop client. Many other XMPP-compatible messaging clients and servers are being encouraged to adopt it, too.
						- XMPP
							- Regarding the XMPP attack surface, there are growing examples of how to implement XMPP properly and securely, that are nicely documented and tested at the links below. In short, servers should only allow OTR, should use full disk encryption, require TLS, support a Tor .onion service address, and disable all logging.
							- Otr.im: https://otr.im/chat.html
							- Calyx Institute: https://www.calyxinstitute.org
				- Deniable Authentication
					- https://www.praetorian.com/blog/an-opinionated-series-on-why-signal-protocol-is-well-designed-deniability
					- This is another layer of content protection on top of encryption. Kind of like steganography
					- All messages can be edited and faked except during an conversation
				- Post quantum cryptography
					- http://pqcrypto.org/index.html
					- https://www.whonix.org/wiki/PQCrypto
			- Quick contact method - use Session
			  Eg meetups
			- Recommendations (TL;DR)
			  collapsed:: true
				- Meetups or Groups
				  collapsed:: true
					- Riot once E2E on mobile
					  https://riot.im/app
					- or Signal for subpoena-resistant metadata
					- Later on use Ricochet mobile app or use ChatSecure with Tor hidden services for maximum anonymity.
				- https://www.rooshvforum.com/thread-55973.html
				- Chatroom vs forum
				  collapsed:: true
					- Forum pros
						- We need a forum, not a chatroom. Too many great ideas will be lost ~Suits
					- Chatroom Pros
						- Multiple problems with a forum format though. E.g. it requires paid hosting, regular system admin, you're not able to have end-to-end encryption, it discourages free-flowing conversation not strictly defined to a topic, needs a mass of users in order to become regularly active and useful
					- Ideal Riot changes
						- Threaded messaging
			- My goals for ideal software: confidentiality and anonymity.
			  collapsed:: true
				- Confidentiality
					- End-to-end encryption is necessary even if it's self-hosted, as servers can be compromised
				- Anonymity
					- You don't share your phone number
					- You can use a VPN to access the service
					- Ideally Tor can be used too for those who want full anonymity (which of course usually comes with decreased usability)
			- Have friends only able to reach me via certain methods
			  collapsed:: true
			  See local
				- Confidential (encrypted) medium like Riot
					- Matrix-powered web form?
					- If conversation requires
			- Comparison of many chat apps
			  collapsed:: true
				- Anonymity + Confidentiality  discount almost every mainstream instant messaging app.
					- WhatsApp isn't anonymous - it knows lots of metadata about you because it lacks Sealed Sender, ((663b24fb-4437-4115-83da-5f5b668989fc))
					- Another common suggestion is Slack, which can be anonymous but lacks confidentiality.
			- Best anonymous messaging tools
			  collapsed:: true
				- https://libreplanet.org/wiki/GNU/consensus/Secure_Messaging_Scoreboard#OK
					- >Tox looks like the only viable mobile one currently
				- http://youbroketheinternet.org/secure-email
					- I2P Bote only viable one but has scalability and social usability issues
				- http://youbroketheinternet.org/map
				- https://en.wikipedia.org/wiki/Anonymous_P2P#List_of_anonymous_P2P_networks_and_clients
			- Overview of potential metadata from mobile messengers
			  collapsed:: true
				- [source]
				  (archived) https://medium.com/@thegrugq/signal-intelligence-free-for-all-5993c2f72f90#.y46qursoz
				- Location
				  collapsed:: true
					- Specific location (home, place of work, etc.)
					- Mobility pattern (from home, via commuter route, to work) — very unique, just 4 locations is enough to identify 90% of people.
					  collapsed:: true
						- http://www.nature.com/articles/srep01376?ial=1
					- Paired mobility pattern with a known device (known as “mirroring”, when two or more devices travel together; including car telemetry!)
				- Network
				  collapsed:: true
					- Numbers dialed (who you call)
					- Calls received (who calls you)
					- Calling pattern (numbers dialed, for how long, how frequently)
					  collapsed:: true
						- https://en.wikipedia.org/wiki/Hemisphere_Project
						- http://www.slate.com/blogs/future_tense/2013/09/03/hemisphere_project_an_aclu_lawyer_on_the_troubling_database_used_to_id_burner.html
				- Physical
				  collapsed:: true
					- IMEI
					  id:: 62f388fb-d81f-4d3a-b11b-06c770dd2bb2
					  collapsed:: true
					  AKA International Mobile Equipment Identity
						- Pros/Cons
							- Cons
								- Illegal to change in some countries including the UK
									- ((63061153-6db2-4dcf-bffc-cab105ab529d)) - [Mobile Telephones (Re-programming) Act 2002](https://www.legislation.gov.uk/ukpga/2002/31/section/1)
									- India: Tampering with IMEI numbers is illegal under Section 25 of the Indian Telegraph Act, read with relevant rules and regulations issued by the Department of Telecommunications (DoT). There are significant penalties for doing so.
									- Pakistan: The Pakistan Telecommunication Authority (PTA) has strict regulations against IMEI tampering and cloning. It is illegal and actively enforced.
									- Turkey: Altering IMEI numbers is illegal under Turkish electronic communication laws. Devices with invalid or cloned IMEIs are blocked from networks.
						- # Documentation
							- The IMEI, these days, is a 15-digit number intended specifically to classify the device as unique. The number breaks down like this
							  collapsed:: true
								- **Issuing body:** The first two digits represent the 
								  issuing body, and are based on the country-code location of the 
								  manufacturer. If your phone was made in China (as my OnePlus 11 was), it
								  likely has an 86 up front, matching China’s country calling code. If it
								  was built internationally (say, an iPhone or Google Pixel device), it 
								  will generally start with a 35, which is unused as a country calling 
								  code. And if it was physically built in the Americas, it starts with an 
								  01, also matching its country calling code.
								- **[Type Allocation Code](https://www.gsma.com/solutions-and-impact/industry-services/device-services/tac-allocation):**
								  The next six digits in modern phones are treated as specific 
								  identifiers for the type of device you’re using, representing the serial
								  code for the device model. Despite the sheer number of gadgets being 
								  made each year, Smith says “we have not seen a massive increase in TAC 
								  being allocated.”
								- **Serial code:** The next six digits represent the 
								  exact device you’re using. As you may have determined by the use of 
								  math, each TAC number supports a million IMEI, says Smith. “We are 
								  seeing an increase in the volume of devices being sold, but not an 
								  increase in the number of models, meaning that TAC is now being more 
								  efficiently used,” he explained. “The same IoT model typically has more 
								  than one TAC as they make several million all the same.”
								- **Check digit:** The final digit is essentially used to
								  validate the prior 14 digits with an algorithm. Similar digits exist in
								  other types of identifier codes, such as the Universal Product Code 
								  (UPC) and the International Standard Book Number (ISBN). The algorithm 
								  that the mobile industry uses, the [Luhn algorithm](https://www.techtarget.com/searchsecurity/definition/LUHN-formula), is also used for social security numbers and credit card numbers.
							- `*#06#` **The code you type in** to the dialer of most phones if you want to see your IMEI number.
						- # Solutions
							- Meta
								- Some of these may only spoof IMEI to apps/OS but not to cellular towers
							- [Pixel (Tensor chip) IMEI modification guide](https://discuss.privacyguides.net/t/pixel-tensor-chip-imei-modification-guide/26295)
							  collapsed:: true
								- This guide covers Pixel 6, 6 Pro, 6a, 7, 7 Pro, 7a, Fold, 8, 8 Pro, 8a, 9, 9 Pro, 9 Pro XL, 9 Pro Fold, 9a
								- **A rooted device must be used to perform any actions. All changes will persist after a factory reset and bootloader lock, and this guide does not encourage you to have a rooted device as a daily driver. For educational and research purposes only**
								- _Background_  
								  Since the release of the Pixel 6 in 2021, Google has switched from Qualcomm to Samsung modems in their G-series Tensor SoCs. The modem’s codename is called “Shannon” and it is largely the same as used on Exynos devices.
								- For Google, Samsung added a few extra AT commands to interact with the modem, presumably for carrier testing and other regulatory requirements. A small subset of what was possible to send to it is documented here:
									- [GitHub - davwheat/shannon-pixel-modem-nvitem-enabler-scripts: Enable features which are disabled by default on Shannon-based Pixel phones.](https://github.com/davwheat/shannon-pixel-modem-nvitem-enabler-scripts)
									- [shannon-pixel-modem-nvitem-enabler-scripts-main.zip](../assets/shannon-pixel-modem-nvitem-enabler-scripts-main_1743499135223_0.zip)
								- Notice the AT+GOOGSETNV prefix, everything starts with AT+GOOG is Pixel specific on those modems. We will come to that later.
								- The IMEI, together with all other hardware identifiers is stored in a file called devinfo.
								  A simple parser in Python can be found here:
									- [GitHub - nullbytepl/pixel-devinfo-parser](https://github.com/nullbytepl/pixel-devinfo-parser)
									- [pixel-devinfo-parser-main.zip](../assets/pixel-devinfo-parser-main_1743499182487_0.zip)
								- _Steps_  
								  To get devinfo, we first need to get a root shell:
								- ```bash
								  adb shell
								  su
								  dd if=/dev/block/by-name/devinfo of=/sdcard/devinfo.img
								  adb pull /sdcard/devinfo.img
								  ```
								- From here, you can change the SKU of the device, for example to change the JP variant to US one, if for some reason you run the stock OS and wan’t to avoid the camera shutter sound. But we are here for the more interesting values.
								- We now need to find the original IMEI string in our devinfo, and modify it with a hex editor.  
								  Make sure to not just enter random numbers there but from a device you legally own. This way you make sure that you don’t break the law as well as not looking suspicious from the carrier side.
								- ```bash
								  adb push ./devinfo_modified.img /sdcard/
								  adb shell
								  su
								  dd if=/sdcard/devinfo_modified.img of=/dev/block/by-name/devinfo
								  exit
								  adb reboot bootloader
								  fastboot oem set_config bootmode factory
								  fastboot reboot
								  ```
								- You will see a red screen from the bootloader saying the phone is booted in factory mode.  
								  We now have to recalculate the SHA hashes of the new IMEI values. For that, we execute:
									- `echo “AT+GOOGGETIMEISHA\r” > /dev/umts_router & cat /dev/umts_router`
								- You will see a SHA256 string in a response, i.e:
									- `+GOOGGETIMEISHA:494b450c0a1f5af2ce470010fc0e33cb4917083839b7add4cf9d100c8bad17b7`
								- Copy that string to `/mnt/vendor/persist/modem/cpsha`, that’s our new IMEI verification hash:
									- ```
									  echo 494b450c0a1f5af2ce470010fc0e33cb4917083839b7add4cf9d100c8bad17b7 > /mnt/vendor/persist/modem/cpsha
									  echo 'AT+GOOGBACKUPNV\r' > /dev/umts_router
									  ```
								- Now we saved the backup to EFS as well, although it is not necessary.
									- ```
									  reboot bootloader
									  fastboot oem rm_config bootmode
									  fastboot reboot
									  ```
								- You should have your IMEI changed, and now it’s safe to do a factory reset and lock the bootloader back.  
								  If you have a carrier that supports displaying your current connected IMEI online, you can use it to verify everything went well. But if you see it in `*#06#` it will be enough, the baseband reads it from devinfo.
								- _P.S._  
								  There is a nice FOSS utility that kind of automates what I described here
							- qualcomm-smartphone-write-imei-tool
							  collapsed:: true
								- [Qualcomm_Smartphone_Write_IMEI_Tool_v1.01.zip](../assets/Qualcomm_Smartphone_Write_IMEI_Tool_v1.01_1660295513773_0.zip)
									- [Guide](https://forum.xda-developers.com/t/guide-repair-imei-on-qualcomm-snapdragon-devices.4427589/) | SingleFile [[GUIDE] Repair IMEI on Qualcomm Snapdragon Devices _ XDA Forums (8_12_2022 9_13_41 AM).html](../assets/[GUIDE]_Repair_IMEI_on_Qualcomm_Snapdragon_Devices_XDA_Forums_(8_12_2022_9_13_41_AM)_1660295920861_0.html)
										- [qualcomm driver.zip](../assets/qualcomm_driver_1660295570335_0.zip)
								- [Qualcomm Product Support Tools - QPST.7z](../assets/Qualcomm_Product_Support_Tools_-_QPST_1660293736146_0.7z)
									- [Guide](https://forum.xda-developers.com/t/guide-backup-edit-and-restore-qcn-fixing-lost-imei.4101611/) | [SingleFile] [[GUIDE] Backup, edit and restore QCN. Fixing lost IMEI. _ XDA Forums (8_12_2022 8_44_08 AM)(1).html](../assets/[GUIDE]_Backup,_edit_and_restore_QCN._Fixing_lost_IMEI._XDA_Forums_(8_12_2022_8_44_08_AM)(1)_1660294074479_0.html)
									- [Guide2](https://forum.xda-developers.com/t/unbrick-recover-imei-unbrick-hardbricked-max-pro-m1-and-recover-imei-qfil.3829754/)
									  collapsed:: true
										- Full post
											- This thread is for those who's phone is hard bricked ( not even going to
											   fast boot or recovery ). here we will explain how you can revive it.
											- things you need :-
											  1. QPST Tool - [QPST Tool](https://drive.google.com/file/d/10bYXNYgMIQxSaPXQMfA4yOoD88n-57w_/view)
											  2. QFIL Rom - ZB601KL/ZB602KL [Download from HERE](https://drive.google.com/drive/folders/1gA2MQPoYmPvbo3h5GiKVlA7q-L18k8Up?usp=sharing)
											  3. Qcom drivers - [Qcom drivers](https://drive.google.com/file/d/1z0pA9RvEsuD5b6g-PScszkr4zNPsa7Tx/view?usp=sharing)
											- First of all install QPST tool and drivers and extract QFIL rom after that go to QPST installed folder in my case that was C:\Program Files\Qualcomm\QPST\bin
											- open QFIL.exe
											- In Build type Select Flat Build
											- in Select Programmer go to that folder where u extracted Qfil rom.zip and select prog_emmc_ufs_firehose_Sdm660_ddr.elf
											- Now Click on Load xml  and select rawprogram_unsparse_ww.xml in next window select patch0.xml
											- .
											- >
											-
											- [SCREENSHOTS](https://drive.google.com/drive/folders/1loEg79baQaOfnlccA9rB2w414mCDUdKy?usp=sharing)
											-
											- now Connect your device now if you see Something else like Qualcomm 
											  HS-USB Diagnostics in place of no port Selected Click DownLoad else 
											  check drivers.
											- it will take some time after process completes you can boot your phone 
											  and this rom is not meant for daily uses so flash any fastboot rom now.
											- **Backing Up IMEI (QCN) ?**
											-
											-
											-
											- things you need :-
											  1. QPST Tool - [QPST Tool](https://drive.google.com/file/d/10bYXNYgMIQxSaPXQMfA4yOoD88n-57w_/view)
											  2. Qcom drivers - [Qcom drivers
											- ](https://drive.google.com/file/d/1z0pA9RvEsuD5b6g-PScszkr4zNPsa7Tx/view?usp=sharing)
											- Steps :
											- 1. You should be on rooted stock rom. and Qcom drivers & QPST Tool installed on your pc.
											- 2. Add ro.build.selinux=0 and sys.usb.config=diag,adb to build.prop now reboot.
											- 3. connect your phone to pc and open Qfil select tools > QCN Backup Restore from menu bar. Click Backup in next window.
											- Done..
											- Note : if you see No Port Available in QFIL check drivers or step 2.
											-
											- **
											- Restoring IMEI (QCN)**
											-
											-
											-
											- things you need :-
											  1. QPST Tool - [QPST Tool](https://drive.google.com/file/d/10bYXNYgMIQxSaPXQMfA4yOoD88n-57w_/view)
											  2. Qcom drivers - [Qcom drivers
											- ](https://drive.google.com/file/d/1z0pA9RvEsuD5b6g-PScszkr4zNPsa7Tx/view?usp=sharing)
											- Steps :
											- 1. You should be on rooted stock rom. and Qcom drivers & QPST Tool installed on your pc.
											- 2. Add ro.build.selinux=0 and sys.usb.config=diag,adb to build.prop now reboot.
											- 3. connect your phone to pc and open Qfil select tools > QCN Backup Restore from menu bar.
											- 4. Choose your QCN file and Click Restore in next window.
											- Done..
											- Note : if you see No Port Available in QFIL check drivers or step 2.
											-
											- **Editing QCN File : **
											-
											-
											-
											- things you need :-
											  IMEI to HEX Converter - [https://drive.google.com/file/d/1spyz5bpeSY1NBu1IZGQlLZersARG5EKR/view?usp=sharing](https://drive.google.com/file/d/1spyz5bpeSY1NBu1IZGQlLZersARG5EKR/view?usp=sharing)
											  HEx Editer - download ultra Edit (Do Google search)
											- 1. Open QCN file with ultra Edit click find and search for old imei(hex use hex converter).
											- 2. replace with new hex do for both imei and save.
											- done now you can restore.
							- Certain chipsets, such as Mediatek, make cloning IMEI, WiFi and BT MAC addresses quite easy. There's plenty of tutorials out there.
							- Mudi v2 router with Blue Merle
								- [GitHub - srlabs/blue-merle: The blue-merle package enhances anonymity and reduces forensic traceability of the GL-E750 Mudi 4G mobile wi-fi router](https://github.com/srlabs/blue-merle)
								  collapsed:: true
									- [Example IMEI changer code](https://github.com/srlabs/blue-merle)
									  `/home/boss/Documents/Git/Other/blue-merle`
							- Edit QCN file
							  collapsed:: true
								- IMEI to HEX converter
								- Open QCN file with a hex editor
								  collapsed:: true
									- [UltraEdit](https://www.ultraedit.com/)
									- https://alternativeto.net/feature/hex-editor/?license=opensource
								- use IMEI to HEX converter to find the current IMEI to search for, and new IMEI to add
								  collapsed:: true
									- [CellSerialConverter.py](https://github.com/jeffgolden/CellSerialConverter)
										- This is just a collection of simple functions to convert cellular serial numbers from one format to another. The function translate_serial will take any format (ESN, HEX ESN, MEID or IMEI) and convert to all other appropriate formats.
										- ```python
										  
										  # Converts Hex/Dec provided serial numbers to other formats
										  import re
										  import collections
										  
										  Translation_Result = collections.namedtuple('Translation_Result',
										                                              'source_serial dec_val hex_val imei_val success has_imei')
										  
										  
										  def hex_to_dec(hex_serial):
										      """Convert a given hexadecimal serial number to decimal format.  Serial numbers must be
										         valid hexadecimal values and be of length 14 or 18"""
										      hex_serial = hex_serial.upper()
										      if re.match("^[A-Fa-f0-9]+$", hex_serial) is None:
										          return ""
										  
										      if len(hex_serial) == 14:
										          left = hex_serial[:8]
										          right = hex_serial[8:]
										          left_dec_int = int(left, 16)
										          right_dec_int = int(right, 16)
										  
										          output = str(left_dec_int).rjust(10, "0") + str(right_dec_int).rjust(8, "0")
										  
										      elif len(hex_serial) == 8:
										          left = hex_serial[:2]
										          right = hex_serial[2:]
										  
										          left_dec_int = int(left, 16)
										          right_dec_int = int(right, 16)
										  
										          output = str(left_dec_int).rjust(3, "0") + str(right_dec_int).rjust(8, "0")
										  
										      else:
										          return ""
										  
										      return output
										  
										  
										  def dec_to_hex(dec_serial):
										      """Convert a given decimal serial number to hexadecimal format.  Serial numbers must be numeric
										      and either 18 or 11 digits."""
										  
										      if re.match("^[0-9]+$", dec_serial) is None:
										          return ""
										  
										      if len(dec_serial) == 18:
										          left = int(dec_serial[:10])
										          right = int(dec_serial[10:])
										          hex_left = hex(left)
										          hex_right = hex(right)
										  
										          output = str(hex_left)[2:10] + str(hex_right)[2:].rjust(6, "0")
										      elif len(dec_serial) == 11:
										          left = int(dec_serial[:3])
										          right = int(dec_serial[3:])
										  
										          hex_left = hex(left)
										          hex_right = hex(right)
										  
										          output = str(hex_left)[2:] + str(hex_right).rjust(7, "0")[2:]
										      else:
										          return ""
										  
										      return output.upper()
										  
										  
										  def calc_check_digit(meid):
										      """
										      Calculate the check digit for a given meid.  meid must be numeric and 14 digits.
										      """
										      multiplier = 2
										      sum_val = 0
										      for c in reversed(meid):
										          current = int(c) * multiplier
										          sum_val = sum_val + int(current / 10) + current % 10
										          multiplier = 1 if multiplier == 2 else 2
										      check = 0 if sum_val % 10 == 0 else 10 - sum_val % 10
										      return check
										  
										  
										  def get_imei(meid):
										      """
										      Return the IMEI for a given meid.  MEID must be valid containing 14 numeric digits.
										      """
										      if re.match("^[0-9]+$", meid) is None:
										          return ""
										      return meid + str(calc_check_digit(meid))
										  
										  
										  def translate_serial(serial):
										      """
										      For a given serial return a named tuple containing the source serial (provided),
										      the decimal version (if valid), the hexadecimal version (if valid), the imei (if valid
										      and applicable to the given serial number) and flags for successful conversion and indicating if
										      the given serial has an imei.
										      """
										      serial = serial.upper()
										      source_serial = serial
										      if len(serial) == 15:
										          serial = serial[:14]
										  
										      dec_val = ""
										      hex_val = ""
										  
										      if len(serial) in (18, 11) and str(serial).isnumeric():
										          dec_val = serial
										          hex_val = dec_to_hex(serial)
										      elif len(serial) in (14, 8):
										          dec_val = hex_to_dec(serial)
										          hex_val = serial
										  
										      if dec_val == "" or hex_val == "":
										          dec_val = ""
										          hex_val = ""
										  
										      if len(hex_val) == 14:
										          imei_val = get_imei(hex_val)
										      else:
										          imei_val = ""
										  
										      return Translation_Result(source_serial=source_serial, dec_val=dec_val, hex_val=hex_val, imei_val=imei_val,
										                                success=True if dec_val != "" else False, has_imei=True if imei_val != "" else False)
										  
										  
										  if __name__ == '__main__':
										      print(translate_serial("111111111111111111"))
										  ```
								- Search file for IMEI number ( )
							- [Learning Resources]
							  collapsed:: true
								- [Log in | XDA Forums](https://forum.xda-developers.com/search/46073151/?q=restore+imei&o=relevance)
								- Illegal to change in most places eg UK also it's illegal to possess equipment to change it
								- While the area that the IMEI number is stored on is protected on most phones, many Samsung devices have it saved on the EFS partition, which is easily accessible with a rooted phone. That’s why there are chances that while flashing a ROM to your device, you might end up messing up the EFS partition and thus losing your IMEI number.
								- It is used by your Network to identify the following/it's made up of 5 parts:
									- 1) The first two numbers is RBI (Reporting Body Identifier) = who registered that type of phone ( verify here )
									- 2) The next four numbers is TAC (Type Allocation Code) = what type of unit and its complete specifications
									- 3) The next two numbers is FAC (Final Assembly Code) = who manufacture it
										- example :-
										- 01 AEG
										- 04 Samsung
										- 07 Motorola
										- 10 Nokia
										- 30 Ericsson
										- 41 Siemens
										- 50 Bosch
										- 51 Sony
									- 4) The next six numbers is the Serial Number of the Phone
									- 5) The last number is sort of a check sum, that verifies the previous numbers
									- Combined a total of 15 numbers is used by your network to get the complete information about your phone that is used against their database of Blacklisted phones and final approval to connect to their network, IF they were inaccurate or had complaints (like being stolen, not paid telecoms dues etc) it will be rejected and BLOCKED immediately from connecting to that Network
									- http://forum.xda-developers.com/showthread.php?t=1857054
						- {Archive}
							- [Answering Every Question You Have About IMEI Numbers](https://tedium.co/2024/04/27/mobile-phone-imei-number-history/)
					- International Mobile Subscriber Identity (IMSI)
					  collapsed:: true
						- Cons
							-
						- How to anonymise
						-
						- [Apps like XPrivacy can only spoof them to other apps, not to the telecom network](https://github.com/M66B/XPrivacy/issues/690)
						- Related: ((62f55393-cfe7-4bd5-8986-88ab1ab875ec))
					- {Archive}
						- [Mobile equipment identifier (MEID)](https://en.wikipedia.org/wiki/Mobile_equipment_identifier) - CDMA2000 only
						- Electronic serial numbers (ESNs) - deprecated, no more numbers
				- Content
				  collapsed:: true
					- Identifiers, e.g. names, locations
					- Voice fingerprinting
					- Keywords
				- In addition to all that metadata, there is additional metadata that is created by the Signal app itself.
			- Future: post-quantum crypto (necessary for decentralised web)
			  intralink2:: https://workflowy.com/#/841df8456316
		- _{Archive}_
		- Related:
			- _Pastebins_
				- [Self-destructing encrypted pastebin](https://privatebin.net/)
				  collapsed:: true
					- https://privatebin.net/
					  See markdown in sub bullets
						- https://docs.mattermost.com/help/messaging/formatting-text.html
						- https://en.support.wordpress.com/markdown-quick-reference/
				- Anonymous pastebin
				  collapsed:: true
					- BitText
						- http://bittext.ch/
						- http://bittexttizfec375.onion/
						- https://bitmessage.org/forum/index.php/topic,3237.0.html - can't seem to access their onion site
					- http://pastethis.i2p/
					- http://zerobin.i2p/
					- I2P pastebin
					  http://erkqiwnjl7vtysqd3wvddv6tfvnhswarqkbn4blhdlhfxn7cf2ha.b32.i2p/
			- ((64463cc6-cedb-4d60-9227-fed03b619a00))
			- ((64463cc5-2aa5-4916-8686-c3f6d3c46a08)) : ((64463cc5-a732-4069-9ccd-d28adb8da813))
			- ((630f9531-1efc-4743-8838-deac07e3442d))
	- Email
	  id:: 663b24fb-d9cc-4bff-b533-9c9cedc07adb
	  collapsed:: true
	  #Email
		- Pros/Cons
		  collapsed:: true
			- Pros
			- Cons
				- Many unfixable problems
					- _PGP cons_
					  collapsed:: true
						- PGP is complicated
						- PGP screams 'suspect'
							- Though Tor + PGP is fairly private
						- Encryption breaks search / Indexing hurts security
						- Not perfect-forward (access to the key means access to all previous emails)
						- Key handling would be a nightmare
					- _Metadata leaks_
					  collapsed:: true
						- Servers involved
						  See Signal Sealed Sender
						- People's names and email address
						  See Signal Encrypted Profiles
						- Subject header
						- etc etc
					- Many unfixable problems
					- No E2EE
					  collapsed:: true
						- What's missing is end to end encryption. That's a challenging thing to overcome, however, because aside from there needing to be a standard everyone can agree on, you also end up with key storage complexities and the loss of server side email intelligence, like Gmail's search and Inbox's ability to group similar email. And that's without even touching in spam filtering.
					- Don't ever put in an email what you wouldn't put on a postcard and put in a mailbox
				- Unclear
					- [Email Security: Where We Are and What the Future Holds - Privacy Guides](https://www.privacyguides.org/articles/2025/11/15/email-security/)
		- Using Email
			- My System
			  collapsed:: true
				- Currently
					- See [AnonAddy](https://workflowy.com/#/bc84369206bc) for disposable emails
					- Hostgator for multiple domains
					  collapsed:: true
						- David 3 domains
						- My 3 domains
							- aaronsollesse.com
							- sollesse.com
							- [spinningatoms.com](http://spinningatoms.com) (email on <a href="http://mail.spinningatoms.com">mail.spinningatoms.com</a>)
					- Web hosting alternatives
					  collapsed:: true
						- Bluehost - $17/month with monthly contract
						  [https://www.bluehost.com/help/article/shared-hosting-prices](https://www.bluehost.com/help/article/shared-hosting-prices)
					- See [Mailbox.org](https://workflowy.com/#/8966f5381e94) (3 euros/month)
				- How it could be improved
					- Planned
					- 48 €/year for [ProtonMail](https://workflowy.com/#/01273b20f090) - Bridge for Thunderbird,
					- New AnonAddy account with less links to personal ID
					  collapsed:: true
						- 1) Pay with cryptocurrency not debit card
						- 2) Forward emails to a non-identity linked email address eg admin@spinningatoms.com
						- 3) Only have mail subdomain pointed to AnonAddy, host the main domain MX with ProtonMail or similar
						- 4) Ideally use a privately registered rather than Namecheap eg Njalla
				- 1 Backlink
					- See [My System](https://workflowy.com/#/4ccbb6c23a12)
					  #Email
			- _IMAP / POP3 / SMTP Email_
			  collapsed:: true
				- Pros/Cons
				  collapsed:: true
					- Pros
						- Unlike DNS there is TLS so only the receiver can read data
					- Cons
						- Most email providers don't offer encryption of email at rest
						  collapsed:: true
							- Offers encryption of email at rest (though theoretically can read whatever email you receive in transit)
						- Client-side encryption isn't offered by most providers
						  collapsed:: true
							- ((663b24fb-febe-4b1e-888c-4e7dcb6a3ab4)), Protonmail
								- If the receiver is using the service too then messages will be sent E2EE
							- Email E2E made easy with ProtonMail - recipient doesn't even need an account
								- You're mostly right. ProtonMail has a feature that you can force the other user to reply using encryption. It sends them a generic email with a link to ProtonMail's portal where they can reply to your message.
							- Even Protonmail etc rely mainly on Javascript encryption
							- they also have E2E with Thunderbird via ProtonMail Bridge
						- Not anonymous (still metadata)
						  collapsed:: true
							- p≡p is aiming to have this for emails sent to other p≡p participants
							- Anonymous email to/from legacy SMTP
							  https://github.com/DevanaLabs/lemon.email-dApp
								- Would have to hit some sort of gateway that then translates emails into an encrypted hash for blockchain storage
							- Email alternatives (P2P asynchronous messaging)
							  #EncryptedChat https://workflowy.com/#/c3eaed240dce
				- SOPs
				  collapsed:: true
					- Which email provider to choose
						- Either
							- Web hosting
							  collapsed:: true
								- Pros/Cons
									- Pros
										- Only need to setup nameservers for each newly purchased domain. Then can create loads of email accounts from within cPanel
									- Cons
										- Some providers like Hostgator have disabled catch-all addresses
										- Not all have 2FA (like Hostgator)
							- Dedicated email provider
							  collapsed:: true
								- Pros/Cons
									- Pros
									- Cons
										- It's technical - requires pointing multiple DNS records including TXT, MX, SPF, DMARC
										- Expensive - 3 euros/month for [Mailbox.org](https://workflowy.com/#/8966f5381e94) with 50 aliases is pretty decent
					- How to move providers
						- TXT record to verify ownership
						- MX records to deliver email
						- Extra TXT records
							- DMARC
							- SPF
				- Hosted Email
				  collapsed:: true
					- _My system_
						- See [Mailbox.org](https://workflowy.com/#/8966f5381e94)
					- _Inbox IMAP/POP3_
						- Hosted providers
							- _Free email _
								- Gmail
								  collapsed:: true
									- Buy a legacy G Suite via eBay for unlimited users
								- Microsoft Exchange
								  collapsed:: true
									- Exchange Online
									  https://products.office.com/en-us/exchange/compare-microsoft-exchange-online-plans
								- Fastmail
								  collapsed:: true
									- [https://www.fastmail.com/pricing/](https://www.fastmail.com/pricing/)
								- _Allows free hosting using your own domain_
								  collapsed:: true
									- Zoho Mail
									  collapsed:: true
										- Zoho Mail - up to 25 email addresses for free
										  https://www.zoho.eu/workplace/pricing.html?src=zmail
									- BigRock
									  collapsed:: true
										- [https://www.bigrock.in/](https://www.bigrock.in/)
									- AT Mail
									  collapsed:: true
										- [https://www.atmail.com](https://www.atmail.com)
							- _No Freemium_
								- AWS WorkMail
									- https://aws.amazon.com/workmail/pricing/
					- _Outbox - mass SMTP_
						- Hosted providers
							- Mailgun
							- Amazon SES
							- Sendgrid
					- By type
						- Privacy-conscious email service providers
						  collapsed:: true
							- ProtonMail
							  collapsed:: true
							  id:: 62f388fb-0af9-46e5-9796-0d7a52d86901
								- Pros/Cons
								  collapsed:: true
									- Pros
										- Data is encrypted-at-rest with client-side encryption
										  [https://protonmail.com/blog/zero-access-encryption/](https://protonmail.com/blog/zero-access-encryption/)
										- Has an onion site
											- [https://protonmail.com/tor](https://protonmail.com/tor)
											- [https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion/](https://protonmailrmez3lotccipshtkleegetolb73fuirgj7r4o4vfu7ozyd.onion/)
										- Can sync with 3rd-party clients like Thunderbird (i.e. IMAP support), unlike ((62f388fb-0af9-46e5-9796-0d7a52d86901))
										- Doesn't support CalDAV or CardDAV for syncing with mobile apps (or desktop like Thunderbird)
											- https://teddit.httpjames.space/r/ProtonMail/comments/v3zycc/please_expand_the_bridge_to_also_sync_all/
									- Cons
										- Uses Google ReCaptcha currently
										  [https://github.com/ProtonMail/WebClient/issues/242#issuecomment-851066019](https://github.com/ProtonMail/WebClient/issues/242#issuecomment-851066019)
										- They complied with Swiss authorities demands to record the IP address of a customer, and the customer was subsequently arrested
										  [https://news.ycombinator.com/item?id=28427259#28427996](https://news.ycombinator.com/item?id=28427259#28427996)
								- ProtonMail Bridge
								  collapsed:: true
									- [https://protonmail.com/bridge/](https://protonmail.com/bridge/)
							- [Tuta](https://tuta.com)
							  id:: 663b24fb-febe-4b1e-888c-4e7dcb6a3ab4
							  collapsed:: true
							  AKA formerly Tutanota
								- Pros/Cons
									- Pros
										- Tutanota is one of the few mail providers that encrypts the entire mailbox. The encrypted data can't be decrypted by us as only the user holds the key for decryption.
										-
									- Cons
										- [German court ruling requires Tutanota to hand out newly incoming and outgoing non-encrypted emails of one suspected criminal before these are being encrypted.](https://www.cyberscoop.com/germany-court-ruling-tutanota-email-monitoring)
											- [Disucssion](https://old.reddit.com/r/privacytoolsIO/comments/ka3gn1/german_court_forces_encrypted_email_provider)
										- Doesn't use standard PGPP for E2EE, unlike ((62f388fb-0af9-46e5-9796-0d7a52d86901))?
										- Can't sync with 3rd-party clients like Thunderbird (i.e. no IMAP support), unlike unlike ((62f388fb-0af9-46e5-9796-0d7a52d86901))
								- Comparisons
									- ((4ff846fb-2c2c-4b4c-b76a-630ce7268653))
								- [Tuta Calendar | F-Droid - Free and Open Source Android App Repository](https://f-droid.org/en/packages/de.tutao.calendar/)
								- [Tuta Mail | F-Droid - Free and Open Source Android App Repository](https://f-droid.org/en/packages/de.tutao.tutanota/)
								-
								- Related: ((62e910bc-363c-4fe1-827d-91d75fcc1afa))
							- [Mailbox.org](https://mailbox.org)
							  id:: 65f9db9a-2519-4d8c-a6d6-92120670aa63
							  collapsed:: true
								- Pros/Cons
									- Pros
										- [2FA but not the most user-friendly implementation](https://kb.mailbox.org/display/MBOKBEN/How+to+use+two-factor+authentication+-+2FA)
										- [PGP encryption at rest ("zero access encryption")](https://kb.mailbox.org/display/MBOKBEN/The+Encrypted+Mailbox)
										  id:: 65f9db9a-d4c8-4af7-9882-7d65b004e22d
										- [Catch-all addresses](https://kb.mailbox.org/display/MBOKBEN/Using+catch-all+alias+with+own+domain)
									- Cons
										- Lacks
											- [IMAP/SMTP on devices via app passords](https://userforum-en.mailbox.org/topic/1522-will-mailbox-org-implement-app-passwords-someday#comment-4146)
									- Unclear
										- Uses aliases for all additional emails
											- Pros/Cons
												- Pros
													- [Supports many custom domains](https://kb.mailbox.org/display/MBOKBEN/Using+e-mail+addresses+of+your+domain)
													- It allows them to offer support for 25 email addresses including custom domains for cheap
												- Cons
													- It's a unified inbox on mobile and webmail (but can be circumvented via ((6312a075-ceb2-4a57-adc5-2a27f91e865c)) message filters for desktop)
														- Meta
															- ((65f9db9a-d4c8-4af7-9882-7d65b004e22d)) isn't affected on the emails you move into a folder
														- **Create Message Filters**:
															- Go to "Tools" in the menu bar and select "Message Filters."
															- Click on "New" to create a new filter.
														- **Set Filter Conditions**:
															- In the "Filter Name" field, enter a name for your filter (e.g., Alias 1 Inbox).
															- In the "Match all of the following" section, set conditions based on the email alias you want to filter. For example, you can set the condition "From" "contains" "your_alias@example.com".
											- [https://github.com/Welpy-cw/Folder-Account](https://github.com/Welpy-cw/Folder-Account)
								- DNS setup for custom domains
									- Meta
										- [How to setup](https://kb.mailbox.org/en/private/custom-domains/using-e-mails-with-a-custom-domain/)
											- Step 2: Enter the mailbox.org key in the DNS settings of your provider
												- e.g. Your mailbox.org Securitycode is:
													- `9a88536a620fc4f7b69dd519cd86e1709493d139.sollesse.com.  IN TXT b89edd39ca17529d0afd9afd7e3f88c86e0ace16`
												- In a TXT record
													- Add a "Hostname" value - the first part of the key (6).
													- Add a "Target" value - the second part of the key (7).
											- On ((64e0946f-5565-48b0-b04f-101314d15d4c)) [setup DNS records](https://www.namecheap.com/support/knowledgebase/article.aspx/322/2237/how-can-i-set-up-mx-records-required-for-mail-service/):
												- Select your domain
												- Nameservers: `Namecheap BasicDNS`
												- Advanced DNS tab
											- Try to add it again on Email Aliases in Mailbox.org e.g. `@sollesse.com`
											- Update Mail Settings on Namecheap
												- Select `Custom MX`
												- Example MX Record:
													- Host: `@`
													- Value: `mxext1.mailbox.org`
													- Priority: `10`
												- Save all changes, then click add new record and repeat for other MX records
												-
									- ## habitlaboratory.com
									  collapsed:: true
										- [All records](https://dnschecker.org/all-dns-records-of-domain.php?query=habitlaboratory.com&rtype=ALL&dns=google)
											- A Records :
												- [0] Name : habitlaboratory.com | ttl: 14400 | ip: 192.254.235.116
											- MX Records :
												- [0] Name : habitlaboratory.com | ttl: 14400 | ip: 80.241.60.215 | mx: mxext2.mailbox.org. | preference: 10
												  [1] Name : habitlaboratory.com | ttl: 14400 | ip: 80.241.60.212 | mx: mxext1.mailbox.org. | preference: 10
												  [2] Name : habitlaboratory.com | ttl: 14400 | ip: 80.241.60.216 | mx: mxext3.mailbox.org. | preference: 20
											- NS Records :
												- [0] Name : habitlaboratory.com | ttl: 21600 | value: ns6501.hostgator.com.
												  [1] Name : habitlaboratory.com | ttl: 21600 | value: ns6502.hostgator.com.
											- SOA Records :
												- [0] Name : habitlaboratory.com | ttl: 21600 | mname: ns6501.hostgator.com. | rname: root.gator3251.hostgator.com.
											- TXT Records :
												- [0] Name : habitlaboratory.com | ttl: "14400" | value: "v=spf1 include:mailbox.org"
												  [1] Name : habitlaboratory.com | ttl: "14400" | value: "v=spf1 a mx include:websitewelcome.com ~all"
										- TXT for verification
											- Name
											  [9a88536a620fc4f7b69dd519cd86e1709493d139.habitlaboratory.com](http://9a88536a620fc4f7b69dd519cd86e1709493d139.habitlaboratory.com).
											- Value:
											  3ff04cc6257948e5750768b40332146f3aa26db1
										- MX for emails
										- TXT for SPF
										- TXT for DKIM
										  collapsed:: true
											- Key 1
												- Name
												  MBO0001._domainkey.habitlaboratory.com.
												- Value
												  v=DKIM1; k=rsa; p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA2K4PavXoNY8eGK2u61LIQlOHS8f5sWsCK5b+HMOfo0M+aNHwfqlVdzi/IwmYnuDKuXYuCllrgnxZ4fG4yVaux58v9grVsFHdzdjPlAQfp5rkiETYpCMZwgsmdseJ4CoZaosPHLjPumFE/Ua2WAQQljnunsM9TONM9L6KxrO9t5IISD1XtJb0bq1lVI/e72k3mnPd/q77qzhTDmwN4TSNJZN8sxzUJx9HNSMRRoEIHSDLTIJUK+Up8IeCx0B7CiOzG5w/cHyZ3AM5V8lkqBaTDK46AwTkTVGJf59QxUZArG3FEH5vy9HzDmy0tGG+053/x4RqkhqMg5/ClDm+lpZqWwIDAQAB
											- Key 2
												- Name
												  MBO0002._domainkey.habitlaboratory.com.
												- Value
												  v=DKIM1; k=rsa; p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAqxEKIg2c48ecfmy/+rj35sBOhdfIYGNDCMeHy0b36DX6MNtS7zA/VDR2q5ubtHzraL5uUGas8kb/33wtrWFYxierLRXy12qj8ItdYCRugu9tXTByEED05WdBtRzJmrb8YBMfeK0E0K3wwoWfhIk/wzKbjMkbqYBOTYLlIcVGQWzOfN7/n3n+VChfu6sGFK3k2qrJNnw22iFy4C8Ks7j77+tCpm0PoUwA2hOdLrRw3ldx2E9PH0GVwIMJRgekY6cS7DrbHrj/AeGlwfwwCSi9T23mYvc79nVrh2+82ZqmkpZSTD2qq+ukOkyjdRuUPck6e2b+x141Nzd81dIZVfOEiwIDAQAB
										- TXT for DMARC - optional, maybe not good to set
											- if the options are set too strict your e-mails may be rejected by the receiving server.
									- ## sollesse.com
									- ## aaronsollesse.com
									- ## synthfleshop.casa
									- ## spinningatoms.com
										- `ns6501.hostgator.com`
										  `ns6502.hostgator.com`
									- ## mail.spinningatoms.com
									- [source] [https://kb.mailbox.org/display/MBOKBEN/Using+e-mail+addresses+of+your+domain](https://kb.mailbox.org/display/MBOKBEN/Using+e-mail+addresses+of+your+domain)
								- Related: Consider importing MBOX (email message history) from old accounts into new ones i.e.
							- https://mail.riseup.net/
							- http://freedomhacker.net/list-of-secure-email-providers-that-take-privacy-serious/
							- https://prism-break.org/en/projects/autistici-inventati
							- https://www.privacytools.io/
							- For more email providers, take a look at Privacy-Conscious Email Services http://www.prxbx.com/email/ . Please decide for yourself whether if you trust them with your data. For more discussion about safe email providers, please see issue #461 https://github.com/nylira/prism-break/issues/461.
							- MyKolab is hosted in Switzerland and benefits from the strong Swiss privacy laws https://mykolab.com/privacy. It is run exclusively with free software and using the service supports the development of Kolab. Also, it lets you export all your data at any time. https://prism-break.org/en/projects/kolab-now
							- Riseup’s services may also be accessed via their Tor Hidden Service addresses. A list is available here. https://www.riseup.net/en/tor#riseups-tor-hidden-services https://prism-break.org/en/projects/riseup
						- Free custom domain providers
						  collapsed:: true
							- Zoho - but email forwarding, IMAP/POP is paid. Have to use their web app or mobile to access
					- Comparison
					- 1 Backlink
						- See [Hosted Email](https://workflowy.com/#/2e4a26948d8d)
				- Self-Hosted Email
				  collapsed:: true
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Inbox
								- Prevents the harm from data leaks and inbox scanning by your service provider
								- Fantastic if it uses PGP encryption client-side
								  collapsed:: true
									- Authorities would find it much more difficult to get access to emails on a random self-hosted VPS compared to a dedicated email host like Zoho. It would take a technician at least several hours since it'd be all manual work, vs a mostly automated process on Zoho since they are centralised service who must get many police requests.
										- Additionally if your software automatically encrypts incoming email with PGP encryption (like ProtonMail or Mailbox does) then it'll be impossible to access your existing emails unless you yourself get served a warrant directly to decrypt them for authorities. Or they'd have to get a technician to hack the software on your live server to not encrypt incoming mail, a process which could take weeks and I don't see being authorised unless you were a suspected terrorist or something.
							- Outbox
								- Sorts of info a SMTP relay can collect:
									- Metadata of who you're contacting
									- Name, address, payment information, domain, DNS records
									- Device diagnostics (such as temperature), software versions, enabled services, connection status, connection type, serial number
									- Anything related to customer support, including information customers provide
						- Cons
							- SMTP difficulties
								- Most ISPs or their provided routers block port 25 (SMTP)
								- Requires a reverse PTR record from your ISP
								- email service providers typically reject emails coming from residential IP blocks.
								- Gaining positive reputation with spam filters is very difficult, expect a lot of your emails to go missing
								  collapsed:: true
									- You need a static not dynamic IP
										- 1. Your IP could change at any time.
										- 2. Your IP will be on Dynamic Host Blacklists and cannot be removed (Many email server will refuse connections).
										- I know you say test server but you will still run into above problems and really just not worth the hassle involved trying to get the blacklists removed against the IP for it to change at any time putting back to being blocked
									- Takes a long time for a personal server to gain reputation
										- The way most of these providers deal with spam is they slowly white-list IP addresses. When a company like Mailchip or Mailgun spin up a new server, it's always in a large subnet range they've purchased and they slowly start sending low priority e-mail through it to existing/known receivers and throttle it up to full speed.
										- If you're running a personal server that sends like 5 or 6 e-mails a days, well that's an issue.
										- The big players make it difficult to run a small personal server, but running a dedicated business or corporate server that sends 100s of e-mails per day is typically fine once it's well established.
								- Many steps to setup
								  collapsed:: true
									- Make sure the computer sending the email has a Reverse PTR record from your ISP
										- What's a reverse PTR record? It's something your ISP has to configure for you -- a way of verifying that the email you send from a particular IP address actually belongs to the domain it is purportedly from.
										- Don't even bother reading any further until you've verified that your ISP has correctly configured the reverse PTR record for the server that will be sending email. It is absolutely the most common check done by mail servers these days. Fail the reverse PTR check, and I guarantee that a huge percentage of the emails you send will end up in the great bit bucket in the sky -- and not in the email inboxes you intended.
									- Setup DKIM keys in your DNS to verify authenticity
										- Configure DomainKeys Identified Mail in your DNS and code
										  https://blog.codinghorror.com/so-youd-like-to-send-some-email-through-code/
										-
									- Set up a SPF / SenderID record in your DNS
									- Test setup
									  https://blog.codinghorror.com/so-youd-like-to-send-some-email-through-code/
								- Even rhe Helm personal email server "solves" the SMTP issue by using their own hosted SMTP relay gateway EC2 instance
								  collapsed:: true
									- This avoids the issues of dynamic IPs, untrusted IPs, SMTP port blocking etc
							- IMAP/POP3 difficulties
								-
							- Maintenance is difficult and time-consuming
								- Lots of steps to setup
									- jeffreifman.com/how-to-install-your-own-private-e-mail-server-in-the-amazon-cloud-aws/configure-your-domain/
									- https://www.digitalocean.com/community/tutorials/how-to-run-your-own-mail-server-with-mail-in-a-box-on-ubuntu-14-04
								- Maintain security updates whilst resolving any errors caused by patches
									- If it *had* done this, it may have hit issues of reliability as the patch may fail and fuck up your server, and the customers would have no idea how to fix it
								- several services (MTA, SMTP, IMAP, web UI), each of which could go wrong
								- This is integral and requires 99.99% uptime
							- Requires a fair amount of memory eg Mail-in-a-box requires 768MB RAM
					- See [Consider Dockerised Self-Hosted Email](https://workflowy.com/#/150e22b5288d)
					  #Reminders
					- SOP for Offshore Self-Hosted Email
					  collapsed:: true
						- 1st get your own offshore web domain
						- Optional
							- If you want to go the whole nine yards then avoid the common .com / .org /.net / .us domains, because they are under the control of the US government, and the US government have atrack record of seizing domains they can get their hands on if they think they have a good reason for it.
							- Domain suffixes such as .no (Norway) or .at (Austria) are run by national-level, non-US agencies that are not under the jurisdiction of the US government.
							- ((649b1406-bee6-4bb0-8a79-2fce116f8e24)) - domain
							- https://www.reddit.com/r/privacy/comments/5o0rmq/what_is_the_best_way_to_get_anonymous/
							- African countries
							- https://en.wikipedia.org/wiki/Internet_censorship_and_surveillance_by_country
						- 2nd get an offshore VPS
							- Install iRedMail
								- iRedMail
									- + for extra security http://arstechnica.com/information-technology/2014/04/taking-e-mail-back-part-4-the-finale-with-webmail-everything-after/
								- https://prism-break.org/en/projects/indimail
								- A beginner’s guide to running your own mail server is available here: “NSA-proof your e-mail in 2 hours”. http://sealedabstract.com/code/nsa-proof-your-e-mail-in-2-hours/
								- Kolab integrates Roundcube into its webclient and offers desktop clients as well. Recent versions also feature a file cloud turning it into a complete solution for personal information management. https://prism-break.org/en/projects/kolab
							- See [Mail-in-a](https://workflowy.com/#/d5d4e9026b36)<a href="https://workflowy.com/#/d5d4e9026b36">-box</a>
							- ownCloud Mail
					- _Platforms_
					  collapsed:: true
						- Roundcube only
						  Bitnami
							- https://bitnami.com/stack/roundcube
						- Nextcloud mail
							- https://github.com/nextcloud/mail
						- iRedMail
						  $99 remote install
							- Paid support
							  http://www.iredmail.org/support.html
						- [Mailcow](https://mailcow.email/)
						  id:: 662d398a-5353-47ce-b39b-5749a438540a
							- [https://andryyy.github.io/mailcow-dockerized/](https://andryyy.github.io/mailcow-dockerized/)
							- [https://mailcow.github.io/mailcow-dockerized-docs/third_party-mailpiler_integration/](https://mailcow.github.io/mailcow-dockerized-docs/third_party-mailpiler_integration/)
						- _Dockerised_
							- ((662d398a-5353-47ce-b39b-5749a438540a))
							- [Mail-in-a-box](https://mailinabox.email/)
							- [Maddy: Composable all-in-one mail server]([https://news.ycombinator.com/item?id=27557542](https://news.ycombinator.com/item?id=27557542))
						- Unsorted
							- [Stalwart](https://stalw.art/blog/stalwart-webadmin/)
							- [Mox](https://github.com/mjl-/mox)
					- 1 Backlink
					  collapsed:: true
						- Consider Dockerised [Self-Hosted Email](https://workflowy.com/#/3341e4c7b065) for inbox instead of current cPanel
						  #Email
				- Disposable Emails
				  collapsed:: true
					- Note: don't put the web service domain name in the disposable email address
						- e.g. reddit.com@mydomain.org
						- amazon.co.uk@mydomain.org
						- The only weakness I can see is that it’s a clear pattern. If god forbid someone compromised your personal email account and your phone , maybe someone physically in your home, then it’d be trivial for them to reset your passwords.
						- Maybe throw a random number or two in the middle of the alias or at the end so it’s not easy to guess. Of course then the login is way harder to remember. Depends on your unique situation.
						- And if someone accesses your phone and computer while not locked they may likely have access to your all your passwords anyway with a password manager.
					- _Alternative open-source webserver/webmail_
						- ((63134593-906c-43b5-96fe-33dc2c34fda4)) extensions
							- [Addy](https://addy.io/)
							  id:: 655e4ece-7894-4a56-a949-b3aeb654bfba
							  collapsed:: true
							  AKA AnonAddy
								- Pros/Cons
									- Pros
										- Docker image
										  [https://github.com/anonaddy/docker](https://github.com/anonaddy/docker)
										- Browser extension supports self-hosting
											- Just click "change instance" if you're logged out of the extension
										- You can also add your ProtonMail public key and it’ll forward the email encrypted.
									- Cons
										-
								- [https://addons.mozilla.org/en-GB/firefox/addon/anonaddy/](https://addons.mozilla.org/en-GB/firefox/addon/anonaddy/)
								- [https://github.com/anonaddy/anonaddy](https://github.com/anonaddy/anonaddy#self-hosting)
								- [https://www.ghacks.net/2019/11/25/a-look-at-the-email-forwarding-service-anonaddy/](https://www.ghacks.net/2019/11/25/a-look-at-the-email-forwarding-service-anonaddy/)
								- _Types of email addresses_
									- vuejs@johndoe.anonaddy.com (AKA random bit before @)
									- Custom domains eg **alias@example.com**.
								- Free plan allows unlimited aliases at `username.anonaddy.com`
									- or 20 aliases at `anonaddy.com`
							- SimpleLogin
							  collapsed:: true
								- [https://simplelogin.io/](https://simplelogin.io/)
								- [https://github.com/simple-login](https://github.com/simple-login)
								- Pros/Cons
									- Pros
										- Docker image
										- Browser extension supports self-hosting
											- Just click "settings" if you're logged out of the extension
										- Roadmap for new services including masked phone numbers and credit cards
							- Firefox Private Relay
							  collapsed:: true
								- [https://github.com/mozilla/fx-private-relay](https://github.com/mozilla/fx-private-relay)
								- [https://addons.mozilla.org/en-GB/firefox/addon/private-relay/](https://addons.mozilla.org/en-GB/firefox/addon/private-relay/)
								- Waiting list for it will be open soon - possibly June?
								- [https://relay.firefox.com/](https://relay.firefox.com/)
								- _Limitations_
									- Can't reply to emails
									  [https://github.com/mozilla/fx-private-relay/issues/99](https://github.com/mozilla/fx-private-relay/issues/99)
									- No catch-all/username-based addresses
									  [https://github.com/mozilla/fx-private-relay/issues/55](https://github.com/mozilla/fx-private-relay/issues/55)
										- e.g. Ability to create custom aliases without even needing to use an extension. Ex. Just enter spamsite@username.anonaddy.com creates the alias for that site, and I know where the email came from.
									- Max 5 aliases until they release their premium version
									  [https://github.com/mozilla/fx-private-relay/issues/573#issuecomment-673146505](https://github.com/mozilla/fx-private-relay/issues/573#issuecomment-673146505)
						- [inboxen.org](http://inboxen.org) - mostly usable
						  collapsed:: true
						  Disposable emails can't reply
							- https://github.com/Inboxen/Inboxen
							- Pros
								- Docker image
								  https://github.com/crazy-max/docker-inboxen
								- Creates lots of masked emails with easily webmail interface
								- Forward admin emails to real email address
								  https://github.com/Inboxen/Inboxen/issues/182
							- Cons
								- Disposable emails cannot send replies through GUI
								  https://github.com/Inboxen/Inboxen/issues/166
								- Lacks - _p3, faster usability though_
									- When forwarded to real email with a header which allows blocking forwarding
									  http://i.imgur.com/I989K8n.png
									- Can reply to forwarded emails from email client and it will automatically appear as a normal reply
									- Firefox WebExtension to create a new disposable email
										- Trashmail
										  http://i.imgur.com/UnB10XR.png
										- Or just right-click context menu and it'll copy one to the clipboard + save url and date time as description
									- Enhanced forward/notification system
										- Notifications app? Similar to GitHub notifications
										  https://github.com/Inboxen/Inboxen/issues/130
											- Firefox or Android app which is just used for notifications?
										- IMAP being considered as a paid feature
										  https://github.com/Inboxen/Inboxen/projects/2
						- Use a catch-all (wildcard) email address
						  collapsed:: true
							- Pros/Cons
								- Cons
									- Can't one-click block an email address
									- Can't reply easily showing your reply address as the received mail address
							- TLDR;
								- buy a domain that you keep secret (eg.: yxz.com)
								- configure catch-all (wildcard) email address (*@yxz.com) that forwards all incoming emails to your primary email address
								- when signing up, generate a random hash as the part before @ with your domain (93784f@yxz.com)
							- I made also a Chrome extension that generates these hashes for you and you just copy the single-use email address. Some folks were worried that email addresses with random strings can get you blocked, so the extension can also generate a "fake user", eg.: itercar.gabrielle79@yxz.com. The same principle, only less suspicious.
							- https://protectiid.com/ - how to setup a Blur masked emails equivalent by using catch-all email forwarding from domain registrar
								- https://protectiid.com/
								- Chrome extension
								  https://chrome.google.com/webstore/detail/protect-iid/pohhdoefhlffonadgcfpfebhpcecanbm
							- Who is the email host in this context? Can it work with any e.g. ProtonMail or Gmail?
								- I don't think the Namecheap forwarding will work together with ProtonMail or Gmail. You can configure the catch-all directly in both ProtonMail (https://protonmail.com/support/knowledge-base/catch-all/) and Gmail (https://medium.com/@Nicolrnscodin/catchall-for-domain-aliases-in-gsuite-gmail-b509b147633d) though. The upside of this setup is that you'll be able to reply which I don't think is possible with Namecheap.
						- forward.cat
						  collapsed:: true
						  Creates only 1 disposable email per real. Also 7 day life limit
							- Pros
								- Allows creating 1 disposable email address which forward to 1 real email
							- Cons
								- Deactivation link is only in the first email received when creating a temporary email address
								- Temporary emails only last a week, can be extended up to two
						- spamgourmet.com
						- [maildrop.cc](http://maildrop.cc)
						- Spamex
						- 33mail
				- Email clients
				  collapsed:: true
					- Desktop
						- [Thunderbird](https://www.thunderbird.net)
						  id:: 6312a075-ceb2-4a57-adc5-2a27f91e865c
						  collapsed:: true
							- Pros/Cons
								- Pros
									- ((663b24fb-02ae-46d2-9f7c-88d846f3ed23)) support
									  collapsed:: true
										- Thunderbird now supports HKP keyservers that return one key per email address
										- Thunderbird can now upload OpenPGP public keys to VKS and HKP keyservers
										- Thunderbird now notifies the user if a message includes nested encryption, and allows viewing each encrypted part of the message
										- OpenPGP signature dates are now shown for signed messages
										- OpenPGP candidate keys can now be discovered and imported from GnuPG keyring, if external GnuPG is enabled
										- Candidate OpenPGP keys are now automatically discovered from GnuPG keyring, if external GnuPG is enabled
										- Thunderbird now supports option to always send public key with autocrypt header
										- Automatic enabling/disabling of encryption can now be enabled through UI
										- User-defined OpenPGP passphrases now supported
										- OpenPGP signature filenames now always end in ".asc"
										- Thunderbird can now open OpenPGP Key Manager dialog from commandline using "-keymanager" option
								- Cons
									- ["Show remote content" no longer available for encrypted emails](https://bugzilla.mozilla.org/show_bug.cgi?id=1931550#c41)
										- Moved to [Betterbird](https://www.betterbird.eu/) for now
										  collapsed:: true
											- [Install Betterbird on Linux | Flathub](https://flathub.org/apps/eu.betterbird.Betterbird)
											- [GitHub - Betterbird/thunderbird-patches: Betterbird is a fork of Mozilla Thunderbird. Here are the patches that provide all the goodness.](https://github.com/Betterbird/thunderbird-patches)
											- Differences
												- [Allows showing remote content in PGP-encrypted emails](https://github.com/Betterbird/thunderbird-patches/issues/376#issuecomment-2529043940)
												- [Betterbird. Simply better.](https://www.betterbird.eu/#featuretable)
									- Lacks
										- [System tray support on Linux](https://connect.mozilla.org/t5/ideas/system-tray-support-on-linux/idi-p/29820/page/3#comments)
										- [Roadmap](https://developer.thunderbird.net/planning/roadmap)
											- v136 scheduled for early March
											- [Thunderbird Send](https://blog.thunderbird.net/2023/09/thunderbird-podcast-5-remote-work-tips-tricks/)
											  Built on ((650aae19-5fc1-4605-8fe2-5bef37439231))
											- [Thunderbird Sync](https://blog.thunderbird.net/2023/07/an-update-on-thunderbird-sync/)
											  id:: 651a864e-c145-4495-8635-3412b0243e52
											  collapsed:: true
											  We plan to support syncing of your email account definitions, credentials, signatures, saved searches, tags, **tasks**, filters, and most major preferences. Not contacts or calendars?
												- Seems like it's intended to be added in the next update as part of the New User Experience
												- [Topicbox](https://thunderbird.topicbox.com/groups/daily/T85adc00762e552c6) - it's intended to include CardDAV and CalDAV
												- [446444 - [meta] Sync for Thunderbird](https://bugzilla.mozilla.org/show_bug.cgi?id=446444#a495439565_1689)
												- [464665 - Sync Iphone Contacts](https://bugzilla.mozilla.org/show_bug.cgi?id=464665#a438860191_546015)
												- [Carddav enhancement - syncronisation of address lists](https://bugzilla.mozilla.org/show_bug.cgi?id=1668791#c15)
												- Notably they're also working on improving the Calendar in [Aug 2024](https://blog.thunderbird.net/2024/09/thunderbird-monthly-developer-digest-august-2024/)
												- I asked for an update [here](https://connect.mozilla.org/t5/ideas/firefox-sync-for-thunderbird/idc-p/74973/highlight/true#M40381)
												- [Firefox Sync (for Thunderbird) - Page 3 - Mozilla Connect](https://connect.mozilla.org/t5/ideas/firefox-sync-for-thunderbird/idi-p/28971/page/3#comments)
											- Linux system tray in [July 2024](https://blog.thunderbird.net/2024/07/thunderbird-monthly-development-digest-july-2024/)
											- [Address book - merge contacts feature](https://bugzilla.mozilla.org/show_bug.cgi?id=1331249#a191328115_101158)
											  id:: 661716a8-0e16-4f45-8286-8d4c085d5230
											- [Address book - categories](https://bugzilla.mozilla.org/show_bug.cgi?id=1764184)
											  id:: 66176eae-f317-4056-b325-ffb89effbfdc
											- [Hierarchical tasks](https://bugzilla.mozilla.org/show_bug.cgi?id=194863#c69)
											- [Multi-process for calendar](https://bugzilla.mozilla.org/show_bug.cgi?id=1731227#c5)
											- Threaded conversation view
											  collapsed:: true
												- [There's basic threading](https://support.mozilla.org/en-US/kb/message-threading-thunderbird)
												- Gmail-like
											- [Converting emails into to-dos](https://bugzilla.mozilla.org/show_bug.cgi?id=380814#a489351839_29811)
											- [IMAP notes](https://bugzilla.mozilla.org/show_bug.cgi?id=713843#a340370642_546015)
										- [Send later](https://connect.mozilla.org/t5/ideas/firefox-sync-for-thunderbird/idi-p/28971/page/3#comments)
										-
								- Unclear
								- Comparisons
							- Links
								- [Blog](https://blog.thunderbird.net/)
								- [Changelog](https://www.thunderbird.net/en-US/thunderbird/releases/)
								- [Support forum](https://support.mozilla.org/en-US/questions/thunderbird)
								- [Beta/Daily/alpha testing forum](https://thunderbird.topicbox.com/groups/beta)
								- [Mozilla Connect - feature requests for Thunderbird](https://connect.mozilla.org/t5/forums/filteredbylabelpage/board-id/discussions/label-name/thunderbird)
							- ### Changelog
								- ((69189c21-30cb-46f2-8cf4-93d3385c99ff))
								- [[2025-03-31 Monday]] Testing ((651a864e-c145-4495-8635-3412b0243e52)) with Thunderbird Daily (in `~.Downloads`) - the Firefox/Thunderbird sign-in partially failed
							- ## Documentation
								- Installation
									- Thunderbird Beta via Flatpak
									  collapsed:: true
										- `flatpak remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo`
										- `flatpak install flathub-beta org.mozilla.Thunderbird`
										- `flatpak run --branch=beta --arch=x86_64 --command=thunderbird --file-forwarding org.mozilla.Thunderbird @@u %u @@`
											- As opposed to: `flatpak run --branch=stable --arch=x86_64 --command=thunderbird --file-forwarding org.mozilla.Thunderbird @@u %u @@`
											- #+BEGIN_WARNING
											  Can't use the same profile for Beta + Release - it'll tell you to make a new profile in the Stable version because updates have been made to the profile which are incompatible with older versions
											  #+END_WARNING
									- Thunderbird Daily
									  collapsed:: true
										- Profile
										  `/home/boss/.thunderbird/955dsfql.default-nightly/`
										- Related:
											- {{embed ((663b24fb-d09f-4377-8fa4-1f49c2914470))}}
									- Flatpak vs application
									  id:: 663b24fb-d09f-4377-8fa4-1f49c2914470
									  collapsed:: true
										- Profile
											- `/home/boss/.var/app/org.mozilla.Thunderbird/.thunderbird/b012opsa.default-default`
								- Features
									- Save as Search Folder
									  collapsed:: true
										- use saved searches... Ctrl+Shift+F and save the search as inbox for whatever email address. Then you can click on the saved search and treat it like an inbox.
										- Alternatively use ((661716a8-3da1-4cb4-8c82-6aa970e74874)) if searching the folder is starting to take too long
									- Message Filters
									  id:: 661716a8-3da1-4cb4-8c82-6aa970e74874
									  collapsed:: true
										- Tools > Message Filters
									- Address Book
									  collapsed:: true
										- vCard format for storing contact info
										- Has CardDAV support for syncing - therefore can view ((62f93609-8bb0-4716-95f8-e7f76b2669e6)) contacts
										- [Error 403 (Forbidden)!!1](https://play.google.com/store/apps/details?id=com.rm.android.wcps) can be used to sync WhatsApp profile pictures to phone contacts
										- Lacks
											- ((661716a8-0e16-4f45-8286-8d4c085d5230))
											- ((66176eae-f317-4056-b325-ffb89effbfdc))
											- [1728770 - vCard CATEGORIES support](https://bugzilla.mozilla.org/show_bug.cgi?id=1728770)
											- [271976 - (missing-vCard-fields) thunderbird does not import all outlook/outlook express/OE address book fields/information [meta/tracking]](https://bugzilla.mozilla.org/show_bug.cgi?id=271976)
											-
								- Tweaks
									- Disabling accessibility/automatic text sizing improves performance
								- SOPs
									- Mobile restore
									  id:: 672bf2de-8e95-49de-b849-70ae1553a571
									  collapsed:: true
										- On desktop app go to Settings > Export for Mobile > then on the mobile app scan each QR code. Don't click `Done` until all 3 have been scanned
										- ((649b13ce-23ea-43bb-9041-7bb0b328707c))
									- Moving emails from one email account to another
									  collapsed:: true
										- Select multiple emails -> `RMB` > `Copy To`/`Move To`
											- "I would advise using the 'Copy-to' because it's less risky. If something goes wrong with a 'Move-to' upload then you may lose an email if it's been already moved out of one folder, but gets lost in an upload to server. But if it's just performing a 'Copy-to' then the original will still be in original folder and you can repeat the operation. "
									- Add email account to Thunderbird
									  collapsed:: true
										- File > New > Existing Mail Account
										- You'll see the Mail Account Setup
										  http://i.imgur.com/pwYOQDC.png
										- Add email account info
										- Press Continue, then Manual Config whilst it's trying to look up our configuration (it won't finish)
										  http://i.imgur.com/4iUniHO.png
										- Email info
										  collapsed:: true
										  Example: http://i.imgur.com/DCk4bzR.png - follow notes below
											- Incoming/IMAP
											  collapsed:: true
												- Server name: mail.postmymeds.co.uk
											- Encryption: SSL/TLS
											  If you're having problems with this just select Auto
											- Outgoing/SMTP
											  collapsed:: true
												- Server name: smtp.mailgun.org
												- Encryption: SSL/TLS
												  If you're having problems with this just select Auto
											- Username
											  collapsed:: true
												- Incoming: **[Your full email address]**
												- Outgoing:
											- Click Re-test, then Done
											- Try to send an email from that address and it'll most likely have an error message and prompt you for the SMTP password:
											  d2d4451cd6
										- _Note: Full SMTP info_
										  collapsed:: true
										  As of 7/4/17
											- smtp.mailgun.org
											  Server name
											- 465
											  Port
											- postmaster@postmymeds.co.uk
											  Username
											- d2d4451cd6
											  Password
										- Make sure every PMM account uses that SMTP
										  http://i.imgur.com/pOTbURB.png
									- MBOX import/export
									  collapsed:: true
										- Export
											- Example MBOX file
											  `/home/boss/.var/app/org.mozilla.Thunderbird/.thunderbird/b012opsa.default-default/ImapMail/imap.mailbox.org/INBOX.sbd/Amazon`
										- Import
											- Remove the .mbox extension, copy the file into Mail/Local Folders of the profile (`~/.thunderbird/b012opsa.default-default/Mail/Local Folders`), when TB is closed, restart TB. ([July 2023](https://libreddit.lunar.icu/r/Thunderbird/comments/15e67ow/how_to_import_mbox_file_into_supernova/ju8263a/?context=3))
										- [[2024-03-22 Friday]] Attempt to manually merge two MBOX inbox files (aaron@habitlaboratory.com and habitlaboratory.com emails in the wirelessbear@mailbox.org folder) failed - it didn't show up in Thunderbird that the emails had been copied in
										- Thunderbird uses mbox files, so one big text file per mail folder. There is experimental maildir support (one file for each email) which is friendlier for anti viruses: [Maildir in Thunderbird | Thunderbird Help](https://support.mozilla.org/en-US/kb/maildir-thunderbird)
									- Filtering messages
									  collapsed:: true
										- `CTRL+U` = view source for the selected email
										- One easy wait to filter is using the sender's display name e.g. If  delicioustacos appears in the From header in the source (Ctrl+U), why not filter on From + contains +  delicioustacos
									- Opening URIs
									  collapsed:: true
										- `/usr/bin/flatpak run --branch=stable --arch=x86_64 --command=betterbird --file-forwarding eu.betterbird.Betterbird`
										- Example
											- `e8af4f6e02ed47b28e481f7a128234ca@baesystems.com`
								- Birdtray support on Wayland
								  collapsed:: true
									- [start birdtray with x11 session if possible `XDG_SESSION_TYPE=x11 birdtray`](https://github.com/gyunaev/birdtray/issues/426#issuecomment-1214944745)
									-
								- Potential add ons to install
								  collapsed:: true
									- Go to Tools > Add Ons > Get Add Ons
									- 1) Manually sort folders
									- 2) Thunderbrowse
									- 3) Send Later
									- 4) Minimize to tray
								- [Thunderbird Appointments](((66d07cb6-9ab3-4e60-975e-bd6374fcb8bf)))
								  id:: 66f44a86-65ee-4d4d-95f7-c5d23ba193fb
							- ## Troubleshooting
								- 'Subject' column missing
								  collapsed:: true
									- you might be able to 'clone' the columns of a folder which has 'Subject' present to that other folder by right-clicking the other folders columns > 'Apply columns to' in the column selector menu.
									  source:: [https://support.mozilla.org/en-US/questions/1320014](https://support.mozilla.org/en-US/questions/1320014)
								- `Options` button for show remote content missing
								  collapsed:: true
									- https://bugzilla.mozilla.org/show_bug.cgi?id=1931834 my report
									- Temp fix
										- `flatpak update --commit=da24ca372f80bdf48f4654080b8c2d7316156887835685679e2a3b41df4f6475 org.mozilla.Thunderbird`
							- {Archive}
							  collapsed:: true
								- Used to use [ShadowBird](https://github.com/overdodactyl/ShadowBird), no traces of it now. ((644c0b1a-b81c-4ac0-8bf9-8d83d0f9df94)) is my only modification
							- Related: ((63134593-906c-43b5-96fe-33dc2c34fda4))
				- _Increasing security_
				  collapsed:: true
					- PGP
					  id:: 663b24fb-02ae-46d2-9f7c-88d846f3ed23
					  collapsed:: true
					  Questionable because email is fundamentally insecure
						- [Gpg Frontend](https://flathub.org/apps/com.bktus.gpgfrontend)
						  id:: 66e03d46-0f11-492d-9978-e71ebd116cc1
						  collapsed:: true
							- [Encrypt and Decrypt Text](https://gpgfrontend.bktus.com/guides/encrypt-decrypt-text/)
								- Encryption uses a public key only, and you use the receipient's pubkey so they can decrypt it with their private key
								- ((66a2d2fd-b6ec-4aa3-9a83-fca887cc5748)) steps
								  id:: 66e03e0e-cdba-4223-93be-dd899cb168eb
									- Copy their pubkey to clipboard
									- In ((66e03d46-0f11-492d-9978-e71ebd116cc1)) click Import key > Clipboard
									- In ((66e03d46-0f11-492d-9978-e71ebd116cc1)) in the Key ToolBox right pane keep the tab on `Only Public Key` for ease filtering. Click the checkbox for the pubkey
									- Paste your address into the left text page
										- Aaron Sollesse
										  59 Lynwood road
										  Ealing
										  Middlesex
										  London
										  W5 1JG
									- Click `Encrypt`
						- ((663b24fb-c2c5-4650-929b-f56aca133bc2))
						- PGP encryption
						  collapsed:: true
							- [Autocrypt 1.1.0 documentation](https://autocrypt.org/) used in ((663b24fb-e901-4314-abf8-6f0c529ade12))
						- Cryptography (eg PGP, AES) > SSL/TLS
						- PGP stands for Pretty Good Privacy, and it is used for encrypting, decrypting and signing texts, e-mails, files, directories, and whole disk partitions and to increase the security of e-mail communications.
						- ((649b1404-12b4-4805-97e8-01869dd40d7a))
						- Finally you can use the following 2 pages to learn how to encrypt and decrypt messages using PGP.
						- https://tails.boum.org/doc/encryption_and_privacy/gpgapplet/public-key_cryptography/index.en.html
						- https://tails.boum.org/doc/encryption_and_privacy/gpgapplet/decrypt_verify/index.en.html
						- The second is using --hidden-recipient as a modifier to the gpg command when using GPG on the command-line. When the metadata of the subsequent encrypted file is analyzed, the key ID of the recipient reads 0x0000000000000000.
						- Use PGP whenever possible + store on microSD
						  collapsed:: true
							- store your PGP keys and other sensitive data on a SD card, is that if that day comes when you are compromised and you get a knock at your
							- door, you have time to dispose of that SD card or USB drive quickly. Even better, if you have a micro SD card that plugs into an SD adapter,
							- then you can snap it with your fingers or at the very least hide it. USBs would need to be smashed into pieces and it might not be easy to do this
							- in the heat of the moment, so do what you feel best about. But always prepare for the day they might come for you.
						- PGP Signatures
						  collapsed:: true
							- Since we just finished a section on verifying downloads with signatures and public keys, I figured we should do a quick post on verifying messages by using the same two things, signatures and public keys.
							- Now for those of you who are members of the Silk Road Forums, you will notice that some people, mainly Moderators like to sign their messages with signatures. Let us look at an example of a signed message from Dread Pirate Roberts. The last message he left before going on his leave of absence.
							- Quote
								- —–BEGIN PGP SIGNED MESSAGE—–
								- Hash: SHA512
								- Silk Road has not been compromised even if the allegations are true. Neither had access to sensitive material. I will make an announcement later to address the concerns this has raised.
								- —–BEGIN PGP SIGNATURE—–
								- iQIcBAEBCgAGBQJStEgqAAoJEMyyOOR8/t+867AP/RpjCq1B3WSYgnscbZU+UZOy
								- K0AGMM7tmu1DV1pr2S379YjVxQeUWeTbwDYhaYcWkDBDshnlpSd97fwAL1YVrBQx
								- jWE08tyo1sd1v5F/HajCx0DC2L5NeqD4UTDd6Dl2AOeBI4pZ+Ah/Q4VoB9cOBQGw
								- lSbjBY2U4redqBeRd1mFR8N+f3XmxYXzmB4Mf8ddvQkl62HmkwRwA27uUExt73uj
								- f3/EYVc/XjPgKG345S8yUwcGxLQcfoRM7UosbSGeEaDvvWjfZ6qQw4p7CbqIimHu
								- IOT6dhFcPmoVdiZGDvjtM3jXfF2sTi5mclGp/4axsrvOWZlCbrobE9EuJnGvscU4
								- ekU90vtcviES9XEJAr9XGOGgzY/OBf1xpj0iRY7rBDHUqA/FjfSULxqanZYhh0Wn
								- webHldrjylBRKM0PsnQdPn1CVGj8ThwB6SLfd0WEN1FEQt0hXP3uK1zDOri/fIcJ
								- Pnvf3jxYNcw9Q+2OW6QpZ/7t+S2E0yiifbNCobAMI18mrynuw3pk/xumg6t2WF/j
								- YHRpbTfFCCsbiPwR8P9CcUNQ5Iqcc2ewq4GOPx053aL/Vo/nfPdu/9hrRpfF3U5E
								- J7rFvAStaejxH7/vNxZRrTTiwrrc6njsFJHXWVAJjd+fHLI1efptbc8Kzwms9Yl0
								- 0nzLjAJPFZOv6y7gP8tG
								- =lDZd
								- —–END PGP SIGNATURE—–
							- So why should you care about this? What is the significance of signing a message? The reason is, in case somebody were to compromise DPR’s account, due to having a weak password or possibly an exploit in the forum’s coding, then the person would not be able to sign the messages without access to DPR’s private key. So let us look at how we can verify this message left by DPR. First of all you need to visit Dread Pirate Roberts’ profile page and grab his PGP public key. I am not going to post the key here for space reasons, but just visit his page at the following URL and import that key into your keyring.
							- http://silkroad5v7dywlc.onion/index.php?action=profile;u=1
							- Next, highlight the entire PGP signed message from top to bottom and copy it to your clipboard (Right click, Copy). You will see your little Clipboard icon in the top right of Tails turn red. Click on that clipboard and select Decrypt/Verify. You should get the following results. One in the window on top and the other on the bottom.
							- Quote
								- Silk Road has not been compromised even if the allegations are true. Neither had access to sensitive material. I will make an announcement later to address the concerns this has raised.
								- gpg: Signature made Fri 20 Dec 2013 01:37:46 PM UTC using RSA key ID 7CFEDFBC
								- gpg: Good signature from “Dread Pirate Roberts <silkroad6ownowfk.onion>”
								- gpg: WARNING: This key is not certified with a trusted signature!
								- gpg:          There is no indication that the signature belongs to the owner.
								- Primary key fingerprint: 5A48 F5D0 50E9 9052 62B4  799D CCB2 38E4 7CFE DFBC
							- Again we get the same warning we did when verifying our downloads, saying we have not verified that the PGP public key is authentic. We can see the signature name was made by Dread Pirate Roberts and the comment section has the Silk Road URL, so far so good. Now remember when we verified TOR? We wanted to check out the fingerprints to see if they matched. We do this by going to our key ring (Manage Keys), and selecting DPR’s key, right clicking it and going to properties. Now move to the tab Details and look under where it says Fingerprint: and compare the numbers in there to the numbers we got when we verified the signature. They should be the following.
							- 5A48 F5D0 50E9 9052 62B4
							- 799D CCB2 38E4 7CFE DFBC
							- We have ourselves a match! So unless DPR’s private key was compromised, we know that he himself was the one who wrote that message. So now you see why some people decide to sign their messages. It is a way of verifying that their account has not been compromised by verifying that the person in control of the account is the same person that is in control of the PGP private key.
							- Do you want to learn how to sign a message? It is very easy. Open up gedit Text Editor and type in a message. Next, select the message and copy it to your clipboard (Right Click – Copy) and then click on your clipboard icon up top and choose Sign/Encrypt Clipboard with Public Keys. Do not choose a key from your list of PGP public keys unless you want to encrypt the message. If you want to encrypt the message to send to somebody’s inbox or so that only one person can view it, then select their name and it will encrypt it with their PGP public key. In our case, we just want to sign the message without encrypting it, but you can certainly do both at the same time if you wanted to.
							- If you look down near the bottom you will see where it says Sign message as: click on this and select your personal key. It will ask you for your passphrase because remember you are signing this with your private key. Once you enter it correctly, the PGP signed message will be copied to your clipboard and you can paste it anywhere (Right Click – Paste) that you want to. Here it what mine looked like.
							- —–BEGIN PGP SIGNED MESSAGE—–
								- Hash: SHA512
								- This is my PGP signed message for demonstration purposes.
								- —–BEGIN PGP SIGNATURE—–
								- iQIcBAEBCgAGBQJS0GiWAAoJEPuh6tSg81nyqXAP/2mEqvk9RP0FEHZi3edH9faV
								- OmDoOostmzm90nGMGOOu4cuG0M6jgl7R3hfUZBE6zCh59MG8a9EDuUzpIT3U5nfd
								- zS0GWtzUQKGXPXfJ1OvWlsA6Sm7TsEsviBBz5DJxyVLcJGNU6OLUVm7onxBLwfTq
								- D1jAATIB43WJbDrq3XY9MF9GCoOLlcLeKNVa4m0JF582IvQJ05mSZXeXCueImvol
								- FaflpLW5MKyJJ92a8uheB0pLHUQTLr6jZn6TcfKY9dK8puOam5k2TGut/Sm47uqc
								- aMA1trXw4xntww/8X4QyL5SbSN7QVOFsy/g0b3Grp5OrConsfnsUoeRH5ArnxY0W
								- ijPl92aTbZazvXspW2REkJ3yq+fWjuGrYHw8m7/YVBig+OSMuBUXhSE5Pjq95fyM
								- bA1P7rF2fi7eRsl1z0qyETV3Bs1RltwvBUVIwj3SZNeVVoG5cHgpiPgGFq4S9Qke
								- unIFeHy3YpBk90kLA1n8n61VnkKAUy0Dt9AoTJloeOqPtcgeKHVsFzxdPCBcSwqd
								- XYnIx4lNeaw4OvHYgZsCMvFlUItSBGnFWLN9foQ8UybAUPGI9Z4sK2WmtyWK4fLl
								- cXnYY9zt56Ji4DiVsQrEUamNTQEDGxpvBL/kQKRMKN6HviEXW+qr57LAo6t6sTQw
								- KTV4uJkH1JxuOOhN9tIe
								- =Nkox
								- —–END PGP SIGNATURE—–
							- And if you want to verify it, check out my PGP public key in my profile and verify my PGP signature against my key! It is really that simple. But you might be asking, cannot somebody just change the message and copy the signature? No, changing the message will change the signature because the signature depends on both the message and the PGP private key. So if you change one single character of my signed message you will get the following error.
							- gpg: Signature made Fri 10 Jan 2014 09:39:34 PM UTC using RSA key ID A0F359F2
							- gpg: BAD signature from “Jolly Roger (They would live and die under it)”
							- So when should you sign a message? And when should you not sign a message?
								- Great question. **The majority of users should probably not sign messages unless they have to because it gives you plausible deniability.** It is easier to deny posting certain things or certain communications you may have had with vendors or other people including law enforcement if you do not sign your messages, because you can always claim somebody else gained access to your account. It is harder to do this if you signed the message with your PGP private key. If you are dealing with somebody who wants to verify your identity and make sure that your current signature matches the public key they had on file for you from 6 months ago, then maybe they might get you to send a signed message. But again, all they really need to do is send you an encrypted message with your PGP public key they had on file, and if you cannot decrypt it, you are not who you say you are.
								- In real world application, developers can use PGP signed messages in News Announcements or perhaps new releases of their programs providing a download URL so that users can be sure the developer is the one posting the URL and not some malicious attacker who compromised the forum account of the developer and so forth. So for the average Silk Road forum user there really is not a lot of times when you should be signing messages unless you are a moderator or making a public announcement and so forth, but it is an option you now have in your arsenal, and now you can start verifying the signatures of the Administrators and Moderators in case you believe their accounts may have been compromised.
						- PGP Email Addresses
						  collapsed:: true
							- This post was created by HonoluluExpress and posted at the following page and I have decided to add it to my security thread with his permission. The rest of the post is written in his words.
							- http://silkroad5v7dywlc.onion/index.php?topic=19277.msg383130#msg383130
							- Over the time I’ve been here I’ve been talking to a lot of people. I have also acquired a lot of gpg/pgp keys and I see that LOT of people use there real email addresses. I would like to remind everyone that when you give someone your pgp/gpg key THEY CAN SEE THE EMAIL ADDRESS THAT YOU ASSOCIATED WITH THAT KEY. You are NOT suppose to use ANY type of clearnet email service such as: gmail, yahoo, hotmail, etc. If you want to use a valid email address then you need to use an email provider that supports Tor and anonymity. For example I use safe-mail. I’m able to access this email service on Tor which allows me to stay anonymous. You may also use an email such as “123@123.com”.
							- DO NOT UNDER ANY CIRCUMSTANCES ASSOCIATE A CLEAR NET EMAIL ADDRESS WITH YOUR PGP/GPG KEY. THIS WILL COMPROMISE YOUR ANONYMITY.
							- Definition of DOX: Personal information about people on the Internet, often including real name, known aliases, address, phone number, SSN, credit card number, etc.
					- Combining PGP with masked/disposable emails/email forwarding e.g. Inboxen
					  collapsed:: true
						- Post
							- So I am overhauling my email and this process has taken many weeks and it has sucked terribly as a non-tech person (I have been questioning how much I really need email privacy the whole way, haha). Anyway, I am at the end of my testing services phase and trying to come up with a process/organization that works for me. I am currently deciding between Anonaddy and Simplelogin for my $36/$30 and came up with an idea.
							- AA/SL both have PGP support. I can setup PGP with them so they transmit all my email encrypted to my Gmail accounts. I can IMAP my Gmail accounts in Thunderbird and use Enigmail (or whatever the current PGP plugin for Thunderbird is) to decrypt. My research says I can also use Fairmail on Android to do this too.
							- Assuming I trust SL/AA, then would this be just like using GDrive with Cryptomator? I never have to trust Google but can use a Google account with unlimited storage, unlimited aliases and so forth? Has anyone done this? Does it even work? Will it reasonably keep Google from reading and mining my email for personal data? Do I even need to spend more money on Protonmail now (I was waiting for Black Friday to buy Proton Mail Plus)?
							- I want to add that I will be using my own domains with AA/SL so if they die off I won't lose access to my accounts. Also, from my research it seems the problem with PGP is metadata and the subject line still leaks to Google, only the message content is encrypted. Is this correct? If I can live with that are there any other issues I need to consider, privacy-wise and/or technically?
							- I need a sanity check and advice from people who know tech and how this all works, thanks!
						- [https://www.reddit.com/r/privacytoolsIO/comments/jkr3n7/good_idea_to_use_anonaddysimplelogin_as_an/](https://www.reddit.com/r/privacytoolsIO/comments/jkr3n7/good_idea_to_use_anonaddysimplelogin_as_an/)
						- Pros
							- Email inbox is encrypted at rest
							- Mailvelope can be used with gmail PGP
						- Cons
							- Greater technical burden compared to non-PGP use
							- Sending email isn't addressed by this method, though I'm not sure there is a method at all for this and you can just continue to use a mainstream SMTP provider for sending, or ProtonMail/Tutanota for E2EE
						- Longer feedback
							- I used AA with Gmail and it has been working well so far. There is an option to mask the subject and it will be present in the email banner instead.
							- Thunderbird now supports PGP natively. On Android, I used OpenKeyChain and K9 mail (use the latest version instead of suggested version if you want a relatively modern design).
					- 2-Factor Authentication
					  collapsed:: true
					  AKA 2FA / MFA / Multi-factor authentication
						- Swap email to POP3
						  collapsed:: true
							- Better email is kept on local hard drive rather than vulnerable on a server out of my control
						- Google 2-Step Verification
						  collapsed:: true
							- https://myaccount.google.com/signinoptions/two-step-verification
							- Options
								- Prompt on phones signed into Google
								- Text message
								- Voice call
								- Google Authenticator or other TOTP app
									- https://support.google.com/accounts/answer/1066447
									- First setup text message or voice call
							- https://www.google.com/landing/2step/
						- Mail.com doesn't have 2FA
						- cPanel-Hostgator
						  collapsed:: true
							- cPanel supports 2fa
							  https://support.hawkhost.com/index.php?/Knowledgebase/Article/View/157/0/how-do-i-enable-two-factor-authentication-2fa-for-cpanel
							- Bluehost supports
							  https://my.bluehost.com/hosting/help/two-factor-authentication
						- [ProtonMail](https://protonmail.com)
						  id:: 663b24fb-0c93-4d9d-a6b8-8e3c3cfa326b
						  collapsed:: true
							- Cons
								- Server-side is closed source
								- Mobile apps are closed-source
								- Swiss privacy is overrated
							- https://protonmail.com/signup
							- 4 euros a montj
							- Paid user features
								- Import and Export only available via ProtonMail Bridge
								- https://protonmail.com/support/knowledge-base/export-import-emails/
								- Send encrypted emails to recipients who don't use ProtonMail
						- 2FA for border crossings
						  collapsed:: true
							- 1
								- Once 2FA fails, preventing you from accessing your own accounts, a border agent may attempt to access your email to reset the accounts. Ensure that your devices have all been signed out of your email, and that no passwords are stored on the device. Ideally, use a completely different email account to provision your accounts – one that is not normally synced with your devices, and one known only by you. This is sound security advice too for protection from everyday phishing. You can go through the same dance to lock yourself out of that email account as well, of course, making those backup codes only available to yourself on the other side of the border.
								- The 2FA for that email account can forward to some dead account that you’ve long since closed, or take this as far as you want to go with it. Chances are a border agent is only willing to go so far down the rabbit hole before giving up, but YMMV. It’s best to have a dead end somewhere that even you can’t recover from, but have many offsite recovery hooks to.
							- Data Redundancy and the Cloud
								- While you may wipe your devices of personal data, a traveler often needs at a minimum access to their basic contacts and calendar. This information can be synced in iCloud; before arriving at the border, wiping your device will remove all of your personal information, including iCloud data, from the phone. Once you’ve arrived at your destination, using your 2FA backup code to re-sync your iCloud content will give you back your minimum working data to be functional again. This could be as simple as giving your friend a code and calling them later, or posting it using stego somewhere.
								- Your iCloud information is, of course, subject to warrants, however border crossings often go by much looser rules. The probability of obtaining a warrant is generally going to be low at a border crossing, unless you’ve got reason to believe otherwise, but there are also rules involving what soil your data sits on (rules that have been pushed on recently, mind you, in this country). Keeping your data in any online system will no doubt expose it to a warrant, but that’s not what we’re trying to protect ourselves from here.
						- Backup 2FA device
						  collapsed:: true
							- See [Google Nexus 7 (2013)](https://workflowy.com/#/31333e405aae)
							- Copy all 2FA codes
							- 2 Backlinks
								- Backup phone probably makes more sense than a separate device for [Backup 2FA device](https://workflowy.com/#/59e51237df60) - seeing as it'll need to be sent an exported andOTP backup via internet or WebRTC anyway
								- See [Backup 2FA device](https://workflowy.com/#/59e51237df60) (Google Nexus 7)
				- configure the email client to delete old emailsafter a month, year, etc. Or just use POP3
				- To phase out old email addresses, set forwarders on them
				- How to migrate email
				  collapsed:: true
					- Create an email account on the new server with the same email address + password, then drag-and-drop the emails using Thunderbird
					  source:: [https://mediatemple.net/community/products/dv/204405444/how-do-i-migrate-email-between-servers-using-imap](https://mediatemple.net/community/products/dv/204405444/how-do-i-migrate-email-between-servers-using-imap)
				- Email reputation
				  collapsed:: true
					- Hosting your own email isn't that hard. Buy a domain name, then use some off-the-shelf solution like Mailcow, Maddy or Mail-in-a-Box on your own server. Or use a GUI-based web app like Nextcloud or cPanel that also allows deploying an email inbox.
						- The real difficulty comes in when you want to send emails, not in receiving them. For that you either need to spend a long time building up the reputation of your server's static IP address, or you have to use a 3rd-party to deliver emails for you. Mailgun, SendGrid, Amazon SES, etc have great delivery rates, but it does mean your email content is now exposed to an additional party. I don't know of another good workaround for this, it's just a result of how broken email is as a protocol.
					- If you search "email reputation static IP" or similar you can find articles like [this one](https://luxsci.com/blog/8-factors-influence-ip-reputation-email-deliverability.html)
						- which explain the various factors, but it basically boils down to "how
						- has the IP address been used?" e.g. was it ever used for spam, what's
						- it's email reputation like now, etc.
						- There are a number of tools which can be used to check your [email reputation](https://sendgrid.com/blog/5-ways-check-sending-reputation/).
						- From what I understand though an IP needs to send hundreds of thousands
						- of emails per month to build reputation significantly, and during this
						- time all these emails may have unreliable deliverability rates. Using a
						- hosting company's in-built email would not necessarily have a good
						- reputation, it all depends on what the thousands of users which share
						- the IP do with email. If a large amount of emails isn't being sent per
						- month, it also means email providers are less likely to remember that IP
						- as a high reputation sender.
				- [Learning Resources]
					- https://discuss.techlore.tech/t/list-of-anonymous-and-free-email-providers-with-imap/10725
					-
			- See [FOSS alternative to Blur masked/disposable emails/email forwarding e.g. Inboxen #001-type:privacy  #001-p2](https://workflowy.com/#/0da5eea02c86)
			- Mailing list clients
			  collapsed:: true
				- Standard email clients
					- Thunderbird
					- KMail
				- Other GUIs
					- Source Hut's native one
					  e.g. [https://lists.sr.ht/~petercxy/shelter](https://lists.sr.ht/~petercxy/shelter)
			- Business Email Management
			  collapsed:: true
				- Front
					- [https://frontapp.com](https://frontapp.com/try-front/email-management-software?utm_device=m&utm_medium=ppc&utm_term=front%20app&utm_source=adwords&utm_campaign=ls_brand-exact&hsa_kw=front%20app&hsa_grp=84680077615&hsa_acc=8738266666&hsa_src=g&hsa_ad=475598411263&hsa_net=adwords&hsa_cam=8169237257&hsa_mt=e&hsa_tgt=kwd-354808540727&hsa_ver=3&gclid=EAIaIQobChMIh-nRobyx7QIVztPtCh3OvQpwEAAYASAAEgLC1PD_BwE)
					- Features
						- Tagging
						  [https://images.prismic.io/sacra/85aac588-3d3b-4194-a457-aef29e9656a2_image34.png?auto=compress,format](https://images.prismic.io/sacra/85aac588-3d3b-4194-a457-aef29e9656a2_image34.png?auto=compress,format)
						- Chat threads in each email
						  [https://images.prismic.io/sacra/5d92efa8-fc8f-49a0-a5fa-86e39f7fa7ce_image30.png?auto=compress,format](https://images.prismic.io/sacra/5d92efa8-fc8f-49a0-a5fa-86e39f7fa7ce_image30.png?auto=compress,format)
					-
				- Zendesk
		- _Email alternatives_
			- _Solutions_
				- Decentralised ((650aae19-56a4-43ed-b1dc-b3acd07ea36e)) e.g. ((631fa97e-a0a9-406c-b7b9-20536d421090))
				- Email to X bridges
					- Pros
						- Faster growth by also allowing use of legacy protocol, rather than having to use two apps
					- Matrix bridge
					  [https://github.com/JojiiOfficial/Matrix-EmailBridge](https://github.com/JojiiOfficial/Matrix-EmailBridge)
				- _Hybrid email / instant chat apps_
					- Criptext
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Signal Protocol is more secure than PGP (forward secrecy etc)
							- Cons
								- Server is closed-source (like Telegram)
									- Can't verify that they actually don't store received unencrypted emails
									- Can't verify that emails sent to non-Criptext emails with the encryption option actually encrypt client-side
									  Or maybe this is visible in the client
								- We also keep email metadata (subject, date and recipient email address) in order to enable certain features of the Services, such as the “unsend”, “read receipts” and “expiration” features.
								- Privacy policy indicates they're selling some data to advertisers
									- https://www.criptext.com/en/privacy/
							- Unclear
								- All your emails and private keys are stored solely on your device.
									- Once Criptext delivers an email there‘s no trace of it left in our servers whatsoever.
									- If undelivered after 30 days it's deleted
								- Attachments are stored in servers
						- Open questions
							- ((663b24fb-4437-4115-83da-5f5b668989fc))?
							- Encrypted Profiles?
							- Sealed Sender?
							- Encrypted subject line?
							- Importing current inbox into Criptext?
							- Pin for Android app and encrypted database?
							- Trimming email inbox for mobile apps so it doesn't take up lots of space?
					- [Delta Chat](https://delta.chat)
					  id:: 663b24fb-e901-4314-abf8-6f0c529ade12
					- ((663b24fb-c2c5-4650-929b-f56aca133bc2))
				- ((663b24fb-febe-4b1e-888c-4e7dcb6a3ab4)) or Protonmail could be but server code isn't open-source nor can be federated
					- Tutanota server code isn't open source
					  [[Reddit - The heart of the internet](https://www.reddit.com/r/tutanota/comments/h0oipn/will_we_ever_be_able_to_selfhost_our_mail/](https://www.reddit.com/r/tutanota/comments/h0oipn/will_we_ever_be_able_to_selfhost_our_mail/))
					-
			- [Learning Resources]
			  collapsed:: true
				- Anonymous remailers
					- Remailers
					  collapsed:: true
						- An anonymous remailer is a server that receives messages (in this case an email) with embedded instructions on where to send them next, and that forwards them without revealing where they originally came from.
						- A nymserver also referred to as a pseudonymous remailer assigns its users a user name, and it keeps a database of instructions on how to return messages to the real user. These instructions usually involve the anonymous remailer network itself, thus protecting the true identity of the user.
						- Some of the advantages of using these services are to protect the intended recipient from an adversary, and also protect the sender of the message. Some of these services use what is called a common mailbox, in which all messages are stored in a central mail box with no “To and From” headers. It is up to the users who use the service to attempt to use their PGP keys to try and decrypt all of the messages stored in the central message box and see if they can decrypt any of them. If they can, this message is intended for them. This way it rules out again, the sender and receiver. This system of remailers, can also form a chain, in which the message is bounced off of multiple remailers before making it to its intended reicipient to widen the gap between the sender and receiver.
						- Another effective option some services offer is the ability to delay when the message gets sent on to the next server in the chain, or the recipient itself. If you are found to be sending out PGP encrypted traffic through some type of analysis at 5:00PM, and another person being monitored receives it at 5:01PM, it is easier to correlate that this message may be from you to the other person being monitored.
					- ******* http://remailer.paranoici.org/howto.php
					- ******* http://mixmaster.sourceforge.net/ client + server
					- ******* https://www.cypherpunks.to/remailers/
					- ******* Send an empty email to the remailer with "remailer-key" (not including the quotation marks) in the subject line.
					- ******* Email should have PGP message for first remailer, which then decrypts it to get knowledge of where to send the second message ?
					- ******* Remailers
					  collapsed:: true
						- Web-based http://gilc.org/speech/anonymous/remailer.html
						- http://www.noreply.org/echolot/rlist2.html
					- ******* https://www.whonix.org/wiki/E-Mail
				- https://www.whonix.org/wiki/E-Mail
				- https://github.com/OpenTechFund/secure-email
		- Related: ((644c0a79-0d6c-4add-bac7-198ba4ce278c))
	- ((6525b4a1-b3a9-4636-84e0-140ed18f5825))
	- [[Social Media]]
	- _Related:_ ((64f5d198-5bf7-42f6-b8bd-33f86bac188e))
	- Related: [[Software]]