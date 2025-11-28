- Principles
  collapsed:: true
	- Separate email and hosting
	  collapsed:: true
		- I've had to restore servers to a previous backup before, during which time
			- Email inbox is unavailable
			- Emails are lost
		- Get a webmail client which has a different SMTP configured
			- Allows emergency emails if mailgun cant send
- Infrastructure
  id:: 635036c9-08c9-47d6-ad33-98c1fc61a0dd
  collapsed:: true
  #Infrastructure
	- Infrastructure-as-a-Service (IaaS)
	  collapsed:: true
		- Cloud Computing Platforms
		  id:: 6463499f-3979-4c95-ac84-9b62840fb9cf
		  collapsed:: true
			- _Types of IaaS services_
				- DNS
				  collapsed:: true
				  id:: 6306a863-f972-441e-a315-829ba17420d5
					- _Choosing a privacy-friendly DNS service_
					  collapsed:: true
						- _Principles_
						  collapsed:: true
							- Get domains to implement DNSSEC for greater security
							- Set your OS to use a particular DNS or it'll use the DNS of whatever WiFi networks you connect to throughout the day
							- Host own DNS on home server to avoid logs?
							- Using unvetted DNS services can result in being tracked or MiTM'd
							  collapsed:: true
								- How can DNS be exploited?
									- Usually a resolver will tell each DNS server what domain you are looking for. This request sometimes includes your full IP address. Or if not your full IP address, increasingly often the request includes most of your IP address, which can easily be combined with other information to figure out your identity.
									- DNS request
									- This means that every server that you ask to help with domain name resolution sees what site you’re looking for. But more than that, it also means that anyone on the path to those servers sees your requests, too.
									- There are a few ways that this system puts users’ data at risk. The two major risks are tracking and spoofing.
								- Tracking
									- Like I said above, it’s easy to take the full or partial IP address info and figure out who’s asking for that web site. This means that the DNS server and anyone along the path to that DNS server — called on-path routers — can create a profile of you. They can create a record of all of the web sites that they’ve seen you look up.
									- And that data is valuable. Many people and companies will pay lots of money to see what you are browsing for.
									- a router offering to sell data
									- Even if you didn’t have to worry about the possibly nefarious DNS servers or on-path routers, you still risk having your data harvested and sold. That’s because the resolver itself — the one that the network gives to you — could be untrustworthy.
									- Even if you trust your network’s recommended resolver, you’re probably only using that resolver when you’re at home. Like I mentioned before, whenever you go to a coffee shop or hotel or use any other network, you’re probably using a different resolver. And who knows what its data collection policies are?
									- Beyond having your data collected and then sold without your knowledge or consent, there are even more dangerous ways the system can be exploited.
								- Spoofing (MiTM)
									- With spoofing, someone on the path between the DNS server and you changes the response. Instead of telling you the real IP address, a spoofer will give you the wrong IP address for a site. This way, they can block you from visiting the real site or send you to a scam one.
									- spoofer sending user to wrong site
									- Again, this is a case where the resolver itself might act nefariously.
									- For example, let’s say you’re shopping for something at Megastore. You want to do a price check to see if you can get it cheaper at a competing online store, big-box.com.
									- But if you’re on Megastore WiFi, you’re probably using their resolver. That resolver could hijack the request to big-box.com and lie to you, saying that the site is unavailable.
						- Enhancing DNS security
						  collapsed:: true
							- _Webmaster-side domain authentication_
							  collapsed:: true
								- DNSSEC
								  It's for authentication (prevent spoofing), doesn't prevent tracking. Done on webmaster side
									- A way of signing and providing validation for a subset of DNS records
									- https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-configure-dnssec.html
										- Attackers sometimes hijack traffic to Internet endpoints such as web servers by intercepting DNS queries and returning their own IP addresses to DNS resolvers in place of the actual IP addresses for those endpoints. Users are then routed to the IP addresses provided by the attackers in the spoofed response, for example, to fake websites.
										- You can protect your domain from this type of attack, known as DNS spoofing or a man-in-the-middle attack, by configuring Domain Name System Security Extensions (DNSSEC), a protocol for securing DNS traffic.
							- _DNS enhanced security protocols_
							  collapsed:: true
								- _Note:_ Don't use encrypted DNS t if using a VPN
								  source:: [https://privacyguides.org/providers/vpn/#info](https://privacyguides.org/providers/vpn/#info)
									- Unless your VPN provider hosts the encrypted DNS servers, no. Using DOH/DOT (or any other form of encrypted DNS) with third party servers will simply add more entities to trust, and does absolutely nothing to improve your privacy/security. Your VPN provider can still see which websites you visit based on the IP addresses and other methods. Instead of just trusting your VPN provider, you are now trusting both the VPN provider and the DNS provider.
									- A common reason to recommend encrypted DNS is that it helps against DNS spoofing. However, your browser should already be checking for TLS certificates with HTTPS and warn you about it. If you are not using HTTPS, then an adversary can still just modify anything other than your DNS queries and the end result will be little different.
									- Needless to say, you shouldn't use encrypted DNS with Tor. This would direct all of your DNS requests through a single circuit, and would allow the encrypted DNS provider to deanonymize you.
								- _Types_
									- DNS-over-HTTPS (DoH) and Mozilla Firefox's Trusted Recursive Resolver preference
										- Pros/Cons
											- Cons
												- Several
													- First, please understand that most people who object to DoH are not objecting to encrypted DNS, they're objecting to less-well-encrypted DNS. So the relevant comparison isn't generally with "regular DNS" (Do53) but instead with DNS-over-TLS (DoT), the standard for DNS encryption which was already widely deployed when DoH was cooked up and promoted, largely to people who weren't aware that it was undermining an already-solved problem.
													- I think there are three main issues with DoH:
														- **HTTPS stack fingerprinting**
															- Regular DNS and DNS-over-TLS use very stripped-down packets. They don't contain extra information besides what's necessary to serve the purposes of the _user_. By contrast, DoH uses an HTTPS stack, which contains a ton of extra information. That extra information can be used to [uniquely fingerprint](<[https://en.wikipedia.org/wiki/Device_fingerprint#Browser_fingerprint](https://en.wikipedia.org/wiki/Device_fingerprint#Browser_fingerprint)>) a user, in a way that's visible to the DoH server operator, and allows them to distinguish and track individual users as they move from location to location, in a way that was anonymous under Do53 or DoT. So **this loss of privacy is new to DoH**, and the parties who pushed DoH are, largely and not coincidentally, ones who make their money by monetizing users' information.  These same folks worked over the HTTPS stack for years, increasing their ability to fingerprint web users; now they've just re-purposed that same technology for fingerprinting DNS users.
														- **Net Neutrality**
															- DoH allows the server operator to send the user far more information than the user asked for, at the user's expense (using the user's bandwidth or data subscription, or utilization against their cap). If a DoH operator also happens to be a CDN, a "content distribution network," they can abuse this capability to stuff the user's machine full of answers which benefit their CDN customers. This is particularly problematic since this silent bundling of DoH and CDN functionality creates a structural imbalance which transparently favors the customers of that CDN, but which cannot equally favor the customers of competing CDNs. This is the very definition of a Net Neutrality violation. It expends the user's resources, without their knowledge or consent, to favor one third party over another third party, based on whether those third parties are paying new and extra charges to the second party, the CDN.  **This is a new loss of user autonomy and control over their resources, which did not exist with Do53 or DoT.** And, again, DoH was pushed by parties in the small intersection set of CDN operators who also operate public DNS resolvers. So, again, it doesn't look like coincidental malfeasance, it looks like bad people trying to be clever and not get caught.
														- **Undermining the standards process**
															- Last but not least, protocols work within a [framework](<[https://en.wikipedia.org/wiki/OSI_model](https://en.wikipedia.org/wiki/OSI_model)>) that ensures interoperability. That framework specifies clearly-bounded layers of functionality, which can be modularly exchanged, and which are agnostic to the layers above and below. That's how, for instance, the Internet protocol can work on top of both WiFi and cellular phones, or how Ethernet can work on top of both fiber and copper. Do53 is a layer 5 protocol, riding on top of either TCP or UDP at layer 4, on top of IP at layer 3, perhaps Ethernet at layer 2, and, for instance, fiber at layer 1. But the point is that each of these layers is independent of the others.  Thus DoT, DNS-over-TLS, is simply regular old DNS at layer 5, riding on top of TLS (encrypted TCP) at layer 4.  Everything else remains the same, and agnostic to the change.  Thus all your old tools continue to work, nothing is broken, no functionality lost.  DoT is a well-designed protocol, and in no small part, it's well-designed by being minimalist.  It does exactly what it's supposed to, and no more.  That also makes it easy to audit, and easy to understand the security implications of.  By comparison, DoH is DNS (layer 5) on top of HTTP (also layer 5) on top of TLS (layer 4).  Having a protocol of one layer riding on top of another protocol of the same layer really doesn't work. Thus DoH isn't \_really\_ DNS, it's a way of encapsulating DNS data inside something that's been modified to work on top of HTTP, a sort of a shim, and then using HTTP as a kind of catch-all transport layer (which is what TCP and UDP actually are).  It's just a complete mess, and not the sort of thing that people with protocol-design experience cook up.  It's the sort of thing that people used to coding web server stuff cook up.  So, a couple of big companies jamming it through the IETF, right over the top of an already-finished, much cleaner and better designed protocol, is abusing the process as well as the form. The result is a clunky, overweight protocol, which doesn't play well with others.  Do53 had its problems, but they were problems of being very early to the game, before a lot of other things had been figured out.  DoT doesn't really have significant problems, it just is what it is.
													- The first two points are significant and immediate privacy and autonomy losses for users in the real world. The last one may seem abstract, but when you chip away at the foundations that make everything possible, and then reward the folks who do the chipping, you're heading for disaster at an increasing rate of speed.
										- How recursive resolution (core part of DNS) works - different DNS servers talk to each other to find out who has the correct IP address for a particular domain name
										  source:: https://hacks.mozilla.org/2018/05/a-cartoon-intro-to-dns-over-https
										- We are introducing two new features to fix this — Trusted Recursive Resolver (TRR) and DNS over HTTPS (DoH).
											- Because really, there are 3 threats here:
												- Resolvers - You could end up using an untrustworthy resolver that tracks your requests, or tampers with responses from DNS servers.
												- On-path routers - they can track or tamper in the same way.
												- DNS servers - they can track your DNS requests.
											- So how do we fix these?
												- Avoid untrustworthy resolvers by using Trusted Recursive Resolver.
												- Protect against on-path eavesdropping and tampering using DNS over HTTPS.
												- Transmit as little data as possible to protect users from deanonymization.
													- QNAME minimisation
														- https://datatracker.ietf.org/doc/rfc7816/?include_text=1
														- Normally, a resolver would send the whole domain name to each server—to the Root DNS, the TLD name server, the second-level name server, etc. But QNAME minimisation instead means that it will only send the part that is relevant to the DNS server it’s talking to at the moment.
										- Feature
											- This means Firefox can ignore the resolver that the network provides and just use the one that is configured in Firefox
										- Mozilla recently created "DNS over HTTPS", a new IETF standards effort that we’ve championed. This is because most DNS requests are sent unencrypted
										- Mozilla also added Trusted Recursive Resolver, a new secure way to resolve DNS that we’ve partnered with Cloudflare to provide
										- Mozilla has a new feature, "Trusted Recursive Resolver" (TRR), that sends all DNS requests through Cloudflare in the U.S. by default, opening up your browsing activity to snooping.
										  source:: https://blog.ungleich.ch/en-us/cms/blog/2018/08/04/mozillas-new-dns-resolution-is-dangerous/
											- You can override the default setting -- instructions are at the bottom of the post:
												- 1. Enter about:config in the address bar
												- 2. Search for network.trr
												- 3. Set network.trr.mode = 5 to completely disable it
													- 3] Change network.trr.mode to 2 to enable DoH. This will try and use DoH but will fallback to insecure DNS under some circumstances like captive portals. (Use mode 5 to disable DoH under all circumstances.)
											- 4] Set network.trr.uri to your DoH server. Cloudflare’s is https://mozilla.cloudflare-dns.com/dns-query but you can use any DoH compliant endpoint.
											- More info on TRR preferences
											  https://gist.github.com/bagder/5e29101079e9ac78920ba2fc718aceec
										- (TRR stands for Trusted Recursive Resolver – it is the DoH Endpoint used by Firefox.)
										- https://wiki.mozilla.org/Trusted_Recursive_Resolver
										- https://bugzilla.mozilla.org/show_bug.cgi?id=1434852
										- Create a policy to disable DNS over HTTPS
										  https://bugzilla.mozilla.org/show_bug.cgi?id=1484843
									- DNSCRYPT
										- https://www.reddit.com/r/linux/comments/7owb1s/psa_dnscrypt_is_now_abandoned/
										- http://dnscrypt.org/
										- Secure communications between a client and a DNS resolver.
										- _Supported by these public DNS resolvers_
											- OpenNIC
										- https://dnscrypt.info/public-servers
										- Use DNSCrypt-Proxy client (cross-platform)
										  https://github.com/jedisct1/dnscrypt-proxy/releases
											- Android
											  https://github.com/Magisk-Modules-Repo/dnscrypt-proxy-magisk
										- Created by OpenDNS
											- OpenDNS launched its encrypted DNS service DNSCrypt back in 2012 and has been offering it ever since. It protects DNS look-ups made by your system by encrypting them, similar to how your Internet traffic is encrypted when you connect to https websites.
											- The company released DNSCrypt to Github and others have started to implement the feature into third-party services.
										- Q4 2019 now supports anonymised DNS
										  https://www.reddit.com/r/privacytoolsIO/comments/djciee/dnscrypt_now_offers_anonymized_dns/
									- DNS-over-TLS (DoT)
								- _Comparisons_
									- Comparisons
										- DNS-over-HTTPS and DNS-over-TLS
											- https://news.ycombinator.com/item?id=16728385
												- For TLS
													- They are effectively the same thing, but HTTPS has the added overhead of the HTTP headers per request
												- For DoH
													- Some ISPs block outbound DNS from customers to anywhere but their resolvers, filtering based on target port. This is a particularly common trick in countries that attempt to censor the internet.
														- It's a lot harder to do that with DNS-over-HTTPS because it looks like normal traffic.
														- That said, in this case ISPs can just null route the IP address of the obvious main resolvers such as 1.1.1.1. I imagine most of the benefit is surely to people who can spin up their own resolvers.
													- Dns over https would be harder for governments and other middleman to block or intercept, despite it being less efficient. It would look like any other https request. Especially if browsers agreed to universally support it.
										- DNSCRYPT and DNS-over-HTTPS
											- dnscrypt-proxy also supports DNS-over-HTTPS and is probably the most popular DoH client. You can use it to connect to Cloudflare or other DoH servers, and this will not be limited to queries sent by Firefox. adGuard app on android also allows dnscrypt to route all the phone communications go through the dns crypt servers encrypted without rooting.
										- DNSCRYPT and DNS-over-TLS
										  source:: https://tenta.com/blog/post/2017/12/dns-over-tls-vs-dnscrypt
											- So although DNSCrypt provides a significant security advantage, it comes with other disadvantages.
												- 1. Not completely encrypted: Even though the domain requested (question) and IP address (answer) is hidden, the complete process is not obfuscated. The total number of questions, their relative size and more remain available. Furthermore, it remains trivial to identify that you are, in fact, performing DNS resolution.
												- 2. Complex and not well supported: In the world of encryption, it's always safer to go with standardized protocols that have gone through a rigorous review process. Unfortunately DNSCrypt has not been standardized yet, and some of the ways it uses cryptography are unusual.
												- 3. Hard to use: Because DNSCrypt isn't standardized, very few programs natively support it, requiring users to download and configure helper applications, significantly increasing the difficulty of use and risk of misconfiguration.
											- DNS over TLS takes a completely different approach
												- Establishing a fully encrypted tunnel between your computer and the DNS server. Rather than sending requests in the clear, with just the critical data encrypted, the whole connection is encrypted.
												- Furthermore, since TLS is the encryption protocol used to secure almost all other internet services, the technology is well understood and constantly improved.
							- Methods
							  collapsed:: true
								- Certificate Patrol browser extension
									- http://patrol.psyced.org/
									- The X.509 trust model isn't working, it has become the trust in who has the money.
									- Not compatible with Firefox Quantum
									  https://addons.mozilla.org/en-GB/android/addon/certificate-patrol/
								- _Testing DNS_
									- https://www.dnsleaktest.com
								- I also suggest setting your router to intercept DNS traffic to force all devices on your network to use the DNS service of your choice. If you're going to use the Tor network or a VPN I would also consider setting them up at the router level if you can live with the downside of slower network speeds.
								- dnsprivacy-monitoring [Jenkins]
								  https://dnsprivacy.org/jenkins/job/dnsprivacy-monitoring/
							- More on how DNS works
							  collapsed:: true
								- HTTP Protocol
									- HTTP Alternative Services (Alt-Svc)
										- http://httpwg.org/http-extensions/alt-svc.html
										- https://tools.ietf.org/html/rfc7838
										- Explanation
										  https://www.mnot.net/blog/2016/03/09/alt-svc
										- Alt-Svc header
										  source:: https://medium.com/@alecmuffett/different-ways-to-add-tor-onion-addresses-to-your-website-39106e2506f9
											- The Alt-Svc header is feature in HTTP protocol which has recently (Sep’18) landed in TorBrowser (8.0). The Alt-Svc header informs the client that “…you accessed me via www.example.com but you may also transparently access me at www.examplexamplexam.onion…” — and then expects TorBrowser to act accordingly.
											- Alt-Svc Pros
												- Has very positive benefits for load-balancing in architectures where all resources are effectively site-owned resources by virtue of being under your physical control, or else under the physical control of a third party who implements Onions on your behalf, e.g. Cloudflare.
												- Excellent solution for infrastructure providers (Hosting Providers, Web-Accelerators, CDNs) to offer their customers, if and where it has no consequential impact upon the customer’s extant security threat model; e.g.: “Cloudflare already sees all my traffic content in cleartext, irrespective of whether or not it arrives over an onion circuit, so it’s totally okay to use them to provide me with onion addresses…”
												- People who worry about Usability are happy that all those messy, ugly onion addresses are hidden away where the user cannot see them.
											- Alt-Svc Cons
												- Absolutely requires HTTPS (Pro: does not need an EV HTTPS certificate,
												- Con: cannot load-balance non-HTTP-based protocols) and…
												- …the first connection will likely not be via an Onion, but instead via a Tor exit-node, yielding possible congestion / slow-start / poor user experience.
												- [author note: someone will surely say “…but requiring HTTPS is a ‘Pro’…” and I mostly won’t argue with that; but these two issues go together…]
												- Problematic in multi-cloud deployments or where CDNs are heavily-used but are not site-owned resources; an Alt-Svc header can only be issued by the specific origin which serves the data (no wildcards) so if you use CDN.COM and cite links like href=“https://example.cdn.com/foo.js” to serve resources, the only way to onionify your CDN traffic is to convince CDN.COM to issue Alt-Svc headers from example.cdn.com which will point at your self-owned CDN onion addresses on your behalf; and CDN.COM will either have to issue Alt-Svc headers for all requests to example.cdn.com (consuming extra bandwidth & costing you money) or else they will need to track Tor exit nodes in order to selectively issue the headers.
												- People who care about Trust will be concerned that it’s not clear to the user if, whether, or how much of, the website has been loaded over onion network interfaces; not least for lack of a visible, ugly, onion address.
												- The Las Vegas Rule “cookies” codicil will likely not be satisfied; however this is possibly a matter of taste.
						- _Choosing a resolver_
						  collapsed:: true
							- Self-hosting DNS
							  collapsed:: true
								- Pros
									- simple local caching dns server that sits on a raspberry pi doing all the heavy lifting here. That would be pretty cool. Secure DNS for the whole home! (Begone you cretinous ISP's who log my DNS queries!)
								- Bind and DNS (advanced) https://np.reddit.com/r/privacy/comments/5r8gcz/limiting_outgoing_domain_name_resolution/
								- Unbound
								  https://en.wikipedia.org/wiki/Unbound_%28DNS_Server%29
									- Validating, recursive, and caching DNS server.
									- http://www.unbound.net/
							- ? choose your ISP's own DNS, since they already know where you're connecting to anyway ?
							  collapsed:: true
								- However these are usually sent UNENCRYPTED
								- Why would you replace your ISP's DNS server with another one?
									- There are a variety of problems with the DNS protocol ("the language of DNS"). DNS requests are usually sent unencrypted and potentially everyone between you and the DNS server can read your DNS requests. Mozilla is using a new technique to transport requests over https, which encrypts the data. That is generally speaking a good thing. However usually the DNS servers that you use are local DNS servers (from your ISP) and thus the attack vector (i.e. who can spy on you) is local.
								- Unpopular opinion now. If you care about privacy, do not run your own DNS resolver at home. Your ISP will be able to see all the requests between your resolver and the authoritative servers, as there is no way to encrypt that communication. For the most paranoid (and technical), I would recommend running a DNS resolver in the cloud with DNSCrypt or DOH and using that instead.
							- _Public DNS resolvers_
							  collapsed:: true
							  Look for non-14 Eyes
								- _Unencrypted DNS_
									- OpenDNS (part of Cisco)
									- OpenNIC
									  http://www.opennicproject.org/
										- Open, democratic, and anti-censorship DNS provider.
										- Non-14 eyes Swiss
										  https://servers.opennic.org/edit.php?srv=ns1.zh.ch.dns.opennic.glue
										- http://www.opennicproject.org/configure-your-dns/
										- https://en.wikipedia.org/wiki/OpenNIC
									- CloudNS
									  https://cloudns.com.au/
										- DNS hosting with DNSCrypt, DNSSec, and Namecoin support.
								- DNSCRYPT
									- https://dnscrypt.info/public-servers
									- Cloudflare
										- dnscrypt-proxy is compatible with Cloudflare and now has built-in support for Tor.
										- Just add `proxy = "socks5://127.0.0.1:9050"` to the configuration file.
								- DNS-over-HTTPS (DoH)
									- Current
										- https://mozilla.cloudflare-dns.com/dns-query (unfiltered by CloudFlare)
										- https://dns.google.com/experimental (unfiltered by Google — the most stable and running for longer)
										- https://doh.cleanbrowsing.org/doh/family-filter/ (filtered by CleanBrowsing, blocks adult content)
										- https://doh.cleanbrowsing.org/doh/secure-filter/ (filtered, blocks malicious domains only)
									- https://dnsprivacy.org/wiki/display/DP/DNS+Privacy+Public+Resolvers
									- https://github.com/curl/curl/wiki/DNS-over-HTTPS#publicly-available-servers
									- rfc 8336. h2 coalescing. h2 push. caching. it starts to add up to a very interesting story.
										- HTTP/2 connection coalescing
										  AKA connection reuse
											- _Privacy risk for Tor_
												- This can be used to track you if you're using Tor (changing IP address between access of each site)
											- After you do the DNS lookup to find the IP address, you still need to connect to the web server at that address. To do this, you send an initial request. This request includes a server name indication, which says which site on the server you want to connect to. And this request is unencrypted.
											- That means that your ISP can still figure out which sites you’re visiting, because it’s right there in the server name indication. Plus, the routers that pass that initial request from your browser to the web server can see that info too.
											- However, once you’ve made that connection to the web server, then everything is encrypted. And the neat thing is that this encrypted connection can be used for any site that is hosted on that server, not just the one that you initially asked for.
											- This is sometimes called HTTP/2 connection coalescing, or simply connection reuse. When you open a connection to a server that supports it, that server will tell you what other sites it hosts. Then you can visit those other sites using that existing encrypted connection.
											- Why does this help? You don’t need to start up a new connection to visit these other sites. This means you don’t need to send that unencrypted initial request with its server name indication saying which site you’re visiting. Which means you can visit any of the other sites on the same server without revealing what sites you’re looking at to your ISP and on-path routers.
											- With the rise of CDNs, more and more independent sites are being served by a single server. And since you can have multiple coalesced connections open, you can be connected to multiple shared servers or CDNs at once, visiting all of the sites across the different servers without leaking data. This means this will be more and more effective as a privacy shield.
										- As a complete layperson, h2 push might be interesting because a DNS resolver could learn to detect patterns in DNS queries (e.g. someone who requests twitter.com usually requests pbs.twimg.com and abs.twimg.com right after) and start to push those automatically when they get the query for twitter.com.
									- See 'Trusted Recursive Resolver'
									  intralink2:: https://workflowy.com/#/419b904612ed
								- DNS-over-TLS (DoT)
									- https://dnsprivacy.org/wiki/display/DP/DNS+Privacy+Public+Resolvers
									- 1.1.1.1 does support DNS-over-TLS as well: https://developers.cloudflare.com/1.1.1.1/dns-over-tls/
								- Onion service
									- Notes
										- Onion services can be used as your Trusted Recursive Resolver
											- If you're using Firefox Nightly, you can set …http://dns4torpnlfs2ifuz2s2yf3fc7rdmsbhm6rw75euj35pac6ap25zgqad.onion as your Trusted Recursive Resolver (https://wiki.mozilla.org/Trusted_Recursive_Resolver …) to resolve via Tor. This is an alpha feature and there are a few kinks to work out, so try it out but don't rely on it yet.
											  source:: https://twitter.com/grittygrease/status/1004015405223088133
											- One of the coolest things about this is if you go to http://tor.cloudflare-dns.com , it will serve you an Alt-Svc header for the .onion, so next time you visit http://tor.cloudflare-dns.com it will connect through the hidden service under the hood. No more worries about malicious exit nodes!
										- Note: Tor by default uses the exit node's DNS
										  https://news.ycombinator.com/item?id=17247492
										- Note: if using a Tor it's difficult to correlate users (it's not a big privacy leak)
									- What services
										- https://blog.cloudflare.com/welcome-hidden-resolver
						- SNI
						  collapsed:: true
						  Unencrypted, major issue
							- Unfortunately the Server Name Indicator header in HTTPS messages also reveals the name of the website contacted by the user so provides a similar leakage channel for web traffic as the DNS queries. However there is work underway to try to encrypt that information too.
						- _[Learning Resources]_
						  collapsed:: true
							- [https://privacytools.io/providers/dns](https://privacytools.io/providers/dns)
							- https://dnsprivacy.org/wiki/
						- Related: [Internet connection middlemen](https://workflowy.com/#/53ecf60dfe10)
						  #Privacy
						- 1 Backlink
						  collapsed:: true
							- See [Choosing a privacy-friendly DNS service](https://workflowy.com/#/be67377ca998)
							  #Infrastructure
					- _Decentralised DNS_
					  collapsed:: true
						- Pros/Cons
						  collapsed:: true
							- Pros
								- Domains can be hijacked
								  collapsed:: true
									- [Peter Sunde: dark.fail domain was hijacked through fake court order](https://twitter.com/brokep/status/1389317881737977860) to the domain registrar
										- [https://news.ycombinator.com/item?id=27031650](https://news.ycombinator.com/item?id=27031650)
										- [https://twitter.com/brokep/status/1389317881737977860](https://twitter.com/brokep/status/1389317881737977860)
										- Series of events
											- First, the domain was registered through a service I started, @njal_la(or transferred in, not sure here). Njalla in turn uses @tucows as a registrar for .FAIL domains.
											- On the 28th of April, Tucows receives a court order, from Amtsgericht Köln, the district court of Cologne, NRW, Germany. It contains a list of domain names that they want handed over. Two of three domains listed are registered through Njalla, the last one with [@hover](https://mobile.twitter.com/hover).
											-
						- _Solutions to Zooko's triangle_
						  collapsed:: true
						  human-meaningful, secure and decentralised
							- Alternative TLDs on blockchain
								- Namecoin
								  collapsed:: true
								  .bit
									- .bit websites for decentralised DNS
									- https://bit.namecoin.org/
									- IPFS plans to be compatible with Namecoin
									- 4.6GB as of Sep 2016
									  https://bitinfocharts.com/namecoin/
									- No one wants to download a blockchain to their phone to resolve domain names (SPV/light clients needed)
										- We'd still all end up relying on intermediaries to do look-ups, but at least it would be less vulnerable to censorship.
								- Ethereum Name Service
								  .eth
								- Blockstack
								  collapsed:: true
								  .id
									- https://blockstack.org/
								- Emercoin (.emc, .coin, .lib and .bazar TLDs).
								- Eg Firefox extensions #Productivity https://workflowy.com/#/caec280c27e7
							- Decentralised certificates authority + P2P root DNS
								- Handshake
									- Pros/Cons
									  collapsed:: true
										- Pros
											- Assigns every TLD, unlike other projects which only decentralise one TLD
									- _Journal_
									  collapsed:: true
										- Wed, Jan 13, 2021 - trying to access these domains currently isn't easy compared to ENS or Namecoin.
									- [handshake.org](http://handshake.org)
									- https://www.reddit.com/r/handshake
									- this project is building a decentalized certificate authority and an experimental peer-to-peer root dns
									  collapsed:: true
										- Certificate Authority
											- Compatible by legacy DNS through reservations
												- First, the top 100,000 alexa domains are reserved, so you can’t register Google and go redirect it to your site selling pet rocks. This was a big problem with previous attempts at decentralized systems.
												- Second, the existing TLDs are also reserved, so you can’t just go register .com domains that will eventually conflict with Versign-managed .coms.
											- It allows for any TLD to be used (except for existing TLDs, and not everything available on launch)
												- because anyone can register a tld, another option is to simply USE tlds as your domain. So for example, bruce lee can just register “brucelee” and use it, sans any subdomains. This is pretty awesome, but its also a new pattern for users, and they will have to get used to it. Browsers will also have to choose to adopt allowing bare TLDs instead of assuming they are search terms (currently if you type brucelee into a browser, it won’t do a DNS lookup but will just google brucelee for you). That said, if you enter "brucelee/" your browser will correctly recognize that as a domain. We believe that browsers will offer optional support for this pretty quickly (Brave is already [evaluating](https://twitter.com/BrendanEich/status/1036389193864208384)), and perhaps some will make it the default soon, but in the beginning domains that follow the “thing.domain” pattern will be most in demand because they will simply “work” with existing browsers, as long as users point their DNS at a handshake-supporting server, or if the large DNS servers begin to support Handshake domains.
											- Why is the TLD I want "Coming Soon"?
												- Handshake names are released over the course of the first year after the mainnet launch so that users who learn about Handshake late will still have access to good names. This means that many of the names will open for bidding at a later date. Importantly, if you’re a Namebase user you can add TLDs to your watchlist to get notified when they release.
										- P2P Root DNS
											- Handshake is a decentralized, permissionless naming protocol compatible with DNS where every peer is validating and in charge of managing the root zone with the goal of creating an alternative to existing Certificate Authorities. Its purpose is not to replace the DNS protocol, but to replace the root zone file and the root servers with a public commons.
											- The Handshake protocol maintains the root zone file in a decentralized manner, making the root zone uncensorable, permissionless, and free of gatekeepers.
									- About
									  collapsed:: true
										- Full node and SPV/light nodes available
										- Token distribution
											- it just came out of stealth sporting a working implementation and an impressive list of investors on board. an interesting part is that all $10.2m it raised are donated to notable free open source projects.
											- most of the tokens are distributed to open source community, so if you have an active github, you are eligible for some.
										- DNS resolution privacy
											- In Handshake, the P2P layer used to communicate with peers and propagate transactions is end-to-end encrypted by default [3]. Handshake has implemented a Noise Protocol, similar to the one used by the Lightning Network’s LND. If you find yourself having someone else resolve your names on your behalf, that peer will only be able to see a hash of the HNS name being resolved.
												- https://github.com/lightningnetwork/lnd/blob/master/brontide/noise.go
											- Your privacy is important, especially when traversing the decentralized web; Handshake has taken many steps technically to ensure those who utilize HNS can maintain the utmost privacy possible. They also have plans in the works to improve privacy going forward (See: Zone Replication and DNSCurve) that could enable peers in the network to act as “proxies”, resolving the requests for you, providing you even more privacy.
											  https://handshake.org/files/handshake.txt
											- Further plans and thoughts on how the core contributors are potentially seeking to improve privacy — that fall outside the scope of this post — can be found in the paper.
											  https://handshake.org/files/handshake.txt
									- How to Use
									  collapsed:: true
										- 1. Browser extension for DNS resolution
											- https://chrome.google.com/webstore/detail/namebase-handshake-extens/npfmealdhkkjfdajjkhegghlckcldfle
										- 2. Change your OS settings to point to the Handshake resolver. You can follow the instructions here (link to blog post) to change your DNS resolver settings
											- SPV resolver daemon?
											  https://github.com/handshake-org/hnsd
										- 3. Long term, the goal/hope is for browsers to start integrating Handshake
											- Brave has already expressed interest in Handshake and will likely be the first browser to adopt it.
											- Firefox change Tested Recursive Resolver
										- Current used method: easyhandshake TRR hardcoded into Firefox about:config in "Handshake-DNS" Firefox profile (separate browser folder)
											- [https://matthewzipkin.medium.com/resolving-hns-names-using-dns-over-https-94643fe62ecd](https://matthewzipkin.medium.com/resolving-hns-names-using-dns-over-https-94643fe62ecd)
										- [https://learn.namebase.io/starting-from-zero/how-to-access-handshake-sites](https://learn.namebase.io/starting-from-zero/how-to-access-handshake-sites#level-3-dns)
									- _Test sites_
									  collapsed:: true
										- [http://welcome.nb/](http://welcome.nb/)
										- Sci-Hub
										  [http://sci-hub.hns](http://sci-hub.hns)
											- _Related:_ [Sci-Hub](https://workflowy.com/#/46dff73b2a86)
											  #Science
										- [https://github.com/namebasehq/awesome-handshake](https://github.com/namebasehq/awesome-handshake)
									- Handshake TLD domain registrars
									  collapsed:: true
										- https://namebase.io/
										- Specific TLD registrars
											- Eg .hijfyh domain registrar
									- _Related:_
									  collapsed:: true
										- [Resolvr](https://workflowy.com/#/5d4b2d093fb4)
									- _{Archive}_
									  collapsed:: true
										- Detailed blog posts
											- https://medium.com/amentum/the-case-for-handshake-9b0af0d989fe
									- 2 Backlinks
									  collapsed:: true
										- See [Handshake](https://workflowy.com/#/566b2f22243e)
										- See [Handshake](https://workflowy.com/#/566b2f22243e)
										  #Infrastructure
						- There is a plan by IETF to reserve an .alt TLD for use by non-DNS name services, so this could put all its domains under handshake.alt
						  collapsed:: true
							- https://tools.ietf.org/html/draft-ietf-dnsop-alt-tld
						- https://decentralized.blog/ten-terrible-attempts-to-make-ipfs-human-friendly.html
						- Secure and Decentralised (but not human readable
						  collapsed:: true
							- .onion hidden services
							- GNS from GNUnet
							  collapsed:: true
								- Unlike DNS, GNS does not rely on central root zones or authorities. Instead any user administers his own root and can can create arbitrary name value mappings. Furthermore users can delegate resolution to other users' zones just like DNS NS records do. Zones are uniquely identified via public keys and resource records are signed using the corresponding public key. Delegation to another user's zone is done using special PKEY records and petnames. A petname is a name that can be freely chosen by the user. This results in non-unique name-value mappings as www.bob.gnu to one user might be www.friend.gnu for someone else.
							- See cjdns (public key address + DHT routing)
							  collapsed:: true
								- https://github.com/cjdelisle/cjdns
							- Beame
							  collapsed:: true
							  turn any machine with a web browser into a HTTPS server (don't require static/public IP)
								- HTTPS Server without a public/static IP. TLS Tunnels with decentralized credentials. https://www.beame.io
								- Beame.io is an information security company at the cutting edge of decentralized credential and identity technology. We invented a way to turn any machine with a web browser into a HTTPS server. With our technology, machines on private networks can be accessed on-demand in an end-to-end encrypted session.
								- Deploy SSL certificates to machines without public IPs. Get end-to-end encrypted connections to your computer from any web browser on any network.
								- Comparison to Let's Encrypt
									- http://i.imgur.com/Y9gAV0K.png
						- _Unknown _
						  collapsed:: true
							- OpenAlias
								- https://openalias.org/
						- Threat entities in centralised DNS
						  collapsed:: true
							- ICANN
							- Domain Registries
							  collapsed:: true
							  VeriSign, Donuts, Google, Amazon Registry Services
								- Generic TLDs (gTLDs)
								- Country Code TLDs (ccTLDs)
								- https://en.m.wikipedia.org/wiki/List_of_Internet_top-level_domains
							- Domain Registrars
							  GoDaddy, Namecheap, Hostgator, Google Domains etc
							- Certificate Authorities
							- DNS hosting
							  collapsed:: true
								- OpenDNS
								- Google DNS
								- CloudFlare
								- Offered by own ISP often. Or
								- Freemium DNS hosting
								  Dynu.com, No-IP, EveryDNS, EasyDNS, Afraid, Zoneedit and ClouDNS
						- ICANN ownership being given away supposedly won't affect root DNS servers except making them more distributed
						  collapsed:: true
							- The ICANN transfer doesn't affect ownership of TLDs, the organisations that maintain the root DNS servers are not being transferred. Seriously, stop blowing the ICANN thing out of proportion, it will have absolutely NO EFFECT on the internet whatsoever, for good or for bad.
								- (Network security engineer here, this is super not in depth because I don't want to be writing for an hour.)
							- DNS is the system that is used to 'translate' the URLs we enter into browsers, into the actual logical addresses where that site is, allowing us to actually "go to" Facebook.com when we type in Facebook.com.
							- It is a VASTLY distributed, recursive system, that essentially keeps asking 'itself' the same question, until it gets an answer. LONG story short, there are 'root' DNS servers that are the grand-daddies, and the US has control over a majority of those via our commerce department.
							- By "Handing Over Control," articles / videos are stating that because the technical ownership isn't being renewed by the IANA, and ownership will be moved to ICANN, which technically DOES have a bit of outside influence, despite being based in the US, and a long time integral part of the internet, just like IANA. (These articles conveniently leave out that IANA is bloody OWNED by ICANN, meaning that the big bad influence ... has already been technically going on.) There is a metric FUCKTON more depth to go into in terms of the architecture and logistics behind DNS and this diversification of operations (like DNS is really interesting in a super dry nerdy kind of way) but sufficed to say, jack all will realistically change with this move.
							- If ANYTHING, this is a move the industry (outside of the US) has been asking for, for a WHILE (the distribution of root servers to be more world-wide.)
						- Convincing web projects to add a decentralised DNS
						  collapsed:: true
							- Add IPNS link to access IPFS version
							- Currently the only option to access the IPFS version is via centralised DNS (a subdomain redirect) and there are [many privacy issues with DNS](<[https://hacks.mozilla.org/2018/05/a-cartoon-intro-to-dns-over-https/](https://hacks.mozilla.org/2018/05/a-cartoon-intro-to-dns-over-https/)>).
							- For now, since only IPFS-Companion has a built in resolver instead of relying on a centralised API:
								- Could you post the immutable IPNS link on your [documentation](http://docs.hueyhex.io/access.html)? That way people can access the IPFS version by themselves using the [IPFS Companion](https://addons.mozilla.org/en-US/firefox/addon/ipfs-companion/) browser extension or an IPFS gateway.
							- When there is a browser extension with JavaScript (in-built) resolver:
								- This could be Namecoin, Emercoin etc. They could then be easily accessed via a browser extension like [this one](https://addons.mozilla.org/en-US/firefox/addon/b-dns/).
						- Assorted
						  collapsed:: true
							- Tip: Other possibilities to register .bit domains: domaincoin.net, peername.com,dotbit.me
							- Tip: You can verify your domain on namecha.in, for example: zeroid.bit
							- https://en.m.wikipedia.org/wiki/Alternative_DNS_root
							- Edit
							- OpenNIC
							- RealNames
							- Firefox extension
							- https://bit.namecoin.org/freespeechme.html
							- Also many bit proxies online
						- 1 Backlink
							- See [Decentralised DNS](https://workflowy.com/#/5e845ecbe383)
							  #Infrastructure
					- Domain Registrars
					  collapsed:: true
						- _Anonymous domain registrar_
						  Non-14 Eyes, accepts cryptocurrency
							- Njalla
							  collapsed:: true
								- Pros/Cons
									- Pros
										-
									- Cons
										- [Temporarily banned nitter.net after a false accusation of CSAM](https://news.ycombinator.com/item?id=38986880)
									- Unclear
									- Comparisons
								- Parent company in Nevis (Caribbean island)
								- 15 €/year for .com etc
								- https://njal.la/
								- http://njalladnspotetti.onion/
								- Accepts cryptocurrency, PayPal
								- https://news.ycombinator.com/item?id=14177597
							- epik.com
							- easyDNS becomes first domain provider to accept ethereum
							  collapsed:: true
								- https://www.easydns.com/blog/2017/10/04/ethereum-payments-now-accepted-for-all-services/
							- Not evaluated
							  collapsed:: true
								- Prq.se
									- https://en.wikipedia.org/wiki/PRQ
								- Nforce.com
							- https://discuss.privacyguides.net/t/privacy-concerns-regarding-namecheap-being-purchased-for-1-5-billion/31077/13
							-
						- Cloudflare
						  https://www.cloudflare.com/products/registrar/
						- Namecheap
					- _DNS setup for business _
					  collapsed:: true
						- TTL
						  collapsed:: true
							- Updating TTL (time-to-live) takes time to propagate also
							- What TTL values for what records?
								- A record - strike a balance as you may change hosts. Up to 1 hour (3600s) is decent. 1800 TTL is good - DigitalOcean used to use that as the default
								- CNAME record – In many cases, a CNAME record will never be modified (ex. pointing www.example.com to example.com’s A record). In those scenarios, a 12 hour to 1 day TTL is a good compromise as the benefits of caching outweigh need for a faster propagation time. If your CNAME record could potentially change (such as if you are using a CDN), you will want to a have a lower TTL.
								- MX Record – MX records rarely, if ever, change, especially if you are using an email provider with a good track record or you have lots of redundancy when self hosting. You can usually set this to a 12 hour or 1 day TTL. If you want to ensure faster propagation times in the event of an emergency, a 1 to 4 hour TTL is a good compromise.
								- TXT Records – Most commonly used for SPF or DKIM records. Usually safe to set in the 1 hour to 12 hour range since they rarely change.
						- Nameservers
						  collapsed:: true
							- Authoritative nameservers know where the IP address<>domain mapping actually is
							- At domain registrar choose to use different nameservers to manage my DNS (zone files)
						- Once you have saved your changes to the nameservers listed with your domain, you will need to wait some time for the domain to propogate. This is when the domain registry communicates the nameserver changes with your Internet Service Provider, so that they can cache the new nameservers to ensure quick site connections. This process usually takes 30-45 minutes, but could take up to a few hours depending on your registry and ISP's communication methods.
						- Use A records for WWW
						  collapsed:: true
							- CNAME can only point to another domain name, not an IP address
							- Leaving mail.postmymeds.co.uk to point to the old IP (A record)
						- Email host server DNS
						  collapsed:: true
							- A record: To keep the inbox on the old server the "mail.postmymeds.co.uk" value needs to be 'xxx.xxx.xxx' with the xxx being the IP address
							- MX record: keep as "0 mail.postmymeds.co.uk"
					- 3 Backlinks
					  collapsed:: true
						- See DNS
						  #Infrastructure [DNS](https://workflowy.com/#/3b93cb4c2994)
						- Related: [DNS](https://workflowy.com/#/3b93cb4c2994)
						  #Infrastructure
						- DNS
						  #Software [https://workflowy.com/#/3b93cb4c2994](https://workflowy.com/#/3b93cb4c2994)
				- Web hosting
				  collapsed:: true
					- Non-14 Eyes, accepts cryptocurrency
					  anonymous web hosting
					- Web admin panels
						- _Proprietary_
							- cPanel
							- Cloudways
						- _Open-source_
							- Ajenti
							  collapsed:: true
								- http://ajenti.org/
							- Vesta Control Panel
							  collapsed:: true
								- https://vestacp.com/
							- Webmin
							- [Cockpit Project — Cockpit Project](https://cockpit-project.org/)
							- [GitHub - kalaksi/lightkeeper](https://github.com/kalaksi/lightkeeper)
								- https://flathub.org/apps/io.github.kalaksi.Lightkeeper
							-
				- Compute (virtual servers)
				- Serverless
				  collapsed:: true
				  AKA microservices
					- Pros/Cons
						- Pros
							-
						- Cons
							- Amazon Prime Video got rid of serverless and used normal virtual servers for huge cost savings
								- [Scaling up the Prime Video audio/video monitoring service and reducing costs | Hacker News](https://news.ycombinator.com/item?id=35811741)
								- [Scaling up the Prime Video audio/video monitoring service and reducing costs by 90% - Prime Video Tech](https://www.primevideotech.com/video-streaming/scaling-up-the-prime-video-audio-video-monitoring-service-and-reducing-costs-by-90)
							- [Majestic Monolith](https://m.signalvnoise.com/the-majestic-monolith) is a good alternative
							- Dropbox decided to drop AWS and build it's own infrastructure
						- Unclear
							-
						- Comparisons
							-
						- Related: ((63f4bf2e-0811-427e-a54b-1b9b38963017))
					- ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
					- ((64b7c5ea-fc23-4c8f-bba3-40309679cf7d))
					- ((653bb0cc-77e8-4ad0-b2b1-6d5d2ee052fa))
				- Block storage (file systems)
				  collapsed:: true
					- Object storage (buckets) is probably PaaS
				- Containers-as-a-Service (CaaS)
				  id:: 6463499e-ee8c-4db4-9ba2-6b0307e7b528
				  collapsed:: true
					- [Docker Cloud](https://cloud.docker.com)
					  collapsed:: true
						- Supersedes [Docker Hub](https://hub.docker.com/)
						- https://docs.docker.com/docker-cloud/
					- Docker Enterprise Edition (EE) / Docker Datacenter
					  collapsed:: true
						- See Dokku or Cloudron for a Docker-powered PaaS
						- It's like Docker Cloud + a cluster
						- _Features_
							- Docker Universal Control Plane (UCP)
							  is the enterprise-grade cluster management solution from Docker.
								- https://docs.docker.com/datacenter/images/ucp.png
								- https://docs.docker.com/datacenter/ucp/2.1/guides/
							- Docker Trusted Registry (DTR) - alternative to Docker Distribution
							  enterprise-grade image storage solution from Docker
						- https://store.docker.com/editions/enterprise/docker-ee-server-ubuntu
						- https://store.docker.com/editions/enterprise/docker-ee-aws?tab=description
						- https://blog.docker.com/2016/11/three-considerations-docker-datacenter-deployment/
						- 1 Backlink
							- See [Containers-as-a-Service (CaaS)](https://beta.workflowy.com/#/7bd4b0b56d86) e.g. <a href="https://beta.workflowy.com/#/79a035ebe732">Docker Cloud</a>, <a href="https://beta.workflowy.com/#/b0e3ab3e186c">Docker Enterprise Edition (EE) / Docker Datacenter</a>
							  #Infrastructure
					- _Kubernetes-based_
					  collapsed:: true
						- _General purpose_
							- Google Container Engine
							  https://cloud.google.com/container-engine/
							- Azure Container Service
							  https://azure.microsoft.com/en-us/services/container-service/
							- Red Hat OpenShift
								- 1 Backlink
									- See [Red Hat OpenShift](https://workflowy.com/#/28fb14b95a44)
							- Tectonic
							  https://coreos.com/tectonic/
							- Many more
							  https://kubernetes.io/docs/setup/pick-right-solution/
						- _Gaming-oriented_
							- Google Agones
								- https://github.com/GoogleCloudPlatform/agones
								- https://cloud.google.com/blog/products/gcp/introducing-agones-open-source-multiplayer-dedicated-game-server-hosting-built-on-kubernetes
								- Used by
									- Pokemon GO
									- Backend for SpatialOS?
								- It provides short-lived workers for dedicated game servers (e.g. a few dozen created for every new Overwatch match)
								  https://cloud.google.com/blog/products/gcp/introducing-agones-open-source-multiplayer-dedicated-game-server-hosting-built-on-kubernetes
								- There is nothing super exciting here, it's just running a game server on Kubernetes which probably a lot of companies already do. The interesting part is the scheduling / healthcheck ( done by integrating the SDK into your engine )
							- Amazon GameLift
								- https://aws.amazon.com/gamelift/
					- OpsFarm (hosted Rancher)
					  http://opsfarm.com/
					- ((64b7eede-2e9c-445d-b566-71db85dfa49c))
					  id:: 6463499e-c32b-4232-aa24-b4a0cef99f84
					- Mesosphere Enterprise DC/OS
					- _Related: _
						- See FOSS and other Container Orchestration tools
						  #Infrastructure-Containers [https://workflowy.com/#/8a01766881ce](https://workflowy.com/#/8a01766881ce)
						- [[Docker]]
				- Database-as-a-service (DBaaS)
				  collapsed:: true
				  id:: 635036c9-37a1-4e61-80bb-8eb1e04980c7
					- Amazon Relational Database Service (RDS)
					- AWS ElastiCache
					  intralink2:: https://workflowy.com/#/08feabea5218
					- http://www.scaledb.com/products-2.php
					- https://cloud.oracle.com/en_US/mysql
					- https://www.compose.com/mysql
					- https://azure.microsoft.com/en-gb/blog/azure-sql-database-point-in-time-restore/
					- Scalr for EC2 DB servers?
						- We chose to use EC2 MySQL instances because we have a high read volume and need master-slave replication. Of course, you can spin up multiple RDS instances and setup MySQL replication between them yourself, but we use Scalr.net, which manages that for you using EC2 instances.
						- Basically, we just tell Scalr how many MySQL instances we want at it keeps them up, automates the setup of replication, handles automatic failover of slave promotion to master if the master gets terminated etc. It does both SQL dump backups and EBS volume snapshots of the master. So, when it needs to create a new slave, it automatically temporarily mounts an EBS volume of the last master snapshot to initialize the slave DB, then starts replication from the appropriate point. All point and click 🙂 (and no, I don't work for Scalr or anything. Scalr is available as Open Source if you don't want to use their service)
					- \_Related: \_Database Management
					  intralink2:: https://workflowy.com/#/bbb23c2e267c
			- _Biggest providers_
				- [[AWS]]
				- [GCP](https://cloud.google.com/)
				  id:: 663a5790-13e8-4491-8f8c-a314785db64b
				  collapsed:: true
				  AKA Google Cloud Platform
					- Pros/Cons
					  collapsed:: true
						- Pros
							-
						- Cons
							- [Bad service, even Google internal teams don't use it](https://youtu.be/cj5NF1rnhV4)
						- Unclear
						- Comparisons
					- Services
						- [Google Cloud Run](https://cloud.google.com/run)
						  id:: 653bb0cc-77e8-4ad0-b2b1-6d5d2ee052fa
						  Very cheap for stateless containerised or serverless loads
					- Certifications
					  collapsed:: true
						- Learning Pathways
						- Free courses
						- Paid courses
						- [Google Cloud Infrastructure for AWS professionals](https://www.cloudskillsboost.google/paths/71)
						  id:: 65f082bf-4d5a-496d-9207-bedb8c216047
						- [Cloud Architect Accelerated Learning Path for AWS professionals](https://www.cloudskillsboost.google/paths/125)
						  preparing them for the Professional Google Cloud Architect Certification
				- [Azure](http://azure.microsoft.com/)
				  id:: 663a5790-2e2f-4272-b816-924917da0a49
				  collapsed:: true
				  AKA Microsoft Azure
					- Pros/Cons
						- Pros
							-
						- Cons
							- https://azsh.it/
								- [400 reasons to not use Microsoft Azure | Hacker News](https://news.ycombinator.com/item?id=43210536)
								-
				- Oracle Cloud Platform
				- [Vultr](https://www.vultr.com/)
				  collapsed:: true
					- Pros/Cons
						- Pros
							-
						- Cons
							- New Dec 2023 [Terms and Conditions allow them to a perpetual license to use all your content](https://www.vultr.com/legal/tos/) and you can't login to your account without accepting the T&C
							  collapsed:: true
								- You hereby grant to Vultr a non-exclusive, perpetual, irrevocable, royalty-free, fully paid-up, worldwide license (including the right to sublicense through multiple tiers) to use, reproduce, process, adapt, publicly perform, publicly display, modify, prepare derivative works, publish, transmit and distribute each of your User Content, or any portion thereof, in any form, medium or distribution method now known or hereafter existing, known or developed, and otherwise use and commercialize the User Content in any way that Vultr deems appropriate, without any further consent, notice and/or compensation to you or to any third parties, for purposes of providing the Services to you.
								- Links
									- [old.reddit.com/r/selfhosted/comments/1bouuv7/warning_vultr_a_major_cloud_provider_is_now](https://old.reddit.com/r/selfhosted/comments/1bouuv7/warning_vultr_a_major_cloud_provider_is_now/)
									- [youtube.com/watch?v=AddtrV6UFFs&t=0s](https://www.youtube.com/watch?v=AddtrV6UFFs&t=0s)
									- 👉 [techcrunch.com/2024/03/05/roku-disables-tvs-and-streaming-devices-until-users-consent-to-forced-arbitration](https://techcrunch.com/2024/03/05/roku-disables-tvs-and-streaming-devices-until-users-consent-to-forced-arbitration/)
									- 👉 [techzine.eu/blogs/infrastructure/118134/vultr-merges-ai-ml-cloud-native-and-inferencing-genai-for-all](https://www.techzine.eu/blogs/infrastructure/118134/vultr-merges-ai-ml-cloud-native-and-inferencing-genai-for-all/)
						- Unclear
						- Comparisons
				- [DigitalOcean](https://www.digitalocean.com)
				  id:: 67376781-c0ff-4eb0-8a85-b6769861711d
					- When creating a droplet
						- Default username for SSH: `root`
			- _Open-source_
				- [Cloud Foundry](https://cloudfoundry.org/)
				- Red Hat OpenStack
				- [Ubicloud](https://www.ubicloud.com/)
				  collapsed:: true
					- https://github.com/ubicloud/ubicloud
					- Services
						- Elastic compute
						- Block storage
						- Virtual networking
						- Managed ((63bae0ae-2db2-4cf2-b923-755efe250d86))
						- ((65bd59ed-6cb1-4ad9-aba7-97d280d1a512)) runners
						  id:: 65bd5b76-07e5-4bbc-9b4f-6b0651a16e89
						  collapsed:: true
							- [Open-source x64 and ARM GitHub runners](https://news.ycombinator.com/item?id=39191870)
								- Our first use-case is GitHub Actions. We support x64 and arm64 Linux
								  runners; and reduce your Github Actions bill by 10x. We can give you
								  hardware similar to default GitHub runners because of the very high
								  margins on the cloud. One difference with our hardware is that we use
								  local NVMes for better disk performance.
								- Ubicloud and our GitHub Actions integration is also open source. You can check out our integration here: [https://github.com/ubicloud/ubicloud/blob/main/routes/web/we...](https://github.com/ubicloud/ubicloud/blob/main/routes/web/webhook/github.rb)
								- For
								  security and isolation, we give you a clean and ephemeral VM for each
								  job. When the job completes, we deprovision the VM and wipe out the
								  block storage device attached to the VM. We set up your firewall rules
								  to lock down access to the VM; and also encrypt your data at rest and
								  in-transit.
								- (We use Linux KVM and the Cloud Hypervisor as our underlying VM tech. For our block device, we use and extend SPDK: [https://www.ubicloud.com/blog/building-block-storage-for-clo...](https://www.ubicloud.com/blog/building-block-storage-for-cloud-with-spdk-non-replicated))
								- Ubicloud
								  runners are also fully compatible with GitHub runners. To get started,
								  all you need to do is change 1-line in your workflow file. Each account
								  gets 1,250 free build minutes per month with standard-2 runners.
								- We’d love to hear your feedback!
								- [https://www.ubicloud.com/docs/github-actions-integration/qui...](https://www.ubicloud.com/docs/github-actions-integration/quickstart)
		- Self-hosted infrastructure-as-a-service (IaaS)
			- OpenStack
			  collapsed:: true
				- https://en.wikipedia.org/wiki/OpenStack
				- Components
					- Compute (Nova)
					- Networking (Neutron)
					- Block storage (Cinder)
					- Identity (Keystone)
					- Image (Glance)
					- Object storage (Swift)
					- Dashboard (Horizon)
					- Orchestration (Heat)
					- Workfow (Mistral)
					- Telemetry (Ceilometer)
					- Database (Trove)
					- Elastic map reduce (Sahara)
					- dare metal (Ironic)
					- Messaging (Zaqar) 3.16
					- Shared file system (Manila)
					- DNS (Designate)
					- Search (Searchlight)
					- Key manager (Barbican)
		- _Platform-as-a-Service (PaaS)_
		  id:: 635036c9-3db9-42e3-916f-f648a36c35ad
			- _Popular web apps management platforms_
				- _Comparison_
				  collapsed:: true
					- https://cozy.io/en/comparison/
					- Cloudron v Sandstorm
					  collapsed:: true
						- Cloudron seems to sit somewhere in the middle. You get Docker-based app containers, and can run apps written in various languages with centralized login. Though Cloudron can't do nearly as much to protect you from vulnerabilities in apps, and Sandstorm has a much better plan for connecting your apps together, rather than just having a collection of silo'd web app interfaces.
						- From a developer point of view Cloudron try to keep changes required for existing apps to be ported to a minimum. To achieve this, we use docker as well as an heroku inspired deployment approach. Sandstorm have their own containerization.
						- Sandstorm and us are trying to solve very similar issues, but the approach and architecture is different.
					- cozy.io and cloudstead.io are focusing on specific services around personal information, like owncloud. Our architecture allows installing arbitrary apps like owncloud as an app. Cozy.io and cloudstead.io would not have gogs or gitlab as apps.
				- _Web app deployment_
				  collapsed:: true
					- _Open-source_
						- Nextcloud
						- Yunohost
						  https://yunohost.org/#/apps
						- Cozy
						  https://cozy.io/en/apps/
						- Sandstorm
						  collapsed:: true
						  https://apps.sandstorm.io/
							- Pros
								- Easy to migrate to a new host running Sandstorm
									- user data is very clearly divided into grains (app instances / documents) with clear owners, and these grains can easily be transferred between servers. Today, you can click "download backup" to get a zip, then upload it to some other server, and end up with exactly the same grain reproduced there. We plan to streamline this further, to allow mass transfers and synchronizing grains between servers. It's a major goal for us that it should be trivial to move between hosts, so that you're never stuck with a host that you don't like.
									- Making a whole server backup/migration
									  https://docs.sandstorm.io/en/latest/administering/backups/
							- Top Apps
						- Bitnami
						  https://alternativeto.net/software/bitnami-application-stacks/
					- AWS Marketplace
					  https://aws.amazon.com/marketplace
					- Softaculous
					  https://www.softaculous.com/software/
					- cloudstead.io
					- _Related: see Heroku etc _
				- Enterprise suite
				  collapsed:: true
					- Nextcloud
					- WikiSuite
					  collapsed:: true
					  http://wikisuite.org/Software
						- TikiSuite (integrated into WikiSuite)
						  https://suite.tiki.org/Tiki+Suite+FAQ
							- ClearOS (integrated into TikiSuite but had it's own marketplace)
							  https://suite.tiki.org/ClearOS
						- http://wikisuite.org/Roadmap
					- arkOS (alpha)
					  collapsed:: true
					  https://arkos.io/
						- Hosted service at Skylark
						  https://skylark.cloud/
					- https://prism-break.org/en/subcategories/servers-enterprise-suite
				- Encapsulated Packages
				  id:: 6312a079-ed4b-4377-ba3a-4edce7119230
				  collapsed:: true
					- Meta
						- DEBs
							- [Alien](https://sourceforge.net/projects/alien-pkg-convert/)
								- is a computer program that converts different Linux package distribution file formats to Debian. It supports conversion between Linux Standard Base, RPM, deb, Stampede (.slp) and Slackware (tgz) packages.
						- RPMs
					- Pros/Cons vs traditional packages (DEB/RPM)
					  id:: 663a5790-1384-4fe1-8d26-7f5facd72520
					  collapsed:: true
						- Pros
							- Solves the problem of distro-agnostic packaging
							- Security benefits of sandboxing packages (especially if using Flatseal)
							  collapsed:: true
								- (for example, using program namespaces and cgroups like Docker seems to do).
							- Not using shared libraries allows avoiding dependency hell, especially important for proprietary apps
							  collapsed:: true
								- I've always felt that one of the biggest issues with Linux from a user's standpoint is dependency hell. Current package managers don't often do a great job of dealing with multiple different versions of the same program, and in the worst case a dependency conflict can break something else (possibly important) on your system.
								- Old proprietary apps sometimes require an old obscure library, which means that modern updated distros won't be able to run the app. Bundled libraries with encapsulated apps make it possible
							- Not using shared libraries means app developer can use old libraries if it's needed to maintain app compatibility, especially important for proprietary software
							- Not reliant on distro package maintainers for timely updates, supporting all packages etc
							- Compared to
						- Cons
							- Many Flatpaks have the permissions `filesystem=host` or `filesystem=home`, which means it's not sandboxed. Needs Flatseal to edit this
							- Small memory and storage benefits by having many shared libraries used by system
							- Shared libraries rather than bundled libraries mean that security fixes are updated faster. Flatpaks can contain exploitable libraries until the app itself is updated
							  collapsed:: true
								- The flatpak runtimes and apps do not get security updates
								- 2020 review
									- A perfect example is [CVE-2019-17498](https://www.cvedetails.com/cve/CVE-2019-17498) with public exploit <a href="https://github.com/github/securitylab/tree/main/SecurityExploits/libssh2/out_of_bounds_read_disconnect_CVE-2019-17498">available</a> for some 8 months. The first app on Flathub I find to use libssh2 library is Gitg and, indeed, it does ship with unpatched libssh2.
									- But is it just this one application? Let's look at the **official runtimes** at the heart of Flatpak (org.freedesktop.Platform and org.gnome.Platform <b>3.36 </b>- as of time of writing used by most of the applications on Flathub).
									- The first unpatched vulnerable dependency I found in the offical runtime is ffmpeg in version 4.2.1 with no security patches backported, [CVE-2020-12284](https://www.cvedetails.com/cve/CVE-2020-12284).
								- Shared libraries means the developer is responsible for keeping the app libraries up-to-date
								- Security benefit of shared libraries (patch one dependency to the benefit of multiple programs)
						- {Archive}
							- [https://flatkill.org/2020/](https://flatkill.org/2020/)
					- Comparison against containers
					  collapsed:: true
						- _Both_
							- Allow easy running on multiple distributions and distro versions
						- _Containers_
							- A container aims to offer isolation on any system which implements its runc/containerd protocol, and will be soon on Windows as well as Linux.
						- _Encapsulated packages_
							- They're not containers, although you can make them containers if you want sandboxing etc
							- We are explicitly using many features of the linux kernel (bind mounts, namespaces, seccomp, etc) to create the sandbox that Flatpak apps are running in. It may be possible to use equivalent technologies on other kernels, but that would be a non-trivial amount of work, and we don't consider this one of our priorities.
					- Docker vs Flatpak
					  collapsed:: true
						- Docker pros
							- Web apps mean URLs - thus I can easily link to web app pages from my outliner, I can have multiple tabs of web app
							- Lighter weight than Flatpak often - since Flatpaks are commonly ((62adbaaa-dd49-44ea-90f4-b41951662bcb)), or just generally heavier than a web app
							- Better enforced sandbox than Flatpak
						- Flatpak pros
							- Easy to backup - Flatpak user data is in `/home/boss/.var/app/` whereas app data is in `/var/lib/flatpak/`
								- Docker data on the other hand
									- is stored in a protected folder so needs to be periodically cron dumped by root,
									- and user data in volumes should be in bind mounts for easier access if not periodically dumping from volumes
									- See [Where is Docker data stored](https://workflowy.com/#/8aca70b2ce5e)
									  #Infrastructure-Containers
							- Deduplication of binaries - if you have 12 apps using the same runtime, won't download the runtime 12 times
								- Flatpak (rather, its OStree component) looks for the dependency resources for a program on the filesystem after the bundle is installed: if they are already present, the copy is removed so that a single copy is used by all the programs that require it; if it is not already present the bundled one is used. Until there is one program that depends on a file, that file is not removed; I'm not sure what the default behaviour on orphaned dependencies is but I guess it can be changed or avoided by managing things fully manually.
						- See [Docker](https://workflowy.com/#/6983127b69f3)
						  #Infrastructure-Containers
						- 2 Backlinks
							- See [Docker vs Flatpak](https://workflowy.com/#/e757ceafb96d)
							- Snap/Flatpak package (then again I prefer Docker now - see [Docker vs Flatpak](https://workflowy.com/#/e757ceafb96d))
							  [https://github.com/mattermost/focalboard/issues/79#issuecomment-801895273](https://github.com/mattermost/focalboard/issues/79#issuecomment-801895273)
					- _Types_
						- ((6313455f-8855-4849-8ac2-8012e198774c))
						  #PC-Linux
						- Portable binaries
						  collapsed:: true
							- AppImage
							  http://appimage.org/
							- Holy-build-box
								- Pros/Cons
									- Pros
										- For C programs it's similar to AppImage
								- [https://github.com/phusion/holy-build-box](https://github.com/phusion/holy-build-box)
							- Go compiler
					- _Related: _[Container runtimes](https://workflowy.com/#/a7e42aa8bdcd)
					  #Infrastructure-Containers
			- _Container-based PaaS_
			  id:: 6463499d-ddc1-4971-a467-a223d3f73579
			  collapsed:: true
				- _Open-source_
					- Porter (Kubernetes-based, Heroku-like)
					  collapsed:: true
						- [https://news.ycombinator.com/item?id=26993421](https://news.ycombinator.com/item?id=26993421)
							- Intro
							  collapsed:: true
								- Hi HN! We are Alexander, Justin, and Trevor from Porter. We're building a Kubernetes-based Platform as a Service (PaaS) that deploys applications on your own cloud provider. Specifically, Porter provisions a Kubernetes cluster in your own cloud account and lets you deploy and manage applications on it through a Heroku-like PaaS layer. And although applications deployed via Porter run on Kubernetes, no knowledge of Kubernetes is necessary to use Porter. Here is our repository ([https://github.com/porter-dev/porter](https://github.com/porter-dev/porter)) and website (<a href="https://getporter.dev">https://getporter.dev</a>). There was also an HN thread about us a few weeks ago, posted by someone who discovered us (<a href="https://news.ycombinator.com/item?id=26587637">https://news.ycombinator.com/item?id=26587637</a> - thank you OP!).
								- We have known each other since high school/college and have been working on projects together full-time since 2020. When YC funded us in S20, we were building a remote development platform for teams on Kubernetes (kinda like repl.it but for microservices in particular). This was a more enterprisey product and we got burnt out by the slow sales/iteration cycle (we had zero experience with sales, let alone enterprises). So we decided to pivot a few months after demo day.
								- When we were struggling to get traction with the original direction, we learned a ton by talking to engineering teams that are using Kubernetes (k8s). One thing we noticed is that there's an increasing number of startups who start on a PaaS like Heroku and end up migrating to k8s later as their applications “grow out” of Heroku, due to constraints in networking, performance, security, etc.
								- While Kubernetes is great, it incurs a ton of engineering overhead. For teams who don’t know k8s at all, learning everything from scratch is daunting and time-consuming. Even if there are devops engineers on the team who are familiar with kubernetes, adopting k8s slows down developer velocity because other developers always need the devops engineers’ help to troubleshoot the slightest application issues. While we were working on our previous product, we discovered that some companies even built internal development platforms (IdP) that are much like Porter, in order to help developers deploy and troubleshoot their applications without help from the devops engineers. Our goal with Porter is to create a platform that is truly as easy to use as Heroku, without compromising the flexibility of k8s.
								- There are many self-hosted PaaS's that came before Porter, such as Flynn, Tsuru, Dokku, and CapRover, which were all created before Kubernetes changed the DevOps landscape. While these are great lightweight options for smaller projects, a PaaS built on top of the k8s ecosystem comes with many benefits such as scalability, stability, configurability and interoperability across cloud providers. We believe that k8s is the best system to deliver a PaaS on, and we’re not alone - many of the new hosted PaaS’s are also built on top of k8s, although that’s an implementation detail that is usually not advertised to the user. We want to not only deliver the PaaS experience on top of Kubernetes, but also give users full ownership/control of the underlying k8s cluster by running it in their own cloud.
								- How it works: we spin up a k8s cluster in your own AWS/GCP/DO account and let you deploy and manage applications on it through a Heroku-like abstraction layer. For teams using a PaaS like Heroku, Porter can be a drop-in replacement that you don’t “grow out” of. And although our abstraction layer covers most use cases, we let those who want to customize go freely under the hood to interact with the underlying cluster. In each cloud provider, we provision the standard managed k8s offering (e.g. EKS/GKE/DigitalOcean Kubernetes), so the clusters we provision are perfectly compatible with kubectl and any other k8s tooling out there. It’s even possible to connect Porter to an existing k8s cluster—this isn’t the primary use case we’re building for at the moment, but we’d love to discuss it in the comments if anyone is interested.
								- In terms of implementation, we’ve built Porter around the Helm ecosystem, and every application you deploy is packaged as a Helm chart. For those who want more visibility, we’ve built features like “devops mode” that lets you visualize and manage the Helm charts and its underlying k8s objects.
								- We’ve published Porter to be fully open source under the MIT license. We provide a hosted version that is currently in open beta, but it's also possible to run Porter locally. It’s worth clarifying that on the hosted version, the applications you deploy through Porter still run in your own cloud. What is hosted by us is only the PaaS layer, not your applications. We plan to release a self-hostable version of the PaaS layer itself in the near future, packaged as a Helm chart. We do not support this yet because self-hosting the PaaS layer inevitably incurs devops overhead and requires some knowledge of k8s, and we are currently focused on those who just want the Heroku experience without having to deal with k8s in any way.
								- In terms of pricing, we are still figuring out the specifics. Our goal is to not charge individual developers/small startups but instead draw revenue from larger teams based on usage, and with premium features that are geared towards collaboration. Existing PaaS’s like Heroku/Netlify have solid examples of such premium features - review apps, pipelines, and Role Based Access Control are a few examples that we also consider to be potential premium features on Porter. That said, we are currently focused on laying out the stable foundation of the platform, so these premium features are further down on our roadmap.
								- Thank you so much for reading and we'd love it if you could give it a try: [https://github.com/porter-dev/porter](https://github.com/porter-dev/porter). We'll be hanging out in the comments to hear any ideas and feedback you may have. If you have any experiences related to what we’ve built, we would love it if you could share them below. Very much looking forward to learning from you!
						- [https://github.com/porter-dev/porter](https://github.com/porter-dev/porter)
					- Portainer (supports Docker and Kubernetes)
					  collapsed:: true
						- [https://github.com/portainer/portainer](https://github.com/portainer/portainer)
					- Rancher
					- [Kubernetes](https://kubernetes.io/)
					  id:: 663a5790-fa61-4dc7-ac70-4471a6f30628
					  collapsed:: true
						- Ecosystem
							- ((6633312b-0785-4e6b-a86d-edbc49b69b5e))
							- [Helm](https://helm.sh/) - package manager
							- [Home | Argo](https://argoproj.github.io/)
								- Open source tools for Kubernetes to run workflows, manage clusters, and do GitOps right.
								- [GitHub - argoproj/argo-cd: Declarative Continuous Deployment for Kubernetes](https://github.com/argoproj/argo-cd)
								- [GitHub - argoproj/argo-workflows: Workflow Engine for Kubernetes](https://github.com/argoproj/argo-workflows)
								-
					- CapRover
					  collapsed:: true
						- [https://caprover.com/](https://caprover.com/)
					- Dokku (Docker-based self-hosted Heroku)
					  id:: 6463499d-ad5b-416b-b21b-7e9d6b700f6b
					  collapsed:: true
					  [Application Error](http://dokku.viewdocs.io/dokku/)
						- A docker-powered PaaS that helps you build and manage the lifecycle of applications
						  https://github.com/dokku/dokku
						- Powered by Docker, you can install Dokku on any hardware.
						-
						- Once it's set up on a host, you can push Heroku-compatible applications to it via Git. They'll build using Heroku buildpacks and then run in isolated containers. The end result is your own, single-host version of Heroku.
					- [GitHub - Dokploy/dokploy: Open Source Alternative to Vercel, Netlify and Heroku.](https://github.com/Dokploy/dokploy)
						- It's similar to Dokku but has a nice web UI, makes it easier to deploy Docker/Compose solutions and auto LetsEncrypt functionality is built-in by design (not as a separate plugin).
				- [Cloudron](https://cloudron.io/)
				  collapsed:: true
					- Pros/Cons
						- Unclear
							- They are the package maintainers
								- e.g. https://cloudron.io/blog/2018-11-21-cloudron-3.3.html
					- Top Apps
						- Nextcloud
						- Mattermost
						- Radicale
						  Contacts and calendar
					- Pricing
						- There is no hosted option - there are simply different subscription packages for self-hosted
						- Free plan limitations - max 2 apps, no SSH support, no premium apps
					- Documentation
						- **Editing Cloudron free to support more than 2 apps**
						  collapsed:: true
							- 26/5/18 - Only allow max of 2 apps on the free plan (src/appstore.js line 132)
							  https://git.cloudron.io/cloudron/box/commit/29682c094425f2b1e6f478c89f307a7d01caded4
							- Other possible
								- src/updatechecker.js
								- https://git.cloudron.io/cloudron/box/commit/9eb58cdfe5aab1a8e3ed2dc1208f4f82e49a14dc
								- https://git.cloudron.io/cloudron/box/commit/eeaaa95ca3ee1ea002442ccf5f9ba2c893bd1ec8
								- /api/v1/users/${APPSTORE_USER_ID}/cloudrons/${CLOUDRON_ID}/subscription?accessToken=${APPSTORE_TOKEN}
								- https://git.cloudron.io/cloudron/box/commit/371f81b980ac02b062c1c8d802e32870ac42cd54
								- https://git.cloudron.io/cloudron/box/commit/682f7a710ccccc14b0508109a66458c888b91b74
							- count > 2
						- Installation
						  collapsed:: true
							- See
								- https://cloudron.io/references/selfhosting.html
								- sudo ./cloudron-setup --provider ec2
						- 3rd party Dockerfiles can be used too
						  https://cloudron.io/developer/packaging/
						- Setting up WordPress site
						  #CreateAWebsite https://workflowy.com/#/fbb05bf85b3f
				- Convox
				  collapsed:: true
					- [https://convox.com/](https://convox.com/)
				- Render (Heroku-like)
				- Cloud 66's Maestro
				- _Enterprise deployment_
				  collapsed:: true
					- Cloudify
					  collapsed:: true
						- [http://getcloudify.org](http://getcloudify.org)
					- [OpenShift](https://www.openshift.com)
					  collapsed:: true
						- See [OpenShift](https://workflowy.com/#/5c3ddb175b09)
						- See [Red Hat OpenShift](https://workflowy.com/#/28fb14b95a44)
				- _Docker images_
				  collapsed:: true
					- Nextcloud
						- [https://github.com/nextcloud/docker](https://github.com/nextcloud/docker)
					- Bitwarden_rs, Confluence, Discourse, Element and Matrix, Jellyfin, Mastodon, Mattermost, Rocket.chat, SOGo,Taiga and even Minecraft! And it all works!
					- See [Docker](https://workflowy.com/#/6983127b69f3)
					  #Infrastructure-Containers
				- Related: ((6463499c-d91d-42c9-b035-93b6bc153e41))
			- Sorted by license
				- ## Proprietary
					- Database-only
						- _with free tiers_
							- [Railway](https://railway.app/new)
							- [ElephantSQL](https://elephantsql.com)
							  collapsed:: true
								- Documentation
									- Details tab > URL (keep this private)
									- Teacjers
										- ![image.png](../assets/image_1666777572841_0.png){:height 55, :width 878}
									- Browser tab can be used for executing queries
									-
					- Allows backends
						- [Render](https://render.com/)
						  id:: 638f15bf-3107-4b98-bbcd-207daba07378
						  collapsed:: true
							- For backend: `new Web Service` e.g. Express/Node
							- Settings
							  id:: 638f5b76-a402-4196-9a00-fc197fb7c6d2
								- Build command: `npm i`
								- Start command: `npm start`
								- Environment variables:
									- `DATABASE_URL` = `https://whatever.elephantsql.com/app`
							- Related: ((638efd3a-70fe-4f2f-ac89-8fcdbc7cdf44))
					- [Firebase](https://firebase.google.com/)
					  id:: 638d061d-953c-4c18-aa02-ef4b64a6b88f
					  collapsed:: true
						- *Products*Cloud
							- [Cloud Firestore](https://firebase.google.com/products/firestore) (NoSQL)
							- [Firebase Realtime Database](https://firebase.google.com/products/realtime-database)
							- [Firebase Authentication](https://firebase.google.com/products/auth)
							  id:: 638e231d-32a2-47d2-836e-6563a046202b
							  collapsed:: true
								- [Working personal repo](https://github.com/SchoolOfCode/bc13_w11d5_hackathon-front-end-aaron-and-mike/commits/main) (work done by Mike Chara)
								- Working guide - [How to build a chatroom app with React and Firebase - LogRocket Blog](https://blog.logrocket.com/how-to-build-chatroom-app-react-firebase/) - confirmed [[Dec 6th, 2022]]
								  id:: 638fad24-757c-4577-9d8c-a37dcb31377d
									- /home/boss/Documents/Git/1MY REPOS/firebase-auth-test
									- Docs
										- [Get Started with Firebase Authentication on Websites](https://firebase.google.com/docs/auth/web/start)
										- [Authenticate with Firebase Anonymously Using JavaScript](https://firebase.google.com/docs/auth/web/anonymous-auth)
										- [Authenticate with Firebase Using Email Link in JavaScript](https://firebase.google.com/docs/auth/web/email-link-auth)
										-
								- How to to setup
									- Video tutorial - old (2020)
									  id:: 638f5812-7e9a-4d6e-84c9-3d925fdf994e
									  collapsed:: true
										- {{video https://youtu.be/zQyrwxMPm88}}
											- d
									- Docs
										- [Where do I start with Firebase Authentication?](https://firebase.google.com/docs/auth/where-to-start)
										- [Easily add sign-in to your Web app with FirebaseUI](https://firebase.google.com/docs/auth/web/firebaseui)
										- [Add Firebase to your JavaScript project](https://firebase.google.com/docs/web/setup)
										- [Where do I start with Firebase Authentication?](https://firebase.google.com/docs/auth/where-to-start?authuser=0)
									- [Error 403 (Forbidden)!!1](https://console.firebase.google.com/project/website1-6fb11/overview)
									- `npm install firebaseui --save`
									- [Getting started with Firebase for the web – Firebase Fundamentals - YouTube](https://youtu.be/rQvOAnNvcNQ)
									  collapsed:: true
										- `npm init -y`
										- `npm i firebase`
										- `/src/index.js`
											- ```javascript
											  import { initalizeApp } from "firebase/app";
											  import {
											    getAuth,
											    onAuthStateChanged,
											  } from "firebase/auth";
											  import { getFirestore } from "firebase/firestore";
											  
											  const firebaseApp = initializeApp({});
											  const auth = getAuth(firebaseApp);
											  const db = getFirestore(firebaseApp);
											  
											  // Detect auth state
											  ```
											- ![image.png](../assets/image_1670257700349_0.png)
											-
							- [Firebase Cloud Messaging | Send notifications across platforms at no-cost](https://firebase.google.com/products/cloud-messaging)
							- [Firebase Hosting](https://firebase.google.com/products/hosting)
							  id:: 63dfca2f-c9f7-4de4-ac1c-d1ad33df01e4
							- [Cloud Storage for Firebase | Store and serve content with ease](https://firebase.google.com/products/storage)
					- ((63904f39-6a5a-49aa-b6c5-f9811359b487))
					- [Heroku](https://www.heroku.com/)
					  id:: 635036c9-3af8-4aa4-9e6c-c771acd65b01
					  collapsed:: true
						- https://devcenter.heroku.com/articles/local-development-with-docker-compose
						- https://devcenter.heroku.com/articles/container-registry-and-runtime
					- [Netlify](https://app.netlify.com)
					  id:: 638d061d-6a10-4b9b-a0ef-377ef8ad1618
					  collapsed:: true
						- How to use with create-react-app
							- Make sure to use `npx create-react-app `
							- [Create React App on Netlify | Netlify Docs](https://docs.netlify.com/integrations/frameworks/create-react-app/#app)
							- [Framework integrations | Netlify Docs](https://docs.netlify.com/configure-builds/common-configurations/#create-react-app)
							- Settings
							  id:: 638f28fe-9916-486a-b340-4dd2e4425025
								- Base directory: ``
								- Build command: `react-scripts build`
								- Publish directory: `build`
								- ..
								- Environment variables:
									- `REACT_APP_BACKEND_URL`= `https://whatever.render.com/app`
						- Related: ((638efd3a-70fe-4f2f-ac89-8fcdbc7cdf44))
					- Vercel
					- ((67376781-c0ff-4eb0-8a85-b6769861711d)) Apps
					- Digger
					  collapsed:: true
						- [https://diggerdev.com](https://diggerdev.com)
						- Pros/Cons
							- Pros
								- Simpler than manually provisioning on AWS
								- Simpler than manually creating Terraform
								- Portable to other clouds unlike PaaS like Heroku
						- What
							- ((638d061d-e696-4f04-933c-35f8836e125d))-based PaaS that generates ((638d061d-e696-4f04-933c-35f8836e125d))for AWS in a simple way
						- 1 Backlink
							- See [Digger](https://workflowy.com/#/e26075958ee2) (Terraform-based PaaS)
					- Google AppEngine
					- ((6396fb64-9aeb-4ee3-bf46-849eac2fb748)) : ((6396fb64-f1fa-498a-ac4f-242eed1e3dff))
					- _Hosting-only_
						- Static site only
						  AKA static hosting
							- [GitHub Pages](https://pages.github.com/)
							  id:: 6360df10-883d-42a0-9a73-074c5aa2be13
							  collapsed:: true
							- CloudFlare Pages
							  collapsed:: true
								- [https://blog.cloudflare.com/cloudflare-pages/](https://blog.cloudflare.com/cloudflare-pages/)
						- ((63dfca2f-c9f7-4de4-ac1c-d1ad33df01e4))
					- _managed hosting_
					  collapsed:: true
						- Rackspace
						- fortrabbit.com/
						- Managed PHP and WordPress
							- CloudWays
							  https://www.cloudways.com/en/
							- RunCloud.io
							- ServerPilot
							  https://serverpilot.io/
						- Managed WordPress hosting
							- WPEngine
							  https://wpengine.com
							- _Budget_
							  collapsed:: true
								- http://www.45air.com
								- https://www.siteground.com/
								- https://getflywheel.com/pricing/
								- https://wpoven.com/
				- ## Open-source
				  collapsed:: true
					- [Supabase](https://supabase.io)
					  id:: 63a9bb63-857e-4380-9c0c-6b0c6d60f364
					  collapsed:: true
						- Pros
							- Worked well for my final month School of Code project - auth + database
						- Documentation
							- Features
								- Database - ((63bae0ae-2db2-4cf2-b923-755efe250d86))
								- [Supabase Auth](https://github.com/supabase/auth)
								  id:: 6463499d-8136-428d-82e9-ef2fed5174d5
								  collapsed:: true
									- [Auth | Supabase Docs](https://supabase.com/docs/guides/auth)
									- [GitHub - supabase/auth-js: An isomorphic Javascript library for Supabase Auth.](https://github.com/supabase/auth-js)
									-
									- Authentication
									- Supabase auth is pretty simple -- it stores data in the auth.users table. You can access that in prisma (you may need to create a view that gives you access this table depending on your security setup.). Also you can create a trigger on the auth.users table that creates a record, say, in a table called public.users so you can add additional user information tied to the user.
								- Supabase Storage - supports S3
							- ((63df86be-87bf-443e-b10b-77795b1b6351))
							- Testing
								- Example from Stefan's project `supabase.test.ts`
								  collapsed:: true
									- ```typescript
									  import {
									    supabaseAnon,
									    supabaseService,
									  } from "../../jest.setup";
									  
									  const businessUser1 = {
									    email: "fawiwe3771@moneyzon.com",
									    password: "password123",
									  };
									  
									  const businessUser1ID =
									    "44437ab8-2ab2-49d6-a71a-fe8f49f39032";
									  
									  const businessUser2 = {
									    email: "bilisaw709@quamox.com",
									    password: "password123",
									  };
									  
									  describe("Supabase Testing for Profiles Table Row Level Security", () => {
									    it("Should not be able to view a profile when not logged in", async () => {
									      const { statusText } = await supabaseAnon
									        .from("profiles")
									        .select()
									        .eq("id", businessUser1ID)
									        .single();
									      expect(statusText).toEqual("Not Acceptable");
									    });
									  
									    it("Should not be able to create a profile when not logged in", async () => {
									      const newProfile = {
									        id: "5bade4e6-5383-4bfb-9df4-29a276f4cecb",
									        user_type: "consumer",
									        full_name: "Test Profile",
									      };
									  
									      const { statusText } = await supabaseAnon
									        .from("profiles")
									        .insert(newProfile)
									        .select()
									        .single();
									      expect(statusText).toEqual("Unauthorized");
									    });
									  
									    it("Should not be able to edit a profile when not logged in", async () => {
									      const { statusText } = await supabaseAnon
									        .from("profiles")
									        .update({
									          full_name: "Updated Test Profile",
									        })
									        .eq("id", businessUser1ID)
									        .single();
									      expect(statusText).toEqual("Not Acceptable");
									    });
									  
									    it("Should not be able to delete a profile when not logged in", async () => {
									      const { statusText } = await supabaseAnon
									        .from("profiles")
									        .delete()
									        .eq("id", businessUser1ID)
									        .single();
									      expect(statusText).toEqual("Not Acceptable");
									    });
									  
									    it("Testing as Business User 1: Should be able to login, and be authenticated.", async () => {
									      const { data } =
									        await supabaseAnon.auth.signInWithPassword(
									          businessUser1
									        );
									      expect(data.session?.user.role).toEqual(
									        "authenticated"
									      );
									    });
									  
									    it("Testing as Business User 1: Should be able to update a profile assigned to their user_id", async () => {
									      const {
									        data: { user },
									      } = await supabaseAnon.auth.getUser();
									      const { data } = await supabaseAnon
									        .from("profiles")
									        .update({
									          full_name: "Test Business User 1 Updated",
									        })
									        .eq("id", user?.id)
									        .select();
									      expect(data![0].full_name).toEqual(
									        "Test Business User 1 Updated"
									      );
									    });
									  
									    it("Testing as Business User 1: Reversion Of Edited Profile Name Change Successful", async () => {
									      const {
									        data: { user },
									      } = await supabaseAnon.auth.getUser();
									      const { data } = await supabaseAnon
									        .from("profiles")
									        .update({
									          full_name: "Test Business User 1",
									        })
									        .eq("id", user?.id)
									        .select();
									      expect(data![0].full_name).toEqual(
									        "Test Business User 1"
									      );
									    });
									  
									    it("Business User 1 Logs Out", async () => {
									      const { error } = await supabaseAnon.auth.signOut();
									      expect(error).toEqual(null);
									    });
									  });
									  
									  describe("Supabase Testing for Businesses Table Row Level Security", () => {
									    it("Should not be able to create a business while not logged in", async () => {
									      const testBusiness = {
									        name: "Test Business",
									        website: "www.example.com",
									        postcode: "SW1P 4QE",
									        lat: 90,
									        lon: 90,
									        address_line1: "123 Example Street",
									      };
									  
									      const { statusText } = await supabaseAnon
									        .from("businesses")
									        .insert(testBusiness)
									        .select()
									        .single();
									      expect(statusText).toEqual("Unauthorized");
									    });
									  
									    it("Testing as Business User 1: Should be able to login, and be authenticated.", async () => {
									      const { data } =
									        await supabaseAnon.auth.signInWithPassword(
									          businessUser1
									        );
									  
									      expect(data.session?.user.role).toEqual(
									        "authenticated"
									      );
									    });
									  
									    it("Testing as Business User 1: Should be able to create a business while logged in", async () => {
									      const {
									        data: { user },
									      } = await supabaseAnon.auth.getUser();
									  
									      const testBusiness = {
									        name: "Test Business",
									        website: "www.example.com",
									        postcode: "SW1P 4QE",
									        lat: 90,
									        lon: 90,
									        address_line1: "123 Example Street",
									        user_id: user?.id,
									      };
									  
									      const businessResponse = await supabaseAnon
									        .from("businesses")
									        .insert(testBusiness)
									        .select()
									        .single();
									      expect(businessResponse.data).toEqual(
									        expect.objectContaining(testBusiness)
									      );
									    });
									  
									    it("Testing as Business User 1: Should be able to update a business assigned to their user_id", async () => {
									      const {
									        data: { user },
									      } = await supabaseAnon.auth.getUser();
									      const { data } = await supabaseAnon
									        .from("businesses")
									        .update({
									          name: "Test Business Updated",
									        })
									        .eq("user_id", user?.id)
									        .select();
									      expect(data![0].name).toEqual("Test Business Updated");
									    });
									  
									    it("Testing as Business User 1: Should be able to delete a business assigned to their user_id", async () => {
									      const {
									        data: { user },
									      } = await supabaseAnon.auth.getUser();
									      const { data } = await supabaseAnon
									        .from("businesses")
									        .delete()
									        .eq("user_id", user?.id)
									        .select();
									      expect(data![0].user_id).toEqual(user?.id);
									    });
									  
									    it("Business User 1 Creates Another Business For Additional Testing From Business User 2", async () => {
									      const {
									        data: { user },
									      } = await supabaseAnon.auth.getUser();
									  
									      const testBusiness = {
									        name: "Test Business",
									        website: "www.example.com",
									        postcode: "SW1P 4QE",
									        lat: 90,
									        lon: 90,
									        address_line1: "123 Example Street",
									        user_id: user?.id,
									      };
									  
									      const businessResponse = await supabaseAnon
									        .from("businesses")
									        .insert(testBusiness)
									        .select()
									        .single();
									      expect(businessResponse.data).toEqual(
									        expect.objectContaining(testBusiness)
									      );
									    });
									  
									    it("Business User 1 Logs Out", async () => {
									      const { error } = await supabaseAnon.auth.signOut();
									      expect(error).toEqual(null);
									    });
									  
									    it("Testing as Business User 2: Should be able to login, and be authenticated.", async () => {
									      const { data } =
									        await supabaseAnon.auth.signInWithPassword(
									          businessUser2
									        );
									      expect(data.session?.user.role).toEqual(
									        "authenticated"
									      );
									    });
									  
									    it("Testing as Business User 2: Should not be able to update a business not assigned to their user_id", async () => {
									      const { error } = await supabaseAnon
									        .from("businesses")
									        .update({
									          name: "Test Business Updated",
									        })
									        .eq("user_id", businessUser1ID)
									        .select();
									  
									      const { data } = await supabaseAnon
									        .from("businesses")
									        .select()
									        .eq("user_id", businessUser1ID);
									      expect(data![0].name).toEqual("Test Business");
									    });
									  
									    it("Testing as Business User 2: Should not be able to delete a business not assigned to their user_id", async () => {
									      const { error } = await supabaseAnon
									        .from("businesses")
									        .delete()
									        .eq("user_id", businessUser1ID)
									        .select();
									  
									      const { data } = await supabaseAnon
									        .from("businesses")
									        .select()
									        .eq("user_id", businessUser1ID);
									      expect(data![0].name).toEqual("Test Business");
									    });
									  
									    it("Test Conclusion: Successful sign out of Business User 2 and Deletion Of Remaining Test Business", async () => {
									      const { error } = await supabaseAnon.auth.signOut();
									      expect(error).toEqual(null);
									  
									      const { data } = await supabaseService
									        .from("businesses")
									        .delete()
									        .eq("user_id", businessUser1ID)
									        .select();
									      expect(data![0].user_id).toEqual(businessUser1ID);
									    });
									  });
									  
									  describe("Supabase Testing for Deals Table Row Level Security", () => {
									    let testBusinessID = "";
									    let testDealID = "";
									  
									    it("Testing as Business User 1: Should be able to login, and be authenticated.", async () => {
									      const { data } =
									        await supabaseAnon.auth.signInWithPassword(
									          businessUser1
									        );
									      expect(data.session?.user.role).toEqual(
									        "authenticated"
									      );
									    });
									  
									    it("Testing as Business User 1: Create A Business For Testing Purposes", async () => {
									      const {
									        data: { user },
									      } = await supabaseAnon.auth.getUser();
									  
									      const testBusiness = {
									        name: "Test Business",
									        website: "www.example.com",
									        postcode: "SW1P 4QE",
									        lat: 90,
									        lon: 90,
									        address_line1: "123 Example Street",
									        user_id: user?.id,
									      };
									  
									      const businessResponse = await supabaseAnon
									        .from("businesses")
									        .insert(testBusiness)
									        .select()
									        .single();
									      testBusinessID = businessResponse.data.id;
									      expect(businessResponse.data).toEqual(
									        expect.objectContaining(testBusiness)
									      );
									    });
									  
									    it("Testing as Business User 1: Should be able to create a deal", async () => {
									      const testDeal = {
									        name: "Test Deal",
									        business_id: testBusinessID,
									        user_id: businessUser1ID,
									      };
									  
									      const { data } = await supabaseAnon
									        .from("deals")
									        .insert(testDeal)
									        .select()
									        .single();
									      testDealID = data.id;
									      expect(data.name).toEqual("Test Deal");
									    });
									  
									    it("Testing as Business User 1: Should be able to edit a deal they created", async () => {
									      const { data } = await supabaseAnon
									        .from("deals")
									        .update({
									          name: "Updated Test Deal",
									        })
									        .eq("id", testDealID)
									        .select()
									        .single();
									      expect(data.name).toEqual("Updated Test Deal");
									    });
									  
									    it("Business User 1 Logs Out", async () => {
									      const { error } = await supabaseAnon.auth.signOut();
									      expect(error).toEqual(null);
									    });
									  
									    //Not Logged In Tests
									    it("Should not be able to create a deal while not logged in", async () => {
									      const testDeal = {
									        name: "Test Deal",
									      };
									  
									      const { statusText } = await supabaseAnon
									        .from("deals")
									        .insert(testDeal)
									        .select()
									        .single();
									      expect(statusText).toEqual("Unauthorized");
									    });
									  
									    it("Should not be able to update a deal while not logged in", async () => {
									      const response = await supabaseAnon
									        .from("deals")
									        .update({
									          name: "Updated Test Deal Again",
									        })
									        .eq("id", testDealID)
									        .select()
									        .single();
									      expect(response.statusText).toEqual("Not Acceptable");
									    });
									  
									    it("Test Conclusion: Deletion Of Remaining Test Business and Deal", async () => {
									      const { error } = await supabaseService
									        .from("deals")
									        .delete()
									        .eq("user_id", businessUser1ID)
									        .select();
									  
									      const { data } = await supabaseService
									        .from("businesses")
									        .delete()
									        .eq("user_id", businessUser1ID)
									        .select();
									      expect(data![0].user_id).toEqual(businessUser1ID);
									    });
									  });
									  ```
					- [Appwrite](https://appwrite.io)
					  id:: 67376781-dfb0-424e-a925-52f0f6595885
					  collapsed:: true
						- [[Page not found · GitHub](https://github.com/appwrite/appwrite](https://github.com/appwrite/appwrite))
						- [Appwrite in 100 Seconds - YouTube](https://youtu.be/L07xPMyL8sY)
							- Handles database, auth, and other backend aspects
							- Provides SDKs for ((6396fb64-f1fa-498a-ac4f-242eed1e3dff)), Flutter, mobile etc
							-
					- [PocketBase](https://pocketbase.io/)
					  id:: 63a2c22f-17f6-466b-b7cf-fd92078ee2b8
					  collapsed:: true
						- Features
						  collapsed:: true
							- 1 binary file for entire backend, perfect for local test projects
							- embedded database ( ((6396fb64-828e-4462-a6b8-3b05ab6bc31a)) ) with realtime subscriptions
							- File storage - local or S3
							- Authentication and user management
							- convenient Admin dashboard UI
							- simple REST-ish API via [GitHub - labstack/echo: High performance, minimalist Go web framework](https://github.com/labstack/echo) - Go web framework
						- Documentation
							- Homepage examples
								- Realtime DB
								  collapsed:: true
									- ```js
									  // JavaScript SDK
									  import PocketBase from 'pocketbase';
									  
									  const pb = new PocketBase('http://127.0.0.1:8090');
									  
									  ...
									  
									  // list and search for 'example' collection records
									  const list = await pb.collection('example').getList(1, 100, {
									      filter: 'title != "" && created > "2022-08-01"',
									      sort: '-created,title',
									  });
									  
									  // or fetch a single 'example' collection record
									  const record = await pb.collection('example').getOne('RECORD_ID');
									  
									  // delete a single 'example' collection record
									  await pb.collection('example').delete('RECORD_ID');
									  
									  // create a new 'example' collection record
									  const newRecord = await pb.collection('example').create({
									      title: 'Lorem ipsum dolor sit amet',
									  });
									  
									  // subscribe to changes in any record from the 'example' collection
									  pb.collection('example').subscribe('*', function (e) {
									      console.log(e.record);
									  });
									  
									  // stop listening for changes in the 'example' collection
									  pb.collection('example').unsubscribe();
									  ```
								- Authentication
								  collapsed:: true
									- ```js
									  // JavaScript SDK
									  import PocketBase from 'pocketbase';
									  
									  const pb = new PocketBase('http://127.0.0.1:8090');
									  
									  ...
									  
									  // sign-up with username/email and password
									  await pb.collection('users').create({
									      email:           'test@example.com',
									      password:        '123456',
									      passwordConfirm: '123456',
									      name:            'John Doe',
									  });
									  
									  // sign-in with username/email and password
									  await pb.collection('users').authWithPassword('test@example.com', '123456');
									  
									  // sign-in/sign-up with OAuth2 (Google, Facebook, etc.)
									  await pb.collection('users').authWithOAuth2(
									      'google',
									      'YOUR_CODE',
									      'YOUR_CODE_VERIFIER',
									      'YOUR_REDIRECT_URL'
									  );
									  
									  // send verification email
									  await pb.collection('users').requestVerification('test@example.com');
									  
									  // send password reset email
									  await pb.collection('users').requestPasswordReset('test@example.com');
									  ```
								- File storage
								  collapsed:: true
									- ```js
									  
									  // JavaScript SDK
									  import PocketBase from 'pocketbase';
									  
									  const pb = new PocketBase('http://127.0.0.1:8090');
									  
									  ...
									  
									  // file input (eg. <input type="file" id="fileInput" />)
									  const fileInput = document.getElementById('fileInput');
									  
									  const formData = new FormData();
									  
									  // listen to file input changes
									  fileInput.addEventListener('change', function () {
									      for (let file of fileInput.files) {
									          formData.append('yourFileField', file);
									      }
									  });
									  
									  // set some other regular text field value
									  formData.append('title', 'Hello world!');
									  
									  ...
									  
									  // create a new record and upload the file(s)
									  await pb.collection('example').create(formData);
									  
									  // delete all 'yourFileField' files from a record
									  await pb.collection('example').update('RECORD_ID', {
									      'yourFileField': null,
									  });
									  ```
								- Extendable
								  collapsed:: true
									- ```go
									  // main.go
									  package main
									  
									  import (
									      "log"
									  
									      "github.com/pocketbase/pocketbase"
									      "github.com/pocketbase/pocketbase/core"
									      "github.com/pocketbase/pocketbase/tools/hook"
									  )
									  
									  func main() {
									      app := pocketbase.New()
									  
									      app.OnRecordAfterUpdateRequest().Add(func(e *core.RecordUpdateEvent) error {
									          log.Println(e.Record.Id)
									          return nil
									      })
									  
									      app.OnMailerBeforeRecordVerificationSend().Add(func(
									          e *core.MailerRecordEvent,
									      ) error {
									          // send custom email
									          if err := e.MailClient.Send(...); err != nil {
									              return err
									          }
									          return hook.StopPropagation
									      })
									  
									      if err := app.Start(); err != nil {
									          log.Fatal(err)
									      }
									  }
									  ```
							- [Official docs](https://pocketbase.io/docs/)
							  collapsed:: true
								- Intro
									- Put binary in parent directory of your git repo
									- `./pocketbase serve`
									- A web server will be started with the following routes:
										- http://127.0.0.1:8090/ - if `pb_public` directory exists, serves the static content from it (html, css, images, etc.)
										- [PocketBase](http://127.0.0.1:8090/_/) - Admin dashboard UI
										- http://127.0.0.1:8090/api/ - REST API
									- The prebuilt PocketBase executable will automatically create and manage 2 new directories alongside the executable:
										- `pb_data` - stores your application data, uploaded files, etc. (usually should be added in `.gitignore`).
										- `pb_migrations` - contains JS migration files with your collection changes (can be safely committed in your repository).
										- You can even write custom migration scripts. For more info check the [Migrations docs](https://pocketbase.io/docs/migrations).
								- Commands
									- You could find all available commands and their options by running `./pocketbase --help` or `./pocketbase [command] --help`
							- Examples
							  collapsed:: true
								- Fetch a single record with the ID of `'258asqsoihc4oaz'` from the collection (table) `'quickfic_chapterContent'`
								  
								  ```js
								  import PocketBase from "pocketbase";
								  
								  const pb = new PocketBase("http://127.0.0.1:8090");
								  
								  const authData = await pb.admins.authWithPassword(
								    process.env.POCKETBASE_EMAIL,
								    process.env.POCKETBASE_PASSWORD
								  );
								  
								  // Fetch a single quickfic_chapterContent record.
								  const record = await pb
								    .collection("quickfic_chapterContent")
								    .getOne("258asqsoihc4oaz");
								  
								  // "logout" the last authenticated account
								  pb.authStore.clear();
								  ```
									- Run file using `node -r dotenv/config src/pocketbase.js`/`npm run pb`
							- ((63df8f12-9671-4cb1-b5a3-5a1f390adf5e))
						- Related: ((63b993a7-4e55-4137-a7d2-aba11803ef9e))
					- Coolify
					  collapsed:: true
						- self-hosted [https://news.ycombinator.com/item?id=26624341](https://news.ycombinator.com/item?id=26624341)
					- [Space Cloud](https://github.com/spaceuptech/space-cloud)
					  collapsed:: true
						- [https://news.ycombinator.com/item?id=26997595](https://news.ycombinator.com/item?id=26997595)
					- [PostgREST](https://postgrest.org)
					  collapsed:: true
						-
					- Userbase
					  collapsed:: true
						- [https://github.com/smallbets/userbase](https://github.com/smallbets/userbase#development)
						- [https://userbase.com/](https://userbase.com/)
					- [[Page not found · GitHub Pages](https://parseplatform.org/](https://parseplatform.org/))
					- [[Page not found · GitHub](https://github.com/xgenecloud/xgenecloud](https://github.com/xgenecloud/xgenecloud))
					- CouchDB + PouchDB
					  collapsed:: true
						- [https://couchdb.apache.org/](https://couchdb.apache.org/)
						- [https://pouchdb.com/](https://pouchdb.com/)
			- Gernerous free tiers
				- [Heroku Free Alternatives | Hacker News](https://news.ycombinator.com/item?id=33300053)
				- [Ask HN: So you moved off Heroku, where did you go? | Hacker News](https://news.ycombinator.com/item?id=33077118)
			- _Sorted by category_
				- Authorisation and Authentication
				  id:: 63a3166e-79ac-429a-b496-f58e487b3016
				  collapsed:: true
				  AKA Single Sign-On (SSO)
					- Meta
					  id:: 662a340c-6fa6-47e5-b72d-7253d44706f4
					  collapsed:: true
						- Overview of ((662a30d8-8107-4fbd-86ac-9a10c80ccb48)) in the context of ((66268000-e839-4084-a07e-3a1ea40dc54b)) and ((662a312e-b78f-45d4-9998-1dc9b23ec69d)) in the context of ((66267ffe-7f17-4d25-adea-8446abcfd8e0))
						  collapsed:: true
							- OAuth is an authorisation framework i.e. the act of allowing or denying users based on access rights (permissions). It does not provide authentication i.e. identifying if a user is a particular individual. For authentication you can use software like OIDC (OpenID Connect).
							- OAuth exists as an alternative to the insecure workflow where you would have to provide your username and password for a resource (e.g. Facebook login) to a client app (e.g. Clash of Clans). Instead you the user/resource owner authorise a client app to obtain an access token from an OAuth authorisation server. This token usually has a limited lifespan and fine-grained permissions, meaning it doesn't allow access to everything on an account like admin permissions might, but instead perhaps read-only permissions on specific data like your email and profile information. This access token is delivered to the client app, which then on your behalf can access resource servers which hold the sensitive data using the access token.
					- # Sorted by category
						- ## Authorisation
						  id:: 662a30d8-8107-4fbd-86ac-9a10c80ccb48
							- Meta
								- ((646349f5-99e6-49a5-9e82-fa0b79023382))
								- Permissions list is usually return as ((224ff848-65b9-4eee-a3c5-f15131048264))
							- [OAuth](https://oauth.net/)
							  id:: 66268000-e839-4084-a07e-3a1ea40dc54b
							  collapsed:: true
							  AKA Open Authorisation
								- Pros/Cons
									- Pros
										-
									- Cons
										-
									- Unclear
									- Upstream/Downstream Pros/Cons
									- Comparisons
										- ((66268000-e839-4084-a07e-3a1ea40dc54b)) vs JSON Web Tokens (JWT)
											- For ((66268000-e839-4084-a07e-3a1ea40dc54b))
												- Fine-grained - can give different access tokens depending on level of granted access
												- Robust - works at web scale for maximising user privacy by allowing 3rd-party apps access to parts of your private data
											- For JSON Web Tokens (JWT)
											  id:: 224ff848-65b9-4eee-a3c5-f15131048264
												- Much simpler - useful for developing simple apps for private LAN
											- Similarities
												-
											- Unclear
												- JWT Diagram
												  collapsed:: true
													- ![image.png](../assets/image_1714040623528_0.png)
								- Documentation
									- What is it
										- Resource owner (user) authorises a client application to obtain a resource key (access token) from an authorisation server, which it can then access resource servers e.g. Facebook user profile, friends
											- Previously you'd provide your username + password to a client application, which would then have full access to your account including the ability to change your email and password and thus lock you out
											- Key advantages
												- Revokable by end user
												- Limited permissions - application has read/write permissions to specific data only
									- Diagrams
										- ![image.png](../assets/image_1714040491627_0.png)
											- [OAuth Vs JWT | What is the difference? | Tech Primers - YouTube](https://youtu.be/a9R3Gq1BKxI)
										- ((662a25e7-c18e-40f7-84a7-e811f2b15314))
									- Parties involved
										- **Resource Owner**
											- The resource owner is the entity that owns the resources that the client application wants to access. This could be a user or a system that controls access to the resources. The resource owner authorizes the client application to access its resources.
										- **Client**
											- The client is the application or service that is attempting to access the protected resources on behalf of the resource owner. This could be a web application, a mobile app, or any other type of software that interacts with the OAuth server to obtain access to resources.
										- **Authorization Server**
											- The authorization server is responsible for authenticating the resource owner and granting authorization to the client application. It issues access tokens to the client after successful authentication and authorization. The authorization server also handles user consent and may interact with the resource server to access protected resources.
										- Additionally, there may be a fourth party:
										- **Resource Server**
											- The resource server is the server hosting the protected resources that the client application wants to access. It verifies the access tokens provided by the client application and grants access to the requested resources if the token is valid.
										- OAuth 1.0 vs 2.0
											- OAuth 2.0 delegates most security defences to HTTPS/TLS
											- It's easier to work with
											- More flexible (allows non-web clients)
											- Better decoupling (separation of duties)
								- {Archive}
									- [OAuth 2 Explained In Simple Terms - YouTube](https://youtu.be/ZV5yTm4pT8g)
										- Example diagram
										  id:: 662a25e7-c18e-40f7-84a7-e811f2b15314
											- ![image.png](../assets/image_1714039574427_0.png)
							- ((224ff848-65b9-4eee-a3c5-f15131048264))
						- ## Authentication
						  id:: 662a312e-b78f-45d4-9998-1dc9b23ec69d
							- Meta
								- ((646349f5-99e6-49a5-9e82-fa0b79023382))
							- [OIDC](https://openid.net/developers/how-connect-works/)
							  id:: 66267ffe-7f17-4d25-adea-8446abcfd8e0
							  collapsed:: true
							  AKA OpenID Connect | Identity layer built on top of ((66268000-e839-4084-a07e-3a1ea40dc54b))
								- [OpenID Connect vs OAuth | OpenID Connect explained - YouTube](https://youtu.be/PsbIGfvX900)
									- ((224ff848-65b9-4eee-a3c5-f15131048264)) is requested additionally, for additional private identifying info e.g. email, name, etc
						- ((662a30d8-8107-4fbd-86ac-9a10c80ccb48)) + ((662a312e-b78f-45d4-9998-1dc9b23ec69d))
							- Meta
								- Comparison table
								  collapsed:: true
									- | Software | Licence | GitHub Stars | Language | Initial Release | Comments |
									  | Keycloak | Apache-2.0 | 20k | Java | 2014 |
									  | ORY (Hydra and Kratos) | ? | 15k [GitHub - ory/kratos: Next-gen identity server replacing your Auth0, Okta, Firebase with hardened security and PassKeys, SMS, OIDC, Social Sign In, MFA, FIDO, TOTP and OTP, WebAuthn, passwordless and much more. Golang, headless, API-first. Available as a worry-free SaaS with the fairest pricing on the market!](https://github.com/ory/kratos) | Go | 2018 | Hydra handles OAuth 2.0 and OICD, whereas Kratos handles IAM, MFA, etc |
									  | Zitadel | Apache-2.0 | 7k [GitHub - zitadel/zitadel: ZITADEL - Identity infrastructure, simplified for you.](https://github.com/zitadel/zitadel) | Go | 2020 |
							- [Keycloak](https://www.keycloak.org/)
							  id:: 646349f5-e242-4b35-af4c-f406f25110b9
							  collapsed:: true
								- Research doc
								  collapsed:: true
									- Keycloak supports both OAuth and OIDC (thus authorisation and authentication) to enable single sign-on. It's open-source [GitHub - keycloak/keycloak: Open Source Identity and Access Management For Modern Applications and Services](https://github.com/keycloak/keycloak) and written 90% in Java, 8% in TypeScript. The TypeScript code can be found in `/js` directory and is mainly used for the web UI, local server and several libraries. The rest of it is written in JDK 17 including the extensible API and SPI. It is a Red Hat project under their WildFly division, initially released in 2014.
									- To get started you need to choose the installation method:
										- \_ Bare metal (via OpenJDK i.e. Java)
										- \_ Container (via Docker or Podman)
										- \_ Container orchestration (via Kubernetes or OpenShift)
									- In production you'll also need to select a database. Keycloak supports MariaDB Server, Microsoft SQL Server, MySQL, Oracle Database, PostgreSQL and Amazon Aurora PostgreSQL.
									- Depending on whether Keycloak needs to be exposed to external networks you may also need to set up a reverse proxy for security such as Apache HTTP Server, HAProxy, NGINX, etc. You also should set up HTTP over TLS or HTTPS for secure communication.
									- It can connect to existing user directories such as Office 365, LDAP, Active Directory. Two user directories that were specifically mentioned to check if it can integrate with were Okta and Amazon Cognito.
									- It can integrate with Okta, and here are some resources for doing so: [404 — Anaconda documentation](https://server-docs.anaconda.com/en/latest/admin/Keycloak_config/okta.html.) It can also integrate with Amazon Cognito, here are some resources for doing so: [How to add Keycloak as SAML Identity Provider in AWS Cognito | by karthik | Medium](https://awskarthik82.medium.com/how-to-add-keycloak-as-saml-identity-provider-in-aws-cognito-f091ec550dd7) and [How to add Keycloak as OIDC Identity Provider in AWS Cognito | by karthik | Medium](https://awskarthik82.medium.com/how-to-add-keycloak-as-oidc-identity-provider-in-aws-cognito-95018415aa0)
									- In production you'll also likely want high availability and multi-node clustered setup. Distributed cache option is available, and is built on top of [Infinispan](https://infinispan.org), a high-performance, distributable in-memory data grid. It also uses JGroups for inter-node messaging.
									- Metrics and logging are available for data analysis and recordkeeping.
									- A plain-text file-based vault or a Java KeyStore-based vault is available for storing secrets (Kubernetes, OpenShift, OIDC identity providers Client Secret, LDAP Bind Credential, SMTP Mail server password, etc).
									- There are several APIs available: [Server Developer Guide](https://www.keycloak.org/docs/latest/server_development) including Admin REST and Identify Brokering. There are also SPIs available including Action Token Handler, Event Listener, User Storage, Vault, etc.
									- The Authentication SPI supports several authentication mechanisms including Kerberos, password, OTP. This SPI like all the others can be extended. You can also add your own custom SPIs, custom REST endpoints, custom JPA entities to the Keycloak data model and more.
									- There are a number of community-supported extensions available here: [Page not found · GitHub Pages](https://www.keycloak.org/extensions.html.)
									- Their notable requested features lists includes:
										- \_ Trusted Device 2FA [Trusted Device two factor authenticator · Issue #8742 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/8742)
										- \_ Refresh token duration per-tab [Refresh token rotation with multiple tabs · Issue #14122 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/14122)
										- \_ SCIM support (System for Cross-domain Identity Management) [SCIM support · Issue #13484 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/13484)
										- \_ SMTP OAuth 2.0 authentication [Add support for SMTP OAuth 2.0 authentication for outgoing email · Issue #17432 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/17432)
										- \_ User ID ignored during user creation using the REST API [User ID ignored during user creation using the REST API · Issue #12454 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/12454)
										- \_ Federated Credential Management API [Implement the Federated Credential Management API · Issue #16834 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/16834)
										- \_ Passkeys support [Passkeys support · Issue #23656 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/23656)
										- \_ Passkeys auth flow form [WebAuthN Passwordless Form on Authentication Flows · Issue #25779 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/25779)
										- \_ Password strength meter / policy visibility [Password Strength Meter / Policy Visibility · Issue #12787 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/12787)
										- \_ realms/users/clients CRDs [[PLACEHOLDER] Add realms/users/clients CRDs · Issue #13566 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/13566)
										- \_ Software Bill of Materials [Feature - Include sbom for KeyCloak release · Issue #9448 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/9448)
										- \_ Automatically disable dormant users [Automatically disable dormant users. · Issue #11800 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/11800)
										- \_ Set order of credential types [Make it possible to set order of credential types · Issue #12102 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/12102)
										- \_ Authentication Flows not executed after Identity Provider User login [Authentication Flows not executed after Identity Provider User log in · Issue #10250 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/10250)
										- \_ Improved Metrics [Review Metrics Support · Issue #9036 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/9036)
										- \_ Read secrets from files [Read secrets from files · Issue #10816 · keycloak/keycloak · GitHub](https://github.com/keycloak/keycloak/issues/10816)
								- ((662a340c-6fa6-47e5-b72d-7253d44706f4))
								-
							- ((64943781-2095-423c-8eaa-49c5e356b480))
							- ((646349f5-7db9-48bb-b691-37ce8597e60e))
						- Related:
							- [Identity management - Wikipedia](https://en.wikipedia.org/wiki/Identity_management#Solutions)
					- # Sorted by license
						- FOSS
							- ((646349f5-e242-4b35-af4c-f406f25110b9))
							- [Ory Hydra](https://www.ory.sh/hydra/)
							  id:: 646349f5-7db9-48bb-b691-37ce8597e60e
							  collapsed:: true
							  ((66268000-e839-4084-a07e-3a1ea40dc54b)) + ((66267ffe-7f17-4d25-adea-8446abcfd8e0))
								- [Ory Kratos](https://github.com/ory/kratos)
							- [ZITADEL • The best of Auth0 and Keycloak combined. Built for the serverless era](https://zitadel.com/)
							  id:: 64943781-2095-423c-8eaa-49c5e356b480
							  collapsed:: true
								- [GitHub - zitadel/zitadel: ZITADEL - The best of Auth0 and Keycloak combined. Built for the serverless era.](https://github.com/zitadel/zitadel)
								-
							- [Keyoxide](https://keyoxide.org/)
							  collapsed:: true
							  Decentralised
								- [Keyoxide - Codeberg.org](https://codeberg.org/keyoxide)
								- Related: [Keybase](https://keybase.io/)
							- [Passport.js](https://www.passportjs.org/) for ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) + ((634bc0c1-71ec-40e0-ba94-bf79e177b591))
							  collapsed:: true
								- [passport - npm](https://www.npmjs.com/package/passport)
							- ((6463499d-8136-428d-82e9-ef2fed5174d5))
							- [Auth.js](https://authjs.dev/)
							  id:: 63a9bb71-000d-49c3-abf4-68024d7d6c26
							  collapsed:: true
								- [GitHub - nextauthjs/next-auth: Authentication for the Web.](https://github.com/nextauthjs/next-auth)
								-
								- Cons
									- Lacks React support in January 2023
								- Built on [OAuth Community Site](https://oauth.net/)
								- Split from ((63a31675-544d-45bc-adcc-146f5a186060))
								  id:: 63b57c64-c41c-4de2-aa37-5add66b3fdba
									- Runtime/framework agnostic
									- Builds on ((63a31675-544d-45bc-adcc-146f5a186060)) conventions/API
									- Decoupled from Next.js and Node.js
								- Bindings
									- SvelteKit (January 2023)
									- React (but not ((6737678f-c8d8-4751-ac83-fccd7d07c145)) yet in Jan)
							- [NextAuth.js](https://next-auth.js.org)
							  id:: 63a31675-544d-45bc-adcc-146f5a186060
							  collapsed:: true
								- When you need flexible, secure, and scalable auth, NextAuth.js is top notch. It ties into your existing database and provides a simple API to manage users and
								  sessions.
								- Related: ((63a9bb71-000d-49c3-abf4-68024d7d6c26)) : ((63b57c64-c41c-4de2-aa37-5add66b3fdba))
						- Proprietary
							- [Auth0](https://auth0.com/)
							  collapsed:: true
								- ((63974faf-1483-4e24-8001-ccf1736eaa64))
							- ((638e231d-32a2-47d2-836e-6563a046202b))
							- ((6463499e-3bb4-49ea-90d5-2df420c0fb1e))
							- ((64b81154-09ce-46c2-993a-0451497bcf3c))
							- ((64afc836-955f-4e6a-a145-6ca6ea566f42))
							- [Facebook Login](https://developers.facebook.com/docs/facebook-login/)
							- [Google Identity](https://developers.google.com/identity)
							- Twitter Login
							- [Clerk](https://clerk.com/)
						- Unsorted
							- Ipsilon (Or Keycloak): A web app adds OpenId, OAuth, OpenID Connect, Persona to FreeIPA.
							- RADIUS support is also used occasionally. I use a fork of a lovely Go project "ldap-radius" to handle that.
							- Kerberos
							- Related: ((63974fae-ea36-4574-b068-7eba4a7e8918))
					- User directory
						- FOSS
							- [LDAP](https://en.wikipedia.org/wiki/Lightweight_Directory_Access_Protocol)
							  collapsed:: true
							  AKA Lightweight Directory Access Protocol
								- Open, vendor-neutral
							- FreeIPA: Handles the actual user database. Supports Kerberos, LDAP.
							  collapsed:: true
								- Its basically an Active Directory for Linux/Unix environments. It's free the free upstream project for Red Hat Identity Management. It does Kerberos and also LDAP. Much better than setting up OpenLDAP freestyle. FreeIPA already has schemas, replication, upgradability, a web and a command line management front-end
							- [[IT Systems]] : ((63baa382-4e87-4588-858c-1bf3ed4a685d)) : ((16e48ca5-10dd-4c45-986c-5f03be9328c7))
						- Proprietary
							- [Active Directory](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)
							- ((64afc836-955f-4e6a-a145-6ca6ea566f42))
							- Google Apps, Office 365, ADFS, AD, SAML-P, WS-Federation, etc.
					- [Learning Resoureces]
						- [Best Open Source Auth Tools & Software for Enterprises 2025 | Cerbos](https://www.cerbos.dev/blog/best-open-source-auth-tools-and-software-for-enterprises-2025)
						-
					- Related: ((646349f5-850a-4bf6-ace6-ab463763e0ec))
			- _Related:_ ((638d061d-e696-4f04-933c-35f8836e125d))
		- Free services for open-source projects
			- [https://fosshost.org](https://fosshost.org/donate/)
	- Infrastructure as Code (IaC)
	  id:: 66cd757f-4ffc-4688-beb0-f0f2c2b603ea
	  collapsed:: true
	  AKA Continuous Integration / Continuous Delivery
		- Infrastructure as Code types
		  collapsed:: true
			- Pros/Cons
			  collapsed:: true
				- Pros
					-
				- Cons
					-
				- Unclear
				- Comparisons
			- _Server Provisioning_
			  id:: 6463499d-6d71-4948-84f4-9ae88ef6c73d
			  Whereas configuration management and server templating tools define the code that runs on each server, server provisioning tools such as Terraform, CloudFormation, and are responsible for creating the servers themselves. In fact, you can use provisioning tools to not only create servers, but also databases, caches, load balancers, queues, monitoring, subnet configurations, firewall settings, routing rules, SSL certificates, and almost every other aspect of your infrastructure
				- [CDK](https://cdk.dev/)
				  id:: 663e21a1-7e69-4806-a8dc-02c6d3686b5f
				  collapsed:: true
				  AKA Cloud Development Kit
					- Pros/Cons
						- Pros
							- You can write in a real programming language rather than configuration files
							  id:: 663d167c-3368-4382-b1e8-98a1d9a2177a
							  collapsed:: true
								- Configuration files
									- JSON or YAML template files for ((6463499e-dc33-4af7-bbb7-33338a8a325b))
									- HCL for ((638d061d-e696-4f04-933c-35f8836e125d))
								- Languages
									- [[JavaScript]]
									- ((629ccb26-1eab-4686-a7b8-f9433a871440))
									- [[C#]]
									- ((63e40d8d-784b-4c11-925c-5847395b972f))
									- [[Python]]
									- ((659d38ce-a277-4a58-8530-b3527f40432a))
									- ((646349e5-1c66-47b8-87ee-79d9bbf5e3c0)) (in Developer Preview)
								- Related: ((638d061d-e696-4f04-933c-35f8836e125d)) : ((6642210b-3bab-421a-a48d-6b97c49e6d02)) : ((6645bf72-b9b0-4f61-97e3-c166432e1b93))
						- Cons
							- It transpile from every language yet
							- It involves transpiling to [[JavaScript]] classes, which may have some limitations I don't fully understand
						- Unclear
						- Upstream/Downstream Pros/Cons
							- ((663cee91-26d7-47ea-8989-ab0ed0b22869))
						- Comparisons
							- ((ba67650c-f474-4038-b234-99dd345a80ca))
							  collapsed:: true
								- {{embed ((ba67650c-f474-4038-b234-99dd345a80ca))}}
					- Implementations
						- [CDKTF](https://www.terraform.io/cdktf)
						  id:: 663d1c53-446f-45e6-9c59-9dc8344c6c20
						  collapsed:: true
						  AKA CDK for Terraform / Cloud Development Kit for Terraform
							- Pros/Cons
								- Pros
									-
								- Cons
									- I am a senior software engineer with lots of AWS CDK experience, who just built a relatively large service with CDKTF. Here are my thoughts.
									  collapsed:: true
										- CDKTF is still unstable. Minor version updates cause breaking changes, and engineering teams do not want to write infrastructure whose code they have to constantly maintain.
										- Teams adopting CDK\* tools are usually those whose engineers own the entire stack (infrastructure, software, and operations). Those teams do not like knowingly signing up for operations work that could otherwise be avoided by not using CDKTF.
										- Native interfaces are too low level. CDK\* is great for providing customers with out-the-box abstractions. For example, the AWS CDK has L2 and L3 constructs that provide opinionated patterns that fit most customer use cases. CDKTF lacks this. Yes they have the AWS Adapter, but it is in preview and not reliable.
										- There are not many examples online, or on public git repositories. Engineers typically choose the path of least resistance. Being a new adopter means you can not piggy back of the existing work of others. This adds cognitive load and slows down the speed at which you can deliver products.
										- Bugs, bugs, bugs. CDKTF is still young and has a fair amount of bugs, mostly when transpiling from code to terraform JSON. I’ve personally found two regarding cross-stack dependencies and FQNs not being properly referenced. When these happen, you create temporary custom work arounds that no one wants in their code base. The CDKTF team also takes a while to address these bugs from my experience.
										- You can only use Typescript. I get that there are multiple languages supported via JSII, but in reality, you can only use Typescript. The same is true for AWS CDK. You can use Python and such, but life is much easier if you just stick to Typescript.
										- If your team does not know Typescript, then they are going to have to learn it. Good engineers can switch between languages pretty seemlessly, many however struggle when “learning” a new one.
										- The documentation sucks. Until recently, CDKTF constructs had no documentation. The ones available now are still occasionally incorrect, which results in me having to read the AWS CDKTF provider’s source code. Just another factor that adds more cognitive load and slows down delivery.
										- There is little contribution to community forums. That means that when CDKTF bugs occur, you are the one figuring out how to solve it. This is frustrating and can easily block less capable engineers.
										- It is hell for junior engineers. They will be learning AWS (or other cloud providers), Typescript, CDK, and Terraform concurrently, in addition to any other organization specific things. It is overwhelming, and you need to dedicate resources towards ramping them up. This, coupled with the poor documentation and lack of community contribution leads to a stressful environment for junior engineers and less capable engineers.
										- Infrastructure silo’d people tend to hate CDK\* because it “over-complicates” infrastructure. I’d argue the opposite. Generally their gripe comes down to needing to learn how to code, so there always tends to be some political pushback, albeit misguided in my opinion.
										- Your infrastructure code now needs to be held to the same standard as traditional software. This means linting, formatting, good design choices, and writing readable code. I tend to think unit tests for CDK\* are useless, so I personally skip them unless it’s for helper functions. Regardless, it adds more steps and rigor to your release process. Additionally, If you have an infrastructure silo, forcing them to adopt CDK\* will likely generate tons of tech debt. The code will not follow best practices, code reviewers will miss bugs, which results in issues you will eventually need to address.
										- Sharing reusable constructs means deploying more infrastructure, unless you are using a mono-repo. You now need an artifact repository for your packages. This should not be a big blocker, but it’s worth mentioning. Additionally, you tack on CI/CD costs for building and publishing your artifacts. While these are simple tasks, they introduce additional steps required to get up and running at scale.
										- CDK\* does not make sense for all teams, but I think it unlocks some great benefits for those who do use it. That being said, CDKTF has so many downsides right now, that I think an organization would be crazy to adopt it for a real use case. That opinion obviously changes once Hashicorp provides a stable 1.0 release.
								- Unclear
								- Upstream/Downstream Pros/Cons
									- ((64b7f615-66b0-4272-83e0-90ebbce92b48))
								- Comparisons
									- ((663d1c53-446f-45e6-9c59-9dc8344c6c20)) vs ((638d061d-e696-4f04-933c-35f8836e125d))
									  id:: 498af5d2-f7fd-4a04-8871-178d4d297635
										- For ((663d1c53-446f-45e6-9c59-9dc8344c6c20))
											- ((663d167c-3368-4382-b1e8-98a1d9a2177a))
										- For ((638d061d-e696-4f04-933c-35f8836e125d))
											-
										- Similarities
											- ((663d1c53-446f-45e6-9c59-9dc8344c6c20)) transpiles to HCL files so it also is cloud-agnostic
										- Unclear
											- ((6642210b-3bab-421a-a48d-6b97c49e6d02))
									- ((64b7f615-66b0-4272-83e0-90ebbce92b48)) vs ((663d1c53-446f-45e6-9c59-9dc8344c6c20))
										- For ((64b7f615-66b0-4272-83e0-90ebbce92b48))
										- For ((663d1c53-446f-45e6-9c59-9dc8344c6c20))
										- Similarities
										- Unclear
											- [GitHub - hashicorp/cdktf-aws-cdk: Use AWS CDK constructs in CDKTF projects](https://github.com/hashicorp/cdktf-aws-cdk)
												- [[technical preview] AWS Adapter - CDK for Terraform | Terraform | HashiCorp Developer](https://developer.hashicorp.com/terraform/cdktf/create-and-deploy/aws-adapter)
												- [Currently TypeScript-only](https://github.com/hashicorp/cdktf-aws-cdk/issues/151#issuecomment-1635597150)
									- ((663d1c53-446f-45e6-9c59-9dc8344c6c20)) vs ((66421b61-027a-482e-93e1-955ba1ede40b))
										- For ((663d1c53-446f-45e6-9c59-9dc8344c6c20))
											-
										- For ((66421b61-027a-482e-93e1-955ba1ede40b))
											- More mature
											- Better language support rather than mainly ((629ccb26-1eab-4686-a7b8-f9433a871440))
										- Similarities
										- Unclear
							- Documentation
								- [Repo](https://github.com/hashicorp/terraform-cdk)
								- [Docs](https://developer.hashicorp.com/terraform/cdktf)
								- [Tutorials](https://developer.hashicorp.com/terraform/tutorials/cdktf)
								- [Providers](https://github.com/cdktf)
							- [Learning Resources]
								- [CDKTF | Terrateam](https://terrateam.io/docs/integrations/cdktf/)
								-
								- [Create AWS Infrastructure using CDK for Terraform - DEV Community](https://dev.to/aws-builders/create-aws-infrastructure-using-cdk-for-terraform-3eg5)
								- [How to Build on AWS with CDK for Terraform (CDKTF)](https://spacelift.io/blog/terraform-cdk)
								-
						- ((64b7f615-66b0-4272-83e0-90ebbce92b48))
					- Ecosystem
						- [Construct Hub](https://constructs.dev/)
						  collapsed:: true
							- One shared pattern across all CDKs, is that they allow you to manage complexity and reduce code duplication by creating custom abstraction layers, referred to as [<u>constructs</u>](https://www.terraform.io/cdktf/concepts/constructs). Constructs allow developers to reuse existing resource configurations written in their programming language rather than defining resources by hand, simplifying development, and speeding up delivery of new features and services.
								- You can write your own custom constructs to share across your team and organization, and you can also browse [<u>Construct Hub</u>](https://constructs.dev/) to discover open source construct libraries for all CDKs. Check out the [<u>prebuilt provider constructs</u>](https://constructs.dev/search?cdk=cdktf&sort=downloadsDesc&offset=0) currently available for CDKTF on Construct Hub.
					- [Learning Resources]
						- CDK resources
							- [cdk.dev](https://cdk.dev/)
							- [GitHub - kalaiser/awesome-cdk: A collection of awesome things related to the AWS Cloud Development Kit (CDK)](https://github.com/kalaiser/awesome-cdk)
							- https://www.reddit.com/r/Terraform/comments/18115po/why_cdktf_has_such_little_adoption/
						- ((663c9df7-3979-42ee-9d86-2d453f96c946))
						- Notes from webinar [[2024-06-10 Monday]]
							- You can see your application visually on the CloudFormation console also
							- Each Construct can hold 1 or more AWS resources
							- `cdk init` is usually how you start a project
							- A **stack** is a unit of deployment e.g. one Terraform project. Equivalent to CloudFormation stacks
							- You can collate stacks to deploy a service (i.e. multiple stacks to make up your product)
							- Different levels of constructs available, with level 3 being the most abstract (patterns), level 2 (curated), leve
							- AWS CDK Toolkit
				- [Pulumi](https://www.pulumi.com/)
				  id:: 66421b61-027a-482e-93e1-955ba1ede40b
				  collapsed:: true
					- Pros/Cons
						- Pros
							- Doesn't ((6642210b-3bab-421a-a48d-6b97c49e6d02))
						- Cons
							- The 10k baseline enterprise contract fee and per-resource pricing model can also deter smaller projects or companies from adopting Pulumi. Look, I'd love to adopt Pulumi for its modern programming languages support and developer-friendly approach. However, unlike Terraform and TerraGrunt, it doesn't offer a fallback option to avoid using their agents, which could be a deal-breaker for some. It's like swinging a hammer and getting charged a few pennies every swing.
						- Unclear
						- Comparisons
							- ((66421b61-027a-482e-93e1-955ba1ede40b)) vs ((663e21a1-7e69-4806-a8dc-02c6d3686b5f))
							  id:: ba67650c-f474-4038-b234-99dd345a80ca
								- For ((66421b61-027a-482e-93e1-955ba1ede40b))
									-
								- For ((663e21a1-7e69-4806-a8dc-02c6d3686b5f))
									-
								- Similarities
									-
								- Unclear
									- [IaC Ergonomics: Choosing an Infrastructure as Code Tool | lbr.](https://leebriggs.co.uk/blog/2022/08/26/choosing-an-iac-tool)
									  id:: c7edc278-317a-4062-a34a-5712fc2f7cf9
									  collapsed:: true
										- ![image.png](../assets/image_1715608464267_0.png)
										- ...
										- ## The Authoring Experience
										  id:: 66422423-7fe5-4765-8f77-8af5398dc6e1
											- The **authoring experience** is defined as what mechanisms you have at your disposal to express your infrastructure. We already decided in [my last post](https://leebriggs.co.uk/blog/2022/07/20/nobody-knows-what-declarative-is.html) that generally, Infrastructure as Code tools have settled on the idea that they’re declarative, and what’s important is your ability to manipulate the way the declarative graph is built. There are 3 main camps that have been defined for the authoring experience:
											- ### Domain Specific Languages
												- A domain specific language is what it sounds like: a language defined specifically for that domain.
												- DSLs often have a shallow learning curve, and are built specifically for that purpose meaning they are often well suited to the purpose. They are often not [Turing complete](https://en.wikipedia.org/wiki/Turing_completeness) on their own and have a “ceiling” in terms of how expressive they are.
												- Some people will argue that DSLs are favourable for Infrastructure as Code because they prevent you from creating complexity because of that limited expressiveness. Those people are wrong, because ultimately badly written DSL code is just as complex and hard to refactor and understand as badly written code in a general purpose language, but I’ve found people are very very willing to die on that hill.
											- ### Programming Languages
												- Programming languages are the language(s) you know and love from application development or scripting. Python, TypeScript, Go, Java and many more are options in the Infrastructure as Code space, and they all bring their own toolchains, syntax and idiosyncrasies.
												- Programming languages are flexible, well understood in the industry (we build applications with them!), well supported by development tools and processes and have large ever growing communities behind them. You’ll often find that if you’re using an IDE in general development, your IDE gives you a lot of extra support and functionality beyond scribbling your infrastructure into a word document and hoping you didn’t make any mistakes.
												- However, programming languages have a slightly higher learning curve than DSLs. This increase in complexity brings with it a dramatic increase in expressibility and control. Again, some people don’t think this is a good thing but my experience has been that those people are just scared of programming languages.
												- Personally, I believe the Infrastructure as Code industry is trending the way of programming languages by default for the authoring experience for 2 reasons:
													- What you learn is reusable in other functions, like application development
													- Infrastructure is complicated, so you need the ability to represent it correctly when defining it.
												- Most of the major Infrastructure as Code tools have invested some time in a programming language authoring model at this point, so the winds seem to be changing.
												- Personally, I believe this to be a good thing. Using a language with a first class type system and IDE support is, in my opinion, the “correct” way to define your infrastructure. I’ve [written before](https://leebriggs.co.uk/blog/2022/08/26/choosing-an-iac-tool{ post_url 2022-05-09-learning-to-love-yaml }) about how if you’re not functional as a software developer and see yourself more as a “sysadmin” type, defining infrastructure in a programming language can level up your career because you’re learning the language through the lense of something you already know instead of blindly running `create-react-app` and hoping for the best.
												- If you’re an application developer you likely already know a programming language, and now you get to learn Infrastructure as Code through the lense of something you know - the language.
												- As I mentioned in the DSL section, naysayers will tell you that programming languages have too much “power” for infrastructure and the increased flexibility that comes with a programming language means that people can make things too hard to maintain and manage. Again, this is true of any software and language, but I won’t spend all of this post arguing with people who don’t want to see the way the industry is going hurtling towards them.
											- ### Configuration Languages
												- The last option is configuration languages. These have the least amount of expressibility, and usually need a templating language bolted on top to create any ability to get your job done. We’ve already decided that’s [completely fucking stupid](https://leebriggs.co.uk/blog/2019/02/07/why-are-we-templating-yaml.html), so I won’t say any more about that.
							- ((66421b61-027a-482e-93e1-955ba1ede40b)) vs ((638d061d-e696-4f04-933c-35f8836e125d))
								- For ((66421b61-027a-482e-93e1-955ba1ede40b))
									- Terraform ((6642210b-3bab-421a-a48d-6b97c49e6d02)) whereas Pulumi uses general-purpose programming languages
									- There's a [Pulumi Terraform bridge](https://github.com/pulumi/pulumi-terraform-bridge)
								- For Terraform
									- Bigger community
									- Probably more provider support
								- Similarities
								- Unclear
									-
					- [GitHub - pulumi/pulumi: Pulumi - Infrastructure as Code in any programming language. Build infrastructure intuitively on any cloud using familiar languages 🚀](https://github.com/pulumi/pulumi)
					-
				- [Terraform](https://www.terraform.io/)
				  id:: 638d061d-e696-4f04-933c-35f8836e125d
				  collapsed:: true
					- Pros/Cons
						- Pros
							-
						- Cons
							- TF's biggest problem is that it uses SDKs under the hood. If they converted to native cloud vendor specific templates, my life would be a whole lot better. TF is built on top of things like it's made of popsicle sticks.
						- Unclear
							- Utilises a DSL (Domain Specific Languages i.e. HCL, HashiCorp Configuration Language)
							  id:: 6642210b-3bab-421a-a48d-6b97c49e6d02
							  collapsed:: true
								- Pros
									- makes it usable by non-developer operations people
								- Cons
									- General-purpose programming languages are a lot more powerful
									  id:: 6645bf72-b9b0-4f61-97e3-c166432e1b93
										- Benefits include:
											- Autocomplete
											- Compile-time warnings
											- Control flow statements
											- Object-oriented
											- Reusable components
											- Logical components
											- Using your existing SDLC
											- Testing tools
									- Related: ((663d167c-3368-4382-b1e8-98a1d9a2177a))
								- ((c7edc278-317a-4062-a34a-5712fc2f7cf9)) : ((66422423-7fe5-4765-8f77-8af5398dc6e1))
								- [DSLs are a waste of time | lbr.](https://leebriggs.co.uk/blog/2023/09/04/dsl)
								  collapsed:: true
									- ..
									- ## Configuration complexity clock
										- The fact Puppet and Terraform (and other tools, of course) tend to converge on a DSL to solve infrastructure problems doesn’t appear to be a coincidence. Infrastructure (whether it be at the operating system layer or the API layer) is at its core, a sea of _configuration_. When dealing with configuration, the ((66422514-4230-4300-ad93-00509225e582)) dictates that eventually, you’re going to try and configure a DSL to manage it.
										- If you’re familiar with the configuration complexity clock, you’ll notice that the next step in the evolution of infrastructure configuration is to “hard code” the values again, which isn’t really a possibility because, well, have you seen how much infrastructure we’re dealing with? So what’s really happening here is that the DSLs (and particularly, the HCL DSL) is becoming it’s own progamming language, adding new constructs and methods which increase the amount of complexity in the language itself.
										- This is all well and good, because the features solve problems people have, the real issue here is that it’s still a DSL, and you’re still learning to play guitar hero instead of actually learning a useful skill you can learn elsewhere - playing the guitar.
								- [The Configuration Complexity Clock](https://mikehadlow.blogspot.com/2012/05/configuration-complexity-clock.html)
								  id:: 66422514-4230-4300-ad93-00509225e582
								  collapsed:: true
									- When I was a young coder, just starting out in the big scary world of enterprise software, an older, far more experienced chap gave me a stern warning about hard coding values in my software. “They _will_ have to change at some point, and you don’t want to recompile and redeploy your application just to change the VAT tax rate.” I took this advice to heart and soon every value that my application needed was loaded from a huge .ini file. I still think it’s good advice, but be warned, like most things in software, it’s good advice _up to a point_. Beyond that point lies pain.
									- Let me introduce you to my ‘Configuration Complexity Clock’.
									- ![image.png](../assets/image_1715610968432_0.png)
									- This clock tells a story. We start at midnight, 12 o’clock, with a simple new requirement which we quickly code up as a little application. It’s not expected to last very long, just a stop-gap in some larger strategic scheme, so we’ve hard-coded all the application’s values. Months pass, the application becomes widely used, but there’s a problem, some of the business values change, so we find ourselves rebuilding and re-deploying it just to change a few numbers. This is obviously wrong. The solution is simple, we’ll move those values out into a configuration file, maybe some appsettings in our App.config. Now we’re at 2 on the clock.
									- Time passes and our application is now somewhat entrenched in our organisation. The business continues to evolve and as it does, more values are moved to our configuration file. Now appsettings are no longer sufficient, we have groups of values and hierarchies of values. If we’re good, by now we will have moved our configuration into a dedicated XML schema that gets de-serialized into a configuration model. If we’re not so good we might have shoe-horned repeated and multi-dimensional values into some strange tilda and pipe separated strings. Now we’re at 4 or 5 on the clock.
									- More time passes, the irritating ‘chief software architect’ has been sacked and our little application is now core to our organisation. The business rules become more complex and so does our configuration. In fact there’s now a considerable learning curve before a new hire can successfully carry out a deployment. One of our new hires is a very clever chap, he’s seen this situation before. “What we need is a business rules engine” he declares. Now this looks promising. The configuration moves from its XML file into a database and has its own specialised GUI. Initially there was hope that non-technical business users would be able to use the GUI to configure the application, but that turned out to be a false hope; the mapping of business rules into the engine requires a level of expertise that only some members of the development team possess. We’re now at 6 on the clock.
									- Frustratingly there are still some business requirements that can’t be configured using the new rules engine. Some logical conditions simply aren’t configurable using its GUI, and so the application has to be re-coded and re-deployed for some scenarios. Help is at hand, someone on the team reads [Ayende’s DSLs book](http://www.manning.com/rahien/). Yes, a DSL will allow us to write arbitrarily complex rules and solve all our problems. The team stops work for several months to implement the DSL. It’s a considerable technical accomplishment when it’s completed and everyone takes a well earned break. Surely this will mean the end of arbitrary hard-coded business logic? It’s now 9am on the clock.
									- Amazingly it works. Several months go by without any changes being needed in the core application. The team spend most of their time writing code in the new DSL. After some embarrassing episodes, they now go through a complete release cycle before deploying any new DSL code. The DSL text files are version controlled and each release goes through regression testing before being deployed. Debugging the DSL code is difficult, there’s little tooling support, they simply don’t have the resources to build an IDE or a ReSharper for their new little language. As the DSL code gets more complex they also start to miss being able to write object-oriented software. Some of the team have started to work on a unit testing framework in their spare time.
									- In the pub after work someone quips, “we’re back where we started four years ago, hard coding everything, except now in a much crappier language.”
									- They’ve gone around the clock and are back at 12.
									- Why tell this story? To be honest, I’ve never seen an organisation go all the way around the clock, but I’ve seen plenty that have got to 5, 6, or 7 and feel considerable pain. My point is this:
									- _At a certain level of complexity, hard-coding a solution may be the least evil option._
									- You already have a general purpose programming language, before you go down the route of building a business rules engine or a DSL, or even if your configuration passes a certain level of complexity, consider that with a slicker build-test-deploy cycle, it might be far simpler just to hard code it.
									- As you go clockwise around the clock, the technical implementation becomes successively more complex. Building a good  rules engine is hard, writing a DSL is harder still. Each extra hour you travel clockwise will lead to more complex software with more bugs and a harder learning curve for any new hires. The more complex the configuration, the more control and testing it will need before deployment. Soon enough you’ll find that there’s little difference in the length of time it takes between changing a line of code and changing a line of configuration. Rather than a commonly available skill, such as coding C#, you find that your organisation relies on a very rare skill: understanding your rules engine or DSL.
									- I’m not saying that it’s never appropriate to implement complex configuration, a rules-engine or a DSL, Indeed I would jump at the chance of building a DSL given the right requirements, but I _am_ saying that you should understand the implications and recognise where you are on the clock before you go down that route.
							- Orchestration focus rather than Configuration Management
							  collapsed:: true
								- Chef, Puppet, Ansible, and SaltStack are all “configuration management” tools, which means they are designed to install and manage software on existing servers. CloudFormation and Terraform are “orchestration tools”, which means they are designed to provision the servers themselves, leaving the job of configuring those servers to other tools.
								- Configuration Management is often taken care of by Docker
							- Immutable rather Mutable
							  collapsed:: true
								- Configuration management tools such as Chef, Puppet, Ansible, and SaltStack typically default to a mutable infrastructure paradigm - it updates the servers already running
								- If you’re using an orchestration tool such as Terraform to deploy machine images created by Docker or Packer, then every “change” is actually a deployment of a new server
								- This approach reduces the likelihood of configuration drift bugs, makes it easier to know exactly what software is running on a server, and allows you to trivially deploy any previous version of the software at any time.
							- Declarative rather than Procedural
							  collapsed:: true
								- Chef and Ansible encourage a procedural style where you write code that specifies, step-by-step, how to to achieve some desired end state. Terraform, CloudFormation, SaltStack, and Puppet all encourage a more declarative style where you write code that specifies your desired end state, and the IAC tool itself is responsible for figuring out how to achieve that state.
								- For example, imagine traffic has gone up and you want to increase the number of servers to 15. With Ansible, the procedural code you wrote earlier is no longer useful; if you just updated the number of servers to 15 and reran that code, it would deploy 15 new servers, giving you 25 total! So instead, you have to be aware of what is already deployed and write a totally new procedural script to add the 5 new servers:
									- ec2:
										- count: 5
										- image: ami-v1
										- instance_type: t2.micro
								- With declarative code, since all you do is declare the end state you want, and Terraform figures out how to get to that end state, Terraform will also be aware of any state it created in the past. Therefore, to deploy 5 more servers, all you have to do is go back to the same Terraform template and update the count from 10 to 15:
								- Problems with procedural
									- When dealing with procedural code, the state of the infrastructure is not fully captured in the code. Reading through the three Ansible templates we created above is not enough to know what’s deployed. You’d also have to know the order in which we applied those templates. Had we applied them in a different order, we might end up with different infrastructure, and that’s not something you can see in the code base itself. In other words, to reason about an Ansible or Chef codebase, you have to know the full history of every change that has ever happened.
									- The reusability of procedural code is inherently limited because you have to manually to take into account the current state of the codebase. Since that state is constantly changing, code you used a week ago may no longer be usable because it was designed to modify a state of your infrastructure that no longer exists. As a result, procedural code bases tend to grow large and complicated over time.
							- Client-only rather than Client/Server architecture
							  collapsed:: true
								- Chef, Puppet, and SaltStack all use a client/server architecture by default. The client, which could be a web UI or a CLI tool, is what you use to issue commands (e.g “deploy X”). Those commands go to a server, which is responsible for executing your commands and storing the state of the system. To execute those commands, the server talks to agents, which must be running on every server you want to configure. This has a number of downsides:
									- You have to install and run extra software on every one of your servers.
									- You have to deploy an extra server (or even a cluster of servers for high availability) just for configuration management.
									- You not only have to install this extra software and hardware, but you also have to maintain it, upgrade it, make backups of it, monitor it, and restore it in case of outages.
									- Since the client, server, and agents all need to communicate over the network, you have to open extra ports for them, and configure ways for them to authenticate to each other, all of which increases your surface area to attackers.
									- All of these extra moving parts introduce a large number of new failure modes into your infrastructure. When you get a bug report at 3AM, you’ll have to figure out if it’s a bug in your application code, or your IAC code, or the configuration management client software, or the configuration management agent software, or the configuration management server software, or the ports all those configuration management pieces use to communicate, or the way they authenticate to each other, or…
								- ((6463499e-dc33-4af7-bbb7-33338a8a325b)), Ansible, and Terraform, use a client-only architecture.
									- Actually, ((6463499e-dc33-4af7-bbb7-33338a8a325b)) is also client/server, but AWS handles all the server details so transparently, that as an end user, you only have to think about the client code. The Ansible client works by connecting directly to your servers over SSH. Terraform uses cloud provider APIs to provision infrastructure, so there are no new authentication mechanisms beyond what you’re using with the cloud provider already, and there is no need for direct access to your servers. We found this as the best option in terms of ease-of-use, security, and maintainability.
						- Comparisons
							- ((498af5d2-f7fd-4a04-8871-178d4d297635))
								- {{embed ((498af5d2-f7fd-4a04-8871-178d4d297635))}}
					- Links
						- [hashicorp/terraform](https://github.com/hashicorp/terraform)
						  Terraform enables you to safely and predictably create, change, and improve infrastructure. It is a source-available tool that codifies APIs into declarative configuration files that can be shared amongst team members, treated as code, edited, reviewed, and versioned.
					- Documentation
						- Cheatsheet
							- How to use environment variables as Terraform variables
							  collapsed:: true
								- Change the `terraform apply` command to add the variable arguments
								  ```bash
								  terraform apply \
								  -var="AWS_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID}" \
								  -var="AWS_SECRET_ACCESS_KEY=${AWS_SECRET_ACCESS_KEY}" \
								  -var="AWS_SESSION_TOKEN=${AWS_SESSION_TOKEN}"
								  ```
								- Add default values for these variables to `variables.tf`
								  
								  ```yml
								  variable AWS_ACCESS_KEY_ID {
								  type = string
								  default = "default1"
								  }
								  
								  variable AWS_SECRET_ACCESS_KEY {
								  type = string
								  default = "default1"
								  }
								  
								  variable AWS_SESSION_TOKEN {
								  type = string
								  default = "default1"
								  }
								  ```
								- In `main.tf` you can now use the variable
								  
								  ```yml
								  echo "$var.AWS_ACCESS_KEY_ID}"
								  
								  cat > ~/.aws/credentials << EOL
								  aws_access_key_id = ${var.AWS_ACCESS_KEY_ID}
								  EOL
								  ```
							- How to reference output values from one module in another
							  collapsed:: true
								- In root directory you need to
									- Root module (`main.tf` is convention) you just need to make sure the source points to the correct paths for both modules, and add a new Input Variable e.g. `new1`
										- ```yaml
										  module "queue" {
										  source = "./modules/queue"
										  }
										  
										  module "s3" {
										  source = "./modules/s3"
										  new1 = module.queue.queue_url
										  }
										  ```
								- In module 1 (`queue`) you add an output value in that modules tf file or by convention in a `output.tf` file in that module subdirectory
									- ```yaml
									  # Example resource
									  resource "aws_sqs_queue" "terraform_queue" {
									    # blah blah
									  }
									  # NEW: Outputs
									  output "queue_url" {
									    value = aws_sqs_queue.terraform_queue.url
									  }
									  ```
										- `url` is the attribute, which can be found from the docs for the specific type of resource
								- In module 2 (`s3`) you need to declare an Input Variable to hold the other module's output value. You can put it in this module's tf file or by convention in a`variables.tf`
									- ```yaml
									  variable "sqs_url" {
									  type = string
									  }
									  ```
								- Then within module 2 (`s3`) you're able to reference the other module's Output Value by the name of your Input Variable
									- ```yaml
									  resource "aws_s3_bucket" "whatever" {
									  description = "${var.sqs_url}"
									  }
									  ```
							- ((661e6277-3a5c-4d27-9a29-79f3620f3da7)) can be used to script (non-interactive) `terraform console`
							  collapsed:: true
								- e.g. `terraform console <<<local.name`
								- Useful in environments like a Bash script where you can't interactively use `terraform console`
							- `aws_instance` : `ec2_instance`
							  collapsed:: true
								- `user_data` field
									- Can either point to a shell script in the same folder, or inline a shell script which then gives you access to Terraform variables:
									  
									  ```yml
									  user_data = file("${path.module}/run_on_ec2.sh")
									  
									  or
									  
									  user_data = <<EOF
									  #!/bin/bash
									  
									  echo "hello world"
									  echo "${var.prefix}"
									  
									  EOF
									  ```
							- `data "template_file" "<unique-name>"` can be used to reference other files like `.json` or `.sh`
							  collapsed:: true
								- Example
									- ```yaml
									  data "template_file "queue-policy" {
									  template = templatefile("./queue-policy.json", {
									  QUEUE_NAME = var.queue_name
									  REGION = var.region
									  })
									  }
									  ```
							- My scripts
								- BAE nitro enclave project
									- `run_terraform.sh`
									  collapsed:: true
										- ```sh
										  # Helper script to run Terraform commands
										  terraform init
										  terraform plan
										  
										  # first bit is to pick a specific existing AMI
										  aws ssm get-parameter --name /ro/Corp/AMI/Amazon2 | grep -o -P '(?<=Value\").*(?=\",)' | \
										  xargs -I{} terraform apply -var="ami={}" -var=instance_profile=BAE-Default-EC2-Role' \
										  -var='instance_size=m5.xlarge' -var=region=eu-west1' -var='subnet=subnet-75e05411' \
										  -var="AWS_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID}" \
										  --auto-approve
										  
										  # more vars but can't be bothered to copy them
										  ```
									- `main.tf`
									  collapsed:: true
										- ```yml
										  terraform {
										    required_providers {
										        aws = {
										            source = "hashicorp/aws"
										              version = "~> 4.16"
										          }
										      }
										  
										      # Remote tfstate on S3
										      backend "s3" {
										        bucket = "nest-nitro-eu-west-1"
										          key = "terraform.tfstate"
										          region = "eu-west-1"
										          endpoints = {
										            s3 = "https://s3.eu-west-1.amazonaws.com"
										          }
										      skip_region_validation = true
										      skip_credentials_validation = true
										      skip_metadata_api_check = true
										      skip_requesting_account_id = true
										      skip_s3_checksum = true
										      }
										      required_version = ">= 1.2.0"
										  }
										  
										  provider "aws" {
										    region = var.region
										  }
										  
										  # Bootstrap bash script which runs on newly made EC2 e.g. sudo apt update
										  data "template_file" "ec2-startup" {
										    template = templatefile("./scripts/ec2.sh", {
										        AWS_ACCESS_KEY_ID = var.AWS_ACCESS_KEY_ID
										          AWS_SECRET_ACCESS_KEY = var.AWS_SECRET_ACCESS_KEY
										          AWS_SESSION_TOKEN = var.AWS_SESSION_TOKEN
										          REGION = var.region
										      })
										  }
										  
										  module "ec2" {
										    source = "./modules/ec2"
										      ami = var.ami
										      instance_profile = var.instance_profile
										      instance_size = var.instance_size
										      subnet = var.subnet
										      security_groups = var.security_groups
										      user_data = base64encode(data.template_file.ec2-startup.rendered)
										  }
										  ```
									- `variables.tf`
									  collapsed:: true
										- ```yml
										  variable ami {
										  type = string
										  default = ""
										  description = "AMI ID for current corporate AMI"
										  }
										  
										  variable instance_profile {
										  type = string
										  default = "BAE-Default-EC2-Role"
										  description = "IAM role for the EC2"
										  }
										  
										  variable instance_size {
										  type = string
										  default = "mx.5large"
										  description = "instance size of the EC2"
										  }
										  
										  variable region {
										  type = string
										  default = "eu-west-1"
										  description = "region to deploy resources to"
										  }
										  
										  variable subnet {
										  type = string
										  default = "subnet-75e05411"
										  description = "subnet to deploy EC2 into"
										  }
										  
										  variable security_groups {
										  type = list(string)
										  default = ["sg-03210312"]
										  description = ""
										  }
										  
										  variable AWS_ACCESS_KEY_ID {
										  type = string
										  default = "default1"
										  }
										  
										  variable AWS_SECRET_ACCESS_KEY {
										  type = string
										  default = "default1"
										  }
										  
										  variable AWS_SESSION_TOKEN {
										  type = string
										  default = "default1"
										  }
										  ```
						- Learning resource sorted by priority
						  id:: 093d7ed4-60df-4011-b09e-cfb4920b19a3
							- [Hashicorp Certified Terraform Associate | Pluralsight](https://app.pluralsight.com/paths/certificate/hashicorp-certified-terraform-associate)
							  id:: 6f6e4c2c-97e7-42a1-9511-97785c7cdfe1
							  collapsed:: true
								- Courses
									- # Terraform - Getting Started
									  id:: 652909e6-133d-41fc-9e32-f216c04abfd1
									  collapsed:: true
										- Meta
											- Consider redoing whilst using my own repo (Gitea or GitHub? That way I can get a URL commit for each practical task)
										- [Repo](https://github.com/ned1313/Getting-Started-Terraform)
										  id:: 652e82bb-a001-4862-8f2d-3535a2456c46
										  `/home/boss/Documents/WORK/Programming/Learning/Terraform - Getting Started | Pluralsight course/Getting-Started-Terraform`
										- ## What You Need to Know About Infrastructure as Code
										  collapsed:: true
											- ### Infrastructure as Code defined
												- Provisioning infrastructure through software to achieve consistent and predictable deployments
											- Concepts
												- Defined in code - you're not following multiple steps to configure a deployment, it's all in one text file usually
												- Stored in source control - like most code store it in [[Git]]
												- Declarative or imperative
												  collapsed:: true
													- Imperative example
														- ```
														  get taco shell
														  get beans
														  put in cheese
														  ```
													- Declarative example
														- ```
														  food taco "bean-taco" {
														    ingredients = [
														      "beans", "cheese", "lettuce", "salsa"
														      ]
														  }
														  ```
												- Idempotent and consistent
													- Idempotent = aware of existing state, so you won't repeat the same steps to create a duplicate
												- Push or pull
													- Push = client-side, your configuration is pushed to target environment
													- Pull = agent running on server-side, it pulls config from a central source periodically
											- Benefits of IaC
												- Reusable components
													- Can now use this code for multiple projects
												- Automated deployment
												- Repeatable process
												- Consistent environments
												- Documented architecture
										- ## Deploying Your First Terraform Configuration
										  collapsed:: true
											- ### What is Terraform
											  collapsed:: true
												- Features
												  collapsed:: true
													- Infrastructure automation tool
													  collapsed:: true
														- Networking, virtual machines, etc
													- Open-source
													- Vendor-agnostic
													  collapsed:: true
														- Works any cloud platform with an API
													- Single binary compiled from ((646349e5-1c66-47b8-87ee-79d9bbf5e3c0))
													  id:: 652917ea-8b1a-4133-88ae-9e6fbc883144
													- Declarative syntax
													- HashiCorp Configuration Language or JSON (for writing configs). HCL is more human-readable than JSON
													- Push-based deployment
												- Core components
												  collapsed:: true
													- Executable i.e. ((652917ea-8b1a-4133-88ae-9e6fbc883144))
													- Configuration files - usually `.tf`
													- Provider plugins - executables triggered by Terraform to interact with the platform provider's APIs e.g. AWS
													- State data - current metadata about your deployment. Terraform calculates a diff between your state data and the config whenever you update your config, after checking if state data changed first
											- ### Installing Terraform
											  collapsed:: true
												- Download the executable for your platform
												- Add to your PATH environment variable
												- [GitHub - ned1313/Getting-Started-Terraform: Exercise files for my Pluralsight course](https://github.com/ned1313/Getting-Started-Terraform)
												- To find out how to download Terraform: https://terraform.io/downloads
											- ### Using the CLI
											  collapsed:: true
												- `terraform version`
												  See the current version installed
												- `terraform -help`
											- ### Globomantics Scenario
											  collapsed:: true
												- 1 AWS region, 1 VPC with 1 subnet, 1 EC2 running NGINX, and networking
											- ### Terraform Object Types
											  collapsed:: true
												- Providers
												  collapsed:: true
													- AWS plugin in this case
												- Resources
												  collapsed:: true
													- What you're creating in the target environment e.g. EC2 instance, database
												- Data sources
												  collapsed:: true
													- A way to query information from a provider
													- e.g. list of AWS availability zones in a region, list of VM templates for a VPS cluster
											- ### Configuration Block Syntax
											  collapsed:: true
												- HashiCorp Configuration Language (HCL) uses block syntax for everything in the file
												- `main.tf` - template
												  id:: 65295314-1a1e-459a-8190-862029ca2693
												  collapsed:: true
													- collapsed:: true
													  ```tf
													  block_type "label" "name_label" {
													    key = "value"
													      nested_block {
													        key = "value"
													          nested_block {
													            key = "value"
													          }
													      }
													  }
													  ```
														- `name_label` = a unique identifier that can be reused for the rest of the config
												- `main.tf` - example
												  collapsed:: true
													- collapsed:: true
													  ```tf
													  resource "aws_instance" "web_server" {
													    name = "web-server"
													      ebs_volume {
													        size = 40
													      }
													  }
													  ```
														- `name = "web-server"` = will be shown in AWS console
												- Terraform Object Reference
												  collapsed:: true
													- Template
													  collapsed:: true
														- `<resource_type>.<name_label>.<attribute>`
													- Examples
													  collapsed:: true
														- `aws_instance.web_server.name`
													- See Terraform documentation for the full list of attributes available
											- ### Reviewing the Base Configuration
											  collapsed:: true
												- `main.tf` example
													- collapsed:: true
													  
													  ```tf
													  # PROVIDERS
													  
													  provider "aws" {
													    access_key 	= "ACCESS_KEY"
													      secret_key 	= "SECRET_KEY"
													      region 		= "us-east-1"
													  }
													  
													  # DATA
													  
													  data "aws_ssm_parameter" "amzn2_linux" {
													    name = "/aws/service/ami-amazon-linux-latest/amzn2-ami-hvm-x86_64-gp2"
													  
													  }
													  
													  #############
													  # RESOURCES
													  #############
													  
													  ## NETWORKING
													  resource "aws_vpc" "app" {
													    cidr_block				= "10.0.0.0/16"
													      enable_dns_hostnames 	= true
													  }
													  
													  resource "aws_internet_gateway" "app" {
													    vpc_id = aws_vpc.app.id 	# Associating the internet gateway with the VPC
													  }
													  
													  resource "aws_subnet" "public_subnet1" {
													    cidr_block				= "10.0.0.0/24"
													      vpc_id					= aws_vpc.app.id
													      map_public_ip_on_launch = true 		# Gets a public IP address
													  }
													  
													  ## ROUTING
													  resource "aws_route_table" "app" {
													    vpc_id = aws_vpc.app.id
													  
													      route {
													        cidr_block = "0.0.0.0/0"
													          gateway_id = aws_internet_gateway.app.id
													      }
													  }
													  
													  resource "aws_route_table_association" "app_subnet1" {
													    subnet_id		= aws_subnet.public_subnet1.id
													      route_table_id	= aws_route_table.app.id
													  }
													  
													  ## SECURITY GROUPS
													  # Nginx security group
													  resource "aws_security_group" "nginx_sg" {
													    name = "nginx_sg"
													      vpc_id = aws_vpc.app.id
													  
													      # HTTP access from anywhere
													      ingress {
													        from_port	= 80
													          to_port		= 80
													          protocol	= "tcp"
													          cidr_blocks = ["0.0.0.0/0"]
													      }
													  
													      # outbound internet access (to anywhere)
													      egress {
													        from_port = 0
													          to_port = 0
													          protocl = "-1"
													          cidr_blocks = ["0.0.0.0/0"]
													      }
													  }
													  
													  ## INSTANCES
													  resource "aws_instance" "nginx1" {
													    ami = nonsensitive(data.aws_ssm_parameter.amzn2_linux.value)
													      instance_type = "t2.micro"
													      subnet_id = aws_subnet.public_subnet1.id
													      vpc_security_group_ids = [aws_security_group.nginx_sg.id]
													  
													      user_data = <<EOF
													  #! /bin/bash
													  sudo amazon-linux-extras install -y nginx1
													  sudo service nginx start
													  sudo rm /usr/share/nginx/html/index.html
													  echo '<html><head><title>Taco Team Server</title></head><body style=\"background-c"'
													  EOF
													  
													  }
													  ```
														- `ACCESS_KEY` and `SECRET_KEY` shouldn't be stored in the file itself - instead point to environment variables or a credentials file
														- `aws_ssm_parameter` = AWS Systems Manager parameter, giving it the label `amzn2_linux`
														- `name` = grabs this AMI for usage
											- ### Terraform Workflow
											  id:: 65292b80-13ca-4172-bcb5-a4946b65047b
											  collapsed:: true
												- 3 basic steps
													- 1. `terraform init`
													     id:: 652e608c-2051-471f-a103-13af45cef2da
														- Looks for configuration files in current working directory and analyses them to see whether they need any provider plugins
														- If any provider plugins are needed, it'll try to download them from the public registry (unless you specify a different download location)
														- It will create a state data file in the current working directory if you don't specify a particular backend
													- 2. `terraform plan`
														- It look at the differences between your configuration and state data then make a plan to update your target environment with the desired configuration
														- You don't have to use `terraform plan`, but Terraform will always generate an execution plan before it makes any changes
													- 3. `terraform apply`
													     id:: 652e6200-f872-4aed-901c-9116d08e34d3
														- It will execute the `terraform plan` that's been saved using provider plugins. The resources will be created or modified in the target environment and then the state data will be updated to match
														- If `terraform plan` or `terraform apply` is run again without any changes, Terraform will tell us no changes are necessary
												- 4th step (optional): `terraform destroy`
													- It will destroy everything in the target environment that Terraform is managing, based on what it knows from the state data
											- ### Deploying the Base Configuration
											  collapsed:: true
												- ((652e82bb-a001-4862-8f2d-3535a2456c46)) : `commands/m3_commands.sh`
												- Copy the `main.tf` into a new directory, then replace the values for the AWS keys with your own.
												  id:: 652e8332-1791-4e2d-94e4-4f3d2d61337f
												- #+BEGIN_WARNING
												  Don't commit these keys to source control. This method is just a demo of the least-secure method - a better method will be shown later.
												  #+END_WARNING
												- Do the typical 3 steps of ((65292b80-13ca-4172-bcb5-a4946b65047b)) except:
													- `terraform plan -out m3.tfplan` = will write the execution plan to a file named `m3.tfplan`. Doesn't need to have file extension `.tfplan` but it's best practicet
													- `terraform apply "m3.tfplan"` = applies that exact plan
												- A lock file `.terraform.lock.hcl` will be created to record the provider selections - include this in version control so that Terraform can guarantee to make the same selections by default when you run `terraform init` in the future
											- ### Validating the Deployment
												- In the ((64b806d2-fdd2-4f63-84b8-4f0b76f20027)) for EC2 left-click the instance -> go to the assigned website for it and check there's success text
										- ## Using Input Variables and Outputs
										  collapsed:: true
											- ### Working with Data in Terraform
											  collapsed:: true
											  The 3 types of values
												- Input variables
												  id:: 652ea860-d320-492d-8883-c0d6e8092187
													- They pass information to Terraform at runtime i.e. when generating an execution plan
												- Local values
													- Computed values inside the configuration that can be referenced throughout the config
												- Output values
													- Computed based on ((652ea860-d320-492d-8883-c0d6e8092187)) and internal references, returned by Terraform
											- ### 1) Input Variable Syntax
											  collapsed:: true
												- ```tf
												  variables "name_label" {}
												  ```
												- ```tf
												  variables "name_label" {
												    type	= value
												    description = "string" # i.e. the purpose behind the variable
												      default = value
												      sensitive = true | false
												  }
												  ```
													- `default = value` allows you to set a default value for the variabel
														- Note: Terraform will prompt you to submit one if there isn't one computed
													- `sensitive = true | false` - boolean that makes Terraform not show the variable in it's logging or terminal output. Often used for passwords or API keys
												- Example:
												  
												  ```tf
												  variable "billing_tag" {}
												  
												  variable "aws_region" {
												    type 		= string
												      description = "Region to use for AWS resources"
												      default		= "us-east-1"
												      sensitive	= false
												  }
												  ```
												- Terraform Variable Reference
													- ```tf
													  var.<name_label>
													  ```
													- Example
													  ```tf
													  var.aws_region
													  ```
											- ### Terraform Data Types
											  collapsed:: true
												- Primitives
												  collapsed:: true
													- String, number, bool
												- Collection
												  id:: 652fd48e-7831-4f75-a767-b8aa710b8dd8
												  collapsed:: true
													- i.e. a grouping of primitives or other collections, all of the same data type
													- List - ordered group of elements
													- Set - unordered group of unique elements
													- Map - group of key-value pairs
												- Structural
												  collapsed:: true
													- i.e. similar to ((652fd48e-7831-4f75-a767-b8aa710b8dd8)) except they allow you to mix the data types stored in each group
													- Tuple - equivalent to lists
													- Objects - equivalent to maps
												- Any
												  collapsed:: true
													- e.g. `list(any)` can be a list of strings, numbers or even list of lists
													- Like ((652fd48e-7831-4f75-a767-b8aa710b8dd8)) all the elements inside must be of the same data type
												- Null
												  collapsed:: true
													- i.e. less of a data type and more an absence of a value
													- Often used as the default value for an input variable
												- #### Data Type Examples
													- ```yml
													  # List
													  [1, 2, 3, 4]
													  
													  # Map
													  {
													    small	= "t2.micro"
													      medium	= "t2.small"
													  }
													  
													  
													  ```
												- #### Referencing Collection Values
													- Example 1
														- ```yml
														  variable "aws_regions" {
														  type		= list(string)
														  description	= "Regions to use for AWS resources"
														  default		= ["us-east-1", "us-east-2", "us-west-1", "us-west-2"]
														  }
														  ```
														- Referencing this variable:
														  
														  ```yml
														  # Template syntax
														  var.<name_label>[<element_number>]
														  
														  # Example
														  var.aws_regions[0]
														  ```
													- Example 2
														- ```yml
														  variable "aws_instance_sizes" {
														  type = map(string)
														  description = "Instance sizes to use in AWS"
														  default = {
														  small = "t3.micro"
														  medium = "m4.large"
														  large = "m4.xlarge"
														  }
														  }
														  ```
														- Referencing this variable:
														  
														  ```yml
														  # Either
														  var.<name_label>.<key_name>
														  var.<name_label>["key_name"]
														  
														  # Either
														  var.aws_instance_sizes.small
														  var.aws_instance_sizes["small"]
														  ```
											- ### Globomantics Configuration Updates
											  collapsed:: true
												- Potential improvements
													- Remove AWS credentials from being hard-coded
													- Replace hard-coded values with variables
													- Tags for company, project and billing
													- Generate output of public DNS hostname
											- ### Adding Variables to the Configuration
											  collapsed:: true
												- Create a `variables.tf` file
												- Swap
													- `main.tf`
														- Old
														  ```yml
														  provider "aws" {
														  access_key = "AK321312"
														  secret_key = "0WADWDWWAD"
														  region 	   = "us-east-1"
														  }
														  ```
														- New
														  ```yml
														  provider "aws" {
														  access_key = var.aws_access_key
														  secret_key = var.aws_secret_key
														  region 	   = var.aws_region
														  }
														  ```
													- `variables.tf`
													  
													  ```yml
													  variable "aws_access_key" {
													  type = string
													  description = "AWS Access Key"
													  sensitive = true
													  }
													  
													  variable "aws_secret_key" {
													  type = string
													  description = "AWS Secret Key"
													  sensitive = true
													  }
													  
													  variable "aws_region" {
													  type = string
													  description = "AWS region to use for resources"
													  default = "us-east-1"
													  }
													  ```
														- Notable: `sensitive = true`
											- ### 2) Local Values Syntax
											  collapsed:: true
												- Internal to the configuration
												- Values with multiple references throughout your config
												- Data transformation
												- Syntax
													- ```yml
													  locals {
													  key = value
													  }
													  ```
												- Example
													- `main.tf`
													  ```yml
													  locals {
													  instance_prefix = "globo"
													  common_tags = {
													  company 	= "Globomantics"
													  project		= var.project
													  billing_code = var.billing_code
													  }
													  }
													  ```
													- Terraform Locals Reference
														- ```yml
														  local.<key>
														  local.instance_prefix
														  local.common_tags.company
														  ```
															- #+BEGIN_NOTE
															  When referencing it use `local`, not `locals`.
															  #+END_NOTE
											- ### Adding Locals to the Configuration
											  collapsed:: true
												- Create a `locals.tf` file for best practice (though you can just do everything in `main.tf`)
												- Example
													- `main.tf`
													  ```yml
													  resource "aws_vpc" "app" {
													  tags = local.common_tags
													  }
													  ```
													- `locals.tf`
													  ```yml
													  locals {
													  common_tags = {
													  company = var.company
													  project = "${var.company}-${var.project}"
													  billing_code = var.billing_code
													  }
													  }
													  ```
													- `variables.tf`
													  
													  ```yml
													  variable "company" {
													  type = string
													  description = "Company name for resource tagging"
													  default = "Globomantics"
													  }
													  
													  variable "project" {
													  type = string
													  description = "Project name for resource tagging"
													  }
													  
													  variable "billing_code" {
													  type = string
													  description = "Billing code for resource tagging"
													  }
													  ```
											- ### 3) Output Values Syntax
											  collapsed:: true
												- Used to get information out of Terraform
												- These are stored in state data
												- Syntax
													- ```yml
													  output "name_label" {
													  value		= value
													  description = "string"
													  sensitive = true | false
													  }
													  ```
												- Example
													- `main.tf`
													  ```yml
													  output "public_dns_hostname" {
													  value		= aws_instance.web_server.public_dns
													  description	= "Public DNS hostname of web server"
													  }
													  ```
											- ### Adding Outputs to the Configuration
											  collapsed:: true
												- Example
													- `outputs.tf`
													  ```yml
													  output "aws_instance_public_dns" {
													  value = "http://${aws_instance.nginx1.public_dns}"
													  description = "Public DNS hostname for the EC2 instance"
													  }
													  ```
											- ### Validate the Configuration
											  collapsed:: true
												- Can be used to check that you've got your value string interpolation written correctly for example
												- Two commands for linting code:
													- `terraform fmt`
														- Formats code in working directory to follow HashiCorp's standard
														- Command flags
															- `-check` will check your code but not alter the files
															- `-recursive` will check and change your code in the working directory and any subdirectories
														- Does not check validity of logic or syntax unlike ((652ffe90-52f0-4351-a294-4f580b5b1749))
													- `terraform validate`
													  id:: 652ffe90-52f0-4351-a294-4f580b5b1749
														- First run ((652e608c-2051-471f-a103-13af45cef2da))
														- Checks the syntax and logic
														- Does not check state
														- No guarantee of success - there are other reasons it may fail
											- ### Using the Validate Command
											  collapsed:: true
												- Example
													- `terraform fmt -check` tells you which files it needs to change
													- `terraform fmt` will make the changes in those files e.g. spacing
													- `terraform validate` then can be used to notice variables that don't exist, incorrect brackets around values etc
											- ### Supplying Variable Values
											  collapsed:: true
												- Multiple ways of doing this (in order of precedence)
													- Environment variables starting with `TF_VAR_` will also be used
													- `terraform.tfvars` or `terraform.tfvars.json` in the same directory is found automatically by Terraform and utilised
													- `.auto.tfvars` or `.auto.tfvars.json` in the same directory is similarly found automatically by Terraform and utilised
													- At the CLI use `-var-file` flag to give a text file full of the variables desired
													- At the CLI use `-var` flag to give the value at runtime
													- Using the `default` value
											- ### Deploying the Updated Configuration
											  collapsed:: true
												- How to pass our variables at the command line
													- Example1 - use `-var` flag
														- ```yml
														  terraform plan -var=billing_code="A234FWD" -var=project="web-app" -out test.tfplan
														  ```
													- Example2 - store nonsensitive variables in a file called `terraform.tfvars`
														- ```YML
														  billing_code = "AS40242"
														  project = "globo-web-app"
														  ```
													- Example3 - store sensitive data in environment variables
														- ```yml
														  # For Unix
														  export TF_VAR_aws_access_key=YOUR_ACCESS_KEY
														  export TF_VAR_aws_secret_key=YOUR_SECRET_KEY
														  
														  # For PowerShell
														  $env:TF_VAR_aws_access_key="YOUR_ACCESS_KEY"
														  ```
										- ## Updating Your Configuration with More Resources
										  collapsed:: true
											- ### Overview
											  collapsed:: true
												- Improve our architecture
												- Using the documentation
												- Adding resources
												- Viewing state data
											- ### Globomantics Archtecture Updates
											  collapsed:: true
												- Potential improvements
													- Add a second availability zone
													- Add a second EC2 instance
													- Add load balancing for instances
													- Maintain readability of code
												- Additional data sources and resources
													- ```yml
													  # Data source
													  "aws_availability_zones" # List of current availability zones
													  
													  # Load balancer resources
													  "aws_lb" # AWS Application Load Balancer
													  "aws_lb_target_group" # Target group for load balancer
													  "aws_lb_listener" # Listener configuration for target group
													  "aws_lb_target_group_attachment" # Attach to EC2 instances
													  ```
											- ### Adding New Resources to the Configuration
											  collapsed:: true
												- Create
													- `loadbalancer.tf`
													- `instances.tf`
													- `network.tf`
												- Notable moving files from `main.tf`
													- `instances.tf` needs `data "aws_ssm_parameter"`
											- ### Using the Documentation
											  collapsed:: true
												- [Documentation for Terraform](https://developer.hashicorp.com/terraform)
												- [Documentation for providers and resources](https://registry.terraform.io)
													- Providers : AWS : Documentation : use filter search box on the left
													- e.g. `aws_availability_zones` has arguments and attributes
														- Adding it to `network.tf`
														  ```yml
														  data "aws_vailability_zones" "available" {
														  state = "available"
														  }
														  ```
											- ### Updating the Network and Instance
											  collapsed:: true
												- Updated the `aws_subnet` resource
													- Old
													  ```yml
													  resource "aws_subnet" "public_subnet1" {
													  cidr_block              = var.vpc_public_subnet1_cidr_block
													  vpc_id                  = aws_vpc.app.id
													  map_public_ip_on_launch = var.map_public_ip_on_launch
													  
													  tags = local.common_tags
													  }
													  ```
													- New
													  
													  ```yml
													  resource "aws_subnet" "public_subnet1" {
													  cidr_block              = var.vpc_public_subnet1_cidr_block
													  vpc_id                  = aws_vpc.app.id
													  map_public_ip_on_launch = var.map_public_ip_on_launch
													  availability_zone = data.aws_availability_zones.available.names[0]
													  
													  tags = local.common_tags
													  }
													  
													  resource "aws_subnet" "public_subnet2" {
													  cidr_block              = var.vpc_public_subnet1_cidr_block
													  vpc_id                  = aws_vpc.app.id
													  map_public_ip_on_launch = var.map_public_ip_on_launch
													  availability_zone = data.aws_availability_zones.available.names[1]
													  
													  tags = local.common_tags
													  }
													  ```
											- ### Adding the Load Balancer Resource
											  collapsed:: true
												- `loadbalancer.tf`
												  
												  ```yml
												  # AWS LB target group
												  resource "aws_lb_target_group" "nginx" {
												    name 	= "nginx-alb-tg"
												      port	= 80
												      protocol = "HTTP"
												      vpc_id	= aws_vpc.app.id
												  
												      tags = local.common_tags
												  }
												  
												  # AWS LB listener
												  resource "aws_lb_listener" "nginx" {
												    load_balancer_arn = aws_lb.nginx.arn
												      port = 80
												      protocol = "HTTP"
												  
												      default_action {
												        type = "forward"
												          target_group_arn = aws_lb_target_group.nginx.arn
												      }
												  
												      tags = local.common_tags
												  }
												  
												  # aws_lb_target_group_attachment
												  resource "aws_lb_target_group_attachment" "nginx1" {
												    target_group_arn = aws_lb_target_group.nginx.arn
												      target_id = aws_instance.nginx2.id
												      port = 80
												  }
												  ```
											- ### Working with State Data
											  collapsed:: true
												- Contents
													- Resources, data sources and outputs
													- JSON format (and not meant to be touched by users)
													- Maps object address in config to unique ID in target environment
												- Planning
													- Whenever an execution plan is generated the state data is loaded into memory and then updated with new values after querying the target environment
													- Diff between configuration and state data
													- Whilst updating it creates a lockfile
												- Location
													- Local (by default)
													- Remote: alternatively store the state data on AWS, Azure, NFS, Terraform Cloud
													- Remote has the benefits of collaboration and protection vs data loss
													- See ((652909e9-8763-44ee-ad4b-d9a5103b4ad6)) for more info on remote state data store
												- Workspaces
													- Allows you to use the same configuration to spin up multiple instances of a deployment, each with separate state data
													- See ((652909e9-8763-44ee-ad4b-d9a5103b4ad6)) fro more info
											- ### State Data Scenarios
											  collapsed:: true
												- How Terraform will update state depending on the scenario
												- Scenario 1
												  New resource block in the config
													- Before:
														- Configuration: `aws_instance.nginx`
														- State data: `empty`
														- AWS: `empty`
													- Next
														- AWS: `Create instance`
														- State data: `new_aws_instance`
												- Scenario 2
												  Missing instance in AWS
													- Before:
														- Configuration: `aws_instance.nginx`
														- State data: `aws_instance`
														- AWS: `empty`
													- Next
														- AWS: `Create instance`
														- State data: `aws_instance-updated-id`
												- Scenario 3
												  Removed instance resource from configuration
													- Before:
														- Configuration: `empty`
														- State data: `aws_instance`
														- AWS: `id-2324223`
													- Next:
														- AWS: `Destroy instance`
														- State data: `empty`
												- Scenario 4
												  Removed entry from state data
													- Before:
														- Configuration: `aws_instance.nginx`
														- State data: `empty`
														- AWS: `id-2324223`
													- Next:
														- AWS: `Create instance`
														- State data: `aws_instance`
											- ### Terraform State Content and Commands
											  collapsed:: true
												- `"mode": "managed"` indicates a resource, not a data source
												- State Commands
													- ```yml
													  # List all state resources
													  terraform state list
													  
													  # Show a specific resource
													  terrfaform state show ADDRESS
													  
													  # Move an item in state
													  terraform state mv SOURCE DESTINATION
													  # e.g. renaming resources or moving them into modules
													  
													  # Remove an item in state
													  terraform state rm ADDRESS
													  # useful for removing a resource from Terraform management without actually destroying it
													  ```
											- ### Deploying the Updated Architecture
											  Practical exercise changes only
											- ### Updating the Outputs
											  Practical exercise changes only
										- ## Adding a New Provider to Your Configuration
										  collapsed:: true
											- ### Overview
											  collapsed:: true
												- Extending the script
												- Understanding providers
												- Dependency graphs
												- Post deployment configuration
											- ### Globomantics Architecture Overview
											  collapsed:: true
												- Copy website content
												  id:: 65323c59-5f43-46d0-9c92-c7e9ef0523a3
												- Log traffic to an S3 bucket
												- Use specific provider versions
												- Properly format files
												- Plan
													- Copy website content and log traffic both to S3
											- ### Terraform Providers
											  collapsed:: true
												- They're available in both public and private registries
												- Provider tiers
													- Official (maintained by HashiCorp)
													- Partner (maintained by a 3rd-party that is in HashiCorp's Partner Program)
													- Community
												- Open-source
												- Written in Go
												- Made up of both resources and data sources
												- Versioned using ((646349e1-db48-4473-9372-0dfa7d2b191e))
												- Terraform allows you to select which version to use
												- Multiple instances of a provider can be used
													- Alias argument to refer to each
													- Usecases
														- AWS provider usage is limited to one region, need multiple instances to access multiple regions
											- ### Terraform and Provider Block Syntax
											  collapsed:: true
												- `terraform.tf` - `terraform` block template syntax
												  ```yml
												  terraform {
												    required_version = "version_constraints" # Minimum and maximum version of Terraform
												    required_providers {
												        provider_name = {
												            source = "address_to_provider"
												              version = "version_constraints"
												              # =, >, <, =>, =<, ~>
												              # ~> only allows the right number to increment
												          }
												      }
												  }
												  ```
													- `terraform` block - Used for setting version of Terraform required, backend settings for state data, required provider plugins, provider metadata and experimental language features
													- `provider_name` - convention is to use the same as the provider_plugin, unless you're using multiple instances with different sources
												- `terraform.tf` - `terraform` block example
												  ```yml
												  terraform {
												    # Must be at least 1.0,
												    required_version = ">= 1.0, < 2.0"
												      required_providers {
												        aws = {
												            source = "hashicorp/aws"
												              # =. <, >, and ~>
												              # Looks for the latest 4.x
												              version = "~>4.0"
												          }
												      }
												  }
												  ```
												- By default if you don't specify a version, required version etc then it'll look for the latest version
												- Provider Block Syntax
													- Used to reference providers that we've specified in the Terraform block
													- `providers.tf`
													  ```yml
													  provider "provider_name" {
													    alias = "alias_name"
													      # Provider specific arguments
													  }
													  ```
													- `providers.tf` - example
													  
													  ```yml
													  provider "aws" {
													    alias = "west"
													      # Provider specific arguments
													  }
													  
													  resource "aws_instance" "web_server" {
													    provider = aws.west
													      # Resource specific arguments
													  }
													  ```
											- ### Specifying Required Providers
											  collapsed:: true
												- `terraform.tf`
												  ```yml
												  terraform {
												  required version = ">=1.0"
												  
												  required_providers {
												  aws = {
												  source = "hashicorp/aws"
												  version = "~> 4.0"
												  }
												  }
												  }
												  ```
												- Example using environment variables for sensitive data whilst using Terraform:
													- ```bash
													  export AWS_ACCESS_KEY_ID="awsaccesskey"
													  export AWS_SECRET_ACCESS_ID="awssecretkey"
													  export AWS_REGION="us-west-2"
													  terraform plan
													  ```
											- ### Adding the Random Provider
											  collapsed:: true
												- In this example we're going to use it to generate a random ID for our S3 bucket
												- https://registry.terraform/providers/hashicorp/random : Use Provider button
												- `terraform.tf`
												  ```yml
												  terraform {
												  required version = ">=1.0"
												  
												  required_providers {
												  aws = {
												  source = "hashicorp/aws"
												  version = "~> 4.0"
												  }
												  
												  random = {
												  source = "hashicorp/random"
												  version = "~> 3.5.0"
												  }
												  }
												  }
												  ```
												- Example usage of `random` in `locals.tf`
												  ```yml
												  resource "random_integer" "s3" {
												  min = 10000
												  max = 99999
												  }
												  ```
											- ### Creating ((64b81154-09ce-46c2-993a-0451497bcf3c)) and ((6463499e-42ab-4a58-8911-df6138dfee8f)) Resources
											  collapsed:: true
												- New data to add
													- ```yml
													  # S3 Resources
													  "aws_s3_bucket" # S3 bucket itself
													  "aws_s3_object" # Objects in the bucket
													  
													  # Instance access
													  "aws_iam_role" # Role for instances
													  "aws_iam_role_policy" # Role policy for S3 access
													  "aws_iam_instance_profile" # Instance profile
													  
													  # Load balancer access
													  "aws_s3_bucket_policy" # Grant load balancer principal access
													  "aws_elb_service_account" # Get load balancer principal id
													  ```
												- Example
													- `s3.tf`
													  
													  ```yml
													  # aws_s3_bucket
													  
													  # aws_s3_bucket_policy
													  
													  # aws_s3_object
													  ```
													- `instances.tf`
													  
													  ```yml
													  # aws_iam_role
													  
													  # aws_iam_role_policy
													  
													  # aws_iam_instance_profile
													  ```
													- `loadbalancer.tf`
													  ```yml
													  # aws_elb_service_account
													  ```
													- `locals.tf`
													  ```yml
													  locals {
													  common_tags = {
													  company = var.company
													  project = "${var.company}-${var.project}"
													  billing_code = var.billing_code
													  }
													  
													  s3_bucket_name = "globo-web-app-${random_integer.s3.result}"
													  }
													  ```
											- ### Viewing the Updated Configuration
											- ### Planning and Dependencies
											  collapsed:: true
												- Terraform Planning
													- 1. Refresh and inspect state
													- 2. Dependency graph
													- 3. Make list of additions, updates, and deletions
													- Parallel execution
												- Determining Dependencies
													- It automatically resolves and reorders tasks depending on what variables are needed
													- It infers the dependency tree implicitly
													- `depends_on` is a way to explicitly make some resources depend on others if implicitly doesn't work
												- Meta-argument
													- Definition: An argument in a resource or data source that instructs Terraform on managing the object and is not used by the provider to configure the target object.
											- ### Updating the Load Balancer and Instances
											  collapsed:: true
												- `instances.tf`
												  ```yml
												  
												  ```
												- `loadbalancer.tf`
												  ```yml
												  access_logs {
												  bucket = aws_s3_bucket.web_bucket.bucket
												  prefix = "alb-logs"
												  enabled = true
												  }
												  ```
											- ### Post Deployment Configuration
											  collapsed:: true
												- Configuration Option choices
													- Resources - there are MySQL providers, Kubernetes,
													- Pass data - a way to pass a Bash script are provided by all platforms
														- Terraform can't detect if this was successful other than the script returning a 1 or 0
													- Configuration managers (3rd-party software) e.g. ((6463499d-b2c2-41e3-9f06-5b5fd75a452b))
													- Provisioners - usually a bad idea
											- ### Provisioner Syntax
											  collapsed:: true
												- Defined in resource
												- Creation or destruction
												- Multiple provisioners
												- `null_resource`, or since v1.4 the built-in `terraform_data` resource
												- Failure options
												- Last Resort!
												- They're not creating objects in a form Terraform can check and validate
												- Provisioner types
													- File - creates
													- Local-exec - allows you to run a script on the local machine that is executing the Terraform run
													- Remote-exec - allows you to run a script on a remote system
												- Provisioner Example
													- These are nested inside resource blocks
													- ```yml
													  provisioner "file" {
													  connection {
													  type = "ssh"
													  user = "root"
													  private_key = var.private_key
													  host = self-public_ip
													  }
													  source = "/local/path/to/file.txt"
													  destination = "path/to/file.txt"
													  }
													  
													  provisioner "local-exec" {
													  command = "local command here"
													  }
													  
													  provisioner "remote-exec" {
													  connection {
													  
													  }
													  scripts = ["list", "of", "scripts"]
													  
													  }
													  ```
											- ### Updating the Startup Script
											- ### Formatting and Deploying the Updated Configuration
											  collapsed:: true
												- `terraform init` again - downloads the new provider plugin
													- `terraform validate` will show an error until you do so
												- `-replace` - marks a resource for replacement regardless of it's status
													- e.g. `terraform plan -replace aws_instance.nginx1 -replace aws_instance.nginx2 -out m6.tfplan`
										- ## Using Functions and Looping in Your Configuration
										  collapsed:: true
											- ### Overview
											  collapsed:: true
												- Loops and dynamic blocks
												- Using functions
												- Terraform console
											- ### Globomantics Update
											  collapsed:: true
												- Potential improvements
													- Dynamically increase instances
													- Use a template for startup script
													- Simplify networking input
													- Add consistent naming prefix
												- Deployment will be the same, just improve our IaC
											- ### Loops in Terraform
											  collapsed:: true
												- Looping Constructs
													- Count
														- 1, 2, 3
														- Integer input
													- For_each
														- Map or set input (key-value pairs)
													- Dynamic blocks
														- Map or set input
											- ### Count Syntax
											  collapsed:: true
												- `instances.tf`
												  ```yml
												  resource "aws_instance" "web_servers" {
												  count = 3
												  tags = {
												  Name = "globo-web-${count.index}"
												  
												  }
												  }
												  ```
												- Count References
													- ```yml
													  <resource_type>.<name_label>[element].<attribute>
													  aws_instance.web_servers[0].name # Single instance
													  aws_instance.web_servers[*].name # All instances i.e. returns a list
													  ```
											- ### For_each syntax
											  collapsed:: true
												- `s3.tf`
												  ```yml
												  resource "aws_s3_object" "taco_toppings" {
												    # It'll create two buckets, one for each topping
												    for_each = {
												        cheese = "cheese.png"
												          lettuce = "lettuce.png"
												      }
												      key = each.value
												      source = "./${each.value}"
												      tags = {
												        Name = each.key
												      }
												  }
												  ```
												- You can transform a list or tuple to a set using the `toset` function
												- Require a set in order to use
												- For_each References
													- ```yml
													  <resource_type>.<name_label>[key].<attribute>
													  aws_s3_object.taco_toppings["cheese"].id # Single instance
													  # Note: cannot use a star AKA splat syntax (*) because we're using a map, not a list
													  # We would need to use a for expression which will be covered later
													  ```
											- ### Looping Targets
											  collapsed:: true
												- ```yml
												  # Primary resources
												  "aws_subnets" # Count loop
												  "aws_instance" # Count loop
												  "aws_s3_bucket_object" # For_each loop
												  
												  # Impacted resources
												  "aws_route_table_association" # Count loop
												  "aws_lb_target_group_attachment" # Count loop
												  ```
											- ### Updating the VPC and Instances
											  collapsed:: true
												- `variables.tf`
												  ```yml
												  variable "vpc_public_subnet_count" {
												  type = number
												  description = "Number of public subnets to create."
												  default = 2
												  }
												  ```
												- `network.tf`
													- Old
													  
													  ```yml
													  resource "aws_subnet" "public_subnet2" {
													  cidr_block              = var.vpc_public_subnet1_cidr_block
													  vpc_id                  = aws_vpc.app.id
													  map_public_ip_on_launch = var.map_public_ip_on_launch
													  availability_zone = data.aws_availability_zones.available.names[1]
													  
													  tags = local.common_tags
													  }
													  ```
													- New
													  ```yml
													  resource "aws_subnet" "public_subnets" {
													  count = var.vpc_public_subnet_count
													  cidr_block              = var.vpc_public_subnets_cidr_block[count.index]
													  vpc_id                  = aws_vpc.app.id
													  map_public_ip_on_launch = var.map_public_ip_on_launch
													  availability_zone = data.aws_availability_zones.available.names[count.index]
													  
													  tags = local.common_tags
													  }
													  ```
												- Updating route table
													- Old
													  ```yml
													  resource "aws_route_table_association" "app_subnet1" {
													  subnet_id		= aws_subnet.public_subnet1.id
													  route_table_id	= aws_route_table.app.id
													  }
													  ```
													- New
													  ```yml
													  resource "aws_route_table_association" "app_subnets" {
													  count = var.vpc_public_subnet_count
													  subnet_id		= aws_subnet.public_subnets[count.index].id
													  route_table_id	= aws_route_table.app.id
													  }
													  ```
												- Do the same for instances, and load balancer group attachment
											- ### Updating the S3 Bucket Objects
											- ### Path Expressions
											  collapsed:: true
												- 3 different that you can access
													- `path.root`- directory of the root module i.e. the configuration we're working on
													- `path.module` - resolves to teh path of the module you're using
													- `path.cwd` - current working directory. Usually the same as `path.root`
												- This then allows us to use as a variable (example)
													- ```yml
													  source = "${path.root}/${each.value}"
													  ```
											- ### Terraform Expressions and Functions
											  collapsed:: true
												- Supports
													- Interpolation and heredoc
													- Arithmetic and logical operators
													- Conditional expressions (if)
													- For expressions
												- Terraform Functions
													- They're built-in natively
													- Syntax: `Func_name(arg1, arg2, arg3, ...)`
													- Testing functions
														- `terraform plan`
														- `terraform console` - much more efficient
													- Several broad categories which covers the 100+ functions available
											- ### Common Function Categories
											  collapsed:: true
												- Numeric
												  e.g. `min(42, 13, 7)`
												- String
												  e.g. `lower("TACOS")`
												- Collection
												  e.g. `merge(map1, map2)`
												- IP network
												  e.g. `cidrsubnet()`
												- Filesystem
												  e.g. `file(path)`
												- Type conversion
												  e.g. `toset()`
											- ### Functions for the Configuration
											  collapsed:: true
												- ```yml
												  # Startup script
												  templatefile(file_location, { map of variables })
												  # Extract subnet address from VPC CIDR
												  cidrsubnet(cidr_range, subnet bits to add, network number)
												  # Add tags to common tags
												  merge(common_tags, { map of additional tags })
												  # S3 bucket name
												  lower("bucket name")
												  ```
											- ### Testing Functions with Terraform Console
											  collapsed:: true
												- `terraform console`
													- Starts an interactive environment where we can test different functions and make use of variables values, resources and data source values within our functions.
												- Examples
													- ```yml
													  min(42,5,16)
													  lower("TACOCAT")
													  ```
												-
											- ### Using the Templatefile Function
											  collapsed:: true
												- `/templates/startup_script.tpl`
												  
												  ```yml
												  #! /bin/bash
												  
												  sudo amazon-linux extras install -y nginx1
												  sudo service nginx start
												  # etc
												  ```
												- `instances.tf`
												  ```yml
												  inside a resource {
												  user_data = templatefile("${path.module}/templates/startup_script.tpl", {
												  s3_bucket_name = aws_s3_bucket.web_bucket.id
												  })
												  }
												  ```
												- To test this
													- ```yml
													  terraform console templatefile("${path.module}/templates/startup_script.tpl", {
													  s3_bucket_name = aws_s3_bucket.web_bucket.id
													  }
													  ```
											- ### Using Cidrsubnet Function
											- ### Adding a Naming RP Prefix
											  collapsed:: true
												- `variables.tf`
												  
												  ```yml
												  variable "naming_prefix" {
												  type = string
												  description = "Naming prefix for all resources"
												  default = "globo-web-app"
												  }
												  
												  variable "environment" {
												  type = string
												  description = "Environment for the resources"
												  default = "dev"
												  }
												  ```
												- `locals.tf`
												  ```yml
												  locals {
												  naming_prefix = "${var.naming_prefix}-${var.environment}"
												  }
												  ```
												- ```yml
												  terraform console
												  merge(local.common_tags, { Name = "${local.naming_prefix}-vpc"})
												  ```
											- ### Validating and Deploying the Updated Configuration
											  collapsed:: true
												- `terraform validate`
												- `terraform plan -out m7.tfplan`
												- `terraform apply "m7.tfplan"`
										- ## Using a Module for Common Configurations
										  collapsed:: true
											- ### Overview
												- A common feature of programming languages is to import modules or libraries for common tasks, data structures or functions
												- Modules are Terraform's equivalent to this
												- What is a module?
												- Using existing modules
												- Creating new modules
											- ### Terraform Modules
												- They can have:
													- Input variables
													- Resources and data sources
													- Output values
												- A module is a set of `.tf` or `.tf.json` files in a directory
												- Main config you're working with is called the **root module** and it can invoke other modules to create resources
												- You can have a tree of child modules which invoke other child modules
												- A parent module can invoke the child module multiple times either by
													- Repeating the `module` block
													- Using the `count` meta arguments
													- Using `for_each` meta arguments
											- ### Globomantics Updates
											- ### Module Structure
											- ### Module Syntax
											- ### Module Scoping
											- ### Adding the VPC Module
											- ### For Expressions
											- ### Using a For Expression
											- ### Creating the S3 Module
											- ### Adding the S3 Module
											- ### Validating and Applying the Configuration
											- ### Moving Resource Options
											- ### Fixing a Failed Run
									- # Terraform Deep Dive
									  id:: 652909e9-8763-44ee-ad4b-d9a5103b4ad6
									- # Getting Started with Terraform Cloud
									  id:: 652909ee-7bdf-42db-9b2c-d7212654901a
								-
							- [Managing Infrastructure with Terraform | Pluralsight](https://app.pluralsight.com/paths/skill/managing-infrastructure-with-terraform)
							  collapsed:: true
								- Courses
								  collapsed:: true
									- _Core Terraform Functionality_
									  collapsed:: true
										- ((652909e6-133d-41fc-9e32-f216c04abfd1))
										- ((652909e9-8763-44ee-ad4b-d9a5103b4ad6))
										- ((652909ee-7bdf-42db-9b2c-d7212654901a))
									- Implementing Terraform with Cloud Providers
									  collapsed:: true
										- Implementing Terraform on Microsoft Azure
										- Implementing Terraform with AWS
										- Implementing Terraform with Google Cloud Platform
							- Terraform: Up & Running (3rd ed)
							  Calibre
							- [Serverless Land](https://serverlessland.com)
							  id:: 663a5790-1a97-4be5-8790-6eed8c4cc3f5
						- Completed learning resources (references)
					- [Learning Resources]
						- ((093d7ed4-60df-4011-b09e-cfb4920b19a3))
							- {{embed ((093d7ed4-60df-4011-b09e-cfb4920b19a3))}}
						- https://www.checkov.io/
							- Great tol for checking if your Terraform is following best practices
						- https://blog.gruntwork.io/why-we-use-terraform-and-not-chef-puppet-ansible-saltstack-or-cloudformation-7989dad2865c
						- Demystifying ((638d061d-e696-4f04-933c-35f8836e125d)) State talk
						  collapsed:: true
							- What is Terraform
								- `*.tf` configuration files written in Hashicorp Configuration Language (HCL)
								- Structured in to modules with inputs and outputs
								- Declarative not Imperative
									- Describes end state of resources, not how to get there
									- No loops, functions, etc
							- What is Terraform state
								- JSON file (`terraform.tfstate`)
								- Created and managed _exclusively_ by Terraform. Don't change by hand
								- Describes the "real" resources managed by the configuration
							- ## Local State
								- Default and most basic state "backend"
									- No special config required
								- Stored locally
								- Not shared - collaboration is challenging
								- Basically just for testing
								- **Demo**
									- `lock` file which works like npm or yarn lock file
									- Using a sandbox AWS account
							- ## Remote State
								- State file stored remotely e.g. S3 bucket
								- Backend config is provider-specific
								- Can be easily shared for collaboration this way
								- Gives state locking - prevents simultaneous state writes and state corruption
								- **Demo**
									- `terraform init` if you change or add a `backend` section in the `terraform {}` section of the `main.tf` file
									- You can delete `terraform.tfstate` file whenever because in the `/.terraform/` folder it has the real state? you have the state file hosted remotely
									- S3 buckets have versioning which is very useful to revert to an older state by using an older config
							- ## Managing Multiple Environments
								- nest
							- ## State Manipulation
							- ## Best Practices
							- Questions
								- Can Terraform do things like create new users on an EC2, change the SSH config
						- [GitHub - futurice/terraform-examples: Terraform samples for all the major clouds you can copy and paste. The future, co-created.](https://github.com/futurice/terraform-examples)
						- https://blog.gruntwork.io/an-introduction-to-terraform-f17df9c6d180
						- [Use Terraform for provisioning correct infrastructure, Ansible for configuring servers](https://opencredo.com/kubernetes-aws-terraform-ansible-1/)
					- Related: ((650bee1d-9820-4336-ac32-a3e59ac5fc83))
				- [OpenTofu](https://opentofu.org/)
				  id:: 650bee1d-9820-4336-ac32-a3e59ac5fc83
				  collapsed:: true
				  ((638d061d-e696-4f04-933c-35f8836e125d)) FOSS fork
					- [GitHub - opentofu/opentofu: OpenTofu lets you declaratively manage your cloud infrastructure.](https://github.com/opentofu/opentofu)
					-
				- [SST](https://sst.dev/)
				  id:: 6491f0b0-a218-4fb2-8037-03ca593c3125
				  collapsed:: true
					- [GitHub - serverless-stack/sst: 💥 SST makes it easy to build full-stack serverless apps.](https://github.com/serverless-stack/sst)
					- TypeScript-based control over all sorts of AWS services
					- Support for Next.js, Astro and SvelteKit
					- [SST in 100 seconds - YouTube](https://youtu.be/JY_d0vf-rfw)
					  collapsed:: true
						- {{video https://youtu.be/JY_d0vf-rfw}}
				- See [Digger](https://workflowy.com/#/e26075958ee2) (Terraform-based PaaS)
				- ((6463499e-dc33-4af7-bbb7-33338a8a325b))
				- OpenStack Heat
			- _Configuration Management_
			  id:: 6463499d-56d9-4954-b881-ca482d664d19
			  designed to install and manage software on existing servers.
				- [Ansible](https://www.ansible.com/)
				  id:: 6463499d-b2c2-41e3-9f06-5b5fd75a452b
				  collapsed:: true
					- Pros/Cons
						- Pros
							-
						- Cons
							-
						- Unclear
							- Factor 1
							  collapsed:: true
								- Pros
									-
								- Cons
									-
						- Comparisons
							- ((6463499d-b2c2-41e3-9f06-5b5fd75a452b)) vs ((644c0b9b-9c03-42c8-99b7-f9dfb8282bbb)) : ((652d41e6-e0d1-4b9c-be90-c959bd89a75d))
							  collapsed:: true
								- For ((6463499d-b2c2-41e3-9f06-5b5fd75a452b))
									- It's a specialised tool for this purpose, whereas ((644c0b9b-9c03-42c8-99b7-f9dfb8282bbb)) can be used for many purposes
									- Idempotency
									  i.e. it'll never do a step if it's already done
										- The quality whereby the took ensures that it can be safely re-run any number of times, and at each run it will either come to the desired state, or remain there, or at least move closer to it in a //convergent// manner.
									- Declarative rather than imperative
									- Re-distributable, re-usable packages.
										- Ruby has gems, Perl has CPAN, Node has npm, Java has maven - and all languages these have their own conventions of how reusable source code must be packaged and shared with the world.
										  
										  Shell Scripts don't.
										  
										  Chef has cookbooks that follow conventions and can be imported much the same way you import a gem into your ruby application to give your application some new ability. Puppet has puppetforge and it's modules, Juju has charms (they are pretty close to shell scripts so you might be interested). Ansible has playbooks in [Ansible Galaxy](https://galaxy.ansible.com)
								- For ((644c0b9b-9c03-42c8-99b7-f9dfb8282bbb)) : ((652d41e6-e0d1-4b9c-be90-c959bd89a75d))
									- Comes with the OS, nothing extra needs to be installed
									- One-click run
								- Code examples
								  collapsed:: true
									- [1](https://hvops.com/articles/ansible-vs-shell-scripts/)
									  collapsed:: true
										- ```bash
										  # Install the PGP key
										  gpg --keyserver keyserver.ubuntu.com --recv-keys 561F9B9CAC40B2F7
										  gpg --armor --export 561F9B9CAC40B2F7 | apt-key add -
										  
										  # Install https support for apt
										  apt-get install apt-transport-https -y
										  
										  # Add the passenger apt repository
										  echo "deb https://oss-binaries.phusionpassenger.com/apt/passenger raring main" > /etc/apt/sources.list.d/passenger.list
										  chown root: /etc/apt/sources.list.d/passenger.list
										  chmod 600 /etc/apt/sources.list.d/passenger.list
										  
										  # Update the apt cache so we can use the new repo
										  apt-get update
										  
										  # Install nginx
										  apt-get install nginx-full passenger -y
										  
										  # Set up passenger in the nginx configuration
										  sed -i "s/# passenger_root/passenger_root/" /etc/nginx/nginx.conf
										  sed -i "s/# passenger_ruby/passenger_ruby/" /etc/nginx/nginx.conf
										  
										  # Start nginx
										  service nginx restart
										  ```
										- ```yaml
										  ---
										  - hosts: all
										    tasks:
										      - name: Ensure the PGP key is installed
										        apt_key: >
										          state=present
										          id=AC40B2F7
										          url="http://keyserver.ubuntu.com/pks/lookup?op=get&fingerprint=on&search=0x561F9B9CAC40B2F7"
										  
										      - name: Ensure https support for apt is installed
										        apt: >
										          state=present
										          pkg=apt-transport-https
										  
										      - name: Ensure the passenger apt repository is added
										        apt_repository: >
										          state=present
										          repo='deb https://oss-binaries.phusionpassenger.com/apt/passenger raring main'
										  
										      - name: Ensure nginx is installed
										        apt: >
										          state=present
										          pkg=nginx-full
										  
										      - name: Ensure passenger is installed
										        apt: >
										          state=present
										          pkg=passenger
										          update_cache=yes
										  
										      - name: Ensure the nginx configuration file is set
										        copy: >
										          src=/app/config/nginx.conf
										          dest=/etc/nginx/nginx.conf
										  
										      - name: Ensure nginx is running
										        service: >
										          name=nginx
										          state=started
										  ```
									- 1 liners
										- ```bash
										  sudo apt install nginx -y
										  ```
										- Becomes either:
											- ```yml
											  - shell: apt-get install nginx -y
											  ```
											- Best practice:
											  ```yaml
											  - apt: pkg=nginx state=present
											  ```
							- ((6463499d-b2c2-41e3-9f06-5b5fd75a452b)) vs [[Docker]]
							  id:: 6808efda-33f4-42ca-82f6-a159691e835f
								- For ((6463499d-b2c2-41e3-9f06-5b5fd75a452b))
									-
								- For [[Docker]]
									- Can be more easily tested since instead of spinning up a new VPS or VM you just destroy and recreate a container
					- [GitHub - ansible/ansible](https://github.com/ansible/ansible)
					  Ansible is a radically simple IT automation platform that makes your applications and systems easier to deploy and maintain. Automate everything from code deployment to network configuration to cloud management, in a language that approaches plain English, using SSH, with no agents to install on remote systems.
					- [Documentation](https://docs.ansible.com)
						- [Ansible modules and plugins](https://docs.ansible.com/ansible/latest/module_plugin_guide/index.html)
						  id:: 652db617-6a75-411c-b2e9-ffd0ec19670e
						  collapsed:: true
							- Notable
								- [ansible.builtin.command module – Execute commands on targets — Ansible Documentation](https://docs.ansible.com/ansible/latest/modules/command_module.html)
								-
								- [dnf_module](https://docs.ansible.com/ansible/latest/modules/dnf_module.html)
								  id:: 654bc0c3-2467-4b85-be59-70664da8c90c
								  DNF package manager
								- [ansible.builtin.git module – Deploy software (or files) from git checkouts — Ansible Documentation](https://docs.ansible.com/ansible/latest/modules/git_module.html)
								- [ansible.builtin.systemd_service](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/systemd_service_module.html)
								  id:: 654bc29d-f845-4ef7-9133-48cbfdba699d
								- [ansible.builtin.file module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file_module.html)
								  id:: 654bc2a7-59dc-41bf-84cf-a12d11091985
								  Manage files and file properties
								- [community.docker.docker_image module – Manage docker images — Ansible Documentation](https://docs.ansible.com/ansible/latest/collections/community/docker/docker_image_module.html)
								-
						- [Ansible playbooks — Ansible Documentation](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_intro.html)
						- Example ((644c0b9b-9c03-42c8-99b7-f9dfb8282bbb)) script converted to ((6463499d-b2c2-41e3-9f06-5b5fd75a452b)) playbook
						  collapsed:: true
							- ((644c0b9b-9c03-42c8-99b7-f9dfb8282bbb)) version:
								- ```bash
								  yum install -y yum-utils
								  yum-config-manager --add-repo https://download.docker.com/docker.repo
								  yum install -y docker-ce docker-ce-cli
								  systemctl enable docker
								  systemctl start docker
								  systemctl status docker
								  sudo mkdir /etc/systemd/system
								  sudo nano /etc/systemd/system/proxy.conf
								  sudo systemctl daemon-reload
								  sudo systemctl restart docker
								  docker build -t nitro-nest1 .
								  cat ~/.aws/credentials
								  ```
							- ((6463499d-b2c2-41e3-9f06-5b5fd75a452b)) version:
								- ```yml
								  ---
								  - name: Install Docker and configure proxy
								    hosts: your_target_host
								    become: yes # Ensure privilege escalation to execute commands as sudo
								  
								    tasks:
								      - name: Install yum-utils
								        yum:
								          name: yum-utils
								          state: present
								  
								      - name: Add Docker repository
								        command: yum-config-manager --add-repo https://download.docker.com/docker.repo
								        register: add_repo_result
								  
								      - name: Install Docker packages
								        dnf:
								          name:
								            - docker-ce
								            - docker-ce-cli
								          state: present
								        when: "'Added new repo' in add_repo_result.stdout"
								  
								      - name: Enable and start Docker
								        systemd:
								          name: docker
								          enabled: yes
								          state: started
								  
								      - name: Create a systemd service for proxy.conf
								        file:
								          path: /etc/systemd/system/proxy.conf
								          state: touch
								  
								      - name: Reload systemd
								        systemd:
								          state: reloaded
								  
								      - name: Restart Docker
								        systemd:
								          name: docker
								          state: restarted
								  
								      - name: Build Docker image
								        command: docker build -t nitro-nest1 .
								        args:
								          chdir: /path/to/your/dockerfile/directory
								        become_user: your_docker_user
								  
								      - name: Display AWS credentials
								        command: cat ~/.aws/credentials
								        changed_when: false
								  ```
									- Uses these modules:
										- ((654bc0c3-2467-4b85-be59-70664da8c90c))
										- ((654bc29d-f845-4ef7-9133-48cbfdba699d))
										- ((654bc2a7-59dc-41bf-84cf-a12d11091985))
						- Installation
							- Kubuntu
								- ```bash
								  sudo apt install python3-pip
								  pipx install ansible
								  sudo apt install ansible-core
								  ```
							- CentOS
								- ```bash
								  python3 -m pip install --user ansible
								  ```
						- Cheatsheet
							- ```yaml
							  - name: Setup dev env
							    hosts: localhost
							    connection: local
							    gather_facts: yes
							  
							    environment:
							        OPENSSL_CONF: ~/openssl.cnf
							    vars:
							        CSU_user: testuser
							      aws_account_id: 91331141
							  
							  - name: Push the image
							    command: docker push {{ aws_account_id }}.dkr.ecr.eu-west-1.amazonaws.com/nitro-nest1:latest
							  ```
				- Puppet
				- Chef
				- SaltStack
				- [pyinfra](https://pyinfra.com/)
				  collapsed:: true
					- [GitHub - pyinfra-dev/pyinfra: pyinfra turns Python code into shell commands and runs them on your servers. Execute ad-hoc commands and write declarative operations. Target SSH servers, local machine and Docker containers. Fast and scales from one server to thousands.](https://github.com/pyinfra-dev/pyinfra)
					-
			- _Server Templating Tools_
			  An alternative to configuration management that has been growing in popularity recently are server templating tools such as Docker, Packer, and Vagrant. Instead of launching a bunch of servers and configuring them by running the same code on each one, the idea behind server templating tools is to create an image of a server that captures a fully self-contained “snapshot” of the operating system, the software, the files, and all other relevant details.
				- _Virtual machine-based_
					- Vagrant
					  collapsed:: true
						- Docker Containers are built from images, with some additional configuration. You can also create images from other images. Let’s say you want to use the Ubuntu 14.04 image. You also want to use Apache and PHP. You could use the Ubuntu image and then install Apache and PHP. This way you can create another image and share this image with others. Images are like blueprints for containers. Containers are built from those images.
							- Compared with Vagrant, where you have a base OS which is Ubuntu, then using a tool like Puppet, you then instruct it to install Apache and PHP. You then ‘vagrant up’, and you’re ready to go with your local development.
					- Packer
					- [Microsandbox](https://github.com/microsandbox/microsandbox): Virtual Machines that feel and perform like containers
						- [GitHub - microsandbox/microsandbox: Self-Hosted Plaform for Secure Execution of Untrusted User/AI Code](https://github.com/microsandbox/microsandbox)
				- _Container-based_
					- See [Docker](https://workflowy.com/#/6983127b69f3)
					  #Infrastructure-Containers
			- Comparison
				- ![image.png](../assets/image_1687285917612_0.png)
			- Related: ((653a9ddb-ae82-4c2f-82ea-9c9e8f266c59))
		- CI/CD
		  id:: 6463499d-76db-4797-a83f-4b9b7439743a
		  collapsed:: true
		  AKA Continuous Integration / Continuous Delivery
			- Version Control via Git
			  See ((635fc546-d883-4e58-89d4-6c1069039fb6))
			- CI
			  id:: 63904f39-e11b-4b28-9065-ce6396f67c4c
			  collapsed:: true
			  AKA Continuous Integration / AKA Build server | Detects changes on Version Control, compiles a build
				- Why
				  collapsed:: true
					-
					- Why aren't the developers building the project on their local machines, or are they? Because with complex software, amazingly many things can go wrong when just "compiling through". problems I have actually encountered:
						- incomplete dependency checks of different kinds, resulting in binaries not being updated.
						- Publish commands failing silently, the error message in the log ignored.
						- Build including local sources not yet commited to source control (fortunately, no "damn customers" message boxes yet..).
						- When trying to avoid above problem by building from another folder, some files picked from the wrong folder.
						- Target folder where binaries are aggregated contains additional stale developer files that shoulkd not be included in release
				- Open-source
					- [GitLab CI/CD](https://about.gitlab.com/solutions/continuous-integration/)
					  id:: 6576c4da-6f96-4e61-86e1-8987313bd78a
					  collapsed:: true
						- GitLab CI Multi-Runner
						- [Auto DevOps | GitLab Docs](https://gitlab.com/help/topics/autodevops/index.md)
						- [GitLab Pipelines](https://docs.gitlab.com/ci/pipelines/)
							- Types
								- Branch pipeline
									- Your pipeline can run every time you commit changes to a branch.
									- e.g. runs when a new feature branch pull request gets merged to Develop branch
								- Tag pipeline
									- Runs every time you create or push a new tag
								- Merge request pipeline
							- Example `.gitlab-ci.yml`
							  collapsed:: true
								- Four example jobs
								  ```yaml
								  build-job:
								  stage: build
								  script:
								  - echo "Hello, $GITLAB_USER_LOGIN!"
								  
								  test-job1:
								  stage: test
								  script:
								  - echo "This job tests something"
								  
								  test-job2:
								  stage: test
								  script:
								  - echo "This job tests something, but takes more time than test-job1."
								  - echo "After the echo commands complete, it runs the sleep command for 20 seconds"
								  - echo "which simulates a test that runs 20 seconds longer than test-job1"
								  - sleep 20
								  
								  deploy-prod:
								  stage: deploy
								  script:
								  - echo "This job deploys something from the $CI_COMMIT_BRANCH branch."
								  environment: production
								  ```
								- Only trigger on pushes to `develop` branch
									- ```yaml
									  rules:
									  - if: '$CI_COMMIT_BRANCH == "develop"'
									  when: always
									  ```
									- Successor to `only` keyword which is getting deprecated
								- Other project example
								  collapsed:: true
									- ```yaml
									  default:
									  image: python:3.13.1
									  
									  stages:
									  - lint
									  - test
									  - build-job
									  
									  variables:
									  ROOT_DIR: src
									  BACKEND_DIR: ${ROOT_DIR}/backend
									  
									  lint-backend:
									  variables:
									  GIT_STRATEGY: clone
									  GIT_SUBMODULE_STRATEGY: recursive
									  stage: lint
									  before_script:
									  - echo 1
									  - echo 2
									  script:
									  - echo 3
									  - echo 4
									  
									  lint-frontend:
									  image: docker:24.0.5
									  stage: lint
									  script:
									  - echo 5
									  ```
							- [Predefined variables](https://docs.gitlab.com/ci/variables/predefined_variables/)
							- [YAML reference](https://docs.gitlab.com/ci/yaml/)
							- Stages describes the sequential execution of jobs. Multiple jobs can be in each stage. If there are runners available, jobs in a single stage run in parallel
							- Tips
								- Use the [`needs` keyword](https://docs.gitlab.com/ci/yaml/#needs) to run jobs out of stage order, to increase pipeline speed and efficiency
								- Use the `rules` keyword to specify when to run or skip jobs. The only and except legacy keywords are still supported, but can’t be used with rules in the same job.
								- Keep information across jobs and stages persistent in a pipeline with cache and artifacts. These keywords are ways to store dependencies and job output, even when using ephemeral runners for each job.
								- Use the `default` keyword to specify additional configurations that are applied to all jobs. This keyword is often used to define before_script and after_script sections that should run on every job.
					- [CircleCI](https://circleci.com/)
					  id:: 63904f39-e211-423b-aeb4-2374897398df
					- [Concourse CI](https://concourse-ci.org/)
					  collapsed:: true
						- [GitHub - concourse/concourse: Concourse is a container-based continuous thing-doer written in Go.](https://github.com/concourse/concourse)
						-
					- [Jenkins](https://www.jenkins.io/)
					  id:: 6463499d-7235-4155-8c9d-78c9cf0e7367
					  collapsed:: true
					  Monitors executions of repeated jobs, such as building a software project or jobs run by cron
						- Pros/Cons
							- Pros
								-
							- Cons
								- https://twitchard.github.io/posts/2019-06-21-life-is-too-short-for-jenkins.html
								- [Too complicated according to devs in 2024](https://www.reddit.com/r/webdev/comments/1chjuf7/what_is_considered_the_current_best_cicd_tool_to/)
							- Unclear
							- Comparisons
						- Currently using Jenkins but am disappointed with the lack of coherency between plug-ins for configuring pipelines (ala your example of the manual step with the Build Pipeline Plugin.) Very frustrating.
						- I have used the Promoted Builds Plugin as a way to model a build lifecycle including “manual” steps (like blessing a build for production) which can easily be set via its REST API, which kicks off the next step in the process. This makes integrating with external systems very easy.
						- Selenium on Jenkins
							- https://wiki.jenkins.io/display/JENKINS/Selenium+Plugin
							- https://www.blazemeter.com/blog/headless-execution-selenium-tests-jenkins
							- https://saucelabs.com/resources/articles/selenium-jenkins-how-to-do-it-yourself-and-sauce-labs-advantage
						- left out two key things:
							- 1. Pre-commit builds – if a developer can check in code that breaks the central build for everyone else, then your pipeline is not truly “continuous”.
							- 2. If your individual pipeline tasks are tightly bound to the structure of the pipeline itself, then you can’t “orchestrate” pipelines… another crucial feature of Continuous Delivery. For example, can the tasks (such as build project x with Maven) be re-used in other pipelines without duplication? How easy is it to re-arrange the pipeline, branch off to run additional test/deployment tasks and then re-join for a final promotion/deployment step?
							- Point 1. is solved by TeamCity or using Jenkins in combination with Gerrit. Don’t know what Go and Bamboo can achieve in this space, and would be interested to find out.
							- Point 2. is solved by the very new “Build Flow Plugin” in Jenkins, which allows you to let go of Jenkins’ notion of upstream/downstream build jobs, and orchestrate the whole pipeline from a single Groovy-like DSL. Again, I don’t have first hand experience or doing this in Go or Bamboo, but I’m pretty sure this is impossible in TeamCity, where each step/project can only use the output of a single preceding step/project.
						- https://wiki.jenkins.io/display/JENKINS/Job+DSL+Plugin
						- Blue Ocean - new UI plugin
						  https://jenkins.io/projects/blueocean/
					- [Tekton](https://tekton.dev/)
					  id:: 6633312b-0785-4e6b-a86d-edbc49b69b5e
					  collapsed:: true
						- [GitHub - tektoncd/pipeline: A cloud-native Pipeline resource.](https://github.com/tektoncd/pipeline)
						-
					- [BuildBot](https://buildbot.net/)
					- [PHPCI](https://www.phptesting.org/)
					- [Flox | Your dev environment, everywhere](https://flox.dev/)
					  Nix-based
					- _Docker-based_
						- [Drone](https://github.com/drone/drone)
						  collapsed:: true
						  Docker containers for builds
							- d
							- [source] http://rancher.com/building-super-fast-docker-cicd-pipeline-rancher-droneci/
							- Cons
								- Hashicorp Vault integration requires enterprise
								- http://docs.drone.io/vault-secrets/
							- Drone runs on your Rancher infrastructure much like a tool like Jenkins would, but, unlike Jenkins, Drone is Docker-native – every part of your build process is a container. Running on your infrastructure speeds up the build process, since base images can be shared across builds or even projects. You can also avoid a LOT of latency if you push to a Docker registry that is on your own infrastructure such as ECR for AWS.
							- Drone being Docker-native removes a lot of configuration friction as well. Anyone who’s had to configure Jenkins knows that this is a big plus.
							- A standard Drone deployment does something like this:
							- Run a container to notify Slack that a build has started
							- Configure any base image for your “test” container, code gets injected and tests run in the container
							- Run a container that builds and pushes your production image (to Docker Hub, AWS ECR, etc)
							- Run a container that tells Rancher to upgrade a service
							- Run a container to notify Slack that a build has completed/failed
							- A .drone.yml file looks strikingly similar to a docker-compose.yml file – just a list of containers. Since each step has a container dedicated to that task, configuration of that step is usually very simple.
					- [Comparison Jenkins vs GitLab CE](https://www.inovex.de/blog/modern-cicd-with-jenkins-2-and-gitlab-ci-comparison) - hard to say
				- SaaS
					- Meta
					  collapsed:: true
						- hosted CI providers emerged that try to capture this market and address some of the pain points that these small teams are experiencing:
							- Remove the hassle of having to run and maintain your own CI infrastructure.
							- Tools that try to speed up test runs by splitting them up to run in parallel.
							- Seamless push to productions platforms like Heroku, Amazon EC2 and Google App Engine.
					- [GitHub Actions](https://github.com/features/actions)
					  id:: 63a04b77-2247-4d65-87c2-8bad97d831fd
					  collapsed:: true
						- Pros/Cons
							- Cons
								- [The Pain That Is GitHub Actions | Hacker News](https://news.ycombinator.com/item?id=43419701)
								-
						- My templates
							- `https://github.com/PercaysoRecruitment/pe3-soc-cohort13-ajvsol`
								- `.github/workflows/tests.yml`
								  collapsed:: true
									- ```yml
									  name: Tests CI
									  
									  on: [push, pull_request]
									  
									  jobs:
									    test:
									      runs-on: ubuntu-latest
									      steps:
									        - uses: actions/checkout@v2
									        - name: Test using Node.js
									          uses: actions/setup-node@v1
									          with:
									            node-version: "18"
									        - run: npm install
									        - run: npm run test2
									  
									        - name: Tests ✅
									          if: ${{ success() }}
									          run: |
									            curl --request POST \
									            --url https://api.github.com/repos/${{ github.repository }}/statuses/${{ github.sha }} \
									            --header 'authorization: Bearer ${{ secrets.GITHUB_TOKEN }}' \
									            --header 'content-type: application/json' \
									            --data '{
									              "context": "tests",
									              "state": "success",
									              "description": "Tests passed",
									              "target_url": "https://github.com/${{ github.repository }}/actions/runs/${{ github.run_id }}"
									            }'
									  
									        - name: Tests 🚨
									          if: ${{ failure() }}
									          run: |
									            curl --request POST \
									            --url https://api.github.com/repos/${{ github.repository }}/statuses/${{ github.sha }} \
									            --header 'authorization: Bearer ${{ secrets.GITHUB_TOKEN }}' \
									            --header 'content-type: application/json' \
									            --data '{
									              "context": "tests",
									              "state": "failure",
									              "description": "Tests failed",
									              "target_url": "https://github.com/${{ github.repository }}/actions/runs/${{ github.run_id }}"
									            }'
									  ```
						- [Quickstart for GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/quickstart)
						- [Demo](https://github.com/tfrommen/unit-test-examples)
						  `/home/boss/Documents/Git/1MY REPOS/github-actions-demo/unit-test-examples`
							- `on: [push]` = action will trigger on `git push`
						- [Continuous Integration Pipelines with GitHub Actions for (React) Developers](https://profy.dev/article/continuous-integration-with-github-actions)
						- # Ecosystem
							- [Install Actioneer on Linux | Flathub](https://flathub.org/en/apps/me.spaceinbox.actioneer)
								- [GitHub - makoni/actioneer-gtk](https://github.com/makoni/actioneer-gtk)
							- [GitHub - nektos/act: Run your GitHub Actions locally 🚀](https://github.com/nektos/act)
								- Pros
									- **Fast Feedback** - Rather than having to commit/push every time you want to test out the changes you are making to your `.github/workflows/` files (or for any changes to embedded GitHub actions), you can use `act` to run the actions locally. The [environment variables](https://help.github.com/en/actions/configuring-and-managing-workflows/using-environment-variables#default-environment-variables) and [filesystem](https://help.github.com/en/actions/reference/virtual-environments-for-github-hosted-runners#filesystems-on-github-hosted-runners) are all configured to match what GitHub provides.
									- **Local Task Runner** - I love [make](https://en.wikipedia.org/wiki/Make_(software)). However, I also hate repeating myself. With `act`, you can use the GitHub Actions defined in your `.github/workflows/` to replace your `Makefile`!
								- 2022 complaint - But just one word of warning: when you run `act` with no arguments, what does it do? Displays usage? Nope -- it runs all workflows defined in the repo, all at once in parallel!
							- [GitHub - mxschmitt/action-tmate: Debug your GitHub Actions via SSH by using tmate to get access to the runner system itself.](https://github.com/mxschmitt/action-tmate)
							-
						- Related: ((65bd5b76-07e5-4bbc-9b4f-6b0651a16e89))
					- [Bamboo](https://www.atlassian.com/software/bamboo)
					  id:: 646349e5-298b-4ca3-989e-063392d39b0a
					  collapsed:: true
					  From [Atlassian](https://www.atlassian.com/)
						- Documentation
							- Troubleshooting
								- It has a security feature which blanks out anything with a secret/key/password in it with asterisks to prevent accidental disclosure in logs. [[2023-12-13 Wednesday]] ran into this issue when trying to `printenv` AWS login keys
					- _AWS services_
					  id:: 63a04d0d-b4cf-4754-ba57-5f0ebb21e063
						- ![image.png](../assets/image_1671450379506_0.png)
						- 1. Source
							- ((64b7f676-aaa5-4351-aeee-dcc14b014bae))
						- 2. Artifacts
							- ((64b7f64c-8e70-4bf4-8680-2795cb1cc84f))
						- 3. Build
							- ((64b7f66c-86f0-443a-b53b-190d004e78e7))
							  collapsed:: true
						- Related: ((63904f39-62e0-44d6-bd61-d5a6e98444a4)) : ((63a04cfd-4c07-4f11-be92-fa0f531c527b))
					- [Azure Pipelines](https://azure.microsoft.com/en-us/products/devops/pipelines/) for Azure DevOps
					- [Codeship](https://codeship.com)
					- [Travis-CI](https://www.travis-ci.com/)
					  id:: 6576c508-19a1-4a79-b53f-aac0109adfe8
					  collapsed:: true
						- Travis CI
							- Travis is $130 minimum
					- [TeamCity](https://www.jetbrains.com/teamcity/)
					- [Octopus Deploy](https://octopus.com/)
					- Google Cloud Build
			- CD
			  id:: 63904f39-62e0-44d6-bd61-d5a6e98444a4
			  AKA Continuous Deployment / Continuous Delivery
				- _FOSS_
					- http://www.leroydeploy.com/
					- https://www.gocd.org/
					- Capistrano for deployment
					  collapsed:: true
						- http://capistranorb.com/
						- Capistrano
						- a deploy practice
						- Ansible has a playbook for it
						- usually it declares at least 4 phases of a deployment
							- Checkout
							- Migrate
							- Symlink
							- And restart
						- It helps defining a shared directory
							- where you temporary files or uploaded files there
							- so when you have new updates, you just have to redeploy and app will updated with new code
							- but still access to files generated during production
							- in case of Wordpress, it's wp-content/uploads
					- https://docs.chef.io/resource_deploy.html
					- [Ansistrano](https://github.com/ansistrano/deploy) - ((6463499d-b2c2-41e3-9f06-5b5fd75a452b))-based
				- AWS services
				  id:: 63a04cfd-4c07-4f11-be92-fa0f531c527b
					- ((64b7f676-aaa5-4351-aeee-dcc14b014bae))
					  1. Source
					- ((64b7f64c-8e70-4bf4-8680-2795cb1cc84f)) 2) Artifacts
					- ((64b7f66c-86f0-443a-b53b-190d004e78e7)) 3) Build
					- ((64b7f692-54e9-4bcf-95f9-301d3c298b1d)) 4) Deploy | Coordinate application deployments to Amazon EC2 instances
					- ((64b7f69c-6359-41e8-ae5d-bccf8b1f1a4d)) 5) Pipeline
					- ((6463499d-63a1-485e-bf7e-1bae513fd542))
					- Related: ((63904f39-e11b-4b28-9065-ce6396f67c4c)) : ((63a04d0d-b4cf-4754-ba57-5f0ebb21e063))
				- [DeployBot](https://deploybot.com/)
				- [Spinnaker](http://spinnaker.io/)
				  collapsed:: true
					- It provides two core sets of features: cluster management and deployment management.
					  https://www.spinnaker.io/concepts/
					- https://blog.spinnaker.io/scaling-spinnaker-at-netflix-part-1-8a5ae51ee6de
				- Buddy CD
				- Deployer
				- LaunchDarkly
				- ((6463499c-2d65-4504-8fc0-d3e90046dc53))
			- Workflow
				- ITSyndicate job proposed CI/CD
					- Integration with git repository by web hooks, so pushes to dev/test will trigger docker image update/deploy.
					- Additional manual tasks for prod env. Versioning of docker images (f.e. by build number)
					- I'd like it to create new builds both whether it's a dockerfile update or an image commit
			- ((635036c9-3db9-42e3-916f-f648a36c35ad))e.g. ((635036c9-3af8-4aa4-9e6c-c771acd65b01))
		- Secrets management (SSH keys, U2F, GPG, etc)
		  collapsed:: true
			- Pros/Cons
				- Pros
					- Public-key cryptography is immune to phishing, as the requester has to provide a matching key
				- Cons
			- Types of keys/secrets
			  collapsed:: true
				- PKA
					- USB security keys (FIDO)
					  collapsed:: true
						- Pros/Cons
							- Pros
								- Secure against phishing because it uses challenge-response
								- Public-key cryptography (used for SSH/GPG keys) means it's far more difficult to crack than passwords
								  AKA public-key authentication
									- It's like how SSH keys are used for server access because passwords are brute forced all the time
								- Very difficult to fingerprint a key from it's use on multiple domains
								  source:: [How FIDO2 and WebAuthn Stop Account Takeovers - explanation of how it works](https://workflowy.com/#/eb864db33d78) 30:00
								- Database breaches insufficient for account being compromised - the domain has to also be hijacked/MITM subsequently
						- Protocols
							- U2F (FIDO1)
							  collapsed:: true
							  AKA CTAP1 / FIDO Universal 2nd Factor
								- Products
									- Proprietary
										- Yubico Yubikeys
									- Software
										- [https://github.com/danstiner/rust-u2f](https://github.com/danstiner/rust-u2f)
								- App support
									- [Dashlane](https://www.tomsguide.com/reviews/dashlane) and <a href="https://www.tomsguide.com/reviews/keeper">Keeper</a> support U2F keys, while <a href="https://www.tomsguide.com/reviews/lastpass">LastPass</a> and <a href="https://www.tomsguide.com/reviews/1password">1Password</a> support Yubico's own standard.
							- WebAuthn (FIDO2)
							  collapsed:: true
							  AKA CTAP2
								- Pros/Cons
									- unlike U2F, WebAuthn does not require a traditional password (but it can if desired)
									- the primary difference is that a FIDO2 authenticator can also be a single multi-factor (passwordless) authenticator
									- A FIDO2 authenticator may be used in either single-factor mode or multi-factor mode. In single-factor mode, the authenticator is activated by a test of user presence, which usually consists of a simple button push. In multi-factor mode, the authenticator (something you have) performs user verification. Depending on the authenticator capabilities, this can be:[11]
										- something you know: a secret such as a PIN, passcode or swipe pattern
										- something you are: a biometric such as fingerprint, iris or voice
								- Products
									- Hardware
										- Yubico
									- Open source hardware
										- NitroKey FIDO2
										  collapsed:: true
											- [https://www.nitrokey.com/#comparison](https://www.nitrokey.com/#comparison)
										- Nitrokey 3c NFC [#Tasks-Start Thu, Jul 1, 2021 ]
										  collapsed:: true
											- [https://shop.nitrokey.com/shop/product/nk3cn-nitrokey-3c-nfc-148](https://shop.nitrokey.com/shop/product/nk3cn-nitrokey-3c-nfc-148)
										- SoloKeys
										  collapsed:: true
											- [https://www.indiegogo.com/projects/solo-v2-safety-net-against-phishing#/](https://www.indiegogo.com/projects/solo-v2-safety-net-against-phishing#/)
									- Software
										- Krypton
										  collapsed:: true
											- Test Mon, May 17, 2021 - didn't work on GitHub despite it prompting a notification on my Android app
											- [https://addons.mozilla.org/en-US/firefox/addon/krypton-authenticator/](https://addons.mozilla.org/en-US/firefox/addon/krypton-authenticator/)
											- [https://krypt.co/](https://krypt.co/)
											- [https://github.com/kryptco/krypton-android](https://github.com/kryptco/krypton-android)
										- Chrome and Android support (October 2022)
										- https://github.com/bulwarkid/virtual-fido
								- Software support
									- U2F security keys can be used as an additional method of two-step verification on online services that support the U2F protocol, including Google,[[2]](https://en.wikipedia.org/wiki/Universal_2nd_Factor#cite_note-Using_Security_Key-2) <a href="https://en.wikipedia.org/wiki/Microsoft_Azure">Azure</a>,<a href="https://en.wikipedia.org/wiki/Universal_2nd_Factor#cite_note-Azure-15">[15]</a> <a href="https://en.wikipedia.org/wiki/Dropbox_(service)">Dropbox</a>,<a href="https://en.wikipedia.org/wiki/Universal_2nd_Factor#cite_note-Auto58-1-16">[16]</a> <a href="https://en.wikipedia.org/wiki/GitHub">GitHub</a>,<a href="https://en.wikipedia.org/wiki/Universal_2nd_Factor#cite_note-Auto58-2-17">[17]</a> <a href="https://en.wikipedia.org/wiki/GitLab">GitLab</a>,<a href="https://en.wikipedia.org/wiki/Universal_2nd_Factor#cite_note-Auto58-3-18">[18]</a> <a href="https://en.wikipedia.org/wiki/Bitbucket">Bitbucket</a>,<a href="https://en.wikipedia.org/wiki/Universal_2nd_Factor#cite_note-Auto58-4-19">[19]</a> <a href="https://en.wikipedia.org/wiki/Nextcloud">Nextcloud</a>,<a href="https://en.wikipedia.org/wiki/Universal_2nd_Factor#cite_note-Auto58-5-20">[20]</a> <a href="https://en.wikipedia.org/wiki/Facebook">Facebook</a>,<a href="https://en.wikipedia.org/wiki/Universal_2nd_Factor#cite_note-Auto58-6-21">[21]</a> and others.<a href="https://en.wikipedia.org/wiki/Universal_2nd_Factor#cite_note-Auto58-7-22">[22]</a>
								- Web Authentication protocol
									- FIDO2 is the successor of the FIDO Universal 2nd Factor (U2F) legacy protocol. FIDO2 authentication has all the advantages of U2F—the primary difference is that a FIDO2 authenticator is a multi-factor authenticator (something you have).
									- A FIDO2 authenticator may be used in either single-factor mode or multi-factor mode. In single-factor mode, the authenticator is activated by a test of user presence (TUP), which usually consists of a simple button push. In multi-factor mode, the authenticator is activated by either a PIN (something you know) or a biometric (something you are).
									- https://www.w3.org/TR/2019/REC-webauthn-1-20190304/
								- Test it here [https://webauthn.org/](https://webauthn.org/)
								- _[Learning Resources]_
									- [https://github.com/herrjemand/awesome-webauthn](https://github.com/herrjemand/awesome-webauthn)
						- _{Archive}_
						  collapsed:: true
							- How FIDO2 and WebAuthn Stop Account Takeovers - explanation of how it works
							  [https://youtu.be/aMo4ZlWznao](https://youtu.be/aMo4ZlWznao)
								- 1 Backlink
									- Very difficult to fingerprint a key from it's use on multiple domains
									  source:: [How FIDO2 and WebAuthn Stop Account Takeovers - explanation of how it works](https://workflowy.com/#/eb864db33d78) 30:00
					- SSL certificates
					- SSH keys
					- PGP
				- OTP
					- HOTP
					- TOTP secrets
			- Types of software
				- _Simple_
					- Ansible Vault
					  collapsed:: true
						- Cons
							- Because it uses symmetric encryption with one password, this means that everyone reading and writing secrets will share this value. The more people with the password, the more change of leakage.
							- If the password becomes compromised, the files can be re-keyed, but then the password needs to be redistributed to everyone.
							- Ansible jobs tend to live in Git repositories, which is not great re-keying, because you'd need to remember to overwrite the history each time - otherwise an old compromised password will happily decrypt the historical version of the file.
							- Depending on your usage of Ansible, you might run into a chicken & egg situation (eg: a pull model where a machine needs the password beforehand to decrypt)
							- Ansible's current model of encrypting entire files has made it hard to search for values without decrypting to view each file, though as of version 2.3 they have added support for single encrypted values.
						- and then pass the decrypt key while run the deploy
						- https://gist.github.com/tristanfisher/e5a306144a637dc739e7
					- git-crypt
					- sneaker
					  https://github.com/codahale/sneaker
					- https://blog.threatstack.com/cloud-security-best-practices-finding-securing-managing-secrets-part-2
				- _Moderately complex_
					- credstash
					  collapsed:: true
					  https://github.com/fugue/credstash
						- It uses KMS to store encrypted values in DynamoDB, and allows you to scope the access via IAM roles.
						- CredStash is a very simple, easy to use credential management and distribution system that uses AWS Key Management Service (KMS) for key wrapping and master-key storage, and DynamoDB for credential storage and sharing.
					- blackbox (uses GPG)
					  collapsed:: true
					  https://github.com/StackExchange/blackbox
						- Create documentation
						- Add setup in Ansible playbook
					- pass
					  collapsed:: true
						- https://www.passwordstore.org/
					- https://github.com/crayfishx/hiera-gpg
				- _Very complex but powerful_
					- FOSS
						- [GitHub - Infisical/infisical: ♾ Infisical is the open-source secret management platform: Sync secrets across your team/infrastructure and prevent secret leaks.](https://github.com/Infisical/infisical)
						- [GitHub - openbao/openbao: OpenBao exists to provide a software solution to manage, store, and distribute sensitive data including secrets, certificates, and keys.](https://github.com/openbao/openbao)
						  FOSS fork of ((6463499d-e761-4836-9e35-efcd7ab40d17))
						-
					- [HashiCorp Vault](https://www.vaultproject.io)
					  id:: 6463499d-e761-4836-9e35-efcd7ab40d17
					  collapsed:: true
						- Cons
						  collapsed:: true
							- There's running Vault and getting Vault up and running reliably in production and ensuring that failure doesn't cause severe adverse effects. That probably means introducing HA.
							- Here are a few issues.
								- sealing/unsealing the vault - How are you going to manage the master encryption key shards. what's your process for unsealing the Vault in the event of failure. Where are the keys, who has access to them, and what's the procedure in the event of failure
								- storage backends - What is the right storage backend for you? Most of the storage backends do not support HA. (Some of my suggestions don't either.) If you require HA, can you run Consul, etcd, or Zookeeper reliably with HA? So now you're configuring and running Vault + a storage backend in an HA configuration. You're now potentially deploying two new systems that require testing to assess failure scenarios.
								- auth backends - How will you be authenticating services so they can access the vault? Are you going to issue them tokens or credentials? The EC2 backend for my purposes looks interesting. Once you've picked one it's time to implement. Will that require the introduction of third party libraries? I found hvac for Python integration.
							- This is all work that may end up taking weeks or longer to do before you're ready to roll it out. So I purposely focused on things with a much shorter period of time to implement under the assumption there's a higher likelihood of the work getting done. Personally I'd like to use Vault. But it's lower on my priority list for things to learn and do. That happens to many of us in this job. What I hope people get out of the piece is going from bad to better and setting themself up for future improvement as time permits.
							- Personal story. I've worked in places where there was far more to do than there was reasonably time to accomplish. I became adept at solving things to be become incrementally better than necessarily solving for the best solution.
						- Use a Docker container
						  https://hub.docker.com/_/vault/
						- GUI
						  collapsed:: true
							- Goldfish
							- https://github.com/Caiyeon/goldfish
							- Vault UI
								- https://github.com/djenriquez/vault-ui
								- https://hub.docker.com/r/djenriquez/vault-ui/
						- https://www.hashicorp.com/blog/using-hashicorps-vault-with-chef/
						- Initialise Vault with GPG (first run and optionally each seal/unseal)
						- https://www.vaultproject.io/docs/concepts/pgp-gpg-keybase.html
					- OpenStack Keystone
					  collapsed:: true
						- Some of the more common back ends include:
						- Key Value Store. An interface supporting primary key lookups, such as an in-memory dictionary.
						- ((64634999-fc4a-4bf0-9d74-f8dc23708311)). Distributed memory caching system
						- Structured Query Language (SQL). Uses SQLAlchemy (a Python SQL toolkit and Object Relational Mapper) to store data persistently
						- Pluggable Authentication Module (PAM). Uses the local system's PAM service to authenticate
						- Lightweight Directory Access Protocol (LDAP). Connects via the LDAP to a back-end directory, such as Active Directory®, to authenticate users and obtain role information
					- IBM Vault
			- _[Learning Resources]_
			  collapsed:: true
				- [How to handle secrets on the command line](https://smallstep.com/blog/command-line-secrets/)
			- \_Related: \_Password management
			  #Software https://workflowy.com/#/27387d381fe1
			- 4 Backlinks
			  collapsed:: true
				- FIDO2 - see [Secrets management](https://workflowy.com/#/52c1b1e7eea2)
				  #Infrastructure
				- Supercomputers can easily crack passwords. Far better to use public-key cryptography e.g. [(SSH keys, U2F, GPG, etc)](https://workflowy.com/#/52c1b1e7eea2)
				  #Infrastructure
				- See [Managing secrets ](https://workflowy.com/#/52c1b1e7eea2)
				- See [Secrets management](https://workflowy.com/#/52c1b1e7eea2)
				  #Infrastructure
		- Authentication
		  collapsed:: true
			- _Software_
				- Centralised
					- _SSO_
						- OpenID
						  collapsed:: true
						  Single login for all sites
							- **Cons**
								- Not decentralised
								- If compromised requires changing every password
							- https://en.m.wikipedia.org/wiki/OpenID
							- OpenID Connect for OAuth
						- LDAP
						  collapsed:: true
							- https://en.wikipedia.org/wiki/Lightweight_Directory_Access_Protocol
						- GitHub - nitnelave/lldap: Light LDAP implementation
						  collapsed:: true
							- [https://github.com/nitnelave/lldap](https://github.com/nitnelave/lldap)
				- See [Decentralised identity/trust/reputation](https://workflowy.com/#/6496725af187)
				  #Decentralisation
				- FOSS
					- Authelia
				- [Authentik](https://goauthentik.io/)
				- [Nango Supported APIs and API Wikis | Nango Docs](https://docs.nango.dev/providers) - support for 50+ OAuth providers
			- ((635eb171-c518-4825-aaaf-029c16ce1a86))
			  #Privacy-VPN
			- Know Your Customer (KYC)
				- [Stripe Identity](https://stripe.com/identity)
		- Container Ecosystem
		  id:: 6463499c-d91d-42c9-b035-93b6bc153e41
		  collapsed:: true
		  #Infrastructure-Containers
			- Container runtimes
				- Pros/Cons vs traditional packages
					- Pros
						- Less memory overhead than a virtual machine
				- _Comparison against encapsulated containers e.g. Flatpak _
				  intralink2:: https://workflowy.com/#/010baf677d12
				- _Types_
					- [[Docker]]
					- [Podman](https://podman.io/)
					  id:: 631219e3-ce87-482f-a283-a8cb0f8b23f5
					  collapsed:: true
						- Pros/Cons compared to [[Docker]]
							- Pros
								- Runs rootless, so no need for bind mounts
									- All files are saved neatly in home directory
									- Better security
								- Compatible with Docker Compose
						- Documentation
							- Setup
							  collapsed:: true
								- Journal
									- [[2023-04-11 Tuesday]] Attempt - got stuck on ((64359b73-c71a-48a0-8cb6-cd2beebe1197)) which failed to work (using Nix packages for all components. then tried with apt for just `podman`)
								- [Installation](https://podman.io/getting-started/installation)
									- `sudo apt-get -y install podman`
								- https://github.com/containers/podman/blob/main/docs/tutorials/podman_tutorial.md
								- https://github.com/containers/podman/blob/main/docs/tutorials/rootless_tutorial.md
									- cgroup V2 support
										- `podman --runtime crun` ?
										- or for all commands by changing the value for the "Default OCI runtime" in the containers.conf file either at the system level or at the user level from runtime = "runc" to runtime = "crun". at `~/.config/containers/containers.conf`
									- Check if cgroupV2 enabled
										- `grep cgroup /proc/filesystems`
											- If your system supports cgroupv2, you would see:
											- ```
											  nodev   cgroup
											  nodev   cgroup2
											  ```
									- `sudo apt install slirp4netns`
									- `fuse-overlayfs -V` - Check if it is installed, and what version
									- `sudo apt install shadow-utils newuid`
										- i.e. `sudo apt install libvshadow-utils rootlesskit` on Ubuntu
									- `cat /etc/subuid`
										- 2nd number should be >10000 e.g. `boss:100000:65536`
									- `cat /etc/subgid`
									- `ls ~/.config/containers/`
										- If user config files don't exist there, then check where they exist
											- `ls /usr/share/containers`
											- `ls /etc/containers`
										- copy the template files over: `cp -a /usr/share/containers ~/.config/containers/`
										- 2. `registries.conf`
											- `cp /etc/containers/registries.conf ~/.config/containers/registries.conf`
										- 3. `storage.conf`
								- Set up the Podman socket in order for Docker Compose to work:
									- `sudo systemctl enable podman.socket`
									- If the above command not possible, then (chatgpt answer)
										- `sudo nano /etc/systemd/system/podman.socket`
										  id:: 64359b73-c71a-48a0-8cb6-cd2beebe1197
											- ```
											  [Unit]
											  Description=Podman API Socket
											  
											  [Socket]
											  ListenStream=/run/podman/podman.sock
											  SocketMode=0660
											  SocketUser=root
											  SocketGroup=podman
											  
											  [Install]
											  WantedBy=sockets.target
											  ```
									- `sudo systemctl start podman.socket`
									- `sudo systemctl status podman.socket`
									- This sets up a Unix socket in to communicate with Docker Compose and symlinks it to /var/run/docker.sock.
								- To test if you can communicate with the socket, run the following curl command:
									- `sudo curl -H "Content-Type: application/json" --unix-socket /var/run/docker.sock http://localhost/_ping`
								- Troubleshooting
									- `echo $UID` = check user ID (1000 currently)
							- Try it with existing Docker software
							- Commands
								- `podman ps` = Show running containers
								- `podman ps -a` = Show all containers
							- Troubleshooting
								- `docker compose up` results in the error `Cannot connect to the Docker daemon at unix:///run/user/1000/podman/podman.sock`
									- `export DOCKER_HOST=unix:///var/run/docker.sock`
									- Then reload bash or open a new terminal
						- Podman Desktop - Flatpak
						- [Learning Resources]
							- https://docs.podman.io/en/latest/Tutorials.html
					- rkt
					  collapsed:: true
						- https://coreos.com/rkt/docs/latest/rkt-vs-other-projects.html
					- Mesos
					- Open Container Initiative-spec
					  collapsed:: true
						- https://github.com/opencontainers/runtime-spec/blob/master/implementations.md
			- Container Orchestration
			  collapsed:: true
			  For managing multiple containers, especially on multiple servers
				- Container management platform
				  For managing multiple containers, especially on multiple servers
					- Rancher
					  collapsed:: true
					  http://rancher.com/ | deploy and manage Docker containers and Kubernetes
						- _Info_
						  collapsed:: true
							- http://rancher.com/docs/
							- https://github.com/rancher/rancher
							- https://forums.rancher.com/
						- Pros/Cons
						  collapsed:: true
							- Pros
								- Good GUI for seeing host performance
								  http://i.imgur.com/j05wZ4c.png
								- Integrated load balancing
								- Load balancing and health check included
								- Rolling upgrades, green/blue upgrades feature
								- Dns and service discovery out-of-the-box
							- Cons
						- Rancher environments are clusters of servers and these are managed by container orchestration tools e.g. Cattle, Kubernetes, Mesos, (Docker) Swarm
						- Each server is a host and you have an overview of the cluster of containers (stack) and/or standalone containers
						  http://i.imgur.com/3KFYPZj.png
						- service discovery, packaging and more
						- Benefits
						  collapsed:: true
							- Easy deployment to on-premises, hybrid, public cloud or multi-public cloud
						- With the Rancher application catalog you can easily manage your applications and deploy them with a click of a button. The public catalog delivers more than 90 popular Docker applications.
						- Rancher aids Kubernetes deployments
						  collapsed:: true
							- Rancher aids Kubernetes deployments
							- needs. In these situations, setting up andconfiguring Kubernetes, as well as automating infrastructure deployment, gives rise to severalchallenges:
								- Creating a custom Kubernetes ennvironment that works
								- Automating the deployment of multiple Kubernetes clusters
								- Managing the health of Kubernetes clusters (e.g. recovering from etcd
								- node problems)
								- Automating the upgrade of Kubernetesclusters
								- Deploying multiple clusters, onpremises and across disparate cloudproviders
								- Enterprise readiness, including 24x7support
								- Customizing and repeatedly deployingmultiple combinations of infrastructureservices (e.g. storage, load balancer)
								- Deploying and managing upgrades forKubernetes add-ons such as Dashboard,Helm and Heapster
							- Features
								- • A certified and supportedKubernetes distribution withsimplified configuration options
								- • Infrastructure services includingload balancers, cross-hostnetworking, storage drivers, andsecurity credentials management
								- • Automated deployment andupgrade of Kubernetes clusters
								- • Support for multiple clusters andclouds
								- • Enterprise-class features such asrole-based access control and 24x7support
							- The services integrated with Rancher include:
								- Ingress controller with multiple loadbalancer implementations (HAproxy,traefik, etc.)
									- If you chose to deploy an ingress controller onnative Kubernetes, each provider would haveits own code base and set of configurationvalues. However, Rancher load balancer has ahigh level of customization to meet user needs.The Rancher ingress controller provides theflexibility to select your load balancer ofchoice—including HAproxy,Traefik,andnginx—while the configuration interface remains thesame. Rancher alsoprovides the ability to scalethe load balancer, customize load balancersource ports,and schedule the load balanceron a specific set of hosts
								- Highly customizable load balancer
								- Cross-host networking drivers for IPSECand VXLAN
								- Storage drivers
								- Certificate and security credentialsmanagement
								- Private registry credential management
								- DNS service which is a drop-in replacement for SkyDNS
								- Features such as role-based access control,integration with LDAPand active directories,detailed audit logs, high-availabilitymanagement server, metering (via Heapster),and encrypted networking are available out ofthe box.
						- With the Rancher application catalog you can easily manage your applications and deploy them with a click of a button. The public catalog delivers more than 90 popular Docker applications.
						- Kubernetes
						  #Infrastructure-Containers https://workflowy.com/#/4aed3095684f
						- Documentation
							- Part 1 - unorganised notes
								- https://rancher.postmymeds.co.uk
								- http://pict.ovh/scr/Capto_Capture-2017-07-26_15-05-16_.mp4
								- On the video above - you can see example of the deployment with our test domain. You can try with another one, if you want to.
								- Click Add, add tags and launch command from Rancher on the server. The only necessary condition - docker service must be installed on the target server
								- Also we'll prepare Ansible role for adding servers to Rancher automatically.
								  ***
								- Now during deploy/upgrade of the stack in the DB - the website's URL is fixed for Wordpress.
								- wp --allow-root option update home ''"$SITE_PROTO"'://'"$SITE_DOMAIN"''
								- wp --allow-root option update siteurl ''"$SITE_PROTO"'://'"$SITE_DOMAIN"''
								- And during deploy in WP config DB params are being set up (name/user/password).
								- MySQL DB (DB container) is created together with params, init db dump you mentioned is uploaded to the DB automatically.
								- To Dockerize any of your current websites - you need to add 1 docker file to your code repo: https://gitlab.postmymeds.co.uk/wordpress/app/blob/master/Dockerfile
								- CI is configured separetely for each website. To do it - you need to add 1 file to the repo and fix docker image path in there.
								- And configure CI in a way, when push goes to master - image is updated automatically and deployed to prod stack automatically; when push goes to dev - image is updated and deployed to dev stack.
								- HOW TO CONFIGURE CI , you may ask - we'll prepare this information in the Documents and Manuals after the whole infrastructure is ready. We'll prepate documents with images and manuals when we end with all CI configurations and stuff.
								- Also we may leave an opportunity for roll-back to previous image, so after update through CI - you'll have a button in Rancher rollback. When you click on it - your stack will be rolled back to previous version, so to the version which was before the latest update. Let me know if it fits you :smile:
								  ***
								- Now for tests we're using the code from the provided repo - https://github.com/LeapingDragon/PMM-UK1
								- You're able to launch it just with 2 clicks (you can see it on the video) with any kind of domain.
								  ***
								- Also as you've said:
								- Hi Serhii, at this stage no we don't need any further decoupling for scaling
								- I took out the [1.6] Configure scaling API triggers from the estimate.
								- Let me know if you have any questions
								- Easy way to setup Docker to the server - run this command from root - curl https://releases.rancher.com/install-docker/17.03.sh | sh
								- After script sets everything up - server can be added to Rancher.
								- And after it - you can deploy WP stack from the catalogue, as you can see it in the video.
								- and last notes:
								- domain needs to be pointed to the IP of the server, where it will be deployed.
								- SSL certificate from Let's Encrypt (free one) is automatically set up and configured and is automatically added to Rancher (so you can choose it in balancer).
								- letsencrypt container is stack - looks after the certificate and automatically updates it 30 days before it expires.
							- Part 2 - see #PMM
					- DC/OS
					  collapsed:: true
						- As a datacenter operating system, DC/OS is itself a distributed system, a cluster manager, a container platform, and an operating system.
						- Mesophere
						  Enterprise/IaaS DC/OS
							- https://mesosphere.com/
				- _Self-Hosted_
					- Kubernetes
					  collapsed:: true
					  Can't run Docker Compose
						- Production-Grade Container Orchestration
						- Automated container deployment, scaling, and management
						- Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications.
						- https://www.digitalocean.com/community/tutorials/an-introduction-to-kubernetes
						- drivers for storage and networking, monitoring, security, RBAC
						- role-based access control (RBAC)
						- Manages multiple hosts, schedules services and manage health of containers
						- It introduces concepts like Pods, Replica Sets and Stateful Sets not found in Swarm along with features like autoscaling.
						- Kubernetes
						  collapsed:: true
							- drivers for storage and networking, monitoring, security, RBAC
							- role-based access control (RBAC)
							- Manages multiple hosts, schedules services and manage health of containers
							- Automatic binpacking
							- Automatically places containers based on their resource requirements and other constraints, while not sacrificing availability. Mix critical and best-effort workloads in order to drive up utilization and save even more resources.
							- Self-healing
							- Restarts containers that fail, replaces and reschedules containers when nodes die, kills containers that don't respond to your user-defined health check, and doesn't advertise them to clients until they are ready to serve.
							- Horizontal scaling
							- Scale your application up and down with a simple command, with a UI, or automatically based on CPU usage.
							- Service discovery and load balancing
							- No need to modify your application to use an unfamiliar service discovery mechanism. Kubernetes gives containers their own IP addresses and a single DNS name for a set of containers, and can load-balance across them.
							- Automated rollouts and rollbacks
							- Kubernetes progressively rolls out changes to your application or its configuration, while monitoring application health to ensure it doesn't kill all your instances at the same time. If something goes wrong, Kubernetes will rollback the change for you. Take advantage of a growing ecosystem of deployment solutions.
							- Secret and configuration management
							- Deploy and update secrets and application configuration without rebuilding your image and without exposing secrets in your stack configuration.
						- Load Balancing and Pods
						  source:: http://rancher.com/load-balancing-in-kubernetes/
						  collapsed:: true
							- Managing Containers
								- To understand Kubernetes load balancing, you first have to understand how Kubernetes organizes containers.
								- Since containers typically perform specific services or sets of services, it makes sense to look at them in terms of the services they provide, rather than individual instances of a service (i.e., a single container). In essence, this is what Kubernetes does.
							- Placing Them in Pods
								- In Kubernetes, the pod serves as a kind of basic, functional unit. A pod is a set of containers, along with their shared volumes. The containers are generally closely related in terms of function and services provided.
								- Pods that have the same set of functions are abstracted into sets, called services. It is these services which the client of a Kubernetes-based application accesses; the service stands in for the individual pods, which in turn manage access to the containers that make them up, leaving the client insulated from the containers themselves.
							- Managing Pods
								- Pods are routinely created and destroyed by Kubernetes, and are not designed to be persistent entities. Every pod has its own IP address (localhost-based), UID, and port; new pods, whether they are duplicates of current or previous pods, are assigned new UIDs and IP addresses.
								- Within each pod, communication between containers is possible, but direct communication with containers in different pods is not possible.
							- Letting Kubernetes Handle Things
								- Kubernetes uses its own built-in tools to manage communication with individual pods. This means that under ordinary circumstances, it is sufficient to rely on Kubernetes to keep track of pods internally, without worrying about the creation, deletion, or replication of individual pods. There may be times, however, when it is necessary for at least some internal elements of an application managed by Kubernetes to be visible to the underlying network. When this happens, the method of exposure must take into account the lack of persistent IP addresses.
							- Pods and Nodes
								- In many respects, Kubernetes can be seen as a pod-management system as much as a container-management system; much of its infrastructure deals with containers at the pod level, rather than at the container level.
								- In terms of internal Kubernetes management, the level of organization above the pod is the node, a virtual machine which serves as the deployment environment for the pods, and which contains resources for managing and communicating with them. Nodes can handle the creation, destruction, and replacement/redeployment of pods internally. Nodes themselves can also be created, destroyed, and redeployed. At the node and pod levels, functions such as creation, destruction, redeployment, use, and scaling are handled by internal processes called controllers.
							- Services as Dispatchers
								- That’s how Kubernetes handles containers and pods at the management level. But as we mentioned above, it also abstracts functionally related/identical pods into services, and it is at the service level that external clients and other elements of the application interact with pods.
								- Services have IP addresses (used internally by Kubernetes) which are relatively stable. When a program element needs to make use of the functions abstracted by the service, it makes a request to the service, rather than an individual pod. The service then acts as a dispatcher, assigning a pod to handle the request.
							- Dispatching and Load Distribution
								- If by now, you’re thinking, “Hey, shouldn’t load balancing happen at the dispatching level?”— You’re right. A service in Kubernetes is a bit like a heavy-equipment pool, sending functionally identical machines into the field as needed. And as part of the dispatching process, it needs to manage availability and prevent resource bottlenecks.
							- Let kube-proxy Do It
								- The most basic type of load balancing in Kubernetes is actually load distribution, which is easy to implement at the dispatch level. Kubernetes uses two methods of load distribution, both of them operating through a feature called kube-proxy, which manages the virtual IPs used by services.
								- The default mode for kube-proxy is called iptables, which allows fairly sophisticated rule-based IP management. The native method for load distribution in iptables mode is random selection— an incoming request goes to a randomly chosen pod within a service. The older (and former default) kube-proxy mode is userspace, which uses round-robin load distribution, allocating the next available pod on an IP list, then rotating (or otherwise permuting) the list.
							- Genuine Load Balancing: Ingress
								- As we mentioned above, however, neither of these methods is really load balancing. For true load balancing, the most popular, and in many ways, the most flexible method is Ingress, which operates by means of a controller in a specialized Kubernetes pod. The controller includes an Ingress resource—a set of rules governing traffic—and a daemon which applies those rules.
								- The controller has its own built-in features for load balancing, with some reasonably sophisticated capabilities. You can also include more complex load-balancing rules in an Ingress resource, allowing you to take into account load-balancing features and requirements for specific systems or vendors.
							- LoadBalancer as an Alternative
								- As an alternative to Ingress, you can also use a service of the LoadBalancer type, which uses a cloud service-based, external load balancer. LoadBalancer can only be used with specific cloud service providers, such as AWS, Azure, OpenStack, CloudStack, and Google Compute Engine, and the capabilities of the balancer are provider-dependent. Other load-balancing methods may be available from service providers, as well as third parties.
							- In the Balance, It’s Ingress
								- Currently, however, Ingress is the load-balancing method of choice. Since it is essentially internal to Kubernetes, operating as a pod-based controller, it has relatively unencumbered access to Kubernetes functionality (unlike external load balancers, some of which may not have good access at the pod level). The configurable rules contained in an Ingress resource allow very detailed and highly granular load balancing, which can be customized to suit both the functional requirements of the application and the conditions under which it operates.
					- (Apache) Mesos
					  collapsed:: true
					  https://mesos.apache.org/ | A distributed systems kernel that manages cluster resources and tasks.
						- Mesos is one of the core components of DC/OS that predates DC/OS itself, bringing maturity and stability to the platform.
						- Mesos with Mesosphere (or Marathon, its open source version)
					- Swarm mode
					  id:: 6463499c-2c88-4c36-ac5b-8e43a34669a5
					  collapsed:: true
					  AKA Docker Native Orchestration
						- Docker Engine 1.12 shipped with Native Orchestration, which is a replacement for stand alone Docker Swarm. The Docker native cluster (Swarm) consists of a set of nodes (Docker Engines/ Daemons) which can either be managers or workers. Workers run the containers you launch and managers maintain cluster state.
						- It uses two extra containers: one acts as Swarm master node and the other one a first client node.
						- When you run Docker without using swarm mode, you execute container commands. When you run the Docker in swarm mode, you orchestrate services. You can run swarm services and standalone containers on the same Docker instances.
					- Cattle
					  Rancher’s native orchestrator
					- _Comparisons _
					  collapsed:: true
						- Docker Swarm vs Kubernetes
						  See http://info.rancher.com/comparing-kubernetes-swarm
				- _Managed/PaaS_
				  PaaS/CaaS https://workflowy.com/#/7bd4b0b56d86
				- Deprecated
				  collapsed:: true
					- Fleet (deprecated - instead CoreOS uses Kubernetes)
					  https://github.com/coreos/fleet
					-
				- _Comparison_
				  collapsed:: true
					- Detailed comparison - Kubernetes is the most feature-rich yet steep learning curve, then Mesos then Swarm
					  http://rancher.com/comparing-rancher-orchestration-engine-options/
				- \_Related: \_Docker GUIs
				  intralink2:: https://workflowy.com/#/6983127b69f3
			- Docker Registries
			  collapsed:: true
				- What Is a Docker Registry?
					- A Docker registry is a place to store and distribute Docker images. It serves as a target for your docker push and docker pull commands. Before we get any further, let’s cover some of the basic terminology related to Docker registries.
					- Image
					- An image is essentially a template for Docker containers. It consists of a manifest and an associated series of layers.
					- Layer
					- A layer represents a filesystem difference. An image’s layers are combined together into a single image that forms the base for a container’s filesystem.
					- Registry
					- A registry is a content delivery and storage system for named Docker images. It can be thought of as a collection of repositories keyed by name.
					- Repository
					- A repository is simply a collection of different versions for a single Docker image. In this way, you can think of it as being similar to a git repository. For example, the official Ubuntu repository has a description of what is in the image as well as a list of the available versions.
				- _SaaS_
					- Docker Cloud
					  intralink2:: https://workflowy.com/#/79a035ebe732
					- Docker Trusted Registry
					  intralink2:: https://workflowy.com/#/b0e3ab3e186c
					- ((64b7f20b-d92b-49cc-a0ad-64e70eca6cff))
					- Google Container Registry
					  https://cloud.google.com/container-registry/
					- Quay
					  https://quay.io/
					- Heroku
					  intralink2:: https://workflowy.com/#/cf957bc08042
				- _Self-hosted_
					- Docker Distribution
					  collapsed:: true
						- Docker Distribution (v2.0)
						  https://github.com/docker/distribution
						- Will supersede Docker Registry (v1.0)
						  https://docs.docker.com/registry
						- See [Docker](https://workflowy.com/#/6983127b69f3)
						  #Infrastructure-Containers
					- GitLab
					  collapsed:: true
						- https://about.gitlab.com/direction/#scope
					- Artifactory
					  https://www.jfrog.com/confluence/display/RTF/Docker+Repositories
					- and Bintray.
				- [https://blog.codeship.com/overview-of-docker-registries/](https://blog.codeship.com/overview-of-docker-registries/)
				- See [Docker](https://workflowy.com/#/6983127b69f3)
				  #Infrastructure-Containers
			- Deploying to Docker Registries
			  id:: 6463499c-2d65-4504-8fc0-d3e90046dc53
			  collapsed:: true
				- Jenkins
				  https://wiki.jenkins.io/display/JENKINS/CloudBees+Docker+Build+and+Publish+plugin
				- [[Docker]]
				- Heroku
				  https://devcenter.heroku.com/articles/container-registry-and-runtime
			- ((6463499d-ddc1-4971-a467-a223d3f73579))
			- ((6463499e-ee8c-4db4-9ba2-6b0307e7b528))
			- Dev Containers
			  id:: 68022be0-04ad-4958-9b63-33f346da4603
			  collapsed:: true
			  AKA Development Containers / Developing in a container / Dev-Environments-As-Code
				- ## FOSS
					- [DevPod](https://devpod.sh/)
					  collapsed:: true
					  Client-only and unopinionated: Works with any IDE and lets you use any cloud, kubernetes or just localhost docker
						- [GitHub - loft-sh/devpod: Codespaces but open-source, client-only and unopinionated: Works with any IDE and lets you use any cloud, kubernetes or just localhost docker.](https://github.com/loft-sh/devpod)
						- [Install Devpod on Linux | Flathub](https://flathub.org/apps/sh.loft.devpod)
					- [Coder - Your Self-Hosted Remote Development Platform](https://coder.com/)
					  collapsed:: true
						- [GitHub - coder/code-server: VS Code in the browser](https://github.com/cdr/code-server) 
						  VS Code in the browser
					- [Home | Eclipse Che](https://www.eclipse.org/che/)
					- [Tilt | Kubernetes for Prod, Tilt for Dev](https://tilt.dev/)
					- [GitHub - hocus-dev/hocus: 🪄 Spin up ready-to-code, disposable dev environments on your own servers. Self-hosted alternative to Gitpod and Github Codespaces.](https://github.com/hocus-dev/hocus)
					- [GitHub - stepchowfun/toast: Containerize your development and continuous integration environments. 🥂](https://github.com/stepchowfun/toast)
					- [GitHub - recode-sh/cli: A CLI to create remote development environments in your cloud provider account in seconds](https://github.com/recode-sh/cli)
				- ## Proprietary
					- ### Local
						- [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) 
						  id:: 68022cfa-1c35-40a5-866a-c010d77b700c
						  collapsed:: true
						  by Microsoft
							- James' Dev Containers session
								- https://containers.dev/implementors/spec/ contains info about the Dev Container spec
								- Built on Docker
								- It uses bind mounts to add your workspace files into it
								- `vscode-server` gets installed in each dev container
								- It's an alternative to meta version managers like nvm for Node, sdkman for Java, https://github.com/pyenv/pyenv or Conda for Python, etc. Allows you to maintain multiple installs of dependencies
								- On an internet-connected machine you can use devcontainer-CLI - it's built on top of docker-CLI
								- `devcontainer.json`
									- Instead of "image" you can have "build" and add a dockerfile/shell script
								-
								- Dev Containers aspects
									- Templates
										- A dev container with lots of features available
									- Features
										- https://ghcr.io + https://mcr.io registries have many features/templates uploaded
										- It's a section within `devcontainer.json`
										- Basically for reusable container code e.g. install+setup X package
										- `version` refers to versioning of the devcontainers-feature.json itself - used for enterprise heavy reliance on devcontainers feature
										- `dependsOn` section if for writing dependencies to be automatically installed
										- After IMPEXing update `devcontainer-feature.json`
							- dev-containers/features/README.md - our BAE repo for putting devcontainers features artifacts in the GitLab package registry
								- Project structure
									- ```
									  - src/
									  - README.md
									  - package.sh
									  ```
									- `README.md`
										- To add a feature create a feature directory under `src/`. Each feature is expected to comprise at least the following contents:
											- devcontainer-feature.json
											- install.sh
											- README.md
										- ## Package
											- Dev container features are packaged and distributed as compressed tarballs `.tgz` and follow a specific naming convention. To package an existing dev container feature, run the following:
											- `tar --create --gzip --file devcontainer-feature-<feature-id>.tgz --directory src/<feature-id> .`
											- where `<feature-version> refers to the 'version' property defined in devcontainer-feature.json
											- Alternatively use the `package.sh` script as follows:
											- ``./package.sh <username> <personal-access-token> <feature-id> <feature-version>`
											- Note: The GitLab personal access token must have the 'API' scope.
										- ## Use
											- To make use of the dev container features on this git repo, add the following to your `devcontainer.json`:
											- ```json
											  {
											  	...
											  	"features": {
											  		"https://gitlab.com/api/v4/projects/178/generic/<feature-id>/feature-version>/devcontainer-feature-<feature-id>.tgz": {
											  			...
											  		},
											  		...
											  	}
											  	...
											  }
											  ```
							- Dev container multi container attempt on project (wasn't working well so this is the version we're sticking with) - see James' merge request
							- VSCode project structure
								- `.devcontainer/`
									- `devcontainer.json`
										- `devcontainer.json` [lifecycle scripts](https://containers.dev/implementors/json_reference/#lifecycle-scripts)
											- `postStartCommand` = do this everytime a dev container is launched
												- Example
													- ```json
													  "postStartCommand": "git submodule update --init",
													  ```
											- `postCreateCommand` = do this when the container is first created
												- Example
													- ```json
													  "postCreateCommand": "cd folder1 && touch test.txt",
													  ```
									- `extensions/`
										- blah.blah.vsix
								- `.vscode/`
									- `launch.json`
									- `settings.json`
									- `tasks.json`
							- Entrypoint:
								- `docker compose -f which-craft/.docker/docker-compose.yml up`
								- This starts three containers `web-server` (`cloud` network), `websockify` ((`cloud` network), `field-device` (on the `field-device` network).
								- Note: Docker Compose msut be run in WSL, not in the dev container since we currently do not mount the Docker socket into the container nor do we install the Docker CLI.
							- Copy the VSIX file for each extension into `.devcontainer/extensions/`. The dev container will automatically install the extensions from this location.
							- `.devcontainer/devcontainer.json`
								- Example
								  collapsed:: true
									- ```json
									  {
									  	"name": "project1",
									  	"image": "ubuntu:24:04",
									  	"containerUser": "user",
									  	"runArgs": [
									  		"--device=/dev/kvm"
									  	],
									  	"containerEnv": {
									  		"SDL_AUDIODRIVER": "pulseaudio"
									  	},
									  	"postStartCommand": "git submodule update --init",
									  	"postCreateCommand": "ls -alhg",
									  	"remoteEnv": {
									  		"SOMETHING_1": "test1",
									  		"SOMETHING_2": "test2"
									  	},
									  	"workspaceFolder": "/workspaces/$localWorkspaceFolderBasename}",
									  	"workspaceMount": "source=${localWorkspaceFolder},target=/workspaces/which-craft,type=bind",
									  	"mounts": [
									  		"source=/mnt,target=/mnt,type=bind,consistency=cached"
									  	],
									  	"customizations": {
									  		"vscode": {
									  			"settings": {
									  				"terminal.integrated.profiles.linux": {
									  					"bash": { "path": "/bin/bash" }
									  				},
									  				"terminal.integrated.defaultProfile.linux": "bash"
									  			},
									  			"extensions": [
									  				"${containerWorkspaceFolder}/.devcontainer/extensions/redhat.java.vsix",
									  				"${containerWorkspaceFolder}/.devcontainer/extensions/redhat.vscode-yaml.vsix"
									  			],
									  		}
									  	}
									  	
									  }
									  ```
							- `src/.devcontainer/` directory
								- The `devcontainer.json` can be used to define the VSCode extensions in the dev container for example, as long as you store the VSIX file for each extension in `.devcontainer/extensions/`
								- `src/.devcontainer/Dockerfile`
								  collapsed:: true
									- ```
									  FROM python:3.13.1
									  
									  RUN useradd --create-home user
									  USER user
									  ```
								- `src/.devcontainer/devcontainer.json`
								  collapsed:: true
									- ```json
									  {
									  "name": "whatever", 
									  "build": {
									  "dockerfile": "Dockerfile",
									  "context": "${localWorkspaceFolder}"
									  },
									  "postStartCommand": "./whatever/setup/python.sh whatever/backend whatever/backend/.pip && ./whatever/setup/node.sh whatever/frontend whatever/setup/deps && ./whatever/setup/jre.sh whatever/setup/deps",
									  "containerEnv": {
									  "ENABLE_DOCS": 1
									  },
									  "customizations": {
									  "vscode": {
									  	"settings": {
									  		"terminal.integrated.profiles.linux": {
									  			"bash": { "path": "/bin/bash" }
									  		},
									  		"terminal.integrated.defaultProfile.linux": "bash",
									  		"sonarlint.pathToNodeExecutable": "/home/user/.node/bin/node",
									  		"sonarlint.ls.javaHome": "/home/user/.java/jre"
									  	},
									  	"extensions": [
									  		"${containerWorkspaceFolder}/.devcontainer/extensions/charliemarsh.ruff.vsix",
									  		"${containerWorkspaceFolder}/.devcontainer/extensions/dbaeumer.vscode-eslint.vsix",
									  		"${containerWorkspaceFolder}/.devcontainer/extensions/esbenp.prettier-vscode.vsix",
									  		"${containerWorkspaceFolder}/.devcontainer/extensions/ms-python.debugpy.vsix",
									  		"${containerWorkspaceFolder}/.devcontainer/extensions/ms-python.python.vsix",
									  		"${containerWorkspaceFolder}/.devcontainer/extensions/ms-python.vscode-pylance.vsix",
									  		"${containerWorkspaceFolder}/.devcontainer/extensions/python-docstring-generator.vsix",
									  		"${containerWorkspaceFolder}/.devcontainer/extensions/sonarsource.sonarlint-vscode.vsix",
									  		"${containerWorkspaceFolder}/.devcontainer/extensions/streetsidesoftware.code-spell-checker.vsix",
									  		"${containerWorkspaceFolder}/.devcontainer/extensions/vitest.explorer.vsix"
									  	]
									  }
									  }
									  }
									  ```
							- ((68022be0-04ad-4958-9b63-33f346da4603)) in ((67a8e13b-994c-44b2-809e-b0fc960a004d))
							  id:: 68290fd6-eae8-45a2-83ed-d5820ad56883
							  collapsed:: true
								- Pre-requisites
									- Docker
										- Add user to the `docker` group
											- `sudo usermod -aG docker $USER`
										- Set a common ID for the `docker` group to enable sharing of the Docker daemon between WSL distros
											- `sudo groupmod -g 36257 docker`
										- Prepare a shared directory for your Docker socket
											- ```bash
											  DOCKER_DIR=/mnt/wsl/shared-docker
											  mkdir -pm o=,ug=rwx "$DOCKER_DIR"
											  sudo chgrp docker "$DOCKER_DIR"
											  ```
										- configure the Docker daemon to use the shared socket by creating a config file at `/etc/docker/daemon.json` with the following content:
											- ```json
											  {
											  	"hosts": ["unix:///mnt/wsl/shared-docker/docker.sock"]
											  }
											  ```
										- To automatically launch the Docker daemon on login add the following your `~/.bashrc`
											- ```
											  DOCKER_DISTRO="<YOUR-DISTRO-NAME>"
											  DOCKER_DIR=/mnt/wsl/shared-docker
											  DOCKER_SOCK=$DOCKER_DIR/docker.sock"
											  export DOCKER_HOST="unix://$DOCKER_SOCK"
											  if [ ! -S "$DOCKER_SOCK" ]; then
											  mkdir -pm o=,ug=rwx "$DOCKER_DIR"
											  chgrp docker "$DOCKER_DIR"
											  /mnt/c/Windows/System32/wsl.exe -d $DOCKER_DISTRO sh -c "nohup sudo -b dockerd < /dev/null > $DOCKER_DIR/dockerd.log 2>&1"
											  fi
											  ```
										- Grant passwordless access to `dockerd` by running `sudo visudo` and adding the following line:
											- `$docker ALL=(ALL) NOPASSWD: /usr/bin/dockerd`
									- VSCode client installed in Windows
									- VSCode server installed in WSL
									- VSCode Remote WSL extension installed
									- VSCode Dev Containers extension installed
								- Retrieve the VSCode client git commit hash (Help > About > Commit)
									- `sudo mkdir -p /var/lib/docker/volumes/vscode/_data/vscode-server/bin/linux-x64/<commit-hash>`
									- `sudo cp -r ~/.vscode-server/bin/<commit-hash> /var/lib/docker/volumes/vscode/_data/vscode-server/bin/linux-x64/`
									- In VSCode open the Command Palette (CTRL+SHIFT+P)
									- Select `Dev Containers: Reopen in Container`
					- ### SaaS
						- [GitHub Codespaces](https://github.com/features/codespaces)
						- [Gitpod](http://gitpod.io/)
				- [Development Containers | Hacker News](https://news.ycombinator.com/item?id=34513877)
				- Related: ((646349e4-e38f-4bf7-9b2a-8a3d813101e0))
			- Related: ((646349e4-e38f-4bf7-9b2a-8a3d813101e0))
		- Multiple Websites/Apps on One Server
		  id:: 6463499c-7e93-4675-bd3f-ff831c772a24
		  collapsed:: true
		  #VirtualHosts
			- In DigitalOcean DNS records add a CNAME record for each subdomain
				- Name: (subdomain name)
				- Hostname: (full domain name + . at end)
			- _Web servers_
				- [Caddy](https://caddyserver.com/)
				  id:: 6463499c-eb78-40d8-9a9e-ca7a9f0ad0be
				  collapsed:: true
					- Documentation
						- May 2022 - normal Ubuntu package version is easy to use and Caddyfile is simple. docker-compose may be nice extra but a bit unnecessary
						- docker-compose version setup
						  collapsed:: true
							- See [Install Docker on Ubuntu 22.04](https://workflowy.com/#/279e6f424ac2)
							- See [Executing the Docker Command Without Sudo (Optional)](https://workflowy.com/#/9b87a05dbdcb)
							- `sudo apt install docker-compose`
							- `cd ~/ && mkdir caddy && cd caddy`
							- `mkdir caddy`
							- `cd caddy`
							- `nano docker-compose.yml`
								- Copy template from https://hub.docker.com/_/caddy#docker-compose-example
									- Change `<version>` to `latest`
									- Remove `external`
									- Change volumes to bind mounts (add `./` infront of them)
								- My template
									- [[2025-10-07 Tuesday]]
										- ```yaml
										  services:
										    caddy:
										      image: caddy:2.10-alpine
										      restart: unless-stopped
										      cap_add:
										        - NET_ADMIN
										      ports:
										        - "80:80"
										        - "443:443"
										        - "443:443/udp"
										      volumes:
										        - $PWD/conf:/etc/caddy
										        - $PWD/site:/srv
										        - ./caddy_data:/data
										        - ./caddy_config:/config
										  
										  volumes:
										    caddy_data:
										    caddy_config:
										  
										  ```
											- The configuration assumes you put a custom Caddyfile into `$PWD/conf`
									- {Archive}
									  collapsed:: true
										- ```yml
										  version: "3.9"
										  
										  services:
										    caddy:
										      image: caddy:2.7.4 # Alternatively: caddy:latest
										      restart: unless-stopped
										      cap_add:
										        - NET_ADMIN
										      ports:
										        - "80:80"
										        - "443:443"
										        - "443:443/udp"
										      volumes:
										        - ./Caddyfile:/etc/caddy/Caddyfile
										        - ./site:/srv
										        - ./caddy_data:/data
										        - ./caddy_config:/config
										  
										  volumes:
										    caddy_data:
										    caddy_config:
										  ```
							- `nano Caddyfile`
								- ```
								  11.synthfleshop.casa {
								      reverse_proxy <docker-service-name>:80
								  }
								  
								  15-baikal.synthfleshop.casa {
								      reverse_proxy baikal:80
								  }
								  
								  ```
								- Enhanced
									- ```
									  15-baikal.synthfleshop.casa {
									      reverse_proxy baikal:80 {
									          header_up Host {host}
									          header_up X-Real-IP {remote_host}
									          header_up X-Forwarded-Proto https
									      }
									      # Enable CORS for CalDAV clients
									      header {
									          Access-Control-Allow-Origin "*"
									          Access-Control-Allow-Methods "GET, POST, PUT, DELETE, OPTIONS, PROPFIND, PROPPATCH, MKCOL, COPY, MOVE, LOCK, UNLOCK"
									          Access-Control-Allow-Headers "Content-Type, Depth, User-Agent, X-File-Size, X-Requested-With, If-Modified-Since, X-File-Name, Cache-Control, Authorization"
									      }
									  }
									  ```
							- [Create an A DNS record for the chosen Caddy URL](https://cloud.digitalocean.com/networking/domains)
							- `docker compose up -d`
							- Expected file structure
								- ```
								  your-project/
								  ├── docker-compose.yml
								  ├── conf/
								  │   └── Caddyfile          ← Place the Caddyfile here
								  ├── site/                  ← Optional static files
								  ├── caddy_data/           ← Caddy data (created automatically)
								  └── caddy_config/         ← Caddy config (created automatically)
								  ```
							- ## Example web service to be proxied
								- https://hub.docker.com/r/ckulka/baikal
									- ```yaml
									  # Docker Compose file for a Baikal server
									  
									  version: "2"
									  services:
									    baikal:
									      image: ckulka/baikal:nginx
									      restart: always
									      ports:
									        - "80:80"
									      volumes:
									        - config:/var/www/baikal/config
									        - data:/var/www/baikal/Specific
									  
									  volumes:
									    config:
									    data:
									  ```
								- Docker Compose with both services (alternatively: use shared network/external network in order to keep separate docker compose files)
									- My combined compose file
										- ```yaml
										  services:
										    baikal:
										      image: ckulka/baikal:nginx
										      restart: always
										      volumes:
										        - config:/var/www/baikal/config
										        - data:/var/www/baikal/Specific
										      networks:
										        - app-network
										  
										    caddy:
										      image: caddy:latest
										      restart: unless-stopped
										      cap_add:
										        - NET_ADMIN
										      ports:
										        - "80:80"
										        - "443:443"
										        - "443:443/udp"
										      volumes:
										        - $PWD/conf:/etc/caddy
										        - $PWD/site:/srv
										        - ./caddy_data:/dataservices:
										    baikal:
										      image: ckulka/baikal:nginx
										      restart: always
										      volumes:
										        - config:/var/www/baikal/config
										        - data:/var/www/baikal/Specific
										      networks:
										        - app-network
										  
										    caddy:
										      image: caddy:latest
										      restart: unless-stopped
										      cap_add:
										        - NET_ADMIN
										      ports:
										        - "80:80"
										        - "443:443"
										        - "443:443/udp"
										      volumes:
										        - $PWD/conf:/etc/caddy
										        - $PWD/site:/srv
										        - ./caddy_data:/data
										        - ./caddy_config:/config
										      networks:
										        - app-network
										  
										  volumes:
										    config:
										    data:
										    caddy_data:
										    caddy_config:
										  
										  networks:
										    app-network:
										      driver: bridge
										  
										  ```
						- Alternative
							- Caddy Docker
								- [https://github.com/caddyserver/caddy-docker](https://github.com/caddyserver/caddy-docker)
								- [https://hub.docker.com/\_/caddy](https://hub.docker.com/_/caddy)
							- See [Caddy setup](https://workflowy.com/#/87c5a0ced569)
							- Caddy works well with [Caddy-Docker-Proxy](https://github.com/lucaslorentz/caddy-docker-proxy) for multiple Docker projects
							- [Localias](https://github.com/peterldowns/localias) is built on Caddy and meant for easy local development
						- `sudo systemctl reload caddy`
						  Reloading
					- Example setups
						- See Jellyfin [Setup on a VPS](https://workflowy.com/#/c59a7b5a25d8)
						- Caddyfile with multiple web apps
						  ```
						  13-nextcloud.synthfleshop.casa {
						          reverse_proxy localhost:8080
						  }
						  13-ttrss.synthfleshop.casa {
						          reverse_proxy localhost:8280
						  }
						  ```
					- Related:
						- ((663a578f-bad3-4b35-8666-694af7544616))
						- See [Docker](https://workflowy.com/#/6983127b69f3)
						  #Infrastructure-Containers
						- See [Nginx Proxy Manager (GUI)](https://workflowy.com/#/5a5894443e89)
				- [Nginx](https://nginx.org/)
				  id:: 67376780-c521-4602-bbcb-c23d12ced6a4
				  collapsed:: true
					- Pros/Cons
						- Pros
						- Cons
						- Unclear
						- Comparisons
							- ((6737677f-2658-4b70-9dec-73c8da7b5334))
							- Nginx vs Caddy
					- [Freenginx](https://news.ycombinator.com/item?id=39373327)
					- [Nginx Proxy Manager](https://github.com/jc21/nginx-proxy-manager) (GUI)
					- Nginx Setup
					  id:: 6463499c-e15b-4225-9e1e-0e31863d1196
						- /etc/nginx for config files
						  
						  **Web Root: **
						  /usr/share/nginx/html is default for nginx
						  but it's easier to use apache's default /var/www/
						- 2021
						  collapsed:: true
							- Setup Nginx
							  [archived] [[404 - Page not found](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04))
								- 5. Setup server blocks
									- Create a directory
									  sudo mkdir -p /var/www/your_domain/html
										- Example
											- sudo mkdir -p /var/www/jellyfin.synthfleshop.casa/html
							- 2. Configure HTTPS for Nginx with automatic SSL certificates using Let's Encrypt Certbot
							     source:: [https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04)
						- 2019
						  collapsed:: true
							- Nginx Initial Setup
							  collapsed:: true
								- Get Nginx
									- sudo apt-get install nginx
									- sudo service nginx start
								- Config php.ini
									- sudo apt-get install php5-fpm libapache2-mod-php5 php5-mcrypt
									- sudo mkdir -p /etc/php5/fpm/
									- sudo pico /etc/php5/fpm/php.ini
									  ; Maximum allowed size for uploaded files.
									  upload_max_filesize = 40000M
									  
									  ; Must be greater than or equal to upload_max_filesize
									  post_max_size = 40000M
										- touch /etc/php5/fpm/php.ini
										  To create a file
									- service nginx restart
								- sudo update-rc.d nginx defaults
								  Set auto startup
							- Nginx General
							  collapsed:: true
								- Starting Nginx
									- sudo /etc/init.d/nginx start
								- Fixing Nginx
									- sudo nginx -c /etc/nginx/nginx.conf -t
									- sudo nginx -t
									- Fixes
										- sudo chown -R bakashi:sudo /var/log/nginx
										- **sudo /etc/init.d/nginx start**
							- Nginx Setup for each Subdomain
							  collapsed:: true
							  https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-server-blocks-virtual-hosts-on-ubuntu-14-04-lts
								- Create SSL certificates
								  intralink2:: https://workflowy.com/#/86a6cb0e42e0
								- Create working folders for each subdomain
								  The first folder is the folder where your server code is placed and the other is for logging access and errors.
									- sudo mkdir -p /var/www/SUBDOMAIN.DOMAIN.com/html
									  -p makes parent directories along the way
									- sudo chown -R $USER:$USER /var/www/example.com/html
									- sudo -P mkdir /var/log/nginx/SUBDOMAIN.DOMAIN.com
								- Create server block file
									- sudo cp /etc/nginx/sites-available/default /etc/nginx/sites-available/[example.com](http://example.com)
								- Configure Nginx site file
									- nano /etc/nginx/sites-available/SUBDOMAIN.DOMAIN.com
										- nano /etc/nginx/sites-available/baikal.rasenshuriken.space
										- sudo mv /home/bakashi/nginx.conf /etc/nginx/sites-available/owncloud.rasenshuriken.space
										-
									- Add this content
									  In the file, add the content like below. The important parts are: The upstream handler FPM. You can double check with the following official site on Nginx Configuration for OwnCloud 7. Here is the configuration, remember to adjust the server name, the name of the SSL key and SSL certificate and the path to the working directory as well as the logging folder.
									  
									  upstream php-handler {
									  server unix:/var/run/php5-fpm.sock;
									  }
									  
									  server {
									  listen 80;
									  ** server_name owncloud.yourdomain.com;**
									  enforce https
									  return 301 https://$server_name$request_uri;
									  }
									  
									  server {
									  listen 443 ssl;
									  <b> server_name owncloud.yourdomain.com;</b>
									  
									  <b> ssl_certificate /etc/nginx/ssl/owncloud.yourdomain.com.crt;
									  ssl_certificate_key /etc/nginx/ssl/owncloud.yourdomain.com.key;</b>
									  
									  Path to the root of your installation
									  <b> root /var/www/owncloud.yourdomain.com/;</b>
									  set max upload size
									  client_max_body_size 10G;
									  fastcgi_buffers 64 4K;
									  
									  rewrite ^/caldav(._)$ /remote.php/caldav$1 redirect;
									  rewrite ^/carddav(._)$ /remote.php/carddav$1 redirect;
									                      rewrite ^/webdav(.*)$ /remote.php/webdav$1 redirect;
									  
									  index index.php;
									  error_page 403 /core/templates/403.php;
									  error_page 404 /core/templates/404.php;
									  
									  location = /robots.txt {
									  allow all;
									  log_not_found off;
									  access_log off;
									  }
									  
									  location ~ ^/(?:\.htaccess|data|config|db_structure\.xml|README){
									  deny all;
									  }
									  
									  location / {
									  The following 2 rules are only needed with webfinger
									  rewrite ^/.well-known/host-meta /public.php?service=host-meta last;
									  rewrite ^/.well-known/host-meta.json /public.php?service=host-meta-json last;
									  
									  rewrite ^/.well-known/carddav /remote.php/carddav/ redirect;
									  rewrite ^/.well-known/caldav /remote.php/caldav/ redirect;
									  
									  rewrite ^(/core/doc/[^\/]+/)$ $1/index.html;
									  
									  try_files $uri $uri/ /index.php;
									  }
									  
									  location ~ \.php(?:$|/) {
									                       fastcgi_split_path_info ^(.+\.php)(/.+)$;
									  include fastcgi_params;
									  fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
									  fastcgi_param PATH_INFO $fastcgi_path_info;
									  fastcgi_param HTTPS on;
									  fastcgi_pass php-handler;
									  }
									  
									      Optional: set long EXPIRES header on static assets
									  
									  location ~\* \.(?:jpg|jpeg|gif|bmp|ico|png|css|js|swf)$ {
									  expires 30d;
									  Optional: Don't log access to assets
									  access_log off;
									  }
									  
									  }
										- owncloud
										  upstream php-handler {
										  server unix:/var/run/php5-fpm.sock;
										  }
										  
										  server {
										  listen 80;
										  ** server_name owncloud.rasenshuriken.space;**
										  enforce https
										  return 301 https://$server_name$request_uri;
										  }
										  
										  server {
										  listen 443 ssl;
										  <b> server_name owncloud.rasenshuriken.space;</b>
										  
										  <b> ssl_certificate /etc/nginx/ssl/owncloud.rasenshuriken.space.crt;
										  ssl_certificate_key /etc/nginx/ssl/owncloud.rasenshuriken.space.key;</b>
										  
										  Path to the root of your installation
										  <b> root /var/www/owncloud.rasenshuriken.space/;</b>
										  set max upload size
										  client_max_body_size 10G;
										  fastcgi_buffers 64 4K;
										  
										  rewrite ^/caldav(._)$ /remote.php/caldav$1 redirect;
										  rewrite ^/carddav(._)$ /remote.php/carddav$1 redirect;
										                        rewrite ^/webdav(.*)$ /remote.php/webdav$1 redirect;
										  
										  index index.php;
										  error_page 403 /core/templates/403.php;
										  error_page 404 /core/templates/404.php;
										  
										  location = /robots.txt {
										  allow all;
										  log_not_found off;
										  access_log off;
										  }
										  
										  location ~ ^/(?:\.htaccess|data|config|db_structure\.xml|README){
										  deny all;
										  }
										  
										  location / {
										  The following 2 rules are only needed with webfinger
										  rewrite ^/.well-known/host-meta /public.php?service=host-meta last;
										  rewrite ^/.well-known/host-meta.json /public.php?service=host-meta-json last;
										  
										  rewrite ^/.well-known/carddav /remote.php/carddav/ redirect;
										  rewrite ^/.well-known/caldav /remote.php/caldav/ redirect;
										  
										  rewrite ^(/core/doc/[^\/]+/)$ $1/index.html;
										  
										  try_files $uri $uri/ /index.php;
										  }
										  
										  location ~ \.php(?:$|/) {
										                         fastcgi_split_path_info ^(.+\.php)(/.+)$;
										  include fastcgi_params;
										  fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
										  fastcgi_param PATH_INFO $fastcgi_path_info;
										  fastcgi_param HTTPS on;
										  fastcgi_pass php-handler;
										  }
										  
										      Optional: set long EXPIRES header on static assets
										  
										  location ~\* \.(?:jpg|jpeg|gif|bmp|ico|png|css|js|swf)$ {
										  expires 30d;
										  Optional: Don't log access to assets
										  access_log off;
										  }
										  
										  }
									- Link site config to sites available folder
										- ln -s /etc/nginx/sites-enabled/SUBDOMAIN.DOMAIN.com /etc/nginx/sites-available/SUBDOMAIN.DOMAIN.com
											- ln -s /etc/nginx/sites-enabled/owncloud.rasenshuriken.space /etc/nginx/sites-available/owncloud.rasenshuriken.space
										- sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/
										  DigitalOcean says it's this way round
								- Unzip and moving files
									- tar -xjf owncloud-x.y.z.tar.bz2
									- sudo cp -r /var/www/owncloud.rasenshuriken.space /usr/share/nginx/html/owncloud.rasenshuriken.space
								- Fix
									- sudo rm /etc/nginx/sites-enabled/default
									- Check syslog (/var/log/syslog) for messages about config file issues.
									- Maybe need apt-get install php5
										- in owncloud docs
										- **But this has apache?**
									- sudo apt-get install apache2 mysql-server libapache2-mod-php5
									- sudo apt-get install php5-gd php5-json php5-mysql php5-curl
									- sudo apt-get install php5-intl php5-mcrypt php5-imagick
									- sudo chown -R bakashi:bakashi /usr/share/nginx/html/owncloud.rasenshuriken.space
							- https://www.digitalocean.com/community/tutorials/how-to-optimize-nginx-configuration
							- nginx [https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-server-blocks-virtual-hosts-on-ubuntu-14-04-lts](https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-server-blocks-virtual-hosts-on-ubuntu-14-04-lts)
						- Nginx glossary
						  collapsed:: true
							- sudo systemctl restart nginx
								- 1 Backlink
									- See [sudo systemctl restart nginx](https://workflowy.com/#/8c29de71ec97)
					- Learning Resources
						- https://www.digitalocean.com/community/tutorials/apache-vs-nginx-practical-considerations
						- https://www.digitalocean.com/community/tutorials/understanding-nginx-http-proxying-load-balancing-buffering-and-caching
						- https://www.digitalocean.com/community/tutorials/understanding-and-implementing-fastcgi-proxying-in-nginx
				- Apache
				  collapsed:: true
					- cd /etc/apache2/sites-available/mysite (one by one)
					- nano virtual hosts file
					- Apache https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-14-04-lts
					- Apache virtual hosts (for multiple WordPress sites)
					  https://www.digitalocean.com/community/tutorials/how-to-set-up-multiple-wordpress-sites-on-a-single-ubuntu-vps
			- _Related:_ Installing a Control Panel
			  intralink2:: [A simpler way to organize your work - Workflowy](https://workflowy.com/#/99d70a5de329)
		- _[Learning Resourcces]_
		  collapsed:: true
			- https://www.reddit.com/r/devops/
			- Uber tech stack
				- https://eng.uber.com/tech-stack-part-one/
				- https://eng.uber.com/tech-stack-part-two/
				- https://eng.uber.com/soa/
			- Many advanced stuff here
				- https://github.com/Netflix
				- Pivotal Cloud Foundry github
			- https://github.com/codenvy-legacy/container-devops
		- _{Archive}_
		  collapsed:: true
			- Overview of the different infrastructure/software types
			  https://www.safaribooksonline.com/library/view/terraform-up-and/9781491977071/ch01.html
	- Dashboards/Monitoring
	  collapsed:: true
		- Monitoring System
		  id:: 6463499c-18cf-49dd-a6f7-593e7aded1d5
		  collapsed:: true
			- Transaction/Web Application Monitoring
			  collapsed:: true
				- SaaS
				  collapsed:: true
					- Dynatrace
					  Gianni says it's AI-enhanced and way better than Zabbix, ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) etc
					- New Relic
					  collapsed:: true
						- New Relic Synthetics for automated tests
							- $69/mo for 10k tests
							  https://newrelic.com/synthetics/pricing
							- There are 4 different monitors available - Ping, Simple Browser, Scripted Browser, and API Test.
								- Ping and Simple Browser monitors: To set these up, simply input the URL, choose the locations and frequency for this monitor, and hit create.
								- Scripted Browser and API Test monitors: To set these up, you have to choose your locations and frequency, input your script into the script editor, and then hit create.
							- https://docs.newrelic.com/docs/synthetics/new-relic-synthetics
							- Need to learn node.js and write the script by hand
						- Get code-level visibility by integrating with our New Relic APM solution.
						  https://newrelic.com/application-monitoring
							- ($200/mo for monitoring a t2.xlarge instance, $25/mo for t2.nano)
							  https://newrelic.com/application-monitoring/pricing
					- https://anturis.com/pricing/
					- https://www.uptrends.com/pricing
					- http://webapplicationmonitoring.net/
					- dotcom-monitor
					  collapsed:: true
					  https://www.dotcom-monitor.com/web-application-monitoring-tools/
						- Fairly expensive ($78/mo for 10 tasks every 180 mins, $107 every 60m, $160 every 15m)
						  http://i.imgur.com/6fYdVxp.png
						- https://userauth.dotcom-monitor.com/Public/PricingSelect
					- Pingdom (transaction monitor)
					  collapsed:: true
						- https://www.pingdom.com/product/transaction-monitoring
						- https://help.pingdom.com/hc/en-us/articles/213063645-Transaction-Check-Cheat-Sheet
						- http://royal.pingdom.com/2013/02/06/monitor-login-form-submissions-pingdom-transaction-monitor/
						- Very expensive per transaction check
						  https://www.pingdom.com/pricing
				- _Open-source_
				  collapsed:: true
					- _Browser automation_
					  id:: 6360e332-3615-46d4-b233-fee7e35bfbbd
					  collapsed:: true
					  AKA web scraping
						- Pros/Cons
						  collapsed:: true
							- Pros
								-
							- Cons
								-
							- Unclear
								- It makes it easier to use/abuse on a wide scale
									- Abusive how? Headed chrome can be automated, as can wget. Its bizarre to ask a client side program to implement server-side controls for users you want to allow on your site but throttle.
							- Comparisons
								-
							- Related: ((63f4bf2e-0811-427e-a54b-1b9b38963017))
						- _Both fairly easy to use_
							- ((6360f2aa-b95c-4675-b0c4-493f0b7f8ae5))
							- [Playwright](https://github.com/microsoft/playwright)
							  collapsed:: true
								- Newer than ((6360f2aa-b95c-4675-b0c4-493f0b7f8ae5)), smaller dev community?
						- [Puppeteer](https://github.com/puppeteer/puppeteer)
						  id:: 63904f39-ea05-45f2-8aac-f9be943f1b1f
						  collapsed:: true
							- [Note: doesn't work with `create-react-app`, instead set it up on the backend. Because frontend can't open an embedded browser](https://stackoverflow.com/questions/55031823/how-to-make-puppeteer-work-with-a-reactjs-application-on-the-client-side)
							- Documentation
								- Tips
									- How to save entire HTML
									  `const html = await page.content();` OR
									  `let bodyHTML = await page.evaluate(() => document.body.innerHTML);`
										- `const html = await page.content();`
											- This doesn't return the server-side html (equivalent of right click » show source)
											- It does return the rendered DOM (equivalent of the DOM shown in the devtools) (ie: js dom)
										- Note: `outerHTML` alternatively will also store the `<head>`
										- It's an object, to serialise to string:
										  `new XMLSerializer().serializeToString(document.doctype) + document.documentElement.outerHTML;`
							-
						- PhantomJS
						  collapsed:: true
						  Headless version of ((6463499c-17bc-43d8-8319-f0081946d631))
							- https://code.tutsplus.com/tutorials/headless-functional-testing-with-selenium-and-phantomjs--net-30545
							- PhantomJS on ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
								- https://stackoverflow.com/questions/34645131/how-do-i-run-phantomjs-on-aws-lambda-with-nodejs
								- https://github.com/ryfeus/lambda-packs/tree/master/Selenium_PhantomJS
						- [Selenium](http://www.seleniumhq.org/)
						  id:: 6463499c-17bc-43d8-8319-f0081946d631
						  collapsed:: true
						- Chromeless
						  collapsed:: true
							- https://github.com/graphcool/chromeless
						- [Serverless Chrome](https://github.com/adieuadieu/serverless-chrome)
						  collapsed:: true
							- Silly question how do you get Chrome installed in ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))?
								- You include the Chrome binary with your Lambda deploy package and execute it with a wrapper script. It does take some work to make a headless Chrome build that works for Lambda, but fortunately, there's a project called Serverless Chrome that supplies binaries that work on Lambda (and probably Azure Functions and whatever Google calls their own version).
							-
						- ((63f8fe5a-e718-4363-aba5-549a93eec7a7))-powered
							- [GitHub - ScrapeGraphAI/Scrapegraph-ai: Python scraper based on AI](https://github.com/ScrapeGraphAI/Scrapegraph-ai)
							- [LaVague](https://github.com/lavague-ai/LaVague)
							  LLM automates ((6463499c-17bc-43d8-8319-f0081946d631))
							- https://jamesturk.github.io/scrapeghost/
							- [GitHub - lucgagan/auto-playwright: Automating Playwright steps using ChatGPT.](https://github.com/lucgagan/auto-playwright)
							  collapsed:: true
								- [Revolutionizing Playwright Tests with AI](https://ray.run/blog/auto-playwright)
								-
							- [GitHub - Skyvern-AI/skyvern: Automate browser-based workflows with LLMs and Computer Vision](https://github.com/Skyvern-AI/Skyvern)
							- [GitHub - vignshwarar/AI-Employe: Create browser automation as if you were teaching a human using GPT-4 Vision.](https://github.com/vignshwarar/AI-Employe)
							- [GitHub - handrew/browserpilot: Natural language browser automation](https://github.com/handrew/browserpilot)
							- [GitHub - KillianLucas/open-interpreter: A natural language interface for computers](https://github.com/KillianLucas/open-interpreter/)
							  id:: 65f556bd-c181-402c-82b3-57da2c8561c2
							- https://github.com/TaxyAI/browser-extension
							-
						- [Learning Resources]
							- 2023 Q1 - [new flag for Chrome which makes bot detection harder](https://news.ycombinator.com/item?id=34864589)
							- [Ask HN: What are the best tools for web scraping in 2022?](https://news.ycombinator.com/item?id=32409632)
						- Related: ((6360f0ed-dac2-4efc-941e-631b8015a8a6))
					- Nagios
					  collapsed:: true
					  https://www.nagios.org/ / https://www.nagios.com
						- well Nagios is a pain, if this should be used we suggest the usage of Check_MK (nagios clone)
					- Zabbix
					  collapsed:: true
					  Active/Passive Monitoring + Alerting
						- complex monitoring solution including data gathering, data archiving
						  (trends, compaction,...), visualizer with dashboards, alerting and some
						  management support for alerts escalations. (have a look at collectd,
						  prometheus, cacti. They are all able to gather data)
						- Zabbix is a monitoring solution, which works with aktive+passige agents,
						  which can "measure" things on your systems. Based on those measured
						  values, you can take actions/alerting etc. In addition to this, it plots
						  nice graphs with disk/cpu etc. usage
					- Cabot
					  collapsed:: true
					  http://cabotapp.com/
						- Self-hosted, easily-deployable monitoring and alerts service - like a lightweight PagerDuty
					- Openduty
					  collapsed:: true
					  https://github.com/ustream/openduty
						- Openduty is an incident escalation tool, just like Pagerduty .
				- Cheaper versions
				  collapsed:: true
					- PhantomJS on Lambda
					  intralink2:: https://workflowy.com/s/ES1H.nMZlZizIUJ#/9933712a3826
			- Elastic Stack
			  collapsed:: true
			  AKA ELK Stack / Elasticsearch, Logstash, and Kibana
				- log management platform
				- Elasticsearch is a NoSQL database that is based on the Lucene search engine
				- Logstash is a log pipeline tool that accepts inputs from various sources, executes different transformations, and exports the data to various targets
				- Kibana is a visualization layer that works on top of Elasticsearch.
			- Kibana
			  https://www.elastic.co/products/kibana
			- Grafana (and Graphite)
			- [Prometheus](https://prometheus.io/)
			  id:: 6463499c-d02a-43fd-853b-2a96df5b9eba
			- Remote Management & Monitoring
			  collapsed:: true
				- Pros/Cons
					- Cons
						- SolarWinds hack
						- Kaseya hack
						  [https://news.ycombinator.com/item?id=27718529](https://news.ycombinator.com/item?id=27718529)
						- Management/access should instead be handled through VPNing into the network, using rotating keys or TOTP auth
						- Monitoring should be ingest-only, with reports coming sent from each server to a central server
			- Grafana + InfluxDB
				- Setup a Grafana server with Influxdb, and install "collectd" on each vps/dedi to collect stats and push them to influxdb. This lets you have over time stats of cpu, bandwidth, disk, etc and build your own custom dashboard. If you want, you can also install Loki on the Grafana server and Promtail on each server for collecting logs e.g. web server logs and consolidating them in one place, extracting metrics from the logs, etc. Grafana has a data store+collection agent to support pretty much any use case.
			- ((6463499c-d02a-43fd-853b-2a96df5b9eba))
			- Glances
				- Git - [Glances - An Eye on your system](https://nicolargo.github.io/glances/)
			- Netdata
				- Git - [GitHub - netdata/netdata: Monitor your servers, containers, and applications, in high-resolution and in real-time!](https://github.com/netdata/netdata)
				  Home Page - [Netdata: Monitoring and troubleshooting transformed](https://www.netdata.cloud/)
			- _Comparison_
			  collapsed:: true
				- 1
					- Zabbix - complex monitoring solution including data gathering, data archiving (trends, compaction,...), visualizer with dashboards, alerting and some management support for alerts escalations. (have a look at collectd, prometheus, cacti. They are all able to gather data)
					- Grafana - visualizer of data. It can read data at least from prometheus, graphite and elastics. Its primary goal is to visualize things in user defined dashboards and corelate things from possibly various sources. You can for example see cpu load (float time serie data from prometheus for example) with nice annotations refering to some special event in log file (loaded from elastics of course)
					- Kibana - visualization + analytics on logged data into elastics. Have a fast look at kibana discover to get idea. It is "must to have" tool when you need to search your logs (various services, various servers) in one place.
				- 2
					- Zabbix is a monitoring solution, which works with aktive+passige agents, which can "measure" things on your systems. Based on those measured values, you can take actions/alerting etc. In addition to this, it plots nice graphs with disk/cpu etc. usage
					- Kibana/Grafana on the other hand do get the informations from logs sent from your systems. They do not actively monitor things and also alerting/messaging is not the main focus of them. (If possible at all...?) They are however great at digging through all your logfiles.
					- So in short:
						- - Active/Passive Monitoring + Alterting = Zabbix
						- - Centralized log management = Grafana/Kibana
					- It also is not one or the other, you can also combine them
		- _Admin dashboards_
		  id:: 6463499c-a3c8-4548-a7e9-8b2ef09bef9a
		  collapsed:: true
			- # FOSS
				- [GitHub - gethomepage/homepage: A highly customizable homepage (or startpage / application dashboard) with Docker and service API integrations.](https://github.com/gethomepage/homepage)
				- ((664c986e-e8a4-49c5-b2cf-dbc11e3122de))
				- [GitHub - obazoud/awesome-dashboard: A curated list of amazingly awesome dashboards/visualization resources.](https://github.com/obazoud/awesome-dashboard)
				- [GitHub - glanceapp/glance: A self-hosted dashboard that puts all your feeds in one place](https://github.com/glanceapp/glance)
			- # Proprietary
			- Metronic Admin Dashboard
			  collapsed:: true
				- Metronic built with HTML, SASS, jQuery, Bootstrap 4 and Angular 4 and it can be used to build any web application regardless used server side languages and technologies. To run the Metronic build tasks you will need to install nodejs, npm, bower, angular-cli and others.
				- http://themeforest.net/item/metronic-responsive-admin-dashboard-template/4021469 $27
				- Link it up to social media
				- Look at HootSuite for ideas
				- http://www.makeuseof.com/tag/automate-informative-google-analytics-reports-custom-reporting/
				- It has inbuilt Asana-like tool
				  http://keenthemes.com/preview/metronic/theme/admin_1/app_todo_2.html
			- Website with embedded elements
			  collapsed:: true
				- WordPress front end?
					- Embed WorkFlowy current tasks list, though copy URL may be disabled
					- WorkFlowy embed
					  #WorkFlowy https://workflowy.com/#/4cf368b7e7aa
					- Embeddable Software
					  collapsed:: true
						- WorkFlowy
						- Chat
							- Hypothesis
							- Instant chat
							  https://tlk.io/
							- Discourse
							  https://meta.discourse.org/t/embedding-discourse-comments-via-javascript/31963
							- Gitter
							  https://sidecar.gitter.im/
							- Riot
							- Chatlio (Slack integration)
							  https://chatlio.com/
						- Files
							- HackMD
							  intralink2:: https://workflowy.com/#/a9b0ea96e3b5
				- WordPress backend powered by admin menu editor
				- HTML?
			- https://www.knackhq.com/
			- AdminLTE
			  https://almsaeedstudio.com/themes/AdminLTE/index2.html
			- "Dashboard of myself
			  https://www.reddit.com/r/productivity/comments/5slzl9/the_dashboard_of_myself/
			- Related: ((663904b1-af62-4dbb-9e10-edf132813c19))
		- _Homelab Services/HTPC_
		  collapsed:: true
			- Organizr
			  https://github.com/causefx/Organizr
				- https://cloud.githubusercontent.com/assets/16184466/23820730/728ccad4-05dc-11e7-8b9a-717f41485c73.png
				- https://cloud.githubusercontent.com/assets/16184466/23820734/922b077a-05dc-11e7-80da-901d6a398ac1.png
	- Paper Management
	  collapsed:: true
	  AKA paperless management
		- _Suggested stack_
			- Camera app (or CamScanner or Text Fairy) + self-hosted Paperless or Mayan EDMS
		- _Components_
			- Scanning choice
			  collapsed:: true
				- _Physical scanner_
					- High detail
					  the detail a real scanner can provide for photographs and OCR applications
				- _Mobile camera app_
					- Easier and faster
					- Cheaper
					- Portable whilst travelling
			- Apps - Optical Character Recognition (OCR) for images (to make PDFs/OCR'd images)
			  collapsed:: true
				- _Open-source_
				  collapsed:: true
					- _Web app_
						- Pros/Cons
						  collapsed:: true
							- Cons
								- To use OCR-enabled search the data can't be encrypted, so either needs special search or a locally hosted server
								  e.g.
									- Paperless encrypts (GnuPG) the original files via the consumption script, the OCR'd text is not encrypted and is therefore stored in the clear (it needs to be searchable, so if someone has ideas on how to do that on encrypted data, I'm all ears). This means that Paperless should never be run on an untrusted host. Instead, I recommend that if you do want to use it, run it locally on a server in your own home.
						- Paperless
						  collapsed:: true
							- https://news.ycombinator.com/item?id=37800951
							- [paperless-ng](https://github.com/jonaswinkler/paperless-ng)
							- Original Paperless (no longer under dev but basically feature complete)
							  collapsed:: true
								- [https://github.com/danielquinn/paperless](https://github.com/danielquinn/paperless)
								- [https://paperless.readthedocs.io/en/latest/](https://paperless.readthedocs.io/en/latest/)
								- How it works
									- Buy a document scanner like this one (used by me) or this other one recommended by another user.
									- Set it up to "scan to FTP" or something similar. It should be able to push scanned images to a server without you having to do anything. If your scanner doesn't know how to automatically upload the file somewhere, you can always do that manually. Paperless doesn't care how the documents get into its local consumption directory.
									- Have the target server run the Paperless consumption script to OCR the file and index it into a local database.
									- Use the web frontend to sift through the database and find what you want.
									- Download the PDF you need/want via the web interface and do whatever you like with it. You can even print it and send it as if it's the original. In most cases, no one will care or notice.
								- Components
									- This is all really a quite simple, shiny, user-friendly wrapper around some very powerful tools.
									- ImageMagick converts the images between colour and greyscale.
									- Tesseract does the character recognition.
									- Unpaper despeckles and deskews the scanned image.
									- GNU Privacy Guard is used as the encryption backend.
									- Python 3 is the language of the project.
										- Pillow loads the image data as a python object to be used with PyOCR.
										- PyOCR is a slick programmatic wrapper around tesseract.
										- Django is the framework this project is written against.
										- Python-GNUPG decrypts the PDFs on-the-fly to allow you to download unencrypted files, leaving the encrypted ones on-disk.
								- There's another project out there called Mayan EDMS that has a surprising amount of technical overlap with Paperless. Also based on Django and using a consumer model with Tesseract and Unpaper, Mayan EDMS is much more featureful and comes with a slick UI as well, but still in Python 2. It may be that Paperless consumes fewer resources, but to be honest, this is just a guess as I haven't tested this myself. One thing's for certain though, Paperless is a much better name.
								- 3rd party desktop app (requires a Paperless server)
								  https://github.com/thomasbrueggemann/paperless-desktop
							- [paperless-ngx](https://news.ycombinator.com/item?id=37800951)
						- Paperless-ng. Nice to have a fully searchable library of all my paperwork.
						- Mayan EDMS
						  collapsed:: true
							- https://mayan.readthedocs.io/en/latest/
						- Nextcloud OCR
						  collapsed:: true
						  Uses tesseract-ocr and OCRmyPDF
							- https://apps.nextcloud.com/apps/ocr
					- _Android_
						- Pros/Cons
						  collapsed:: true
							- Cons
								- Unsuited for search of many documents easily
								- Unsuited for uploading large documents eg hundreds of pages
						-
						- Text Fairy
						  https://github.com/renard314/textfairy/blob/master/README.md
						- Character Recognition (not updated since 2014)
						  collapsed:: true
							- OCR software based on Tesseract library to perform character recognition on images selected from the gallery or captured from the camera. Recognition results can be edited or copied for export
							- Extract text from images
							- https://gitorious.org/character-recognition/character-recognition
						- OpenNoteScanner
						  collapsed:: true
							- Pros/Cons
								- Pros
									- No OCR - doesn't allow copying text from the image
								- Cons
									- Basically just a private camera + gallery
									- Can't yet process existing images (must instead take a picture of them using it's camera feature)
									  https://github.com/ctodobom/OpenNoteScanner/issues/20
							- Scans text, including handwritten
							- [https://github.com/ctodobom/OpenNoteScanner](https://github.com/ctodobom/OpenNoteScanner)
							-
							- List
								- Compared to CamScanner, just for example, Open Scan Note:
									- has better recognition of what it's looking at (understands it's a document and catches the right shape)
									- produces grainer images of documents it catches under the same lighting conditions
									- produces decent (not excellent) scans in bright environments
									- produces noticably lower-quality scans (e.g. of text) in medium-well lit environments, compared to CamScanner
									- does not stamp the scan with branding, unlike CamScanner and other free apps of this sort
									- has more limited options for combining taken scans into a single .pdf document.
									- By contrast, CamScan does brand scans you take with it and needs (very) slight assistance in selecting appropriate boundaries for the objects it is asked to scan. But it does allow you to combine several pages into one.
									- Both apps have a menu from which you can share your document (E.g. to Evernote, Seafile, Tresorit or whatever else you happen to have an account with).
						- See [Text Fairy (OCR Text Scanner)](https://workflowy.com/#/aa39e5272623)
						  #Phone
						- _Proprietary Android apps_
						  collapsed:: true
							- CamScanner [found to have a backdoor]
							- [https://swiftscan.app/en/index.html](https://swiftscan.app/en/index.html)
					- Browser extension
						- See [Copyfish - Free OCR Software](https://workflowy.com/#/b5250e695cd5)
						  #WebBrowser
			- Open source libraries
			  collapsed:: true
				- Tesseract OCR (accurate OCR engine)
				  https://github.com/tesseract-ocr/tesseract
				- Leptonica
				  http://www.leptonica.com/
					- pedagogically-oriented open source site containing software that is broadly useful for image processing and image analysis applications.
				- hocr2pdf
				  http://exactcode.com/opensource/exactimage/
					- Aims to be an alternative to ImageMagick with increased speed
					  https://github.com/ImageMagick/ImageMagick
					- Is a command line front-end for the image processing library to create perfectly layouted, searchable PDF files from hOCR, annotated HTML, input obtained from an OCR system.
			- Merging PDFs
			  collapsed:: true
				- Merge separate PDFs together
				  https://www.pdflabs.com/tools/pdftk-the-pdf-toolkit/
				- PDFCreator
				  https://f-droid.org/packages/de.baumann.pdfcreator/
		- \_Related: \_Knowledge Management
		  intralink2:: https://workflowy.com/#/16db34c48751
		- 3 Backlinks
			- See [Paper Management](https://workflowy.com/#/430149ff582b)
			  #Software
			- See [Paper Management](https://workflowy.com/#/430149ff582b)
			  #Infrastructure
			- See [Paper Management](https://workflowy.com/#/430149ff582b) eg <a href="https://workflowy.com/#/6c864ac6c93e">Paperless</a>
	- Cyber Warfare
	  collapsed:: true
		- _Two types:_
			- Espionage (spying)
			  AKA Cyber Espionage
			- Sabotage (disruption)
			  collapsed:: true
				- DDoS
				  AKA Distributed Denial of Service attack
					- DDoS Mitigation
					  id:: 6463499c-a471-4ad8-99a5-ab7a4a562fad
					  collapsed:: true
						- _Proprietary solutions_
							- AWS Shield
							- CloudFlare
							- Sucuri DDoS Protection
							- [KiwiFlare](https://kiwifarms.net/threads/kiwiflare.147312/)
							  collapsed:: true
								- OP
									- If you see this page, you are seeing what I've been working on the last two months. It is an anti-bot strategy I adopted from the haproxy-protection program by Thomas Lynch. I will explain the motivations behind this rewrite when we have fully migrated to it.
									  
									  The system is a proof-of-work using SHA256. This is similar to how cryptocurrencies work. When you are seeing this page, your browser is doing math to try and solve a very complicated question probabilistically. If you have multiple tabs open, they will all do work, but if one finds the answer, they will share it with the other tabs.
									  
									  One of the main advantages to this system to what I was doing before is more lax rate limiting. There is still rate limiting, but when you go over the limit, you will be presented another DDoS retarding page instead of a 429 error that will last several minutes. You probably wont even notice when this happens.
									  
									  In addition, this page is not based on IP. If you use a popular VPN, your authentication token is distinct to you and you will not encounter rate limiting from other people's activity.
									  
									  I've used ddosify to test the code and it is resilient to tens of thousands of connections. There's more testing to be done which is why I didn't deploy it to other servers yet.
								-
						- _Open-source_
							- [Deflect](https://github.com/deflect-ca/deflect)
							  collapsed:: true
							  anti-DDoS CDN system
								- Docs
								  collapsed:: true
								  https://docs.deflect.ca/en/latest/index.html
									- Our approach
										- We set up distributed reverse proxy caches on a collection of geographically distributed, low-cost hosting providers. Each host is functionally equivalent, though we are learning which are the best quality providers. Using short time-to-live DNS, distributed caching, IP blacklisting and other identified practices, Deflect services multiple clients simultaneously at a low cost for us and zero cost to them.
										- Design
											- Deflect is designed as a robust, low cost, non-proprietary and easily reproducible system to provide protection to multiple websites, which we call “Origins”.The system was created to remain neutral to different web servers, with some limitations detailed below. It is built using Debian 6 VPSs, which we call “Edges”, and a controlling server we call “Controller”. The caching component is handled by Apache Traffic Server.
										- Deflect in Action
											- To access a Deflect-protected website:
											  Enter the website’s address in the browser.The DNS will retrieve an alias pointing to our pool of edges. One of
											  these edges is then selected using round robin
											  DNS.If the requested address is permitted and the edge has the content of
											  the page in its cache, it will immediately reply to the browser. If
											  the content is not cached on the edge, it will be requested from the
											  origin and sent to the browser.If the address is not permitted, a notification page is displayed.
								- Source code
									- Components
									  collapsed:: true
										- Swabber
										  Simple pubsub-based IP banning engine. Subscribes to a ban publisher,
										  bans the IPs and then unbans them after a configured time period.
										  Designed to work in concert with Banjax.
										- BotHound
										  a system for collecting, storing, and calculating DDOS attack
										  characteristics in order to build attack fingerprints and classify
										  botnets.
										- Bundler
										  collapsed:: true
										  A utility for bundling resources in web pages into a single page by inlining them using the data URI scheme.
											- A utility for bundling resources in web pages into a single page by inlining them using the data URI scheme. It is designed to be easy to use in all kinds of scenarios, ranging from ones where one simply wants to produce a web page with certain resources bundled to scenarios where one would like to proxy resource requests, include caching functionality, modify request headers, and more.
											- Was used for Distributed Deflect
											  collapsed:: true
												- Distributed Deflectaims to allow volunteers to become part of the network and help protect online content. However, DDeflect must have a way to prevent volunteers from being able to monitor which content users are accessing, or to modify the content they are caching. Bundler is a core internal component of Distributed Deflect that aims to address these issues.
												- Bundler's task is to retrieve websites and produce an encrypted, authenticated bundle of the website content that can then be sent to the volunteer edges for caching. This way, volunteer edges can cache and deliver content without being able to break the content's confidentiality or integrity.
										- Bundler-proxy
										  collapsed:: true
										  A service for proxying requests via bundler, with support for remapping
										  based on host header and other features for encapsulating and providing
										  access to bundled content.
											- A service for proxying requests via bundler, with support for remapping based on host header and other features for encapsulating and providing access to bundled content.
										- Banjax
										  collapsed:: true
										  Apache Traffic Server Plugin performing various anti-DDoS measures,
										  including pattern-based banning, JavaScript browser challenge-responses,
										  captchas and authenticated access to uncached sections of websites.
											- Apache Traffic Server Plugin performing various anti-DDoS measures, including pattern-based banning, JavaScript browser challenge-responses, captchas and authenticated access to uncached sections of websites.
										- Edgemanage
										  collapsed:: true
										  Edgemanage is a tool for managing the HTTP availability of a cluster of web servers via DNS.
											- Edgemanage is a tool for managing the HTTP availability of a cluster of web servers via DNS. The machines tested are expected to be at risk of large volumes of traffic, attack or other potential instability. If a machine is found to be underperforming, it is replace by a more performant host to ensure maximum availability.
										- Learn2Ban
										  collapsed:: true
										  Learn2ban is a machine learning anti-DDoS tool.
											- Learn2ban is a machine learning anti-DDoS tool. It uses support vector machines to learn about HTTP traffic access patterns and then use this information to determine when attacks and happening and how.
										- Botbanger
										  collapsed:: true
										  A tool for using the data generated by Learn2Ban to actively classify
										  incoming traffic and use the generated classifications to determine
										  whether user activity is a malicious bot or a legitimate access
											- A tool for using the data generated by Learn2Ban to actively classify incoming traffic and use the generated classifications to determine whether user activity is a malicious bot or a legitimate access. Runs on edges in tandem with Banjax and Swabber. Soon to be reimplemented as part of Banjax.
										- autodeflect
										  collapsed:: true
										  Autodeflect is a set of Ansible recipes designed for use in the creation of independent standalone instances of Deflect.
											- Autodeflect is a set of Ansible recipes designed for use in the creation of independent standalone instances of Deflect. The recipes feature much of the configuration logic used in the production instances of the Deflect system and they can be used to greatly aid in the operation of a personal instance. While these recipes are still in their infancy, they will gradually allow for the complete automated configuration of a standalone Deflect instance.
										- eqbackup
										  collapsed:: true
										  Automating the deployment of differential, encrypted, off-site backups.
											- Not strictly related to the Deflect system but part of the broader infrastructure - a system for automating the deployment of differential, encrypted, off-site backups.
									- eQPress - WordPress managed hosting framework
									  https://equalit.ie/eqpress/
										- Console, like a plugin
										  https://equalit.ie/console-to-manage-eqpress-account/
											- PHP error log – contains a record of all PHP errors produced by plugins and themes.
											- Web server access log – contains a record of every file transferred from your site.
											- Web server error log – contains a record of every error encountered by the web server.
									- Repos
										- [GitHub - equalitie/DDeflect: Distributed Deflect; proxies Web traffic with protection against DDOS using voluntary edges. http://www.deflect.ca](https://github.com/equalitie/DDeflect)
										- [GitHub - equalitie/autodeflect: Ansible Deflect configuration automation](https://github.com/equalitie/autodeflect)
										-
								- The key elements of Deflect Labs are:
								  collapsed:: true
								  https://docs.deflect.ca/en/latest/_images/Deflect_Labs_Components-digraph.png
									- Deflect itself, by its nature a rich target for DDoS attacks.
									- BotnetDBP - a set of tools to actively and accurately differentiate between legitimate and malicious requests in order to further reduce the load on the Deflect network.
									- BotHound and Grey Memory - Bothound detects and classifies the attacks using the anomaly-detection and machine-learning tool Grey Memory.
									- Sniffles and Edgemanage provide an unfiltered view of inbound traffic, and give an unmistakable indicator of which site is targeted.
									- Opsdash - ElasticSearch cluster where the majority of collected data is stored and queried.
									- https://docs.deflect.ca/en/latest/deflect_labs_tech.html
								- Self-host
								  collapsed:: true
									- https://github.com/equalitie/autodeflect (Ansible recipes)
							- [FastNetMon](https://github.com/pavel-odintsov/fastnetmon)
							  collapsed:: true
								- https://www.webhostingtalk.com/showthread.php?t=1385247
								- https://fastnetmon.com/
							- [GitHub - bunkerity/bunkerweb: 🛡️ Make your web services secure by default !](https://github.com/bunkerity/bunkerweb)
							-
							- https://www.globalsign.com/en/blog/how-to-prevent-a-ddos-attack-on-a-cloud-server/
							- https://www.quora.com/Is-there-any-open-source-DDoS-protection-tools
						- _Strategy_
							- Hand-written rules
							  collapsed:: true
								- https://www.nginx.com/blog/mitigating-ddos-attacks-with-nginx-and-nginx-plus/
							- Machine-generated rules
							- Serve mainly cached content
							  collapsed:: true
								- Absorbs traffic through caching. Cache — or save —
								  versions of your content to serve to website visitors. This reduces
								  traffic requests to your website server and absorbs potential DDoS
								  attacks. For example, if many visitors want to view the same content on
								  your website (or, in a DDoS attack, an attacker is trying to overwhelm
								  your website with traffic), a service will fetch the content from
								  your website's server once and then serve a cached copy repeatedly.
								- ((67376780-c521-4602-bbcb-c23d12ced6a4))
								- Varnish
								- ((64634999-fc4a-4bf0-9d74-f8dc23708311))
					- DDoS Attacking
					  collapsed:: true
						- BlackHorizon is a clone of a piece of HTTP DoS software called GoldenEye, which was written by Jan Seidl in 2014. It was itself an expansion on the 2012 HULK project by Barry Shteiman. Unlike Seidl’s thoughtful adaptation and expansion of HULK, the BlackHorizon codebase mainly changes the ASCII art and the author’s name. When examined, it was clear that the functional components of the code were almost entirely unaltered from GoldenEye.
						- Bulletproof Hosts? used for command and control
						  No questions asked
							- Dmzhost Limited https://dmzhost.co
							- ((67376781-c0ff-4eb0-8a85-b6769861711d))
						- Software
							- Denial-of-service as a service
							  collapsed:: true
								- Some vendors provide so-called "booter" or "stresser" services, which have simple web-based front ends, and accept payment over the web. Marketed and promoted as stress-testing tools, they can be used to perform unauthorized denial-of-service attacks, and allow technically unsophisticated attackers access to sophisticated attack tools without the need for the attacker to understand their use.
							- Attack tools
							  collapsed:: true
								- In cases such as MyDoom the tools are embedded in malware, and launch their attacks without the knowledge of the system owner. Stacheldraht is a classic example of a DDoS tool. It utilizes a layered structure where the attacker uses a client program to connect to handlers, which are compromised systems that issue commands to the zombie agents,
								  which in turn facilitate the DDoS attack. Agents are compromised via
								  the handlers by the attacker, using automated routines to exploit
								  vulnerabilities in programs that accept remote connections running on
								  the targeted remote hosts. Each handler can control up to a thousand
								  agents.[21]
								- DDoS tools like Stacheldraht still use classic DoS attack methods centered on IP spoofing and amplification like smurf attacks and fraggle attacks (these are also known as bandwidth consumption attacks). SYN floods
								  (also known as resource starvation attacks) may also be used. Newer
								  tools can use DNS servers for DoS purposes. Unlike MyDoom's DDoS
								  mechanism, botnets can be turned against any IP address. Script kiddies use them to deny the availability of well known websites to legitimate users.[28] More sophisticated attackers use DDoS tools for the purposes of extortion – even against their business rivals
								- Slowloris
								  Aliases/Tools - Slowloris, Pyloris, Torloris
								- Fully Randomized NoCache Flood
								  Aliases/Tools - Hulk, GoldenEye, BlackHorizon
								- Joomla! Reflection DDoS
								  Aliases/Tools - DAVOSET, UFONet
								- WordPress XMLRPC Floods
								  Aliases/Tools - WordPress Pingback
						- Keywords
							- Load testing
								- RUDY (R-U-Dead-Yet)
									- https://sourceforge.net/projects/r-u-dead-yet/
						- Attack type (including variants and clones)
							- WordPress pingback
							- Joomla pingback
							- Slow Loris
							  collapsed:: true
								- Aliases/Tools
								- Slowloris, Pyloris, Torloris
								- Attack Type Exploits Obfuscation Attack Class Attack Rate
								- Layer 7 Denial of Service Connection exhaustion None Single-source Low
								- Slowloris is a DoS tool that was originally released in 2009.
								  It is unique among the other Layer 7 attacks we will be discussing in
								  this report because it does not focus on flooding the network with
								  traffic. Instead, it attempts to use up all the connections to a web server leaving none left for legitimate users.
								  This low number of connections allows Slowloris to attack a website
								  without drawing the same attention that a flood of traffic would.
								- SlowDroid
								  https://www.netsec.ieiit.cnr.it/?q=slowdroid
							- Fully Randomized
							- NoCache Flood
							- Cache Bypass flood
							- Python script flood
					- _[Learning Resources]_
					  collapsed:: true
						- https://en.wikipedia.org/wiki/Denial-of-service_attack
		- _Applications_
			- Industrial espionage
			  collapsed:: true
				- theft of trade secrets, bribery, blackmail and technological surveillance
				- "Moles", or trusted insiders
				- Agents and the process of collection
				  collapsed:: true
					- Economic or industrial espionage commonly occurs in one of two ways.
					  Firstly, a dissatisfied employee appropriates information to advance
					  interests or to damage the company. Secondly, a competitor or foreign
					  government seeks information to advance its own technological or
					  financial interest.[12] "Moles", or trusted insiders, are generally considered the best sources for economic or industrial espionage.[13]
					  Historically known as a "patsy", an insider can be induced, willingly
					  or under duress, to provide information. A patsy may be initially asked
					  to hand over inconsequential information and, once compromised by
					  committing a crime, bribed into handing over more sensitive material.[14] Individuals may leave one company to take up employment with another and take sensitive information with them.[15] Such apparent behavior has been the focus of numerous industrial espionage cases that have resulted in legal battles.[15] Some countries hire individuals to do spying rather than use of their own intelligence agencies.[16] Academics, business delegates, and students are often thought to be used by governments in gathering information.[17] Some countries, such as Japan, have been reported to expect students be debriefed on returning home.[17] A spy may follow a guided tour of a factory and then get "lost".[14]
					  A spy could be an engineer, a maintenance man, a cleaner, an insurance
					  salesman, or an inspector: anyone who has legitimate access to the
					  premises.[14]
					  A spy may break into the premises to steal data and may search through waste paper and refuse, known as "dumpster diving".[18]
					  Information may be compromised via unsolicited requests for
					  information, marketing surveys or use of technical support or research
					  or software facilities. Outsourced industrial producers may ask for
					  information outside the agreed-upon contract.[19]
					  Computers have facilitated the process of collecting information
					  because of the ease of access to large amounts of information through
					  physical contact or the Internet.
				- A "bag-op" refers to the use of hotel staff to access data, such as
				  through laptops, in hotel rooms. Information may be stolen in transit,
				  in taxis, at airport baggage counters, baggage carousels, on trains and so on.
				- Malware/spyware
				- DDoS
				- \_Related: \_Corporate Warfare
				  collapsed:: true
					- Lawfare
					- Patent wars
					- Low-grade corporate warfare is constantly being waged between
					  technology giants by "patent trolls, insider blogs and corporate talking
					  points".[11]
					  https://books.google.de/books?id=-lY4ZmDEA2sC&pg=PA32
					- Supply chain attacks in corporate warfare can be called supply chain interdiction.[12]
		- _Acquisition_
		  collapsed:: true
			- Cyber-arms or cyber-weapons industry - sale of software exploits, zero-days, cyberweaponry, surveillance technologies
				- OfflineTraditional arms producers and military services companies such as BAE Systems, EADS, Leonardo, General Dynamics, Raytheon and Thales have all expanded into the cybersecurity markets. However smaller software companies such as Blue Coat and Amesys have also become involved, often drawing attention for providing surveillance and censorship technologies to the regimes of Bashar al-Assad in Syria and Muammar Gaddafi in Libya.[8]
				  Suppliers of exploits to western governments include the Massachusetts firm Netragard.[9]
				  The trade show ISS World that runs every few months has been referred to as the 'international cyber arms bazaar' and the 'wiretappers ball'[10] focuses on surveillance software for lawful interception.
			- Notable markets
				- Cyber Arms Bazaar – a darknet market operating out of various Eastern European countries, trafficking crimeware and hacking tools[13] that has run since at least the year 2000.[11][14] Tom Kellermann, chief cybersecurity officer of Trend Micro estimates over 80 percent of financial sector cyberattacks could be traced back to the bazaar, with retail cyberattacks not far behind.[11]DarkodeTheRealDeal
			- Research certified ethical hacker
			- https://www.rand.org/content/dam/rand/pubs/research_reports/RR600/RR610/RAND_RR610.pdf
		- Penetration Testing
		  collapsed:: true
		  AKA ethical hacking, white hat hacking
			- Specialized OS distributions[edit]
			  Several operating system distributions are geared towards penetration testing.[17]
			  Such distributions typically contain a pre-packaged and pre-configured
			  set of tools. The penetration tester does not have to hunt down each
			  individual tool, which might increase the risk complications—such as
			  compile errors, dependencies issues, configuration errors. Also,
			  acquiring additional tools may not be practical in the tester's context.
			- Popular penetration testing OS examples include:
			  Kali Linux (which replaced BackTrack in December 2012) based on Debian LinuxParrot Security OS based on Debian and made by Frozenbox network\*BlackArch based on ArchLinux (having more than 1840 packages)BackBox based on UbuntuPentoo based on Gentoo LinuxWHAX based on Slackware Linux[18][19]
			- Many other specialized operating systems facilitate penetration
			  testing—each more or less dedicated to a specific field of penetration
			  testing.
			  A number of Linux distributions include known OS and Application vulnerabilities, and can be deployed as targets.
			  Such systems help new security professionals try the latest security
			  tools in a lab environment.
			- Examples include Damn Vulnerable Linux(DVL),
			  the OWASP Web Testing Environment (WTW), and Metasploitable.
			- Software frameworks[edit]
			  collapsed:: true
				- Metasploit Project
				- nmap
				- w3af
				- OWASP ZAP
				- Burp suite
				- NESSUS
					- https://en.wikipedia.org/wiki/Nessus_(software)
				- OpenVAS
					- http://www.openvas.org/
				- dSploit
				- Backbox
				- BackTrack
	- ((6829d6c7-1c9e-44e7-95e0-d334b25d03e7))
	- [Learning Resources]
	  collapsed:: true
		- Tech stacks
			- [https://panelbear.com/blog/tech-stack/](https://panelbear.com/blog/tech-stack/)
				- [https://news.ycombinator.com/item?id=25186342](https://news.ycombinator.com/item?id=25186342)
				- TypeScript, React and Bootstrap - frontend
				- Terraform, Docker, Kubernetes, CircleCI
			- Honestly, having gone down this path a year back, just use Heroku for your backend. Maybe Netlify if you want to separate your frontend and backend.
			- I recommend just writing a Docker container instead.
				- That's the ultimately portability and you can run in much more efficient environments (Cloud Run, Fargate, DigitalOcean Apps, [Fly.io](http://Fly.io)) and still scale up to large Kubernetes-based clusters if/when you need it.
				- Docker containers avoid the lock-in of a particular platform or CLI, and they can also be used as cheap CI/CD with multi-stage builds within the container.
			- Checkout [Hatchbox.io](http://Hatchbox.io), just started using it myself. You basically pay a flat monthly rate for their Heroku-esque management service and then pay for the servers on your provider of choice separately (e.g. DO, AWS, etc).
- _Comms_
  collapsed:: true
	- See [Email](https://workflowy.com/#/a097fcfcb31b)
	  #Email
	- VoIP
	  collapsed:: true
		- **TO DO **
		  collapsed:: true
			- [https://crypton.is - they accept cryptocurrency](https://workflowy.com/#/e9487986b163)
			- Try to signup to [voip.ms](http://voip.ms) with real info again
			- Ask the main 3 providers if I can get a virtual UK mobile number
				- A) Can buy UK mobile numbers directly (like TextMeUp, Vyke etc)
				  collapsed:: true
					- voipms - yes
					- twilio - yes
					- flowroute - no, US numbers only
				- B) Can port UK mobile numbers
				  collapsed:: true
					- voip - support ticket said I couldn't, but I haven't tested it
					  intralink2:: https://workflowy.com/#/0e1ec259a228
					- twilio - haven't asked
					- flowroute - sent a ticket
					  https://manage.flowroute.com/accounts/port_orders/coverage_lookup/
				- voip.ms had an error during sign-up, it wanted me to provide ID
				  collapsed:: true
					- probably because I faked address and used a voip number
					- **ALSO **tried a Tor account and that required manual verification too
			- Setup Twilio numbers
			- Setup voip.ms
		- _Tested - Android (receiving calls/texts test, mainly for 2FA)_
		  collapsed:: true
			- Skype - for the sake of completeness is reliable
			- TextMeUp
			  collapsed:: true
				- Cons
					- sometimes texts aren't received. Had problems with using Google Play to purchase a renewal so left it to expire after a year
					- XPrivacyLua has to unrestrict a lot of permissions because otherwise the app keeps crashing e.g. it needs to track you, use analytics etc
			- Vyke - reliable and quick text receiving
		- Getting a good vanity phone number
		  collapsed:: true
			- Some VoIP providers automatically offer 07 numbers
			  e.g. TextMeUp, Vyke
			- Porting a number
			  collapsed:: true
				- https://en.wikipedia.org/wiki/Local_number_portability
				- https://en.wikipedia.org/wiki/Mobile_number_portability
				- Note: geographic numbers start with 01 or 02
				  https://en.wikipedia.org/wiki/Telephone_numbers_in_the_United_Kingdom#Structure
				- National numbers = 03 or 08
			- Buy UK local phone numbers
			  collapsed:: true
				- https://www.ebay.co.uk/sch/i.html?_from=R40&_trksid=m570.l1313&_nkw=phone+number&_sacat=0
					- https://www.ebay.co.uk/itm/o2-UK-GOLD-VIP-BUSINESS-EASY-MOBILE-PHONE-NUMBER-DIAMOND-PLATINUM-SIM-CARD/323295737233?hash=item4b45ed7591:g:UxIAAOSwd~ZbhZW1
					- https://www.ebay.co.uk/itm/EE-GOLD-VIP-BUSINESS-EASY-MOBILE-PHONE-NUMBER-DIAMOND-PLATINUM-PAYG-SIM-CARD/323270928687?hash=item4b4472e92f:g:BLYAAOSwDrVbE9VD
		- SIP
		  collapsed:: true
			- _Android clients_
				- Linphone / Zoiper / SIPDroid apps
			- _SIP providers_
				- SIP providers that accept cryptocurrency
				  Session Initiation Protocol
					- SIP Trunking (bought with Bitcoin)
					  collapsed:: true
						- http://www.sip-dojo.com/what-is-sip/sip-trunking
						- SIP gateway that provides trunking service and can be bought with Bitcoin
							- https://www.letsbrik.co/
							  Browser or Android-based
							- https://www.bitphone.net/
							  Browser-based
							- https://www.callwithus.com/
							- https://www.swilliamtell.ch/
						- Asterisk as a VoIP gateway to PSTN
						- While Bitcoin has many privacy issues of its own, the Bitcoin community maintains a couple lists of "trunking" providers that allow you to obtain a PSTN phone number in exchange for Bitcoin payment.
						- http://kwlug.org/node/812
						- Ostel
						  OStel is a public testbed of the Open Secure Telephony Network (OSTN) project,
							- https://ostel.co/faq
							- ostel.co is a free SIP service run by the Guardian Project that supports only TLS and ZRTP, but does not allow outdialing to normal PSTN telephone numbers
						- ZRTP
							- http://zfoneproject.com/faq.html#zfoneis
					- NetTALK
					  collapsed:: true
						- https://beyondbitcoinx.net/news/nettalk-the-first-voip-provider-to-accept-cryptocurrency-payments-including-bitcoin-bitcoin-cash-ethereum-and-litecoin/459/
					- https://github.com/privacytoolsIO/privacytools.io/issues/520
				- _Assorted SIP_
					- £25 setup + £60/year SureVoIP
					  collapsed:: true
						- https://www.surevoip.co.uk/products/surevoip-single-user
					- £120/year Sipgate
					  collapsed:: true
						- https://www.sipgate.co.uk/basic/callpackages/uk-flat-allnet-uk
						- http://www.live.sipgate.co.uk/team/plans
					- £27 VoIPFone
					  collapsed:: true
						- https://www.voipfone.co.uk/prices_telephone_numbers.php
						- https://www.voipfone.co.uk/softphone_download.php
		- VoIP
		  collapsed:: true
			- _3rd-party Android apps_
				- Textable (supports Flowroute, VoIP.ms, Twilio, Bandwidth.com, Nexmo, Tropo, Plivo)
				  collapsed:: true
				  Also has a web app
					- https://play.google.com/store/apps/details?id=co.textable.textable&hl=en
					- Cons
						- I applaud your efforts, but I don't know about routing SMS through someone else's service. Unless you plan to open source the code, how do the users know you're not scooping up all the traffic that routes through the app? Obviously the app itself can communicate directly with providers (which could be verified by looking at the source), but the push notifications would need to route through your service.
						- Color me paranoid, but I wouldn’t want to wake up one day and there is a hefty bill for millions of spam messages sent using my auth tokens that somehow leaked out and got decrypted. Better safe...
					- Web app
						- https://app.textable.co/login
						- The concept is to store the messages in the cloud so that you can acces via web as well as an api to access it from your own CRM, etc
				- VoIP.ms SMS (supports voip.ms) [FOSS]
			- _Providers_
				- _Top recommended on subreddit VOIP_
				  collapsed:: true
					- [https://crypton.is](https://crypton.is) - they accept cryptocurrency
					- https://voip.ms/
					  collapsed:: true
						- What number
							- $4 for London geographic number (203)
							  https://voip.ms/phone-numbers/international/country/united-kingdom/gbr/geographic
							- $2.50 for UK national numbers
							  https://voip.ms/phone-numbers/international/country/united-kingdom/gbr/national
							- Porting numbers
							  https://wiki.voip.ms/article/Porting_a_Number
								- Only allows geographic and national numbers?
								- Customer support request: Unfortunately this rate center is not supported by our network, we have no carriers that cover this city. You can verify what rate centers are available by log in on your portal -> DID Numbers -> DID Portability -> Check availability. Unfortunately we cannot anticipate if a rate center will be available soon since this will depend directly from our carriers. We apologize for this inconvenience.
						- https://wiki.voip.ms/article/Getting_Started
						- _Clients_
							- VoIP SMS app
							- Any SIP client
					- Flowroute
					  collapsed:: true
						- https://www.flowroute.com
						- All their numbers start with 1 e.g. 1770691507
					- Twilio
					  collapsed:: true
						- Burner and Hushed literally just use Twilio
						- Has UK mobile numbers - and allows international SMS and voice calls
						  https://support.twilio.com/hc/en-us/articles/223183068-Twilio-international-phone-number-availability-and-their-capabilities
						- _Clients_
							- s
						- Setup
							- https://www.reddit.com/r/VOIP/comments/70d91m/using_twilio_phone_number_and_trying_to_connect/
							- https://www.reddit.com/r/twilio/comments/7ix8q4/any_voip_service_that_allow_twilio/
							- s
								- SIP URI
									- Equivalent to a SIP phone number and takes the form, sip:username@SIPDomain
								- Twilio SIP Domain
									- It takes the form {example}.sip.{region}.twilio.com
									- where {example} is specified by the customer and {region}is the data center where the registrar is located. Initially only us1.
					- [Fonoster](https://github.com/fonoster/fonoster) (FOSS Twilio alternative?)
					  collapsed:: true
						- [https://fonoster.com/](https://fonoster.com/)
						- [https://github.com/fonoster/fonoster](https://github.com/fonoster/fonoster)
				- Teli
				- DIDLogic
				- £7/year Vyke
				- £23/year TextMe Up
				  collapsed:: true
					- Previous app has 10mm dls and been running for years. Free text to UK and other places. Normal looking mobile number
						- Purchased credits never expire
						  https://textmeup.zendesk.com/hc/en-us/articles/220027067-Will-my-credits-expire-
				- $30/year Hushed
				  collapsed:: true
					- Can only receive calls from UK numbers
				- £121/year Vonage
				  collapsed:: true
					- https://www.vonage.co.uk/home/call-plans/plans/
		- Physical phone
		  collapsed:: true
			- You need a device called an Analog Telephone Adapter (ATA) to connect your cordless phone. Callcentric and VoIP.ms both require you to configure the ATA yourself instead of an auto configuration with services such as Vonage.
			- I suggest going with an Unlocked Grandstream Handytone 502. These will work with virtually any American or Canadian phone made post WWII as long as it is not made by Automatic Electric (their bells seem to be a bit harder to ring) and it has either a Touch Tone or rotary dial.
			- For Callcentric, you can use the Grandstream HT702 setup instructions for the HandyTone 502, EXCEPT, they don't tell you how to set an optimized dial plan (and therefore you must dial all calls with 1+Area Code+Number).
			- For reference, yes, you can have 10 (or even 7) digit dialing on Callcentric, they tell you otherwise so they don't have to provide the tech support.
		- https://www.sipgatebasic.co.uk/callpackages/uk-flat-allnet-uk
		- www.voipfone.co.uk/softphone_download.php
		- Unsorted
		  collapsed:: true
			- https://www.reddit.com/r/VOIP
			- http://www.1worldsip.com/desktop/faq.html
			- Comparisons
			  collapsed:: true
				- forums.moneysavingexpert.com/showthread.php?t=47695
				- https://www.moneysavingexpert.com/phones/cheap-overseas-calls#voipmob
				- https://www.telephonesystemsguide.com/sip-trunking/#pricing
				- http://uk.pcmag.com/internet-telephony-voip-products/41717/guide/the-best-voip-providers-and-phone-services-of-2017
				- https://www.softwareadvice.com/uk/voip/sip-trunking-comparison/
				- https://getvoip.com/sip-trunking/
				- https://www.voipreview.org/sip-providers
			- https://guardianproject.info/2010/05/26/how-to-setup-a-private-mobile-phone-system-for-android-and-beyond/
			- http://www.magicjack.com/plans.html
			- https://www1.pbxes.com/index_e.php
			- https://androidforums.com/threads/free-voip-calling-using-google-voice-sipdroid.252222/
			- https://www.vyke.com/login/
			-
		- 1 Backlink
		  collapsed:: true
			- Anonymous SIP providers that accept cryptocurrency - see [VoIP](https://workflowy.com/#/d03d7e27b3ef)
			  #Software
	- Wireless Networking
	  collapsed:: true
		- Wi-Fi
		  collapsed:: true
			- Applications
				- HTC Vive Wireless Adapter powered by Intel WiGig
					- Product
					  https://www.amazon.com/Vive-Wireless-Adapter-PC/dp/B07GKHNBCT
					- 60Ghz band, helping prevent any interference and running at low latency
					- https://en.m.wikipedia.org/wiki/Wireless_Gigabit_Alliance
					-
				- See meshnets
		- Emulated Radio
		  collapsed:: true
		  AKA Software-Defined Radio
			- Products
			  collapsed:: true
				- LimeSDR
				- LTE Femtocells (0.1W, 60ft, 6 users) can cost as little as $100.
				- Nokia Flexi Zone can cost <$200 (I think, didn't check) and they have integrated 3G/LTE/Wi-Fi
			- Applications
			  collapsed:: true
				- Greater than Wi-Fi range
					- Off the shelf 2.4 GHz 802.11ac (Wi-Fi) gear can easily do miles but that's only for point-to-point connectivity
				- I think mobile setups like base stations mounted on drones or high altitude platforms are really interesting. We’re currently looking at providing cellular connectivity to rescuers and rescuees at sea using a fixed wing drone.
				- Mobile/Cell technologies work better when not all stations are "visible" from each other - as the channel access control in 802.11 is fundamentally peer-to-peer (even with an AP)
				- Some of the major outdoor WiFi companies (Ubiquiti, Miktrotik) etc started out with 802.11 then moved to cellular-style (TDMA etc.) methods for this reason.
			- Related: Cellular Radio
			  collapsed:: true
			  #Phone https://workflowy.com/#/32f4252412af?q=Lte
				- intralink2:: https://workflowy.com/#/d435a0936492?q=Lte
				- intralink2:: https://workflowy.com/#/12dc50ede192?q=Lte
			- https://news.ycombinator.com/item?id=18569961
			- Private LTE Networks
			  collapsed:: true
				- It's estimated that private LTE-networks will become $27 billion market by 2024. That's roughly 330 thousand LTE base stations for private networks.
				- 5G is specially designed this kid of industry in mind, so more advanced applications come in addition to the LTE markets. For example, many factories can replace their physical networks with 5G private networks for automation and robotics.
				-
- _Web & Apps_
  collapsed:: true
	- Create a Website
	  collapsed:: true
	  #CreateAWebsite
		- Website Development
		  id:: 6463499b-1d87-47ca-8775-bad033fd6636
		  collapsed:: true
			- GitHub
			- _Self-hosted OR Hosted_
			  See [Code Collaboration platform (GitHub alternative)](https://workflowy.com/#/b65803f27b82)
			- VersionPress
			  Beta
		- Anonymous Domains
		  collapsed:: true
			- We can use AndroPlus paypal for sites which won't have Ruko address on it (i.e. not CNC, epoxy, modelling agency)
			  
			  For sites that do have Ruko home address on them:
			  Search 'bank mandiri' (or other indo bank) followed by 'domain name registry' - should be able to pay using a domestic bank transfer using fake details at the bank
			  
			  Buying Domain Anonymously
			  
			  1. find an indonesian domain registrar on google e.g. bank mandiri domain registrar
			     e.g. https://www.niagahoster.co.id/
			     Then do bank deposit with fake details (matching domain signup details) + take a pic of receipt
			  
			  -offshore domain service OR register your domain with fake details, you basically use a VCC (virtual credit card) that is created by someone that is preloaded with an amount you ask for. They are typically used to verify paypals with incorrect information to stay anonymous.
		- How to Setup a New Website
		  collapsed:: true
			- General
				- Setup a WordPress Site
				  collapsed:: true
				  #CreateAWebsite-WordPress-Setup
					- Setting up via Docker Compose
					  collapsed:: true
						- Stats - minimum 320MB needed
						  [https://i.imgur.com/lqtNtrG.png](https://i.imgur.com/lqtNtrG.png)
							- Caddy consumes ~70MB RAM
							- MySQL consumes 180MB
							- WordPress consumes 68MB
					- Create a Duplicate Site to Edit
					  collapsed:: true
						- CUsersBossDocumentsWORKDuplicator Pro - basic Divi site
						- Either:
							- https://managewp.com/how-to-create-a-local-copy-of-a-live-wordpress-site
						- OR:
							- Create subdomain named 'test' > copy main site all files into 'test >
								- in MySQL Databases create a new db 'test' > Scroll to the bottom add the database user to access all priveleges with 'test'
								- in phpmyadmin go to the original database being used by wp-config and export > open 'test' db and import
								- Edit WP-options > 1) SiteURL + 37) Home
								- May also require changing WP permalinks to default (and restart XAMPP)
					- How to develop a new site whilst keeping the existing one still online
					  collapsed:: true
						- Theme Test Drive plugin
							- http://wordpress.org/extend/plugins/theme-test-drive/
							- It makes it so that when I’m logged in, it shows me one theme, but it shows everyone else a different theme.
							- In this case it will show the average user the basic landing page, while I can write content and build out the primary site. Once everything is done and ready to launch all I have to do is turn off the plugin and activate my primary theme.
						- Copy site to a subdomain
						  Ideally on both I've done "WordPress installed in it's own directory"
						- Work on site offline (via XAMPP) then later upload
							- Moving Site to Local
								- Download SQL database through PhpMyAdmin
								- Download WordPress folder through web panel or FTP
								- Copy WordPress folder in 'htdocs' folder in XAMPP folder
								- Open wp-config.php file in a text editor and change
									- Change username to 'root'
									- Change password to '' (nothing)
									- MySQL hostname to 'localhost'
								- Open up localhost/phpmyadmin
									- Create a new table
									- Import SQL database
									- In 'wp_options' change options 1 and 2 to 'http://localhost/wp'
							- The only problem is links not getting properly updated and still directing to old site even once changed in phpmyadmin
							- Upload local site to live site
								- Once you've created your local site you can use the duplicator plugin to back it up and upload it on to your hosting account. It's free and available here http://wordpress.org/extend/plugins/duplicator/.
								- http://serverpress.com/news/using-duplicator-to-import-a-live-website/
								- Change Hostgator >a phpmyadmin > trial > wp_options > 1 siteurl: http://balivillasrus.com/trial and 37 home: http://balivillasrus.com + use original wp-config.php
					- Putting WordPress in it's own directory
					  collapsed:: true
						- WordPress > Settings > Permalinks > Postname
							- This creates a .htaccess file, which is needed
						- https://codex.wordpress.org/Giving_WordPress_Its_Own_Directory
					- cPanel/SSL
					  #SysAdmin https://workflowy.com/#/c052a4355787
					- Adding a New Domain to Self-Hosted cPanel
					  collapsed:: true
						- Add domain to ((67376781-c0ff-4eb0-8a85-b6769861711d)) DNS records
						  https://cloud.digitalocean.com/networking/domains
						- Create a New cPanel Account
							- flgx: make separate cpanel account for each domain pointing to the same IP
								- Addon Domain doesn't work as expected
								- - It's more secure for passing on freelancer login info
								- Downside is that it requires uploading the site to multiple cPanels potentially
							- WHM > Account Functions > Create new Account > fill in all details
							- List Accounts - make sure all columns correct (e.g. package). Otherwise use 'Modify an Account' to edit
							- Dedicated IP 'no'
						- Setup Mail
							- cPanel > Mail > Authentication
							- DigitalOcean > Networking > Add TXT records for the domain
								- Example SPF
									- @
									- "v=spf1 +a +mx +ip4:139.59.172.91 ~all"
								- Example DKIM
									- default.\_domainkey
									- "v=DKIM1; k=rsa; p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAuqitvSV1hPR9TAYVVwT6cc0fB6u7UeJoXBL43sK+YTv+iOgzKzxxOhGySczncKHUhMvVCfwTHS6yVrbGMnjVvrxdNBQSxsdY/ppoYC1YMgfs8Y9yogqtdd3j0J6GJeNQly5afs5x0ywxcfTeQLs4AQiUTvddC1aDhOt2F1eJINCZm5yQUCu77rGzk4zzfYBFh""eEGTzpNjBtmGg9TpWPywu2D5X5USbWNpgLLXTVOE6yNCs/Pex2uKW7PxoxKvI8FA9KOaRUYp8qMvi2cGF2kZPJ4IjuFwWSrtuxHWoEUcVr5yig6VAPH8dkXn1i+0j9eILCPH6bm4YCLLKRbLMKeeQIDAQAB"
									  Works
									- "v=DKIM1; k=rsa; p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAupYHcau1Ok1+Nfe8RL5WTHVSCDBuWH4Qx+ZGW/F+LPJNc1Jnzruj8gRWR4nCzvNotEM+cie8ASS5SJaiP/Al4vTiqVgrzuo9rlpOEcpXtJeHXIG23vwd1sehMuKQB+4/Oszhvh1Hshcs9n8bJLUcjrJVtR/O854nPWvqFackrPid2C+Zq/PfIevjRcK9ugNN5CkUcxygeGmtlHPi2az6UYQsn7BgYULm1TkONilN+PuU+92kEXpw8Xeo5ZsOcgPY38K48O4ftEq2e6eyHuf6SNp3OOWbhdUxK5ZIfWflEuFBmafFKkaTA2EVkY7IV3OVFt32/wG+D6A2Jd8ACbZiDwIDAQAB\;"
									  Doesn't work
						- Duplicator Installer
							- On cPanel open MySQL Databases > at bottom Set Password > copy the database and user names for installer
							- Hostname + port is on phpmyadmin http://i.imgur.com/8r3Jyqm.png localhost:3306
							- After run installer, i go to the file manager, i open > WP-INCLUDES > default-constants.php > and here modify the memory limits to 84M and 124M
						- Troubleshooting
							- Can't Addon Domain error
							  http://i.imgur.com/PTS9xnl.png
								- Go to WHM > Server Config > Tweak Settings > Domains > Allow Remote Domains ON
						- Use FTP to transfer files between domains?
						- /usr/local/apache/conf/httpd.conf
						- \_Related: \_Setup cPanel + SSL
						  intralink2:: https://workflowy.com/#/c052a4355787
					- Setting up WordPress Multisite
					  collapsed:: true
						- https://codex.wordpress.org/Create_A_Network
						- Pros/Cons
							- Pros
								- Less disk memory usage as plugins, themes etc are shared
								- Quicker access and maintenance - easily access all websites by logging in one time and managing all sites from one WordPress dashboard panel
							- Cons
								- Despite being on one WordPress install, hosting costs will reflect the need to host many websites.
								- Site administrators cannot install new themes or plugins and cannot edit the profiles of users on their individual sites. Only the Network Admin has the ability to perform these tasks in a WordPress network.
								- There is no way to restrict plugins on individual sites.
								- All themes are installed for the entire network. If you edit the code of one theme, you edit it for all sites using that theme.
								- Note: You can install plugins in order to allow each site to tweak their own CSS without affecting anyone else.
								- There are many plugins that aren’t WordPress Multisite compatible.
								- Changing hosts, or removing a single site from Multisite is very difficult thing to do.
								- Multisite network requires higher technical knowledge especially in the areas of server administration and network management.
								- Issues that affect one site can (potentially) bring the entire WordPress Multisite network down.
							- {archive}
								- https://managewp.com/blog/wordpress-multisite-vs-multiple-sites
				- Design a New WordPress site
				  collapsed:: true
					- Start:
						- Create a Duplicate Site to Edit
						  intralink2:: https://workflowy.com/#/f0892fdea4ba
						- How to develop a new site whilst keeping the existing one still online
						  intralink2:: https://workflowy.com/#/a87ac36b8ec2
						- Designing Process
						  collapsed:: true
							- Find the tech elements you need by browsing the web. Make a list--I want menus that work like this site, a shopping cart that works like that site, a home page that works like this one.
							- Create the entire site (or at least the critical elements) using Keynote on the Mac (PowerPoint works too, but Keynote is a little easier to work with). Begin by copying and pasting elements from other sites, but as you make progress, hire a graphic designer to create the elements you need. Keynote makes it easy to actually have spots on the screen link to other slides in the 'presentation', so the document you create will actually allow your team to click on various parts of the screen and jump to other pages.
							- Also works for mobile apps
							  http://keynotopia.com/
						- Install WordPress
						- Then install theme
						  collapsed:: true
							- WordPress Theme
							  #WordPressTheme
								- Ideal Features
								  collapsed:: true
									- Theme must have same size post excerpts on Blog main page (like ramit's site, cernovich, etc
									- Hide dates of posts and comments
								- Genesis Themes
								  collapsed:: true
									- Genesis Framework Pros
									  collapsed:: true
										- Pros
											- Genesis has a killer community support forum (over 101K sites to date) and tons of loyal users.
												- That’s because they have SEO capabilities built right into the theme and gorgeous advanced features like sliders, image galleries, and seamless integration with premium plugins like Gravity Forms.
											- Good framework base for designers to make their own custom themes on top of
											- Genesis Design Palette Pro (DPP) for customising design without code
												- Allows you to customize things like fonts, colors, spacing, etc. without any knowledge of code. If you’re the DIY type but are afraid to dig into your CSS files, I highly recommend using this plugin. DPP currently works with the Metro Pro, Minimum Pro, eleven40, Beautiful Pro, and Executive themes, and they’re rolling out support for more Genesis themes in the coming weeks.
												  http://www.theblogmaven.com/designpalettepro
											- Minimal code for speed and high security
									- Integrates with WooCommerce via Genesis Connect Plugin
									  https://wordpress.org/plugins/genesis-connect-woocommerce/
									- Child Themes
									  collapsed:: true
										- Generate Pro http://wallstreetplayboys.com/
										- Metro Pro https://boldanddetermined.com/
										- News Pro http://www.dangerandplay.com/
										- Parallax Pro
										  http://30daystox.com/
									- 3rd Party Child Themes
									  collapsed:: true
										- $80 one-site $200 unlimited http://www.simpleprothemes.com/flex/
									- StudioPress tutorials
									  collapsed:: true
										- https://web.archive.org/web/20140301184143/http://my.studiopress.com/setup/parallax-pro
									- http://bestblackhatforum.com/search.php?action=results&sid=986cdc5aec6115fccb061ac58bd49d05&sortby=&order=desc
								- Elegant Themes - Divi
								  collapsed:: true
									- $89 for everything + 1 year updates
									  https://www.elegantthemes.com/join.php
									- Their most popular one is Divi with Divi Builder
									  https://www.elegantthemes.com/gallery/divi/
										- http://www.howtobeast.com/ uses it - looks great
									- Extra Theme includes several new features
									  #LandingPage https://workflowy.com/#/1c173ca89b7d
									- Also available as a separate plugin with same features
									  #LandingPage https://workflowy.com/#/1c173ca89b7d
									- [downloaded in My Docs]
								- Themeforest
								  collapsed:: true
									- Avada
									  http://themeforest.net/item/avada-responsive-multipurpose-theme/2833226
									- X
									  http://themeforest.net/item/x-the-theme/5871901
									- Enfold
									  http://themeforest.net/item/enfold-responsive-multipurpose-theme/4519990
									- BeTheme
									  http://themeforest.net/item/betheme-responsive-multipurpose-wordpress-theme/7758048
										- But it uses it's own layout builder Muffin Builder
									- Jupiter
									  http://themeforest.net/item/jupiter-multipurpose-responsive-theme/5177775
									- Bridge
									  http://themeforest.net/item/bridge-creative-multipurpose-wordpress-theme/7315054
										- http://demo.qodeinteractive.com/bridge/demos/
									- The7 (integrates with Visual Composer)
									  http://themeforest.net/item/the7-responsive-multipurpose-wordpress-theme/5556590
									- http://themeforest.net/popular_item/by_category?category=wordpress
								- Getting themes for free
								  collapsed:: true
									- Lots of themes downloaded in My Docs..>..OPTIONAL
									- (use bestblackhatforum)
								- Also see landing page themes/page Builder plugins/etc
								  #LandingPage https://workflowy.com/#/5f19d15d7caa
						- Then install plugins
						  collapsed:: true
							- WordPress plugins
							  #WordPressPlugins https://workflowy.com/#/af67d298a0ce
					- More:
						- Divi Builder
						  #LandingPage https://workflowy.com/#/1c173ca89b7d
						- Design Choices
						  collapsed:: true
							- Color
							  collapsed:: true
								- Choose an action colour for links which contrasts with colour scheme of site
							- Images
							  collapsed:: true
								- Show author picture on article page?
								  collapsed:: true
									- Utilise halo effect
									- Roosh, Mike Cernovich, Victor Pride, Rollo Tomassi are all jacked and above average looks
									- Other writers eg journalists look ugly and they don't show pictures because it discredits them
								- Inline Photographs or images
								  collapsed:: true
									- > Pick photos that illustrate your words,
									- or add a different nuance to what youʼre saying with your words.
								- Featured picture
								  collapsed:: true
									- Large image, most of above the fold. Headline soft-coded (responsive theme) on top of it
										- Examples
											- Mark Manson
											  https://web.archive.org/web/20160416103849/http://markmanson.net/insecurity
											- Smart Passive Income
											  https://web.archive.org/web/20160416104005/http://www.smartpassiveincome.com/is-your-website-is-broken/
											- Mike Cernovich
											  https://web.archive.org/web/20160416105400/http://cernovich.com/unwinding-on-the-island-of-koh-samui-thailand/
										- Why
											- In the future we'll all use larger and higher definition screens eg like iMacs - this looks best on those now
											- Responsive - works for large desktops, tablets and mobiles
										- How
											- Divi allows soft coding the headline onto the featured pic
									- \_Related: \_Images
									  #Rewrite https://workflowy.com/#/0eeda73de6cc
							- Increase the font size of your opening paragraph
							  collapsed:: true
								- Fewer characters per line has a psychological effect on the way we view content: The fewer the characters, the easier the text is to comprehend and the less complex it seems.
								  source:: http://socialtriggers.com/perfect-content-width/
									- Typographical researchers, Bruijn eta al., discovered that people prefer shorter line lengths when reading content online because it appears more organized and easier to understand.
									- Going one step further, two other researchers, Dyson and Haselgrove, found that people comprehend shorter line lengths better than longer line lengths.
								- Examples
									- MarkManson.net
									- Smashing Magazine
							- Category Pages
							  collapsed:: true
								- Also for each category create a section above it to explain the category
									- - link to most popular/useful articles
							- HideMyWP plugin
						- Sliders (incl Vectors)
						  collapsed:: true
						  Vector Graphics: http://flaticon.com 64px
						  or http://iconfinder.com
						  
						  Changing Vector Colours
						  Direct select the area
						  Click on the 'Fill' square on the bottom left
						  Change the colour on the top-right
							- Creating Vectors in Adobe Illustrator
								- Click arrow next to Image Trace to expand box
								- In popout box click 'Outline' (top-right icon)
								- In advanced set it to ignore white
								- Adjust parameters
								- When ready click 'Expand' at top
								- Save for Web
								- Select any areas you want to make transparent by clicking on them then setting Opacity to 0%
								- _To Change Canvas size_ - Artboard icon above hand icon
							- Changing Vector Colours
								- Direct select the area
								- Click on the 'Fill' square on the bottom left
								- Change the colour on the top-right
						- Grids
						  collapsed:: true
							- Grid Elements (Visual Composer)
							  http://localhost/localsite/1/wp-admin/post.php?post=69&action=edit
							  
							  To create a scroll-over effect:
							  Go to Grid Elements > scroll down > Click on the 'Single Block' dropdown list next to Preview and Update
							  Blue Scale Out > 'Search' icon for Hover
							  
							  On the middle box change columns to 1 > Press the top '+' in the box > add Icon >
							  e.g. Font Awesome 'Search';
							- Divi - Image + Text modules
							- Plugins which allow pages
								- Essential Grid
								  Evidence http://tweetsave.com/themepunch/status/767624356814024708
									- Order it by Title (post-based = pages too)
									  https://www.themepunch.com/essgrid-doc/grid-item-display-order/
									- Link entire image to post
									  https://www.themepunch.com/essgrid-doc/grid-item-links/#link-whole-item
								- Ultimate Post Grid
									- Yes, every post, page or custom post type has an ID. You can use those to limit by specific pages: http://bootstrapped.ventures/wp-ultimate-post-grid/limit-posts/
								- UberGrid
									- https://codecanyon.net/item/ubergrid-responsive-grid-builder-for-wordpress/4851992
									- Choosing Page IDs
										- It is not supported "out of the box", but you can cheat on it by installing some kind of additional taxonomy (using this plugin for example: https://wordpress.org/plugins/simple-taxonomy/) and assign pages you want to this taxonomy. And after that - UberGrid can only pull posts / pages from that taxonomy.
								- uSquare - last choice
								  Fixed customisation
							- Archive - other plugins
								- More options
								  https://archive.is/uJJmf / https://webcache.googleusercontent.com/search?q=cache:https://elegantmarketplace.com/forums/topic/posts-display-your-wordpress-posts-pages-in-a-grid-layout/&gws_rd=cr&ei=82m6V8X0GsaOgAbJ67CoDQ
								- For full-width grids: Can use Divi Call to Action module (Image + button)
								  https://www.elegantthemes.com/blog/divi-resources/how-to-create-a-responsive-image-grid-with-the-divi-page-builder-and-the-call-to-action-module
						- Remove 'Posted by' meta info
						  collapsed:: true
							- You can remove the post meta from the top of posts by adding in the following CSS in “Custom CSS” box in Theme Options panel.
							- .entry-header .entry-meta { display: none; }
						- Hide blog post published date
						  collapsed:: true
							- In Divi Options
							- For non-Divi, it's a bit of custom CSS that can be found via google
						- Setup them as an editor
						  collapsed:: true
							- Add them as user in WP - level: editor
							- Hidden Costs: Editor vs Admin roles on website
							- Note: if they request more permissions then use - https://wordpress.org/plugins/user-role-editor
					- Content
						- Page jumps
						  collapsed:: true
							- https://en.support.wordpress.com/splitting-content/page-jumps
			- Specialised
				- How to Setup a Membership Site
				  #ProductCreation https://workflowy.com/#/02c5e6122c62
				- How to Create an eCommerce Site
				  collapsed:: true
					- Check out https://gumroad.com/
					- How to Create an eCommerce Dropship Store
				- Or a simple Landing Page website
				  #LandingPage https://workflowy.com/#/5f19d15d7caa
				- Decoupled Content Management System (CMS) Websites
				  id:: 634bc017-3f63-44a5-b15a-93811312aba7
				  collapsed:: true
				  AKA Headless CMS
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Allows use of admin CMS backend and a separate front-end which communicates via API eg JavaScript web app, native mobile app, a different CMS etc
							- WordPress dashboard (or other database-driven CMS backend) makes it easy to update content
							- Directly supports native apps/platform-agnostic
							- Easy to scale
							- Presentation can be handled in a variety of ways, from interactive JS frameworks like Angular, to static generators, to mobile apps, or even another CMS. Multiple frontends can peacefully coexist.
							- The content for the site is accessible via a web-service API, usually in a RESTful manner and in a mashup-friendly format such as JSON.
						- Cons
							- front-end editing capability (e.g. Divi)
							- Themes and templates
					- Comparison of types
					  collapsed:: true
						- Traditional / Coupled / Monolith CMS
						  collapsed:: true
						  https://img.storyblok.com/9sl2TsC4ICZE0qL2B7si5rcVpyc=/764x0/f/39898/c55bc0f4d9/traditional.png
							- WordPress, Drupal, Squarespace, Ghost, Joomla
						- Decoupled/Headless/API-driven CMS
						  collapsed:: true
						  https://img.storyblok.com/y59eoBOj1Y26gLBdhwEDDQ3HMF0=/764x0/f/39898/7cb3dc02a1/headless.png
							- Example platforms
								- Headless WordPress
									- https://medium.freecodecamp.org/off-with-their-heads-building-a-headless-wordpress-to-manage-content-bb04e6b2a792
									- https://github.com/DrewDahlman/headless-wordpress
									- https://github.com/postlight/headless-wp-starter
									- https://blog.daftcode.pl/wordpress-as-a-headless-cms-b4144c626695
								- Headless Drupal
								- Storyblok
								  SDKs available in Javascript, Node.js, Ruby and PHP currently but it supports any language via API
									- https://www.storyblok.com/x
							- A headless CMS has its front-end part removed, and what still remains is content delivery via an API or static content files, some would also name those content management systems “API driven CMS”.
							- Its focus is just on storing and delivering the content, and provide some kind of CRUD part. This means that the content of a headless CMS can be used on a website, an app, a wearable device or even your new high-end toaster.
							- We know that more and more websites are built with the headless CMS architecture, even WordPress tries to change from being a monolith to an API-driven CMS the so-called “headless WordPress” or “Headless Drupal”. Both of these options try to make the CMS work in a way that they were not designed for. In fact, they won’t scale that properly, since their monolithic nature doesn’t allow them to be as extensible and performant as needed.
							- The technical view on a headless content management system would be:
							- An open content management API
							- A completely free choice of technology for developers to work with
							- Reuse of content for different systems out of the box
							- Mix up and match with existing CMS, E-commerce or other systems.
					- five ways of decoupling:
					  collapsed:: true
						- Static Generator/Renderer
						  https://pantheon.io/sites/default/files/decoupledcms-what-can-you-do.png
						- Hybrid
						  https://pantheon.io/sites/default/files/decoupledcms-what-can-you-do.png
						- “Single Page” App
						  https://pantheon.io/sites/default/files/decoupledcms-what-can-you-do.png
						- Native Mobile App / IOT
						  https://pantheon.io/sites/default/files/decoupledcms-what-can-you-do.png
						- CMS on CMS
						  https://pantheon.io/sites/default/files/decoupledcms-what-can-you-do.png
						- Static: the user-facing website is built via a static site generator that pulls from the CMS, allowing clean, elegant markup. Little to no end-user interactivity, but great for beautiful and scalable sites.
						- Hybrid: a portion of the website is highly interactive and communicates with the CMS via API. This is great for advanced editorial tools, calculators, or dashboards.
						- Single page app: the end-user experience is a complete application-in-browser, usually leveraging one of the newer JS frameworks such as Angular, Ember, or Backbone.
						- Native app: the frontend is a native mobile app. Users may or may not also interact directly with the website.
						- CMS2: you can even decouple a CMS with another CMS! This allows you to create a strong separation of concerns between content and layout/presentation, while still using familiar tools for both.
					- ((6396fb64-9aeb-4ee3-bf46-849eac2fb748)) : ((635fba72-d8b2-4372-b1f9-ce7a107f2df7))
					  collapsed:: true
						- {{embed ((635fba72-d8b2-4372-b1f9-ce7a107f2df7))}}
					- wReader on AngularJS
					  https://premium.wpmudev.org/blog/delivering-wordpress-content-with-web-apps-using-angularjs/
					- Sample web app 2
					  https://premium.wpmudev.org/blog/naked-wordpress-and-web-apps/
					- [Learning Resources]
						- [Slack](https://schoolofcodebootcamp.slack.com/archives/C6TJK2J4T/p1679385863309639)
						- https://pantheon.io/decoupled-cms
					- {Archive}
					  collapsed:: true
						- https://www.storyblok.com/tp/coupled-decoupled-and-headless-content-management-systems
		- Optimisation and Enhancement
		  collapsed:: true
			- WordPress Plugins
			  collapsed:: true
			  #WordPressPlugins
				- _Categories_
					- Every Site (mandatory)
					  collapsed:: true
						- Security
						  collapsed:: true
							- _General_
								- _Comparison_
								  collapsed:: true
									- http://researchasahobby.com/best-security-plugin-for-wordpress-combination
									- Spreadsheet of features
									  https://docs.google.com/spreadsheets/d/1Z5haAzRooBxFEXU6OK4xi_kkiyxYB0_UkrNCyUvPK9M/edit#gid=835953270
								- iThemes Security Pro
								- Sucuri
								  collapsed:: true
									- Top security company, synergises well with WP security)
									- Products
										- Sucuri Website Firewall (CloudProxy)
										  Basically CloudFlare
											- In short, Sucuri Website Firewall (CloudProxy) is a proactive (unlike monitoring and malware detection, which is reactive) approach to your website security. It’s a cloud-based protection for your website (all traffic goes through Sucuri cloud environment).
											- The most important features are:
												- stops attacks before they reach you website
												- prevents vulnerabilities exploitation
												- optimizes performance (four caching options)
								- WP Security
								- Bulletproof Security
								  collapsed:: true
									- https://wordpress.org/plugins/bulletproof-security/
								- WordFence Security
								  collapsed:: true
									- https://en-gb.wordpress.org/plugins/wordfence/
							- _Specific_
								- User Role Editor
								  collapsed:: true
									- Note: if they request more permissions then use - https://wordpress.org/plugins/user-role-editor
								- _Brute Force Protection / Limit Login Attempts_
								  collapsed:: true
									- iThemes Security Pro
									  Most customisable
									- Limit Login Attempts Reloaded
									  collapsed:: true
									  Fork of the extremely popular original
										- https://wordpress.org/plugins/limit-login-attempts-reloaded/
										- Limit Login Attempts
										  Not updated in 5 years but still very popular - 2mm downloads
											- https://wordpress.org/plugins/limit-login-attempts/
									- WP Cerber
									  collapsed:: true
										- https://wordpress.org/plugins/wp-cerber/
								- _Hiding WP Login page_
								  collapsed:: true
									- WPS Hide Login
									  Works together with iThemes Security Pro
										- https://wordpress.org/plugins/wps-hide-login/
									- https://wordpress.org/plugins/rename-wp-login/
						- Speed
						  collapsed:: true
							- CloudFlare
							  collapsed:: true
								- http://cloudflare.com and change DNS at domain registrar
							- W3 total cache
							  collapsed:: true
								- Much better than preinstalled super cache
							- WP.SmushIt
							  collapsed:: true
								- Auto compress images to speed up your site with no loss of image quality
						- https://wordpress.org/plugins/google-sitemap-generator/
						- WP Optimise
						  collapsed:: true
						  Database optimisation
							- https://wordpress.org/plugins/wp-optimize/
						- Backup
						  collapsed:: true
							- WP-DB-Backup
							  collapsed:: true
								- https://github.com/matzko/wp-db-backup
								- Easy DB-only backup https://wordpress.org/plugins/wp-db-backup/
							- Install BackWPUp (free)
							  collapsed:: true
								- http://www.wpbeginner.com/plugins/how-to-create-a-complete-wordpress-backup-for-free-with-backwpup/
							- Alternatives
							  collapsed:: true
								- https://wordpress.org/plugins/updraftplus/
								- https://wordpress.org/plugins/backupwordpress/
								- https://wordpress.org/plugins/wordpress-backup-to-dropbox/
							- Note: Use Duplicator for restoring backups.
							- Duplicator
							  collapsed:: true
								- Duplicator installer
								  #CreateAWebsite https://workflowy.com/#/62c215bba2f9
					- Any Content Site
					  collapsed:: true
						- Content area
						  collapsed:: true
							- Lightboxes
							  collapsed:: true
							  For popup pictures, videos, MP3s
								- WP Lightbox
								  http://lightbox.tipsandtricks-hq.com/lightbox-ultimate-demo/
							- Table of Contents
							  collapsed:: true
								- https://wordpress.org/plugins/table-of-contents-plus/screenshots/
							- Collapsible areas
							  collapsed:: true
								- https://wordpress.org/plugins/jquery-collapse-o-matic/
								- Sample page
								  http://habitlaboratory.com/wp-admin/post.php?post=1037&action=edit
							- WooSidebars
							  collapsed:: true
								- Allows different widgets to display on different pages
								- https://woocommerce.com/woosidebars/
						- Calls to Action
						  collapsed:: true
							- Affiliate plugins
							  collapsed:: true
								- ThirstyAffiliates
								  collapsed:: true
								  Easy management of affiliate links and converts commenters/forum posters keywords into affiliate links
									- Easily manage site-wide affiliate links - means you can easily edit all affiliate links from one dashboard instead of each post
									- Autolinker - automatically convert keywords into affiliate links - useful for forums and comment-heavy blogs
										- assists you with inserting links into your posts, pages and comments
									- Stats - the insight you need to find out what links are popular on your site
									- Google Click Tracking - adds the special Google Analytics Click Event code on your affiliate links as you insert them
									- CSV Importer - import your links from other packages in simple CSV format
									- Geolocations - geo target your visitors and redirect them to geographically appropriate alternative affiliate URLs, a great way to level up your income
									- Scheduled Links - create special schedules for your affiliate links to automatically
									- change the destination URL, great for sales running during a specific time period
									- https://wordpress.org/plugins/thirstyaffiliates/
								- Pretty Link Pro
								  Cloaking links, tracking analytics
								- Amazon Link Engine
								  collapsed:: true
								  Amazon link localisation
									- https://wordpress.org/plugins/amazon-link-engine/
									- Lock-in (dependency) - all the links added to your page will be their links, not yours
							- Optin Forms
							  collapsed:: true
							  #OptinForms Popups, widget, in-line, onclick trigger from menu/picture/text link, below post etc
								- Related: Email Marketing
								  #EmailMarketing https://workflowy.com/#/9f71ee524b9f
								- Optin form types
									- Popup/lightbox options
										- Ninja Popups 4.3 $25 (and have it downloaded too)
										  collapsed:: true
										  http://codecanyon.net/item/ninja-popups-for-wordpress/3476479
											- Menu link
											  #ninja-popup-POPUPIDHERE
											- http://demo.arscode.pro/ninja-popups/open-popup-by-clicking-on-the-link-or-button/
											- From banner/button
											  [ninja-popup ID=25] <img class="alignnone size-full wp-image-107" title="banner2" src="http://demo.arscode.pro/ninja-popups/wp-content/uploads/sites/2/2012/11/banner2.png" alt="" width="400" height="80" /> [/ninja-popup]
											- From link
											  [ninja-popup ID=45] <strong> Click Here for Extra Bonus</strong> [/ninja-popup]
											- Contact form 7 from link
											  [ninja-popup ID=151] <strong> Click Here for Extra Bonus</strong> [/ninja-popup]
										- From menu button
										  collapsed:: true
											- http://socialtriggers.com/ has got a great one
										- Lightboxes
										  collapsed:: true
											- http://lightbox.tipsandtricks-hq.com/open-lightbox-from-wordpress-menu/
										- OptinMonster
										  collapsed:: true
											- In-line, after-post, popup behaviour, from a pic or link
										- Bloom
										- Note: Exit Intent popups are patented, so only appear in a few plugins
									- Welcome Gate
									  Homepage-only, one-time display, skipped if direct linked,
										- Free - http://www.welcomegateapp.com/
										- Paid - OptinMonster
								- Products
									- Annual subscription
										- LeadPages (popups and landing pages)
										  collapsed:: true
										  $25-49/month
											- https://www.leadpages.net/pricing/
											- Used a lot by Ramit Sethi - must have good split-testing features then
										- OptinMonster
										  collapsed:: true
										  Annual price however - $80-200/year?
											- Widget forms
											  http://optinmonster.com/docs/how-to-create-a-sidebar-widget-optin/
									- One-time cost
										- Bloom
										  collapsed:: true
											- Sales page
											  https://www.elegantthemes.com/plugins/bloom/
											- https://www.elegantthemes.com/plugins/bloom/documentation/
											- Types of Optin forms
												- Automatic popup
												- In-line normal and in-line to unlock content
												- Below content
												- Widget area
												- After scrolling, commenting, purchasing, inactivity
												- Onclick trigger popup/two-step opt-in/LeadBoxes
													- Official solution
													  source:: https://www.elegantthemes.com/blog/theme-releases/introducing-bloom-1-1-now-supporting-hubspot-emma-activecampaign-salesforce
														- Bloom 1.1 also introduces a brand new trigger method for Fly-Ins and Pop-Ups. Using the On Click Trigger, you can trigger opt-in forms to appear at the click of a button. Simply give your button or anchor link a particular CSS class or ID and Bloom will trigger your desired opt-in form automatically when that link is clicked!
														- https://aspengrovestudios.com/how-to-create-a-click-trigger-for-the-bloom-plugin-by-elegant-themes/
											- Adding it into Divi
												- https://www.elegantthemes.com/blog/resources/exploring-divi-2-4-using-the-divi-code-module-to-integrate-third-party-plugins-in-the-builder
											- Missing features (in v1.1)
												- Redirect after optin
												- Exit intent trigger
												  collapsed:: true
												  However not possible as this is copyrighted
													- However a patent troll is sitting on this. OptinMonster etc are infringing
													  source:: https://www.elegantthemes.com/blog/theme-releases/introducing-bloom-1-1-now-supporting-hubspot-emma-activecampaign-salesforce
												- Sendy.co integration (though there is custom HTML allowed + 3rd party integration plugin)
												  collapsed:: true
													- Sendy-Bloom integration plugin
													  http://appvisionaire.com/downloads/bloom-sendy-integration-addon
												- ability to send a custom one time email to people who sign up that’s specific to that one optin form (LeadMagnet delivery)
												  collapsed:: true
													- This is a feature LeadPages use. They have you the ability to send a lead magnet as well but just being about to send an email would require less resources on your end and if we wanted to send a lead magnet in that email we can use cloud services like S3 for people to download whatever it is we’re giving away.
											- Bloom updates here (last checked: v1.1)
											  https://www.elegantthemes.com/blog/category/theme-releases
										- Rapidology
										  collapsed:: true
										  Open-source fork of Bloom, created by LeadPages
											- https://github.com/LeadPages/rapidology-plugin
											- Forked in August 2015
											- Features
												- https://www.rapidology.com/
												- Features missing from LeadPages
													- Landing Page creation
												- Features vs Bloom
													- It seems to be beating it on certain things e.g. redirect after optin
													- No Custom Form Fields, LeadMagnet Delivery, LeadDigits (SMS Marketing Tool), LeadLinks (Automation Link Tool)
											- Cons
												- Branding (though this can be be removed prior to compiling)
													- I understand your desire to remove the “Powered by” badge from your Rapidology forms. However, this is not currently a feature that Rapidology supports.
													- Because Rapidology is a free plugin, we rely on the “Powered by” badge to spread the word about Rapidology. That said, we have taken steps to ensure the badge is subtle and un-obtrusive.
										- OptinSkin
										  collapsed:: true
											- http://optinskin.com/
											- Can be one-click placed below posts, in side bar etc
											- Easy split-testing
											- Allows Custom designed HTML forms to be easily entered
										- UberOptin
										  collapsed:: true
											- $29, allows insertion via shortcode or widget
											- Simple styles, best suited for sidebar widget if anything
										- Thrive Leads
										  collapsed:: true
											- https://thrivethemes.com/leads/more/
											- Includes sticky ribbon optin form (like HelloBar)
											- Good for Conversion Optimisation:
												- Define exactly where and when your opt-in forms are shown, based on rules about post categories, tags, post formats and more. Create relevant, specific offers for different segments of your audience.
												- 4 A/B testing strategies: Designs, content, triggers, form types, lead magnets
											- Integrates with Sendy
								- utilize good, clean UX when you design your CTA inside your user flow
									- You should test if you want your CTA immediately when the user accesses your site, or maybe right before they leave. This article gives good overview of the different options: http://blog.invisionapp.com/designing-email-list-cta/
							- Social sharing buttons
							  collapsed:: true
								- Monarch (by Elegant Themes)
								  collapsed:: true
									- Overview
									  https://www.elegantthemes.com/blog/theme-releases/monarch
									- Types
										- Floating sidebar buttons
										- Inline buttons before/after post
										- On top of pictures - auto or per-pic
										- Popups
										- Fly-ins
										- Inline Social Follow Links
										- Sidebar & Footer Social Follow Links
									- Customisation
										- Let Users ‘Like’ a Page
										- Display Total & Individual Counts
								- Social Warfare
								  collapsed:: true
									- https://warfareplugins.com/
								- Simple Share Buttons Adder.
								  collapsed:: true
								  https://wordpress.org/plugins/simple-share-buttons-adder/
									- It gives you the usual options of which social networks to show, but you can also upload your own custom buttons to match your WordPress theme!
								- https://en-gb.wordpress.org/plugins/easy-social-share-buttons/screenshots/
								- https://wordpress.org/plugins/click-to-tweet-by-todaymade/
							- Related posts
							  collapsed:: true
								- Widget
									- https://en-gb.wordpress.org/plugins/wordpress-popular-posts/
								- Below post
									- https://en-gb.wordpress.org/plugins/yuzo-related-post/
									- https://wordpress.org/plugins/upprev/
								- Yet Another Related Posts Plugin (YARPP)
							- Sticky widgets (when scrolling down page)
							  collapsed:: true
								- https://en-gb.wordpress.org/plugins/q2w3-fixed-widget/
							- Displaying Old Posts
							  collapsed:: true
								- Options
									- Clean Archives Reloaded plugin
									  http://habitlaboratory.com/archives/ Just create/edit a post or page and type [cleanarchivesreloaded] where you would like the archives list to show up. You can also use [cartotalposts] to show your total post count.
									- https://wordpress.org/plugins/collapsing-categories/screenshots/ sidebar - categories like Bold&Determiend
									- Category landing pages with only a few popular posts - Social Triggers style
										- Also uses only 'next page' on blog homepage - can't see full archive/sitemap easily
									- Category pages with a custom paragraph at start highlighting popular articles before continuing by Most Recent (James clear style)
						- Comments
						  collapsed:: true
							- Akismet
							- With Comment Reply Notification
							  collapsed:: true
								- you can set up email delivery to notify your reader when you’ve responded to their comment. They’ll be surprised to hear from you – and chances are, they’ll leave comments again!
								  https://wordpress.org/plugins/comment-reply-notification/
								- One quick note here: this plugin hasn’t been updated in over two years, but I still use it here on the Blog Maven, and it still works like a charm.
							- Comment redirect (for first-time commenters)
							  collapsed:: true
							  https://yoast.com/wordpress/plugins/comment-redirect/
								- e.g. http://outspokenmedia.com/thanks-for-commenting/
						- Redirect pages
						  collapsed:: true
							- https://wordpress.org/plugins/quick-pagepost-redirect-plugin/
							- pretty link pro
						- Contact Forms
						  collapsed:: true
							- Contact Form 7
							- Ninja Forms
							- Gravity Forms
							  collapsed:: true
								- Gravity Forms. This is a very powerful form builder for WordPress. It really is the best form plug-in out there. While it is usable in a variety of ways, I love using it for all my membership sites as a contact form as well as a testimonial collector. Not only that, you can use it to collect questions from your members. It is handy, too, because it will easily pre-fill the name/email of your member based on their membership, so it saves them the hassle.
						- Design
						  collapsed:: true
							- UberMenu
							  collapsed:: true
								- Purchased (via Post My Meds)
								- Documentation
									- http://sevenspark.com/docs/ubermenu-3
									- Google Maps
									  http://sevenspark.com/docs/ubermenu-3/content/shortcodes/maps
										- Get an API key
										  https://developers.google.com/maps/documentation/javascript/get-api-key#get-an-api-key
									- Contact Form 7
									  http://sevenspark.com/docs/ubermenu-3/content/contact
									- Troubleshooting
										- Top-level menu items are on multiple lines rather than 1
											- http://sevenspark.com/docs/ubermenu-3/faqs/item-wrap
										- Submenu width is limited to width of top-level menu
											- In UberMenu settings, make the submenu unbounded (from the main menu)
										- Divi integration
											- http://sevenspark.com/docs/ubermenu-3/theme-integration/divi
					- DB + File Management (cPanel-like)
					  collapsed:: true
						- File Manager
						  https://wordpress.org/plugins/file-manager
						- DB Manager
						  https://wordpress.org/plugins/wp-dbmanager/
						- DB backup
						  https://wordpress.org/plugins/wp-db-backup/
					- Blogs
					  collapsed:: true
						- WordPress SEO by Yoast
							- for creating easy SEO-optimised blog
					- Collapsible widget menus
					  collapsed:: true
						- Page Tree: This is a super simple yet really beneficial plugin that allows me to have a sidebar widget with expandable and collapsable menus. Super easy to use and very effective.
						  http://wordpress.org/extend/plugins/page-tree/
					- Conversion Optimisation
					  collapsed:: true
						- Divi Leads
						  intralink2:: https://workflowy.com/#/4b3726173464
						- Thrive Clever Widgets
						  collapsed:: true
							- https://thrivethemes.com/cleverwidgets/
							- Pros
								- Use this to customise pages to the user
								- and A/B test
							- Problem is that it fills up the Widgets page with many widget boxes, which only get activated on certain pages. Not a good dashboard for managing these widgets
						- Pretty Link Pro
						  collapsed:: true
							- https://prettylinkpro.com/user-manual/setup-split-tests-on-your-links/
					- Landing pages
					  #LandingPage https://workflowy.com/#/5f19d15d7caa
					- Membership Site Plugins
					  #ProductCreation https://workflowy.com/#/f8cfdb2ba09e
					- eCommerce
					  collapsed:: true
					  #WordPressPlugins-eCommerce
						- WooCommerce
						  collapsed:: true
							- Pros/Cons
							  collapsed:: true
								- Cons
									- Products and customer orders use the Posts table, making it much more difficult to copy changes from Staging to Production site
										- Two new plugins being developed to move these elements into a custom table
										- WooCommerce Custom Product Tables Beta
											- https://woocommerce.wordpress.com/2018/07/17/woocommerce-custom-product-tables-beta/
											- https://github.com/woocommerce/woocommerce-product-tables-feature-plugin
											- https://trello.com/c/aAZNP5hF/130-custom-product-tables-for-performance
										- WooCommerce Custom Orders Table
											- https://github.com/liquidweb/woocommerce-custom-orders-table
											- https://trello.com/c/2QGrEbBW/113-custom-order-tables-for-performance
							- Shortcodes
							  collapsed:: true
							  http://docs.woothemes.com/document/woocommerce-shortcodes/
								- Example with 1 arg
									- [woocommerce_my_account order_count="12"]
							- plugins
							  collapsed:: true
								- Composite products
								- product addons
								- Subscriptions
								- FG Magento to WooCommerce
									- Tools > Import > Magento
									- https://www.fredericgilles.net/fg-magento-to-woocommerce/
							- Change WooCommerce's Add to Cart button:
							  collapsed:: true
								- Text https://docs.woocommerce.com/document/change-add-to-cart-button-text/
								- Styling http://i.imgur.com/B7K1jlZ.png
							- \_Related: \_Divi Shop module
							  #LandingPage-Divi https://workflowy.com/#/f6266dd5d457
						- Payment Processors
						  collapsed:: true
						  #WordPressPlugins-Payment Tags: payment gateway, credit card processor
							- Types
							  collapsed:: true
								- Payment processor enables you to authorize and process credit card transactions.
								- The merchant account acts as a kind of online bank, holding your funds until they are sent to your actual bank.
							- Shopping Carts
							  collapsed:: true
							  If you don't need a full WooCommerce backend
								- e-Junkie
								  Cheap and simple for digital products
									- Affiliate management for your products
									- Customize emails that get sent to your customers
									- Can broadcast emails/newsletters to all of your previous customers
									- You can easily update your products and change prices if you wish
								- 1ShoppingCart
								  Good for affiliate tracking
								- DL Guard
								  http://www.dlguard.com/dlginfo/index.php
								- Digital Access Pass
								  http://digitalaccesspass.com/
								- WP Wishlist
								  http://www.smartpassiveincome.com/wp-wishlist
								- Other PayPal compatible options for digital delivery
								  https://cms.paypal.com/au/cgi-bin/?cmd=_render-content&content_ID=developer/solutions_dgd
								- Related: Order Fulfilment for physical products
								  #eCommerce https://workflowy.com/#/cbcd4ae1ff14
							- "Payment Processors"
								- Combined PP and MAs
									- VISA
									- Mastercard
									- American Express
									- Bitcoin payment gateways
									  collapsed:: true
										- https://startpage.com/do/m/mobilesearch?language=english&query=bitcoin+woocommerce
										- Coinbase (for Bitcoin)
									- PayPal
									  collapsed:: true
										- Pros and Cons
										  collapsed:: true
											- Pros
											  collapsed:: true
												- Easiest and quickest to set up
												- Accepts credit cards
											- Cons
											  collapsed:: true
												- Least professional however
												- Unsuitable for anonymity also
										- PayPal buttons or WooCommerce+PayPal
										- Setup
										  collapsed:: true
											- Woo Subscriptions setup
											  collapsed:: true
												- Subscriptions can only be used on one website
												  collapsed:: true
													- As a result, PayPal can only be used to sell subscriptions on one website.
													  source:: https://docs.woothemes.com/document/subscriptions/store-manager-guide/#section-4
													- If you want to sell subscriptions on multiple sites, use a modern payment gateway like Stripe.
													  http://docs.woothemes.com/document/subscriptions/payment-gateways/
												- Setup
												  source:: https://docs.woothemes.com/document/subscriptions/store-manager-guide/#section-4
												  collapsed:: true
													- Choose IPN notifications URL
													  collapsed:: true
													  https://www.paypal.com/cgi-bin/customerprofileweb?cmd=_profile-ipn-notify
														- This format:
														  collapsed:: true
															- http://example.com/?wc-api=WC_Gateway_Paypal
													- Request API credentials
													  collapsed:: true
													  https://www.paypal.com/uk/cgi-bin/webscr?cmd=_profile-api-add-direct-access-show
														- Signature
														- Enter the details on your website
														  http://example.com/shop/wp-admin/admin.php?page=wc-settings&tab=checkout&section=wc_gateway_paypal
											- Which PayPal plugin
											  collapsed:: true
												- https://docs.woothemes.com/document/paypal-extension-comparison/
												- PayPal Express
												  collapsed:: true
													- When using the PayPal Express option, customers are taken directly to PayPal.com to authorize funds, and then return to your store to choose shipping and pay. Since the checkout process does not occur on your website, an SSL certificate is not required and you don’t have to stress over PCI compliance. Pretty great, huh?
													- Allows overriding Business Name on PayPal Business account - ensures congruent branding
												- Digital Goods
												  collapsed:: true
													- PayPal is not accepting new signups and activations for Digital Goods product at this time
													- keeps customer on site, Standard doesn't
													- Only PayPal Standard or Digital Goods can be used with Subscriptions
												- Only PayPal Advanced can't be used
												- Advanced and Pro have monthly fees
											- Update the Auto Return
											  collapsed:: true
												- https://www.paypal.com/cgi-bin/customerprofileweb?cmd=_profile-website-payments
									- Google Wallet
									  collapsed:: true
										- is good, albeit not automated
									- Apple Pay
								- Payment Processors
									- Cons
										- They can arbitrarily decide to deplatform certain businesses and individuals
											- Porn industry
											  collapsed:: true
												- https://www.cnbc.com/2022/08/02/bill-ackman-blasts-visa-saying-it-has-the-power-to-pressure-pornhub-to-remove-child-pornography.html
												- https://thehill.com/policy/technology/548279-mastercard-updates-policy-for-adult-content-sellers/
											- Legal marijuana products are being made difficult to get payment processing
											  collapsed:: true
												- https://www.marijuanamoment.net/marijuana-banking-reform-will-not-be-enacted-as-part-of-manufacturing-bill-congressional-leaders-agree/
												- https://www.aba.com/advocacy/our-issues/cannabis
									- Companies such as First Data and Chase Paymentech have direct software connection to the VISA, MasterCard, and American Express networks for routing transactions
									- Who
								- Payment Gateways
								  collapsed:: true
								  Companies offer businesses a connection to one or more Payment Processors,
									- https://www.woothemes.com/product-category/woocommerce-extensions/payment-gateways/
									- Several checkout plugins for WooCommerce in Blog Plugins folder in My Docs
									- Authorize.net
									- Brain tree
									- 2Checkout
									  collapsed:: true
										- Accept Credit Cards, PayPal, and Debit Cards
										- Supports >100 online shopping carts
										  https://www.2checkout.com/online-shopping-carts/
										- High transaction fees though
									- TrialPay
									- Amazon Payments
									- square
									- SagePay
									  collapsed:: true
										- WooCommerce plugin
										  collapsed:: true
											- SagePay Form / SagePay Direct
											- $79
											- https://www.woothemes.com/products/sage-pay-form/
											- https://docs.woothemes.com/document/sagepay-form/
											- **Documentation extended**
											  collapsed:: true
												- What does each Status setting do?
												  collapsed:: true
													- PAYMENT transaction type is used to gain an authorisation from the bank, then settle that transaction early the following morning, committing the funds to be taken from your customer's card. In some cases you may not wish to take the funds from the card immediately, but merely place a shadow on the customer's card to ensure they cannot subsequently spend those funds elsewhere, and then only take the money when you are ready to ship the goods. This type of transaction is called a DEFERRED transaction.
													- The AUTHENTICATE and AUTHORISE methods are specifically for use by merchants who are either (i) unable to fulfil the majority of orders in less than 6 days (or sometimes need to fulfil them after 30 days) or (ii) do not know the exact amount of the transaction at the time the order is placed (for example, items shipped priced by weight, or items affected by foreign exchange rates).
													  collapsed:: true
														- Unlike normal PAYMENT or DEFERRED transactions, AUTHENTICATE transactions do not obtain an authorisation at the time the order is placed. Instead the card and card holder are validated using the 3D-Secure mechanism provided by the card-schemes and card issuing banks, with a view to later authorisation.
													- http://www.sagepay.co.uk/support/16/36/transaction-types
													- http://www.sagepay.co.uk/support/16/36/authorisation-process
												- What's the purpose of the 'Customer payment page' link here?
												  collapsed:: true
													- Sometimes it is required to manually create an order for a customer from the backed i.e. WooCommerce >> Orders >> Add Order, In this case you will fill out the customer and product details and when you click Save Order button then you will get that link which can be provided to the customer to make the payment. When the customer clicks the Customer payment page link then they will see all the available payment methods and can proceed to complete the payment.
												- Setting the order status to 'Completed' will take the actual funds for both DEFERRED and AUTHORISED payments.
										- \_Related: \_Payment Processing SOP
										  #PMM-SOPs-Customer https://workflowy.com/#/2de8302ba059
										- Setup a server to accept SagePay payments
										  collapsed:: true
											- SagePay control panel
											  collapsed:: true
											  https://live.sagepay.com/mysagepay
												- Change domain
												- Add IP address
												  collapsed:: true
													- 139.59.172.91
													- subnet
													  255.255.255.255
										- _{Archive}_
										  collapsed:: true
											- SagePay test mode issue
											  collapsed:: true
												- Problem
												  collapsed:: true
													- At the moment I can not test a payment as the test card details do not work when I try using it.
													  collapsed:: true
														- error message - wrong ip address
													- Screenshots
													  collapsed:: true
														- http://prntscr.com/dderul
														- http://prntscr.com/ddes7s
													- test card info
													  http://www.sagepay.co.uk/support/12/36/test-card-details-for-your-test-transactions
												- Solution
												  collapsed:: true
													- WooCommerce support ticket
													  collapsed:: true
													  https://woocommerce.com/my-account/tickets/?id=508507
														- They say to add IP address via SagePay control panel
													- SagePay control panel
													  collapsed:: true
													  https://live.sagepay.com/mysagepay
														- Use the test portal login
														  collapsed:: true
															- Change domain
															- Add IP address
															  collapsed:: true
																- 139.59.172.91
																- subnet
																  255.255.255.255
											- Tokens - have usef get it setup once I've got the server up
								- Payment Facilitators
								  When a company uses their merchant account and connection to a Payment Processor or Payment Gateway to sell for vendors without a merchant account.
									- Stripe
									  collapsed:: true
										- allows crypto payments too. All in conjunction with the standard visa and MC.
									- Authorize.net
									  collapsed:: true
										- Alows payment in PayPal (even if you don't want or have a PayPal account). All in conjunction with the standard visa and MC.
									- [Stripe alternatives](https://news.ycombinator.com/item?id=32558191)
								- Unsure
								  collapsed:: true
									- Amex
									- ClickBank
								- Definitions
								  http://www.clickbank.com/payment-models-overview-and-why-it-matters-to-you-clickbank/
								-
							- Merchant Accounts
							  collapsed:: true
								- Pros
									- Processing cards yourself enables you to do 1-click upsells and control renewals
								- Providers
									- https://www.cardpaymentoptions.com/credit-card-processors/
									- powerpay.biz
										- https://www.cardpaymentoptions.com/credit-card-processors/powerpay-review-rating-complaints/
									- Open one in Bulgaria?
							- Related:
							  collapsed:: true
								- Product Creation
								  #ProductCreation https://workflowy.com/#/c2c4024dcfa0
								- _Affiliate Management_
								  #Affiliate-Management https://workflowy.com/#/219c75ca7588
								- Accounting
								  #Software https://workflowy.com/#/10c3abbea400
						- Currency conversion
						  collapsed:: true
							- Standard WooCommerce currency converter just shows a different price on the product page
							- Aelia changes price through checkout process
							  https://aelia.co/shop/currency-switcher-woocommerce/
								- Comparison
								  I found the Woo Commerce converter inadequate as it's only an illustration, not an actual conversion. It was okay as a starting point, but I wanted customers to be able to see their own currency all the way through the browsing process.
								  
								  I've gone for Aelia Currency Switcher for Woo Commerce. You can either have currencies being changed dynamically depending on preselected exchange rates, or you can manually enter prices in different currencies (which is what I've done). The customer can see the price in their currency, and check out in that currency. You can also have it as a drop down list for the customer to pick from rather than automatic, if you wish.
								  
								  You can also have a default currency other than your own. I'm testing out having US dollars as the default currency as I think that people in locations other than the ones I've covered specifically will have more of an intuitive feel for USD prices and GBP. I'm just starting out with it, so we'll see.
						- Related: eCommerce
						  #eCommerce https://workflowy.com/#/f494aa3b04ee
					- Booking system
					- Onsite optimisation
					  #SEO https://workflowy.com/#/8e1504dc6559
				- _Plugin Download Sites_
					- Cheap GPL
					  collapsed:: true
						- https://wpspring.com
						- https://www.gplvault.com
						- https://www.gplguru.com
						- https://www.woosociety.com/
						- https://gplchimp.com/
						- http://www.gplplugins.com/
						- http://sozot.com/
						- https://wpnull.org/
						- https://www.ultimatewoo.com
						- http://woogpl.com/
						- https://gpldl.com/
						- https://www.themecanal.com/
						- https://gpl.life/
						- https://www.96down.com/
						- https://club.wpeka.com/
					- bestblackhatforum.com
					  Though much of it is likely viruses
			- Speed Optimisation
			  collapsed:: true
				- Speed testing + Analysis
				  collapsed:: true
					- _Basic suggestions_
						- Google Analytics - Site Speed Suggestions
						  https://analytics.google.com/analytics/web/#report/content-site-speed-suggestions/a74269825w112380137p117327945/
						- PageSpeed Insights
						  https://developers.google.com/speed/pagespeed/insights/
					- https://gtmetrix.com/
					- https://tools.pingdom.com
					- _Comprehensive analysis_
						- https://www.webpagetest.org/
					- https://danielmiessler.com/blog/10-ways-to-test-your-website-performance/#gs.3FFHExA
					- _Specific enhancement analysis_
						- Varnish
						  http://www.isvarnishworking.com/
						- GZip
						  http://www.feedthebot.com/tools/gzip/
						- WordPress theme/plugin load
						  collapsed:: true
							- WP Performance Profiler
								- tracking theme and plugin load speed called
								- It also tracks other requests: https://slocumthemes.com/2015/01/wp-performance-profiler/
							- P3
								- https://en-gb.wordpress.org/plugins/p3-profiler/
				- _Top recommendations_
				  collapsed:: true
					- ((67376780-c521-4602-bbcb-c23d12ced6a4))
					  collapsed:: true
					- PHP-FPM (FastGCI alternative)
					- Varnish (caching)
					- gZip Compression
					  collapsed:: true
						- For Apache, you can use mod_deflate.
					- Minify & Consolidate CSS and JavaScript Files
					  collapsed:: true
						- bwpminify wordpress
						- https://wordpress.org/plugins/wp-minify-fix/
						- “I wasn’t able to get rid of all render-blocking JavaScript and CSS in above-the-fold content.”
							- If it’s about CSS, this might help:
							- 1. ABOVE THE FOLD
							- http://jonassebastianohlsson.com/criticalpathcssgenerator/
							- -
							- concatenate basic css in case of errors
							- 2. CSS OPTIMIZER
							- http://www.cssportal.com/css-optimize/
							- it could be inlined
							- 3. HTML COMPRESSOR
							- https://htmlcompressor.com/compressor/
						- – Autoptimize like described at https://www.wpfaster.org/blog/how-to-use-autoptimize-inline-and-defer-css-option This eliminates the render blocking CSS for ‘above the fold content’.
						- I found Autoptimize to work. Use this trick from WP Faster “https://www.wpfaster.org/blog/how-to-eliminate-render-blocking-css-above-fold”. It WORKS.
						- 5. Minify your JS and CSS with online tools and use FTP to replace what Google tells you could be minified. You can use https://cssminifier.com/, that site will also have JS minify as well. You’ll need access to Cpanel or an FTP program to replace your CSS and JS. Make backup of your original files though in case you make a mistake.
					- Image optimisation
					  collapsed:: true
						- Icon fonts
							- Finally, leverage fonts in place of icons, such as the amazing Elegant Font (http://www.elegantthemes.com/blog/resources/elegant-icon-font). Fonts are generally less weight than images, and can also be tweaked down with third-party tools like IcoMoon (http://icomoon.io/) to eliminate unneeded icons in the font, helping the font to load that much faster (or to add your own icons, or mix-and-match icon fonts (license-permitting)).
							- https://wordpress.org/plugins/font-awesome/
							- https://wordpress.org/plugins/icon-fonts/
							- http://www.wpbeginner.com/wp-themes/how-to-easily-add-icon-fonts-in-your-wordpress-theme/
							- https://wordpress.org/plugins/better-font-awesome/
							- https://www.elegantthemes.com/blog/resources/elegant-icon-font
							- https://www.elegantthemes.com/blog/resources/how-to-use-and-embed-an-icon-font-on-your-website
							- https://www.elegantthemes.com/blog/tips-tricks/font-awesome-wordpress
						- http://pngcrush.com/
						- http://jpgoptimiser.com/
						- https://wordpress.org/plugins/ewww-image-optimizer/
						- https://wordpress.org/plugins/wp-smushit/
						- https://wordpress.org/plugins/resize-image-after-upload/
						- EWWW Image Optimizer"
							- Reduce file sizes for images within WordPress including NextGEN Gallery and GRAND FlAGallery. Uses jpegtran, optipng/pngout, and gifsicle.
					- CDN
					  collapsed:: true
						- CloudFront
							- https://www.elegantthemes.com/blog/tips-tricks/how-to-use-amazon-s3-and-cloudfront-with-wordpress
						- Self-hosted CDN
							- Browsers can parallelise 5 websites?
							- http://www.journaldev.com/1506/how-to-create-own-self-hosted-cdn-for-wordpress
							- https://seo-hacker.com/implement-selfhosted-cdn-site-speed/
							- https://stackoverflow.com/questions/12402268/how-to-create-your-own-cdn-is-it-just-creating-a-subdomain
						- Offload assets to 3rd parties
							- Public CDNs
								- Google Hosted Libraries (hosts 12 most popular libraries)
								  https://developers.google.com/speed/libraries/
								- jsDelivr (hosts any assets, open-source too)
								  Powered by MaxCDN, CloudFlare etc
									- Unlike the competition jsDelivr uses a unique Multi-CDN infrastructure to offer the best possible uptime and performance. The main backbone of it is built on top of CDN networks provided by MaxCDN and CloudFlare.
									- And we also use custom servers in locations where CDNs have little or no presence. In total at this moment this results in 42 global POP locations. In the future we plan to add even more locations to offer top performance even in less popular countries.
									- Of course lots of locations means nothing if you can’t load balance across them correctly. For the load balancing system we use services provided by Cedexis. One of their main features is the real time performance data they gather on all major CDN providers. 1.3 billion RUM (Real User Metrics) performance tests per day are processed and available to all Cedexis users.
									- Software
									  https://www.jsdelivr.com/sponsors/our-sponsors
							- Commercial CDN
								- Amazon CloudFront
						- CDN
							- MedExpress
							  http://i.imgur.com/To637De.png
						- Easy enable S3/CloudFront for WordPress
						  https://docs.bitnami.com/aws/apps/wordpress/#how-to-configure-wordpress-for-cloud-storage-on-amazon-s3
						- Plugins
							- WP Offload S3 Lite" Description Automatically copies media uploads to Amazon S3 for storage and delivery. Optionally configure Amazon CloudFront for even faster delivery.
							- ((6463499e-9096-4ccf-8af2-96569e23c33b))
								- Includes the Amazon Web Services PHP libraries, stores access keys, and allows other plugins to hook into it.
				- Much of the above can be deployed with
				  collapsed:: true
					- DevOps for WordPress
						- https://github.com/carlalexander/debops-wordpress
						- What does it do for you?
						  collapsed:: true
							- "DebOps for WordPress" takes an unconfigured server and turns it into a fast and secure WordPress server. It takes care of all server configuration and maintenance tasks. It'll handle the setup of:
								- Automatic updates
								- MySQL backups
								- Let's encrypt SSL certificates
								- Fail2ban
								- Firewall
								- And a lot more
							- On top of all that, you'll also have a working WordPress installation using:
								- Nginx
								- MariaDB (MySQL replacement)
								- PHP 7.0
								- ((6607f722-b674-4037-af49-e03bafebc259))
								- WP-CLI
								- Varnish (optimized for WordPress)
							- Don't know what these words mean? That's ok! All you need to know is that it's everything you'd expect from a top tier host (minus the dashboard).
						- What is it made of?
						  collapsed:: true
							- "DebOps for WordPress" is made up of two components: Ansible and DebOps. Ansible is configuration management tool that focuses on simplicity and readability. It's used to manage IT infrastructures of all sizes.
							- DebOps is a set of Ansible playbooks and roles created by Maciej Delmanowski. It handles all the building blocks required to build one server. But it's powerful enough that you can use it to build an entire data center with it.
							- DebOps acts as a layer on top of Ansible which adds extra functionality. It handles things the creation of directories and encryption of passwords using external tools. This removes the need for other tool or scripts to handle them.
						- How to migrate between dev and production servers
						  collapsed:: true
							- https://github.com/carlalexander/debops-wordpress/issues/117
				- _Dismissed_
				  collapsed:: true
					- mod_pagespeed
					  collapsed:: true
						- http://i.imgur.com/tau9iZM.png
						- Too general and automatic - instead stick with NGINX + PHP-FPM
						- PageSpeed
						  Open-source Apache/NGINX module
							- https://www.modpagespeed.com/
							- ngx_pagespeed
					- PHP-CGI + FastCGI
					  collapsed:: true
						- PHP-FPM (FastGCI alternative) is better
						- Recommended not use php-cgi?
						  https://documentation.cpanel.net/display/ALD/More+about+PHP+Handlers
							- daily process log shows it maxing out
							  intralink2:: https://workflowy.com/#/f3c6cf6e418e
				- W3 Total Cache
				  collapsed:: true
					- http://www.onlinemediamasters.com/w3-total-cache-settings/
				- Scaling Routes
				  collapsed:: true
					- https://www.digitalocean.com/community/tutorials/automating-the-deployment-of-a-scalable-wordpress-site#step-eight-%E2%80%94-automating-the-process
					- _By Limitation_
						- Web server CPU, RAM or I/O
						  collapsed:: true
							- Load Balancer + Multiple EC2 Instances
								- Load Balancer
								  #Infrastructure https://workflowy.com/#/e92c7eb5c858
									- HAProxy as standard
									- Amazon have a native one - ((6463499e-9ecf-4800-bf1f-65704c310016)) (likely built on HAProxy)
								- Memcached or ((6607f722-b674-4037-af49-e03bafebc259)) Server as session handler (make sure users don't swap between servers)
									- https://www.digitalocean.com/company/blog/horizontally-scaling-php-applications/
								- GlusterFS or Ceph to keep filesystem in sync
									- NFS
									  #Infrastructure-Containers https://workflowy.com/#/8281ea60abe9
									- Container orchestration
									  #Infrastructure-Containers https://workflowy.com/#/826cca5ca469
						- Database CPU, RAM or I/O
						  collapsed:: true
							- Amazon Aurora
							- Read Replicas
							- Galera Cluster
								- MariaDB Galera Cluster is a synchronous multi-master cluster for MariaDB
						- Load Balancer
						  #Infrastructure https://workflowy.com/#/e92c7eb5c858
				- Assorted
				  collapsed:: true
					- CDN
					  collapsed:: true
						- Assets addon
						  Serve your CSS & JS from S3/CloudFront
							- https://deliciousbrains.com/wp-offload-s3/doc/assets-addon/
					- Performance
					  collapsed:: true
						- https://developers.google.com/speed/docs/insights/rules
						- ((64634999-fc4a-4bf0-9d74-f8dc23708311))
						  collapsed:: true
							-
						- Develop AMP site
						  collapsed:: true
							- Enable AMP plugin
							  https://docs.bitnami.com/aws/apps/wordpress/#how-to-enable-accelerated-mobile-pages-amp-in-wordpress
						- www.onlinemediamasters.com/slow-wordpress-admin-panel/
						- https://developers.google.com/speed/pagespeed/insights/?url=http%3A%2F%2Fec2-52-56-165-49.eu-west-2.compute.amazonaws.com
						- http://i.imgur.com/ccS5gem.png
						- WP Optimise plugin (check in 6-12 months time, checked in March and no optimisations needed)
						  intralink2:: https://workflowy.com/#/c29dc5a18f8d
						- Assorted tips
						  collapsed:: true
							- 4. Uss CSS Sprites if your site has too many background images.
							- 5. Use a CDN or at least Cloudflare and enable aggressive optimization from within its settings area. (if so, then you better not minify files in your caching plugin so as to avoid conflict of functions)
							- 6. Use Custom CSS box of Divi instead of a theme/child theme style.css file. Doing this, all your css rules will be placed in the section inline and Google likes this. Css shud be at the top.
							- 7. Use CSS as much as possible in lieu of jQuery for transition or animation.
							- 8. Again try to use CSS and avoid adding too many HTML elements to reduce the HTML size of the site (like use css classes for making a text bold or italic or so, instead of adding TEXT
							- 9. Try to create a subdomain on your site and put all your images there which are less likely to be changed (frequently). Then call those images on your site pages instead of pulling them down from the default wp-uploads directory. This helps in parallel downloading for browsers and hence more speed.
							- 10. Avoid using plugins for every possible means. Instead try to execute those small functions via custom coding in your theme files.
							- 11. Try to avoid using too many web fonts on a site – maximum 2 or 3.
					- Cache/all-in-one
					  collapsed:: true
						- W3 total cache
						- WP Super Cache
						- https://premium.wpmudev.org/project/wp-hummingbird/
					- Add expires
					  collapsed:: true
						- in header?
						- https://fixmywp.com/blog/add-expire-headers-wordpress-site.php
						- http://tinyurl.com/zmqh2nb
					- Accelerated Mobile Pages (AMP)
					  collapsed:: true
						- What
							- Setting up structured data within google search console
							- Google is apparently pushing people to create AMPs to rank high
							- https://www.ampproject.org/learn/about-amp/
							- Basically Google-CDN for HTML+JS - similar to jQuery or FontAwesome 3rd-party assets being used
							- https://wordpress.org/plugins/amp/
							- Essentially, AMP is a modified and slimmed down version of HTML plus a JavaScript library. Common HTML elements like img and video are replaced with AMP HTML specific version like amp-img and amp-video, which are, in fact, web components. And, Google being Google, a big part of AMP HTML is amp-ad, a container for serving Google’s (and some other ad services’) advertising. AMP isn’t intended to be used instead of existing pages, but as part of a parallel mobile web. Sites will typically offer both standard HTML pages and AMP HTML pages.
							- AMPed pages are fast, largely because AMP insists that pages don’t use third-party JavaScript libraries.
							- AMP in action consists of three different parts:
							  https://www.ampproject.org/learn/about-amp/
								- AMP HTML is HTML with some restrictions for reliable performance and some extensions for building rich content beyond basic HTML. The AMP JS library ensures the fast rendering of AMP HTML pages. The Google AMP Cache can be used to serve cached AMP HTML pages.
								- AMP HTML
							- New version of HTML - AMPHTML code is heavily stripped-down to ensure faster loading times and smooth readability.
							- New JavaScript framework - AMP.JS loads external resources asynchronously, stops any external scripts from blocking the page render. Third party JavaScript is strictly disallowed.
							- Modified Image element - AMP-IMG elements opt Lazy loading functionality. Google will cache and host amp content so fetching from your server is no longer needed.
							- Streamlined version of CSS - AMP-CUSTOM CSS is used. Except custom fonts, external stylesheets, inline style attributes and certain styles are disallowed due to performance implication.
							- Example
							  https://streamable.com/0anuh
							- Rich card carousel
							  http://i.imgur.com/FUQNoRm.png
							- It's essentially the same as using Medium to publish your blog instead
								- Tech lead for AMP says: The original idea behind AMP was to allow content to be distributed to platforms (such as Google, Twitter and Pinterest) in a way that retains branding and monetization control for the publisher
								  https://www.alexkras.com/google-may-be-stealing-your-mobile-traffic/#comment-55336
							- Most importantly, I was surprised to find out that instead of redirecting users to an optimized version hosted on my server, Google was actually serving a snapshot of the page from their own cache. To make things worse, Google was injecting a large toolbar at the top of the snapshot encouraging users to get back to Google search results (a functionality already provided by the back button) and making it harder to get to the original site.
							- To draw a contrast, Google have been keeping snapshots of sites for a very long time, available via a “cache” link right next to search results. The cache link, however, was optional. Clicking on the search result, traditionally, would take the user to the original source. With AMP, Google have turned this equation around.
							- This is basically RSS/Atom 2.0, with ability to add their analytics and ads
							- You can use AMP formatted pages for better load times but if you don't use Google AMP Cache then you won't get the Google search results benefits eg AMP icon, inclusion in rich carousels or prefetched content
							  source:: https://www.alexkras.com/i-had-lunch-with-google-amp-team/
								- Can the cache be optional?
								- My first question was if I could get the speed up that AMP provides without participating in the cache aspect. The answer was yes and no.
								- Yes. The AMP project is open source and there is nothing stopping anyone from including it in their pages. The only way Google will know to cache the APM page is when non AMP page has a rel="amphtml" link on it, pointing to the AMP version. i.e.
								- <link rel="amphtml" href="https://www.example.com/url/to/amp/document.html"/>
								- Removing this link will essentially “disable” the AMP cache.
								- Another option is to remove the amp tag from the html tag inside of the AMP page.
								- HTML pages are not valid AMP pages without the amp tag. Therefore removing this tag will prevent the page from being cached.
								- No. While you’ll get the optimized page loading that AMP provides, without caching you will not get:
									- AMP icon in Google search.
									- Chance to appear in AMP specific features such as Top Stories Carousel.
									- Content providers (i.e. Google) will not be able to pre-fetch your content. Meaning a delay (comparing to other AMP sites) from when user clicks on your link to when your content is presented in front of them.
								- Bottom line: The web cache is the core aspect of AMP project and the benefits of using AMP without cache are greatly reduced.
							- Google is using AMP to co-opt publisher's traffic. This means users are scrolling to another story from another publisher or easily bouncing back to the Google results when they land on your content. (See the X in the story link on the animated gif example.) There goes your time on site and long term user retention. If #1 was a problem for you already, you probably don't notice.
							- Google has a strong business interest in users never going to other sites. Between AMP & voice search, the future is going to be very rough for businesses that rely on free search traffic.
							- Stops external scripts from being used e.g. likely Piwik analytics or other non-Google analytics
							- Google owns 80% of the market. Google is a de-facto monopoly. They can force you to act against your long term interests for a short term gain. I personally find the gain suspicious, it's already possible to make fast pages. Soon, we'll all merely be Google content providers.
							- I don't think if you're running a business there's any way to avoid optimizing for Google in the short-term. You simply have to do it, if you want to be seen. Not optimizing for Google won't hurt Google, it'll just hurt you. Because Google can always just promote someone else.
							- If there's a symbol and sites with that symbol are faster, they'll learn to look for the symbol, perhaps not even consciously.
								- Even making your own non-AMP site fast won't matter because you're associated with all the other slow non-AMP sites
							- > Can I stop content from being cached? >No
							  > https://developers.google.com/amp/cache/faq
								- > No. By using the AMP format, content producers are making the content in AMP files available to be cached by third parties. For example, Google products use the Google AMP Cache to serve AMP content as fast as possible.
							- Incompatible with Divi Builder as of Jan 2017 - requires more dev on the WordPress AMP support
							  https://github.com/Automattic/amp-wp
						- Pros/Cons
							- Pros
								- Google ranks you higher (indirectly by offering a speedy website)
								- Faster
								- More visually appealing on Google
								  http://searchengineland.com/google-amp-carousels-multiplying-267572
								- AMP offers two primary benefits: fully asynchronous asset loading, and a CDN for free. That's a big deal. I don't know how well it works with dynamic pages, though.
								- Google's CDN network (inexpensive vs other options), as well as eligibility to show up in a premium organic listing via the mobile content carousel.
							- Cons
								- Privacy
									- AMP pages are loaded on Google, not the website they originate from
									  https://daringfireball.net/2016/10/why_publish_amp_pages
										- instead of redirecting users to an optimized version hosted on my server, Google was actually serving a snapshot of the page from their own cache
										- Essentially it's an improved version of Google cached content
										- Or RSS 2.0
								- Bad UX
									- Big blue bar at top prompting you to go back to Google - but it is scrollable at least now
										- https://webmasters.googleblog.com/2016/08/amp-your-content-preview-of-amped.html
									- Can't copy links
									- Stops some assets from loading eg comments
								- Limited
									- AMP HTML documents can not include any author-written JavaScript, nor any third-party scripts.
								- AMP pages encourage people to scroll right to the next AMP article.
								- Loss of brand individuality
								- Google shows their cached version of your page
									- The domain shown will be Google's, not your own
									- If you have AMP pages properly configured with analytics, ads and other goodies you might want, the traffic remains essentially yours. The cached URL might be shown, but everything on the page remains in the publisher’s control and is served from the publisher’s own site. It is your page, except for the URL.
									- This is something Google told me would be impossible for it to do, if the company wanted to continue to prerender AMP pages and to support features like swiping from one AMP story to the next.
						- How to
							- http://searchengineland.com/google-launches-new-amp-testing-tool-261061
							- Add a header on top of each page which redirects to real homepage
							- Also make every page title into a link
						- Similar to Facebook Instant Articles
						  https://instantarticles.fb.com/
							- https://instantarticles.fb.com/
						- https://www.ampproject.org/
					- http://dizzyzane.web.fc2.com/SpeedeeArticles/idlewords/website-obesity-crisis/#fake-fixes
				- Improvements done on PMM server/site
				  #PMM-Projects https://workflowy.com/#/ee2e40732b54
			- Website Builders
			  collapsed:: true
				- _See_ [Wordpress Plugin - Page Builders](https://workflowy.com/#/253a6778a8a1)
				- _See_ [Admin dashboards](https://workflowy.com/#/e21031e779cc)
				- ((663a58ee-e115-40ae-b1d8-18a08bad17f7))
				  collapsed:: true
					-
				- Appdrag
				  collapsed:: true
					- Check this: [https://appdrag.com](https://appdrag.com) There is a pagebuilder producing real code that you can export and also a cloud sql db and API builder also producing real code (node.js) that you can modify and/or export and run on your own.
					- Static files are stored in S3 and served by cloudfront. API endpoints are served by AWS Lambda, so it's quite fast and scalable.
					- It's also supporting advanced features like SSR and translations.
					- It's a low code solution, easy to use for non coders, and full access to source and advanced backend features for devs.
					- Disclaimer: I am the CTO ;)
					- Documentation: [https://support.appdrag.com/](https://support.appdrag.com/)
				- [http://luminaldev.com/](http://luminaldev.com/)
				- WebFlow
	- Web Browser
	  #WebBrowser [Web Browser](https://workflowy.com/#/3e78223f844a)
	- Databases
	  id:: 635036c7-aa13-4f35-abf6-bfc160f712f0
	  collapsed:: true
		- Database Management Systems (DBMS)
		  id:: 63baa382-4e87-4588-858c-1bf3ed4a685d
		  collapsed:: true
			- Database Engines
				- Types
					- ((16e48ca5-10dd-4c45-986c-5f03be9328c7))
					- Object-oriented database management system (OODBMS)
					  id:: 806fabd0-dc5b-45de-b504-d3d897c783a7
					- Object–relational database management system (ORDBMS)
				- Sorted by SQL/No
					- SQL
					  id:: 16e48ca5-10dd-4c45-986c-5f03be9328c7
					  collapsed:: true
					  AKA Relational (RDBMS) / Relational database management system (RDBMS)
						- Relational database management systems
							- [PostgreSQL](https://www.postgresql.org/)
							  id:: 63bae0ae-2db2-4cf2-b923-755efe250d86
							  collapsed:: true
								- Pros/Cons
									- Pros
										- Postgres can replace a ton of technologies
											- 1
												- Postgres can replace - up to millions of users - many backend technologies, Kafka, RabbitMQ, Mongo and ((6607f722-b674-4037-af49-e03bafebc259)) among them.
												- Use Postgres for caching instead of Redis with [UNLOGGED tables](https://www.compose.com/articles/faster-performance-with-unlogged-tables-in-postgresql/) and TEXT as a JSON data type. [Use stored procedures](https://chat.openai.com/chat) to add and enforce an expiry date for the data just like in Redis.
												- Use Postgres as a message queue with [SKIP LOCKED](https://www.enterprisedb.com/blog/what-skip-locked-postgresql-95) instead of Kafka (if you only need a message queue).
												- Use Postgres with [TimescaleDB](https://www.timescale.com/) as a data warehouse.
												  Use Postgres with [JSONB](https://scalegrid.io/blog/using-jsonb-in-postgresql-how-to-effectively-store-index-json-data-in-postgresql/) to store Json documents in a database, search and index them - instead of Mongo.
												- Use Postgres as a cron demon to take actions at certain times, like sending mails, with [pg_cron](https://github.com/citusdata/pg_cron) adding events to a message queue.
												- Use Postgres for [Geospacial queries](https://postgis.net/).
												- Use Postgres for [Fulltext Search](https://supabase.com/blog/postgres-full-text-search-vs-the-rest) instead of Elastic.
												- Use Postgres to [generate JSON in the database](https://www.amazingcto.com/graphql-for-server-development/), write no server side code and directly give it to the API.
													- [Storing JSON in Postgres using Node.js](https://medium.com/storing-json-in-postgres-using-node-js-c8ff50337013)
													- [JSONB PostgreSQL: How To Store & Index JSON Data](https://scalegrid.io/blog/using-jsonb-in-postgresql-how-to-effectively-store-index-json-data-in-postgresql/)
												- Use Postgres with a [GraphQL adapter](https://graphjin.com/) to deliver ((63a2bb46-8e4a-4d42-b382-f116c0f77196)) if needed.
													- [GraphJin](https://graphjin.com/)
														- [GitHub - dosco/graphjin: GraphJin - Build NodeJS / GO APIs in 5 minutes not weeks](https://github.com/dosco/graphjin)
													-
												- There I’ve said it, **just use Postgres for everything**.
											- [I replaced my entire tech stack with Postgres... - YouTube](https://youtu.be/3JW732GrMdg)
												- JSONB
													- Binary JSON, which means it supports NoSQL
												- pg_cron
													- CRON jobs
												- Unlogged Tables
													- In-memory cache database like ((6607f722-b674-4037-af49-e03bafebc259)) or ((64634999-fc4a-4bf0-9d74-f8dc23708311))
												- pgvector
													- Vector database
												- pgai
													- Vector embeddings
												- tsvector
													- Full text search engine
												- pg_graphql
													- Turns database into GraphQL API
												- ElectricSQL
													- Realtime sync layer
												- pgcrypto
													- Authentication, web tokens with pgjwt
												- MoonCake
													- Alternative to Google Analytics. Time series database
												- PostgREST
													- Serve DB into RESTful API
												- React Postgres Components
										- [GitHub - dhamaniasad/awesome-postgres: A curated list of awesome PostgreSQL software, libraries, tools and resources, inspired by awesome-mysql](https://github.com/dhamaniasad/awesome-postgres)
										-
								- # Ecosystem
									- [PostgREST – Serve a RESTful API from any Postgres database](https://postgrest.org/en/stable/index.html)
										- [PostgREST – Serve a RESTful API from any Postgres database | Hacker News](https://news.ycombinator.com/item?id=34172205)
									- [Show HN: Bi-directional sync between Postgres and SQLite](https://powersync.com)
										- [Show HN: Bi-directional sync between Postgres and SQLite | Hacker News](https://news.ycombinator.com/item?id=38473743)
									- [Postgres IDE in VS Code | Hacker News](https://news.ycombinator.com/item?id=44073588)
									-
								- [Learned Resources]
									- ILIKE operator
										- [PostgreSQL - ILIKE operator - GeeksforGeeks](https://www.geeksforgeeks.org/postgresql-ilike-operator/)
									- https://www.tutorialspoint.com/postgresql/index.htm
									- https://www.postgresqltutorial.com/postgresql-cheat-sheet/
								- Related:
									- ((63904f3c-fae7-41e9-870c-43837ab8f4e5))
									- ((635663a4-50a5-44ab-aa72-9e8cdeb69537))
							- [MySQL](https://www.mysql.com/)
							  id:: 67376780-e2e5-43ae-af2b-3528c1a9e157
							- [SQLite](https://www.sqlite.org/)
							  id:: 67376780-ce02-49be-b98e-90b34da732d3
							  collapsed:: true
								- Used in
									- ((63a2c22f-17f6-466b-b7cf-fd92078ee2b8))
								- Forks
									- libSQL
										- t plans to do one database per user
										- `sqld` - server mode, allows it to be used in serverless environments like ((66317064-8967-4ccf-ad8f-b7008850a130))
										- Native replication
										- Encrypted-at-rest
								- # Ecosystem
									- [GitHub - benbjohnson/litestream: Streaming replication for SQLite.](https://github.com/benbjohnson/litestream)
										- [Litestream: Revamped | Hacker News](https://news.ycombinator.com/item?id=44045292)
										-
							- [MariaDB](https://mariadb.org/)
						- Documentation
							- Cheatsheet
								- ((63e40d9f-1155-418b-83dc-aa5caa4654fe))
								- Table aliases
								  id:: 63f624a9-c52b-4a4c-8db5-0d5656346c36
								  collapsed:: true
									- table aliases or shorthand names that are used to reference the `bookings` and `members` tables, respectively.
									- Table aliases are commonly used in SQL queries to provide shorter names for tables and make the queries easier to read and write. In this example, `bks` is an alias for the `bookings` table, and `mems` is an alias for the `members` table.
									- The alias is defined after the table name, separated by a space. In the example query, the `FROM` clause specifies the `cd.bookings` and `cd.members` tables and gives each of them an alias. This allows the `starttime` column to be selected from the `bookings` table using the shorthand `bks.starttime`, and the join condition can reference the `mems` alias for the `members` table.
									- Using aliases can make SQL queries shorter and easier to read, especially when working with complex queries that reference multiple tables.
									- Examples
										- `bks` and `mems` here
										  ```sql
										  SELECT starttime
										  FROM cd.bookings bks
										  INNER JOIN cd.members mems
										  ```
										- ((63f62339-286e-456b-b8e0-de11e85336db))
								- `SHOW DATABASES;`
								- `use <database-name>`
									- e.g. `use sakila`
									- Must do this in order to use ((66607591-870e-4702-b937-d9fb21b078d1))
								- `SHOW TABLES;`
								  id:: 66607591-870e-4702-b937-d9fb21b078d1
							- Learning resource sorted by priority
							  id:: 9af00762-3ba7-4c1c-9978-ce4b6077be2c
								- ((6356a6af-0197-4196-a6ab-258c05ba4f27))
								- ((63581b59-a4ae-419c-84e0-6d9fd9d3237c))
								- ((6385d632-d548-4dc3-a04f-88aff1876a82))
							- Completed learning resources (references)
						- [Learning Resources]
						  collapsed:: true
							- ((9af00762-3ba7-4c1c-9978-ce4b6077be2c))
								- {{embed ((9af00762-3ba7-4c1c-9978-ce4b6077be2c))}}
							- Kysely - TypeScript SQL Query Builder [GitHub - kysely-org/kysely: A type-safe typescript SQL query builder](https://github.com/koskimas/kysely) [Kysely: TypeScript SQL Query Builder | Hacker News](https://news.ycombinator.com/item?id=34506657)
							- Backups
								- [Other Logseq](<((654187dd-a10e-4187-8f77-9c09213836da))>)
							- [SQL Tutorial](https://www.w3schools.com/sql/default.asp)
							  collapsed:: true
								- [SQL LIKE Operator](https://www.w3schools.com/sql/sql_like.asp)
									-
							- [Channel](https://www.usechannel.com/)
							- [Lost At SQL: I made a SQL game to help people learn / challenge their skills](https://lost-at-sql.therobinlord.com/)
								- https://news.ycombinator.com/item?id=35665142
							- Cheatsheet
							  collapsed:: true
								- ![Screen+Shot+2016-04-17+at+12.22.49+PM.png](../assets/Screen+Shot+2016-04-17+at+12.22.49+PM_1729716162529_0.png)
							- Courses
								- [Master SQL](https://roadmap.sh/courses/sql)
								- [SQL Noir – Learn SQL by solving crimes](https://www.sqlnoir.com)
								-
						- Related:
							- ((635663a4-50a5-44ab-aa72-9e8cdeb69537))
					- [NoSQL](https://en.wikipedia.org/wiki/NoSQL)
					  id:: 64634999-f8bf-4650-9e69-f68bda7d4cd5
					  collapsed:: true
					  AKA Non-relational database
						- Pros/Cons\_
						  collapsed:: true
							- Pros
								- Changing the database schema in SQL is a nightmare. Being schema-less offers more flexibility
								- Horizontal scaling through extra nodes/machines is possible, whereas SQL DB it's harder
							- Cons
								- Lacks [ACID](https://wikiless.tiekoetter.com/wiki/ACID) guarantees
								- Less community support, documentation compared to SQL
								- Unnecessary duplication of data within the same DB
							- Unclear
								- [Eventual consistency](https://www.enterpriseintegrationpatterns.com/ramblings/18_starbucks.html)
							- _Benefits and cons for MMOs_
							  collapsed:: true
								- Related: Spatial data NoSQL
								  intralink2:: https://workflowy.com/#/105caaa723dd
								- https://www.gamedev.net/forums/topic/628223-mmo-and-databases/
								- I've done a bit of SQL work, and my impression is that it would be a bit like a square-peg-in-a-round-hole situation trying to get the relational model to make sense for an MMO. If we take the simplified case of just inventory management, would you maintain a table of every item in the game universe, and have a field defining a UID for which container it lived in? Wouldn't that make a simple query like "what's in my inventory?" take forever? Many MMOs get around this by having a limited number of slots in your inventory, with few objects existing outside of players' inventories (or in banks) but if you wanted to really open that up and do an inventory system like the late Ultima games, or even something like Skyrim, where the player can have hundreds of unique items, and there are tens of thousands of unique items randomly placed throughout the world, I imagine things quickly get hairy. You'd probably also want a database model that lends itself to spatial queries (what items exist within a 20 meter bubble of some position in the world), which isn't something relational databases do very well.
								- ..
								- The trick when using a RDMS is the crazy variety of attributes an item or character may have. For example what buffs apply, what resistances things have, etc etc. I don't have a great answer so far. You can have very wide tables with lots of attributes, spin off sub-tables, serialise data in a single column, etc etc. How does it work if you add new features? Nobody wants to modify the schema of a running MMO if they can help it.
								- ..
								- Sharding for performance
								  collapsed:: true
									- A query for "what's in my inventory" does not take forever if you have proper indexes.
									- However, you don't want a relational database table to grow too big, because that leads to poor performance. Instead, you will need to shard the storage somehow. Many MMOs simply shard by "world instance." Shared-world systems will have to shard by consistent hashing or similar.
									- Once you shard your data, you probably can't do transactions across shards, so no inter-server player trades without escrow for example. Unless you build your system using the large, expensive, "enterprise" versions of DB/2 or Oracle. Which you probably shouldn't :-)
									- The Cryptic Studios guys had a GDC presentation a few years ago about how their design migrated from RDBMS through a number of caching and re-structuring steps to an object-store database. Other developers stay with RDBMS-es. It all depends on what your particular trade-off between run-time performance, willingness to cache in RAM, cost of hardware, cost of development, and game rules is.
								- RDBMS/SQL comes with 3 very major advantages:
								  collapsed:: true
									- 1. It's ubiquitous, there are literally millions of experts on the market, bindings for every language, and middleware readily available
									- 2. The respective implemenations have been tested in millions of installations, concepts have been tested millions of times
									- 3. ACID compliance (which is equally important as it is hard to get right) is understood as a natural, basic features in all mainstream implementations, and it has been tested on millions of installations. It will "just work" and unless you explicitly do something very stupid, it won't bite your ass when you don't expect it.
								- I'm looking at various NoSQL systems right now. They seem to fit closer to the mental model you have for how an MMO works. MongoDB especially seems promising. It has spatial queries and indexing, which you'd need if you want to have, say, large numbers of items floating freely in the world (ala Ultima Online, if anyone remembers that game). In the case of storing bags of items, it also has arrays natively supported. So you could have bags represented as documents in a collection (ie: as rows in a table), with items stuffed in to an array inside each bag document (row). It feels very similar to how tables work in Lua, actually. It seems to map pretty well to OOP. The primary downside is that it's not ACID compliant. So transactions (like moving an item from one bag to another) get tricky and you probably have to manage a two-phase commit manually.
						- Sorted by
							- _Notable products_
								- ((63a9bb62-f035-405e-b4c9-633f8b95c38b))
								  collapsed:: true
									- Pros/Cons
									  collapsed:: true
										- Pros
										  collapsed:: true
											- Very easy to query compared to SQL
									- Comparisons
									  collapsed:: true
										- ((63921751-9f8d-45b2-a33f-90d9020c6fd8))
										  collapsed:: true
											- {{embed ((63921751-9f8d-45b2-a33f-90d9020c6fd8)) }}
								- object storage in Postgres (jsonb fields)
							- _Types_
								- [Key-value database](https://en.wikipedia.org/wiki/Key-value_database)
								  id:: 64634999-79da-4354-8f74-4a85427a1aa8
								  collapsed:: true
									- Pros
									  collapsed:: true
										- Great for caching i.e. storing frequently accessed data in memory rather than disk
										- Good fro session management - data stored as long as the user is logged in, then later discarded
									- Examples
										- ((63904f38-5b8c-48f0-97f1-9d4c04eb211c))
										- [Memcached](https://memcached.org/)
										  id:: 64634999-fc4a-4bf0-9d74-f8dc23708311
											- Memcached is a high-performance, distributed memory object caching system, generic in nature, but intended for use in speeding up dynamic web applications by alleviating database load
											- [Bitnami package for WordPress for AWS Cloud](https://docs.bitnami.com/aws/apps/wordpress/#how-to-install-the-memcached-module-using-the-libmemcached-library)
										- ((6391e86b-0a86-47d1-aa3d-7473eeceeb0b))
										- AWS DynamoDB
										- [lmdb-js](https://github.com/kriszyp/lmdb-js)
										  collapsed:: true
											- [Since 2021](https://www.gatsbyjs.com/docs/reference/release-notes/v4.0/) now being used instead of Redux in Gatsby
										- Source available, not FOSS
											- [Redis](https://redis.io/)
											  id:: 6607f722-b674-4037-af49-e03bafebc259
										- [Valkey](https://valkey.io/)
										  [FOSS fork of](https://github.com/valkey-io/valkey) ((6607f722-b674-4037-af49-e03bafebc259))
										- Related: ((63904f38-908c-4905-a795-2b45d54a9e44))
								- [Document database](https://en.wikipedia.org/wiki/Document-oriented_database)
								  collapsed:: true
									- Examples
										- [MongoDB](https://www.mongodb.com)
										  id:: 63a9bb62-f035-405e-b4c9-633f8b95c38b
										  collapsed:: true
											- Pros
												- Spatial data
												  https://docs.mongodb.com/manual/geospatial-queries/
											- Cons
												- Still only somewhat ACID compliant since 2018
												  intralink2:: https://workflowy.com/#/e56b558e742d
													- https://www.mongodb.com/blog/post/multi-document-transactions-in-mongodb
													- https://www.mongodb.com/transactions
													- There is no easy "atomic" updates to multiple collections and even multiple documents in the same collection. It's not a problem in most cases because it can be circumvented with Two Phase Commit, or restructuring your schema so updates are made to a single document.
													- https://stackoverflow.com/questions/7149890/what-did-mongodb-not-being-acid-compliant-before-v4-really-mean
											- [Install MongoDB — MongoDB Manual](https://www.mongodb.com/docs/manual/installation/)
											- [mongodb - npm](https://www.npmjs.com/package/mongodb)
											- https://www.mongodb.com/languages/javascript/mongodb-and-npm-tutorial
											- [Learning Resources]
												- ((63ea1938-5a8e-4b77-a3d5-4a72dc88ba02))
												-
										- Couchbase
										  collapsed:: true
											- Pros/Cons
												- Pros
													- Couchbase is for high-performance only because it's NoSQL but with an in-memory database like Memcached infront of it
												- Cons
												- Comparison of ((6391e86b-0a86-47d1-aa3d-7473eeceeb0b)) with ((6391e874-5f03-4a15-8263-bbf865e65615))
												  collapsed:: true
													- Couchbase cons
													  collapsed:: true
														- Their free hosted plan is only a 30 day trial
														- Their managed hosted plan is [pretty expensive](https://www.couchbase.com/pricing) - $720/month minimum?
														- [Couchbase is nowhere near as popular as MongoDB](https://insights.stackoverflow.com/survey/2021#section-most-popular-technologies-databases)
													- MongoDB cons
													  collapsed:: true
														- School of Code have some sort of business relationship with Couchbase, they may be more likely to hire me if I use their DB
													- Unsure
													  collapsed:: true
														- You have to use SQL++ which is basically SQL for accessing the JSON. Unlike MongoDB which allows you to access it normally like JSON - [Query Documents — MongoDB Manual](https://www.mongodb.com/docs/manual/tutorial/query-documents)
														- [MongoDB supports Elasticsearch?](https://code.likeagirl.io/5-different-ways-to-synchronize-data-from-mongodb-to-elasticsearch-d8456b83d44f)
											- Documentation
											- Related:
												- ((63904f45-75cb-44d9-a073-f86950b882f5))
												- ((63974fae-f647-4f75-9f79-5c0766865aa5))
										- CouchDB
										  collapsed:: true
											- Pros
												- Spatial data (Geocouch plugin)
										- Elasticsearch
										- PostgreSQL
										  intralink2:: [A simpler way to organize your work - Workflowy](https://workflowy.com/#/dd2c2d08a4e2)
										- MonooDB
										- Azure Cosmos DB
										- ((6391e86b-0a86-47d1-aa3d-7473eeceeb0b))
										- [Litestore](https://github.com/h3rald/litestore) - self-contained (built on ((63b9934f-1259-4546-8611-fba0c1a87ee3)) )
										  id:: 63b993a7-4e55-4137-a7d2-aba11803ef9e
										  collapsed:: true
											- [LiteStore - H3RALD](https://h3rald.com/litestore)
											- Related:
												- ((63b9934f-1259-4546-8611-fba0c1a87ee3))
												- ((63a2c22f-17f6-466b-b7cf-fd92078ee2b8))
								- Graph database
								  collapsed:: true
									- Pros
									  collapsed:: true
										- Good for social networks
									- Examples
										- Neo4j
										- OrientDB
										- InfiniteGraph
								- Column-Family database
								  collapsed:: true
									- Pros
									  collapsed:: true
										-
									- Examples
										- Cassandra
										- Apache HBase
										- ((6363a8b1-4497-44a3-aad9-82eb124080bc))
								- Vector database
								  collapsed:: true
									- _Meta_
									  collapsed:: true
										- A vector is an array of numbers. They can represent words, sentences, images, audio, etc
									- Weaviate
									- Pinecone
									- [Chroma](https://www.trychroma.com/)
									  collapsed:: true
										- [GitHub - chroma-core/chroma: the AI-native open-source embedding database](https://github.com/chroma-core/chroma)
									- Milvus
									- pgvector
									- redisearch
							- _Other evaluating criteria_
							  collapsed:: true
								- ACID compliancy
									- Pros/Cons
									  collapsed:: true
										- Pros
											- Ensures consistent data and no data loss
										- Cons
											- Limits scalability
												- Sometimes you can work around the lack of these features because you need to scale horizontally or scaling becomes your first and primary concern. You may not need need consistency now, you may be able to handle it later (eventual consistency). You may not need all the data returned in order: you may want the queries executed in parallel over clusters. Or your data may itself be fairly un-valuable.
												- Assuming nothing in the database is really dependent on the order of inserts, modifications or deletes, it vastly improves performance.
									- https://en.wikipedia.org/wiki/NoSQL#ACID_and_join_support
									- RavenDB
									- MongoDB (partially)
									- OrientDB
									- Neo4j
									- CouchDB
								- Spatial data
									- Apache CouchDB
									- MongoDB
									- SpaceBase
										- http://www.paralleluniverse.co/spacebase/
							- Comparisons
							  collapsed:: true
								- http://kkovacs.eu/cassandra-vs-mongodb-vs-couchdb-vs-redis
						- Related: ((63904f46-8a89-4b1d-a2dc-634d38cba4fc))
				- Misc
					- In-memory
					  collapsed:: true
						- ((6463499e-529d-478c-822f-2ff43f26b6bf))
						- ((64b7f38a-d557-4a8d-8f77-d9a80e3ee23f))
						- ((64634999-fc4a-4bf0-9d74-f8dc23708311))
						- ((6607f722-b674-4037-af49-e03bafebc259))
						- [GitHub - electric-sql/pglite: Lightweight Postgres packaged as WASM into a TypeScript library for the browser, Node.js, Bun and Deno](https://github.com/electric-sql/pglite)
						  [Show HN: I open-sourced the in-memory PostgreSQL I built at work for E2E tests | Hacker News](https://news.ycombinator.com/item?id=39960537)
						-
					- Datalog DBs
					  collapsed:: true
						- [DataScript](https://github.com/tonsky/datascript)
							- In-memory Immutable database and Datalog query engine that runs in the browser
							- [npm package](https://www.npmjs.com/package/datascript)
							- Used by Logseq, etc
						- http://datomic.com/
					- NewSQL
					  collapsed:: true
						- class of modern relational database management systems that seek to provide the same scalable performance of NoSQL systems for online transaction processing (OLTP) read-write workloads while still maintaining the ACID guarantees of a traditional database system
						- https://en.wikipedia.org/wiki/NewSQL
						- _Examples_
							- VoltDB
							  collapsed:: true
								- https://en.wikipedia.org/wiki/VoltDB
								- is an in-memory database designed by Michael Stonebraker (who was involved in Ingres and PostgreSQL), Sam Madden, and Daniel Abadi. It is an ACID-compliant RDBMS which uses a shared nothing architecture. It includes both enterprise and community editions.
								- Michael Stonebraker really is a man to listen to when it comes to database technology, being successful both on the academic and commerical fronts.
								- He agrees with the fundamental premise of NoSQL that what he terms OldSQL is broken! He just argues (forcibly) that throwing out ACID guarantees is literally throwing the baby out with the bathwater.
								- What he argues for is ACID compliant databases without all the locking and transactional overhead of systems like Oracle, MS SQL Server, PostgreSQL and MySQL inter alia. He also suggests that they should be sent to the "home for retired software" :-)!
								- How, you may ask? Well, two ways:
								- His point about NewSQL is that for OLTP apps, you need a shared-nothing sharded architecture (check out his VoltDB - based on HStore) and that for OLAP you need dedicated columnar stores, i.e. Vertica (based on CStore, which he sold to HP).
								- To answer the actual question directly: "Why are nosql databases not acid compliant" is because they weren't designed to be. ACID is a lot of work and requries
							- Spanner (by Google)
							  collapsed:: true
								- not pure relational database system because each table must have a primary key column.
								- [source] https://en.wikipedia.org/wiki/Spanner_(database)
							- See Apache Ignite
							- MariaDB Columnstore
			- Sorted by company
				- Vercel
				  collapsed:: true
					- Vercel now supports 4 hosted database services - Postgres, KV (based on ((6607f722-b674-4037-af49-e03bafebc259)) + Upstash), Edge Config, Blob (built on CloudFlare R2, it's object storage like S3)
					  including a serverless Postgres database, a durable Redis store, and file uploads with CloudFlare R2
			- [Learning Resources]
				- [Database Fundamentals](https://tontinton.com/posts/database-fundementals/)
				-
		- Database access GUIs
		  collapsed:: true
			- _Web app_
				- Adminer
				  collapsed:: true
					- 1 Backlink
						- See [Adminer](https://workflowy.com/#/d752396fb47a)
					- How to use with Docker
						- Example credentials for Baserow
							- URL for Adminer
							  [http://localhost:8069](http://localhost:8069)
							- username: baserow
							- password: zLEUtJKhvUM7Pt6
							- database: baserow
							- server: db
								- This is because when using docker-compose containers in the same network can be accessed using their service name as defined in the docker-compose. This means the adminer container should be able to connect to the hostname db which will be the db container. Additionally this means you don’t need to expose the port for the db container as if containers are on the same network then they can access all of the other containers ports (unless you also want to access the postgres db from some other non-docker host on the server or externally).
				- [GitHub - paraswaykole/slashbase: Modern database IDE for your dev & data workflows. Supports MySQL, PostgreSQL & MongoDB.](https://github.com/paraswaykole/slashbase)
				-
			- _Desktop app_
				- DBeaver
				  collapsed:: true
					- Flatpak install
					  flatpak install flathub io.dbeaver.DBeaverCommunity
					- Example credentials for Baserow
						- username: baserow
						- password: zLEUtJKhvUM7Pt6
						- database: baserow
						- server: localhost
						- port: 5432
						- docker-compose.yml also needs an exposed port for `db` service if using DBeaver:
						  db:
						  ports:
							- "${HOST_PUBLISH_IP:-127.0.0.1}:${POSTGRES_PORT:-5432}:5432"
				- [TablePlus](https://tableplus.com/)
				  collapsed:: true
					- [No Flatpak yet](https://github.com/TablePlus/TablePlus-Linux/issues/149#issuecomment-1961119055)
					- [GitHub - TablePlus/TablePlus: TablePlus macOS issue tracker](https://github.com/TablePlus/TablePlus)
				- [Install Beekeeper Studio on Linux | Flathub](https://flathub.org/apps/io.beekeeperstudio.Studio)
				  A modern, easy to use, and good looking SQL client for MySQL, Postgres, SQLite, SQL Server, and more.
				-
			- Azure Data Studio: An Open-Source GUI Editor for Postgres - [https://news.ycombinator.com/item?id=19423539](https://news.ycombinator.com/item?id=19423539)
		- Schema
		  id:: 67404be3-17f4-4395-ade7-c6da98913a05
		  collapsed:: true
			- Database Builder
			  collapsed:: true
				- [Ragic](http://www.ragic.com/)
				  Web database builder which is as simple as Excel
				- https://zapier.com/learn/forms-surveys/simple-database-app-builders/#need
				- Zoho Creator
				- Microsoft Office Access
				- LibreOffice - Base
				- https://www.knack.com/
				- Related: [[Project Management Software]] : [Spreadsheet-Database hybrids](((663904b1-af62-4dbb-9e10-edf132813c19))) (other LS)
			- Planning
				- [drawDB | Online database diagram editor and SQL generator](https://drawdb.app/)
				  [GitHub - drawdb-io/drawdb: Free, simple, and intuitive online database diagram editor and SQL generator.](https://github.com/drawdb-io/drawdb)
				- Entity-Relationship Diagramming (ERD)
				  id:: 63ff4fed-088c-4540-83f4-24954cd3b566
				  collapsed:: true
					- # Software
						- Logseq plugins
							- Mermaid
								- [[Logseq]] : ((63503767-a6e1-4cd1-b790-913f39ac8a00))
								- [[Logseq]] : ((663a5794-5b1f-4361-b5ab-a37bcf6013d3))
								- Examples
									- {{renderer code_diagram,mermaid}}
										- ```mermaid
										  erDiagram
										  CUSTOMER ||--o{ ORDER : places
										  ORDER ||--|{ LINE-ITEM : contains
										  CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
										  ```
							- Related: [DBML - Database Markup Language](https://dbml.dbdiagram.io/home)
					- # Examples
						- ![image.png](../assets/image_1666689903250_0.png)
							- Primary key = `Users.user_id`
							- Foreign keys = `Comments.author` and `Posts.author`
					- # Symbols
						- ![ERD-Notation.PNG](../assets/ERD-Notation_1677676625776_0.PNG)
						- Foreign keys
							- Foreign keys are created any time an attribute relates to another entity in a one-to-one or one-to-many relationship.
							- Each car can only be financed by one bank, therefore the primary key `BankId` from the `Bank` table is used as the foreign key `FinancedBy` in the Car table.  This `BankID` is able to be used as the foreign key for multiple cars.
							- ![Foreign Key Example](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/erd-symbols/Keys.PNG)
			- [Found a simple tool for database modeling: dbdiagram.io | Hacker News](https://news.ycombinator.com/item?id=43808803)
			-
		- [[Project Management Software]] : [Spreadsheet-Database hybrids](((663904b1-af62-4dbb-9e10-edf132813c19))) (other LS)
		- Database Version Control
		  collapsed:: true
			- LiquiBase
			  http://liquibase.org/
			- Doctrine Database Migrations
			  https://github.com/doctrine/migrations
				- http://docs.doctrine-project.org/projects/doctrine-migrations/en/latest/reference/introduction.html
			- http://databaserefactoring.com/
		- Object–relational mapping (ORM)
		  collapsed:: true
			- What
				- A layer for ((63a307c8-fe3c-48fc-84a5-0d84da521338)) so you can treat them as ((63a307cd-c53a-43f3-a7ea-4026a557006d)) / ((63a307dd-3d0e-4614-93a0-d51f8821ef84)) ? (((806fabd0-dc5b-45de-b504-d3d897c783a7)))
			- Software
				- [Prisma](https://www.prisma.io/)
				  id:: 63a30713-fe4a-4f2a-8d6a-c658a01d24bc
				  collapsed:: true
					- Pros/Cons
						- Pros
							- TypeScript safety whilst to access SQL databases
							- intuitive data model, automated migrations, type-safety & auto-completion
					- What
						- Next-generation ORM for ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) & ((629ccb26-1eab-4686-a7b8-f9433a871440))
						- [Works with](https://www.prisma.io/stack) many types of ((16e48ca5-10dd-4c45-986c-5f03be9328c7)) plus ((63a9bb62-f035-405e-b4c9-633f8b95c38b))
						- Compatible with many frameworks including NextJS, NestJS, GraphQL, Express, etc
						- is an alternative to ((63904f3c-fae7-41e9-870c-43837ab8f4e5))
						- ((63a30f58-6e07-4752-8555-f18d4f48d91b))
						- [Used to be built on GraphQL](https://www.prisma.io/blog/prisma-and-serverless-73hbgKnZ6t), now instead built on JSON
						- Used in
							- ((63a2f545-a921-4726-b477-e84a86fdbf5b))
					- Documentation
						- Combining ((63a30713-fe4a-4f2a-8d6a-c658a01d24bc)) with ((63a9bb63-857e-4380-9c0c-6b0c6d60f364))
						  id:: 63df86be-87bf-443e-b10b-77795b1b6351
						  collapsed:: true
							- *Database*
								- https://supabase.com/docs/guides/integrations/prisma
								- [Build a Full-Stack App with Next.js, Supabase & Prisma](https://alterclass.io/courses/build-a-fullstack-app-with-nextjs-supabase-and-prisma-322389284337222224)
								- [Set up a free PostgreSQL database on Supabase to use with Prisma - DEV Community 👩‍💻👨‍💻](https://dev.to/prisma/set-up-a-free-postgresql-database-on-supabase-to-use-with-prisma-3pk6)
								- [Supabase and Prisma workflow compilation · Discussion #7659 · supabase/supabase · GitHub](https://github.com/supabase/supabase/discussions/7659)
								-
							- *Auth*
								- I’m doing this right now for a personal project and it’s working well! I need to make a blog post because some things I had to figure out for myself. Do you need to create a database entry for each authenticated user?
									- If so, the trick is to setup a Supabase trigger to add a row when a new user is authenticated.
									- You can also go on GitHub and search “supabase auth prisma” to find examples.
									- ...
									- Hey sorry for late reply! My project is open source. Here’s the repo and branch I’m working off of. I need to update the README. But to push up Prisma schema changes it’s just “npx prisma db push” iirc.
									- DM if you have any questions about this.
									- https://github.com/quentinlintz/progress/tree/foundation
								- Use prisma middleware to inject current user on supabase queries before any prisma query [[Supporting Postgres' `SET` across queries of a request · Issue #5128 · prisma/prisma · GitHub](https://github.com/prisma/prisma/issues/5128#issuecomment-921179713](https://github.com/prisma/prisma/issues/5128#issuecomment-921179713)) and leverage RLS/policies capabilites
						- Combining ((63a30713-fe4a-4f2a-8d6a-c658a01d24bc)) with ((63a2c22f-17f6-466b-b7cf-fd92078ee2b8))
						  id:: 63df8f12-9671-4cb1-b5a3-5a1f390adf5e
							- You don't need external orm to work with PocketBase. We have advanced query support via a simple filter syntax, eg.: "status = 'pending' || status = 'active'". You can even query nested relation fields, eg. `someRel.totalComments > 100` (check [pocketbase.io/docs/manage-co…](https://pocketbase.io/docs/manage-collections/#rules-filters-syntax))
							- what is the point of using PocketBase in the first place if you are going to query the database with Prisma or any other external orm?
							  You want to use PocketBase because of the abstractions that it provide - you have pagination, sorting, validations and most importantly acces checks for your data. It's not just db read/write.
					- [Learning Resources]
						- [GitHub - bennyfreemantle/next-prisma-demo: A quick next app using prisma to connect to a postgres database - learning purposes](https://github.com/bennyfreemantle/next-prisma-demo)
				- [SQL Alchemy](https://www.sqlalchemy.org/) - Python-based ORM for SQL-based databases
		- [Learning Resources]
			- https://news.ycombinator.com/item?id=34220524
			-
		- Related:
			- Databases for game development
			  #Multimedia-Videogames-Design https://workflowy.com/#/801da68a1aba
			- ((635036c9-37a1-4e61-80bb-8eb1e04980c7))
			  #Infrastructure
	- See DNS
	  #Infrastructure [DNS](https://workflowy.com/#/3b93cb4c2994)
	- CDN
	  collapsed:: true
		- Caching server. They sits between your hosted server and user and caches different pages of website. Usually these servers are also distributed across different locations. When user wants to view a page, if that page is already cached by user's nearest server, it will be server quickly from thers without contacting to original hosted server, otherwise it will be cached and served to user.
		- This kind of solution if your website is static/does not depend on who is accessing, this makes website cachable.
		- _Providers_
			- CloudFlare
			  collapsed:: true
				- Pros
					- Fast CDN
				- Cons
					- If you set up 2 of their DNS servers, it means you decide that all the traffic that is exchanged with your web server goes through cloudflare.
					- Consequently, you hand over a part of your webmaster power to Cloudflare.
					- First of all you add a single point of failure to the chain that leads to your website. If for some reasons the cloudflare service goes down the pipe you site will become unavailable.
					- Since all your traffic goes through their servers, depending on the options you choose the cloudflare service:
					- Inject javascript into your code while returning pages.
					- It modifies the code of your pages.
					- Modify the http headers of your pages. For instance, it adds a cookie entry.
					- If they want, cloudflare has the ability to:
					- block your website
					- Monitor all your visitors & gather information about them
					- If your web server does not work well with Cloudflare (misconfiguration), your website may not be available without you noticing it.
					- Since many websites using cloudflare get the same IP and same DNS, and since your website finds himself with other websites that aren't as nice as yours (Sites with malwares, phishing), it is theoretically possible that Google penalizes all the websites behind those IPs. (It already happened with some web servers by the past).
					- In the future, if a massive number of webmasters decide to use Cloudflare all over the world, Cloudflare could become a single point of access on the internet. It can turn into "big brother".
					- Nevertheless from a technical point of view cloudflare is the best CDN. They have the best engineers who understand everything about the Internet. Also, i have noticed the IPs from their network have good reputation for Google. There are also considered as generic, not country specific. Also the reliability of their CDN never stops increasing.
			- AWS CloudFront
	- FTP
	  collapsed:: true
		- FTP info template
			- FTP
				- test2.postmymed.com
			- FTP USER
				- dev@test2.postmymed.com
			- PASS
				- $Kwdas~qE~V5
- _Supplementary_
  collapsed:: true
	- Encrypt data (at rest)
	  collapsed:: true
		- _Database_
		  collapsed:: true
			- MariaDB encryption (+ Percona XtraBackup encrypted incremental)
			  collapsed:: true
				- https://mariadb.com/kb/en/mariadb/data-at-rest-encryption/#limitations
				- https://mariadb.com/kb/en/mariadb/verifying-mariadb-101-encryption/
				- https://mariadb.com/kb/en/encryption/
				- https://mariadb.com/kb/en/mariadb/mariadb-vs-mysql-compatibility/
				- https://www.digitalocean.com/community/tutorials/switching-to-mariadb-from-mysql
			- WordPress database encryption
			  collapsed:: true
				- Custom freelance job
					- Just encrypt customer details table, decrypt for WordPress users with Content Editor role
				- Messaged one guy - several others recommended on his page
					- https://geek.hellyer.kiwi/services/
					- Hello, I came across your end-to-end encryption and I'm interested in hiring you to develop this plugin to encrypt WooCommerce data - just customer info (name, contact info, address) in the orders and within their user profiles.
			- AWS RDS encryption
		- dm-crypt/LUKS
		- VeraCrypt
		- Server FDE encryption
		  collapsed:: true
			- Partition or full disk encryption not possible at rest - only filesystem level
				- https://www.digitalocean.com/community/tutorials/how-to-use-dm-crypt-to-create-an-encrypted-volume-on-an-ubuntu-vps
				- https://launchbylunch.com/posts/2014/Jan/13/encrypting-docker-on-digitalocean/
			- Performance hit in exchange for encryption
		- GPG
	- Backup Strategy
	  id:: 64634999-59af-4326-82dd-d835db9ff7f7
	  collapsed:: true
		- FIxes for error
		  collapsed:: true
			- https://postmymeds.co.uk/wp-admin/admin.php?page=backwpup
			- https://postmymeds.co.uk/wp-admin/admin.php?page=backwpupabout
			- Mailgun errors
				- dbindex cache file is out of date: “/var/cpanel/databases/dbindex.db.json
					- https://forums.cpanel.net/threads/the-dbindex-cache-file-is-out-of-date-var-cpanel-databases-dbindex-db-json.496151/
				- http://i.imgur.com/8xC7rar.png
				- and see notepads
			- https://serverfault.com/questions/665231/the-alias-directive-will-probably-never-match-because-it-overlaps-an-earlier-ali
		- Snapshots (versioning)
		  collapsed:: true
		  Like System Restore or Time Machine (same client)
			- Snapshots vs backups
			  collapsed:: true
				- What’s the Difference Between System Snapshots and Backups?
				- Semantics may vary, but generally speaking, backups are copies of files kept in a location separate from the files themselves. Backups rarely include everything on a disk; when they do, they’re called disk images or disk clones. This type of backup “mirrors” the entire disk, including user data, the operating system, boot sectors, and more. Disk images can be used in the bare metal restore process, where you copy the contents of a hard disk onto a computer without an OS.
				- Snapshots, on the other hand, are saved states of a filesystem created at specific points in time and kept on the same storage device as the filesystem. They usually include all directories and files of a filesystem, or at the very least, the files required by the OS.
				- Keeping the snapshot in the same place as the filesystem makes it possible to perform a rollback, but it also saves disk space. In this setup, each new snapshot doesn’t have to save the entire filesystem state. Instead, snapshots act like incremental backups and save only changes that were made since the last snapshot. This means that every snapshot depends on the previous one to fully restore the system. Conversely, a full backup or a disk image is independent of other backups, and can restore the system on its own.
				- linux-system-restore-disks
				- The problem with snapshots is they’re vulnerable to disk failures — if your disk suffers severe mechanical damage, you’ll likely lose the snapshots along with the entire filesystem. To prevent this, it’s recommended to make a snapshot right after you install and set up your Linux distribution, and copy it to a separate storage device.
			- Desktop GUI software
			  collapsed:: true
				- Deja Dup (comes pre-installed in Ubuntu Desktop)
				- Cronopete
				- BackInTime
				- TimeShift
				- System Restore alternatives for Linux (snapshots)
				  collapsed:: true
					- Article
					  http://www.makeuseof.com/tag/10-easy-ways-restore-linux-system/
				- Time machine-like
				  collapsed:: true
					- http://askubuntu.com/questions/647495/which-is-most-timemachine-like-backup-program-for-ubuntu
					- http://www.nuxified.org/blog/easy-linux-backup-software-time-machine-functionality/
					- https://www.google.bg/search?q=time+machine+for+linux&client=firefox-b&hl=en&sa=X&as_q=&nfpr=&spell=1&ved=0ahUKEwiD0qK8kMXSAhWqC5oKHSb3C5kQvwUICg
					- https://help.ubuntu.com/community/OSXApplicationsEquivalents#Time_Machine
					- https://github.com/laurent22/rsync-time-backup/blob/master/README.md
					- http://superuser.com/questions/153895/best-linux-backup-software-that-is-most-like-time-machine
				- ZFS GUI like
				  collapsed:: true
					- https://forums.freebsd.org/threads/58594/
			- Differential/delta backups with versioning
			  collapsed:: true
				- See [Borg](https://workflowy.com/#/4c41ad0d5600)
				- ZFS
				  id:: 6360e32e-29f9-4526-ac4e-59ead71baa88
				  collapsed:: true
					- Platforms
					  collapsed:: true
						- Native ZFS on Linux
						- Ubuntu 16.04 LTS ("Xenial Xerus"), released on April 21, 2016, allows the user to install the OpenZFS binary packages directly from the Ubuntu software repositories
					- What
					  collapsed:: true
						- It's a filesystem (alternative to standard ext4)
						- ZFS / btrfs are software RAID
					- https://en.wikipedia.org/wiki/ZFS#ZFS_compared_to_most_other_file_systems
					- zfs file system - that essentially versions your hard drive, then you can make a copy of it as normal
					  collapsed:: true
						- Zfs is Kinda like git but for an entire hard drive
					- Manual
					  collapsed:: true
						- http://www.howtogeek.com/175159/an-introduction-to-the-z-file-system-zfs-for-linux/
						- https://wiki.ubuntu.com/Kernel/Reference/ZFS
						- https://pthree.org/2012/04/17/install-zfs-on-debian-gnulinux/
						- http://zfsonlinux.org/
					- Recurring snapshots
					  collapsed:: true
						- https://community.spiceworks.com/how_to/15303-recurring-zfs-snapshots
						- https://github.com/zfsonlinux/zfs-auto-snapshot
						- https://zpool.org/zfs-snapshots-and-remote-replication/
						- Snapshots with time machine-like expiration
							- https://blogs.oracle.com/chrisg/entry/snapping_every_minute
							- https://zpool.org/zfs-snapshots-and-remote-replication/
						- zfSnap - for automatic creating and deleting rolling ZFS snapshots via cron
							- http://www.zfsnap.org/
							- http://www.zfsnap.org/zfsnap_manpage.html
							- https://github.com/zfsnap/zfsnap/wiki/zfSnap
						- zrep - zfs replication and failover
						  https://github.com/bolthole/zrep/blob/master/00-README
							- http://www.bolthole.com/solaris/zrep/
					- Restoring to previous snapshot
					  collapsed:: true
						- https://docs.oracle.com/cd/E19253-01/819-5461/6n7ht6r4m/index.html
						- https://thegeekdiary.com/zfs-tutorials-creating-zfs-snapshot-and-clones/
						- https://www.howtoforge.com/tutorial/how-to-use-snapshots-clones-and-replication-in-zfs-on-linux/#rolling-back-a-snapshot
						- http://www.tech-recipes.com/rx/1435/zfs-restore-a-filesystem-from-a-snapshot-backup/
					- As root filesystem
					  collapsed:: true
						- https://scotte.org/2016/12/ZFS-root-filesystem-on-AWS
					- GUI
					  collapsed:: true
						- https://github.com/will666/Open-ZFS-GUIs
						- https://blogs.oracle.com/talley/entry/manage_zfs_from_your_browser
					- Management tools
					  collapsed:: true
						- [https://bitbucket.org/ozmt/ozmt](https://bitbucket.org/ozmt/ozmt)
					- PMM ZFS setup
					  #PMM-SOPs https://workflowy.com/#/ffb17c8cb38b
					- How to Restore to a Previous Snapshot
					  collapsed:: true
						- Login via SSH and switch to root
						  sudo su
						- Use Midnight Commander for navigation
						- When you get to /var/www/postmymeds.co.uk then go to the hidden .zfs folder
						  cd .zfs
						- Look inside and decide what snapshot we want to restore
						- For zfs it can be done with zfs rollback, e.g.
						  zfs rollback zdatapool/www/postmymeds.co.uk@2017-05-26_14.11.01--24h
						- Note: if there's a more recent snapshot than the selected one, you'll need to add -r to force deletion of those snapshots
						  zfs rollback zdatapool/www/[postmymeds.co.uk](http://postmymeds.co.uk)@2017-05-26_14.11.01--24h -r
					- Ubuntu 19.10 has ZFS as an option
					  [https://ubuntu.com/blog/enhancing-our-zfs-support-on-ubuntu-19-10-an-introduction](https://ubuntu.com/blog/enhancing-our-zfs-support-on-ubuntu-19-10-an-introduction)
					- ZFS on Linux 0.7.13 - [https://news.ycombinator.com/item?id=19327351](https://news.ycombinator.com/item?id=19327351)
					- [https://itsfoss.com/what-is-zfs/](https://itsfoss.com/what-is-zfs/)
					- [The 'hidden' cost of using ZFS for your home NAS](<[https://louwrentius.com/the-hidden-cost-of-using-zfs-for-your-home-nas.html](https://louwrentius.com/the-hidden-cost-of-using-zfs-for-your-home-nas.html)>)
					- ((63503641-2c97-4f6a-9f32-f661e8c24716))
					- _Learning Resources_
					  collapsed:: true
						- https://www.howtogeek.com/175159/an-introduction-to-the-z-file-system-zfs-for-linux/
						- https://www.howtogeek.com/272220/how-to-install-and-use-zfs-on-ubuntu-and-why-youd-want-to/
						- https://wiki.ubuntu.com/Kernel/Reference/ZFS
						- https://github.com/zfsonlinux/zfs/wiki/faq
						- [Overview — ZFSBootMenu 2.3.0 documentation](https://zfsbootmenu.org/)
						-
					- _Related: _
						- btrfs
						  id:: 6360e32e-f263-4cdf-8473-c5b60e05cbe7
						  collapsed:: true
							- In 2008, the principal developer of the ext3 and ext4 file systems, Theodore Ts'o, stated that although ext4 has improved features, it is not a major advance, it uses old technology, and is a stop-gap. Ts'o believes that Btrfs is the better direction because "it offers improvements in scalability, reliability, and ease of management"
							- Btrfs is intended to address the lack ofpooling, snapshots, checksums, and integral multi-device spanning in Linux file systems.[8
							- ZFS vs btrfs
								- ZFS better as of 2015 but due to licence issues btrfs may surpass it (however Ubuntu now shipping with OpenZFS may have changed this)
								  https://www.reddit.com/r/linux/comments/32cu9w/zfs_vs_btrfs/
								- Ubuntu 16.04 and Debian Linux ship both ZFS (OpenZFS) and BTRFS
								- btrfs is not ready for production. ZFS has been for nearly a decade.
								- ZFS is recommended to have 1GB RAM per TB if data deduplication is used
								  https://superuser.com/questions/993014/how-important-is-the-1gb-ram-per-1tb-disk-space-rule-for-zfs
				- ((65f86472-20de-46a6-af62-43cecb6b0a0f))-based
				  collapsed:: true
					- ((65f86472-20de-46a6-af62-43cecb6b0a0f))-based versioning
						- rsync snapshot scripts
						  collapsed:: true
							- https://netfuture.ch/2013/08/simple-versioned-timemachine-like-backup-using-rsync/
							- https://www.google.co.uk/search?q=rsync+versioning&ie=utf-8&oe=utf-8&client=firefox-b&gfe_rd=cr&ei=xH6-WPufA4338Aezzae4DQ
							- https://www.howtoforge.com/backing-up-with-rsync-and-managing-previous-versions-history
							- https://ubuntuforums.org/showthread.php?t=2135788
							- Still, for most people considering git for backup, the closest, correct, choice is rdiff-backup which is available, and maybe even installed by default, in most distributions of Linux. It stores the most recent version as is (you can do a plain cp to restore), and older versions as "reverse deltas" using the rsync algorithm. So, what rsync does only for network bandwidth, rdiff-backup extends to disk space as well! This is still not as efficient as git (because the topmost revision is not compressed), but good enough for most people. It also has a handy "remove-older-than" option to prune old backups, which can make this whole thing pretty much fire and forget using a script+cron.
							- It is often possible to store several hours, days, and even weeks' worth of snapshots with slightly more than 2x storage. This method, while not as space-efficient as some of the proprietary technologies (which, using special copy-on-write filesystems, can operate on slightly more than 1x storage), makes use of only standard file utilities and the common rsync program, which is installed by default on most Linux distributions.
							  http://www.mikerubel.org/computers/rsync_snapshots/
							- "rsync snapshots" - sometimes known as "hard link snapshots". The originator of this method was Mike Rubel[2]. What you are doing here is making a hard links only copy of yesterdays backup (which means it takes up no space, since it's just hard links) and then doing your "dumb rsync". Any files that changed will break the hard links and your snapshot from yesterday will take up as much space on disk as (the total size of all files that changed since yesterday). It's very simple, very elegant, and requires no software support or requirements on the remote end - as long as you can ssh to the server and run rsync/cp/rm it will work.
						- Rsnapshot
						  collapsed:: true
							- It can create incremental backups using rsync, cp, and hardlinks (I'm sure there are a few other tools).
							- http://www.rsnapshot.org/
							- https://wiki.archlinux.org/index.php/Rsnapshot
							- https://github.com/rsnapshot/rsnapshot
							- http://www.pontikis.net/blog/howto-rsnapshot-backup
							- https://www.howtoforge.com/set-up-rsnapshot-archiving-of-snapshots-and-backup-of-mysql-databases-on-debian
							- https://linux.die.net/man/1/rsnapshot
							- http://www.tecmint.com/rsnapshot-a-file-system-backup-utility-for-linux/
							- http://rsnapshot.org/faq.html
							- https://wiki.centos.org/HowTos/RsnapshotBackups
							- [http://www.thegeekstuff.com/2009/08/tutorial-backup-linux-using-rsnapshot-rsync-utility](http://www.thegeekstuff.com/2009/08/tutorial-backup-linux-using-rsnapshot-rsync-utility)
					- rsync a directory
						- sudo rsync -r --info=progress2 /media/kubuntu/xxxx/home/ home 1/
						- `-a`
						- sudo cp "/media/gamedisk/1SanDiskWin10 Steam Linux" "/media/boss/SanDisk-54_Ext4/Games/1SanDiskWin10 Steam Linux"
						- `rsync --progress -r /media/gamedisk/1SanDiskWin10-Steam-Linux /media/boss/SanDisk-54_Ext4/Games/1SanDiskWin10-Steam-Linux`
						-
						- sudo rsync -r --info=progress2 /media/boss/7c40b7b1-bab1-458f-8074-76eb4e4a3d5a/boss/Documents/MUSEUM/Docker/TinyTinyRSS/db /home/boss/Desktop/db
				- syncthing => Backup Server with BTRFS/ZFS snapshots
				- Duplicati
				- _Comparisons_
				  collapsed:: true
					- rsnapshot vs zfs
						- https://serverfault.com/questions/725336/rsnapshot-vs-zfs-btrfs-snapshots
					- rsnapshot vs borg
						- https://news.ycombinator.com/item?id=11817701
					- borg vs duplicati
						- Duplicati 2 attempted to move to a hash-based system but they chose to use fixed block offsets rather than checksum-based offsets, so the incremental detection is inefficient after an insert point.
				- automatic snapshots on ZFS https://github.com/zfsnap/zfsnap/wiki/zfSnap a config like hourly snapshots for 24 hours, daily for a month would be ideal
				- 1 Backlink
				  collapsed:: true
					- Chunking means that it allows [Differential/delta backups](https://workflowy.com/#/80a211459f04) even with cloud storage that doesn't support it natively
			- Interactive, file-level ZFS Time Machine-like tool
			  [https://github.com/kimono-koans/httm](https://github.com/kimono-koans/httm)
		- Unsuitable
		  collapsed:: true
			- Git as backup?
			  collapsed:: true
				- http://thehelpfulhacker.net/2010/02/15/using-git-as-a-poor-mans-time-machine/
				- https://www.google.co.uk/search?q=Git-based+GUI+software+intended+for+backups&ie=utf-8&oe=utf-8&client=firefox-b&gfe_rd=cr&ei=SyW_WIDTGe7R8geL8LHoCg
				- https://serverfault.com/questions/341199/git-as-a-backup-tool
			- Duplicity for encrypted backups
			  collapsed:: true
				- https://www.digitalocean.com/community/articles/how-to-use-duplicity-with-gpg-to-securely-automate-backups-on-ubuntu
		- Assorted
		  collapsed:: true
			- Virtual machines
				- Hypervisor snapshots as usual
			- https://www.r1soft.com/server-backup-manager
			- http://alternativeto.net/software/crashplan/
			- https://www.google.bg/search?q=centos+crashplan&ie=utf-8&oe=utf-8&client=firefox-b&gfe_rd=cr&ei=QQu_WP_qJoau8we_uqOYAg
			- https://en.wikipedia.org/wiki/Comparison_of_file_synchronization_software#Commercial
		- _FOSS_
		  collapsed:: true
			- Duplicati
			- Decentralised cloud storage
			  #Technology https://workflowy.com/#/00518a8e6a35
			- Bacula when more clients
			  #Software https://workflowy.com/#/4cda036210d6
			- Distributed filesystems e.g. Ceph
			  intralink2:: https://workflowy.com/#/8281ea60abe9
		- _Proprietary_
		  collapsed:: true
			- CrashPlan on CentOS?
				- https://lonesysadmin.net/2015/01/25/install-crashplan-linux/
				- https://support.code42.com/CrashPlan/4/Configuring/Using_CrashPlan_On_A_Headless_Computer
			- backup buddy encryption - client-side encryption
				- http://www.backupvault.co.uk
		- Cold Storage
		  collapsed:: true
			- I'm sure he already has a cluster for redundancy, from there you can have one of the servers do incremental backups to a different server.
			- For offline copies it depends on whether you have a person who can run a home server for you and physically swap out hard drives or if you have to rely on one of the major service providers and their cold storage options.
		- \_Related: \_File Sync & Backup software
		  #Software https://workflowy.com/#/bf8aafdbcfc3
	- Accounting
	  collapsed:: true
		- Budgeting
		  #Budget https://workflowy.com/#/9ae6d3cca9b6
		- Receipt Management
		  See Document Management https://workflowy.com/#/430149ff582b
		- Invoicing
			- InvoicePlane
			  https://alternativeto.net/software/invoiceplane/reviews
			- FOSS
				- [Invoice Dragon](https://invoicedragon.com/)
				  collapsed:: true
					- [GitHub - LaniJ/invoice-dragon: Open source application for creating free invoices and receipts](https://github.com/LaniJ/invoice-dragon)
					- [Show HN: Invoice Dragon – An open source app to create PDF invoices | Hacker News](https://news.ycombinator.com/item?id=36860898)
					-
		- Accounting full
			- QuickBooks
			- Freshbooks
			- GnuCash
		- Datasheet
			- - Accounting: Freshbooks, Waveapps, Quickbooks, Zoho
			- Automate or outsource administrative tasks
			  collapsed:: true
				- I use accounting and invoicing software that links to my business bank account, so I don’t have to manually enter all my transactions. It automatically scans my bank account and imports transactions as they occur, so I don’t really have to do anything -- other than watch for double counting or accounting errors due to the software’s quirks.
				- On taxes -- I hire a CPA to do my taxes and keep track of my filing documents, so I don’t have to worry about it at all.
				- For anything else you feel is menial, outsource to a VA.
			- Getting paid
			  collapsed:: true
				- Very important to have a reliable payment system that allows you to accept credit and debit cards -- not PayPal!
				- I send invoices to my clients through my accounting software. It keeps track of what services I provide and at what pricing, maintains a list of customers, and automatically sends out reminders for overdue invoices at pre-set intervals. I don’t have to chase my clients down for their payments. My software does that.
				- My accounting software is integrated with Stripe through its API, so when my clients pay my invoices, the money gets debited straight into my business bank account. Easy peasy.
		- _Related: _
			- Legal - Accounting
			  #Law https://workflowy.com/#/c5d2e2452144
			- Payment Processors
			  #WordPressPlugins-Payment https://workflowy.com/#/ff89e3c9ccaf
	- Enterprise
	  collapsed:: true
	  Advanced
		- Intrusion Detection System
			- https://www.upguard.com/articles/top-free-network-based-intrusion-detection-systems-ids-for-the-enterprise
			- https://www.alienvault.com/blogs/security-essentials/open-source-intrusion-detection-tools-a-quick-overview
		- See enterprise suite
		- See Odoo ERP
		- Centralized logging system using ELK stack, Graylog2
		- Infrastructure as code e.g. Ansible, Puppet, CloudFormation
		  intralink2:: https://workflowy.com/#/c4583a059daf
		- Continuous Delivery System by Docker, Jenkins, Ansible, TeamCity -
		- Configure and manage: Docker, Mysql, Apache, Nginx, Memcached, ((6607f722-b674-4037-af49-e03bafebc259)), Vagrant, MongoDB, OpenVPN, Elasticsearch, Postfix, Zimbra
		- Monitoring system with New Relic, Zabbix, ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64))
		- HAProxy for load balancing
- Systems Administration
  id:: 6336ac7d-9081-4a23-b7e5-0474a8023b4d
  collapsed:: true
  #SysAdmin AKA SysAdmin
	- Current servers
	  id:: 663a578f-bad3-4b35-8666-694af7544616
	  collapsed:: true
		- Tiny Tiny RSS VPS (`13-Ubuntu-22.04-LTS-London`)
		  collapsed:: true
		  $7.20/month ($6 droplet, $1.20 backups, 20% VAT)
			- [https://13.synthfleshop.casa](https://12.synthfleshop.casa)
			- DigitalOcean `13-Ubuntu-22.04-LTS-London`
			- Documentation
				- Setup SOP
					- See [New Non-Root User with Root Privileges](https://workflowy.com/#/329da35168d6)
					- See [Basic ufw setup](https://workflowy.com/#/6d45326c359c)
					- See [Caddy](https://workflowy.com/#/6b12f4a3140d)
					- Nextcloud setup
					  collapsed:: true
						- docker-compose
						  [https://github.com/nextcloud/docker#running-this-image-with-docker-compose](https://github.com/nextcloud/docker#running-this-image-with-docker-compose)
							- Newest template
							  [https://github.com/nextcloud/docker/blob/master/.examples/docker-compose/insecure/mariadb/apache/docker-compose.yml](https://github.com/nextcloud/docker/blob/master/.examples/docker-compose/insecure/mariadb/apache/docker-compose.yml)
						- Update Caddyfile and add another section with different domain for Nextcloud
							- Template
							  13.synthfleshop.casa {  
							   reverse_proxy localhost:8096
							  }
							  13-nextcloud.synthflesh.casa {  
							   reverse_proxy localhost:8080
							  }
						- Create an A DNS record for the chosen Caddy URL
						  [https://cloud.digitalocean.com/networking/domains](https://cloud.digitalocean.com/networking/domains)
						- Related: [Nextcloud Tasks (CalDAV)](https://workflowy.com/#/27a329fcb1b4)
					- See [Tiny Tiny RSS](https://workflowy.com/#/13b177dd31d4)
		- ((baikal)) CalDAV Tasks (`15-Ubuntu-24.04-LTS-London`)
		  collapsed:: true
		  Created [[2025-10-04 Saturday]]
			- [[2025-10-07 Tuesday]] Created it because now Planify supports generic CalDAV servers instead of just Nextcloud
			- `docker-compose.ssl.yaml` - using nginx + traefik + Let's Encrypt
			  collapsed:: true
				- ```yaml
				  # Docker Compose file for a Baikal server with Let's Encrypt using Traefik (https://docs.traefik.io/)
				  #
				  # The acme.json file must exist before you run docker compose up.
				  #
				  # 1. Adjust host in line 17
				  # 2. Create acme.json: touch /etc/ssl/private/acme.json
				  # 3. Adjust file permissions: chmod 600 /etc/ssl/private/acme.json
				  # 4. Start the stack: docker compose -f docker compose.ssl.yaml up
				  
				  version: "2"
				  services:
				    baikal:
				      image: ckulka/baikal:nginx
				      restart: always
				      labels:
				        traefik.enable: true
				        traefik.http.routers.baikal.rule: Host(`15-baikal.synthfleshop.casa`)
				        traefik.http.routers.baikal.tls: true
				        # Traefik middleware required for iOS, see https://github.com/ckulka/baikal-docker/issues/37.
				        traefik.http.routers.baikal.middlewares: baikal-dav
				        traefik.http.middlewares.baikal-dav.redirectregex.regex: https://(.*)/.well-known/(card|cal)dav
				        traefik.http.middlewares.baikal-dav.redirectregex.replacement: https://$$1/dav.php/
				        traefik.http.middlewares.baikal-dav.redirectregex.permanent: true
				      volumes:
				        - config:/var/www/baikal/config
				        - data:/var/www/baikal/Specific
				  
				    # See https://doc.traefik.io/traefik/v2.10/
				    traefik:
				      image: traefik:2.10
				      restart: always
				      ports:
				        - 80:80
				        - 443:443
				      volumes:
				        - type: bind
				          source: /etc/ssl/private/acme.json
				          target: /acme.json
				        - type: bind
				          source: /var/run/docker.sock
				          target: /var/run/docker.sock
				      command:
				        # See https://doc.traefik.io/traefik/v2.10/observability/access-logs/
				        - --accesslog
				        # See https://doc.traefik.io/traefik/v2.10/routing/entrypoints/#redirection
				        - --entrypoints.web.address=:80
				        - --entrypoints.websecure.address=:443
				        - --entrypoints.web.http.redirections.entryPoint.to=websecure
				        - --entrypoints.web.http.redirections.entryPoint.scheme=https
				        # See https://doc.traefik.io/traefik/v2.10/https/acme/
				        - --certificatesresolvers.letsencrypt.acme.email=your-email@example.com
				        - --certificatesresolvers.letsencrypt.acme.storage=/acme.json
				        - --certificatesresolvers.letsencrypt.acme.caserver=https://acme-staging-v02.api.letsencrypt.org/directory
				        - --certificatesresolvers.letsencrypt.acme.tlschallenge
				  
				        # https://doc.traefik.io/traefik/v2.10/providers/docker/
				        - --providers.docker
				        - --providers.docker.exposedByDefault=false
				  
				  volumes:
				    config:
				    data:
				  ```
			- {Archive}
				- Tried ((6463499c-eb78-40d8-9a9e-ca7a9f0ad0be)) briefly but the unofficial `ckulka/baikal-docker` image didn't seem to work well with it
		- {Archive}
		  collapsed:: true
			- Jellyfin + Syncthing VPS (11-Ubuntu-22.04-LTS-Frankfurt)
			  collapsed:: true
			  $16/month ($12 droplet, $2.40 backups, 20% VAT)
				- Deprecating to a snapshot because we've used this server for maybe a few hours over the past 3 months. Mostly using streaming sites instead with Metastream as it's more reliable than Jellyfin syncplay
				- [https://11.synthfleshop.casa](https://6.synthfleshop.casa)
				- DigitalOcean `11-Ubuntu-22.04-LTS-Frankfurt`
				- Documentation
					- Setup SOP
						- See [New Non-Root User with Root Privileges](https://workflowy.com/#/329da35168d6)
						- See [Basic ufw setup](https://workflowy.com/#/6d45326c359c)
						- See [Caddy](https://workflowy.com/#/6b12f4a3140d)
						- See [Jellyfin](https://workflowy.com/#/d028601d1865) - <a href="https://workflowy.com/#/93869d0c08ea">v5 - May 2022</a>
						- See [Syncthing](https://workflowy.com/#/26351aa44633)
					- File export
						- `~/syncthing/docker-compose.yml`
						  collapsed:: true
							- ```
							  ---
							  version: "3"
							  services:
							    syncthing:
							      image: syncthing/syncthing
							      container_name: syncthing
							      hostname: Syncthing-11-Ubuntu-22.04-LTS-Frankfurt
							      environment:
							        - PUID=1000
							        - PGID=1000
							      volumes:
							        - ./syncthing-VPS-11:/var/syncthing
							      ports:
							        - 8384:8384
							        - 22000:22000/tcp
							        - 22000:22000/udp
							      restart: unless-stopped
							  ```
						- `~/jellyfin/docker-compose.yml`
						  collapsed:: true
							- ```
							  services:
							    jellyfin:
							      image: jellyfin/jellyfin:latest
							      container_name: jellyfin
							      # user: uid:gid
							  #    network_mode: "host"
							      volumes:
							        - ./config:/config
							        - ./cache:/cache
							        - ./media:/media
							        - ./media2:/media2:ro
							      restart: "unless-stopped"
							      ports:
							        - 8096:8096
							        - 8920:8920 #optional
							      # Optional - alternative address used for autodiscovery
							      environment:
							       - JELLYFIN_PublishedServerUrl=https://11-jellyfin.synthfleshop.casa
							  ```
						- `~/caddy/docker-compose.yml`
						  collapsed:: true
							- ```
							  
							  version: "3.7"
							  
							  networks:
							          web:
							                  external: true
							          internal:
							                  external: false
							                  driver: bridge
							  
							  services:
							    caddy:
							      image: caddy:latest
							      restart: unless-stopped
							      ports:
							        - "80:80"
							        - "443:443"
							        - "9096:8096"
							        - "9920:8920"
							        - "9384:8384"
							      volumes:
							        - ./Caddyfile:/etc/caddy/Caddyfile
							        - ./site:/srv
							        - ./caddy_data:/data
							        - ./caddy_config:/config
							      networks:
							        - web
							        - internal
							  
							  volumes:
							    caddy_data:
							    caddy_config:
							  ```
						- `~/caddy/Caddyfile`
						  collapsed:: true
							- ```
							  11.synthfleshop.casa {
							          reverse_proxy jellyfin:8096
							  }
							  11-jellyfin.synthfleshop.casa {
							          reverse_proxy jellyfin:8920
							  }
							  11-syncthing.synthfleshop.casa {
							          reverse_proxy syncthing:8384
							  }
							  ```
				- 1 Backlink
					- Deprecated Tue, May 24, 2022 in favour of [Jellyfin VPS (11-Ubuntu-22.04-LTS-Frankfurt)](https://workflowy.com/#/ae5d9ca5f882), because old server was based on `docker run` whereas new server uses docker-compose. Newer server is easily to update and less fragile incase of issues
			- Nextcloud Tasks VPS (8-Ubuntu-20.04-LTS-London)
			  collapsed:: true
			  $7.20/month ($6 droplet, $1.20 backups)
				- [https://8.synthfleshop.cas](https://8.synthfleshop.cas)a
				- Used this guide to quickly setup because Caddy/docker-compose version didn't work (though I didn't troubleshoot it much)
				  [https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-nextcloud-on-ubuntu-20-04](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-nextcloud-on-ubuntu-20-04)
				- See [Nextcloud Tasks (CalDAV)](https://workflowy.com/#/27a329fcb1b4)
				  #Software
			- Jellyfin VPS (10-Ubuntu-20.04-LTS-Frankfurt)
			  collapsed:: true
			  $26/month ($21.60 droplet, $4.32 backups)
				- Deprecated Tue, May 24, 2022 in favour of [Jellyfin VPS (11-Ubuntu-22.04-LTS-Frankfurt)](https://workflowy.com/#/ae5d9ca5f882), because old server was based on `docker run` whereas new server uses docker-compose. Newer server is easily to update and less fragile incase of issues
				- [https://6.synthfleshop.casa](https://6.synthfleshop.casa)
				- DigitalOcean `10-Ubuntu-20.04-LTS-Frankfurt`
					- Built from `6-Ubuntu-20.04-LTS-Frankfurt`, a smaller VPS
				- Documentation
					- See [Syncthing](https://workflowy.com/#/26351aa44633)
						- mv /var/syncthing/Sync/\* /media/Other/
					- See [Jellyfin](https://workflowy.com/#/d028601d1865)
					- See [wg-easy](https://workflowy.com/#/f7cbbe256ec0)
					  #Privacy-VPN
					- Transmission (torrenting)
						- [https://docs.linuxserver.io/images/docker-transmission](https://docs.linuxserver.io/images/docker-transmission#application-setup)
						- [https://github.com/linuxserver/docker-transmission](https://github.com/linuxserver/docker-transmission)
			- WordPress VPS (7-Ubuntu-20.04-LTS-London)
			  collapsed:: true
				- Documentation
					- See [Caddy](https://workflowy.com/#/6b12f4a3140d)
					  #VirtualHosts
						- nano ~/Caddy/docker-compose.yml
					-
				- _Related:_ [FOSS cPanel alternative](https://workflowy.com/#/32d24740653a)
		- Related:
			- See [$12 DigitalOcean droplets](https://workflowy.com/#/84e06c84e3cd)
			  #Budget
	- [[Terminal]] (AKA Basic Knowledge)
	- Hardware Virtualisation
	  collapsed:: true
	  AKA Platform Virtualisation, or self-hosted DigitalOcean
		- [https://en.wikipedia.org/wiki/Hardware_virtualization](https://en.wikipedia.org/wiki/Hardware_virtualization)
		- Pros
		  collapsed:: true
			- Since dedicated servers are a bit different from VPS the security and the privacy you get is much better than with VPS. Thanks to this, if they would like to snoop on you they would need to physically get to the server and read the disks. Whereas with a VPS providers can read it without you noticing it, at any time. They are able to just perform a live snapshot of the system and pass it to the authorities.
			- A VPS (virtual private server) gives you the ability to host several instances of your operating system within a single dedicated server. Each virtual machine or container within your server behaves independently as though it were a server by itself. This gives users all of the benefits and administrative access of a full dedicated server without the high cost of maintaining actual server hardware.
		- Buy a Dedicated Server
		  collapsed:: true
		  $60/month?
			- SoftLayer
			- OVH in europe
		- _OS-based_
		  collapsed:: true
			- _See_ [Qubes](https://workflowy.com/#/e3b3f652ed7d)<a href="[A simpler way to organize your work - Workflowy](https://workflowy.com/#/e3b3f652ed7d">) </a><a href="[A simpler way to organize your work - Workflowy](https://workflowy.com/#/e3b3f652ed7d">OS</a>)
			  #PC-Linux
			- Windows Sandbox
				- is simple to use, but it breaks other virtualisation software like HyperV
			- VirtualBox
			  collapsed:: true
				- Adjust size https://www.howtogeek.com/124622/how-to-enlarge-a-virtual-machines-disk-in-virtualbox-or-vmware/
			- VMware
			  collapsed:: true
				- Shared folder between host and guest
					- On guest: sudo apt install open-vm-tools open-vm-desktop
					- Can confirm it's running after VM restart via either:
						- systemctl status vmtoolsd
						- `vmware-toolbox-cmd -v`
						- dkpg -l | grep "open-vm-tools"
						- ps ax|grep vmware
					- Requires Windows to have file sharing enabled (if host)
					- In VMware VM settings > Options > enable Shared Folders
				- WinSCP as an alternative way to share between host and guest
					- `ip a` on guest to get the IP address (`wlp1s0`)
					  id:: 67a8e129-036f-4b07-b056-5a43eb189da3
						- ```
						  2: wlp1s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
						      link/ether a8:3b:76:72:e6:63 brd ff:ff:ff:ff:ff:ff
						      inet 192.168.1.129/24 brd 192.168.1.255 scope global dynamic noprefixroute wlp1s0
						         valid_lft 83744sec preferred_lft 83744sec
						      inet6 fe80::5ad7:4790:94b6:8a6/64 scope link noprefixroute 
						         valid_lft forever preferred_lft forever
						  ```
							- `192.168.1.129` is the IP address of the current device
							- Can set an IP address in the router web UI based on device MAC address
					- Need to ensure `openssh-server` is installed on the guest if Ubuntu Desktop, or it comes preinstalled on Ubuntu Server
				- Increasing size of disk (within VM only?) can be done on live disk
					- `df -h` to see the disk size
					- `sudo apt install -y gparted`
					- unmount the ext4 partition. It'll say it failed but it'll be unmounted
					- Right-click the partition -> resize -> drag the slider to take up the entire space
					- Apply (green tick)
				-
		- Bare metal-based
		  collapsed:: true
		  eg Open Source VPS Options
			- VirtKick
			  Killed https://www.lowendtalk.com/discussion/101802/virtkick-acquired-by-onapp/p4
				- Open source self-hosted Digital Ocean
				- https://demo.virtkick.com
				- What is the technology behind VirtKick?
					- The very first thing that you see is the UI. The UI is built with Rails and AngularJS, some parts are generated on the backend and some parts with more interaction are AngularJS.
					- Our temporary backend that we are using is WebVirtMgr. WebVirtMgr is another open source application that lets users control their virtualization with libvirt. We wrapped it into VirtKick, added JSON API on top of it, and use it as a JSON API to libvirt, where libvirt is another abstraction to KVM that we are using for virtualization. However, KVM is our first step, the next step will be OpenVZ, and the next step will be Docker.
				- I know that Digital Ocean currently supports nested virtualization so its possible to create VirtKick in Digital Ocean and start a virtual machine. The install on Digital Ocean button is a very cool initiative. Someone thought they could use these new features, metadata API feature from Digital Ocean and implement something like this.
				- https://web.archive.org/web/20160429133811/https://www.indiegogo.com/projects/virtkick-take-cloud-back#/
			- OpenStack
				- https://www.openstack.org/software/
				- a great project however I believe it is great for big infrastructures, big corporate infrastructures where people expect more that to just have a VM. They expect to have some complicated networking infrastructure, failover redundancy, and things like that. These are things the neither Digital Ocean or Linode provide and they are fine with this. So there are many more people that just want the VM rather than people who want sophisticated configuration.
				  From VirtKick CEO
			- 1. OpenVZ
			     Container based
				- A great alternative to Parallels Virtuozzo Containers, OpenVZ uses a container system to give your users root access to their own virtual private servers. In fact, Parallels Virtuozzo is based on OpenVZ, meaning the company has a financial interest in ensuring it continues to function well.
			- 2. Linux VServer
				- With Linux VServer, you can run multiple “units” of your OS using kernel level isolation. They all still use the same kernel but are separate server instances from each other. In the project’s own words, it does this by using “”security contexts”, segmented routing, chroot, extended quotas and some other standard tools”.
			- 3. Xen hypervisor
				- Although Xen is not exclusively designed for VPS management like the other two, many system administrators use it to create virtual private servers. Xen supports a wide range of operating systems and was developed by several large organizations, including Cisco, AMD, Intel, IBM, Citrix, and Red Hat.
			- KVM
			  True virtualization
			- [https://en.wikipedia.org/wiki/Comparison_of_platform_virtualization_software](https://en.wikipedia.org/wiki/Comparison_of_platform_virtualization_software)
		- Troubleshooting
			- VM network access troubleshooting
			  collapsed:: true
				- `sudo nano /etc/resolv.conf` and add the newline `nameserver 172.30.2.1 search repodomain.com`. This will manually pin the IP address to access the domain?
			-
		- _Related:_ [SR-IOV tech allows virtualizing a GPU into multiple sandboxed GPUs](https://workflowy.com/#/c910598c3566)
		  #Multimedia-Videogames
	- How to Setup a Server
	  collapsed:: true
	  Some web control panels deploy services easily How to Host a Website
		- Buy a VPS
		  collapsed:: true
			- $5/mo 20gb SSD servers
			  collapsed:: true
				- https://www.digitalocean.com/pricing/
				- https://indovirtue.com/budget-singapore-openvz-ssd-vps
				- https://www.atlantic.net/cloud-hosting/pricing/
			- Other good deals
			  collapsed:: true
				- http://www.webhostingtalk.com/forumdisplay.php?f=104
				- http://lowendbox.com/ directory. Remember more expensive = longer-lasting company, thus need backups frequently if cheap company
			- Cheap Storage VPS
			  collapsed:: true
				- e.g. https://hosthatch.com/storage-vps $5/mo for 250gb with root access
		- SSH
		  id:: 64634999-0677-495a-a974-39c697065b37
		  collapsed:: true
			- Generating SSH Keys locally
			  collapsed:: true
				- https://confluence.atlassian.com/display/STASH/Creating+SSH+keys
				- Linux - terminal
					- `ssh-keygen`
					  Generate standard RSA key
						- Save it in e.g. `/home/boss/.ssh/new_key`
					- `ssh-keygen -t ed25519 -C "boss-XPS-9380"`
					  Generate stronger ed25519-based key. Also comments whatever is put in quotes
					- RSA vs ED25519
					  collapsed:: true
						- For RSA
							- Wider compatibility, but not always relevant especially if using modern servers
						- For ED25519
							- Faster to generate
							- On average more secure unless compared against a 4096 bit RSA key
						- Unclear
							- Key Size: RSA keys can vary in size (e.g., 2048, 3072, 4096 bits). Larger keys are more secure but also slower.
							  Security Level: A 2048-bit RSA key is generally considered secure, but for higher security, a 3072-bit or 4096-bit key is recommended.
							- Key Size: Ed25519 keys are always 256 bits.
							  Security Level: Ed25519 provides a high level of security equivalent to a 3000-bit RSA key.
					- `cat ~/.ssh/id_rsa.pub`
					  copy public ssh key
					- `chmod 0400 id_rsa.pem`
					  Change permissions so that only the owner or user of the file can read it
				- Windows - use git bash. or puttygen
				- Add a password or not?
				  collapsed:: true
					- Pros/Cons
						- Pros
							- Extra security
						- Cons
							- Doesn't play well with all apps and automation e.g. Vorta
							- It's kind of 3rd factor auth - an adversary would need access to local PC for my SSH private key, at which point getting password from manager shouldn't be too hard
			- Uploading SSH Public Key + Restarting SSH
			  collapsed:: true
				- _Upload_
					- Either
						- `ssh-copy-id -i ~/.ssh/boss-XPS-9380.pub remote_username@server_ip_address`
						- `scp -i <private-key-for-SSH-login> <local-pubkey-path> <remote_username@server_ip_address>:.ssh/authorized_keys`
							- Example
								- `scp -i ~/.ssh/boss-XPS-9380 ~/.ssh/boss-XPS-9380.pub zh1583@zh1583.rsync.net:.ssh/authorized_keys`
					- Alternatively
						- Linux - use openssh-client `ssh-copy-id user@hostname.example.com` to copy key over
						- [http://askubuntu.com/questions/4830/easiest-way-to-copy-ssh-keys-to-another-machine](http://askubuntu.com/questions/4830/easiest-way-to-copy-ssh-keys-to-another-machine)
				- If you want to copy SSH pubkey to another user:
					- ((64634999-7383-4f93-9c1a-93b000e4d0af))
					- `cp /root/.ssh/authorized_keys /home/kid/.ssh/authorized_keys`
					  ((64634a45-1e34-45ac-8f35-91077749abe2))
				- Checking it's been uploaded
					- `ssh username@host cat .ssh/authorized_keys`
						- Example
							- `ssh zh1583@zh1583.rsync.net cat .ssh/authorized_keys`
				- _Restart SSH server_
				  id:: 64634999-f95d-4227-b210-86096ce6b8a4
					- Either
						- `sudo systemctl restart ssh`
						- `sudo service ssh restart`
						- `sudo /etc/init.d/ssh restart`
			- Accessing Server via SSH
			  id:: 64634999-40de-4875-a40c-5eb1ada1d30c
			  collapsed:: true
				- 2021 - Linux
					- _Command line_
						- Template
							- `ssh username@ipaddress`
						- Example
							- `ssh root@139.59.163.122`
							- ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba))
							  `ssh ec2-user@52.56.35.20 -i ~/Downloads/key1.pem`
						- _This may be required if password-based access is still enabled:_
							- `ssh username@ipaddress -p portnumber -i /path/to/ssh/private/key`
							- `ssh root@139.59.163.122 -p 22 -i ~/.ssh/boss-XPS-9380`
						- Use password saved in password manager for the private key (if using a password for SSH key)
					- Konsole - SSH bookmark/connection manager plugin
					  [https://pointieststick.files.wordpress.com/2021/06/screenshot_20210625_204943.png?w=768](https://pointieststick.files.wordpress.com/2021/06/screenshot_20210625_204943.png?w=768)
				- 2019 - Windows
				  collapsed:: true
					- OpenSSH:
						- ssh root@SERVER_IP_ADDRESS
					- PuTTY/KiTTY:
						- Create a putty-version of private key with puttygen http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html (find it in .ssh folder or search puttygen)
						- Enter server IP address, port 22 (SSH)
						- Connection > Data > username: root
						- SSH > Auth > Private key file > select private SSH key (in .ssh folder)
						- Main menu > enter name for session > save
			- Misc
				- If unsure if SSH key is formatted correctly, can encode it to base64 then decode it again
					- ```bash
					  cat $PWD/ssh_key | base65 > $PWD/encoded_ssh_key
					  cat $PWD/encoded_ssh_key | base64 -d $PWD/decoded_ssh_key
					  ```
			- Connecting to ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) on corporate networks
			  id:: 665f0a8a-cf17-4aab-9831-fb4b70f5c454
			  collapsed:: true
				- When creating the EC2 sinstance ensure that:
					- Network settings > Subnet > set it to a private subnet
					- Advanced details > IAM instance profile > e.g. `BAE-Default-EC2-Role`
				- [Install the Session Manager plugin](https://docs.aws.amazon.com/systems-manager/latest/userguide/install-plugin-linux.html) for the ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad))
					- `sudo dnf install -y https://s3.amazonaws.com/session-manager-downloads/plugin/latest/linux_64bit/session-manager-plugin.rpm`
					- `session-manager-plugin`
					  Verify it's installed
				- Start a session in one terminal
					- `aws ssm start-session --target <your-instance-ID> --region -eu-west-2 --document-name AWS-StartPortForwardingSession --parameters "localPortNumber=55678,portNumber=22" --profile sandbox`
						- `--profile sandbox` assumes that `[sandbox]` section in `~/.aws/credentials` contains the correct access token and key. If it's under `[default]` then leave out this entire flag
				- Open a second terminal and SSH into instance
					- `ssh -i <your-pem-file>.pem ec2-user@localhost -p 55678`
				- ## Troubleshooting
					- UnauthorizedRequest error
						- `rm ~/.aws/credentials`
						  Delete the existing ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad)) credentials file
						- `aws configure` to create a new credentials file
					- TargetNotConnected error
						- Make sure your instance subnet is using a private subnet
						-
			- Dropbear - SSH alternative
				- Setup Dropbear as a backup to OpenSSH, listening on a different port. Useful when using a script that turns off SSH and you want to retain a permanent SSH connection (e.g. via Remote SSH VSCode)
				  collapsed:: true
					- `sudo apt install dropbear`
					- `sudo nano /etc/default/dropbear`
						- `NO_START=0` so it starts on boot
						- `PORT=1039` for example. Think it has to be above 1024
					- `sudo service dropbear start`
					- `sudo systemctl status dropbear`
					- Then with VSCode can use the blue remote SSH connect in the bottom left
					- `~/.ssh/config` can be modified from the prompts
					  ```
					  Host something-dropbear
					  Hostname 192.168.19.128
					  User username1
					  Port 1039
					  IdentityFile /path/to/id_ed25519_priv_key
					  ```
						- Obtain hostname via `ip a` from within the VM/container
			- [Learning Resources]
				- [https://www.digitalocean.com/community/tutorials/how-to-use-ssh-to-connect-to-a-remote-server](https://www.digitalocean.com/community/tutorials/how-to-use-ssh-to-connect-to-a-remote-server)
				- [https://www.digitalocean.com/community/tutorials/how-to-set-up-multi-factor-authentication-for-ssh-on-ubuntu-20-04](https://www.digitalocean.com/community/tutorials/how-to-set-up-multi-factor-authentication-for-ssh-on-ubuntu-20-04)
		- Accessing server by other means
		  collapsed:: true
			- See [WireGuard](https://workflowy.com/#/7422274de418)
			  #Privacy-VPN
			- FIDO2
				- [https://www.stavros.io/posts/u2f-fido2-with-ssh/](https://www.stavros.io/posts/u2f-fido2-with-ssh/)
		- Basic Security
		  collapsed:: true
			- Passwords
			  id:: 663a578f-8d32-4dbd-83e8-b8d53f276f4c
			  collapsed:: true
				- `passwd`
				  Change current user's password. Requires knowing the current passwordpass
				- `passwd USERNAMEHERE`
				  Change another user's password. Requires being logged in as `root`
				- `sudo passwd USERNAMEHERE`
				  Change another user's password
					- `sudo passwd ec2-user`
					  id:: 665f1731-0138-41bc-9371-143617f03d3d
				- `passwd -S USERNAMEHERE`
				  To see password status of any user account
					- The status information consists of 7 fields as follows:
						- vivek : Account login name (username)
						- P : This field indicates if the user account has a locked password (L), has no password (NP), or has a usable password (P)
						- 05/05/2012 : Date of the last password change.
						- 0 : Password expiry minimum age
						- 99999 : Password expiry maximum age.
						- 7 : Password expiry warning period.
						- -1 : Inactivity period for the password
				- Workflow for changing password whilst logged in as the sudo user
					- ((665f1731-0138-41bc-9371-143617f03d3d))
			- New Non-Root User with Root Privileges
			  id:: 64634999-8fb6-4449-a9b3-4075608c6dff
			  collapsed:: true
				- Use DigitalOcean dashboard in Droplet > Access > Reset Root Password (since no root password enabled initially, only SSH)
				- ((64634999-40de-4875-a40c-5eb1ada1d30c))
				- [Create a new user with root capability](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-20-04)
					- `adduser <new-username>`
						- Example: `adduser kid`
					- Give `<new-username>` sudo capability
						- `usermod -aG sudo <new-username>`
							- Example: `usermod -aG sudo kid`
					- Then can swap to the new user eg `su <new-username>`
					  `su kid`
				- [Enabling External Access for Your Regular User](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-20-04)
				  id:: 64634999-7383-4f93-9c1a-93b000e4d0af
					- Note: must be done whilst logged in as `root`
					- `rsync --archive --chown=USER:USER ~/.ssh /home/USER`
						- Example
							- `rsync --archive --chown=kid:kid ~/.ssh /home/kid`
				- No remote root login
				  id:: 64634999-fa89-46a6-8316-c7024c009463
					- To lock down which users are allowed to access your server via ssh,
						- edit the file `/etc/ssh/sshd_config`
						  id:: 64949f65-7ff2-46d9-9d3c-1208fdcdf3fd
						  `sudo nano /etc/ssh/sshd_config`
							- Note: the `PermitRootLogin yes` line in "sshd_config" refers to being able to `sudo su root` i.e. local root login
							- At the bottom of the file, add the following:
								- ```
								  AllowUsers user1 user2 user3
								  ```
									- Example
										- ```
										  AllowUsers kid
										  ```
								- Substitute in your username for `user1` and any additional users you need to grant remote access for `user2` and `user3` and so on, separated by spaces.
					- Followed by ((64634999-f95d-4227-b210-86096ce6b8a4))
						- {{embed ((64634999-f95d-4227-b210-86096ce6b8a4))}}
				- Optional
					- Enabling password-based SSH authentication (e.g. to allow freelancers VPS access)
						- ((64949f65-7ff2-46d9-9d3c-1208fdcdf3fd))
						- ```
						  PasswordAuthentication yes
						  ```
							- otherwise for a secure server it should be
							  ```
							  PasswordAuthentication no
							  ```
						- If using DigitalOcean also edit `/etc/ssh/sshd_config.d/*.conf` and remove that line from there
				- ((64634999-f95d-4227-b210-86096ce6b8a4))
					- {{embed ((64634999-f95d-4227-b210-86096ce6b8a4))}}
				- {Archive}
				  collapsed:: true
					- Adding SSH Key to New User:
						- mkdir .ssh (new directory .ssh)
						- chmod 700 .ssh (restrict permissions)
						- nano .ssh/authorized_keys
						- Paste in my .pub key
						- CTRL+X (edit) > Y (save) > ENTER (confirm name)
						- chmod 600 .ssh/authorized_keys (restrict permissions)
						- exit (return to root user)
			- ((64634998-13c7-437b-803c-0fec50787fff))
			- Firewall
			  collapsed:: true
				- `ufw` - Uncomplicated Firewall
				  collapsed:: true
					- [source] [https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-20-04](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-20-04)
					  collapsed:: true
						-
					- _Glossary_
					  collapsed:: true
						- ufw man page
						  “ ufw is not intended to provide complete firewall functionality via its command interface, but instead provides an easy way to add or remove simple rules. It is currently mainly used for host-based firewalls. ”
						- https://help.ubuntu.com/14.04/serverguide/firewall.html
						- sudo ufw enable
						  Enable ufw
						- sudo ufw allow 22
						  Open port 22 (SSH)
						- sudo ufw deny 22
						  Close port 22 (SSH)
						- sudo ufw status numbered
						  View open ports
					- Basic ufw setup
					  collapsed:: true
						- Allow SSH connections, so that you can still log into the server when ufw is turned on
						  sudo ufw allow OpenSSH
						- Enable firewall
						  sudo ufw enable
						- Check status
						  sudo ufw status
						- Allow [443 SSL (HTTPS)](https://workflowy.com/#/50d58cf97486) connections
						  sudo ufw allow 443
						- (optional) Allow [80 HTTP](https://workflowy.com/#/b4dd04fc561a) connections
						  sudo ufw allow 22
						- 2 Backlinks
							- See [Basic ufw setup](https://workflowy.com/#/6d45326c359c)
							- See [Basic ufw setup](https://workflowy.com/#/6d45326c359c)
					- {Archive}
					  collapsed:: true
						- [https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands](https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands)
				- `sudo netstat -ntlp | grep LISTEN`
				  Check what ports are open
				- https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-using-iptables-on-ubuntu-14-04
				- http://www.cyberciti.biz/faq/what-process-has-open-linux-port/
				- common ports
				  collapsed:: true
					- 21 FTP
					- 22 SSH
					- 23 TELNET
					- 25 SMTP
					- 53 DNS
					- 80 HTTP
					  collapsed:: true
						- 1 Backlink
							- (optional) Allow [80 HTTP](https://workflowy.com/#/b4dd04fc561a) connections
							  sudo ufw allow 22
					- 110 POP3
					- 115 SFTP
					- 135 RPC
					- 139 NetBIOS
					- 143 IMAP
					- 194 IRC
					- 443 SSL (HTTPS)
					  collapsed:: true
						- 1 Backlink
							- Allow [443 SSL (HTTPS)](https://workflowy.com/#/50d58cf97486) connections
							  sudo ufw allow 443
					- 445 SMB
					- 1433 MSSQL
					- 3306 MySQL
					- 3389 Remote Desktop
					- 5632 PCAnywhere
					- 5900 VNC
				- Simple port scanner
				  http://www.yougetsignal.com/tools/open-ports/
				- Opening ports for website
				  intralink2:: https://workflowy.com/#/998690f44388
			- fail2ban
			  collapsed:: true
				- https://www.digitalocean.com/community/tutorials/how-to-install-and-use-fail2ban-on-ubuntu-14-04
			- Reverse proxy or similar
			  collapsed:: true
				- See Wireguard (other Logseq)
				- ((6463499c-e15b-4225-9e1e-0e31863d1196))
					- More notes
					  [https://workflowy.com/#/ae35658f2a03?q=nginx](https://workflowy.com/#/ae35658f2a03?q=nginx)
			- [Learning Resources]
			  collapsed:: true
				- https://www.digitalocean.com/community/tutorials/additional-recommended-steps-for-new-ubuntu-14-04-servers
				- http://arstechnica.com/gadgets/2012/11/how-to-set-up-a-safe-and-secure-web-server/1
				- http://blog.al4.co.nz/2011/05/setting-up-a-secure-ubuntu-lamp-server/
				- https://www.digitalocean.com/community/tutorials/how-to-install-and-use-fail2ban-on-ubuntu-14-04
					- https://startpage.com/do/m/mobilesearch?language=english&query=how+to+secure+server+vs+hackers
		- Install software with `apt`
		  collapsed:: true
			- Pros
				- Easy to install packages
				- You dont need to worry about package dependency and configuration
			- Commands
				- sudo apt update
				  To update and see what is newest versions of packages available
				- sudo apt upgrade
				  upgrade all software
				- sudo apt dist-upgrade
				  intelligent upgrade of all packages
				- sudo apt install <package>
				  To install a particular package by it's name <package> eg unzip
		- Setup Virtual Network Computing (VNC)
		  collapsed:: true
			- Notes
			  collapsed:: true
				- https://www.youtube.com/watch?v=gFdBSyy4xcM
				- sudo apt-get install xrdp
				- sudo apt-add-repository ppa:ubuntu-mate-dev/ppa
				- sudo apt-add-repository ppa:ubuntu-mate-dev/trusty-mate
				- sudo apt-get update
				- sudo apt-get upgrade
				- sudo apt-get install ubuntu-mate-core ubuntu-mate-desktop
				- echo mate-session >~/.xsession
				- sudo service xrdp restart
				- https://www.digitalocean.com/community/tutorials/how-to-setup-vnc-for-ubuntu-12
			- #1
			  collapsed:: true
				- sudo apt-get -y install ubuntu-desktop tightvncserver xfce4 xfce4-goodies (install VNC server and XFCE 4 desktop) 478mb
				- adduser vnc
				- passwd vnc
			- Get root as user vnc:
			  collapsed:: true
				- sudo - su root
				- echo "vnc ALL=(ALL) ALL" >> /etc/sudoers
			- Step 4:
			  collapsed:: true
				- tightvncserver (wasn't in steps but I found it and set pw here - not sure if necessary)
				- nano /etc/init.d/vncserver
					- `mkdir /home/vnc/.vnc/`
				- nano /home/vnc/.vnc/xstartup (ignore the 'edit' in tutorial)
			- Install VNC Client which allows SSH Tunnel:
			  collapsed:: true
				- TightVNC for Windows http://www.tightvnc.com/download.php
			- Error - TightVNC connection refused
			  collapsed:: true
				- http://stackoverflow.com/questions/23839647/error-in-tightvnc-viewer-no-connection-could-be-made-because-the-target-machine
				- sudo apt-get install x11vnc
				- x11vnc -storepasswd
				- x11vnc -usepw
				- sudo x11vnc -xkb -noxrecord -noxfixes -noxdamage -display :0 -auth /var/run/lightdm/root/:0 -usepw
				- http://pocketcloudsupport.wyse.com/entries/20003443-Why-am-I-getting-the-error-Could-not-connect-to-server-with-TightVNC-
				- **In the end used noticed that port was 5900 accoding to terminal so connected with that**
				- service vncserver restart (if any prblems)
		- ((6463499c-e15b-4225-9e1e-0e31863d1196))
		- Setup server management panel + SSL
		  collapsed:: true
			- Setup cPanel
			  collapsed:: true
				- Install cPanel/WHM via SSH
					- See documentation
				- Install WordPress installer on cPanel
					- WHM > CPAddons > Blogs (WordPress)
					- Or install Softaculous
						- https://www.softaculous.com/docs/Installing_Softaculous_in_cPanel
				- WHM > Server Configuration »Tweak Settings > >> Domains >> Allow Remote Domains ON
				- Install PHP ZipArchive (to use Duplicator
					- EasyApache 4 > Customise > PHP Extensions > ZIP
				- Change PHP upload limits in WHM PHP Configuration Editor
				  https://documentation.cpanel.net/display/56Docs/PHP+Configuration+Editor
				- If PMM server:
					- Get 'mbstring' so that customised WooCommerce PDF Invoices plugin works
					- WordPress debugging revealed a fatal error in how it was working
			- cPanel alternatives
				- http://www.hostingadvice.com/blog/cpanel-vs-plesk-vs-webpanel/
				- FOSS
					- [Cockpit Project — Cockpit Project](https://cockpit-project.org/)
						- [GitHub - cockpit-project/cockpit: Cockpit is a web-based graphical interface for servers.](https://github.com/cockpit-project/cockpit)
						-
					- [Coolify](https://coolify.io/)
						- [GitHub - coollabsio/coolify: An open-source & self-hostable Heroku / Netlify alternative. Cloud version available here -> https://app.coolify.io](https://github.com/coollabsio/coolify)
					- ((6463499d-ad5b-416b-b21b-7e9d6b700f6b))
			- Setup SSL
			  id:: 64634998-13c7-437b-803c-0fec50787fff
				- [mkcert](https://github.com/FiloSottile/mkcert) for making locally-trusted self-signed development certificates
				  collapsed:: true
					- `mkcert -install` = create a local Certificate Authority which will be installed in OS + browser trust stores
					- Usage
						- `mkcert -key-file key.pem -cert-file cert.pem example.com`
							- This will create a certificate for just `example.com`
							- By including `-key-file key.pem -cert-file cert.pem` it will output the files in the directory you run this command from
								- The CA certificate and its key are stored in an application data folder in the user home. You usually don't have to worry about it, as installation is automated, but the location is printed by `mkcert -CAROOT`
								- https://github.com/FiloSottile/mkcert?tab=readme-ov-file#changing-the-location-of-the-ca-files
						- `mkcert -key-file key.pem -cert-file cert.pem example.com "*.example.com" example.test localhost 127.0.0.1 ::1`
							- This will create a certificate for these 6 sources
							- Created a new certificate valid for the following names 📜
								- "example.com"
								- "*.example.com"
								- "example.test"
								- "localhost"
								- "127.0.0.1"
								- "::1"
				- Create a self-signed SSl certificate using OpenSSL
				  collapsed:: true
					- ```sh
					  # Interactive
					  openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -sha256 -days 365
					  
					  # Non-interactive and 10 years expiration
					  openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -sha256 -days 3650 -nodes -subj "/C=XX/ST=StateName/L=CityName/O=CompanyName/OU=CompanySectionName/CN=CommonNameOrHostname"
					  ```
				- ((6463499c-eb78-40d8-9a9e-ca7a9f0ad0be))
				- Adding SSL certificate to server
				  collapsed:: true
					- Free SSL certificates
					  collapsed:: true
						- Let's Encrypt SSL
						  [archived] [How To Secure Apache with Let's Encrypt on Ubuntu 14.04 | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-secure-apache-with-let-s-encrypt-on-ubuntu-14-04)
							- (note: don't need to edit the SSL certificate conf file after)
							- Quick version
								- sudo wget https://dl.eff.org/certbot-auto && sudo chmod a+x certbot-auto
								- sudo ./certbot-auto --apache --agree-tos --email aaron@sollesse.com --redirect -d cloud.mightdrop.pw
								- [source] https://bayton.org/2016/07/installing-nextcloud-on-ubuntu-16-04-lts-with-redis-apcu-apache/
							- Renew on bitnami
								- https://gist.github.com/printminion/6ec2fc0fefaba8e0a98a63a6d73b0802
								- [Generate and Install a Let's Encrypt SSL Certificate for a Bitnami Application](https://docs.bitnami.com/google/how-to/generate-install-lets-encrypt-ssl/#step-5-renew-the-lets-encrypt-certificate)
							- [Just a moment...](https://alternativeto.net/news/2025/7/let-s-encrypt-launches-free-ssl-tls-certificates-for-ip-addresses/)
							-
						- http://arstechnica.com/security/2009/12/how-to-get-set-with-a-secure-sertificate-for-free/
					- Nginx create SSL certificates
					  collapsed:: true
						- Further explanation https://www.digitalocean.com/community/tutorials/how-to-create-an-ssl-certificate-on-nginx-for-ubuntu-14-04
						- sudo mkdir /etc/nginx/ssl
						- sudo openssl req -x509 -nodes -days 365 -newkey rsa:4096 -keyout /etc/nginx/ssl/owncloud.**HOSTNAME.com**.key -out /etc/nginx/ssl/owncloud.<b>HOSTNAME.com</b>.crt
					- Commercial SSL certificates
					  collapsed:: true
						- How to activate & install a SSL certificate
							- https://www.digitalocean.com/community/tutorials/how-to-install-an-ssl-certificate-from-a-commercial-certificate-authority
							- https://www.namecheap.com/support/knowledgebase/category.aspx/14/ssl-certificates
							- https://www.liquidweb.com/kb/install-a-ssl-certificate-on-a-domain-using-cpanel/#step3
						- Add SSL certificate to server
							- Via cPanel (SSL/TLS > Manage SSL Sites)
							  https://postmymed.com:2083/cpsess0599944155/frontend/paper_lantern/ssl/install.html
							- Via WHM
						- See PMM files for SSL certificate files
						- Extended Validation
							- Long green bar
							- Doesn't appear on Google Chrome, does on Firefox
							- Mobile browsers?
				- How to add SSL to wordpress
				  collapsed:: true
				  Unneccesary if doing the above method. Simply change Site Address to HTTPS after
					- http://www.wpbeginner.com/wp-tutorials/how-to-add-ssl-and-https-in-wordpress/
					- https://premium.wpmudev.org/blog/ssl-https-wordpress/#
				- Enforcing HTTPS
				  collapsed:: true
				  AKA Force HTTPS / force SSL
					- _Via Plugin_
						- WP Force SSL plugin
						  https://wordpress.org/plugins/wp-force-ssl/
						- https://en-gb.wordpress.org/plugins/https-redirection/
						- https://wordpress.org/plugins/really-simple-ssl/
					- _Via htaccess file_
					  intralink2:: https://workflowy.com/#/073a20e9a1c9
				- Enforcing non-WWW
				  collapsed:: true
				  AKA force non-www / remove www
					- Create a CNAME record
						- Name: www.DOMAIN.com
						- Value: DOMAIN.com
					- Enforcing HTTPS + non-WWW via htaccess file
						- https://stackoverflow.com/a/6347222
							- RewriteCond %{HTTP_HOST} ^(www\.)(.+) [OR]
							- RewriteCond %{HTTPS} off
							- RewriteCond %{HTTP_HOST} ^(www\.)?(.+)
							- RewriteRule ^ https://%2%{REQUEST_URI} [R=301,L]
						- https://stackoverflow.com/a/21467534
						-
				- Ensure all these domains redirect properly
				  collapsed:: true
					- DOMAIN.com
					- www.DOMAIN.com
					- https://DOMAIN.com
					- http://DOMAIN.com
					- https://www.DOMAIN.com
					- http://www.DOMAIN.com
				- Insecure content / mixed content warnings
				  collapsed:: true
					- Determine what is causing it
						- Check that every image on the page is HTTPS
						- Online diagnoser
						  https://www.whynopadlock.com/
						- Firefox tools
							- Firebug
							  http://getfirebug.com/
							- Web Console
							  https://developer.mozilla.org/en-US/docs/Tools/Web_Console
					- https://managewp.com/wordpress-ssl-settings-and-how-to-resolve-mixed-content-warnings
					- https://en-gb.wordpress.org/plugins/ssl-insecure-content-fixer/
				- Related: ((634ae34a-1409-46ff-ace7-6fac429027b0))
			- _Related:_
				- Adding a New Domain to Self-Hosted cPanel
				  #CreateAWebsite-WordPress-Setup https://workflowy.com/#/4df588ebb4a2
				- Setup a WordPress Site
				  #CreateAWebsite https://workflowy.com/#/54b6113772cf
		- Apache commands
		  collapsed:: true
			- Start Apache
			  apachectl start
			- Stop Apache
			  apachectl stop
			- Graceful Stop
			  apachectl graceful-stop
			- Restart Apache
			  apachectl restart
			- Graceful restart
			  apachectl graceful
			- To find the Apache version
			  httpd -v
		- ServerName/Virtual Hosts?
		  collapsed:: true
			- ServerName
				- https://unix.stackexchange.com/questions/155150/where-in-apache-2-do-you-set-the-servername-directive-globally
				- The file to edit:
				- /etc/apache2/apache2.conf
				- Command to edit file:
				- sudo nano /etc/apache2/apache2.conf
				- For a global servername you can put it at the top of the file (outside of virtual host tags).
				- The first line looks like:
				- ServerName myserver.mydomain.com
				- Then save and test the configuration with the following command:
				- apachectl configtest
				- You should get:
					- Syntax OK
				- Then you can restart the server and check you don't get the error message:
				- sudo service apache2 restart
			- Set Up Your Domain
				- _Method 1_
				  collapsed:: true
					- In order to use your own domain with the site, you will need to update your Apache configuration. Edit both
						- sudo nano /etc/apache2/sites-available/owncloud-ssl.conf
						- and
						- sudo nano /etc/apache2/sites-available/000-owncloud.conf
						- and replace the line:
							- ServerName www.example.com
							- with:
							- ServerName your_domain.com
					- Next, you should edit the trusted_domains entry in you ownCloud configuration. This is located in
						- sudo nano /var/www/owncloud/config/config.php
						  'trusted_domains' =>
						  array (
						  0 => 'your_domain.com',
						  ),
					- Once again, you will need to restart Apache in order for the changes to take affect:
						- sudo service apache2 restart
				- _Method 2_
				  collapsed:: true
					- Update DNS with A record
					- Next, you should edit the trusted_domains entry in you ownCloud configuration. This is located in
						- sudo nano /var/www/owncloud/config/config.php
						  'trusted_domains' =>
						  array (
						  0 => 'your_domain.com',
						  ),
						  
						  or it can be a 1 or 2 on a new line
		- Modify your hosts file to override the DNS for a domain
		  collapsed:: true
			- This is useful when you want to test your site without the test link, prior to going live with SSL; verify that an alias site works, prior to DNS changes; and for other DNS-related reasons. Modifying your hosts file causes your local machine to look directly at the IP address specified.
			- How to
				- Run notepad as administrator
				  Can't use Notepad++
				- On Windows 7 open C:\Windows\System32\Drivers\etc\hosts.
				- Add 'IP DOMAIN'
				  e.g. 52.56.184.68 postmymeds.co.uk
					- Can add www domain also
				- Saving will automatically update it
	- Server Management
	  collapsed:: true
		- How to setup SSH access for a freelancer
		  collapsed:: true
			- Use puttygen to create public (to put on server) and private (to keep) key pairs
			- Upload to SSH key directory
			  collapsed:: true
				- Example:
					- on EC2 Bitnami it's here
					  /home/bitnami/.ssh
					- on Amazon Linux it's here
					  /home/ec2-user/.ssh/authorized_keys
				- intralink2:: https://workflowy.com/#/329da35168d6
			- _Alternatives_
			  collapsed:: true
				- It is much better to give a separate key to your freelancer which you can delete anytime you want. You don’t want to hand the password over to a stranger
				- Turn off SSH key requirement to allow password access - but only allow certain IP addressed via AWS Security Groups?
				  **WARNING: **Requires turning off SSH key login requirement | Security risk mitigated by using AWS security groups to allow SSH for only my VPN + their IP address
					- Change SSH key requirement
					  nano /etc/ssh/sshd_config
						- change the PasswordAuthentication value as yes
					- Restart the ssh service.
						- In Debian or Ubuntu instance:
						  /etc/init.d/ssh restart
						- In CentOS or Red Hat instance:
						  /etc/init.d/sshd restart
					- Test it out by opening another terminal (don't close the primary before this)
		- Setting up FTP access via terminal
		  collapsed:: true
			- https://stackoverflow.com/questions/7052875/setting-up-ftp-on-amazon-cloud-server
			- https://silicondales.com/tutorials/aws-ec2-tutorials/setup-ftp-sftp-aws-ec2-instance/
		- WinSCP
		  collapsed:: true
		  Basically SFTP but with sudo. Allows scp over ssh
			- How to SFTP with sudo permissions
				- https://stackoverflow.com/questions/3381498/how-to-use-sudo-over-sftp-with-cyberduck
				- (Already setup in WinSCP)
		- HeidiSQL
		- SSL Certificates
		  collapsed:: true
			- You _must_ have both www and non-www on the same certificate
				- "If a user types in https://example.com, the TLS handshake between their browser and your server happens before the redirect. Users will see an error message in their browser indicating the site's certificate is invalid."
		- Analysis
		  collapsed:: true
			- Analysing Disk Usage
			  collapsed:: true
			  AKA memory
				- df -h
				- ncdu
				  collapsed:: true
				  Text-based but good intuitive visual disk usage analysis
					- Install ncdu
					  sudo apt-get install ncdu
					- Start tool
					  ncdu
					- _Keyboard_
						- Use enter and arrow keys to move around
						- Delete folder recursively (it'll give a confirmation prompt too)
						  d
						- Quit when finished
						  q
				- http://askubuntu.com/questions/5980/how-do-i-free-up-disk-space
				- http://askubuntu.com/questions/9642/how-can-i-monitor-the-memory-usage
			- Performance
			  collapsed:: true
				- htop
				- Checking Performance
					- ((67376781-c0ff-4eb0-8a85-b6769861711d)) - Graphs for overall average
					- WHM Daily Process Log
					  https://139.59.172.91:2087/cpsess4751013164/scripts2/showcpuusage
						- Guide
						  https://documentation.cpanel.net/display/ALD/Daily+Process+Log
					- Apache
					  https://139.59.172.91:2087/cpsess4751013164/scripts2/apachestatus
						- Guide
						-
		- WD MyCloud
		  collapsed:: true
			- http://wdmycloud/
			- Help
			  http://wdmycloud/web/WebHelp/10152015/EN-US/index.htm#welcome.htm
			- Remote access
				- _Cloud access_
				  collapsed:: true
					- Assign a static IP address
						- This is important to note. When you set your computer to a static ip address, the router does not know that a computer is using that ip address. So the very same ip address may be handed to another computer later, and that will prevent both computers from connecting to the internet. So when you asign a static IP addresses, it's important to assign an IP address that will not be handed out to other computers by the dynamic IP address server. The dynamic IP address server is generally refered to as the dhcp server.
				- Router
				  #Privacy-Threats https://workflowy.com/#/f2f5f69ac5cc
				- See [Syncthing](https://workflowy.com/#/26351aa44633)?
				- SFTP?
				  collapsed:: true
					- https://mountainduck.io/
					- Use a DDNS if using a dynamic IP/DHCP
					- DDNS not needed if using a static IP
				- HTTPS?
				- MyCloud.com?
				- WebDAV "remote mapping" removed
				  collapsed:: true
					- Removed from firmware v3
					  https://community.wd.com/t/re-enable-remote-drive-mapping-through-mycloud-com/134944/5
					- Documentation
					  https://support.wdc.com/knowledgebase/answer.aspx?ID=16497#ConfigureWebDAV
					- Alternative solutions
						- I'm using VPN from my PC to the router on my MyCloucMirror Network so that I can then map drives again.
						- SSH
						  collapsed:: true
							- I was able to re-enable it in the most recent MyCloud firmware
							  (v04.04.01-112) by using SSH to make a simple modification to one of
							  MyCloud's web server configuration files. After making the change I can
							  remotely map a folder using the following standard Windows 7 command:
							  
							  net use z: \\device1234567-12345678.wd2go.com@SSL:443\Public\_ /User:user_id password
							  
							  (Note that the above host name, user_id, and password are a random example.)
						- Apache WebDAV
						  collapsed:: true
							- Remote folder mapping is accomplished using WebDAV. The MyCloud is
							  running an apache web server and apache supports WebDAV. The current
							  MyCloud firmware still enables the apache WebDAV module but removed the
							  configuration that is needed to turn it on for each share. The
							  configuration was previously located in the following text configuration
							  file \root\etc\nas\apache2\auth\require.inc. I just added back the 15
							  or so lines of configuration required to turn on WebDAV for my public
							  share.
							  
							  Here are a few other details:
							  
							  Unless you make further modifications to the configuration, the
							  username and password that need to be used in the windows 7 command are
							  actually a user id number assigned by the MyCloud and a hash of the
							  users password. I learned about this in the following post: https://community.wd.com/t/enable-webdav/94727/372.
							  
							  The hostname to use in the Windows 7 command is the hostname provided
							  by the Western Digital DDNS service. You also need to make sure that
							  windows considers the security certificate to be valid. This can be done
							  by going to the webpage in internet explorer (for example https://device1234567-12345678.wd2go.com33)
							  and making sure there are no certificate warnings. If there is a
							  warning the certificate will need to be accepted before Windows will
							  allow a WebDAV connection.
							  
							  Lastly the :443 in my Windows 7 command example assumes that port 443 is the port that has been forwarded.
							  
							  If it becomes apparent that Western Digital is not going to add the
							  feature back, it wouldn’t be too hard to write a complete step by step
							  guide on how to do this.
						- CloudDAVMod
						  collapsed:: true
							- https://community.wd.com/t/app-clouddavmod-various-versions-for-firmware-v4-04-2017/161543/64
		- Managing Multiple Servers
		  id:: 653a9ddb-ae82-4c2f-82ea-9c9e8f266c59
		  collapsed:: true
			- ((6463499c-18cf-49dd-a6f7-593e7aded1d5))
			  id:: 653aa115-8854-4604-89bd-437f8c937fa2
			- Orchestration
			  id:: 66cd757e-c8d2-4b0e-9d0e-33772f444011
				- ((6463499d-56d9-4954-b881-ca482d664d19)) e.g. ((6463499d-b2c2-41e3-9f06-5b5fd75a452b))
				- ((6463499d-6d71-4948-84f4-9ae88ef6c73d)) e.g.
				- Related: ((663a58ee-47ac-45a2-ba9f-70480c933acf))
			- Related: ((6463499c-7e93-4675-bd3f-ff831c772a24))
		- Loop devices
		  collapsed:: true
			- A loop device is a virtual block device in Unix-like operating systems that allows a regular file to be accessed as if it were a physical disk or partition. This enables users to mount file images, such as ISO files, as if they were actual devices, facilitating the use and manipulation of these files as if they were real disk drives. Loop devices are particularly useful for managing and editing file system images offline, such as CD or DVD images, without the need for physical media.
			- Can use `losetup` to create them and `mount`/`umount` to mount/unmount them
	- **Setup Software**
	  collapsed:: true
		- How to Host a Website
		  collapsed:: true
			- Other types
			  collapsed:: true
				- Basic 1 WordPress domain install
				  Not control panel backend
					- https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-on-ubuntu-14-04
					- https://www.digitalocean.com/community/tutorials/one-click-install-wordpress-on-ubuntu-14-04-with-digitalocean
				- Multiple domains/apps
				  #VirtualHosts https://workflowy.com/#/8ecadd24eaed
			- Connect or Setup DNS
			- Setup a Hostname
			  collapsed:: true
				- https://www.digitalocean.com/community/tutorials/how-to-set-up-a-host-name-with-digitalocean
				- ping test.example.com
			- Installing a Control Panel
			  collapsed:: true
				- http://www.tecmint.com/web-control-panels-to-manage-linux-servers/
				- Control panels
					- https://serverpilot.io/
					- VestaCP
					- Sentora
				- \_Related: \_Multiple domains/apps
				  #VirtualHosts https://workflowy.com/#/8ecadd24eaed
			- LAMP (Linux, Apache, MySQL, PHP)
			- Opening ports so website is accessible on WAN
			  collapsed:: true
				- \_Related: \_Basic Security
				  intralink2:: https://workflowy.com/#/044e8cd79152
				- Why
					- Your Web server works great at this point, but it's not reachable from outside your LAN—exposing it to the Internet will require you to do some configuration on your NAT router and/or your LAN's firewall.
				- However, you need to carefully consider what you want to expose.
					- To actually let folks outside your LAN use your Web server requires only a single opening—if you have a NAT router, like most home users, you need to forward TCP port 80 to your Web server. Some ISPs block port incoming requests on TCP port 80 for their residential customers; if that's the case for you, pick another high-order port, like 8080 or 8088, and forward that to TCP port 80 on your Web server.
					- Don't forward any ports you don't have a reason to forward. It might be tempting to use the "DMZ host" function in your NAT router to open all of its ports to the Internet, but this is a terrible idea. It robs your host of much of the protection from attack it gains by being behind a NAT router.
					- There are a couple of additional ports you might consider opening up besides TCP port 80. If you're going to use SSL/TLS encryption for serving things via HTTPS, you should also forward TCP port 443 to your Web server. If you want to be able to connect via ssh from the Internet, you should forward TCP port 22. However, if you're going to do this, make sure to take the appropriate precautions (which we'll get to in just a moment).
				- sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
				- sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
			- Complete Basic Security (if not already finished)
			  #SysAdmin https://workflowy.com/#/044e8cd79152
			- Fast server
			  collapsed:: true
				- Nginx
				  (pronounced "engine-ex")
				- php5-fpm
				  php handler, works as separate service. very fast
					- which is a heavily modified PHP package with built-in FastCGI capabilities. Blacken's recommendation to go with php5-fpm instead of the older and better-known php5-cgi bundle was because fpm's ability to turn on or turn off new PHP processes as dictated by server load makes it a much smarter and more powerful package; it can consume fewer resources and at the same time scale transparently under load and maintain speed.
				- Varnish cache
				  Server side caching
			- _Learning Resources_
			  collapsed:: true
				- ((67376780-c521-4602-bbcb-c23d12ced6a4)) > Apache
				  id:: 6737677f-2658-4b70-9dec-73c8da7b5334
				  Faster and more scalable but bigger learning curve
					- Why: http://arstechnica.com/business/2011/11/a-faster-web-server-ripping-out-apache-for-nginx/
					- How: http://arstechnica.com/gadgets/2012/11/how-to-set-up-a-safe-and-secure-web-server/2/
						- Nginx
						  #VirtualHosts https://workflowy.com/#/8ecadd24eaed
					- Nginx v Apache modules
						- Modules
						  collapsed:: true
							- Both Nginx and Apache are extensible through module systems, but the way that they work differ significantly.
							- Apache
							- Apache's module system allows you to dynamically load or unload modules to satisfy your needs during the course of running the server. The Apache core is always present, while modules can be turned on or off, adding or removing additional functionality and hooking into the main server.
							- Apache uses this functionality for a large variety tasks. Due to the maturity of the platform, there is an extensive library of modules available. These can be used to alter some of the core functionality of the server, such as mod_php, which embeds a PHP interpreter into each running worker.
							- Modules are not limited to processing dynamic content, however. Among other functions, they can be used used for** rewriting URLs, authenticating clients, hardening the server, logging, caching, compression, proxying, rate limiting, and encrypting**. Dynamic modules can extend the core functionality considerably without much additional work.
						- Nginx
						  collapsed:: true
							- Nginx also implements a module system, but it is quite different from the Apache system. In Nginx, modules are not dynamically loadable, so they must be selected and compiled into the core software.
							- For many users, this will make Nginx much less flexible. This is especially true for users who are not comfortable maintaining their own compiled software outside of their distribution's conventional packaging system. While distributions' packages tend to include the most commonly used modules, if you require a non-standard module, you will have to build the server from source yourself.
							- Nginx modules are still very useful though, and they allow you to dictate what you want out of your server by only including the functionality you intend to use. Some users also may consider this more secure, as arbitrary components cannot be hooked into the server. However, if your server is ever put in a position where this is possible, it is likely compromised already.
							- Nginx modules allow many of the same capabilities as Apache modules. For instance, Nginx modules can provide **proxying support, compression, rate limiting, logging, rewriting, geolocation, authentication, encryption, streaming, and mail functionality.**
		- OpenVPN
		  collapsed:: true
			- DigitalOcean user data
			  https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-14-04
				- Starting from 'Transferring Certificates and Keys to Client Devices'
					- All files are in the Root folder (use 'ls' to check after SSH login)
					- Only need to download 'client.ovpn' though and add it to OpenVPN/data/config/ folder, + rename it to 'SERVERNAME.ovpn'
				- Downloading file
					- Easiest method is WinSCP or FileZilla
					  intralink2:: https://workflowy.com/#/a9c8c3ccea98
					- or use SFTP via CLI (though I didn't get it to work)
						- scp root@178.62.82.32:/etc/openvpn/easy-rsa/keys/client1.key Downloads/
						- scp root@178.62.82.32:/etc/openvpn/easy-rsa/keys/client1.crt Downloads/
						- scp root@178.62.82.32:/etc/openvpn/easy-rsa/keys/client.ovpn Downloads/
						- scp root@178.62.82.32:/etc/openvpn/ca.crt Downloads/
		- ownCloud/Nextcloud
		  collapsed:: true
			- Setup
			  collapsed:: true
				- Contacts
					- https://doc.owncloud.org/server/8.1/user_manual/pim/index.html
				- Calendars
					- Setup Thunderbird calendars
					- Click on the calendar in the left-hand menu THEN click-and-drag create an event
			- Apps
			  collapsed:: true
				- https://apps.owncloud.com/
				- https://apps.nextcloud.com/
				- https://docs.nextcloud.com/server/10/admin_manual/installation/apps_supported.html
			- Extra apps
			  collapsed:: true
				- Shorty
				  collapsed:: true
				  Link shortener
					- https://apps.owncloud.com/content/show.php/Shorty?content=150401&PHPSESSID=cj35c61hg34e38jfsg7c3qujp4
				- Tasks
				  collapsed:: true
				  For CalDAV (requires calendar app)
					- https://apps.owncloud.com/content/show.php/Tasks?content=164356&PHPSESSID=cj35c61hg34e38jfsg7c3qujp4
				- Dashboard
				  collapsed:: true
					- https://apps.owncloud.com/content/show.php/dashboard?content=160265&PHPSESSID=cj35c61hg34e38jfsg7c3qujp4
				- Files move/copy
				  collapsed:: true
					- https://apps.owncloud.com/content/show.php/Files+move?content=150271&PHPSESSID=cj35c61hg34e38jfsg7c3qujp4
				- Files Tree
				  collapsed:: true
					- https://apps.owncloud.com/content/show.php/Files+Tree?content=155479&PHPSESSID=cj35c61hg34e38jfsg7c3qujp4
				- Mail or roundcube
				- News (RSS)
				  collapsed:: true
					- http://github.com/owncloud/news
					- Clients
						- https://github.com/owncloud/core/wiki/Apps
				- Tasks
				  collapsed:: true
					- https://github.com/owncloud/tasks
					- and make sure foldersync and a caldav task app is setup
					- Thunderbird
						- Click on the calendar in the left-hand menu THEN click-and-drag create a task
					- Consider reminderFox for Thunderbird http://www.reminderfox.org/remote-calendar-n/#features
					- download your tasks as ICS files using the download button for each calendar.
					- Download Android zips to get source
					- https://github.com/MirakelX/mirakel-android
					- https://github.com/dmfs/opentasks
				- SMS
				  collapsed:: true
					- https://play.google.com/store/apps/details?id=fr.unix_experience.owncloud_sms&hl=en
					- https://f-droid.org/repository/browse/?fdid=fr.unix_experience.owncloud_sms
					- https://apps.owncloud.com/content/show.php?content=167289&forumpage=4
				- https://nextcloud.com/collaboraonline/ - web libreoffice
				- https://nextcloud.com/webrtc/
				- Tagspaces
				  collapsed:: true
					- https://www.tagspaces.org/blog/webdav-edition/
				- 2-factor authentication
				  collapsed:: true
					- https://www.freeipa.org/page/Owncloud_Authentication_against_FreeIPA
				- More
				  collapsed:: true
					- https://github.com/owncloud/core/wiki/Apps
			- _Manual: Maintenance and assorted tasks_
			  collapsed:: true
				- Migrating and upgrading
				  collapsed:: true
					- https://docs.nextcloud.com/server/11/admin_manual/maintenance/manual_upgrade.html
					- Rough manual
						- Download Nextcloud version
						  https://nextcloud.com/changelog/
						- Upload to a new directory e.g. /var/next/
						- To unpack your new tarball, run:
						  tar xjf nextcloud-[version].tar.bz2
						- Stop apache
						  intralink2:: https://workflowy.com/#/58790eff2c53
						-
						- /var/www/owncloud
						- Login as www-data for occ commands
						  su -s /bin/bash www-data
						- Run install after copying files
						  sudo -u www-data php occ upgrade
				- Remove index.php from slug
				  collapsed:: true
					- For Nextcloud index.php removal from URL, guy who configured LAMP on this server, forgot to enable .htaccess & mod_rewrite.
					- Also see
					- https://help.nextcloud.com/t/remove-index-php-from-the-url/2611/14
				- Managing storage (trashbin and file versions)
				  collapsed:: true
					- Managing Trashbin (like Windows Recycle Bin)
					  collapsed:: true
						- Managing deleted files
						  https://docs.nextcloud.com/server/13/user_manual/files/deleted_file_management.html
							- How the deleted files app manages storage space
								- To ensure that users do not run over their storage quotas, the Deleted Files app allocates a maximum of 50% of their currently available free space to deleted files. If your deleted files exceed this limit, Nextcloud deletes the oldest files (files with the oldest timestamps from when they were deleted) until it meets the memory usage limit again.
								- Nextcloud checks the age of deleted files every time new files are added to the deleted files. By default, deleted files stay in the trash bin for 30 days. The Nextcloud server administrator can adjust this value in the config.php file by setting the `trashbin_retention_obligation` value. Files older than the `trashbin_retention_obligation` value will be deleted permanently. Additionally, Nextcloud calculates the maximum available space every time a new file is added. If the deleted files exceed the new maximum allowed space Nextcloud will expire old deleted files until the limit is met once again.
						- Configuration parameters
						  https://docs.nextcloud.com/server/13/admin_manual/configuration_server/config_sample_php_parameters.html
							- auto
								- default setting. keeps files and folders in the trash bin for 30 days and automatically deletes anytime after that if space is needed (note: files may not be deleted if space is not needed).
					- Managing File Versions
					  collapsed:: true
						- Config.php
							- https://doc.owncloud.org/server/9.1/admin_manual/configuration_server/config_sample_php_parameters.html#file-versions
							- 'versions_retention_obligation' => 'auto',
							- auto
								- default setting. Automatically expire versions according to expire rules. Please refer to Controlling File Versions and Aging for more information.
						- Controlling File Versions and Aging
							- https://doc.owncloud.org/server/9.1/admin_manual/configuration_files/file_versioning.html
							- The Versions app (files_versions) expires old file versions automatically to ensure that users don’t exceed their storage quotas. This is the default pattern used to delete old versions:
								- For the first second we keep one version
								- For the first 10 seconds ownCloud keeps one version every 2 seconds
								- For the first minute ownCloud keeps one version every 10 seconds
								- For the first hour ownCloud keeps one version every minute
								- For the first 24 hours ownCloud keeps one version every hour
								- For the first 30 days ownCloud keeps one version every day
								- After the first 30 days ownCloud keeps one version every week
							- The versions are adjusted along this pattern every time a new version is created.
							- The Versions app never uses more that 50% of the user’s currently available free space. If the stored versions exceed this limit, ownCloud deletes the oldest file versions until it meets the disk space limit again.
					- Reported bugs
					  collapsed:: true
						- Versions should delete when disk full
						  https://github.com/nextcloud/server/issues/11683
						- Trashbin ignores quotes
						  https://github.com/nextcloud/server/issues/10862
						- Trashbin should empty when disk full
						  https://github.com/nextcloud/server/issues/11658
				- Website is inaccessible
				  collapsed:: true
					- Disk space got full and server was down
						- The issue was the server was a bit outdated. You should run sudo apt-get update && sudo apt-get upgrade often
						- Also run this: sudo systemctl status snap.nextcloud.apache and sudo systemctl status snap.nextcloud.mysql
							- to see if the apache and mysql services are running
							- if both are running and nextcloud does not work, then there is a huge problem.
							- In this case, snap.nextcloud.apache was down
							- once the webserver is down, nextcloud/webapp/ or any website can never be accessed
			- 2 Backlinks
			  collapsed:: true
				- See [ownCloud/Nextcloud](https://workflowy.com/#/d93e0a6496ad)
				- See [ownCloud/Nextcloud](https://workflowy.com/#/d93e0a6496ad)
				  #SysAdmin
		- Remote PC Access
		  collapsed:: true
			- How to Setup a PC as a FTP Server
				- http://lifehacker.com/124212/geek-to-live--how-to-set-up-a-personal-home-web-server
				- http://lifehacker.com/124804/geek-to-live--how-to-assign-a-domain-name-to-your-home-web-server
				- http://lifehacker.com/130806/how-to-set-up-a-home-ftp-server
		- Seafile
		  collapsed:: true
			- https://github.com/haiwen/seafile-docker
			- Personal Seafile EC2
				- Let's Encrypt auto-renewal cron in /var/spool/cron/crontabs/root
				- or you can run crontab -l command to list cron as well.
	- Subfields
		- DevOps
		  id:: 63904f38-558d-474c-b38b-a121e3233aa4
		  collapsed:: true
		  #DevOps
			- Pros/Cons
			  collapsed:: true
				- Pros
					-
				- Cons
					-
				- Unclear
				- Comparisons
					- ((63904f38-558d-474c-b38b-a121e3233aa4)) as career vs ((6396fb64-6ebd-4c5d-9e3d-d1604de0ea30))
					  id:: 31ea52db-a427-4048-8e18-6e05673cb9e5
						- For ((63904f38-558d-474c-b38b-a121e3233aa4)) as career
							- DevOps is Usually more "necessary" than regular devs in hard financial times, as devops has to control permissions and be responsible for servers
						- For ((6396fb64-6ebd-4c5d-9e3d-d1604de0ea30))
							- Less on-call
							- Less boring ops/configuration kind of work (yaml guru)
							- Less responsiblity (SLOs)
							- More thankful work (not being thanked for prevented outages but stared at when down)
							- FAANG requires DevOps AND coding skills for interviews (Linux/HTTP and leetcode) if your title is DevOps
							- Less tooling/technology learning needed (tooling landscape moves very quickly and is big )
							  collapsed:: true
								- ![image.png](../assets/image_1714240239117_0.png)
						- Similarities
							-
						- Unclear
							- DevOps salary: Think the floor is higher, middle is lower, ceiling is the same or slightly lower
						- Assorted
							- On-call is way worse than other areas of SWE. You are responsible for the infra of the entire company.. so think of the networking. cloud services, CI/CD pipelines, servers, etc. Shit breaks constantly and you'll be pinged at 2am to fix a huge bug that's costing the company hundreds of thousands of dollars per minute and they need it fixed ASAP
							- To succeed you have to basically know everything about tech. Not in depth, but in breadth. Programming, OS, Networking, Distributed systems, cloud computing, containers, etc etc
							- You don't get to code as much as other SWE areas. I mean actual programming. A lot of people just love to write code, but with DevOps / SRE it's usually more like configuration coding.. think YAML files and JSON files.
							- It's generally seen as a cost center. The rockstars in a tech company are the SWEs who are working on the product... not the poor souls who are supporting the infrastructure and having to be on-call
							- Burn out is EXTREMELY common (just google DevOps work life balance, and you'll be met with endless amount of posts talking about how terrible it is)
							- Related to #4, you are not as visible to management or customers as a result. You are wayyyyy in the background, no one knows WTF you do other than your team and your pet dog that you cry to every night before bed.
			- Version Control System
			  id:: 6737677f-ea5a-4602-9709-d1557a3ac3cf
			  AKA VCS / Distributed Version Control
				- [[Git]]
				- SVN
				- Mercurial
				- [`jj`](https://jj-vcs.github.io/jj/latest/)
				  id:: 691335d0-885e-48cb-9ec5-01a222dc5096
				  collapsed:: true
				  AKA Jujutsu | [[Git]]-compatible VCS
					- [GitHub repo](https://github.com/jj-vcs/jj)
					- ## Ecosystem
						- https://github.com/idursun/jjui
						- https://github.com/rafikdraoui/jj-diffconflicts
			- Dependency Management
			  id:: 6827b984-93e3-4d84-892b-b4777361e819
				- BAE SATURN workflow
				  id:: 6827b98c-da09-4c3e-9da1-6c5ed08abca8
				  collapsed:: true
					- JavaScript
					  collapsed:: true
						- `Dockerfile.yarn`
						  collapsed:: true
							- ```yml
							  FROM node:22.13.1-slim AS build
							  
							  WORKDIR /deps
							  
							  COPY package.json .yarnrc.yml .
							  
							  RUN corepack enable
							  
							  RUN corepack pack -o yarn-tmp.tgz
							  
							  RUN yarn
							  
							  RUN apt install -y make python build-essential
							  
							  RUN mkdir ./tmp
							  RUN tar -xvf yarn-tmp.tgz -C ./tmp
							  RUN cd ./tmp && tar -czf yarn.tgz \
							      --mtime='UTC 1970-01-01' \
							      --sort='name' \
							      --owner=0 \
							      --group=0 \
							      --mode=774 \
							      *
							  RUN mv ./tmp/yarn.tgz .
							  
							  RUN rm ./.yarn/install-state.gz
							  
							  RUN tar -czf yarn-deps.tgz \
							      --mtime='UTC 1970-01-01' \
							      --sort='name' \
							      --owner=0 \
							      --group=0 \
							      --mode=774 \
							      ./.yarn
							  
							  RUN sha256sum yarn.tgz yarn-deps.tgz | sort > yarn.sha256
							  
							  FROM scratch
							  COPY --from=build /deps/yarn.tgz /deps/yarn-deps.tgz /deps/*.json /deps/*.lock /deps/.yarnrc.yml /deps/yarn.sha256 /
							  ```
						- `.yarnrc.yml`
							- ```yml
							  cacheFolder: ./.yarn/cache
							  enableGlobalCache: false
							  nodeLinker: node-modules
							  ```
						- `Dockerfile.pnpm`
							- ```
							  FROM node:22.13.1-slim AS build
							  
							  WORKDIR /deps
							  
							  ENV COREPACK_INTEGRITY_KEYS=0 
							  RUN corepack enable pnpm
							  
							  RUN corepack pack pnpm@10.9.0 -o pnpm.tgz
							  
							  
							  FROM scratch
							  COPY --from=build /deps/pnpm.tgz .
							  
							  ```
						- `Dockerfile.npm`
							- ```
							  FROM node:22.13.1-slim AS build
							  
							  WORKDIR /deps
							  
							  # Copy our dep definitions
							  COPY package.json .yarnrc.yml .
							  
							  # Install Yarn
							  RUN corepack enable
							  
							  RUN corepack pack -o yarn-tmp.tgz
							  
							  # Package Yarn
							  RUN mkdir ./tmp
							  RUN tar xvf yarn-tmp.tgz -C ./tmp
							  RUN cd ./tmp && tar -czf yarn.tgz \
							      --mtime='UTC 1970-01-01' \
							      --sort='name' \
							      --owner=0 \
							      --group=0 \
							      --mode=774 \
							      *
							  RUN mv ./tmp/yarn.tgz .
							  
							  # Install our deps
							  RUN yarn
							  RUN rm ./.yarn/install-state.gz
							  
							  # Package our deps
							  RUN tar -czf yarn-deps.tgz \
							      --mtime='UTC 1970-01-01' \
							      --sort='name' \
							      --owner=0 \
							      --group=0 \
							      --mode=774 \
							      ./.yarn
							  
							  RUN sha256sum yarn.tgz yarn-deps.tgz debs.tgz | sort > files.sha256
							  
							  FROM scratch
							  COPY --from=build /deps/yarn.tgz /deps/yarn-deps.tgz /deps/*.json /deps/*.lock /deps/.yarnrc.yml /deps/debs.tgz /deps/yarn.sha256 /
							  ```
					- Python
					  collapsed:: true
						- ((67a8e143-856e-4949-bd93-4c62cfe7ee1c))
						- `Dockerfile.pip`
						  collapsed:: true
							- ```
							  FROM python:3.13.1-slim AS build
							  
							  WORKDIR /deps
							  
							  COPY pyproject.toml .
							  
							  # RUN python3 -m pip download --requirement requirements.txt --dest .pip
							  RUN python3 -m pip download --dest .pip .
							  RUN python3 -m pip install --no-index --find-links .pip .pip/*.whl
							  RUN python3 -m pip list --format freeze > requirements.txt
							  
							  RUN tar -czf .pip.tar.gz \
							      --mtime='UTC 1970-01-01' \
							      --sort='name' \
							      --owner=0 \
							      --group=0 \
							      --mode=774 \
							      -C .pip \
							      .
							  RUN sha256sum .pip/* | sort > .pip.sha256
							  
							  FROM scratch
							  COPY --from=build /deps/.pip.tar.gz /deps/pyproject.toml /deps/.pip.sha256 /deps/requirements.txt /
							  ```
						- `python -m pip install --no-index --find-links path/to/whls-dir path/to/whl/*.whl`
							- This is how you can install all Python wheels and resolve the order of proper installation automatically
						- ((67cc4979-cb32-41f7-9f5f-4f5c3a6a900b))
					- Java/Kotlin
					  collapsed:: true
						- `Dockerfile.gradle`
							- ```
							  FROM gradle:jdk17 AS build
							  
							  WORKDIR /deps
							  
							  COPY * .
							  
							  RUN ./gradlew build test
							  
							  RUN tar -czf .gradle.tar.gz \
							      --mtime='UTC 1970-01-01' \
							      --sort='name' \
							      --owner=0 \
							      --group=0 \
							      --mode=774 \
							      -C ~/.gradle/caches/modules-2/files-2.1 \
							      .
							  RUN sha256sum .gradle/* | sort > .gradle.sha256
							  
							  FROM scratch
							  COPY --from=build /deps/.gradle.tar.gz /deps/.gradle.sha256 /
							  ```
					- Rust
					  collapsed:: true
						- `Dockerfile.cargo`
							- ```
							  FROM rust:1.86.0-slim AS build
							  
							  WORKDIR /deps
							  
							  COPY Cargo.lock Cargo.toml .
							  
							  RUN cargo vendor
							  
							  RUN tar -czf .vendor.tar.gz \
							      --mtime='UTC 1970-01-01' \
							      --sort='name' \
							      --owner=0 \
							      --group=0 \
							      --mode=774 \
							      -C vendor \
							      .
							  RUN sha256sum .vendor.tar.gz | sort > .vendor.sha256
							  
							  FROM scratch
							  COPY --from=build /deps/.vendor.tar.gz /deps/Cargo.lock /deps/Cargo.toml /deps/.vendor.sha256 /
							  ```
			- DevOps for Websites
				- Git for web development
				  id:: 64634998-e08f-4cc0-8ca6-a060b0c36c69
				  collapsed:: true
					- Manual
					  collapsed:: true
						- WordPress-Git Workflow
						  collapsed:: true
							- Goals
								- Make setup + deployments easier
								- Keep sensitive information out of the repository
								- Never have a git status return modified files on production
							- Steps
								- Clone repository
								- Import database
								- Fill out wp-config.php
								- Setup virtual host (if necessary)
							- Avoid updating plugins on your production system using the admin interface of Wordpress - as at best, your git copy will overwrite any plugins you update as soon as you push/checkout, at worst you'll get conflicts. Do your updates using the the admin interface on your development system, commit, push and checkout in production.
							- IfModule you can drop into your dev site’s .htaccess file to load files from production site if not present on dev site
						- Push / pull are to remote directories
						- beginner resoureces
						  collapsed:: true
							- https://premium.wpmudev.org/blog/git-for-wordpress-development/
						- [[Git]]
					- _Git software ecosystem_
					  collapsed:: true
						- Git Workflow
							- _WordPress plugins_
								- Revisr
								  collapsed:: true
									- https://revisr.io/docs/
									- Pros/Cons
									  collapsed:: true
										- Pros
											- Can track database changes
											- Requires manual commits
												- VersionPress tracks every change you make to your site automatically)and Revisr tracks changes when you commit them to the Git repository manually.
										- Cons
											- Can't merge databases if there's conflicting changes that would change IDs
									- Dashboard
									  collapsed:: true
									  /wp-admin/admin.php?page=revisr
										- Settings
										  /wp-admin/admin.php?page=revisr_settings
											- General Settings
												- “Automatic backup schedule”. If set, Revisr will automatically commit any modified or untracked (but not ignored) files and backup the database at the interval of your choosing. Combine this with the auto-push functionality (explained here) and have peace of mind with lightning fast (and free) daily or weekly off-site backups.
											- Remote
												- Remote URL
												  collapsed:: true
													- https://PostMyM:PASSWORD@github.com/LeapingDragon/PMM-UK1.git
													- IMPORTANT: If you’re using the HTTPS method to connect, you will need to provide your password in the URL as shown in the screenshot above. This will be stored in clear text in your .git/config file, so make sure that you take the necessary precautions to lock it down as described here.
													- Using the SSH method to connect avoids this issue altogether, although you will have to generate an SSH key on your server and add it to Bitbucket or GitHub. You can read more about that here (the process is generally the same for both providers, but make sure when generating a key that you don’t use a passphrase so Revisr can push automatically).
													- Note: I don't think SSH to push is possible. To pull yes, but not push. When I try to use just CLI bash I can pull but not pull with commands.
												- Automatically push new commits?
												  YES for Production
												- Automatically pull new commits?
												  USUALLY YES for Development
												- Docs
												  collapsed:: true
													- Revisr Webhook URL – Revisr will send a POST request to this URL when pushing (see “Automatically pulling commits” below)
													- Automatically push new commits – Just like the name implies, this setting will make Revisr push commits as soon as they are made. Combined with the daily backup setting, this could be a real time saver!
													- Automatically pull new commits – Checking this box will generate a secure webhook that can be added to Bitbucket, GitHub, or other instances of Revisr. When this webhook is triggered, Revisr will pull any pending commits from the remote repository. This is mainly helpful if you have multiple instances of Revisr on the same repository.
														- You could add this URL to another instance of Revisr in the “Revisr Webhook URL” field, or even set it up as POST hook on Bitbucket or GitHub to automate pushes and pulls according to your workflow.
													- https://help.github.com/articles/which-remote-url-should-i-use/
									- Doing commits
									  collapsed:: true
										- You'll see new stuff added marked as [untracked]
										  http://i.imgur.com/NqdAOpD.png
									- Revisr for database
									  collapsed:: true
										- See
										  https://www.sitepoint.com/revisr-git-for-wordpress/
									- Revisr as a Backup Solution
									  collapsed:: true
										- To use Revisr as an automatic backup tool, try the following settings:
											- Automatic Backups – Daily
											- Auto-push: On (if using a remote repository like Bitbucket or GitHub)
											- Tracked tables: All Tables (or select tables manually)
										- With this configuration, Revisr will automatically backup both your website files and tracked database tables once a day and push those changes to BitBucket or GitHub without any further intervention.
										- You could also use this method with an addition of a webhook to keep data on a staging server consistent with production.
									- \_See \_How to Use Commit & Push Updates using Revisr
									  #PMM-SOPs-Management https://workflowy.com/#/ffc2c496ce0d
									- _{Archive}_
									  collapsed:: true
										- gitignore
											- It is also adviseable to add Revisr to the .gitignore file via the settings page to make sure that reverts don't rollback any new functionality.
											- https://help.github.com/articles/ignoring-files/
											- Keep uploads out of repo
												- Reasons to keep uploads out of the repo
													- Uploads in the repo mean as soon as anything's uploaded your repo is out of date
													- Uploads + thumbnails = heavy repo w/ no benefit
												- Does the requested file exist in the local filesystem?
													- Yes
														- Load it as we normally would
													- No
														- Attempt to load the file from production
													- No more FTP-ing files to your dev/staging environments!
												- Apache version
													- mod_rewrite
													  wp-content/uploads/.htaccess
													- Behold: A Better Way
													  Use IfModule
														- Attempt to load files from production if they're not in our local version
														- <IfModule mod_rewrite.c>
															- RewriteEngine on
															- RewriteCond %{REQUEST_FILENAME} !-d
															- RewriteCond %{REQUEST_FILENAME} !-f
															- RewriteRule (.*) https://postmymeds.co.uk/wp-content/uploads/$1
														- </IfModule>
													- Alternative
														- <IfModule mod_rewrite.c>
														- RewriteEngine On
														- RewriteCond %{REQUEST_FILENAME} !-f [NC]
														- RewriteRule ^(.\*\.(js|css|png|jpe?g|gif|ico)) http://example.com/$1 [NC,P,L]
														- </IfModule>
														- Source: http://stackoverflow.com/questions/5130410/modrewrite-to-another-server-if-file-image-is-not-found
														- Note: If you’re working with WordPress, make sure this directive appears before the WordPress-generated rewrite rules in your .htaccess file. Otherwise, WP will catch the missing file URL and route it to a 404 internally.
												- And, here’s how to tell nginx the same thing
													- Directives to send expires headers and turn off 404 error logging.
													- location ~\* \.(js|css|png|jpe?g|gif|ico)$ {
													- expires 24h;
													- log_not_found off;
													- try_files $uri $uri/ @production;
													- }
													- location @production {
													- resolver 8.8.8.8;
													- proxy_pass http://example.com/$uri;
													- }
													- view raw
													- site.conf hosted with ❤ by GitHub
													- Source: https://github.com/aliso/vvv-site-wizard/blob/master/vvv#L383
												- 80/20 plugin version - using Amazon Offload S3 (CDN)
										- Secure access to Git repo
										  https://revisr.io/doc/securing-the-environment/
											- Once everything is setup, you’ll want to make sure that the “.git” directory isn’t directly accessible to the public (especially if using the HTTPS method to push). You can do this with Apache by adding the following .htaccess file to your .git directory:
												- content: Deny from all
											- If you initialized the repository through Revisr, Revisr will automatically add the above .htaccess file.
											- If your repository is using a “.gitignore” file, depending on the contents you may not want the file to be accessible. You can prevent direct access to the “.gitignore” file with the following code added to your .htaccess:
												- <Files .gitignore>
												- Order Allow,Deny
												- Deny from all
												- </Files>
								- VersionPress
								  collapsed:: true
									- Pros
									- Cons
										- Version 4 doesn't by default allow remote workflows (diff servers for prod/staging); requires CLI and has no GUI
											- More info
											  https://blog.versionpress.net/2016/11/remote-workflows/
											- Staging UI is hard not because the UI would be that complex but because most people on common WP hosts would not be allowed to create staging clones of their sites, or because they want to run staging sites on different servers than production sites (both of which are reasonable demands). This problem hence will not be solved in the v4 timeframe. However, we’re working on something that will make staging really simple in a controlled environment that we’re going to introduce soon.
								- https://wppusher.com/screencast
							- See [Desktop Clients](https://workflowy.com/#/fbe6150cc04c)
						- Non-Git workflow
							- _Non-Version Control file migration_
							  collapsed:: true
								- automatic rsync between directories?
								- scp over ssh can do it
								  https://www.digitalocean.com/community/questions/how-to-copy-files-from-one-server-to-another-droplet
									- scp -r /path/to/my/files root@0.0.0.0:/path/on/remote/droplet
									- Of course you will need to replace 0.0.0.0 with your new droplet's IP and update the paths included above. This command would copy everything in /path/to/my/files to the directory /path/on/remote/droplet on the other droplet.
								- Not possible via FileZilla
								- WinSCP possible using advanced mode
									- https://winscp.net/eng/docs/custom_commands#fxp
								- Linux app - PAC Manager
								  https://sourceforge.net/projects/pacmanager/
							- _Database migrate + overwrite individual tables_
							  collapsed:: true
								- Revisr
								  intralink2:: https://workflowy.com/#/f59ea55862a0
								- WP Migrate DB Pro
								  https://deliciousbrains.com/wp-migrate-db-pro/
							- _Full database merging_
							  collapsed:: true
								- Full Git is useful for pulling new files eg new plugins etc whereas VersionPress is useful for new content, plugin settings, etc
								- **VersionPress ** - Git for WordPress
								  collapsed:: true
								  Beta - files should be stable, would allow database changes which is better than normal Git
									- https://versionpress.net
									- https://github.com/versionpress/versionpress/
									- https://docs.versionpress.net/en
									- http://blog.versionpress.net/
									- https://docs.versionpress.net/en/getting-started/installation-uninstallation
								- Mergebot
								  collapsed:: true
								  Beta - for database merging
									- SaaS - $9/month in beta and requires constantly uploading all database changes on the dev site to Mergebot servers
									- https://wordpress.org/plugins/mergebot/
									- https://blog.versionpress.net/2016/08/mergebot-early-thoughts/
									- New
									  https://deliciousbrains.com/tag/mergebot/
									- https://premium.wpmudev.org/blog/mergebot-database-merging-wordpress/
								- WP Stagecoach
								  collapsed:: true
									- does do a merge but you can't work locally, it creates a staging site from the live site that you're supposed to work on. The merge works great but it's a killer blow not to be able to work locally.
					- _[Learning Resources]_
					  collapsed:: true
						- Using Git with WP
						  https://wordpress.stackexchange.com/questions/83046/is-git-github-a-good-wordpress-deployment-solution
						- Visual Git guide
						  https://marklodato.github.io/visual-git-guide/index-en.html
						- https://git-scm.com/docs
						- https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud
					- _{Archive}_
					  collapsed:: true
						- https://premium.wpmudev.org/blog/improve-wordpress-development-workflow-local-server/
						- http://stevegrunwell.github.io/wordpress-git/
							- He provides text for a recommended .gitignore file.
						- https://www.digitalocean.com/community/tutorial_series/introduction-to-git-installation-usage-and-branches
					- _Related:_
						- How to Setup a Dev Site
						  #PMM-SOPs-WebDev https://workflowy.com/#/ce8db0bad6c7
				- WordPress staging and development
				  collapsed:: true
					- https://wpstagecoach.com/
					- https://en-gb.wordpress.org/plugins/wp-staging/
					- https://www.elegantthemes.com/blog/tips-tricks/how-to-create-a-wordpress-staging-site
					- See VersionPress
				- Managing Freelancers for Web Development
				  collapsed:: true
					- Setup Dev Site
					  #SysAdmin-Dev
						- Create a subdomain (if one not available for use)
						  collapsed:: true
						  i.e. testX.postmymed.com
							- If not one available, create a new user via WHM
							- Add the subdomain on DigitalOcean networking to the server IP address
							  https://cloud.digitalocean.com/networking
						- Duplicator
						  collapsed:: true
							- Create package via original site
							  e.g. https://postmymed.com/wp-admin/admin.php?page=duplicator-pro
							- Click on Archive > Save (to PC) > Copy the filename (to use in the following command)
						- Open KiTTY to operate server
						  collapsed:: true
							- mv command + cp command
							- Move archive file to new directory. Example:
								- mv /home/**pmmcouk**/public_html/wp-content/backups-dup-pro/<b>ArchiveFullName_archive.zip</b> /home/<b>t1pmm</b>/public_html
									-
							- Copy installer file to new directory. Example:
								- cp -i /home/**pmmcouk**/public_html/wp-content/backups-dup-pro/<b>ArchiveFullName_installer.php</b> /home/<b>t1pmm</b>/public_html
									-
						- Duplicator and beyond
						  collapsed:: true
							- Duplicator setup
							  collapsed:: true
								- Go to test site address in the list below
								  e.g. http://test1.postmymed.com
									- In the file directory click on the installer.php file
								- Create a new user and STRONG password
								- Choose HTTP domain name and finalise setup
							- Login to cPanel
							  collapsed:: true
								- Delete WP Force SSL plugin via cPanel File Manager
								  (causes redirect to postmymed.com bug)
							- Clear cache
							- Open WP-Admin dashboard
							  collapsed:: true
							  e.g. http://test1.postmymed.com/wp-admin/
								- Disable Force SSL checkout
								  e.g.
								  http://test3.postmymed.com/wp-admin/admin.php?page=wc-settings&tab=checkout
								- Update 'dev' user password
								  e.g. http://test1.postmymed.com/wp-admin/user-edit.php?user_id=14&wp_http_referer=%2Fwp-admin%2Fusers.php
							- Create a PrivateBin.net with login info
							  (click here to see full note) Note: these passwords are incorrect
							  
							  WORDPRESS
							  
							  URL
							  http://test1.postmymed.com/wp-admin
							  
							  USER
							  dev
							  
							  PASSWORD
							  zU3&##isSme9#a(!5Q3ORRHp
							  
							  CPANEL
							  
							  URL
							  https://139.59.172.91:2083
							  
							  USER
							  t3pmm
							  
							  PASSWORD
							  $1(M!X1]RCCh
						- _Related: _
						  collapsed:: true
							- Dev sites currently in use
							  #PMM-SOPs-Management https://workflowy.com/#/9ddf5066c6d4
							- Duplicator
							  #PMM-Meta-Website https://workflowy.com/#/cfa2ab206dcb
							- How to setup a dev site **NEW**
							  #PMM-SOPs-WebDev https://workflowy.com/#/ce8db0bad6c7
						- **UNSORTED**
						  collapsed:: true
							- Platform
								- Windows - FileZilla
								  FileZilla unencrypted XML
							- Pre-req:
								- Secure workstation
									- Antivirus
									- Firefox + extensions
									- Disk encryption
				- ((6463499b-1d87-47ca-8775-bad033fd6636))
			- ((635036c9-08c9-47d6-ad33-98c1fc61a0dd))
		- ((6737678f-0428-47ed-a72e-9b272ffcc6c4))
		  collapsed:: true
		- Penetration Testing
		  id:: 6737677f-c9c2-46cd-ba89-5a06fe898699
		  collapsed:: true
		  AKA Ethical hacking / white hat hacking
			- See Cyber Warfare
			  #Infrastructure [A simpler way to organize your work - Workflowy](https://workflowy.com/#/d9e9b9db2377)
			- How to find public servers
				- With a fast enough connection you can do an availability check on every ipv4 address in about ten minutes from a single host using something like zmap (https://github.com/zmap/zmap). Once you've done that survey you can use something like zgrab2 (https://github.com/zmap/zgrab2) to check every active address for a given port (in this case ssh). Once you've got that you can have your botnet start trying to do logins. The second and third parts generally involve distributed work but if you're in the "logging in to random people's computers and trying to compromise them" you probably have access to a decent chunk of compute.
			- Related: ((6737678f-0428-47ed-a72e-9b272ffcc6c4))
	- ((64634999-59af-4326-82dd-d835db9ff7f7))
	- [Learning Resources]
	  collapsed:: true
		-
		- [fzf](https://github.com/junegunn/fzf)
			- a general-purpose command-line fuzzy finder.
			- [So you've installed `fzf` – now what? | Hacker News](https://news.ycombinator.com/item?id=35248098)
			-
	- Related:
		- ((63209013-7150-4d21-b323-02724c5647fd))
		- ((635036c9-08c9-47d6-ad33-98c1fc61a0dd))
		- PostMyMeds SysAdmin
		  #PMM-SOPs https://workflowy.com/#/287a71ce1ce2
- Linux internals
  id:: 6828f01e-8b60-49cf-9e5f-becd6a246cc1
  collapsed:: true
	- Directories
	  collapsed:: true
		- `/home/<user>`
		  AKA `~`
			- `~/.profile` - adding stuff to a user's bash profile is good for ensuring it'll run whenever that user logs in
		- `/etc`
			- The `/etc/skel/.profile` file is part of the skeleton directory structure in Linux, which is used to initialize a new user's home directory when the user is created using the useradd command. This file, along with other files in the /etc/skel directory, is automatically copied to the new user's home directory. The /etc/skel/.profile file typically contains shell initialization commands and environment settings that are applied when the user logs in.
			-
	- Filesystems
		- [RAMfs](https://wiki.debian.org/ramfs) is a RAM-based filesystem, useful for having an amnesic OS which only writes filesystem changes to RAM and then it resets after reboot
		- ((6360e32e-29f9-4526-ac4e-59ead71baa88))
		- ((6360e32e-f263-4cdf-8473-c5b60e05cbe7))
		- exFAT
		- ext4
		- NTFS
		- FAT32
	- `sudo`
		- `sudo -u` = let's you run commands as another user
	- Bluetooth
	  collapsed:: true
		- GATT, or the Generic ATTribute Profile, comes into play once a dedicated connection is established between two Bluetooth Low Energy (BLE) devices, meaning that the advertising process governed by the Generic Access Profile (GAP) has already been completed. This connection is exclusive, and a BLE peripheral can only be connected to one central device at a time, such as a mobile phone, until the existing connection is broken.
		- A virtual controller is a software-emulated Bluetooth device
		- Python libraries
			- [Bumble library](https://github.com/google/bumble) by Google seems to be a decent alternative to the CLI tool `bluetoothctl` which is used to interact with BlueZ, but it's documentation is very missing. API Guide webpage is empty
			- [Bleak](https://github.com/hbldh/bleak) has a lot more GitHub stars
			- Probably not suitable
				- [QtBluetooth](https://www.riverbankcomputing.com/static/Docs/PyQt6/api/qtbluetooth/qtbluetooth-module.html)
				  collapsed:: true
					- Methods
					  collapsed:: true
						- https://www.riverbankcomputing.com/static/Docs/PyQt6/api/qtbluetooth/qlowenergycontroller.html
					- Probbaly too heavyweight
				- [pybluez](https://github.com/pybluez/pybluez) - barely any updates since 2022
				  collapsed:: true
					- Can do device discovery
					- Docs are moderately detailed
					- BLE support is experimental
				- [BTZen](https://github.com/wrobell/btzen)?
				  collapsed:: true
					- Can discover and connect to devices
					- May require some configuration of bluez
					- More built towards managing smart devices
			- Check OS support, Bluetooth Low Energy support, not sure if Python code has ARM vs x86 support
		- Brave search "bluetoothctl equivalents in bleak"
	- [PipeWire](https://pipewire.org/)
	  id:: 67eab246-e845-4b95-b651-413534657429
	  collapsed:: true
		- [source](https://gitlab.freedesktop.org/pipewire/pipewire)
		- Overview
			- Aims to greatly improve handling of audio and video under Linux. It provides a low-latency, graph-based processing engine on top of audio and video devices that can be used to support the use cases currently handled by both PulseAudio and JACK. PipeWire was designed with a powerful security model that makes interacting with audio and video devices from containerized applications easy, with support for Flatpak applications [on Wayland] being the primary goal.
			- Can act as a replacement for both PulseAudio and ALSA servers.
				- Can handle user-level, not kernel-level ALSA connectivity
			-
		- Deep dive
		  collapsed:: true
			- Like JACK, PipeWire implements no connection logic internally. The burden of watching for new streams and connecting them to the appropriate output device or application is left to an external component known as a session manager.
			- [Docs](https://docs.pipewire.org/)
			  collapsed:: true
				- Overview
					- Nodes
						- Example usecase:
							- Sink (only input ports) - like headphones
							- Source (only output ports) - like microphone
				- [SPA](https://docs.pipewire.org/page_spa.html)
				- introspection tools like pw-dump
					- Can be used to see the current state of the PW server and it's capabilities. View as a collection of objects, each of which has a specific type. These objects have associated parameters, and properties, methods, events, and permissions.
			- https://gitlab.freedesktop.org/pipewire/pipewire#inspecting-the-pipewire-state lists several tools/commands that can be used to inspect PipeWire state
			- Well-known monitors include:
				- The ALSA monitor, which enables audio devices
				- The ALSA MIDI monitor, which enables MIDI devices
				- The libcamera monitor, which enables cameras
				- The Video4Linux2 (V4L2) monitor, which also enables cameras, but also other video capture devices through the V4L2 Linux API
				- The BlueZ monitor, which enables bluetooth audio devices
		- Session managers
			- WirePlumber
			  collapsed:: true
				- Recommended by [ArchWiki](https://wiki.archlinux.org/title/PipeWire). Allows configuring Bluetooth devices through rules and properties in its configuration file, providing detailed control over device settings
				- [Docs](https://pipewire.pages.freedesktop.org/wireplumber/)
				- [Configuration file](https://pipewire.pages.freedesktop.org/wireplumber/daemon/configuration/conf_file.html)
				- [TLDR](https://docs.pipewire.org/page_overview.html) It basically runs Lua scripts to manage the logic of monitoring and spawning devices (e.g. ALSA, bluez, libcamera, v4l2)
					- V4L2 AKA Video4Linux version 2. Video capture and output device API
				- Can automate [bluetooth configuration for example](https://pipewire.pages.freedesktop.org/wireplumber/daemon/configuration/bluetooth.html)
			- Piperwire
		- Packages
			- `pipewire-pulse`
				- Can replace `pulseaudio` and `pulseaudio-bluetooth`
		- Compatibility
		  collapsed:: true
			- Python support?
				- Bindings are WIP but seems to have stalled [Python bindings (#1654) · Issues · PipeWire / pipewire · GitLab](https://gitlab.freedesktop.org/pipewire/pipewire/-/issues/1654)
				- Rust bindings are official however https://gitlab.freedesktop.org/pipewire/pipewire-rs
			- Bluetooth
				- [bluez5 SPA plugin](https://github.com/PipeWire/pipewire/tree/master/spa/plugins/bluez5)
				- [Bluetooth properties](https://docs.pipewire.org/page_man_pipewire-props_7.html#props__bluetooth_properties)
					- Can change the codec, role,
				- Note: [BlueZ](https://www.bluez.org/) is the implementation of BT support on Linux, and `bluetoothctl` is the CLI for managing devices e.g. pairing
		- Wiring it up
			- Can create a [virtual device](https://gitlab.freedesktop.org/pipewire/pipewire/-/wikis/Virtual-Devices) e.g. virtual sink or source, which you can then select via WebRTC. Apps like Discord allow selecting particular these as your audio input or output
	- `systemd`
	  id:: 67b1e143-1d5d-4b5f-87a4-e35a7ae8a7d0
	  collapsed:: true
		- Services/unit files are stored in `/etc/systemd/system/` directory
		- `systemctl enable`
			- Example: `systemctl enable ssh`
		- `systemctl link` for specifying the path of service units that are not installed in the traditional system-wide service directories
		- `systemctl start`
		- `systemctl stop`
		- [Tyblog | systemd has been a complete, utter, unmitigated success](https://blog.tjll.net/the-systemd-revolution-has-been-a-success/)
		- TUIs
			- [GitHub - rgwood/systemctl-tui: A fast, simple TUI for interacting with systemd services and their logs](https://github.com/rgwood/systemctl-tui)
			- [GitHub - Lennart1978/servicemaster: Linux Systemd administration tool with nice TUI written in C](https://github.com/Lennart1978/servicemaster)
			- [GitHub - joehillen/sysz: An fzf  terminal UI for systemctl](https://github.com/joehillen/sysz)
			- [GitHub - matheus-git/systemd-manager-tui: A program for managing systemd services through a TUI (Terminal User Interfaces).](https://github.com/matheus-git/systemd-manager-tui)
			- [GitHub - isd-project/isd: isd (interactive systemd) – a better way to work with systemd units](https://github.com/isd-project/isd)
			- [GitHub - GuillaumeGomez/systemd-manager: A systemd service manager written in Rust with the GTK-rs wrapper and direct integration with dbus](https://github.com/GuillaumeGomez/systemd-manager)
		- Directories
			- Global = /lib/systemd/system/
			- User dir = ~/.config/systemd/user/
		- `systemctl status ssh` for system service `ssh`, or `systemctl --user status ssh` for user service `ssh`
		- View the Unit/Service File `systemctl cat <service-name>`
			- Displays the full configuration of the unit file, including how the service is started (ExecStart), documentation links, and mo
		- Related: ((6581601b-a5cd-4d5e-83e4-77dd49750f3c))
	- `passwd`
	  collapsed:: true
		- Don't run `sudo passwd` alone, use `sudo passwd <USERNAME>`
			- Running `sudo passwd` with no flags/options will change the password of the `root` user, since that's what `sudo` does
			- Instead use `sudo passwd <USERNAME>` to change the password of the specific user you want to edit
			- Can test whether it's worked or not by using `su root` or `su $USER` then seeing if your password is changed successfully
	- `chroot`
	  collapsed:: true
	  A way of accessing a path as a virtual filesystem
		- Example usage
			- `lostep` to create a loop device
				- `LOOPDEV=$(sudo losetup -f -P --show "${IMAGE_FILE}")
			- Other setup
				- ```shell
				  mkdir -p "${BASE}/mnt"
				  sudo e2fsck -f "${LOOPDEV}p2"
				  sudo resize2fs "${LOOPDEV}p2"
				  ```
			- `mount` it
				- ```shell
				  sudo mount -v "${LOOPDEV}p2" "${BASE}/mnt"
				  sudo mount -v -t tmpfs none "${BASE}/mnt/tmp"
				  sudo mount -v --bind /dev "${BASE}/mnt/dev"
				  ```
			- `chroot` into it
				- `sudo chroot "{BASE}/mnt" /bin/bash --login -c "run-parts --verbose --exit-on-error /tmp/workspace/setup"`
				- or
				- `sudo chroot "${BASE}/mnt" /bin/bash --login`
	- `journalctl`
	  collapsed:: true
		- `journalctl` can be used to view the journal (systemd logs only?) that's in binary format in `/var/log/journal`
		- `journalctl --reverse` - view logs in reverse order (starting from most recent entries)
	- `pgrep`
	  collapsed:: true
		- Used to search through named processes
		- Example: `pgrep 'bash'` is equivalent to `ps ax | awk '{sub(/.*\//, "", $5)} $5 ~ /bash/ {print $1}'`
	- `chpasswd` - can be used to change the password of a user
	  collapsed:: true
		- E.g. `echo 'user:userpassword' | chpasswd'
	- SELinux
	  collapsed:: true
		- Visually explore SELinux policies https://github.com/Heydarchi/SELinux-Explorer
	- ## Networking
	  id:: 6829d6c7-1c9e-44e7-95e0-d334b25d03e7
	  collapsed:: true
		- I almost went down a deep rabbit hole in the wrong direction because I didn't fully understand the networking - which TCP and unix sockets open where, what connections already exist for websocket frontend<->ADB server (on field device) comms, etc
		- SSH
		  collapsed:: true
			- `ssh`
			  id:: 6829d688-cb8a-426e-8f7b-541dfc58df52
			  collapsed:: true
				- SSH jump host AKA SSH gateway
				- SSH port forwarding AKA SSH tunneling
				  collapsed:: true
					- Is a method that allows data to be exchanged between two devices over an encrypted SSH connection.
					- Example
						- `ssh -4 -NgL 8888:localhost:5555 user@localhost`
						- -4: This option forces SSH to use IPv4 addresses only.
						- 8888:localhost:5555: This specifies the local port (8888) and the remote port (5555) along with the remote host (localhost). When you connect to port 8888 on your local machine, the traffic is forwarded to port 5555 on the remote machine.
						- user: This is the username you are logging in as on the remote machine.
						- localhost: This is the hostname or IP address of the remote machine. In this case, it's set to localhost, meaning the remote machine is the same as the local machine.
						- Flags
							- -g: Allows remote hosts to connect to local forwarded ports. This is useful when you want to allow remote hosts to connect to the forwarded ports.
							- -L: Specifies a local port forwarding. This works by allocating a socket to listen to port on the local side, and then forwarding connections to the specified remote host and port. For example, ssh -L [bind_address:]port:host:hostport can be used to forward traffic from the local machine to a remote host.
							- -N: Do not execute a remote command. This is useful for just forwarding ports or using the -D option for dynamic port forwarding.
			- `/usr/sbin/sshd -D` = start the SSH daemon in foreground detached mode (i.e. will run in the foreground and not become a background process)
			- `ssh-keyen -A` = Automatically generate host keys if they not present on the system. Usually stored in `/etc/ssh` and named `ssh_host_rsa_key`
			- Securely SSHing into a remote server
				- `ssh-keyscan IPADDRESS >> ~/.ssh/known_hosts` = queries the remote machine for it's known hosts and appends them to your file. This is useful for verifying the authenticity of the SSH host keys before proceeding with SSH key authentication
				- `sshpass -p PASSWORD ssh-copy-id -i ~/.ssh/id_ed25519 user@IPADDRESS` = `ssh-copy-id` copies the local SSH public key to the remote machine under the username specified
		- How to list all IPs on the connected network
			- `sudo apt install arp-scan`
			- `sudo arp-scan --interface=eth0 --localnet`
		- `ifconfig`
		  Deprecated, use `ip` instead?
			- `ifconfig` to get your own IP address (it's `eth0`)
		- `eth0`
		  collapsed:: true
			- In the context of tools like `ifconfig` it's the first Ethernet interface on a Linux system e.g. wired network
			- `inet` address will refer to a Docker devcontainer
		- `netcat` can be used to create unidirectional tunnels. `socat` can be used to create bidirectional tunnels
			- `netcat` can be used to create a listener on a port, two instances to create two listeners on different ports, then `socat` to join them together into a bidirectional stream
				- ```bash
				  nc -l 55545
				  nc -l 55546
				  socat tcp:localhost:55545 tcp:localhost:55546
				  ```
		- IPv6
		  collapsed:: true
			- Checking for ipv6 support
				- `test -f /proc/net/if_inet6 && echo "IPv6 supported" || echo "IPv6 not supported"`
			- Enabling IPv6
			  collapsed:: true
				- To enable it try either
					- `sudo sysctl -w net.ipv6.conf.all.disable_ipv6=0`
						- `sudo systemctl restart NetworkManager` = restart NetworkManager
					- `sudo nano /etc/sysctl.conf`
						- ```
						  net.ipv6.conf.all.disable_ipv6 = 0
						  net.ipv6.conf.default.disable_ipv6 = 0
						  net.ipv6.conf.lo.disable_ipv6 = 0
						  ```
					- `sudo nano /etc/sysconfig/network-scripts/ifcfg-eth0`
					  collapsed:: true
						- ```
						  IPV6INIT=yes
						  IPV6_AUTOCONF=yes
						  IPV6_DEFROUTE=yes 
						  IPV6_FAILURE_FATAL=no
						  ```
							- IPV6INIT=yes – This initializes the interface for IPv6 addressing.
							- IPV6_AUTOCONF=yes – This enables the IPv6 auto-configuration for the interface.
							- IPV6_DEFROUTE=yes – This indicates that the default IPv6 route has been assigned to the interface.
							- IPV6_FAILURE_FATAL=no – indicates that the system won’t fail even when IPv6 fails.
						- After adding the IPv6 configuration, you can restart the networking service using the command
							- `sudo /etc/init.d/networking restart`
							- or
							- `sudo systemctl restart networking`
							- `sudo systemctl restart NetworkManager`
					- For CentOS or similar distributions, you can edit the network configuration file
						- `sudo nano /etc/sysconfig/network`
						- set `NETWORKING_IPV6=yes`
					- `sudo nano /etc/default/grub`
						- Ensure `ipv6.disable=1` is not in `GRUB_CMDLINE_LINUX`
				- Verifying it's fixed
					- `ip -6 addr` = check if IPv6 addressing is enabled
					- `ping6 2a00:7b80:451:1::8`
					- `sudo sysctl -a | grep ipv6.*disable` to check the status of IPv6, where a value of 0 indicates that IPv6 is active and 1 indicates it is disabled.
		- Checking internet connection
		  collapsed:: true
			- `nc -zv 10.100.0.100 22` = check port 22 on that IP
			- `telnet 10.100.0.100 22` = check port 22 on that IP (TCP connection , SSH specifically)
			- `ping 10.100.0.100` = check ICMP connection
		- Network monitor
		  collapsed:: true
			- `nethogs` for per-process real-time usage speed
			- `iftop` for speed and URLs connected to
		- Using `arp-scan` to find other devices on Lane
			- `arp-scan --interface=eth0 --localnet`
		- Check what processes are using what ports `sudo lsof -i`
		- Checking if a specific port is open
		  collapsed:: true
			- [Nmap](https://nmap.org/)
				- This is a network exploration tool and security scanner. To check a specific port, you can use the command nmap -p [port-number] [address]. For example, nmap -p 443 google.com would check if port 443 is open on google.com.
			- Netcat (nc): This tool can be used to check if a port is open. The command to use is nc -vz [address] [port-number]. The -v option enables detailed output, and -z checks if the port is open without sending data.		For example, nc -vz google.com 443 would check if port 443 is open on google.com.
			- Telnet: This protocol can be used to check if a specific port is open. The command to use is telnet [address] [port-number]. For example, telnet google.com 443 would check if port 443 is open on google.com.
		- Instead of running a webserver on the cloud it's possible to run it from another device (e.g. local) then just SSH tunnel port forward it to the cloud
		- Networking
		- Checking whether a particular localhost port is accessible
		  collapsed:: true
			- nc -zv localhost 8081
			- uses netcat (often abbreviated as nc), a versatile networking utility, and here’s what each option means:
			  collapsed:: true
				- -z: Zero-I/O mode — This tells nc to just scan for listening daemons/ports without sending any actual data. It’s used for port scanning.
				- -v: Verbose mode — Makes nc output more detailed information about what it’s doing (like connection attempts, success, failure messages).
				- localhost: The host to connect to, here it means connect to your local machine.
				- 8081: The TCP port number to scan or connect to on the specified host (localhost).
		- Checking whether `adb reverse localabstract:gnirehtet tcp:31416` is working properly (`adb reverse <remote> <local>`)
		  collapsed:: true
			- Check detection of adb tunnel: `adb reverse --list` = `host-17 locabstract:gnirehtet tcp:31416`
			- To check host (local) side: `ss -ltn | grep 31416` or `netstat -an | grep 31416`
			- To check phone (remote) side: `adb shell cat /proc/net/unix | grep gnirehtet`. Have to use `cat` because it's localabstract, more restricted permissions for checking these unix sockets
		- Obtaining IP addresses:
		  collapsed:: true
			- Check all network interfaces: `ip addr show` for all, `ip addr show eth0` for just the main network
		- View the routing table to understand accessible networks: `adb shell ip route show`
		- 10.0.2.2	Emulator alias for host's localhost	Access host's localhost from emulator browser (i.e. why a HTTP server on host can be reached at http://10.0.2.2:8000 from emulator browser)
		  10.0.2.15	Emulator device's own IP	Actual emulator IP on its virtual network (i.e. what shows up when you run `adb shell ip addr show`
		- WireShark is great for checking whether network requests are working in real-time
		  Useful for even monitoring DevContainers within WSL connecting to an Android emulator within the DevContainer
		- `nc -zv localhost 8081`
		- uses netcat (often abbreviated as nc), a versatile networking utility, and here’s what each option means:
		  collapsed:: true
			- -z: Zero-I/O mode — This tells nc to just scan for listening daemons/ports without sending any actual data. It’s used for port scanning.
			- -v: Verbose mode — Makes nc output more detailed information about what it’s doing (like connection attempts, success, failure messages).
			- localhost: The host to connect to, here it means connect to your local machine.
			- 8081: The TCP port number to scan or connect to on the specified host (localhost).
		- Checking whether `adb reverse localabstract:gnirehtet tcp:31416` is working properly (`adb reverse <remote> <local>`)
		  collapsed:: true
			- Check detection of adb tunnel: `adb reverse --list` = `host-17 locabstract:gnirehtet tcp:31416`
			- To check host (local) side: `ss -ltn | grep 31416` or `netstat -an | grep 31416`
			- To check phone (remote) side: `adb shell cat /proc/net/unix | grep gnirehtet`. Have to use `cat` because it's localabstract, more restricted permissions for checking these unix sockets
		- Obtaining IP addresses:
		  collapsed:: true
			- Check all network interfaces: `ip addr show` for all, `ip addr show eth0` for just the main network
			- View the routing table to understand accessible networks: `adb shell ip route show`
			- 10.0.2.2	Emulator alias for host's localhost	Access host's localhost from emulator browser (i.e. why a HTTP server on host can be reached at http://10.0.2.2:8000 from emulator browser)
			- 10.0.2.15	Emulator device's own IP	Actual emulator IP on its virtual network (i.e. what shows up when you run `adb shell ip addr show`
			- WireShark is great for checking whether network requests are working in real-time
			- Useful for even monitoring DevContainers within WSL connecting to an Android emulator within the DevContainer
		- `nslookup` on a Windows host (e.g. in PowerShell) prints your DNS name and IP address
		- port forwarding is used to direct incoming traffic from the internet to a specific device within a local network, while reverse port forwarding (AKA revese tunneling) is used to create a secure connection from a remote server to a local machine, allowing the local machine to be accessed from the internet.
	- Related: ((673767a8-4dad-4c2e-84d3-02256c35a3a9))
- Architectures
	- ARM
	  collapsed:: true
		- Figuring out how to run STF
			- Found out the STF packages are ARM-based, which means I can't test STF in the Ubuntu VM nor WSL
			- Also can't run ARM guest Raspberry Pi image in VMware or VirtualBox unless I'm using an ARM host
			- Realised Tim created a launch.sh for launching it via QEMU
		- Difficult to get Python packages on a x86 machine to be used on an ARM machine. Better to get source instead of wheel (binary)?
	- x86
- [Learning Resources]
  id:: 63a9bb62-9f2b-4487-8b01-47ecd334ed2d
  collapsed:: true
	- _cPanel doesn't work well with AWS_
	  collapsed:: true
		- can't be used with RDS as cPanel requires super priveleges in order to support older databases and RDS doesn't allow that
		  source:: Jan 17 https://features.cpanel.net/topic/support-for-aws-rds-as-remote-mysql-server#comment-50954
		- Failover instances can't be administered via cPanel
	- _Discovery_
		- Market share
		  https://www.datanyze.com/market-share
		- BuiltWith
	- https://www.datanyze.com/market-share/accelerators/
	- https://www.datanyze.com/market-share/email-marketing/Alexa%20top%201K
	- https://www.datanyze.com/market-share/analytics/Alexa%20top%201K
	- https://www.datanyze.com/market-share/publisher-advertising-tools/
	- https://www.datanyze.com/market-share/customer-relationship-management/
	- https://www.datanyze.com/market-share/ad-servers/
	- https://www.datanyze.com/market-share/marketing-automation/
	- https://www.datanyze.com/market-share/retargeting/
	- https://www.datanyze.com/market-share/search-marketing/
- Related:
	- ((6336ac7d-9081-4a23-b7e5-0474a8023b4d)) : Easy app deployment