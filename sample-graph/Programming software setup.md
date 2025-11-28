- Steps
	- ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) : ((63974fb0-ef9b-4610-9d0a-fb5337fbfefc))
	- ((63209272-1088-4824-a762-4ac7ded04b0a))
	- ((646349ad-a758-4162-98a2-67e78cef36f4))
	- Run some commands to allow use of `puppeteer` ((634bc0c1-c4b8-488f-9c11-5918d0bfb50d)) package
	  collapsed:: true
		- `sudo sysctl -w kernel.unprivileged_userns_clone=1`
		- Then do ((63734d16-ee7e-4f5a-8812-ba9d334e17aa))
		- Needed into order to run `puppeteer` npm package
		- [source] [puppeteer/troubleshooting.md at main · puppeteer/puppeteer · GitHub](https://github.com/puppeteer/puppeteer/blob/main/docs/troubleshooting.md#setting-up-chrome-linux-sandbox)
	- Modify `fs.inotify.max_user_watches` to allow Visual Studio Code to watch for file changes
	  collapsed:: true
		- Steps
			- `cat /proc/sys/fs/inotify/max_user_watches`
			- `sudo nano /etc/sysctl.conf`
			- `fs.inotify.max_user_watches=524288` - add this to end of file. Note: this is the maximum
			- `sudo sysctl -p` = load in the value
			- [source] https://code.visualstudio.com/docs/setup/linux#_visual-studio-code-is-unable-to-watch-for-file-changes-in-this-large-workspace-error-enospc
- Related: [[PC]] : ((62d4471d-2ebd-46b8-b700-3b6362e06c80))