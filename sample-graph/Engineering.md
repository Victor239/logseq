### Categories
	- ### BAE
	  collapsed:: true
		- Team notes
		  collapsed:: true
			- George is 29
			- Adam is 32(?)
		- Annual leave informing SOP
		  collapsed:: true
			- Calendar appointment - mark Out of Office, subject Out of Office
			- Calendar meeting - mark Free, subject Aaron Out of Office, invite people
		- WC
		  collapsed:: true
			- tech stack
				- Git submodule
				- GitLab pipelines
				- Bash scripts for building, installing
				- Python scripts (+ binary) for running on Ubuntu
				- PyImgui for GUI desktop on Ubuntu
				- Ruff and other linting
				- Java for Android
				- Vagrant and Docker for dev environment
				- TypeScript, Next.js for frontend
				- ADB
			- Directory structure
				- Get a LLM to add lines to see indenting level like ((68e66df0-0f54-44b1-90b6-44769a958927))
				- ```
				  root/
				    .devcontainer/
				    .vscode/
				    dwhite/
				    docs/
				    security/
				    src/
				      .docker/
				      .pip/
				      component1/
				        .venv/
				        tests/
				        src/
				        build.sh
				        pyproject.toml
				        README.md
				      component2/
				      component3/
				      dependencies/
				        project/
				          android/
				            deps/
				            README.md
				          pyinstaller/
				            deps/
				            README/md
				        toolchains/
				          android-emulator/
				            deps/
				            devcontainer-feature.json
				            install.sh
				            README.md
				          android-sdk-build-tools/
				      .dockerignore
				      .prettierignore
				      .prettierrc.yml
				      build.sh
				      Dockerfile
				      eslint.config.js
				      ruff.toml
				      Vagrantfile
				    .gitattributes
				    .gitignore
				    .gitlab-ci.yml
				    .gitmodules
				    README
				    
				  ```
		- Corporate cards
		  collapsed:: true
			- AMEX is primary
				- Also I need to do another form to withdraw cash (for OC expenses)?
			- Barclaycard for places which don't take AMEX e.g. training providers
	- ### LLMs
	  collapsed:: true
		- Pros/Cons
			- Pros
				- We're just moving up the delegation/abstraction ladder, like we did with compilers.
					- I don't care about the individual lines of code, I care about architecture, code structure, rigorous automated e2e tests, contracts with comprehensive validation, etc. Rather than waste a bunch of time pouring over agent PRs I just make them jump over extremely high static/analytic hurdles that guarantee functionality, then my only job is to identify places where the current spec and the intended functionality differ and create a new spec to mitigate.
			- Cons
				- [Study: Artificial Intelligence Use Reprograms the Brain, Leading to Cognitive Decline](https://arxiv.org/abs/2506.08872)
				  collapsed:: true
					- Students who repeatedly relied on ChatGPT showed weakened neural connectivity, impaired memory recall, and diminished sense of ownership over their own writing.
					- #### **LLM Users Forget What They Just Wrote**
						- In post-task interviews:
							- 83.3% of LLM users were unable to quote even one sentence from the essay they had just written.
							- In contrast, 88.9% of Search and Brain-only users *could* quote accurately.
						- 0% of LLM users could produce a *correct quote*, while most Brain-only and Search users could.
				- [Study: Developers think AI is making them 20% faster, but they're actually 19% slower](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/)
				  collapsed:: true
					- If so many developers are so extraordinarily productive using these tools, where is the flood of shovelware? We should be seeing apps of all shapes and sizes, video games, new websites, mobile apps, software-as-a-service apps — we should be drowning in choice. We should be in the middle of an indie software revolution. We should be seeing 10,000 Tetris clones on Steam.
		- [Brave Search extended with Ask Brave](https://alternativeto.net/news/2025/9/brave-launches-ask-brave-ai-chat-search-with-privacy-and-multimedia-answers/) - gives longer answers, with web citations. Can also be triggered via search plugin when appending `??`
		- Use LLMs to generate Anki flashcards of stuff I want to learn e.g. my code snippets
		- [Free web LLM access sites](https://wuu73.org/blog/aiguide1.html)
		- [MCP Registry](https://github.com/mcp) by GitHub
		- ### AI agents
		  collapsed:: true
			- AI agents can be assigned GitHub issues which you can then review and approve on your phone when it's done
			  collapsed:: true
				- Cursor has web-based background agents
				- You can set up hooks: https://docs.anthropic.com/en/docs/claude-code/hooks-guide. And use something like ntfy to get notifications on your phone. I’ve also seen people assign Claude code issues on GitHub and then use the GitHub mobile app on their phone to get notifications and review PRs.
			- Claude Code leveraging
			  collapsed:: true
				- [opcode](https://github.com/getAsterisk/opcode) - desktop companion for Claude Code
				- [Write docs beforehand](https://news.ycombinator.com/item?id=44836879)
				- Try Claude Code for terminal issues e.g. why PC sometimes freezes or process takes up too much CPU
				- Monolithic with docker orchestration: I essentially 10x'd when I started letting Claude itself manage docker containers, check their logs for errors, rm them, rebuild them, etc. Now I can get an entirely new service online in a docker container, from zero to operational, in one Claude prompt.
				- 5. it's not just docker, give it playwright MCP server so it can see what it is implementing in UI and requests
					- Or just `$ playwright`. Skip the MCP ceremony (and wasted tokens) and just have CC use CLI tools. Works remarkably well.
				- Use agents to validate the code. Is it over engineered, does it conform to conventions and spec, is it actually implemented or half bullshit. I run three of these at the end of a feature or task and it almost always send Opus back to the workbench fixing a bunch of stuff. And since they have their own context, you don't blow up the main context and can go for longer.
				- [Learning Resources]
					- [6 weeks of Claude Code | Hacker News](https://news.ycombinator.com/item?id=44746621)
					-
			- [GitHub - openai/agents.md: AGENTS.md — a simple, open format for guiding coding agents](https://github.com/openai/agents.md)
				- Though this should have been a directory with an `index.md` which has includes to multiple files/dirs in the same dir
			- [How I'm using coding agents in September, 2025](https://blog.fsck.com/2025/10/05/how-im-using-coding-agents-in-september-2025/)
			- [It’s also become clear to me that [agentic AI] LLMs actively reward existing top tier software engineering practices:](https://simonwillison.net/2025/Oct/7/vibe-engineering/)
			  collapsed:: true
				- **Automated testing**. If your project has a robust, comprehensive and stable test suite agentic coding tools can _fly_ with it. Without tests? Your agent might claim something works without having actually tested it at all, plus any new change could break an unrelated feature without you realizing it. Test-first development is particularly effective with agents that can iterate in a loop.
				- **Planning in advance**. Sitting down to hack something together goes much better if you start with a high level plan. Working with an agent makes this even more important—you can iterate on the plan first, then hand it off to the agent to write the code.
				- **Comprehensive documentation**. Just like human programmers, an LLM can only keep a subset of the codebase in its context at once. Being able to feed in relevant documentation lets it use APIs from other areas without reading the code first. Write good documentation first and the model may be able to build the matching implementation from that input alone.
				- **Good version control habits**. Being able to undo mistakes and understand when and how something was changed is even more important when a coding agent might have made the changes. LLMs are also fiercely competent at Git—they can navigate the history themselves to track down the origin of bugs, and they’re better than most developers at using [git bisect](https://til.simonwillison.net/git/git-bisect). Use that to your advantage.
				- Having **effective automation** in place. Continuous integration, automated formatting and linting, continuous deployment to a preview environment—all things that agentic coding tools can benefit from too. LLMs make writing quick automation scripts easier as well, which can help them then repeat tasks accurately and consistently next time.
				- A **culture of code review**. This one explains itself. If you’re fast and productive at code review you’re going to have a much better time working with LLMs than if you’d rather write code yourself than review the same thing written by someone (or something) else.
				- A **very weird form of management**. Getting good results out of a coding agent feels uncomfortably close to getting good results out of a human collaborator. You need to provide clear instructions, ensure they have the necessary context and provide actionable feedback on what they produce. It’s a _lot_ easier than working with actual people because you don’t have to worry about offending or discouraging them—but any existing management experience you have will prove surprisingly useful.
				- Really good **manual QA (quality assurance)**. Beyond automated tests, you need to be really good at manually testing software, including predicting and digging into edge-cases.
				- Strong **research skills**. There are dozens of ways to solve any given coding problem. Figuring out the best options and proving an approach has always been important, and remains a blocker on unleashing an agent to write the actual code.
				- The ability to **ship to a preview environment**. If an agent builds a feature, having a way to safely preview that feature (without deploying it straight to production) makes reviews much more productive and greatly reduces the risk of shipping something broken.
				- An instinct for **what can be outsourced** to AI and what you need to manually handle yourself. This is constantly evolving as the models and tools become more effective. A big part of working effectively with LLMs is maintaining a strong intuition for when they can best be applied.
				- An updated **sense of estimation**. Estimating how long a project will take has always been one of the hardest but most important parts of being a senior engineer, especially in organizations where budget and strategy decisions are made based on those estimates. AI-assisted coding makes this _even harder_—things that used to take a long time are much faster, but estimations now depend on new factors which we’re all still trying to figure out.
			- [Designing agentic loops](https://simonwillison.net/2025/Sep/30/designing-agentic-loops/)
			- A better term is agentic coding, agentic software engineering, etc. rather than being vibe based.
				- My process starts from a Claude Code plan, whose first step is to write a spec. I use TDD, and enforce my "unspoken rules of code quality" using a slew of generated tools. One tiny tool blocks code which violates our design system. Another tool blocks code which violates our separation of layering - this forces the HTTP route handler code to only access the database via service layer. Watching the transcript I have to occasionally remind the model to use TDD, but once it's been reminded it doesn't need reminding again until compaction. Claude 4.5 is far better at remembering to do TDD than 4.1 was.
				- Code reviews are super simple with TDD due to the tests mirroring the code. I also create a simple tool which hands the PR and spec to Gemini and has it describe any discrepancies: extra stuff, incorrect stuff, or missing stuff. It's been great as a backup.
		- [JetBrains has announced a collaboration with Zed to co-develop](https://alternativeto.net/news/2025/10/jetbrains-will-collaborate-with-zed-to-bring-the-agent-client-protocol-acp-to-their-ides/) the [Agent Client Protocol (ACP)](https://alternativeto.net/software/agent-client-protocol/about/), a protocol designed to streamline how code editors and intelligent agents interact
			- The protocol itself separates agents from editors. Developers build a single [ACP](https://alternativeto.net/software/agent-client-protocol/about/) implementation, ensuring compatibility with any editor that adopts the protocol. This reduces the need for repeated custom integrations and eliminates vendor lock-in for users, enabling agents of choice within familiar development environments.
		- [Google launches Gemini CLI Extensions with public GitHub ecosystem and major partners | AlternativeTo](https://alternativeto.net/news/2025/10/google-launches-gemini-cli-extensions-with-public-github-ecosystem-and-major-partners/)
		  collapsed:: true
			- [Gemini CLI Extensions | Gemini CLI](https://geminicli.com/extensions/)
		-
	- ### Docker
	  collapsed:: true
		- Overriding a Docker image's entrypoint and getting shell access inside
		  id:: 68e4de6b-fb1a-4cf4-949a-7bea4d8629f5
			- `docker run -it --rm --entrypoint /bin/sh <image_name>`
		- Examining the entrypoint of an image
		  collapsed:: true
			- `docker inspect <image_name>`
				- This outputs a JSON object describing the image. The fields we care about are:
					- **`Config.Entrypoint`** → The main executable that always runs (like a script or binary)
					- **`Config.Cmd`** → Default arguments passed to the ENTRYPOINT (or standalone if ENTRYPOINT is empty)
				- Example
					- ```json
					  "Config": {
					      "Entrypoint": ["/usr/local/bin/markdown_to_pdf"],
					      "Cmd": ["document.md"]
					  }
					  ```
				- We can then ((68e4de6b-fb1a-4cf4-949a-7bea4d8629f5)) in order to `cat` the script
		- `docker` setup
		  collapsed:: true
			- `sudo usermod -aG docker ${USER}` = add your user to the `docker` group
				- Can be checked with `groups`
				- Restart WSL session or terminal for this to take effect
			- WSL - setup sharing of the Docker daemon between WSL distros
				- `sudo groupmod -g 36527 docker` = set a common ID for the `docker` group to enable sharing
				- Prepare a shared directory for your Docker socket
					- `DOCKER_DIR=/mnt/wsl/shared-docker`
					- `mkdir -pm o=,ug=rwx ${DOCKER_DIR`
					- `sudo chgrp docker ${DOCKER_DIR}`
				- Configure the Docker daemon to use the shared socket by creating a config file at `/etc/docker/daemon.json` with the following content:
					- ```
					  {
					  	"hosts": ["unix://mnt/wsl/shared-docker/docker.sock"]
					  }
					  ```
			- To automatically launch the Docker daemon on login, add the login to your `~/.bashrc` file, updating the `distro-name` to the correct version of Ubuntu e.g. `Ubuntu-22.04`
			  collapsed:: true
				- ```bash
				  DOCKER_DISTRO=<your-distro-name>
				  DOCKER_DIR=/mnt/wsl/shared-docker
				  DOCKER_SOCK=${DOCKER_DIR}/docker.sock
				  export DOCKER_HOST=unix://${DOCKER_SOCK}
				  if [ ! -S "${DOCKER_SOCK}" ]; then
				    mkdir -pm o=,ug=rwx "${DOCKER_DIR}"
				    chgrp docker "${DOCKER_DIR}"
				    /mnt/c/Windows/System32.wsl.exe -d ${DOCKER_DISTRO} sh -c "nohup sudo -b dockerd < /dev/null > ${DOCKER_DIR}/dockerd.log 2>&1"
				  fi  
				  ```
			- Grant passwordless access to `dockerd`
				- `sudo visudo`
					- Add the following line:
					  `%docker ALL=(ALL) NOPASSWD: /usr/bin/dockerd`
			- Checking docker is functional
				- `docker run --rm hello-world`
		- `docker rmi -f image-name` = delete the build, but when you rebuild it'll use the cached layers
		- `docker rmi $(docker images -q) -f && docker system prune` 
		  Wipe all Docker images
		- Docker bake - like multi-stage builds except it uses multiple Dockerfiles, and it uses `.hcl`
			- to be able to build artifacts from one in another
	- Build pipeline
	  collapsed:: true
	- ((68d10df3-028b-47d9-951d-3cc0be11e2ad))
	- VSCode
	  collapsed:: true
		- Recommended extensions
			- `bierner.markdown-mermaid` = live previews of mermaid-js diagrams
			- `hediet.vscode-drawio` = edit draw.io diagrams
			- `esbenp.prettier-vscode` = autoformat the Markdown you write
			- [Markdown annotated-hexdumps - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=EdwardWoolhouse.md-annotated-hexdumps)
				- Built on [GitHub - danishcake/marked-annotated-hexdump: A markedjs extension for creating annotated hex dumps](https://github.com/danishcake/marked-annotated-hexdump)
			- [Multimarkdown tables for VSCode - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=EdwardWoolhouse.multimarkdown-tables-vsc)
				- Built on [GitHub - fletcher/MultiMarkdown-6: MultiMarkdown-7 is now in pre-release development here on GitHub](https://github.com/fletcher/MultiMarkdown-6) - recommended for less verbose and more featureful tables
				  collapsed:: true
					- Alpha: [GitHub - fletcher/MultiMarkdown-7: Lightweight markup processor to produce HTML, LaTeX, and more. Currently in pre-release.](https://github.com/fletcher/MultiMarkdown-7)
		-
	- ### WSL
	  collapsed:: true
		- `ipconfig` on Windows host (e.g. PowerShell) can be used to find the Windows host IP
			- Look at the `Internet adapter vEthernet (WSL)` line - `IPv4 Address`
		- VSCode
			- To install plugins into WSL DevContainers drag-and-drop a VSIX into the plugins pane from an Explorer folder window
	- ### Windows
	  collapsed:: true
		- Getting it's IP address
			- ```
			  # cmd
			  ipconfig
			  
			  # or PowerShell (nicely filtered)
			  Get-NetIPAddress -AddressFamily IPv4 |
			    Where-Object { $_.IPAddress -notlike '169.*' -and $_.IPAddress -ne '127.0.0.1' } |
			    Select-Object IPAddress, InterfaceAlias
			  ```
	- ((68d55ad7-1ebe-4d15-8286-b4daa26f035f))
	- ### VMs
	  collapsed:: true
		- `ip addr` from within guest to find out the IP address
			- `ip addr show dev eth1` specifically
		- `hostname -I` from within guest to find out it's IP address
		- `ip a s` =
		- Passing data between host and guest
			- `python3 -m http.server` to host a directory then using browser/curl/wget to download files (possible putting them in a `tar` beforehand)
			- VirtualBox - install Guest Additions. Allows you to use Shared Folders feature
			- `scp` or `rsync`
		- Setting the machine's IP
			- Viewing: `ip addr show`
			- Temporary until reboot: `ip addr add <ip/prefix> dev `
				- e.g. `ip addr add 192.168.56.101/24 dev enp0s8`
			- Permanent: edit `/etc/netplan/something.yaml`
				- ```yaml
				  network:
				    version: 2
				    renderer: NetworkManager
				    ethernets:
				      enp0s8:
				        dhcp4: no
				        addresses:
				          - 192.168.56.101/24
				        gateway4: 192.168.56.1      # optional (only if you want internet through it)
				        nameservers:
				          addresses: [8.8.8.8, 1.1.1.1]
				  ```
- Group
  collapsed:: true
	- Documentation
	  collapsed:: true
		- https://docs.mathjax.org for displaying equations using LaTeX or others
		- [xyChart](https://mermaid.js.org/syntax/xyChart.html) for simple charts
	- [GitHub - slopus/happy: Mobile and Web client for Claude Code, with realtime voice, encryption and fully featured](https://github.com/slopus/happy)
	- [Writing good design documents](https://news.ycombinator.com/item?id=44779428)
	- System design
	  collapsed:: true
		- WC project scripts
		  collapsed:: true
			- `build.sh`
			  collapsed:: true
				- ```bash
				  #!/bin/bash
				  
				  # Usage:
				  # 
				  # ./build.sh [CONFIG]
				  #
				  # Build PROJECT using build configuration [CONFIG]
				  # 
				  # Positional arguments:
				  #	CONFIG		build configuration (debug|release)
				  
				  set -e
				  
				  # A safety feature to prevent this from running in WSL
				  if `[ -f /.dockerenv ]`; then
				  	echo "ERROR: This run script must be run from WSL."
				      exit 1
				  fi
				  
				  SCRIPT_DIR=$(realpath $(dirname ${0}))
				  PROJECT_ROOT=$(realpath $(dirname ${SCRIPT_DIR}))
				  
				  echo "Building the module1..."
				  ${SCRIPT_DIR}/module1/build.sh
				  
				  echo "Building the module2..."
				  ${SCRIPT_DIR}/module2/build.sh
				  
				  echo "Copying the outputs to ${OUTPUT_FOLDER}..."
				  ```
			- `.gitlab.ci.yml`
			  collapsed:: true
				- ```yaml
				  stages:
				    - lint
				    - test
				    - build
				  
				  variables:
				    ROOT_DIR: project-name
				    FRONTEND_DIR: ${ROOT_DIR/web-frontend
				  
				  default:
				  	image: docker:24.0.5
				      services:
				      	- name: docker:24.0.5-dind
				          command:
				          - /bin/sh
				          - -c
				          - echo "hello world"
				      before_script:
				      	- echo 1
				          - echo 2
				  
				  lint-web-frontend:
				  	stage: lint
				      image: python:3.13.1
				      before_script:
				      	- echo 1
				          - echo 2
				      script:
				      	- echo 3
				      allow_failure: false
				  ```
			- `wc/device-monitoring/tests/unit testing`
			  collapsed:: true
				- ((68ef9075-fab2-48c2-bf1b-3bf4cccbb59b))
			- `wc/device-monitoring/build.sh`
			  collapsed:: true
				- ```bash
				  #!/bin/bash
				  
				  # Usage:
				  # 
				  # ./build.sh
				  #
				  # Build the field device device monitor.
				  
				  set -e
				  
				  OUTPUT_NAME=monitor-devices
				  
				  # A safety feature to prevent this from running in WSL
				  if `[ -f /.dockerenv ]`; then
				  	echo "ERROR: This run script must be run from WSL."
				      exit 1
				  fi
				  
				  CWD=$(cwd)
				  SCRIPT_DIR=$(realpath $(dirname ${0}))
				  PROJECT_ROOT=$(realpath $(dirname ${SCRIPT_DIR}))
				  
				  # Install build time debs
				  sudo dpkg -i ${SCRIPT_DIR}/.deb/pyinstall/*.deb || dpkg -i ${SCRIPT_DIR}/.deb/pyinstall/*.deb
				  
				  python3 -m venv ${SCRIPT_DIR}/.venv
				  source ${SCRIPT_DIR}/.venv/bin/activate
				  
				  python3 -m pip install --no-index \
				  	--find-links ${SCRIPT_DIR}/.pip/ppadb \
				  	-r ${SCRIPT_DIR}/requirements-ppadb.txt
				  python3 -m pip install --no-index \
				  	--find-links ${SCRIPT_DIR}/.pip/ppadb \
				  	-r ${SCRIPT_DIR}/requirements-pyinstaller.txt
				  python3 -m pip install --no-index \
				  	--find-links ${SCRIPT_DIR}/.pip/ppadb \
				  	-r ${SCRIPT_DIR}/requirements-pytest.txt
				  pip install -e ${SCRIPT_DIR} --no-build-isolation --no-index
				  
				  pyinstaller -F ${SCRIPT_DIR}/src/main.py \
				  	--distpath ${SCRIPT_DIR}/dist
				      --specpath ${SCRIPT_DIR} \
				      --workpath ${SCRIPT_DIR}/build \
				      --name ${OUTPUT_NAME}
				      
				  # Clean up the build artefacts
				  rm --recursive ${SCRIPT_DIR}/build/
				  rm ${SCRIPT_DIR}/${OUTPUT_NAME}.spec
				  ```
			- `wc/device-monitoring/test.sh`
			  collapsed:: true
				- ```bash
				  set -e
				  
				  # A safety feature to prevent this from running in WSL
				  if `[ -f /.dockerenv ]`; then
				  	echo "ERROR: This run script must be run from WSL."
				      exit 1
				  fi
				  
				  SCRIPT_DIR=$(realpath $(dirname ${0}))
				  PROJECT_ROOT=$(realpath $(dirname ${SCRIPT_DIR}))
				  
				  main() {
				  	python3 -m venv ${SCRIPT_DIR}/env
				      source ${SCRIPT_DIR}/env/bin/activate
				      
				      python3 -m pip install --no-index \
				      	--find-links ${SCRIPT_DIR}/.pip/ppadb \
				          -r ${SCRIPT_DIR}/requirements-ppadb.txt
				      python3 -m pip install --no-index \
				      	--find-links ${SCRIPT_DIR}/.pip/pytest \
				          -r ${SCRIPT_DIR}/requirements-pytest.txt
				      pip install -e ${SCRIPT_DIR} --no-build-isolation --no-index --no-deps
				     	python3 -m pytest ${SCRIPT_DIR}/tests/test_unit_device_monitor.py -v
				      
				      deactivate
				      
				  }
				  
				  main
				  ```
			- `wc/?/install.sh`
			  collapsed:: true
				- ```bash
				  #!/bin/bash
				  
				  # A script to complete x install. 
				  # This scrip tmust be run with sudo.
				  
				  if [[ ${EUID} -ne 0 ]]; then
				  	echo "ERROR: This script must be run with sudo"
				      exit 1
				  fi
				  
				  USER_HOME=$(getent passwd ${SUDO_USER} | cut -d: -f6)
				  SCRIPT_DIR=$(realpath $(dirname ${0}))
				  
				  install() {
				  	# Runs the install in the correct order.
				      
				      create_configuration_directory /opt/fd
				      
				      disable_system_logging
				      
				      echo "Install finished!"
				  }
				  
				  create_configuration_directory() {
				  	CONFIG_DIR=$1
				      mkdir -p ${CONFIG_DIR}
				  }
				  
				  disable_system_logging() {
				  	echo "disbling"
				  }
				  
				  install
				  ```
		- [Good system design | Hacker News](https://news.ycombinator.com/item?id=44921137)
		- Modules which solely handle backend logic when they raise errors and throws an exception it should just be a descriptive title like `MicrophoneUnavailableError`. Leave it up to the frontend modules to catch these exceptions and determine the suitable more detailed error messages to display to a user
	- Firefox search engines in the address bar
	  collapsed:: true
		- Like with the optional search box, you can add keywords to search queries in order to use that search engine instead e.g. `@google` for Google, `@tabs, %` for Tabs means you can use either to search through your tabs, etc
			- You have to prefix `<keyword><whitespace>` in order to switch
			-
	- Terminal keybindings
	  collapsed:: true
		- https://keycombiner.com/collections/terminal/
		- Note: should see if there's a way to change this to vim-style, so that I can have same set of keybindings in terminal + VSCode editor + logseq + thunderbird etc
		- default key-bindings: `/etc/inputrc`
		- custom key-bindings: `~/.inputrc`
	- [Whispering](https://github.com/epicenter-md/epicenter/tree/main/apps/whispering) - STT
	- [zedless](https://github.com/zedless-editor/zed) - zork of zed, without opt-out AI for example
	  collapsed:: true
		- > I’m gradually removing all the features I deem undesirable: telemetry, auto-updates, proprietary cloud-only AI integrations, reliance on node.js, auto-downloading of language servers, upsells, the sign-in button, etc. I’m also aiming to make some of the cloud-only features self-hostable where it makes sense, e.g. running Zeta edit predictions off of your own llama.cpp or vLLM instance. It’s currently good enough to be my main editor, though I tend to be a bit behind on updates since there is a lot of code churn and my way of modifying the codebase isn’t exactly ideal for avoiding merge conflicts. To that end I’m experimenting with using tree-sitter to automatically apply AST-level edits, which might end up becoming a tool that can build customizable “unshittified” versions of Zed.
		- zed has a CLA, AI features with opt-out not opt-in, sign-in, is VC funded. All likely to make it enshittified eventually
	- Virtual Desktop Infrastructure (VDI)
	  collapsed:: true
		- Related to VPNs but distinct
		- **What it is:** VDI hosts desktop environments on centralized servers in data centers or the cloud. Users access virtual desktops remotely via thin clients or apps.
		- **How it works:** Full desktops (OS, apps, data) run on servers; users interact remotely via protocols (e.g., PCoIP, RDP).
		- Providers
			- VMware Horizon (VMware)
			- Citrix Virtual Apps and Desktops (Citrix)
			- Microsoft Remote Desktop Services (RDS) / Azure Virtual Desktop (Microsoft)
			- Nutanix Frame (Nutanix)
			- Amazon WorkSpaces (AWS)
	- [Go is still not good](https://news.ycombinator.com/item?id=44982491)
	- [Reducing cognitive load in your coding style](https://github.com/zakirullin/cognitive-load)
	  collapsed:: true
		- Intermediate variables > complex conditionals
		  collapsed:: true
			- Complex conditionals
				- ```go
				  if val > someConstant // 🧠+
				      && (condition2 || condition3) // 🧠+++, prev cond should be true, one of c2 or c3 has to be true
				      && (condition4 && !condition5) { // 🤯, we are messed up by this point
				      ...
				  }
				  ```
			- Introduce intermediate variables with meaningful names:
				- ```go
				  isValid = val > someConstant
				  isAllowed = condition2 || condition3
				  isSecure = condition4 && !condition5 
				  // 🧠, we don't need to remember the conditions, there are descriptive variables
				  if isValid && isAllowed && isSecure {
				      ...
				  }
				  ```
		- Early returns > nested Ifs
		  collapsed:: true
			- Nested Ifs
				- ```go
				  if isValid { // 🧠+, okay nested code applies to valid input only
				    if isSecure { // 🧠++, we do stuff for valid and secure input only
				        stuff // 🧠+++
				    }
				  } 
				  ```
			- Compare it with the early returns:
				- ```go
				  if !isValid
				    return
				  
				  if !isSecure
				    return
				  - // 🧠, we don't really care about earlier returns, if we are here then all good
				  - stuff // 🧠+
				  ```
		- Composition > Inheritance
		  collapsed:: true
			- Inheritance
				- `AdminController extends UserController extends GuestController extends BaseController` means you have to look through many classes to find the functionality. I found this issue very problematic in my reverse tethering merge request - yumechan's adb library uses lots of subclasses
			- Composition
				- e.g. ((68d401e5-e7c5-46c3-bf8e-01baeef7a4a8))
		- Fewer, deeper, larger > too many small methods/classes/modules
		  collapsed:: true
			- It's a lot of cognitive load to keep in mind all the relationships between different interfaces
			- > The best components are those that provide powerful functionality yet have a simple interface.
			  *John Ousterhout, A Philosophy of Software Design*
			- The interface of the UNIX I/O is very simple. It has only five basic calls:
				- ```
				  open(path, flags, permissions)
				  read(fd, buffer, count)
				  write(fd, buffer, count)
				  lseek(fd, offset, referencePosition)
				  close(fd)
				  ```
			- This deep module example is taken from the book [A Philosophy of Software Design](https://web.stanford.edu/~ouster/cgi-bin/book.php) by John Ousterhout. Not only does this book cover the very essence of complexity in software development, but it also has the greatest interpretation of Parnas' influential paper [On the Criteria To Be Used in Decomposing Systems into Modules](https://www.win.tue.nl/~wstomv/edu/2ip30/references/criteria_for_modularization.pdf). Both are essential reads. Other related readings: [A Philosophy of Software Design vs Clean Code](https://github.com/johnousterhout/aposd-vs-clean-code), [It's probably time to stop recommending Clean Code](https://qntm.org/clean), [Small Functions considered Harmful](https://copyconstruct.medium.com/small-functions-considered-harmful-91035d316c29).
		- A well-crafted monolith with truly isolated modules is often much more flexible than a bunch of shallow microservices e.g. Linux vs microkernel GNU Hurd
		- Avoid tight-coupling with a framework
		  collapsed:: true
			- By relying too heavily on a framework, we force all upcoming developers to learn that "magic" first. It can take months.
			- Doesn't mean invent everything from scratch - instead write in a somewhat framework-agnostic way
				- The business logic should not reside within a framework; rather, it should use the framework's components. Put a framework outside of your core logic. Use the framework in a library-like fashion. This would allow new contributors to add value from day one, without the need of going through debris of framework-related complexity first.
		- [Use good abstractions, otherwise they just become indirection](https://fhur.me/posts/2024/thats-not-an-abstraction)
		  collapsed:: true
			- What makes a good abstraction?
				- An abstraction is only as good as its ability to hide the complexity of what lies underneath. Think of a truly great abstraction, like TCP. TCP helps us pretend that we have a reliable communication channel, even though it's built on top of an unreliable protocol, IP. It takes on the complexity of error correction, retransmission, and packet sequencing so that we don't have to. And it does such a good job that, as developers, we very rarely have to peek into its inner workings. When was the last time you had to debug TCP at the level of packets? For most of us, the answer is never.
				- That’s the sign of a great abstraction. It allows us to operate as if the underlying complexity simply doesn't exist. We take advantage of the benefits, while the abstraction keeps the hard stuff out of sight, out of mind.
			- Bad ones are often thin layers over a function, that just make a system more difficult to trace, debug and understand
			- All abstractions leak
				- There’s a well-known saying: "All abstractions leak." It’s true. No matter how good the abstraction, eventually, you’ll run into situations where you need to understand the underlying implementation details. This leakage might be subtle—like when you’re trying to understand the performance characteristics (what’s the big O complexity here?)—or it could be more blatant, requiring you to dive deep into debugging to figure out why something isn’t working as expected. A good abstraction minimizes these situations; a bad one turns every small bug into an excavation.
				-
	- Konsole, Yakuake (built on Konsole), Ghostty etc are all terminal **emulators** since they're software apps which mimics the functionality of traditional hardware terminals
	- [Google launches Chrome DevTools MCP allowing AI agents to debug, automate & test in Chrome | AlternativeTo](https://alternativeto.net/news/2025/9/google-launches-chrome-devtools-mcp-allowing-ai-agents-to-debug-automate-and-test-in-chrome/) it's a MCP server that allwos AI agents to connect to a Google Chrome browser
	- Docker on Windows/WSL
	  collapsed:: true
		- Installing Docker Desktop for Windows whilst you have WSL2 installed will automatically install `docker` in your Ubuntu WSL
	- How to get a Bash script to only run in WSL, but not DevContainers
	  collapsed:: true
		- ```bash
		  if `[ -f /.dockerenv ]`; then
		  	echo "ERROR: This run script must be run from WSL."
		      exit 1
		  fi
		  ```
	- Language-specific developer surveys
	  collapsed:: true
		- [Python Developers Survey 2024 Results](https://lp.jetbrains.com/python-developers-survey-2024/)
	- `systemd`
	  id:: 68d5437d-a485-42a9-b4a6-e3548168ef55
	  collapsed:: true
		- How to search logs
			- `journalctl`
				- `-u <service>` e.g. `journalctl -u nginx`
			- `/var/log/syslog` file contains many messages including systemd. Especially useful if piped to grep
		- `sudo usermod -aG systemd-journal <yourusername>` = grants you admin-level read access of `journalctl`
			- Also note you need to relogin for the changes to take effect
		- `systemctl cat <service-name>` = display the service file path and its contents
		- ### Creating `.service` files
			- Example
				- ```
				  [Unit]
				  Description=Android Debug Bridge
				  
				  [Service]
				  Type=simple
				  ExecStart=adb -a server nodaemon
				  Restart=always
				  TimeoutStartSec=infinity
				  
				  [Install]
				  WantedBy=multi-user.target
				  ```
			- How to get services to only start after another service
			  id:: 68de8e04-3387-4015-bd75-bb36bc426924
				- In your dependent service, where `primary.service` is the service to be active first:
				  ```
				  [Unit]
				  Description=Example
				  Requires=primary.service
				  After=primary.service
				  ```
			- Using `systemd-notify` to custom trigger when dependent services start
			  id:: 68de8e5f-d061-4efe-8efd-e25cd1049008
			  i.e. when ((68de8e04-3387-4015-bd75-bb36bc426924)) doesn't give enough delay (<1 second from service start) and you need to instead depend on a later output
				- Write a wrapper script for your primary service which uses `systemd-notify` to let `systemd` know that the service is not only starting, but now is started/ready
					- `adb-wrapper.sh`
					  ```bash
					  #!/bin/bash
					  # Wrapper for adb server to notify systemd when ready
					  
					  # Start adb in background
					  adb -a server nodaemon &
					  ADB_PID=$!
					  
					  # Wait until adb responds to `adb devices`, not just the command failing
					  until adb devices >/dev/null 2>&1; do
					  	sleep 1
					  done
					  
					  # Notify systemd that the service is ready
					  systemd-notify --ready
					  echo "adb service is ready"
					  
					  # Wait for the adb process to exit so system tracks it
					  wait $ADB_PID
					  ```
				- Use a systemd service to execute the wrapper script. It should also have `Type=notify` and `NotifyAccess=all`
					- ```
					  [Unit]
					  Description=Android Debug Bridge
					  
					  [Service]
					  Type=notify
					  ExecStart=/lib/systemd/system/adb-wrapper.sh
					  NotifyAccess=all
					  Restart=always
					  
					  [Install]
					  WantedBy=multi-user.target
					  ```
				- Make your second systemd service with `Requires` and `After` on your initial service
					- ```
					  [Unit]
					  Description=Device Monitoring
					  
					  [Service]
					  StandardOutput=journal
					  StandardError=journal
					  Type=simple
					  ExecStart=/usr/local/bin/monitor-devices
					  Restart=always
					  RestartSec=5
					  TimeoutStartSec=infinity
					  
					  [Install]
					  WantedBy=multi-user.target
					  ```
	- `adb`
	  id:: 68d55ad7-1ebe-4d15-8286-b4daa26f035f
	  collapsed:: true
		- Android emulator
			- To connect to Android console
				- `telnet localhost 5554` or `nc localhost 5554`
				- In Android console
					- [Send emulator console commands  |  Android Studio  |  Android Developers](https://developer.android.com/studio/run/emulator-console) for docs
					-
					- `help` = list all commands
					- `sensor status` = list all sensors and their status
		- `adb shell`
			- `dumpsys battery get temp`
		- Connecting Android devices into WSL
			- `platform-tool-latest-windows` needed
			- `.\adb -a nodaemon server` to run the server from Windows
				- or just `adb -a nodaemon server` if `adb` is already in PATH (just using `adb` executes it)
			- In WSL `nano ~/.bashrc`
				- ```
				  export ADB_SERVER_ADDRESS_REMOTE=${netsh.exe interface ip show config "vEthernet (WSL)" | grep -Po 'IP Address: *\K([0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3})'}
				  export ADB_SERVER_PORT_REMOTE=5037
				  export ADB_SERVER_SOCKET_REMOTE=tcp:${ADB_SERVER_ADDRESS_REMOTE}:${ADB_SERVER_PORT_REMOTE}
				  ```
			- `source ~/.bashrc`
			- Then you can execute `adb -L ${ADB_SERVER_SOCKET_REMOTE} devices` for example
		- Troubleshooting
			- Why APK is crashing
				- `adb logcat`
			-
	- `socat`
	  collapsed:: true
		- Using this to port forward Android emulator on port 5554 to 5555 for (?) which we then `adb connect <WSL-IP-ADDRESS>:5555` from within the VM
			- ```bash
			  socat TCP-LISTEN:5555,bind=$(hostname -I | cut -d ' ' -f1) TCP:localhost:5555
			  ```
	- Vagrant
	  collapsed:: true
		- Obtaining the IP address of one
			- `vagrant global-status` = get the status of all Vagrant boxes, including their ID number
			- `vagrant ssh-config <the-box-id>` e.g. `vagrant ssh-config 121t4dg`
				- Shows the hostname/IP address
	- An alternative to the word "auth" - which is commonly used for both authentication + authorisation despite them being quite different - instead use "login" for authentication and "permissions" for authorization
	  collapsed:: true
		- e.g. a login library vs a permissions management library
	- Funny fictional allegory about [why frameworks can suck](https://minds.md/benji/frameworks)
	- [GitHub - simonhaenisch/md-to-pdf: Hackable CLI tool for converting Markdown files to PDF using Node.js and headless Chrome.](https://github.com/simonhaenisch/md-to-pdf) - useful for writing documentation
	- helix vs kakoune vs neovim
	  collapsed:: true
		- [Helix: A Neovim inspired editor, written in Rust | Hacker News](https://news.ycombinator.com/item?id=33147270)
			- the paradigm change from verb-noun to noun-verb
				- It switches from "action selection" to "selection action" which allows you to first select the thing you want to operate on and only then specify what you want do with it. So for example in Vim you may accidentally select too many characters to delete and then you need to redo the command whereas in Kakoune you can adjust the selection before executing the action.
				- I think one of the best things Kakoune has to offer is that selection mode (visual mode in Vim) is always accessible through <shift><movement> so if I want to select some random number of characters going left, I'll just hold L, or if I want to select all characters until the end of line I'll just press GL whereas gl takes me to the end of line. It makes it so easy to select text.
				- > selection action is already possible in vim using 'v' or 'V'. But many times, I do want immediate action-operator when I know exactly what I need to operate on. So Kakoune is un-convincing.
					- This argument doesn't make sense, it's just as fast to type in Kakoune. The order is just different but it makes it possible for you to adjust it when you've either made a mistake or don't exactly know what kind of selection you want.
					- I know the visual mode in Vim exists under 'v' but the point I was making was that in Kakoune it's more handy and I use it constantly because it's so available, just hold Shift key as oppose typing another letter to enter it. I know it sounds insignificant but I find myself using the visual mode all the time in Kakoune whereas I barely used it in Vim because of that tiny extra effort to enter the mode.
				- Helix combines elements of both Vim and Kakoune. Like Kakoune, it uses a selection-first editing model, allowing users to see what they are about to modify before executing an action.
		- [Are we Helix yet? · zed-industries/zed · Discussion #33580 · GitHub](https://github.com/zed-industries/zed/discussions/33580)
		-
- Group
  collapsed:: true
	- [Multiple kernels](https://www.phoronix.com/news/Linux-Parker-Proposal) as an evolution to container technology has two experimental implementations now in 2025
	- use `sonarqube` vscode extension for teaching best practices
	- [GitHub - Chalarangelo/30-seconds-of-code: Coding articles to level up your development skills](https://github.com/Chalarangelo/30-seconds-of-code)
	  collapsed:: true
		- Snippets and articles e.g. https://github.com/Chalarangelo/30-seconds-of-code/blob/master/content/snippets/js/s/10-vs-code-extensions-for-js-developers.md
		- [Article collections](https://www.30secondsofcode.org/collections/p/1/)
	- Composition vs Inheritance
	  id:: 68d401e5-e7c5-46c3-bf8e-01baeef7a4a8
	  collapsed:: true
		- [The Flaws of Inheritance](https://www.youtube.com/watch?v=hxGOiiR9ZKg)
			- Composition example
				- Instead of subclasses, have independent classes (i.e. no `extends`). The methods that were in your subclass instead takes a parent class instance as a **parameter**
			- Interfaces are better than subclassing, because they only define the critical parts of the functionality rather than subclassing which inherits everything by default
	- SOLID
- Group
  collapsed:: true
	- Writing Documentation
	  collapsed:: true
		- If it's a tutorial, watch a newbie go through it without saying anything, whilst noting down where you could improve it. Then repeat with a new user
		- In README you should describe exactly what a tool is for, and ideally compare it against other competing tools
	- `dpkg -l | grep <package-name>` = check if a package is installed
	- `dpkg -i something.deb` = install a DEB package
	- Windows 11 keybindings
	  collapsed:: true
		- `Meta + Tab` = Overview/Virtual Desktops
		- `Meta + `
	- `sudo !!` = repeat previous command but prefix `sudo`
	- Windows 11 avoid Microsoft account setup
	  collapsed:: true
		- For those who care at the first setup screen instead of answering any of the questions press Shift + F10
		- CMD will open
		- Type (no quotes) “net user Prefferedusername /add” (replacing Prefferedusername with the user name you wish to use) and press enter.
		- Next type “net localgroup administrators Prefferedusername /add” and press enter.
		- Next type “net user Prefferedusername /active:yes” and press enter.
		- Next type “net user Prefferedusername /expires:never” and press enter.
		- Next type “net user administrator /active:no” and press enter.
		- Next type “net user defaultUser0 /delete” (this is case sensitive make sure the "U" is capitalized) and press enter.
		- Next type "regedit" and press enter.
		- This opens registry editor, navigate to "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE"
		- Delete "DefaultAccountAction", "DefaultAccountSAMName", and "DefaultAccountSID"
		- Right click on "LaunchUserOOBE" and rename it to "SkipMachineOOBE" and make sure the value is set to "1".
		- Close registry editor and type "shutdown /r /t 0"
	- [GitHub - mrdoob/three.js: JavaScript 3D Library.](https://github.com/mrdoob/three.js/)
	- [Google style guide](https://developers.google.com/style)
	- Diagramming for understanding code
	  collapsed:: true
		- UML https://en.wikipedia.org/wiki/Class_diagram
		- Useful to use boxes for diagram in Draw.io like
			- ```
			  name-of-file.tsx
			  -----------------
			  let codeVar = {
			  	console.log("test")
			  }
			  ```
		- Also specify whether a component is part of a library or part of your own app code. Maybe colour code the boxes
	- `sed` - for easily replacing words
	  collapsed:: true
		- e.g. `sed s/click/press` = replace `click` with `press`
	- https://pwn.college/dojos for reverse engineering and ED fundamentals including kernel ED
	- Categories of tabs in work browser
	  collapsed:: true
		- [Merged] To review
			- Recent others MRs that I haven't reviewed but contain relevant code to understand
		- [My MRs] In review
		- [Issues]
			- Links to issue board, my to-do list, roadmap
		- [Others MRs] Waiting for changes
			- For MRs I've reviewed but need changes
		- [Others MRs] To review
			- Open MRs without my review yet
		- `#issue-number)` `issue-name`
		  e.g. `411) Fix the X bug`
		-
	- [Critical path method - Wikipedia](https://en.wikipedia.org/wiki/Critical_path_method)