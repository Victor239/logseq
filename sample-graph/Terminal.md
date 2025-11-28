- Pros/Cons
  collapsed:: true
	- Pros
		-
	- Cons
		-
	- Unclear
	- Comparisons
		- CLIs vs GUIs
		  id:: 05d611e4-7cd9-489b-8993-914cb1bb8e27
			- For CLIs
				- Speed: it's slower to physically navigate a cursor through stacks of panels and windows and drop downs to execute a command, rather than simply typing a few keystrokes. You have to spend time looking for things, even when you know what they're called.
				- Space: When you have to visually represent every command a programme is capable of, you run out of screen space fairly quickly. There are only so many sub-sub-sub menus and tabbed panels you can stuff in before an interface becomes overwhelming. The CLI hides all its commands out of sight, and only brings them into view when called.
				- Composability: In programming the number of possible keywords, functions, and combinations is exponential. When you're working in programmatic code you have a wide range of flexibility. You can write your own scripts to do anything you wish. Including remixing other people's scripts and utilities. Programmers need access to those powerful, lower-level abstractions with fewer constraints to create software.
			- For GUIs
				-
			- Similarities
				-
			- Unclear
				-
- # Unix Shell
  id:: 644c0b9b-9c03-42c8-99b7-f9dfb8282bbb
	- Meta
		- `poweroff`
		- `sudo` - super-root user
		  collapsed:: true
			- One final note – while using root is a very bad habit for day to day sysadmin work, when setting up a server most commands needs root privileges so I do tend to run a root shell. Thus sudo commands are omitted, and you should assume root unless stated otherwise (you can gain a root shell from an account that has the appropriate access rights with sudo -i).
		- `--help`
		  Find out what command does e.g. apt-get --help
		- In the future, you can save a lot of time by checking the man page first:
		  `man <command name>`
		- *Environment variables*
		  id:: 639d8ce1-4fb8-4b74-9c53-374b5591e365
		  collapsed:: true
			- `printenv` = List all environment variables
			- `printenv HOME SHELL` = List the specific environment variables `HOME` and `SHELL`
			- `export GOPATH=$HOME/go` = Set a temporary environment variable of `GOPATH=$HOME/go`
			- *Setting a permanent environment variable*
			  id:: 64634a46-c61c-4520-bd6f-d38493de8851
				- `nano ~/.bashrc`
				  Open this file
				- `export GOPATH=$HOME/go`
				  Add this line or similar example into the file in order to set a permanent environment variable of `GOPATH=$HOME/go`
					- Similar
						- `export PATH=$PATH:/var/lib/flatpak/exports/bin`
				- `source ~/.bashrc` = Reload bashrc without having to log back in again
				  id:: 644c0b9b-cdd7-48ca-900d-1ae586db9309
			- Adding directories to PATH
				- `sudo nano ~/.bashrc`
				- Example: `export PATH=$PATH:/usr/sbin:/sbin`
				- `source ~/.bashrc`
			- Convert an env var value into a file
				- ```bash
				  echo "${my_env_var}" > /data/file.txt
				  ```
			- Convert a file into an env var
				- ```bash
				  export my_env_var=$(cat /data/file.txt)
				  ```
					- Utilises [command substitution](https://tldr.org/LDP/abs/html/commandsub.html)
	- ### Cheatsheet
	  id:: 67914a25-8a0d-4741-a10a-9101612cd80f
	  collapsed:: true
		- Resolved ulimit error "too many files open"
		  collapsed:: true
			- `ulimit -n 65535` in npm proxy script fixed that partially
			- ((679f62c2-e519-4fc1-9923-03a7091c4001))
			- ((679f62c2-fbe9-4b53-83a6-f4216b598fee))
			- ((679f62c2-823d-4ff3-b1f8-45d52aed45b8))
			- with [Set Permanently ulimit -n / open files in ubuntu · GitHub](https://gist.github.com/bfgits/b4f922958716088f4c840365e54c625e) as a comprehensive solution
		- `mkdir -p` flag will create parent directories as needed so you can create arbitrarily nested directories in one command
		- `set`
		  collapsed:: true
		  Useful for debugging by exiting on errors or printing each command before their terminal output
			- `set –ex` at the top of every Bash script
			  id:: 679f62b7-2f3c-4696-94bd-e9c25c035efe
				- `set -e`: This flag tells the shell to exit immediately if a command exits with a non-zero status (i.e., an error). This is useful for ensuring that scripts stop running as soon as an error occurs.
				- `set -x`: This flag enables tracing, which means the shell will print each command before it is executed. This is helpful for debugging scripts as it shows you exactly what commands are being run.
				- `set +e` is good to include here if you’ve included `set –e` in your child scripts for better error detection
		- `trap`
		  collapsed:: true
		  Useful for running mandatory cleanup functions on script failure
			- `trap exit_fun EXIT`
			  collapsed:: true
				- Using trap exit_fun EXIT in a Bash script sets up a trap for the EXIT signal. This means that when the script exits for any reason, the exit_fun function will be executed. The EXIT signal is triggered when the script finishes execution, either due to reaching the end of the script or an explicit exit command.
				- It’s important to note that in POSIX-compliant shells, the EXIT trap does not handle signals like INT (interrupt), TERM (terminate), or HUP (hang up). To handle these signals, you would need to set additional traps:
					- ```shell
					  trap 'echo "Interrupt signal received"; exit_fun' INT
					  trap 'echo "Terminate signal received"; exit_fun' TERM
					  trap 'echo "Hang up signal received"; exit_fun' HUP
					  ```
				- can be exited with CTRL+D, which executes EXIT in any terminal(?)
			- `trap function1 EXIT`
				- This will run this function1 whenever the script exits for any reason. Useful for cleanup operations like removing temporary files and direcotries before the script fails. This doesn’t execute if the script exits due to signals like SIGINT or SIGTERM
		- Heredoc (append or replace text in file)
		  id:: 679f62c2-823d-4ff3-b1f8-45d52aed45b8
		  collapsed:: true
			- ```shell
			  cat <<EOF >> /etc/test.txt
			  test text1
			  test text2
			  EOF
			  ```
		- Conditionals
			- If statements
			  collapsed:: true
				- Shell script to programmatically append to file only if it doesn't already exist in it
				  id:: 679f62c2-e519-4fc1-9923-03a7091c4001
					- ```shell
					  if ! grep “fs.file-max = 65535” /etc/sysctl.conf; then
					  cat <<EOF >> /etc/sysctl.conf
					  fs.file-max = 65535
					  fi
					  ```
					- ((679f62c2-823d-4ff3-b1f8-45d52aed45b8))
				- Check the output of a command and run conditional (less than)
				  id:: 679f62c2-fbe9-4b53-83a6-f4216b598fee
					- ```shell
					  if [ "$(ulimit -n)" -lt 2000 ]; then
					  echo "$(ulimit -n)"
					  ```
			- Conditional based on exit status of a command
			  collapsed:: true
				- ```bash
				  ./my_program # or just do a one line command
				  if [ $? -eq 0 ]; then
				      echo "Success: Result is 0"
				  elif [ $? -eq 1 ]; then
				      echo "Success: Result is 1"
				      exit 1  # Set exit status of this script to 1
				  else
				      echo "Failure: Result is neither 0 nor 1"
				  fi
				  ```
					- `[ ... ]`: In Bash, `[` is a built-in command also known as `test`. It's used for evaluating conditional expressions. The `[` command is typically followed by a space-separated list of arguments and ends with `]`. It's important to have spaces around the square brackets for correct syntax.
					- `$?`: This is a special variable in Bash that holds the exit status of the last command executed. After executing a command, `$?` stores its exit status, which is an integer value indicating whether the command succeeded (usually 0) or failed (a non-zero value).
					- `-eq`: This is an operator used within the `test` command to check for equality. It evaluates to true if the operands are equal.
					- `0`: This is the value we are comparing `$?` against. In this context, `0` represents success, as it is a common convention in Unix-like systems for programs to return 0 upon successful execution.
				- ```bash
				  output=$(./run_script.sh)
				  status_code=$?
				  
				  if [[ $status_code -eq 0 ]]; then
				  	echo "Ran successfully."
				  else
				  	echo "Ran unsuccessfully."
				  fi
				  ```
		- Handling decimals
		  collapsed:: true
			- ((4910918d-a2dc-47cf-9f45-1e0dcf14fdfb))
		- Spaces around `=` in variable assignment: In Bash, when assigning values to variables, you cannot have spaces around the `=` sign. For example, `var = ...` is incorrect. It should be `var=....`
		- Getting the length of a string
		  id:: 678cc3ba-42a6-4c2c-a6ab-047be5e0b01f
		  collapsed:: true
			- `${#var}`
				- is equivalent to [[JavaScript]] : `var.length`
			- Related: ((678cc144-a20c-4ec7-af99-e8f4419a09e5))
		- String replacement
		  collapsed:: true
			- {{embed ((b39b308a-c1c0-455e-be4e-af7bc83df1df))}}
		- Arithmetic expansion vs command substitution
		  collapsed:: true
			- ((7bb53ae2-9d3e-4b44-97ff-c8ee3023577e))
		- ((19485a88-a441-470e-86b2-9f32402c953a))
		- ((678cda80-df87-4c61-9f3e-07b91e6e7dab))
		- If you've got file access to a system but not shell/SSH then to debug you can instead save the output of commands directly to a text file in the same directory
		  collapsed:: true
			- ```shell
			  #!/bin/bash
			  
			  # Define the output file
			  OUTPUT_FILE="$(dirname "$0")/ssh_status.txt"
			  
			  # Run the command and save the output
			  systemctl status ssh > "$OUTPUT_FILE" 2>&1
			  
			  # Print a message indicating where the output is saved
			  echo "SSH service status saved to $OUTPUT_FILE"
			  ```
			- Saving multiple command outputs to the same file
				- ```shell
				  #!/bin/bash
				  
				  # Define the output file
				  OUTPUT_FILE="$(dirname "$0")/service_status.txt"
				  
				  # Run the SSH service status check and save the output
				  echo "=== SSH Service Status ===" > "$OUTPUT_FILE"
				  systemctl status ssh >> "$OUTPUT_FILE" 2>&1
				  
				  # Run the Burger service status check and append the output
				  echo -e "\n=== Burger Service Status ===" >> "$OUTPUT_FILE"
				  systemctl status burger >> "$OUTPUT_FILE" 2>&1
				  
				  # Print a message indicating where the output is saved
				  echo "Service statuses saved to $OUTPUT_FILE"
				  ```
		- Snippet to exit script if there's no exactly one argument provided
		  collapsed:: true
			- ```shell
			  if [ "$#" -ne 1 ]; then
			  exit 2
			  fi
			  ```
			- `-ne` = not equal
			- `$1` is how to refer to the first argument as a variable e.g. `VAR1="$1"`
		- `if` statement with two `[[`
		  collapsed:: true
			- ```shell
			  if [[ "${VAR}" == "ADD" ]]; then
			  pass
			  fi
			  ```
		- `[[ ... ]]` vs `[ ... ]` for conditional expressions
		  collapsed:: true
			- In shell scripting, `[[ ... ]]` and `[ ... ]` (or `test ...`) are both used for conditional expressions, but `[[ ... ]]` is more powerful and preferred in modern Bash scripting. Here’s why:
			- Key Differences Between `[` and `[[` in Shell Scripts
				- Safer String Comparisons
					- `[[ ... ]]` prevents issues with empty or unquoted variables.
					- `[[ $var == "" ]`] is safe even if `$var` is empty.
					- `[ $var == "" ]` can cause errors if `$var` is empty.
				- Pattern Matching (`=~`)
					- `[[ ... ]]` supports regular expressions with =~, while [ does not.
					- ```shell
					  if [[ "hello123" =~ ^hello[0-9]+$ ]]; then
					  echo "Matches!"
					  fi
					  ```
					- This would not work with `[ ... ]`.
				- Logical Operators (&& and || Without -a and -o)
					- `[[ ... ]]` allows `&&` and `||` for combining conditions, whereas `[` requires `-a` (AND) and `-o` (OR).
					- ```shell
					  if [[ $a -gt 5 && $b -lt 10 ]]; then
					  echo "Both conditions met"
					  fi
					  ```
					   With `[ ... ]`, you must write:
					- `if [ $a -gt 5 -a $b -lt 10 ]; then`
				- No Need for Quoting with `[[ ... ]]`
					- `[[ ... ]]` allows safer variable expansion without needing explicit quotes.
					- Example:
					- ```shell
					  file="my file.txt"
					  if [[ -e $file ]]; then  # Works fine
					  ```
					- With [ ... ], you must quote $file or it will break if it contains spaces:
						- ```shell
						  if [ -e "$file" ]; then  # Safe
						  if [ -e $file ]; then    # ERROR if file has spaces
						  ```
				- Better Syntax Handling
					- `[[ ... ]]` does not require escaping `!` (negation).
					- ```shell
					  if [[ ! -f "file.txt" ]]; then  # Works fine
					  
					  In [ ... ], ! must be escaped:
					  
					  if [ \! -f "file.txt" ]; then  # Works, but clunky
					  ```
			- When to Use Which?
				- Prefer `[[ ... ]]` in Bash and KornShell (ksh) scripts for improved syntax and safety.
				- Use `[ ... ]` only when writing scripts meant for POSIX-compliant shells, like sh, since `[[ ... ]]` is Bash/Ksh-specific.
		- Using `|` pipe operator and `stdin`
		  collapsed:: true
			- `echo @user:$(echo -n "user" | openssl passwd -6 -stdin)" | sudo tee "${BASE}/mnt/userconf.txt"`
				- `echo -n "user"` - the `-n` flag will prevent the trailing newline from being added
				- `-stdin` - reads it's input from standard input (`stdin`)
				- `| sudo tee "${BASE}/mnt/userconf.txt"`
					- `|` takes the output from the previous command and passes it as input to the next command
					- `tee` with -i` option (which defualts to standard input if no file is specified) to both display the output on the terminal and write it to a file at the same time
		- `source <file-path>` reads and executes commands from the specified file as if they were in the shell. It is equivalent to dotting (`dot` or `.`) a script in Bash
			- Can be used to obtain variables from other files for example
		- Related: ((652d41e6-e0d1-4b9c-be90-c959bd89a75d))
	- [Bash](https://www.gnu.org/software/bash/)
	- Users
	  collapsed:: true
		- Change user
		  `su - user2`
		- Change to root
		  `sudo su`
		- Check which user you are
		  `whoami`
		- logout
		  `exit`
		- Related: [[IT Systems]] : ((64634999-8fb6-4449-a9b3-4075608c6dff))
	- Navigation & Moving Files
	  collapsed:: true
		- Transferring Files
		  collapsed:: true
			- **Between Local and Remote**
				- Linux
				  collapsed:: true
					- Uploading via SCP (SSH)
					  id:: 663a57ae-8972-4c68-8624-a4b7e64b97ea
					  collapsed:: true
						- On local system
							- `cd ~/Videos/`
							- ```bash
							  scp -i <SSH KEY> <LOCAL FILE PATH> <REMOTE SERVER USERNAME>@<REMOTE SERVER IP>:<REMOTE SERVER DIRECTORY FOR UPLOAD>
							  ```
								- Example
									- ```bash
									  scp -i ~/.ssh/boss-XPS-9380 Tenet.mp4 root@138.68.101.35:/media/Movies
									  scp -i ~/.ssh/forum-admins2 s9e-MediaSites-2.12.3.zip webmaster@82.147.84.253:/var/www/forum/src/addons
									  scp -i ~/.ssh/forum-admins2 /home/boss/Downloads/AdminCPStyle.zip webmaster@82.147.84.253:/var/www/forum/src/addons
									  ```
							- Note: entering the user ((663a578f-8d32-4dbd-83e8-b8d53f276f4c)) will be required
						- From remote system
							- Get your local host's username
								- `whoami`
							- Get your local host's IP address
								- `hostname -I`
								- `ip addr show`
								  Look next to "inet"
							- ((64634999-0677-495a-a974-39c697065b37)) into remote
							- SCP pull file to remote
								- `scp user@local-machine-ip:/path/to/local/file /path/to/remote/destination/`
								- Example
									- `scp user@192.168.1.100:/home/user/localfile.txt /home/ec2-user/remotefile.txt`
						- Related: ((663a57ae-b9a0-4c48-95e9-92d79ed3e8da))
					- ((65f86472-20de-46a6-af62-43cecb6b0a0f))
					- See syncthing
					- _[Learning Resources]_
					  collapsed:: true
						- [https://linuxize.com/post/how-to-use-scp-command-to-securely-transfer-files/](https://linuxize.com/post/how-to-use-scp-command-to-securely-transfer-files/)
				- _{Archive}_
				  collapsed:: true
					- Windows methods
					  SCP or SFTP via GUI tools only
						- You can't use command line because Linux doesn't understand c:\ just as Windows doesn't understand / partitions
						- WinSCP
							- If you can't connect to the VM then check `systemctl status ssh`, and `systemctl start ssh` if it's inactive
						- Cyberduck
						- How to Use SFTP with Filezilla
						  https://www.digitalocean.com/community/tutorials/how-to-use-filezilla-to-transfer-and-manage-files-securely-on-your-vps
						- https://www.digitalocean.com/community/tutorials/how-to-use-sftp-to-securely-transfer-files-with-a-remote-server
			- **Between Remote and Remote**
				- Transferring via SCP (SSH) between Servers
				  id:: 663a57ae-b9a0-4c48-95e9-92d79ed3e8da
				  collapsed:: true
				  PuTTY
					- Examples
						- (port of remote destination) (source destination) (remote destination)
						  scp -P 3498 -r /home/boss/public_html/bvrbali root@128.199.96.9:/bvrbali
						- scp -r /home/pmmedicine/public_html ubuntu@52.56.137.239:/1MAGENTO
						- scp -r /home/pmmedicine/public_html ubuntu@52.56.137.239:/1MAGENTO
					- _Public key authentication version_
					  Taught by freelancer
						- [1] Generate OpenSSH via terminal
						  collapsed:: true
							- Source has generated a key pair (private and public) using the command: ssh-keygen
							- Press enter to save it in default location (only one allowed, doing it again overwrites)
							-
						- [2] Copy public key from source to destination
						  collapsed:: true
							- I've inserted the public key from Source (/root/.ssh/id_rsa.pub) into cPanel (/root/.ssh/authorized_keys)
							- [source] cat /root/.ssh/id_rsa.pub - to get the public key
							- [remote] nano /root/.ssh/authorized_keys - APPEND it to the end of the file (in case you have multiple public keys, they all have to be in that file)
						- [3] Transfer from source to destination via SCP
						  collapsed:: true
							- [source] scp test_file root@<remote_server_IP>:/root/ - to copy the LOCAL test_file to remote server at location /root/
							- [source] if asked if you want to accept the authenticity of the host, accept it. This will happen only to the first transfer.
							- I've SCPed a file from local to /root on the cPanel server using:
								- scp <location_to_local_file> root@<cpanel's server IP>:<Location on cpanel server>
					- Flags
						- `-r`
						  Copy recursively
							- `scp -r [source] [destination]`
					- Info
						- http://www.hypexr.org/linux_scp_help.php
						- http://www.computerhope.com/unix/scp.htm
					- Related: ((663a57ae-8972-4c68-8624-a4b7e64b97ea))
				- ((65f86472-20de-46a6-af62-43cecb6b0a0f))
		- `cp` 
		  collapsed:: true
		  Copying
			- cp <source> <target>
			  id:: 64634a45-1e34-45ac-8f35-91077749abe2
			  collapsed:: true
				- Examples
				  collapsed:: true
					- cp /root/
					- cp -i /home/**pmmcouk**/public_html/wp-content/backups-dup-pro/<b>ArchiveFullName_installer.php</b> /home/<b>t1pmm</b>/public_html
				- 1 Backlink
					- cp /root/.ssh/authorized_keys /home/kid/.ssh/authorized_keys
					  See [cp <source> <target>](https://workflowy.com/#/d0cff37f4a23)
			- cp -r includes/* ./
			  collapsed:: true
			  You can also use mv to move a whole directory and its content
				- (copy includes directory to current directory) Note: may need to mkdir first
			- Midnight Commander
			  collapsed:: true
				- Install
				  sudo apt-get install mc
				- Run
				  mc
				- Manual
					- Responds to mouse clicks
					- _Keyboard shortcuts_
						- Enter directory
						  Enter
						- Swap between panels
						  Tab
				- https://i.stack.imgur.com/xxgGm.png
			- Flags
				- Can use multiple e.g. `-TPv`
				- `-P` = copy a symbolic link directly, don't traverse it
				- `-T`: Forces the destination to be a directory if the source is a single file. This ensures that the file is copied into the directory rather than being named the same as the directory.
				- `-R`: Recursively copies directories and their contents. This flag is essential when copying directories to ensure that all files and subdirectories within the source directory are also copied.
				- `-v`: Verbose mode, which provides more detailed output about the files being copied. This can be useful for tracking the progress of the copy operation or for debugging purposes.
		- `ls`
		  collapsed:: true
		  List all contents of a directory
			- `ls -d */`
			  List directories in the current directory
		- `cd`
		  id:: 673767a8-7e32-448c-aea4-2424824fbb19
		  collapsed:: true
		  Change directory
			- `cd _directoryname_`
			  Move into a subdirectory
				- Example
					- `cd /home/boss/Downloads`
				- `cd /`
				  Go to root
			- `cd _public_html/cgi-bin_`
			  Move multiple directories within path:
			- `cd ..`
			  Move up a directory
				- Can do `cd ../../..` to move up three folders
			- Faster `cd`ing
			  id:: 6336adf2-8bc5-437d-bfd7-b377e773b90d
				- `cd` then write the first letter of a folder then `TAB` will autofill the rest of the folder name
			- Can do `../folder2` to `cd` to a sibling directory from `folder1`
		- `mv`
		  Rename/move file/directory
			- mv _source_ <u>dest</u>
			  collapsed:: true
			  Rename/Move a File
				- mv /path/to/source /path/to/dest
				- e.g. mv /home/jack/testfile /home/jack/testfile2
				- mv /home/bakashi/owncloud-8.1.1.tar.bz2 owncloud-8.1.1.tar.bz2
			- mv _source/_ <u>dest/</u>
			  collapsed:: true
			  Rename/Move a Folder
				- mv /path/to/source /path/to/dest
				- e.g. mv /home/vivek/data/ /nas/home/vivek/archived/
			- `mv /sourcedir/{,.[^.]}* /destdir/` = move all files including hidden files
	- Searching
	  collapsed:: true
		- `grep` search
			- ((636a77ab-1b7d-410e-8f03-fd427f329770))
			-
	- Executing Files
	  collapsed:: true
		- chmod +x scriptname.sh
		  Set execute permission on your script:
		- To run your script, enter:
			- ./script-name-here.sh
			- OR
			- sh script-name-here.sh
			- OR
			- bash script-name-here.sh
	- Editing Files
	  collapsed:: true
		- `ls`
		  collapsed:: true
		  List
			- `ls -l`
			  id:: 634bc1ee-d662-4244-bf4d-6bd64e77dbd1
			  List all permissions of files within directory
			- ls -l _filename_
			  List permissions of one file within directory
			- Colour code
				- Blue: Directory
				- Green: Executable or recognized data file
				- Cyan (Sky Blue): Symbolic link file
				- Yellow with black background: Device
				- Magenta (Pink): Graphic image file
				- Red: Archive file
				- Red with black background: Broken link
		- `chmod` Change permissions
		  collapsed:: true
			- `chmod 666 _filename_`
			  id:: 634bc1ee-436c-4b88-bfa2-877c4c7b1b12
			  Change permissions of one file to 666
			- `chmod -R 666 _filename_/`
			  Change every file in a directory to 666 permissions
			- `find _/opt/lampp/htdocs_ -type d -exec chmod 755 {} \;`
			  To change all the directories to `755` (-rwxr-xr-x)
			- To change all the files to `644` (-rw-r--r--)
			  `find /opt/lampp/htdocs -type f -exec chmod 644 {} \;`
			- Make file executable
				- `chmod +x my_script.sh`
			- Permission numbers explanation
			  collapsed:: true
				- `r` (read) has a numeric value of `4`
				- `w` (write) has a numeric value of `2`
				- `x` (execute) has a numeric value of `1`
				- Example:
					- Owner: `rwx` = 4 + 2 + 1 = 7
					- Group: `r-x` = 4 + 0 + 1 = 5
					- Others: `---` = 0 + 0 + 0 = 0
					- `750` is the final value
				- http://linuxcommand.org/images/permissions_diagram.gif
				- (owner, members of owners group, everyone else)
				- rwx = 111 in binary = 7
				- rw- = 110 in binary = 6
				- r-x = 101 in binary = 5
				- r-- = 100 in binary = 4
				- 777 (rwxrwxrwx)= no restrictions
				- 755 (rwxr-xr-x) The file's owner may read, write, and execute the file. All others may read and execute the file. This setting is common for programs that are used by all users.
			- Directory permissions
			  collapsed:: true
				- 777(rwxrwxrwx) No restrictions on permissions. Anybody may list files, create new files in the directory and delete files in the directory. Generally not a good setting.
				- 755 (rwxr-xr-x) The directory owner has full access. All others may list the directory, but cannot create files nor delete them. This setting is common for directories that you wish to share with other users.
				- 700 (rwx------) The directory owner has full access. Nobody else has any rights. This setting is useful for directories that only the owner may use and must be kept private from others.
			- Permissions for WordPress
			  collapsed:: true
				- All of our files and folders should now have the correct ownership. Now it’s time to adjust the permission modes. To make things simpler, you’ll only need to remember the following:
				- All files should be 664.
				- All folders should be 775.
				- wp-config.php should be 66
			- Related: ((634bc1ee-d662-4244-bf4d-6bd64e77dbd1))
		- `chown` 
		  id:: 64634a45-b3fc-4d6f-b5fe-2ee7f5e71fac
		  collapsed:: true
		  Take ownership
			- _Syntax_
				- `chown boss file1 dir1` = changes the ownership of a file named `file1` and directory `dir1` to a new owner named `boss`
				- chown owner_name file_name
				- chown owner_name:group_name file_name
				- `-R` - recursively
			- Arguments
				- `-h`, `--no-dereference` = affect each symbolic link instead of any referenced file (useful only on systems that can change the ownership of a symlink)
			- sudo chown -R www-data:www-data /var/www
			- sudo chown -R daemon:daemon /bitnami/wordpress
			- `chown --from=oldguy newguy * -R` = change all files belonging from one user to another
				- This also works for owner:group. `chown -R --from=oldowner:oldgroup newowner:newgroup`
			- Related: ((634bc1ee-d662-4244-bf4d-6bd64e77dbd1))
		- [`nano`](https://nano-editor.org)
		  collapsed:: true
			- Documentation
				- Modern bindings
					- In version 8.0, ^F is now bound to initiate a forward search by default, while ^B starts a backward search. M-F and M-B are set to repeat the search in the corresponding direction. The command-line option --modernbindings (-/) has been introduced to provide a set of new commands. These include ^Q for quit, ^X for cut, ^C for copy, ^V for paste, ^Z for undo, ^Y for redo, ^O for open a file, ^W for write a file, ^R for replace, ^G for find again, ^D for find again backwards, ^A for set the mark, ^T for jump to a line, ^P for show the position, and ^E for execute. These modern bindings are also activated when the name of nano's executable (or a symlink to it) starts with “e”.
					- Another new feature allows users to open a file at a specific line number using nano filename:number, in addition to the existing nano +number filename. The ** and ** commands now move the cursor to the first and last row in the viewport, while maintaining the horizontal position.
				- `man nano`
				- CTRL + W = search for a string
				- ALT + A = mark (highlight)
					- Use arrows to move
					- ALT + DEL to delete
				- Alternatively for large files (so that you don't load the whole file into memory and cause a crash)
					- `tail -100 filename` for last 100 lines
					- `head -n 100 filename` for first 100 lines
						- `head -n 100 filename | cat -n` if you want to see line numbers also
					- `grep` to search for specific things
			- Forks
				- [`micro`](https://micro-editor.github.io/)
				  Keybindings are closer to ((63209272-1088-4824-a762-4ac7ded04b0a))
					- https://news.ycombinator.com/item?id=37171294
					- `ALT+G` = see the shortcuts
					- id:: 66cf4bb7-9a3c-415b-8105-5809102dee9e
		- ((65770a27-6361-4507-9cff-d2f1217d157d))
		- `tar`
			- Untar compressed gzip files
				- `tar -xvzf filename.tar.gz`
		- Related: ((63209272-1088-4824-a762-4ac7ded04b0a))
	- Removing Files
	  collapsed:: true
		- `sudo rm -rf /path/to/dir/*` will remove everything in the specified folder. `-f` forces removal without asking for confirmation
		- `sudo rm -r foldername` will delete a folder and everything in it
	- Installing/Uninstalling
	  collapsed:: true
		- Uninstalling
			- Example
			  sudo apt-get --remove purge winehq-stable
	- Links
	  collapsed:: true
		- Hard links
		  collapsed:: true
			- What
			  collapsed:: true
				- [What is the difference between a hard link and a symbolic link? - Ask Ubuntu](https://askubuntu.com/questions/108771/what-is-the-difference-between-a-hard-link-and-a-symbolic-link)
				- [unix - What is the difference between a symbolic link and a hard link? - Stack Overflow](https://stackoverflow.com/questions/185899/what-is-the-difference-between-a-symbolic-link-and-a-hard-link)
				-
			- How to - for Logseq dual repo
			  collapsed:: true
				- Make a third hard link to a dedicated `hard-linked-files` folder
				  `cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-coding2/pages/Terminal.md hard-linked-files/Terminal.md`
				- `cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-coding2/pages/Terminal.md logseq-unenc/pages/Terminal.md`
			- To do
			  collapsed:: true
				- ```
				  Examples
				  
				  -----------
				  1) Link from original location to hard-linked-files dir
				  -----------
				  
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-coding2/pages/Technology.md hard-linked-files/Technology.md
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-coding2/pages/Software.md hard-linked-files/Software.md
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-coding2/pages/Programming-multimedia.md hard-linked-files/Programming-multimedia.md
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v 'logseq-coding2/pages/Programming software setup.md' 'hard-linked-files/Programming software setup.md'
				  
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v ls-android/pages/Inbox-Android.md hard-linked-files/Inbox-Android.md
				  
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v 'logseq-unenc/pages/Game design ideas.md' 'hard-linked-files/Game design ideas.md'
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-unenc/pages/PC.md hard-linked-files/PC.md
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-unenc/pages/SS14.md hard-linked-files/SS14.md
				  
				  -----------
				  2) Link from original location to other LS dir
				  -----------
				  
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-coding2/pages/Technology.md logseq-unenc/pages/Technology.md
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-coding2/pages/Software.md logseq-unenc/pages/Software.md
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-coding2/pages/Programming-multimedia.md logseq-unenc/pages/Programming-multimedia.md
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v 'logseq-coding2/pages/Programming software setup.md' 'logseq-unenc/pages/Programming software setup.md'
				  
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v ls-android/pages/Inbox-Android.md logseq-unenc/pages/Inbox-Android.md
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v ls-android/pages/Inbox-Android.md logseq-coding2/pages/Inbox-Android.md
				  
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v 'logseq-unenc/pages/Game design ideas.md' 'logseq-coding2/pages/Game design ideas.md'
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-unenc/pages/PC.md logseq-coding2/pages/PC.md
				  cd /home/boss/Vaults/gocryptfs1/Android-sync/Android-ATHENAEUM/Logseq && ln -v logseq-unenc/pages/SS14.md logseq-coding2/pages/SS14.md
				  ```
	- Networking
	  collapsed:: true
		- `hostname -I`
		  Check IP Address
		- `sudo netstat -pna | grep <port number>`
		  Check what process is using a specified port number
			- Example
				- `sudo netstat -pna | grep 11434`
				  Check what process is using port 11434
		- Wireshark
		- [Sniffnet](https://github.com/GyulyVGC/sniffnet)
			- [Sniffnet: comfortably monitor your Internet traffic](https://sniffnet.net/)
	- Terminal - how to do spaces in filepath
	  `cd ~/.steam/steam/steamapps/common/Grand\ Theft\ Auto\ V/`
	- Keyboard shortcuts
	  id:: 6341d9ab-4595-445a-8b0b-ec20e3648122
	  collapsed:: true
		- Related: Yakuake ((634204fc-aae9-418e-8112-c0353c355afe))
		- Priority
			- ((64977e6c-a25a-46a5-883f-3c38f532573a))
			- ((673767a8-413b-4024-8c6e-195a6689cd4c))
		- Bash Navigation
			- `CTRL + A`/`Home` = Move to the start of the command line
			- `CTRL + E`/`End` = Move to the end of the command line
			- `CTRL + F` = Move one character forward
			- `CTRL + B` = Move one character backward
			- `ALT + F`/`Esc + F`/`CTRL + Right arrow` = Moves the cursor one word forward
			- `ALT + B`/`Esc + B`/`CTRL + Left arrow` = Moves the cursor one word backward
		- Bash Control/Process
			- `CTRL + L` = Similar to clear command, clears the terminal screen
			- `CTRL + D` = Closes the current terminal
		- Bash History
			- `Up arrow`/`CTRL + P` = Moves to previous command
			- `Down`/`CTRL + N` = Moves to next command
			- `CTRL + R` = Incremental reverse search of bash history
			  id:: 673767a8-413b-4024-8c6e-195a6689cd4c
			- `ALT + P` = Non-incremental reverse search of bash history
			- `CTRL + J` = Ends history search at current command
			- `CTRL + S` = Gets the next most recent command
			- `CTRL + O` = Runs and re-enters the command found via Ctrl + S and Ctrl + R
			- `CTRL + G` = Exits history search mode
		- Bash Editing
			- `CTRL + U` = Deletes before the cursor until the start of the command
			- `CTRL + K` = Deletes after the cursor until the end of the command
			- `CTRL + D` = Removes the character under the cursor
			- `CTRL + H` = Removes character before the cursor
			- `CTRL + W` = Removes the word before the cursor
			  id:: 64977e6c-a25a-46a5-883f-3c38f532573a
			- `ALT + D` = Removes from the character until the end of the word
			- `ALT + Backspace` = Removes from the character until the start of the word
		- Bash Information
			- `TAB` = Autocompletes the command or file/directory name
			- `CTRL + I`= Completes the command like TAB
		- Process Management
			- Here are some of the basic process management shortcuts:
			- Ctrl+Z: pause a process (plus `bg` to resume in the background, `fg` to raise to foreground)
			- Ctrl+C: politely ask the process to
			  shut down now
				- Quitting CLI programs
					- Usually `CTRL + C`, `CTRL + D` or `q`
					- Vim is more elaborate to quit
			- Ctrl+\: mercilessly kill the process that is currently in the foreground
			- Alt+SysRq+s: Write data to disk (always do this before killing anything important)
			- Alt+SysRq+s, k: mercilessly kill all current
			  processes on a given virtual console
			- Alt+SysRq+s, b: mercilessly reboot without unmounting,
			- Alt+SysRq+r, e, i, s, u, b: Safely **r**eboot **e**ven **i**f the **s**ystem is **u**tterly **b**roken,
		- [Learning Resources]
		  collapsed:: true
			- [1](https://www.makeuseof.com/linux-bash-terminal-shortcuts/)
			  collapsed:: true
				- | **Bash Navigation** |
				  | Ctrl + A | Move to the start of the command line |
				  | Ctrl + E | Move to the end of the command line |
				  | Ctrl + F | Move one character forward |
				  | Ctrl + B | Move one character backward |
				  | Ctrl + XX | Switch cursor position between start of the command line and the current position |
				  | Ctrl + \] + x | Moves the cursor forward to next occurrence of x |
				  | Alt + F / Esc + F | Moves the cursor one word forward |
				  | Alt + B / Esc + B | Moves the cursor one word backward |
				  | Alt + Ctrl + \] + x | Moves cursor to the previous occurrence of x |
				- [Linux Bash Terminal Keyboard Shortcuts
				  --------------------------------------
				  
				  | Shortcut | Action |
				  | --- | --- |
				  | **Bash Navigation** |
				  | Ctrl + A | Move to the start of the command line |
				  | Ctrl + E | Move to the end of the command line |
				  | Ctrl + F | Move one character forward |
				  | Ctrl + B | Move one character backward |
				  | Ctrl + XX | Switch cursor position between start of the command line and the current position |
				  | Ctrl + \] + x | Moves the cursor forward to next occurrence of x |
				  | Alt + F / Esc + F | Moves the cursor one word forward |
				  | Alt + B / Esc + B | Moves the cursor one word backward |
				  | Alt + Ctrl + \] + x | Moves cursor to the previous occurrence of x |
				  | **Bash Control/Process** |
				  | Ctrl + L | Similar to clear command, clears the terminal screen |
				  | Ctrl + S | Stops command output to the screen |
				  | Ctrl + Z | Suspends current command execution and moves it to the background |
				  | Ctrl + Q | Resumes suspended command |
				  | Ctrl + C | Sends SIGI signal and kills currently executing command |
				  | Ctrl + D | Closes the current terminal |
				  | **Bash History** |
				  | Ctrl + R | Incremental reverse search of bash history |
				  | Alt + P | Non-incremental reverse search of bash history |
				  | Ctrl + J | Ends history search at current command |
				  | Ctrl + \_ | Undo previous command |
				  | Ctrl + P / Up arrow | Moves to previous command |
				  | Ctrl + N / Down arrow | Moves to next command |
				  | Ctrl + S | Gets the next most recent command |
				  | Ctrl + O | Runs and re-enters the command found via Ctrl + S and Ctrl + R |
				  | Ctrl + G | Exits history search mode |
				  | !! | Runs last command |
				  | !\* | Runs previous command except its first word |
				  | !\*:p | Displays what !\* substitutes |
				  | !x | Runs recent command in the bash history that begins with x |
				  | !x:p | Displays the x command and adds it as the recent command in history |
				  | !$ | Same as OPTION+., brings forth last argument of the previous command |
				  | !^ | Substitutes first argument of last command in the current command |
				  | !$:p | Displays the word that !$ substitutes |
				  | ^123^abc | Replaces 123 with abc |
				  | !n:m | Repeats argument within a range (i.e, m 2-3) |
				  | !fi | Repeats latest command in history that begins with fi |
				  | !n | Run nth command from the bash history |
				  | !n:p | Prints the command !n executes |
				  | !n:$ | Repeat arguments from the last command (i.e, from argument n to $) |
				  | **Bash Editing** |
				  | Ctrl + U | Deletes before the cursor until the start of the command |
				  | Ctrl + K | Deletes after the cursor until the end of the command |
				  | Ctrl + W | Removes the command/argument before the cursor |
				  | Ctrl + D | Removes the character under the cursor |
				  | Ctrl + H | Removes character before the cursor |
				  | Alt + D | Removes from the character until the end of the word |
				  | Alt + Backspace | Removes from the character until the start of the word |
				  | Alt + . / Esc+. | Uses last argument of previous command |
				  | Alt + < | Moves to the first line of the bash history |
				  | Alt + > | Moves to the last line of the bash history |
				  | Esc + T | Switch between last two words before cursor |
				  | Alt + T | Switches current word with the previous |
				  | **Bash Information** |
				  | TAB | Autocompletes the command or file/directory name |
				  | ~TAB TAB | List all Linux users |
				  | Ctrl + I | Completes the command like TAB |
				  | Alt + ? | Display files/folders in the current path for help |
				  | Alt + \* | Display files/folders in the current path as parameter |
				  
				  Plenty More to Learn About Linux
				  --------------------------------
				  
				  The Bash shell keyboard shortcuts work around the developer's DRY (Don't Repeat Yourself) philosophy. They help make effective use of your time by improving productivity in a fast-paced work environment.
				  
				  The above cheat sheet is just the tip of an iceberg. The more you begin to explore Linux terminal commands and Bash shortcuts, the easier and more interesting Linux becomes.
			- [2](https://gist.github.com/tuxfight3r/60051ac67c5f0445efee)
			  collapsed:: true
				- ```
				  Bash Shortcuts
				  ==============
				  
				  ![visual cheetsheet](https://raw.githubusercontent.com/fliptheweb/bash-shortcuts-cheat-sheet/master/moving_cli.png)
				  
				  ## Moving
				  
				  | command  | description                    |
				  |----------|--------------------------------|
				  | ctrl + a | Goto BEGINNING of command line |
				  | ctrl + e | Goto END of command line       |
				  | ctrl + b | move back one character        |
				  | ctrl + f | move forward one character     |
				  | alt + f  | move cursor FORWARD one word   |
				  | alt + b  | move cursor BACK one word      |
				  | ctrl + xx | Toggle between the start of line and current cursor position |
				  | ctrl + ] + x	 | Where x is any character, moves the cursor forward to the next occurance of x |
				  | alt + ctrl + ] + x  | Where x is any character, moves the cursor backwards to the previous occurance of x |
				  
				  ## Edit / Other
				  
				  | command  | description                    |
				  |----------|--------------------------------|
				  | ctrl + d          | Delete the character under the cursor |
				  | ctrl + h          | Delete the previous character before cursor |
				  | ctrl + u          | Clear all / cut BEFORE cursor |
				  | ctrl + k          | Clear all / cut AFTER cursor |
				  | ctrl + w          | delete the word BEFORE the cursor |
				  | alt + d           | delete the word FROM the cursor |
				  | ctrl + y          | paste (if you used a previous command to delete) |
				  | ctrl + i          | command completion like Tab
				  | ctrl + l          | Clear the screen (same as clear command) |
				  | ctrl + c          | kill whatever is running |
				  | ctrl + d          | Exit shell (same as exit command when cursor line is empty) |
				  | ctrl + z          | Place current process in background |
				  | ctrl + _          | Undo |
				  | ctrl + x ctrl + u	| Undo the last changes. ctrl+ _ does the same |
				  | ctrl + t          | Swap the last two characters before the cursor |
				  | esc + t           | Swap last two words before the cursor |
				  | alt + t           | swap current word with previous |
				  | esc + .           | |
				  | esc + _           | |
				  | alt + [Backspace] | delete PREVIOUS word |
				  | alt + <           | Move to the first line in the history |
				  | alt + >           | Move to the end of the input history, i.e., the line currently being entered |
				  | alt + ?           | display the file/folder names in the current path as help |
				  | alt + *           | print all the file/folder names in the current path as parameter |
				  | alt + .           | print the LAST ARGUMENT (ie "vim file1.txt file2.txt" will yield "file2.txt") |
				  | alt + c           | capitalize the first character to end of word starting at cursor (whole word if cursor is at the beginning of word)|
				  | alt + u           | make uppercase from cursor to end of word |
				  | alt + l           | make lowercase from cursor to end of word |
				  | alt + n           | |
				  | alt + p           | Non-incremental reverse search of history. |
				  | alt + r           |Undo all changes to the line|
				  | alt + ctl + e     |Expand command line. |
				  | ~[TAB][TAB]       | List all users |
				  | $[TAB][TAB]       | List all system variables |
				  | @[TAB][TAB]       | List all entries in your /etc/hosts file |
				  | [TAB]             | Auto complete |
				  | cd -              | change to PREVIOUS working directory |
				  
				  ## History
				  
				  | command  | description                    |
				  |----------|--------------------------------|
				  | ctrl + r          | Search backward starting at the current line and moving 'up' through the history as necessary |
				  | crtl + s          | Search forward starting at the current line and moving 'down' through the history as necessary |
				  | ctrl + p          | Fetch the previous command from the history list, moving back in the list (same as up arrow) |
				  | ctrl + n          | Fetch the next command from the history list, moving forward in the list (same as down arrow) |
				  | ctrl + o          | Execute the command found via Ctrl+r or Ctrl+s |
				  | ctrl + g          | Escape from history searching mode |
				  | !!                | Run PREVIOUS command (ie `sudo !!`) |
				  | !vi               | Run PREVIOUS command that BEGINS with vi |
				  | !vi:p             | Print previously run command that BEGINS with vi |
				  | !n		            | Execute nth command in history |
				  | !$		            | Last argument of last command |
				  | !^		            | First argument of last command |
				  | ^abc^xyz	        | Replace first occurance of abc with xyz in last command and execute it |
				  
				  # Kill a job
				  
				  n = job number, to list jobs, run `jobs`
				  
				  ```bash
				  kill %n
				  ```
				  
				  Example:
				  
				  ```bash
				  kill %1
				  ```
				  
				  ## References
				  
				  1. http://cnswww.cns.cwru.edu/php/chet/readline/readline.html
				  2. https://github.com/fliptheweb/bash-shortcuts-cheat-sheet/blob/master/README.md
				  ```
	- ### Scripting
	  id:: 652d41e6-e0d1-4b9c-be90-c959bd89a75d
	  collapsed:: true
		- Whilst variable replacement uses curly brackets `"${var1}"`
			- Command output replacement uses smooth brackets `"$(pwd)"`
		- Creating or appending multiple lines of text
		  id:: 65770a27-6361-4507-9cff-d2f1217d157d
		  collapsed:: true
			- [Here Documents](https://tldp.org/LDP/abs/html/here-docs.html) `<<`
			  id:: 661e6277-3a5c-4d27-9a29-79f3620f3da7
			  collapsed:: true
			  Can be used to add multi-lines of string into files from the terminal for example
				- Syntax
					- ```bash
					  COMMAND <<InputComesFromHERE
					  ...
					  ...
					  ...
					  InputComesFromHERE
					  ```
				- Examples
					- ```bash
					  cat << EOF > /tmp/yourfilehere
					  These contents will be written to the file.
					          This line is indented.
					  EOF
					  ```
			- Here's a shell script that will add the following to a file at `test.txt`
				- This script uses a ((661e6277-3a5c-4d27-9a29-79f3620f3da7)) to write the contents of the file to `test.txt`.
				- ```sh
				  #!/bin/bash
				  
				  cat <<EOF > test.txt
				  something1
				  something2
				  something3
				  EOF
				  ```
			- Equivalent as a shell command requires `\n` for line breaks
			  collapsed:: true
				- ```bash
				  echo -e "[default]\noutput = json\nregion = eu-west-1\naws_access_key_id = ${AWS_access_key_id_value}\naws_secret_access_key = ${aws_secret_access_key}\naws_session_token = ${aws_session_token}" > ~/.aws/credentials`
				  ```
			- Equivalent as multiple shell commands
				- ```bash
				  echo "something1" > test.txt
				  echo "something2" >> test.txt
				  echo "something3" >> test.txt
				  ```
				- ### Explanation:
					- `>` is used to create or overwrite `test.txt` with the first line (`something1`).
					- `>>` is used to append the subsequent lines (`something2` and `something3`) to the file without overwriting the content.
			- Source: Conversation with Bing, 11/12/2023
			  collapsed:: true
				- (1) How to manage credentials for a shell script that uses AWS CLI?. https://stackoverflow.com/questions/74281038/how-to-manage-credentials-for-a-shell-script-that-uses-aws-cli.
				  (2) Setting AWS Credentials, Script Task and PowerShell - Atlassian Community. https://community.atlassian.com/t5/Bamboo-questions/Setting-AWS-Credentials-Script-Task-and-PowerShell/qaq-p/711326.
				  (3) Getting Temporary Credential on AWS CloudShell - Medium. https://medium.com/@daichiharada/getting-temporary-credential-on-aws-cloudshell-9a7da5a9d612.
				  (4) A useful script for AWS credentials - DevNambi.com. https://devnambi.com/2020/set-aws-session.html.
				  (5) Configuration and credential file settings - AWS Command Line Interface. https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html.
				  (6) shell script - Replace environment variables in a file with their .... https://unix.stackexchange.com/questions/294835/replace-environment-variables-in-a-file-with-their-actual-values.
				  (7) Substitute Shell Variables in a Text File | Baeldung on Linux. https://www.baeldung.com/linux/substitute-variables-text-file.
				  (8) Replace environment variables in text if they exist. [linux - Replace environment variables in text if they exist - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/492772/replace-environment-variables-in-text-if-they-exist.)
				  (9) How To Read and Set Environmental and Shell Variables on Linux. [Tutorial  | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-read-and-set-environmental-and-shell-variables-on-linux.)
			- Related: ((658406f2-2d59-4454-9df4-eb8eaa58dd8c))
		- Use `;` to convert multi-line scripts to a single line for terminal usage
		  collapsed:: true
			- ```bash
			  output=$(sudo systemctl status amazon-ssm-agent)
			  status_code=$?
			  echo "output"
			  
			  # Becomes
			  output=$(sudo systemctl status amazon-ssm-agent); status_code=$?; echo "output"
			  ```
		- Optional arguments in Bash
		  collapsed:: true
			- Example
				- build.sh
					- ```bash
					  #!/bin/bash
					  
					  # Usage:
					  #
					  # ./build.sh [OPTIONS]
					  #
					  # Options:
					  #   -d     build web frontend dependencies only
					  #   -s     scrcpy server path (absolute path)
					  #
					  # Build the web frontend and its dependencies.
					  
					  set -e
					  
					  # truncated
					  
					  while getopts "ds:g:" OPTION; do
					  case ${OPTION} in
					  	 d) DEPENDENCIES_ONLY=1 ;;
					  	 s) SCRCPY_SERVER_PATH=${OPTARG} ;;
					  	 g) GNIREHTET_CLIENT_PATH=${OPTARG} ;;
					  esac
					  done
					  
					  # truncated, code which utilises variables mentioned above
					  if [ ${GNIREHTET_CLIENT_PATH} ]; then
					   echo hello
					   mv ${GNIREHTET_CLIENT_PATH} /expected/path/for/dependency.bin
					  fi
					  ```
		- Bash logical OR operator (`||`)
		  collapsed:: true
			- The command before the || is always executed first.
			    The command after the || is executed only if the command before it fails (i.e., exits with a non-zero status).
		- Brace expansion in Bash
		  collapsed:: true
			- `cp --recursive /home/dir1/{deploy.sh,deployment.config,src,README.md} /home/dir2`
			- This uses brace expansion in Bash to specify multiple files/directories to copy from /home/dir1. It expands to:
				- /home/dir1/deploy.sh
				- /home/dir1/deployment.config
				- /home/dir1/src
				- /home/dir1/README.md
			- e.g. `/home/dir1/{a,b,c,d}`
		- `~-` is a Linux env var which is the path for the last directory you were in
		- Bash uses falsey evaluation of undefined shell variables so `if [ ${BUILD_CLIENT} ]; then` is preferable to `if [ ${BUILD_CLIENT:-0} = 1 ]; then`
		- If a variable doesn't exist then it's not possible to use unary/comparison operaors to check if it's a certain value normally, need to use
			- `if [ ${VARIABLE:-0} = 1]; then`
			- `:-` provides a default value
			- Explanation of `${VARIABLE:-0}`
				- If VARIABLE is unset or empty, it defaults to "0"
				- If VARIABLE is set, it uses its value
				- The `:-` provides a default value
				- Prevents errors if the variable doesn't exist
		- `unzip demo.zip -d destination` = unzips to that (existing directory, use mkdir) dir rather than current directory
		- How to run one command as another user
			- `sudo -u username command`
			- `su -c 'command' username`
		- `kill $(pgrep sshd)` == `pkill sshd`
		- `((cycle_count++))` = increment a `cycle_count=1` var
		- Adding text to the bottom of a text file e.g. `echo "hello" >> /path/to/file.txt`
		- `./.command.sh` vs `./command.sh` vs `.command.sh` in bash
		  collapsed:: true
			- Basically `./` prefix is used to execute a script in the same directory
			- ./.command.sh: This refers to a script file named .command.sh located in the current directory. The leading dot makes it a hidden file in Unix-like systems. To execute it, you must use ./.command.sh if it has execution permissions. Hidden scripts are often used for configuration or internal processes.
			- `./command.sh`: This is a standard executable script file in the current directory. The file must have execution permissions (e.g., set via chmod +x command.sh) to run directly. This is the most common way to execute a script.
			- `.command.sh`: This notation is typically used when sourcing a script (i.e., executing it in the current shell session using the source command or the dot . command). For example, . ./.command.sh or source .command.sh will run the script without starting a new subshell. This is useful for applying configuration changes to the current shell environment.
		- `./dir/command.sh` vs `dir/command.sh` in bash
		  collapsed:: true
			- ./dir/command.sh:
			  
			  This explicitly tells the shell to execute the script located in the dir directory relative to the current working directory.
			  
			  The ./ prefix indicates that the script should be run from the current directory. This is useful when the script is not in a directory listed in the PATH environment variable.
			  
			  Using ./ ensures that the shell knows to look in the current directory for the script, which can be important for security reasons, as it prevents accidental execution of scripts from other directories in the PATH.
			  
			  dir/command.sh:
			  
			  This form assumes that dir is in one of the directories specified in the PATH environment variable.
			  
			  If dir is not in the PATH, the shell will not find command.sh and will return an error indicating that the command is not found.
			  
			  If dir is in the PATH, the shell will execute command.sh without needing the ./ prefix.
			  
			  In summary, ./dir/command.sh is used when you want to execute a script located in the current directory's subdirectory and ensure that the shell does not search the PATH for it. On the other hand, dir/command.sh is used when dir is part of the PATH, allowing the shell to locate and execute the script without specifying the current directory.
		- `$PATH` environment variable
			- The `PATH` variable in Linux is an environment variable that tells the shell which directories to search for executable files when running a command. It allows users to run commands from anywhere in the file system without specifying the full path to the executable. For example, instead of typing the full path like /bin/echo, you can simply type echo if /bin is included in the PATH. The PATH variable contains a list of directories separated by colons, and the system checks these directories in order to find the executable file. To view the current value of the PATH variable, you can use the command echo $PATH.
		- `>>` append redirection operator
			- Appends something before the operator to the file given after it
			- E.g. `echo 'touch /home/user/logged' >> /home/user/.profile`
		- Turn a multi-line into one line
			- `sudo apt install -y $(tr '\n' ' ' < packages.txt`
			- `tr '\n' ' '` = translates or transcodes (replace) newline characters (`\n` with just a space ` `). It therefore joins multiple lines into one line
			- `< packages.txt` = the redirection operator `<` is used to take the output from the `txt` and pass it as input to the `tr` command
			- `packages.txt`
				- ```
				  adb
				  steam
				  ffmpeg
				  ```
		- `realpath ${dirname ${0})` in shell
			- `${0}` = name of the current script file
			- `$(dirname $0})` = name of it's directory
			- `realpath ${dirname ${0})` = then trns that relative or symbolic link into an absolute path
		- Variables use `${VAR}` but command substitution uses `$(code)`
		- Related:
			- ((67914a25-8a0d-4741-a10a-9101612cd80f))
			- [[Programming]] : ((65cd3f7c-24c9-4260-b67c-2fe5f005e6a2))
	- Troubleshooting
	  collapsed:: true
		- Login keyring
		  collapsed:: true
			- In VAS/Citrix into Alma Linux desktop to resolve the keyring conflicting with the login password use `rm ~/.local/share/keyrings/login.keyring` to remove the cached keyring pw and then enter the login password in the new prompt.
		- Useful environment variables
		  collapsed:: true
			- `$PWD`
				- `echo $PWD` = prints the current directory full path you're in
			- `$HOME`
		- Use `echo` statements in logs
		  collapsed:: true
			- ((679f62b7-2f3c-4696-94bd-e9c25c035efe))
			- Example
			  ```bash
			  echo "------EXECUTING: ls /data/file------"
			  ls /data/file
			  ```
		- `|` pipe operator for passing values
		  id:: 673767a8-79f9-4a7e-aabf-d57a0fad3b7f
		  collapsed:: true
			- Examples
				- ```bash
				  cat /data/file/hello.txt | base64 > /data/file/hello-encoded.txt
				  echo "$MY_ENV_VAR" | base64 > /data/file/hello-encoded.txt
				  echo "$MY_ENV_VAR" | sed 's/\\n\n/g' > /data/file/hello-encoded.txt
				  ```
			- Related: ((68a119b8-c45c-44ff-8879-49ac30cb6f48))
		- `xargs` for passing values of one command to another
		  id:: 68a119b8-c45c-44ff-8879-49ac30cb6f48
		  collapsed:: true
			- Default `xargs` behaviour
				- ```bash
				  echo "mybook.epub" | xargs fanficfare -u
				  # Becomes: fanficfare -u mybook.epub (appends to end)
				  ```
			- `-I {}`
				- ```bash
				  echo "mybook.epub" | xargs -I {} fanficfare -u {}
				  # Becomes: fanficfare -u mybook.epub (replaces {} with input)
				  ```
				- Pros
					- ### Argument positioning:
						- ```BASH
						  # Put filename in middle of command
						  echo "file.txt" | xargs -I {} cp {} /backup/{}
						  # Becomes: cp file.txt /backup/file.txt
						  ```
				- ### Multiple uses of same argument:
					- ```BASH
					  
					  echo "document.pdf" | xargs -I {} echo "Processing {} and saving {}.bak"
					  # Becomes: echo "Processing document.pdf and saving document.pdf.bak"
					  ```
			- ## Other useful xargs options:
				- ```BASH
				  # -n: Process N arguments at a time
				  echo "file1 file2 file3" | xargs -n 1 echo "Processing:"
				  # Runs: echo "Processing:" file1
				  #       echo "Processing:" file2  
				  #       echo "Processing:" file3
				  
				  # -P: Run commands in parallel
				  find . -name "*.epub" | xargs -P 4 -I {} fanficfare -u {}
				  # Processes 4 files simultaneously
				  
				  # -r: Don't run command if input is empty
				  echo "" | xargs -r echo "This won't run"
				  ```
			- Related: ((673767a8-79f9-4a7e-aabf-d57a0fad3b7f))
		- ((64634a45-ec59-47cb-932f-159ffe39e08a)) to analyse a text file
		  collapsed:: true
		- Adding text to files
		  id:: 658406f2-2d59-4454-9df4-eb8eaa58dd8c
		  collapsed:: true
			- Either `cat` or `printf`
			  id:: 659bc1ff-0861-4b91-afd0-cbccfedf3b46
				- ```bash
				  cat > /date/file.txt << EOL
				  hello
				  world
				  EOL
				  
				  echo "hello world" >> /data/file.txt
				  printf "hello world" >> /data/file.txt
				  ```
			- Related: ((65770a27-6361-4507-9cff-d2f1217d157d))
	- [Learning Resources]
	  collapsed:: true
		- [Shell / Bash Roadmap](https://roadmap.sh/shell-bash)
		- http://linuxcommand.org/
		- http://cli.learncodethehardway.org/book/
		- ![w null_648y3576mbt81.jpg](../assets/w_null_648y3576mbt81_1667135625816_0.jpg)
		- ![fzpfl0d1vq281.png](../assets/fzpfl0d1vq281_1667135660192_0.png)
		- ![w null_j2k4k1j6f1x71.jpg](../assets/w_null_j2k4k1j6f1x71_1667135645020_0.jpg)
		- ![command-line-handbook-2025-05.pdf](../assets/command-line-handbook-2025-05_1749578535869_0.pdf)
			- [Show HN: I wrote a modern Command Line Handbook | Hacker News](https://news.ycombinator.com/item?id=44126612)
			-
		-
		- ![2021-04-28 11.38.34.jpg](../assets/2021-04-28_11.38.34_1696065044304_0.jpg)
		- navigation with Up/Down, search with Ctrl+R, history expansion with  `!!`  and friends, last argument recall with Alt+. or  `$_`
		- https://www.digitalocean.com/community/tutorials/
		- http://linux.die.net
		- http://help.ubuntu.com
		- http://askubuntu.com/ or http://stackoverflow.com/
		- https://www.digitalocean.com/community/tutorials/?primary_filter=popular
		-
- # CLI Utilities
  id:: 673767a8-4dad-4c2e-84d3-02256c35a3a9
	- Meta
		- Lots of tools implement `-` as the last thing you were using e.g. `cd -`, `git switch -`, `git checkout -`, etc
			- `cd -` can take you back to which directory you were previously in
	- [[Git]]
	- coreutils
	- `cd`
	  Change directory
	- `cp`
	  collapsed:: true
	  Copy
		- `cp` flags
		  collapsed:: true
			- The `--recursive` (or `-r`) flag with the cp command in Bash means:
			- Meaning of `--recursive`
				- It instructs cp to copy directories recursively.
				- When copying a directory, it ensures not only the directory itself is copied, but also all its contents including:
					- Subdirectories and their contents
					- All files inside those directories
				- Without this flag being used only files will be copied, no directories
		- `cp` with symbolic links
			- To copy a symbolic link as a link (rather than copying the target file), you should use the -P or --no-dereference option with the cp command. This ensures that the symbolic link is copied as a link, not the file it points to.
		-
	- `if` statement
	  collapsed:: true
		- `if` statement
		  collapsed:: true
			- `-f`
				- File - checks whether file exists
				- E.g. `if [ -f /home/user/exists.txt ];`
		- `if` directory exists in bash
		  collapsed:: true
			- To check if a directory exists:
			  ```bash
			  if [ -d "$DIRECTORY" ]; then
			  echo "$DIRECTORY does exist."
			  fi
			  ```
			- To check if a directory does not exist:
			  ```bash
			  if [ ! -d "$DIRECTORY" ]; then
			  echo "$DIRECTORY does not exist."
			  fi
			  ```
		- [`if`](https://linux.die.net/Bash-Beginners-Guide/sect_07_01.html) 
		  collapsed:: true
			- `-z STRING` = True of the length of "STRING" is zero.
				- Example: if X process isn't running then exit the loop this If statement is in:
				  ```bash
				  if [ -z "$(pgrep sshd)" ]; then
				  exit 1
				  fi
				  ```
		-
	- Emacs
	- Vim
	- yt-dlp
	- `bash`
		- Can be used to execute additional bash scripts
		- Example: `bash checking-script.sh &` = runs that script, in the background (`&`)
	- `wait` = loop waiting for all previously started background processes to finish before continuing with the script
	- ((63209383-221c-406e-a07c-ac95c9a06e71))
	- ((67e7f5f0-b79f-4af3-869f-a220d7e5cdb9))
	- ffmpeg
	- ImageMagick
	- `cat`
	  id:: 673767a8-96fb-4adb-a940-025de96121f9
	  collapsed:: true
		- ((658406f2-2d59-4454-9df4-eb8eaa58dd8c))
	- `bat`
	  ((673767a8-96fb-4adb-a940-025de96121f9)) clone with enhancements
		- [GitHub - sharkdp/bat: A cat(1) clone with wings.](https://github.com/sharkdp/bat) cat alternative recommended by Bertie (AKA `batcat` on Ubuntu)
	- `mkdir`
		- `-p` can make arbitrarily nested directories
	- `printf`
	  collapsed:: true
		- ((658406f2-2d59-4454-9df4-eb8eaa58dd8c))
	- `wc`
	  id:: 64634a45-ec59-47cb-932f-159ffe39e08a
	  collapsed:: true
	  Check bytes and other stats of text file
		- `DEST_DIR_WC=$(cd "$DEST_DIR" && wc -w *.md | awk '{ print $1 }' | paste -sd+ | bc)` = Get the word count of all Markdown files in the `$DEST_DIR` dir
		- collapsed:: true
		  ```bash
		  wc -c /my/file/path.txt
		  wc -m /my/file/path.txt
		  wc --lines /my/file/path.txt
		  ```
	- `systemctl`
	  id:: 6581601b-a5cd-4d5e-83e4-77dd49750f3c
	  collapsed:: true
		- Commands
			- `systemctl restart docker`
			- `systemctl daemon-reload`
			  Reload systemd files
		-
		- Example - how to autostart a program on boot
			- Commands
				- `nano /etc/systemd/system/mega-cmd.service`
					- ```
					  [Unit]
					  Description=Mega-CMD systemd service
					  After=network.target
					  StartLimitIntervalSec=0
					  [Service]
					  Type=simple
					  Restart=on-failure
					  RestartSec=1
					  User=pi
					  ExecStart=/usr/bin/mega-cmd-server
					  
					  [Install]
					  WantedBy=multi-user.target
					  ```
				- `systemctl enable --now mega-cmd`
					- Does both of these:
						- `systemctl start mega-cmd`
						- `systemctl enable mega-cmd`
						  Service will start at boot
				- `systemctl status mega-cmd`
			- [source](https://github.com/meganz/MEGAcmd/issues/88#issuecomment-751341956)
		- Related:
			- ((67b1e143-1d5d-4b5f-87a4-e35a7ae8a7d0))
			- ((6550215b-10a2-4ffa-96bd-ce4dd905c403))
	- `df`
	  collapsed:: true
	  Check disk usage
		- Arguments
			- `.` = Check disk usage of current filesystem
		- Troubleshooting
			- Deleting files isn't giving you free space. Use% is stuck at 100%
			  collapsed:: true
				- The ext3 and ext4 family of filesystems reserve a portion of the disk to keep it from becoming truly "100% full", for stability reasons, and so that the FS can store metadata in some of that space.
				  
				  You can directly tweak how much of the space is reserved:
				  
				  tune2fs -m 1 /dev/sdXX
				  replacing "1" with the percentage (0 to 100) of the disk to reserve, and "XX" with the device node and partition number of the device node, so in your case "XX" would be "b2".
				  
				  Analogy: you have a full bus, and the only remaining seat is next to a very large person who occupies a seat and a half by himself. A person who is very insistent on getting a seat walks up and demands to sit there. Although most people would consider the second seat taken, this person is insistent. So the large person goes, "Whoa, OK!" and squishes in to allow them to sit. But as soon as 1 person gets off the bus and opens up another seat, even if the passenger next to the large person moves into a seat, most people still consider the bus to be 100% full, because nobody wants to sit next to the large person.
				  
				  Source
				  
				  You can also check this to see Reserved Blocks count…
				  
				  dumpe2fs -h /dev/sdb2
				  To quote the very intelligent user who nailed the issue in the source above:
				  
				  You will see "Available" go positive when "Used" is reduced to below 0.95*136236548 blocks = 129424720 blocks roughly.
				  
				  (we have to adjust the "0.95" to the reserved % in your specific case, and the 136236548 blocks to the total block size of your device).
	- `pkill`
	  collapsed:: true
		- `kill $(pgrep Grayjay)` equivalent to `pkill -9 Grayjay`
		- Flags
			- Most Common Signals:
				- `-9` (SIGKILL): Force kill immediately, cannot be caught or ignored by the process
				- `-15` (SIGTERM): Default signal, graceful termination request, can be caught by process
				- `-2` (SIGINT): Interrupt signal, same as pressing Ctrl+C
				- `-1` (SIGHUP): Hangup signal, often used to reload configurations
				- `-3` (SIGQUIT): Quit signal, similar to SIGTERM but also produces a core dump
			- Additional Useful pkill Flags:
				- `-f`: Match against full command line, not just process name
				- `-u username`: Only kill processes owned by specific user
				- `-t terminal`: Kill processes running on specific terminal
				- `-n`: Select most recently started process
				- `-o`: Select oldest process
		- Best Practices:
			- Try SIGTERM (-15) first for graceful shutdown
			- Use SIGKILL (-9) only as a last resort as it can leave resources in inconsistent states
			- SIGHUP (-1) is useful for daemons that support configuration reloading
	- `trap`
	  collapsed:: true
		- [The Bash Trap Command | Linux Journal](https://www.linuxjournal.com/content/bash-trap-command)
		-
	- `find`
	  collapsed:: true
		- `find . -type d -name "node_modules" -prune -exec rm -rf '{}' +`
		  collapsed:: true
			- 1. find .
				- find: This is a Unix command used to search for files and directories in a directory hierarchy.
				- .: The starting point for the search, here it means the current directory and all its subdirectories recursively.
			- 2. -type d
				- This option filters the search to include only directories (d stands for directories).
				- So find will look for directories only, ignoring regular files or other types.
			- 3. -name "node_modules"
				- This option further filters the results so that only directories with the exact name "node_modules" are matched.
				- It is case sensitive.
				- The "node_modules" is the target directory name we want to find.
			- 4. -prune
				- -prune tells find not to descend into the matched directories.
				- This is useful here because node_modules directories can be very large and deep, and since we want to delete them wholly, we don’t want to traverse inside them unnecessarily.
				- It prunes (excludes) the subdirectory contents from further searching.
			- 5. -exec rm -rf '{}' +
				- -exec: This option runs a command on each matched file/directory.
				- rm -rf: The command that removes files/directories recursively and forcefully:
				- rm: remove command.
				- -r: recursively remove directories and their contents.
				- -f: force deletion without prompting.
				- '{}': Placeholder for the current file or directory found by find. It represents each matched node_modules directory.
				- +: This symbol at the end means that rm -rf will be invoked once with multiple arguments (i.e., multiple matched directories are passed in one command) rather than launching one rm for each directory, making the deletion more efficient.
		- Use `find` to locate the first file with a given filename
			- `apk=${find directory/to/search -type f -name "app-debug.apk" print -quit)`
		-
	- `less`
	  Pager i.e. reading documentation
		- `git config --help | less +/push.autoSetupRemote` = execute `git config --help ` to open that docs in pager, pipe it to `less` with `+/` prefix and jump to the line with `push.autoSetupRemote`
	- [Beyond Compare - Wikipedia](https://en.wikipedia.org/wiki/Beyond_Compare) can be used to compare two directories, files, archives
	- ## Categories
		- ((673767a8-4dad-4c2e-84d3-02256c35a3a9))
		- Package managers
		  id:: 673767a8-88e3-47f1-84bc-65932795709e
		  collapsed:: true
			- Meta
				- Basic commands for each package manager
				  collapsed:: true
					- ![image.png](../assets/image_1703373260642_0.png)
			- # Examples
				- [GitHub - kdeldycke/meta-package-manager: 🎁 wraps all package managers with a unifying CLI](https://github.com/kdeldycke/meta-package-manager)
					- Ironically has to be installed through a package manager like `uv`, which can be installed via `brew install uv`or `pipx install uv`
				- ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) : ((63baa386-4747-40e9-b222-ab1fb5ab1bf6))
				- [sdkman](https://sdkman.io/)
				  id:: 683864dd-0965-42eb-819d-fe8fdd524c26
		- Terminal multiplexers
		  collapsed:: true
			- Features
				- They allow you to manage multiple terminal sessions within a single terminal window or SSH connection
			- Software
			  collapsed:: true
				- `screen`
				  id:: 65c9f527-a611-4d38-af26-680d91d29506
					- Pros/Cons
					  collapsed:: true
						- Pros
							-
						- Cons
							-
						- Unclear
						- Comparisons
							- ((d585592c-b9c5-4e53-abdc-eddfe05c39a3))
					- How to use
						-
				- [`tmux`](https://github.com/tmux/tmux)
				  id:: 65c9f52b-520f-4dc8-84b0-86d5f96590a8
				  collapsed:: true
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Features
							  collapsed:: true
								- Some of its top features include:
									- **Session Management**: `tmux` allows you to create multiple sessions, each containing one or more windows, and each window containing one or more panes. This makes it easy to organize and switch between different tasks or projects.
									- **Window and Pane Splitting**: Within a `tmux` session, you can split windows both horizontally and vertically, allowing you to view multiple terminal sessions simultaneously. This is particularly useful for tasks like monitoring multiple logs or running multiple commands concurrently.
									- **Session Detachment and Reattachment**: `tmux` sessions can be detached from the terminal and later reattached, allowing you to keep long-running processes running even after you disconnect from the terminal or log out. This makes `tmux` especially useful for remote server management or for running tasks in the background.
									- **Customizable Key Bindings**: `tmux` allows you to customize key bindings for various commands and actions, making it easy to create shortcuts for common tasks and workflows.
									- **Scriptability**: `tmux` can be controlled and scripted using its command-line interface, allowing for automation and integration with other tools and workflows.
									- **Session Sharing and Collaboration**: `tmux` supports multi-user sessions, allowing multiple users to connect to the same session simultaneously. This makes it possible to collaborate on tasks or troubleshoot issues together in real-time.
									- **Named Sessions and Windows**: Sessions and windows in `tmux` can be given user-defined names, making it easy to identify and switch between them.
									- **Scrollback Buffer**: `tmux` includes a scrollback buffer, allowing you to scroll up and view previously displayed output even after it has scrolled off the screen.
									- **Status Bar and Visual Customization**: `tmux` includes a status bar at the bottom of the terminal window, which displays information such as the current session name, window name, and other status indicators. This status bar can be customized and configured to display additional information or be hidden entirely.
									- **Plug-in and Extension Support**: `tmux` has a vibrant ecosystem of plug-ins and extensions that extend its functionality even further, offering features such as enhanced status bars, session management tools, and more.
						- Cons
							-
						- Unclear
						- Comparisons
							- ((65c9f52b-520f-4dc8-84b0-86d5f96590a8)) vs ((65c9f527-a611-4d38-af26-680d91d29506))
							  id:: d585592c-b9c5-4e53-abdc-eddfe05c39a3
								- For ((65c9f52b-520f-4dc8-84b0-86d5f96590a8))
									-
								- For ((65c9f527-a611-4d38-af26-680d91d29506))
								- ((63f8fe5a-255e-4682-b228-cc2790a41d73)):
									- **Usability**:
										- `tmux`: Known for its modern and intuitive interface, `tmux` offers a more user-friendly experience with features like easy window and pane splitting, customizable key bindings, and a cleaner status bar.
										- `screen`: `screen` has been around for longer and may have a steeper learning curve for new users due to its less intuitive interface and configuration options. However, it has a straightforward and simple command set once you get used to it.
									- **Configuration**:
										- `tmux`: `tmux` offers extensive customization options, allowing users to configure key bindings, customize the status bar, and more. Configuration is typically done through a configuration file (`~/.tmux.conf`) or through runtime commands.
										- `screen`: Configuration in `screen` is typically done through command-line options or by modifying the `.screenrc` configuration file. While `screen` provides some customization options, it may not be as extensive as `tmux`.
									- **Window and Pane Management**:
										- `tmux`: `tmux` provides more advanced window and pane management features, including support for nested splits, synchronized input between panes, and resizable panes.
										- `screen`: While `screen` also supports window and pane splitting, its capabilities may be more limited compared to `tmux`. Screen also lacks synchronized input between panes by default.
									- **Scrollback Buffer**:
										- `tmux`: `tmux` includes a scrollback buffer, allowing you to scroll up and view previously displayed output even after it has scrolled off the screen.
										- `screen`: `screen` also includes a scrollback buffer with similar functionality to `tmux`.
									- **Scriptability**:
										- `tmux`: `tmux` provides a powerful command-line interface that can be scripted and automated using shell scripts or other programming languages.
										- `screen`: Similarly, `screen` can also be scripted and automated, but its scripting capabilities may not be as flexible or modern as `tmux`.
									- **Active Development**:
										- `tmux`: `tmux` is actively developed and maintained, with regular updates and new features being added by the open-source community.
										- `screen`: `screen` development has slowed down in recent years, with fewer updates and new features being introduced compared to `tmux`.
									- In summary, while both `tmux` and `screen` serve similar purposes as terminal multiplexers, `tmux` generally offers a more modern and feature-rich experience with better usability, extensive customization options, and more advanced window and pane management capabilities. However, `screen` may still be preferred by some users due to its simplicity, stability, and longstanding presence in the Unix ecosystem. Ultimately, the choice between `tmux` and `screen` depends on individual preferences, requirements, and familiarity with each tool.
					- # [Documentation](https://linux.die.net/man/1/tmux)
						- [Wiki](https://github.com/tmux/tmux/wiki)
							- [Getting started](https://github.com/tmux/tmux/wiki/Getting-Started)
						- How to use
							- **Detach a Session**:
								- First, create a new detached session in tmux using the `-d` flag:
								  ```
								  $ tmux new-session -d -s my_session your_application
								  ```
							- **Attach to the Session Later**:
								- To reattach to the detached session:
								  
								  ```
								  $ tmux attach-session -t my_session
								  ```
						- ## Terms
							- Window = tabs
						- ## Keybindings
						  id:: 673767a8-951c-4fb9-83e8-33c6688a9716
						  collapsed:: true
							- ### `CTRL + B` = Prefix key
								- Type this before any command to ensure that tmux responds to the keybinding and not the shell itself
							- ### Sort by priority to learn
								- ((688a2c88-19da-4c83-9e05-f19d4051b49a))
								  id:: 67aa9265-5737-4c07-a8f2-288feebb90a1
								- ((67aaa115-1efd-4261-9b41-80a4f4e09553))
								- ((3e89c6ac-cce7-48ec-bf26-a38f61098d32))
							- ### Sorted by category
							  id:: 67aaa115-1efd-4261-9b41-80a4f4e09553
								- Pane management
									- ((67aa8d04-bfbc-4bd5-a8f6-bcb7e9774622))
									- ((67aa8cfb-f3ee-4d0c-8ce8-0fdfe17cfb46))
									- ((67aaa340-8fbb-4d67-ab0a-5e88a2f2c098))
										- {{embed ((67aaa340-8fbb-4d67-ab0a-5e88a2f2c098))}}
									- ((4229a814-b136-46b8-af24-4c111e61cb12))
									- ((67aa9def-ed96-4edb-a8ad-e551e70692f7))
									- ((eaeeec85-1f23-4f02-890f-e21b8589815a))
									- ((59bfd859-78f6-434f-9b09-51e4a252fc1b))
								- Window management
									- ((88a65992-fa70-4b18-8b5a-1bcb7ce40ded))
									- ((902632ab-c424-4483-997d-0c60a93c8374))
									- ((67aa936f-a1f9-4c99-889b-f008df8d1fbb))
									- ((65da5b95-18db-409d-8c27-fa704a869d19))
									- ((219d4ec5-33f1-4944-86d6-0abb172bb8b3))
									- ((04db1fd3-be9e-4215-875d-70e68463f45a))
									- ((21cbd27d-b931-4366-b3ad-4d7fcfa916db))
								- Session management
									- ((5dd76b5e-21d5-4826-88f9-b96a5bf4efc3))
									- ((8106bec6-96b0-4e99-8b6c-9c393222ae7f))
									- Related:
										- ((67aa8dc6-58ac-4e38-a66d-1a2b105dcfbd))
							- ### Sorted by ((688a2c88-19da-4c83-9e05-f19d4051b49a))
							  Last updated: [[2025-02-10 Monday]] | Note: `M` = `ALT`
								- `CTRL + b` =  Send the prefix key
								- `CTRL + o` = Rotate through the panes
								  id:: eaeeec85-1f23-4f02-890f-e21b8589815a
								- C-b C-z     Suspend the current client
								- C-b Space   Select next layout
								- C-b !       Break pane to a new window
								- `"` = Split vertically
								  id:: 67aa8d04-bfbc-4bd5-a8f6-bcb7e9774622
								- C-b #       List all paste buffers
								- `$` = Rename current session
								  id:: 5dd76b5e-21d5-4826-88f9-b96a5bf4efc3
								- `%` = Split window horizontally
								  id:: 67aa8cfb-f3ee-4d0c-8ce8-0fdfe17cfb46
								- `&` = Kill current window
								  id:: 902632ab-c424-4483-997d-0c60a93c8374
								- C-b '       Prompt for window index to select
								- C-b (       Switch to previous client
								- C-b )       Switch to next client
								- `,` = Rename current window
								  id:: 65da5b95-18db-409d-8c27-fa704a869d19
								- C-b -       Delete the most recent paste buffer
								- `.` = Move the current window
									- Can press a number after to specify what it becomes? unclear
								- C-b /       Describe key binding
								- `<number>` = Select window `<number>`
								  id:: 67aa936f-a1f9-4c99-889b-f008df8d1fbb
								  collapsed:: true
									- C-b 0       Select window 0
									- C-b 1       Select window 1
									- C-b 2       Select window 2
									- C-b 3       Select window 3
									- C-b 4       Select window 4
									- C-b 5       Select window 5
									- C-b 6       Select window 6
									- C-b 7       Select window 7
									- C-b 8       Select window 8
									- C-b 9       Select window 9
								- `:` = Prompt for a command
								- C-b ;       Move to the previously active pane
								- C-b =       Choose a paste buffer from a list
								- `?` = List keybindings
								  id:: 688a2c88-19da-4c83-9e05-f19d4051b49a
								- C-b C       Customize options
								- C-b D       Choose and detach a client from a list
								- C-b E       Spread panes out evenly
								- C-b L       Switch to the last client
								- C-b M       Clear the marked pane
								- C-b [       Enter copy mode
								- C-b ]       Paste the most recent paste buffer
								- `c`  = Create a new window
								  id:: 88a65992-fa70-4b18-8b5a-1bcb7ce40ded
								- `d` = Detach the current client
								  id:: 3e89c6ac-cce7-48ec-bf26-a38f61098d32
								- C-b f       Search for a pane
								- C-b i       Display window information
								- C-b l       Select the previously current window
								- C-b m       Toggle the marked pane
								- `n`  =  Select the next window (cycle focus)
								  id:: 219d4ec5-33f1-4944-86d6-0abb172bb8b3
									- How you can visually tell = `*` suffix gets appended to the end of the name of the window
								- C-b o       Select the next pane
								- `p` = Select the previous window (cycle focus)
								  id:: 04db1fd3-be9e-4215-875d-70e68463f45a
								- C-b q       Display pane numbers
								- C-b r       Redraw the current client
								- `s` = Choose a session from a list
								  id:: 8106bec6-96b0-4e99-8b6c-9c393222ae7f
								- C-b t       Show a clock
								- `w` = Choose a window from a list
								  id:: 21cbd27d-b931-4366-b3ad-4d7fcfa916db
								- `x` = Kill the active pane
								  id:: 59bfd859-78f6-434f-9b09-51e4a252fc1b
								- `z` = Maximise/minimise the active pane
								  id:: 4229a814-b136-46b8-af24-4c111e61cb12
								  AKA Zoom
									- How you can visually tell = `Z` suffix gets appended to the end of the name of the window
								- C-b {       Swap the active pane with the pane above
								- C-b }       Swap the active pane with the pane below
								- C-b ~       Show messages
								- C-b DC      Reset so the visible part of the window follows the cursor
								- C-b PPage   Enter copy mode and scroll up
								- `<arrow keys>` = Cycle pane focus
								  id:: 67aa9def-ed96-4edb-a8ad-e551e70692f7
								  collapsed:: true
									- C-b Up      Select the pane above the active pane
									- C-b Down    Select the pane below the active pane
									- C-b Left    Select the pane to the left of the active pane
									- C-b Right   Select the pane to the right of the active pane
								- Layouts
								  id:: 67aaa340-8fbb-4d67-ab0a-5e88a2f2c098
									- `ALT + 1` =  Set the even-horizontal layout
									  id:: 6695b528-d265-4c77-a4ef-1d62b30ecb5e
									- `ALT + 2` =  Set the even-vertical layout
									  id:: 55b7fbb8-bb5f-4075-a06a-26a5387d1b62
									- `ALT + 3` =  Set the main-horizontal layout
									- `ALT + 4` =  Set the main-vertical layout
									- `ALT + 5` = Set the tiled layout
								- C-b M-n     Select the next window with an alert
								- C-b M-o     Rotate through the panes in reverse
								- C-b M-p     Select the previous window with an alert
								- C-b M-Up    Resize the pane up by 5
								- C-b M-Down  Resize the pane down by 5
								- C-b M-Left  Resize the pane left by 5
								- C-b M-Right Resize the pane right by 5
								- C-b C-Up    Resize the pane up
								- C-b C-Down  Resize the pane down
								- C-b C-Left  Resize the pane left
								- C-b C-Right Resize the pane right
								- C-b S-Up    Move the visible part of the window up
								- C-b S-Down  Move the visible part of the window down
								- C-b S-Left  Move the visible part of the window left
								- C-b S-Right Move the visible part of the window right
							- ### Non-prefix
								- Hold `SHIFT` = allows you to select text whilst in mouse-mode
						- ## Commands
							- Meta
								- `'='` can be used to exact match
								  collapsed:: true
									- `tmux attach -t '=Assorted2'`
										- `tmux attach -t Assorted2`
							- `tmux` = Open tmux in terminal
							- ### Flags
								- `-d`: This flag stands for "detached".
								  collapsed:: true
									- When creating a new session or window, using `-d` will cause `tmux` not to attach to the created session or window immediately. Instead, it creates the session or window in the background and returns to the shell prompt without attaching to it. This is useful for starting `tmux` sessions in scripts or for situations where you want the session to run in the background without attaching to it right away.
								- `-s`: This flag stands for "session".
								  collapsed:: true
									- It is used to specify the name of the session when creating a new session or attaching to an existing one. For example, if you have a session named "work", you can attach to it using `tmux attach-session -s work`. If the session doesn't exist and you're creating a new one, you can use `-s` to specify its name, like `tmux new-session -s work`.
								- `-t`: This flag stands for "target".
								  collapsed:: true
									- It is used to specify the target window or pane when sending commands to `tmux`. For example, if you want to send a command to a specific window or pane within a session, you would use `-t` followed by the target specification. For example, `tmux send-keys -t session_name:window_index.command` would send the specified command to the designated window within the specified session. Similarly, `tmux send-keys -t session_name:window_index.pane_index.command` would send the command to a specific pane within a specific window of the specified session. This flag is often used with commands like `send-keys` to direct input to a specific location within a `tmux` session.
							- `tmux ls` = list active tmux sessions
							- `tmux attach` = attach terminal to specified tmux session
							- `tmux detach` = Detach from current tmux session
							- `tmux new` = Create new session
							  id:: 67aa8dc6-58ac-4e38-a66d-1a2b105dcfbd
							  collapsed:: true
							  AKA `tmux new-session`
								- Flags
									- `-- <command>` or `'<command>'` = Run command immediately in shell
										- Examples
											- `$ tmux new 'emacs ~/.tmux.conf'`
											- `$ tmux new -- emacs ~/.tmux.conf`
									- `-s<name>` = Specify a name for the session
										- `$ tmux new -smysession`
									- `-d` = Detach (opens in the background)
									- `-n<name>` = Give the first window in the session a specific name, instead of it automatically being given the name of the command running in it
										- `$ tmux new -nmytopwindow top`
						- `~/.tmux.conf` conf file
							- `tmux source ~/.tmux.conf` = hot reload
							- ```
							  # Better pane splitting (using | and -)
							  bind | split-window -h
							  bind - split-window -v
							  unbind '"'
							  unbind %
							  ```
						- ## Troubleshooting
							- Using nested tmux with remote SSH
							  collapsed:: true
								- Create a conf file on the remote server to use a different prefix key than the host
									- ```shell
									  cat << 'EOF' > ~/.tmux.conf
									  # Unbind the default prefix key
									  unbind C-b
									  
									  # Set the new prefix key to Ctrl+a
									  set-option -g prefix C-a
									  
									  # Ensure Ctrl+a functions as the new prefix
									  bind C-a send-prefix
									  
									  # Other useful options can be added here
									  # For example, enable mouse support
									  set -g mouse on
									  
									  # Set a custom status bar color
									  set-option -g status-bg colour235
									  set-option -g status-fg colour136
									  EOF
									  ```
								- Save the script to a file, for example, `setup_tmux.sh`.
								- Make the script executable: `chmod +x setup_tmux.sh`.
								- Run the script: `./setup_tmux.sh`.
							- Moving pane to window
							  collapsed:: true
								- [Moving tmux pane to window - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/14300/moving-tmux-pane-to-window/14301#14301)
								-
							- Selecting text with mouse support - hold down `SHIFT`
					- [Changelog](https://github.com/tmux/tmux/commits/master/CHANGES)
					- # Ecosystem
						- [GitHub - rothgar/awesome-tmux: A list of awesome resources for tmux](https://github.com/rothgar/awesome-tmux?tab=readme-ov-file#plugins)
					-
					- I use tmux for remote sessions in case of disconnect but not for local sessions.
					- TMUX for local are:
						- It's very easy to add a new shell (control-b c) and then do whatever you would do in a new terminal window. This keeps your number of OS terminal windows to a minimum. It's also easier and faster for me to switch between shells using TMUX instead of clicking to find the correct OS terminal window, or using OS keys to switch windows. It's much faster and more direct for me to press control-b 4 to go to the 4th shell in my TMUX session.
						- Scroll back history is actually faster and easier with TMUX than with the scroll bar, even when you use the center mouse wheel. I find that I very often scroll past what I want because the mouse scroll wheel is inaccurate and overshoots in both directions. I have what I think are some VERY friendly TMUX key maps that make scrolling back into history very easy and accurate. It's also very helpful that TMUX scrollback history is SEARCHABLE. So if you know the word you want to find, you just quickly type it and BAM you're there. Bonus that I can then use TMUX copy and paste to grab values or commands or whatever and then paste them into the current shell or into other shells.
						- The consistency of having my remote and local sessions look and feel exactly the same means my brain doesn't have to switch gears as much. This leads to a "flow" and peace of mind while working.
					- [Learning Resources]
						- tmux
						  collapsed:: true
							- tmux cheastsheet [Ultimate tmux (v2.3) Cheat Sheet by cloudranger - Download free from Cheatography - Cheatography.com: Cheat Sheets For Every Occasion](https://cheatography.com/cloudranger/cheat-sheets/ultimate-tmux-v2-3/)
							- `~/.tmux.conf`
								- ```
								  setw -g mouse on
								  bind | split-window -h
								  bind - split-window -v
								  unbind '"'
								  unbind %
								  set-option -g default-shell /bin/bash
								  ```
								- `default-shell` needed when using devcontainers in WSL
						- [Tmux Cheat Sheet & Quick Reference | Session, window, pane and more](https://tmuxcheatsheet.com/)
						- [[Page not found](https://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/](https://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/))
					- {Archive}
						- [- YouTube](https://www.youtube.com/watch?v=vtB1J_zCv8I&t=0s)
						-
				- [shpool](https://github.com/shell-pool/shpool)
				  collapsed:: true
		- Soft links
		  collapsed:: true
			- `ln -s /path/to/original /path/to/link`
			- `ls -l softlink_name` To see what a softlink currently points to
				- Or try `ls <path>` where path is where the soft link points to
			- To update a soft link, either remove and recreate it or use force flag `ln -sfn /home/user/documents mydocs`
		- Modern alternatives for `cd`/`ls`
		  collapsed:: true
			- `cd -` = go back to last directory
			- https://superuser.com/questions/308575/alternatives-to-cd-ls-for-command-line-navigation
			- https://github.com/ajeetdsouza/zoxide for cd alternative
			- https://github.com/eza-community/eza for ls alternative
			- bat for cat alternative
		- Writing `.xz` compressed image or `img` uncompressed to a SD card
		  collapsed:: true
			- https://gitlab.com/bztsrc/usbimager recommended by Armbian https://docs.armbian.com/User-Guide_Getting-Started/#preparing-sd-card
			- Alternative: `dd`
		- Data Recovery
		  collapsed:: true
			- `safecopy`
				- Find out USB mount point
					- `lsblk`
					- `sudo fdisk -l`
				- `sudo apt-get install safecopy`
				- `sudo safecopy /dev/sdx /path/to/image.img`
			- `gddrescue`
				- Example
					- `sudo ddrescue -f /dev/sdX image_file logfile`
			- Mounting
				- `sudo mkdir /mnt/image`
				- `sudo mount -o loop /path/to/image.img /mnt/image`
		- `whereis`
		  collapsed:: true
			- e.g. `whereis steam` = show path of executable
		- AI-powered
		  id:: 663a57ae-0b8a-408d-a1e4-98b64cdb2ae7
		  collapsed:: true
			- [GitHub - TheR1D/shell_gpt: A command-line productivity tool powered by GPT-3 and GPT-4, will help you accomplish your tasks faster and more efficiently.](https://github.com/TheR1D/shell_gpt)
			- [GitHub - m1guelpf/plz-cli: Copilot for your terminal](https://github.com/m1guelpf/plz-cli)
			- [GitHub Next | Copilot for CLI](https://githubnext.com/projects/copilot-cli)
			- Related: ((663b6831-1b8a-4d66-b029-53facf290f8c))
	- TUIs
	  id:: 673767a8-239b-49d2-a5b2-bc9cba54b2c8
	  collapsed:: true
		- Pros/Cons
			- Pros
				- Easier to cross-platform
		- [Ask HN: Interesting TUIs (text user interfaces), maybe forgotten ones? | Hacker News](https://news.ycombinator.com/item?id=40273177)
		- [`isd`](https://isd-project.github.io/isd/)
		  collapsed:: true
		  a better way to work with `systemd` units
			- Related: [GitHub - rgwood/systemctl-tui: A fast, simple TUI for interacting with systemd services and their logs](https://github.com/rgwood/systemctl-tui)
			-
		- `ncdu`
		- File Managers
			- [Ranger](https://ranger.github.io/)
			  Used by Aidan at BAE
				- [GitHub - ranger/ranger: A VIM-inspired filemanager for the console](https://github.com/ranger/ranger)
			- [GitHub - jarun/nnn: n³ The unorthodox terminal file manager](https://github.com/jarun/nnn)
			- [GitHub - sxyazi/yazi: 💥 Blazing fast terminal file manager written in Rust, based on async I/O.](https://github.com/sxyazi/yazi)
			- `mc`
			  AKA [Midnight Commander](https://midnight-commander.org/)
			- [Screenshots - Vifm](https://vifm.info/gallery)
			-
		- [Learning Resources]
		  collapsed:: true
			- `tput cup 2 0` for example is a way to move the cursor position to a specific location in the terminal screen. Useful for writing TUIs
		- Related: ((67e7f5e8-faec-4139-9ce1-99c39a9076a7))
	- ### [Learning Resources]
	  collapsed:: true
		- [How I use my terminal | Hacker News](https://news.ycombinator.com/item?id=44356646)
		- [GitHub - jarun/advcpmv: A patch for GNU Core Utilities cp, mv to add progress bars](https://github.com/jarun/advcpmv) good alternative to `cp`/`mv` with progress bars. Alternative to `rsync`
		- Highest rated
			- `awk`/`sed`
			- ((d585592c-b9c5-4e53-abdc-eddfe05c39a3))
			- `mosh`
			- `fzf` + `ctrl+R` search for a previous command in a bash shell. Game changer.
			- `find`
				- Debugging Next.js TypeScript Node project
					- Use the `find` command listed below in order to remove every `node_modules` directory. Had to do this for `node_modules`, `esm` in a TypeScript Node Next.js project to ensure all the temporary build files were removed in order to debug why the Next.js watch task wasn't working (`workspace demo run dev`)
					- Also removed `.tsbuildinfo` files using `find . -type f -name "*.tsbuildinfo" -exec rm -f '{}' +`
					- `find .` — start searching from the current directory.
					- `-type f` — look only for files.
					- `-name "*.tsbuildinfo"` — match files ending with .tsbuildinfo.
					- `-exec rm -f '{}' +` — delete the matched files efficiently in batches without prompting.
					- `yarn` in the web files directory (it's equivalent to `yarn install`, or `yarn path/to/dir` to install the files. Then restarted watch mode
					- It seems Next.js can't use Watch Mode with multiple directories/workspaces. Had to restart Watch Mode each time
			- `regex`
			- `zoxide`
		-
		- `tldr`
		  collapsed:: true
		  man pages on steroids with usage examples
			- tldr lspci " (no quotes)
			  will give you the following;
			  
			  tldr lspci
			  
			  lspci
			  List all PCI devices.
			  
			  More information: [No manual entry for /lspci. - manned.org](https://manned.org/lspci.)
			- Show a brief list of devices:
			  lspci
			- Display additional info:
			  lspci -v
			- Display drivers and modules handling each device:
			  lspci -k
			- Show a specific device:
			  lspci -s 00:18.3
			- Dump info in a readable form:
			  lspci -vm
			- ​in essence a very abbreviated for of the 'man' pages.
			  if you can remember the command, but not all the ways to use it - this can be a great memory refresher.
		- GPU-accelerated Alacritty running Oh My Zsh that's enhanced with productivity tools like fzf, exa, bat, zoxide and starship.There's also awesome tools like lazydocker, lazygit, btop and neovim pushing the limits of what's possible in a terminal UI and distrobox which lets me easily run Ubuntu VMs to install experimental software without impacting my Fedora Desktop.
		- musikcube -- the best terminal-based audio/streaming player by miles
		- micro -- sorry, but I hate vim (*heresy, I know)* and nano feels like someone's abandoned side project.
		- zoxide - better `cd`
		- `tldr` - better `man`
		- `exa` - better `ls`
		- `duf` - better `df`
		- `wcurl`
		  collapsed:: true
			- [Ubuntu Server 25.10](https://alternativeto.net/software/ubuntu-server/about/) will no longer include [wget](https://alternativeto.net/software/wget/about/) in its default installation, opting instead for wcurl, a wrapper included with [curl](https://alternativeto.net/software/curl/about/) 8.14.x, as the new standard for command-line downloads. This decision is part of Ubuntu's strategy to streamline its server distribution by eliminating redundant tools. wcurl is designed to serve as a drop-in replacement for wget, translating most basic wget commands for compatibility with curl. Users who require advanced wget features can still manually install it from the core repository, with full support and security updates guaranteed throughout the Ubuntu 25.10 support cycle.
			- [wcurl](https://curl.se/wcurl/)
				- Instead of...
				- wget https://mirrors.rit.edu/ubuntu-releases/24.04.3/ubuntu-24.04.3-desktop-amd64.iso
				- ...you can use
				- wcurl https://mirrors.rit.edu/ubuntu-releases/24.04.3/ubuntu-24.04.3-desktop-amd64.iso
			-
			-
			- `aria2` - better `wget`
		- `bat` - better `cat`
		- ((65c9f52b-520f-4dc8-84b0-86d5f96590a8))
		  collapsed:: true
		- ssh in connection with nc
		  collapsed:: true
			- Seriously... ssh + nc combo is insanely powerful if you know how to use it. Port-forwarding anything anywhere, forward tunnels, reverse tunnels, firewall hole-punching, forwarding traffic forward and and backward through a corporate HTTP proxy, being able to act as HTTP proxy if need be ...
			  
			  The things ssh can do when coupled with nc are insane.
			- I’ve just recently setup a reverse ssh tunnel + socat forward to allow people inside one firewall access computers inside another firewall, transparently.
			  
			  I had to use an external relay to get it to work because of corporate it policies, but it works really well.
			  
			  Transparent rdp to a windows machine inside a nat’ed network from another heavily firewalled network, all over a secure reverse ssh tunnel.
			  
			  [EDIT] I've done a separate post on the method I used for this:
				- # [How to access RDP over a reverse SSH Tunnel](https://www.reddit.com/r/linux/comments/1ak27fb/how_to_forward_any_service_over_a_reverse_ssh/)
				  collapsed:: true
					- Due to numerous requests for a HOWTO on [this](https://libreddit.northboot.xyz/r/linux/comments/1ajslo3/what_are_your_most_valuable_and_loved_command/)
					  thread, below is a little example of how to implement a reverse SSH 
					  tunnel and then forward any service to/from another machine in the same 
					  network.
					  
					  For the purpose of this exercise we'll have a remote Windows machine 
					  we want to access using RDP, and in the same remote network behind a 
					  firewall we'll have a linux machine that we'll use to setup the tunnel 
					  and forward the connection. We'll call these machines "windowspc" and 
					  "linuxpc" respectively.
					  
					  We will require a publicy-accessible machine through which to relay 
					  our packets; we'll call this machine "relay". This will also be running 
					  linux. For the purpose of this exercise we'll assume that it's wide 
					  open, but in practice it should be firewalled as tightly as possible for
					  whatever clients you are connecting from. In my case, I have restricted
					  the packets to be only from a particular subnet; I did this at the 
					  router level so the relay machine doesn't know or care about these 
					  restrictions. I also have the router setup to NAT unusual ports to the 
					  relay just as an extra minor level of security.
					  
					  The windowspc shouldn't have any configuration applied to it, except 
					  to allow rdp from local network. Note that this happens by default on 
					  port 3389, so we'll need to forward to that port on the windows machine 
					  when we get to that.
					- # Setup the Reverse Tunnel for direct SSH access
					  
					  We don't strictly need this for our end goal of an rdp relay, but 
					  it's still useful to both test the reverse tunnel, and also to allow us 
					  to remotely administer the linux pc if we should need to. This step will
					  demonstrate the basic concepts of the tunnel without the added 
					  complexity of the service forward. The ssh key generation and transfer 
					  is still required for all services though, so don't skip that part.
					  
					  We'll need to setup the reverse ssh tunnel to the linuxpc. To do 
					  this, ensure openssh-server is installed on the linuxpc, and the relay. 
					  We assume the relay's SSH server is listening on port 2022.
					  
					  On the linuxpc, we need to setup the ssh keys to access the relay without a password:
					  
					  ```
					  ssh-keygen
					  ssh-copy-id -p user@relay.public.ip
					  ```
					  
					  On the linuxpc, we run the following command to setup the tunnel:
					  
					  `ssh -f -N -R 2222:localhost:22 -p 2022 -o ServerAliveInterval=60 user@relay.public.ip`
					  
					  The options to ssh are as follows:
					- -f : Fork on tunnel creation (go to background)
					- -N : Don't create a prompt on the remote machine
					- -R <inport>:<IP>:<outport> : Create a reverse 
					  tunnel, where: * <inport> is the port we reference when accessing 
					  the tunnel * <IP> is the IP we use when accessing the tunnel * 
					  <outport> is the port we want on the machine where the tunnel 
					  originated.
					- -p <number> : The port on the relay we need to access the ssh server **on the relay**
					- -o ServerAliveInterval <seconds> : We use this so when we 
					  create the tunnel it doesn't die after a period of inactivity, useful 
					  when starting from a systemd script for example
					- user@ip - The user on the relay machine that the tunnel will be created for.
					  
					  If that succeeds, then I should be able to open a shell on the relay machine, and perform the following:
					  
					  ```
					  user@relay:~> ssh -p 2222 linuxuser@localhost
					  linuxuser@linuxpc:~>
					  ```
					  
					  Note that the port 2222 on localhost at relay has been forwarded to 
					  the port 22 on the linuxpc, using the reverse ssh tunnel! So we can now 
					  access the linuxpc, which is sitting behind a firewall and possibly on 
					  an unroutable network from the internet by logging in to the relay and 
					  then doing a simple 'ssh localhost'.
					- # SSH to remote PC without logging in to relay
					  
					  That's all well and good, but what if we want to just login directly 
					  to the linuxpc without first SSH'ing to the relay? Well, with the magic 
					  of socat we can manage that. Socat creates a bidirectional network 
					  forward, and is quite simple to setup.
					  
					  Assuming that port 12322 is open on the relay, we setup a socat port forward on the relay computer:
					  
					  ```
					  user@relay:~> socat TCP-LISTEN:12322,fork TCP:localhost:2222
					  ```
					  
					  This sets up the port forward on the relay computer, so we can now access the linuxpc from anywhere in the world!
					  
					  ```
					  anyuser@anywhere:~> ssh -p 12322 linuxuser@relay.public.ip
					  linuxuser@linuxpc:~>
					  ```
					- # Forward RDP to the Windows computer
					  
					  So now we have all the tools to do the entire chain from an arbitrary
					  computer on the internet to the windows PC inside the firewall. We need
					  to make a couple of socat forward instances (one on the relay and one 
					  on the linuxpc), and run them over a reverse ssh tunnel.
					  
					  I'll just write the commands without too much explanation. The trick 
					  is making sure your ports line up, and that when you do the socat you 
					  can't forward to the same port you're listening on for the reason that 
					  the port is already in use when you're listening on it (remember it's a 
					  bidirectional forward).
					  
					  On the linux PC, setup a reverse SSH tunnel, and a socat forward to the windows pc:
					  
					  ```
					  linuxuser@linuxpc:~> ssh -f -N -R 33389:localhost:33389 -p 2022 user@relay.public.ip
					  linuxuser@linuxpc:~> socat TCP-LISTEN:33389,fork TCP:windowspclocal:3389
					  ```
					  
					  Then we setup a socat from the relay to the tunnel port of 33389:
					  
					  ```
					  user@relay:~> socat TCP-LISTEN:12389,fork TCP:localhost:33389
					  ```
					  
					  For clarity, I've set the listen port to be 12389, to differentiate 
					  from the 3389 of the linuxpc socat, but we could make it any port. Now 
					  from anywhere in the world, we should be able to RDP to the windows PC, 
					  using the normal RDP clients, just make sure to set the port to 12389. 
					  When you open your rdp client, set the target to be `relay.public.ip:12389`, and use the windows computer credentials to login.
					- # Security Implications
					  
					  I'm not a security expert by any means, but note that there are a 
					  couple of security issues here. Mostly, we are opening the windows PC to
					  anywhere on the internet, so if you're worried about that (you should 
					  be!), lock down your relay firewall to only accept connections from 
					  either a certain computer or subnet as appropriate.
					  
					  In my case I've set the relay user to root, but as I've set it up as a
					  VM and the only thing it does is to run the relay, I'm not overly 
					  concerned about the security of the root user. If you set your relay ssh
					  server to only allow connections using an ssh key pair, that will also 
					  help with some security.
					  
					  There's also a whole bunch of ssh key transfer that happens between 
					  the computers to make access more convenient, but that's beyond the 
					  scope of this post - it's not too hard to figure out where those need to
					  be done and were omitted for clarity of the ssh/socat process.
					  
					  I've wrapped everything up in a bunch of systemd services so they all
					  start at boot, the extra little trick for that is for the ssh reverse 
					  tunnel you'll need to set `Type=forking` in the service otherwise 
					  systemd thinks it's hung and tries to restart it constantly. 
					  Alternatively, it should be possible remove the '-f' ssh option instead,
					  but I haven't tested that explicitly.
					- # Summary
					  
					  You should now be able to setup a reverse tunnel to/from a remote 
					  computer that's on a NAT'ed, non-routable network, and then forward that
					  connection to another computer inside that same network for arbitrary 
					  service access from the internet.
					  
					  Thanks for coming to my TED talk :-).
					  
					  [EDIT] Fixed a couple of typos, added some clarification; added systemd stuff; edited to make it read a bit better.
					- Comment section
						- Forwarding a service on a remote machine to be accessible on your local machine, on Linux:
							- `~/.ssh/config`
							- Under a Host entry:
							- `LocalForward localIP:localPort remoteIP:remotePort`
							- Establish the ssh session, connect to localIP:localPort on your machine and you have access.
							- Add as many of these directives as you want. Bind them to the default
							  port on your local machine, use any 127.x.x.x IP and set up a `etc/hosts` entry, make it easy on yourself. Webserver for docker? Local IP 127.1.2.3, port 80, add a hosts entry to make it `docker.remote` or something. :p
		- `jq` for json
		- `yq` for yaml
		- `find` for file selection
		- `sed/awk/perl` (data filtering and massaging)
		- pv - monitor the progress of data through a pipe
		  collapsed:: true
			- ... but it's all about the glue! I have this in a shell script called ~/bin/,pv
			  
			  ```
			  exec /usr/bin/time nocache tar cpS "$@" --sort=name | pv -bratpes $(du -cks "$@"|sed -n '/.total$/ s/.total$//p')k
			  ```
			  
			  and from a source directory, I do something like
			  
			  ```
			  ,pv files-to-copy | nocache tar xp -C /destination/directory
			  ```
			  
			  or of course
			  
			  ```
			  ,pv files-to-copy | ssh otherhost -c 'nocache tar xp -C /destination/directory'
			  ```
			  
			  ... for which I have aliases.
			  
			  Notes:
			- exec means that the shell script process disappears, since it's not going to do anything else.
			- /usr/bin/time reports the total time (etc.) after the process is done.
			- nocache makes the processes skip the filesystem cache, so copying a 
			  bunch of files doesn't push the stuff I want in the cache out.
			- The -s option to pv, and the output of the following subcommand 
			  $(...) tells pv how big all of the files are in advance, so it can 
			  provide an ETA in the status output.
			- For other details ... check the manpages. I don't remember.
			  
			  > Why does it start with a comma? Almost all my shell and almost everything in my ~/bin do. This is the most useful and effective shell 
			  tip I have ever received: [https://rhodesmill.org/brandon/2009/commands-with-comma/](https://rhodesmill.org/brandon/2009/commands-with-comma/)
		- https://github.com/agarrharr/awesome-cli-apps
		- Ansible, makes it easy to manage multiple servers.
		- [Lazygit](https://github.com/jesseduffield/lazygit), simple TUI to manage git repository.
		- [Lazydocker](https://github.com/jesseduffield/lazydocker), simple TUI to manage docker.
		- [Mosh](https://github.com/mobile-shell/mosh), remote 
		  shell that supports intermittent connectivity, allows roaming. Mosh 
		  keeps the session alive if the client goes to sleep and wakes up later, 
		  or temporarily loses its Internet connection.
		- [Tailscale](https://tailscale.com/), connect securely to devices behind a firewall or NAT.
		- [Navi](https://github.com/denisidoro/navi), TUI cheatsheet, make your own cheatsheet of difficult to remember commands. Searchable with fzf.
		- \* mock AWS services [https://github.com/spulec/moto](https://github.com/spulec/moto)
		- \* query cloud services [https://github.com/turbot/steampipe](https://github.com/turbot/steampipe)
		- \* munge CSV [https://github.com/johnkerl/miller](https://github.com/johnkerl/miller) [https://github.com/BurntSushi/xsv](https://github.com/BurntSushi/xsv)
		- \* page json [https://github.com/PaulJuliusMartinez/jless](https://github.com/PaulJuliusMartinez/jless)
		- \* text to tree structure \[I use this as a hack to version control my music library\] [https://github.com/birchb1024/frangipanni](https://github.com/birchb1024/frangipanni)
		- [Topgrade](https://github.com/topgrade-rs/topgrade), 
		  updater. Keeps your system up to date by updating/upgrading all package 
		  managers. Configurable with a *.toml. I have it setup to update pacman, 
		  yay, vim, nvim, git pull repositories.
		- Stow, all my dotfiles are in a git repository. Stow symlinks them in the correct path. [https://systemcrafters.net/managing-your-dotfiles/using-gnu-stow/](https://systemcrafters.net/managing-your-dotfiles/using-gnu-stow/).
		- [Atuin](https://atuin.sh/), syncable shell history. Can also be used as a fully-offline enhanced history search tool.
		- [Bat](https://github.com/sharkdp/bat), A cat clone with syntax highlighting and Git integration.
		- [Ripgrep](https://github.com/BurntSushi/ripgrep), rust based grep replacement.
		- [Zoxide](https://github.com/ajeetdsouza/zoxide), A smarter cd command. Supports all major shells. Aliased to cd. eval "$(zoxide init --cmd cd zsh)"
		- [Tealdear](https://github.com/dbrgn/tealdeer), A very fast implementation of tldr in Rust.
		- [Dua-cli](https://github.com/Byron/dua-cli), View disk space usage and delete unwanted data, fast. NCDU replacement, faster.
		- [Youtube-dl](https://github.com/ytdl-org/youtube-dl), download videos from youtube and other video sites.
		- ZSH with  zsh-autosuggestions, zsh-syntax-highlighting and [powerlevel10k](https://github.com/romkatv/powerlevel10k) theme.
		- https://github.com/Textualize/toolong
		- [GitHub - httpie/cli: 🥧 HTTPie CLI  — modern, user-friendly command-line HTTP client for the API era. JSON support, colors, sessions, downloads, plugins & more.](https://github.com/httpie/cli)
		- [GitHub - sharkdp/hyperfine: A command-line benchmarking tool](https://github.com/sharkdp/hyperfine)
		- [GitHub - sayanarijit/xplr: A hackable, minimal, fast TUI file explorer](https://github.com/sayanarijit/xplr)
		- Lots
			- `netstat`
				- `netstat -lt4n`
					- ipv4
			- bash, git, ssh, awk, sed, grep, tr, cat, cut, tac, wc, ls, and cd.
			- Edit: as some have pointed out and some more they didn't: vim, convert, nslookup, dig, ping, nmap, strace, gdb, netstat, ss, ffmpeg, cvlc, xdotool, find, scp, rsync, mplayer, diff, nc, tcpdump, openssl, telnet, dmesg
			- Edit 2: jq, date, wget, curl, man, dd, ddrescue, cdrecord, dos2unix, uudecode, file, hexdump, binwalk, foremost, lftp, lshw, less, more, ipcalc, mc, minicom, pv, whois, who, w, last, ansible, tar, bzip2, zip
			- curl, dig, traceroute, whois, wget, ping and nmap
			- nping, tcptraceroute, mtr, iperf, nc & host (hostx package)
			- netstat, nslookup, fish, zoxide, [eza](https://github.com/eza-community/eza), snapper, corectrl, neovim, bpytop, iotop, ss
			- fd (modern find) and rg (modern grep)
		- [GitHub - junegunn/fzf: :cherry_blossom: A command-line fuzzy finder](https://github.com/junegunn/fzf)
		-
	- Related: ((6828f01e-8b60-49cf-9e5f-becd6a246cc1))
- # Frameworks
	- Terminal UI (TUI) toolkits
	  collapsed:: true
		- [Ink](https://github.com/vadimdemedes/ink) - ((629ccb26-62cc-426a-9616-4d8969f32580))
		- [GitHub - charmbracelet/bubbletea: A powerful little TUI framework 🏗](https://github.com/charmbracelet/bubbletea)
		- [GitHub - fdehau/tui-rs: Build terminal user interfaces and dashboards using Rust](https://github.com/fdehau/tui-rs)
		- [GitHub - Textualize/textual: The lean application framework for Python.  Build sophisticated user interfaces with a simple Python API. Run your apps in the terminal and a web browser.](https://github.com/textualize/textual)
		- [GitHub - gui-cs/Terminal.Gui: Cross Platform Terminal UI toolkit for .NET](https://github.com/gui-cs/Terminal.Gui)
		- [GitHub - ArthurSonzogni/FTXUI: :computer: C++ Functional Terminal User Interface. :heart:](https://github.com/ArthurSonzogni/FTXUI)
		- [GitHub - p-gen/smenu: smenu started as a lightweight and flexible terminal menu generator, but quickly evolved into a powerful and versatile CLI selection tool for interactive or scripting use.](https://github.com/p-gen/smenu)
		-
		- Ecosystem
			- [GitHub - spf13/cobra: A Commander for modern Go CLI interactions](https://github.com/spf13/cobra)
			-
	- Testing sandbox
		- Scripting
			- Creating a multi-line file. test test
			  collapsed:: true
				- Scripting
				  collapsed:: true
					- Creating a multi-line file
					  collapsed:: true
						- Here's a shell script that will add the following to a file at `~/.aws/credentials`, replacing the $ prefixed values with their environment variables:
						  collapsed:: true
							- This script uses a ((661e6277-3a5c-4d27-9a29-79f3620f3da7)) to write the contents of the file to `~/.aws/credentials`. The `${}` syntax is used to substitute the environment variables in the file with their corresponding values.
							- ```sh
							  #!/bin/bash
							  
							  cat <<EOF > ~/.aws/credentials
							  [default]
							  output = json
							  region = eu-west-1
							  aws_access_key_id = ${AWS_access_key_id_value}
							  aws_secret_access_key = ${aws_secret_access_key}
							  aws_session_token = ${aws_session_token}
							  EOF
							  ```
						- Equivalent as a shell command requires `\n` for line breaks
						  collapsed:: true
							- ```bash
							  echo -e "[default]\noutput = json\nregion = eu-west-1\naws_access_key_id = ${AWS_access_key_id_value}\naws_secret_access_key = ${aws_secret_access_key}\naws_session_token = ${aws_session_token}" > ~/.aws/credentials`
							  ```
						- Source: Conversation with Bing, 11/12/2023
						  collapsed:: true
							- (1) How to manage credentials for a shell script that uses AWS CLI?. https://stackoverflow.com/questions/74281038/how-to-manage-credentials-for-a-shell-script-that-uses-aws-cli.
							  (2) Setting AWS Credentials, Script Task and PowerShell - Atlassian Community. https://community.atlassian.com/t5/Bamboo-questions/Setting-AWS-Credentials-Script-Task-and-PowerShell/qaq-p/711326.
							  (3) Getting Temporary Credential on AWS CloudShell - Medium. https://medium.com/@daichiharada/getting-temporary-credential-on-aws-cloudshell-9a7da5a9d612.
							  (4) A useful script for AWS credentials - DevNambi.com. https://devnambi.com/2020/set-aws-session.html.
							  (5) Configuration and credential file settings - AWS Command Line Interface. https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html.
							  (6) shell script - Replace environment variables in a file with their .... https://unix.stackexchange.com/questions/294835/replace-environment-variables-in-a-file-with-their-actual-values.
							  (7) Substitute Shell Variables in a Text File | Baeldung on Linux. https://www.baeldung.com/linux/substitute-variables-text-file.
							  (8) Replace environment variables in text if they exist. [linux - Replace environment variables in text if they exist - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/492772/replace-environment-variables-in-text-if-they-exist.)
							  (9) How To Read and Set Environmental and Shell Variables on Linux. [Tutorial  | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-read-and-set-environmental-and-shell-variables-on-linux.)
						- Related: ((658406f2-2d59-4454-9df4-eb8eaa58dd8c))
					- Conditional based on exit status of a command
					  collapsed:: true
						- ```bash
						  ./my_program # or just do a one line command
						  if [ $? -eq 0 ]; then
						      echo "Success: Result is 0"
						  elif [ $? -eq 1 ]; then
						      echo "Success: Result is 1"
						      exit 1  # Set exit status of this script to 1
						  else
						      echo "Failure: Result is neither 0 nor 1"
						  fi
						  ```
							- `[ ... ]`: In Bash, `[` is a built-in command also known as `test`. It's used for evaluating conditional expressions. The `[` command is typically followed by a space-separated list of arguments and ends with `]`. It's important to have spaces around the square brackets for correct syntax.
							- `$?`: This is a special variable in Bash that holds the exit status of the last command executed. After executing a command, `$?` stores its exit status, which is an integer value indicating whether the command succeeded (usually 0) or failed (a non-zero value).
							- `-eq`: This is an operator used within the `test` command to check for equality. It evaluates to true if the operands are equal.
							- `0`: This is the value we are comparing `$?` against. In this context, `0` represents success, as it is a common convention in Unix-like systems for programs to return 0 upon successful execution.
						- ```bash
						  output=$(./run_script.sh)
						  status_code=$?
						  
						  if [[ $status_code -eq 0 ]]; then
						  	echo "Ran successfully."
						  else
						  	echo "Ran unsuccessfully."
						  fi
						  ```
					- Use `;` to convert multi-line scripts to a single line for terminal usage
					  collapsed:: true
						- ```bash
						  output=$(sudo systemctl status amazon-ssm-agent)
						  status_code=$?
						  echo "output"
						  
						  # Becomes
						  output=$(sudo systemctl status amazon-ssm-agent); status_code=$?; echo "output"
						  ```
					- [Here Documents](https://tldp.org/LDP/abs/html/here-docs.html) `<<`
					  collapsed:: true
					  Can be used to add multi-lines of string into files from the terminal for example
						- Syntax
							- ```bash
							  COMMAND <<InputComesFromHERE
							  ...
							  ...
							  ...
							  InputComesFromHERE
							  ```
						- Examples
							- ```bash
							  cat << EOF > /tmp/yourfilehere
							  These contents will be written to the file.
							          This line is indented.
							  EOF
							  ```
					- Related: [[Programming]] : ((65cd3f7c-24c9-4260-b67c-2fe5f005e6a2))
				- Scripting
					- Creating a multi-line file
					  collapsed:: true
						- Here's a shell script that will add the following to a file at `~/.aws/credentials`, replacing the $ prefixed values with their environment variables:
							- This script uses a ((661e6277-3a5c-4d27-9a29-79f3620f3da7)) to write the contents of the file to `~/.aws/credentials`. The `${}` syntax is used to substitute the environment variables in the file with their corresponding values.
							- ```sh
							  #!/bin/bash
							  
							  cat <<EOF > ~/.aws/credentials
							  [default]
							  output = json
							  region = eu-west-1
							  aws_access_key_id = ${AWS_access_key_id_value}
							  aws_secret_access_key = ${aws_secret_access_key}
							  aws_session_token = ${aws_session_token}
							  EOF
							  ```
						- Equivalent as a shell command requires `\n` for line breaks
							- ```bash
							  echo -e "[default]\noutput = json\nregion = eu-west-1\naws_access_key_id = ${AWS_access_key_id_value}\naws_secret_access_key = ${aws_secret_access_key}\naws_session_token = ${aws_session_token}" > ~/.aws/credentials`
							  ```
						- Source: Conversation with Bing, 11/12/2023
							- (1) How to manage credentials for a shell script that uses AWS CLI?. https://stackoverflow.com/questions/74281038/how-to-manage-credentials-for-a-shell-script-that-uses-aws-cli.
							  (2) Setting AWS Credentials, Script Task and PowerShell - Atlassian Community. https://community.atlassian.com/t5/Bamboo-questions/Setting-AWS-Credentials-Script-Task-and-PowerShell/qaq-p/711326.
							  (3) Getting Temporary Credential on AWS CloudShell - Medium. https://medium.com/@daichiharada/getting-temporary-credential-on-aws-cloudshell-9a7da5a9d612.
							  (4) A useful script for AWS credentials - DevNambi.com. https://devnambi.com/2020/set-aws-session.html.
							  (5) Configuration and credential file settings - AWS Command Line Interface. https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html.
							  (6) shell script - Replace environment variables in a file with their .... https://unix.stackexchange.com/questions/294835/replace-environment-variables-in-a-file-with-their-actual-values.
							  (7) Substitute Shell Variables in a Text File | Baeldung on Linux. https://www.baeldung.com/linux/substitute-variables-text-file.
							  (8) Replace environment variables in text if they exist. [linux - Replace environment variables in text if they exist - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/492772/replace-environment-variables-in-text-if-they-exist.)
							  (9) How To Read and Set Environmental and Shell Variables on Linux. [Tutorial  | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-read-and-set-environmental-and-shell-variables-on-linux.)
						- Related: ((658406f2-2d59-4454-9df4-eb8eaa58dd8c))
					- Conditional based on exit status of a command
					  collapsed:: true
						- ```bash
						  ./my_program # or just do a one line command
						  if [ $? -eq 0 ]; then
						      echo "Success: Result is 0"
						  elif [ $? -eq 1 ]; then
						      echo "Success: Result is 1"
						      exit 1  # Set exit status of this script to 1
						  else
						      echo "Failure: Result is neither 0 nor 1"
						  fi
						  ```
							- `[ ... ]`: In Bash, `[` is a built-in command also known as `test`. It's used for evaluating conditional expressions. The `[` command is typically followed by a space-separated list of arguments and ends with `]`. It's important to have spaces around the square brackets for correct syntax.
							- `$?`: This is a special variable in Bash that holds the exit status of the last command executed. After executing a command, `$?` stores its exit status, which is an integer value indicating whether the command succeeded (usually 0) or failed (a non-zero value).
							- `-eq`: This is an operator used within the `test` command to check for equality. It evaluates to true if the operands are equal.
							- `0`: This is the value we are comparing `$?` against. In this context, `0` represents success, as it is a common convention in Unix-like systems for programs to return 0 upon successful execution.
						- ```bash
						  output=$(./run_script.sh)
						  status_code=$?
						  
						  if [[ $status_code -eq 0 ]]; then
						  	echo "Ran successfully."
						  else
						  	echo "Ran unsuccessfully."
						  fi
						  ```
					- Use `;` to convert multi-line scripts to a single line for terminal usage
						- ```bash
						  output=$(sudo systemctl status amazon-ssm-agent)
						  status_code=$?
						  echo "output"
						  
						  # Becomes
						  output=$(sudo systemctl status amazon-ssm-agent); status_code=$?; echo "output"
						  ```
					- [Here Documents](https://tldp.org/LDP/abs/html/here-docs.html) `<<`
					  Can be used to add multi-lines of string into files from the terminal for example
						- Syntax
							- ```bash
							  COMMAND <<InputComesFromHERE
							  ...
							  ...
							  ...
							  InputComesFromHERE
							  ```
						- Examples
							- ```bash
							  cat << EOF > /tmp/yourfilehere
							  These contents will be written to the file.
							          This line is indented.
							  EOF
							  ```
					- Related: [[Programming]] : ((65cd3f7c-24c9-4260-b67c-2fe5f005e6a2))
				- Scripting
					- Creating a multi-line file
					  collapsed:: true
						- Here's a shell script that will add the following to a file at `~/.aws/credentials`, replacing the $ prefixed values with their environment variables:
							- This script uses a ((661e6277-3a5c-4d27-9a29-79f3620f3da7)) to write the contents of the file to `~/.aws/credentials`. The `${}` syntax is used to substitute the environment variables in the file with their corresponding values.
							- ```sh
							  #!/bin/bash
							  
							  cat <<EOF > ~/.aws/credentials
							  [default]
							  output = json
							  region = eu-west-1
							  aws_access_key_id = ${AWS_access_key_id_value}
							  aws_secret_access_key = ${aws_secret_access_key}
							  aws_session_token = ${aws_session_token}
							  EOF
							  ```
						- Equivalent as a shell command requires `\n` for line breaks
						  collapsed:: true
							- ```bash
							  echo -e "[default]\noutput = json\nregion = eu-west-1\naws_access_key_id = ${AWS_access_key_id_value}\naws_secret_access_key = ${aws_secret_access_key}\naws_session_token = ${aws_session_token}" > ~/.aws/credentials`
							  ```
						- Source: Conversation with Bing, 11/12/2023
						  collapsed:: true
							- (1) How to manage credentials for a shell script that uses AWS CLI?. https://stackoverflow.com/questions/74281038/how-to-manage-credentials-for-a-shell-script-that-uses-aws-cli.
							  (2) Setting AWS Credentials, Script Task and PowerShell - Atlassian Community. https://community.atlassian.com/t5/Bamboo-questions/Setting-AWS-Credentials-Script-Task-and-PowerShell/qaq-p/711326.
							  (3) Getting Temporary Credential on AWS CloudShell - Medium. https://medium.com/@daichiharada/getting-temporary-credential-on-aws-cloudshell-9a7da5a9d612.
							  (4) A useful script for AWS credentials - DevNambi.com. https://devnambi.com/2020/set-aws-session.html.
							  (5) Configuration and credential file settings - AWS Command Line Interface. https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html.
							  (6) shell script - Replace environment variables in a file with their .... https://unix.stackexchange.com/questions/294835/replace-environment-variables-in-a-file-with-their-actual-values.
							  (7) Substitute Shell Variables in a Text File | Baeldung on Linux. https://www.baeldung.com/linux/substitute-variables-text-file.
							  (8) Replace environment variables in text if they exist. [linux - Replace environment variables in text if they exist - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/492772/replace-environment-variables-in-text-if-they-exist.)
							  (9) How To Read and Set Environmental and Shell Variables on Linux. [Tutorial  | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-read-and-set-environmental-and-shell-variables-on-linux.)
						- Related: ((658406f2-2d59-4454-9df4-eb8eaa58dd8c))
					- Conditional based on exit status of a command
						- ```bash
						  ./my_program # or just do a one line command
						  if [ $? -eq 0 ]; then
						      echo "Success: Result is 0"
						  elif [ $? -eq 1 ]; then
						      echo "Success: Result is 1"
						      exit 1  # Set exit status of this script to 1
						  else
						      echo "Failure: Result is neither 0 nor 1"
						  fi
						  ```
							- `[ ... ]`: In Bash, `[` is a built-in command also known as `test`. It's used for evaluating conditional expressions. The `[` command is typically followed by a space-separated list of arguments and ends with `]`. It's important to have spaces around the square brackets for correct syntax.
							- `$?`: This is a special variable in Bash that holds the exit status of the last command executed. After executing a command, `$?` stores its exit status, which is an integer value indicating whether the command succeeded (usually 0) or failed (a non-zero value).
							- `-eq`: This is an operator used within the `test` command to check for equality. It evaluates to true if the operands are equal.
							- `0`: This is the value we are comparing `$?` against. In this context, `0` represents success, as it is a common convention in Unix-like systems for programs to return 0 upon successful execution.
						- ```bash
						  output=$(./run_script.sh)
						  status_code=$?
						  
						  if [[ $status_code -eq 0 ]]; then
						  	echo "Ran successfully."
						  else
						  	echo "Ran unsuccessfully."
						  fi
						  ```
					- Use `;` to convert multi-line scripts to a single line for terminal usage
					  collapsed:: true
						- ```bash
						  output=$(sudo systemctl status amazon-ssm-agent)
						  status_code=$?
						  echo "output"
						  
						  # Becomes
						  output=$(sudo systemctl status amazon-ssm-agent); status_code=$?; echo "output"
						  ```
					- [Here Documents](https://tldp.org/LDP/abs/html/here-docs.html) `<<`
					  collapsed:: true
					  Can be used to add multi-lines of string into files from the terminal for example
						- Syntax
							- ```bash
							  COMMAND <<InputComesFromHERE
							  ...
							  ...
							  ...
							  InputComesFromHERE
							  ```
						- Examples
							- ```bash
							  cat << EOF > /tmp/yourfilehere
							  These contents will be written to the file.
							          This line is indented.
							  EOF
							  ```
					- Related: [[Programming]] : ((65cd3f7c-24c9-4260-b67c-2fe5f005e6a2))
				- Here's a shell script that will add the following to a file at `~/.aws/credentials`, replacing the $ prefixed values with their environment variables:
					- This script uses a ((661e6277-3a5c-4d27-9a29-79f3620f3da7)) to write the contents of the file to `~/.aws/credentials`. The `${}` syntax is used to substitute the environment variables in the file with their corresponding values.
					- ```sh
					  #!/bin/bash
					  
					  cat <<EOF > ~/.aws/credentials
					  [default]
					  output = json
					  region = eu-west-1
					  aws_access_key_id = ${AWS_access_key_id_value}
					  aws_secret_access_key = ${aws_secret_access_key}
					  aws_session_token = ${aws_session_token}
					  EOF
					  ```
				- Equivalent as a shell command requires `\n` for line breaks
				  collapsed:: true
					- ```bash
					  echo -e "[default]\noutput = json\nregion = eu-west-1\naws_access_key_id = ${AWS_access_key_id_value}\naws_secret_access_key = ${aws_secret_access_key}\naws_session_token = ${aws_session_token}" > ~/.aws/credentials`
					  ```
				- Source: Conversation with Bing, 11/12/2023
				  collapsed:: true
					- (1) How to manage credentials for a shell script that uses AWS CLI?. https://stackoverflow.com/questions/74281038/how-to-manage-credentials-for-a-shell-script-that-uses-aws-cli.
					  (2) Setting AWS Credentials, Script Task and PowerShell - Atlassian Community. https://community.atlassian.com/t5/Bamboo-questions/Setting-AWS-Credentials-Script-Task-and-PowerShell/qaq-p/711326.
					  (3) Getting Temporary Credential on AWS CloudShell - Medium. https://medium.com/@daichiharada/getting-temporary-credential-on-aws-cloudshell-9a7da5a9d612.
					  (4) A useful script for AWS credentials - DevNambi.com. https://devnambi.com/2020/set-aws-session.html.
					  (5) Configuration and credential file settings - AWS Command Line Interface. https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html.
					  (6) shell script - Replace environment variables in a file with their .... https://unix.stackexchange.com/questions/294835/replace-environment-variables-in-a-file-with-their-actual-values.
					  (7) Substitute Shell Variables in a Text File | Baeldung on Linux. https://www.baeldung.com/linux/substitute-variables-text-file.
					  (8) Replace environment variables in text if they exist. [linux - Replace environment variables in text if they exist - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/492772/replace-environment-variables-in-text-if-they-exist.)
					  (9) How To Read and Set Environmental and Shell Variables on Linux. [Tutorial  | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-read-and-set-environmental-and-shell-variables-on-linux.)
				- Related: ((658406f2-2d59-4454-9df4-eb8eaa58dd8c))
		- Conditional based on exit status of a command
		  collapsed:: true
			- ```bash
			  ./my_program # or just do a one line command
			  if [ $? -eq 0 ]; then
			      echo "Success: Result is 0"
			  elif [ $? -eq 1 ]; then
			      echo "Success: Result is 1"
			      exit 1  # Set exit status of this script to 1
			  else
			      echo "Failure: Result is neither 0 nor 1"
			  fi
			  ```
				- `[ ... ]`: In Bash, `[` is a built-in command also known as `test`. It's used for evaluating conditional expressions. The `[` command is typically followed by a space-separated list of arguments and ends with `]`. It's important to have spaces around the square brackets for correct syntax.
				- `$?`: This is a special variable in Bash that holds the exit status of the last command executed. After executing a command, `$?` stores its exit status, which is an integer value indicating whether the command succeeded (usually 0) or failed (a non-zero value).
				- `-eq`: This is an operator used within the `test` command to check for equality. It evaluates to true if the operands are equal.
				- `0`: This is the value we are comparing `$?` against. In this context, `0` represents success, as it is a common convention in Unix-like systems for programs to return 0 upon successful execution.
			- ```bash
			  output=$(./run_script.sh)
			  status_code=$?
			  
			  if [[ $status_code -eq 0 ]]; then
			  	echo "Ran successfully."
			  else
			  	echo "Ran unsuccessfully."
			  fi
			  ```
			- Use `;` to convert multi-line scripts to a single line for terminal usage
			  collapsed:: true
				- ```bash
				  output=$(sudo systemctl status amazon-ssm-agent)
				  status_code=$?
				  echo "output"
				  
				  # Becomes
				  output=$(sudo systemctl status amazon-ssm-agent); status_code=$?; echo "output"
				  ```
			- [Here Documents](https://tldp.org/LDP/abs/html/here-docs.html) `<<`
			  collapsed:: true
			  Can be used to add multi-lines of string into files from the terminal for example
				- Syntax
					- ```bash
					  COMMAND <<InputComesFromHERE
					  ...
					  ...
					  ...
					  InputComesFromHERE
					  ```
				- Examples
					- ```bash
					  cat << EOF > /tmp/yourfilehere
					  These contents will be written to the file.
					          This line is indented.
					  EOF
					  ```
			- Related: [[Programming]] : ((65cd3f7c-24c9-4260-b67c-2fe5f005e6a2))
		- Related: [[Programming]] : ((65cd3f7c-24c9-4260-b67c-2fe5f005e6a2))
- Related:
	- ((6336ac7d-9081-4a23-b7e5-0474a8023b4d))