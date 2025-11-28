- #Phone
  id:: 62d44724-ef05-49ae-bf7b-a0f873daf193
- Pros/Cons
  collapsed:: true
	- Cons
		- ((649b13cd-0859-4c2f-8ad3-28bfe496eeba)) gives realtime location to government and telecom companies
	- Links
		- See [Stock Android AOSP](https://workflowy.com/#/5c6940e545df)
		- See [LineageOS](https://workflowy.com/#/1543bac42ca5)
- Journal
  collapsed:: true
	- [[2024-11-13 Wednesday]] Researched current state-of-the-art for ((6436ae2f-4aac-4d12-9ee3-add1862e15a4)) privacy. ((649b13c9-8a5f-428a-8892-cf12c66d6bfa)) is the best once it gets voice+SMS support again, best model is a company hosts tons of physical SIMs in modems then you can access it via an app
	- Setup [postmarketOS on old Poco F1](<https://wiki.postmarketos.org/wiki/Xiaomi_POCO_F1_(xiaomi-beryllium)>) when I upgrade to a new phone?
	- 11/09/2022 - Updating to a new minor LineageOS version caused GApps to crash constantly
	  collapsed:: true
		- Summary
			- Solution: wiping multiple Android partitions was necessary, including `/data`, `/system`, `recovery` and `internal storage`. Then reinstalling the April 2022 LineageOS recovery, system images as well as MindTheGapps.
		- Related:
			- ((6318fc64-2500-47a7-abc5-92337d9cbb55))
			- ((631b4ef3-29d3-4526-b74d-d9b71299a9b0))
			- ((6318fc64-68b1-45e2-a20d-c92068e956af))
- Phone Software
  collapsed:: true
	- Mobile Operating System
	  collapsed:: true
	  id:: 635037d1-737d-452b-802e-49e5474b7279
		- Journal
		  collapsed:: true
			- Sun, Nov 1, 2020 - GrapheneOS is better than LineageOS, but it's expensive currently as it relies on the latest Pixel devices
			- July 2020
				- Android has much better security, features, device support and UX than Linux-based phones
				- [LineageOS for ](https://workflowy.com/#/1abc0e737ad8)<a href="https://workflowy.com/#/1abc0e737ad8">microG</a> is ideal middle-ground between privacy and features for me at the moment since it's 1-2 versions behind mainstream Android
				- LineageOS-supported phones are ideal still since if OEM updates stop for them then you can still get latest Android via LOS
		- ### Mostly Libre
		  i.e. still uses binary blobs for drivers
			- [Android](https://android.com)
			  id:: 631fa93e-1087-4996-91b8-7526842b4ba8
			  collapsed:: true
			  #Phone-Android AKA Stock Android AOSP | by ((64e0943b-37fb-4eb2-a52b-50ce07e795fa))
				- Pros/Cons (_Compared to non-Android mobile OS)_
				  collapsed:: true
				  id:: 631fa93e-324c-408e-a865-7aa4a0899c63
				  e.g. iOS, Sailfish, Ubuntu Touch etc
					- Pros
						- Initiatives to ensure longevity and regular security updates despite obstacles from OEMs
						  id:: 649b13d3-139c-445c-bb2b-54cf06c55ca8
						  collapsed:: true
							- Status
								- _See_ [Background - current state](https://workflowy.com/#/cbaf757ef64c)
								- (Q3 2022) Phones which launch with Android 12 _shouldn't_ require device-specific LineageOS builds because closed-drivers are contained in kernel modules, and every phone plugs these into a stable ABI
								  See [Project ?](https://workflowy.com/#/1fbe19f22919)
								- Future:
									- Android Common Kernel being merged into mainline Linux
									  collapsed:: true
										- _See_ [Android Common Kernel](https://workflowy.com/#/3793b62b18b4)
										- These patches can include:
											- Backports and cherry-picks of upstream functionality needed for Android features
											- Features ready for Android devices but still under development upstream (for example, Energy Aware Scheduler task placement optimizations).
											- Vendor/OEM features that are useful for other ecosystem partners (for example, sdcardfs).
										- How many extra lines of code
											- ~2016 - over 60k lines
											- 2018 Feb - 32,000 insertions and over 1,500 deletions compared to mainline Linux 4.14.0
												- Among the areas where Android is carrying kernel patches they are looking at upstreaming are for GKI enablement, DMA-BUF HEAPS, DRM core patches, and more.
											- 2018 Nov - 30 patches, 6.5k lines
												- only about 30 patches in the Android Common Kernel, adding about 6,500 lines of code, that are needed to boot Android. The eventual plan is to push that to zero, but there are a number of issues to deal with still, including solving problems with priority inheritance in binder, getting energy-aware scheduling into the mainline, and upstreaming the SDCardFS filesystem bridge.
									- Phone OEMs pushing their proprietary drivers to upstream so a stable ABI isn't needed
									- Qualcomm or other SoC vendor upstreaming their proprietary drivers so they can use mainline kernel
							- Arguments against
							  collapsed:: true
								- Phhusson put it best. Whole thread regarding treble and updates on android is worth a read:
								  source:: [https://teddit.net/r/Android/comments/qbg4q0/only_3_years_guaranteed_updates_for_pixel_6_and/hh9l6yi/#c](https://teddit.net/r/Android/comments/qbg4q0/only_3_years_guaranteed_updates_for_pixel_6_and/hh9l6yi/#c)
									- [https://twitter.com/phhusson/status/1447695889737388032?s=20](https://twitter.com/phhusson/status/1447695889737388032?s=20)
										- With Pixel 6 coming, we'll hear a lot of Google blaming SoC vendors for poor upgrades, and how Google being their own SoC vendor will make upgrades much more better. 18/26
										- Do you remember when Google said carriers were preventing upgrades and became a carrier? Do you remember when Google said OEMs were preventing upgrades, and then became their own OEMs? Nexus 5 had 2 major upgrades, Pixel 2 had 3. Nexus 5 had 3 years of upgrades, P2 had 3. 19/26
										- ...
										- We'll soon hear how Fuchsia will help bringing forever upgrades to every device in the world. Maybe try to be suspicious about those claims, and analyze everything that's been said over and over again in the past. 21/26
									- Pixel 6 has only 3 years guaranteed OS updates despite not having their own SoC
							- _Android initiatives_
							  collapsed:: true
								- (2022 / Android 12) Project ? - new phones require the ability to run a Generic Kernel Image (GKI), which makes it easier for OEMs and custom ROMs to support many phones for years
								  collapsed:: true
								  [https://cdn.arstechnica.net/wp-content/uploads/2019/11/ABI*Monitoring.pdf*-\_Google_Chrome.png](https://cdn.arstechnica.net/wp-content/uploads/2019/11/ABI_Monitoring.pdf_-_Google_Chrome.png)
									- What
									  collapsed:: true
										- So all devices run a Generic Kernel Image (GKI, based off Google's Android Common Kernel) instead of a device-specific one
									- Rollout
									  collapsed:: true
										- For [Android 12 / S](https://workflowy.com/#/b811bc7ac61a), devices shipping with Q4 2021 LTS kernel must be able to use the GKI. So basically new devices from Q3 2022 realistically
										  source:: [https://source.android.com/devices/architecture/kernel/generic-kernel-image](https://source.android.com/devices/architecture/kernel/generic-kernel-image)
									- Pros/Cons
									  collapsed:: true
										- Pros
											- Enables OEMs to update to a newer [Android Common Kernel](https://workflowy.com/#/3793b62b18b4) for security fixes and bug fixes without SoC vendor (eg Qualcomm) involvement
											- Benefits for consumers if Android maintain a stable ABI in their Android Common Kernel
											  collapsed:: true
												- Generic Kernel Image which is compatible with all devices means it's far easier to update and swap kernels
												- Vendors can offer kernel updates finally
												- ROMs like LineageOS will no longer need device-specific builds
												- Will make it easier for projects for non-Android OSes like mobile Linux to flourish
													- Android devices as a whole will be able to run LTS Linux kernels
													- individual Android devices will require virtually zero unique tweaks to become mainlined (depends on kernel modules support)
													- Like postmarketOS to reimplement drivers as open-source
														- postmarketOS is like Debian of Linux on mobile. Other mobile Linux like Plasma Mobile and ubports can build on top of it
													- Non-Android OSes like postmarketOS will have far less work because currently they have to mainline each device themselves. Instead they just need to make sure the kernel modules containing the drivers can plug in correctly, then use the Android Common Kernel (mainline Linux + a few patches)
													-
										- Cons
											- Android 's stable ABI will be within a specific Android version only
											  collapsed:: true
												- ie most devices will finally get Android Common Kernel updates, but won't get Android version updates eg 12->13
												- Google will have to maintain ACK's for each Android version, now that they're guanteeing a stable ABI for ACK updates
											- Linux shouldn't never be asked to maintain a stable ABI, but Android can provide one if they don't want to force manufacturers to upstream
											  collapsed:: true
												- Ideal world: all drivers are open-source and thus in the Linux kernel
												- It's a ton of work to support closed-source drivers like this
													- RE 3: Kernel developers are diametrically opposed to this for good reason.
													- People like the fact that they can install Linux on any old computer and it'll "just work". Linux supporting a stable in-kernel ABI means less drivers will get upstreamed plus they'll have to bear the burden of maintaining this stable interface across many years. Which is unrealistic, so your older devices will be stuck using an old kernel (which unsurprisingly is the same problem Android has).
													- If Google wants make a stable in-kernel ABI then that can be part of their Android Common Kernel and they can maintain it themselves. But don't ask Linux devs to do all the work for vendors who refuse to open-source their drivers.
												- Linux's leverage comes from having an unstable ABI
													- The unstable kernel ABI is a major incentive for hardware manufacturers to contribute their drivers into the mainline kernel. If they don't do that, the kernel keeps evolving while they get left behind and must pay the maintenance costs. I believe it's how the kernel developers maintain their _leverage_. Contribute your drivers because nobody is gonna waste time supporting you otherwise.
													- If the ABI is stabilized, that leverage is lost. Cheap minimum effort proprietary drivers for a single architecture become viable.
													- This is how Windows works to this day:
														- release a driver for specific versions of Windows and processor architectures. The drivers would of course stop working with the next/64 bit version of Windows and they never made a new driver because the product is old and they think it's a waste of time and money to support it.
													- A stable ABI is a great thing for the companies since they can cheap out on the software development _and_ keep it closed. Doesn't seem so great for the long term health of the kernel though: the drivers won't be compatible with other architectures, won't be updated to take advantage of new code, will prevent breaking changes from being made even if they are improvements, can't be backported to older kernels, etc.
													- So if anything it will hurt people's ability to update the kernel. It seems Google just wants to make it cheaper to develop drivers _for_ Linux. The kernel developers want to make it expensive to develop drivers _outside_ Linux.
												- having a stable interface for manufacturers to target is primarily for the module loader being used for drivers -- which would render it sort of moot on devices where the hardware stack is supported by mainline, since AOSP can already boot off a nearly-vanilla Linux kernel given that constraint.
											- Alternatively ARM PCIe interface should be used
											  collapsed:: true
												- PCIe (peripheral component interconnect express) is an interface standard for connecting high-speed components.
												- Google is trying to fix a hardware (standardisation) problem with software
												- Do the latest Qualcomm chipsets not use PCIe?
													- Google Pixel 4 uses Qualcomm SDM855 Snapdragon 855
									- How
									  collapsed:: true
										- Background - current state
										  collapsed:: true
											- First they take a LTS Linux kernel and fork it 3 times
											  collapsed:: true
												- 1. Android Common Kernel - Android-specific patches are applied to Linux LTS kernel, published for SoC vendors to use
													- [https://source.android.com/devices/architecture/kernel/android-common](https://source.android.com/devices/architecture/kernel/android-common)
													- There's not a huge amount of out-of-tree patches from Linux LTS
														- the project is still carrying 485 patches on top of the 5.9-rc kernel, he said. About 30 of those are currently being discussed for merging; 78 of them are intended to be upstreamed. Another 25 are being worked on by Linaro with the intent of getting them upstream. There are 54 patches that will eventually be replaced by alternatives; these include the [ION memory allocator](https://lwn.net/Articles/480055/). That leaves 260 patches currently not on a path for upstreaming; many of them have to do with the GKI build or configuration changes. There are ten patches that could be considered for upstream, but they need an upstream user as well.
														  https://lwn.net/Articles/830979/
													- 2 Backlinks
														- Enables OEMs to update to a newer [Android Common Kernel](https://workflowy.com/#/3793b62b18b4) for security fixes and bug fixes without SoC vendor (eg Qualcomm) involvement
														- _See_ [Android Common Kernel](https://workflowy.com/#/3793b62b18b4)
												- 2. SoC kernel - Qualcomm (or other SoC vendor) makes additions so it works with their SoC. They provide a kernel version to OEMs
												- 3. Device Kernel - device manufacturer (OEM) adds stuff to make it support other hardware eg speakers, display, camera, USB ports
											- Usually new devices ship with a 2 year old LTS kernel
											- 1 Backlink
											  collapsed:: true
												- _See_ [Background - current state](https://workflowy.com/#/cbaf757ef64c)
										- Generic Kernel Image - a kernel which runs on all Android devices (AKA just the Android Common Kernel)
										- Stable API/ABI via kernel modules for vendor's closed-source drivers to load into
										  collapsed:: true
											- Google would ship a "Generic Kernel Image (GKI)" along with several "GKI Modules" that would expose this stable API/ABI in the kernel. The hardware-specific drivers (probably closed source drivers) would be loaded as kernel modules. So instead of forks on top of forks, everything gets modularized into additive packages.
											- The GKI kernel presents a stable Kernel Module Interface (KMI) for kernel modules, so modules and kernel can be updated independently.
										- In-kernel ABI would be stable only for a single LTS version - which means you can't update to a newer kernel, but it does mean every device runs the same kernel
										  collapsed:: true
											- For now, Google is only proposing that the in-kernel ABI be stable for a single LTS version. So this wouldn't allow devices to upgrade from one version of the Linux kernel to another—it would just allow for a single generalized kernel image to work across multiple devices, instead of the device-specific kernel forks we have today. It would definitely allow for easier security updates, and hopefully it would get new LTS releases to market faster.
									- _{Archive}_
									  collapsed:: true
										- https://arstechnica.com/gadgets/2019/11/google-outlines-plans-for-mainline-linux-kernel-support-in-android
										- https://reddit.com/comments/dyv2qi
										- https://news.ycombinator.com/item?id=21580311
										-
									- See [Generic Kernel Image (GKI)](https://workflowy.com/#/1bfe537b404f)
									- 3 Backlinks
									  collapsed:: true
										- See [(2022 / Android 12) Project ? - new phones require the ability to run a Generic Kernel Image (GKI), which makes it easier for OEMs and custom ROMs to support many phones for years](https://workflowy.com/#/1fbe19f22919)
										- (Q3 2022) Phones which launch with Android 12 _shouldn't_ require device-specific LineageOS builds because closed-drivers are contained in kernel modules, and every phone plugs these into a stable ABI
										  See [Project ?](https://workflowy.com/#/1fbe19f22919)
										- Unlike normal linux, the drivers for each part of android aren't included in the kernel. Some aren't provided at all and have to be reverse engineered. In the future some of these will be updated via [Project Mainline](https://workflowy.com/#/090f79f8a586) and rest will become <a href="https://workflowy.com/#/1fbe19f22919">kernel modules or GKI modules</a>
								- (2020) Project Mainline - some kernel and OS components updated via Google Play Store
								  collapsed:: true
									- hat
									  collapsed:: true
										- Allows kernel and OS-level components to be updated to be delivered via Google Play System Updates, usually as APEX files
									- Pros/Cons
									  collapsed:: true
										- Pros
											- Some kernel-level stuff can be fixed or updated on a monthly basis via Google Play instead of your kernel never getting updated
										- Cons
											- OS-level components rather than kernel-level components are becoming Mainline updates
												- This is good for modularity that Android is getting broken up into packages
												- However it does mean reliance on a central authority
												- e.g. Android Storage UI, PermissionController etc
									- [https://arstechnica.com/gadgets/2019/09/android-10-the-ars-technica-review/3/#h3](https://arstechnica.com/gadgets/2019/09/android-10-the-ars-technica-review/3/#h3)
									- Mostly, Project Mainline means removing the responsibility and customizability for a piece of code from the OEM to Google and having the code live in the open source Android repository.
									- Version enhancements
									  collapsed:: true
										- Android 11 - 21 OS components now updateable
										  id:: 644c0ad0-efaf-4094-9c04-85e5811be3a3
											- Google Play system update: 21 OS components are now updatable, including 9 additions in Android 11 focused on improving privacy, security, and developer consistency across devices. Highlights include an enhanced permissions component that standardizes user and developer access to critical privacy controls on Android devices, a Neural Networks API (NNAPI) component that optimizes performance and guarantees consistent APIs across devices, and a Tethering component for improved interoperability. The new updatable OS components in Android 11 are: Tethering, NNAPI, Cell Broadcast Receiver, adbd, Internet Key Exchange, Media Provider, statsd, WiFi, and SDK extension.
											- 1 Backlink
												- See [Android 11 - 21 OS components now updateable](https://workflowy.com/#/2eac9d8687eb) (Project Mainline/security)
									- 1 Backlink
									  collapsed:: true
										- Unlike normal linux, the drivers for each part of android aren't included in the kernel. Some aren't provided at all and have to be reverse engineered. In the future some of these will be updated via [Project Mainline](https://workflowy.com/#/090f79f8a586) and rest will become <a href="https://workflowy.com/#/1fbe19f22919">kernel modules or GKI modules</a>
								- (2019) OEM ROMs are being mandated to deliver 2 years of Android's security updates
								  collapsed:: true
									- https://www.osnews.com/story/30820/google-mandates-two-years-of-android-security-updates/
								- (2018 / Android 8) Project Treble - new phones require the ability to run a single Generic System Image (GSI) that all Android phones can run
								  collapsed:: true
									- Pros/Cons
									  collapsed:: true
										- Pros
											- Makes it easier for OEMs and custom ROMs to support many phones for years, since they're no longer reliant on SoC vendors to support latest Android
											- Now custom ROMs can release a single build/GSI instead of device-specific ones
											- New Android versions can be pushed
										- Cons
											- Older devices which were on Android 8.x or earlier aren't compatible with the latest Project Treble spec
											  collapsed:: true
												- The reality, however, is not that simple. Google further refined Project Treble’s requirements with [Android 8.1](https://www.xda-developers.com/tag/android-oreo/) Oreo and Android 9 Pie by fully implementing the VNDK (Vendor Native Development Kit) and introducing CTS-on-GSI (Compatibility Test Suite on Generic System Image) tests. Nowadays, Android 8.x devices aren’t even officially considered to be Project Treble compatible, as Google is focusing only on compatibility with <a href="https://www.xda-developers.com/tag/androidpie/">Android Pie</a> and above. When we are talking about devices like the <a href="https://forum.xda-developers.com/mate-9">Huawei Mate 9</a> or the <a href="https://forum.xda-developers.com/oneplus-5">OnePlus 5</a>/5T, which originally launched with <a href="https://www.xda-developers.com/tag/android-nougat/">Android Nougat</a> and subsequently <a href="https://www.xda-developers.com/stock-android-oreo-huawei-mate-9-project-treble/">received Treble support</a> via <a href="https://www.xda-developers.com/oneplus-5t-project-treble-oxygenos-beta/">system software updates</a>, you can’t simply flash <a href="https://developer.android.com/topic/generic-system-image/releases">Google’s version of Android 11 GSIs</a> on them and expect it to boot with everything working.
											- Device-specific images are required in order to support modern expected features expected
											  collapsed:: true
												- Why
													- LineageOS in 2020 has device-specific builds because the various patches that are included in each phone's system image have to be ported to the generic Android system images
													- GSIs and custom ROMs based on GSIs have limited featuresets and don't support all the unique hardware that flagship phones have
													- Unlike normal linux, the drivers for each part of android aren't included in the kernel. Some aren't provided at all and have to be reverse engineered. In the future some of these will be updated via [Project Mainline](https://workflowy.com/#/090f79f8a586) and rest will become <a href="https://workflowy.com/#/1fbe19f22919">kernel modules or GKI modules</a>
									- _Download from here_
									  _See_ [Generic System Image (GSI)](https://workflowy.com/#/0c7ccf914447)
									- New devices use Project Treble, which means all devices must be able to run a standardised Android GSI build; so manufacturers should be able to release OS + security updates on time without any changes needed
									  collapsed:: true
										- Pros
										- Obstacles
											- However, if you're still using the OEM ROM then despite it being cheap+easy to push Android updates they'll withhold it, because it maximises new phone sales (planned obsolescence)
												- But this is being circumvented with Project Mainline on Android Q, which will allow some libraries to be updated like a Linux package manager
										- [https://source.android.com/setup/build/gsi](https://source.android.com/setup/build/gsi)
										- One released for each Android version, with variants for each architecture eg ARM 64
										- ...
										- Project Treble is a hardware abstraction layer, like Halium. It allows all phones launched with Android Oreo to get Android version updates without any changes needed to be made by the manufacturer
										- [https://source.android.com/devices/architecture/](https://source.android.com/devices/architecture/)
										- It's helping ROM development since it allows one ROM to work on multiple devices instead of one ROM per device
										  https://github.com/phhusson/treble_experimentations/wiki
										- [https://www.xda-developers.com/googles-project-treble-modularize-android-so-oems-can-update-devices-faster/](https://www.xda-developers.com/googles-project-treble-modularize-android-so-oems-can-update-devices-faster/)
										- Archive
											- [https://www.androidauthority.com/project-treble-818225/](https://www.androidauthority.com/project-treble-818225/)
							- _Related:_ [Android devices relying on proprietary hardware results in limitations](https://workflowy.com/#/515e1b87a8ca)
						- ((635037cc-6477-4588-80ff-c8149cad6935)) : ((649b13cc-a9a2-40f4-9a73-97d19f4a0390))
						- Lots of privacy enhancements over time
						  id:: 649b13d3-03b4-45c0-ade8-697837438d1b
						  collapsed:: true
							- ((64fed706-d987-4c12-a888-29dcdd6e26b8))
							  collapsed:: true
								- {{embed ((6d86af70-8bf3-496f-a5f9-08081a20dc28))}}
							- ((649b13d1-4753-4edb-b1df-397c5c89ad35))
							  collapsed:: true
								- {{embed ((64fed773-470b-44f5-a826-c1c657fe5618))}}
							- ((649b13d1-806c-4635-a439-e008c6a27fa0))
							  collapsed:: true
								- {{embed ((649b13d1-f871-4042-aba4-d644fe765610))}}
							- ((649b13d1-6e1b-4314-bb5c-632667e0e799))
							  collapsed:: true
								- {{embed ((649b13d1-472b-4c84-bcf5-931794d076ae))}}
							- ((649b13d1-cbcd-4003-bb52-a7292cfc356f))
							  collapsed:: true
								- {{embed ((649b13d1-4577-4eae-9806-24f964f2099b))}}
					- Cons
					  id:: 649b13d2-56c9-4c4d-800b-e23db485c570
						- Not totally easy to upgrade devices to newer Android versions
						  collapsed:: true
							- The key delay when it comes to a major Android version move stems from us only getting source code on the day the AOSP tags go public. So we have a very small window of time to port all our OS level features over. Whilst we have always ported it over within days of the tags being public, it's a huge strain on the team due to the amount of rapid development effort which is required. Ideally we would be getting AOSP source code early, before it's released to the public, so we could begin porting now, months before the public release. This would mean we avoid running into any pain in life and would drastically reduce our workload. As for time scales, it might take 1-2 days to port devices fully over and a few more days to port OS level changes. Google publishes the beta Linux kernels publicly for upcoming Android versions, so we are currently porting changes to that in order to save time, as usually they are quite similar or even the same kernels deployed when the tags are publicly released.
							- -
							- GrapheneOS needs 1-2 days to use the [adevtool](https://github.com/GrapheneOS/adevtool) project to extract libraries/firmware etc which aren't buildable by AOSP from the stock OS. We need to redo the rules and configurations we use for this every major version at least.
							- {Archive}
								- [https://discuss.grapheneos.org/d/92-how-much-has-treble-and-the-like-eased-upgrades-for-gos/3](https://discuss.grapheneos.org/d/92-how-much-has-treble-and-the-like-eased-upgrades-for-gos/3)
						- Google Play Store will require App Bundles and thus require Play App Signing, which allows them to alter apps in any way they choose before publishing
						  collapsed:: true
							- Pros/Cons
								- Unclear
									- Can Google already alter apps?
										- "Since Google already controls the Play Store, the Android operating system (including installer), and the Android SDKs including compiler, they can already do this regardless of how your app is signed."
										  source:: [https://www.cs.cmu.edu/~rdriley/487/papers/Thompson_1984_ReflectionsonTrustingTrust.pdf](https://www.cs.cmu.edu/~rdriley/487/papers/Thompson_1984_ReflectionsonTrustingTrust.pdf)
							- Info
								- Main discussion
								  collapsed:: true
									- My Reddit post - PSA: Google Play Store will be able to send you compromised Android apps from August
									  source:: [https://old.reddit.com/r/privacy/comments/nbc508/psa_google_play_store_will_be_able_to_send_you/?](https://old.reddit.com/r/privacy/comments/nbc508/psa_google_play_store_will_be_able_to_send_you/?)
										- Content
										  From August, [App Bundles are required for Google Play Store apps](<[https://developer.android.com/guide/app-bundle](https://developer.android.com/guide/app-bundle)>). To use App Bundles, publishers [must use Play App Signing](<a href="https://stackoverflow.com/a/63298314">https://stackoverflow.com/a/63298314</a>).
										  
										  This means handing over the signing keys to Google, which [allows them to change the app in whatever way they want](<a href="https://commonsware.com/blog/2020/09/23/uncomfortable-questions-app-signing.html">https://commonsware.com/blog/2020/09/23/uncomfortable-questions-app-signing.html</a>) before delivering it to users. Despite [public outcry](<a href="https://news.ycombinator.com/item?id=27010463">https://news.ycombinator.com/item?id=27010463</a>) there's no sign of Google changing this requirement.
										  
										  Best recommendation at this time is to swap to getting apps directly from the creators (e.g. [Signal standalone APK](<a href="https://signal.org/android/apk/)">https://signal.org/android/apk/)</a>) and use trusted alternative app stores like [F-Droid](<a href="https://f-droid.org/">https://f-droid.org/</a>).
									- Article
									  source:: [https://commonsware.com/blog/2020/09/23/uncomfortable-questions-app-signing.html](https://commonsware.com/blog/2020/09/23/uncomfortable-questions-app-signing.html)
										- Discussion
										  [https://news.ycombinator.com/item?id=27010463](https://news.ycombinator.com/item?id=27010463)
								- F-Droid does is basically the same what major Linux distros do - build everything from source on trusted infrastructure, then signs with their own keys. Reproducible Builds are supported to ensure that the binaries they produce match the source code that was provided
								  collapsed:: true
									- [https://f-droid.org/en/docs/Reproducible_Builds/](https://f-droid.org/en/docs/Reproducible_Builds/)
									- Related [https://wiki.debian.org/ReproducibleBuilds](https://wiki.debian.org/ReproducibleBuilds)
							- Solution
								- Uninstall [Goog](https://workflowy.com/#/6d907157ce11)<a href="https://workflowy.com/#/6d907157ce11">le Play Store apps</a>
						- Android itself is non-free due to heavy reliance on Google Play Services
						  collapsed:: true
							- See [https://www.gnu.org/philosophy/android-and-users-freedom.en.html](https://www.gnu.org/philosophy/android-and-users-freedom.en.html)
							- Copypasta - based on GNU/Linux original
							  collapsed:: true
								- _"What you’re referring to as Android, is in fact, Google Play Services/Android, or as I’ve recently taken to calling it, Google Play Services plus Android. Android is not an operating system unto itself, but rather another free component of a fully functioning Google Play Services system made useful by Google Play Services. Many phone users run a modified version of the Google Play Services system every day, without realizing it. Through a peculiar turn of events, the version of Google Play Services which is widely used today is often called “Android”, and many of its users are not aware that it is basically the Google Play Services system, developed by Google. There really is a Android, and these people are using it, but it is just a part of the system they use. Android is the kernel: the program in the system that allocates the machine’s resources to the other programs that you run. The kernel is an essential part of an operating system, but useless by itself; it can only function in the context of a complete operating system. Android is normally used in combination with the Google Play Services: the whole system is basically Google Play Services with Android added, or Google Play Services/Android. All the so-called “Android” distributions are really distributions of Google Play Services/Android. "_
								  source:: [https://reddit.com/comments/ads23v/comment/edk8tvc?context=3](https://reddit.com/comments/ads23v/comment/edk8tvc?context=3)
								- Alternative 2
									- What you’re refering to as Android, is in fact, Google Play Services/Android, or as I’ve recently taken to calling it, Google Play Services plus Android. Android is not an operating system unto itself, but rather another component of a fully functioning Google Play Services system.
									- Many mobile users run a modified version of the Google Play Services system every day, without realizing it. Through a peculiar turn of events, the version of Google Play Services which is widely used today is often called Android, and many of its users are not aware.
									- There really is a Android, and these people are using it, but it is just a part of the system they use. Google Play Services is the core: the program in the system that is required for full functionality of a mobile device. The core is an essential part of an operating system, but useless by itself; it can only function in the context of a complete operating system. Android is normally used in combination with Google Play Services: the whole system is basically Google Play Services with Android added, or Google Play Services/Android. All the so-called Android ROMs are really distributions of Google Play Services/Android!
							- They make it very difficult to use a forked version of AOSP
							  collapsed:: true
								- e.g. Open Handset Alliance means nearly every manufacturer being contractually barred from manufacturing a device that runs the non-Android
								- Requires replicating essential apps which are Google-only (done by Amazon and Samsung)
								- Requires replicating important APIs for app usability (done by Amazon)
								- [http://arstechnica.com/gadgets/2013/10/googles-iron-grip-on-android-controlling-open-source-by-any-means-necessary/4/](http://arstechnica.com/gadgets/2013/10/googles-iron-grip-on-android-controlling-open-source-by-any-means-necessary/4/)
									- Google Maps API, Google Cloud Messaging, Location APIs, In-app purchasing, Play Games
									- Google Play Services is essential for most features a user would expect in a modern mobile phone. For running bank apps (SafetyNet), many maps apps or apps that include maps (eg Uber, Tinder - due to Google Maps API), push notifications, etc. It's absolutely used to lock-in users to the Google ecosystem and discourage them from degoogling.
							- ((6318fc66-9d9f-4547-8e1c-172958500c0d))
							- [Play Integrity API](https://developer.android.com/google/play/integrity)
							  id:: 649b13d2-3bf6-43ed-b52c-7bbcf094ca3c
							  collapsed:: true
							  Successor to SafetyNet Attestation
								- Bypassing
									- [https://github.com/kdrag0n/safetynet-fix/issues/78](https://github.com/kdrag0n/safetynet-fix/issues/78)
								- SafetyNet API
								  collapsed:: true
									- Opt-in API for developers to use
									- [https://www.howtogeek.com/241012/safetynet-explained-why-android-pay-and-other-apps-dont-work-on-rooted-devices/](https://www.howtogeek.com/241012/safetynet-explained-why-android-pay-and-other-apps-dont-work-on-rooted-devices/)
									- [https://developer.android.com/training/safetynet](https://developer.android.com/training/safetynet)
							- Needed for
							  collapsed:: true
								- Push Notifications
								- Location Services (although microG implements alternative location services)
							- 1 Backlink
							  collapsed:: true
								- See [Android itself is non-free due to heavy reliance on Google Mobile Services](https://workflowy.com/#/9f418aba5d76)
						- Still has a few privacy/security loopholes
						  collapsed:: true
							- _Can be solved by using a custom ROM_
								- Internet permission control isn't great
									- Requires LineageOS or other ROM in order to have it natively
									- Alternatively use ((649b13cf-caf2-4248-adbb-6e642bd536d9)) or <a href="https://workflowy.com/#/05e140ac2ec7">AFWall+ (Donate)</a>
								- See [Developer option to have a randomised MAC address each time you connect to a network](https://workflowy.com/#/3c545e3cd340) - this should be a basic user-level setting like it is on GrapheneOS
							- _Remaining issues_
								- Nothing like ((663b24fb-4437-4115-83da-5f5b668989fc))
								- Before First Unlock (BFU) is significantly more secure than After First Unlock (AFU)
								  collapsed:: true
									- _See_ [Android OS - File-Based Encryption (FBE) - encrypted whilst lock screen on](https://workflowy.com/#/5d03615e5a79)
									- Only BFU is immune to cellebrite and other imaging tools
								- Some privacy enhancements require your apps to be targeting a newer Android API (11 for most benefit)
									- ((63219e37-0f66-4883-878d-3f5f173af6b7)) doesn't retroactively apply to older apps, only apps which update from November 2021 (i.e. target Android 11)
										- But "Riru - Enhanced mode for Storage Isolation" can work for those or GrapheneOS' implementation
										  [[Page not found · GitHub](https://github.com/Magisk-Modules-Repo/riru_storage_redirect](https://github.com/Magisk-Modules-Repo/riru_storage_redirect))
									- `QUERY_ALL_PACKAGES` permission
									  id:: 644c0ad0-a7b3-4853-abd4-7e41b5125f29
									  collapsed:: true
										- [Apps can obtain a list of all your other installed apps, but as of Android 11 it's now moved to a new permission. In Nov 2021 it will be restricted in Google Play Store for updating apps (they have to target Android 11)](https://developer.android.com/about/versions/11/privacy/package-visibility)
										  id:: 649b13d2-53ec-4093-a4f1-d887c902825d
											- Note: use AppChecker to detect what API the apps you have installed are targeting
											- ...
											- [Apps can obtain a list of all your other installed apps](https://arstechnica.com/information-technology/2020/03/4000-android-apps-silently-access-your-installed-software)
											- H - [https://9to5google.com/2021/03/31/installed-android-apps-limit/](https://9to5google.com/2021/03/31/installed-android-apps-limit/) "Google Play limiting Android 11+ apps from seeing what’s installed on devices this May" -Pretty self explanatory: part of a larger series of policy updates. Apps will no longer be able to see what other apps are installed on a device. -Apps that need access, like antivirus or browsers, will still have access.
											- [Google is restricting which apps can see the other installed apps on your device](https://www.xda-developers.com/google-is-restricting-which-apps-can-see-the-other-installed-apps-on-your-device/)
												- Google will be restricting which apps can request the QUERY_ALL_PACKAGES permission which is currently required for apps targeting API level 30 (Android 11) and above that want to query the list of installed apps on a user’s device that runs Android 11 or later.
												- Permitted use includes; device search, antivirus apps, file managers, and browsers.
										- ((6797d4d0-96eb-4588-897e-88c84cf1f4dc))
								- Even without ((644c0ad0-a7b3-4853-abd4-7e41b5125f29)) [apps can list a wide range of apps to individually detect](https://peabee.substack.com/p/everyone-knows-what-apps-you-use)
									- [Everyone knows all the apps on your phone | Hacker News](https://news.ycombinator.com/item?id=43518866)
								- Encrypted SD cards have severe limitations
								  collapsed:: true
									- Summary
									  collapsed:: true
										- [Adoptable Storage ](https://workflowy.com/#/adedc1f62126)has severe cons that make it only useful if you have massive apps
									- Background of Android storage
									  collapsed:: true
										- Big post 1
										  source:: [https://android.stackexchange.com/questions/214288/how-to-stop-apps-writing-to-android-folder-on-the-sd-card/218469#218469](https://android.stackexchange.com/questions/214288/how-to-stop-apps-writing-to-android-folder-on-the-sd-card/218469#218469)
										- Big post 2
										  source:: [https://android.stackexchange.com/a/217936](https://android.stackexchange.com/a/217936)
									- Using ADB to transfer files
									  collapsed:: true
										- It includes a percentage progress bar
										- e.g.
										- adb push /home/boss/Desktop/Android-SD/test-file /sdcard/test-file
									- You can format external SD cards as Adoptable Storage so that they get emulated as part of internal storage
									  collapsed:: true
										- Adoptable Storage
											- Pros/Cons
											  collapsed:: true
												- Pros
													- Entire SD card is encrypted
												- Cons
													- You can only move apps to SD card, not files
													  collapsed:: true
														- Once you've "adopted" the storage space you can move apps to it freely by going to a specific app's "App Info" page, clicking Storage, and choosing "Change" for each app.
														  source:: [https://forum.xda-developers.com/t/there-is-a-method-to-install-move-apps-to-sd.4179493/post-83757281](https://forum.xda-developers.com/t/there-is-a-method-to-install-move-apps-to-sd.4179493/post-83757281)
															- If you want to move multiple apps you can use something like "Internal Storage To SD Card" from the Play Store, which helps streamline the process; or even go into Developer Options and enable the option "Force allow apps to write on external storage" near the bottom which will force the majority of apps to favor the external SD card over the phone's.
													- SD card can't be accessed normally unless perhaps you root, and even then the UX is bad
													  collapsed:: true
														- MTP (file transfer) and ADB will only be able to send files to the internal storage. This is a problem if trying to keep large backup folders (SeedVault, OAndBackupX, TWRP) because they're only accessible via emulated filesystem
														- e.g. adb push /home/boss/Desktop/Android-SD/.SeedVaultAndroidBackup/ /sdcard/.SeedVaultAndroidBackup/
															- /sdcard/ path sends to internal storage, not adoptable storage
													- Even if you find a way to transfer files because Android's storage structure changes frequently it may not be possible to use this next version
											- How to enable it if your OEM has it disabled
											  source:: [https://forum.xda-developers.com/t/enable-adoptable-storage-no-root-needed.3615882/post-72837194](https://forum.xda-developers.com/t/enable-adoptable-storage-no-root-needed.3615882/post-72837194)
											  collapsed:: true
												- adb shell
												- sm list-disks
												- sm list-volumes all
												- sm set-force-adoptable true
												- sm partition disk:179,128 private (replace with mixed what number you want to be external, ie: mixed 80 will leave 80% of card as external, 20% internal)
												- sm set-force-adoptable false
												- sm list-volumes all
												- NOTE: the fourth command partitions your SD card, and may take 2-3 minutes (or longer) to complete, depending on the size of your card. plus make sure you have a reliable and fast SD Card.
												- Disconnect your phone from the USB cable and reboot it. The reboot is crucial. Your phone may (or may not) take a bit longer to boot this time.
												- Once your phone is fully booted, tap Settings > Developer Options and disable USB Debugging, clicking “OK” to any messages that may appear.
												- Go to Settings > Storage & USB and tap your SD card. Tap the three dots in the upper-right corner and choose “Migrate data”.
												- [source2] [https://stackoverflow.com/questions/38044532/how-to-turn-a-portable-sd-card-into-internal-storage-via-adb-command/38597684#38597684](https://stackoverflow.com/questions/38044532/how-to-turn-a-portable-sd-card-into-internal-storage-via-adb-command/38597684#38597684)
											- SD card's real storage is now at `/mnt/expand/[uuid]/`
											  collapsed:: true
												- This might work if you have root
													- adb push /home/boss/Desktop/Android-SD/.SeedVaultAndroidBackup/ /mnt/expand/998b4da3-332b-4878-8b0f-70f16bf41e4a/media/0/.SeedVaultAndroidBackup/
													- adb push /home/boss/Desktop/Android-SD/test-file/ /mnt/expand/998b4da3-332b-4878-8b0f-70f16bf41e4a/media/0/test-file/
											- 1 Backlink
											  collapsed:: true
												- [Adoptable Storage ](https://workflowy.com/#/adedc1f62126)has severe cons that make it only useful if you have massive apps
									- Alternative solution: encrypt the folder
									  collapsed:: true
										- See [Encrypt as much data as possible on external SD card](https://workflowy.com/#/6598dd271a18)
										- _My current folders_
											- .SeedVaultAndroidBackup - Should be by default encrypted
											- OAndBackupX - Should be by default encrypted
											- Storage-backup
												- ((649b13ce-f81c-41be-a7ff-f6d677c158c0)) and syncthing untrusted folders to sync home directory to SD card instead of FolderSync?
											- TWRP
												- nandroid backups can be encrypted when they're created. Not sure if the current ones are. Delete them after backing them up and create new ones
									- 1 Backlink
									  collapsed:: true
										- Note: Adoptable Storage isn't viable (see [Encrypted SD cards have severe limitations](https://workflowy.com/#/c776b1646889))
								- VPN implementation is poor usability-wise
								  collapsed:: true
									- See Syncthing - [Android app doesn't run whilst VPN is on as it detects it as a metered network](https://workflowy.com/#/00460af000ee)
									- "Block connections without VPN" setting overrides any apps that I've made exceptions for within VPN app
										- It prevents Syncthing connecting between Android and Linux laptop whilst both are on different VPNs (and Android ProtonVPN is set to allow Syncthing to avoid the VPN)
										-
									- 3 Backlinks
										- See [VPN implementation is poor](https://workflowy.com/#/c08cbfe9ff89)
										  #Phone-Android
										- See [VPN implementation is poor](https://workflowy.com/#/c08cbfe9ff89)
										  #Phone-Android
										- See [VPN implementation is poor](https://workflowy.com/#/c08cbfe9ff89)
										  #Phone-Android
								- [Google's version of App Tracking Transparency. By Q2 2022 all apps will have to declare this info, though an ability to opt out from tracking won't be mandatory. If app targets Android 13 it'll have to declare AD_ID permission](https://www.theverge.com/2021/5/6/22422894/google-play-app-privacy-info-apple-app-store-labels)
								  collapsed:: true
									- Late 2021: advertising ID will be inaccessible if you turn off personalised ads
									  source:: [https://support.google.com/googleplay/android-developer/answer/6048248](https://support.google.com/googleplay/android-developer/answer/6048248)
										- As part of Google Play services update in late 2021, the advertising ID will be removed when a user opts out of personalization using advertising ID in Android Settings. Any attempts to access the identifier will receive a string of zeros instead of the identifier.
								- Related:
									- ((649b13cc-b2bd-4baf-ad2b-67e9a502588a))
							- _Related:_
								- ((649b13d3-03b4-45c0-ade8-697837438d1b))
								- ((6318fc66-9d9f-4547-8e1c-172958500c0d))
						- Android devices relying on proprietary hardware results in limitations
						  collapsed:: true
							- _Documentation_
							- _Limitations_
							  collapsed:: true
								- libhybris is needed to run non-Android OS's because all devices come with proprietary firmware blobs
							- Fairphone suggests Qualcomm is the biggest barrier to long-term Android support
							  collapsed:: true
								- SoC manufacturer (usually Qualcomm) customises Android for particular SoC. Then the phone manufacturer (eg Fairphone) adds support for rest of hardware, plus any customisation
								- Qualcomm only supports each SoC up to a certain Android version. As of 2020 they support their SoCs for 3 years
								  source:: [https://arstechnica.com/gadgets/2020/12/qualcomm-promises-three-years-of-android-updates-for-its-entire-soc-lineup/](https://arstechnica.com/gadgets/2020/12/qualcomm-promises-three-years-of-android-updates-for-its-entire-soc-lineup/)
								- Fairphone 2 (2015) has been supported for 5 years (to Android 9)
								  source:: [https://www.fairphone.com/en/2021/03/25/android9-fairphone2/](https://www.fairphone.com/en/2021/03/25/android9-fairphone2/)
							- SoC manufacturers burden their kernels with tons of proprietary code to prevent them from being updated, requiring them to make a [Kernel Module Interface (KMI)](https://workflowy.com/#/18f86940869f) rather than updating the kernel off mainline Linux
							- Kernel Module Interface (KMI)
							  collapsed:: true
								- Allows proprietary drivers to plug into the kernel as modules, allowing the kernel to be updated for minor releases
								- 1 Backlink
									- SoC manufacturers burden their kernels with tons of proprietary code to prevent them from being updated, requiring them to make a [Kernel Module Interface (KMI)](https://workflowy.com/#/18f86940869f) rather than updating the kernel off mainline Linux
							- Kernel not updated
							  collapsed:: true
								- Have to use the old Linux kernel the device was shipped with because it's compatible with their drivers and OEM won't give kernel updates
									- Linux kernel LTS announced extending support from 2 to 6 years (which allowed Project Treble for Android devices, and Ubuntu/Red Hat to increase LTS duration support)
									  https://www.androidauthority.com/linux-kernel-lts-extended-6-years-project-treble-803479/
								- 2 years official support max because of old kernel not LTS and OEM doesn't bother maintaining for long
							- _Related:_ [Initiatives to ensure longevity and regular security updates despite obstacles from OEMs](https://workflowy.com/#/85ee55ef847b)
							- 1 Backlink
							  collapsed:: true
								- _Related:_ [Android devices relying on proprietary hardware results in limitations](https://workflowy.com/#/515e1b87a8ca)
						- _Minor issues (2019 last checked)_
						  collapsed:: true
							- Android is getting more limited
								- Silent updates from N onwards
								  collapsed:: true
									- Chromebook's core features is the way it silently updates the operating system in the background, in an almost invisible way -- no intrusive prompts or annoying progress bars; new updates just download when they're available and then apply themselves without any fuss when the system restarts.
									- Starting with the upcoming "N" release, Android will work the same way: Devices will download and install system updates in the background, with a new version of the software simply appearing when the system next restarts. No long waits for downloading (that you're aware of, anyway), no endless-seeming spinning circle animation thingies, and no agonizing "Android is updating" boxes that keep you from using your phone while new software is applied.
								- Theming requires root from Android 9 onwards
								- Call recording is being heavily restricted
								  collapsed:: true
									- History
										- They have blocked access to real call recording on Android 6
										- See [Android 9 / P / Pie (2018)](https://workflowy.com/#/f2eee6b946da) - <a href="https://workflowy.com/#/d8ec4951b4c3">Disables non-root + non-system apps from call recording</a>
										- completely blocked call recording over the microphone on Android 10
										- In response, apps started using Accessibility Service to record calls on Android 10 and above
										- April 2022 (post-Android 12 release) - Google Play Store update bans apps from using Accessibility Service to record calls
											- Apps are no longer permitted to use Accessibility API for call recording on Google Play Store
											  source:: [https://support.google.com/googleplay/android-developer/answer/11899428#accessibility_preview](https://support.google.com/googleplay/android-developer/answer/11899428#accessibility_preview)
												- [https://teddit.net/r/Android/comments/u81i7b/google_will_kill_call_recording_apps_once_and_for/](https://teddit.net/r/Android/comments/u81i7b/google_will_kill_call_recording_apps_once_and_for/)
											- 1 Backlink
												- See [April 2022 (post-Android 12 release) - Google Play Store update bans apps from using Accessibility Service to record calls](https://workflowy.com/#/bd863300efaf)
									- Workarounds
										- System apps and root apps can still call record. Needed for Android 11+12?
									- See [Call recording apps](https://workflowy.com/#/3b40b1b5144b)
									- 1 Backlink
										- See [Stock Android AOSP](https://workflowy.com/#/5c6940e545df) - <a href="https://workflowy.com/#/2d492b1c1c5a">Call recording is being heavily restricted</a>
								- ((649b13cf-a825-48f5-ae83-b47b6ad6bff9)) will hinder custom ROM development; and make running Linux on Android(Zircon kernel)-based devices almost impossible
						- Limitations compared to Linux
						  collapsed:: true
							- No WINE access
							- limited productivity apps (no Thunderbird, LibreOffice, Gimp, Calibre
							- rooting is mandatory to backup the data of any app (including thenAndroid config settings, which in turn is much more convoluted) which lacks an "export & import" feature ([oandbackupx](https://github.com/machiav3lli/oandbackupx) is challenging to use due to Android limitations, such as app permissions)
							- Can't natively mount directories e.g. Rclone, VeraCrypt
							- command-line access restricted to what ((649b13ce-0b9e-4741-ba6d-7959858e3443)) provides, and the said program is limited by the Android OS (e.g. mpv can't display video without some third-party forks and other compatibility blocks/downright hacks)
							- too aggressive battery optimisation and background killing apps
							- Firefox (Fenix) doesn't essentially have feature-parity with the desktop version, especially about:config variables are mostly non-functional
						- Nearby Share doesn't work on Linux, ((63a9ade4-acd5-44f9-9166-2c1393865f7a)) should be used instead
						- ((631fa93e-1087-4996-91b8-7526842b4ba8)) doesn't allow sharing a VPN when sharing a hotspot or tethering. Guest devices will have to independently connect to a VPN
						  id:: 67d9699d-588b-487a-b0b3-ed875b814f9c
						- [2025 issues](https://divested.dev/pages/blog#2025-08-27-android-issues)
					- Unclear
						- [GApps](https://play.google.com/store/apps/details?id=com.google.android.gms)
						  id:: 6318fc66-9d9f-4547-8e1c-172958500c0d
						  collapsed:: true
						  AKA Google Mobile Services (GMS) / Google Play Services
							- Pros/Cons
							  collapsed:: true
								- Pros
									- Needed for much app functionality. However much of these can be achieved with [microG](https://workflowy.com/#/5b760a9e66c3) instead
									  collapsed:: true
										- Uber's map is inaccurate and not usable with microG. Relies on Google Play Services
											- 1 Backlink
												- See [Uber's map is inaccurate and not usable with microG. Relies on Google Play Services](https://workflowy.com/#/672191b32f79)
										- Needed for [Diopter Calculator app](https://workflowy.com/#/d19bbd08c7d6) - relies on ARCore
										- May break functionality of used Google apps like maps, analytics, AdWords, translate, play store
										- Other apps still use it like Revolut, Asana. Possibly Snapchat, WhatsApp, Instagram
										- Note: less breakage if never installed GApps rather than installing then trying to remove (I.e. use a ROM like LineageOS)
										- _{Archive}_
											- Asana uses it to interface with Google analytics, provide in app indexing, receive push notifications, facilitate login with a Google account
											- Problem is that if you don't allow Google high accuracy location services then Instagram uploaded pics can't have a tagged location
								- Cons
									- See [Android itself is non-free due to heavy reliance on Google Mobile Services](https://workflowy.com/#/9f418aba5d76)
									- Privacy risks
										- It expects special access and to be built into the OS
										  source:: [https://nitter.42l.fr/GrapheneOS/status/1437380920533823490#m](https://nitter.42l.fr/GrapheneOS/status/1437380920533823490#m)
										  collapsed:: true
											- The standard integration requires massively invasive access and privileges in the OS. It expects extensive access to internal privileged APIs and special SELinux MAC/MLS policy
											- It took us years to realize that there was a highly maintainable approach without privacy and security sacrifices: teaching Play services to work as it should have functioned in the first place. Fully sandboxed without special access/privileges like every other library/service.
										- It can remotely push apps to your phone without consent
										  collapsed:: true
											- [https://news.ycombinator.com/item?id=27558500](https://news.ycombinator.com/item?id=27558500)
												- [https://play.google.com/store/apps/details?id=gov.ma.covid19.exposurenotifications.v3&showAllReviews=true](https://play.google.com/store/apps/details?id=gov.ma.covid19.exposurenotifications.v3&showAllReviews=true)
											- You can also do it with consent by visiting Google Play Store in your browser
										- Google Play Protect can scan all apps - even those installed from unknown sources
										- It's always recording microphone data
										  https://www.makeuseof.com/tag/stop-google-android-listening/
										- Google Maps records battery status (allows fingerprinting)
										  https://techcrunch.com/2018/08/02/google-maps-location-sharing-will-now-share-your-phones-battery-status-too/
										- Google stores location data even with 'Location History' turned off
										  https://www.reddit.com/r/privacy/comments/96xb14/google_tracks_your_movements_even_with_location/e43uj7l/
										- Location Services will always upload your location to Google
										  source:: [https://news.ycombinator.com/item?id=27321298](https://news.ycombinator.com/item?id=27321298)
									- Bad defaults (doesn't require root to turn off)
										- Any Google account added to phone tries to sync app data to Google
										- Google play services and play store have access to usage data (which apps, how long etc)
									- Google play store will automatically update it's own settings
										- eg downloading Google Play services for Instant Apps without asking nor is there a way to block it
										- Only managed to see a download notification briefly then XPrivacy notification after new app downloaded
							- Installation/Uninstalling
							  id:: 631c3eab-c621-4fa0-a109-0e84ebfe8510
								- Installing
									- GrapheneOS's App store to install the 3 main GApps
									  id:: 631cacd9-4195-4d9c-a3ae-bffe81076ae4
									  collapsed:: true
										- There are 3 GApps, which need to be installed in sequential order:
										  id:: 631dcd68-68aa-4d89-9b88-3c2283fc951d
											- 1.  `com.google.android.gsf` (Google Services Framework) `/system/priv-app/GoogleServicesFramework/GoogleServicesFramework.apk` AKA `/data/app/~~9cHuMK07Ko9NWKpuQR_lVA==/com.google.android.gsf-ALlBLOeRopTXFsjVrlTr4A==/`
											- 2.  `com.google.android.gms` (Google Play Services) `/system/product/priv-app/GmsCore/`
											- 3.  `com.android.vending` (Google Play Store) `/system/product/priv-app/Phonesky/`
										- How to make them system apps
											- Unfinished SOP
											- `/system/priv-app/GoogleServices/Framework/` AKA `/data/app/~~9cHuMK07Ko9NWKpuQR_lVA==/com.google.android.gsf-ALlBLOeRopTXFsjVrlTr4A==/`
											- Via `adb shell`
												- `adb shell`
												- `mount` - shows available folders
										- Related:
											- ((631dcdbe-89c6-4051-8d76-e59a40559ad5))
											- ((6318fc64-5c92-4685-bd8e-2939200a1c95)) partition info
									- [OpenGApps](https://opengapps.org)
									  id:: 649b13d2-804a-4d55-b423-4cdad45edc51
									  collapsed:: true
										- [source] [https://github.com/opengapps/opengapps](https://github.com/opengapps/opengapps)
										- collapsed:: true
										  1. Pico (just Google Play Services)
										     source:: https://github.com/opengapps/opengapps/wiki/Pico-Package
											- This package is designed for users who want the absolute minimum GApps installation available. In this package you will find the core Google System Base, Google Android Shared Library, Google Play Store, Google Calendar Sync, Dialer Framework and the following Play Store applications:
											  collapsed:: true
												- Google Package Installer (replaces stock/AOSP Package Installer)
												- Google Play Services
											- For 6.0+ also:
											  collapsed:: true
												- Google Text-to-Speech
										- collapsed:: true
										  2. Nano
											- -
											  * Device Health Services
											  * Google Markup
											  * Google App (Search)
											  * Google Sounds
											  * Google Digital Wellbeing
										- collapsed:: true
										  3. Micro
											- -
											  * Google Calendar (replaces stock/AOSP Calendar)
											  * Google Pixel Launcher
											  * Gmail
										- collapsed:: true
										  4. Mini (includes Maps, YouTube, Messages
										     source:: https://github.com/opengapps/opengapps/wiki/Mini-Package
											- Google Calculator (replaces stock/AOSP Calculator)
											- Google Clock (replaces stock/AOSP Clock)
											- Google Maps
											- Google Messages (not installed on tablet devices) (replaces stock/AOSP SMS app)
											- Google Photos (replaces stock/AOSP Gallery)
											- Google Tags (replaces stock/AOSP NFC Tags)
											- YouTube
									- [MindTheGapps](https://gitlab.com/MindTheGapps/vendor_gapps)
									  collapsed:: true
										- https://androidfilehost.com/?w=files&flid=322935
								- Uninstalling
								  collapsed:: true
									- Summary: no working method I'm aware of currently
									- Trying
										- Wipe > LineageOS > MicroG Installer > wipe > LineageOS
										- Use `adb shell` to uninstall GApps
										  id:: 631dcdbe-89c6-4051-8d76-e59a40559ad5
											- Doesn't matter if you have root or not, and doesn't matter if they're installed as system apps
											- Enter the adb shell
											  `adb shell`
											- List all OEM and carrier apps installed on phone
											  `pm list packages | grep '<OEM/Carrier/App Name>'`
												- Alternatively use the app App Manager from F-Droid to check the package names
											- Check what users are installed `adb shell pm list users`
											- Uninstall `NameOfPackage`
											  `pm uninstall -k --user 0 NameOfPackage`
												- e.g. `pm uninstall -k --user 0 com.google.android.gms`
												- work profile is -1 for some reason, so `adb uninstall --user -1 com.appname`
											- Related: ((631cacd9-4195-4d9c-a3ae-bffe81076ae4))
										- Wiping `/data` partition of installed apps may be required
										- Systemless Debloater from Fox's Magisk Module Repo?
									- Tried, didn't work
										- **Lead to bootloop**
											- Wipe > flash LineageOS for microG ROM
											- Wipe > LineageOS > [MicroG Installer](https://github.com/micro5k/microg-unofficial-installer/releases) (which includes a GApps uninstaller)
												- Note: can't flash MicroG Installer without an OS already present, the ZIP prevents it otherwise
												- Use microG unofficial installer, which also removes GApps. Then wipe 3 partitions using TWRP custom recovery, then reboot to LineageOS recovery and flash LineageOS ZIP alone using it. Reboot system
											- Wipe 3 partitions using TWRP custom recovery, then reboot to LineageOS recovery and flash LineageOS ZIP alone using it. Reboot system
												- ((6318fc64-baac-43f1-9d6d-8c7190588edf))
												- Save to `~/Documents/OPTIONAL/Android/`
												- Wipe ART/Dalvik, Cache and System only! This will wipe the OS but your apps nor internal storage
												  See [Android partitions](<((6318fc64-0a33-4133-9f0d-ec0fc1a46d62))>) for more info
												- Boot into LineageOS recovery ( ((6318fc64-69c1-47ce-ae59-ddbaec207165)) )
												- Flash the same custom rom again (TWRP: Advanced > ADB Sideload > `adb sideload lineage-19.1-20220903-nightly-beryllium-signed.zip`)
												- Either
													- Apply update > Apply from ADB > `adb sideload lineage-19.1-20220903-nightly-beryllium-signed.zip`)
													- OR
													- Install > choose ZIP from microSD
												- {Archive}
													- https://wiki.lineageos.org/devices/beryllium/install#installing-lineageos-from-recovery
											- ((631c620f-070b-42bd-8d81-5260412c6947)). Wipe those partitions using TWRP custom recovery, then reboot to LineageOS recovery and flash LineageOS ZIP alone using it. Reboot system
										- **Booted, but still had bug of Google Play Services constantly crashing**
											- Wipe 3 partitions using TWRP custom recovery, then reboot to LineageOS recovery and flash LineageOS ZIP and then GApps (MindTheGapps June 2022) using it. Reboot system
									- Insufficient - GApps also installs to [`/data` partition](<((6318fc64-080f-48d1-bc10-7d40a08c43bf))>) ?
									- Remove `/system/addon.d/70-gapps.sh`
									  id:: 631c620f-070b-42bd-8d81-5260412c6947
										- Open GApps normally installs a 70-gapps.sh ROM update or re-flash survival script in the /system/addon.d/ folder so doing what you suggested will not remove Open GApps on ROMs who support addon.d like LineageOS for example.
										- Delete 70-gapps.sh first then re-flash ROM after wiping System & caches but NOT Data & you will not loose your other apps, data & settings.
								- Note: non-GApps Google apps currently used
									- Maps
									- My Maps
									- Gboard
									- Translate
							- Software included
								- [Google Play Store](https://play.google.com)
								  id:: 66d095d8-4f55-4927-bc65-eaa9a58b0630
							- _Alternative_
								- [microG](https://microg.org/)
								  id:: 649b13d2-f7fb-449f-808b-d819f81d3094
								  collapsed:: true
									- Links
										- https://github.com/microg/android_packages_apps_GmsCore
										- https://www.reddit.com/r/MicroG
									- [https://stackoverflow.com/questions/37337448/what-is-the-difference-between-google-service-frameworkgsfgoogle-mobile-servi](https://stackoverflow.com/questions/37337448/what-is-the-difference-between-google-service-frameworkgsfgoogle-mobile-servi)
									- _Journal_
									  collapsed:: true
										- Wed, Jan 20, 2021
											- Annoying that [Citymapper](https://workflowy.com/#/35535435574e) is unreliable as it uses the new Maps v2 API. Google Maps (web app or native) can provide train/bus schedules but the UX isn't as good. This map be fixed in the Mapbox builds but I haven't bothered with reinstalling for it yet
									- Pros/Cons
									  collapsed:: true
										- Pros
											- Avoids the privacy risks of ((6318fc66-9d9f-4547-8e1c-172958500c0d))
											- Uses less data/battery/storage memory than GApps
											- Pretty decent support for GApps features
												- FCM/GCM support added to allow push notifications e.g. Discord, WhatsApp, Signal
												  collapsed:: true
													- _Current used apps which use FCM push notifications - last updated <time startYear="2021" startMonth="7" startDay="8"_
													  Only includes apps which have sent a registered notificaiton
														- Barclays
														- Blockfolio
														- Bolt
														- Delta
														- Discord
														- Element
														- Firefox
														- Firefox Nightly
														- Foursquare
														- ((649b1463-b077-434e-a501-df6e30d6c4fb))
														- GitHub
															- Note: OctoDroid doesn't need push notifications
														- Instagram
														- Notion
														- ((6654edaf-be09-46b8-a9d7-d808d7bed3ab))
														- Signal
															- Note: uses WebSockets in absence of gapps
														- Todoist
														- UptimeRobot
														- ((663b24fb-f1f2-4dbe-ae47-d3a910654835)) stuff
															- Note: Apparently uses a fallback XMPP server without gapps
													- Push notifications seem fine and reliable in my testing
														- Steps to set it up
															- There seems to be an issue with automatic device registration in latest version. If you have similar issues as described by @Mafus1, open the system phone app and dial _#_#2432546#_#_ to do a manual device registration.
															  Q4 2018 https://github.com/microg/android_packages_apps_GmsCore/issues/439#issuecomment-433018720
															- enable "Google device registration" in microG settings
															- enable "GCM" in microG settings
															- installed the "push notificaiton tester" app
															- Reinstall apps to register them with GCM
															- Did you uncheck the "Confirm new apps" option under Google Cloud Message in MicroG settings?
												- Aurora Store is decent
												  collapsed:: true
													- _Can_
														- Download already paid-for apps (which you can buy on Google Play website)
															- ((649b13ce-6535-4d48-a434-b44092fda1a0))
															  id:: 644c0ad0-fe5c-4a48-ad2d-d2ed42b11637
															- _Paid apps which have a "payment verification" app or file_
																- ((649b13cd-4504-4d24-8dc2-d589cedd0eea)) PRO key
																- AFWall+ Unlocker (I have the donate app version, but Unlocker is needed to work with the Free app) - **£6.49**
																  _See_ [AFWall](https://workflowy.com/#/e5f2eed18186)
													- _Can't_
														- microG doesn't support in-app purchases in Q3 2018 so
														  [https://www.bountysource.com/issues/41943746-in-app-purchase-support](https://www.bountysource.com/issues/41943746-in-app-purchase-support) / <a href="https://github.com/microg/android_packages_apps_GmsCore/issues/309">https://github.com/microg/android_packages_apps_GmsCore/issues/309</a>
										- Cons
											- GrapheneOS' approach with sandboxed Google Play Services is better in many respects
											  collapsed:: true
												- broad app compatibility, maintainability and security
												- "[microG] not as secure as the official Play services implementation and doesn't provide comparable privacy for user data. It leaks user data across apps, doesn't properly enforce the API security model and doesn't provide comparable transport security via pinning and other measures."
												  source:: GrapheneOS [https://nitter.42l.fr/GrapheneOS/status/1437380920533823490#m](https://nitter.42l.fr/GrapheneOS/status/1437380920533823490#m)
											- ROMs with built-in microG have less supported devices and may take longer than [LineageOS](https://workflowy.com/#/1543bac42ca5) or <a href="https://workflowy.com/#/5c6940e545df">Stock Android AOSP </a> to get the latest Android version
											- Some apps are dependent on GApps
											  collapsed:: true
												- See [Uber's map is inaccurate and not usable with microG. Relies on Google Play Services](https://workflowy.com/#/672191b32f79)
												- Note: use [Plexus](https://plexus.techlore.tech) to check whether an app needs GCM or not
												  id:: 649b13d2-abc9-4fb0-a722-1313c6d874b8
												  collapsed:: true
													- [https://github.com/techlore-official/plexus](https://github.com/techlore-official/plexus)
												- _Untested_
												- WhatsApp backups to Google Drive fail (Oct 2021). E2EE soon
												- See Diopter Calculator
												- ((649b13ca-0417-44e6-ab64-fa0ebae72f22))
												- _Requires maps API v2 or unusable_
												  collapsed:: true
												  [Maps API (mapsv1) is a system library, providing the same functionality as now deprecated Google Maps API (v1).](https://workflowy.com/#/0e649e40591a)
													- _Doesn't work and there's no alternative_
														- Uber (tested in Q1 2021, the web app is no longer useable in London as well)
													- _Mostly doesn't work, glitchy_
													- _However there is a web app available _
														- Tinder
															- Pros/Cons
																- Cons
																	- Match Group apps including Tinder are partnering with GARBO to allow background checks on users
																	  source:: 9m [https://youtu.be/J9U-4j-OtWE](https://youtu.be/J9U-4j-OtWE)
															- 4 Backlinks
																- See [Tinder](https://workflowy.com/#/1d745abfd07e)
																- See [Tinder](https://workflowy.com/#/1d745abfd07e)
																- See [Tinder](https://workflowy.com/#/1d745abfd07e)
																- See [Tinder](https://workflowy.com/#/1d745abfd07e)
														- See [Citymapper](https://workflowy.com/#/35535435574e) (most of the time the GPS takes ages to pinpoint)
														- Google Maps (most of the time the GPS takes ages to pinpoint)
													- ## _Currently works but may not permanently_
												- _However there are new microG builds which use a Mapbox-based Maps v2 API. Worth testing these_
												  collapsed:: true
													-
											- [It doesn't support certain Google apps/services/APIs](https://github.com/microg/GmsCore/wiki/Implementation-Status)
											  collapsed:: true
												- It does allow
													- Gboard - gesture typing
													- See [Google Camera](https://workflowy.com/#/819ac3cc5131) (may require additional apk)
												- It doesn't allow
													- Google Lens
														- Requires you to install the Google app (not Lens) + requires Google Mobile Services
														- Need VR/AR?
												- _Untested_
													- Google Pay
											- Google Play store may be necessary for paid apps and in-app purchases
											  collapsed:: true
												- _Frequent in-app purchases_
													- See [Tinder](https://workflowy.com/#/1d745abfd07e)
												- https://github.com/microg/android_packages_apps_GmsCore/issues/309#issuecomment-368274404
											- Having to enable signature spoofing is a security vulnerability
											  collapsed:: true
												- LineageOS has far weaker security than GrapheneOS but even they consier it to be an unacceptable threat to the Android security model
												-
											- Google is making it more difficult to use microG
											  collapsed:: true
												- ((649b13d2-3bf6-43ed-b52c-7bbcf094ca3c))
												  collapsed:: true
												- app bundles
												  collapsed:: true
													- marketed as a way to ease app deployment and improve user experience, and also requiring dev opt-in, the technology is really about devs surrendering their signing keys to google. everything that this technology claims to do can be done without such a bold requirement. but what this technology achieves without stating it is inhibiting sideloading and blocking competing markets. and how long before google starts to inject their code inside all apps? what about their code failing unless running on a googlephone rendering in-the-wild apps unusable for "compatible" android platforms?
												- [source] https://gitlab.com/Nanolx/NanoDroid#stock-rom-without-gapps-custom-rom-withwithout-opengapps
												  collapsed:: true
													- if you want to use microG make sure the ROM is either pre-patched with signature spoofing support or deoxeded so you can patch yourself see here
													- you can use the Patcher package to de-odex (up to Android 8.1) and/or patch services.jar (up to Android 9.0)
											- Other issues
											  [https://www.bountysource.com/teams/microg/issues](https://www.bountysource.com/teams/microg/issues)
									- Overview
									  collapsed:: true
										- MicroG is "[a] free-as-in-freedom re-implementation of Google’s proprietary Android user space apps and libraries" -- it essentially replaces GPSe. It allows you to "run apps that use Google Play Services or Google Maps Android API (v2)", use a Network Location Provider (NLP) to calculate approximate location without using your phone's GPS, and allows Play Store apps to have proper push notifications with Google Cloud Messaging (GCM). Apart from being FOSS, all of the MicroG components take up less than 50MB of storage, use less data and battery, and are free of spyware.
										- _Components_
										  [https://github.com/microg/GmsCore/wiki/Implementation-Status](https://github.com/microg/GmsCore/wiki/Implementation-Status)
											- Service Core (GmsCore) is a library app, providing the functionality required to run apps that use Google Play Services or Google Maps Android API (v2).
											  collapsed:: true
												- More details and installation instructions
												- https://github.com/microg/android_packages_apps_GmsCore/wiki
											- Services Framework Proxy (GsfProxy) is a small helper utility to allow apps developed for Google Cloud to Device Messaging (C2DM) to use the compatible Google Cloud Messaging service included with GmsCore.
											  collapsed:: true
												- Read GmsCore documentation for details
												- https://github.com/microg/android_packages_apps_GmsCore/wiki
											- [UnifiedNlp](https://github.com/microg/android_packages_apps_UnifiedNlp)
											  id:: 649b13d2-f567-4c93-b93e-5b0c563a0aec
											  collapsed:: true
											  AKA Unified Network Location Provider
												- Links
													- [https://f-droid.org/repository/browse/?fdfilter=nlp&fdid=com.google.android.gms](https://f-droid.org/repository/browse/?fdfilter=nlp&fdid=com.google.android.gms)
												- What is it
												  collapsed:: true
													- A location middleware provider
													- Unified Network Location Provider (UnifiedNlp) is a library that provides Wi-Fi- and Cell-tower-based geolocation to applications that use Google’s network location provider. It is included in GmsCore but can also run independently on most Android systems.
														- More details and installation instructions
														- [https://github.com/microg/android_packages_apps_UnifiedNlp/blob/master/README.md](https://github.com/microg/android_packages_apps_UnifiedNlp/blob/master/README.md)
												- How to
												  collapsed:: true
													- Download
													  collapsed:: true
														- Can be downloaded from F-Droid, or it comes with microG
													- Usage
													  collapsed:: true
														- If using LineageOS, need to install it as a system app to use it as a location provider
													- UnifiedNlp alone does not provide any features, but acts as a middleware for multiple backends. Most of them can be downloaded and updated using F-Droid. Here is a list of backends known to me.
													- List of backends for geolocation:
													  collapsed:: true
														- AppleWifiNlpBackend - Uses Apple's service to resolve Wi-Fi locations. It has excellent coverage but the database is proprietary.
														- OpenWlanMapNlpBackend - unmaintained - use OpenBmap
															- Uses OpenWlanMap.org to resolve user location but the NLP backend did not reach release-quality, yet. Users interested in a freely licensed and downloadable database for offline use should stick with openBmap for now - Last updated in 2015
														- OpenBmapNlpBackend - Uses openBmap to resolve user location. Community-created, freely licensed database that can optionally be downloaded for offline operation. The coverage varies from country to country (it's best in central Europe).
															- https://github.com/wish7code/org.openbmap.unifiedNlpProvider
														- MozillaNlpBackend - Uses the Mozilla Location Service to resolve user location. The coverage is OK. Only the cell tower database is free.
														- LocalWifiNlpBackend - Local location provider for Wi-Fi APs using on-phone generated database.
															- https://github.com/n76/wifi_backend
														- LocalGSMBackend - Local location provider for GSM cells. It works offline by downloading freely licensed database files from Mozilla, OpenCellID, or lacells.db.
															- https://github.com/n76/Local-GSM-Backend
													- List of backends for (reverse) geocoding:
													  collapsed:: true
														- NominatimGeocoderBackend - Address lookup backend.
												- UnifiedNlp
												  collapsed:: true
													- UnifiedNlp is the microG Network Location Provider, which provides the current location of the device without the use of the GPS. While Google's NLP can only use Google's servers for positioning, UnifiedNlp obtains the geolocation through different plugins, which interface to different services.
													- By default there are two plugins installed:
														- MozillaNlpBackend, which uses the Mozilla Location Service (online)
														- NominatimNlpBackend, which uses MapQuest's Nominatim service (based on OpenStreetMap) for geocoding (online)
													- If you want to use these plugins, go to microG Settings -> UnifiedNlp Settings, configure and enable both.
													- If you instead want different plugins (like the LocalGsmNlpBackend, which uses a local offline database of the GSM towers to obtain the location) you can download them in F-Droid and enable them in the same way.
													- Reboot and check whether UnifiedNlp is correctly set up in the "Self-Check" section of the "microG Settings" app.
												- Location provider backends
												  collapsed:: true
													- Comparison
													  [https://github.com/GrapheneOS/os_issue_tracker/issues/24#issuecomment-792069571](https://github.com/GrapheneOS/os_issue_tracker/issues/24#issuecomment-792069571)
													- List of backends for geolocation:
														- _Updated in 2021_
															- Déjà Vu
															  collapsed:: true
															  AKA org.fitchfamily.android.dejavu
																- UnifiedNlp backend that uses locally acquired WLAN/Wi-Fi AP and mobile/cellular tower data to resolve user location. This backend uses no network data. All data acquired by the phone stays on the phone.
																- Review
																	- Compared to [Local GSM Location](https://workflowy.com/#/cb7310854432) Deja Vu additionally has Wi-Fi data and thus better accuracy
																	- I found that this gives very good results when able to learn from an enabled GPS. I believe it might be a problem for GrapheneOS that this backend basically builds an on-phone database of visited locations. If you would ever have to hand over your phone-data, you would have to hand over where you have been.
															- Local GSM Location
															  collapsed:: true
															  AKA LocalGsmNlpBackend / org.fitchfamily.android.gsmlocation
																- Uses an offline database blended from [opencellid.org](https://opencellid.org) (GSM cell data) and <a href="https://location.services.mozilla.com/">Mozilla Location Service (MLS)</a>. Can download directly from these services or from a <a href="https://github.com/wvengen/lacells">repository at github</a>.
																- Review
																	- As for the locations, for me, results are mixed. The phones I have available only report the stongest network cell, not neighboring cells.
																	- Triangulation is thus impossible. The strongest cell near my home is not mapped by either opencellid or MLS. When in other places, I do get locations from this backend. These locations are often both off and have a quite large reported confidence area of 1000-5000m. The true location is most of the time in the reported confidence area.
																	- As a side note, as far as I can see, the returned confidence radius does not take into account the definition differences of Android (68% confidence) with ranges returned from MLS ([some kind of "100%" confidence](https://ichnaea.readthedocs.io/en/latest/algo/observations.html#the-station-model)) or from opencellid (<a href="https://community.opencellid.org/t/documenting-the-columns-in-the-downloadable-cells-database-csv/186">98% confidence</a>).
																- A facility in the setting menu allows you to create a database using data from OpenCellId and/or Mozilla Location Services CSV files. Alternatively, the on-phone database can be generated in advance via the lacells-creator scripts that gather tower information from those two sources, too.
																- This backend performs no network data. All data acquired by the phone stays on the phone and no queries are made to a centralized AP location provider.
																- Location calculation is done onboard and works without network connectivity. The cell-tower based lookup for your current location is implemented via a included binary cell database extracted from OpenCellID.
																- This "NetworkLocationProvider" works without network connectivity and will never post your data anywhere. You are thus encouraged to help OpenCellID to gather more cells in order to improve this project.
																- 1 Backlink
																	- Compared to [Local GSM Location](https://workflowy.com/#/cb7310854432) Deja Vu additionally has Wi-Fi data and thus better accuracy
														- Apple UnifiedNlp Backend uses Apple's Wifi database.
														- MozillaNlpBackend uses Mozilla Location Services
														- OpenWlanMapNlpBackend uses [OpenWlanMap.org](http://OpenWlanMap.org)
														- [Radiocells.org](http://Radiocells.org)
														  AKA OpenBmapNlpBackend
															- uses [Openbmap.org](http://Openbmap.org) / radiocells.org
														- _Outdated_
															- LocalWifiNlpBackend
															  AKA WiFi Location Service / org.fitchfamily.android.wifi_backend
																- Superceded by Deja Vu backend
																- Uses (on-device generated) WiFi data (local)
													- List of backends for (reverse) geocoding:
													  This allows convert geo-coordinates to an address, resulting in better user experience.
														- NominatimNlpBackend
											- Store (Phonesky) <- instead use Yalp Store
											  collapsed:: true
												- is a frontend application providing access to the Google Play Store to download and update applications. Development is in early stage and there is no usable application yet.
											- _Outdated_
											  collapsed:: true
												- Maps API (mapsv1) is a system library, providing the same functionality as now deprecated Google Maps API (v1).
												  collapsed:: true
													- More details and installation instructions
													- https://github.com/microg/android_frameworks_mapsv1
													- 1 Backlink
														- _Requires maps API v2 or unusable_
														  [Maps API (mapsv1) is a system library, providing the same functionality as now deprecated Google Maps API (v1).](https://workflowy.com/#/0e649e40591a)
									- Using microG
									  collapsed:: true
										- _Installing microG_
											- _ROMs with microG included_
												- [LineageOS for microG](https://lineage.microg.org/)
												  id:: 649b13d2-a633-4de3-aa08-e24106059dab
												  collapsed:: true
													- Pros/Cons
														- Pros
															- Supports every LineageOS device
															  [https://download.lineage.microg.org/](https://download.lineage.microg.org/)
															- updating LOS will include the latest ((649b13d2-f7fb-449f-808b-d819f81d3094))
															  id:: 644c0ad0-f9ed-4997-83c1-70a3966ef50c
														- Cons
													- [https://forum.xda-developers.com/android/software/lineageos-microg-t3700997](https://forum.xda-developers.com/android/software/lineageos-microg-t3700997)
													- [LineageOS (for](https://lineage.microg.org/) ((649b13d2-f7fb-449f-808b-d819f81d3094)) )
														- https://download.lineage.microg.org/sailfish/
														- Get LineageOS for microG - because unlike official LineageOS it's deodexed? thus signature spoofing works
														- LineageOS
															- https://wiki.lineageos.org/devices/sailfish
															- Latest ROM
															  https://forum.xda-developers.com/pixel/development
															- Note: according to LineageOS subreddit LineageOS 17 isn't out for any device yet (Nov 2019)
														- LineageOS (for microG) OR just use LineageOS + NanoDroid
															- Why do we need a custom build of LineageOS to have microG? Can't I install microG on the official LineageOS?
																- MicroG requires a patch called "signature spoofing", which allows the microG's apps to spoof themselves as Google Apps. LineageOS' developers refused (multiple times) to include the patch, forcing us to fork their project.
																	- https://review.lineageos.org/#/c/64967/
																	- https://review.lineageos.org/#/c/65366/
																	- https://review.lineageos.org/#/c/195283/
													- Related: ((630f96f0-f2c4-4706-9d72-58e13201e03f))
												- ((649b13d0-bf0d-4357-82c5-c3e1ffc28138))
											- NanoDroid + ROM with signature spoofing support
											  collapsed:: true
												- NanoDroid
													- NanoDroid is a installer for various OpenSource related things, most noticably microG and F-Droid. It supports direct /system installation, both devices with or without A/B partition scheme, aswell as Magisk Mode (module) installation. It also includes several tools (eg. GNU Bash, GNU Nano, more), scripts, fonts, sounds and additional features (system debloating, init scripts, automatic logcat creation), aswell as a companion F-Droid Repository.
													- Furthermore it allows the user to do fine-graded installations using configuration files, which allow to choose what to install, or if several alternatives are available, which of them, see "Alter Installation" in the full documentation (link at the end of this post).
													- In order for full microG experience NanoDroid contains a modified Play Store which allows (in-)app-purchases with microG, which would normally not be possible. It also tries to remove all previously installed GApps on it's own. For ROMs without builtin signature spoofing support NanoDroid includes an on-device Patcher which tries to patch your ROM from TWRP.
													- _Pros_
													  collapsed:: true
														- modified Play Store which allows (in-)app-purchases with microG, which would normally not be possible
															- NanoDroid does now have a companion F-Droid Repository for easy updates of Play Store (patched with (in-)app-purchase support) and MPV builds Repository Info-Page
															  https://nanolx.org/fdroid/repo/
														- Can be used to keep microG layer up-to-date
													- Support thread
													  https://forum.xda-developers.com/apps/magisk/module-nanomod-5-0-20170405-microg-t3584928
													- Download
													  collapsed:: true
														- https://downloads.nanolx.org/NanoDroid/
														- https://gitlab.com/Nanolx/NanoDroid
													- Installation method
													  https://gitlab.com/Nanolx/NanoDroid#stock-rom-without-gapps-custom-rom-withwithout-opengapps
											- Magisk package
											- Use a deodexed ROM +
											  collapsed:: true
												- microG unofficial installer - automatically remove GApps and install microG
												  https://forum.xda-developers.com/showthread.php?t=3432360
													- I have created a flashable ZIP that automatically remove GApps and install microG: microG unofficial installer
										- _Updating microG_
											- If you have ((649b13d2-a633-4de3-aa08-e24106059dab)), then ((644c0ad0-f9ed-4997-83c1-70a3966ef50c))
										- _Setting up microG_
											- ((649b13d2-f567-4c93-b93e-5b0c563a0aec))
											- F-Droid
											  collapsed:: true
												- You have the F-Droid Privileged Extension installed by default, why not use it? To make a good use of it go to the F-Droid Settings and enable auto updates.
											- Google Cloud Messaging
											  collapsed:: true
												- Many apps rely on the Google Cloud Messaging, a Google proprietary system to push notifications to your device. This feature is implemented in microG but, as not every user requires it, is disabled by default. If you need it, enable the "Google Device registration" and the "Google Cloud Messaging" features in the "microG Settings" app.
											- Weather service
											  collapsed:: true
												- If you want the weather features of LineageOS (like in the lock screen or in the cLock widget) you have to download a weather provider from [here](https://download.lineageos.org/extras). Choose your favorite one, install it and configure it in cLock (or in Settings → Apps → Gear icon → Weather).
											- SU (root)
											  collapsed:: true
												- Our ROM doesn't include root by default for security reasons, but you can easily install it: go [here](https://download.lineageos.org/extras), download the appropriate ZIP and install it from the recovery.
									- Using microG
									  collapsed:: true
										- assorted
										  collapsed:: true
											- you need signature spoofing for it to work (fake that you're the real Google Play Services)
												- https://github.com/microg/android_packages_apps_GmsCore/wiki/Signature-Spoofing
												- Not in LineageOS ROM
												- https://www.reddit.com/r/LineageOS/comments/5qcryp/lineageos_signature_spoofing_for_microg/
												- Maybe via LineageOS
												  collapsed:: true
													- Yes, I am. How? Because I'm doing it
													- https://www.reddit.com/r/LineageOS/comments/5qe9j4/users_what_do_you_use_as_an_xposed_alternative/dcz03tk/
													- Ask any further questions if you wish. I have microG working in its fullest on LineageOS nightly 20170123.
													- Edit: You'll likely run into one other problem. The UnifiedNlp component to microG doesn't work anymore on Android 7+ unless you install it as a privileged app. This is due to the fact that only privileged apps have been hard-coded access to provide locations. That being said, the recipe that works for me is;
													- Before you upgrade copy over your previous GmsCore.apk from /system/priv-app/ (first time ignore this) to /sdcard/
													- Upgrade system through twrp or other
													- Patch system with Tingle (figure this separate sub-process out on your own)
													- Copy GmsCore.apk back to /system/priv-app/
													- Install LineageOS extras - (for su, and persists if you've already installed)
													- Yeah it sucks that it's not as simple as just not having Gapps and installing the microG app as normal, but this is how it is now.
												- https://www.reddit.com/r/LineageOS/comments/5qe9j4/users_what_do_you_use_as_an_xposed_alternative/dcz05jg/
												- Maybe in other ROMs eg NitrogenOS, OmniRom
												- Xposed+FageGapps
												- Tingle
												  collapsed:: true
													- https://github.com/ale5000-git/tingle
													- Additionally if you want the built-in UnifiedNlp to work from GmsCore you also need to install it as a /system/priv-app/ apk, More about that here
													- https://www.reddit.com/r/LineageOS/comments/5qe9j4/users_what_do_you_use_as_an_xposed_alternative/dcz05jg/
											- https://www.reddit.com/r/androidapps/comments/5igwf2/how_to_install_microg/
												- https://forum.xda-developers.com/android/development/microg-unofficial-installer-t3432360
										- Setup
										  collapsed:: true
											- Set up Signature Spoofing
												- https://github.com/microg/android_packages_apps_GmsCore/wiki/Signature-Spoofing
											- Did you enable Google Cloud Messaging in the microG settings? You need to do that before you install the apps (if you have already installed them, you need to uninstall them, then reinstall them).
											- Additionally if you want the built-in UnifiedNlp to work from GmsCore you also need to install it as a /system/priv-app/ apk, More about that here
										- WhatsApp
										  collapsed:: true
											-
											- GDrive backup may not work?
											- WhatsApp without GDrive is possible (but not necessary)
											  https://faq.whatsapp.com/en/android/20887921
												- Note: The easiest way to transfer data to a new phone is by using Google Drive. If you want to use a local backup, you'll need to transfer the files to the new phone using a computer, file explorer or SD Card. If your data isn't stored on the /sdcard/WhatsApp/folder, you might see "internal storage" or "main storage" folders.
									- https://forum.xda-developers.com/android/apps-games/app-microg-gmscore-floss-play-services-t3217616/page510
									- xposed module fakegapps.
									- _Related: _
										- Alternatives for ((649b1407-93b8-4b76-9528-5bf2a10d9870))
								- ((635037d0-5875-4083-8a49-4c68a6af8843))
					- _Compared to Linux_
					  collapsed:: true
					  id:: 631fa93d-9604-49fd-b8d3-2731d6dc41bb
					  Desktop or mobile vesions
						- Pros
							- Linux devices lack modern hardware-dependent security features
							  collapsed:: true
								- Verified boot
								  [https://source.android.com/security/verifiedboot/](https://source.android.com/security/verifiedboot/)
								- ((644c0acf-58a1-4b82-9767-c88c65955315))
								- rollback protection
								- Hardware backed keystore
								  [https://source.android.com/security/keystore/](https://source.android.com/security/keystore/)
								- Linux phones are marketed with useless hardware security features
									- Hardware Kill Switches
									  collapsed:: true
										- Hardware kill switches are nothing but marketing frills.
										- The microphone kill switch is useless since audio can still be gotten via the sensors (such as the gyroscope).
										  [https://crypto.stanford.edu/gyrophone/files/gyromic.pdf](https://crypto.stanford.edu/gyrophone/files/gyromic.pdf)
										- While the Librem 5 does have a "lockdown mode" that disables the sensors, it also requires flipping all of the other switches, including the network ones which effectively turns your device into a brick just to prevent audio recording.
										- The network kill switch is useless since the attacker will just wait until you turn them back on again to exfiltrate data. If you need to disable network access, you can use airplane mode.
										- The camera kill switch can be useful as a small usability improvement but it is really no better than some tape.
									- Modem Isolation
									  id:: 649b13d1-e2a8-451b-bd09-44269a1b0ed5
									  collapsed:: true
										- Modem isolation isn't anything special. ((644c0acb-a922-4046-b811-c90172124515))
										- The way the Librem 5 isolates the modem is via the Linux kernel USB stack which is not a strong barrier as shown in the Linux article.
										  [https://madaidans-insecurities.github.io/linux.html](https://madaidans-insecurities.github.io/linux.html)
										- There is also a lot of misinformation about how the modem being on a separate chip means it's isolated. This is completely untrue. Just look at how FireWire for example can be used for DMA yet it's completely separate from the rest of the hardware. Whether the modem is on a separate chip or not is irrelevant to if it's isolated.
										  [https://en.wikipedia.org/wiki/IEEE_1394#Security_issues](https://en.wikipedia.org/wiki/IEEE_1394#Security_issues)
										- ((644c0acc-16fa-4526-91aa-c590a321bb77))
							- Stronger security model
							  collapsed:: true
								- Linux devices are missing many security features
								  collapsed:: true
									- File-Based Encryption doesn't exist at all (thus no protection against DMA/cold boot attacks)
									  #Privacy [Android OS - File-Based Encryption (FBE) - encrypted whilst lock screen on](https://workflowy.com/#/5d03615e5a79)
									- They do not have full system MAC policies
									- Lacks hardened kernels
									  collapsed:: true
									  [https://source.android.com/security/overview/kernel-security](https://source.android.com/security/overview/kernel-security)
										- It is a monolithic kernel written entirely in a memory unsafe language and has hundreds of bugs, many being security vulnerabilities, found each month.
										  [https://events19.linuxfoundation.org/wp-content/uploads/2017/11/Syzbot-and-the-Tale-of-Thousand-Kernel-Bugs-Dmitry-Vyukov-Google.pdf](https://events19.linuxfoundation.org/wp-content/uploads/2017/11/Syzbot-and-the-Tale-of-Thousand-Kernel-Bugs-Dmitry-Vyukov-Google.pdf)
										- In fact, there are so many bugs being found in the kernel, developers can't keep up which results in many of the bugs staying unfixed for a long time.
										  [https://syzkaller.appspot.com/upstream](https://syzkaller.appspot.com/upstream)
										- The kernel is also decades behind in exploit mitigations
										  [https://jon.oberheide.org/files/syscan12-exploitinglinux.pdf](https://jon.oberheide.org/files/syscan12-exploitinglinux.pdf)
										- and many kernel developers simply do not care enough.
										  [https://www.washingtonpost.com/sf/business/2015/11/05/net-of-insecurity-the-kernel-of-the-argument/](https://www.washingtonpost.com/sf/business/2015/11/05/net-of-insecurity-the-kernel-of-the-argument/)
									- Weak app sandboxing
									  id:: 649b13d1-9916-4123-b233-28fa415ea885
									  collapsed:: true
										- (5 trivial flaws allow you to get root password running in a "sandbox").
										- (Qubes + Docker is the best atm. Or possibly Snap/Flatpak, or LXC containers)
										- [source] [https://www.reddit.com/r/CopperheadOS/comments/85dia6/comparable_desktop_os/dvwndnt/](https://www.reddit.com/r/CopperheadOS/comments/85dia6/comparable_desktop_os/dvwndnt/)
										- Flatpak hasn't got strong sandboxing
										  collapsed:: true
											- Flatpak aims to sandbox applications but its sandboxing is very flawed.
											  [https://flatkill.org/](https://flatkill.org/)
											- It fully trusts the applications and allows them to specify their own policy. This means security is optional and apps can just choose not to be sufficiently sandboxed.
											- Flatpak's permissions are also far too broad to be meaningful. For example, many applications come with filesystem=home which is read-write access to the user's home directory, giving access to all of your personal files and allowing trivial escapes via writing to ~/.bashrc or similar.
											- Another example of Flatpak's broad permissions is how it allows unfiltered access to the X11 socket, allowing easy escapes due to X11's lack of GUI isolation.
											- Adding X11 sandboxing via a nested X11 server such as Xpra is easy but Flatpak developers refuse to acknowledge this and continue to claim "X11 is impossible to secure".
											  [https://blogs.gnome.org/alexl/2015/02/17/first-fully-sandboxed-linux-desktop-app/](https://blogs.gnome.org/alexl/2015/02/17/first-fully-sandboxed-linux-desktop-app/)
											- Even more examples of this is how Flatpak gives full access to directories such as /sys or /proc (kernel interfaces known for information leaks).
											- Another example is how the seccomp filter only blacklists ~20 syscalls.
											  [https://github.com/flatpak/flatpak/blob/f687f6b2ebfe9bc69f59e42bb96475ca01f08548/common/flatpak-run.c#L2646-L2693](https://github.com/flatpak/flatpak/blob/f687f6b2ebfe9bc69f59e42bb96475ca01f08548/common/flatpak-run.c#L2646-L2693)
										- This means all applications have access to each other's data and can snoop on your personal information.
										- Most programs are written in memory unsafe languages such as C or C++ which has been the cause of the majority of discovered security vulnerabilities and modern exploit mitigations such as Control-Flow Integrity are not widely used.
										  [https://msrc-blog.microsoft.com/2019/07/16/a-proactive-approach-to-more-secure-code/](https://msrc-blog.microsoft.com/2019/07/16/a-proactive-approach-to-more-secure-code/)
										- ((649b140a-578f-4292-a91b-235386358548))
								- Better permission model
								  collapsed:: true
									- Storage
									- Phone
									-
								- Linux mobile OS like PureOS enable AppArmor but most processes still run unconfined so it's mostly useless.
								- They change a few security-relevant settings but these are also mostly useless as they don't even apply the exec-shield patch so that sysctl doesn't exist, disabling kexec is to prevent root from booting a malicious kernel but root can do so many other things to modify the kernel such as loading a kernel module, hiding kernel symbols from /proc ignores the fact that they're clearly visible in System.map and finally, disabling source routing is already a Debian default.
								  [https://source.puri.sm/pureos/packages/pureos-security-hardening](https://source.puri.sm/pureos/packages/pureos-security-hardening)
								- PureOS also uses linux-libre which prevents you from loading any firmware updates
								- Librem 5 prevents you from even flashing new firmware manually which leaves you with insecure firmware with known vulnerabilities.
								  [https://puri.sm/posts/librem5-solving-the-first-fsf-ryf-hurdle/](https://puri.sm/posts/librem5-solving-the-first-fsf-ryf-hurdle/)
								- Sudo/root access is an insecure alternative for a proper API respecting the principle of least privilege.
								  collapsed:: true
									- Daniel Micay (GrapheneOS author):
									  source:: [https://www.reddit.com/r/GrapheneOS/comments/du23la/rooted_or_root/flqgp47/?context=3](https://www.reddit.com/r/GrapheneOS/comments/du23la/rooted_or_root/flqgp47/?context=3)
										- Turning the entire application / user interface layer and beyond into root attack surface obviously massively reduces security. It destroys the security model and a huge amount of the effort that has gone into systemically improving OS security over the years.
										- It also largely defeats the purpose of core security features like verified boot and attestation including the GrapheneOS Auditor app. Not much point in verifying the integrity of the entire OS (kernel and userspace) and preventing downgrade attacks if the OS is just going to trust the persistent state with root access... it wouldn't make much sense to bother with it at all if that was going to be the case.
										- It also makes absolutely no sense for developers to take the lazy and ignorant shortcut of requiring direct root access to implement features. They don't have a clue what they're doing and have no respect for the security of their users. It's completely inappropriate to expose root access rather than a proper API respecting the principle of least privilege. As an example, it's a complete joke to expose root to an application to have it manage the firewall rules rather than exposing an API for managing the firewall rules with sanity checks, and there's already an existing API for doing that so it's not needed anyway. Developers just need to stop being lazy, ignorant and careless with user security.
									- Similarly WebExtension model is far better security than Firefox's old XUL extension model which allowed you to change the browser in any way
									- _Related:_ [Rooting](https://workflowy.com/#/5d249f1fc893)
								- Easy to get sudo/full root access
								  collapsed:: true
									- On ordinary desktops, a compromised non-root user account with access to sudo is almost equal to full root compromise as there are too many ways for an attacker to retrieve the sudo password.
									  [https://www.whonix.org/wiki/Dev/Strong_Linux_User_Account_Isolation](https://www.whonix.org/wiki/Dev/Strong_Linux_User_Account_Isolation)
									- Usually, the standard user is part of group sudo which makes this a massive issue and makes a sudo password almost security theater. For example, the attacker can exploit the plethora of keylogging opportunities such as
									- X's lack of GUI isolation (though Wayland is here to prevent that)
									  [https://theinvisiblethings.blogspot.com/2011/04/linux-security-circus-on-gui-isolation.html](https://theinvisiblethings.blogspot.com/2011/04/linux-security-circus-on-gui-isolation.html)
									- the many infoleaks in /proc
									  [https://www.openwall.com/lists/oss-security/2011/11/05/3](https://www.openwall.com/lists/oss-security/2011/11/05/3)
									- use LD_PRELOAD to hook into every process
									  [https://github.com/Aishou/wayland-keylogger](https://github.com/Aishou/wayland-keylogger)
									- Even if we mitigate every single way to log keystrokes, the attacker can just setup their own fake sudo program to grab the user password.
								- Daniel Micay (GrapheneOS author):
								  source:: [https://www.reddit.com/r/GrapheneOS/comments/du23la/rooted_or_root/flqgp47/?context=3](https://www.reddit.com/r/GrapheneOS/comments/du23la/rooted_or_root/flqgp47/?context=3)
								  collapsed:: true
									- Fedora are building next-generation desktop / server operating systems taking security into account. They're far from being comparable to the security model of an OS like iOS or Android at this point, but they're working on it.
									- You cannot end up with something like Qubes by locking down a Linux distribution. GrapheneOS doesn't (currently) provide what Qubes does. User profiles in GrapheneOS/AOSP are directly comparable to Qubes workspaces in terms of semantics. However, the enforcement of those semantics depends on the Linux kernel.
									- The insecurity of the Linux kernel is not fixed by changing defaults or using MAC frameworks and containers. MAC frameworks and containers depend entirely on the kernel enforcing the security model, and the design of the kernel is inherently insecure. SELinux can be used to reduce kernel attack surface, as can seccomp-bpf, but it cannot reduce the attack surface to a tiny amount without designing the whole application model around that. Even then, everything still sits upon an insecure foundation. The Linux kernel has a bunch of remote attack surface like the network stack too, not just local attack surface.
									- Traditional Linux distributions have far bigger issues than just the kernel and fixing those requires approaching the underlying structure of the OS in a different way.
									-
									- The Linux kernel's combination of insecure architecture, insecure language and tooling, sprawl in scope and code size, poor testing, poor code review and anti-security / anti-correctness culture is what makes it such a security disaster.
									- [https://www.reddit.com/r/GrapheneOS/comments/bj1gpz/syzbot_and_the_tale_of_thousand_kernel_bugs/](https://www.reddit.com/r/GrapheneOS/comments/bj1gpz/syzbot_and_the_tale_of_thousand_kernel_bugs/)
									-
									- The flow of discovered vulnerabilities (hundreds every month) is so fast that triage doesn't even happen for most and only a small portion are even fixed. It's trash.
								- See [Scoped Storage](https://workflowy.com/#/84a8e2bfbc4e)
						- Cons
							- Lower software compatibility
							  collapsed:: true
								- e.g. Flatpak, Snap, AppImage, packages, etc
								- apt/package managers, Flatpak, AppImage
								- Backups - CrashPlan, Duplicacy
								- Containers - Docker
								- Encryption - Veracrypt
							- Lower hardware compatibility
							  Some mobiles, plus servers, laptops, desktops etc
							- More resource-heavy, slow, inflexible and less user-friendly
							- Lower stability and reliability
							  collapsed:: true
								- Linux manages the demands of many programs at once, allowing computers to hum along for years at a time without rebooting.
							- More restrictions
							  collapsed:: true
								- Eg call recording, clipboard managers
								- See Rooting
							- Requiring huge system resources to build it
							  collapsed:: true
								- (>100GB of disk space, 16GB of RAM etc
						- _{Archive}_
							- [https://madaidans-insecurities.github.io/linux-phones.html](https://madaidans-insecurities.github.io/linux-phones.html)
						- _See_ Linux [Pros/Cons](https://workflowy.com/#/123aa8faae43)
						  #PC-Linux
						- 1 Backlink
							- Inherits Android vs Linux pros/cons (see [Compared to Linux](https://workflowy.com/#/fdf8f2b1e572))
							  #Phone-Android
				- Android versions
				  id:: 649b13d1-fd88-4773-a27e-ac5d7acb352d
				  collapsed:: true
					- _Postponed to Android 16+?_
						- Linux Terminal app
						  id:: 67adc977-34d5-4706-8e2d-01ea080d826c
						  collapsed:: true
							- Pros/Cons
								- Pros
									- March 2025 - terminal tabs, GUI support with opt-in GPU hardware acceleration (ANGLE-based VirGL until GPU virtualization support is available), speaker/microphone support
									-
								- Cons
									- No USB-passthrough?
								- Unclear
								- Comparisons
									- ((ed189c8b-89c8-4cc1-a12a-82cd82bfa994))
										- {{embed ((ed189c8b-89c8-4cc1-a12a-82cd82bfa994))}}
							- [Linux Terminal app could be coming to Android, just like ChromeOS - Android Authority](https://www.androidauthority.com/android-linux-terminal-app-3489887/)
							  collapsed:: true
								- [Reddit - Dive into anything](https://www.reddit.com/r/linux/comments/1g1esfs/google_is_preparing_to_let_you_run_linux_apps_on/)
								- [Reddit - Dive into anything](https://www.reddit.com/r/Android/comments/1g1erso/google_is_preparing_to_let_you_run_linux_apps_on/)
								- Like Linux on DeX
									- ((63219e35-31c8-4454-9e84-be51a2684aae))
								- ((649b13ce-0b9e-4741-ba6d-7959858e3443)) can do a lot of this, but can't do some things like Docker
								- Usecases
									- ((63209272-1088-4824-a762-4ac7ded04b0a))
									- ((644c0bb5-76e1-4489-9fa4-22a803fa3c9d))
									-
							- [[2025-01-26 Sunday]] [This is Doom running on Android 16's Linux Terminal - Android Authority](https://www.androidauthority.com/android-16-linux-terminal-doom-3521804/)
						- Improved desktop mode? 
						  id:: 66db752a-27d4-45e8-b3be-3bc884a9d050
						  collapsed:: true
						  Maybe pushed back to A16
							- ((63219e35-31c8-4454-9e84-be51a2684aae))-like Desktop Mode
							  id:: 6521b31d-8ec7-4b86-a6f6-a5663ad9317a
								- I don’t have a lot to show here, but I found a very interesting new Developer Option called “force desktop mode.” Its description reads “force experimental desktop mode on secondary displays.” (2019)
							- I run my S23 Ultra with a pair of XReal One's, and a folding Bluetooth keyboard (DeX or KDE Connect let's you use your phone as a touchpad). It is really amazing in widescreen mode sitting in a coffee shop, reading through technical documents and answering work email. When I'm done, it can all fold up and fit in a (spacious) pair of cargo shorts.
								- Or ((633b7502-b358-45fb-95d2-5fc35ed27d3f))
							- QPR1
								- [Android 16's New Desktop Mode is Awesome! - YouTube](https://www.youtube.com/watch?v=Y4V2xtlHvjw)
								-
							- Parts shipped earlier
								- ((66028eb2-021c-4711-baa0-3ebcc7b05647)) : ((6724d0cd-aee8-4526-8bee-4caa2a60b023))
						- Once desktop mode is out, consider the Xreal One Pro headset or ((633b7502-b358-45fb-95d2-5fc35ed27d3f))
						- Google enforcing mandatory developer verification for app installs including side loading
							- The next step will be Google using their newfound APK signing powers to modify apps obtained from the Play Store and make them impossible to run on operating systems that aren’t Play Certified, to kill off Aurora Store and third-party ROMs. AOSP has no future, sad.
							- Effects
								- All revanced apps - gone
								- All Switch emulators - gone
								- Any modded app - gone
					- [Android 16 / W](https://developer.android.com/about/versions/16/summary) (2025)
					  id:: 67276edf-6bc1-48aa-8f13-58c144b30264
						- Pros/Cons
							- Pros
								- [Features](https://developer.android.com/about/versions/16/features)
									- [Privacy](https://developer.android.com/about/versions/16/features#privacy)
										- [Local Network Permission](https://developer.android.com/about/versions/16/behavior-changes-16#local-network-permission)
							- Cons
								-
							- Unclear
							- Comparisons
					- [Android 15 / V](https://developer.android.com/about/versions/15/summary) (2024)
					  id:: 66028eb2-021c-4711-baa0-3ebcc7b05647
					  collapsed:: true
						- Pros/Cons
							- Pros
								- [Features](https://developer.android.com/about/versions/15/features)
									- [Improved large screen multitasking](https://developer.android.com/about/versions/15/features#large-screen-multitasking)
									  id:: 6724d0cd-aee8-4526-8bee-4caa2a60b023
									  collapsed:: true
										- Split-screen app combinations
										- [Android Developers Blog: Developer Preview: Desktop windowing on Android Tablets](https://android-developers.googleblog.com/2024/09/developer-preview-desktop-windowing-on-android-tablets.html)
											- Note: preview only on Pixel Tablets currently
											- [Android 15 preps better desktop mode with enhanced windowing capabilities](https://www.androidauthority.com/android-15-desktop-mode-demo-3430991/)
												- [Android 15 desktop mode demo - YouTube](https://www.youtube.com/watch?v=QuIiK69BIiM)
									- [Privacy](https://developer.android.com/about/versions/15/features#privacy)
									  collapsed:: true
										- [Private Space](https://developer.android.com/about/versions/15/features#private-space)
										  id:: 670bfaa4-c14d-4575-aad6-5f846468d6da
											- Sounds like ((649b13cc-2a74-4519-8841-bbc386eac1a2))
											- When a user locks the private space, the profile is stopped. While the profile is stopped, apps in the private space are no longer active and can't perform foreground or background activities, including showing notifications.
											- new Private Space feature that creates a separate profile you can hide apps in.
											- In the Android 15 settings, you can find "Private Space," where you can set up a separate PIN code, password, biometric check, and optional Google account for apps you don't want to be available to anybody who happens to have your phone. This could add a layer of protection onto sensitive apps, like banking and shopping apps, or hide other apps for whatever reason.
											  In your list of apps, drag any app down to the lock space that now appears in the bottom right. It will only be shown as a lock until you unlock it; you will then see the apps available in your new Private Space. After that, you should probably delete it from the main app list. Dave Taylor has a rundown of the process and its quirks.
											  It's obviously more involved than Apple's "Hide and Require Face ID" tap option but with potentially more robust hiding of the app.
											- Related: ((649b13ce-b4f8-45e9-857a-28eb2ad4ffd2))
										- Cellular security
										  collapsed:: true
											- The first toggle, “Security notifications,” is the less strict of the two. Once enabled, Android will let you know whenever you connect to a cellular network that either isn’t encrypted or records your IMEI and IMSI numbers. One common situation in which this would occur is if a law enforcement agency is using a Stingray device to track nearby cell network usage. The ACLU has some [helpful resources 2](https://www.aclu.org/issues/privacy-technology/surveillance-technologies/stingray-tracking-devices-whos-got-them) explaining how and where Stingrays are used in the US.
											- Going a step further, you can also choose to “Require encryption,” protecting against potential surveillance. The option warns that you may be unable to connect properly in certain areas, but your phone usage should remain secure. Any calls placed to emergency services will ignore this setting, however, to ensure the call can be completed.
							- Cons
								- [Minimum installable target API level](https://developer.android.com/about/versions/15/behavior-changes-all#minimum-target-api-level) - It'll block installing apps 10 years old ( ((644c0acf-f144-4757-9ed8-53a987886c62)) i.e. lower than API 24) unless you use adb
									- `adb install --bypass-low-target-sdk-block <apk path>`
									- For non rooted phones. Install Shizuku and an app called Install With Options and use it to bypass that check.
							- Unclear
							- Comparisons
					- [Android 14 / U](https://developer.android.com/about/versions/14/summary) (2023)
					  id:: 64fed706-d987-4c12-a888-29dcdd6e26b8
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Features
									- [Improvements for app stores](https://developer.android.com/about/versions/14/features#app-stores)
								- Privacy
								  id:: 6d86af70-8bf3-496f-a5f9-08081a20dc28
									- [Google Online Security Blog: Android 14 introduces first-of-its-kind cellular connectivity security features](https://security.googleblog.com/2023/08/android-14-introduces-first-of-its-kind.html)
									- Proactive info about apps' data permissions
									- [Passkey support](https://developer.android.com/about/versions/14/features#credential-manager)
									  id:: 651de7c6-cad5-45fe-902d-b7334b088ac6
									- [Toast notifications when screenshots are taken](https://developer.android.com/about/versions/14/features/screenshot-detection)
									- [Grant partial access to photos and videos](https://developer.android.com/about/versions/14/changes/partial-photo-video-access)
									  Selected Photos Access, which allows users to grant apps access to specific images and videos in their library, rather than granting access to all media of a given type.
							- Cons
								- [Apps can kill only their own background processes](https://developer.android.com/about/versions/14/behavior-changes-all#kill-own-background-processes) - stops apps like SuperFreezZ?
							- Unclear
								- [Minimum installable target API level](https://developer.android.com/about/versions/14/behavior-changes-all#minimum-target-api-level) ([23](https://apilevels.com/) AKA ((644c0acf-f144-4757-9ed8-53a987886c62)) ) - only app it stops usage of is ((644c0acd-0d02-4c23-8f82-dc7c50d3c9b2))
								- [User consent required for each MediaProjection capture session](https://developer.android.com/about/versions/14/behavior-changes-14#media-projection-consent) - how does this affect ((63a9ade4-0cdf-4680-a839-6b6f92e57f51))
								-
							- Comparisons
					- [Android 13 / T](https://developer.android.com/about/versions/13/summary) (2022)
					  id:: 649b13d1-4753-4edb-b1df-397c5c89ad35
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Features
									- [Users can now stop some foreground services via the Quick Settings menu](https://developer.android.com/guide/components/foreground-services#handle-user-initiated-stop)
									- [Better tablet and large screen support](https://developer.android.com/about/versions/13/features/large-screens) - two column Quick Settings, taskbar (like Windows 11/MacOS), drag-and-drop split-screen,
								- Privacy
								  id:: 64fed773-470b-44f5-a826-c1c657fe5618
									- [Opt-in runtime permission to allow notifications](https://developer.android.com/about/versions/13/changes/notification-permission)
									- [New runtime permission for nearby Wi-Fi devices](https://developer.android.com/about/versions/13/behavior-changes-13#nearby-wifi-devices-permission)
									- [Use of body sensors in the background requires new permission](https://developer.android.com/about/versions/13/behavior-changes-13#body-sensors-background-permission)
									- [Granular media permissions](https://developer.android.com/about/versions/13/behavior-changes-13#granular-media-permissions)
									  Apps must now use separate permissions to request access to different types of media, instead of the `READ_EXTERNAL_STORAGE` permission e.g. images, videos, audio files
									- [Photo picker](https://developer.android.com/training/data-storage/shared/photopicker) allows giving an app access to only selected photos/videos, instead of a whole library
							- ## Cons
							- Unclear
							- Comparisons
					- Android 12 / S (2021)
					  id:: 649b13d1-806c-4635-a439-e008c6a27fa0
					  collapsed:: true
						- ((649b13d3-139c-445c-bb2b-54cf06c55ca8))
						- Pros
							- _Features_
								- One-Handed Mode
								  collapsed:: true
									- [https://9to5google.com/2021/02/19/android-12-dp1-heres-a-look-at-one-handed-mode-in-action-video/](https://9to5google.com/2021/02/19/android-12-dp1-heres-a-look-at-one-handed-mode-in-action-video/)
								- 12L update - includes remembering which apps you've split-screened; and much better large screen tablet/foldable support
								  collapsed:: true
									- Video overview
									  [https://www.youtube.com/watch?v=Hjg9m2z1y9M](https://www.youtube.com/watch?v=Hjg9m2z1y9M)
									- [https://blog.google/products/android/12l-larger-screens/](https://blog.google/products/android/12l-larger-screens/)
								- Transfer ((663b24fb-f1f2-4dbe-ae47-d3a910654835)) messages from iOS to Android
								  [https://blog.google/products/android/whatsapp-chat-history/](https://blog.google/products/android/whatsapp-chat-history/)
								- Removal of iptables, replaced by eBPF/bpfilter (since it's a new Linux kernel feature)
								  collapsed:: true
									- [https://prog.world/why-is-the-kernel-community-replacing-iptables-with-bpf/](https://prog.world/why-is-the-kernel-community-replacing-iptables-with-bpf/)
									- This is a newer, much more efficient kernel side implementation.
							- _Privacy_
							  id:: 649b13d1-f871-4042-aba4-d644fe765610
								- [Privacy Dashboard](https://developer.android.com/about/versions/12/features#privacy-dashboard) - show usage of each permission over the day
								  collapsed:: true
									- [Timeline](https://android-developers.googleblog.com/2021/05/android-security-and-privacy-recap.html)
								- [Microphone and camera indicators](https://developer.android.com/about/versions/12/behavior-changes-all#mic-camera-indicators)
								  id:: 649b13d1-a358-4221-b66e-37cdb5da82ea
								  collapsed:: true
								  Notification whenever an app is checking Location, Microphone or Camera. This should be make Bouncer defunct
									- [https://www.androidpolice.com/2021/03/22/android-12-isnt-simply-copying-ios-14s-privacy-indicators-its-improving-them/](https://www.androidpolice.com/2021/03/22/android-12-isnt-simply-copying-ios-14s-privacy-indicators-its-improving-them/)
									- [https://nitter.cc/kdrag0n/status/1372984116778442755?ref_src=twsrc%5Etfw](https://nitter.cc/kdrag0n/status/1372984116778442755?ref_src=twsrc%5Etfw)
									- In the meantime
										- F-Droid apps
											- Microphone and camera only
												- Privacy Indicators
												- Vigilante
								- [Bluetooth (Nearby Devices) permissions separated from Location permission](https://developer.android.com/guide/topics/connectivity/bluetooth/permissions)
								- [Automatic app updates for 3rd party app stores](https://developer.android.com/about/versions/12/features#automatic-app-updates)
									- [Android 12 will let alternative app stores do automatic updates](https://www.xda-developers.com/android-12-alternative-app-stores-update-apps-background/)
									  collapsed:: true
										- [Droid-ify](https://github.com/Iamlooker/Droid-ify)
										  collapsed:: true
											- Have updated these apps manually through Droid-ify on Tue, Apr 26, 2022, will see if they auto-update in future
											  collapsed:: true
												- Briar
												- Catima
												- Cryptomator
												- Element
												- FFUpdater
												- FairEmail
												- FlorisBoard
												- Fox's Magisk Module Manager
												- GMaps WV
												- Hypatia
												- K-9 Mail
												- KeePassDX
												- Linphone
												- Logseq
												- ((649b13ce-c4a3-4f27-87fb-25442ce2a9a0))
												- Nekome
												- Nitter
												- OCR (Tesseract)
												- Open TimeLimit
												- Setter
												- [Shattered Pixel Dungeon](https://store.steampowered.com/app/1769170/Shattered_Pixel_Dungeon/)
												  id:: 644c0acf-c1c4-4549-be63-feb430011d8b
													- [Google Play Store app](https://play.google.com/store/apps/details?id=com.shatteredpixel.shatteredpixeldungeon&hl=en_GB)
												- ((63209285-2e05-40f2-bce9-5b8d813eea86))
												- Simple Dialler
												- Simple Gallery Pro
												- Status
												- Tailscale
												- ((63209285-a267-4f3c-b28b-c8116948c1d1))
												- UnCiv
												- Zulip
											- If the above apps don't auto-update, then they may need the first install via Droid-ify
											  collapsed:: true
												- Hypatia
												- FFUpdater
												- PCAPDroid
												- Florisboard
												- Florisboard Beta
											- Neo Store (AKA the new version)
										- Requesting apps use this method
										  collapsed:: true
											- _Requested_
											  collapsed:: true
												- ((63209285-a267-4f3c-b28b-c8116948c1d1))
												- ((651408a1-d5e3-413b-85f3-2f4829175e3b))
												  issue got closed. It can self-update, but not background and automatically [[2023-10-09 Monday]]
												- ((65166ca4-1398-465a-8ff7-029210238874))
												- FFUpdater
												- Signal
												  [https://community.signalusers.org/t/use-the-new-permission-for-automatic-background-app-updates/37828/1](https://community.signalusers.org/t/use-the-new-permission-for-automatic-background-app-updates/37828/1)
											- F-Droid (Droid-ify app includes this support already)
											  collapsed:: true
												- [https://github.com/Iamlooker/Droid-ify](https://github.com/Iamlooker/Droid-ify)
											- Aurora (this is getting few updates so far in 2021, maybe just focus on GrapheneOS sandboxed Play Store)
								- [Approximate vs Precise Location](https://developer.android.com/training/location/permissions#accuracy)
								  collapsed:: true
									- [source] [https://developer.android.com/about/versions/12/approximate-location](https://developer.android.com/about/versions/12/approximate-location)
										- On Android 12, users can navigate to system settings to set the preferred location accuracy for any app, regardless of that app's target SDK version. This is true even when your app is installed on a device running Android 11 or lower, and then upgrades to Android 12. If the user downgrades your app's location access from precise to approximate, either from the permission dialog or in system settings, the system restarts your app's process.
										- Can be set per-app for apps which target Android 12+
										- If your app needs to pair a device with nearby devices over Bluetooth or Wi-Fi, consider using [companion device](https://developer.android.com/guide/topics/connectivity/companion-device-pairing) <a href="https://developer.android.com/guide/topics/connectivity/companion-device-pairing">pairing</a> or the new <a href="https://developer.android.com/about/versions/12/bluetooth-permissions">Bluetooth permissions</a>, instead of requesting the ACCESS_FINE_LOCATION permission.
									-
									- The speaker, Erik W. mentions that the new Precise and Approximate are simply user-facing terms for ACCESS_FINE_LOCATION and ACCESS_COARSE_LOCATION respectively.
										- As I understand, FINE location is for acquiring location based on GPS signal. COARSE is by using CELL TOWER and WiFi assocations. If this new Approximate location is simply a forced coarse location, Wifi signals are still too accurate. I requested FUZZING a location. If I have a weather widget that just needs to know the city I'm in- the app and the 30 3rd party SDK's don't need to know my location within 30 yards. Coarse location would still lock me in based on the 15 wifi networks and 20 bluetooth devices around me in my apartment. That's still way too accurate.
										- The request is "If I'm here. Say I'm somewhere random within 30 miles." A fuzzed location.
									- Bluetooth is not accessible using ACCESS_COARSE_LOCATION
									- If you're using the Fused Location Provider (which almost everyone does) the location is randomized to city level accuracy (2000m or so).
										- Its possible to improve the city-level cell tower location by augmenting it with wifi data manually, but the app is going to have to build and update that database itself. As far as I know, the Fused Location Provider is the only API capable of doing this on Android.
								- [Clipboard access notifications](https://developer.android.com/about/versions/12/behavior-changes-all#clipboard-access-notifications)
								- Nearby device permissions
								  collapsed:: true
									- Android 12 minimizes data access by adding a new runtime permission for nearby experiences that do not use location. Up until now, apps such as watch and headphone companion apps required the location permission to scan for nearby Bluetooth devices for pairing. We heard from users and developers that this was confusing and led to granting the permission to access location data when it wasn’t needed. For apps targeting Android 12, you’ll have the option to decouple nearby device discovery from the fine location permission for use cases like pairing devices by using the new BLUETOOTH_SCAN permission and by declaring usesPermissionFlags=neverForLocation . Once the device is paired, apps can use the new BLUETOOTH_CONNECT permission to interact with it. Apps that use Bluetooth scanning for location must still have the location permission. Nearby device permissions will be available to try in Beta 1.
								- [App hibernation for unused apps](https://developer.android.com/about/versions/12/behavior-changes-12#app-hibernation)
								  collapsed:: true
									- App hibernation - hibernate apps which you don't use for a while
								- New toggles
									- Microphone and camera toggles
									  collapsed:: true
										- You may have seen people placing stickers on cameras or plugging audio blockers into their phones. In Android 12, we’re introducing two new controls that allow users to quickly and easily cut off apps’ access to the microphone and camera on the device.
										- To ensure user safety, emergency calls will be exempted.
									- Extra Dim
									  collapsed:: true
										- Replaces [Lower](https://workflowy.com/#/24ab5485b5b8)<a href="https://workflowy.com/#/24ab5485b5b8"> </a><a href="https://workflowy.com/#/24ab5485b5b8">Brightness</a><a href="https://workflowy.com/#/24ab5485b5b8"> Screen Filter Pro</a>
									- See [Redesigned volume panel in LineageOS 19](https://workflowy.com/#/570bb6a9db5b)
								- [One-time permissions](https://en.wikipedia.org/wiki/Android_version_history#cite_note-unwrappingandroid11-270)
								- Can disable 2G?
								  collapsed:: true
									- Settings > Network & Internet > SIMs > Allow 2G and turning that setting off.
									- Note: this is not on Lineage 19. Possibly incorrect about this being an Android feature
								- _{Archive}_
									- [https://android-developers.googleblog.com/2021/05/android-security-and-privacy-recap.html](https://android-developers.googleblog.com/2021/05/android-security-and-privacy-recap.html)
							- Generic Kernel Image (GKI) required to be used for all devices which launch with Android 12
							  collapsed:: true
								- Pros
									- Basically means that Linux can much more easily be run on these devices, since all that's needed is to check the kernel modules are properly working with Linux and that to add in the Android patches for Linux
								- GKIs are a version of Google's Android Common Kernel (which is forked from Linux) that will be required to be able to run on any OEM device
								- Generic Kernel Images (GKIs) will mean that OEMs have to provide their own firmware as kernel modules, which means newer kernels can be used without
								  source:: [https://lwn.net/Articles/771974/](https://lwn.net/Articles/771974/)
								- 2021: Android 12 requires shipping with the GKI
								  [https://lwn.net/Articles/830979/](https://lwn.net/Articles/830979/)
								- See [(2022 / Android 12) Project ? - new phones require the ability to run a Generic Kernel Image (GKI), which makes it easier for OEMs and custom ROMs to support many phones for years](https://workflowy.com/#/1fbe19f22919)
								- 4 Backlinks
									- Pros - Supports GrapheneOS/CalyxOS with relockable bootloader, 5 years of kernel and OS updates guaranteed, launches with Android 12 (and thus [GKIs](https://workflowy.com/#/1bfe537b404f) for mobile Linux in future)
									- Launches with Android 12, and thus uses a [Generic Kernel Image (GKI)](https://workflowy.com/#/1bfe537b404f)
									- Android 11 base - [Android 12](https://workflowy.com/#/b811bc7ac61a) means that the device runs with a <a href="https://workflowy.com/#/1bfe537b404f">Generic Kernel Image (GKI)</a>, which I'm not sure if FP4 does. Android 12-based phones should be able to run mobile Linux quite easily
									- See [Generic Kernel Image (GKI)](https://workflowy.com/#/1bfe537b404f)
							- More Mainline components
								- [Android Runtime (ART)](https://www.xda-developers.com/google-android-runtime-art-mainline-module-android-12/)
							- [Microphone and camera toggles](https://developer.android.com/about/versions/12/behavior-changes-all#mic-camera-toggles) in Quick Settings
							- [Microphone and camera indicators](https://developer.android.com/about/versions/12/behavior-changes-all#mic-camera-indicators)
							- [Approximate location](https://developer.android.com/about/versions/12/behavior-changes-all#approximate-location)
							- Supports [GrapheneOS' App Store](https://github.com/GrapheneOS/Apps/releases)
								- It requires Android 12+
								- Allows downloading their camera, PDF viewer apps and auto-updating them
						- Cons
							- Material You redesign
								- Cons
									- Quick action tiles are massive
							- Many people say it's buggy
							  [https://redd.it/s1x7kf](https://redd.it/s1x7kf)
							- [How to bring back separate wi-fi toggle from internet](https://www.xda-developers.com/bring-back-wifi-mobile-data-quick-settings-tiles-android-12-adb/)
							- Opens non-verified links in default browser
							  [https://www.reddit.com/r/Android/comments/qrqwya/android_12_will_always_open_nonverified_links_in/](https://www.reddit.com/r/Android/comments/qrqwya/android_12_will_always_open_nonverified_links_in/)
					- Android 11 / R (2020)
					  id:: 649b13d1-6e1b-4314-bb5c-632667e0e799
					  collapsed:: true
						- Pros
							- _Features_
								- Native screen recording
								- Notification history feed
								- Chat bubbles
								- Screenshot markup editor
								- ((644c0ad0-efaf-4094-9c04-85e5811be3a3)) (Project Mainline/security)
							- Privacy
							  id:: 649b13d1-472b-4c84-bcf5-931794d076ae
								- Scoped Storage
								  id:: 63219e37-0f66-4883-878d-3f5f173af6b7
								  collapsed:: true
									- Pros/Cons
									  collapsed:: true
										- Pros
											- My post: By November 2021 WhatsApp will finally stop requiring the Storage (Files & Media) permission in order to be functional
											  source:: [https://old.reddit.com/r/privacy/comments/mphifm/by_november_whatsapp_will_finally_stop_requiring/?](https://old.reddit.com/r/privacy/comments/mphifm/by_november_whatsapp_will_finally_stop_requiring/?)
											  collapsed:: true
												- [In November](https://developer.android.com/distribute/best-practices/develop/target-sdk) any Google Play store apps which update will be required to target Android 11 (API level 30). <a href="https://developer.android.com/about/versions/11/privacy/storage#permissions-target-11">In this API level</a> apps with the Files & Media (Storage) permission cannot write to shared storage, which is where WhatsApp currently stores all media, databases and backups.
												- This means that WhatsApp will have to use [Scoped Storage](https://developer.android.com/about/versions/11/privacy/storage#scoped-storage)
												- like every other app, which is a private folder where they can store
												- those three types of files. Using SS means it doesn't require access to [](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play)
												- the rest of your phone storage in order to view pictures sent to you, [](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play)
												- make backups and other basic functionality.[](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play)
												- The only way any app can write to shared storage is if they request a restricted ["all files access"](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play)
												- permission, and apps which request this permission are manually
												- reviewed by Google Play store staff in order to limit to legitimate
												- usecases like file managers and file encryption apps. They're unlikely
												- to be allowed this permission since Scoped Storage seems like it was
												- perfectly designed to counter WhatsApp's privacy breaching.
												- TL;DR: You no longer have to give WhatsApp the Files & Media (Storage) in November.
											- Apps which target Android 11 (API level 30)
											- For users with Android 11 the Files & Media (Shared Storage) permission only allows read-access, but not write-access
											- Starting in Android 11, apps cannot create their own app-specific directory on external/shared storage. To access the directory that the system provides for your app, call getExternalFilesDirs().
											  source:: [https://developer.android.com/about/versions/11/privacy/storage#app-specific-external](https://developer.android.com/about/versions/11/privacy/storage#app-specific-external)
											- From May if an app targets Android 11 (API level 30) and wants write-access to shared storage then it'll be evaluated by the Google Play store before being allowed
											  source:: [https://developer.android.com/training/data-storage/manage-all-files](https://developer.android.com/training/data-storage/manage-all-files)
											- November 2021 is when updating apps
										- Cons
											- Existing popular apps (eg WhatsApp) will request read+write access to media storage e.g. /Photos
											  collapsed:: true
												- However ((649b13ce-c4a3-4f27-87fb-25442ce2a9a0))
											- Apps can still request to read all of Shared Storage despite having no real need i.e. WhatsApp will likely
											- Some apps won't have migrated their data from shared storage to app-specific data directory before Android 11 is enforced
											  collapsed:: true
												- Migrate data to directories that are visible when using scoped storage
													- If your app uses the legacy storage model and previously targeted Android 10 or lower, you might be storing data in a directory that your app cannot access when the scoped storage model is enabled. Before you target Android 11, migrate data to a directory that's compatible with scoped storage.
											- App-specific data directories inaccessible by apps which target Android 11 (API level 30), though these are already mainly only targeted by rooted backup apps anyway
											  source:: [https://developer.android.com/training/data-storage/app-specific](https://developer.android.com/training/data-storage/app-specific)
											  collapsed:: true
												- These files are not accessible via a file manager already. They require being accessed by eg File API, MediaStore API etc
												- _Typical location_
													- The Android/data/ directory and all subdirectories.
													- The Android/obb/ directory and all subdirectories.
											-
											-
									- Now all apps have read+write access to two private folders which only they can access
									  collapsed:: true
										- One for their own required files (this folder in /sdcard/Android/ has been around for years)
										- Another (new) one for files that the app creates eg audio recordings, backups etc
									- Two levels of permission now
									  collapsed:: true
										- Access to media only - ie shared storage location
										  [https://developer.android.com/training/data-storage/shared](https://developer.android.com/training/data-storage/shared)
											- Your app can contribute to well-defined media collections, including the [MediaStore.Downloads](https://developer.android.com/reference/android/provider/MediaStore.Downloads) collection, witout requesting any storage-related permissions. If you're developing a camera app, for example, you don't need to request storage-related permissions because <a href="https://developer.android.com/training/data-storage/shared/media#app-attribution">your app owns the images</a> that you're writing to the media store.
											  source:: [https://developer.android.com/training/data-storage/shared/media#storage-permission](https://developer.android.com/training/data-storage/shared/media#storage-permission)
										- Allowed to manage all files
									- Summary
									  [https://www.androidcentral.com/what-scoped-storage](https://www.androidcentral.com/what-scoped-storage)
									- Forced Scoped Storage
									  collapsed:: true
										- ((63219e34-77c4-47fe-985b-29a582113b0e))
										- [GrapheneOS Storage Scopes](https://grapheneos.org/features#storage-scopes)
										  id:: 63219e37-6ffb-43fd-af6b-0529f25f47a7
								- Permissions restrict to max "only whilst app is in use" includes Location, Microphone and Camera
								  id:: 644c0ad0-3ccd-4534-a4a5-aafaaa2b5bdb
								  collapsed:: true
									- Only Location in Android 11
									- Otherwise have to use an app notification
								- [Developer option to have a randomised MAC address each time you connect to a network](https://www.techrepublic.com/article/how-to-enable-enhanced-randomize-mac-addresses-on-android/)
								  collapsed:: true
									- Can be disabled per network
									- Android settings > Developer options > Networking: > Enable Wi-Fi-enhanced MAC randomisation
									- On GrapheneOS this option is available via normal Network area of settings, not Developer Options
								- ((649b13d2-53ec-4093-a4f1-d887c902825d))
								- [Most apps can't query to find out what other apps you have installed](https://9to5google.com/2021/03/31/installed-android-apps-limit/)
									- Banking apps can
									- Applications that can continue to use the permission include device search, antivirus, file managers, and browsers.
									- [Package visibility filtering on Android  |  Android Developers](https://developer.android.com/training/package-visibility)
									-
						- {Archive}
							- [https://en.wikipedia.org/wiki/Android*version_history#Android_11*(API_30)](<https://en.wikipedia.org/wiki/Android_version_history#Android_11_(API_30)>)
							- [https://developer.android.com/about/versions/12/summary](https://developer.android.com/about/versions/12/summary)
					- Android 10 / Q (2019)
					  id:: 649b13d1-cbcd-4003-bb52-a7292cfc356f
					  collapsed:: true
						- Pros
							- _Privacy_
							  id:: 649b13d1-4577-4eae-9806-24f964f2099b
								- Enhanced permissions management
								  collapsed:: true
									- See what apps have what permissions
									- Enable location only whilst app is in use
								- Project Mainline - doing security updates via Google Play, which were before handed by OEMs
								  collapsed:: true
									- This means even if you have a 5-year old phone, you could still get security updates. Unlike before, where OEMs would only give you security updates for a year or two
									- APEX - making system libraries be updatable separately from Android platform updates (like a package manager)
										- https://www.xda-developers.com/android-q-apex-biggest-thing-since-project-treble/
										- What’s the purpose?
											- At this point, all I can do is speculate. My best guess is that Google is trying to create a core set of APEX packages that can be updated by Google to possibly create a unified base core of Android shared between vendors, making “system” only updates possible, but using single package updates.
								- Auto revoke app permissions if you haven't used the apps in a while
								  id:: 649b13d3-5f1d-43a7-87c2-a84239c99eeb
								  collapsed:: true
									- [[268]](https://en.wikipedia.org/wiki/Android_version_history#cite_note-unwrappingandroid11-270)
								- Clipboard access prevented for background apps
								  id:: 649b13d3-0ea2-4545-8a35-4747f6476bff
								  collapsed:: true
									- only the configured default input method editor (your keyboard of choice) and the currently focused app can access the clipboard. Apps without focus cannot access the clipboard. This is a stricter restriction than preventing apps in the background from accessing it, since an app in the foreground or a foreground service cannot access it, only the foreground app that's currently focused. Clipboard managers need to be implemented by the keyboard chosen as the default by the user.
									- Note: FlorisBoard uses an optional private clipboard. Also in later Android version there's a notification for clipboard access
								- [Apps can't access unique hardware identifiers directly](https://developer.android.com/about/versions/10/privacy/changes#non-resettable-device-ids)
								  collapsed:: true
									- As of Android 10, apps cannot obtain permission to access non-resettable hardware identifiers such as the serial number, MAC addresses, IMEIs/MEIDs, SIM card serial numbers and subscriber IDs. Only privileged apps included in the base system with READ_PRIVILEGED_PHONE_STATE whitelisted can access these hardware identifiers. Apps targeting Android 10 will receive a SecurityException and older apps will receive an empty value for compatibility.
										- Apps can determine the model of the device (such as it being a Pixel 4) either directly or indirectly through the properties of the hardware and software. There isn't a way to avoid this short of the OS supporting running apps in a virtual machine with limited functionality and hardware acceleration. Hiding the CPU/SoC model would require not even using basic hardware virtualization support and these things could probably still be detected via performance measurements.
									- Related: Android 11: [Developer option to have a randomised MAC address each time you connect to a network](https://workflowy.com/#/3c545e3cd340)
									- 1 Backlink
										- MAC (see [Apps can't access unique hardware identifiers directly](https://workflowy.com/#/f6d2f1127964))
							- System-wide dark mode including force override for apps
							- Gesture Navigation
								- option to use gestures to navigate rather than 3-button navigation. Also swipe from bottom corners to use Assistant (e.g. Screenshot Assistant)
								  Unavailable on 3rd party launchers until a later update (December?)
							- Digital Wellbeing/Family suite apps enhanced, including Focus Mode
							- _Minor improvements_
								- Faster sharing menu
								- Smart Replies available for all apps
								- Live Caption (subtitles for any live video)
								  collapsed:: true
									- The feature will live-caption any video that's being played, without a data connection. To activate Live Caption, play a video and then press a volume button. The volume slider that shows up will have a caption button at the bottom -- tap it. You can then move around the caption by dragging it around the screen.
									- Currently only for Pixel 4, on others by the end of the year
								- Wi-Fi sharing via QR codes
								- 'bubbles' multitasking - circles on-screen for quick access to different conversations like Facebook's Chat Heads
					- Android 9 / P / Pie (2018)
					  collapsed:: true
						- Pros
							- Blocks 3rd party app background camera/microphone/sensor use. Must be a foreground serviceAndroid 9 will block background apps from using microphone, camera or sensors. A foreground service can be used instead (which requires a notification)
							- Gotten rid of annoying notification that [app name] is using battery. Still accessible in Settings
						- Cons
							- Xposed Framework not yet available for it ([Not yet available for Android 9/P even](https://workflowy.com/#/454437d08808))
							  collapsed:: true
								- 1 Backlink
									- Not yet available for Android 9/P even
									  [Xposed Framework not yet available for it (Not yet available for Android 9/P even)](https://workflowy.com/#/49e06110eafe)
							- Clock moved to left side
							- Recent Apps/App Switcher menu now is instead horizontal. Need root + current launcher to add feature
							  collapsed:: true
							  https://www.xda-developers.com/android-pie-recent-apps-customization/
								- Pill (home button) can be hold-and-slide to change apps
								  https://www.androidcentral.com/sites/androidcentral.com/files/styles/xlarge/public/article_images/2018/08/android-p-cycle-through-recents.gif?itok=VCZO1Vz6
							- Quick setting tiles no longer expandable
							  https://www.androidpolice.com/2018/03/07/android-p-feature-spotlight-quick-setting-toggles-no-longer-expandable/
							- Disables non-root + non-system apps from call recording
							  collapsed:: true
								- [https://www.xda-developers.com/android-pie-blocks-non-root-call-recording-apps/](https://www.xda-developers.com/android-pie-blocks-non-root-call-recording-apps/)
								- Issue
								  https://issuetracker.google.com/issues/112602629#comment54
								- How to enable call recording
									- System apps
										- Samsung, OnePlus has it natively
										- LineageOS dialler
										  https://www.xda-developers.com/lineageos-changelog-20/
									- [Axet's call recorder](https://f-droid.org/en/packages/com.github.axet.callrecorder/) (F-Droid)
										- There's a Magisk package (root) which enables full access?
											- Otherwise it only records one side of the conversation?
										- Or can you just install it as a system app for it to work?
										- https://gitlab.com/axet/android-call-recorder
									- Rooted
										- Xposed modules
										  e.g. http://repo.xposed.info/module/com.pyler.enablecmcallrec
										- Boldbeast Recorder
											- Boldbeast recorder from the Google Play Store. Go to settings > call settings > fix recording issues > enable root options.
											- Then use the following settings and you're good to go!
											- Record Mode: Alsa
											- File Sampling Rate: Auto
											- Tune Audio Effect: No
											- Change Audio Controls: Yes
											- Change Audio Driver: No
											- Start Input Stream: Yes
											- Alsa Device: Auto
											- Alsa Bits: 16 Bits
											- Alsa Channels: Auto
											- Alsa Sampling Rate: 8000
										- Total Recall?
										  https://play.google.com/store/apps/details?id=com.killermobile.totalrecall
										- skvalex call recording
										- Call Recorder-ACR?
										- [Magisk](https://workflowy.com/#/baba54354fcf) module which activates the native call recording
									- VoIP apps
									- 1 Backlink
										- See [How to enable call recording](https://workflowy.com/#/6581cf768a8a)
								- See [Call](https://workflowy.com/#/3b40b1b5144b)<a href="https://workflowy.com/#/3b40b1b5144b"> </a><a href="https://workflowy.com/#/3b40b1b5144b">record</a><a href="https://workflowy.com/#/3b40b1b5144b">ing</a>
								- 1 Backlink
									- See [Android 9 / P / Pie (2018)](https://workflowy.com/#/f2eee6b946da) - <a href="https://workflowy.com/#/d8ec4951b4c3">Disables non-root + non-system apps from call recording</a>
							- Split screen initialization animation is bad
					- Android 8 / O / Oreo (2017)
					  collapsed:: true
						- Notification channels
							- a way for apps to split their notifications into various themes that you can choose to let through or block individually.
							- “For example, you might setup separate notification channels for each conversation group created by a user in a messaging app,”
						- Picture in picture
							- Like MinVid for YouTube
						- unread notification app badges
					- Android 7 / N / Nougat (2016)
					  collapsed:: true
						- Pros
							- File-Based Encryption and Direct Boot
							  intralink2:: https://workflowy.com/#/04d8fa38b775
							- Split Screen Mode
							- Quick reply via notification
						- Cons
							- No Xposed currently
							- TWRP doesn't work currently
					- Android 6 / M / Marshmallow (2015)
					  id:: 644c0acf-f144-4757-9ed8-53a987886c62
					- Android 5 / L / Lollipop (2014)
				- _Documentation_
					- Installing
					  collapsed:: true
						- Generic System Image (GSI)
						  [https://developer.android.com/topic/generic-system-image/releases](https://developer.android.com/topic/generic-system-image/releases)
							- New GSI build that supports all Treble devices, instead of just the latest Treble devices
							  [https://www.xda-developers.com/developer-boots-android-11-22-older-devices-project-treble-gsi/](https://www.xda-developers.com/developer-boots-android-11-22-older-devices-project-treble-gsi/)
							- Treble-enabled Generic System Images
								- Support thread
								  https://forum.xda-developers.com/project-treble/trebleenabled-device-development/aosp-9-0-phh-treble-t3831915
								- Download
								  https://github.com/phhusson/treble_experimentations/releases/tag/v119
							- _See _[Project Treble - Generic System Image (GSI)](https://workflowy.com/#/72a1dee3eda0)
						- _Device-specific_
							- Pixel and Nexus factory images
							  [https://developers.google.com/android/images](https://developers.google.com/android/images)
							- See other device manufacturers websites
					- Setup
						- Android Settings: System > Gestures > Brightness control
							- Enabled - slide across status bar to adjust brightness
					- Task manager (processes)
						- Developer Options > Running Services
					- Features
						- Mobile Device Management (MDM)
						  id:: 66051aab-a6ac-4db3-92db-63e21eb0838c
						  collapsed:: true
							- Pros/Cons
								- Pros
									- [Can be used to prevent hostile law enforcement or partners from installing surveillance apps](https://support.google.com/a/answer/9997133?hl=en) e.g. [China](https://www.rfa.org/english/news/china/phones-police-checks-03262024133232.html)
									  Supported editions for this feature: Frontline Starter and Frontline Standard; Business Plus; Enterprise Standard and Enterprise Plus; Education Standard, Education Plus, and Endpoint Education Upgrade; Enterprise Essentials and Enterprise Essentials Plus; G Suite Basic and G Suite Business; Cloud Identity Premium.
								- Cons
									- [Incompatible with](https://discuss.grapheneos.org/d/4411-does-gos-play-well-with-mdm-for-corporateenterprise-environments) ((63209286-6f40-4063-9fdc-2543251d416e))
									  collapsed:: true
										- I answered this in [https://github.com/GrapheneOS/os-issue-tracker/issues/1938#issuecomment-1416839482](https://github.com/GrapheneOS/os-issue-tracker/issues/1938#issuecomment-1416839482) as my company also uses MDM using VMware Airwatch
											- This is an issue I've personally encountered with my company that uses VMware One Intelligent Hub (Airwatch).
											- Work profiles that depend on Google Play will normally have GSF, GMS, and Play Store automatically installed upon the creation of the work profile like it does on stock OS. Work profiles can't access Google Play from the user profile it's in. Since Google Play apps are not considered components that get automatically installed in the work profile, apps like Intune and Intelligent Hub don't handle a situation where those components are unavailable.
											- I've _partially_ solved this issue with [GrapheneOS/platform_frameworks_base@e585676](https://github.com/GrapheneOS/platform_frameworks_base/commit/e5856762e6492fc015859de10b80bf26f9e60239) which allows GrapheneOS Apps app to be added to all work profile creations by default, so you can install sandboxed Google Play once the work profile gets created then finish the (unfortunately, likely broken and half baked) installation of your work profile.
											- This still doesn't work 100% because the MDM app will likely place restrictions on what apps you can install. Play Store on stock OS is considered a trusted first party source, but on GrapheneOS only the Apps app is a trusted first party source. Play Store on GrapheneOS is a third party source, so even if your work profile gets created and you can install sandboxed Google Play, the MDM app nor you will be able to install your company apps like Duo (MFA), Okta, Microsoft Teams and Outlook, GlobalProtect, VMware Tunnel, etc.
											- MDM stuff on GrapheneOS is a really complex situation to tackle when we don't want to create special case bypasses for sandboxed Google Play like it does on stock OS, and when we don't have a testing or sandboxed environment to start attempting to add support for MDM that would mimic a production environment.
										- In short: No for lots of reasons.
										- MDM apps depend on lots of privileged functionality that only stock OS provides. The biggest issue right now is MDM apps depend on Play services + Play Store to properly initialise the work profile and to install the company apps. On GrapheneOS, we do not ship Google apps and services by default obviously. This means that when a work profile is created the MDM app expects Play services to be installed automatically, but it's not on GrapheneOS. MDM apps do not handle this case and will usually chain crash or create a very broken / incomplete work profile.
										- It is possible to initialise the broken work profile with your MDM app, then go into GrapheneOS Apps and install sandboxed Google Play, but your work profile will still not be 100% functional because MDM apps delegate installation of the company apps to Play Store. If your company policy forbids you from installing 3rd-party apps in your work profile, then Play Store cannot install any apps because Play Store is not a privileged 1st-party app store like it is on stock OS and will always forbid you from installing your company apps like the corporate VPN, Microsoft Office, Duo MFA, Okta, etc (just examples).
										- The only realistic solutions would be us creating special case bypasses or exceptions for Google apps, but we want to avoid doing such a thing in the first place. We may end up creating _opt-in_ hidden toggles for something like this in the long run.
										- It's also extremely difficult for us to test or add support for this when we do not have a sandbox/playground/test environment of an actual MDM solution that mimics a production environment (Airwatch, InTune, etc).
										- The best you need to do is get a cheap work phone that you can enroll and use strictly for MDM and work.
								- Unclear
								- Comparisons
							- Docs
								- [Different levels of endpoint management and what Google edition you need](https://support.google.com/a/answer/9852079?sjid=6000644266928879828-EU)
								- [Device management overview  |  Android Open Source Project](https://source.android.com/docs/devices/admin)
									- Android Enterprise uses these device management modes:
										- **Fully managed device** (also referred to as _device owner mode_): A DPC app is set as a [device owner](https://source.android.com/docs/devices/admin#fully-managed) during setup and it manages an entire device. This type of device management can be used only on organization-owned (company-owned) devices that are used for work.
										- **Work profile** (also referred to as _managed profile mode_): A DPC app is set as a [profile owner](https://source.android.com/docs/devices/admin#work-profile) and it manages only the work profile on a device, which can also have a personal profile. This type of device management can be used on a personal device or an organization-owned device.
								- [Manage devices for your organization - Google Workspace Admin Help](https://support.google.com/a/topic/24642?hl=en&ref_topic=10012113&sjid=6000644266928879828-EU)
								-
							- Software solutions
								- FOSS
									- [Headwind MDM](https://h-mdm.com/)
									  $20/year per device
									- [Scalefusion MDM](https://www.knowledgenile.com/blogs/open-source-mobile-device-management-tools#Scalefusion MDM)
									- **[Flyve MDM](https://www.knowledgenile.com/blogs/open-source-mobile-device-management-tools#FlyveMDM)**
										- [Flyve MDM Agent | F-Droid - Free and Open Source Android App Repository](https://f-droid.org/en/packages/org.flyve.mdm.agent.mqtt/)
										-
									- **[OneMDM](https://www.knowledgenile.com/blogs/open-source-mobile-device-management-tools#OneMDM)**
									- **[Miradore](https://www.knowledgenile.com/blogs/open-source-mobile-device-management-tools#MIRADORE)**
									- **[ManageEngine](https://www.knowledgenile.com/blogs/open-source-mobile-device-management-tools#ManageEngine)**
									- **[Relution](https://www.knowledgenile.com/blogs/open-source-mobile-device-management-tools#Relution)**
									- **[WipeDrive](https://www.knowledgenile.com/blogs/open-source-mobile-device-management-tools#WipeDrive)**
									- ### [](https://scalefusion.com/mobile-device-management?utm_campaign=MDM-Solution&utm_source=Knowledgenile&utm_medium=Listing&utm_term=Open%20Source)
					- Permissions
						- [Nearby Devices](https://developer.android.com/develop/connectivity/wifi/wifi-permissions)
							- Includes
								- [NEARBY_WIFI_DEVICES](https://developer.android.com/reference/android/Manifest.permission#NEARBY_WIFI_DEVICES)
								- Also Bluetooth and ultra-wideband
						- ajvsol
					- ((6306a77a-3999-4fd1-99dd-630a77dd542c))
					- Android TV
						- Projectivity Launcher
						- BBC iPlayer APK 
						  BBC only whitelists certain devices to download from Google Play Store
							- [TDUK_BBC_iPlayer_001_2024.apk](../assets/TDUK_BBC_iPlayer_001_2024_1763986446392_0.apk)
			- _Android-based ROMs_
			  id:: 649b13d1-a8c5-4f57-b5a7-d505dd2c6f2a
				- Meta
					- [Comparison of Android-based Operating Systems](https://eylenburg.github.io/android_comparison.htm)
				- [LineageOS](https://lineageos.org)
				  id:: 630f96f0-f2c4-4706-9d72-58e13201e03f
				  collapsed:: true
					- Pros/Cons
					  collapsed:: true
						- Pros
							- [Project Treble](https://workflowy.com/#/72a1dee3eda0) since Android 8+ is making ROM development much easier
							- Call recording is supported if you're located in a country where this is legal when installing LineageOS. However has to be enabled by the device maintainer
							  collapsed:: true
								- How to check if it's enabled
									- Use com.android.dialer (AKA "Telephone")
										- Call someone, then press the "Record call" button on the calling screen
										  [https://i.imgur.com/eJfk8K3.png](https://i.imgur.com/eJfk8K3.png)
										- 2 Backlinks
											- For LineageOS [Use com.android.dialer (AKA "Telephone") ](https://workflowy.com/#/b4d5a9fe7f15)
											- On LineageOS I had to activate manual call recording once - [Use com.android.dialer (AKA "Telephone") ](https://workflowy.com/#/b4d5a9fe7f15)
								- Restrictions
									- Manual only
									  collapsed:: true
										- Has to be enabled at the start of each call, unless you use a different app like [Call Recorder (com.github.axet.callrecorder)](https://workflowy.com/#/d36098ce1215) from F-Droid for automatic call recording
									- Geographic restriction
									  collapsed:: true
										- These seems to be rules for selecting the current country
										  [https://github.com/LineageOS/android_packages_apps_Dialer/blob/lineage-17.1/java/com/android/dialer/location/CountryDetector.java#L141](https://github.com/LineageOS/android_packages_apps_Dialer/blob/lineage-17.1/java/com/android/dialer/location/CountryDetector.java#L141)
										- which gets compared to the list here
										  [https://github.com/LineageOS/android_packages_apps_Dialer/blob/lineage-17.1/java/com/android/dialer/callrecord/res/xml/call_record_states.xml](https://github.com/LineageOS/android_packages_apps_Dialer/blob/lineage-17.1/java/com/android/dialer/callrecord/res/xml/call_record_states.xml)
										- How it does the check
											- In a GSM phone, it asks the cellular network itself (NOT the SIM card) for its country code, and uses that if it's available.
											- If that fails (e.g. if you have a CDMA phone, or if the cellular network fails to report a country code), it will fallback to asking the SIM card for its country code.
											- If that fails too, then it checks the locale, which (most likely) corresponds to the language and region you selected when you first ran the setup wizard or modified it in settings. (I am not 100% confident about what other factors may impact this part though.)
											- If, for any reason, it still cannot find your locale, then it assumes you are in the USA.
									- Feature has to be enabled by the device maintainer
									  collapsed:: true
										- In addition to geographic limitations, the feature also needs to be tested on each specific model, and then enabled by that device's maintainer.
											- They don't even attempt to enable it without the device maintainer's cooperation, because there is no single generic solution that's guaranteed to work exactly the same on every different phone.
										- Device maintainer may not have enabled the feature for a few reasons
											- Maybe the device maintainer never tried to enable the feature because it wasn't useful to them personally.
											- Maybe enabling it in order to perform their own tests would have been illegal in the jurisdiction where they live, and so they never tested it hence it was never enabled for anyone else either.
											- Or, maybe they tried to enable it but they couldn't find a configuration that works. (This could happen, for example, if in-call audio is handled in a non-standard way on this particular hardware.)
										- Example
											- Your phone's device tree is missing a configuration file which would enable the feature.
												- Specifically, the overlay needs to override this file: [https://github.com/LineageOS/android_packages_apps_Dialer/blob/lineage-18.1/java/com/android/dialer/callrecord/res/values/config.xml](https://github.com/LineageOS/android_packages_apps_Dialer/blob/lineage-18.1/java/com/android/dialer/callrecord/res/values/config.xml)
												- The overridden file needs to set the "call recording enabled" field to true, but also (and actually much more importantly) to specify the specific audio mixer settings which would be needed on that hardware in order to capture both sides of the conversation. Depending on the hardware, there may or may not be a single trivial XML configuration setting which could accomplish this task.
								- 1 Backlink
									- See [LineageOS](https://workflowy.com/#/1543bac42ca5) - <a href="https://workflowy.com/#/7a612aa23bab">Call recording is supported if you're located in a country where this is legal when installing LineageOS. However has to be enabled by the device maintainer</a>
							- Features
							  collapsed:: true
								- Internet permission
								- Redesigned volume panel in LineageOS 19
								  [https://lineageos.org/Changelog-26/](https://lineageos.org/Changelog-26/)
									- 2 Backlinks
										- LineageOS 19 (Android 12) has a [Redesigned volume panel in LineageOS 19](https://workflowy.com/#/570bb6a9db5b) which allows toggling between vibrate and silent mode
										- See [Redesigned volume panel in LineageOS 19](https://workflowy.com/#/570bb6a9db5b)
									- Replaces F-Droid app [QuickTiles](https://workflowy.com/#/a860045b6873) which I used for toggling it before
						- Cons
							- See [Basically requires you to use stock OS or a security-focused ROM like GrapheneOS or CalyxOS without root etc](https://workflowy.com/#/ea8c2616a63e)
							- Less supported devices and takes longer than [Stock Android AOSP ](https://workflowy.com/#/5c6940e545df) to get the latest Android version
							- Daniel Micay argues that stock Android or AOSP has much better security than LineageOS, let alone GrapheneOS
							  source:: https://www.reddit.com/r/CopperheadOS/comments/917yab/can_anyone_technically_explain_why_lineageos_as/e2xiot5/
							  collapsed:: true
								- It significantly weakens the SELinux policies, rolls back mitigations for device porting / compatibility, disables verified boot, lacks proper update security including rollback protection, adds substantial attack surface like FFmpeg alongside libstagefright, etc. They merge in huge amounts of questionable, alpha quality code from the Code Aurora Forum repositories too. Many devices (including Nexus and Pixel phones) also don't get their full firmware updates shipped by LineageOS. It's unrealistically expected that users will flash the firmware and vendor partitions on their own each month and of course that's another incompatibility with verified boot and a locked bootloader.
								- If you've used it, you're probably aware the endless churn and bugs which strongly reflects on the security since bugs are often exploitable. You don't want to be using nightly builds / snapshots of software in production if you're security conscious.
								- If you want something decently secure, use the stock OS or AOSP on a Pixel. The only real alternative is buying an iPhone. Verified boot and proper update security (i.e. offline signing keys, rollback protection) are standard and should be expected, but other issues like attack surface (i.e. not bundling in every sketchy codec under the sun, etc.) and SELinux policy strength matter too.
							- Unless using a Pixel/Nexus, it requires an unlocked bootloader
							  collapsed:: true
								- requires an unlocked bootloader unless you sign every single release yourself on another machine. This completely hoses the security model, if someone gets a hold of your phone for 5 minutes they can flash a compromised image and you'd be none the wiser and there's no roll back protection either.
								- Require bootloader to stay unlocked. Not a huge security concern if you consider phone compromised if out of possession
									- With the bootloader unlocked the only risk is that if your phone is out of your possession for a significant period of time, consider it compromised. So don't turn on and unlock it again since it's easy to flash a backdoor to it via the bootloader, which could upload your sensitive data as soon as it gets internet access.
							- Additionally security updates are completely in the hands of the maintainer, this isn't really an issue for pixels but for other more obscure devices can be problematic, especially if the manufacturer is no longer providing updates or custom ROMs rely on using older firmware.
							- AFAIK AOSP does not do this, while ironically Lineage uses Google for connectivity servers and fallback DNS.
							- _Lacks_
							  collapsed:: true
								- Bring back PrivacyGuard
									- PrivacyGuard was deprecated in 17.1 in favour of AOSP's PermissionHub but the Hub is sorely lacking in features. Permission Manager X[1] is very similar to what PrivacyGuard was and it works on LOS 18.1. It would be great to see it or a similar feature return to LOS officially so that rooting is not required.
									- [1] [https://f-droid.org/packages/com.mirfatif.permissionmanagerx/](https://f-droid.org/packages/com.mirfatif.permissionmanagerx/)
								- Integrate Wrong PIN Shutdown
									- Wrong PIN Shutdown[1] is an excellent FOSS app which enhances security by shutting down your phone after there's too many failed login attempts (user configurable amount). It requires root and device admin permissions, which could be avoided by integrating it into LOS.
									- Currently on LOS 18.1 you can have as many attempts as you like without issue, adding in this feature would allow at least delaying an attacker. An additional possibiity for greater security is enabling the phone to automatically factory reset after X shutdowns, but this feature is likely not for everyone.
									- [1] [https://f-droid.org/packages/org.nuntius35.wrongpinshutdown/](https://f-droid.org/packages/org.nuntius35.wrongpinshutdown/)
								- Create a dashboard for managing network access for all apps
									- LOS has 6 toggles currently for configuring the firewall for each app (eg Wi-Fi data, Mobile data etc) but this can only be configured on a per-app basis. A dashboard for configuring apps in bulk would be supremely helpful here. Example UI attached (AFWall)
					- # Documentation
						- [Filtering and sorting supported devices](https://lineageosdevices.com/)
						- Versioning scheme
							- LOS 21 (released [[2024-02-14 Wednesday]] ) = Android 14 (released 5 months earlier [[2023-09-04 Monday]] )
							- LOS 18 (released Q2 2021) = Android 11 (released 6 months earlier, Q3 2020)a
						- SOPs
						  id:: 649b13d1-e58f-450a-b61f-a9f3881d2384
							- Installing ((630f96f0-f2c4-4706-9d72-58e13201e03f))
							  id:: 6318fc64-bca8-4498-b89b-ce06723bda00
							  collapsed:: true
								- Download the LineageOS installation package that you would like to install (or build the package yourself)
								  id:: 6318fc64-baac-43f1-9d6d-8c7190588edf
									- e.g. https://download.lineageos.org/beryllium
								- (optional) Download either ((6318fc66-9d9f-4547-8e1c-172958500c0d)) or ((649b13d2-f7fb-449f-808b-d819f81d3094))
									- ((649b13d2-804a-4d55-b423-4cdad45edc51))
									- ((649b13d2-f7fb-449f-808b-d819f81d3094))
								- If you are not in recovery, then ((6318fc64-69c1-47ce-ae59-ddbaec207165))
								- Now tap Factory Reset, then Format data / factory reset and continue with the formatting process. This will remove encryption and delete all files stored in the internal storage, as well as format your cache partition (if you have one).
								- Return to the main menu.
								- Sideload the LineageOS .zip package:
									- On the device, select “Apply Update”, then “Apply from ADB” to begin sideload.
										- If on TWRP: Advanced > ADB Sideload
									- On the host machine, sideload the package using: adb sideload filename.zip
								- (Optionally): If you want to install any additional add-ons, click Advanced, then Reboot to Recovery, then when your device reboots, click Apply Update, then Apply from ADB, then adb sideload filename.zip those packages in sequence.
								- Note: If you want Google Apps on your device, you must follow this step before booting into LineageOS for the first time!
								- Once you have installed everything successfully, click the back arrow in the top left of the screen, then “Reboot system now”.
								- {Archive}
									- [source] [https://wiki.lineageos.org/devices/sailfish/install](https://wiki.lineageos.org/devices/sailfish/install)
								- Related:
									- ((631b4654-9823-4293-b5c4-1417299c0a06))
									- ((6318fc64-5f04-4c15-a3ae-3ba92e5f2926))
							- Updating LineageOS (minor versions)
							  id:: 631b4654-9823-4293-b5c4-1417299c0a06
							  collapsed:: true
								- Note: it will uninstall Magisk, ((6318fc66-9d9f-4547-8e1c-172958500c0d)), any other flashed files. Don't bother with this, because 09/09/2022 I've got problems with Google Play Services constantly crashing and it making other apps like Uber and Google Play Store crash
								- Basically same as ((6318fc64-5f04-4c15-a3ae-3ba92e5f2926))
							- Upgrading ((630f96f0-f2c4-4706-9d72-58e13201e03f)) (major versions)
							  id:: 6318fc64-5f04-4c15-a3ae-3ba92e5f2926
							  collapsed:: true
								- Version A: using TWRP
									- ((6318fc64-69c1-47ce-ae59-ddbaec207165))
										- {{embed ((6318fc64-69c1-47ce-ae59-ddbaec207165))}}
									- In TWRP: Advanced > Sideload
									- On PC terminal, `cd` to appropriate directory and sideload the new LineageOS ZIP
										- e.g. `adb sideload lineage-19.1-20220426-nightly-beryllium-signed.zip`
									- If also wanting to install GApps and/or Magisk
										- Click "Back" > ADB Sideload
										- On PC terminal, `cd` to appropriate directory and sideload the ZIP
								- Version B: [using official LineageOS method](https://wiki.lineageos.org/devices/beryllium/upgrade/)
									- Once you've booted into recovery
										- Click `Advanced`, then `Enable ADB`.
										- Run `adb -d reboot sideload`.
										- Run `adb -d sideload /path/to/zip` (inserting the path to your LineageOS package).
							- Installing a new ROM
							  collapsed:: true
								- _Steps_
									- Install ROM on backup phone to see if it works there fine first
									- ((6318fc64-69c1-47ce-ae59-ddbaec207165))
									- Flash system image ZIP
									- (optional) Root phone
									  _See_ [How to Root](https://workflowy.com/#/993444d17433)
									- Finish setup
									  _See _[Setting up new phone](https://workflowy.com/#/290b4f929026)
								- _Related:_ [Installing LineageOS from recovery](https://workflowy.com/#/0c2feb459151)
							- https://andrevallestero.github.io/lineageos-device-browser/
							  Newest phones with LOS support
						- TO-DO
							- ((649b13d2-abc9-4fb0-a722-1313c6d874b8))
						- _Features_
							- Network Location Provider
							  collapsed:: true
								- Apple (online, but location calculation is done on the phone)
								- Radiocells.org (either online or offline)
								- Déjá Vu (100% offline)
								- Local GSM (downloads the complete cell tower data information for a country from either Mozilla or OpenCellID -- ~230MB for US -- and calculates location offline)
								- WiFi Location Service (same as Déjá Vu but only uses WiFi points instead of cell tower data)
							- It uses Aurora Store to update Google Play apps
							  collapsed:: true
								- Play Store apps aren't updated by MicroG repos -- they're updated with Aurora Store, which is a FOSS front-end for the Google Play Store. You can set a custom whitelist of apps to be updated from the Play Store in Aurora Store.
								- If I understand what you're trying to do (I haven't done Android tinkering in years until a week ago), you should be able to:
									- restore the [titanium](https://workflowy.com/#/15c43e198c80)<a href="https://workflowy.com/#/15c43e198c80"> backup</a> on a new LOS + MicroG flash
									- install Aurora Store from F-Droid
									- enable the whitelist in Aurora Store settings
									- add all of your apps from the backup into the whitelist
									- when Aurora Store checks for updates, those apps' updates will be downloaded and you'll be prompted to install them
								- I believe Aurora Store may attempt to update all apps on the phone if they exist on the Play Store as well by default, but I feel safer using a white list. That way you don't get Aurora Store trying to update Slide from F-Droid with Slide from the Play Store, for example.
								- 1 Backlink
									- [It uses ](https://workflowy.com/#/57988614d2dd)<a href="https://workflowy.com/#/57988614d2dd">Aurora</a><a href="https://workflowy.com/#/57988614d2dd"> Store to update Google Play apps</a>
							- _Apps_
								- ((649b13ce-0e7b-4303-9ab3-8a71ad53ccb3))
						- Deprecated
						  collapsed:: true
							- LineageOS Privacy Guard
								- One of the defining features of LOS is Privacy Guard. You can deny any app any permissions it requests, even ones not "officially" supported by Android. Sure, there's permissions for Phone, Location, etc. -- but there's also permissions for things like keep awake, start at boot, run in background, toggle NFC, etc. You can deny any of these to an app which requests it. Additionally, you can require that an app ask you every time it wants to access a permission -- not just the first time it tries to access that permission.
								- For example, I've denied Google Maps the following permissions: read contacts, send SMS, camera, record audio, call phone, modify settings, toggle WiFi, toggle NFC, start at boot, read external storage, and write to external storage. Google Maps still functions perfectly, despite listing all these permissions.
								- Note that for general Android permissions, both the Android permission and the Privacy Guard permissions have to be on for an app to access that permission. Privacy Guard gives everything all of its permissions by default, but an app will still have to ask for permissions like Phone, Location, etc.
								- Privacy Guard is a way to control more permissions than the built-in Android permissions, and to use apps that force you to accept permissions without actually giving them permission.
						- How to check if your device will receive the upcoming next version
							- Find device codename on [Devices](https://wiki.lineageos.org/devices/) webpage
							- Look up codename on LineageOS GitHub organisation repos e.g. [Branches · LineageOS/android_device_xiaomi_beryllium · GitHub](https://github.com/LineageOS/android_device_xiaomi_beryllium/branches)
							- Check the branches for `lineage-22` or whatever is relevant for your particular device
					- Related:
						- ((649b13d0-fc6f-4ce9-a017-703c6e520cb9))
						- ((649b13d2-a633-4de3-aa08-e24106059dab))
						- ((649b13d1-fd88-4773-a27e-ac5d7acb352d))
				- [GrapheneOS](https://grapheneos.org)
				  id:: 63209286-6f40-4063-9fdc-2543251d416e
				  collapsed:: true
				  AKA CopperheadOS previously
					- Pros/Cons
					  id:: 635037d0-d4a1-49cc-b9bc-13a5b4f970c5
						- Pros
							- Being able to relock bootloader and ((644c0acf-58a1-4b82-9767-c88c65955315)) enables very high local protection from Evil Maid attacks
							  id:: 649b13d1-d103-4938-85a5-b13074f90f94
							  collapsed:: true
								- ((644c0acf-58a1-4b82-9767-c88c65955315)) enables hardware-based verification
									- Can check that firmware and OS isn't compromised via an app
							- Better than security features than ((631fa93e-1087-4996-91b8-7526842b4ba8))
							  collapsed:: true
								- [https://grapheneos.org/features](https://grapheneos.org/features)
								- An easier way to change the captive portal from Google to GrapheneOS servers
								  [https://github.com/GrapheneOS/os_issue_tracker/issues/198#event-4018946005](https://github.com/GrapheneOS/os_issue_tracker/issues/198#event-4018946005)
								- Reproducible builds
								  [https://grapheneos.org/build#reproducible-builds](https://grapheneos.org/build#reproducible-builds)
							- Extra permission toggles for Network, Sensors
							  collapsed:: true
								- paper on using heavily throttled sensor polling within iOS and Android for recording speech.
								  [https://www.usenix.org/system/files/conference/usenixsecurity14/sec14-paper-michalevsky.pdf](https://www.usenix.org/system/files/conference/usenixsecurity14/sec14-paper-michalevsky.pdf)
							- [Wi-Fi anonymity](https://grapheneos.org/features) (per-connection MAC randomization, anonymous DHCP, anonymous IPv6)
							- [Sandboxed Google Play Services](https://grapheneos.org/usage#sandboxed-play-services)
							  id:: 635037d0-5875-4083-8a49-4c68a6af8843
							  collapsed:: true
								- Pros/Cons
								  id:: 635037d0-8190-4f4d-9baa-7f533f693746
									- Pros
										- microG lacks support for many APIs which GrapheneOS might now be able to support with their version
										  collapsed:: true
											- [Diopter Calculator app](https://workflowy.com/#/d19bbd08c7d6) ?
											-
									- Cons
										- [Supports eSIM support currently (it depends on Play Services), though it may have some limitations](https://github.com/GrapheneOS/os-issue-tracker/issues/159#issuecomment-1292329307)
									- in a sandbox which has some advantages over microG, though it has limitations
									- {Archive}
										- [Used to lack network-based location services support and was planning for a local db solution](https://github.com/GrapheneOS/os-issue-tracker/issues/24#issuecomment-905869927])
										  id:: 635037d0-a3e1-47c5-a9c7-8d218c761570
								- Docs
								  collapsed:: true
									- [https://apps.grapheneos.org/packages/](https://apps.grapheneos.org/packages/)
									- Compatibility layer/helpers embedded within GrapheneOS
										- Search for `GmsCompat`
										  [https://github.dev/GrapheneOS/platform_frameworks_base](https://github.dev/GrapheneOS/platform_frameworks_base)
									- Usage
									  [https://grapheneos.org/usage#sandboxed-google-play](https://grapheneos.org/usage#sandboxed-google-play)
										- Docs
											- Intro
												- GrapheneOS has a compatibility layer providing the option to install and use the official releases of Google Play in the standard app sandbox. Google Play receives absolutely no special access or privileges on GrapheneOS as opposed to bypassing the app sandbox and receiving a massive amount of highly privileged access. Instead, the compatibility layer teaches it how to work within the full app sandbox. It also isn't used as a backend for the OS services as it would be elsewhere since GrapheneOS doesn't use Google Play even when it's installed.
												- Since the Google Play apps are simply regular apps on GrapheneOS, you install them within a specific user or work profile and they're only available within that profile. Only apps within the same profile can use it and they need to explicitly choose to use it. It works the same way as any other app and has no special capabilities. As with any other app, it can't access data of other apps and requires explicit user consent to gain access to profile data or the standard permissions. Apps within the same profile can communicate with mutual consent and it's no different for sandboxed Google Play.
												- The core functionality and APIs are almost entirely supported already since GrapheneOS largely only has to coerce these apps into continuing to run without being able to use any of the usual invasive OS integration. A compatibility layer is also provided to support dynamically downloaded/loaded modules (dynamite modules). The compatibility layer will be gradually expanded and improved in order to get more of the Google Play functionality working.
												- GrapheneOS provides a dedicated compatibility layer for Play Store app installation/updates/removal teaching it to use the standard unprivileged approach available to sandboxed apps. It prompts the user to permit it as an app source and then prompts for the initial app install/update or removal. It will use Android 12's support for unattended updates when possible which means it can do unattended updates of modern (API 29+) apps where it was the installer for the currently installed version already.
											- Installation
												- Google Play is divided up into 3 separate apps:
													- Google Services Framework (com.google.android.gsf)
													- Google Play services (com.google.android.gms)
													- ((66d095d8-4f55-4927-bc65-eaa9a58b0630)) (com.android.vending)
												- To use sandboxed Google Play, you simply need to install the official releases of these 3 apps in the user and work profiles where you want to use it.
												- The simplest approach is to only use the Owner user profile. Apps installed in the Owner profile are sandboxed the same way as everywhere else and don't receive any special access. If you want to choose which apps use Google Play rather than making it available to all of them, install it in a separate user or work profile for apps depending on Google Play. You could also do it the other way around, but it makes more sense to try to use as much as possible without Google Play rather than treating not using it as the exceptional case.
												- You can open our app repository client (Apps) and install the 3 core Google Play apps mirrored in our repository. Our app repository client has support for dependency installation so you can simply directly install the Play Store and it will install GSF and then GMS as dependencies.
												- You should give a battery optimization exception to Google Play services for features like push notifications to work properly in the background. It isn't needed for the other 2 apps.
												- The Play Store provides many services used by apps including Play Asset Delivery, Play Feature Delivery, in-app purchases and license checks for paid apps. You can use sandboxed Google Play without the Play Store but many apps won't work correctly without it. The Play Store app is also the most secure way to install and update apps from the Play Store. Installing it is highly recommended for general purpose usage but you can install only GSF or only GSF/GMS if you know it's all you need for what you want to use.
												- After installing the apps, you should open the Play Store and press sign in to trigger initialization. Signing into an account is optional and it will work fine without it, but you do need to get it initialized and this is currently the best way to mimic the initialization done by the stock OS setup wizard.
												- You can obtain updates to these apps from our app repository client. Our compatibility layer supports the Play Store updating itself and also Play services but we've chosen to block it from being able to update them in order to ship the updates through our repository after testing them. They use long staged rollouts for these app updates and it results in confusion when users can't install older versions in another user, which is resolved by us handling the updates ourselves.
												- Our compatibility layer has support for Play Games Services which you can obtain by installing Google Play Games from the Play Store. Many games on the Play Store depend on having Google Play Games installed.
											- Configuration
												- The compatibility layer has a configuration menu available at Settings ➔ Apps ➔ Sandboxed Google Play.
												- By default, apps using Google Play geolocation are redirected to our own implementation on top of the standard OS geolocation service. If you want to use Google's geolocation service instead, you can disable the "Reroute location requests to OS APIs" toggle and manually grant "Allow all the time" Location access to Google Play services. For it to be fully functional, you also need to use "Google Location Accuracy" link to access the Google Play services menu for opting into their network location service. This will send the nearby Wi-Fi and cellular networks provided via the Location permission to their service to retrieve a location estimate. The Nearby Devices permission can also be granted to give it access to nearby Bluetooth device IDs. If you stick with the default enabled redirection mode, none of this needs to be granted for working geolocation in apps. In order to fully take advantage of Wi-Fi and Bluetooth scanning, you also need to enable the scanning toggles in Settings ➔ Location ➔ Location services which are disabled by default rather than enabled by default like the stock OS.
												- Re-routing location to the OS geolocation service will use more power than using the Google Play geolocation service since we do not provide a network-based location service and implement it via GNSS / A-GPS only. In the future, we plan on providing a pseudo-network geolocation service for the OS by using a local database of cell towers, and the location redirection feature can also make use of this future OS implementation for network location requests once it's available.
												- The Google Location Accuracy and Google settings activities would normally be integrated into the OS but we don't include any of the standard Google Play integration so there needs to be an app providing a way to access them.
												- The menu also provides links to this usage guide, Play services system settings, Play Store system settings and Google settings. The Play services and Play Store system settings are only included for convenience since they can be accessed the same way as any other app via Settings ➔ Apps.
											- Limitations
												- Our compatibility layer has to be expanded on a case-by-case basis to teach Play services to work as a regular app without any of the invasive access and integration it expects. In many cases, it doesn't truly need the access or we can teach it to use the regular approach available to a normal app. In some cases, the functionality it offers fundamentally requires privileged access and cannot be supported. For example, it's unlikely Android Auto will be supported. The same applies to other highly invasive OS integration / control or privileged access to hardware. There are also a lot of features such as the FIDO2 security key support which could be made to fully work despite reliance on a lot of privileged APIs (their FIDO2 service is partially working already). In the case of FIDO2, we could also eventually support redirecting to our own implementation similarly to how we do that by default for geolocation. Our compatibility layer is a very actively developed work in progress and most of the remaining unavailable functionality is quickly becoming supported.
												- Functionality depending on the OS integrating Play services and using it as a backend is unavailable. An OS integrating Play uses it as the backend for OS services such as geolocation. GrapheneOS never uses it as the backend/provider for OS services. In cases such as text-to-speech (TTS) where the OS allows the user to choose the provider, Play services can often be used. It's on a level playing field with other apps on GrapheneOS.
												- Play Store assumes that uninstallation always succeeds so it will stall if it tries to uninstall an app and you reject it. You can work around this by force stopping and then reopening it.
											- Privileged ((649b13ca-0417-44e6-ab64-fa0ebae72f22)) management
											  id:: 644c0acf-7f11-4ade-9b07-1812672b5ac4
												- By default GrapheneOS always has shipped with baseline support for eSIM, where users can use any eSIMs installed previously on the device. However, in order to manage and add eSIMs, proprietary Google functionality is needed. This is fully disabled by default.
												- Privileged eSIM management can be enabled in Settings ➔ Network & Internet ➔ Privileged eSIM management. The toggle will be greyed out and unusable if sandboxed Google Play is not installed, as the functionality is reliant on it.
												- By enabling the toggle, the proprietary Google functionality is enabled and will be used by the OS to provision and manage eSIMs.
								- Also available on ProtonAOSP, which only supports Pixels also [but unlike GrapheneOS they allow root](https://protonaosp.org/root)
								- ((6318fc66-9d9f-4547-8e1c-172958500c0d))
							- eSIM support. Requires ((635037d0-5875-4083-8a49-4c68a6af8843))
							  id:: 649b13d1-99cb-442b-805c-40a7c0424493
							  collapsed:: true
								- [https://grapheneos.org/usage#sandboxed-google-play-esim](https://grapheneos.org/usage#sandboxed-google-play-esim)
								- phhusson made a FOSS alternative that's better than Graphene's
								  [https://gitea.angry.im/PeterCxy/OpenEUICC](https://gitea.angry.im/PeterCxy/OpenEUICC)
							- ((63219e37-6ffb-43fd-af6b-0529f25f47a7))
							- Call recording support in dialler [since April 2023](https://discuss.grapheneos.org/d/3320-crowdfunding-to-implment-call-recording/40)
							  id:: 6516c476-3ca5-441a-b77d-95668a90c8b7
							- [A duress password feature](https://github.com/GrapheneOS/os_issue_tracker/issues/29#issuecomment-808978734)
							- [Improved user profiles](https://grapheneos.org/features#improved-user-profiles)
							  id:: 6734cfe5-e8f7-4cbe-ae3a-a32c97b63717
							  collapsed:: true
								- Meta
									- Basically like desktop OS users, so you can't see running apps or disk of other users
									- Reduces the harm of `QUERY_ALL_PACKAGES` for fingerprinting you by viewing all your packages
									  id:: 67e802f5-ffc8-4d6c-a2de-64ab1603a24d
										- Can create many separate profiles
									- Android's user profiles are isolated workspaces with their own instances of apps, app data and profile data (contacts, media store, home directory, etc.). Apps can't see the apps in other user profiles and can only communicate with apps within the same user profile (with mutual consent with the other app). Each user profile has their own encryption keys based on their lock method. They're a great fit for GrapheneOS with a lot of room for improvement.
									- #### [Notification forwarding](https://grapheneos.org/features#improved-user-profiles#notification-forwarding)
										- GrapheneOS supports forwarding notifications from users running in the background to the currently active user. Forwarding notifications to other users is disabled by default and can be enabled within each user profile where forwarding to the active profile is wanted. Notifications forwarded from other profiles are displayed by default in a standard local notification channel.
									- https://news.ycombinator.com/item?id=45241558
									-
								- Related:
									- ((649b13ce-b4f8-45e9-857a-28eb2ad4ffd2))
									- ((66028eb2-021c-4711-baa0-3ebcc7b05647)) : ((670bfaa4-c14d-4575-aad6-5f846468d6da))
							- ((649b13d1-0440-4bfa-8802-d4559e628c21))
							- ((6516c476-3ca5-441a-b77d-95668a90c8b7))
						- Cons
							- Incompatible with ((63209284-e6f8-47bd-a47c-e2733cf7b886)) unless using ((65193b42-39f7-4774-a8d9-bed08bd5f6f6)). However they do have good reasoning for this
							  collapsed:: true
								- ((63209284-e6f8-47bd-a47c-e2733cf7b886)) : ((644c0acc-4506-4afb-87dc-4413f76e7079))
							- [Some apps ban usage on this OS](https://grapheneos.org/articles/attestation-compatibility-guide#apps-banning-grapheneos)
							  Revolut also
							- [Some apps incompatible with this OS](https://discuss.grapheneos.org/d/8330-app-compatibility-with-grapheneos)
								- [GitHub - PrivSec-dev/banking-apps-compat-report: Report and track banking app compatibility with GrapheneOS, including which workarounds may be required.](https://github.com/PrivSec-dev/banking-apps-compat-report)
								- https://privsec.dev/posts/android/banking-applications-compatibility-with-grapheneos/
								-
							- Drama and censorship
							  collapsed:: true
								- [Daniel Micay publicly steps down from GrapheneOS | Hacker News](https://news.ycombinator.com/item?id=36089104) 2023
								- June 2022 - Daniel Micay ([thestinger](https://github.com/thestinger))
									- Daniel Micay gets mad that a supposed CalyxOS contributor made a PR to Bromite browser. Threatened Bromite that they need to not accept the PR or GrapheneOS project would cut ties with Bromite and prevent them from using their code from Vanadium browser
									  source:: [https://github.com/bromite/bromite/pull/2102](https://github.com/bromite/bromite/pull/2102)
									- When previous PR gets closed for being too heated, Daniel Micay says Bromite is no longer welcome to use GrapheneOS/Vanadium code and they'll be changing their licensing to prevent it being used in the future. Also anyone who contributes to Bromite will be banned "until there is an apology and a commitment not to support abusive behavior towards us"
									  source:: [https://github.com/bromite/bromite/issues/2141](https://github.com/bromite/bromite/issues/2141)
								- 22/10/21 I post a message on the Matrix group saying I was disappointed that Fuchsia was going to be used because it could
									- strcat:
										- and I don't see how ((649b13cf-a825-48f5-ae83-b47b6ad6bff9)) has anything to do with a 'walled garden'
										- I consider it misinformation and concern trolling
										- near 0 tolerance policy for that stuff due to daily raids on our rooms and attacks on the project
									- My reply
										- Well I can't reply now if I might get banned now right
								- There is a fight between CalyxOS and Techlore vs GrapheneOS
									- Techlore video
									  [https://www.youtube.com/watch?v=Dx7CZ-2Bajg](https://www.youtube.com/watch?v=Dx7CZ-2Bajg)
							- Their approach has several big issues which will become more apparent over time
							  id:: 635037d0-40fe-4427-ab55-8c617947e5a2
								- They're more in favour of becoming a secure, walled garden like iOS rather than libre software like Linux
								  collapsed:: true
									- iOS has many issues, such as them trying to implement CSAM scanning,
									- GrapheneOS doesn't take steps to prevent [Tivoisation](https://en.wikipedia.org/wiki/Tivoization)
								- They ignore just how harmful relying on closed-source hardware can be
								  collapsed:: true
									- _Current closed-source components in Pixel phones_
										- ((649b13cd-0383-495e-8973-cdb138645c60))
										- ((649b13cc-b652-4669-9955-ecfea35cd008))
										- Bluetooth
										- Wi-Fi
									- All of these if they were written by hostile adversaries, or even just exploited, could be a vector for serious privacy harm
									- outdated and insecure firmware with known vulnerabilities
								- They prioritise having the ((649b13cc-b652-4669-9955-ecfea35cd008)) over pro-consumer hardware features
								  collapsed:: true
									- They don't care about
									  [mirrored]
										- [Fairphone](https://workflowy.com/#/49ee6e93a36d) and <a href="[A simpler way to organize your work - Workflowy](https://workflowy.com/#/d66a2335ad37">PinePhone</a>) modularity for repair and battery replacement
										  collapsed:: true
											- No easily removable battery
											  e.g. 2 hours to swap. Delicate and requires special items [https://www.ifixit.com/Guide/Google+Pixel+5+Battery+Replacement/140528](https://www.ifixit.com/Guide/Google+Pixel+5+Battery+Replacement/140528)
										- [Fairphone](https://workflowy.com/#/49ee6e93a36d) and <a href="[A simpler way to organize your work - Workflowy](https://workflowy.com/#/d66a2335ad37">PinePhone</a>) having microSD slots
										- [PinePhone](https://workflowy.com/#/d66a2335ad37) hardware killswitches
								- Roadmap prioritises replacing Linux. First switch to hypervisor + VMs, then switching to a microkernel + containers for Linux, then not needing containers since all software runs natively
								  collapsed:: true
									- [Roadmap](https://grapheneos.org/faq#roadmap)
										- In the long term, GrapheneOS aims to move beyond a hardened fork of the Android Open Source Project. Achieving the goals requires moving away from relying on the Linux kernel as the core of the OS and foundation of the security model. It needs to move towards a microkernel-based model with a Linux compatibility layer, with many stepping stones leading towards that goal including adopting virtualization-based isolation.
										- First stage will be to use hypervisor like Xen for reinforcing existing security boundaries. Linux would be running inside the virtual machines at this point, inside and outside of the sandboxes being reinforced.
											- This approach is similar to [Qubes OS](<((635037c3-993a-4bfc-9c65-2157fd59a626))>)
											  #PC-Linux
											- It's also similar to WSL (Windows Subsystem for Linux)
										- collapsed:: true
										  2. In the longer term, a microkernel would be used on the host and then Linux inside the sandboxes can be replaced with a compatibility layer like gVisor, which would need to be ported to arm64 and given a new backend alongside the existing KVM backend.
										     collapsed:: true
											- gVisor
												- What
												  collapsed:: true
													- Application kernel for containers
													- Instead of containers like Docker using the shared Linux kernel, each container will use the gVisor kernel
												- [https://github.com/google/gvisor](https://github.com/google/gvisor)
												- [https://gvisor.dev/](https://gvisor.dev/)
										- collapsed:: true
										  3. Over the longer term, the microkernel would be able to run all userspace software natively, Linux can fade away completely and so can the usage of virtualization.
										     collapsed:: true
											- The anticipation is that many other projects are going to be interested in this kind of migration, so it's not going to be solely a GrapheneOS project, as demonstrated by the current existence of the gVisor project and various other projects working on virtualization deployments for mobile. Having a hypervisor with verified boot still intact will also provide a way to achieve some of the goals based on extensions to Trusted Execution Environment (TEE) functionality even without having GrapheneOS hardware
							- Limitations of ((635037d0-5875-4083-8a49-4c68a6af8843))
							  collapsed:: true
								- Cons
								  [mirrored]
								- Play services Location APIs are able to return real results if users explicitly grant Play services foreground Location access + Phone access.
								- new configuration menu for our compatibility layer in Settings → Apps → Sandboxed Google Play. It currently exposes shortcuts to the Google Play configuration activities including the one for opting into using their network location service if you want to use it.
								- Latest release of GrapheneOS has support for rerouting apps using the Google Play geolocation service to the GrapheneOS geolocation service. Redirection is enabled by default on 1st launch unless the user previously granted Location to Play services. Users still have the option to use Google Play's geolocation service by toggling off redirection, granting it Location access and optionally opting into their network location service. Similar options can be provided for other features such as their sensors API in the future.
							- A bit expensive usually as it's only [officially compatible with latest few years of Pixel phones](https://grapheneos.org/faq#supported-devices)
							  collapsed:: true
								- Pixel 3 is still supported by GrapheneOS, whereas the oldest device supported is the Pixel 2 by CalyxOS and LineageOS (Fri, Oct 15, 2021) which is Q4 2017, 4 years ago released
								- ...
								- They've also signalled they might need custom-built phones in the future for better hardware
								- Standard hardware-based security features like the hardware-backed keystores, verified boot, ((644c0acf-58a1-4b82-9767-c88c65955315)) and various hardware-based exploit mitigations need to be available.
								- Devices also need to have decent integration of IOMMUs for isolating components such as the GPU, radios (NFC, Wi-Fi, Bluetooth, Cellular), media decode / encode, image processor, etc., because if the hardware / firmware support is missing or broken, there's not much that the OS can do to provide an alternative
							- Small list of supported devices, difficult to run on non-supported devices
							  collapsed:: true
								- Need to build it myself
								- Won't include auto updates
								- FAQ
								  source:: [https://grapheneos.org/faq#device-support](https://grapheneos.org/faq#device-support)
									- Many other devices are supported by GrapheneOS at a source level, and it can be built for them without modifications to the existing GrapheneOS source tree. Device support repositories for the Android Open Source Project can simply be dropped into the source tree, with at most minor modifications within them to support GrapheneOS. In most cases, substantial work beyond that will be needed to bring the support up to the same standards. For most devices, the hardware and firmware will prevent providing a reasonably secure device, regardless of the work put into device support.
									- GrapheneOS also supports generic targets, but these aren't suitable for production usage and are only intended for development and testing use. For mobile devices, the generic targets simply run on top of the underlying device support code (firmware, kernel, device trees, vendor code) rather than shipping it and keeping it updated. It would be possible to ship generic system images with separate updates for the device support code. However, it would be drastically more complicated to maintain and support due to combinations of different versions and it would cause complications for the hardening done by GrapheneOS. The motivation doesn't exist for GrapheneOS, since full updates with deltas to minimize bandwidth can be shipped for every device and GrapheneOS is the only party involved in providing the updates. For the same reason, it has little use for the ability to provide out-of-band updates to system image components including all the apps and many other components.
									- Some of the GrapheneOS sub-projects support other operating systems on a broader range of devices. Device support for Auditor and AttestationServer is documented in the [overview of those projects](https://attestation.app/about). The <a href="https://github.com/GrapheneOS/hardened_malloc">hardened_malloc</a> project supports nearly any Linux-based environment due to official support for musl, glibc and Bionic along with easily added support for other environments. It can easily run on non-Linux-based operating systems too, and supporting some like HardenedBSD is planned but depends on contributors from those communities.
								- Other potential devices need a security chip at minimum
							- _Lacks_
								- [app communication/visibility scopes for non-system components · Issue #2197 · GrapheneOS/os-issue-tracker · GitHub](https://github.com/GrapheneOS/os-issue-tracker/issues/2197) as a successor to ((644c0ad0-a7b3-4853-abd4-7e41b5125f29)) blocking
								  id:: 6797d4d0-96eb-4588-897e-88c84cf1f4dc
								- Datura firewall (CalyxOS feature) provides an overview of all app network permissions
						- Unclear
							- I intentionally degrade my security and privacy through a few tradeoffs
								- Wireless ADB debugging enabled for ((63209285-2e05-40f2-bce9-5b8d813eea86))
								- USB debugging enabled for ((63a9ade4-0cdf-4680-a839-6b6f92e57f51))
							- (see ((631fa93d-9604-49fd-b8d3-2731d6dc41bb)) )
							  #Phone-Android
							- Lead dev would rather write-from-scratch than build on existing FOSS solutions most of the time
							  id:: 649b13d1-7ddf-4366-b96e-e1edc58593f2
							  collapsed:: true
								- _Would rather not use_
									- [F-Droid](https://github.com/GrapheneOS/os_issue_tracker/issues/94#issuecomment-782668317)
									- [microG however now](https://github.com/GrapheneOS/os_issue_tracker/issues/204#issuecomment-747060877) can run Google Play Services in a sandbox, which has advantages
									- [Network-based location services alternative](https://github.com/GrapheneOS/os_issue_tracker/issues/24#issuecomment-819771941) 
									  id:: 649b13d1-0440-4bfa-8802-d4559e628c21
									  (alternative: OpenCellID/radiocells
										- They developed [their own network-based location service implementation](https://github.com/GrapheneOS/platform_packages_apps_NetworkLocation) (source code)
											- This is an alternative to Google Play Services network-based location services
										- Prior to Feb 2025 their OS geolocation service was not network-based, instead GNSS-A-GPS only
										- [[2025-02-28 Friday]] [Initial release](https://grapheneos.social/@GrapheneOS/114076777599414646)
											- This release adds an opt-in GrapheneOS network location client providing location detection **based on nearby Wi-Fi networks** using a local trilateration algorithm run on the device. It fetches a list of nearby Wi-Fi networks from Apple’s location service either directly or through a GrapheneOS proxy.
											- We’re in the process of building our own network location database based on scraping all of the cell tower and Wi-Fi data from Apple’s service. Scraping all the cell tower data is quick and will be easy to keep rapidly updated. A contributor scraped more than 2 billion Wi-Fi APs over 3 months.
											- This data isn’t copyrightable and Apple freely offers it without requiring authentication. It will be the initial basis for our database, but we’ll add other sources including an option to send us data from GrapheneOS devices. We’ll provide database downloads to support offline network location.
										- [[2025-03-04 Tuesday]] [Cell tower and offline support not here yet](https://grapheneos.social/@GrapheneOS/114099234319165119)
									- [SeedVault](https://github.com/GrapheneOS/os-issue-tracker/issues/1924)
								- _Will re-use existing FOSS_
									- CameraX (uses Android's CameraX API, instead of Open Camera app or AOSP Camera)
							- 2023 comparison table
							  collapsed:: true
								- ![image.png](../assets/image_1695459446636_0.png)
							- [Doesn't support Android Find My Device](https://discuss.grapheneos.org/d/11520-android-find-my-device-when-powered-off)
						- Comparisons
					- # Documentation
						- ## Installation
						  id:: 67290801-caaa-4f62-ade4-ab9fb82ca60e
							- Install a supported Chromium-based browser that's not in Snap or Flatpak
								- e.g. [Microsoft Edge DEB](https://www.microsoft.com/en-us/edge)
							- Open [Web Installer](https://grapheneos.org/install/web)
						- ## Setup
						  id:: 6729f0d1-74b9-4270-a9ac-64ddfe24eddc
							- ### Usage
								- [eSIM support](https://grapheneos.org/usage#esim-support)
								  i.e. Settings > Network & internet > eSIM support
									- Related: ((644c0acf-7f11-4ade-9b07-1812672b5ac4))
								- [Sandboxed Google Play](https://grapheneos.org/usage#sandboxed-google-play)
								  id:: 6729f6aa-f261-4257-8aab-f3db1be5e16a
								  collapsed:: true
								  Settings > Apps > Sandboxed Google Play
									- [Configuration](https://grapheneos.org/usage#sandboxed-google-play-configuration)
										- Optionally switch to Google's Network Location Service for higher accuracy and lower battery usage rather than just relying on GPS
										  id:: 6729fae7-094c-4af5-ac38-4685333f7490
											- Meta
												- It will send the nearby Wi-Fi and cellular networks provided via the Location and Nearby Devices permissions to their service to retrieve a location estimate
											- Play Services app info > Permissions
												- ((67326a69-1c9b-4cce-96df-8ca738553dee))
												- ((67326ac4-233c-4c4b-b2c6-9a32de408a9e))
												- ((67c0a0b5-4af4-41cb-8d14-828426b65191))
											- Geolocation
												- Disable `Reroute location requests to OS APIs`
												- Enable `Google Location Accuracy`
												- [[2025-02-27 Thursday]] Temporarily reversed these so I can test the new geolocation service
												  id:: 67c0a0b5-4af4-41cb-8d14-828426b65191
											- Android Settings > Location  > Location services
												- Enable `Wi-Fi scanning` and `Bluetooth scanning`
												- Related: ((672a4be6-8a69-40f9-8fd8-448d1d236843))
									- Google Play services
										- Permissions
											- `Location`: Precise; Allowed all the time
											  id:: 67326a69-1c9b-4cce-96df-8ca738553dee
												- Needed for ((6729fae7-094c-4af5-ac38-4685333f7490))
											- `Nearby Devices`: allowed
											  id:: 67326ac4-233c-4c4b-b2c6-9a32de408a9e
												- Needed for ((6729fae7-094c-4af5-ac38-4685333f7490))
									- Related: ((6730c86c-4c5d-4ab1-bb2c-710e8d89e73d))
								- [Storage Scopes](https://grapheneos.org/usage#storage-scopes)
								- [Contact Scopes](https://grapheneos.org/usage#contact-scopes)
									- This is enabled per-app
								- [LTE-only mode](https://grapheneos.org/usage#lte-only-mode)
									- If you have a reliable LTE connection from your carrier, you can reduce attack surface by disabling 2G, 3G and 5G connectivity in **Settings \> Network & internet \> SIMs \> SIM \> Preferred network type**
								- [Banking apps](https://grapheneos.org/usage#banking-apps)
									- Related: [App compatibility guide](https://discuss.grapheneos.org/d/8330-app-compatibility-with-grapheneos)
							- ### Features
								- [Sensors permission toggle](https://grapheneos.org/features#sensors-permission-toggle)
								  Settings > Security & privacy > More security & privacy
									- all other sensors not covered by existing Android permissions (Camera, Microphone, Body Sensors, Activity Recognition) including an accelerometer, gyroscope, compass, barometer, thermometer and any other sensors
									- Disable `Allow Sensors permission to apps by default`
										- You'll still receive a notification if an app tries to access it
								- [Duress PIN/Password](https://grapheneos.org/features#duress)
								  Settings > Security & privacy > Device unlock > Duress Password
								- Location Services
								  id:: 6730cbe0-e9d9-435a-908b-afba1637fd5f
								  Settings > Location > Location Services
									- ((6729fae7-094c-4af5-ac38-4685333f7490))
									- ((6730c86c-4c5d-4ab1-bb2c-710e8d89e73d))
									- ((672a4be6-8a69-40f9-8fd8-448d1d236843))
							- Related: ((649b13cd-71ac-45d5-8723-269f9c7cb15c))
						- ## Troubleshooting
							- Can't toggle `Usage access` or other special app access permission for an app
							  collapsed:: true
								- You need to open the App Info for that specific app then toggle that option by clicking the 3 dots in the upper right corner
							- Unknown tracker alerts
							  id:: 6730c86c-4c5d-4ab1-bb2c-710e8d89e73d
							  collapsed:: true
								- Meta
									- ((672a4be6-8a69-40f9-8fd8-448d1d236843))) is a more private alternative as it doesn't depend on sending data to Google
								- Go to ((6729f6aa-f261-4257-8aab-f3db1be5e16a))
									- Play services app info
										- Grant Location > Allow all the time; Nearby Devices
									- `Google settings`
										- All Services > Personal and device safety > Unknown tracker alerts
									- Turn on Bluetooth always or background Bluetooth scanning (Location > Location Services > Bluetooth scanning)
								- {Archive}
									- [No "Unknown tracker alerts" on GOS Android 14 - GrapheneOS Discussion Forum](https://discuss.grapheneos.org/d/9494-no-unknown-tracker-alerts-on-gos-android-14/3)
								-
						- Components
							- [Auditor](https://attestation.app)
							  id:: 644c0acf-58a1-4b82-9767-c88c65955315
							  collapsed:: true
							  Remote attestation / Hardware-based attestation / intrusion detection app for Android devices
								- It provides both local verification with another Android device via QR codes and optional scheduled server-based verification with support for alert emails. It uses hardware-backed keys and ((644c0acf-58a1-4b82-9767-c88c65955315)) support as the foundation and chains trust to the app for software checks.
								- [https://play.google.com/store/apps/details?id=app.attestation.auditor](https://play.google.com/store/apps/details?id=app.attestation.auditor)
								- [https://attestation.app](https://attestation.app)
								- [[Page not found · GitHub](https://github.com/GrapheneOS/Auditor](https://github.com/GrapheneOS/Auditor))
								- Related:
									- [[PC]] Linux status
										- [Reddit - Dive into anything](https://www.reddit.com/r/linux/comments/1115a9e/is_secure_boot_on_linux_useless_until_unified/)
										- distributions like Debian support Secure Boot, which is a form of verified boot for UEFI systems. Secure Boot ensures that only EFI programs signed with the correct key are executed, but it faces challenges in the boot process due to the need for each element in the chain to be verified
											- To fully implement verified boot in Linux, distributions would need to ensure that all parts of the boot process, including initrd, are signed and verified. This involves using tools and techniques like dm-verity or encryption to ensure that each element in the boot chain is what it should be.
												- ((67826b0d-8952-4cd4-8281-7c2dcae1cf7a)) : ((67c074c4-a262-43f4-a8a8-216c39d62680))
												- [Verified Boot](https://www.chromium.org/chromium-os/chromiumos-design-docs/verified-boot/) Chromium OS
												-
									- [Trusted Computing - Wikipedia](https://en.m.wikipedia.org/wiki/Trusted_Computing)
						- [Servers](https://grapheneos.org/articles/grapheneos-servers)
							- Attestation server - Canada
							- [GrapheneOS network servers](https://grapheneos.org/articles/grapheneos-servers#grapheneos.network) - Canada, USA Las Vegas, France, Singapore
						- _Includes several inbuilt solutions that would otherwise need root functionality_
						  collapsed:: true
							- [SeedVault](https://github.com/seedvault-app/seedvault)
							  id:: 6318fc65-99f9-4edb-a705-eb1deb420890
							  collapsed:: true
							  (app backup, alternative to Titanium Backup/OAndBackupX)
								- Pros/Cons
									- Pros
										- Doesn't require ((63209284-e6f8-47bd-a47c-e2733cf7b886))
										- Installed by default by multiple ROMs including ((63209286-6f40-4063-9fdc-2543251d416e)) and ((630f96f0-f2c4-4706-9d72-58e13201e03f))
										- Android 15 rework
										  collapsed:: true
											- [Experimental D2D transfer backups - allows ignoring the app setting that it specifically says it doesn't want to be backed up](https://github.com/seedvault-app/seedvault/issues/165#issuecomment-938077424)
											  id:: 649b13d0-fc6f-4ce9-a017-703c6e520cb9
											  collapsed:: true
												- [App developers should be told they can allow their app to only be backed up if encrypted](https://github.com/seedvault-app/seedvault/wiki/FAQ#why-do-some-apps-not-allow-to-get-backed-up)
													- It is not yet widely known that backups can now be encrypted with a device key and even [Google claims that it can not access backup data](https://security.googleblog.com/2018/10/google-and-android-have-your-back-by.html) [<a href="https://www.nccgroup.com/us/our-research/android-cloud-backuprestore/?research=Public+Reports">audit</a>]. Instead of opting out completely, app developers can say that their app <a href="https://developer.android.com/guide/topics/data/autobackup#define-device-conditions">should only get backed up, if the backup is encrypted</a>.
													- So if you are annoyed that your favorite app is not included in backups, you can contact the app's developers and make them aware of this option. For example, [this is](https://github.com/grote/Transportr/commit/4dc38f429f75909a088d8bd8a5b3b5ddd8030f71) how the Transportr app enabled only encrypted backups.
												- Related PRs
													- [[DO NOT MERGE] Initial support for backup of D2D-only apps by t-m-w · Pull Request #478 · seedvault-app/seedvault · GitHub](https://github.com/seedvault-app/seedvault/pull/478#issuecomment-1555345810)
													  id:: 6516c614-9bf3-419f-8cfc-2831792a717e
													- [Pretend to be a device to device transfer - fake-d2d by Uldiniad · Pull Request #473 · seedvault-app/seedvault · GitHub](https://github.com/seedvault-app/seedvault/pull/473#event-8396955648)
													- [Add experimental support for forcing D2D transfer backups by stevesoltys · Pull Request #562 · seedvault-app/seedvault · GitHub](https://github.com/seedvault-app/seedvault/pull/562#event-10460712712)
													-
											- App data deduplication to reduce backup size
												- we new only keep 3 daily snapshots and 2 weekly ones (one from this and one from last week). Anything older than this gets cleaned up automatically after each backup run.
											- [Scheduling system rework to prevent backups failing](https://github.com/seedvault-app/seedvault/pull/628)
											- [Ability to restore specific apps](https://github.com/seedvault-app/seedvault/issues/309)
											  collapsed:: true
												- #+BEGIN_TIP
												  You can trigger the setup wizard restore, which will try to restore all apps back to the lack backup point
												  #+END_TIP
												- For documentations' sake, if you know what you are doing and accept the risks, you can start a restore without SetupWizard or debug build with adb:
													- `adb shell am start-activity -a com.stevesoltys.seedvault.RESTORE_BACKUP`
												- Alternatively can trigger the standard setup wizard restore using the dialler: `*#*#RESTORE#*#*` aka `*#*#7378673#*#*`
									- Cons
										- [Doesn't grant runtime permissions after restore](https://github.com/seedvault-app/seedvault/issues/773)
										- [Several missing bits](https://gitlab.com/CalyxOS/calyxos/-/issues/2917#note_2279826526)
										- Lacks
											- [Show size of last backup](https://github.com/seedvault-app/seedvault/issues/362)
											- [Can't backup system apps](https://github.com/seedvault-app/seedvault/issues/142)
											- [No flashable ZIP yet, must use custom ROMs like GrapheneOS or LineageOS](https://github.com/seedvault-app/seedvault/issues/9#issuecomment-1806897959)
											- [Remote backup in-built](https://github.com/seedvault-app/seedvault/issues?q=is%3Aopen+sort%3Areactions-%2B1-desc+label%3A%22%F0%9F%97%84%EF%B8%8F+storage%22) (though I use Syncthing for this)
											- [Backup restore management](https://github.com/seedvault-app/seedvault/issues/100#event-14386001246)
										- [It can't backup some apps until you manually start them](https://github.com/seedvault-app/seedvault/wiki/FAQ#why-do-apps-not-get-backed-up-when-not-recently-used) - OS-level feature
										- ((63209286-6f40-4063-9fdc-2543251d416e)) - [last update to Seedvault in Oct 2024](https://grapheneos.org/releases) (search page for "seedvault"). GOS maybe once a year only updates this dependency
										  id:: 67100df6-de3d-4ea0-929d-f0fc1a0b7afa
									- Unclear
									- Comparisons
										- ((63216f53-22cf-428a-9193-e5a423158e2b))
								- See passwords for recovery passphrase
								- What makes this different?
								  collapsed:: true
									- This application is compiled with the operating system and does not require a rooted device for use.
									- It uses the same internal APIs as adb backup which is deprecated and thus needs a replacement.
								- # Documentation
									- Stored in `/.SeedVaultAndroidBackup/` hidden dir on SD card
									- Trigger a system restore post-setup wizard
										- [On GrapheneOS at least it's also available under the 3 dot menu as `Restore backup`](https://github.com/GrapheneOS/os-issue-tracker/issues/4311)
										- through a dialer code `*#*#7378673#*#*` or vanity number `*#*#RESTORE#*#*`. It allows [restoring only specific apps](https://github.com/seedvault-app/seedvault/pull/670)
										- How to trigger a restore
										  `adb shell am start-activity -a com.stevesoltys.seedvault.RESTORE_BACKUP`
											- [FAQ · seedvault-app/seedvault Wiki · GitHub](https://github.com/seedvault-app/seedvault/wiki/FAQ#how-to-restore-after-passing-through-setup-wizard)
									- You can restore using an existing seed phrase + backup by clearing the app data. In android show all apps, show system apps, then clear data of Seedvault
								- Backup
								  collapsed:: true
									- Misc
										- SMS text messages
										- Device settings
										- Call history
									- Didn't do local contacts
									- App doesn't allow backup
										- AFWall+ (Donate
										- Alarm Klock
										- AndStatus
										- App Manager
										- Apple UnifiedNlp Backend
										- AppyParking
										- Barclays
										- Bolt
										- Brave
										- See [Briar](https://workflowy.com/#/7f8fcb8c2496)
										- Bromite
										- CamScanner
										- Coinbase
										- ((644c0acd-6179-4a8f-aa56-bab5f8a46b39))
										- Dayuse
										- Delta
										- ((663b24fb-e901-4314-abf8-6f0c529ade12))
										- See [Discord](https://workflowy.com/#/776244a9838b)
										  #Software-Chat
										- DroidFS
										- DUSK
										- Element
										- Eventbrite
										- Exodus
										- FastHub
										- Fedilab Lite
										- ((649b13ce-166b-43de-bea7-4262b566ccce))
										- Firefox
										- Firefox Nightly
										- FlorisBoard
										- Foxit PDF
										- G-Droid
										- GamerLink
										- GitHub
										- GoFantastic
										- Grasshopper
										- Groupon
										- GSM Location Service
										- Hinge
										- Houseparty
										- ICSx
										- ((654cbb47-7dca-4be3-9b27-e59d32b68f16))
										- Ihateironing
										- Imgur
										- Instagram
										- Just Eat
										- See [K-9 ](https://workflowy.com/#/30959deb9ab6)<a href="https://workflowy.com/#/30959deb9ab6">Mail</a>
										- ((63a9ade4-acd5-44f9-9166-2c1393865f7a))
										- LabCoat
										- Laundrapp
										- Ledger Live
										- Linphone
										- Magisk
										- Maps
										- Mimo
										- Morrisons
										- Mozilla VPN
										- MX Player
										- Nekogram X
										- Netflix
										- ((649b13cf-caf2-4248-adbb-6e642bd536d9))
										- Notion
										- Nova Launcher + ((649b13ce-a3a4-4d76-8185-c6a99207b002))
										- OpenContacts
										- OpenKeychain
										- Oversec
										- Revolut
										- Shazam
										- Shelter
										- Signal
										- Skype
										- Sky Go
										- Smarter Time
										- Speedtest
										- ((64f5d195-048b-4532-86da-5e3fa35b3d2c))
										- Status
										- StreetComplete
										- Syncthing + Fork
										- ((644c0acd-786d-4030-8a84-c8b275a6e053))
										-
										- Tesco Groceries
										- TicketMaster
										- TimeLimit
										- Todoist
										- ((644c0b17-c25b-493f-ba37-b254cc6f2e21))
										- TrackerControl
										- Transportr
										- Trips
										- Uber
										- UntrackMe
										- UptimeRobot
										- Vyke
										- WebApps
										- ((63ff8189-440c-460c-904e-72d2227e81fc))
								- Extra tools
								  collapsed:: true
									- The [Seedvault backup parser](https://github.com/tlambertz/seedvault_backup_parser) allows you to decrypt and inspect your backups. It can also re-encrypt them.
								- Related: ((6318fc64-68b1-45e2-a20d-c92068e956af))
							- Internet permission toggle (replaces ((649b13cf-a724-4193-93dd-3f200c359a0d)) )
							- _Other current root apps_
								- ((649b13cf-d6ff-4267-9a99-c559649eee01))
								- TWRP custom recovery for nandroid backups
								- Related: ((644c0acc-4506-4afb-87dc-4413f76e7079))
							- _Related:_
								- ((6306a77a-3999-4fd1-99dd-630a77dd542c))
						- Custom build that allows ((649b13cd-e6ad-4655-91b6-5dcdce92aaed)) root
						  id:: 65193b42-39f7-4774-a8d9-bed08bd5f6f6
						  collapsed:: true
							- Instructions from Discord
								- Is there anyone in here who is interested in a solution to a permanent root through OTA updates with a locked bootloader for stock Android and custom ROM's?
								- prebuilt virtual machine with all tools required to do it available for those interested
								  This is development, so here goes:
								  Hello everyone! I made this discovery, and I elected to make my phone the guinea pig for this experiment before publishing this to the masses, in order to endure that this was both safe and effective before releasing this information to everyone. Now, this comes with a few warnings:
								- Second. NEVER, EVER, EVER, DISABLE OEM UNLOCKING IF YOU DO THIS!!! Doing so will zero out your recovery and more, making your phone unrecoverable and a permanent brick. No going back.
								  With that out of the way... here we go!
								- First, go here and download the virtual machine that was so kindly built by the creator of the ((65193e34-8c19-4a3a-9c4b-adba11e09476)) tool:
								- [https://mega.nz/file/BmYQWKwD#7HihEJh5RzdGzjcVi2Bfzf3-aUfpKNMy5WRrCWYf0zY](https://mega.nz/file/BmYQWKwD#7HihEJh5RzdGzjcVi2Bfzf3-aUfpKNMy5WRrCWYf0zY)
								- Original forum posting where link was found:
								- [https://forum.xda-developers.com/t/guide-to-lock-bootloader-while-using-rooted-grapheneos-magisk-root.4510295/page-4#post-88366269](https://forum.xda-developers.com/t/guide-to-lock-bootloader-while-using-rooted-grapheneos-magisk-root.4510295/page-4#post-88366269)
									- **\*UPDATED\*\*** to latest and minimal release of Ubuntu (small footprint) and latest avbroot tool version (many bug-fixes and improvements)\*
									- I've made linux virtual machine for VirtualBox 7.0 in OVA format, so you
									  may use tool on any host OS supported by VirtualBox and have guaranteed
									  working environment without messing host system with all of these
									  dependencies and complex development stuff.
									- [[Download link](https://mega.nz/file/BmYQWKwD#7HihEJh5RzdGzjcVi2Bfzf3-aUfpKNMy5WRrCWYf0zY)]
									- Also I've written [instruction](https://mega.nz/file/sz5xQQjT#ds42D4PMGlt6Kx5Vsfc7bAxFOyxdctX5i0GMh-45YM4) how I've "built" this VM "from sources", so you may reproduce it and get trusted one. ![:)](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)
									  Login credentials: user '_ubuntu_' and password '_ubuntu_' (may be connected by ssh via network - don't forget setup networking in VM settings and virtualbox/host).
									- It's based on [Ubuntu 22.10 Minimal cloud image](https://cloud-images.ubuntu.com/minimal/releases/kinetic/release-20230323/) with avbroot tool sourced from [git repository](https://github.com/chenxiaolong/avbroot) (commit 0fff7b77dd284e99da4282a5c12a8aab802480f0) and placed in ~/avbroot directory.
									- Follow instructions in avbroot [README.md](https://github.com/chenxiaolong/avbroot/blob/0fff7b77dd284e99da4282a5c12a8aab802480f0/README.md) while skipping 'Installing dependencies' section, 'Usage' steps 2,3 and replacing `python ...` invokations with `python3 ...`. To access host file system add VM shared folder (with _auto-mount_ checked, empty _mount point_). Files in _folder path_ are accessed with prefix /media/sf\_<_folder_name>_/ from guest.
									- Example usage (when files are located at '/home/artem/Documents'
									  directory on Linux host and shared folder with path '/home/artem' and
									  name 'artem' added to VM):
									- ```bash
									  cd ~/avbroot
									  python3 avbroot.py patch --input /media/sf_artem/Documents/bluejay-ota-tq1a.230105.001.a2-deb3f832.zip --privkey-avb /media/sf_artem/Documents/avb.key --privkey-ota /media/sf_artem/Documents/ota.key --cert-ota /media/sf_artem/Documents/ota.crt --magisk /media/sf_artem/Documents/Magisk-v25.2.apk
									  ```
									- Notes:
										- I've did my best to achieve as small footprint as possible. Imported VM takes up ~1.0GB on hard drive right after importing. After full cycle of working with Google Pixel 6a stock OTA VM growed up to ~1.2GB due to temporary files created during process. Size may vary depending on OTA files used. (You may try to use separate VM shared folder to place guest temporary dir on host.)
										- Don't decrease VM RAM to 512MB. I've tried - it's a devil. Because it looks like everyting working ok, but you may not notice that some procedure within script executing failed (due to memory allocation error), but script didn't aborted and just resulted in wrong content in generated output, so you may face this problem later (to be found at very end after flashing, etc... - rooting not working or something like that).
										- You may change disk medium type to immutable (in virtualbox media manager) which makes VM to automatically reset to initial state and size on each power on (i.e. loosing all system changes you made and data inside VM since point, at which you changed type). Note, that it happens at power ON, not off! It's convenient as long as you keep all your data on host and using VM only as execution environment.
										- By default VM isn't connected to any network. You may enable network adapter in VM settings to access internet from guest or work via ssh. If you select NAT network, then it already contains port forwarding rule on 2222 tcp port for ssh'ing, but you may need to change guest IP in rule to match address, actually assigned by vbox to your VM instance in your setup (login to started guest, type ifconfig and find address of form '10.0.X.X' in command output). On linux host connect from terminal using command ssh -p 2222 ubuntu@localhost.
								- You will need to use this virtual machine to build the custom keys. Best instructions I could find are here:
								- Detailed instructions with commands, substitute "bramble" with your model/board:
								- [https://forum.xda-developers.com/t/guide-to-lock-bootloader-while-using-rooted-grapheneos-magisk-root.4510295/page-3#post-88285795](https://forum.xda-developers.com/t/guide-to-lock-bootloader-while-using-rooted-grapheneos-magisk-root.4510295/page-3#post-88285795)
								  https://drive.google.com/drive/folders/15zGvZHCeQTpo9wPLAFVajDyV7ppaxIeQ?usp=sharing
								- [message.txt](../assets/message_1696152514517_0.txt)
				- CalyxOS
				  id:: 649b13d0-bf0d-4357-82c5-c3e1ffc28138
				  collapsed:: true
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Supports [microG](https://workflowy.com/#/5b760a9e66c3) built-in, and has additional security over <a href="https://workflowy.com/#/1abc0e737ad8">Lineage for microG</a>
							- Includes Datura Firewall
								- [https://calyxos.org/docs/tech/datura-details/](https://calyxos.org/docs/tech/datura-details/)
						- Cons
							- Only supports Pixel devices?
						- Unclear
							- Includes [microG](https://workflowy.com/#/5b760a9e66c3)
							- CalyxOS supports Fairphone 4
								- [https://calyxos.org/news/2022/04/01/fairphone4-oneplus8t-oneplus9-test-builds/](https://calyxos.org/news/2022/04/01/fairphone4-oneplus8t-oneplus9-test-builds/)
								- 1 Backlink
									- See [CalyxOS supports Fairphone 4](https://workflowy.com/#/9fbd965e808e)
					- Supports verified boot, like GrapheneOS
					- Doesn't have all the security hardening patches of GrapheneOS
					- Heard of it, used it, liked it, recommended it, even ran into the developers a few times.
					- It's not perfect, but it's more usable than GrapheneOS for most people and it's more freedom oriented than iOS. It doesn't have the privacy features of GrapheneOS or iOS, but it's reasonable. It's much better than running Lineage/MicroG
					- 1 Backlink
					  collapsed:: true
						- Basically requires you to use stock OS or a security-focused ROM like GrapheneOS or [Calyx](https://workflowy.com/#/419015786f9e)<a href="https://workflowy.com/#/419015786f9e">OS</a> without root etc
						  source:: [https://teddit.net/r/LineageOS/comments/n7yo7u/a_discussion_about_bootloader_lockingunlocking/](https://teddit.net/r/LineageOS/comments/n7yo7u/a_discussion_about_bootloader_lockingunlocking/)
				- DivestOS
				  collapsed:: true
					- [https://github.com/privacyguides/privacyguides.org/discussions/58](https://github.com/privacyguides/privacyguides.org/discussions/58)
					- Pros/Cons
						- Pros
							- Soft-fork of LineageOS
							- _Improvements over LineageOS_
								- automated kernel CVE patching, proprietary blob removal, delta OTA updates, signed releases, verified boot, and a realtime malware scanner (hypatia).
						- Cons
							- Supports verified boot with many devices, however this is incompatible with rooting
				- /e/
				- OmniROM
				  collapsed:: true
					- https://www.omnirom.org
					- Supports microG out of the box
				- Paranoid Android
				  collapsed:: true
					- http://www.paranoidandroid.co/
				- Fairphone Open
				- Related: Libre ((644c0acf-d47e-4c38-89f9-3181dc76c6c4)) ie ((644c0acf-e4e0-46a9-b103-ad20b97d8c09))
			- Non-Android
				- ((644c0ace-85e1-472b-8dd8-81766029ec97))
				- Sailfish OS
				  collapsed:: true
				  Not yet libre UI
					- [https://sailfishos.org/](https://sailfishos.org/)
					- Pros/Cons
						- Pros
							- Can run Debian like an app
								- Based on LXC container tech
						- Cons
							- Android compatibility layer only legal with their licensed phones?
					- Sailfish OS (also styled as SailfishOS[4] or abbreviated to SFOS) is a mobile operating system combining the Linux kernel for a particular hardware platform use, the open-source Mer core middleware, a proprietary UI contributed by Jolla, and other third-party components
					  https://en.wikipedia.org/wiki/Sailfish_OS
					- Highly gesture-oriented
					- Can run Android apps
					  Built-in Alien Dalvik plays the role of an Android compatibility layer. It emulates, but does not simulate, Android OS
					- Application Manager window allows you to see multiple apps open and running simultaneously
					  App Switcher in Android
					- Devices
						- Ported to several Android phones
						- Jolla phone
						  https://jolla.com/jolla/
						- Fairphone 2
					- Reviews
						- https://www.youtube.com/watch?v=lP_opXBWZzc
					- Not entirely open-source
					  https://reviewjolla.blogspot.co.uk/p/sailfish-os-open-source-licencing-stage.html
				- ((649b13d0-64a3-4e77-8663-91a1aa71f20e))
				- ((649b13d0-25c0-41d7-aba8-d874673b3711))
				- ((649b13d0-98eb-4868-a381-a95fabd64a2d))
		- ### Fully Libre
			- Meta
				- Getting non-Android OS to work on mobile devices
					- Action of porting is adjusting OS to a device so that every feature works, unlike desktop, where thanks to ACPI and drivers and generalized hardware stuff generally just works. Phones are not really generalized hardware and each has its quirks so it needs a wee bit of work.
					- FSF is doing the Librephone project to reverse engineer these drivers
			- _Android-based ROMs_
			  id:: 644c0acf-d47e-4c38-89f9-3181dc76c6c4
				- [Replicant](https://www.replicant.us/)
				  id:: 644c0acf-e4e0-46a9-b103-ad20b97d8c09
				- Related: Mostly libre ((649b13d1-a8c5-4f57-b5a7-d505dd2c6f2a)) e.g. ((630f96f0-f2c4-4706-9d72-58e13201e03f))
		- Proprietary
		  collapsed:: true
			- iOS
			  id:: 63734d36-430f-4369-9137-f51c908a89ad
				- ((63208fd2-65bc-4405-a355-1239401f84ab))
				- Pros/Cons
				  collapsed:: true
					- Pros
						- See [AppTrackingTransparency](https://workflowy.com/#/e4dafed73a56)
						- They often have better cameras
							- (though Pixel 2, let alone 3 is better in 2018)
						- Stock Android is far more privacy-invasive
							- (though LineageOS with no GApps is pretty good privacy-wise)
					- Cons
						- Poor privacy
						  collapsed:: true
							- They are decent about keeping your data private from advertisers, but not from government
								- They were part of PRISM
								- They have to share data in EU
								- They share data in China
								- [https://protonvpn.com/blog/apple-blocks-app-updates/](https://protonvpn.com/blog/apple-blocks-app-updates/) "When Myanmar needs ProtonVPN the most, Apple stands in the way of human rights" -While Proton is focusing on themselves specifically, I suspect they are not the only ones. -Apple blocked a ProtonVPN update because of their description in which they admit to being useful to "challenge governments." Apple has a history of putting profit over human rights.
							- They have implemented client-side scanning for child abuse images
							  [https://news.ycombinator.com/item?id=28068741](https://news.ycombinator.com/item?id=28068741)
								- Why
									- It allows them to work with authoritarian governments under the pretext that the tech they use was developed for terorrism or CP. So it begins with this shit in the USA, but conveniently allows them to work with China and scan for images of Winnie the Pooh on all iPhones in Beijing. Thus profiting Apple since they can keep selling their products in China without incurring the wrath of the CCP.
								- In their (very influential) opinion, it is safe to build systems that scan users’ phones for prohibited content.
								- Problems
									- It allows any government to abuse this technology
										- Example 1
											- US Government: We suspect the person in this photo of committing a crime. Here is your subpoena, Apple. You are directed to scan all iPhone and iCloud storage for any pictures matching this NeuralHash and report to us where you find them.
											- Chinese Government: Here is the NeuralHash for Tienanmen square. Delete all photos you find matching this or we will bar you from China.
										- example 2
											- Chinese Government: Here is the NeuralHash for some child abuse imagery, please scan this user's phone and tell us if it's found.
											- Apple: Sure we found it.
											- Chinese Government: this user has unpermitted winnie the pooh memes. Send them to an internment camp.
									- It's already known that Apple has to use servers operated by China for their operations there [1] so this capability will be fully within their hands now too to arbitrarily censor and report iPhone users for any material they want to disallow
									  [https://www.businessinsider.com/apple-data-china-censors-apps-nyt-2021-5?op=1&r=US&IR=T](https://www.businessinsider.com/apple-data-china-censors-apps-nyt-2021-5?op=1&r=US&IR=T)
										- That’s not a slippery slope; that’s a fully built system just waiting for external pressure to make the slightest change.
											- All it would take to widen the narrow backdoor that Apple is building is an expansion of the machine learning parameters to look for additional types of content, or a tweak of the configuration flags to scan, not just children’s, but anyone’s accounts. That’s not a slippery slope; that’s a fully built system just waiting for external pressure to make the slightest change. Take the example of India, where recently passed [rules](https://www.eff.org/deeplinks/2021/07/indias-draconian-rules-internet-platforms-threaten-user-privacy-and-undermine) include dangerous requirements for platforms to identify the origins of messages and pre-screen content. New laws in Ethiopia requiring content takedowns of “misinformation” in 24 hours <a href="https://www.accessnow.org/ethiopias-hate-speech-and-disinformation-law-the-pros-the-cons-and-a-mystery/">may apply to messaging services.</a> And many other countries—often those with authoritarian governments—have <a href="https://www.eff.org/deeplinks/2021/02/indonesias-proposed-online-intermediary-regulation-may-be-most-repressive-yet">passed</a> <a href="https://www.eff.org/deeplinks/2020/11/turkey-doubles-down-violations-digital-privacy-and-free-expression">similar</a> <a href="https://www.eff.org/deeplinks/2021/04/proposed-new-internet-law-mauritius-raises-serious-human-rights-concerns">laws</a>.
											- Apple’s changes would enable such screening, takedown, and reporting in its end-to-end messaging. The abuse cases are easy to imagine: governments that outlaw homosexuality might require the classifier to be trained to restrict apparent LGBTQ+ content, or an authoritarian regime might demand the classifier be able to spot popular satirical images or protest flyers.
											- We’ve already seen this mission creep in action. One of the technologies originally built to scan and hash child sexual abuse imagery has been repurposed to create a [database of “terrorist” content](https://www.eff.org/deeplinks/2020/08/one-database-rule-them-all-invisible-content-cartel-undermines-freedom-1) that companies can contribute to and access for the purpose of banning such content. The database, managed by the <a href="https://gifct.org/">Global Internet Forum to Counter Terrorism</a> (GIFCT), is troublingly without external oversight, despite <a href="https://cdt.org/insights/human-rights-ngos-in-coalition-letter-to-gifct/">calls from civil society</a>. While it’s therefore impossible to know whether the database has overreached, we do know that platforms <a href="https://www.eff.org/wp/caught-net-impact-extremist-speech-regulations-human-rights-content">regularly flag critical content</a> as “terrorism,” including documentation of violence and repression, counterspeech, art, and satire.
										- Highest likelihood content for government scanning:
											- Confidential government documents
											- Piracy
											- Wrongthink e.g. covid "misinformation"
											- Certain types of porn
											- LGBT content if in a content which bans it
											- Tax avoidance and cryptocurrency
									- Combined with Pegasus zero-click hacking, this allows anybody who buys the NSO Group's spyware to plant evidence and then have their phone automatically report on them. I can't imagine a more horrifying way that is so freely available to put anyone in jail at any time.
										- This will go great with zero-click iMessage exploits like this one: [https://9to5mac.com/2021/07/19/zero-click-imessage-exploit/](https://9to5mac.com/2021/07/19/zero-click-imessage-exploit/)
											- https://www.sciencefocus.com/future-technology/pegasus-a-cyber-security-expert-explains/
											- Edit: Actually, this won't even require an exploit if they also scan media for people who have enabled "iMessage in iCloud".Just send someone an image in the DB (or an image that's been engineered togenerate a false positive) and wait for them to get raided.
									- Australia ruling that naked cartoon children count as actual child porn. [1]
									  [https://arstechnica.com/tech-policy/news/2010/01/simpsons-powerpuff-girls-porn-nets-jail-time-for-australian.ars](https://arstechnica.com/tech-policy/news/2010/01/simpsons-powerpuff-girls-porn-nets-jail-time-for-australian.ars)
										- It's perfectly legal elsewhere (if a bit weird) to have some Simpsons/whatever mash-up of sexualised images, but if I flew on a plane to the land down under, would I then be flagged?
											- edit: If this is scanning stuff on your phone automatically, and you have whatsapp or whatever messenger set to save media automatically, then mass texting an image that is considered 'normal' in the sender country, but 'bad' in the recipients, you could get a lot of people flagged just by sending a message.
							- Most of the the data they collect is not end-to-end encrypted
							  source:: [https://support.apple.com/en-us/HT202303](https://support.apple.com/en-us/HT202303)
								- Non E2EE:
									- Backup, Safari History & Bookmarks, Calendars, Contacts, Find My (Devices & People), iCloud Drive, Messages in iCloud, Notes, Photos, Reminders, Siri Shortcuts, Voice Memos, Wallet passes, [iCloud.com](http://iCloud.com), Mail
								- E2E data:
									- Apple Card transactions (requires iOS 12.4 or later)
									- Home data
									- [Health data](https://support.apple.com/en-us/HT202303#health) (requires iOS 12 or later)
									- iCloud Keychain (includes all of your saved accounts and passwords)
									- Maps Favorites, Collections and search history (requires iOS 13 or later)
									- Memoji (requires iOS 12.1 or later)
									- Payment information
									- QuickType Keyboard learned vocabulary (requires iOS 11 or later)
									- Safari History and iCloud Tabs (requires iOS 13 or later)
									- Screen Time
									- Siri information
									- Wi-Fi passwords
									- W1 and H1 Bluetooth keys (requires iOS 13 or later)
							- No open-source software because GPL is incompatible with the iOS store license
								- e.g. GnuCash, Electrum
							- No permission management via LineageOS Privacy Guard, [AFWall](https://workflowy.com/#/e5f2eed18186), XPrivacyLua
							- No AdAway ad blocker
							- No Orbot or ((644c0b17-c25b-493f-ba37-b254cc6f2e21))
							- iMessage is not meaningfully E2EE
							  source:: [https://mjtsai.com/blog/2021/01/14/reminder-imessage-not-meaningfully-e2e/](https://mjtsai.com/blog/2021/01/14/reminder-imessage-not-meaningfully-e2e/)
							- Other
								- Can't open encrypted VeraCrypt containers
							- They collect all the same data Google and others do
							  source:: [https://youtu.be/r38Epj6ldKU](https://youtu.be/r38Epj6ldKU)
								- Their Privacy Policy is bad
								  [apple.com/legal/privacy](http://apple.com/legal/privacy)
								- [https://support.apple.com/en-us/HT205223](https://support.apple.com/en-us/HT205223)
							- Their AppTrackingTransparency makes their own apps look better because "it's not data shared with third parties" and they count themselves as the 1st party
						- No custom launchers
						- No Android for Work dual apps
						- No [Titanium](https://workflowy.com/#/15c43e198c80)<a href="https://workflowy.com/#/15c43e198c80"> Backup</a> or nandroid backups
						- Automation like Tasker doesn't exist
						- Rooting/jailbreaking is extremely difficult
						- All app developers are forced to pay 30% and use their payment architecture
						  collapsed:: true
							- (eg see Librem Tunnel leaving the iOS store, Fortnite with Epic v Apple case etc)
						- Cannot choose the default application for various tasks
						  collapsed:: true
							- For example, using a different email client, Twitter client, or Reddit client.
						- I cannot use contact groups for anything
						  collapsed:: true
							- I cannot (easily) place contacts into groups, or use groups to make decisions about who I’m communicating with.
						- etc
						  collapsed:: true
							- iPhone [does not allow you to have privacy](https://gist.github.com/iosecure/357e724811fe04167332ef54e736670d) due to its blackbox nature, and is simply a false marketing assurance by Apple to you. Recently, an unpatchable hardware flaw was [discovered](https://9to5mac.com/2020/08/01/new-unpatchable-exploit-allegedly-found-on-apples-secure-enclave-chip-heres-what-it-could-mean/) in Apple's T1 and T2 "security" chips, rendering Apple devices critically vulnerable.
							- Also, [they recently dropped plan for encrypting iCloud backups after FBI complained](https://www.reuters.com/article/us-apple-fbi-icloud-exclusive/exclusive-apple-dropped-plan-for-encrypting-backups-after-fbi-complained-sources-idUSKBN1ZK1CT). They also collect and sell data [quite a lot](https://i.imgur.com/n8Bk0bA.jpg). Siri still records conversations 9 months after Apple [promised not](https://www.theregister.co.uk/2020/05/20/apple_siri_transcriptions/) to do it. Apple Mail app is vulnerable, yet Apple stays in [denial](https://9to5mac.com/2020/04/27/iphone-mail-vulnerabilities-2/).
							- Also, [Apple sells certificates to third-party developers that allow them to track users](https://www.theatlantic.com/technology/archive/2019/01/apples-hypocritical-defense-data-privacy/581680/), [The San Ferdandino shooter publicity stunt was completely fraudulent](https://www.aclu.org/blog/privacy-technology/internet-privacy/one-fbis-major-claims-iphone-case-fraudulent), and [Louis Rossmann dismantled Apple's PR stunt "repair program"](https://invidio.us/watch?v=rwgpTDluufY).
							- [Apple gave the FBI access to the iCloud account of a protester **accused** of setting police cars on fire](https://www.businessinsider.com/apple-fbi-icloud-investigation-seattle-protester-arson-2020-9).
							- [Apple's authorised repair leaked a customer's sex tape during iPhone repair.](https://www.youtube.com/watch?v=xt3YSD36ZNc) This is how much they respect your privacy. You want to know how much more they respect your privacy? Apple's Big Sur(veillance) fiasco seemed [not enough](https://teddit.bus-hit.me/r/privatelife/comments/jvdokk/), it seems. Still not enough to make your eyes pop wide open?
							- Apple's CSAM mandatory scanning of your local storage is a fiasco that will echo forever. This blog [article](https://www.hackerfactor.com/blog/index.php?%2Farchives%2F929-One-Bad-Apple.html) should be of help. But they [lied](https://www.icenterpro.eu/apples-csam-system-was-hacked-but-the-firm-claims-it-is-protected/) how their system was never hacked. I [doubt](https://teddit.bus-hit.me/r/MachineLearning/comments/p6hsoh/). They even [removed CSAM protection references](https://www.macrumors.com/2021/12/15/apple-nixes-csam-references-website/) off of their website for some reason.
							- Pretty sure atleast the most coveted privacy innovation of App Tracking protection with one button tracking denial would work, right? [Pure. Privacy. Theater.](https://www.yahoo.com/news/former-apple-engineer-says-button-164452709.html)
							- Surely this benevolent company blocked and destroyed Facebook and Google's ad network ecosystem by blocking all those bad trackers and
							  ads. Sigh. [Nope.](https://twitter.com/PatrickMcGee_/status/1449608262492459011) Now it is just Apple having monopoly over your monetised data.
							- Also, Android's open source nature is starting to pay off in the long run. Apple 0-day exploits are far [cheaper](https://www.wired.com/story/android-zero-day-more-than-ios-zerodium/) to do than Android.
					- Unclear
						- AppTrackingTransparency
						  collapsed:: true
						  AKA App Tracking Trasparency / Privacy Labels
							- Pros/Cons
								- Pros
									- Not
								- Cons
									- Not that effective
							- Website
							  [https://www.apple.com/privacy/labels/](https://www.apple.com/privacy/labels/)
							- Example app
							  [https://apps.apple.com/gb/app/whatsapp-messenger/id310633997](https://apps.apple.com/gb/app/whatsapp-messenger/id310633997)
							- See their ads for it [Apple privacy ads](https://workflowy.com/#/170bc828671b)
							- 3 Backlinks
								- See [AppTrackingTransparency](https://workflowy.com/#/e4dafed73a56)
								- iOS - enable [AppTrackingTransparency](https://workflowy.com/#/e4dafed73a56)
								- Check [AppTrackingTransparency](https://workflowy.com/#/e4dafed73a56) for proprietary apps
					- {Archive}
					  collapsed:: true
						- Old cons
							- iOS used to not have
								- FOSS VPN (now has Wireguard)
								- Bitcoin wallets
							- Android phones allow removable batteries, removable SD cards, aux/headphone port - now Pixel and other flagships don't have this
				- Searching the app store online
				  collapsed:: true
					- [https://fnd.io/](https://fnd.io/)
					- [https://theappstore.org](https://theappstore.org)
				- Related: ((63734d16-48e6-44c2-a290-2e41a5927244))
		- Convergent OS
		  id:: 631fa93c-fd77-4435-a292-fd9573d0242f
		  collapsed:: true
		  AKA Convergent Operating Systems
		  #ConvergentOS
			- Pros/Cons
			  collapsed:: true
			  Compared to normal desktop OS
				- Pros
					- Enables gestures
					- Many apps are more limited or don't exist on mobile operating systems
					- Android is getting more limited
					  #Phone https://workflowy.com/#/df191e8d9e26
				- Cons
					- No mouse
					- Many browser add-ons are built for desktop version
			- ### Convergence I wish I had
				- [[2025-09-26 Friday]] ideas
					- *Can bolved by Logseq DB mode and RTC sync*
						- Desktop Logseq access on mobile
					- Desktop Firefox access on mobile
					- Desktop Calibre access on mobile
						- Mainly because it could replace ((651ad907-9c59-4259-b50d-553ee5778684))
					- Desktop FreeTube access on mobile
					- Desktop TTRSS access on mobile - better UX for mobile app
					- *Already solved by scrcpy virtual display*
						- ((659b8ecc-2e3b-44fd-98f2-03df02214fb8))
						- ((687014ae-e32c-403a-9480-b7db4010dcf1))
						- ((684cafb8-a7d6-47b9-a012-fcefe01569d8))
			- Best approaches
			  it either needs to use emulation, virtualisation or the software has to be compiled for both ARM+x86
				- Convergence 1.0 - use desktop as a display monitor for mobile
				  collapsed:: true
				  Being able to plug a monitor, keyboard and mouse into smartphone and use it as a full-fledged desktop replacement
					- _Approach done by_
						- ((63a9ade4-0cdf-4680-a839-6b6f92e57f51)) : ((670be97c-236d-42e0-a498-acd0fcb2dc48))
						- Running Linux from Android eg
						  collapsed:: true
							- See [Samsung](https://workflowy.com/#/111d9f1b3f69)<a href="https://workflowy.com/#/111d9f1b3f69"> </a><a href="https://workflowy.com/#/111d9f1b3f69">DeX</a>
						- Android multi-tasking launchers
						  collapsed:: true
							- Taskbar
								- Pros/Cons
								  collapsed:: true
									- Pros
										- You can setup Taskbar as home launcher, and your own launcher eg Nova as primary launcher
									- Cons
										- The biggest downside to desktop mode on Android right now is the limited app support for larger screens or foldables
								- [https://github.com/farmerbb/Taskbar/](https://github.com/farmerbb/Taskbar/)
								- Features
								  collapsed:: true
									- Taskbar is an open-source Android app that puts a floating start menu and recent apps tray on top of any screen
									- Supports launching Android apps in freeform multi-window when plugging into an external monitor
								- Changelog
								  [https://github.com/farmerbb/Taskbar/blob/master/CHANGELOG.md](https://github.com/farmerbb/Taskbar/blob/master/CHANGELOG.md)
								- Documentation
								  collapsed:: true
									- Installing
										- You can download Taskbar 6.0 from the Google Play Store link below or compile the app from its source code on GitHub. The app is totally free to use, but there’s a $1.99 donate version in case you want to support farmerbb’s development efforts.
									- Setting up Taskbar’s desktop mode is quite easy:
									  source:: [https://www.xda-developers.com/taskbar-samsung-dex-desktop-mode-android-10/](https://www.xda-developers.com/taskbar-samsung-dex-desktop-mode-android-10/)
										- In Developer Options, turn on “enable freeform windows” and “force desktop mode” and then reboot your device. (The latter may be unavailable on some OEM software like ZenUI/ROG UI, but don’t worry if it’s not there.)
										- Install Taskbar 6.0 (older versions won’t work) from Google Play.
										- Open Taskbar’s settings and go to “Desktop Mode.” Enable it and grant the app permission to “display over other apps” as this is required for the app’s floating start menu to appear. Then, set the app as your default home app. Don’t worry, though, as the next prompt will ask you to set your preferred/primary launcher app, so Taskbar won’t be hijacking your home screen. (Note that on some devices, changing the default launcher will disable Android 10’s full-screen navigation gestures.)
										- Next, I highly recommend you follow the instructions to “enable additional settings” for desktop mode. This will allow you to lower the DPI so UI elements aren’t enormous on the external display, to hide the navigation bar, and to even dim the phone’s screen to save battery life while it’s connected to the external display. You’ll have to set up ADB access on your PC and run the following command:
										- adb shell pm grant com.farmerbb.taskbar android.permission.WRITE_SECURE_SETTINGS
										- (If you are using Taskbar’s “Donate” version, replace “com.farmerbb.taskbar” with “com.farmerbb.taskbar.paid” in the above command.)
										- Finally, check to make sure that “usage access” has been enabled for Taskbar. Doing so will allow the app to show a row of your recently used applications in the start menu.
										- Now, simply connect your phone to your external display using a USB Type-C to Type-C cable (if your external display supports Type-C input) or via a USB Type-C to HDMI adapter.
										- Once connected, you can use the start menu to launch apps, search for apps, add app icons to the home screen, open some system menus, and more. You can tap the icon next to the start menu to add/show widgets. You can launch multiple instances of windows, and in some cases like Google Chrome, have multiple tabs.
									- Setup in a video
										- [https://www.youtube.com/watch?v=kpV4hiURirs](https://www.youtube.com/watch?v=kpV4hiURirs)
								- Requirements
								  collapsed:: true
									- Desktop mode requires a USB-to-HDMI adapter (or a lapdock), and a compatible device that supports video output. Additionally, certain settings require granting a special permission via adb.
									- Keep in mind that in order to actually make use of this feature, your smartphone must support display output. Qualcomm’s latest Snapdragon 800 and 700 series chipsets natively support DisplayPort Alternate Mode over a USB 3.1 Type-C port, but some vendors (like Google) have disabled this functionality on their smartphones. If your device doesn’t support DisplayPort Alternate Mode, then you may have luck using a [DisplayLink-certified adapter](https://www.displaylink.com/) and the <a href="https://play.google.com/store/apps/details?id=com.displaylink.presenter">DisplayLink Presenter app</a> to mirror the phone’s display. Screen mirroring using a DisplayLink adapter isn’t as ideal as native desktop mode through a standard connector, but it’s better than not having any display output at all! Fortunately, Taskbar can still be used if you’re just mirroring your phone’s display so long as the app is set as the default launcher, but you’ll have to use the developer’s <a href="https://workflowy.com/#/74577f823652">SecondScreen</a> app to change the resolution and density.
									- I recommend you use a Bluetooth keyboard and mouse. If you have a portable external monitor/laptop chassis like the [NexDock 2](https://nexdock.com/), then you’ll have an even better experience with Taskbar.
								- Integrations
								  collapsed:: true
									- Lawnchair Launcher
										- Changelog
										  [https://github.com/LawnchairLauncher/lawnchair/releases](https://github.com/LawnchairLauncher/lawnchair/releases)
										- Combined with a Lawnchair Launcher build here so that Taskbar appears when using
										  source:: [https://www.xda-developers.com/taskbar-samsung-dex-desktop-mode-android-10/](https://www.xda-developers.com/taskbar-samsung-dex-desktop-mode-android-10/)
											- [https://github.com/farmerbb/libtaskbar-Lawnchair-Example](https://github.com/farmerbb/libtaskbar-Lawnchair-Example)
									- SecondScreen (was previously necessary so that screen resolution has higher, rather than giant apps on screen)
										- [https://f-droid.org/packages/com.farmerbb.secondscreen.free/](https://f-droid.org/packages/com.farmerbb.secondscreen.free/)
										- [https://github.com/farmerbb/SecondScreen](https://github.com/farmerbb/SecondScreen)
										- SecondScreen is an application designed for power users that frequently connect their Android devices to external displays. It works with your existing screen mirroring solution to give you the best experience possible. With SecondScreen, you can change your device's resolution and density to fit your TV or monitor, enable always-on desktop mode in Chrome, and even turn your device's backlight off, among several other features.
										- Combines well with [scrcpy (Android screen mirroring)](https://workflowy.com/#/13c7bd144649)
										- This app REQUIRES elevated permissions, granted via root access or adb shell commands.
										- 2 Backlinks
											- [SecondScreen](https://workflowy.com/#/74577f823652) + <a href="https://workflowy.com/#/13c7bd144649">scrcpy (Android screen mirroring)</a>
											- Keep in mind that in order to actually make use of this feature, your smartphone must support display output. Qualcomm’s latest Snapdragon 800 and 700 series chipsets natively support DisplayPort Alternate Mode over a USB 3.1 Type-C port, but some vendors (like Google) have disabled this functionality on their smartphones. If your device doesn’t support DisplayPort Alternate Mode, then you may have luck using a [DisplayLink-certified adapter](https://www.displaylink.com/) and the <a href="https://play.google.com/store/apps/details?id=com.displaylink.presenter">DisplayLink Presenter app</a> to mirror the phone’s display. Screen mirroring using a DisplayLink adapter isn’t as ideal as native desktop mode through a standard connector, but it’s better than not having any display output at all! Fortunately, Taskbar can still be used if you’re just mirroring your phone’s display so long as the app is set as the default launcher, but you’ll have to use the developer’s <a href="https://workflowy.com/#/74577f823652">SecondScreen</a> app to change the resolution and density.
									- Also used in Bliss OS
										- [https://forum.xda-developers.com/android/software/bliss-os-x86-pc-s-12-x-development-t4004419](https://forum.xda-developers.com/android/software/bliss-os-x86-pc-s-12-x-development-t4004419)
								- [https://teddit.net/r/Android/comments/dq8dve/make_android_10s_hidden_desktop_mode_more_useful/](https://teddit.net/r/Android/comments/dq8dve/make_android_10s_hidden_desktop_mode_more_useful/)
								- 1 Backlink
								  collapsed:: true
									- Use with [Taskbar](https://workflowy.com/#/052277d0dce4) (enhances Android native <a href="https://workflowy.com/#/0bb6dbb6c437">Desktop mode</a>)
							- _Abandoned_
								- Seena
								- Sentio Desktop
									- Doesn't work well with scrcpy + Android 10 because
										- Very few apps run automatically in windowed mode
						- Windows 10 Android app mirroring
						- Android native support
						  collapsed:: true
							- Desktop mode
								- it’s technically hidden in Android 10, requiring a development flag to be enabled as well as support built-in to the stock launcher app
								- Use with [Taskbar](https://workflowy.com/#/052277d0dce4) (enhances Android native <a href="https://workflowy.com/#/0bb6dbb6c437">Desktop mode</a>)
							- Foldables support
								- _Android support for foldables_
									- Example vid
									  https://cdn.vox-cdn.com/thumbor/B11MID2fiEGjyu2V7RRMZtIdXA8=/0x0:1920x1080/620x413/filters:focal(807x387:1113x693):gifv():no_upscale()/cdn.vox-cdn.com/uploads/chorus_image/image/62221999/android_support_for_Foldables.0.gif
								- Hardware
								  #Phone https://workflowy.com/#/22df69ffbb19
					- Combine with a Thunderbolt cable
						- [Thunderbolt 3 cables support](https://www.benq.com/en-us/knowledge-center/knowledge/usb-c-introduction-what-is-dp-alt-mode.html#S2) USB-C ((63219e34-cda2-4a69-a2c8-b74b33cf9a91)) in order to display external displays
				- Convergence 1.5 - use the same software on desktop + mobile
				  collapsed:: true
				  Apps that work as well on a phone as on a desktop (adaptable user interface)
					- _Approach done by_
						- Librem 5 with PureOS apps
						  See [The Simplicity of Making Librem 5 Apps](https://puri.sm/posts/the-simplicity-of-making-librem-5-apps/)
						- _Not ready yet_
							- Ubuntu Touch
							- KDE Plasma Mobile
							- Fuschia by Google
							- Windows 10 (e.g. on 2-in-1 tablets like Surface Pro)
							- Android on ChromeOS
						- ((670beff0-f581-4aa4-9e26-fbe764b101ad))
						- ((649b13ce-0b9e-4741-ba6d-7959858e3443))
				- Convergence 2.0 - tight integration to allow seamless running mobile apps+all data on desktop
				  collapsed:: true
				  AKA seamless convergence / convergent app use / two-way app sync
					- Summary
						- Very difficult
					- **Processor architecture/app development-wise: **either we need the same architecture on both devices or app devs need to support both archs and create an API for copying data between data
						- Summary
						  collapsed:: true
							- Most likely candidate is Windows 10 tablets which boost the interest in ARM desktops
						- _Same architecture on both avenues_
						  collapsed:: true
							- _Why_
								- Code has to be written slightly differently on each architecture to take into account how they process memory
							- _Devices_
								- x86 phones - high power consumption
								  collapsed:: true
									- DragonBox Pyra
									  intralink2:: https://workflowy.com/#/f585b88c5048
									- x86 Intel Atom devices
									  They abandoned it though in 2015/16
										- Dell Venue 8 Pro tablet
										- Asus Zenfone 2 phone
									- Purism would likely be on board with this for their next phone after Librem 5
									  #Phone [https://workflowy.com/#/f1334ace49d6](https://workflowy.com/#/f1334ace49d6)
								- ARM desktops
								  collapsed:: true
								  You might as well use Convergence 1.0 and just stream phone to a monitor
									- _Windows 10 on ARM_
										- Lenovo Miix 630
										- HP Envy x2
									- \_See \_ARM
									  #PC https://workflowy.com/#/aa7ccc5ab2a6
								- RISC-V everywhere?
								  It'll be years before it's ARM-level performance let alone Intel Atom
							- _Programming language_
								- PyPy runs on multiple architectures
								  https://pypy.org/features.html
						- App developer side
						  collapsed:: true
							- Responsive - like websites and repaint the UI depending on device resolution
							- Cross-architecture compatible
								- requires apps to be available on both ARM + Intel architectures, as well as have an API which will allow translating all data between them
								- Compiling for both phone + desktop architectures
									- e.g. armhf and i386/amd64 (Intel)
									- This is on top of supporting multiple operating systems
					- Sync-wise:
						- Once ((63a9ade4-acd5-44f9-9166-2c1393865f7a)) gets 2-way file sync this may be possible
							- ((63a9ade4-acd5-44f9-9166-2c1393865f7a)) 2-way file sync (allows sync mechanism)
							- _Two routes for having compatible desktop/mobile apps (convergence 1.5)_
								- Ubuntu Touch getting snap/anbox support in March 2019
								- KDE Plasma Mobile apps which are the same as desktop
						- UBports might implement it
						  intralink2:: https://workflowy.com/#/0da2fac108a9
			- Organised by libre-ness
				- _Fully libre_
					- Mobile operating systems
					  collapsed:: true
						- [postmarketOS](https://postmarketos.org/)
						  id:: 644c0ace-85e1-472b-8dd8-81766029ec97
						  (Alpine Linux)
						- [KDE Plasma Mobile](https://www.plasma-mobile.org/)
						  id:: 649b13d0-25c0-41d7-aba8-d874673b3711
						  collapsed:: true
							- [KDE Plasma Mobile — The Linux Phone You've Been Waiting For? - OMG! Ubuntu](http://www.omgubuntu.co.uk/2016/11/kde-plasma-mobile-linux-smartphone-wars)
							- ((63a9ade4-acd5-44f9-9166-2c1393865f7a))
							- Concept video
							  https://youtu.be/3XK5EdoWySQ
							- Prototype video
							  https://youtu.be/auuQA0Q8qpM
							- Roadmap
							  https://community.kde.org/Plasma/Mobile/Roadmap
								- 1.0 tasks (getting it to dumbphone state)
								  https://phabricator.kde.org/project/profile/247/
								- 2.0 tasks (few basic apps)
								  https://phabricator.kde.org/project/view/248/
							- Plasma Mobile shares 90% of the same code as Plasma Desktop
								- Plasma Mobile is being developed in tandem with the popular Plasma desktop, in fact it shares more then 90% of the code with it. This means that work done on either of the two, mobile and desktop often benefits the other, and that there’s a large degree of compatibility between the two. The result is a system that feels the same across different devices, but makes use of the special capabilities of a given device, and supports different ways of using the software
						- [Ubuntu Touch](https://ubports.com/)
						  id:: 649b13d0-64a3-4e77-8663-91a1aa71f20e
						  collapsed:: true
							- Originally by Canonical, but now a community project
								- Scopes (their launcher)
								  https://youtu.be/CsDFMIphtZk
								- Unity UI abandoned
								  https://www.techradar.com/news/canonicals-dream-for-an-ubuntu-phone-is-dead
								- Dg https://insights.ubuntu.com/2015/10/20/ubuntus-path-to-convergence/
							- Lacks
								- Limited device support
								  https://devices.ubuntu-touch.io/
							- UBports community
								- https://ubports.com/
								- Roadmap
								  [https://github.com/ubports/ubuntu-touch/milestones](https://github.com/ubports/ubuntu-touch/milestones)
									- OTA-8 (due March 2019) will include Anbox and support Snaps
									- [https://github.com/orgs/ubports/projects/](https://github.com/orgs/ubports/projects/15#column-6822333)15
									- Seamless Convergence (two-way app sync)
									  https://github.com/ubports/ubuntu-touch/issues/901
								- Blog
								  https://ubports.com/blog/ubports-blog-1/tag/blogs-2
								- https://ubports.com/community/faq
								- Features
									- App store
									  https://open-store.io
							- Convergence - you can plug in a monitor and get a full desktop environment
							  https://ubuntu-touch.io/features/convergence
						- PureOS by Purism
						  id:: 649b13d0-98eb-4868-a381-a95fabd64a2d
						  collapsed:: true
						- Mobian (Debian-based)
					- Mobile environments
					  collapsed:: true
					  AKA Interface
						- Phosh (started by ((649b13d0-98eb-4868-a381-a95fabd64a2d)) )
						- ((649b13d0-25c0-41d7-aba8-d874673b3711))
						- Lomiri (part of ((649b13d0-64a3-4e77-8663-91a1aa71f20e)) )
						- Sxmo
						  collapsed:: true
							- [https://wiki.postmarketos.org/wiki/Sxmo](https://wiki.postmarketos.org/wiki/Sxmo)
					- Android emulators and desktop Android OSes
					  collapsed:: true
						- Desktop Android OSes
							- Android-x86
							- [Android Generic](https://android-generic.github.io/)
							- Waydroid-Linux
							- [Bliss OS for PC](https://blissos.org/)
							  id:: 63415eac-8599-47ed-a38a-325631482926
							  collapsed:: true
								- FOSS OS, based on Android, works on modern PCs and tablets
							- Phoenix OS
							  collapsed:: true
								- Image
								  https://liliputing-wpengine.netdna-ssl.com/wp-content/uploads/2016/01/phoenix_03.jpg
								- http://www.phoenixos.com/
								- Works well with touchscreen laptops apparently
								- For x86. Android-based, like Remix OS
							- Remix OS
						- ReDroid
						  collapsed:: true
							- [https://github.com/remote-android/redroid-doc](https://github.com/remote-android/redroid-doc)
							- Enable `ashmem` and `binderfs` in kernel config
						- ### ARM emulation on x86
							- [libhoudini](https://github.com/Rprop/libhoudini) to enable ARM app support
							- [android_translation_layer / Android Translation Layer · GitLab](https://gitlab.com/android_translation_layer/android_translation_layer)
							  id:: 670beff0-f581-4aa4-9e26-fbe764b101ad
							  collapsed:: true
								- Has been used to port ((65166ca4-1398-465a-8ff7-029210238874)) [to Flatpak](https://github.com/flathub/flathub/pull/5679)
								  id:: 670beffa-13af-4db8-bbb0-c417dae63081
									- When it's published then on their Flathub repo request
										- Rumble support from BraveNewPipe
										- Bidirectional sync watch history with FreeTube
							- _Android emulators_
							  id:: 63219e36-f656-49e9-865a-7347177df70b
								- [Anbox](https://anbox.io)
								  id:: 631fa93c-6e5d-45fd-8497-7c857dc93d67
								  collapsed:: true
									- Links
										- [https://github.com/anbox/anbox](https://github.com/anbox/anbox)
										- Updates - [merged PRs](https://github.com/anbox/anbox/pulls?q=is%3Apr+is%3Amerged)
									- What
										- uses an LXC container to run Android, allowing Android apps to run similarly to Linux apps
										- Similar methodology to how Google is getting Android apps to work on ChromeOS
										- Video demo
										  https://youtu.be/MbmiHnasGWg
									- Pros/Cons
										- Pros
											- _See [Anbox as my platform for Android apps](https://workflowy.com/#/2f4df04a4a2d)_
											  #Productivity-Key
										- Cons
											- Uses Android 7
											  [https://github.com/anbox/anbox/issues/1297#issuecomment-708285765](https://github.com/anbox/anbox/issues/1297#issuecomment-708285765)
											- Aurora store doesn't have a number of apps, possibly due to Android 7 being used
												- ((663b24fb-f1f2-4dbe-ae47-d3a910654835))
												- See [Citymapper](https://workflowy.com/#/35535435574e)
												- Hews
											- _Lacks_
												- Notification support
												  [https://github.com/anbox/anbox/issues/1340#issuecomment-707550728](https://github.com/anbox/anbox/issues/1340#issuecomment-707550728)
												- Magisk/superuser/root support
												  [https://github.com/anbox/anbox/issues/894#issuecomment-636646302](https://github.com/anbox/anbox/issues/894#issuecomment-636646302)
												- Back button on all windows (need to press ESC instead)
												  [https://github.com/anbox/anbox/issues/331#event-1637657092](https://github.com/anbox/anbox/issues/331#event-1637657092)
												- Drag-and-drop copy files
												  [https://github.com/anbox/anbox/issues/1010#issuecomment-655532110](https://github.com/anbox/anbox/issues/1010#issuecomment-655532110)
													- Alternative: Install "X-plore file manager" on anbox , after opening it ,click on "Wifi file sharing" and then activate wifi server ..
													- open the ip address:port on your linux machine's browser ...and start drag and drop files
												- _Minor_
													- Drag-and-drop to install APKs (currently have to install via ADB, F-Droid or Aurora store)
													  https://github.com/anbox/anbox/issues/913
													- VPN support
													  https://github.com/anbox/anbox/issues/1004
											- Many apps will fail to install if they're built for ARM and not x86-64 (AKA amd64)
											  https://github.com/anbox/anbox/wiki/Common-Problems
									- Documentation
										- Setup Anbox
											- manually load the kernel modules
											  [https://github.com/anbox/anbox/blob/master/docs/install.md#before-ubuntu-1904](https://github.com/anbox/anbox/blob/master/docs/install.md#before-ubuntu-1904)
												- sudo modprobe ashmem_linux
												- sudo modprobe binder_linux
											- Verify the kernel modules are loaded
											  ls -1 /dev/{ashmem,binder}
												- _Should see_
													- /dev/ashmem
													- /dev/binder
												- In newer Ubuntu binder works differently, so instead check with this
												  lsmod | grep -e binder_linux
													- Should see
														- binder_linux [various numbers] [various numbers]
														- [source] [https://github.com/anbox/anbox/issues/1569#issuecomment-676594975](https://github.com/anbox/anbox/issues/1569#issuecomment-676594975)
												- [https://github.com/anbox/anbox/pull/1309#issuecomment-683926966](https://github.com/anbox/anbox/pull/1309#issuecomment-683926966)
												- [https://github.com/anbox/anbox/pull/1520](https://github.com/anbox/anbox/pull/1520)
													- [https://brauner.github.io/2019/01/09/android-binderfs.html](https://brauner.github.io/2019/01/09/android-binderfs.html)
											- Install
											  [https://github.com/anbox/anbox/blob/master/docs/install.md#install-the-anbox-snap](https://github.com/anbox/anbox/blob/master/docs/install.md#install-the-anbox-snap)
												- Installing (currently devmode due to limitations)
												  snap install --devmode --beta anbox
												- Updating
												  snap refresh --beta --devmode anbox
											- Run
												- Either
												  anbox session-manager
												- Or through application menu open "Anbox Application Manager"
										- Data locations
											- Anbox has it's core files in /snap/anbox/current
											- /var/snap/anbox/common/data for applications and data
										- Installing apps
											- First install F-Droid in order to get apps graphically
											  adb install /home/boss/Documents/OPTIONAL/Android/Anbox/F-Droid.apk
											- Install Aurora Store for Google Play Store apps
								- [Waydroid](https://waydro.id/)
								  id:: 63a9ade4-ad80-4f73-ad36-483fb022f583
								  (uses containers i.e. host kernel, rather than emulation)
									- [GitHub - waydroid/waydroid: Waydroid uses a container-based approach to boot a full Android system on a regular GNU/Linux system like Ubuntu.](https://github.com/waydroid/waydroid)
									- Pros/Cons
										- Pros
											- Good performance
												- ((649b13d0-1efd-4874-ac25-6cf6df5bb330))
											- Decent integration with host OS
												- Can launch Android apps from host
										- Cons
											- Requires ((643afaae-59a0-4cec-9333-4324e3f3c991))
											- Not great for playing Android games e.g. Genshin Impact
												- Games would require mouse and keyboard support
											- Bugs
												- [Mouse pointer is invisible on KDE Wayland in windowed mode](https://github.com/waydroid/waydroid/issues/255)
												- Gesture navigation is a bit buggy, especially in multi-window mode
											- Lacks
												- [Flatpak support](https://github.com/waydroid/waydroid/issues/64#issuecomment-1120205036)
												- The camera and microphone don't work yet
												  collapsed:: true
													- But these are not important for my needs right now anyway, and I'm sure support will come with time.
												- The filesystem and clipboard are isolated
												  collapsed:: true
													- You can copy/paste within Android but the clipboard doesn't share across the Android/Linux boundary. To share a picture from my Pinephone thru an Android app I need to first download the picture into Android's environment. With creativity you can probably set up file sharing with SMB, FTP, [KDE Connect](https://www.reddit.com/r/PinePhoneOfficial/comments/q4uos8/small_tip_you_can_install_kde_connect_on_waydroid/) or so on.
												- [Bluetooth passthrough](https://github.com/waydroid/waydroid/issues/155) (headphones can hear Waydroid apps, but inaccessible within Waydroid Android settings)
												- [Forced portrait mode apps unusable unless you do a specific workaround](https://github.com/waydroid/waydroid/issues/70#issuecomment-1089260765)
													- ((644c0ace-acfa-41b8-b23c-03481db872d8))
													- Turn on multi-window mode in order to prevent apps from forcing portrait orientation
													  collapsed:: true
														- First we need to set the property while a Waydroid session is running:
														  waydroid prop set persist.waydroid.multi_windows true
														- After that, we can restart the container:
														  sudo systemctl restart waydroid-container
														- {Archive}
														  collapsed:: true
															- [https://github.com/waydroid/waydroid/issues/70](https://github.com/waydroid/waydroid/issues/70)
										- Unclear
											- In future ((6914f923-82e0-4318-9d75-371331198c01)) will have Android game support likely via Waydroid, so they might upstream new commits
											- [[2025-02-13 Thursday]] ((63a9ade4-0cdf-4680-a839-6b6f92e57f51)) : ((670be97c-236d-42e0-a498-acd0fcb2dc48)) works pretty well as an alternative. Waydroid is supposedly getting more development from Valve in a private fork, for their upcoming VR headset
									- Documentation
										- [Installation](https://docs.waydro.id/usage/install-on-desktops)
											- `sudo apt install lxc -y`
											- Steps
												- ```
												  export DISTRO="focal" && \
												  sudo curl - --proto '=https' --tlsv1.2 -Sf https://repo.waydro.id/waydroid.gpg --output /usr/share/keyrings/waydroid.gpg && \
												  echo "deb [signed-by=/usr/share/keyrings/waydroid.gpg] https://repo.waydro.id/ $DISTRO main" > ~/waydroid.list && \
												  sudo mv ~/waydroid.list /etc/apt/sources.list.d/waydroid.list && \
												  sudo apt update
												  ```
											- Looks like that `python3-gbinder` [package wasn't made for your version of your distro.](https://github.com/erfanoabdi/gbinder-python/issues/5)
												- [https://github.com/waydroid/waydroid/issues/368#issuecomment-1152486583](https://github.com/waydroid/waydroid/issues/368#issuecomment-1152486583)
											- This script installs as a workaround
											  [https://gist.github.com/cniw/7a0220ce8b75368f7f57aa422d3fea97](https://gist.github.com/cniw/7a0220ce8b75368f7f57aa422d3fea97)
											- Install Waydroid
											  `sudo apt install waydroid -y`
											- Start the init process
											  `sudo waydroid init`
												- Extracted to:
												  `/var/lib/waydroid/images`
											- Then start the waydroid container service (or just simply reboot):
											  sudo systemctl start waydroid-container
											- Open Waydroid window
											  `waydroid show-full-ui`
										- Setup
										  collapsed:: true
											- Dark theme (Settings > Display > Dark theme)
											- Increase font size ((Settings > Display > Font size > Largest)
											- Setup a shared folder
												- [source] [Setting up a shared folder](https://docs.waydro.id/faq/setting-up-a-shared-folder)
												- sudo mkdir ~/.local/share/waydroid/data/media/0/Waydroid1
												- sudo mount --bind ~/Waydroid1 ~/.local/share/waydroid/data/media/0/Waydroid1
											- Disable on-screen keyboard
												- Android Settings > Apps & Notifications > App info > Android Keyboard (AOSP) > Disable (next to Force Stop)
											- Play Store
												- QuickRotate
												  collapsed:: true
													- [https://github.com/plateaukao/quickrotate/releases](https://github.com/plateaukao/quickrotate/releases)
													- Alternatively: Rotation Control
													  id:: 644c0ace-acfa-41b8-b23c-03481db872d8
														- 1 Backlink
															- See [Rotation Control](https://workflowy.com/#/c489d40fe753)
												- Firefox (F-Droid version has a too high target API level?)
											- Install apps
												- F-Droid
													- Also add IzzyOnDroid key from their website to allow for CloudStream
												- ((63a9ade4-acd5-44f9-9166-2c1393865f7a)) (for manual clipboard sharing)
												- ((65166ca4-1398-465a-8ff7-029210238874))
												- Slide
												- Glider
												- CloudStream
											- To consider
										- Troubleshooting
											- Restarting Waydroid container
											  `sudo systemctl restart waydroid-container`
											- Launching Waydroid after restarting container
											  waydroid show-full-ui
											- Reinstalling
											  [https://docs.waydro.id/usage/install-on-desktops#reinstalling-waydroid](https://docs.waydro.id/usage/install-on-desktops#reinstalling-waydroid)
												-
										- Data locations
											- `/home/.waydroid`
											  Non-existent
											- `~/waydroid`
											  Non-existent
											- `~/.share/waydroid`
											  Non-existent
											- `~/.local/share/waydroid/data/media/0/`
											  Equivalent to /sdcard/ on Android device
											- `~/.local/share/applications/*aydroid*`
											- `~/.local/share/waydroid`
											- `/var/lib/waydroid`
										- New
										  [https://github.com/waydroid/waydroid-package-manager](https://github.com/waydroid/waydroid-package-manager)
									- Demos
										- Sep 2021 - mostly showing game performance on a Pixel 3a
										  id:: 649b13d0-1efd-4874-ac25-6cf6df5bb330
										  [https://youtu.be/dyOgI8PRt9w](https://youtu.be/dyOgI8PRt9w)
								- Hybris for Linux (libhybris)
								  collapsed:: true
								  Compatibility layer | Makes it easier to port non-Android OSes to Android-based devices using Halium
									- Libhybris5 is basically an Android compatibility layer for Linux. Think of it in terms of capability it provides as "WINE for Linux" but then providing "Android for Linux".
									- https://github.com/libhybris/libhybris
									- https://en.wikipedia.org/wiki/Hybris_(software)
								- Related: ((631fa93e-1087-4996-91b8-7526842b4ba8)) : ((649b13d2-56c9-4c4d-800b-e23db485c570))
						- ### x86 emulation on ARM
						  id:: 670be101-bc11-4dd5-a571-13eb92d8edf3
						  collapsed:: true
							- ## Software
								- Box86
								- Box64
								- [Hangover](https://github.com/AndreRH/hangover)
								- QEMU
								- [FEX-Emu](https://fex-emu.com/)
								  id:: 670be21c-1864-4317-a12a-b912c738e737
								- [Winlator](https://github.com/brunodev85/winlator)
								- ### Proprietary
									- [CrossOver](https://www.codeweavers.com/crossover/)
									  id:: 67cae8da-f8fd-4bf7-aa80-4617be177154
									  Powered by WINE
									- ((65a98a51-83ea-4050-b57f-79da79369760))
									- Apple's Gaming Porting Toolkit
									  id:: 67caea19-a358-4b07-9824-174161d23ab6
									  Powered by ((67cae8da-f8fd-4bf7-aa80-4617be177154))
							- ## Alternatives
								- Porting desktop apps to Android
									- Qt already has Android support
										- Multiple KDE apps [on Android now](https://community.kde.org/Android/F-Droid)
									- [GTK has a WIP Android backend](https://gitlab.gnome.org/GNOME/gtk/-/merge_requests/7555)
							- ## Usecases
								- Run ((644c0bb5-76e1-4489-9fa4-22a803fa3c9d)) games on Android devices
								- Run ((644c0bb5-76e1-4489-9fa4-22a803fa3c9d)) games on ((67cae86d-70be-4444-9267-e537acdd241e))
								  id:: 67cae906-3d56-4c08-9cd5-3d28b32f0e43
									- Meta
										- [M1 compatible games master list - AppleGamingWiki](https://www.applegamingwiki.com/wiki/M1_compatible_games_master_list)
									- ### ((63734d16-48e6-44c2-a290-2e41a5927244))-based
										- [I Tried Windows Gaming on a Mac Mini…And It’s Amazing. - YouTube](https://youtu.be/rcDRbJrF7sc) via ((67cae8da-f8fd-4bf7-aa80-4617be177154)) on ((67cae961-f308-4987-ae3e-323d6cfd13d6))
										- [Gaming on Mac in 2025 - YouTube](https://youtu.be/t6VXciGdZO4) on ((67cae961-f308-4987-ae3e-323d6cfd13d6))
											- Comparable to PS5, however the base model is the best value as the upgrades cost a lot
										- [Mac Gaming Sucks...but that's CHANGING! - Apple Game Porting Toolkit - YouTube](https://youtu.be/F6Gi2LcXhxM) via ((67caea19-a358-4b07-9824-174161d23ab6)) on ((67cae9c0-a0fb-458d-9420-eab50f649127))
									- ### ((65a98a51-37bd-4253-b4ab-8437dc26f765))-based
										- Meta
											- [/r/AsahiGaming - game compatibility list](https://www.reddit.com/mod/AsahiGaming/wiki/compatibility)
										- [Testing 12 PROTON games on Mac with Asahi Linux! - YouTube](https://youtu.be/s9Dpeg6_Z5g) via Proton on M1 Max MacBook Pro
											- ((634bc201-ab66-494b-8738-826601b04f57)) only runs decent FPS on Low, likewise with Kingdom Come Deliverance 1
								- Desktop versions of apps - Firefox, FreeTube, Logseq etc
					- Toolkits
					  collapsed:: true
						- Halium project
						  collapsed:: true
						  Hardware Abstraction Layer
							- https://halium.org
							- https://github.com/Halium/halium-devices
							- What
								- includes the Linux kernel, Android Hardware Abstraction Layer or HAL, and libhybris
								- Note: Project Treble has made this much easier as it implements a HAL
								  intralink2:: https://workflowy.com/#/8ccc90945b02
							- Halium is an Open Source Project Working Towards a Common Base for Non-Android Mobile Operating Systems
							- https://docs.halium.org/en/latest/
							- Introducing Project Halium
								- Currently distributions like AsteroidOS, LuneOS, Mer, Plasma Mobile, SailfishOS, and Ubuntu Touch have one thing in common that they use the libhybris to interact with the android binary blobs and they also run the various android daemons using different methods. And there is lot of fragementation on how this task is handled even though these parts don’t need to be different as their essential goal is to make use of android binary blobs.
								- Project Halium is the effort by the community which aims to bring the common grounds for different distributions and have a common base which includes the Linux kernel, Android Hardware Abstraction Layer, and libhybris. Project Halium also aims to standardize the middlewares used to interact with the hardware of the device. By having these parts shared, we believe that it will reduce the fragmentation we have currently.
						- Script to install Anbox, libhoudini and Google App Store
						  https://www.linuxuprising.com/2018/07/anbox-how-to-install-google-play-store.html?m=1
					- ((63219e35-fae2-4fe8-a220-1adba4633994))
					  id:: 63219e36-9720-4c95-82f6-7de03a2d50bd
				- _Mostly libre_
					- Android <> Desktop integration
					  collapsed:: true
						- Features
						  collapsed:: true
							- Universal clipboard (copy and paste)
							- Notification mirroring
							- Remote Replying (SMS, WhatsApp etc)
							- Pushing Files (wirelessly)
							- Screen mirroring
								- like AirMirror, Android on Windows 10, scrcpy
						- _Open-source_
							- [scrcpy](https://github.com/Genymobile/scrcpy)
							  id:: 63a9ade4-0cdf-4680-a839-6b6f92e57f51
							  collapsed:: true
							  Android screen and audio mirroring
								- # Pros/Cons
									- Pros
										- Features
											- Screen mirroring
											  collapsed:: true
												- Related: ((649b13cf-babf-4d83-8afd-576a1869a25a))
											- Connect wirelessly
											  collapsed:: true
												- [https://www.genymotion.com/blog/open-source-project-scrcpy-now-works-wirelessly/](https://www.genymotion.com/blog/open-source-project-scrcpy-now-works-wirelessly/)
												- Pros/Cons
													- Pros
														- USB-C cable I'm using in Q4 2019 is very sensitive and will close scrcpy if nudged at all
													- Cons
														- Slower performance, probably only significant if trying to watch shows via ((649b13cf-59ff-4f2f-ac3f-83fa18732064))
														- [[2025-11-08 Saturday]] I can't seem to get it working via the newer method whilst VPNs are active
												- display and control of Android devices connected on USB (or over TCP/IP)
													- scrcpy uses adb and you can actually do adb over WiFi (adb tcpip 5555, afair)
													- cant get it to work, set the port and all, typed adb connect ''my ip:5555'' says connected but scrcpy doesnt open.
														- Edit: God damn it works, I'm a noob and I got it to work, I wasnt using the right adb, used the one in the scrcpy folder and it works lol, even made a batch file that connects adb wireless and then launches scrcpy thank you.
												- The application communicates with the device over adb, so it should be easy to make it work wirelessly: Connect to a device over Wi-Fi.
												  https://developer.android.com/studio/command-line/adb.html#wireless
													- It was not counting on an adb bug preventing adb reverse to work over a connection established by adb connect.
													  [https://issuetracker.google.com/issues/37066218](https://issuetracker.google.com/issues/37066218)s
													- Therefore, we implemented a workaround to fallback using adb forward (and reversing the client/server roles) when adb reverse fails.
													-
												- How to run scrcpy wirelessly?
												  id:: 644c0ace-1dcc-4c5e-8fcd-a53727a44289
													- Here are the steps:
														- 1.  Connect the device to the same Wi-Fi as your computer
														- 2.  Get your device IP address (in Settings → About phone → Status)
														- 3.  In Android Developer options turn on "ADB over network" and allow USB debugging when prompted
														- 4.  Enable adb over TCP/IP on your computer:
														      adb tcpip 5555
														- 5.  Connect to your device:
														      adb connect DEVICE_IP:5555 (replace DEVICE_IP)
															- At work:
															  adb connect 192.168.1.85
														- 6.  Run scrcpy as usual (ie type in `scrcpy`)
													- Other notes
														- To switch back to USB mode: adb usb.
														- As expected, the performances are not the same as over USB.
														- The default scrcpy bit-rate is 8Mbps, which is probably too much for a Wi-Fi connection. Depending on the use case, decreasing the bit-rate and the resolution may be a good compromise:
														- scrcpy --bit-rate 2M --max-size 800
														- For people in a hurry:
														- scrcpy -b2M -m800
														- Note that while it now works over TCP/IP, this is not an optimal solution for streaming a video wirelessly, since the raw stream is still sent over TCP, where a packet loss is very bad for latency, due to head-of-line blocking. But it’s better than nothing!
												- _Troubleshooting_
													- _Method A_
														- Turn off USB Debugging,
														- Revoke USB debugging authorizations,
														- Plug the cable back in,
														- Turn on USB Debugging
													- _Method B_
														- adb kill-server
														- adb start-server
											- Universal copy and paste
											  collapsed:: true
												- To copy from the device to the computer:
												- put something in the device clipboard (select a text, press "Copy");
												- press Ctrl+c in scrcpy;
												- paste in any application on the computer.
											- [Supports gamepads](https://github.com/Genymobile/scrcpy/blob/master/doc/gamepad.md) using `--gamepad=uhid`/`G` or `--gamepad=aoa`
											  id:: 649b13cf-da25-4c0f-8ec2-ac3aa1f94691
											  collapsed:: true
												- ((631fa93e-1087-4996-91b8-7526842b4ba8)) : ((66e93ef5-6a40-4e8d-a68d-d3d4260746fe)) : ((66e93efa-51c2-421f-919a-868cc7ab1494))
												- Related: ((631fa93e-1087-4996-91b8-7526842b4ba8)) : ((66e93ef5-6a40-4e8d-a68d-d3d4260746fe)) : ((66f330f5-88f3-41a3-bf34-7f97f92f5ff6))
											- Running it landscape, etc
												- `ALT + R` = Rotate device screen
											- [Virtual display](https://github.com/Genymobile/scrcpy/pull/5370)
											  id:: 670be97c-236d-42e0-a498-acd0fcb2dc48
											  collapsed:: true
											  i.e. single app mirroring / each app as a separate window
												- ## v3.0 has Virtual Display e.g. `scrcpy --new-display=1920x1080`
												- [Docs](https://github.com/Genymobile/scrcpy/blob/master/doc/virtual_display.md)
												- Example of how to suggest apps optmise for it
													- [Tasks.org comment](https://github.com/tasks/tasks/issues/1256#issuecomment-2649170997)
														- A limited workaround to this is using [scrcpy](https://github.com/Genymobile/scrcpy)'s [virtual display](https://github.com/Genymobile/scrcpy/blob/master/doc/virtual_display.md) feature to have Tasks display as an app on your desktop. This requires 
														  your phone being nearby either using a wired connection via adb, or [wireless adb](https://github.com/Genymobile/scrcpy/blob/master/doc/connection.md#tcpip-wireless) on the same Wi-Fi network.
									- Cons
										- Bugs
											- [Audio quality drop in virtual display · Issue #6015 · Genymobile/scrcpy · GitHub](https://github.com/Genymobile/scrcpy/issues/6015)
											- [HOME doesn't work when using `--no-vd-system-decorations`](https://github.com/Genymobile/scrcpy/issues/5567#issuecomment-2648027471)
										- Lacks
											- [AppImage/Snap/Flatpak package](https://github.com/Genymobile/scrcpy/issues/287#issuecomment-442024377)
											- [Use the specified app icon for the app window when launching a virtual display with `--start-app` · Issue #5835 · Genymobile/scrcpy · GitHub](https://github.com/Genymobile/scrcpy/issues/5835)
											- [Add a flag to swap the `HOME` functionality when using virtual display + `--start-app` + specifying a launcher · Issue #5836 · Genymobile/scrcpy · GitHub](https://github.com/Genymobile/scrcpy/issues/5836)
											  i.e. being able to easily return to a launcher when using virtual displays
											- [Integration with](https://github.com/Genymobile/scrcpy/issues/13) ((63a9ade4-acd5-44f9-9166-2c1393865f7a))
												- [391624 – Add support for screen sharing](https://bugs.kde.org/show_bug.cgi?id=391624)
											- [Optional root (su, Magisk Zygisk module, etc) for mirroring Android 12+ w/FLAG_SECURE · Issue #3049 · Genymobile/scrcpy · GitHub](https://github.com/Genymobile/scrcpy/issues/3049#issuecomment-1625693728)
											- [scrcpy client as virtual webcam driver · Issue #776 · Genymobile/scrcpy · GitHub](https://github.com/Genymobile/scrcpy/issues/776#issuecomment-1466366098)
												- [Use Phone camera as PC webcam · Issue #3541 · Genymobile/scrcpy · GitHub](https://github.com/Genymobile/scrcpy/issues/3541)
												-
											- [Use phone as a microphone · Issue #4208 · Genymobile/scrcpy · GitHub](https://github.com/Genymobile/scrcpy/issues/4208)
												- [[2025-03-29 Saturday]] Can be done already [using a script](https://github.com/Genymobile/scrcpy/issues/4208#issuecomment-2577575104)
												  collapsed:: true
												  `/home/boss/Documents/Git/1MY_REPOS/snippets/Shell/scrcpy-mic.sh`
												- [v3.2 audio sources enhancement](https://github.com/Genymobile/scrcpy/releases/tag/v3.2)
										- {Archive}
										  collapsed:: true
											- Desktop mode/multi-window
												- [Android 12L tablet mode not yet widely available](https://github.com/Genymobile/scrcpy/issues/3222)
													- To manually use
														- [in Developer Options set smallest width to 600dp to activate the taskbar](https://9to5google.com/2022/04/01/android-taskbar-google-pixel-enable)
												- [Scrcpy put android phone on Desktop mode? · Issue #2114 · Genymobile/scrcpy · GitHub](https://github.com/Genymobile/scrcpy/issues/2114#issuecomment-859153117)
												- [Force desktop mode Android 10 · Issue #1413 · Genymobile/scrcpy · GitHub](https://github.com/Genymobile/scrcpy/issues/1413#issuecomment-1514218350)
								- # Documentation
									- [Mouse bindings](https://github.com/Genymobile/scrcpy/blob/master/doc/mouse.md#mouse-bindings)
										- right-click triggers BACK (or POWER on)
										- middle-click triggers HOME
									- [Shortcuts](https://github.com/Genymobile/scrcpy/blob/master/doc/shortcuts.md)
									- Full-screen = `super + F`
										- scrcpy --fullscreen
										- scrcpy -f short version
									- _Installation method_
									  collapsed:: true
										- `sudo apt install scrcpy adb`
										  id:: 63a9ade4-fc71-46d0-9d87-5fb5873b16ad
										- Unofficial Snap package
										  collapsed:: true
										  `sudo snap install scrcpy`
											- [source] [https://snapcraft.io/scrcpy](https://snapcraft.io/scrcpy)
											- sudo snap install scrcpy
											- Documentation (in progress)
											  https://github.com/sisco311/scrcpy-snap
											- Announcement
											  https://github.com/Genymobile/scrcpy/issues/256#issuecomment-471225913
										- Official installation method
											- Old version
											  collapsed:: true
												- 6/2/19 attempt v1.6 - gave up because it wouldn't compile https://github.com/Genymobile/scrcpy/releases
												- ADB setup
													- Docs/ESSENTIALS/Portable/ADB-Linux
													  source:: https://www.xda-developers.com/install-adb-windows-macos-linux/
													- i.e. USB debugging on phone + sudo apt install adb
												- Install dependencies
												  https://github.com/Genymobile/scrcpy/blob/master/BUILD.md#debianubuntu
												- Download the prebuilt server
												  [downloaded] https://github.com/Genymobile/scrcpy/blob/master/BUILD.md#prebuilt-server
												- Install Android Studio
													- Go to the /bin folder and
														- export ANDROID_HOME=~/opt/android-studio/
														- ./studio.sh
												- Run the command
													- meson x --buildtype release --strip -Db_lto=true \
														- -Dprebuilt_server=/home/boss/Documents/ESSENTIALS/Portable/scrcpy-server-v1.6.jar
													- cd x
													- ninja
													- sudo ninja install
									- Usage
										- Wired
											- Plug an Android device, turn on usb debugging and execute:
											  scrcpy
											- If several devices are connected, the identifier of the device you want to mirror must be provided:
											  scrcpy -s 01234567890abcdef
										- ((644c0ace-1dcc-4c5e-8fcd-a53727a44289))
									- https://github.com/Genymobile/scrcpy/blob/master/FAQ.md
									-
									- Combination
										- Android native desktop mode is pretty bad, even with Taskbar
										  [https://www.youtube.com/watch?v=kpV4hiURirs](https://www.youtube.com/watch?v=kpV4hiURirs)
										- Desktop mode via SecondScreen + Taskbar
										  collapsed:: true
											- Pros/Cons
												- Cons
													- SecondScreen doesn't seem to work well with full-screen gestures when on scrcpy
											- Turn on Taskbar app (to enable desktop mode with taskbar collapsible menu)
											- Turn on SecondScreen app (which can be used to set the resolution and landscape mode)
											- Connect to scrcpy
										- _Getting Android to simulate an external display, then using scrcpy to show that display_
										  collapsed:: true
											- Pros/Cons
												- Cons
													- Doesn't have a taskbar nor a start menu or clock. Just an app picker shortcut (like start menu)
													- Desktop mode on Poco F1 LineageOS (Android 11) doesn't have the desktop mode with proper start menu
											- Alt
												- Pros/Cons
													- Cons
														- Doesn't have a taskbar nor a start menu or clock. Just an app picker shortcut (like start menu)
												- In Android Developer settings: simulate secondary display: 4k
												- scrcpy --display 1
											- Alt 2
												- Can create multiple "simulate secondary displays" via CLI rather than via Developer settings
												  adb shell settings put global overlay_display_devices 1920x1080/480
												- [source] [https://github.com/Genymobile/scrcpy/issues/1413#issuecomment-640273175](https://github.com/Genymobile/scrcpy/issues/1413#issuecomment-640273175)
											- Alt3
												- Cons
													- Phone display only takes up all immediate space when put into landscape mode via `META` + `R`
												- adb devices && scrcpy --turn-screen-off --stay-awake --window-width 1920 --window-height 1040
										- scrcpy + Taskbar + a script
										  collapsed:: true
											- Cons
												- Tried it, doesn't work well at all
											- [source] [https://github.com/farmerbb/Taskbar/issues/171#issuecomment-780879479](https://github.com/farmerbb/Taskbar/issues/171#issuecomment-780879479)
											- [https://gist.github.com/farmerbb/068b8e4f5fb61f33fca3fa9130778c99](https://gist.github.com/farmerbb/068b8e4f5fb61f33fca3fa9130778c99)
										- Desktop mode on scrcpy via a script (however Android's native desktop mode sucks since it doesn't have resizable windows
										  [[Page not found · GitHub](https://github.com/nikp123/scrcpy-desktop](https://github.com/nikp123/scrcpy-desktop))
								- # Ecosystem
									- [Install Aurynk on Linux | Flathub](https://flathub.org/apps/io.github.IshuSinghSE.aurynk)
									- scrcpy fork
										- [Web version of scrcpy](https://github.com/yume-chan/ya-webadb)
											- https://docs.tangoapp.dev/
										- [Proprietary Tango web app](https://app.tangoapp.dev/)
										- [FOSS version of old web app](https://github.com/tango-adb/old-demo)
								- Related:
									- [Corellium Virtual Hardware](https://www.corellium.com/) for iOS virtualisation
									- [STF | Smartphone Test Farm](https://github.com/DeviceFarmer/stf)
							- [KDE Connect](https://invent.kde.org/network/kdeconnect-kde)
							  id:: 63a9ade4-acd5-44f9-9166-2c1393865f7a
							  collapsed:: true
								- Pros/Cons
									- Pros
										- Open-source alternative to PushBullet, AirDroid etc
										- Seems to work with current VPN (Mullvad) which allows exceptions for LAN both it's desktop and Android apps. It also has split-tunneling to specifiy allow the app
									- Cons
										- Transfer speed is slow, but I can just use Syncthing instead really
										  [https://bugs.kde.org/show_bug.cgi?id=439545](https://bugs.kde.org/show_bug.cgi?id=439545)
										- Lacks
											- [486361 – Quality of Life: allow "Send to Device" share button to send to device immediately if there's only one available](https://bugs.kde.org/show_bug.cgi?id=486361)
											- [Can't automatically or manually send Android clipboard to desktop](https://bugs.kde.org/show_bug.cgi?id=445658#c4), and [the reverse](https://bugs.kde.org/show_bug.cgi?id=444472)
											  collapsed:: true
												- Because of ((649b13d3-0ea2-4545-8a35-4747f6476bff))
													- However I can just use scrcpy for that
												- [Wiki](https://userbase.kde.org/KDEConnect#Clipboard)
												- Using [this script](https://github.com/draumaz/kdeconnectbidirectionalclipboard) made the "Send Clipboard" button on the ((63a9ade4-acd5-44f9-9166-2c1393865f7a)) notification work again
													- Commands on PC
														- ```bash
														  asb shell
														  cd /sdcard/Download
														  curl -fLO https://github.com/draumaz/kdeconnectbidirectionalclipboard/releases/download/1/kdeconnectbidirectionalclipboard-v1.zip
														  su -c 'magisk --install-module kdeconnectbidirectionalclipboard-v1.zip'
														  ```
													- Script executes [these commands](https://github.com/KDE/kdeconnect-android/commit/edc655da5ac1eb5c3027c8556cc62037a1d4c5ac#diff-ac7ef6bdb0cb04522672bc5149779c69324abb1aadf808b74223a603b5771a6bR31):
														- ```bash
														  adb -d shell pm grant org.kde.kdeconnect_tp android.permission.READ_LOGS;
														  adb -d shell appops set org.kde.kdeconnect_tp SYSTEM_ALERT_WINDOW allow;
														  adb -d shell am force-stop org.kde.kdeconnect_tp;
														  ```
									- Unclear
								- # Links
									- https://phabricator.kde.org/project/board/159/
									- https://nicolasfella.wordpress.com/
									- https://community.kde.org/KDEConnect
									- https://github.com/KDE/kdeconnect-kde
									- [Components for kdeconnect](https://bugs.kde.org/describecomponents.cgi?product=kdeconnect)
									  collapsed:: true
										- common
										  https://bugs.kde.org/buglist.cgi?component=common&order=changeddate%20DESC%2Cbug_status%2Cpriority%2Cassigned_to%2Cbug_id&product=kdeconnect&query_format=advanced&resolution=---
										- android application
										  https://bugs.kde.org/buglist.cgi?component=android-application&order=changeddate%20DESC%2Cbug_status%2Cpriority%2Cassigned_to%2Cbug_id&product=kdeconnect&query_format=advanced&resolution=---
									- https://www.reddit.com/search?q=Kde%20connect&sort=new
									- https://www.reddit.com/r/kde/search?q=Kde%20connect&sort=new
								- # Features
									- Shared clipboard (copy and paste) e.g. allows you to use PC as password manager
									- Notification mirroring: Read+reply Android notifs on Desktop. + the reverse
										- Receive desktop notifications on your phone (if desired, so it's 2-way)
										- How to send certain notifications from phone > desktop
											- Android app ((63a9ade4-acd5-44f9-9166-2c1393865f7a)) > Plugin Settings >  Notification Sync > click on it to add/remove apps
												- e.g. remove ((651ad3df-16ac-4b19-99d3-1f6db31a0372)), ((6312a076-eb26-4bd5-a669-ea0a50d06668))
												- Ensure [Tasks.org](((65ea4fb5-ec50-4c3c-ab50-ae13830ea523))) notifications get mirrored
									- touchpad emulation: use your phone screen as your computer's touchpad (keyboard emulation is also available);
									- display your phone's battery status on the desktop;
									- multimedia remote control: use your Android device to control various Linux media players;
									- Easy share links - use the Android share menu > KDE Connect
									- File transfer
									  collapsed:: true
										- _Methods_
											- A) On laptop click ((63a9ade4-acd5-44f9-9166-2c1393865f7a)) > hamburger menu > Browse Files > copy and paste folders onto desktop
												- Pros/Cons
													- Cons
														- Pretty slow transfer when trying to copy 10GB+ folder full of small files
											- B) On Android click Send Files > select file
												- Pros/Cons
													- Pros
														- Decent speed transfer
													- Cons
														- Requires ZIPing a folder into a file first
									- [Use remote keyboard for typing](https://nicolasfella.wordpress.com/2018/03/20/kde-connect-state-of-the-union/)
									- [Reply to SMS + WhatsApp messages from your desktop](https://nicolasfella.wordpress.com/2018/03/20/kde-connect-state-of-the-union/)
									- Trigger custom commands from your phone
									  collapsed:: true
										- Pre-configure commands in the KDE Connect desktop settings so you can trigger them from your phone. Use it to extend KDE Connect’s functionality to suit your needs!
										- https://userbase.kde.org/KDE_Connect/Tutorials/Useful_commands
										- Open a set website directly, for instance, Netflix: firefox --new-tab netflix.com/browse
									- Browser integration - sending links to your phone, controlling media
									  collapsed:: true
										- https://community.kde.org/Plasma/Browser_Integration
										- https://addons.mozilla.org/en-US/firefox/addon/plasma-integration/
									- Voice dictation to PC notepad
										- Use the remote input feature > open keyboard > press the microphone button
										- Note: PC should be focused on a notepad program
									- Works over WiFi, bluetooth
								- # Desired features
									- _High desired_
										- [2-way autosync (like FolderSync)](https://bugs.kde.org/show_bug.cgi?id=367726)
										  collapsed:: true
											- Note: pre-requisite for convergence 2.0
											  intralink2:: https://workflowy.com/#/fb58efeeed21
										- Keyboard shortcut to open remote keyboard
										- [File browser (not just one-off sending)](https://bugs.kde.org/show_bug.cgi?id=397926)
										  collapsed:: true
											- https://bugs.kde.org/show_bug.cgi?id=377033
											- https://bugs.kde.org/show_bug.cgi?id=380022
										- [Use android microphone](https://bugs.kde.org/show_bug.cgi?id=362990)
									- _Medium_
										- Android remote keyboard: prevent screen to dim while typing
										  https://bugs.kde.org/show_bug.cgi?id=392824
										- Contacts / mail sync
									- _Low desired_
										- Screen mirroring (see ((63a9ade4-0cdf-4680-a839-6b6f92e57f51)) )
										- USB connection
									- _Very low desired_
										- [SMS app](https://bugs.kde.org/show_bug.cgi?id=362516)
										- [Phone calls via PC](https://bugs.kde.org/show_bug.cgi?id=345686)
										  collapsed:: true
											- https://bugs.kde.org/show_bug.cgi?id=345686
											- Access contacts from desktop
											- https://bugs.kde.org/show_bug.cgi?id=397333
								- # Documentation
									- Restarting the Linux service
										- ```
										  killall kdeconnectd
										  kdeconnect-cli --refresh
										  ```
								- How to use on Windows
								  collapsed:: true
									- KDE Connect dev may be building a Windows version
										- Dev blog https://albertvaka.wordpress.com
										- Homepage https://community.kde.org/KDEConnect
										- https://github.com/albertvaka/kdeconnect-kde
										- Windows package task
											- https://todo.kde.org/?controller=task&action=readonly&task_id=1513&token=27364ace24813c264a6065a06a2f2174c17e3e1180bc810f76c6c606202b
									- KDE community are developing Windows installers for various KDE apps
									  But have said that Albert (KDE Connect dev) is working on KDE Connect
										- https://community.kde.org/Windows
										- They're currently developing installers for individual KDE apps
										  http://kfunk.org/2016/06/18/kde-on-windows-update/
											- http://kfunk.org/tag/kde-windows/
									- Hacks
										- KDE Connect Indicator to use it on Xubuntu, etc
										  http://www.webupd8.org/2014/11/kde-connect-indicator-use-kde-connect.html
										- http://www.techradar.com/news/software/operating-systems/how-to-run-kde-on-windows-611178
										  Outdated
								- _Alternatives/Similar_
								- [it's on KDE on Ubuntu](http://www.omgubuntu.co.uk/2017/02/easy-way-connect-android-to-ubuntu-pc)
							- [Deskscreen](https://deskreen.com)
							  id:: 649b13cf-babf-4d83-8afd-576a1869a25a
							  collapsed:: true
							  (desktop screen mirroring)
								- Cons
									- No Flatpak
									  [https://github.com/pavlobu/deskreen/issues/26](https://github.com/pavlobu/deskreen/issues/26)
								- [https://github.com/pavlobu/deskreen](https://github.com/pavlobu/deskreen)
								- What
									- lets you use any device with a web browser as a second screen over Wi-Fi. Best of all, it offers support for Windows, macOS, and Linux.
							- PushRocket (self-hosted)
							  id:: 649b13cf-1206-4c58-b2fd-3a8d4c858cc6
							  collapsed:: true
								- See push notifications
								  intralink2:: https://workflowy.com/#/3a80ef8f8e2d
								- Built on [Pushjet](https://workflowy.com/#/cda5cc66f106) code but using MQTT instead of FCM
								- https://gitlab.com/pushrocket
								- https://trello.com/b/AVEBTzMB/pushrocket
								- Allows push notifications etc from non-WiFi
								- 1 Backlink
									- See [PushRocket (self-hosted)](https://workflowy.com/#/ddd22062d407)
						- _Proprietary_
							- ((63219e35-31c8-4454-9e84-be51a2684aae))
							- PushBullet
							  collapsed:: true
								- Closed source. the
									- Notification mirroring
									- Reply To SMS, WhatsApp etc
									- Universal Copy & Paste
									- File sharing via separate app
							- AirDroid
							  collapsed:: true
								- Features
									- Notification Mirror
										- Mirror phone notifications from any allowed apps to your computer.
									- Messages Replying
										- Reply to mobile messages (WhatsApp, Facebook Messenger, Telegram and Kik) from desktop clients.（Desktop client only)
									- Apps Management
									- AirMirror - mirror screen
										- AirMirror is a feature in AirDroid that allows you to control your Android device wirelessly. The Android device doesn't need to be rooted. With the AirMirror feature, you can use your computer mouse and keyboard to interact with all the apps you have on the Android device.
									- Access files, messages, contacts, call logs, SMS
									- 2.  Backup & Sync - Backup photos and videos from phone to computer.（Desktop client only)
									- Universal Clipboard (copy and paste)
									- 3.  SMS & Contacts management - Send and receive SMS, and manage phone contacts from the desktop.
									- 4.  AirIME - Use your desktop keyboard to type on your phone.（Desktop client only)
									- 7.  Other phone management features (Web client only)
									- Remote camera: See through the lens of both front and back cameras.
									- Find phone: locate your phone when it’s lost.
									- Apps & Media: manage photos, ringtones and videos, upload, install and export apks.
									- _Minor features_
										- 5. Record screenshot - Record phone screenshot with one click, no root required. (Android 5.0+)
										- 6. Speed boost
										- Clean memory and boost phone speed.
							- Dukto
							  collapsed:: true
								- http://www.msec.it/blog/?page_id=11
								- Open-source, allows LAN transfer of files wirelessly. Opens Android in file explorer
							- Webkey (root required)
							  collapsed:: true
								- https://play.google.com/store/apps/details?id=com.webkey
								- click and type on phone,
								- get, save screenshots,
								- get GPS location,
								- remote shell terminal
								- 3G support though webkey.cc
							- [Multilicity 4](https://alternativeto.net/software/multiplicity/about/)
							  Desktop screen mirroring/extending via Seamless Display, also multi-device keyboard and mouse control
						- _Similar_
							- [Sidecar by Apple](https://support.apple.com/en-us/HT210380)
						- {Archive}
						  collapsed:: true
							- Android Notifier - wifi or bluetooth only, possibly USB soon
							  Open source. Android>PC notification mirroring
								- https://code.google.com/p/android-notifier/
								- http://www.howtogeek.com/64617/how-to-receive-your-android-phones-alerts-on-your-desktop-computer/
							- Desktop Notifications
							  Closed source. Android>PC notification mirroring
								- Made by a university but closed source
								- Uses Google account to send notifications
								- https://play.google.com/store/apps/details?id=org.hcilab.projects.notification
								- Firefox extension
						- Related:
							- ((6746dffa-41fd-433e-b5ba-948bfd086023))
					- [Fuchsia](https://fuchsia.dev/)
					  id:: 649b13cf-a825-48f5-ae83-b47b6ad6bff9
					  collapsed:: true
					  (Zircon microkernel) | by ((64e0943b-37fb-4eb2-a52b-50ce07e795fa))
						- Pros/Cons
						  collapsed:: true
							- It's MIT-licensed, unlike Linux which is GPLv2
							  collapsed:: true
								- it's open sourced in a way that's designed to support making proprietary products, so you'll forgive my not really celebrating.
									- This is a tragedy for Free Software. The Linux kernel (and specifically its GPL nature) is the best thing that has ever happened to Free Software drivers and embedded systems. The only reason that companies release open source drivers for their products is because they are legally required to in order integrate with the Linux kernel. Clearly Google wants to move away from this world.
									- I will mourn the day that a non-copyleft kernel supplants Linux and our only reason for free software hardware support comes to and end.
								- Legal
									- The Kernel is an MIT license, and the user space is BSD [1]
										- [1] [https://fuchsia.dev/fuchsia-src/contribute/governance/policy...](https://fuchsia.dev/fuchsia-src/contribute/governance/policy/open-source-licensing-policies)
									- > The ((649b13cf-a825-48f5-ae83-b47b6ad6bff9)) kernel is released under the following MIT-style license: /zircon/kernel/LICENSE.
									- > All Fuchsia user space components are released under a BSD-style license: /LICENSE or an Apache 2.0 license: [https://fuchsia.googlesource.com/infra/+/main/LICENSE](https://fuchsia.googlesource.com/infra/+/main/LICENSE).
									- > All code that is BSD-licensed has an additional IP grant: /PATENTS.
							- Pros
								- Microkernel capability-based design has more security since there's more sandboxing
									- [22/10/21 I post a message on the Matrix group saying I was disappointed that Fuchsia was going to be used because it could](https://workflowy.com/#/14ca7568df11)
									- the network stack is a sandboxed userspace process too
									- drivers, filesystems, network stack, etc.
									- so a remote code exec vuln in network stack would be contained in an extremely strong sandbox (way better than you have on Linux)
									- as opposed to Linux where the whole network stack is entirely trusted code and if you exploit it you gain full control of the OS with 0 containment
									- that's the whole Linux vs. Minix debate
									- Similar to systemd debate. It's not the UNIX philosophy of do one thing only
									- Pros/Cons of monolithic kernel
									  collapsed:: true
										- Pros
											- Drivers being in kernel means that hardware can be supported for a long time, if it's upstreamed
											- Having drivers not in kernel means there's no incentive for OEMs to update their drivers ever
										- Cons
											- OEMs who won't upstream could actually have longer support on a microkernel instead
											- Slower, bigger and more complex kernel
											- More complex kernel so there's potentially more errors
											- Linux is built in a memory-unsafe language mostly (it's not Rust)
											  collapsed:: true
												- > https://source.android.com/setup/build/rust/building-rust-modules/overview
												- I know that the bluetooth stack is being rewritten, anything else?
													- Keystone HAL, binder, serialisation stuff
													- Virtualization
													  [https://android.googlesource.com/platform/packages/modules/Virtualization](https://android.googlesource.com/platform/packages/modules/Virtualization)
													-
											- Bigger kernel, which
											- Slower kernel, which affects I/O
							- Cons
								- It's an existential risk to Linux
								  collapsed:: true
									- Some groups explictly want to follow the Embrace, Extend and Extinguish route to replace Linux
										- See [Replacing Linux with a microkernel is a goal of some entities like Android and GrapheneOS](https://workflowy.com/#/7840d536acbd)
										  #PC-Linux
								- [Custom ROMs - hindered] The different license gives manufacturers keep part of device middleware closed-source, and thus hamper development of custom ROMs for phones e.g. LineageOS
								  collapsed:: true
									- The different license gives manufacturers keep part of device middleware closed-source, and thus hamper development of custom ROMs for phones e.g. LineageOS
									- Replacing the Android licenses (Apache License 2.0 and GNU GPL v2) with ((649b13cf-a825-48f5-ae83-b47b6ad6bff9))'s (BSD 3 clause, MIT, and Apache 2.0) Zircon microkernel enables device manufacturers to keep their device kernel code modifications closed-source, which means you'd have to reverse engineer the code to run Zircon yourself
									- This means you're stuck with the OEM ROM (Android skinned) until it's reverse engineered which would then allow you to run the Android GSI (Generic System Image) and thus any custom Android-based ROM e.g. LineageOS
									- ...
									- ((649b13cf-a825-48f5-ae83-b47b6ad6bff9)) will result in most devices being limited to stock Android OS due to the OEM proprietary drivers being compatible only with a different kernel, thus not allowing for any non-Android (Linux-based) OS, but should allow for Android-based ROMs
									- Would have to use OEMs which open-source their drivers (e.g. Purism); or any which deem to release their firmware regardless of license obligation (possibly Google); or older devices which are maintained by Android or OS other porters
								- [Android on Linux - hindered] Switching to Zircon also means libhybris and Anbox will have to be totally reengineered in order for Linux-based phones and desktops to run Android apps. It will most likely need a virtual machine
								- [Linux on Android-based devices - slower] Running Linux OSes on Android (Zircon)-based devices requires the Machina emulator; there's no
								  collapsed:: true
									- https://9to5google.com/2018/06/15/fuchsia-friday-machina-brings-support-for-running-linux-on-top-of-fuchsia/
									- This is unlike how Anbox does it:
										- Projects like Shashlik or Genimobile use an emulator to run the Android environment. The emulator creates an entire emulated system which has its own kernel etc whereas Anbox runs the Android system under the same kernel as the host operating system does. No emulation layer like QEMU is necessary. Everything runs directly on the hardware. This approach also allows a much better integration with the host operating system.
										- It uses LXC container system, similarly to how ChromeOS brings Android apps to it
							-
							- Unclear
							- Related: GrapheneOS [Roadmap includes switching to a microkernel, then to a hypervisor](https://workflowy.com/#/a86d25f96f3b)
						- Fuschia (OS)
						  collapsed:: true
							- Merges all their operating systems into one
								- Google has a multitude of operating systems scattered across various hardware form factors. Mobile phones are powered by the full-fledged version of Android, televisions get Android TV, cars get Android Auto, smartwatches run on Wear OS, and desktops, laptops, and now tablets showcase Chrome OS.
							- Replacing Linux kernel with Magenta/Zircon - for "performance" but likely just copyright
							- UI based on the Dart programming language
							- Widget and application framework named Flutter
								- Flutter tool will allow easier development of apps which look good on both desktop and mobile
								  ((649b13cf-a825-48f5-ae83-b47b6ad6bff9))
						- Andromeda (desktop environment)
						  collapsed:: true
							- Andromeda sounds like the interface and application layer for large-screen devices like tablets and laptops. Running atop Fuchsia and leveraging scalable floating windows, Andromeda could look very much like Chrome and be optimized for mouse and keyboard use as well as touch. In other words, very much like the Chrome OS we have today but using the newer more modular Fuchsia as a base.
						- Eventually, the Android runtimes will be phased out in favor of newer, but compatible, software like Mojo
						- (2021 May) The Google Nest Hub is the world's first commercial Fuchsia device
						  [[May | 2021 | Ars Technica](https://arstechnica.com/gadgets/2021/05/google-launches-its-third-major-operating-system-fuchsia/](https://arstechnica.com/gadgets/2021/05/google-launches-its-third-major-operating-system-fuchsia/))
						- ((649b13cf-a825-48f5-ae83-b47b6ad6bff9))'s primary app-development language is [Flutter](https://workflowy.com/#/338b6a4816ad)
				- _Non-libre_
					- [Apple Handoff](https://support.apple.com/en-gb/102426)
					  id:: 683839c4-8d4e-404d-b163-8927ae190f33
					- [Windows version](https://www.windowscentral.com/software-apps/windows-11/windows-11-is-getting-its-own-version-of-the-macs-handoff-feature-resume-apps-across-android-and-pc) of ((683839c4-8d4e-404d-b163-8927ae190f33))
					  collapsed:: true
					- Android multi-tasking launchers
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Works with any android tablet
							- Cons
								- More limited than a specialised OS
						- Samsung DeX
						  id:: 63219e35-31c8-4454-9e84-be51a2684aae
						  collapsed:: true
							- Pros/Cons
								- Cons
							- Commonly used devices
								- Tab S7+
								- [Tab S8](https://teddit.adminforge.de/r/SamsungDex/comments/xgczeo/tab_s8_is_now_my_main_computer_for_school/)
							- Commonly used software
								- deploy a couple of OpenShift servers locally via ((649b13ce-0b9e-4741-ba6d-7959858e3443)) and bVNC
									- On the tab screen itsself I have ((649b13ce-0b9e-4741-ba6d-7959858e3443)), Slack, RemoteDB (android app), and a floating youtube window for entertainment. On the monitor I have bVNC running a linux environment (installed via Andronix)
								- code-server
							- [Learning Resources]
								- https://teddit.adminforge.de/r/SamsungDex
							- Related: ((63413f29-f610-4c39-a8bc-34e622d2d540))
						- Leena
						- Sentio
						- Xiaomi PC Launcher
						  collapsed:: true
							- [https://www.apkmirror.com/apk/xiaomi-inc/pc-launcher/pc-launcher-12-1-125-release/pc-launcher-12-1-125-android-apk-download/](https://www.apkmirror.com/apk/xiaomi-inc/pc-launcher/pc-launcher-12-1-125-release/pc-launcher-12-1-125-android-apk-download/)
					- Running Linux from an Android phone
					  collapsed:: true
						- Unsure
							- ((63413f29-f610-4c39-a8bc-34e622d2d540))
						- Doesn't use 3D video acceleration
							- UserLand
							- DriveDroid?
						- Does
							- ((63219e35-31c8-4454-9e84-be51a2684aae))
							- ((649b13ce-0b9e-4741-ba6d-7959858e3443))
							- i've heard good things about linux deploy and complete linux installer. the problem is that they require not just root but a kernel that supports loop devices, which isn't really an advertized feature. the only way to know if it'll work is to try it
								- https://reddit.com/comments/az3y8c/comment/ei5y1e3?context=3
					- Android app mirroring by Windows 10
					  collapsed:: true
						- https://www.theverge.com/2018/10/3/17933644/microsoft-android-apps-windows-10-app-mirroring-report
					- iOS and Mac Continuity
					  collapsed:: true
						- Features
							- Phone calls from desktop
							- Automatic desktop unlock
							- Universal copy and paste
						- Archive
							- https://www.apple.com/uk/macos/continuity/
					- Android emulators
					  collapsed:: true
						- Windows Subsystem for Android
						- [Error 403 (Forbidden)!!1](https://play.google.com/googleplaygames)
						-
					- {Archive}
						- [Windows Continuum](https://www.microsoft.com/en-us/windows/Continuum)
			- {Archive}
			  collapsed:: true
				- Firefox OS [abandoned]
				  Cancelled in Sep 2016
					- https://groups.google.com/forum/?_escaped_fragment_=msg/mozilla.dev.fxos/FoAwifahNPY/Lppm0VHVBAAJ#!msg/mozilla.dev.fxos/FoAwifahNPY/Lppm0VHVBAAJ
				- Remix OS [abandoned]
				  Android-based, offering Android apps with a desktop interface | Closed-source
					- Jide's Remix OS is being killed off
					  https://www.theverge.com/circuitbreaker/2017/7/18/15988382/jide-remix-os-desktop-android-development-ending
					- https://alternativeto.net/software/remix-os/
					- Jide's Remix OS Player (BlueStacks alternatitive)
					- https://alternativeto.net/software/remix-os-player/
					- http://www.jide.com/remixos-player
					- Remix OS for Mobile (Jide's upcoming Singularity ROM)
					- Android-based and Stock-like, plug it into HDMI connector to use with Remix OS
					- http://www.jide.com/remixos-for-mobile
			- _Related: _
				- Deskreen - turn any device into a second monitor
				  collapsed:: true
					- [https://news.ycombinator.com/item?id=25891464](https://news.ycombinator.com/item?id=25891464)
					- [https://deskreen.com/](https://deskreen.com/)
					- [https://github.com/pavlobu/deskreen](https://github.com/pavlobu/deskreen)
				- ((65a98a50-811c-4de7-8127-0919127fe8af))
	- ((631fa93e-1087-4996-91b8-7526842b4ba8)) Apps & Data
	  id:: 6306a77a-3999-4fd1-99dd-630a77dd542c
	  collapsed:: true
		- Settings controlled via OS
		  collapsed:: true
			- Android 9 will [block background apps from using microphone, camera or sensors](https://developer.android.com/about/versions/pie/android-9.0-changes-all#privacy-changes-all). A foreground service can be used instead (which requires a notification)
			  collapsed:: true
				- Notification requirement
				  https://developer.android.com/guide/components/services
			- _Basic permissions not covered by XPL_
				- Location
				  collapsed:: true
					- Mobile phone
					  collapsed:: true
						- Location Services (Apple/Google)
						  See #IL-0005
						- Use "Bouncer" app so that Location permission is only temporarily given to apps which need it
						  collapsed:: true
							- Apps which only \_temporarily \_need Location (mainly whilst in foreground)
								- Uber
								- Maps apps
							- Apps which permanently have access
								- Google Play Services
								  See #IL-0005
								- Open-source apps
									- Weather e.g. Your local weather, Good Weather
									- Maps e.g. OsmAnd, Offi
									- Device Locator
								- See [Tinder](https://workflowy.com/#/1d745abfd07e)
								- Happn
							- "Unsupported app"
								- Unsupported means the app was built before Android 6.0. Apps before 6.0 are granted the permissions at runtime. For example if an app that wanted location was built before Android 6.0 it would ask you when you install it, and not when you open the app (like newer apps do). So by default, the unsupported apps have that permission. Now you can manually open up app info and remove the permission (it will warn you that the app is old and may crash if you remove it), but unfortunately there is no way for Bouncer to know about granting information for old apps like those. They are shown on the permissions screen because by default they will have that permission, it’s only if you manually go in and remove it yourself that the app won’t have that permission.
					- Location/Face can't really be hidden anymore
					  collapsed:: true
						- _Can be discovered via_
							- Facial recognition via CCTV
							- IP address (or still via traffic analysis if you use VPNs/Tor)
							- ((649b13cd-0859-4c2f-8ad3-28bfe496eeba))
						- Location via mobile phone radio baseband
							- Note: unrelated to hardware baseband isolation. That simply prevents carriers (and other entities) from hacking your phone or
						- Location via Facial Recognition
							- As funny as this is, not having Facebook isn't really that weird. The real problem is staying away from photos. That guy instantly deanonymized himself when he had his picture taken. Now, Big Data has his name (through contacts or microphone snooping). They have a picture. From the EXIF data, his location could be leaked. If I were him, I'd be super annoyed.
							- They have a picture. From the EXIF data, his location could be leaked. If I were him, I'd be super annoyed.
							- Eh, that's a losing battle, unless you become a total social recluse you're gonna get your picture taken a some point and be scanned by a facial recognition algorithm and land in the databases. There's no way around it anymore.
					- Mobility pattern (from home, via commuter route, to work) — very unique, just 4 locations is enough to identify 90% of people.
					  http://www.nature.com/articles/srep01376?ial=1
					- Paired mobility pattern with a known device (known as “mirroring”, when two or more devices travel together; including car telemetry!)
				- Voice
				  collapsed:: true
					- Voice fingerprinting
					- Unencrypted Voice Channels
						- PSTN (cellular)
						- See [WhatsApp](https://workflowy.com/#/1e4b5f5d1337)
						  #Phone
				- Storage
				- Contacts list
				  collapsed:: true
				  _Can be discovered via_
					- My hosted server being hacked (ownCloud as of Jan 2017)
					- See [WhatsApp](https://workflowy.com/#/1e4b5f5d1337)
					  #Phone
					- SnapChat
					  See #IL-0009
			- _XPrivacyLua_
			  id:: 649b13cf-d6ff-4267-9a99-c559649eee01
			  collapsed:: true
				- Comparison with Android 12
				  collapsed:: true
					- It can fake info that any app might require you to give the permission for
					- XPrivacyLua also covers:
						- Internet - covered instead by custom ROMs permissions
						- WiFi scan results, SSID/BSSID, configured WiFi networks
						- IMSI + ((62f388fb-d81f-4d3a-b11b-06c770dd2bb2))
						- Unsure
							- Fake account info - though Shelter can be used for this
							- Preventing clipboard paste - though nowadays there's a toast alert for this
							- Fake Android ID, serial, Google services framework ID, Google advertising ID,
							- Hide list of installed apps
							- Hide recent tasks, running processes/services/tasks,
				- Meta
				  collapsed:: true
					- Successor - XPrivacyLua
					  collapsed:: true
						- Difference - instead of blocking permissions, it replaces with fake data
							- Old version of XPrivacyLua allowed more customisation of the values you can fake however it broke functionality with too many apps and required lots of technical support so the newer version instead just fakes lots of info.
						- Comparison of permissions
						  https://github.com/M66B/XPrivacyLua/blob/master/XPRIVACY.md
							- Lost capabilities
							  collapsed:: true
								- Can't prevent voice or SIP calls from being started, though can prevent audio being recorded
								- Can't block IPC Binder or Reflection
								- Can't restrict individual sensors though it can block all: might be implemented as pro feature
									- acceleration
									- gravity
									- heartrate
									- humidity
									- light
									- magnetic
									- motion
									- orientation
									- pressure
									- proximity
									- rotation
									- step
									- temperature
							- Requires manual editing
							  collapsed:: true
								- Network access - instead use [AFWall](https://workflowy.com/#/e5f2eed18186)
								- Can't prevent C2DM messages - instead use a firewall and block xxx.mtalk.google.com:yyy for Google Play services
								- Storage access - If you want to confine apps to their own folder, see the example definitions about how this can be done with a custom restriction definition.
								  https://github.com/M66B/XPrivacyLua/tree/master/examples
						- XPrivacyLua is not a permission manager, but a privacy manager. XPrivacyLua doesn't block things and doesn't revoke permissions, but does replace real data by fake data. This means you can grant Android permissions to an app and still let XPrivacyLua prevent the app from seeing privacy sensitive data. Revoking permissions can result in an app refusing to work and/or to crash. However, replacing real by fake data generally doesn't let an app crash.
						- https://github.com/M66B/XPrivacyLua
						- https://forum.xda-developers.com/xposed/modules/xprivacylua6-0-android-privacy-manager-t3730663
					- Previous - XPrivacy
					  collapsed:: true
						- [cloned] https://github.com/M66B/XPrivacy
						- Maintenance and bug fixes needed as well as keeping it up to date with newer Android versions
						- Dev says he's spent >2500 hours on it and there's not enough interest (he's basically the solo maintainer)
						  https://forum.xda-developers.com/xposed/modules/xprivacy-ultimate-android-privacy-app-t2320783/post71999237#post71999237
						- Requires an Xposed for Android 7 first
				- [Top identifiers it fakes](https://github.com/M66B/XPrivacyLua/blob/master/README.md)
				  collapsed:: true
					- _Standard permissions_
						- Activity (sensors), calendars, call log, contacts, location, messages, camera
						- Mainly useful to fake if the apps won't work without permission access, or if more nuanced permission access is required
							- Example: can block certain people from being seen in contacts
					- _Other_
						- Get applications (hide installed apps and widgets) required for "share to other app"
						- Read account name (fake name, mostly e-mail address)
						- Read notifications (fake status bar notifications)
						- Read network data (hide cell info, Wi-Fi networks, fake Wi-Fi network name)
						- Read sync data (hide sync data)
						- Record audio (prevent recording)
						- Record video (prevent recording)
						- Use analytics (Fabric/Crashlytics, Facebook app events, Firebase Analytics, Google Analytic, Mixpanel, Segment)
						- Use tracking (fake user agent for WebView only, Build properties, network/SIM country/operator)
					- _Defunct_
						- Hardware identifiers hidden in Android 10+
						  _See_ [Apps can't access unique hardware identifiers directly](https://workflowy.com/#/f6d2f1127964)
						- Clipboard access only accessible by foreground app (plus needed for copying and pasting text)
						  [Clipboard access prevented for background apps](https://workflowy.com/#/0a65f19ef324)
				- List of apps which won't work with heavy XPrivacyLua restrictions
				  id:: 649b13cf-237a-44bc-906e-818b273bea78
				  collapsed:: true
					- _Crashes immediately_
						- Yahoo Weather
						- TextMeUp
					- _Crashes soon after boot_
						- See [Tinder](https://workflowy.com/#/1d745abfd07e)
						- Upwork
						- See [Citymapper](https://workflowy.com/#/35535435574e)
						- Todoist (requires Tracking, )
					- {Archive}
						- _Crashes immediately_
							- Action Launcher 3
							  collapsed:: true
								- Alternatives which have Covers
									- ((649b13ce-20b8-4de2-85e2-d39f540deb85))
									- Apex Launcher
									- Xposed GEL Settings
										- Requires v5.14 of Google Search app
								- 18/9/18 - swapped to Nova Launcher (Prime) because Action Launcher 3 keeps crashing and even via Titanium I can't recover it again
				- Installing
				  collapsed:: true
					- [Virtual XPosed](<[https://f-droid.org/en/packages/io.va.exposed/](https://f-droid.org/en/packages/io.va.exposed/)>) + [XPrivacyLua](<a href="https://www.f-droid.org/en/packages/eu.faircode.xlua/">https://www.f-droid.org/en/packages/eu.faircode.xlua/</a>) is what you're looking for.
			- Network (eg AFWall+)
			  collapsed:: true
				- _ROMs_
					- LineageOS has internet permission for each app, but doesn't have a whitelist mode nor native networks logs
				- _Apps_
					- AFWall
					  id:: 649b13cf-a724-4193-93dd-3f200c359a0d
					  collapsed:: true
						- _Related: GrapheneOS has this built-in?_
						  _See [Includes several inbuilt solutions that would otherwise need root functionality](https://workflowy.com/#/89a5425df166)_
					- [NetGuard](https://apt.izzysoft.de/fdroid/index/apk/eu.faircode.netguard)
					  id:: 649b13cf-caf2-4248-adbb-6e642bd536d9
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Simple UI
							- Cons
								- Can't be used simultaneously with a VPN
								- Pro version is closed-source?
						- FAQ
						  [https://github.com/M66B/NetGuard#frequently-asked-questions-faq](https://github.com/M66B/NetGuard#frequently-asked-questions-faq)
							- [https://github.com/M66B/NetGuard/blob/master/FAQ.md](https://github.com/M66B/NetGuard/blob/master/FAQ.md)
						- 1 euro for Pro version
						  [https://contact.faircode.eu/?product=netguardstandalone](https://contact.faircode.eu/?product=netguardstandalone)
			- Battery optimisation
			  collapsed:: true
			  id:: 631fa93c-15e7-4ef2-9b41-a116b90d39bd
				- Non battery optimised apps
				  Settings > Apps > special app access > Advanced > Battery > Battery optimization
					- Alarm Klock
					- App store by GrapheneOS
					- ((631fa93c-54bb-47c9-a344-baa7b9c76215))
					- Discord
					- ((649b13ce-1fe5-4f94-b330-5dcef6fb807e))
					- EteSync
					- F-Droid
					- Geometric Weather
					- ((649b13ce-c4a3-4f27-87fb-25442ce2a9a0))
					- ((638e7c15-6b65-4f35-82c7-05460cb45d8d))
					- Neo Store
					- ((63207624-8cee-43e5-9123-70441ef78225))
					- Neo Backup
					- Signal
					- ((63216f53-22cf-428a-9193-e5a423158e2b))
					- Syncthing-Fork
					- Your Local Weather
				- Battery lifetime optimisation
					- When plugged into a charger/PC
						- Phone-side decides whether it'll charge (the Integrated Controller)
						  source:: [https://stackoverflow.com/a/34720251](https://stackoverflow.com/a/34720251)
					- Advanced Charging Controller (ACC) - Magisk module
					  [https://github.com/VR-25/acc/](https://github.com/VR-25/acc/)
		- # Sorted by download method
		  id:: 644c0ace-86c4-434b-be9f-d475fa53c28a
			- ((6513e187-8f79-48e6-8db3-f8038bbfda5a)) apps
			  id:: 649b13cf-e2cb-4e21-8bf4-27f84e9b79f3
			  collapsed:: true
			  Last updated: [[2024-11-05 Tuesday]]
				- Meta
					- [F-Droid](https://f-droid.org)
					  id:: 6513e187-8f79-48e6-8db3-f8038bbfda5a
					  collapsed:: true
						- Pros/Cons
							- Compared to Accrescent
							  id:: 644c0ace-6f23-4066-b43f-3eec2c270acc
								- F-Droid pros
									- [They're for FOSS software](https://teddit.froth.zone/r/fossdroid/comments/ypqe19/opinion_on_privacyguidesorg_discouraging_people/ivkn52k/?context=3)
									- [izzyondroid hosts apps like libretube and vimusic which are available in official repo, is this by design or it's something that should be reported? and if it's by design how can i prioritize official repo over third-party ones in this situation? : fossdroid](https://teddit.froth.zone/r/fossdroid/comments/zmlzw3/izzyondroid_hosts_apps_like_libretube_and_vimusic/j0bz67e/?context=3)
									- [Are F-Droid app any less vulnerable to manipulation than Google Play apps? : fdroid](https://teddit.froth.zone/r/fdroid/comments/yav6fp/are_fdroid_app_any_less_vulnerable_to/itilkdo/)
									- [izzyondroid hosts apps like libretube and vimusic which are available in official repo, is this by design or it's something that should be reported? and if it's by design how can i prioritize official repo over third-party ones in this situation? : fossdroid](https://teddit.froth.zone/r/fossdroid/comments/zmlzw3/izzyondroid_hosts_apps_like_libretube_and_vimusic/j0bz67e/?context=3)
									- https://teddit.froth.zone/r/fossdroid/comments/ypqe19/opinion_on_privacyguidesorg_discouraging_people/ivkn52k/?context=3
								- Accrescent pros
								- Unsure
									- They don't allow 3rd-party repos
								- Accrescent vs IzzyOnDroid
									- Apps don't need to be open-source, split APKs are fully supported, metadata verification is more robust, (unattended) unprivileged updates are supported in the official client, and (in my opinion - you may read the docs for yourself) Accrescent has more strict quality control requirements.
									- From the developer's side, only stricter SDK requirements. On the client side, the auditing and quality control is much more thorough.
						- # Setup
						  id:: 6729ee56-7b89-45e7-b2ae-f6f71fccf575
							- Settings > Manage installed apps
							- Settings > Repositories
								- [NewPipe upstream repository](https://archive.newpipe.net/fdroid/repo?fingerprint=E2402C78F9B97C6C89E97DB914A2751FDA1D02FE2039CC0897A462BDB57E7501)
								- [IzzyOnDroid](https://apt.izzysoft.de/fdroid/repo?fingerprint=3BF0D6ABFEAE2F401707B6D966BE743BF0EEE49C2561B9BA39073711F628937A)
								- [KDE repo](https://cdn.kde.org/android/stable-releases/fdroid/repo/?fingerprint=13784BA6C80FF4E2181E55C56F961EED5844CEA16870D3B38D58780B85E1158F)
								- [Guardian Project](https://guardianproject.info/fdroid/repo?fingerprint=B7C2EEFD8DAC7806AF67DFCD92EB18126BC08312A7F2D6F3862E46013C7A6135)
							- Display > enable `Use pure black background in dark theme`
							- Other > enable `Expert mode`
							- Expert mode > enable `Keep install history`
						- # Troubleshooting
							- Unattended updates no longer working on ((63209286-6f40-4063-9fdc-2543251d416e))
								- Due to the Sensors permission, is being fixed
									- https://gitlab.com/fdroid/fdroidclient/-/merge_requests/1410
									- https://gitlab.com/fdroid/fdroidclient/-/merge_requests/1413
				- _Currently installed apps from F-Droid_
					- Acode editor
					  collapsed:: true
						- Android code editor
					- Acatus-Photon
					- addy.io
					  collapsed:: true
						- Changelog
						  [[Just a moment...](https://gitlab.com/Stjin/-android/-/blob/master/CHANGELOG.md](https://gitlab.com/Stjin/-android/-/blob/master/CHANGELOG.md))
					- [Aegis Authenticator](https://f-droid.org/en/packages/com.beemdevelopment.aegis/)
					  id:: 66def4fb-d36b-4bff-8549-5642b8d4712e
					  collapsed:: true
					  for ((670bdaca-259b-4639-8ad8-cf380b048772))
					- [AirGuard](https://github.com/seemoo-lab/AirGuard)
					  id:: 672a4be6-8a69-40f9-8fd8-448d1d236843
					  collapsed:: true
					  AKA bluetooth trackers warning / unknown tracker alerts
						- On ((63209286-6f40-4063-9fdc-2543251d416e)) this is probably the more private solution for ((6730c86c-4c5d-4ab1-bb2c-710e8d89e73d)) rather than using Google's service
						- GOS : ((6730cbe0-e9d9-435a-908b-afba1637fd5f)) - enable Bluetooth scanning. Also grant this app the Nearby Devices permission. This allows periodic Bluetooh scanning whilst the Bluetooth setting is off
					- Alarm Klock
					  collapsed:: true
						- Changes
						  [[Page not found · GitHub](https://github.com/kraigs-android/kraigsandroid/commits/master](https://github.com/kraigs-android/kraigsandroid/commits/master))
					- Amaze (File Manager)
					- Andor's Trail
					- Anemo
					  id:: 672a4c4f-e143-4db3-b876-26460d5cacb2
					- AnkiDroid
					  id:: 649b13cf-ae6f-4669-8c7f-e8768f538e70
					  collapsed:: true
						- Changelog
						  [[404 Not Found](https://docs.ankidroid.org/changelog.html](https://docs.ankidroid.org/changelog.html))
					- [AntennaPod](https://antennapod.org/)
					  id:: 63ff8145-0876-4aa6-b1d7-b362e5fb8cd6
					  collapsed:: true
						- Pros/Cons
							- Pros
								- ((671d6a9e-2e9e-47bf-9920-3d9205c200be))
							- Cons
								- Lacks
									- https://github.com/AntennaPod/AntennaPod/issues/4159
									  [Ability to skip ads in the podcast - Feature request - AntennaPod Forum](https://forum.antennapod.org/t/ability-to-skip-ads-in-the-podcast/212)
									-
									-
						- Changelog
						  [https://github.com/AntennaPod/AntennaPod/releases](https://github.com/AntennaPod/AntennaPod/releases)
					- APK Explorer & Editor
					- App Manager - Android package manager
					- aShell You
					- Audile
					- Audio Recorder
					- Audire
					- Aurora Store
					  id:: 63209285-ef03-44e2-8e84-34e7f088906f
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Cons
							  collapsed:: true
								- Even when using this LOTS of personal data has to be sent to Google in order to download an app
								  collapsed:: true
									- Even if you use Aurora Store anonymous login, the fingerprint is very unique and include totally unique IDs like the Android ID
									- Post
									  source:: [https://teddit.net/r/fdroid/comments/kxf860/is_there_any_difference_between_downloading_an/gjbkj0x](https://teddit.net/r/fdroid/comments/kxf860/is_there_any_difference_between_downloading_an/gjbkj0x)
									  collapsed:: true
										- Whenever you download and install an application on Google Play, these data are automatically transmitted to the developer via the Play Developer Console:
										  collapsed:: true
											- System-on-chip name
											- Application binary interface
											- Number of cores
											- GraphicsLibraryES Version
											- Available RAM
											- Screen class
											- Density class
											- Screen width
											- Screen height
											- Device-independent pixel width
											- Device-independent pixel height
											- Screen refresh rate (for some apps, usually games)
											- Android version
											- Android SDK
											- Device brand
											- Device model
											- Device Manufacturer (OEM)
											- Virtual Machine
											- Android ID (supposed to be reserved for “privileged” apps)
											- Advertising ID
											- Play Referral ID
											- Root state (especially for security-oriented and banking apps)
											- ((649b13d2-3bf6-43ed-b52c-7bbcf094ca3c)) state (for security-oriented and banking apps)
											- Available sensors (including significant_motion, wake_gesture, glance_gesture, and stationary_detect sensors; typically for pedometer utilities, navigation apps, etc.)
											- Google Account email (ostensibly for feedback, but take a moment to contemplate the many ways in which this could be abused)
											- Approximate location (borough, county, city, state, etc.)
											- Country
											- Region
											- (Preferred) Language
											- Installation date and time
											- Uninstallation date and time (also used to arbitrate refunds)
										- When you buy an app (or subscribe to an ezine) via Google Play, or perform an in-app transaction, these data are also transmitted:
										  collapsed:: true
											- Asset purchased
											- (Subscription schedule)
											- Transaction value
											- Transaction currency
											- Transaction date and time
											- Transaction state
											- Card Issuer
											- Resolving merchant and/or bank
						- Changelog
						  [https://gitlab.com/AuroraOSS/AuroraStore/blob/HEAD/CHANGELOG](https://gitlab.com/AuroraOSS/AuroraStore/blob/HEAD/CHANGELOG)
						- [https://auroraoss.com/faq/#aurora-store](https://auroraoss.com/faq/#aurora-store)
						- Lacks
						  collapsed:: true
							- Multi-account support
							  collapsed:: true
							  [https://gitlab.com/AuroraOSS/AuroraStore/-/issues/606](https://gitlab.com/AuroraOSS/AuroraStore/-/issues/606)
								- ((644c0ad0-fe5c-4a48-ad2d-d2ed42b11637))
						- [It uses ](https://workflowy.com/#/57988614d2dd)<a href="https://workflowy.com/#/57988614d2dd">Aurora</a><a href="https://workflowy.com/#/57988614d2dd"> Store to update Google Play apps</a>
						- [https://auroraoss.com](https://auroraoss.com)
						- 1 Backlink
						  collapsed:: true
							- See [Aurora](https://workflowy.com/#/b8a1c067853c)<a href="https://workflowy.com/#/b8a1c067853c"> Store</a>
					- Auxio
					- [BCR-GUI](https://github.com/nicorac/bcr-gui)
					  collapsed:: true
						- GUI for
					- Breezy Weather
					- Briar
					  collapsed:: true
						- Briar for mobile darknet chat
						  collapsed:: true
							- https://code.briarproject.org/akwizgran/briar/wikis/Roadmap
							- https://briarproject.org/
						- Changelog
						  [https://code.briarproject.org/briar/briar/-/wikis/changelog](https://code.briarproject.org/briar/briar/-/wikis/changelog)
						- 3 Backlinks
						  collapsed:: true
							- See [Briar](https://workflowy.com/#/7f8fcb8c2496)
							- Must have cryptographically assured anonymity e.g. Signal's Sealed Sender, [Briar](https://workflowy.com/#/7f8fcb8c2496)'s Tor hidden services
							- Use Session, [Briar](https://workflowy.com/#/7f8fcb8c2496) or other anonymous messaging
					- Cache Cleaner
					- Caffeinate
					- Call Recorder
					  id:: 631fa93c-54bb-47c9-a344-baa7b9c76215
					  collapsed:: true
					  `com.github.axet.callrecorder`
						- [[404 Page Not Found | F-Droid - Free and Open Source Android App Repository](https://f-droid.org/packages/com.github.axet.callrecorder/](https://f-droid.org/packages/com.github.axet.callrecorder/))
						- To enable
						  collapsed:: true
							- On LineageOS I had to activate manual call recording once - [Use com.android.dialer (AKA "Telephone") ](https://workflowy.com/#/b4d5a9fe7f15)
						- Thu, Sep 2, 2021 - on my phone I currently have Call Recorder as a user app, system app, and have a Magisk module for it. not sure what's the bare essentials, but it works
						  collapsed:: true
							- [https://gitlab.com/axet/android-call-recorder/-/issues/142](https://gitlab.com/axet/android-call-recorder/-/issues/142)
							- [https://gitlab.com/axet/android-call-recorder/-/issues/157](https://gitlab.com/axet/android-call-recorder/-/issues/157)
						- 3 Backlinks
						  collapsed:: true
							- Has to be enabled at the start of each call, unless you use a different app like [Call Recorder (com.github.axet.callrecorder)](https://workflowy.com/#/d36098ce1215) from F-Droid for automatic call recording
							- See [Call Recorder (com.github.axet.callrecorder)](https://workflowy.com/#/d36098ce1215) from F-Droid
							- See [Call](https://workflowy.com/#/d36098ce1215)<a href="https://workflowy.com/#/d36098ce1215"> </a><a href="https://workflowy.com/#/d36098ce1215">Record</a><a href="https://workflowy.com/#/d36098ce1215">er</a> from F-Droid
					- Canta
					- Catima - Loyalty Card Manager
					- Chrono
					- Chronos
					- Clima
					- CoinWatch
					- ConnectBot
					  id:: 639c2414-bbb3-46bd-bb3c-1ce6a8a4ee16
					  collapsed:: true
						- How to setup
						  collapsed:: true
							- Generate ed25519 keys with password protection
							- Name it e.g. `Android PocoF1`
							- Hold-click on the key and copy the public key
							- _On PC_
							  collapsed:: true
								- SSH into server
								- `nano ~/.ssh/authorized_keys`
								- Paste in the public key
					- Cryptomator
					  collapsed:: true
						- Changelog
						  [[Page not found · GitHub](https://github.com/cryptomator/android/releases](https://github.com/cryptomator/android/releases))
					- CryptoTracker
					- CoinTrend
					- Currencies
					- Decisions
					- ((663b24fb-e901-4314-abf8-6f0c529ade12))
					- Dicer
					- DiskUsage
					  id:: 644c0acd-0d02-4c23-8f82-dc7c50d3c9b2
					- Drinkable
					- DroidFS
					  collapsed:: true
						- Changelog
						  [https://forge.chapril.org/hardcoresushi/DroidFS/releases](https://forge.chapril.org/hardcoresushi/DroidFS/releases)
						- What
						  collapsed:: true
							- DroidFS allows you to create encrypted virtual volumes on which you can safely store and access files.
							- Currently, DroidFS supports only **gocryptfs**.
						- FOSS version of EDS basically
						- Related: ((672a4c4f-e143-4db3-b876-26460d5cacb2))
					- Editor
					  collapsed:: true
						- by Bill Farmer
					- EDS Lite
					  id:: 649b13ce-01d9-4efd-b4c5-29d44b1ba1c9
					  collapsed:: true
						- Related: ((678cbc12-c466-43bf-b3ad-450b4f5e142f))
					- ((631fa97e-a0a9-406c-b7b9-20536d421090))
					- ((631fa97e-a0a9-406c-b7b9-20536d421090)) X
					- Elisa
					- Emerald Dialer
					- Energize
					- [Etar Calendar](https://f-droid.org/en/packages/ws.xsoh.etar/)
					  id:: 649b13ce-1fe5-4f94-b330-5dcef6fb807e
					  collapsed:: true
						- Note: LineageOS forked it to be their native calendar and likely have improved it too
						- Old feature requests
						  collapsed:: true
							- Show length in event in minutes and hours when selected
							  https://github.com/Etar-Group/Etar-Calendar/issues/144
							- Can't change calendar of previously created events
							  https://github.com/Etar-Group/Etar-Calendar/issues/101
							- \_Alternative \_Android app extending calendar notifications with snooze button and notifications persistance
							  https://github.com/quarck/CalendarNotification
						- [LineageOS Etar fork](https://github.com/LineageOS/android_packages_apps_Etar)
						  id:: 649b13ce-0e7b-4303-9ab3-8a71ad53ccb3
						  collapsed:: true
							- Cons
							  collapsed:: true
								- Etar Calendar is still updating often
					- Eternity
					- EteSync
					- Exodus
					- F-Droid Build Status
					- FakeTraveler
					- Fedilab Lite
					- [Fennec](https://f-droid.org/en/packages/org.mozilla.fennec_fdroid/)
					  id:: 649b13ce-166b-43de-bea7-4262b566ccce
					  collapsed:: true
					  F-Droid (FOSS ((63134593-906c-43b5-96fe-33dc2c34fda4)) build)
						- Changelog
						  [[404: Page Not Found](https://www.mozilla.org/en-US/firefox/android/86.0/releasenotes/](https://www.mozilla.org/en-US/firefox/android/86.0/releasenotes/))
						- Tweaks
						  collapsed:: true
							- ## https://addons.mozilla.org/en-US/firefox/addon/export-tabs-urls-and-titles/
							- Disabling accessibility/automatic text sizing improves performance
							  collapsed:: true
								- Disabling automatic text sizing improves performance
								  [https://teddit.net/r/firefox/comments/pa5aca/just_discovered_how_to_make_firefox_nightly_for/](https://teddit.net/r/firefox/comments/pa5aca/just_discovered_how_to_make_firefox_nightly_for/)
								- How to disable accessibility/automatic text sizing on
								  collapsed:: true
									- mobile Firefox
									  collapsed:: true
										- Settings > Accessibility
									- Desktop Firefox
									  collapsed:: true
										- accessibility.force_disabled to 1
									- Thunderbird
									  collapsed:: true
										- How to access about:config (Config Editor) on Thunderbird [https://support.mozilla.org/en-US/kb/config-editor](https://support.mozilla.org/en-US/kb/config-editor)
										- accessibility.force_disabled to 1
						- ((65d6fdef-36dc-4b22-83e8-a6e9eda3b23a))
					- Find My Device (FMD)
					- [FlorisBoard](https://github.com/florisboard/florisboard)
					  id:: 649b13ce-93ff-441e-b914-ff387f720e3b
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Pros
							  collapsed:: true
								- FLOSS Keyboard swipe typing app
								- Good Gboard replacement since it has better glide typing than ((644c0acd-e3aa-47ab-877f-3d8028e5086d))
								- Private clipboard manager
								  collapsed:: true
									- Note: can be circumvented by granting an app Accessibility access, as XClipper (F-Droid) demonstrated
									  collapsed:: true
										- It'll automatically see any copied text
										- Solution: bar internet access to any proprietary apps which have this
									- Optionally can use a private clipboard rather than system one
									- See clipboard history by long-pressing the ENTER button then selecting the icon
									  collapsed:: true
										- A more direct way to access it is by long-pressing enter and then selecting the clipboard manager icon or by setting a swipe pref to the clipboard manager show action.
								- Spell checker can be added
								  collapsed:: true
									- [https://github.com/marcoagpinto/aoo-mozilla-en-dict](https://github.com/marcoagpinto/aoo-mozilla-en-dict)
							- Cons
							  collapsed:: true
								- [Could use with better word prediction](https://github.com/florisboard/florisboard/issues/642)
								- Next word predictions
								- Lacks
								  collapsed:: true
									- [Can't change emoji platform style](https://github.com/florisboard/florisboard/issues/660)
									- [Lacks gif search](https://github.com/florisboard/florisboard/issues/53)
									- [Private user dictionary](https://github.com/florisboard/florisboard/issues/109#issuecomment-756686959)
						- [Changelog](https://github.com/florisboard/florisboard/releases)
						- Related: ((644c0acc-dc08-4f95-a77e-d52a9bb2ebed))
					- Fossify Calendar
					- Fossify Contacts
					- Fossify File Manager
					- Fossify Gallery
					- Fossify Music Player
					- Fossify Phone
					- Git+ Coach
					- Glider for Hacker News
					  id:: 6313456a-25bf-46e1-8d2e-68062a24bae6
					  collapsed:: true
						- how to delete HN comments [Ask HN: You cannot delete comments posts or your account on HN. Concerned? | Hacker News](https://news.ycombinator.com/item?id=23622865)
					- GMaps WV
					- Goodtime - Pomodoro Timer
					- [HeliBoard](https://github.com/Helium314/HeliBoard)
					  id:: 65ce1d71-7db1-46e3-a4e3-1d91107c81c2
					  collapsed:: true
					  AKA ((65ce1d86-1db9-41a4-8f71-8dffffb2c5de))
						- Pros/Cons
						  collapsed:: true
							- ## Pros
							- Cons
							  collapsed:: true
								- Lacks
								  collapsed:: true
									- [Copy and paste keyboard shortcuts don't work](https://github.com/Helium314/HeliBoard/issues/319) (whilst using scrcpy)
							- Unclear
							- Comparisons
						- https://codeberg.org/Helium314/aosp-dictionaries
						- add nouserlib version for people concerned about security implications of loading user-provides libraries. if this version is installed as system app, and swypelibs are available for the system, they will be used
						- Rebrand of
						  collapsed:: true
							- [OpenBoard](https://github.com/Helium314/openboard)
							  id:: 65ce1d86-1db9-41a4-8f71-8dffffb2c5de
						- [Hidden functionality](https://github.com/Helium314/HeliBoard?tab=readme-ov-file#hidden-functionality)
						  collapsed:: true
							- Long-pressing the Clipboard Key (the optional one in the suggestion strip) pastes system clipboard contents.
							- Long-pressing keys in the suggestion strip toolbar pins them to the suggestion strip.
							- Long-press the Comma-key to access Clipboard View, Emoji View, One-handed Mode, Settings, or Switch Language:
							  collapsed:: true
								- Emoji View and Language Switch will disappear if you have the corresponding key enabled;
								- For some layouts it's not the Comma-key, but the key at the same position (e.g. it's `q` for Dvorak layout).
							- When incognito mode is enabled, no words will be learned, and no emojis will be added to recents.
							- Sliding key input: Swipe from shift to another key to type a single uppercase key
							  collapsed:: true
								- This also works for the `?123` key to type a single symbol from the symbols keyboard, and for related keys.
							- Long-press the `?123` from main view to directly open numpad.
							- Long-press a suggestion in the suggestion strip to show more suggestions, and a delete button to remove this suggestion.
							- Swipe up from a suggestion to open more suggestions, and release on the suggestion to select it.
							- Long-press an entry in the clipboard history to pin it (keep it in clipboard until you unpin).
							- Swipe left in clipboard view to remove an entry (except when it's pinned)
							- You can add dictionaries by opening the file
							  collapsed:: true
								- This only works with _content-uris_ and not with _file-uris_, meaning that it may not work with some file explorers.
							- _When using debug mode / debug APK_
							  collapsed:: true
								- Long-press a suggestion in the suggestion strip twice to show the source dictionary.
								- When using debug APK, you can find Debug Settings within the Advanced Preferences, though the usefulness is limited except for
								  dumping dictionaries into the log.
								- In the event of an application crash, you will be prompted whether you want the crash logs when you open the Settings.
								- When using multilingual typing, space bar will show an confidence value used for determining the currenly used language.
								- Suggestions will have some tiny numbers on top showing some internal score and source dictionary (can be disabled)
							- For users doing manual backups with root access: Starting at Android 7, some files and the main shared preferences file are not in the default location, because the app is using [device protected storage](<https://developer.android.com/reference/android/content/Context#createDeviceProtectedStorageContext()>). This is necessary so the settings and layout files can be read before the device is unlocked, e.g. at boot. The files are usually located in `/data/user_de/0/<package_id>/`, though the location may depend on the device and Android version.
						- Related: ((644c0acc-dc08-4f95-a77e-d52a9bb2ebed))
					- Hypatia
					- I2P
					- ICSx
					  collapsed:: true
						- Changelog
						  [https://forums.bitfire.at/category/5/icsx?tag=announcement](https://forums.bitfire.at/category/5/icsx?tag=announcement)
					- ImgurViewer
					- InnerTune
					- Jerboa for Lemmy
					- ((63a9ade4-acd5-44f9-9166-2c1393865f7a))
					- KDE Itinerary
					- KeePassDX
					  id:: 649b13ce-ab97-4433-9643-95bcf3802a8d
					  collapsed:: true
						- Changelog
						  [[Page not found · GitHub](https://github.com/Kunzisoft/KeePassDX/blob/HEAD/CHANGELOG](https://github.com/Kunzisoft/KeePassDX/blob/HEAD/CHANGELOG))
					- Koler
					- Kotatsu
					- Kriptofolio
					- Lab+ for Gitlab
					- LabCoat
					- LabNex for GitLab
					- Lemuroid
					- LibChecker
					- ((649b13ce-ebbe-44ce-8f19-72f42b3766f3))
					- LibreTrack
					- LibreTranslator
					- Lichess
					- Linphone
					- Logcat Reader
					  collapsed:: true
						- Changelog
						  [[Page not found · GitHub](https://github.com/darshanparajuli/LogcatReader/releases](https://github.com/darshanparajuli/LogcatReader/releases))
					- Logseq
					- [Loop Habit Tracker](https://f-droid.org/app/org.isoron.uhabits)
					  id:: 644c0acd-8a99-465f-bbb4-e96b62092b69
					  collapsed:: true
						- [GitHub - iSoron/uhabits: Loop Habit Tracker, a mobile app for creating and maintaining long-term positive habits](https://github.com/iSoron/uhabits)
						-
					- Massive
					- Material Files
					- [Media Merger](https://f-droid.org/en/packages/com.github.axet.mover/)
					  id:: 649b13ce-c4a3-4f27-87fb-25442ce2a9a0
					  collapsed:: true
						- [Doesn't work on Android 16 (#21) · Issues · axet / android-media-merger · GitLab](https://gitlab.com/axet/android-media-merger/-/issues/21)
						  id:: 68737102-44f2-43ee-abc6-d0a87ca5fc42
						- Changes
						  [[Not Found](https://gitlab.com/axet/android-media-merger/-/commits/master](https://gitlab.com/axet/android-media-merger/-/commits/master))
						- _Usecase_
						  collapsed:: true
							- Android uses FAT partition for `/sdcard/`, which doesn't support symbolic links
						- Alernative
						  collapsed:: true
							- [File Navigator](https://f-droid.org/packages/com.w2sv.filenavigator/)
							- Tasker
							  collapsed:: true
								- - Lightweight, likely won't have to update the scripts for years
								- - Steep learning curve
							- FolderSync
							  collapsed:: true
								- - Simple setup
								- - Cluttered, especially if I add more remote sync folders later
						- {Archive}
						  collapsed:: true
							- _Issue <time startYear="2021" startMonth="1" startDay="11"_ > fix pushed within a few weeks
							  collapsed:: true
							  [https://gitlab.com/axet/android-media-merger/-/issues/17](https://gitlab.com/axet/android-media-merger/-/issues/17)
								- Crashes when trying to set the target folder location
					- Medito
					- Migu
					- Mindful Notifier
					- Mindustry
					- Mitch
					  collapsed:: true
						- Itch.io
					- MJ PDF
					- mpv-android
					  collapsed:: true
						- Changelog
						  [https://github.com/mpv-android/mpv-android/releases](https://github.com/mpv-android/mpv-android/releases)
					- MTG Familiar
					- ((638e7c15-6b65-4f35-82c7-05460cb45d8d))
					- MuPDF Viewer
					- NClientV2
					- Neo Launcher
					- ((649b13cf-caf2-4248-adbb-6e642bd536d9))
					  collapsed:: true
					- [NewPipe](https://newpipe.net/)
					  id:: 65166ca4-1398-465a-8ff7-029210238874
					  collapsed:: true
					  ((644c096b-7a26-4af2-a0b6-62d094da43ec)) FOSS player
						- [GitHub - TeamNewPipe/NewPipe: A libre lightweight streaming front-end for Android.](https://github.com/TeamNewPipe/NewPipe)
						  id:: 6521b316-6d1c-47c7-b059-bc5e78b55011
						- Pros/Cons
						  collapsed:: true
							- Pros
							  collapsed:: true
								-
							- Cons
							  collapsed:: true
								- wontfix
								  collapsed:: true
									- [Rumble support](https://github.com/TeamNewPipe/NewPipeExtractor/issues/779)
								- [A large rewrite is in-progress](https://github.com/orgs/TeamNewPipe/projects/14/views/1)
								  collapsed:: true
									- [NewPlayer](https://github.com/TeamNewPipe/NewPipe/issues/11603) component
									  id:: 670cf61a-fa0e-419d-a4bd-d952959cfe87
								- Lacks
								  collapsed:: true
									- [Self-hosted sync server](https://github.com/TeamNewPipe/NewPipe/issues/8039#issuecomment-1783924326)
									- [Sync between devices](https://github.com/TeamNewPipe/NewPipe/issues/5325#issuecomment-2308892832) (two devices using the NewPipe)
									- [Ports to other platforms](https://github.com/TeamNewPipe/NewPipe/issues/1051#ref-issue-2102264600) (sync with ((6313458c-20f9-43f5-be52-44845eb02203))? )
									- Syncing subscriptions and watch history with 3rd-party apps
									  collapsed:: true
										- Feature requests
										  collapsed:: true
											- [Self-host your own list of subscriptions · Issue #9973 · TeamNewPipe/NewPipe · GitHub](https://github.com/TeamNewPipe/NewPipe/issues/9973)
											- [Sync between devices · Issue #5325 · TeamNewPipe/NewPipe · GitHub](https://github.com/TeamNewPipe/NewPipe/issues/5325#issuecomment-2363348502)
										- [With FreeTube](https://github.com/TeamNewPipe/NewPipe/issues/3249)
										- Related: ((6313458c-20f9-43f5-be52-44845eb02203)) : ((6828d490-4762-44b2-81fc-cb1280d647fb))
									- [Search filter UI](https://github.com/TeamNewPipe/NewPipe/issues/2251#event-11365716946)
							- Unclear
							  collapsed:: true
								- A : ((670beffa-13af-4db8-bbb0-c417dae63081))
							- Comparisons
						- # Ecosystem
						  collapsed:: true
							- [Tubular](https://github.com/polymorphicshade/Tubular)
							  collapsed:: true
							  Fork that implements SponsorBlock and ReturnYouTubeDislike
								- https://apt.izzysoft.de/fdroid/index/apk/org.polymorphicshade.tubular
							- [BraveNewPipe](https://github.com/bravenewpipe/NewPipe)
							  id:: 653c075b-60af-4e96-b37a-b8f9be723440
							  collapsed:: true
							  Fork that supports ((649b1448-ca00-412e-83fe-fb9bb8279847)) and ((649b1448-a81c-40fc-b5be-d7e869f27b13)). Also supports Sponsorblock
								- Due to restrictive project policy, the NewPipeTeam refuses to add platforms that they find offensive. This fork (BraveNewPipe) will not be as restrictive. As long as the platforms work in the spirit of free speech, they could be integrated.
								- Issues can be opened in [this repo](https://github.com/bravenewpipe/NewPipeExtractor)
							- [PipePipe](https://github.com/InfinityLoop1308/PipePipe)
							  Fork that supports NicoNico and BiliBili
						- Related: ((6313458c-20f9-43f5-be52-44845eb02203))
					- Nitter for Android
					- Noice
					- Nova Video Player
					- ((663915c8-abda-4f12-8175-26e94f6c120d))
					- [Notification Notes](https://f-droid.org/en/packages/com.khuttun.notificationnotes/)
					  id:: 644c0acd-0b88-4709-acc6-a176b363d9c0
					  collapsed:: true
						- Current notes
						  collapsed:: true
							- **Title:** [Daily] 30m minimum coding-related work
							  id:: 666c73e7-a1a0-41f8-9d59-a86872c63268
							  collapsed:: true
								- **Description:**
								  collapsed:: true
								  Reason: Overemployed or FAANG is my best solution to avoiding Clown World. When I'm overqualified for these, then focus on startup/entreprReason: Overemployed or FAANG is my best solution to avoiding Clown World. When I'm overqualified for these, then focus on startup/entrepreneurship skills and projects.
								  
								  [New year's resolution]
									- Last updated: [[2024-06-14 Friday]]
									- More info
									  collapsed:: true
										- Reasons expanded
										  collapsed:: true
											- Also is a potential answer for my dating approach - which is to say, instead spend free time focusing on making lots of money for the next few years (until I'm 40?) so I can afford my own house
									- Old versions:
									  collapsed:: true
										- 2022? Anki review 1 flashcard per day + get a full-time developer job
										- 2020? 1 coding video per day
						- {Archive}
					- ((644c0acd-59dd-4065-a2e9-41351725caf8))
					- OCR
					- OCR (Tesseract)
					- OctoDroid
					- Offi
					  collapsed:: true
						- Changelog
						  [https://gitlab.com/oeffi/oeffi/-/blob/master/oeffi/CHANGES](https://gitlab.com/oeffi/oeffi/-/blob/master/oeffi/CHANGES)
						- [https://oeffi.schildbach.de/index.html](https://oeffi.schildbach.de/index.html)
					- Okular Mobile
					- Open Food Facts
					  collapsed:: true
						- [https://world.openfoodfacts.org/open-food-facts-mobile-app](https://world.openfoodfacts.org/open-food-facts-mobile-app)
						- Wikipedia of food products
					- Open Link With
					- Open Note Scanner
					- Open TimeLimit
					  collapsed:: true
						- Changelog
						  collapsed:: true
							- [https://codeberg.org/timelimit/opentimelimit-android/releases](https://codeberg.org/timelimit/opentimelimit-android/releases)
					- OpenKeychain
					  id:: 649b13ce-23ea-43bb-9041-7bb0b328707c
					  collapsed:: true
						- Changelog
						  [https://github.com/open-keychain/open-keychain/blob/HEAD/OpenKeychain/src/main/res/raw/help_changelog.md](https://github.com/open-keychain/open-keychain/blob/HEAD/OpenKeychain/src/main/res/raw/help_changelog.md)
						- Restore using this code
						  collapsed:: true
							- `7576-8309-8636-3451-0066-6219-9504-9222-1672`
							- Might need to do it multiple times for each key
							- Use ((63a9ade4-0cdf-4680-a839-6b6f92e57f51)) to type it in faster
						- Autocrypt setup
						  collapsed:: true
							- in Thunderbird app go to End-to-end encryption settings for a particular email address > `Send Autocrypt Setup Message`
					- Orbot
					- Organic Maps
					- [OsmAnd~](https://osmand.net)
					  id:: 649b13ce-e7da-4568-ae97-917c53a44c72
					  collapsed:: true
					  Maps & GPS Navigation
						- Changelog for OsmAnd~ (free version)
						  [https://osmand.net/help/changes.html](https://osmand.net/help/changes.html)
						- [https://github.com/osmandapp/Osmand](https://github.com/osmandapp/Osmand)
					- ((65ec1e05-1ff8-4f17-80c5-6f8d49f82f81))
					  id:: 65140ae3-550d-40a8-b0e8-0e757de81358
					- Package Manager
					  collapsed:: true
						- Changelog
						  [https://github.com/SmartPack/PackageManager/blob/HEAD/change-logs.md](https://github.com/SmartPack/PackageManager/blob/HEAD/change-logs.md)
					- PassAndroid
					- PCAPDroid
					  collapsed:: true
						- Logs network requests. Uses local VPN to do it (thus can't work at the same time as ((649b13cf-caf2-4248-adbb-6e642bd536d9)) firewall
					- [Permission Manager X](https://github.com/mirfatif/PermissionManagerX)
					  id:: 63219e35-8143-4405-873e-8c9a9b9dc7ff
					  collapsed:: true
						- Lacks
						  collapsed:: true
							- Can't set global defaults
							- Can't fake data like XPrivacyLua can
						- It can do far more than what Bouncer can
						  source:: http://localhost:8193/archive/1623017977.039395/singlefile.html
						- Related: ((6321aa1e-2671-43ee-993a-d32f42ed8c69))
					- Permission Pilot
					- Photok
					- PlainApp
					- Plexus
					- Podcini.R
					- PrivacyBreacher
					- QUIK SMS
					  collapsed:: true
						- Changelog
						  [https://github.com/moezbhatti/qksms/releases](https://github.com/moezbhatti/qksms/releases)
					- Quinb
					- [RedReader](https://f-droid.org/en/packages/org.quantumbadger.redreader/)
					  id:: 644c0acd-6ef9-4096-a978-11fac5b87b89
					- Routine Tracker
					- ((649b1407-36a5-447b-ba05-aa7a96f80a1b))
					- Save on Device
					- SecScanQR
					  collapsed:: true
						- Changelog
						  [https://github.com/Fr4gorSoftware/SecScanQR/releases](https://github.com/Fr4gorSoftware/SecScanQR/releases)
					- Secure photo viewer
					- Shattered Pixel Dungeon
					- [Shelter](https://f-droid.org/en/packages/net.typeblog.shelter/)
					  id:: 649b13ce-b4f8-45e9-857a-28eb2ad4ffd2
					  collapsed:: true
					  For setting up an Android Work Profile i.e.
						- Pros
						  collapsed:: true
							- Unlike Island and Insular, it blocks contacts searching
							  [https://secure-system.gitlab.io/Insular/faq.html](https://secure-system.gitlab.io/Insular/faq.html)
						- Related:
						  collapsed:: true
							- ((66028eb2-021c-4711-baa0-3ebcc7b05647)) : ((670bfaa4-c14d-4575-aad6-5f846468d6da))
							- [Remove Shelter - Tool Suggestions - Privacy Guides Community](https://discuss.privacyguides.net/t/remove-shelter/21658) instead of
							- ((63209286-6f40-4063-9fdc-2543251d416e)) : ((6734cfe5-e8f7-4cbe-ae3a-a32c97b63717))
							- https://f-droid.org/packages/com.hmdm.launcher/
							-
					- [Shizuku](https://shizuku.rikka.app/)
					  id:: 63209285-2e05-40f2-bce9-5b8d813eea86
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Cons
							  collapsed:: true
								- [GrapheneOS disallows shell (adb) to execute codes from apk, so Shizuku can't be used](https://github.com/GrapheneOS/platform_system_sepolicy/commit/fe67984a4070a6f840487e0e496a164e4e58b261)
							- Unclear
							  collapsed:: true
								- [Not entirely free, has some restrictions to prevent people distributing a self-compiled APK but it makes sense](https://github.com/RikkaApps/Shizuku/issues/69)
						- Summary: Good alternative for (superuser) rooting, it's basically an ADB Server that runs on the phone so it allows apps to tie into it and run commands that normally can only be run over ADB. Super useful for non-root users
						- Links
						  collapsed:: true
							- [Repo](https://github.com/RikkaApps/Shizuku/)
							- [Changelog](https://github.com/RikkaApps/Shizuku/releases)
						- [Documentation](https://shizuku.rikka.app/guide/setup/)
						  collapsed:: true
							- [Installation](https://android.izzysoft.de/repo/apk/moe.shizuku.privileged.api)
							- [Setup on](https://shizuku.rikka.app/guide/setup/?night=1#start-shizuku) ((63209286-6f40-4063-9fdc-2543251d416e))
							  collapsed:: true
								- Use the `Start via Wireless debugging` option
								  collapsed:: true
									- Note: need to click on `Wireless debugging` itself to show the `Pair device with pairing code` option
									- App Info > enable `Exploit protection compatibility mode`?
									  collapsed:: true
										- That should be sufficient without having to disable `Secure app spawning` system-wide
										  collapsed:: true
											- [Android settings - Security and privacy > Exploit protection > "Secure app spawning" may need to be disabled.](https://github.com/RikkaApps/websites/pull/79#issue-1751837442)
							- App compatibility
							  collapsed:: true
								- [[2024-11-11 Monday]] Using it for
								  collapsed:: true
									- ((66cf8e7e-185a-492d-8e00-d67e3b15d5f7))
									- ((63216f53-22cf-428a-9193-e5a423158e2b))
								- Compatible but I don't need the features
								  collapsed:: true
									- aShell You
									  collapsed:: true
										- [aShell](https://f-droid.org/en/packages/in.sunilpaulmathew.ashell/)
										  Local ADB shell
									- Aurora Store
									- Mihon
									- Obtainium
									- [Canta](https://f-droid.org/en/packages/org.samo_lego.canta/)
									  Delete system apps
									- Aniyomi
								- I don't current use
								  collapsed:: true
									- Insular, Darq, Hail,
								- Other
								  collapsed:: true
									- Mixplorer - browse app data
									- https://github.com/timschneeb/awesome-shizuku
									- https://github.com/legendsayantan/ShizuTools
									- List 1
									  collapsed:: true
										- **[Ambient Music Mod](https://github.com/KieronQuinn/AmbientMusicMod)**
										  Ports Now Playing from Pixels to other Android devices. To get get On Device recognition, it uses Shizuku (Android 12+) or root access (Android 9+).
										- **[AppLock](https://github.com/Mufanc/AppLock)**
										  Prevents specific apps from being killed by swipe or one-click cleanup. Theoretically supports Android 9~12, MIUI 12+. Beside root based Xposed Module, it's supports Shizuku-based Non-Root working mode.
										- **[Better Internet Tiles](https://github.com/CasperVerswijvelt/Better-Internet-Tiles)**
										  Brings back separate Wi-Fi and mobile data tiles on Android 12 which requires shell accesss, which can be granted using either Shizuku or root.
										- **[Blocker](https://github.com/lihenggui/blocker)**
										  A component controller for Android applications. Currently, it supports using PackageManager, Intent Firewall & Shizuku to control the state of components.
										- **[DarQ](https://github.com/KieronQuinn/DarQ)**
										  Provides a per-app selectable force dark option for Android 10 and above. It uses a root or Shizuku (ADB) service to apply the theme seamlessly and quickly, without needing an accessibility service.
										- **[DSU Sideloader](https://github.com/VegaBobo/DSU-Sideloader/)**
										  Helps users easily install GSIs via DSU's Android feature. It requires Android 10 or higher, Unlocked Bootloader Device with Dynamic Partitions & a GSI. From 2.01 it supports Shizuku besides adb commands as installation method.
										- **[Droid-ify](https://github.com/Iamlooker/Droid-ify)**
										  quick material F-Droid client which supports Shizuku to install applications and updates in the background like the root installer on non-rooted devices.
										- **[FreezeYou](https://github.com/FreezeYou/FreezeYou)**
										  A lightweight app freezer which helps saving battery and boosting speed of device as well as by disabling (and enabling when needed) some unnecessary apps. You can freeze/unfreeze apps automatically. It supports Shizuku besides many other options.
										- **[Hail](https://github.com/aistra0528/Hail)**
										  Freezes apps when they are unnecessary to use device in a better way, cuts down the usage of ram and saves power. User can unfreeze it to revert. There are two ways to "freeze" apps, hide and disable. There are two ways to "freeze" apps, hide and disable. Hail can work with Device Owner - Hide, Superuser - Disable and Shizuku - Disable.
										- **[Island](https://github.com/oasisfeng/island)**
										  Isolates & clones apps for privacy protection & parallel running. It can also freeze apps, to completely block its background behaviors, hide apps & use VPN only on one side, or different VPN on both sides. It supports cloning app instantly using Shizuku.
										- **[Key Mapper](https://github.com/keymapperorg/KeyMapper)**
										  Remaps buttons and fingerprint reader gestures to allow anyone to map their buttons in any combination to anything. It can map single or multiple key events to a custom action. Using Shizuku it can do more things without user input.
										- **[LSPatch](https://github.com/LSPosed/LSPatch)**
										  Rootless implementation of LSPosed framework, integrating Xposed API by inserting dex and so into the target apk utilizing Shizuku.
										- **[RootlessJamesDSP](https://github.com/ThePBone/RootlessJamesDSP)**
										  System-wide JamesDSP implementation for non-rooted Android devices.It supports Shizuku (Android 12+) & ADB (Android 10+). Undoubtedly it's the best FOSS alternative of Wavelet.
										- **[SAI](https://github.com/Aefyr/SAI)**
										  An advanced apk installer with split apk (APKS) support supports Shizuku as installer besides rootless & root.
										- **[SkyDroid](https://github.com/redsolver/skydroid)**
										  A decentralized domain-based Android App Store which offers easy and fast app distribution. Supports Shizuku to install & updates apps.
										- **[SystemUI Turner](https://github.com/zacharee/Tweaker)**
										  An app for viewing and modifying hidden settings on Android devices which utilizes ADB & Shizuku.
										- ((63209285-a267-4f3c-b28b-c8116948c1d1))
										  Manga reader for Android . Supports Shizuku to install Extensions in the backgroud.
										- ((649b13ce-0b9e-4741-ba6d-7959858e3443))
										  With rish, it's possible to connect to & interact with shell runs by Shizuku using Termux.
										- **[UpgradeAll](https://github.com/DUpdateSystem/UpgradeAll)**
										  Simplifies the process of finding updates for Android apps Magisk modules and more from various sources & supports Shizuku as an apk installation method.
									- [GitHub - SheeshTony/ShizukuApps: The ultimate curated list of Android apps that use Shizuku for enhanced functionality without root access. Updated September 2025](https://github.com/SheeshTony/ShizukuApps)
									-
								- [List2](https://github.com/ThePBone/awesome-shizuku)
						- Related:
						  collapsed:: true
							- ((63209284-e6f8-47bd-a47c-e2733cf7b886))
							- Their other apps
							  collapsed:: true
								- [Riru](https://github.com/RikkaApps/Riru) - deprecated now, integrated into Magisk as "Zygisk"
								- ((63217e1a-be03-48a4-8736-748f53ce30a4))
					- [Shosetsu](https://shosetsu.app/)
					  id:: 651ad3df-16ac-4b19-99d3-1f6db31a0372
					  collapsed:: true
						- ((651ad907-9c59-4259-b50d-553ee5778684))
						- Pros/Cons
						  collapsed:: true
							- Pros
							  collapsed:: true
								-
							- Cons
							  collapsed:: true
								- Lacks
								  collapsed:: true
									- [FanFiction.net support](https://gitlab.com/shosetsuorg/shosetsu/-/issues/331)
									- [AO3 support limited](https://gitlab.com/shosetsuorg/extensions/-/issues/246) - no Mature or Explicit. Also no browsing capability
									  collapsed:: true
										- ((644c09a1-3b99-4b7b-aa34-fff7d78df75a))
									- [Other Wildbow works](https://gitlab.com/shosetsuorg/extensions/-/issues/545)
							- Unclear
							- Comparisons
						- Links
						  collapsed:: true
							- [Extensions repo](https://gitlab.com/shosetsuorg/extensions)
							- [Shosetsu / Shosetsu · GitLab](https://gitlab.com/shosetsuorg/shosetsu)
							- [Old GitHub](https://github.com/shosetsuorg/shosetsu/issues)
						- Documentation
						  collapsed:: true
							- [Need to login to Questionable Questing via webview in order to access those stories in NSFW section](https://gitlab.com/shosetsuorg/extensions/-/issues/546)
						- Replacement for
						  collapsed:: true
							- [QuickNovel](https://apt.izzysoft.de/fdroid/index/apk/com.lagradost.quicknovel)
							  id:: 6318fc64-a6a0-41b2-b84f-1a9cd3c04fc5
							  collapsed:: true
								- [GitHub - LagradOst/QuickNovel: Android app for downloading novels](https://github.com/LagradOst/QuickNovel)
								- Lacks
								  collapsed:: true
									- [Enable selecting text · Issue #169 · LagradOst/QuickNovel · GitHub](https://github.com/LagradOst/QuickNovel/issues/169)
									  id:: 651adc29-69fc-49ec-9a79-11baec362469
									- [[Source request] SpaceBattles · Issue #142 · LagradOst/QuickNovel · GitHub](https://github.com/LagradOst/QuickNovel/issues/142)
									- [[Source Request] fanfiction.net · Issue #86 · LagradOst/QuickNovel · GitHub](https://github.com/LagradOst/QuickNovel/issues/86)
									- https://github.com/LagradOst/QuickNovel/issues/60#event-6193935458
								- Moved to ((651ad3df-16ac-4b19-99d3-1f6db31a0372)) mainly because of ((651adc29-69fc-49ec-9a79-11baec362469))
					- [Showly](http://showlyapp.com/)
					  id:: 63ff8144-7cca-483b-8160-9ce8896b3247
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- ((644c0b31-7dfc-45f6-bc2a-8c7bcd441043))
							- Cons
							  collapsed:: true
								- [Better widescreen display support · Issue #958 · michaldrabik/showly · GitHub](https://github.com/michaldrabik/showly/issues/958)
								- Lacks
								  collapsed:: true
									- [Scheduled backups · michaldrabik/showly · Discussion #988 · GitHub](https://github.com/michaldrabik/showly/discussions/988)
									- [F-Droid](https://github.com/michaldrabik/showly-2.0/issues/46#issuecomment-700575881)
									- [Export as XML](https://github.com/michaldrabik/showly-2.0/issues/453)
									  collapsed:: true
										- 3rd party projects for ((66a2459c-ea0b-4d10-89ac-908a5fb4ac44)) backup
										  collapsed:: true
											- [My profile - 3Scoop](https://trakt.tv/users/3scoop)
											- https://darekkay.com/blog/trakt-tv-backup/ (https://gist.github.com/darekkay/ff1c5aadf31588f11078)
											- https://pypi.org/project/traktexport/
											- https://github.com/xbgmsharp/trakt]
									- Local database for ratings, comments and tags
									- How does it handle shows being deleted on server side?
									- [Info tab for each show](https://github.com/michaldrabik/showly-2.0/issues/173)
									- [Rewatch history](https://github.com/michaldrabik/showly-2.0/issues/158)
									- [Recommendations tab](https://github.com/michaldrabik/showly-2.0/issues/159)
									- [Scattered progress bar](https://github.com/michaldrabik/showly-2.0/issues/171)
									- Ignore show
						- [GitHub - 1RandomDev/showly-oss: Fork of the Showly app without Google Trackers.](https://github.com/1RandomDev/showly-oss)
						  collapsed:: true
							- [Removed button to unlock premium features · michaldrabik/showly-2.0@af6f628 · GitHub](https://github.com/michaldrabik/showly-2.0/commit/af6f62838f2fede1ba16afc3be2513a70a4bc80b)
						- Ratings
						  id:: 651ada65-a58a-40fd-8af7-3e6f03fb9cb4
						  collapsed:: true
							- Meta
							- Scoring levels
							  collapsed:: true
								- collapsed:: true
								  10. Masterpiece = A flawless or near-flawless work of art. This rating is reserved for the very best, where every element comes together beautifully.
									- Either
									  collapsed:: true
										- Massive fanbase, loved by fans of the genre as it's a classic of it, a pinnacle
										- Universally-liked, so it's a Can't-Miss for virtually anyone as it even transcends people's genre preferences
										- An all-time favourite of mine thanks to it's genre, storytelling, characters etc
										- Very memorable for much of the content
								- collapsed:: true
								  9. Excellent = Near-perfect in execution. Captivating, well-crafted, and memorable, with only the smallest of issues.
									- Either
									  collapsed:: true
										- Large fanbase, though it may have some small issues or competition which prevent it become a genre-classic
										- Universally-mildly liked
										- A pinnacle of a genre, but not necessarily my favourite type of genre. Can't-Miss for genre fans
										- Unique and/or high-quality enough to deserve a top spot but has some very small issues
										- Large parts or good number of scenes will be memorable
								- collapsed:: true
								  8. Very Good = Highly enjoyable with strong performances and production. Any flaws are minor and don't significantly detract from the experience.
									- Either
									  collapsed:: true
										- Decent fanbase, though some issues or genre competition that prevent it from taking the top spot in the genre
										- Universal-neutral reaction at minimum (few are going to hate it)
										- Some scenes will be memoryable
								- collapsed:: true
								  7. Good = A solid piece of entertainment. The story, acting, and production are well-done, though not without minor issues.
									- Enjoyable viewing but probably won't be memorable
								- 6. Decent = Somewhat enjoyable with noticeable flaws. It has its moments, but overall it's just above average.
								- 5. Mediocre = A mixed bag with as many flaws as strengths. It may be passable for a casual watch but lacks lasting impact.
								- 4. Below Average = Has some potential or moments of interest, but numerous shortcomings in plot, pacing, or production bring it down.
								- 3. Poor = Significant problems in multiple areas. The few positive aspects are overshadowed by a generally weak execution.
								- 2. Terrible = Barely any redeeming qualities. Flawed storytelling, poor performances, and technical issues dominate the experience.
								- 1. Abysmal = A complete failure on every level. The plot, acting, and production are severely lacking, making it unwatchable.
							- Related: ((65f9db9a-0ca1-4c2c-8edc-ede1e7ab2f53))
					- SilverDict
					- Simple Contacts Pro
					- SimplyTranslate Mobile
					- Spotube
					- Squawker
					- Squircle CE - Code Editor
					- Stealth
					- Step and Height Counter
					- Stocks Widget
					- StreetComplete
					  collapsed:: true
						- Changelog
						  [https://github.com/streetcomplete/StreetComplete/releases](https://github.com/streetcomplete/StreetComplete/releases)
					- [Syncthing-Fork](https://f-droid.org/en/packages/com.github.catfriend1.syncthingandroid/)
					  id:: 649b13ce-c5f5-4c70-a58f-6f411b515aaa
					  collapsed:: true
						- Full restore
						  id:: 672bfa93-b520-4b0e-8061-bbce191522cf
						  collapsed:: true
							- Settings > Behaviour > enable `Autostart`
							- Add device to desktop [[Software]] : [Syncthing](((6312a076-d503-40c4-b98f-cbdef17b1fcb)))
							  collapsed:: true
								- On mobile app check the Device ID and copy it > on desktop web Syncthing add a new device and use that ID > accept it on mobile
							- Add each folder
							  collapsed:: true
								- On desktop web app click on the first folder > Edit > Sharing tab > add the new device
								- On mobile app > accept the notification for the folder > Folder Type: `Receive Only`
								- Repeat this for every folder
							- Related: ((672c007c-7fc5-4933-a826-d195748895b0))
						- Syncthing
						  collapsed:: true
							- Changelog
							  [https://github.com/syncthing/syncthing-android/releases](https://github.com/syncthing/syncthing-android/releases)
							- [[Software]] : [Syncthing](((6312a076-d503-40c4-b98f-cbdef17b1fcb)))
					- ((65ea4fb5-ec50-4c3c-ab50-ae13830ea523))
					- TagSpaces
					- [Tasks.org](((65ea4fb5-ec50-4c3c-ab50-ae13830ea523)))
					- Telegram FOSS
					- [Termux](https://github.com/termux/termux-app)
					  id:: 649b13ce-0b9e-4741-ba6d-7959858e3443
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Pros
								-
							- Cons
								-
							- Unclear
							- Upstream/Downstream Pros/Cons
							- Comparisons
							  collapsed:: true
								- ((67adc977-34d5-4706-8e2d-01ea080d826c)) vs ((649b13ce-0b9e-4741-ba6d-7959858e3443))
								  id:: ed189c8b-89c8-4cc1-a12a-82cd82bfa994
								  collapsed:: true
									- For ((67adc977-34d5-4706-8e2d-01ea080d826c))
									  collapsed:: true
										- Supported officially by Android, so likely to have capabilities increased in the future rather than decreased
									- For ((649b13ce-0b9e-4741-ba6d-7959858e3443))
									  collapsed:: true
										- Doesn't run Debian-only
										- Container-based, so better perfomance than virtual machine-based
									- Similarities
									  collapsed:: true
										-
									- Unclear
										- t does not appear to have any access to the Android file system so it cannot interact with native Android apps. For me that's a deal breaker.
										- It can run Docker, so potential Distrobox and containerised apps
										- Once there's GUI support can use potentially the desktop version of Firefox
						- # Documentation
						  collapsed:: true
							- Info
							  collapsed:: true
								- [Filesystem layout](https://github.com/termux/termux-packages/wiki/Termux-file-system-layout)
								  collapsed:: true
									- `/data/data/com.termux/files/home`
									  Home directory `~`
							- Commands
							  collapsed:: true
								- `termux-setup-storage`
								  collapsed:: true
									- this creates a new directory in termux, ~/storage, which contains simlinks to /storage/emulated/0 and can be accessed by a standard gui file manager.
								- `pkg upgrade`
								  Do this on a regular basis
								- termux:boot for auto-boot
								- termux-backup
								  collapsed:: true
									- [Backing up Termux - Termux Wiki](https://wiki.termux.com/wiki/Backing_up_Termux)
									- You need to archive contents of these directories:
									- /data/data/com.termux/files/usr
									  /data/data/com.termux/files/home
									- You can use utility tar. Before uninstalling the app, ensure that archives are placed to safe location such as /sdcard.
								- `pkg install git python pip nodejs curl`
							- [GitHub - termux/termux-tasker: Termux add-on app for integration with Tasker.](https://github.com/termux/termux-tasker)
							- [GUI desktop environment](https://wiki.termux.com/wiki/Graphical_Environment#Desktop_environment)
						- Termux wiki: [Termux Wiki](https://wiki.termux.com/wiki/Main_Page) Termux repo: [GitHub - termux/termux-app: Termux - a terminal emulator application for Android OS extendible by variety of packages.](https://github.com/termux/termux-app) Subreddit: https://www.reddit.com/r/termux/
						- Another related app is Termux. It can't run full Linux distro but it is much more lightweight and it has a pretty active community at /r/termux.
						- ((644c0acd-6461-4321-b905-37253e76b2c3))
						- ((644c0acd-1c33-433f-bdc2-9af37717acaf))
						- Related: ((67adc977-34d5-4706-8e2d-01ea080d826c))
					- Thunderbird
					  id:: 649b13ce-3d3d-484e-b868-4d4f577867f7
					  collapsed:: true
					  AKA formerly K-9 Mail
						- Cons
						  collapsed:: true
							- Doesn't allow separate SMTP to be used with IMAP e.g. can't use my Mailgun account for SMTP. Instead FairEmail app allows separation
						- Note: FairEmail is no longer maintained
						  id:: 649b13ce-e390-4271-ac52-4573ce723ba8
						  [[Oops! We broke the matrix. Someone call Neo! | XDA Forums](https://forum.xda-developers.com/t/closed-app-5-0-fairemail-fully-featured-open-source-privacy-oriented-email-app.3824168/post-86909365](https://forum.xda-developers.com/t/closed-app-5-0-fairemail-fully-featured-open-source-privacy-oriented-email-app.3824168/post-86909365))
						- Related: ((657ca277-93c1-419b-9dec-a5fa9a17c372))
					- ((644c0b17-c25b-493f-ba37-b254cc6f2e21))
					- TorServices
					- Track & Graph
					- TrackerControl
					  collapsed:: true
						- Changelog
						  [https://github.com/OxfordHCC/tracker-control-android/releases](https://github.com/OxfordHCC/tracker-control-android/releases)
						- Built on ((649b13cf-caf2-4248-adbb-6e642bd536d9))
					- Trail Sense
					- Transportr
					- Tubular
					- Twire
					- ((638e80eb-97e7-4bc4-b849-ede25c5771d6))
					- Vinyl Music Player
					- VLC
					- [Voice Audiobook Player](https://f-droid.org/en/packages/de.ph1b.audiobook/)
					  id:: 672a6407-ceaa-4cbc-bd96-c6679a97efab
					  collapsed:: true
						- [Show chapter instead of book for M4B files in the media notification · PaulWoitaschek/Voice · Discussion #2930 · GitHub](https://github.com/PaulWoitaschek/Voice/discussions/2930)
						-
					- WiFiAnalyzer
					- WiGLE WiFi Wardriving FOSS Map
					- ((63ff8189-440c-460c-904e-72d2227e81fc))
					- Xtra
					  collapsed:: true
						- Twitch app
						- https://github.com/crackededed/Xtra/releases
					- Yet Another SafetyNet Attestation Checker
					- Your local weather
					  collapsed:: true
						- (worse version of [Geometric Weather](https://workflowy.com/#/bb2171dac9e7))
						- (forked from Good Weather)
						- Simplified daily forecast view
						  https://github.com/thuryn/your-local-weather/issues/71
						- Set default view to multi-day forecast
						  https://github.com/thuryn/your-local-weather/issues/29
				- {Archive}
					- [[2024-11-05 Tuesday]] update, but removed at some point earlier
					  collapsed:: true
						- AdAway
						  collapsed:: true
							- Changelog
							  [https://github.com/AdAway/AdAway/blob/master/CHANGELOG.md](https://github.com/AdAway/AdAway/blob/master/CHANGELOG.md)
						- Advanced Charging Controller (ACCA)
						- Apple UnifiedNLP Backend
						- Autostarts
							- Root-only, block apps from starting automatically
						- Barinsta
						  collapsed:: true
							- Changelog
							  [https://github.com/austinhuang0131/barinsta/releases](https://github.com/austinhuang0131/barinsta/releases)
						- Brackeys IDE
						- Bromite (3rd-party F-Droid repo)
						  collapsed:: true
							- Changelog
							  [https://github.com/bromite/bromite/blob/master/CHANGELOG.md](https://github.com/bromite/bromite/blob/master/CHANGELOG.md)
						- APK Kit
						- Aves
						- ClipShare
						- [DarQ](https://github.com/KieronQuinn/DarQ)
						  id:: 632194a8-c91b-40b9-8620-c91826923c25
						  collapsed:: true
							- https://apt.izzysoft.de/fdroid/index/apk/com.kieronquinn.app.darq
							-
						- Deja Vu (location provider)
						  collapsed:: true
							- Uses locally acquired mobile/cellular tower data and WLAN/Wi-Fi AP data to resolve user location. Doesn't use network data
							- network provider for microG and UnifiedNLP
						- Drip
						  collapsed:: true
							- Period tracking
							- Used to use
								- Periodical
						- Droid-ify
						  collapsed:: true
							- F-Droid client that targets Android 12 and supports background app updates without needing root or the F-Droid Privileged Extension
							  [https://www.privacyguides.org/android/#droid-ify](https://www.privacyguides.org/android/#droid-ify)
							- 1 Backlink
								- [Droid-ify](https://workflowy.com/#/f5b6c58b30d2) (F-Droid client)
						- [FFUpdater](https://f-droid.org/packages/de.marmaro.krt.ffupdater/)
						  id:: 649b13ce-04e2-4a9c-b08e-cfc7860e6063
						  collapsed:: true
						- Geometric Weather
						  collapsed:: true
							- Wed, Jan 20, 2021 - Uninstalling Yahoo Weather since it's proprietary in favour of
							- _Alternatives_
								- [Your Local Weather ](https://workflowy.com/#/102abdd4458c) (worse version of GW)
								- Forecastie
									- Simplified view
									  https://github.com/martykan/forecastie/issues/158
									- Smaller widget
									  https://github.com/martykan/forecastie/issues/68
									- Chance of Rain (likely non-FOSS)
									  https://github.com/martykan/forecastie/issues/79
									- Hourly forecast module (likely non-FOSS)
										- http://i.imgur.com/Wvv02eM.png
										- "openweathermap.org . It seems to only support a 5 day/3 hour forecast API and not not support an hourly forecast, but there may be other providers who support this for free"
										  https://github.com/martykan/forecastie/issues/136
							- _Related:_ LineageOS [Weather service](https://workflowy.com/#/90223003ff03)
						- Get Off Your Phone
						- Good Weather
						- KeePassDroid
						  collapsed:: true
							- Related: ((649b13ce-ab97-4433-9643-95bcf3802a8d))
							- Changelog
							  [https://github.com/bpellin/keepassdroid/blob/HEAD/CHANGELOG](https://github.com/bpellin/keepassdroid/blob/HEAD/CHANGELOG)
						- [KurobaEx](https://github.com/K1rakishou/Kuroba-Experimental)
						  id:: 6313456a-cd8c-440f-8547-bf92c4d4cf78
						  collapsed:: true
							- Related: ((653c060d-62b0-4887-bf8d-c74bf7da71d5))
							- 4chan and other imageboard viewer
							- [https://f-droid.org/packages/com.github.k1rakishou.chan.fdroid/](https://f-droid.org/packages/com.github.k1rakishou.chan.fdroid/)
						- lemmur
						  collapsed:: true
							- Changelog
							  [https://github.com/krawieck/lemmur/releases](https://github.com/krawieck/lemmur/releases)
						- LibreTorrent
						  collapsed:: true
							- Changelog
							  [https://gitlab.com/proninyaroslav/libretorrent/blob/HEAD/NEWS](https://gitlab.com/proninyaroslav/libretorrent/blob/HEAD/NEWS)
						- Local GSM Location (UnifiedNLP provider)
						- Locate my device
						- Lunary
						  collapsed:: true
							- Ethereum wallet
						- ((649b13cd-e6ad-4655-91b6-5dcdce92aaed))
						- Markor
						  collapsed:: true
							- Pros
								- See [Markor as my notebook editor on mobile](https://workflowy.com/#/304788378214)
							- Changelog
							  [https://github.com/gsantner/markor/blob/HEAD/CHANGELOG.md](https://github.com/gsantner/markor/blob/HEAD/CHANGELOG.md)
								- Blog post form
								  [https://gsantner.net/collection/tags.html#markor](https://gsantner.net/collection/tags.html#markor)
							- 1 Backlink
								- [Markor](https://workflowy.com/#/3b75684e65ad) as my notebook editor on mobile
						- MemeTastic
						- microG Services Framework
						- MMRL - rooted modules manager
						- Money Manager Ex
						- MRepo
						- Neo Backup / OAndBackupX
						  collapsed:: true
							- Changelog
							  [https://github.com/machiav3lli/oandbackupx/blob/HEAD/CHANGELOG.md](https://github.com/machiav3lli/oandbackupx/blob/HEAD/CHANGELOG.md)
							- I've made some thing for you. :) Maybe other people are also interested. Just a crappy tool to decrypt backups.
								- [https://github.com/Tiefkuehlpizze/OABXDecrypt](https://github.com/Tiefkuehlpizze/OABXDecrypt)
						- OpenContacts
						- Oversec
						- Setter - reverse image search
						  collapsed:: true
							- 1 Backlink
								- See [Setter - ](https://workflowy.com/#/8fc2adc77b8f)<a href="https://workflowy.com/#/8fc2adc77b8f">reverse</a><a href="https://workflowy.com/#/8fc2adc77b8f"> </a><a href="https://workflowy.com/#/8fc2adc77b8f">image</a><a href="https://workflowy.com/#/8fc2adc77b8f"> search</a>
								  #Phone
						- Simple App Launcher
						  collapsed:: true
							- Changelog
							  [https://github.com/SimpleMobileTools/Simple-App-Launcher/blob/HEAD/CHANGELOG.md](https://github.com/SimpleMobileTools/Simple-App-Launcher/blob/HEAD/CHANGELOG.md)
						- Simple Gallery Pro
						  collapsed:: true
							- Changelog
							  [https://github.com/SimpleMobileTools/Simple-Gallery/blob/HEAD/CHANGELOG.md](https://github.com/SimpleMobileTools/Simple-Gallery/blob/HEAD/CHANGELOG.md)
						- SuperFreezZ App stopper
						- Twidere X
						  collapsed:: true
							- Changelog
							  [https://github.com/TwidereProject/TwidereX-Android/releases](https://github.com/TwidereProject/TwidereX-Android/releases)
						- UnifiedNlp (no GAPPS)
						- UntrackMe
						  collapsed:: true
							- Changelog
							  [https://framagit.org/tom79/nitterizeme/-/releases](https://framagit.org/tom79/nitterizeme/-/releases)
						- UP-FCM Distributor
						  id:: 632033c8-db1d-405f-a57a-6cd4d66cee57
						  collapsed:: true
							- No configuration required, enables Firebase Cloud Messaging notifications for any app with the configured setting to use this app
							- Available on IzzyOnDroid
							- Related: ((631fa97e-a0a9-406c-b7b9-20536d421090))
							-
						- WebApps Sandboxed Browser
						  collapsed:: true
							- Changelog
							  [https://github.com/tobykurien/WebApps/releases](https://github.com/tobykurien/WebApps/releases)
						- WiFi Location Service (UnifiedNLP provider)
						- Wrong PIN Shutdown
						- xBrowserSync
					- Pre-2021
					  collapsed:: true
						- Drowser
						  collapsed:: true
							- Uninstalled (Sun, Apr 4, 2021) because I never use it
						- Net Monitor
						  collapsed:: true
							- Incompatible with Android 10+. Use AdGuard instead
						- Lawnchair
						  collapsed:: true
							- Currently no F-Droid version
							  [https://github.com/LawnchairLauncher/lawnchair/issues/1473#issuecomment-813084132](https://github.com/LawnchairLauncher/lawnchair/issues/1473#issuecomment-813084132)
						- Lynket
						  collapsed:: true
							- Rarely ever used
						- FairEmail
						  id:: 657ca277-93c1-419b-9dec-a5fa9a17c372
						  collapsed:: true
							- ((649b13ce-e390-4271-ac52-4573ce723ba8))
							- Related: ((649b13ce-3d3d-484e-b868-4d4f577867f7))
			- ((66d095d8-4f55-4927-bc65-eaa9a58b0630)) apps
			  id:: 63209285-e561-4da1-bf20-0996e9ee49f4
			  collapsed:: true
				- Meta
					- How to detect Google Play Store apps
					  collapsed:: true
						- Use [AppChecker](https://workflowy.com/#/53d4acbf948e) and check "Installer" - will say "com.android.vending" instead of something like "fdroid"
				- # Apps sorted by category
					- [Paid apps](https://play.google.com/store/account/orderhistory)
					  id:: 649b13ce-6535-4d48-a434-b44092fda1a0
					  collapsed:: true
						- # Sorted by usage
						  Last updated: [[2024-11-05 Tuesday]]
							- _Frequently used_
								- ((649b13ce-a3a4-4d76-8185-c6a99207b002))
								- ((66a2459c-8ee4-4ae4-97d2-e244322204e4))
							- _Barely used_
								- [[Software]] : [HabitHub](((664c986c-8374-46fc-a227-0c701c9e275c))) - Premium
								- ZoiPer Pro
								- ((649b13ce-6570-4331-be4c-b5aeada7bfe7))
								- ((644c0acd-6179-4a8f-aa56-bab5f8a46b39))
								- ((649b13ce-457d-4e95-8aec-f7837b7cead3))
								- ((64e9e731-7b83-4d25-945c-3742401bf924))
								- ((64e9e731-ea6c-4e0d-9429-69cfb1ddb188))
							- {Archive} Unused
							  collapsed:: true
								- [[2024-11-05 Tuesday]]
									- ARP Guard
									- ((644c0acd-5a4d-4a25-9306-05b666484907))
									- ((63209284-786d-4fa2-93a0-95447391e1cc))
									- Override DNS
						- # Sorted by account
						  Last updated: [[2024-11-05 Tuesday]]
							- ## bluesteelmagnet account
								- Action Launcher Plus
								- ARP Guard (WiFI Security)
								- AZ Screen Recorder
								- Contact Photo Sync PRO
								- [Cronometer](https://play.google.com/store/apps/details?id=com.cronometer.android.gold)
								  id:: 644c0acd-6179-4a8f-aa56-bab5f8a46b39
								- ((649b13ce-6570-4331-be4c-b5aeada7bfe7))
								- FoxFi
								- iSyncr for iTunes
								- [ReverseTethering NoRoot PRO](https://play.google.com/store/apps/details?id=com.floriandraschbacher.reversetethering.pro)
								  id:: 649b13ce-457d-4e95-8aec-f7837b7cead3
								  collapsed:: true
									- Related: [gnirehtet](https://github.com/Genymobile/gnirehtet), made by ((63a9ade4-0cdf-4680-a839-6b6f92e57f51)) devs
								- ((66a2459c-8ee4-4ae4-97d2-e244322204e4))
							- ## aaronsollesse account
								- AFWall+ (Donate)
								- ((644c0acd-5a4d-4a25-9306-05b666484907))
								- Bouncer
								- Cryptomator
								- DiskDigger Pro
								- Dropsync Pro
								- Foldersync Pro
								- [[Software]] : [HabitHub](((664c986c-8374-46fc-a227-0c701c9e275c)))
								- ((64e9e731-ea6c-4e0d-9429-69cfb1ddb188))
								- [Lower Brightness Screen Filter Pro](https://play.google.com/store/apps/details?id=nu.lower.brightness.pro)
								  id:: 649b13ce-87fa-47db-b5fd-95b47b8ac79e
								  collapsed:: true
									- Not quite replaced by Extra Dim in ((649b13d1-806c-4635-a439-e008c6a27fa0))
								- ((64e9e731-7b83-4d25-945c-3742401bf924))
								- ((649b13ce-a3a4-4d76-8185-c6a99207b002))
								- Override DNS
								- Repainter
								- Secure Settings
								- ScreenCam plugin: Show touches
								- [Swift Backup](https://swiftapps.org/)
								  id:: 63216f53-22cf-428a-9193-e5a423158e2b
								  collapsed:: true
									- Unclear
										- ((63209285-2e05-40f2-bce9-5b8d813eea86)) compatibility
										  id:: 644c0acd-4ac7-45de-8ff9-22d45f385686
											- Can backup the app itself but not the app data
											- [Shizuku mode (ADB access) cannot read/write at private app data](https://swiftapps.org/faq#appparts) located in ((632170c7-2b8c-4f6e-a75a-7d37397093cf))
									- [FAQs | Swift Backup](https://swiftapps.org/faq#sdcard)
										- ### [Are SD Cards & USB drives supported?](https://swiftapps.org/faq#sdcardfaq#sdcard)
											- Yes. You can switch `SwiftBackup` folder location from Internal storage to an SD Card or USB drive from the 'Home' tab in the app. Click on the icon beside the storage information to bring up the switching screen.
											- **Is root required for this feature?**
												- SD Cards: Root required on Android 10 and below
												- USB drives: Root required on Android 11 and below
									- Related: ((631fa93b-a7e4-477a-a4d5-d8d90298fa2e))
								- Tasker
								- Titanium Backup PRO
								- XPrivacyLua
								- XPrivacy Pro
								- ZoiPer Pro - SIP Softphone
					- Apps with sensitive data that shouldn't be accessing internet but do
						- Disabled via ((630f96f0-f2c4-4706-9d72-58e13201e03f)) permissions
							- ((649b13ce-acd2-4f35-a942-e1c01eaf7d0c))
							- ((64e0946f-ca07-48a0-bac6-1b7bba5c490f))
							- ((649b13ce-20b8-4de2-85e2-d39f540deb85))
				- # Sorted by A-Z currently installed apps
				  id:: 649b13ce-cf11-42f6-876c-af12970a2bed
				  collapsed:: true
				  Last updated: [[2024-11-05 Tuesday]]
					- Meta
						- How to update list
							- On current phone open Google Play Store > Manage apps and device > Manage > Sort by Name
							- Note: it seems to add all apps not just Google Play Store apps if they share a package name
					- ## [[2024-11-06 Wednesday]] Too old to install
						- App Ops
						  id:: 6321aa1e-2671-43ee-993a-d32f42ed8c69
						  collapsed:: true
							- [Documentation](https://appops.rikka.app/guide/)
							- Permissions explanations
								- RUN_IN_BACKGROUND
									- The article has not been completed, more information will be added later
									  
									  All apps targeting API 26 and above will always subject to this restriction.
									  
									  Refer to the following article:
									  
									  Https://developer.android.com/about/versions/oreo/background
								- RUN_ANY_IN_BACKGROUND
									- The article has not been completed, more information will be added later
									- Refer to the following article:
									- Https://developer.android.com/about/versions/pie/power#battery-saver
									- Https://developer.android.com/topic/performance/power/power-details
								- "Run in background" seen in the App Ops app actually refers to the two ops `RUN_IN_BACKGROUND` (added from Android 7) and `RUN_ANY_IN_BACKGROUND` (added from Android 9). Changing these ops will behave differently on different system versions.
							- Related: ((63219e35-8143-4405-873e-8c9a9b9dc7ff))
						- Coinbase
						-
					- Airbnb
					- AppChecker - List APIs of Apps
					  id:: 649b13ce-acd2-4f35-a942-e1c01eaf7d0c
					  collapsed:: true
						- Nice UI for checking the API level various installed apps target
						  collapsed:: true
							- Relevant for [Scoped Storage](https://workflowy.com/#/84a8e2bfbc4e)
						- App Manager can show and sort by API level but its worse UI
					- Autenticaco Gov
					  collapsed:: true
						- Portuguese government auth app
					- Barclays
					  collapsed:: true
						- 1 Backlink
						  collapsed:: true
							- See [Barclays](https://workflowy.com/#/f3bdb4ef771c)
					- Bolt: Fast, Affordable Rides
					- Booking.com
					- Boost for Lemmy
					- ((649b140b-d592-4fce-86f5-df33b3ce2dae))
					  id:: 649b13ce-6cd2-4327-87d1-b599a93aa040
					- Citymapper
					  id:: 649b13ce-61e6-4038-b6a6-c9fc4247df4a
					  collapsed:: true
						- Note: it now has a web app
						  [https://citymapper.com](https://citymapper.com)
						- 6 Backlinks
						  collapsed:: true
							- See [Citymapper](https://workflowy.com/#/35535435574e) (most of the time the GPS takes ages to pinpoint)
							- Annoying that [Citymapper](https://workflowy.com/#/35535435574e) is unreliable as it uses the new Maps v2 API. Google Maps (web app or native) can provide train/bus schedules but the UX isn't as good. This map be fixed in the Mapbox builds but I haven't bothered with reinstalling for it yet
							- See [Citymapper](https://workflowy.com/#/35535435574e)
							- See [Citymapper](https://workflowy.com/#/35535435574e)
							- See [Citymapper](https://workflowy.com/#/35535435574e)
							- See [Citymapper](https://workflowy.com/#/35535435574e)
					- Codecademy Go
					- Coinmarket Cap
					- Color Grab (color detection)
					- ((644c0acd-6179-4a8f-aa56-bab5f8a46b39))
					- Cut The Rope
					- daily.dev
					- Dcoder, Compile IDE
					  id:: 63209284-fa60-4f8d-8df7-4fe890e0961e
					- Deliveroo
					- Delta
					- Discord
					  collapsed:: true
						- See [Discord](https://workflowy.com/#/776244a9838b)
						  #Software-Chat
					- Domino's Pizza Delivery
					- Easy Fast Intermittent Fasting
					- [EDS NG](https://play.google.com/store/apps/details?id=com.sovworks.projecteds)
					  id:: 678cbc12-c466-43bf-b3ad-450b4f5e142f
					  collapsed:: true
						- EDS app is unreliable - complains about copying error when trying to open KeePass DB sometimes
						- [[2025-01-19 Sunday]]
							- Please enter the following code to activate the features package
							      in EDS NG (right menu -> premium features -> right menu
							      -> purchase code):
							- `OBQWG23BM5SV63DFM5QWG6K7OYYQ-W7KRSTZTNPLXF6PSKKWH4VFHASE765IN-CIKA`
						- {Archive}
							- EDS (paid version)
							  id:: 649b13ce-6570-4331-be4c-b5aeada7bfe7
							  collapsed:: true
								- EDS (paid version) is needed to open hidden volumes in VeraCrypt containers
								- Currently crashes (July 2021) on startup, likely since it hasn't updated in nearly as year
								- ((649b13ce-01d9-4efd-b4c5-29d44b1ba1c9))
					- EteSync
					- Eventbrite
					- Foursquare
					- freeCodeCamp
					- FREE NOW (Kapten/mytaxi)
					  collapsed:: true
						- 1 Backlink
						  collapsed:: true
							- See [FREE NOW (Kapten/mytaxi)](https://workflowy.com/#/86af75700f71)
					- Gboard
					- ((649b1463-b077-434e-a501-df6e30d6c4fb))
					- [GitHub](https://play.google.com/store/apps/details?id=com.github.android)
					  id:: 649b13ce-dd5a-4efc-a71e-762b52cdbb1b
					  collapsed:: true
					- ((64e0946f-ca07-48a0-bac6-1b7bba5c490f)) Pocket
					- Google Docs
					- Google Lens
					- Google Maps
					- Google Translate
					- Google Wallet
					- [[Software]] : [HabitHub](((664c986c-8374-46fc-a227-0c701c9e275c)))
					- Habitica
					  id:: 649b13ce-7b4d-46da-badf-85bdf091f9ab
					- Hotels.com
					- ((663b24fb-831b-448c-81fb-0a8407d24408))
					- iD Mobile
					  collapsed:: true
						- 1 Backlink
						  collapsed:: true
							- See [iD Mobile](https://workflowy.com/#/156072b86baf)
					- Instagram
					  collapsed:: true
					- Just-Eat
					- KAYAK
					- Ledger Live
					- Leetcode Ally
					- LibChecker
					- Lime
					- Linphone
					- Lyft
					- Magic: The Gathering Companion
					- Memento Database
					- MetaMask
					- Metro Bank
					- Monzo Bank
					- MX Player
					- NHS App
					- [Nova Launcher](https://play.google.com/store/apps/details?id=com.teslacoilsw.launcher)
					  id:: 649b13ce-20b8-4de2-85e2-d39f540deb85
					  collapsed:: true
						- Pros/Cons
							- Pros
								-
							- Cons
								- [[2025-02-28 Friday]] No longer being updated
									- Lacks support for ((670bfaa4-c14d-4575-aad6-5f846468d6da))
							- Unclear
							- Comparisons
						- Setup
						  id:: 67322b1e-4afe-4529-8844-722ed5d9d4c2
							- Restore backup from ATHENAEUM/
							- Android settings > Apps > Default apps > Home app > select `Nova Launcher`
						- Possible 2025 replacements
							- Smart Launcher. Bought it outright and have zero regrets. It's not cheap, but considering I'll have it forever like Nova, it's worth it and is actively supported.
							- Octopi Launcher is also good. I jumped to that first and while it's really well done, Smart Launcher was a little more polished. Really can't go wrong with either. Octopi is a lot less expensive if that's a factor for you.
						- Related: ((649b13ce-a3a4-4d76-8185-c6a99207b002))
					- [Nova Launcher Prime](https://play.google.com/store/apps/details?id=com.teslacoilsw.launcher.prime)
					  id:: 649b13ce-a3a4-4d76-8185-c6a99207b002
					  collapsed:: true
					- ((64f5d195-c47a-4c21-a120-f03c0f767782))
					- PayPal
					- Play Integrity API Checker
					- Premier Inn
					- Probuilds for LoL & Wild Rift
					- [Background Video Recorder](https://play.google.com/store/search?q=Quick+Video+Recorder)
					  id:: 644c0acd-9a88-4c31-bffa-001debe144a7
					- RA Guide
					- ((6654edaf-be09-46b8-a9d7-d808d7bed3ab))
					- Session
					- Shazam
					- ((66a2459c-8ee4-4ae4-97d2-e244322204e4))
					- ((6312a076-eb26-4bd5-a669-ea0a50d06668))
					- Slack
					- Solaris
					- ((64f5d195-048b-4532-86da-5e3fa35b3d2c))
					- Stagecoach Bus
					- ((644c0bb5-76e1-4489-9fa4-22a803fa3c9d))
					- Stremio
					- Sync for Lemmy
					- taxi.eu
					- TB Checker - Play Integrity
					- Telegram
					- Text Fairy (OCR Text Scanner)
					  collapsed:: true
						- 1 Backlink
						  collapsed:: true
							- See [Text Fairy (OCR Text Scanner)](https://workflowy.com/#/aa39e5272623)
							  #Phone
					- Tfl Go
					- Tfl Oyster and contatless
					- Ticketmaster UK Event Tickets
					  collapsed:: true
						- There is a web app available, but being able to access the tickets offline I found valuable at one festival where internet reception was shit in a place with so many people
					- [TP-Link Tapo](https://play.google.com/store/apps/details?id=com.tplink.iot)
					  id:: 644c0acd-786d-4030-8a84-c8b275a6e053
						- To connect my [TP-Link Tapo Smart Mini Wi-Fi Plug - Tapo P100](https://www.amazon.co.uk/gp/product/B07Z942YWS) to a new Wi-Fi network use the app to connect via bluetooth and setup the Wi-Fi connection
					- Trainline
					- Trips by Lonely Planet
					- TripAdvisor
					- Trivago
					- Uber
					- Uber Eats
					- Unmind
					- UptimeRobot
					- Vyke
					- Waze
					- WhatsApp
					  collapsed:: true
						- [Scoped Storage](https://workflowy.com/#/84a8e2bfbc4e) will finally allow me to remove the Storage permission
						- Cons
						  collapsed:: true
							- Doesn't have ((663b24fb-4437-4115-83da-5f5b668989fc))
						- Watomatic - auto-replies (eg let people know you're not using WhatsApp anymore
						  [https://github.com/adeekshith/watomatic](https://github.com/adeekshith/watomatic)
					- WiFi Analyzer (open-source)
					- WiGLE WiFi Wardriving
					- YouCut video editor
					- Zoiper
					- {Archive}
					  collapsed:: true
						- [[2024-11-05 Tuesday]]
							- Airtable
							- Background Video Recorder Ultimate
							  collapsed:: true
								- 1 Backlink
								  collapsed:: true
									- See [Background Video Recorder Ultimate](https://workflowy.com/#/9d27b488e5c5)
							- Blockfolio
							- Bouncer
							  id:: 63209284-786d-4fa2-93a0-95447391e1cc
							  collapsed:: true
								- Should be partially defunct by Android 12 due to [Privacy Indicators - notification whenever an app is checking Location, Microphone or Camera](https://workflowy.com/#/6230c933365e)
								  collapsed:: true
									- However for Files & Media permission it will be useful still
								- Lacks
									- Ability to ignore a certain permission type. Emailed the feature request
							- Brain N-Back
							- BOOM & MEGABOOM by Ultimate Ears
							- Dynalist
							  collapsed:: true
								- 1 Backlink
								  collapsed:: true
									- See [Dynalist](https://workflowy.com/#/a866d98aa80d)
							- FolderSync Pro
							  collapsed:: true
								- 1 Backlink
								  collapsed:: true
									- See [FolderSync Pro](https://workflowy.com/#/5ee6ccb3c3dd)
							- Librera Reader
							  id:: 649b13ce-ebbe-44ce-8f19-72f42b3766f3
							  collapsed:: true
								- Pros/Cons vs Calibre content server
								  collapsed:: true
									- Pros
									  collapsed:: true
										- Doesn't require connecting to Calibre content server in order to open offline library (after phone restart, browser shutdown, desktop Calibre closing, etc)
									- Cons
									  collapsed:: true
										- Lacks reference mode
									- Both
									  collapsed:: true
										- Dark mode
								- Google Play version has Network feature which allows connecting to Calibre library (OPDS catalog)
								- ((62e283e1-ebea-4ab9-9763-aa6a1b7ea0ba)) : ((6525b49c-3732-4cf4-88f2-eb912365e2cf))
							- ProtonVPN
							  collapsed:: true
								- Pros/Cons
								  collapsed:: true
									- Pros
									  collapsed:: true
										- Supports split-tunnelling
										- Supports WireGuard
								- See [VPN implementation is poor](https://workflowy.com/#/c08cbfe9ff89)
								  #Phone-Android
								- 1 Backlink
								  collapsed:: true
									- Android - see [ProtonVPN](https://workflowy.com/#/af3c69e7197d) Android app
									  #Phone
							- [Repainter](https://play.google.com/store/apps/details?id=dev.kdrag0n.dyntheme)
							  id:: 63209284-c01f-4374-9a63-ee38b3b0f462
							  collapsed:: true
								- Makes Material You theming darker
							- Stack for Stack Overflow
							  collapsed:: true
								- [https://github.com/tylerbwong/stack/issues/110#ref-pullrequest-754936707](https://github.com/tylerbwong/stack/issues/110#ref-pullrequest-754936707)
								- [https://play.google.com/store/apps/details?id=me.tylerbwong.stack](https://play.google.com/store/apps/details?id=me.tylerbwong.stack)
							- [Storage Isolation](https://play.google.com/store/apps/details?id=moe.shizuku.redirectstorage)
							  id:: 63218542-c020-4f75-9c0e-7e6c9f4b093b
							  collapsed:: true
								- Pros/Cons
									- Pros
										- Older apps or non-Play Store apps might not have been updated yet to the Scoped Storage requirement. This isolates their storage
										- These files will be deleted when uninstalling or clearing data
										- In system's app info, these files will also be counted as storage usage
								- Note: this is a default feature of [GrapheneOS](<((63209286-6f40-4063-9fdc-2543251d416e))>)?
								- Made by creators of ((63209285-2e05-40f2-bce9-5b8d813eea86)) and other apps
							-
				- {Archive}
				  collapsed:: true
					- AFWall+ (Donate)
					  collapsed:: true
						- Cons
							- Deprecated in Android 12 since iptables is removed
					- AzireVPN
					  collapsed:: true
						- 2 Backlinks
						  collapsed:: true
							- _Android (currently [AzireVPN](https://workflowy.com/#/20cc5b77ba6f)) _
							- See [AzireVPN](https://workflowy.com/#/20cc5b77ba6f) - not FOSS but I currently have a subscription with them, and Wireguard doesn't deactivate the "always-on VPN" notification
							  #Phone
					- WorkFlowy
					- UNO!
			- ## Other apps
				- _App stores or download methods_
					- ### ((644c0acd-59dd-4065-a2e9-41351725caf8)) apps
					  id:: 63207624-8cee-43e5-9123-70441ef78225
					  collapsed:: true
					  Last updated: [[2024-11-05 Tuesday]]
						- Meta
							- [Obtainium](https://github.com/ImranR98/Obtainium)
							  id:: 644c0acd-59dd-4065-a2e9-41351725caf8
							  e.g. from F-Droid
						- List
							- Not sure if needed, likely self-updating
							  id:: 65166e25-de88-490a-b45a-6db846d2d7d9
								- ((651669ce-4f99-4d79-b234-9a914dcb012c))
								- [Aniyomi](https://aniyomi.org)
								  id:: 651408a1-d5e3-413b-85f3-2f4829175e3b
								  collapsed:: true
									- [GitHub - aniyomiorg/aniyomi: An app for manga and anime](https://github.com/aniyomiorg/aniyomi)
								- [Mihon](https://github.com/mihonapp/mihon)
								  id:: 65a6dc53-c6ef-4fb1-b5ca-4123b083a7f1
								  collapsed:: true
									- Successor to Tachiyomi
										- [Tachiyomi](https://tachiyomi.org/)
										  id:: 63209285-a267-4f3c-b28b-c8116948c1d1
										  collapsed:: true
											- Pros/Cons
												- ((644c0b31-6f08-4ddd-8fa5-57db5cb644be))
											- Note: was taken off F-Droid due to DCMA request
											- [App can auto-update itself](https://github.com/tachiyomiorg/tachiyomi/issues/6736)
											- [[2024-01-11 Thursday]] Extensions were removed from the main app due to copyright claims? Now available in repos such as [GitHub - keiyoushi/extensions: Source extensions for the Tachiyomi app.](https://github.com/keiyoushi/extensions)
												- Go to More → Settings → Browse
												  Tap on "Extension repos" and then "Add" button at bottom
												  Input `https://raw.githubusercontent.com/keiyoushi/extensions/repo/index.min.json`
									- [Alternatives](https://alternativeto.net/software/tachiyomi/)
										- [Mangayomi](https://github.com/kodjodevf/mangayomi)
										- [Kotatsu](https://github.com/KotatsuApp/Kotatsu)
										- https://github.com/Suwayomi/Suwayomi-Server#syncing-with-tachiyomi
										- ((651408a1-d5e3-413b-85f3-2f4829175e3b))
										- J2k
										- https://tachiyomi.org/forks/TachiyomiJ2K/
										- https://github.com/Jays2Kings/tachiyomiJ2K
										- SY
										- https://tachiyomi.org/forks/TachiyomiSY/
										- https://github.com/jobobby04/TachiyomiSY
										- AZ
										- https://tachiyomi.org/forks/TachiyomiAZ/
										- https://github.com/az4521/TachiyomiAZ
										- Repo for the extensions are here: https://github.com/keiyoushi/extensions
										- Edit: Tachiyomi (and iirc also aniyomi?), go to More (settings) > Browse > Extension repo. Then enter: https://raw.githubusercontent.com/keiyoushi/extensions/repo/index.min.json
							- ((653c075b-60af-4e96-b37a-b8f9be723440))
							- ((653c060d-62b0-4887-bf8d-c74bf7da71d5))
							- [CloudStream](https://apt.izzysoft.de/fdroid/index/apk/com.lagradost.cloudstream3)
							  id:: 649b13cf-59ff-4f2f-ac3f-83fa18732064
							  collapsed:: true
								- Pros/Cons
									- ## Pros
									- ## Cons
									- Unclear
									- Comparisons
								- Repo
									- [Original (DMCA takdown)](https://github.com/reduplicated/Cloudstream)
									- https://github.com/recloudstream/cloudstream
								- [Pre-release build](https://github.com/recloudstream/cloudstream/releases/tag/pre-release) (since they update stable quite slowly)
								- [Add all repos for plugins here](https://self-similarity.github.io/http-protocol-redirector?r=cloudstreamrepo://raw.githubusercontent.com/self-similarity/MegaRepo/builds/repo.json)
									- Best
										- https://raw.githubusercontent.com/Rowdy-Avocado/Rowdycado-Extensions/builds/repo.json
										  https://github.com/Rowdy-Avocado/Rowdycado-Extensions
										-
								- Related: ((6494265e-c3dd-46c7-8913-7dea23d5ee72))
							- ((65ec1605-44a8-4334-bd70-b45a4e0f4679))
							- ((66825a1d-c720-4353-9757-af437e7343c2))
							- [LNReader](https://github.com/LNReader/lnreader)
							- [Round Sync](https://github.com/newhinton/Round-Sync)
							  collapsed:: true
								- Rclone for Android
								- [RCX](https://github.com/x0b/rcx) - Rclone for Android
								  id:: 649b13ce-f81c-41be-a7ff-f6d677c158c0
								  Abandoned since ~2021
									- Cons
										- Lacks scheduled sync
										  [https://github.com/x0b/rcx/issues/38](https://github.com/x0b/rcx/issues/38)
										- Can't mount remotes
										  [https://github.com/x0b/rcx/issues/104#issuecomment-881869997](https://github.com/x0b/rcx/issues/104#issuecomment-881869997)
							- {Archive}
								- ((65aaeb34-ba89-4dae-86ba-1cbb903f8d37))
								- [MRepo](https://github.com/ya0211/MRepo)
					- ### ((63218e46-d5cc-44cf-877f-948c45235bd9)) apps
					  collapsed:: true
					  Last updated: [[2024-11-05 Tuesday]]
						- Meta
							- [GrapheneOS app store](https://github.com/GrapheneOS/Apps)
							  id:: 63218e46-d5cc-44cf-877f-948c45235bd9
							  collapsed:: true
								- Can update itself
						- List
							- App Store
							- ((644c0acf-58a1-4b82-9767-c88c65955315))
							- Camera
							- Info
							- PDF Viewer
							- Vanadium
							- ((635037d0-5875-4083-8a49-4c68a6af8843))
					- ### ((651669ce-4f99-4d79-b234-9a914dcb012c)) apps
					  collapsed:: true
					  Last updated: [[2024-11-06 Wednesday]]
						- Meta
							- [Accrescent](https://accrescent.app/)
							  id:: 651669ce-4f99-4d79-b234-9a914dcb012c
							  collapsed:: true
								- [GitHub - accrescent/accrescent: A novel Android app store focused on security, privacy, and usability](https://github.com/accrescent/accrescent)
								- ((649b13cf-e2cb-4e21-8bf4-27f84e9b79f3)) : ((644c0ace-6f23-4066-b43f-3eec2c270acc))
						- List
							- Aves Gallery
					- ### Self-updating
						- Originally from ((63207624-8cee-43e5-9123-70441ef78225))
							- {{embed ((65166e25-de88-490a-b45a-6db846d2d7d9))}}
				- ### Manual
				  collapsed:: true
					- ((644c0b14-6d87-4d9c-8750-8d5a181513df))
					- Tiny Tiny RSS
			- ((649b13ce-166b-43de-bea7-4262b566ccce)) shortcuts (web app)
			  collapsed:: true
				- Activities
					- Airbnb
					- [Booking.com](http://Booking.com)
					- Byhours
					- Dayuse
					- Deliveroo
					- Eventbrite
					- Groupon
					- Just Eat
					- Lonely planet
					- Morrison's
					- OpenTable
					- Premier Inn
					- Tripadvisor
					- Trivago
					- Vrbo
			- {Archive}
			  collapsed:: true
				- ((6516669f-1bb2-4355-90e0-2fe32a948d2e))
		- # Sorted by category
			- ((644c0acc-dc08-4f95-a77e-d52a9bb2ebed))
			- Gaming
			  id:: 66e93ef5-6a40-4e8d-a68d-d3d4260746fe
			  collapsed:: true
			  AKA Android Gaming
				- # Where to download from
					- [[Game Releases | Mobilism](https://forum.mobilism.org/viewforum.php?f=408](https://forum.mobilism.org/viewforum.php?f=408))
					- [https://ac-market.org/](https://ac-market.org/)
					- [https://tutuapp.vip/android/](https://tutuapp.vip/android/)
					- [https://teddit.net/r/Piracy/wiki/megathread#wiki_ix._android](https://teddit.net/r/Piracy/wiki/megathread#wiki_ix._android)
				- [GitHub - oxters168/Pluvia: Lightweight unofficial Steam client for Android](https://github.com/oxters168/Pluvia)
				-
				- # Games
					- _Turn-based combat_
						- Slay the Spire
						- XCOM®: Enemy Within
						- CHRONO TRIGGER
						- Final Fantasy Tactics
						- ((632d02ab-0498-4fa3-bd00-a823b71576b9))
					- _Real-time combat_
						- Dead Cells
						- Castlevania: Symphony of the Night
					- ## Strategy
						- ((64e9e731-7b83-4d25-945c-3742401bf924))
						- ((64e9e731-ea6c-4e0d-9429-69cfb1ddb188))
						- Brawlhalla
						- Cultist Simulator
					- PUBG Lite
					- Fortnite?
					- Deus Ex: The Fall
					- Death Road to Canada
					- ((64e0952b-cc96-41e1-9fee-38fd40473021))
					- GTA San Andreas
					- Secrets of Mana
					- ((64e9e731-e25f-45ba-9adb-f149401e954d))
					- ## Gamepad support
					  id:: 66e93efa-51c2-421f-919a-868cc7ab1494
					  Last updated: [[2024-11-05 Tuesday]]
						- Brawlhalla
						- ((644c0acf-c1c4-4549-be63-feb430011d8b))
						- Relic Hunters Remix
						- Diablo Immortal
						- ((648f9076-9c44-4a26-8af5-8d709d1ab64d))
						- ((64e9e732-dbd1-4751-b55e-bfe184da2f35))
						- ((669830d9-9e56-4a55-9c8d-ee93da065942))
						- 20 Minutes Till Dawn
						- Chrono Trigger
						- Dead Cells
						- Baldur's Gate - Dark Alliance
						- Black Desert Mobile
						- Dicey Dungeons
						- DYSMANTLE
						- Escapists 2
						- ((66e9791c-ad28-40cc-b712-ffc6319dabd1))
						- Grand Theft Auto: San Andreas
						- Grand Theft Auto III
						- Grand Theft Auto: Vice City
						- Gunfire Reborn
						- [Hitman: Blood Money](https://store.steampowered.com/app/6860/Hitman_Blood_Money)
						  id:: 047fc08e-9f82-4ae5-8613-903d5f2a4d3d
						- Hyper Light Drifter
						- Kingdom Rush 5: Alliance TD
						- Lego Star Wars
						- Monopoly Go
						- Omega Strikers
						- PPSSPP PSP Emulator
						- Punishing Grey Raven
						- Roblox
						- Rumble Club
						- ((6597f2e6-dbe7-4032-8431-4ab80ea6a64b))
						- ((64e9e731-e25f-45ba-9adb-f149401e954d))
						- Stumble Guys
						- SuperTuxCartTerraria
						- Torchlight: Infinite
						- Undecember
						- Vampire Survirors
						- Worms 4
						- ### Gacha
							- Devil May Cry: Peak of Combat
							- Genshin Impact
							- Honkai: Star Rail
							- Naruto X Boruto Ninja Voltage
							- Snowbreak: Containment Zone
							- Solo Leveling: Arise
							- Tower of Fantasy
							- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
							- Zenless Zone Zero
						- Emulators
							- RetroArch
							- My Boy for Game Boy Advance
							- ((644c0bb4-b761-4b11-8296-a93c70eb6a5e))
							- Citra
							- PPSSPP
						- [All Mobile Games with Controller Support | Backbone](https://playbackbone.com/gb/games/?sort=alphabetical)
							- [via Google Play Store](https://backbone.com/gb/games/?platform=android)
						- ((649b1463-b077-434e-a501-df6e30d6c4fb)) mobile app
						- GamePass Ultimate
						- Related:
							- ((63a9ade4-0cdf-4680-a839-6b6f92e57f51)) : ((649b13cf-da25-4c0f-8ec2-ac3aa1f94691))
							- Related: ((631fa93e-1087-4996-91b8-7526842b4ba8)) : ((66e93ef5-6a40-4e8d-a68d-d3d4260746fe)) : ((66f330f5-88f3-41a3-bf34-7f97f92f5ff6))
				- Playing via Linux
				  id:: 66f330f5-88f3-41a3-bf34-7f97f92f5ff6
				  collapsed:: true
					- Waydroid
						- [GitHub - Aman9das/Waydroid_Setup_Guide](https://github.com/Aman9das/Waydroid_Setup_Guide)
						- [Waydroid_Setup_Guide/COMPATIBILITY.md at main · Aman9das/Waydroid_Setup_Guide · GitHub](https://github.com/Aman9das/Waydroid_Setup_Guide/blob/main/COMPATIBILITY.md)
					- Related: ((63a9ade4-0cdf-4680-a839-6b6f92e57f51)) : ((649b13cf-da25-4c0f-8ec2-ac3aa1f94691))
				- [Learning Resources]
					- [Discover The Best Mobile Games & Reviews](https://minireview.io/)
					-
				- Related: [[Videogames]] : ((64e0952b-9587-483c-942e-8c1e417b07ac))
		- Reviewing
		  collapsed:: true
			- Review old apps
				- Use [AppChecker](https://workflowy.com/#/53d4acbf948e) or App Manager to check API level
				- Check [AppTrackingTransparency](https://workflowy.com/#/e4dafed73a56) for proprietary apps
			- Battery optimised apps (last checked April 2021)
				- Apps and Notifications > Special app access > Battery optimisation > remove any optimised apps that shouldn't be running in the background
		- Linux mobile and ((631fa93c-fd77-4435-a292-fd9573d0242f)) apps
		  id:: 63219e35-fae2-4fe8-a220-1adba4633994
		  collapsed:: true
			- Maui apps
			  collapsed:: true
				- https://mauikit.org/apps/
					- Unlisted apps (but are listed in blog posts)
						- Booth - camera app
						- Bonsai - git repo manager
					- [All apps](https://invent.kde.org/maui)
				- Framework that allows responsive, Linux + Android cross-platform apps
				- [F-Droid repo](https://binary-factory.kde.org/view/Android/)
					- and
					  https://cdn.kde.org/android/stable-releases/fdroid/repo/?fingerprint=13784BA6C80FF4E2181E55C56F961EED5844CEA16870D3B38D58780B85E1158F
			- Purism apps
				- megapixels (camera)
				  collapsed:: true
					- https://gitlab.com/postmarketOS/megapixels
					- https://source.puri.sm/Librem5/millipixels/
				- Tootle, Lollypop, and Firefox
				- I’ll check the news (Feeds), check social media (Tootle, Cawbird), chat with friends (Axolotl Signal client, Chatty), and might listen to a news podcast (gPodder + VLC) over my Bluetooth headphones
				  id:: 63416616-e7c9-4d31-a210-374671e6bccd
				- https://puri.sm/posts/my-first-year-of-librem-5-convergence/ + Nexdock 360 + generic magnet mount for phones to back of laptop
				  id:: 635f89a0-abea-4909-a421-ef8f32614d28
			- Related:
				- ((63219e36-f656-49e9-865a-7347177df70b))
				- ((63412f42-1797-4d76-9607-7351eafe4f40))
		- Unsorted
		  collapsed:: true
			- ((649b13cf-237a-44bc-906e-818b273bea78))
			- _Notable apps_
			  collapsed:: true
				- Firewall
					- ((649b13cf-caf2-4248-adbb-6e642bd536d9)) - FOSS, uses a local VPN
					- root using iptables frontend like [AFWall](https://workflowy.com/#/e5f2eed18186)
					- If wanting to just restrict apps using data whilst being in the background, then use:
						- Select the app -> app info -> app data -> background data (off)
					- 1 Backlink
						- See [Firewall](https://workflowy.com/#/9127819b0944) (internet permission)
				- Dialler app
					- Stock AOSP/LineageOS
					- _{Archive_} - Alternatives
						- Simple Dialler
						- OpenContacts - has it's own private contacts database
							- Separate contact database
								- Pros
									- Useful for if you have to share contacts with a proprietary app but don't want them to have all your contacts
										- ((663b24fb-f1f2-4dbe-ae47-d3a910654835))
										-
								- Cons
						- Emerald Dialler
				- See [Aurora](https://workflowy.com/#/b8a1c067853c)<a href="https://workflowy.com/#/b8a1c067853c"> Store</a>
				- F-Droid
				- _See_ [Titanium](https://workflowy.com/#/15c43e198c80)<a href="https://workflowy.com/#/15c43e198c80"> Backup</a>
				- _See _[Magisk](https://workflowy.com/#/baba54354fcf)<a href="https://workflowy.com/#/baba54354fcf"> - AKA Systemless Root/SU</a>
				- _See_ [microG](https://workflowy.com/#/5b760a9e66c3)
				- _See_ TWRP
				- _App managers_
				  id:: 63734d34-65d7-41d7-9aec-6a92ee6729d7
					- App Manager (F-Droid)
						- Was a fork of Exodus, now instead scanner for examining packages
					- AppChecker
						- Great for checking which API level apps target i.e. find outdated apps easily
					- Exodus
						- Cons
							- Requires scanning all your apps and checking the results online. No apparent local database checked
				- _Call recording apps_
					- _Related:_
						- See [Stock Android AOSP](https://workflowy.com/#/5c6940e545df) - <a href="https://workflowy.com/#/2d492b1c1c5a">Call recording is being heavily restricted</a>
					- Pre-requisites:
						- ROM/OS must support call recording
							- See [LineageOS](https://workflowy.com/#/1543bac42ca5) - <a href="https://workflowy.com/#/7a612aa23bab">Call recording is supported if you're located in a country where this is legal when installing LineageOS. However has to be enabled by the device maintainer</a>
						- An app may be needed to setup call recording
							- Some ROM/OS have native call recording
								- For LineageOS [Use com.android.dialer (AKA "Telephone") ](https://workflowy.com/#/b4d5a9fe7f15)
							- Otherwise
								- App store must allow call recording apps (or you'll have to download it directly)
									- See [April 2022 (post-Android 12 release) - Google Play Store update bans apps from using Accessibility Service to record calls](https://workflowy.com/#/bd863300efaf)
								- Working apps (Tue, Apr 26, 2022 LineageOS 19/Android 12L)
									- See [Call Recorder (com.github.axet.callrecorder)](https://workflowy.com/#/d36098ce1215) from F-Droid
									- Axet's Call Recorder (Magisk module)
										- 1 Backlink
											- See [Axet's ](https://workflowy.com/#/4f69e834aaac)<a href="https://workflowy.com/#/4f69e834aaac">Call</a><a href="https://workflowy.com/#/4f69e834aaac"> </a><a href="https://workflowy.com/#/4f69e834aaac">Record</a><a href="https://workflowy.com/#/4f69e834aaac">er (Magisk module)</a>
								- Unsure if still supported
									- Automatic Call Recorder Pro
									  id:: 644c0acd-5a4d-4a25-9306-05b666484907
					- See [How to enable call recording](https://workflowy.com/#/6581cf768a8a)
					- 3 Backlinks
						- See [Call](https://workflowy.com/#/3b40b1b5144b)<a href="https://workflowy.com/#/3b40b1b5144b"> </a><a href="https://workflowy.com/#/3b40b1b5144b">record</a><a href="https://workflowy.com/#/3b40b1b5144b">ing</a>
						- See [Call](https://workflowy.com/#/3b40b1b5144b)<a href="https://workflowy.com/#/3b40b1b5144b"> </a><a href="https://workflowy.com/#/3b40b1b5144b">record</a><a href="https://workflowy.com/#/3b40b1b5144b">ing</a>
						- See [Call recording apps](https://workflowy.com/#/3b40b1b5144b)
				- Rooted apps
				  _See_ [Rooting](https://workflowy.com/#/5d249f1fc893)
				- Split-screen apps
					- Split Screen Launcher
						- [https://play.google.com/store/apps/details?id=com.fb.splitscreenlauncher](https://play.google.com/store/apps/details?id=com.fb.splitscreenlauncher)
				- ((650aae19-56a4-43ed-b1dc-b3acd07ea36e))
			- Not Present Assets
			  collapsed:: true
				- SSH keys to servers
				- AWS app
				- DigitalOcean app
				- Google Analytics app
				- Google AdWords app
				- Second WorkFlowy via Orgzly
				- Habitica
			- Content
			  collapsed:: true
				- Identifiers, e.g. names, locations
				- Voice fingerprinting
				- Keywords
				- Text - Stylometrics
			- _Linkability_
			  collapsed:: true
				- Never use debit card as a oyster card
					- Easy to tie where you are going to where you make purchases
			- All-round harmful apps
			  collapsed:: true
			  #IL-0007
				- _Solutions_
					- _Detecting harmful apps_
						- Permissions app on F-Droid
					- Blocking
						- Rooting necessary for many of the more precise permissions illustrated via the Permissions app
				- Google Play Services
				  #IL-0005
					- Provider of Google Location Services
					- Records location data even when location history turned off
					  source:: https://www.reddit.com/r/privacy/comments/96xb14/google_tracks_your_movements_even_with_location/e43uj7l/
					- Requests many permissions (unless turned off)
					-
				- WhatsApp
				  #IL-0006
					- Pros/Cons
						- Pros
							- Multi-account support
							- Multi-device support (doesnt require phone online)
							- End-to-end encrypted backups
						- Cons
							- Lacks, but rolled out in beta
					- [https://www.theguardian.com/technology/2017/jan/13/whatsapp-backdoor-allows-snooping-on-encrypted-messages](https://www.theguardian.com/technology/2017/jan/13/whatsapp-backdoor-allows-snooping-on-encrypted-messages)
					- Why
						- All data shared with Facebook Inc
						  See #IL-0010
						- Privacy leaks/permissions
							- _Android permissions_
								- _Allowed permanently_
									- Contacts **[high identification]**
									  collapsed:: true
										- Pros/Cons
											- Pros
												- Gives names to contacts and profile pictures
												- Especially useful for identifying the name or face of new numbers I collect during night game
											- Cons
												- Plots social graph
										- What
											- Own phone number
											- All my contacts phone numbers
									- Storage
									  collapsed:: true
									  Fixed in next Android version
										- Pros
											- To send pics
											- Background download pics from group chats
											- Android 11 storage permission is scoped?
											  [When Android 11/Lineage 18 is available, Scoped Storage should mean that WhatsApp is far less privacy invasive ](https://workflowy.com/#/d1c483335dd6)
								- _Denied_
								  As of Jan 2021
									- _Sometimes allowed, auto-removed by [Bouncer](https://workflowy.com/#/2eb692a67430)_
										- Camera - for video calls
										- Microphone **[high content]** - for voice calls
									- Call Logs
									- Location
									- Telephone
									- SMS
							- _Android secret perms_
								- IP address - and thus location
							- _Other_
								- User-submitted data
									- Profile names
									- Profile pictures **[high identification]**
										- And easily linked to Facebook
								- Chat content
									- Chat logs are backed up unencrypted to Google Drive/iCloud by all chat participants
									- _Note: Depending on if Facebook actually has the private keys_
										- Full chat content
										- Writing analysis
										- psychometric analysis
							- _Outdated / defunct_
								- Clipboard access
									- On Android 10 now only your keyboard app and foreground apps can access clipboard
									  [Clipboard access prevented for background apps](https://workflowy.com/#/b269a0f7ccf8)
					- Solution
						- 1. Orbot always on phone - or root it to Torify transparently
						- 2. Use WhatsApp in a Torified VM using Anbox
						- 3. Put Matrix username in status and only chat via Riot
							- https://riot.im/app/#/user/!StValentine:matrix.org
						- Matrix bridge - still quite convoluted Sun, Jan 10, 2021
						  [https://matrix.org/docs/guides/whatsapp-bridging-mautrix-whatsapp](https://matrix.org/docs/guides/whatsapp-bridging-mautrix-whatsapp)
				- Instagram
				- SnapChat
				  #IL-0009
				- _Not installed_
					- Facebook
					  See #IL-0008
			- Google Pay
			  collapsed:: true
				- Can support many bank accounts via PayPal integration, though not every country yet
				- I just want a native service by my bank. I don't want to share all my  data about how I spend my money with PayPal and Google. Is that really too much to ask?
			- Can't run SPV or full blockchain nodes
			- Automation apps
			  collapsed:: true
				- _See_ [Tasker](https://workflowy.com/#/90d21c677d84)
				- Easer
			- See [Voice Assistants & Smart Speakers](https://workflowy.com/#/72feb74b665c)
			- Interesting apps
			  collapsed:: true
				- FOSS workout app
					- [https://github.com/wger-project/wger](https://github.com/wger-project/wger)
					- [https://wger.de/en/software/features](https://wger.de/en/software/features)
				- ## Audio player
					- ## See if there is a Simple FOSS app for music + audio player. Can do background playing (for videos like MX Player); remembers last position/time (like AntennaPod); can increase playback speed (like VLC);
			- Find my device software
			  id:: 66d098ad-73d9-44c7-b85e-3ec18d953d9b
				- # FOSS
					- [Find My Device (FMD)](https://f-droid.org/it/packages/de.nulide.findmydevice/)
					  id:: 66cf8e7e-185a-492d-8e00-d67e3b15d5f7
					  collapsed:: true
					  [[2024-08-29 Thursday]] Have set this up with server + Hushed number [[2024-08-29 Thursday]]
						- Pros/Cons
							- Pros
								-
							- Cons
								-
							- Unclear
							- Upstream/Downstream Pros/Cons
							- Comparisons
								- ((66cf8e7e-185a-492d-8e00-d67e3b15d5f7)) vs ((6638cb59-c6e7-4914-9f20-a55127a18d79))
									- For ((66cf8e7e-185a-492d-8e00-d67e3b15d5f7))
										-
									- For ((6638cb59-c6e7-4914-9f20-a55127a18d79))
										-
									- Similarities
										- Both can store a history of last known locations
									- Unclear
										-
						- Documentation
							- Cloned locally
								- `/home/boss/Documents/Git/Other/findmydeviceserver`
								- `/home/boss/Documents/Git/Other/findmydevice`
							- [FMD Server](https://gitlab.com/Nulide/findmydevice/-/wikis/FMD%20Server)
								- Default webserver: [FMD](https://fmd.nulide.de:1008/)
								- Privacy Notice
									- What data is stored when visiting the website?
									- To establish a connection your IP address is transmitted, but not saved. While using the website the private key and the user-id will be saved temporarily in your browser, but will be removed when leaving the page.
									- What data is stored on the server?
									- The server stores the plaintext random user id and your password hash. It also stores all encrypted data uploaded by your phone: location, date, any pictures, battery level, the public key, and the encrypted private key.
									- Is my data transferred/sold/etc?
									- Your data is only used to provide the functionality of finding your device. It is not given to other parties.
					- [GitHub - xfarrow/locatemydevice: Application miming Google's Find My Device through SMS](https://github.com/xfarrow/locatemydevice)
					- [GitHub - tranquvis/SimpleSmsRemote: Android app for remotely controlling a phone through sms messages](https://github.com/tranquvis/SimpleSmsRemote)
				- # Proprietary
					- Google's [Find My Device](https://www.google.com/android/find/)
					  id:: 6638cb59-c6e7-4914-9f20-a55127a18d79
					  AKA previously Android Device Manager (ADM)
		- _Related: _
			- ((650aae19-56a4-43ed-b1dc-b3acd07ea36e))
	- Phone SOPs
	  collapsed:: true
		- _Mini SOPs_
			- Locking and Unlocking Bootloader
			  collapsed:: true
				- Unlocking bootloader
				  source:: [https://www.xda-developers.com/how-to-unlock-bootloader-and-root-the-google-pixel-2-and-pixel-2-xl/](https://www.xda-developers.com/how-to-unlock-bootloader-and-root-the-google-pixel-2-and-pixel-2-xl/)
				  collapsed:: true
					- _Boot into bootloader_
						- _Unlock developer options_
							- Android Settings > About > tap Build 10 times?
							- Android Settings > System
					- adb reboot bootloader
					- fastboot flashing unlock
				- Lock bootloader
				  collapsed:: true
					- Pros/Cons
						- Pros
							- Protects from Evil Maid attacks (physical USB access)
						- Cons
							- Basically requires you to use stock OS or a security-focused ROM like GrapheneOS or [Calyx](https://workflowy.com/#/419015786f9e)<a href="https://workflowy.com/#/419015786f9e">OS</a> without root etc
							  source:: [https://teddit.net/r/LineageOS/comments/n7yo7u/a_discussion_about_bootloader_lockingunlocking/](https://teddit.net/r/LineageOS/comments/n7yo7u/a_discussion_about_bootloader_lockingunlocking/)
								- What is bootloader locking/unlocking?
								  collapsed:: true
									- The bootloader on your phone is the software responsible for loading your phone's operating system. It sits between the lowest level hardware firmware and the higher level operating system and takes care of several things to get your phone ready to load the OS.
									- This includes checking to make sure that only authorized operating systems run on the hardware by default. Authorized operating systems are usually signed by the manufacturer of the phone with a private encryption key to which only they have access, and this signature is checked before the operating system is allowed to load. This ensure that third parties don't modify/replace the operating system with malicious versions.
									- Some phones allow you to unlock the bootloader and run any operating system you want on your phone, signed or unsigned, or just modify the one that comes with it by default.
									- Basically, unlocking the bootloader skips the signature check during boot (along with a few other things) and allows any operating system to run on your phone. This is why you need to unlock your bootloader when running LineageOS or other custom ROMs.
								- I hear there are some security concerns with an unlocked bootloader...
								  collapsed:: true
									- The reason manufactures ship their phones with locked bootloaders is to protect against a class of security vulnerabilities called "Evil Maid" attacks ([https://en.wikipedia.org/wiki/Evil_maid_attack](https://en.wikipedia.org/wiki/Evil_maid_attack)).
									- Basically, if an attacker has physical access to a device with an unlocked bootloader, they can install malicious software on your device and you may never know about it.
									- How worried about this kind of attack should you be? Probably not very.
									- Unless you are being individually targeted by state actors or the like, these attacks are hard to do with little benefit for the typical ransomware and general hackers of the world. There are simply no roaming bands of hackers, scouring the pubs and restaurants to find unlocked phones to compromise, in day to day life.
									- However, that doesn't mean there is no concern, you should consider your own individual needs and risk profile with respect to lock/unlocking your bootloader.
								- After installing a custom ROM, should/can I relock the bootloader?
								  collapsed:: true
									- This is a more complex question, but in general, the answer is no.
									- If you were to just take your average phone with a custom ROM installed and relock the bootloader, you would get an error message when you rebooted and the phone would refuse to load the operating system. This is because the list of "approved" signing keys in most phones is limited to those that the manufacturer installed before shipping the phone to you.
									- This would "brick" your phone, making it unusable. Some phone can be recovered from this state, others might not be able to.
									- Now for the complexity... some phone support custom signing keys.
									- Modern Google Pixel and OnePlus devices allow you to install your own custom signing keys so that you can boot operating systems signed by them with a relocked bootloader. This is part of the Android Verified Boot (AVB) v2 specification and is not widely (maybe at all) supported beyond Google and OnePlus.
									- In these specific cases, you can theoretically relock your bootloader, but there are several issues with doing so which will be discussed next.
									- There are also a few phones (like the original Pixel/XL and OnePlus phones like the 5/5t and older) that don't support AVB v2, but can have their bootloaders relocked because they simply _never_ check to see if the OS is signed by the vendor, just that it has some valid signature on it. Most of the following discussion applies to these phones as well but there are some quirks that they do not suffer from, but likewise have less security as well. As all of these phones are now out of support from their respective vendors, making each and every one of them have more significant security issues than an unlocked bootloader, they will not be discussed further here.
								- Ok, but will relocking the bootloader get rid of that annoying/scary message during power on?
								  collapsed:: true
									- Probably not, at least not in the way you want. Android Verified Boot has specific bootloader messages depending upon what state it is in, you can read more about them here: https://source.android.com/security/verifiedboot/boot-flow
									- Basically, the only way to not have some kind of warning/alert message during boot is to have a locked bootloader with the vendors original OS. So while you can change the orange "Unlocked bootloader" message to a yellow "Custom OS" message, you'll still get _a_ message during boot.
								- Oh, ok, but will it help me pass ((649b13d2-3bf6-43ed-b52c-7bbcf094ca3c))?
								  collapsed:: true
									- Not really, SafetyNet is dependent on many things, including a locked bootloader. If you want to relock your bootloader for this reason I suggest you go no farther. Google can change SafetyNet requirements at any time and do so reasonably often.
								- Humm, well I have an AVBv2 supported phone and still want to relock my bootloader, now what?
								  collapsed:: true
								  Lineage Recovery is built in a mode that allows root + flashing anything. Need to build a version myself
									- Ok, but before you relock your bootloader consider what ROM you are going to install.
									- Using a custom ROM, like LineageOS for example, that is compiled as a userdebug build of Android will get you no benefits with locking the bootloader.
									- Android has three build variants (see https://source.android.com/setup/develop/new-device#build-variants for details) and LineageOS builds userdebug for the official releases.
									- For the main operating system itself, that's not much of an issue, but because Lineage Recovery is also built in userdebug mode, that's a problem. When Lineage recovery is built this way, it allows any package, signed or unsigned, to be installed on your phone. This effectively negates the benefits of locking the bootloader.
									- And userdebug recovery even allows you to shell in to the phone as root, which makes things even worse.
									- Other custom ROM may have different builds, but you need to understand what they are and what is enabled in them.
									- In fact most custom ROMs simply use TWRP or another third party recovery which has the same issues as they are designed to never even look at the signatures of the packages they are flashing to your device.
									- The way around this, is of course to build your own build of LineageOS in user mode so you can install it on your phone. Unfortunately some devices might not build successfully in user mode without modifying the source code and troubleshooting any issues that arise.
								- Ok, ok... I've built my own ROM in user mode... anything else?
								  collapsed:: true
								  Enable rollback protection flag, and create custom update package for firmware updates
									- Well yes actually.
									- Another feature of AVB is rollback protection, which basically verifies that your system partitions haven't been modified or corrupted. LineageOS disables this by default, so you'll want to enable that as well.
									- Oh... and about firmware updates.
									- Since you'll be locking your bootloader with a recovery that only supports your packages, you're going to have to manage firmware updates from your phone's manufacturer as well somehow.
									- You could do this by creating a custom update package that you sign, or by unlocking your bootloader temporarily (which will wipe all your data of course) to use TWRP or something else to flash the firmware and then relock the bootloader afterwards.
								- Look, I've got the firmware updates handled, what else is there?
								  collapsed:: true
								  Might need to add a prebuilt vendor image to build process
									- Does your device include the vendor partition when building Lineageos?
									- Some do, some don't, depending upon how the maintainer setup the build for LineageOS. If it does, you're ok.
									- If it doesn't... well, you've got another problem as now you have to add the "prebuilt" vendor image in to your build process. Otherwise that rollback protection we enabled a little while ago is going to be missing on the vendor partition, and that's kind of important.
								- Fine! I'll do all that, surely there can't be anything else... right?
								  collapsed:: true
								  No root access
									- Ah... well yes... and don't call me Shirley.
									- Did you want root access through ADB or Magisk?
									- You did? Oh, sorry about that.
									- User builds disable root access in ADB, and since you've enabled AVB and rollback protection, you can't just install Magisk since it would "corrupt" the boot partition and AVB would block the boot process. You'll need to integrate it in to your build process and then hope that it doesn't do anything strange and trip AVB or the rollback protection.
								- Alright, I'll live without root and all the other stuff, am I good to go now?
								  collapsed:: true
								  Monthly manual builds
									- Mostly, yes.
									- You still have to deal with building your custom ROM every month or so to get all the security updates from AOSP and your phone's vendor, and of course you'll have to manually install it through ADB sideload.
									- Unless of course you setup an OTA server to, which means you need web hosting... and more configuration changes in your build... and... and...
									- Well, you get the picture.
								- Great! I've got all that done...
								  collapsed:: true
								  GApps/microG in builds
									- Hang on a sec, did you think about GAPPS or microG?
									- I mean, you don't have to, but a lot of people seem to like to be able to access Google services for some reason and at the moment your custom build has neither of these services in it.
									- So, take some more time and integrate one of them in to your custom build, because just like Magisk, you can't install them after the fact.
								- What else could there be!?!
								  collapsed:: true
									- Well, there is something else to consider. Custom ROMs are often passion projects and sometimes a "bad" release will be made. This sometimes results in bootloops or other nastiness that you can usually troubleshoot and debug pretty easily... but with a locked bootloader, maybe not.
									- You won't have access to TWRP or other custom recoveries that would make it easier and to use them you would have to unlock your bootloader (which might not be possible as you've probably disabled that in developers options) which would wipe your data.
									- Likewise, when Lineage Recovery is built in user mode, it does not let you "upgrade" to an older version, making it impossible to reflash the OTA of the last working build you have.
									- This is a risk that you'll have to accept if you want to relock your bootloader.
									- Of course if you had a second "development" phone to test your builds on first, that would mitigate most of that risk. You don't mind spending some more money on one do you?
								- Well, honestly, that seems like far too much work, isn't their an easier way?
								  collapsed:: true
									- Of course, use the OS that came with your phone.
									- Or use an custom ROM that is specifically designed to be used with relocked bootloaders. There are a few around but they often have (for all the reasons stated above) very limited device support.
								- Sigh... is this discussion over yet?
								  collapsed:: true
									- Well if you made it this far, you probably are having second (third, fourth, etc.) thoughts about relocking your bootloader, which is probably for the best.
									- Overall, it's not recommended for the vast majority of people to attempt to relock their bootloader. It's simply too much work and risk for too little reward and security.
								- Having said that, if you have any inclination to do even more research, there are a few resources you might want to look at over on XDA:
								  collapsed:: true
									- [Guide: Relock bootloader with custom rom on oneplus 5/5t](https://forum.xda-developers.com/t/guide-relock-bootloader-with-custom-rom-on-oneplus-5-5t.3849299/)
									- [[GUIDE] Re-locking the bootloader on the OnePlus 6t with a self-signed build of LOS](https://forum.xda-developers.com/t/guide-re-locking-the-bootloader-on-the-oneplus-6t-with-a-self-signed-build-of-los.4113743/) (disclaimer: I am the author of this guide)
									- [[GUIDE] Re-locking the bootloader on the OnePlus 8t with a self-signed build of LOS 18.1](https://forum.xda-developers.com/t/guide-re-locking-the-bootloader-on-the-oneplus-8t-with-a-self-signed-build-of-los-18-1.4259409/#post-84871391) (disclaimer: I am the author of this guide)
									- [[GUIDE] Re-locking the bootloader with a pre-built custom ROM, such as LineageOS official](https://forum.xda-developers.com/t/guide-re-locking-the-bootloader-with-a-pre-built-custom-rom-such-as-lineageos-official.4260825/)
								- You can also [search this subreddit](https://teddit.net/r/LineageOS/search/?q=lock%20bootloader%20&restrict_sr=1) for many posts on the subject.If you do decide to continue, I would recommend three things:
								  collapsed:: true
									- Go in to the process with a mindset that, if something goes wrong, you don't mind having a nice shiny high-tech paperweight at the end of it.
									- Don't try this on your daily driver phone, pick up a phone to experiment on. Only after you are confident with the process move to your primary phone.
									- And of course, as always, backup often!
								- So if it wasn't blatantly obvious by now, I wouldn not suggest attempting to relock your bootloader with a custom OS. Good luck!
								- 1 Backlink
								  collapsed:: true
									- See [Basically requires you to use stock OS or a security-focused ROM like GrapheneOS or CalyxOS without root etc](https://workflowy.com/#/ea8c2616a63e)
							-
					- How-to
						- adb reboot bootloader
						- fastboot flashing lock
			- Boot into custom recovery
			  id:: 6318fc64-69c1-47ce-ae59-ddbaec207165
			  collapsed:: true
				- _If it's already installed as a recovery _
					- _If rooted as well_
						- Use Power App (F-Droid) which allows rebooting into recovery directly
					- _If unrooted_
						- With the device powered off, hold Volume Down + Power and choose Recovery Mode.
						- OR
						- `adb reboot recovery` whilst plugged into PC and phone is on
					- Related:
						- ((649b13cd-41c8-4da3-965e-3e1c2e4d7889))
						- {{embed ((649b13cd-aa0d-4988-b726-e10855d7a83c))}}
				- _Otherwise_
					- With the device powered off, hold Volume Down + Power until you get to Bootloader mode.
					- OR
					- `adb reboot bootloader` whilst plugged into PC and phone is on
				- (optional) Download the latest TWRP boot image
				  e.g. https://eu.dl.twrp.me/beryllium/
				- Navigate to folder with TWRP boot images
				  `cd /home/boss/Documents/OPTIONAL/Android`
				- Boot into TWRP
				  id:: 649b13cd-aa0d-4988-b726-e10855d7a83c
				  `fastboot boot twrp-3.3.1-0-sailfish.img`
			- Flash TWRP as a recovery
			  id:: 649b13cd-41c8-4da3-965e-3e1c2e4d7889
			  collapsed:: true
				- Note: not much point if using LineageOS since each update will replace it with their own custom recovery Lineage Recovery. Instead just ((649b13cd-aa0d-4988-b726-e10855d7a83c)) when necessary
				- _Steps_
					- ((649b13cd-aa0d-4988-b726-e10855d7a83c))
					- `fastboot flash recovery recovery.img`
					- Flashed TWRP ZIP file on my device, through TWRP
						- OR Install > Install Image > select it > choose Recovery (as location to install image)
							- Download the latest TWRP image file (.img) from the download link and boot TWRP. Go to install and find and select the Images... button. Browse to the image that you downloaded and select it. Choose recovery and swipe to flash.
						- App Install Method (Requires Root):
							- Download the Official TWRP App (root required):
								- Play Store (recommended)
								- No Play Store? Download the latest version here.
							- Install the app and open it. Agree to the Terms. Select TWRP Flash. Select your device from the device list (beryllium) and choose a version. The file will download to your Downloads folder. Browse to and select the file. Tap on Flash to Recovery. Find out more about the app here.
				- **Note: This will remove Magisk or other superuser **
				- _Alternative_
					- App Install Method (Requires Root):
						- Download the Official TWRP App (root required):
						- [Play Store (recommended)](https://play.google.com/store/apps/details?id=me.twrp.twrpapp)
						- [No Play Store? Download the latest version here.](https://dl.twrp.me/twrpapp/)
						- Install the app and open it. Agree to the Terms. Select
						- TWRP Flash. Select your device from the device list (beryllium) and
						- choose a version. The file will download to your Downloads folder. [](https://twrp.me/app/)
						- Browse to and select the file. Tap on Flash to Recovery. Find out [more about the app here.](https://twrp.me/app/)
			- Make a Nandroid backup using TWRP
			  collapsed:: true
			  id:: 6318fc64-fadc-4435-bc98-8cba5f73142c
				- First, see ((649b13cd-aa0d-4988-b726-e10855d7a83c))
				- TWRP: Backup
				  collapsed:: true
					- Most important - backup `data` partition
						- What is it
							- Basically user apps
							- AKA /sdcard/Android
							- It'll include everything in `sdcard/Android/`
								- e.g. `sdcard/Android/data`, `sdcard/Android/obb`, `sdcard/Android/media`
							- Note: doesn't include everything else in `data/media/` AKA `sdcard`
								- **WARNING: **`data` partition backups don't include `/data/media/`, which is basically the viewable sdcard/storage folder
								  source:: https://twrp.me/faq/backupexclusions.html
									- Need to create a separate backup of that via MTP or adb pull
										- See [Copy the MTP-mounted files on PC or an external hard drive](https://workflowy.com/#/7126bb923af4)
					- In TWRP recovery go to Backup > select "Boot," "System," and "Data"
						- Select Storage: microSD card (if phone has one)
					- 1 Backlink
						- Easiest: [TWRP: Backup](https://workflowy.com/#/13bddb43aee2) but instead select "Internal Storage
				- (optional) Check backup files exist
				  collapsed:: true
					- TWRP: Advanced > File Manager
						- /sdcard/TWRP/BACKUPS
						  AKA /data/media/0/TWRP/BACKUPS
					- Or should show up in file manager on laptop
				- (optional) Copy these files to computer
				  collapsed:: true
					- Should show up in file manager as a phone
						- Go into `TWRP` folder
						- Copy & paste the folder through the file manager to wherever you want it
						  e.g. desktop or external hard drive
					- If not then:
						- TWRP: Mount > Data > Select Storage: Internal Storage > Enable MTP
					- Copy the MTP-mounted files on PC or an external hard drive
						- A) Use Dolphin GUI file manager to go to Devices, then copy all files (except possibly /Android/) and paste to PC or an external hard drive
							- Pros/Cons
								- Pros
									- Gives good progress percentage, speed and time left estimates
								- Cons
									- Possibly slower, same way deleting a folder using Dolphin or slower than `rm`
						- B) Use terminal (e.g. Yakuake) to navigate to MTP folder
							- Install gvfs-fuse in order to view filesystem
							  sudo apt install gvfs-fuse
							- Consider using a different FUSE method to mount via MTP if `gvfs-fuse` doesn't work
							  [https://wiki.archlinux.org/index.php/Media_Transfer_Protocol#FUSE_filesystems](https://wiki.archlinux.org/index.php/Media_Transfer_Protocol#FUSE_filesystems)
							- MTP mount is usually located at `/var/run/user/1000/gvfs`
							- cp -a /source/. /dest/ (this includes .dotfiles)
								- A) Copy current directory recursively (all) to another directory
								  cp -r \* /media/boss/Transcend/1TEMP-BACKUP/Pixel-home/
								- B) Copy target directory recursively (all) to another directory
								  cp -a /something/data/media/0/ /media/boss/Transcend/1TEMP-BACKUP/Pixel-home/
									- cp -a /source/. /dest/ (this includes .dotfiles)
						- C) ADB pull
						  adb pull /sdcard/TWRP/ /media/boss/Transcend/1TEMP-BACKUP/Pixel-home/
						- 1 Backlink
							- See [Copy the MTP-mounted files on PC or an external hard drive](https://workflowy.com/#/7126bb923af4)
				- (optional) Backup everything TWRP can't backup
				  collapsed:: true
					- Easiest: [TWRP: Backup](https://workflowy.com/#/13bddb43aee2) but instead select "Internal Storage
					- or
					- AKA most of `sdcard`
						- Exclude `sdcard/Android/`as it's copied during the previous step
						  _See_ [TWRP > Backup](https://workflowy.com/#/13bddb43aee2)
						- Exclude /TWRP - since that should be copied by the previous step ([(optional) Copy these files to computer)](https://workflowy.com/#/bcbb7c6b86b2)
						- Exclude any folders being synced via Syncthing
							- [[Software]] : [Syncthing](((6312a076-d503-40c4-b98f-cbdef17b1fcb)))
							- Related:
							  [Copied entire /sdcard/ (includes Titanium backup) to my external HDD via adb pull (incase my `data/media/` i.e. `sdcard` gets wiped or if I need to)](https://workflowy.com/#/0f249c0b7aed)
			- Flash stock Android
			  collapsed:: true
			  id:: 6318fc64-8e87-4bef-9ac4-638f34aebb6c
				- OTA image (advantage: without the need to wipe the device or unlock the bootloader) [TWRP > ADB Sideload > ]
				  https://developers.google.com/android/ota#sailfish
				- OR
				- Factory image [TWRP > flash?]
				  https://developers.google.com/android/images#sailfish
					- Instructions here
					  https://developers.google.com/android/images#instructions
		- _Full SOPs_
			- ((630f96f0-f2c4-4706-9d72-58e13201e03f)) : ((649b13d1-e58f-450a-b61f-a9f3881d2384))
			- Full Restore
			  id:: 649b13cd-71ac-45d5-8723-269f9c7cb15c
			  collapsed:: true
				- [[2024-11-05 Tuesday]] Had to install from scratch because backup SOP isn't suitable for migrating to ((63209286-6f40-4063-9fdc-2543251d416e)) currently
				  id:: 6729eac8-2eba-48ae-b76e-1ed1a024b3f3
				  collapsed:: true
					- Because of ((649b13cd-b813-4be7-a002-0163db44c803)) : ((6729e516-4f9c-4e62-8693-b8aa0a1e9f03))
				- # Current
				  Last updated: [[2024-11-05 Tuesday]]
					- ((63209286-6f40-4063-9fdc-2543251d416e)) : ((67290801-caaa-4f62-ade4-ab9fb82ca60e))
					- ((63209286-6f40-4063-9fdc-2543251d416e)) : ((6729f0d1-74b9-4270-a9ac-64ddfe24eddc))
					- ### Other setup
						- Use the default browser to download and install ((6513e187-8f79-48e6-8db3-f8038bbfda5a))
						- Enable developer mode by tapping in the Android Settings > About > Build 10 times
						- Enable USB debugging - it's needed for ((63a9ade4-0cdf-4680-a839-6b6f92e57f51))
					- ## App installs
					  id:: 672a3ccc-85a0-4b69-8dff-8bb6ec5fe0fc
						- ### ((6513e187-8f79-48e6-8db3-f8038bbfda5a)) full restore
							- F-Droid : ((6729ee56-7b89-45e7-b2ae-f6f71fccf575))
							- Update ((649b13cf-e2cb-4e21-8bf4-27f84e9b79f3)) if old phone available
								- Old phone : ((6513e187-8f79-48e6-8db3-f8038bbfda5a)) > Manage installed apps. Manually install these
							- Can't install yet on Android 15 as too new
								- ActivityWatch
								- Native Alpha
								- OpenScan
								- Session
						- ### ((66d095d8-4f55-4927-bc65-eaa9a58b0630)) SOP
							- Add my Google accounts
								- aaronsollesse + bluesteelmagnet
									- Needed to reinstall paid apps - ((649b13ce-87fa-47db-b5fd-95b47b8ac79e))
									- Allows restore of WhatsApp backup
							- ((66d095d8-4f55-4927-bc65-eaa9a58b0630)) settings
								- Turn auto-update apps off
								- Turn off updates available notification
							- Update ((63209285-e561-4da1-bf20-0996e9ee49f4)) if old phone available
							- Install all ((63209285-e561-4da1-bf20-0996e9ee49f4))
						- Related: ((6306a77a-3999-4fd1-99dd-630a77dd542c)) : ((644c0ace-86c4-434b-be9f-d475fa53c28a))
					- ## Post- ((672a3ccc-85a0-4b69-8dff-8bb6ec5fe0fc))
						- Rearrange the Quick Settings tiles
						  collapsed:: true
							- Meta
								- Internet quick tile is an Android upstream merge of the old Wi-Fi and Mobile Data tiles, and GrapheneOS [won't undo that change](https://github.com/GrapheneOS/os-issue-tracker/issues/1615#issuecomment-1296322240)
							- Current order [[2024-11-05 Tuesday]] from left to right:
								- Torch
								- Bluetooth
								- **Wi-Fi**
								- **Mobile Data**
								- Auto-rotate
								- Do Not Disturb
								- Alarm
								- Extra Dim
								- **Lower Brightness Pro**
								- Hotspot
								- **USB Tethering**
								- **Caffeine**
								- Aeroplane mode
								- Battery Saver
								- Screen Recording
								- Mic access
								- Camera access
								- Night Light
								- Location
								- Security & Privacy
								- Quick Share
								- Screen Cast
								- **Shazam**
								- QR Code scanning
								- One-handed mode
					- ## App-specific setup
					  id:: 672a38ac-0db1-4243-b820-5c0d4d472640
						- ((649b13cf-e2cb-4e21-8bf4-27f84e9b79f3)) individual setup
							- ### High priority
								- Obtainium - import settings from `/CORE/Obtainium` then install each app
								- ((649b13ce-c5f5-4c70-a58f-6f411b515aaa)) : ((672bfa93-b520-4b0e-8061-bbce191522cf))
								- OpenKeychain
								- ((663915c8-abda-4f12-8175-26e94f6c120d))
							- ((631fa97e-a0a9-406c-b7b9-20536d421090))
							- ((649b13ce-166b-43de-bea7-4262b566ccce))
							- ((649b13ce-c4a3-4f27-87fb-25442ce2a9a0))
							- ((63209285-2e05-40f2-bce9-5b8d813eea86))
							- ((6312a075-ceb2-4a57-adc5-2a27f91e865c)) : ((672bf2de-8e95-49de-b849-70ae1553a571))
						- ((63209285-e561-4da1-bf20-0996e9ee49f4)) individual setup
							- ### High priority
								- ((649b13ce-20b8-4de2-85e2-d39f540deb85)) : ((67322b1e-4afe-4529-8844-722ed5d9d4c2))
								- ((663b24fb-f1f2-4dbe-ae47-d3a910654835))
							- ((62f93609-8bb0-4716-95f8-e7f76b2669e6))
							- ((64e0946f-ca07-48a0-bac6-1b7bba5c490f)) Pocket
							- ((63216f53-22cf-428a-9193-e5a423158e2b))
						- Keyboard
						  id:: 644c0acc-dc08-4f95-a77e-d52a9bb2ebed
						  collapsed:: true
							- Software
								- Options
									- ((65ce1d71-7db1-46e3-a4e3-1d91107c81c2))
									  [[2024-11-12 Tuesday]] preferred option
									- ((649b13ce-93ff-441e-b914-ff387f720e3b))
									- [FUTO Keyboard](https://keyboard.futo.org/)
									  id:: 66825a1d-c720-4353-9757-af437e7343c2
									  collapsed:: true
										- Repos
											- [Issues-only](https://github.com/futo-org/android-keyboard)
											- [Source code](https://gitlab.futo.org/alex/latinime)
										-
									- Gboard
									- AnySoftKeyboard
									  id:: 644c0acd-e3aa-47ab-877f-3d8028e5086d
									  collapsed:: true
										- Cons
											- Swipe gesture typing needs it's accuracy improved
												- [https://github.com/AnySoftKeyboard/AnySoftKeyboard/issues/1933](https://github.com/AnySoftKeyboard/AnySoftKeyboard/issues/1933)
												- [https://github.com/AnySoftKeyboard/AnySoftKeyboard/issues/1792](https://github.com/AnySoftKeyboard/AnySoftKeyboard/issues/1792)
												- [https://github.com/AnySoftKeyboard/AnySoftKeyboard/issues/2731](https://github.com/AnySoftKeyboard/AnySoftKeyboard/issues/2731)
												- [https://github.com/AnySoftKeyboard/AnySoftKeyboard/issues/2534](https://github.com/AnySoftKeyboard/AnySoftKeyboard/issues/2534)
												- [https://github.com/AnySoftKeyboard/AnySoftKeyboard/issues/2613](https://github.com/AnySoftKeyboard/AnySoftKeyboard/issues/2613)
										- Missing
											- Keyboard shortcuts? eg Action: from atn (haven't tested if they have it or not)
												- Abbreviations - already implemented?
												  https://github.com/AnySoftKeyboard/AnySoftKeyboard/issues/570
									- AOSP keyboard APK
									  collapsed:: true
									  Doesn't have settings to turn off/on gesture typing however
										- Indic language version on F-Droid
										  https://f-droid.org/repository/browse/?fdfilter=keyboard&fdid=org.smc.inputmethod.indic&fdpage=2
										- AOSP libraries online somewhere
											- https://android.googlesource.com/platform/packages/inputmethods/LatinIME
										- Lollipop keyboard - dev previews
											- http://forum.xda-developers.com/android/apps-games/lollipop-keyboard-phones-root-t2910268
										- http://forum.xda-developers.com/sitesearch.php?q=aosp%20keyboard
									- Google's gesture typing module
									  collapsed:: true
									  **Requires root to install**
										- **Requires root**
											- "I'm afraid I'm not able to roll the keyboard into an APK for you, sorry to disappoint. You do, indeed, need root to install the binary blob."
										- The AOSP keyboard can work with swype if you're willing to run a small binary blob from google called libjni_latinimegoogle.so
										- I got it from opengapps
										  http://opengapps.org/
											- by selecting the proper version of gapps and finding the library in the zip file. I found it in 'optional/swypelibs-lib-arm.tar.xz/common/lib/libjni_latinimegoogle.so'
										- You can install it with a root shell (I used adb shell on my rooted phone) with the following commands (change the location of libjni_latinmegoogle.so to wherever you have yours in the cp command):
											- mount -o remount,rw /system
											- cp /storage/emulated/0/libjni_latinimegoogle.so /system/lib/libjni_latinimegoogle.so
											- chmod 644 /system/lib/libjni_latinimegoogle.so
											- mount -o remount,ro /system
											- reboot
								- Ideal features
								  collapsed:: true
									- Gesture typing
									- Personal dictionary (for autotext/shortcuts/text expansion)
								- Non-root solution
								  collapsed:: true
									- Stock keyboard (likely doesn't have addon/personal dictionary, so a non-starter)
									- Google Keyboard from app store (every feature but theoretical privacy risk)
								- Easy solution - download AOSP keyboard + enable gesture typing (requires root)
								  collapsed:: true
									- Gesture Typing
									  collapsed:: true
										- Install "LatinImeGoogle.apk" - AOSP Stock keyboard (LatinIME)
										  collapsed:: true
											- source available here https://android.googlesource.com/platform/packages/inputmethods/LatinIME/
										- copy the "libjni_latinimegoogle.so" file (gesture decoder) to the System\lib folder and reboot
										  collapsed:: true
											- A) Copy from PC (in Vault)
											- B) Find file on Android
											  collapsed:: true
												- The library inside the apk is called "libjni_latinimegoogle.so" under /lib/<arch_type>/ inside the apk.
												- You can extract this library from within android using program like root explorer and on PC using android apktool (http://code.google.com/p/android-apktool/)
											- Rename this shared library to "libjni_latinime.so" to replace the AOSP built one and it will decode the gestures through the AOSP based keyboard.
									- Direct version
									  collapsed:: true
										- http://forum.xda-developers.com/android/apps-games/app-aosp-android-keyboard-5-rows-row-t3142784
								- Creating custom keyboard
								  collapsed:: true
									- Compiling own LatinIME
									  collapsed:: true
										- https://stackoverflow.com/questions/28976193/android-keyboard-build-latinime-and-package-w-libjni-latinime-so?rq=1
										- https://stackoverflow.com/questions/19373833/android-latinime-build?rq=1
										- https://yyl.github.io/android/2014/06/16/build-aosp-keyboard.html
									- AutoText/Text Expansion/Personal Dictionary/User Dictionary
									  collapsed:: true
										- Rooted
										  collapsed:: true
											- https://www.reddit.com/r/Android/comments/2f9mcn/modxposed_macro_text_expansion_requires/
											- http://repo.xposed.info/module/net.mitchtech.xposed.macroexpand
										- custom words are saved in a database at /data/data/com.android.inputmethod.latin/databases/auto_dict.db
									- Reverse engineering APKs https://ibotpeaches.github.io/Apktool/
									- AnySoftKeyboard apk
								- [OpenGapps comes with Google's swype gesture typing libraries](https://github.com/opengapps/opengapps/wiki/Advanced-Features-and-Options#skip-googles-swype-library-setting)
								- [How to manually install Google's swype gesture typing libraries via adb](https://www.reddit.com/r/LineageOS/comments/9mgpbk/is_swipe_texting_possible_on_a_nongapps_install/e7endbc)
								  collapsed:: true
									- It is indeed possible to swipe using the default AOSP keyboard in LOS and no Google Apps/Microsoft. I'm surprised no one has mentioned it yet (unless I have misunderstood your post.) There is a swipe library which you can push to your phone which will give you swipe capability. However, you'll need root.
									- For reference, the library is called "libjni_latinimegoogle.so" and you need to push it to "/system/lib/" (which is why you need root.)
									- To get the lib, go to https://opengapps.org/ and download pico version (the smallest in size) to your desktop, taking care to select the proper architecture (e.g. ARM) and Android version (e.g. 7.1).
									- Extract the zip file and look for the directory called "Optional" and inside there should be a file called "swypelibs-lib-arm.tar.lz" (or some variation of that.) You will have to extract that file as well to have access to "libjni_latinimegoogle.so".
									- You will then need to push "libjni_latinimegoogle.so" to "/system/lib" on your phone; which means using ADB.
									- adb devices
									- adb root
									- (Then mount file system read-write with next command)
									- adb remount
									- adb push libjni_latinimegoogle.so /system/lib/
									- adb unroot
									- (you can also kill server at this point if you wish)
									- adb kill-server
									- Reboot your phone. (This will remount the file system read-only, while detecting the new swipe lib.)
									- On your phone, go into Settings, Languages & input, Virtual keyboard, Android keyboard (AOSP), Gesture Typing and enable it there, etc.
							- Add words to personal dictionary
							  collapsed:: true
								- Action:, Next Action etc
						- ### Stuff which hasn't been exported over
							- Chance - bookmarked
							- ((649b13ce-166b-43de-bea7-4262b566ccce))- tabs
							-
					- ## Post- ((672a38ac-0db1-4243-b820-5c0d4d472640))
						- Turn off 2G to prevent vulnerability to IMSI-catchers
						- Setup remote wipe/lock/ring
						  collapsed:: true
							- https://www.google.com/android/devicemanager
							- Ring + Lock + Wipe should be available
							- If not check on Android phone > Settings > Security > Device administrators > tick Android Device Manager
						- Speed up animations
						  collapsed:: true
							- Settings > System > About Device > tap Build Number 7 times to unlock Developer Options
							- Developer options >Drawing section.
							- You’ll find the three options we want here — Window animation scale, Transition animation scale, and Animator duration scale.
							- 0.5x or off
						- Update syncthing desktop web side to use `/home/boss/Music/Music-Library/- NEWMUSIC` for music folder
						- Change each ((649b13ce-c5f5-4c70-a58f-6f411b515aaa)) from Receive-Only to Send & Receive when I'm ready to stop using old phone
						  id:: 672c007c-7fc5-4933-a826-d195748895b0
						- ((6729fae7-094c-4af5-ac38-4685333f7490))
				- {Archive}
					- Install ((630f96f0-f2c4-4706-9d72-58e13201e03f)) or ((649b13d2-a633-4de3-aa08-e24106059dab)), ((649b13cd-e6ad-4655-91b6-5dcdce92aaed))
		- Incomplete
			- Setting up a moderately private Android for non-nerds (for friends/relatives)
			  collapsed:: true
				- GApps (because Google Maps primarily)
				- LineageOS (because more privacy preserving OS)
				- _Google Play Store_
				  collapsed:: true
				  Has automatic updates for apps
					- AnonAddy
					- Amaze
					- ((650aae22-a7a0-4980-b626-3e91b2b33d05))
					- ((649b13ce-1fe5-4f94-b330-5dcef6fb807e))
					- Firefox
					- Google Maps
					- See [K-9 ](https://workflowy.com/#/30959deb9ab6)<a href="https://workflowy.com/#/30959deb9ab6">Mail</a>
					- Lawnchair Launcher
					- Markor
					- Privacy Indicators (IzzyOnDroid)
					- QKSMS
					- Signal
					- Simple Gallery
					- Twidere X
					- VLC
					- WhatsApp
					- YouTube
				- F-Droid
				  collapsed:: true
					- Shelter
					- QuickTiles
						- LineageOS 19 (Android 12) has a [Redesigned volume panel in LineageOS 19](https://workflowy.com/#/570bb6a9db5b) which allows toggling between vibrate and silent mode
						- 1 Backlink
							- Replaces F-Droid app [QuickTiles](https://workflowy.com/#/a860045b6873) which I used for toggling it before
			- Resetting a phone which won't boot
			  id:: 6318fc64-2500-47a7-abc5-92337d9cbb55
			  collapsed:: true
				- Test runs
				  id:: 6318fc64-841c-43e5-bf9d-b64c9fb80389
					- **Changelog - update after**
					  [23/9/20 - LineageOS 17.1 update resulted in phone being unbootable](https://workflowy.com/#/ceaf6bd322fd)
					- Thu, Nov 19, 2020 - Flashing
				- Make a full backup if possible ( ((6318fc64-fadc-4435-bc98-8cba5f73142c)) )
				- Make several other backups if possible
					- Signal
					- ((66def4fb-d36b-4bff-8549-5642b8d4712e))
						- Obtaining Steam 2FA
							- [About alternative rooted solution · Issue #10 · steamguard-totp/steamguard-shared-secret · GitHub](https://github.com/steamguard-totp/steamguard-shared-secret/issues/10)
							  collapsed:: true
								- ```
								  cd /tmp; wget "https://github.com/frida/frida/releases/download/16.0.8/frida-server-16.0.8-android-arm64.xz"
								  unxz frida-server-16.0.8-android-arm64.xz
								  sudo adb root
								  sudo adb push frida-server-16.0.8-android-arm64 /data/local/tmp/
								  sudo adb shell "chmod +x /data/local/tmp/frida-server-16.0.8-android-arm64"
								  sudo adb shell "/data/local/tmp/frida-server-16.0.8-android-arm64"
								  
								  yay -S aur/python-frida # use your brain here
								  cd /tmp; wget https://gist.githubusercontent.com/acuifex/1b80ac3490381801c79f9ea20ab763f4/raw/2540e65f18948e8650bcd1b83b97f2aca4dda1c6/dump.py
								  # if raw link somehow goes bad: [steam shared secret dump script · GitHub](https://gist.github.com/acuifex/1b80ac3490381801c79f9ea20ab763f4)
								  python3 ./dump.py
								  # enter into guard section in the steam app on your phone
								  
								  # clean up the server
								  sudo adb shell "rm /data/local/tmp/frida-server-16.0.8-android-arm64 /data/local/tmp/re.frida.server/"
								  
								  ```
								- I might add that the time my comment is written, the previous answer no longer outputs the direct otp code.
								- Instead it's something like
								- ```
								  {
								  "accounts": {
								  "NUMBERS": {
								  "shared_secret": "som/ething=",
								  "identity_secret": "something=",
								  "secret_1": "something=",
								  "serial_number": "a number",
								  "revocation_code": "the backup code",
								  "account_name": "your account name",
								  "token_gid": "some token",
								  "confirm_type": 3
								  }
								  }
								  }
								  ```
								-
								- To get the otp code, copy the shared_secret, decrypt base64 and encrypt to base32 :
								- ```
								  echo "<shared_secret>" | base64 -d | base32
								  ```
					- ((649b13ce-20b8-4de2-85e2-d39f540deb85))
				- Check if existing backup solutions are working properly
					- [[Software]] : [Syncthing](((6312a076-d503-40c4-b98f-cbdef17b1fcb)))
					- SeedVault
					- Neo Backup
					- ((63216f53-22cf-428a-9193-e5a423158e2b))
				- Flash the same ROM/stock system image again
				- If that doesn't work, then ((6318fc64-8e87-4bef-9ac4-638f34aebb6c))
				- If that doesn't work, then factory reset using TWRP
					- Wipe > Factory Reset (does `data` but not `data/media/`
					  i.e. wipes apps but not generic folders
				- First boot
				  id:: 6318fc64-1ae2-4d95-be7c-14e631a42b22
			- Android-based workflow
			  id:: 63412f42-1797-4d76-9607-7351eafe4f40
			  collapsed:: true
				- Pros/Cons
					- Cons
						- I have an eGPU and am a gamer - even current laptop isn't sufficient
						- Laptop is the best form factor for portable workstation
				- [PRoot - allows running full Linux GUI apps](https://teddit.froth.zone/r/fossdroid/comments/xy014z/for_those_who_want_to_run_foss_video_editors_on/)
				  id:: 644c0acd-1c33-433f-bdc2-9af37717acaf
					- [PRoot](https://wiki.termux.com/wiki/PRoot)
				- [AnLinux - run Linux on Android without root. Built on Termux and PRoot](https://github.com/EXALAB/AnLinux-Adfree)
				- ((649b13ce-0b9e-4741-ba6d-7959858e3443)) with code server then vscode.dev in the browser. Repo and pipelines are in ADO.
				  id:: 644c0acd-6461-4321-b905-37253e76b2c3
					- For web development there is a neat full stack app called AWD, then I use an app called Droid Inpsect Browser to get developer tools. And finally I have a pretty beefy web server app called Android Web Server.
					- [Termux - code-server Docs](https://coder.com/docs/code-server/latest/termux#installation])
				- Andronix - Linux distributions on Android
				  id:: 63413f29-f610-4c39-a8bc-34e622d2d540
				  collapsed:: true
					- Pros/Cons
						- Pros
							- Supports multiple distros including Ubuntu, Fedora, Manjaro
						- Cons
							- Android 12 breaks it
								- I think right now with Android 12 there's a huge limitation now with some background processing that Google themselves aren't fixing until Android 13. You can Google "Android 12 breaks andronix". I haven't gotten a stable virtual desktop in months. I've been using native apps in replacement (which are poor replacements naturally compared to their desktop counter parts). Other than that I've been doing a lot of react development with the tab still. The file management is wonky but you're able to grant access pretty easy with more up to date apps now. In ((649b13ce-0b9e-4741-ba6d-7959858e3443)) there's just a couple commands to put in (no root needed). I don't know them off the top of my head but quick Google search will show them.
							- [Limitations](https://docs.andronix.app/get-started/limitations/)
								- Can't mount external hardware like drives and adapters
								- Has to be installed on internal storage not SD cards
								- Lacks Flatpak+Docker+Snap support due to architecture differences and missing kernel features in the PRoot environment
					- Tutorial
					  collapsed:: true
						- {{video https://youtu.be/jvuufPWKF3k}}
							- {{youtube-timestamp 61}} Need AndroNix, ((649b13ce-0b9e-4741-ba6d-7959858e3443)) and VNC Viewer apps
							-
					- https://andronix.app/
					- https://github.com/AndronixApp
					- https://play.google.com/store/apps/details?id=studio.com.techriz.andronix
					- [Compatible with Samsung DeX](https://teddit.adminforge.de/r/SamsungDex/comments/s3j9k9/andronix_dex_is_an_incredible_combo_tab_s7_and/)
					- ((63219e35-31c8-4454-9e84-be51a2684aae))
				- ((63219e35-fae2-4fe8-a220-1adba4633994))
				- Accessories
					- See VR glasses / ((633b7502-b358-45fb-95d2-5fc35ed27d3f))
			- Detecting app-based trackers
			  collapsed:: true
				- ((63734d34-65d7-41d7-9aec-6a92ee6729d7))
					- {{embed ((63734d34-65d7-41d7-9aec-6a92ee6729d7))}}
			- Debloating
			  collapsed:: true
				- [GitHub - Universal-Debloater-Alliance/universal-android-debloater-next-generation: Cross-platform GUI written in Rust using ADB to debloat non-rooted Android devices. Improve your privacy, the security and battery life of your device.](https://github.com/Universal-Debloater-Alliance/universal-android-debloater-next-generation)
		- UNSORTED
			- _Current phone experiments_
			  collapsed:: true
				- _Main phone:_ LineageOS 17.1 (Android 10)
				- _Spare_: LineageOS 16 (Android 9) for microG
				- Future:
			- _Troubleshooting_
			  collapsed:: true
				- {Archive}
					- [Used EmojiSwitch to install iOS 12.1 beta emojis, now can't connect to internet via WiFi or cellular data](https://workflowy.com/#/365c87126424)
			- Setting up new phone
			  collapsed:: true
				- Restart phone and complete initial setup steps
				- _Full app backup setup_
				  id:: 6318fc64-68b1-45e2-a20d-c92068e956af
					- September 2022 review
						- Options
							- ((6318fc65-99f9-4edb-a705-eb1deb420890))
							- [Neo Backup](https://f-droid.org/en/packages/com.machiav3lli.backup/)
							  id:: 649b13cd-7aed-4183-9c8c-ebc8ed613b4b
							  collapsed:: true
							  AKA OAndBackupX
								- Cons
									- Doesn't have a setting up backup apps whose data size has changed
										- E.g. if I update my Nova Launcher settings like which app folders exist, it won't backup. Only if I actually update the app will a backup trigger
										- Instead have to use a periodic backup based on X days since last backup
										- [https://github.com/machiav3lli/oandbackupx/issues/241](https://github.com/machiav3lli/oandbackupx/issues/241)
							- ((63216f53-22cf-428a-9193-e5a423158e2b))
							- [DataBackup | F-Droid - Free and Open Source Android App Repository](https://f-droid.org/packages/com.xayah.databackup.foss/)
						- Status
						  id:: 6320392d-c8ac-40d9-8d8c-17624fc73294
							- ((6318fc65-99f9-4edb-a705-eb1deb420890)) - restored all apps, but not the app data for most of them. On a second restore, it failed to detect the most recent SeedVault backup and instead did one from a year ago
							- OAndBackupX - completely failed to restore. Deleted all these backups and updated the app to newest version of Neo Backup
							- ((63216f53-22cf-428a-9193-e5a423158e2b)) - worked, though with some caveats
							  id:: 631fa93b-a7e4-477a-a4d5-d8d90298fa2e
								- some apps I had to clear the app data for because app was in some way corrupt
									- Signal - note: restore using native file picker, as using Amaze File Manager caused backup file to not be recognised
									- Obsidian - open `/ATHENAEUM/Notebook/`
									- Element > ((6320335e-00d8-465d-bc7e-70e08bc9a106))
								- Some apps just needed to relogin
									- ((663b24fb-f1f2-4dbe-ae47-d3a910654835))
									- Uber
									- Instagram
								- Some apps required manually configuration for other reasons
									- Syncthing-Fork - required manual config because my internal storage wasn't copied to the new install and I instead had to use this app to copy it. Had to set folders to Receive Only on phone to initiate it and re-add some folders
									- ((65166ca4-1398-465a-8ff7-029210238874)) - go to Android Settings > Apps > Default apps > Opening links > NewPipe > enable the four youtube domains
									- Turn off ((631fa93c-15e7-4ef2-9b41-a116b90d39bd)) for relevant apps
					- {Archive}
						- [Titanium Backup](https://play.google.com/store/apps/details?id=com.keramidas.TitaniumBackup)
						  id:: 649b13cd-4504-4d24-8dc2-d589cedd0eea
						  collapsed:: true
							- _Cons_
								- Hasn't been updated since Nov 2019 (checked via Aurora)
								- Fri, Jan 15, 2021 - can't open Titanium without it crashing. Tried to install brand new and old ones, same thing
							- TXT file for license
							  collapsed:: true
								- Full-text
								  This is your license file for Titanium Backup.
								  (Do not modify this file)
								  ```
								  #
								   Instructions:
								   - Copy this file (TitaniumBackup_license.txt) to your SD card (not in a folder)
								   - Start Titanium Backup and verify that your registration info is displayed
								   - If not, please uninstall and then reinstall Titanium Backup
								   - Optional: delete this file from your SD card
								  #
								  generation=1
								  keyId=edaf9e1163b4
								  #
								  customerName=Aaron Sollesse
								  customerEmail=aaronsollesse@gmail.com
								  #
								  signature=@@@2d812e6c63b9a99b26062e91e771c125ca7ca7c8bcbc01e7a4b0d5b740dae7060ce718cf42ab63fbc7730a92281298443a7efea454523b7cb553431da446d1724d7502cdb351c8bd727d9326a122d1ddeafb89dace892e287557c814245c0c9ed09c61a4d24200c57bb034b2993bb0bb6f8fcc4e85431ed93ecd8771d95f0dca8bedeab76dd80d37104a933e9fea82acf3231b3291f36df3e12f8fc35fb6eb27ce1861c7d2a1bd881812c440fd118b2f92e66e9655d1fa51ef692d537eed12d92364e438b31b7fbbe826e962b4b86739500a22cc8cab11143eb8787f100d3aa559c82aa4cc971c409264f21f67b0d56b94660efaf6ff6983af2c132fd5127fa0a5d6@@@
								  ```
								- http://matrixrewriter.com/wiki/
								- We hope you will enjoy the unique features of the PRO/Donate version !
								- To get the most out of Titanium Backup, _please_ read all instructions from the Wiki. You can also bookmark the homepage:
								- [http://www.matrixrewriter.com/android/](http://www.matrixrewriter.com/android/)
							- Restore troubleshooting
							  collapsed:: true
								- Stuck on 0%
								  source:: [https://forum.xda-developers.com/showpost.php?s=2c9016bb3219036b13d17233aebd8958&p=71347855&postcount=3](https://forum.xda-developers.com/showpost.php?s=2c9016bb3219036b13d17233aebd8958&p=71347855&postcount=3)
									- In Developer Options on Android disable "Verify apps
									- settings/developer options and look for "verify apps over USB" and tick that off. Now go into titanium backup go into menu/preferences scroll to the very bottom to troubleshooting settings then select app processing mode and then select auto/indirect. Now reboot and titanium backup will restore your apps and data in batches or individually just like before!
					- Related: ((649b13cd-b813-4be7-a002-0163db44c803))
				- Flash additional packages
					- Root phone with Magisk
						- Seee [Magisk](https://workflowy.com/#/baba54354fcf)<a href="https://workflowy.com/#/baba54354fcf"> - AKA Systemless Root/SU</a>
						- Download Magisk from here
						  [https://github.com/topjohnwu/Magisk/releases](https://github.com/topjohnwu/Magisk/releases)
					- F-Droid Privileged Extension
				- Setup ((649b13ce-c4a3-4f27-87fb-25442ce2a9a0)), Syncthing, FolderSync, EteSync, andOTP
			- Backups
			  id:: 649b13cd-b813-4be7-a002-0163db44c803
			  collapsed:: true
				- [[2024-11-05 Tuesday]] My system ((6318fc64-68b1-45e2-a20d-c92068e956af)) doesn't work well for upgrading from a 6-year old LineageOS device to 1-year old GrapheneOS device
				  id:: 6729e516-4f9c-4e62-8693-b8aa0a1e9f03
					- ((649b13cd-7aed-4183-9c8c-ebc8ed613b4b)) and ((63216f53-22cf-428a-9193-e5a423158e2b)) are root-only so can't be used on GrapheneOS
					- ((6318fc65-99f9-4edb-a705-eb1deb420890)) I'm using a version with a buggy
					- Related: ((649b13cd-71ac-45d5-8723-269f9c7cb15c)) : ((6729eac8-2eba-48ae-b76e-1ed1a024b3f3))
				- Syncing
				  collapsed:: true
					- _Backup phone_
					  collapsed:: true
						- Check other backup functionality has been working correctly
							- EteSync for calendar, contacts and tasks
							- [[Software]] : [Syncthing](((6312a076-d503-40c4-b98f-cbdef17b1fcb))) for files
							- FolderSync for Titanium backups to AWS
						- Make backups of other data
							- AFWall export (_See_ [AFWall](https://workflowy.com/#/e5f2eed18186))
							  Stored in /afwall/ on Android
							- andOTP (possibly covered by Titanium)
						- Copy a filesystem backup of phone home directory to hard drive
							- Note: Won't be able to copy over the "Android" folder as that includes lots of app-specific data
						- Make a Titanium backup and copy these files to hard drive
						- **----CURRENT PROGRESS----**
						- Make a nandroid backup and copy these files to hard drive
						  _See_ [Make a Nandroid backup using TWRP](https://workflowy.com/#/31c655f91cbe)
						- ((649b13cd-b813-4be7-a002-0163db44c803))
						- See Pixel guides
						  [Guide/How-to](https://workflowy.com/#/8640753b6383)
					- Dropsync (Dropbox)
					- FolderSync (many services, AWS, FTP, WebDav)
				- it's remarkable how much data your Google account holds on its own
				  collapsed:: true
					- Google Calendar settings
					- Wi-Fi networks & passwords
					- Home screen wallpapers
					- Gmail settings
					- Apps installed through Google Play (backed up on the Play Store app)
					- Display settings (Brightness & Sleep)
					- Language & Input settings
					- Date & Time
					- Third-party app settings & data (varies by app)
					- contacts (via Google Contacts), saved SMS messages (especially if you're using Hangouts for SMS and IM), and more.
					- There are still some things your Google account won't save, however. Recent calls, saved photos and video (which is why camera backup via Google+ Photos or Dropbox is a good idea), downloaded files, and locally saved music are all things you'll need to make sure you move on your own, either via cloud storage like Dropbox or Google Drive, or using a different backup tool, discussed below.
				- If rooted
				  collapsed:: true
					- Nandroid backups (clone) - **monthly**
					  [Make a ](https://workflowy.com/#/8c6d4da2dd2a)<a href="https://workflowy.com/#/8c6d4da2dd2a">nandroid</a><a href="https://workflowy.com/#/8c6d4da2dd2a"> backup and copy these files to hard drive</a>
				- ((6318fc65-99f9-4edb-a705-eb1deb420890))
				- ((649b13cd-4504-4d24-8dc2-d589cedd0eea))
				- andOTP - only in-app backup works, not Titanium Backup because the encryption key is separate from the app data
				- SMS messages, recent calls
				- Personal dictionary for keyboard ie Action: Work etc calendar lifelogging
				- Related: ((6318fc64-68b1-45e2-a20d-c92068e956af))
			- Rooting
			  id:: 63209284-e6f8-47bd-a47c-e2733cf7b886
			  collapsed:: true
				- Pros/Cons
				  collapsed:: true
					- Pros
						- _Privacy enhancements _
						  collapsed:: true
							- Hidden permissions control via [XPrivacyLua](https://workflowy.com/#/2f1156481e5a) or Permissions Manager X
								- _See_ [XPrivacyLua](https://workflowy.com/#/2f1156481e5a) - however it does cause a security vulnerability by requiring Xposed
							- MaxLock on all important apps
						- _Some security enhancements can be changed via rooting_
						- _Quality of life enhancements_
							- Required for installing Google Camera libraries (if not installing GApps)
								- See [Google Camera](https://workflowy.com/#/819ac3cc5131)
								- This works fine on lineageos without any google packages installed.
							- Power App- Allows you to reboot, boot into recovery, or the bootloader
							- Performance tuning apps for battery e.g. ((649b13cd-9391-4867-970e-2e4f2a1e6f01)) , CPU overclocking
							- Emoji Switcher app
							- F-Droid and Aurora Store background app updates
						- Unsorted
						  collapsed:: true
							- _There are alternatives_
								- AFWall - internet permission can be blocked in many ROMs e.g. LineageOS
								- Bouncer - only needed for removing Phone/Contacts/Storage permissions currently
								- F-Droid Privileged Extension
								  collapsed:: true
									- See [Android 12 will let alternative app stores do automatic updates](https://workflowy.com/#/c58f30ca1278)
								- OAndBackupX - [SeedVault](https://workflowy.com/#/96a59c2e3b71) is a partial alternative
								  collapsed:: true
									- App backup
										- Titanium Backup is more private and restores more data than Google's backup can. However a non-root solution Seed Vault is decent already
											- _See_ [Titanium](https://workflowy.com/#/15c43e198c80)<a href="https://workflowy.com/#/15c43e198c80"> Backup</a>
												- It’s so much more flexible than backing up /data, because you can transfer your apps+data into a totally different ROM, like Cyanogenmod.
												- http://lifehacker.com/5784857/how-to-set-up-a-fully-automated-app-and-settings-backup-on-android
												- If you buy the pro app (e.g. through Google Play website) and write an email to the developer, they send you a text-file license to enable "pro" without needing Google Play ~~Shit~~ Services. I did it myself.
								- EDS (Magisk module) - can work without root?
								- See [Axet's ](https://workflowy.com/#/4f69e834aaac)<a href="https://workflowy.com/#/4f69e834aaac">Call</a><a href="https://workflowy.com/#/4f69e834aaac"> </a><a href="https://workflowy.com/#/4f69e834aaac">Record</a><a href="https://workflowy.com/#/4f69e834aaac">er (Magisk module)</a>
							- _A-Z _
								- AdAway - alternative is to set the DNS servers eg NextDNS?
								- Amaze File Manager
								- App Manager
								- Package Manager
								- SuperFreezZ
								- ((63ff8189-440c-460c-904e-72d2227e81fc))
								- Wrong PIN Shutdown
							- See [Advanced Charging Controller (ACC) - Magisk module](https://workflowy.com/#/decf53f0a2b1)
					- Cons
						- MagiskHide is being abandoned, plus hardware attestation in the future will make rooting near-impossible
						  source:: [https://teddit.net/r/Android/comments/nej1vx/magisk_developer_topjohnwu_leaves_apple_to_join/gykkh1e/#c](https://teddit.net/r/Android/comments/nej1vx/magisk_developer_topjohnwu_leaves_apple_to_join/gykkh1e/#c)
						- _See_ [Sudo/root access is an insecure alternative for a proper API respecting the principle of least privilege.](https://workflowy.com/#/e343cd1d9464)
						- Rooting makes your phone less secure
						  collapsed:: true
							- Better security, and thus privacy
							- GrapheneOS is better security model
						- Has caused time-wasting issues
						  collapsed:: true
							- Spent >1 day trying to fix bootloops caused by flashing Magisk
							  See* [Trying to flash TWRP and Magisk each caused phone to bootloop](https://workflowy.com/#/317eced8833d)*
						- Incompatible with verified boot
						- ((63209285-2e05-40f2-bce9-5b8d813eea86)) is a good alternative
					- _Unclear_
						- Many improvements can be gained through simply flashing a custom ROM
							- _See_ [Android-based ROMs](https://workflowy.com/#/669830808624)
							- Firewall
							  collapsed:: true
								- Root - AFWall[AFWall](https://workflowy.com/#/e5f2eed18186)
								- _Firewall functionality without root_
									- LineageOS native firewall
										- it's also using iptables like [AFWall](https://workflowy.com/#/e5f2eed18186) but does not need root nor run in the background.
										- Has to be done per-app
											- Hold-click app to open App Info
											- > Mobile data & WI-FI
											- Uncheck "Allow network access"
									- GrapheneOS has Network as a per-app permission
									- ((649b13cf-caf2-4248-adbb-6e642bd536d9)) - however requires being used as a VPN service. GrapheneOS has criticisms of this app
								- Checking data usage
									- In Android settings search for "Mobile data usage" or "App data usage"
							- F-Droid Privileged Extension
							  collapsed:: true
								- https://f-droid.org/en/packages/org.fdroid.fdroid.privileged.ota/
								- This allows background downloading and installing of updates
								- It didn't work to flash through FlashFire for me, had to boot into TWRP recovery (Dec 2017)
							- Aurora Services
							  collapsed:: true
								- Fork of (see [F-Droid Privileged Extension)](https://workflowy.com/#/1b3f44562f33)
								-
						- Many improvements can be gained through simply flashing or adb
							- Replace GCM with ((649b13d2-f7fb-449f-808b-d819f81d3094))
						- _Potentially defunct functionality_
							- Block ads via hosts file
							  collapsed:: true
								- Impact on Google Spying: limited
								- Impact on App Spying: limited
								- (NOTE: I've never actually done this, so feel free to correct me if I'm wrong)
								- A hosts file is a special file that lets you override what a domain name (eg "ads.google.com") resolves to. In plain english: it lets you prevent EVERY app on the system from connecting to some domains. You can download ready-made hosts files maintained by people who collaborate to build a giant list of sites to block.
								- Pros:
									- Tried and true method of blocking ads and malicious websites
								- Cons:
									- AFAIK no existing hosts files are designed to help with Android privacy, they're meant to block general-purpose ad networks. Google's servers that are not explicitly ad-related, such as Google's Mothership or whatever they call the Creep Central server, won't be blocked.
									- Does nothing if Google or normal apps report to an IP address rather than a domain name
									- Can't allow some apps to connect, and others not: it's block everyone or no one
									- Requires root due to needing to modify a system file
							- Remove bloatware - stock system apps
							  collapsed:: true
								- _See_ [Titanium](https://workflowy.com/#/15c43e198c80)<a href="https://workflowy.com/#/15c43e198c80"> Backup</a>
									- Freeze them first to make sure your phone operates normally without them, then delete them completely to free up that space. You'll be glad you did.
									- See Cyanogenmod Barebones list
										- https://web.archive.org/web/20121031034502/http://wiki.cyanogenmod.com:80/index.php?title=Barebones
										- Also saved as a picture to T drive - Rooted
									- Hate Facebook/Instagram/Evernote? Want to get rid of those stock apps? They’re in /data/data.
								- with System App Remover
							- Convert apps to System Apps for enhanced security
							- AdAway (F-Droid)
							  Remove ads in free apps and websites
					- _Conclusion_
						- Sat, Nov 21, 2020 - Stick with rooting until LineageOS 18, then test if Seedvault is a good alternative
						  id:: 644c0acc-db71-48fd-a5f6-0336e6b28f70
				- Terminology and overview
				  collapsed:: true
					- Partitions and system levels
					  collapsed:: true
						- Android phones have 3 system levels:
							- system
							- recovery
							  collapsed:: true
								- You have to flash a custom recovery, and you don't need one to root. All phones have a "stock" recovery. A custom one would be like CWM/ClockWorkMod, or TWRP/TeamWinRecoveryProject.
							- bootloader
							  collapsed:: true
								- An unlocked bootloader is what it takes to install custom ROM's like CyanogenMod and AOKP.
									- A locked bootloader is Android's gate to make sure no one accidentally obtains root, or can do anything else dangerous. On Nexus devices, unlocking the bootloader is as easy as typing in 3 words and hitting enter. It's made to be easy on purpose, because Google believes in giving you the choice to modify your phone if you so choose. Other manufacturers (Ahem, Samsung) want to control the experience for you. They make it difficult, but not impossible, to unlock the bootloader.
									- Unlocking your bootloader is also safe. Some manufacturers like HTC and Sony give you all the tools to do it yourself.
									- The only downside to unlocking the bootloader is a voided warranty. If you don't want to void your warranty, don't unlock your bootloader. I personally, and tons of other Android users have returned devices with unlocked bootloaders successfully, but your results may vary. If you don't want to risk it, don't.
								- the bootloader is unlocked you don't need an exploit, you can just flash su/Superuser.apk in a custom recovery
								- You do not, repeat DO NOT need root to flash a custom ROM.
									- Unlock bootloader, flash custom recovery, flash ROM. Stop there if you don't want or need superuser permissions.
								- download mode, odin or fastboot
						- Each level can modify the level above it.
							- So in order to modify system, you need to first make recovery do your bidding.
							- And to do that, you need to unlock the bootloader.
						- In Android phones, internal storage is split up into partitions:
						  id:: 6318fc64-0a33-4133-9f0d-ec0fc1a46d62
							- `/boot/` contains the Linux kernel and ramdisk. SuperSU and no-dm-verity will patch the files here.
							  collapsed:: true
								- 4. /boot - This is the partition that enables the phone to boot. It includes the kernel and the ramdisk. Wiping this will also turn your phone into a $600 paper weight, but with the ROM on it. Again, MAY be fixed by flashing.
							- `/system/` Android OS
							  id:: 6318fc64-5c92-4685-bd8e-2939200a1c95
								- `/system/app/` -
								- `/system/priv-app/` - This is related to Android permissions. Most permissions are categorized as normal, dangerous or system. Normal permissions are granted automatically, without prompting the user. For example, the permission to connect to the Internet. Dangerous permissions are only granted after asking the user. For example, the permission to read your calendar. System permissions are even more dangerous, so they are only granted to apps installed by the manufacturer under the folder /system/priv-app. Apps installed by the manufacturer, but that do not require these extra-dangerous permissions are installed under /system/app.
								- All ROM data, no UserData, wiping this will turn your phone into a $600 paper weight. Don’t worry, it’s not permanent, you can always flash a ROM/ Restore via some Official utility (RUUs for HTC, Odin for Samsung, etc) to fix it up.
							- `/data/` Here resides your personal data, apps and settings are installed here. A factory reset just wipes this partition.
							  id:: 6318fc64-080f-48d1-bc10-7d40a08c43bf
								- `/data/app` - user apps stored here. The 'Android Package' installation files (APKs) in /data/app/ which consist of a base.apk and optional Split APKs that contain language/device/feature based resources of the app.
								- `/data/data/` or `/data/user/*/` - stores private app data including your app preferences, login info, databases, etc
								  id:: 632170c7-2b8c-4f6e-a75a-7d37397093cf
							- `/recovery/` recovery system goes here. We will flash TWRP onto it.
							  collapsed:: true
								- 5. /recovery - There is a stock Recovery in every device, but it does’t allow you to flash custom ROMs or do other stuff that Custom Recoveries allow you to do. This partition, usually booted by a combination of keys (For Example: VolUp + Power), can save your device if you do something stupid, even if you wipe /boot.
							- `/cache/` amongst other uses, LG’s Software Update downloads OTAs here.
							  collapsed:: true
								- Stores temporary files creates by the OS.
							- `Dalvik-cache` - Not a partition, however important. Android apps run on a Virtual Machine called the Dalvik Virtual Machine. The Dalvik cache stores the temporary files for apps. When Android is “Optimizing Apps” after booting up, It’s actually creating files in the dalvik cache so apps run better.
							- `/Android/`
								- `/Android/data/` - External Data i.e. stored on the internal storage or SD Card, external data may contain media files, downloaded game resources, ad resources, etc. Some apps/games may store ‘Data’ here.
								- `/Android/obb/` - Expansion i.e. Some games and apps have large .obb files which contain a huge number of resources. These .obb files are called expansions and can be found in Android/obb/ on the internal storage or SD Card.
								- `/Android/media/`- Media i.e. Very few apps use this directory. Among the popular apps, WhatsApp uses this directory on Android 11 and up to store all your media files.
					- Unlock bootloader to use fastboot on command line and flash recovery. Flash the SuperSu zip once in recovery eg TWRP
					- Magisk-in-Zygote (Zygisk)
					  collapsed:: true
						- close resemblance to Riru
						- Riru is used for LSPosed
				- How to Root
				  collapsed:: true
					- Choose rooted/Xposed/Magisk method
						- _TL;DR_
							- Flash SuperSU via TWRP recovery
							- Install FlashFire app (or just go back into TWRP recovery)
							- Install Magisk Manager to install Magisk
							- Download Magisk module for Xposed
						- [Magisk](https://github.com/topjohnwu/Magisk)
						  id:: 649b13cd-e6ad-4655-91b6-5dcdce92aaed
						  collapsed:: true
						  AKA Systemless Root/SU
							- Pros/Cons
							  collapsed:: true
								- Pros/Cons
								  collapsed:: true
									- As with anything, there are advantages and disadvantages to gaining root access with the systemless method. The primary downside is that it doesn’t work on devices with locked bootloaders by default—there may be workarounds, but they’re very specific to each device. In other words, if there is no workaround for your device and it has a locked bootloader, there’s essentially no way of gaining root access.
									- Other than that, however, the systemless method is generally better. For example, it’s much easier to accept over-the-air (OTA) updates when you’re rooted using this method, especially when using a tool like FlashFire. FlashFire can flash stock firmwares and re-root them while flashing, as well as handle OTA installation (again, re-rooting it while flashing). Basically, if you’re running a rooted device, FlashFire is a good tool to have. Keep in mind that it’s currently still in beta, but development is making good progress.
									- The systemless root method is also much cleaner, since it doesn’t add or modify files in the /system partition. That means it’s much easier to unroot your phone, too. It doesn’t even survive a factory reset, so it’s much simpler to make sure devices are unrooted and wiped clean before selling them.
									- Of course, that last bit is a double-edged sword, as some users would prefer to stay rooted after factory resetting their device—the good news is that you need only re-flash the appropriate SuperSU file to re-gain root access, which is easy. And if you want to unroot without performing a factory reset, you can just flash a clean boot image for your device. One command prompt command and you’re done.
									- It’s also worth noting that there are certain services, like Android Pay, that simply won’t work on rooted devices. At one point, Pay did work on systemless devices, but this was completely accidental. There are currently no plans to try and bypass Pay’s protection on rooted devices.
								- Pros
									- Open-source
								- Cons
									- v23 was the last version with MagiskHide since the maintainer got employed by Google
									  source:: [https://www.xda-developers.com/magisk-development-continues-without-magiskhide/](https://www.xda-developers.com/magisk-development-continues-without-magiskhide/)
										- Downloaded
										  /home/boss/Documents/OPTIONAL/Android/Magisk/Magisk-v23.0.apk
								- modules like [MagiskHide Props Config](https://forum.xda-developers.com/t/module-magiskhide-props-config-safetynet-prop-edits-and-more-v5-4-0.3789228/) to spoof the CTS profile to pass basic attestation, as long as the method in question relies on a valid combination of device and modelmnames, build fingerprints, and security patch levels, there’s nommguarantee that the root hiding trick will remain useful in the future.mThis is due to the fact that Google Play Services is starting to usemhardware attestation for CTS profile validation in many cases, even when basic attestation is selected.
							- Documentation
								- History
								  collapsed:: true
									- _Background_
										- History
											- Systemless root by Chainfire allowed users to get root access without modifying the system partition, allowing uninterrupted installation for OTA updates even when the device is rooted.
											- Now come to August 2016, and we’ve an entire interface built upon systemless principles which is aimed to make custom MOD (even ROMs) available for Android device to go systemless. This new systemless interface is developed by topjohnwu over at xda and is being called Magisk — The Universal Systemless Interface.
										- Magisk - The Universal Systemless Interface - overview
											- Magisk is a systemless interface that developers can use to build custom MODs for Android devices without altering the system files.
											- Magisk modifies boot image and add files to /data and /cache
											- It touches your /system partition only if root installed in /system is detected!
										- https://forum.xda-developers.com/apps/magisk/official-magisk-v7-universal-systemless-t3473445
									- Systemless root by Chainfire allowed users to get root access without modifying the system partition, allowing uninterrupted installation for OTA updates even when the device is rooted.
									- This is now the typical method from Marshmallow onwards
									- https://www.howtogeek.com/249162/what-is-systemless-root-on-android-and-why-is-it-better/
								- v24+ - Some features deprecated, now in separate apps
								  collapsed:: true
									- Magisk Modules deprecated
										- Fox's Magisk Module Manager
											- [https://github.com/Fox2Code/FoxMagiskModuleManag](https://github.com/Fox2Code/FoxMagiskModuleManager/issues/41)er
									- MagiskHide deprecated (root hiding)
										- Basic root hiding - Zygisk + DenyList
										  id:: 63209284-7330-41b6-b2f6-d02a88acfff9
											- First you need to enable setting to run parts of Magisk in the Android system process zygote, called Zygisk!Go to: Magisk -> Settings -> **Zygisk (Beta)**
											- While there, also enable **Enforce DenyList** setting. After that, tap on **Configure DenyList**.
											- In the DenyList, enable (add to the DenyList) all the apps that are not playing with Magisk and/or root, including apps such as **SafetyNet Helper Sample** or **RootBeer**. (You want the tests to run from the perspective of how hidden apps will see Magisk)
												- _Note, that since modules now have the ability to hook into apps by utilizing Zygisk, apps in the DenyList cannot be affected by any Magisk Module through modifications in the zygote process._
										- Passing ((649b13d2-3bf6-43ed-b52c-7bbcf094ca3c))and other advanced root detection
										  collapsed:: true
											- Apps
												- [https://github.com/kdrag0n/safetynet-fix](https://github.com/kdrag0n/safetynet-fix)
												- [https://github.com/Magisk-Modules-Repo/MagiskHidePropsConf](https://github.com/Magisk-Modules-Repo/MagiskHidePropsConf)
												- ((649b13cd-1a22-4a7b-b86c-ce017052e6f1))
											- Next, you'll need to install kdrag0n's Universal SafetyNet Fix module, ideally [**the latest version**](<[https://github.com/kdrag0n/safetynet-fix/releases/latest](https://github.com/kdrag0n/safetynet-fix/releases/latest)>). (The riru version is discontinued since v2.1.3)
											- **Now perform a reboot. After bootup, test how the root/Magisk-sensitive applications behave. You may need to clear their data or even reinstall them altogether. It is also a good idea to clear cache and DATA of the** **_Play services_** **and** **\*Play store\*\*\***. If everything's in order, you are finished!\*\*
											- If some apps still detect root, perhaps you can try to use [**the MagiskHide Props Config**](https://github.com/Magisk-Modules-Repo/MagiskHidePropsConf/releases/latest) module to spoof other devices' build configuration. This requires a few tries to get the right device fingerprint spoofed.
											- Download the latest release and install the module. Finish the installation by rebooting the phone.
											- Now it's time for a disclaimer:
											- > This module changes your devices prop values. Fingerprint, model and whatever prop you want (depending on what options you use). This may have consequences (everything in life does, live with it). Your device might be perceived as a different device (which can create issues with the Play Store, YouTube video resolution, OTA updates, etc) and cause system instabilities and even bootloops.Read through the [documentation](https://github.com/Magisk-Modules-Repo/MagiskHidePropsConf/blob/master/README.md#issues-support-etc) to find more details and how to fix your device if things go south.
											- Install a Terminal emulator app - if you don't have any yet. Open it, and run the command props or alternatively su -c 'props' ( ((649b13ce-0b9e-4741-ba6d-7959858e3443)) )
											- **From herein,** [**please continue here...**](<[https://github.com/Magisk-Modules-Repo/MagiskHidePropsConf/blob/master/README.md#usage](https://github.com/Magisk-Modules-Repo/MagiskHidePropsConf/blob/master/README.md#usage)>)
									- [https://forum.xda-developers.com/t/magisk-general-support-discussion.3432382/](https://forum.xda-developers.com/t/magisk-general-support-discussion.3432382/)
									- [https://forum.xda-developers.com/t/discussion-magisk-the-age-of-zygisk.4393877/](https://forum.xda-developers.com/t/discussion-magisk-the-age-of-zygisk.4393877/)
									-
								- https://www.supersuroot.com/
								- System Partitions
								  collapsed:: true
									- Chainfire has released SuperSU Beta as an experimental version. Still SuperSU root has various bugs such as, when factory resetting the device will remove the root. That is the major issue of SuperSU root this moment. Chainfire has mentioned about this issue,
									- “To have root on modern Android versions, we need our files to be executable and our daemon to be started on boot. We normally do this by making modifications to /system, tapping into binaries and scripts executed by init. If we’re also modifying the boot image, then we should be able to do all this without modifying system at all. A benefit of this is that it makes OTAs easier - reflashing the boot image is less hassle than reflashing system.”
								- Benefits of SuperSU Systemless Root
								  collapsed:: true
									- 1.  Easy to unroot
									- 2.  A clean design & approach
									- 3.  A clean system partition
									- 4.  Excludes unnecessary things, which are not essential on Android 6.0 Marshmallow
									- 5.  Easier OTA’s because of reflashing boot image
									- 6.  Most importantly, if you do not have correct compatible kernel installation, SuperSU does not soft brick your device.
								- https://forum.xda-developers.com/apps/supersu/2014-09-02-supersu-v2-05-t2868133
								- https://forum.xda-developers.com/moto-g4-plus/how-to/root-systemless-rooting-supersu-2-74-2-t3405772
								- How to remove
								  collapsed:: true
									- https://forum.xda-developers.com/showpost.php?p=63816659&postcount=2769
									- https://forum.xda-developers.com/apps/supersu/unroot-systemless-root-t3249542
								- How to Install
								  collapsed:: true
									- Get latest from here
									  [https://github.com/topjohnwu/Magisk/releases](https://github.com/topjohnwu/Magisk/releases)
										- [https://forum.xda-developers.com/apps/magisk/official-magisk-v7-universal-systemless-t3473445](https://forum.xda-developers.com/apps/magisk/official-magisk-v7-universal-systemless-t3473445)
									- _Either_
										- Flash ZIP via custom recovery e.g. TWRP
										- OR
										- Flash via LineageOS recovery
											- Plug USB into phone
											- Turn on USB debugging if not already enabled
											- Reboot in recovery
											  adb reboot recovery
											- _In LineageOS Recovery_
												- Apply update > Apply from ADB
												- In terminal
												  adb sideload /home/boss/Downloads/Magisk-v25.0.apk
												- Reboot
								- Systemless Xposed
								  collapsed:: true
									- Many times I wanted to accept OTAs on my phone, but I have to restore the system in order to make it install.
									- Sometimes I don't want to install custom roms on my devices, I just want to root and get Xposed rockin.
									- I always wanted to have systemless Xposed since systemless SuperSU is available, and now I have done it by myself
									- https://forum.xda-developers.com/xposed/unofficial-systemless-xposed-t3388268
										- Download the latest version of Material Design Xposed Installer apk
											- Don't use this installer though or you'll get system version?
										- Download and install Xposed Framework SDK 23: Android 6.0 via Magisk Manager's Download Section
									- https://www.howtogeek.com/263663/how-to-install-the-new-systemless-xposed-framework-for-frustration-free-android-customization/
									- 1 Backlink
										- _See_ [Systemless Xposed](https://workflowy.com/#/637dd6904e5b)
							- Magisk modules
							  id:: 6516669f-1bb2-4355-90e0-2fe32a948d2e
							  Last update: [[2023-09-29 Friday]]
								- [Axet's Call Recorder](https://github.com/Magisk-Modules-Repo/callrecorder-axet)
								  id:: 649b13cd-8852-439e-a129-e1a0494647b3
								  collapsed:: true
									- https://github.com/di72nn/callrecorder-axet
								- [Basic Call Recorder](https://github.com/chenxiaolong/BCR)
								- [Google Glide Typing library](https://github.com/akaessens/magisk_google_glide_lib)
								- [Shamiko](https://github.com/LSPosed/LSPosed.github.io)
								  id:: 649b13cd-1a22-4a7b-b86c-ce017052e6f1
								  collapsed:: true
									- Pros
										- Unlike [Magisk's DenyList](<((63209284-7330-41b6-b2f6-d02a88acfff9))>), this aids compatibility with ((63218542-c020-4f75-9c0e-7e6c9f4b093b)). Otherwise SI can't enforce on those DenyList apps
									- Basically the new MagiskHide.
									- Documentation
										- Install ZIP via Magisk modules page
										- Use Magisk > Settings > Configure DenyList to add apps to be hidden
									- Apps to hide Magisk from
										- Barclays
										- LoLegacy
										- Revolut
									- Is there a repo or just a Telegram link
								- [Storage Isolation Enhanced](https://github.com/RikkaApps/StorageRedirect-assets)
								  id:: 63219e34-77c4-47fe-985b-29a582113b0e
								  collapsed:: true
								  AKA Zygisk - Enhanced mode for ((63218542-c020-4f75-9c0e-7e6c9f4b093b))
									- Pros/Cons
										- Cons
											- Limited utility long-term since most apps already use ((63219e37-0f66-4883-878d-3f5f173af6b7))
											-
									- Magisk module for ((63218542-c020-4f75-9c0e-7e6c9f4b093b))
									  id:: 632192de-65f7-488a-b6a6-f089b2225c0c
									- Enhanced mode provides the following features:
										- No longer relying on logcat to detect app process creation
											- Avoid the problem that the app will not be isolated for a short period of time due to the possible delay of the log
											- Avoid the problem that the log is disable (e.g., Huawei EMUI disable log on boot)
										- Start on boot
											- Avoid the problem that custom systems block start on boot (including but not limited to MIUI)
										- Block system remount
											- Avoid remount triggered by the behavior of custom systems making the isolation invalid (e.g., MIUI 11)
										- Record file access behavior for apps
										- Modify the behavior of MediaProvider and DownloadManger to prevent apps to read/write unaccessiable folders through them
							- _Alternatives to Magisk_
								- SuperUser
								  collapsed:: true
									- https://github.com/seSuperuser/super-bootimg
									- https://github.com/phhusson/Superuser
									- https://github.com/phhusson/Superuser/issues/63
								- SuperSU (Chainfire)
								  collapsed:: true
									- Closed-source
									- Per-app configuration
									- Temporary/complete unroot
								- Comparison - SuperSU has more features?
								- [source] https://android.stackexchange.com/a/44509
							- Usecases
							  collapsed:: true
								- Advanced Charging Controller (ACC)
								  id:: 649b13cd-9391-4867-970e-2e4f2a1e6f01
								  [https://github.com/Magisk-Modules-Repo/acc](https://github.com/Magisk-Modules-Repo/acc)
						- Xposed (everything)
						  collapsed:: true
							- Pros/Cons
							  collapsed:: true
								- Pros
									- See [XPrivacyLua](https://workflowy.com/#/2f1156481e5a)
									  #Phone
								- Cons
									- Not yet available for Android 9/P even
									  collapsed:: true
									  [Xposed Framework not yet available for it (Not yet available for Android 9/P even)](https://workflowy.com/#/49e06110eafe)
										- Xposed Framework not yet available for it
										  https://forum.xda-developers.com/xposed
											- EXposed
												- From VXposed developer, this app runs on system instead of in virtual sspace
												- Repo
												  https://github.com/tiann/exposed
												- Mostly in Chinese, it could see my Xposed modules on device but couldn't activate them
										- 1 Backlink
											- Xposed Framework not yet available for it ([Not yet available for Android 9/P even](https://workflowy.com/#/454437d08808))
							- Xposed Framework
							  collapsed:: true
								- [LSPosed](https://github.com/LSPosed/LSPosed) - EdXposed fork, and Magisk (Zygisk) module
								- Current FOSS iteration: EdXposed
								  collapsed:: true
								  [https://github.com/ElderDrivers/EdXposed](https://github.com/ElderDrivers/EdXposed)
									- **Easy recovered.** Based on Magisk, just disable EdXposed in Magisk Manager, you can recover from brick.
								- VirtualXposed - basically a virtual machine as a APK
								  collapsed:: true
									- Cons
										- It's like Android for Work - apps must be installed in this virtual space to be affected by the Xposed modules like XPrivacyLua
									- Links
										- https://vxposed.com/
										- Thread
										  https://forum.xda-developers.com/xposed/virtualxposed-xposed-root-unlock-t3760313
										- Repo
										  https://github.com/android-hacker/VirtualXposed
									- Here's how VirtualXposed works
										- All apps run inside VirtualApp (https://github.com/asLody/VirtualApp) - This is library wraps around some android system calls to allows to run apks as plugins inside the original app. The concept seems viable, and the source code seems fine to me. The project is also mostly open-source project, with over 4200 stars on Github. (Its not free for commercial use though, that requires the purchase of a license.)
										- It seems to use Epic (https://github.com/tiann/epic) to actually process xposed hooks - This is an open-source library, actually inspired from xposed itself, for developer to "hook" into their own apps. The concept is legit, source code seems fine, 600 stars on github.
										- VirtualXposed is essentially a launcher which wraps around the above two libraries, allowing you to install apps into the launcher which run under VirtualApp, and which are hooked using Epic. VirtualXposed itself has over 4000 stars on Github, has a very-logical looking commit history, and seems clean to me.
							- See [Magisk](https://workflowy.com/#/baba54354fcf)
							- Xposed modules
							  collapsed:: true
								- [https://repo.xposed.info/module-overview](https://repo.xposed.info/module-overview)
								- Examples 1
								  collapsed:: true
									- Xposed, more specifically MinMinGuard, AdAway and YouTube AdAway.
									- XBlast Tools is useful for making the Quick Settings buttons smaller. They don't need to be so big so I can fit all of them on one screen. No more need for a notifications quick bar using Power Toggles or whatever.
									- Notification Mod allows for interacting with the status bar while the lockscreen is up. Normally this isn't allowed since you can do some things through it such as Quick Settings or also possibly Quick Reply to SMS (never tried it while locked) but I find it convenient,
									- Super useful tweaks - disabling the 'safe headset volume', hosts blocking, privacy management, gravitybox.
									- Not-completely-necessary tweaks, but I wouldn't do without them - tinted statusbar, statusbar volume, swipeback.
									- Xposed minminguard takes care of the blank spaces caused by AdAway, removes adds + the boxes those adds used. Together with adaway this is a amazing :)
									- App Settings: lets me modify settings of specific apps such as the DPI or forcing fullscreen.
									- VpnDialog: loads my VPN on boot without asking if I'm sure I want to trust the connection
									- Xprivacy: intercepts and alters permissions for apps. An example would be telling Facebook I am located in x when I am really at y location.
									- Xposed Additions: lets me modify and remap buttons including to tasker actions.
									- GravityBox: lets you get some custom ROM features on top of stock Android. Way too many tweaks to list here.
								- Examples 2
								  collapsed:: true
									- Installer
										- http://repo.xposed.info/module/de.robv.android.xposed.installer
									- http://lifehacker.com/how-to-create-your-own-customized-version-of-android-wi-1440101209
									- http://lifehacker.com/gravitybox-adds-a-ton-of-tweaks-to-android-in-one-custo-1502250290
									- http://hackerspace.lifehacker.com/xposed-module-roundup-android-requires-root-1624858563/1638309690/+whitsongordon
									- http://lifehacker.com/playpermissionsexposed-reveals-changes-to-android-permi-1679206905
									- https://www.reddit.com/r/xposed/
							- _See_ [Systemless Xposed](https://workflowy.com/#/637dd6904e5b)
							- https://forum.xda-developers.com/showthread.php?t=3034811
						- [Shizuku](<((63209285-2e05-40f2-bce9-5b8d813eea86))>)
						- Sui
						  id:: 63217e1a-be03-48a4-8736-748f53ce30a4
						  collapsed:: true
							- Pros
								- Hidden app manager
								  collapsed:: true
									- (Android 8.0+, Sui 12.1+) Long press system settings from the home app, you will find the shortcut of Sui
									- (Android 8.0+, Sui 12+) Enter "Developer options" in system settings, the system will ask you to add the shortcut of Sui
									- Enter `*#*#784784#*#*` in the default dialer app
							- Magisk module made by creators of ((63209285-2e05-40f2-bce9-5b8d813eea86)). Intended to replace the current Shizuku app
						- [KernelSU](https://kernelsu.org/)
						  id:: 65aaeb34-ba89-4dae-86ba-1cbb903f8d37
						  collapsed:: true
						  2024 solution that's much harder to detect | Supports kernel 5.10+ officially, 4.14+ can be done with manual building
							- Pros/Cons
								- Pros
									-
								- Cons
									-
								- Unclear
								- Upstream/Downstream Pros/Cons
								- Comparisons
									- ((65aaeb34-ba89-4dae-86ba-1cbb903f8d37)) vs ((649b13cd-e6ad-4655-91b6-5dcdce92aaed))
										- For ((65aaeb34-ba89-4dae-86ba-1cbb903f8d37))
											- Harder to detect
										- For ((649b13cd-e6ad-4655-91b6-5dcdce92aaed))
											-
										- Similarities
											-
										- Unclear
											- better compatibility with some older or niche devices but can cause issues with SafetyNet and requires more technical knowledge.
											- KernelSU: Often requires compiling a custom kernel for your device, which can be a complex process. There's no dedicated management app, and configuration can be more involved.
											- Magisk: Generally considered easier to use. It comes with a user-friendly Magisk Manager app for managing root access, installing modules, and hiding from SafetyNet.
											- Magisk: More success reported in bypassing SafetyNet checks due to its systemless approach.
											-
							- https://github.com/tiann/KernelSU
							- https://xdaforums.com/t/kernelsu-kernel-assisted-superuser-for-android-root-shell.3870559/#post-78234762
						- [APatch](https://github.com/bmax121/APatch)
						  collapsed:: true
						  Fork of ((65aaeb34-ba89-4dae-86ba-1cbb903f8d37)), Only supports Android kernel versions 3.18 - 6.1
							- [[2024-09-20 Friday]] ((649b13cc-23ea-4398-8dcb-488f7f9c55e6)) is using kernel v4.9.377
							-
					- 2024 Q1 notes
						- https://xdaforums.com/t/info-play-integrity-api-replacement-for-safetynet.4479337/ what is Play Integrity and how to fix.
						- Gives BASIC integrity using Play Integrity Fix or PlayIntegrityFork https://github.com/osm0sis/PlayIntegrityFork
						- To pass DEVICE you must search for a valid fingerprint and set it into /data/adb/pif.json file. There are tools to help with this like https://github.com/TheFreeman193/PIFS or https://github.com/daboynb/PlayIntegrityNEXT
						- To check integrity:
						- - In Play Store settings tab the About until Developer Options enabled
						- - General settings > Developer Options > check Play Integrity. In the Labels value there can be three items: BASIC INTEGRITY, DEVICE INTEGRITY and STRONG INTEGRITY
					- One-click root methods (for popular smartphones)
					  collapsed:: true
						- •This page contains a massive compilation by Android Central. Majority of the most popular phones can be found here:
						- http://www.androidcentral.com/root
						- One-Click Root methods:
						- •Z4Root:
						- http://z4rootapk.com/
						- •KingoApp:
						- http://www.kingoapp.com/
						- •Super OneClick (and support thread):
						- http://shortfuse.org/?page_id=2
						- http://forum.xda-developers.com/showthread.php?t=803682
					- [avbroot](https://github.com/chenxiaolong/avbroot)
					  id:: 65193e34-8c19-4a3a-9c4b-adba11e09476
					  collapsed:: true
					  Sign (and root) Android A/B OTAs with custom keys while preserving Android Verified Boot
						- Pros/Cons
							- Pros
								- Allows combining custom ROMs like ((63209286-6f40-4063-9fdc-2543251d416e)) with ((63209284-e6f8-47bd-a47c-e2733cf7b886))
							- Cons
								- Prevents OTA updates, they ,ust be sideloaded. Unless using [Custota](https://github.com/chenxiaolong/Custota) to utilise a custom OTA server
							- Unclear
							- Comparisons
					- Rooting via installation file
					  collapsed:: true
						- In most cases we look for the installation file (Google), load it up on the SD card and install it through recovery mode. Whatever you do, first make sure you’ve backed up everything you don’t want to lose (just in case). To root your phone this way, you’ll have to search for the installation files yourself. It would be impractical to list out about a thousand links right here. That’s because every single android phone is just a little bit different. So, the (rooted or unrooted) android OS from Samsung’s S4 may not work exactly right on HTC one. There are subtle differences in the way each phone works and that means to be able to root your phone, you will have to look for the specific root installation file for your exact model.
						- Once again, after you’ve googled it out and found a good looking source for the root installation file, all you need to do is put it on the SD card and install it through recovery mode. To enter recovery mode, turn off the phone, leave it for a minute and press the power key + Volume key(s) for a few seconds and you will be booted into recovery mode (This may vary with phone models). It’s kind of like the BIOS menu of a computer. You will then be able to see some weird looking options and this is where you must fight the urge to sniff around. You may not get even a confirmation message on some phones for certain actions. If an important file is messed with by mistake, your phone may be bricked. In the recovery mode, for most phones you can navigate through the options by using volume keys, and ‘select’ an option by pressing power key. You’ll see an option that’s something like “apply update from SD card”. This is where you can install a rooted OS from the file you downloaded. You will be taken to the parent directory of your SD card where you can select your (usually a .zip) installation file and again resist the urge to press any button. It usually takes a couple of minutes (up to 5 minutes) and then either the phone will be automatically rebooted or you’ll be back to the main recovery menu where you can reboot yourself. And Voila! Your phone is now rooted and your horizons just expanded.
					- _Device-specific_
					  collapsed:: true
						- LG G5
							- _Unlock bootloader (via LG Developer website + Minimal ADB and Fastboot_
								- Read rest of instructions in HTML in T drive
								- Enable USB Debugging and OEM unlock
									- USB-Debugging is required for the commands “adb” and “fastboot” to work. To enable USB-Debugging, go to Settings >> About phone >> Software info and tap Build number 7 times. Return to the previous screen, select Developer options and enable USB-Debugging.
									- 2.  Enable OEM unlock on your phone. Activating the "Enable OEM unlock" is necessary for the bootloader unlock. To enable OEM unlock, go to Settings >> Developer options and check Enable OEM unlock.
								- Plug in USB between PC and phone
								- Turn on PTP mode
								- Open C:\Program Files (x86)\Minimal ADB and Fastboot\cmd-here.exe (run as admin)
									- adb reboot bootloader
							- _Flash custom recovery (TWRP)_
								- Download TWRP img for phone model at twrp.me
								- Put it on SD card (or can instead just via PC on USB I think)
								- Enable USB Debugging
									- USB-Debugging is required for the commands “adb” and “fastboot” to work. To enable USB-Debugging, go to Settings >> About phone >> Software info and tap Build number 7 times.
									- Return to the previous screen, select Developer options and enable USB-Debugging.
								- Plug in USB between PC and phone
								- Turn on PTP mode
								- Open C:\Program Files (x86)\Minimal ADB and Fastboot\cmd-here.exe (run as admin)
									- adb reboot bootloader
									- fastboot flash recovery twrp-3.1.0-0-h850.img
								- For TWRP to "stick" you must first boot directly into TWRP and not back into Android, until after flashing the SuperSU zip.
									- After flashing TWRP unplug the USB cable and pull the battery. Plug battery back in then boot into recovery which should hopefully load TWRP.
								- To boot into recovery:
									- a. Using 2 hands.. use one hand/finger to press/hold volume down.. and use the other hand for the power button. Press n hold both buttons.
									- b. As soon as you see the LG logo on the screen.. let go of the power button then quickly press it again (never letting go of volume down).
									- c. Keep holding until you see the Factory Reset screen. Click thru the factory reset screens.. Yes.. Yes...
										- **Note: **This appears to be bs, after unrooting then trying to root again clicking Yes on these didn't wipe any data
							- 10. You will not be able to decrypt your internal data while in TWRP (unless performing a full /data wipe in TWRP and you will lose encryption!) but you can manually mount your external SD card to view the SuperSu zip. Feel free to back up first.. but otherwise.. time to install SuperSu. Click the Install button and navigate to the external_sd, select the SuperSu zip then swipe to install. Now you're rooted and TWRP'd! Reboot into system...
						- Samsung Galaxy S5
							- https://forum.xda-developers.com/verizon-galaxy-s5/general/testers-required-easier-root-method-t3561529/post71202995#post71202995
						- Samsung Galaxy Young 2 steps
							- Framaroot - fail
							- towelroot - fail
							- kingoroot - fail
							- iRoot -
						- Xiaomi Pocophone F1
							- LG G5 guide is similar
							  intralink2:: https://workflowy.com/#/3c90798f02ba
							- Download Android tools
							- fastboot flash recovery openrecovery-twrp-2.7.0.0-mako.img
					- Custom ROM Overviews
					  collapsed:: true
						- Android is open-source but most components proprietary
							- WiFi and bluetooth drivers
							- hardware components like GPS chips, cameras and graphics
							- Google Play, Gmail, Google Maps, etc
						- LineageOS (previously CyanogenMod)
							- https://prism-break.org/en/projects/cyanogenmod
							- http://wiki.cyanogenmod.org/w/Main_Page
							- https://wiki.cyanogenmod.org/w/Barebones
							- CyanogenMod Install + other steps to do
							  collapsed:: true
								- How to
									- http://forum.xda-developers.com/galaxy-s5/general/how-to-t3298654
									- how to root
										- #0 - Install Samsung USB Drivers (That should be the first step you ever do, before diving into the world of ROMs and Android Development.)
										- enable OEM Unlock or Rooting will fail!
											- #1 - Settings - About Device - Tap 7 Times on Build Number - Developer Options are now enabled.
											- #2 - Settings - Developer Options - Enable OEM Unlock - Enable USB Debugging.
										- #1 - Run Odin as Administrator
										- Downgrade to one version lower ideally as the newer versions have the most problems
											- www.sammobile.com to find stock firmware
										- Boot a custom Recovery (to allow nandroid backups, rooting and custom ROMs)
											- usually TWRP (Team Win Recovery Project) or CWM (Clockwork Mod) — is separate from your Android OS, and is the place where you can wipe partitions, install ROMs, and make backups.
									- http://forum.xda-developers.com/galaxy-s5/general/rom-debranded-g903fxxu1apa4-stock-rom-t3306727
								- Install NOGAPPS
									- http://forum.xda-developers.com/showthread.php?t=1715375
								- Cell towers GPS
									- http://forum.xda-developers.com/showpost.php?p=49783851&postcount=519
									- Generating the lacells.db as described at XDA, and pushed it to the device
								- Will I still get over-the-air (OTA) updates?
									- Will downloading them break my root? If you root your phone without flashing a custom ROM, then you will likely still get OTA updates from your carrier, and they will break your root. We highly recommend against downloading these updates, since you may not be able to re-root your phone for awhile after updating. Alternatively, you can use an app like OTA Rootkeeper that will help you keep your root access (though it doesn't work with every version of Android).
									- https://play.google.com/store/apps/details?id=org.projectvoodoo.otarootkeeper&hl=en
						- Replicant
						- Copperhead
						- OmniROM
						- Fairphone Open
					- _[Learning Resources]_
					  collapsed:: true
						- https://lifehacker.com/5789397/the-always-up-to-date-guide-to-rooting-any-android-phone
						- http://forum.xda-developers.com
						- http://androidforums.com/
						- http://rootzwiki.com/index
				- _Current rooted apps_ - Wed, Apr 14, 2021
				  id:: 644c0acc-4506-4afb-87dc-4413f76e7079
					- _Magisk rooted_
						- AdAway
						- App Manager
						- [Aurora Store](<((63209285-ef03-44e2-8e84-34e7f088906f))>)
						  id:: 63209284-4a22-4cc1-895f-b0e23a2878d2
						  collapsed:: true
							- May be resolved by: [Android 12 will let alternative app stores do automatic updates](https://beta.workflowy.com/#/c58f30ca1278)
						- [Bouncer](<((63209284-786d-4fa2-93a0-95447391e1cc))>)
						- EDS
						  id:: 63209284-e089-4dbc-8f4b-939568e30e4a
						- Fox's Magisk Module Manager
						- ((63219e35-8143-4405-873e-8c9a9b9dc7ff))
						- Power App
						  collapsed:: true
							- [Shizuku compatibility requested](https://github.com/Domi04151309/PowerApp/issues/14)
						- ((63209284-c01f-4374-9a63-ee38b3b0f462))
						- SuperFreezZ
						  collapsed:: true
							- [Unknown if Shizuku compatible](https://gitlab.com/SuperFreezZ/SuperFreezZ/-/issues/160)
						- _Root optional_
							- Amaze File Manager
							- Material Files
							- ((63209285-2e05-40f2-bce9-5b8d813eea86))
						- Incompatible with ((63209285-2e05-40f2-bce9-5b8d813eea86))
							- Neo Backup (OAndBackupX)
							- ((63216f53-22cf-428a-9193-e5a423158e2b))
					- ((63209285-2e05-40f2-bce9-5b8d813eea86))-powered
						- [DarQ](<((632194a8-c91b-40b9-8620-c91826923c25))>)
					- _System apps_
						- ((6516669f-1bb2-4355-90e0-2fe32a948d2e))
						  id:: 63218746-e4bd-416f-8521-3f330ecebd53
					- [Learning Resources]
						- https://github.com/fynks/awesome-android-root
					- {Archive}
					  collapsed:: true
						- Wrong PIN Shutdown. Deprecated since it's no longer maintained
						- ((63ff8189-440c-460c-904e-72d2227e81fc)). Deprecated since I use ((638e7c15-6b65-4f35-82c7-05460cb45d8d)) instead now, and it doesn't require root
						- F-Droid Privileged Extension - flashed via recovery. Deprecated by Neo Store / Droid-ify, which allow unautomatic updates
						  collapsed:: true
							- May be resolved by: [Android 12 will let alternative app stores do automatic updates](https://beta.workflowy.com/#/c58f30ca1278)
						- _See_ [AFWall](https://workflowy.com/#/e5f2eed18186) - deprecated since it's incompatible with VPN usage (currently Mullvad)
						-
				- Alternative: ((63209285-2e05-40f2-bce9-5b8d813eea86))
			- New phone KeePass is a catch 22
			  collapsed:: true
				- Accounts (including Nextcloud) aren't copied over, and the password to gain access isn't easy
		- _Related: _
			- ((649b13cc-ed21-4d97-b946-440f2d0ff508)) : ((649b13cc-2779-4dfa-96e9-206343b62928))
			- ((649b13cc-23ea-4398-8dcb-488f7f9c55e6)) : ((644c0acb-0208-4ff7-8e23-8b7c7c74346a))
	- Mobile phone [[Privacy]]
	  id:: 63ff8143-8751-4460-80f6-b4212a0bbc22
	  collapsed:: true
		- Current
			- Different passwords for phone PIN and 2FA app (and both different from debit card PINs)
			- Messages don't show on lock screen (to prevent 2FA codes being viewed, and to block nosy people)
			- Related: ((63a9ad71-d5a4-49f6-abde-5cf5bda2052c))
		- All parts of phones are compromised
			- They hack the SIM Cards (GEMALTO), cellphone towers (stingrays), telco companies (BELGACOM), the mobile operating system (IRRITANT HORN)
			- - huge investment into Stingrays
			-
		- Pros/Cons
		  collapsed:: true
			- See
			- Most promising upcoming changes
				- To try: [XPrivacyLua](https://workflowy.com/#/3e92e5b4e5ea) (since Permissions Manager X isn't sufficient)
				- [Privacy Indicators](https://workflowy.com/#/6230c933365e) in Android 12
				- See [GrapheneOS](https://workflowy.com/#/ebacd6711d08) only if buying a new supported phone
		- _Risks/threat angles_
			- Duress passwords
			  collapsed:: true
				- [GitHub - x13a/Duress: Duress password trigger.](https://github.com/x13a/Duress)
				- Linux [GitHub - rafket/pam_duress: A pam module written in C for duress codes in linux authentication](https://github.com/rafket/pam_duress)
			- Wireless connectivity chips
			  id:: 649b13cd-0465-4324-b96a-f882181b1a0c
			  collapsed:: true
				- Cellular radio
				  id:: 649b13cd-0859-4c2f-8ad3-28bfe496eeba
				  collapsed:: true
				  Potentially very dangerous to privacy. Basic solution: disable 2G
					- _Hardware baseband modem processor_
					  id:: 649b13cd-0383-495e-8973-cdb138645c60
						- On baseband isolation via modem hardware being physically separated
						  id:: 644c0acc-16fa-4526-91aa-c590a321bb77
							- My post: ["Upcoming 2020 flagship phones will have baseband isolation, making them Stingray-proof and immune to backdoors"](https://www.reddit.com/r/privacy/comments/e9ma76/upcoming_2020_flagship_phones_will_have_baseband/) > I was ultimately incorrect, but it created a good discussion
							  collapsed:: true
								- Full text of OP
									- [https://arstechnica.com/gadgets/2019/12/qualcomms-new-snapdragon-865-is-a-step-backwards-for-smartphone-design/](https://arstechnica.com/gadgets/2019/12/qualcomms-new-snapdragon-865-is-a-step-backwards-for-smartphone-design/)
									- The new Snapdragon 865 SoC will not have a cellular modem at all, instead it will need a modem on a separate chip. This makes it vastly superior for security and privacy.
									- For those unaware of what baseband isolation is, basically cellular modems contain blobs of unknown code that are usually on the same System-on-Chip and therefore they have direct access to your system CPU and RAM, which allows it to infiltrate your system without there being any defence against it.
									- Stingrays that law enforcement use to push malware to your phone are the most well-known form of attack, but there are likely other backdoors being used by the NSA and other groups.
									- Some more reading about baseband isolation is available here: [https://www.osnews.com/story/27416/the-second-operating-system-hiding-in-every-mobile-phone/](https://www.osnews.com/story/27416/the-second-operating-system-hiding-in-every-mobile-phone/)
									- As far as I'm aware, the only current phones with baseband isolation are the Librem 5, PinePhone, Necunos NC\_1, and Neo900. This is a _huge_ change by having baseband isolation go mainstream.
									- This means phones will finally by default be protected from easy surveillance by government agencies and hackers on a hardware level. They could still track your location by just asking cell companies to give that data, but they can no longer have access to everything on your phone simply by pushing malware to it without you knowing.
								- Learnt
									- > qualcomm devices have had isolated basebands for years now, via IOMMU hardware isolation, specifically smmu. Just because something is now on a seperate chip doesnt mean its better isolated, the reason that the librem 5 has it seperated is so that they can shut off the power via a hardware switch, which you cant do with an intergrated modem.
									- Government stingrays have those telco signed certs, so your phone is very happy to talk to them as well.
										- The "security" between devices and cell stations is certificate based. You phone has the certs loaded from the telco, and uses it to verify it's talking to a legit base station.
							- ((649b13d1-e2a8-451b-bd09-44269a1b0ed5))
							- **Learnt**
								- Modems being on the same SoC means it has Direct Memory Access (DMA), but it's restricted by IOMMU
								- _USB-based modems can be exploited more easily than hardware-enforced IOMMU_
									- _What is IOMMU _
									  collapsed:: true
										- Hardware
											- it connects DMA-capable IO bus to the main memory and maps device-visible virtual bus addresses to the actual physical addresses exactly the same way CPU's MMU maps virtual addresses to the physical ones.This is why one is supposed to use DMA handles (or whatever they call it in Windoze parlance), rather than physical addresses when setting up DMA transfers - if the target machine is equipped with IOMMU a bus address does not necessarily have to correspond to physical RAM one, although there is a direct correspondence between these two on "classical" x86-based system without IOMMU.
									- Modems not being on the same SoC can still mean it can get DMA depending on the USB protocol implementeds
									- Unless you have the hardware documentation, you can't judge whether it's a secure interface that will not give DMA to the modem connected via USB
										- For example it could have a switch for specially coded data that puts it in a circuit that bypasses the usual mechanisms
										- It could have any sort of implementation that deviates from a fully securely implemented USB spec
									- Linux USB stack is also exploited with greater regularity than hardware-enforced IOMMU
									- iPhones use USB-connected modems (Broadcom or Intel I believe), as does Librem 5 and a few of the other "baseband isolation" phones
									- ((635037c3-993a-4bfc-9c65-2157fd59a626)) doesn't trust USB controllers either
									  collapsed:: true
										- https://blog.invisiblethings.org/2011/05/31/usb-security-challenges.html
										- https://www.qubes-os.org/doc/certified-hardware/
										- https://www.qubes-os.org/doc/security-guidelines/#reassigning-usb-controllers
										- https://www.qubes-os.org/doc/usb-qubes
								- USB-based modems only have better utility if there are also physical killswitches
								- _Stingrays_
									- They can intercept your communications, [if you're using GSM](https://en.wikipedia.org/wiki/Stingray_phone_tracker#Interception_of_communications_content)
									- They can do GSM downgrade attacks to then push malware, but this can be prevented by disabling 2G/GSM. It doesn't work on 3G and above since it requires mutual authentication
									- It can mimic your Carrier's push function to force a system update containing spyware. I've found it difficult to find information about how this works
						- ((649b13ca-7483-4a1d-bd90-89845f24084f))
						- Levels of threats and solutions
							- _Level 1: IMSI catchers_
							  collapsed:: true
								- Disable 2G(GSM) to prevent being hacked by IMSI-catchers
									- Replace Android IMSI-Catcher Detector with instructions on how to disable 2G
										- Why
										  collapsed:: true
											- IMSI-catchers work by downgrading connection to 2G and intercepting IMSI/IMEI of the device. However 3G and newer standards, on the other hand, are encrypted in transit and include mutual authentication, which makes classic MITM impossible.
											  source:: https://github.com/CellularPrivacy/Android-IMSI-Catcher-Detector/issues/82
												- Examples of attacks that involve downgrading connection to 2G
													- https://www.wikileaks.org/spyfiles/files/0/80_ABILITY-GSM_3G_Intercept.pdf
													- https://netzpolitik.org/wp-upload/Gamma-2011-GSM.pdf
													- https://www.privateinternetaccess.com/blog/2016/10/active-4g-lte-vulnerability-allows-hackers-police-eavesdrop-conversations-read-texts-track-smartphone-location/
													- https://boingboing.net/2017/08/14/buster-buster-buster.html
													- https://www.cis.upenn.edu/current-students/undergraduate/courses/documents/EAS499Honors-IMSICatchersandMobileSecurity-V18F-1.pdf
												- The 3G wireless standard offers some risk mitigation due to mutual authentication required from both the handset and the network
												  [SOURCE] http://www.ijritcc.org/download/1430372773.pdf
													- 3G introduced mutual authentication that made it a lot harder to mount fake base station attacks (such as those used in IMSI catchers). LTE tightened up many signaling protocols by requiring authentication and integrity protection for them.
											- AIMSICD is no use, because once it tells you that there is an IMSI-catcher in range, data has already been harvested. It would be nice to just tell how to disable 2G.​
										- Solution
										  collapsed:: true
											- Android settings - set to 4G preferred network. can't seem to set it to "only 3G/4G"
											  collapsed:: true
												- network settings--> mobile networks-->Preferred network type and select your preference accordingly.
												- lte/wcdma
												- change preferred network type to "WCDMA only" (3G). This can be done at least in the hidden Android Testing menu. After you change this option you need to disable and enable the radio again. This should prevent downgrading attacks from IMSI Catchers.
												- [source] [https://grapheneos.org/usage#lte-only-mode](https://grapheneos.org/usage#lte-only-mode)
											- Xposed module
											  collapsed:: true
												- Xposed framework, and the Intelli3G module (available on the Play Store or on xda). Inside the app, you can set any combination you want, like LTE/WCDMA which means 4G/3G but not 2G.
												- On Android there's a setting you can edit by pressing a combination on the dialler or you can use Xposed + Intelligi3G (set it to WCDMA/LTE only).
										- Network indicator icons in Android
										  collapsed:: true
											- 1x: 1xRTT (slow like a dialup modem (here: 80–100 kbit/s), shows up on US Cellular CDMA networks with Google Fi in Northern California)
											- GSM AKA 2G
											- G: GPRS (slow like dialup modem, here: 56–114 kbit/s)
											  AKA 2.5
											- E: Edge (enhanced GSM, about 400 kbit/s)
											  AKA 2.75
											- 3G: UMTS (384 kbit/s to 7.2 Mbit/s)
											  AKA CDMA, EvDo, TD-SCDMA, UMTS, WCDMA
											- H: HSPA (enhanced 3G, sometimes shown as 3.5G; up to 21 Mbit/s)
											- H+: HSPA+ (even more enhanced/faster HSPA; up to 42.2 Mbit/s)
											- 4G: LTE (thanks to eldarerathis for confirmation); up to 300 Mbit/s
											- 5G: not yet in the wild; up to 10 Gbit/s planned
									- IMSI-Catcher detector apps (all are abandoned and/or don't catch all methods of hacking)
										- AIMSICD
											- Uninstalled Nov 17 because app hasn't been updated with the new version and is just wasting battery otherwise
											- https://github.com/5GSD/AIMSICDL
											- https://github.com/5GSD/AICDm
							- Level 2: Government hacking (baseband radio exploits)
							  collapsed:: true
								- _Why it is dangerous_
								  collapsed:: true
									- Baseband processor has DMA (direct memory access) to CPU
									- Analogy compared to laptop connectivity
									  collapsed:: true
										- Thought experiment for the dubious.
										- Imagine that you have been assigned by work to carry a laptop with you at all times. This "GovCorp" laptop has a solid-state hard drive so that you can't tell if it's spinning or not and a cool VIA x86 processor so that no fan is needed either. Thus when it's on there is no more "physical motion" to your laptop than there is when it's off.
										- This laptop has Windows 2000 on it, installed by GovCorp, with whom you have a draconian contract in which you are associated by serial number to the laptop. You don't have the administrator password to this laptop, and aren't able to see most of the software that's installed on it. While GovCorp is very secretive about what the software might be or how it might work, they're happy to admit there's a lot of software on it, and that this is a feature, not a bug.
										- In the start menu, there is no "Shut down" option, just a "Suspend" option. Suspending and resuming are very reliable on this laptop, and only take a second or two. Of course, there's no hard drive to spin up and no fan, so it's hard to know exactly what it's doing when you suspend, beyond turning the screen off.
										- The laptop has a built-in mic and you keep most of your communication with friends, your emails to your representatives, a few credit card numbers and transactions, and most of your contacts on the laptop.
										- The laptop+GovCorp contract came with free network connectivity via a number of clearly labeled GovCorp ethernet jacks around the city. You don't know how the security or firewalling on the laptop might be set up (only the Administrator account can see the configuration and of course you don't have Administrator access), but you trust that something has been done to ensure that your data is private from GovCorp, with whom you have the contract.
										- So for the next year you walk around with this laptop whose Windows 2000 you did not install or configure and for which you do not have Administrator access or even a full start menu (but for which GovCorp has both), communicating, suspending, and resuming, and very often plugging your ethernet cable into the GovCorp jacks around the city.
											- Do you feel as though the data that you put on this laptop is secure?
											- Do you feel as though your location when plugged into the GovCorp network is private from GovCorp?
											- Do you trust that the mic is not recording you just because you don't see an audio app on the screen or the laptop has been "suspended" and the screen is dark?
											- Do you trust that the laptop is not evolving (i.e. that software is never added/removed without your knowledge?)
										- Your cell phone is the same thing, only smaller, even more tightly tied to GovCorp, and it finds and connects to networks through the air, by itself, without your having to plug in a cable.
									- It uses a separate CPU run entirely in firmware that the OS cannot replace but which can attack the OS. This should be obvious: some of the "attacks" used to root phones so their own users can control them are baseband radio exploits. It's reasonable to assume that manufacturer backdoors and most of the law enforcment backdoors are in the baseband radio firmware. Carrier backdoors might be in the OS instead, simply to save carriers the trouble of flashing custom firmware to all their devices.
									- So far as Tor is concerned a mutually adversarial relationship between phone subscriber and carrier is assumed, an assumption I have always shared. After all, phone companies make money selling out your privacy, and are subject to laws like CALEA that require backdoors for the cops. Software authors are not subject to such laws in enough countries to block safe hosting for non police friendly projects.
								- Devices with hardware baseband isolation
								  intralink2:: https://workflowy.com/#/0106e0a61351
								- Device without baseband radio (e.g. tablet) + a portable router
								  collapsed:: true
									- Overview
										- The Tor Project thus believes that a device entirely without a baseband radio must be used. They recommend a wi-fi only tablet used with separate carrier-provided wifi hotspot. Since that hotspot is not on the tablet's bus it cannot attack the tablet's OS any more effectively than any of the other untrusted routers on the entire Internet can. A radio that does not work from the OS, btw, still works in firmware and could be remotely used against the OS. If you can get the device apart you could remove it and set it aside, otherwise you need another device if Tor level safety is needed.
										- This sort of device won't be able to make conventional phone calls, but broadband-only data plans on wifi hotspots should be able to run VOIP applications, and the carriers won't be able to block them as they don't control the app infrastructure on this sort of device. Text messaging would be limited to Twitter-style web apps, but carrier charges for text are a huge scam anyway, Functionality would be close to a normal phone, except for cops and advertisers trying to track the device. Speaking of tracking, those cell hotspots often lack accurate GPS, as they are not expected to be able to make 911 calls. Thus, tracking is limited in many cases to triangulation. In an urban environment that might not place you in a particular building, thus not be enough for a warrant or a police ambush.
									- Portable routers
										- Current one
										- Thinner version £23 https://www.amazon.co.uk/gp/aw/d/B00KR51QCO/
								- Related: Open-source basebands
								  collapsed:: true
								  Note: this means using your own DIY cell towers, useful for remote areas
									- Software-defined radio
										- GSM
											- OpenBTS
											  Has done Burning Man successfully
												- http://openbts.org/
												- http://wush.net/trac/rangepublic/wiki
											- OsmocomBB - Compatible with old phones
											  https://osmocom.org/projects/baseband/wiki/Phones
												- How
													- Open source baseband http://bb.osmocom.org/ have managed to reverse engineer an old GSM chipset (with help from leaked documents and source code) and created an open source GSM base band for those old phones.
												- Models
													- Sony Ericcson J100i
													  http://www.gsmarena.com/sony_ericsson_j100-1430.php
														- https://osmocom.org/projects/baseband/wiki/SonyEricssonJ100i
													- Motorola C123
													  http://www.gsmarena.com/motorola_c123-2101.php
														- https://osmocom.org/projects/baseband/wiki/MotorolaC123
													- OpenMoko phones
													  https://shop.goldelico.com/wiki.php?page=Wireless%20Data
											- OpenBSC
											  http://openbsc.osmocom.org/trac/
										- LTE
											- openLTE
											  https://sourceforge.net/projects/openlte/
											- gr-lte
											  https://github.com/kit-cel/gr-lte
											- Open Source Long-Term Evolution (LTE) Deployment
												- https://sites.google.com/site/osldproject/
												- http://flexnets.github.io/aloe/
											- OpenAirInterface
												- http://www.openairinterface.org/
										- OpenCellular by Facebook
										  https://techcrunch.com/2016/07/06/facebooks-opencellular-is-a-new-open-source-wireless-access-platform-for-remote-areas/
									- Hardware
										- OpenBTS provided a station at Burning Man 2008
											- http://openbts.sourceforge.net/FieldTest/
											- The OpenBTS Project's 70-foot tower and three antennas
											  http://i.imgur.com/J3w2x1F.png
											- Tech ($3-5k)
											  [archived] http://openbts.sourceforge.net/FieldTest/TechPrep.html
												- We borrowed a 30-ft Army surplus AS-2236 mast from a consulting client. These run $200-$400. We also bought a 8'-long 9 dBi marine cellular antenna, new, for $100, to put on top of it.
												  http://openbts.sourceforge.net/FieldTest/FullMast.jpg
												- We used our existing USRP, RFX900 daughter cards and an Apple MacBook Pro for the digital radio, GSM stack and Asterisk server. (Those are Nokia 3310 and 5110 handsets on top of the USRP.) That USRP equipment cost about $1,500. Running at full load (7 active lines) the multi-threaded basestation consumed about 50% of the Intel dual-core 2.33 GHz MacBook.
							- Level 3: Government tracking (triangulation)
							  collapsed:: true
								- Prevent triangulation (get internet whilst preventing location tracking)
								- Solutions
									- Dapp which pays you to share your mobile hotspot
										- QLC Chain
										- Althea
										- #Decentralisation https://workflowy.com/#/6c238c12c361
									- Mesh networks
									- WiFi coverage everywhere
									- Mini ProxyHam
									- No ((649b13cd-0859-4c2f-8ad3-28bfe496eeba)) - use WiFi only tablet
									- Directional antennas (see [Remote Wi-Fi](https://workflowy.com/#/bd17d0566480))
										- 2 Backlinks
											- (1, 2) see [Directional antennas](https://workflowy.com/#/c1ccd0b292cd)
											- See [Directional antennas](https://workflowy.com/#/c1ccd0b292cd)
								- Disable Wi-Fi RTT
					- **SORT**
						- Dangers
							- collapsed:: true
							  1.  Prevent passive triangulation via CSLI (cell-site location information)
							      collapsed:: true
								- Why
									- cell-site location information, or CSLI. CSLI is created whenever a cellphone talks to a cell tower: It’s a record of towers that a cellphone pinged, what direction the cellphone’s ping came from, and what time the ping came.
									- Police seek three different kinds of CSLI. The first is historical CSLI, when detectives ask for days, weeks, or months of this kind of location data from the past. This is an extremely common process: From January to June 2015, Verizon received more than 21,000 requests of this type. Right now, this kind of process doesn’t require a warrant in most jurisdictions. (The courts don’t completely agree on the law around this technology, though, so the Supreme Court could wind up weighing in on the issue soon.)
									- The second kind of CSLI is "prospective" or “real-time.” Law-enforcement agents might ask a mobile provider for a phone’s current location or its upcoming week of pings. They might also demand that the provider send a ping to the phone right now, generating its own record of CSLI. This type of search usually does require a warrant.
									- The third type of CSLI is called a "tower dump," and it works more like a dragnet. Authorities will ask a provider for all the CSLI from a tower or towers from a certain period, then comb through that looking for a common number. (They’d be investigating a question like: Which cellphone numbers were near this bank an hour before or after it was robbed?) Hanni Fakhoury, a senior staff attorney at the Electronic Frontier Foundation, told me there was very little case law on this kind of search, but that, in the one relevant court ruling he knew of, a warrant was not required.
								- cellular geolocation systems involving time difference of arrival (TDOA) and angle of arrival (AOA)
									- It uses both triangulation + signal strength to determine location
							- 2.  Prevent active triangulation real-time/prospective CSLI
							      i.e. cellular provider pings your number
							- collapsed:: true
							  3.  Protect against Stingrays
							      collapsed:: true
								- Stingrays are devices that mimic cellphone towers and can pinpoint a phone’s physical location or record which number they’re calling.
								- Stingrays rely on jamming to work. If you set your phone to only use LTE towers it significantly raises the difficulty of an attack. Most android phones allow the types of signal allowed to be changed with the secret menu. Open the phone dialer and dial _#_#4636#_#_ In the menu that pops up, you can check "set preferred network type" drop down menu. You want an option that doesn't allow fallback/downgrades. The options vary depending on which Android OS you're running, but generally you want "LTE only". This prevents the jamming of 4g and 3g signals from moving you back to 2g where A5/0 encryption can be selected that is breakable (or rather, isn't encrypted at all). It'll simply knock your device offline instead.
							- collapsed:: true
							  4.  E911
							      collapsed:: true
								- Note 1
									- also part of underwraps subsections of ETSI LI spec framework for LI (Lawful Interception) hint at leveraging the E911 feature that makes a cell not be able to disconenct if a 911 operator toggles a cell phone into "stay online no matter what" mode. Heck, ive played with that mode once... had to rip out the battery! (no way to hang up). Technology was added to prevent poor signal drops during a 911 call, but then used to keep line open while victim is delirious or expiring. For docs, Just look for havesting all spec docs starting with S3LI03 prefix on the net. Or hang around Cryptome or usual places.
									- Regarding the gocv tracking your movements in real time (if battery not removed from your non-GPS cell : 1996 the FCC defined a fancier "E911 Phase 2" for more precise ALI information to PSAPs using latitude and longitude information, and to identify a mobile caller's location within 125 meters (410 feet) 67% of the time to the PSAP. A PSAP is one of over 6,000 Public Safety Answering
									- Points (PSAP), some route , some deal directly with initial public calls. FCC 97-402 CC Docket No. 94-102 rules (i.e., by October 1, 1996). besides the 34-bit Mobile Identification Number (MIN), being sent in Phase I of E911, the 34 bit MIN accepted a "call back' even without a valid phone number, as the 1996 regulation also stipulates that CELL PHONES WITH NO CONTRACT OR DORMANT DEVICES MUST HAVE FREE ACCESS TO 911 service, no matter what. The tracking protocol is indepentdant of billing accept/reject.
									- To allow the cell to be detected within 410 feet WITHOUT GPS, cell phone towers use triangulation methods automated with cellular geolocation systems involving time difference of arrival (TDOA) and angle of arrival (AOA)
								- US Patent 7,751,826 [google.com]
								  US Patent 7751826 - Motorola submitted the patent in 2002, it was issued in 2010:
									- The Federal Communications Commission (FCC) has mandated that, by December 2002, all cellular telephone carriers must market handsets capable of providing an emergency locator service. This emergency locator service, known as E911, will enable personnel at the public safety answering point (PSAP) to pinpoint the location of a cellular telephone user dialing 911. This FCC mandate further requires that the user not be able to override the emergency locator service in the case of a 911 emergency call.
									- This technology has raised public concern that, in addition to being used for emergency location, the locator service may be used by cellular carriers or by others to track the movements of cell phone users without their consent. There is therefore a need for a system that complies with the FCC mandate for location service while providing maximum privacy protection for cell phone users.
									- The invention overcoming these and other problems in the art relates in one regard to a system and method for selectively activating or deactivating E911 tracking service, in an embodiment by disabling power to GPS locator circuitry in a cellular telephone until the key sequence "9-1-1-Send" is detected. In one embodiment, the power to the GPS circuitry in a cellular handset may be activated by detection of a keypad sequence and the rotation of a physical switch to permit power delivery. When the handset detects the key sequence "9-1-1" it may output a signal that loads the switch into a "ready" position. When the user presses the "Send" button, the switch closes, enabling power to be delivered to the GPS circuitry. In other embodiments, the selective delivery of power may be controlled by software.
									- Motorola has been building phones for more than a decade in which the GPS circuitry is physically separated from electrical power until the user does something that causes it to be connected. This obviously doesn't help you if your phone has been hacked or modified and it doesn't help you avoid network triangulation, but it makes you wonder how all these supposed experts know all about the "dangers" of cell phones without having done much research or talking to the people who actually made the phones (you know, the inventors of patents are listed on the patents).
								- 1 Backlink
									- It turns off however it can be forced on by [E911](https://workflowy.com/#/28eb86738c18)
							- Closed-source firmware - has backdoors
							- Has full access to CPU - unless there's hardware baseband isolation
							  collapsed:: true
								- the baseband processor has complete, unfettered access the application processor, which means it has complete, unfettered access to the OS.
									- .. and by unfettered, we mean it has DMA access to the application processor. It's not a hook or an API call or some functions it can call - it has low level bit for bit access to manipulate the CPU that your OS (like android) runs on.
									- Further, your carrier (verizon, att, whatever) can push OTA updates and commands straight to baseband via the radio, bypassing the CPU and OS (like android) and manipulating the phone on a low level bit by bit basis.
									- Even the most well secured, rooted, reloaded phone has every piece of it totally owned by the carrier, via the baseband processor.
								- Qualcomm and most modern SoCs has separate IOMMU groups for modem/baseband processor and main processor. This means the baseband processor doesn't get access to the OS
							- Baseband processor
							  collapsed:: true
								- Reveals location constantly
								- Texts and phone calls are not private
								- Data not private unless using a VPN
								- Can be hacked by state actors with IMSI catchers
								- Can be hacked by amateurs with physical possession of phone
							- SIM cards
							  collapsed:: true
								- [https://srlabs.de/bites/sim_attacks_demystified/](https://srlabs.de/bites/sim_attacks_demystified/)
								- [https://thehackernews.com/2019/09/simjacker-mobile-hacking.html?m=1](https://thehackernews.com/2019/09/simjacker-mobile-hacking.html?m=1)
								- [https://srlabs.de/bites/rooting-sim-cards/](https://srlabs.de/bites/rooting-sim-cards/)
							- Carrier settings updates
							  collapsed:: true
								- [https://googleprojectzero.blogspot.com/2020/12/an-ios-zero-click-radio-proximity.html?m=1](https://googleprojectzero.blogspot.com/2020/12/an-ios-zero-click-radio-proximity.html?m=1)
							- Modems are often isolated by being connected via USB, or if on your SoC the modem has DMA then it's isolated via IOMMU groups.
							- SIM cards have to implement the E911 feature which allows 911 operators to toggle a cell phone into "stay online no matter what" mode.
							- Some SIM cards have additional apps installed on them, which allows attacks like SIMjacker and WIBattack.
							- Modem, transmitter and antenna
						- Solutions
							- ((649b13ca-7483-4a1d-bd90-89845f24084f))
							- Airplane mode
							  collapsed:: true
								- It turns off however it can be forced on by [E911](https://workflowy.com/#/28eb86738c18)
							- (1-4) Block cell signal completely
							  collapsed:: true
								- Take battery out of phone (turning it off is insufficient)
								- Tablet
								- Faraday cage
								- Faraday bag
								- Cell phone jammer
							- (1, 2) see [Directional antennas](https://workflowy.com/#/c1ccd0b292cd)
							- (1, 2) Some weak false associations or intermediary transmission layer such a radio that links you to your phone
							- ProxyGambit
							  collapsed:: true
							  Directional antenna (ProxyHam) + reverse tunneled GSM bridge
								- Pic of whole setup
								  http://i.imgur.com/jZjl5lO.jpg
								- Reverse tunneled GSM bridge/Reverse TCP tunnel
									- Why
										- GSM doesn't give away as accurate location as IP or MAC and GSM chips can be acquired with no tie to you.
									- GSM gateway
										- Raspberry Pi GSM bridge (Pi running RasPBX; a Huawei dongle for 3G; a Chan dongle which works as an Asterisk channel driver; and a USB modeswitch. The whole kit came to €75.)
										  [archived] https://www.raspberrypi.org/blog/raspberry-pi-gsm-gateway/
									- The question is: can it proxy my location or show IP directly?
									- Alternatives
										- Hardware version of OpenVPN/SSH tunnel?
										- similar to dropping a portable charger + cheap 3G phone in a hidden location in a coffee shop
											- Use Android as an OpenVPN _server _(requires Linux on phone)
											  [archived] http://davebennett.tech/vpn-server-android/
								- http://www.broadband-hamnet.org/just-starting-read-this.html
							- _Alternative internet access to mobile broadband_
							  collapsed:: true
							  None viable
								- Mobile broadband (submarine cable
								  https://en.wikipedia.org/wiki/Mobile_broadband
								- ((64e0946d-e1fe-4a7a-8612-66fd9811f448))
								- Mesh networks
									- Residential gateway modems
									  https://en.wikipedia.org/wiki/Residential_gateway
							- _Alternative PSTN/POTS access to cellular networks_
							  collapsed:: true
								- ((65d8a377-1017-4ae2-9daa-8ddf76668577))
								- OpenBTS
								  Software-based GSM access point (FOSS cellular infrastructure/base tower)
									- https://en.wikipedia.org/wiki/OpenBTS
									- http://openbts.org/w/index.php?title=Main_Page
									- Open Base Transceiver Station
									- i.e. create a hardware access point, connect to it to make phone calls to PTSN
									- software-based GSM access point, allowing standard GSM-compatible mobile phones to be used as SIP endpoints in Voice over IP (VOIP) networks
									- Replace much of the traditional infrastructure involved in cellular networks with software.
									- All you need to run a GSM network with OpenBTS is radio software and an off-the-shelf Linux server.
									- When combined with basic PC and RF components that can be picked up on the surplus market, this enables the creation of a GSM base station at a cost of somewhere in the order of £1,000-£2,000.
									- $3300 Range Networks Professional Development Kit
									  https://web.archive.org/web/20160407211540/http://www.rangenetworks.com/products/professional-development-kit
										- The Range Networks Professional Development Kit is intended for professional lab use. It makes it easy to experiment with OpenBTS or to simulate small 2.5G cellular networks, and you can set up a test network and start making calls in less than an hour.
										- This kit enables your GSM handset to connect directly with VoIP networks. Handsets appear as SIP endpoints to VoIP networks.
										- The Professional Development Kit uses the the commercial release of the OpenBTS software. The Professional Development Kit is designed for short range laboratory use. Approximately the size of a textbook, the kit can easily sit on any workspace.
										- For commercial network use, check out the 10W and 50W Range Networks OpenCell products. A 1W version of the OpenCell is also available for laboratory use.
										- Benefits
										- Run the commercial version of OpenBTS out of the box
										- Designed to use in labs or for commercial experimental use
										- Make calls, send SMS, and access GPRS data using OpenBTS
										- Small enough to fit on any workstation
										- What's Included
										- A Range Networks' designed software-defined radio for the purpose of running OpenBTS
										- GSM band of operation is adjustable via software
										- A Mini-ITX board configured with:
											- The latest commercial release OpenBTS software
											- Software libraries that support OpenBTS
											- Asterisk and Ubuntu
										- Board includes 16GB mSATA flash drive, and 2GB RAM
										- 12V 5 Amp power supply
										- Two rubber duck antennas with SMA-type connectors
										- Two pre-programmed SIM cards
										- Two multi-band cellular phones
									- Used for Stingrays?
										- A search and rescue team in Iceland, for instance, used the software to turn one of its helicopters into a flying cellphone tower that can be used to triangulate the location of missing persons.
										- And yes, the software can be used by hackers to hijack people’s phone calls by spoofing cellphone towers
									- Hardware
										- https://www.ettus.com/product/details/UB210-KIT
										- Universal Software Radio Peripheral (USRP™) platform
										- OpenBTS support through the open-source USRP Hardware Driver™ (UHD)
										- http://shop.fairwaves.co/
											- Blog
											  http://umtrx.org
									- $300 LimeSDR
										- LimeSDR is a low cost, open source, apps-enabled (more on that later) software defined radio (SDR) platform that can be used to support just about any type of wireless communication standard. LimeSDR can send and receive UMTS, LTE, GSM, LoRa, Bluetooth, Zigbee, RFID, and Digital Broadcasting, to name but a few.
										- Possibilities
											- Radio astronomy
											- RADAR
											- 2G to 4G cellular basestation
											- Media streaming
											- IoT gateway
											- HAM radio
											- Wireless keyboard and mice emulation and detection
											- Tire pressure monitoring systems
											- Aviation transponders
											- Utility meters
											- Drone command and control
											- Test and measurement
										- https://www.crowdsupply.com/lime-micro/limesdr
									- Possiblt hardware - comparison
									  http://i.imgur.com/T9VrjNB.png
									- Worked well at Burning Man
										- In describing the opportunity presented by customizable cells, Tim cited an actual example from Burning Man: "We let users pick their own number, permitted short outgoing calls, and only allowed incoming calls from PSTN numbers they had recently called. So your accountant or boss can't call you at the festival, but your cat sitter can call you back. The essence of this is to break the one-size-fits-all behaviour of current (huge) cell networks."
										- Dean Elwood is CEO of Voxygen, a communications technology design and development company that works with cellular operators, and which has received a temporary licence from Ofcom to operate an OpenBTS-based GSM test network. When asked about the opportunity presented by open source GSM he replied: "Huge." He continued: "It has the potential to disrupt the network equipment provider market where, currently, enormous fees are charged for making the smallest configuration change. Mobile operators are under incredible pressure due to competition from companies such as Skype who are encroaching on their revenues, and open source represents a future model for the delivery of network technology where costs are substantially reduced. This could spell a significant disruption to certain vendors."
									- https://stackoverflow.com/questions/14753784/dtmf-sending-attempt-failed-by-gsm-mobile-phone-over-pstn-dial-tone-using-asteri
									- Comments
										- It is interesting, but I think it is a dead end. The concept is possible because GSM doesn't require mutual authentication. Consequently, devices can "relatively" easily attach to a tower, if a bunch of circumstances are true.
										- Umts requires mutual authentication, so any devices that will connect must be preconfigured to do so. This means that attaching to your own tower becomes a lot less simple: each device must be configured to work with your own cloud.
										- I think it is a dead end because gsm will be phased out eventually. This is only "easy" today because many phones are dual stacked gsm/umts.
										- OpenBTS really started some interesting work in this space, but I think openBSC is the more advanced (and less approachable) soloution. OpenBSC recently reported some small ability to support a little bit of GPRS. Without GPRS support, there is no ability to do data on your phoney tower. Unfortunately, the hardware on openBSC is less accessible.
									- https://www.reddit.com/r/RTLSDR/
									- https://www.reddit.com/r/RTLSDR/comments/33fwlb/im_a_beginner_what_should_i_do_how_do_i_get_it/
									- https://www.reddit.com/r/RTLSDR/comments/2unves/rrtlsdr_is_trending_new_to_software_defined_radio/
								- SatNOGS
								  FOSS satellite ground station and network
									- https://satnogs.org/
									- Targeting Low Earth Orbit satellites first (obviously)
									- $300 prototypes available to 3D print
							- **Unfeasible**
							  collapsed:: true
								- Software to selectively choose what cellular towers to connect to
									- I dont think so. If you were able to do this, you could bring down the entire cell infrastructure via DoS. Cell works because it load-balances itself so well.
							- FOSS modem firmware
							  collapsed:: true
								- Legality
									- allowing the user to change parts of the software is illegal, which only means you have to prevent unsigned builds from being installed. That doesn't mean source code can't be released.
								- Implementations
									- See PinePhone [FOSS modem firmware being developed](https://workflowy.com/#/a1bc2d40ff7f)
									- OpenLTE
										- https://sourceforge.net/projects/openlte/
									- YateBTS
										- http://wiki.yatebts.com/index.php/Main_Page
									- OsmocomBB
										- FOSS modem firmware for phones (GSM, and for a few dumbphones)
										  [https://osmocom.org/projects/baseband/wiki](https://osmocom.org/projects/baseband/wiki)
										- Osmocom
											- Umbrella organisation has projects for virtually all parts of cellular infrastructure
							- FOSS alternative base stations
							  collapsed:: true
								- Software-Defined Radio
									- What is it
										- It can transmit/receive any signal frequency theoretically
										- Does this in much smaller and cheaper devices than analog
										- LimeNET base stations hold the potential to completely transform the way telco networks run by shifting the emphasis and value away from proprietary hardware to open hardware with app stores on top.
									- [https://en.m.wikipedia.org/wiki/Software-defined_radio](https://en.m.wikipedia.org/wiki/Software-defined_radio)
									- [http://yatebts.com/technology/software_defined_mobile_networks](http://yatebts.com/technology/software_defined_mobile_networks)
									- _Products_
										- Lime Microsystems products (all open-source hardware)
										  [https://www.crowdsupply.com/lime-micro](https://www.crowdsupply.com/lime-micro)
											- [https://limemicro.com/](https://limemicro.com/)
											- LimeNET Snap (apps)
											  [https://limenet.snapcraft.io/](https://limenet.snapcraft.io/)
											- Forum
											  [https://discourse.myriadrf.org/c/projects/limesdr/21](https://discourse.myriadrf.org/c/projects/limesdr/21)
											- Hardware
												- LimeNET CrowdCell (2022?)
												  [https://www.crowdsupply.com/lime-micro/limenet-crowdcell](https://www.crowdsupply.com/lime-micro/limenet-crowdcell)
												- LimeNET Micro (2018)
												  [https://www.crowdsupply.com/lime-micro/limenet-micro](https://www.crowdsupply.com/lime-micro/limenet-micro)
												- LimeNET (2017)
												  [https://www.crowdsupply.com/lime-micro/limenet](https://www.crowdsupply.com/lime-micro/limenet)
												- LimeRFE (2019)
												  [https://www.crowdsupply.com/lime-micro/limerfe](https://www.crowdsupply.com/lime-micro/limerfe)
												- LimeSDR (2017)
												  [https://www.crowdsupply.com/lime-micro/limesdr](https://www.crowdsupply.com/lime-micro/limesdr)
													- [https://limemicro.com/products/boards/limesdr/](https://limemicro.com/products/boards/limesdr/)
												- LimeSDR Mini (2017)
												  [https://www.crowdsupply.com/lime-micro/limesdr-mini](https://www.crowdsupply.com/lime-micro/limesdr-mini)
										- Realtek RTL2832U chipset
										  [https://old.reddit.com/r/RTLSDR/](https://old.reddit.com/r/RTLSDR/)
								- DIY IMSI catcher/base station (GSM-based)
									- https://evilsocket.net/2016/03/31/how-to-build-your-own-rogue-gsm-bts-for-fun-and-profit/
								- $1400 LTE base station
									- http://securityaffairs.co/wordpress/41513/hacking/low-cost-imsi-catcher-lte.html
								- [https://librecellular.org/](https://librecellular.org/)
					- ![Blue Merle - Reducing Your Cellular Footprint.pdf](../assets/Blue_Merle_-_Reducing_Your_Cellular_Footprint_1728727579617_0.pdf)
				- Location Services
				  collapsed:: true
				  Use GPS only, but if rooted/custom ROM then use µg UnifiedNlp
					- Android Location Services
					  http://developer.android.com/guide/topics/location/obtaining-user-location.html
						- periodically checks on your location using GPS, Cell-ID, and Wi-Fi to locate your device. When it does this, your Android phone will send back publicly broadcast Wi-Fi access points' Service set identifier (SSID) and Media Access Control (MAC) data. Again, this isn't just how Google does it; it's how everyone does it. It's Industry practice for location database vendors.
					- See [Unified](https://workflowy.com/#/cafeea2a4f61)<a href="https://workflowy.com/#/cafeea2a4f61"> Network Location Provider (</a><a href="https://workflowy.com/#/cafeea2a4f61">Unified</a><a href="https://workflowy.com/#/cafeea2a4f61">Nlp)</a> (no GAPPS) - location middleware provider
					- Guide
					  https://forum.fairphone.com/t/pencil2-living-without-google-2-0-a-google-free-fp2/11587
						- Install [µg ](https://workflowy.com/#/cafeea2a4f61)<a href="https://workflowy.com/#/cafeea2a4f61">Unified</a><a href="https://workflowy.com/#/cafeea2a4f61">Nlp</a> (no GAPPS)
						- Install geolocation backends such as LocalGsmNlpBackend
						- Install geocoding backend NominatimeNlp
						- Reboot your phone
						- Start the [µg ](https://workflowy.com/#/cafeea2a4f61)<a href="https://workflowy.com/#/cafeea2a4f61">Unified</a><a href="https://workflowy.com/#/cafeea2a4f61">Nlp</a> app and set up the backends. In LocalGsmNlpBackend select 'create database' and let it generate a database from OpenCellID or Mozilla Location Services (this takes ages and downloads huge amounts of data so make sure you are on WiFi)
						- Enable Location options in Settings
						- Result: both GPS and network-based location services work with little or no privacy impact.
				- GPS
				  collapsed:: true
				  Not a risk. Receiver only not transmitter
					- Note: The presence of a GPS chip, does not necessitate nor require user tracking, the GPS chip itself receives an inbound broadcast signal to determine your location and does not broadcast your location. Applications that have access to the GPS data can (and often do in other phone manufacturers) use that data to show you your location on your device, and send your exact location to servers
					- http://www.howtogeek.com/137862/htg-explains-how-gps-actually-works/
				- Bluetooth
				- WiFi
				  collapsed:: true
					- Wi-Fi Triangulation (multiple WiFi networks nearby)
					- WiFi RTT (estimating location based on connecting to just one AP)
				- Hardware killswitch for radio (SIM, WiFi, GPS)
				  collapsed:: true
					- Software toggles is enough
					- I want a hardware switch for turning off any transmitting/receiving (a.k.a. airplane mode)
				- Hardware killswitch for camera/microphone
			- Binary blobs in firmware (see Librem 5 for a RYF-certified device)
			- Android OS - File-Based Encryption (FBE) - encrypted whilst lock screen on
			  collapsed:: true
			  AKA Direct Boot / android lock screen encryption
				- [http://wordpress.conncoll.edu/informationsecurity/2017/04/12/mobile-device-encryption/](http://wordpress.conncoll.edu/informationsecurity/2017/04/12/mobile-device-encryption/)
				- Android FBE as of Nougat (7) doesn't evict cryptographic keys whilst the screen is locked (unlike iPhones), which means it's still susceptible to DMA attacks
				  source:: https://blog.cryptographyengineering.com/2016/11/24/android-n-encryption/
				  collapsed:: true
					- Apple 'Complete protection' protection class
						- Files encrypted with this class key can only be accessed when the device is powered up and unlocked. To ensure this, the class key is evicted from RAM a few seconds after the device locks.
						- https://developer.apple.com/reference/foundation/nsfileprotectioncomplete
						- Credential encrypted storage is only available after the user has successfully unlocked the device, up until when the user restarts the device again. If the user enables the lock screen after unlockin the device, this doesn't lock credential encrypted storage.
						- ...
						- it’s the two missing categories that cause the problems. These are the “complete protection” categories that allow the user to lock their device following first user authentication — and evict the keys from memory.
						- Moreover, a quick read of the documentation shows that even if you wanted to, there is no unambiguous way for Android to tell applications when the system has been re-locked. If keys are evicted when the device is locked, applications will unexpectedly find their file accesses returning errors. Even system applications tend to do badly when this happens.
						- And of course, this assumes that Android N will even try to evict keys when you lock the device
					- You have to use a DMA attack (e.g. cold boot attack)
						- Are keys that easy to steal?
							- Of course it’s reasonable to ask whether it’s having keys in RAM is that big of concern in the first place. Can these keys actually be accessed?
							- The answer to that question is a bit complicated. First, if you’re up against somebody with a hardware lab and forensic expertise, the answer is almost certainly “yes”. Once you’ve entered your passcode and derived the keys, they aren’t stored in some magically secure part of the phone. **People with the ability to access RAM or the bus lines of the device** can potentially nick them.
							- Of course, all of this is mostly irrelevant. The main point is that if the keys are loaded you don’t need to steal them. If you have a way to get past the lockscreen, you can just access files on the disk.
						- See DMA attacks e.g. cold boot
						  intralink2:: https://workflowy.com/#/48e05d6498eb
							- DMA attacks - Any port/slot that provides DMA can be used to dump the RAM of a box. For example, Firewire, Thunderbolt, PCI slots. See:
								- http://en.wikipedia.org/wiki/DMA_attack
								- ...but even if that wasn't available an attacker can always just crack open the case and attach some really fancy hardware directly to the memory chips (search for "forensic RAM analysis"). There's not much in the way of commercial products but don't take that as evidence that such devices do not exist. We must assume that they do (absence of evidence is not evidence of absence).
						- With physical access to the a device an assailant can dump RAM (if they're quick enough and ideally use cooling stuff like liquid nitrogen)
						  https://en.wikipedia.org/wiki/Data_remanence#Data_in_RAM
						- Non-Android devices are slightly more susceptible to cold boot attacks, but even that requires a DMA attack
							- File-based encryption? See LUKS or VeraCrpyt
							- LUKS
								- You should however note that if your computer is taken whilst running or in suspend mode (hibernation is fine), there are various, fairly easy techniques to extract the password from RAM. I would thusly advice caution on which state you leave your laptop in whilst traveling, but overall you should be safe from most potential scenarios of data loss.
								- The encryption key is cached somewhere in RAM as the operating system needs it every time it reads/writes data on the encrypted disk.
							- https://en.wikipedia.org/wiki/Cold_boot_attack
					- ...
					- https://source.android.com/security/encryption/file-based
					- In 6 or lower it's a choice between allowing Tasker and password managers access to unencrypted state or no notifications or apps being loaded on initial boot
					- https://yourtechexplained.com/2016/12/08/explained-android-nougat-file-based-encryption/
					- The major difference is that smartphone users are never encouraged to shut down their device. In practice this means that — after you enter a passcode once after boot — normal users spend their whole day walking around with all their cryptographic keys in RAM. Since phone batteries live for a day or more (a long time compared to laptops) Full-Disk Encryption doesn’t really offer much to protect you against an attacker who gets their hands on your phone during this time.
				- If your device is rooted, then
				  collapsed:: true
					- If you're rooted, then malware has an easier time getting access to anything
						- Apps such as Super SU prompt the user before allowing another app to become root. Doesn't this mitigate the vulnerability in your last paragraph? – SilverlightFox Jan 29 '16 at 14:40
						- Well, all these apps do is implement a directory based Access Control Management. This might prompt a message when you install apps or maybe even if they run, but all the background processes associated with your account which run all the time will still have root privileges, since you are logged in as root. This should be obvious given that the SU-apps only run when you are logged in as a root user. The problem with being root is not that apps might escalate their privileges, but that malware has an easy time. – AdHominem Jan 29 '16 at 14:51
						- I'm not sure how it has an easy time if you don't allow it to escalate. – SilverlightFox Jan 29 '16 at 14:58
						- Unix has a directory based access control. Each process runs either in kernel mode or user mode. Processes which are started during boot and login are started as root on a rooted device, and no matter what you do after login (like starting an own, additional access control), they will remain root processes. If these processes have a vulnerability and get exploited, the shellcode runs with root privileges. It's really simple.
				- If your bootloader is unlocked - anything goes (easy to flash any ZIP to system)
				  collapsed:: true
					- However can't reasonable lock bootloader, plus there's other security flaws with LineageOS that can only be avoided by recompiling
				- 1 Backlink
				  collapsed:: true
					- _See_ [Android OS - File-Based Encryption (FBE) - encrypted whilst lock screen on](https://workflowy.com/#/5d03615e5a79)
			- Anonymous SIP providers that accept cryptocurrency - see ((646c8171-0696-40f9-a644-bb14c67a1591))
			- Carrier unencrypted comms (PSTN, SMS, RCS)
			  collapsed:: true
				- Legacy unencrypted comms
				- RCS
					- It basically changes your SMS/MMS to be over IP. This means you get IM-like features in your default SMS app. Things like read receipts, typing indicators, images, video, and audio messages without the automatic carrier compression you see today. Because it's a carrier service/protocol, it also has automatic SMS fallback. Because it's an Internet protocol, you can send messages over WiFi.
					  source:: https://reddit.com/comments/9f7mzy/comment/e5up0gg?context=3
					- Mainly useful in the US or Canada since people in Europe tend to use WhatsApp
					- It's for carriers only, not FOSS
					  [https://9to5google.com/2019/07/30/android-rcs-apis-oems-not-third-party-apps/](https://9to5google.com/2019/07/30/android-rcs-apis-oems-not-third-party-apps/)
						- [https://support.google.com/messages/thread/176392876/when-will-you-release-api-s-to-textra-and-other-to-allow-them-to-support-rcs?hl=en](https://support.google.com/messages/thread/176392876/when-will-you-release-api-s-to-textra-and-other-to-allow-them-to-support-rcs?hl=en)
						- [https://twitter.com/TextraSMS/status/1568128147044057088?lang=en](https://twitter.com/TextraSMS/status/1568128147044057088?lang=en)
						- [https://www.reddit.com/r/androidapps/comments/n69nkd/does_textra_support_rcs/gx6xznn/](http://libreddit.localhost:8080/r/androidapps/comments/n69nkd/does_textra_support_rcs/gx6xznn/)
						- AFAIK APIs still aren't released, so "open source" doesn't mean much then only app that uses RCS is Google messages and other 3rd party apps can't integrate it.
			- Android permissions
			  collapsed:: true
				- User-configurable permissions
					- Pretty good control in [Android 12 / S (2021)](https://workflowy.com/#/b811bc7ac61a)
					- [Bouncer](https://workflowy.com/#/2eb692a67430) can cover other usecases eg limiting Files access duration
				- other manifest and AppOp permissions
					- See [Private clipboard manager](https://workflowy.com/#/6a62be3f07f6) (clipboard permission)
					- See [Firewall](https://workflowy.com/#/9127819b0944) (internet permission)
					- _See_ [XPrivacyLua](https://workflowy.com/#/2f1156481e5a)
					- _See_ [Permission Manager X](https://workflowy.com/#/331f8464bbbe)
					- _Deprecated_
						- LineageOS Privacy Guard
							- alternative to Samsung's app permission monitor which logs with timestamps when a permission was last used
							  source:: https://reddit.com/comments/8wclyd/comment/e1v9cpl?context=3
						- App Ops permission manager
							- https://play.google.com/store/apps/details?id=com.findsdk.apppermission&hl=en_GB
			- SMTP
			- ((649b1407-93b8-4b76-9528-5bf2a10d9870))
			- Phone identifiers
			  collapsed:: true
				- Not accessible by apps in current Android
					- MAC (see [Apps can't access unique hardware identifiers directly](https://workflowy.com/#/f6d2f1127964))
					- Telephony
						- IMSI - SIM card/telco subscriber ID
						  http://en.wikipedia.org/wiki/International_mobile_subscriber_identity
						- IMEI - mobile phone device ID
						  http://en.wikipedia.org/wiki/International_Mobile_Station_Equipment_Identity
			- [Tor Project comments](https://blog.torproject.org/mission-improbable-hardening-android-security-and-privacy#Changes)
			  id:: 649b13cc-b2bd-4baf-ad2b-67e9a502588a
			  collapsed:: true
				- _Existing solutions_
					- Needs many DroidWall rules - was made into orWall but later abandoned
						- orWall https://orwall.org/ - Put your apps behind Orbot and block all unwanted traffic in one go.
					- Copperhead hardened Android
					  https://copperhead.co/android/docs/technical_overview
						- Verified Boot with user-controlled keys
						- Unfortunately, not only is Copperhead the only Android rebuild that supports Verified Boot, but the Google Nexus/Pixel hardware is the only Android hardware that allows the user to install their own keys to retain both the ability to modify the device, as well as have the filesystem security provided by verified boot.
				- Future Work
					- **Completed**
						- Future Work: Port Tor Browser to Android
						  collapsed:: true
							- The Guardian Project is undertaking a port of Tor Browser to Android as part of their OrFox project. This port is still incomplete, however. The Tor Project is working on obtaining funding to bring it on par with the desktop Tor Browser.
						- Future Work: Build Reproducibility (solved by [GrapheneOS](https://workflowy.com/#/ebacd6711d08) reproducible builds)
						  collapsed:: true
							- Copperhead itself is not yet built reproducibly. It's our opinion that this is the AOSP's responsibility, though. If it's not the core team at Google, they should at least fund Copperhead or some other entity to work on it for them. Reproducible builds should be an organizational priority for all software companies. Moreover, in combination with free software, they are an excellent deterrent against backdoors.
							- In this brave new world, even if we can trust that the NSA won't be ordered to attack American companies to insert backdoors, deteriorating relationships with China and other state actors may mean that their incentives to hold back on such attacks will be greatly reduced. Closed source components can also benefit from reproducible builds, since compromising multiple build systems/build teams is inherently harder than compromising just one.
					- _Work in progress_
						- Future Work: Orbot Stability
						  collapsed:: true
							- [https://github.com/guardianproject/orbot](https://github.com/guardianproject/orbot)
							- Unfortunately, the stability of Orbot itself still leaves a lot to be desired. It is fairly fragile to network disconnects. It often becomes stuck in states that require you to go into the Android Settings for Apps, and then Force Stop Orbot in order for it to be able to reconnect properly. The startup UI is also fragile to network connectivity.
							- Worse: If you tap the start button either too hard or multiple times while the network is disconnected or while the phone's clock is out of sync, Orbot can become confused and say that it is connected when it is not. Luckily, because the Tor network access security is enforce by Orwall (and the Android kernel), instabilities in Orbot do not risk Tor leaks.
						- Future Work: Backups and Remote Wipe
						  collapsed:: true
							- Unfortunately, backups are an unsolved problem. In theory, adb backup -all should work, but even the latest adb version from the official Android SDK appears to only backup and restore partial data. Apparently this is due to adb obeying manifest restrictions on apps that request not to be backed up. For the purposes of full device backup, it would be nice to have an adb version that really backed up everything.
							- Instead, I use the export feature of K-9 Mail, Contacts, and the Calendar Import-Export app to export that data to /sdcard, and then adb pull /sdcard. It would be nice to have an end-to-end encrypted remote backup app, though. Flock had promise, but was unfortunately discontinued.
							- Similarly, if a phone is lost, it would be nice to have a cryptographically secure remote wipe feature.
						- Future Work: MicroG support
						  collapsed:: true
							- Instead of Google Play Services, it might be nice to provide the Open Source MicroG replacements. This requires some hackery to spoof the Google Play Service Signature field, though. Unfortunately, this method creates a permission that any app can request to spoof signatures for any service. We'd be much happier about this if we could find a way for MicroG to be the only app to be able to spoof permissions, and only for the Google services it was replacing. This may be as simple as hardcoding those app ids in an updated version of one of these patches.
					- _Minor work_
					- Future Work: Disk Encryption via TPM or Clever Hacks
					  collapsed:: true
						- Unfortunately, even disk encryption and a secure recovery firmware is not enough to fully defend against an adversary with an extended period of physical access to your device.
						- Cold Boot Attacks are still very much a reality against any form of disk encryption, and the best way to eliminate them is through hardware-assisted secure key storage, such as through a TPM chip on the device itself.
						- It may also be possible to mitigate these attacks by placing key material in SRAM memory locations that will be overwritten as part of the ARM boot process. If these physical memory locations are stable (and for ARM systems that use the SoC SRAM to boot, they will be), rebooting the device to extract key material will always end up overwriting it. Similar ARM CPU-based encryption defenses have also been explored in the research literature.
						- Like the last post on the topic, this prototype obviously has a lot of unfinished pieces and unpolished corners. We've made a lot of progress as a community on many of the future work items from that last post, but many still remain.
					- Future work: More Device Support
					  collapsed:: true
						- As mentioned above, installation should work on all devices that Copperhead supports out of the box. However, updates require the addition of an updater-script and an adaptation of the [releasetools.py](http://releasetools.py) for that device, to convert the radio and bootloader images to the OTA update format.
					- Future Work: Netfilter API (or better VPN APIs)
					  collapsed:: true
						- Back in the WhisperCore days, Moxie wrote a Netfilter module using libiptc that enabled apps to edit iptables rules if they had permissions for it. This would eliminate the need for iptables shell callouts for using OrWall, would be more stable and less leaky than the current VPN APIs, and would eliminate the need to have root access on the device (which is additional vulnerability surface). That API needs to be dusted off and updated for the Copperhead compatibility, and then Orwall would need to be updated to use it, if present.
						- Alternatively, the VPN API could be used, if there were ways to prevent leaks at boot, DNS leaks, and leaks if the app is killed or crashes. We'd also want the ability to control specific app network access, and allow bypass of UDP for VoIP apps.
					- Future Work: Fewer Binary Blobs
					  collapsed:: true
						- There are unfortunately quite a few binary blobs extracted from the Copperhead build tree in the repository. They are enumerated in the README. This was done for expedience. Building some of those components outside of the android build tree is fairly difficult. We would happily accept patches for this, or for replacement tools.
					- Future Work: F-Droid auto-updates, crash reporting, and install count analytics
					  collapsed:: true
						- These requests come from Moxie. Having these would make him much happier about F-Droid Signal installs.
						- It turns out that F-Droid supports full auto-updates with the Priviledged Extension, which Copperhead is working on including.
					- Future Work: Baseband Analysis (and Isolation)
					  collapsed:: true
						- Until phones with auditable baseband isolation are available (the Neo900 looks like a promising candidate), the baseband remains a problem on all of these phones. It is unknown if vulnerabilities or backdoors in the baseband can turn on the mic, make silent calls, or access device memory. Using a portable hotspot or secondary insecure phone is one option for now, but it is still unknown if the baseband is fully disabled in airplane mode. In the previous post, commenters recommended wiping the baseband, but on most phones, this seems to also disable GPS.
						- It would be useful to audit whether airplane mode fully disables the baseband using either OpenBTS, OsmocommBB, or a custom hardware monitoring device.
					- Future Work: Wifi AP Scanning Prevention
					  collapsed:: true
						- What
						  collapsed:: true
							- Having a static MAC address makes you fingerprintable
							- Also Your device’s SSID data, which reveals the Wi-Fi names your device trusts.
						- Solutions
						  collapsed:: true
							- MAC address randomised when probing for new Wi-Fi networks (Android 10+)
							  source:: [https://source.android.com/devices/tech/connect/wifi-mac-randomization](https://source.android.com/devices/tech/connect/wifi-mac-randomization)
							- Android 11+: See [Developer option to have a randomised MAC address each time you connect to a network](https://workflowy.com/#/3c545e3cd340)
							- Android Settings > Location > Wi-Fi and Bluetooth Scanning > keep both settings off so it doesn't scan when it's off
						- Copperhead may randomize the MAC address, but it is quite likely that it still tries to connect to configured APs, even if they are not there (see these two XDA threads). This can reveal information about your home and work networks, and any other networks you have configured.
						- There are a few apps but we have not yet had time to audit/test either. Any reports would be useful here.
						- Abandoned apps
						  collapsed:: true
							- Wifi Privacy Police App (last updated 2016) - hides the names of what Wi-Fi networks you're trying to connect to, plus has better phishing protection
							  collapsed:: true
							  [https://f-droid.org/packages/be.uhasselt.privacypolice/](https://f-droid.org/packages/be.uhasselt.privacypolice/)
								- It prevents your smartphone from sending out the names of Wi-Fi networks it wants to connect to over the air. This makes sure that other people in your surroundings can not see the networks you’ve connecte to, and the places you’ve visited.
								- If your smartphone encounters an unknown access point with a known name (for example, a malicious access point pretending to be your home network), it asks whether you trust this access point before connecting. This makes sure that other people are not able to steal your data.
							- Smarter Wi-Fi Manager (last updated 2016) - WiFi is only enabled when you are in a location you have previously used WiFi
							  [https://f-droid.org/packages/net.kismetwireless.android.smarterwifimanager/](https://f-droid.org/packages/net.kismetwireless.android.smarterwifimanager/)
					- Future Work: Better SIP Support
					  collapsed:: true
						- Right now, it is difficult to use two or more SIP clients in OrWall. You basically have to switch between them in the settings, which is also fragile and error prone. It would be ideal if OrWall allowed multiple SIP apps to be selected.
						- Additionally, SIP providers and SIP clients have very poor support for TLS and SRTP encryption for call setup and voice data. I could find only two such providers that advertised this support, but I was unable to actually get TLS and SRTP working with CSipSimple or LinPhone for either of them.
					- Future Work: Installation and full OTA updates without Linux
					  collapsed:: true
						- In order for this to become a real end-user phone, we need to remove the requirement to use Linux in order to install and update it. Unfortunately, this is tricky. Technically, Google Play can't be distributed in a full Android firmware, so we'd have to get special approval for that. Alternatively, we could make the default install use MicroG, as above. In either case, it should just be a matter of taking the official Copperhead builds, modifying them, changing the update URL, and shipping those devices with Google Play/MicroG and the new OTA location. Copperhead or Tor could easily support multiple device install configurations this way without needing to rebuild everything for each one. So legal issues aside, users could easily have their choice of MicroG, Google Play, or neither.
						- Personally, I think the demand is higher for some level of Google account integration functionality than what MicroG provides, so it would be nice to find some way to make that work. But there are solid reasons for avoiding the use of a Google account (such as Google's mistreatment of Tor users, the unavailability of Google in certain areas of the world due to censorship of Google, and the technical capability of Google Play to send targeted backdoored versions of apps to specific accounts).
					- Future Work: Better Boot Key Representation/Authentication
					  collapsed:: true
						- The truncated fingerprint is not the best way to present a key to the user. It is both too short for security, and too hard to read. It would be better to use something like the SSH Randomart representation, or some other visual representation that encodes a cryptographically strong version of the key fingerprint, and asks the user to click through it to boot. Though obviously, if this boot process can also be modified, this may be insufficient.
					- Future Work: Faster GPS Lock
					  collapsed:: true
						- The GPS on these devices is device-only by default, which can mean it is very slow. It would be useful to find out if [µg ](https://workflowy.com/#/cafeea2a4f61)<a href="https://workflowy.com/#/cafeea2a4f61">Unified</a><a href="https://workflowy.com/#/cafeea2a4f61">Nlp</a> can help, and which of its backends are privacy preserving enough to recommend/enable by default.
						- See [OpenCellID/radiocells](https://workflowy.com/#/4379eb362876)
					- Future Work: Sensor Management/Removal
					  collapsed:: true
						- As pointed out in great detail in one of the comments below, these devices have a large number of sensors on them that can be used to create side channels, gather information about the environment, and send it back. The original Mission Impossible post went into quite a bit of detail about how to remove the microphone from the device. This time around, I focused on software security. But like the commentor suggested, you can still go down the hardware modding rabbithole if you like. Just search YouTube for teardown nexus 6P, or similar.
				- Initial post https://blog.torproject.org/blog/mission-improbable-hardening-android-security-and-privacy
			- Dating risks
			  collapsed:: true
				- ((6447c671-0b43-4a05-97b5-b742eea57575))
				- Multiple privacy settings with a secondary WhatsApp
					- Use secondary WhatsApp (Shelter/Android for Work) with limited access to contacts
					- VoIP phone number bought with cryptocurrency
					- _See_ [AFWall](https://workflowy.com/#/e5f2eed18186)
					- VPN/Orbot (Tor)
				- See [Dating privacy](https://workflowy.com/#/1fa5d32c144c)
			- What happens when your phone no longer receives security updates - you lose firmware updates
			  collapsed:: true
				- With a tiny handful of exceptions, it really isn't a big deal
					- Almost every kernel and driver bugs require malicious code to have already successfully exploited and own userspace before the higher priv bug becomes an issue. So exploiting kernel, driver and firmware bugs is already a lot more complex by that barrier alone. As unless you're being specifically targeted, it is very very difficult and not particularly cost effective to figure out a full exploit path to kernel space. it's infinitely more cost effective, and rewarding to the attacker to just get their code installed in userspace, since the OS already provides valid ways to remain persistent.
					- Most malware these days just quietly "click" ads in the background to scam ad cdns or spam the user with ads anyways. Don't need kernel space for that.
					- This is why Android 10's project mainline is so interesting to me. It's google's solution to make sure userspace, the most important area in the OS these days, stays patched.
			- Project Pegasus by NSO Group
			  collapsed:: true
				- Intrusion methods
					- Forensic analysis of the exploit
					  [https://www.amnesty.org/en/latest/research/2021/07/forensic-methodology-report-how-to-catch-nso-groups-pegasus/](https://www.amnesty.org/en/latest/research/2021/07/forensic-methodology-report-how-to-catch-nso-groups-pegasus/)
					- ((663b24fb-f1f2-4dbe-ae47-d3a910654835)) stuff
						- A few months ago, it was a WhatsApp vuln that was exploited. Only a WhatsApp phone call could inject spyware in your phone (cve-2019-3568) without any need to answer. Spyware could use cam/mic, analyse mails, and use location info…
					- iMessage
					- Android exploits are more expensive than iOS
					  [http://zerodium.com/images/zerodium_prices_mobiles.png](http://zerodium.com/images/zerodium_prices_mobiles.png)
						- Zerodium paused paying out iOS bounties
						  [https://lifars.com/2021/01/current-state-of-zero-day-exploit-market/amp/](https://lifars.com/2021/01/current-state-of-zero-day-exploit-market/amp/)
		- _Solutions_
			- Pretty Good Phone Privacy (PGPP)
			  id:: 62f55393-cfe7-4bd5-8986-88ab1ab875ec
			  collapsed:: true
			  [[2024-06-03 Monday]] [Shutting down](https://invisv.com/articles/service_shutdown.html)
				- Pros/Cons
					- Pros
						- If they're telling the truth then they use PGPP to not store info on your IMSI
							- IMSIs are what are associated with your identity (because it's your SIM and service) in a normal mobile plan, and it's what was (is?) used by carriers when they aggregate / analyze / sell location data.
					- Cons
						- Still tracks IMEI (e.g. for stolen phones database EIR)
							- IMEIs can be queried by a network core (not the tower) and US carriers probably do this every once in a while to check against their stolen phone database. It can be changed on some devices but not others. It's not inherently tied to you as a person but of course it is tied to that device.
				- ((62f557ed-0f88-48e8-96ef-bef83f95ad53))
			- Encryption-at-rest for all apps (like andOTP, Signal)
			- Proper virtualisation i.e. ((635037c3-993a-4bfc-9c65-2157fd59a626))
			- ((66051aab-a6ac-4db3-92db-63e21eb0838c))
			- _Poor solutions_
				- Use a cover on front + rear camera (e.g. reusable black vinyl)
					- Instead ((649b13d1-a358-4221-b66e-37cdb5da82ea))
				- ((649b13cc-87bb-4662-b326-9259cfec38d4))
	- Troubleshooting
	  collapsed:: true
		- [[2025-04-30 Wednesday]]  [Unresponsive and black screen after boot · Issue #5249 · GrapheneOS/os-issue-tracker · GitHub](https://github.com/GrapheneOS/os-issue-tracker/issues/5249)
		  id:: 6811cc50-0948-4a4a-8d0e-f40c205da86b
			- Holding down the power button for 60+ seconds managed to restart the phone.
		- Phone issue - ((6318fc66-9d9f-4547-8e1c-172958500c0d)) not working
		  collapsed:: true
			- Have tried
				- Flashing a new GApps
				- Flashing same GApps
			- To do
				- Wait until next LineageOS OTA update released on 10th or so and install that. Then flash Magisk and boot into system
				- Uninstall any remaining non-system Google stuff like Play Store or anything that lingers
				- Then flash GApps again#
				- New
					- DONE install Magisk + try to TWRP backup /data
					  :LOGBOOK:
					  CLOCK: [2022-09-11 Sun 18:22:17]--[2022-09-11 Sun 18:22:18] => 00:00:01
					  :END:
					- NOW run backups using Neo Backup + ((63216f53-22cf-428a-9193-e5a423158e2b))
					  :LOGBOOK:
					  CLOCK: [2022-09-11 Sun 18:22:28]
					  :END:
					- LATER try to install LiveBoot
			- Related: ((631b4654-9823-4293-b5c4-1417299c0a06))
		- [[2023-02-17 Friday]] How to enable data roaming on Xiaomi Pocophone F1
			- **Solution:** Android 12 Settings > Network and Internet > SIMs > Access point names > select `iD Mobile (UK) - id`
			- Customer service tech advice
			  collapsed:: true
				- You can follow the steps below to get internet and MMS working:
				- Open Settings from the Home screen.
				- Tap Wireless and networks or More (this will depend on your Android version).
				- Tap Mobile networks > Access point names.
				- Tap the Menu button (this could be the lower left soft key, 3 dots in the top right corner, or the word 'more').
				- Tap New APN.
				- Type the following:
				- Name: iD
				- APN: id
				- MMSC: http://mms.um.idmobile.co.uk:10021/mmsc
				- MMS Proxy: mms.idmobile.co.uk
				- MMS Port: 8799
				- APN
				  Type: You'll need to choose from a list or type something in. If you're
				  given the list, choose internet+mms. If you're asked to type something,
				  type in a \*
				- Tap Menu > Save.
				- Pick the name we've just created.
				- Next to your signal bars, you'll now see 4G, 3G, H, E or G. This shows you're now connected.
				  
				  You can also see more information about using your phone abroad click on the link below:
				  
				  [International and Roaming](https://www.idmobile.co.uk/help-and-advice/international-and-roaming)
	- **UNSORTED**
		- ((649b1407-93b8-4b76-9528-5bf2a10d9870)) / ((630f9707-836b-4814-8d7d-0ce9109fc35d))
		- Basics
		  collapsed:: true
			- Consider
			  collapsed:: true
				- Stingle Photos
					- [https://stingle.org/](https://stingle.org/)
					- Stingle Photos (Stingle Photos is a secure, end-to-end encrypted gallery and sync app) - [https://f-droid.org/packages/org.stingle.photos](https://f-droid.org/packages/org.stingle.photos)
					- https://github.com/stingle/stingle-photos-android
					- Similar to Cryptee?
			- Recording all communication automatically + backup online
			  collapsed:: true
			  avoiding False Rape Accusations
				- Automatically records all phone conversations and text messages.
					- See [Call](https://workflowy.com/#/3b40b1b5144b)<a href="https://workflowy.com/#/3b40b1b5144b"> </a><a href="https://workflowy.com/#/3b40b1b5144b">record</a><a href="https://workflowy.com/#/3b40b1b5144b">ing</a>
					- Text messages - https://play.google.com/store/apps/details?id=com.riteshsahu.SMSBackupRestore + addon
					- Dropsync or Folder Sync for phone calls and text messages if inbuilt cloud backup doesn't work
				- Android Google account backup
				- Location GPS tracking - alibi sousveillence via Android app
					- Google account linked to the phone records my location every 5 minutes so I have alibi in case of a false rape accusation. I leave it connected to a cigarette lighter socket in my car and rarely bring it home. I use no other phone to engage in hoe-banging activities.
					- _Open-source apps_
						- TinyTravelTracker
						  collapsed:: true
							- https://f-droid.org/repository/browse/?fdfilter=location&fdid=com.rareventure.gps2&fdpage=3
							- Requires manual exporting prior to USB backup
							- - Buggy and no web GUI
						- μlogger
						  collapsed:: true
							- (Log position to your own server) - https://f-droid.org/app/net.fabiszewski.ulogger
							- [cloned] https://github.com/bfabiszewski/ulogger-android.git
						- OwnTracks
						  collapsed:: true
							- [cloned]
							- OwnTracks already exists, has multiple tracking modes, handles geofencing, handles iBeacons and sends data into an MQTT server that's trivial to run.
							- Owntracks just throws things in MQTT that you then pull out with any number of libs.I'm fairly certain that what comes out is JSON but haven't addressed it at that level yet. Once there you could store anything you wanted, any way you wanted.The interesting part of Owntracks is that you can tell it "Where I'm at right now is a location I want to track, flag any record within a 250m circle of this." and that location name comes along for the ride in the data stream.There's also elevation, speed, and battery life.
						- LOCH/locory
						  collapsed:: true
							- [cloned] https://github.com/berrnd/locory.git
				- WhatsApp auto backup to Google Drive
				- Manual
					- Weekly backups via USB
		- Threat Levels
		  collapsed:: true
			- collapsed:: true
			  1.  Discrete Polyamory
			      collapsed:: true
				- To DO
					- In UK, almost all chat is via WhatsApp
						- Hide WhatsApp
						- Hide gallery picspictures from WhatsApp
							- Use F-Droid gallery app + hide most folders
						- Hide notifications
				- Systems
					- Use desktop + TrueCrypt for as much functions as possible
					- BlueStacks. Online dating
					- Possibly get a second phone
					- One Phone Method
					  collapsed:: true
						- Privacy screen protector
						- Hide apps via Covers + premium Hidden Apps setting
						- Action Launcher 3. OR AppLock
						- Hide calls and texts
							- VoIP apps
							  #Software [VoIP](https://workflowy.com/#/d03d7e27b3ef)
							- Filter calls and texts from specified contacts into an app
							  Much longer than just using a VoIP app
								- Android 'Shelter' (Work profile) + whitelist only certain SMS/phone calls to the Shelter profile app
								- Android apps
								  collapsed:: true
									- Whitelist Call Blocker
									  https://play.google.com/store/apps/details?id=de.tn_software.callblocker&hl=en
									- CATE
										- (the Call and Text Eraser) hides texts and calls from certain contacts and boasts tricky features such as the ability to “quick clean” incriminating evidence by shaking your smartphone.
									- https://play.google.com/store/apps/details?id=com.thinkyeah.privatespacefree
									- https://play.google.com/store/apps/details?id=hazar.studio.privatecontacts
								- Related: Japanese infidelity phones
								  collapsed:: true
								  Hides missed calls, texts and emails from specified contacts with only a subtle indicator. Press a combination of keys to open
									- Fujitsu's ageing F-Series flip phones
									  hides missed calls, emails and texts from any contacts that are designated as private.
										- nicknamed the 'uwaki keitai' of 'infidelity phone' - are the mobiles of choice for customers who believe newer versions are not as discreet at hiding their affairs.
										- They feature a nearly invisible 'privacy mode' that **hides missed calls, emails and texts from any contacts that are designated as private.**
										- The only indication that such a person has got in touch is a subtle change in the colour of shape of how the battery level icon of the network signal antenna bars are shown.
										- A secret combination of keys is needed to turn off the privacy mode, revealing the concealed calls and messages and making voicemail available.
										- Secrets: The phones feature a nearly invisible 'privacy mode' that hides missed calls, emails and texts from any contacts designated as private
										- A Japanese pick-up artist and blogger who goes by the name Bakanabe, said he uses the phone because women he's seeing might try to check his phone for strange calls or emails when he's not around.
										- 'With Fujitsu's "privacy mode", they can't see that information at all. The key is to give off the impression that you're not locking your phone at all,' he told the Wall Street Journal.
										- Fujitsu's F-06D, in 'Innocent White': The F-series range of Fujitsu smartphones has been dubbed the 'infidelity phone' for a range of features that love cheats use to hide their affairs
									- DoCoMo phones
										- also had the privacy features that make them still popular as "infidelity phones."
						- Lock any app with AppLock
							- ☞ AppLock can lock Facebook, Whatsapp, Gallery, Messenger, SMS, Contacts, Gmail, Settings, incoming calls and any app you choose. Prevent unauthorized access and guard privacy. Ensure security.
							- ☞ AppLock can hide pictures and videos. Hidden pictures and videos are vanished from Gallery and only visible in the photo and video vault. Protect private memories easily. No pin code, no way.
						- Hide photos and videos
							- Vault app
								- Calculator theme, which hides photos and videos inside a virtual vault within one’s phone that’s disguised to look like a calculator app
							- AppLock
							- Dropsync - upload then delete
							- Gallery app - hide folders
						- Container apps (Shelter for a 'Android for Work' second profile)
						- Hide emails,
							- Samsung My Knox, Parallel Space, 2Accounts, App Cloner etc
				- {Archive}
					- Datasheets
						- [archived] https://www.rooshvforum.com/thread-45506.html
			- collapsed:: true
			  2.  Advanced: Law enforcement
			      collapsed:: true
				- Clandestine Mobile Phone Use
				  collapsed:: true
					- Mobile phones should primarily be used for signalling, rather than for actually communicating operational information. Remember the golden rule of telephone conversations:
					  collapsed:: true
						- keep it short
						- keep it simple
						- stick to your cover
					- Mitigations
					  collapsed:: true
						- Turn it OFF, for real.
						- Know how to turn the phone to a completely off state. This means removing the battery, taking out the SIM card and placing in a shielded bag (if possible). This really off state is how you store and transport the phone when not in use.
						- A note on storage: it should not be at your house or anywhere that is directly linked to you.
					- Hiding location
					  collapsed:: true
						- Location
							- Specific location (home, place of work, etc.)
							- Mobility pattern (from home, via commuter route, to work) – very unique, 4 loc’s will identify 90%
							- Paired mobility pattern with a known device (known as “mirroring”, when two devices or more devices travel together)
						- Where you use the phone is itself very important. Never use it at locations which are associated with you, that means never at home, never at the office/work, never at a friend’s house. Never have the phone in an ON state at locations that are associated with you, or your immediate social network. Never.
						- Do not turn the phone in the same location as a phone associated with you. Make sure that your real phone is somewhere else, but not in an OFF state if possible. You don’t want the disappearance of one phone from the network to coincide with the appearance of another. Paired events are indicators of relation, and you want to avoid those as much as possible. You also want you regular phone to appear with a typical usage pattern, which means keeping it on as you normally would.
					- Contamination, avoid it
					  collapsed:: true
						- Never use different phones from the same location.
						- Never carry phones for different compartments together (keep them turned off, batteries out)
						- Never carry phones turned on over the same routes you normally take. Avoid patterns and predictability.
				- Bad CIA OPSEC
				  collapsed:: true
					- OPSEC
						- Dedicated mobile phone The agents had a mobile phone used specifically for communication with their handler. This phone was kept in a static location waiting for contact, and possibly spent a lot of time switched off.
						- Pre-arranged meeting place The agents had a meeting location (allegedly at a Pizza Hut) where they met their handlers. This location was (allegedly) reused for multiple agents and multiple meetings.
						- Signalling code word Contact by the handler to the agent was via a code word (allegedly: “PIZZA!”), which was meaningless by itself but also contextually anomalous.
					- The adversary, Hezbollah, used access to the telephone company logs (they have those), and searched for atypical mobile phone usage patterns:
						- phones that only receive a few calls / messages over long periods of time
						- mobile phones that are never mobile
						- weird / unusual messages (PIZZA!!)
					- That is, they were looking for phones that were kept at home, turned on occasionally, and only received calls/sms infrequently. The exact usage pattern one would expect for a mobile that is used exclusively for a handler to contact an agent.
					- This data gave Hezbollah a general location (down to the apartment complex) of where the agents were located. Next, the adversary correlated the location data with the home addresses of members who had access to secret information. They conducted surveillance on those members and discovered they were using a Pizza Hut to meet with their handlers.
					- Speculation Finally, the adversary was able to continually monitor the meeting location and detect other members of the spy network meeting with their handlers. The CIA is known for over using the same locations for meetings [1].
					- The problems with these tradecraft practises are pretty obvious from a counterintelligence analysis. They are anomalous (atypical mobile phone use) and they are rigidly predictable (reusing the same meeting location).
					- For encryption applications used by anti-government forces this provides a clear blueprint for action - look normal. Even basic monitoring of traffic will reveal anomalous activity which can be used to identify who needs to be watched more closely.
					- Hiding anomalous activity is hard, but vitally important. The problem with many security systems based purely on secrecy is that their usage is itself anomalous. It singles out and attracts attention to the users. If the adversary doesn’t know who those users are initially, they can cross correlate real world data with the suspicious activity and narrow their focus to real people. Those people can, and will, end up dead.
				- Burner phone best practices
				  collapsed:: true
					- There’s a good mix of useful and mis-information in regard to burner phones out there. I thought I would compile some facts and review the proper use-case for a burner phone.
					- Tracking: Fingerprinting
						- Burner phones, for both CDMA (US Sprint, US Verizon Wireless) and GSM (Ever other carrier network in the world), are easy to trace. Carriers specifically segregate burner/prepaid traffic from normal subscriber traffic. Yes, this is primarily used to control which type of traffic should receive priority, but it’s used by LEOs to easily identify network traffic used by targets.
						- Bruce Schneier recently commented on what the NSA is actively doing in regards to burner phones. In a recent lawsuit between the NSA and the EFF, the court documents show that one of the ways the US keeps track of burner traffic, is by fingerprinting the number of unique contacts, and the times of the calls. With this information, it’s much easier to keep track of whose phone is whose.
						- For example, Joe talks to John, George, and Jimmi on a daily basis. He cycles through burner phones at least once a week. For each phone, Joe adds the contact information for John, George, and Jimmi and calls only them. Joe stops never re-uses a burner phone.
						- From this information, we can easily track his first burner’s contact (namely John, George, and Jimmi) because this information is stored on the SIM (http://www.forensicswiki.org/wiki/SIM_Cards), and correlate it to the contacts used by the next burner phone. How hard would it be for law enforcment to trace this information? Turns out not very hard if you’re a subject of interest.
					- Tracking: Location
						- There are two parts to the location of your burner you need to be aware of. First, carriers maintain logs of the signal strengh between your phone and a carrier tower/base station. With this information they can http://www.al911.org/wireless/triangulation_location.htm. On your smart phone this is considered your “Course-Grain” location as opposed to “Fine-Grain” that the GPS in your smartphone provides.
						- The second location to think about here is the location used to register/activate the phone in the first place. For American burners, they are required to call into a toll-free number and setup their new phone using a name, address, and secret password. Of course this information is not verified and can be easily spoofed. But the phone number used to activate the account, is forever associated to that device.
					- When not to use a burner
						- hiding from a national adversary: If you think the government is after you, there’s really not much a burner phone is going to help you with. They can pull up security camera footage of when you purchased the phone, they can map all the locations in which you’ve powered on the device, they can watch the calls being made by a variety of burners and correlate them all together.
						- near your home: Every time you power up, that information is logged. If you decide to constantly turn on your device in or around our apartment, it is very easy for even local law enforcement to find you
						- calling someone you know that does not use a burner: If all you’re going to do is call Jimmy down the street, it’s easy to correlate your activities across multiple burners because the destination address never change. It becomes a bit harder if Jimmy changes his phone number at the same time you change yours.
						- registering for a gmail address: you might think it’s a good idea to setup a burner to make a new email address but while it can be, you also have to be careful with how you use that address, and where you registered your phone. If you buy a phone in London, and then pretend that you’re in Brazil for all of your email correspondence, this will be a red flag for investigators. Make sure you remember what that phone will be for.
					- When is a burner useful
						- hiding from non-law enforcement: If your goal is to just make sure that no one you know can find your name or home address, a burner is useful.
						- registering for inconsequential accounts: If you just need to register an account, but aren’t concerned about being tracked back to its activity, you can use a burner as an alternative to registering with a pay phone or something else.
					- Pro tips
						- Get feature/dumb/flip-phones rather than smart phones. iOS, Android (or whatever other OS you choose) is not interested in keeping track of your privacy. Feature phones have the benefit of being generally too stupid to leak information about you.
						- Never turn your phone on in, or around your home. Take the battery out when it’s not being used.
						- Leave your phone at a place you’re going to use it to make sure it never gets turned on at your home
						- If possible, pay someone else to activate the phone for you. This is a way of removing yourself from the activation process completely. There are some burner trading sites on the deep web.
						- Fill your phone with fake contacts. Each burner should look like it has a different set of contacts in it.
						- Never save your real contacts in the phone. Put them on paper, or on a separate device, but never on the phone. This information is potentially saved on the SIM and accessible to carriers.
						- Pad operational calls with random calls. Dial numbers you don’t know, leave messages, call tech support, send an SMS. Make it difficult to differentiate between your operations and random activities.
						- Use a burner as little as possible before switching to the next one.
						- If purchased from a retail store, wait at least 60 days to activate. This is usually how far back mom and pop stores keep security footage.
						- Activate from a payphone as far away from home as possible, or at least in the area where you will be using it most often
						- Dispose of burner phones completely. Don’t recycle them or throw them away in your apartment garbage. They should be destroyed completely, electronically wiped, and physically wipe down.
		- Google Location History alternative
		  collapsed:: true
			- Traccar
			  https://f-droid.org/app/org.traccar.client
		- DEFUNCT: Enable different encryption wake and lock screen passwords (e.g. long wake passphrase, PIN for lockscreen)
		  collapsed:: true
			- Separating boot encryption password and lock screen security
				- Cryptfs and SnooperStopper don't work anymore due to File-Based Encryption?
				  source:: [https://github.com/GrapheneOS/os_issue_tracker/issues/28#issue-427352435](https://github.com/GrapheneOS/os_issue_tracker/issues/28#issue-427352435)
			- [https://github.com/xmikos/SnooperStopper](https://github.com/xmikos/SnooperStopper)
				- Or
				- [https://play.google.com/store/apps/details?id=org.nick.cryptfs.passwdmanager](https://play.google.com/store/apps/details?id=org.nick.cryptfs.passwdmanager)
		- Android lock screen protection
		  collapsed:: true
			- Enforce maximum failed unlock attempts
				- Wrong Pin Shutdown
					- 1-5 attempts before shutting down
					- October 2017 - set to 4
		- Deniable encryption - Android equivalent to VeraCrypt hidden containers
		  id:: 649b13cc-87bb-4662-b326-9259cfec38d4
		  collapsed:: true
			- Examples
				- Mobiflage
				  collapsed:: true
					- http://users.encs.concordia.ca/~mmannan/student-resources/Thesis-MASc-Skillen-2013.pdf
					- https://www.ccsl.carleton.ca/~askillen/mobiflage/
					- GitHub link
				- MobiHydra
				  collapsed:: true
					- http://www.chenirvine.org/publications/MobiHydra_technical_report.pdf
				- Mobipluto
				  collapsed:: true
					- http://www.cs.wayne.edu/fengwei/paper/mobipluto-acsac15.pdf
				- [DueProcess](https://github.com/brnhrd/DueProcess) (2021)
				  id:: 649b13cc-2a74-4519-8841-bbc386eac1a2
				  collapsed:: true
				  deniable encryption for apps on via work profile modern Android
					- Pros/Cons
						- Pros
							- Built for Android 10
						- Cons
							- Not maintained
							- The secret swipe pattern has a little unreliable detection
					- `/home/boss/Documents/Git/Categories/Privacy/DueProcess`
					- [https://android.ins.jku.at/plausible-deniability/](https://android.ins.jku.at/plausible-deniability/)
					- With the increase of invasive phone searches, and the massive hassle if you don't cooperate, I think plausible deniability will be very helpful in protecting our rights in the future.
					- This app uses the work profile feature of Android to encrypt and hide apps and data in a separate profile. Additionally, the app will also hide itself under lockdown mode. The result is that you can unlock your phone and let someone else handle it while still securely hiding private data from them, without them realizing you're hiding something.
					- The protection is not perfect, and may not hold up to highly sophisticated attackers if you are a target of special scrutiny. But it can help most average Joes go under the radar during regular invasive searches, e.g. at airport/border security. And within the current limitations of Android, this is pretty much as good as you can get out of a convenient app-based solution.
					- Desktops have had tools for plausible deniability like TrueCrypt hidden volumes, but this seems to be the first mobile solution of it's kind and I hope it inspires more work in this area.
					- Disclaimer: I didn't make this, just found something useful and wanted to share it. This app was the Master's thesis project of Bernhard Gründling, and as a result it's particularly well though out and well documented.
					-
					- Submitted
					  [https://github.com/privacyguides/privacyguides.org/pull/79](https://github.com/privacyguides/privacyguides.org/pull/79)
			- _Threat model_
				- Forced to unlock phone but they only have time or rules to run a full image
			- _Potential solutions_
				- EDS app to unlock folders
				- Android apps with an encrypted database and pin to unlock app; and using a different pin unlocks a different database
				  collapsed:: true
					- Cons
						- Each app needs to implement this separately and that's not feasible especially when many of the most important are proprietary
					- _Apps with sensitive info_
						- _Proprietary_
							- WorkFlowy
							- Dynalist
							- Airtable
							- WhatsApp, [Discord](https://workflowy.com/#/776244a9838b), Telegram, Riot, Slack
							- See [Tinder](https://workflowy.com/#/1d745abfd07e)
						- _FOSS_
							- RedReader
							- GnuCash
							- Face Slim
							- Firefox
							- Contacts
							- ((649b13ce-1fe5-4f94-b330-5dcef6fb807e))
							- QKSMS (though I could use Signal)
						- _Own_
							- ((63734c9f-69e2-48d3-850d-318fb3cd7230))
				- Xposed MaxLock? to lock settings with a PIN, as well as apps or launchers or app list pills
				- Proper FBE encryption like iOS
				- Linux-based mobile OS that allows multi-user login (Android's implementation always runs both users)
				- Hidden second mobile OS
				  id:: 649b13cc-df3a-48f6-90f9-9670460fc209
				  collapsed:: true
					- Why I think it's poor now
						- Because it requires the device to be depowered. Better is first aiming for all apps to be encrypted at rest (like andOTP or Signal)
					- Cons
						- The problem is phones are 99% of the time left turned on, and these hidden OS normally require rebooting to go into
					- By Year
						- Mobiflage: Deniable Storage Encryptionfor Mobile Devices
						- MobiHydra: Pragmatic and Multi-Level Plausibly Deniable Encryption Storage for Mobile Devices (2014)
						  collapsed:: true
							- MobiHydra [11] has expanded Mobiflage by supporting multiple levels of deniability, which enables data transfer between two modes across a specific cache partition and mitigates the booting time attack of Mobiflage.
						- MobiPluto: File system friendly deniable storage for mobile devices (2015)
						  collapsed:: true
							- MobiPluto [12] is another PDE original system that implements linear allocation space using a LVM (logic volume management) tool to avoid modifying the Ext4 driver, and it also enables multiple levels of deniability (multiple hidden volumes). However, these original systems have some common defects because they share the same pedigree, such as the boot time being longer than the normal android boot time (i.e., booting time attack), corruption of the across boundary of the volume, and so on.
						- MobiMimosa: Personal Privacy Protection Framework Based on Hidden Technology for Smartphones (2017)
						  collapsed:: true
							- https://ieeexplore.ieee.org/document/7903654/
							- MobiMimosa uses data partitions in its outer volume (or called public volume) to store the regular data of users. The hidden volume locates the second half of the public volume and is used to store the sensitive data of users. When enabling multiple hidden volumes, a hidden volume could locate another partition (e.g., a cache partition). Users are allowed to use any encryption algorithm that the android kernel enables to encrypt the hidden volume. We also improve mode of data transmission between two volumes. This is necessary due to android security framework. In the android system, data of an application can only be stored into its installing directory or emulated Sdcard.
						- MobiCeal: Towards Secure and Practical Plausibly Deniable Encryption on Mobile Devices (2018)
						  collapsed:: true
							- A proof of concept implementation of MobiCeal is provided on an LG Nexus 4 Android phone using Android 4.2.2. It is shown that the performance of MobiCeal is significantly better than prior PDE systems against multi-snapshot adversaries.
					- Newest
			-
	- More
	  See local KDB #AndroidPhone-INFOSEC
- Phone Hardware
  id:: 649b13cc-cb87-4eac-8f9f-5c130d3d21c1
  collapsed:: true
	- _Current phones_
		- ((65339b44-e96d-4207-861c-38bebfe53a5f)) (purchased Q4 2024)
		  id:: 679ddfab-0db4-4b3d-9bf8-8614f6528e17
		- [Xiaomi Pocophone F1](https://www.gsmarena.com/xiaomi_pocophone_f1-9293.php) (2018)
		  id:: 649b13cc-23ea-4398-8dcb-488f7f9c55e6
		  collapsed:: true
		  AKA Poco F1
			- Pros/Cons
				- ## Pros
				- ## Cons
				- Unclear
				- Comparisons
					- ((649b13cc-23ea-4398-8dcb-488f7f9c55e6)) vs ((65339b44-e96d-4207-861c-38bebfe53a5f)) (started [[2024-03-08 Friday]] )
					  id:: 65ead18e-8bd9-41e4-8d68-f25fe63890ba
						- For ((649b13cc-23ea-4398-8dcb-488f7f9c55e6))
							- Familiarity
							- Still supported by ((630f96f0-f2c4-4706-9d72-58e13201e03f))
							- I'm currently reliant on ((63209284-e6f8-47bd-a47c-e2733cf7b886)) + multiple rooted backup apps, not sure if ((6318fc65-99f9-4edb-a705-eb1deb420890)) is comparable
						- For ((65339b44-e96d-4207-861c-38bebfe53a5f))
							- ((63209286-6f40-4063-9fdc-2543251d416e)) support
							- Bigger storage up to 256GB - my current 64GB is hampering me
							- ((63219e34-cda2-4a69-a2c8-b74b33cf9a91)) so I can use ((64e0946d-1d0e-4824-b150-1a08f26aba23))
							- Much better camera, CPU, RAM (8 > 6)
							- Fresh new battery
							- ((649b13d1-99cb-442b-805c-40a7c0424493))
						- Similarities
							- Same size as ((649b13cc-23ea-4398-8dcb-488f7f9c55e6)), a bit too bit big tbh
						- Unclear
							- ((63209286-6f40-4063-9fdc-2543251d416e)) : ((635037d0-d4a1-49cc-b9bc-13a5b4f970c5))
								- {{embed ((635037d0-d4a1-49cc-b9bc-13a5b4f970c5))}}
						- Conclusion
							- ((6318fc65-99f9-4edb-a705-eb1deb420890)) :
			- _Purchased device info_
				- £310 via eBay. Includes 12 month UK-based warranty via the seller
				  Purchased October 2018?
			- _Journal_
				- Thu, Apr 1, 2021 - moved to LineageOS 18.1 (with microG) as primary phone
				- Tue, Dec 1, 2020 - try [LineageOS for microG](https://workflowy.com/#/1abc0e737ad8) as my daily driver
				  collapsed:: true
					- Why
						- I have barely tested microG at all, but I am pretty happy with LineageOS on my [Google Pixel 1](https://workflowy.com/#/96f310804583) nowadays
						- My [Google Pixel 1](https://workflowy.com/#/96f310804583) battery life is pretty bad now after daily use
					- Ordered 256GB microSD to install new OS on since current microSD is only 64GB and I'm used to 128GB on Pixel 1. Arriving Saturday
					- My steps
						- sudo snap stop anbox - so it doesn't interfere with selecting the correct adb device
						- Vol button up + lock button to boot into Recovery (TWRP already installed)
						- ADB Sideload
							- Flashed the lateste Xiaomi firmware (otherwise LineageOS doesn't install)
								- Download from here
								  [https://xiaomifirmwareupdater.com/](https://xiaomifirmwareupdater.com/)
								- adb sideload firmware-v10_beryllium_miui_POCOF1Global.zip
					- **Next**
						- Download latest device-specific [LineageOS for microG](https://workflowy.com/#/1abc0e737ad8) image
						  [https://download.lineage.microg.org/beryllium/](https://download.lineage.microg.org/beryllium/)
						- Download latest device-specific TWRP recovery
						  [https://twrp.me/xiaomi/xiaomipocophonef1.html](https://twrp.me/xiaomi/xiaomipocophonef1.html)
						- _See_ [Flash TWRP as a recovery](https://workflowy.com/#/3f4dc2bfe282)
						- _See_ [Setting up microG](https://workflowy.com/#/6af7417dcd1f)
					- _See_ [microG](https://workflowy.com/#/5b760a9e66c3)
					- _See_ [Generic System Image (GSI)](https://workflowy.com/#/0c7ccf914447)
				- _{Archive}_
					- Q1? 2019 - LineageOS 16 with GApps
					- Q4 2019 - LineageOS 16 with microG
					- Q1 2019 (planned) - LineageOS 17 once it's available, plus NanoDroid so I can get in-app purchases working with microG
			- Rooted to-do
			  id:: 644c0acb-0208-4ff7-8e23-8b7c7c74346a
				- How to unlock bootloader
				  collapsed:: true
					- How to unlock
						- https://www.youtube.com/watch?v=x0jWw7hpIB0
						- https://www.youtube.com/watch?v=v5ytDelaa4w
					- In Settings > Developer Options
						- Enable USB Debugging (may require restart)
						- Enable OEM Unlock
				- How to flash and/or boot TWRP
				  collapsed:: true
					- adb reboot bootloader
					- fastboot flash recovery twrp-pocophone1.img
					- _Boot to recovery_
						- EITHER
							- adb reboot recovery
							  This step is needed because otherwise stock recovery will overwrite TWRP if you boot into system (ROM) first
							- fastboot boot twrp-pocophone1.img
				- In TWRP flash [combo ROM+GApps/NoGApps *e.g. LineageOS with microG)]; F-Droid Privileged Extension and Magisk
				  collapsed:: true
					- Flash pie vendor and firmware
					  https://forum.xda-developers.com/poco-f1/development/rom-lineageos-16-0-t3849934
					- Flash the latest LineageOS build and GApps
						- Official LineageOS
						  https://wiki.lineageos.org/devices/beryllium
					- Flash [Magisk](https://workflowy.com/#/baba54354fcf)
					  https://github.com/topjohnwu/Magisk/releases
				- How to sideload flash (ie from PC) via TWRP
				  collapsed:: true
					- Plug in device and turn on USB Debugging mode in Developer Options
					- Use terminal to check if computer recognises the device
					  adb devices
					- adb reboot bootloader
					- fastboot boot twrp\*.img
					- In TWRP
						- Advanced > ADB Sideload
						- EITHER
							- adb sideload uninmod_magisk-v3.zip
							  Preferred method
							- adb push uninmod_magisk-v3.zip /sdcard/uninmod_magisk-v3.zip
				- LineageOS (beryllium)
				  collapsed:: true
					- Without microG
					  https://wiki.lineageos.org/devices/beryllium
						- Official version now (v16 LOS)
						  https://forum.xda-developers.com/poco-f1/development/rom-lineageos-16-0-t3849934
							- Instructions :
								- Download the latest build and GApps
								- Reboot to recovery
								- Flash the latest build and GApps (adb sideload if you are encrypted or use external sdcard)
								- Reboot
					- With ((649b13d2-f7fb-449f-808b-d819f81d3094)) (and signature spoofing)
					  https://download.lineage.microg.org/beryllium/
					- _Related: _
						- Android versions
						  intralink2:: https://workflowy.com/#/3814d91a5ec9
				- Google Camera
				  collapsed:: true
					- Pros/Cons
						- Looks really good on Pixel
						  https://www.xda-developers.com/google-pixel-night-sight-google-camera-review/
					- _Methods_
						- Pre-req 1: Google Play Services or alternative
							- Standard GCam can be used with the FOSS Gcam Services Provider app only if GCam version is 7.5 or lower
							  [https://github.com/lukaspieper/Gcam-Services-Provider](https://github.com/lukaspieper/Gcam-Services-Provider)
								- Otherwise requires a modified GCam apk or compatible Android OS
								  source:: [https://github.com/lukaspieper/Gcam-Services-Provider#compatibility](https://github.com/lukaspieper/Gcam-Services-Provider#compatibility)
							- microG is sufficient for compatibility
							- Or use full GApps (Google Mobile Services)
						- _Download a ported GCam for best compatibility_
							- Port Hub
							  [https://www.xda-developers.com/google-camera-port-hub/](https://www.xda-developers.com/google-camera-port-hub/)
							- Poco F1
								- Discussion
									- [https://forum.xda-developers.com/t/port-modded-google-camera-with-hdr-night-sight-and-etc.3910336/](https://forum.xda-developers.com/t/port-modded-google-camera-with-hdr-night-sight-and-etc.3910336/)
									- [https://forum.xda-developers.com/t/bsg-google-camera-port-7-4-104-june-18.3843130/](https://forum.xda-developers.com/t/bsg-google-camera-port-7-4-104-june-18.3843130/)
								- Confirmed working
								  [https://www.celsoazevedo.com/files/android/google-camera/dev-san1ty/](https://www.celsoazevedo.com/files/android/google-camera/dev-san1ty/)
					- Can get via PE
					  https://www.xda-developers.com/poco-f1-pixel-experience-android-pie/
						- Or APK (just for Pixel)
						  [Download Google Camera with Night Sight on Pixel 3, Pixel 2, and Pixel](https://www.xda-developers.com/google-camera-night-sight-google-pixel-3-google-pixel-2-google-pixel/)
						- https://www.reddit.com/r/PocoPhones/comments/9qvc11/installing_modded_google_camera_on_lineage_os_16/
					- 2 Backlinks
						- See [Google Camera](https://workflowy.com/#/819ac3cc5131) (may require additional apk)
						- See [Google Camera](https://workflowy.com/#/819ac3cc5131)
			- Hiding the notch
				- Developer Options > Drawing > Display cutout: hide
			- Battery can be replaced but it's a chore
			  https://www.youtube.com/watch?v=9FER7aYtuFU
		- [Google Pixel](https://www.gsmarena.com/google_pixel-8346.php) (2016)
		  id:: 649b13cc-ed21-4d97-b946-440f2d0ff508
		  collapsed:: true
		  AKA Google Pixel 1 / first gen | Backup phone | Purchased in May 2018 via eBay UK
			- Used for almost 3 years (May 2018 - April 2021)
			  collapsed:: true
				- Stopped using because
					- Battery life got too poor
						- Li-Ion 2770 mAh, non-removable
					- LineageOS no longer new versions
					- Camera and processor could use an upgrade
					- Screen too small (5", next phone Poco F1 is 6.18")
			- _Purchased device info_
			  collapsed:: true
				- 128GB
				- No warranty?
				  _See_ [Google provides no warranty UNLESS you purchase via the Google store](https://workflowy.com/#/cef0811b2046)
				- _See_ [1 (released Sun, Jan 10, 2016) ](https://workflowy.com/#/cba4caef87c5)
			- _Pros/Cons_
			  collapsed:: true
				- Pros
					- Bootloader unlocked on every Pixel model for 1st gen at least
					- Has headphone jacks (unlike Pixel 2 onwards)
				- Cons
					- Sun, Nov 21, 2021 - TWRP no new builds since Q2 2020
					  [https://eu.dl.twrp.me/sailfish/](https://eu.dl.twrp.me/sailfish/)
					- Not removable battery
					- No microSD card
				- Upstream Pros/Cons
					- ((635037cc-6477-4588-80ff-c8149cad6935))
			- _Journal_
			  collapsed:: true
				- Dec 2020 - battery life not great anymore after 2.5 years of daily use
					- If I'm sitting on the phone making reading a bunch it can drain half the battery in maybe 2 hours
				- 2020 sometime - started using LineageOS + OpenGApps + [Magisk](https://workflowy.com/#/baba54354fcf)
				- May 2018 - LineageOS + OpenGApps doesn't seem to work for Pixel 1st gen
			- _Guide/How-to_
			  id:: 649b13cc-2779-4dfa-96e9-206343b62928
			  collapsed:: true
				- Problems
					- Trying to flash TWRP and Magisk each caused phone to bootloop
					  collapsed:: true
					  Sat, Nov 21, 2020
						- Trying to flash TWRP as a permanent recovery, caused a bootloop
						- _Later_
							- Trying to flash Magisk v? caused phone to bootloop again
								- _Kubuntu terminal_
									- cd ~/Documents/OPTIONAL/Android/Pixel1-sailfish
									- fastboot boot twrp-3.4.0-0-sailfish.img
								- _Android TWRP_
									- Install >
									- /sdcard/Android-1/twrp-installer-3.4.0.0-sailfish.zip
									- (since it removes root when finished)
									-
									- Flashing the latest Magisk
									- Then Advanced > Fix Recovery Bootloop
							- Made a full backup
							  _See _[Make a Nandroid backup using TWRP](https://workflowy.com/#/31c655f91cbe)<a href="https://workflowy.com/#/31c655f91cbe">
							  </a>
							- Updated from Sat, Sep 19, 2020 LineageOS build to <time startYear="2020" startMonth="11" startDay="21">Sat, Nov 21, 2020</time>
							- After that now it flashes fine. Likely incompatible LineageOS and Magisk builds. Still haven't tried to flash TWRP after because Lineage Recovery should be sufficient
					- LineageOS 17.1 update resulted in phone being unbootable
					  Wed, Sep 23, 2020
						- Symptoms
							- loss of Night Light (blue filter) and Android gesture navigation on previous update so I installed the very newest one
							- Phone could only boot to Lineage recovery
						- Steps
						  [Resetting a phone which won't boot](https://workflowy.com/#/6d5417eb2ca9)
					- Used EmojiSwitch to install iOS 12.1 beta emojis, now can't connect to internet via WiFi or cellular data
					  Thu, Nov 14, 2019
						- Did a Titanum backup of all apps
						- Copied entire /sdcard/ (includes Titanium backup) to my external HDD via adb pull (incase my `data/media/` i.e. `sdcard` gets wiped or if I need to)
						  adb pull /sdcard/ /media/boss/Transcend/0FILES/Android-backup/
							- **Noteworthy: **
								- **are my /sdcard/WhatsApp/ folder getting synced via Syncthing?**
								  _See_ [Syncthing](https://workflowy.com/#/26351aa44633)
						- Made a TWRP backup of my `data` partition (note: doesn't include`data/media/` i.e. `sdcard`)
							- **WARNING: **`data` partition backups don't include `/data/media/`, which is basically the viewable sdcard/storage folder
							  source:: https://twrp.me/faq/backupexclusions.html
								- Need to create a separate backup of that via MTP or adb pull
						- Copied TWRP data partition backup to my external HDD
						  adb pull /sdcard/TWRP/backups/ /media/boss/Transcend/0FILES/Android-TWRP-data/
						- Via TWRP flashed a OTA image of Android 10
						  _See_ [Flash stock Android ](https://workflowy.com/#/54ead667ca81)
						- **Problem was fixed**
						- _Finishing touches_
							- Flash TWRP as a recovery
							  [Flash TWRP's newest version as a recovery](https://workflowy.com/#/205305d803ab)
							- Flash Magisk via TWRP
								- Rebooted into TWRP
						- **Problem returned**
						- Froze the EmojiSwitch app using Titanium Backup
						- _Then repeated:_
							- Flash OTA image
							  _See_ [Flash stock Android ](https://workflowy.com/#/54ead667ca81)
							- Flash TWRP as recovery
							- Flash Magisk
					- Flashed Magisk-v17.3 to Android 9 stock ROM (which lost Magisk during 8>9 update) and now bootloops (doesn't get past the white Google screen on startup)
					  Fri, Jan 11, 2019
						- ## I can use ADB to get into TWRP 3.2.3-1
						- The uninstall Magisk ZIP however is on my PC
						- ADB Sideload isn't working properly
							- In TWRP
								- Advanced > ADB Sideload
								- EITHER
									- adb sideload uninmod_magisk-v3.zip
									- adb push uninmod_magisk-v3.zip /sdcard/uninmod_magisk-v3.zip
				- **Rooting on Ubuntu (LineageOS + OpenGApps doesn't seem to work for Pixel 1st gen when I tried in May 2018)**
					- Download
						- TWRP
						  https://twrp.me/google/googlepixel.html
						- ((649b13d2-a633-4de3-aa08-e24106059dab))
						- NanoDroid
						  collapsed:: true
							- https://gitlab.com/Nanolx/NanoDroid/blob/master/README.md
							- Installation Process
								- NanoDroid
								- Download pre-built zip or create one from this repository
								- Installing from scratch
									- This is the recommended way.
										- perform full wipe (/system, /data, /cache, Dalvik/ART cache)
											- recommended, but not required
										- install desired ROM
											- make sure it does not include GApps if you want to use microG
												- NanoDroid tries to get rid of GApps on it's own, but it may not always work, try without any warranty
										- either pre-patched with signature spoofing support or deoxeded so you can patch yourself (instructions follow)
										- install Magisk
											- recommended, but not required
											- if Magisk is installed, NanoDroid will be installed as Magisk-Module, else it will install into /system directly
										- install desired Kernel (if any)
										- install NanoDroid
										- reboot into ROM
						- Magisk (root)
						- GApps or microG
							- OpenGApps 8.0 (ARM64)
							  https://opengapps.org/?api=7.1&variant=nano
						- ADB and Fastboot on Ubuntu 18.04 steps (Q4 2019)
						  sudo apt-get install android-tools-adb android-tools-fastboot
					- In Settings >> System > Developer Options
						- Enable USB Debugging (may require restart)
						- Enable OEM Unlock
					- Start the server
					  sudo adb start-server
					- adb devices
					- _Reboot to bootloader_
						- _Either_
							- adb reboot bootloader
							- OR
							- Power off your device completely. Hold volume down and turn on the device. Your device should now be in the bootloader.
					- fastboot oem unlock
					  Unlock bootloader
					- In Settings > Developer Options
						- Enable USB Debugging (may require restart)
					- Copy these files to your phone (can do this in normal system or TWRP mode)
						- LineageOS
						- OpenGApps
						- FDroid privileged
						- Magisk for this
					- _Boot TWRP from Ubuntu_
						- adb reboot bootloader
						- Download the latest IMG file for your device from TWRP website
						  e.g. https://eu.dl.twrp.me/sailfish/
						- fastboot boot twrp.img
					- How to flash TWRP [incomplete]
						- Copy TWRP installer ZIP + VerifiedBootSigner ZIP to phone
						- Use ADB to boot from the TWRP img
						- Once there flash the TWRP ZIP then the VBS ZIP
					- Installing TWRP as a recovery
					  id:: 644c0acb-2932-4b34-80df-59bc1eea78dd
						- `adb reboot bootloader`
						- `cd ~/Documents/OPTIONAL/Android/Pixel1-sailfish`
						- `fastboot boot twrp.img`
						  Launch TWRP
						- Flash twrp.img
						- {Archive}
							- Note: no 'recovery' partition anymore on Pixels so this below doesn't work:
								- fastboot flash recovery recovery.img
								  Flash TWRP recovery
						- ((649b13cd-41c8-4da3-965e-3e1c2e4d7889))
					- In TWRP, flash/install the files
						- Flash the Magisk ZIP
							- cd Documents/OPTIONAL/Android/
							- cd 'Pixel 1 sailfish'
						- or
						- Advanced > Sideload
							- adb sideload xxx.zip
					- Before installing the custom ROM, it’s better if you Wipe all the data by Clicking the Wipe button and Select Advanced Wipe – Tick all except Internal Storage
				- **Rooting on Windows (LineageOS + OpenGApps doesn't seem to work for Pixel 1st gen when I tried in May 2018)**
					- Download
						- TWRP
						  https://twrp.me/google/googlepixel.html
						- LineageOS (for microG)
							- https://download.lineage.microg.org/sailfish/
							- Get LineageOS for microG - because unlike official LineageOS it's deodexed? thus signature spoofing works
							- LineageOS
								- https://wiki.lineageos.org/devices/sailfish
								- https://forum.xda-developers.com/pixel-xl/development/rom-lineageos-15-1-pixel-xl-marlin-t3725985
								- Old
									- https://updater2.invisiblek.org//sailfish
									- 15.1 didn't work with OpenGApps from when I tried in May 2018
									  https://androidfilehost.com/?a=show&w=files&flid=241141
							- LineageOS (for microG) OR just use LineageOS + NanoDroid
								- Why do we need a custom build of LineageOS to have microG? Can't I install microG on the official LineageOS?
								  source:: https://lineage.microg.org/
									- MicroG requires a patch called "signature spoofing", which allows the microG's apps to spoof themselves as Google Apps. LineageOS' developers refused (multiple times) to include the patch, forcing us to fork their project.
										- https://review.lineageos.org/#/c/64967/
										- https://review.lineageos.org/#/c/65366/
										- https://review.lineageos.org/#/c/195283/
						- NanoDroid
							- https://gitlab.com/Nanolx/NanoDroid/blob/master/README.md
							- Installation Process
								- NanoDroid
								- Download pre-built zip or create one from this repository
								- Installing from scratch
									- This is the recommended way.
										- perform full wipe (/system, /data, /cache, Dalvik/ART cache)
											- recommended, but not required
										- install desired ROM
											- make sure it does not include GApps if you want to use microG
												- NanoDroid tries to get rid of GApps on it's own, but it may not always work, try without any warranty
										- either pre-patched with signature spoofing support or deoxeded so you can patch yourself (instructions follow)
										- install Magisk
											- recommended, but not required
											- if Magisk is installed, NanoDroid will be installed as Magisk-Module, else it will install into /system directly
										- install desired Kernel (if any)
										- install NanoDroid
										- reboot into ROM
						- Magisk (root)
						- ((6318fc66-9d9f-4547-8e1c-172958500c0d)) or microG
							- OpenGApps 8.0 (ARM64)
							  https://opengapps.org/?api=7.1&variant=nano
					- In Settings > Developer Options
						- Enable USB Debugging (may require restart)
						- Enable OEM Unlock
					- Power off your device completely. Hold volume down and turn on the device. Your device should now be in the bootloader.
					- Minimal ADB and Fastboot program
						- fastboot oem unlock
						  Unlock bootloader
					- In Settings > Developer Options
						- Enable USB Debugging (may require restart)
					- Copy these files to your phone (can do this in normal system or TWRP mode)
						- LineageOS
						- OpenGApps
						- FDroid privileged
						- Magisk for this
					- How to flash TWRP
						- Copy TWRP installer ZIP + VerifiedBootSigner ZIP to phone
						- Use ADB to boot from the TWRP img
						- Once there flash the TWRP ZIP then the VBS ZIP
					- Power off your device completely. Hold volume down and turn on the device. Your device should now be in the bootloader.
					- Minimal ADB and Fastboot program
						- fastboot boot files/twrp\*.img
						  Launch TWRP
							- Note: no 'recovery' partition so this below doesn't work:
								- fastboot flash recovery recovery.img
								  Flash TWRP recovery
					- In TWRP, flash/install the files
					- Before installing the custom ROM, it’s better if you Wipe all the data by Clicking the Wipe button and Select Advanced Wipe – Tick all except Internal Storage
				- **Assorted ROM steps**
					- Last LineageOS build (actually nvm there might be a 18.1 build)
						- [https://archive.org/download/lineageos171-20220217/](https://archive.org/download/lineageos171-20220217/)
						- [https://archive.org/details/lineageos171-20220217](https://archive.org/details/lineageos171-20220217)
				- 1 Backlink
					- Google Pixel [Guide/How-to](https://workflowy.com/#/8640753b6383)
					  #Phone
	- _Journal_
		- ((635037cc-4a02-4903-8965-b7f8d81eb2f3))
		- Consider a replacement for ((65339b44-e96d-4207-861c-38bebfe53a5f))
			- Why
				- Foldable phones for increased productivity, RAM
					- ((66bd0cf2-1be8-4375-af83-08eb49d85a56))
					- [HONOR Magic V5 (2025)](https://www.gsmarena.com/honor_magic_v5-13982.php) is super thin and has a large battery life thanks to silicon-carbon battery
				- Increased RAM to make better use of ((63a9ade4-0cdf-4680-a839-6b6f92e57f51)) : ((670be97c-236d-42e0-a498-acd0fcb2dc48)) feature
				-
		- {Archive}
			- Consider a new phone replacement for ((649b13cc-23ea-4398-8dcb-488f7f9c55e6))
			  collapsed:: true
			  Started [[2021-10-01 Friday]], last updated [[2024-03-08 Friday]]
				- Why
					- Unlocked bootloader means current phone is susceptible to Evil Maid attacks. Only DivestOS, CalyxOS, GrapheneOS allow relocking bootloader and Verified Boot currently. **However** this means no root, and it's currently required for app data backup via ((63216f53-22cf-428a-9193-e5a423158e2b))
						- ((63209286-6f40-4063-9fdc-2543251d416e)) : ((649b13d1-d103-4938-85a5-b13074f90f94))
					- eSIM would make international travel easier, though there's no FOSS implementation yet
					- ((63219e34-cda2-4a69-a2c8-b74b33cf9a91)) could enable a Samsung DEX-like experience. Though scrcpy is fine, and until Google Pixel Tablet is released in 2023 there's probably going to be little app support
					- Battery on F1 won't last forever and [replacement procedure is difficult](https://www.ifixit.com/Guide/Pocophone+F1+Battery+Replacement/138933), though this isn't urgent
					- Newer phones have updated kernels, which have support for exFAT with 5.10 and for NTFS with 5.15. This allows compatibility with exFAT SD cards, which don't have the 4GB file size limit which can mess with some backup sizes such as Signal and ((63216f53-22cf-428a-9193-e5a423158e2b))
					- After getting new phone, consider putting postmarketOS on Poco F1
					  id:: 644c09ca-6185-444e-bf92-e26e3ef7e183
					- ((649b13c9-2c58-49ad-a151-a73c49bdbc1d)) form factor is likely more productive
					- ((666ac10e-deb2-4d3f-b8ec-ecd66b91410d)) works better in sunlight
				- ((65ead18e-8bd9-41e4-8d68-f25fe63890ba))
				- _Shortlist_
					- ((65339b44-e96d-4207-861c-38bebfe53a5f))
					- ((635037cc-9ee5-4b8f-9dbb-abf07858ad32))
					  collapsed:: true
						- _Most notable pros/cons_
							- Pros - modular e.g. battery replacement, ((63219e34-cda2-4a69-a2c8-b74b33cf9a91)), microSD slot, [eSIM](https://workflowy.com/#/ecaf193f1615) + 5G, apparently has a relockable bootloader
							- Cons - Android 11 base so likely doesn't use a GKI (mobile Linux and kernel updates less likely), specs aren't quite flagship
						- Fairphone 4
					- ((635037cc-5575-4925-90f0-6b9ffcd6a48c))
					- ((635037cc-bdd1-4ad9-8650-d7e74ad15445))
					  collapsed:: true
						- _Most notable pros/cons_
							- Pros - Supports GrapheneOS/CalyxOS with relockable bootloader, 5 years of kernel and OS updates guaranteed, launches with Android 12 (and thus [GKIs](https://workflowy.com/#/1bfe537b404f) for mobile Linux in future)
							- Cons - no ((63219e34-cda2-4a69-a2c8-b74b33cf9a91)), GrapheneOS doesn't support location services or root or eSIM anyway, closed-source [Titan-M](https://workflowy.com/#/d0b45216f4f6) chip, no removable battery, no microSD card
						- 6 (releasing ~November 2021)
					- [Samsung Galaxy Z Fold4 (2022)](https://www.gsmarena.com/samsung_galaxy_z_fold4-11737.php)
					- ((635037cc-acae-433a-8e7d-a8b89379fa9d))
					  collapsed:: true
						- _Most notable pros/cons_
							- Pros - can run mainline Linux for longevity, slightly modular e.g. battery replacement, hardware killswitches, ((63219e34-cda2-4a69-a2c8-b74b33cf9a91)), microSD slot
							- Cons -
						- $400 PinePhone Pro
						- 1 Backlink
							- [See PinePhone Pro](https://workflowy.com/#/e446d6d51dba) is still years off primetime usage due mobile Linux being alpha, whilst Waydroid support is early too
				- _Analysis_
					- Only ((635037cc-9ee5-4b8f-9dbb-abf07858ad32)) and ((635037cc-6477-4588-80ff-c8149cad6935)) have acceptable hardware
						- ((635037cc-6477-4588-80ff-c8149cad6935)) is the only phone here with Evil Maid protection, which makes it the most secure as a daily driver
					- ((635037cc-acae-433a-8e7d-a8b89379fa9d)) is still years off primetime usage due mobile Linux being alpha, whilst Waydroid support is early too
					- ((63209286-6f40-4063-9fdc-2543251d416e))' approach
	- Phone models
	  id:: 63134569-450d-44f0-bf01-19db08dc9528
	  collapsed:: true
		- Potential models
		  id:: 635037cc-4a02-4903-8965-b7f8d81eb2f3
			- Google Pixel line
			  id:: 635037cc-6477-4588-80ff-c8149cad6935
			  collapsed:: true
				- Pros/Cons
				  id:: 635037cc-8619-4217-a23b-fe4aade68cd2
					- Pros
						- Only devices supported by ((63209286-6f40-4063-9fdc-2543251d416e)) and CalyxOS
						  collapsed:: true
							- GrapheneOS is not only utilizes reproducible builds but each GrapheneOS installation on any given device is also bitwise identical, is cryptographically validated by Android Verified Boot, and its authenticity can be proven remotely via Android Remote Attestation to show that the operating system installed is the same operating system that the developers wrote, and Daniel Micay personally inspected, compiled and digitally signed on a system he physically possesses, bought and paid for.
						- Bootloader unlocked and relockable
						- Extra security features
						  id:: 649b13cc-a9a2-40f4-9a73-97d19f4a0390
						  collapsed:: true
							- Features that other phones don't have
								- Verified boot with support for custom keys
								  collapsed:: true
									- [https://source.android.com/security/verifiedboot/](https://source.android.com/security/verifiedboot/)
									- [archived] [https://daltondur.st/secure_pinephone_1/](https://daltondur.st/secure_pinephone_1/)
										- Verified Boot – sometimes called or trademarked Secure Boot – verifies that the owner of a system approved a piece of software to run, or boot, on that system. This is usually achieved by checking a set of (practically, for now) unforgeable signatures provided with the software. The theory goes that the device owner had to create the unforgeable signature, and the device owner would not create that signature if they did not approve of the system running the signed software.
									- Note: Windows 11 requires Secure Boot to be enabled.
									  source:: [https://en.wikipedia.org/wiki/Windows_11#System_security](https://en.wikipedia.org/wiki/Windows_11#System_security)
										- Many Linux distributions do not have Microsoft-signed bootloaders, so their installers will not be able to boot on new Windows 11 PCs. Users can enroll their own signing keys in Secure Boot, but the technical knowledge required to do so is much higher than what is required to boot a USB stick. Ubuntu, Fedora, Red Hat, and OpenSUSE will be fine, but this will certainly be a loss for smaller distros. This is exactly the kind of concern that people have when we start to talk about enabling Verified Boot.
								- Hardware-backed Keystore
								  collapsed:: true
									- [https://source.android.com/security/keystore/](https://source.android.com/security/keystore/)
								- ((649b13cc-b652-4669-9955-ecfea35cd008))
								- Hardened basebands
								  collapsed:: true
									- [https://media.defcon.org/DEF%20CON%2027/DEF%20CON%2027%20presentations/DEFCON-27-Xiling-Gong-Peter-Pi-Exploiting-Qualcomm-WLAN-and-Modem-Over-The-Air.pdf](https://media.defcon.org/DEF%20CON%2027/DEF%20CON%2027%20presentations/DEFCON-27-Xiling-Gong-Peter-Pi-Exploiting-Qualcomm-WLAN-and-Modem-Over-The-Air.pdf)
								- Good IOMMU to isolate hardware devices
								  collapsed:: true
									- [https://media.defcon.org/DEF%20CON%2027/DEF%20CON%2027%20presentations/DEFCON-27-Xiling-Gong-Peter-Pi-Exploiting-Qualcomm-WLAN-and-Modem-Over-The-Air.pdf](https://media.defcon.org/DEF%20CON%2027/DEF%20CON%2027%20presentations/DEFCON-27-Xiling-Gong-Peter-Pi-Exploiting-Qualcomm-WLAN-and-Modem-Over-The-Air.pdf)
								- Fine-grained forward-edge kernel Control-Flow Integrity
								  collapsed:: true
									- [https://android-developers.googleblog.com/2018/10/control-flow-integrity-in-android-kernel.html](https://android-developers.googleblog.com/2018/10/control-flow-integrity-in-android-kernel.html)
								- Kernel ShadowCallStack
								  collapsed:: true
									- [https://security.googleblog.com/2019/10/protecting-against-code-reuse-in-linux_30.html](https://security.googleblog.com/2019/10/protecting-against-code-reuse-in-linux_30.html)
							- Here you can read in depth as to why the GrapheneOS project specifically uses Pixels:
							- https://grapheneos.org/faq#device-support
							- In summary, Pixels have firmware and hardware level attack mitigation, which isn't present on many Android phones. With Graphene OS, you completely cut your ties with Google and receive extra software security hardening.
						- Google Camera
						- Now Playing
						  collapsed:: true
							- [https://www.xda-developers.com/google-pixel-now-playing-feature-ported/](https://www.xda-developers.com/google-pixel-now-playing-feature-ported/)
							- [https://github.com/KieronQuinn/AmbientMusicMod/blob/main/app/src/main/assets/faq.md](https://github.com/KieronQuinn/AmbientMusicMod/blob/main/app/src/main/assets/faq.md)
							- See [Try a Now Playing app equivalent (Shazam alternative but more private)](https://workflowy.com/#/c34dd9d81ae0)
						- Live Captions
						  collapsed:: true
							- [https://www.xda-developers.com/enable-pixel-4-live-caption-android-10/](https://www.xda-developers.com/enable-pixel-4-live-caption-android-10/)
						- [6 + 7 support protected KVM (pKVM)](https://x.com/GrapheneOS/status/1585424713387483143)
						  collapsed:: true
							- GrapheneOS:
								- Pixel 6 and Pixel 7 support protected KVM (pKVM) which is currently being used as an improved sandbox for certain OS functionality. We're interested in greatly expanding usage of this functionality and providing user-facing virtualization support via a management app in the OS.
								- This functionality is now properly open sourced as part of Android 13 and you can even use it to run virtual machines via adb on a Pixel 7 with the stock OS via crosvm (VMM written in Rust used by ChromeOS and Android). It's already fairly close to being usable for so much more.
								- The current usage within the OS is extremely limited but it would be nice to see it replace a lot of the existing fine-grained OS sandboxing done with seccomp-bpf and SELinux. Media stack via pKVM would be quite cool. We plan to focus on uninvasive features built on it for now.
								- It'd be difficult for us to develop and maintain broader usage for VM-based sandboxing within the OS. On the other hand, there's a fairly clear path to developing uninvasive user-facing functionality for running apps in a more restricted VM-based sandbox or for managing OS VMs.
								- Android provides the Chromium layer-1 sandbox as an OS feature available to every app via isolatedProcess services. It would also be very interesting to move this to per-site virtual machine instance using microdroid. It'd be a large project but very high impact for browsers.
								- Since isolatedProcess is an OS API, it'd benefit all Chromium-based browsers and other apps using it rather than being specific to Vanadium. That'd be a difficult project but we can consider it as a future large feature on the same scale as our sandboxed Google Play feature.
								- These features do slightly reduce trust in privileged core userspace processes particularly if there's a mistake in SELinux policy.
								- Worth noting that since protected virtual machines are now supported, the kernel isn't all powerful within the OS anymore:
						- Gfxstream is a graphics virtualization technology that forwards graphics API calls from the guest Linux virtual machine directly to the host Android device, enabling GPU-accelerated rendering for Linux apps.
					- Cons
						- [[2025-06-14 Saturday]] [Google Pixel-specific source code seems to be going closed-source](https://www.reddit.com/r/linux/comments/1l9amau/aosp_project_is_coming_to_an_end/) which will likely impact GrapheneOS
							- It sounds like Google is doing two things
								- dumping the whole Android 16 code at once with squashed commit history, making it very hard for developers to see what’s actually changed and where
								- not publishing any code specific for Pixel devices; the code they publish can only run in a virtual machine
									- Since AOSP no longer have device support, it's likely worth building their own phone from scratch to have full SoC drivers, or reverse engineer Pixel drivers
							- https://twitter.com/seangchau/status/1933029688202703062
								- > We're seeing some speculation that AOSP is being discontinued. To be clear, AOSP is NOT going away. AOSP was built on the foundation of being an open platform for device implementations, SoC vendors, and instruction set architectures.
								  
								  AOSP needs a reference target that is flexible, configurable, and affordable – independent of any particular hardware, including those from Google. For years, developers have been building Cuttlefish (available on GitHub as the reference device for AOSP) and GSI targets from source. We continue to make those available for testing and development purposes.
								- Replies
									- > Without an actual hardware, build target though, there's no way to actually validate in the community if there's a problem. 
									  
									  There needs to be an actual hardware build target for AOSP.
									  
									  Please keep Pixel a hardware build target. 
									  
									  It opens a massive antitrust wormhole otherwise.
						- Average battery life
						- Not Samsung so no ((63219e35-31c8-4454-9e84-be51a2684aae))
						- Titan-M Hardware Security Module (HSM) is closed-source, though this may be the point
						  id:: 649b13cc-b652-4669-9955-ecfea35cd008
						  collapsed:: true
							- Pros/Cons
							  collapsed:: true
								- Pros
									- It's supposed to be separate and tamperproof
										- The OS stores a high entropy random value as the Weaver token on the secure element (Titan M on Pixels) and uses it as another input for key derivation.
								- Cons
									- For example a compromised Titan M could open you up completely to MITM of any network connections your device makes.
									- It could also allow any entities that already have some limited access to your device (i.e. an app restricted via OS perms) to gain broader access to sensitive data on your device.
							- What
							  collapsed:: true
								- _Equivalent implementations_
									- Trusted Platform Module (TPM) on x86-64
									- Secure Enclave on Mac/iPhone
								- Is used by GrapheneOS for
									- Modern Pixel handsets use the Titan M security chip for pin authentication and password authentication.
										- The Titan M contains its own internal clock that the operating system has no influence over and as a result cannot spoof. The Titan chip itself is small (almost the size of a grain of rice) and by nature of its design is extremely difficult to attack. Since the Titan M also is integrated into the disk encryption process, it also stores the tokens used to derive the keys to the files on the SSD and won't release the tokens to the operating system unless it gets the correct passphrase or pin, meaning that any attempts to access the files on the phone's drive need to be made through that specific Titan chip, on that specific phone. This is to prevent offline cracking attempts where the phone is physically cut open, the SSD is removed from the PCB, mirrored via NAND cloning, and the encrypted data on it subjected to guessing attacks run on a much more powerful system that can run more guesses than the phone would otherwise allows.
										- During a brute force attack when many attempts may be entered into the phone in an attempt to find the right one, the Titan M will enforce a progressively lengthening time. After the first five attempts, the Titan will shut off access to the tokens for 30 seconds and switch off the fingerprint reader. Even if the operating system is exploited and the clock is bypassed, the Titan M answers only to its own timer housed within the chip and can ignore further attempts to guess the pincode or password. Continuing to attempt to make attempts on the pincode without waiting will result in the Titan punishing the attempt by progressively increasing the timeout for longer and longer periods of time, up to a maximum of only allowing one guess every day. At the time of one day per guess which is reached after 150 incorrect attempts (which would take approximately 2 weeks of timeout to reach), this extends the time it would take to exhaust a 4-number pincode to around six and a half centuries, and extends a two-word passphrase from a 2048-word wordlist into computational infeasibility.
										- Because of the safety implications this has of data loss, and the strength of the Titan M being able to enforce this timeout, Data Wipe on Authentication failure is obsolete. This won't protect you if your password is "password" or "1234" or something easily guessable like the year of your high school graduation or your birthday. However, it will bolster the strength of a short, but hard-to-guess pincode or passord to keep your data safe, without needing to keep it in a perpetually precarious situation where it's liable to be accidentally destroyed.
									- Disk encryption
										- All modern phones should offer strong file based, hardware-bound encryption, rather than full disk software-only encryption. The reason for this is simple: phones aren't laptops. They're left on around the clock more often than not, during which, the hard drive will need to be unlocked in order for the phone to function. Park this in your mind, since there's more on that in the question immediately after the one following this one.
										- GrapheneOS makes full use of the hardware-bound encryption in modern Android devices. The Titan M handles the user's pincode or password. Upon getting the correct password, the Titan M will calculate, then release an access token to the phone that the phone in turn can use to derive the keys via a key derivation function which also uses a mathematical proof of uniqueness called a "cryptographic hash" of the first 2,000 bytes of a special partition set aside on the phone's SSD as a safeguard to mitigate data remnance issues. Each file is encrypted with AES-256-XTS, and the filesystem metadata is encrypted with AES-256-HEH on modern handsets (older handsets use AES-256-CTS for the filenames, but these are on the way out).
										- File Based Encryption has several advantages over Full Disk Encryption:
											- It allows work profiles to be made more secure, because when one user is logged out, the keys can be ejected from memory. This isn't doable with full disk encryption because full disk encryption is all-or-nothing.
											- When files are not in use, such as if the screen is locked, their keys can be ejected from memory.
											- With the use of the Strongbox Key Master on modern Android Handsets (Pixel 3 and later), pictures can be taken and written to the drive encrypted while the screen is still locked, without having to unlock the drive so that files can be written to it.
											- The phone can handle updates even while locked and more importantly, the data is at rest.
											- It allows some features most people have come to expect out of cellphones, such as direct boot.
										- The filesystem metadata on modern GrapheneOS handsets is itself padded to disguise filename lengths, then is encrypted with AES-256-HEH, so adding another layer of encryption on top would be redundant, and unnecessary. It would also break other security features such as direct boot and background updates, making updating and patching more difficult. Since phones spend a majority of their time powered on, the gains of layering one within the other would likely never be realized. It would add more complexity to the entire stack and increase the amount of attack surface and amount of code that would need to be maintained and the amount of places that bugs could hide for very little gain. In short, the tradeoffs of simply "add both" would not be worth the benefits, would break certain features that are more important than file metadata which itself is already encrypted, and would represent a number of steps backward.
									- Factory reset
										- When you hit factory reset on your cellphone, the Titan will destroy its access tokens and the phone will change the header partition. Without either the access tokens or if even one bit is changed of the header partition, the key derivation function will produce an incorrect result, and the data on the drive will be lost forever. The key derivation function by virtue of its design cannot be reversed. The data on it will be gone. Forever. No ifs, ands, or buts.
										- There is no recovery from this state, so if there's anything on your phone that you really don't want to lose, make sure you have it backed up separately beforehand. This includes changing your 2FA tokens, password manager, exported any bookmarks you don't want to lose, saved any pictures, videos, or movies, anything stored on your phone.
								- x
									- The primary selling point of the Titan M hardware security module is the Strongbox Keymaster,
										- which allows secret keys to be created, stored and used within the chip, where even root on the
										- operating system cannot extract them. The physically separated chip offers significantly less
										- attack surface than ARM Trusted Execution Environment. Auditor on GrapheneOS starting with
										- version 11 of the ((644c0acf-58a1-4b82-9767-c88c65955315)) uses the Strongbox Keystore API for verifying the operating system
										- if it is present. This security feature has extensive functionality and could be used for secure
										- payments, public key cryptography, or allowing apps to use the Titan M to save data to the drive
										- encrypted while the phone is locked, without needing to risk exposing the keys. For example, one
										- application that this would benefit from would be to allow the phone to take pictures without
										- needing to handle the keys to the drive. The chip is physically hard-wired to the buttons on the
										- phone, so user input to it cannot be spoofed by a malicious app or a compromised operating
										- system.</p>
										- <p>It provides 'insider attack protection' which requires the owner to authenticate to the chip
										  														- using a password that is chosen by the owner, before the chip will allow the firmware of the
										  														- device to be updated. This is intended to dissuade a situation similar to the <i>2015 Apple v.
										  														- FBI</i> case, where a malicious actor could confiscate the device, find an exploit to gain
										  														- control of the operating system, then use legal or extralegal pressure to force Google to issue
										  														- a rogue firmware update that would disable the security features. Since the phone cannot accept
										  														- the updates without the owner's password, this removes the vendor from being a third party in
										  														- that particular attack vector.</p>
										- <p>The Titan M is also used for verifying of the user's password and for drive encryption. The
										  														- chip creates and stores a secret token. The chip will not calculate and release the secret token
										  														- that the phone will use to derive the keys to the drive until it gets the correct password.
										  														- Since the chip uses its own internal timer built into it, it can enforce a progressively
										  														- lengthening timeout to deter brute force attacks more reliably than relying on the strength of
										  														- the password and a work factor such as a key derivation function alone. This also presents a
										  														- safer alternative to keeping the keys in a continually precarious state and erasing them should
										  														- ten incorrect guesses at the pincode be made. Unlike the factory image, GrapheneOS supports the
										  														- use of long passphrases to allow for both security measures of a cryptographically strong
										  														- passphrase and hardware bound encryption to be used together, combining hardware-backed
										  														- encryption with a cryptographically strong passphrase.  </p>
										- <p>The Titan M is incorporated into the boot process by storing the last good version of the
										  														- operating system within itself and not allowing the phone to be downgraded to an earlier
										  														- revision to disable or roll back security protections. </p>
										- <p>Factory Reset Protection to discourage steal-and-sell attacks where an attacker steals the
										  														- phone, changes the IMEI and resets the operating system in order to resell it as if it were a
										  														- legitimately purchased secondhand device is not yet implemented on GrapheneOS, but is also one
										  														- of the features it supports and may be implemented in the future.</p>
									- [https://www.blog.google/products/pixel/titan-m-makes-pixel-3-our-most-secure-phone-yet/](https://www.blog.google/products/pixel/titan-m-makes-pixel-3-our-most-secure-phone-yet/)
									- 2021 - [https://www.zdnet.com/article/google-sets-up-android-group-for-future-car-keys-national-id-e-wallets/](https://www.zdnet.com/article/google-sets-up-android-group-for-future-car-keys-national-id-e-wallets/) "Google sets up Android group for future car keys, national ID, e-wallets" -"Google has set up the Android Ready SE Alliance to support the adoption of Android smartphones and wearables as digital keys, identity documents, and wallets for digital cash." -As part of this, Google has launched StrongBox SE (Secure Element) This applet works alongside Google's Titan M chip to create a more secure device. Google believes the Titan M to be so secure, they offer a $1m bug bounty for anyone who can achieve full chain remote execution with persistence against it. -The ultimate goal is to make Android secure enough for official, important digital files like driver's license, keys, and other credentials.
								-
							- Discussions of adding a HSM to Linux phones
							  collapsed:: true
								- [https://forum.fairphone.com/t/titan-m-replacement/77148/11](https://forum.fairphone.com/t/titan-m-replacement/77148/11)
								- [https://forum.pine64.org/showthread.php?tid=13179&page=2&highlight=verified+boot](https://forum.pine64.org/showthread.php?tid=13179&page=2&highlight=verified+boot)
							- _Related:_
							  collapsed:: true
								- Trusted Execution Environment (TEE)
								  collapsed:: true
									- [https://en.wikipedia.org/wiki/Trusted_execution_environment](https://en.wikipedia.org/wiki/Trusted_execution_environment)
									- ARM TrustZone
									- Intel SGX Software Guard Extensions
									- AMD Platform Security Processor (PSP)
									- RISC-V MultiZone™ Security Trusted Execution Environment
									- RISC-V Keystone Customizable TEE Framework
								- owner-controlled verified boot process via Heads' Measured Boot process and TPMTOTP
								  collapsed:: true
									- secured boot process with entirely open source, auditable, owner-controlled software named [Heads](https://github.com/osresearch/heads).
									  [archived] [https://daltondur.st/secure_pinephone_1/](https://daltondur.st/secure_pinephone_1/)
										- 1
											- Heads’s approach to verifying the boot process is desirable in other ways, too. Like our potential solution to prevent an attacker with physical access from getting access to the data on our PinePhone, Heads uses a TPM 2.0-compliant module to encrypt its disk encryption keys. Like TBBR-style Verified Boot, it uses the checksum of the next piece of software that will be booted to determine what happens next. It then diverges from Verified Boot for a while. Instead of checking that the next code to be loaded matches a given signature and halting boot on an unexpected result, Heads measures every piece of code in the boot process instead (until it begins to boot the Linux kernel, when it switches back to signature verification). The first bootloader creates a checksum of itself and places that information into the computer’s TPM. Then it checksums the next piece of code in the boot process and tells the TPM about it, that piece of code checksums the next, and so on. At the end of this process, the system’s TPM knows about the checksums of all of the code that’s running on the system. Now, Heads asks the TPM to decrypt the disk encryption key. The TPM looks over all of the checksums it knows about. If they match a set of expected values, the TPM gives the decrypted disk encryption key back to Heads. If not, the TPM refuses the operation. Assuming the first bootloader on the system can be trusted (that’s the root of trust), an attacker cannot change the system software without causing the TPM to refuse our decryption request. This entire process is called Measured Boot.
											- Now, of course, Measured Boot is not perfect. An attacker could snoop on the communications between Heads and the TPM to learn the hash values that the TPM expects, then boot their own software that fakes those values back to the TPM at a later time. This is where adding Verified Boot to Measured Boot could be quite powerful: the attacker can’t boot their own software that fakes the boot measurements because VB will block it. The attacker needs to be able to fake the measurements and pass VB in order to succeed in their attack. That would be a tall order for even the most seasoned attackers. Even when using one of these technologies alone, though, the Evil Maid’s requirements for a successful attack are so high as to prevent most from trying.
									- Hugo Landau discussed this in his blog post, [How secure boot and trusted boot can be owner-controlled](https://www.devever.net/~hl/secureboot). Corey Doctorow discussed it twice, once in <a href="https://boingboing.net/2012/01/10/lockdown.html">Lockdown: The coming war on general-purpose computing</a> and again in <a href="https://boingboing.net/2012/08/23/civilwar.html">The Coming Civil War over General Purpose Computing</a> (both are used as background sources on Hugo’s post)
									- TPMTOTP
										- There is also the associated problem of “how do I verify that my Heads machine hasn’t been tampered with before I type in my encryption key?” After all, the Evil Maid could have simply stolen your computer and replaced it with one that looks a lot like it, and now only needs to steal your encryption passcode. Once you type in your passcode on the fake computer, the Evil Maid learns of it and is able to decrypt your real computer. This is where Matthew Garrett’s [Anti Evil Maid 2 Turbo Edition](https://mjg59.dreamwidth.org/35742.html) project, better known as TPMTOTP, comes in to play. I feel like he does a better job of explaining it on his blog, but in a nutshell it uses TOTP to display a six-digit number on screen that changes every thirty seconds. If that number matches the number in your 2-factor authentication app or hardware TOTP token, you’re (probably) safe to unlock! There is also a similar implementation that uses a hardware security key to verify that the computer is yours: plug in your security key and it does a bit of HOTP magic with the computer. If you see the green light on your key, you’re safe to enter your passcode. However, this does not grant any more security over TPMTOTP, it just makes the process more convenient to perform on every boot.
										- TPM - requires a Trusted Platform Module
								- Adding a TPM and porting Heads' Measured Boot process and TPMTOTP to the PinePhone would be a great start.
						- Google provides no warranty UNLESS you purchase via the Google store
						  collapsed:: true
							- Like many other manufacturers, I think they offer commercial bulk buying of their phones without warranty - which allows 3rd party resellers to sell the devices on with their own warranty policy attached
							- I spoke to the Google Support (UK) a little while ago. They only cover warranty for phones bought through them. If you buy from an authorised reseller (E.g. your carrier), the warranty is honoured by them, not Google.
								- If you buy from third party sites like eBay, you are getting it from an unauthorised seller, so you would have to ask them where they bought the phone originally and get a receipt, then contact directly the original reseller from which the person from eBay bought the phone. Google won't honour the warranty unless you can prove that the phone was bought through them. There may be exceptions but I wouldn't risk it.
						- Lacks a number of pro-consumer features which are important to Linux phones like ((649b13cb-4bf6-46f3-9f65-5419728ccc6b)) and ((649b13cb-e023-4f42-a55c-a6539fd2c2a4))
							- ((644c0acb-3ce9-4f51-b07b-0973381a8057))
							- ((644c0acb-f24c-497c-a7a2-6b7b24742fb4))
							- ((644c0acb-77cc-4f0a-b65c-7c53364525f4))
						- Google will likely replace the kernel in later models with ((649b13cf-a825-48f5-ae83-b47b6ad6bff9)), making it incompatible with mobile Linux
						- Many closed-source blobs for firmware, unlike ((649b13cb-e023-4f42-a55c-a6539fd2c2a4))
						- Most models don't support ((63219e34-cda2-4a69-a2c8-b74b33cf9a91)). Except ((65339b44-e96d-4207-861c-38bebfe53a5f)) : ((96fa4825-1ceb-403f-82c2-37b21fbfd874))
						  id:: 65339c71-7acb-45e2-ba4f-a3e2b80441bd
					- ((63209286-6f40-4063-9fdc-2543251d416e))
				- Models
					- Google Pixel 10 series (2025)
					  collapsed:: true
						- [It'll use the Tensor G5 SoC, which will be manufactured at TSMC rather than Samsung Foundry](https://www.reddit.com/r/hardware/comments/1dxa30e/a_note_on_the_tensor_g5_the_first_fully_custom/)
					- Google Pixel 9 range (2024)
					  id:: 66bd0cd8-9927-43ac-900b-85d6dacc026f
					  collapsed:: true
						- Meta
							- Comparisons in-generation
								- Comparison table
								  collapsed:: true
									- ![image.png](../assets/image_1723665633586_0.png)
								- [- YouTube](https://youtu.be/KkbAMUHqTpM)
								  ((66bd0ce2-b82b-4e12-9634-f0210092d7a0)) vs ((66bd0ce8-48f7-4c0d-8462-e4ff62076146))
									- They look virtually the same
									- Both 128GB storage, 9 can go up to 256 but 9 Pro to 512
									- 7 years of updates, like a Samsung phone also
									- Not much difference truly
							- Comparisons cross-generation
								- ((66bd0cd8-9927-43ac-900b-85d6dacc026f)) vs ((6718d73b-96bc-4517-a943-c33ace50aca4))
								  id:: 67279228-8c0d-4e67-87e3-ff1401f2db0c
									- For ((66bd0ce2-b82b-4e12-9634-f0210092d7a0))
										- Camera lens cutout doesn't go edge-to-edge
										- 12GB RAM rather than 8GB
										- G4 chip instead of G3
										- Slightly bigger battery
										- Satellite functionality
											- Settings > Safety & emergency on a Pixel phone today, you’ll very likely see “Satellite SOS” > allows texting and calling emergency services
									- For ((65339b44-e96d-4207-861c-38bebfe53a5f))
										- 6.2" rather than 6.3"
										- Cheaper
									- [Google Pixel 9 vs Pixel 8: Which one to get? - YouTube](https://youtu.be/3hzT9VvrTkc)
						- Google Pixel 9
						  id:: 66bd0ce2-b82b-4e12-9634-f0210092d7a0
						- Google Pixel 9 Pro
						  id:: 66bd0ce8-48f7-4c0d-8462-e4ff62076146
						- Google Pixel 9 Pro XL
						- [Google Pixel 9 Pro Fold](https://www.gsmarena.com/google_pixel_9_pro_fold-13220.php) (2024)
						  id:: 66bd0cf2-1be8-4375-af83-08eb49d85a56
						  collapsed:: true
						  Successor to ((666af42d-d4e6-4ae2-a84f-a89ab7cd9f6f))
							- Pros/Cons
								- Pros
									- Enough inner screen space for two app multitasking
								- Cons
									- Very expensive
									- Bezels are a little thick
									- Camera bump is a big thick
									- Average battery life
									- Average CPU
									- Average camera
								- Unclear
								- Comparisons
									- [[2025-02-26 Wednesday]] ((66bd0cf2-1be8-4375-af83-08eb49d85a56)) vs owned ((65339b44-e96d-4207-861c-38bebfe53a5f))
									  id:: 67bee5b4-02be-4bfc-b5e6-441e90c667b3
										- For ((66bd0cf2-1be8-4375-af83-08eb49d85a56))
											-
										- For ((65339b44-e96d-4207-861c-38bebfe53a5f))
											- This Fold generation doesn't have impressive enough battery life to be worth upgrading to. Oppo Find N5 with it's silicon-carbon battery and thinness is more appealing
											- 16GB RAM is the bare minimum for an upgrade, ideally more
							- [Google Pixel 9 Pro Fold Is So Good! But… - YouTube](https://youtu.be/nK9zxuXa3OA)
								-
					- Google Pixel 8 range (2023)
					  id:: 6718d73b-96bc-4517-a943-c33ace50aca4
					  collapsed:: true
						- Meta
							- ((67279228-8c0d-4e67-87e3-ff1401f2db0c))
						- [Google Pixel 8](https://www.gsmarena.com/google_pixel_8-12546.php) (2023)
						  id:: 65339b44-e96d-4207-861c-38bebfe53a5f
						  collapsed:: true
						  AKA [shiba](https://wiki.lineageos.org/devices/shiba/) - but shares same base as shusky ([LOS repo](https://github.com/LineageOS/android_device_google_shusky)) | ((6724de36-ecc1-4496-a18f-54dbc00b3c25))
							- Pros/Cons
								- Pros
									- First modern Pixel series to support ((63219e34-cda2-4a69-a2c8-b74b33cf9a91))
									  id:: 96fa4825-1ceb-403f-82c2-37b21fbfd874
									  collapsed:: true
										- [[2025-03-17 Monday]] Not compatible with all hardware
											- USB C hub with HDMI attached monitor didn't work - both work monitor and mum's TV
											- USB C hub utilising USB C ((64e0946d-1d0e-4824-b150-1a08f26aba23)) monitor did work. Mirrored display is vertical, like scrcpy
										- [[2024-06-13 Thursday]] [Now supports it](https://arstechnica.com/gadgets/2024/06/googles-pixel-8-series-finally-supports-displayport/)
										- https://www.patreon.com/posts/confirmed-pixel-91026490
										- https://www.androidcentral.com/apps-software/with-pixel-8-google-may-finally-have-an-answer-to-samsung-dex
										- http://libreddit.localhost:8080/r/Android/comments/178jb23/confirmed_pixel_8_supports_display_output_heres_a/
										- [GrapheneOS added support](https://github.com/GrapheneOS/os-issue-tracker/issues/2616#issuecomment-1817409685)
										- ((6521b31d-8ec7-4b86-a6f6-a5663ad9317a))
									- Superb camera
									- 7(?) years of updates
									- 256GB model available - as much as I'm currently using [[2023-10-21 Saturday]] (total for internal memory + SD card usage)
								- Cons
									- Slightly too big for my preferred hand size (is 6.2", maybe 5.10" preferred)
									- Average battery - 4575 mAh
									- [[2025-02-26 Wednesday]] 8GB RAM is noticeably limiting now that I've started using ((63a9ade4-0cdf-4680-a839-6b6f92e57f51)) : ((670be97c-236d-42e0-a498-acd0fcb2dc48))
								- Upstream Pros/Cons
									- ((67279228-8c0d-4e67-87e3-ff1401f2db0c))
									- ((635037cc-6477-4588-80ff-c8149cad6935))
								- Unclear
								- Comparisons
									- ((67bee5b4-02be-4bfc-b5e6-441e90c667b3))
									  collapsed:: true
										- {{embed ((67bee5b4-02be-4bfc-b5e6-441e90c667b3))}}
									- ((65ead18e-8bd9-41e4-8d68-f25fe63890ba))
									  collapsed:: true
										- {{embed ((65ead18e-8bd9-41e4-8d68-f25fe63890ba))}}
									- ((65339b44-e96d-4207-861c-38bebfe53a5f)) vs ((65339b73-6d19-42a9-b33f-fcba67731818))
									  collapsed:: true
										- Pros
											- 6.2" rather than 6.7
									- ((6724a01f-439f-43d9-a2d7-5284183361ea))
									  collapsed:: true
										- {{embed ((6724a01f-439f-43d9-a2d7-5284183361ea))}}
									- ((65339b44-e96d-4207-861c-38bebfe53a5f)) vs ((666af42d-d4e6-4ae2-a84f-a89ab7cd9f6f))
									  id:: 666af48d-cf2d-43a7-8f79-006afa76cf83
									  collapsed:: true
										- For ((65339b44-e96d-4207-861c-38bebfe53a5f))
											- ((666af42d-d4e6-4ae2-a84f-a89ab7cd9f6f)) : ((46b49913-f7d7-457c-9f3e-7a97820df736))
										- For ((666af42d-d4e6-4ae2-a84f-a89ab7cd9f6f))
							- Journal
								- ((6811cc50-0948-4a4a-8d0e-f40c205da86b))
								- [[2024-11-01 Friday]] Bought this and switched to it as main phone
								  id:: 6724de36-ecc1-4496-a18f-54dbc00b3c25
								  collapsed:: true
									- ((63209286-6f40-4063-9fdc-2543251d416e)) finally updated the ((6318fc65-99f9-4edb-a705-eb1deb420890)) dependency so it should be good to test now
									- Plan
										- Use it as a second phone for a few weeks with some apps, see how well backups work. If it's not good enough to deprecate root + ((63216f53-22cf-428a-9193-e5a423158e2b)) + ((649b13cd-7aed-4183-9c8c-ebc8ed613b4b)) then wait for LineageOS 22 to release in early 2025 then upgrade
									- [[2025-02-01 Saturday]] Review
										- Has worked well as a replacement the last 3 months.
							- Related:
								- ((63209286-6f40-4063-9fdc-2543251d416e))
								- ((679ddfab-0db4-4b3d-9bf8-8614f6528e17))
						- [Google Pixel 8 Pro](https://www.gsmarena.com/google_pixel_8_pro-12545.php) (2023)
						  id:: 65339b73-6d19-42a9-b33f-fcba67731818
						- ((666af42d-d4e6-4ae2-a84f-a89ab7cd9f6f))
						- [Google Pixel 8a](https://www.gsmarena.com/google_pixel_8a-12937.php) (2024)
						  id:: 663c821a-8c94-4ca1-b203-97fc90f85c2e
						  collapsed:: true
							- Pros/Cons
								- ## Pros
								- ## Cons
								- Unclear
								- Comparisons
									- ((663c821a-8c94-4ca1-b203-97fc90f85c2e)) vs ((65339b44-e96d-4207-861c-38bebfe53a5f))
									  id:: 6724a01f-439f-43d9-a2d7-5284183361ea
										- For ((663c821a-8c94-4ca1-b203-97fc90f85c2e))
											- 6.1" rather than 6.2"
										- For ((65339b44-e96d-4207-861c-38bebfe53a5f))
					- [Google Pixel 7 (2022)](https://www.gsmarena.com/google_pixel_7-11903.php)
					  id:: 635a1f15-0225-4af0-a5a3-0ef0f0d6be36
					  collapsed:: true
						-
					- [Google Pixel 6 (2021)](https://www.gsmarena.com/google_pixel_6-11037.php)
					  id:: 635037cc-bdd1-4ad9-8650-d7e74ad15445
					  collapsed:: true
						- Pro/Cons
							- Pros
								- 5 years of guaranteed updates
								- Launches with Android 12, and thus uses a [Generic Kernel Image (GKI)](https://workflowy.com/#/1bfe537b404f)
								- eSIM slot
								- ((63209286-6f40-4063-9fdc-2543251d416e)) supports Google Play Services, which is needed for several things including use of the <a href="https://workflowy.com/#/d19bbd08c7d6">Diopter Calculator app</a>
							- Cons
								- modem/connectivity issues
									- https://redd.it/w7uby1
									- https://redd.it/vqku2g
								- [£600, kinda expensive](https://store.google.com/uk/product/pixel_6?hl=en-GB)
								- Like other Pixel phones, no ((63219e34-cda2-4a69-a2c8-b74b33cf9a91))
								- 6.4" - slightly bigger than Pocophone F1 which is already big to hold
						- See General Pixel ((635037cc-8619-4217-a23b-fe4aade68cd2))
							- {{embed ((635037cc-8619-4217-a23b-fe4aade68cd2))}}
					- [Google Pixel 5](https://www.gsmarena.com/google_pixel_5-10386.php) (released Fri, Jan 10, 2020) | £599 price Mon, Nov 30, 2020
					  collapsed:: true
						- Specs
							- 8GB RAM
							- 128GB storage
					- 4a 5G (released Sat, Jan 11, 2020) | £499 price <time startYear="2020" startMonth="11" startDay="30">Mon, Nov 30, 2020</time>
					  collapsed:: true
						- 4a vs 4a 5G
							- $500 vs $350
							- Also comes with better CPU, dual rear camera, bigger battery, 6.2" size
							  [https://www.androidcentral.com/google-pixel-4a-5g-vs-pixel-4a](https://www.androidcentral.com/google-pixel-4a-5g-vs-pixel-4a)
					- [4a](https://www.gsmarena.com/google_pixel_4a-10123.php) (released Sat, Aug 1, 2020) | £315 price Mon, Nov 30, 2020
					  collapsed:: true
						- Specs
							- Screen 5.8"
							- 6GB RAM
							- 128GB storage
						- Differences to 4
						  [https://cdn.mos.cms.futurecdn.net/RDqzGXMXLuxmiyiHf28U3V.jpg](https://cdn.mos.cms.futurecdn.net/RDqzGXMXLuxmiyiHf28U3V.jpg)
							- Weaker CPU
							- Half the price
							- 1 rear camera instead of 2
							- Reviews basically say that 4a is far better value
								- [https://www.androidcentral.com/pixel-4a-vs-pixel-4](https://www.androidcentral.com/pixel-4a-vs-pixel-4)
						- Something to be aware of when considering a purchase of this device, is the fact that Google will stop providing security updates after August of 2023. GrapheneOS will also stop doing so after that date. This means you'll get a maximum of 2 years of usage out of this phone.
					- [4](https://m.gsmarena.com/google_pixel_4-ampp-9896.php) (released Tue, Oct 1, 2019)
					  collapsed:: true
						- Specs
							- Screen 5.8"
							- 6GB RAM
							- 128GB storage
					- 3
					  collapsed:: true
						- See [Google Pixel 3](https://workflowy.com/#/d87f6689003f)
					- 2
					- [1](https://www.gsmarena.com/google_pixel-8346.php) (released Sun, Jan 10, 2016)
					  collapsed:: true
						- _See_ [Google Pixel (first gen)](https://workflowy.com/#/96f310804583)
						- Specs
							- Screen 5"
							- 4GB RAM
							- 128GB storage
			- Fairphone line
			  id:: 649b13cb-4bf6-46f3-9f65-5419728ccc6b
			  collapsed:: true
				- Pros/Cons
				  collapsed:: true
					- Pros
						- Modular - easy to repair, replace parts like battery, and upgrade
						- They support updating to Android OS versions which are out of OEM support (especially Qualcomm since they only provide 2-3 years support)
						- Supported by [LineageOS](https://wiki.lineageos.org/devices/#fairphone)
					- Cons
						- Generally worse specs than flagship phones
						- Their OS updates come later than most brands
						- Lacks hardware killswitches, unlike ((649b13cb-e023-4f42-a55c-a6539fd2c2a4))
				- Fairphone 2
				  id:: 649b13cb-8880-4248-a8c8-f9cf2ea8ae56
				  collapsed:: true
					- https://www.fairphone.com
					- https://forum.fairphone.com
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Modular, but limited
							  collapsed:: true
							  Easy to repair, some upgrading possibly but not main focus
								- Company's intention is easy replacement of damaged parts, not necessarily upgrading existing parts
								- The phone consists of 7 removable parts
								  http://i.imgur.com/eUt3Jo2.png + case
									- the main chassis, the removable battery, the display assembly, rear camera module, receiver/top module (5), the speaker/bottom module and back protective cover.
									- 7 modules (detailed)
										- 1. The external case, of which multiple variations are possible
										- 2. The replaceable battery pack
										- 3. The transceiver (or core unit), which is the core of the system. It includes the main chipset, memory and flash storage, modem, radios and antennas, the SIMs and MicroSD card holders, motion sensors and power management. It contains most of the expensive electronics and networking functions.
										- 4. The display unit, which includes the main LCD module, touch sensing driver and a 0.7mm-thick Gorilla® Glass 3 lens.
										- 5. The receiver unit, which includes the receiver, headset connector, front-facing camera, noise-cancelling microphone, ambient light and proximity sensor and the notification LED.
										- 6. The rear camera unit, which includes the rear camera and flash.
										- 7. The speaker unit, which includes the speaker, vibration mechanism, main microphone and USB connector.
								- More info
									- Phone’s modularity is not computer’s modularity. Not even close.
									- The FP2's modularity is mainly means to reduce e-waste and increase repairability. Future upgrades are possible, but at some point it will surely be more feasible to create a new - more modular - phone. E.g. the addressed upgrade to the core module may never come as designing it would take a lot of time and money which may be better spent designing a new fairer phone.
									- It is already very easy to replace and upgrade Fairphone 2 components, we will go even further with version 3. We would like it is possible to change even more, like the processor or the internal memory, which is not yet possible."
									- https://forum.fairphone.com/t/fairphone-3-hardware-and-obsolence-discussion/10522/9
									- > Ideally the motherboard, processor and modem are modular
									- Seeing FP2 as a modular phone with upgradable modules is a bit of a pipe dream IMO. Repairability is what comes first. Upgrading some core component like the chipset requires new memory and a new motherboard as well and all that needs to integrate with existing hardware too. You'd probably be better off developing/buying an entirely new phone.
									- FP2 was a first step in modularity and upgrades will probably come (they are working on a camera upgrade already), but there is a limit. The core module with the motherboard will probably be the limit, as new chips won't fit into the current design of the module.
									- So FP3 will come one day, but nobody knows when yet.
									- Obsolescence affected by SoC chip producers e.g. Qualcomm
										- Maybe one day in the far future Fairphone will even design their own chips and make it possible to keep upgrading the same set of modules forever.
										- chip producers like Qualcomm. In the long run, FP will depend on community projects or will need to do porting by itself - and if security updates stop, and the SoC is left behind by Qualcomm, you are sooner or later fu\*\*\*ed.
										- depend on on the SoC manufacturer for drivers.
										- If you really want to become independent you would need to make your own hardware (i.e. chips), and preferably doing that in an open source design.
							- Fairphone Open OS allows easy rooting
						- Cons
							- Fairphone 3 likely out in late 2018
							- Not open hardware, so somewhat expensive replacement parts + they may eventually go out of business
					- Hardware specifications release poll
					  https://forum.fairphone.com/t/poll-should-fairphone-allow-the-development-of-third-party-hardware-modules-for-fp2/9455
					- Hardware baseband isolationist
					  collapsed:: true
						- Open processor has one viable candidate the A20 https://www.crowdsupply.com/eoma68/micro-desktop/updates/picking-a-processor
						- Fairphone question about hardware baseband isolation
							- Not sure if worked on MASTER. Try Chromium
							- https://fairphone.zendesk.com/hc/en-us/requests
							- Hello, I created a post on your forum but I realised that it's a community forum and instead I would like an official response from your team.
							- Is this something that your team intends to do in the future? Not open-source baseband, but instead hardware isolation: https://forum.fairphone.com/t/fairphone-baseband-os-firmware/1228/28
						- Requires a new SoC
							- "As the modem is integrated in the system-on-a-chip (SoC), this would currently mean replacing the entire core module. Apparently there is either no production benefit to moving the baseband modem away from the SoC (as virtually nobody does this), even though it would have privacy/security benefits (see also the discussion [here](https://forum.fairphone.com/t/fairphone-baseband-os-firmware/1228/28?u=johannes) ). Perhaps one day we'll see replaceable baseband modems or baseband modems with a hardware kill switch (like the wifi switch on some laptops)."
							  https://forum.fairphone.com/t/a-lot-to-do-for-fp3-mains-cost-ram-storage-ip68-cover-cost-thickness-weight/19851/32
						- Also consider that Neo900 costs around £1000
							- Fairphone 3 would cost even more as it has proprietary modules, better specs, slim design
					- https://shop.fairphone.com/en/
					- 1 Backlink
					  collapsed:: true
						- See [Fairphone 2](https://workflowy.com/#/9abb5dff2c4c)
				- Fairphone 3
				  collapsed:: true
					- Pros/Cons
						- Cons
							- Requires Halium to run mobile Linux (Ubuntu Touch). PinePhone comparatively doesn't need this hardware abstraction layer and instead just runs mainline Linux
							- Doesn't support a specific Wi-Fi feature
							  [https://forum.fairphone.com/t/why-the-snapdragon-632-processor-choice/55899/11](https://forum.fairphone.com/t/why-the-snapdragon-632-processor-choice/55899/11)
				- Fairphone 4
				  collapsed:: true
				  id:: 635037cc-9ee5-4b8f-9dbb-abf07858ad32
					- Pros/Cons
						- Pros
							- Supported by postmarketOS (alpha)
							  [https://wiki.postmarketos.org/wiki/Fairphone*4*(fairphone-fp4)](<https://wiki.postmarketos.org/wiki/Fairphone_4_(fairphone-fp4)>)
							- See [CalyxOS supports Fairphone 4](https://workflowy.com/#/9fbd965e808e)
							- Supports ((63219e34-cda2-4a69-a2c8-b74b33cf9a91))
							- Removable battery
							- Supports eSIM and 5G
							- Has a microSD card slot
							- 5 year warranty
							- Dual cameras
							- IP54 (water resistant)
							- Apparently has a relockable bootloader
							  [https://forum.fairphone.com/t/does-fp4-have-secure-boot-or-verified-boot-yes/76686/12](https://forum.fairphone.com/t/does-fp4-have-secure-boot-or-verified-boot-yes/76686/12)
						- Cons
							- Android 11 base - [Android 12](https://workflowy.com/#/b811bc7ac61a) means that the device runs with a <a href="https://workflowy.com/#/1bfe537b404f">Generic Kernel Image (GKI)</a>, which I'm not sure if FP4 does. Android 12-based phones should be able to run mobile Linux quite easily
							- Qualcomm Snapdragon 750G (SM7225) SoC - means support for firmware/kernel updates will only last up to September 2023
							  [https://www.privacyguides.org/android/#fairphone](https://www.privacyguides.org/android/#fairphone)
							- Hasn't got 6 GHz band Wi-Fi - though it can just USB tether to give my laptop internet
							- No headphone slot
							- Has a notch
							- 6.3" - slightly bigger than Pocophone F1 which is already big to hold
							- Poorer mobile Linux support will be an issue as Android gets more locked down due to Fuchsia and ((649b13d2-3bf6-43ed-b52c-7bbcf094ca3c))
					- General Fairphone pros/cons
						- Pros/Cons
			- ### Supports Linux
			  id:: 67c208a7-44aa-4cc0-ae52-019d8d51e1d8
				- PinePhone line
				  id:: 649b13cb-e023-4f42-a55c-a6539fd2c2a4
				  collapsed:: true
					- General PinePhone Pros/Cons
						- Pros
							- Cheaper ($400 for Pro)
							- Slightly modular and easily repairable
							  id:: 644c0acb-3ce9-4f51-b07b-0973381a8057
							- Runs mainline Linux
							  id:: 644c0acb-77cc-4f0a-b65c-7c53364525f4
								- So software updates could be even longer than 5 years potentially
							- Can run Android via Waydroid (basically a container) or GloDroid (Android builds for the SoC)
							  collapsed:: true
								- GloDroid
									- Pros/Cons
										- Cons
											- _Lacks_
												- Modem stuff
												  collapsed:: true
													- Cellular call
													  [https://github.com/GloDroid/glodroid_manifest/issues/159](https://github.com/GloDroid/glodroid_manifest/issues/159)
													- Radio initialisation
													  [https://github.com/GloDroid/glodroid_manifest/issues/157](https://github.com/GloDroid/glodroid_manifest/issues/157)
													- GNSS
													  [https://github.com/GloDroid/glodroid_manifest/issues/104](https://github.com/GloDroid/glodroid_manifest/issues/104)
													- USSD
													  [https://github.com/GloDroid/glodroid_manifest/issues/158](https://github.com/GloDroid/glodroid_manifest/issues/158)
												- Android stuff
												  collapsed:: true
													- OTA updates
													  [https://github.com/GloDroid/glodroid_manifest/issues/38](https://github.com/GloDroid/glodroid_manifest/issues/38)
													- GApps support
													  [https://github.com/GloDroid/glodroid_manifest/issues/77#issuecomment-727545261](https://github.com/GloDroid/glodroid_manifest/issues/77#issuecomment-727545261)
													- microG support
													  [https://github.com/GloDroid/glodroid_manifest/issues/126#issuecomment-766171609](https://github.com/GloDroid/glodroid_manifest/issues/126#issuecomment-766171609)
												- Hardware acceleration
												  [https://github.com/GloDroid/glodroid_manifest/issues/152#issuecomment-947439059](https://github.com/GloDroid/glodroid_manifest/issues/152#issuecomment-947439059)
												- Builds are debug-only, which decreases security
												  [https://github.com/GloDroid/glodroid_manifest/issues/97#issuecomment-846887263](https://github.com/GloDroid/glodroid_manifest/issues/97#issuecomment-846887263)
										- Unclear
											- Does camera work?
									- [https://github.com/GloDroid/glodroid_manifest](https://github.com/GloDroid/glodroid_manifest)
							- Waydroid can be used for running Android apps with great performance side-by-side with your Linux apps
							- Less closed-source firmware, so lower risk of compromised chips
							- Hardware killswitches for modem, bluetooth, etc
							  id:: 644c0acb-f24c-497c-a7a2-6b7b24742fb4
							- Supports ((63219e34-cda2-4a69-a2c8-b74b33cf9a91))
							- [There's a compatible keyboard case for it](https://liliputing.com/2021/08/pine64-news-roundup-pinephone-keyboard-goes-on-sale-in-september-ubuntu-touch-20-04-is-coming-and-visual-voicemail-arrives.html)
							  collapsed:: true
								- [https://www.notebookcheck.net/Pine64-s-new-keyboard-case-turns-the-PinePhone-into-a-pocketable-Linux-laptop.535230.0.html](https://www.notebookcheck.net/Pine64-s-new-keyboard-case-turns-the-PinePhone-into-a-pocketable-Linux-laptop.535230.0.html)
							- Android will eventually try to kill Linux support in favour of ((649b13cf-a825-48f5-ae83-b47b6ad6bff9)) [1] which will lock down the ecosystem more, so mobile Linux will be the only open alternative in the future
							  collapsed:: true
								- Google has developed a new kernel (lower level of software below the operating system) called ((649b13cf-a825-48f5-ae83-b47b6ad6bff9)) and have replaced the Linux kernel on one of their devices already with it. Expect them to do the same on their Pixel phones in the next 2-5 years. After that the rest of Android manufacturers will follow and stop supporting Linux, because Fuchsia's license allows them to stop open-sourcing their firmware and thus limit their customers' ability to run software of their choice on these phones.
								- Once that happens expect Android to quickly start becoming more locked down and proprietary, similar to iOS. Custom ROMs are unlikely to run on many Android devices, and if it happens to Pixels too then projects like GrapheneOS and CalyxOS will have to use similar hardware to PinePhone anyway in order to find a SoC which allows flashing a custom OS.
						- Cons
							- [No longer supports other Linux distributions than Manjaro](https://news.ycombinator.com/item?id=32494659)
							- Waydroid is beta quality - there are some limitations like being unable to use camera and mic in Android apps
							- Mobile Linux software is alpha quality
							  collapsed:: true
								- [Mid-2022 - battery performance is very poor. However phone calls mostly work and SMS](https://youtu.be/GSfR3uHbh60)
								- [PINE64 aren't investing much into software, but Purism does](https://youtu.be/GSfR3uHbh60?t=527)
								- Mobile Linux OSes are alpha quality - it's got a long way to go in terms of UX, security features, app support, etc
								- The software has got a longgg way to go before it becomes comparable to Android
								- Even KDE is still lacking comparing to mainstream OS's (if you contrast this against the desktop space)
								- ((63a9ade4-ad80-4f73-ad36-483fb022f583)) allows running Android easily
								- ((649b13d1-9916-4123-b233-28fa415ea885)) in Flatpak and Snap is weak compared to Android, and apps can opt out of it
							- No multi-year support guarantee (though since it runs mainline Linux it'll be multi-year regardless)
							- It still has some closed-source firmware
							  See [It has very little closed-source firmware](https://workflowy.com/#/402a71dc1831)
							- Doesn't support Verified/Secure Boot, unlike Pixels with GrapheneOS/CalyxOS
							  collapsed:: true
								- [archived] [https://daltondur.st/secure_pinephone_1/](https://daltondur.st/secure_pinephone_1/)
					- $400 PinePhone Pro
					  id:: 635037cc-acae-433a-8e7d-a8b89379fa9d
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Better hardware now
							- Cons
								- Hardware is not comparable to mid-range 2021 Android phones, since they require open CPU firmware to support Linux
							- Unclear
								- See [It has very little closed-source firmware](https://workflowy.com/#/402a71dc1831) (on PinePhone, unconfirmed for Pro)
								- ((649b13ca-0417-44e6-ab64-fa0ebae72f22)) ?
								- 5G?
					- $150 PinePhone by Pine64
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Pros
								- It has very little closed-source firmware
								  source:: [https://www.pine64.org/2020/01/24/setting-the-record-straight-pinephone-misconceptions/](https://www.pine64.org/2020/01/24/setting-the-record-straight-pinephone-misconceptions/)
								  collapsed:: true
									- **Here’s what’s open**
										- Let’s start with the Allwinner A64 SoC, which is the brains of the PinePhone; it runs mainline Linux, uses [mainline ATF](https://developer.trustedfirmware.org/dashboard/view/6/) and u-boot and there are open source drivers for all main SoC components. This openness extends to the <a href="https://cgit.freedesktop.org/drm/drm/commit/?id=a1d2a6339961efc078208dc3b2f006e9e9a8e119">Lima GPU driver introduced in kernel 5.2</a>.
										- Linux 5.6 will contain drivers for all major components of the SoC.
										- The parts which still need to be upstreamed to mainline are HDMI audio and msgbox – both drivers are in the works. For more information on mainlining efforts, please refer to the A64 column at [https://linux-sunxi.org/Linux_mainlining_effort#Status_Matrix](https://linux-sunxi.org/Linux_mainlining_effort#Status_Matrix)
										- It’s worth mentioning that LPDDR3 initialization is done by u-boot SPL, which is also open source. There are no blobs in there either.
									- **So, where are the blobs?**
										- The non-FOSS parts of the phone are as follows: WiFi and Bluetooth firmware must be uploaded to the Realtek RTL8723cs on initialization, an optional auto-focus firmware (currently not used in any PinePhone OSes) can be uploaded to the rear OmniVision OV5640 camera, and the Quectel EG25-G LTE modem runs its own closed-source OS.
										- The WiFi module communicates with the CPU over SDIO and BT is over UART – neither of these connections provide direct access to CPU memory.
										- The LTE modem on the PinePhone is a ‘black box’, and runs its own Linux system internally. This includes all the proprietary modules (blobs) needed to run the actual cellular radios. However, this system is almost entirely isolated from the main system running on the A64 SoC. The only data contacts between A64 and modem are USB connection for data and I2S connection for audio. All data going in or out of the modem must go over these connections.
										- There is no RAM or flash storage shared between the systems. In short, unless you explicitly send data to the modem, it is never in contact with the blobs running inside it. The modem cannot send any data to the phone unless phone is willing to receive it (that’s the basics of USB).
									- 2 Backlinks
										- It still has some closed-source firmware
										  See [It has very little closed-source firmware](https://workflowy.com/#/402a71dc1831)
										- See [It has very little closed-source firmware](https://workflowy.com/#/402a71dc1831) (on PinePhone, unconfirmed for Pro)
								- "separate cellular modem from the SoC"
								  source:: Discord
							- Cons
								- Why get a phone with poor performance hardware? I won't use it
								- _Cons compared to Librem 5_
									- Allwinner A64 is less libre than Librem's i.MX since Allwinner have violated GPL several times
									- i.MX8 is significantly more powerful than A64
									- Librem is trying to get rid of all blobs e.g. RAM calibration routines will run on a separate CPU from main CPU
									- Librem 5 likely to be the first and only FSF RYF-certified phone. It uses a secondary processor for some binary blobs to still achieve RYF
						- Also
						- FOSS firmware being developed
						  collapsed:: true
							- Nutcracker Challenge: Blob-Free WiFi & BLE
								- BL602 evaluation board (EVB) – which we have codenamed PineCone
								- WiFi & Bluetooth Low Energy
								- Repos
									- SDK
									  [https://github.com/pine64/bl_iot_sdk](https://github.com/pine64/bl_iot_sdk)
									- Reverse engineering
									  [https://github.com/pine64/bl602-re](https://github.com/pine64/bl602-re)
									- Documentation
									  [https://github.com/pine64/bl602-docs](https://github.com/pine64/bl602-docs)
							- FOSS modem firmware being developed
								- [https://github.com/Biktorgj/pinephone_modem_sdk](https://github.com/Biktorgj/pinephone_modem_sdk)
								- [https://wiki.pine64.org/wiki/PineModems#Modems_used_in_Pine64_boards_and_devices](https://wiki.pine64.org/wiki/PineModems#Modems_used_in_Pine64_boards_and_devices)
								- 1 Backlink
									- See PinePhone [FOSS modem firmware being developed](https://workflowy.com/#/a1bc2d40ff7f)
						- Built for KDE Plasma Mobile
						- https://itsfoss.com/pinebook-kde-smartphone/
						- Specs
						  collapsed:: true
							- The PinePhone separate out SoC and LTE module due to mainline binary blobs and GPL concern.
							- The phone will strictly be running mainline Linux and it will be powered by a SOPine module with an Allwinner A64 ARM Cortex-A53 quad-core processor.
							- It has a 1440x720p IPS display and the phone looks like your regular Android smartphone. On the back, it has a 5MP camera and a 2MP camera on the front.
							- The Linux-based phone packs 2GB of LPDDR3 RAM, a 32GB eMMC module, and 4G LTE Cat 4 support. On the connectivity front, it has 802.11n WiFi and Bluetooth 4.0.
							- The phone also comes with a headphone jack and sensors including a gyroscopic sensor and light sensor.
							- Pine64 aims to provide physical switches through this phone to allow users to disable or enable the wireless components, cameras, and speaker for privacy.
						- Pine64 board is not fully open source hardware
						  source:: [Hardware Source](https://forum.pine64.org/showthread.php?tid=165)
						  collapsed:: true
							- Schematics open but we do not release Gerber file.
							- we will post schematic but not PCB layout source file. However, we can post the PCB image file.
							- only the schematic, but not the layout will be published.
							- We did not see the reason of release PCB source file is necessary. In general, schematic and PCB image file already enough for board modification which I have been practiced for more than 30 years.
								- One main reason is we don't mind DIY modify the board for their project needs but we don't plan to support the modified board such as optimized DRAM path for overclocking.
								- Pine64 is NOT an open source hardware project
					- Related: ((63412f42-1797-4d76-9607-7351eafe4f40))
				- [SHIFT6mq](https://shop.shiftphones.com/shift6mq.html) (compatible with postmarketOS)
				- ((635037cc-5575-4925-90f0-6b9ffcd6a48c)) + ((635f89a0-abea-4909-a421-ef8f32614d28))
				- [FLX1 - FuriPhone FLX1 Linux Phone](https://furilabs.com/shop/flx1/)
				-
			- 2021: 128GB storage minimum as that's how much I currently use
		- Anti-features
			- The notch
			  collapsed:: true
				- Though Pixel 3 at least allows hiding it through software
				- Solutions
					- Nacho Notch - blends it into status bar
					  https://www.xda-developers.com/hide-notch-huawei-p20-essential-phone-oneplus-6-asus-zenfone-5/
			- Glass back for wireless charging
			  collapsed:: true
				- Easier to break (planned obsolescence)
				- https://www.theverge.com/circuitbreaker/2018/10/10/17958760/google-pixel-3-xl-design-glass-aluminium-smartphone
				-
		- # By attributes
			- ((649b13d1-a8c5-4f57-b5a7-d505dd2c6f2a)), ideally libre (e.g. Replicant or Sailfish OS)
			- ((63209286-6f40-4063-9fdc-2543251d416e)) support
			- DisplayPort alt-mode (video output over USB)
			  id:: 63219e34-cda2-4a69-a2c8-b74b33cf9a91
			  collapsed:: true
			  AKA DP Alt Mode
				- (Allows you to run a desktop OS from your phone (e.g. like ((63219e35-31c8-4454-9e84-be51a2684aae)), a full Linux desktop, etc)
				- Needed for ((64e0946d-1d0e-4824-b150-1a08f26aba23)) display support. Is used for various convergence OS like Samsung DEX etc
				  #TravelGearWishlist
				- [https://en.everybodywiki.com/List_of_devices_with_video_output_over_USB-C#Smartphones
				- Most Pixel phones likely don't include it so it doesn't take away from Chromecast sales
					- Plus Pixel tablet sales in 2023
			- _Basic minimum specs required_
				- Battery
				  Samsung S5 = 2800 mAh
				- 4+ core CPU
				  collapsed:: true
					- Very popular SoC
					  e.g. chip supplier Qualcomm needs to prep chip for newer Android versions
				- 4GB+ RAM
				  2GB = Samsung S5
				- Display/size - 4.5"+
				  collapsed:: true
					- 4.5"+
					  5.1 inches = Samsung S5
					- 4K screen? (for VR)
				- Cameras
				  collapsed:: true
					- Primary
					  Samsung S5 = 16 MP, f/2.2, 31mm, phase detection autofocus, LED flash
					- Secondary
					  Samsung S5 = 2 MP, f/2.4, 22mm, 1080p@30fps, dual video call
			- Unlockable bootloader (to allow custom recovery and ROM)
			  collapsed:: true
				- Xiaomi Pocophone F1
				- See [Fairphone 2](https://workflowy.com/#/9abb5dff2c4c)
				- Google Pixel 3
					- Cons
						- DRM restricts Qi charging to their own products
						  https://news.ycombinator.com/item?id=18284361
					- Differences to 2
						- Only new hardware is: another selfie camera, glass back for wireless charging, Titan chip, and is now ip68 from ip67.
						- Titan chip for security also used in their servers
							- https://www.anandtech.com/show/13248/hot-chips-2018-google-titan-live-blog-6pm-pt-1am-utc
				- See LineageOS supported deices
			- microSD card slot
			- Repairability
			  id:: 67c0581b-c947-4e3e-b7cc-4dffddcbbf73
			  collapsed:: true
				- This phone can be easily unscrewed
					- [Every Phone Should Copy This! - YouTube](https://www.youtube.com/watch?v=FmmUAhE6MxU)
				- ((649b13cb-4bf6-46f3-9f65-5419728ccc6b))
				- Related: ((649b13cb-7080-424b-98c7-2d158a44d0f1))
			- _Removable battery_
			  id:: 649b13cb-7080-424b-98c7-2d158a44d0f1
			  collapsed:: true
				- Removable Battery
					- Pros
						- Emergency battery
						  collapsed:: true
							- Many times you may be out all day, or unexpectedly stay overnight someplace else where you haven't got the opportunity to charge your phone
							- Or you may not be in a place during the day/night where you'd like to leave your phone away out of your pocket (privacy/security/ease)
							- Or you are out all day/night then want to play music bluetooth on someone's speakers
						- If your phone is frozen.
						  collapsed:: true
							- A lot can be said about the advantages of modern day cell phones, but due to the complexity of the way they work they sometimes freezes. No matter what you do it simply won’t respond. The fastest and easiest fix for this problem is to remove the battery for a second. This way ,when you reenter the battery and boot your phone again it will most likely work like a charm again. If it does not you will most likely have to buy a new phone or have it sent to a service center.
						- Water damage can be minimised by removing a battery quickly
						  collapsed:: true
							- The first thing you should do if your phone gets wet is to remove the battery. This way you will minimize the chances of your phone being ruined forever. If you can get the battery out before something shorts out you will be on the right track towards saving your phone. The next thing you should so is to put it in a bowl of dry rice for a few days. Through the miracle of osmosis, the rice will “pull” the water out of your phone.
						- Much cheaper to replace deteriorating battery
						  collapsed:: true
							- As your battery charges it slowly deteriorates. After a year or two your battery will most likely have lost much of it’s ability to retain that all important battery juice. If you got a phone with a replaceable battery you could simply buy a new one and replace it quite simply. If your battery is unreachable you will likely have to pay someone a lot of money to have it replaced or even more expensive option, buy a new phone.
							- It’s planned obsolescence. Disposable phones.
						- Turn off tracking
						  collapsed:: true
							- Supposed you would like to get of the grid for whatever reason, and you would like to bring your phone with your. Remove the battery. This way your phone will stop transmitting, due to the lack of power.
						- Higher resale value
						  collapsed:: true
							- Resale, the biggest advantage of a user replaceable battery. Want to upgrade your phone, what happens when everyone knows that it is at the end of it’s battery life, that cost of replacing the battery will come off the resale price.
							- Tell them you just did it, no one will believe you. With a user replaceable phone that means dropping $20 to $30 dollars on the price, embedded phone $150 – $200 gone.
							- Fixed batteries is all about killing resale, nothing more than that.
						- Allows using bigger battery/cases
						  collapsed:: true
							- http://www.androidpolice.com/2014/12/23/zerolemons-10000mah-extended-battery-will-turn-your-galaxy-note-4-into-an-everlasting-brick-for-60/
					- Cons
						- Lower water resistance
					- _Myths_
						- Removable back can't be full-metal and premium look
							- LG G5 looks great
				- 2018
				- 2017/16
					- [LG V20](https://www.gsmarena.com/compare.php3?idPhone1=7815&idPhone2=8238&idPhone3=8712#diff-*,h990ds,h930)
					- LG G5
					  collapsed:: true
					  [LG G5 - Full phone specifications](http://gsmarena.com/lg_g5-7815.php) H850 = EU rootable version
						- LG G5
							- Version
								- LG H850, single SIM and bootloader unlockable
								- Titan grey
							- Specs, guides, info etc
							  intralink2:: https://workflowy.com/#/fae8b37aa0aa
							- _My phone IDs_
								- Phone 1
									- 357657076223706
									  IMEI
									- 04DC2B5382C9D810E008E0B0600B9C730043DE94F1D82B6D3B2972F726B4DD5F
									  Device-ID
								- Recent replacement attempts
								  Very difficult to find an EU one (bootloader unlockable)
									- 1
									  didn't work with myiD network
									- 2
									  australian
										- 357657071347807
										  IMEI
										- 741331A4A9DF86DB23EF737717EC37890547B361C7A858580A0D149CD6E200B9
										  Device-ID
									- 3
									  UK - amazon. Was delivered 'IOT_H850_Marketing' which is a sample model for marketing and not compatible with bootloader unlocking unlike normal LG G5 UK phones.
										- 357657070111816
										  IMEI
										- 10432F6C1068BB7F9D95F70CE07406BB86B4669315F39715C245FF693ADEAD82
										  oem device-id
							- Guides/How-to
								- e.g. LG G5
								  intralink2:: https://workflowy.com/#/84fecb8bde17
								- _Setting up a custom ROM + rooted_
									- First unlock the bootloader
									  https://forum.xda-developers.com/lg-g5/development/official-european-lg-g5-h850-bootloader-t3363040
										- http://developer.lge.com/resource/mobile/RetrieveBootloader.dev
											- Enable USB debugging + OEM un
											- Get the IMEI number
											- Open 'cmd' in Minimal ADB and Fastboot portable folder
												- adb reboot bootloader
												- fastboot oem device-id
											- Likely need to use Google Chrome and/or new account each time
									- Boot into stock recovery mode and flash TWRP recover, then SuperSU
										- Download the recovery img https://dl.twrp.me/h850/ and put it in Minimal ADB and Fastboot portable folder
											- adb reboot bootloader
											- fastboot flash recovery recovery.img
										- For TWRP to "stick" you must first boot directly into TWRP and not back into Android, until after flashing the SuperSU zip.
										- After flashing TWRP unplug the USB cable and pull the battery. Plug battery back in then boot into recovery which should hopefully load TWRP.
										- To boot into recovery:
											- a. Using 2 hands.. use one hand/finger to press/hold volume down.. and use the other hand for the power button. Press n hold both buttons.
											- b. As soon as you see the LG logo on the screen.. let go of the power button then quickly press it again (never letting go of volume down).
											- c. Keep holding until you see the Factory Reset screen. Click thru the factory reset screens.. Yes.. Yes...
										- 10. You will not be able to decrypt your internal data while in TWRP (unless performing a full /data wipe in TWRP and you will lose encryption!) but you can manually mount your external SD card to view the SuperSu zip. Feel free to back up first.. but otherwise.. time to install SuperSu. Click the Install button and navigate to the external_sd, select the SuperSu zip then swipe to install. Now you're rooted and TWRP'd! Reboot into system...
										- Make /system read-only
										- Have SuperSU zip on a microSD and 'install' it
									- Boot into TWRP recovery and do a nandroid backup
										- "Backup" button. After that, you see a list of check boxes—make sure that the "Boot," "System," and "Data" options are selected here
									- Then flash/install LineageOS
										- https://wiki.lineageos.org/devices/h850/install
									- Don't want root but want to keep TWRP? Then just swap the SuperSU zip with this zip: no-verity-opt-encrypt-4.1.zip
									- Then flash/install <span>GApps</span>, F-Droid Privileged and SuperSU
										- ((6318fc66-9d9f-4547-8e1c-172958500c0d))
											- https://wiki.lineageos.org/gapps.html
											- Lineage 14.1 (Android 7.1)
											  http://opengapps.org/?api=7.1&variant=nano
									- Restore Titanium backup
										- Install Titanium + pro key via google play store
										- In preferences point to microSD folder
										- Batch actions > restore
								- _Reset to stock condition_
									- Flash the stock ROM
										- LG G5
										  intralink2:: https://workflowy.com/#/84fecb8bde17
										- Stock ROMs
											- http://downloads.codefi.re/autoprime
											- https://android.stackexchange.com/questions/17152/where-can-i-find-stock-or-custom-roms-for-my-android-device
										- or find the correct kdz for you device
									- Flash the stock recovery
									- Relock the bootloader
										- In Minimal ADB
											- adb reboot bootloader
											- _Lock via any one:_
												- fastboot oem lock
												- fastboot flashing lock
												- fastboot oem relock
											- fastboot reboot
											  Reboot device
						- Cost
							- £320 refurb/used in Nov 2016 on eBay
							  £365 brand new
							- April 2017 - paid £360 new via eBay
							- Phone : LGH850 -
								- IMEI or MEID : 357657070236597
								- Device ID : 356F0E657E0A91CCEF614B331F46897F6F17F3F287DDF81DBD1C8030F580A187
						- Pros/Cons
							- Pros
								- Great camera
								  Superior to Galaxy S7 + iPhone 7 according to GSM arena
								- Removable battery
								- Decent RAM + CPU
							- Cons
								- Ideally 6GB RAM like G6
								- No waterproof
						- Guides/Tools
							- Assorted info
							  https://forum.xda-developers.com/lg-g5/how-to/info-autos-g5-thread-t3350648
							- Where to get LG G5 ROMs
								- Stock ROM
									- http://downloads.codefi.re/autoprime/LG/LG_G5/H850/
									- https://forum.xda-developers.com/lg-g5/development/stock-h850-20d-eu-rom-flashable-zips-t3592762
									- https://docs.google.com/spreadsheets/d/1ANmGSVJo1_5x5urQvTfyfrIc7smiL6yrFDNZ4Ao_pfs/edit#gid=1166065548
									- find the correct kdz for you device, or use Lg bridge/ LG UP to get back to stock.
					- Samsung Galaxy S5 (G900F)
					  collapsed:: true
						- http://www.gsmarena.com/samsung_galaxy_s5-6033.php
						- Cost: currently £150 from eBay
						  August 2016
							- £230 from eBay
							  February 2016
						- _Features_
							- dustproof and waterproof
							- removable battery, 2GB ram, 16MP camera
							- 4G compatible model is G900F for Europe - international version and has LTE compatibility for most locations in Europe, Asia, Australia and Canada
						- _Guides_
							- Download TWRP + lineageOS for device model
					- ((649b13cb-4bf6-46f3-9f65-5419728ccc6b))
					- https://www.productchart.com/smartphones/sets/3
				- Related: ((67c0581b-c947-4e3e-b7cc-4dffddcbbf73))
			- eSIM
			  id:: 649b13ca-0417-44e6-ab64-fa0ebae72f22
			  collapsed:: true
			  AKA embedded SIM
				- eSIM support (easy subscribing for local SIM when in a foreign country)
				- Pros/Cons
					- Pros
						- Theoretically, eSIM should mean that you could go to another country and simply add a roaming eSIM to your handset while retaining access to your main "home" number. That's one of the disadvantages currently because, if you change SIMs abroad, for example, you can't access your own number.
						- “eSIMs have the potential to eliminate roaming charges abroad", says Truphone's Steve Alder. "It also enables people to switch operators quickly to get connected if they’re in an area with no signal, frees up space for new features or additional battery life and could lower the risk of device theft.
					- Cons
						- (If you're limited to 1 carrier at a time) Possibly greater lock-in if your carrier is being difficulty about switching you
						- If you don't additionally have a physical SIM slot - more difficult when traveling to other countries if they don't support eSIMs also
				- # Getting eSIMs from local/international providers
				  id:: 649b13c9-210d-4b84-9e8c-4cba6e390193
				  collapsed:: true
					- ## ((63061153-6db2-4dcf-bffc-cab105ab529d))
						- [Lyca Mobile](https://www.lycamobile.co.uk/en/bundle/uk-plan-smart/) (£5/month)
						- There are some eSIM providers with 30 day contracts
						  collapsed:: true
						  [[Page not found - esims.io](https://esims.io/united-kingdom](https://esims.io/united-kingdom))
							- Airalo - 5GB $15
							- Simtex - 6GB $23
						- ### Doesn't support eSIM as of [[2024-11-13 Wednesday]]
							- Lebara
						- [Learning Resources]
							- [[Page Not Found - Ken's Tech Tips](https://kenstechtips.com/index.php/esim-on-uk-networks](https://kenstechtips.com/index.php/esim-on-uk-networks))
								- Cons
									- No provider has pay-as-you-go eSIM, only pay-monthly currently
							- [Compare eSIM for United Kingdom - Find the Best Travel Data Plans](https://esimdb.com/uk)
							- Others
							  collapsed:: true
							  [[Bad title - Wikipedia](https://en.wikipedia.org/wiki/List_of_United_Kingdom_mobile_virtual_network_operators](https://en.wikipedia.org/wiki/List_of_United_Kingdom_mobile_virtual_network_operators))
								- BT (doesn’t support eSIM for personal customers)
								- Virgin
								- Truphone (doesn't support 5G)
								- Out of the main four, I think it’s only Three that doesn’t support it
									- O2
									- Vodafone
					- ## International
						- Airalo
						  [https://play.google.com/store/apps/details?id=com.mobillium.airalo](https://play.google.com/store/apps/details?id=com.mobillium.airalo)
						- [esims.io](http://esims.io)
						- Ubigi
						- Simtex
						- Flexiroam
						- MTX Connect
					- [Learning Resources]
						- [https://esims.io/providers/](https://esims.io/providers/)
					-
				- SIM card that allows subscribing to eSIM providers
					- [https://blog.esper.io/android-dessert-bites-24-esim-me-1248143/](https://blog.esper.io/android-dessert-bites-24-esim-me-1248143/)
						- [https://esim.me/](https://esim.me/)
						- ..
						- Open-source eSIM manager
						  [https://gitea.angry.im/PeterCxy/OpenEUICC](https://gitea.angry.im/PeterCxy/OpenEUICC)
							- Implementing the EuiccService API is what makes the profiles downloaded by OpenEUICC show up in settings. OpenEUICC also has a rather basic UI, but because it has one, tapping the plus sign in Settings > Network & Internet invokes the app’s UI to download a new eSIM profile. However, AOSP’s Settings app does not probe for the existence of an LPA app unless the android.hardware.telephony.euicc feature is declared, so developers attempting to integrate OpenEUICC into their AOSP builds will need to take note of that.
							-
						- Android 13's Multiple Enabled Profiles is currently being integrated into OpenEUICC, and is currently incompatible with eSIM.me or other removable eUICC
						  [https://www.blog.esper.io/android-13-deep-dive/#multiple_enabled_profiles](https://www.blog.esper.io/android-13-deep-dive/#multiple_enabled_profiles)
				- Related:
					- ((6436ae2f-4aac-4d12-9ee3-add1862e15a4))
			- Baseband Isolation
			  id:: 649b13ca-7483-4a1d-bd90-89845f24084f
			  collapsed:: true
			  AKA Hardware baseband processor isolation / _baseband processor isolation_
				- Pros/Cons
					- Pros
						- Modems are commonly connected over an interface with direct memory access (e.g. PCIe). Instead baseband isolation relies on the USB stack
					- Cons
						- Linux USB stack (which is used instead of Direct Memory Access (DMA)) is arguably insecure too
					- Unclear
						- IOMMU groups may be sufficient
						  id:: 644c0acb-a922-4046-b811-c90172124515
							- Qualcomm SoCs have isolated the modem via an IOMMU for years.
							  [[DEF CON® 27 Hacking Conference Speakers](https://www.defcon.org/html/defcon-27/dc-27-speakers.html#Gong](https://www.defcon.org/html/defcon-27/dc-27-speakers.html#Gong))
							- Learning more about this it seems IOMMU is sufficient (it can be on the same SoC and still be separated) and that even it separated physically might not lead to isolation
							- Argued here that IOMMU makes the DMA access of modems not an issue, and that backdoors could just as likely be present in other SoC components like the WiFi or bluetooth firmware
								- [OP](https://www.reddit.com/r/CopperheadOS/comments/6wtul0/on_sensationalism_about_basebands_all_future/)
								  collapsed:: true
									- Like everything else, baseband security could be better, but I don't think it has the urgency / severity that's attributed to it vs. everything else. It's not a particularly weak spot in the security of Pixel phones. Airplane mode also does work properly for reducing the attack surface when it's not needed.
									- There are people that have done real research on it but there's not a lot that's up-to-date. Simply ignore sensationalist journalism glossing over the details and making false assumptions. Isolation of hardware components is more complicated than whether they have direct memory access. You can disregard anything portraying the baseband as being unique in that it runs a secondary operating system or has direct access to memory. It's something that applies to components like SSDs, WiFi, batteries, touchscreens, fingerprint readers and many others. Those components all effectively run a secondary OS and many have direct access to some of the memory including the GPU, image processor, WiFi, Bluetooth and cellular baseband. If they portray any of that as something unique, then it's clearly nonsense. Nearly all of that is closed source software too. Closed source doesn't mean it's any less secure, and even if it was open-source signature verification would usually prevent modifying it. It would only be safe to leave out signature verification for firmware loaded by the OS in early boot and that cannot be written afterwards.
									- Direct memory access doesn't imply full access to all memory. Snapdragon SoCs have IOMMUs for isolating hardware components with direct memory access and they're in active use. Qualcomm has the IOMMUs set up for their SoC components as a standard baseline. Similarly, the OS has direct memory access but is constrained. It can't access all memory just as hardware components generally can't access all memory. For components that aren't part of the SoC, it's the responsibility of other vendors to set up IOMMU isolation rather than Qualcomm. The quality of the isolation will vary. It's much more complicated that a black and white issue where there's either an IOMMU or no IOMMU. There can be an IOMMU with very tight restrictions providing proper isolation or a setup where the IOMMU is effectively not doing anything and permits access to all of the memory. Determining that requires real research. It would be nice if there was better documentation and more source code available but either way it would need to be verified on real hardware. If you don't have code execution on a component, then you can't really be sure if the IOMMU is working properly even if you can see that it's set up and seemingly doing something.
									- The baseband is meant to be isolated from the OS just as the OS is meant to be isolated from it. That can be contrasted with TrustZone which has access over the OS and the bootloaders leading up to loading the OS as they could load something else instead. Those are strictly more trusted components than the OS. It doesn't make them "backdoors" or inherently "compromised". Like everything else, they aren't perfect. There are bugs, some of which are security bugs. They aren't directly exposed to remote attack surface like the OS, WiFi, the cellular baseband, etc. Bootloader / TrustZone security primarily matters to verified boot.
									- Even though the WiFi chips on the Nexus 5X and Pixels are from Qualcomm (via Qualcomm Atheros), it isn't developed with the rest of the SoC and doesn't meet the same security standards. It might be a shared responsibility with the vendor like HTC / Google to set up the IOMMU for a peripheral (i.e. not part of the SoC) like WiFi. The WiFi drivers for Qualcomm Atheros are similarly not part of the Qualcomm Snapdragon platform (MSM) kernels but rather get added in by vendors shipping it on their devices. Those drivers (qcacld-2.0) are horrible are not on par with the quality of the other Qualcomm kernel drivers. Qualcomm acquired Atheros rather than developing it on their own and it's a lot different than their own SoC platform. Maybe one day they'll have it properly integrated into their processes and up to the same standards but for now it seems to be treated as a separate silo.
									- Cellular protocols are a lot more complex than WiFi but the baseband is in a better place in terms of security resources / standards that are applied to it. Is it perfect? Of course not. Since it's firmware with signature verification, it's inherently outside of what can be hardened by us even if the source code was available. It's important to note that source code availability doesn't directly impact privacy / security. It makes it possible for outsiders to contribute and it makes it easier for researchers to work with it but it doesn't make or break whether something can be audited, fuzzed, etc. Source code access can contribute a lot to security when it's done well. Lowering the barrier to entry helps independent security researchers and academics substantially while it makes little impact on a state actor with the resources to overcome obstacles to debugging even if they can't obtain sources and they likely can get them.
							- All phones arguably use IOMMU to achieve this already, though as a non-technical person this is hard to prove
							- Related:
								- ((644c0acc-16fa-4526-91aa-c590a321bb77))
								- ((649b13d1-e2a8-451b-bd09-44269a1b0ed5))
				- ((649b13cd-0859-4c2f-8ad3-28bfe496eeba))
				- _Phones with baseband isolation_
					- _Confirmed_
						- $600 Librem 5 by Purism (April)
						  id:: 635037cc-5575-4925-90f0-6b9ffcd6a48c
						  collapsed:: true
						  Libre SoC, CPU firmware
							- Pros/Cons
								- Pros
									- ((635f89a0-abea-4909-a421-ef8f32614d28))
									- 3 hardware killswitches and a easily removable modem
									  [https://puri.sm/posts/defending-against-spyware-like-pegasus/](https://puri.sm/posts/defending-against-spyware-like-pegasus/)
										- Hardware Kill Switches for Camera, Microphone, WiFi/Bluetooth, and Baseband
									- CPU separate from Baseband
										- By decoupling the baseband from the CPU so that it can't directly access the OS's memory+busses and securing communication on the wire (defaulting to secure messaging over Matrix, and using SSL everywhere) so that it can't be sniffed in transit by the modem.
										- I'm guessing that what this ends up looking like is a USB modem talking to the OS with pppd or a similar model that also enables voice calls over LTE
									- Kernel is updated frequently unlike Android phones since the manufacturers have access to the SoC drivers
									- Runs PureOS by default, can run most GNU+Linux distributions
									- Works with 2G/3G/4G, GSM, UMTS, and LTE networks
									- _See_ [Librem 5 doesn't use a SoC, it uses 6 chips](https://workflowy.com/#/beb2435c3383)
								- Cons
									- Hardware lacks security features
									  source:: https://www.reddit.com/r/CopperheadOS/comments/99i14e/overview_of_my_continuing_privacy_and_security/e4rzd2v/
									  collapsed:: true
										- I'm not interested in hardware without the basics like verified boot, attestation, hardware-bound encryption, hardware-backed key storage, etc. The expectation is now that there's a dedicated security chip isolated from the SoC implementing features like exponential throttling for authentication / key derivation, key storage, etc.
										- It would be nice to have a phone meeting industry standard security standards, better IOMMU setup
										- some improvements like a truly working audio recording kill switch but I've seen no sign of that. Other kill switches are just marketing gimmicks protecting against unclear / non-existent threat models. A microphone kill switch not disabling other ways of recording audio also wouldn't accomplish much, since gyroscopes, accelerometers, etc. can sample at very high rates and record a large range of audio. It's far more than enough to record and identify speech when the OS rate limits (100-200Hz) are bypassed (5kHz+), particularly since it's being done successfully even with the OS rate limits in place.
									- Expensive for poor hardware specs (because most funding is going towards hardware development). Wait for the next versions for better value
									- Does not run Android by default, but may later do so via Anbox
									- [Android likely has a superior security model than Linux](https://workflowy.com/#/9ae7901ed1f4)
								- Unclear
									- Uses a new UI called Phosh
									  collapsed:: true
										- Previous mobile environments have limitations,
										  [https://amosbbatto.wordpress.com/2020/08/05/advantages-of-phosh/](https://amosbbatto.wordpress.com/2020/08/05/advantages-of-phosh/)
											- Ubuntu Touch has far less development work on it compared to Canonical, though they're financially motivated by profit-sharing from PinePhone sales
											- KDE Plasma Mobile was a prototype at the time of Librem 5 crowdfunding, and PureOS their desktop OS for their laptops was GNOME-based like Phosh is
												- One of the goals of the Librem is to offer lifetime software updates, which is a promise that no other phone currently on the market can hope to match. The reason why this promise is credible is because once Purism finishes developing Phosh and its associated parts, there should be less software maintenance afterwards on Purism’s part, than if it had used one of the existing Linux DE’s. Unlike Ubuntu Touch, LuneOS and Firefox OS whose components and applications often don’t have active maintainers, all the software that Purism has modified to incorporate into PureOS/Phosh has active maintainers who will continue providing updates in the future. The maintainers of programs such as the Linux kernel, wlroots, GTK, libpurple, Fractal, Epiphany, gEdit, Animatch, Kings Cross, Geary, Lollypop, and all the rest of GNOME (Contacts, Control Center, Passwordsafe, Clocks, Software, Calculator, Podcast, ModemManager, Usage, Chess, etc.) are invested in the future development of their code, so Purism will have much less of a burden to bear in the long term.
												- Because Purism upstreams its code changes to the original software projects, future versions of these programs should require no or very little modification to be re-incorporated into Phosh. Purism has managed to get libhandy incorporated into GNOME, as well as Calls and Chats (aka, Chatty), so it is likely to get help from the community in maintaining their code. The few programs such as phosh, phoc, squeekboard, haegtasse, wys and feedbackd that Purism will have to maintain alone will not be nearly as difficult as shouldering the maintenance burden of one of the other mobile DE’s, and some of these Purism bits are likely to get incorporated into GNOME in the future, as more devices will be needing an adaptive mobile interface, cellular telephony, and haptic feedback.
												- By developing on top of GTK and GNOME, Purism should have less long-term software maintenance to do than if it had used Plasma Mobile, because Phosh will be based on the standard GNOME stack (after Purism’s changes are accepted upstream), whereas Plasma Mobile uses Halium. The only commercial company helping to shoulder the burden of maintaining Halium is Jolla, a Finnish company with 50 employees that develops Sailfish OS. In contrast, IBM/Red Hat, SUSE, Canonical, Google and System76 all contribute to the development of GTK and GNOME, but those same companies contribute much less to KDE Plasma, and they have no interest in helping to develop KDE Plasma Mobile, since they are focused on desktop Linux.
												- If Purism had chosen Ubuntu Touch or KDE Plasma Mobile, it would have gotten its phone to market faster, but it wouldn’t be able to promise “lifetime updates” for its phone, because the long-term maintenance costs would be too high for the company. There is huge market opportunity for a phone that provides lifetime software updates, because the market is now trending toward consumers who want their phones to last longer, rather than being forced to constantly buy new phones.
							- Specs
								- It's a 4 year old SoC
								- 5mp camera sensor, 3gb of ram, 720p screen, and a really bad cpu with predicted 8 hours of stand by battery.
							- https://puri.sm/posts/tag/phones/
							- [https://puri.sm/shop/librem-5/](https://puri.sm/shop/librem-5/)
							- [https://source.puri.sm/Librem5/community-wiki/-/wikis/Frequently-Asked-Questions](https://source.puri.sm/Librem5/community-wiki/-/wikis/Frequently-Asked-Questions)
							- News
								- https://puri.sm/posts/category/hardware/
								- https://puri.sm/posts/tag/phones/
							- we are pretty confident that we will be using one of NXP’s new i.MX 8 family of CPUs/SOCs for the Librem 5 phone (ARM)
							- Standard OS's
								- PureOS
								- GNOME fork called Phosh
									- Purism intends to port GNOME shell to mobile. So far the fork is called Phosh, but they mean to push it upstream. There is also work on a GTK widget/lib to allow GTK apps using it to be responsive (or adaptive). This widget would simply be used as a replacement of an existing one, so the migration would be easy.
								- Plasma Mobile (KDE)
								  https://plasma-mobile.org/
							- Running Android (or Replicant, LineageOS etc)
							  collapsed:: true
								- Could possibly run it via Anbox natively on their PureOS
									- https://anbox.io/
									- Same approach as Google's Chrome OS for Android
								- Or just install Android?
								- Android apps are a later stretch goal
								  https://forums.puri.sm/t/is-it-possible-to-use-android-apps-on-the-librem-5/3169
						- ((649b13cb-e023-4f42-a55c-a6539fd2c2a4))
						- Neo900
						  collapsed:: true
							- Pros/Cons
								- Pros
									- Open-source software 100%
									- Open-source hardware 99%
									  http://neo900.org/faq#privacy
										- - (non-free) hardware baseband **isolated**
									- Modular https://youtu.be/EJHMXQ3nSt0
								- Cons
									- N900's screen doesn't support multi touch
									- Resistive rather than capacitive screen means it's less responsive to touch
									- However up to £900 possibly
									- Poor specs - 1GB RAM, 5MP front camera, VGA front camera
									  http://neo900.org/specs
							- 480 euros for 40% downpayment
								- https://my.neo900.org/index.php?id_product=1&controller=product&id_lang=1
								- Follow project here http://talk.maemo.org/showthread.php?t=91142&page=285
							- and here http://neo900.org/
								- They're taking ages between updates (as of March 2017)
								- https://neo900.org/git/ee/tree/
								- IRC https://irclog.whitequark.org/neo900/
								- https://irclog.whitequark.org/neo900/2017-03-01
								- On March 1st 2017 they have soldering issues and are thinking of swapping CPUs completely
							- N900 comparison
								- Pro's and cons compared to my Galaxy S5.
									- Pro's:
										- Hardware keyboard
										- Brilliant OS
										- Great multitasking
										- Pretty good form-factor
										- Very precise pen input
										- Very interesting device
									- Cons:
										- Screen resolution (granted, not a dealbreaker)
										- Slow GPS and no official Google Maps support
										- Poor battery life
										- Poor performance (and finnicky webbrowser due to low RAM)
										- Not many apps (no native whatsapp, though the 3rd party one worked well enough 2 years ago)
										- Poor camera
							- http://www.wired.com/2013/11/neo900/
							- N900
								- Runs gnu/linux variant
								- Baseband processor included!
								- Needs several binary blobs
								- available for less then 100€
								- Hardware slow as fuck/outdated
								- Can do mobile chat/voice/video - Yes/Yes/Yes
								- USB host for GPS/Modem/? - Only via adapter, beta statusg - due to the age of the device, most batteries are dead by now/have very low capacity
						- ~£1.2k Necunos NC_1 (March) ?
						  collapsed:: true
						  Does it even have a modem?
							- Specs
								- Display: 5.0"
								- Body: Aluminium
								- Memory: 1GB
								- Storage: 8GB
								- Camera: 5 MP 1.4"
							- Closed source firmware with memory access: NO
							- Binary blobs: NO
							- Locked bootloader: NO
						- ((644c0acc-16fa-4526-91aa-c590a321bb77))
					- _Future potentials: _
						- Open Source Hardware (OSHW)
						  Ideal but current early versions are low ROI
						- ((65a98a50-95e7-49ad-a0c8-56d6db8715ec))
						- ((649b13c9-e1a1-478e-b316-0ac482835be4))
				- _{Archive}_
				  collapsed:: true
					- Explanation
						- https://www.devever.net/~hl/nosecuresmartphone
							- Discussion
							  https://news.ycombinator.com/item?id=10905643
			- ((649b13cd-0465-4324-b96a-f882181b1a0c))
			- _Open hardware_
			  collapsed:: true
				- SoC
				- Mobile CPU
					- Manfacturers
						- Qualcomm
							- Cons
								- Max 3 years driver support
									- What's the use of a cellphone without display/sound/wifi/modem drivers? The only reason why lineageos exists is because manufacturers made the kernel sources available. It's theoretically possible to reverse-engineer your own, but there simply aren't enough people willing to put in the effort to do it. See for instance, the sad state of third party OS for ios devices, even though the bootloader has been compromised years ago.
						- Mediatek?
						- Google
						- Samsung
				- _Assorted_
					- Fairphone 2's history is a good demonstration of why using a SoC means there won't be future Android updates (but perhaps LineageOS)
					  source:: [https://amosbbatto.wordpress.com/2020/08/05/advantages-of-phosh/](https://amosbbatto.wordpress.com/2020/08/05/advantages-of-phosh/)
						- The Fairphone 2 contains a Snapdragon 801 processor, but none of the Android phones with the Snapdragon 800/801 that were released in 2013-15 got upgraded to Android 7 (Nougat) in 2016, because Qualcomm decided that it wouldn’t release updated graphics drivers for the Snapdragon 800/801, because it was too old. Others say that the reason the Snapdragon 800/801 couldn’t be officially upgraded to Nougat is because it lacked hardware AES encryption and full disk encryption, where were features was mandated by Nougat’s Android Compatibility Definition Document (CDD) and it couldn’t pass the encryption speed requirements of the Android Compatibility Test Suite (CTS).
						- Because LineageOS doesn’t have to obey Android’s onerous [CDD](https://source.android.com/compatibility/cdd) rules and pass its <a href="https://source.android.com/compatibility/cts/">CTS</a>, LineageOS provided Snapdragon 800/801 phones with upgrades to AOSP 7-10, and a lot of Fairphone 2 users switched to LineageOS. However, Fairphone couldn’t officially tell its users to switch to LineageOS, because they wouldn’t be able to legally use Google Web Services and the Google Play Store. Fairphone then spent €500,000 to switch from Qualcomm’s unsupported Snapdragon 801 drivers to community-developed drivers. In November 2018, the Fairphone 2 became the only Snapdragon 800/801 phone to officially receive a Nougat upgrade, but it arrived 27 months after its release. Today, the Fairphone 2 is using a version of Android which is 3 years out-of-date. It is unlikely to ever receive another official upgrade due to the high cost of complying with Android’s CDD and CTS, despite the fact that LineageOS 17.1 (AOSP 10) runs fine on the Fairphone 2.
						- Unfortunately, Android’s CCD and CTS make it expensive and time-consuming to keep providing upgrades, and chipmakers like Qualcomm stop providing firmware and driver updates, so it is difficult to support a Android phone for more than the standard 2-3 years.
						- ..
						- Most Android phones use an integrated mobile system-on-a-chip (SoC) which provides the CPU, GPU, VPU, DSP, ISP, NPU, WiFi, Bluetooth, cellular baseband, GNSS, USB controller and charge controller. An SoC, such as the Qualcomm Snapdragon, Mediatek Helios, Samsung Exynos, Hisilicon Kirin, UNISOC or Xiaomi Surge, is typically only manufactured for 1 to 2 years and only provides firmware and driver updates for 2 to 3.5 years.
					- Librem 5 doesn't use a SoC, it uses 6 chips
						- In contrast, the Librem 5 uses 6 separate chips ([i.MX 8M Quad](https://www.nxp.com/docs/en/data-sheet/IMX8MDQLQCEC.pdf), <a href="https://www.redpinesignals.com/Products/Hosted_Connectivity/Multi-Protocol_Wireless_SoCs_&_Modules/RS9116_SoCs_&_Modules/RS9116N-DB00-CC0.php">RS9116</a>, <a href="http://www.broadmobi.com/en/module_show.php?id=18">BM818</a> or <a href="https://www.thalesgroup.com/en/markets/digital-identity-and-security/iot/iot-connectivity/products/iot-products/pls8-e-high-speed">PLS8</a>, <a href="https://www.st.com/resource/en/datasheet/teseo-liv3f.pdf">Teseo-LIV3F</a>, <a href="https://www.cirrus.com/products/wm8962-62b/">WM8962</a> and <a href="https://www.ti.com/lit/ds/symlink/bq25895.pdf">bq25895</a>) to provide the same functionality as the mobile SoC used in the typical Android phone. (Actually the Librem 5 has less functionality since it doesn’t have an DSP, ISP or NPU, which are found in most mobile SoC’s, although those features will be added in the future Fir batch.) The chips used by the Librem 5 will be produced for many years, so the manufacturers will provide many years of driver and firmware updates. For example, NXP <a href="https://www.nxp.com/products/product-information/product-longevity:PRDCT_LONGEVITY_HM">promises to produce</a> the <a href="http://i.MX">i.MX</a> 8M Quad till January 2028, which means at least a decade of guaranteed firmware and driver updates for the chip. Both NXP and Redpine Signals are contributing to the drivers used in mainline Linux, so their driver updates will benefit the Librem 5. Because the Librem 5 only uses free/open source drivers, the community can maintain the drivers long after the manufacturer stops supporting them, just like the Linux kernel still supports the 80486 processor introduced in 1989. In addition, Purism <a href="https://forums.puri.sm/t/does-respects-your-freedom-certification-allow-updating-of-proprietary-firmware/9484/12">intends to offer proprietary firmware updates</a>, so the Librem 5 will take advantage of the long support cycles from its chip manufacturers.
					- Android's initiatives like Treble and Mainline to increase phone longevity
					  _See_ [Initiatives to ensure longevity and regular security updates despite obstacles from OEMs](https://workflowy.com/#/85ee55ef847b)
					- Apple provide updates for years but make it extremely difficult to repair their devices
						- Apple is the best phone maker in terms of provide long-term software support. It offers [between 4 and 5 years](https://www.androidpolice.com/2017/11/02/android-versus-ios-software-updates-revisited-two-years-later/) of software updates, which seems generous until considering that Apple typically sells its phone models for 3 years, with a $100 discount in the second year and a $200 discount in the third year. People buying an iPhone in its third year of production are still paying as much as an upper mid-range Android phone, but getting fewer years of software support. While the iPhone may be better than the typical Android phone in terms of providing software updates, Apple has been the mobile industry’s leader in terms of promoting planned obsolescence. The original iPhone in 2007 was the first phone to use a sealed case and a non-removable battery (except for the $5000 Vertu Constellation in 2006 that hardly anyone bought). Apple has introduced all sorts of malicious practices that limit the lifespan of their phones, including using <a href="https://en.wikipedia.org/wiki/Pentalobe_security_screw">custom pentalobe screws</a> to prevent users from fixing their phones, <a href="https://slate.com/technology/2016/02/iphone-home-buttons-replaced-by-third-parties-can-trigger-error-53-bricking.html">software updates</a> that refuse to work with 3rd party repairs, <a href="https://boingboing.net/2018/10/20/louis-rossman.html">seizing imported parts</a> as so-called “counterfeits”, “unauthorized” batteries <a href="https://www.theverge.com/2019/8/14/20805744/apple-iphone-battery-replacements-ios-safety-statement-unauthorized">showing ominous warnings</a>, <a href="https://www.extremetech.com/electronics/248113-apple-wants-build-products-100-recycled-materials-refuses-allow-iphone-mac-recycling">prohibiting recyclers</a> from refurbishing iPhones and reusing their parts, and <a href="https://newspunch.com/apple-slowing-down-old-iphones/">slowing down the processor</a> of older iPhones. These Apple policies make it hard to recommend iPhones to people who want to own their phones for a long time.
				- _Related:_
					- _See_ [Phones with baseband isolation](https://workflowy.com/#/6463a55cc5bd)
			- Open-source firmware
			  collapsed:: true
				- See [$150 PinePhone by Pine64](https://workflowy.com/#/99b48b062019)
			- Foldable
			  id:: 649b13c9-2c58-49ad-a151-a73c49bdbc1d
			  collapsed:: true
				- Pros/Cons
					- Pros
						- Better productivity by being able to multi-task with two or more apps at once, or a virtual keyboard with bigger app real estate
				- _Products_
					- [Huawei Mate XT Ultimate](https://www.gsmarena.com/huawei_mate_xt_ultimate-13320.php) (2024) 
					  id:: 67c050b3-0a59-4c53-81f8-afd40dbcb3b6
					  collapsed:: true
					  trifold phone, landscape is much better for watching media
						- [The Tri Folding Phone Impressions! - YouTube](https://www.youtube.com/watch?v=Yv_S7KrOlfk) review
					- ((66bd0cf2-1be8-4375-af83-08eb49d85a56))
					- [Samsung Galaxy Z Fold5](https://www.gsmarena.com/samsung_galaxy_z_fold5-12418.php) (2023)
					- [Pixel Fold](https://www.gsmarena.com/google_pixel_fold-12265.php) (2023)
					  id:: 666af42d-d4e6-4ae2-a84f-a89ab7cd9f6f
					  collapsed:: true
						- Pros/Cons
							- ## Pros
							- Cons
								- [[2024-06-13 Thursday]] [Still doesn't have](https://www.reddit.com/r/GooglePixel/comments/170xkwv/pixel_fold_android_14_altdp/) ((63219e34-cda2-4a69-a2c8-b74b33cf9a91))
								  id:: 46b49913-f7d7-457c-9f3e-7a97820df736
							- Unclear
							- Comparisons
								- ((666af48d-cf2d-43a7-8f79-006afa76cf83))
									- {{embed ((666af48d-cf2d-43a7-8f79-006afa76cf83))}}
						- [Error 403 (Forbidden)!!1](https://store.google.com/gb/product/pixel_fold)
						- Comparisons
					- [Xiaomi Mix Fold 3](https://www.gsmarena.com/xiaomi_mix_fold_3-12468.php) (2023)
					- [Microsoft Surface Duo 2](https://www.gsmarena.com/microsoft_surface_duo_2-11117.php) (2021)
				- ((631fa93c-fd77-4435-a292-fd9573d0242f))
			- _Misc models_
			- Future
				- Satellite capabilities
				  collapsed:: true
					- Pros
						- Cheaper and better local mobile network providers, since they have to compete with global satellite network providers now also
						- Circumvents local ISP and nationwide government firewalls, tracking and blocking the internet
						- Decreases the dependence on urban centers, whereas the U.N. is pushing countries to concentrate their citizens into easily managed smart city megalopolises
							- ((649b12dd-30e2-4787-9f27-9bc6aaa59583))
				- Hardware killswitch for microphone
				  collapsed:: true
					- [France passes bill to allow police remotely activate phone camera, microphone | Hacker News](https://news.ycombinator.com/item?id=36616037)
					-
			- ## Attributes I don't care about
			  collapsed:: true
				- ((65aaeb34-ba89-4dae-86ba-1cbb903f8d37)) support
				- Headphone jack (though could use a USB-C adapter)
				- Dual boot
				  collapsed:: true
					- 1230€ Bittium Tough Mobile
					  collapsed:: true
						- https://www.bittium.com/bittiumtoughmobile
						- Article
							- A year ago, Finnish company Bittium -- formerly Elektrobit Wireless Communications -- unveiled its ruggedized, Android-based Bittium Tough Mobile LTE smartphone as part of its Bittium Specialized Device Platform. At this week’s Mobile World Congress in Barcelona, Bittium followed up with a new software build for the phone based on Android 6.0 that offers a secure, containerized dual-boot scheme to separate user space into Confidential and Public sectors.
							- The Public mode enables typical usage, including social networking access, while the Confidential mode is “completely isolated and hardened for secure authority and information security use,” says Bittium. As a result, Jason Bourne, Carrie Mathison, and other government, enterprise, and public safety workers dealing with sensitive information, can avoid buying and carrying two separate devices.
							- Bittium also upgraded the phone’s Bittium Secure Suite, which enables features such as remote management and encrypted connections. The software includes secure boot, runtime integrity, and an application permission firewall. You can encrypt emails with PGP, and call upon FIPS 140-2 compliant hardware crypto. Other features include secure user credential storage, mass memory encryption and tampering detection.
							- The latest Bittium Secure Suite version adds a feature called Bittium SafeMove Analytics, which strengthens Bittium Tough Mobile’s hand in the first responder and public safety market. Bittium, Sonim, and Motorola all compete in this area, focusing primarily on users of the emerging, U.S.-based FirstNet public safety network.
							- Bittium SafeMove Analytics adds visual and real-time tracking, as well as sensor-based data collection. Administrators can track users’ movements on a map and create geo-fencing alarms, for example, warning a first responder if they’re moving into a hazardous area. The feature also helps analyze mobile networks and organize a mobile IoT network with on-the-fly analysis of sensor data.
							- Also at MWC, Bittium demonstrated two medical products. There’s a Bittium Wearable Platform for Health Monitoring that measures stress, fatigue, and sleeping quality, as well as Faros ECG Event and Faros ECG Mobile software for remote heart monitoring.
							- The Bittium Tough Mobile hardware appears to be unchanged. It runs Android 6.0, up from Android 5.1, on Qualcomm’s quad-core, 2.3GHz Snapdragon 801. The phone is equipped with 2GB LPDDR3, 16GB eMMC, and a microSD slot. The glove-usable 5-inch HD touchscreen is joined by 8- and 2-megapixel cameras.
							- The 180-gram, 13.5mm thick phone has dual SIM slots, and supports 4G LTE and other cellular standards, including LTE band 14 for public safety. There’s also WiFi-ac, Bluetooth 4.0, NFC, a push-to-talk (PTT) button, and aGPS/Glonass, iZAT positioning.
							- The Bittium Tough Mobile supplies a full slate of non-healthcare sensors, as well as a USB 3.0 port, speakers, a noise-cancelling mic, a 3.5mm audio jack, and a 2420mAh Li-Ion battery. The cast magnesium unibody design features MIL-STD-810G shock resistance, IP67 water and dust protection, and -20 to 55ºC operation.
					- xdadeveloper solutions
						- https://github.com/chenxiaolong/DualBootPatcher
					- http://ironsides.tech/products/
					- Planet Computing clamshell phones
					- Probably the open hardware phones too
				- Physical QWERTY keyboard
				  collapsed:: true
					- Pros/Cons
						- Pros
							- No software keyboard on screen means apps can show more and this aids productivity
							- Hardware keyboards are more accurate compared to a same-size software keyboard (eg foldable phone LG G8x)
						- Cons
							- Swipe typing is very good nowadays
							- Very few phones that have this which make them expensive (often for poor specs too)
							- Foldables are arguably better for productivity since they can have a virtual keyboard on one screen OR you can display two apps simultaneously
					- £650 F(x)Tec Pro1 - amazing demo on Sailfish OS with Debian
					  collapsed:: true
						- Pros/Cons
							- SFOS incompatible with Android apps on this phone
								- On officially supported device, yes, because it includes proprietary components including the Android compatibility layer. Android apps just run alongside SFOS ones, you can multitask. It works decently on recent devices and performance is ok, except they don't communicate with the camera or Bluetooth if I remember correctly. On SFOS community ports, such proprietary software is not included and you cannot buy the specific bits from Jolla, plus they probably would not work on a ported device unless it uses the same SoC as an official device for which a Sailfish license already exists. This is the case for the Pro¹, actually. If you have an official device with the same SoC, then theoretically it is not unfeasible to transfer the Android compatibility layer, but I am afraid this would be grey area or even illegal, and I cannot even confirm. Probably not a topic to discuss outside of the Pro¹ community chat servers.
						- Demo
							- [https://store.fxtec.com/product/fxtec-pro1/](https://store.fxtec.com/product/fxtec-pro1/)
							- UserLAnd for Android allows the same thing?
							- This phone can't run Android apps in SFOS
					- £500 Gemini PDA by Planet Computing
					  collapsed:: true
					  Clamshell with physical keyboard
						- https://store.planetcom.co.uk/products/gemini-pda-1
						- 6" touchscreen
						- 4200mAh battery
						- 2x USB-C
						- MicroSD slot
						- Headphone jack
						- Physical SIM and eSIM
					- £430 preorder Cosmo Communicator by Planet Computing (successor)
					  collapsed:: true
					  Clamshell with physical keyboard
						- https://www.indiegogo.com/projects/cosmo-communicator#/
						- New
							- Also has an external colour 2" touchscreen display for easy phone call control and notifications
							  https://c1.iggcdn.com/indiegogo-media-prod-cld/image/upload/c_limit,w_695/v1541357827/ipu0sr68dlkhhcyis5ax.jpg
							- Backlit keyboard
							- 24MP camera (previously 5MP)
							- 6GB RAM (from 4GB
							- NFC
					- Related: UMPC
				- IR blaster
				  collapsed:: true
					- LG G5
					- LG V20
				- Modular
				  id:: 649b13c9-e1a1-478e-b316-0ac482835be4
				  collapsed:: true
					- Pros/Cons
						- Pros
							- Easy replacement of parts. Lasts longer?
						- Cons
							- Big tradeoff with performance, waterproofing etc
							- Battery life is always going to be limited etc
							  https://reddit.com/comments/9f2lsb
					- _Open hardware_
						- PuzzlePhone
						  collapsed:: true
						  Half funded via IndieGoGo. Shipping early 2017
							- Modular (3: battery, electronics and screen)
							  http://i.imgur.com/FfbkiN2.png
							- Updates
							  https://www.indiegogo.com/projects/puzzlephone-upgradeable-sustainable-incredible-android-smartphone#/updates
							- Specs
								- Main
									- Display: 5” Full HD 1920 x 1080
									- Front camera: 5 megapixels
									- Rear camera: 12 megapixels + LED Flash
									- Battery: 2.800 mAh
									- Processor: ARM 64 bits, 8 cores
									- RAM memory: 3 GB
									- Storage Memory: 16/32/64 GB (depending on model)
									- microSD support: Yes, the Brain module supports a microSD card.
								- Connectivity:
									- 2G/3G/4G/LTE Cat4/6* (*depending on markets)
									- USB 3.0/2.0 Type-C
									- NFC + Bluetooth LE 4.2
									- WiFI 802.11 a/b/g/n/ac
									- GPS
								- Sensors:
									- Accelerometer
									- Gyroscope
									- Proximity
									- Ambient light
								- Size: 69 mm X 137 mm X 8.9 mm
								- Weight: 170 g
								- What’s in the box?
									- 1 Spine + 1 Brain + 1 Heart = 1 Fully Operational PuzzlePhone
									- AC/DC USB Type C charger + USB cable
									- Headphones with integrated microphone
							- The PuzzlePhone Compatible Open Standard
								- http://www.puzzlephone.com/blog-read/puzzlephone-ceo-on-the-puzzlephone-compatible-open-standard/
								- $31 PuzzlePhone Piece Maker
									- (29€) All you need to develop a custom Heart module and Make own custom solution there. Includes: 1. Access to the PuzzlePhone Makers Community for updates on these materials during the R&D process
									- 2. 3D CAD of casework in STL format for 3D printing prior to end of campaign
									- 3. Puzzlephone Design Guide: How to make your own modules
									- 4. Module connector cables in various lengths, plus break out connector board
									- 5. Unlocked boot-loader
						- EOMA68 phone
					- _Proprietary_
						- ((649b13cb-4bf6-46f3-9f65-5419728ccc6b))
						- BLOCKS (smartwatch)
						  collapsed:: true
							- https://www.chooseblocks.com
							- Many modules, at a late stage will have a SIM card module
							  https://i.imgur.com/yfd3xQj.png
						- Moto Z
						  collapsed:: true
							- Moto Z Force is the slightly thicker but better specs version
							- Mods are basically cases you can attach to the back
								- Speakers
								- Mini projector
								- Battery life
								- etc
							- http://www.theverge.com/2016/6/9/11889076/lenovo-moto-z-mod-smartphone-specs-announcement
					- _[Learning Resources]_
						- Modular smartphone projects
							- https://en.m.wikipedia.org/wiki/Modular_smartphone
							- https://en.m.wikipedia.org/wiki/List_of_open-source_hardware_projects
						- Open-hardware phones
						  http://www.openphoenux.org
				- Wireless charging
				  collapsed:: true
					- Pros
						- Cool?
					- Cons
						- Picking up phone to use which stop it charging
						- Fast charging available only via USB-C currently
						- Will likely conflict with removable battery requirement
				- OLED, 4K etc
				- 5G wireless radio connection
				  collapsed:: true
					- Could be dangerous
					  collapsed:: true
						- ![A 5G phone can do this to a bottle of champagne - imagine what it is doing to your blood...😳 [cvdya6nE53wy].mp4](../assets/A_5G_phone_can_do_this_to_a_bottle_of_champagne_-_imagine_what_it_is_doing_to_your_blood...😳_[cvdya6nE53wy]_1711041655720_0.mp4)
			- {Archive}
			- Related: ((65a98a50-a2bd-44d0-849a-24c12fce1c0a))
		- # Comparison sites
			- [GSMArena.com - mobile phone reviews, news, specifications and more...](http://www.gsmarena.com)
			- [Smartphones with removable battery](http://www.productchart.com/smartphones/sets/3)
			- [Compare phones, smartphones, tablets - GSMArena.com](http://www.gsmarena.com/compare.php3)
		- Mobile phones index
		  For multiple or unsorted attributes
		- [Learning Resources]
			- [Best smartphones of 2025 - buyer’s guide - GSMArena.com tests](https://www.gsmarena.com/smartphone_buyers_guide-review-2036.php)
	- Purchase route
	  collapsed:: true
		- Buy used - craigslist/ebay
		-
	- Additional expenses
	  collapsed:: true
		- Physical expenses
			- For buying second-hand, Gumtree or eBay
			  collapsed:: true
				- ~£220 https://www.gumtree.com/search?q=samsung+galaxy+s5&search_category=all&search_location=North+West+London&tl=&distance=0.0001
				- £210 15gb black http://www.ebay.co.uk/itm/Samsung-Galaxy-S5-G900-4G-LTE-16GB-Black-Factory-Unlocked-GRADE-A-/171902695645?hash=item280632f8dd
				- £168 refurb good condition http://www.ebay.co.uk/itm/400787792861
			- Tempered glass/privacy screen protector
			  collapsed:: true
				- See eBay
				- £3.70 tempered glass screen protector
					- http://www.ebay.co.uk/sch/i.html?_from=R40&_trksid=p2050601.m570.l1311.R3.TR4.TRC0.A0.H1.Xsamsung+galaxy+s5+glass.TRS0&_nkw=samsung+galaxy+s5+glass+protector&_sacat=0
				- £7 privacy screen protector
				- As of Aug 2016 - no combined tempered glass/privacy screen protectors on Amazon
					- eBay: this one didn't turn out to be a privacy screen protector
					  http://i.imgur.com/Wf0iJvv.png
					- Amazon: good privacy screen protector ONLY
					  Tech Armor Privacy Screen Protector for Samsung Galaxy S5
			- £17 for 64GB microSD card
			  collapsed:: true
				- http://www.ebay.co.uk/sch/i.html?_from=R40&_trksid=p2050601.m570.l1311.R1.TR12.TRC2.A0.H0.X64gb+micro.TRS0&_nkw=64gb+micro+sd+card&_sacat=0
			- £7 extra battery
			- £3 reusable camera cover
			  collapsed:: true
				- Black static cling vinyl stickers
				  https://www.amazon.co.uk/d/Stationery-Office-Supplies/FloWriter-60-x-Small-Black-Chalkboard-Labels/B00YL68TIO/ref=pd_vtph_201_tr_t_2?_encoding=UTF8&psc=1&refRID=9GS30TCGDS7MME171P7A
		- Non-physical
			- http://www.moneysavingexpert.com/phones/unlock-mobile-phone
			- http://www.moneysavingexpert.com/insurance/cheap-mobile-phone-insurance
				- Not necessary because I never leave my phone behind
				- - I have Barclays insurance still (remember to register new phone)
- Phone Plans
  id:: 6436ae2f-4aac-4d12-9ee3-add1862e15a4
  collapsed:: true
  AKA cell plan / phone number
	- Pros/Cons
		- Pros
			-
		- Cons
			- [The Hated One never has a SIM card in his phone, he keeps a dumb phone which is off unless he's expecting a call and sometimes in a faraday bag. Otherwise just relies on Wi-Fi](https://youtu.be/4Dei2buz1X0)
		- Unclear
			- It's unclear whether your phone pings cellular towers whilst no SIM is inside. Maybe on Airplane Mode and on ((63209286-6f40-4063-9fdc-2543251d416e))
		- Comparisons
	- _To do_
		- Get a new cheap pay monthly contract to keep on mobile router/spare phone, for whenever I need to tether because home internet isn't working
		  id:: 6422a753-ac56-4e5a-a422-b71c21a25708
		  collapsed:: true
			- Why not
				- [iD Mobile for example will cancel your phone number if you don't use data/top-up every 90 days](https://community.idmobile.co.uk/cancelling-an-id-mobile-plan-109/what-happens-if-i-don-t-use-my-pay-as-you-go-phone-for-a-while-45155)
			- [£6 monthly is the cheapest with iD Mobile](https://www.idmobile.co.uk/sim-only-deals)
		- Buy a new O2 SIM in-person for anonymity, only top-up in-person
		- In future: use [eSIM providers](<((649b13c9-210d-4b84-9e8c-4cba6e390193))>) as the second dual-SIM, on a provider which offers 30 day contracts, or ideally pay-as-you-go (none atm)
	- # Types
		- _Sorted by pay type_
			- Prepaid phone plan
			  source:: [https://www.youtube.com/watch?v=By3VOtPuWIY](https://www.youtube.com/watch?v=By3VOtPuWIY) Techlore
			  collapsed:: true
				- Pros/Cons
				  collapsed:: true
					- Pros
						- Often cheaper than pay monthly plans
						- Often requires no identification info
					- Cons
						- MVNO's have deprioritised traffic compared to the originator network
						  id:: 644c0aca-bcac-4e87-9082-167b96aa9e98
				- Mint Mobile (MVNO for T-Mobile network)
				  collapsed:: true
				  [https://mintmobile.com](https://mintmobile.com)
					- Steps
						- Route A
							- 1.  Buy a SIM kit with a prepaid card or [privacy.com](http://privacy.com)
							- 2.  Send to a maildrop or your home using a pseudo email
						- Route B
							- 1.  Buy starter kit via Amazon (Amazon account made with pseudo email)
							- 2.  Use Amazon gift card purchased with cash
							- 3.  Ship to an Amazon locker
				- Ting
				  [https://ting.com](https://ting.com)
				- Local convenience store - often have prepaid cell plans
				  collapsed:: true
					- Steps
						- 1. Ensure the company you buy the plan from doesn't verify identity
						- 2. Buy with cash
				- Others
				  collapsed:: true
					- Boost Mobile
					- Cricket Wireless
					- Republic Wireless
			- Pay-as-you-go
			  collapsed:: true
				- Pros/Cons
				  collapsed:: true
					- Pros
						- Great privacy in the UK since you can purchase it all with cash
				- Pay-as-you-go bundles
				  id:: 649b13c9-5cef-47d4-9eb0-845735fb93c8
				  [Best pay as you go Sim deals: Compare the best offers - MSE](https://www.moneysavingexpert.com/mobiles/best-pay-as-you-go-sim-cards/)
					- Pros/Cons
						- (usually expires after a month, better deal than traditional pay-as-you-go
					- UK providers
						- O2
						  [https://www.o2.co.uk/help/pay-as-you-go/big-bundles](https://www.o2.co.uk/help/pay-as-you-go/big-bundles)
						- EE
							- Automatically charges you for a pack
							- Want a different pack?
								- You can change your pack before you start using it. To find the one that’s best for you, go to My EE, or text ALL PACKS to 150.
			- Pay monthly
			  collapsed:: true
			  AKA post-paid / subscription
				- ((654cbb47-7dca-4be3-9b27-e59d32b68f16))- £10/month, 30GB data, unlimited texts+mins. 12 month contract, expires December 2021
					- Roaming - uses up normal allowance in most of EU
						- If you're roaming in one of our 50 Inclusive Roaming destinations, the minutes, texts and data you use simply come out of your remaining monthly allowances.
						- 50 countries
							- Band 1 - _Austria, Azores, Belgium, Bulgaria, Canary Islands, Croatia, Cyprus, Czech Republic, Denmark, Estonia, Finland, France, French Guiana, Germany, Gibraltar, Greece, Guadeloupe, Guernsey, Hungary, Iceland, Ireland, Isle of Man, Italy, Jersey, Latvia, Liechtenstein, Lithuania, Luxembourg, Madeira, Malta, Martinique, Monaco, Netherlands, Norway, Poland, Portugal, Réunion, Romania, Saint Barthélemy, Saint-Martin, San Marino, Slovakia, Slovenia, Spain, Sweden, Vatican City._
							- Band 2 - _Azerbaijan, Macedonia, Belarus, Kazakhstan._
					- Speed
					  id:: 644c0aca-5f97-48f6-9fdb-08563d95ca17
						- LibreSpeed app - Nottingham, England (LayerIP)
							- 00:30 Sunday, Blackfriars Road
								- 60 Mbps download, 31 upload
							- 18:40 Monday, home
								- 1.3Mbps download
								- Meanwhile WiFi - 47 Mbps download, 4.5 Upload
						- Speedtest.net
							- Three vs iD Mobile - 11/01/2022 Tuesday, 13:00
		- _Sorted by X_
			- Pretty Good Phone Privacy (PGPP) phone plans
			  id:: 62f557ed-0f88-48e8-96ef-bef83f95ad53
			  collapsed:: true
				- [Buy plans from here](https://invisv.com/pgpp/) - ($40/mo)
					- Includes two parts:
						- ((62f55393-cfe7-4bd5-8986-88ab1ab875ec))
						- [INVISV Relay](https://invisv.com/relay/)
						  id:: 644c0aca-273b-4966-a270-69b343e3b9cb
						  AKA PGPP Relay service
							- Pros/Cons
								- ## Pros
								- Cons
									- 2025 June - [shutdown](https://invisv.com/articles/service_shutdown.html)
									- [[2024-03-28 Thursday]] [INVISV Relay is not open-source yet they have plans to](https://play.google.com/store/apps/details?id=com.invisv.relay)
								- Unclear
								- Comparisons
							- INVISV as entry node and Fastly as exit node
							- Related: ((66055a04-a526-4818-8d13-b0c7ce0a2c5d))
					- Plans
					- [App](https://play.google.com/store/apps/details?id=com.invisv.pgpp)
				- Discussions
					- https://github.com/privacyguides/privacyguides.org/discussions/1615
					- https://news.ycombinator.com/item?id=32429419
					- https://discuss.grapheneos.org/d/460-pretty-good-phone-privacy-pgpp-for-anonymising-imsi
					- https://www.reddit.com/r/PrivacyGuides/comments/wmfx8v/pgpp_pretty_good_phone_privacy_esim_network_that/?
			- Disposable/anonymous numbers
			  id:: 649b13c9-f664-4faf-ac1e-894243f5d6cd
			  collapsed:: true
				- # Sorted by usecase
					- ((663b24fb-f1f2-4dbe-ae47-d3a910654835)) and dating
						- ((6652f853-2369-4a8d-94ab-f1af9b9a7bae)) but can't receive calls
						- ### Calls and ((663b24fb-f1f2-4dbe-ae47-d3a910654835))
							- Need to be a ((6652f867-b1d6-47e0-8382-b6761c5b96c1))
				- Sorted by ((65f9db9a-f844-44f2-b70d-cac8db463edb))/non
				  id:: 660561f1-cd48-43be-bb3e-eaaa3850b295
					- ((65f9db9a-f844-44f2-b70d-cac8db463edb)) : ((663b24fb-55d6-4ced-96e5-481e4cfc01d1))
					- Non- ((65f9db9a-f844-44f2-b70d-cac8db463edb)) providers
					  id:: 6652f867-b1d6-47e0-8382-b6761c5b96c1
						- [SMSPool](https://www.smspool.net/)
						  id:: 6652f853-2369-4a8d-94ab-f1af9b9a7bae
						  collapsed:: true
						  SMS, no calls
							- [SMSPool - non-voIP US phone numbers starting at $0.25 - 9 countries and more supported - Buy directly from suppliers | BlackHatWorld](https://www.blackhatworld.com/seo/smspool-non-voip-us-phone-numbers-starting-at-0-25-9-countries-and-more-supported-buy-directly-from-suppliers.1433523/)
							- $10/month for a US number, SMS only
								- I emailed support and confirmed you can keep renewing a number
							- [SMSPool - Online SMS Service](https://play.google.com/store/apps/details?id=com.smspool.app)
							-
						- [sms verification | BlackHatWorld](https://www.blackhatworld.com/tags/sms-verification/)
						- ### _Can pay with crypto_
							- [Silent Link](https://silent.link/)
							  However [[2024-11-13 Wednesday]] they only offer data plans with no phone call/SMS, and it's SIM/eSIM and not app-based
							- [Crypton.sh](https://crypton.sh/)
							  id:: 649b13c9-8a5f-428a-8892-cf12c66d6bfa
							  collapsed:: true
							  Accessible via web app only? SMS inbound/outbound only
								- Pros/Cons
									- Pros
										- Don't even need an email address to sign up
										-
									- Cons
										- [[2024-11-13 Wednesday]] SMS + voice inbound no longer available, only data
									- Unclear
										- €8.00 Modem Rental + €6.00 phone number cost
											- They use custom modems to run all these SIMs
										- Only UK phone numbers available currently - from operator Telefonica UK Ltd [[2024-11-13 Wednesday]]
									- Comparisons
								- Physical SIM card in the cloud, for sending + receiving SMS messages. Messages are encrypted using your chosen private key. Includes a web interface, as well as an API for interacting with it from any device. Pricing is around €7.00/month, and payment is accepted in BTC, XMR or credit card.
								- differs from JMP in a number of ways, and might be more along the lines of what you're looking for. All of your messages are encrypted with zero-access encryption on their servers meaning they couldn't access your information even if they wanted to, they have numbers from many different countries (JMP only has US/CA numbers), offer a plethora of different payment methods to suit you whatever your requirements may be, use physical SIM cards in bespoke modems that they then rent out to you , and are hosted in Iceland -- a country known for their strong privacy legislation. While I think that they're a better service in many ways, they do have two major caveats. Calls, and pricing. First, calls. Crypton doesn't offer any calling, instead only offering SMS. This means that if you're just using it to verify an account, it'll probably be fine, but also ensure that wherever you're signing up to won't call you to give you your verification code (like I believe Google and Telegram have the option of.) And second, pricing. Crypton is significantly more expensive than JMP, coming in at €6/mo plus a pay-as-you-go pricing additionally for outgoing SMS, which ranges anywhere from €0.02 to €0.024 per message.
							- [VirtualSIM](https://virtualsim.net/)
							  Accessible via web app only?
							- [Major Phones LLC - US and UK virtual phone numbers](https://www.majorphones.com/) - doesn't offer numbers for longer than 30 days
							- [Smspva](https://smspva.com/)
							- [TextVerified](https://www.textverified.com/)
							- smscodes.io
							- [/r/phoneverification/](https://www.reddit.com/r/phoneverification/)
						- ### Can't pay with crypto
							- [Google Voice](https://workspace.google.com/products/voice/)
							  collapsed:: true
							  $10/month for UK enterprise plan
								- it's also pretty easy to get a free US-based GV number by "borrowing" the cell phone number of a friend in the USA for one-time verification of the account. (You can unlink that number later, without consequences in my experience, and just use GV via VoIP.)
						- {Archive}
							- ((62f55393-cfe7-4bd5-8986-88ab1ab875ec))
					- Masked Numbers (receive only)
					  collapsed:: true
						- Blur is a service run by the privacy company Abine. It allows you to create disposable credit cards. You choose how much you want to add to a card, and a “masked card” will be automatically created. You can obtain a new card whenever needed. All charges on the credit card will show up as “ABINE, INC”.
						- The cost of this service (MaskMe Premium) is $5 a month, and it also gives you access to the other features — Masked Phone Numbers, Masked Emails and the MaskMe apps for iOS and Android.
					- Unknown
						- [SIP2SIM](https://www.aa.net.uk/voice-and-mobile/sip2sim)
						  collapsed:: true
						  a SIM or eSIM that allows a real mobile phone to connect to your own SIP/VoIP server or to our own VoIP service
							- Pros
								- As it acts as a SIM card can utilise native call recording
								- Works with SIP-based phone systems like Asterisk and different VoIP providers
								- Can easily port existing phone number
							- [£12/month without data](https://www.aa.net.uk/voice-and-mobile/sip2sim/)
								- [Announcement](https://www.aa.net.uk/voice-and-mobile/onsim-on-sip2sim/)
			- Unlimited 4G/LTE data
			  id:: 649b13c9-ca82-49ed-bea6-a49963b07810
			  collapsed:: true
				- Why
					- Superb for #MobileAccomodation and ((64c38af3-1c05-4e5a-9fad-5ca15194a89d))
				- Providers
					- If you purchase a contributing membership from the Calyx Institute, they gift you a fully unlimited 4G/LTE mobile data plan: [https://calyxinstitute.org/membership/internet/4g-lte-faq](https://calyxinstitute.org/membership/internet/4g-lte-faq) . The membership costs $500 the first year and $400 each additional year. It's a popular option in the nomad community.
					- Librem AweSIM - $99/month gets you a new phone number, unlimited talk, text, and data.
					  [[Error 404 – Purism](https://puri.sm/products/librem-awesim/](https://puri.sm/products/librem-awesim/)<a) href="[Error 404 – Purism](https://puri.sm/products/librem-awesim/">)
					  </a>
					- AT&T has an unlimited 4G for business plan that is only about $100/month. They accept 'consultant' as a business (I went into a store to simplify the process of setting up the account)
			- Visual voicemail
			  collapsed:: true
				- [https://source.android.com/devices/tech/config/voicemail](https://source.android.com/devices/tech/config/voicemail)
				- Looking up carrier feature support
				  collapsed:: true
				  [https://support.apple.com/en-gb/HT204040](https://support.apple.com/en-gb/HT204040)
					- _UK carrier support_
						- 3 (and thus iD Mobile) don't support visual voicemail
						- O2 and Sky supports visual voicemail
						- EE supports visual voicemail, and eSIM
				- App support for carrier IMAP solution
				  collapsed:: true
					- Integrated into default dialler?
					- Simple Dialer doesn't support it yet
					  [https://github.com/SimpleMobileTools/Simple-Dialer/issues/180](https://github.com/SimpleMobileTools/Simple-Dialer/issues/180)
					- Phone by Google doesn't show it, which may indicate its missing due to lack of carrier support
					- [https://github.com/micwallace/visualvoicemail](https://github.com/micwallace/visualvoicemail)
				- Cloud-based voicemail - dialers are forwarded to their voicemail service instead
				  collapsed:: true
					- Google Voice (incompatible with microG)
				- ((6436ae2f-4aac-4d12-9ee3-add1862e15a4))
				  #Phone
			- Privacy cell plans provided by business i.e. telecoms don't get your identity
			  collapsed:: true
				- Purism
					- “[SIMple Plus](https://shop.puri.sm/shop/librem-simple-plus/)”, provides subscribers with 4G high speed internet with a 3 GB monthly data limit and a $59/month price. Additionally, they can send texts globally to over 160 countries at no extra cost. The plan is designed especially for those who are interested in the SIMple plan, but would like a higher data cap.
					- In October 2020, Purism launched AweSIM with unlimited talk, text, and data for $99/month fully unlimited prepaid plan. Subscribers can enjoy video streaming, high-speed 4G/4G-LTE data, Roaming is included at no additional cost within the US, US Virgin Islands, Puerto Rico, Canada, and Mexico.
					- In March 2022, Purism introduced its most affordable plan, SIMple with 1 GB high speed data, unlimited talk and text for $39 a month. Based on popular demand, SIMple Plus offers data limit to 3 GB, for $59 a month.
			- Cheap monthly rate but can purchase data add-ons
			  collapsed:: true
				- Ideally
					- Can purchase add-ons via website - makes it easier to use with mobile router instead of having to take out SIM to put in phone
					- Not a ((644c0aca-bcac-4e87-9082-167b96aa9e98))
				- Providers
					- iD Mobile
					  id:: 654cbb47-7dca-4be3-9b27-e59d32b68f16
					  collapsed:: true
						- Current contract [[2024-01-19 Friday]]
							- £10/month, 60GB, Unlimited texts/minutes
						- Web app but MVNO
						- Monthly fee: £6/mo 8GB or £8/mo 30GB
						- Addons: £30 6GB 1 month, £10 15GB 12 months
	- # Tools
		- ((649b13ca-0417-44e6-ab64-fa0ebae72f22))
		- Countries which allow registering a SIM without a government-issued ID (2018)
		  collapsed:: true
		  just take advantage of their being no roaming charges within the most of Europe.
			- ((63061153-6db2-4dcf-bffc-cab105ab529d))
			- ((64e09424-2cc1-4686-a779-b49dfbd2178d))
			- ((64e09426-a604-49ad-a9f0-0efa6c4a1930))
			- ((64e09427-6d80-41ec-b036-c5af52148f2c))
			- ((644c0a62-3e32-4b4e-b2d8-25544539d637))
			- ((644c0a62-cad3-45b8-a175-dc1117feda1c))
			- Estonia
			- Latvia
			- Lithuania
			- ((64e09426-c1eb-4f3c-9d34-baf8b13418df))
			- Croatia
			- Bosnia
			- Serbia
			- Kosovo
			- Romania
			- Moldova
			- Ukraine
			- [2024 comment](https://discuss.grapheneos.org/d/13538-what-mobile-provider-do-you-guys-recommend-2024/16) - UK, Netherlands, Spain, Czech Republic, Lithuania, Latvia
		- [Check signal coverage over the UK](https://checker.ofcom.org.uk/)
		  id:: 644c0aca-cdce-4baf-82d0-951e50ed9ee9
		  collapsed:: true
			- _Providers_
				- EE
				- Three
					- Pay Monthly plans
					  [http://www.three.co.uk/Store/SIM/Plans_for_phones](http://www.three.co.uk/Store/SIM/Plans_for_phones)
						- £11/mo, 12GB data, 12 month contract, unlm mins/txt
					- [Speedtest.net](http://Speedtest.net) comparisons
						- ## Three vs iD Mobile - 11/01/2022 Tuesday, 13:00
				- O2
					- Pay Monthly plans
					  [https://www.o2.co.uk/shop/sim-cards/sim-only-deals#deviceType=phone&contractLength=P12M](https://www.o2.co.uk/shop/sim-cards/sim-only-deals#deviceType=phone&contractLength=P12M)
						- £15/mo, 5GB data, 12 month contract, unlm mins/txt
						- £18/mo, 20GB data, 12 month contract, unlm mins/txt
				- Vodafone
					- Pay Monthly plans
					  [https://www.vodafone.co.uk/mobile/best-sim-only-deals](https://www.vodafone.co.uk/mobile/best-sim-only-deals)
						- £16/mo, 5GB data, 12 month contract
			- My W5 area - O2 and Vodafone have the best coverage, Three to a lesser extent
		- [Check which UK mobile virtual network operator (MVNO) piggybacks off which network](https://www.moneysavingexpert.com/mobiles/piggybacking/)
		  collapsed:: true
			- Pros/Cons
				- Pros
					- Usually a better deal
				- Cons
					- Traffic is deprioritised for MVNOs
					- Data speed cap
			- UK networks and their MVNOs
				- EE: BT Mobile*, Plusnet Mobile*, Utility Warehouse. Smaller firms: 1pMobile*, The Phone Co-op*
				- O2: Giffgaff*, Tesco Mobile*, Sky Mobile*. Smaller firm: LycaMobile*
				- Three: ((654cbb47-7dca-4be3-9b27-e59d32b68f16)), Smarty*. Smaller firm: FreedomPop*
					- ((654cbb47-7dca-4be3-9b27-e59d32b68f16)) - ((644c0aca-5f97-48f6-9fdb-08563d95ca17))
				- Vodafone: Voxi*, Virgin Mobile* (1). Smaller firms: Asda Mobile*, Lebara Mobile*, TalkMobile\*
		- ((646c8171-0696-40f9-a644-bb14c67a1591))
	- {Archive}
	  collapsed:: true
		- [https://www.moneysavingexpert.com/mobiles/best-pay-as-you-go-sim-cards/](https://www.moneysavingexpert.com/mobiles/best-pay-as-you-go-sim-cards/)
	- _Related:_ ((6436adcd-e969-4bd9-ae99-4f22eb90b63f))
- {Archive}
  collapsed:: true
	- https://ssd.eff.org/en/module/problem-mobile-phones
- _Related:_
	- ((631fa93e-1087-4996-91b8-7526842b4ba8))
	- ((649b113b-aad4-46d9-b20e-3cfb66a0a190)) : ((6318f9b5-6ae9-4400-9f05-f0d538165ccc))
	- _See_ Replacing lost/damaged [Phone ( ((6318faff-7c2f-4d19-9ab3-8b0e4c027446)) )
	  ((62d0cbab-3aca-4af3-836d-b51792264a02))
	- ((631fa93c-6e5d-45fd-8497-7c857dc93d67))