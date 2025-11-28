tags:: [[Programming]]
isbn:: NA
date:: 2017
publisher:: O'Reilly Media Inc.
language:: NA
authors:: [[Martin Kleppmann]]
format:: [epub](/home/boss/Vaults/gocryptfs1/Calibre/Calibre-Library/Martin Kleppmann/Designing Data-Intensive Applications (1536)/Designing Data-Intensive Applications - Martin Kleppmann.epub)

- [[Synopsis]]
	- 9781491903117
- [Designing Data-Intensive Applications](calibre://show-book/Calibre-Library/1536)  {{renderer calibreViewer, special, http://localhost:3296/#book_id=1536&fmt=epub&library_id=Calibre-Library&mode=read_book}} {{renderer calibreHighlight, false, 2000, http://localhost:3296, Calibre-Library, 1536, epub}}
  lastsync:: Sat Oct 28 2023 22:35:29 GMT+0100 (British Summer Time)
	- https://dataintensive.net/
	- Intro
	  collapsed:: true
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/12/2/4/2/2[preface]/8/8/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} CPU clock speeds are barely increasing, but multi-core processors are standard, and networks are getting faster. This means parallelism is only going to increase.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/12/2/4/2/2[preface]/8/2/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Internet companies such as Google, Yahoo!, Amazon, Facebook, LinkedIn, Microsoft, and Twitter are handling huge volumes of data and traffic, forcing them to create new tools that enable them to efficiently handle such scale.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/12/2/4/2/2[preface]/10/2:99%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} We call an application data-intensive if data is its primary challenge—the quantity of data, the complexity of data, or the speed at which it is changing—as opposed to compute-intensive, where CPU cycles are the bottleneck.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/12/2/4/2/2[preface]/12/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} The tools and technologies that help data-intensive applications store and process data have been rapidly adapting to these changes. New types of database systems (“NoSQL”) have been getting lots of attention, but message queues, caches, search indexes, frameworks for batch and stream processing, and related technologies are very important too.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/12/2/4/2/2[preface]/16/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Fortunately, behind the rapid changes in technology, there are enduring principles that remain true, no matter which version of a particular tool you are using. If you understand those principles, you’re in a position to see where each tool fits in, how to make good use of it, and how to avoid its pitfalls. That’s where this book comes in.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/12/2/4/2/2[preface]/24/2[idm140605786354848]/4/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} If you develop applications that have some kind of server/backend for storing or processing data, and your applications use the internet (e.g., web applications, mobile apps, or internet-connected sensors), then this book is for you.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/12/2/4/2/2[preface]/26/2[sec_preface_scope]/6/1:446%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Alternatively, you can find all of the references at https://github.com/ept/ddia-references, where we maintain up-to-date links
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/12/2/4/2/2[preface]/26/2[sec_preface_scope]/8/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} We look primarily at the architecture of data systems and the ways they are integrated into data-intensive applications. This book doesn’t have space to cover deployment, operations, security, management, and other areas
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/12/2/4/2/2[preface]/28/2[idm140605786018704]/4/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} This book is arranged into three parts
		-
	- # {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/14/2/4/2[part_foundations]/2/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Part 1: Foundations of Data Systems
		- Summary: We discuss the fundamental ideas that underpin the design of data-intensive applications. The first four chapters go through the fundamental ideas that apply to all data systems, whether running on a single machine or distributed across a cluster of machines
		- ## Chapter 1
			- Summary
			  collapsed:: true
				- discussing what we’re actually trying to achieve: reliability, scalability, and maintainability; how we need to think about them; and how we can achieve them. In
				- Chapter 1 introduces the terminology and approach that we’re going to use throughout this book. It examines what we actually mean by words like reliability, scalability, and maintainability, and how we can try to achieve these goals.
			- ### Intro
			  collapsed:: true
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/8/2[idm140605786449728]:1%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Many applications today are data-intensive, as opposed to compute-intensive. Raw CPU power is rarely a limiting factor for these applications—bigger problems are usually the amount of data, the complexity of data, and the speed at which it is changing.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/10/2[idm140605786447520]:1%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} A data-intensive application is typically built from standard building blocks that provide commonly needed functionality. For example, many applications need to:
					- Store data so that they, or another application, can find it again later (databases)
					- Remember the result of an expensive operation, to speed up reads (caches)
					- Allow users to search data by keyword or filter it in various ways (search indexes)
					- Send a message to another process, to be handled asynchronously (stream processing)
					- Periodically crunch a large amount of accumulated data (batch processing)
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/20/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} In this chapter, we will start by exploring the fundamentals of what we are trying to achieve: reliable, scalable, and maintainable data systems
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/22/2[idm140605786434544]/6/1:3%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} why should we lump them all together under an umbrella term like data systems?
				- Many new tools for data storage and processing have emerged in recent years. They are optimized for a variety of different use cases, and they no longer neatly fit into traditional categories [1]. For example, there are datastores that are also used as message queues (Redis), and there are message queues with database-like durability guarantees (Apache Kafka). The boundaries between the categories are becoming blurred.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/22/2[idm140605786434544]/4/2[idm140605786432976]:1%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} We typically think of databases, queues, caches, etc. as being very different categories of tools. Although a database and a message queue have some superficial similarity—both store data for some time—they have very different access patterns, which means different performance characteristics, and thus very different implementations.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/22/2[idm140605786434544]/10/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Secondly, increasingly many applications now have such demanding or wide-ranging requirements that a single tool can no longer meet all of its data processing and storage needs. Instead, the work is broken down into tasks that can be performed efficiently on a single tool, and those different tools are stitched together using application code.
				  
				  For example, if you have an application-managed caching layer (using ((64634999-fc4a-4bf0-9d74-f8dc23708311)) or similar), or a full-text search server (such as Elasticsearch or Solr) separate from your main database, it is normally the application code’s responsibility to keep those caches and indexes in sync with the main database.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/22/2[idm140605786434544]/16/2[idm140605786235728]:1%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} When you combine several tools in order to provide a service, the service’s interface or application programming interface (API) usually hides those implementation details from clients. Now you have essentially created a new, special-purpose data system from smaller, general-purpose components.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/22/2[idm140605786434544]/18/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} If you are designing a data system or service, a lot of tricky questions arise. How do you ensure that the data remains correct and complete, even when things go wrong internally? How do you provide consistently good performance to clients, even when parts of your system are degraded? How do you scale to handle an increase in load? What does a good API for the service look like?
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/22/2[idm140605786434544]/22/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} In this book, we focus on three concerns that are important in most software systems:
				  collapsed:: true
					- Reliability
						- The system should continue to work correctly (performing the correct function at the desired level of performance) even in the face of adversity (hardware or software faults, and even human error). See “Reliability”.
					- Scalability
						- As the system grows (in data volume, traffic volume, or complexity), there should be reasonable ways of dealing with that growth. See “Scalability”.
					- Maintainability
						- Over time, many different people will work on the system (engineering and operations, both maintaining current behavior and adapting the system to new use cases), and they should all be able to work on it productively. See “Maintainability”.
			- ### {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Reliability
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/4/2[ix_reliable]:98%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} For software, typical expectations include:
					- The application performs the function that the user expected.
					- It can tolerate the user making mistakes or using the software in unexpected ways.
					- Its performance is good enough for the required use case, under the expected load and data volume.
					- The system prevents any unauthorized access and abuse.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/8/1:60%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} we can understand reliability as meaning, roughly, “continuing to work correctly, even when things go wrong.”
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/10/2[idm140605786205920]:5%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} things that can go wrong are called faults, and systems that anticipate faults and can cope with them are called fault-tolerant or resilient.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/12/2[idm140605786201696]:1%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Note that a fault is not the same as a failure [2]. A fault is usually defined as one component of the system deviating from its spec, whereas a failure is when the system as a whole stops providing the required service to the user. It is impossible to reduce the probability of a fault to zero; therefore it is usually best to design fault-tolerance mechanisms that prevent faults from causing failures.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/14/2[idm140605786196368]:2%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Counterintuitively, in such fault-tolerant systems, it can make sense to increase the rate of faults by triggering them deliberately—for example, by randomly killing individual processes without warning. Many critical bugs are actually due to poor error handling [3]; by deliberately inducing faults, you ensure that the fault-tolerance machinery is continually exercised and tested, which can increase your confidence that faults will be handled correctly when they occur naturally. The Netflix Chaos Monkey [4] is an example of this approach.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/34/10[netflix-simian-army]/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} [4] Yury Izrailevsky and Ariel Tseitlin: “The Netflix Simian Army,” techblog.netflix.com, July 19, 2011.
				- #### {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/18/2[idm140605786186832]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Hardware Faults
				  collapsed:: true
					- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/18/2[idm140605786186832]/4/2[idm140605786185392]:86%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Hard disks crash, RAM becomes faulty, the power grid has a blackout, someone unplugs the wrong network cable
					- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/18/2[idm140605786186832]/8/2[idm140605786173600]:2%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Our first response is usually to add redundancy to the individual hardware components in order to reduce the failure rate of the system. Disks may be set up in a RAID configuration, servers may have dual power supplies and hot-swappable CPUs, and datacenters may have batteries and diesel generators for backup power
					- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/18/2[idm140605786186832]/14/2[idm140605786159024]:6%29&fmt=epub&library_id=Calibre-Library&mode=read_book }}  there is a move toward systems that can tolerate the loss of entire machines, by using software fault-tolerance techniques in preference or in addition to hardware redundancy. Such systems also have operational advantages: a single-server system requires planned downtime if you need to reboot the machine (to apply operating system security patches, for example), whereas a system that can tolerate machine failure can be patched one node at a time, without downtime of the entire system (a rolling upgrade; see Chapter 4).
				- #### {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/20/2[idm140605786156304]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Software Errors
				  collapsed:: true
					- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/20/2[idm140605786156304]/6/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Another class of fault is a systematic error within the system [8]. Such faults are harder to anticipate, and because they are correlated across nodes, they tend to cause many more system failures than uncorrelated hardware faults [5]. Examples include:
					  
					  A software bug that causes every instance of an application server to crash when given a particular bad input. For example, consider the leap second on June 30, 2012, that caused many applications to hang simultaneously due to a bug in the Linux kernel [9].
					  
					  A runaway process that uses up some shared resource—CPU time, memory, disk space, or network bandwidth.
					  
					  A service that the system depends on that slows down, becomes unresponsive, or starts returning corrupted responses.
					  
					  Cascading failures, where a small fault in one component triggers a fault in another component, which in turn triggers further faults [10].
					- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/34/12[Ford2010vv]/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} [5] Daniel Ford, François Labelle, Florentina I. Popovici, et al.: “Availability in Globally Distributed Storage Systems,” at 9th USENIX Symposium on Operating Systems Design and Implementation (OSDI), October 2010.
					- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/34/20[Minar2012vh_ch1]/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} [9] Nelson Minar: “Leap Second Crashes Half the Internet,” somebits.com, July 3, 2012.
					  
					  [10] Amazon Web Services: “Summary of the Amazon EC2 and Amazon RDS Service Disruption in the US East Region,” aws.amazon.com, April 29, 2011.
					- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/20/2[idm140605786156304]/12/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} There is no quick solution to the problem of systematic faults in software. Lots of small things can help: carefully thinking about assumptions and interactions in the system; thorough testing; process isolation; allowing processes to crash and restart; measuring, monitoring, and analyzing system behavior in production. If a system is expected to provide some guarantee (for example, in a message queue, that the number of incoming messages equals the number of outgoing messages), it can constantly check itself while it is running and raise an alert if a discrepancy is found [12].
					- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/34/26[Kreps2012td_ch1]/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} [12] Jay Kreps: “Getting Real About Distributed System Reliability,” blog.empathybox.com, March 19, 2012.
				- #### {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/22/2[idm140605786126144]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Human Errors
				  collapsed:: true
					- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/22/2[idm140605786126144]/4/2[idm140605786125024]:197%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} one study of large internet services found that configuration errors by operators were the leading cause of outages, whereas hardware faults (servers or network) played a role in only 10–25% of outages [13].
					- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/34/28[Oppenheimer2003vc]/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} [13] David Oppenheimer, Archana Ganapathi, and David A. Patterson: “Why Do Internet Services Fail, and What Can Be Done About It?,” at 4th USENIX Symposium on Internet Technologies and Systems (USITS), March 2003.
					- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/24/2[sec_introduction_reliability]/22/2[idm140605786126144]/6/1:68%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} The best systems combine several approaches:
						- Design systems in a way that minimizes opportunities for error. For example, well-designed abstractions, APIs, and admin interfaces make it easy to do “the right thing” and discourage “the wrong thing.” However, if the interfaces are too restrictive people will work around them, negating their benefit, so this is a tricky balance to get right.
						- Decouple the places where people make the most mistakes from the places where they can cause failures. In particular, provide fully featured non-production sandbox environments where people can explore and experiment safely, using real data, without affecting real users.
						- Test thoroughly at all levels, from unit tests to whole-system integration tests and manual tests [3]. Automated testing is widely used, well understood, and especially valuable for covering corner cases that rarely arise in normal operation.
						- Allow quick and easy recovery from human errors, to minimize the impact in the case of a failure. For example, make it fast to roll back configuration changes, roll out new code gradually (so that any unexpected bugs affect only a small subset of users), and provide tools to recompute data (in case it turns out that the old computation was incorrect).
						- Set up detailed and clear monitoring, such as performance metrics and error rates. In other engineering disciplines this is referred to as telemetry. (Once a rocket has left the ground, telemetry is essential for tracking what is happening, and for understanding failures [14].) Monitoring can show us early warning signals and allow us to check whether any assumptions or constraints are being violated. When a problem occurs, metrics can be invaluable in diagnosing the issue.
						- Implement good management practices and training—a complex and important aspect, and beyond the scope of this book.
			- ### {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/16/2/4/2/2[ch_introduction]/26/2[sec_introduction_scalability]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Scalability
		- ## Chapter 2
		  collapsed:: true
			- Chapter 2 compares several different data models and query languages—the most visible distinguishing factor between databases from a developer’s point of view. We will see how different models are appropriate to different situations.
			- Summary: we compare several different data models and query languages, and see how they are appropriate to different situations. In
		- ## Chapter 3
		  collapsed:: true
			- Chapter 3 turns to the internals of storage engines and looks at how databases lay out data on disk. Different storage engines are optimized for different workloads, and choosing the right one can have a huge effect on performance.
			- Summary: Storage engines: how databases arrange data on disk so that we can find it again efficiently.
		- ## Chapter 4
		  collapsed:: true
			- Chapter 4 compares various formats for data encoding (serialization) and especially examines how they fare in an environment where application requirements change and schemas need to adapt over time.
			- Summary: Formats for data encoding (serialization) and evolution of schemas over time.
	- # Part 2
	  collapsed:: true
		- In Part II, we move from data stored on one machine to data that is distributed across multiple machines. This is often necessary for scalability, but brings with it a variety of unique challenges. We first discuss replication (Chapter 5), partitioning/sharding (Chapter 6), and transactions (Chapter 7). We then go into more detail on the problems with distributed systems (Chapter 8) and what it means to achieve consistency and consensus in a distributed system (Chapter 9).
	- # Part 3
	  collapsed:: true
		- We discuss systems that derive some datasets from other datasets. Derived data often occurs in heterogeneous systems: when there is no one database that can do everything well, applications need to integrate several different databases, caches, indexes, and so on
		- ## Chapter 10
			- In Chapter 10 we start with a batch processing approach to derived data, and
		- ## Chapter 11
			- we build upon last chapter with stream processing
		- ## Chapter 12
			- Summary: We put everything together and discuss approaches for building reliable, scalable, and maintainable applications in the future.
	- [Learning Resources]
	  collapsed:: true
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/12/2/4/2/2[preface]/32/2[idm140605785997888]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} [O’Reilly Safari](http://oreilly.com/safari)
		  collapsed:: true
			- Safari (formerly Safari Books Online) is a membership-based training and reference platform for enterprise, government, educators, and individuals.
			  
			  Members have access to thousands of books, training videos, Learning Paths, interactive tutorials, and curated playlists from over 250 publishers, including O’Reilly Media, Harvard Business Review, Prentice Hall Professional, Addison-Wesley Professional, Microsoft Press, Sams, Que, Peachpit Press, Adobe, Focal Press, Cisco Press, John Wiley & Sons, Syngress, Morgan Kaufmann, IBM Redbooks, Packt, Adobe Press, FT Press, Apress, Manning, New Riders, McGraw-Hill, Jones & Bartlett, and Course Technology, among others.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1536&bookpos=epubcfi%28/12/2/4/2/2[preface]/34/2[idm140605786396256]/8/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} We have a web page for this book, where we list errata, examples, and any additional information. You can access this page at [Designing Data-Intensive Applications [Book]](http://bit.ly/designing-data-intensive-apps.)
		  
		  To comment or ask technical questions about this book, send email to bookquestions@oreilly.com.
		  
		  For more information about our books, courses, conferences, and news, see our website at [O'Reilly Media - Technology and Business Training](http://www.oreilly.com.)
		  
		  Find us on Facebook: [Facebook](http://facebook.com/oreilly)
		  
		  Follow us on Twitter: http://twitter.com/oreillymedia
		  
		  Watch us on YouTube: [Error 403 (Forbidden)!!1](http://www.youtube.com/oreillymedia)