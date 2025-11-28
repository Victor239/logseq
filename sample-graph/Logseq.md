# Links
collapsed:: true
	- [https://logseq.com/](https://logseq.com/)
	- [[Page not found · GitHub](https://github.com/logseq/logseq](https://github.com/logseq/logseq))
	- [Changelog](https://docs.logseq.com/#/page/changelog)
		- Alternative
		  [https://github.com/logseq/logseq/releases](https://github.com/logseq/logseq/releases)
	- [Roadmap](https://trello.com/b/8txSM12G/logseq-roadmap)
- # Pros/Cons
	- ## Pros
		- Data is plain text files, either org-mode or markdown
		- Can access local files via web app or desktop app
		  collapsed:: true
			- [https://docs.logseq.com/#/page/embed%20media%20-%20audio%2C%20photos%2C%20videos](https://docs.logseq.com/#/page/embed%20media%20-%20audio%2C%20photos%2C%20videos)
				- Natively can embed audio from local or URL
			- Linking to local files
				- Use the `/link` command
				- In the “link” box add the full absolute filepath. Or if you want only stuff in Logseq's `assets` folder, then enter in `assets/filename`
			- Embedding images
			  [https://docs.logseq.com/#/page/628d2347-b607-4528-a9f0-8a9e618a3868](https://docs.logseq.com/#/page/628d2347-b607-4528-a9f0-8a9e618a3868)
		- Multiple methods of multitasking
		  collapsed:: true
			- SHIFT+LMB bullets to open them in a sidebar
				- Can open multiple in the sidebar
			- CTRL+LMB bullets to open a tab for them (with
			- CTRL+N for new window
		- Page/version history
		  collapsed:: true
			- Allows reverting back (0.3.8) + Automatic backup with Git
			- 1 Backlink
				- See [Page/version history](https://workflowy.com/#/2ed631528717)
		- `CTRL + SHIFT + P` = Command palette
		  id:: 649b131d-ea21-47a4-ae83-e7ac7c16afe8
		  collapsed:: true
			- e.g. toggle wide mode
		- PDF highlights
		  id:: 632091d4-2e08-4fd0-8fc5-bb32cc1afc5e
		  collapsed:: true
			- Pros/Cons
				- Pros
					- When viewing the annotation inside the PDF, can right-click the highlight > `Linked references` > and this will allow you to see where exactly in the outliner that the annotation is linked from
				- Cons
					- Lacks
						- [Can't yet export PDF with annotations embedded](https://discuss.logseq.com/t/export-pdf-with-highlights-save-highlights-to-pdf-file/6076)
						  id:: 62e8e0fc-0151-4837-83ec-4f97b54a4c1b
							- [Export PDF with Highlights / Save highlights to PDF file - #9 by Hao_Chan - Feature Requests - Logseq](https://discuss.logseq.com/t/export-pdf-with-highlights-save-highlights-to-pdf-file/6076/9)
				- Unsure
					- It may even have mobile support in future
					  [https://discuss.logseq.com/t/pdf-annotation-on-mobile-devices/4449](https://discuss.logseq.com/t/pdf-annotation-on-mobile-devices/4449)
				- Comparisons
					- ((632091d4-2e08-4fd0-8fc5-bb32cc1afc5e)) vs [[Zotero]] vs ((62e283e1-ebea-4ab9-9763-aa6a1b7ea0ba)) file annotations
					  id:: 62e297f8-1bfa-4cce-9c87-9a45000893dd
						- For ((632091d4-2e08-4fd0-8fc5-bb32cc1afc5e))
							- Annotations stored in same app as main outliner, makes it much quicker to full-text search for a specific highlight
							- PDFs themselves being stored in main outliner means I can organise it much better, plus give it additional tags and properties
							- *Limitations*
								- Removing a highlight from a PDF will affect wherever the highlight was copied to. It'll no longer display the selected text in a note
								- A little labour-intensive to put highlight and annotations in same location - requires LMB the highlight > Copy ref > paste into notetaking section
								- Highlights are sorted by date added, not page order
								- ((62e8e0fc-0151-4837-83ec-4f97b54a4c1b)) unlike [[Zotero]]
							- Example: [[calibre/The Fate of Empires and Search for Survival - Sir John Bagot Glubb (1978)]]
						- For [[Zotero]]
							- Logseq has a ((62e2b185-026c-4cb5-b758-e23891a317cf)), though it is quite limited currently
							  id:: 62e8e0fc-cfe8-4ce9-b973-67ceeec2c921
							- Zotero can export annotations to embed in PDF, so no lock-in
							- Zotero can do [Automatic metadata retrieval for imported files](https://workflowy.com/#/f7e26ed585ec)
							- Zotero has another type of annotation: Notes. Arguably you can just use Area Highlights here instead
							- If I ever need to move to a new outliner app then Logseq has more lock-in since exported annotations are just a unique ID link
							- Limitations
								- The organisation via folder hierarchy is not nearly as useful to me as Logseq's hierarchy, nor even Calibre's table
						- For ((62e283e1-ebea-4ab9-9763-aa6a1b7ea0ba))
							- ((62e29bfa-86b7-424c-bd2c-cb02d005fbaf)) makes it possible to easily search the entire document text, including non-annotated parts
							- ((62e2ab21-cbc9-4601-a81e-0c73495f5343)) should allow easily opening the linked Calibre file
						- Similarities
							- Both make it easy to paste annotations into another copy (in Logseq creating a highlight copies it to clipboard; in Zotero you can drag-drop any highlight to another app to paste it)
							- Both have annotation links which when put in outliner will open the PDF directly to the correct page
						- Related:
							- ((64b4f66c-c844-4ef9-b8b9-3be7282f21fa))
							- ((62e29b65-6348-4a21-ac4c-94061b42c6d6))
					- ((632091d4-2e08-4fd0-8fc5-bb32cc1afc5e)) vs [[Zotero]]
						- Comparison between Logseq and Zotero PDF annotations
						  id:: 62e283e4-92b0-4f74-bce6-8c0c404fdc06
							- For ((632091d4-2e08-4fd0-8fc5-bb32cc1afc5e))
								- Annotations stored in same app as main outliner, makes it much quicker to full-text search for a specific quote
								- PDFs themselves being stored in main outliner means I can organise it much better, plus give it additional tags and properties
							- For [[Zotero]]
								- Zotero can export annotations to embed in PDF, so no lock-in
								- Zotero can do ((644c0c08-81c1-4cf4-b6d1-3467419f453c))
								- In Logseq removing a highlight from a PDF will affect wherever the highlight was copied to. It'll no longer display the selected text in a note
								- Zotero has another type of annotation: Notes. Arguably you can just use Area Highlights here instead
								- If I ever need to move to a new outliner app then Logseq has more lock-in since exported annotations are just a unique ID link
							- Similarities
								- Both make it easy to paste annotations into another copy (in Logseq creating a highlight copies it to clipboard; in Zotero you can drag-drop any highlight to another app to paste it)
								- Both have annotation links which when put in outliner will open the PDF directly to the correct page
					- ((6bbfa2ff-3d0e-49ba-a01e-e0b447244b50))
						- {{embed ((6bbfa2ff-3d0e-49ba-a01e-e0b447244b50))}}
			- [https://docs.logseq.com/#/page/pdf%20highlights](https://docs.logseq.com/#/page/pdf%20highlights)
			- How does it work on backend
				- `assets` folder is where a copy of PDF Is saved
				- `.edn` text file created with same filename and it contains highlight location and text. Not human-readable
				- Folder created for same filename if area highlights are used
			- Video
			  [https://youtu.be/vIDyXyEj_FI](https://youtu.be/vIDyXyEj_FI)
			- Related:
				- ((6336ac86-534f-4bd7-b12f-f905197d041f))
				- ((653cd877-e6c4-4e08-a2d7-4b1b992327bf))
		- `/Embed Twitter` support
		- [Query/table/function](https://docs.logseq.com//#/page/query%2Ftable%2Ffunction)
			- [Contacts in DB Version - #6 by danzu - General - Logseq](https://discuss.logseq.com/t/contacts-in-db-version/31197/6)
		- Code blocks with syntax highlighting
		  collapsed:: true
			- Use
			  ```javascript
			  var array1 = hello;
			  ```
		- ((63503767-41a1-44ac-bcf2-4dfa5351566d)) for making databases
		  collapsed:: true
			- logseq queries
		- Markdown-based table support
		- Aliases for internal links
		  collapsed:: true
			- e.g. [How to get a programming job](((629ccb26-a280-407e-86ec-f53f4085d664)))
		- Local flle support
		  collapsed:: true
			- `/Link` to link to local files
				- Example
					- [unbelievable](/home/boss/Pictures/Memes/74292r3df2rrr3MEM021023.jpg-1536x1454.jpg)
					- [HTML file](/home/boss/Downloads/170 Coding Interview Questions _ AlgoExpert (2_27_2023 5_38_07 PM).html)
			- `/Image Link` to link to local images
			  collapsed:: true
				- ![unbeliev](/home/boss/Pictures/Memes/74292r3df2rrr3MEM021023.jpg-1536x1454.jpg)
			- `/Upload an asset` to copy that file into Logseq storage
		- `$$ test $$` syntax for LaTeX
		- New
			- YouTube timestamp support
			  collapsed:: true
				- /Embed Youtube Timestamp
				- [https://www.loom.com/share/995d6755b29c48c6b610646736aa5049](https://www.loom.com/share/995d6755b29c48c6b610646736aa5049)
				- Related: [https://github.com/sethyuan/logseq-plugin-media-ts](https://github.com/sethyuan/logseq-plugin-media-ts)
				- 1 Backlink
					- See [YouTube timestamp support](https://workflowy.com/#/5dc5ff5abef1)
			- _Alpha_
				- [Flashcard](https://docs.logseq.com/#/page/cards) (Anki) + Spaced Repetition support
				  id:: 62e8e0fc-4a9a-4ab1-b5e6-7b07d77906ca
				  collapsed:: true
					- Pros
						- [There's an Anki sync plugin](https://github.com/debanjandhar12/logseq-anki-sync)
						-
					- Cons
						- Lacks
							- Alpha quality, [many feature requests](https://discuss.logseq.com/search?q=card%20%23feature-requests)
								- [Lacks Anki algorithm - cards you forget show again 1 day later instead of 1 minute](https://discuss.logseq.com/t/add-anki-sm-2-algorithm-to-flashcard/4505)
								- [Order of cards isn't randomised](https://discuss.logseq.com/t/random-card-order-in-flashcard-review/5897)
								-
							- Remnote has a much better implementation
								- [https://youtu.be/8LqxWlXYaZg](https://youtu.be/8LqxWlXYaZg)
					- Documentation
						- https://docs.logseq.com/#/page/cards
						- https://docs.logseq.com/#/page/Queries
							- Using queries to review only subsets of all flashcards
								- 1) Use `/card` command to produce something like `{{cards [[Logseq]]}}` with the term being a tag, not a page
								  collapsed:: true
									- Example
									  collapsed:: true
										- {{cards [[A001]]}}
										- {{cards [[A002]]}}
										  collapsed:: true
											- Summary: 1 items, 1 review counts [[2022-08-12 Friday]]
											  collapsed:: true
												- Remembered:   0 (0%)
												- Forgotten :   1 (100%)
										- `{{query (and [[A002]] [[card]])}}`
										  collapsed:: true
											- {{query (and [[A002]] [[card]])}}
											  query-table:: true
										- `{{query (and [[A001]] [[card]])}}`
										  query-table:: false
										  collapsed:: true
											- {{query (and [[A001]] [[card]])}}
											  query-table:: false
						- ^^**Created flashcards in Logseq up to here**^^
						  id:: 62f67eaf-d7f3-4d8f-8f67-3d6e2753aaff
						  collapsed:: true
							- This is used in my notetaking so I can keep track of if I've made all the flashcards I wanted to for the notes above or below this heading
					- Comparison of Logseq Anki support with ((62f63614-33b0-4e8d-b42a-7987bdf192d1))
					  id:: 62e8e0fc-9f1d-4e8b-9e21-d5b0e4ff84f8
						- _Anki Pros / Logseq Cons_
							- Table/database GUI for editing
								- Logseq queries can render as tables only properties in separate columns, not child blocks
								  source:: [https://docs.logseq.com//#/page/62974fec-f075-433d-acb6-9813e1ddb72f](https://docs.logseq.com//#/page/62974fec-f075-433d-acb6-9813e1ddb72f)
						- _Anki Cons / Logseq Pros_
							- Easily and quickly make flashcards and write the meta course notes all in one app
						- `https://github.com/logseq/logseq/blob/master/src/main/frontend/extensions/srs.cljs`
						- Related: [Comparison of LibreOffice Calc vs Baserow for card editing](https://workflowy.com/#/5da7044d4350)
					- Testing Logseq cards
						- What's my favourite colour? #card #A001
						  card-last-interval:: 4
						  card-repeats:: 1
						  card-ease-factor:: 2.36
						  card-next-schedule:: 2022-08-16T16:21:44.902Z
						  card-last-reviewed:: 2022-08-12T16:21:44.904Z
						  card-last-score:: 3
							- Blue
						- What is my mobile OS? #card #A001
						  card-last-interval:: 4
						  card-repeats:: 1
						  card-ease-factor:: 2.36
						  card-next-schedule:: 2022-08-16T16:21:50.149Z
						  card-last-reviewed:: 2022-08-12T16:21:50.151Z
						  card-last-score:: 3
							- Android
						- Country #card #A002
						  card-last-interval:: -1
						  card-repeats:: 1
						  card-ease-factor:: 2.5
						  card-next-schedule:: 2022-08-12T23:00:00.000Z
						  card-last-reviewed:: 2022-08-12T17:34:20.880Z
						  card-last-score:: 1
						  collapsed:: true
							- UK
						- Year #card #A002
							- 2022
				- [[Zotero]] integration
				  id:: 62e2b185-026c-4cb5-b758-e23891a317cf
				  collapsed:: true
					- Pros/Cons
						- Lacks
							- [Zotero 6 Notes support](https://discuss.logseq.com/t/support-for-zotero-6-notes-import/2087)
							- [Requires online Zotero syncing, rather than local files](https://discuss.logseq.com/t/zotero-integration-isnt-privacy-first-at-all/6656/4)
								- https://discuss.logseq.com/t/link-to-external-pdfs-in-local-zotero-folder-and-better-bibtex-support/6038/4
								- https://discuss.logseq.com/t/comprehensive-zotero-plugin/8571/43
								- https://discuss.logseq.com/t/logseq-reads-the-export-from-zotero/1972
							- [Easily open PDF directory or in system viewer](https://discuss.logseq.com/t/pdf-option-to-open-pdf-in-directory-or-in-default-viewer/4156)
							-
					- `/Zotero` command to embed your Zotero files
					- https://docs.logseq.com/#/page/zotero
				- Client-side encryption
				  collapsed:: true
					- 1 Backlink
						- See [Client-side encryption](https://workflowy.com/#/e7f2927a3ba4)
		- _Upcoming_
		- _Minor features_
			- [Wide document layout option `t w`](https://discuss.logseq.com/t/wide-document-layout-option/7844)
			- [Can create new windows natively, or tabs using plugin](https://github.com/pengx17/logseq-plugin-tabs)
	- ## Cons
		- Hosted sync is closed-source, HOWEVER client apps are FOSS and you can just use Syncthing to sync (similar model to Obsidian)
		  collapsed:: true
			- Pros/Cons
				- Pros
				- Cons
					- Real-time collaboration and other group features will require payment
			- Are you going to open-source the future server-side backend?
				- We have no plans for that. But we're considering providing a free self-host sync option for non-profit organizations or researchers in the future, the sync service for our own storage is not started yet.
		- Lacks
			- Meta
				- [Roadmap](https://trello.com/b/8txSM12G/logseq-roadmap)
				  id:: 67375e40-2c1c-485f-b156-dec70830bc1b
			- [Database storage](https://github.com/logseq/logseq/pull/9858) option [coming soon](https://trello.com/c/0hUluTN4/1128-database-version)
			  id:: 644c0a6f-c32b-440e-957f-baa7436c1b0b
			  collapsed:: true
				- Pros/Cons
					- Pros
						- New changes and features
						  id:: 6918d012-e2ab-4d39-bbc5-19331e450a2a
							- [feat: cmd+k move blocks · logseq/logseq@dc9f714 · GitHub](https://github.com/logseq/logseq/commit/dc9f714)
							- Mobile app - quick add (share sheet?)
							- MCP server
							  collapsed:: true
								- https://github.com/logseq/logseq/pull/12111
								- {{video https://www.loom.com/share/d72749e88e0246b5a24d48fd1b1ec60d}}
								- https://github.com/logseq/logseq/blob/master/deps/cli/CHANGELOG.md#030
								-
							- logseq CLI
							-
					- ### Lacks
						- ### Database version missing features
						  id:: 69046afc-ccc7-4cc6-b782-a66d6f5a1c17
							- Pros/Cons for swapping over to Logseq DB now
								- Pros
									- Better performance
										- Will save a lot of time with no freezes
										- Motivation to develop plugins to gain any other functionality
										- Motivation to create github issues to address other missing functionality
								- Cons
									- Unsure when/if ((69046b01-137d-4bef-b65d-47734fd7e142)) will be ready
										- **Then again I can just merge them now**
							- [Merge two graphs including assets and links](https://discord.com/channels/725182569297215569/1433725402685378580)
							  id:: 69046b01-137d-4bef-b65d-47734fd7e142
								- This would make me confident to migrate one of my graphs over to DB version, knowing that I'll be able to still merge all (or as many as I want) of my graphs together for productivity purposes. It's annoying that [[Software]] for example wants to be in both graphs
							- ((67375e40-71ad-4122-a04e-e1bd3a35aca4)) availability
								- Ideal for making me confident that data isn't stuck in DB format with no way to recover it. Then again, DB manual exports are possible
							- [Linked references are expanded by default and this heavily impacts performance](https://github.com/logseq/db-test/issues/546)
							  id:: 69188a2a-767f-4293-a808-02031a9cc337
								- https://discord.com/channels/725182569297215569/1439256373136457860
									- Changing `:ref/default-open-blocks-level 2` to `0` didn't help
								- [Copilot Pro agent session](https://github.com/copilot/tasks/pull/PR_kwDOQbTpoc61L4u7?session_id=054f6d56-6dad-4a7b-82bc-f33b53ce7976)
									- `src/main/frontend/ui.cljs`
										- Now I can see that the foldable component renders the content function only when it's not collapsed (line 673). The key issue is that the `references` component in reference.cljs starts processing (fetching data) immediately in its `hooks/use-effect!` hook, regardless of whether the section is collapsed or not.
									- `yarn watch`
								- To test
									- ```
									  :ref/default-open-blocks-level 0
									  :ui/auto-expand-block-refs? false 
									  ```
									- My other config
										- ```
										   :ref/linked-references-collapsed-threshold 5
										    :feature/enable-journals? true
										   :default-home {:page "Programming"}
										   :feature/enable-whiteboards? true
										   :editor/preferred-pasting-file? true
										   :ui/auto-expand-block-refs? false
										   
										    ;; Block content larger than `block/content-max-length` will not be searchable
										   ;; or editable for performance.
										   :block/content-max-length 30000
										  
										   ;; Whether to show command doc on hover
										   :ui/show-command-doc? true
										  
										   ;; Whether to show empty bullets for non-document mode (the default mode)
										   :ui/show-empty-bullets? true
										   
										    ;; Setup custom shortcuts under `:shortcuts` key
										   ;; Syntax:
										   ;; 1. `+` means keys pressing simultaneously. eg: `ctrl+shift+a`
										   ;; 2. ` ` empty space between keys represents key chords. eg: `t s` means press `s` follow by `t`
										   ;; 3. `mod` means `Ctrl` for Windows/Linux  and `Command` for Mac
										   ;; 4. use `false` to disable particular shortcut
										   ;; 4. you can define multiple bindings for one action, eg `["ctrl+j" "down"]`
										   ;; full list of configurable shortcuts are available below:
										   ;; https://github.com/logseq/logseq/blob/master/src/main/frontend/modules/shortcut/config.cljs
										   ;; Example:
										   ;; :shortcuts
										   ;; {:editor/new-block       "enter"
										   ;;  :editor/new-line        "shift+enter"
										   ;;  :editor/insert-link     "mod+shift+k"
										   ;;  :editor/hightlight       false
										   ;;  :ui/toggle-settings     "t s"
										   ;;  :editor/up              ["ctrl+k" "up"]
										   ;;  :editor/down            ["ctrl+j" "down"]
										   ;;  :editor/left            ["ctrl+h" "left"]
										   ;;  :editor/right           ["ctrl+l" "right"]}
										   :shortcuts {:editor/new-block "enter"
										   :editor/backspace ["ctrl+d" "backspace"]
										   :editor/right ["l" "right"]
										   :ui/toggle-right-sidebar ["t r" "f2"]
										   :editor/new-line "shift+enter"
										   :editor/left ["h" "left"]
										   :ui/toggle-left-sidebar ["t l" "f1"]
										   :editor/escape-editing ["shift+backspace"]
										   :editor/up ["k" "up"]
										   :editor/down ["j" "down"]
										   :editor/open-edit ["i" "enter"]}
										  ```
				- Status
					- ((67375e40-2c1c-485f-b156-dec70830bc1b))
					- [Changelog (on forum)](https://discuss.logseq.com/t/logseq-db-changelog/30013)
					- ## [db-test repo - issues](https://github.com/logseq/db-test/issues?q=is%3Aissue%20state%3Aopen%20sort%3Areactions-desc)
					- My testing
						- [[2025-08-16 Saturday]] Web version doesn't seem to work when I try to Export. [Desktop version](https://github.com/logseq/logseq/actions/workflows/build-desktop-release.yml) goes white and crashes during import of my `test-full-graph`. Need to wait for Web version to get RTC sync since it didn't crash during import
					- Closed alpha version finished [[2024-07-31 Wednesday]]. Will likely not be open alpha until 2025
						- Has
							- Reliable multi-window
							- Import MD files to database
							- Table view
							- Improved undo/redo
						- Lacks
							- [Importer todos](https://github.com/logseq/docs/blob/master/db-version.md#importer-todos)
							  id:: 67c0e8f3-614d-4747-80e9-6bd79f9bf4b6
								- Import pdf annotations as `#PDF Annotation`
								- Import org mode files
								- Import text files e.g. *.txt or *.edn
								- Query macros and related query filters that have changed
							- DB -> Markdown
							- Kanban view
							- Experiment with two-way sync between db and Markdown files
					- [Updates on the Logseq DB Alpha - YouTube](https://youtu.be/8NJ2xpCx0vY) [[2024-09-27 Friday]]
						- Seems you can put # tags on different nodes and it'll help organise
						- It doen't look suitable for tables arbitrarily, but can do global tables well e.g. all items with a #Book tag have the same property columns
				- [Why](https://discuss.logseq.com/t/why-the-database-version-and-how-its-going/26744) [[2024-04-29 Monday]]
				  collapsed:: true
					- Context
						- Everyone loves plain-text files, and with tools like Git and Obsidian, we can use them in conjunction with Logseq. However, there are some limitations:
							- Building real-time collaboration on top of Markdown files is extremely challenging, for example:
								- Creating a new block requires rewriting the entire Markdown file.
								- Renaming a page updates all files that reference it.
							- The structure data support is limited compared to a database, lacking features like persistent IDs, timestamps, and more.
						- Templates and properties make it easy to add new books, papers, and more, but they’re difficult to maintain and collaborate on.
						- Our vision is to **create a better environment for learning and collaboration**. The current app falls short of our goals, with limitations including:
							- No web support (except for limited support on [https://demo.logseq.com](https://demo.logseq.com/)).
							- Data loss when using Logseq sync with multiple clients.
							- Poor performance with large graphs.
								- #+BEGIN_IMPORTANT
								  Biggest issue I've personally faced
								  #+END_IMPORTANT
							- Unreliable undo functionality.
							- No built-in publishing support for pages.
						- We received so much love and support from you guys that it’s unacceptable that Logseq still loses data. We wanted to do better so we started to build a solid foundation for the future: the database version, the goals are:
							- Be stable, improved data stability, reliable undo/redo
							- Be performant, fast to open, fast to type
							- Be joyful, anyone can create any workflow with the new classes and properties
						- We’ve also decided to develop the new database version **with real-time collaboration (RTC) in parallel**, as implementing RTC with offline support is extremely complex. By considering RTC early in the design process, we can minimize the risks of having to change our implementation later on.
					- Challenges
						- Storage
							- The new database version should be accessible across multiple platforms, including Web, Electron, and Mobile.
							- It should be capable of handling large-scale data, effortlessly supporting up to 50,000 pages.
							- Your data should be safe, they should never be erased by browsers
							- To facilitate advanced querying, the new database version should offer support for Datalog queries.
							- Furthermore, it should provide flexibility by allowing users, plugins or even other apps to create custom classes and properties.
						- An intuitive UX for classes and properties
							- Writing should be a delightful experience
						- RTC should work offline
							- We’re committed to local-first, where users have full control over their data
						- RTC should support End-to-End encryption
							- Yes, privacy-first
					- To enable:
						- Performance +++
						  No more re-index required
						  No more structural parsing required
						  Reliable page & block timestamp
						  Reliable page & block history
						  Reliable sync & RTC
						  Reliable & snappy multi-window
						  Enabling more features on web app
				- [Docs](https://github.com/logseq/docs/blob/feat/db/db-version.md)
					- [DB version changes](https://github.com/logseq/docs/blob/feat/db/db-version-changes.md)
					- Built on [SQLite](https://github.com/logseq/sqlite-db)
						- Our forked [Datascript](https://github.com/logseq/datascript)). We added persistent storage support and other features, currently, the underlying data will be stored to SQLite through [sqlite-wasm](https://github.com/sqlite/sqlite-wasm).
				- When it's released
					- Make more use of deep linking (URI) - `copy block URL` then `xdg-open logseq://graph/logseq-unenc?block-id=65a98a51-0b92-4884-bdea-87e4db5ed40a`
					- Use https://github.com/Joemnewton/logseq-reminder-notifications-db
					-
				- Other new features
					- [New tags](https://discuss.logseq.com/t/introducing-newtags-with-examples/32310)
			- _Major_
				- *Regressions*
					- [Bug - collapsing using the vertical line no longer works properly anymore](https://github.com/logseq/logseq/issues/6536)
						- [fold/unfold on levels (without content selected) does not work anymore / as before · Issue #6530 · logseq/logseq · GitHub](https://github.com/logseq/logseq/issues/6530)
						- `block.cljs` for `block-children-left-border`
						  [fix: performance degrading for nested linked references · logseq/logseq@eeb827a · GitHub](https://github.com/logseq/logseq/commit/eeb827a1d35bd471d4ff79a5bc5263c4a2656000)
					- [Pasting text from Firefox adds in line breaks](https://github.com/logseq/logseq/issues/9303)
					  Using MarkDownload extension to copy fixes this but takes extra time
					- {Archive} Fixed
					  collapsed:: true
						- Can't reinstall original for https://github.com/abtris/logseq-plugin-automatic-url-title because of GitHub rate limiting
							- https://github.com/logseq/logseq/issues/10328
							- https://github.com/logseq/logseq/issues/9865#issuecomment-1752149426
						- [Block references always automatically expands when moving to any block after update to 0.8.13](https://github.com/logseq/logseq/issues/7802)
							- This PR caused it: [fix: open inline block refs by default when zoom in a block by tiensonqin · Pull Request #7650 · logseq/logseq · GitHub](https://github.com/logseq/logseq/pull/7650)
				- Lacks VIM keybindings
				- Programming support
					- [GitHub - logseq/nbb-logseq: nbb with features enabled for logseq](https://github.com/logseq/nbb-logseq)
					- ((687014b9-a5fe-4f00-96d4-4c946c994158))
				- Make the breadcrumbs a sticky header
				- Doesn't show entire breadcrumbs
				  collapsed:: true
					- [https://discuss.logseq.com/t/ability-to-show-entire-breadcrumbs-instead-of-truncated/7940](https://discuss.logseq.com/t/ability-to-show-entire-breadcrumbs-instead-of-truncated/7940)
					- [https://discuss.logseq.com/t/how-do-you-get-entire-breadcrumbs-to-show-instead-of-it-being-truncated/7892](https://discuss.logseq.com/t/how-do-you-get-entire-breadcrumbs-to-show-instead-of-it-being-truncated/7892)
				- Slow performance with large local graph? Need to test it more
				  collapsed:: true
					- Slow performance
					- [https://trello.com/c/68pohS4z/1125-performance-improvement](https://trello.com/c/68pohS4z/1125-performance-improvement)
						- [https://github.com/logseq/logseq/issues/2792#issuecomment-919924561](https://github.com/logseq/logseq/issues/2792#issuecomment-919924561)
						- Poor performance when I have 100k line per MD file
							- [https://discuss.logseq.com/t/very-slow-performance-with-large-local-graph/1484/22](https://discuss.logseq.com/t/very-slow-performance-with-large-local-graph/1484/22)
							- [https://github.com/logseq/logseq/issues/6002](https://github.com/logseq/logseq/issues/6002)
						- _Testing 14/07/22_
							- With 800k words MD file (Life2, 45k lines, 5M characters) it freezes for 5-10 seconds when expanding/collapsing level 3 bullets
							- With 400k words MD file (Mind, 10k lines, 2.5M characters) it freezes for 1-2 seconds when expanding/collapsing level 3-8 bullets
							- _To test_
								- 500k words (Fan [fiction.md](http://fiction.md), 30k lines, 4.2M characters)
					- Crash when trying to re-index
						- https://github.com/logseq/logseq/issues/6154
					-
				- ((636381e5-30ab-4830-ae58-7472732fbf8f))
				- ((65f6b84d-6181-4e2c-983e-d95dfecd2a99))
					- {{embed ((65f6b84d-6181-4e2c-983e-d95dfecd2a99))}}
			- _Moderate_
				- [EPUB support](https://discuss.logseq.com/t/support-epub-format-ebooks/2010)
				  Unlike PDFs it would be smaller, just text content etc
					- When this is released then clip all future articles in this format and just annotate them. This is because when I use ((644c0b2c-99ab-4e9e-9c67-0862dd593479)) it is easy for importing into LS but it doesn't ensure the article is read-only and doesn't show up in search
				- Push notification reminders
					- [Task notifications](https://discuss.logseq.com/t/task-notifications/6638)
				- Favourite blocks in the left sidebar
				  collapsed:: true
					- [https://discuss.logseq.com/t/favorite-blocks-on-left-sidebar/5778](https://discuss.logseq.com/t/favorite-blocks-on-left-sidebar/5778)
				- Better table/database support
				  id:: 660e8211-9d7c-4fac-b0c5-3c646bab8bb9
				  collapsed:: true
					- _Current_
						- _Native_
							- Queries
							  collapsed:: true
								- Each block can have properties
									- Cons
										- This means defining each cell by one primary datatype. Though this could be something like a unique ID
										- GUI needs to allow easily editing the property (column) name for all blocks simultaneously
									- Example
										- Perk Cafe
										  																			  type:: Coffee Shop
										  																			  address:: 123 Main St.
										  																			  serves_food:: Yes
								- Documentation
									- [https://docs.logseq.com/#/page/queries](https://docs.logseq.com/#/page/queries)
									- [Logseq simple queries ](https://logseq.github.io/#/page/queries)<a href="https://logseq.github.io/#/page/queries">206</a> are intended for those not comfortable in datascript/datalog/datomic language. I collect examples of powerful simple queries for future usage:
										- Find all blocks referencing the page: `[[Logseq]]`, `#Logseq` or `tags:: Logseq`.
										  {{query [[Logseq]]}}
										- Find all pages with page tags `tags:: book` .
										  {{query (page-tags book)}}
										- Find all pages with both page tags `logseq` & `queries`.
										  {{query (and (page-tags logseq) (page-tags queries))}}
										- Find all pages with page tags `logseq` or `queries`
										  {{query (page-tags logseq queries)}}
										- Find all Todo blocks `doing` or `now`
										  {{query (todo doing now)}}
										- Find Todo blocks done in last 7 days.
										  {{query (and (todo done) (between -7d today))}}
										- Find all Todo/Doing Now/Later blocks in current page.
										  {{query (and (todo todo doing now later) (page <% current page %>))}}
										- Find all Todo/Doing Now/Later blocks where `tiensonqin` was tagged.
										  {{query (and (todo todo doing now later) [[tiensonqin]]) }}
									- [https://github.com/logseq/logseq/blob/master/src/main/frontend/db_schema.cljs](https://github.com/logseq/logseq/blob/master/src/main/frontend/db_schema.cljs)
						- [Markdown Table Editor Plugin](https://github.com/haydenull/logseq-plugin-markdown-table])
						  id:: 649b131d-54ae-4050-ab97-fa37bd72445c
						  collapsed:: true
							- Pros
							  collapsed:: true
								- Nice pop-up GUI, could very easily be the basis for Notion-like GUI
							- Cons
								- Tables are Markdown-based rather than each row or cell being a block, which may limit interlinking opportunities
								- _Lacks_
									- Could use with more features to match ((6631e29c-5695-4a50-92cd-10285688826d)) parity
									  [https://github.com/haydenull/logseq-plugin-markdown-table/issues/13](https://github.com/haydenull/logseq-plugin-markdown-table/issues/13)
						- [tablerender-plugin](https://github.com/hkgnp/logseq-tablerender-plugin)
						  id:: 660e8211-7aa5-4e68-aa70-211628be9d00
						  collapsed:: true
							- Pros
							  collapsed:: true
								- Very portable by it being represented by plain text
							- Lacks
								- Table is live rendering always even if I try to zoom into a single column/row to edit that because the table is always in the breadcrumbs at minimum. This is because the table renderer is linked to whatever bullets are below it, instead of renderers being linked to specific tables
								- Can't make every cell a hyperlink to the block. This would be very handy for converting many of my WorkFlowy sections to tables e.g. [Top Alternatives for WorkFlowy](https://workflowy.com/#/a6ec6e76920b) would have Logseq|Pros/Cons|Documentation and Athens Research|Pros/Cons|Documentation
								  [https://github.com/hkgnp/logseq-tablerender-plugin/issues/9](https://github.com/hkgnp/logseq-tablerender-plugin/issues/9)
						- [csv2logseq_block](https://github.com/Arrowyz01/csv2logseq_block)
						  collapsed:: true
							- Pros
								- Easy import of existing CSVs
							- Cons
								- Not properly integrated as a plugin. Requires running the tool on CLI
						- [logseq-plugin-luckysheet](https://github.com/sethyuan/logseq-plugin-luckysheet)
						  collapsed:: true
							- Inserts
							  [https://github.com/mengshukeji/Luckysheet](https://github.com/mengshukeji/Luckysheet)
					- _Feature requests_
						- [Table creator GUI (currently have to paste or type in Markdown tables)](https://discuss.logseq.com/t/table-creation-interface-not-query-table/1974)
						- [Notion-like databases](https://discuss.logseq.com/t/excel-notion-like-databases/4035)
						- [Kanban/tables](https://discuss.logseq.com/t/kanban-tables/1264)
						- [Support for plain text search in simple queries - Feature Requests - Logseq](https://discuss.logseq.com/t/support-for-plain-text-search-in-simple-queries/665/)
						- [Notion database functionality](https://discuss.logseq.com/t/is-it-possible-to-implement-notion-database-functionality-in-logseq/2128)
						- [Notion tables](https://discuss.logseq.com/t/tables-broad-like-that-in-notion/1529)
						- [Reimagining Query Tables (editing, database features, etc.) - Feature Requests - Logseq](https://discuss.logseq.com/t/reimagining-query-tables-editing-database-features-etc/9568)
					- Related:
						- ((636381e5-30ab-4830-ae58-7472732fbf8f)) : ((653e4732-ef31-431b-bea3-0f5891aa0290))
						- ((6525b49e-8fcd-4440-9a3e-3c65d4edb58b))
						- ((6525b49d-1200-4868-9453-784db52d5987))
						- ((6525b49e-aeb9-406e-a1e6-7ca7d14f9630))
				- [SingleFile/HTML support](https://discuss.logseq.com/t/read-html-documents-like-pdf/2012)
				- [Show Block's page breadcrumbs when in-line linking](https://discuss.logseq.com/t/show-blocks-page-when-inline-searching/694/2)
				- [Keyboard shortcut for "copy block reference" (i.e. copy bullet link)](https://discuss.logseq.com/t/quick-way-to-add-a-block-embed-for-linked-references-drag-and-drop-or-link-button/118)
					- Note: web app supports OPML for imports
				- [Support Markdown checkboxes as Logseq tasks](https://discuss.logseq.com/t/treat-markdown-checkboxes-as-ls-tasks/965/4)
				- [Hide certain blocks or blocks and their children from search results - Feature Requests - Logseq](https://discuss.logseq.com/t/hide-certain-blocks-or-blocks-and-their-children-from-search-results/26998)
				- Better web clipper built on [Defuddle](https://news.ycombinator.com/item?id=44067409)
			- _Minor_
				- [Block-level graph view](https://discuss.logseq.com/t/block-level-graph-view/6303)
				- [Converting blocks to pages](https://discuss.logseq.com/t/moving-a-block-to-another-page-location-or-converting-it-to-a-page-and-vice-versa/156/7) (equivalent to Dynalist items <> pages)
				  collapsed:: true
					- Related
						- [https://github.com/hyrijk/logseq-plugin-block-to-page](https://github.com/hyrijk/logseq-plugin-block-to-page)
						- [https://github.com/vipzhicheng/logseq-plugin-move-block](https://github.com/vipzhicheng/logseq-plugin-move-block)
			- Plugin issues/lacking features
				- [do not format URLs in code tags by borutmrak · Pull Request #16 · 0x7b1/logseq-plugin-automatic-url-title · GitHub](https://github.com/0x7b1/logseq-plugin-automatic-url-title/pull/16)
				-
	- ## Unclear
		- Can  headings be used?
		- Can text be given a background colour?
	- ## Comparisons
		- ((62e297f8-1bfa-4cce-9c87-9a45000893dd))
		  collapsed:: true
			- {{embed ((62e297f8-1bfa-4cce-9c87-9a45000893dd))}}
		- [[Logseq]] vs ((6313462d-10af-4744-92d2-041a06816d23))
		  collapsed:: true
			- Pros
				- Additional features compared to WorkFlowy, which reduces the con: [Some data should be moved into different apps which offer less limitations or more features](https://workflowy.com/#/023f444ddf1a)
					- Code blocks with syntax highlighting - allows reducing Dynalist reliance (still is useful for QuickDynalist/inbox feature)
					- PDF annotation - eliminate Zotero reliance
					- Can open any type of local file - eliminate TagSpaces reliance
				- Additional features which are just generally better than WorkFlowy
					- See [Page/version history](https://workflowy.com/#/2ed631528717)
					- See [Client-side encryption](https://workflowy.com/#/e7f2927a3ba4)
					- See [YouTube timestamp support](https://workflowy.com/#/5dc5ff5abef1)
				- WorkFlowy can't handle a large amount of bullets well, input workflow is too slow and reliability is poor
					- WF takes at least a minute to load so I usually use Markor or Obsidian to take notes
					- WF unloads in background on mobile, on desktop it often fails to load
					- WF is also very time consuming to export, and reliability may not be there anymore
		- [[Logseq]] vs ((62f63614-33b0-4e8d-b42a-7987bdf192d1))
		  collapsed:: true
			- {{embed ((62e8e0fc-9f1d-4e8b-9e21-d5b0e4ff84f8))}}
			-
		- [[Logseq]] vs ((634bc1d7-6c8e-4cb1-8b72-5ebdbfb847ee))
		  id:: 6712e8fc-c577-4c88-84c0-1f71ed8de159
		  collapsed:: true
			- For [[Logseq]]
				- Database mode allows scaling indefinitely. I'm not sure how plain text editors are able to scale
				- Cross-platform
				- Great plugins for modern usecases e.g. ((653cd59e-8634-47f6-aa9f-64ada1deef9c)), ((66caed0a-99b0-4633-8876-46f752dd5208)), etc
				- Modern UI
			- For ((634bc1d7-6c8e-4cb1-8b72-5ebdbfb847ee))
				- Plain text editors like ((634bc1d7-6c8e-4cb1-8b72-5ebdbfb847ee)) and ((634d22db-89bb-432b-8dcf-776e2bd185ba)) are some of the longest updated software in existence
				- Larger community, especially with many developers
				- Long history
				- ((634d22db-89bb-432b-8dcf-776e2bd185ba)) support with ((664373fe-15d7-47a1-8472-08013e1929de)) or evil
				- More plugins and more powerful ones e.g. magit
			- Similarities
				- ((62e283e5-ce69-4a9b-97e2-9be105f7ff35))
				- Plugin support
				- Different languages for core code vs plugin system
					- Logseq uses Clojure for core code, JavaScript for plugins
					- Emacs uses C for core code, Lisp for plugins
					- Neovim uses C for core code, Lua or VimScript for plugins
			- Related: ((671377eb-39eb-4971-a3cb-bdbb8c34568f))
- My Upwork Python script for converting OPML to MD
  collapsed:: true
	- Run using
	  `python3 convert.py`
	- 1 Backlink
		- OPML import has bugs (then again can get a custom conversion script made, see [My Upwork Python script for converting OPML to MD](https://workflowy.com/#/30533acab5d8))
- # Documentation
	- [Official docs](https://docs.logseq.com/#/page/Contents)
	- [Official docs 2](https://hub.logseq.com/)
	- [Unofficial docs](https://mschmidtkorth.github.io/logseq-msk-docs/#/page/Logseq%20-%20Unofficial%20Documentation)
	- Installation
	  collapsed:: true
		- Firejail + ((63a43fcd-7346-4ef8-a922-050ec3ffe517))
			- Using in order to have two separate Logseq profiles using AppImage
	- Paid Aspects
		- [Logseq Sync](https://blog.logseq.com/how-to-setup-and-use-logseq-sync/)
		  id:: 67375e40-71ad-4122-a04e-e1bd3a35aca4
	- Technology
	  collapsed:: true
		- Uses datascript to create a DB to allow collaboration?
		  [https://github.com/tiensonqin/datascript](https://github.com/tiensonqin/datascript)
	- Basics
	  collapsed:: true
		- By default Pages are created as Markdown
		- Markdown syntax used
		  [https://docs.logseq.com/#/page/markdown](https://docs.logseq.com/#/page/markdown)
		- [logseq://graph/logseq-data?block-id=6141d4f8-39d8-44f4-83b3-7c2fa82a02fb](logseq://graph/logseq-data?block-id=6141d4f8-39d8-44f4-83b3-7c2fa82a02fb)
		- `/` to activate trigger menu
	- Aliases and external links
	  collapsed:: true
		- How to create a page which will redirect to a block
			- s
			- Test
			- [[Testblock]]
			- Test block
				- alias:: testblock
			- Unrelated
				- https://docs.logseq.com/#/page/term%2Falias
				-
		- ...
		- It's also possible to link to pages outside of Logseq, i.e. websites. To point to a URL, either use the trigger menu by typing /link or use the keyboard shortcut Cmd-l (macOS)/Ctrl-l (Windows) to add the following shortcode to the block: `[]()`. Between the brackets `([ ])`, put the label (name) of the link. Between the parenthesis, put the URL:
			- [This is the label or name of the link]([https://thisistheurl.com](https://thisistheurl.com))
		- Apart from linking to pages outside of Logseq, you can also use the alias function to link to an internal page. This is handy for when you want to show a different label for an internal link. For example, [I worked on projects]([[Projects]]) will make the entire "I worked on projects" sentence clickable and point it to the Projects page.
		- Finally, for aliases that you use often it's best to add a page alias. For example, you might want the link [[PKM]] to point to the page Personal Knowledge Management. To do this, add the following in the first block of the page Personal Knowledge Management: alias:: PKM
		- Now, anytime you click a [[PKM]] link, you'll end up on the Personal Knowledge Management page.
	- Local file links
	  collapsed:: true
		- ```
		  ![file title](/filepath.jpg) 
		  ![file title](file:///filepath.jpg)
		  [file title](/filepath/filename.xxx)
		  [file title](file:///filename.xxx)
		  ```
	- How to copy and paste links (block references)
	  collapsed:: true
		- _Either_
			- right-click, “copy block ref”, pasting it will look like: ((6140b721-66ca-4682-861a-ef2f59072268)) but then turns into the block it refers to.
			- The same thing as above, copying block ref, but now pasting it as {{embed ((string of numbers))}}, it shows not just as a link, but the complete block. The nice part is that you can edit this block in either location, because it points to literally one and the same block.
			- It’s also possible to type ((, which then becomes ((<cursor)), and you lookup the block you want to link to.
		- Give each link an alias e.g. `[Founders and Coders](((629ccb26-c33a-4e26-8262-1fe1d869027a)))`
			- This ensures that my outliner has better forward compatibility, incase in the future I need to move to another app
	- Block references = internal links in WorkFlowy. Copy block ref = Copy link
	  collapsed:: true
		- Use `[test]` infront of block refs to change the text on the link (AKA alias)
	- Block embeds = mirroring in WorkFlowy
	- [Properties](https://docs.logseq.com/#/page/term%2Fproperties)
	  collapsed:: true
		- Example
			- No concept of WorkFlowy Notes in Logseq, instead just create a multi-line block
			  status:: released
			  genre:: Action-Adventure
			  rating:: 5
			- Looks similar to a code block
	- Tags are pages? [[test]]
	- [Tasks and todos](https://docs.logseq.com/#/page/tasks%20%26%20todos)
	- [PDF highlights](https://docs.logseq.com/#/page/pdf%20highlights)
	- LaTeX
	  id:: 644c0a6f-3f3f-4d6b-8c4e-85ce1df31255
	  collapsed:: true
		- `$$E = mc^2$$` represents as $$E = mc^2$$
		- ((63664cf4-bae5-4dc5-98ec-2705f29717b3)) admonitions
			- {{embed ((63664cf4-bae5-4dc5-98ec-2705f29717b3))}}
		- Related: ((635eb280-ab1e-42b6-b5c4-49eef87e8ad3))
	- On-Disk Encryption is deprecated
	  collapsed:: true
		- [Why it's deprecated](https://discuss.logseq.com/t/deprecation-of-on-disk-encryption/12334)
		  collapsed:: true
			- Notice: The encryption feature mention here is about the on-disk encryption, which is an **experimental feature** and is **not enabled by default**. The end-to-end encryption trait of Logseq Sync is not related or affected.
			- Maybe some of our users have noticed [the recent removal 1](https://github.com/logseq/logseq/pull/7221) of the experimental on-disk encryption feature from Logseq codebase, and the feature will not be included after  `0.8.10` . Existing encrypted graph may be decrypted with [the neat encryption UI from Kanru 4](https://github.com/kanru/logseq-encrypt-ui).
			- As a local-first tool for thought, privacy is one of our top 
			  consideration, and removing the on-disk encryption support is a tough 
			  decision for all of us. However, we have to make it because of the 
			  following reasons:
			-
			- **The current status of the on-disk encryption feature is not developed enough to meet our standards**, and this explains why it’s the only feature labeled as “experimental”. There are some implicit bugs (like [1 2](https://github.com/logseq/logseq/issues/6834), [2 3](https://github.com/logseq/logseq/issues/7031))
			   without a clear path to reproduce. Also, the lack of idiot-proof design
			   makes it hard for users to use correctly. Due to the nature of 
			  encryption, any misuse of the feature would be fatal to data integrity, 
			  then spread panic.
			-
			- **We can’t afford the excessive effort to maintain the on-disk encryption feature.**
			   It’s too intrusive to the core of Logseq, and causes a number of edge 
			  cases to cover. The situation gets worse and worse following the rapid 
			  development of Logseq. Also, given that Logseq is a cross-platform tool,
			   we have to ensure the on-disk encryption works on all platforms and 
			  endures all cross-device data sync scenarios, which is a too 
			  overwhelming task.
			-
			- **The on-disk encryption feature is incompatible with Logseq Sync.** We received a few [bug reports 2](https://github.com/logseq/logseq/issues/7245)
			   with both the on-disk encryption feature and Logseq Sync enabled. As 
			  Logseq Sync is encrypting the file content already, the extra on-disk 
			  encryption towards the content triggers buggy cases.
			-
			- ### 
			   [](https://discuss.logseq.com/t/deprecation-of-on-disk-encryption/12334#how-to-decrypt-my-data-1) How to decrypt my data?
			- You can still visit your encrypted data in a previous version of Logseq (before  `0.8.10` )
			- There’s a nice UI for doing the encryption / decryption outside of Logseq: [https://github.com/kanru/logseq-encrypt-ui 4](https://github.com/kanru/logseq-encrypt-ui)
			-
			- ### 
			   [](https://discuss.logseq.com/t/deprecation-of-on-disk-encryption/12334#possible-alternative-2) Possible alternative
			- If you are using Logseq Sync already, no extra on-disk encryption 
			  feature is required - Logseq Sync is doing end-to-end encryption with [AGE 12](https://github.com/kanru/rage-wasm).
			- Other alternatives are [EncFS 5](https://en.wikipedia.org/wiki/EncFS) and [VeraCrypt 2](https://www.veracrypt.fr/code/VeraCrypt/)
		- Documentation
			- To enable encryption
				- Click the `...` in the top-right for Settings > Editor > Encryption
			- To check on encrypted graphs (AKA encrypted local directories)
				- Top-left click the graph name > All Graphs > check for the padlock symbol next to it
			- [https://github.com/logseq/logseq/pull/1073#issuecomment-760269309](https://github.com/logseq/logseq/pull/1073#issuecomment-760269309)
			- Standalone app to decrypt
			  [https://github.com/kanru/logseq-encrypt-ui](https://github.com/kanru/logseq-encrypt-ui)
				- Alternatively use these CLI apps since it uses `age` to encrypt
					- The file can be decrypted by [https://github.com/filoSottile/age](https://github.com/filoSottile/age) or <a href="https://github.com/str4d/rage">https://github.com/str4d/rage</a>
	- [Keyboard shortcuts](https://docs.logseq.com/#/page/keyboard%20shortcuts)
	  id:: 63209777-2774-4345-8a71-d508db2c73ab
	  collapsed:: true
		- ## Important
		  id:: 66bf58c0-74a1-4f7d-bd9c-331818ccc2d8
			- 2x ((66bf589d-f7b6-403f-a772-e3a60d906a13)), then ((65ea222b-3b8c-4033-ad2c-2b4c09a2fa2d))
			  id:: 66bf58c3-661e-4a09-8788-eea2bd23b6e3
			- ((66c5fbab-12a4-4a79-bf72-85388bb17d38))
			- Block manipulation
				- ((67375e40-daa9-4cf0-9544-02fe5cedaa25))
				- ((67375e40-c1ab-4c16-a1b4-45e1a1774ef9))
				- ((644c0a6f-b1f5-483d-bc22-bc8d2c4dfc6b))
				- ((67375e40-ac40-4ed0-a57b-e0f2d4242fee))
		- Basics
			- `CTRL + ;` = toggle expanded/collapse state of currently edited or selected blocks
			  id:: 65ea222b-3b8c-4033-ad2c-2b4c09a2fa2d
			- `Enter`/`CTRL + G` = Jump to the next match to your Find bar search
			- `SHIFT + ENTER`/`CTRL + SHIFT + G` = Jump to the previous match to your Find bar search
			- `CTRL + K` = focus the search box
			  id:: 6320977a-e2c4-481a-aadb-30f3aa088d8a
			- `CTRL + SHIFT + K` = search blocks in the current page
			- `CTRL + C` = copy block reference
			- `CTRL + E` = copy block embed
		- Navigation
			- `ALT + Left` = Zoom out editing block / Backwards otherwise
			- `ALT + Right` = Zoom in editing block / Forwards otherwise
			- `CTRL + Up` = Collapse
			  id:: 67375e40-daa9-4cf0-9544-02fe5cedaa25
				- Related:
					- ((6855c4fe-a438-47aa-b315-beced6e70f93))
					- ((680abbd5-00e2-46c6-9202-93b8883f8273))
			- `CTRL + Down` = Expand
			  id:: 67375e40-c1ab-4c16-a1b4-45e1a1774ef9
				- Related: Heynote :
					- ((6855c51f-67d4-4633-a7ed-77e75ff12d3c))
					- ((680abbd5-016e-4f93-9b13-59890bf9cbfc))
			- `CTRL + [` = Backwards
			  id:: 660e8211-4059-4b67-86b4-c280ef9d223f
			- `CTRL + ]` = Forwards
			- `G H` = Go to home
			- `G J` = Go to journals
			- `G A` = Go to all pages
			- `G S` = Go to keyboard shortcuts
		- Block editing general
			- `ESC` = Escape editing current block
			- `CTRL + Left` = Move cursor by whole word to the left
			- `CTRL + Right` = Move cursor by whole word to the right
			- `CTRL + Enter` = Rotate the TODO state of the current item
			- `CTRL + O` = Follow link under cursor
			- `ALT + SHIFT + Up` = Move block up
			  id:: 644c0a6f-b1f5-483d-bc22-bc8d2c4dfc6b
			- `ALT + SHIFT + Down` = Move block down
			  id:: 67375e40-ac40-4ed0-a57b-e0f2d4242fee
			- mod+click support deselect if it's on an selected block
			- support mod+shift+click
		- Block command editing
			- `ALT + L` = Delete entire block content
			- `ALT + A` = Move cursor to the beginning of a block
			- `ALT + E` = Move cursor to the end of a block
			- `ALT + D` = Delete a word forwards
			- `ALT + W` = Delete a word backwards
			- `SHIFT + Up` = Select content above
			  id:: 67375e40-74d4-484f-aa6e-c5310c7b813d
			- `SHIFT + Down` = Select content below
		- Toggle
			- `T L` = Toggle left sidebar
			- ((63c70226-b36a-4c81-aad3-8bbcccd3e003))
			- `T R` = Toggle right sidebar
			- ((63c702a2-ba5c-4995-9e39-eef0339e04f6))
		- Others
			- `ALT + P` = Previous page of current pdf doc
			- `ALT + N` = Next page of current pdf doc
			- `ALT + X` = Close current pdf viewer
			- `ALT + SHIFT + J` = Open today's page in the right sidebar
			- `CTRL + SHIFT + Y` = Insert YouTube timestamp
			- `CTRL + D` `CTRL + A` = Open file in default app
			- `CTRL + D` `CTRL + I` = Open file in parent directory
			- `C` = Create git commit with message
			- ((6341d63d-cb12-465e-b936-e7efac4abf91))
			- `CTRL + a` = select parent block
			  id:: 66bf589d-f7b6-403f-a772-e3a60d906a13
			- ((65ea222b-3b8c-4033-ad2c-2b4c09a2fa2d))
			  id:: 66bf58aa-ab28-4b62-b5da-2864cf5066d4
			- `c t` = Close top result in right sidebar
			  id:: 66c5fbab-12a4-4a79-bf72-85388bb17d38
		- _Plugin-based_
			- ((6320a718-2f53-4e61-85c6-5a2ec147b46e))
				- ((6320850b-1f87-4653-96d9-fedd85d0201d))
				- ((6320852a-625c-4205-b117-af91259e32f8))
				- ((632d7e38-16db-431e-8c5d-7f9528e3c348))
			- ((6320a764-cc17-427d-be42-49b731d5b593))
			  id:: 6320ab4e-d4b6-44dc-81d4-06b49322739a
				- `MOD + E` = create a new parent block at the end of the current page
				- `ALT + ENTER` = create a sibling block after the current block
				- `CTRL + ALT + ENTER` = create a child block for the current block (NOTE: only works if the current block has 1+ child blocks)
				- `MOD + ALT + C` = copy the selected text as a link to it's block reference
				  id:: 6320abd4-b511-4af7-9023-4c333007a6cd
			- ((634bc0dc-29b0-4264-889d-0d455029e8d2))
				-
	- [Queries](https://docs.logseq.com/#/page/queries)
	  id:: 63503767-41a1-44ac-bcf2-4dfa5351566d
	  collapsed:: true
		- Short intro
			- There're two kinds of queries:
				- Simple queries by using `{{query }}`, the format is something like this: `{{query Something you're looking for}}`. You can type `/query` to create a simple query.
		- Examples
		- Using with [flashcards](((62e8e0fc-4a9a-4ab1-b5e6-7b07d77906ca)))
		- [Functions](https://docs.logseq.com/#/page/6322022c-dab3-4493-bff9-eb2b410bb708)
			- Basically `{{function }}` as a child block of the query block e.g. ``{{function (total :property)}}``
		- [Learning Resources]
			- https://docs.logseq.com/#/page/Query%20Builder
			-
			- [5 must-have queries](https://www.youtube.com/watch?v=_dS-3Nb71mo)
				- 1) `{{query (page-property :type "book")}}` is used on [[book]] page, which summarises many pages which have a particular value (`book`) for a particular property (`type`)
				  [source] https://www.youtube.com/watch?v=_dS-3Nb71mo
			- Self-paced course
				- [**Kick-Off Session:** Supercharge Your Search By Mastering Logseq Queries](https://discuss.logseq.com/t/kick-off-session-supercharge-your-search-by-mastering-logseq-queries/10069)
				- [**Lesson 1:** What Are Logseq Queries and Why You Should Learn to Use Them](https://discuss.logseq.com/t/lesson-1-what-are-logseq-queries-and-why-you-should-learn-to-use-them/9987)
				- [**Lesson 2:** Why You Should Outline and Link Your Notes](https://discuss.logseq.com/t/lesson-2-why-you-should-outline-and-link-your-notes/10038)
				- [**Lesson 3:** How to Think Like a Computer Using Boolean Logic](https://discuss.logseq.com/t/lesson-3-how-to-think-like-a-computer-using-boolean-logic/10074)
				- [**Lesson 4:** How to Search Your Notes Using Query Filters and Links](https://discuss.logseq.com/t/lesson-4-how-to-search-your-notes-using-query-filters-and-links/10131)
				- [**Lesson 5:** How to Power Your Workflows Using Properties and Dynamic Variables](https://discuss.logseq.com/t/lesson-5-how-to-power-your-workflows-using-properties-and-dynamic-variables/10173)
			- [Template for daily time-block planner](https://www.youtube.com/watch?v=D8CRNuuBkoU)
			- https://yewtu.be/watch?v=55s-K1uAUc0
			- https://twitter.com/logseq/status/1523985681265180672
			  collapsed:: true
				- {{twitter https://twitter.com/logseq/status/1523985681265180672?s=20&t=O-uPJMIPHj8-3RhtmNDbug}}
	- Themes
	  collapsed:: true
		- eg
		  [https://discuss.logseq.com/t/cobra-theme-black-and-yellow-awesome-dark-mode/440/14](https://discuss.logseq.com/t/cobra-theme-black-and-yellow-awesome-dark-mode/440/14)
		- Marketplace feature in alpha should allow it
		- Can be swapped between dark and light theme from Settings > General > Theme
		- [[2024-11-15 Friday]] Using Bonofix dark theme
	- Whiteboards
	  collapsed:: true
		- [Built on tldraw](https://github.com/logseq/logseq/pull/5341)
	- **Plugins**
	  id:: 634bc0dc-3d6d-449f-8a00-f3b07ce065fc
	  collapsed:: true
		- Meta
			- ((652d6d35-1af1-481b-b71c-a772db67fb10)) : ((652d6d43-d095-481a-b3d2-c003b34ef506))
		- Installed and activated
			- Awesome Links
			  collapsed:: true
				- Very helpful to have automatic favicons for links due to so many being old WorkFlowy links which need replacing
			- Awesome Styler
			- [Awesome UI](https://github.com/yoyurec/logseq-awesome-ui)
			  Allows for ((6320a718-2f53-4e61-85c6-5a2ec147b46e)) to be wide + at top. Also 80% width search bar
			- [Block to Page](https://github.com/hyrijk/logseq-plugin-block-to-page)
			  id:: 63642a17-9d88-4ac9-bff6-b4d9484f6258
			- [Browser](https://github.com/haydenull/logseq-plugin-browser)
			  collapsed:: true
			  id:: 63642a17-7f8b-40ec-bdb9-e77481938e5a
				- Lacks
					- Toggle so that hyperlinks open in a Logseq iframe rather than external browser
					- Cookies aren't saving bug, so unable to login to sites
				- Usage
					- `CTRL+SHIFT+P` opens command palette
					- Search for "browser" and open "Modify-plugin-browser-config"
					- Text fields
						- Key = mouseover text for the icon
						- Icon = `ti-` prefix (stands for Tabler Icons) followed by the code, e.g. `ti-brand-youtube`
						- ?
						- ? = `{"background":"#fff"}`
			- [Bullet Threading](https://github.com/pengx17/logseq-plugin-bullet-threading)
			  id:: 63642a17-b838-4f25-bce7-67051dfce969
			- *Calibre plugins*
			  id:: 653cd5c0-705e-4455-b094-32148adbaa68
			  collapsed:: true
				- Pros/Cons
					- Pros
						-
					- Cons
						- Issues
							- DONE [Doesn't use the new version of book. Using cached data which doesn't refresh? · Issue #4 · duydl/logseq-calibre-metadata · GitHub](https://github.com/duydl/logseq-calibre-metadata/issues/4)
							  :LOGBOOK:
							  CLOCK: [2023-10-29 Sun 17:09:28]--[2023-10-29 Sun 17:09:29] =>  00:00:01
							  :END:
							- DONE ["Close viewer" button is missing · Issue #6 · duydl/logseq-calibre-annotation · GitHub](https://github.com/duydl/logseq-calibre-annotation/issues/6)
							  :LOGBOOK:
							  CLOCK: [2024-04-03 Wed 13:13:00]--[2024-04-03 Wed 13:13:02] =>  00:00:02
							  :END:
					- Unclear
						- Syncing button just 1-way copies Calibre annotation -> Logseq, as plain text and a hyperlink button
							- Pros
								- Can edit the text of the annotation copy in Logseq if I want to shorten it, add context or other editing e.g. add headings or examples
								  id:: 653d0c25-412c-469b-9464-97981b0b0420
							- Cons
								- It doesn't sync annotation deletions
								- Editing an existing highlight to change or remove an annotation will sync another copy of the highlight+annotation
					- Comparisons
						- ((653cd5c0-705e-4455-b094-32148adbaa68)) vs ((632091d4-2e08-4fd0-8fc5-bb32cc1afc5e))
						  id:: 6bbfa2ff-3d0e-49ba-a01e-e0b447244b50
						  collapsed:: true
							- For ((653cd5c0-705e-4455-b094-32148adbaa68))
								- ((653cd877-e6c4-4e08-a2d7-4b1b992327bf)) is generally in favour of EPUB
								- Logseq storage doesn't get bloated with book storage which makes syncing to mobile easier
								- ((62e29bfa-86b7-424c-bd2c-cb02d005fbaf)) makes it possible to easily search the entire document text, including non-annotated parts
								- All highlights made are automatically copied into Logseq, rather than having to additionally copy + paste them in
								- ((653d0c25-412c-469b-9464-97981b0b0420))
							- For ((632091d4-2e08-4fd0-8fc5-bb32cc1afc5e))
								- Might be quicker to be developed for mobile support
				- ## Plugins
					- [calibreAnnotation](https://github.com/duydl/logseq-calibre-annotation)
					  id:: 653cd59e-8634-47f6-aa9f-64ada1deef9c
						- Issues
							- Syncing annotations between content server and local whilst requiring username/password. Possible since [[2024-07-29 Monday]] but uses browser tab, not integrated viewer
							  collapsed:: true
								- Old notes
									- [GitHub issue](https://github.com/duydl/logseq-calibre-annotation/issues/9) - basically ((653cd597-bd56-4b8f-a889-aa801169a26f)) doesn't sign into my user it signs in as anonymous so these annotations aren't visible on desktop Calibre
									- Calibre > View > Browse annotations
										- Shows all annotations in the library and to which users they each belong to
									- ![image.png](../assets/image_1709295994033_0.png)
										-
						- It'll add the tag `Annotated-CalibreViewer`
						- {Archive}
							- [calibreMetadata](https://github.com/duydl/logseq-calibre-metadata) - now integrated into calibreAnnotation
							  id:: 653cd597-bd56-4b8f-a889-aa801169a26f
							  collapsed:: true
								- Documentation
									- It adds a `C` button to the toolbar
									- In the settings instead of e.g. `http://localhost:3296` change this to the actual IP address on the home network
									  collapsed:: true
										- Note: after some testing I found this unreliable, instead use `http://127.0.0.1:3296`
										- Click on the Calibre Connect/Share button to see the IP address in-use
											- e.g. 
											  ![image.png](../assets/image_1698595271298_0.png)
								- Code contribution
									- Errors [[2024-04-03 Wednesday]]
										- 5x `Failed to execute 'postMessage' on 'DOMWindow': The target origin provided ('file://') does not match the recipient window's origin ('null').`
										- 1x `ERROR: [Loader:#logseq-calibre-metadata - logseq-calibre-metadata][11:32:19] loadhandshake Timeout Error: handshake Timeout`
										  `file:///app/logseq/resources/app/js/lsplugin.core.js:2:88419`
									- Related:
										- ((629ccb26-1eab-4686-a7b8-f9433a871440))
										- [[Logseq]] : ((65be11bf-dfe3-4e75-abc3-3d16c5fb09cc))
								- Issue
									- ((65e1c7b3-f356-41e1-a666-a401c27b6661))
								-
								- ![image.png](../assets/image_1712163049033_0.png)
								-
				- ## Workflow
					- ((649b131d-ea21-47a4-ae83-e7ac7c16afe8)) and start typing "Calibre" to get `Calibre - Add a Calibre book`
					- This will import a book and it's metadata as a new page using ((653cd597-bd56-4b8f-a889-aa801169a26f))
					- ((653cd59e-8634-47f6-aa9f-64ada1deef9c)) has two buttons:  `Open` and `Sync`
						- `Open` - opens the Calibre book viewer on the right side
						- `Sync` - fetches annotations and copies them into blocks in Logseq
				- To test
					- + [[calibre/Designing Data-Intensive Applications - Martin Kleppmann (2017)]]
					- ((644c0b2b-301e-461b-9682-d93aa3432d8f))
				- Related: ((62e283e1-ebea-4ab9-9763-aa6a1b7ea0ba))
			- [File Manager](https://github.com/haydenull/logseq-plugin-file-manager)
			  id:: 63642a17-4772-4429-97b4-64d83e7aa04a
			- [gpt3-openAI](https://github.com/briansunter/logseq-plugin-gpt3-openai)
			  collapsed:: true
				- developer tools
					- /cookie editor for my GAE project on Android Studio
					- open in developer tools
			- Journals calendar
			- [logseq-plugin-automatic-url-title](https://github.com/0x7b1/logseq-plugin-automatic-url-title)
			  collapsed:: true
				- I swapped to this from another plugin because it includes favicons
					- [webpage-title](https://github.com/paulkinlan/logseq-webpage-title)
					  id:: 63667db9-ce1e-4e68-a758-febc1c239cc3
			- Markdown Table Editor
			- [media-controls](https://github.com/stefanbuck/logseq-media-controls)
			- [Media Timestamp](https://github.com/sethyuan/logseq-plugin-media-ts)
			  id:: 636691bd-b11a-4c7a-81ba-b4df5d52ac54
			  collapsed:: true
				- Allows taking MP4s you've uploaded into Logseq and either
					- RMB the bullet > "Convert to media Render"
				- Documentation
					- Usage
						- Use `/` then `/Insert media` to enter in a URL or local filepath. It'll insert this template text:
						  ```logseq
						  {{renderer :media, }}
						  ```
						- To create a timestamp, create a child bullet then inside it use `/` then `/Media timestamp`
					- Compatibility
						- ```
						  const VideoExts = new Set(["mp4", "mov", "mpg", "mpeg", "webm", "ogv", "avi"]
						  
						  const AudioExts = new Set(["mp3", "m4a", "wav", "ogg"]) 
						  ```
					- #+BEGIN_TIP
					  It can pass through symlinks without issue.
					  #+END_TIP
				- Testing
					- MKV doesn't work
						- Solution
							- **Best:** ((6655e501-3e4b-4350-983a-0dce9ee99d02)) to convert it to m4v/mp4
							- WinFF to convert (uses FFMPEG)
						- Example
							- `/home/boss/Videos/2-Complete/Alex's War (2022) 1080p WEBRip x265 An0mal1/Alex's War (2022) 1080p WEBRip x265 An0mal1.mkv`
								- {{renderer :media, /home/boss/Videos/2-Complete/Alex's War (2022) 1080p WEBRip x265 An0mal1/Alex's War (2022) 1080p WEBRip x265 An0mal1.mkv}}
					- Online MP4s don't work
						- You probably used `/Embed video URL`, it wrongly inserts the video (it inserts it as an iframe instead of a video). Try use a markdown link like this: `![](https://sp.rmbl.ws/s8/2/D/d/L/2/DdL2k.Faa.mp4)`
					- Local files using either absolute or relative paths work
					  collapsed:: true
						- `/home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq/logseq-unenc/assets/why-guns-are-necessary_1661987816394_0.MP4`
						  collapsed:: true
							- `{{renderer :media, ../assets/why-guns-are-necessary_1661987816394_0.MP4}}`
								- {{renderer :media, ../assets/why-guns-are-necessary_1661987816394_0.MP4}}
							- `{{renderer :media, /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq/logseq-unenc/assets/why-guns-are-necessary_1661987816394_0.MP4}}`
								- {{renderer :media, /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq/logseq-unenc/assets/why-guns-are-necessary_1661987816394_0.MP4}}
						- `/home/boss/Videos/2-Complete/AnimePahe_5-toubun_no_Hanayome_Movie_-_01_1080p_NanDesuKa.mp4`
							- s
								- {{renderer :media, /home/boss/Videos/2-Complete/AnimePahe_5-toubun_no_Hanayome_Movie_-_01_1080p_NanDesuKa.mp4}}
				- Pro version: [GitHub - sethyuan/logseq-media-ts: Create timestamps for audio and video to facilitate your learning and meeting reviews.](https://github.com/sethyuan/logseq-media-ts)
				  id:: 653abadc-0346-448f-bcfe-21e1eb8e35b3
				-
			- [open-in-external-app](https://github.com/haydenull/logseq-plugin-open-in-external-app)
			  id:: 636683cc-d1bb-4261-99d8-895985464c11
			  collapsed:: true
				- [Asking how to use it with FreeTube](https://github.com/haydenull/logseq-plugin-open-in-external-app/issues/4)
				- [Example URIs](https://github.com/libredirect/libredirect/blob/master/src/assets/javascripts/services.js) ((649b1412-27c8-4758-bfc3-130574c4447a))
					- ```
					  lbry://
					  youtube://
					  ```
				- Configuration syntax
					- ```json
					  menus: Registered menus
					  
					      menuName: Menu name
					      pathRegExp: Get file path from block content regexp
					      extensionName: Open file extension name
					      apps:
					          title: App name
					          openSchema: Call app schema, {path} will be replaced by file path
					  ```
				- Configuration example
					- ```json
					  {
					    "menus": [
					      {
					        "menuName": "Excalidraw",
					        "pathRegExp": "\\[\\[([\\d\\D]+)]]",
					        "extensionName": "excalidraw",
					        "apps": [
					          {
					            "title": "vscode",
					            "openSchema": "vscode://file/{path}"
					          }
					        ]
					      }
					    ]
					  }
					  ```
			- [PDF Export](https://github.com/sawhney17/logseq-pdf-export)
			  id:: 63642a17-a7ce-409c-875d-10452bf64686
			- ((660e8211-7aa5-4e68-aa70-211628be9d00))
			- [Tabs](https://github.com/pengx17/logseq-plugin-tabs)
			  id:: 6320a718-2f53-4e61-85c6-5a2ec147b46e
			  collapsed:: true
				- Limitations
					- Subscribed to several issues
					-
			- [web-parser](https://github.com/sawhney17/logseq-web-parser)
			  id:: 63642a16-6245-4798-a153-fd746577a2f8
			  collapsed:: true
				- Related: ((63667835-41da-4d49-b3f1-7be0de84135e))
			- https://github.com/briansunter/logseq-get-youtube-captions
			- ## Plugins installed via developer mode
			  id:: 652d6d35-1af1-481b-b71c-a772db67fb10
			  collapsed:: true
				- How to
				  id:: 652d6d43-d095-481a-b3d2-c003b34ef506
					- Download the newest zip file from the Releases page.
					- Unzip the zip file into the folder where you want to store the plugin.
					  `~/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq/plugins`
					- Logseq settings > Advanced > toggle on the developer mode
					- Plugin screen -> Load unpacked plugin button -> click on the unzipped folder
					- [Logseq Plugin Setup Guide.md · GitHub](https://gist.github.com/xyhp915/bb9f67f5b430ac0da2629d586a3e4d69)
				- Installed
					- [GitHub - wns3645/logseq-plugin-automatic-url-title](https://github.com/wns3645/logseq-plugin-automatic-url-title)
					  Fixed, original version in Logseq marketplace doesn't work anymore and is unmaintained
		- Integrated into workflow
			-
		- Need to better integrate into my workflow
		  id:: 634e515f-8e33-4683-9d12-9a5bf3e46297
			- ((63642a17-7f8b-40ec-bdb9-e77481938e5a))
			- ((63642a17-4772-4429-97b4-64d83e7aa04a))
			- ((63642a17-a7ce-409c-875d-10452bf64686))
			- ((63642a17-9d88-4ac9-bff6-b4d9484f6258))
			- ((63642a16-6245-4798-a153-fd746577a2f8))
			- ((63667db9-ce1e-4e68-a758-febc1c239cc3))
			- ((636683cc-d1bb-4261-99d8-895985464c11))
			- *Vim-like*
			  id:: 634bcf60-7cb2-4efc-bc34-0c95ad9b2119
			  collapsed:: true
				- Native `config.edn`
				  collapsed:: true
					- Changes
						- ```edn
						   :shortcuts {
						   	:editor/new-block "enter"
						  	:editor/new-line "shift+enter"
						      :editor/left ["h" "left"]
						  	:editor/down ["j" "down"]
						      :editor/up ["k" "up"]
						  	:editor/right ["l" "right"]
						  	:editor/open-edit ["i" "enter"]
						  	:editor/backspace ["ctrl+d" "backspace"]
						  }
						  ```
				- Best
					- [vipzhicheng/logseq-plugin-vim-shortcuts](https://github.com/vipzhicheng/logseq-plugin-vim-shortcuts)
					  id:: 634bc0dc-29b0-4264-889d-0d455029e8d2
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Cons
								- Lacks
									- [`Esc` = Exit Visual mode](https://github.com/vipzhicheng/logseq-plugin-vim-shortcuts/issues/13) - instead use ((664d1685-5e00-4dfa-a25f-cf954bb0df0d))
									- [Word navigation](https://github.com/vipzhicheng/logseq-plugin-vim-shortcuts/issues/14) e.g. `w`, `e`, `b`. Not possible yet as Logseq lacks cursor support
						- Keybindings
							- Priority to learn
								- ((660e8211-3c51-4e8c-b7e0-a7514f74ab7d))
								- ((660e8211-9ae6-45a9-a731-39f9c6c6bbf0))
								- ((660e8211-87bc-4ee2-bd42-91b9a2bf969f))
							- Customisations
								- Disable Logseq's default ((660e8211-4059-4b67-86b4-c280ef9d223f)) in order to use ((664d1685-5e00-4dfa-a25f-cf954bb0df0d))
								- Disable Logseq's default `gg`
								- `gg` / ((660e8211-9ec5-44f6-af38-54c80469fef9))
							- ## Default supported shortcuts
							  collapsed:: true
								- `j` : Move to next line. In visual block mode, it is for selecting down.
								- `k` : Move to previous line. In visual block mode, it is for selecting up.
								- `h` : Outdent.
								- `l` : Indent.
								- `J` : Move to next sibling. In visual block mode, it is for moving down.
								- `K` : Move to previous sibling. In visual block mode, it is for moving up.
								- `H` : Highlight focus out to parent level.
								- `L` : Highlight focus into child level.
								- `a`  and  `A` : Move the cursor to the end and enter edit mode.
								- `i`  and  `I` : Move the cursor to the beginning and enter edit mode.
								- `yy` : Copy current block content. Only supports one block – for copying multiple blocks, please use  `cmd+c` .
								- `Y` : Copy current block ref.
								- `p` : Paste clipboard content to next sibling. Only supports one block – for pasting multiple blocks, please use  `cmd+v` .
								- `P` : Paste clipboard content to previous sibling. Only supports one block – for pasting multiple blocks, please use  `cmd+v` .
								- `o` : Insert an empty block to next sibling.
								- `O` : Insert an empty block to previous sibling.
								- `dd` : Delete current block. Child blocks will also be deleted, but only current block content in the clipboard.
								- `T` : Scroll to top, because Logseq uses  `gg`  to go to graph view.
								  id:: 660e8211-9ec5-44f6-af38-54c80469fef9
								- `G` : Scroll to bottom.
								- `u` : Undo.
								- `ctrl+r` : Redo.
								- `gu` : Change block content to lower case.
								- `gU` : Change block content to upper case.
								- `mod+shift+u` : Toggle block content between lower and upper case.
								- `NUMBER` + `mod+shift+u` : Trigger different case style, supports 1–16.
								- `zo` : Extend block.
								- `zc` : Collapse block.
								- `zO` : Extend block hierarchically.
								- `zC` : Collapse block hierarchically.
								- `NUMBER` + `m` : Save current page or block as a mark to  `NUMBER`  register.
								- `NUMBER` + `'` : Load saved mark on main region.
								- `NUMBER` + `mod+'` : Load saved mark on right sidebar.
								- `cmd+j cmd+j` : Exit editing mode.  `ctrl+[`  does the same thing.
								  id:: 660e8211-3c51-4e8c-b7e0-a7514f74ab7d
									- Note: Disable Logseq's default ((660e8211-4059-4b67-86b4-c280ef9d223f))
								- `mod+alt+j` : Join next sibling block.
								- `mod+shift+enter` : Jumping into internal page or tag.
								- `mod+shift+;`  and  `mod+alt+;` : Trigger command mode. This provides many handy commands to use, explained below.
								  id:: 660e8211-9ae6-45a9-a731-39f9c6c6bbf0
								- `ctrl+a` : Increase the first found number in block. Supports multiple selections and combo.
								- `ctrl+x` : Decrease the first found number in block. Supports multiple selections and combo.
								- `x` : Cut a leading character. Supports multiple selections.
								- `x` : Cut a leading word. Supports multiple selections.
								- `/` : Trigger search in page bar on the below. Supports smartcase.
								- `n` : Search next search match.
								- `N` : Search previous search match.
								- `sb` : Search block content in Baidu.
								- `se` : Search block content in Wikipedia.
								- `sg` : Search block content in Google.
								- `sh` : Search block content in Github.
								- `ss` : Search block content in Stackoverflow.
								- `sy` : Search block content in Youtube.
								- `ctrl+v` : Toggle visual block mode.
								  id:: 660e8211-87bc-4ee2-bd42-91b9a2bf969f
								- `mod+/` : Trigger emoji picker UI.
						- Modes
							- **Normal mode**
							  A block is focused/highlighted.
							- **Insert mode**
							  You can edit a block
							- **Visual block mode**
							  You can select more blocks up and down and move the selected blocks using j and k.
							- **Command mode**
							  collapsed:: true
							  In VIM this mode can be triggered by `:`, but here, the shortcut is `mod+shift+;`, also can be memorised as `mod+:`
								- After trigger, you can find an input area at the bottom, you can input some commands here like in VIM. For now it's about 10+ commands, but I believe that would be more.
								- NOTE: on Windows, the trigger is ctrl+alt+;
								- The bottom input features
									- Autosuggestion when you input.
									    Press Tab if only one command matched, the matched command will be autocompleted right away.
									    Press Up and Down to traverse command history, it's a 1000 limit history, I think it's enough to use.
									    Press Esc to close command mode and back to the main window. For now Logseq can not get focused automatically sometime. so you need to click the main window to continue.
									    Just in case bug stuck, there are Run button and Close at bottom right to help you trigger behaviors.
						- Related: [[Logseq]] : ((63209777-2774-4345-8a71-d508db2c73ab))
				- Mid
					- [GitHub - vipzhicheng/logseq-plugin-vim-editor: Logseq VIM editor](https://github.com/vipzhicheng/logseq-plugin-vim-editor)
					  Deprecated for newer plugin?
					- [vim-wyatt-logseq-plugin](https://github.com/j-wyatt-a/vim-wyatt-logseq-plugin)
					  collapsed:: true
						- [Supported keybindings](https://github.com/j-wyatt-a/vim-wyatt-logseq-plugin/blob/main/src/config.js)
							- `h` = Moves the cursor left
							- `j` = moves the cursor down
							- `k` = moves the cursor up
							- `l` = Moves the cursor right
							- `w` = forword
							- `b` = backword
							- `0` = beginning of block
							- `a` = editEndOfWord
							- `SHIFT + a` = editEndOfBlock
							- `CTRL + l`= redraw
							- `f` = move down half a page
							- `t` = move up half a page
							- `gg` = beginOfPage
							- `gf` = goParentBlock
							- `gh` = goBlockEndChild
							- `SHIFT + g` = endOfPage
							- `yy` = copy block
							- `dd` = delete block
							- `x` = delete word ?
							- `u` = undo
							- `CTRL + r` = redo
							- `p` = paste
							- `o` = new line
							- `/` = search
							- `TAB` = toggleExpand
							- `ALT + Enter` = newBlock
							- `q` = closeTab
							- `SHIFT + h` = zoom out
							- `SHIFT + l` = zoom in
							- `;` = char jump mode
				- [Vim-mode requested](https://discuss.logseq.com/t/vim-mode-powerful-shortcuts/275/37)
				- Related:
					- ((6318fc57-db8a-441f-af0e-c8392241a76b)) : ((634bf00a-932c-4a43-8a7c-c822f175ffed))
					  [[PC]]
			- [Markdown Table Editor](https://github.com/haydenull/logseq-plugin-markdown-table)
			- ((660e8211-7aa5-4e68-aa70-211628be9d00))
			- [Journals Calendar](https://github.com/xyhp915/logseq-journals-calendar)
			- [Fenced Code Plus](https://github.com/xyhp915/logseq-fenced-code-plus)
			  id:: 63503767-a6e1-4cd1-b790-913f39ac8a00
			  collapsed:: true
				- Note: alternatives like ((663a5794-5b1f-4361-b5ab-a37bcf6013d3))currently offload rendering to an external API
				- Related: ((6346ffda-fb5b-40a8-bafe-8ad823e738f4))
			- [npgrosser/logseq-diagrams-as-code](https://github.com/npgrosser/logseq-diagrams-as-code)
			  id:: 663a5794-5b1f-4361-b5ab-a37bcf6013d3
			  collapsed:: true
			  Lets you create diagrams from textual representation (aka 'Diagrams as Code')
				- [Mermaid](https://mermaid.js.org)
				- [PlantUML](https://plantuml.com)
					- [State Diagram](https://plantuml.com/state-diagram)
					- `useReducer --> Reducer Function` is not functional. Needs to be `useReducer --> ReducerFunction`
				- Related ((6794caaf-3de5-4bde-abf6-8595c7797e64))
			- Not yet on marketplace
				- [Areas](https://github.com/bsongOT/logseq-plugin-areas)
				  collapsed:: true
				  id:: 63715cdb-3cff-4992-b122-a437728aee02
					- [PR for marketplace wip](https://github.com/logseq/marketplace/pull/245)
					-
				- [Highlighters](https://github.com/DenaroCF/Highlighters-for-Logseq)
		- [get-youtube-captions](https://github.com/briansunter/logseq-get-youtube-captions)
		- # Plugins to look into
			- ## Quick Capture
			  id:: 67160958-5490-42db-9b17-63b92bf36354
				- [logseq-quicktodo](https://github.com/hkgnp/logseq-quicktodo-plugin)
				  id:: 660e8211-39e9-4b19-8f00-af56bff0c4c7
				  Can add to today's journal, tagged task or a default page
				- [GitHub - TankCool/logseq-quick-capture: Quick capture your ideas to journal or specify page.](https://github.com/tankcool/logseq-quick-capture)
				  id:: 660e8211-ba6e-4ec5-896a-930f26221af8
				  Can add to journal or a default page
				- [hkgnp/firefox-extension-logseq-quickcapture](https://github.com/hkgnp/firefox-extension-logseq-quickcapture)
				  id:: 65f6b8d9-9e1a-4448-840e-97d47238ad29
				- [Quick Add](https://github.com/vyleung/logseq-quick-add-plugin)
				  id:: 6320a764-cc17-427d-be42-49b731d5b593
				  sounds more like Vim functionality
				- Related: ((64243827-555b-49b0-98a5-fec08eba1ba4))
			- [GitHub - sethyuan/logseq-plugin-reminder: System notification for Scheduled and Deadline.](https://github.com/sethyuan/logseq-plugin-reminder)
			- [logseq-plugin-smartsearch/README.en.md at master · sethyuan/logseq-plugin-smartsearch · GitHub](https://github.com/sethyuan/logseq-plugin-smartsearch/blob/master/README.en.md)
			-
			- [GitHub - sethyuan/logseq-media-ts: Create timestamps for audio and video to facilitate your learning and meeting reviews.](https://github.com/sethyuan/logseq-media-ts)
			- [GitHub - ahonn/logseq-plugin-todo: A simple to-do list plugin for logseq](https://github.com/ahonn/logseq-plugin-todo)
			- [GitHub - vipzhicheng/logseq-plugin-move-block: A Logseq plugin help you copy or cut blocks to anywhere you want.](https://github.com/vipzhicheng/logseq-plugin-move-block)
				- move-block e.g. move it to today's journal
			- [GitHub - sawhney17/logseq-github-plugin: A plugin to fetch stuff from github like active issues etc...](https://github.com/sawhney17/logseq-github-plugin)
			- [GitHub - renatocaliari/logseq-plugin-highlights-extractor](https://github.com/renatocaliari/logseq-plugin-highlights-extractor)
			- [GitHub - vipzhicheng/logseq-plugin-vim-editor: Logseq VIM editor](https://github.com/vipzhicheng/logseq-plugin-vim-editor)
			- [citation-manager](https://github.com/sawhney17/logseq-citation-manager) - requires [[Zotero]] /Paperpile/etc
			  id:: 660e8211-0f7b-401e-bf69-5d8bd9ed1781
			  collapsed:: true
				- This plugin allows you to integrate *any* citation manager that supports sync with BibTex including Paperpile and Zotero.
				- It’s been tested with 6k+ references and is also 100% local!
				- This plugin, currently supports inserting references by either creating a literature note page and linking to it (with fully user customisable templates!) or inserting a literature note inline based on a use customizable template.
			- [GitHub - benjypng/logseq-recurrence-plugin](https://github.com/hkgnp/logseq-recurrence-plugin)
			- [GitHub - sawhney17/logseq-custom-workflow-plugin](https://github.com/sawhney17/logseq-custom-workflow-plugin)
			- [GitHub - QWxleA/logseq-interstitial-heading-plugin: Insert an interstitial heading in your daily note](https://github.com/QWxleA/logseq-interstitial-heading-plugin)
			- [GitHub - vipzhicheng/logseq-plugin-block-calendar: A block calendar for Logseq.](https://github.com/vipzhicheng/logseq-plugin-block-calendar)
				- Have you wanted to have a calendar on the right sidebar in
				- I am thrilled to announce Logseq Block Calendar was just released! Now you can render a calendar in blocks and put it wherever you want.
				- also showed coloured dots for complete or incomplete tasks
			- [GitHub - benjypng/logseq-chartrender-plugin](https://github.com/hkgnp/logseq-chartrender-plugin)
			- [GitHub - c6p/logseq-hypothesis: Logseq plugin for hypothes.is](https://github.com/c6p/logseq-hypothesis)
			- [GitHub - sawhney17/logseq-go-now](https://github.com/sawhney17/logseq-go-now)
			- swap-block
			  id:: 6363bd83-c096-40c2-b9a3-abce93f741fd
			- [GitHub - debanjandhar12/logseq-anki-sync: An logseq to anki syncing plugin with superpowers - image occlusion, card direction, incremental cards, and a lot more.](https://github.com/debanjandhar12/logseq-anki-sync)
			- [GitHub - readwiseio/logseq-readwise-official-plugin](https://github.com/readwiseio/logseq-readwise-official-plugin)
			- comment - useful when quoting a paragraph and wanting to separate out your own comment, rather than adding `>` to the original quote
			- agenda
			- logseq-dictionary
			- https://logseqweekly.com/plugins/
			- [**Block Navigation**](https://github.com/kerfufflev2/logseq-plugin-blocknav)
			  Looking to make your workflow more keyboard-driven? The Block Navigation plugin
			   makes creating and editing blocks anywhere on a page a breeze.
			- [**Interval Hints**](https://github.com/kerfufflev2/logseq-plugin-interval-hints)
			  If  you use the Scheduled and Deadline functionality of Logseq, you definitely will want to check out Interval Hints. It's a highly configurable plugin to add a countdown or interval to deadline and scheduled tasks.
			- `/draw` will activate native Excalidraw. tldraw is a premium feature
			- [GitHub - karlsander/logseq-plugin-db-table](https://github.com/karlsander/logseq-plugin-db-table) (WIP)
				- https://www.loom.com/share/63ffad9498a643d893f51dacf78c039d
			- [logseq config: ui tweaks, minimalist and colorful · GitHub](https://gist.github.com/knoopx/dea143840ba00ba566a914818aaf3d4b)
			  id:: 63664c26-018a-49d1-8ad5-3dfd672f3412
			- [Admonition Panels](https://github.com/nmartin84/logseq-qol-improvements)
				- admonitions-panels. also see markdown admonitions
		- # To develop
			- [DBML - Database Markup Language](https://dbml.dbdiagram.io/home)
			- [GitHub - yuzutech/kroki: Creates diagrams from textual descriptions!](https://github.com/yuzutech/kroki)
			  id:: 6794caaf-3de5-4bde-abf6-8595c7797e64
			-
	- **Other Custom Modifications**
	  collapsed:: true
		- [Edit and run javascript code inside Logseq itself](https://discuss.logseq.com/t/edit-and-run-javascript-code-inside-logseq-itself/20763)
		  id:: 65be11bf-b2b2-481d-877a-104ba2da7b58
		  collapsed:: true
		  Also Python and R
			- Meta
				- The theoretical background and discussion is [here 69](https://discuss.logseq.com/t/logseq-for-code-management/20743).
				- A specific implementation and its discussion is below.
				- It supports other languages as well. Please visit their threads for directions:
					- [python 75](https://discuss.logseq.com/t/edit-and-run-python-code-inside-logseq-itself/20829)
					- [r 12](https://discuss.logseq.com/t/edit-and-run-r-code-inside-logseq-itself/20878)
				- Limitations
					- Code block needs to be defined as `javascript`, not just `js`
					- Objects get printed as `[object Object]` since they don't normally fit on one line unless you do a workaround 
					  i.e. ((507dc5b1-e753-4ada-9eee-5acd64ec1f7d)) e.g. `return JSON.stringify(myObject);`
					- [[JavaScript]] unlike [[Python]] requires a `return` statement in the code-block at the top-level because of it's implementation
					  collapsed:: true
						- Author: "This code is not top-level. Before running, every code-block gets wrapped within an asynchronous function (thus needing return), to allow for smooth evaluation of multiple macros at the same time. This is by design."
						- [[JavaScript]]
							- Does work
								- ```javascript
								  function test1() {
								      return 'hello world';
								  };
								  
								  return test1();
								  ```
									- {{evalparent}}
								- ```javascript
								  return 'hello world';
								  ```
									- {{evalparent}}
							- Doesn't work
								- ```javascript
								  function test1() {
								      return 'hello world';
								  };
								  
								  test1();
								  ```
									- {{evalparent}}
				- Usecases
					- Testing all my code snippets in-app
					- ChatGPT
					- Simple accounting
			- Setup
				- 1) Define a few buttons in file `config.edn`, inside `macros{}`:
				  collapsed:: true
					- ```edn
					  :evalpage "<button class='kit eval' data-kit='evalpage'>► Evaluate code of open code-blocks</button>"
					  :evalparent "<button class='kit eval' data-kit='evalparent'>► Evaluate code of parent block</button>"
					  :runpage "<button class='kit run' data-kit='runpage' data-page-name='$1'>► Run code of page $1</button>"
					  :togglemsg "<button class='kit' data-kit='togglemsg'>► Toggle messages</button>"
					  ```
				- 2) Define a few css rules in file `custom.css`:
				  collapsed:: true
					- button.kit {
					    background: var(--ls-tertiary-background-color);
					    padding: 2px 4px 2px 4px;
					  }
					  button.out {
					    background: var(--ls-tertiary-background-color);
					    display: inline-table;
					    line-height: 12px;
					    margin: 0px 3px 0px 3px;
					    padding: 2px;
					  }
					  div.out button.out {
					      visibility: hidden;
					  }
					  div.out:hover button.out {
					      visibility: visible;
					  }
					  div.out {
					    font-size: 14px;
					  }
					  span.out {
					    display: inline-table;
					    font-size: 14px;
					    padding: 2px;
					    white-space: pre-wrap;
					  }
				- 3) Put the following code in file `custom.js` (create inside folder `logseq` if missing):
				  collapsed:: true
					- ```js
					  const AsyncFunction = async function(){}.constructor;
					  function Concept(_key){
					      return {_key, __proto__: Concept.prototype};
					  }
					  Concept.prototype.setChild = Concept.setChild = function setChild(name){
					      const child = Concept(name);
					      this[name] = child;
					      return child;
					  }
					  Concept.prototype.setStatic = function setStatic(func){
					      this[func.name] = func;
					      return this;
					  }
					  
					  const Language = logseq.Language = Concept.setChild("Language");
					  const Module = logseq.Module = Concept.setChild("Module");
					  
					  const Kits = Module.setChild("Kits")
					  .setStatic(function addClickEventToButton(handler, button){
					      button.addEventListener("click", function onClicked(e){
					          e.preventDefault();
					          e.stopPropagation();
					          handler(e);
					      });
					  })
					  .setStatic(function createElementOfClass(tag, className, ...children){
					      const elem = document.createElement(tag);
					      elem.classList.add(className);
					      elem.append(...children);
					      return elem;
					  })
					  .setStatic(function evalDiv(div){
					      const blockId = div && div.getAttribute("blockid");
					      const block = logseq.api.get_block(blockId);
					      const divRow = Kits.onParentEvalStarted(div);
					      Kits.runRoot(block).then(Kits.onParentEvalFinished.bind(null, divRow));
					  })
					  .setStatic(function getKitByName(name){
					      var handler = kits[name];
					      if (typeof handler === "function") return Promise.resolve(handler);
					  
					      return Kits.runPageByName(name).then( ()=>kits[name] );
					  })
					  .setStatic(function loadDependencies(dependencies){
					      const langs = Object.values(dependencies);
					      if (langs.length < 1) return;
					  
					      return Promise.all(langs.map( (lang)=>lang.load() ))
					          .then( ()=>(new Promise( (resolve)=>setTimeout(resolve, 1000) )) );
					  })
					  .setStatic(function onLoadFailed(module, er){
					      Msg.ofStatus("could not load " + module, "error");
					      throw(er);
					  })
					  .setStatic(function onObserverFinished(nofFound, missing){
					      if (nofFound) Msg.info("handled " + nofFound + " macro(s)");
					      if (missing.length > 1) Msg.warning(missing.join("\n"));
					  })
					  .setStatic(function onParentEvalFinished(divRow, res){
					      if (typeof res === "string" && res.slice(0, 10) === "data:image") {
					          const img = Kits.createElementOfClass("img", "out");
					          img.setAttribute("src", res);
					          res = img;
					      }
					  
					      divRow.lastChild.remove();
					      divRow.lastChild.after("=>", Kits.createElementOfClass("span", "out", res));
					  })
					  .setStatic(function onParentEvalStarted(container){
					      const btnRemove = Kits.createElementOfClass("button", "out", "X");
					      const divRow = Kits.createElementOfClass("div", "out", btnRemove, "...running...");
					  
					      const wrapper = container.getElementsByClassName("block-content-wrapper")[0];
					      wrapper.append(divRow);
					  
					      Kits.addClickEventToButton(Kits.onRemoveClicked.bind(null, wrapper), btnRemove);
					      return divRow;
					  })
					  .setStatic(function onRemoveClicked(wrapper, e){
					      if (!e.ctrlKey) return e.target.parentElement.remove();
					      if (!e.shiftKey) {
					          return Kits.removeElems(wrapper.querySelectorAll("div.out"));
					      }
					  
					      const divs = document.querySelectorAll("div.ls-block div[data-lang]");
					      Array.prototype.forEach.call(divs, (div)=>{
					          const container = div.closest("div.ls-block");
					          Kits.removeElems(container.querySelectorAll("div.out"));
					      });
					  })
					  .setStatic(function onRootRunFailed(er){
					      Msg.error("run failed");
					      throw(er);
					  })
					  .setStatic(function onRootRunFinished(nofCodeblocks, res){
					      Msg.success("ran " + nofCodeblocks + " codeblock(s)");
					      return res;
					  })
					  .setStatic(function removeElems(elems){
					      Array.prototype.forEach.call(elems, (elem)=>elem.remove() );
					  })
					  .setStatic(function runRoot(root){
					      var begin;
					      const dependencies = {};
					      var prom = new Promise( (resolve)=>begin=resolve )
					          .then(Kits.loadDependencies.bind(null, dependencies));
					  
					      var nofCodeblocks = 0;
					      const blocks = (root.children) ? [root] : logseq.api.get_page_blocks_tree(root.name);
					      blocks.forEach(Kits.traverseBlocksTree, (block)=>{
					          const content = block.content;
					          const codeStart = content.indexOf("```") + 3;
					          if (codeStart < 3) return;
					  
					          const langEnd = content.search(/\w\W/);
					          const strLang = content.slice(codeStart, langEnd + 1);
					          var lang = logseq.Language[strLang];
					          if (!lang) return;
					  
					          if (!lang.eval) dependencies[lang._key] = lang;
					          const lineEnd = content.indexOf("\n", codeStart);
					          const codeEnd = content.indexOf("```", lineEnd);
					          if (codeEnd < 0) return;
					  
					          nofCodeblocks += 1;
					          const code = content.slice(lineEnd, codeEnd);
					          prom = prom.then( ()=>lang.eval(code) );
					      });
					  
					      begin();
					      return prom
					          .then(Kits.onRootRunFinished.bind(null, nofCodeblocks))
					          .catch(Kits.onRootRunFailed);
					  })
					  .setStatic(function runPageByName(pageName){
					      var page = logseq.api.get_page(pageName);
					      if (page) return Kits.runRoot(page);
					  
					      Msg.warning("page not found");
					      return Promise.resolve();
					  })
					  .setStatic(function traverseBlocksTree(block){
					      if (Array.isArray(block)) return;
					  
					      this(block);
					      block.children.forEach(traverseBlocksTree, this);
					  });
					  
					  const Msg = Module.setChild("Msg")
					  .setStatic(function cond(status, msg){
					      if (Msg.state === "on") Msg.ofStatus(msg, status);
					  });
					  Msg.error = Msg.cond.bind(null, "error");
					  Msg.info = Msg.cond.bind(null, "info");
					  Msg.success = Msg.cond.bind(null, "success");
					  Msg.warning = Msg.cond.bind(null, "warning");
					  Msg.ofStatus = logseq.api.show_msg;
					  Msg.state = "off";
					  
					  const JS = Language.setChild("javascript")
					  .setStatic(function eval(code){
					      return AsyncFunction(code)();
					  });
					  
					  const Python = Language.setChild("python")
					  .setStatic(function load(uri){
					      Msg.ofStatus("Preparing python...", "info");
					      return import(uri || Python.pyodideUri)
					          .then(Python.onLoaderFetched)
					          .then(Python.onPyodideLoaded)
					          .catch(Python.onFail);
					  })
					  .setStatic(function onLoaderFetched(loader){
					      return loader.loadPyodide();
					  })
					  .setStatic(function onPyodideLoaded(Pyodide){
					      Python.Pyodide = Pyodide;
					      Python.eval = Pyodide.runPythonAsync.bind(Pyodide);
					      Msg.ofStatus("Python ready", "success");
					  });
					  Python.onFail = Kits.onLoadFailed.bind(null, "pyodide");
					  Python.pyodideUri = "https://cdn.jsdelivr.net/pyodide/v0.23.4/full/pyodide.mjs";
					  
					  const R = Language.setChild("r")
					  .setStatic(function load(uri){
					      Msg.ofStatus("Preparing R...", "info");
					      return import(uri || R.webrUri)
					          .then(R.onModuleFetched)
					          .then(R.onWebrLoaded)
					          .catch(R.onFail);
					  })
					  .setStatic(function onModuleFetched(module){
					      R.module = module;
					      const webR = new module.WebR();
					      return webR.init().then( ()=>webR );
					  })
					  .setStatic(function arrayFromRes(res){
					      if (res.toArray) return res.toArray().then(arrayFromRes);
					      if (!Array.isArray(res)) return Promise.resolve(res);
					      return Promise.all(res.map(arrayFromRes));
					  })
					  .setStatic(function onWebrLoaded(Webr){
					      R.Webr = Webr;
					      R.eval = function(code){
					          return Webr.evalR(code).then(R.arrayFromRes);
					      }
					      Msg.ofStatus("R ready", "success");
					  });
					  R.onFail = Kits.onLoadFailed.bind(null, "webr");
					  R.webrUri = "https://webr.r-wasm.org/latest/webr.mjs";
					  
					  const kits = logseq.kits = Concept.setChild("kits")
					  kits.evalpage = Kits.addClickEventToButton.bind(null, function onEvalPageClicked(e){
					      document.querySelectorAll("div.ls-block div[data-lang]").forEach( (div)=>{
					          Kits.evalDiv(div.closest("div.ls-block"));
					      });
					  });
					  kits.evalparent = Kits.addClickEventToButton.bind(null, function onEvalParentClicked(e){
					      const child = e.target.closest("div.ls-block");
					      Kits.evalDiv(child.parentElement.closest("div.ls-block"));
					  });
					  kits.runpage = Kits.addClickEventToButton.bind(null, function onRunPageClicked(e){
					      var pageName = e.target.dataset.pageName || "";
					      if (pageName === "current page") {
					          const page = logseq.api.get_current_page();
					          if (page) pageName = page.name;
					      }
					      Kits.runPageByName(pageName);
					  });
					  kits.togglemsg = Kits.addClickEventToButton.bind(null, function onToggleMsgClicked(e){
					      Msg.state = (Msg.state === "on") ? "off" : "on";
					      Msg.ofStatus("Messages " + Msg.state, "success");
					  });
					  
					  const kitelems = document.getElementsByClassName("kit");
					  const kitsObserver = new MutationObserver(function onMutated(){
					      var nofFound = 0;
					      const missing = ["Missing kit(s): "];
					  
					      const proms = Array.prototype.map.call(kitelems, (elem)=>{
					          const data = elem.dataset;
					          const status = data.kitStatus;
					          if (status === "handled") return;
					  
					          if (data.pageName === "$1") {
					              data.pageName = "current page";
					              elem.textContent = elem.textContent.replace("page $1", "current page");
					          }
					  
					          data.kitStatus = "handled";
					          const kitName = data.kit;
					          return Kits.getKitByName(kitName).then( (handler)=>{
					                  if (typeof handler !== "function") {
					                      missing.push(kitName);
					                      return;
					                  }
					  
					                  handler(elem);
					                  nofFound += 1;
					              });
					      });
					  
					      Promise.all(proms).then( ()=>{
					          Kits.onObserverFinished(nofFound, missing);
					      });
					  });
					  kitsObserver.observe(document.getElementById("app-container"), {
					      attributes: true,
					      subtree: true,
					      attributeFilter: ["class"]
					  });
					  Msg.ofStatus("kits ok", "success");
					  ```
				- 4) Last step
				  collapsed:: true
					- This sets a single `MutationObserver` for all your needs.
					  collapsed:: true
						- No need to edit this file again.
					- Restart Logseq and accept running `custom.js`.
					  collapsed:: true
						- Before continuing, ensure that you get a success message “kits ok”
			- Testing sandbox
			  collapsed:: true
				- Works
					- ```javascript
					  let test = 1
					  return test
					  ```
						- {{evalparent}}
					- Some functions seem to work
						- ```javascript
						  let test = 1
						  
						  function increment() {
						    test++
						  }
						  increment();
						  
						  return test
						  ```
							- {{evalparent}}
						- ((646349b1-7599-465f-978d-a5b10b88a004))
				- **Bug:** In JavaScript a return statement is required on the top-level otherwise it'll output as `undefined`.
					- Outputs `undefined`:
					  ```
					  function test1() {
					      return 'hello world'
					  };
					  
					  test1();
					  ```
					- Outputs `hello world`, but I don't think this is correct JS in any other environment:
					  ```
					  function test1() {
					    return 'hello world';
					  };
					  - return test1();
					  ```
				- Doesn't work
					- ```javascript
					  const myObject = { key1: 'value1', key2: 'value2', key3: 'value3' };
					  let test = 1
					  
					  // Using JSON.stringify with space parameter set to an empty string
					  // const jsonString = JSON.stringify(myObject, null, '');
					  
					  //(() => {
					  //    return ('This is an immediately invoked arrow function expression (IIFE).');
					  //})();
					  
					  function test1() {
					      return 'printed text';
					  };
					  
					  test1();
					  ```
						- {{evalparent}}
					- ```javascript
					  function test1() {
					      return 'hello world';
					  };
					  
					  return test1();
					  ```
						- {{evalparent}}
					- ```javascript
					  let text7 = 'hello';
					  
					  function test8() {
					      return text7 + ' world';
					  };
					  
					  test8();
					  ```
						- {{evalparent}}
				- Random `{{evalparent}}` tests:
				  id:: 65be0922-9ab5-4b5e-a7e2-a9a87bd68ad7
					- id:: 65be0c77-57cb-4feb-9454-2a3fc5c6351d
					  ```javascript
					  let numWordPairs = {'hello': 3};
					  let property = 3;
					  let word = 'hello'
					  
					  // return numWordPairs
					  // doesn't work for Logseq as it returns [object Object]
					  // instead:
					  return JSON.stringify(numWordPairs)
					  ```
						- {{evalparent}}
					- `return` can't be nested in a function
						- Doesn't work
							- ```javascript
							  function test1() {
							      return 'printed text';
							  };
							  
							  test1();
							  ```
								- {{evalparent}}
						- Works
							- ```javascript
							  function test1() {
							    let text = 'printed text';
							  };
							  
							  test1();
							  ```
				-
			- How to use
				- Either:
					- Execute one block at a time
						- Add a child block to a block with code. `/code block` should have `python`, `javascript` or `r` as the code block type
						- `{{evalparent}}`
						- The results:
							- are not saved anywhere
							- are lost when moving away
							- can be selected and copied
							- can be removed by:
								- `click` on the X-button (appears on hover) for a single one.
								- `Ctrl + click` for all the results of a code-block.
								- `Ctrl + Shift + click` for every result everywhere.
					- Execute one page at a time
						- Type `{{runpage}}` to get a button for running all code in the current page (of the main pane).
							- from top to bottom:
								- ignoring any content outside code-blocks of supported languages
								- auto-`await`ing each code-block before moving to the next one
							- Some other page can be specified by its name, e.g. `{{runpage mypage}}`
						- Type `{{evalpage}}` to get a button for running all visible code-blocks in parallel and showing their results.
				- Type `{{togglemsg}}` to get a button for toggling helpful (but tiring) messages.
				- Have your code run when needed from anywhere in Logseq:
					- Inside your code, register the entry function of each module with `logseq.kits.mypage = ` the function.
						- `mypage` should be the actual name of the module’s page
					- Define your own macros (like the predefined above) by adding to their attributes:
						- `class='kit'`
						- `data-kit='mypage'`
					- The system will:
						- run once the page’s code, if needed
						- call the entry function once for each macro, passing it the macro’s element
							- The macro can provide arguments to the element, read from your code with `.dataset` or `.getAttribute`
		- ## Not integrated / tested
			- https://discuss.logseq.com/t/a-no-plugin-notification-system/24850 powered by ntfy and cron
			- https://discuss.logseq.com/t/turn-your-pages-into-interactive-applications-javascript-mini-apps-input-output-no-persistent-state/6064/11
			- https://discuss.logseq.com/t/make-custom-macros-that-replace-themselves-with-their-value-on-first-run/20967
			- https://discuss.logseq.com/t/code-buttons-simple-way-to-execute-javascript-inside-markdown-codeblock/21035
			- https://discuss.logseq.com/t/my-logseq-workflow/2278
			- https://discuss.logseq.com/t/queries-for-task-management/14937
	- Admonitions
	  collapsed:: true
		- Create by typing `<`
		- Existing types:
			- Quote
				- #+BEGIN_QUOTE
				  quote
				  text
				  #+END_QUOTE
				- ```logseq
				  #+BEGIN_QUOTE
				  quote
				  text
				  #+END_QUOTE
				  ```
			- Latex
			  id:: 63664cf4-bae5-4dc5-98ec-2705f29717b3
				- #+BEGIN_EXPORT latex
				  test
				  #+END_EXPORT
				- ```
				  #+BEGIN_EXPORT latex
				  test
				  #+END_EXPORT
				  ```
			- Note
				- #+BEGIN_NOTE
				  test
				  note
				  #+END_NOTE
				- ```logseq
				  #+BEGIN_NOTE
				  test
				  note
				  #+END_NOTE
				  ```
			- Tip
				- #+BEGIN_TIP
				  test
				  tip
				  #+END_TIP
				- ```logseq
				  #+BEGIN_TIP
				  test
				  tip
				  #+END_TIP
				  ```
			- Important
				- #+BEGIN_IMPORTANT
				  test
				  important
				  #+END_IMPORTANT
				- ```logseq
				  #+BEGIN_IMPORTANT
				  test
				  important
				  #+END_IMPORTANT
				  ```
			- Caution
				- #+BEGIN_CAUTION
				  test
				  caution
				  #+END_CAUTION
				- ```logseq
				  #+BEGIN_CAUTION
				  test
				  caution
				  #+END_CAUTION
				  ```
			- Pinned
				- #+BEGIN_PINNED
				  test
				  pinned
				  #+END_PINNED
				- ```logseq
				  #+BEGIN_PINNED
				  test
				  pinned
				  #+END_PINNED
				  ```
			- Warning
				- #+BEGIN_WARNING
				  test
				  warning
				  #+END_WARNING
				- ```logseq
				  #+BEGIN_WARNING
				  test
				  warning
				  #+END_WARNING
				  ```
			- Example
				- #+BEGIN_EXAMPLE
				  test
				  example
				  #+END_EXAMPLE
				- ```logseq
				  #+BEGIN_EXAMPLE
				  test
				  example
				  #+END_EXAMPLE
				  ```
			- Verse
				- #+BEGIN_VERSE
				  test
				  verse
				  #+END_VERSE
				- ```verse
				  #+BEGIN_VERSE
				  test
				  verse
				  #+END_VERSE
				  ```
			- Ascii
				- #+BEGIN_EXPORT ascii
				  test ascii
				  #+END_EXPORT
				- ```logseq
				  #+BEGIN_EXPORT ascii
				  test ascii
				  #+END_EXPORT
				  ```
			- Center
				- #+BEGIN_CENTER
				  test 
				  center
				  #+END_CENTER
				- ```logseq
				  #+BEGIN_CENTER
				  test 
				  center
				  #+END_CENTER
				  ```
			- Comment
				- #+BEGIN_COMMENT
				  test
				  comment
				  #+END_COMMENT
				- ```logseq
				  #+BEGIN_COMMENT
				  test
				  comment
				  #+END_COMMENT
				  ```
	- Tables
	  collapsed:: true
		- [Documentation](https://docs.logseq.com/#/page/tables)
			- [feat: Add version 2 of tables by bendyorke · Pull Request #8532 · logseq/logseq · GitHub](https://github.com/logseq/logseq/pull/8532)
		- Example
			- #### Usage Summary
			  |FIELD1|hex    |Dark ambiance                                  |Bright ambiance                               |FIELD5|R  |G  |B  |
			  |--|--|--|--|--|--|--|--|
			  |0     |`#2e3440`|background                                     |plain text, caret, brackets                   |N     |46 |52 |64 |
			  |1     |`#3b4252`|gutters, popups                                |                                              |i     |59 |66 |82 |
			  |2     |`#434c5e`|current line, selection                        |                                              |t     |67 |76 |94 |
			  |3     |`#4c566a`|line numbers                                   |                                              |e     |76 |86 |106|
			  |4     |`#d8dee9`|caret, variables, constants, attributes, fields|gutter, popups                                |S     |216|222|233|
			  |5     |`#e5e9f0`|                                               |current line, selection                       |n     |229|233|240|
			  |6     |`#eceff4`|plain text, brackets                           |background                                    |w     |236|239|244|
			  |7     |`#8fbcbb`|classes, types, primitives                     |classes, types, primitives                    |F     |143|188|187|
			  |8     |`#88c0d0`|declarations, calls                            |declarations, calls                           |r     |136|192|208|
			  |9     |`#81a1c1`|syntax, keywords, operators, tags, punctuation |syntax, keywords, operators, tags, punctuation|s     |129|161|193|
			  |10    |`#5e81ac`|pragmas, comment keywords, pre-processor       |pragmas, comment keywords, pre-processor      |t     |94 |129|172|
			  |11    |`#bf616a`|errors                                         |errors                                        |A     |191|97 |106|
			  |12    |`#d08770`|danger, annotations, décor                     |danger, annotations, décor                    |u     |208|135|112|
			  |13    |`#ebcb8b`|warn, escape, regex                            |warn, escape, regex                           |r     |235|203|139|
			  |14    |`#a3be8c`|strings                                        |strings                                       |o     |163|190|140|
			  |15    |`#b48ead`|numbers                                        |numbers                                       |r     |180|142|173|
			  |16 |`#616e88`|comments                                       |comments                                      |a     |97 |110|136|
			  logseq.table.version:: 2
			  logseq.table.hover:: cell
			  logseq.table.compact:: true
			  logseq.table.headers:: none
			  logseq.table.borders:: true
			  logseq.table.stripes:: true
			  logseq.table.max-width:: 30
			  logseq.color:: grass
	- ((65be11bf-dfe3-4e75-abc3-3d16c5fb09cc))
	- Browser extension
	  collapsed:: true
		- Lacks
			- [Notefox](https://addons.mozilla.org/en-GB/firefox/addon/websites-notes) -like functionality
- Troubleshooting
  collapsed:: true
	- Copy block references breaking, and being unable to intralink to specific blocks
		- 23/09/22 - Upon examining the blocks in Visual Studio Code, noticed the indentation of `collapsed:: true` below them was off by two spaces. Realigned them (they're supposed to be two spaces to the right of `-` and then Copy Block Ref made the `id::` property properly)
	- Formatting is messed up, necessitating a partial or whole revert
		- [[2024-05-07 Tuesday]] Git revert and git reset's weren't much help. What worked in the end was seeing the start of the changed block in GitKraken for that commit, then editing the file directly in visual studio code and fixing the code block which caused messed up formatting
		- 1
			- 1) Use Logseq's page history to see if a revert can be made through there
			- 2) If not, then use Vorta to mount an older backup
				- 2a) First make a backup of the existing graph to Desktop
				- 2b) Use Kompare to diff the old backup and existing graph
				- 2c) Open the files in Kate, and find where the start and finish points are in Kompare
				- 2d) Left-click at the start of one selection, find/scroll down, then SHIFT+LMB the end of the section to select the entire area
				- 2e) Copy and paste it over into the existing graph
	- Clear cache
		- Settings > Advanced > Clear cache
- Contributing code
  id:: 65be11bf-dfe3-4e75-abc3-3d16c5fb09cc
  collapsed:: true
	- SOP
		- ((63dc1965-e60c-418a-b045-991a2def0768)) : ((660d7476-50d4-4ec0-ad40-0d0cbc7dcfb9)) (if extending someone else's plugin and looking to upstream the code)
		- Relevant file locations
			- `/home/boss/.logseq/plugins/`
			  Plugin folders
			- `/home/boss/Documents/Git/1MY_REPOS/`
			  My repos
		- ((6655da8b-ada1-41c0-922c-9d751ba4760a))
			- `/home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq/ls-dev/Logseq-linux-x64-0.10.9.AppImage`
			- Basically a sandboxed AppImage
	- [logseq/CODEBASE_OVERVIEW.md at master · logseq/logseq · GitHub](https://github.com/logseq/logseq/blob/master/CODEBASE_OVERVIEW.md)
	  collapsed:: true
		- Clojure/ClojureScript
			- Nowadays compile-to-js are common practice. With the advent of web assembly, you can use almost any language to write browser apps. The Logseq app mostly uses Clojure.
			  
			  Simply put, Clojure is a dynamic typing functional programming language, with Lisp's syntax, running on the JVM. ClojureScript is just Clojure compiling to JavaScript.
			  
			  Clojure is easy to learn, you can pick it up pretty quickly following the [official guide](https://clojure.org/guides/learn/syntax).
			  
			  Logseq chose ClojureScript not only because of all the [benefits](https://clojure.org/about/rationale) of the language itself but also because of its awesome ecosystem, such as the [DataScript](https://github.com/tonsky/datascript) library. More on that later.
		- React & Rum
			- [React](https://reactjs.org/) is a library for building data-driven UI declaratively. Comparing to the imperative ways (such as DOM manipulation or using jQuery), it's simpler and easier to code correctly.
			- [Rum](https://github.com/tonsky/rum) is a React wrapper in ClojureScript. More than just providing the familiar React APIs, Rum adds many Clojure flavors to React, especially on the state management part. As a result, if you have experience with React, read Rum's [README](https://github.com/tonsky/rum) before diving into the code.
		- DataScript
			- [DataScript](https://github.com/tonsky/datascript) is an in-memory database that implements the [Datalog](https://en.wikipedia.org/wiki/Datalog) logic programming language. Datalog is very different from and much more expressive than the more common SQL and NoSQL query languages. Many users have implemented interesting features on top of Logseq just by utilizing the rich query language. Get started with Datalog with this [tutorial](http://www.learndatalogtoday.org/)
	- Codebase tips and info
		- TypeScript files here `logseq/libs/src/LSPlugin.core.ts` is stored as [[JavaScript]] here `logseq/resources/js/lsplugin.core.js`
	- ## Plugins
		- Documentation
			- Tips
				- [Plugins are installed globally (for every graph)](https://discuss.logseq.com/t/different-plugins-for-each-graph/5846) though there's a FR to make it per-graph
				- ((660e7dce-4a27-4ae4-ad0f-098e909f1bc1)) is in `logseq-coding` - can Reload plugin and see it activate. It'll use the latest code (can edit the "hello world" text)
		- Extension ideas
			- If a link to a GitHub issue exists, show an icon for whether the issue is completed, closed, etc
			- Consider changing autopairing so that `<` also pairs
			  `def autopair-map`
		- [Logseq Plugin API docs](https://plugins-doc.logseq.com/)
		- [An Intro to Making Logseq Plugins ft. Sawhney - YouTube](https://youtu.be/57h7te3NvJg)
		  collapsed:: true
			- {{video https://youtu.be/57h7te3NvJg}}
				- {{youtube-timestamp 1490}} Last watched
				-
		- Templates
			- [GitHub - sawhney17/logseq-plugin-starter-template: A quick and easy to use template to get you going from the get go](https://github.com/sawhney17/logseq-plugin-starter-template)
			  collapsed:: true
				- Steps
					- `yarn` to install all modules
					- `yarn build` to create a `dist` folder
					- In Logseq
						- Settings > Advanced > Developer mode
						- Plugins > click "Load Unpacked Plugin"
				- Template code explanation
					- ```javascript
					  ```
					- ```javascript
					  logseq.ready(main).catch(console.error)
					  ```
						- Essential line at bottom of code, check if the code was properly loaded
					- ```javascript
					  const main = async () => {
					    console.log('plugin loaded');
					    logseq.Editor.registerSlashCommand('insertBlocks', async (e) => {
					      insertSomeBlocks(e)
					    })
					  }
					  ```
						- Load the plugin
			- [GitHub - pengx17/logseq-plugin-template-react: Logseq plugin boilerplate for React. Powered by Vite ✨](https://github.com/pengx17/logseq-plugin-template-react)
			- https://github.com/logseq/logseq-plugin-samples
		- Tutorials
			- [Plugins 01](https://docs.logseq.com/#/page/plugins%2001) (Hello World)
			  id:: 660e7dce-4a27-4ae4-ad0f-098e909f1bc1
			  collapsed:: true
			  `/home/boss/Documents/Git/1MY_REPOS/snippets/JavaScript/logseq-plugin-hello-world/package.json`
				- This guide will walk you through creating a simple Hello World plugin for Logseq.
				- ## Preparations
					- Right now plugin development needs the Logseq desktop app, get the latest one here: https://github.com/logseq/logseq/releases.
					- Click the three-dots menu, go to `Settings` and turn on `Developer Mode`. After that, there will be a `plugins` button inside the menu. Click it to go to the plugin list page.
				- ## Project Bootstrap
					- Create a folder called `logseq-hello-world` and a `package.json` inside.
					- There are three required fields: `name`, `main`, and `logseq`. Leave `name` to `logseq-hello-world` and change `main` to `index.html`. The `logseq` is for plugin configuration. For now just set it to an empty object `{}`. It will look like this:
					- ```json
					  {
					    "name": "logseq-hello-world",
					    "version": "1.0.0",
					    "main": "index.html",
					    "logseq": {}
					  }
					  ```
					- Create an `index.html` as the entry point for our plugin. Usually you'd like to use some front-end build tool to bundle assets for you. For simplicity's reason we just use a single html file in this guide.
				- ## Build the Exciting Plugin!
					- Copy the code below to your index.html:
					- ```html
					  <!DOCTYPE html>
					  <html lang="en">
					    <head>
					      <meta charset="UTF-8" />
					      <meta http-equiv="X-UA-Compatible" content="IE=edge" />
					      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
					      <title>Logseq Hello World</title>
					      <script src="https://cdn.jsdelivr.net/npm/@logseq/libs/dist/lsplugin.user.min.js"></script>
					    </head>
					    <body>
					      <script>
					        // Write our code here!
					      </script>
					    </body>
					  </html>
					  ```
					- For a *real* project you'd better install the plugin sdk by running `npm install @logseq/libs`. For our purpose a script tag will do, which will load a global `logseq` object.
					- Replace the comment will the code below:
					- ```javascript
					  logseq.ready(() => {
					    logseq.App.showMsg("Hello World Logseq!");
					  }).catch(console.error);
					  ```
					- The code should be self-explanatory: It registers a callback function to show a message when the Logseq app is ready.
				- ## Run the Plugin
					- In the plugin list page, click `Load unpacked plugin` and choose the `logseq-hello-world` folder. A "Hello World Logseq!" message will show immediately and every time the app launches. Congratulations on writing your first Logseq plugin!
				- ## Next Steps
					- Learn from many plugin samples:
					  https://github.com/logseq/logseq-plugin-samples
					- Ask questions and discuss on Discord: https://discord.com/channels/725182569297215569/752845167030960141
					- The plugin architecture:
					  https://whimsical.com/logseq-plugins-draft-wip-B2iSbFBuWx1S4E4CkJed9y
					- Read the Plugin API documentation: https://plugins-doc.logseq.com/
			- [Plugins 02](https://docs.logseq.com/#/page/plugins%2002%20-%20build%20a%20mind%20map%20plugin)
			  collapsed:: true
				- In [[Plugins 01]] we demonstrated how to get started developing Logseq plugins. To recap, the simple steps are:
					- download the latest Logseq app
					- turn on developer mode
					- build a normal web app with JavaScript, HTML & CSS, plus the Logseq plugin sdks: @logseq/libs
					- install the app on the plugins page
				- In this guide, we will dive deeper by building a more *real-world* plugin - a mind map app that turns your Logseq page into a beautiful mind map graph.
				- The finished code is at https://github.com/logseq/logseq-plugin-samples/tree/master/logseq-mind-mapping. The simplify, in this guide we will only show the most essential part of the code.
				- ## Some Background
					- To build more sophisticated plugins for Logseq, it's better for us to understand a little bit how it works. Currently, each plugin runs in an iframe separate from the main Logseq app. The main app provides some APIs (such as operations on the block, getting app settings) through the SDK to the plugins. The iframe serves as the plugin's UI and can be shown or hidden through related APIs. What's more, the main Logseq app provides ways to *inject* UI elements such as icons or buttons to some specific positions in the main app.
					- That's all, let's get started!
				- ## Preparations
					- As we do in [[Plugins 01]], create a project folder contains a package.json, which contains three required fields: `name`, `main` and `logseq`.
					- In our `index.html` we need to add the scripts that we need:
					- ```html
					    <script src="https://cdn.jsdelivr.net/npm/@logseq/libs/dist/lsplugin.user.min.js"></script>
					    <script src="https://cdn.jsdelivr.net/npm/regenerator-runtime"></script>
					    <script src="https://cdn.jsdelivr.net/npm/mind-elixir/dist/mind-elixir.js"></script
					  ```
					- The `@logseq/libs` should be obvious. We will use async/await in our JavaScript, hence the regenerator-runtime is needed. Finally, we load the wonderful mind-elixir library to actually draw our mind map.
				- ## Build the Map
					- The first line should be familiar now:
					- ```js
					  logseq.ready(createModel(), main).catch(console.error)
					  ```
					- We register a function `main` to run when the main app is ready. But what's the `createModel` function? Let's see its content:
					- ```js
					  function createModel() {
					    return {
					      openMindMap() {
					        logseq.showMainUI();
					      },
					    };
					  }
					  ```
					- It just returns an object, which contains a method to open the plugin's UI (main UI). *Model* is an important concept in Logseq plugin development. We will later inject a button (or some other UI) into the main app as a template string. Because functions like event handlers can not be passed through string, we need a place for them. And that's what *model* is for. Besides creating them on ready, we can also add the model using the`logseq.provideModel` API.
					- Let's add to the `main` function:
					- ```js
					    logseq.App.onPageHeadActionsSlotted(({ slot }) => {
					      logseq.provideUI({
					        key: "hook-ui-page-file-mounted",
					        slot,
					        template: `
					            <a data-on-click="openMindMap" 
					               style="opacity: .5; position: relative; top: -3px; padding-right: 8px;"
					               title="Open Mind Mapping Canvas">
					              <i class="iconfont icon-mind-map" style="font-size: 17px;"></i>
					            </a>
					          `,
					      });
					    });
					  
					  ```
					- This code just adds a button in the page head to open our mind map. Notice the `openMindMap` will be called on our `model`.
					- Next, let's build up the UI:
					- ```js
					    const root = document.querySelector("#app");
					    const displayMap = document.createElement("div");
					    displayMap.classList.add("mind-display", "hidden");
					    root.append(displayMap);
					  ```
					- Because the plugin's UI runs in a separate iframe, we can do anything we want here, without affecting the main APP's UI. Because the map hasn't been built, we will hide it first.
					- Next, we'd like to get all the blocks from the current page. But here's a problem: we don't know if the page is visible or not! Luckily the `logseq.on(ui:visible:changed)` API call will let us register a callback when the visibility of the page has changed.
					- ```js
					   logseq.on("ui:visible:changed", async ({ visible }) => {
					      if (!visible) {
					        displayMap.classList.add("hidden");
					        displayMap.innerHTML = "";
					        return;
					      }
					  
					    // TODO: build the map! 
					  })
					  ```
					- If the page is hidden, we will hide the map too. If it's visible, we shall build the map:
					- ```js
					   const blocks = await logseq.Editor.getCurrentPageBlocksTree();
					   initMindMap(displayMap, blocks);
					  ```
					- `logseq.Editor` includes APIs to interact with the Logseq editor and `getCurrentPageBlocksTree` is a powerful one to get back all the blocks of the current page as a tree structure. The tree of blocks is a fundamental data structure of Logseq, with which you can do many powerful things in your plugin.
					- After we get back the blocks tree, we just walk the whole tree and use the elixir-mind APIs to build a connected mind map. The details are not relevant here and are therefore left out. Feel free to check the finished code. Also, load the plugin in your Logseq app and enjoy the beautiful mind map generating from your pages!
				- ## Conclusion
					- In this guide, we walk through building a simple but powerful mind map plugin for Logseq. While the plugin APIs are still work-in-progress, they can already do many powerful things. We invite you to hack them with your imagination. Feedbacks are super welcomed - we will improve the plugin APIs through listening to your voices!
	- Related: [[Browser debugging]] : ((660e7d59-c343-4c40-bc06-5bf8c83a2dca))
- Testing sandbox
  collapsed:: true
	- [ASMR FACE LICKING, LENS LICKING |ROLEPLAY - SUCCUB WILL TAKE YOUR SLEEP | 3DIO, MASSAGE | HALLOWEEN - YouTube](https://youtu.be/mwCREMbOxs0)
	-
- [Learning Resources]
	- [https://github.com/logseq/awesome-logseq](https://github.com/logseq/awesome-logseq)
	- [How to Write a Curated Newsletter with Logseq](https://www.youtube.com/watch?v=DouRLUPwHTU)