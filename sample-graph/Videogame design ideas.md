- _Games software stack_
  collapsed:: true
  id:: 635593ab-520f-40f0-9729-ce8b6c8f5612
	- _Priority stack_
		- Houdini for asset creation
		- Houdine Engine plugin for a game engine (ideally Godot)
		    intralink2:: https://workflowy.com/#/915ba038ffa2
		- Substance Designer/Painter for texturing (if necessary, Houdini might fit usecase)
		- Voxel Farm plugin for game engine (Unity or Unreal)
			- Otherwise have to take an existing voxel engine and implement Dual Contouring/Surface Nets; and all the other things modern game engines implement to save performance
	- FOSS development to encourage
	  collapsed:: true
		- Features
			- SpatialOS-like unlimited players multiplayer
			    Not possible for FOSS projects - too big a feature + costly hosting. Likely requires Kubernetes, Bullet/Ammo server etc
			- Voxel Farm-like voxel game engine
		- Projects
			- See FOSS, especially:
			    intralink2:: https://workflowy.com/#/f81f6bef8cbc
				- FOSS [Minecraft](https://workflowy.com/#/v_aae130f17e85_d1f0835fa2b6_6e16c8126dfe4782) clones for voxel features
	- _Networking for MMOs in a single universe (netcode)_
	  collapsed:: true
		- Keywords
			- Distributed physics
			- Distributed spatial simulation
			- distributed simulation architectures
			- Distributed computing for games
			- Distributed operating system with load balancing
		- Components
		  collapsed:: true
			- FOSS aspects
			  collapsed:: true
				- CoE's Soulborn Engine stack
				    intralink2:: https://workflowy.com/#/c25b78bb7409
				- Messaging solutions
				  collapsed:: true
					- gRPC v RabbitMQ v GraphQL
					  collapsed:: true
						- gRPC v RabbitMQ v GraphQL
							- gRPC-Web:
								- Speaks protocol buffers, a fast and compact format compared to JSON
								- Allows clients to use the same APIs as backend services.
							- GraphQL:
								- Enables a client-centric view of the system. I have abstractions in my GraphQL server that only make sense to clients. It's a query-centric implementation of the Backend-for-frontend pattern, where the owners of the service are also the consumers.
								- Enables an entire UI's requirements to be fetched in one go (or optionally split up, if some content is less important). To achieve the same level of aggregation performance in gRPC would require building something analogous to GraphQL.
							- The other benefits of gRPC-Web outlined in the article (generating typescript bindings) are equally possible with GraphQL (Relay Modern generates flow types, and is probably just one pull request from supporting TypeScript too)
							- The status code standardisation only makes sense for single-purpose endpoints/calls, once you're dealing with aggregations, the semantics of a downstream status code will vary depending on the use case the query fulfills.
							- I think both solutions have use cases, and can even happily co-exist. I don't believe gRPC-Web to be as much of a game-changer as GraphQL, but for certain scenarios (needing to rapidly fetch streams of data that don't have cross-dependencies) I can definitely see the benefits of a solution based on gRPC.
						- Chronicles of Elyria is using RabbitMQ somehow
					- RabbitMQ
					  collapsed:: true
					    super fast routing and message protocol used to serve 10's of millions of requests by banks and other high-traffic websites across the internet each day
						- CoE using to communicate between non-spatial and spatial data services
						    intralink2:: https://workflowy.com/#/c25b78bb7409
					- https://stackoverflow.com/questions/3164821/amqp-or-xmpp-for-real-time-online-games
					- Pub/Sub
					  collapsed:: true
						- https://pdfs.semanticscholar.org/89f3/1fa3876d44f983197df593ad69834483d0a1.pdf
						- (I'm not trying to discuss the merits/drawbacks of UDP vs TCP, I understand the differences and the overhead concerns for low latency networks.  And I'm aware that most pub/sub systems use TCP, which makes it immediately unpalatable to most game server designers
						- MQTT
						  collapsed:: true
						    http://mqtt.org/
							- it's a lightweight pub/sub messaging system that is designed for reliability, speed and minimal code footprint, mostly used in the IoT realm currently.
						- ZeroMQ
				- _Databases (e.g. for spatial data)_
				  collapsed:: true
					- _Notes:_
					  collapsed:: true
						- Databases main
						    #Software https://workflowy.com/#/bbb23c2e267c
						- Noteworthy: other MMOs DBs
						  collapsed:: true
							- Microsoft SQL - used by Eve Online, Guild Wars
							  collapsed:: true
							    <$5k/mo for EVE's DB server
								- EVE Online uses Microsoft SQL
								- EVE's db server
								    https://www.eveonline.com/article/tranquility-tech-iii-one-year-anniversary
								- Guild Wars used MSSQL, 2k tx/sec normally, up to 5k tx
								    source:: https://www.dbms2.com/2007/06/09/the-database-technology-of-guild-wars/
							- Farmville uses membase, which they made for the purpose, based on memcached apparently
						- CoE plan to use PostgreSQL and PostGIS for spatial data
						- You should have a game server that manages the spatial lookups, the script invocations, and so on
						  collapsed:: true
							- You should have a game server that manages the spatial lookups, the script invocations, and so on. It would only need to go out to the database rarely (maybe every few seconds) to persist state changes to the world, and you'd only ever need to read back from the data layer when starting up a new server instance.
							- If all your "game" is is a giant database, then sure, you could just use a typical database's cache in RAM functions
							- But as soon as you have to integrate actual game logic with this separate data system, you will hurt in the long run. The problem with externalizing all your storage is predominantly access latency. Unless every game server is also a database shard server (waste of hardware) you will have to hit the network to grab every single piece of data you want. Now you have an unreliability concern and a latency problem - expect on the order of a couple milliseconds for every data fetch instead of microseconds at worst. Plus, if your network flakes or a database server goes down, you're screwed; in a persistence-only model, you just keep on chugging and hit the data store as soon as it becomes available again.
							- Building scalable, performant systems is often counterintuitive. "Rolling your own" may be a sin when you're talking about linked list classes, but when it comes to building an MMO, you need to have very domain-specific solutions. Integrating with a data store back-end is fine, but building everything around off-the-shelf middleware is a surefire way to kill yourself as soon as you hit scale.
					- **Spatial databases<**
					  collapsed:: true
						- _Data in use (anything which is relevant for current gameplay) should be in the game-server's memory for fast access._
						  collapsed:: true
							- A good database system should be able to handle caching things in RAM just fin
							- You wouldn't store the positions of any currently ingame-players in a MySQL database. Databases are for data at rest, not for data in use. You would use a database to persist the state of player-characters when they go offline and retrieve it again when they come online again. Data in use (anything which is relevant for current gameplay) should be in the game-server's memory for fast access.
							- Note: keep the entire size of your DB in RAM and it's effectively the same as an in-memory DB that way
							- You should use the data layer for persistence only, and do your nontrivial logic up in the game logic itself.
						- _SQL_
						  collapsed:: true
							- PostgreSQL
							  collapsed:: true
								- supports SQL, NoSQL, and even spatial queries (via PostGIS), enabling it to act as a backend and persistent storage for both our spatial and non-spatial data.
								  collapsed:: true
									- PostGIS
							- MariaDB has a spatial database
							  collapsed:: true
								- https://mariadb.com/kb/en/library/geographic-geometric-features/
						- NoSQL
						  collapsed:: true
						    #Software https://workflowy.com/#/de222e24ddce
							- _Document_
							  collapsed:: true
								- Apache CouchDB
								- ((63a9bb6d-2e04-4815-b3f1-d9e67b471066))
						- In-memory
						  collapsed:: true
							- ((6607f722-b674-4037-af49-e03bafebc259)) is not RAM, it's network-attached-RAM, which is an order of magnitude less efficient than co-locating the RAM with the routing/signaling server
							- ((6607f722-b674-4037-af49-e03bafebc259))
							  collapsed:: true
							    with the Geo API
								- https://www.gamedev.net/blogs/entry/2265641-in-memory-key-value-databases-redis-initial-evaluation/
							- And if you must back it up with a database, run an upsert on it every few minutes.
						- _Distributed databases_
						  collapsed:: true
							- Postgres-XL (distributed cluster version)
							  collapsed:: true
								- https://www.postgres-xl.org/
							- https://en.wikipedia.org/wiki/Spatial_database#Table_of_free_systems_especially_for_spatial_data_processing
					- _Sharded databases (for spatial info - makes it like psuedo-SpatialOS)_
					  collapsed:: true
					    I would do something like have shards that hold limited information of a geographical area (e.g. positions of player). Only certain regions would be replicated (e.g. neighbouring regions). A simulation client that runs external to the database but on the same local machine would do the simulation and update the shards.
						- MongoDB
						- MySQL Cluster
				- SpatialOS FOSS components
				    intralink2:: https://workflowy.com/#/b7120ab3b3eb
				- yojimbo (built for 64 player, not MMO)
				  collapsed:: true
				    https://github.com/networkprotocol/yojimbo
					- Uses UDP
					- ((63542965-aaa8-4872-b7bb-026c76092669)) may integrate it
					  collapsed:: true
						- Star Citizen sponsors it
						    https://github.com/networkprotocol/libyojimbo/blob/master/README.md
						- Game fans like the technical background of yojimbo
						    https://forums.starcitizenbase.com/topic/20145-netcode-theorycraft-why-did-cig-donate-2500-to-a-retired-network-engineer/
					- Author: Glenn Fiedler
					    https://gafferongames.com/about
				- Telepathy & Mirror
				  collapsed:: true
					- MMO Scale Networking via Mirror & Telepathy
					- Telepathy - TCP networking in C#
					  collapsed:: true
					    https://github.com/vis2k/Telepathy
						- "UDP vs. TCP: Minecraft and World of Warcraft are two of the biggest multiplayer games of all time and they both use TCP networking. There is a reason for that." - is their reasoning
						  collapsed:: true
							- But then they can't do a single-shard world, so they could be wrong
						- Note: yojimbo uses UDP
						- https://docs.google.com/document/d/e/2PACX-1vQqf_iqOLlBRTUqqyor_OUx_rHlYx-SYvZWMvHGuLIuRuxJ-qX3s8JzrrBB5vxDdGfl-HhYZW3g5lLW/pub#h.h4wha2mpetsc
						- However they used SQLite and a mid-spec server for their test, which could be why it didn't perform as well as it could have
					- Mirror - high level Networking API for Unity, built on top of the low level Telepathy library.
					    https://github.com/vis2k/Mirror
					- 200 players in one place but apparently laggy
					    https://youtu.be/Utl-dYShJAY
				- Photon Unity Networking
			- Proprietary
				- Replication Graph for ((635593ab-2437-42be-b560-b9628e19a174))
				  collapsed:: true
					- https://forum.unity.com/threads/replication-graph.593392/
					- https://www.unrealengine.com/en-US/tech-blog/replication-graph-overview-and-proper-replication-methods
					- https://docs.unrealengine.com/en-US/Engine/Networking/ReplicationGraph
					  collapsed:: true
						- The Replication Graph Plugin is a system for network replication in multiplayer games that is designed to scale well with large numbers of players and replicated Actors. As an example, Epic's own Fortnite Battle Royale starts each game with 100 connected players and about 50,000 replicated Actors.
					- Video doc
					    https://youtu.be/CDnNAAzgltw
					-
				- Huge scaling for Unity Engine
				  collapsed:: true
					- Expected to launch in Q1/2 2019
					    https://forum.unity.com/threads/unet-deprecation-thread.543501/
					- Forum section for multiplayer networking
					  collapsed:: true
					    https://forum.unity.com/forums/connected-games.26/
						- Forum ECS
						    https://forum.unity.com/forums/entity-component-system-and-c-job-system.147/
					- Feature overview
					    https://unity.com/solutions/real-time-multiplayer/network-transport-layer
					- Announcement - Work on it started in 2018
					    https://blogs.unity3d.com/2018/08/02/evolving-multiplayer-games-beyond-unet/
					- Forum mod confirms it's on the roadmap
					    https://forum.unity.com/threads/replication-graph.593392/
			- _Spatial simulation_
			  collapsed:: true
			    Suited for MMOs or large 3D worlds
				- Pros/Cons
					- Pros
					  collapsed:: true
						- For 3D single-shard MMOs it's necessary because otherwise simulation has greater latency as you have to communicate more slowly via networking rather than NUMA RAM
						  collapsed:: true
							- My experience from massive simulations is that any attempt to "overlay" simulations (not clustering them geographically) will fail to scale, because the communications overhead (networking) is orders of magnitude higher latency and lower bandwidth than NUMA RAM. Giant persistent worlds are totally possible, and have been built for 20 years, but they all end up sharding by geography and replicating entities across shard borders in one way or another.
							- If you don't need any kind of physical simulation or physically-based rules (enemy targeting, spells, meelee combat, etc) then you can probably go with a fully sharded "web style" network topology, but then, what would your game be? The world can only see so many Hearthstones or Clash of Clans.
							- Anyway, I say ((6607f722-b674-4037-af49-e03bafebc259)) is great, because I've used it for a number of different use cases, and I've seen several other companies use it, and it's great as long as you stay within a single machine. Once you need a cluster of machines, many of the things that are good about Redis, such as transactional cross-key updates, stop working. If all you use is pub/sub, and you shard the pub/sub key space across separate Redis instances, that can scale higher, but it has the draw-back that you get NxM network connections -- each interested subscriber process needs to connect to each Redis instance, and because both Redis and subscribers scale by number of players, it ends up growing as O(N-squared) albeit with a very small "k" value.
					- Cons
					  collapsed:: true
						- Difficult to create
						- By the time you need such low latency/high tps you'll already have the profit margins to hire the team for it
						  collapsed:: true
							- You talk of multiple servers, and you also talk as though you are a single individual.
							- Pick a solution that fits your actual problem.  People pick something that is high performance for a different industry but terrible for games, or that scales to support thousands of machines when they won't ever need it.
							- Consider your game at its most successful, but while still small enough to not hire anybody. How many transactions per second will it need to support?
							- Realistically, for many games the peak rate is a single digit number of tiny transactions per second.  Even if the game were to become successful and make enough money to start hiring additional programmers, the peak rate for thousands of users can reach tens of transactions per second.
							- Typically games don't realistically need clusters of servers until they're also large enough to have large teams of developers.  When they grow to that point it is easy enough to hire somebody to write that code.  If your game is small enough you can't hire people to write and maintain databases, then it is also small enough that you don't really need that technology.
							- And if you're the person hired to add that to a game that is large enough to require such a cluster, you likely don't need that kind of tech until you are reaching a thousand transactions per second or more.  If you're in that boat, you'll have time to do a full evaluation of many technologies and probably wouldn't be asking here.
				- Alternatives
					- See the analysis of Soulborn Engine
					    intralink2:: https://workflowy.com/#/57f14cfcb176
					- How else do you decide when a new worker should be allocated (unle
					  collapsed:: true
						- You could allocate X amount of users/pbjects/other-entities to worker #1, then the next X users to worker #2 ?
						  collapsed:: true
							- This has latency issues compared to running all the nearby objects and users on one worker I expect
					- I could use non-spatial workers on a self-hosted platform, and keep spatial workers on the hosted platform
					  collapsed:: true
						- _Spatial_
						  collapsed:: true
							- Players
							- Objects
						- Non-Spatial
						  collapsed:: true
							- ai, chat, mail, login, character info
					- I can run PhysX/Bullet/Box2D standalone via C++ easily enough to give me physical simulation outside of Unity or unreal if it’s going to affect my pricing that greatly (RE: SpatialOS)
				- _FOSS Solutions_
					- Chronicles of Elyria - Soulborn Engine
					  collapsed:: true
					    Bullet/Ammo physics - used by Soulborn Engine for spatial, physical simulation
						- Was using SpatialOS, but instead focusing on FOSS components now
						    source:: https://chroniclesofelyria.com/forum/topic/23401/a-year-of-foundation
							- Why was SpatialOS dropped
							  collapsed:: true
								- Wasn't working with non-spatial workers like authentication, login server, AI, procedural story engine
								  collapsed:: true
									- Though I'm sure this is an excuse because they allow non-spatial workers or even using 3rd party services
								- Cheaper than SpatialOS and more customisable
							- Comparing each feature/component of SpatialOS to Soulborn Engine
							  collapsed:: true
								- SpatialOS is:
								  collapsed:: true
									- A pub/sub messaging system
									- Provides fault tolerance by auto-restarting services that shut down and auto-migration
									- Its a Load Balancer by spawning multiple workers of the same type in balancing messages between them
									- It's a hosting environment
									- It has monitoring and debugging abilities
									- It's a spatial orchestrator for communicating to workers which ones are responsible for which entities
									- It's a spatial, physical simulation
									- It's an entity visualizer.
								- Soulborn is (full description)
								  collapsed:: true
									- ECS built on PostgreSQL
									- pub/sub messaging system using RabbitMQ
									- fault tolerance provided by Docker Swarm
									- load balancer provided by Docker Swarm
									- hosting envrionment using NodeJS and Docker
									- monitoring systems using Docker Swarm
									- orchestrator via PostgreSQL and an orchestrator we wrote
									- spatial, physical simulation based (currently) on Ammo Physics
									- entity visualizer using VoxElyria
								- Soulborn is (short, low tech description)
								  collapsed:: true
									- As we had already started leveraging Docker Swarm, a Container technology for load balancing and fault tolerance of our non-spatial services, we knew we could transition to a full Docker stack if necessary for our spatial services as well. When we realized we were going to need to communicate between our spatial services and non-spatial services, we integrated RabbitMQ into our back-end, a super fast routing and message protocol used to serve 10's of millions of requests by banks and other high-traffic websites across the internet each day. And because we needed persistent storage for all our non-spatial data, we integrated PostgreSQL into our backend. Fortunately, PostgreSQL supports SQL, NoSQL, and even spatial queries, enabling it to act as a backend and persistent storage for both our spatial and non-spatial data.
							- Solution analysis
							  collapsed:: true
								- PostgreSQL works for other MMOs. Performance is improved by keeping movement and physics data in-memory, or by switching to NoSQL
								- RabbitMQ is fast but spatial simulation like SpatialOS/Dual Universe makes it more likely that nearby entities are simulated on the same hardware, maximising speed
								  collapsed:: true
									- So entities are communicated between each-other on RAM, communications overhead (networking) is orders of magnitude higher latency and lower bandwidth than NUMA RAM
						- Game engine - Cry or Unrealc
						  collapsed:: true
							- CryEngine used for look and client-side logic
							- Unreal Engine used for look and client-side logic
							    https://chroniclesofelyria.com/game/faq
						- Bullet / Ammo physics and spatial simulation
						    intralink2:: https://workflowy.com/#/a9b5c5b8b143
					- Physics engines
					  collapsed:: true
						- Bullet / Ammo
						  collapsed:: true
							- Features
							  collapsed:: true
								- One of the most complete physics libraries available in any programming language. Bullet Physics has been used in many commercial products such as [Grand](https://workflowy.com/#/a7330264241b)<a href="https://workflowy.com/#/a7330264241b"> </a><a href="https://workflowy.com/#/a7330264241b">Theft</a><a href="https://workflowy.com/#/a7330264241b"> </a><a href="https://workflowy.com/#/a7330264241b">Auto</a> IV and Red Dead Redemption, movies such as 2012 and Sherlock Holmes, and is available as a physics engine in many 3D authoring tools including Blender and Cinema 4D – and we now have those same resources available in Javascript!
							- Ammo (JavaScript implementation)
							  collapsed:: true
							    https://github.com/kripken/ammo.js/
								-
							- Bullet (C++ implementation)
							  collapsed:: true
							    https://github.com/bulletphysics/bullet3
								-
						- PhysX
						  collapsed:: true
							- https://github.com/NVIDIAGameWorks/PhysX-3.4
						- Project Chrono
						  collapsed:: true
							- https://projectchrono.org/
						- Open Dynamics Engine
						  collapsed:: true
							- http://www.ode.org/
					- Aether Engine prototype
					  collapsed:: true
					    Requires HadeanOS
						- FOSS Aether Engine OpenGL prototype
						  collapsed:: true
							- So, I decided to give it a go on our platform - Hadean (full disclosure, I’ve only been an employee here for 5 weeks). In 5 weeks, I built this demo [1, 2] which I think is already shaping up to be more impressive. I have my own ideas [2], but I want to know what suggestions you have/improvements you’d like to see. If you have any questions about the demo or the platform I’ll be around for a while, comment or message me.
							- I decided to take a different approach to their grid, while the 2D hexagons they use may be better in a few cases, their approach seems overly generic for many use cases [3].
							- My approach uses an octree with cells stored by Morton (Z-Order) index. A leaf cell in the tree corresponds to a single worker/core. New cells will be dynamically spawned when the entitIes move out of the live area, and despawned when they’re empty. Cells will also be subdivided when the load in a single cell increases beyond a threshold, this will maintain an almost constant amount of computation per worker. All of this is made fairly trivial on Hadean, which handles spawning and communication between workers across machines and clouds.
							- [1] Youtube video https://www.youtube.com/watch?v=w2fKRy5zC54
							- [2] github repo https://github.com/hadeaninc/spatial-tree-simulation-public
							- [3] SpatialOS load balancing https://docs.improbable.io/reference/12.0/workers/configuration/loadbalancer-config
						- FOSS open source N dimensional spatial processing C++ library libzinc
						  collapsed:: true
						    https://github.com/hadeaninc/libzinc
							- https://www.hadean.com/blog/open-source-library-for-spatial-representations
						- HadeanOS
						  collapsed:: true
							- https://www.hadean.com/
							- Uses only a few thousand LoC OS
							  collapsed:: true
								- MINIX uses 15k
								    http://www.minix3.org/
						- Aether Engine (works with Unreal etc)
						  collapsed:: true
							- https://www.aetherengine.io/features
						- Technical explanation of HadeanOS Aether Engine
						  collapsed:: true
							- https://www.hadean.com/blog/mmorpg-rethinking-game-architecture
					- Distributed Scene Graph for OpenSimulator
					  collapsed:: true
						- https://github.com/intelvwi/DSG
					- Science papers
					  collapsed:: true
						- https://pdfs.semanticscholar.org/27ef/5a5f552855eef816444ee6fb5e3bb85c8fc6.pdf
						- _Several papers published for OpenSimulator_
						  collapsed:: true
							- http://opensimulator.org
							- Faster dynamic spatial partitioning in OpenSimulator
							  collapsed:: true
							    November 2017, Volume 21, Issue 4, pp 193–202
								- Umar FarooqEmail author
								- John Glauert
							- Load Balancing for Virtual Worlds by Splitting and Merging Spatial Regions
							  collapsed:: true
							    Informatica 42 (2018) 107–116 107
								- Authors
								  collapsed:: true
									- Umar Farooq
									- University of Science and Technology Bannu, Pakistan
									- E-mail: umar@ustb.edu.pk
									- John Glauert
									- University of East Anglia Norwich, UK
									- E-mail: j.glauert@uea.ac.uk
									- Kashif Zia
									- Sohar University, Oman
									- E-mail: kzia@soharuni.edu.om
							- A Comparative Analysis of Spatial PartitioningMethods for Large-scale, Real-time Crowd Simulation
							  collapsed:: true
								-
							- A scalable dynamic load distribution scheme for multi-server distributed virtual environment systems with highly-skewed user distribution
							- A refinement-tree based partitioning method for dynamic load balancing with adaptively refined grids
							- DynamicSpatialPartitioningforReal-TimeVisibilityDetermination
							- https://gameprogrammingpatterns.com/spatial-partition.html
				- _Proprietary_
					- _Standalone engines_
						- SpatialOS
							- Pros/Cons
							  collapsed:: true
								- Cons
								  collapsed:: true
									- Compared to Dual Universe's spatial simulation
									    intralink2:: https://workflowy.com/#/c723f548401e
										- SpatialOS uses 2D spatial simulation as opposed to 3D
										- DU uses dynamic load balancing, Spatial uses static boundaries for load balancing. They've recently made dynamic loadbalancer but it's still a bit awkward
										    https://docs.improbable.io/reference/13.0/shared/worker-configuration/loadbalancer-config#dynamically-load-balanced-workers
										- Do workers for low-traffic areas of the world shut down when not in use?
										  collapsed:: true
											- Load balancing for workers suggests it would (but then again they don't mention an alternative DB they use for storing state)
											- But In-memory DB makes this debatable since it'll always have to run to maintain state. But instead it should use a simple NoSQL or SQL db to maintain state of those regions
							- Used by
							  collapsed:: true
								- Scavengers
								  collapsed:: true
									- Scavengersgame.com
								- Seed
								  collapsed:: true
									- [https://www.seed-project.io/](https://www.seed-project.io/)
									- Low poly graphics simulating a whole world. RimWorld / The Sims-like
									- Screenshots
									    https://assets.rockpapershotgun.com/images/2017/08/seed4amb.png
								- Rebel Horizons
								  collapsed:: true
									- http://www.rebelhorizons.com/
								- Abandoned
								  collapsed:: true
									- Lazarus
									- Worlds Adrift
									- (previously) [Chronicles of Elyria](((63a9ae5b-f56f-40d4-85dd-32c5e3459a05)))
									- Mavericks (1000 player battle royale)
									    https://mavericks.gg
								- _Quite a few_
								    https://www.youtube.com/watch?v=Cex8pgqUDNY
							- Demos
							  collapsed:: true
								- SURVIVAL game
								    https://www.youtube.com/watch?v=lGWON5TtS04
							- How it works
							  collapsed:: true
								- They worked on it for 3 years and are backed by venture capital
								    https://www.reddit.com/r/gamedev/comments/42n7tz/largescale_simulation_using_100s_of_unity3d/czdp43s
								- SpatialOS explanation
								  collapsed:: true
									- Allows splitting workers across a cluster of different servers
									- networking on the server, load balancing all the entities in the world, replication of entities across multiple server nodes, cross-process communication, collision detection of millions of entities, etc.
									- Distributed physics so two worker can see the entities but only one has  authority over it, and it changes multiple times per second
									    source:: https://improbable.io/games/blog/distributed-physics-without-server-boundaries
								- _Aspects_
								  collapsed:: true
									- Entities
									  collapsed:: true
									    in-memory DB e.g. eg ((6607f722-b674-4037-af49-e03bafebc259)), ((64634999-fc4a-4bf0-9d74-f8dc23708311))
										- All things in your world exist as entities. SpatialOS maintains the persistent state of all entities across a cluster of servers
									- Workers (container microservices)
									  collapsed:: true
									    Has load balancing, fault tolerance
										- Workers are micro-services that simulate the components of entities across the world. SpatialOS runs as many workers across your world as needed to simulate every component in the world. All data synchronization is handled for you.
										- which overlap and dynamically reorganize to power a huge, seamless world.
									- Operations
									    gRPC
									- Components
									  collapsed:: true
										- Entities consist of components, which define their state and how other entities interact with them. Components are defined in a schema language. Automatically generated integrations then allow different workers to visualize and simulate them.
								- Apparently it might not support 3D axis, only flat 2D axis instancing (which is why Dual Universe didn't use it?)
								- CoE was going to use it but had issues with the pricing and non-spatial systems like authentication
								- https://www.gamedev.net/forums/topic/689484-spatialos-single-shard-mmo/?page=2
							- Backend platforms for games and apps
							  collapsed:: true
								- FOSS
								  collapsed:: true
									- Nakama
									  collapsed:: true
										- http://github.com/heroiclabs/nakama
										- http://heroiclabs.com/
										- is an open-source distributed social and realtime server for games and apps.
									- Back4App
									  collapsed:: true
										- https://www.back4app.com/
								- Proprietary
								  collapsed:: true
									- Firebase
									- SpatialOS upports Amazon's GameSparks and Microsoft's PlayFab games platform include leaderboards, real-time and turn-based multiplayer, notifications and player save data.
							- Tech stack
							  collapsed:: true
								- Open source components
								  collapsed:: true
									- [source] https://improbable.io/games/blog/open-source-at-improbable
									- Core OS (Docker/Kubernetes based)
									- Core OS components fleet and etcd
									  collapsed:: true
										- etcd is a distributed key-value store, allowing easy storage and access of data throughout a cluster of machines. We use etcd at large scale, with more than a dozen clusters, and have contributed to the integration of Prometheus-based monitoring within etcd.
										- Fleet is an init system for clusters; a shared systemd across many machines. As a cluster manager, fleet allows deployment of single container anywhere in the cluster, or multiple containers in many configurations across varied hosts. Fleet can be used to protect against failure by maintaining a fixed number of instances of a given container or service. Our use case for fleet is a bit unique, but we’ve found it a fantastic tool, and have also contributed fixes to scalability and monitoring.
									- Prometheus monitoring
									  collapsed:: true
										- Prometheus is a monitoring system built and open sourced by Soundcloud. Prometheus uses a target model whereby it pulls from applications providing metrics according to the specification, making it extremely flexible and scalable. As well as monitoring, Prometheus contains a component, Alertmanager, with a powerful expression language and management of alerts through grouping, deduplicating and other utilities.
										- As with most things at Improbable, we run Prometheus at unusually large scale, pushing its experimental federation support to its limit, and work closely with the Prometheus developers on improving scalability of the system. We also provide Prometheus metrics of SpatialOS deployments direct to users.
									- gRPC and Gateway
									  collapsed:: true
										- gRPC is an cross-language RPC mechanism built by Google, following the finalisation of the HTTP/2 standard. gRPC is our tool of choice for inter-service communication, across all layers of our platform, using a set up very similar to that discussed here.
										    https://coreos.com/blog/gRPC-protobufs-swagger.html
										- We’ve contributed some ongoing bug fixes to gRPC, as well as contributing to design discussions.
										- A project building off of gRPC is gRPC gateway, an automatic RESTful service generator. gRPC Gateway generates a REST API served by reverse-proxy over the specifying gRPC service. As users of gRPC Gateway, we contributed some error handling code, and support for version 3 of protobuf, Google’s data interchange format.
										    https://github.com/gengo/grpc-gateway
									- Bazel
									  collapsed:: true
										- Bazel is the build tool by Google. Bazel has an emphasis on reproducibility, and can be used for both client and server. We love building our Scala with Bazel, so we contributed improved build mechanisms for Scala, particularly around tests.
							- 1 Backlink
							  collapsed:: true
								- _See_ [SpatialOS](https://workflowy.com/#/ced4703c0504)
					- _Games_
					  collapsed:: true
						- _Implemented_
							- Dual Universe (uses a 3D alternative to SpatialOS)
							    intralink2:: https://workflowy.com/#/c723f548401e /  http://i.imgur.com/ojLDBXC.png
							- _SpatialOS-based games (at least 3)_
							    intralink2:: https://workflowy.com/#/393eac05bc4a
							- Roblox distributed physics
							  collapsed:: true
								- They use client-side for some of it, which does risk modding
								    http://gamasutra.com/view/feature/173977/scaling_a_physics_engine_to_.php
							- Camelot Unchained
							  collapsed:: true
							    https://gallery.mailchimp.com/2b70fd18d895dd960141bac55/images/cae6e4e6-7285-41e4-a36f-b2a7cbaaa87d.jpg
								- Camelot Unchained managed 1000s of players and 10 000s of projectiles (which can interact with other projectiles) on a single map (I played an early test with 6000) by using GPUs/PhysX on the server (NB: not the client, so there's no need for customers to have NVIDIA cards). The main drawback with that is determinism - but that's a far more approachable problem compared to 1000s of players on CPU cores.
								- Can support 1000 low-poly characters on their custom engine
								    http://camelot-unchained.wikia.com/wiki/Game_Engine
							- Cloudgine (though this is more offloading processing to server-side)
							  collapsed:: true
								- Epic Games recently announced the acquisition of Cloudgine, the technology that powers the cloud-based multiplayer mode of Crackdown 3.
								  collapsed:: true
									- https://venturebeat.com/2018/01/22/epic-acquires-cloudgine-so-unreal-devs-can-offload-game-processing-to-servers/
						- _Plans to implement_
							- ((63542965-aaa8-4872-b7bb-026c76092669)) "Server Meshing" (likely will be aided by Amazon Lumberyard partnership)
								- Server-Side Object Container Streaming (SSOCS)
								- Other networking info
									- https://starcitizen.tools/Object_Container_Streaming
									- https://starcitizen.fandom.com/wiki/Instancing
								- https://youtu.be/camufEiCjeM
								- Been delayed, likely moved to 3.7
								    https://www.reddit.com/r/starcitizen/comments/9na9se/server_meshing_on_the_roadmap/
							- ((632d02af-9d3a-45b1-ab6d-69f923db836e))
							- _Indie games_
								- https://www.gamedev.net/projects/820-unsettled-world/
				- _[Learning Resources]_
				  collapsed:: true
					- networked physical simulation
						- Glenn Fielder articles
						    https://gafferongames.com/categories/networked-physics/
							- UDP does better than TCP
					- https://developer.oculus.com/blog/networked-physics-in-virtual-reality-networking-a-stack-of-cubes-with-unity-and-physx/
					- https://gamedev.stackexchange.com/questions/164175/resolving-collision-physics-across-distributed-physics-engines#
					- https://www.reddit.com/r/gamedev/comments/42n7tz/largescale_simulation_using_100s_of_unity3d/
					- https://medium.com/an-improbable-future
					- https://medium.com/@Improbableio
			- _Kubernetes-based hosting for instance or session-based multiplayer_
			    #Infrastructure https://workflowy.com/#/7bd4b0b56d86
		- [Learning Resources]
			- https://www.gamedev.net/forums/forum/8-networking-and-multiplayer/
	- Game engines
	  id:: 635593ab-6d31-4120-b696-8a6f470c53bb
	  collapsed:: true
		- Rendering lighting, collisions, physics, etc
		- _Performance enhancements_
			- Occlusion culling
			  collapsed:: true
				- AKA Visual culling or fractual culling as devs call it
				- https://i.kinja-img.com/gawker-media/image/upload/s--iGTq2Ic3--/c_scale,fl_progressive,q_80,w_800/ucoln8kedwfglsrlxvm5.gif
		- _Proprietary_
			- Unreal Engine
			  id:: 635593ab-2437-42be-b560-b9628e19a174
			  collapsed:: true
				- Pros/Cons
					- Pros
						- Unreal is best suited for developing highly graphical and photorealistic games
						  collapsed:: true
							- Used to run ((63542965-aaa8-4872-b7bb-026c76092669))
							- RTX raytracing/casting demo from Unreal 2018
							-
						- As a 3D Artist, Unreal Engine is a lot more user friendly than unity. Primarily because of UE's Material Workflow.
						- Unity is easier to begin with, but if you're dedicated then UE is better
						  collapsed:: true
							- However, if you're just interested in making games without too much "initial effort", so to say, Unity is quite good.
							- However, if you're dedicated and don't mind spending some more time into getting everything perfect, I feel UE is the better choice.
							- Coming from a programmers perspective here XD
						- Blueprint Visual Scripting technology (flowchart-based) are great for non-programmers
						  collapsed:: true
							- which allows you create games using the Blueprint only. Even a non-programmer can write code and create games using the UE4 to an extent; however, such games would have some limits. Apart from all, the bad sight of this engine is, it is not able to develop games for the past generation consoles
							- Unreal Engine Blueprints (flowchart-based) are awesome for programming, for a non-programmer!
						- flowchart ai thingy
						  collapsed:: true
							- one of the things ive beenconsidering too is incorperating machine learning intot he game
							- effectively take top 10 players, record all their actions, break them up based on interaction modules as it were, then have the ai utilize modules in reactions to players
						- It's highly recommended for 3D games
						    https://www.reddit.com/r/gamedev/comments/85js40/epic_games_releases_12_million_worth_of_paragon/dvxx9du
						- C# layer may be possible
						  collapsed:: true
							- for this team https://sandbox.facepunch.com/
							- Though it could be buggy
						- AAA studios who have the budget can go for this less efficient but with a higher max quality graphics/performance engine
						- Unreal support publishing to many platforms eg consoles
						- Unreal Engine 4 is gaining a stronger and stronger presence due to its tight integration of C++, the powerful, native Blueprint visual scripting language, and its recent addition of Mono C#. Blueprint is flexible, effective, and can be compiled down into somewhat optimized C++ code. Unreal C++ is an impressive concoction of its own that adds reflection and garbage collection features commonly associated with high level languages like C#.
					- Cons
						- [Source-available](https://wiki.froth.zone/wiki/Source-available?lang=en) [commercial software](https://wiki.froth.zone/wiki/Commercial_software?lang=en) with [royalty](https://wiki.froth.zone/wiki/Royalty_payment?lang=en) model [for commercial use](https://www.unrealengine.com/en-US/eula)
						- Support for Linux is limited
						  collapsed:: true
							- Several developers I've seen have dropped Linux support in their games because Unreal doesn't do a good job of it
							- Independent dev submitting PRs
							    https://www.patreon.com/ue4linux
						- C++ is more verbose and difficult than C#, making projects take longer
						- Cost - 5% royalty fee after $12k/year
						  collapsed:: true
							- free to use, however, you need to pay a royalty fee of 5% on the money you make off your games, designed by the Unreal Engine 4. In a nutshell, Epic Games will get 5% of everything you earn, be it the in-app purchases, in-game ads or the money you charge the users to purchase your game. However, the makers of the Unreal Engine 4 let the developers use its full version for free in case the revenue you earn from the game is up to $3,000/ quarter.
						- It has far less documentation or tutorials than Unity
						- Unity has an extremely good asset store for getting games up and running quickly
						- Becoming a monoculture
						  id:: 635b850e-b22f-4f1a-9745-fd5f9c64fac0
							- CDPR is dropping Red Engine and moving to Unreal 5
								- https://teddit.net/r/Games/comments/ydyvjc/the_witcher_were_thrilled_to_reveal_that_together/
							- lot more support documentation and premade code that they can use
					- Unclear
						- Projects like Cyberpunk 2077 are switching from their proprietary engine to Unreal Engine, and it is likely in large part because it allows them to hire developers more cheaply
							- He's stressing the creative angle, but the cynic in me can't help but see a primarily monetary motivation - it's cheaper for a studio with an apparently high turnover rate to hire a guy with Unreal on his resume than it is to keep the guy who's built their proprietary tech, because the former come a dime a dozen, while the later are unique specimens with appropriate price tags.
							- Yeah the longer the proprietary guy works for you the more valuable he is and the more you have to pay him. Cheaper to hire a kid out of university and throw him into unreal.
							- Even from the perspective of the individual dev it's better to know unreal than a proprietary engine. Sure you might make more knowing the proprietary stuff but that knowledge ain't worth shit to other companies which limits your options should anything happen to the company you currently work for. It's only really an incentive for your boss to pay you just barely more than the average.
							  
							  Proprietary software is pretty much a net negative for everyone involved.
			- Unity 3D
			  collapsed:: true
				- Pros/Cons
					- Pros
						- Mid 2022 - merged with an advertising company
							- [I’ll take “sentences I never thought I’d write” for 200, Alex : godot](https://teddit.namazso.eu/r/godot/comments/vzd5pu/ill_take_sentences_i_never_thought_id_write_for/)
						- Well-known as the best for 2D
						- Source available, though not open-source
						    https://blogs.unity3d.com/2018/03/26/releasing-the-unity-c-source-code/
						- Free, or up to $125/month
						    https://store.unity.com/
						- Said to be easier to get started with than Unreal
						- Unity is the better platform for developing mobile and 2D/3D games
						- Supports the most platforms
						- Unity 3D uses C# or JavaScript, which is more preferred than C++, as it gives no pain to switch from Java to C# as compared to C++.
						- you can also buy assets that allow coding in Python, real ECMA JavaScript, Lua, etc
						  collapsed:: true
							- Jurassic (JavaScript)
								- https://github.com/paulbartrum/jurassic
								- https://assetstore.unity.com/packages/tools/integration/jurassic-javascript-runtime-interpreter-for-unity-2345
								-
							- https://assetstore.unity.com/packages/tools/integration/python-interpreter-645
							- https://assetstore.unity.com/packages/tools/integration/unity-lua-interface-library-391
						- Unity support publishing to many platforms eg consoles
					- Cons
						- Said to be less extensive than Unreal
						- Said to result in lower fidelity games than Unreal
						- As it has such an extensive asset store they don't have as many native features as Unreal, which means more money spent on these assets and less official support/polish
				- https://forum.unity.com/
				- Documentation
				  collapsed:: true
					- https://unity3d.com/learn/tutorials
				- Linux software
				  collapsed:: true
					- Unity Hub
					  collapsed:: true
						- _Setup_
						  collapsed:: true
							- Download (AppImage in ESSENTIALS)
							    https://forum.unity.com/threads/unity-hub-release-candidate-0-20-1-is-now-available.546315/
							- Announcement post
							    https://blogs.unity3d.com/2018/01/24/streamline-your-workflow-introducing-unity-hub-beta/
					- https://forum.unity.com/forums/linux-editor.93/
					- https://forum.unity.com/threads/linux-ide-going-forward.593803/
				- Assets
				  collapsed:: true
					- Top FPS assets
					    http://i.imgur.com/DUUHmWI.png
					- Systems
					  collapsed:: true
						- _Basics - movement and combat_
						  collapsed:: true
							- OOTII
							  collapsed:: true
								- Third Person Motion Controller (auto animate any character with walking, jumping etc even non-humanoid)
								  collapsed:: true
									- https://assetstore.unity.com/packages/templates/systems/third-person-motion-controller-15672
									- Components Include:
									  collapsed:: true
										- Actor Controller
										- Motion Controller
										- Multiple Cameras
										- Debug Logger
										- Object Pool
										- Profiler
									- 3 types of movement in the video (adventure, shooter and MMO style)
								- Bone Controller (set limb movement limits, make characters respond to the environment/threat/terrain etc)
								  collapsed:: true
									- https://assetstore.unity.com/packages/tools/animation/bone-controller-31483
								- Camera Controller (1st, 3rd person, 3rd over shoulder, MOBA style iso, and a few more)
								  collapsed:: true
									- https://assetstore.unity.com/packages/tools/camera/camera-controller-13768
								- Mount Points (snapping weapons to humans/vehicles, skin meshes to allow clothing without clipping etc)
								  collapsed:: true
									- https://assetstore.unity.com/packages/tools/animation/mount-points-16318
								- Spell Casting Motion Pack (requires Third Person Motion Controller)
								  collapsed:: true
									- https://assetstore.unity.com/packages/templates/systems/spell-casting-motion-pack-91109
								- Shooter Motion Pack
								  collapsed:: true
									- https://assetstore.unity.com/packages/templates/systems/shooter-motion-pack-104578
									- Movement, cover, reloading,
							- Opsive
							  collapsed:: true
							    https://assetstore.unity.com/publishers/2308
								- _Comparison_
								    https://d2ujflorbtfzji.cloudfront.net/package-screenshot/8ec42be0-e003-4fd6-b758-a1410f380f53_scaled.jpg
								- €160 Ultimate Character Controller (1st and 3rd person POV,
								    UFPS+TPC
								- €67 UFPS: Ultimate FPS
								  collapsed:: true
								    v2=UFPS+TPC e.g. locomotion system from UFPS and the ability system from TPC.
									- https://assetstore.unity.com/packages/templates/systems/ufps-ultimate-fps-106748
								- €84 Third Person Controller (shooting, melee, fall, etc etc)
								  collapsed:: true
									- https://assetstore.unity.com/packages/templates/systems/third-person-controller-126347
							- Invector
							  collapsed:: true
							    https://assetstore.unity.com/publishers/13943
								- _Showcase _(used in many games)
								    https://youtu.be/G4qrxFp4zKo
								- Third Person Controller - Basic Locomotion Template
								  collapsed:: true
									- Rolling, climbing, pushing, jumping, strafing backwards
									- https://assetstore.unity.com/packages/templates/systems/third-person-controller-basic-locomotion-template-59332
								- Third Person Controller - Melee Combat Template
								  collapsed:: true
									- https://assetstore.unity.com/packages/templates/systems/third-person-controller-melee-combat-template-44227
								- Third Person Controller - Shooter Template ( ThirdPerson, TopDown or 2.5D Shooter)
								  collapsed:: true
									- https://assetstore.unity.com/packages/templates/systems/third-person-controller-shooter-template-84583
							- Easy Character Movement (rigidbody)
							  collapsed:: true
								- https://assetstore.unity.com/packages/templates/systems/easy-character-movement-57985
							- All in One Game Kit - ELC Character System (multiple camera angles, movement styles, etc)
							- TopDown Engine (2D Roguelike)
							  collapsed:: true
								- https://assetstore.unity.com/packages/templates/systems/topdown-engine-89636
						- _Other_
						  collapsed:: true
							- Event System - Dispatcher (scalable message and events system)
							  collapsed:: true
								- https://assetstore.unity.com/packages/tools/integration/event-system-dispatcher-12715
							- Game Kit Controller (advanced item use, especially for computers, hacking etc)
							  collapsed:: true
								- https://assetstore.unity.com/packages/templates/systems/game-kit-controller-40995
								- (zoom, rotate objects, use pin codes, type in passords, use computers (evernote text doc), hack panels using a key combo, use inventory items to hack panels, security cameras with full control, two-step door locks)
							- uBuild: In-game modular building system (Sims-like)
							  collapsed:: true
								- https://assetstore.unity.com/packages/templates/systems/ubuild-in-game-modular-building-system-75709
							- Inventory Pro (inventory, crafting GUI, loot etc)
							  collapsed:: true
								- https://assetstore.unity.com/packages/tools/gui/inventory-pro-66801
							- Rucksack - Multiplayer Inventory System
							  collapsed:: true
								- https://assetstore.unity.com/packages/templates/systems/rucksack-multiplayer-inventory-system-114921
							- Population Engine (add NPCs to cities, vehicles, scenery)
							  collapsed:: true
								- https://assetstore.unity.com/packages/templates/systems/population-engine-71314
						- _Game types_
						  collapsed:: true
							- uMMORPG (tons of features, Guild Wars 2-like, also a ton of extra add-ons available)
							  collapsed:: true
								- https://assetstore.unity.com/packages/templates/systems/ummorpg-51212
								- 6000 Lines of carefully crafted C# Code
							- uRPG
							  collapsed:: true
								- https://assetstore.unity.com/packages/templates/systems/urpg-95016
							- uSurvival (T/FPS zombie survival-type game)
							  collapsed:: true
								- https://assetstore.unity.com/packages/templates/systems/usurvival-95015
							- MMORPG KIT (2D/3D/Survival)
							  collapsed:: true
								- https://assetstore.unity.com/packages/templates/systems/mmorpg-kit-2d-3d-survival-110188
							- Game Creator (scripting scenes with NPCs, quck time events, etc, many addons available)
							- Adventure Creator (navigation, cutscenes, conversation choices, physic games, inventory, lip syncing etc)
							  collapsed:: true
								- https://assetstore.unity.com/packages/tools/integration/event-system-dispatcher-12715
						- _RPG_
						  collapsed:: true
							- Quest Machine (hand written and procedural quests system)
							  collapsed:: true
								- https://assetstore.unity.com/packages/templates/systems/quest-machine-39834
							- RPG Editor: ORK Framework (RPG combat systems etc)
					- Input Management
					  collapsed:: true
						- https://assetstore.unity.com/categories/tools/input-management
					- Integrations
					  collapsed:: true
						- https://assetstore.unity.com/categories/tools/integration
					- GUI
					  collapsed:: true
						- https://assetstore.unity.com/categories/tools/gui
						- NGUI: Next-Gen UI
						  collapsed:: true
							- https://www.youtube.com/watch?v=UMZggH3-8lc
					- Visual Scripting
					  collapsed:: true
						- https://assetstore.unity.com/categories/tools/visual-scripting/?order_by=popularity&q=category%3A115&rows=42
						- Playmaker
						  collapsed:: true
							- Showcase
							    https://www.hutonggames.com/showcase.html
							- https://assetstore.unity.com/packages/tools/visual-scripting/playmaker-368
						- Behavior Designer - Behavior Trees for Everyone (lifelike AI)
						  collapsed:: true
							- https://assetstore.unity.com/packages/tools/visual-scripting/behavior-designer-behavior-trees-for-everyone-15277
						- DOTween Pro
						  collapsed:: true
							- https://assetstore.unity.com/packages/tools/visual-scripting/dotween-pro-32416
						- Bolt
						  collapsed:: true
							- https://assetstore.unity.com/packages/tools/visual-scripting/bolt-87491
					- VFX
					  collapsed:: true
						- https://assetstore.unity.com/categories/vfx
						- Particles
						  collapsed:: true
							- Spells
							  collapsed:: true
								- Realistic Effects Pack 4
								  collapsed:: true
									- https://assetstore.unity.com/packages/vfx/particles/spells/realistic-effects-pack-4-85675
									-
								- REP 3
								  collapsed:: true
									- https://assetstore.unity.com/packages/vfx/particles/spells/realistic-effects-pack-3-27523
						- Shaders
						  collapsed:: true
							-
					- Tools
					  collapsed:: true
						- https://assetstore.unity.com/packages/tools/utilities/gpu-instancer-117566
						- Physics
						  collapsed:: true
							- PuppetMaster by ROOTMOTION
						- Animation
						  collapsed:: true
							- Final IK by ROOTMOTION
							  collapsed:: true
								- https://assetstore.unity.com/packages/tools/animation/final-ik-14290
							- Puppet3D
							  collapsed:: true
								- https://assetstore.unity.com/packages/tools/animation/puppet3d-111554
							- UMotion Pro
							  collapsed:: true
								- https://assetstore.unity.com/packages/tools/animation/umotion-pro-animation-editor-95991
							- Voxel Importer
							  collapsed:: true
							    Import "MagicaVoxel", "Qubicle" and Pixel art. Animate your voxel character!
								- https://assetstore.unity.com/packages/tools/modeling/voxel-importer-62914
						- AI
						  collapsed:: true
							- Dialogue System
							  collapsed:: true
								- https://assetstore.unity.com/packages/tools/ai/dialogue-system-for-unity-11672
						- _Related: _Animation main
						    intralink2:: https://workflowy.com/#/1df82d81000b
					- Audio
					  collapsed:: true
						- Sound FX
						  collapsed:: true
							- Universal Sound FX
							  collapsed:: true
								- https://assetstore.unity.com/packages/audio/sound-fx/universal-sound-fx-17256
					- Animations
					  collapsed:: true
						- Parkour & Acrobatics
						  collapsed:: true
							- https://assetstore.unity.com/packages/3d/animations/parkour-acrobatics-animation-pack-15704
							- Most I wouldn't want to use as they're unnecessary flips but it's decent
						- Heroic Traversal (superhero/Brute-like)
						  collapsed:: true
							- https://assetstore.unity.com/packages/3d/animations/heroic-traversal-67802
						- Hero General Animation Collection
						  collapsed:: true
							- Sitting, emotes, communication, environment interaction, exercise, sneaking, https://assetstore.unity.com/packages/3d/animations/hero-general-animation-collection-5988
						- https://assetstore.unity.com/packages/3d/animations/rpg-character-mecanim-animation-pack-63772
					- _Unsorted_
					  collapsed:: true
						- MapGen
						  collapsed:: true
							- WorldComposer
							  collapsed:: true
								- https://assetstore.unity.com/packages/tools/terrain/worldcomposer-13238
							- MapMagic
							- Gaia
							  collapsed:: true
								- https://assetstore.unity.com/packages/tools/terrain/gaia-42618
						- _Environment VFX_
						  collapsed:: true
							- Living Particles
							  collapsed:: true
								- https://assetstore.unity.com/packages/vfx/particles/spells/living-particles-105817
					- 1 Backlink
					  collapsed:: true
						- Unity Store [assets](https://workflowy.com/#/443cde325406)
				- _Related: _Game design elements
				    intralink2:: https://workflowy.com/#/ae83dd8cb9cd
			- CryEngine
			  collapsed:: true
				- does not require its users to pay the royalty fee upon designing the game. However, you need to pay a fixed amount viz. $9.90 /- per month in order to gain the access to CryEngine
			- UNIGINE 2 (used by Dual Universe, they say better for MMOs)
			    intralink2:: https://workflowy.com/#/f6853532203b
			- _Others_
			  collapsed:: true
				- Game Maker Studio
				- https://www.rpgmakerweb.com/
		- _FOSS_
			- [Godot](https://godotengine.org)
			  id:: 63a9acd6-3dd5-4a11-a446-5d6596cdbfd8
			  collapsed:: true
				- Pros/Cons
					- [Pros](https://godotengine.org/features)
						- FOSS no matter your revenue
						- Easy to extend because it's open-source
						- Very lightweight (30MB)
						- 2D - some argue it to be the best for 2D games
						- [The Engine editor is a Godot game in itself, so it's easy to extend](https://github.com/godotengine/godot/issues/4181#issuecomment-203516916)
						- Multi-language support including a Python-like language called GDScript, and bindings for many other languages e.g. C++, C#
						  collapsed:: true
							- C++
							- Scripting engine
							  collapsed:: true
								- GDScript (Python-like)
								    Good for fast prototyping, you can later move that code over to C++
									- Previous iterations of Godot have had directly implemented C++ and an in-house python-like scripting language called GDScript. It was used after having already tried Python, Lua, and other scripting languages and found all of them lacking in efficiency when dealing with the unique architectural designs that the Godot Engine implements. As such, GDScript is uniquely tailored for Godot usability in the same way that Blueprints for UE4 are.
									- Python scripting lets you prototype way faster than C#: no worrying about types, duck typing can help you set up systems without massive boilerplate, etc.
										- When you find a design you like, you can move your python code over to C++, which has static typing and is much faster than C# / Python.
									- given that the documentation is targeted for GDScript, if you're starting with Godot I strongly recommend that you learn it and use it initially. Then you can move part or all of your code to C# or C++ if you prefer those languages or have strong performance requirements.
										- If you know C# or C++ already, you can learn 95% of GDScript's features in maybe 2 hours, at most.
									- I'm sure GDScript is pleasant to work with, but it's esoteric. I will never use GDScript on any other projects at work or in my spare time unless I'm working on Godot. I prefer to use C# or C++ on my personal projects not for any particular technical requirements on the projects themselves (such as speed) but because it lets me use and improve a general skill that I can apply outside on other things.
								- C# (via Mono)
								- VisualScript (Flow-based programming)
									- Later on, a visual scripting system called VisualScript was implemented that could function equivalently to GDScript.
									- https://docs.godotengine.org/en/3.0/getting_started/scripting/visual_script/getting_started.html
								- Pluggable (GDNative API) support
									- C++
									- Nim (Python-like)
									- D
							- What to choose
							- The engine is written in C++. Compiled-in "modules," also written in C++, can be integrated if desired. A scripting engine is built in that exposes an API (the one in the docs) from C++ to anything that wants to bind to that scripting engine. GDScript is already bound and integrated, and this latest update now adds C# as a bound and integrated language (alongside a visual scripting language called VisualScript).
							- 3.0 also supports GDNative, a C API for communicating with the engine's scripting engine, allowing (for example) additional languages to be bound (but not integrated). C++ and a few other languages have been added in this manner; thus, you can generate bindings in C++ that enable dynamically-linked code to hook into the scripting API. The scripts added via GDNative-generated bindings are referred to as NativeScript (*.gdns files) which just point to the library and a class within it. Any calls from any language to the scripting engine will trigger whatever the bound code is, regardless of the bound implementation's language. These GDNative-bound languages, however, are not integrated, "first-party" languages like GDScript, VisualScript, and C#. Any changes made must be recompiled into the same dynamic library to take effect. Still, this bound NativeScript code can be executed without recompiling the engine.
							- PluginScript
							  collapsed:: true
								- Created by author of godot-python binding
								    https://github.com/touilleMan/godot-python
								- https://github.com/godotengine/godot/pull/11953
								- Recently, however, the developer who added Python created an additional system based on GDNative called PluginScript which essentially teaches the engine how to treat a GDNative-bound language as a first-party scripting language. AFAIK, they've had some success getting Python working in this manner (uses the in-engine script editor, works with debugging, scripts have automatic and live re-loading, etc.). In a nutshell, PluginScripts will allow you to simply download new scripting languages for the engine directly from the in-engine Asset Library.
								- ..
								- this is for adding "plug & play" script languages via GDNative.
								- It abstracts away some of the inconviences of GDNative.
								- If a language is exposed as a PluginScript it will benefit from the same editor integration as GDScript/C#.
									- So you can download the plugin from the assetlib and are able to choose that language directly in the "Add script" dialog, have the buildsystem set up, use the godot script editor, able to use templates, build automatically when running the game, etc.. all the things you'd have to do manually when using GDNative bindings directly.
							- [Bindings](https://github.com/Vivraan/godot-lang-support)
								- The power that truly sets Godot 3.0 apart however is its inclusion of a new C API for binding scripted properties, methods, and classes to code implemented in other languages. This API allows any native or bound language’s capabilities to be automatically integrated with every other native or bound language’s dynamically linked functionality. The dynamically linked libraries are registered as “GDNative” code that points to the bound languages’ code rather than as an in-engine script, effectively creating a foreign interface to Godot’s API. This means that properties, methods, and classes declared and implemented in one language can be used by any other language that has also been bound. Bindings of this sort have already been implemented for C++ (Windows, Mac, and Linux). Developers are also testing bindings for Python (already in beta), Nim, and D.
								- Rust and JavaScript bindings are in the works as well, if I understand correctly.
								- Rust
									- https://github.com/GodotNativeTools/godot-rust
								- Most performant/hardest to least
									- C++
									- C#
									- GDScript / Python
									- VisualScript
								- Unsorted
									- [Rust](https://github.com/godot-rust/gdnative)
									- [JavaScript](https://github.com/GodotExplorer/ECMAScript)
									- [TypeScript](https://github.com/GodotExplorer/ECMAScript)
								- Edit: C# was recently merged in, and someone ran a comparison of the performance between GDScript, C#/Mono, and GDNative C++.
								    https://github.com/cart/godot3-bunnymark
								- In comparing these various scripting options, C# will likely have better performance than GDScript, but GDScript is more tightly integrated and easier to use. VisualScript will be the least performant of these, but arguably the easiest for non-programmers to use. If raw performance is the goal, then GDNative will be the most effective (since it is literally native code), but it is the least easiest to use out of these as you have to create different builds of the dynamic library for each target platform.
								- The “loose integration” this enables will empower any Godot developer to leverage pre-existing libraries associated with any of the bound languages such as C++’s enhanced optimizations/data structures, any C# Unity plugins that are ported to Godot, pre-existing GDScript plugins, and the massive library of powerful statistical analysis and machine learning algorithms already implemented by data research scientists in Python. With every newly added language, users of Godot will not have to resign themselves to the daunting “language barrier” that haunts game development today. Instead, they’ll be able to create applications that take advantage of every conceivable library from every language they like.
								- In addition, here is a post I made on Reddit that goes more in-depth into the relationship between the engine’s scripting languages.
								    https://www.reddit.com/r/gamedev/comments/77vp6k/introducing_c_scripting_in_godot_engine/dopjhd3/
						- GDScript is quite nice
							- [Has optional typing](https://godotengine.org/article/optional-typing-gdscript)
							- Python-like, so it's easy to read
						- Native support for Bullet physics engine (best)
						  collapsed:: true
							- PhysX has GPU-acceleration only on Nvidia GPUs
							- Unity has addons to use Bullet instead but it lacks GPU-acceleration I believe because it's non-native?
						- In v4: Vulkan for cross-platform and performance
						- [Godex](https://github.com/GodotECS/godex) - ECS library
						- [On Evaluating Godot. I just wrapped up a 3-week internal… | by Casey Yano | Medium](https://caseyyano.com/on-evaluating-godot-b35ea86e8cf4) - ((644c0bbc-9a44-4320-a7fc-1ad01f89ddf3)) creators
					- Cons
						- 3D support only decent since March 2018 so it's lagging behind other engines. Will stay limited until Vulkan port in 3.2
						  collapsed:: true
							- Video overview of 3.0 features
							    https://youtu.be/XptlVErsL-o
							- Not likely to get much more 3D features until Vulkan is written perhaps
							    intralink2:: https://workflowy.com/#/74a14274cca6
						- _Lacks certain features_
							- [An easier type of visual scripting](https://github.com/godotengine/godot/issues/17795#issuecomment-419994283)
							- Limited multi-platform export support
							  collapsed:: true
								- VR support
								- Poor/no console support
							- [2023 complaints](https://godotengine.org/article/whats-missing-in-godot-for-aaa/)
								- Streaming
								- Low level rendering access. Scene job system. Swarms. Large team VCS support
								- Commercial asset store
								- Game specific templates and behaviors. Visual scripting. Specialized artist UIs
						- [Thousands of bugs still open on GitHub (though reminds me of Riot/Matrix)](https://github.com/godotengine/godot/issues?page=2&q=is%3Aissue+is%3Aopen+sort%3Acomments-desc)
						- Young so it:
							- [Lacks the extensive third party add-ons, assets and tooling that Unity has](https://github.com/NathanWarden/unity-godot-compat)
							- Moderately lacks the documentation and tutorials that Unity currently has
					- {Archive}
						- https://willnationsdev.wordpress.com/2017/07/21/godot-the-game-changer-for-gamedevs/
				- _Links_
				  collapsed:: true
					- GitHub milestones
					    https://github.com/godotengine/godot/milestones
					- Patreon news. £10k Jan 2021
					    https://www.patreon.com/godotengine/posts
					- _Games using Godot_
					  collapsed:: true
					    https://godotengine.org/showcase / https://youtu.be/ZR1Yfmr1KRM
						- Spacestation 14
						    https://spacestation14.io/post/18_02_26_progress-report-5-waiting_for_godot/
					- _Community_
					  collapsed:: true
					    https://godotengine.org/community
						- Forum
						    http://godotdevelopers.org/
						- Q&A
						    https://godotengine.org/qa
						- https://www.reddit.com/r/godot/
						- https://www.youtube.com/c/GodotEngineOfficial
						- Discord, Matrix
					- https://github.com/Calinou/awesome-godot
				- _Upcoming features_
				  collapsed:: true
					- Roadmap (planned)
					    https://github.com/godotengine/godot-roadmap/blob/master/ROADMAP.md
					- Wishlist (someday) - empty atm
					    https://github.com/godotengine/godot-roadmap/blob/master/WISHLIST.md
					- v3.1 alpha
					  collapsed:: true
					    https://gist.github.com/Calinou/49aefe52ce8f67ffa3f743932123d14f
						- https://github.com/godotengine/godot/milestone/7
						- Planned
						  collapsed:: true
							- OpenGL ES 2.0 support
							- Proper Mono export support
							- Support for 2D meshes, 2D skeletons, and deformable polygons
							- New animation tree, with state machine and root motion support
							- Blender to Godot exporter that keeps Cycles/Eevee materials (tentatively)
							- Features voted in Patreon that do not involve changing 3D rendering
				- Reviews
				  collapsed:: true
					- Mostly positive
					  collapsed:: true
						- https://medium.com/rock-milk/why-godot-engine-e0d4736d6eb0
					- Mostly negative
					  collapsed:: true
						- https://www.reddit.com/r/godot/comments/8m4cug/moving_from_unity_to_godot/
						- https://www.reddit.com/r/gamedev/comments/9ahqh2/do_you_think_godot_will_ever_match_gms2_in/
				- Voxel-related tools
				  collapsed:: true
					- _Voxel engines_
					  collapsed:: true
						- godot_voxel
						  collapsed:: true
							- https://github.com/Zylann/godot_voxel
							- Pros/Cons
							  collapsed:: true
								- Pros
								  collapsed:: true
									- Experimental support for smooth terrain using Transvoxel http://transvoxel.org/, by using voxels as isolevels
									- Has physics
									    https://www.youtube.com/watch?v=0HLKJK1ex64
								- Cons
								  collapsed:: true
									- still don't know how physics will work. Will Godot physics be enough? Or will I have to roll my own? Or mix the two with a special kind of collider?
									- Lacks
									  collapsed:: true
										- Level of detail (not a priority for my project)
										- Game specific features such as cave generation or procedural trees (though it might include tools to help doing them)
										- Editor tools (only a few things are exposed)
										- Import and export of voxel formats
										- For reasons why I don't work on X or Y, see https://github.com/Zylann/godot_voxel/issues/17
							- https://godotengine.org/qa/31576/voxel-isometric-supported?show=31576#q31576
							- Game
							  collapsed:: true
							    https://github.com/Zylann/voxelgame
								- Requires both
								  collapsed:: true
									- godot_voxel
									- godot_opensimplex (simplex noise is an alternative to perlin noise)
									    https://github.com/Zylann/godot_opensimplex
								- It's all GDScript with SurfaceTool, so expect world generation to be slow as hell.
								- But thanks to thread goodness the game runs smoothly at 60 fps with a decent viewing range.
					- _Unanalysed_
					  collapsed:: true
						- RPG In A Box
						    https://www.rpginabox.com/development-update-as-of-5-2-18/
					- PixaVoxet - Voxel to Pixel Art Animator/Renderer inside Godot
					    https://github.com/mishapsi/pixavoxet
					- https://www.reddit.com/r/godot/comments/7w3qnr/magicavoxel_obj_godot/
					- MagicaVoxel importer
					    https://www.reddit.com/r/godot/comments/94honk/tool_script_magicavoxel_importer/
					- _Related: _Voxel software and info
					    intralink2:: https://workflowy.com/#/0cfb2f49040d
				- Tutorials
				  collapsed:: true
					- See Community page
					- https://www.youtube.com/channel/UCBHuFCVtZ9vVPkL2VxVHU8A
					- https://www.youtube.com/channel/UCxboW7x0jZqFdvMdCFKTMsQ
					- https://www.youtube.com/channel/UC5C24RIrjvsn7ddwsuUtJOQ
					- https://mrminimal.gitlab.io/2018/07/26/godot-dedicated-server-tutorial.html
				- Games built on it
					- Slay the Spire 2
					- ((635eb2d2-ed36-4f2e-bb93-1c0b5168b728))
					- ((644c0a94-4b83-43d6-9598-bdde4df85ee7))
					- [Brotato](https://godotengine.org/showcase/brotato/)
					  id:: 669830d9-9e56-4a55-9c8d-ee93da065942
					- [Halls of Torment](https://godotengine.org/showcase/halls-of-torment/)
			- [Open 3D Engine (O3DE)](https://github.com/o3de/o3de) 
			  collapsed:: true
			  AKA Amazon Lumberyard
				- Amazon Lumberyard, the game engine they made based on CryEngine and was to be used with AWS services, it has been open-sourced after they couldn't make it take off
				- Amazon Lumberyard
				  collapsed:: true
					- Fork of Unreal engine
					- Runs ((63542965-aaa8-4872-b7bb-026c76092669))
					-
					- CryEngine-based | Presumably operates better with MMOs, as they rewrote the entire networking system and offer first-class support for their cloud infrastructure.
			- Seeds of Andromeda / Vorb Engine
			    intralink2:: https://workflowy.com/#/9b71aa0b3989
			- [Phaser](https://github.com/photonstorm/phaser) - 2D
			- [Twine](https://github.com/klembot/twinejs) - for interactive, nonlinear stories
			- [gb-studio](https://github.com/chrismaltby/gb-studio) - for retro game creator
			- [Ren'Py](https://github.com/renpy/renpy) - visual novel engine
			- [libGDX](https://github.com/libgdx/libgdx) - cross-platform Java game dev framework
		- _Related:_ Voxel game engines
		    intralink2:: https://workflowy.com/#/cf636af2bfc3
	- 3D graphics and compute APIs for rendering
	  collapsed:: true
		- What
			- Every game is made using an api, its a layer than translates from the game to the graphics card. Its what physically tells the gpu what to do (the physical instructions).
			- This isn't important for the majority of game devs, only the game engine devs?
		- _Desktop etc APIs_
			- Vulkan (cross-platform Windows and Linux, and MacOS via MoltenVK)
			  collapsed:: true
			    Parity with Direct3D 12
				- Benefits
				  collapsed:: true
					- Makes writing drivers much easier: or in the case of Mac, ends up using the Metal driver which is the only one Apple really cares about
					- Reduces driver overhead in tons of ways
					- Opens up massive opportunities for optimization, via multithreading CPU work and providing ways to offload work to the GPU
					- Things like the Vulkan debug layers and validation layers, plus the ease with which one can make their own layers, makes debugging and testing Vulkan loads easier (in my experience)
					- These three facts mean that even poorly implemented Vulkan renderers can be significantly more performant.
				- Learning Resources
				  collapsed:: true
					- If you want to chart a path to Vulkan, start learning the basics of 3D graphics without all the minute details of fussing about at a low-level with the GPU. Use the DSA extensions and stuff to get a better idea of what it's like to use a modern API, too:
					- https://github.com/Fennec-kun/Guide-to-Modern-OpenGL-Functions
					- From there, diving into Vulkan can be done with: https://vulkan-tutorial.com/ and https://github.com/SaschaWillems/Vulkan
					- https://www.fasterthan.life/blog/2017/7/11/i-am-graphics-and-so-can-you-part-1
				- Vulkan is a low-overhead, cross-platform 3D graphics and computing API. Vulkan targets high-performance realtime 3D graphics applications such as video games and interactive media across all platforms. Compared with OpenGL and Direct3D 11, and like Direct3D 12 and Metal, Vulkan is intended to offer higher performance and more balanced CPU/GPU usage. Other major differences from Direct3D 11 (and prior) and OpenGL are Vulkan being a considerably lower level API and offering parallel tasking. Vulkan also has the ability to render 2D graphics applications;[10] however, it is generally best suited for 3D. In addition to its lower CPU usage, Vulkan is also able to better distribute work among multiple CPU cores.[11]
			- _Vulkan implementations of DirectX_
			  collapsed:: true
			    Only useful if the game is already made with DirectX
				- _Overview_
				    https://imgur.com/JR30YOS
				- _Implementations_
				  collapsed:: true
					- vkd3d (Direct3D 12)
					    Normally Windows 10 only
					- DXVK (Direct3D 10/11)
					- VK9 (DirectX 9)
					- _Lesser used_
					  collapsed:: true
						- dxup(dx10)
				- _Related:_
				  collapsed:: true
					- WineD3D is going to implement a Vulkan backend (codename Damavand)
					  collapsed:: true
						- Pros
						  collapsed:: true
							- DXVK running into issues that likely could be resolved by using WineD3D's approach
							    https://reddit.com/comments/e920wb
						- It currently supports DX7-11 with an OpenGL backend
			- DirectX incl Direct3D (Windows only)
			- OpenGL (predecessor to Vulkan)
			  collapsed:: true
				- Vulkan, formerly named the "Next Generation OpenGL Initiative" (glNext),[53][54] is a grounds-up redesign effort to unify OpenGL and OpenGL ES into one common API that will not be backwards compatible with existing OpenGL versions.
			- Metal (MacOS and iOS)
		- Web APIs
			- WebGL (OpenGL ES-based)
			- WebGL tentative successors
			  collapsed:: true
			    Since
				- Obsidian/WebGPU (Mozilla's FOSS API)
				  collapsed:: true
					- https://github.com/KhronosGroup/WebGLNext-Proposals/tree/master/Obsidian-Mozilla
					- WebGPU (formerly Obsidian?)
					  collapsed:: true
						- https://github.com/gpuweb/gpuweb
						- WebGPU prototope in Servo browser, backed by gfx low-level core.
						    https://github.com/kvark/webgpu-servo
				- WebMetal (Apple's proprietary API)
	- _Other aspects of game design_
	  collapsed:: true
		- 3D modelling + texturing + animation
		  collapsed:: true
			- _3D modelling software_
			  collapsed:: true
				- _3D models/assets and e-stores_
				  id:: 64e0944e-e850-4745-a22e-a5fcca03cad8
				  collapsed:: true
					- Inspiration
					  collapsed:: true
						- _Voxel art_
						  collapsed:: true
							- 54 image gallery http://imgur.com/gallery/8zEE1/
							- https://twitter.com/ephtracy
							- https://www.reddit.com/r/VOXEL/
							- https://www.reddit.com/r/VoxelArt/
						- _High poly_
						  collapsed:: true
							- https://www.artstation.com/dyotoorion
					- Free 3D models
						- _General 3D models_
						  collapsed:: true
							- http://devassets.com/browse/
							- https://zerobudgetgames.com/
							- https://www.blendswap.com/blends
							- Unreal Engine releases $17M of assets for MOBA Paragon
							    https://www.unrealengine.com/en-US/paragon
						- _Voxel assets_
						  collapsed:: true
							- https://kenney.nl/assets
							- https://assetstore.unity.com/lists/free-low-poly-and-voxel-10940
							- https://itch.io/game-assets/free/tag-voxel
							- https://opengameart.org/art-search-advanced?field_art_tags_tid=voxel
						- _Low poly assets_
						  collapsed:: true
							- https://assetstore.unity.com/lists/free-low-poly-and-voxel-10940
							- https://itch.io/game-assets/free/tag-low-poly
							- https://opengameart.org/art-search-advanced?field_art_tags_tid=low%20poly
							- Specific assets
							  collapsed:: true
								- Weapons
								  collapsed:: true
									- https://assetstore.unity.com/packages/3d/props/guns/modern-weapons-pack-14233
								- Environments
								  collapsed:: true
									- https://assetstore.unity.com/packages/3d/environments/urban/simple-modular-street-kit-13811
						- [SketchFab](https://sketchfab.com)
						- [The DM Workshop](https://www.shapeways.com/shops/dmworkshop) on [Shapeways](https://www.shapeways.com) (need to make a free account to see download button)
						  collapsed:: true
							- However it'll be a very detailed STL file, so need to convert it to FBX via Blender
								- Tutorial [https://www.youtube.com/watch?v=j8sZ-VM0FoI](https://www.youtube.com/watch?v=j8sZ-VM0FoI)
					- Paid 3D Model stores
						- General 3D models
						  collapsed:: true
							- https://sketchfab.com/store
							- _Weapons_
							  collapsed:: true
								- AAA quality - CHAMFERZONE on Unity store
						- _Voxel assets_
						  collapsed:: true
							- Simple brand assets - see recommendations
							    https://assetstore.unity.com/packages/3d/environments/urban/simple-world-volume-one-43072
							- https://sketchfab.com/store/3d-models?poly_count=0..10000&q=voxel
							- https://assetstore.unity.com/lists/voxel-46470
						- _Low poly assets_
						  collapsed:: true
							- https://sketchfab.com/store/3d-models?formats=uasset&formats=unitypackage
				- _Modelling / editor software_
				  collapsed:: true
					- Blender
					  collapsed:: true
					    Everything: modeling, rigging, animation, simulation, rendering, compositing and motion tracking, even video editing and game creation.
						- https://www.blender.org/
						- Blender founders started Open Movies (short movies) to start dogfooding their software and discover what else they need to change
						- Tutorials
						  collapsed:: true
							- Blender Guru beginner series - modelling, materials, lighting (fundamentals)
							  collapsed:: true
							    https://www.youtube.com/watch?v=JYj6e-72RDs&list=PLjEaoINr3zgHs8uzT3yqe4iHGfkCmMJ0P&index=2
								- _Basic 3D_
								  collapsed:: true
									- Basic 3D is needed to be able to do VFX, gaming, VR, animated movies, 3D printing, architectural visualisation
									- _Aspects_
									  collapsed:: true
										- Modelling
										- Texturing
										- Lighting
										- _Advanced_
										  collapsed:: true
											- Animation
											  id:: 644c09ab-da4c-48af-b1d5-45622e9b6a80
											- Compositing
							- Blender Guru intermediate series
							    https://www.youtube.com/watch?v=yi87Dap_WOc&list=PLjEaoINr3zgHJVJF3T3CFUAZ6z11jKg6a
					- 3DS Max, Cinema 4D, Maya,
					- https://dust3d.org/
					- Houdini - uses AI for procedural modeling
					  collapsed:: true
						- _Very high-quality_
						  collapsed:: true
							- Used in big movies
							    https://www.youtube.com/watch?v=wH1Pgr-pJGE
							- Can be used to generate assets for good-looking 3D worlds
							    https://www.youtube.com/watch?v=nlCD7lJubes
						- Houdine Engine - used for integrating these assets into common game engines
						  collapsed:: true
							- _Plugins for game engines_
							  collapsed:: true
								- Houdini Engine for Unity
								  collapsed:: true
								    https://github.com/sideeffects/HoudiniEngineForUnity
									- This plug-in brings Houdini's powerful and flexible procedural workflow into Unity through Houdini Digital Assets. Artists can interactively adjust the asset's parameters inside Unity, and use Unity geometries as an asset's inputs. Houdini's procedural engine will then "cook" the asset and the results will be available right inside Unity.
								- Houdini Engine for Unreal
								    https://github.com/sideeffects/HoudiniEngineForUnreal
							- Houdine Engine for Godot?
							  collapsed:: true
								- https://www.sidefx.com/forum/topic/54360/?page=1#post-254757
						- Used for 3D modelling as well as procedural level design
						- https://80.lv/articles/procedural-level-building-in-ue4-with-houdini/
						- _{Archive}_
						  collapsed:: true
							- The Next Leap: How A.I. will change the 3D industry - Andrew Price
							    https://www.youtube.com/watch?v=FlgLxSLsYWQ
					- _Voxel modeller / editor_
					  collapsed:: true
						- _FOSS _
						  collapsed:: true
							- VoxelShop (on Linux)
							  collapsed:: true
								- https://github.com//simlu/voxelshop
								- https://blackflux.com/node/11
							- Goxel (on Linux)
							  collapsed:: true
								- https://guillaumechereau.github.io/goxel/
								- https://github.com/guillaumechereau/goxel
								- Goxel 3D procedural rendering
								    https://blog.noctua-software.com/goxel-procedural.html
							- Voxel model editor
							  collapsed:: true
								- https://www.reddit.com/r/VoxelGameDev/comments/98rkg8/nicks_voxel_editor_an_opensource_voxel_model/
						- _Proprietary_
						  collapsed:: true
							- MagicaVoxel (not available on Linux but easy to setup on it)
							  collapsed:: true
							    http://www.voxelmade.com/wp-content/uploads/2017/02/laptop-magicavoxel-e1486239745941.jpg
								- https://ephtracy.github.io/
								- How to setup on Linux
								  collapsed:: true
									- https://medium.com/@r_musitelli/install-magicavoxel-win-64-on-linux-d90236fdf927
									- https://blog.mjurtz.com/2018/01/install-magicavoxel-on-linux/
								- Exporting straight from MagicaVoxel in .obj format.
								  collapsed:: true
									- This method exports two elements: your model, and a texture containing all of the colors in your palette. All of the settings you might have set in the MagicaVoxel renderer will NOT be exported (lighting, emissive materials, transparency, metal…).
								- Baking your model in MagicaVoxel and export in .ply format.
								  collapsed:: true
									- If you find that exporting straight in .obj doesn’t give good enough results, you might want to go to the next level: baking. Baking is a process that saves the lighting information of a model in the mesh itself. Although baking is generally done with a texture, MagicaVoxel actually stores the lighting information in each vertex (point) of the model. When exporting a baked model from MagicaVoxel, you don’t get a mesh and a texture, but only a very dense mesh that contains all the color information.
									- There are several downsides to this technique: first, the mesh can be heavy if your model is big and complex. Second, MagicaVoxel only bakes the lighting from the Sky and Sun in the MagicaVoxel renderer, and the lighting from emissive materials and the transparency won’t be taken into account. It will also be harder to add lighting and transparency effects in Sketchfab without using a 3d software like Blender.
							- $75 Qubicle (not available on Linux)
							  collapsed:: true
							    http://www.voxelmade.com/wp-content/uploads/2017/03/laptop-qubicle-e1488832899657.jpg
								- http://minddesk.com
								- Looks really easy to use
								    https://youtu.be/QhoXjh1fP_s
								- Used by quite a few published indie games
							- VoxelMax for Unity
							  collapsed:: true
								- https://assetstore.unity.com/packages/tools/modeling/voxel-max-39877
								- s an easy to use Voxel editor and
								- Voxelizer
								  collapsed:: true
									- This package is capable to convert any mesh or texture into editable voxel model. VoxelMax is also capable to reduce the necessary polygon count in it's models.
							- Constrained morphing voxels in Avoyd Editor
							  collapsed:: true
							    https://www.enkisoftware.com/imgstore/Avoyd_2018-02-06_Constrained_morphing_voxels.jpg
								- https://www.enkisoftware.com/devlogpost-20180206-1-Voxel-Editor-Evolved
								- Tutorial
								    https://youtu.be/GxL8vNprIXo
								- £40 software
								- Will include movement, procedural map generation etc
								- https://www.enkisoftware.com/imgstore/Avoyd_2017-12-07_4k3WorldTreeScattering_thumb.jpg
						- Voxelisers
						  collapsed:: true
							- See VoxelMax for Unity
						- Reverse voxelisers (pixelisers)
						- Getting voxels into each game engine
						  collapsed:: true
							- Unity
							  collapsed:: true
								- https://assetstore.unity.com/packages/tools/magicavoxel-qubicle-to-unity-63336
								- http://weheartgames.com/2015/04/adding-voxel-art-from-magicavoxel-into-unity3d/
						- _Related: _
						  collapsed:: true
							- Voxel game engines
							    intralink2:: https://workflowy.com/#/cf636af2bfc3
							- Voxel models (free, paid and inspiration)
							    intralink2:: https://workflowy.com/#/264a06ce43a0
					- See Animation
					    intralink2:: https://workflowy.com/#/1df82d81000b
			- _Materials & texturing software_
			  collapsed:: true
				- _Online texture and e-stores _
				  collapsed:: true
					- https://www.poliigon.com/category
				- Substance Designer - uses AI for automatic texturing with a material pattern rather than texturing individual assets
				  collapsed:: true
				    http://i.imgur.com/XSaACm6.png
					- PBR materials/texturing
					- is the Ultimate 3D Material Authoring and Scan Processing Tool.
					  collapsed:: true
						- It has become the standard in the entertainment industry for PBR material authoring.
					- Used for Destiny 2; Robo Recall, Assassin's Creed Origins; Forza Horizon 3; Ghost Recon Wildlands; Call of Duty WW2, ((62d447c3-1697-44f5-8b10-040563bc1698))
					- https://store.steampowered.com/app/978690/Substance_Designer_2019/
					- _{Archive}_
					  collapsed:: true
						- The Next Leap: How A.I. will change the 3D industry - Andrew Price
						    https://www.youtube.com/watch?v=FlgLxSLsYWQ
				- Substance Painter
			- Animation
			  collapsed:: true
			    Rigging
				- See
				  collapsed:: true
					- 3D modelling software
					    intralink2:: https://workflowy.com/#/0d9c94a26f87
					- Unity animation software
					    intralink2:: https://workflowy.com/#/4673d868b33c
					- Mixamo
					  collapsed:: true
						- https://www.mixamo.com/#/
						- Animated 3D characters. No 3D knowledge required.
						  collapsed:: true
							- Rapidly create, rig and animate unique characters for design projects.
				- _Aspects_
				  collapsed:: true
					- IK, Inverse Kinematics
					  collapsed:: true
						- https://www.reallusion.com/iclone/Help/iClone4/Std/08_Animation/Motion_Layer/What_is_IK_FK.htm
					- FK, Forward Kinematics
					  collapsed:: true
						- https://www.reallusion.com/iclone/Help/iClone4/Std/08_Animation/Motion_Layer/What_is_IK_FK.htm
					- Rigging
				- Harmony
				- https://www.reddit.com/r/gamedev/comments/9vxszn/walk_cycles_are_hard_so_i_made_a_quick_cheatclip/
				- Motion capture
				  collapsed:: true
					- DensePose - can use normal video instead of motion capture suits
					    https://github.com/facebookresearch/DensePose
				- _Related: _
				  collapsed:: true
					- Game design ideas - animation
					    intralink2:: https://workflowy.com/#/a4d231277316
					- Unity animation assets
					    intralink2:: https://workflowy.com/#/a59f1e064155
				- 1 Backlink
				  collapsed:: true
					- _Related: _[Animation](https://workflowy.com/#/1df82d81000b)
			- VFX
			  collapsed:: true
				- See Houdini
		- _Voxel vs polygons_
		  collapsed:: true
		    Terrain, assets etc
			- What
			    3d pixels are called voxels (volume + pixel), basically many cubes joined together
			- Pros/Cons
			  collapsed:: true
				- Pros
				  collapsed:: true
					- Easier for an unskilled 3D artist to create assets
					- GPUs render everything as polygons - voxels are just for data storage and physics. We don't have voxel graphics cards
					    See Algorithms for isosurface extraction
					- Star Citizen has tons of texture glitches because they don't use voxels
					    https://www.youtube.com/watch?v=13y5uYHdIRU
					- Allows Level of Detail (LoD)-based rendering for higher performance
					  collapsed:: true
					    https://static1.squarespace.com/static/5aa5ba4b55b02ca2a2f3b593/t/5bf962d003ce64e76c197c49/1543070442415/voxbun2.gif?format=500w
						- Large voxel terrains may contain millions of polygons.  Rendering such terrains at a uniform scale is both inefficient and can lead to aliasing of distant objects.  As a result, many game engines choose to implement some form of level of detail based rendering, so that distant terrain is rendered with less geometry.
					- High poly is unmanageable, only AAA can even attempt
					  collapsed:: true
						- Right now, it takes years of work to be able to use complex tool chains for 3D graphics, and if you want to make a specific change in the art, you often have to go back to the right tool in the chain to make the change, Siles said.
						- “Voxels are the solution, and they have been around since the 1970s,” Siles said. “Voxels are more like manipulating clay. With polygons, you have a problem when you scale from millions to billions of polygons. It’s a data management problem that is hard to overcome. We have the software breakthrough to this with voxels now.”
					- Procedural generation
					- In game modifiability and destructibility of terrain and objects.
					  collapsed:: true
						- Allows terraforming the world
						- Fully ((67375ec1-1917-489b-842d-81e3ef13f3c7))
				- Cons
				  collapsed:: true
					- Star Citizen is making a higher quality graphics and more beautiful world (but it's expensive)
					- Easier to get crowdfunding if more of the content is company rather than user-generated?
					- Voxel Cons:
					  collapsed:: true
						- Very large resource overhead
						- Rasterization  (everything is blocky)
			- _Notable games using voxels_
			  collapsed:: true
				- Dual Universe - UNIGINE + Voxel Farm?
				    intralink2:: https://workflowy.com/#/3f4fdc07774a
				- Space Engineers
				    intralink2:: https://workflowy.com/#/4454dc99b411
				- ((67375ec5-fb82-4aec-98e4-7c76445c30b7)) - unknown engine
				- Stellar Overloaded game
				  collapsed:: true
				    Slanted blocks, some small ones
					- https://store.steampowered.com/app/397150/Stellar_Overload/
					- 25cm³ blocks (voxels)
				- SoA team talking about rounded planets Level of Detail
				  collapsed:: true
					- https://www.youtube.com/watch?v=bJr4QlDxEME
			- _How to get sloped voxels_
			  collapsed:: true
				- Algorithms for isosurface extraction
				  collapsed:: true
					- Marching Cubes
					  collapsed:: true
						- Pros
						  collapsed:: true
							- Most popular and well-known
						- Cons
						  collapsed:: true
							- There's cracks during Level of Detail (see Transvoxel for at least one solution)
							- Dull edges (see Dual Contouring for at least one solution)
						- https://github.com/nsf/mc
						- C++ implementation with LOD support
						    https://github.com/stoyannk/voxels
					- Transvoxel
					  collapsed:: true
						- https://transvoxel.org/
						- Marching Cubes has issues with cracks for Level of Detail, this solves it
					- (Naive) Surface Nets
					  collapsed:: true
						- [saved]
						  collapsed:: true
							- https://0fps.wordpress.com/2012/07/10/smooth-voxel-terrain-part-1/
							- https://0fps.net/2012/07/12/smooth-voxel-terrain-part-2/
						- Original theory and discussion
						  collapsed:: true
						    uses far less vertices or faces than Marching Cubes or Marching Tetrahedra
							- https://0fps.net/2012/07/10/smooth-voxel-terrain-part-1/
							- https://0fps.net/2012/07/12/smooth-voxel-terrain-part-2/
							- Conclusion
							  collapsed:: true
								- Each of the isosurface extraction methods has their relative strengths and weaknesses.  Marching cubes is nice on account of the free and easily usable implementations, and it is also pretty fast.  (Not to mention it is also the most widely known.)  Marching tetrahedra solves some issues with marching cubes at the expense of being much slower and creating far larger meshes.  On the other hand surface nets are much faster and can be extended to generate high quality meshes using more sophisticated vertex selection algorithms.  It is also easy to implement and produces slightly smaller meshes.  The only downside is that it can create non-manifold vertices, which may be a problem for some applications.  I unfortunately never got around to properly implementing dual contouring, mostly because I’d like to avoid having to write a robust linear least squares solver in javascript.  If any of you readers wants to take up the challenge, I’d be interested to see what results you get.
						- Implementation
						  collapsed:: true
							- The original papers have a javascript implementation
							    https://github.com/mikolalysenko/mikolalysenko.github.com/blob/master/Isosurface/js/surfacenets.js
							- Ported to C
							    https://github.com/r03ert0/surface-nets
							- C# for Unity
							    https://github.com/TomaszFoster/NaiveSurfaceNets/blob/master/NaiveSurfaceNets.cs
							- NoCubes mod for Minecraft (uses Surface Nets algorithm)
							  collapsed:: true
								- https://github.com/cadiboo/nocubes
								- Original is closed-source so fork has been created
								    https://www.minecraftforum.net/forums/mapping-and-modding-java-edition/minecraft-mods/2851780-no-cubes-forked-and-fixed?comment=190
						- Quality can be improved by using Dual Contouring algorithm instead, but it's more difficult and there are downsides
						    intralink2:: https://workflowy.com/#/588c8d28a20f
					- Dual Contouring
					  collapsed:: true
					    Sharper edges, doesn't look so obviously voxel
						- Pros/Cons
						  collapsed:: true
							- Pros
							  collapsed:: true
								- This technique produces very high quality meshes that can preserve sharp features
								- Allows building cubes
							- Cons
							  collapsed:: true
								- You need to have Hermite data, and recovering this from an arbitrary function requires using either numerical differentiation or applying some clunky automatic differentiator.  These tools are nice in theory, but can be difficult to use in practice (especially for things like noise functions or interpolated data).  T
								- Solving an overdetermined linear least squares problem is much more expensive than taking a few floating point reciprocals, and is also more prone to blowing up unexpectedly when you run out of precision.
								- There is some discussion in the paper about how to manage these issues, but it can become very tricky.
						- _Used by big companies_
						  collapsed:: true
							- Used by Dual Universe
							    source:: https://www.youtube.com/watch?v=MWcuwt9bjHo
							- Used by Voxel Farm since 2012 according to a comment
							    source:: https://0fps.net/2012/07/12/smooth-voxel-terrain-part-2/
							- 7 Days to Die
							    https://youtu.be/uaVca4OT99A?t=2m38s
						- Some notes:
						  collapsed:: true
							- Marching cubes uses guesswork to smooth edges, dual contouring doesn't
							    source:: http://procworld.blogspot.com/2010/11/from-voxels-to-polygons.html
							- Dual contouring means that for every cell, you also introduce a vertex on the cell's boundary. For a cube grid, you just pair every cube with the vertex offset of their top-left-back corner. This vertex's coordinates are constrained to the range 0 to 1.
							- Where to put the extra vertex is a complicated thing you can throw a lot of math at, but I found that hill climbing from the middle works almost as well as full brute force, so I used that.
							- You don't need to specify your vertex coordinates with floats, you can use whatever resolution you like. In my experiments 8 values (3 bits per axis) was enough that it looks basically continuous, but I'm using 16 values (4 bits per axis) because when I go bitpack everything later I don't want to deal with things that aren't byte-aligned.
							- You don't need to store vertex coordinates of cells that don't touch the surface. Full air and full solids can null it our or use something that compresses easily.
							- As far as I can tell, there's no easy way to do collision detection with dual contours (and thus you can fall through the ground in my demo). You'll have to generate the mesh for the relevant part of the grid and do full mesh collision against that. (Which is some serious work that I haven't felt like doing yet.)
							- Collision could be made much easier if you found the plane for each of the 6 faces of your "cube," but because each side has four vertices and they can all be moved separately, they might not actually be coplanar. I'd love to hear a good solution for this :-). (Other than building the world out of tetrahedra instead.)
						- Implementations
						  collapsed:: true
							- https://github.com/Lin20/isosurface
							  collapsed:: true
								- https://reddit.com/comments/3m1fpl
							- https://reddit.com/r/dualcontouring
						- Tutorial
						    http://www.boristhebrave.com/2018/04/15/dual-contouring-tutorial/
					- Dual Marching Cubes
					  collapsed:: true
						- is an algorithm for meshing voxel data that uses an octree to optimize the mesh, resulting in a mesh that uses less geometry where less is needed. It also (as far as I can tell) supports both smooth and blocky geometry. This would potentially provide better rendering performance compared to transvoxel.
						- _Implementations_
						  collapsed:: true
							- First is this one, which solves an issue with non-manifold geometry sometimes being generated: https://github.com/dominikwodniok/dualmc
							- The second is the VolumeComponent from Ogre3D, which is more game-oriented and additionally has a LOD mechanism: http://wiki.ogre3d.org/VolumeComponent
							- https://github.com/Lin20/isosurface
							  collapsed:: true
								- Author proposes that DC by itself may be better as it supports multiple materials
								    https://www.reddit.com/r/dualcontouring/comments/3m1fpl/im_publishing_my_2d3d_dual_contouring_and_dual/
							-
						- Document from volume-gfx.com - https://www.volume-gfx.com/volume-rendering/dual-marching-cubes/
						- Original paper: https://www.cs.rice.edu/~jwarren/papers/dmc.pdf
				- In Avoyd I use something I call constrained morphing voxels. Each voxel has a byte for how much material is in it, and if neighbours allow the cube is distorted to lower the volume.
				- Slopes represented by specific material sets or a parameter for cube, such as done in Stellar Overload or stb_voxel_renderer.h.
				- Tutorials
				  collapsed:: true
					- https://wordsandbuttons.online/interactive_explanation_of_marching_cubes_and_dual_contouring.html
			- _Voxel game engines_
			  collapsed:: true
				- Ideal features
				  collapsed:: true
					- _Voxel engine features (rendering only)_
					  collapsed:: true
						- Source code is available
						- It uses Dual Contouring for smooth terrain/sloped voxels
						- using an octree to represent the voxel data to stream huge worlds
						  collapsed:: true
							- Storing individual chunks as an Octree instead of the entire scene would be a good way to mitigate the performance overhead.
							- The idea I had was to add an option in the module to set the number of LOD levels. It would currently be 1 level. Level 2 would subdivide the current grid into a 1-level octree structure, and so on, so the root is still a grid and extends to the farthest the viewer can see.
							  collapsed:: true
								- But I said earlier only one viewer would be supported yet. So instead of having a deep octree, why not having indexed grids? No need for hashing, and accessing a LOD is just a matter of an index (I wonder if I am clear enough?).
								- When dealing with voxel data, I also found OpenVDB, which subdivides blocks by a factor of 8 instead of 2 (by block I mean "cubic chunks", if we were to use Minecraft's terminology). However I feel it's too abrupt of a transition, or maybe I miss something.
						- Level of Detail
						- Ambient occlusion - Vertex-based ambient occlusion on voxel edges
					- _Voxel game engine features_
					  collapsed:: true
						- _Game engine-specific_
						  collapsed:: true
							- networking
							  collapsed:: true
								- f you try to do low-latency FPS-capable networking with physics included in what's networked. That's a nightmare.
						- _Voxel-specific_
						  collapsed:: true
							- It's a plugin for a mainstream game engine (e.g. Unreal / Unity / Godot)
							- Physics
							- Editor tools
							- Import and export of voxel formats
							- (ambient occlusion, proper transparency, some time of region system https://www.youtube.com/watch?v=RMBQn_sg7DA, saving/loading chunks to disk
							- _What terrain content_
							  collapsed:: true
								- Multiple biomes
								- Specific terrain generation such as cave generation or procedural trees
				- Engines vs Game Engines
				  collapsed:: true
					- Game Engines
					  collapsed:: true
						- _Smooth terrain (Roblox-like)_
						  collapsed:: true
							- Basically every proprietary engine
							- godot_voxel
							- _See_ [Minecraft](https://workflowy.com/#/9e047fad0219)<a href="https://workflowy.com/#/9e047fad0219"> clone</a> mods
						- _Blocky terrain (Minecraft-like)_
						  collapsed:: true
							- _See_ [Minecraft](https://workflowy.com/#/9e047fad0219)<a href="https://workflowy.com/#/9e047fad0219"> clones</a>
							- Vorb Engine
							- Game of Stones
					- Engines
					  collapsed:: true
						- PolyVox
						- stb_voxel_render.h
				- _FOSS_
				  collapsed:: true
					- _Sloped voxels (Roblox-like)_
					  collapsed:: true
						- Game of Stones (game engine based on voxel engine PolyVox)
						  collapsed:: true
							- https://github.com/alexsaalberg/game_of_stones
							- So I've made a voxel engine with C++, PolyVox, BulletPhysics, and OpenGL. The engine is pretty basic, it was a fun process, I learned a lot, but now I want to make a complete game.
						- Cubiquity/PolyVox
						  collapsed:: true
							- https://bitbucket.org/volumesoffun/cubiquity
							- Supports Unity and Unreal
							- Showcase
							  collapsed:: true
							    http://www.volumesoffun.com/polyvox-projects
								- Eg
								    http://foreverwar.sourceforge.net/screenshots.html
							- http://www.volumesoffun.com/cubiquity-is-now-fully-open-source-under-the-mit-license/
							- http://www.volumesoffun.com/reflections-on-cubiquity-and-finding-the-path-forward/
						- stb_voxel_render.h
						  collapsed:: true
							- Demo
							    https://www.youtube.com/watch?v=2vnTtiLrV1w&t=107
							- [cloned] https://github.com/nothings/stb/blob/master/stb_voxel_render.h
							- Written in C | 3803 LoC
							- Sloped blocks, can scale to millions of blocks easily with individual colours
							- Detailed textures for every block if desired
							    https://youtu.be/2vnTtiLrV1w?t=63
						- Quixel for Unity
						  collapsed:: true
						    Last update: 2014
							- https://github.com/Chippington/Quixel
							- https://forum.unity.com/threads/open-source-quixel-terrain-engine-smooth-voxel-terrain.240645/
							- 3117 LoC
						- Minecraft clone mods
						  id:: 64e0944d-c053-4333-9fe9-0c508415b16b
						  collapsed:: true
						    Can't find any that are Dual Universe-like; and I'd prefer to rely on a game engine like Godot at least
							- Minetest
							  collapsed:: true
								- natural_slopes (half cubes)
								  collapsed:: true
								    https://framagit.org/karamel/natural_slopes/raw/master/screenshot.png
									- https://forum.minetest.net/viewtopic.php?f=9&t=18140&hilit=smooth+terrain
								- Erosion
								  collapsed:: true
								    http://i.imgur.com/KaPJ7um.png
									- https://forum.minetest.net/viewtopic.php?f=11&t=15806
								- _Abandoned_
								  collapsed:: true
									- SimplySlopes
									  collapsed:: true
										- https://forum.minetest.net/viewtopic.php?f=11&t=13555
							- ((635036a8-f85b-4117-9b50-c24c242b9940))
					- _No marching cubes_
					  collapsed:: true
						- ((648f9076-9c44-4a26-8af5-8d709d1ab64d)) clones
						  id:: 635036a8-f85b-4117-9b50-c24c242b9940
						  collapsed:: true
						    1m*1m [blocks](https://minecraft.gamepedia.com/Block)
							- Noteworthy See ((648f9076-9c44-4a26-8af5-8d709d1ab64d)) clones mods
								- Fastcraft 2 (performance optimisation)
								  collapsed:: true
									- https://www.reddit.com/r/feedthebeast/comments/7rswqn/fastcraft_2_preview/
									- https://www.reddit.com/r/feedthebeast/comments/7s2hlj/in_light_of_the_news_of_fastcraft_2/
								- ComputerCraft
								- Optifine
							- ((6350388d-53e9-47f4-901d-862913d53e85))
							- Minetest (C++ engine, Lua game)
							  collapsed:: true
								- Pros/Cons
								  collapsed:: true
									- Lacks
									  collapsed:: true
										- Low draw range
										    https://github.com/minetest/minetest/issues/7222
									- The limitations I've had are mainly in the HUD/networking/performance areas.
								- Info
								  collapsed:: true
									- Minetest game engine is C++; mods and content is in Lua
									- https://www.minetest.net/
									- https://github.com/minetest/minetest
									- [https://forum.minetest.net/](https://forum.minetest.net/)
									- AppImage builds
									    [https://github.com/An0n3m0us/Minetest-AppImages](https://github.com/An0n3m0us/Minetest-AppImages)
									- Flatpak
									    [https://flathub.org/apps/details/net.minetest.Minetest](https://flathub.org/apps/details/net.minetest.Minetest)
								- Dev docs
								  collapsed:: true
									- https://dev.minetest.net/Changelog
									- https://dev.minetest.net/TODO
								- _Mods_
								  collapsed:: true
									- Mesecons (digital stuff like programmable blocks)
									  collapsed:: true
										- https://github.com/minetest-mods/mesecons
										- https://forum.minetest.net/viewtopic.php?f=11&t=628
										- Mesecons adds everything digital, from all kinds of sensors, switches, solar panels, detectors, pistons, lamps, sound blocks to advanced digital circuitry like logic gates and programmable blocks.
									- Dreambuilder
									  collapsed:: true
										- https://gitlab.com/VanessaE/dreambuilder_modpack
										- https://forum.minetest.net/viewtopic.php?f=11&t=9196
										- Dreambuilder is my attempt to give the player pretty much everything they'll ever want to build with, and all the tools they should ever need to actually get the job done. This modpack was, for most of its life, maintained as a subgame based on minetest_game, minus a couple of mods that I don't like, with a number of minor things changed, and a number of extra mods added on. Since then, many things have changed, from content to packaging format. Read on!
									- _Games_
									  collapsed:: true
										- [https://forum.minetest.net/viewforum.php?f=15](https://forum.minetest.net/viewforum.php?f=15)
										- MineClone 2
										    [https://git.minetest.land/MineClone2/MineClone2](https://git.minetest.land/MineClone2/MineClone2)
										- [Game] Carbone NG [carbone-ng]
										  collapsed:: true
											- https://github.com/Calinou/carbone-ng
											- https://forum.minetest.net/viewtopic.php?t=12824
											- Original
											    https://forum.minetest.net/viewtopic.php?t=9033
										- Overcraft Origins
										  collapsed:: true
											- https://forum.minetest.net/viewtopic.php?id=7427
											- http://overcraft-origins.wikia.com/wiki/Overcraft_Origins_Wiki
										- Clonecraft
								- 1 Backlink
								  collapsed:: true
									- See [Minetest (C++ engine, Lua game)](https://workflowy.com/#/6dabeb5e3cc0)
							- VoxelJS (JavaScript-based)
							  collapsed:: true
								- http://voxeljs.com/
							- Terasology (Java-based)
							  collapsed:: true
								- https://terasology.org/
								- They cubic chunks, rotation of every block, mod api, and repo, multiple alternative crafting system, very high biome Id limit (believe it's in the 100,000s). The technical achievements of it are pretty awesome.
								- https://github.com/MovingBlocks/Terasology
							- TrueCraft (C# based)
							  collapsed:: true
								- https://github.com/SirCmpwn/TrueCraft
							- Kubex (Java-based)
							  collapsed:: true
								- https://github.com/Ivelate/Kubex
							- Vox (C++ and C)
							  collapsed:: true
								- https://github.com/AlwaysGeeky/Vox
							- Blackvoxel (C++ based)
							  collapsed:: true
								- https://www.blackvoxel.com/
							- Craft (C based)
							  collapsed:: true
								- https://github.com/fogleman/Craft
							- _Published game_
							  collapsed:: true
								- Delver
								  id:: 67375ec2-759d-46fb-b1e4-18bbbceb4a50
								  collapsed:: true
								    http://i.imgur.com/401wXjS.png
									- [https://github.com/Interrupt/delverengine](https://github.com/Interrupt/delverengine)
									- wrote the engine in Java using the LibGDX framework.
									- [http://www.delvergame.com/](http://www.delvergame.com/)
									- 2 Backlinks
									  collapsed:: true
										- See [Delver](https://workflowy.com/#/051c1d43a05c)
										- _See_ [Delver](https://workflowy.com/#/051c1d43a05c)
							- https://osgameclones.com/#minecraft-games
						- Seeds of Andromeda and Vorb Engine (universe scale Minecraft)
						  collapsed:: true
							- https://www.reddit.com/r/VoxelGameDev/comments/8ocgup/seed_of_andromeda_and_vorb_engine_are_now_open/
							  collapsed:: true
								- Seed Of Andromeda and Vorb Engine are now Open Sourced (Planet-Scale Voxel Sandbox)
								- Source Code
								  collapsed:: true
									- Most of Regrowth Studios is either employed full time somewhere else, or at school, so we don't think its likely we will ever really continue the project in its original form. For this reason, we are open sourcing everything under the MIT license for you to use! Hopefully some aspect of this project is useful to you, even if only as a learning device :)
								- Screenshots: https://www.seedofandromeda.com/images
								- Videos showing what the game is capable of:
								  collapsed:: true
									- Star System: https://www.youtube.com/watch?v=oIy8ZQ7vDZQ&t=1s
									- Massive Cellular Automata Physics: https://www.youtube.com/watch?v=eKQYRFYXCWk
									- Procedural Gas Giants: https://www.youtube.com/watch?v=dPgKbKLAf4k
									- Procedural Stars: https://www.youtube.com/watch?v=REDKCg7P9t4
								- Old Dev Blogs (Includes technical blogs): https://www.seedofandromeda.com/blogs
								- Source Code
								  collapsed:: true
									- Follow the instructions on SoACode and it should properly clone submodules.
									- SoACode: https://github.com/RegrowthStudios/SoACode-Public
									- SoAGameData: https://github.com/RegrowthStudios/SoAGameData
									- SoADeps: https://github.com/RegrowthStudios/SoADeps
									- Vorb: https://github.com/RegrowthStudios/Vorb
									- VorbDeps: https://github.com/RegrowthStudios/Vorb-Deps
									- NOTE: A lot of code is commented out due to this being mid-refactor. Commented out code is typically something I was intending to rewrite, but it is still functional. Might even be worth reverting my last refactor.
								- Click here for an announcement video and some high level discussion of features.
								- You can PM me or comment here if you ever have any high level questions about parts of the code. I can at least look and try to remember what the hell I was thinking.
							- Features
							    http://i.imgur.com/IHDQq4R.png
							- Open-sourcing announcement video
							    https://www.youtube.com/watch?v=D8ua34JYMUY
					- See Godot voxel engines
					    intralink2:: https://workflowy.com/#/a36fd9c872c1
					- _Related tools_
					  collapsed:: true
						- Minecraft importer library
						    https://github.com/dougbinks/enkiMI
				- _Proprietary_
				  collapsed:: true
					- _Proprietary but source available_
					  collapsed:: true
						- $149 Voxel Plugin for Unreal
						  collapsed:: true
							- Pros/Cons
							  collapsed:: true
								- Pros
								  collapsed:: true
									- Source available for Free version but it lacks
									  collapsed:: true
										- Voxel Graphs
										- Voxel Actors & Grass
										- Voxel Physics
										- Multiplayer
										- Importers
									- That version last works in Unreal 4.18
									- Importers: import from meshes, heightmaps, landscapes, MagicaVox, 3D Coat and splines
									- Multiplayer
									- Tessellation, Voxel physics, Full source access
									- Seamless LOD, Blueprint interface
								- Cons
								  collapsed:: true
									- Only been around since mid 2017
									- Uses Marching Cubes algo, and you can tell it's got some sharp edged terrain
									    https://voxel-plugin.readthedocs.io/en/latest/generalconcept.html
							- Documentation
							    https://voxel-plugin.readthedocs.io/en/latest/
							- https://voxelplugin.com/
							- [cloned] https://github.com/Phyronnaz/VoxelPlugin
							- Issues / bug reporting
							    https://gitlab.com/Phyronnaz/VoxelPluginIssues/issues
							- Announcement thread
							    https://forums.unrealengine.com/community/released-projects/125045-voxel-plugin%E2%84%A2
						- Space Engineers - VRAGE game engine
						  collapsed:: true
						    2017 code available but not open-source
							- Pros/Cons
							  collapsed:: true
								- Cons
								  collapsed:: true
									- Windows-only since it's DirectX
							- http://www.keenswh.com/vrage.html
							- I am trying to build SpaceEngineers and during the build, it says I need to buy SpaceEnigeers game first for the assets
							- https://blog.marekrosa.org/2015/05/space-engineers-full-source-code-access_40.html
							- Space Engineers
							  collapsed:: true
								- 0.5m block size
								    http://spaceengineers.wikia.com/wiki/Category:Blocks
							- own game engine, VRAGE 2 for destructible voxel-based universe
							  collapsed:: true
							    https://github.com/KeenSoftwareHouse/SpaceEngineers
								- Keen Software House developed and utilizes a video game engine called VRAGE. VRAGE stands for "volumetric rage" and/or "voxel rage".[15]
								- VRAGE 1.0 open-sourced
								  collapsed:: true
								    https://github.com/KeenSoftwareHouse/Miner-Wars-2081
									- The first iteration of VRAGE, VRAGE 1.0, was built and tailored specifically for Miner Wars 2081 and the game’s need for destructible voxel terrain and an open-world. With the open source release in 2013 of Miner Wars 2081, the VRAGE 1.0 engine was also open sourced, under a restrictive commercial license.[9]
								- VRAGE 2.0 is still under development.
								  collapsed:: true
								    https://github.com/KeenSoftwareHouse/SpaceEngineers
									- Description
									  collapsed:: true
										- Its core feature is volumetricity of the environment. Volumetric objects are structures composed from block-like modules interlocked in a grid. Volumetric objects behave like real physical objects with mass, inertia and velocity. Individual modules have real volume and storage capacity and can be assembled, disassembled, deformed, and destroyed.
										- The second iteration of the engine, VRAGE 2.0 is currently in development and powers the studio's latest games, Space Engineers and Medieval Engineers.
										- VRAGE 2.0's core feature is volumetricity within the environment. Volumetric objects are structures composed from block-like modules interlocked in a grid. Volumetric objects behave like real physical objects with mass, inertia and velocity. Individual modules have real volume and storage capacity and can be assembled, disassembled, deformed and destroyed. Due to Medieval Engineers development, VRAGE received a fresh upgrade: structural integrity and DirectX 11 rendering.
									- Key features
									  collapsed:: true
										- Real Physics
										  collapsed:: true
											- Planets, moons, asteroids (see more info - http://blog.marekrosa.org/2015/11/planets-because-you-wanted-them_12.html)
											- All objects have volume – volumetric objects and voxel terrain
											- Static and dynamic objects
											- Destructible, deformable and persistent environment
											- Super-large worlds – game area spans to 6.6 astronomical units. More info: http://blog.marekrosa.org/2014/12/space-engineers-super-large-worlds_17.html
										- Havok Physics and Havok Destruction
										  collapsed:: true
											- Volumetric Objects
											- Modular block-like structures interlocked in a grid
											- Block sizes: 0.25m,0.5m and 2.5m
											- Example usage: space ships, space stations, asteroid stations, castles, fortifications, wooden catapults and more
										- Voxel Terrain
										  collapsed:: true
											- Free-form volumetric surface
											- Multi-material, mineable and fully destructible
											- Multiple levels of LOD transition*
											- Procedurally generated in real-time. More info: http://blog.marekrosa.org/2014/12/space-engineers-super-large-worlds_17.html
											- Example usage: asteroids in Space Engineers, landscape in Medieval Engineers
										- Rendering Engine
										  collapsed:: true
											- Deferred shading
											- Dynamic and deformable geometry
											- Real-time dynamic global illumination - ambient, environment and reflection maps
											- Procedurally generated grass
											- Deferred lighting with soft-shadows – sun, point, hemispheric and spot
											- Particle effects and particle editor
											- Post-processing effects - HDR, SSAO, FXAA (anti-aliasing), Vignetting, Chromatic aberration
							- Used to use CryEngine/Amazon Lumberyard for rendering ?
							- Havok is physics engine
					- _Cheap_
					  collapsed:: true
						- _Unreal_
						  collapsed:: true
							- Voxel Plugin by CodeSpartan
							  collapsed:: true
								- Cons
								  collapsed:: true
									- Limited terrains
									  collapsed:: true
										- create plains, hills, mountains or even asteroids
										- 1 biome?
									- Might not support the latest version 4.21
								- https://www.unrealengine.com/marketplace/voxel-plugin
						- _Unity_
						  collapsed:: true
							- _Smooth terrain_
							  collapsed:: true
								- Voxeland
								  collapsed:: true
									- Pros/Cons
									  collapsed:: true
										- Pros
										  collapsed:: true
											- It's been around since 2013 so likely to stick around
											- Utilises MapMagic World Generator for polygons or procedural terrain for voxels
											  collapsed:: true
											    https://youtu.be/vrs-XA1-ME8
												- When using Voxeland together with MapMagic you can create biomes
												- MapMagic
												    https://assetstore.unity.com/packages/tools/terrain/mapmagic-world-generator-56762
											- Used by Subnautica, a highly rated and good looking game (but it has issues with draw distance)
											  collapsed:: true
											    https://www.youtube.com/watch?v=uePLsB1AzCQ
												- Evidence
												    https://forum.unity.com/threads/voxeland-voxel-terrain-tool.187741/page-6#post-1505358
											- You can scale objects to be any size
											- Can make planets in combination with the Space Graphics Toolkit
											  collapsed:: true
											    https://forum.unity.com/threads/voxeland-voxel-terrain-tool.187741/page-28#post-3190864
												- Octree - scalable to huge worlds
												- https://assetstore.unity.com/packages/tools/level-design/space-graphics-toolkit-4160
												- https://forum.unity.com/threads/50-off-space-graphics-toolkit.147954/
											- MegaSplat allows easy painting terrain with different biomes
											    https://www.youtube.com/watch?v=uqhzsCCekjk
										- Cons
										  collapsed:: true
											- Doesn't use dual contouring so it's not completely smooth terrain + can't create cubic blocks e.g. for building. No plans to change as it'd require altering the entire plugin
									- https://assetstore.unity.com/packages/tools/terrain/voxeland-9180
									- Support thread
									    https://forum.unity.com/threads/voxeland-voxel-terrain-tool.187741/
									- Issues/bug report
									    https://gitlab.com/denispahunov/voxeland/issues
								- Ultimate Terrains
								  collapsed:: true
									- Pros
									  collapsed:: true
										- Uses dual contouring unlike Voxeland - this means terrain is smoother and you can create cubic blocks if desired
									- Cons
									  collapsed:: true
										- Has been around since early 2016 but didn't have official ongoing support and updates until mid 2018
										- Quite a bit of popping
										    https://www.youtube.com/watch?v=SnbsGUerFRM
									- https://assetstore.unity.com/packages/tools/terrain/ultimate-terrains-voxel-terrain-engine-31100
							- _Blocky/cubic-only_
							  collapsed:: true
								- Voxel Play
								  collapsed:: true
									- https://assetstore.unity.com/packages/templates/systems/voxel-play-106618
					- _Expensive_
					  collapsed:: true
						- ~$3k TerrainEngine for Unity
						  collapsed:: true
						    Temporarily unavailable
							- Pros/Cons
							  collapsed:: true
								- Pros
								  collapsed:: true
									- Looks very high quality graphics, fast and emulating physics (wind blowing) on thousands of trees
									    https://youtu.be/rD6z9g1xyZE
									- Good Reviews from those who have it,
								- Cons
								  collapsed:: true
									- Not currently unavailable, waiting on a new release
									    https://forum.unity.com/threads/terrainengine-voxel-terrain-smooth-cubic-2d-hexagonal-infinite-procedural-terrain.174595/page-19#post-3816502
									- Very strange history
									  collapsed:: true
									    https://forum.unity.com/threads/terrainengine-voxel-terrain-smooth-cubic-2d-hexagonal-infinite-procedural-terrain.174595/page-19#post-3803167
										- After reading through all 19 pages of this thread I am perplexed by what has gone on here. On the one hand we have a few people claiming they got the program and are very happy with their purchase and on the other hand we have hundreds of people saying they can't even get a reply to an email, a price or even a place to purchase the product.
										- In the beginning it appears you had to PM the author, convince him you are serious (i.e. sound like you work for a game studio) and then, if you were fortunate, you would be given a price and a contract to purchase the program. And I may be mistaken, but from what I read, this had to be paid using a bank check which was to be sent to France?
										- Later people were directed, by Dyox himself, to purchase the program through a company called Junglee, which many did, only to find they were no longer able to get updates due to a falling out between Dyox and the retailer. I'm not sure anybody got their money back or were given the updates they paid for.
										- There never has been a website for this program. Dyox announced that he was going to put up a website (four years after the release date) back in Feb 2017, and even provided some screenshots just to prove it, but the launch date was to be delayed because the prices were wrong. It still hasn't materialized, and expecting anyone to believe you can't put one up in nearly two years is very, very dubious.
										- Now it may be that Dyox isn't a business man, and all evidence points to this, and that he doesn't really like dealing with people, especially tire kickers. And it may be that he really is so busy working on updates that he doesn't even have time to reply to emails. But after five years of hyping the crap out of this program, and five years of people screaming for support or contact of any sort, it makes me wonder why he chose to sell the program in the first place.
										- There is a Trello page up here at https://trello.com/b/KN6UKYhH/terrainengine-updates but it hasn't been updated since January. After looking at the testimonials, screenshots, videos and the Trello board, I'm not willing to say the program doesn't actually exist, but if this is a scam then this is the most elaborate scam in the history of game development.
							- YouTube
							    https://www.youtube.com/channel/UC_YMl5CMzCzirrYC4a9eDQQ
						- $1k Voxel Farm
						  collapsed:: true
							- https://www.voxelfarm.com
							- Pricing
							  collapsed:: true
								- $300/year Indie - UE4 and Unity support; Binary SDK; Windows only
								  collapsed:: true
									- Components are included in binary form. You will be able to extend the Voxel Farm Engine's functionality by using the Voxel Farm APIs. The binary SDK includes multiple examples and full source code for Unity and Unreal Engine integrations.
								- $1k/year Pro - partial source code SDK; multiplatform
								    The PRO license includes the source code for the engine so you can build for other platforms. It does not include the source code for external tools, which is mainly Voxel Studio, and the Voxel Farm cloud solution.
								- $25k AAA - for full source code (2015)
								    https://80.lv/wp-content/uploads/2015/03/voxelfarm-80lv.png
							- Features
							  collapsed:: true
								- They've had Dual Contouring since 2012
								- Import any model and voxelise it
								    https://www.youtube.com/watch?v=4rVsbwfrH88
								- Massive procedural voxel-based worlds
								- Voxel editing/construction (like Dual Universe) maybe 10cm2
								    https://www.youtube.com/watch?v=SyU_ZO586h8
								- Voxel-based occlusion (2015)
								    https://procworld.blogspot.com/2015/08/voxel-occlusion.html
								- Import MagicaVoxel models
								    https://www.youtube.com/watch?v=BIvL3_AGqa8
								- Level of Detail (less detailed if further away)
								    https://www.youtube.com/watch?v=xMXrJjDLNX0
							- Plugins for Unity, Unreal, CryEngine
							- Blog
							    https://procworld.blogspot.com
							- How it works
							  collapsed:: true
								- He's not using voxels as a solution to polygon rendering, he later polygonizes and decimates his voxel data to render in a real-time engine. This is the very first thing he explores.
								- Yes that video is a bit silly, and doesn't really represent at all the strives he's made in this area. Its nothing about optimizing rendering of an existing engine. It's about content generation via procedural generation. He's using voxels to store data of implicit shapes, then uses a dual-contouring algorithm to approximate the voxel data for run-time.
								- IMO the reason his system is efficient (when compared to minecraft, for example) is that he uses a sort of LoD system back at the voxelization stage, so that the implicit shapes are sampled at higher rates (like a tighter grid) closer to the camera. This way he can have very detailed meshes up close, while allowing you to see mountains way off into the distance. No skydomes or area-loading.
							- _Tech demos_
							  collapsed:: true
								- Making the Citadel for Unreal Engine
								    https://youtu.be/vef6GZom1Fk
								- Unity 5 plugin
								    https://youtu.be/aW0odCkOGng
						- ? Atomontage
						  collapsed:: true
						    Unreleased
							- https://www.atomontage.com/
							- The company has completed its initial prototypes. It hopes to create plug-ins for its technology to work with game engines such as Unreal and Unity, and then it expects to launch a beta version in 2019. Atomontage is working with a team in Slovakia.
				- _Related: _General-purpose/polygon game engines
				    intralink2:: https://workflowy.com/#/4375794c2f2f
			- https://www.reddit.com/r/VoxelGameDev
			- https://unitycoder.com/blog/2012/10/18/voxel-resources-engines-for-unity/
			- Related:
			  collapsed:: true
				- Voxel models (free, paid and inspiration)
				    intralink2:: https://workflowy.com/#/264a06ce43a0
				- Voxel modellers/editors
				    intralink2:: https://workflowy.com/#/2b3be138b085
		- SFX
		- HUD/UI
		  collapsed:: true
			- _Game UIs_
				- See [Space](https://workflowy.com/#/f649d71e0a7c)<a href="https://workflowy.com/#/f649d71e0a7c"> </a><a href="https://workflowy.com/#/f649d71e0a7c">Station</a><a href="https://workflowy.com/#/f649d71e0a7c"> </a><a href="https://workflowy.com/#/f649d71e0a7c">13</a><a href="https://workflowy.com/#/f649d71e0a7c"> (SS13)</a>
				    https://tgstation13.org/wiki//images/c/ca/Space_Station_13_2016-09-18_HUD.png
				- 7 Days to Die
				    https://7daystodie.com/wp-content/uploads/2015/12/Alpha_13_New_GUI.jpg
			- _Toolkit UIs_
				- RPG UI Kit
				    https://forums.unrealengine.com/filedata/fetch?id=1212131&d=1488223757
					- https://forums.unrealengine.com/unreal-engine/marketplace/110888-rpg-ui-kit-feedback
				- RPG& MMO UI 5
				    https://d2ujflorbtfzji.cloudfront.net/package-screenshot/8412cee2-2413-47b0-acc5-3add2de02d20_scaled.jpg
		- VFX
		  collapsed:: true
			- Fog/lighting
		- _AI to creatively generate media_
		  collapsed:: true
			- BicycleGAN - uses AI to show you many alternatives of the same picture/outline e.g. coloured shoes, day/night cycle etc
			    http://i.imgur.com/2l7yR9h.png / https://github.com/junyanz/BicycleGAN
				- affinelayer.com/pixsrv - image-to-image demo
			- Progressive Growing of GANs - generates images from a sample of other images
			    http://i.imgur.com/ekLZ97W.png / https://github.com/tkarras/progressive_growing_of_gans
				- https://research.nvidia.com/sites/default/files/pubs/2017-10_Progressive-Growing-of/karras2018iclr-paper.pdf
			- StackGAN - generates images from text descriptions
			    https://github.com/hanzhanggit/StackGAN
			- - copies the style of a picture/video and edits your media in that same way
			    https://github.com/CompVis/adaptive-style-transfer
				- A Style-Aware Content Loss for Real-time HD Style Transfer
		- Visual scripting
		  collapsed:: true
			- Unreal has Blueprints, which are a non-coder friendly way to design and implement pretty much anything that would go into your game.
			- Unity doesn't have this yet (probably will in 2 years time), but you can buy a plugin to do a lot of that stuff for you, Playmaker or Bolt are probably the two best solutions at the moment.
			- If you can't code, you will need to get Playmaker or Bolt if you use Unity, and you will also benefit from a host of other plugins which you might find useful - Unreal has less of an extensive plugin ecosystem.
	- Related: ((632092fc-a990-4d64-9150-855b5615136c))
- SOPs
	- Backup code via Git to an online repo
- # Games to develop
  id:: 63aff1b2-0fe5-4a17-b18f-ea43e026f96f
  collapsed:: true
	- *Idea types*
		- Priority
		  id:: 644c09ab-d5f2-4bcd-b324-8a9a0080269d
			- Game based on my best design ideas notes
			  collapsed:: true
				- Most important in deciding genre
					- ((67375ec1-4b3a-42f5-a8f6-c0cf4ea9c329))
					- ((67375ec1-fd7d-40cb-876f-e9b48e15b402))
					- ((67375ec1-9e66-4b0c-a3a3-9351d55f59c2))
					- ((63734bb5-0a6f-44e9-8bfe-4a0206a1a4a9))
					- ((6353979e-5e39-41d3-b371-6b1d4408ad1d))
					- ((63734bb5-e123-4821-9645-82f2fa2e593d)) : ((6751dba1-f96c-4cd3-83e7-9a309bf2796f))
				- Genre?
					- ((64e9e72d-a085-432d-81de-c7b093613df7))
						- ((63503886-bb79-451d-9faa-58794efb38e7)) but 3D arena
						- ((63503886-8b29-4c86-9c7e-cca4128b1a94)) but smaller arena
						- Unlock a choice of new movement ability from ((63734bb5-0a6f-44e9-8bfe-4a0206a1a4a9)) at every stage
					- Metroidvania like ((6743584d-3395-41d0-b44b-824153afe9fa))
				- Compared to existing games
					- ((675c2b82-ac3c-47c0-9878-08f1c2996360)) but has attack combos like ((63209426-3e95-4515-9877-af2f9f1bfe07)), instead of weapon wheel it has GoW's ((64c4f1ad-bf19-4772-83f0-5ff8ba76ab98))
					- ((63503886-8b29-4c86-9c7e-cca4128b1a94)) but with ((6743818a-9d53-46a4-a673-aee134d4bec8)), abilities and ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) movement
					- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) but with a challenging ((658ecccc-e274-4c73-9eb1-8a1d3eb9a3e5)),
					- ((63734e86-47cc-4360-addf-cf2ded2c066d)) but PvE roguelike
					- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) : ((673bd74e-8b2d-411d-bf75-770ddf835cd3)) but offline, long runs (at least ((63503886-bb79-451d-9faa-58794efb38e7)) length)
					- ((63503886-bb79-451d-9faa-58794efb38e7)) but behind-the-back perspective, jumping, lock-on target,
					- ((63209426-3e95-4515-9877-af2f9f1bfe07)) but has a jump button and crouch instead of ((64c4f1d5-b730-4d9c-930a-9c12371b5195)) and ((64c4f1de-7f99-4a47-95dd-c9a3b6387110))
				- Potential related existing ideas
					- [[SS14]] : ((8488f9ed-04ec-444f-8494-7dc2fd3a79bb)) : ((67433468-6847-418b-979c-3a214dc01be8))
					- ((63b0a2cb-230d-4c06-9f7f-0b507e88badf))
					- ((67375ec2-ae9b-4acf-adce-c6c59fb28551))
			- Over-the-shoulder action roguelike - Project AR
			  id:: 63b0a2cb-230d-4c06-9f7f-0b507e88badf
			  collapsed:: true
				- Ideal to play next to copy ideas from
					- ((644c0bc4-6684-4de8-a27b-51c9f2508ab5))
					- ((63209426-3e95-4515-9877-af2f9f1bfe07))
					- ((632093da-8019-4aa4-b3d4-d9180b8a1d2a))
					- ((63a9ae59-d4b7-4772-9ed3-277fbab4ed34))
					- ((642ea344-df98-4386-9bb4-9a359ee941cd)) / ((6436d7ed-2ffc-4e9c-a880-be463753f07b)) / ((63503886-7d76-4f63-92c6-1b295e1cacb0))
					- ((632cf632-35b8-4d56-adc5-f97d144609f9))
					- ((632d02af-2c75-415e-b20b-0a44238c96e8))
					- ((632093db-d4fd-4216-93b6-564f99899c16))
					- ((6753b335-cb84-44c6-ad40-7209c216770e))
					- ((63503886-8b29-4c86-9c7e-cca4128b1a94))
				- # Project plan
					- ## Goals
						- ### Features
							- The best feeling 3D action combat game
							  e.g. ((63734e86-47cc-4360-addf-cf2ded2c066d)), ((632093da-8019-4aa4-b3d4-d9180b8a1d2a)), ((632d02af-2c75-415e-b20b-0a44238c96e8)), ((62d447c3-1697-44f5-8b10-040563bc1698)), ((63209426-3e95-4515-9877-af2f9f1bfe07)); ((632d02ac-e241-4bee-897b-97682e44733a)), ((632093db-5f19-44b7-8ca3-6de20a8b30ad)), ((638e80f1-76fd-4701-9efc-db2476bffef9)), ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)); Genshin Impact, Wizard of Legend 2; ((632093db-d4fd-4216-93b6-564f99899c16))
								- Related: ((630f97d2-68f2-4ff5-8816-6d455cc4f989))
							- ((644c0bc4-c820-478f-b8d3-60ff3c30d1eb))
							  collapsed:: true
							  e.g. ((67539fca-fd99-4276-9918-22cfc3133fd4)), ((63503886-8b29-4c86-9c7e-cca4128b1a94))
								- Represent highly varied combat styles e.g. Keras Selyrian in [[calibre/Soulbrand - Andrew Rowe (2021)]] (fire, stone, metal sorcery, multiple swords, etc. Slashing fireballs with annihilation mana, or turning them aside with fire, or creating a wind tunnel in the middle of fireballs or gas using wind mana)
								- Can either choose to use 1 of the 3 powers offered, or just convert it into points to spend at a shop for full build/theorycrafting with loadout paths
							- Roguelite
								- With many levels/biomes 
								  e.g. ((632cf632-35b8-4d56-adc5-f97d144609f9)), ((636d5f22-6a6f-4c9c-8c30-8e4fc920a9dd)), ((63503886-8b29-4c86-9c7e-cca4128b1a94)), ((6416d884-7dde-4aa9-a3e9-c83eab1c6332)); ((632093da-8019-4aa4-b3d4-d9180b8a1d2a)) : ((647b5739-f16b-427a-b424-f0d9ca09ff85))
								- Permanent progression
								  e.g. ((63503886-bb79-451d-9faa-58794efb38e7)), ((632cf632-35b8-4d56-adc5-f97d144609f9)), ((636d5f22-6a6f-4c9c-8c30-8e4fc920a9dd))
							- Boss fights 
							  e.g. ((63a9ae5c-0bd2-4144-bdd2-63fe04fc2929)) / ((632093db-42a7-4662-8965-bac77a23d873)) / ((63a9ae53-2d09-427c-b472-57975ca10ea0)) / ((63542962-0114-464e-8d91-b3b3219205fc)) / ((63a9ae59-d4b7-4772-9ed3-277fbab4ed34)) / ((6436d7ed-2ffc-4e9c-a880-be463753f07b))
							- Mob fights 
							  e.g. ((63a9ae53-37dd-4e91-95ba-349e879e6cf9)) / ((632cf632-35b8-4d56-adc5-f97d144609f9)) / ((63503886-8b29-4c86-9c7e-cca4128b1a94))
							- Controller support
							  e.g. ((63734e86-47cc-4360-addf-cf2ded2c066d)); ((632093da-8019-4aa4-b3d4-d9180b8a1d2a)); ((62d447c3-1697-44f5-8b10-040563bc1698)); ((63209426-3e95-4515-9877-af2f9f1bfe07)); ((6753b335-cb84-44c6-ad40-7209c216770e))
						- Undecided
						- ### Non-goals
							- Best graphics
								- Instead stylised like ((644c0bb4-6a5b-4592-b085-b833fc9538e4)) or ((63ff8120-233f-4838-b8f9-fa4acfb7425f)) fan games
							- RPG campaign
							- Multiplayer more than ~10 players (due to netcode limitations for good action combat)
							- Simulation
							  e.g. ((6416d895-e7bf-4c2e-bd46-519ccdcda840)), [[SS13]]
						- ### Differentiating
							- Most similar
								- ((63503886-8b29-4c86-9c7e-cca4128b1a94)) - fantasy theme instead; maybe multi-rooms with similar theme like ((636d5f22-6a6f-4c9c-8c30-8e4fc920a9dd)) rather than giant arenas; roguelite; weapon and armour pickups
								- ((67539fca-fd99-4276-9918-22cfc3133fd4)) - over-the-shoulder; progression tied to enhancing actual parts of body like ((644c0c06-091b-49fa-9d2f-39642d3b4233))
							- ((63734e86-47cc-4360-addf-cf2ded2c066d)) - no ((6436aeff-e574-4def-a50c-64b6d2f18e10)) instead a 3rd non-ult ability; ((6436ad35-0be5-492e-b77a-78c1d468d6fc)) : ((6436ad35-0c4f-4c5a-b594-78dec944e5e5)) is more limited; ((6436aeff-ada8-40ae-a37e-9b164c402056)) maybe not available
							- ((632093db-5f19-44b7-8ca3-6de20a8b30ad)) - no grappling hook for everyone, no ((63a9ae52-9099-4c6e-b53f-04280a990d76)), no battle royale
							- ((632093da-8019-4aa4-b3d4-d9180b8a1d2a)) : ((647b5739-f16b-427a-b424-f0d9ca09ff85)) - roguelite progression; no style meter,
							- ((632cf632-35b8-4d56-adc5-f97d144609f9)) - dash in any direction
							- ((642bf04c-c045-4331-8b1b-993420f21011)) - magic abilities and skill trees;
							- ((63a9ae59-d4b7-4772-9ed3-277fbab4ed34)) - with a skill tree;
							- ((632cd63c-fe84-44cd-bb15-85ce4c054eca)) - with better action combat; with an endless dungeon/roguelite loop
							- ((63503886-bb79-451d-9faa-58794efb38e7))
							- ((6753b335-cb84-44c6-ad40-7209c216770e))
							- ((632093db-42a7-4662-8965-bac77a23d873))
							- Related:
								- ((67702e78-34d6-49db-8054-a53c1fdfc7b3))
								- ((630f97d2-68f2-4ff5-8816-6d455cc4f989)) : ((642e9fae-d440-414e-8e32-26c8ace9e3ce))
					- ## Engine
						- Decide between ((63a9acd6-3dd5-4a11-a446-5d6596cdbfd8)) and Unity
							- ((63a9acd6-3dd5-4a11-a446-5d6596cdbfd8)) as engine. Either using the GDScript language, or TypeScript bindings
					- ## Game modes
						- 2 modes like ((632d02b0-57c8-4213-87c9-e5a3db5712fb)):
							- Escalating arena/dungeon - like ((632cf632-35b8-4d56-adc5-f97d144609f9)) / ((63503886-8b29-4c86-9c7e-cca4128b1a94)) / ((63b1c4cd-a2cf-4c4e-b93a-93c63acde71f))
						- PvP?
							- Battle royale / duels / arena 4v4 like ((62d447c3-1697-44f5-8b10-040563bc1698)) / 5v5 like ((63734e8e-d44a-40b9-8967-da58b8d300ee))
							- Boss / juggernaut mode e.g. 5 v 1
							  collapsed:: true
								- Games with similar mechanics
									- ((64e9e72c-a562-400f-a494-8fe78b41fbaf)) - juggernaut mode
									- Monster Hunter - monsters have multiple stages
									- Elden Ring - bosses with long combos, massive health bars
									- ((6436af07-f2b9-4bb5-9c67-4dce6f32a415)) - [Dragon Knight](https://heroesofthestorm.fandom.com/wiki/Dragon_Knight), [Garden Terror](https://heroesofthestorm.fandom.com/wiki/Garden_Terror), [Triglav Protector](https://heroesofthestorm.fandom.com/wiki/Triglav_Protector), [Immortal](https://heroesofthestorm.fandom.com/wiki/Immortal) - can't be CC'd, immune to certain abilities
										- [Boss monsters](https://heroesofthestorm.fandom.com/wiki/Mercenary_camp#Boss_Camps) - [Archangel, - Heroes of the Storm Wiki](https://heroesofthestorm.fandom.com/wiki/Archangel,)
										- Other monsters - [Punisher, - Heroes of the Storm Wiki](https://heroesofthestorm.fandom.com/wiki/Punisher,) [Sky Temple Guardian, - Heroes of the Storm Wiki](https://heroesofthestorm.fandom.com/wiki/Sky_Temple_Guardian,) [Grave Golem - Heroes of the Storm Wiki](https://heroesofthestorm.fandom.com/wiki/Grave_Golem)
									- ((62e2844f-3eba-403e-ad55-73d00b47065e)) - dragons, https://leagueoflegends.fandom.com/wiki/Baron_Nashor, https://leagueoflegends.fandom.com/wiki/Rift_Herald
									-
					- ## Combat system
						- ((6834ebce-7a8e-4159-965e-b53331953bd9))
						- Movement
							- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)),  ((6743584d-3395-41d0-b44b-824153afe9fa)) and other top movement games abilities all available, however you can only choose one at game start and have to unlock the rest during a run. Maybe can unlock several starting ones over time
							- Normal evade varies in strength depending on equipment (like ((632d02af-9d3a-45b1-ab6d-69f923db836e)) : ((63b1c8b0-988f-4257-8012-44ab056bee0c)) ) or perhaps stats
							- Dashes which have side effects (like ((63a9ae59-d4b7-4772-9ed3-277fbab4ed34)) / ((63a9ae55-9be0-463d-8091-ba0d992765c8)) )
							- Multiple dashes or shorter cooldown (like ((638e80ea-d789-4dfb-943c-66b73f5b3ba1)) / ((62e2844f-3eba-403e-ad55-73d00b47065e)) )
							- Related: ((6436ad35-0be5-492e-b77a-78c1d468d6fc)) : ((6436ad35-0c4f-4c5a-b594-78dec944e5e5))
						- Either
							- Weapon equipped determines "class" (like ((632d02af-9d3a-45b1-ab6d-69f923db836e)) )
								- Pros
									- Players are not locked into a playstyle, and can try the whole variety
							- Can change if you go to a certain location (like Final Fantasy XIV?)
						- Magic
						  collapsed:: true
							- Chests offer either 1 of 3 upgrades to their existing abilities, or 1 of 3 new abilities
								- Generally 1 magic, 1 weapon and 1 movement
							- Either a ((67539fca-fd99-4276-9918-22cfc3133fd4)) giant talent tree or multiple tabbed character screen for all the different disciplines
								- Individual limb/organ - equivalent to ((644c0c06-091b-49fa-9d2f-39642d3b4233)) : ((644c0c05-14f1-4b52-8b3d-1c8f7be15179))
								- Planes of self - equivalent to ((644c0c06-091b-49fa-9d2f-39642d3b4233)) : ((668eb97a-c716-43dc-8034-130ff7358741))
								- Aura - equivalent to ((644c0c06-091b-49fa-9d2f-39642d3b4233)) : ((644c0c05-691f-4e3c-8e13-f1f9e222dc83))
								- Bonds
									- Knowledge domain i.e. ((667319e7-8046-4543-874f-675a647fa8c3)) : ((68207163-0633-47df-93a9-4b90776b06af))
									- People or places i.e. ((67375dae-fd6a-411d-8905-b850cf13d30c))
									- Element or material i.e. ((667dcc66-616f-4f41-8136-a8f61c1c3c7f)), ((666841cc-85c0-4c08-9693-9c1863a5eb24)), ((667dca5a-3f56-446c-80de-384282b38a35))
							- Related:
								- [[Worldbuilding]]
									- ((681dd4d1-4e48-4b48-bd0b-5e709db1cca5))
									- ((63734eb1-85d8-4420-9b5e-5929ed4e383d))
						- ((63531eea-d78d-4e60-a053-0edd8b75764c))
							- "Dynamic Force" - martial art tree based around
							- Weapon variety (like ((632093db-5f19-44b7-8ca3-6de20a8b30ad)) )
							- Additional weapons
								- Hand wraps for a martial artist
								- Bracelets or a chakram
								- Books/grimoires like ((63734e95-da7c-4bc5-a615-a231ff184c44))
							- Different hand held items per tree
							  collapsed:: true
								- | Discipline | Title | Item |
								  | Dark Magic | Warlock | Focus |
								  | Elemental Magic | Elementalist | Staff |
								  | Nature Magic | Druid | Rod |
								  | Void Magic | Sorcerer | Ring |
								  | Conjuration Magic | Conjurer | Glove |
								  | Blood Magic | Sanguimancer | Vial of X's Blood |
								  | Death Magic | Necromancer | Gauntlet |
								  | Alteration | Wizard | Staff |
								  | Dynamic Force | Monk | Hand Wraps |
								  | Archery | Archer | Long Bow |
								  | Trickery | Rogue | Twin Daggers / Short Bow |
								  | ? | Cleric | Totem |
								  | Swordsmanship | Blademaster | Twin Swords / Greatsword |
								  | ? | Paladin | Two-Handed Hammer |
								  | ? | Fighter | ? |
								  | ? | Spearman | Spear |
								  | Alchemy | Alchemist | Potion |
								  | ? | Barbarian | Axe |
								  | ? | Bard | Lute |
							- More
								- Focus - can be a skull, gem, chains, heavy necklace, etc
								- Conjurer
								  collapsed:: true
									- [[Mother of Learning]] : ((63a9ada5-4b5a-4285-ac2e-aa03393f670d))
									- ((63a9ae6a-7a6e-44ef-b688-9b27358a0d5e))
									- ((632d02af-2b02-45a3-86e2-52fe7520b541)) : ((63b1e9a1-1a09-48b0-a292-a68d1f831bb1))
								- Wizard
								  collapsed:: true
									- Ideas
										- 1
											- • [School of Abjuration](http://dnd5e.wikidot.com/wizard:abjuration)
											- • [School of Bladesinging](http://dnd5e.wikidot.com/wizard:bladesinging)
											- • [School of Chronurgy](http://dnd5e.wikidot.com/wizard:chronurgy)
											- • [School of Conjuration](http://dnd5e.wikidot.com/wizard:conjuration)
											- • [School of Divination](http://dnd5e.wikidot.com/wizard:divination)
											- • [School of Enchantment](http://dnd5e.wikidot.com/wizard:enchantment)
											- • [School of Evocation](http://dnd5e.wikidot.com/wizard:evocation)
											- • [School of Graviturgy](http://dnd5e.wikidot.com/wizard:graviturgy)
											- • [School of Illusion](http://dnd5e.wikidot.com/wizard:illusion)
											- • [School of Necromancy](http://dnd5e.wikidot.com/wizard:necromancy)
											- • [Order of Scribes](http://dnd5e.wikidot.com/wizard:order-of-scribes)
											- • [School of Transmutation](http://dnd5e.wikidot.com/wizard:transmutation)
											- • [School of War Magic](http://dnd5e.wikidot.com/wizard:war-magic)
								- Other titles - Mage, Archmage, Sorcerer, Magician, Witch, Wizard
								- Other items - wand, staff, ring,
							- Non-combat?
								-
							- Related: ((63b1ece5-5084-4b96-bebd-47a94ba18e5d))
						- Consider
							- ((63a9acd6-3a0d-45d6-9f61-799d514a08ef))
							- ((635397c8-40a0-4ba1-8051-f465aaf22837))
				- # Project AR
				  id:: 644c09ca-44f9-4e56-a61c-ca264ca7cff6
					- Elite disciplines (based on Guild Wars elite professions) - you have to have the base class item in one weapon slot, then the elite in the other
					- Deciding on dashes etc
					- Either:
						- Agility stat. At certain thresholds it becomes a combat roll, dash, two dashes, etc
						- Based on weight of armour, like New World. This raises the question, is there class specific armour? Does New World have that?
						- Weapon determines it
						- Level determines it
				- Related:
					- ((62e8e25a-100d-405c-a67e-434fb979ee55))
					- ((630f97d2-68f2-4ff5-8816-6d455cc4f989)) : ((649b1460-4de6-410c-9367-71103a820e2b)) : ((642e9fae-d440-414e-8e32-26c8ace9e3ce))
			- [[SS14]] : ((8488f9ed-04ec-444f-8494-7dc2fd3a79bb))
			- Adult visual novel
			  collapsed:: true
				- These make tons on Patreon if reviewed well on f95zone
			- Turn-based tactics roguelite or RPG
			  id:: 67375ec2-ae9b-4acf-adce-c6c59fb28551
			  collapsed:: true
				- Ideal to play next
					- ((647b02b4-979e-4e7e-8a91-5a5237186f39))
					- ((632093e2-995e-4689-ae53-a7e18067dbf7))
					- ((632d02b0-248f-49f7-ad94-5ec2fe549bfc))
					- ((632093e1-e4e6-4c84-ae91-1f468cfb7fbb))
					- ((630f97d7-90d9-42db-8bc5-b8ecdcde8020))
					- XCOM 2 modded with classes and Long War
				- Goals
					- Features
						- Deep tactical combat like ((632093e2-053a-453d-a20d-fe0e416381f9)), ((632093e2-9014-4f25-8fed-cf47c045231f))
						- ((644c0bc4-c820-478f-b8d3-60ff3c30d1eb)) like ((632093e2-995e-4689-ae53-a7e18067dbf7)), ((632d02b0-248f-49f7-ad94-5ec2fe549bfc))
						- Random event system like ((63734e8a-f6d9-4a15-8625-a69028becf7a))
						- Procedurally generated battle maps like ((632d02ab-14a1-4cc3-88dd-f9a66bd163e7)), ((632093e1-0978-4a2a-a71f-d0c19f8471cc)), ((630f97d7-90d9-42db-8bc5-b8ecdcde8020))
						- Interesting overmap/metagame, either:
							- Hex map like ((647a61da-49f0-4b37-a77a-3bd15f88e451)), ((63503889-fde0-45be-b636-2d124684d990)), ((6310f284-6246-4f7f-9331-bc4d98902e8c)), ((632d02ab-0498-4fa3-bd00-a823b71576b9))
							- Open world with resources like ((632093e2-f22a-4d08-be41-65311e74c684)), ((644c0bbd-5cf6-4f24-81f4-c590b93f8cec)), ((632d02ab-14a1-4cc3-88dd-f9a66bd163e7)), ((647b02b4-979e-4e7e-8a91-5a5237186f39)), ((632cfe94-c204-4902-80c8-08f0dcd48c13)), ((644c0bbc-3ad1-4de6-a8c9-05033f2f211f))
							- Social sim or narrative like ((6416d895-8b59-4246-8951-28b39e4c744b)), ((644c0bb4-83b8-41d7-86a6-5dbeeada6622)), ((632d02b0-248f-49f7-ad94-5ec2fe549bfc)), ((63734e8a-f6d9-4a15-8625-a69028becf7a))
					- Non-goals
						- Simply lane-based overmap like ((644c0bbc-9a44-4320-a7fc-1ad01f89ddf3)), ((63a9ae56-8f28-4868-8cf5-c84f780c6463)), ((644c0bbd-c768-41cb-b961-6b71aa9e814d))
					- Differentiating
						- ((647b30ab-6bd5-442e-bbfc-9c69ef5693d0)), ((647b2f32-96fa-4d65-b0b8-2f7baf8afbf8)) - instead roguelite not roguelike
						- ((632d02ab-14a1-4cc3-88dd-f9a66bd163e7)) - more fantasy classes
						- Several games - instead needs an endless dungeon mode
							- ((632093e2-053a-453d-a20d-fe0e416381f9)), ((632d02b0-248f-49f7-ad94-5ec2fe549bfc))
						- ((632093e1-e4e6-4c84-ae91-1f468cfb7fbb)) - more interesting overmap
						- ((647b02b4-979e-4e7e-8a91-5a5237186f39)) -
						- ((632093e1-0978-4a2a-a71f-d0c19f8471cc)) - more polish
						- ((644c0bbd-c768-41cb-b961-6b71aa9e814d)) - much more polish, better combat like ((632093e2-053a-453d-a20d-fe0e416381f9))
						- ((632093e1-9f1e-403e-bfeb-3034c60f3e1b))
						- ((647b02b4-979e-4e7e-8a91-5a5237186f39)) - not online-only, with more classes/skills/builds, more interesting overmap/metagame
						- ((630f97d7-90d9-42db-8bc5-b8ecdcde8020))
						- *Upcoming*
							- ((644c0bc4-a245-4628-8417-466836cbee47)) - hopefully has good overmap and build diversity
							- ((644c0bc4-1750-41f7-8bfa-6bdd53793e20))
							- ((644c0bc4-574d-4f2a-b80a-11f7c50dc9a3))
			- ((63a9acd6-3dd5-4a11-a446-5d6596cdbfd8))-based game
			- Simulation
			  collapsed:: true
				- Ideal to play next to copy ideas from
					- ((64e0952a-893f-47f0-9162-90957f77bfab))
					- ((63a9ae57-9cb8-465b-b4f2-7b69a9655cf5))
					- ((64e9e72e-183e-4f57-94e9-fe9c86b43224))
					- ((6318fd52-c87b-4b6c-9ea1-fea756d1d4a8))
					- ((64e0952f-2ca3-4893-8e8d-4df56b20b14c))
				- Project plan
					- Goals
						- Features
							- Can easily scale from one character to a whole colony
							  e.g. ((64e0952a-893f-47f0-9162-90957f77bfab)), ((63a9ae57-9cb8-465b-b4f2-7b69a9655cf5)), ((6318fd52-c87b-4b6c-9ea1-fea756d1d4a8))
							- Life skills are enjoyable
							  e.g. ((6416d895-e7bf-4c2e-bd46-519ccdcda840)), ((632d02af-2c75-415e-b20b-0a44238c96e8)), ((632d02af-9d3a-45b1-ab6d-69f923db836e)), ((64e9e731-e25f-45ba-9adb-f149401e954d))
								- Mining
								  e.g. [[SS13]], ((630f97d8-cbc3-46a7-8174-8df682803cdb)), ((632d02af-9d3a-45b1-ab6d-69f923db836e))
								- Fishing
								  e.g. ((6416d895-e7bf-4c2e-bd46-519ccdcda840)), ((632d02af-9d3a-45b1-ab6d-69f923db836e)), ((632d02af-2c75-415e-b20b-0a44238c96e8)), ((64e9e731-e25f-45ba-9adb-f149401e954d))
								- Farming
								  e.g. [[SS13]], ((64e9e731-e25f-45ba-9adb-f149401e954d)), ((632d02a9-cd45-42a1-aad7-8062cc756fee))
							- Needs
							  e.g. ((644c0bb9-13bd-462d-8c29-8c4ef125f89c)), ((632d02a9-cd45-42a1-aad7-8062cc756fee)), ((63ff81d5-9245-4704-8653-c206210ad4c9))
							- Complex jobs with their own deep gameplay
							  e.g. [[SS13]], ((644c0bb6-00c0-4b8b-b30e-7efb5aa6277e)), ((65837445-f7e1-430d-9b40-0adba3e12226)) , ((65706a6f-cee2-4cb3-9fa1-15b60ef703a5))
								- Policing
								  e.g. ((64e0952d-12e2-4074-8a1b-9fe7acc00b49)), ((644c0bb6-00c0-4b8b-b30e-7efb5aa6277e)), [[SS13]]
								- Trading
								  e.g. ((632cfe94-c204-4902-80c8-08f0dcd48c13)), ((632d02a9-cd45-42a1-aad7-8062cc756fee)), ((63542965-aaa8-4872-b7bb-026c76092669)), ((632d02ae-e2b7-493e-a9cc-1fcfddc0e9de))
							- Can swap between first- and third-person POV
							  e.g. ((6416d895-e7bf-4c2e-bd46-519ccdcda840)), ((632cd63c-fe84-44cd-bb15-85ce4c054eca))
							- Futuristic setting setting with inequal distribution of wealth, to allow for a wide-range of technology and jobs
							  id:: 65837c2c-0ac4-46c0-948d-e2be48cd5f79
							  e.g. ((632d02a9-cd45-42a1-aad7-8062cc756fee)), ((63ff81d5-9245-4704-8653-c206210ad4c9)), ((64e0952a-893f-47f0-9162-90957f77bfab)), ((644c0c03-17cf-4c6f-8bf8-fd1665dbf6c2)), [[SS13]]
								- Space ships and building
								  e.g. ((63542965-246b-4357-817d-b63458858119)), ((64e9e72e-c7e4-4a3b-b14a-bcfb82753ba7)),
							- Random events e.g. [[SS13]], ((632d02a9-cd45-42a1-aad7-8062cc756fee))
							- Videogame physics and motions
							  e.g. ((6350382e-c0b2-45a0-9dd8-99ad68789b59))
								- Unlike ((6416d895-e7bf-4c2e-bd46-519ccdcda840)), ((63542965-aaa8-4872-b7bb-026c76092669))
						- Undecided
							- Multiplayer
							- Game loop
							- Simulates hands
							  e.g. [[SS13]], ((65837445-f7e1-430d-9b40-0adba3e12226))
							- NPCs to do social simulation with
							  e.g. ((632093dd-19f7-4171-a5a0-ab6ed70875d9)), ((63b02dcb-33f9-41fc-8a0a-19baef5f6b81)), ((644c0bb7-9349-4052-a88c-1251b30239cb))
							- Procedural quests to befriend NPCs
							  e.g. ((63734e80-6f3e-4955-a4ed-a7efa5fa0d06)), ((632d02a9-cd45-42a1-aad7-8062cc756fee)), ((6416d895-e7bf-4c2e-bd46-519ccdcda840)), ((644c0bb9-13bd-462d-8c29-8c4ef125f89c))
						- Non-goals
						- Differentiating
							- ((644c0bb6-00c0-4b8b-b30e-7efb5aa6277e)) - ((65837c2c-0ac4-46c0-948d-e2be48cd5f79))
							- ((63542965-aaa8-4872-b7bb-026c76092669)) - ((64e0952b-b4e9-4b8b-8d3d-dbf307f71f46))
							- ((632d02af-9d3a-45b1-ab6d-69f923db836e))
							- ((64e9e733-23d8-4b60-82a4-1ba505f4e452))
				- ((65820a05-ace0-491e-9df5-4e9112136369))
			- Interactive fiction visual novel powered by Stable Diffusion. Setting could be ((63682fad-d46a-4eb4-8463-bf07980b6627)) / ((64e094e9-a492-49a3-bd54-ef19c2955528))
			  collapsed:: true
				- Interactive fiction visual novel starring your own completely custom character, all powered by Stable Diffusion. Based on Thresholder and the game AI Roguelite
				- Free demo includes first world that everyone visits - real world where your character does normal scenario or perhaps straight away into the alien world
				- Recurring characters that fandom knows:
				- - The evil scientist
				- - The tough guy
				- - Female spy/infiltrator
				- - Cutesy petite girl
				- They have a high likelihood of escaping and surviving
			- ((63734d0a-a726-4fed-970e-7da77d3faa44))'s anti-dating sim visual novel UnLove
			  collapsed:: true
				- Initial discussion
				  collapsed:: true
					- Working title: Unlove
					  MC is a male working in a halfway house for those with mental problems
					  THe basic premise is you do NOT want these girls getting attached to you. Every route is a bad end
					  However the girls are all cute and such (pick me/trendy girls) but very fucked up emotionally. Cute but undateable
					- the one Jimbob and I stopped working on because it was too much work
					- it's an interesting premise which hasn't been done before, and people are usually looking for unique shit in VNs
					- 14m
					- so what's the objective if every ending is bad?
					- 13m
					- to achieve a healthy outlook in life, even if that means being alone
					- not everything has to be about loving others :)
					- 13m
					- think it'd work better if there are tons of bad endings, but there's a few good ones. maybe those revolve around finding a woman outside this halfway house
					- or becoming a monk, etc
					- 12m
					- already missed the point, lmao
					- well, if you're interested, you can hit us up. but if you steal it, I'm gonna come to london and beat your ass
					- 11m
					- lmao
					- not sure I like the idea. I like the base of "anti-dating sim" but I'd want to go in a different direction
					- 9m
					- well, its more of Jimbob's concept to begin with. The start was an entirely different concept to what I lead him too and we both agreed on it
					- 8m
					- I think it'd be funnier and interesting with ends like - you have to brainwash Katie to get a loving relationship with her, you have to murder Amber's family, you have to turn Rebecca into a zombie, etc
					- 7m
					- memeworthy is good and sells to youtubers and influencers.
					- but unlove was supposed to be a more grounded experience, about the dangers of trying to get with a pick me girl, or someone with mental issues and trying to "fix them" as it were
					- and then a quick and abrupt mental spiral downwards, once you got stuck in their routes. You can break up with them at anytime or break contact, but if you keep going, it just gets worse
					- Jimbob is a fucked up person, because while we were still in the planning phase, he was talking about how much he was gonna enjoy tormenting the protagonist
					- not that it left the planning phase lmao
				- Personalities
					- BPD
					- Depressed
					- Stalker
					- Sociopath
					- Baby-crazy
					- Bipolar
					- Secret slut
					- Sex addict
					- Hoarder/bad hygiene
					- Social media addict
					- Flake - always cancels at last minute, reschedules, only free for a bit, travels often
					- Perfect girl who turns out to be a lesbian
					- Girl who's addicted to raving, ecstasy and alchool
				- My idea
					-
		- ((632cf49f-a6f7-4d2d-b3a5-3ee44968263e)) as core
		  id:: 63ff802e-0425-4bc9-b768-0e3393b09e0b
			- [[SS14]]
				- {{embed ((63aff72d-eaa8-45ec-8719-35c05d1daecc))}}
			- ((6350382e-c0b2-45a0-9dd8-99ad68789b59)) : ((63b03b3e-857f-4798-bba3-027e11a0abe3))
				- {{embed ((63b03b3e-857f-4798-bba3-027e11a0abe3))}}
			- ((6350388d-53e9-47f4-901d-862913d53e85)) : ((63b00452-5086-4637-82c9-4963f025df76))
			  collapsed:: true
				- {{embed ((63b00452-5086-4637-82c9-4963f025df76))}}
			- ((638e80ec-616a-4d85-a1bb-3a57bcd2dc93)) : ((63b02e5d-b499-400f-95e7-12ce3709c229))
			  collapsed:: true
				- {{embed ((63b02e5d-b499-400f-95e7-12ce3709c229))}}
			- Making a 3D everything game but not built on SS3D
			  id:: 644c09ca-8b6b-4c8e-9c52-fff4f9d348b7
			  collapsed:: true
				- Stages
					- 3D open world - everything climbable like ((64e0952a-37d7-4849-873b-3ef6483fac07))
					- Resource gathering like New World
					- Combat - like Devil May Cry, Genshin Impact, Diablo 4
					- SS13-like deep activities/jobs
					- Magic - magic crafting like Minecraft mods, crazy spells like Skyrim mods,
					- Procedural activities - like Skyrim radiant quests, No Man's Sky
					- Crafted content - like Skyrim expansion mods
			- ((6436aefb-b837-4985-a2a0-4922bcce7199))
			  collapsed:: true
				- {{embed ((658c093c-23f7-4cba-aff4-28daf99f8e51))}}
		- ((6436aefb-c23d-44d1-a9d7-3898b173f2e2))
			- ((638e80ec-616a-4d85-a1bb-3a57bcd2dc93))
			- ((638e80ec-ef2e-4099-9c4d-d18e1d685097))
		- Decompiled games as core
			- Naruto-based project ((643839c5-593c-421d-9d75-4dd9d694851e))
				- {{embed ((643839c5-593c-421d-9d75-4dd9d694851e))}}
				- *Unreal Engine*
					- ((63734e86-47cc-4360-addf-cf2ded2c066d))
				- ((6436aeff-1a52-4356-94a8-18ac35e09ff8))
		- ((63a9acd6-28fe-438e-9bf8-c876831447cb))
			- {{embed ((63a9acd6-28fe-438e-9bf8-c876831447cb))}}
		- ((62e8e25a-100d-405c-a67e-434fb979ee55))
		- ((642e9fae-d440-414e-8e32-26c8ace9e3ce))
- # Game Elements
  id:: 632cf690-622d-4e95-9bfe-0927acacc7dd
	- Copy the CoE alpha client progression method (see ((6436af09-6570-4268-95e5-b91edc3df569)) )
	- Animation and controls
	  collapsed:: true
		- Controller/Platform
		  id:: 63734bb5-e123-4821-9645-82f2fa2e593d
		  collapsed:: true
			- ((6751dba1-f96c-4cd3-83e7-9a309bf2796f))
			- # Common controls
			  id:: 67703070-3a64-4a45-8534-ecc270b74813
				- `A` = Jump and `B` = Evade/Dodge/Dash
				  id:: 67702e78-34d6-49db-8054-a53c1fdfc7b3
				  collapsed:: true
					- Example games
						- Yes
							- ((62d447c3-1697-44f5-8b10-040563bc1698))
							- ((632093db-42a7-4662-8965-bac77a23d873))
							- ((649b1461-cc38-49dd-a8be-f0b18d52ff05))
							- ((632093e3-f744-4984-b5ec-1332218f2373))
							- ((632d02af-9d3a-45b1-ab6d-69f923db836e)) : ((68239b35-c3f1-43f8-b707-25dd4a65ac37))
							- ((6318fd58-0de6-4946-98ef-95fa22f457c6)) : ((68239b35-c3f1-43f8-b707-25dd4a65ac37))
							- ((632093da-8019-4aa4-b3d4-d9180b8a1d2a))
							- ((632d02a6-96eb-4e27-851e-69567cd2fd39))
						- Probably
							- ((66f4563f-1579-4acb-965c-011877de1dac))
						- No
							- On a different button
								- ((63734e86-47cc-4360-addf-cf2ded2c066d)) : ((63a9ae56-4b9c-478f-b6b1-e89effac8f2d))
								- ((632d02ac-e241-4bee-897b-97682e44733a)) : ((644c0bc0-3881-40a8-9bba-92457ceeea43))
							- No jump
								- ((6416d881-7c50-481d-a3ed-16851d598978))
								- ((630f97d8-5e75-445d-9a55-6f2c4f1e517f))
								- ((6753b335-cb84-44c6-ad40-7209c216770e))
							- No dash
								- ((6350388b-832c-47b4-92eb-c65fe8af02a2))
					- Related:
						- ((63734bb5-e123-4821-9645-82f2fa2e593d)) : ((6834ebce-7a8e-4159-965e-b53331953bd9))
				- Games with dodge + sprint on same button
				  id:: 6751d668-824c-49b3-9837-b59a5d7c893f
				  collapsed:: true
					- Meta
						- Some people complain about this on ((632093db-42a7-4662-8965-bac77a23d873)) and wish sprint used Interact button instead
					- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) : ((64e09530-85c0-489e-b882-e52ee6774808))
					- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) : ((ae3be7e2-d53b-482e-a43b-c03f50a3c81d))
					- ((6416d881-7184-425d-acf9-90b93098ee9d))
					- ((632d02a6-96eb-4e27-851e-69567cd2fd39)) ?
					- ((6350388b-267d-471c-a621-4ad795cbf7cd)) : ((6735f984-a300-4547-911d-cc37b51e3aac))
					- ((632093db-42a7-4662-8965-bac77a23d873)) : ((660043d6-f226-4534-902f-0e857e196fa4))
						- Related: ((67ae8383-499f-4951-b598-bf5e82e2c034)) : ((67ae8394-02c2-4970-b7c8-fbc48db1ecf9))
					- ((6416d881-7c50-481d-a3ed-16851d598978)) : ((a3ed77f2-6476-4ecf-8a1d-3dd01c2b3bfd))
				- Heavy + light melee attacks (or corollaries)
				  id:: 6754f1d2-fba1-4e61-96fa-a506e3890924
				  collapsed:: true
					- Has
						- ((63209426-3e95-4515-9877-af2f9f1bfe07))
						- ((632d02ac-e241-4bee-897b-97682e44733a))
						- ((63734e86-47cc-4360-addf-cf2ded2c066d))
						- ((632093db-42a7-4662-8965-bac77a23d873))
						- ((632d02a6-96eb-4e27-851e-69567cd2fd39))
					- Only one attack button but also has charged attacks (hold down button)
					  id:: 677d756b-6d22-424a-a881-ba9f6525225d
						- Pros
							- Keeps the attacks down to using just one button
							- Can have multiple levels of Charge e.g. ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) has 3 levels of charge for Attack spells, plus Ultimates also
						- Examples
							- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) : ((68239b47-d3b3-48dd-81d1-2a9c06adf64f))
							- ((632cd63c-fe84-44cd-bb15-85ce4c054eca))
							- ((63503886-bb79-451d-9faa-58794efb38e7))
							- ((632d02af-9d3a-45b1-ab6d-69f923db836e)) : ((68239b35-c3f1-43f8-b707-25dd4a65ac37))
					- Doesn't have
						- ((632093da-8019-4aa4-b3d4-d9180b8a1d2a))
						- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
						- ((66e97906-5bc2-4864-84b9-bdc570cd9b5b))
				- ((680abbfa-afbd-4b97-86f6-4014f735e28e))
				- ((67702e78-34d6-49db-8054-a53c1fdfc7b3)) + ((680abbfa-afbd-4b97-86f6-4014f735e28e))
				  id:: 6834ebce-7a8e-4159-965e-b53331953bd9
				  collapsed:: true
					- 5+
						- ((63734e86-47cc-4360-addf-cf2ded2c066d)) : ((6754f1dc-7752-4053-bb34-1bdb26ff49fa))
					- 5 slots
						- ((62d447c3-1697-44f5-8b10-040563bc1698))
						- ((649b1461-cc38-49dd-a8be-f0b18d52ff05))
						- ((632d02af-9d3a-45b1-ab6d-69f923db836e)) : ((68239b35-c3f1-43f8-b707-25dd4a65ac37))
						- ((6318fd58-0de6-4946-98ef-95fa22f457c6)) : ((68239b35-c3f1-43f8-b707-25dd4a65ac37))
					- 4 slots
						- ((632093e3-f744-4984-b5ec-1332218f2373)) : ((64e9e732-a23e-4333-812c-d429554b5af4))
						- ((632093db-42a7-4662-8965-bac77a23d873)) : ((67497bc8-2b03-4d8c-a205-e24d0c7811c1))
					- 3 slots
						- ((632093da-8019-4aa4-b3d4-d9180b8a1d2a))
			- ### Action games with notable control schemes
			  id:: 6751dba1-f96c-4cd3-83e7-9a309bf2796f
			  collapsed:: true
				- Meta
					- ((67703070-3a64-4a45-8534-ecc270b74813))
				- ((63209426-3e95-4515-9877-af2f9f1bfe07)) : ((67497bc7-5565-4c36-8951-1ca10d17d5c2))
				- ((632093db-42a7-4662-8965-bac77a23d873)) : ((67497bc8-2b03-4d8c-a205-e24d0c7811c1))
				- ((632093da-8019-4aa4-b3d4-d9180b8a1d2a)) : ((de8b01db-0496-4753-bae2-3c2d16293e38))
				- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) : ((67497bc8-d2bc-46b8-bdd1-e9ace46e7352))
				- ((632d02af-9d3a-45b1-ab6d-69f923db836e)) : ((35221324-7124-4762-bedd-10a253ed3693))
				- ((6712d68e-e434-4b36-8161-b12e6a3c02af)) : ((2eb58632-9f1b-4852-b81d-c143059610fb))
				- ((632d02ac-e241-4bee-897b-97682e44733a)) : ((64e9e733-2bf5-4e5c-a398-c3c79becb86c))
				- ((6751dc2f-275f-49a4-8e0c-2b8b0a0b9ff7)) : ((4951da8d-9a73-4ba4-a65e-a0329dec0421))
				- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) : ((67497bc7-9d7b-401d-9fc6-2885eeeb1603))
				- ((62d447c3-1697-44f5-8b10-040563bc1698)) : ((b46c1034-bf46-44a0-9a7f-acb181d2c499))
				- ((6350388b-267d-471c-a621-4ad795cbf7cd)) : ((6735f984-a300-4547-911d-cc37b51e3aac))
				- ((632cd63c-fe84-44cd-bb15-85ce4c054eca)) : ((bb785503-5b61-4e3a-8894-f7fccfcb0031))
				- ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040)) : ((f78cc8fe-aaa5-428a-af92-4c2b5c129e3f))
				- ((64e9e735-17f6-47c0-8562-4fd90ea1a5f2)) : ((4e0c35a7-df57-4e7f-b7a9-53982530888e))
				- ((644c0bb3-4efa-462f-9800-95f5811527a2)) : ((847c1d7d-3328-4272-a25d-ed7cfe46b15e))
				- ((66e97906-5bc2-4864-84b9-bdc570cd9b5b)) : ((d855732a-9f86-4d97-8328-7e032a7e53cc))
				- ((64e0952a-37d7-4849-873b-3ef6483fac07)) : ((0ce68990-2853-4de5-ac05-36c273bfa87f))
				- ((6318fd58-0de6-4946-98ef-95fa22f457c6)) : ((8e666e85-dee4-4e1c-901b-15ec573e361e))
				- ((65fb4927-e8b8-40e0-81bb-4704c6141cde)) : ((694022b0-c97d-454f-995a-f13950893c7d))
				- ((6743584d-3395-41d0-b44b-824153afe9fa)) : ((67497bc7-f683-4836-ad5b-fafe88c59e10))
				- ((6416d881-7c50-481d-a3ed-16851d598978)) : ((a3ed77f2-6476-4ecf-8a1d-3dd01c2b3bfd))
				- ((65b65c2d-fda8-47eb-9d04-7f0740b50870)) : ((cb3a46c9-bea0-4204-b620-bbde5449b2b4))
				- ((632d02a6-96eb-4e27-851e-69567cd2fd39)) : ((c1cffb0e-bee9-4a5b-a588-7c5f6f52211c))
				- ((632c98cc-51c1-4483-8db2-36a045f7a73d)) : ((60a3e11e-de47-4bd0-82a6-639aa1453d5f))
				- ((63734e86-47cc-4360-addf-cf2ded2c066d)) : ((67375eca-1e56-4a52-8c36-703a9074b33e))
				- ((666aac4e-0231-4fef-9e0a-7d319071ba01))
				- ((63a883ea-de2b-4ab4-b3b1-6caaee385dcf)) : ((aefc3173-8669-43d3-a0b9-5caa1a433ea5))
				- ((63a9ae52-49c6-4187-a324-95dc48c17a46)) : ((e847402e-1b26-4ed3-9445-ae4acb446ec9))
				- ((67375ed1-85f8-41a6-b2e3-8dd1607e53ad)) : ((6a2b8486-c45a-4b2c-93a1-360616dbbbf6))
				- ((6416d884-27d0-4c35-8727-39eca505fdad)) : ((3cee5c83-4f79-4378-bbb9-e3e0bd73d56e))
				- ((6416d880-7232-47da-9fd0-2c7cea8ed15d)) : ((377d5e47-6252-42a4-bbe4-b2833ff10f43))
				- ## Comparisons
					- ((9ef30981-0d26-4a25-8360-5ec6bf92b1ca))
				-
			- # Controls using a controller (also multiple powers access with 1-click)
				- _Idea game controls_
				  id:: 63a9acd6-28fe-438e-9bf8-c876831447cb
					- ((63734e8e-d44a-40b9-8967-da58b8d300ee))-based RPG 
					  id:: 62e8e25a-100d-405c-a67e-434fb979ee55
					  collapsed:: true
					  (shooter like Destiny + RPG like Skyrim/Witcher)
						- Gameplay modes
							- PvP -
						- _Confirmed buttons_
							- # Xbox/Gamepad
							  id:: 67375ec1-1d06-4f50-b133-d462b73594a1
							  collapsed:: true
								- Meta
								  collapsed:: true
								- `X` = Reload whilst ranged weapon equipped / Heavy Melee whilst melee weapon equipped / Interact
									- Heavy Attack whilst melee weapon equipped
										- Similar to ((632d02a6-96eb-4e27-851e-69567cd2fd39)), which instead uses X for Light Attack and Y for Heavy Attack
									- Interact
									    [from] ((6318fd58-0de6-4946-98ef-95fa22f457c6)) / ((62d447c3-1697-44f5-8b10-040563bc1698))
									- Hold X = sheathe weapons
									    [from] Skyrim
								- `Y` = Ability 3 / Ultimate
								  collapsed:: true
									- Ability slot
									    [from] [((62d447c3-1697-44f5-8b10-040563bc1698))]
								- `A` = Jump
								- `B` = tap for Dodge Roll or Strafe / hold to Crouch / Slide
								  collapsed:: true
									- Tap B = dodge roll / strafe
									    [from] ((62d447c3-1697-44f5-8b10-040563bc1698)) / <a href="https://workflowy.com/#/0743298a09ec">Elden Ring</a>
									- Alternate
										- See [Destiny 2](https://workflowy.com/#/35b3ebca4848) - <a href="https://workflowy.com/#/719c6aef90d5">Controls</a> -
									- Related: [Quick movements](https://workflowy.com/#/57dd87474b8a)
								- `LT` = Aim / Block / Alt Fire
								  collapsed:: true
									- Block if shield
									- Zoom if using a weapon with a scope
									- Alternate fire
									- Perhaps a melee strike with a ranged weapon
								- `LB` = Ability 1
								- `L3` = Sprint
								  collapsed:: true
									- [from] ((6318fd58-0de6-4946-98ef-95fa22f457c6)); ((62d447c3-1697-44f5-8b10-040563bc1698)); etc
								- `L3 directional` = Player Movement
								  collapsed:: true
								- `RT` = Fire / Light Melee whilst melee weapon equipped
								- `RB` = Ability 2
								- `R3` = Light Melee whilst melee OR ranged weapon equipped / Finisher
								  collapsed:: true
									- Light Melee whilst ranged weapon equipped
									    [from] Overwatch / [Star Wars: Battlefront 2](https://workflowy.com/#/2dcb2ce71c0d) /
									- Finisher move. Take less damage during animation?
									    [from] [Destiny 2](https://workflowy.com/#/35b3ebca4848)
								- `R3 directional` = Camera Movement
								  collapsed:: true
								- `Up D-pad` = View Class Abilities during PvP / Favourites Menu during open-world
								  collapsed:: true
									- D-Pad Up = View Class Abilities
									    [from] ((62d447c3-1697-44f5-8b10-040563bc1698)) / <a href="https://workflowy.com/#/22bd29fb8db0">Paladins</a>
									- [Favourites menu](https://skyrim.fandom.com/wiki/Favorites) from ((632cd63c-fe84-44cd-bb15-85ce4c054eca))
									  id:: 6436ad35-3533-4c91-929b-45fab18e88ef
										- Vanilla Favorites in Skyrim:
											- Bind spells/shouts/weapons to `1` to `8` to quick equip
											- Or use the pop-up to quick equip
										- Quickly rebind anything to your item + ability slots (LT/RT/LB/RB/Y/LB+RB/LT+RT)
										- Start off with 3 tabs - All, Weapons and Abilities
										- Have the ability to create custom tabs and be able to set a particular tab to the default opened one (or a setting to always open the last opened tab)
									- ((6436e1bd-6f2e-4e3c-9b97-5081a92864f1))
								- `Down D-pad` = Switch Shoulder Camera (press) / Switch 1st-person and 3rd-person perspective (hold)
								  collapsed:: true
									- [from] ((62d447c3-1697-44f5-8b10-040563bc1698)) - <a href="[A simpler way to organize your work - Workflowy](https://workflowy.com/#/e0d4406b85f0">Controls</a>) - <a href="[A simpler way to organize your work - Workflowy](https://workflowy.com/#/c9396cc6d964">D-pad) Down = Switch Shoulder Camera (press) / Switch 1st-person and 3rd-person perspective (hold)</a>
								- `Left D-pad` = ((6436ad34-4a5f-4145-a8e4-4707422974d2)) 1
								- `Right D-pad` = ((6436ad34-4a5f-4145-a8e4-4707422974d2)) 2
								- `Back` = Quick Menu
								  collapsed:: true
									- Inventory
									    [from] ((632093e3-f744-4984-b5ec-1332218f2373))
									- Game Status - allows easily doing things like summoning vehicle, returning to orbit etc
									    [from] ((6318fd58-0de6-4946-98ef-95fa22f457c6))
								- `Start` = Full-Screen Menu
								- Combos
									- `LB + RB` = Ability slot
									- `LT + RT` = Charged up dual cast / Special weapon ability
									  collapsed:: true
										- e.g. if holding a staff or two-handed spellblade or pair of nun-chucks then it may have a special ability
								- _Unbound buttons_
								- _Not present abilities_
									- Naraka has hold melee button for charged heavy attack
									- Prone
									- `LB` or `R3` - lock-on engage/disengage (use right stick to swap targets)
									- Cover button
									- Grenades (often LB)
									- Special senses e.g. ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040)) senses; ((632093e3-f744-4984-b5ec-1332218f2373)) valuables scanning; ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) Cuff Scan
									- Stances
									    [from] Ghost of Tsushima / Nier 2 / ((649b1461-cc38-49dd-a8be-f0b18d52ff05))?
									- Grappling hooks
										- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)); Halo Infinite; Dying Light 2; Just Cause; ((644c0bb7-b3f2-4c0c-b830-5d7976985142)); ((632093db-5f19-44b7-8ca3-6de20a8b30ad))
								- Mouse and keyboard
								  collapsed:: true
									- `LMB` =
									- `RMB` =
									- `Space` =
									- `WASD` =
						- UI
							- _Recommended_
								- Mini-map with North and all 8 quadrants like ((63734e95-5ad3-4e2f-b3e4-c090bad28154))
							- ((63734e95-5ad3-4e2f-b3e4-c090bad28154))-like
							  collapsed:: true
								- ![image.png](../assets/image_1681321919883_0.png)
							- Breath of the Wild
							    [[Neoseeker - Error 404 : File Not Found](https://cdn.staticneo.com/ew/thumb/6/6f/B_HUD.jpg/662px-B_HUD.jpg](https://cdn.staticneo.com/ew/thumb/6/6f/B_HUD.jpg/662px-B_HUD.jpg))
						- Related:
							- ((6350382e-c0b2-45a0-9dd8-99ad68789b59)) : ((63b0a2cb-230d-4c06-9f7f-0b507e88badf))
							- ((630f97d2-68f2-4ff5-8816-6d455cc4f989)) : ((6436af0a-d40f-4a22-a471-7c672faa0e9f))
					- SS13 (Unitystation, SS14 etc) gamepad controls
					  collapsed:: true
						- https://docs.google.com/document/d/1dcRrXodteS5cdYeHPRdnFopd9t4dCkJTFmAboKWcibw/edit
						- See: [playing SS13 with a controller](https://www.youtube.com/watch?v=W8VOjFjwiI4)
						- [Wait for input manager for unitystation to be sorted out](https://github.com/unitystation/unitystation/issues/953#issuecomment-448505121)
						- Related: [[SS13]] : ((6350382e-ca53-421e-aa3c-3d4fbc94615e))
					- Unnamed RPG
					  collapsed:: true
						- Reload - X ( ((6318fd58-0de6-4946-98ef-95fa22f457c6)) )
						- Sheath/unsheath - hold X (Skyrim) or left/right D-pad (Witcher 3)
						- LT/RT - left/right hand weapons (Skyrim); if two-handed item then left trigger to block (Skyrim) or aim (Destiny); both triggers to dual cast (Skyrim)
						- Melee when using a gun - using RB (Destiny) or R3 (right stick click | Overwatch)
						- Sprint - L3 (left stick click - Destiny) or hold A (Witcher 3/Gears of War) or LB (Skyrim)
						- Crouch - L3 (left stick click - Skyrim) or R3 (right stick click - COD) or B (Overwatch/Destiny 2) or X (Final Fantasy XV)
						- Roll/((644c09aa-cead-4c40-97ad-620a4656d784)) - double tap crouch (Destiny 2 Hunter)
						- Interact - X (Destiny 2) or A (Skyrim/Witcher)
						- _Potential_
							- Lock-on target - R3 ( ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040)) ) or R1 (Devil May Cry 4)
								- Tab targeting/lock on + free roam camera
									- ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040))
									- ((632d02ae-e2b7-493e-a9cc-1fcfddc0e9de))
							- Cover - A ( Gears of War ) or RB ( ((6436aefb-b837-4985-a2a0-4922bcce7199)) )
						- Vehicle/horse - Y ( ((6436aefb-b837-4985-a2a0-4922bcce7199)) ) or B ( ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040)) ) or A (Skyrim
						- Roll - A ( ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040)) - during Combat intent)
						- Strafe - B ( ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040)) - during Combat intent)
						- ((644c09aa-a594-439b-8ba5-c9c3031f970a))
				- ## Example existing games
					- ((632093e5-1f77-49e2-a0e0-60538a424d89))
						- ((632d02af-9d3a-45b1-ab6d-69f923db836e)) : ((35221324-7124-4762-bedd-10a253ed3693))
					- RPG
						- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d))
						- ((632093db-5f19-44b7-8ca3-6de20a8b30ad))
						- ((632093db-42a7-4662-8965-bac77a23d873))
						- ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040))
						  collapsed:: true
							- https://staticdelivery.nexusmods.com/mods/952/images/69-3-1432949983.jpg
							- Images2
								- https://staticdelivery.nexusmods.com/mods/952/images/126-0-1467040893.jpg
								- https://thewitcher3.wiki.fextralife.com/file/The-Witcher-3/ps4_controls.jpg
							- https://thewitcher3.wiki.fextralife.com/Controls
							- [https://witcher.fandom.com/wiki/The_Witcher_3_controls](https://witcher.fandom.com/wiki/The_Witcher_3_controls)
							-
					- ((63734e8e-d44a-40b9-8967-da58b8d300ee))
						- ((62d447c3-1697-44f5-8b10-040563bc1698)) : ((64e9e732-0fc0-4931-a298-972deec4690e))
						- Apex Legends
						  collapsed:: true
							- ![image.png](../assets/image_1667134927548_0.png)
							- PC controls
								- [https://gameplay.tips/guides/6733-apex-legends.html](https://gameplay.tips/guides/6733-apex-legends.html)
								- [https://www.metabomb.net/off-meta/gameplay-guides/apex-legends-controls-pc-playstation-4xbox-one](https://www.metabomb.net/off-meta/gameplay-guides/apex-legends-controls-pc-playstation-4xbox-one)
						- ((6436af07-a6ac-49dd-9329-ee73897c3af8))
						- Overwatch
						  collapsed:: true
							- https://i.ytimg.com/vi/WawW9MttDXo/maxresdefault.jpg
						- Valorant
					- ((632cf072-c2c6-43b5-92f8-55eca18f42b6))
						- ((632d02ac-e241-4bee-897b-97682e44733a))
						- ((630f97d8-5e75-445d-9a55-6f2c4f1e517f))
						- ((6318fd58-0de6-4946-98ef-95fa22f457c6))
					- _Dual-wielding_
						- ((632cd63c-fe84-44cd-bb15-85ce4c054eca))
						- ((6350388b-832c-47b4-92eb-c65fe8af02a2))
					- Misc
						- ((63734e86-47cc-4360-addf-cf2ded2c066d))
						- ((632093e3-f744-4984-b5ec-1332218f2373))
						  id:: 63734bb5-003a-4c39-b20f-010509ec733e
						- Realm Royale
						  collapsed:: true
							- [https://store.steampowered.com/app/813820/Realm_Royale/](https://store.steampowered.com/app/813820/Realm_Royale/)
					- ((6436aefb-b837-4985-a2a0-4922bcce7199)) controls
					  collapsed:: true
						- https://guides.gamepressure.com/gtav/gfx/word/71109935.png
						- https://guides.gamepressure.com/gtav/guide.asp?ID=22277
					- *Multiple controls via one or more buttons*
					  id:: 67375ec1-283f-4b11-b708-551ac123724a
						- ((6436ad34-fec9-4083-bb0e-2876179eceac))
						- ((64384388-3c5e-400d-924c-ef4053a876bf))
						- ((6436ad35-3533-4c91-929b-45fab18e88ef))
						- ((632d02af-9d3a-45b1-ab6d-69f923db836e)) : ((35221324-7124-4762-bedd-10a253ed3693))
						- Ideas
							- Ability wheel picker
							  id:: 6436e1bd-6f2e-4e3c-9b97-5081a92864f1
							  collapsed:: true
								- based on ((6436ad34-4a5f-4145-a8e4-4707422974d2))
								- Either
									- Prevents you from using other face buttons `A/B/X/Y` and `LB/LT/RB/RT` but you can press one of those buttons next to activate the ability
									- Doesn't prevent using those buttons, but selecting the ability has to be done using joystick then a confirm button (e.g. `A`)
						- Related: ((680be129-85c7-4ff5-8db2-b342a4a4b8d0))
				- ## PC keyboard
					- Guild Wars 2
					- ((63a9ae5b-f56f-40d4-85dd-32c5e3459a05))
					- ((6436af07-f2b9-4bb5-9c67-4dce6f32a415))
					  collapsed:: true
						- 5 abilities - QWERT
						- Movement via mouse clicks/drags
				- _Note_
					- CTRL for mantle over short objects + climb up
					- SHIFT to sprint / strafe jump or dash
					- Quick+Charged attacks, rather than Light+Heavy
					  id:: 64cfc03b-d6ac-4c41-ae16-912d9b8fd4a8
					  collapsed:: true
				- ## Communication types
				  id:: 6436ad34-4a5f-4145-a8e4-4707422974d2
					- _All types_
						- Pings
						  collapsed:: true
							- Apex Legends pinging
								- One middle-click to indicate "go there"; two for "enemy sighted there"; hold it to open ping menu
								    Ping menu [https://cdn.gamer-network.net/2019/usgamer/apex_legends_ping_wheel.jpg](https://cdn.gamer-network.net/2019/usgamer/apex_legends_ping_wheel.jpg) Video demo <a href="https://www.youtube.com/watch?v=prBDEKUSPMs">https://www.youtube.com/watch?v=prBDEKUSPMs</a>
							- ((632093e3-f744-4984-b5ec-1332218f2373)) ping wheel
						- Emote picker
							- [from] Guild Wars / ((633b7574-d7f5-4251-9ec0-91420f47f961)) / Battlefront 2 / ((62e2844f-3eba-403e-ad55-73d00b47065e)) / Wild Rift
						- Voice line picker
							- [from] Battlefront 2
						- ((6436af07-a6ac-49dd-9329-ee73897c3af8)) : ((6436e202-ced8-4f97-946f-5fe61cc69fc3))
						- ((6436af07-a6ac-49dd-9329-ee73897c3af8)) : ((6436af07-e54e-4598-beb3-eee56bdef852))
						- Sprays
						- Push-to-Talk
					- _Combos_
						- Battlefront 2 = Emote picker wheel + Voice line picker wheel
			- Controller vs Mouse and Keyboard
			  id:: 65820a05-ace0-491e-9df5-4e9112136369
			  collapsed:: true
			  AKA Gamepad vs M&KB
				- ## For Controller
					- Good to play with so I'm familiar with common control schemes for later solo game development
					- Probably easier muscle memory for how to play a particular game
					- More effective if there's a dodge button since `L3 Directional` allows greater precision than `WASD`
					  collapsed:: true
						- ((667e7bf2-ee27-4d4b-b409-7cc6165b88cb)) : ((6809fcde-f20e-40e1-aad0-8a9953647a29))
					- More comfortable ergonomically for sitting back in a chair
				- ## For Mouse and Keyboard
					- On controllers it's difficult to use `L3 Directional` + D-pad simultaneously, or `R3 Directional` + `X/Y/A/B` since you only have two thumbs
					  id:: 67375ec1-7f56-43a2-8ea6-a70fa03ae29c
						- Though there are pro controllers + Steam Deck has back buttons
					- Some games have so many actions it's difficult to pair it down to a controller
						- [[SS13]]
						- ((64e9e736-d473-45d7-beb3-750800f93638))
							- Though ((632d02af-9d3a-45b1-ab6d-69f923db836e)) managed it
					- Some games have worse UX when you use controllers, often with different UI  e.g. ((632d02ab-0498-4fa3-bd00-a823b71576b9))?
					- Some games place high importance on accuracy and have low auto-aim so it encourages mouse usage
					  id:: 680fb2f1-062f-4ee6-a53c-c39e1819d1ec
						- Examples
							- Side Scroller
								- ((64e0952a-6991-4504-894d-6da07a1d5c41))
								- ((680f3fcc-c403-418f-b9d2-66563831d5db))
							- Topdown
								- ((680abbfe-9dd2-4019-99f4-5d11911a0932))
							- ((632cf072-6f23-43ef-8329-7a7abf11e09d))
								- ((64e9e732-4b67-492b-b577-67d80d651a1f))
						- ### Not
							- ((63503886-bb79-451d-9faa-58794efb38e7)) - has generous auto-aim
				- ## Unclear
					- KB+M for 1st person e.g. FPS, and Strategy | Controller for 3rd person e.g. racing, platformer, RPGs
				- ## Conclusion
					- Prefer gamepad if possible for muscle memory aspect alone
			- Controller limitations
				- _Ideally minimalistic enough that it can be played via controller, though if it's online it'll need to be PC for the keyboard chat unless it's voice chat-only_
				- _PC game with in-depth magic system because you have a mouse and can use a hotkey bar_
					- ((632093e2-053a-453d-a20d-fe0e416381f9)) hotbar
					  id:: 67375ec1-bd4d-44fe-a046-932d98df868d
					  collapsed:: true
						- https://steamcdn-a.akamaihd.net/steam/apps/435150/ss_5034004fa3690a17da2c266bc577e8aa54e2f3ef.1920x1080.jpg?t=1561485554
					- skill bar [Guild Wars]
					- inventory bar [SS13]
					- _Not much depth_
						- ((6436af07-f2b9-4bb5-9c67-4dce6f32a415))
				- ConsolePort for ((633b7574-d7f5-4251-9ec0-91420f47f961))
				  id:: 6436ad34-fec9-4083-bb0e-2876179eceac
				  collapsed:: true
					- [https://github.com/seblindfors/ConsolePort](https://github.com/seblindfors/ConsolePort)
					- Xbox One controls
					    [https://youtu.be/aIxqPcaDYRo](https://youtu.be/aIxqPcaDYRo)
						- LT = SHIFT on PC (hold to access an alternate set of abilities, swaps all existing action buttons)
						- LB = Action button 4
						- L3 = LMB on PC
						- RT = CTRL on PC (hold to access an alternate set of abilities, swaps all existing action buttons)
						- RMB = Action button 5
						- R3 = RMB on PC
						- X = Action button 1
						- Y = Action button 2
						- A = Jump
						- B = Action button 3
						- D-Pad = more action buttons (6/7/8/9)
						- Hold LT + RT (hold to access an alternate set of abilities, swaps all existing action buttons)
				- _Console games with in-depth magic systems you can pause_
					- ((632cd63c-fe84-44cd-bb15-85ce4c054eca))
					- Divinity: Original Sin
				- _Console games with limited magic systems because you can't pause_
					- ((63734e8e-d44a-40b9-8967-da58b8d300ee))
					- ((63734e92-d7d1-4094-b3e9-97390685ebc0))
					- _Battle Royales_
						- ((6350388b-832c-47b4-92eb-c65fe8af02a2))
						- Realm Royale
					- _Unsorted _
						- Magicka
						- ((64e9e735-2410-4399-8316-ce4e62cd9d73))
					- _Other?_
						- ((63a9ae55-9be0-463d-8091-ba0d992765c8))
						- ((6318fd58-0de6-4946-98ef-95fa22f457c6))?
						- ((63209426-3e95-4515-9877-af2f9f1bfe07))?
						- Dark Souls?
				- _Idea:_ prepping more complicated magic in advance?
					- Witcher creating potions etc
					- Skyrim using an arcane enchanter or whatever to make limited use staffs
					- Skyrim mod with that spell that lets you store several spells which can be used simultaneously
				- _Related:_ ((63734eb1-85d8-4420-9b5e-5929ed4e383d))
			- ((680be129-85c7-4ff5-8db2-b342a4a4b8d0))
			- Xbox Elite Wireless Controller (4 extra paddles)
			- [Learning Resources]
				- Find control schemes for games
					- [StrategyWiki, the free strategy guide and walkthrough wiki](https://strategywiki.org)
		- FPS games with third person (base)
		  collapsed:: true
			- See FOSS, in particular:
			    intralink2:: https://workflowy.com/#/f81f6bef8cbc
				- Minetest (Minecraft clone)
			- _FPS + TPS_
				- ((632cd63c-fe84-44cd-bb15-85ce4c054eca))
				- ((6318fd58-0de6-4946-98ef-95fa22f457c6))
				- _See_ [Paladins](https://workflowy.com/#/22bd29fb8db0)
			- _TPS_
				- ((62d447c3-1697-44f5-8b10-040563bc1698))
				- ((6350388b-267d-471c-a621-4ad795cbf7cd))
				- Smite
				- https://youtu.be/F_K1PCmga7w?t=2451
			- _TPS with cover systems_
				- See [Grand](https://workflowy.com/#/a7330264241b)<a href="https://workflowy.com/#/a7330264241b"> </a><a href="https://workflowy.com/#/a7330264241b">Theft</a><a href="https://workflowy.com/#/a7330264241b"> </a><a href="https://workflowy.com/#/a7330264241b">Auto</a><a href="https://workflowy.com/#/a7330264241b"> V</a>
				- DayZ
				- The Division
				- [Watch_Dogs](https://store.steampowered.com/app/243470/Watch_Dogs/)
				  id:: 67375ec2-42b2-448c-8892-df931f45ad63
					- Mods
						- [Koschei's Brutalist Merge at Watch Dogs Nexus - Mods and community](https://www.nexusmods.com/watchdogs/mods/325)
				- ((64ccc63b-e037-484e-ba92-d7fcd6095644))
		- 3D Movement and controls
		  id:: 63734bb5-0a6f-44e9-8bfe-4a0206a1a4a9
		  collapsed:: true
			- Example games
				- Theoretical combo
					- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) with ((64e0944d-aa38-44bd-9d74-c50867f50b56)), ((644c09aa-55f9-41e1-b24e-eb71fc8231c7)), ((650820a5-74ab-4bcf-a106-c4226c774930)) from sliding instead of timed jump from ground, ((6743589d-2933-4044-8368-638019e898c9))
				- ## Best
					- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) : ((64cfc00c-d01f-4d32-84fd-81deb64c78b1))
					  i.e. ((674371aa-d3bf-4de8-9ce5-7eaab0f67c91)), ((650817b2-ce64-4a2d-b37f-75a497ff236b)), ((650820a5-74ab-4bcf-a106-c4226c774930)), ((64e0944d-1d69-4819-8e3e-cc153dcf8de7)), ((65081384-d16c-4e7b-a4f5-a30e36747d69)), ((644c09aa-0a1f-40dd-aae1-45a6b1ed7b28)), ((64e0944d-121f-49f5-8229-d029b9cd957e)), ((680ffb4d-2330-4476-b004-361ea12c9e81)) : ((65082771-3643-432c-aea6-9538db99a2a0)), ((67435751-d79b-4aad-adff-4bb087eb073c))
					- ((6743584d-3395-41d0-b44b-824153afe9fa))
					  ((674355e1-56c1-49a6-bae8-b64e5fa8ada3)), ((644c09aa-55f9-41e1-b24e-eb71fc8231c7)), ((650817b2-ce64-4a2d-b37f-75a497ff236b)),, ((65081384-d16c-4e7b-a4f5-a30e36747d69)), ((64e0944d-aa38-44bd-9d74-c50867f50b56)), ((67435751-d79b-4aad-adff-4bb087eb073c)), ((650820a5-74ab-4bcf-a106-c4226c774930)), ((67435f07-7eb7-48f6-b2f3-c4af9005baec)), ((67375ec1-c207-4f94-aeb7-fc3c8a43b6d3)); ((6743589d-2933-4044-8368-638019e898c9))
					- ((67dea417-532e-4f40-a398-78a17c7831b0))
					  ((644c09aa-3aef-45bc-81cf-2f6f22323b7a)); ((644c09aa-4b72-48da-ab04-9f3a93c630ab)) / ((650817b2-ce64-4a2d-b37f-75a497ff236b)), ((644c09aa-55f9-41e1-b24e-eb71fc8231c7)); ((680ffca8-9d11-47e4-ae37-affa31c2bfb5)) : ((680ffcb8-0654-429b-8a84-d57a9f6e2336)); ((680ffb4d-2330-4476-b004-361ea12c9e81)) : ((680ffb52-6e0f-4e5c-aed9-73feba0d65da)); ((67375ec1-03ff-4d2b-ac62-99cf061b5fb5)); ((64e0944d-1d69-4819-8e3e-cc153dcf8de7))
					- ((644c0bb7-b3f2-4c0c-b830-5d7976985142)) - ((644c09aa-3aef-45bc-81cf-2f6f22323b7a)); ((64e0944d-aa38-44bd-9d74-c50867f50b56)); ((644c09aa-55f9-41e1-b24e-eb71fc8231c7)), ((67375ec1-c207-4f94-aeb7-fc3c8a43b6d3)); ((680ffca8-9d11-47e4-ae37-affa31c2bfb5)) : ((680ffeae-2be5-4328-81be-ad1ae84c0b97))
					- ((632d02ac-e241-4bee-897b-97682e44733a)) - ((644c09aa-55f9-41e1-b24e-eb71fc8231c7)), ((64e0944d-aa38-44bd-9d74-c50867f50b56)), diving roll, gliding, ((644c09aa-3aef-45bc-81cf-2f6f22323b7a)), bullet jump; ((67375ec1-c207-4f94-aeb7-fc3c8a43b6d3))
					- ((6436af07-a6ac-49dd-9329-ee73897c3af8)) - vertical climbing, double jump, dashing, teleporting; sliding; flight
					- ((648f9073-a167-46c9-8f87-3502ba37521e)) - double jump, dashing, sliding, grapple hook, ground slam
					- ((64e9e72d-680a-41ca-a8a4-e4af2cc8a574)) - superspeed; vertical wallrunning; high jump; ((68109864-f90f-4eda-94ad-04bb36f0e03e)); ((64e0944d-1d69-4819-8e3e-cc153dcf8de7))
					- ((64e9e733-aa9c-4bda-9605-56045896e07a)) - sliding; dashing; mantling; grapple hooking; ((674371aa-d3bf-4de8-9ce5-7eaab0f67c91)); forward roll; ledge climbing horizontally and vertically | 2: hand gliding; wallrunning;
					- ((634bc201-ab66-494b-8738-826601b04f57)) - ((64e0944d-aa38-44bd-9d74-c50867f50b56)); ((644c09aa-3aef-45bc-81cf-2f6f22323b7a)); ((650817b2-ce64-4a2d-b37f-75a497ff236b)); ((65d9b95c-2c6f-4472-9e98-98265c125c35)); ((67375ec1-c207-4f94-aeb7-fc3c8a43b6d3))
					- ((632d02a6-96eb-4e27-851e-69567cd2fd39)) - ((644c09aa-3aef-45bc-81cf-2f6f22323b7a)); ((644c09aa-4b72-48da-ab04-9f3a93c630ab)) / ((650817b2-ce64-4a2d-b37f-75a497ff236b)); ((64e0944d-1d69-4819-8e3e-cc153dcf8de7)); ((65d9b95c-2c6f-4472-9e98-98265c125c35)) : ((6810b911-f77a-4dba-a8d5-2e97f4ed0198))
					- ((680a4092-6dc1-4dd8-a657-cc94ac67fbca)) - ((65d9b95c-2c6f-4472-9e98-98265c125c35)), ((68109889-bc64-4c7f-946b-0c778fba0a48)), ((64e0944d-1d69-4819-8e3e-cc153dcf8de7)); ((644c09aa-3aef-45bc-81cf-2f6f22323b7a)); ((65d9b95c-2c6f-4472-9e98-98265c125c35)); ((680ffca8-9d11-47e4-ae37-affa31c2bfb5)) : ((680ffeae-2be5-4328-81be-ad1ae84c0b97))
					- ((6436af06-ccc4-48c7-9d49-9dbe17c2b305)) - vertical wallrunning; vertical wallsliding; wallkicking; horizontal wallrunning; grappling hook; double jump; sliding; gliding;
					- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) - dash, stomp jump, air dash, gliding, vertical wallrunning, grapple hooking; ((65d9b95c-2c6f-4472-9e98-98265c125c35)) : ((6810b911-f77a-4dba-a8d5-2e97f4ed0198))
					- ((6318fd58-0de6-4946-98ef-95fa22f457c6)) - includes triple jumping, strafing, ground slides, mantling; ((644c09aa-cead-4c40-97ad-620a4656d784)); ((649b122d-f250-4877-9239-a89c9fa5c47f))
					- ((632093da-8019-4aa4-b3d4-d9180b8a1d2a)) - ((644c09aa-4b72-48da-ab04-9f3a93c630ab)); ((644c09aa-e0b8-4a0e-8e2b-2e122b5f7768)) : ((644c09aa-c5f7-4cb1-b6f8-9dc7749b2c4a)) + ((644c09aa-e583-4b9c-b4d5-84f9cb714651));
					- ### Unplayed but expected
						- ((680fda33-4000-4c81-b615-db8f61d44523)) - ((680ffca8-9d11-47e4-ae37-affa31c2bfb5)) : ((680ffeae-2be5-4328-81be-ad1ae84c0b97)); ((64e0944d-1d69-4819-8e3e-cc153dcf8de7))
						- ((680fd87a-3c64-41e7-b4c2-91645b530e13))
						- ((644c0bb4-4d37-4ef9-a8b7-7fcfd20887f4))
						- ((680fd495-07d9-436d-acaf-2e55cebedd5c))
						- ((66f4563f-1579-4acb-965c-011877de1dac)) - ((680ffca8-9d11-47e4-ae37-affa31c2bfb5)) : ((680ffeae-2be5-4328-81be-ad1ae84c0b97)); ((64e0944d-1d69-4819-8e3e-cc153dcf8de7))
				- ## Lower tiers
					- Closed-source
						- _Tier 2_
							- ((63734e86-47cc-4360-addf-cf2ded2c066d))
							- [DeathSprint66](https://store.steampowered.com/app/1273560/DeathSprint_66?snr=1_25_4__318) - horizontal wallrunning, skateboarding, sliding
							- ((6350388b-267d-471c-a621-4ad795cbf7cd)) - ((644c09aa-4b72-48da-ab04-9f3a93c630ab));
							- Batman Arkham
							- ((6350388b-832c-47b4-92eb-c65fe8af02a2)) - double jump, teleporting, super jump, skating, flight (levitation)
							  collapsed:: true
								- e.g.
								    [https://www.youtube.com/watch?v=BDmksUkkoKM](https://www.youtube.com/watch?v=BDmksUkkoKM)
								- Ice skating
								    [https://youtu.be/p5YeieUuHXY](https://youtu.be/p5YeieUuHXY)
								- Controls
									- MOUSE1 - left gauntlet
									- MOUSE2 - right gaunlet
									- Q - left gauntlet special
									- E - right gauntlet special
									- SHIFT - movement rune
							- Apex Legends - climbing; grapple hooking; sliding;
							- ((644c0bbe-dfac-42d6-9fba-900d98dfd49b)) - double jump; dash; grapple hooking;
							- Ghostrunner - wall running, ((680ffca8-9d11-47e4-ae37-affa31c2bfb5)) : ((680ffcb8-0654-429b-8a84-d57a9f6e2336)), dashing
							  collapsed:: true
								- [https://www.youtube.com/watch?v=zsjaRHMr088](https://www.youtube.com/watch?v=zsjaRHMr088)
							- [Sunset Overdrive parkour](https://youtu.be/LJlaXGLLo38)
						- _Tier 3_
							- ((630f97d8-5e75-445d-9a55-6f2c4f1e517f)) - dodge roll; climb+mantle; cover
							  collapsed:: true
								- CTRL - Roll / Climb / Mantle
								- SPACE - use Cover
							- Breath of the Wild - gliding; climbing
							- Assasin's Creed  - see Parkour moves
							- Unturned - leaning, third-person/first-person switch, crouch, prone
							  collapsed:: true
								- H - third-person/first-person perspective swap
								- X - crouch
								- Z - prone
						- ((644c0bb4-4d37-4ef9-a8b7-7fcfd20887f4)) - vertical wall running, gliding, superspeed
					- ((632cf49f-a6f7-4d2d-b3a5-3ee44968263e))
						- ((64e0952e-d0e9-4637-bd2c-5eb43ee1ea20))
			- # Movement types
				- _Basic level (e.g. GTA V, Skyrim)_
				  collapsed:: true
					- Jumping
					  id:: 65d9bbdd-a84c-4926-9c75-ed5b9a1b5fd3
					- Sprinting
					  id:: 644c09aa-f79c-490a-8dbd-e15ad0e5d9f8
					- Swimming
					- Crouching
					- FPS normal walk strafing
					  collapsed:: true
						- Destiny 2
						    https://youtu.be/HCI6oocEksk?t=28
				- Climbing
				  id:: 6436ad35-599b-43e0-832f-4e5a1f366369
				  collapsed:: true
					- _Basic (automatically just sticky to edges)_
						- ((6318fd58-0de6-4946-98ef-95fa22f457c6))
					- Vaulting
					  e.g. fences, low cover
						- ((630f97d8-5e75-445d-9a55-6f2c4f1e517f))
						- ((64e9e733-aa9c-4bda-9605-56045896e07a)) - can vault over enemies too
						    [https://youtu.be/TBuCueqP_vw?t=396](https://youtu.be/TBuCueqP_vw?t=396)
					- Sprint vaulting
					  id:: 674371aa-d3bf-4de8-9ce5-7eaab0f67c91
						- ((65d9d75d-1864-4f43-997c-280647515d86))
						- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d))
					- Mantling
					  i.e. gripping edge of platforms to climb up
						- ((644c0bbf-7251-4de0-8772-89dace4b3365))
						- ((644c0bb7-b3f2-4c0c-b830-5d7976985142))
						- ((64e9e733-aa9c-4bda-9605-56045896e07a))
					- _Vertical movement_
					  id:: 6436ad35-1ffe-464d-8ae8-06af3955f1b3
						- Stamina/height-dependent
							- ((64e0952a-37d7-4849-873b-3ef6483fac07)) / ((6416d881-7184-425d-acf9-90b93098ee9d)) - stamina-dependent
							- [Apex Legends - height-dependent](https://youtu.be/nHWnQzTmFhQ)
						- Related:
							- ((6436ad35-0be5-492e-b77a-78c1d468d6fc)) : ((6436ad35-0c4f-4c5a-b594-78dec944e5e5)) + ((65081384-d16c-4e7b-a4f5-a30e36747d69))
					- _Parkour (climbing diagonal surfaces, hanging off ledges, walking across straight-lines, vaulting waist-height obstacles, _
						- Assassin's Creed
						    https://youtu.be/Xg_Dx8xWXis
				- Quick movements
					- Sliding
					  id:: 64e0944d-aa38-44bd-9d74-c50867f50b56
					  collapsed:: true
					  AKA Running ground slide / crouch sliding
						- ((6318fd58-0de6-4946-98ef-95fa22f457c6))
							- [[DESTINY 2 PC Key Binding Guide & Mouse Sensitivity Recommendations - YouTube](https://youtu.be/eZNOkBHiOm0?t=37](https://youtu.be/eZNOkBHiOm0?t=37))
							- 3rd person perspective
								- [Bungie ViDoc – Forsaken Launch and Beyond - YouTube](https://youtu.be/Xpz1Fl8pW0o?t=159)
								- https://youtu.be/jn1dML6RC5w?t=97
						- ((6743584d-3395-41d0-b44b-824153afe9fa))
					- Surfing
					  collapsed:: true
						- ((64e0952a-37d7-4849-873b-3ef6483fac07))
						- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d))
					- Dash
					  id:: 64e0944d-971f-477b-a1b6-bc93d8ac8fc4
					  collapsed:: true
						- Subtypes
							- Forward dash-like
							  id:: 67375ec1-9b8f-42a5-8f5a-e67a7e5ecf84
								- _Straight forward (dash)_
								  id:: 67375ec1-f384-411c-a69f-c55e1930bee8
									- Overwatch - Tracer's Blink; [Genji](https://playoverwatch.com/en-us/heroes/genji/)'s Swift Strike
									- ((6436af07-a6ac-49dd-9329-ee73897c3af8)) - Maeve's Pounce
									- ((6436af07-a6ac-49dd-9329-ee73897c3af8)) - Androxus' Nether Step
									    [https://youtu.be/qjGyIrm9qtQ?t=25](https://youtu.be/qjGyIrm9qtQ?t=25)
									- Genshin Impact - dash
									    [https://youtu.be/TqB-Mm_FxaA](https://youtu.be/TqB-Mm_FxaA)
									- Skyrim - Whirlwind Sprint shout
									    [https://youtu.be/HHJgg7VMAro](https://youtu.be/HHJgg7VMAro)
									- ((6350388b-832c-47b4-92eb-c65fe8af02a2))
									- ((66e97985-9ce5-4533-96c5-5983fff092db)) : ((66e979d3-2d03-4d01-8ac5-4b1e2a66455c))
								- Air dash
								  id:: 650817b2-ce64-4a2d-b37f-75a497ff236b
									- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) : ((65080a57-c93c-4b7b-b55e-bfb0e04358b2))
									- ((634bc201-ab66-494b-8738-826601b04f57)) air dash
									- Subtypes
										- Air melee
										  id:: 6810a8fe-1bf0-4e91-8c58-de2366e04d76
											- ((6743584d-3395-41d0-b44b-824153afe9fa)) - roundhouse kick forward
										- ((644c09aa-3aef-45bc-81cf-2f6f22323b7a)) into air dash
										  id:: 67375ec1-145d-4d00-8d9d-e482390fbc82
											- ((632d02a6-96eb-4e27-851e-69567cd2fd39)) - [double air dash](https://youtu.be/rGdMlJuAdkY) (vertical flip -> forward air dash)
											- ((67dea417-532e-4f40-a398-78a17c7831b0))
										- Weapon attack air dash
										  id:: 67435df5-a002-4c7a-a300-eab5640784cd
											- ((632093db-42a7-4662-8965-bac77a23d873)) - ((66000973-aef2-45fc-b851-ec1fc76cc6fd))
								- Bullet jump
								  id:: 650820a5-74ab-4bcf-a106-c4226c774930
								  AKA forward rolling jump / twisting forward flip / crouch+jump simultaneously
									- ((632d02ac-e241-4bee-897b-97682e44733a)) e.g.   [Example](https://youtu.be/u1sngO7uKVI))
									- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) : ((65080a5c-23c8-482b-a3f1-69829499f7a0))
									- ((6743584d-3395-41d0-b44b-824153afe9fa)) : ((674469b6-1d50-44ff-8333-2902e1c9e788))
									- Related: ((67375ec1-c207-4f94-aeb7-fc3c8a43b6d3))
								- Related: ((649b122d-f250-4877-9239-a89c9fa5c47f))
							- Omnidirectional dash
							  id:: 644c09aa-4b72-48da-ab04-9f3a93c630ab
								- Examples
									- ((67dea417-532e-4f40-a398-78a17c7831b0))
									- ((6350388b-267d-471c-a621-4ad795cbf7cd))
									- ((648f9073-a167-46c9-8f87-3502ba37521e))
									- ((644c0bbe-dfac-42d6-9fba-900d98dfd49b))
										- `B` to Dash
									- ((64e9e733-aa9c-4bda-9605-56045896e07a)) - dodge
									    [[Dying Light: Showcase All Agility Skills - YouTube](https://youtu.be/TBuCueqP_vw](https://youtu.be/TBuCueqP_vw))
									- [[Video Game Dashing) - TV Tropes](https://tvtropes.org/pmwiki/pmwiki.php/Main/VideoGameDashing](https://tvtropes.org/pmwiki/pmwiki.php/Main/VideoGameDashing))
							- Teleport dash
							  id:: 644c09aa-a594-439b-8ba5-c9c3031f970a
								- Forward
									- Evie's Blink ( ((6436af07-a6ac-49dd-9329-ee73897c3af8)) )
									- Koga's Shadow Step ( ((6436af07-a6ac-49dd-9329-ee73897c3af8)) )
									- ((6318fd58-0de6-4946-98ef-95fa22f457c6)) (Warlock)
									    [Destiny: Warlock's Blink  ( Teleport ) - YouTube](https://www.youtube.com/watch?v=gMCU56hxNZ8)
								- Omnidirectional
									- Mal'Damba's Slither ( ((6436af07-a6ac-49dd-9329-ee73897c3af8)) )
							- _Spin strafe_
							  id:: 644c09aa-cead-4c40-97ad-620a4656d784
								- Destiny 2 (Hunter - Marksman's Dodge) - can be sideways or front/back [double tap B/crouch]
								    [https://youtu.be/E67j1ZUQNyQ?t=12](https://youtu.be/E67j1ZUQNyQ?t=12)
								- Naruto: Naiteki
								    https://youtu.be/m12qPr255kM?t=80
								- Shinobi Life Online
					- Diving roll
					  id:: 649b122d-f250-4877-9239-a89c9fa5c47f
					  collapsed:: true
						- ((64ccc63b-e037-484e-ba92-d7fcd6095644)) rolls
						- ((675c2b82-ac3c-47c0-9878-08f1c2996360))
						- ((632d02af-2b02-45a3-86e2-52fe7520b541))
						- Destiny 2 (Hunter - Gambler's Dodge)
						    [- YouTube](https://youtu.be/bZYmgpmljj4?t=62)
						- Related:
							- ((67375ec1-9b8f-42a5-8f5a-e67a7e5ecf84)) : ((650820a5-74ab-4bcf-a106-c4226c774930))
					- ((650820a5-74ab-4bcf-a106-c4226c774930))
					- ((67375ec1-b758-4a5b-9307-327f2143b181)) after ((67435751-d79b-4aad-adff-4bb087eb073c))
					  id:: 644c09aa-0511-4c6b-b537-98f066e5f84e
						- ((6743584d-3395-41d0-b44b-824153afe9fa))
					- Forward shoulder barge
					  collapsed:: true
						- [Destiny 2  - Official Gameplay Reveal Trailer - YouTube](https://youtu.be/jn1dML6RC5w?t=81) (Destiny 2)
						- https://youtu.be/2GG_3X-46Jc
					- Horizontal wallrunning
					  id:: 644c09aa-55f9-41e1-b24e-eb71fc8231c7
					  collapsed:: true
						- ((67dea417-532e-4f40-a398-78a17c7831b0))
						- ((64e0952e-d0e9-4637-bd2c-5eb43ee1ea20))
						- Warframe (jumping up a wall multiple times, or horizontal wall running)
						    https://youtu.be/u1sngO7uKVI?t=101
						- Call of Duty Black Ops 3 - automatic for a few seconds if you're moving horizontally already whilst sprinting + next to a wall
						    [https://youtu.be/_N0bVN4AzTc](https://youtu.be/_N0bVN4AzTc)
						- ((644c0bb7-b3f2-4c0c-b830-5d7976985142)) : [[Titanfall 2 Tips: How To Wall Run Like A Pro - YouTube](https://youtu.be/QaaYz29jMQg](https://youtu.be/QaaYz29jMQg))
						- Related: ((b06fb5f5-c813-48b9-a928-62e1436066a4))
					- Wall mantling
					  collapsed:: true
						- ((644c0bbf-7251-4de0-8772-89dace4b3365)) : [Wall mantling](https://youtu.be/c0iDRuh2GkU?t=224) can be used to jump backwards, upwards or outwards
					- Wall-kicking
					  id:: 644c09aa-79ce-4960-8224-5525e40d1f8c
					  collapsed:: true
					  Initiate a wallrun then quickly kick off for a speed boost
						- ((6743584d-3395-41d0-b44b-824153afe9fa))
						- ((644c0bb7-b3f2-4c0c-b830-5d7976985142))
						- ((644c0bbf-7251-4de0-8772-89dace4b3365))
						- Related: ((65081384-d16c-4e7b-a4f5-a30e36747d69))
					- Boosted speed/jump
					  id:: 644c09aa-0a1f-40dd-aae1-45a6b1ed7b28
					  collapsed:: true
						- Faster runspeed and increased jump height
						- Examples
							- ((6436af07-a6ac-49dd-9329-ee73897c3af8))
								- [Koga's Agility](https://youtu.be/zyPkAiiyehs?t=58)
								- [Maeve's Prowl](https://youtu.be/WFhQNUkRBbU?t=33)
							- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) : ((65080a5a-b08f-4062-94da-da4f854b541b))
						- Related: ((65d9b95c-2c6f-4472-9e98-98265c125c35))
					- Hitting structures and mobs with weapon to bounce off of them
					  id:: 6743589d-2933-4044-8368-638019e898c9
						- ((6743584d-3395-41d0-b44b-824153afe9fa))
					- Has leaning/peeking
						- ((63b0486e-cdac-468f-ae86-8b9ce6e027d6))
					- ### Tech
						- ((67375ec1-c207-4f94-aeb7-fc3c8a43b6d3))
						- Slide ultrahop
						  id:: 68101bad-25f3-4c05-9903-82e26cc2de59
						  collapsed:: true
							- ((6743584d-3395-41d0-b44b-824153afe9fa)) : ((68101018-fecd-40a5-988c-b7fe76819fa6))
							- Sliding into jumping
								- See [Warframe - Bullet jump (twisting forward flip) [crouch+jump simultaneously]](https://workflowy.com/#/0e4a483f06da)
								- ((6743584d-3395-41d0-b44b-824153afe9fa))
								- (idea) forward jump from slide
									- Pros/Cons
										- Pros
											- Skill-based - has to be timed to during sliding momentum, otherwise it won't go forward much
											- Faster forward than simply simply letting go of crouch/slide and sprinting instead
										- Cons
											- Forward-only - if you want to swap directions quicker then instead end the slide and sprint/slide in that direction
										- Unclear
											- About as fast to feet/vertical as simply letting go of crouch/slide
				- Falling
					- ((67435751-d79b-4aad-adff-4bb087eb073c))
					- ((64e9e733-aa9c-4bda-9605-56045896e07a)) - ((644c09aa-91e1-44d1-b8f9-fb6e96a768b1))
					- ((680a4092-6dc1-4dd8-a657-cc94ac67fbca))
				- Stealth movement
				  collapsed:: true
					- Crouching
						- DayZ (B)
					- Prone (crawl)
						- DayZ (hold B to move into prone)
					- Prone positions
						- DayZ
					- Cover
					  collapsed:: true
						- Cover behind low objects
							- See [Grand](https://workflowy.com/#/a7330264241b)<a href="https://workflowy.com/#/a7330264241b"> </a><a href="https://workflowy.com/#/a7330264241b">Theft</a><a href="https://workflowy.com/#/a7330264241b"> </a><a href="https://workflowy.com/#/a7330264241b">Auto</a><a href="https://workflowy.com/#/a7330264241b"> V</a> (RB)
							- ((64ccc63b-e037-484e-ba92-d7fcd6095644)) (A)
						- Cover behind walls
							- Metal Gear Solid 5 (automatic, no button)
					- Invisibility
						- Skye's Hidden (Paladins)
					- Intangibility
						- Reaper's Wraith Form (Overwatch)
					- _Stealth game examples_
						- Splinter Cell
						- [HITMAN World of Assassination](https://store.steampowered.com/app/1659040/HITMAN_World_of_Assassination/)
						  id:: 67375ec1-2354-490a-9536-ef383aa582ca
							- World of Assassination allows you to pay missions from 3 different Hitman games
							- ((67375ec9-7eb8-44a7-a85f-23262dbb4602)) allows you to play it offline
						- Metal Gear Solid
						- Assassin's Creed
				- Grapple
				  id:: 680ffca8-9d11-47e4-ae37-affa31c2bfb5
				  collapsed:: true
					- To specific points only
					  id:: 680ffcb8-0654-429b-8a84-d57a9f6e2336
						- ((67dea417-532e-4f40-a398-78a17c7831b0))
						- ((64e9e735-af8a-463c-83fc-12d86e17b07d))
						- [Ghostrunner](https://store.steampowered.com/app/1139900/Ghostrunner/)
						  collapsed:: true
							- [[Ghostrunner: 16 Minutes of Gameplay | Summer of Gaming 2020 - YouTube](https://youtu.be/zsjaRHMr088?t=385](https://youtu.be/zsjaRHMr088?t=385))
					- Grapple hook
					  id:: 64e0944d-121f-49f5-8229-d029b9cd957e
					  AKA hookshot / to any specific point then reel in
						- ((680fda33-4000-4c81-b615-db8f61d44523))
						- ((632093db-5f19-44b7-8ca3-6de20a8b30ad))
						- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d))
						- ((64e9e733-aa9c-4bda-9605-56045896e07a))
					- Slingshot
					  id:: 680ffeae-2be5-4328-81be-ad1ae84c0b97
					  i.e. can use swing around using the hook's momentum
						- ((644c0bb7-b3f2-4c0c-b830-5d7976985142))
						- ((666aac4e-0231-4fef-9e0a-7d319071ba01)) - Spider-Man, Venom
						- ((644c0bb5-754e-4fbe-b8d4-b6eec5237782))
						  id:: 67375ec1-bdf2-4209-83c3-13101647af40
						- ((644c0bbe-dfac-42d6-9fba-900d98dfd49b)) - alternate fire for Super Shotgun
						- ((680a4092-6dc1-4dd8-a657-cc94ac67fbca))
					- Grapple swinging
						- [Marvel’s Spider-Man Remastered](https://store.steampowered.com/app/1817070/Marvels_SpiderMan_Remastered/) (2022)
						  id:: 680fd87a-3c64-41e7-b4c2-91645b530e13
						- [Marvel’s Spider-Man: Miles Morales](https://store.steampowered.com/app/1817190/Marvels_SpiderMan_Miles_Morales/) (2022)
						  collapsed:: true
							- [Marvel's Spider-Man 2 Miles Morales Backlash Goes NUCLEAR + Proves Woke South Park Panderverse Right - YouTube](https://youtu.be/NOHPtB5XQSQ)
							-
						- [Marvel's Spider-Man 2](https://store.steampowered.com/app/2651280/Marvels_SpiderMan_2/) (2025)
						  collapsed:: true
							- Cringe Mary Jane missions
							- [SPIDER-MAN 2 Proves Modern Gaming is Getting Worse + Panders to Woke Journalist Demands - YouTube](https://youtu.be/7TPTR8-qmbk)
							- [Marvel's Spider-Man 2 Woke Culture War Goes NUCLEAR + Latinx Backlash & Insomniac EXPOSED - YouTube](https://youtu.be/b78quXQYUtA)
							-
				- Rooftop parkour
				  collapsed:: true
					- ((67375ec2-42b2-448c-8892-df931f45ad63)) (basic)
					    [- YouTube](https://youtu.be/wfBuroUgthI)
					- Assassin's Creed
					    https://youtu.be/JAvX7Dsj6qs
				- _Supernatural movement_
					- _Superhuman_
						- Wallrunning
						  id:: 6436ad35-0be5-492e-b77a-78c1d468d6fc
						  collapsed:: true
							- ((644c09aa-55f9-41e1-b24e-eb71fc8231c7))
							- Vertical
							  id:: 6436ad35-0c4f-4c5a-b594-78dec944e5e5
							  collapsed:: true
								- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
								- Saints Row 4 - continuously jumping vertically on building faces
								    [Saints Row 4 - All Super Powers Gameplay - YouTube](https://youtu.be/jUDB-0PYQz0)
								- ((648f9073-99b4-4b00-b9c4-37202273a975)) - straight wall running
								- ((644c0bb4-4d37-4ef9-a8b7-7fcfd20887f4)) - several types including flight , teleport and a superspeed dash up walls
								- ((63734e86-47cc-4360-addf-cf2ded2c066d)) - wall running
								- ((632093e3-f744-4984-b5ec-1332218f2373)) - ((6436ce99-2edf-410a-b608-06a2654ba824))
								- _Related:_ ((6436ad35-599b-43e0-832f-4e5a1f366369)) : ((6436ad35-1ffe-464d-8ae8-06af3955f1b3))
							- Vertical wall kickflipping
							  id:: 65081384-d16c-4e7b-a4f5-a30e36747d69
							  collapsed:: true
								- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) :
									- ((6508149d-096f-4adf-b2a3-c7d6c5a8daf6))
									- ((65080a61-98ca-4983-b9b4-016dd55d8508))
							- Horizontal wall kickflipping
							  id:: 674355e1-56c1-49a6-bae8-b64e5fa8ada3
							  collapsed:: true
								- ((6743584d-3395-41d0-b44b-824153afe9fa))
								  id:: 674355eb-015e-49f3-a359-8a484b0e6a7b
						- Ceiling running
						  collapsed:: true
							- ((6436aeff-1a52-4356-94a8-18ac35e09ff8))
							- ((64e0952f-14ff-43fb-bbe6-db6c115ac3c7))
						- _Teleportation types_
						  id:: 644c09aa-e0b8-4a0e-8e2b-2e122b5f7768
						  collapsed:: true
							- _Targeted teleport_
								- ((67375ec1-ff0a-4dd5-ba64-74539c4272b4)) (Blink)
								    [Corvo's blink vs. Daud's blink effects - YouTube](https://www.youtube.com/watch?v=LwVyfkk0VHc)
								- Overwatch - Reaper's Shadow Step
								- City of Heroes
								    https://www.youtube.com/watch?v=RF0tPPPZc9E
								- ((6436af07-f2b9-4bb5-9c67-4dce6f32a415))
							- _Incorporeality to teleport_
								- Overwatch -
								- ((67375ec1-ff0a-4dd5-ba64-74539c4272b4)) - Shadow Walk
								    [Dishonored 2 Shadow Walk Build (Non-Lethal) - YouTube](https://www.youtube.com/watch?v=3B-4HD7cDog)
								- Overwatch - Reaper's Wraith Form; Moira's Fade
									- [https://playoverwatch.com/en-us/heroes/moira/](https://playoverwatch.com/en-us/heroes/moira/)
								- Paladins - Skye's Hidden;
							- _Rewind position _
								- Overwatch - Tracer
								- Paladins -
							- _To lock-on target_
							  id:: 644c09aa-c5f7-4cb1-b6f8-9dc7749b2c4a
								- ((648f9074-2c2d-498a-a336-5058b0ee584d))
								- ((66e97985-9ce5-4533-96c5-5983fff092db)) : ((66e979d3-2d03-4d01-8ac5-4b1e2a66455c))
								- ((632093da-8019-4aa4-b3d4-d9180b8a1d2a))
							- _Strafe teleport_
							  id:: 644c09aa-e583-4b9c-b4d5-84f9cb714651
								- ((632093da-8019-4aa4-b3d4-d9180b8a1d2a))
								- ((63a9ae55-9be0-463d-8091-ba0d992765c8))
						- Bunny hop
						  id:: 67375ec1-c207-4f94-aeb7-fc3c8a43b6d3
						  collapsed:: true
						  AKA Slide hop
							- ((6743584d-3395-41d0-b44b-824153afe9fa)) : ((6810104e-12bf-4e73-88a1-4e4a3c3c582f))
							- ( ((644c0bb7-b3f2-4c0c-b830-5d7976985142)) )
							    [Titanfall 2: The Slidehop Guide (PC 1080P) - YouTube](https://www.youtube.com/watch?v=x7ZLp2xUlIo)
							- Related:
								- ((64e0944d-aa38-44bd-9d74-c50867f50b56))
								- ((650820a5-74ab-4bcf-a106-c4226c774930))
								- ((68101bad-25f3-4c05-9903-82e26cc2de59))
						- Ultrahop
						  id:: 67435f07-7eb7-48f6-b2f3-c4af9005baec
						  collapsed:: true
						  i.e. a ((650820a5-74ab-4bcf-a106-c4226c774930)) with greater height
							- ((6743584d-3395-41d0-b44b-824153afe9fa)) - ((68101018-fecd-40a5-988c-b7fe76819fa6)) can do ((67435751-d79b-4aad-adff-4bb087eb073c)) into a high jump. Can do a ((650820a5-74ab-4bcf-a106-c4226c774930)) into a high jump
							- Related: ((650820a5-74ab-4bcf-a106-c4226c774930))
						- ((64e0944d-971f-477b-a1b6-bc93d8ac8fc4))
						- Bullet time
						  id:: 65d9b95c-2c6f-4472-9e98-98265c125c35
						  collapsed:: true
						  AKA slow motion / superspeed
							- ((634bc201-ab66-494b-8738-826601b04f57))
							- Perfect Dodge
							  id:: 6810b911-f77a-4dba-a8d5-2e97f4ed0198
							  i.e. slow time after Perfect Evade
								- ((632d02a6-96eb-4e27-851e-69567cd2fd39))
								- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
							- Related: ((644c09aa-0a1f-40dd-aae1-45a6b1ed7b28))
						- Montages
							- Warframe - Chaining together glides, bullet jumps and rolls
							    https://youtu.be/u1sngO7uKVI?t=137
					- Magical movement
						- Super jump
						  id:: 67375ec1-b758-4a5b-9307-327f2143b181
						  collapsed:: true
						  AKA Single big jump
							- Paladins
								- Bomb King's F; Buck's something;
							- Related: ((644c09aa-0511-4c6b-b537-98f066e5f84e))
						- Air jump types
						  id:: 680ffb4d-2330-4476-b004-361ea12c9e81
						  collapsed:: true
							- Double jump
							  id:: 644c09aa-3aef-45bc-81cf-2f6f22323b7a
								- Examples
									- ((67dea417-532e-4f40-a398-78a17c7831b0))
								- Subtypes
									- ((6318fd58-0de6-4946-98ef-95fa22f457c6)) double jump types
									  collapsed:: true
										- [Warlock](https://www.destinypedia.com/Warlock#Subclasses) glides
											- [Balanced Glide](https://youtu.be/cB7roakCxDU?t=32) - start an airborne drift with both moderate speed and directional control
											- [Strafe Glide](https://youtu.be/cB7roakCxDU?t=32) - start an airborne drift with strong directional control
											- [Burst Glide](https://youtu.be/cB7roakCxDU?t=38) - start an airborne drift with a strong initial boost of speed
											- [Blink](https://youtu.be/cB7roakCxDU?t=46) - teleport a short distance
										- [Titan](https://www.destinypedia.com/Titan_(class)#Subclasses) lifts
										  collapsed:: true
											- [Strafe Lift](https://youtu.be/cB7roakCxDU?t=20) - jump whilst airborne to activate Lift and launch into the air with strong directional control
											- [Catapult Lift](https://youtu.be/cB7roakCxDU?t=23) -  jump whilst airborne to activate Lift and launch into the air with strong initial burst of momentum
											- [High Lift](https://youtu.be/cB7roakCxDU?t=27) -
											- [Learning Resources]
												- Learn Top 1% TITAN Movement
												    [https://youtu.be/AmTA8ocavQ8](https://youtu.be/AmTA8ocavQ8)
										- [Hunter](https://www.destinypedia.com/Hunter#Subclasses) jumps
											- [High Jump](https://youtu.be/cB7roakCxDU?t=16)
											- [Strafe Jump](https://youtu.be/cB7roakCxDU?t=12)
											- [Triple Jump](https://youtu.be/cB7roakCxDU)
								- *Jetpack-like*
									- [Thrust Jump](https://youtu.be/XOPQ_oq8vjQ) (Call of Duty: Black Ops 3)
							- Several
							  id:: 65082771-3643-432c-aea6-9538db99a2a0
								- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) : ((65080a5f-c9a9-4556-b7b3-bca7fec6cab0))
							- Many
							  id:: 680ffb52-6e0f-4e5c-aed9-73feba0d65da
								- E.g: shapeshifted faerie Zoe in ((67dea417-532e-4f40-a398-78a17c7831b0))
							- Related: ((67375ec1-145d-4d00-8d9d-e482390fbc82))
						- Falling faster types
						  collapsed:: true
							- Ground slam
							  id:: 67435751-d79b-4aad-adff-4bb087eb073c
							  collapsed:: true
								- i.e. whilst in mid-air going vertically downards
								- ((6743584d-3395-41d0-b44b-824153afe9fa))
								- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
								- ((64e9e72d-680a-41ca-a8a4-e4af2cc8a574))
								- ((648f9073-a167-46c9-8f87-3502ba37521e))
								- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d))
								- Related: ((644c09aa-0511-4c6b-b537-98f066e5f84e))
							- Directed slam
							  id:: 68109864-f90f-4eda-94ad-04bb36f0e03e
							  collapsed:: true
								- ((64e9e72d-680a-41ca-a8a4-e4af2cc8a574)) : Death From Above superman punch
							- Falling faster
							  id:: 68109889-bc64-4c7f-946b-0c778fba0a48
							  collapsed:: true
								- ((680a4092-6dc1-4dd8-a657-cc94ac67fbca)) : ((680a5b72-ff39-41ca-b7ae-347cb9ef4173))
						- Related:
							- ((650817b2-ce64-4a2d-b37f-75a497ff236b))
					- _Flight types _
						- Short flight
						  id:: 67375ec1-03ff-4d2b-ac62-99cf061b5fb5
						  collapsed:: true
							- Forced forward flight
							  id:: 644c09aa-90f2-43a2-bfba-1481704fddaf
							  i.e. can't hover
								- ((6436af07-a6ac-49dd-9329-ee73897c3af8))
									- [Imani's Frostfall Glide](https://youtu.be/iga0YSUITjE?t=120)
									- [Evie's Soar](https://youtu.be/4LiKiO-fMr4)
								- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) : ((650809e5-7c77-4a2f-b455-e10693d1526e))
							- Overwatch - [Echo's Flight](https://youtu.be/Ebkzgr3l2QQ?t=20)
								- [https://playoverwatch.com/en-us/heroes/echo/](https://playoverwatch.com/en-us/heroes/echo/)
							- Call of Duty Black Ops 3 - Thrust Jump
						- Glide
						  id:: 64e0944d-1d69-4819-8e3e-cc153dcf8de7
						  collapsed:: true
						  AKA gliding
							- ((64e0952a-37d7-4849-873b-3ef6483fac07))
							- Veloren
							- ((632d02ac-e241-4bee-897b-97682e44733a))
							- ((648f9073-99b4-4b00-b9c4-37202273a975))
							- Saints Row 4
							- [Just Cause 3](https://store.steampowered.com/app/225540/Just_Cause_3/)
							  id:: 680fda33-4000-4c81-b615-db8f61d44523
							- ((6318fd58-0de6-4946-98ef-95fa22f457c6))
							- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) : ((65080a66-9860-45fb-bc47-69501589bfcf))
							- Warframe - Aim glide
							    https://youtu.be/u1sngO7uKVI?t=57
							- Warframe - Air Dodge Roll (Air Glide > Bullet Jump to the side)
							    https://youtu.be/u1sngO7uKVI?t=82
						- _Hover-like_
						  collapsed:: true
							- Skimming
								- Two forcefield disks used as steps (hoverboard-like)
							- Hoverboard
							- Jetpack
							- Flying animal/summon
							- Winged flight
							- Helicopter
						- Separate flight+hover modes
						  collapsed:: true
							- Anthem has flight+hover modes
							- Saints Row 4 - glide flight and Death From Above hovering
							-
						- Directed flight
						  collapsed:: true
							- ((680fd87a-3c64-41e7-b4c2-91645b530e13))
							- Batman Arkham City
							- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
					- Other supernatural
						- *Water running-like*
						  collapsed:: true
							- Water running
								- ((64e9e72d-4d56-447a-b3e9-151167d89304))
							- Water surfing
							  id:: 650811a0-3adf-4346-a158-6fc8cd605282
								- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) : ((65080a69-c676-454b-b9cc-735672cbd3bd))
						- Ceiling running
						- Underground tunneling
						- Summons riding
				- Mount
				  collapsed:: true
					- Horse (X - Skyrim)
					- Vehicle (Y - GTA V)
					- Summon animal ( ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040))
					- Summon speeder bike (Destiny 2 - hold Select/View)
					- Spaceship
				- ((6416d885-f857-4011-a7c3-3dce30010c69)) : ((64e9e72d-142a-45a8-b31e-ebbe846c8e8f))
				- Tech
					- ["Suspended Jump" - Dodge roll into jump](https://youtu.be/yp002taWvTI?t=340)
			- Related:
				- ((63734bb5-e123-4821-9645-82f2fa2e593d))
				- ((67375ec1-9e66-4b0c-a3a3-9351d55f59c2)) : ((680fc5df-2942-4906-96fe-b017a19f4201))
		- Common actions
			- Blocking
			  id:: 65d9c11b-e778-4608-8a4c-8a65c3d36fb9
		- Combat system
		  id:: 67436760-9989-4867-ac00-af0ffd65d190
		  collapsed:: true
			- Related:
				- ((63734bb5-0a6f-44e9-8bfe-4a0206a1a4a9))
				- ((6353979e-5e39-41d3-b371-6b1d4408ad1d))
				- ((63734bb5-e123-4821-9645-82f2fa2e593d)) : ((6751dba1-f96c-4cd3-83e7-9a309bf2796f))
				- ((63b0a2cb-230d-4c06-9f7f-0b507e88badf))
		- Games with particular systems
		- [Magic Systems and Power Classifications](((63734eb1-85d8-4420-9b5e-5929ed4e383d)))
		- Related:  [Animation](https://workflowy.com/#/1df82d81000b)
	- Character Customisation
	  collapsed:: true
		- Design/appearance
			- City of Heroes
			- City of Titans
			- ((634bc201-ab66-494b-8738-826601b04f57))
		- Champions Online
		    https://youtu.be/ixUdTLkajis?t=3m59s
		- _Basic_
			- City of Heroes (auras, skin/animal)
			    https://youtu.be/4R4huHUzVP8?t=6m24s
	- Progression
	  id:: 67375ec1-4b3a-42f5-a8f6-c0cf4ea9c329
	  collapsed:: true
		- Horizontal > vertical progression
		  collapsed:: true
			- Meta
				- Vertical progression is constant level cap increases. Raising numbers in armor/weapon values invalidating a lot of the content. Take World of Warcraft before the last expansion or two. Only "end game" viable areas were from the latest expansions. Rest of the game only served the purpose of getting the player up to the level required to cluster around a couple of the newest areas.
				- Horizontal progression is a consistent level cap without raising armor/weapon values no matter what comes out. Player progression comes mostly from diversifying play style rather than "raising numbers" so this means a lot more of the content is optimal all the time
					- Horizontal progression is great because it keeps the game alive and resources aren't wasted on updates like Destiny's "Age of Triumph" where they either abandon content or rework it for the optimal level of the month.
			- Good examples
				- Power slots with limited capacity
					- Examples
						- ((632cd63c-fe84-44cd-bb15-85ce4c054eca)) [dragon shouts](https://elderscrolls.fandom.com/wiki/Dragon_Shouts)
						- ((632d02af-9d3a-45b1-ab6d-69f923db836e)) [Heartrunes](https://www.thegamer.com/new-world-heartrune-gem-guide/) (Ultimate ability)
						- ((63a9ae55-9be0-463d-8091-ba0d992765c8)) [cloaks](https://wizardoflegend.fandom.com/wiki/Outfits)
						- ((67431579-5d39-45c4-9572-9f2c66766704)) e.g. ((64e0952a-9d60-4a12-887c-975c287cc7df))
						- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) Echoes
						- ((62e2844f-3eba-403e-ad55-73d00b47065e)) runes, summoner spells, 6 slot equipment, equipment abilities
				- ((64ccaf0d-aa29-4849-941f-94b5c672a5f3))
					- It had a level cap of 20 that could be reached fast.
					- Then it was about earning skill points, learning/capturing skills, unlocking secondary professions and making builds that could tackle content.
					- And the content got hard.
		- Talent trees
		  id:: 63531eea-d78d-4e60-a053-0edd8b75764c
		  collapsed:: true
		  AKA skill trees
			- #hackandslash e.g. ((63503886-7d76-4f63-92c6-1b295e1cacb0))
			- ((63b08980-48de-4e66-b604-239b32fdc548)) e.g. ((632cf632-35b8-4d56-adc5-f97d144609f9))
			- Elder Scrolls modded
			-
		- Visual progression
		  collapsed:: true
		  e.g. different armours/weapons, skins
			- Good examples
				- ((632cf072-c2c6-43b5-92f8-55eca18f42b6)) e.g. ((6318fd58-0de6-4946-98ef-95fa22f457c6)), ((630f97d8-5e75-445d-9a55-6f2c4f1e517f))
				- ((632093e5-1f77-49e2-a0e0-60538a424d89)) e.g. ((632d02af-9d3a-45b1-ab6d-69f923db836e))
				- ((67431579-5d39-45c4-9572-9f2c66766704)) ?
			- Bad examples
				- ((644c0bb4-6a5b-4592-b085-b833fc9538e4)) e.g. ((644c0bb4-9801-4ac3-a423-cf17703a148b)) (though it does have weapons)
		- Classes
		  collapsed:: true
			- Good examples
				- ((632d02af-9d3a-45b1-ab6d-69f923db836e)) - classless but tied to weapons
				- ((63734e95-da7c-4bc5-a615-a231ff184c44)) - tied to a job
			- Games with classes
				- ((6318fd58-0de6-4946-98ef-95fa22f457c6)) - Titan, Hunter, Warlock
			- Related: ((64f5d198-6840-46c8-8050-64bd52d458a5)) : ((644c0a95-a494-4659-93a8-16af2110f2f7))
		- Level scaling choice
		  collapsed:: true
			- Pros/Cons
				- Pros
					- Allows you to replay many areas of the game rather than being limited to a smaller area over time
				- Cons
					- Makes you feel like your character hasn't progressed
					-
				- Unclear
				- Comparisons
			- Examples
				- ((634bc201-ab66-494b-8738-826601b04f57)) initially didn't have it, but since 2.0 update (2023) it has level-scaling across the whole city
				- ((632093db-42a7-4662-8965-bac77a23d873)) has level scaling across a region, but not for whole open-world
				- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) has some level scaling in co-op?
				- World levels
					- Examples
						- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) SOL-3 Phase Level
							- Harder enemies but also better resource drops
							- Note: this forcibly increases the more experience you gain, but you can delay it by 10 levels to go down a tier. It does this to encourage ((644c09aa-2014-4f02-a148-dd2218155839))
								- Though also you have to do a SOL3 Phase Ascension Quest every 20 union levels to unlock the next tier
						- ((630f97d8-5e75-445d-9a55-6f2c4f1e517f))
				- Region-based no level scaling, but specific landmarks have level scaling enemies
					- Xenoblade, early WoW, Elden Ring, and (to a certain extent) BotW all did this right.
					- low level areas have baddies that match the zone's intended level and they stay that way for the rest of the game. but then there are also massive, intimidating Big Baddies wandering around or perched at interesting landmarks. you can't fight them now, but maybe you can if you come back later. it's an easy way to inspire an aspirational goal for a player.
					- but not only that, when done right, it can impart a sense of wonder and mystery. you're awestruck at their scale, how you must seem like nothing to them, how quickly they smite you if you step too close. you can't help but wonder who they are, how they came to be there, what their story might be, what secrets they could be hiding or powerful artifacts they may carry. when paired with environmental storytelling, these "someday encounters" can be packed with tons of character.
				- ((6318fd58-0de6-4946-98ef-95fa22f457c6)) damage scaling
					- [Enemies are immune to you if your total power level is 100 below theirs. At 99 levels below you start dealing about 40% damage, which raises to 100% if you match their power level. It doesn't go above that](https://www.reddit.com/r/DestinyTheGame/comments/iylgeu/power_level_and_damage_scaling_tldr_at_the_bottom)
		- Transhumanism
		  collapsed:: true
			- _Good exam_ples
				- Space Station 13 - nanites, genetics, augmented limbs, cybernetics
				- ((6318fd52-c87b-4b6c-9ea1-fea756d1d4a8)) - mutations, cybernetics
				- ((632d02a9-cd45-42a1-aad7-8062cc756fee))
				- Deus Ex
				- ((634bc201-ab66-494b-8738-826601b04f57))
		- Character upgrading and Inventory
		  collapsed:: true
			- ((633b7574-d7f5-4251-9ec0-91420f47f961))
			- Guild Wars
			- ((66792589-6978-450f-80ec-445ef8ff0c47))
			- The Division
			- DayZ
			- Deus Ex
		- Related: ((6353979e-5e39-41d3-b371-6b1d4408ad1d))
	- Graphical User Interfaces
	  collapsed:: true
		- GW2
		    https://wiki.guildwars2.com/wiki/Graphical_user_interface
		- GW1
		    https://wiki.guildwars.com/wiki/User_interface
		- Navigation help
			- Compass
				- ((63209426-3e95-4515-9877-af2f9f1bfe07))
				- ((676ebd86-d91c-4a02-8312-71522117c1f6))
			- Minimap
				- ((6416d895-e7bf-4c2e-bd46-519ccdcda840))
			- Augmented reality
				- ((632093e3-b52f-4403-9f27-1ff84c817090))
				- ((6416d895-b94e-4f38-91e4-c67cce5aebca))
	- Time design
	  id:: 64e0944c-92b7-4dc5-b994-0ddb9669b0a9
	  collapsed:: true
		- _Different types_
			- Realtime
			  collapsed:: true
				- Examples - [Space Station 13 (SS13)](https://workflowy.com/#/f649d71e0a7c), <a href="https://workflowy.com/#/3fa5068f474f">Real-Time Combat</a>
				- Pros/Cons
				  collapsed:: true
					- Pros
					- Cons
			- Realtime with pause
			  collapsed:: true
				- Examples - Rimworld, [Stellaris](https://workflowy.com/#/99fffa2f27a2), FTL
				- Pros/Cons
					- Pros
					- Cons
			- Roguelike
			  collapsed:: true
				- Examples - ((6318fd52-c87b-4b6c-9ea1-fea756d1d4a8))
				- Pros/Cons
				  collapsed:: true
					- Pros
					- Cons
					  collapsed:: true
						- Difficult to convert to multiplayer
						  collapsed:: true
							- ((64e0952f-bb27-4797-8637-36430c983fb9)) was built on a roguelike but turns are now every ~0.5 seconds it looks like
			- Turn-based
			  collapsed:: true
				- Examples - most ((6416d854-4ee1-47fa-84c8-d49b19b606c2)), <a href="https://workflowy.com/#/18bc4fe039df">Turn-Based Combat</a>,
				- Pros/Cons
					- Pros
						- Easy to work in multiplayer
					- Cons
			- Turn-based with QTEs
			  id:: 680f5f4b-777b-4f8a-b3ec-4ee3b3923e0a
			  collapsed:: true
				- Examples
					- ((680cf12f-dae4-49a9-b89b-9c26d4e0875b))
					- Paper Mario
					- ((67411590-8691-445b-9080-1edd3b7dd87d))
					- [Sea of Stars](https://store.steampowered.com/app/1244090/Sea_of_Stars/)
			- Unsorted
				- Examples - ((64e9e730-2e7f-4959-a965-bca0f235ab6f))
	- Advanced systems which give depth
	  collapsed:: true
		- # Elements
			- Reminders for when you haven't played the game in a while
			  collapsed:: true
				- Reminder for story content
				  AKA story recap
					- ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040)) - loading screens
					- FFXVI does this better than any game I've ever seen. It has an Active Time Lore system, so holding the touchpad at any point tells you where you are, who is in that scene/area and backgrounds for all of it. There are also two "professors" in your home base area that give you the background on everything you've encountered in the game, as well as a "live" update of what areas the factions control, who's fighting with who, and so on and so forth. You can move a slider back and forth to see how those relationships have changed from the beginning of the game to where you are now.
					  Honestly at the very least every game needs to implement the ATL system, it's ingenious.
					- Far Cry: Primal did an AWESOME job with this, because every time you loaded up the game, there was a short summary of the story so far, told by one caveman to another at a campfire or similar as far as I remember.
					- I just picked up Tactics Ogre Reborn and it has a complete breakdown of everything that has happened. To an absurd degree, like including short bios of the random named bosses on the battles between the main story mission. “Bob was a Golgathian Berzerker that hated cats. He was slain in battle by <main character> at <place>.”
				- Reminder for game mechanics
					- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) - has a resonator practice mode where they teach you several combos for each resonator, and all their abilities
					- Ghost of Tsushima controller prompts
					- Assassin's Creed: Black Flag
					-
			- Quest generation simulation
			  collapsed:: true
				- ((632cfe94-c204-4902-80c8-08f0dcd48c13)) - quests generated in each area, NPCs can claim these quests, quests broadcast depend on the features of that star system
			- Squad/colony management
			  collapsed:: true
				- Good examples
					- Pokémon
					- ((644c0bb4-7b21-4650-9d9c-000eef66eea1))
					- XCOM
					- ((632d02a9-cd45-42a1-aad7-8062cc756fee))
					- [Dwarf Fortress](((63542966-ba87-4fb3-a14e-0459aafc2fbb)))
					- ((632cfe94-c204-4902-80c8-08f0dcd48c13)) - autoequip for template builds or deeply customise their gear/abilities;
					- ((63503881-6ad9-406e-848f-2f7808e89b1f))
					- ((6318fd52-c87b-4b6c-9ea1-fea756d1d4a8))
					  collapsed:: true
						- Didn't realise it has squads
						    [https://redd.it/glxmhe](https://redd.it/glxmhe)
					- Skyrim
					- Mount & Blade
			- Event-centered RPG
			  id:: 67375ec1-fd7d-40cb-876f-e9b48e15b402
			  collapsed:: true
				- sometimes a prompt pop ups when you reach a certain area/time, and then you get or lose stats
				- Good examples
					- ((65955e60-15a2-4016-beca-210fad44f2b5)) or similar Paradox (Studio) titles - First comes a preliminary event, which can lead to a sub event (chosen randomly)
					  collapsed:: true
						- [https://ck2.paradoxwikis.com/Events](https://ck2.paradoxwikis.com/Events)
						- Possibly Stellaris and Europa Univeralis has it also
					- World of Horror - Just as before, but less advanced as it usually only has a success or failure event. Usually requiring a skill check.
					  collapsed:: true
						- https://woh.fandom.com/wiki/Event_Codex
					- ((632093e2-45af-4437-b2a1-ba228ce5a08a)) - multiple choices before event with some requiring skill req or it does a hidden skill check
					  collapsed:: true
						- Random encounters
							- [https://wasteland.fandom.com/wiki/Wasteland_3_random_encounters](https://wasteland.fandom.com/wiki/Wasteland_3_random_encounters)
							- [https://guides.gamepressure.com/wasteland-3/guide.asp?ID=55647](https://guides.gamepressure.com/wasteland-3/guide.asp?ID=55647)
					- ((64e9e730-77ce-438d-84f0-e88e96edc2e9)) - rooms with random events have a prompt, then usually a d100 roll to see the event outcome
					- ((644c0bbc-9a44-4320-a7fc-1ad01f89ddf3)) - some random events
					- [[SS13]] - mostly negative events
					- ((632d02a9-cd45-42a1-aad7-8062cc756fee)) [events](https://rimworldwiki.com/wiki/Events)
					- [[SS13]] [random events](https://tgstation13.org/wiki/Random_events)
						- e.g. electrical storms, spider infestations, random heart attacks, mass hallucinations, false alarms
				- Related:
					- ((67375ec1-9e66-4b0c-a3a3-9351d55f59c2)) : ((67432c2d-71c9-4dab-b2f2-a307c41aec59))
			- Missions/careers
			  collapsed:: true
				- Ideal: all the below
				- Procedural v Handcrafted
				  collapsed:: true
					- Procedural
					  collapsed:: true
						- City of Heroes procedural missions
						  collapsed:: true
						    http://www.escapistmagazine.com/forums/read/9.860780-Procedural-vs-handcrafted-comparing-City-of-Heroes-to-DC-Universe-Online
							- TL;DR: It was more interesting as procedural than entirely handcrafted missions because enemies were level-adjusted and there's never-ending content
							  collapsed:: true
								- City of Heroes' missions were, for the most part, restricted to two types; the first were the 'kill x number of y' grinds that take place in the larger hub. The other type was private missions, which were done in procedurally generated Instanced areas; that procedural generation actually meant there were hundreds, if not thousands, of missions, usually very lightly story-wrapped with some before-mission text, a bit of written dialogue in-mission, and some after-mission text. Of course, the procedural generation led to plenty of repetition in terms of surrounding- there were perhaps a dozen or two 'skins' ranging from caves to underground bases to laboratories, office complexes, etc, with most of the procedural generation altering layouts and enemy placements. Maybe not super satisfying to someone who likes more exposition, but to someone happy to 'fill in the blanks' in their own head, which I definitely was, it went fine. 'I'm going to this same-y underground base to prevent the neo-Nazi supersoldiers from tampering with time travel this time? Okie dokie! =D Imma kick dem Nazis IN DA FACE!'
								- The sheer number of missions, and the time to hit the level cap of 50, also led to this nice sense of progression... you started off as this newbie hero who largely went around fighting street thugs, dealing with drug shipments, etc, etc, all kinds of basic stuff. As time went on, and you got stronger, you worked your way up to more and more unusual and extreme threats, in different zones of the overworld; dealing with criminal sorcerers hiding in Perez Park, trying desperately to navigate the Hollows alive without the benefit of superpowered movement, escalating to awesome things like visiting alternate dimensions, different planes of existence, fighting giant robots, taking on the game's equivilent of 'Canon' villains, just REALLY cool stuff.
						- Skyrim radiant quests
						  collapsed:: true
							- Dark Brotherhood - kill a specific target
							- Companions - killing beasts, bounty hunting, retrieve stolen heirlooms, rescue kidnapped citizens
							    https://en.uesp.net/wiki/Skyrim:Companions#Radiant_Quests
							- Thieves Guild - Bedlam, Burglary, Fishing, Heist, Numbers, Shill and Sweep Job
							    http://elderscrolls.wikia.com/wiki/Thieves_Guild_(Skyrim)#Small_jobs
						- Hacking mini-games e.g. Hacknet
						    intralink2:: https://workflowy.com/#/5aacca2bec49
						- Thief Simulator mini
					- Handcrafted
					  collapsed:: true
						- Best examples: Skyrim,
				- Repeatable missions
				  collapsed:: true
					- ((63542965-aaa8-4872-b7bb-026c76092669)) jobs e.g. mining, delivery
					- ((632cd63c-fe84-44cd-bb15-85ce4c054eca)) : ((6718a967-8675-489c-a166-5c002ab3137d))
					- ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040)) notice boards
					- ((632d02af-9d3a-45b1-ab6d-69f923db836e)) [town project boards](https://www.thegamer.com/new-world-town-projects-quests-explained/#town-project-boards-explained)
					- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) - Tactical Holograms, ((673bd74e-8b2d-411d-bf75-770ddf835cd3)), Tower of Adversity, ((67434b39-bab9-438f-9cf2-5d9586dd5cb9))
					- ((6436aefb-b837-4985-a2a0-4922bcce7199)) - [freemode missions](https://gta.fandom.com/wiki/Category:Freemode_Missions),
						- [Side missions](https://gta.fandom.com/wiki/Missions_in_GTA_V#Side_Missions)
							- [Taxi Jobs](https://gta.fandom.com/wiki/Taxi_Jobs_in_GTA_V) | [Private Taxi Fares](https://gta.fandom.com/wiki/Private_Taxi_Fare) | [Towing](https://gta.fandom.com/wiki/LSPD_Auto_Impound) | [Hao Street Races](https://gta.fandom.com/wiki/Hao_Street_Races) | [Offroad Races](https://gta.fandom.com/wiki/Offroad_Races) | [Sea Races](https://gta.fandom.com/wiki/Sea_Races) | [Triathlon](https://gta.fandom.com/wiki/Triathlon) | [Arms Trafficking Air](https://gta.fandom.com/wiki/Arms_Trafficking_Air) | [Arms Trafficking Ground](https://gta.fandom.com/wiki/Arms_Trafficking_Ground) | [Hunting](https://gta.fandom.com/wiki/Hunting) | [Property Management](https://gta.fandom.com/wiki/Property_Management) | [Flight School](https://gta.fandom.com/wiki/Flight_School) | [Random Events](https://gta.fandom.com/wiki/Random_Events_in_GTA_V) | [Strangers & Freaks](https://gta.fandom.com/wiki/Random_characters) | [Stock Car Racing](https://gta.fandom.com/wiki/Stock_Car_Racing) [E] | [Wildlife Photography Challenge](https://gta.fandom.com/wiki/Wildlife_Photography_Challenge) [E]
				- ((67375ec1-fd7d-40cb-876f-e9b48e15b402))
				- _Misc_
				  collapsed:: true
					- (If MMO) Both instanced and open world missions
					  collapsed:: true
						- ((64e9e72e-3a44-4e8d-907d-f369f66d7d0a))
						- ((6318fd58-0de6-4946-98ef-95fa22f457c6))
					- Player tool for creating custom missions
					  collapsed:: true
						- Mission Architect (City of Heroes)
						  collapsed:: true
							- https://paragonwiki.com/wiki/Mission_Architect
							- http://cityofheroes.wikia.com/wiki/Mission_Architect
							- https://kotaku.com/5161479/the-city-of-heroes-mission-architect-explained
			- Metabolism
			  collapsed:: true
				- Good examples
				  collapsed:: true
					- Space Station 13 - many chemical effects
					- ((632d02a9-cd45-42a1-aad7-8062cc756fee)) - addictions and dependencies,
					- SCUM
			- ## *Combat aspects*
			  id:: 6353979e-5e39-41d3-b371-6b1d4408ad1d
			  collapsed:: true
				- Abilities reshape the environment
				  id:: 63a9acd6-3a0d-45d6-9f61-799d514a08ef
				  collapsed:: true
					- Types
						- Divinity: Original Sin 2 - [Fire, Water, Ice, Electricity, Blood, Poison, Oil, Lava, Web, Smoke, Cursed, Blessed, Source, Deathfog](https://divinityoriginalsin2.wiki.fextralife.com/Environmental+Effects)
						- Diablo 3 - [Fire, Cold, Lightning, Poison, Arcane, Holy](https://us.diablo3.blizzard.com/en-us/game/guide/gameplay/combat-skills)
						- Gunfire Reborn - fire for normal damage, corrosive for yellow armour, shock for blue shield
						- Genshin Impact - elemental combos
				- Role / class  / disciplines
				  id:: 63b1ece5-5084-4b96-bebd-47a94ba18e5d
				  collapsed:: true
					- Magic schools
						- ((63a9ae6a-ebb8-462b-b029-5d58fbdc2fa6)) : ((63a9ae6a-a933-4073-8711-0084060a7223))
						- Naruto - 10 types
							- ((63a9acc6-ef37-4b04-a24d-3b24bc7af239))
						- ((632cd63c-fe84-44cd-bb15-85ce4c054eca))
						- ((63a9ae69-b5fe-4b5d-959e-906914d96bef))
						- ((632d02af-2b02-45a3-86e2-52fe7520b541))
						- ((63734e95-da7c-4bc5-a615-a231ff184c44))
						- Dungeon World
						- ((632d02ac-e241-4bee-897b-97682e44733a)) - each is like a class
						- ((642ed60c-9aee-4a05-92ab-50f32a2b6cf5))
						- Related: ((63a9acd6-3a0d-45d6-9f61-799d514a08ef))
				- Destructible environments
				  id:: 67375ec1-1917-489b-842d-81e3ef13f3c7
				  collapsed:: true
					- Good examples
						- ### Fully
							- ((648f9076-9c44-4a26-8af5-8d709d1ab64d))
							- ((64e9e733-23d8-4b60-82a4-1ba505f4e452))
							- ((64e0952a-6991-4504-894d-6da07a1d5c41))
							- Teardown
						- ### Mostly
							- ((630f97d8-cbc3-46a7-8174-8df682803cdb))
							- ((632d02ab-14a1-4cc3-88dd-f9a66bd163e7))
						- ### Partially
							- ((63b0486e-cdac-468f-ae86-8b9ce6e027d6))
							- ((6350388b-2b51-4898-87c5-97274b525822))
						- The Finals
						- Starbase
						- Battlefield V
						- Rainbow Six Siege
						- ((63503886-f4f6-4930-8a39-e5fbfcd42eed))
						- Crackdown
						- [Red Faction Guerilla](https://store.steampowered.com/app/667720/Red_Faction_Guerrilla_ReMarstered/)
						- Worms
						- Terraria
						- Rimworld
						- Streets of Rogue
				- High mob variety
				  collapsed:: true
					- Examples with high mob variety
					  collapsed:: true
						- ((632093db-42a7-4662-8965-bac77a23d873))
						- Monster Hunter
						- Shadow of the Colossus
						- Furi
				- Parry/counter/riposte system
				  id:: 635397c8-40a0-4ba1-8051-f465aaf22837
				  collapsed:: true
				  i.e. timing to stop an enemy attack (+ optional: attack enemy back)
					- Examples
						- PvE
							- ((649b1461-cc38-49dd-a8be-f0b18d52ff05)) : ((64d11073-2c6c-4ea2-b104-d7ce720c5781))
							- ((632093da-8019-4aa4-b3d4-d9180b8a1d2a)) : ((63a9ae52-fdb9-4caf-b0c1-a3fe7bbdfc79))
							- ((63542962-0114-464e-8d91-b3b3219205fc))
							- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
						- PvP
							- ((62e2844f-3eba-403e-ad55-73d00b47065e))
								- ((63b30115-49b7-49a6-956b-d2f43a67a3a2))'s Riposte - near invuln, then a ((63b2f44a-3dba-4922-b766-ebcb9cfb6b16))
								- ((63b3033b-98db-42bf-a00e-fd3a4d445f55))'s Unbreakable
								- ((63b304a0-afac-434a-ac79-48e403673aeb))'s Counter Strike
								- ((63b30478-432d-42cf-8f5c-baa960cfa84e))'s Spell Shield
								- ((63b3055a-915c-4cb2-a102-c9c9bd39d258))'s Blade Whirl
							- ((632093db-42a7-4662-8965-bac77a23d873))
							  collapsed:: true
								- [Parry frame windows](https://youtu.be/u16m-zepZVs)
							- ((63734e86-47cc-4360-addf-cf2ded2c066d)) : ((63b345d0-c86a-4a8d-8e6d-ccbd68d5dba9))
							- ((63503881-5f34-4011-bbf1-419e1627ba1e))
							- 2001's Super Smash Bros Melee - featured a Perfect Guard mechanic which greatly reduces block stun and has the quirk of reflecting projectiles back to the sender.
							- Fighting games like Street Fighter allow blocking by timing a forward or down input in a small frame window to negate a single hit from normal, special and super attacks.
						- Arkham series
						- ((648f9073-da04-44de-8e75-3563209630eb)) - Witch Time
						- Shadow of Mordor / War
						- ((649b1461-e807-4202-b9b4-500bfdbb6b3f))
						- ((63a9ae52-49c6-4187-a324-95dc48c17a46))
						- Nioh
						- ((675aab12-39ac-44ff-bb10-b4ddb191ecb3))
						- Dark Souls
						- Ghost of Tsushima
						  id:: 644c09aa-e435-4087-9c43-349093a939f1
						- ((63209426-3e95-4515-9877-af2f9f1bfe07))
						- Furi
					- [Learning Resources]
						- [Ranking "Parry" Abilities in Video Games - YouTube](https://youtu.be/n8SJxSJNUao)
						-
				- Dodging
				  collapsed:: true
					- Perfect dodge
					  id:: 658ecccc-e274-4c73-9eb1-8a1d3eb9a3e5
					  collapsed:: true
						- Very brief time slow, for style reasons but no practical utility
							- ((632d02a6-96eb-4e27-851e-69567cd2fd39))
							- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
						- If timed correctly triggers time slow
							- ((632d02a6-96eb-4e27-851e-69567cd2fd39)) - [Perfect Dodge Practice - YouTube](https://youtu.be/kxCWe1gMq1A). Requires a specific plug-in
							- ((639c8949-dae4-42e3-9de6-fda7b519f9eb))
							- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
							- ((632093db-2034-4684-a5df-f2b8188e81ac))
							- ((64e0952a-37d7-4849-873b-3ef6483fac07))
							- ((644c09aa-e435-4087-9c43-349093a939f1)) - [Ghost of Tsushima - Perfect dodge - YouTube](https://youtu.be/b2jlogFKlxc)
							- ((64e9e72e-037d-462b-adcc-6053c4e2efbf)) - [Spider-Man PS4 [Perfect Dodge Guide] - YouTube](https://youtu.be/nNqmCRNlyFI)
							- ((6416d881-7184-425d-acf9-90b93098ee9d))
					- Invulnerability frame dodges
						- with iframe dodges
						- Elden Ring, Nier, WuWa, For spoken
						- Without
						- Sekir
					- Equipment weight affects dodge style
						- ((632d02af-9d3a-45b1-ab6d-69f923db836e))
						- Example styles
							- Hop
							- Dodge roll
							- Leaping dodge roll e.g. ((675c2b82-ac3c-47c0-9878-08f1c2996360))
							- Strafe e.g. ((675aab12-39ac-44ff-bb10-b4ddb191ecb3)), ((649b1461-cc38-49dd-a8be-f0b18d52ff05))
							- Nero ((632093da-8019-4aa4-b3d4-d9180b8a1d2a))
				- Ability types sorted by projectile/vector
				  collapsed:: true
					- Projectile
						- Examples
							- [Ashe's Frost Shot](https://www.leagueoflegends.com/en-gb/champions/ashe/) ( ((62e2844f-3eba-403e-ad55-73d00b47065e)) )
							- [Zigg's Bouncing Bomb](https://www.leagueoflegends.com/en-gb/champions/ziggs/)
					- Beam
					  id:: 63b2f44a-3dba-4922-b766-ebcb9cfb6b16
						- Examples
							- [Vel'Koz's Life Form Disintegration Ray](https://www.leagueoflegends.com/en-gb/champions/vel-koz/)
					- Arc
						- Examples
							- [Yone's Spirit Cleave](https://www.leagueoflegends.com/en-gb/champions/yone/)
							- ((63b2ff05-971b-4753-b6cf-f3ed73020f83))
					- Zone
					  id:: 63b2ed38-0cc9-4ddb-9bc7-9d4703cde637
						- Examples
							- [Miss Fortune's Make It Rain](https://www.leagueoflegends.com/en-gb/champions/miss-fortune/) ( ((62e2844f-3eba-403e-ad55-73d00b47065e)) )
						- *Subtypes*
							- Aura 
							  id:: 63b2f1eb-733c-43bc-9557-a50d82308b46
								- [Zac's Unstable Matter](https://www.leagueoflegends.com/en-gb/champions/zac/)
								- [Karthus' Defile](https://www.leagueoflegends.com/en-gb/champions/karthus/)
					- Vector
						- Examples
							- [Irelia's Flawless Duet](https://www.leagueoflegends.com/en-gb/champions/irelia/)
					- Thrust
						- Examples
							- [Pantheon's Comet Spear](https://www.leagueoflegends.com/en-gb/champions/pantheon/)
					- Directed Zone
						- Examples
							- [Pantheon's Aegis Assault](https://www.leagueoflegends.com/en-gb/champions/pantheon/)
					- Targeted
						- Examples
							- [Quinn's Vault](https://www.leagueoflegends.com/en-gb/champions/quinn/)
							- [Warwick's Infinite Duress](https://www.leagueoflegends.com/en-gb/champions/warwick/)
							- [Pantheon's Shield Vault](https://www.leagueoflegends.com/en-gb/champions/pantheon/)
							- [Karthus' Ultimate: Requiem](https://www.leagueoflegends.com/en-gb/champions/karthus/)
					- Homing
					- Thorns abilities
					  collapsed:: true
						- [Ranking "Thorns" Abilities in Video Games - YouTube](https://youtu.be/5vW_pYDucjU)
						-
					- [Learning Resources]
						- ((62e2844f-3eba-403e-ad55-73d00b47065e))
						- ((632093db-42a7-4662-8965-bac77a23d873)) - player and enemies
						- ((63a9ae59-d4b7-4772-9ed3-277fbab4ed34)) : ((ee42d1a5-3996-4a26-ac8c-017499184041))
				- Chain abilities
				  collapsed:: true
					- ((63b32cf5-2469-4584-9dfa-6f19f51fce95))'s The Darkin Blade
					- ((632d02af-2b02-45a3-86e2-52fe7520b541)) e.g. ((63b33bab-bf43-4d08-a11a-71be997b000f))
					-
				- Ammo-dependent basic attacks
				  collapsed:: true
					- Note: ((63b3498e-a44d-4032-b47d-cf0b2cfbbbd9))
					- Graves auto-reload
					- Relevance: can keep `R` or another reload key free for a different keybinding if reloading is automatic
				- Action combat vs tab-targeting
				  id:: 65875c92-4d9f-4c78-80e7-775624cd4386
				  collapsed:: true
					- Action combat
					  id:: 64e9e734-1441-4b4b-8212-700d8f5b3ef2
					  collapsed:: true
						- Meta
							- Minute screen shake and hit animations make melee combat feel much more impactful
							  collapsed:: true
								- [Nindo - Mini Clips #6 - YouTube](https://youtu.be/vdDKhHk5g1U)
									- {{video https://youtu.be/vdDKhHk5g1U}}
									- Hit animations
										- ![image.png](../assets/image_1726560571110_0.png)
						- ((632093e5-1f77-49e2-a0e0-60538a424d89)) games
						  id:: 65875cd7-f660-407b-9e4f-76700ad44819
							- _Released_
								- ((632d02af-2c75-415e-b20b-0a44238c96e8))
								- ((632d02af-9d3a-45b1-ab6d-69f923db836e))
								- ((644c0bb4-6a5b-4592-b085-b833fc9538e4))
								- Blade and Soul
								  collapsed:: true
									- Looks much better after Unreal Engine 4 update in 2021, and LazyPeon loves it's combat
									- P2W in end-game?
								- [Phantasy Star Online 2 New Genesis](https://store.steampowered.com/app/1056640/Phantasy_Star_Online_2_New_Genesis/)
								  id:: 642ed60c-9aee-4a05-92ab-50f32a2b6cf5
								  collapsed:: true
									- Controls
										- *Combat*
										- *Navigation*
											- `SPACEBAR`x2 = Double Jump
											- Hold `SPACEBAR` = Photon Glide
											- Double tap either `WASD` = photon dash (start sprinting)
										- `LMB` = Normal attack
										- `RMB` = Photon Arts (PA)
										- `X` = Dodge
										- `Q` = Lock On
										- `G`/`H` = move cursor left/right on Sub-Palette
										- `R` = activate selected item on Sub-Palette
										-
								- Crowfall
								- Swords of Legends Online
								  collapsed:: true
									- Pros/Cons
									  collapsed:: true
										- Pros
										  collapsed:: true
											- Isn't pay-to-win?
											- Graphics are great
										- Cons
										  collapsed:: true
											- Eastern fantasy isn't as cool as European medieval fantasy
											- World is quite instanced
											- Combat feels more spammy than strategic
											- Linear, on rails experience
									- LazyPeon preview
									    [https://youtu.be/H9woSaNKJxs](https://youtu.be/H9woSaNKJxs)
								- Elyon
								  collapsed:: true
									- Pros/Cons
									  collapsed:: true
										- Pros
										  collapsed:: true
											- Good combat
										- Cons
										  collapsed:: true
											- Visually dated since it's based on Unreal 3, despite the game releasing in 2021
											- Grinding and levelling boring
											- Korean MMO = pay-to-win
									- Previews
									  collapsed:: true
										- Kira - similar to BDO in a lot of ways
										  collapsed:: true
										    [https://youtu.be/IiKvd4qKXeU](https://youtu.be/IiKvd4qKXeU)
											- Also has aerial combat sequences, higher tech eg planes/guns/etc alongside fantasy
										- LazyPeon -
										    [https://youtu.be/q0UZE8fYyCA](https://youtu.be/q0UZE8fYyCA)
								- TERA
								  collapsed:: true
									- Cons
									  collapsed:: true
										- 2011 release, graphics kinda dated now
									- LazyPeon 2020 review -
									    [https://youtu.be/qT1jCDkTBas](https://youtu.be/qT1jCDkTBas)
							- _Upcoming_
								- ((632d02ae-e2b7-493e-a9cc-1fcfddc0e9de))
								- ((63ff821a-1309-4ad5-944d-b5cb4f3cd5b5))
								- Blue Protocol
								  id:: 67375ec1-6a7b-4e7e-9176-735aacc3dc11
								  collapsed:: true
									- [[2025-08-22 Friday]] [- YouTube](https://www.youtube.com/watch?v=j-dwZQ5NPAQ)
										- Looks similar to ((644c0bb4-9801-4ac3-a423-cf17703a148b)) in terms of UI, activities etc
										- Has an intersting sprint/jump mechanic which keeps you trying to time it to go faster (like ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) sprint )
										-
									- Looks decent but combat isn't as good as ((63ff821a-1309-4ad5-944d-b5cb4f3cd5b5)) and there's no PvP
									    [[Blue Protocol First Impressions "Is It Worth Playing?" - YouTube](https://youtu.be/SqZk6_MIBDI](https://youtu.be/SqZk6_MIBDI))
									- Pros/Cons
									  collapsed:: true
										- Action combat looks pretty good
										    [https://teddit.net/r/MMORPG/comments/nm8qa6/blue_protocol_combat_preview_and_new_class_reveal/](https://teddit.net/r/MMORPG/comments/nm8qa6/blue_protocol_combat_preview_and_new_class_reveal/)
									- JRPG
									- [[- YouTube](https://www.youtube.com/watch?v=SqZk6_MIBDI](https://www.youtube.com/watch?v=SqZk6_MIBDI))
					- Tab-targeting
					  id:: 658758e6-0cff-49c0-9cbd-9fb65e5c5615
				- ((6754f1d2-fba1-4e61-96fa-a506e3890924))
				- Multiple equipped weapons with weapon skills
				  id:: 65875a09-be65-4fe3-8822-5b9cea672a03
				  collapsed:: true
					- Dual weapon
						- Requires manually swapping the weapon to access other weapon skills
							- ((632d02af-9d3a-45b1-ab6d-69f923db836e))
							- ((63734e95-0e43-4014-8f8d-80db575226d1))
							- ((632d02af-2b02-45a3-86e2-52fe7520b541))
						- Automatically swap your weapon when you use a skill related to that weapon on your hotbar
						  id:: 65875a6d-57d2-4ea5-a5d5-f794b3b154f9
							- ((64e9e735-af8a-463c-83fc-12d86e17b07d))
							- ((6436d7ed-2ffc-4e9c-a880-be463753f07b))?
					- Quadruple weapon
						- ((632093da-8019-4aa4-b3d4-d9180b8a1d2a))
				- Attack combos
				  id:: 6743818a-9d53-46a4-a673-aee134d4bec8
				  collapsed:: true
					- Good examples
						- ((63734e86-47cc-4360-addf-cf2ded2c066d)) : ((67375eca-77b6-41d0-97fd-aa83be6462c1))
						- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
					- Related: ((630f97d2-68f2-4ff5-8816-6d455cc4f989)) : ((632093da-1c6a-4042-bac9-fd453ad47da5))
				- Challenging bosses
				  collapsed:: true
					- ((632093db-42a7-4662-8965-bac77a23d873))
					- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
				- Rollback netcode
				  collapsed:: true
					- Basically you will predict the next frame of the remote opponent, which will be that they're doing what they did last frame
					- As opposed to delay-based netcode
					- Usually they use a mix
					- https://youtu.be/0NLe4IpdS1w
					- [GGPO](https://github.com/pond3r/ggpo) is a common library for it
				- Levels of weaponry
				  id:: 64e0944c-4b9d-4eab-945e-d9fbfba127d5
				  collapsed:: true
					- Tiers of historical firearms
					  id:: 6667fbe1-5688-42d4-8ec0-a9cbeb405118
					  collapsed:: true
						- Meta
							- [/r/worldbuilding - why the gun hate?](https://www.reddit.com/r/worldbuilding/comments/1gn8kup/why_the_gun_hate)
								- As for why dune mostly avoids ranged weaponry: while it gives a lot of lore reasons why they aren't used (projectile weapons are countered by personal shields, laser weapons create explosions the size of a nuke when used against shields), I think the main "aesthetic" reason is to show humanity being technologically stuck similar of how we imagine the middle ages. That's why robots or any kind of AI are also banned and everybody is extremely religious. If i remember correctly, getting "unstuck" from this "middle age" is also a major theme in the later books.
						- # [History of firearms](https://en.wikipedia.org/wiki/Firearm#History)
							- [Fire lance](https://en.wikipedia.org/wiki/Fire_lance)
							  10th century China
							- [Hand cannon](https://en.wikipedia.org/wiki/Hand_cannon)
							  13th century China
							- [Matchlock](https://en.wikipedia.org/wiki/Matchlock) 
							  AKA firelock | 1410s Europe | Requires a flammable twine to be lit
								- *Guns*
									- [Arquebus](https://en.wikipedia.org/wiki/Arquebus)
									  1470s Europe
							- [Wheellock](https://en.wikipedia.org/wiki/Wheellock) pistol
							  1500 Europe | Uses a friction-wheel to spark (like modern cigarette lighters). First self-igniting firearm, so better resistance to rain, no telltale glow or burning smell, concealable
							- ### [Flintlock](https://en.wikipedia.org/wiki/Flintlock) types
							  1540-1810 | Uses a flint-striking ignition | [Drawbacks](https://en.wikipedia.org/wiki/Flintlock#Drawbacks) included misfires, accidental fires etc
								- Meta
									- Gunpowder (AKA powder, blackpowder) was a mixture of saltpeter (potassium nitrate i.e. oxidising agent), charcoal (fuel) and sulfur (increases combustion rate). It was usually stored in small containers or flasks and poured into the barrel of the pistol during the loading process.
									- Shot i.e. projectiles. Bullets (typically a spherical lead ball) for pistols. Pellets (multiple small lead balls) for blunderbusses or shotguns
								- [Snaplock](https://en.wikipedia.org/wiki/Snaplock)
								  1540s Europe
								- [Snaphance](https://en.wikipedia.org/wiki/Snaphance)
								  1560s Europe
								- [Flintlock](https://en.wikipedia.org/wiki/Flintlock_mechanism)
								  id:: 66680052-09dd-4900-8c9b-4b98cc4572bb
								  AKA true flintlock | 1610s Europe
									- *Guns*
										- [Pistol](https://en.wikipedia.org/wiki/Flintlock#Pistols)
										  collapsed:: true
											- [Traditional reloading](https://youtu.be/EcphrAcl-Hk)
											- Steps to reload in [[SS13]] : ((8488f9ed-04ec-444f-8494-7dc2fd3a79bb)) idea
												- Pouring Powder
												  id:: 66681b57-af7a-4b2d-8d1a-9a905de63847
												  A measured amount of gunpowder was poured into the barrel.
													- Either using a tiny flask of gunpowder, or taking a paper cartridge from your cartridge pouch
												- Wadding
												  id:: 66681b57-27fe-40a5-9bf1-52347c6e7c62
												  A piece of cloth or paper (wadding) was rammed down the barrel to hold the powder in place.
												- Inserting the Shot
												  id:: 66681b57-08e8-41f6-9246-ace62fd4fa40
												  The lead ball (or pellets) was placed on top of the gunpowder. Faster with ((66682221-04b5-4392-a701-7ea7ea210063)) as there's no need for ramming hard
												- Priming the Pan
												  id:: 66681b57-62e9-4b83-b8b2-8d7bd25d9777
												  A small amount of fine gunpowder was placed in the flash pan.
												- Cock and Fire
												  id:: 66681b57-2da5-4bf6-86ec-82ae2904e44b
												  The hammer, holding a piece of flint, was pulled back (cocked). When the trigger was pulled, the flint struck the steel frizzen, creating sparks that ignited the powder in the flash pan, which in turn ignited the main charge of gunpowder in the barrel, firing the shot.
										- [Muskets](https://en.wikipedia.org/wiki/Musket)
										  collapsed:: true
										  1660-1840 Europe | Their introduction caused the decline of plate armour due to it's high velocity
											- [Reloading using paper cartridge - contains bullet as well as powder](https://youtu.be/lfGOLqxcbIg)
											- Steps to reload in [[SS13]] : ((8488f9ed-04ec-444f-8494-7dc2fd3a79bb)) idea
												- *Stationary, automated steps*
													- ((66681b57-62e9-4b83-b8b2-8d7bd25d9777))
													- Paper cartridge to combine these steps:
														- ((66681b57-af7a-4b2d-8d1a-9a905de63847))
														- ((66681b57-08e8-41f6-9246-ace62fd4fa40))
														- ((66681b57-27fe-40a5-9bf1-52347c6e7c62))
													- ((66681b57-2da5-4bf6-86ec-82ae2904e44b))
										- [Blunderbuss](https://en.wikipedia.org/wiki/Blunderbuss)
										  Early 1600s-mid 1800s
									- Flintlock weapons vs compound crossbows
									  [_k_ - Compound bow vs flintlock - Weapons - 4chan (05_09_2024 13_13_52).html](../assets/_k_-_Compound_bow_vs_flintlock_-_Weapons_-_4chan_(05_09_2024_13_13_52)_1728644703827_0.html)
							- [Caplock](https://en.wikipedia.org/wiki/Percussion_cap)
							  id:: 666801aa-9d44-4a49-b86d-116e880c922c
							  AKA percussion cap / percussion lock | 1810s Europe | More resistant to rain than wheellock or flintlock; quicker and easier to load; more reliable; no smoke when fired | Brought about later invention of ((66680e62-c3fa-4284-a611-614bcb1ea461))
							- ### [Revolver](https://en.wikipedia.org/wiki/Revolver) types
							  1830s | First mass-produced breech-loading firearms
								- ((666801aa-9d44-4a49-b86d-116e880c922c))
								  1830s
								- [Cartridge](https://en.wikipedia.org/wiki/Cartridge_(firearms))
								  id:: 66680e62-c3fa-4284-a611-614bcb1ea461
								  AKA round | 1850s | i.e. bullet (projectile) and propellant (e.g. gunpowder) in one pre-assembled ammunition | Invented for breech-loading firearms
							- [Semi-automatic pistol](https://en.wikipedia.org/wiki/Semi-automatic_pistol)
							  1890s
						- # Long guns
							- Smooth-bored, muzzle-loading
							- Rifled muskets [were solved by invention of the](https://en.wikipedia.org/wiki/Musket#Replacement_by_the_rifle) Minie ball
							- [Minie ball](https://en.wikipedia.org/wiki/Mini%C3%A9_ball)
							  id:: 66682221-04b5-4392-a701-7ea7ea210063
							  1840s
								- Successor to round shot because it was loose enough not require being rammed down into a barrel, yet maintained good accuracy during firing
							- [Smokeless powder](https://en.wikipedia.org/wiki/Smokeless_powder)
							  1880s
							- [Breech-loading](https://en.wikipedia.org/wiki/Breechloading) firearms [largely came about due to development of](https://en.wikipedia.org/wiki/Breechloader#History) self-contained metallic cartridges in 1800s. Though they initially struggled due to the necessity of ejecting the previous cartridge case in order to reload
						- ## Misc
						- ## Fantasy fiction with firearms
						  id:: 666826d2-a19e-4862-943f-31bec644f055
							- ((6366b870-cb19-4cc7-be99-a591e295f610)) (heavy use of ((66680052-09dd-4900-8c9b-4b98cc4572bb)) pistols and muskets)
							- [[Mother of Learning]] : ((666829b6-7b19-4a27-a361-5599454aa2ad))
							- ((6602858f-1a1a-42f7-899e-b4c8f275c7c4)) - use of rifles, and artillery
							- ((63682fad-d46a-4eb4-8463-bf07980b6627)) Teaguewater had rifles, sounds like ((66680052-09dd-4900-8c9b-4b98cc4572bb))
							- Warhammer Fantasy
							- ((644c0c05-a3d8-48c1-b474-dc41847b7b44))
							- ### Notable counter-examples
								- ((6318fcc3-8b62-4e01-b92a-af642a01bb8d)) - none due to gnomes
								- ((65a6424c-e1ea-4807-9a89-efa5fd457bea)) - strong repulsor personal shields
								- ((640ba437-789c-45e6-860c-c92dd80f0372)) - Jedi can deflect projectiles or use their Force powers
					- Tiers of Sci-Fi Military Hardware
						- Tier 1
							- Disablers and Energy Guns
							  collapsed:: true
								- Eg as a fanfic idea could exchange these for the Basic Three Jutsu
								  collapsed:: true
									- Not sufficient to beat the other at their own speciality
									- We'd have Energy Shields, plus the weapons have limited ammo
						- Tier 1.5
							- ((64e9e72c-a562-400f-a494-8fe78b41fbaf)) Needler
							- ((64e9e72c-a562-400f-a494-8fe78b41fbaf)) Plasma Pistol
							- Tasers (SS13)
							- Stun Batons
						- Tier 2
						  Ballistics. Swapping from projectile to hitscan/very fast. But less armour penetration?
							- Sidearms
						- Tier 3 - Light Infantry
							- SMGs / Auto Rifles / Trace Rifles (rapid fire/continuous)
							- Hand Cannons
							- Scout Rifle (1 shot at a time)
							- Pulse Rifle (3-4 round burst
							- Fusion Rifle (7 shot burst, has RNG/recoil)
							- Energy Swords
						- Tier 4 - Heavy Infantry
							- Light Machine Gun (Destiny 2, Star Citizen, GTA V)
							- Miniguns
							- Sniper Rifle / Linear Fusion Rifle
							- Shotguns
							- Energy Katana (SS13)
						- Tier 5 - Anti-Fortification
							- Spartan Laser
							- Grenade Launchers
							- Rocket Launchers
							- Frag Grenades
							- Power Armour/Exosuits (Class IX / Mech L1) e.g. MAX, Ripley
							  collapsed:: true
								- MAX Exo-Suit ( ((63734e95-5ad3-4e2f-b3e4-c090bad28154)) )
								  collapsed:: true
									- https://vignette.wikia.nocookie.net/planetside2/images/7/7e/Class_MAX.gif
									- https://planetside.fandom.com/wiki/MAX
								- See Star Citizen class IX space suits
								    intralink2:: https://workflowy.com/#/b42471be3739
								- Ripley (SS3D)
								    https://ss3d.space/assets/img/posts/19.11.01/BwoinkMiniMech.png
								- Defiant (Worm)
								    https://vignette.wikia.nocookie.net/parahumans/images/5/50/Dragon_defiant_by_aerryi-d9b0dbb.png/revision/latest?cb=20160601150946
								- DVa's mech
								    https://overwatch.fandom.com/wiki/D.Va
								- ((644c0c03-17cf-4c6f-8bf8-fd1665dbf6c2)) Astartes armour
						- Tier 6 - Speeder class
							- Fast Attack Vehicles-class
							  collapsed:: true
								- M1161 ITV
								- Warthog vehicle with turret
								    https://www.halowaypoint.com/en-us/universe/vehicles/warthog
								- Spectre vehicle
								    https://www.halowaypoint.com/en-us/universe/vehicles/spectre
								- Harasser ( ((63734e95-5ad3-4e2f-b3e4-c090bad28154)) )
								    [Harasser | PlanetSide 2 Wiki | Fandom](https://planetside.fandom.com/wiki/Harasser)
							- Speeders
							  collapsed:: true
								- ((63542965-aaa8-4872-b7bb-026c76092669)) - X1; Nox; Dragonfly
						- Tier 7 - Light Armour class
							- Attack Helicopters-class
							  collapsed:: true
								- AH-1Z Viper
								    https://battlefield.fandom.com/wiki/AH-1Z_Viper
							- Scout Helicopters-class
							  collapsed:: true
								- AH-6 Little Bird
								    https://battlefield.fandom.com/wiki/AH-6_Little_Bird
								- Banshee ship
								- Hornet
								    https://halo.fandom.com/wiki/AV-14_Attack_VTOL
									-
							- APC-class
							  collapsed:: true
								- LAV-25 (Battlefield)
								    https://battlefield.fandom.com/wiki/LAV-25
								- Ursa Rover ( ((63542965-aaa8-4872-b7bb-026c76092669)) )
								- **Infantry Fighting Vehicle<**(**IFV</** also known as a mechanized infantry combat vehicle (MICV)
								- Sunderer (Planetside 2)
							- Transport Helicopters-class
							  collapsed:: true
								- Falcon
								    https://www.halowaypoint.com/en-us/universe/vehicles/falcon
								- UH-1Y Venom
								    https://battlefield.fandom.com/wiki/UH-1Y_Venom
						- Tier 8 - Heavy Armour class
							- Tanks
							  collapsed:: true
								- Grizzly
								  collapsed:: true
									- https://www.halowaypoint.com/en-us/universe/vehicles/grizzly
								- Scorpion
								  collapsed:: true
									- https://www.halowaypoint.com/en-us/universe/vehicles/scorpion
								- Wraith
								  collapsed:: true
									- https://www.halowaypoint.com/en-us/universe/vehicles/wraith
								- Tumbril Nova Tank
								  collapsed:: true
								    https://robertsspaceindustries.com/media/ul5zp2zllebm2r/store_slideshow_large/TMBL_HeavyTank_ShotG_PJ03-Squashed.jpg
									- https://robertsspaceindustries.com/pledge/ships/nova-tank/Nova
								- ((63734e95-5ad3-4e2f-b3e4-c090bad28154)) four tank types
							- Mech L2 (4-10m) e.g. Titans, Knightmares
							  collapsed:: true
								- Titans ( ((644c0bb7-b3f2-4c0c-b830-5d7976985142)) ) ~24ft/7m
								  collapsed:: true
									- ![image.png](../assets/image_1730665613517_0.png)
									-
									- https://titanfall.fandom.com/wiki/Titan
									- https://titanfall.fandom.com/wiki/Category:Titans_(Titanfall_2)
								- Knightmare Frame ( ((64f5d199-70ac-4585-b8e3-8b312e2960ff)) )
								  collapsed:: true
									- https://codegeass.fandom.com/wiki/Knightmare_Frame
								- Mantis
								    https://www.halowaypoint.com/en-us/universe/vehicles/mantis
								- Sentinels (2023 in X-Men: Days of Future Past)
								  collapsed:: true
									- https://youtu.be/Xc7LXPJDgNU
								- Gygax mech
								- Durand mech
								    https://68.media.tumblr.com/6d6303178c3ed5e71342684ef104ed40/tumblr_oto1o1ZvCS1vp3hgzo1_1280.png
								- Metal Gears (Metal Gear Solid)
							- Small spaceships (<25m)
							  collapsed:: true
								- Aegis Avenger
								  collapsed:: true
									- https://youtu.be/XNqa2vRSFtY
								- https://starcitizen.tools/Category:Small_ships
						- Tier 9 - Area Superiority class
							- Medium combat ships (25-50m)
							  collapsed:: true
								- Vanguard Warden
								  collapsed:: true
									- https://starcitizen.tools/Vanguard_Warden
								- https://starcitizen.tools/Category:Medium_ships
							- Fleet Carriers e.g. Bastion
							  collapsed:: true
								- [Bastion](https://planetside.fandom.com/wiki/Bastion_Fleet_Carrier/Main)
								  collapsed:: true
								  (Planetside 2)
									- ![image.png](../assets/image_1719223973910_0.png)
								- [Titan](https://battlefield.fandom.com/wiki/MK-1_Titan) (Battlefield 2142)
								  collapsed:: true
									- ![image.png](../assets/image_1719224031886_0.png)
								- [Drake Interplanetary Kraken](https://starcitizen.tools/Kraken) ( ((63542965-aaa8-4872-b7bb-026c76092669)) )
								  collapsed:: true
									- ![image.png](../assets/image_1719224074805_0.png)
							- Mech L3 (10-30m) eg Transformers
							  collapsed:: true
								- Transformers : [Mecha](https://transformers.fandom.com/wiki/Category:Mecha)
								- Gundam : [Mobile Weapons](https://gundam.fandom.com/wiki/Category:Mobile_Weapons)
								- [Metal Gears](https://metalgear.fandom.com/wiki/Category:Metal_Gears)
									- [Metal Gear Sahelanthropus | Metal Gear Wiki | Fandom](https://metalgear.fandom.com/wiki/Metal_Gear_Sahelanthropus)
									- [Metal Gear REX | Metal Gear Wiki | Fandom](https://metalgear.fandom.com/wiki/Metal_Gear_REX)
								- Most the [Nine Titans](https://attackontitan.fandom.com/wiki/Nine_Titans_(Anime)) (main titans of ((63ff8120-b5e6-4e65-ab30-85c48f7b2caf)) )
									- ![image.png](../assets/image_1719223053200_0.png)
									- War Hammer Titan
									  collapsed:: true
										- https://attackontitan.fandom.com/wiki/War_Hammer_Titan
									- https://attackontitan.fandom.com/wiki/Armored_Titan
									- https://attackontitan.fandom.com/wiki/Beast_Titan
							- Walking Tanks
							  collapsed:: true
							  AKA Walkers
								- [AT-AT](https://starwars.fandom.com/wiki/All_Terrain_Armored_Transport)
								  collapsed:: true
									- [https://starwars.fandom.com/wiki/All_Terrain_Armored_Transport](https://starwars.fandom.com/wiki/All_Terrain_Armored_Transport)
								- [AT-TE](https://starwars.fandom.com/wiki/All_Terrain_Tactical_Enforcer)
								  collapsed:: true
									- ![image.png](../assets/image_1719223136902_0.png)
						- Tier 10
							- Large spaceships (e.g. 125m)
							  collapsed:: true
								- Carrack
								  collapsed:: true
									- https://starcitizen.tools/Carrack
								- https://starcitizen.tools/Category:Large_ships
						- Tier 11
							- Mechs L4 (>60m) e.g. ((64e0944c-898a-480c-9bd5-d9e27059b13b))
							  collapsed:: true
								- [Jaegers](https://pacificrim.fandom.com/wiki/Jaeger)
								  id:: 64e0944c-898a-480c-9bd5-d9e27059b13b
								  collapsed:: true
								  (Pacific Rim) e.g. 250ft/76m
									- https://pacificrim.fandom.com/wiki/Category:Jaegers
									- ![image.png](../assets/image_1719223627550_0.png)
								- [Evangelions](https://evangelion.fandom.com/wiki/Evangelion)
								- [Colossus Titan](https://attackontitan.fandom.com/wiki/Colossus_Titan)
						- Sources
							- ((640ba437-789c-45e6-860c-c92dd80f0372))
							- ((64e9e72c-a562-400f-a494-8fe78b41fbaf))
							- ((63542965-aaa8-4872-b7bb-026c76092669))
							- ((63734e95-5ad3-4e2f-b3e4-c090bad28154))
							- ((6318fd58-0de6-4946-98ef-95fa22f457c6))
				- Magic system
				  collapsed:: true
					- Related:
						- [[Worldbuilding]] : ((63734eb1-85d8-4420-9b5e-5929ed4e383d))
						- ((630f97d2-68f2-4ff5-8816-6d455cc4f989)) : ((632093da-60c0-4d1e-8757-1c7b56a9c69b)) : ((680a9693-afd6-40a9-800d-c43dc67cf5ff))
				- ### Examples from media
					- ((649b1461-cc38-49dd-a8be-f0b18d52ff05))
					- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
					- ((639c8949-dae4-42e3-9de6-fda7b519f9eb))
					- ((6416d881-7184-425d-acf9-90b93098ee9d))
				- Related: ((67436760-9989-4867-ac00-af0ffd65d190))
			- Atmospherics
			- Highly Customisable Difficulty
			  id:: 67375ec1-2df3-47b6-b8c2-4e861f1b32df
			  collapsed:: true
				- Examples
					- Highly Customisable Difficulty
						- ((63503886-bb79-451d-9faa-58794efb38e7)) : ((6754f1dc-40ba-4e03-b7ab-002744b87d1b))
						- Rogue Legacy 2 - "house rules"
						- Arkham (Batman) games
						  id:: 64e0944c-3914-41d5-ab5f-266c7e2748f6
						  collapsed:: true
							- One game series that approaches difficulty well is the Arkham (Batman) games. As you progress through the game, you go from fighting standard thugs that just throw punches, the thugs wielding pipes and bats, then to armored thugs with stun batons and riot shields, and ones with guns. Once you've taken out a few groups in the "stealth" areas of the games, heartbeat monitors are added to enemies so you can't take them out one by one without being detected at all. This is a great way to slowly develop your aresnal of tactics as a player, having to deal with a variety of threats, then the game starts combining the different types of enemies and gives you the opportunity to play smart and vary your gameplay, rather than just having to beat up on higher health enemies in an unnecessarily prolonged fight.
							- I think a good way to design enemies with scaling difficulty in mind would be to start with the most advanced possible tactics, where the enemy will anticipate your attacks and try to avoid/block them, and respond in the most intelligent way when you use a certain tactic or ability, etc...that way you have your "hard" difficulty enemy. Then you can strip down aspects of that AI to make your medium and easy difficulties, where easy would just have them basically running at you and not responding too intelligently to your attacks.
						- [Dishonored 2](https://store.steampowered.com/app/403640/Dishonored_2/)
						  id:: 67375ec1-ff0a-4dd5-ba64-74539c4272b4
						  collapsed:: true
							- custom difficulty options also include a lot of examples of ways to make the game more difficult that are more interesting than just cranking up enemy health and damage but easier to implement than complex intelligent AI. Some examples are whether enemies can see you or not while you're leaning around a corner, how perceptive enemies are of things above them, how loud walking is, how long sleep darts take to take effect, whether healing elixirs are instant or heal over time (and how much they heal), and how many enemies will attack you at the same time. None of those are complex AI - all of them are things that, theoretically, are just changing numbers or toggling certain mechanics on or off, with the only difficulty of implementing them just being to make sure that those numbers can be changed or mechanics can be toggled without breaking anything. But they do serve as ways to make the game more challenging in ways that are more meaningful and not just tedious like making enemies take longer to kill.
						- Control
						  collapsed:: true
							- also let's you 'control' the different variables. Though the only way to do so is under enhancements (cheats) in the options. That seems like a decent way to do it, though. Give the balanced ideal version as default, and let the players know that modifications to that are at your own discretion.
						- Thief remake
						  collapsed:: true
							- is that it let you finetune the difficulty how you liked.
						- ((64e9e730-3133-4afb-a30f-e454885ba0a3)) - Kaycee's Mod
						  collapsed:: true
							- [https://inscryption.fandom.com/wiki/Kaycee's_Mod#List_of_Challenges](https://inscryption.fandom.com/wiki/Kaycee's_Mod#List_of_Challenges)
							- Many types of challenges, each give varying point worth in 5s. Need a certain amount total for next unlockable in this endless mode (adds new starting decks, lore text and potential cards)
					- _Low Customisable Difficulty_
						- The Metro franchise - low customisability but the best version of it. Yours and enemy health pool is lower, plus reduced resources each level
						- The Division 2 - enemies just become damage sponges
				- Related: ((63503886-24bc-4f20-8739-613cc1408d3b))
			- End-game progression
			  collapsed:: true
				- ((e5d5e948-1b4c-4187-b38e-5cb70ac9da20)) : ((66f16d2d-3761-437a-b25b-c4ffd3179a00))
				- ((6436d7ed-2ffc-4e9c-a880-be463753f07b))
				- ((632d02ac-e241-4bee-897b-97682e44733a))
				- ((632d02af-9d3a-45b1-ab6d-69f923db836e))
			- Good open-world
			  id:: 67375ec1-9e66-4b0c-a3a3-9351d55f59c2
			  collapsed:: true
				- # Features
					- ## Good
						- Auto-renewing, gatherable resources everywhere
						  collapsed:: true
							- New World - having mineable/forageable materials everywhere (and rare ones) makes it much more enjoyable to explore
							- 7 Days to Die - voxel-based world means everything is a resource of some kind
							- Mindustry
							- Satisfactory
						- Dungeons
						  collapsed:: true
							- Like ((632cd63c-fe84-44cd-bb15-85ce4c054eca)), ((632d02af-2c75-415e-b20b-0a44238c96e8)), ((64e0952a-37d7-4849-873b-3ef6483fac07)) shrines, ((632093db-42a7-4662-8965-bac77a23d873)), ((632093e2-9014-4f25-8fed-cf47c045231f))
							- Dungeons have lore, loot, enemies, NPCs, quests and puzzles
						- Unique weapons - ((632093db-42a7-4662-8965-bac77a23d873)); ((649b1461-f28d-4044-a0d9-63b96daeddff))
						- Side quests - ((632cd63c-fe84-44cd-bb15-85ce4c054eca)); ((649b1461-f28d-4044-a0d9-63b96daeddff))
						- Random events
						  id:: 67432c2d-71c9-4dab-b2f2-a307c41aec59
						  collapsed:: true
							- Good examples
								- ((632cd63c-fe84-44cd-bb15-85ce4c054eca)) [random encounters](https://elderscrolls.fandom.com/wiki/Random_Encounters_(Skyrim)), ((67434349-68c0-4223-8438-a0aa4c131a73)), [Immersive Patrols](https://www.nexusmods.com/skyrimspecialedition/mods/718)
									- Without mods there are already enough random events that make every walk in the field never feel the same (merchants traveling, bandit raids, warring factions, etc). But with mods it can be lot better: use WARZONES, Immersive Patrols, Immersive World Encounters, DFB Random Encounters, Extended Encounters, and Radiance. You can even get NPCs finishing quests with FollowerLivePackage/Follower Goes on Trip.
								- ((6318fd58-0de6-4946-98ef-95fa22f457c6)) - Public Events, and Heroic Public Events
								- ((632d02ab-0498-4fa3-bd00-a823b71576b9)) barbarians, tribal village, finding natural wonders
								- ((632d02a9-cd45-42a1-aad7-8062cc756fee)) visitors who are traders, people fleeing enemies, crash-landed resources, barbarian raids, manhunter packs, weather, solar flares, toxic fallout, diseases
									- ((632d02a9-cd45-42a1-aad7-8062cc756fee)) - Events chosen through a storyteller AI which evaluates the situation (Checks Population/Wealth/etc.) and reacts accordingly
									  collapsed:: true
										- [https://rimworldwiki.com/wiki/Events](https://rimworldwiki.com/wiki/Events)
								- ((6416d895-e7bf-4c2e-bd46-519ccdcda840)) - outlaws, runaway prisoners, and people in need of help
								- ### Apparently
									- ((6436aefb-b837-4985-a2a0-4922bcce7199)) - [random events](https://gta.fandom.com/wiki/Random_Events_in_GTA_V)
									- ((632d02af-2b02-45a3-86e2-52fe7520b541)) -
									- ((67375ec6-298c-411e-bb92-ad25a65d77fa)) - bandit ambushes, merchant caravans, and noble delegations, "you encountered trader with a broken cart, help/rob/ignore?" or "your brothers decided to kill each other for honour reasons, let them fight/order them to stop"
									- ((633b7574-d7f5-4251-9ec0-91420f47f961))
							- Related: ((67375ec1-fd7d-40cb-876f-e9b48e15b402))
						- Rewarding exploration
						  collapsed:: true
							- Aspects
								- Unguided exploration which doesn't have in-game markers on where to go to (e.g. like Elden Ring, unlike Ubisoft games)
								- Fast travel needed sparingly (e.g. New World or Skyrim, big distance between each fast travel area + few fast travel spots)
								- Compass vs minimap
								  collapsed:: true
									- Compass
									  collapsed:: true
										- Examples - New World (top of screen); Red Dead Redemption 2 (option to replace mini-map with it)
										  collapsed:: true
											- [https://www.vgr.com/red-dead-redemption-2-how-to-use-each-mini-map-option/](https://www.vgr.com/red-dead-redemption-2-how-to-use-each-mini-map-option/)
									- Minimap
									  collapsed:: true
										- Examples - ((6416d895-e7bf-4c2e-bd46-519ccdcda840)) (can also be expanded to double-size, like GTA V)
								- GPS or no
								  collapsed:: true
									- i.e. shows you with an arrow where your selected quest is
									- Examples
									  collapsed:: true
										- ((632d02af-9d3a-45b1-ab6d-69f923db836e)) uses a marker on compass
										- Red Dead Redemption 2 shows either marker on compass, or line on minimap
										-
								- Achievements with rewards tied to them
									- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) has Astrites attached to loads of achievements
						- Regular public events across game world
						- Player housing or base building
						  collapsed:: true
							- Craft a home from scratch
								- e.g. ((64e9e733-23d8-4b60-82a4-1ba505f4e452)), ((648f9076-9c44-4a26-8af5-8d709d1ab64d)), ((63503886-f4f6-4930-8a39-e5fbfcd42eed))
							- Buy an instanced room
								- e.g. ((632d02af-9d3a-45b1-ab6d-69f923db836e)), ((644c0bb6-00c0-4b8b-b30e-7efb5aa6277e))
						- Fun traversal
						  id:: 680fc5df-2942-4906-96fe-b017a19f4201
						  collapsed:: true
							- ### Priority to try
								- ((680fd87a-3c64-41e7-b4c2-91645b530e13))
								- ((65b65c2d-fda8-47eb-9d04-7f0740b50870))
								- ((680fd495-07d9-436d-acaf-2e55cebedd5c))
								- ((644c0bb4-4d37-4ef9-a8b7-7fcfd20887f4))
								- ((680fda33-4000-4c81-b615-db8f61d44523))
							- ### ((650820a5-74ab-4bcf-a106-c4226c774930))
							- {{embed ((650820a5-74ab-4bcf-a106-c4226c774930))}}
							- ### ((680ffca8-9d11-47e4-ae37-affa31c2bfb5)) : ((64e0944d-121f-49f5-8229-d029b9cd957e))
								- {{embed ((64e0944d-121f-49f5-8229-d029b9cd957e))}}
							- ### ((644c09aa-0a1f-40dd-aae1-45a6b1ed7b28)), ((67375ec1-b758-4a5b-9307-327f2143b181)), vertical wallrunning, gliding
								- ((680fd495-07d9-436d-acaf-2e55cebedd5c))
								- ((64e9e72d-680a-41ca-a8a4-e4af2cc8a574)) - superspeed, vertical wallrunning, big jumps, gliding
								- ((644c0bb4-4d37-4ef9-a8b7-7fcfd20887f4))
								- ((644c0bb4-3402-4593-b494-1459314b8581)) - big jumps
							- ((65b65c2d-fda8-47eb-9d04-7f0740b50870))
							- ((680fd87a-3c64-41e7-b4c2-91645b530e13))
							- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) - ((677d7583-43ff-4514-94bc-05b81cd5d2c6))
							- Mirror's Edge
							- ((67dea417-532e-4f40-a398-78a17c7831b0))
							- ((64e0952b-318c-48c2-8174-8bc4b26239f1))
							- Related: ((63734bb5-0a6f-44e9-8bfe-4a0206a1a4a9))
						- Simulated economy
						  collapsed:: true
							- Gives your actions consequences and gives NPCs a lifelike routine
							- ((632cfe94-c204-4902-80c8-08f0dcd48c13))
							- ((63a9ae57-9cb8-465b-b4f2-7b69a9655cf5))
							- ((64e0952a-893f-47f0-9162-90957f77bfab))
						- ((67375ec1-fd7d-40cb-876f-e9b48e15b402))
					- ## Bad
						- Too many map markers to events
						-
				- # Examples
					- ## Good
						- ((632cd63c-fe84-44cd-bb15-85ce4c054eca))
						- ((644c0bb4-9801-4ac3-a423-cf17703a148b))
						- ((634bc201-ab66-494b-8738-826601b04f57))
						- ((6416d895-e7bf-4c2e-bd46-519ccdcda840))
						- ((632d02af-9d3a-45b1-ab6d-69f923db836e))
						- ((648f9076-9c44-4a26-8af5-8d709d1ab64d))
						- ((632cfe94-c204-4902-80c8-08f0dcd48c13))
						- ((632d02a9-cd45-42a1-aad7-8062cc756fee))
						- [[SS13]]
						- ### Unplayed
							- ((64e0952a-37d7-4849-873b-3ef6483fac07)) : ((6741983e-c533-4a81-8a52-978388a28c33))
							- ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040))
							- ((632093db-42a7-4662-8965-bac77a23d873))
							- ((66dd529a-cd34-4cc4-82cb-cab617ad5216))
							- ((64e9e72d-7d1d-4195-99e0-c2d335e1ea1b))
							- ((644c0bb6-0313-4c23-94b4-fbc94b9c1ec2))
							- ((63734e95-0e43-4014-8f8d-80db575226d1))
							- ((6318fd52-c87b-4b6c-9ea1-fea756d1d4a8))
							- ((63ff81d5-9245-4704-8653-c206210ad4c9))
							- ((67375ec9-e8bf-47c8-813d-952722f818e7))
							- ((67375ec9-ca58-4b64-9fe3-d956ca0efde0))
							- ((64e9e72c-1a9e-45ff-9d27-f4083ffe50cb))
					- ## Mid
						- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d))
						- ((63734e80-3981-4b17-a325-d4ba7f823565))
						- ((64e9e733-23d8-4b60-82a4-1ba505f4e452))
						- ((632d02af-2c75-415e-b20b-0a44238c96e8))
						- ((6436aefb-b837-4985-a2a0-4922bcce7199))
					- ## Bad
			- Attributes
			  collapsed:: true
				- Good examples
					- Skyrim
					- ((632d02af-9d3a-45b1-ab6d-69f923db836e))
					- Divinity: Original Sin 2
			- Social & Personal stats + gameplay
			  collapsed:: true
				- _Social stats_
				  collapsed:: true
					- One stat like RimWorld
					    https://rimworldwiki.com/wiki/Social
				- Personal stats
				  collapsed:: true
					- Needs
					    https://rimworldwiki.com/wiki/Needs
					- https://rimworldwiki.com/wiki/Health
					- https://rimworldwiki.com/wiki/Skills
					- Traits
					    https://rimworldwiki.com/wiki/Traits
				- Relationship+Friendship stats per character like The Sims
				    http://sims.wikia.com/wiki/Relationship
			- Dialogue systems
			  collapsed:: true
			  AKA social conversation with NPCs
				- Alpha Protocol
				  collapsed:: true
					- You can reply in one of four tones:
						- Aggressive, Suave, Professional or Silence
						- Action, Thrills, Duty, Silence
						- Confident, Dismissive, Practical, Attack
					- Limited time window to respond
				- Skyrim
				- Fallout
				- Mass Effect
				- ((63b02dcb-33f9-41fc-8a0a-19baef5f6b81)) : [persuasion mini game is actually a pretty interesting take on the RNG dilemma of dialogue checks in role-playing games](https://libreddit.lunar.icu/r/truegaming/comments/18kfhdy/starfields_persuasion_mini_game_is_actually_a/)
					- Before people bring out their pitchforks, I'm not saying starfield has great role playing overall. However one particular mechanic related to it caught my attention. When it comes to persuasion checks in games you either have it being solely based on skill level, RNG or perhaps both. The system in star field goes for the latter.
					- Whenever you try to get your point across the mini game activates, you have 3 chances to make arguments choosing from different possibilities with each their own chance of success and approval point gain. Get enough approval points in these steps and you succeed. At first this just seems like the same thing with literal extra steps but this seemly simple system has some unapparent benefits.
					  id:: 663a9988-8451-4a09-91f7-84a353e9e01a
						- \-it being several steps can lessen the impact of RNG feeling cheap since it doesn't hinge on one failure but rather your character failing many times.
						- \-If a reply makes sense in the current context it has a higher chance to succeed, which can help with both RP'ing different characters and aiding players that just want to succeed as long they pay attention.
						  id:: 663a997c-ee8a-45d3-b02b-a7dbe12bba8f
						- \-outside of just having skills that increase the chance of succeeding a step, you also have skills that unlock new kinds of possibilities like being able to bribe to get your point across
						- \-it can create more natural conversations since there's more back and forth.
					- Now the implementation in starfield ain't perfect but still great and I feel this kind of system deserves a try in other games too, it's a good mix of making the mechanic dynamic while still being versatile enough to be used across a big non linear game as you don't need to make every possible reply unique.
					- I love to see this ((663a997c-ee8a-45d3-b02b-a7dbe12bba8f)). I'm really tired of games doing the Mass Effect formula. You could have "I WILL KILL YOU AND YOUR ENTIRE FAMILY" under paragon, and you'd KNOW you'd get the paragon option, irregardles of what's actually getting said.
						- Modern CRPGs sometimes fail into that as well, with showing results, mostly making you aim for results rather than reading the situation and saying something appropriate. And what's appropriate may just vary... be agressive to a civilian and you might lose favor, but be agressive to a scumlord in a bar and you might gain favor.
					- Bannerlord
						- ((663a9988-8451-4a09-91f7-84a353e9e01a)) Bannerlord does the same, and it did it first. On top of that, character traits, earned through gameplay, influence it. All reacting to the traits the other guy has.
						  It does it better! Good luck influencing someone as a merciful lord when the other guy is a total dirtbag.
			- ((63531eea-d78d-4e60-a053-0edd8b75764c))
			  id:: 635036a8-0d12-441d-9c0c-6f264ac8c1ef
			- Hygiene
			  collapsed:: true
				- Good examples
				  collapsed:: true
					- Rimworld - Hygiene mod which adds cleanliness/toilet/thirst meters
					- The Sims - hygiene/toilet/hunger meters
			- NSFW features
			  collapsed:: true
				- RimWorld - cannibalism; making art and clothing out of human body parts
				- SS13 - cannibalism; sex; dismemberment
			- Mini-games
			  collapsed:: true
				- Examples
					- ((67dea417-532e-4f40-a398-78a17c7831b0))
					- ((64e9e731-2c51-4f40-8b68-85f38a224f43))
					- Dave the Diver
					- ((64e9e731-e25f-45ba-9adb-f149401e954d))
				- Mini-games for skills
					- Skyrim lockpicking
					- ((632d02af-2c75-415e-b20b-0a44238c96e8))
					- ((632d02af-9d3a-45b1-ab6d-69f923db836e))
			- Computers in-game
			  collapsed:: true
				- Lua scripting in Dual Universe
				- (Lua) ComputerCraft for [Minecraft](https://workflowy.com/#/v_aae130f17e85_d1f0835fa2b6_6e16c8126dfe4782)
				  collapsed:: true
					- https://github.com/dan200/ComputerCraft
				- DCPUs in Tech Compliant
				  collapsed:: true
					- intralink2:: https://workflowy.com/#/8c502eeeb6d8
				- OpenComputers
				  collapsed:: true
					- https://ocdoc.cil.li/
			- Crafting
			  collapsed:: true
				- New World - portable camp can be used to craft low-level items; crafting stations needed for higher-level crafting
				- 7 Days to Die - crafting slower on-person compared to in a worktable; some crafting required being done in a specific machinedddddd
				- Divinity: Original Sin -
				- SS13
				- ((632cd63c-fe84-44cd-bb15-85ce4c054eca)) - crafting stations
				- Minecraft
				- ((6318fd52-c87b-4b6c-9ea1-fea756d1d4a8))
				- 1 Backlink
				  collapsed:: true
					- See [Craft](https://workflowy.com/#/277ad4edf6c2)<a href="https://workflowy.com/#/277ad4edf6c2">ing</a>
				- Improvised crafting
				  collapsed:: true
					- The Escapists
					- See [Space](https://workflowy.com/#/f649d71e0a7c)<a href="https://workflowy.com/#/f649d71e0a7c"> </a><a href="https://workflowy.com/#/f649d71e0a7c">Station</a><a href="https://workflowy.com/#/f649d71e0a7c"> </a><a href="https://workflowy.com/#/f649d71e0a7c">13</a><a href="https://workflowy.com/#/f649d71e0a7c"> (SS13)</a>
					- Divergence
					    http://store.steampowered.com/app/422940/
					- For weapons and tools
			- Companions/pets/mounts
			- Economy
			  collapsed:: true
				- _Good examples_
				  collapsed:: true
					- ((632cfe94-c204-4902-80c8-08f0dcd48c13)) - real-time economic simulation. Merchant ships regularly drop off goods but can be raided, which affects prices and supply in that city. Can profit arbitrage selling different goods in different star systems. Economy has long-term consequences
					  collapsed:: true
						- Economy has long-term effects e.g. pirates can raid you later using better designed ships
						  collapsed:: true
							- I've been playing this game for a year or so, and it's fantastic. Highly recommend, some of the best $15 I've ever spent.
							- The game does some things which you wouldn't expect a game to do. I found a ton of valuable blueprints in an abandoned station in the middle of space, and some of the big battleship designs were duplicates of what I already had, so obviously I chose to sell them for profit. But why would I pay that 30% trade tariff? Nah man, fuck that shit. So, I docked at a pirate station and sold them the battleship blueprints on the black market.
							- ...big mistake. I mean, I really should have thought that through. Within a few years, the pirates attacking my merchant fleets had high-tech battleships... built from the designs I'd sold to them. I had to spend millions upgrading my colony world Patrol HQs so I could have larger escort fleets for my merchant convoys, completely negating any profit I made off selling those blueprints.
							- It was awesome. I love a game with that level of depth. And it's just gonna keep getting better.
					- Rimworld - can make money from farming, production of drugs/clothing/art/weapons/foodtRW
			- Base building
			  collapsed:: true
				- _Good examples_
				  collapsed:: true
					- 7 Days to Die - block-based buildings but some blocks have many different shapes e.g. wood blocks or railings
					- Rust - piece-based but it's smooth and works well
					- Dual Universe - voxel-based
					- Satisfactory - create huge factories
					- ((632d02a9-cd45-42a1-aad7-8062cc756fee))
					- See [Minecraft](https://workflowy.com/#/v_aae130f17e85_d1f0835fa2b6_6e16c8126dfe4782)
					- ((67375ec5-fb82-4aec-98e4-7c76445c30b7))
				- 1 Backlink
				  collapsed:: true
					- See [Base building](https://workflowy.com/#/801e605ba5ce) - mostly 7 Days to Die style, plus Satisfactory automation
			- Tech tree
			  collapsed:: true
			  AKA TechWeb
				- Good examples
				  collapsed:: true
					- Rust
					  collapsed:: true
						- _Current system_
						  collapsed:: true
							- Tech Tree
							  collapsed:: true
								- [source] [https://www.rustafied.com/updates/2020/12/3/tech-trees-are-here](https://www.rustafied.com/updates/2020/12/3/tech-trees-are-here)
								- 3 tiers of tech tier, and progression involves unlocking each item in a linear fashion
							- Blueprint system
							  collapsed:: true
								- Pros/Cons
								  collapsed:: true
									- Pros
									  collapsed:: true
										- Like real-life you can sell Blueprints for how to make an item, or sell the items themselves and carve out a business niche as a skilled vendor
								- Blueprints - can be found or use a Bluebook Page/Book/Library (latter for higher rarity)
								    [https://rust.fandom.com/wiki/Blueprints](https://rust.fandom.com/wiki/Blueprints)
								- Researching - make Blueprints using scrap + the items you want to make a blueprint of, at a Research Table
								    [https://rust.fandom.com/wiki/Research_Table](https://rust.fandom.com/wiki/Research_Table)
						- _Deprecated_
						  collapsed:: true
							- Workbench Experimentation - get a random blueprint in exchange for an amount of scrap, blueprint tier limited by workbench tier
							  collapsed:: true
								- For each tier workbench (1, 2 or 3), an amount of scrap can be traded for a random same-tier blueprint.  For example, placing 75 scrap in a workbench tier 1 will give you a random blueprint from the tier 1 items, such as a metal hatchet, or revolver.  Tier 2 will cost 300 scrap for a tier 2 random blueprint etc.
							- XP System - gain XP via crafting/fishing/hunting/mining/etc. Higher your level, the more advanced items you can make
							  collapsed:: true
							    [https://rust.fandom.com/wiki/Tech_Tree](https://rust.fandom.com/wiki/Tech_Tree)
								- Pros/Cons
								  collapsed:: true
									- Pros
									  collapsed:: true
										- Simple, intuitive method
									- Cons
									  collapsed:: true
										- You need to grind to make advanced items
					- 7 Days to Die
					  collapsed:: true
						- You need Blueprints to learn how to craft each advanced item. Some Blueprints can be earned through simply putting stat points into that attribute
					- Space Station 13 - several implementations
					- ((632d02ab-0498-4fa3-bd00-a823b71576b9))
					- Minecraft vanilla - acquiring newer materials lets you craft newer items, cyclical
					- Minecraft mods
					- Rimworld vanilla - use a research bench with one colonist manning it to complete a research. Tree-based
			- Maps
			  collapsed:: true
				- If you want to make navigation more meaningful, don't remove quest markers. Remove the player marker.
					- Kingdom Come: Deliverance in Hardcode mode doesn't have it
						- They also add a lot of landmarks to help you navigate without player mark. Very well done.
			- Inventory
			  collapsed:: true
				- Weight limits are pointless
					- [Inventory and weight management are boring in most RPG I have played, and I have heard most of its excuses - r/truegaming](https://snoo.habedieeh.re/r/truegaming/comments/1gb0740/inventory_and_weight_management_are_boring_in#)
					-
			- Nemesis System
			  collapsed:: true
				- ((65b65c2d-fda8-47eb-9d04-7f0740b50870))
				- ((632cd63c-fe84-44cd-bb15-85ce4c054eca)) : ((644c0bb4-92cd-40f4-95ad-8bddbc042dfc))
				- The idea that the player can get killed by some random orc grunt and then see that orc rise through the ranks and become the player's greatest nemesis is something you wouldn't be able to get with a more scripted structured set of enemy leaders.
			- Combat Interaction] Interactions with monsters involving different moves/part by interrupting monster's actions and attacking on the weakness.
			- Controls] High-level operation that requires the grasp of precision/reaction time/timing.
			- Puzzle Solving] Enjoying solving puzzles/problems for certain purposes.
			- Strategy] Gameplay that requires thinking/planning to find optimal solutions.
			- Graphics] Exquisite visuals and appealing art style.
			- Sound Design and Music] High-quality sound effects, dubbing, and background music.
			- Exploration] Exploring , random events, easter eggs in the game.
			- Character Design] Character personalities and background story.
			- [Team and Equipment Combination] Combining different equipment and character for different combat styles (such as set builds, skill sets and team-up strategy).
			- Random Elements - Random elements and designs for a non-repetitive experience (Such as Roguelike dungeons)
			- Worldview/Theme -Intriguing world settings or themes.
			- Storyline - An interesting and exciting storyline.
			- Socialization - Meeting new friends and interacting with other players in the game. Rich Gameplay] Interesting mini-games outside combat system.
			- Power Level - Growing stronger with better weapons and character development.
			- Competition - Competing with other players, challenging/surpassing opponents (rankings, ranks, etc.).
			- Immersion - Better immersion for an enhanced experience.
			- Collection - Rich collectible elements (such as characters, skins, items, achievements, etc.)
			- Challenge - High difficulty/challenging gameplay/bosses that can only be overcome through practice.
			- Freedom - High degree of freedom for customized demands.
			- Relaxation - Easy and simple event design that requires less mental effort.
		- # Examples of games with/without depth
		  collapsed:: true
			- Games with depth
				- ((65c744a5-892b-4e16-a2a9-5f883733af29)) : ((65c744a8-730d-4cbc-8172-9d745b964ff8))
					- {{embed ((65c744a8-730d-4cbc-8172-9d745b964ff8))}}
				- [Construction and management simulation](https://workflowy.com/#/9f121d6dd637) games e.g. Dwarf Fortress
					- RimWorld - character traits, needs, crafting,  mining, research
					- [[SS13]]
				- [All ideal features](https://workflowy.com/#/036ad3f534e4) Shinobi Life Online competitor - movement, environment, skills
				- ((633b7574-d7f5-4251-9ec0-91420f47f961)) or Skyrim - huge campaign, number of skills, collectable weapons/armour
			- Games without depth
				- Star Citizen - procedural environments, FPS, spaceship dogfights
				    intralink2:: https://workflowy.com/#/77497ad48459
				- N[o](https://workflowy.com/#/05ecea48ba49)<a href="https://workflowy.com/#/05ecea48ba49"> </a><a href="https://workflowy.com/#/05ecea48ba49">Man's</a><a href="https://workflowy.com/#/05ecea48ba49"> </a><a href="https://workflowy.com/#/05ecea48ba49">Sky</a>
				- ((67375ec5-fb82-4aec-98e4-7c76445c30b7))
				- Nin Online
	- RPG elements
	  collapsed:: true
		- Companions
		  AKA sidekick
			- ((632d02a6-96eb-4e27-851e-69567cd2fd39)) - Pods
			- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) - Abby
			- ((6416d881-7184-425d-acf9-90b93098ee9d)) - Paimon
			- ((63209426-3e95-4515-9877-af2f9f1bfe07)) - Mimir, Atreus
			- ((64e9e72d-1333-4fbc-b000-4af3ef53541f)) - BD-1
			- ((673dc0d7-1eae-487a-b256-900d77a1f5d7)) - Nix
			- ((6318fd58-0de6-4946-98ef-95fa22f457c6)) - Ghost
			- ((64e9e72c-a562-400f-a494-8fe78b41fbaf)) - Cortana
			- ((644c0bc0-afb0-4f36-aacc-1bcc5aa204cf)) - Claptrap
			- ((644c0bb4-83b8-41d7-86a6-5dbeeada6622)) - Morgana
			- ((676ebd86-d91c-4a02-8312-71522117c1f6)) - Lydia
			- ((63a9ae55-dced-410f-a40d-75d689151b5f)) - Ellie
			- ((6416d895-8b66-49d3-8e4e-b030d3f18a2d)) - Cuff
			- ((634bc201-ab66-494b-8738-826601b04f57)) - Johnny Silverhand
			- ((644c0bb7-b3f2-4c0c-b830-5d7976985142)) - BT-7274
		- ## Bad
			- [Ghost Train Ride](https://youtu.be/OCKZsyz7B5U)
			  collapsed:: true
			  for linear adventure games
				- Definition:
					- Queue - cinematic scenes, puzzles, one route. NPCs who badger you to get back focused on the Queue
					- Thrills - surprise set piece which involves the risk of death unless you do a QTE or some kind of action
					- Gift Shop - finally the rewarding part, player is allowed to do some combat. Stuck in an arena environment
				- Examples
					- ((6754f1e8-528c-4844-aa43-1025bbd8522c)), The Last of Us, Tomb Raider new gen, Uncharted, God of War, Jedi Fallen Order
	- MMO elements
	  collapsed:: true
		- War dynamic
		- Sieges
		- Transport
			- Mountable creatures for land travel
			- Boats for the seas.
		- ELO based rating
		  collapsed:: true
			- https://en.m.wikipedia.org/wiki/Elo_rating_system
				- A player's Elo rating is represented by a number which increases or decreases depending on the outcome of games between rated players. After every game, the winning player takes points from the losing one. The difference between the ratings of the winner and loser determines the total number of points gained or lost after a game. In a series of games between a high-rated player and a low-rated player, the high-rated player is expected to score more wins. If the high-rated player wins, then only a few rating points will be taken from the low-rated player. However, if the lower rated player scores an upset win, many rating points will be transferred. The lower rated player will also gain a few points from the higher rated player in the event of a draw. This means that this rating system is self-correcting. A player whose rating is too low should, in the long run, do better than the rating system predicts, and thus gain rating points until the rating reflects their true playing strength.
		- Advanced systems
			- Economy
				- Player trading vs an exchange system
					- [Making sure you're not a bot!](https://red.artemislena.eu/r/truegaming/comments/1on9h0h/the_grand_exchange_runescapes_downfall/)
					-
			- Virtual recreation
			- Housing
			- Base building
			- Marriage
		- Balancing
			- ((6318fd58-0de6-4946-98ef-95fa22f457c6)) : ((644c0bc0-4fc7-4c84-9ec9-ed62f3138190))
			- _See_ MtG uses Standard as a rotating format every 1-2 years
		- ((67375ec1-9e66-4b0c-a3a3-9351d55f59c2))
	- PvP elements
	  collapsed:: true
		- ((67375eca-bff2-41c4-b8e9-1893287b7f00))
	- Monetisation
	  id:: 644c09aa-eabe-4f53-9bea-f56eacc9304b
	  collapsed:: true
		- Real Money Transactions (RMT)
		  id:: 644c09aa-2014-4f02-a148-dd2218155839
		  collapsed:: true
		  AKA Microtransactions / MTX / macrotransactions
			- _Acceptable with caveats_
				- Cosmetics
				  id:: 64e0944b-c169-431b-8f53-4a965b9b6b4a
				  collapsed:: true
				  e.g. skins,
					- Pros/Cons
					  collapsed:: true
						- Pros
							- Doesn't limit the fun of the core gameplay loop at all
						- Cons
							- We used to be able to just unlock nice cosmetics through gameplay e.g. best armour sets or PvP emotes in ((64ccaf0d-aa29-4849-941f-94b5c672a5f3))
					- _Examples of games which purely use this_
						- ((686427b8-751d-470f-a128-1439f1ef2fd0))
						- Dota 2
					- _Examples of games which also include this_
						- ((6436af07-f2b9-4bb5-9c67-4dce6f32a415))
						- PUBG
						- Overwatch
					- Elements
						- Cosmetic options for a SS3D game
							- THREE new types of cosmetic options have been added to ((6350388b-832c-47b4-92eb-c65fe8af02a2))
								- Artifacts - These are optional magical relics that float behind your character. During CB 1.1, two are available to choose between: the Fracture and the Orrery. You can also choose a "None" option if they're not to your liking.
								- Afterglows - These are trails that emit from your character's feet when you're levitating. During CB 1.1, two are available to choose between: Simmering Rage or Light's Purity.
								- Cloudbursts - These are particles that flow out of your character while dropping in to the map. During CB 1.1, two are available to choose between: the Cerulean Spiral or the Prismatic Flare.
					- It needs to be also able to be unlocked in game if it's a MMO, where loot is why people keep playing the game
				- Limited usage items
					- _Examples of games which also include this_
						- ((686427b8-751d-470f-a128-1439f1ef2fd0)) sprays
			- _Controversial_
				- Convenience
				  collapsed:: true
					- They build inconveniences into the game, to later sell you conveniences
				- Boosters
				  collapsed:: true
					- _Examples of games which purely use this_
					  collapsed:: true
						- Clash of Clans
					- _Examples of games which also include this_
						- { ((6436af07-f2b9-4bb5-9c67-4dce6f32a415)) } Boosts - basically double exp + gold for a while
				- Unlockable Content
				  collapsed:: true
					- Pros/Cons
					  collapsed:: true
						- Pros
						  collapsed:: true
							- In most games (especially RPGs), it's normal to unlock extra content or items or whatever the further you get into the game
							- If core gameplay loop is fun and diverse, then people are more okay with there being a few options behind paywalls
						- Cons
						  collapsed:: true
							- There needs to be a way to earn it via playtime and not just real money otherwise it's a paywall on progression
							- The steepness of the grind to unlock the content instead through just playtime can determine whether the game forces you to pay to unlock (often making it pay-to-win in multiplayer games)
					- _What_
					  collapsed:: true
						- Compared to DLC, this is content that from game launch is already behind a pay wall
					- _Examples of games which also include this_
					  collapsed:: true
						- { ((6436af07-f2b9-4bb5-9c67-4dce6f32a415)) } Heroes
						    Though there is a free rotation of heroes available
						- GTA Online businesses
						- ((63542965-aaa8-4872-b7bb-026c76092669)) ships
						- Chronicles of Elyria titles
				- Downloadable Content (DLC)
				  collapsed:: true
				  e.g. expansions
					- Pros/Cons
						- Cons
							- Destiny 2 and ((633b7574-d7f5-4251-9ec0-91420f47f961)) both shown it's best to later eventually make those DLCs free once your playerbase is bored with the existing free content.
							- "They split the community and lock gear making it required for consumers to pay up if they want to keep top gear and play with their friends that have the new content. DLC packs in general are exactly what most multiplayer games are moving away from with battle/season passes cause it gives all main content (maps, guns) to every player while giving cosmetics/xp to those willing to pay for it, no longer cutting the community in half making it terrible for every consumer while the developer makes additional money off the consumers."
					- _Examples of games which also include this_
					  collapsed:: true
						- Witcher
						- Skyrim
						- Destiny
						- ((633b7574-d7f5-4251-9ec0-91420f47f961))
				- ((644c09ab-7ccf-40ca-a3d1-04688ceb712f))
				- Lootboxes
				  collapsed:: true
					- Examples of games
						- ((63ff8219-c5df-42bd-8a16-756b5cd0c5a7))
						- ((62e2844f-3eba-403e-ad55-73d00b47065e))
						- ((6306a6fd-5caa-4b20-97a2-99c8fc74fc2a))
						- ((644c0bb4-6a5b-4592-b085-b833fc9538e4))
				- Season pass
				  collapsed:: true
					- Usually a mix of ((64e0944b-c169-431b-8f53-4a965b9b6b4a)),
					- FOMO-inducing by having limited time events and rewards cosmetics
				- Premium currencies
					- Creates psychological distance since you don't spend real money directly, you have to do an intermediate step
			- _[Learning Resources]_
				- Games which are popular because they are standouts for NOT being heavily monetised
				  collapsed:: true
					- ((63b0486e-cdac-468f-ae86-8b9ce6e027d6)) [is way more popular than Battlefield 2042](https://www.reddit.com/r/pcgaming/comments/14htsgc/battlebit_remastered_is_dominating_steam_because/) - it's a 1/3rd or less of the box price, it's got additional fun features (environmental destruction, 254 player matches), it doesn't have silly battlepass or monetisation, but it doesn't even have good graphics
					- Deep Rock Galactic + Warframe have got very positive reviews - compared to Destiny 2
					- ((64e9e731-e25f-45ba-9adb-f149401e954d)) - compared to FarmVille
					- ((64e0952a-9d60-4a12-887c-975c287cc7df)) - compared to Diablo III, Torchlight III
					- Dota 2 - compared to League, all heroes are available for free
					- Left 4 Dead 2 - compared to Back 4 Blood
					- ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040)) - compard to Assassin's Creed Odyssey
					- ((66a2459a-aa55-4816-b69b-b3a26d08672b)) - compared to ((6306a6fd-5caa-4b20-97a2-99c8fc74fc2a))
					- Monster Hunter: World - compard to Middle-earth: Shadow of War
					- Minecraft - compared to LEGO Worlds
				- Heavily monetised, no good competitors
				  collapsed:: true
					- Genshin Impact
					- FIFA
					- ((644c0bb9-13bd-462d-8c29-8c4ef125f89c)) - might be dethroned by ((668e500d-b8cc-4ddf-8c27-982745d71713))
					- Call of Duty
					- Apex Legends, Fortnite
					- Rainbow Six: Siege
					- Rust
					- Grand Theft Auto V
				- Many listed here around 8m - every MMO has them
				    [https://youtu.be/etnoU35ArEA](https://youtu.be/etnoU35ArEA)
			- Related: ((64e0944d-4bcc-4880-9f1e-6797202a72f1))
		- [[Open-Source Software]] : ((632cf49f-a6f7-4d2d-b3a5-3ee44968263e))
		  #Software-FOSS
		- _[Learning Resources]_
			- 3 strategies of monetisation for games
			  collapsed:: true
				- Sure there's plenty of examples where Epic paid exclusivity, excessive microtransactions or a high grind/P2W content exists and the game is still successful, but they succeed in spite of it. It benefits the business, but hurts the consumer.
				- It's much better instead the model of Dota 2 and CS:GO where monetisation is entirely based on cosmetics and core gameplay loop is unaffected. And I think more F2P games would succeed if they stopped limiting the fun gameplay experience you can have based on how much grinding or paying you do.
				- Another good strategy is paid content DLCs like Destiny 2 and World of Warcraft, though as they've both shown it's best to later eventually make those DLCs free once your playerbase is bored with the existing free content.
				- You can also lock extra content behind grinding/paying like GTA Online businesses, Star Citizen ships and Chronicles of Elyria titles. Just as long as your core gameplay loop is fun and the grind isn't too harsh.
				- See? 3 strategies there which don't harm consumers but still ensures the business can get paid. By going the easy money route of Epic exclusivity instead it should be obvious why consumers dislike that.
	- Quality of Life
	  collapsed:: true
		- ((644c0bb7-d88f-4d25-ac7e-0f4123fd3040)) -like summary before each session
			- [source] [https://teddit.net/r/patientgamers/comments/rpotkt/more_games_need_to_have_the_witcher_3s_summary/](https://teddit.net/r/patientgamers/comments/rpotkt/more_games_need_to_have_the_witcher_3s_summary/)
		- Permanent tutorial mode for returning players
			- e.g. Vermintide 2
			- [https://teddit.net/r/truegaming/comments/r7n1pc/games_should_have_a_permanent_tutorial_mode/](https://teddit.net/r/truegaming/comments/r7n1pc/games_should_have_a_permanent_tutorial_mode/)
	- Addictive games features
	  id:: 64e0944d-4bcc-4880-9f1e-6797202a72f1
	  collapsed:: true
		- Categories
			- ### FOMO-inducers
			  id:: 6502fa28-1e56-4ad4-be4f-1e0d5f9d76a4
			  AKA Fear of Missing Out
				- Daily quests/rewards
				- Limited time sales
			- ### Gamification
				- Levelling up system with real consequences (Better stats, skills, gear)
				- Examples
					- ((633b7574-d7f5-4251-9ec0-91420f47f961))
			- ### Pay-to-win
			  id:: 644c09ab-7ccf-40ca-a3d1-04688ceb712f
				- How
					- Limited features
					- Disadvantages for players who don't pay to speed up getting better gear, level etc
				- Categories
					- Gear
					- Buffs
						- Experience
						- Armour
					- Resources
				- Examples of games
					- Clash of Clans
					- Farmville
				- _Related:_ ((644c09aa-eabe-4f53-9bea-f56eacc9304b))
			- ### Encourages grinding
				- Meta
					- A lot of these are due to making money earning difficult, and having purchasable items which have meaningful gameplay effects
				- Examples
					- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) - like in many gacha games there is a stamina/energy mechanic which limits your rewards from certain repeatable quests to a few times per day. Also there is a few classes of limited pools - the others being ((673bd74e-8b2d-411d-bf75-770ddf835cd3)) which resets weekly and ((tower of adversity. The characters and 4/5 star weapons also require a ton of astrites to gamble to win. Levelling up character or weapon costs resources, and each new tier of 10-20 levels requires more materials for ascension
					- ((632d02ac-e241-4bee-897b-97682e44733a)) - lots of materials needed to craft
					- ((6306a6fd-5caa-4b20-97a2-99c8fc74fc2a)) - max 3 quests at a time, new one daily like gacha games. Battle pass for additional experience but it has both a free and paid lane. EXP from games is only counted for first 15 wins per day?
					- ((632d02a9-cd45-42a1-aad7-8062cc756fee)) - lots of stuff to buy, weapons, armour, drugs, organs, cybernetics, spaceship construction, lots of tech unlocked by research desk, caravans,
					- ### Apparently
						- ((64e0952a-9d60-4a12-887c-975c287cc7df))
						- ((632cfe94-c204-4902-80c8-08f0dcd48c13))
						- ((64e9e72d-7d1d-4195-99e0-c2d335e1ea1b))
						  collapsed:: true
							- Early on I always felt broke in this game, and even once you get going there’s always better equipment to buy. Better weapons, armour, horse, horse tack. Depending on the maintenance skill level, you can also have to take armour and weapons to be repaired. You can buy skill books, and pay to get training to up your skills. You also need to eat in the game, so you can hunt and gather food, or just buy at stores and inns.
							  
							  And if you get the DLCs, there’s one where you rebuild a village, and that turns into a huge money sink to get it all built, and depending on what you do it can actually be losing money by the day at first until you get more things built.
						- ((64e0952a-893f-47f0-9162-90957f77bfab))
						- ((64e9e72e-c7e4-4a3b-b14a-bcfb82753ba7)) - settlements, fleet building
						- ((66f33155-bff5-4cb9-bc0b-15c41544ba82))
						  collapsed:: true
							- When you level up, you get memory points, crafting points and learning points. Crafting points are levelling up lockpicking, rhetoric, crafting skill, and so on. Learning points are for levelling up combat skills. To use your points and increase your skills, you have to use a learning book or a crafting book of the correct level and skill. So, apprentice learning books will only level your skills up to 25, adept is 50 and so on up to master at 100. The books are single use for 1 level of one skill and the price goes up every tier until levelling one skill up 1 point costs you like 1500 gold. There's also still weapons, armor, potions and real estate to eat your gold. I've yet to feel comfortable financially and I'm level 24.
						- ((6436aefb-b837-4985-a2a0-4922bcce7199)) online
						- ((63b02dcb-33f9-41fc-8a0a-19baef5f6b81)) - ship building
						- ((64e0952e-b6ba-4dc3-ae69-99b92e2f353c))
						- ((67375ec6-298c-411e-bb92-ad25a65d77fa))
						- ((67375eca-e20b-44a9-873e-6922ed5fcf90))
			- ### Encourages completionism
				- Examples
					- ((632093e2-45af-4437-b2a1-ba228ce5a08a)) - there are lots of expensive significant upgrades available such as higher levelled weapons, crafting components, cyborg tech upgrades, etc. Ammo also remains expensive throughout e.g. power cells and .50 cal, to the point they recommend each squad member using a different type of gun ammo (at least for early-game)
					- ((644c0bb4-9801-4ac3-a423-cf17703a148b)) - rewards astrites for tons of achievements in the game including first-time doing X, milestones of how many times doing Y, etc. Astrites are used for the relatively expensive characters or rare weapons
					- ((634bc201-ab66-494b-8738-826601b04f57)) - lots of expensive cyberware, cars, housing
			- ### Locking mechanics behind bosses
				- Meta
					- This gives a goal for players to spend time to upgrade themselves and work towards, whilst also giving them direction for after by utilising the new rewards
				- Examples
					- ((63503886-f4f6-4930-8a39-e5fbfcd42eed)) - allows you to unlock the next tier of gear
					- ((64e0952a-c643-4e2f-841f-43d3d78a0070)) - [Bosses](https://terraria.wiki.gg/wiki/Bosses) rewards
					- ((67375ec9-05f0-4fe7-92e7-ee1c9f7b1633)) [Bosses](https://hollowknight.fandom.com/wiki/Category:Bosses_(Hollow_Knight))
					- ((63a9ae59-d4b7-4772-9ed3-277fbab4ed34)) - beating bosses can reward you [powers, structures and/or recipes](https://www.ign.com/wikis/v-rising/All_V_Blood_Bosses_and_Rewards)
			- ### Hours long rounds
				- Examples
					- [[SS13]]
			- ### Attention demanding
				- Examples
					- ((63734e92-d7d1-4094-b3e9-97390685ebc0))
		- _Related:_
			- ((644c09aa-2014-4f02-a148-dd2218155839))
			- ((63209269-77da-4c9a-993b-40a26e05dd12))
			    #OnFriendships
	- Use network stack for single shard topology
	  collapsed:: true
		- Use CoE's network stack for single shard before/after they've tested it
		- ((63542965-aaa8-4872-b7bb-026c76092669)) server meshing
		- Dual Universe single shard tech
	- _Related:_
		- ((6416d854-4ee1-47fa-84c8-d49b19b606c2)) : ((65bbef18-75b1-40d7-aec9-ed002ad7b2a7))
		- ((632cfccb-8554-4050-8044-21eefaef67fa))
		- Ideal Naruto game features
		  [[Videogames]]
		- SS13 Ideal Remake features
		  collapsed:: true
			- Features
				- Character
					- Character customisation
					- Needs
						- Sims 4 Needs - Hunger, Bladder, Hygiene, Energy, Social, and Fun
						- RimWorld needs - Food, Rest, Joy, Beauty, Comfort, Space
						    https://rimworldwiki.com/wiki/Needs
					- Body parts/organs (like ((632d02a9-cd45-42a1-aad7-8062cc756fee)))
					- Biohazards e.g. diseases
					- Multiple damage types
						- Brute
						- Burn (cold/hot)
						- Toxic (carcinogen: e.g. hydrogen/chlorine)
						- Stun (only for brains)
						- Radiation (e.g. uranium)
				- Jobs
					- https://nanotrasen.se/wiki/index.php/Guides
					- https://nanotrasen.se/wiki/index.php/Roles
					- _Meta - job aspects_
						- Entertainment e.g. clown, mime, barman
						- Paperwork e.g. coroner, detective, and cargo
						- ID card for door access
						- Radios for department messaging
						- Combat - FPS, spaceship and automated defenses
					- _Specific jobs _
						- Construction
							- Specific tools
								- Anti-grav generators - to build floating refueling stations, satellites etc
								- Break into spaceships using circular saws (like Space Engineers)
								    https://youtu.be/D42MlPuffHE?t=226
							- Spaceship building
								- v1 complexity - build engines, doors etc in one click
								    e.g. Dual Universe https://youtu.be/rVzpScPkNYE?t=257
								- v2
									- Pads
									    https://youtu.be/Ab9q5ZQw20M?t=671
							- Mining
							- Hacking
								- https://nanotrasen.se/wiki/index.php/Hacking
								-
							- https://nanotrasen.se/wiki/index.php/Guide_to_Construction
							- Factories - save constructions so you can mass produce and sell vehicles/buildings etc
							- Delivery chutes
								- Unstable mutagen from chemistry to botany
								- Raw food from botany to
							- RedistHeat (centralised climate control)
							    https://ludeon.com/forums/index.php?topic=21770.0
							- Quantum Storage (sorta replicates transport chutes)
							    https://steamcommunity.com/sharedfiles/filedetails/?id=1195015110
							- Dubs Bad Hygiene (incudes plumbing/waste disposal, central heating, air conditioning/cooling)
							    https://steamcommunity.com/sharedfiles/filedetails/?id=836308268
							- MarsX - atmospherics, etc
							    https://ludeon.com/forums/index.php?topic=25926.0
							- Rimstation13
							    https://ludeon.com/forums/index.php?topic=36827.0
							-
						- Cooking
						- Chemistry, genetics, medicine
							- Chemistry
								- https://nanotrasen.se/wiki/index.php/Chemist
								- https://nanotrasen.se/wiki/index.php/Guide_to_Chemistry
								- ((632d02a9-cd45-42a1-aad7-8062cc756fee)) mods for more drugs
									- Complete Drug Overhaul (about a dozen craftable drug recipes)
									    https://ludeon.com/forums/index.php?topic=32819.0
									- More Consumables and Mutagens
									    https://ludeon.com/forums/index.php?topic=33284.0
									- Nuke's Drug Cocktails
									    https://steamcommunity.com/sharedfiles/filedetails/?id=853758537
									- MedicalDrugs
									    https://steamcommunity.com/sharedfiles/filedetails/?id=844859500
									-
									-
								- Science Never Stops (infinite research option)
								    https://ludeon.com/forums/index.php?topic=34000.0
							- Genetics
								- Duties: Clone people, play with DNA, find powers.
								    https://nanotrasen.se/wiki/index.php/Guide_to_Genetics
								- RW mods
									- Genetic Rim (create hybrid animals)
									    https://ludeon.com/forums/index.php?topic=35158.0
									- Clone Bay
									    https://rim-world.com/clone-bay-mod/
									- Powers
										- A RimWorld of Magic
										    https://ludeon.com/forums/index.php?topic=37161.0
											- Guide
											    https://i.redd.it/h58603eijng11.png
										- Star Wars: Force mod
							- Medical
								- Surgery - damaged body parts like in RimWorld or SS13 BayMed
								- expanded prosthetics and organ engineering OR Rah's Bionics and Surgery Expansion
								- Misc. Robots++ (medical ER bot)
								    https://ludeon.com/forums/index.php?topic=26151.0
							- Virologist
							    Also known as Pathologist or a Microbiologist
								- Curing
								    https://nanotrasen.se/wiki/index.php/Guide_to_Virology#Curing
									- detecting whether someone has an unknown virus is to take their blood and put it in the centrifuge in virology.
									- If there isn't currently an outbreak on the station, you'll have to deal with infecting and injecting monkeys.
							- Roboticist
							    Or rather, a Biomechanical Engineer or Mechatronic Engineer
								- https://nanotrasen.se/wiki/index.php/Roboticist
								- Duties: Create and maintain a cybernetic and robotic army, and build impressive mech suits.
								- Guides: Guide to Robotics
							- Scientist
							    Scientist (Or rather a Xenoarcheologist, Anomalist, Plasma Researcher, Xenobiologist, or Chemical Researcher) is o
								- Duties: Do experiments, research, and make bombs.
								- Guides: Guide to Research and Development, Guide to Toxins, Guide to Chemical Research, Guide to Telescience, Guide to Xenobiology Guide to Chemistry, Guide to the E.X.P.E.R.I-MENTOR
								- https://nanotrasen.se/wiki/index.php/Scientist
						- Civilian
							- Bartender
								- https://nanotrasen.se/wiki/index.php/Guide_to_Food_and_Drinks
							- Chef
								- https://nanotrasen.se/wiki/index.php/Guide_to_Food_and_Drinks
					- Antagonists e.g. traitor, wizard, blob,
					- Management - security cameras, ID cards
					- Comms - radio departments, intercom,
					- Inventory - on-body; hands; backpack; toolbelt; held toolboxes
					- Intents - harm,
					- Hygiene and waste recycling
				- Vehicles
					- Land Vehicles
						- Design - see ((640ba437-789c-45e6-860c-c92dd80f0372))
							- Something like ATT Battle Tank
							    https://www.syfy.com/sites/syfy/files/styles/860xauto/public/wire/legacy/databank_aatbattletank_01_169_9de46aea.jpeg?itok=t2RmDWbe&timestamp=1497663261
							- AT-TE Walker
							    https://www.syfy.com/sites/syfy/files/styles/860xauto/public/wire/legacy/ATTE-ST.jpg?itok=QLC96PH0&timestamp=1497663261
							- X-34 Landspeeder
							    http://origin.blastr.com/sites/blastr/files/styles/blog_post_in_content_image/public/X34-landspeeder.jpg?itok=H4MRTaaI
							- Speeder Bike
							    http://origin.blastr.com/sites/blastr/files/styles/blog_post_in_content_image/public/databank_speederbike_01_169_c4204c29.jpeg?itok=PpbaTybv
						- Other inspiration - ((63542965-aaa8-4872-b7bb-026c76092669)), Space Engineers
					- Space stations
						- _Design_
							- Trade Federation Battleship
							    http://origin.blastr.com/sites/blastr/files/styles/blog_post_in_content_image/public/databank_tradefederationbattleship_01_169_fc5458ce.jpeg?itok=oGKSjWX6
							- Death Star
						-
					- Smuggling e.g. drugs, weapons, stolen goods
				- Complexity
					- wealth of options that I have to do a single task, like getting through an airlock.
						- Get AI to open it
						- Hack it
						- Steal someone's access
						- Emag it
						- C4 it
						- RCD dismantle it
						- Exosuit drill it
						- Dismantle the associated APC and crowbar it open
				- Gamepad controls
				    intralink2:: https://workflowy.com/#/f5906bdd27b9
				- _Related:_
					- See [Space](https://workflowy.com/#/f649d71e0a7c)<a href="https://workflowy.com/#/f649d71e0a7c"> </a><a href="https://workflowy.com/#/f649d71e0a7c">Station</a><a href="https://workflowy.com/#/f649d71e0a7c"> </a><a href="https://workflowy.com/#/f649d71e0a7c">13</a><a href="https://workflowy.com/#/f649d71e0a7c"> (SS13)</a>
					- SS3D fork idea
					  [[Videogame design ideas]]
					- Stationeers or other SS13 remake
					    intralink2:: https://workflowy.com/#/72a0bd301913
					- ((63542965-aaa8-4872-b7bb-026c76092669)) or other FPS sim
			- ((63542965-aaa8-4872-b7bb-026c76092669)) /MMO-like features
				- Interesting Worlds
					- Procedural full-destructible planet (like Space Engineers, ((67375ec5-fb82-4aec-98e4-7c76445c30b7)), Stationeers etc)
					- Lots of flora and fauna (like ((64e9e72e-c7e4-4a3b-b14a-bcfb82753ba7)) )
				- Spaceship customisation
					- Hardpoints for modular weaponry
					- Upgrade to better thrusters, shielding etc (like ((64e9e72e-c7e4-4a3b-b14a-bcfb82753ba7)) )
					- Customisable design (like Space Engineers, ((67375ec5-fb82-4aec-98e4-7c76445c30b7)) )
				- NPCs - space-faring aliens, creatures
		- Unity Store [assets](https://workflowy.com/#/443cde325406)
- _[Learning Resources]_
  collapsed:: true
	- The Rise of the Systemic Game | Game Maker's Toolkit - YouTube
	    [https://www.youtube.com/watch?v=SnpAAX9CkIc](https://www.youtube.com/watch?v=SnpAAX9CkIc)
	- Building Better Skill Trees | Game Maker's Toolkit - YouTube
	    [https://www.youtube.com/watch?v=wsmEuHa1eL8](https://www.youtube.com/watch?v=wsmEuHa1eL8)
	- [What Makes a Good Combat System? - YouTube](https://www.youtube.com/watch?v=8X4fx-YncqA](https://www.youtube.com/watch?v=8X4fx-YncqA)
		- Usually has ((6754f1d2-fba1-4e61-96fa-a506e3890924)) - more than one option available
		- Has more than one defensive option - e.g. dodge and block, maybe even counter/parry (timed block)
		- Poise so that enemies can't be easily stunlocked
		- Stamina meter so you get punished for spamming attacks
		- Varied and challenging enemy design
		- Telegraphed attacks via visual and/or sound indicators
		- Enemies which are resistant to certain attacks, but not so invulnerable that you're limited to one option against them
		- Satisfying combat - animations, sound, slow-mo, recovery animation
	- https://www.reddit.com/r/gamedev
	- ((634bc201-ab66-494b-8738-826601b04f57)) : Update 2.0
	-
- _Related:_
	- [[Videogames]]
	- ((632092fc-a990-4d64-9150-855b5615136c))
	    #Programming