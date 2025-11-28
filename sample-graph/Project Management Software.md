- Project Management
  id:: 64098f11-95d7-41d2-9465-17500ddeec24
  #Software-PM
	- **My usecases**
	  collapsed:: true
		- _Priority_
			- Web-based CalDAV app (Tasks and Orgzly mobile apps have CalDAV already)
			  collapsed:: true
				- Android + web
					- [Install Super Productivity on Linux | Flathub](https://flathub.org/apps/com.super_productivity.SuperProductivity)
					-
				- _Android apps with CalDAV support_
					- Tasks (has CalDAV)
					  #Software https://workflowy.com/#/433fa5dd4038
					- Orgzly (has CalDAV)
					  #Outliners https://workflowy.com/#/f98c5435aacd
				- _Web-based or desktop CalDAV app_
					- EteSync Tasks
					  ((633b7546-8735-4803-8694-43f949258c50))
					- ((64463cc6-5edc-41cf-b28e-e9e48b8aabe7))
					- ((64463cc6-5eb6-4f60-8bf1-37a8cecad1db))
					- [Cron](https://cron.com)
				- **OR can just use Orgzly + Emacs org-mode**
				- _Related:_
					- [caldav-push](https://www.reddit.com/r/fossdroid/comments/1fizd63/first_caldav_push_usable_with_nextcloud_and_davx⁵/)
					  collapsed:: true
						- There is currently no ability to Push data to clients if there are 
						  changes on the server in WebDAV. So clients would need to schedule syncs
						  regularily for changes on calendar, contacts, tasks, files, etc when 
						  using WebDAV or CalDAV/CardDAV.
						-
						- There is a Standard in the works by the team behind the DAVxâµ (Android sync app).
						-
						- Project on Github: [https://github.com/bitfireAT/webdav-push/](https://github.com/bitfireAT/webdav-push/)
						-
						- The team on DAVx5 just announced that it's been implemented to a certain extent now into [u/Nextcloud](https://teddit.froth.zone/u/Nextcloud)
						  (activate the app dav_push) and DAVxâµ (version >4.4.2) now and it 
						  already works and can be used publically in a first Alpha version. You 
						  can use [u/UnifiedPush](https://teddit.froth.zone/u/UnifiedPush)
						  to receive events and tasks almost instantly on your Android now, which
						  is super cool. No need to wait for scheduled syncs. FCM will also be 
						  supported as well as it will be extended to CardDAV address books and 
						  Files (WebDAV)
						-
						- The tutorial shows the few steps you need to do: [https://www.youtube.com/watch?v=XQ2jhqbDL6M&ab_channel=bitfirewebengineering](https://www.youtube.com/watch?v=XQ2jhqbDL6M&ab_channel=bitfirewebengineering)
						-
						- It's hard work to bringt that to life but the team is making constant progress.
						- ((65a64271-402b-4c98-943a-4d461ded7a38))
					- ((64463cc6-aff8-42cb-97f0-08898d8dbb70))
			- Outliner app as base e.g. org-web
			  collapsed:: true
				- Most developed WorkFlowy open-source bases
				  intralink2:: https://workflowy.com/#/fe381071fe71
				- Orgzly + Emacs org-mode with git sync
				  intralink2:: https://workflowy.com/#/73220a9fa8c3
			- Open-source libraries as base
			  collapsed:: true
				- for mobile app
					- Asana
						- Android v7 appcompat library
						- Android design
						- Android recyclerview v7
						- Android support annotations
						- Android support v5
						- CircleImageVIew
						- CWAC RichEdit
						- EventBus
						- FloatingActionButton
						- GreenDao
						- Jackson
						- LeakCanary
						- Mixpanel
						- OkHttp
						- Picasso
						- Retrofit
						- StickyListHeaders
					- Tried 5 others - no libraries accessible
					- Encrypted storage (PGP?)
						- Qhttps://github.com/0xbb/otp-authenticator/blob/master/README.md
				- Keyboard shortcuts
					- https://github.com/RobertWHurst/KeyboardJS
		- _Types_
			- Collaborative Project Management
			  collapsed:: true
			  w/ **Outliner**
				- It's difficult to have both outlining and effective project management features
				- Best current designs
				  collapsed:: true
					- Dynalist
					  intralink2:: https://workflowy.com/#/a8d17c91ce3a
					- + needs
						- Activity Stream/Feed
						  https://imgur.com/GE5m39A
						- Following
						- Task Comments
						- Assigning
						- Task editor popup
						  http://i.imgur.com/G4yi8tc.png
							- http://i.imgur.com/KDz4sVD.png
						- Task dependencies/Start date (Mark As Waiting On...)
						  Allows Timeline/Gantt chart
						- Liking/reactions
						- Project/category
							- Could be solved by sharing a parent tag then creating child ones on certain nodes
							- This would be in Tag Pane in Dynalist, and there would be no indent for child tags
						- API or push notifications for tasks
					- Orgzly (org-mode)
					  intralink2:: https://workflowy.com/#/f98c5435aacd
					- Todoist
					  intralink2:: https://workflowy.com/#/2fd192b99f3f
				- TaskWarrior?
				  collapsed:: true
					- Taskwarrior is a command-line todo list manager. It maintains a task list, allowing you to add/remove, and otherwise manipulate your tasks. Task has a rich set of subcommands that allow you to do sophisticated things. You'll find it has customizable reports, charts, GTD features, device synching, documentation, extensions, themes, holiday files and much more.
					- https://taskwarrior.org/
					- https://tasktools.org/
					- Taskserver
					  https://git.tasktools.org/TM/taskd
						- Looks like little progress
						- The Taskserver is a lightweight, secure server providing multi-user, multi-client access to task data. This allows true syncing between desktop and mobile clients.
						- https://tasktools.org/projects/taskd.html
						- About
							- Users want task list access from multiple devices running software of differing sophistication levels to synchronize data seamlessly. Synchronization requires the ability to exchange transactions between devices that may not have continuous connectivity, and may not have feature parity.
							- The Taskserver provides this and builds a framework to go several steps beyond merely synchronizing data.
						- Development
							- Future Taskserver releases are being planned now. Features currently being designed include:
								- Data encryption
								- Group lists
								- Task delegation
								- Configuration syncing
					- Web/mobile web app
					  https://inthe.am/about
				- DIY - paying a developer
				  collapsed:: true
					- Pros/Cons
						- Pros
							- Viable as it's only 2-man teams who work on WorkFlowy and Dynalist
								- Dynalist
									- Shida Li does all the backend stuff, infrastructure, server admin, database... basically all the magic under the hood.
									- Erica Xu does design, frontend work, and support. So if you feel like anything UI-related needs fixing, tell Erica to fix it!
							- Sooner rather than later as I'll have to replace internal links
								- Search for tags or workflowy.com and replace them all
					- Starting from scratch - duplicating WorkFlowy
						- Technologies used React for frontend, node.js/python for backend
						- Features
							- ➜ Infinitely nested lists
							- ➜ Zoom in on any sub-list
							- ➜ Tagging allows search to filter list items
							- Automatic regular syncing
							- Works offline
							- Works on phones and tablets
							- ➜ Add notes to any list item
							- ➜ Simply click to edit, like a text document
							- ➜ Quick expand and collapse lists
							- ➜ Mark items as complete
							- ➜ Instant full text search
							- Zoom in by clicking a bullet point
							- Zoom out by clicking "Home" above the list
							- Collapse a bullet point
							- Expand a bullet
							- Click the tag "#now" to filter the list
							- Search for "genius"
							- Hit the "esc" key to clear the #tag filter
							- Drag a bullet to a new location
							- Hover over a bullet until the menu pops up, then click "Complete"
							- Type to edit some text
							- Hit "enter" to create a new line
							- Hit "tab" to indent
							- Hold "shift" and hit "tab" to outden
							- Export to plain text or HTML
							- Mobile-friendly
							- Share task (search by @name)
							- Themes, markup, fonts
							- URL links to other tasks
							- http://blog.workflowy.com/2012/09/25/hidden-search-operators/
							- New features
								- Reminders or changelog for updated nodes (like followers inbox)
								- Recurring task / Deadlines
									- http://blog.workflowy.com/2014/04/24/workflowy-tip-dates-for-easy-filtering/ http://blog.workflowy.com/2015/03/06/a-useful-hack-for-repeated-tasks-in-workflowy/
								- Asana's Hypertext - dynamic conversion of URLs to task title
									- http://blog.workflowy.com/2014/03/27/is-this-how-links-should-work
								- http://blog.workflowy.com/2014/01/23/what-missing-feature-do-you-want-most-in-workflowy/comment-page-2/
						- Non-WorkFlowy improvements
							- Lazy loading (like VimFlowy)
							- Client-side encryption
							  See #ClientSideEncryption
							- Allows attachments in Asana-style (puts it onto Amazon S3)
			- Online WorkFlowy data
			  collapsed:: true
			  More secure than WorkFlowy - allows sync with own server/AWS etc
				- Alternatives
					- Calculist
				- Advanced Security
					- Android encryption via CyanogenMod
					  vs local attack
				- _Possibly to move from online WF to offline_
					- [[World]]
					- [[Game]]
					- ((644c0a70-8c2a-4d45-bd4f-fd13876c8d64))
					- The rest is also good to ensure competitive advantage
			- Local WorkFlowy replacement
			  collapsed:: true
			  Pre-req:
				- Prerequisites
				  collapsed:: true
					- Encryption at minimum. Steganography maybe impossible if also wanting regular automatic cloud sync
						- For desktop can use TrueCrypt as normal or ownCloud
					- Mobile
						- Mild steganography, strong encryption
							- Action Launcher covers
							- Samsung Knox or other virtual container
							- BoxCryptor or Cryptomator for second layer
						- Alternatively: Need custom ROM eg Copperhead, Cyanogenmod
							- Android encryption with encryption password and screen pattern lock
							- Rooting allows on-the-fly mounting of TrueCrypt containers
						- Android for Work - cons vs Knox
							- No separate home launcher
								- By default, the following intents are automatically configured by the system during the Work Profile creation to be forwarded to the Primary Profile:
								- ● Home intent—The launcher doesn’t run in the Work Profile
							- No separate encryption for virtual container
				- Workflow
				  collapsed:: true
					- If hidden desired
						- In /downloads/data/ a TrueCrypt container with org file
					- Otherwise just use same workflow as online WorkFlowy data
			- Dream productivity app
			  id:: 663b24fd-96ae-4442-b5b4-56eb3fc40421
			  collapsed:: true
			  #Software-Dream AKA Ideal productivity app
				- _Principles_
				  collapsed:: true
					- Future-proof
					  collapsed:: true
						- It's time-consuming to move data to new systems
						- How
							- Few if any dependencies
							- Client-side software, preferably Linux
					- Low Maintenance
					  collapsed:: true
						- Why
							- Time-consuming otherwise
						- How
							- Client-side software
								- Server-side requires
									- Dependencies
									- Maintenance (I'm not a systems administrator)
									- A paid server
				- Core
				  collapsed:: true
					- Outliner for hierarchy and structure
					  collapsed:: true
					  #Outliners https://workflowy.com/#/88864c616a9b
						- Calculist
						  intralink2:: https://workflowy.com/#/279bb9cfab0c
						- Org-mode
						  intralink2:: https://workflowy.com/#/d9881922728f
						- Vimflowy
						  intralink2:: https://workflowy.com/#/4e25fdbe2954
						- _Get inspiration from_
							- Dynalist
							  intralink2:: https://workflowy.com/#/a8d17c91ce3a
					- Add in Asana/Todoist's sections using : to create visual separation but not change the parent item
					  collapsed:: true
					  https://get.todoist.help/hc/en-us/articles/115001709669-Creating-sections-inside-projects
						- This allows you to create something which works well in Kanban form (the section headers are not actual tasks, they're more descriptive of the tasks within their section
							- Example project
								- _Draft the blog post:_
									- Task1
									- Task2
								- _Rewrite and edit: _
									- Task1
									- Task2
								- _Scheduled publish and syndicate:_
									- Task1
									- Task2
					- Tag Attributes (TaskPaper, Dynalist) to enable aspects like assigning, due + completion date, progress % etc
					  #Outliners https://workflowy.com/#/17eeb4fcbe74
					- Multiple Views
					  collapsed:: true
					  Implemented as Plugins or Item Properties
						- _Outliner is easy to turn into_
							- Mind Map View
							- Kanban/Card View
							- Dynalist Views feature
							  intralink2:: https://workflowy.com/#/4663ed338dd8
							- Some of the views that we’re interested in experimenting with include
								- Calendar View
								- Presentable View
								- Column View
								  intralink2:: https://workflowy.com/#/d6b716822ab2
						- ((663a0528-7561-41e3-ae6d-34b4dc2e4d26))
						- Grid/Spreadsheet View
						- ActiveCollab views
						  http://i.imgur.com/TZvA4ro.png
							- List/overview
							- Column/Kanban view
							- ((663a0528-7561-41e3-ae6d-34b4dc2e4d26))
						- Different section types
							- Code blocks
							- Checklists vs bullet points vs presentable
							- Eisenhower matrix (urgent v important)
							  See My Effectiveness app on android
						- Apps based on data within (like Airtable Blocks)
						- See Zenkit - Zenkit does List, Table, Kanban, Calendar, Mind Map - see how they do it
						- See Notion
					- Other good ideas from all project management apps
				- _Other important features_
				  collapsed:: true
					- Software for permanently linked, hosted multimedia files
					  collapsed:: true
						- Usecase - permanently linked, hosted multimedia files
							- Use instead of imgur for permanent pictures linked from WorkFlowy
							- Link other multimedia including videos and documents from WorkFlowy also
						- Server
							- If it hasn't got client-side encryption, then it needs to be locally hosted (would get too expensive if using a cloud server for the amount of storage anticipated)
							- Client-side encryption may not be compatible with the idea of Imagus-previewed images anyway
						- _Software solutions_
							- See FileSafe (E2EE on cloud storage or self-hosted)
							- Perkeep
							  collapsed:: true
							  Previously Camlistore
								- Features
								  collapsed:: true
									- Encrypted blobs (client-side encryption)
									  https://groups.google.com/forum/#!topic/perkeep/MHtuHrGCtqU
									- Tag-oriented (vs. hierarchical)
									- Permissions, encryption, compression, sharing, etc.
									- Spans storage across machines and clouds
									- FUSE mountable
									- Has CLI and Web interfaces built-in
									- plugins let you store stuff in S3 or mongo or google cloud storage
									- design attempts to be agnostic about where the stuff is actually stored
										- Usually you want to be storing your stuff in multiple different places. Among others, Perkeep lets you choose one or more (or all) of the following:
										- Your own hard drive local to the Perkeep instance Your own hard drive local to another Perkeep instance you run Your friend's hard drive local to another Perkeep instance _they_ run with encryption to ensure privacy A removable hard drive you can periodically sync to and from A cloud service like S3, etc
									- Search
										- Search: pointing Perkeep’s search handlers at an index means you can search for your things. It’s worth pointing out that you can lose your index at any time. If your database holding your index goes corrupt, just delete it all and re-replicate from your storage to your index: it’ll be re-indexed and search will work again.
								- Cons
								  collapsed:: true
									- No way to delete files via the GUI?
									  https://github.com/perkeep/perkeep/issues/1076
								- https://perkeep.org/doc/compare
								- https://github.com/perkeep/perkeep
								- https://perkeep.org/doc/
								- We do provide the Cloud Launcher to run a copy on Google Compute Engine yourself. Perkeep runs happily on desktop machines, Raspberry Pis, home servers, Amazon EC2, Google Cloud Platform, or any other cloud provider. We suggest using at least two for redundancy. Your replicas can sync amongst themselves.
								  https://perkeep.org/launch/
								- Objects, not files
								  collapsed:: true
									- Perkeep’s data model is based primarily on nameless objects. Perkeep can model traditional files with filenames and a POSIX filesystem, but it can just as happily represent a tweet or a “like” with no name. Perkeep is built as something you casually throw data into and don’t worry about organizing too much. It’s all indexed so you can search for it later. Or you can give it a name (or multiple names!) if you prefer, but you can do that whenever you want later. You can even have objects or files with multiple parent containers.
									- Many other products & services assume a file-centric view of the world. Perkeep takes the view that files are becoming less important over time. People care about backing up and searching their content, not their files. (Note that iOS went about 10 years before having a file browser or any concept of files.)
									- Because Perkeep can handle objects so well, we can import your tweets or likes or check-ins or other social media content in a more natural representation, rather than inventing files and names for everything.
								- Demo
								  https://youtu.be/8Dk2iVlc67M?t=856
							- Private IPFS network
							  collapsed:: true
								- Private IPFS network for permanently linked, hosted files
									- https://github.com/ipfs/go-ipfs/blob/master/docs/experimental-features.md#private-networks
									- https://github.com/ipfs/go-ipfs/issues/3404#issuecomment-367607230
							- Upspin
							  collapsed:: true
							  https://github.com/upspin/upspin
								- https://upspin.io/
								- Compared to Perkeep
									- Upspin is also open source, and has many similar goals. It differs in that its data model is very file-centric, with everything having a name. It has prioritized sharing between users via a global namespace and a global filesystem. See the section on Objects, not files above.
									- Upspin was announced on 2017-02-21, about 6.5 years after Perkeep (Perkeep was named Camlistore at the time).
									- There are probably interesting collaboration areas between Upspin and Perkeep. They share at least one common contributor familiar with both systems. One could imagine Perkeep users creating a share that is exported as an Upspin namespace, in the same way that Perkeep users can mount their data with FUSE.
								- Like Upspin, IPFS wants to have a global namespace and be a filesystem.
							- _Alternatives_
							  collapsed:: true
								- TagSpaces+Nextcloud for multimedia other hosted files
								- See S3/Minio
								- Or just a folder on the filesystem
									- Requires a 'Files' pane to be able to find files by size, and ones which are no longer attached to any bullet
					- Quick Capture / notational velocity
					  id:: 64243827-555b-49b0-98a5-fec08eba1ba4
					  collapsed:: true
						- ## _Shortcuts_
							- `CTRL+SHIFT+I` for Dynalist's Capture to Inbox - however this conflicts with browser's web developer tools
							- `CTRL+ALT+I` - custom hotkey for ((657b8767-8071-48fb-96df-f30379dc796b)) : ((67000f1e-0095-4728-a75d-9df2aa7fa201)) - Capture to QuickNote
							  id:: 680abbd6-9cb2-4d20-875d-01498a5c2bdb
						- ## _Implementations_
							- ((65b7e7af-d429-4b93-bb1a-33dc05bf5400))
							- ((657b8767-8071-48fb-96df-f30379dc796b)) : ((67000f1e-0095-4728-a75d-9df2aa7fa201))
							- ((64098f10-1d1d-4f4d-a2e4-1e4b7fb406a2)) : ((65f55774-9ebf-4a05-a1a7-9683cf8eadef))
							- [[Logseq]] : ((67160958-5490-42db-9b17-63b92bf36354))
							- ((657b8765-b5fd-44a1-949e-2416b257a8bd))
							- ((67000f1e-e944-453b-b4bd-cee69a8b44ec)) buffer
							- Text Triage: Drafts
							  collapsed:: true
								- Drafts is my commander-in-chief in my battle against ADHD. It effectively acts as a brain dump and processor for all things text. Every time I have something that needs to be written down, I go into Drafts, type away, and then use its powerful Actions system to send it off to whatever app will process it properly. I use it for sending ideas to my writing app or my journal app, plugging events into my calendar, creating new tasks in my todo list, sending out a tweet or Facebook message, and translating text into Spanish or Italian. Capturing text in the moment is the only way to make sure it’s still there before you’ve forgotten about it.
					- Good scrollng toolbar
					  collapsed:: true
						- It's HTML according to the flowy dev
						- _four categories of designs:_
							- Scrollable. As the name suggests, all options are horizontally listed, and the toolbar can be scrolled. The options can be loosely grouped, indicated by larger space between groups. Example: Bear.
							- Two-level. Most options on the toolbar will trigger a secondary menu. For example, after you choose “block-level items”, you can choose between “paragraph”, “heading”, or “ordered list”. Example: Google Docs.
							- Hidden options. Most frequently used options are directly accessible, whereas less used options a hidden in a “…” menu. Example: Dynalist before the toolbar revamp.
							- Customizable. You can rearrange, add, or remove options on the toolbar. There might be a fixed number of option slots on the toolbar, or you can do whatever and the toolbar will scroll.
						- Dynalist (Q4 2018)
							- 1
							  https://i.imgur.com/pVNbEuD.png
								- Unindent
								- Indent
								- Narrow/Focus/Zoom
								- Delete
								- Mark Complete
								- Edit Note area (or title if already clicking note area)
								- Set due date
								- Move bullet up by one (swap with the bullet ontop of it)
								- Move bullet down by one (swap with the bullet below of it)
							- 2
							  https://i.imgur.com/JocS0hL.png
								- Move item below X (opens a search page)
								- Add checkbox
								- Change background colour
								- Change heading style
								- Get hyperlink
						- HandyFlowy scrolling toolbar
						  source:: https://blog.workflowy.com/2016/04/21/handyflowy-workflowy/#more-1450
							- a
							  https://uc8db89bf1f1077288f75b5d9fd8.dl.dropboxusercontent.com/cd/0/get/ASnzYkHO8H8V9RvkzGfe_lElpf5yPb8OqMbUBoltobfV8IDxemVM_ix0GQRR1KuK9mJzt6Gxb_EXL-AxIIb_o_bm3hN2HOtykf6XYeXDqhyiphDNJcDD3U1B9gHY5BIQutzrp39Ws5Cdg5V3P5Ae4HyRV4-m9XUvbz6FiL3gkTes0PUsHKCEBLVIAaTw0CIvL2I/file?dl=1
								- HandyFlowy boasts a set of scrolling toolbars, which allow easy access to a range of Edit and Search buttons. The Pro version allows you to customize the order of these buttons and which you’d like to include/ exclude from the toolbar. Here’s the Edit toolbar in action:
								- DELETE and DUPLICATE whole lists with one tap
								- UNDO if you screw up… REDO if you second-guess yourself.
							- Hidden cursor swipes
							  https://ucdc73a21589fdc944046cd68d6d.dl.dropboxusercontent.com/cd/0/get/ASmE1_AojuCKNREOQ3tZ2CdRMUmsj0oQYZaUlTPpCtY7teRW9G9-x12jBBtW4HBPJ_fjv27N6p82vcIVXpSBvllOsDF34YwFWeFJH5tNOk0-F0OW66o48DO8wals7QuwF5nYJawGEWmLlGDLbyoruSrr6zUyU_rYkA7mstwcCkMpIbEnjaGxzRNBbKom508oy-Y/file?dl=1
								- TIP: HandyFlowy’s hidden cursor swipes can easily eliminate 6 of the “cursor-moving” buttons. You can swipe:
								- horizontally below your text to move your cursor left/ right,
								- ⬏ or ⬑ (across & up) to move up a list… and
								- ⬎ or ⬐ (across & down) to move down a list
							- Navigation panel
							  https://uce50c24e1b85ac8bcd543bfcb74.dl.dropboxusercontent.com/cd/0/get/ASnW1R9f5En3gN7UnVou9pqeDLJrHrMgLjzH8hrdDT3RSH04kqm3s0J_8g0YQefQKBUPdxKiZxMdYY1srY24UeWaLlLTONFrS9uTzNcA2EfKzWPSZckkoTh2gz-0ubfGJf59gZj6oodJnjdVsILWaW4lp5vSXnN6Uv4Q4RIZJZ2Ju82Alkou5UlBLQOxxRbw24E/file?dl=1
								- NAVIGATE YOUR HISTORY – Go back and forth between the lists visited and searches performed, just like on desktop
								- ZOOM OUT to a parent list
								- JUMP TO PREVIOUS/ NEXT zoomed-in sibling list
								- Go to your CUSTOM “START” LIST
								- Below I’ll demonstrate how quick it is to jump to the next zoomed-in sibling list by swiping diagonally up to the right on the navigation panel… and then I’ll go back to square one by swiping up to the “zoom out” arrow (instead of using the breadcrumb navigation links).
							- Bookmarks panel
							  https://ucfa9b10f23630f2474994bb81b6.dl.dropboxusercontent.com/cd/0/get/ASnOUXx0e21N1FEVM8TXvEMlLSmMX312Ninpyr_qMbclpufA2bNW60enEhEhpt4QjFMCPaV_nQCpR-6o4O8Y8OwzL-opV9zvtDMZJSO5PcSHr6z7mfog8u1a4dB8FWHbrnwVuRYIdGNkN028f7Iw-wyaMvEGkT-RKXVmFUmpyqHsphg2IhW_SZ7ENTp-JKS-xOg/file?dl=1
								- HandyFlowy has a slide-out BOOKMARKS panel, similar (in concept) to WorkFlowy’s starred pages menu. You can…
								- Bookmark any list or save any search
								- Nest bookmarks in folders
								- Sync your bookmarks to iCloud
							- Top bar
							  https://uce3912187e4bd72d625a0613426.dl.dropboxusercontent.com/cd/0/get/ASkjz37gzjbpZL2yqoMzJATcuqAuTnr13V8M2vOzty-YXcCUTkTFZWUhi7QJkkeNh27DgZJ5THToeeid8darBfxR5HvgMZVp3yrroqlkTFapu4gaRN4ooA1pO_aJyUzUyNyJXVAgz7UuFS4OHSGIAxMdho66hzl2_FzaziIgCjN-FU1FMu5jxxBeffA9fLL6BXo/file?dl=1
								- HandyFlowy has another interesting toolbar that I’ve kept hidden in the above GIF’s…
								- On one side it shows a TITLE BAR, which when you long-press, copies the URL of the list you’re in to your clipboard.
								- On the flip side you have 4 buttons which will either (1) expand and collapse your lists ENTIRELY… or (2) expand and collapse your lists INCREMENTALLY:
							- 1
							  https://uce3912187e4bd72d625a0613426.dl.dropboxusercontent.com/cd/0/get/ASkjz37gzjbpZL2yqoMzJATcuqAuTnr13V8M2vOzty-YXcCUTkTFZWUhi7QJkkeNh27DgZJ5THToeeid8darBfxR5HvgMZVp3yrroqlkTFapu4gaRN4ooA1pO_aJyUzUyNyJXVAgz7UuFS4OHSGIAxMdho66hzl2_FzaziIgCjN-FU1FMu5jxxBeffA9fLL6BXo/file?dl=1
								- VIEW MODE: That open lock button on the bottom toolbar, when pressed, locks editing temporarily – and you can scroll through your lists without inadvertent keyboard popups
					- Timestamps
					  collapsed:: true
						- Org-mode allows start (scheduled) and end dates (deadline)
							- Also allows as many timestamps as desired in note content
					- Tabbed left pane for filtering into task views as well as bookmarks
					  collapsed:: true
						- Todoist - Add a left pane in Dynalist to show only tasks (items with checkmarks)
						  http://i.imgur.com/ZlRW6m1.png from http://2doapp.com/
							- _Items_
								- _Main items_
									- All / My Tasks
									  i.e. show only checklists/bullets with checkmarks
									- Today (and Overdue)
									- Next 7 Days (or just create ability to set whatever you want via search operators)
									- Scheduled
									  i.e. All, but they have to have a due date
										- Opposite of this is 'Inbox'
									- Done
								- Tags e.g. #dailies
								  Show all tags for 'All' list
									- e.g. priority1/p1, blocked, etc
								- Filtering
								  Select different combos of tags (or -tag to not have it) and ability to save these search views as bookmarks
							- _Additional options_
								- Flatten results
								  https://trello-attachments.s3.amazonaws.com/557bc9fae857201432096ec9/57e291b8d5e0357ab19e5f3b/364ea5e6e48a18b715524dc2fb732e86/upload_4_5_2017_at_12_52_11_PM.png
								- Add a task at the bottom - puts it into the Inbox
								  https://i.imgur.com/PIClbE7.png
							- _Concepts_
								- Orgzly
								  https://imgur.com/a/FfI8WV1
									- "Searches" lets you define those 4 shortcuts and reorder them
								- Todoist
								  https://i.imgur.com/fhEOxsO.png
								- Astrid Tasks web app-like
								  https://i.imgur.com/PIClbE7.png
									- Basically the same as the mobile app - 3 panels (tags; list of tasks; a selected task). Add a task and Add a comment at the bottom of 2nd and 3rd panels
						- Dynalist tabbed left pane - My files, Bookmarks, Tags (Pro)
						  https://i.imgur.com/7xdBz0S.png
				- _Replace _
				  collapsed:: true
					- Dynalist / Tasks - recurring, and adjustable reminders
					  intralink2:: https://workflowy.com/#/c38e72ec9edf
					- [[Software]] : [HabitHub](((664c986c-8374-46fc-a227-0c701c9e275c)))-like calendar history for recurring tasks (see Tasks app spec)
					- [columns] Airtable - (relational database) with Org-mode or Calculist draft spreadsheets
					  collapsed:: true
						- Why
						  collapsed:: true
							- Otherwise have to interlink or clone much more frequently
							- _Examples which are better in databases than lists_
								- Documents like recipes, schedules, and budgets aren’t expressed effectively as outlines
								- Supplements would be better in a database than a list - this way it can be present in multiple lists for goals
								- Contacts - to see more info at a glance yet still hide majority in infinite hierarchical list
								- Food plan and recipes - sort by price, macros, goals, time to prepare etc
						- Concepts
						  collapsed:: true
							- How data should be stored for a table in an outliner view
								- A) All text should be stored as tuples (one item per record)
								  collapsed:: true
									- Pros/Cons
										- Pros
											- Records are easily linked together in outline view
										- Cons
											- Difficult to define field type
									- Example
										- Table title [∆]
										  (the triangle icon is a button which opens below as a table)
											- Name|||Age|||Sex
											- John|||20|||M
											- Marie|||21|||F
								- B) Table stored in tree view (1st level sibling bullets are column titles, their children are the relevant column items)
								  collapsed:: true
								  https://i.imgur.com/RZmdHzC.png
									- Pros/Cons
										- Pros
											- Easier to define field types
										- Cons
											- Records are not linked together except in Table View
									- Example
										- Table title
											- Name
												- John
												- Marie
											- Age
												- 20
												- 21
											- Sex
												- M
												- F
								- C) Table stored in tree view (children of 1st bullet are the column titles, the next sibling bullet is the 1st column data and it's children are other column data etc)
								  collapsed:: true
									- Pros/Cons
										- Pros
											- Records are easily linked together in outline view
										- Cons
											- Less intuitive than (B)
											- Unsure how easy it is to define field types
									- Example
										- Table title
											- Name
												- Age
												- Sex
											- John
												- 20
												- M
											- Marie
												- 21
												- F
								- D) See Tag Attributes
								  collapsed:: true
								  e.g. Airtable/Notion (database) FOSS alternative e.g. SlickGrid #001-type:utility #001-type:privacy #001-p1
									- Make search able to
							- 1) Dynalist-like bullet right-click menu - has "Open table editor"
							- Bullets which have these additional hidden fields get a 'table' icon at the end of the text (just before Dynalist due date icon)
							- Table editor view
								- v1 - Table View
								  https://i.imgur.com/RZmdHzC.png
								- v1.1 - Field types
									- This is a hidden attribute for every bullet (default: single line text)
									- Setting field type chooses it for every child item of the parent (assuming data is stored in tree view not tuples)
								- v1.5 - Add filtering
								  https://i.imgur.com/PLEdooB.png
								- v2 - Save multiple views (this + filtering allows useful ways of sorting databases
								  https://i.imgur.com/uU345NJ.png
								- v2.1 - Sorting and drag-and-drop reordering
								- v2.2 - Hide columns (temporarily)
							- Some way to assign field type
						- Examples
						  collapsed:: true
							- Calculist
							  #Outliners https://workflowy.com/#/0ec25c24b154
							- Org-mode spreadsheet
							  intralink2:: https://workflowy.com/#/01b3d5d89d56
							- Airtable
							  #Software https://workflowy.com/#/48aafcd815ef
							- Dynalist - columns
							  https://trello.com/c/06RIufbM/91-adding-columns-to-items
							- WorkFlowy tables
							  https://workflowy.zendesk.com/hc/en-us/community/posts/360001796923-Tables-?page=1#community_comment_360000609606
							- See OmniOutliner
							- TreeLine - data editor (for database functionality)
							  intralink2:: https://workflowy.com/#/2068c66958f1
								- Concept
									- 2) Show a pop-up that is like uTracker's Modify Tracker screen for editing single records
					- Anki - copy the Anki+Airtable model
					  collapsed:: true
					  #MetaLearning https://workflowy.com/#/15217543ec98
						- Why
							- Much easier to manage Anki flashcards using a table similar to Airtable
							- I don't have to duplicate data twice - just have it copy my outliner notes into it
						- Example Airtable
						  https://i.imgur.com/fVnMbTK.png
						- Example of use
							- _Database side_
								- There would be a document with the default Table/Database view
								- One of the fields (columns) is "Interlink" which would link to the full version of bullet point, and this would be linked both ways
								- The other fields would be the content that is relevant. Basically a summary of what is on the main cards
								- OR I could use interlinks for some of the field data and have it simply print off the anchor text (this way I don't have to keep updating it too)
							- Anki view translation
								- It would copy the data into Anki fields, from there I can easily choose the card template I want to use
					- _Not yet wireframed_
					  collapsed:: true
						- Asana - inbox (notifications feed), assign, comments
						- NachApp - sidebar for switching to To-Do/agenda view; calendar view; Tracker view (graphs, daily progress etc)
						  https://i.imgur.com/dus6YoZ.png source:: https://nachapp.com/
							- To-do list/agenda view
							  https://i.imgur.com/OGGtSfD.png
							- Calendar view
							  https://i.imgur.com/DDwhtnp.png
							- Tracker1
							  https://i.imgur.com/IiT0O50.png
							- Tracker2
							  https://i.imgur.com/dReFssW.png
							- Graph1
							  https://i.imgur.com/VwqZaSL.png
							- Graph2
							  https://i.imgur.com/nYU6lMf.png
				- _Unused currently but useful_
				  collapsed:: true
					- Revision History
						- http://talk.dynalist.io/t/pro-feature-revision-history/25/12
					- Embedded iframes for many useful apps (Google Sheets, images, videos, issue tracker etc)
					  Only for view-only really
						- Disable Nextcloud X-Frame-Options header
						  https://docs.nextcloud.com/server/9/admin_manual/configuration_server/harden_server.html#serve-security-related-headers-by-the-web-server
					- Dynalist Powerpack
					  http://talk.dynalist.io/t/powerpack-2/977
					- Pomodoro timers
					- Zotero Connector integration
						- Save references to Zotero from your web browser
						  https://chrome.google.com/webstore/detail/zotero-connector/ekhagklcjbdpajgpjgmbionohlpdbjgc/reviews
					- TiddlyWiki for rich text
					- Org-mode functionality
						- org mode is awesome
						  https://www.youtube.com/watch?v=fgizHHd7nOo
					- Command mode in Calculist (for stuff which hasn't got a GUI option yet)
					- TreeSheets
					  http://strlen.com/treesheets/docs/images/screenshots/screenshot_todo.png / http://strlen.com/treesheets/
				- **More**
				  collapsed:: true
					- Comments pane + a small area between notes + title area indicating no. of comments +
						- Progress counters / completion %
						- Task delegation
						- Start + due/ETA date (allows for Gantt chart view)
					- Calendar view (see Asana, Airtable) to see when tasks are due
						- Also outliner version - i.e. a flat search view with headers for due date
						- http://i.imgur.com/JMmiqJm.png
					- Checkvist + Dynalist keyboard shortcuts
						- Checkvist
						  [archived] https://checkvist.com/assets/cv_keyboard.pdf
					- "Watch changes" notifications i.e. Asana Inbox
					- Zapier integration (integrate with anything on public cloud)
					-
				- _[Learning Resources]_
				  collapsed:: true
					- Digital Tools I Wish Existed
					  collapsed:: true
					  [https://news.ycombinator.com/item?id=25228089](https://news.ycombinator.com/item?id=25228089)
						- Queue management for inbound digital content
							- Where to begin? Probably the most common problem I see myself and other people dealing with is processing the incoming deluge of articles to read and videos to watch. This isn’t all personal recommendations - it encompasses any and all content I think my future self would appreciate me consuming. A list of issues, roughly by order of appearance:
								- Content (or links to it) arrive from a variety of sources including text messages from friends, email conversations, tweetstorms and replies, references in books, suggestions in real-world conversations, and more.
								- Every book, article, post, or tweet has the potential to lead to more content.
								- Content is published in a variety of formats including but not limited to images, sound files, videos, Google Drive docs, diagrams, long-form paywalled articles, PDFs, powerpoint presentations, and base 64 encoded blobs.
								- I have little visibility into required time investment and foundational context until I’ve opened it and started thinking about it. Should I sit down with a pen and paper to read this or can I skim it while waiting for my coffee?
								- Learning, work, news, and entertainment all have different priorities in my life (roughly in that order).
								- I would like to batch process content in different “streams” regardless of where they are stored. For example: I have two hours, let me work through interesting text content my friends sent me last week. Or: show me all the interesting/relevant videos I’ve queued over the past month.
								- I’m not always connected to a stable internet connection.
								- If it’s a long piece of content I want my position saved reliably so I can resume at a later point.
								- I often want it in a different format than the one it was originally published in (audio → text, text → audio, pdf → ebook). Automated conversion works but is cumbersome. Listening to text articles requires sending them to a special app and converting articles to ebooks is annoying and loses a lot of formatting and navigation.
								- I love to respond to a person’s recommendation - preferably before they’ve forgotten why they sent me it in the first place.
								- I’d like a centralized history of content tied to my notes and annotations in case I want to find it again later. It feels like every week I’m speaking with someone and I remember a blog post I read a few months ago they might find relevant … or was it a Reddit post? Can I find it my history? Oh no, it’s been replaced with [deleted] … find an archived copy… rinse and repeat.
							- Following my curiosity feels like chasing a caffeinated bunny around while real understanding requires time, perspective, and reflection. The internet makes the former much easier - so I find myself constantly balancing the two. Additionally, my energy and attention levels vary throughout the day and it’s far easier to just open Twitter rather than continue reading a long-form article I started on my laptop two days ago. Too often I default to the lower-friction one.
							- Honorable Mentions: Pocket, Instapaper, [Zotero](https://workflowy.com/#/935fa4d3e496)
						- A universal book log, recommendation & sharing system #
							- I love exploring other peoples’ reading lists. Here’s my own. I find everyone keeps their reading lists in different formats on different platforms. Plaintext lists are nice but hard to parse. Spreadsheets are easy to parse but a pain to manage. Third-party services aren’t interoperable, require logins, and are not future-proof.
							- Part of the problem here is metadata is hard. Someone has to sit there and fill out the author, title, subtitle, summary, page count - and they’re probably not going to do it for free. Amazon is a good at it but is hostile to publishers. Goodreads has much potential but seems to have stagnated. Linking to the book’s Wikipedia entry would be my preference but very few books have an entry.
							- Whatever this tool for managing my ever-growing reading list will be, it should:
								- Let me compare my reading list with another to see overlap. I find this a wonderful way to spark conversation and find common interests.
								- Allow me to tag books instead of placing them into static lists (think clusters or tag clouds).
								- Be tied to my highlights, annotations, and bookmarks in a non-proprietary, searchable, and shareable format. Make them public if I want to.
								- Save context on where and when I found this book: why I thought it was important to read, when I read it, what I wrote down while reading it, and what other content I discovered through it.
								- Let me query this tool like a relational database. For example: show me all books about scaling startups recommended by people I follow on Twitter or by people they follow. The current Twitter search makes me feel like I’m using a government site created before I myself even knew what a computer was.
								- Help me deal with prioritization. My reading list is a mess and I can’t be alone. Are certain books better read before others? Prerequisites? Could three of them be replaced with one? What are the other books by the this author? Are they worth reading too? Why exactly did I think reading this 800 page book was relevant when I added it? Is 80% of the content attainable from a blog post? Where is that post? Has someone in my network written a rebuttal to the ideas in this book? The list goes on and on.
								- Provide relevant suggestions with the typical recommender approach based on what people interested in the same topics also enjoyed reading and learning from.
							- Honorable Mentions: None :(
						- Intelligent PDF viewers, eBook readers, audiobook & podcast players
						  [https://d33wubrfki0l68.cloudfront.net/5aa98bca712e33bc729c180c9a588f4d5ac7e9af/c5011/digital-tools/ebook-concept.png](https://d33wubrfki0l68.cloudfront.net/5aa98bca712e33bc729c180c9a588f4d5ac7e9af/c5011/digital-tools/ebook-concept.png)
							- Reading is incredible and I love my Kindle. But eBooks today are just a step above OCR’ing a book and slapping on a few basic features which have existed for 30+ years. While I’m reading an eBook I want to:
								- Have relevant illustrations, graphs, and tables appear for duration of their mentions so I don’t have to flip back and forth between them.
								- See glossary terms and their definitions which appear on this page. Highlighting and searching a term is great but the author may have added important context to the glossary definition.
								- View popular annotations and highlights across all mediums - not just by other readers who own an Amazon Kindle readers and purchased this book version and also happened to highlight it enough times. A quote was referenced in 300 blog articles? A two sentence excerpt retweeted 50,000 times? You bet I want to know!
								- Follow referenced information easily. You cited a paper - great, let’s look at the footnotes. Oh, the full reference is in the back of the book. Online list of citations? Of course not! Drop a bookmark, navigate to the back of the book, pull out my laptop, find the paper. Of course, a paywall. Grab a snack. Acquire the PDF. Search for keywords to try to find the referenced information. Sigh, 2019.
								- Not be hindered by the DRM system. Copyright is important and I want to support authors but it’s insane to me all these content licenses I’m acquiring can’t be donated to a library upon account closure. Yes, legal DRM-free eBooks exist but they aren’t without their own issues.
								- Seamlessly switch between devices and formats while retaining my position. Something like Whispersync (a neat idea but come on, I’m not made of money. Also, see above points).
								- Let me use a digital or physical keyboard instead of an e-ink keyboard to type my annotations. A possibility here is a companion app, which feels like a notes app but ties my notes to their location/text in the book I’m reading.
							- Audiobook player
							  [https://d33wubrfki0l68.cloudfront.net/7bc95c0c51628e5ba06ddb7e688a58c600e503c8/81599/digital-tools/audiobook-player.png](https://d33wubrfki0l68.cloudfront.net/7bc95c0c51628e5ba06ddb7e688a58c600e503c8/81599/digital-tools/audiobook-player.png)
								- Most of these points above also apply to my experience listening to podcasts, audiobooks, and watching Youtube videos and interviews. I find myself wishing I could:
									- Navigate them more comfortably. Both Libby and Audible leave much to be desired in terms of navigation. Finding a quote I remember hearing to three days ago is basically blindly stumbling around - and I lose my current spot too. Seeing a list of chapter numbers for the book I’m listening to has been helpful a grand total of 0 times. And how cool would it be to drop a bookmark from my bluetooth-connected headphones as I’m biking down a street.
									- View an auto-generated transcript of a podcast as I’m listening to it. It should have easy-to-follow links to references to other podcasts, media, books and support searching for key terms. YouTube already transcribes all of their videos and Google Meet now generates live captions as we’re talking - why can’t we do something similar with podcast apps?
								- Honorable Mentions: [Readwise](https://readwise.io/), <a href="https://www.weavatools.com/">Weava</a>, <a href="https://www.descript.com/">Descript</a>, <a href="https://otter.ai/">Otter.ai</a>, <a href="https://getpolarized.io/#features">Polar</a>
						- A centralized search interface for my digital brain (memex) #
							- I want to be able to open an interface, type three words, and instantly see results from everything my digital self has interacted with. Emails, years of full-text browsing history, text messages, Slack messages across all my organizations, calendar invites and events, books, podcast transcripts I’ve consumed, Twitter and Instagram DMs, PDFs I’ve downloaded, bash commands, videos I’ve seen, my online and offline files, notes, blog post drafts - I really do mean everything.
							- I acutely feel the need for this when I’m trying to find something I know I’ve seen online but can’t remember where I saw it. Google is wonderful for finding new information, but absolutely poor for re-finding things. Chrome’s history has so much potential - but I suspect Google would much rather have us look at their ads a few additional times rather than go direct to the source. I accept I might be in the minority on this one. Regardless, this tool should:
								- Accept and parse the following queries:
									- spacex announcement type:video 2016
									- links from:jon@test.org topic:python
									- paper on temperature, productivity referenced in book:Uninhabitable Earth
									- type:pdf habits digital interfaces
									- reading comprehension type:blog post
									- printer ink receipt
									- type:book read:2017 finance
									- file:py datetime parse
								- Respect my privacy: hosted on something I control and never mined for ads.
								- Support all my devices with two-way sync so I can search and add to it wherever I am.
								- Be extensible: allow me to easily ingest my own information and extend with desired functionality.
								- Cluster information based on content, tags, geo-location, connected people, conversations, source, and other factors I’m not even aware of.
								- Notify me about changes to documents and webpages I’ve visited.
								- Allow a rough export of my research on a topic (like, a knowledge dump off everything I’ve consumed on pandas) with the ability to easily share it.
							- Honorable Mentions: [Memex by Worldbrain.io](https://worldbrain.io/), <a href="https://roamresearch.com/">Roam Research</a>, <a href="https://www.notion.so/">Notion</a>, <a href="https://coda.io/welcome">Coda.io</a>, <a href="https://www.alfredapp.com/">Alfred</a>, <a href="https://trovenow.com/">Trove</a>, <a href="https://localnative.app/">Local Native</a>, <a href="https://github.com/pirate/ArchiveBox">ArchiveBox</a>, <a href="https://raindrop.io/">Raindrop</a>
					- https://www.reddit.com/r/productivity/comments/5p5upr/i_wrote_about_all_of_the_apps_i_use_every_day_to/
					- https://www.amazingmarvin.com/sneak-peek
					  collapsed:: true
						- Dashboard
						  http://i.imgur.com/Z2zzpS8.png
						- Features 1
						  http://i.imgur.com/kEqqnMo.png
						- Features 2
						  http://i.imgur.com/9VnGmQ0.png
						- Plugins
						  http://i.imgur.com/vn8CtdL.png
						- To Do List sections
						  http://i.imgur.com/IlZWzAy.png
						- Time blocking
						  http://i.imgur.com/D3uoK5Z.png
						- Time estimates
						  http://i.imgur.com/nwFzDiq.png
						- Time tracking
						  http://i.imgur.com/4LhDbxf.png
						- Project prioritisation
						  http://i.imgur.com/PIEP2HW.png
						- Custom task labels
						  http://i.imgur.com/bGATaeK.png
						- Task jar
						  http://i.imgur.com/K6TJuPz.png
						- Scheduled rewards
						  http://i.imgur.com/6BpiZDN.png
						- Sand and pomodoro timers
						  http://i.imgur.com/DVI51O4.png
						- Super Focus Mode
						  http://i.imgur.com/D1rH2i8.png
						-
					- http://talk.dynalist.io/c/showcase
	- Outliners
	  id:: 62e283e5-ce69-4a9b-97e2-9be105f7ff35
	  collapsed:: true
	  #Outliners
		- _Proprietary_
			- WorkFlowy
			  id:: 6313462d-10af-4744-92d2-041a06816d23
			  collapsed:: true
			  #WorkFlowy | Outliner
				- WorkFlowy Search Operators
				  collapsed:: true
					- **Documented Search Operators**
					  collapsed:: true
					  https://blog.workflowy.com/2012/09/25/hidden-search-operators/
						- Use spaces to combine search terms, implying "AND"
						  #tag @tag
						- OR (must be CAPS with leading and trailing space)
						  #tag OR @tag
						- Quotes search for exact strings (spaces no longer interpreted as "AND") Also use to find strings inside of strings.
						  "find this exact string"
						  "ring" will match **ring** and st<b>ring</b> and sp<b>ring</b>s
						- Completed items
						  is:complete
						- NOT this: Prepend search terms with "-"
						  -#tag -is:complete
						- Items you have shared
						  is:shared
						- Items others have shared & you have added
						  is:embedded
						- Edited in the last x time unit  (h = hours, d = days, m or (none) = minutes)
						  changed:30d
					- ** Undocumented Search Operators ("undocumented" = may go away)**
					  collapsed:: true
						- Completed in the last x time unit  (h = hours, d = days, m or (none) = minutes)
						  completed:30d
						- Items with notes
						  has:note
						- Items last changed by you (useful with Shared outlines)
						  changed-by:me
						- Items last changed by other users (useful with Shared outlines)
						  changed-by:others
						- Items edited since a specific date (mm/dd/yyyy) #datesFeatureBrokeThese
						  last-changed-since:01/31/2018
						- Items edited before a specific date (mm/dd/yyyy) #datesFeatureBrokeThese
						  last-changed-before:01/31/2018
						- Items completed since a specific date (mm/dd/yyyy) #datesFeatureBrokeThese
						  completed-since:01/31/2018
						- Items completed in February 2018 #datesFeatureBrokeThese
						  completed-since:02/01/2018 -completed-since:03/01/2018
				- Pros/Cons
				  collapsed:: true
					- Pros
						- Core part of ((62d05f36-5b1b-4969-99e8-540017192620))
						- Mirroring (transclusion/virtual clone instances of items elsewhere in doc)
						- [[ for quick intralinking
						- Dates
						  id:: 65af7eeb-67ea-49d7-a4d5-fe4b794f8c2f
						  collapsed:: true
							- Pros/Cons
								- Pros
									- Supports date ranges
									- Supports semantic dates
										- Shortcuts like, “now”, “today”, “tomorrow”, “next week”, “last week”, “two months from now”
								- Cons
									- Doesn't support "last month", "last week" etc
									- Doesn't support "overdue" natively, but you can do it via`1/1/10-now`
									- Only supports MM/DD/YYYY at the moment
										- * Note: We’re using a month/day/year format by default, and haven’t added day/month/year used in much of the world. We’re sorry, we wanted to add this but it added a bunch of complexity we weren’t ready to take on yet. If you aren’t in the US, we recommend using a year/month/day format, and we hope to be able to let people choose their own format sometime soon
										  source:: [https://blog.workflowy.com/2019/12/30/dates-in-workflowy-try-it-out/](https://blog.workflowy.com/2019/12/30/dates-in-workflowy-try-it-out/)
						- Images and file attachments/embeds
					- Cons
						- Lacks
							- Usability
							  collapsed:: true
								- Quick Add to Inbox
								  [https://workflowy.zendesk.com/hc/en-us/community/posts/360002310283-Quick-Add-to-Inbox-mostly-app-support-?page=2#comments](https://workflowy.zendesk.com/hc/en-us/community/posts/360002310283-Quick-Add-to-Inbox-mostly-app-support-?page=2#comments)
								- WorkFlowy Web Clipper on Firefox (Chrome-only at the moment)
									- [https://blog.workflowy.com/2020/07/20/workflowy-web-clipper-a-smoother-way-to-research/](https://blog.workflowy.com/2020/07/20/workflowy-web-clipper-a-smoother-way-to-research/)
									- [https://addons.mozilla.org/en-GB/firefox/search/?q=workflowy](https://addons.mozilla.org/en-GB/firefox/search/?q=workflowy)
								- click to search
								  https://workflowy.zendesk.com/hc/en-us/community/posts/360012940423-Option-to-click-enter-to-search-stop-instant-search-?mobile_site=true
								- lazy loading
								  [https://workflowy.zendesk.com/hc/en-us/community/posts/360012936143-Lazy-Loading-faster-start-up-?mobile_site=true](https://workflowy.zendesk.com/hc/en-us/community/posts/360012936143-Lazy-Loading-faster-start-up-?mobile_site=true)
							- Features
							  collapsed:: true
								- Code blocks and syntax highlighting
								  collapsed:: true
								  [https://workflowy.zendesk.com/hc/en-us/community/posts/360032397131-Code-Formatting?page=1#community_comment_360013740212](https://workflowy.zendesk.com/hc/en-us/community/posts/360032397131-Code-Formatting?page=1#community_comment_360013740212)
									- workflowyCodeFormatter 3rd party extension
										- [https://github.com/ryanpcmcquen/workflowyCodeFormatter](https://github.com/ryanpcmcquen/workflowyCodeFormatter/blob/master/README.md#what-happened-to-syntax-highlighting)
										- _Issues_
											- Can't change colour for it to be red like Dynalist code highlighting
											  [https://github.com/ryanpcmcquen/workflowyCodeFormatter/issues/22](https://github.com/ryanpcmcquen/workflowyCodeFormatter/issues/22)
											- It uses brightness-based syntax highlighting, but doesn't alter colours
												- Uses Microlight for code highlighting. This alters brightness but not colour. It's slightly more readable than no highlighting, but worse than
												  [https://github.com/ryanpcmcquen/workflowyCodeFormatter/blob/master/README.md#what-happened-to-syntax-highlighting](https://github.com/ryanpcmcquen/workflowyCodeFormatter/blob/master/README.md#what-happened-to-syntax-highlighting)
									- _See_ [Code highlighting via Dynalist Powerpack](https://workflowy.com/#/42804140846b)
								- Push notifications (mobile + desktop) for dates
								  https://workflowy.zendesk.com/hc/en-us/community/posts/360001403723-Calendar-Agenda-Dates-Something-please-
								- End-to-end encryption
								  [https://workflowy.zendesk.com/hc/en-us/community/posts/360028638051-End-to-end-encryption-](https://workflowy.zendesk.com/hc/en-us/community/posts/360028638051-End-to-end-encryption-)
								- Tables
								  collapsed:: true
								  https://workflowy.zendesk.com/hc/en-us/community/posts/360001796923-Tables-?mobile_site=true
									- Or just use a [Spreadsheet-based](https://workflowy.com/#/1a412c3542d2) app?
								- Flatten search results
								  collapsed:: true
								  id:: 63503860-56e3-4797-bb65-3dc9a1168bd9
								  [https://workflowy.zendesk.com/hc/en-us/community/posts/360019009791-A-Plea-for-Flat-Search-Results](https://workflowy.zendesk.com/hc/en-us/community/posts/360019009791-A-Plea-for-Flat-Search-Results)
									- 1 Backlink
										- _Related:_ [Flatten search results](https://workflowy.com/#/58529478cb8d)
										  #WorkFlowy
								- Point in time restore (Git based?)
								- [Knowledge graph](https://workflowy.com/#/9fa7685f5ac4)-like visual overview of linked items
				- [Blog](https://blog.workflowy.com/)
				- Features
					- Bulletpoints
					- Collapsible or folding areas, with infinite nesting hierarchy
					  collapsed:: true
						- Uses code-folding
						- http://tibleiz.net/code-browser/code-folding.html
					- Drag-and-drop + shortcuts makes outlining very quick
					- Easy to import notes + export to other formats
					  collapsed:: true
						- No lock-in in case I want to move to a newer and more suitable app in future
					- Auto-save
					- WorkFlowy featuers
					- https://blog.workflowy.com/category/feature-announcement/
					- Embedding workflowy lists
					  collapsed:: true
						- http://entulho.fiatjaf.alhur.es/guias/how-to-embed-workflowy-lists-in-your-website/
						- Example
						- https://websitesfortrello.github.io/classless/
					- hoisting (where you zoom in on only part of the outline
				- Database SOP
				  collapsed:: true
					- See example #001 ((633b7546-8735-4803-8694-43f949258c50))
					- Create child bullets:
					  collapsed:: true
						- Filtering criteria
						  Most used: #001-p1
							- Priority: #001-p1 #001-p2
							  The lower, the higher the priority
						- Filtered table #001
							-
					- Find-and-replace bookmarklet (see Bookmarks folder)
					  source:: https://blog.workflowy.com/2018/09/13/find-and-replace/
					  collapsed:: true
						- Javascript code
						  javascript:(function FR_1_5(){function toastMsg(str,sec,err){WF.showMessage("<b>"+str+"</b>",err);setTimeout(function(){WF.hideMessage()},(sec||2)*1e3)}function applyToEachItem(functionToApply,parent){functionToApply(parent);for(let child of parent.getChildren()){applyToEachItem(functionToApply,child)}}function findMatchingItems(itemPredicate,parent){const matches=Array();function addIfMatch(item){if(itemPredicate(item)){matches.push(item)}}applyToEachItem(addIfMatch,parent);return matches}function getItemsWithVisibleMatches(parent){return findMatchingItems(function(item){let itemTree=item.getProjectTreeObject();if(itemTree){let isVisible=WF.completedVisible()||!item.isCompleted();return itemTree.search_result&&itemTree.search_result.matches&&isVisible}},parent)}function escapeForRegExp(str){return str.replace(/[-\[\]{}()*+?.,\\^$|#]/g,"\\$&")}function%20countMatches(items,rgx){let%20matchCount=0;items.forEach(item=>{let%20result=item.getProjectTreeObject().search_result;if(result.nameMatches){let%20nameMatch=item.getName().match(rgx);if(nameMatch)matchCount+=nameMatch.length}if(result.noteMatches){let%20noteMatch=item.getNote().match(rgx);if(noteMatch)matchCount+=noteMatch.length}});return%20matchCount}function%20replaceMatches(items,rgx,r){WF.editGroup(function(){items.forEach(item=>{let%20result=item.getProjectTreeObject().search_result;if(result.nameMatches)WF.setItemName(item,item.getName().replace(rgx,htmlEscapeTextForContent(r)));if(result.noteMatches)WF.setItemNote(item,item.getNote().replace(rgx,htmlEscapeTextForContent(r)))})});r===""?WF.clearSearch():WF.search(tQuery.replace(find,r))}function%20showFindReplaceDialog(b,t,b1,b2,di){const%20style='#inputBx{width:95%;height:20px;display:block;margin-top:5px;border:1px%20solid%20#ccc;border-radius:4px;padding:4px}.btnX{font-size:18px;background-color:#49baf2;border:2px%20solid;border-radius:20px;color:#fff;padding:5px%2015px;margin-top:16px;margin-right:16px}.btnX:focus{border-color:#c4c4c4}';const%20box=`<p><b>Replace:</b><input%20value="${htmlEscapeText(di)}"%20id="inputBx"%20type="text"%20spellcheck="false"></p>`;const%20buttons=`<div><button%20type="button"%20class="btnX"%20id="btn1">${htmlEscapeText(b1)}</button><button%20type="button"%20class="btnX"%20id="btn2">${htmlEscapeText(b2)}</button></div>`;WF.showAlertDialog(`<style>${htmlEscapeText(style)}</style><div>${b}</div>${box+buttons}`,t);setTimeout(function(){let%20userInput;const%20inputBx=document.getElementById("inputBx");const%20btn1=document.getElementById("btn1");const%20btn2=document.getElementById("btn2");inputBx.select();inputBx.addEventListener("keyup",function(event){if(event.key==="Enter"){btn1.click()}});btn1.onclick=function(){userInput=inputBx.value;WF.hideDialog();setTimeout(function(){replaceMatches(Matches,rgx_gi,userInput)},50)};btn2.onclick=function(){userInput=inputBx.value;WF.hideDialog();setTimeout(function(){replaceMatches(Matches,rgx_g,userInput)},50)}},100)}if(!WF.currentSearchQuery()){return%20void%20toastMsg('Use%20the%20searchbox%20to%20find.%20<a%20href="https://workflowy.com/s/C7C.M60IuWhoJq"%20target="_blank">Click%20here%20for%20more%20information.</a>',3,true)}const%20tQuery=WF.currentSearchQuery().trim();const%20Matches=getItemsWithVisibleMatches(WF.currentItem());const%20isQuoted=tQuery.match(/(")(.+)(")/);const%20find=isQuoted?isQuoted[2]:tQuery.includes("%20")?false:tQuery;if(find===false){if(confirm('The%20search%20contains%20at%20least%20one%20space.\n\n1.%20Press%20OK%20to%20convert%20your%20search%20to%20"exact%20match".\n\n2.%20Activate%20Find/Replace%20again.')){WF.search('"'+tQuery+'"')}return}const%20Title="Find/Replace";const%20modeTxt=isQuoted?"Exact%20Match,%20":"Single%20Word/Tag,%20";const%20compTxt=`Completed:%20${WF.completedVisible()?"Included":"Excluded"}`;const%20findTxt=isQuoted?isQuoted[0]:tQuery;const%20body=`<p><b>Mode:</b><br>${modeTxt+compTxt}</p><p><b>Find:</b><br>${htmlEscapeText(findTxt)}</p>`;const%20findRgx=escapeForRegExp(htmlEscapeTextForContent(find));const%20rgx_gi=new%20RegExp(findRgx,"gi");const%20rgx_g=new%20RegExp(findRgx,"g");const%20allCount=countMatches(Matches,rgx_gi);const%20caseCount=countMatches(Matches,rgx_g);if(allCount>0){showFindReplaceDialog(body,Title,`Replace:%20All%20(${allCount})`,`Replace:%20Match%20Case%20(${caseCount})`,find)}else{WF.showAlertDialog(body+"<br><br><i>No%20matches%20found.</i>",Title)}})();
				- Extensions
				  collapsed:: true
					- WFx
					  collapsed:: true
						- WFx: A Browser Extension That Helps You Use WorkFlowy More Productively
						- [https://blog.workflowy.com/2019/08/07/wfx/](https://blog.workflowy.com/2019/08/07/wfx/)
						- Features
							- List Jumping - type in "CE" in a pop-up and clicking enter will take you to a new specific bullet. OR set it to a webpage. OR since it's a web extension, type it while you're looking at a non-workflowy webpage
								- It'll also check if a tab is already open for that webpage and use that instead
							- Global Search (rather than only searching through child items
							- PowerPack (premium features)
								- Move to List (move an item to a specific list, type in eg "11" in the prompt)
								- Move to Child
								- Move to Star - select multiple items to move under a starred item
								- Find-And-Replace
								- Multi-Tagger - select multiple items, add tags them all at once (notes area or as separate children?)
								- Reset Checklist (incomplete them all
								- Adding Machine - adds totals to child items calculated from the sum of grandchild items
								- Word/Character Count - of everything under an item
								- Tag Counter - number of times the tag has been used, underneath a particular item
								- Tag Index - show all the tags used underneath a particular item (shows it in the approx Notes area)
								- Numbered Bullets
				- WorkFlowy embed
				  collapsed:: true
					- What
					  collapsed:: true
						- An iFrame is an inline frame used inside a webpage to load another HTML document inside it. This HTML document may also contain JavaScript and/or CSS which is loaded at the time when iframe tag is parsed by the user’s browser.
					- WorkFlowy itself embedded
					  collapsed:: true
						- Why
							- When you load WorkFlowy in a new tab, it will load all of your lists (That’s why it’s so blazing fast to get around)… so it’ll take a couple of seconds depending on how large your entire account is. Now when you load a shared list, it loads just that list and no other. So it loads quicker than normal – even with my background image. That there makes it practical enough for me to temporarily open a new tab with my “Notepad” when I want to jot a random idea down. I can then shut it down if I want when I’m done.
						- Use PhraseExpress to open notepad WorkFlowy
							- Finally, if you’d like to set up a custom keyboard shortcut that opens a shared list in a new tab, one possibility would be the “freemium” PhraseExpress. You can then create a new phrase and tell it to open a specific web page: Options gears > Automation > Open a web page. Insert your shared list URL and choose a Keyboard shortcut:
							  http://i.imgur.com/3uq0fYY.png
							- https://blog.workflowy.com/2016/08/24/shared-list-use-cases/#more-2166
						- Code
							- `<iframe src="ShareURLWorkflowyGives" width="800" height="400"></iframe><br>`
					- IFrames embedded in WorkFlowy
					  collapsed:: true
						- https://blog.workflowy.com/2016/06/09/iframe-in-workflowy/
						- IFRAME EMBED INSTRUCTIONS
						  
						  Permalink for the corresponding WorkFlowy blog post: 
						  https://blog.workflowy.com/2016/06/09/iframe-in-workflowy
							- **1. INSTALL TAMPERMONKEY**
								- Install an extension called TamperMonkey (Chrome/ Safari/ Firefox/ Opera/ Dolphin Browser/ UC Browser):
									- https://tampermonkey.net/?ext=dhdg&browser=chrome
								- Create a new user script in Tampermonkey with the copy-paste JavaScript you can find here (replace everything in the new user script):
									- https://raw.githubusercontent.com/Wizmann/Utils/master/UserScript/WorkflowyPlus.js
								- Refresh your browser.
								- Use the instructions for the embed links in each example given below.
							- **2. APPS**
								- **MINDMEISTER MIND MAPS**
								  collapsed:: true
									- (1) Grab the URL of your mind map and
									- (2) Put it in a WorkFlowy note (Shift+Enter)
									- (3) Wrapping it like so:
										- ![iframe](YOUR_LINK)
								- **YOUTUBE VIDEOS**
								  collapsed:: true
									- (1) Right click on your YouTube video,
									- (2) > “Copy embed code”,
									- (3) Paste that somewhere and strip away everything except the URL.
									- (4) Pop that URL into a WorkFlowy note and
									- (5) Wrap it thusly:
										- ![iframe](YOUR_LINK)
								- **GOOGLE DOCS**
								  collapsed:: true
									- (1) Open your Google Document on the web
									- (2) Click on "share" (top right)
									- (3) Copy the shared link to your clipboard
									- (4) Include this in a WorkFlowy list’s note:
										- ![iframe](YOUR_LINK)
								- **SHARED EVERNOTE NOTES**
								  collapsed:: true
									- (1) Right click on your target note in your desktop client
									- (2) > Share > Copy Share URL
									- (3) Paste that link into your browser and follow it
									- (4) Recopy the resulting URL
									- (5) Paste into a WorkFlowy note like this (The “.html” is important!):
										- ![iframe](YOUR_LINK**_.html_**)
								- **GINGKO TREE (MARKDOWN PREVIEW)**
								  collapsed:: true
									- (1) Copy the URL of your Gingko Tree and
									- (2) Wrap your link in the following Markdown tag in a WorkFlowy note:
										- ![iframe](YOUR_LINK)
					- X-Frame-Options
					  collapsed:: true
						- Many prominent web sites do NOT allow loading their web sites inside an IFRAME, such as Google and Yahoo, by way of the X-Frame-Options. In these cases the IFRAME will appear blank, so be sure to check each site you're loading into this script to confirm it works.
					- Nextcloud External Sites app allows embedding iframes
					  collapsed:: true
						- https://docs.nextcloud.com/server/9/admin_manual/configuration_server/external_sites.html
				- WorkFlowy habit enhancement
				  id:: 663b24fd-a872-4e7b-a096-25a69db5a4d8
				  collapsed:: true
					- https://blog.workflowy.com/
					- $20 power user book
					  http://www.productivitymashup.com/do-way-way-more-in-workflowy
					- Kanban Calendar
					  source:: http://www.productivitymashup.com/blog/2014/7/17/kanban-calendar-preamble
					  collapsed:: true
						- Kanban
							- for instance. One of the most productive task-management systems with 2 main principles at its core:
							- (1) Visualize your workflow
							- (2) Limit your work in progress.
						- Three lists
							- All of the stuff you'd like to get around to doing sooner or later
							- The stuff you intend to do today, and
							- The stuff that is plotted on specific days ahead of you - according to due date.
						- When overwhelmed, move additional tasks to Calendar/Date-Specific Tasks section rather than the non-dated Backlog section
						- How to pull tasks from Backlog to Today
						  https://youtu.be/A-fWKn1CyQE
						- Implement Double Kanban too
						  http://www.productivitymashup.com/blog/2014/9/5/workflowy-double-kanban
						- https://www.productivitymashup.com/blog/2014/8/17/kanban-calendar-workflowy
					- http://talk.dynalist.io/t/3-kanban-system-gtd-using-dynalist-io/514
					- Kanban Timeline
					  collapsed:: true
						- _Template Description_
						  Click to see more
						  1. I go through "Items-for-Later" and add a #to-day_ tag for tasks I'd like to do today. (This helps aggregate tasks from other Parent nodes such as tasks from another day or "Project" nodes).
						  
						  2. I go through a list of tasks and assign a @Project for each node to categorize them. (I like to have each node have a specific @Project so I can see where my time was allocated.)
						  
						  3. My main workflow is within my Calendar section where I move around the bulk of my tasks from day to day. This is actually an adaptation from the Kanban Calendar template. Rather than have "Today" as it's own Parent node, I like to have all my tasks for that day within the "Calendar" node for whatever day it is. The #to-day_ tag moves with the day so i can easily jump from the Home screen. The main reason for this is that it helps with tracking completed items as you can view everything that was done on a certain day (here's an example: https://www.dropbox.com/s/z5qwnole8iisxj9/Screenshot_102815_105018_AM.jpg?dl=0).
							- _Tags: _
							  Tasks: _Task | _FollowUp | _Next | _Later | _Milestone | _Deadline | _delegated
							  Notes: _contact | _name | _phone | _email | _address | _template | _Mech | _Elec | _Str
							- **CALENDAR #to-day**
							  Something with a deadline/date
								- **October 2015**
									- _Follow Up #Follow_
										- #Week
										  Items that will be categoriezed at the end of the week
											- Task 1
											- Task 2
											- Task 3
										- #Month
										  Items to be categorized at the end of the month
											- Task 1
											- Task 2
											- Task 3
									- 1 Mon
										- Completed Task 1 @Project1
										- Completed Task 2 @Project1
										- Completed Task 3 @Project2
									- 2 Tue #to-day_
										- Task 1 @Project1 #to-day_
										- Task 2 @Project1 #to-day_
										- Task 3 @Project2 #to-day_
									- 3 Wed
										- Task 1 @Project2
										- Task 2 @Project1
								- **November 2015**
							- .................................................................................
							- **PROJECTS**
							  Long-term items that relate to work projects
								- **7589_Project 1**
								  @Project1
									- Notes
									- Tasks
								- **4562_Project 2**
								  @Project2
									- Notes
									- Tasks
								- **4789_Project 3**
								  @Project3
									- Notes
									- Tasks
							- .................................................................................
							- **PERSONAL**
							  Long-term items that relate to personal projects
								- Notes
								- Tasks
							- .................................................................................
							- **NOTEPAD**
							  Quick Short-term items that will move to another category.
					- HandyFlowy (improved mobile app)
					  https://blog.workflowy.com/2016/04/21/handyflowy-workflowy/#more-1450
					- View last change on bullet hover.
					- Filter changes in last 24hrs:
					  collapsed:: true
						- intralink2:: https://workflowy.com/#/?q=last-changed%3A1d
						  last-changed:1d
						- Remove 'd' for mins.
					- Unicode formatting list
					  intralink2:: https://workflowy.com/s/Cc98IvoILg
					- Flat WorkFlowy lists for easier searching
					  https://rawbytz.wordpress.com/2015/12/16/flat-workflowy-lists/
					- _(removed by owner)_
				- SOP
					- _See_ [********** Extensions for interlinking from WorkFlowy](https://workflowy.com/#/71f26ef8075a)
				- _Related:_
					- [[Logseq]]
					- ((64098f10-1d1d-4f4d-a2e4-1e4b7fb406a2))
					- WorkFlowy as a key system
					  #Productivity https://workflowy.com/#/9159431588b2
			- [Dynalist](https://dynalist.io/)
			  id:: 64098f10-1d1d-4f4d-a2e4-1e4b7fb406a2
			  collapsed:: true
				- [http://blog.dynalist.io/](http://blog.dynalist.io/)
				- _Journal_
				  collapsed:: true
					- Fri, Dec 4, 2020 - move #GirlFunnel-Leads and #BusinessCommitmentAnalysis from Dynalist back into WorkFlowy
						- Pros/Cons
							- Pros
								- I want to maintain one main outliner and keep everything in it that can be stored. Both those two sections don't require additional
						- Note: main data still in Dynalist is #Programming because WorkFlowy still doesn't support code blocks or syntax highlighting
					- Fri, Jun 1, 2018 - created #Programming in Dynalist to store all code snippets there
						- Pros
							- WorkFlowy doesn't support code blocks. Dynalist via Powerpack supports code blocks and syntax highlighting
					- Sun, Apr 15, 2018 - Swapped to using DEPOSITORY (INBOX) in Dynalist
					  intralink1:: https://dynalist.io/d/TZoZ5yx-utFURJ7j1JWUA3cC#z=fPFRV1DtZWQhurjNpGJhQs-0
						- Pros
							- Get familiar with the tool, get ideas for my own project management app
							- Can quickly add items
								- Launchy 'DEP' to open the browser
						- Cons
							- Can't full text search my main WorkFlowy to find notes I made earlier if it remains separate
				- Pros/Cons
					- Pros
						- [Can import from WorkFlowy](http://help.dynalist.io/import/#import-from-other-apps)
						- Inbox feature
						  id:: 65f55774-589b-45cc-bbff-be95fc54401f
						  collapsed:: true
							- `CTRL+SHIFT+I` = Capture to Inbox
							  id:: 65f55774-9ebf-4a05-a1a7-9683cf8eadef
								- Pro-only, but quickly capture something without finding that item first
								- How to
									- [In Settings select a bullet as `Your inbox`](https://help.dynalist.io/article/119-set-an-inbox-location)
									- Pressing the hotkey opens a capture pop-up
										- ![image.png](../assets/image_1710667802498_0.png)
								- desktop app has a global shortcut for this
								  http://talk.dynalist.io/t/capture-to-inbox-shortcut-goes-global-on-desktop-app/1215
							- Quick Dynalist app allows instant adding notes to Dynalist
								- Links
									- https://github.com/timediv/QuickDynalist
									- https://play.google.com/store/apps/details?id=com.louiskirsch.quickdynalist
									- Thread
									  https://talk.dynalist.io/t/quick-dynalist-the-native-android-app-for-dynalist/3026/93?u=aaron
								- Features
									- Custom inboxes
									  https://talk.dynalist.io/uploads/default/optimized/2X/9/90a0b00528f9e1a83eb5f60a2757c31383f1195d_1_281x500.jpeg
									- Good advanced search
									  https://talk.dynalist.io/uploads/default/optimized/2X/b/bc13eaedb4eae3f5d72d98c219415d48345aaf9d_1_281x500.jpeg
						- Code blocks, and code highlighting via Powerpack 3
						  collapsed:: true
							- Update Fri, Dec 4, 2020 - no longer works for me on Firefox
								- Violentmonkey toggling Powerpack 2 or 3 neither enable code highlighting and with Powerpack 2 it stops navigation
							- Powerpack 3
							  [https://talk.dynalist.io/t/powerpack-3/2744](https://talk.dynalist.io/t/powerpack-3/2744)
								- [https://dynalist.io/d/lzBWy1bl_LtzycHHl-ktmSVB](https://dynalist.io/d/lzBWy1bl_LtzycHHl-ktmSVB)
								- [https://github.com/PiotrSss/DynalistPowerpack](https://github.com/PiotrSss/DynalistPowerpack)
								- Old version Powerpack 2 - better compatibility with Firefox?
								  [https://talk.dynalist.io/t/powerpack-2/977](https://talk.dynalist.io/t/powerpack-2/977)
									- [https://dynalist.io/d/OzuUqkYwKBE-g5QOJBFIkVbg](https://dynalist.io/d/OzuUqkYwKBE-g5QOJBFIkVbg)
									- [https://greasyfork.org/scripts/31392-dynalist-powerpack-2](https://greasyfork.org/scripts/31392-dynalist-powerpack-2)
							- _See_ [Code highlighting not present in WorkFlowy](https://workflowy.com/#/5aa2eb82292a)
					- Cons
						- _Pros/Cons of moving everything from WorkFlowy_
						  collapsed:: true
							- Pros
								- Can more quickly add items
									- Capture to Inbox hotkey - quickly capture something without finding that item first
									- Quick Dynalist app
									  intralink2:: https://workflowy.com/#/50741a9565be
								- Can more quickly navigate to other items
									- Internal hyperlinks use the item name instead of URL
									- There's a shortcut to open quickfinder
									- CTRL+F opens the search bar
								- I can then full text search one outliner to find all notes
								- Backup is quicker as there's an export all as ZIP option
								- I'm concerned that WorkFlowy backup may eventually be unfeasible on my laptop due to CPU consumption
								- _Other improvements over WorkFlowy_
								  collapsed:: true
									- API
									- Supports documents
									- Google Calendar integration
									  http://blog.dynalist.io/gcal-integration/
									- Keyboard hotkey support
									  http://blog.dynalist.io/gcal-integration/
									- File upload, numbered list, checkbox list, date support, colour lines (background)
									- Markdown - headers
									- Cross linking - link to any other without leaving the current context
									- Internal links with anchor text
									  http://i.imgur.com/kKo09Aw.gif
									- Fast add (without finding item first)
										- This feature allows you to quickly add some text to the end of an item.
										- The interface would look a bit like the File Finder we have now: you bring up the interface with a shortcut, and write your text and then search for the destination all with keyboard.
										- Use case: want to quickly capture something without finding that item first.
									- Lazy loading - fast page load and search
									- Recurring tasks
									  https://blog.dynalist.io/recurring-dates/
									- _I'm not using these at all_
										- ((6458ee2f-9855-4d38-89e5-726aa7bdd3ee))
										- Has very basic mind map functionality
										  http://blog.dynalist.io/clone/
										- Inline images
							- Cons
								- $8/month
								- Would have to redo all interlinking - need strong incentives to not instead just move to my own self-hosted Calculist or similar
								  collapsed:: true
									- Privacy - some way to access 'True offline mode' data on multiple devices
									  https://trello.com/c/46l658SA/146-pro-true-offline-mode-disable-data-sync
									- Alt Privacy - self-hosted/remoteStorage/client-side encryption
									  All 4 discussed here http://talk.dynalist.io/t/true-offline-mode-or-encrypted-data/580
										- Client-side encryption
										  **Sufficient** when combined with auto-backups
											- Also see CRDTs
											  #Software https://workflowy.com/#/49b92cb3f5bb
										- Self-hosted
										  **Ideal** as I'd have the source code to adapt for lifetime usage
										- remoteStorage
										  **Realistic **as CSE is hard and self-hosting means their business could get forked
											- Should I suggest?
												- Pros
													- Would likely be implemented as it solves the sync problem in the True Offline Mode
													- Would be easier to prove privacy with remoteStorage than with closed-source client-side encryption (e.g. WhatsApp's "encryption")
												- Cons
													- Would likely make self-hosted version never exist as they've already allowed users to host their own data, why give them the client too?
														- _However _I could make my own some day using money to fund
											- Encryption could be built into it, or just left to app devs
											  https://community.remotestorage.io/t/encryption-option-in-library/108/33
								- WorkFlowy has proven longevity and reliability
								- Performance - Mobile app can't handle docs >1MB (8MB doc wasn't loading) - however now it has Lazy Loading and I can collapse all it may not be an issue
								  https://talk.dynalist.io/t/performance-with-very-large-documents/519/8?u=aaron
									- Collapse all children
									  Ctrl-Shift-. (period).
								- CTRL+F doesn't allow a normal page search
						- Future enhancements
							- _Their current 2017 focus: _Mobile apps, collaboration and API
								- [Changelog](https://dynalist.io/changelog)
								- [Roadmap](https://trello.com/b/z0HxDPNo/dynalist-roadmap)
								- [Blog](http://blog.dynalist.io/)
							- Push notifications for tasks [swap Todoist subscription for this once implemented]
							  collapsed:: true
								- Mobile
								  [https://trello.com/c/jeDrJWys/182-mobile-notification-for-dates](https://trello.com/c/jeDrJWys/182-mobile-notification-for-dates)
								- Desktop
								  [https://trello.com/c/WvJagv3K/181-desktop-notification-for-dates](https://trello.com/c/WvJagv3K/181-desktop-notification-for-dates)
								- _Related: _[Pro] push notifications via Google Calendar integration
									- http://blog.dynalist.io/gcal-integration/
									- [http://help.dynalist.io/article/94-pro-features](http://help.dynalist.io/article/94-pro-features)
								- Slack notifications for updates (API)
								  https://trello.com/c/J9txodwx/131-update-notification-through-slack
								- Push notifications can be done via non-sensitive notifications ("You have 1 due task"); Server Sent Events; MQTT etc
								  ((630f9707-836b-4814-8d7d-0ce9109fc35d)) [Mobile push notifications](https://workflowy.com/#/3a80ef8f8e2d)
							- Tables
							  collapsed:: true
								- Dynalist tables using katex arrays
									- $$ \begin{array}{cccccccc} Daily & Mo & Tu & We & Th & Fr & Sa & Su \\ \hline ~Ex~ & [x] & [] & [] & [x] & [] & [] & []\\ ~Md~ & [] & [] & [] & [] & [] & [] & [] \\ \end {array} $$
									- 2
									- $$ \begin{array}{cccccccc}
									  														- Daily & Mo & Tu & We & Th & Fr & Sa & Su \\ \hline
									  														- ~Ex~ & [x] & [] & [] & [x] & [] & [] & []\\
									  														- ~Md~ & [] & [] & [] & [] & [] & [] & [] \\
									  														- \end {array} $$
								- A) Tag attributes + flattened search results; then ask for a simple table view
								  [https://trello.com/c/t9YcUQe8/167-tag-attributes](https://trello.com/c/t9YcUQe8/167-tag-attributes)
									- Note
										- Much more likely trojan horse route into Dynalist than trying to get tables added. Could work with Wildcard or another userscript to turn metadata into tables
									- _Two pre-reqs_
										- Tag Attributes e.g. @priority(4)
											- From TaskPaper
											  intralink2:: https://workflowy.com/#/067ae4cbbb28
											- Roadmap
											  https://trello.com/c/t9YcUQe8/167-tag-attributes
											- https://talk.dynalist.io/t/tag-attributes/1059/5
										- Flattened search results
										  https://trello.com/c/Xp5R5eNA/143-flattened-search-results
									- New feature to request - table search results with filter
										- _Features_
											- Tag Attributes allows there to be multiple columns
												- Otherwise it has to be one dropdown with a checkbox next to each tag, since there's no way to categorise
											- Like Asana's simple table view http://i.imgur.com/fsa7sFk.png
											  intralink2:: https://workflowy.com/#/4f91d6bbbeaf
								- B) Columns/Tables (aka spreadsheet, tuple)
								  https://trello.com/c/06RIufbM/91-adding-columns-to-items
									- https://apidocs.dynalist.io/
									- http://talk.dynalist.io/t/adding-columns-to-items/341
									- I agreed that a per-document view is fine rather than per-item
									  http://talk.dynalist.io/t/multiple-views-kanban-column-calendar-etc/1468/5?u=aaron
									- Mentioned 'define field type'
									  http://talk.dynalist.io/t/adding-columns-to-items/341/27?u=aaron
									- Not posted yet - I just wanted to get across the main point about field types first
										- I also think it should use the outline format as the "backend" rather than a separate format. It allows:
										- Easy conversion back into a normal outline format if desired
											- Export doesn't need to be reimplemented
											- Hyperlinks can be used to take you to a specific cell
											- Full-text search shows all table content
										- As for how to present it in Dynalist:
										  intralink2:: https://workflowy.com/#/9445614abc2b
							- [*Encrypted* automatic daily backup](http://talk.dynalist.io/t/encrypted-automatic-daily-backup/1460)
							- [Project management](http://talk.dynalist.io/t/a-few-dynalist-project-management-ideas/805/10)
							- Collaboration
							  collapsed:: true
								- Share items rather than a document
								  https://trello.com/c/V2zvGqou/21-share-part-of-the-document
									- Can't share only part of the document (item level rather than document level)
									- But does have separate documents that work like separate workflowy accounts/files)
								- _Pre-req: API_
									- Assign tasks
									- Notifications for overdue items - already possibly with GCal + pro
									- Reminders via API using the date feature
									  e.g. Slack, email, in-app
									- Push updates or new comments via API
									  e.g. comment system, works via Slack etc
										- They plan on in-line comments, not real-time chat for the moment
										  http://talk.dynalist.io/t/commenting/388/8?u=aaron
								- Asana-style Inbox
								  http://talk.dynalist.io/t/mentions-subscribing-via-name/520/3
									- (notifications area for tagged)
									- API-based
									- All updates under a certain node pushed via API
									- All updates where you are @aaron1 tagged get pushed
									- Mentions and subscribing via +NAME
										- For collaboration it would be great to have this:
										- Ability to give yourself a @NAME in the settings menu
										- When put in title or note area allows:
											- Mentions/Assigning:
												- Being notified once (via mobile app push notification) whenever a new instance of your @NAME appears in a document
												- Multiple people can be designated as "task assignees" due to the flexibility of no native "assignee" area
												- These mentions could be added anywhere - in the title/note top line/note hidden area
											- Subscribing/Following:
												- Whenever a mention is added the target person is not automatically subscribed to receive future notifications, will only receive the one-time notification that a new mention has been made
												- They can however optionally choose to follow/subscribe to the item
												- Whenever new sub items are added, or a progress meter changes, or comments are added, the subscriber receives a notification about this
											- Notifications Pane (left-side above bookmarks):
												- Includes all one-off mentions, as well as ongoing subscription notifications
												- In the future filterable by mentions/subscriptions/by document/colour tag
												- Similar to concept to Asana's Inbox
								- Airtable-style Slack notifications
								  http://talk.dynalist.io/t/gathering-api-v0-1-ideas/675/38
							- Views
							  collapsed:: true
							  [Multiple Views - Kanban, Column, Calendar etc - 🌟Features - Dynalist Forum](http://talk.dynalist.io/t/multiple-views-kanban-column-calendar-etc/1468)
								- Views is an important concept in the vision of Dynalist. Basically, a view is another way of displaying the same content. For example, a Dynalist can also be shown as a mind map, as the underlying data is the same — nested lists.
								  http://help.dynalist.io/article/84-switch-to-another-view
									- Some of the views that we’re interested in experimenting with include
										- Mind Map View
										- Kanban View
										- Calendar View
										- Presentable View
										- Column View
										  intralink2:: https://workflowy.com/#/d6b716822ab2
								- ActiveCollab Views
								  intralink2:: https://workflowy.com/#/de63bfb030a7
							- Cloning/Mirroring - display a bullet in multiple places
							  https://trello.com/c/zrla0Fmx/150-clone-display-an-item-in-multiple-places
				- Documentation
				  collapsed:: true
					- Links
					  http://help.dynalist.io/formatting/#link
						- You can make a link [like this](www.dynalist.io). There’s no associated keyboard shortcut.
						- If you don’t need the link to be named, pasting the URL is enough to make it clickable. No Markdown needed.
					- Image link
						- You can make an image link ![like this](example.com/kitten.jpg). There’s no associated keyboard shortcut.
						- The difference between image links and normals is that image links have an image icon to mark it, and hovering on an image link would open a preview of the linked image inside Dynalist.
					- Add tags ( or @), dates (!), and internal links ([[) with triggers.
					- Finder lets you jump to any document or bookmark within a few keystrokes. Use Ctrl+O to open it.
					- Dynalist features analysis
						- Mobile app
							- Above keyboard
								- Left indent
								- Right indent
								- Zoom
								- Delete
								- Complete
								- Note
								- Calendar due date
								- Move bullet up
								- Move bullet down
								- Move item (search for item or document to move it under)
								- Tick box
								- Background colour highlight
								- Header 1-3 + clear
								- Link (find out item link)
							- Right in Header
								- Undo
								- Search
								- Read mode (allows text highlight by character)/write mode
								- Popup menu
							- Then in far left corner a burger menu
								- My files
									- New file
									- New folder
								- Bookmarks
									- Saved searches
									- Saved items
									- Bookmark current state
						- Inbox
						- Mobile Brave browser can be used to create web app frames for any page eg Dynalist
					- Pure Java I believe, if you mean the server backend.
				- Not yet a suggestion
				- _Related: _WorkFlowy
				  #Outliners https://workflowy.com/#/f67c68c49e0d
			- [Tana](https://tana.inc/)
			  id:: 636381e5-30ab-4830-ae58-7472732fbf8f
			  collapsed:: true
				- Table view
				  id:: 653e4732-ef31-431b-bea3-0f5891aa0290
					- ![image.png](../assets/image_1698580254592_0.png)
				- ![image.png](../assets/image_1667465709503_0.png)
				- ![image.png](../assets/image_1667465758888_0.png)
				- ![image.png](../assets/image_1667465778356_0.png)
				- ![image.png](../assets/image_1667465799453_0.png)
				- ![image.png](../assets/image_1667465833326_0.png)
				- ![image.png](../assets/image_1667465898503_0.png)
				-
			- OmniOutliner
			  collapsed:: true
				- https://www.omnigroup.com/omnioutliner
			- Moodo
			  collapsed:: true
			  Integrates strongly with Google Calendar, Drive, Gmail
				- https://www.moo.do/
				- Looks decent
			- LiquidPlanner
			  collapsed:: true
			  Expensive
				- https://www.liquidplanner.com/
				- Primarily ((663a0528-7561-41e3-ae6d-34b4dc2e4d26)) view, maybe 4 levels at least of hierarchy in outliner view
				  http://i.imgur.com/YPJ6AJr.png
				- Kanban view also
				- Features
				  https://i.imgur.com/NZ7A3Yw.png
				- Quite expensive
				- https://www.youtube.com/watch?v=wAmtjps42Ac
			- [Todoist](https://workflowy.com/#/2fd192b99f3f)
			- Checkvist
			  collapsed:: true
				- https://checkvist.com
				- Keyboard-centric, not built for mouse usage
				- It has a different selection model (to allow two-letter keyboard shortcuts), multiple lists support, file attachments, due dates/calendar integration, Markdown with code highlighting.
				- Main focus of the tool - keyboard support and productivity, may be a bit geeky style.
				- https://checkvist.com/auth/pricing
				- https://checkvist.uservoice.com/forums/2121-general
			- GTDNext
			  collapsed:: true
				- https://app.gtdnext.com/
			- TaskPaper
			  collapsed:: true
				- For Mac only
				- 3rd party apps
				  https://support.hogbaysoftware.com/t/what-other-apps-support-taskpapers-file-format/1114
				- Task Attributes (Dynalist plans to make tag attributes)
				  https://guide.taskpaper.com/reference/searches/#attributes
		- Plain text editors
		  collapsed:: true
		  Incl. Emacs org-mode
			- [Emacs](https://www.gnu.org/software/emacs/)
			  id:: 634bc1d7-6c8e-4cb1-8b72-5ebdbfb847ee
			  collapsed:: true
				- Pros/Cons
					- Pros
						- Supports a "Note"-like field on each bullet
						- [Emacs: The Editor for the Next Forty Years [video] | Hacker News](https://news.ycombinator.com/item?id=21638197)
						-
					- Cons
						- UIs are very opinionated because of Emacs history
						- [Potential repetitive strain injury due to strong dependence on modifier keys](https://en.wikipedia.org/wiki/Emacs#Emacs_pinky)
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Far more features
								- besides text editing, it is also used as a email reader, newsgroup reader, ftp client, irc client, web browser, shell interface, file management application, scientific calculator, calendar and personal info management application, lisp language system, among other things
							- Extremely customisable
							- Unlike a web app (what I'd have to pay to have created), data is offline thus far more difficult to intercept. It can be locked in an encrypted container
							- Can interlink within the document and to other files on filesystem or URLs
							- Extensions
								- Org-brain - concept mapping https://reddit.com/comments/836o1r
								- Magit extension - enhanced Git CLI
								  https://emacsair.me/2017/09/01/the-magical-git-interface/
						- Cons
							- Forks which improve on default Emacs things
								- [https://github.com/emacs-ng/emacs-ng](https://github.com/emacs-ng/emacs-ng)
								- Several hotkeys do not match modern standards, though Aquaemacs uses them
									- [http://ergoemacs.org/emacs/modernization.html](http://ergoemacs.org/emacs/modernization.html)
							- Written in Emacs Lisp
							- Lacks the ability to scroll without bringing point along with me so I can quickly check something off screen then just continue typing where I left off.
								- I upvoted this, but the workaround is to create a marker to return too. This issue is that it's quite easy to forget to create the marker before starting to move around
							- I upvoted this, but the workaround is to create a marker to return too. This issue is that it's quite easy to forget to create the marker before starting to move around
							- Hate to choose the obvious answer but- real parallelism in elisp.
								- There's been a lot of great work to hack around the issue, introducing concurrent cooperative multithreading (as well as many modes using process-based parallelism, like in SLIME), but as computers get increasingly parallel it's a shame that Emacs can't yet actually take advantage of that. It would certainly be a major change, but I think it's going to need to be done eventually.
								- 4. Improve threading so that things like TRAMP didn’t freeze when you were connecting
							- Unsure if it can have multiple bullets open/expanded like WorkFlowy
								- 2018 recollection of 2016? trial - no
							- Limited to two split windows, unlike multiple tabs in WorkFlowy
							  intralink2:: https://workflowy.com/#/07ed73fa121f
							- Have to learn the keybindings and shortcuts
							- Have to learn how to search
					- Comparisons
						- ((9c059bb1-0976-45e5-b420-676c8acdad61))
						- ((6712e8fc-c577-4c88-84c0-1f71ed8de159))
				- Clients
					- Desktop Clients
					  collapsed:: true
						- ((634bc1d7-6c8e-4cb1-8b72-5ebdbfb847ee))
						- _Collaboration_
							- [Emacs] allow multiple clients to edit a single file on-line
							  https://github.com/zk-phi/togetherly/
							- Rudel
							  https://www.emacswiki.org/emacs/Rudel
							- A real-time collaborative editing platform built on Git.
							  https://github.com/technomancy/conspire
							- Safe and simple one-script git synchronization
							  https://github.com/simonthum/git-sync
							- SyncOrg has - Automatic Git synchronization (via SSH and HTTP). Access to the raw files in case of conflict to solve.
							  intralink2:: https://workflowy.com/#/69b9c3319a2d
							- _Git sync_
								- https://www.git-tower.com/windows/
							- See org-web
						- Org tools
						  collapsed:: true
							- https://github.com/yjwen/org-reveal
							- http://pandoc.org/
							- http://orgmode.org/worg/code/org-info-js
					- Web Apps
					  collapsed:: true
						- Features to have
							- WorkFlowy style drag-and-drop reordering and indenting
							  https://github.com/mickael-kerjean/filestash/issues/129
							- WorkFlowy style narrowing and breadcrumbs
							  https://github.com/mickael-kerjean/filestash/issues/129
							- Flattened search results and item properties to make a table of search results which can also be further filtered
							- A HTML scrolling toolbar above the keyboard in the mobile web app
							  collapsed:: true
								- This is a feature available for web apps, for example WorkFlowy.com uses it:
								- ![](https://i.imgur.com/TVF9H9R.png)
								- scrolling above the keyboard like in the HandyFlowy mobile app would be helpful in  order to use the keyboard shortcuts (indent, unindent, zoom in, zoom out, delete, complete)
						- _Projects_
							- Filestash
							  id:: 67a8e14d-6d01-4753-b06e-5351e661a98b
							  collapsed:: true
							  [cloned] https://github.com/mickael-kerjean/filestash previously Nuage
								- **Last checked: Tue, Sep 29, 2020**
								- Screenshots
								  https://i.imgur.com/g6aOMaz.png
									- GIF
									  https://raw.githubusercontent.com/mickael-kerjean/nuage/master/.assets/img/orgmode.gif
									- Photo management
									  https://raw.githubusercontent.com/mickael-kerjean/nuage/master/.assets/img/photo_management.gif
								- Demo
								  https://demo.filestash.app
								- Lacks
									- Orgzly/WorkFlowy-like outliner view (marked as wontfix)
									  https://github.com/mickael-kerjean/filestash/issues/129
										- Narrowing like WorkFlowy
										  [https://imgur.com/a/ki8ildW](https://imgur.com/a/ki8ildW)
									- Electron app in progress (marked as wontfix)
									- FUSE for desktop app
									- _Planned_
										- Database viewer (MySQL, )
										  https://github.com/mickael-kerjean/nuage/wiki/ROADMAP-for-Release-0.5:-databases
											- Current v0.3 features
												- What's new in v0.3:
												- a structure for your data that makes sense for non technical user where:
													- databases are seen as folders
													- tables are seen subfolders
													- row are files that open up as an editable form created by querying your internal schema
												- db views: views are visible within nuage and are read only
												- foreign key: links are created within nuage to reach data accessible from foreign keys. Notes: A lot of application don't implement foreign keys at the database level but at the application level. This horrendous flacky practise despite being very widely used (wordpress, joomla, ...) isn't supported by nuage.
											- I'm working on something like this, after connecting to your database, you get something like:
												- screenshot
												  https://archive.kerjean.me/public/2019/Screen%20Shot%202019-02-16%20at%2011.40.10%20am.png)
												- other view
												  https://archive.kerjean.me/public/2019/Screen%20Shot%202019-02-16%20at%2011.45.05%20am.png
											- The data is fully editable and you can even create shared links a la Dropbox. This all comes as a plugin for [this project](https://github.com/mickael-kerjean/nuage) that's given to customers who need it. If there's a need, can also make it work for postgres, mssql and oracle (not for free thought)
											- https://reddit.com/comments/aqwvul/comment/egkhujw?context=3
										- Video transcoding and google photos-like viewer
										  https://github.com/mickael-kerjean/nuage/wiki/ROADMAP-for-Release-0.6:-Multimedia-solution
								- Features
								  https://github.com/mickael-kerjean/nuage_org_demo
									- Manage your files directly from your browser, drag-and-drop upload
									- Mobile version (progressive web app)
									- Connect to multiple cloud backends - FTP, SFTP, WebDAV, Git, S3, Minio, LDAP
									- Multimedia viewer/player: audio, video, images
									- Emacs keybindings + org mode friendly ;)
									- Frequently access folders are pin to the homepage for quick access
							- org-web (built with React)
							  collapsed:: true
							  [https://github.com/DanielDe/org-web](https://github.com/DanielDe/org-web) / <a href="https://org-web.org">https://org-web.org</a>
								- **Last checked: <time startYear="2020" startMonth="9" startDay="29"**
								- Pros
								  collapsed:: true
									- JavaScript so something I can feasibly easily hire developers for/enhance myself
									- Quite a few features
										- Table viewer + editor
										  https://i.imgur.com/drTzwhz.png
										- Customisable org-capture buttons (i.e. like quick capture)
										- Timestamps - popup for adding/editing them (including start -> end timestamps)
									- Emacs community will support this to an extent
								- Cons
								  collapsed:: true
									- Miss out on all the developed features for original Emacs client
									- Lacks
										- _Requested_
											- Narrowing (as well as +/- expand/collapse, and breadcrumbs
											  https://github.com/DanielDe/org-web/issues/28
										- _Not yet requested_
											- Drag-and-drop (like Nestable or WorkFlowy)
											  https://github.com/dbushell/Nestable
											- Undo and redo button
											- Hyperlinks to narrowed views
												- This feature would allow easy navigation to narrowed views of other parts of the org file, as well as hyperlinks that could be saved in bookmarks etc for ease of use.
												- CUSTOM_ID could be used for [linking](http://orgmode.org/manual/Internal-links.html) to a narrowed view e.g. creating the CUSTOM_ID "jdbw87d6" for an item would allow using the URL https://org-web.org/#/jdbw87d6 to open to a narrowed view of that bullet.
											- Left pane hamburger menu for saved searches like Orgzly
											  intralink2:: https://workflowy.com/#/f8ac022399e8
												- Search feature
												  https://github.com/DanielDe/org-web/issues/12
											- WebDAV, SFTP/FTP, GIT, S3 backend
											  https://github.com/DanielDe/org-web/issues/5
											- Export to Anki format
											- Future plans
												- A backend API for use in your own appsscripts/IFTTT/Alexa Skillsetc.
											- _Mobile app_
												- Redesign
												  https://i.imgur.com/EU6VMir.png
													- Left pane
													  intralink2:: https://workflowy.com/#/b3255b581b54
													- Settings menu in top-right
														- Move 'sync' here
														- Move 'Sign Into GitHub' here
													- Orgzly way of selecting and moving bullets
														- https://i.imgur.com/b1QYGg4.png
														- https://i.imgur.com/8K33gSi.png
												- Needs parity with Orgzly, Tasks and Dynalist
												  intralink2:: https://workflowy.com/#/f98c5435aacd
												- Mobile app release in F-Droid + Google Play
												- _Not yet requested_
													- 'Header menu' appears instead as a scrolling toolbar above keyboard
													  intralink2:: https://workflowy.com/#/48a8dd6e18be
													- Similar UI to Orgzly?
													  https://i.imgur.com/J4fCjlh.png
														- https://i.imgur.com/J4fCjlh.png
														- https://user-images.githubusercontent.com/1091022/30556545-19370164-9c60-11e7-8171-3ecabb8126b5.jpg
													- Notifications for deadlines/scheduled items
													- Item Finder (Dynalist Pro has it. Launchy-like)
													- Move Item (Dynalist Pro has it. Launchy-like)
													- Future plans
														- Offline support via service workers/progressive web app
														- org-agenda view
												- _Requested features_
													- Client-side encryption
													  https://github.com/DanielDe/org-web/issues/27
							- OrgModeWeb
							  collapsed:: true
							  http://i.imgur.com/ujlx37K.png / https://github.com/borablanca/orgmodeweb
								- **Last checked: <time startYear="2020" startMonth="9" startDay="29"**
								- [https://orgmodeweb.org](https://orgmodeweb.org)
								- Pros
									- Responsive and nice UI
									- Progressive Web App, works offline (service workers) and on mobile web
								- Lacks
									- WebDAV sync (only Dropbox and Browser LocalStorage are supported now)
									  Planned
									- Download/export from browser LocalStorage
									- Doesn't persist the open state of children items
									  https://github.com/borablanca/orgmodeweb/issues/2
									- Drag-and-drop reordering+un/indenting; or any kind of indenting mode (like Orgzly) in the UI
									  https://github.com/borablanca/orgmodeweb/issues/3
									- Narrowing (like WorkFlowy)
									- Breadcrumbs (pre-req: narrowing)
									- Hyperlinks aren't clickable?
									- Android app, so it can support local storage sync
									- Desktop app wrapper, so it can support local storage sync
								- Questions
									- Internal links to other notes?
							- organice (built with React)
							  collapsed:: true
							  [https://github.com/200ok-ch/organice](https://github.com/200ok-ch/organice) / <a href="https://organice.200ok.ch/">https://organice.200ok.ch/</a>
								- Syncs with Dropbox, Google Drive and WebDAV.
							- Grasp (browser extension for org-capture)
							  https://github.com/karlicoss/grasp
						- _Reddits_
							- https://www.reddit.com/r/orgmode/top/?t=month
							- https://www.reddit.com/r/emacs/top/?t=month
					- Mobile app org-mode
					  collapsed:: true
						- [Orgzly](http://www.orgzly.com)
						  id:: 67000f1e-9810-4504-ae0d-014e7960a98b
						  collapsed:: true
							- Info
								- http://www.orgzly.com/help#FAQ
								- https://github.com/orgzly/orgzly-android
								- https://plus.google.com/communities/104387367636243222968
								- Beta notes
								  https://groups.google.com/forum/m/#!forum/orgzly-android-beta
							- Pros/Cons
							  collapsed:: true
								- Pros
									- Open-source and locally hosted
									- Org-mode - thus huge potential for extension
										- Will allow tables and other functions
									- Been around for years - will likely stay for years too
									- Desktop support via CalDAV sync (OR filesync + desktop Emacs)
									  https://github.com/orgzly/orgzly-android/issues/38#issuecomment-379571428
										- Emacs org-mode CalDAV sync adapter
										  https://github.com/dengste/org-caldav
										- CalDAV sync
										  https://github.com/orgzly/orgzly-android/issues/38#issuecomment-331722665
										- Desktop web app like Duplicati (app runs natively on desktop, opens into web app and can do multiple instances)
											- You can get Orgzly working on Linux desktop using ARC Welder
								- Cons
									- Missing Ideal Features
										- **To replace Tasks?**
											- Feature parity
												- _Done_
													- Reminder notification
													  https://github.com/orgzly/orgzly-android/issues/26#issuecomment-300388461
													- Automatic sync
													  https://github.com/orgzly/orgzly-android/issues/8#issuecomment-344913322
													- Today view (agenda view)
													- Recurring/repeating tasks
													  https://github.com/orgzly/orgzly-android/issues/227
												- Notification persistence
												  https://github.com/orgzly/orgzly-android/issues/107
												- Clickable hyperlinks
												  https://github.com/orgzly/orgzly-android/issues/181
												- GUI to add links
												  https://github.com/orgzly/orgzly-android/issues/102
											- _To exceed Tasks_
										- To replace [[Software]] : [HabitHub](((664c986c-8374-46fc-a227-0c701c9e275c))) -
										- **To replace WorkFlowy?**
											- _Essential_
												- Zooming/hoisting/focusing into bullets (like WorkFlowy)
												  https://github.com/orgzly/orgzly-android/issues/21
													- And thus hyperlinks between notes  work
													- My Google+ feature request (zoom planned, hyperlinks desired but not figured out yet)
													  https://plus.google.com/107617112016126591346/posts/UG2wDHUk2Q1
													- He says its planned in Sep 2019
													  https://github.com/orgzly/orgzly-android/issues/607#issuecomment-535995562
												- Internal linking to narrowed views
												  https://github.com/orgzly/orgzly-android/issues/21
													- Internal links hopefully once zoom integrated
													- http://orgmode.org/manual/Internal-links.html#Internal-links
													- How to
														- As for linking to another note -- it would be good to stay compatible with Org mode. That is, to have a usable links from Org mode as well.
														- One idea is to use the search query as a link. So you'd have a "t.buy fruit". And if that returns one note, you'd jump to it. If it returns multiple notes, it will display them as a regular search does now.
														- This search expression could be then converted to Org mode's "advanced search". Though it would need a support from a custom link type (org-add-link-type).
														- Or we could start assigning ids to notes, though I'm not a big fan of that.
											- Collaboration
											- _Related: _A web client which supports CalDAV (e.g. Nextcloud Tasks)
											  #Software-PM https://workflowy.com/#/9c9a40470d20
											- Client/server model
											- _Lower importance_
												- Encryption support planned
												  https://github.com/orgzly/orgzly-android/issues/43
													- June 2016 email - PGP first, EncFS later
														- PGP support is planned, so you could have filename.org.gpg notebook someplace.
														- I've just TODO-ed EncFS support, thanks.
														  overview http://arstechnica.com/civis/viewtopic.php?t=1245367
													- Per-note encryption
												- Steganographic encryption
													- (He ignored suggestion for TrueCrypt) - only form of steganographic/deniable encryption
													- encrypted within hidden container
														- EDS current capabilities
															- Container mounting is supported (on rooted devices). You can use any file manager, gallery program or media player to access your files inside the container.(not available in the "Lite" version, root access required)
															- A container can be opened directly from a network share (not available in the "Lite" version).
															- Network shares can be mounted to the file system of your device. Automatic mount/dismount is supported (depending on the available Wifi connection)(not available in the "Lite" version, root access required)
														- _Syncing mobile changes_: mount TrueCrypt container using EDS. Copy file from local folder into mounted container. Then have Dropsync or FolderSync to sync with FTP/ownCloud/AWS etc
														- _Online version updated last_: mount TrueCrypt container using EDS. Copy file from mounted container into local folder. In Orgzly delete the old then import the notebook
												- Drag and drop bullets like WorkFlowy or Nestable
												  https://github.com/dbushell/Nestable
												- HandyFlowy power user enhancements
												  [archived] https://blog.workflowy.com/2016/04/21/handyflowy-workflowy/#more-1450
							- Existing Features
							  collapsed:: true
								- WorkFlowy-like view
									- https://orgmode.org/manual/Clean-view.html
								- Two-way sync with Dropbox and local directories (and via FTP/AWS etc in combination with FolderSync Lite)
								- Search
								  http://www.orgzly.com/help#Search
									- New
										- ** Tags inheritance (t operator)
											- t.tag now searches for inherited tags as well.
										- ** Search by note's tag only (new tn operator)
											- This is what t.tag used to do.
								- Outlinking
									- Version 1.4.4
									- Basic links support in note view
									- http, https and mailto are currently supported.  Both standalone and
									- within square brackets (both with and without the name).
									- IOW:
										- http://www.orgzly.com
										- [[mailto:sup...@orgzly.com][Support]]
										- [[http://www.orgzly.com/help]]
									- As of 1.4.4 now supports external links [[http://www.orgzly.com/][Like that]] ( http://orgmode.org/manual/External-links.html )
								- org-js
								  https://github.com/mooz/org-js
							- 1 Backlink
								- See [Orgzly](https://workflowy.com/#/f98c5435aacd)
						- SyncOrg
						  collapsed:: true
						  Forked from unmaintained MobileOrg
							- +Can sync with git repos | -Less features than Orgzl
							- +Sainath Adapa Yes, I have used it. It got released very recently and is still in beta state. +Orgzly feels more polished and stable. The plus of SyncOrg is that it does git synchronization, and you can also choose to sync to a private Gitlab repo if you like. The pluses of Orgzly are in all other areas: stability, features related to org todo, UI, etc. It would be awesome if both the devs joined forces to give the best of both apps.
							- https://play.google.com/store/apps/details?id=com.coste.syncorg
							- https://github.com/wizmer/syncorg
							- MobileOrg
							  Old and not updated?
								- how syncing works
									- https://www.reddit.com/r/orgmode/comments/4a5t2a/mobileorg_question/
				- Distributions
					- [Spacemacs](http://spacemacs.org/)
					  id:: 664373fe-15d7-47a1-8472-08013e1929de
					  collapsed:: true
						- Spacemacs/evil mode (emacs + vim)
						  id:: 67000f1e-bd81-470a-971c-7f4075cdfb52
						  collapsed:: true
						- [GitHub - syl20bnr/spacemacs: A community-driven Emacs distribution - The best editor is neither Emacs nor Vim,  it's Emacs *and* Vim!](https://github.com/syl20bnr/spacemacs)
						- 1
							- I’m a recent convert to Doom Emacs and although I’m extremely happy about it as a sweet spot of flexibility vs batteries-included, it required many hours of fiddling and research to make it usable, mostly due to the lack of documentation. Spacemacs, however, was practically a plug-and-play experience(*).
							- Now, Spacemacs started breaking on me when I tried to customize it too much, so it’s not perfect.
							- In short, if you want the most stable, easiest out of the box experience of Emacs including org-mode and its classic packages, such as org-agenda and org-capture, Spacemacs is probably your best bet.
					- [Doom Emacs](https://github.com/doomemacs/doomemacs)
					  collapsed:: true
						- [https://ethanaa.com/blog/switching-to-doom-emacs/#search-for-other-occurrences-in-buffer](https://ethanaa.com/blog/switching-to-doom-emacs/#search-for-other-occurrences-in-buffer)
						- [https://blog.jethro.dev/posts/migrating_to_doom_emacs/](https://blog.jethro.dev/posts/migrating_to_doom_emacs/)
						-
				- Forks
					- [emacs-ng](https://github.com/emacs-ng/emacs-ng)
					  collapsed:: true
						- [Homepage](https://emacs-ng.github.io/emacs-ng)
						- Automatically merges with upstream ((634bc1d7-6c8e-4cb1-8b72-5ebdbfb847ee)) weekly
						- additive native layer over emacs, bringing [features](https://emacs-ng.github.io/emacs-ng/#features) like:
							- Deno's Javascript and Async I/O environment, Mozilla's Webrender, and other features in development
							- TypeScript, Threading
						- [[2025-02-10 Monday]] Slow development speed, no active maintainers?
				- # Documentation
					- ## Packages
						- ### AI
							- AI code completion: copilot.el. Github Copilot code completion inside emacs. Very reliable. Can complete both code and text (eg. inside org-mode)
							- Code discussion: copilot-chat.el. Chat with github copilot. Since it use same account above, I assume one advantage of it over other LLM plugin is that it is free for people already subscribed to Github Copilot
							- Code change / refactor: aider. for emacs integration, aider.el. With the most recent claude model, claude-3-5-sonnet-20241022. My feeling is that I should try it firstly before writing the code by myself, cause its coding ability and code quality is really good.
							- [GitHub - lanceberge/elysium: Automatically apply AI-generated code changes in Emacs](https://github.com/lanceberge/elysium)
							- [GitHub - copilot-emacs/copilot.el: An unofficial Copilot plugin for Emacs.](https://github.com/copilot-emacs/copilot.el)
							- [GitHub - jart/emacs-copilot: Large language model code completion for Emacs](https://github.com/copilot-emacs/copilot.el)
							- [GitHub - emacs-openai/chatgpt: Use ChatGPT inside Emacs](https://github.com/emacs-openai/chatgpt)
							- [GitHub - joshcho/ChatGPT.el: ChatGPT in Emacs](https://github.com/joshcho/ChatGPT.el)
							- [GitHub - Exafunction/codeium.el: Free, ultrafast Copilot alternative for Emacs](https://github.com/Exafunction/codeium.el)
							-
					- [org-mode](https://orgmode.org/)
					  id:: 67000f1e-e944-453b-b4bd-cee69a8b44ec
					  collapsed:: true
						- _Confirmed features_
							- Can indent and hide leading stars (Clean View/org-indent-mode)
							  [https://i.imgur.com/ON2Vii8.png](https://i.imgur.com/ON2Vii8.png)
								- [https://orgmode.org/manual/Clean-View.html](https://orgmode.org/manual/Clean-View.html)
								- Getting rid of leading stars in the outline.
							- Changing stars into bullets
								- [https://github.com/sabof/org-bullets](https://github.com/sabof/org-bullets)
						- Questions
							- [https://emacs.stackexchange.com/](https://emacs.stackexchange.com/)
							- Zoom/hosting?
							  collapsed:: true
								- Zooming mode. When you move to a child heading, it automatically narrows the buffer to that heading. When you call outline-up-heading, the buffer is widened and narrowed to a parent heading.
								- I don't know of a mode or function to do this already, but it wouldn't be hard to write. Something like:
									- (defun my/org-zoom-in ()
										- (outline-next-visible-heading)
										- (org-narrow-to-subtree))
									- (defun my/org-zoom-out ()
										- (widen)
										- (outline-up-heading)
										- (org-narrow-to-subtree))
								- And you could turn it into a minor mode, advising the outline commands, easily enough.
							- Mouse-friendly?
								- org-mouse.el - built-in
								  collapsed:: true
								  [[emacs/org-mode.git - Emacs Org mode](https://code.orgmode.org/bzg/org-mode/src/master/lisp/org-mouse.el](https://code.orgmode.org/bzg/org-mode/src/master/lisp/org-mouse.el))
									- Description
										- built-in, just turn it on
										  [https://emacs.stackexchange.com/questions/55298/org-mode-collapse-expand-section-on-click](https://emacs.stackexchange.com/questions/55298/org-mode-collapse-expand-section-on-click)
										- ;; Org mouse implements the following features:
											- ;; * following links with the left mouse button
											- ;; * subtree expansion/collapse (org-cycle) with the left mouse button
											- ;; * several context menus on the right mouse button:
												- ;;    + general text
												- ;;    + headlines
												- ;;    + timestamps
												- ;;    + priorities
												- ;;    + links
												- ;;    + tags
											- ;; * promoting/demoting/moving subtrees with mouse-3
											- ;;    + if the drag starts and ends in the same line then promote/demote
											- ;;    + otherwise move the subtree
									- ;; FIXME:
										- ;; + deal with folding / unfolding issues
									- ;; TODO
										- ;; + org-store-link, insert link
										- ;; + org tables
										- ;; + occur with the current word/tag (same menu item)
										- ;; + ctrl-c ctrl-c, for example, renumber the current list
										- ;; + internal links
							- Hiding blocks (notes on WorkFlowy)
								- [https://emacs.stackexchange.com/questions/45982/org-mode-any-way-to-automatically-collapse-blocks-e-g-begin-quote?rq=1](https://emacs.stackexchange.com/questions/45982/org-mode-any-way-to-automatically-collapse-blocks-e-g-begin-quote?rq=1)
							- Interlinking? Seems so
								- Uses `org-store-link` to create a unique global ID for a location (equivalent to WorkFlowy bullet hyperlink) and/or a human-readable `CUSTOM_ID` (equivalent to WorkFlowy tags)
								  [https://orgmode.org/org.html#Handling-Links](https://orgmode.org/org.html#Handling-Links)
								- [https://orgmode.org/org.html#Internal-Links](https://orgmode.org/org.html#Internal-Links)
							- Making
						- [Org-roam](https://www.orgroam.com/)
						  collapsed:: true
							- seeks to copy Roam Research (outliner/graph view tool)
							  [https://www.orgroam.com/img/screenshot.png](https://www.orgroam.com/img/screenshot.png)
							- [GitHub - org-roam/org-roam-ui: A graphical frontend for exploring your org-roam Zettelkasten](https://github.com/org-roam/org-roam-ui)
							-
							- [https://news.ycombinator.com/item?id=28025491](https://news.ycombinator.com/item?id=28025491)
							- [https://youtu.be/Lg61ocfxk3c?t=372](https://youtu.be/Lg61ocfxk3c?t=372)
							- Documentation
								- [https://www.orgroam.com/manual/](https://www.orgroam.com/manual/)
								- _Modules_
									- company-org-roam - provides completion for org-mode files using [[
									- org-roam-server - shows graph/mindmap of backlinks and can be used for mouse navigation
									- org-roam-buffer - shows backlinks in a sidebar
									  [https://github.com/org-roam/org-roam/blob/master/doc/images/org-roam-graph.gif](https://github.com/org-roam/org-roam/blob/master/doc/images/org-roam-graph.gif)
										- The org-roam-buffer (window on the right) shows backlinks for the active Org-roam buffer (window on the left), as well as the surrounding content in the backlink file. The database is built once, and updated incrementally. The graph is generated from the link structure, and can be used to navigate to the respective files.
						- Org-sidebar - keep a tree view in a sidebar
						  [https://preview.redd.it/ytat2b3qaxp31.gif](https://preview.redd.it/ytat2b3qaxp31.gif?format=mp4&s=a32dd5dc1b3c35f83ab50cb266616f0f986e64fb)
							- [https://github.com/alphapapa/org-sidebar](https://github.com/alphapapa/org-sidebar)
						- emacs --daemon for quick startup
						- deft module for full-text search?
					- [Org-roam - seeks to copy Roam Research (outliner/graph view tool)](https://workflowy.com/#/5351330476f0)
					- Features
					  collapsed:: true
					  My manual
						- Key abbreviations:
							- M – Alt (used to be called Meta on ancient keyboards, that's why)
							- C – Control
							- S – Shift
							- C-x f – means holding both Control and x, release both, and press f
						- Shortcuts
							- Save
							  C-x C-s
							- Open/New
							  C-x C-f – open document
							- New Heading
							  ALT(M) + Enter(RET)
						- New document
							- Emacs does not actually understand you are editing an org-mode document, yet. To enable org-mode on your current document, type
								- M-x org-mode
								- Which will enable the org-mode on the current document.
							- To make Emacs understand that this is an org-mode document, add the following to the top of your document:
								- MY PROJECT -*- mode: org -*-
						- Changing list to idented headlines and subheadings
							- #+STARTUP: indent
							  Add to top of any .org file
							- (but this is how to activate it for all .org files http://orgmode.org/manual/Clean-view.html#Clean-view )
						- Cycling visibility of subheadings/content
							- TAB whilst on a heading to unfold subheadings (1 level)
							- TABx2 whilst on a heading to unfold all subheadings and content
							- TABx3 whilst on an unfolded headling to fold it
							- Move to it (click or arrows) + TAB whilst on an unfolded heading to fold it
							- SHIFT+TAB to close all, x2 to unfold subheadings (1 level), x3 to unfold all
							- http://orgmode.org/manual/Global-and-local-cycling.html#Global-and-local-cycling
						- Initial visibility
							- http://orgmode.org/manual/Initial-visibility.html
							- http://orgmode.org/manual/Property-syntax.html#Property-syntax
							- C-c C-x p     (org-set-property)
							- C-c C-c     (org-property-action)
								- With the cursor in a property drawer, this executes property commands.
						- Moving content
							- Move a heading up or down
							  Hold ALT + use arrow keys
							- Hierarchy
								- Promote or demote a headline
								  ALT(M) + arrow right/left
								- Move all subheadings up or down hierarchy
								  SHIFT + ALT + arrow right/left
						- Editing
							- Delete everything on the right of cursor
							  CTRL + K
						- TODO
							- Example
							  * TODO Headingtitle
							- Checkboxes - [ ] -
							- AGENDA
								- See Agenda
								  CTRL + T
								- Refresh Agenda
								  CTRL + G?
								- http://orgmode.org/worg/org-tutorials/org4beginners.html#orgheadline13
							- Switching from one TODO keyword to another is C-c C-t or S-<left/right>.
							- command org-todo (DONE)
							  C-c C-t
							- Can be scheduled
							  http://orgmode.org/img/planning.jpg
							- S-left/right – cycle workflow
							- C-c C-v – show todos in current document
							- http://orgmode.org/worg/org-tutorials/org4beginners.html#orgheadline11
						- Markup
							- You can make words *bold*, /italic/, _underlined_, =code= and ~verbatim~, and, if you must, +strike-through+.
						- Lists
							- Unordered lists start with -,+,or \*. Ordered lists start with a number and a dot. Descriptions use ::
							- http://bzg.fr/org-playing-with-lists-screencast.html
							- http://orgmode.org/manual/Plain-lists.html#Plain-lists
						- Capturing (i.e. adding TODOs)
							- Open capture
							  CTRL + C
							- Save
							  CTRL + C
						- Links
							- URL hyperlinks automatically recognised
							- [[link][description]]       or alternatively           [[link]]
							- You can directly edit the visible part of a link. Note that this can be either the ‘link’ part (if there is no description) or the ‘description’ part. To edit also the invisible ‘link’ part, use C-c C-l with the cursor on the link.
							- Internal links
								- link like ‘[[#_my-custom-id]]’ (**remove the underscore) **which will link to the entry with the CUSTOM_ID property ‘my-custom-id’. You are responsible yourself to make sure these custom IDs are unique in a file.
									- C-c C-x p     (org-set-property)
								- Links such as ‘[[My Target]]’ or ‘[[My Target][Find my target]]’ lead to a text search in the current file for the corresponding target which looks like ‘<<My Target>>’.
								- http://orgmode.org/manual/Internal-links.html
							- http://screencast.com/t/1vnwZcCvnzh5
							- https://youtu.be/fgizHHd7nOo?t=5m35s
							- http://orgmode.org/manual/External-links.html#External-links
						- Inline images
						- Tables
							- https://youtu.be/fgizHHd7nOo?t=6m59s
						- Export
							- to LaTeX or PDF
							  https://youtu.be/fgizHHd7nOo?t=15m11s
						- Clocking
							- Clocking in a task is C-c C-x C-i.
							- Clocking out a task is C-c C-x C-o.
							- You can use I and O from an agenda buffer.
							- Clocking logs are stored in a drawer.
							- Org makes it easy to clock in and out and to produce nice reports, which you can customize to suit the needs of your hairy boss.
					- Features (ALL)
						- Tabs/Windows
						  collapsed:: true
							- Frames
							  https://www.gnu.org/software/emacs/manual/html_node/emacs/Frames.html
							- Window Splitting (Tabs/windows-like) (CTRL + X)
							  https://www.gnu.org/software/emacs/manual/html_node/emacs/Split-Window.html
							- Tab Bar Mode
							  collapsed:: true
								- https://www.emacswiki.org/emacs/TabBarMode
								- https://github.com/dholm/tabbar
								- Tabbar Ruler allows drag-and-drop
								  https://github.com/mattfidler/tabbar-ruler.el
							- elscreen - tabs with fixed frames eg copying Thunderbird frames
							  collapsed:: true
								- http://emacs-fu.blogspot.com/2009/07/keeping-related-buffers-together-with.html
								- http://www.emacswiki.org/emacs/EmacsLispScreen
								- escreen - simpler version
									- http://www.emacswiki.org/emacs/EmacsScreen
									- https://www.reddit.com/r/emacs/comments/1osw07/comment/ccvd8q9
							- Add-ons
							  collapsed:: true
								- Winner Mode - go back to a previous window config
								  https://www.emacswiki.org/emacs/WinnerMode
						- Windows Configuration (what split windows/frames)
						  collapsed:: true
							- WorkgroupsForWindows
								- Workgroups a window-configuration persistence package.
						- Tables
						  collapsed:: true
						  Also spreadsheets, databases etc
							- Filtering
								- https://emacs.stackexchange.com/questions/20129/how-can-i-filter-table-in-org-mode
							- Org-mode as a spreadsheet
							  https://i.imgur.com/iwl8r8e.png
								- https://www.youtube.com/watch?v=I762W3lEUEk
								- http://orgmode.org/worg/org-tutorials/org-spreadsheet-intro.html
								- http://orgmode.org/manual/The-spreadsheet.html
							- Databases in Emacs
								- At some point plain text doesn't scale well. For a store, I'd be using a relational database, even sqlite https://www.emacswiki.org/emacs/SQLite-el That doesn't rule out org-mode as an interface, as it can be parsed and formatted by elisp.
								- https://www.emacswiki.org/emacs/SqlMode
								- https://github.com/kiwanami/emacs-edbi
						- Narrowing (zooming/hoisting/focusing)
						  collapsed:: true
							- Command C-c C-x b org-tree-to-indirect-buffer as the equivalent of zooming into a WorkFlowy bullet
							- or C-x n s (but some say its not as good as WorkFlowy's?)
							- https://stackoverflow.com/questions/17156595/in-emacs-org-mode-how-to-narrow-display-to-two-subtrees-in-two-separate-files
						- Enable stuff in variables/config init file
						  collapsed:: true
							- Recognise org-mode across all files
							  http://orgmode.org/worg/org-tutorials/org4beginners.html#orgheadline4
						- {Archive}
						  collapsed:: true
							- Demo - why Emacs is awesome
							  https://youtu.be/fgizHHd7nOo
							- http://orgmode.org/features.html
						- http://orgmode.org/worg/org-tutorials/org4beginners.html#orgheadline10
						- https://www.linuxjournal.com/article/9116?page=0,1
						- http://orgmode.org/worg/org-tutorials/orgtutorial_dto.html
						- http://github.com/jkitchin/jmax with all features in vid
						- https://www.youtube.com/watch?v=oJTwQvgfgMM google talk
						- http://mobileorg.ncogni.to/doc/getting-started/encryption/
						- Can export SOPs - Export to PDF, HTML, ODT, DOC
						- https://emacs.stackexchange.com/questions/9709/keep-the-headlines-expanded-in-org-mode
						  collapsed:: true
							- More Features
								- an Agenda system integrated for calendars (which can rollover tasks or set deadlines)
								- Keywords for marking entries and a good search system (combined with Helm it's pretty amazing).
								- Property drawers for entries.
								- replacing automated launches of WorkFlowy subtrees in the browser with some Emacs Lisp code to automatically open Org mode subtrees or create sparse trees
								- Tutorials
									- http://emacswiki.org/emacs/OrgMode
									- http://doc.norang.ca/org-mode.html
								- Emacs tutorial, that comes with Emacs itself (C-h t)
								- Advanced
									- http://orgmode.org/worg/org-configs/org-customization-guide.html
									- Evil mode = vim within emacs
										- vi-style key-bindings (which take time to learn but avoid combined keystrokes that may stress the hands).
								- Learning Streams
									- https://emacs.stackexchange.com
									- https://reddit.com/r/Emacs
									-
								- https://two-wrongs.com/why-you-should-buy-into-the-emacs-platform
					- Comparing emacs v markdown markup languages
					  https://mickael.kerjean.me/2017/03/20/emacs-tutorial-series-episode-2/
					- https://www.gnu.org/software/emacs/
				- [Learning Resources]
					- [The Emacs Window Management Almanac | Karthinks](https://karthinks.com/software/emacs-window-management-almanac)
					- [Learning Streams]
					  collapsed:: true
						- https://www.reddit.com/r/emacs
						- https://www.reddit.com/r/orgmode
						- http://emacsrocks.com
			- [Vim](https://www.vim.org/)
			  id:: 634d22db-89bb-432b-8dcf-776e2bd185ba
			  collapsed:: true
				- Pros/Cons
				  collapsed:: true
					- Pros
						-
					- Cons
						-
					- Unclear
					- Upstream/Downstream Pros/Cons
						- Downstream: ((663341b5-ddd5-4338-a332-195f59f96fd3))
					- Comparisons
						- ((634d22db-89bb-432b-8dcf-776e2bd185ba))vs ((634bc1d7-6c8e-4cb1-8b72-5ebdbfb847ee))
						  id:: 9c059bb1-0976-45e5-b420-676c8acdad61
						  collapsed:: true
							- [https://github.com/abo-abo/avy](https://github.com/abo-abo/avy)
							- For ((634d22db-89bb-432b-8dcf-776e2bd185ba))
								- Keybindings are arguable, but generally leans in favour of ((634d22db-89bb-432b-8dcf-776e2bd185ba))
								  collapsed:: true
									- For ((634d22db-89bb-432b-8dcf-776e2bd185ba))
										- Modal editing (two different modes) means that most commands take less keystrokes e.g. saving in Emacs in `CTRL + x`,  `CTRL + s` vs Vim is `:w`
										- Their keybindings won't interfere with [Common User Access (CUA)](https://en.wikipedia.org/wiki/IBM_Common_User_Access)keybindings e.g. `CTRL + X` (cut), `CTRL + V` (paste)
										- Emacs' keybindings more likely to cause repetitive stress injury, especially your left pinky finger due to hitting `CTRL` constantly. Often people rebind it to `CAPSLOCK`
									- For ((634bc1d7-6c8e-4cb1-8b72-5ebdbfb847ee))
										- Their keybindings is used in some other GNU software by default e.g. Bash
										- Keybindings may make more sense in some places e.g. [many of them are used in MacOS](https://jblevins.org/log/kbd)
							- For ((634bc1d7-6c8e-4cb1-8b72-5ebdbfb847ee))
								- Lots of powerful programs like ((67000f1e-e944-453b-b4bd-cee69a8b44ec)), magit
							- Similarities
								-
							- Unclear
								- ((17d08eab-9922-43c4-ab70-efcc65f70a87)) is the new debate
								- Differences between Vim and Emacs
								  collapsed:: true
									- https://stackoverflow.com/a/1433315
									- https://en.wikipedia.org/wiki/Editor_war#Comparison
									- https://unix.stackexchange.com/a/1010
									- https://www.reddit.com/r/emacs/comments/9hen7z/what_are_the_benefits_of_emacs_over_vim/
								- [The values of Emacs, the Neovim revolution, and the VSCode gorilla · Murilo Pereira](https://www.murilopereira.com/the-values-of-emacs-the-neovim-revolution-and-the-vscode-gorilla)
								  id:: 671377eb-39eb-4971-a3cb-bdbb8c34568f
								  collapsed:: true
									- Values and commentary
										- | Value | Commentary |
										  | --- | --- |
										  | **Approachability** | Ease of getting started with for typical tasks, and contribution friendliness |
										  | **Doing one thing well** | Unix philosophy, fitting into an ecosystem |
										  | **Editing efficiency** | Fewer interactions, mnemonics, composable keystrokes, etc. |
										  | **Extensibility** | The degree to which behavior and appearance can be changed |
										  | **Freedom** | Embraces [free](https://www.gnu.org/philosophy/free-sw.en.html) software, rejects proprietary software |
										  | **Integration** | Cohesive core and concerted third-party functionality |
										  | **Introspectability** | Capable of being understood and inspected ad-hoc |
										  | **Keyboard centrism** | Focus on keyboard interactions |
										  | **Maintainability** | The degree to which it can be modified without introducing faults |
										  | **Progressiveness** | A measure of eagerness to make progress and leverage modern technology |
										  | **Stability** | Things that worked before continue to work the same way |
										  | **Text centrism** | Text as a universal interface |
										  | **Velocity** | Short and focused release cycles, aligned personpower, leveraging the community effectively |
									- Emacs
										- Extensibility
										- Freedom
										- Introspectability
										- Keyboard centrism
										- Stability
										- Text centrism
									- Vim
										- Doing one thing well
										- Editing efficiency
										- Keyboard centrism
										- Stability
										- Text centrism
										- Notably doesn't have Extensibility, as it's plugin system is much weaker
									- Neovim
										- Approachability
										- Editing efficiency
										- Extensibility
										- Keyboard centrism
										- Progressiveness
										- Text centrism
										- Velocity
										- Notably doesn't have a focus on Stability, as they'd rather focus on Progressiveness i.e. move faster and possibly break things
										- Notably doesn't have the Freedom and Introspectability of Emacs
										- As I see it, it also currently has a better story than Emacs on:
											- **development process**: [non-mailing-list-driven-development](https://github.com/neovim/neovim/pulls) ([why it's better](https://asylum.madhouse-project.org/blog/2018/07/24/on-git-github-and-email/)), [extensive automated builds](https://github.com/neovim/neovim/blob/master/CONTRIBUTING.md#automated-builds-ci), a [public roadmap](https://neovim.io/roadmap/), [recurrent funding](https://neovim.io/sponsors/), frequent [stable, automated releases](https://github.com/neovim/neovim/releases)
											- **user interface**: all UI-related code for every single platform was removed from the core, replaced by a consistent [API](https://neovim.io/doc/user/api.html) (both TUIs and GUIs use it) that made a diversity of decoupled [display implementations](https://neovim.io/news/2020/10/#guis) possible (UIs are literally plugins!)
											- **out of the box experience**: better defaults, built-in LSP client
									- VSCode
										- Approachability
										- Integration
										- Maintainability
										- Progressiveness
										- Velocity
									- Comparison table
										- | Value | Emacs | Vim | Neovim | VSCode |
										  | --- | --- | --- | --- | --- |
										  | Approachability |  |  | ✓ | ✓ |
										  | Doing one thing well |  | ✓ |  |  |
										  | Editing efficiency |  | ✓ | ✓ |  |
										  | Extensibility | ✓ |  | ✓ |  |
										  | Freedom | ✓ |  |  |  |
										  | Integration |  |  |  | ✓ |
										  | Introspectability | ✓ |  |  |  |
										  | Keyboard centrism | ✓ | ✓ | ✓ |  |
										  | Maintainability |  |  |  | ✓ |
										  | Progressiveness |  |  | ✓ | ✓ |
										  | Stability | ✓ | ✓ |  |  |
										  | Text centrism | ✓ | ✓ | ✓ |  |
										  | Velocity |  |  | ✓ | ✓ |
									-
							- {Archive}
							  collapsed:: true
								- [Is It "WRONG" To Learn Emacs With The Evil Bindings - YouTube](https://youtu.be/omROuzns-m0)
								- [Vim vs Emacs | Prime Reacts - YouTube](https://youtu.be/v53okHVQZuA)
				- # Documentation
					- ## **Controls**
						- Mouse and keyboard - minimal
						  collapsed:: true
							- ## Modifier and editing keys
								- `TAB` =
								- `Caps Lock` =
								- `SHIFT` =
								- `CTRL` =
								  collapsed:: true
									- Ctrl-d, Ctrl-u, Ctrl-e, Ctrl-y
									- built-in autocompletion (works only in insert mode):
										- ctrl-n/ctrl-p - open keyword autocomplete menu (based on current 
										  file and included files) and go to next/previous suggestion; when 
										  autocompletion popup is opened, move to the next/previous suggestion
										- ctrl-x, ctrl-f - open autocompletion menu for file names (relative to current working directory)
										- ctrl-x, ctrl-] - open autocompletion menu based on tags (ctags)
										- ctrl-e  - exit autocompletion menu and drop inserted suggestion
									- Ctrl-w[s,v,+,-,<,>,=,h,j,k,l] - basic splits management: split horizontally, vertically, changing sizes of splits, moving between splits
									- [`CTRL`+`[`](https://vimhelp.org/insert.txt.html#i_CTRL-%5B) = End insert or Replace or mode, go back to Normal mode
									  id:: 664d1685-5e00-4dfa-a25f-cf954bb0df0d
								- `ALT` =
							- ## Character keys
								- ### Row 1: Number row
									- `{mark} = Jump to mark
									  id:: 6640dce9-16b3-4438-bd51-c2fc7e9f8118
									  collapsed:: true
										- Jump to the specified mark.
										  
										  With local marks that are found in the current text such as lower case letters, it can be used as a motion in commands.
										  When used with global marks found in a different text or buffer (such as captial letters), the cursor jumps to the mark, changing texts (buffers) in the process.
										  
										  :marks lists all the current marks.
									- `"` = Register specification
									  id:: 664665b7-1fb6-4bce-a378-459f0e201fdf
									  collapsed:: true
										- Use register {a-zA-Z0-9.%#:-"} for next delete, yank or put (i.e. paste).
										  
										  Use uppercase character to append with delete and yank.
										  
										  {.%#:} only work with put and are currently not supported in the game.
										  
										  Type :reg to see the register's content.
										- You can specify a register name before a paste command to tell VIM which register you'd like to paste from
											- e.g. `"2p` to paste the line that was deleted right before the most recent delete
										- `"_` = Black Hole register
											- Nothing is actually stored here, so you can use this to make delete operations without affecting the registers
										- The named registers `"a`-`"z` can be used before any delete, yank (and in the future also change or substitute) command.
											- When the upper case version of their name is used `"A`-`"Z`, the deleted text will be appended to their existing content instead of replacing it.
									- Use register {a-zA-Z0-9.%#:-"} for next delete, yank	or put (use uppercase character to append with delete and yank)
									- `$` = Move to the end of the current line
									  id:: 6640ed39-e97a-4136-b1b2-b775181a015a
									  collapsed:: true
										- To the end of the line.
										  
										  When a count is given also go [count - 1] lines downward.
										  
										  Example: $w2$
									- `%`  = Move to the matching bracket or parentheses
									  id:: 66412ed6-68a2-43e1-a6f6-2889f5ccfea9
									  collapsed:: true
										- Find the next item in this line after or under the cursor and jump to its match.
										  
										  Items can be: ( [ { } ] ) /* */ #if #ifdef #else #elif #endif.
										  
										  No count is allowed, {count}% jumps to a line {count} percentage down the file (isn't supported in the game).
									- `^` = Move to the first non-space character in the current line
									  id:: 66412091-d0ef-43fe-a1b5-0271ae1961b7
									  Similar: ((66411fc7-7131-42c2-a490-88b2d7653e53))
									- `*` = Search forward for the word nearest to the cursor
									  id:: 66413cd9-0607-48fa-8cba-38d0dd378562
									  collapsed:: true
									  Opposite: ((66413e1f-5c1b-4be1-8b37-50d2c8fb3683))
										- Search forward for the [count]'th occurrence of the whole word nearest to the cursor in the current line.
										  
										  The word used for the search is the first of:
										  1. the keyword (A-Za-z0-9_@) under the cursor
										  2. the first keyword after the cursor
										  3. the non-blank word under the cursor
										  4. the first non-blank word after the cursor
									- `1`-`9` = Use as a part of a number [count] before an operation or a motion to repeat it the specified number of times
									  id:: 6641b69c-4ca0-45de-a249-f2b2c0d1cf46
									  collapsed:: true
									  AKA digits / [count]
										- Desc
											- An optional number that may precede the command to multiply or iterate the command. If no number is given, a count of one is used, unless otherwise noted.
											  
											  You can use <Del> to erase the last digit.
										- Examples
											- `4j` = move 4 down
											  ((6640d1f9-d4c2-4dc9-ada8-65020c9c877d))
											- `3w` = to the beginning of the 3rd next word
											  ((6640cfc3-ea48-4d9a-9162-b20f7126c21c))
											- `2G` = To the first non-whitespace character in the line with that number (equivalent to `:2`)
											  ((66413ab6-1419-4402-8ba3-17d067ba258a))
											- `4$` = To the end of the line, 4 lines down
											  ((6640ed39-e97a-4136-b1b2-b775181a015a))
											- `3*` = 3rd occurrence of the same word you're currently cursoring over
											  ((66413cd9-0607-48fa-8cba-38d0dd378562))
											- `3x` = Delete current and next 2 characters
											  ((6640d610-296b-4ef7-80a7-8a2c8491e8e9))
											- `5~` = Swap next 5 characters to lower/uppercase
											- `2gg` = Go to 2nd line after first line of text
											  ((66413a7a-4bff-4e26-acc6-b89d61aebe0d))
											- ((6640e592-227d-4237-9d56-ca4fd77a191c))
												- ((66452040-2f6b-467f-a3ac-9ef2608f4779))
												- ((664526ba-a308-48be-a28f-9df0c3e297bb))
									- `0` = Move to the beginning of the current line
									  id:: 66411fc7-7131-42c2-a490-88b2d7653e53
									  collapsed:: true
									  Similar: ((66412091-d0ef-43fe-a1b5-0271ae1961b7))
										- To the first character of the line.
										  
										  Example: 0
										  (Press '+' or '-' to move through the example)
									- `(` = Move to the beginning of the current (or previous) sentence
									  id:: 66478362-411f-4bff-8cc0-2ac8f20265da
									  collapsed:: true
										- [count] sentences forward.
										  
										  A sentence (see :help sentence) is defined as ending at a `.`,`!` or`?` followed by either the end of a line, or by a space or tab. Any number of closing `)`, `]`, `"` and `'` characters may appear after the `.`,`!` or`?`  before the spaces, tabs or end of line.
										  
										  A paragraph boundary (an empty line) is also a sentence boundary.
									- `)` = Move to the beginning of the next sentence
									  id:: 66478369-2d24-4466-a693-8896e73e0d67
									- `-`
									- `_`
									- `=`
									- `+` = Go to the start of the next line
								- ### Row 2 (QWE)
									- `w` = Jump to the next beginning of word
									  id:: 6640cfc3-ea48-4d9a-9162-b20f7126c21c
									  collapsed:: true
									  Inverse: ((fee495bc-993e-45d3-bc93-910e40f9ded7))
										- [count] words forward.
										  
										  Position the cursor at the beginning of the word.
										  
										  A word (see :help word) consists of a sequence of letters, digits and underscores, or a sequence of other non-blank characters, separated with white space (spaces, tabs, EOL). An empty line is also considered to be a word.
										  
										  Example: wwww
									- `W` = Jump to the next beginning of WORD
									  id:: 6640e30f-f1aa-44ff-8753-5812c410d8aa
									  collapsed:: true
									  Inverse: ((6640d550-d418-4f60-9789-53c93642ce04))
										- [count] WORDs forward.
										  
										  Position the cursor at the beginning of the WORD.
										  
										  A WORD (see :help WORD) consists of a sequence of non-blank characters, separated with white space (spaces, tabs, EOL). An empty line is also considered to be a WORD.
										- Position the cursor at the beginning of the next word. Skips punctuation
									- `e` = Jump to the next end of word
									  id:: f7bbbe79-3274-4c9a-b28f-7e5696f9caf5
									  collapsed:: true
										- Forward to the end of word [count].
										  
										  Position the cursor at the end of the word.
										  
										  Does not stop in an empty line.
										  
										  A word (see :help word) consists of a sequence of letters, digits and underscores, or a sequence of other non-blank characters, separated with white space (spaces, tabs, EOL). An empty line is also considered to be a word.
									- `E` = Jump to the next end of WORD
									  id:: 6640e341-f867-4bb2-92a9-4c3bcdc7ecac
									  collapsed:: true
										- Forward to the end of WORD [count].
										  
										  Position the cursor at the end of the WORD.
										  
										  Does not stop in an empty line.
										  
										  A WORD (see :help WORD) consists of a sequence of non-blank characters, separated with white space (spaces, tabs, EOL). An empty line is also considered to be a WORD.
									- `r``{char}` = Replace the character under the cursor with another one `{char}`
									  id:: 6640e3fa-5b9c-4768-aff0-f2c9238ad97f
									  collapsed:: true
										- Replace the character under the cursor with {char}.
										  
										  If you give a [count], VIM replaces [count] characters with [count] {char}s.
										  
										  Example: rXrX6rX
									- `CTRL`+ `r`/`R` = Redo
									  id:: 664ca859-e1e6-41c3-86e8-fe072590f43e
									  collapsed:: true
										- Redo [count] changes that were undone.
										  :redo - redo one change that was undone.
										  
										  Note that the r can be either lowercase or uppercase.
									- `t``{char}` = Move to one character before the next occurrence of a given character in the same line
									  id:: 664128ed-cf79-4553-9103-8e2ed4440ce3
									  collapsed:: true
									  Similar: ((664124da-375b-45e7-a03e-ddc6eabfbae5))
										- Till before [count]'th occurrence of {char} to the right.
										  
										  The cursor is placed on the character left of {char}.
									- `T``{char}` = Move to one character before the previous occurrence of a given character in the same line
									  id:: 664128f6-9b22-4aa8-90a7-aa81fa8a89ba
									  collapsed:: true
										- #+BEGIN_WARNING
										  When going backwards like this you need to use the character on the left-side instead. This means you're following the direction of travel, and still ending up "before" that character
										  #+END_WARNING
									- `y``{motion}` = Yank (copy)
									  id:: 66466a2f-df30-4522-a762-af9012f38835
									  collapsed:: true
										- Yank {motion} text [into a register].
										  
										  Text is stored into "0 register unless another register is specified.
										- Examples
											- `yy` = Linewise yank (copy) text
											  id:: 66466a6b-ccb7-45c1-b5a1-f1094aeb30fb
											  Equivalent to ((66477c6a-6d56-449b-982a-b078b71daeb8))
												- Yank whole line
												- Yank [count] lines [into a register].
												  
												  The cursor position in the line doesn't matter.
												  
												  Text is stored into "0 register unless another register is specified.
											- ((664665b7-1fb6-4bce-a378-459f0e201fdf))
												- `"ayh` = Yank current character and character to the left
											- `yl` = Copy current character
											- `yip` = Yank insert ? copy all of paragraph and move to first character?
									- `Y` = Linewise yank (copy) text
									  id:: 66477c6a-6d56-449b-982a-b078b71daeb8
									  Equivalent: ((66466a6b-ccb7-45c1-b5a1-f1094aeb30fb))
									- `u` = Undo [count] changes
									  id:: 664cc9bf-f15c-4530-a9e5-7fab2ab8c5aa
									  collapsed:: true
										- `:undo` = undo only one change
									- `i` = Insert text before cursor position
									  id:: 6647050f-9384-4c47-a66c-2f0c58fa9b65
									  collapsed:: true
									  Similar: ((66475f9a-66e8-4818-8e90-94895ab98c72))
										- Insert text before the cursor [count] times.
										  
										  In the game, you can't add text that is longer than the missing text. When a count is specified and the total length exceeds the length of the missing text, the count will be ignored resulting in a single text addition.
									- `I` = Insert text before first non-space character in the current line
									  id:: 6647052c-d545-4009-82c2-eaf3e2600e6b
									- `ia` = text-objects
									  id:: 6647904f-7373-4d00-908c-29ba3366ad6c
									  collapsed:: true
										- Text objects let you select a meaningful text element you're currently standing on such as a sentence, a code block, a quoted string, etc as the range of an operation with any additional movement.
										- Text objects are two characters used after an operator (`d`, `y`, `c`, etc.) to select a range to operate on.
											- The first character is either `a`(for "an object", including white space) or `i` (for "inner" object, without surrounding white space, or only the white space).
											- The second character denotes the object type and is one of the following:
												- `w`ord, `W`ORD, `s`entence, `p`aragraph,
												- `"` or `'` or \` = a `"`, `'`, or \` quoted string
													- Unique attributes:
														- They only work within 1 line
														- When used not within a quote, one is searched for down the line
														- When standing on a quote, the pairs are determined from the beginning of the line
												- `{`, `}`, or `B` = A `{ }` block
												- `(`, `)`, or `b` = A `( )` block
												- `[` or `]` = A `[ ]` block
												  id:: f2bfffc4-c8c0-4980-ac3a-cb01c13cd274
												- `<` or `>` = A `< >` block
												- `t` = A HTML or XML tag block
											- Type :help followed by any text object (e.g. `ap`, `a{`, `i'` etc.) for examples.
										- Examples
											- `yiw` = Copy inner word (e.g. copy the word "hippo" whilst cursor is on any letter in the word)
											- `d2a}` = Delete everything (assuming cursor is inside a nested code block) in inner + outer (parent) code block
											  ((f2bfffc4-c8c0-4980-ac3a-cb01c13cd274))
											- `c2a[` = Change outer `[ ]` code block
											- `ci"` = Change inner `"` quote on the same line (cursor doesn't have to be in it even)
											-
										- More info
											-
										- [Learning Resources]
											- [Mastering the Vim Language - YouTube](https://youtu.be/wlR5gYd6um0?t=545)
												- `iw` = inner word (works from anywhere in a word)
												- `it` = inner tag (the contents of a HTML tag)
												- `i"` = inner quotes
												- `ip` = inner paragraph
												- `as` = a sentence
												- Example 1
													- `diw` whilst cursor is inside a word will delete the word
													- `dit` whilst inside a HTML tag will delete the contents of that tag
													- etc
												- Start-6:50
													- Verbs + nouns e.g. `d` (delete) + `w` (word)
											- [vim: Text objects - YouTube](https://youtu.be/SIePe-A4rs0)
												- `vaw` = select a word in visual mode (includes whitespace after word)
												- `viw` = select a word in visual mode (doesn't include whitespace after)
												- `viW` select a WORD " " (e.g. "turn-on")
												- `vas` = select a word (includes whitespace after)
									- `o` = Open a new line below the current line and enter insert mode.
									  id:: 6647633d-b4d9-4796-a466-41bb2ae5dd02
									  collapsed:: true
										- Begin a new line below the cursor and insert text, repeat [count] times.
										- Examples
											- `4o` = Create 4 lines, duplicate the content of insert mode into every line
									- `O` = Open a new line above the current line and enter insert mode.
									  id:: 6647638c-cb9e-49ee-b8f3-0a2d02614a4a
									- `p` = Paste text [from the specified register, default `""`] after the current position
									  id:: 66453ba2-cd52-4896-ab3c-d20b76eae4ed
									  collapsed:: true
										- Paste the last yanked, changed, or deleted text after the current position
										- Put the text [from the specified register] after the cursor [count] times.
										  
										  When no register is specified, use the unnamed register (") which contains the last text deleted (d, x), changed (c, s), or yanked (y).
									- `P` = Paste text [from the specified register, default `""`] before the current position
									  id:: 66453c62-9bd0-4d97-b561-230d432bc80d
									  collapsed:: true
										- Paste the last yanked, changed, or deleted text before the current position
									- `[` = Use `[{` or `[(` to find the first unmatched `{` or `(` going backward from current position
									  id:: 66477d84-ca40-4595-9f75-35f50878a51b
									  collapsed:: true
										- Go to [count] previous (or next) unmatched '{' (or ')') starting at, but not including, cursor position.
										- Great for jumping to the beginning of the code block you're currently in
									- `]` = Use `]}` or `])` to find the first unmatched `}` or `)` going forward from current position
									  id:: 66477d96-e902-4355-b789-08ac05d7c8ae
									  collapsed:: true
										- Great for jumping to the end of the code block you're currently in
									- `{` = Move to the empty line before the current (or previous) paragraph
									  id:: 66477aa5-cbd8-469a-895a-6b7af309de8a
									  collapsed:: true
										- Moves the previous paragraph if the cursor is not in a paragraph
									- `}` = Move to the empty line after the current (or next) paragraph
									  id:: 66477a74-49a4-461f-8233-3a6f391793be
									  collapsed:: true
										- [count] paragraphs forward.
										  
										  Move the cursor to the empty line after the current paragraph, or after the next paragraph if the cursor isn't in a paragraph. See :help paragraph .
								- ### Row 3 (ASD)
									- `a` = Append text after cursor position
									  id:: 66475f9a-66e8-4818-8e90-94895ab98c72
									  collapsed:: true
									  Similar: ((6647050f-9384-4c47-a66c-2f0c58fa9b65))
										- Append text after the cursor [count] times.
										  
										  If the cursor is in the first column of an empty line Insert starts there.
										- Enters insert mode
									- `A` = Append text at the end of the current line
									  id:: 66475ff5-d4c2-4d86-b62b-0913ba9db13e
									  collapsed:: true
										- Examples
											- `5A!` = Paste `!!!!!` at the end of the current line
									- `s` =  Substitute current char with new text (enters insert mode)
									  id:: 6646fe73-b079-489a-84e1-5d484de5e874
									  collapsed:: true
									  AKA Substitute | Equivalent to ((66470485-e47e-477e-8ea5-73df6c8af2b4))
										- Delete characters into register and start insert
										- Delete (substitute) [count] characters [into the specified register] and start insert (s stands for Substitute).
										  
										  Synonym for "cl" (not linewise).
										- Examples
											- `5s` = Delete 5 characters and enter insert mode
											  id:: 6647592b-9ab7-48cf-82f5-f44c0d75dda3
											  Equivalent to `ce` of a 5 letter word
												- {{embed ((664759d0-6a92-4156-9ca9-dd4bccb95205))}}
										- Basically more concise version of ((6646748e-e0dc-4c92-8f00-3228dcc82022)) but more limited
									- `S` = Substitute current line with new text (enters insert mode)
									  id:: 66475aec-3e9a-4115-a121-4d2c4293afb6
									  Equivalent to ((66467501-d6f7-4e62-a6de-fbb4e4b9cbd0))
									- `d``{motion}` = Delete range indicated by following motion
									  id:: 6640e592-227d-4237-9d56-ca4fd77a191c
									  collapsed:: true
									  For deleting whole words | Related: ((6640d610-296b-4ef7-80a7-8a2c8491e8e9))
										- Desc
										  collapsed:: true
											- Delete text that {motion} moves over [into a register if specified].
											  
											  See also help on "dd".
											  
											  Example: dwdbd7l
										- `{motion}` examples
											- `dd` = Delete the entire current line, regardless of where the cursor is
											  id:: 664121a0-efb7-4708-bd5f-ae4e384ceaf0
											  Similar: ((66467501-d6f7-4e62-a6de-fbb4e4b9cbd0))
											- `dj` = Delete the current line and 1 line below
												- `4dj` = Delete current line and 4 lines below
												  id:: 66452040-2f6b-467f-a3ac-9ef2608f4779
											- `d$` = Deletes to the rest of the line
											- ((664124da-375b-45e7-a03e-ddc6eabfbae5))
												- `d2fX` = Delete everything up to the second "X" character
												  id:: 664526ba-a308-48be-a28f-9df0c3e297bb
												- `d3f ` = Delete everything up to the 3rd whitespace
											- ((66412ed6-68a2-43e1-a6f6-2889f5ccfea9))
											  Delete all content in a code block
												- Alternate: `G` or `gg`
									- `D` = Delete from the current position until the end of the line
									  id:: 66477e70-3caa-4a29-85a8-a16c0b9112d6
									- `f``{char}` = Move to the next occurrence of a given character in the same line
									  id:: 664124da-375b-45e7-a03e-ddc6eabfbae5
									  collapsed:: true
									  Similar: ((664128ed-cf79-4553-9103-8e2ed4440ce3))
										- To [count]'th occurrence of {char} to the right.
										  
										  The cursor is placed on {char}.
									- `F``{char}` = Move to the previous occurrence of a given character in the same line
									  id:: 66412519-4030-4c04-ba78-5897e208fda0
									- `g`
									  collapsed:: true
										- gu[u,w]/gU[U,w] - switch to lowercase/uppercase [whole line, word]
										- gt, gT - go to next/previous tab page
										- gf - edit file whose name is under cursor (can be relative to pwd path or full path
										- ga - print unicode number (dec, hex, oct) for character under cursor
										- gj, gk - move one line down/up in wrap mode
									- `gg` = Move to the first line of the text (soft beginning of line)
									  id:: 66413a7a-4bff-4e26-acc6-b89d61aebe0d
									  collapsed:: true
										- Goto line [count], default first line, on the first non-blank character.
									- `G` = Move to the last line of the text (soft beginning of line) or to the given [count] line number
									  id:: 66413ab6-1419-4402-8ba3-17d067ba258a
									  collapsed:: true
										- `G``<digit>` = Go to the line number `<digit>`
										  id:: 664ca395-7b26-40ac-8c5d-b565b3f805d9
										  Equivalent to ((664ca361-854f-4396-b444-bb4762465164))
									- `h` = Move left by one character
									  id:: 99ab4d04-98f2-4911-ad14-169c63c9ea60
									- `H` = To line [count] from top (Home) of window on the first non-blank character
									  id:: 664c95f2-5bf3-411d-90be-efe27e7e59d3
									- `j` = Move down by one character
									  id:: 6640d1f9-d4c2-4dc9-ada8-65020c9c877d
									  collapsed:: true
										- `j/k` whilst cursor is on the final character of a line of text
										  id:: 6640d279-a631-4243-9654-74d7f0d19e41
											- Moves you to the final character of a line of text of the line above/below as appropriate, rather than vertically in the same column
									- `k` = Move up by one character
									  id:: 6640d213-5e89-4e80-af1a-4461ed7b072d
									  collapsed:: true
										- ((6640d279-a631-4243-9654-74d7f0d19e41))
									- `l` = Move right by one character
									  id:: 6640d21a-025a-46ff-bb35-f967926c4b17
									- `L` = To line [count] from bottom of window (Low) on the first non-blank character
									  id:: 664c961c-d847-4d71-919f-cb2f49aab724
									  collapsed:: true
										- To line [count] from bottom of the window (Low) on the first non-blank character (linewise), without scrolling the screen.
										  
										  In this game, if the last line of the text is visible on the screen use it instead of the bottom line on the window.
									- `;` = Repeat latest `f`, `t`, `F` or `T` search
									  id:: 66412b24-9f42-42cd-91ee-dc5ae6c3476a
									  collapsed:: true
										- Repeat latest f, t, F or T [count] times.lhjll
									- `:` = Enter VIM Command line mode
									  collapsed:: true
										- `:``<digit>` = Go to line `<digit>`
										  id:: 664ca361-854f-4396-b444-bb4762465164
										  Equivalent to ((664ca395-7b26-40ac-8c5d-b565b3f805d9))
										- `:reg` = View registers
										  id:: 66466200-5a6d-45f3-9a11-1d07b8732eb7
										  collapsed:: true
											- i.e. where cut text is stored
											- A register is denoted by `"` followed by a single character for the register's name
												- Examples
													- `"d` = register named `d`
													- `"-` = register named `-`
													  id:: 66466241-d0db-4551-87a6-7fb7fb66a6c0
											- Text than is shorter than a line is automatically saved to ((66466241-d0db-4551-87a6-7fb7fb66a6c0)) if target register isn't specified
											- When you delete a line or more the deleted content is stored in numbered registers `"1`-`"9`. The latest delete is stored in `"1` and so on. When another line is deleted, the text is `"9` is discarded and all content is moved down by 1.
										- `:ls` = List current buffers
										  id:: 664670a5-8212-4ba0-befc-e288d2158119
										  collapsed:: true
											- Buffers allow you to edit multiple files at the same time.
											- The active buffer is marked with `%` and the buffer you came from is marked with `#`
											-
										- `:b` =  Swap buffer
										  id:: 66470115-7bb6-4168-aa27-6f37afcafd9e
										  collapsed:: true
											- To switch buffers you can use `:b buffer_name` or `:b buffer_number` when the number is the index of the buffer in the output of `:ls`
												- You can also type `:b#` to switch to the last buffer before the current one (the only marked with `#`)
										- `:help` = View full command list
										- `:set` =
										  id:: 664c9be1-95d1-4330-92a4-e7d36dc0cb9b
										  collapsed:: true
											- ((664c9b79-7681-423d-bc77-4858fb5fee7d))
										- `:marks` = See a list of all the marks in the current text, as well as the global ones.
										  id:: 664c9ecf-1a72-4093-b5f5-445325a5d779
										  collapsed:: true
											- You can narrow the list by providing the flags you're interested in. For example `:marks Spencer` will list the marks `S`, `p`, `e`, `n`, `c` and `r`
										- `:delm` = Delete marks
										  id:: 664ca910-085e-4571-902a-f8492265664d
										  collapsed:: true
											- You can remove marks with `:delm`. Just list the marks
											- `:delm!` = Delete all the local marks
									- `'{mark}` = Jump to the first non-blank character in the line of the specified mark (linewise motion)
									  id:: 664caa6e-18aa-4c94-907b-78ecc27cfeb3
									  collapsed:: true
										- Jump to the first non-blank character in the line of the specified mark.
										  
										  With local marks that are found in the current text such as lower case letters, it can be used as a linewise motion.
										  When used with global marks found in a different text or buffer (such as captial letters), the cursor jumps to the mark, changing texts (buffers) in the process.
									- `#` = Search backwards for the word nearest to the cursor
									  id:: 66413e1f-5c1b-4be1-8b37-50d2c8fb3683
									  collapsed:: true
									  Inverse: ((66413cd9-0607-48fa-8cba-38d0dd378562))
										- Search backward for next occurrence of the whole word nearest to the cursor in the current line
									- `~` = Flip the case of the character under the cursor
									  id:: 6640eab7-c8f2-46eb-9e87-01a7d193a21a
									  collapsed:: true
										- Switch case of the character under the cursor and move the cursor to the right.
										  
										  If a [count] is given, do that many characters.
										  
										  Example: ~~99~
								- ### Row 4 (ZXC)
									- `|` = Move to column [count] in the current line
									  id:: 664c9a8a-dc2e-4c7c-ab29-ffc2f744df46
									  collapsed:: true
										- `33|` = Move to column 33
									- `z` = Scroll the screen without moving the cursor
									  id:: 66412be9-2ed3-475d-9936-5e4357f23c99
									  collapsed:: true
										- Desc
										  collapsed:: true
											- Redraw, cursor line at
											  
											  zt - Top of window
											  
											  zz - Center of window
											  
											  zb - Bottom of window
										- Examples
											- `t` = top
											- `z` = middle
											- `b` = bottom
									- `Z` = prefix?
									  collapsed:: true
										- ZZ - save file in current window and quit it (works same as :wq), only works for existing files
										- ZQ - drop unsaved in file changes in current window and quit it (works same as :q!)
									- `x` = Delete the character under the cursor (forward delete)
									  id:: 6640d610-296b-4ef7-80a7-8a2c8491e8e9
									  collapsed:: true
									  Similar: ((6640e592-227d-4237-9d56-ca4fd77a191c)) / ((6646748e-e0dc-4c92-8f00-3228dcc82022))
										- Delete [count] characters under and after the cursor in the current line [into a register if specified]. Does the same as 'dl'.
										  
										  Example: xxx2x
									- `X` = Delete the character before the cursor (backspace)
									  id:: 6640ea7e-d024-433a-ac79-ddc6ed577286
									- `c``{motion}` = Change range indicated by the following motion (w, e, etc.) and enter insert mode
									  id:: 6646748e-e0dc-4c92-8f00-3228dcc82022
									  collapsed:: true
									  i.e. delete range + replace | Similar: ((6640e592-227d-4237-9d56-ca4fd77a191c))
										- Delete (change) {motion} text [into the specified register] and start insert.
										- "cw" and "cW" are treated like "ce" and "cE" if the cursor is on a non-blank. This is because "cw" is interpreted as change-word, and a word does not include the following white space.
											- When standing on a non-blank character and using `cw` the change doesn't include spaces following the word. This is because `cw` is interpreted as change-word, and a word does not include the following white space
										- After using the red key, it's good to remember that text deleted with change (`c`, `cc` or `C`) or substitute (`s` or `S`) commands are automatically yanked into the relevant register ready to be pasted
										- Examples
											- `cl` = Delete current character into register and start insert
											  id:: 66470485-e47e-477e-8ea5-73df6c8af2b4
											  Equivalent: ((6646fe73-b079-489a-84e1-5d484de5e874)) / `cw`
											- `cc` = Delete lines into register and start insert
											  id:: 66467501-d6f7-4e62-a6de-fbb4e4b9cbd0
											  collapsed:: true
											  Equivalent: ((66475aec-3e9a-4115-a121-4d2c4293afb6)) | Similar: ((664121a0-efb7-4708-bd5f-ae4e384ceaf0))
												- Delete (change) [count] lines [into the specified register] and start insert (linewise).
												  
												  Synonym for S.
											- `ce` = Delete current character until end of word
											  Equivalent (assuming 5 letter word): ((6647592b-9ab7-48cf-82f5-f44c0d75dda3))
												- ((6646748e-e0dc-4c92-8f00-3228dcc82022)) is similar to ((6640e592-227d-4237-9d56-ca4fd77a191c)); whilst ((6646fe73-b079-489a-84e1-5d484de5e874)) is similar to ((6640d610-296b-4ef7-80a7-8a2c8491e8e9))
												  id:: 664759d0-6a92-4156-9ca9-dd4bccb95205
											- `c$` = Change text from current location until teh end of the line
											  id:: 66478046-4f64-4cd9-b9a6-2cf9219c9c9c
											  Equivalent to: ((664674cb-f888-47ab-835f-415bb40055a2))
									- `C` =  Change text from current location until the end of the line
									  id:: 664674cb-f888-47ab-835f-415bb40055a2
									  collapsed:: true
									  Equivalent to: ((66478046-4f64-4cd9-b9a6-2cf9219c9c9c))
										- Delete (change) from the cursor position to the end of the line and [count]-1 more lines [into the specified register], and start insert.
										  
										  Synonym for c$ (not linewise).
										- `2C` = Delete the current line and next 1 line
									- `b` = Jump to the previous beginning of word
									  id:: fee495bc-993e-45d3-bc93-910e40f9ded7
									  collapsed:: true
									  Inverse: ((6640cfc3-ea48-4d9a-9162-b20f7126c21c))
										- [count] words backward.
										  
										  Position the cursor at the beginning of the word.
										  
										  A word (see :help word) consists of a sequence of letters, digits and underscores, or a sequence of other non-blank characters, separated with white space (spaces, tabs, EOL). An empty line is also considered to be a word.
									- `B` = Jump to the previous beginning of WORD
									  id:: 6640d550-d418-4f60-9789-53c93642ce04
									  collapsed:: true
									  Inverse: ((6640e30f-f1aa-44ff-8753-5812c410d8aa))
										- [count] WORDS backward.
										  
										  Position the cursor at the beginning of the WORD.
										  
										  A WORD (see :help WORD) consists of a sequence of non-blank characters, separated with white space (spaces, tabs, EOL). An empty line is also considered to be a WORD.
										  
										  Example: BBB
									- `n` = Repeat the last `*``#``? ` or `/` search in the same direction
									  id:: 664141c4-28b1-474d-9962-cf595f20eccc
									  collapsed:: true
										- Repeat the latest "/" or "?" [count] times.
										- `*` and `#` searches are also considered "/" and "?" repectively.
											- ((66413cd9-0607-48fa-8cba-38d0dd378562))
											- ((66413e1f-5c1b-4be1-8b37-50d2c8fb3683))
										- id:: 6641b5c7-8609-4438-bb7d-5a12fb28c6c7
										  #+BEGIN_TIP
										  Useful because trying to use the search button again may overwrite the query
										  #+END_TIP
									- `nu`, `nonu` = Show the line number in front of each line in the text
									  id:: 664c9b79-7681-423d-bc77-4858fb5fee7d
									  collapsed:: true
										- Show the line number in front of each line in the text. Off by default.
										  
										  Makes it really easy to jump to a specific line using ':' and the line number, or the line number followed by G or gg.
										  
										  :set nu - shows line numbers.
										  :set nonu - hides line numbers.
										  :set nu! - toggle line numbers.
										  :set nonu! - toggle line numbers.
									- `N` = Repeat the last `*``#``? ` or `/` search in the opposite direction
									  id:: 66414201-db99-4a0c-9bd0-96ac396a5b4b
									- `m{mark}` = Set mark {a-zA-Z} at cursor position
									  id:: 664cc8fb-1024-4338-a05b-4b9fc064ce89
									  collapsed:: true
										- Set a mark at cursor position (shown as a flag, but is invisible in VIM).
										  Local marks such as lower case a - z‎ are private to the current text and can mark different locations in different texts at the same time.
										  Global marks, such as capital A - Z are unique and save also the filename or buffer. A new global mark will always replace the existing one if any.
									- `M` = To Middle line of window, on the first non-blank character
									  id:: 664c9a18-c4ce-4b6c-af6d-5fcbb73174be
									  collapsed:: true
										- To Middle line of window, on the first non-blank character (linewise), without scrolling the screen.
										  
										  In this game, if either of the first line of the text, the last line of the text, or both are visible on the screen use them instead of the first and last line of the window for calculating the middle.
									- `,` = Reverse the last `f`, `t`, `F` or `T` search
									  id:: 66412873-d125-4152-a3fa-612ab7993c1c
									  collapsed:: true
										- Repeat latest `f`, `t`, `F` or `T` in the opposite direction
										- Repeat latest f, t, F or T in opposite direction.
										  
										  Example: fu,tt2,
									- `.` = Repeat last change
									  id:: 6647b388-3053-4cc6-93de-9bb33e663329
									  collapsed:: true
										- Repeat the last simple change. Without a count, the count of the last change is used. If you enter a count, it will replace the last one.
										  
										  If the last change included a specification of a numbered register, the register number will be incremented.
										  
										  Does not repeat a command-line command.
										- Simple changes can be either the last command executed (e.g. `dw`, `2rG`, etc) or the entire last edit operation including all the text entered in insert mode (for example `ct"Awesome<esc>`). Movements are not considered as changes.
										  
										  If a count is not supplied with the dot command, the count used in the last simple change is used. If a count is specified, it is used instead.
										- Examples of what it can repeat
											- `ciw` followed by inserting "hello"
									- `/` = Search forward for [count]'th occurrence of search pattern specified
									  id:: 664c9fa1-73f4-4b2f-b6bb-4c9261c439a7
									  collapsed:: true
										- Search forward '/' or backward '?' for the [count]'th occurrence of pattern (not restricted to whole words).
										  
										  /pattern - Search forward for pattern
										  / - Search forward for last pattern
										  ?pattern - Search backward for pattern
										  ? - Search backwards for last pattern
										  
										  'n' and 'N' also work with '/' and '?'.
									- `?` = Search forward for [count]'th occurrence of search pattern specified
									  id:: 664c9fed-8399-48ec-bfb6-35690ef4a2c0
								- `Spacebar` =
							- ## Function keys
								- `F1` =
							- ## Navigation and other editing keys
								- `Backspace` =
								- `Up` =
								- `Down` =
								- `Left` =
								- `Right` =
							- ## **Specific Contexts**
						- Mouse and keyboard - full
						  collapsed:: true
							- Mouse
								- `LMB` =
								- `RMB` =
								- `MMB` =
								- `MMB scroll` =
							- Modifier and editing keys
							  collapsed:: true
								- `TAB` =
								- `Caps Lock` =
								- `SHIFT` =
								- `CTRL` =
								- `ALT` =
							- Character keys
								- `WASD` = Character movement
								- Row 1: Number row
									- ` =
									- `1` =
									- `2` =
									- `3` =
									- `4` =
									- `5` =
									- `6`=
									- `7` =
									- `8` =
									- `9` =
									- `0` =
									- `-` =
									- `+` =
								- Row 2 (QWE)
									- `Q` =
									- `R` =
									- `T` =
									- `Y` =
									- `U` =
									- `I` =
									- `O` =
									- `P` =
									- `[` =
									- `]` =
								- Row 3 (ASD)
									- `A` =
									- `S` =
									- `D`
									- `F` =
									- `G` =
									-
									-
									- `K` =
									- `L` =
									- `;` =
									- `'` =
									- `#` =
								- Row 4 (\ZX)
									- `\` =
									- `Z` =
									- `X` =
									- `C` =
									- `V` =
									- `B` =
									- `N` =
									- `M` =
									- `,` =
									- `.` =
									- `/` =
								- `Spacebar` =
							- Function keys
							  collapsed:: true
								- `F1` =
								- `F2` =
								- `F3` =
								- `F4` =
								- `F5` =
								- `F6`=
								- `F7` =
								- `F8` =
								- `F9` =
								- `F10` =
								- `F11` =
								- `F12` =
							- Navigation and other editing keys
								- `Backspace` =
								- `Enter` =
								- `Insert` =
								- `Delete` =
								- `Home` =
								- `End` =
								- `Page Up` =
								- `Page Down` =
								- `Up` =
								- `Down` =
								- `Left` =
								- `Right` =
							- Numeric keypad
							  collapsed:: true
								- `1` =
								- `2` =
								- `3` =
								- `4` =
								- `5` =
								- `6`=
								- `7` =
								- `8` =
								- `9` =
								- `0` =
							- ## **Specific Contexts**
					- Cheatsheet
					- ## Learning resource sorted by priority
					  id:: 59f7513e-af19-46a4-a49c-0ffa64ace1ba
						- ((634bd1ec-d116-4fef-830f-cc728e2ad066))
						- ((63209272-1088-4824-a762-4ac7ded04b0a)) : ((663b63f5-e0ab-40c3-af11-e6d5bd63fe4a))
						- [[Logseq]] : ((634bc0dc-29b0-4264-889d-0d455029e8d2)) - too limited
						- [Vim As Your Editor - ThePrimeagen](https://youtube.com/playlist?list=PLm323Lc7iSW_wuxqmKx_xxNtJC_hJbQ7R)
						- [VimTutor](https://vimschool.netlify.app/introduction/vimtutor/)
						- $10 [Vim Ninja](https://www.vimninja.com/)
						- [/r/vim wiki](https://www.reddit.com/r/vim/wiki/index)
						- [Vim Snake](https://vimsnake.com/)
						  collapsed:: true
							- [GitHub - patmood/vim_snake: Vim Snake Game powered by web assembly](https://github.com/patmood/vim_snake)
							-
						- [Vim Racer - An Online Game for VIM Navigation](https://vim-racer.com/)
							- [Vim Racer | Hacker News](https://news.ycombinator.com/item?id=41347051)
							- Leaderboards show the most optimal route
						- [GitHub - micahkepe/vimtutor-sequel: Vimtutor Sequel - Advanced Vim Tutor Lessons ⌨️](https://github.com/micahkepe/vimtutor-sequel)
						- [GitHub - igrigorik/vimgolf: Real Vim ninjas count every keystroke - do you?](https://github.com/igrigorik/vimgolf)
						- [GitHub - m4xshen/hardtime.nvim: Break bad habits, master Vim motions](https://github.com/m4xshen/hardtime.nvim)
							- [Show HN: Hardtime.nvim – break bad habits and master Vim motions | Hacker News](https://news.ycombinator.com/item?id=44020734)
							-
					- Completed learning resources (references)
						- [VIM Adventures](https://vim-adventures.com/)
						  id:: 663bb0c9-5667-459c-aa3d-7345064b4081
						  collapsed:: true
						  Learn VIM while playing a game
							- Meta
								- $25 6-month access for Game-only (13 levels)
								- $30 6-month access for Game + Challenges (CTF challenges to train skills, and a level teaching macros)
							- Walkthroughs
								- [Vim Adventures - Levels 4 - 12 (Speed Run Practice) - YouTube](https://youtu.be/Ql4rYPJysoE)
									- [Level 14](https://youtu.be/BIuJxt6INAk)
								- [Newest 'vim-adventures' Questions - Arqade](https://gaming.stackexchange.com/questions/tagged/vim-adventures)
								- [GitHub - pepers/vim-adventures: solutions to puzzles in Vim Adventures](https://github.com/pepers/vim-adventures)
							- Order of keys learnt
								- `h j k l`
								  logseq.order-list-type:: number
									- ((99ab4d04-98f2-4911-ad14-169c63c9ea60))
									  logseq.order-list-type:: number
									- ((6640d1f9-d4c2-4dc9-ada8-65020c9c877d))
									  logseq.order-list-type:: number
									- ((6640d213-5e89-4e80-af1a-4461ed7b072d))
									  logseq.order-list-type:: number
									- ((6640d21a-025a-46ff-bb35-f967926c4b17))
									  logseq.order-list-type:: number
								- `w e b`
								  logseq.order-list-type:: number
									- ((6640cfc3-ea48-4d9a-9162-b20f7126c21c))
									  logseq.order-list-type:: number
									- ((f7bbbe79-3274-4c9a-b28f-7e5696f9caf5))
									  logseq.order-list-type:: number
									- ((fee495bc-993e-45d3-bc93-910e40f9ded7))
									  logseq.order-list-type:: number
								- `x B`
								  logseq.order-list-type:: number
									- ((6640d610-296b-4ef7-80a7-8a2c8491e8e9))
									  logseq.order-list-type:: number
									- ((6640ea7e-d024-433a-ac79-ddc6ed577286))
									  logseq.order-list-type:: number
									- ((6640d550-d418-4f60-9789-53c93642ce04))
									  logseq.order-list-type:: number
								- `r W E`
								  logseq.order-list-type:: number
									- ((6640e3fa-5b9c-4768-aff0-f2c9238ad97f))
									  logseq.order-list-type:: number
									- ((6640e30f-f1aa-44ff-8753-5812c410d8aa))
									  logseq.order-list-type:: number
									- ((6640e341-f867-4bb2-92a9-4c3bcdc7ecac))
									  logseq.order-list-type:: number
								- `d`
								  logseq.order-list-type:: number
									- ((6640e592-227d-4237-9d56-ca4fd77a191c))
									  logseq.order-list-type:: number
									- ((664121a0-efb7-4708-bd5f-ae4e384ceaf0))
									  logseq.order-list-type:: number
									- ((66477e70-3caa-4a29-85a8-a16c0b9112d6))
									  logseq.order-list-type:: number
								- `~ $ 0 ^`
								  logseq.order-list-type:: number
									- ((6640eab7-c8f2-46eb-9e87-01a7d193a21a))
									  logseq.order-list-type:: number
									- ((6640ed39-e97a-4136-b1b2-b775181a015a))
									  logseq.order-list-type:: number
									- ((66411fc7-7131-42c2-a490-88b2d7653e53))
									  logseq.order-list-type:: number
									- ((66412091-d0ef-43fe-a1b5-0271ae1961b7))
									  logseq.order-list-type:: number
								- `% f t , ; g z`
								  logseq.order-list-type:: number
									- ((66412ed6-68a2-43e1-a6f6-2889f5ccfea9))
									  logseq.order-list-type:: number
									- ((664124da-375b-45e7-a03e-ddc6eabfbae5))
									  logseq.order-list-type:: number
									- ((66412519-4030-4c04-ba78-5897e208fda0))
									  logseq.order-list-type:: number
									- ((664128ed-cf79-4553-9103-8e2ed4440ce3))
									  logseq.order-list-type:: number
									- ((664128f6-9b22-4aa8-90a7-aa81fa8a89ba))
									  logseq.order-list-type:: number
									- ((66412873-d125-4152-a3fa-612ab7993c1c))
									  logseq.order-list-type:: number
									- ((66412b24-9f42-42cd-91ee-dc5ae6c3476a))
									  logseq.order-list-type:: number
									- ((66413a7a-4bff-4e26-acc6-b89d61aebe0d))
									  logseq.order-list-type:: number
									- ((66413ab6-1419-4402-8ba3-17d067ba258a))
									  logseq.order-list-type:: number
									- ((66412be9-2ed3-475d-9936-5e4357f23c99))
									  logseq.order-list-type:: number
								- `* # n`
								  logseq.order-list-type:: number
									- ((66413cd9-0607-48fa-8cba-38d0dd378562))
									  logseq.order-list-type:: number
									- ((66413e1f-5c1b-4be1-8b37-50d2c8fb3683))
									  logseq.order-list-type:: number
									- ((664141c4-28b1-474d-9962-cf595f20eccc))
									  logseq.order-list-type:: number
										- ((6641b5c7-8609-4438-bb7d-5a12fb28c6c7))
									- ((66414201-db99-4a0c-9bd0-96ac396a5b4b))
									  logseq.order-list-type:: number
								- `Digits`
								  logseq.order-list-type:: number
									- ((6641b69c-4ca0-45de-a249-f2b2c0d1cf46))
									  logseq.order-list-type:: number
								- `p y " :reg`
								  logseq.order-list-type:: number
									- ((66453ba2-cd52-4896-ab3c-d20b76eae4ed))
									  logseq.order-list-type:: number
									- ((66453c62-9bd0-4d97-b561-230d432bc80d))
									  logseq.order-list-type:: number
									- ((66466200-5a6d-45f3-9a11-1d07b8732eb7))
									  logseq.order-list-type:: number
									- ((664665b7-1fb6-4bce-a378-459f0e201fdf))
									  logseq.order-list-type:: number
									- ((66466a2f-df30-4522-a762-af9012f38835))
									  logseq.order-list-type:: number
								- `c s i a o :b`
								  logseq.order-list-type:: number
									- ((664670a5-8212-4ba0-befc-e288d2158119))
									  logseq.order-list-type:: number
									- ((6646748e-e0dc-4c92-8f00-3228dcc82022))
									  logseq.order-list-type:: number
									- ((66467501-d6f7-4e62-a6de-fbb4e4b9cbd0))
									  logseq.order-list-type:: number
									- ((664674cb-f888-47ab-835f-415bb40055a2))
									  logseq.order-list-type:: number
									- ((6646fe73-b079-489a-84e1-5d484de5e874))
									  logseq.order-list-type:: number
									- ((66475aec-3e9a-4115-a121-4d2c4293afb6))
									  logseq.order-list-type:: number
									- ((66470115-7bb6-4168-aa27-6f37afcafd9e))
									  logseq.order-list-type:: number
									- ((6647050f-9384-4c47-a66c-2f0c58fa9b65))
									  logseq.order-list-type:: number
									- ((6647052c-d545-4009-82c2-eaf3e2600e6b))
									  logseq.order-list-type:: number
									- ((66475f9a-66e8-4818-8e90-94895ab98c72))
									  logseq.order-list-type:: number
									- ((66475ff5-d4c2-4d86-b62b-0913ba9db13e))
									  logseq.order-list-type:: number
									- ((6647633d-b4d9-4796-a466-41bb2ae5dd02))
									  logseq.order-list-type:: number
									- ((6647638c-cb9e-49ee-b8f3-0a2d02614a4a))
									  logseq.order-list-type:: number
								- `( ) { } [ ] ia .`
								  logseq.order-list-type:: number
									- ((66477aa5-cbd8-469a-895a-6b7af309de8a))
									  logseq.order-list-type:: number
									- ((66477a74-49a4-461f-8233-3a6f391793be))
									  logseq.order-list-type:: number
									- ((66478362-411f-4bff-8cc0-2ac8f20265da))
									  logseq.order-list-type:: number
									- ((66478369-2d24-4466-a693-8896e73e0d67))
									  logseq.order-list-type:: number
									- ((66477d84-ca40-4595-9f75-35f50878a51b))
									  logseq.order-list-type:: number
									- ((66477d96-e902-4355-b789-08ac05d7c8ae))
									  logseq.order-list-type:: number
									- ((6647904f-7373-4d00-908c-29ba3366ad6c))
									  logseq.order-list-type:: number
									- ((6647b388-3053-4cc6-93de-9bb33e663329))
									  logseq.order-list-type:: number
								- `-- unknown`
								  logseq.order-list-type:: number
								- `H M L | / ? ' ` ((6640dce9-16b3-4438-bd51-c2fc7e9f8118)) `m u`
								  logseq.order-list-type:: number
									- ((664c95f2-5bf3-411d-90be-efe27e7e59d3))
									  logseq.order-list-type:: number
									- ((664c961c-d847-4d71-919f-cb2f49aab724))
									  logseq.order-list-type:: number
									- ((664c9a18-c4ce-4b6c-af6d-5fcbb73174be))
									  logseq.order-list-type:: number
									- ((664c9be1-95d1-4330-92a4-e7d36dc0cb9b))
									  logseq.order-list-type:: number
									- ((664c9b79-7681-423d-bc77-4858fb5fee7d))
									  logseq.order-list-type:: number
									- ((664c9a8a-dc2e-4c7c-ab29-ffc2f744df46))
									  logseq.order-list-type:: number
									- ((664c9fa1-73f4-4b2f-b6bb-4c9261c439a7))
									  logseq.order-list-type:: number
									- ((664c9fed-8399-48ec-bfb6-35690ef4a2c0))
									  logseq.order-list-type:: number
									- ((6640dce9-16b3-4438-bd51-c2fc7e9f8118))
									  logseq.order-list-type:: number
									- ((664c9ecf-1a72-4093-b5f5-445325a5d779))
									  logseq.order-list-type:: number
									- ((664ca910-085e-4571-902a-f8492265664d))
									  logseq.order-list-type:: number
									- ((664ca859-e1e6-41c3-86e8-fe072590f43e))
									  logseq.order-list-type:: number
									- ((664caa6e-18aa-4c94-907b-78ecc27cfeb3))
									  logseq.order-list-type:: number
									- ((664cc8fb-1024-4338-a05b-4b9fc064ce89))
									  logseq.order-list-type:: number
									- ((664cc9bf-f15c-4530-a9e5-7fab2ab8c5aa))
									  logseq.order-list-type:: number
							- Priority to master
								- ((6641b69c-4ca0-45de-a249-f2b2c0d1cf46))
								- ((6640e592-227d-4237-9d56-ca4fd77a191c))
				- # Ecosystem
					- ## Plugins
					  id:: 66437e84-b790-46c3-8d6a-d78ec581be14
						- [EasyMotion](https://github.com/easymotion/vim-easymotion)
						  collapsed:: true
							- [Usage example](https://github.com/easymotion/vim-easymotion?tab=readme-ov-file#usage-example-for-the-base-features)
							- It basically highlights the first of a word and replaces it with a different letter, repeated for many words, whilst fading all other characters on screen. You can then just type in 1-2 characters to easily jump to that position
							- GIF
							  collapsed:: true
								- https://camo.githubusercontent.com/011737d35fce5ac3066a77758b176947865432e8288566635456bc184887bfa0/68747470733a2f2f662e636c6f75642e6769746875622e636f6d2f6173736574732f333739373036322f323033393335392f61386539333864362d383939662d313165332d383738392d3630303235656138333635362e676966
							- [EasyMotion - Vim motions on speed! : vim online](https://www.vim.org/scripts/script.php?script_id=3526)
						- [vim-sneak](https://github.com/justinmk/vim-sneak)
						- [Leap](https://github.com/ggandor/leap.nvim)
				- # Forks
					- [Neovim](https://neovim.io/)
					  id:: 663341b5-ddd5-4338-a332-195f59f96fd3
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Pros
								- Scripting can be accomplished in Lua in addition to Vim script
								- Modern and extensible compared to Vim
								- Language Server Provider (LSP) support
							- Cons
								-
							- Unclear
							- Upstream/Downstream Pros/Cons
								- ((634d22db-89bb-432b-8dcf-776e2bd185ba))
								- ((9c059bb1-0976-45e5-b420-676c8acdad61))
							- Comparisons
								- ((17d08eab-9922-43c4-ab70-efcc65f70a87))
								  collapsed:: true
									- {{embed ((17d08eab-9922-43c4-ab70-efcc65f70a87))}}
						- # Documentation
							- ## Installation
							  id:: 67a8e14d-078e-481d-8a76-18381f3443c6
								- `brew install neovim`
									- `which nvim` = `/home/linuxbrew/.linuxbrew/bin/nvim`
									- [[2025-02-13 Thursday]] This finally worked with VSCode NeoVim
								- `sudo apt install neovim`
									- [[2025-02-12 Wednesday]] No new version in 1.3-0.7 years
								- [AppImage](https://github.com/neovim/neovim/blob/master/INSTALL.md#appimage-universal-linux-package)
									- To expose nvim globally:
										- `mkdir -p /opt/nvim`
										- `mv nvim-linux-x86_64.appimage /opt/nvim/nvim`
									- And the following line to your shell config (~/.bashrc, ~/.zshrc, ...):
										- `export PATH="$PATH:/opt/nvim/"`
									- `which nvim` = `/opt/nvim//nvim`
								- [Flatpak](https://github.com/neovim/neovim/blob/master/INSTALL.md#flatpak)
								  id:: 664cf776-5585-4bf6-80da-61172b4cb142
								  collapsed:: true
									- You can find Neovim on [Flathub](https://flathub.org/apps/details/io.neovim.nvim). Providing you have Flatpak [set up](https://flatpak.org/setup/):
									- ```
									  flatpak install flathub io.neovim.nvim
									  flatpak run io.neovim.nvim
									  ```
									- You can add `/var/lib/flatpak/exports/bin` (or `~/.local/share/flatpak/exports/bin` if you used `--user`) to the `$PATH`, which allows it to run with `io.neovim.nvim`.
										- ((64634a46-c61c-4520-bd6f-d38493de8851))
										- `export PATH=$PATH:/var/lib/flatpak/exports/bin`
									- Note that Flatpak'ed Neovim will look for `init.vim` in `~/.var/app/io.neovim.nvim/config/nvim` instead of `~/.config/nvim`.
							- ## How to use
								- In a terminal open with `nvim`
								- ### Customisation
									- is stored in either `~/.config/nvim/init.vim` or `~/.config/nvim/init.lua`
									- Example config file
										- ```lua
										  -- tabs vs spaces
										  vim.opt.tabstop = 2  -- 2 spaces
										  vim.opt.expandtab = true  -- 
										  ```
									- Modular config (i.e. can split into multiple files and directories)
									  collapsed:: true
									  Recommended to have a file for each plugin
										- ![image.png](../assets/image_1729273319216_0.png)
									- Example config
									  collapsed:: true
										- ![image.png](../assets/image_1729273452395_0.png)
							- [Neovim in 100 Seconds - YouTube](https://youtu.be/c4OyfL5o7DU)
						- # Ecosystem
							- [GUIs](https://github.com/neovim/neovim/wiki/Related-projects#gui)
								- [GitHub - glacambre/firenvim: Embed Neovim in Chrome, Firefox & others.](https://github.com/glacambre/firenvim)
								- [GitHub - akiyosi/goneovim: A GUI frontend for neovim.](https://github.com/akiyosi/goneovim) written in Go
								- [Neovide](https://neovide.dev/)
								  id:: 67aa7d01-bb28-420f-83a6-4d18c00d57d0
								  collapsed:: true
								  Rust-based GUI
									- [GitHub - neovide/neovide: No Nonsense Neovim Client in Rust](https://github.com/neovide/neovide)
									- Pros/Cons
										- Pros
											-
										- Cons
											- Lacks
												- [Multiple instances / windows](https://github.com/neovide/neovide/issues/1332)
													- [WIP PR](https://github.com/neovide/neovide/pull/2872)
												- [Tmux-like sessions for multiple servers with one ui · Issue #2174 · neovide/neovide · GitHub](https://github.com/neovide/neovide/issues/2174)
										- Unclear
										- Comparisons
							- ## Distributions
								- LunarVim
									- [LunarVim - Installing Rolling Release, Walkthrough, Sample Configuration (IDE for Neovim) - YouTube](https://youtu.be/NlRxRtGpHHk?list=PLhoH5vyxr6QoYP4bKw0krF4aEn_3_pfWA)
									-
								- NvChad
								- AstroVim
								- LazyVim
								- [You Should Use A Neovim Distro If You Are New - YouTube](https://youtu.be/6qSzFWRz6Ck)
							- ## Plugins
							  collapsed:: true
								- Vim : ((66437e84-b790-46c3-8d6a-d78ec581be14))
									- {{embed ((66437e84-b790-46c3-8d6a-d78ec581be14))}}
								- [Moving Even Faster with Vim Sneak and EasyMotion | Barbarian Meets Coding](https://www.barbarianmeetscoding.com/boost-your-coding-fu-with-vscode-and-vim/moving-even-faster-with-vim-sneak-and-easymotion/)
								- https://github.com/ThePrimeagen/harpoon
								- Motion plugins
								  collapsed:: true
									- [Quick Scope v Hop v Lightspeed](https://youtu.be/HNzrQnqJ9N8)
										- Quick Scope: github.com/unblevable/quick-scope
										- Hop: github.com/phaazon/hop.nvim
										- Lightspeed: github.com/ggandor/lightspeed.nvim
								- I use a lot of them, many specific to my work, but here are some of the ones that I think will most improve the quality of life for most developers.
								  collapsed:: true
									- - For a plug-in manager I user packer
									- - For file/text search I recommend telescope (https://github.com/nvim-telescope/telescope.nvim)
									- - Copilot (https://github.com/github/copilot.vim)
									- - Nerd tree for file browsing (https://github.com/preservim/nerdtree)
									- - commentary for commenting (https://github.com/tpope/vim-commentary)
									- - ALE for linting (https://github.com/dense-analysis/ale)
									- - Mason for installing LSP servers (https://github.com/williamboman/mason.nvim)
									- [GitHub - github/copilot.vim: Neovim plugin for GitHub Copilot](https://github.com/github/copilot.vim)
								- The only **required** plugin dependency is [plenary.nvim](https://github.com/nvim-lua/plenary.nvim), but there are a number of optional dependencies that enhance the obsidian.nvim experience.
								  collapsed:: true
									- **Completion:**
										- **\[recommended\]** [hrsh7th/nvim-cmp](https://github.com/hrsh7th/nvim-cmp): for completion of note references.
									- **Pickers:**
										- **\[recommended\]** [nvim-telescope/telescope.nvim](https://github.com/nvim-telescope/telescope.nvim): for search and quick-switch functionality.
										- [Mini.Pick](https://github.com/echasnovski/mini.pick) from the mini.nvim library: an alternative to telescope for search and quick-switch functionality.
										- [ibhagwan/fzf-lua](https://github.com/ibhagwan/fzf-lua): another alternative to telescope for search and quick-switch functionality.
									- **Syntax highlighting:**
										- **\[recommended\]** [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter): for base markdown syntax highlighting. See [syntax highlighting](https://github.com/epwalsh/obsidian.nvim#syntax-highlighting) for more details.
										- [preservim/vim-markdown](https://github.com/preservim/vim-markdown): an alternative to nvim-treesitter for syntax highlighting (see [syntax highlighting](https://github.com/epwalsh/obsidian.nvim#syntax-highlighting) for more details), plus other cool features.
									- **Miscellaneous:**
									- 🆕 [pomo.nvim](https://github.com/epwalsh/pomo.nvim): for running lightweight [pomodoro](https://en.wikipedia.org/wiki/Pomodoro_Technique) timers.
								- [folke/todo-comments.nvim - Neovim plugin | Developers using todo-comments.nvim | Alternatives
								  		to todo-comments.nvim](https://dotfyle.com/plugins/folke/todo-comments.nvim)
								- [GitHub - hrsh7th/nvim-cmp: A completion plugin for neovim coded in Lua.](https://github.com/hrsh7th/nvim-cmp)
								- ### Quality of Life
									- [GitHub - nvim-tree/nvim-tree.lua: A file explorer tree for neovim written in lua](https://github.com/nvim-tree/nvim-tree.lua)
									  Basically VSCode's File Explorer pane
									- [GitHub - nvim-treesitter/nvim-treesitter: Nvim Treesitter configurations and abstraction layer](https://github.com/nvim-treesitter/nvim-treesitter)
									  e.g. for syntax highlighting
									- [GitHub - windwp/nvim-autopairs: autopairs for neovim written in lua](https://github.com/windwp/nvim-autopairs)
									- [GitHub - rcarriga/nvim-notify: A fancy, configurable, notification manager for NeoVim](https://github.com/rcarriga/nvim-notify)
									- [GitHub - nvim-telescope/telescope.nvim: Find, Filter, Preview, Pick. All lua, all the time.](https://github.com/nvim-telescope/telescope.nvim)
									  i.e. fuzzy search
									-
								- ### UI
									- [GitHub - shellRaining/hlchunk.nvim: This is the lua implementation of nvim-hlchunk, you can use this neovim plugin to highlight your indent line and the current chunk (context) your cursor stayed](https://github.com/shellRaining/hlchunk.nvim)
									- [GitHub - lukas-reineke/indent-blankline.nvim: Indent guides  for Neovim](https://github.com/lukas-reineke/indent-blankline.nvim)
									- [visual-whitespace.nvim](https://github.com/mcauley-penney/visual-whitespace.nvim): blockwise highlighting
										- https://www.reddit.com/r/neovim/comments/1g4jdb4/visualwhitespacenvim_blockwise_highlighting/
									- [GitHub - folke/zen-mode.nvim: 🧘  Distraction-free coding for Neovim](https://github.com/folke/zen-mode.nvim)
								- ### Plugin Managers
									- packer.nvim
									- [lazy.nvim](https://dotfyle.com/plugins/folke/lazy.nvim)
									- [mason.nvim](https://github.com/williamboman/mason.nvim)
								- ### Themes
									- navarasu/onedark.nvim
								- ### Icons
									- nvim-tree/nvim-web-devicons
								- ### Unsorted
									- [OXY2DEV/markview.nvim](https://github.com/OXY2DEV/markview.nvim)
									  id:: 671296f1-27e4-4fed-9ed7-f1fca2452e59
									  Highly customisable markdown(latex & inline html) previewer for Neovim]
										- Screenshot
											- ![image.png](../assets/image_1729252976780_0.png)
										- GIF
										  collapsed:: true
											- https://snoo.habedieeh.re/img/n3iwnhj0s1td1.gif
										- Also has hybrid mode rather than split view
										- [Horizontal rules](https://github.com/OXY2DEV/markview.nvim/wiki/Horizontal-rules) i.e. `---`
									- [GitHub - MeanderingProgrammer/render-markdown.nvim: Plugin to improve viewing Markdown files in Neovim](https://github.com/MeanderingProgrammer/render-markdown.nvim)
									- [MeanderingProgrammer/render-markdown.nvim](https://github.com/MeanderingProgrammer/render-markdown.nvim)
									  Plugin to improve viewing Markdown files in Neovim
										-
								- [Learning Resources]
									- [GitHub - rockerBOO/awesome-neovim: Collections of awesome neovim plugins.](https://github.com/rockerBOO/awesome-neovim)
									- https://dotfyle.com/neovim/plugins/trending
									- [GitHub - niuiic/awesome-neovim-plugins: Awesome neovim plugins I have written.](https://github.com/niuiic/awesome-neovim-plugins)
									-
					- [SpaceVim](https://spacevim.org/)
					  collapsed:: true
						- [GitHub - SpaceVim/SpaceVim: A community-driven modular vim/neovim distribution - The ultimate vimrc](https://github.com/SpaceVim/SpaceVim)
					- Related: ((664373fe-15d7-47a1-8472-08013e1929de))
				- [Learning Resources]
				  collapsed:: true
					- ((59f7513e-af19-46a4-a49c-0ffa64ace1ba))
						- {{embed ((59f7513e-af19-46a4-a49c-0ffa64ace1ba))}}
					- Cheat sheet
					  collapsed:: true
						- [Graphical vi-vim Cheat Sheet and Tutorial](http://www.viemu.com/a_vi_vim_graphical_cheat_sheet_tutorial.html)
						  collapsed:: true
							- ![image.png](../assets/image_1715982577183_0.png)
							- 7 lessons
								- 1
								  collapsed:: true
									- ![image.png](../assets/image_1715982661496_0.png)
								- 2
								  collapsed:: true
									- ![image.png](../assets/image_1715982767058_0.png)
								- 3
								  collapsed:: true
									- ![image.png](../assets/image_1715982791796_0.png)
								- 4
								  collapsed:: true
									- ![image.png](../assets/image_1715982805056_0.png)
								- 5
								  collapsed:: true
									- ![image.png](../assets/image_1715982813049_0.png)
								- 6
								  collapsed:: true
									- ![image.png](../assets/image_1715982822362_0.png)
								- 7
								  collapsed:: true
									- ![image.png](../assets/image_1715982707791_0.png)
						- ![image.png](../assets/image_1665239256741_0.png)
					- [Vim in 100 Seconds - YouTube](https://youtu.be/-txKSRn0qeA)
					  Includes 10m of VSCode extension for Vim
					- GIF
					  collapsed:: true
						- https://i.imgur.com/HEOuCxg.mp4
					- Infographic cheatsheet
					  collapsed:: true
						-
						- ![VimDeskPad.png](../assets/VimDeskPad_1715586898120_0.png){:height 285, :width 830}
						- 2
						  collapsed:: true
							- ![image.png](../assets/image_1716309902687_0.png)
					- ![summary.pdf](../assets/summary_1715587067740_0.pdf)
					- Macros
						- [Reddit - Dive into anything](https://www.reddit.com/r/vim/comments/1bds8io/why_vim_is_the_best/)
					- [Moving fast with the core Vim motions](https://www.barbarianmeetscoding.com/boost-your-coding-fu-with-vscode-and-vim/moving-blazingly-fast-with-the-core-vim-motions/)
						- [Moving fast with the core Vim motions | Hacker News](https://news.ycombinator.com/item?id=36312027)
				- Related:
					- ((634bf00a-932c-4a43-8a7c-c822f175ffed))
					- ((6641f3b8-e338-479a-b727-06f7a51a65fc))
			- Folding Editors
			  collapsed:: true
				- Differences
					- Pros: Lower privacy risk compared to hosted online with my own encryption.
					- Cons: Not as convenient - not online so can't use mobile, can't zoom, can't drag and drop nodes, have to mount TrueCrypt container to use, can't URL interlink.
					- Conclusion - tradeoff the usability for additional privacy only with highly sensitive docs e.g. OPSEC
				- Notepad++ (language = python)
				- http://tibleiz.net/code-browser/download.html
				- https://en.wikipedia.org/wiki/Folding_editor
				- https://www.google.com/search?q=text+editor+with+collapsible&oq=text+editor+with+collapsible&gs_l=serp.3..0i22i30.50708.54843.0.54991.28.16.0.0.0.0.385.1169.2-3j1.4.0....0...1c.1.64.serp..24.4.1168.jArPQTGRUBI
			- TaskPaper
			  collapsed:: true
			  Looks almost exactly like WorkFlowy. Mac-only
				- Pros
					- Fold, focus, and filter to make big list small
					- Drag and drop to organize your list
					- Plain text files; edit anywhere
					- Type and your lists are auto formatted
					- Projects:, - tasks, notes, and @tags
				- Cons
					- Mac-only, though can be named as a .txt file and edited via text editor on Android
					- No interlinking or zoom?
				- https://www.taskpaper.com/
				- Note: downloaded free version to L
				- Compatible apps on other platforms
				  http://support.hogbaysoftware.com/t/how-do-i-taskpaper-files-on-ios-windows-or-other-platforms/1114/2
					- TaskPaper for Windows
					- Lucid Pad for Android
					- Though they lack the folding + tags + interlinking?
			- taskpaper+
			  collapsed:: true
				- http://taskpaperplus.eu5.org/
				- local web app
			- [Simpletask](https://github.com/mpcjanssen/simpletask-android) (forked from todo.txt)
			- Treeline
			  collapsed:: true
				- Cons
					- you can't edit in note pane, have to click on editor tab and enter or correct information in small database entry window, keyhole-like view.
				- Outliner/database combo
				  https://treeline.bellz.org/scrnsht.html
				- Templates
					- Single HTML Document is the most flexible one (gives Note like section?)
		- Open-source Self-Hosted Web App
			- Top Alternatives for ((6313462d-10af-4744-92d2-041a06816d23))
				- [[Logseq]]
				  id:: 62d1b97d-2b7d-42ba-ad6d-dbb8e5b772a4
				- Athens Research
				  collapsed:: true
					- Top Alternatives for WorkFlowy
					  collapsed:: true
						- [https://github.com/athensresearch/athens](https://github.com/athensresearch/athens)
						- Demo
						  [https://athensresearch.github.io/athens](https://athensresearch.github.io/athens)
						- Changelog (last read: [2.0.0-beta.35](https://github.com/athensresearch/athens/compare/v2.0.0-beta.34...v2.0.0-beta.35) (2022-05-18) )
						  [https://github.com/athensresearch/athens/blob/master/CHANGELOG.md](https://github.com/athensresearch/athens/blob/master/CHANGELOG.md)
							- Also see GitHub non-main branches
							- Changelog does not have user-friendly descriptions
						- Feature requests
							- Ordered list
							  [https://github.com/athensresearch/athens/discussions/categories/feature-requests?discussions_q=category%3A%22Feature+Requests%22+sort%3Atop](https://github.com/athensresearch/athens/discussions/categories/feature-requests?discussions_q=category%3A%22Feature+Requests%22+sort%3Atop)
						- Vision
						  [https://github.com/athensresearch/athens/blob/master/VISION.md](https://github.com/athensresearch/athens/blob/master/VISION.md)
						- Docs
						  [https://athensresearch.github.io/docs/](https://athensresearch.github.io/docs/)
						- Open Collective
						  [https://opencollective.com/athens](https://opencollective.com/athens)
					- _Pros/Cons_
					  collapsed:: true
						- Pros
							- Many WorkFlowy features - dark theme, bookmarks, zooming, collapsing
							- Roam Research features - backlink references, graphing
							- Desktop app. Local-first
							  [https://github.com/athensresearch/athens/releases](https://github.com/athensresearch/athens/releases)
							- Self-hostable with real-time collab
							  [https://github.com/athensresearch/athens-backend/](https://github.com/athensresearch/athens-backend/)
						- Cons
							- Q3 2021 - pivoted to focus on collaboration foremost
							  [https://athensresearch.ghost.io/season-2/](https://athensresearch.ghost.io/season-2/)
							- _Lacks_
								- Export
								  [https://github.com/athensresearch/athens/discussions/676](https://github.com/athensresearch/athens/discussions/676)
									- [https://github.com/athensresearch/athens/issues/839](https://github.com/athensresearch/athens/issues/839)
								- Syntax highlighting
								  [https://github.com/athensresearch/athens/discussions/758](https://github.com/athensresearch/athens/discussions/758)
								- E2EE sync for hosted/self-hosting
								  [https://github.com/athensresearch/athens/discussions/868](https://github.com/athensresearch/athens/discussions/868)
								- Interoperability with popular tools like Roam
								  [https://github.com/athensresearch/athens/discussions/761](https://github.com/athensresearch/athens/discussions/761)
								- _Planned_
									- Real-Time Collaboration (WIP)
									- Self-hosting
									- Mobile app
									- API
									- Browser extension
									- plugin system, publishing
					- Documentation
					  collapsed:: true
						- [https://github.com/athensresearch/handbook/](https://github.com/athensresearch/handbook/) / <a href="https://athensresearch.gitbook.io/handbook">https://athensresearch.gitbook.io/handbook</a>
						- Features
							- Image embeds
								- Drag-and-drop or copy and paste to add. It'll be added to the database folder
							- Sidebar (basically an extra tab that can be side-by-side or collapsed)
							- /slash commands
							- [[]] inline linking
						- Files stored
						  /home/boss/Documents/athens/index.transit
						- App stored
						  /home/boss/Desktop/veracrypt1/Utilities/Athens-Research
					- Last downloaded: 1.0.0-beta.60 Mon, Mar 22, 2021
					- 2 Backlinks
					  collapsed:: true
						- _See_ [Athens Research](https://workflowy.com/#/eb20c0852942)
						- See [Athens Research](https://workflowy.com/#/eb20c0852942)
				- See Org-mode [Web Apps](https://workflowy.com/#/01b0753e4925) (at least 3 viable options)
				  #Outliners
				- See [Org-roam](https://workflowy.com/#/5351330476f0)
				- _Moderate_
					- See [Orgzly](https://workflowy.com/#/f98c5435aacd)
				- _Abandoned_
					- See [TiddlyRoam ](https://workflowy.com/#/d8aaf19ad03a)
					- [Streams plugin](https://workflowy.com/#/52a7b9bc2605) for TiddlyWiki
					- Calculist
					  collapsed:: true
						- Links
						  collapsed:: true
							- http://calculist.io/
							- [cloned] https://github.com/calculist
						- Manual
						  collapsed:: true
							- Computation
								- As for the issue you are seeing with @item, I should clarify.
								  https://github.com/calculist/calculist/issues/17#issuecomment-320823021
									- example function [=>] @item(guid)
									- This defines a function, but @item is already defined. I think what you are trying to do is use the @item function in a computed expression. To do that, you just need to change [=>] to [=]. So it would look like this.
									- example [=] @item(guid)
									- If you really were trying to define a function, then you would need to declare an input variable. So it would look something like this.
									- example function [=>] guid | @item(guid)
									- using function [=] example_function("a6b149b1-c41d-4437-8ae1-80f5d4ad61af")
									- But then example function is just calling @item, so it's not adding any new behavior. It's the same as
									- using function [=] @item("a6b149b1-c41d-4437-8ae1-80f5d4ad61af")
									- I hope that clears things up.
							- Referencing other items
								- Airtable-like linking: A way to reference $value -  Showing the $value of itemA in itemB
									- test2 [=] @item("93103f18-087a-4d93-a582-5cac175b8b6c")
						- Pros/cons vs offline KDB
						  collapsed:: true
							- Pros
								- Online access
								- Allows tables/spreadsheet
							- Cons
								- Mobile view is poor
						- Pros
						  collapsed:: true
							- Online access
							- Zooming/focusing/hoisting
							- Lots of extra features
							- Functions which have weak/no GUI currently but are powerful
								- Command mode including import, export (very org-mode like)
								  https://github.com/calculist/calculist/wiki/Command-Mode
								- Computation (Excel spreadsheet-like; simplified Javascript)
								  https://github.com/calculist/calculist/wiki/Computation
								- Computation for navigation
								  https://github.com/calculist/calculist/issues/17#issuecomment-277546419
								- _More_
								  collapsed:: true
									- ((6458ee2f-9855-4d38-89e5-726aa7bdd3ee)) (typesetting/markup language e.g. for books, scientific articles etc)
									  id:: 635eb280-ab1e-42b6-b5c4-49eef87e8ad3
									  [LaTeX Expressions · calculist/calculist Wiki · GitHub](https://github.com/calculist/calculist/wiki/LaTeX-Expressions)
										- [Introduction to LaTeX](https://www.latex-project.org/about/)
										- Sort of like a syntax or markup
										- LaTeX Features
											- Typesetting journal articles, technical reports, books, and slide presentations.
											- Control over large documents containing sectioning, cross-references, tables and figures.
											- Typesetting of complex mathematical formulas.
											- Advanced typesetting of mathematics with AMS-LaTeX.
											- Automatic generation of bibliographies and indexes.
											- Multi-lingual typesetting.
											- Inclusion of artwork, and process or spot colour.
											- Using PostScript or Metafont fonts.
									- Math functions
									  https://github.com/calculist/calculist/wiki/Math-Functions
							- Data visualisation
							  https://i.imgur.com/NrpPCu4.png
							- Desktop app and web app
						- Cons
						  collapsed:: true
							- Lacks
								- By priority to discuss
								  collapsed:: true
									- Item Attributes
									- Spreadsheet
									- Inline comments (Quip-style)
									- Lazy loading
								- By personal highest priority (for migration/usage)
								  collapsed:: true
									- 'Notes' area
									  intralink2:: https://workflowy.com/#/898209508fc4
									- Tags + search
									- Breadcrumbs
									  intralink2:: https://workflowy.com/#/df132df20344
								- Roadmap
								  collapsed:: true
								  https://www.patreon.com/calculist/posts
									- List sharing and collaborating
									- Data visualization (charts and graphs)
									- Public API and integrations
									- Version control and automatic backups
									- Sync between desktop and web
									- Better search functionality
									- Make self-hosting the web app easier
								- See 'Dream app'
								  intralink2:: https://workflowy.com/#/6f314962833c
								- By Difficulty
									- _Hard_
									  collapsed:: true
										- Spreadsheet mode
										  collapsed:: true
											- Post
											  https://github.com/calculist/calculist/issues/32
												- Spreadsheets in Calculist implemented also can play well with other Calculist features, for example:
												- Command mode on one of `Spreadsheet Columns` values e.g. `sort columns A-Z`
												- Computation within each cell/item
												- Accessors to reference columns, rows or cells in a simple format like Excel's e.g. `Row 1` or `Column A` or `Item A3:A7`
												- I think this is a decent draft of how to make a spreadsheet work within Calculist and fits in line with it's overall approach (although challenging to implement), let me know what you think.
											- Org-mode as a spreadsheet
												- https://youtu.be/fgizHHd7nOo?t=6m59s
												- https://www.youtube.com/watch?v=I762W3lEUEk
												- http://orgmode.org/worg/org-tutorials/org-spreadsheet-intro.html
												- http://orgmode.org/manual/The-spreadsheet.html
										- API
										  Planned https://www.patreon.com/posts/what-new-should-12929463
										- Inline comments (Quip-style)
										  collapsed:: true
										  Made the same request on CryptPad https://github.com/xwiki-labs/cryptpad/issues/79#issuecomment-319861379
											- DRAFT
												- In-line commenting would be great to have
												- http://i.imgur.com/ZQWJPcE.png
												- The picture from Quip above also shows in-line commenting as well as real-time chat panel, but the latter I think is overkill.
											- Made same request here
											  http://talk.dynalist.io/t/commenting/388/5?u=aaron
										- Mobile view
										  collapsed:: true
											- _Create issue: Mobile-friendly_
												- Very cool app. I like using outliners for jotting down notes when out and about e.g. grocery lists, unfortunately there's a few bugs in the mobile view currently:
											- Mobile view for web app isn't suitable yet
												- Text doesn't wrap
												- The header grey background isn't sticky but the text is
												- Needs a click-based zoom
												- Command mode doesn't work
											- Mobile app
										- Lazy loading
										- Following
										  collapsed:: true
											- $properties
												- Following
													- $name
													- $value
													- $assignee
													- $comments
													- $status
													- $priority
											- $preferences list
												- Updates
													- Always Ignore
													- Always Follow
													-
										- Relational Database mode
										  collapsed:: true
										  Pre-req: Spreadsheet | Maybe this is similar to spreadsheet View in that it's better implemented in my closed-source fork of Calculist as a good USP, add all the logic in the GUI
											- New Example Database
												- $properties
													- View Type [=] Database
													- Database Columns [=]
														- Colour
														- Size
														- Flavour
											- Each `Database Column` has a field type
												- Single line text / Long text / Date / Phone number / Email / URL / Number / Currency / Percent / Formula / Auto Number / Barcode
											- Dropdown menu appears in $properties when creating a new `Database Column`
											- Each cell has restrictions which force you to enter data according to field type requirements
											- Each cell also has GUI buttons and pop-ups which make correct data entry easier
											- Within the Preferences List you can define whether following intralinks to other records, tables or databases results in expanding to the record, table or database level view (default: record)
											- Terminology change: Row = Record, Spreadsheet = Table
											- Ability in $properties to have a floating sidebar panel appear which allows easy navigating to other tables
										- uTracker/Form/Journal/Data Entry mode
										  collapsed:: true
										  Pre-req: Relational Database mode
											- New Example Journal
												- $properties
													- View Type [=]  uTracker
													- uTracker Columns [=]
														- Colour [=] Text
														- Size [=] Dropdown menu
															- Large
															- Medium
															- Small
														- Flavour
															- Chocolate
													- Primary uTracker Column [=] Creation Datetime
													- Primary uTracker Column Prefix [=] Entry
													- Hide Old Entries = Yes
													- Sort = Newest at Top
												- Records
													- Entry 15:23 21/03/17
														- Colour [=]
														- Size [=]
														- Flavour [=]
														- <=SAVE=>
														  Pressing this button moves the entry to the 'Old Entries' sub-item
													- Old Entries
														- Entry 13:45 21/03/17
															- Colour [=]
															- Size [=]
															- Flavour [=]
														- Entry 12:32 21/03/17
															- Colour [=]
															- Size [=]
															- Flavour [=]
										- Collaborative editing - enhancements
										  collapsed:: true
										  https://github.com/calculist/calculist/issues/28
											- _Suggested_
												- Ways sharing could be enhanced:
													- As you mentioned above, read-write vs read-only access.
													- Ensure the shared list appears under the target user's 'list' bullet or perhaps a separate 'shared list' one.
													- Add an in-app notification that a new list has been shared with them.
												- And more generally about lists/bullets:
													- Allow embedding lists into your normal document so it appears like a normal section of sub-bullets. Perhaps the top bullet has a highlight or some visual indicator that it's the start of a list. This same embedded list could be cloned in multiple places in your document.
													- I'm not a fan of usernames being in the URL for both your main document as well as lists. It harms your privacy if seen by your ISP or other individuals and makes even less sense now if a list has shared read-write access and was made for someone else for example.
													- Instead I'd prefer a unique URL string for each list e.g. https://app.calculist.io/L/66fe7003c83f. I'm not sure about the exact length but I'd opt for random strings with no symbols and length which allows at least a billion variations.
												- Each bullet themselves could have a unique URL string (e.g. https://app.calculist.io/B/66fe7003c83f) which loads the app zoomed in on that particular bullet. This could allow seamlessly sharing a zoom level with others
										- Tasks (to-do) functionality
										  collapsed:: true
											- DRAFT
											- Completed ability
											- Toggle visibility
											- Recurring tasks
											- Dates
											- API for dates to allow reminders
											- Related
											  http://talk.dynalist.io/t/pro-recurring-tasks/28/6
										- Cloning/embed a referenced item's subitems (individual items already possible)
										  collapsed:: true
										  Suggested https://github.com/calculist/calculist/issues/17#issuecomment-321469690
											- VimFlowy http://i.imgur.com/iohzFu5.png
										- CardDAV sublist type + sync
										  collapsed:: true
											- Use 'item properties' to create a sublist or table which follows CardDAV template
											- Example
												- PERSON'S NAME
													- Pros/Cons
													- Some other organised info in table format
														- Status:
														- Touch Max: French kissing
														- Looks: 7.5
													- CardDAV data
														- FIRST NAME:
														- LAST NAME:
														- PHONE NUMBER:
														- EMAIL:
														- NOTES:
									- _Moderate_
									  collapsed:: true
										- Item Properties
										  collapsed:: true
										  Suggested https://github.com/calculist/calculist/issues/29
											- An extensible way of defining properties for an item. This would be a sub-item for properties, with sub-items with each having `PROPERTY  [=] VALUE`. This would be particularly useful when developing an API as each item property can be referenced for different actions, or if trying to narrow down a search, or as a way to store metadata for items.
											- Example
												- Item A
													- $properties
														- Creation Datetime [=] 17:39 29/02/17
														- Deadline Datetime [=] 12:43 21/07/17
														- Assignee [=] @Dan
														- Followers [=] @Jake @Steve
														- Priority [=] High
														- Status [=] In-progress
														- Completion % [=] 30
														- Reminder1 Datetime [=] 12:43 20/07/17
														- Reminder2 Datetime [=] 12:43 19/07/17
														- Reminder2 Text [=] This must be completed within 48 hours!
														- Notes [=] blah blah blah
														- Tags [=] #Software #Management
													- sub item A blah blah
													- sub item B blah blah
											- On the Preferences list there could be an Item Properties section which allows commenting out if you want to disable any properties list-wide, or to add custom user-generated ones.
											- This sort of extensible framework also is flexible enough to allow later GUI customisability e.g. maybe some people want to display the `Status` and `Completion %` in-line with the item or in a small area below it, whereas others might prefer seeing `Assignee` and `Deadline Datetime`. This would also solve #26 nicely.
											- The GUI for this could also be organised via properties e.g. `GUI itemleft [=] Status`, `GUI itemright1 [=] Priority`, `GUI itemright2 [=] Completion %`, `GUI itembelow [=] Tags`.
										- [[ for hypertext button
										  collapsed:: true
											- [[ to bring up item name in a dropdown menu
											- Adds a button with the item name, dynamic
											- Links to the item via it's unique ID
										- Copy Link button
										  collapsed:: true
											- Click item menu to do so
											- Clicking 'Copy Link' adds it to clipboard, toast notification and pop-up
											- GUI version of copy guid
										- Additional Item Properties
										  collapsed:: true
											- Checkbox
											- View Type e.g. Gantt chart, Grid, Kanban
											  intralink2:: https://workflowy.com/#/25ae1c998f84
										- 'Notes' area like WorkFlowy
										  Suggested https://github.com/calculist/calculist/issues/26
										- Version history (enhanced undo)
										  Planned https://www.patreon.com/posts/what-new-should-12929463
										- Search
										  Planned https://www.patreon.com/posts/what-new-should-12929463
										- File finder
										- Capture to inbox
										- 'Move to' feature - move current item below a specified item (currently only 'move to' list)
										  http://blog.dynalist.io/move-item/
										- Breadcrumbs
										- Easier interlinking
										  collapsed:: true
											- `goto ($value)` to zoom into the referenced item
												- rather than moving to the homepage view and uncollapsing it's parent items.
											- URLs for each bullet (using the $guid)
											  Pre-req: `goto ($value)` to zoom into the referenced item
											- 'Back' navigation
											  Pre-req: `goto ($value)` to zoom into the referenced item
												- A command or some way to go back to the previous item would be useful. If each zoom level's URL corresponded the item's `$guid` then the browser back button
											- A way to find out what other items are referencing the current selected one e.g. `mentions` or `referers`
											  Pre-req: a search feature
										- Tags / marks
										  collapsed:: true
										  Useful if for whatever reason you remove the tag later
											- Marks (one-way link, only one parent mark)
											  VimFlowy http://i.imgur.com/37prL1v.png
										- Modular - plugins concept (enable/disable features easily)
									- _Easy_
									  collapsed:: true
										- Firefox compatibility (seems to be fine on Chrome)
										- Design enhancements
											- Markdown formatting
											- Highlighting
											- Bigger bullet points
											- More obvious 'nested' bullet point
											- Adjustable font and font size via a settings button rather than /preferences manual URL type
											- Option to 'Use bullet point to zoom in' which creates + or - next to certain bullet points
										- GUI buttons for navigating
											- copy ( $guid )
											- goto $value
					- VimFlowy
					  collapsed:: true
						- [cloned] [https://github.com/WuTheFWasThat/vimflowy](https://github.com/WuTheFWasThat/vimflowy)
						- https://vimflowy.bitballoon.com/
						- Pros/Cons
						  collapsed:: true
							- Pros
								- Collapsing and expanding bullets
								- Zooming into bullets
								- Uses SQLite database locally or online
								- Customisable keyboard shortcuts
								- Modular - plugins can be enabled/disabled e.g. todo, ((6458ee2f-9855-4d38-89e5-726aa7bdd3ee)), HTML, text formatting etc
								- Cloning/embed
								  VimFlowy http://i.imgur.com/iohzFu5.png
								- Marks (like Asana Hypertext)
								  VimFlowy http://i.imgur.com/37prL1v.png
							- Cons
								- Mainly one contributor and makes infrequent commits
								- Missing
									- Mobile-optimisation for web app
									  https://github.com/WuTheFWasThat/vimflowy/issues/255
									- Non-vim mode
									  https://github.com/WuTheFWasThat/vimflowy/issues/201
									- allow editing a doc from multiple windows
									  https://github.com/WuTheFWasThat/vimflowy/issues/192
									- Mouse selection of text
									  https://github.com/WuTheFWasThat/vimflowy/issues/10
									- Drag-and-drop with mouse
									  https://github.com/WuTheFWasThat/vimflowy/issues/9
									- Collaboration
									  https://github.com/WuTheFWasThat/vimflowy/issues/166
									- No 'note area'
									- _Easy fix_
										- Desktop app
										  https://github.com/WuTheFWasThat/vimflowy/issues/194
											- Desktop apps can be created via
												- Electron
												- Nativefier for Electron
												  https://github.com/jiahaog/nativefier
										- Undo
											- Calculist has a reliable #undo feature thanks to jsondiffpatch from @beneidel
											  https://github.com/benjamine/jsondiffpatch
										- Import/export CSV
											- Calculist can import/export #CSV data thanks to PapaParse.js from @mholt6
											  https://github.com/mholt/PapaParse
			- [GitHub - vslinko/obsidian-outliner: Work with your lists like in Workflowy or RoamResearch](https://github.com/vslinko/obsidian-outliner)
			-
			- fiber-note
			  collapsed:: true
				- [https://github.com/namiwang/fiber-note](https://github.com/namiwang/fiber-note)
				- [https://namiwang.github.io/2020/11/12/building-a-roam-like-networked-heavily-customized-realtime-editor-part-1.html](https://namiwang.github.io/2020/11/12/building-a-roam-like-networked-heavily-customized-realtime-editor-part-1.html)
				-
			- Flowy
			  collapsed:: true
				- https://github.com/suyash/flowy
				- Flowy
					- https://suy.io/flowy/
					- A Workflowy clone that works offline, signed out and allows plugging in your own storage
					- https://github.com/suyash/flowy
					- Features
						- Works Offline: It installs a service worker and works using IndexedDB as an offline first cache.
						- Works signed out: No need to sign in to anything to use it, works out of the box with the browser cache. The browser cache will generally persist unless it is unused for a very long time.
						- "Moving" Storage: To get off-browser persistence and sync the same set of tasks on another device, allows plugging in your own storage server with an verification key, allowing resyncing the remote storage with your local tasks, or vice-versa. There are also a couple of sample server implementations for trying things out.
			- Magnolial
			  collapsed:: true
				- Saved to local
				- https://github.com/eflynch/magnolial
				- Demo
				  http://evanlyn.ch
			- CrushPaper
			  collapsed:: true
				- http://crushpaper.com/
				- [cloned] https://github.com/ZapBlasterson/crushpaper
				- Pros
				- Cons
					-
			- Concord
			  collapsed:: true
				- [cloned] https://github.com/scripting/concord
				- Part of Fargo
				  http://fargo.io/screen1.gif
				- Concord is the open source outlining engine in all our products. It manages the data structures and basic user interaction. Concord's functionality is documented in our Outliner Howto.
				- http://fargo.io/docs/outlinerHowto.html
			- HackFlowy
			  collapsed:: true
				- Missing Features
					- Critical
						- Enter 'tab' doesn't create a new line if there is already a node below it (it just moves to start of next line)
						- Using tab to indent does the indent but then highlights the node below it
						- Backspace to remove an empty node is very slow
						- Keyboard shortcuts non-existent
						- Add note doesn't work
						- No zoomable pages
						- Can't collapse and expand nodes
						- No search feature
						- No tag feature (part of search)
						- No 'save now'/saving/saved on GUI
						- Page doesn't extend vertically if you fill up the A4 screen
						- Can't drag and drop nodes
						- Can't select multiple nodes at once to move or delete
			- TreeSheets
			  id:: 680abbd5-a3bd-4a6b-9816-2674ecbf240c
			  collapsed:: true
				- Hierarchical spreadsheet
				- [https://github.com/aardappel/treesheets](https://github.com/aardappel/treesheets)
				- [http://strlen.com/treesheets/](http://strlen.com/treesheets/)
				- AppImage build
				  [https://github.com/aardappel/treesheets/releases/continuous](https://github.com/aardappel/treesheets/releases/continuous)
			- ThinkTool
			  collapsed:: true
				- [https://github.com/c2d7fa/thinktool](https://github.com/c2d7fa/thinktool)),
				- [https://thinktool.io/](https://thinktool.io/)
				- 1
					- Neat! I enjoyed your thoughts about choosing a data structure and editor component. I'm also building something in this space ([https://thinktool.io/](https://thinktool.io/),  and I decided on a somewhat different data structure, with pros and cons.
					- Instead of having pages that contain blocks inside of them (like Roam), I decided to have just one type of item. These items can have other items as children and parents, and they also contain text content which can link (bidirectionally) to other items.
					- The main advantage of this approach is that items can have multiple parents. So in practice, you never have to think about whether a note should be its own page or just a block inside a different page. This just feels more elegant than Roam's approach to me.
					- The main disadvantage is that you're now working with a graph rather than a tree. You can end up with funky situations like an item that's its own parent. Since I still want the user to interact with the app through a tree-based UI, I have to add an intermediary data structure representing what the user can actually see. This data structure needs to be built lazily as the user expands and collapses items, so we don't try to represent an infinite loop.
					- Whenever the user does something (adds an item, edits it, creates a link, etc.), we need to update both the intermediary data structure and the persistent data -- and ensure that these changes are kept in sync. For example, adding a link is a simple change in the graph, but it may require multiple updates to the tree.[1]
					- I also ended up going with ProseMirror for the editor component (after trying Quill, Slate, an input-based approach and using contenteditable directly). I'm really happy with ProseMirror, even though integrating it wasn't entirely pain-free.[2]
					- ---
					- [1] You can see the code for the tree-representation here if you're interested, although it's not necessarily written for public consumption: https://github.com/c2d7fa/thinktool/blob/master/src/client/s...
					- [2] The editor code is here: [https://github.com/c2d7fa/thinktool/blob/master/src/client/s](https://github.com/c2d7fa/thinktool/blob/master/src/client/s)... -- same disclaimer as above.
			- _See _Mind Map types e.g. Foam
			  #Software-PM [https://workflowy.com/#/699c40f52132](https://workflowy.com/#/699c40f52132)
			- _See org-mode based ones_
			  intralink2:: https://workflowy.com/#/01b0753e4925
		- Ecosystem tools
			- Alternatives to OPML, MD etc for to-do lists https://news.ycombinator.com/item?id=32552782
			- OPML converter
			  collapsed:: true
				- [https://github.com/banjerluke/workflowy-to-logseq](https://github.com/banjerluke/workflowy-to-logseq)
				- Personal freelance project - Dynalist OPML to Logseq MD conversion script
				- Logseq OPML importer
				  [https://github.com/logseq/logseq/commit/b13572547d4a1f45862f7b9713cd2fef82b50676](https://github.com/logseq/logseq/commit/b13572547d4a1f45862f7b9713cd2fef82b50676)
		- _Related:_
			- See [Mind Map ](https://workflowy.com/#/149675201676)
	- Real-time Collaboration
	  collapsed:: true
	  Document, Spreadsheet | Conflict-free Replicated Data Types (CRDTs) AKA CDRTs (misspelling)
		- _Differences_
		  collapsed:: true
			- [14/01, 16:28] L_Tom Taila: Yo check out www.notion.so
			- [14/01, 17:06] Aaron: Yeah I've seen that before, funnily enough I was just looking at it some similar apps last night. It's quite similar to Quip also https://quip.com/about/documents and https://bit.ai/
			- I've realised that virtually all productivity apps use 3 different data models - document-based (Evernote-like), outliner-based (eg Dynalist) and table-based (eg Airtable). Just about using the right tool for the job. For most people a document-based approach like Notion or Quip is the easiest though as it's the most free-form
			- [14/01, 19:12] Aaron: Sure, but they're not nearly as flexible as in Airtable. You can do grouping, filtering, swap it to different views (table, form, kanban, calendar, gallery) and use the data as the backend for over a dozen app-like Blocks
			- [14/01, 19:14] Aaron: I view them as separate because similarly you can have simple tables in Microsoft Word but it's not nearly as powerful as Excel
		- _Document-based_
		  collapsed:: true
			- _My Journal_
			  collapsed:: true
				- Analysis 15/1/19
				  collapsed:: true
					- _For personal use - wait until Q2 at least to check again_
					- Standard Notes is very good for personal data, though it needs inline images and interlinking to consider it
					  intralink2:: https://workflowy.com/#/f5a2ad5a2fa6
					- Outline could have more functionality in the future than Standard Notes (and become on par with Notion) thanks to integrations (eg Airtable) and collaboration features BUT right now is just a glorified markdown editor
					- Need to test the export functionality of Outline + Standard Notes to see which is most viable
					- Need to review Trillium properly, but AFAIK it's not as featureful as Standard Notes
					- _Commercial_
						- Notion has 99% the best UX but isn't viable for personal use, only commercial
							- Export sucks and there being no E2EE or self-hosted means it's a no-go for personal projects (though possibly for my commercial ventures, in that scenario I just want to get my team all using one tool effectively e.g. for Rexford Ventures I had everyone on Airtable)
						- If Airtable adds a rich text editor for long text then it's pretty usable as a replacement for Notion
					-
				- Analysis 28/10/19
				  collapsed:: true
					- I've started using Notion because I need a database, or at least a table for easily reviewing various software projects. So I'm considering using Notion for documents too
					-
			- _Proprietary_
			  collapsed:: true
			  e.g. Notion, Airtable, Evernote, Dropbox Paper
				- [Obsidian](https://obsidian.md/)
				  id:: 657b8767-8071-48fb-96df-f30379dc796b
				  collapsed:: true
					- Pros/Cons
						- Pros
							- Markdown-based, so very little lock-in
							- ((680abbd6-9cb2-4d20-875d-01498a5c2bdb))
							- ((63ff81aa-fb4f-481b-b591-8e5d8085865c))
							- ((64305142-fd5e-4a23-bd7f-5071cab08343))
							- [GitHub - obsidianmd/jsoncanvas: An open file format for infinite canvas data.](https://github.com/obsidianmd/jsoncanvas)
							- [Bases](https://help.obsidian.md/bases) [core plugin](https://help.obsidian.md/plugins)
							  id:: 683181f7-8e2f-435f-80a5-99becdd6a995
							  AKA databases built on YAML
						- Cons
							- Proprietary
							- Lacks
								- Close to tray
								  [https://forum.obsidian.md/t/close-to-tray/6781/31](https://forum.obsidian.md/t/close-to-tray/6781/31)
								- [https://trello.com/c/qQxCzz0H/67-preserve-links-after-renaming-headings-and-blocks](https://trello.com/c/qQxCzz0H/67-preserve-links-after-renaming-headings-and-blocks)
								- Can't open two windows of the same Vault
								  [https://forum.obsidian.md/t/floating-pop-out-multiple-windows-of-the-same-vault/837/158](https://forum.obsidian.md/t/floating-pop-out-multiple-windows-of-the-same-vault/837/158)
					- By Dynalist creators
					- Documentation
					  collapsed:: true
						- Fixing EMFILE error
						  id:: 63bab109-b971-4abe-a17f-cde278bd69d7
							- Switch to root, trying sudo alone was insufficient permissions
							  `sudo su root`
							- Show `max_user_instances`. Probably ~100
							  `cat /proc/sys/fs/inotify/max_user_instances`
							- `echo 1024 | sudo tee /proc/sys/fs/inotify/max_user_instances`
							- To make it permanent
								- In order to make that change permanent you can always add a line to `sudo nano /etc/sysctl.conf`:
								- ```
								  fs.inotify.max_user_instances = 1024
								  ```
					- Plugins
						- Community plugins
							- Obsidian Dataview
							  id:: 6525b49e-aeb9-406e-a1e6-7ca7d14f9630
							  collapsed:: true
								- [https://news.ycombinator.com/item?id=31407781](https://news.ycombinator.com/item?id=31407781)
								- [https://github.com/blacksmithgu/obsidian-dataview](https://github.com/blacksmithgu/obsidian-dataview)
								- [https://minimal.guide/Block+types/Cards](https://minimal.guide/Block+types/Cards)
								- ..
								- [https://forum.obsidian.md/t/allow-links-in-yaml-front-matter-notion-like-databases-from-metadata-links-as-first-class-citizens/10052/3](https://forum.obsidian.md/t/allow-links-in-yaml-front-matter-notion-like-databases-from-metadata-links-as-first-class-citizens/10052/3)
								- 2 Backlinks
									- Related: See [Obsidian ](https://workflowy.com/#/ba27815e45bc)<a href="https://workflowy.com/#/ba27815e45bc">Dataview</a>
									- See [Obsidian Dataview](https://workflowy.com/#/ba27815e45bc)
							- QuickAdd
							  id:: 67000f1e-0095-4728-a75d-9df2aa7fa201
							  collapsed:: true
								- Demo and tutorial
								  [https://youtu.be/gYK3VDQsZJo](https://youtu.be/gYK3VDQsZJo)
								- 1 Backlink
									- [QuickAdd](https://workflowy.com/#/4461f00ba930) for <a href="https://workflowy.com/#/73475ce19351">Obsidian</a>
							- ((6631e29c-5695-4a50-92cd-10285688826d))
							- [GitHub - tgrosinger/advanced-tables-obsidian: Improved table navigation, formatting, and manipulation in Obsidian.md](https://github.com/tgrosinger/advanced-tables-obsidian)
							-
					- [Learning Resources]
					  collapsed:: true
						- [https://teddit.bus-hit.me/r/ObsidianMD](https://teddit.bus-hit.me/r/ObsidianMD)
				- [Notion](https://www.notion.so/)
				  id:: 6525b49e-8fcd-4440-9a3e-3c65d4edb58b
				  collapsed:: true
					- https://www.notion.so/product
					- Pros/Cons
						- Pros
							- Database table support is very good, nearly Airtable level
							- August 2025 - [Notion rolls out Offline Mode: edit pages without an internet connection | AlternativeTo](https://alternativeto.net/news/2025/8/notion-rolls-out-offline-mode-edit-pages-without-an-internet-connection/)
							-
						- Cons
							- Exporting is weak
							  collapsed:: true
								- It loses all hierarchical structure (unlike Evernote which used folders, it shows a flat doc
							- Bad UX for login
							  collapsed:: true
								- pecifically, the login is a randomly-generated one-time code sent to your email address. Notion says this is more secure than them storing a username+password, but that's a dubious argument. They've also said this is two-factor auth (lolno). A side effect of this is that Notion is unusable on my mobile device since I have no email on it.
								- lstamour 19 hours ago [-]
								- They imply that the login is 2FA-protected because your email or Google account can be 2FA-protected, and they're piggybacking off that...
								- Having passwords means storing them correctly and still implementing some form of reset -- and if email is a weak point, they would have to 2FA prompt you to reset your password, or not use magic links, or handle such issues out-of-band. They're probably trying to avoid auth/password support by outsourcing this function to Google for the time being.
								- I agree though, the user experience that is hardest-hit by this is mobile, where iOS now supports much better integration with password managers than was allowed previously...
							- No Linux app despite being Electron
							- 1000 blocks limit until you have to pay monthly
							- Doesn't have Airtable Blocks-like functionality (apps based on database data)
							  intralink2:: https://workflowy.com/#/48aafcd815ef
					- Features
					  collapsed:: true
						- Many content block types
						  http://i.imgur.com/mwCvl8u.png
							- https://www.notion.so/Notion-editor-101-create-and-edit-68c7c67047494fdb87d50185429df93e
						- / or press the + UI element to add a block
						  https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F0ed25d14-3a02-4800-8c80-e97788dc5866%2Fcreatewithplus.gif
						- Drag select to highlight multiple content blocks for deletion/moving
						  https://www.notion.so/front/features/personal-feature-dnd.gif
						- Two columns, checklists, web bookmarks
						  https://www.notion.so/front/use-cases/use-case-screenshot-note.gif
						- Hierarchical folders, emoticons in text and doc titles, emoticons affected by header tags, internal links
						  https://www.notion.so/front/use-cases/use-case-screenshot-wiki.gif
						- Kanban view
						  https://www.notion.so/front/use-cases/use-case-screenshot-task.gif
						- List view
						  https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F546cf2a1-1e48-4a61-a785-20aeae9daa0d%2Flist-view.png?width=860
						- Database type - table, calendar, kanban, list, gallery
						  https://www.notion.so/front/use-cases/use-case-screenshot-database.gif
							- Differences
								- Airtable Blocks are basically apps using the database data
								- Notion Content Blocks are basically anything that makes up a Notion doc
							- Is highly similar to Airtable
							  http://i.imgur.com/AsrQG2h.png
							- _Features_
								- _Similarities to Airtable_
									- Databases have over a dozen different field types
									  http://i.imgur.com/ieWNElu.png
									- Views dropdown menu to save different manipulations of the data
									- Open any record as a pop-up
									  http://i.imgur.com/LQUGg0C.png
									- Data manipulation:
										- Properties - Filter out particular columns
										  http://i.imgur.com/3cWXGzy.png
										- Filter out particular values (font colour changes to blue when a filter is active)
										  http://i.imgur.com/O2y0jt8.png
										- Different Views types
										  http://i.imgur.com/dhGD5Ku.png
										- Sort by multiple columns
										  http://i.imgur.com/a5wCj6g.png
							- https://www.notion.so/Database-101-tables-boards-calendars-c523297c17634873a52317dd7a3e0b77
							- Tables
							  https://www.notion.so/Database-101-tables-boards-calendars-c523297c17634873a52317dd7a3e0b77
						- At least 4 columns
						  https://pbs.twimg.com/media/DlsxhxpV4AEboG4.jpg?format=jpg&name=orig
						- Slack integration - page updates get sent to a specified Slack channel
						  https://www.notion.so/Integrate-with-Slack-46d081bdacdb4269aed1333bb195addb
						- In-line comments
							- Can see comments below the checklist
							  http://i.imgur.com/1hIoFph.png
					- https://www.youtube.com/watch?v=K80A3q0Plgc
					- Template ideas
					  https://notionpages.com/
					- Changelog
					  https://www.notion.so/What-s-New-157765353f2c4705bd45474e5ba8b46c
					-
				- Coda
				  collapsed:: true
					- http://i.imgur.com/brNQDG2.png
					- https://www.theverge.com/2017/10/19/16497444/coda-spreadsheet-krypton-shishir-mehrotra
					- https://coda.io/welcome#packs5
					- https://coda.io/t/Equipment-Inventory-Management_tygMFV9thV3
					- https://coda.io/t/Boxs-Candidate-Coordination-Doc_tBgNyOvzJ8e
					- New product updates
					  https://coda.io/d/Coda-Product-Updates_dz5Ie_WzBJp/Latest-Updates_suT02?viewMode=embedplay&hideSections=true#_luNGN
					- Features
					  collapsed:: true
						- Various type of blocks
						  https://discourse-cdn-sjc2.com/standard17/uploads/coda1/original/2X/e/e9e62a4fa5140fe0d0b590dbd114c55dd6e28ebc.gif
						- Multiple Views can be inserted or changed from one block - Table, Cards (Kanban), Calendar, Chart (Bar/Pie), Detail (like Astrid Tasks task info or Airtable expand record)
						  http://i.imgur.com/brNQDG2.png
						- _Integrations_
							- Embed many types of 3rd party elements e.g. YouTube videos
							  https://discourse-cdn-sjc2.com/standard17/uploads/coda1/original/2X/8/88c359e84198caa2e06982e2f3384b0453f9bf6d.png
								- https://community.coda.io/t/new-easily-embed-anything-in-your-docs/6183/10
								- https://help.coda.io/organizing-your-doc/layout-options/embedding-content-in-your-doc
							- Packs - Buttons and elements which trigger integrations e.g. a message to Slack
							  https://cdn.coda.io/assets/img/NewKindOfApp.e216b7f9d0ec6f7cf2b37e2adefbde79.gif
								- Text all contacts with a unique message
								  https://cdn-images-1.medium.com/max/1600/1*5JtfCFp4HPHmPIgREhM3pw.gif
								- With Packs, you can connect your customer conversations and bug tickets together in a doc, and even push the information back into Intercom and GitHub. So everyone gets the context they need, in the tools they like.
								  https://cdn-images-1.medium.com/max/1600/0*ycJDIMH27AvNjQR7
								- Weather, Wikipedia, Instagram
								  https://coda-templates.netlify.com/images/uploads/packsvacations.gif
								- Bring design, code, and communication together with Figma, GitHub, Intercom, and Slack
								  https://coda-templates.netlify.com/images/uploads/pakcslaunchproducts.gif
								- More
								  https://coda-templates.netlify.com/images/uploads/getstarted.gif
								- {Archive}
									- https://blog.coda.io/connecting-the-doc-9be7fc1fd571
									- Packs Starter Kit
									  https://coda.io/t/_tDpsxMCm1or
							- Automation block e.g. send email
							  https://ph-files.imgix.net/776862d8-6cb5-4e77-a540-b9f5743bd4c1?auto=format&auto=compress&codec=mozjpeg&cs=strip&w=687.0056497175142&h=380&fit=max
								- https://community.coda.io/t/announcing-automation/3434
						- Great mobile UX
						  https://cdn.coda.io/assets/img/MobileTabsLP.8ef9bded19acec63d1ade9c57f7c6182.gif
							- Buttons in tables for mobile view has a good UX
							  https://cdn.coda.io/assets/img/MobileTablesButtonsLP.e261027db999be520da03d521fe7c699.gif
							- the building blocks rearrange to feel like a native app. Buttons become swipe actions. Sections become your nav. And notifications push to your phone.
						- Layouts
						  https://cdn-images-1.medium.com/max/2000/1*-4yUHLKnkZGuaKuZnmqvpA.gif
							- https://blog.coda.io/new-building-block-layouts-6337b28a4ca7
						- Doc Map (like an enhanced floating Table of Contents)
						  https://cdn-images-1.medium.com/max/2000/1*TfP1jVG4b-CoqsralyVfEg.gif
							- https://help.coda.io/organizing-your-doc/setup-best-practices/using-the-doc-map
				- Quip
				  collapsed:: true
					- [https://quip.com/about/tour](https://quip.com/about/tour)
					- Pricing
					  collapsed:: true
						- Free trial is unlimited for personal use, for collaboration though it uses up credits
							- On average, once you start collaborating with another person in Quip, the trial typically lasts between 15 and 30 days.
						- $30 per month for a team of five
						- Adding a personal account
						  https://www.quipsupport.com/hc/en-us/articles/210437626-How-do-I-add-a-personal-account-to-Quip-s-Account-Switcher-
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Contextual Collaboration - chat rooms per task and per document/project or arbitrary
								- Collaboration happens right alongside the projects and tasks it pertains to. It’s easy to stay up to speed on what’s going on, and for teams to share their progress.
							- Spreadsheets and documents with chat
							- Interlink all files
						- Cons
							- Checklists could use with a floating button that allows the subtasks to be collapsed - much easier to avoid being distracting by huge lists of tasks, especially if you use all 9 levels of hierarchy for the tasks.
							- Multiple sheets on a document doesn't have a great UI. I'd want to hide the second sheet from being embedded and have the tabs instead be right underneath the table, rather than at the bottom of the screen.
							- And it seems like you must get this feature request a lot but it would be great to be able to reference values of spreadsheets in other documents. You have the contextual collaboration thing almost entirely down, except for that feature.
					- Features
					  collapsed:: true
						- Main view is the document - which can include spreadsheet, checklists etc
						  http://i.imgur.com/rHZn405.png
							- https://i.imgur.com/tJgXehV.png
							- Checklists allow 9 levels of hierarchy
						- Optional side panel in docs/spreadsheets
						  http://i.imgur.com/AqvntLo.png
							- https://www.quipsupport.com/hc/en-us/articles/115000520486-How-do-I-hide-the-message-thread-
							- Allows instant chat and/or update stream for doc changes
						- Optional: Arbitrary full chat rooms
						  http://i.imgur.com/yIdMkjB.png
						- Context
							- Contextual comments within documents too
							  http://i.imgur.com/UZmLVH1.png
							- Can interlink to documents, spreadsheets, files etc
							  http://i.imgur.com/dfEcmLD.png
							- Reminders can be created on a checklists, spreadsheets or anywhere on a doc
							- Reference cells from the document
							  http://i.imgur.com/Wa7bZbm.png
							- Anchor links
							  https://www.quipsupport.com/hc/en-us/articles/115001098746-Does-Quip-have-anchor-links-
						- Updates (Asana 'Inbox')
						- Tables for advanced task management
						  http://i.imgur.com/hD10WvM.png
						- Tables + spreadsheets
						  https://www.quipsupport.com/hc/en-us/articles/210435246-What-is-the-difference-between-tables-and-spreadsheets-in-Quip-
						- Documents can be exported into several formats
						  https://www.quipsupport.com/hc/en-us/articles/115000654106-Can-I-export-my-Quip-documents-
						- Integrations e.g. Zapier
						  http://i.imgur.com/BfmYw7C.png
				- Airtable (long text field)
				  intralink2:: https://workflowy.com/#/48aafcd815ef
				- Bit.ai
				  collapsed:: true
					- https://bit.ai/
					- Similar to Quip?
				- Dropbox Paper
				  collapsed:: true
					- Quite similar to Quip's document view - allows linking people, adding comments, reminders
				- Samepage
				  collapsed:: true
					- https://www.samepage.io/demo
					- Pages (can have tasks, images etc on it)
					  http://i.imgur.com/v4GqvXU.png
					- Tasks view
					  http://i.imgur.com/V0OhBaz.png
				- Slab (built on Quill)
				  collapsed:: true
					- https://slab.com/
				- HackMD (built on CodiMD)
				- Nuclino (built on ProseMirror)
				  collapsed:: true
					- https://d33wubrfki0l68.cloudfront.net/cade63166b3df91ce74cbf5bc5f9d22e977e46ac/99e84/img/teams/team_hr.jpg
					- Intro/UI
					  https://youtu.be/wvL2SFjpoVo
					- https://www.nuclino.com
					- Features
						- Uses Google Doc-style comment pop-ups though it's based on highlighted text
						  1m https://youtu.be/wvL2SFjpoVo
						- Drag-and-drop inline embedding attachments
						  https://www.youtube.com/watch?time_continue=70&v=wvL2SFjpoVo
				- Evernote
				- Confluence
				  id:: 65f6f2f5-bdf6-4244-bbe7-a8fad73e15a4
				- Microsoft SharePoint
				- [Microsoft Loop](https://loop.microsoft.com/learn)
				  id:: 66cba586-18d7-4248-88d4-82db786a8c85
				- Google Docs
				- Microsoft Office 365
				- ONLYOFFICE Online
				  collapsed:: true
					- https://personal.onlyoffice.com/
				- Deepnote
				  collapsed:: true
					- [https://deepnote.com/](https://deepnote.com/)
					- Pros
						- Compatible with Jupyter
						- Real-time collaboration
					- Cons
						- Proprietary
					- [https://news.ycombinator.com/item?id=24942797](https://news.ycombinator.com/item?id=24942797)
			- _Open-source_
			  collapsed:: true
				- _E2EE (client-side encryption)_
					- [SiYuan](https://github.com/siyuan-note/siyuan)
					  collapsed:: true
						- [SiYuan - Privacy-first personal knowledge management system that supports Markdown, block-level ref, and bidirectional links](https://b3log.org/siyuan/en/)
					- Standard Notes
					  id:: 6525b49e-bed7-44bf-b1b0-41fa9fbf0847
					  collapsed:: true
						- Standard Notes
						  collapsed:: true
						  https://github.com/standardnotes
							- Pros
								- Allows images, videos, files to be client-side encrypted and stored on WebDAV server (eg Nextcloud) or Google Drive/Dropbox
								  https://listed.standardnotes.org/@sn/2703/encrypt-your-dropbox-and-google-drive-with-standard-notes-filesafe
							- Cons
								- Ideally: outliner also rather than just nested folders
								  https://github.com/standardnotes/forum/issues/180
								- All extensions would require being paid for life (unless they're also FOSS?)
									- I was thinking the exact same thing when I was trying out standard notes last week. even something basic that would let you expand and collapse items would be a start. zooming might require a lot more work.
									- at the same time I don't think I would like it in the long run since you would have to pay the subscription fee for life just to keep using that feature.
									- I'm actually paying for a few different services to support them but they are all things that would still work if i didn't have the money for some reason. with SN you're pretty much held hostage
						- https://standardnotes.org/
						- https://github.com/standardnotes/forum/issues
						- Pros/Cons
						  collapsed:: true
							- Pros
								- Device Storage Encryption - ensures decrypted data is never on your hard drive/phone storage
								  collapsed:: true
								  [Listed — Welcome to your new public journal.](https://listed.standardnotes.org/@sn/824/enhanced-security-with-device-storage-encryption)
									- Enhanced security with Device Storage Encryption
									- _October 18, 2017_
									- Last week we introduced a new security feature called Device Storage
									- Encryption (DSE) for iOS, Android, Web, and Desktop. We mentioned
									- briefly how in addition to the already end-to-end encrypted sync
									- Standard Notes provides, DSE can further safeguard your data by making
									- sure unencrypted data never touches a hard drive. This post explains how
									- DSE works, and how it fits in with the existing encryption technologies
									- used by Standard Notes.
									- Standard Encryption
									  collapsed:: true
										- When you’re using Standard Notes with a signed in account, we
										- generate private encryption keys from your password, and save these keys
										- on device. Every key stroke you type, and thus every change you make to
										- a note, is immediately encrypted using these keys, then synced to your
										- other devices. Since you’ll have signed in to these other devices as
										- well, those devices will have your encryption keys available to decrypt
										- incoming changes.
									- Expanding our Threat Model
									  collapsed:: true
										- Before DSE, your encryption keys would need to be stored on your
										- local computer without being encrypted. This was because without an
										- additional password, there would be no straight forward way to encrypt
										- your keys for offline storage (particularly on the web app). Our main
										- threat model (or, what we set out to protect against) was making sure no
										- one but you can read your notes. We treated servers and unencrypted
										- online transmission of data as the main enemy. Your personal device,
										- protected by you in the comfort of your pocket or your home, we treated
										- as safe.
										- With DSE, we expand our threat model to also protect you from device
										- seizures, loss, and theft. All of our applications on every platform
										- (Mac, Windows, Linux, iOS, Android, and Web) now offer the option to add
										- an extra application password called a “Local Passcode”.
									- This passcode serves two purposes:
									  collapsed:: true
										- It will lock the application with a passcode which must be entered before you can enter, use, and read application data.
										- On Desktop and Web, it will encrypt your local key storage. This means that keys that were once stored on your offline device without encryption will now be encrypted using AES-256 with a key derived from your local passcode using PBKDF2.
									- The result is actually kind of cool: unencrypted data never touches your hard drive, or anyone else’s hard drive.
									- How it works:
									  collapsed:: true
										- On enter, the app prompts for your local passcode.
										- It compares the hash of your inputted password to a saved hash, and if correct, uses your inputted password to generate the remainder of your keys.
										- These keys are used to decrypt your saved account encryption keys.
										- The application now reads encrypted data from your local database, and decrypts this data using your decrypted account keys.
										- The decrypted data now lives only in ephemeral memory, and is displayed so that it can be edited by the user.
										- When you make a change to a note, it is encrypted immediately, then synced to your account and saved in your device's database.
										- Finally, when you quit the app, the decrypted data which lived in memory is immediately destroyed.
									- So what?
									  collapsed:: true
										- What’s the significance of decrypted data never touching your hard drive? Well, hard drives are sort of tricky to keep an eye on. Once a file touches disk, you can’t be certain that a copy of it wasn’t made, or that it wasn’t backed up by your system, or synced to a file syncing platform. With memory, things are more volatile, but ephemerality is built in. You can be sure that it won’t be backed up by a system process or 3rd party application.
										- (On iOS and Android, your keys are stored in your device’s secure keychain, so a local passcode serves more as a deterrent to unwanted physical access, compared to the web app, where a secure device keychain is not available.)
										- You can learn more about our other privacy measures here. You can also download the new applications for your platform from our downloads page. And as always, if you have any questions, please don’t hesitate to reach out to hello@standardnotes.org.
								- Can be self-hosted, including extensions
								  collapsed:: true
									- How to self-host
									  https://standardnotes.org/help/47/can-i-self-host-standard-notes
									- _It actually seems that you don't need to self-host the web app (Standard Notes) or the server app (Standard File). All you have to do is host the extensions_
									  collapsed:: true
									  https://docs.standardnotes.org/extensions/local-setup
										- For self-hosting your own extensions, you don't need to self-host either the web app or Standard File. These are all completely independent. As for the webserver for the extension, we do talk about it in the link you shared. http-server -p 8001 --cors. You would run that command from within the extension directory. Then, if ext.json is in the root of that directory, localhost:8001/ext.json should just work.
										- In your screenshot, the link you enter shouldn't be dist.js, it should be the ext.json link.
									- Self-host extensions
									  collapsed:: true
									  https://github.com/sn-extensions
										- https://github.com/standardnotes/forum/issues/422
							- Is there code blocks? Is
							- Cons
								-
								- Limited functionality in free version - you need to self-host extensions or pay for a subscription ($50/year) to have anything beyond MVP functionality
								  e.g. folders, markdown or WYSIWYG editor, dark theme etc)
								- Collaboration / sharing not possible (unless in unencrypted form) - this also limits being able to link to it
									- Unencrypted - see Listed
									- https://github.com/standardnotes/forum/issues/286
									- https://github.com/standardnotes/forum/issues/333
									-
								- _Lacks_
									- Interlinking to other notes
									  https://github.com/standardnotes/forum/issues/324#issuecomment-538043946
									- A way of hyperlinking directly to a note
									  https://github.com/standardnotes/forum/issues/324#issuecomment-458330664
									- Do non-inline attachments show in some form in the exported Markdown files?
										- e.g. at the top of the Markdown note is a special attribute that says the filenames which were attached
									- FileSafe limitations
									  intralink2:: https://workflowy.com/#/7c8c7a2d48f7
									- Secure Spreadsheets limitations
									  intralink2:: https://workflowy.com/#/eeb4ac0fc897
									- Inline due dates (for checklists)
									- Simple Task Editor is basic. I'd like something up to the level of Tasks or Todoist. Dev says he hasn't got the skill to do so though
									  https://standardnotes.org/extensions/simple-task-editor
										- Mobile notification reminders (see MQTT, websockets etc)
										- _Desired features_
											- Reminders
											- Recurring tasks
											- Infinite hierarchy
										- Not currently interested in outliner features
											- https://github.com/sn-extensions/simple-task-editor/issues/8
											- https://github.com/standardnotes/forum/issues/180#issuecomment-441404669
									- Search inside note
									  https://github.com/standardnotes/forum/issues/128
						- Extensions
						  https://standardnotes.org/extensions / https://github.com/sn-extensions
							- Secure Spreadsheets
							  collapsed:: true
								- https://github.com/sn-extensions/secure-spreadsheets
								- https://standardnotes.org/extensions/secure-spreadsheets
							- FileSafe (E2EE for files - Google Drive, Dropbox or WebDAV eg Nextcloud)
							  collapsed:: true
							  https://standardnotes.org/filesafe
								- Picture of structure
								  https://standardnotes.org/assets/filesafe-graph.png
								- Relay (server)
								  https://github.com/standardnotes/filesafe-relay
								- Client
								  https://github.com/standardnotes/filesafe-client
								- _FileSafe limitations_
									- New
										- FileSafe image attachments can now be embedded if you use the Bold Editor
										  https://github.com/standardnotes/forum/issues/96#issuecomment-458580624
											- _Inline attachments and embedded image preview_
												- I suggested Dynalist-like inline buttons and image previewer
												  https://github.com/standardnotes/forum/issues/96#issuecomment-458580624
													- Like Dynalist
													  https://i.imgur.com/ThHKgK7.mp4
											- Web crypto viewer for FileSafe attachments (TagSpaces-like preview all multimedia)
										- Amazon S3 support for FileSafe attachments (currently WebDAV, Google Drive and Dropbox)
									- FileSafe filenames are not encrypted
									  https://github.com/standardnotes/forum/issues/305#issuecomment-450336126
									- Filenames are not unique
									  https://github.com/standardnotes/filesafe-relay/issues/1
									- FileSafe (encrypted attachments) not on mobile yet
									  https://github.com/standardnotes/forum/issues/313
							- Simple Task Editor - Checklist
							  https://standardnotes.org/extensions/simple-task-editor
							- Rich text editor (makes note HTML)
							  https://standardnotes.org/extensions/plus-editor
							- Note history
							- Many themes
							- Listed - publish a blog directly
							  https://listed.standardnotes.org/
						- Offline installation of extensions.
							- This is a big one. Previously, extensions like editors and themes were downloaded from a server every time you wanted to use them. Now, on desktop, extensions are automatically installed locally and offline, so you can use them without a connection. This also improves security by not relying on an external server for extensions.
					- [CryptPad](https://cryptpad.fr/)
					  id:: 6525b49e-2c74-456d-bfce-b8a6ade1972f
					  collapsed:: true
						- _Overview_
							- https://blog.cryptpad.fr/
							- [https://github.com/xwiki-labs/cryptpad](https://github.com/xwiki-labs/cryptpad)
							- Demo
							  https://cryptpad.fr/pad/
							- Open Collective
							  [https://opencollective.com/cryptpad](https://opencollective.com/cryptpad)
						- Pros/Cons
							- Pros
								- Many types of realtime editors
									- Rich Text editor
									  collapsed:: true
										- vs Etherpad-Lite
										  Aug 2017
											- Pros
												- Nicer UI
												- More actively maintained
												- CryptDrive for managing all docs
											- Cons
												- No in-line comments
												- No real-time chat panel
									- Slide editor
									- Code editor
									- Polls
									- Todo List
									- Whiteboard
									- Spreadsheets (based on OnlyOffice)
									  collapsed:: true
										- https://i.imgur.com/ovWtv0E.png
								- Simple version history reverter (doesn't highlight changes, just a snapshot)
								  collapsed:: true
									- http://i.imgur.com/e34eM4E.png
								- File upload to CryptDrive
								  https://blog.cryptpad.fr/2017/06/21/CryptPad-Jackalope-file-upload-pdf-and-pictures/
								- Real-time chatroom in every pad
							- Cons
								- If a pad isn't pinned and is unedited for 6 months then it will be deleted
								- See roadmap
								  https://blog.cryptpad.fr/2018/07/13/CryptPad-Roadmap/
									- Donation URL
									  https://opencollective.com/cryptpad
								- Lacks
									- Reminders
									  https://github.com/xwiki-labs/cryptpad/issues/304
									- No desktop apps - can browser encryption be trusted?
										- https://blog.cryptpad.fr/2017/07/07/cryptpad-analytics-what-we-cant-know-what-we-must-know-what-we-want-to-know/
									- No desktop sync client - for notification
									- No mobile client for notifications/chat
					- Joplin
					  id:: 6525b49e-3e4f-4733-97c0-8e68f6e60d5d
					  collapsed:: true
						- Has to-dos
						- [https://github.com/laurent22/joplin](https://github.com/laurent22/joplin)
						- Platforms
							- Linux
							- Android
							  https://play.google.com/store/apps/details?id=net.cozic.joplin
							- 3rd party web app
							  https://github.com/foxmask/joplin-web
						- Pros
							- Support for alarms (notifications) in mobile and desktop applications.
						- Lacks
							- WYSIWYG for markdown
							  https://github.com/laurent22/joplin/issues/176
					- TiddlyWiki
					  collapsed:: true
						- Documentation
						  collapsed:: true
							- _My current TiddlyWikis_
								- TiddlyWiki1 - for non-bullet notes
								- TiddlyWiki2 - for bullet notes
									- Pros/Cons compared to WorkFlowy/Dynalist
										- Pros
											- Hosted on my own computer, so better privacy
										- Cons
											- Doesn't remember homepage collapse/uncollapse state
											- Tiddler "title" is set to the creation datetime, though this is hidden. The body is the bullet content
							- ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) version install + TW creation
								- New TiddlyWiki on Node.js
								  https://tiddlywiki.com/#TiddlyWiki%20on%20Node.js
									- Pros
										- can be run on server or local
										- plus it scales well as each Tiddler is a separate file, unlike single HTML file TiddlyWiki which only works with little multimedia
										- Lazy loading can be used
										  https://tiddlywiki.com/#LazyLoading
								- _Install node and npm_
									- `node -v`
									  Check node version
									- `sudo apt install nodejs`
									- `npm -v`
									  Check npm version
									- `sudo apt install npm`
								- sudo npm install -g tiddlywiki
								- tiddlywiki --version
								  Check TiddlyWiki version
								- tiddlywiki tiddlywiki1 --init server
								  to create a folder for a new wiki that includes server-related components (it'll be created at ~/tiddlywiki1/) - make sure NOT to run sudo or only root will be able to edit that folder
								- tiddlywiki tiddlywiki1 --listen port=8191
								   to start TiddlyWiki, CTRL+C to cancel
									- 8080 default is usually used by Syncthing
								- [http://127.0.0.1:8191](http://127.0.0.1:8080/)
							- Alternative platforms
								- TiddlyWeb - Multi-user self-hosted version
									- http://tiddlyweb.com/
									- Tank
										- https://tank.peermore.com/tanks/tank-notes/TiddlySpace%20and%20Tank
										- Uses markdown and a URI for each tiddler
								- [https://ibnishak.github.io/Timimi/](https://ibnishak.github.io/Timimi/)
								- _Android compatibility_
									- https://tiddlywiki.com/#Serving%20TW5%20from%20Android
									- Quinoid
										- https://github.com/Marxsal/Quinoid01
										- https://marxsal.github.io/quinoid
									- https://tiddlywiki.com/#TiddlyWiki%20on%20Firefox%20for%20Android%20Video
							- Alternatively can run from a different port e.g:
							  tiddlywiki twiki1 --server 8088
								- This can be useful to avoid clashing with other web services that also use port 8080 by default or for serving multiple Tiddlywikis, with port number as unique identifier. Most port numbers don't have any particular significance - pick a 4 digit number bigger than 1024 and you should be fine.
							- Save button = export
								- New tiddlers are created as individual files back in your wiki directory, as we will see in a moment, and the "save" button in Tiddlywiki now functions as a snapshot/download button which will download the wiki as a "traditional" single-file Tiddlywiki. This is great for making manual backups and for sending/storing/hosting the wiki.
							- LAN Wiki
								- Use ipconfig and scouring the output for a likely candidate - local ip address tend to start either with 192.168. or 10.0. and are made up of four blocks of numbers separated by periods. For example 10.0.1.2 or 192.168.0.4.
								- All you need to do is replace 127.0.0.1 with your real, local ip address.
							- How to export Tiddlers from other people's TiddlyWikis:
								- Advanced Search > Filter > [list[$:/StoryList]] -$:/AdvancedSearch
								- (or click the down arrow next to it and select "All Tiddlers in the story river") then click the export button next down the down arrow
								- In your own TW click the Import tool
							- Contents
								- Use the 'list' field for sorting the order of the parent topic Tiddlers
								- At each level, the tiddlers can be ordered by means of the list field of the parent tag tiddler.
								- They can also be ordered by the macro's sort parameter.
								  e.g. <<toc-selective-expandable 'Contents' sort[title]>>
								- Each parent topic must be tagged 'Contents'
								- Each child topic must be tagged with the parent topic name
								- To create topics which are not openable Tiddlers (they are just section leaders):
									- To obtain this effect, in the tiddler,create a field: toc-link
									- Give the field a value of: no
									- That will tell TiddlyWiki that clicking on that Table of Contents link does not open that tiddler.
								- Add a tag as a parent topic
									- <<toc-selective-expandable "calendar">>
									  e.g. for calendar tag
								- Applying sorting
									- <<toc-selective-expandable tag:"TableOfContents" sort:"sort[title]">>
									- Applying different sorting to different subbranches
									  https://00ss.github.io/help/Adding-a-table-of-contents-to-the-sidebar.html#How%20to%20change%20the%20sort%20order%20of%20sub-branches%20in%20a%20TOC%20macro
								- {Archive}
									- https://youtu.be/bu7JU4DjPrg
									- https://00ss.github.io/help/Adding-a-table-of-contents-to-the-sidebar.html
						- Features
						  collapsed:: true
							- Checklist
							  https://tiddlywiki.com/#TaskManagementExample%20(Draggable)
							- Permalinks and "permaviews" (permalink to all current Tiddlers open)
							- Supported filetypes for links (and some embeds?)
							  https://tiddlywiki.com/#ContentType
							- How to embed
								- https://tiddlywiki.com/#TiddlyWiki%20on%20Node.js
						- Themes
						  collapsed:: true
							- http://127.0.0.1:8088/#ToDo
							- Mobile oriented
								- http://tw5mobile.tiddlyspot.com/
							- http://j.d.mono.tiddlyspot.com/
						- Plugins
						  collapsed:: true
							- _Meta_
								- How to install
									- Drag-and-drop buttons are available on many plugins. Drag it to the tab, then onto the TiddlyWiki page and it'll show a green bar in the page header. Drop there and it'll import
							- Krystal - open two Tiddlers side-by-side, move toolbar to header, bidirectional backlinks at bottom of each tiddler; option to maximise tiddler width
								- [https://crazko.github.io/krystal/](https://crazko.github.io/krystal/)
								- [https://github.com/crazko/krystal](https://github.com/crazko/krystal)
								- bi-directional links at the bottom of each tiddler
								- Customizable Header instead of sidebar
								- edit/view Toolbar option to maximize tiddler width
							- WorkFlowy-like
								- Streams plugin
								  Test TiddlyWiki [http://127.0.0.1:8191/#](http://127.0.0.1:8191/#)
									- [https://github.com/saqimtiaz/streams](https://github.com/saqimtiaz/streams)
									- [https://saqimtiaz.github.io/sq-tw/streams.html](https://saqimtiaz.github.io/sq-tw/streams.html)
									- Streams and Stories [https://trisaster.github.io/](https://trisaster.github.io/)
								- NotoWritey [https://marxsal.github.io/various/notowritey.html](https://marxsal.github.io/various/notowritey.html)
							- Roam Research-like
								- TiddlyRoam
								  [https://joekroese.github.io/tiddlyroam/](https://joekroese.github.io/tiddlyroam/)<a href="https://joekroese.github.io/tiddlyroam/">
								  </a><a href="https://tiddlyroam.org">https://tiddlyroam.org</a><a href="https://joekroese.github.io/tiddlyroam/">
								  </a>
									- 1 Backlink
										- See [TiddlyRoam ](https://workflowy.com/#/d8aaf19ad03a)
								- Stroll [https://giffmex.org/stroll/stroll.html](https://giffmex.org/stroll/stroll.html)
								- TiddlyResearch [https://github.com/kebifurai/TiddlyResearch](https://github.com/kebifurai/TiddlyResearch)
							- TiddlyRemember - easily adding tiddler content into Anki
							  [https://11263871772771252203.googlegroups.com/attach/9cb17793be44/syntax.png?part=0.1&view=1&vt=ANaJVrF5RiLbbSiKh88b4P0jOSwXyloY-qjLmcvHLYsOkuWGiKigJgUnHCcf1CTX7FaldQc1Kkdxn_XOgCe4Syxryqqyl3wU9XT5Nqm0Ekov5qt-gmNUgR0](https://11263871772771252203.googlegroups.com/attach/9cb17793be44/syntax.png?part=0.1&view=1&vt=ANaJVrF5RiLbbSiKh88b4P0jOSwXyloY-qjLmcvHLYsOkuWGiKigJgUnHCcf1CTX7FaldQc1Kkdxn_XOgCe4Syxryqqyl3wU9XT5Nqm0Ekov5qt-gmNUgR0)
								- [https://groups.google.com/g/tiddlywiki/c/UD6VyV_r-94?pli=1](https://groups.google.com/g/tiddlywiki/c/UD6VyV_r-94?pli=1)
								- [https://sobjornstad.github.io/TiddlyRemember/#Question-and-answer%20notes](https://sobjornstad.github.io/TiddlyRemember/#Question-and-answer%20notes)
							- Dynamic Tables - columns or rows can be Tiddlers
								- [http://ooktech.com/jed/ExampleWikis/DynamicTables/](http://ooktech.com/jed/ExampleWikis/DynamicTables/)
							-
							- Timimi - browser extension that allows saving/backing up standalone tiddlywiki files
								- https://github.com/ibnishak/Timimi
								- https://ibnishak.github.io/Timimi/
								- Timimi is a browser extension that allows user to save standalone tiddlywiki files. In addition, Timimi also provides ability to backup the tiddlywiki files to a path of user's choice.
							- Cardo - project management
								- [source] https://www.reddit.com/r/TiddlyWiki5/comments/adqlhv/cardo_a_task_and_project_management_wiki_for/
							- Version control
								- TiddlyGit
								  [https://www.reddit.com/r/TiddlyWiki5/comments/huhler/tiddlygit_new_desktop_app_for_tiddlywiki_with/](https://www.reddit.com/r/TiddlyWiki5/comments/huhler/tiddlygit_new_desktop_app_for_tiddlywiki_with/)
								- http://malsandbox.tiddlyspot.com/#Simple%20Tiddler%20Version%20Control
							- Locator - better search
								- https://bimlas.gitlab.io/tw5-locator/
							- TWRocketDock - opens that Tiddler in a new window basically
								- http://rocketdock.tiddlyspot.com/
							- RichLinks - embeds for HTTP tweets, audio, jsfiddle, video, pdf, youtube, txt files
								- Also has better buttons for GitHub links, Wikipedia
								- http://richlinks.tiddlyspot.com/#About
							- TiddlyMap
							  Concept-mapping - visually show interlinking via tags + custom links
								- http://tiddlymap.org/
							- twproxy
							  Web access requires login user/pass
								- https://github.com/stevenleeg/twproxy
							- Markdown
								- https://tiddlywiki.com/plugins/tiddlywiki/markdown
							- Encrypt individual Tiddlers (encrypt all already possible
								- https://github.com/danielo515/TW5-EncryptTiddlerPlugin
							- Checkboxes for adding/removing tags and fields (e.g. complete, status etc)
								- http://toggle-in-field.tiddlyspot.com
							- uni-link - create aliases for links
								- https://wikilabs.github.io/editions/uni-link/
							- Assorted scripts
								- Demo: https://kookma.github.io/TW-Scripts/
								- Source: https://github.com/kookma/TW-Scripts
						- More
							- http://tiddlyvault.tiddlyspot.com/
							- TW toolmap (3rd party)
							  intralink1:: https://dynalist.io/d/zUP-nIWu2FFoXH-oM7L7d9DM
					- Trillium Notes
					  collapsed:: true
						- https://raw.githubusercontent.com/wiki/zadam/trilium/images/screenshot.png
						- [https://github.com/zadam/trilium](https://github.com/zadam/trilium)
						- Screenshot tour
						  https://github.com/zadam/trilium/wiki/Screenshot-tour
						- Pros/Cons
							- Pros
								- Can be self-hosted and accessible via web app or desktop
								  https://github.com/zadam/trilium/wiki/Server-installation
								- Like Standard Notes you can encrypt all text content
								- Cloning so docs appear in multiple places in folder tree
								- Note attributes can be used for note organization, querying and advanced scripting
								- Encryption has per-note granularity if desired
							- Cons
								- Lacks
									- Tables with filtering and sorting
									  https://github.com/zadam/trilium/issues/410
									- Multi-user collaboration
									  https://github.com/zadam/trilium/issues/347
									- Support OPML import
									  https://github.com/zadam/trilium/issues/286
									- Create WebClipper browser extension
									  https://github.com/zadam/trilium/issues/202
									- Mobile apps
									- CalDAV support
									  https://github.com/zadam/trilium/issues/242
								- Waiting on CKeditor to add
									- Mentions/autocomplete
									  https://github.com/ckeditor/ckeditor5/issues/998
										- Interlinks
										  https://github.com/zadam/trilium/issues/281
									- Code blocks (note: full code page alread
									  https://github.com/ckeditor/ckeditor5/issues/436
					- Turtl
					  collapsed:: true
						- https://turtl.it/
					- Laverna
					  collapsed:: true
						- Client-side encryption
						- Data is stored locally
						- remoteStorage + Dropbox available
							- Only supports Dropbox sync currently
							  https://github.com/Laverna/laverna/issues/6
					- Experimental realtime collaborative editor by Standard Notes
					  collapsed:: true
						- https://github.com/standardnotes/collab-editor
						- Built on Chainpad (same as CryptPad) and CodeMirror)
					- Cryptee
					  id:: 687014b9-dbcb-459d-a0aa-bb9f970df405
					  collapsed:: true
						- Only front-end is FOSS atm https://cdn-images-1.medium.com/max/1200/1*8EX1AGBiW60MICtVGDZC5w.png
						- [https://crypt.ee/](https://crypt.ee/)
						- Screenshots
						  https://crypt.ee/imgs/docs2.jpg
							- https://cdn-images-1.medium.com/max/1200/1*8EX1AGBiW60MICtVGDZC5w.png
						- Pros/Cons
							- _Features_
								- Interlink files - documents can have inline links to PDFs and other attachments
								- Deniable encryption even (Ghost Folders)
								- Inline tagging
								- Cryptee has ghost folders - requires the name of the folder to show it again
								  https://www.reddit.com/r/privacytoolsIO/comments/8t1oqz/a_new_privacy_tool_ive_been_building_for_15_years/
									- [cloned] [https://github.com/cryptee/web-client](https://github.com/cryptee/web-client)
									- Cryptee is a cross-platform, zero-knowledge, client-side AES256 encrypted, Documents and Photos application/service. It's meant as a secure and private alternative for Evernote/Bearnote & Google / Amazon Photos.
										- Cryptee Documents / Notes
										- Cryptee Photos
									- What about rubber-hose cryptanalysis!? (deniable encryption)
										- The feature I've spent the most time crafting is Ghost Folders. Both Documents and Photos has this. It essentially allows you to hide folders completely, and only be able to "summon" them (bring them back) if you know their names. I think that this is going to be a great tool to fight power asymmetry in many different situations. (such as an abusive partner asking you to unlock your phone in front of them, or at work where you wish for others not to see certain folders / albums. etc.) I hope that this feature will provide some plausible deniability.
									- 1 Backlink
										- See [Cryptee has ghost folders - requires the name of the folder to show it again](https://workflowy.com/#/d77761342133)
							- _Lacks_
								- Closed-source backend, and author is unlikely to change
								  https://github.com/cryptee/web-client/issues/10#issuecomment-458327612
								- Does it support a full Markdown-like export?
								  intralink2:: https://workflowy.com/#/4ed86ce64fff
						- See [Cryptee](https://workflowy.com/#/650b211c47ba)<a href="https://workflowy.com/#/650b211c47ba"> has ghost folders - requires the name of the folder to show it again</a>
						- 4 Backlinks
							- See [Cryptee](https://workflowy.com/#/fb3f99e991f8)
							- See [Cryptee](https://workflowy.com/#/fb3f99e991f8)
							- **[PC file viewer] **document-based i.e. future: TagSpaces, Notion, Outline, Standard Notes, [Cryptee](https://workflowy.com/#/fb3f99e991f8), Filestash #001-type:utility #001-type:privacy #001-p1
							  See [Open-source](https://workflowy.com/#/f3d9675f8512) <a href="https://workflowy.com/#/1f3c09bb3ccf">Document-based</a>
							- See [Cryptee](https://workflowy.com/#/fb3f99e991f8)
				- Interactive coding notebooks
				  collapsed:: true
					- Features to replicate
					  See desired features [Desired features](https://workflowy.com/#/4ed86ce64fff)
					- [Jupyter](http://jupyter.org/)
					  id:: 687014b9-a5fe-4f00-96d4-4c946c994158
					  collapsed:: true
					  (40+ languages)
						- Pros/Cons
							- Cons
								- Requires a server component
						- Python-oriented, but now supports many kernels (languages supported)
						  https://github.com/jupyter/jupyter/wiki/Jupyter-kernels
							- JavaScript-bassd
								- https://github.com/n-riesco/ijavascript
								- https://github.com/nearbydelta/itypescript
								- [https://github.com/notablemind/jupyter-nodejs](https://github.com/notablemind/jupyter-nodejs)
								- _Related:_ [Starboard Jupystar (Jupyter support in-browser)](https://workflowy.com/#/77f262b007b4)
						- # Platforms
							- Jupyter Notebook (desktop) (being deprecated)
							- JupyterLab (web)
							  id:: 63045aef-5dca-4ab6-92b7-613e2f09c4b5
							  collapsed:: true
								- Pros/Cons
									- Pros
										- Collaborative editing in beta
										  [https://github.com/jupyterlab/jupyterlab/issues/5382#issuecomment-836931023](https://github.com/jupyterlab/jupyterlab/issues/5382#issuecomment-836931023)
										- [https://github.com/krassowski/](https://github.com/krassowski/jupyterlab-lsp)<a href="https://github.com/krassowski/jupyterlab-lsp">jupyter</a><a href="https://github.com/krassowski/jupyterlab-lsp">lab-lsp</a>
										- Can drag and drop tabs to make it use e.g. four quarters of screen
										  [https://miro.medium.com/max/700/1*kbx-4oQwUDLP6ufI2ABrNA.gif](https://miro.medium.com/max/700/1*kbx-4oQwUDLP6ufI2ABrNA.gif)
									- Cons
										- Lacks
											- **No full-text search (can only search within one file at a time)**
											  [https://github.com/jupyterlab/jupyterlab/issues/1145#issuecomment-881592024](https://github.com/jupyterlab/jupyterlab/issues/1145#issuecomment-881592024)
												- [https://discourse.jupyter.org/t/jupyter-lab-search-notebooks/8590](https://discourse.jupyter.org/t/jupyter-lab-search-notebooks/8590)
												- [https://discourse.jupyter.org/t/how-do-you-search-a-folder-for-all-instances-of-a-keyword/10610](https://discourse.jupyter.org/t/how-do-you-search-a-folder-for-all-instances-of-a-keyword/10610)
											- Commenting like Google Docs
											  [https://github.com/jupyterlab/jupyterlab/issues/9885#ref-issue-790190353](https://github.com/jupyterlab/jupyterlab/issues/9885#ref-issue-790190353)
											- Desktop app
											  [https://github.com/jupyterlab/jupyterlab_app/issues/186](https://github.com/jupyterlab/jupyterlab_app/issues/186)
											- grep for searching across all files
											  [https://github.com/jupyterlab/jupyterlab/issues/1145#ref-issue-790190353](https://github.com/jupyterlab/jupyterlab/issues/1145#ref-issue-790190353)
								- Links
									- [https://github.com/jupyterlab/jupyterlab](https://github.com/jupyterlab/jupyterlab)
								- Documentation
								  [https://jupyterlab.readthedocs.io/en/stable/](https://jupyterlab.readthedocs.io/en/stable/)
									- If adding it to Yakuake
										- addSession "JupyterLab" "jupyter-lab"
									- _What_
										- Next-generation web-based interface for Project Jupyter, will replace Python-based Jupyter Notebook
									- _Usage_
										- Try in-browser
										  [https://jupyter.org/try](https://jupyter.org/try)
										- Install
										  [https://jupyter.org/install.html](https://jupyter.org/install.html)
											- pip3 install jupyterlab
										- Running (in Yakuake)
										  jupyter-lab
										- Open webpage to my "snippets"
										  `http://localhost:8888/lab/tree/Documents/Git/1MY%20REPOS/snippets`
									- Setup
										- Password enabled (means I don't have to use a token URL to access Jupyter via any browser)
										  [https://jupyter-server.readthedocs.io/en/latest/operators/public-server.html](https://jupyter-server.readthedocs.io/en/latest/operators/public-server.html)
										- _Kernels_
										  [https://github.com/jupyter/jupyter/wiki/Jupyter-kernels](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels)
											- IPython kernel (pre-installed)
											- IJavaScript
											  [https://github.com/n-riesco/ijavascript](https://github.com/n-riesco/ijavascript)
												- Installation
												  [https://github.com/n-riesco/ijavascript#ubuntu](https://github.com/n-riesco/ijavascript#ubuntu)
													- Install ((629ccb26-3115-4d41-b4db-a686fe51a4a2))
													  `sudo apt install nodejs`
													- Install npm
													  sudo apt install npm
													- Next
														- npm config set prefix $HOME
														- npm install -g ijavascript
														- ijsinstall
												- 1 Backlink
													- ITypeScript ([IJavaScript](https://workflowy.com/#/575dc8d582ad) fork)
													  [https://github.com/winnekes/itypescript](https://github.com/winnekes/itypescript)
											- ITypeScript ([IJavaScript](https://workflowy.com/#/575dc8d582ad) fork)
											  [https://github.com/winnekes/itypescript](https://github.com/winnekes/itypescript)
									- Features
										- Drag-and-drop to reorder notebook cells and copy them between notebooks.
										- Run code blocks interactively from text files (.py, .R, .md, .tex, etc.).
										- Link a code console to a notebook kernel to explore code interactively without cluttering up the notebook with temporary scratch work.
										- Edit popular file formats with live preview, such as Markdown, JSON, CSV, Vega, VegaLite, and more.
										- _Minor_
											- Many files types have multiple viewers/editors. For example, you can open a Markdown file in a text editor or as rendered HTML. A JupyterLab extension can also add new viewers/editors for files. To open a file in a non-default viewer/editor, right-click on its name in the file browser and use the “Open With…” submenu to select the viewer/editor
											- Right-click on a file or directory and select “Copy Shareable Link” to copy a URL that can be used to open JupyterLab with that file or directory open.
									- [https://jupyterlab.readthedocs.io/en/stable/](https://jupyterlab.readthedocs.io/en/stable/)
									- [https://towardsdatascience.com/jupyter-lab-evolution-of-the-jupyter-notebook-5297cacde6b](https://towardsdatascience.com/jupyter-lab-evolution-of-the-jupyter-notebook-5297cacde6b#c8dd)
									- Tutorials
										- [https://youtu.be/A5YyoCKxEOU](https://youtu.be/A5YyoCKxEOU)
								- Plugins
									- GitPlus - create GitHub commits & pull requests via it
									  [https://www.reviewnb.com/](https://www.reviewnb.com/)
										- [https://github.com/ReviewNB/jupyterlab-gitplus](https://github.com/ReviewNB/jupyterlab-gitplus)
									- Abandoned
										- jyve plugin - allows running Python, JavaScript etc within JupyterLab
											- [https://github.com/deathbeds/jyve](https://github.com/deathbeds/jyve)
								- _Related:_
									- [Starboard Jupystar (Jupyter support in-browser)](https://workflowy.com/#/77f262b007b4)
								- 2 Backlinks
									- Consider using [JupyterLab](https://workflowy.com/#/0bde8b1fb150) or possibly <a href="https://workflowy.com/#/f97690c4f189">Observab</a><a href="https://workflowy.com/#/f97690c4f189">le Notebooks</a> for code notes, snippets or projects. JupyterLab however still doesn't have full-text search when last checked in 2021
									- [JupyterLab (web)](https://workflowy.com/#/0bde8b1fb150) is almost as quick to get started with, however is far more comprehensive
							- ((66cba586-76d4-45bb-ad94-b5cb76e10366))
						- # Ecosystem
							- [Jupyter Book](https://jupyterbook.org/en/stable/intro.html)
							- [JupyterLite](https://github.com/jupyterlite/jupyterlite) - web version
							  id:: 66cba586-76d4-45bb-ad94-b5cb76e10366
							- ## Code editor support
								- ((63209272-1088-4824-a762-4ac7ded04b0a))
								- Zed
						- Could build all sorts of interactive components like Coda, Airtable Blocks etc
						- Sharing with others
						  collapsed:: true
							- You can turn jupyter notebooks into pdfs directly in the jupyter UI.
							- You can upload them to Gitlab/Github and share the link to the rendered result.
							- You can upload them to Colab/Binder/Kaggle and let people play with the code themselves.
							- You can turn jupyter notebooks into beautiful websites/documents with: https://quarto.org/docs/tools/jupyter-lab.html
							- You can add jupyter notebooks to you docs using nbsphinx: https://nbsphinx.readthedocs.io/en/0.9.1/
							- You can turn jupyter notebooks into interactive web apps with voila: https://github.com/voila-dashboards/voila
							- You can turn jupyter notebooks into presentations with rise: https://github.com/voila-dashboards/voila
							- Notebooker ([https://github.com/man-group/notebooker](https://github.com/man-group/notebooker)) is a neat way of scheduling your Jupyter notebooks as parametrisable reports whose results are presented in a little web GUI (either as static HTML, PDF, or as reveal.js slideshow renders)
							- While I have no need for its online functionality and the SAAS part of plotly, I really do like plotly python + [cufflinks](https://github.com/santosjorge/cufflinks) [1]. It lets you make interactive plots in html/js format. Which means you can save the notebook as html, and while people won't be able to rerun the code, they can still zoom in on graphs, hover to see annotations etc, which is a really nice way to share the outcome of your work in a more accessible way.
								- If you're interested in an easier way to create reports using Python and Plotly/Pandas, you should check out our open-source library, Datapane: [GitHub - datapane/datapane: Build full-stack data apps in 100% Python](https://github.com/datapane/datapane) - you can create a standalone, redistributable HTML file in a few lines of Python.
						- [Learning Resources]
							- [JupyterLab 4.0 | Hacker News](https://news.ycombinator.com/item?id=36315796)
							-
					- BeakerX
					  collapsed:: true
						- https://github.com/twosigma/beakerx
					- nteract
					  collapsed:: true
						- https://nteract.io/
					- _JavaScript-oriented_
					  collapsed:: true
						- Starboard Notebook
							- [https://starboard.gg/](https://starboard.gg/)
							- [https://github.com/gzuidhof/starboard-notebook](https://github.com/gzuidhof/starboard-notebook)
							- Pros/Cons
								- Pros
									- It's probably the quickest way to visualize some data with interactivity, do some prototyping, or build a rudimentary dashboard.
									- Mix Markdown, HTML, CSS and Javascript.
									- The file format is a plaintext file, which plays nice with version control systems like git.
									- Runs entirely in your browser, everything is static: no server, no setup and no build step.
									- Keyboard shortcuts
										- You can use ⌘+S (macOS) or ctrl+S (windows) to save a plain text markdown file
									- Open source (fully?)
									- Works on mobile devices
									- Browser-native: there is no bridge required between the server and the browser like in Jupyter notebook as everything is in-browser. This means that you can share the URL to your notebook and it will just work. Starboard is built around browser standards (i.e. there is no widget system: it's HTML elements).
									- Zero-setup: Create a new notebook with one click in your browser, there is zero setup and you don't need a server running to serve your notebook. Everything is a static file.
									- Portable:
										- Some notebook systems are walled gardens or don't play nice with version control. Starboard notebooks are stored on disk as plaintext files for maximum portability. You can check them in to Git, embed the notebook on your blog, export a static website, or even auto-generate notebook reports.
									- Hackable: Different than any other notebook system the Starboard editor itself runs inside the sandbox. The code you write in the notebook can alter the notebook itself: you can dynamically create new cell types, change the CSS styles, or anything really.
									- Starboard Jupystar (Jupyter support in-browser)
									  [https://starboard.gg/jupystar](https://starboard.gg/jupystar)
										-
								- Cons
									- [JupyterLab (web)](https://workflowy.com/#/0bde8b1fb150) is almost as quick to get started with, however is far more comprehensive
									- When is Starboard not a good choice?
										- Large web applications: notebooks are inherently single files. While you can import from other files, it will still become unmanagable. Notebooks are great for prototyping, but you will want to graduate to a proper web app at some point. As Starboard notebooks are just Javascript, it should be pretty straightforward.
										- Long-running computations or very large datasets: To visualize or use data in the browser, you will have to load it into the browser. For long-running computations I suggest that you don't use notebooks at all but use a dedicated script using a suitable programming language (e.g. Python).
										- Old-browser support: Starboard uses new browser tech (especially important is [dynamic import](https://caniuse.com/#feat=es6-module-dynamic-import) support). If you need to support Internet Explorer look elsewhere.
									- Usses %% instead of ``` for code blocks
										- [https://github.com/gzuidhof/starboard-notebook/issues/2](https://github.com/gzuidhof/starboard-notebook/issues/2)
										- Fork which uses ```
										  [https://github.com/Sheraff/notebooks](https://github.com/Sheraff/notebooks)
							- Starboard vs Starboard Notebook
								- It can be confusing as these terms are used interchangeably.
								- Starboard Notebook is the actual notebook runtime with the editor (the code cells, outputs and buttons).
								- This website, Starboard, embeds this editor and allows you to save and share notebooks (allowing you to share by just a link) and will in the future have some social features (stars, upvotes, followers, ...). Think of it as a publishing platform for your notebooks.
								- A somewhat correct analogy: If Starboard was GitHub, Starboard Notebook would be Git.
							- Create offline-only notebooks here (stored in browser cache)
							  [https://starboard.gg/dashboard/new](https://starboard.gg/dashboard/new)
							- Demo
							  [https://sheraff.github.io/notebooks/?file=1%20-%20demo.md](https://sheraff.github.io/notebooks/?file=1%20-%20demo.md)
						- Observable Notebooks
						  id:: 6350385e-9cfe-43b2-8412-b34a3b25f964
							- Pros/Cons
								- Pros
									- Basically Jupyter but built for JavaScript
									- Mostly open-source
										- they released their runtime, their parser, their standard library and all sorts of other stuff through [https://github.com/observablehq](https://github.com/observablehq)
								- Cons
									- editor component itself is closed-source and only available on [https://observablehq.com/](https://observablehq.com/), though you can use <a href="https://workflowy.com/#/535be1a7a939">Dataflow</a> instead
									- Runs a bit differently from JavaScript
									  [https://observablehq.com/@observablehq/observables-not-javascript](https://observablehq.com/@observablehq/observables-not-javascript)
							- [https://yewtu.be/channel/UCCD2tAKN32ya7V639gkbWhg](https://yewtu.be/channel/UCCD2tAKN32ya7V639gkbWhg)
							- Ecosystem
								- Dataflow - FOSS self-hosted editor
									- Pros/Cons
										- Pros
											- Plus, Dataflow has some great ideas of its own - in particular the live file attachments thing.
										- Cons
											- the hosted Observable editor has collaboration features that don't even make sense for a local running version.
									- Dataflow is a new tool that lets you run, edit, and compile Observable notebooks locally on your own computer, with any text editor you want!
									- [https://observablehq.com/@asg017/introducing-dataflow](https://observablehq.com/@asg017/introducing-dataflow)
									- [https://alexgarcia.xyz/dataflow/#introduction](https://alexgarcia.xyz/dataflow/#introduction)
									- [https://github.com/asg017/dataflow](https://github.com/asg017/dataflow)
									- 1 Backlink
										- editor component itself is closed-source and only available on [https://observablehq.com/](https://observablehq.com/), though you can use <a href="https://workflowy.com/#/535be1a7a939">Dataflow</a> instead
							- 1 Backlink
								- Consider using [JupyterLab](https://workflowy.com/#/0bde8b1fb150) or possibly <a href="https://workflowy.com/#/f97690c4f189">Observab</a><a href="https://workflowy.com/#/f97690c4f189">le Notebooks</a> for code notes, snippets or projects. JupyterLab however still doesn't have full-text search when last checked in 2021
						- Iodide Notebook (by Mozilla)
							- [https://alpha.iodide.io/](https://alpha.iodide.io/)
							- https://github.com/iodide-project/iodide
							- JSMD, short for JavaScript MarkDown, is the file format that Iodide notebooks are written in.
							  https://iodide-project.github.io/docs/jsmd/
								- It is simply a collection of contents in different languages, separated by lines that start with %% and indicate the language of the chunk below.
								- Easier to understand for both humans and computers than Jupyter JSON files
							- Lacks
								- Language Server protocol support (allows TypeScript etc)
								  https://github.com/iodide-project/iodide/issues/804
									- https://langserver.org/
						- Kajero
							- Markdown files with code blocks
							- Code blocks can be set to run automatically when the notebook loads. They can also be set to hidden, so that only the result is visible.
							- https://github.com/JoelOtter/kajero
					- _Related:_ [Deepnote](https://workflowy.com/#/d18c68739856)
				- _Rich Text Editors (WYSIWYG)_
					- _Toolkits - editor only, no folder system_
					  collapsed:: true
						- ProseMirror (used by Nuclino, Atlassian)
						  collapsed:: true
						  Aiming for a bigger featureset than Quill
							- http://prosemirror.net/
							- https://github.com/prosemirror/
							- CodeMirror (1st project by CodeMirror team)
								- https://github.com/codemirror/codemirror
						- TOAST UI Editor (used by Dooray)
						  collapsed:: true
							- https://github.com/nhnent/tui.editor/
							- Features
								- Markdown
								- Markdown-like syntax to render colour palette, flowcharts, bar charts
								- , tables, synax highlighting
							- _Future_
								- Emoji
								  https://github.com/nhnent/tui.editor/issues/276
								- Mentions
								  https://github.com/nhnent/tui.editor/issues/170
						- EditorJS (block-based like Notion)
						  collapsed:: true
							- https://github.com/codex-team/editor.js
							- Works on mobile (like Quill, Prosemirror)
							- Does not support collaborative editing (unlike Quill, Prosemirror)
							- Has somewhat unique block-based editing UI - think Notion (the data models of most editors support this, but the default UI of editorjs is much more explicit about this)
							- Not built on React (like Quill, Prosemirror, but unlike Slate and Draft)
						- https://alex-d.github.io/Trumbowyg/
						- https://github.com/bevacqua/woofmark
						- Quill (used by Slab, Slack, LinkedIn, SalesForce etc)
						  collapsed:: true
							- Pros/Cons
								- Pretty basic
								- Lacks
									- Tables coming in v2.0
							- Links
								- https://quilljs.com/
								- https://github.com/quilljs/quill/
							- https://github.com/quilljs/awesome-quill
							- Playground
							  https://quilljs.com/playground/
						- Slate (used by Outline)
						  collapsed:: true
						  https://cdn-images-1.medium.com/max/2000/1*DQIAfHsHRTYG71v8Wwcghg.gif
							- https://github.com/ianstormtaylor/slate
							- Many plugins
								- Suggestions (could be used for mentions, tags etc)
								  https://www.npmjs.com/package/slate-suggestions
								- https://github.com/ianstormtaylor/slate/blob/master/docs/general/plugins.md
						- [archived] https://github.com/iDoRecall/comparisons/blob/master/JavaScript-WYSIWYG-editors.md
					- Bangle (markdown-based, local files, nice UI)
					  collapsed:: true
						- [https://bangle.io/](https://bangle.io/)
						- [https://github.com/bangle-io/bangle-io](https://github.com/bangle-io/bangle-io)
					- ((635eb27e-7770-4aa4-96a8-093c6dd9691d))
					- ((653f787b-5cf5-4864-817f-404d861bc1cc))
					- Zettlr
					  collapsed:: true
						- [https://docs.zettlr.com/en/academic/zkn-method/](https://docs.zettlr.com/en/academic/zkn-method/)
						- [https://zettlr.com](https://docs.zettlr.com/en/academic/zkn-method/)
					- [TagSpaces](http://www.tagspaces.org)
					  id:: 66390660-37dd-4f25-892e-becd3c0c8a1b
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Cryptomator support
								- Use HTML files like Evernote. Drag and drop images to embed them
								- Some features in Pro version https://www.tagspaces.org/products/
									- Full text search for txt, MD, HTML
									- Keeping files on a remote S3 folder (plus S3 compatible APIs like Minio and Digital Ocean Spaces)
								- Unique
									- Mapique perspective allows seeing files sorted by location metadata (e.g. photos taken)
									  [https://www.tagspaces.org/blog/tagspaces-3-3-released/](https://www.tagspaces.org/blog/tagspaces-3-3-released/)
								- New
									- added support for picture-in-picture (PIP) playing mode in the media player
									- Mobile optimisation
									- Intralink HTML and MD files
									- Unique URL per file now (on web version, but [Web app is £125.00/3 users/year](https://workflowy.com/#/fbc47f5bb088))
									  [https://github.com/tagspaces/tagspaces/issues/898](https://github.com/tagspaces/tagspaces/issues/898)
							- Cons
								- Web app is £125.00/3 users/year
								- Bugs
									- [Startup location is ignored and get started tutorial reappears · Issue #2389 · tagspaces/tagspaces · GitHub](https://github.com/tagspaces/tagspaces/issues/2389)
									  id:: 6921d634-b1ea-4dc2-80da-797949fb104e
								- _Lacks_
									- _Upcoming_
										- Notifications based on reminder tags
										- Hierarchical tag groups
										  https://trello.com/c/1Rt4y95j/50-ability-to-add-tag-to-tag-group-from-tag-options-menu-accessed-by-right-click-on-tag
									- OCR for images eg receipts
									- _Extended markdown features_
									- Android
										- Better markdown editor
										  https://trello.com/c/OzGOEFxo/13-ts337-better-dedicated-markdown-editor
											- Based on http://prosemirror.net/examples/markdown/
						- _View progress_
							- Changelog
							  https://github.com/tagspaces/tagspaces/blob/master/CHANGELOG.md
							- Whats new - last checked  3.6.2
							  http://www.tagspaces.org/whatsnew/
							- [https://www.tagspaces.org/blog/tagspaces-3-0/](https://www.tagspaces.org/blog/tagspaces-3-0/)
						- old notes
							- Local-only (on PC+HDD)
							- Functions
								- First-line inbox primarily and when processed into SOPs moved into #WorkFlowy
								- Firefox web clipper extension allows easy importing
								- Replaced with
									- Save page as as MHT/MAFF
										- Mozilla Archive Format - all web elements in an open format eg video, audio, multiple tabs, http://maf.mozdev.org/maff-file-format.html
							- Multimedia Viewer and Tag-Based Organisation
								- Already use WorkFlowy as my main hierarchical organisation
								- After moving from unencrypted Evernote I was going to go with ownCloud for viewing several filetypes and ONLYOFFICE for realtime editing ODT+ODS files
								- TagSpaces is much better suited a system as it's beta (lots of rooms for improvement) and handles much more filetypes
							- Preview 50+ different file types and edit several
								- Images (PNG, BMP, JPG, GIF), Videos and Audio (MP3, OGG), MP4, ZIP,, Documents (PDF, MHT, HTML, MD)
								- Edit - TXT, MD, HTML
								- http://www.tagspaces.org/supported-file-formats/
							- Web Clipper like Evernote
								- To capture whole webpage as MHTML
								- To save the selection from a webpage in HTML format
								- To take screenshot of the visibale part of the current webpage as PNG
							- Self-hosted version
								- + WebDAV / Server Edition http://www.tagspaces.org/webdav-edition/
								- Connection via WebDAV interface to ownCloud or ((644c0b1b-7682-4b57-a600-be7b7a4140ad)) server
								- Restriction: TagSpaces should be located on the same server as the WebDAV server
					- [Outline](https://www.getoutline.com) (built on Slate)
					  collapsed:: true
						- _Links_
							- [https://www.getoutline.com](https://www.getoutline.com)
							- [https://github.com/outline/outline](https://github.com/outline/outline)
							- https://www.getoutline.com/changelog
								- Last checked: Sun, Sep 27, 2020
								- New features
									- Embeds are now supported for Google Docs, Slides, and Sheets
							- Roadmap
							  https://www.getoutline.com/share/3e6cb2b5-d68b-4ad8-8900-062476820311
						- Test playground
						  https://cryptodash.getoutline.com/dashboard
						- Pros/Cons
							- Pros
								- Self-hosted possible
								- Numerous integrations including Zapier, Airtable, GitHub, Vimeo, Codepen
								  https://www.getoutline.com/integrations
								- Code blocks with code highlighting
								  https://www.getoutline.com/screenshot@2x.png
								- Document revision history
								- Export all data
									- We added the ability to export all your data out of Outline. There's a new tab under settings "Export Data" and a new option to export all documents for a collection in the overflow menu.
									- Lacks document history currently
									  https://github.com/hackmdio/codimd/issues/823#issuecomment-399775890
								- API
								- Supports S3 and possibly Minio (self-hosted) for inline images
								- Backlinks shown at bottom of the page
							- Cons
								- Authentication requires Slack or GSuite user
								  https://github.com/outline/outline/issues/862
									- It's designed for teams, Google auth is used to avoid having to manage invites etc. If you could sign in with any old Google account then it would introduce a class of problems with having to manage invites / user management / accidental duplicate teams.
									- Having said that, I do think it would be cool if signing in with your personal gmail account gave you a personal non-team wiki.
								- _Lacks_
									- Very few types of blocks/formatting possible at the moment (only Markdown spec + checkboxes)
									  http://i.imgur.com/oYXzrhK.png
										- Lacks file attachments (ideally FileSafe E2EE/WebDAV)
										  [https://github.com/outline/outline/issues/859](https://github.com/outline/outline/issues/859)
										- Table support v3 (advanced data manipulation)
											- _See Notion_
											  intralink2:: https://workflowy.com/#/3c64e7841d9d
											- Sort by multiple columns
											  http://i.imgur.com/a5wCj6g.png
											- Properties - Filter out particular columns
											  http://i.imgur.com/3cWXGzy.png
											- Filter out particular values (font colour changes to blue when a filter is active)
											  http://i.imgur.com/O2y0jt8.png
										- Table support v4 (database-like eg Notion/Airtable)
											- _See Notion_
											  intralink2:: https://workflowy.com/#/3c64e7841d9d
											- Open any record as a pop-up
											  http://i.imgur.com/LQUGg0C.png
											- Field types
											  http://i.imgur.com/ieWNElu.png
											- Views dropdown menu to save different manipulations of the data
											- Multiple view types eg Kanban
										- _Formatting_
											- Highlight text background with a colour, or change font colour
											- In-line comments
											  https://github.com/outline/outline/issues/457
												- Make a comment on selected text (Notion-style)
												  http://i.imgur.com/Tc8dhYp.png
											- Tags
											  https://github.com/outline/outline/issues/765
									- Hierarchical collections instead of flat-only
									- End-to-end encryption (only CryptPad has got this + real-time collab)
									- _Real-time_ collaborative editing (planned with Q2)
									  [https://github.com/outline/outline/issues/811#issuecomment-658416520](https://github.com/outline/outline/issues/811#issuecomment-658416520)
									- Tag attributes
										- https://talk.dynalist.io/t/tag-attributes/1059
									- Tables
									- Subscribe/follow document
									  https://github.com/outline/outline/issues/743
									- No mobile or desktop apps
									- Full integrations - most (all?) are just iframe/oembed
						- Built on Slate.js (WYIWYG editor)
						  https://www.slatejs.org
					- Rustpad
					  collapsed:: true
						- [https://github.com/ekzhang/rustpad](https://github.com/ekzhang/rustpad)
						- Real time collaborative text editor
					- Etherpad-Lite (Etherpad v2)
					  collapsed:: true
						- http://etherpad.org/
						-
						- New version
						  https://github.com/ether/etherpad-lite
						- Demo
						  http://beta.etherpad.org/
						- Why new version
							- Etherpad Lite is an almost complete rewrite of the original Etherpad software, based on different technical foundations and written by different authors. While the original Etherpad is written in Scala and has quite demanding system requirements, Etherpad Lite is written in server-side JavaScript using node.js (99% Javascript throughout app). The original realtime synchronization library (called Easysync) remains the same.
							- Etherpad Lite has some distinctive features which are not available in the original version:
								- An HTTP API which allows the user to interact with the pad contents, and with user and group management
								- A jQuery plugin exists which helps embedding the collaborative editor in other sites
								- Clients for PHP,[20] Python,[21] Ruby,[22] JavaScript,[23] Java,[24] Objective-C[25] and Perl[26] which interface with the API.
								- More than 50 plugins
						- Huge number of plugins
						  https://static.etherpad.org/plugins.html
							- Embed media
							  https://github.com/JohnMcLear/ep_embedmedia
							- Tables
							  https://github.com/quenenni/ep_tables2
							- email_notifications, invite_via_email, offline_edit, fileupload, tables or rtc for video calls based on WebRTC.
						- https://opensource.com/life/15/12/5-open-source-web-apps-self-hosted
						- http://i.imgur.com/5ilO14u.png
					- CodiMD
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Switch between markdown view, rendered view or split-pane
								- Image attachments via auto-upload to imgur
								- Easy import/export to multiple formats both FOSS and hosted
								- Markdown, Slideshow mode, Book mode, images, export to PDF/MD/HTML, code blocks
							- Cons
								- Lacks
									- Annotations (likely will be Hypothesis-style)
									  https://github.com/hackmdio/codimd/issues/27#issuecomment-428377245
									- Discussion/instant chat support in sidecar (likely will be Matrix/RocketChat-based)
									  https://github.com/hackmdio/codimd/issues/6
									- End-to-end encryption (possibly could use a browser extension)
									  https://github.com/hackmdio/codimd/issues/138
									- Internal links
									  https://github.com/hackmdio/codimd/issues/618#issuecomment-389329595
									- Enhanced note history (basic one implemented)
									  https://github.com/hackmdio/codimd/issues/7
						- Examples
							- https://hackmd.io/features
						- Embeddable
						  https://hackmd.io/features#embed-a-note
						- GFM Markdown for tables
						  https://help.github.com/articles/organizing-information-with-tables/
						- Potential other table rendering
							- http://www.tablesgenerator.com/
							- https://pandoc.org/MANUAL.html#tables
						- See HackMD (proprietary SaaS version)
							- CodiMD was previously named HackMD
							- CodiMD was forked to make the new HackMD Enterprise
							  https://github.com/hackmdio/codimd#hackmd-ce-became-codimd
					- Hackpad (built on Etherpad v1)
					  collapsed:: true
					  Bought+released open-source by Dropbox (basis for Dropbox Paper)
						- Hackpad is a web-based realtime wiki, based on the open source EtherPad collaborative document editor.
						- Pros
							- File versioning and reverting
							- Many features
								- Markdown
								- Tables
								- Images
								- Floating Table of Contents
								- In-line comments (right side panel)
								- In-line attribution (left side panel)
						- Examples
							- https://i.imgur.com/a7aSrc6.png
							  https://hackpad.com/How-to-use-Hackpad-mlZvEsJykI5
							- https://i.imgur.com/pwcdvds.jpg
							  https://hackpad.com/Hackpad-FAQ-tq56fI63mz3
						- Forks
							- Main
							  https://github.com/hackpad/hackpad
							- Abandoned
								- https://github.com/whackpad/whackpad
								- https://github.com/X41/hackpad
					- _Note:_ Simple HTML editors like tinyMCE don't work well
					  collapsed:: true
						- anilshanbhag on Apr 16, 2017 [-]
						- As Rosenhai mentioned, you can use any 'old' editor like Summernote or TinyMCE if you just want to edit html. The problem comes when you want to sync changes to server / others in collaborative environment. Without a state, all you see is a dom element and then you have to generate the diff which is pretty hard due to browser nuances.
						- https://medium.engineering/why-contenteditable-is-terrible-122d8a40e480?gi=cbef26f30418
				- Text file conversion
					- Pandoc
				- **Look into**
					- **GetCanvas (abandned)**
					- **stackedit.io**
				- IPFS research into CRDTs
				  collapsed:: true
					- [https://github.com/ipfs/notes/issues?q=is%3Aissue+is%3Aopen+crdt](https://github.com/ipfs/notes/issues?q=is%3Aissue+is%3Aopen+crdt)
					- [https://github.com/ipfs/notes/tree/master/CRDT](https://github.com/ipfs/notes/tree/master/CRDT)
				- _Wiki-like_
				  collapsed:: true
					- [Wiki.js](https://js.wiki/)
					  collapsed:: true
						- [https://wiki.js.org/img/wiki-screenshot.3d2d7f34.png](https://wiki.js.org/img/wiki-screenshot.3d2d7f34.png)
						- [https://wiki.js.org/](https://wiki.js.org/)
						- [https://github.com/Requarks/wiki](https://github.com/Requarks/wiki)
					- GitBook
					  collapsed:: true
						- https://github.com/GitbookIO/gitbook
						- ^ local GitBook is now deprecated, they're focusing on gitbook.com version only now (online only, and no self-hosted version available)
						- The app looks smoother and better though
						  https://docs.gitbook.com/v2-changes/feature-highlights
						- Editor is built on a fork of Slate
						  https://github.com/GitbookIO/slate-edit-table
					- BookStack
					  collapsed:: true
						- http://alternativeto.net/software/bookstack/
					- MediaWiki
					  collapsed:: true
						- Wikipedia's platform
						- Extensions
							- https://wikiapiary.com/wiki/Extension:Extensions
							- VisualEditor
							  https://www.mediawiki.org/wiki/Extension:VisualEditor
							- Collections (export as diff formats
							  https://www.mediawiki.org/wiki/Extension:Collection
							- AJAX category tree
							  https://www.mediawiki.org/wiki/Extension:CategoryTree
							- Semantic
							  https://www.semantic-mediawiki.org
					- DokuWiki
					  collapsed:: true
						- https://www.dokuwiki.org/dokuwiki#
						- No database required
						- Plugins
							- https://www.dokuwiki.org/plugins?plugintype=4&pluginsort=^c#extension__table
					- [TiddlyWiki](https://workflowy.com/#/5d5f08d3ad7b)
					- Zim
					  collapsed:: true
						- http://alternativeto.net/software/zim---a-desktop-wiki/#comments
					- ReadTheDocs
					  collapsed:: true
						- https://docs.readthedocs.io
					- Documize
					  collapsed:: true
						- http://i.imgur.com/O74VknK.png
						- https://documize.com/
						- https://docs.documize.com
						- Their documentation is built with Documize
						  https://docs.documize.com
						- Pros/Cons
							- Pros
							- Cons
								- Feedback is document-level, not inline
				- _Various Evernote-like editors which use Markdown_
				  collapsed:: true
					- Meta
						- Markdown vs other formats
							- [Markdown, Asciidoc, or reStructuredText – a tale of docs-as-code | Hacker News](https://news.ycombinator.com/item?id=33468213)
							- [How to write in Markdown - The MDN Web Docs project | MDN](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Howto/Markdown_in_MDN)
							- [[Markdown] Decide what to do about <dl> · Issue #4367 · mdn/content · GitHub](https://github.com/mdn/content/issues/4367)
							-
					- Notable (built on CodeMirror)
					  https://raw.githubusercontent.com/fabiospampinato/notable/master/resources/demo/main.png
					- _Evernote-like _
					  collapsed:: true
						- Leanote
						  collapsed:: true
							- http://alternativeto.net/software/leanote/reviews/
						- Paperwork
						  collapsed:: true
							- http://paperwork.rocks/
						- TagSpaces
						  collapsed:: true
						  RTF; also Cryptomator
							- WYSIWYG editor for markdown?
						- Notable
						  collapsed:: true
							- https://github.com/fabiospampinato/notable
					- _Markdown files_
					  collapsed:: true
						- Nextcloud several apps
						  collapsed:: true
							- OwnNote
							- Markdown Editor
							  https://apps.nextcloud.com/apps/files_markdown
						- Gruik
						  collapsed:: true
							- http://gruik.io/
							- Markdown
							- Can be self-hosted also
							- Plans for client-side encryption
					- _ODT (XML) files_
					  collapsed:: true
						- _About ODT format_
							- Odt (LibreOffice/OpenOffice) document is just a compressed Zip file, with Content.xml being document text, formatted using ODT tags. The text is plain and fully searchable, provided its not broken by paragraphing or markup tags. Also the odt has nearly everything and supports templates. There are scripts that allow mass searching for any text string, like "thisisa_tag". Et voila.
						- Collabora Online
					- Marktext
					  collapsed:: true
						- Github: https://github.com/marktext/marktext
						- 1. Realtime preview and use snabbdom as its render engine.
						- 2. Support CommonMark Spec and GitHub Flavored Markdown Spec.
						- 3. Support paragraphs and inline style shortcuts to improve your writing efficiency.
						- 4. Output HTML and PDF file.
						- 5. Dark and Light themes.
						- 6. Various edit mode: Source Code mode, Typewriter mode, Focus mode.
						- https://reddit.com/comments/8rrqr9/comment/e0tmgn1?context=3
					- Umbrella Note
					  collapsed:: true
						- Sync with dropbox, google drive
						- 🎹 Keyboard shortcuts
						- 🔏None of the user data is stored on our servers
						- 🚀You can now use umbrella note forever, even if we shut down
						- 🌌 Night mode
						- 📜 Open source
				- _Notational Velocity-like_
				  id:: 657b8765-b5fd-44a1-949e-2416b257a8bd
					- Demo
					  collapsed:: true
						- ![image.png](../assets/image_1716017743720_0.png)
					- [Notational Velocity](https://notational.net/)
					- [Heynote](https://heynote.com/)
					  id:: 65b7e7af-d429-4b93-bb1a-33dc05bf5400
					  collapsed:: true
						- # Pros/Cons
							- Pros
								- Large persistent text buffer divided into blocks (i.e. block-based editor like ((6525b49e-8fcd-4440-9a3e-3c65d4edb58b)) )
								  collapsed:: true
									- ![image.png](../assets/image_1715989181848_0.png)
									- Makes it very suitable for people who prefer one text document as an [[INBOX]] as the blocks are visually separated and you won't accidentally delete content from other blocks
								- ((65ec8114-75e2-4c6f-b997-dad1f67045e9))
								- Buffers
									- Apart from the default Scratch buffer, you can create as many note buffers as you like. Press Ctrl-N to create a brand new buffer, and press Ctrl-S to move the current block into a new buffer. Use Ctrl-P to quickly switch between buffers.
							- Cons
								- Lacks
									- [Feature Request: Flatpak release · Issue #20 · heyman/heynote · GitHub](https://github.com/heyman/heynote/issues/20)
									- [Feature Request: VIM keymap · Issue #24 · heyman/heynote · GitHub](https://github.com/heyman/heynote/issues/24#issuecomment-1889535758)
										- Related: [GitHub - OXY2DEV/markview.nvim: A hackable markdown, Typst, latex, html(inline) & YAML previewer for Neovim](https://github.com/OXY2DEV/markview.nvim)
									- [Feature Request: Extensions/plug-ins · Issue #75 · heyman/heynote · GitHub](https://github.com/heyman/heynote/issues/75)
									- [Images/Screenshots · Issue #157 · heyman/heynote · GitHub](https://github.com/heyman/heynote/issues/157)
									- wontfix
										- [Android app · Issue #50 · heyman/heynote · GitHub](https://github.com/heyman/heynote/issues/50)
										- [Bug: Scrollbar is created when unnecessary · Issue #328 · heyman/heynote · GitHub](https://github.com/heyman/heynote/issues/328)
								- Bugs
									- [Bug: v2.6.2 breaks the global hotkey · Issue #403 · heyman/heynote · GitHub](https://github.com/heyman/heynote/issues/403)
							- Unclear
								- [Feature request: Clickable hyperlinks](https://github.com/heyman/heynote/issues/26) - Keybindings Hold `CTRL` = links become clickable
							- Comparisons
								- ((65b7e7af-d429-4b93-bb1a-33dc05bf5400)) vs ((657b8767-8071-48fb-96df-f30379dc796b))
									- For ((65b7e7af-d429-4b93-bb1a-33dc05bf5400))
										- Can hide to tray, including with a global hotkey
										  id:: 65f55773-9896-4565-a8ff-37c57186e19b
										- Adjustable font size
										- Open-source
										- Scratchpad colour layout works better since I take a lot of notes of different categories all in one big file
									- For ((657b8767-8071-48fb-96df-f30379dc796b))
										- Has an Android app
								- ((1df15812-857b-46dc-be0e-9d6e60782f21))
								- ((65b7e7af-d429-4b93-bb1a-33dc05bf5400)) vs ((663341b5-ddd5-4338-a332-195f59f96fd3))
								  collapsed:: true
									- For ((65b7e7af-d429-4b93-bb1a-33dc05bf5400))
										- It works great
										- ((64243827-555b-49b0-98a5-fec08eba1ba4)) makes more sense for ((65ec8114-75e2-4c6f-b997-dad1f67045e9)) use case. I'm most likely to switch to [[Logseq]] : ((67160958-5490-42db-9b17-63b92bf36354)) once [[Logseq]] gets DB mode
									- For ((663341b5-ddd5-4338-a332-195f59f96fd3))
										- I get to keep practicing vim motions, which will be useful for utilising them in VSCode
										- ((671296f1-27e4-4fed-9ed7-f1fca2452e59))
									- Similarities
										- Mouse support
										- If using Yakuake for ((663341b5-ddd5-4338-a332-195f59f96fd3))
											- Can close to background/system tray support
											- Shortcut for closing to tray/unhiding
												- Then again yakuake show/hide
						- # Documentation
							- [GitHub - heyman/heynote: A dedicated scratchpad for developers](https://github.com/heyman/heynote)
							- Buffers
								- Buffers are stored in a plain `.txt` file
									- `/home/boss/.config/Heynote/notes/scratch.txt` is the symlink, actual file at `/home/boss/Vaults/gocryptfs1/Android-sync/Android-CORE/Notebook/scratch.txt`
								- [[2025-11-17 Monday]] Switched from using a single buffer to 3, because I use Heynote heavily (since [[Logseq]] DB version for Android is still not released) and since I have to use a regular text editor on Android (because Heynote hasn't got a mobile version) I need to sometimes scroll back or view older sections. Split into Scratch (default), Fiction (for copied sections from web novels I'm reading) and Media (for notes from videos and podcasts I've currently got in-progress)
							- Default welcome text (with keybindings and tutorial)
							  collapsed:: true
								- ```
								  Welcome to Heynote! 👋
								  
								  Ctrl + Enter           Add new block below the current block
								  Ctrl + Shift + Enter   Split the current block at cursor position
								  Ctrl + L               Change block language
								  Ctrl + Down            Goto next block
								  Ctrl + Up              Goto previous block
								  Ctrl + A               Select all text in a note block. Press again to select the whole buffer
								  Ctrl + ⌥ + Up/Down     Add additional cursor above/below
								  Ctrl + Shift + H 	   Default global show/hide keybinding
								  Alt  + Shift + F       Format block content (works for JSON, JavaScript, HTML, CSS and Markdown)
								  Alt                    Show menu
								  
								  This is a Math block. Here, rows are evaluated as math expressions. 
								  
								  radius = 5
								  volume = radius^2 * PI
								  sqrt(9)
								  
								  It also supports some basic unit conversions, including currencies:
								  
								  13 inches in cm
								  time = 3900 seconds to minutes
								  time * 2
								  
								  1 EUR in USD
								  
								  In Markdown blocks, lists with [x] and [ ] are rendered as checkboxes:
								  
								  - [x] Download Heynote
								  - [ ] Try out Heynote
								  
								  
								  ```
							- Keybindings
							  id:: 67ea799e-1fde-4472-a12e-302fab292bba
							  collapsed:: true
								- `Meta + H` = Toggle hide/show ((65b7e7af-d429-4b93-bb1a-33dc05bf5400))
								  id:: 67a8e14c-a404-4eba-91c9-947b99aeb521
									- Previously `CTRL + Meta + H
								- "command palette" that can be accessed by pressing `Ctrl/Cmd+Shift+P`, or just typing `>` in the buffer selector. The command palette allows you to discover all available commands in the app, and to quickly execute them.
								- `CTRL + N` = Create a new buffer
								- `CTRL + P` = Switch buffers
								- `Ctrl + Enter` = Add new block below the current block
								- `Alt + Enter` = Add new block before the current block
								- `Ctrl + Shift + Enter` = Add new block at the end of the buffer
								- `Alt + Shift + Enter` = Add new block at the start of the buffer
								- `Ctrl + Alt + Enter` = Split the current block at cursor position
								- `Ctrl + L` = Change block language
								- `CTRL + Up` = Goto previous block / Cursor: Move cursor to previous block
								  id:: 680abbd5-00e2-46c6-9202-93b8883f8273
								- `CTRL + Down` = Goto next block / Cursor: Move cursor to next block
								  id:: 680abbd5-016e-4f93-9b13-59890bf9cbfc
								- `SHIFT + Up` = Select line up (highlight)
								- `SHIFT + Down` = Select line down
								- `ALT + Up` = Edit: Move line up
								  id:: 6808e225-7ad9-4c22-8c39-6c902d23fe65
								- `ALT + Down` = Edit: Move line down
								- `SHIFT + CTRL + Up` = Selection: Select to previous block
								- `SHIFT + CTRL + Down` = Selection: Select to next block
								- `CTRL + ALT + Up` = Cursor: Add cursor above
								- `CTRL + ALT + Down` = Cursor: Add cursor below
								- `CTRL + ALT + [` = Fold the current/selected block(s)
								  id:: 6855c4fe-a438-47aa-b315-beced6e70f93
								- `CTRL + ALT + ]` = Unfold the current/selected block(s)
								  id:: 6855c51f-67d4-4633-a7ed-77e75ff12d3c
								- `ALT + SHIFT + Up` = Move block up
								  id:: 6808dfcf-8779-4e55-9697-f04fad11de80
									- Default: `CTRL + ALT + SHIFT + Up`
								- `ALT + SHIFT + Down` = Move block down
									- Default was: `CTRL + ALT + SHIFT + Down`
								- `Ctrl + A` = Select all text in a note block. Press again to select the whole buffer
								- `Ctrl + Alt + Up/Down` = Add additional cursor above/below
								- `Alt + Shift + F` = Format block content (works for JSON, JavaScript, HTML, CSS and Markdown)
								- `Alt` = Show menu
								- `CTRL + C` whilst not selecting any text - copy whole line
					- ((64098f10-1d1d-4f4d-a2e4-1e4b7fb406a2)) : ((65f55774-9ebf-4a05-a1a7-9683cf8eadef))
					- nvPY
					  collapsed:: true
						- https://github.com/cpbotha/nvpy
						- http://bettermess.com/plain-text-primer-nvalt-101/
						- http://brettterpstra.com/projects/nvalt/
						- http://notational.net/
						- Where Notational Velocity comes in is it allows for really quick note taking. Unfortunately the original app and NValt are only for the mac but there are many alternative clients out there.
							- The barrier to entry is critical for documentation because if it's too hard and you don't do it then it's lost. A lot of wiki's suck because you have to go to it in a browser, login, find where you want the document, decide what you want to call it, etc. It's time consuming. When you are tired at 4:30 you may just not do it or say you will do it tomorrow. You likely wont.
							- Notational Velocity apps just run always on your desktop. You type in a quick title like "Query Smtp server with telnet" it will first search all current documents and see if there's one that matches. Maybe there's more than one. If so you can select. If there's none you press enter and you have a new document. You are editing in seconds. Everything is just text. The default is markdown like what reddit uses or github but you can really use whatever you like.
							- You can write your documentation in markdown. Then easily export to html for static pages. But you can then also just use a tool like pandoc in the future to convert every markdown textfile into whatever other openformat you want. Maybe you feel that dokuwiki is for you or mediawiki seems best or maybe you pick another new tool that uses textile. Maybe you find out about emacs Org-Mode and want your documentation to be in org-mode markup. Well all you have to do is run pandoc against your national velocity directory. It's simple. Easily assisted by version control like git or whatever you like and you can even put that directory on dropbox or something.
							- But if you pick confluence now. Getting your data into Org-Mode or into that new tool you want to use it's going to be a pita. Not only that but most of the fancy features like adding files to documents will not be supported in other tools so the documentation will become disjoint.
							- I am actually moving from doku to Notational velocity now. Am not done yet but it's nice so far. To many times I didn't write the document because I was too burned out at 4:30.
					- nvALT
					  collapsed:: true
						- https://github.com/ttscoff/nv
					- https://github.com/vhp/terminal_velocity
					- https://github.com/viddo/atom-textual-velocity
					- https://github.com/wincent/corpus
					- Related: ((64243827-555b-49b0-98a5-fec08eba1ba4))
			- Desired features
			  collapsed:: true
				- _Markdown spec_
				  collapsed:: true
					- Interlinking
					- Tables
					- Images
					- Code blocks
					- Quotes
					- GitHub task list items e.g. * [X] closed (done) task item
				- Markdown Extensions
				  collapsed:: true
					- _Why_
					  collapsed:: true
						- Human-readable format that can hopefully be parsed with other Markdown apps for years to come
					- Mentions and tags e.g. @, +, #
					  https://github.com/commonmark/CommonMark/wiki/Deployed-Extensions#mention-and-tag
					- In-line emoji picker e.g. :emoji: (Coda)
					  https://d2ddoduugvun08.cloudfront.net/items/0V411i2l2R1a3R1b1C1J/Screen%20Recording%202018-12-12%20at%2005.01%20PM.gif
					- Embedded foreign media including embedded attachments e.g. @[youtube](crypticid)
					  collapsed:: true
					  https://github.com/commonmark/CommonMark/wiki/Deployed-Extensions#foreign-media
						- Images could be Dynalist style
						  e.g. ![anything](http://i.imgur.com/2qINBDM.png)
					- Abbreviations (like tooltips but it marks every instance of those letters)
					  collapsed:: true
						- HTML syntax
							- <abbr title="pixels per inch">PPI</abbr>
							  https://developers.google.com/web/resources/markdown-syntax#tooltips
						- _Syntax_
							- *[HTML]: Hyper Text Markup Language
							  https://github.com/markdown-it/markdown-it-abbr
						- _Visually_
							- Dotted underline
					- Tooltips (similar to abbreviations)
					  collapsed:: true
						- [Upstage]("Visit Upstage!")
						  https://gist.github.com/jonschlinkert/5854601#link-titles
					- Attributes e.g. alignment,
					  https://talk.commonmark.org/t/consistent-attribute-syntax/272/123
					- Spoiler tags
					  collapsed:: true
						- Reddit: >!some spoilers about Snape!<
						  source:: https://www.reddit.com/r/redesign/comments/89jwt7/release_notes_major_items_in_work_4218/
					- Footnotes
					  collapsed:: true
						- https://github.com/commonmark/CommonMark/wiki/Deployed-Extensions#note
						- https://johnmacfarlane.net/babelmark2/?normalize=1&text=named%5B%5Eid%5D+anonymous%5E%5Bnote%5D%0A%0A++%5B%5Eid%5D%3A+footnote%0A
					- {Archive}
					  collapsed:: true
						- Existing implementations
						  https://github.com/commonmark/CommonMark/wiki/Deployed-Extensions
						- https://github.com/commonmark/CommonMark/wiki/proposed-extensions
				- Based on MD extensions
				  collapsed:: true
					- Comments - uses Google Doc-style comment pop-ups though it's based on highlighted text
						- Can use Markdown footnotes
						  intralink2:: https://workflowy.com/#/94b6bf4dabc3
					- Internal links to other docs
						- _Child items_
							- [another](another.md)
							- [another](./another.md)
						- _Child of a child_
							- [inner](inner/inner.md)
							- [inner, dot](./inner/inner.md)
						- _Same level or from root directory_
							- [outer](../outer.md)
						- [my molecule](files/ethanol.mol)
				- _Notebook-style aspects_
				  collapsed:: true
					- _Features for whole doc_
						- _Sidebar + file picker_
							- Hamburger menu to bring up a Workspaces menu with also a dropdown Communities list (similar to Asana, Nuclino, Discord, Riot)
							  http://i.imgur.com/WeFXA0D.png
								- Workspaces - Nuclino
							- _File picker view - _Breadcrumbs in header + grid for choosing documents or folders (similar to Google Drive, Filestash, Coda)
							- Hierarchy tree structure collapsible sidebar for navigating to different Sections of one Document (Coda; also similar to sheets in spreadsheets, or tables in one base in Airtable)
							  https://cdn-images-1.medium.com/max/800/1*AwqV2VLli46dBhQh8ISaKQ.gif
						- Inline attachments e.g. using E2EE FileSafe (Cryptee, Nuclino, Quip)
							- FileSafe - using popular cloud storage (WebDAV, Google Drive, Dropbox)
							  intralink2:: https://workflowy.com/#/8ba673778892
							- Cryptomator
							- _Numerous web apps_
								- See [Cryptee](https://workflowy.com/#/fb3f99e991f8)
								- Nextcloud
						- Markdown shortcuts
						  https://d2ddoduugvun08.cloudfront.net/items/1S1q3u1I2f2e2g1Z2Z0t/unnamed-3.gif
						- In-doc search
						  https://uploads.intercomcdn.com/i/o/24788473/2aca74a41d9e68bfdfacda84/DocSearch.gif
						- Document version history
						  https://downloads.intercomcdn.com/i/o/39732331/f8dbc8f9ab176cbbca4a7fc0/Screen+Recording+2017-11-16+at+10.47+AM.gif
						- Favicons for doc reflect in brower tab
						  https://cdn-images-1.medium.com/max/800/1*UwZBVLgy_uw_uRoDBvdy5w.gif
						- Presentation mode
						  https://d2ddoduugvun08.cloudfront.net/items/1l0d3p0X2m3c1O403v1Y/Screen%20Recording%202019-01-14%20at%2012.41%20PM.gif
					- _Block types_
						- Rich media embeds
							- Libraries
								- PHP-based for oembed, opengraph,
								  https://github.com/oscarotero/Embed
								- Iframely SaaS
								  https://iframely.com/
								-
							- Examples
								- Video
								- 🎥YouTube
								- 🎥Vimeo
								- 🎥Ted
								- 🎥Streamable
								- 🎥Loom
								- 🎥CloudApp
								- 👫 Social
								- 👫Instagram
								- 👫Twitter
								- 👫Facebook
								- 👫Pinterest Pins & Boards
								- 📂 Cloud Files
									- 📂Google Docs
									- 📂Google Slides
									- 📂Google Sheets
									- 📂Google PDF
									- 📂Google Video
									- 📂OneDrive Excel
									- 📂OneDrive Word
									- 📂OneDrive PowerPoint
									- 📂Box
									- 📂AirTable
									- 📂Dropbox
								- 📈 Presentations
								  id:: 634710bf-d734-43db-b9f3-fa0094183b3a
									- 📈Slideshare
									- 📈Prezi
									- 📈Haikudeck
									- 📈Speakerdeck
									- 📈Google Slides
									- 📈Google PDF
									- 📈OneDrive PowerPoint
									- 📈OneDrive PDF
								- 🖥Spreadsheets / Databases
									- 🖥Google Sheets
									- 🖥OneDrive Excel
									- 🖥Box Excel
									- 🖥Smartsheet
									- 🖥Airtable Database
								- ️ Survey/Forms/Polls
									- Proprietary
										- ✔️Google Forms
										- ✔️Airtable Forms
										- ✔️Typeform
										- ✔️Upscribe
										- ✔️Paperform
										- ✔️Poll Daddy
										- ✔️Poll Everywhe
									- Open-source
										- https://github.com/formbricks/formbricks
										-
										- [https://framaforms.org](https://framaforms.org)
								- 📊 Charts
									- 📊Lucidcharts
									- 📊Tableau
									- 📊Chartblocks
									- 📊Amcharts
								- ✅ Tasks/Schedule
									- ✅Trello Cards & Boards
									- ✅Calendly
									- ✅Google Calendar
									- ✅Airtable Calendar
								- 🎨 Graphic Design Tools
								  id:: 6345af66-f644-437e-b042-84d877426521
									- 🎨Canva
									- 🎨Behance
									- 🎨Sketchfab
									- ((6345af5c-353c-4aed-9b5a-572bd52cc70a))
									- 🎨Marvel
								- 💻Code
									- 💻Github Gists
									- 💻Pastebin
								- 🚗 Maps
									- 🚗Google Maps
									- 🚗Google Directions
									- 🚗Google Street View
								- 🎤 Music
									- 🎤SoundCloud
									- ((64f5d195-048b-4532-86da-5e3fa35b3d2c))
									- 🎤Mixcloud
								- 📷 Images & Gifs
									- 📷Flickr
									- 📷Imgur
									- 📷Giphy
					- _Features for embedded database (with multiple View types_
						- Minimalist table (looks like a checklist until hover
						  https://d2ddoduugvun08.cloudfront.net/items/3E360V0Q292X3v0w151z/unnamed-4.gif
						- Full-screen toggle
						  https://d2ddoduugvun08.cloudfront.net/items/253T2t221a3I0D011X1h/Screen%20Recording%202019-01-15%20at%2011.48%20AM.gif
						- Optional wrap or don't wrap column header text
						  https://d2ddoduugvun08.cloudfront.net/items/2V1q0x412y3N1j3k2L3L/Screen%20Recording%202018-03-13%20at%2011.49%20AM.gif
						- _Fields_
							- Basic Buttons (Coda) - add, modify or delete a row
							  https://cdn-images-1.medium.com/max/800/1*j0VqxauFCfaq82OK6vUhjQ.gif
							- Link to other table (Coda, Airtable)
							  https://s3.amazonaws.com/f.cl.ly/items/2Z3o3N1m1E2B0i3V1n16/Image%202018-12-04%20at%202.29.19%20PM.png?AWSAccessKeyId=AKIAJATDXY6T7PWOQPCQ&Expires=1550581294&Signature=mNJ19ugXMvbXOvpNB6ww26pPoUY%3D&response-content-disposition=attachment
							- Scale (Coda)
							  https://cdn-images-1.medium.com/max/2000/1*kC93nQlx15b6prBBGRWdrQ.gif
								- https://blog.coda.io/on-a-scale-of-1-to-86c78870f575
							- Airtable: Single line text, Long text; Attachment; Checkbox, Multiple Select; Single select; Link to another record; Collaborator; Rating; Rollup; Count; Lookup; Created time; Date; Phone number; Email; URL; Number (numerical); Currency; Percent; Duration; Formula; Autonumber; Barcode;
						- _Views_
							- Table/Grid/Database (Airtable / Coda / Notion / Quip)
							- Cards/Board/Kanban
							- Detail view (Coda | Basically Airtable's expanded record view, or Astrid Tasks task details)
							  http://i.imgur.com/NOZTc4s.png
							- Calendar
							- Form (Airtable)
							- Charts (Bar, line, pie, scatter)
							  https://d2ddoduugvun08.cloudfront.net/items/2C2431383s250W221l0T/unnamed-2.gif
								- https://help.coda.io/organizing-your-doc/layout-options/using-charts-in-coda
							- Matrix (Airtable)
							  http://i.imgur.com/3jGPg7Z.png
								- https://support.airtable.com/hc/en-us/articles/360004334874-Matrix-block
					- Real-time collaborative editing
					- Notifications for changes
				- Examples of highly formatted documents
				  collapsed:: true
					- Notion
					  intralink2:: https://workflowy.com/#/81b9a4e003af
					- Coda
					  intralink2:: https://workflowy.com/#/aca811937ea8
					- Airtable Blocks
					  intralink2:: https://workflowy.com/#/8f7eae7180fe
					- Many more e.g. Quip, Bit.ai, Slab
					  intralink2:: https://workflowy.com/#/bb249f041a4e
			- _Related:_
				- ((649161c9-8d84-401d-9ca6-af28145da219))
				- Knowledge base e.g. wikis
				  intralink2:: https://workflowy.com/#/16db34c48751
		- _Spreadsheet-based_
		  collapsed:: true
			- _Software_
				- _Spreadsheet-Database hybrids_
				  id:: 663904b1-af62-4dbb-9e10-edf132813c19
				  collapsed:: true
				  Basically a javascript spreadsheet with realtime database engine
					- What
					  collapsed:: true
						- The fields in an Airtable table are similar to a cell of a spreadsheet, but have types check-boxes, phone numbers, and drop-down lists, and can reference file attachments like images
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Negates duplicate data as you simply reference data in other tables
							- Uses
							  collapsed:: true
								- for project management
									- http://www.databaseanswers.org/data_models/tracking_progress_on_projects/index.htm
									- http://talk.dynalist.io/t/a-few-dynalist-project-management-ideas/805
									- http://bulletjournal.com/get-started/
									- https://www.buzzfeed.com/nicolenguyen/genius-ways-you-can-customize-your-bullet-journal?utm_term=.rxpm4Xl6lM#.ndGk5aMXMZ
								- Freelancer management
								- Accounting
								- Quantified self (interlink stats + visualisation + APIs)
								- for managing subscriptions and expenses
								- Digital asset management
									- Enter info about asset in other fields and keep one column for the actual link
								- CRM / social network manager
								- rTracker things e.g. journal
								- Weekly / monthly etc reviews
								- Content marketing
									- https://www.process.st/airtable-content-marketing/
								- Archiving with Zapier e.g. completed Asana tasks
								- Anki+Airtable
								  #MetaLearning https://workflowy.com/#/15217543ec98
					- Alternatives
					  collapsed:: true
						- Comparison to uTracker
						  intralink2:: https://workflowy.com/#/66fe7003c83f
						  collapsed:: true
							- Similarities
								- Many field types for users to enter formatted data
								- Easy export to CSV
							- Differences
								- Realtime cloud DB collaboration vs local DB
								- Many field types vs a few
								- Cross-platform vs Android
								- View/edit entire database from one screen vs edit one row/entry per screen, more clicks to get to particular cells (similar to form entry + updating existing)
								- Many 'views' vs only form style view
						- Comparison of Airtable vs Asana
						  collapsed:: true
						  Mainly for freelancer project management
							- Airtable pros
								- Presence indicators (online)
								- Free tier can be used for many freelancers (Asana requires separate workspaces for each/pay for private projects or teams)
								- Easier to prompt updates of 'actual hours' spent, especially for tasks without an estimate beforehand
								- Faster than Asana
							- Asana pros
								- Inbox - easy deferring reading updates to later
								- Easier seeing overdue tasks
							- Related
								- Asana-style Inbox concept
								  intralink2:: https://workflowy.com/#/249685c2ba5a
								- intralink2:: https://workflowy.com/#/02a1164cc7b3
								- intralink2:: https://workflowy.com/#/ad00959a9104
								- intralink2:: https://workflowy.com/#/d33667ac406d
						- Zapier + MySQL integration
						  collapsed:: true
							- https://zapier.com/blog/add-any-app-to-zapier/#database
						- Zapier alternative
						  collapsed:: true
							- https://www.reddit.com/r/selfhosted/comments/5dgcn9/zapier_self_hosted_alternative
							- https://www.reddit.com/r/selfhosted/comments/4hmais/any_self_hosted_like_zapier_is_available_for/?utm_source=amp&utm_medium=comment_header
							- Trigger happy
							-
					- # Open-source
					  collapsed:: true
						- ## Web-based
							- ### Best
								- [NocoDB](https://www.nocodb.com)
								  collapsed:: true
									- Links
										- [[Page not found · GitHub](https://github.com/nocodb/nocodb](https://github.com/nocodb/nocodb))
										- Discord : [https://discord.gg/5RgZmkW](https://discord.gg/5RgZmkW)-
										- Twitter : [https://twitter.com/nocodb](https://twitter.com/nocodb)
									- Pros/Cons
									  collapsed:: true
										- Pros
											- Easy 1-line setup
											  collapsed:: true
												- docker run -p 8080:8080 nocodb/nocodb
												- or
												- npx create-nocodb-app
											- Can connect to standard database software like MySQL (local or across network)
											  collapsed:: true
												- works with MySQL, PostgreSQL, Microsoft SQL Server, SQLite, Amazon Aurora & MariaDB databases.
											- Can connect to cloud storage e.g. S3
											  collapsed:: true
												- For storage you can connect to S3, Mini, GCS, Azure, DigitalOcean spaces & any S3 compatible API
											- Integrations with 3rd-party APIs and services
											  collapsed:: true
												- NocoDB gives programmatic access to REST & GraphQL APIs. And with our API tokens it can be easily integrated with Zapier / Integromat.
												- Also NocoDB's app store allows you to build business workflows on views with combination of Slack, Microsoft Teams, Discord, Twilio, Whatsapp, Email & any 3rd party APIs too. Plus NocoDB provides programmatic access to APIs so that you can build integrations with Zapier / Integromat and custom applications too.
											- Link in a record
											  [https://github.com/nocodb/nocodb/issues/139](https://github.com/nocodb/nocodb/issues/139)
										- Cons
											- Lacks
												- Import/export CSV, JSON
												  [https://github.com/nocodb/nocodb/issues/179#issuecomment-851356677](https://github.com/nocodb/nocodb/issues/179#issuecomment-851356677)
													- Export CSV is done
													- Can't import CSV
													  [https://github.com/nocodb/nocodb/issues/730#issuecomment-970355036](https://github.com/nocodb/nocodb/issues/730#issuecomment-970355036)
													- Can import ODS, XLS
												- Drag-and-drop functionality
												  [https://github.com/nocodb/nocodb/issues/160#issuecomment-860057742](https://github.com/nocodb/nocodb/issues/160#issuecomment-860057742)
													- For SingleSelect and MultiSelect: ability to drag-and-drop reordering the choices
													- Drag-and-drop reorder columns
												- Unique URL when viewing row in the pop-up
												  [https://github.com/nocodb/nocodb/issues/273](https://github.com/nocodb/nocodb/issues/273)
												- Duplicate column
												- Hamburger menu in the header which collapses the left sidebar
												- Mobile responsive
												  [https://github.com/nocodb/nocodb/issues/158](https://github.com/nocodb/nocodb/issues/158)
											- Issues
												- Can't rename tables from UI?
												  [https://github.com/nocodb/nocodb/issues/205#event-4865387194](https://github.com/nocodb/nocodb/issues/205#event-4865387194)
									- Notes
									- Documentation
									  collapsed:: true
										- Setup MariaDB
										  [https://hub.docker.com/_/mariadb?tab=description](https://hub.docker.com/_/mariadb?tab=description)
											- ~/Documents/MUSEUM/Docker/MariaDB/docker-compose.yml
										- Adminstrating locally
											- Adminer
											  [http://localhost:8067](http://localhost:8067/?server=root_db&username=root)
											- NocoDB
											  [http://127.0.0.1:9043](http://127.0.0.1:9043)
										- List stopped Docker containers
										  docker ps --filter "status=exited"
										- List running Docker containers
										  docker ps
										- Viewing data via Adminer (phpmyadmin)
											- Example: `xa1__food` in Adminer is `Food` table in NocoDB
											  [http://localhost:8067/?server=xcdb&username=root&db=xcdb&table=xa1__food](http://localhost:8067/?server=xcdb&username=root&db=xcdb&table=xa1__food)
										- Troubleshooting
											- root_db_1  | 2021-06-12T12:28:21.616381Z 24 [Note] Access denied for user 'root'@'localhost' (using password: NO)
								- [Baserow](https://baserow.io)
								  id:: 64243824-43a2-498d-bb79-59a6e4523bb2
								  collapsed:: true
									- Pros/Cons
									  collapsed:: true
										- Pros
											- _Features_
												- Open-source
												- Interlink between table rows
													- See [Lookup](https://workflowy.com/#/f43d17991c62)
												- Decent number of field types
												  collapsed:: true
													- URL
													- Image and file
													- Single select choice
													- Multiple select
													- Last modified
													- Created on
													- Formula
													- Lookup
													  collapsed:: true
														- Cons
															- Have to select a different table, can't be the same table
															- Linked to a single field of a single record, not a whole record
														- Lookup fields let you select a field in another table to display, use it to combine all the relevant fields you need into a single useful table. To starting using them, create a new field and choose the new lookup option, then select a link row field in the same table to lookup through and finally a target field in the linked table to get values for. Your lookup field will then contain the target field value for every linked row formatted into a list. Finally you can reference lookup fields directly in formulas and use the filter and aggregate formula functions to filter them down and sum them up.
														- 1 Backlink
															- See [Lookup](https://workflowy.com/#/f43d17991c62)
													- Rating
												- Publicly exposing data via a [REST API endpoint](https://baserow.io/api/docs)
													- It was one of the first feature requests that we have received. Easily exposing your data via a public REST API. This makes it possible to integrate Baserow with your existing application or website. You can for example create a table with projects that you have worked on in Baserow, and add a page to your portfolio website that fetches and lists those projects. This way you don't have to setup a backend or CMS by yourself. Your site can even be a fully static. It's possible to perform create, read, update and delete operations on the table.
												- Easy to self-host
												  collapsed:: true
													- [https://baserow.io/docs/guides%2Finstallation%2Finstall-on-ubuntu](https://baserow.io/docs/guides%2Finstallation%2Finstall-on-ubuntu)
													- [https://baserow.io/docs/index](https://baserow.io/docs/index)
													- [https://api.baserow.io/api/redoc/](https://api.baserow.io/api/redoc/)
													- [https://baserow.io/docs/plugins%2Fboilerplate](https://baserow.io/docs/plugins%2Fboilerplate)
													- Cloudron
													  [https://baserow.io/docs/guides%2Finstallation%2Finstall-on-cloudron](https://baserow.io/docs/guides%2Finstallation%2Finstall-on-cloudron)
													- Docker
														- [https://baserow.io/docs/guides%2Frunning-baserow-locally](https://baserow.io/docs/guides%2Frunning-baserow-locally)
														- April 2021
															- git clone [https://gitlab.com/bramw/baserow.git](https://gitlab.com/bramw/baserow.git)
															- cd baserow
															- docker-compose up
												- Real-time collaboration
												- Build with Django and Nuxt
												- Drag-and-drop reorder
												- Multipe view types
													- Table
													- Form
													- Kanban
													  id:: 662d398c-70e7-4318-8437-9862b7065a8a
													- Gallery
													- [Unique URL for each row (when previewed in a pop-up)](https://gitlab.com/bramw/baserow/-/issues/938) - allows hyperlinking to specific records from Logseq or bookmarks
													  collapsed:: true
														- [https://community.baserow.io/t/unique-url-for-each-row-when-viewing-in-the-expanded-pop-up/564](https://community.baserow.io/t/unique-url-for-each-row-when-viewing-in-the-expanded-pop-up/564)
											- Features they have now but I need to test to see if sufficient
												- Multiple types of export - JSON, XML, CSV (premium for JSON/XML)
												  collapsed:: true
													- Can export table or view as CSV (for free). JSON or XML is premium
													  source:: [https://baserow.io/blog/may-2021-release-of-baserow](https://baserow.io/blog/may-2021-release-of-baserow)
													  collapsed:: true
														- You can now easily export all your table or view data to CSV format. Click on the three dots next to a table or view and click on “Export table” or “Export view”. This will open a modal where you can choose how you would like to export. Clicking on the “Export” button at the bottom will generate the file and then offers the file as download.
													- Unsure if this is full export, need to test
													- Full export - needed for trusting the service, so that I can make backups and also switch providers/software at any moment (needed to meet GDPR).
													  collapsed:: true
													  _See_ [May - import/export to Excel, JSON and XML](https://workflowy.com/#/5302aa8d4f54)
														- Like Notion allows full workspace export as Markdown files
														  [https://www.notion.so/GDPR-at-Notion-8952f065d96f4c18abf22fc3c85e272e](https://www.notion.so/GDPR-at-Notion-8952f065d96f4c18abf22fc3c85e272e)
														- This may be a premium feature
														  [https://baserow.io/premium](https://baserow.io/premium)
														- ..
														- I've already asked to export PostgreSQL - since it uses it already to store data
														  collapsed:: true
														  [https://gitlab.com/bramw/baserow/-/issues/90#note_462616083](https://gitlab.com/bramw/baserow/-/issues/90#note_462616083)
															- This is also directly possible using the ./baserow backup_baserow and ./baserow restore_baserow commands.  They create a zip containing the exported SQL database using the pg_dump tool under the hood for you. See this guide for more information on how to use these commands: [https://gitlab.com/bramw/baserow/-/blob/develop/docs/runbooks/back-up-and-restore-baserow.md](https://gitlab.com/bramw/baserow/-/blob/develop/docs/runbooks/back-up-and-restore-baserow.md) .
															  collapsed:: true
																-
															- ..
															- This is currently possible via the `export_group_applications` and `import_group_applications` management commands. We might be able to use this technology at some point to create backups from the user interface.
														- Related:
														  [https://gitlab.com/bramw/baserow/-/issues/141](https://gitlab.com/bramw/baserow/-/issues/141)
													- How to make own backup script
													  collapsed:: true
														- Go to
														  /home/boss/Documents/MUSEUM/Docker/Baserow-backuper/
														- Create a docker-compose.yml which is just the database bind mount volume, with a database management tool
														- Use that tool GUI to dump the database
												- Comprehensive importer
												  collapsed:: true
												  _See_ [May - import/export to Excel, JSON and XML](https://workflowy.com/#/5302aa8d4f54)
													- Can import tables via JSON (May 2021)
													- The CSV and tabular paste importer are only the beginning.
													  collapsed:: true
														- We have plans to create a Microsoft Excel, Apple Numbers, Google Sheets, XML, JSON and many other importers. Of course it's also possible to create your own importer by developing a plugin.
												- Docker
												  collapsed:: true
													- Documentation
													  collapsed:: true
														- [Running Baserow locally](https://baserow.io/docs/guides%2Frunning-baserow-locally)
														- [Running the dev environment](https://baserow.io/docs/development%2Fdevelopment-environment)
														- [Baserow Docker how to guide](https://baserow.io/docs/guides%2Fbaserow-docker-how-to)
														- [Baserow's Docker API](https://baserow.io/docs/reference%2Fbaserow-docker-api)
												- Heroku one-click deploy
												  collapsed:: true
													- [https://baserow.io/docs/guides%2Finstallation%2Finstall-on-heroku](https://baserow.io/docs/guides%2Finstallation%2Finstall-on-heroku)
										- Cons
											- Open core with premium only features
												- Admin dashboard and user management (self hosted only)
												- Row comments
												- ((662d398c-70e7-4318-8437-9862b7065a8a))
												- Additional exporter formats (JSON and XML)
											- Bugs
												- [Drag-and-drop to swap column order doesn't update the expanded single row field order](https://gitlab.com/bramw/baserow/-/issues/939)
											- _Lacks_
												- Limited colour customisation for Single Select choices
												- [Dark theme](https://gitlab.com/bramw/baserow/-/issues/234)
													- [https://community.baserow.io/t/dark-theme-option/562](https://community.baserow.io/t/dark-theme-option/562)
												- Duplicate column + row
												- Export + import DB dump ZIP
												- [One-to-one link to table row, instead of just one-to-many link](https://gitlab.com/baserow/baserow/-/issues/403)
												- [Description per field](https://gitlab.com/baserow/baserow/-/issues/2090#note_1887638895)
												- [Embeddable](https://gitlab.com/baserow/baserow/-/issues/236#note_07d228d88acfc360ca6aa90a0ad9893e650b9370)
												- [Sort by Select Option order, not just alphabetically](https://gitlab.com/baserow/baserow/-/issues/786#note_32c34a0c4eb8285b56d5365e50e5d004307035d7)
												- [Move tables from one database to another](https://gitlab.com/baserow/baserow/-/issues/977#note_1583956796)
												- [iCal feed](https://gitlab.com/baserow/baserow/-/issues/1911#note_1869256776)
												- [Allow changing the primary field](https://gitlab.com/baserow/baserow/-/issues/1301#note_1463733586)
												- [Link to a table in another databse](https://gitlab.com/baserow/baserow/-/issues/1354#note_67211b3fe1823181a1e30069d2afd2c6b4324fb1)
												- [Better mobile UX](https://gitlab.com/baserow/baserow/-/issues/690#note_6755372d8b781b817046aee533a06346084d9805)
												- [Desktop app](https://gitlab.com/baserow/baserow/-/issues/271#note_1818884681)
									- _Links_
										- https://gitlab.com/baserow/baserow
										- [Mirror](https://github.com/bram3w/baserow)
										- Last read: September 2023 release
										  https://baserow.io/blog/category/release
										- [Changelog](https://gitlab.com/bramw/baserow/-/blob/develop/changelog.md)
									- Screenshots
									  id:: 677f953e-040e-463e-a121-e67ef4dda0b8
										- [[2025-01-09 Thursday]]
											- Waiting for [[Logseq]] DB mode to transfer these into their `/table`
											- ![image.png](../assets/image_1736414535257_0.png)
									- # Documentation
										- ## [Installation](https://gitlab.com/bramw/baserow/-/blob/develop/docs/installation/install-with-docker-compose.md)
											- `cd /home/boss/Documents/MUSEUM/Docker/Baserow`
											- [Git clone the full repo as a backup](https://gitlab.com/bramw/baserow)
											- `curl -o docker-compose.yml https://gitlab.com/baserow/baserow/-/raw/master/docker-compose.yml`
											- `curl -o Caddyfile [Not Found](https://gitlab.com/baserow/baserow/-/raw/master/Caddyfile`)
											- [How to set environment variables](https://gitlab.com/bramw/baserow/-/blob/develop/docs/installation/install-with-docker-compose.md#how-to-set-environment-variables)
												- Copy the .env.example file found in the root of Baserows repository ([[Files · master · Baserow / baserow · GitLab](https://gitlab.com/bramw/baserow/-/blob/master/.env.example](https://gitlab.com/bramw/baserow/-/blob/master/.env.example)))  to .env:
												  `curl -o .env [Not Found](https://gitlab.com/bramw/baserow/-/raw/master/.env.example`)
												- Edit .env and provide values for the missing environment variables.
												- `docker-compose up`
											- It'll be exposed on [http://localhost:81](http://localhost:80)
										- ## If wanting bind mounts (recommended for easier backups)
											- Search the `docker-compose.yml` for `volume`
											- Add `./` at the start of each
											- Create folders in the `baserow` parent directory
										- To run the Docker
											- `docker-compose up -d`
										- To update to the latest run:
											- `cd /home/boss/Documents/MUSEUM/Docker/Baserow`
											- `docker-compose down`
											- `git pull`
											- `docker-compose up -d`
										- Accessing the database via GUI
											- See DBeaver
												- Example credentials for Baserow
											- See [Adminer](https://workflowy.com/#/d752397fb47a)
												- Example credentials for Baserow
										- Backups
											- Check Vorta
												- 2024-07-01 - no `/home/boss/Documents/MUSEUM/Docker/Baserow/pgdata`
												- 2024-04-30
												- 2024-01-30
												- 2023-11-30
											- `rsync -avz /home/boss/Documents/MUSEUM/Docker/Baserow/pgdata/ /home/boss/Documents/MUSEUM/Docker/Baserow/pgdata2`
											-
									- Related: ((644c0b31-71f0-4cd8-bc43-7f455aacf439))
								- [Eidos](https://eidos.space/)
								  collapsed:: true
									- [Eidos](https://github.com/mayneyao/eidos)
										-
								- Focalboard
								  collapsed:: true
									- Links
									  collapsed:: true
										- [https://www.focalboard.com/](https://www.focalboard.com/)
										- [https://github.com/mattermost/focalboard](https://github.com/mattermost/focalboard)
										- Changelog
										  [https://github.com/mattermost/focalboard/blob/main/CHANGELOG.md](https://github.com/mattermost/focalboard/blob/main/CHANGELOG.md)
											- Last read
											  [https://github.com/mattermost/focalboard/blob/main/CHANGELOG.md#v06-release---march-15-2021](https://github.com/mattermost/focalboard/blob/main/CHANGELOG.md#v06-release---march-15-2021)
										- Download
										  [https://www.focalboard.com/download/personal-edition/desktop/](https://www.focalboard.com/download/personal-edition/desktop/)
										- User guide
										  [https://www.focalboard.com/guide/user/](https://www.focalboard.com/guide/user/)
									- Pros/Cons
									  collapsed:: true
										- Pros
											- Card view + table view
												- Card
												  [https://www.focalboard.com/img/hero.jpg](https://www.focalboard.com/img/hero.jpg)
												- Table
												  [https://www.focalboard.com/guide/user/all%20tasks.png](https://www.focalboard.com/guide/user/all%20tasks.png)
											- Description box for each card can have multiple images (uses hyperlinking)
											- Multiple export types
												- JSON
													- You can export an archive of all your boards from the settings menu.
														- This is handy to quickly back-up snapshots, or to transfer them to different installations, for example from a Personal Desktop to a server install.
														- Note that the archive does not (currently) include image and file attachments, such as images included in a card.
														- Also note that importing an archive will overwrite changes to items, but will not affect additional items (e.g. boards and cards) that are not part of the archive.
													- [JSONL Archive](https://www.focalboard.com/guide/user/#archives): The <a href="https://jsonlines.org/">JSON lines format</a> is used for perf. This is also the import format.
														- Note that data files (images) aren't part of the export. These are stored in the /files folder, and can be copied separately.
												- CSV: Individual boards and tables can be exported to CSV from the options menu
												- SQLite: Not necessarily a supported method, but if your DB is SQLite (default), the focalboard.db file can simply be copied and queried directly.
												- APIs: In addition, you could write export scripts against the [REST API](https://htmlpreview.github.io/?https://github.com/mattermost/focalboard/blob/main/server/swagger/docs/html/index.html)
											- Has many Property types
											  [https://i.imgur.com/Lea1VwK.png](https://i.imgur.com/Lea1VwK.png) (Notion)
												- _Few currently_
													- Text
													- Number
													- Select (One)
													- Created Time
													- Updated Time
													- Date
													- _Beta_
														- Multiple-Select (only has Single-Select currently)
														- Checkbox
														- URL
											- Docker-compose (web app should have unique URLs)
											  [https://github.com/mattermost/focalboard/tree/main/docker](https://github.com/mattermost/focalboard/tree/main/docker)
											- Unique link for each record
											  [https://github.com/mattermost/focalboard/issues/526](https://github.com/mattermost/focalboard/issues/526)
										- Cons
											- _Lacks_
												- Image/Attachment property type
												  [https://github.com/mattermost/focalboard/issues/111#issuecomment-804321994](https://github.com/mattermost/focalboard/issues/111#issuecomment-804321994)
												- UX annoyances
													- Can't click on column headers to change the property type (have to instead open an individual item)
													  [https://i.imgur.com/Lea1VwK.png](https://i.imgur.com/Lea1VwK.png) (Notion)
													- Can't right click records - and thus no right-click item delete whilst on table view
													  [https://i.imgur.com/2isLlIV.png](https://i.imgur.com/2isLlIV.png) (Airtable)
													- Can't sort by multiple types
													  [https://i.imgur.com/o8oBXJd.png](https://i.imgur.com/o8oBXJd.png) (Notion)
													- ....
													- Reordering columns and rows via drag-and-drop should highlight between columns, not highlight whole cell
													- Better UX for option creation for Select + Multi Select properties. Also reordering and set colours
													- In card view can't scroll between different cards
													  [https://github.com/mattermost/focalboard/issues/417](https://github.com/mattermost/focalboard/issues/417)
													- Drag-and-drop reorder columns in the expanded view (can do it in grid view though)
												- Link to another record
												  [https://github.com/mattermost/focalboard/issues/324#ref-issue-911374994](https://github.com/mattermost/focalboard/issues/324#ref-issue-911374994)
													- [https://github.com/mattermost/focalboard/issues/340#issuecomment-827213535](https://github.com/mattermost/focalboard/issues/340#issuecomment-827213535)
												- Embed web content
												  [https://github.com/mattermost/focalboard/issues/361#issuecomment-830426826](https://github.com/mattermost/focalboard/issues/361#issuecomment-830426826)
												- Snap/Flatpak package (then again I prefer Docker now - see [Docker vs Flatpak](https://workflowy.com/#/e757ceafb96d))
												  [https://github.com/mattermost/focalboard/issues/79#issuecomment-801895273](https://github.com/mattermost/focalboard/issues/79#issuecomment-801895273)
												- UI isn't designed for dozens or hundreds of separate boards
									- _Related:_
										- [Content for database format](https://workflowy.com/#/f510c555e0fc)
									- 2 Backlinks
										- Convert existing databases into [NocoDB](https://workflowy.com/#/9bc784aa2cb8) or <a href="https://workflowy.com/#/4d16dc817c67">Focalboard</a>
										- See [Focalboard](https://workflowy.com/#/4d16dc817c67) [RSS: News > Tech > Desktop > Apps]
										  #Software-PM
								- [AppFlowy](https://www.appflowy.io)
								  id:: 653f787b-5cf5-4864-817f-404d861bc1cc
								  collapsed:: true
									- https://github.com/AppFlowy-IO/appflowy
									- `flatpak install flathub io.appflowy.AppFlowy`
									- Lacks
										- [Export to Markdown](https://github.com/AppFlowy-IO/AppFlowy/issues/411#event-11332912006)
										- [Export to AppFlowy format](https://github.com/AppFlowy-IO/AppFlowy/issues/4387#issue-2080840609)
										- [Web app (desktop only)](https://github.com/AppFlowy-IO/AppFlowy/issues/89#ref-issue-1727286879)
										- [Vim bindings](https://github.com/AppFlowy-IO/AppFlowy/issues/284)
										- [Interlink databases](https://github.com/AppFlowy-IO/AppFlowy/issues/1664)
										- [CalDAV support](https://github.com/AppFlowy-IO/AppFlowy/issues/487)
										- [Backlinks](https://github.com/AppFlowy-IO/AppFlowy/issues/2214)
										- [Search](https://github.com/AppFlowy-IO/AppFlowy/issues/2232#issuecomment-1951323622)
										- [Insert files into docs](https://github.com/AppFlowy-IO/AppFlowy/issues/2237)
										- [Text link](https://github.com/AppFlowy-IO/AppFlowy/issues/1020#event-b4b910c0-6129-5c74-9d67-3b6a19ac3028)
										- [Navigation history](https://github.com/AppFlowy-IO/AppFlowy/issues/3101)
								- [Grist](https://www.getgrist.com)
								  id:: 67a8e14c-c8cd-4e93-a4f0-e4159f79b68b
								  collapsed:: true
									- Pros
										- Can export entire database as SQLite, or individual tables as CSV/XLS
											- With Grist you can download the entire relational structure as a .grist file, which is a SQLite file that can be opened in other SQLite software. If you’d like to export tables as a spreadsheet, tables can be exported individually as a CSV, exported to Google Drive, or downloaded as an Excel workbook. Your documents are also automatically backed up, and snapshots can easily be exported in full. If you make a big mistake, you can also restore your data from a snapshot right in Grist.
									- Cons
										- Open core product - not sure what features may be missing from FOSS version
									- Repos
										- [https://github.com/gristlabs/grist-core](https://github.com/gristlabs/grist-core)
										- [GitHub - gristlabs/grist-desktop: Desktop Grist, packaged with Electron](https://github.com/gristlabs/grist-desktop)
									- [Exports & backups - Grist Help Center](https://support.getgrist.com/exports/#backing-up-an-entire-document)
									- [Flatpak packaging · Issue #16 · gristlabs/grist-electron · GitHub](https://github.com/gristlabs/grist-electron/issues/16)
									- Documentation
										- Built on SQLite
								- [Anytype](https://anytype.io) (very ((6525b49e-8fcd-4440-9a3e-3c65d4edb58b))-like)
								  id:: 635eb27e-7770-4aa4-96a8-093c6dd9691d
								  collapsed:: true
									- Pros/Cons
										- Pros
											- Built on IPFS
											- E2EE
											- Offline-first
										- Cons
											- Lacks
												- [Vim Mode](https://github.com/anyproto/anytype-ts/issues/247)
												- [Create a web interface to access content from browser · Issue #631 · anyproto/anytype-ts · GitHub](https://github.com/anyproto/anytype-ts/issues/631)
												- [It's too easy to delete a space · Issue #946 · anyproto/anytype-ts · GitHub](https://github.com/anyproto/anytype-ts/issues/946)
												- [Limit Linux app distribution methods to AppImage and flatpak · Issue #96 · anyproto/anytype-ts · GitHub](https://github.com/anyproto/anytype-ts/issues/96)
												- [ditch the old day tech MD in favor to HTML, please support it · Issue #933 · anyproto/anytype-ts · GitHub](https://github.com/anyproto/anytype-ts/issues/933)
												- [External Video and Audio. · Issue #934 · anyproto/anytype-ts · GitHub](https://github.com/anyproto/anytype-ts/issues/934)
												- [Provide an option to copy link to block](https://github.com/anyproto/anytype-ts/issues/935)
												-
										- Unclear
											- [Files can be exported to Markdown, or Any-Block (Protobuf and JSON)](https://doc.anytype.io/anytype-docs/basics/import-export)
										- Comparisons
									- https://github.com/anyproto/anytype-ts
									- 5-use code:
										- `mzykpf83sf`
										- Recovery phrase
											- `valid govern donor old sight grief roast mercy rifle skate pair sponsor`
									- # Documentation
										- ## [Sets](https://doc.anytype.io/anytype-docs/basics/sets-and-collections/sets)
											- [Anytype Sets - Notion Databases, but better. - YouTube](https://youtu.be/45-wRS8kFHo)
												- Basically each row has the same `Object type` e.g. `Object type: Book`
												- Each column is called a `Relation` e.g. Author, Title, etc
								- [Teable](https://github.com/teableio/teable)
								- https://github.com/toeverything/AFFiNE
								- ((6631e29c-5695-4a50-92cd-10285688826d))
								- ((649b131d-54ae-4050-ab97-fa37bd72445c)) for [[Logseq]]
							- Firetable/Rowy
							  collapsed:: true
								- [https://](https://firetable.io/)<a href="https://firetable.io/">firetable</a><a href="https://firetable.io/">.io/</a>
								- [https://github.com/rowyio/rowy](https://github.com/rowyio/rowy)
								- [https://github.com/AntlerVC/firetable](https://github.com/AntlerVC/firetable)
								- Demo
								  [https://try.firetable.io/table/mvpResources](https://try.firetable.io/table/mvpResources)
								- Roadmap
								  [https://github.com/AntlerVC/firetable/wiki/Roadmap](https://github.com/AntlerVC/firetable/wiki/Roadmap)
								- Pros/Cons
								  collapsed:: true
									- Pros
										- More advanced features than Baserow
											- Like 10+ field types
											  [https://miro.medium.com/max/2609/1*GvPoBsTKwp79PzVWqrfBkg.png](https://miro.medium.com/max/2609/1*GvPoBsTKwp79PzVWqrfBkg.png)
											- Export to CSV
										- Uses modern tech (React, TypeScript)
									- Cons
										- Lacks
											- Currently only compatible with Firestore (noSQL backend), more *might* happen
											  [https://github.com/AntlerVC/firetable/issues/228](https://github.com/AntlerVC/firetable/issues/228)
												- [https://firebase.google.com/docs/firestore](https://firebase.google.com/docs/firestore)
											- Web app to help deploy it
											  [https://github.com/AntlerVC/firetable/issues/140](https://github.com/AntlerVC/firetable/issues/140)
											- Views feature
											  [https://github.com/AntlerVC/firetable/issues/209](https://github.com/AntlerVC/firetable/issues/209)
											- Export is CLI-only. GUI is marked as WONTFIX
											  [https://github.com/AntlerVC/firetable/issues/160](https://github.com/AntlerVC/firetable/issues/160)
										- Firestore is noSQL
										  [https://firebase.google.com/docs/firestore/data-model](https://firebase.google.com/docs/firestore/data-model)
							- Budibase
							  id:: 634710bd-450a-4f04-b1fa-07e92fd236ab
							  collapsed:: true
								- Pros/Cons
									- Cons
										- Looks like more of a low-code app builder than a web spreadsheet-database
								- [https://www.budibase.com](https://www.budibase.com)
								- [https://github.com/Budibase/budibase](https://github.com/Budibase/budibase)
								- Website is a bit vague on detail right now... a few features:
									- Design your own data model: create typed fields, data validation rules, object relationships, indexing & scaling options
									- HTTP Api for all CRUD operations, based on your data model
									- User Management & User Role definitions
									- Generated UI, with the ability to drop in your own UI wherever suits
									- Fully pluginable backend, for integrations
									- Output is a Single Page Web application, with an HTTP Api & data storage. Web app will be mobile ready (PWA).
								- 1 Backlink
									- [Budibase](https://workflowy.com/#/2f84191e7219)
							- notion-clone
							  collapsed:: true
								- [https://github.com/konstantinmuenster/notion-clone](https://github.com/konstantinmuenster/notion-clone)
							- dwata
							  collapsed:: true
								- Demo
								  [https://demo.dwata.com/browse/0/content](https://demo.dwata.com/browse/0/content)
								- [https://github.com/brainless/dwata](https://github.com/brainless/dwata)
								- [https://dwata.com/](https://dwata.com/)
							- [Diwata](https://github.com/ivanceras/diwata/issues/7) (Elm)
							  collapsed:: true
								- [https://raw.githubusercontent.com/ivanceras/diwata/master/diwata1.png](https://raw.githubusercontent.com/ivanceras/diwata/master/diwata1.png)
								- I'm also working on a project similar to spreadsheet, but mine pertains closely to database than spreadsheets. I also planned to have an export to spreadsheet functionality
							- _Tables built automatically from queries_
							  collapsed:: true
								- See [Obsidian Dataview](https://workflowy.com/#/ba27815e45bc)
								- logseq queries
									- [https://docs.logseq.com/#/page/queries](https://docs.logseq.com/#/page/queries)
									- [https://discuss.logseq.com/t/what-are-the-limitations-to-using-logseq-properties-to-make-a-lightweight-queryable-graph-database-of-pages/7651](https://discuss.logseq.com/t/what-are-the-limitations-to-using-logseq-properties-to-make-a-lightweight-queryable-graph-database-of-pages/7651)
									- [https://discuss.logseq.com/c/queries/14](https://discuss.logseq.com/c/queries/14)
									- 1 Backlink
										- See [logseq queries](https://workflowy.com/#/6193e48249b1) for making databases
							- _Tables, not all-in-one_
							  collapsed:: true
								- Handsontable
								  https://handsontable.com/features
									- https://trello.com/b/PztR4hpj/handsontable-roadmap
									- It has multiple cell types, default is string (also numeric, time, date, checkbox, dropdown)
									  https://docs.handsontable.com/pro/4.0.0/demo-numeric.html
										- Also allows custom renderers using HTML e.g. hyperlinked images on S3 (uploaded/deleted via Mountain Duck)
										  https://i.imgur.com/vnMb94X.png
									- How to extend
										- Multiple sheets
											- You could use a simple HTML list with a js clicable tabs. Here's a good example how to do this. Then you only insert new HOT instance inside the tab.
											  http://www.htmldog.com/articles/tabs/
										- Hyperlinking
											- https://www.google.com/search?q=handsontable+link+to+another+sheet&ie=utf-8&oe=utf-8&client=firefox-b
									- Related: Airtable field types
									  intralink2:: https://workflowy.com/#/b5024f1fc745
								- SlickGrid
									- [cloned] https://github.com/6pac/SlickGrid
									- http://slickgrid.net/
									- Features
										- _Examples_
										  https://github.com/6pac/SlickGrid/wiki/Examples
										- Most comprehensive example
										  https://6pac.github.io/SlickGrid/examples/example4-model.html
										- Editing
											- Field types: text, completion bar, date, checkmark, textbox
											  https://6pac.github.io/SlickGrid/examples/example3-editing.html
											- Undo button + Redo
											  https://6pac.github.io/SlickGrid/examples/example3b-editing-with-undo.html
											- Sortable columns by ascending/descending and filter bar for one/two columns
											  https://6pac.github.io/SlickGrid/examples/example4-model.html
											- Expand record popup
											  http://6pac.github.io/SlickGrid/examples/example-composite-editor-item-details.html
											- Spreadsheet: cell range selection, copy'n'paste and Excel-style formula editor
											  https://6pac.github.io/SlickGrid/examples/example-spreadsheet.html
										- Additional options
											- Second header row
											  http://6pac.github.io/SlickGrid/examples/example-column-group.html
										- _View_
											- Responsive full-width
											  https://6pac.github.io/SlickGrid/examples/example15-auto-resize.html
											- DataView - e.g. show records instead as cards
											  http://6pac.github.io/SlickGrid/examples/example8-alternative-display.html
											- Movable columns and resizable
											  http://6pac.github.io/SlickGrid/examples/example2-formatters-event.html
											- Multiple tabs (equivalent to Airtable Views?)
											  http://6pac.github.io/SlickGrid/examples/example-dynamic-filtered-with-jquery-tabs.html
											- Per column filter
											  https://6pac.github.io/SlickGrid/examples/example-header-row.html
											- Multi-column sort
											  https://6pac.github.io/SlickGrid/examples/example-multi-column-sort.html
												- http://6pac.github.io/SlickGrid/examples/example-multi-column-tristate-numbered-sort.html
											- Grouping
											  https://6pac.github.io/SlickGrid/examples/example-grouping.html
											- Checkbox row selection
											  https://6pac.github.io/SlickGrid/examples/example-checkbox-header-row.html
											- Checkbox row selection #2
											  http://6pac.github.io/SlickGrid/examples/example-checkbox-row-select.html
											- Multiple row selection and drag-and-drop reordering
											  https://6pac.github.io/SlickGrid/examples/example9-row-reordering.html
											- Expandable additional info for each record
											  https://6pac.github.io/SlickGrid/examples/example16-row-detail.html
											- Hamburger menu - e.g. filter out columns, remove elements etc
											  https://6pac.github.io/SlickGrid/examples/example-grid-menu.html
											- Column tooltips
											  http://6pac.github.io/SlickGrid/examples/example-autotooltips.html
											- Column header dropdown menus
											  http://6pac.github.io/SlickGrid/examples/example-plugin-headermenu.html
										- Select2 dropdown editor (don't have to type in an option in a cell - instead select from a dropdowm
										  https://6pac.github.io/SlickGrid/examples/example-select2-editor.html
										- Autocomplete type dropdown
										  http://6pac.github.io/SlickGrid/examples/example-dynamic-filtered-with-jquery-tabs.html
										- Select2 multi-select dropdown
										  https://6pac.github.io/SlickGrid/examples/example-select2-multiselect-editor.html
										- Another multi-select
										  https://6pac.github.io/SlickGrid/examples/example-multiselect-editor.html
								- Recline.js (based on SlickGrid)
									- Cons
										- Complicated setup compared to plugging in a SQL db or creating an Airtable base
										- Abandoned since 2017 - founders now working on an open dataset company
									- https://github.com/okfn/recline
									- Demos
									  http://okfnlabs.org/recline/demos/
									- Docs
									  http://okfnlabs.org/recline/docs/
									- Numerous backends
									  http://okfnlabs.org/recline/docs/tutorial-backends.html
										- gdocs: Google Docs (Spreadsheet)
										- csv: CSV files
										- xlsx: Excel files
										- solr: SOLR (partial)
										- elasticsearch: ElasticSearch
										- dataproxy: DataProxy (CSV and XLS on the Web)
										- ckan: CKAN – support for CKAN datastore
										- couchdb: CouchDB
										- memory: Memory (local data)
								- DataTables
									- https://github.com/DataTables/DataTables
									- https://datatables.net/
							- ((67a8e14d-6d01-4753-b06e-5351e661a98b))
							- DataSpread
							  collapsed:: true
								- https://dataspread.github.io/
								- https://github.com/dataspread/dataspread-web
								- Latest version uses Handsontable
								-
							- Hillview
							  collapsed:: true
								- https://github.com/vmware/hillview
							- Dataface
							  collapsed:: true
								- https://github.com/timwis/dataface
							- bizsitegenie
							  collapsed:: true
								- [cloned] https://github.com/dreamerkumar/bizsitegenie
								- video
								  https://player.vimeo.com/video/167171173
							- Frappe
							  collapsed:: true
								- Frappe DataTable
								  https://user-images.githubusercontent.com/9355208/40740030-5412aa40-6465-11e8-8542-b0247ab1daac.gif
									- https://frappe.io/datatable
									- https://github.com/frappe/datatable
								- FrappeJS
								  https://frappe.io/assets/frappe_io/images/landing-pages/frappejs.png
									- https://frappe.io/frappejs
									- https://github.com/frappe/frappejs
								- _Non-Airtable like_
									- https://frappe.io/erpnext
									- https://frappe.io/gantt ((663a0528-7561-41e3-ae6d-34b4dc2e4d26))
									- https://frappe.io/accounting
									- https://frappe.io/charts
									- Frappe Framework
										- https://frappe.io/frappe
										- https://github.com/frappe/frappe
										- Metadata driven, Low Code Web Framework in Python & JS. Used to build ERPNext
							- _Headless CMS-based_
							  collapsed:: true
								- Pros
								  collapsed:: true
									- Typically they have
										- Revision history
										- API-driven (can output to a outliner-style UI if desired)
								- Directus (JS + PHP)
								  collapsed:: true
									- [cloned] https://github.com/directus/directus
									- https://getdirectus.com/
									- Roadmap
									  https://feathub.com/directus/directus
									  https://getdirectus.com/
									- https://medium.com/directus/user-guide-a-tour-of-directus-9be0ff945ebf
								- GraphCMS
								  collapsed:: true
									- https://graphcms.com/
									- https://medium.com/graphcms-official-blog/graphcms-ready-for-dd4417da5a9e
								- Silverstripe
								  collapsed:: true
									- https://www.silverstripe.com/
								- https://headlesscms.org/
								-
							- VFront
							  collapsed:: true
								- http://www.vfront.org/
								- https://sourceforge.net/projects/vfront/
								- VFront is not a database administration tool like phpMyAdmin and it's not replacing it : interface is for basic non-expert users working on data.
								- VFront you can create forms for manage your data in AJAX style, different rules and privileges for groups, report in XML,HTML,PDF,statistics and much more.
							- nuBuilder
							  collapsed:: true
								- https://www.nubuilder.net/
								- https://sourceforge.net/projects/nubuilder/
								- Possibly abandoned now - sourceforce not updated since 2016?
							- Limbas
							  collapsed:: true
							  German-based
								- https://www.limbas.com/en/
								- https://sourceforge.net/projects/limbas/
							- Collabora Online Base (not announced, wishlist)
							  collapsed:: true
								- https://www.collaboraoffice.com/news/
							- _Abandoned_
							  collapsed:: true
								- Xataface
								  Last release 2015
									- http://xataface.com/
								- Crudin
								  Abandoned since 2013
									- https://sourceforge.net/projects/crudin/
						- ## Desktop-based
							- [DataLoom](https://github.com/trey-wallis/obsidian-dataloom) for ((657b8767-8071-48fb-96df-f30379dc796b))
							  id:: 6631e29c-5695-4a50-92cd-10285688826d
							  collapsed:: true
							  AKA Notion-Like Tables
								- Pros/Cons
									- Pros
										- Can export to CSV or Markdown
										- Has mobile support
										- Multiple sort options
										- Filtering
									- Cons
										-
									- Unclear
									- Comparisons
								- Lacks
									- [Use the Tab key to switch cells · Issue #549 · trey-wallis/obsidian-dataloom · GitHub](https://github.com/trey-wallis/obsidian-dataloom/issues/549)
									- [Export to Google Sheets / Excel](https://github.com/trey-wallis/obsidian-dataloom/issues/452#issuecomment-1961599136)
									- [Advanced database interoperability](https://github.com/trey-wallis/obsidian-dataloom/issues/491#issuecomment-1824736162)
									- [Content search](https://github.com/trey-wallis/obsidian-dataloom/issues/474#issuecomment-1734225532)
										- [2](https://github.com/trey-wallis/obsidian-dataloom/issues/436#event-e4945d4c-f190-51ad-abf5-05cc21b6dd84)
									- [Multiple file attachments in one column](https://github.com/trey-wallis/obsidian-dataloom/issues/676#event-10078155302)
									- [Group by](https://github.com/trey-wallis/obsidian-dataloom/issues/659)
								- Related: ((649b131d-54ae-4050-ab97-fa37bd72445c)) for [[Logseq]]
							- Kexi
							  collapsed:: true
								- http://www.calligra.org/kexi/
							- ((680abbd5-a3bd-4a6b-9816-2674ecbf240c))
							- LibreOffice Base
							  collapsed:: true
								- Features
									- Link columns from different tables together
									  https://www.youtube.com/watch?v=UHkCbQL51r4
								- Documentation
									- 95 video playlist
									  https://www.youtube.com/playlist?list=PLy7Kah3WzqrEerJ0VPNWVaR4CYHMr4wmV
									- Create auto ID column
										- Create table in design view
										- Field Name: ID
										- Field type: integer
										- AutoValue: Yes
										- Description: Unique record number
									- Use 'Text [VARCHAR]' rather than FIXED (it doesn't store whitespace basically)
									- Exporting data
									  https://help.libreoffice.org/Common/Importing_and_Exporting_Data_in_Base
							- Apache OpenOffice Base
							- Symphytum
							  collapsed:: true
								- http://giowck.github.io/symphytum/
						- Related:
							- AppWrite
							- See [Docker vs Flatpak](https://workflowy.com/#/e757ceafb96d) ((63a873fd-893d-4ed7-ae5b-e27945e68230))
					- # Proprietary
						- [Airtable](https://airtable.com)
						  id:: 6525b49d-1200-4868-9453-784db52d5987
						  collapsed:: true
							- Tech stack
							  collapsed:: true
								- Comments
								  collapsed:: true
									- We have a custom frontend framework that supports realtime data synchronization. We use some pieces of other frameworks, like Backbone's routing and events library.
									- We use node on the backend, and have our own realtime database engine that supports relational data, and out-of-order undo. We also have a custom frontend framework that consumes the realtime changes pushed from all other clients.
									- We've closely followed the developer blogs of both those projects (and in Meteor's case, their source code). With those learnings, we built our own realtime database engine that supports relational data (which Meteor doesn't yet support) and also some other major features like the ability to undo any user action out of order (like git revert), which is necessary to support undo in a multi-user context (because the last thing that you did may not be the last change globally if other people are concurrently making changes). Undo is a particularly challenging feature to implement in a structured relational database context, because it can't be reduced to a set of simplistic character insertion operations as is the case for a google word doc, or a spreadsheet (which is a simple 2d array of values without type constraints, foreign key relations, etc).
								- http://underscorejs.org/
								- React
								  collapsed:: true
								  https://medium.com/@matt_bush/how-airtable-uses-react-5e37066a87d4
									- Initial considerations
										- Airtable’s web client codebase at the time consisted largely of two types of classes: model classes, which keep data in sync in realtime between web clients and Airtable’s servers, and component classes, which render model-based data and other data to the DOM. As a library for building user interfaces, React would take the place of our existing components; meanwhile, we could continue to use existing model code for storage, state changes, and permission checks. This consideration made React preferable to a more opinionated full-stack framework which would require adapting or replacing our model layer.
									- I  went ahead with a pilot project. I rewrote our view configuration menus in React, which include our filtering and sorting menus. After those changes were written, tested, and shipped, and we saw the above benefits, we decided to adopt React more widely across our codebase.
									- We prioritized rewriting parts of our product where lots of new features were planned. Rather than adding features to the pre-React version of a component, we usually preferred to first rewrite the component in React and then add new features on top of the React rewrite. We found that the latter approach has been easier to code review and easier to maintain in the long run, making it worthwhile even taking into account the one-time cost of the rewrite.
									- Looking back one year later
									- A year into using React, we’re thrilled with how it has enabled us to write UI code at a higher level of abstraction, and has inspired a more disciplined and consistent approach to managing application state. We were reminded of this during the “aha” moments we got from our summer engineering interns when they came to grasp React’s benefits after working with it for a few weeks. Our success with React has also encouraged us to adopt other JavaScript features that are supported by the Babel transpiler, like ES2015 classes and ES2017 async functions.
							- New features (last checked: Tue, Sep 1, 2020 )
							  collapsed:: true
							  https://airtable.com/whatsnew
								- Rich text fields
								  [https://community.airtable.com/t/formatting-options-for-long-text-now-accepting-beta-testers/2093/160](https://community.airtable.com/t/launched-rich-text-formatting-for-long-text-fields-now-live-for-everyone/28400)
								- Last modified time field/function
								- ((663a0528-7561-41e3-ae6d-34b4dc2e4d26))
								- Airtable web clipper
								- Flashcards block
								- URL preview block: Loom, Google Drive/Docs/Sheets/Slides
								- Link to views/tables in a different base
									- [source] [https://support.airtable.com/hc/en-us/articles/360052521254](https://support.airtable.com/hc/en-us/articles/360052521254)
									- However can't link to individual rows
									  https://community.airtable.com/t/link-to-other-base/107/459
							- Beta features
							   / https://airtable.com/shrLK2dGvhx46S6bU
							- **Backing up Airtable automatically**
							  collapsed:: true
								- Can sync it to a SQL database via API
									- Zapier + SQL ($20/month)
									  https://zapier.com/apps/airtable/integrations/mysql
									- Zapier + Openside ($50/mo)
									  https://community.airtable.com/t/how-to-set-up-automatic-external-backups-for-airtable-in-20-minutes/18944/5
										- They have a connector which works like Zapier to export all bases to JSON
										- And another plugin which converts the JSON to CSVs
											- If you search the web for JSON to CSV script and the name of the language you want to use, you should have no trouble locating what you need.
								- Self-hosted
									- Incomplete script
									  https://github.com/rickh94/airtable_local_backup
										- Set the `ATDB` environment variable to AirTable base key (e.g. `appXZYtTtmCwA9zAA`)
									- Airtable official API
										- https://github.com/Airtable/airtable.js
										- https://airtable.com/api
									- Info
										- you can use formula fields to expose each record’s RECORD_ID() and use lookup fields to expose the RECORD_ID() of any related records. Then it’s a matter of rebuilding your data structure in SQL (plus any required “join” tables) and creating queries from each CSV record using the exposed RECORD_ID() as the primary key for each record.
											- Also use LAST_MODIFIED_TIME to determine if to sync a record (general release in March possibly?)
											  https://community.airtable.com/t/last-modified-time/18867/204
										- How to handle the 100 pagesize limitation
											- The server returns one page of records at a time. Each page will contain pageSize records, which is 100 by default. If there are more records, the response will contain an offset. To fetch the next page of records, include offset in the next request’s parameters
											- So in my code (which is server side PHP), I do a loop at the bottom of which I check if the returned offset is null or not. If it is NOT null, then I let the loop continue with the new offset. Eventually (depending on just how many records match your filter or are in your view/table) the offset isn’t returned, or is NULL, thus breaking the loop.
											- So no waiting is required, each result contains the information required to determine if an additional request is needed or if all the result have been returned.
											- PHP example
											      <?php
											      // Initialize the offset.
											      $offset = 0;
											  
											      // Initialize the result set.  
											      $records = array();
											  
											      // Make calls to Airtable, until all of the data has been retrieved...
											      while (!is_null($offset)):
											       
											       // We're using an offset to get specific batches of records.
											       if ($offset > 0){
											        $http_params["offset"] = $offset; 
											       }
											       
											       if (isset($params["view"])){
											        // And we're specifying a view. The API will honor any filters 
											        // that have been applied to the view, as well as any sort
											        // order that has been applied to it.
											        $http_params["view"] = $params["view"];
											       }
											       
											       if (isset($params["fields"])){
											        // By default, the APi will return every column/field
											        // You can specify smaller specific fields only
											        // using this query parameter, as we are here.
											        $http_params["fields"] = $params["fields"];
											       }
											  
											       if (isset($params["limit"])){
											        // By default, the APi will return 100 records per request.
											        // You can specify smaller batch sizes using the "limit"
											        // query parameter, as we are here.
											        $http_params["limit"] = $params["limit"];
											       }
											       
											       if (isset($params["sort"])){
											        // We're also specifying a sort order for the request,
											        // which will override any sort order that has been 
											        // applied on the view.    
											        if (is_array($params["sort"])){
											         $http_params["sort"] = $params["sort"];
											        } else {
											         $http_params["sort"] = array($params["sort"],"asc");
											        }
											       }
											  
											       if (isset($params["filterByFormula"])){
											        $http_params["filterByFormula"] = $params["filterByFormula"];
											       }
											  
											       // Specify the URL to call.
											       $curlopt_url =   $this->AIRTABLE_API_URL
											                   . $this->APP_ID
											                   . '/' . rawurlencode($endpoint)
											                   . "?" . http_build_query($http_params);
											  
											       $args = array(
											           'timeout'     => 30,
											           'redirection' => 5,
											           'blocking'    => $blocking,
											           'headers'     => $http_headers,
											           'cookies'     => array(),
											           'body'        => null,
											           'compress'    => false,
											           'decompress'  => true,
											           'sslverify'   => true
											       );
											  
											       $response = wp_remote_get( $curlopt_url, $args );
											  
											       // When getting a table, we'll build an array of records,
											       // when getting a record, we'll just return the record.
											       if (isset($body["records"])){
											        $records = array_merge($records,$body["records"]); 
											       } else {
											        $records = $body;
											       }
											  
											       // Adjust the offset.
											   // Airtable returns NULL when the final batch of records has been returned.
											   $offset = (isset($body["offset"]))? $body["offset"] : null;
											  
											  endwhile;
											  ?>
										- e! I was able to to significantly limit the records being requested by creating both views in Air-table and using filterByFormula via the API. The filterByFormula request used RECORD_ID() to pull only records from an “item details” table that matched records in the “order submissions” table (i.e. rather than requesting the detailed info of all items, we only requested the detailed info for items that customers actually ordered).
									- Lacks
										- Airtable metadata API
											- Zapier obviously uses this, but there's no public release
											- Without it you’ll have to create the SQL tables/fields manually in order to match and maintain the number of fields and the types of fields
											- Feature request has gone unanswered
											- It's possible to pull the JSON from the page to formulate it
												- created a node script that launches a browser environment and downloads the schema to a json file. https://github.com/cape-io/airtable-schema
												- https://github.com/Airtable/airtable.js/issues/12#issuecomment-349987627
												- https://community.airtable.com/t/accessing-tables-model-via-api/13408/5
												-
									- More info
										- What I have done on several Wordpress websites is cache Airtable requests locally to ensure a speedy response. This way I can use the filterByFormula parameter in the API to make quite complex requests and then cache the entirety of the JSON result using a hash of the original request. The end result is that Wordpress can serve data quickly from it’s own local SQL database, but I get all the goodness of Airtable’s interface for managing data. The only “drawback” is the learning curve of switching from SQL queries to Airtable filterByFormula—but it’s not so bad with their great documentation.
											- So if you can’t serve data directly from the Airtable API, don’t “sync” it—cache it so that you can take full advantage of the Airtable GUI and API while getting local database read speeds.
							- I use this to keep track of most of our FAQ and vendor data at work. I also need to keep track of part  associated with different products in sourcing items overseas, so its imperative I have a relational-database schema
							  collapsed:: true
								- Spreadsheets, databases and outliners may not be quite as user-friendly for user-driven entered / complex data, but airtable is amazing
								- I currently use it to organize books I've read, movies I've seen, TV shows I watched, food recipe shortlinks, and all of the relational database asset managements for our company
								- Dynalist is still where I use to track my stream-of-thought-process and all my project wikis, and my changelogs on every other project I work on
							- Pros/Cons
							  collapsed:: true
								- Pros
									- Features
										- Grid view, calendar iew, gallery view, kanban view
										  https://cdn.zapier.com/storage/photos/c7b63e028b0ada7935cef118bc81ed70.gif
											- https://support.airtable.com/hc/en-us/articles/202624989-Guide-to-views
										- Many field types
										  http://i.imgur.com/Rt3j1oL.png
											- Single line text, Long text; Attachment; Checkbox, Multiple Select; Single select; Link to another record; Collaborator; Rating; Rollup; Count; Lookup; Created time; Date; Phone number; Email; URL; Number (numerical); Currency; Percent; Duration; Formula; Autonumber; Barcode;
										- Templates
										  https://airtable.com/templates
									- Blocks
									  https://dl.airtable.com/aOxBqBEnQX6he4WkkF9E_full_New%20Dashboard.png
										- https://blog.airtable.com/introducing-airtable-blocks/
										- Visualisation (charts, graphs) - part of Blocks
										- Map, bar chart, timeline/gantt; OCR, send SMS,
										- bar/line/scatter chart; page designer (e.g. enhanced version of Form view)
										- Google Cloud Vision (e.g. identifies images with description text)
										- Models (3D model viewer)
										- Countdown, time tracker, video conference
										- https://airtable.com/blocks
									- ctrl + K to swap bases
									- Last Modified field (can be used with project overview/tracker bases to more plainly see estimated + actual last modified dates)
								- Cons
									- Not open-source
									- No local offline data storage
										- [https://community.airtable.com/t/fr-offline-mode/625/237](https://community.airtable.com/t/fr-offline-mode/625/237)
									- Missing features
										- _Missing features to replace uTracker_
											- Forms is comparable to uTracker but lacks some key features (below)
											  https://try.airtable.com/static/forms/drag-and-drop.gif
											- _Lacks_
												- Forms view is not available in mobile apps
												  https://community.airtable.com/t/access-to-forms-on-mobile-device/5793/4
													- If you use Android, you can open the 3dot menu and click “Request desktop site” which will take you to the full Airtable website.
													- Example form - can be done from web but not on Android
													  https://airtable.com/tbl15pWTVsbAjKRXr/viwRfYAU75muC2lfD
												- Export to CSV button on Android app
												- Unable to flip rows and columns display (so each column is like a single day's record e.g. one Morning Routine per column)
												  https://community.airtable.com/t/switch-rows-and-columns-display-in-grid-view/4446
										- Native notifications
										  [https://community.airtable.com/t/calendar-view-enhancement-requests-reminders-delete-prompts-persistent-view/1236/111](https://community.airtable.com/t/calendar-view-enhancement-requests-reminders-delete-prompts-persistent-view/1236/103)
										- Export base(s) - can only do per view/table currently
										  https://community.airtable.com/t/download-snapshots/183
										- Granular/advanced user permissions
										  https://community.airtable.com/t/advanced-user-permissions/824/214
										- Blocks on mobile
										  [https://community.airtable.com/t/airtable-blocks-on-mobile/16796](https://community.airtable.com/t/airtable-blocks-on-mobile/16796/14)
										- _Not likely - self-hosted_
											- Choose Dropbox or Google Drive for attachment storage
											  https://community.airtable.com/t/choose-dropbox-or-google-drive-for-attachment-storage/3519
											- On premise self-hosted version
											  https://community.airtable.com/t/on-premise-self-hosted-version/4684
						- ((6525b49e-8fcd-4440-9a3e-3c65d4edb58b))
						- ((657b8767-8071-48fb-96df-f30379dc796b)) : ((683181f7-8e2f-435f-80a5-99becdd6a995))
						- Forest Admin (partly FOSS)
						  collapsed:: true
							- [https://www.forestadmin.com/](https://www.forestadmin.com/)
							- admin panel
							- Part FOSS
								- Database stored on your own server
								- Web app frontend for database manipulation is on their servers
							- [https://medium.com/@SeyZ/myth-4-i-would-never-externalize-my-admin-panels-development-badcd4b5e255](https://medium.com/@SeyZ/myth-4-i-would-never-externalize-my-admin-panels-development-badcd4b5e255)
						- Microsoft Lists (announced for Q3 2020)
						- Zenkit
						  collapsed:: true
							- https://zenkit.com/wp-content/uploads/2018/08/table.gif
							- Pros/Cons
								- Cons
									- Android app doesn't work offline (Jan '19)
							- Similar to Notion it uses multiple views (list, Kanban, spreadsheet, mindmap)
							  https://alternativeto.net/software/zenkit/
							- https://zenkit.com/en/features/
							- https://play.google.com/store/apps/details?id=com.zenkit.zenkit
						- Memento Database (Android, Windows)
						  collapsed:: true
							- Links
								- https://play.google.com/store/apps/details?id=com.luckydroid.droidbase&referrer=utm_source%3Dappsite
								- https://mementodatabase.com/
								- http://wiki.mementodatabase.com
								- Changelog
								  https://www.facebook.com/pages/category/Software/mementodatabase/posts/
							- Pros/Cons
								- Pros
									- Unlimited local libraries (equivalent of bases/spreadsheets)
								- Cons
									- Cloud use costs $3/month
							- App description
								- **KEY FEATURES**
									- • Storing entries with custom fields.
									- • Performing Data analysis, including aggregation, charting, sorting, grouping, and filtering entries by any fields.
									- • Displaying data in the form of a list, a set of cards, a table, on a map, or in a calendar.
									- • Synchronization with Google Sheets.
									- • Cloud storage and Teamwork, by providing access to libraries to other users.
									- • Offline data entry.
									- • Access to data from several Android devices and from laptop and desktop
									- computers; users can work with the same libraries on their phones,
									- tablets, and PCs.
									- • Building the data collection form.
									- • Dozens of types of fields, including text, integer, real, boolean, date/time, rating, checkboxes, radio buttons, currency, image, signature, file, audio, contact, calculation, JavaScript, geolocations with Google Maps coordinates, and others.
									- • One-to-many, one-to-one, and many-to-many relationships between libraries.
									- • Importing and exporting CSV files, permitting interoperation with popular programs like Microsoft Excel, Filemaker.
									- • Populating database entries at the touch of a button with data from Web services and other sources.
									- • Scripting (triggers , scripted data source).
									- • Password protection (encrypt entries using AES-128).
									- • Charts — Pie, Line, Bar, Columns, Area, Scatter, Stepped Area.
									- • Aggregation: sum, maximum, minimum, average.
									- • Reminders.
									- • Sending entries via SMS, e-mail, and other available services.
									- • Searching entries in database by barcode.
									- • Online catalog of database templates -- thousands of templates available.
								- **TARGET USERS & USE CASES**
									- • the casual, perhaps single-library user who just wants to throw up a grocery list, collections or recipe repository.
									- • the intermediate user who might want to have some related libraries tracking some activities.
									- •
										- the power user who might be pushing the boundaries in certain areas,
									- like scripting, complex data structure, retail or barcode solutions,
									- media solutions, inventory, product catalogs, charting, or others.
									- •
									- the organizational / business user who might need teamwork
									- collaboration, cross-platform compatibility, cloud storage &
									- coordination, offline data collection and others.
									- Memento's
									- online catalog of user templates contains thousands of predefined,
									- ready-to-use libraries to use directly or serve as a starting place. It
									- also gives users the opportunity to familiarize themselves with a large
									- number of ways to use Memento to provide solutions.
								- **SYNCHRONIZATION**
									- Elements
										- of a user's database — libraries (tables) and associated files — may be
										- synchronized across devices via an available cloud service.
									- Database
										- also may be synchronized with Google Sheets to enable the user's data
									- to be manipulated or analyzed by either tool, as needed.
									- Import/export from/to CSV-files enables coordinated use with external applications, like Excel.
									- All
										- data can be stored in the Memento Cloud. All such records, photos, and
									- files are synchronized automatically between the cloud and local copies
									- on Android devices. Users can provide access to their data to other
									- users, enabling teamwork use.
								- **GLOSSARY**
									- • Database - a
									- general term for an organized set of data, gathered and organized for a
									- purpose, generally comprising multiple libraries.
									- • Library - a container for entries (records, rows) of fielded data , equivalent of a spreadsheet.
									- • Field - a data structure for a single piece of data, equivalent of a spreadsheet column.
							- _Comparison to uTracker_
								- Pros/Cons
									- Pros
										- Has tabs at the top of each Tracker Entry to allow for multiple sections (similar to how OpenDataKit had multiple pages)
										- More item types (data fields) e.g. screenshots
									- Cons
										- UX is a bit confusing initially but doesn't actually take more clicks - it's more that I'm not used to it yet
										- Currently trying to find equivalent to my TimeSince function - days in possible but unsure about mins/hours. | (i.e. mins/hours/days based since a value was inputted for a particular field in a previous entry)
											- Question asked
											  https://groups.google.com/forum/#!topic/mementodatabase/z_bQ9yY_3TA
											- Feature request for a calculation field allowing easy comparing previous + current entries is popular, but years old
											  https://memento.uservoice.com/forums/110673-general/suggestions/6870788-calculations-on-previous-and-current-fields
										- Exporting is less flexible but maybe sufficient
											- You can only export tracker entries to CSV individually
											- You can export everything in one click, but unlike uTracker it's in a DB format and you can only export photos/media with a Pro subscription
									- _Neutral_
										- _UX differences_
											- Because of the tabbed sections swiping left/right on the tracker body changes between sections rather than entries, but there is arrows at the bottom like uTracker (and I'd change the UX so that swiping on that bottom bar would swap between entries)
										- Calls each Tracker a "Library"
								- Whereas the default view for opening a Tracker is the Form View, the default here is a list view (similar to Airtable's mobile Grid view with one record per row). It also has a table and cards view
							- rTracker functions creation
								- Time Since - created an Upwork project to ask
								- Show Last - showing sleep time in wake routine; previous day's review, morning's goals, last weight when  in today's; weighed, last exercise performance; show in Evening Routine from Morning Routine "What is Next Action?" for review;
								- Sum
									- For morning routine yes/no "taken current stack"/"how many times in past 2 weeks taken?"; for Social: Meet sum of £ spent this month on meets (+ Social: time spending showing the same data)
									- No. of entries - in Social: time spending - how many meets in the past week/month (Social: Meet tracker entries);
									- Total amount of Meets in the last month
									- Cost-Benefit Analysis: ROI multiple (benefit in hrs - cost in hours)
								- Multiply -
									- Days Spent @ Â£100/day (*cost in £) in STUFF Spending tracker
							- Features
								- Possible feature equivalent to Functions
									- http://wiki.mementodatabase.com/index.php/Calculation_field
									- http://wiki.mementodatabase.com/index.php/JavaScript_field
									- Mass calculations (sum, maximum, minimum, average);
							- Requested features
							  https://memento.uservoice.com/forums/110673-general/filters/top
								- Web app
									- There's a web API available
									  https://mementodatabase.docs.apiary.io/#reference/0/entry/get-a-single-entry
									- requested
									  https://memento.uservoice.com/forums/110673-general/suggestions/7266078-instead-of-desktop-a-browser-version-would-be-nic
							- Mobile edition is similar to uTracker in many ways
							  https://lh3.googleusercontent.com/Xy-7FTbCyJap5dYhwabG5Cd8W6fx6N9QfWJq36mhm_9qrQzCt9tvkdxiieC76vTgFD43=w1109-h658
								- 1
								  https://lh3.googleusercontent.com/mE1pJxjGVbPFihg-9O1qBPf9ID6eHqvc7MSkg8LbpcPR026AcBqR9dHY3x0sFWx4rzk=w1109-h658
								- 2
								  https://lh3.googleusercontent.com/yrQiXKZ0idpzovAvvm8wdNjU_U3wb1NSlZ5_tNWLtwol4LRsssFYHCUpg1EJR81bsg=w1109-h658
								- 4
								  https://lh3.googleusercontent.com/azkaxpghgYNFvcrU2pYIjvniFT-JKF6Iv74Zw9ZFhvWTwYGfUthwC8ERIv1qOmvZhHU=w1109-h658
							- Desktop edition
							  https://mementodatabase.com/images/screenshots/desktop_main.png
								- https://mementodatabase.com/images/screenshots/desktop_entry_edit.png
								- https://mementodatabase.com/images/screenshots/desktop_edit_library.png
						- MobiDB
						  collapsed:: true
							- https://mobidb.mobi/
							- https://alternativeto.net/software/mobidb-database-designer/
						- [Fieldbook](https://fieldbook.com)
						  collapsed:: true
							- Allows exporting all data programmatically
								- https://docs.fieldbook.com/docs/import-and-export
								- https://github.com/hay/fieldbook-download
						- [Smartsheet](https://www.smartsheet.com)
						- Google Sheet as a backend
						  collapsed:: true
							- https://github.com/jsoma/tabletop
							- http://jlord.us/sheetsee.js/
						- [Zoho Creator](https://www.zoho.eu/creator/)
						- FileMaker
						- [Process Street](https://www.process.st) grid view
						  collapsed:: true
							- https://www.process.st/process-street-2-0/
					- Unsorted
						- [Budibase | Build internal tools in minutes, the easy way](https://budibase.com/)
						- [No-code open source database and application builder | Baserow](https://baserow.io/)
						- [The Open Source Headless CMS (and More)](https://directus.io/)
						- [Strapi - Open source Node.js Headless CMS 🚀](https://strapi.io/)
						- [NocoDB Cloud](https://nocodb.com/)
						- [KeystoneJS: The superpowered Node.js Headless CMS for developers - Keystone 6](https://keystonejs.com/)
						- [Saltcorn - open-source no-code](https://saltcorn.com/)
						- [Plasmic | Build powerful apps fast— without the limits](https://www.plasmic.app/)
						- [Appsmith | Open-Source Internal Tool Builder](https://www.appsmith.com/)
						- https://www.jigdev.com/
						- [Sanity: The Composable Content Cloud](https://www.sanity.io/)
						- [Build Custom Business Apps with No-Code | Jet Admin](https://www.jetadmin.io/)
						- [Dashibase | No-code dashboards for Supabase and Postgres](https://dashibase.com/)
						- [Corteza - Corteza](https://cortezaproject.org/)
					- Related:
						- ((629ccb26-fc95-4474-af25-e941969486e0))
						- ((6463499c-a3c8-4548-a7e9-8b2ef09bef9a))
						- ((634710c3-5aa0-4751-84bd-8217dc0f8247))
				- Quip
				  intralink2:: https://workflowy.com/#/f0bb1071a556
				- CryptPad zero knowledge spreadsheets (planned)
				  intralink2:: https://workflowy.com/#/322e4425a5b6
				- OpenPaaS spreadsheet
				  intralink2:: https://workflowy.com/#/08582539aa89
				- EtherCalc
				  collapsed:: true
					- Pros
						- Multi-sheet
						  https://ethercalc.org/=8cmx1t9i14mh
							- https://github.com/audreyt/ethercalc/issues/138
							- Add a = before /
							  https://ethercalc.org/=8cmx1t9i14mh
						- API
						  http://docs.ethercalc.apiary.io
					- Cons
						- Needs a Zapier integration (or freelance-dev)
						- Needs an easy way to link to cells/rows/columns in other spreadsheets
					- https://github.com/audreyt/ethercalc
					- https://opensource.com/life/15/12/5-open-source-web-apps-self-hosted
					- Demo
					  https://ethercalc.org/to4snxgsx9mi
					- https://apps.sandstorm.io/app/a0n6hwm32zjsrzes8gnjg734dh6jwt7x83xdgytspe761pe2asw0
				- ONLYOFFICE Online
				  + FileRun?
				- Collabora Online/CODE
				  collapsed:: true
				  Nextcloud server + LibreOffice Online
					- https://nextcloud.com/collaboraonline/
					- Development is slow and featureset is bare minimal
					- Tasks
						- Fulfil the instructions here and setup Collabora Online on collab.postmymed.com alongside our Nextcloud at icloud.postmymed.com
						  https://nextcloud.com/collaboraonline/
						- Setup Let's Encrypt auto
						  https://www.digitalocean.com/community/tutorials/how-to-secure-apache-with-let-s-encrypt-on-ubuntu-14-04
			- _Content for database format_
				- Watched TV shows/anime
				  _See_ [Anime](https://workflowy.com/#/eaa1a764598b)
				- Read fanfics
				  collapsed:: true
					- Organise by
						- Fandom (Naruto, Worm, multicross)
						- Status: up-to-date/not read yet/paused/complete/abandoned
						- Rating out of 10
						- Type: Self-insert / OC / time travel / AU minor/large/different universe /
					- _See_ [Fiction](https://workflowy.com/#/9133fa9459e2)
						- [Web Serial](https://workflowy.com/#/0d389dbd8870)
				- Played games
				- Contacts / CRM / G Leads
				- ((633b7546-8735-4803-8694-43f949258c50))
				  collapsed:: true
					- e.g. Privacy yes/no, utility yes/no, entrepreneurship yes/no
				- _See_ [Usecases](https://workflowy.com/#/ceb6eccf20ec)
		- _Google Drive alternative_
		  collapsed:: true
			- CryptDrive
				- https://blog.cryptpad.fr/2017/06/21/CryptPad-Jackalope-file-upload-pdf-and-pictures/
			- OpenPaaS
			  Very Nextcloud-like, with many apps including LibreOffice Online-like
				- https://www.open-paas.org/
			- Seafile
			- Nextcloud
			- Nextcloud
		- _Related: _
			- ((6318fd16-eaf2-4f5a-a107-0178e65fdee9))
			  #Software-File
			- Wireframing
			  #Management [https://workflowy.com/#/0b6576803896](https://workflowy.com/#/0b6576803896)
	- Mind Map
	  id:: 649161c9-8d84-401d-9ca6-af28145da219
	  collapsed:: true
		- _Proprietary_
			- Roam Research
			  [https://roamresearch.com/assets/images/Roam-Group-min.png](https://roamresearch.com/assets/images/Roam-Group-min.png)
			- Obsidian (by makers of Dynalist)
			  [https://obsidian.md/images/screenshot.png](https://obsidian.md/images/screenshot.png)
			- OrgPad
				- [https://orgpad.com/](https://orgpad.com/)
		- _Open-source_
			- Foam (different model)
			  collapsed:: true
			  [https://foambubble.github.io/foam/assets/images/foam-features-dark-mode-demo.png](https://foambubble.github.io/foam/assets/images/foam-features-dark-mode-demo.png)
				- [https://foambubble.github.io/foam/roadmap](https://foambubble.github.io/foam/roadmap)
					- Mobile support
				- Documentation
					- Setup
						- ((63209272-1088-4824-a762-4ac7ded04b0a)) extensions
							- Markdown All in One, Prettier, GitLens
							- tchayen.markdown-links
							  Provides the graph for markdown file interlinking
							- foam.foam-vscode
					- [[wiki-links]]
					- [https://foambubble.github.io/foam/recommended-extensions](https://foambubble.github.io/foam/recommended-extensions)
			- Org-Roam
			  #Outliners [Org-roam](https://workflowy.com/#/5351330476f0)
			- Plugins for TiddlyWiki
			  #Software-PM [Roam Research-like](https://workflowy.com/#/17f4b2ff17ab)
			- Memex by steve-1820 uses this
			  ((633b7546-8735-4803-8694-43f949258c50)) [directed graph-like visualisation for interlinking](https://workflowy.com/#/956c258a2b51)
		- _Related: [Outliner types ](https://workflowy.com/#/88864c616a9b)_
		  #Outliners
	- ((64098f0e-0cc1-4158-962e-5042cb5d8230))-like
	  collapsed:: true
	  Traditional Project Management
		- Most promising
			- ((644c09ca-07ac-4f1b-b377-da8dc0fd082e))
			- ((66a965fd-d096-4334-a5e5-faa6691e13af))
			- ((64943ac4-fa3b-418a-aff0-d110c197b005)) - now has Kanban, Scrum, Issues, etc
			- ((6497200c-27f2-465e-a699-aa85c137704d))
			- ((64943ac4-581d-4aa0-bf90-c60a7d3aaef8))
				- ((64943ac4-a68a-400c-9745-c880f1ac9545))
		- _Proprietary_
		  id:: 64943ac4-581d-4aa0-bf90-c60a7d3aaef8
		  collapsed:: true
			- Self-Hosted license available
				- ActiveCollab
				  collapsed:: true
				  id:: 64098f0e-7e01-4146-9184-edda5475b0e7
				  Self-hosted from $999; Asana-like
					- Features
					  collapsed:: true
						- Multiple views
						  http://i.imgur.com/TZvA4ro.png
							- List/overview
							- Column/Kanban view
							- ((663a0528-7561-41e3-ae6d-34b4dc2e4d26))
						- Features - rest looks very Asana-like
						  https://activecollab.com/features
						- ActiveCollab offers all the core functionality you expect
						- Task management
						- Contacts
						- Calendaring
						- ((663a0528-7561-41e3-ae6d-34b4dc2e4d26))
						- Document management
						- Project Quotes
						- Time tracking and invoicing (with integration to Xero)
						- https://activecollab.com/roadmap
					- Platforms
					  collapsed:: true
						- Electron desktop app
						  https://github.com/nurtext/active-collab-desktop
						- https://play.google.com/store/apps/details?id=com.a51.activecollab
					- Free download through blackhat?
					  collapsed:: true
						- Downloaded to PMM Nextcloud
						- http://blackworldforum.com/showthread.php?tid=8350
					- Installation
					  collapsed:: true
						- https://activecollab.com/help/books/self-hosted/requirements
				- Easy Redmine
				  intralink2:: https://workflowy.com/#/8778661d6138
			- SaaS
				- [Linear](https://linear.app/)
				  id:: 64943ac4-a68a-400c-9745-c880f1ac9545
				  collapsed:: true
					- List view
						- ![image.png](../assets/image_1682326089956_0.png)
					- Board view (Kanban)
					- ((663a0528-7561-41e3-ae6d-34b4dc2e4d26))
				- [Upbase](https://upbase.io/)
				  id:: 644c09ca-701a-487b-8ba9-b687ccf4c297
				- Portabella (E2EE?)
				  collapsed:: true
					- [https://portabella.io/](https://portabella.io/)
				- [Asana](https://asana.com/)
				  id:: 64098f0e-0cc1-4158-962e-5042cb5d8230
				  collapsed:: true
					- Screenshots
					  collapsed:: true
						- http://i.imgur.com/zoXfIPa.png
						- http://i.imgur.com/exBfQOY.png
						- Simple table view
						  http://i.imgur.com/fsa7sFk.png
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Less versatility needed for project managing small teams than personal management
							- Comments, automatic time stamps, automatic inbox notifications, setting clear obvious deadlines, etc makes it a powerful specialised tool
							- Dedicated section for deadlines, assignee
							- Colours and layout make it clear
							- Inbox feature - I don't know if WorkFlowy has a comparable way of sharing updates
							- Can interlink to SOPs in WorkFlowy or files on server or see 'future project management' or 'Redmine'
						- Cons
							- Limited levels of hierarchy to about 8 which forced me to do some weird interlinking organisation
								- Limited my mental concept  organisation
							- Hosted data - thus a privacy risk
							- Slow to load tasks
							  In 2015, much improved in 2017
							- On PC high memory usage
							- High level of lock-in
								- Very difficult to export SOPs into another program to be used
								- Would be difficult to duplicate this as a self-hosted app
							- On mobile couldn't view internal links from external apps (eg rTracker linking to an Asana note led to unreadable mobile site)
							- On mobile the selected task would only stay loaded for a few minutes in the background then it would refresh to homepage
						- Asana
							- Pros
								- Easy sending of attachments
							- Cons
								- Slow to get an overview of child tasks, basically an anti-outliner
								- Doesn't automatically make you follow every subtask
								- No fields for completion %
					- Instagantt integration
					  https://asana.com/apps/instagantt
					- Asana Slack integration
					  intralink2:: https://workflowy.com/#/d4bad048ed1f
					- Info still in there
					  collapsed:: true
						- Create A Website
						- Networking https://app.asana.com/0/13448633525131/list
						- Travel https://app.asana.com/0/13449246278434/list
						- CV Bsure Operations Manuals https://app.asana.com/0/15828526482642/list
						- Reviews https://app.asana.com/0/14081627226321
						- Small Projects
							- Aarons office https://app.asana.com/0/26393328261490/list
							- Life Strategy https://app.asana.com/0/26391331291701/list
						- Medium Projects
							- Business SOPs https://app.asana.com/0/13939091628542/list
					- {_Archive}_
					  collapsed:: true
						- Moved away from Asana for Personal Management
							- Pros
								- Best for: Recurring routines which require multi-level checklists (e.g. dailies). New projects with many steps. Collaboration.
							- Reasons
								- Limited levels of hierarchy to about 8 which forced me to do some weird interlinking organisation
									- Limited my mental concept  organisation
								- Slow to load tasks
								- On PC high memory usage
								- High level of lock-in
									- Very difficult to export SOPs into another program to be used
									- Would be difficult to duplicate this as a self-hosted app
								- On mobile couldn't view internal links from external apps (eg rTracker linking to an Asana note led to unreadable mobile site)
								- On mobile the selected task would only stay loaded for a few minutes in the background then it would refresh to homepage
				- Flow
				  collapsed:: true
					- https://www.getflow.com/
					- Uservoice
					  http://feedback.getflow.com/forums/214911-flow
					- $19/month for up to 3 people, $59 up to 10 people
					- **Comparisons**
					  collapsed:: true
						- _Slack_
							- Pros
								- GUI for creating tasks from within chat easily (though some Slack bots are decent)
								  http://i.imgur.com/bx7Jop5.png
									- https://www.getflow.com/support/chat/creating-tasks-from-chat
								- One app for chat+tasks - simpler
							- Cons
								- No threading
								- No integrations yet (currently being worked on though)
					- **Pros/Cons**
					  collapsed:: true
						- Pros
							- Has all the task properties/metadata of Asana
							  http://i.imgur.com/kKseFCf.png
							- Instant chat rooms + create tasks from within them
							  https://www.getflow.com/support/chat
							- Many views
								- Dashboard
								  http://i.imgur.com/nngigWN.png
								- Catchup
								  http://i.imgur.com/FvGMPFr.png
								- Project Reporting
								  http://i.imgur.com/mZhEIfy.png
								- Task Tracking
								  http://i.imgur.com/lJRgrOT.png
								- Tasks view
								  http://i.imgur.com/PNa4680.png
								- Calendar
								  http://i.imgur.com/BvJYBB3.png
								- Kanban
								  http://i.imgur.com/qXU0sGm.png
								- https://assets.getflow.com/assets/home/Homepage-video.mp4?mtime=20170504132606
							- Exportable data
								- Yes, you can download a complete copy of your Flow account at any time as an XML file. You can also export any list as a PDF, CSV, or HTML file.
						- Cons
							- Only 3 levels of hierarchy (project/tasks/subtasks)
							- Lacks
								- _In-progress_
									- Public API
									  http://feedback.getflow.com/forums/214911-flow/suggestions/4207932-public-api
									- Resource Management - A simple overview of your team’s individual task workloads.
									- ((663a0528-7561-41e3-ae6d-34b4dc2e4d26))
									- Task Start Dates
									  http://feedback.getflow.com/forums/214911-flow/suggestions/4200808-task-start-dates
									- Mobile app offline mode
									  http://feedback.getflow.com/forums/214911-flow/suggestions/5086573-offline-mode-especially-in-the-app
								- _And not planned_
									- Dependent tasks
									  http://feedback.getflow.com/forums/214911-flow/suggestions/5822196-dependant-tasks
									- Task due time
									  http://feedback.getflow.com/forums/214911-flow/suggestions/4201913-task-due-time
								- Mobile app
								  http://i.imgur.com/FvGMPFr.png
									- https://play.google.com/store/apps/details?id=com.getflow.tasks
									- Lacks
										- No offline capabilities (same like Asana app)
										- No search.
					-
				- ClickUp
				  collapsed:: true
					- https://clickup.com
					- Multiple views
					  https://clickup.com/views
						- List (like Asana)
						- Board (Kanban)
						- Box (Outliner-like)
				- Wrike
				  collapsed:: true
					- https://play.google.com/store/apps/details?id=com.wrike
				- Todoist
				  intralink2:: https://workflowy.com/#/2fd192b99f3f
				- Basecamp
				  collapsed:: true
					- https://basecamp.com/how-it-works
				- Plan
				  collapsed:: true
					- https://getplan.co
				- Workzone
				- ProjectPlace
				- Teamwork
				  collapsed:: true
				  Extensive Projects module. Beta: Slack-like module
					- Task list
					  http://i.imgur.com/QWRBWdR.png
					- ((663a0528-7561-41e3-ae6d-34b4dc2e4d26)) view
					  http://i.imgur.com/XHiPYXs.png
					- Today's tasks dashboard
					  http://i.imgur.com/9gImE53.png
					- https://www.teamwork.com/project-management-software
				- Hive
				  collapsed:: true
					- https://hive.com/features/
		- Open source
			- _Web apps_
				- [Plane](http://plane.so/)
				  id:: 644c09ca-07ac-4f1b-b377-da8dc0fd082e
				  collapsed:: true
					- Pros/Cons
						- Pros
							-
						- Cons
							- [Requires 4GB RAM](https://github.com/makeplane/plane/pull/3474) - I need to upgrade laptop or host it online
						- Unclear
						- Comparisons
					- [FOSS](https://github.com/makeplane/plane) [selfhosted](https://github.com/makeplane/plane/blob/master/CONTRIBUTING.md#setup-the-project) (and [freemium hosted](http://plane.so/)) project management tool, alternative to Jira
					- Kanban, Gannt chart, GitHub Projects-like (cards), calendar, spreadsheet (Airtable-like) views
					- Export your workspace data to CSV, Excel and JSONppp
					- Lacks
						- In progress:
							- Android app
						- CalDAV support
				- [Tegon](https://tegon.ai/)
				  id:: 66a965fd-d096-4334-a5e5-faa6691e13af
				  collapsed:: true
					- [GitHub - tegonhq/tegon: Tegon is an open-source, AI-first alternative to Jira, Linear](https://github.com/tegonhq/tegon)
					-
				- [Tillywork](https://github.com/tillywork/tillywork)
				- [Worklenz](https://github.com/Worklenz/worklenz)
				- [Huly](https://huly.io/)
				  collapsed:: true
					- [GitHub - hcengineering/platform: Huly — All-in-One Project Management Platform (alternative to Linear, Jira, Slack, Notion, Motion)](https://github.com/hcengineering/platform)
				- ((6521b3da-3311-41d4-9469-b8e916ca0243))
				  id:: 6497200c-27f2-465e-a699-aa85c137704d
				- [Leantime](https://leantime.io/)
				  collapsed:: true
					- [GitHub - Leantime/leantime: Leantime is a lean project management system for non-project managers. Designed to help you manage your projects from ideation to delivery.](https://github.com/Leantime/leantime)
				- Redmine
				  collapsed:: true
					- http://www.redmine.org/
					- redmine vs easy redmine
					  collapsed:: true
						- EasyRedmine https://www.youtube.com/watch?v=zThKmNJBpIA (looks like a true Asana alternative but 200euros for self-hosted http://www.easyredmine.com/on-premises-solutions)
							- Easy Redmine - easy time logging, budgeting CRM, help desk
							- https://www.easyredmine.com/resources/tutorials
					- Redmine vs WorkFlowy
					  collapsed:: true
						- Redmine Pros
							- Easy to attach files
							- track task creation time, edits and comments
							- My server so all data is completely private
							- Suited for focus as you only see 2 levels in hierarchy at same time (descriptor and checklist)
						- Redmine Cons
							- Method of setting parent task (via drop down  list?) doesn't look scalable or intuitive
							- Can't see same level projects within s project? Is there breadcrumbs even?
							- Not as speedy workflow
						- Identical
							- Infinite hierarchy
							- Same cost $5/month (redmine $5/mo for VPS, workflowy for pro for delegation capability)
					- Themes
					  collapsed:: true
						- Abacus
						  http://www.redminethemes.org/redmine-themes/abacus-office
						- Flatly light
						  http://www.redminethemes.org/redmine-themes/flatly-light
					- Modules
					  collapsed:: true
						- RModules: depending on the projects you want to use Redmine for, you can select different modules which you can use.
							- Issue Tracking: track bugs and issues with Redmine
							- Wiki: keep a documentation for your projects
							- Time tracking: track time on tasks and deliverables
							- Forums: collaborate with colleagues and discuss project related things
							- News: Create a news channel for your projects
							- Calendar
							- Documents: Store your project files
							- Gantt: Want to create ((663a0528-7561-41e3-ae6d-34b4dc2e4d26)) – that’s the place to be.
					- Plugins
					  collapsed:: true
						- Plugins
							- Possibly with the project tree/hierarchy view allowing drag-and-drop (currently assigning parent task uses a dropdown list, which is a slow workflow and isnt scalable)
							- Drag and drop issues via Stuff To Do Plugin
								- http://www.redmine.org/projects/redmine/wiki/PluginStuffToDo
						- Kanban board
						  http://www.redmine.org/plugins/redmine_agile
						- Checklists
						  http://www.redmine.org/plugins/redmine_checklists
						- Qhttp://www.redmine.org/plugins/usability
						- Qhttps://www.redmineup.com/pages/plugins
						- Qhttp://www.redminecrm.com/projects/questions/pages/1
						- Qhttp://www.redmine.org/plugins/banner
						- WYSIWYG editor
						  http://www.redmine.org/plugins/redmine-ckeditor
						- Progress bar below project title
						  http://stgeneral.github.io/redmine-progressive-projects-list/
						- People plugin
						- Planio maintained plugin versions
						- Tagging for issues, integrates into a tag cloud and searches
						  http://t.umblr.com/redirect?z=https%3A%2F%2Fgithub.com%2Fplanio-gmbh%2Fredmine_tagging&t=ZWM3YWYxMDM5N2ZhN2ZkMGFmNmZiNzVlNzA4MjVmNTZkMGIzZTM4MSxYSjVId2RJZQ%3D%3D&b=t%3ApQ2a-qOmXaD0GPirQeUI-Q&p=http%3A%2F%2Fplan.io/blog%2Fpost%2F142349004143%2Fredmine-plugins-the-top-8-planio-approved-plugins&m=1
						- Slack
						  http://t.umblr.com/redirect?z=https%3A%2F%2Fgithub.com%2Fplanio-gmbh%2Fredmine-slack&t=NDJjOGRmZjhiNzc4MjczMTgzNDM5YTkwNDFjY2EyMzlkMTA4OTQ5MyxYSjVId2RJZQ%3D%3D&b=t%3ApQ2a-qOmXaD0GPirQeUI-Q&p=http%3A%2F%2Fplan.io/blog%2Fpost%2F142349004143%2Fredmine-plugins-the-top-8-planio-approved-plugins&m=1
						- Mentions - emails them
						  http://t.umblr.com/redirect?z=https%3A%2F%2Fgithub.com%2Fplanio-gmbh%2Fredmine_mentions&t=MWI1OWYxNjJiYTUyZGIyMTQ3MDgzZjg4M2RhNWJlMzhlMTc2ZjBkYyxYSjVId2RJZQ%3D%3D&b=t%3ApQ2a-qOmXaD0GPirQeUI-Q&p=http%3A%2F%2Fplan.io/blog%2Fpost%2F142349004143%2Fredmine-plugins-the-top-8-planio-approved-plugins&m=1
						- Default custom query - show default view per project
						  http://t.umblr.com/redirect?z=https%3A%2F%2Fgithub.com%2Fplanio-gmbh%2Fredmine_default_custom_query&t=MGE2MmQwODE0MjEyODk0NWMxZjA4MWUxNDFkNzA2YmUwYTRjMWRlOCxYSjVId2RJZQ%3D%3D&b=t%3ApQ2a-qOmXaD0GPirQeUI-Q&p=http%3A%2F%2Fplan.io/blog%2Fpost%2F142349004143%2Fredmine-plugins-the-top-8-planio-approved-plugins&m=1
						- Tree hierarchy sort
							- Qhttp://www.redmine.org/plugins/redmine_smart_issues_sort
							- Qhttp://www.redmine.org/issues/7907
				- XWiki
				  collapsed:: true
					- http://extensions.xwiki.org/xwiki/bin/view/Extension/Task+Manager+Application
				- OpenProject
				  collapsed:: true
					- Pros
						- Looks quite nice UI
					- Cons
						- Only email notifications
					- https://www.openproject.org/plugins/
					- web hooks to be added soon
					  https://community.openproject.com/projects/openproject/work_packages/24832/activity
					- On Bitnami
					  https://bitnami.com/stack/openproject
				- MyCollab
				  collapsed:: true
					- https://www.mycollab.com/ce-registration/
				- Fluxday
				  collapsed:: true
					- http://fluxday.io/
					- Nicer UI then Redmine but less features
				- Trac
				  collapsed:: true
					- https://trac.edgewall.org/ - wiki and issue tracking
					- Looks like little development
			- _WordPress Themes and Plugins_
			  collapsed:: true
				- https://wordpress.org/plugins/upstream/
				- WP Project Manager
					- https://wordpress.org/plugins/wedevs-project-manager/
				- https://www.projectpanorama.com/
				- PrimusNote
					- WordPress theme
					- Cons
						- No integration with push notifications or calendars?
					- http://primusnote.com/
					- https://themeforest.net/item/primusnote-project-management-team-collaboration-based-on-wordpress/19287601?s_rank=1
				- https://wordpress.org/plugins/kanban/
				- https://codecanyon.net/item/cqpim-wordpress-project-management-plugin/11788321
				- https://wordpress.org/plugins/orbis/
				- https://themeforest.net/tags/project%20management
			- Get an open-source single user Android tasks app developed
			  #Software https://workflowy.com/#/655a4d262a9f
		- _Related: _
			- To-Do list apps
			  #Software https://workflowy.com/#/59099dc255d5
			- Airtable
	- ((64463cc6-fc62-4165-a8d3-6802111d3e93))
	- ((64463cc5-2aa5-4916-8686-c3f6d3c46a08)) : ((64463cc5-a732-4069-9ccd-d28adb8da813))
	- Gantt charts
	  id:: 663a0528-7561-41e3-ae6d-34b4dc2e4d26
	  AKA timeline view
	- _Unsuitable_
		- Agile-based ie software development
		  id:: 64a4516e-15b7-47cd-8cea-9b75fef20041
		  collapsed:: true
			- Take a look at Kanban, for instance. One of the most productive task-management systems with 2 main principles at its core: (1) Visualize your workflow, (2) Limit your work in progress
			- [Taiga](https://www.taiga.io/)
			  id:: 64943ac4-fa3b-418a-aff0-d110c197b005
			  collapsed:: true
				- - based on Agile methodology
			- Wekan
			- https://www.tuleap.org/
			- GitHub or Jira or Airtable for tracking issues/bugs/epics
			- Taiga or Trello for sprints
		- [Atrium](http://openatrium.com)
		  collapsed:: true
			- Arty intranet drupal theme
	- Related: ((64463cc6-aff8-42cb-97f0-08898d8dbb70))
- Related: [[Software]]