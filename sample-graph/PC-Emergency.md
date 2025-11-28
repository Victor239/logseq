# OS Reinstall
	- [[2024-08-06 Tuesday]] Reinstall notes
		- Note that some directories need to be in paths for Flatpaks to appear on desktop
			- '/var/lib/flatpak/exports/share'
			- '/home/boss/.local/share/flatpak/exports/share'
			- are not in the search path set by the XDG_DATA_DIRS environment variable, so applications installed by Flatpak may not appear on your desktop until the
			  session is restarted.
		- ^^Maybe also make ansible.yml and other files available in a private git repo^^
		- Restoring latest Vorta backup ontop of an older local backup
		  collapsed:: true
			- Restore using a local backup (eg rsync from an external NVME)
			- Ansible install script. Maybe also need to be synced with latest version, possibly in a git repo
			- Open Vorta > click a cloud profile (eg rsync.net) > Archives > refresh button. This will show the latest backups. Do the same for the other cloud location(s)
			- Mount the newest archive to ~/Mounts/mount3/
			- Start restoring via rsync
			- = ISSUE: can't use `sudo` rsync. Test this via `ls /home/boss/Mounts/mount3/home/boss/Documents/ESSENTIALS/installs/` and `sudo ls /home/boss/Mounts/mount3/home/boss/Documents/ESSENTIALS/installs/`
				- This way doesn't seem to work well, couldn't attach a .ssh successfully
				  collapsed:: true
					- Install it system-wide too
						- sudo flatpak remote-add --if-not-exists --system flathub-sys  https://flathub.org/repo/flathub.flatpakrepo
						  #sudo flatpak install --system 
						  flatpak install flathub-sys com.borgbase.Vorta
						  flatpak list --system
					- Run it as root
						- sudo -i
						  /usr/bin/flatpak run --branch=stable --arch=x86_64 --command=vorta com.borgbase.Vorta
				- [Run Backup Task with Root Permission · borgbase/vorta · Discussion #801 · GitHub](https://github.com/borgbase/vorta/discussions/801#discussioncomment-3384761)
					- Need to run Vorta as root in order to properly copy all files via rsync? Actually nah, it shouldn't backup root files in the first place unless I've already been using this
						- `sudo cp /home/boss/Documents/ESSENTIALS/installs/com.borgbase.Vorta.policy /usr/share/polkit-1/actions/com.borgbase.Vorta.policy
						  cat /usr/share/polkit-1/actions/com.borgbase.Vorta.policy`
					- Launch it
					  `pkexec vorta`
					- Symlink so it can run with just `vorta`, and makes the policy file work unchanged
					  `sudo ln -s /home/boss/.local/share/flatpak/app/com.borgbase.Vorta/current/active/export/bin/com.borgbase.Vorta /usr/bin/vorta`
	- [[2024-07-28 Sunday]] `/media/boss/1TB-Expansion/emergency-restore-sop.txt`
	  collapsed:: true
		- Restore as much as possible from a local backup on NAS/Framework external drive/external drive
		- Mount the latest Vorta backup, then rsync from the mounted archive to local drive
		- Example (this will delete files in /home/boss that don't exist in /media source):
		- sudo rsync -avz --delete --info=progress2 /media/1TB-Expansion/boss/ /home/boss
		- *************
		  How to mount an encrypted LVM disk via CLI
		  https://askubuntu.com/a/63598
		- sudo lsblk
		  Find out which partition is the external hard drive with the LUKS on it and type "part"
		- sudo cryptsetup luksOpen /dev/sdb3 my_encrypted_volume
		  Decrypt the partition. It'll prompt for password
		- ====
		  TROUBLESHOOTING "Cannot use device /dev/sdb3 which is in use (already mapped or mounted)."
			- sudo dmsetup remove_all
			  Remove all current mounts
			- df -h
			  List all current mounts
			- Then redo the mount attempt again
			  =====
		- Next steps:
			- lsblk -l -n /dev/sdb3
			  Check the decrypted volume exists and what is the name of the lvm volume
			- sudo mkdir /media/my_device
			  Create a directory for where to mount the partition
			- sudo mount /dev/mapper/vgkubuntu--A-root /media/my_device
			  Mount the volume
		- ====
		  TROUBLESHOOTING
		  [source] https://unix.stackexchange.com/a/678435
			- sudo lvscan -a
			  Scan for available logical volumes. Will reveal if you have volume groups with the same volume group name but won't give a warning e.g. `/dev/vgkubuntu/root`
			- sudo vgscan
			  Will give a warning if there is more than one volume group using the same name, and what their UUID each is
			- sudo vgrename Q30rC3-l85L-mxlJ-2yyW-FDzB-hhhu-1UBRhm vgkubuntu-A
			  Will change the volume group selected by it's UUID, to have the non-duplicate name `vgkubuntu-A`
		- ===
		  TROUBLESHOOTING
			- sudo vgchange -ay
			  // Activate LVs if not active. Won't work if you have duplicate volume group names
			- sudo lvscan -a
			  Check all available logical volumes status.
			- sudo lvdisplay
			  Check
			- Try `sudo mount` command again
			  ===
		- `sudo rsync` is fine as long as you're using `-a` flag
		- `rsync -avz --info=progress2 --info=name0 /media/my_device/home/boss/ /home/boss`
		  `rsync -avz --progress --stats /media/my_device/home/linuxbrew/ /home/linuxbrew`
		- rsync -avz --info=progress2 /media/2tb/home/boss/ /media/1tb/home/boss
		- sudo rsync -avz --info=progress2 /media/2tb/home/boss/Games/ /media/1tb/home/boss/Games
		  === 
		  TROUBLESHOOTING - unmount if disconnection
		- sudo cryptsetup close my_encrypted_volume
		  sudo umount /media/my_device
		- ====
		  SOP: Copying data to framework external drive
			- 1
				- kubuntu@kubuntu:~$ sudo lsblk
				  kubuntu@kubuntu:~$ sudo cryptsetup luksOpen /dev/sda1 my_encrypted_volume_1tb
				  kubuntu@kubuntu:~$ sudo cryptsetup luksOpen /dev/nvme0n1p3 my_encrypted_volume_2tb
				  kubuntu@kubuntu:~$ sudo lsblk
				  kubuntu@kubuntu:~$ cd Desktop
				  kubuntu@kubuntu:~/Desktop$ mkdir 1tb
				  kubuntu@kubuntu:~/Desktop$ mkdir 2tb
				  kubuntu@kubuntu:~/Desktop$ sudo mount /dev/mapper/vgkubuntu--A-root 2tb
				  kubuntu@kubuntu:~/Desktop$ sudo mount /dev/mapper/my_encrypted_volume_1tb 1tb
				- kubuntu@kubuntu:~$ sudo lsblk
				- kubuntu@kubuntu:~$ sudo cryptsetup luksOpen /dev/sda1 my_encrypted_volume_1tb
				- kubuntu@kubuntu:~$ sudo cryptsetup luksOpen /dev/nvme0n1p3 my_encrypted_volume_2tb
				- kubuntu@kubuntu:~$ sudo lsblk
				- kubuntu@kubuntu:~$ cd Desktop
				- kubuntu@kubuntu:~/Desktop$ mkdir 1tb
				- kubuntu@kubuntu:~/Desktop$ mkdir 2tb
				- kubuntu@kubuntu:~/Desktop$ sudo mount /dev/mapper/vgkubuntu--A-root 2tb
				- kubuntu@kubuntu:~/Desktop$ sudo mount /dev/mapper/my_encrypted_volume_1tb 1tb
			- sudo rsync -avz --info=progress2 /home/kubuntu/Desktop/2tb/home/boss/ /home/kubuntu/Desktop/1tb/home/boss
			- sudo rsync -avz --info=progress2 /home/kubuntu/Desktop/2tb/home/boss/Games/ /home/kubuntu/Desktop/1tb/home/boss/Games
			  sudo rsync -avz --info=progress2 /home/kubuntu/Desktop/2tb/home/boss/Documents/ /home/kubuntu/Desktop/1tb/home/boss/Documents
			  sudo rsync -avz --info=progress2 /home/kubuntu/Desktop/2tb/home/boss/Videos/ /home/kubuntu/Desktop/1tb/home/boss/Videos
		- ====
		  TROUBLESHOOTING:
		  umount /home/kubuntu/Desktop/2tb
		- On 4TB side:
		  sudo cryptsetup luksOpen /dev/sda1 enc_1tb
		  sudo mount /dev/mapper/enc_1tb /home/boss/1-EMERGENCY/1tb
		  sudo rsync -avz --info=progress2 /home/boss/1-EMERGENCY/1tb/home/boss/Documents/ /home/boss/Documents
		  videos
		  games
		  sudo rsync -avz --info=progress2 /home/boss/1-EMERGENCY/1tb/SteamLibrary/ /home/boss/SteamLibrary
		  sudo rsync -avz --info=progress2 /home/boss/1-EMERGENCY/1tb/ASMR-YouTube_Twitch/ /home/boss/Videos/2-Complete/ASMR-YouTube_Twitch
		  ======
		  Later on:
		  sudo rsync -avz --info=progress2 --exclude='/home/boss/1-EMERGENCY/1tb/home/boss/Documents/*' --exclude='/home/boss/1-EMERGENCY/1tb/home/boss/Games/*' --exclude='/home/boss/1-EMERGENCY/1tb/home/boss/Videos/*' /home/boss/1-EMERGENCY/1tb/home/boss/ /home/boss
		- =====
		  WIP:
		  sudo rsync -avz --info=progress2 --exclude='/home/kubuntu/Desktop/MOUNT/2tb/home/boss/Documents' --exclude='/home/kubuntu/Desktop/MOUNT/2tb/home/boss/Games' --exclude='/home/kubuntu/Desktop/MOUNT/2tb/home/boss/Videos' /home/kubuntu/Desktop/MOUNT/2tb/home/boss/ /home/kubuntu/Desktop/MOUNT/1tb/boss
		  OR
		  sudo rsync -avz --info=progress2 --exclude 'Documents' --exclude 'Games' --exclude 'Videos' --exclude '.local' --exclude '.var' /home/kubuntu/Desktop/2tb/home/boss/ /home/kubuntu/Desktop/1tb/boss
		  sudo rsync -avz --info=progress2 /home/kubuntu/Desktop/MOUNT/2tb/home/boss/.local/ /home/kubuntu/Desktop/MOUNT/1tb/boss/.local
		  sudo rsync -avz --info=progress2 /home/kubuntu/Desktop/MOUNT/2tb/home/boss/.var/ /home/kubuntu/Desktop/MOUNT/1tb/boss/.var
		  ====
		  4TB:
		  sudo rsync -avz --info=progress2 /home/boss/1-EMERGENCY/1tb/boss/.local/ /home/boss/.local
		  sudo rsync -avz --info=progress2 /home/boss/1-EMERGENCY/1tb/boss/.var/ /home/boss/.var
		  .bitmonero
		  Music
		  .recoll
		  MEGA - todo
		- sudo rsync -avz --info=progress2 --exclude 'Documents' --exclude 'Games' --exclude 'Videos' --exclude '.local' --exclude '.var' /home/boss/Videos/1TBMOUNT/boss/ /home/boss
	- ((63ad9567-8df0-4f60-ab52-545451251156)) : ((66a89254-7186-4e5d-9d18-d5579908955f))
	- ((65a98a51-aea7-48dc-9fca-1e93b25c77a4))
- ((659d093f-bf67-444a-b2a1-ec0a28907583)) : ((6655e59f-8ed3-4d3c-ad5b-ce5b86e16fd6))
- Linux
	- [[Linux setup SOP]] : ((63a9adc7-4cc4-4ecc-933c-82c3163cfe29))
	- Restoring backups
	  collapsed:: true
		- Lost data
			- Most data available via ((63134623-9285-4e12-b20f-39308c32c8f8)) > ((63134623-b5e0-49bb-8575-a3794c76004a)). See link for how to recover SSH key (requires)
			- Some instead stored (periodically synced) via Backblaze since it's unsuitable for incremental backups
	- Related: ((644c0b31-0299-4e45-9872-0627836c4d83))
- Related:
	- [[PC]]
	- [[Overcoming Obstacles]]