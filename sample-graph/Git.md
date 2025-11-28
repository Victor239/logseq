- [Git](https://git-scm.com/)
  id:: 6737677f-4c44-4792-810b-c0ce2ecbac07
	- Pros/Cons
	  collapsed:: true
		- Keep track of what changed, who made it, and when it happened
		- Easily roll back changes when necessary
		- With some systems (including Git), branching is cheap and easy, which makes it easier to develop features in parallel
		- Makes it easier to collaborate with other developer
	- Documentation
	  collapsed:: true
		- gitignore files
		  collapsed:: true
			- https://help.github.com/articles/ignoring-files/
			- .gitignore file
			  Keep these files out of the repo
			  /wp-content/themes/twenty*
			  /wp-content/upgrade
			  /wp-content/uploads
			  /sitemap.*
			  /wp-config.php
			  \*.sql
			  
			  Hidden files
			  *.DS_Store
			  *Thumbs.db
			  _.sass-cache_
			  _~imageoptim_
			  
			  source:: https://stevegrunwell.github.io/wordpress-git/#/10
				- Why keep out so much?
					- Config information will vary between environments
					- Generated content (user- or otherwise) has no place in a code repository
					- Remember: Version control !== backup
				- Reasons to keep uploads out of the repo
					- Uploads in the repo mean as soon as anything's uploaded your repo is out of date
					- Uploads + thumbnails = heavy repo w/ no benefit
		- [GitHub Desktop](https://desktop.github.com/)
		  id:: 6737677f-4ce3-4e3f-86a1-294fd4c6fe60
		  collapsed:: true
			- GitHub Flow overview
				- Visual diagram overview
				  collapsed:: true
				  http://i.imgur.com/OLs0D2s.png
					- [1] Create a branch
						- The top line represents the _master_ branch (i.e. production site files)
						- The bottom line represents the new development branch (production site files + any changes made)
					- [2] Add commits
						- Whenever you add, edit, or delete a file, you're making a commit, and adding them to your branch. This process of adding commits keeps track of your progress as you work on a feature branch.
						- Commits also create a transparent history of your work that others can follow to understand what you've done and why. Each commit has an associated commit message, which is a description explaining why a particular change was made. Furthermore, each commit is considered a separate unit of change. This lets you roll back changes if a bug is found, or if you decide to head in a different direction.
						- ProTip
							- Commit messages are important, especially since Git tracks your changes and then displays them as commits once they're pushed to the server. By writing clear commit messages, you can make it easier for other people to follow along and provide feedback.
					- [3] Open a Pull Request
						- Pull Requests initiate discussion about your commits. Because they're tightly integrated with the underlying Git repository, anyone can see exactly what changes would be merged if they accept your request.
						- You can open a Pull Request at any point during the development process: when you have little or no code but want to share some screenshots or general ideas, when you're stuck and need help or advice, or when you're ready for someone to review your work. By using GitHub's @mention system in your Pull Request message, you can ask for feedback from specific people or teams, whether they're down the hall or ten time zones away.
					- [4] Discuss and review your code
						- Once a Pull Request has been opened, the person or team reviewing your changes may have questions or comments. Perhaps the coding style doesn't match project guidelines, the change is missing unit tests, or maybe everything looks great and props are in order. Pull Requests are designed to encourage and capture this type of conversation.
						- You can also continue to push to your branch in light of discussion and feedback about your commits. If someone comments that you forgot to do something or if there is a bug in the code, you can fix it in your branch and push up the change. GitHub will show your new commits and any additional feedback you may receive in the unified Pull Request view.
						- ProTip
							- Pull Request comments are written in Markdown, so you can embed images and emoji, use pre-formatted text blocks, and other lightweight formatting.
					- [5] Deploy
						- Once your pull request has been reviewed and the branch passes your tests, you can deploy your changes to verify them in production. If your branch causes issues, you can roll it back by deploying the existing master into production.
					- [6] Merge
						- Now that your changes have been verified in production, it is time to merge your code into the master branch.
						- Once merged, Pull Requests preserve a record of the historical changes to your code. Because they're searchable, they let anyone go back in time to understand why and how a decision was made.
						- ProTip
							- By incorporating certain keywords into the text of your Pull Request, you can associate issues with code. When your Pull Request is merged, the related issues are also closed. For example, entering the phrase _Closes #32_ would close issue number 32 in the repository. For more information, check out our help article.
							  https://help.github.com/articles/closing-issues-via-commit-messages/
			- How to Use
				- First create a new branch
				  collapsed:: true
				  http://i.imgur.com/0RRKuLH.png
					- Branching explanation
						- Branching is a core concept in Git, and the entire GitHub Flow is based upon it. There's only one rule: anything in the master branch is always deployable.
						- Because of this, it's extremely important that your new branch is created off of master when working on a feature or a fix. Your branch name should be descriptive (e.g., refactor-authentication, user-content-cache-key, make-retina-avatars), so that others can see what is being worked on.
				- Add commits
				  collapsed:: true
					- Make sure to explain each commit with sufficient detail + link to other WorkFlowy bullets or resources if appropriate
					  http://i.imgur.com/ENYDAls.png
				- Pull request
				  collapsed:: true
					- Summarise the commits that will be added or the problem that will be solved
					  http://i.imgur.com/CHYXaKI.png
				- Steps
				  collapsed:: true
					- Make changes using normal Windows File Explorer (you can find the folder via GitHub Desktop)
					- Open GitHub Desktop and in the Changes page submit the commit with a summary and description
					  http://i.imgur.com/ENYDAls.png
						- Make sure to explain each commit with sufficient detail + link to other WorkFlowy bullets or resources if appropriate
		- Branches
		  collapsed:: true
			- https://www.atlassian.com/git/tutorials/using-branches
		- Commands
		  collapsed:: true
			- git-checkout - Switch branches or restore working tree files
			  https://git-scm.com/docs/git-checkout
			- git-clone - Clone a repository into a new directory
			  https://git-scm.com/docs/git-clone
			- To sum it up, clone is for fetching repositories you don't have, checkout is for switching between branches in a repository you already have.
			- New simpler commands
				- git switch and git restore
				  [https://news.ycombinator.com/item?id=27582036](https://news.ycombinator.com/item?id=27582036)
		- Commits are always local
		- [https://news.ycombinator.com/item?id=27579701](https://news.ycombinator.com/item?id=27579701)
	- _Git Hosts_
	  collapsed:: true
		- ((6360e399-3c61-4105-8c74-89f62bcd796a))
		- ((66cd757e-0e15-401d-ae8a-351f102c6280)) and forks
			- [Forgejo](https://forgejo.org)
			  collapsed:: true
			  Forked from ((63f33e71-c747-4d36-afa3-7696cc3ab521)) because a for-profit company took over it | Powers [Codeberg](https://codeberg.org)
				- [forgejo/forgejo: Beyond coding. We forge. - Codeberg.org](https://codeberg.org/forgejo/forgejo)
				- [Forgejo – Launching a Fork of Gitea | Hacker News](https://news.ycombinator.com/item?id=33749757)
				- [Open letter to Gitea | Hacker News](https://news.ycombinator.com/item?id=33372471)
			- [Gitea](http://gitea.io/)
			  id:: 63f33e71-c747-4d36-afa3-7696cc3ab521
			  collapsed:: true
			  Community fork of Gogs [as repo owner goes missing for long periods and is only person with write access](https://news.ycombinator.com/item?id=13296717)
				- https://github.com/go-gitea/gitea
			- Gogs
			  id:: 66cd757e-0e15-401d-ae8a-351f102c6280
			  collapsed:: true
				-
				- Easy deploy Gogs
				  collapsed:: true
					- Cloudron
					- Sandstorm
	- [GUIs](https://git-scm.com/downloads/guis)
	  id:: 6737677f-8947-4ddf-a8d5-5d2869f1e103
	  collapsed:: true
		- Look for a Git TUI with `git blame` support - would be cool to have a `bat`/`cat` alternative to view files
		- _Open source_
			- [Gittyup](https://murmele.github.io/Gittyup)
			  id:: 63543c79-92e1-445f-adf4-ceefeb133d44
			  collapsed:: true
				- https://github.com/Murmele/Gittyup
				- `flatpak install flathub com.github.Murmele.Gittyup`
				- Documentation
					- [Features](https://murmele.github.io/Gittyup/)
				- Continuation of GitAhead client
					- GitAhead
					  collapsed:: true
						- https://github.com/gitahead/gitahead
						- gitahead.com
						- Cons
							- Some missing features compared to GitKraken
								- Some very useful features are still missing:
									- compact view of git log
									- graphical tool to solve git rebase (or merge) conflicts
									- graphical tool to do an interactive git rebase
									- git squash
								- And lots of small graphical modifications could be done to reach the simplicity and the usability of Gitkraken interface for everyday actions like commit, stage, commit amend, stash, etc.
			- GitLens for ((63209272-1088-4824-a762-4ac7ded04b0a))
			  id:: 67376799-16e9-4317-84f0-a530c38e954d
			  collapsed:: true
				- https://gitlens.amod.io/
				- https://github.com/eamodio/vscode-gitlens
				- https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens
				- Reviews
					- https://dev.to/glsolaria/gitlens-where-have-you-been-all-my-life-1c2d
				- [5 Advanced Tips for How to Use GitLens in VS Code](https://www.gitkraken.com/blog/gitlens-advanced-tips)
			- [edamagit](https://github.com/kahole/edamagit) for VSCode
			- [Gitnuro](https://gitnuro.com/)
			  collapsed:: true
				- https://flathub.org/apps/com.jetpackduba.Gitnuro
				- https://github.com/JetpackDuba/Gitnuro
			- [Kommit](https://apps.kde.org/en-gb/kommit/)
			- [Stage](https://github.com/aganzha/stage)
			  collapsed:: true
			  GUI inspired by Magit
				- https://flathub.org/apps/io.github.aganzha.Stage
				-
		- _Closed source_
			- GitKraken
			  collapsed:: true
			  id:: 629ccb26-df31-4528-a49e-3845c3860d35
				- https://www.gitkraken.com
				- Cons
					- Multiple users requires premium, unless you avoid it somehow
						- parallel snap instances doesn't work, they have access to the same app data
						  collapsed:: true
							- Enable parallel instances
							  sudo snap set system experimental.parallel-instances=true
							- sudo snap install gitkraken_2
				- Popular but doesn't support private repos as of mid-2019 unless you pay $30/year
				- _Documentation_
					- Official videos
					  https://youtu.be/ub9GfRziCtU
					- How to make a PR using GitKraken SOP
					  collapsed:: true
					  id:: 629ccb26-8784-4332-90fd-d3c457daa89d
						- **1) Setting up your local repo**
							- _GitHub_
								- Make a fork of the desired repo
							- _GitKraken_
								- Clone with URL to clone it locally
								- Click the + next to 'Remotes' and paste the URL for the upstream repo, and name it "upstream"
								  http://i.imgur.com/dvyhZka.png
								- Note: Never make changes to the default(master) branch of your fork. It should remain as a clean slate. For every PR you make, make a new branch
								- Create a new branch for your PR - right-click on master under the Local tab in the left panel
									- OR use ((63209272-1088-4824-a762-4ac7ded04b0a)) to make a new branch
								- Double-click to check out (switch between) the branch you're working on. It'll have a green checkmark beside the branch name
						- **2) Create your changes**
						  collapsed:: true
							- Ports from tg>Bee
								- Open GItHub PR - files changed
								- **Cherry-picking**
									- _Several remotes_
										- "upstream-fork" - my fork of Bee in own account
										- "upstream-origin" - origin of Bee
										- "tgstation-origin" - tgstation, where stuff is ported from
									- tgstation and beestation upstreams should both be remotes, but you're using the repo for a personal fork of bee. Also create a new branch in your fork
									- Check out your local branch
									- Find the 7-digit code for the PR
										- _Either_
											- On GitHub.com go to a PR and scroll down to the commit where it's actually merged. It'll have a 7-digit code and a purple Merged symbol next to it
											  http://i.imgur.com/xxk5IG4.png
											- In GitKraken it says it in the top-right of the selected commit
											  https://i.imgur.com/uQdilbP.png
									- In GitKraken click on the upstream repo, then CTRL+F and paste in the commit ID
									- In GitKraken
										- To make that nice looking UI GitKraken is a little bloated and suffers from having a lot of commits loaded at once. To help combat this they set a configurable cap on the number of commits loaded into that graph you see. You'll need to increase the number of commits to get changes that were brought in earlier in the timeline. To do that go to File --> Preferences --> General --> Max Commits in Graph, set that to 20000
									- Right Click on the highlighted commit and select Cherrypick commit, confirm by clicking Yes on the banner at the top. That will start the merging process. You may get some conflicts, at that point you'll need to resolve them.
									- **Conflict resolving**
										- Generally you'll want to merge the right-hand side (yellow) as that's the files from the PR you cherrypicked from
										- tgui.js
										  collapsed:: true
											- Pick either one, you'll have to rebuild it after anyway
												- Pick either one, doesn't matter. You'll have to rebuild tgui afterwards anyways
												- after you commit that
												- you'll need a fairly recent version of Node.js installed
												- then you'll go to the tgui folder
												- and run install_dependencies
												- then after that's done run build_assets
												- then compile the DM code and test the UI locally
												- you only ever have to install dependencies once in your life (per repo)
								- Old - error prone
									- Open ((63209272-1088-4824-a762-4ac7ded04b0a)) to the the BeeStation repo and copy&paste the lines from the GitHub window
								-
						- **3) Commit your changes**
							- In GitKraken click on "WIP"
							- Click on Stage Files
							- Commit Message section. Type a descriptive name for you commit, and a description if necessary. Be concise!
						- **In the command bar at the top, click Push to git push them to GitHub**
							- Leave the remote as origin (your online rather than local fork) and and press submit. The branch is already typed in for you.
						- **Make your pull request to the upstream-origin**
							- Right click your online new branch on the left panel or in the branch diagram. Click Start a pull request to upstream/ from origin/YourBranch.
							- PR pop-up
								- On the left, under From Repo and Branch, make sure you you've selected your fork, and your new branch, respectively. This is referring to the branch with the commits you just made.
								- On the right, under To Repo and Branch, make sure you've selected yogstation13/Yogstation-TG and master. This is referring to the master Yogstation repo.
								- Finally, click Edit on GitHub. This will open the GitHub website. You can put the information in GitKraken, but it's easier to do on the GitHub.
							- Template
							  collapsed:: true
								- For ports
								  https://github.com/tgstation/tgstation/pull/46101
								  
								  About The Pull Request
								  hulks no longer get slowdown from damage/stamina
								  
								  Why It's Good For The Game
								  crippling a hulk is too easy, you can just use stamina damage, hulk was meant to be taken lethally but now with baton changes to do stamina, combined with disablers doing stamina you can easily dab on one
								  
								  Changelog
								  cl THEIR-GITHUB-USERNAME
								  balance: hulks no longer slow from damage
								  /cl
								- About the changelog
									- Now you have to write your changelog. This is what players see when they click the changelog button on the server. It has a specific format you need to respect.
									- The correct format is already present in the PR description, you just need to edit it with the changes you made. You can also add a specific contributor name after the first :cl: for that to show up in the changelog. If you leave it blank, it will use your GitHub username.
									- Note: Only make a changelog for changes the players can experience. For example, if you just clean up code or make performance changes, you don't need to add them to the changelog.
									- You can also add icons to each line of changelog
									  http://i.imgur.com/9NTPucO.png
									- https://tgstation13.org/wiki/Guide_to_Changelogs
							- ALTERNATIVELY
								- On GitHub on the upstream webpage click "Compare & pull request"
						- **Testing**
							- Double-click the local branch the check it out
							- Open Dream Maker
							- Compile (CTRL+K)
						- here's how to do more PRs - on GitKraken check out master then click Pull, before making a new branch
						- _Troubleshooting_
							- To add more commits to the same PR, just push changes to your repo
							- merge conflicts
							  collapsed:: true
								- either merge both changes into one file, or simply pick one of the two files to use
								- What we're going to do is merge the Yogstation master branch, with the new updates, onto our branch. This counts as a commit, so any updated files on the Yogstation master branch will be added to your branch. When you make the commit, GitKraken will then ask you to resolve each conflict one by one.
								- In GitKraken click on the little arrow next to Pull, and click Fetch All.
								- Now, right click the master branch of the Yogstation remote. Select Merge remote/master into yourbranch. You will get a notice saying There are merge conflicts that need to be resolved. Click the new node at the top of the branch diagram.
								- Conflict Resolver
									- Either click the checkmark next to the title of the commit of either your branch or the upstream branch to select that one
									- OR
									- go into the diff below and select which changes to merge, line-by-line
										- Click the checkmarks next to what lines you want
								- Finally, click Save in the top right to resolve that conflict. Do the same for all other conflicting files.
								- Once every conflict is resolved, simply type a commit name and press Commit and Merge
						- [Learning Resources]
						  collapsed:: true
							- https://support.gitkraken.com/working-with-repositories/pushing-and-pulling/
						- {Archive}
						  collapsed:: true
							- https://forums.yogstation.net/index.php?threads/release-the-gitkraken-how-to-make-your-first-pull-request.15099/
							- Not very good
							  https://thooloo.tk/babbypr.html
							-
				- _Pricing and features_
					- Individual
						- Individual: In-app merge conflict output editor; work with private repos
					- Pro
						- Integrations with GitHub Enterprise, GitLab Enterprise etc
						- Multiple profiles for work & personal use
				- Snap package was changed to use classic confinement (not containered, allows full system access) since it has to run scripts and use system git
				  source:: https://forum.snapcraft.io/t/classic-confinement-request-for-gitkraken/14682
				  collapsed:: true
					- _Improved_
						- Full Git Hook support
						- Full SSH support
						- Full GPG support
						- Full LFS support
		- TUIs
			- [LazyGit](https://github.com/jesseduffield/lazygit)
			- [GitUI](https://github.com/gitui-org/gitui)
		- Subsets of Git functionality
			-
		- Git GUIs for `git diff`
		  collapsed:: true
			- [GitHub - dandavison/delta: A syntax-highlighting pager for git, diff, grep, and blame output](https://github.com/dandavison/delta) - for better `git diff`
			- https://github.com/ArthurSonzogni/git-tui
			- GitKraken
			- GitLens for VSCode
			- [Beyond Compare](https://www.scootersoftware.com/home)
			- https://www.sublimemerge.com/
			- https://meldmerge.org/
				- https://stackoverflow.com/questions/14821358/git-mergetool-with-meld-on-windows/48979939#48979939
				-
		- Linux support
			- _Proprietary_
				- GitKraken
			- _FOSS_
				- [Unofficial GitHub Desktop for Linux](https://github.com/shiftkey/desktop) (DEB, Snap, AppImage etc)
				  i.e. ((6737677f-4ce3-4e3f-86a1-294fd4c6fe60)) port
				- [https://github.com/francescmm/GitQlient](https://github.com/francescmm/GitQlient)
				- [https://github.com/soramimi/Guitar](https://github.com/soramimi/Guitar)
				- ungit
				  [https://news.ycombinator.com/item?id=27530050](https://news.ycombinator.com/item?id=27530050)
		- Windows-only
		  collapsed:: true
			- Official ((6737677f-4ce3-4e3f-86a1-294fd4c6fe60))
			  Basic but simple
			- SourceTree - most popular full client
				- [https://alternativeto.net/software/sourcetree](https://alternativeto.net/software/sourcetree)
		- Unsorted
		  collapsed:: true
			- Sublime Merge
			- Fork ([https://git-fork.com](https://git-fork.com))
	- Managing binary blobs
	  collapsed:: true
		- [https://opensource.com/life/16/8/how-manage-binary-blobs-git-part-7](https://opensource.com/life/16/8/how-manage-binary-blobs-git-part-7)
		- [https://git-lfs.github.com/](https://git-lfs.github.com/)
	- ((635fc546-d883-4e58-89d4-6c1069039fb6))
	- Advanced Usage
	  collapsed:: true
		- https://www.digitalocean.com/community/tutorials/how-to-use-git-hooks-to-automate-development-and-deployment-tasks
		- https://www.digitalocean.com/community/tutorials/how-to-install-and-update-wordpress-with-version-control-on-centos-7
		- https://www.digitalocean.com/community/tutorials/how-to-set-up-automatic-deployment-with-git-with-a-vps
		- https://www.digitalocean.com/community/tutorials/how-to-use-git-to-manage-your-user-configuration-files-on-a-linux-vps
		- https://www.digitalocean.com/community/tutorials/how-to-use-blue-green-deployments-to-release-software-safely#configure-git-remotes-on-the-local-development-machine
	- [`.gitignore`](https://git-scm.com/docs/gitignore)
	  collapsed:: true
		- `.gitignore`
		  collapsed:: true
			- Better to append a trailing `/` when matching directories so that it only matches directories with that name rather than files too
			- You can exclude something, then later include specific variants e.g. to include `.m2/build/`
				- ```
				  build/
				  !.m2/**
				  ```
			- It doesn't seem possible to ignore files within submodules from a top-level `.gitignore` in my experience, or I just don't know the syntax. Instead can be done from submodule `.gitignore`s
		- https://git-scm.com/docs/gitignore
		- If you've committed a directory then later added it to `.gitignore`, then to remove it you can use `git rm -r --cached some-directory` && `git commit -m 'Remove the now ignored directory some-directory'`
	- Related: ((64634998-e08f-4cc0-8ca6-a060b0c36c69))
- ## Commands sorted alphabetically
	- `git add`
	  id:: 6463498e-64f6-4f41-a5f5-8561abf19c0c
	  collapsed:: true
		- `git add -p` = patch view for making commits. Great at specifying specific lines to add or drop, similar to Source Control tab in VSCode
		- `git add` is relative to the current directory. This allows you to use `git add .` for example whilst in that directory on a terminal to stage just those files
		- https://www.gitkraken.com/learn/git/git-add
		- `git add .`
		  id:: 6334823d-53f4-4935-a37d-32515f871e50
			- = Stages all files in current directory. As opposed to `git add README.md` to just track that file
	- `git clone`
	  id:: 6463498e-17c1-445c-a64a-295ff35a738f
	  collapsed:: true
		-
	- `git branch`
	  collapsed:: true
		- •	Notes
			- `git branch -vv` = see the upstream branch for all your local branches
			- `git branch --set-upstream-to=origin/feature-1` = change the current branch to track that upstream branch
			- `git branch --set-upstream-to=origin/feature-1 feature-2` = change the local branch `feature-2` to track the upstream branch `feature-1`
		- https://www.atlassian.com/git/tutorials/using-branches
			- `git branch` / `git branch --list`
			  List all branches
			- `git branch <branch>`
			  collapsed:: true
			  Create a new branch called ＜branch＞. This does not check out the new branch.
				- Example
				  ```git
				  git checkout -b adding-to-readme
				  ```
			- ((22098c8d-e0b9-4d2c-8be7-71729bf6c7d8))
				- {{embed ((22098c8d-e0b9-4d2c-8be7-71729bf6c7d8))}}
			- `git branch -a`
			  id:: 6463498e-ed57-48fe-b6d2-bf47128e8aae
			  List all branches including remote
			- `git branch -D <branch>`
			  Delete branch
		- If you create a local branch e.g. `16-stub-cicd` then want to `git push` your changes, you'll need to first either:
			- `git push --set-upstream origin 16-stub-cicd`
			- `git config --global push.autoSetupRemote true`
				- Setting `git config --global push.autoSetupRemote true` will enable automatic upstream branch creation when you push a new branch to a remote repository. This means you can push a new branch without specifying --set-upstream every time, as Git will automatically set up the tracking relationship between the local and remote branches.
				- This configuration is particularly useful for workflows where local branches are expected to have the same name as their remote counterparts. It simplifies the process of pushing new branches and ensures that the tracking relationship is set up automatically.
				- If doing this then you'll need to use the exact same branch names locally that you want on a remote i.e. can't create shorthand branch names locally to push to longer branch names upstream
		- Related: ((637367b6-8f50-467a-bb35-78ccb33530b2))
	- [`git commit`](https://git-scm.com/docs/git-commit)
	  id:: 64973074-812e-4865-accd-f66ac694c60f
	  collapsed:: true
		- `git commit --amend` = modify the most recent commit
			- If you want to change the commit message without altering the files, you can use git commit --amend -m "New commit message"
		- Git amending previous commit messages
			- `git commit --amend` is a shortcut for `git rebase -i HEAD~1`, then changing `pick` to `edit` in the rebase editor, and then editing the git commit message
			- To change a commit message X commits ago e.g. 2, first do `git rebase -i HEAD~2`, then change the top line from `pick` to `edit`, then `git commit --amend` to open editor to modify the commit message
		- ## Documentation
			- Flags
				- `--fixup=[(amend|reword):]<commit> `
				  id:: 661f656b-3fb0-4da6-b709-b4d05fa6f63e
					- Create a new commit which "fixes up" `<commit>` when applied with `git rebase --autosquash`. Plain `--fixup=<commit>` creates a "fixup!" commit which changes the content of `<commit>` but leaves its log message untouched. `--fixup=amend:<commit>` is similar but creates an "amend!" commit which also replaces the log message of `<commit>` with the log message of the "amend!" commit. `--fixup=reword:<commit>` creates an "amend!" commit which replaces the log message of `<commit>` with its own log message but makes no changes to the content of `<commit>`.
					- The commit created by plain `--fixup=<commit>` has a subject composed of "fixup!" followed by the subject line from <commit>, and is recognized specially by `git rebase --autosquash`. The `-m` option may be used to supplement the log message of the created commit, but the additional commentary will be thrown away once the "fixup!" commit is squashed into `<commit>` by `git rebase --autosquash`.
					- The commit created by `--fixup=amend:<commit>` is similar but its subject is instead prefixed with "amend!". The log message of <commit> is copied into the log message of the "amend!" commit and opened in an editor so it can be refined. When `git rebase --autosquash` squashes the "amend!" commit into `<commit>`, the log message of `<commit>` is replaced by the refined log message from the "amend!" commit. It is an error for the "amend!" commit’s log message to be empty unless `--allow-empty-message` is specified.
					- `--fixup=reword:<commit>` is shorthand for `--fixup=amend:<commit> --only`. It creates an "amend!" commit with only a log message (ignoring any changes staged in the index). When squashed by `git rebase --autosquash`, it replaces the log message of `<commit>` without making any other changes.
					- Neither "fixup!" nor "amend!" commits change authorship of `<commit>` when applied by `git rebase --autosquash`. See [git-rebase\[1\]](https://git-scm.com/docs/git-rebase) for details.
			- Example
				- `git commit -am "commit message"`
				  id:: 65369e7a-8663-41cc-aae0-c42efac93f49
			- [Git Commit | Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/saving-changes/git-commit)
		- ## Tips
			- Git Commit messages
				- Title: Ideally put the prefix of the issue e.g. `#16` for every commit because that way after it's PR is merged then you can browse the commits list and that part of the commit title will be a hyperlink to the original issue with the same ID (if using GitLab)
				- Starting commit message subject lines with the GitLab issue ID (`#<id>`) can be done to allow GitLab to automatically link the commit to the corresponding issue
				- In order for Git not to mistake the leading `#` as a comment, add the following Git configuration setting:
					- `git config --global commit.cleanup scissors`
			- GPG key for signing commits
			  collapsed:: true
				- Main commands
					- `gpg --gen-key` = Generate a new GPG key
					  id:: 6463498e-24be-461c-ac0e-c9f2c813a797
					- `gpg --list-secret-keys --keyid-format LONG` = List existing keys
					  collapsed:: true
						- Last output: [[2024-04-03 Wednesday]]
							- ```
							  gpg: checking the trustdb
							  gpg: marginals needed: 3  completes needed: 1  trust model: pgp
							  gpg: depth: 0  valid:   2  signed:   0  trust: 0-, 0q, 0n, 0m, 0f, 2u
							  gpg: next trustdb check due at 2024-11-19
							  /home/boss/.gnupg/pubring.kbx
							  -----------------------------
							  sec   rsa3072/A27BC24FCCFB9B1E 2022-11-20 [SC] [expires: 2024-11-19]
							        2490C79CFF035C6D49458100A27BC24FCCFB9B1E
							  uid                 [ultimate] Aaron Sollesse <22418751+ajvsol@users.noreply.github.com>
							  ssb   rsa3072/E1A8A3158780E098 2022-11-20 [E] [expires: 2024-11-19]
							  
							  sec   rsa3072/276565C0FBB053E0 2024-04-03 [SC] [expires: 2026-04-03]
							        75B0DC4A357265189CFC3EBB276565C0FBB053E0
							  uid                 [ultimate] Victor <12621257+Victor239@users.noreply.github.com>
							  ssb   rsa3072/C7C315FCAC50E143 2024-04-03 [E] [expires: 2026-04-03]
							  ```
								- primary key (`sec`) and a subkey (`ssb`)
								- `sec` is key to use unless you're going for an advanced security configuration
								  id:: 660ddbe8-5ae0-4487-9eb9-0fef0f935347
						- Location: `/home/boss/.gnupg/pubring.kbx`
					- `gpg --armor --export A27BC24FCCFB9B1E > public_key_Aaron_Sollesse.asc` = Export GPG public key
					  collapsed:: true
						- e.g. `gpg --armor --export A27BC24FCCFB9B1E > gpg-key.txt`
					- [Add this key to GitHub](https://github.com/settings/keys)
					- ((63209272-1088-4824-a762-4ac7ded04b0a)) - Settings > User > Extensions > `Git: Enable Commit Signing`
				-
				- Tell local git client to auto-sign future commits
					- `which gpg` = Print location of gpg binary
						- e.g. `usr/local/bin/gpg`
					- `git config --global gpg.program "/location/of/gpg"` = Specify gpg program
						- e.g.
							- `git config --global gpg.program "$(which gpg)"`
							- `git config --global gpg.program "/usr/bin/gpg"`
					- `git config --list --global` = List all `git config` settings for `global`
					- `git config --global user.signingkey <PASTE_LONG_KEY_HERE>`
					- `git config --global commit.gpgsign true`
						- Actually that interferes with Logseq autocommits also
						- Alternatively either
							- non-global
							- ((637b3bed-e87a-457a-ac16-860771bfc293)) for specific commits
					- Troubleshooting
						-
				- How to sign a specific commit
					- `git commit -S -m 'test1'`
					  id:: 637b3bed-e87a-457a-ac16-860771bfc293
						- Note: `-s` is a different flag
				- Troubleshooting
				  id:: 660e92b1-c41b-4b0e-a9ff-90d81b994008
					- id:: 660e929e-982b-4b5e-bc9e-14a9ff01e60a
					  ```bash
					  > git -c user.useConfigOnly=true commit --quiet --allow-empty-message --file - -S
					  error: gpg failed to sign the data:
					  [GNUPG:] KEY_CONSIDERED 2490C79CFF035C6D49458100A27BC24FCCFB9B1E 2
					  [GNUPG:] BEGIN_SIGNING H8
					  gpg: signing failed: No pinentry
					  [GNUPG:] FAILURE sign 67108949
					  gpg: signing failed: No pinentry
					  - fatal: failed to write commit object
					  ```
						- ((63f8fe5a-255e-4682-b228-cc2790a41d73)) : **`-c user.useConfigOnly=true`**: This flag sets a configuration option temporarily for the duration of the command. In this case, it sets `user.useConfigOnly` to `true`, which means Git will only use the user configuration and ignore system-level and repository-level configurations. This flag ensures that Git uses only the configuration specified in the user's global configuration file.
						- This is an issue only present in ((6550215b-37e8-4e32-8c81-7d82e21d9091)) - not on command line via ((637b3bed-e87a-457a-ac16-860771bfc293)) nor in native ((63209272-1088-4824-a762-4ac7ded04b0a))
						- Solution
							- [[2024-04-04 Thursday]] In Flatseal enable `socket=gpg-agent`
							  collapsed:: true
								- ![image.png](../assets/image_1712233776873_0.png)
						- {Archive}
						  collapsed:: true
							- [[2024-04-03 Wednesday]] Don't do this - it prevents using ((6463498e-24be-461c-ac0e-c9f2c813a797))
								- Disable TTY for GPG
									- `echo 'no-tty' >> ~/.gnupg/gpg.conf`
								- Also
									- `export GPG_TTY=$(tty)`
								- [source] [A Quick Guide to Signing Your Git Commits – Steve Scargall](https://stevescargall.com/2020/02/04/a-quick-guide-to-signing-your-git-commits/)
				- [Learning Resources]
					- [Signing git commits using GPG (Ubuntu/Mac) · GitHub](https://gist.github.com/ankurk91/c4f0e23d76ef868b139f3c28bde057fc)
				- {Archive}
					-
				- Related: ((6550215b-1c6b-42b9-8be6-c1ec20aacade))
		- ## Tooling
			- AI generated commit messages
				- [OpenCommit — improve commits with AI 🧙 · Actions · GitHub Marketplace · GitHub](https://github.com/marketplace/actions/opencommit-improve-commits-with-ai)
				- [markuswt/gpt-commit: Generate commit messages using GPT-3](https://github.com/markuswt/gpt-commit)
					- [Never write a commit message again (with the help of GPT-3) · Roger Zurawicki](https://zura.wiki/post/never-write-a-commit-message-again-with-the-help-of-gpt-3/)
					-
		- [Learning Resources]
			- [Developer Tip: Keep Your Commits "Atomic" - Fresh Consulting](https://www.freshconsulting.com/insights/blog/atomic-commits/)
			- [How to Write a Git Commit Message](https://cbea.ms/git-commit/) 7 rules for better Git commit messages
	- `git config`
	  id:: 6463498e-c3ca-4659-94c6-4a40ec7f3743
	  collapsed:: true
		- https://www.gitkraken.com/learn/git/git-config
		- git config --global user.email "you@example.com"
		- git config --global user.name "Your Name"
		- `--global` sets it across all repositories
		- `git config --list`
			- user.name=Aaron
			- user.email=22418751+ajvsol@users.noreply.github.com
		- `nano ~/.gitconfig`
		  Editing it directly
		- Securely storing your GitHub authentication for git (to avoid having to type in username + password repeatedly)
		  id:: 633c850e-fd33-4e34-a743-67c417730fab
		  collapsed:: true
			- Either
				- Setup [Git Credential Manager (GCM)](https://github.com/GitCredentialManager/git-credential-manager)
					- Download and install
						- [Download latest release from here](https://github.com/GitCredentialManager/git-credential-manager/releases)
							- ```bash
							  /home/boss/Documents/ESSENTIALS/Programs/gcm-linux_amd64.2.0.785.deb
							  ```
						- OR via the helper script
							- ```bash
							  curl -L https://aka.ms/gcm/linux-install-source.sh | sh
							  ```
					- Configure it
					  ```bash
					  git-credential-manager-core configure
					  ```
					- [Learning Resources]
						- https://github.com/GitCredentialManager/git-credential-manager#linux-install-instructions
				- Git's built-in ephemeral in-memory [credential cache](https://git-scm.com/docs/git-credential-cache)
				  collapsed:: true
					- Enabling it:
					  ```bash
					  git config --global credential.credentialStore cache
					  ```
					- Adjust how long it'll store credentials for. Default is `900` seconds
					  ```bash
					  git config --global credential.cacheOptions "--timeout 300"
					  ```
						- `3600` = 1 hour
						- `21600` = 6 hours
					- [Learning Resources]
						- https://github.com/GitCredentialManager/git-credential-manager/blob/main/docs/credstores.md#gits-built-in-credential-cache
				- [git-credential-keepassxc: Helper that allows Git (and shell scripts) to use KeePassXC as credential store](https://github.com/Frederick888/git-credential-keepassxc)
					- [NixOS Search](https://search.nixos.org/packages?channel=22.11&show=git-credential-keepassxc&from=0&size=50&sort=relevance&type=packages&query=git-credential)
			- [Learning Resources]
				- https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git#platform-linux
				- https://github.com/GitCredentialManager/git-credential-manager
		- [Git aliases](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases)
		  id:: 63a06349-6ec2-4d2c-a4e4-bb92dc159cb8
			- `git checkout -b` can become `gco`
		- Related: ((6550215b-1c6b-42b9-8be6-c1ec20aacade))
	- `git checkout`
	  id:: 6737677d-97c5-41d4-94f1-16ab6c38882c
	  collapsed:: true
		- ((682910c1-2f43-444f-90e3-8a8bc54fbaae))
		- https://www.atlassian.com/git/tutorials/using-branches/git-checkout
		- `git checkout -b <new-branch>`
		  id:: 22098c8d-e0b9-4d2c-8be7-71729bf6c7d8
		  The above example simultaneously creates and checks out ＜new-branch＞. The -b option is a convenience flag that tells Git to run git branch before running git checkout ＜new-branch＞.
		- Related: ((6463498e-8351-4932-b925-9d3ff4faae14))
	- [`git cherry-pick`](https://git-scm.com/docs/git-cherry-pick)
	  id:: 661f634f-9314-45a5-905d-522a67463fe7
	  collapsed:: true
		- Flags
			- `-x`
				- When recording the commit, append a line that says "(cherry picked from commit …​)" to the original commit message in order to indicate which commit this change was cherry-picked from. This is done only for cherry picks without conflicts. Do not use this option if you are cherry-picking from your private branch because the information is useless to the recipient. If on the other hand you are cherry-picking between two publicly visible branches (e.g. backporting a fix to a maintenance branch for an older release from a development branch), adding this information can be useful.
	- `git fetch`
	  id:: 6463498e-6b6d-450b-a960-be2b24b77ad3
	  collapsed:: true
		- ((6463498e-1353-4064-81c2-8d571f8f92d5)) vs ((6463498e-6b6d-450b-a960-be2b24b77ad3))
			- When downloading content from a remote repo,  `git pull`  and  `git fetch`  commands are available to accomplish the task. You can consider  `git fetch` the 'safe' version of the two commands. It will download the remote content but not update your local repo's working state, leaving your current work intact.  `git pull`  is the more aggressive alternative; it will download the remote content for the active local branch and immediately execute  `git merge`  to create a merge commit for the new remote content. If you have pending changes in progress this will cause conflicts and kick-off the merge conflict resolution flow.
		- `git fetch <remote>`
		  id:: 63736c83-f539-4d8a-8a1a-77b5607c05be
		  Fetch all of the branches from the repository. This also downloads all of the required commits and files from the other repository.
			- `git fetch origin`
			  id:: 661e5819-c64e-4309-a2dd-03423f859cfc
			  Most common upstream remote
		- `git fetch <remote> <branch>`
		  Same as the above command, but only fetch the specified branch.
		- `git fetch --all`
		  A power move which fetches all registered remotes and their branches:
		- `git fetch --dry-run`
		  The --dry-run option will perform a demo run of the command. It will output examples of actions it will take during the fetch but not apply them.
		- How to fetch a specific remote branch
		  id:: 6463498e-8351-4932-b925-9d3ff4faae14
			- {{embed ((661e5819-c64e-4309-a2dd-03423f859cfc))}}
			- or `git fetch -all`
			- {{embed ((6463498e-ed57-48fe-b6d2-bf47128e8aae))}}
			- Optional?
				- `git fetch <remote-repo> <remote-branch>:<local-branch>`
					- Example
						- ```
						  git fetch origin tuesday-francesco-gabs:tues-fran-gabs
						  git fetch origin thursdaygabs:thu-gabs
						  ```
			- `git checkout <local-branch>`
				- If you use the same branch name as the remote branch then it should work. Doesn't need `origin` prefix either
			- Or
				- `git checkout -b feature/new-design origin/feature/new-design`
		- [Learning Resources]
			- [Git Fetch | Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/syncing/git-fetch)
			- [What is Git Fetch | Remote Branch & Solutions to Error Problems](https://www.gitkraken.com/learn/git/git-fetch)
	- [`git format-patch`](https://git-scm.com/docs/git-format-patch)
	  id:: 661da265-f98b-411f-9486-e8afe5a97153
	  collapsed:: true
		- `git format-patch [BASE_BRANCH_NAME]`
			- Pros/Cons
				- Pros
					- Unlike `git diff` it includes the commit message
					- Useful when your remote Git repository is down.
				- Cons
					-
				- Unclear
				- Comparisons
			- This will create a `.patch` file for each commit ahead of `master` that your branch is
			- Example
				- ```bash
				  $ git format-patch master
				  0001-Update-build-matrix.patch
				  0002-Display-current-gemfile-when-run-bundle-update.patch
				  ```
				- `git format-patch -n HEAD^`
				  Create a patch from the latest commit
					- Alternates:
						- `git format-patch HEAD^ --stdout > patchfile.patch`
						- `git show HEAD > some-patch0001.patch`
				- `git format-patch -1 9as8dadwad243`
				  i.e. ((661e2de0-d6db-4198-b8ff-8b8d3bc38eef))
			- Flags
				- `-o <directory>`
				  Output directory for `.patch` files e.g. `patches`
				- `-n <commit_sha>`
				  id:: 661e2de0-d6db-4198-b8ff-8b8d3bc38eef
				  Create a patch just for that specific commit. Can find commit SHA using ((661e2e3c-8ca0-4131-bbce-43f38ad5c164))
					- `<n>` -  Prepare patches from the topmost <n> commits e.g. `-1`
		- Related:
			- `git am <patch_file>`
			  Apply a patch file and commit it
			- ((661d7c04-a470-47fb-9c64-92fd2185a5cc))
			- [In Git, How Create Patch for Changes Between Current Head and Given Commit?](https://safjan.com/git-create-path/)
			  collapsed:: true
				- To create a patch in Git for the changes between the current HEAD and a given commit, you can use the `git diff` command with the `--patch` option. Here are the steps:
					- 1.  Get the hash of the commit you want to compare to the current HEAD by running `git log`.
					- 2.  Run `git diff --patch <commit hash> HEAD > mypatch.patch`.
					- 3.  This will create a patch file named `mypatch.patch` in the current directory.
				- The `git diff` command compares the specified commit to the current HEAD and generates a diff. The `--patch` option tells Git to output the diff in patch format. The `>` operator redirects the output to a file named `mypatch.patch`.
				- Note that the patch file will contain only the changes between the two commits, not the entire files. You can apply the patch by using the `git apply` command. For example, you can apply the patch with the following command: `git apply mypatch.patch`
				- This will apply the changes from the patch to the current working directory. If there are any conflicts, Git will stop and ask you to resolve them manually. You can then commit the changes as usual.
	- `git init`
	  Initialise this directory as a git repo
	- `git log`
	  id:: 661e2e3c-8ca0-4131-bbce-43f38ad5c164
	  collapsed:: true
		- `git log --oneline` is useful for easily reviewing, rather than just `git log`
	- `git ls-files`
	  collapsed:: true
		- `git ls-files <subdir>`
			- Check what files are tracked in git in <subdir>
	- `git merge`
	  collapsed:: true
		- `git merge --squash` to squash commits or `git rebase -i HEAD~N`
			- If you want to squash the last N commits into one
			- replace `pick` with `squash` for all commits except the first one
		- https://www.atlassian.com/git/tutorials/using-branches/git-merge
		- How to prevent vim opening after doing a merge
			- `git merge --no-edit`
	- `git patch`
	  collapsed:: true
		- https://www.gitkraken.com/learn/git/git-patch
	- `git pull`
	  id:: 6463498e-1353-4064-81c2-8d571f8f92d5
	  collapsed:: true
		- `git pull --force` doesn't exist but the equivalent to overwrite local changes is `git reset --hard origin/branch-name`
		- `git pull --rebase` = pull and remove all divergent local history. Better than `git pull --force`, which may pull ontop of divergent local history(?)
		- `git pull`
		  Fetch the remote origin’s copy of the current branch and immediately merge it into the local copy. This is the same as  `git fetch`  followed by  `git merge` .
		- `git pull <remote>`
		  Fetch the specified remote’s copy of the current branch and immediately merge it into the local copy. This is the same as  `git fetch ＜remote＞`  followed by  `git merge origin/＜current-branch＞` .
		- `git pull --no-commit <remote>`
		  Similar to the default invocation, fetches the remote content but does not create a new merge commit.
		- `git pull --rebase <remote>`
		  Same as the previous pull Instead of using  `git merge`  to integrate the remote branch with the local one, use  `git rebase` .
		- `git pull --verbose`
		  Gives verbose output during a pull which displays the content being downloaded and the merge details.
		- Related: ((63736c83-f539-4d8a-8a1a-77b5607c05be))
	- `git push`
	  collapsed:: true
		- `git push` to non-default branch
		  id:: 633be631-944e-42f8-8796-2a63ebb132f7
			- ```bash
			  git push <remote> <branch with new changes>:<branch you are pushing to>
			  ```
		- `git push --set-upstream origin feature_branch`
		  id:: 6373664b-31c4-40d6-95ae-872df37ff8bf
		  Pushing a new local branch
		- `git push origin HEAD`
			- This will look at your branch name then push to a remote branch of the same name
		- Related: ((633c850e-fd33-4e34-a743-67c417730fab))
	- [`git-range-diff`](https://git-scm.com/docs/git-range-diff)
	  id:: 661f67c1-36dd-46fa-851f-7849f2a7a57d
	  collapsed:: true
	  Compare two commit ranges (e.g. two versions of a branch)
		- Description
			- This command shows the differences between two versions of a patch series, or more generally, two commit ranges (ignoring merge commits).
			- In the presence of `<path>` arguments, these commit ranges are limited accordingly.
			- To that end, it first finds pairs of commits from both commit ranges that correspond with each other. Two commits are said to correspond when the diff between their patches (i.e. the author information, the commit message and the commit diff) is reasonably small compared to the patches' size. See \`\`Algorithm\`\` below for details.
			- Finally, the list of matching commits is shown in the order of the second commit range, with unmatched commits being inserted just after all of their ancestors have been shown.
			- There are three ways to specify the commit ranges:
				- `<range1> <range2>`: Either commit range can be of the form `<base>..<rev>`, `<rev>^!` or `<rev>^-<n>`. See `SPECIFYING RANGES` in [gitrevisions\[7\]](https://git-scm.com/docs/gitrevisions) for more details.
				- `<rev1>...<rev2>`. This is equivalent to `<rev2>..<rev1> <rev1>..<rev2>`.`
				- <base> <rev1> <rev2>`: This is equivalent to `<base>..<rev1> <base>..<rev2>`.
		- Flags
			-
		- [Can somebody explain the usage of git range-diff? - Stack Overflow](https://stackoverflow.com/questions/52323008/can-somebody-explain-the-usage-of-git-range-diff)
			- Range diff is very useful right after **resolving merge conflicts** (after `rebase`, `cherry-pick`, etc.), especially when you had **multiple conflicting commits**, and you want to make sure that you **haven't accidentally broken** something during the process.
	- [`git rebase`](https://git-scm.com/docs/git-rebase)
	  id:: 661f6879-1fbf-4561-980c-3d6aee180dac
	  collapsed:: true
	  Reapply commits on top of another base tip
		- Git rebase last commit onto another branch
		  collapsed:: true
			- Bertie recommends instead `git rebase -i target-branch` whilst feature-branch is checked out
			- I did a different way and it actually deleted my commit. Fortunately I had already pushed it before so the changes were available remotely:
				- Switch to the branch containing the commit you want to rebase: `git checkout feature-branch`
				  Identify the commit hash of the last commit you want to rebase. You can use git log to find the commit hash.
				  Rebase the last commit onto the target branch: `git rebase --onto target-branch <commit-hash> feature-branch`
		- `git rebase -i HEAD~<number of commits>`
			- Start an interactive rebase session by running the command git rebase -i HEAD~<number_of_commits> where <number_of_commits> is the number of commits you want to squash. For example, if you have four commits, the command would be git rebase -i HEAD~4
		- Description
		- Flags
			- `--autosquash`
			  id:: 661f68ec-8199-4f1b-863c-f264cf060999
			  `--no-autosquash`
				- Automatically squash commits with specially formatted messages into previous commits being rebased. If a commit message starts with "squash! ", "fixup! " or "amend! ", the remainder of the subject line is taken as a commit specifier, which matches a previous commit if it matches the subject line or the hash of that commit. If no commit matches fully, matches of the specifier with the start of commit subjects are considered.
				- In the rebase todo list, the actions of squash, fixup and amend commits are changed from `pick` to `squash`, `fixup` or `fixup -C`, respectively, and they are moved right after the commit they modify. The `--interactive` option can be used to review and edit the todo list before proceeding.
				- The recommended way to create commits with squash markers is by using the `--squash`, `--fixup`, `--fixup=amend:` or `--fixup=reword:` options of ((64973074-812e-4865-accd-f66ac694c60f)), which take the target commit as an argument and automatically fill in the subject line of the new commit from that.
				- Settting configuration variable `rebase.autoSquash` to true enables auto-squashing by default for interactive rebase. The `--no-autosquash` option can be used to override that setting.
				- See also INCOMPATIBLE OPTIONS below.
		- `git rebase -i HEAD~3`
		  Squash the last 3 commits into one
		- `git rebase -i develop`
			- Opens a text document which allows you to quite easily do changes
			- Changing nothing about the doc with do no changes
			- You can do `pick` for the top commit or `reword` then use `squash` for all the following commits in order to squash commits
	- `git remote`
	  collapsed:: true
		- `git remote set-url origin https://github.com/ajvsol/News` = change the remote origin's URL. Handy if trying to point a local repo at a brand new remote repo
		  id:: 63e533e3-d755-4018-ae4a-b022f214de94
	- `git reset`
	  collapsed:: true
		- https://www.gitkraken.com/learn/git/git-reset
		- [Reset all changes after last commit](https://stackoverflow.com/questions/4630312/reset-all-changes-after-last-commit-in-git)
			- **First, reset any changes**
			- This will undo any changes you've made to tracked files and restore deleted files:
			- ```
			  git reset HEAD --hard
			  ```
			- **Second, remove new files**
			- This will delete any new files that were added since the last commit:
			- ```
			  git clean -fd
			  ```
			- Files that are not tracked due to `.gitignore` are preserved; they will not be removed
			- *Warning*:  using `-x` instead of `-fd` *would* delete ignored files.  You probably don't want to do this.
	- `git restore`
	  collapsed:: true
		- `git restore --source=HEAD~1 --staged --worktree .` = revert state to that of the previous commit. Differences from current state will appear as unstaged changes
		- `git restore --source=HEAD --staged --worktree .` = revert state to that of the latest commit
	- `git submodule`
	  collapsed:: true
		- When trying to commit a new submodule into main repo you may get a pipeline error of 403 when GitLab tries to clone in the submodule
			- Go to your submodule project in GitLab.
			- Navigate to: Settings → CI/CD → Expand the "Token Access"/"Hob token permissions" section
			- Description: `CI/CD job token allowlist`
			- `Add group or project` button
			- Enter the path of your top-level repo
		- git submodules don't seem too hard to manage, since whenever you change branch you should `git submodule update` to ensure it's pointed to the correct version however it'll also show when you need to run this command because the Source Control tab in VSCode will show those files as changed for potential git staging until you run the command
		- git submodule change tracked branch
		  collapsed:: true
			- Either
				- 1)
					- `cd` into sumodule directory
					- git checkout the branch
					- `git branch --set-upstream-to=origin/branch-name`
					- Return to the main project directory and commit the changes:
						- `cd ..`
						- `git add path/to/submodule`
						- `git commit -m "Updated submodule to track branch branch-name"`
				- Add to `.gitmodules` file then run `git submodule update --init --recursive --remote submodule-path`
					- ```
					  [submodule "directory/submodule-dir"]
					  path = directory/submodule-dir
					  url = https://gitlab.com/project/repo.git
					  branch = 1-feature-branch
					  ```
					- Example
						- `git submodule update --init --recursive --remote submodules-dir/submodule1`
			- If you want to update all submodules to the latest commit on their tracked branch, you can use `git submodule update --remote`
		- Git submodules
			- When cloning a repository that contains submodules, you need to use the --recurse-submodules flag to initialize and clone the submodules as well. For example: $ `git clone --recurse-submodules <repository_url>`
				- Alternatively just `git clone` then `git submodule init` and `git submodule update`
		- How to add a Git submodule
			- `git submodule add https://github.com/example/repo.git path/to/submodule`
		- When using submodules it's James' convention to push your changes to a named branch which won't conflict with upstream branches e.g. `project-name`. This way you can push your merge requests/commits from different branches into one branch and still easily pull down any upstream changes or feature branches
		- `git submodule init` followed by `git submodule update`
		-
	- `git status`
	  collapsed:: true
		- = Check git status
	- `git switch`
	  collapsed:: true
		- `git switch` vs `git checkout`
		  id:: 682910c1-2f43-444f-90e3-8a8bc54fbaae
			- `git switch` is specifically meant for switching branches, whereas `git checkout` also allows for checking out specific files or even entire commits
- ## SOPs
	- Setup on a new machine
	  collapsed:: true
		- `git config --global user.name "FirstName LastName"`
		- `git config --global user.email myemail@example.com`
		- `git config --global core.autocrlf input`
			- Configure Git to handle line endings properly so that it doesn't think files have changed when the actual content hasn't changed. Recommended if you're collaborating with people who use different operating systems``
		- How to do git config on a new machine
			- `git config --global user.name "user1"`
			- `git config --global user.email "user1@example.com"`
			- `git config --global credential.helper "cache --timeout=86400"`
				- Sets a 24 hour(?) cache time
			- When you do an authenticated operation like `git fetch origin` then you'll get a pop-up asking for username + password. Use the access token from your repo provider instead of the password to store it
				- `git config credential.helper store` to store the token permanently
			- Testing authentication
			  id:: 679f9b3f-e849-4b52-93bf-f50fb4b258f3
				- `git fetch origin` is a good simple command for checking whether you’re authenticated for git + the repo you’re trying to pull from. Can see whether GCM (Git Credential Manager) is authenticated properly with GitLab personal access token
				-
		- `push.autoSetupRemote`
			- `git push` will fail by default unless you do `git push --set-upstream origin <branch-name>` first
			- Enable auto setup
				- ```bash
				  # Enable it globally (for all repositories)
				  git config --global push.autoSetupRemote true
				  
				  # Or enable it for just this repository
				  git config push.autoSetupRemote true
				  ```
	- How to initialise a git repo via CLI
	  id:: 6334823d-020a-4f84-a56c-3fa9adc2deea
	  collapsed:: true
		- ((6334823d-53f4-4935-a37d-32515f871e50))
		- `pwd` = Print working directory (on the CLI)
		- `ls -a` = Lists hidden directories like `.git`
		- `git commit -m 'Initialised repo and created README'` = Makes a commit with that title (`-m` = message)
		- `git log` = Shows git history
	- GitLab's git repo initialisation instructions
	  collapsed:: true
		- Configure your Git identity locally to use it only for this project:
			- `git config --local user.name "FirstName LastName"`
			- `git config --local user.email "email@email"`
		- Create a new repository
			- `git clone <repo url>`
			- `git switch --create main`
			- `touch README.md`
			- `git add README.md`
			- `git commit -m "add README"
			- `git push --set-upstream origin main`
		- Push an existing folder to an empty GitLab repo
			- `git init --initial-branch=main`
			- `git remote add origin https://gitlab.crimson.local/saturb/remote-device-control/which-craft/tango`
			- `git add .`
			- `git commit -m "Initial commit"
			- `git push --set-upstream origin main`
		- Push an existing Git repository
			- `git remote rename origin old-origin`
			- `git remote add origin <repo url>
			- `git push --set-upstream origin --all`
			- `git push --set-upstream origin --tags`
	- How to move a local repo to a new remote repo
	  collapsed:: true
		- ((63e533e3-d755-4018-ae4a-b022f214de94))
	- ((6463498e-8351-4932-b925-9d3ff4faae14))
	- To pull a remote branch
		- `git fetch -a`/`git fetch --all` = get list of all the remote branches and their latest commit
		- `git checkout <branchname>`
	- *Workflow with using branches with team*
	  id:: 637367b6-8f50-467a-bb35-78ccb33530b2
	  collapsed:: true
		- [How to update a dev branch with changes from master branch](https://stackoverflow.com/questions/20101994/how-to-git-pull-from-master-into-the-development-branch)
		  collapsed:: true
			- `git checkout dev`
			- `git fetch origin`
			- `git merge origin/master --no-edit`
			- Then merge the staged changes with the templated name commit. They won't show up on diff of pull request
		- ((6463498e-8351-4932-b925-9d3ff4faae14))
		  id:: 6463498e-cabb-45a1-801e-afcc48df5172
		- Common commands
			- ((22098c8d-e0b9-4d2c-8be7-71729bf6c7d8))
			- ((6373664b-31c4-40d6-95ae-872df37ff8bf))
		- GitHub branch protection rules
			- Prevent merging without PR
			- Lock branch (prevents pushes)
	- Typical solo workflow
	  id:: 6334823d-2d4a-4168-90ec-1e2384c79242
	  collapsed:: true
		- `git init` or `git clone`
		- ((6463498e-64f6-4f41-a5f5-8561abf19c0c))
		- ((64973074-812e-4865-accd-f66ac694c60f))
		- Either
			- `git push`
				- `git remote add origin https://github.com/Schoolof`
				- `git branch -M main`
				- `git push -u origin main`
			- `git pull`
	- How to uncommit
	  collapsed:: true
		- ```git
		  git rm -r --cached node_modules
		  git rm -r --cached .env
		  git commit
		  ```
	- How to change the timestamp of a commit
	  collapsed:: true
		- `git log .`
		  Display the log history, then select the old commit of which you want to change the timestamp
		- `git commit --amend --date="Wed Dec 21 12:30:20 2022 +0500" --no-edit`
			- In the above-stated command, the “–amend” option is added for updating commits, and “ –date” is a parameter that has the desired timestamp value
		- To ensure the updated old commit timestamp:
		  `git log .`
	- How to keep manage multiple repos from a master repo
	  id:: 633b74de-6471-4352-a675-405fb6aca458
	  collapsed:: true
		- `git subtree`
		  id:: 633b74de-bc16-47c3-b00c-5de274be5340
		  collapsed:: true
			- SOP: using `git subtree` for School of Code
			  id:: 633bea8e-34ae-4e70-805b-4982315d9a4c
				- Note: `git subtree` commands need to be run on command line because Visual Studio Code hasn't got that feature yet
				- 1) Cloning the subrepo remote as a local directory. If it isn't added this way, then commits won't be tracked in the parent repo
				  ```bash
				  git subtree add --prefix week-1/w1d2_workshop_romeo-and-juili-git-aandb https://github.com/SchoolOfCode/w1d2_workshop_romeo-and-juili-git-aandb main
				  ```
					- Testing
						- ```bash
						  git subtree add --prefix week-2/workshop_intro-to-codewars https://github.com/SchoolOfCode/bc13_w2d1_workshop_intro-to-codewars-room-42-aaron-and-fenton main
						  ```
					- If that doesn't work, then adjust the prefix. Note: this way seems to create it as a hidden folder?
					  ```bash
					  git subtree add --prefix=week-1/w1d2_workshop_romeo-and-juili-git-aandb https://github.com/SchoolOfCode/w1d2_workshop_romeo-and-juili-git-aandb main
					  ```
					- Has to be executed whilst in the parent repo
						- "You need to run this command from the toplevel of the working tree." error message if trying to run it whilst in a subdirectory
						- Won't work in a non-git repo directory
					- `main` - you only clone one branch at a time
					- ^^ISSUE (sometimes): It copies entire parent dir structure includes week directories^^
						- Didn't happen 19:20 04/10/22
				- 2 To update the parent repo with all the commits from subtree repos, in the terminal of the parent repo run `git push`. This pushes to the (default) parent repo
				  collapsed:: true
					- Whilst in the terminal for the subtree, `git push` needs to specify the remote repo to push to. By default will push to the parent repo
					  ```git
					  git push https://github.com/SchoolOfCode/w1d2_workshop_romeo-and-juili-git-aandb
					  ```
						- WRONG - it'll push the parent repo to the subtree repo
						- ^^hard reset to old commit for this repo^^
				- 3) To update the subtree repo, instead of `git push` whilst in the subtree repo, in the terminal for the parent repo use `git subtree push`:
				  collapsed:: true
				  ```bash
				  git subtree push --prefix=week-1/w1d2_workshop_romeo-and-juili-git-aandb https://github.com/SchoolOfCode/w1d2_workshop_romeo-and-juili-git-aandb main
				  ```
					- "You need to run this command from the toplevel of the working tree." error message if trying to run it whilst in a subdirectory
				- Related: ((633c850e-fd33-4e34-a743-67c417730fab))
			- https://www.atlassian.com/git/tutorials/git-subtree
			  collapsed:: true
				- First add  `git subtree`  at a specified prefix folder:
				  ```
				  git subtree add --prefix .vim/bundle/tpope-vim-surround https://bitbucket.org/vim-plugins-mirror/vim-surround.git main --squash
				  ```
					- ```
					  git subtree add --prefix=week-1/w1d2_workshop_romeo-and-juili-git-aandb https://github.com/SchoolOfCode/w1d2_workshop_romeo-and-juili-git-aandb main
					  ```
					- (The common practice is to not store the entire history of the subproject in your main repository, but If you want to preserve it just omit the –squash flag.)
				- If after a while you want to update the code of the plugin from the upstream repository you can just do a git subtree pull:
					- ```
					  git subtree pull --prefix .vim/bundle/tpope-vim-surround https://bitbucket.org/vim-plugins-mirror/vim-surround.git main --squash
					  ```
				- This is very quick and painless, but the commands are slightly lengthy and hard to remember. We can make the commands shorter by adding the sub-project as a remote.
				- Adding the sub-project as a remote
				  collapsed:: true
					- Adding the subtree as a remote allows us to refer to it in shorter form:
						- ```
						  git remote add -f tpope-vim-surround https://bitbucket.org/vim-plugins-mirror/vim-surround.git
						  ```
					- Now we can add the subtree (as before), but now we can refer to the remote in short form:
						- ```
						  git subtree add --prefix .vim/bundle/tpope-vim-surround tpope-vim-surround main --squash
						  ```
					- The command to update the sub-project at a later date becomes:
						- ```
						  git fetch tpope-vim-surround main
						  git subtree pull --prefix .vim/bundle/tpope-vim-surround tpope-vim-surround main --squash
						  ```
				- Contributing back upstream
				  collapsed:: true
					- We can freely commit our fixes to the sub-project in our local working directory now. When it’s time to contribute back to the upstream project, we need to fork the project and add it as another remote:
						- ```
						  git remote add durdn-vim-surround ssh://git@bitbucket.org/durdn/vim-surround.git
						  ```
					- Now we can use the *subtree push* command like the following:
						- ```git
						  git subtree push --prefix=.vim/bundle/tpope-vim-surround/ durdn-vim-surround main
						  ```
							- ```git
							  git subtree push --prefix=week-2/w1d2_workshop_romeo-and-juili-git-aandb https://github.com/SchoolOfCode/w1d2_workshop_romeo-and-juili-git-aandb main
							  ```
					- After this we’re ready and we can open a pull-request to the maintainer of the package.
			- https://developercommunity.visualstudio.com/t/somewhat-simpler-than-git-submodules-would-like-vs/576356
			  collapsed:: true
				- Add a subtree (as a remote)
				  id:: 633be204-7dae-4d7b-a2af-2d6ce1ab7fa9
					- ```
					  git remote add shared ssh://git@bitbucket.org/xyz/shared.git 
					  git subtree add --prefix=path/to/code --squash shared master
					  ```
				- Pulling upstream changes
					- ```
					  git subtree pull --prefix=path/to/code --squash shared master
					  ```
				- Pushing changes to the upstream repository
					- ```
					  git subtree push --prefix=path/to/code --squash shared master
					  ```
			- ((633be631-944e-42f8-8796-2a63ebb132f7))
			- Unrelated
				- Changing `master` to `main`
				- ```
				  git remote add origin https://github.com/ajvsol/school-of-code.git
				  ```
				- ```
				  git branch -m master main
				  git fetch origin
				  git branch -u origin/main main
				  git remote set-head origin -a
				  ```
				- ```bash
				  git reset --hard 4cabab2
				  ```
				- [Deleting branches](https://www.educative.io/answers/how-to-delete-remote-branches-in-git)
				  collapsed:: true
					- Deleting local branches
						- ```bash
						  git branch -a
						  # *master
						  #  test
						  #  remote/origin/master
						  #  remote/origin/test
						  
						  git branch -d test
						  # Deleted branch test (was ########).
						  ```
					- Deleting remote branches
						- ```bash
						  git branch -a
						  # *master
						  #  test
						  #  remote/origin/master
						  #  remote/origin/test
						  
						  git push origin --delete test
						  # To <URL of your repository>.git
						  #  - [deleted]         test
						  ```
			- https://medium.com/@porteneuve/mastering-git-subtrees-943d29a798ec
			- https://scribe.bus-hit.me/git-subtree-usage-6aaba8b5d947
		- `git submodule`
		  id:: 6463498e-cd08-4f5e-b4b1-2b2dcc380edc
		  collapsed:: true
			- Cons
				- It doesn't show the entire submodule history within the parent repo
				- It's just a hyperlink to the child repo
				  ![image.png](../assets/image_1664824192774_0.png)
			- `git submodule update --init --recursive` 
			  Update all submodules
			- `git module update --init` - download git submodules in repo
			- Example
				- ```
				  git submodule add git@mygithost:billboard lib/billboard
				  ```
					- `git@mygithost:billboard` - external repo that is to be added as a submodule
					- `lib/billboard` - This is the path where the submodule repository will be added to the main repository.
				- ```
				  git submodule add git@mygithost:billboard lib/billboard
				  ```
				- Setup
					- ```bash
					  git submodule add <url> week-2/bc13_w2d1_workshop_dom-102-room-42-aaron-and-fenton
					  ```
				- ```git
				  git submodule add https://github.com/SchoolOfCode/w1d2_workshop_romeo-and-juili-git-aandb week-1/w1d2_workshop_romeo-and-juili-git-aandb
				  ```
				- https://www.atlassian.com/git/tutorials/git-submodule
				- https://github.blog/2016-02-01-working-with-submodules/
				- https://gist.github.com/gitaarik/8735255
				- https://medium.com/@porteneuve/mastering-git-submodules-34c65e940407
		- https://github.com/ingydotnet/git-subrepo
		- Pull requests to a master repo
		  id:: 633d3685-33d2-431e-b1f3-5c942104eebd
		  collapsed:: true
			- Comparison of ((633b74de-bc16-47c3-b00c-5de274be5340)) vs ((633d3685-33d2-431e-b1f3-5c942104eebd))
			  id:: 633d3681-9aea-4045-842c-3394ceae8b4d
				- For pull requests
					- Allows me to still use git clone and git push/pull with child repos
					- Can squash commits to take credit for partner's commits
					- Squashed commits can also look more professional with better commit names/description
				- For git subtree
				  id:: 633d36a5-5aef-4e78-9fe4-a86eeb59c6ea
					- Don't have to change directory structure
						- Steps
							- Move all repos out of `school-of-code`, move into `/home/boss/Documents/WORK/Programming/School-of-Code/1DRAFT-REPOS`
					- Unsquashed commits can improve GitHub activity timeline look
	- Using multple Git identities on one PC
	  collapsed:: true
		- ((6550215b-1c6b-42b9-8be6-c1ec20aacade))
		- [Use multiple Git SSH identities on a single computer | Hacker News](https://news.ycombinator.com/item?id=36768334)
		-
	- Pushing an existing repo to a new host empty repository
	  collapsed:: true
		- `cd existing_repo`
		- `git remote rename origin old-origin`
		- `git remote add origin https://gitlab/blahblah/blah.git`
		- `git push --set-upstream origin --all`
		- `git push --set-upstream origin --tags`
	- If you ever make changes while in a detached HEAD and want to keep them, you should create a branch before leaving that state: `git checkout -b <new-branch>`
	- If you check out a previous commit (using ((6737677d-97c5-41d4-94f1-16ab6c38882c)) <old-commit>, e.g., git checkout HEAD~2), you enter what is called a detached HEAD state. Here's what happens if you make a commit at this point:
	  collapsed:: true
		- The new commits you make are not placed on your current branch (e.g., main) but instead create a new line of commits directly from the previously checked-out commit.
		- Your branch (e.g., main) remains pointing at the latest commit it had before you checked out; your new commits exist only in this detached HEAD state, not on any named branch.
	- How to "overwrite" the latest commits on the branch with your new commits
	  collapsed:: true
		- If your goal is for these new commits to replace (overwrite) the later commits on your branch (essentially rewriting history), you need to do one of the following:
		- 1. Force move the branch to your new commit
			- After making your new commit(s) in the detached HEAD, force-update your branch to point at them:
			- `git checkout main`, then `git reset --hard <your-new-commit-hash>`
	- If you `git checkout old-commit-id` and then want to keep those changes you can first `git commit` them, then:
	  collapsed:: true
		- `git checkout old-branch` to go back to the branch you want to overwrite, then `git reset --hard <commit-hash>` to overwrite that branch with your new commit chain/graph
		- Created a new branch from them `git checkout -c forked-branch-name`
			- `git checkout old-branch` to go back to the branch you want to overwrite, then `git reset --hard forked-branch` to apply the forked-branch changes to your old-branch
	- To checkout a previous commit and then later revert back to the latest commit, follow these steps:
	  collapsed:: true
		- 1. Checkout a Previous Commit
			- First, view your commit history to find the commit hash: `git log`
			- Copy the desired commit hash (it looks like e36e4c8...).
			- Now, checkout that commit: `git checkout <commit-hash>`
			- Or to checkout one commit before HEAD:
			- `git checkout HEAD~1`
			- This puts you in a detached HEAD state, meaning you're not on any branch but just viewing that commit's state. Do not make new commits here unless you intend to create a new branch.
		- 2. Revert Back to the Latest Commit
			- To return to your latest commit on your working branch, simply check out your branch again (commonly main or master): `git checkout main` or `git checkout <your-branch-name>`
			- This moves you back to tip of the branch (latest commit), and your working directory reflects the branch's latest state.
	- Git - if your work requires changes that only exist in a colleague's unmerged branch then best practice is to rebase your branch onto their branch
	  collapsed:: true
		- Either
			- `git checkout feature-branch && git rebase main` to rebase your feature branch onto main
			- `git rebase --onto main origin/main feature`
			- `git checkout -b my-feature origin/feature/new-design`
	- If you need to revert changes made in git and are struggling then try `git reset --mixed HEAD~N` where `N` = how many previous commits you wish to revert
		- Was useful for reverting some CRLF changes that I just could not get to sticking
		- All changes become unstaged but not discarded
	- `.gitkeep` files are often used when trying to get otherwise empty directory structures committed to Git
	- `git checkout -` / `git switch -` = go back to last branch
- ## Troubleshooting
	- git cloning when there's a certificate error
	  collapsed:: true
		- `git -c http.sslVerify=false clone https://your-git.repo.git`
			- `-c http.sslVerify=false` flag
				- Useful for certificate errors blocking git access e.g. corporate wi-fi
				- Example: `git clone -c http.sslVerify=false https://your-repo.git`
	- If you have unstaged files you can't seem to get rid of via `git stash` or `git reset --hard HEAD` or `git reset --hard origin/<branch-name>` then try VSCode's source control Discard All Changes button, or deleting the repo and recloning it
- # Ecosystem
	- ((634bc181-15f9-4d8b-9d1c-22e5cef9f5f0))
		- ((67376799-eb77-4dad-ae0f-105110389725))
- [Learning Resources]
	- ### Git
	  id:: 68d10df3-028b-47d9-951d-3cc0be11e2ad
		- [Git Articles - 30 seconds of code](https://www.30secondsofcode.org/git/p/1/)
			- Git Stashing
			  collapsed:: true
				- [Commands](https://git-scm.com/docs/git-stash#_commands)
				- `git stash` = ((68cd838d-219d-43be-8205-7b576f652933))
				- `git stash push`
				  id:: 68cd838d-219d-43be-8205-7b576f652933
				  collapsed:: true
					- In order to stash your changes, you can use the `git stash push` command.
					  collapsed:: true
						- This command saves the **current state** of the working directory and index into a new stash. You can optionally provide a message for the stash, and include **untracked files** using the `-u` option.
						- ```bash
						  # Usage: git stash push [-u] [<message>]
						  
						  git stash push
						  # Creates a new stash
						  
						  git stash push -u
						  # Creates a new stash, including untracked files
						  
						  git stash push "Bugfix WIP"
						  # Creates a new stash with the message "Bugfix WIP"
						  ```
				- `git stash list`
				  collapsed:: true
					- Stashes are stored as a **stack**, with the most recent stash at the top. You can view a list of all stashes using the [`git stash list`](https://git-scm.com/docs/git-stash#Documentation/git-stash.txt-listltlog-optionsgt) command. This command displays the stash reference, the branch or commit the stash was created on, and the message associated with the stash.
					- ```bash
					  # Usage: git stash list
					  
					  git stash list
					  # stash@{0}: WIP on patch-1: ee52eda Fix network bug
					  # stash@{1}: WIP on master: 2b1e8a7 Add new feature
					  ```
				- `git stash show`
				  collapsed:: true
				  View changes stored in a stash
					- This command displays the changes introduced by the stash relative to the parent commit. You can provide the stash reference to view a specific stash, or omit it to view the latest stash.
					- ```bash
					  # Usage: git stash show [<stash>]
					  
					  git stash show
					  # Displays the changes in the latest stash
					  
					  git stash show stash@{1}
					  # Displays the changes in the stash with the reference stash@{1}
					  ```
				- `git stash apply`
				  collapsed:: true
				  To apply changes from a specific stash
					- This command applies the changes from the specified stash to the working directory. You can provide the stash reference to apply a specific stash, or omit it to apply the latest stash.
					- ```bsah
					  # Usage: git stash apply [<stash>]
					  
					  git stash apply
					  # Applies the latest stash
					  
					  git stash apply stash@{1}
					  # Applies the stash with the reference stash@{1}
					  ```
				- `git stash pop`
				  collapsed:: true
				  To apply changes from a specific stash and remove it from the stash list
					- ```bash
					  # Usage: git stash pop [<stash>]
					  
					  git stash pop
					  # Applies the latest stash and removes it from the stash list
					  
					  git stash pop stash@{1}
					  # Applies the stash with the reference stash@{1} and
					  #  removes it from the stash list
					  ```
				- `git stash drop`
				  collapsed:: true
				  Delete specified stashes
					- This command removes the specified stash from the stash list.
					- ```bash
					  # Usage: git stash drop <stash>
					  
					  git stash drop
					  # Deletes the latest stash
					  
					  git stash drop stash@{1}
					  # Deletes the stash with the reference stash@{1}
					  ```
				- `git stash clear`
				  collapsed:: true
				  Delete all stashes
					- ```bash
					  # Usage: git stash clear
					  
					  git stash clear
					  # Deletes all stashes
					  ```
			- Aliasing
			  collapsed:: true
				- Creating aliases
					- Simply running [`git config --global alias.<alias> <command>`](https://git-scm.com/docs/git-config#Documentation/git-config.txt-alias) will create an **alias for the specified command**.
					- The alias can then be used in place of the command when running Git commands. If your command contains spaces, you can wrap it in quotes.
					- ```bash
					  # Syntax: git config --global alias.<alias> <command>
					  
					  git config --global alias.co checkout
					  # Creates an alias `co` for the `checkout` command
					  
					  git config --global alias.cm "commit -m"
					  # Creates an alias `cm` for the `commit -m` command
					  ```
					- Alternatively, you can [edit the configuration file](https://www.30secondsofcode.org/git/s/edit-config) and **add multiple aliases** all at once. This can be the more practical solution for adding more **complex commands**, as you don't have to worry about escaping special characters.
					- ```bash
					  # Syntax: git config --global -e
					  
					  git config --global -e
					  # Opens the global git configuration file in the default git text editor
					  ```
				- Suggested aliases
					- ```
					  [alias]
					    co = checkout
					    cob = checkout -b
					    coo = !git fetch && git checkout
					    br = branch
					    brd = branch -d
					    st = status
					    aa = add -A .
					    unstage = reset --soft HEAD^
					    cm = commit -m
					    amend = commit --amend -m
					    fix = commit --fixup
					    undo = reset HEAD~1
					    rv = revert
					    cp = cherry-pick
					    pu = !git push origin `git branch --show-current`
					    fush = push -f
					    mg = merge --no-ff
					    rb = rebase
					    rbc = rebase --continue
					    rba = rebase --abort
					    rbs = rebase --skip
					    rom = !git fetch && git rebase -i origin/master --autosquash
					    save = stash push
					    pop = stash pop
					    apply = stash apply
					    rl = reflog
					  ```
		- `sparse-checkout`
			- Alternative to `checkout` which allows users to reduce the working tree to a subset of tracked files**, enabling efficient management of large repositories, particularly monorepos.
			- e.g. only checkout `dir1/`, and `file1` instead of the whole multiple gigabyte repo
		- `git reset --hard origin/develop` is useful for discarding all changes and reverting your branch to the state of that branch, as opposed to `git stash`/`git stash --include-untracked`
		- `git pull --rebase` = pull and remove all divergent local history
		- `git pull -f` equivalent is `git reset --hard origin/<branch-name>`
		- Git Submodules
			- How to make parent repo branch point at a new commit in a submodule
				- In submodule create new branch and/or commits
				  logseq.order-list-type:: number
				- Then from parent git repo use `git add path/to/submodule` and `git commit` that
				  logseq.order-list-type:: number
	- ((6360e399-3c61-4105-8c74-89f62bcd796a)) : ((6463498e-0dfa-4be0-b88d-2a0ba1b484bb))
	- `.gitignore` file
	  collapsed:: true
		- If you want to just ignore `node_modules folder` then all it needs is:
		  ```git
		  node_modules
		  ```
		- `/`  is used to ignore pathnames relative to the  `.gitignore`  file
		- To add or change your global .gitignore file, run the following command:
		  ```
		  git config --global core.excludesfile ~/.gitignore_global
		  ```
		- Examples
			- ```git
			  # Ignore Mac system files
			  .DS_store
			  
			  # Ignore node_modules folder
			  node_modules
			  
			  # Ignore all text files
			  *.txt
			  
			  # Ignore files related to API keys
			  .env
			  
			  # Ignore SASS config files
			  .sass-cache
			  ```
		- How to Untrack Files Previously Committed from New Gitignore
			- To untrack a single file, ie stop tracking the file but not delete it from the system use:
			- git rm --cached filename
			- To untrack every file in .gitignore:
			- First commit any outstanding code changes, and then run:
			- git rm -r --cached
			- This removes any changed files from the index(staging area), then run:
			- git add .
			- Commit it:
			- git commit -m ".gitignore is now working"
			- To undo git rm --cached filename, use git add filename
		- {Archive}
			- https://www.freecodecamp.org/news/gitignore-what-is-it-and-how-to-add-to-repo/
			- https://www.w3schools.com/git/git_ignore.asp
	- ((62e8e1f6-01f5-46f6-89bd-a44d188cac3a))
	- ![git-cheat-sheet-education.pdf](../assets/git-cheat-sheet-education_1664288904798_0.pdf)
	- [Git commands you probably do not need | Hacker News](https://news.ycombinator.com/item?id=34487201)
	- [Git cheat sheet [pdf] | Hacker News](https://news.ycombinator.com/item?id=40486197)
	- Trunk-based development
	  id:: 6737677d-a601-40df-aeeb-fda8853b6b7a
	  collapsed:: true
		- [Here's how Google was able to move up Android 16's release date - Android Authority](https://www.androidauthority.com/android-trunk-stable-explained-3495640/)
		- [Trunk-based development](https://profy.dev/article/trunk-based-development-with-github) - basic explanation of branching/PR workflow
- Related:
	- [[Terminal]]
	- ((635fc546-d883-4e58-89d4-6c1069039fb6))
	- ((6737677f-ea5a-4602-9709-d1557a3ac3cf))