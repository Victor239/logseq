- Keyboard shortcuts
  collapsed:: true
	- `Ctrl + C` Terminate the command
	- `Ctrl + Z` Suspend the command
	- `Ctrl + A` Move to the start of the line
	- `Ctrl + E` Move to the end of the line
	- `Ctrl + F` Move forward one character
	- `Ctrl + B` Move backward one character
	- `Ctrl + U` Delete from the cursor to the start of the line
	- `Ctrl + K` Delete from the cursor to the end of the line
	- `Ctrl + W` Delete from the cursor to the start of the word
	- `Ctrl + D` Delete the character under the cursor
	- `Ctrl + H` Delete the character before the cursor
	- `Ctrl + T` Swap the character under the cursor with the previous one
	- `Ctrl + L` Clear the screen
- `pushd` and `popd` for directory navigation
  collapsed:: true
	- Example
		- ```bash
		  pushd /etc
		  pushd /var/log
		  popd      # Returns to /etc
		  popd      # Returns to the directory you started in
		  ```
	- ascii representation of stacks
		- ```
		  # Start (just in home directory ~)
		  [~]
		  
		  # pushd /etc
		  [/etc]
		  [~]
		  
		  # pushd /var/log
		  [/var/log]
		  [/etc]
		  [~]
		  
		  # popd   (removes /var/log, returns to /etc)
		  [/etc]
		  [~]
		  
		  # popd   (removes /etc, returns to ~)
		  [~]
		  
		  ```
			- Each new directory with pushd adds to the top of the stack; each popd removes the top and reveals the next one down.
			- After each `popd`, the directory stack gets smaller and your current directory changes.[](https://linuxize.com/post/popd-and-pushd-commands-in-linux/)
	- Explanation
		- The `popd` command in Bash is used to remove the top directory from the directory stack and change the current working directory to the new top directory on the stack. It works together with `pushd`, which saves the current directory to the stack and moves to a new one. This system is especially helpful for quickly switching between multiple directories without losing your place.[](https://en.wikipedia.org/wiki/Pushd_and_popd)
		- ## Basic Usage
			- After navigating with `pushd`, use `popd` to return to the previous directory.
			- The directory stack follows a "Last In, First Out" (LIFO) rule—like a stack of plates: the last one added is the first one removed.
			- Running `popd` without arguments pops the most recent directory off the stack and switches to it.
		- ## Options
			- `popd -n` removes the top directory from the stack without changing the current directory.
			- `popd +N` or `popd -N` removes the directory at the Nth position in the stack.
			- `popd` is useful for navigation in scripts or interactive shells where frequent directory changes are needed
- `set`
  collapsed:: true
	- Common at the start of robust shell scripts
		- `set -ou pipefail`
		-
	- Flags
		- `-u`
		  collapsed:: true
		  AKA `-o nounset` / nounset / no unset variables allowed
			- Bash will treat any use of an undefined (unset) variable as an error
				- This helps catch mistakes where a variable name might be misspelled or forgotten to be initialized.
			- Example
				- Without `nounset`:
				  ```bash
				  echo $MY_VAR
				  # → prints an empty line (no error)
				  ```
				- With `nounset`:
				  ```bash
				  set -u
				  echo $MY_VAR
				  # → bash: MY_VAR: unbound variable
				  ```
		- `-o pipefail`
		  collapsed:: true
			- Normally, in a pipeline (like `cmd1 | cmd2 | cmd3`), Bash only returns the **exit code of the last command** (`cmd3`).
			- With `set -o pipefail`, the pipeline’s exit status will be **the first non-zero exit code** in the pipeline.
			- This helps catch errors earlier in a chain of piped commands.
			- Example
				- ```bash
				  false | true
				  echo $?   # Without pipefail -> 0
				  
				  set -o pipefail
				  false | true
				  echo $?   # With pipefail -> 1
				  ```
				- 2
					- Without `pipefail`
					  ```bash
					  false | echo "done"
					  echo $?
					  
					  # Output:
					  # done
					  # 0
					  ```
					- With `pipefail`
					  ```bash
					  set -o pipefail
					  false | echo "done"
					  echo $?
					  
					  # Output:
					  # done
					  # 1
					  ```
- `trap`
  collapsed:: true
	- Tells Bash to **run a command when a specific signal is received**.
	- `trap "echo 'Exiting...'; exit 1" SIGINT`
		- **`SIGINT`** is the interrupt signal — sent when you press **Ctrl + C**.
		- “When the user presses Ctrl + C, print `Exiting...` and exit with status 1.”
- Writing and utilising functions
  collapsed:: true
	- `utils.sh`
		- ```bash
		  #!/bin/bash
		  
		  function setup_host {
		  	echo "test"
		  }
		  ```
		- In another script
			- ```bash
			  source utils.sh
			  
			  setup_host
			  ```
	- Function with two parameters
		- ```bash
		  function scp_wrapper() {
		  	TARGET_DIR=$1
		      HOST_DIR=$2
		      echo "Copying ${TARGET_DIR} to ${HOST_DIR}"
		  }
		  ```
		- Calling the function
		  ```bash
		  scp_wrapper ~/filesystem.txt ~/files.txt
		  ```
- Killing processes using ports
  collapsed:: true
	- `sudo ss --tulnp`
	  Modern replacement for `netstat`
		- Shows you which ports are open and which process (PID/name) is using them
	- `kill -9 8218` = kill process ID 8218
- `sshpass` to automatically provide passwords to SSH commands like `ssh` or `scp`
  collapsed:: true
	- Example
		- `sshpass -p "vagrant" scp -o StrictHostKeyChecking=no vagrant@${IP}:${TARGET_DIR} ${HOST_DIR}`
	- Flags
		- `-o StrictHostKeyChecking=no` = **don’t ask to confirm the host’s fingerprint** when connecting for the first time.
			- Prompt is normally:
			  ```
			  The authenticity of host '192.168.56.10' can't be established.
			  Are you sure you want to continue connecting (yes/no)?
			  ```
- `pushd` and `popd` for navigating between multiple directories
  collapsed:: true
	- `pushd` → add current dir to stack + go to new dir
		- "Push Directory"
		- **Purpose:** Change to a directory **and remember the previous one** on a stack.
	- `popd` → remove top dir from stack + return there
		- "Pop Directory"
		- **Purpose:** Go back to the **directory on top of the stack**.
	- **View stack:** `dirs -v`
		- Shows numbered list of directories in the stack.
	- Example workflow
		- ```bash
		  pwd
		  # /home/user
		  
		  pushd /tmp
		  # /tmp /home/user
		  
		  pushd /var/log
		  # /var/log /tmp /home/user
		  
		  popd
		  # /tmp /home/user
		  
		  popd
		  # /home/user
		  ```
- `sort`
- `uniq`
- `grep`
- `diff`
- idiomatic, safe Bash script header pattern (used in most production install or setup scripts)
  collapsed:: true
	- ```bash
	  #!/usr/bin/env bash
	  set -euo pipefail
	  IFS=$'\n\t'
	  
	  # --- Configuration and argument handling ---
	  usage() {
	    echo "Usage: $0 <install_dir>"
	    echo "Example: $0 /usr/local/bin"
	    exit 1
	  }
	  
	  # Ensure the argument is provided
	  if [ $# -lt 1 ]; then
	    echo "Error: missing argument <install_dir>"
	    usage
	  fi
	  
	  BINARY_INSTALL_DIR=$1
	  
	  # --- Main logic ---
	  
	  ```
- `mkdir`
  collapsed:: true
	- Flags
		- `--parents`
		  Also make parent directories if they don't exist
- [Learning Resources]
	- [GitHub - dylanaraps/pure-bash-bible: 📖 A collection of pure bash alternatives to external processes.](https://github.com/dylanaraps/pure-bash-bible)
	- [GitHub - dylanaraps/pure-sh-bible: 📖 A collection of pure POSIX sh alternatives to external processes.](https://github.com/dylanaraps/pure-sh-bible)