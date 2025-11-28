- _Links_
  collapsed:: true
	- [https://github.com/zotero/zotero](https://github.com/zotero/zotero)
	- [https://www.zotero.org](https://www.zotero.org/blog/zotero-5-0-36/)
	- Zotero desktop changelog
	  [https://www.zotero.org/support/changelog](https://www.zotero.org/support/changelog)
	- Zotero Connector changelog
	  [https://github.com/zotero/zotero-connectors/issues/350](https://github.com/zotero/zotero-connectors/issues/350)
		- 1 Backlink
			- _See_ [Zotero Connector changelog](https://workflowy.com/#/0479b6d4c4d7)
			  #Software-File
- Pros/Cons
	- Pros
		- Built-in PDF reader, with annotations saved to external database (but can be added into PDF on export).  Best way to annotate PDFs and extract those annotations.
		  collapsed:: true
		  [https://www.zotero.org/static/images/blog/6.0/pdf-reader.jpg](https://www.zotero.org/static/images/blog/6.0/pdf-reader.jpg)
			- **How to create annotations**
				- In Zotero PDF
					- Create coloured highlights
					- Create coloured sticky notes
					- Create coloured boxes
			- **How to export annotations**
				- Extracting all annotations from PDF into text = right-click the PDF item in the items list > Add Note from Annotations
				- Extracting specific annotations from PDF into text = double left-click to open PDF in Zotero > select the highlight in the sidebar
				- Exporting PDF with annotations = two methods
					- _Either _
						- File menu > Export PDF
						- (if in a PDF tab) File menu > Save as
				- Exporting PDF without annotations = (An upcoming version will let you omit annotations, but in the meantime you can drag files to your filesystem to copy just the file.)
				- Similarly, when exporting metadata from your library, there's a new “Include Annotations” option under “Export Files”. (right-click folder in sidebar > Export Library/Collection)
			- See [Adding Annotations to Notes](https://www.zotero.org/support/pdf_reader#adding_annotations_to_notes) for more on the various ways of using annotations in notes in Zotero 6.
			- [Annotations are stored in the Zotero database, not in the PDF file](https://www.zotero.org/support/kb/annotations_in_database)
			  id:: 644c0c08-5d72-4c66-8383-ce37a172d0cb
				- which allows for much more advanced functionality as well as conflict-free fast delta syncing.
				- With annotations stored in the database, Zotero is able to quickly sync just the details of each new or updated annotation. By contrast, with standard PDF annotations, the entire PDF file needs to be transferred after every change, so if two people in a group added an annotation at the same time, or even if a PDF was just left open on one computer, it would create an unresolvable file conflict, forcing the user to choose one side or the other.
			- {Archive}
				- [https://forums.zotero.org/discussion/88064/available-in-preview-zotero-pdf-reader-and-new-note-editor](https://forums.zotero.org/discussion/88064/available-in-preview-zotero-pdf-reader-and-new-note-editor)
				- Feature was being handled by Zotfile, now deprecated
				  _See_ [Zotfile (how to actually extract annotations/highlights from PDFs)](https://workflowy.com/#/e6749103f0aa)
		- Zotero Connector browser extension - allows easily saving ((649b1411-9fe3-449b-8f80-03b4af9c5e9a))
		  collapsed:: true
			- [https://www.zotero.org/download/connectors](https://www.zotero.org/download/connectors)
			- [https://github.com/zotero/zotero-connectors](https://github.com/zotero/zotero-connectors)
			- It uses SingleFile under the hood so it saves a full offline page in HTML.
			- I've requested it to be added to the official Firefox Addons site
			  [https://github.com/zotero/zotero-connectors/issues/349](https://github.com/zotero/zotero-connectors/issues/349)
			- Lacks
				- Simplified Snapshots or Reading Mode support
				  [https://github.com/zotero/zotero-connectors/issues/194#issuecomment-345442015](https://github.com/zotero/zotero-connectors/issues/194#issuecomment-345442015)
		- Plugins for additional functionality
		  collapsed:: true
			- _How to install_
				- Tools > Addons > gear icon > "Install Add-on From File."
			- _What plugins_
				- Zotfile (how to actually extract annotations/highlights from PDFs)
				  collapsed:: true
					- Plugin to manage your attachments: automatically rename, move, and attach PDFs (or other files) to Zotero items, sync PDFs from your Zotero library to your (mobile) PDF reader (e.g. an iPad, Android tablet, etc.) and extract annotations from PDF files.
					- http://zotfile.com/#extract-pdf-annotations
					- [https://github.com/jlegewie/zotfile](https://github.com/jlegewie/zotfile)
					- How to
						- File > New Item > Book (or whatever is appropriate)
						- Right-click the item > Add Attachment > Attach Stored Copy of File (attach the annotated PDF)
						- Right-click the PDF attachment and select Manage Attachments->Extract Annotations
					- _Related:_
						- NEW in Zotero 6: [Best way to annotate PDFs and extract those annotations. In Zotero 6 it's a native feature](https://workflowy.com/#/0f2bab0c6073)
					- 1 Backlink
						- Feature was being handled by Zotfile, now deprecated
						  _See_ [Zotfile (how to actually extract annotations/highlights from PDFs)](https://workflowy.com/#/e6749103f0aa)
				- Better BibTeX for Zotero (citekeys)
				  collapsed:: true
					- [https://github.com/retorquere/zotero-better-bibtex/releases](https://github.com/retorquere/zotero-better-bibtex/releases)
					- [https://retorque.re/zotero-better-bibtex/citing/](https://retorque.re/zotero-better-bibtex/citing/)
					- Pros
						- Citekey - a unique ID field for each reference(?)
						- Drag-and-drop references from Zotero to a text writer like Kate and it'll paste the citekey
					- Examples
						- [zotero] ZoteroConnectors
				- _{Archive}_
				  collapsed:: true
					- Zutlio
						- [https://github.com/wshanks/Zutilo/releases](https://github.com/wshanks/Zutilo/releases)
						- Intro
							- Here are some of Zutilo's features:
								- Copy, paste, and remove sets of tags
								- Select and right-click to relate several items
								- Copy items to the clipboard in several formats
								- Keyboard shortcuts for editing items and focusing and hiding different elements of the Zotero user interface
							- Zutilo strives to enable whatever Zotero workflow is desired and otherwise to get out of the way. All of Zutilo's graphical elements can be disabled individually, so that unwanted features do not clutter the user interface.
						- Can be hyperlinked to?
							- To add to the point about "very general tool", it's even possible to hack Zotero so as to give Word/GoogleDoc some rudimentary dynamic content or Roam-like features. Just define a custom citation format (but mentally pretend citations as Roam-like [[links]]), and in Word/GoogleDoc invoke the Zotero add-on for insertion citation. The autocomplete search is fuzzy and fast, and Zotero inserts a field code with unique id that makes it easy to keep track of all references to the same idea/thesis/concept even under different aliases. Better still, if you alter the dynamic content inside Zotero it can automatically update the displayed value of the field code next time you invoke the add-on.
		- Unofficial mobile apps
		  collapsed:: true
			- Zoo for Zotero (Play Store)
				- Requires online Zotero account for syncing
				- [https://github.com/mickstar/Zoo-For-Zotero](https://github.com/mickstar/Zoo-For-Zotero)
				- [https://play.google.com/store/apps/details?id=com.mickstarify.zooforzotero&hl=en_US&gl=US](https://play.google.com/store/apps/details?id=com.mickstarify.zooforzotero&hl=en_US&gl=US)
		- Features
		  collapsed:: true
			- Browser extensions for Chrome, Firefox, and Safari to help you save items with one click
			- Automatic downloading of PDFs and webpage snapshots
			- Word processor plugins to help you quickly insert citations and automatically generate a bibliography from the citations in your document, with support for subsequent citations, given name disambiguation, ordered numeric styles, and other advanced features
			- Organization and tagging
			- Note-taking
			- Advanced sorting and searching
			- Group libraries for easy collaboration and sharing
			- Automatic syncing across your devices
			- Retracted item notifications
			- Web access to your data, notes, and files
			- Automatic metadata retrieval for imported files
			  id:: 644c0c08-81c1-4cf4-b6d1-3467419f453c
			  collapsed:: true
				- [https://forums.zotero.org/discussion/75796/how-to-retrieve-and-update-metadata-in-zotero](https://forums.zotero.org/discussion/75796/how-to-retrieve-and-update-metadata-in-zotero)
				- 1 Backlink
					- Zotero can do [Automatic metadata retrieval for imported files](https://workflowy.com/#/f7e26ed585ec)
			- Portable Zotero for Windows (unofficial)
			  collapsed:: true
				- Zotero 5
				  https://github.com/pedrom34/ZoteroPortable
					- https://forums.zotero.org/discussion/64050/5-0-portable-zotero
				- Zotero 4
				  https://portableapps.com/node/36565
		- [Zotero 7 announcement](https://www.zotero.org/blog/zotero-7/)
		  id:: 66c72320-6c0d-4ce3-b084-6f08e6b52f44
		  New UI, dark mode, EPUB reader/annotator, webpages can be saved as snapshots and annotated, attachment preview pane
			- Zotero Connector saves webpages to HTML, and it can be annotated now but it's not a reader view ((644c0c08-9b2a-4f52-a412-5844bccb987e))
			  id:: 67154a8e-8256-4089-82bc-eaaef70dff49
			  collapsed:: true
				- ![image.png](../assets/image_1729448616810_0.png)
		- [Zotero 6 announcement](https://www.zotero.org/blog/zotero-6)
		  collapsed:: true
		  Top feature being exporting PDF annotations to Notes attachment
			- New features
				- Open PDFs in a new built-in reader within the main Zotero window, in a new tabbed interface
				- Clean up metadata for items while viewing their PDFs
				- Mark up PDFs with highlights, notes, and image annotations
				- Add annotations to Zotero notes with automatic citations, in a powerful new note editor
					- After you’ve marked up a PDF, you can quickly [add some or all annotations to a Zotero note](https://www.zotero.org/support/pdf_reader#adding_annotations_to_notes).
					- Annotations added to notes aren’t just plain text: they include information about the source PDF that lets you quickly jump back to the original page to see context, generate bibliography entries using Zotero’s word processor plugins, toggle annotation colors on and off, include links back to Zotero when exporting to Markdown, and even restore accidentally deleted citations to make sure you’ve properly attributed a quote.
				- Cite other items directly in notes using Zotero’s familiar citation dialog
				- Insert notes into your Word, LibreOffice, and Google Docs documents with active Zotero citations for automatically generating bibliographies
				- Export notes to external Markdown editors with links back to Zotero items and PDFs
		- Can self-host and sync
		  collapsed:: true
			- Syncs across devices and web as well (through their servers or yours with webdav)
			- Server component
				- [https://github.com/zotero/dataserver](https://github.com/zotero/dataserver)
				- [https://github.com/ZotPrime/zotprime](https://github.com/ZotPrime/zotprime)
				- [https://github.com/nextlevelshit/zotero-dataserver-docker](https://github.com/nextlevelshit/zotero-dataserver-docker)
		- Offers free hosted cloud sync e.g. to mobile, though this is not E2EE
		  collapsed:: true
			- [https://www.zotero.org/support/sync](https://www.zotero.org/support/sync)
		- PDF annotations
	- Cons
		- _Lacks_
			- [Bulk annotation tagging](https://forums.zotero.org/discussion/97007/feature-request-bulk-annotation-tagging/p1) - e.g. tag all annotations as `view1` or `read1` to indicate first time read through of a book. In meantime can use different highlight colours
			- [Tray icon](https://github.com/zotero/zotero/issues/1933)
			- End-to-End Encryption for Cloud Sync
			  collapsed:: true
				- Not interested in E2EE but can discuss self-hosting
				  [https://forums.zotero.org/discussion/comment/380780#Comment_380780](https://forums.zotero.org/discussion/comment/380780#Comment_380780)
				- Zotero allows syncing your library and attachments to official servers but this sync is not client-side encrypted (E2EE). We'd like to use your cloud service (especially as there's no other way to sync the database reliably) but as it stands it's a hard blocker for data confidentiality reasons.
				- (posted, new post needs approval)
				- _Workarounds_
					- Database - can be cloud synced eg Syncthing, but since it's a database it can be unreliable
					- Attachments - use Linked Files
			- [Ability to update metadata for a book/journal article etc](https://github.com/zotero/zotero/pull/1582#issuecomment-1085995614)
			- [WebConnector being able to save readable versions of webpages](https://github.com/zotero/zotero-connectors/issues/194#issuecomment-345442015)
			  id:: 644c0c08-9b2a-4f52-a412-5844bccb987e
		- Flatpak issues
			- Not sure if it's an issue for native
				- [URIs do not open properly · Issue #217 · flathub/org.zotero.Zotero · GitHub](https://github.com/flathub/org.zotero.Zotero/issues/217)
				-
	- Comparisons
		- Zotero vs ((660e8211-0f7b-401e-bf69-5d8bd9ed1781))
			-
		- ((62e297f8-1bfa-4cce-9c87-9a45000893dd))
		  collapsed:: true
			- {{embed ((62e297f8-1bfa-4cce-9c87-9a45000893dd))}}
		- ((62e283e4-92b0-4f74-bce6-8c0c404fdc06))
		  collapsed:: true
			- {{embed ((62e283e4-92b0-4f74-bce6-8c0c404fdc06))}}
		- Comparison between ((62e283e0-f115-467d-af93-ec6c58a46187)) and ((62e283e1-ebea-4ab9-9763-aa6a1b7ea0ba))
		  id:: 62e0626f-1834-46b9-bbab-f3b39dfd1f6f
		  collapsed:: true
			- Pros of Zotero / Cons of Calibre
				- full text PDF search, web clipping and basic bibliography management
				- Zotero has a number of annotation features which make it better suited for learning from documents stored within
					- Zotero allows annotations to be exported periodically to an attached doc ("Note"). This can be used to simulate making different summaries of highlights on repeated rereads
					- This attached doc can have additional inline attachments such as images from elsewhere
					- Can easily create backlinks to specific annotations in WorkFlowy by simple drag-and-drop ("QuickCopy")
					- Calibre's only annotation types are highlights with or without notes attached. Zotero also allows Select Area, and Add Note to attach to non-text areas. Better support for non-text
				- Supports a greater range of documents, since EPUB+MOBI can be converted to PDF (via Calibre). Calibre's reader can't open or annotate PDFs, and conversion doesn't work well for all of them
			- Cons of Zotero / Pros of Calibre
				- EPUBs allow changing font size and text reflow, which makes it more readable especially on mobile
				- Missing deDRM plugins
				- Can't convert e-books between differing formats
			- Similarities
				- Downloading metadata is easy
					- [https://www.zotero.org/support/retrieve_pdf_metadata](https://www.zotero.org/support/retrieve_pdf_metadata)
				- Support annotating ebooks (PDFs in Zotero, EPUBs in Calibre) with annotations stored in database by default
				- Support full-text search to locate annotations, but not of entire docs' unannotated content
					- Zotero: Advanced Search > Attachment Content
					- Calibre: Advanced Search (gear icon) > Contains > All these words
			- Need to test
				- Annotation + FanFicFare compatibility
					- Note: FanFicFare EPUB updates don't conflict with annotations made via Calibre or Zotero
					  id:: 63ff838d-9cea-4380-84f6-2625098ab357
			- Conclusion
				- For learning PDF is preferred (use ((62e283e0-f115-467d-af93-ec6c58a46187))) over EPUBs in Calibre for durability, because it's straightforward to export the annotations embedded into the PDF file itself when finished, but this can't be done for EPUB
			- Related: ((62e060ab-9c3e-4d59-8554-679e0041302d))
	- Comparison to [[Logseq]]
		- Comparison between Logseq PDF highlights and Zotero PDF annotations
- # Documentation
	- How to add items
		- Either:
			- Preferably
				- Go to website, use the Zotero browser extension to add it
				- Right-click the item in Zotero > Find Full Text to add the PDF
			- Drag-and-drop PDF into Zotero
				- Right-click > retrieve metadata
	- Troubleshooting
		- http://127.0.0.1:23119/connector/ping
- Download
  collapsed:: true
	- Flatpak
	  flatpak install flathub org.zotero.Zotero
	- Package manager
	- Direct download
	  [https://www.zotero.org/download/](https://www.zotero.org/download/)
- SOP
  collapsed:: true
	- New 2022
		- Creating deeplinks from WorkFlowy > Zotero
			- [https://www.zotero.org/support/creating_bibliographies#quick_copy](https://www.zotero.org/support/creating_bibliographies#quick_copy)
		- Modifying notes
			- Supports images - drag-and-drop from web or PC
		- Reading and annotating books
			- ((62e0626f-1834-46b9-bbab-f3b39dfd1f6f))
	- Archiving webpages
		- Save webpages via SingleFile (+ annotate if necessary) that I want to archive
		- In Zotero "Store Copy of File"
		- Right-click > Show File > in Dolphin then right-click the file and Copy Location
		- Paste the location into outliner
		- e.g.
		  [archive] /home/boss/Zotero/storage/Z4FL8B6A/Zotero Blog » Community Spotlight.html
		- 1 Backlink
			- Check ArchiveBox SOP [SOP - Archiving webpages](https://workflowy.com/#/580850673d02) and archive some webpages from ArchiveBox into Zotero? Or stick with ArchiveBox - seems more suitable perhaps
	- 1 Backlink
		- Integrate [Zotero](https://workflowy.com/#/935fa4d3e496) into workflow (unless Logseq is replacing it). Update <a href="https://workflowy.com/#/f3b160657871">SOP</a> for it and decide on several high-priority PDFs to read plus the workflow to backlink, etc]
- Zotero general
  collapsed:: true
	- Installation
		- Flatpak
		  flatpak install flathub org.zotero.Zotero
			- [https://flathub.org/apps/details/org.zotero.Zotero](https://flathub.org/apps/details/org.zotero.Zotero)
	- Documentation
		- Items can have notes, files, and links attached to them
		- Zotfile + ((649b1411-9fe3-449b-8f80-03b4af9c5e9a)) extension for 2-click adding to Zotero
	- Guides
		- https://remembereverything.org/zotero-electronic-library-citations-and-bibliographies/
		- https://www.zotero.org/support/quick_start_guide
		- [https://remembereverything.org/tag/zotero/](https://remembereverything.org/tag/zotero/)
	- Desc 1
		- While it is "marketed" for scientists, it is a very general tool, that allows me to archive, tag, organize and search any webpage (with the option of taking a snapshot) or digital item.
		- I started using it for research articles, but it quickly expanded as a general bookmark organizer, then to books and even some podcast and movies archival. I use specific folders as reading/watching/listening queues.
		- Best of all it is FLOSS software, which is an absolute requirement for me to future-proof my use, and has an API that can be used to interact with external software. I use it for example as a document "backend" for my emacs org-mode journal (via the zotxt-emacs package).
		- There is an online sync service offered at a very reasonable cost (including a free tier). This is one of the very rare online services I'm paying money for. My understanding is that the sync server is open-source, but not production ready for self-hosting yet. The devs are supposedly working on it.
- # Ecosystem
	- [logseq-zoterolocal-plugin](https://github.com/benjypng/logseq-zoterolocal-plugin)
	  id:: 66caed0a-99b0-4633-8876-46f752dd5208
	  collapsed:: true
		- [[2024-08-22 Thursday]] Attempt to integrate into workflow using logseq-zoterolocal plugin (similarly to Logseq plugin for Calibre, in order to keep my PDF files in one place and just cite them into Logseq). [It doesn't seem to work on Linux](https://github.com/benjypng/logseq-zoterolocal-plugin)
			- [[2024-08-25 Sunday]] [Removed cite key stuff in default template](https://github.com/benjypng/logseq-zoterolocal-plugin/issues/16#issuecomment-2308569653)
				- Page Name Template
					- default `R: <% citeKey %>`
					- changed to `zotero/<% title %>`
				- [[Zotero Template]]
					- Removed `citeKey:: <% citeKey %>` line (3rd line, below `accessDate` and `attachments`
				- [If I want to use BBT I need to pin cite keys for each item](https://retorque.re/zotero-better-bibtex/citing/index.html)
		- Commands
			- `/Insert Zotero template`
			- `/Zotero: Insert full item`
			  id:: 66d83b5e-2731-4ade-a81c-93b1eadf1e20
			- `/Zotero: Cite (insert citation)`
	- Review these [plugins](https://www.zotero.org/support/plugins)
	  collapsed:: true
		- Zotero Better Notes
			- [https://github.com/windingwind/zotero-better-notes](https://github.com/windingwind/zotero-better-notes)
			- Reminder to try it is set: [Try Zotero Better Notes after plain Zotero integrated into habits/workflow](https://workflowy.com/#/67fe057eeac3)
			  #Reminders
			- 1 Backlink
				- Try [Zotero Better Notes](https://workflowy.com/#/78c4fc02e317) after plain Zotero integrated into habits/workflow
		- zotero-cli
			- [https://github.com/edtechhub/zotero-cli](https://github.com/edtechhub/zotero-cli)
		- [https://github.com/ThomasFKJorna/zotero-night](https://github.com/ThomasFKJorna/zotero-night)
			- 1 Backlink
				- See [https://github.com/ThomasFKJorna/zotero-night](https://workflowy.com/#/59d5ea12471c)
	- [Calibre GUI Plugin] [Zotero Metadata Importer](https://www.mobileread.com/forums/showthread.php?t=275476)
	  collapsed:: true
		- ZMI is Zotero to Calibre. It is a Calibre plug-in, not a Zotero plug-in. Currently, there are ~500 Calibre users who have installed ZMI.
			- Note that to import Zotero metadata and .pdf files into Calibre, ZMI must be used to add the books, not the Calibre "Add Books" button. That means your existing books in Calibre can only be updated with Zotero metadata if you go the ZMI "manual" route, which can be tedious if you have a lot of books already in Calibre.
			- If you have a lot of Zotero books already in Calibre, it would be much easier and faster to just start from scratch with a new Calibre "Zotero" Library that is empty, and use ZMI to import all of your Zotero .pdf files all at once and update Calibre automatically.
			- The single "Original Post" for ZMI plus its attached images are a "must read" before doing anything with ZMI. If you use OSX, there are special Calibre instructions to follow first. If you use Windows, pay particular attention to the comments about the Windows Administrator requirements. If you use Linux, you are good to go.
			- After installing the ZMI plug-in and restarting Calibre, read the ToolTips in each of ZMI's Tabs to thoroughly familiarize yourself with your options prior to actually using it.
			- The thread for ZMI can be found at: http://www.mobileread.com/forums/showthread.php?p=3339192 but the Original Post is the only thing worth reading.
			- Hope that helps.
- _Related: _
	- ((649b1411-9fe3-449b-8f80-03b4af9c5e9a))
	- [ArchiveBox](((64243829-7fb3-4d3d-a6dc-62a131bab958)))
	- PDF annotation bug which occurred briefly
	  ((62d0cbab-3aca-4af3-836d-b51792264a02))