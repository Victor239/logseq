- AKA FOSS / Free Open-Source Software / FLOSS / Libre [[Software]]
- Pros/Cons
  collapsed:: true
	- Pros
		- Open-Source software to limit attack points
		- Open-Source software and/or Zero Knowledge only
	- Cons
		- Large parts of the community are ostracising right-wing individuals and views
			- [The Self-Destruction of Open Source Software - YouTube](https://youtu.be/0TANZ9cgKS0) by Bryan Lunduke
			  collapsed:: true
				- {{renderer :media, /home/boss/Vaults/gocryptfs1/1Vault/Logseq-attachments/The Self-Destruction of Open Source Software.mp4}}
	- Unclear
		- [Single vendor is the new proprietary | Hacker News](https://news.ycombinator.com/item?id=40089842)
			- those companies are still doing what is, essentially, proprietary software: like the proprietary software companies of the 80s, they very much consider the software being produced as their exclusive property. They still intend to capture all the value that derives from it. And thanks to copyright aggregation or permissive licensing, they still can change the license any time they want. So it’s still proprietary: they just choose, for now, to release their software under an Open Source license.
- Specifics
  collapsed:: true
	- Copyleft (e.g. GPL) has been more beneficial to the open-source and privacy industry than MIT/BSD license
	  collapsed:: true
		- That's why Linux beat BSD.
			- Remember, BSD had a substantial lead - with lots of well funded
			- enhancements ranging from Sun's SunOS, Dec's Ultrix, and others
			- (arguably even [MacOS (BSD -> Darwin -> MacOS); playstation 4's OS, and Nintendo Switch's](https://en.wikipedia.org/wiki/Berkeley_Software_Distribution)).
			- But thanks to the BSD license, all the best improvements died in those unshared forks.
		- Chromium is copyleft because it was forked from KHTML
			- uses Blink to do web rendering, which was forked from Apple's WebKit, which was forked from KHTML.
			- Chromium also uses V8 for web rendering (JS mostly), but since they built it just for Chrome/ium I feel like they could easily replace Blink (and the associated copyleft license) if they wanted to. Let's hope they don't.
	- Proprietary software is theft from the public domain, because once copyright runs out it's still not available in the Public Domain
	  collapsed:: true
		- This is about THEFT FROM THE PUBLIC DOMAIN.
		- Remember, copyright is a social contract: works inherently belong to the Public Domain, but we temporarily give control over them to their creators (or the creators' assignee) for the express purpose of encouraging more to be created. If the creator['s assignee] uses technology to destroy the work before it can be made available in the Public Domain, they have unfairly reaped the benefits while cutting the public out of the deal.
		- In other words, putting a warning on the box doesn't solve this problem. This sort of business model ought to be outright illegal! Or at least publishers should be forced to give the Library of Congress a reproducible build or something.
	- _[Learning Resources]_
	  collapsed:: true
		- [https://github.com/trimstray/the-book-of-secret-knowledge](https://github.com/trimstray/the-book-of-secret-knowledge)
- [Open-source games](((632cf49f-a6f7-4d2d-b3a5-3ee44968263e)))
- Software Groups
  collapsed:: true
	- Portable Apps
	  collapsed:: true
	  #PortableApps
		- Linux
			- Maintain a list of packages for utilities that don't store my preferences/data
				- Why
				  collapsed:: true
					- Other apps like Firefox or Thunderbird I need to backup the whole folder with my data in one place
					- Also allows me to put them in encrypted containers (hidden or visible)
					- Allows me to hide that I use these apps (via hidden encrypted container)
				- How
				  collapsed:: true
					- Use a package list for these apps
					- Linux doesn't really have portable apps per se,[1] but you can maintain a list of the main package names of the non-default programs you install (you don't need to list any dependencies; just the primary package). Then, you can easily re-install them.
					- For example, you might have this file, called ~/installed_apps.txt:
					- agave
					- gimp
					- openssh-server
					- qalculate
					- Then, to reinstall, do this (assuming a Debian-based distro such as Ubuntu or Mint):
					- sudo apt-get install $(cat ~/installed_apps.txt)
					- The programs will be downloaded and re-installed. And provided that you backed up your entire home directory, including the files and directories beginning with dots, you'll also retain most of your settings. A backup of /etc ought to get most of the rest.
					- [1]: In a number of cases, you could compile programs yourself such that they'd be largely portable. However, such a method wouldn't be useful, because you'd miss out on all the great advantages of package management e.g. automatic management of dependencies, upgrading to latest version, not having to backup a large set of
					- EDIT:
					- Provided that aptitude is installed, here's a script I wrote to list all the non-autoinstalled packages (not on OS). It is a useful tool, but be aware that if you're disciplined in using the approach above, you'll get more accurate results.
					- #!/bin/bash
					- aptitude search '?and(?and(?not(?automatic),?installed),?not(?section(libs)))' --display-format '%p'
					- Save it somewhere (such as ~/bin/list_nonautoinstalled_packages) and make it executable. You can then use it to generate your installed apps list:
					- ~/bin/list_nonautoinstalled_packages > ~/installed_apps.txt
					- When using this script, I've found it best to manually review the output file and prune unnecessary stuff. Doing so is good in case you upgrade your system; dependencies may change, so you'll only waste disk space if you include dependencies in your list.
						- 7-Zip
						- VLC
						- iTunes
						- LibreOffice
						- Chrome
						- Firefox
						- GIMP
						- F.lux
						- Clam
						- Phrase Express
				- Make sure to get portable
				  collapsed:: true
					- Jing
					- Ditto
					- TeamViewer
			- WINE + windows portable app
			- Actually it may not be necessary if I continue with new config (see txt)
		- Portable app updates
			- Windows
				- Updates properly
					- Firefox
				- Installs
					- Evernote
			- Linux
	- Habitica
	  collapsed:: true
		- + Cross-platform. Cloud backup. Good for managing daily habits. Fun and motivating. Good for generating reports to see overview of dailies (also Way of Life app is good at this, but not cross-platform or cloud backup)
		- - No stored data on subtask completion. Non-clickable URLs in subtasks.
		- Codebase is open source - just figure out how to host it myself. Also configure it so I'm premium
		- And use client-side encryption
		- See #ClientSideEncryption
- Libre, OSI-certified
- Not just "source available" software
  collapsed:: true
	- Microsoft shared source licenses which restrict
- Documentation
	- License types
		- MIT
		- BSD
		- GPL
		- AGPL
		  collapsed:: true
			- AWS and Google have a strict policy against using AGPL software. This means they're unable to monetise it without releasing their changes open-source tooo
				- This would have prevented them monetising products like ((6607f722-b674-4037-af49-e03bafebc259)) and ((663a5795-4f40-45f6-86b4-ef5efc8883fe)), which later switched to ((663a5795-a56a-4b11-b469-7e2702b89ce1))
			- ## Examples
				- tgstation
				- element.io
	- Finding Open-Source Software
	  collapsed:: true
		- Why
			- With closed source software, you need to have 100% trust in the vendor because there's nothing except for their morality in the way of them leaking your personal information. Even if you can vouch for their integrity, proprietary software invariably has more uncaught security bugs and exploits because there are fewer eyes examining the source code.
		- [Learning Resources]
			- Regularly updated
				- https://alternativeto.net
				- https://www.opensourcealternative.to/
				- https://ossdatabase.com/
				- https://www.privacyguides.org/
				- https://github.com/awesome-selfhosted/awesome-selfhosted
				- https://github.com/RunaCapital/awesome-oss-alternatives
				- [Open Hub, the open source network](https://openhub.net/)
				- [Open Source Alternatives to Popular Software – OpenAlternative](https://openalternative.co/)
				-
			- www.prism-break.org
			- https://www.osalt.com/
			- https://en.wikipedia.org/wiki/List_of_free_and_open-source_software_packages
			- [https://n0where.net/best-self-hosted-alternatives/](https://n0where.net/best-self-hosted-alternatives/)
			- [https://www.btw.so/open-source-alternatives](https://www.btw.so/open-source-alternatives)
			- Android
				- https://fossdroid.com/
				- https://droid-break.info/
				- https://reddit.com/r/fossdroid
				- https://reddit.com/r/fdroid
			- https://reddit.com/r/opensource
			- https://www.deepdotweb.com
	- Monetisation
	  id:: 646349bf-aefa-41ef-b90e-605c7dd1b3b6
	  collapsed:: true
		- FOSS funding initiatives
		  collapsed:: true
			- _See_ [Open Collective (marketed for open source)](https://workflowy.com/#/eb9eb1febc96)
			  #Privacy
			- NLnet
				- [https://nlnet.nl](https://nlnet.nl/project/current.html)
			- [Mozilla’s Open-Source Support](https://www.mozilla.org/en-US/moss/)
			- NGI TRUST
				- [https://www.ngi.eu/ngi-projects/ngi-trust/](https://www.ngi.eu/ngi-projects/ngi-trust/)
			- [https://sustainoss.org/](https://sustainoss.org/)
		- Methods
		  collapsed:: true
			- Contributor License Agreement (CLA)
			  id:: 65537044-d96b-4261-af0b-d2e055c7df6b
			  collapsed:: true
				- Done by
					- [Grafana](https://grafana.com/docs/grafana/latest/developers/cla/)
					- Element
					  id:: 663b10fd-37a7-4bd7-9f6d-1e2941cfbf79
					  collapsed:: true
						- [A new home and license (AGPL) for Synapse and friends](https://element.io/blog/element-to-adopt-agplv3/)
						  collapsed:: true
							- We have succeeded in making Matrix wildly successful, but Element is losing its ability to compete in the very ecosystem it has created. It is hard for Element to innovate and adapt as quickly as companies whose business model is developing proprietary Matrix-based products and services without the responsibility and costs of maintaining the bulk of Matrix. In order to be fair to our customers, we need to be able to put more focus on them and their specific requirements.
							- So it’s time for us to get back in the game by establishing a level playing field and ensuring we can continue to support Matrix, whilst delivering the services our customers are requesting. This took us to reconsider how we license the open source code we develop.
							  After considerable thought, and taking particular [inspiration from Grafana](https://grafana.com/blog/2021/04/20/grafana-loki-tempo-relicensing-to-agplv3/), we’ve chosen to pursue future development of Synapse (the main Matrix server), Dendrite (our second generation Matrix server) and associated server-side projects (e.g. sydent, sygnal) under the terms of the [Affero General Public License (AGPL) v3](https://www.gnu.org/licenses/agpl-3.0.en.html) - maintaining the code in new repositories in the Element GitHub org, forked from the Apache-licensed repositories in the Matrix.org GitHub org (originally donated by Element).
							- The benefit of switching to AGPLv3 is that it obliges downstream developers to contribute back to the core project - either by releasing their modifications as open source for the benefit of the whole Matrix ecosystem, or by contacting Element for an alternative license. Future code contributors to Synapse will need to sign a contributor license agreement (CLA) based on the [Apache Software Foundation’s CLA](https://www.apache.org/licenses/contributor-agreements.html#clas), giving Element the right to license the contribution commercially to third party proprietary forks so we can use it to help fund Matrix core development in future. (EDIT: to be clear, the sole reason for a CLA is to allow Element to dual-license the software as per [Selling Exceptions to the GNU GPL - GNU Project - Free Software Foundation](https://gnu.org/philosophy/selling-exceptions.html) - **not** to give Element the ability to relicense to a non-OSI license in future. After all, Element already had that ability with the Apache license, and has not used it.)
							- We believe this is the fairest approach possible: preserving the Free and Open Source nature of these Matrix implementations under an OSI-approved open source license (AGPLv3), while encouraging proprietary forks to contribute to the development costs of the underlying project.
							- ...
							- Now, CLAs come in all shapes and sizes: some good and some bad. It’s critical to understand that our reason for requiring one here is to give us the right to [sell AGPL exceptions](https://www.gnu.org/philosophy/selling-exceptions.html): not to “do a Hashicorp” and switch to a non-FOSS licence in future. We’ve made this clear in the wording of the CLA (using a similar approach to Signal’s CLA) by committing to distributing contributions as FOSS under an OSI-approved licence – many thanks to those who gave feedback on the original announcement to suggest this. You can find the final CLA wording [here](https://static.element.io/legal/contributor-license-agreement.pdf), derived from the well-respected Apache Software Foundation CLA.
							- [Discussion](https://news.ycombinator.com/item?id=38162275)
							  collapsed:: true
						- [Synapse now lives at github.com/element-hq/synapse](https://element.io/blog/synapse-now-lives-at-github-com-element-hq-synapse/)
						  collapsed:: true
							- We need to encourage other commercial Matrix vendors and governments building on Synapse or Dendrite to contribute to the underlying costs of developing these projects – either by contributing back code by open sourcing their changes, or by arranging an AGPL exception by contacting [licensing@element.io](mailto:licensing@element.io).
							- In order to sell AGPL exceptions, Element needs to have permission from future code contributors to be able to redistribute their contributions under a non-AGPL licence. This means that future contributors will need to sign a Contributor Licence Agreement (CLA) to grant Element the permission to distribute their code under non-AGPL terms.
							- Now, CLAs come in all shapes and sizes: some good and some bad. It’s critical to understand that our reason for requiring one here is to give us the right to [sell AGPL exceptions](https://www.gnu.org/philosophy/selling-exceptions.html): not to “do a Hashicorp” and switch to a non-FOSS licence in future. We’ve made this clear in the wording of the CLA (using a similar approach to Signal’s CLA) by committing to distributing contributions as FOSS under an OSI-approved licence – many thanks to those who gave feedback on the original announcement to suggest this. You can find the final CLA wording [here](https://static.element.io/legal/contributor-license-agreement.pdf), derived from the well-respected Apache Software Foundation CLA.
						- ![element-contributor-license-agreement.pdf](../assets/element-contributor-license-agreement_1715147226603_0.pdf)
						- [This is to let Element sell AGPL exceptions to commercial Matrix vendors in order to fund their underlying Matrix development](https://matrix.org/blog/2023/12/25/the-matrix-holiday-update-2023/)
						- Sep 2024 - [Sustainable licensing at Element with AGPL](https://element.io/blog/sustainable-licensing-at-element-with-agpl/)
						  collapsed:: true
							- At the time, we held off on making the shift for other projects as we wanted to learn from the community feedback and process with Synapse, and discuss further with the various downstreams.  However, we’re now at the point where we can finalise the move to AGPL - so please be aware that in the near future, we will be moving our development of the following remaining backend projects to the [element-hq](http://github.com/element-hq) GitHub org, under the terms of AGPLv3:
								- sygnal and sydent
								- matrix-authentication-service
								- sliding-sync proxy
								- lb and lb-android
								- dendrite and gomatrixserverlib
								- any remaining synapse modules
							- Much as for the backend projects, the reason is to encourage the ever-growing set of proprietary downstream forks to either contribute their code improvements to the projects, or to support our underlying development costs by procuring a licence if needed - as otherwise neither Element nor its contributions to Matrix will be sustainable.  Forks who open source their changes (e.g. SchildiChat) are of course not affected.
							- This does **not** impact the client SDKs which underpin these apps: matrix-rust-sdk, matrix-js-sdk, matrix-ios-sdk and matrix-android-sdk2, which will remain as Apache 2.0 projects in the matrix-org GitHub org in order to continue to drive Matrix uptake as generously as possible - see The Matrix.org Foundation’s [“Heart of Matrix”](https://matrix.org/blog/2024/08/heart-of-matrix/) blog post for more context.  The only exception is matrix-react-sdk, which despite the name is in fact the Element Web codebase, and is not used by any other app to our knowledge - and so its development will shortly move to the element-hq GitHub org and continue as AGPLv3.
							- Just as for Synapse, contributors will need to sign our [CLA](https://static.element.io/legal/contributor-license-agreement.pdf) (which is automated in GitHub) in order to grant Element the right to sell proprietary licenses to those who need them - which is the whole point of the licence shift in the first place. The CLA however does explicitly include a clause to commit Element to continue to distribute contributions under an OSI-compatible FOSS licence (e.g. AGPL).
					- [Signal >> Contributor License Agreement](https://signal.org/cla/)
					- ((7cc348b0-a232-4687-a29f-6483103a90ba)) - e.g. [PR](https://github.com/Codecademy/docs/pull/4198) uses ((646349bf-dc51-4cf8-8a7f-d6bb8ef13980))
					- [[Logseq]] : [logseq/CONTRIBUTING.md at master · logseq/logseq · GitHub](https://github.com/logseq/logseq/blob/master/CONTRIBUTING.md#-sign-the-cla) / [CLA assistant](https://cla-assistant.io/logseq/logseq)
					-
				- [GitHub - cla-assistant/cla-assistant: Contributor License Agreement assistant (CLA assistant)](https://github.com/cla-assistant/cla-assistant)
				  id:: 646349bf-dc51-4cf8-8a7f-d6bb8ef13980
				- Contributor License Agreement https://github.com/privacyguides/privacyguides.org/pull/1924
				- Selling CLA exceptions to a AGPL-3.0 codebase
					- Pros/Cons (from perspective of codebase owner)
					  collapsed:: true
						- Pros
							- The CLA makes you the only one who can build proprietary modifications on top. Monopolization of the position they gained by advertising as open-source.
						- Cons
							- You're morally obliged to maintain their feature, as well as not move it to a paid tier
						- Unclear
						- Comparisons
					- ((663b10fd-37a7-4bd7-9f6d-1e2941cfbf79))
				- Related:
					- [Mold linker may switch to a source-available license](https://github.com/rui314/mold/releases/tag/v1.7.0)
						- [Mold linker may switch to a source-available license | Hacker News](https://news.ycombinator.com/item?id=33584651)
							- Post
							  collapsed:: true
								- # Problem with my open-source startup
								  
								  I was optimistic when I started the [mold linker](https://github.com/rui314/mold) project that I'd be able to earn a comfortable income in some way if it becomes popular. But I may have to admit that I was a bit too optimistic. I'm still losing my money after two years. I *have* enough money that I earned when I was working as a full-time software engineer, but if I keep losing it, it's not sustainable long term. This isn't my hobby project; I've been working on it full-time as the main product for my startup.
								  
								  It's even a bit ironic that I had been asked by several big-name companies when mold/macOS would become available, since they wanted to use it for their multi-billion-dollar businesses. But none of them gave me financial support.
								  
								  A major obstacle in getting financial support is most companies don't have an internal process to start funding an open-source project. If they need to buy a license, that's fine, that's part of their usual business. But supporting (or *giving money away* to) "free" software is almost impossible. It raises too many questions at every level of management. What is the accounting item it should be categorized to? Is there any legal implication? Who can approve it in the first place? And last but not least, why do they have to do it if it's available for free?
								  
								  I've been trying to establish a business based on selling support and getting financial support. But I need to admit that it's not doing well as I would have hoped.
								  
								  Given this situation, I'm seriously considering changing the mold license from AGPL to a commercial, source-available one. Something like individuals would be able to use it for free but companies have to pay. This should make things smoother for both me and corporate users. I can change the license (or sublicense) because I wrote almost all the code myself, and all remaining patches to mold are licensed under the dual license of MIT/AGPL.
								  
								  I know some people are not happy about even thinking about relicensing, and so am I. But to me, it is more important to make the project viable long-term and grow into something that we can hire an engineer or two to accelerate the development. If my company can earn enough money, we may even be able to start a more ambitious project such as writing a crazy fast C++ compiler from scratch.
								- # Business Source License
								  id:: 1efa66b5-cf23-4e2b-abf7-396eee85057b
								  
								  The new license I'm considering at the moment is [Business Source License 1.1](https://mariadb.com/bsl-faq-adopting/). Under that license, non-production use of our product is always free. Corporate users would be asked to buy a separate per-user commercial license.
								  
								  A notable feature of BSL 1.1 is that each software release licensed under BSL 1.1 will automatically be available under a GPL-compatible license at most four years after the release. For example, if I release mold 2.0 under BSL 1.1 on January 1, 2023, mold 2.0 will be available under a GPL-compatible license at least by January 1, 2027. There's of course a business risk of releasing production software under an open-source license, but I'm not worried too much because mold is already available as open-source software. Four years is short, but I'll to try to establish a business foundation within that time frame and expand our software portfolio so that we don't rely only on the mold linker.
								  
								  Rui Ueyama
								  
								  2022-11-13
							- [mold/LICENSE at main · rui314/mold · GitHub](https://github.com/rui314/mold/blob/main/LICENSE)
							- [They have a CLA](https://raw.githubusercontent.com/rui314/mold/main/CONTRIBUTING.md)
							  collapsed:: true
								- ```md
								  # Contributing to mold
								  
								  We request all patches to mold to be released under the dual license
								  of the GNU AGPLv3 and the MIT license. Please read the following and
								  sign-off your patch as an indication of agreement.
								  
								  > ## Developer's Certificate of Origin
								  >
								  > By making a contribution to this project, I certify that:
								  >
								  >  1. The contribution was created in whole or in part by me and I
								  >     have the right to submit it under the Dual License of the GNU
								  >     AGPLv3 and the MIT license; or
								  >
								  >  2. The contribution is based upon previous work that, to the best
								  >     of my knowledge, is covered under the the Dual License and I
								  >     have the right under the Dual License to submit that work with
								  >     modifications, whether created in whole or in part by me, under
								  >     the Dual License (unless I am permitted to submit under
								  >     different licenses), as indicated in the file; or
								  >
								  >  3. The contribution was provided directly to me by some other
								  >     person who certified (1), (2) or (3) and I have not modified it.
								  >
								  >  4. I understand and agree that this project and the contribution
								  >     are public and that a record of the contribution (including all
								  >     personal information I submit with it, including my sign-off) is
								  >     maintained indefinitely and may be redistributed consistent with
								  >     this project or the open source license(s) involved.
								  
								  If you agree, you just add a line saying:
								  
								  ```
								  Signed-off-by: Random J Developer <random@developer.example.org>
								  ```
								  
								  using your real name (sorry, no pseudonyms or anonymous contributions.)
								  This will be done for you automatically if you use ``git commit -s``.
								  Reverts should also include "Signed-off-by". ``git revert -s`` does that
								  for you.
								  
								  We assume that any contribution that's 10 lines or less does not meet
								  the threshold of originality and therefore copyright does not apply.
								  You don't need to add a "Signed-off-by" line to such small patches.
								  ```
					- ((6638cd47-5245-4882-97e4-2ba23f498a21))
					-
			- Proprietary source-available licenses
			  id:: 663a5795-a56a-4b11-b469-7e2702b89ce1
			  collapsed:: true
				- Business Source License
					- Used by
						- ((638d061d-e696-4f04-933c-35f8836e125d)), though it trigger the ((650bee1d-9820-4336-ac32-a3e59ac5fc83)) fork
					- ((1efa66b5-cf23-4e2b-abf7-396eee85057b))
				- Server Side Public License
				  id:: 663a5795-2362-4b06-8449-249e3736aa1a
					- Used by
						- ((63a9bb62-f035-405e-b4c9-633f8b95c38b))
						- Graylog
						- Elasticsearch
						  id:: 663a5795-4f40-45f6-86b4-ef5efc8883fe
						  collapsed:: true
							- Elastic back in 2021 [which switched](https://venturebeat.com/business/elastic-ceo-reflects-on-amazon-spat-license-switch-and-the-principles-of-open-source/) Elasticsearch from Apache 2.0 to a duo of source available licenses — this was to prevent third-parties such as AWS from offering their own version of Elasticsearch “as-a-service” to their own customers, particularly when they don’t contribute anything meaningful back to the project itself.
							- [[2024-08-30 Friday]] [However they changed back to AGPL](https://www.elastic.co/blog/elasticsearch-is-open-source-again)
								- Elastic now plans to add AGPL as another license option alongside ELv2 and SSPL in the coming weeks. They emphasize that they have continued to operate like an open-source community despite the previous license change. Existing users of Elasticsearch can continue without changes, while new users will have the option to choose the open-source AGPL license.
				- Other licenses
					- ((6607f722-b674-4037-af49-e03bafebc259))
					- ((66475304-c12c-42c1-9e0a-86b9ad6fabc2)) used by ((6534f0fb-6058-4755-9754-117a3f12c27a))
					- Elastic License V2
					- Duplicacy - [commercial](https://github.com/gilbertchen/duplicacy/blob/master/LICENSE.md)
					  id:: 6553675a-f8ed-4f1e-b0b0-90629e7f28b3
					- CC BY-NC-SA
					  collapsed:: true
						- which prohibits all commercial use and requires that derivative works are published under the same license.
						- If you want redistributors to credit the authors, use CC BY. If you don't want to allow anyone other than the copyright holders to sell the software or derivatives, use CC NC. If you want both of the above and distributors need to keep the same license, there's the CC BY-NC-SA mentioned above.
					- Duplicacy
					- [Licenses – Polyform Project](https://polyformproject.org/licenses/)
				- ((63209272-1088-4824-a762-4ac7ded04b0a)) : ((5dcc13bc-fecd-4ce2-9793-c65eb22fc046))
				- [[C#]] : ((6463496d-5daf-4892-b9f0-ad45c649e777))
			- Open-Source Businesses
			  id:: 629ccb26-50de-4519-ab3c-eb3d8b8a65ed
			  collapsed:: true
				- _Models_
					- Open Core (open-source main features, proprietary premium features
					  collapsed:: true
						- Similar to freemium model
						- Examples
						- Pros
							- High margins, High defensibility, High scalability,
						- Examples e.g. Confluent, Elastic, GitHub
						- It is important for the community to not feel that essential functionality is being held back from the core product. For most successful open-core companies their customers represent only a small percentage of their overall users. Ensuring the success of the open source product is key to the success of the commercial offering.
						- [Preventing the bait and switch by open core software companies | Hacker News](https://news.ycombinator.com/item?id=33364390)
						  collapsed:: true
							- [Preventing the bait and switch by open core software companies | Open Core Ventures](https://opencoreventures.com/blog/2022-10-preventing-the-bait-and-switch-open-core/)
								- ![image.png](../assets/image_1714998599095_0.png)
								- Developer Certificate of Origin (DCO) means that the code author keeps copyright, unlike a ((65537044-d96b-4261-af0b-d2e055c7df6b)) where the copyright is assigned upstream
								  id:: 6638cd47-5245-4882-97e4-2ba23f498a21
					- Professional Services (Proserv)
						- Low margins, Low defensibility, Medium scalability
						- Mainly consulting
						- Examples eg Hortonworks, Canonical (Ubuntu), RedHat
					- Hosting
						- Medium margins, Low defensibility, Medium scalability
						- Examples eg MongoDB, WPengine
						- High competition e.g. from cloud infrastructure providers like AWS
					- Marketplace
						- Medium margins, High defensibility, High scalability
						- Examples eg Android, Mozilla
						- Mozilla similarly generates the bulk of their $500m annual revenue by providing lead generation to search engines.
				- How to do
					- ((632cf49f-a6f7-4d2d-b3a5-3ee44968263e))
					- Open-source Dapps (Monetisation for FOSS creators)
					  #Decentralisation https://workflowy.com/#/5f27ccbae305
					- Open-source AI
					- Open-Source Contributors Worth Sponsoring
					  https://news.ycombinator.com/item?id=29024804
					- web apps
				- Hosted Browsh
					- Create scripts to deploy Docker containers automatically and horizontal scale
				- [Learning Resources]
					- https://safing.io/blog/2021/05/06/how-weak-business-models-destroy-everything-we-fight-for/
					- How to monetise OSS
					  https://news.ycombinator.com/item?id=31292768
					- https://github.com/PayDevs/awesome-oss-monetization
					- https://github.com/protontypes/open-business-models
					-
			- Enterprise membership
				- [Matrix membership](https://matrix.org/membership/)
				  collapsed:: true
					- ![image.png](../assets/image_1715148111164_0.png)
					- [Matrix.org - Support Matrix](https://matrix.org/support/)
					-
		- How to dual license open-source projects - [Element example in the header/footer] (https://github.com/element-hq/element-android/pull/8990/files)
		- [Learning Resources]
			- [https://plausible.io/blog/open-source-funding](https://plausible.io/blog/open-source-funding)
			- [It requires surrendering exclusive right to commercially benefit from the project](https://drewdevault.com/2021/01/20/FOSS-is-to-surrender-your-monopoly.html)
			- Element and Matrix
			  collapsed:: true
				- > Element can no longer financially afford to donate its work on Synapse and other server components to the Matrix Foundation under the permissive Apache licence. Instead, Element is continuing development under the copyleft AGPLv3 licence at [github.com/element-hq/synapse](https://matrix.org/blog/2023/12/25/the-matrix-holiday-update-2023/github.com/element-hq/synapse) going forwards. This is to let Element sell AGPL exceptions to commercial Matrix vendors in order to fund their underlying Matrix development: you can read more about it at [Element’s announcement](https://element.io/blog/synapse-now-lives-at-github-com-element-hq-synapse/) - or you can listen to this week’s Matrix Live for a firsthand explanation
				  > [[2023-12-25 Monday]] [Blog post](https://matrix.org/blog/2023/12/25/the-matrix-holiday-update-2023/#in-other-news)
					- [Synapse now lives at github.com/element-hq/synapse](https://element.io/blog/synapse-now-lives-at-github-com-element-hq-synapse/)
				- [GitHub - matrix-org/matrix-spec-proposals: Proposals for changes to the matrix specification](https://github.com/matrix-org/matrix-spec-proposals)
			- ((632cf49f-a6f7-4d2d-b3a5-3ee44968263e)) monetisation
			- Code is open-source, but not the assets, like the art and music
			  collapsed:: true
				- Pros
					- Works for KeeperRL, Amnesia 1 & 2
				- Cons
					- Games like Gmod, Minecraft and Dwarf Fortress have 99% of the work is in the code. These games would be unprofitable if the code was free
			- Some examples of popular ((632cf49f-a6f7-4d2d-b3a5-3ee44968263e)) and how they're funded:
			  collapsed:: true
				- Mindustry - Free direct download, name your price on Itch, about $5 on Steam, and a few dollars on iOS. GPL v3. Paid versions have additional features such as achievements and mod workshop support - Quite successful with 9000 Steam reviews and almost a thousand on iOS. 90% of commits done by the main dev
				- Space Station 13 ecosystem: - FOSS servers like /tg/ make a few hundred $ a month, only bit more than hosting costs - Proprietary engine BYOND makes a few thousand $, but yeah it's closed-source - SS14 and other FOSS SS13 successors make a few hundred, but it gets reinvested into code bounties
				- Veloren - Makes a few hundred per month, being used to cover server and other maintenance costs
				- OpenMW - Main project doesn't accept donations in order to avoid legal issues with Bethesda, but individual devs have Patreons which add up to a few hundred $
				- ((6318fd52-c87b-4b6c-9ea1-fea756d1d4a8)) - Technical lead/host and one developer each get donations via GitHub Sponsors/Patreon to the tune of a few hundred $
				- As you can see, people are far more willing to pay to access the game on other platforms than simply donating. There's probably other notable profitable projects and models that I've missed.
			- [Polar – Pledge for progress](https://polar.sh/)
			- Creating a commercial foundation
			  collapsed:: true
				- e.g. managed hosting, custom development for the software
				- Examples
					- ((649b11eb-796e-4bb3-a608-09d98867166b))
					- Zammad, GitLab, Vanilla and Discourse
					- Gitea
			- [I turned my open-source project into a full-time business](https://docs.emailengine.app/how-i-turned-my-open-source-project-into/)
				- https://news.ycombinator.com/item?id=39522348
	- Maintaining a Fork
	  id:: 661d49e7-76c5-46b1-80e1-f9565ed90972
	  collapsed:: true
		- Maintaining a downstream
		  id:: 661cce79-050f-4019-a31a-a780e5e2107e
			- Examples
				- [Proton](https://github.com/ValveSoftware/Proton) is Valve's experimental fork of [Wine](https://github.com/ValveSoftware/wine)
				  id:: 661d4a1b-dbfb-4d32-ba80-428874990929
					- Uses many ((6463498e-cd08-4f5e-b4b1-2b2dcc380edc))  for dependencies
					  id:: 661d5b7a-332c-4d15-bd98-071d86af7484
						- Git Submodules which check out a specific commit (e.g. ((661d4a1b-dbfb-4d32-ba80-428874990929)) ). Some repos might be forks in your own organisation/account, whereas you might use others directly
					- Don't push changes to `master` branch. Version it e.g. `proton_9.0`
						- This way you can increase the minor version whenever you update the version of the git submodule which contains upstream code
					- Maintains their changes in
						- a Python script called [`proton`](https://github.com/ValveSoftware/Proton/blob/proton_9.0/proton)
						- [A forked `wine` repo](https://github.com/ValveSoftware/wine)
							- [Nothing gets merged directly to the current branch](https://github.com/ValveSoftware/wine/pull/222#issuecomment-1986211602)
								- > Thanks! It is in Proton Experimental [bleeding-edge] branch now ([History for ), - ValveSoftware/wine · GitHub](https://github.com/ValveSoftware/wine/commits/experimental-wine-bleeding-edge-9.0-84776-20240308-p9ca19d-w9f1b44-d69a52b-vffb04f/),) it should appear in next Experimental proper release and then eventually settle in Proton Stable.
								- It gets added to `experimental-wine-bleeding-edge-9.0<unique-id>` rather than current branch `proton_9.0`
					- ((661d8b47-128a-4e37-825f-99516dfebf10))
					  collapsed:: true
						- {{embed ((661d8b47-128a-4e37-825f-99516dfebf10))}}
				- Proton-GE-Custom is a fork of Proton
					- They mostly use
						- `.patch` files
						  id:: 661d7c04-a470-47fb-9c64-92fd2185a5cc
							- Related: ((661da265-f98b-411f-9486-e8afe5a97153))
				- [Tor Browser](https://gitlab.torproject.org/tpo/applications/tor-browser) is the Tor Browser Project's fork of [Firefox ESR](https://github.com/mozilla/gecko-dev)
				  id:: 661d4b27-0b8b-4038-81a8-eb36416ff86f
				  collapsed:: true
					- [ESR Rebase and Commit Structure](https://gitlab.torproject.org/tpo/applications/team/-/wikis/Development-Information/Tor-Browser/Tor-Browser-Repository-Overview#esr-rebase-and-commit-structure)
					  id:: 661d4e46-e4fc-4bfc-9fd5-b8208794e634
						- As we develop Tor Browser, we try not to interlace our changes with the changes coming from Mozilla. Instead, we keep our commits distinct, and apply them _after_ Mozilla commits. Whenever Mozilla releases a new version (including periodic updates) we perform an _ESR rebase_, where we take our Tor Browser commits from a previous `tor-browser-` branch and apply them on top of the new Mozilla Firefox ESR base. This can lead to conflicts, especially when changing between major ESR versions, which we resolve case-by-case by amending our Tor Browser commits.
						- This pattern means that we cannot practically maintain a full history of all the changes for Tor Browser alongside a changing ESR base. If we tried to apply the full history of incremental commits every time we performed a rebase, we would run into constant conflicts for each commit, many of which would be outdated or hard to resolve. Instead of using commits to represent incremental changes, we use commits to represent "features" and any changes to these features are applied as ["fixup!" commits](https://git-scm.com/docs/git-commit#Documentation/git-commit.txt---fixupamendrewordltcommitgt).
						- For example, a [commit for the Tor circuit panel feature](https://gitlab.torproject.org/tpo/applications/tor-browser/-/commit/1b54237b803f465c3bd799c648f0758e73bc749b "Bug 41600: Add a tor circuit display panel.") will be tweaked with [a fixup commit](https://gitlab.torproject.org/tpo/applications/tor-browser/-/commit/ed56d740590dd2f2596e92911c6081c70520f04c "fixup! Bug 41600: Add a tor circuit display panel."). In a later `tor-browser-` branch, the change in the fixup will be merged with the original commit to form a single commit again. This allows us to constantly clean up or adjust our patches in a way that makes the next ESR rebase feasible.
						- As a result, most new commits that land will be "fixup!" commits, or "squash!" commits. Exceptions to this would be for new features, specific patches we want to pull in early from Mozilla upstream, or patches that we expect to be temporary for whatever reasons.
						- What counts as a distinct "feature" often comes down to the question of what makes our life easier as developers, so may require some discussion. For example, [one commit is for Tor Browser strings](https://gitlab.torproject.org/tpo/applications/tor-browser/-/commit/c5f069ae06c52827cccbbdb0b1c5b5fcee59cfba "Tor Browser strings") even though the strings are used in different components: we made this decision because we wanted the strings to share the same file to make translation easier. Occasionally, we will change our mind and will split or merge commits to re-adjust.
						- A downside to this approach is that tools like `git blame` or `git bisect` are less useful than in other projects. Generally, we compensate for this by waiting two rebases before merging the fixups into their target so that these tools still work for recent changes. We can also compensate with some clear comments describing intent or motivation with references to gitlab issues.
					- [Commit Your Changes](https://gitlab.torproject.org/tpo/applications/team/-/wikis/Development-Information/Tor-Browser/Contributing-to-Tor-Browser#commit-your-changes)
						- Unlike most git projects, we perform regular ESR rebases for tor-browser, which means most changes should be committed as fixups of existing "feature" commits from the "origin" branch. For more information, see [the section on our commit structure](moz-extension://c41dff12-6510-43b2-ba87-8ca6561dec19/tpo/applications/team/-/wikis/Development-Information/Tor-Browser/Tor-Browser-Repository-Overview#esr-rebase-and-commit-structure).
						- If you are contributing an entirely new feature to Tor Browser, you can create a new commit. But in most cases, you should determine which existing feature commits your changes should target with a fixup.
						- For example, suppose your changes involve modifying both `browser/components/newidentity/content/newidentity.js` and `browser/components/BrowserGlue.sys.mjs`. If we look at the [history of changes for `newidentity.js`](https://gitlab.torproject.org/tpo/applications/tor-browser/-/commits/tor-browser-115.4.0esr-13.5-1/browser/components/newidentity/content/newidentity.js), this is an entirely separate feature added for Tor Browser. The only normal commit that changes this file has the message ["Bug 40926: Implemented the New Identity feature"](https://gitlab.torproject.org/tpo/applications/tor-browser/-/commit/bd30dffe843051a098ddf0107edbd4d9eca5b08c "Bug 40926: Implemented the New Identity feature"), with a commit hash of `bd30dffe843051a098ddf0107edbd4d9eca5b08c`. For a situation like this, we most likely want to fix up this commit:
						- ```bash
						  # Stage only the changes to newidentity.js
						  git add browser/components/newidentity/content/newidentity.js
						  # Verify that only newidentity.js is staged.
						  git status
						  # Create a new fixup for "Bug 40926: Implemented the New Identity feature".
						  git commit --fixup=bd30dffe843051a098ddf0107edbd4d9eca5b08c
						  ```
						- Next, you will often want to add your own message for what changes you made. To add your message, use `git commit --amend` and append lines for your message, so that the overall message would look something like:
						- ```
						  fixup! Bug 40926: Implemented the New Identity feature
						  
						  Bug <issue-number>: Description of my changes.
						  ```
						- where `<issue-number>` is the gitlab issue number for the issue you are trying to fix.
						- NOTE: A "fixup!" message will be lost once the changes eventually merge into the main commit at a later ESR rebase. This is desirable in most cases since we want the commit message to remain descriptive of the overall intent of the commit. If you wish to append your message permanently to the main commit's message, use `--squash` instead of `--fixup` above to create a "squash!" message.
						- In contrast, if we look at the [history of changes for `BrowserGlue.sys.mjs`](https://gitlab.torproject.org/tpo/applications/tor-browser/-/commits/tor-browser-115.4.0esr-13.5-1/browser/components/BrowserGlue.sys.mjs), it contains changes from several Tor Browser commits, as well as from Mozilla. In a situation like this, you should review each existing commit and determine whether your changes relate to any specific one. For example, if you change a line that was added in one commit, then that would be an obvious target. If none of the commits relate to your change, but they are relevant for some other "feature" commit, you could target that instead. In general, use your best judgement and discuss with other developers if you are not sure.
						- We have an automated tool to help you make these decisions:
						- ```bash
						  ./tools/torbrowser/tb-dev auto-fixup
						  ```
						- This will take each changed file in the current working directory and make suggestions about which commit to target. It will then create the fixup commits for you, and allow you to add any messages.
						- If you are creating, deleting or moving entire files, you may need to take the manual approach above. Similarly, if you are making changes to a single file that may need to fixup several "feature" commits, you may want to use `git add --interactive` to have more fine-grained control.
						- In these situations, you may find it useful to use `tb-dev log` to run `git log`, but limit the commits to only changes made for Tor Browser. I.e. excluding the long history of changes that come from Mozilla, which should never be fixed up. For example:
						- ```bash
						  # View the history of changes to BrowserGlue.sys.mjs
						  ./tools/torbrowser/tb-dev log -- --patch -- browser/components/BrowserGlue.sys.mjs
						  # View what files each commit has targeted.
						  ./tools/torbrowser/tb-dev log -- --stat
						  ```
				- ((64f5dc5e-096c-4c82-9f14-7a0ac55c1505)) uses BYOND modularisation
				  collapsed:: true
					- [Skyrat13/.github/CONTRIBUTING.md at master · Skyrat-SS13/Skyrat13 · GitHub](https://github.com/Skyrat-SS13/Skyrat13/blob/master/.github/CONTRIBUTING.md#skyrat-specifications)
						- Due to the fact that Skyrat is downstream there is special notation that should be followed. If able, new code should be put under modular_skyrat. If you are adding/changing a single line of code, you should add //Skyrat change to end end of the line. If adding/changing multiple lines of code, you should add //Skyrat change start before the first line edited and //Skyrat change stop after the last line edited. If removing code from the core module, it should be commented out. For a single line you would do // [code] //Skyrat change, for multiple line removals, use /* and */, adding a comment up at the top stating Skyrat removal or if it was moved to modular.
				- ((64f5dc5b-23d5-4890-b475-6459ab2ffed2)) uses a closed-source git submodule
					- Though they haven't got an upstream, they just happen to use this git submodule to receive FOSS contributions yet stay partially closed-source
			- ## Me asking devs
			  collapsed:: true
				- My posted question to coderbus
				  id:: 661d725b-b725-4371-a736-fb0315ff3c0a
					- Hi all, I was wondering if anyone had any tips/docs/links for the best practices for maintaining a fork long-term?
					  
					  I've had a look at a few very popular projects that maintain forks long-term to see how they do it:
					  
					  1) Proton is a fork of Wine. They have Wine as a git submodule, and every few weeks when they update this submodule they create a new branch with a new minor version. Their own changes are stored mostly in a single Python script to make tweaks where necessary and they have their own directories for various larger features.
					  
					  2) Tor Browser is a fork of Firefox ESR. They commit directly into their forked repo, and instead periodically rebase all their commits on an updated upstream version.
					  
					  3) Proton-GE-Custom is a fork of Proton. They mostly use .patch files it looks like. 
					  
					  I'm not sure of the pros/cons of these various approaches, nor what other approaches to consider. Any feedback would be appreciated.
				- [Proton/wine query](https://github.com/ValveSoftware/wine/issues/229)
				  id:: 661d8b47-128a-4e37-825f-99516dfebf10
					- TL;DR:
						- Unlike ((661d4b27-0b8b-4038-81a8-eb36416ff86f)), they revert their own conflicting commit, then reapply the upstream cherry-pick, then reapply their previous commit
						- They use ((661f656b-3fb0-4da6-b709-b4d05fa6f63e)) commits to improve their own older commits.
						- They use ((661f6879-1fbf-4561-980c-3d6aee180dac)) ((661f68ec-8199-4f1b-863c-f264cf060999)) to rebase.
						- ((661f62f5-6fa8-4d6e-9682-a98c9904d271))
					- How they do it
						- There's a lot of people involved in the process. Usually everyone working on Proton rebases patches in their area of expertise. It's a huge collaborative effort where we maintain a list of downstream patches and then slowly chop away at it, either via removing patches (upstremed / fixed by unralated upstream change) or rebasing. Sometimes features require almost complete rewrite due to the size of the delta.
						- We don't do merges. We reapply the commits on the new tree. If we pick a patch from upstream we ((661f634f-9314-45a5-905d-522a67463fe7)) `-x` it to include the original commit, e.g. [cdd0337](https://github.com/ValveSoftware/wine/commit/cdd03370324d4a2ae9b3ec95ec3f7752dfb85774). Sometimes that may need a bit of massage to make it apply but that's fine. We may drop a note or revert the commit that created the conflict, apply the cherry-pick and reapply (redo?) the problematic conflict.
						- We use ((661f656b-3fb0-4da6-b709-b4d05fa6f63e)) commits but in a different way - to fixup downstream commits, e.g.: [f5c2fd9](https://github.com/ValveSoftware/wine/commit/f5c2fd9cb7dc27c8c7ea2925a8b45bf4e929988f) fixes a downstream hack targeting a game (for this [previous commit](https://github.com/ValveSoftware/wine/commit/27448768d98b9a47ff6fc4f62ce61421175e7008)).
							- The fixup is editing a different file, so it's just being used to logically improve the quality and comprehensiveness of the original commit.
						- It will eventually get squashed into the original commit using ((661f6879-1fbf-4561-980c-3d6aee180dac)) ((661f68ec-8199-4f1b-863c-f264cf060999)). If it's on the `proton_9.0` branch the squash will happen when we are rebasing things onto the new upstream base. `experimental_9.0` branch is a bit more volatile - we rebase it on top of `proton_9.0` whenever a new stable version is released. So next one will be when Proton 9.0-1 is released. We may occasionally rebase experimental outside of this schedule - when it's significantly easier than the alternative, e.g. a bunch of reverts and cherry-picks, there are too many fixups and things get confusing, etc.
						- To compare two branches that may be rebased version of this patches I use ((661f67c1-36dd-46fa-851f-7849f2a7a57d)) which is an awesome tool.
						  id:: 661f62f5-6fa8-4d6e-9682-a98c9904d271
			- ((64f5dc5e-0066-4a5b-a71a-9e4cf14bcdd1))
			- How to
				- Strategies
					- Mirror Commits
					  id:: 661d70dc-34be-4c4f-9b54-d6140c425c29
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Pros
								- Likely less conflicts overall as my current PRs only have to not conflict with PRs merged whilst the branch is open (eg 1-2 weeks). In contrast bulk merging might result in conflicts with several months worth of code at once
							- Cons
								-
							- Unclear
							- Comparisons
								- ((661d70dc-34be-4c4f-9b54-d6140c425c29)) vs ((661d70e0-68c0-457c-8534-13ae07187da6))
								  id:: 661d7427-de6d-4a2d-91fc-f1cf81d15869
									- **Workflow Preference**: If you prefer to have a detailed history of changes in your fork, mirroring commits might be preferable. If you're more concerned with maintaining a stable version and don't need detailed history, periodic bulk updates could suffice.
									- **Project Size and Frequency of Changes**: For large projects with frequent updates, mirroring commits might become cumbersome. In such cases, periodic bulk updates can help manage the workload more effectively.
									- **Collaboration and Code Review**: If you're collaborating with others on your fork, mirroring commits can make it easier to review and manage changes. Bulk updates may make it harder to track individual contributions.
									- **Risk of Merge Conflicts**: Frequent mirroring of commits can help identify and resolve conflicts early. Bulk updates may lead to larger merge conflicts if changes have diverged significantly between the fork and upstream.
						- With this approach, you continuously pull changes from the upstream repository into your fork.
						  Each individual commit from the upstream repository is mirrored in your fork, maintaining a history of the changes.
						  This method provides granular control over which changes are integrated into your fork and allows for easy tracking of upstream changes.
						- [GitHub - yogstation13/MirrorBot: Yogstation's own mirrorbot™](https://github.com/yogstation13/MirrorBot)
						- [GitHub - austation/PRMirror: Mirror's pull requests from one repository to another. Modified by Terra](https://github.com/austation/PRMirror)
					- Periodically Bulk Update
					  id:: 661d70e0-68c0-457c-8534-13ae07187da6
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Popular forks like I listed here ((661d725b-b725-4371-a736-fb0315ff3c0a)) don't just mirror PRs because it means that their master branch would potentially break often whenever there's a conflicting change
							- Cons
								- you'll run into problems that are several months old
								- There could be a lot of conflicting changes added at once
								  id:: 661d7a8a-7429-4a1b-a646-63ceb0a4265d
							- Unclear
							- Comparisons
								- ((661d7427-de6d-4a2d-91fc-f1cf81d15869))
						- In this approach, you periodically synchronize your fork with the upstream repository, but instead of pulling individual commits, you fetch and merge the entire branch or branches.
						  You might perform this synchronization at set intervals or milestones rather than with every upstream commit.
						  This method simplifies the process of integrating changes but may result in larger and less granular commits in your fork's history.
					- Rebasing
					  id:: 661d7462-6d85-428d-b051-dc40a57e0f7b
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Pros
								- If I want to later upstream anything then it's easier to see which commits of mine I can squash together in order to do so
							- Cons
								- Same issue as ((661d70e0-68c0-457c-8534-13ae07187da6)) that ((661d7a8a-7429-4a1b-a646-63ceb0a4265d))
							- Unclear
							- Comparisons
						- Instead of merging changes from upstream into your fork, you can rebase your changes on top of the upstream changes.
						- This involves rewriting your commit history so that it appears as if your changes were made on top of the latest changes from upstream.
						- Rebasing keeps the commit history cleaner and linear but requires more care to avoid conflicts and ensure that your changes remain compatible with the upstream changes.
					- Cherry-Picking
					  collapsed:: true
						- Cherry-picking involves selecting specific commits from the upstream repository and applying them to your fork.
						- This approach allows for even more granular control than mirroring commits, as you can choose only the commits that are relevant to your fork.
						- Cherry-picking is useful when you want to selectively integrate specific features or fixes from upstream without pulling in the entire history.
					- Merge Strategy
					  collapsed:: true
						- Depending on your project's needs, you can adopt different merge strategies, such as merge commits, squash merges, or fast-forward merges.
						- Merge commits preserve the history of changes from both branches, while squash merges combine all changes into a single commit, simplifying the history.
						- Fast-forward merges simply move the branch pointer forward without creating a merge commit, assuming there are no conflicts.
						- Choosing the appropriate merge strategy depends on factors such as project size, collaboration dynamics, and the desired clarity of the commit history.
					- Unsorted
						- The better approach would probably be to refactor your code in a way that it uses the vanilla "software package". There are several ways of doing that like subclassing or wrapping or whatever.
						- Maintain a patch set separate from the code. Instead of modifying and checking into your own repository, keep a set of patches that you apply to new versions. This creates clear IP separation between your code and the upstream code. It also creates small, purposeful patches you can selectively push back up stream (defect fixes vs. extensions, for example). When you build, organize your build process to apply patches and then build. Don't maintain your own repo. Obviously this works best if you anticipate relatively few changes to the upstream code.
						- Introduce facades, PIMPL, or entry/exit stubs to segregate your code from the upstream code. This minimizes the textual changes you make to the upstream source code.
						- git rerere
							- [Git - Blog Moved](https://git-scm.com/blog/2010/03/08/rerere.html)
							- [Fix conflicts only once with git rerere | by Christophe Porteneuve | Medium](https://medium.com/@porteneuve/fix-conflicts-only-once-with-git-rerere-7d116b2cec67#.m8z8dltdw)
				- Combinations
					- ((661d5b7a-332c-4d15-bd98-071d86af7484)) + ((661d7c04-a470-47fb-9c64-92fd2185a5cc)) + ((661d7462-6d85-428d-b051-dc40a57e0f7b))
			- Options
				- The first one is you can create a repo and import upstream in the first box it asks. That way you’ll be independent of upstream but can add it as a target upstream and pull from it anytime.
				  
				  The 1.5 option is to clone the upstream repo. Which is more or less the same as 1 but it can be quicker
				  [22:54]
				  Option 2 is just to fork upstream as your repo. The downside is every PR you do will default to targeting upstream and not your own fork which is a PITA as I’ve found many times
				  [22:56]
				  So yeah just do the first one in either flavour. You push to your own master or PR to it if you want your commits to be actually searchable (beyond minor stuff). Then occasionally make a branch, target upstream, pull from it then PR that to your master
- [Learning Resources]
  collapsed:: true
	- [Open Source Heroes | Showcase Your Contributions to the Community](https://opensource-heroes.com/)
	- [OSS Insight](https://ossinsight.io/#trending-repos)
	- Proprietary software should be assumed to be malware
	  collapsed:: true
		- ![image.png](../assets/image_1665401676120_0.png)