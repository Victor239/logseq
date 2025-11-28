- Pros/Cons
  collapsed:: true
	- Pros
	- Cons
	- Unclear
	- Comparisons
		- ((6808efda-33f4-42ca-82f6-a159691e835f))
		- ((631219e3-ce87-482f-a283-a8cb0f8b23f5))
		- ((nix))
- # Documentation
	- ## Concepts and tools
		- What is Docker
		  collapsed:: true
			- you have a web container, a database container, a container that saves files, and so on. Each container is different and communicates with each other via IPs and Ports. PaaS platforms also uses container technologies.
		- Installing Docker
		  id:: 63a9ac98-506d-4a32-a94c-29cb647fceff
		  collapsed:: true
			- Quick and easy install script provided by Docker
			  `curl -sSL https://get.docker.com/ | sh`
			- [Installing on Ubuntu 22.10](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)
			  id:: 63aec847-b868-47ef-84fe-eeb5a4f62113
			  collapsed:: true
				- Install pre-requisites
				  ```
				  sudo apt-get update
				  sudo apt-get install \
				      ca-certificates \
				      curl \
				      gnupg \
				      lsb-release
				  ```
				- Add Docker's official GPG key
				  ```
				  sudo mkdir -p /etc/apt/keyrings
				  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg`
				  ```
				- Setup the repository
				  ```
				  echo \
				    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] [Index of linux/ubuntu/](https://download.docker.com/linux/ubuntu) \
				    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
				  ```
				- `sudo apt-get update`
					- If there's a GPG error
						- ```
						  sudo chmod a+r /etc/apt/keyrings/docker.gpg
						  sudo apt-get update
						  ```
				- Install Docker Engine, containerd, Docker Compose
				  `sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin`
				- Verify Docker Engine install is successful
				  `sudo docker run hello-world`
			- ((63a9ac98-d8f1-4006-a1fd-6001dd842c97))
			- Docker Machine
			  collapsed:: true
			  Installed locally, used to provision servers with Docker
				- https://github.com/docker/machine
				- https://www.digitalocean.com/community/tutorials/how-to-provision-and-manage-remote-docker-hosts-with-docker-machine-on-ubuntu-16-04
			- Docker for Mac/Windows
			  collapsed:: true
				- https://docs.docker.com/docker-for-mac/
				- https://docs.docker.com/docker-for-windows/
				- Supersedes Docker Toolbox
				  Available for both Windows and Mac, the Toolbox installs Docker Client, Machine, Compose and Kitematic.
					- https://www.docker.com/products/docker-toolbox
		- Docker Images
		  collapsed:: true
			- Images are like a blueprint for the containers. Images tell Docker what the container should be. You can’t run images; instead you build containers from them. On the Docker Hub you can see a list of images
			- e.g. use image for Ubuntu, MySQL, NGINX, WordPress
		- Dockerfiles
		  collapsed:: true
			- Very important: how to rebuild a docker image whilst using the cached layers from earlier steps in a Dockerfile
			  collapsed:: true
				- Why: Early steps in a Dockerfile might takes ages to do, so whenever you rebuild the image it takes a long time
				- `docker rmi -f image-name` = delete the Docker image
					- This means when you `build` next it'll use the cached layers
					- You can obtain the Docker image name via `docker images`
			- Docker ENTRYPOINT vs CMD
			  collapsed:: true
				- Entrypoint
					- In order to use multiple commands you can't just use `&&`
						- e.g. `entrypoint: echo hi && echo bye`
						- You must instead use `entrypoint: /bin/sh -c "command1 && command2"`
					- Entrypoint scripts seem to require being defined in the container itself, which means rebuilding the container in order to make edits to the script
						- Then again can just use my later notes of `docker rmi` in order to quickly rebuild the image for dev
			- `sleep infinity` should be used instead of `wait infinity` as the entrypoint for a Docker container to keep it running
			- More readable way of formatting `entrypoint:` in `docker-compose.yml`
			  collapsed:: true
				- ```yaml
				  entrypoint:
				    - /bin/sh
				    - -c
				    - |
				     echo "hello"
				     echo "goodbye"
				  ```
			- Dockerfile [FROM](https://docs.docker.com/reference/dockerfile/#from)
			  collapsed:: true
				- Basic usage is to use it once without `AS` keyword in order specify the base image for the entire Dockerfile
				- Docker multi-stage builds
					- `AS` keyword to define build stages, and `--from` to use stuff from one build stage to a later build stage. They're self-contained otherwise
					- ```
					  FROM ubuntu:22.04 AS build-stage
					  <do some stuff>
					  FROM nginx AS deploy-stage
					  COPY --from=build-stage /app/* /usr/share
					  ```
			- ARG variables
				- ARG vars declared before the FROM line can be used in the FROM line itself (e.g. to parameterise the base image)
				- ARG vars declared after the FROM line are only available from that point onward in the Dockerfile, but not persist into RUN instructions unless explicitly passed or converted to ENV
			- if using ENV later (to allow the image to access certain variables) you need to first use it in ARG earlier in the script
			- What Are Dockerfiles?
			  id:: 65435c62-f1c9-4e99-ae95-612bde88fcc0
			  collapsed:: true
				- Dockerfiles are scripts containing commands declared successively which are to be executed, in the order given, by Docker to automatically create a new image.
				- Filename is always `Dockerfile`
				- https://www.digitalocean.com/community/tutorials/docker-explained-using-dockerfiles-to-automate-building-of-images
				- Examples
					- ```dockerfile
					  FROM busybox
					  ENV FOO=/bar
					  WORKDIR ${FOO}   # WORKDIR /bar
					  ADD . $FOO       # ADD . /bar
					  COPY \$FOO /quux # COPY $FOO /quux
					  # Comment
					  RUN echo 'we are running some # of cool things'
					  ```
					- ((649b0fea-21db-4636-abd5-1909a731a60a)) Nitro:
					  id:: 6543a9c6-44fa-47cf-91cc-5d3d873af37d
					  `docker build -t hello-world .`
						- ```dockerfile
						  # Download base image Ubuntu 22.04 (LTS)
						  FROM ubuntu:22.04
						  ENV LOCALREPO=~/Documents/nitro
						  
						  RUN apt update
						  RUN apt install -y python3-pip git
						  RUN pip3 install -U pytest flask flasgger flask_cors
						  
						  # Copy source local git repo into Docker dest
						  COPY $LOCALREPO ~/nitro
						  WORKDIR ~/nitro/examples/api
						  
						  # Clean up package pache to reduce image size
						  RUN rm -rf /var/lib/apt/lists/*
						  RUN apt clean
						  RUN echo 'Docker build successful'
						  
						  CMD ["python3", "webapi.py"]
						  ```
						- Related: ((654a4141-92a7-48f7-a12c-b9e250a398b7))
				- [Dockerfile reference | Docker Docs](https://docs.docker.com/engine/reference/builder/)
				  collapsed:: true
					- Template
						- ```dockerfile
						  # Comment
						  INSTRUCTION arguments
						  ```
							- The instruction is not case-sensitive. However, convention is for them to be UPPERCASE to distinguish them from arguments more easily.
					- A `Dockerfile` **must begin with a `FROM` instruction**. This may be after [parser directives](https://docs.docker.com/engine/reference/builder/#parser-directives), [comments](https://docs.docker.com/engine/reference/builder/#format), and globally scoped [ARGs](https://docs.docker.com/engine/reference/builder/#arg). The `FROM` instruction specifies the [*Parent Image*](https://docs.docker.com/glossary/#parent-image) from which you are building. `FROM` may only be preceded by one or more `ARG` instructions, which declare arguments that are used in `FROM` lines in the `Dockerfile`.
					- [Parser directives](https://docs.docker.com/engine/reference/builder/#parser-directives)
						- Can be added to the top of Dockerfiles
						- Example
							- ```Dockerfile
							  # knowndirective1=value
							  # knowndirective2=value
							  ```
					- [Environment replacement](https://docs.docker.com/engine/reference/builder/#environment-replacement)
						- `ENV` statement can be used to declare environment variables
						- `$variable_name` or `${variable_name}` to reference those environment variables
						- Example
							- ```dockerfile
							  FROM busybox
							  ENV FOO=/bar
							  WORKDIR ${FOO}   # WORKDIR /bar
							  ADD . $FOO       # ADD . /bar
							  COPY \$FOO /quux # COPY $FOO /quux
							  ```
						- Supported by:
							- `ADD`
							- `COPY`
							- `ENV`
							- `EXPOSE`
							- `FROM`
							- `LABEL`
							- `STOPSIGNAL`
							- `USER`
							- `VOLUME`
							- `WORKDIR`
							- `ONBUILD` (when combined with one of the supported instructions above)
					- [.dockerignore file](https://docs.docker.com/build/building/context#dockerignore-files/)
						- You can use `.dockerignore` file to exclude files and directories from the build context.
					- All statemnts
						- [`FROM`](https://docs.docker.com/engine/reference/builder/#from)
							-
				- Preventing prompt errors during package installation
				  collapsed:: true
					- The installation of some packages attempts to open additional prompts to further customize installation options. In an non-interactive  environment, such as during the construction of a Docker image, attempts to open these dialogs results in errors like:
					- ```
					  unable to initialize frontend: Dialog
					  ```
					- These errors can be ignored as they don't prevent the packages from 
					  being installed. But the errors can be prevented by setting the `DEBIAN_FRONTEND` environment variable to `noninteractive`:
					- ```dockerfile
					  RUN DEBIAN_FRONTEND=noninteractive apt-get install -y python3
					  ```
					- The Docker website provides [official guidance on the use of the DEBIAN_FRONTEND environment variable](https://docs.docker.com/engine/faq/#why-is-debian_frontendnoninteractive-discouraged-in-dockerfiles).
					  They consider it a cosmetic change, and recommend against permanently 
					  setting the environment variable. The command above sets the environment
					  variable for the duration of the single `apt-get` command, meaning any subsequent calls to `apt-get` will not have the `DEBIAN_FRONTEND` defined.
				- Related:
					- ((6463499d-b2c2-41e3-9f06-5b5fd75a452b))
					- ((644c0b9b-9c03-42c8-99b7-f9dfb8282bbb)) : ((652d41e6-e0d1-4b9c-be90-c959bd89a75d))
		- Docker Compose
		  id:: 65435c62-530d-4efc-8940-14bbfda5cca6
		  collapsed:: true
			- How to get `echo` working properly when you run `docker compose`
				- `docker compose build --progress=plain --no-cache` = the `build` part is key
			- You can use the name of a service like a flag in order to run docker-compose up with only that service activated
			- Overriding the Docker entrypoint
			  collapsed:: true
				- Entrypoint is the executable file which can be run when a container is run, and can be baked into an image (by using ENTRYPOINT in the Dockerfile for it)
					- This can be overridden by specifying `entrypoint:` either in
						- `docker-compose.yml`
							- Example
								- ```
								  entrypoint:
								    echo "hello"
								  ```
						- `docker-compose run`
							- `docker-compose run --entrypoint="echo bye" containername
					- To update this use `docker compose run` before trying `docker compose up`
			- `docker-compose` entrypoint/command
				- `sleep infinity` is a common entrypoint if you want to ensure a container keeps running
				- If you also want to use `CMD` in Dockerfile/`command:` in docker-compose.yml then this will interfere
					- A Docker container runs exactly one command, and when that command is done, the container exits. If the container has no entrypoint, it's the command: from docker-compose.yml, any arguments after the image name in a docker run command, or the CMD from the Dockerfile. If it does have an entrypoint (entrypoint:, docker run --entrypoint ..., ENTRYPOINT), it's the entrypoint, which gets passed the command as arguments.
					- In short: if you pass an entrypoint or command in docker-compose.yml, it gets run instead of the server the container would normally run. There's no plain-Docker way to run a "hook" before or after the main process.
			- `docker-compose up`
				- `--build` = Ensures that images are always built before containers are launched (rather than using old images)
			- Docker volumes
			  collapsed:: true
				- The relative path is to where the docker-compose.yml exists, not the directory from which you're executing docker-compose up
				- They're mounted post Docker image creation, not before
					- This means you need to use an entrypoint script to run commands on a volume, rather than including it in a Dockerfile
					- `Dockerfile`
						- ```
						  COPY entrypoint.sh /app/entrypoint.sh
						  ENTRYPOINT ["/app/entrypoint.sh"]
						  ```
				- Debugging
					- If you're unsure what is actually mounted then in docker-compose.yml can set `volumes:` to be `./:/app/test1/`
						- `/app` because at the root of a Linux filesystem there's no directory already named `/app`
						- `./` = mounts the whole current directory from your filesystem
						- `/test1/` because it won't conflict with any other volumes or directories you've already created for your Docker container
				- For frontend projects you should use Docker volumes to bind your source code into the container instead of copying it once via Dockerfile, otherwise it won't live update when you make frontend changes
			- `docker-compose.yml`
				- `context: ..` in docker-compose.yml is useful for providing one directory up data to the container
				- [`command` is a Docker Compose v2 feature](https://github.com/docker/compose/blob/v1/docs/Compose%20file%20reference%20(legacy)/version-2.md#command)
			- In summary, to make docker compose up ignore the cache, you can use the following commands:
				- `docker compose build --no-cache` to build the services without using the cache.
				- `docker compose up --build --force-recreate` to start the services after building them without using the cache.
			- `command` section can be used to provide additional arguments to the `ENTRYPOINT` defined in a Dockerfile, linked from Docker Compose. This means you don't have to rebuild the container just to provide different arguments
			- Docker containers can access other containers on the same network via their container names. It acts like DNS like a domain name 
			  collapsed:: true
				- Can either use the container name e.g. `docker-openssh-1`
				- Or service name (i.e. in Docker Compose) e.g. `openssh`
					- Preferable because it gives a predictable DNS
			- If testing multiple containers on different networks in `docker-compose.yml` it can be useful to remove the `networks:` section for a container and replace it with `network_mode: host` for testing, so that the container acts like it's not sandboxed and is instead on the host OS for directly interacting with it
			  collapsed:: true
				- Likewise in Dev Containers you can use host networking via:
					- ```json
					  "runArgs": [
					  "--network=host",
					  ],
					  ```
			- When going from `docker-compose.yml` with some containers representing different machines, going from basic networking to more representative:
				- `network=host` initially and specify the port to be opened. This makes it seem like everything is running on same network
				- Close the ports, and instead create SSH tunnels or port forwarding or reverse tunnels between containers
				- Remove host networking, have different containres on different Docker networks. Have OpenSSH container with access to both Docker networks?
			- Docker Compose is a tool for composing Docker containers. That means defining your services (containers), setting up the network between them, sharing local directories with them, and a few more things.
			- Translate Docker Compose to Kubernetes
				- [Kompose](http://kompose.io/)
				  collapsed:: true
					- http://blog.kubernetes.io/2016/11/kompose-tool-go-from-docker-compose-to-kubernetes.html
			- `docker-compose.yml` construction
				- volumes:
					- Examples
						- _Uses host filesystem_
							- ```yml
							  ./data:/data
							  ./archivebox:/app/archivebox
							  #./archivy_data:/archivy/data  this mounts the ./archivy_data/ folder
							  #- archivy_config:/archivy/.local/share/archivy  this mounts the docker-managed archivy_config volume from the host's working directory into the container
							  elasticsearch_data:/usr/share/elasticsearch/data:rw  this mounts the docker-managed elasticsearch_data volume into the container and makes it writable
							  ```
							- e.g. `~/Documents/MUSEUM/Docker/ArchiveBox/Docker`
			- [Learning Resources]
				- [Overview | Docker Docs](https://docs.docker.com/compose/compose-file/)
		- Container Registries
		  id:: 654a4141-92a7-48f7-a12c-b9e250a398b7
		  collapsed:: true
			- Alternatives
				- [GitHub - psviderski/unregistry: Push docker images directly to remote servers without an external registry](https://github.com/psviderski/unregistry)
					- [Show HN: Unregistry – “docker push” directly to servers without a registry | Hacker News](https://news.ycombinator.com/item?id=44314085)
					-
			- ## Setup
				- ### Installing Docker
					- Set up Docker repo
						- `yum install -y yum-utils`
						- `yum-config-manager --add-repo [404 Not Found](https://download.docker.com/linux/centos/docker-ce.repo`)
					- Install Docker
						- `yum install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin`
					- Enable Docker
						- `systemctl enable docker`
					- Start Docker
						- `systemctl start docker`
					- Check Docker status
						- `systemctl status docker`
					- Verify Docker is installed correctly:
						- `docker run hub.docker.engineering.csu.local:12345/hello-world`
						- The prefix is because plain `docker run hello-world` will fail due to the corporate firewall, and needs the `csu.local` proxy
				- Configure the proxy for the corporate firewall
				  collapsed:: true
					- Create the new file `http-proxy.conf`
						- `sudo nano /etc/systemd/system/docker.service.d/http-proxy.conf`
						- ```
						  [Service]
						  Environment="http_proxy=http://10.129.49.21:8080/"
						  Environment="https_proxy=http://10.129.49.21:8080/"
						  Environment="no_proxy="localhost,127.0.0.0/8,::1,engineering,.local,.imp.net,.csu.local,cloudadfs.ai.baesystems.com"
						  Environment="NO_PROXY=localhost,127.0.0.0/8,::1,engineering,.local,.imp.net,.csu.local,cloudadfs.ai.baesystems.com"
						  ```
						- Source: [Engineering Desktop FAQs](https://engineering/confluence/display/ENGDESK/Engineering+Desktop+FAQs) - What proxy settings should I use?
				- Restart daemon and Docker
					- `sudo systemctl daemon-reload`
					- `sudo systemctl restart docker`
				- `docker run hello-world` should now work
			- ## Building and Uploading
				- `docker build -t <image-name> .`
				  Build the image
					- Example
						- `docker build -t nitro-nest1 .`
				- `cat ~/.aws/credentials`
				  Check the profile name for the corporate AWS account
				- `aws s3 ls --profile <profile-name>`
				  Test profile is working properly
					- Example
						- `aws s3 ls --profile corporate`
				- Login to Docker Private Registry (Elastic Container Registry)
					- `aws ecr get-login-password --region eu-west-1 --profile <profile-name> | docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com`
					- Example: `aws ecr get-login-password --region eu-west-1 --profile corporate | docker login --username AWS --password-stdin 935649231143.dkr.ecr.eu-west-1.amazonaws.com`
				- Tag the image:
					- Example: `docker tag nitro-nest1:latest 935649231143.dkr.ecr.eu-west-1.amazonaws.com/nitro-nest1:latest`
				- Push the image
					- Example: `docker push 935649231143.dkr.ecr.eu-west-1.amazonaws.com/nitro-nest1:latest`
			- ## Running
				- `docker images`
				  Find out the name (repository) of the image you just built
				- Run it
					- Example: `docker run -p 5000:5000 nitro-nest1`
				- Swagger now accessible at [http://127.0.0.1:5000/apidocs/](http://127.0.0.1:5000/apidocs/)
			- Related: ((65435c62-f1c9-4e99-ae95-612bde88fcc0)) : ((6543a9c6-44fa-47cf-91cc-5d3d873af37d))
		- `.dockerignore`
		  collapsed:: true
			- `.dockerignore` in root dir where you run `docker compose` from can be used to exclude files/directories from being utilised in your docker images
		- _Essential components_
		  collapsed:: true
			- Networking
				- Rancher
				  collapsed:: true
					- http://cdn.rancher.com/wp-content/uploads/2016/01/28101519/octoperf-docker-container-network-topology.png
					- Once you start thinking with a cluster, another issue comes up. How can containers communicate with each other? We needed cross-container networking. This network needs to be independent of the cluster layout.
					- Rancher has been incredibly helpful here. It has a built-in Docker container networking system based on IPSec tunneling. This allows you to have cross-host / cross-provider communication between Docker containers as if they were on the same local area network.
				- Some projects that are involved with improving Docker networking are:
				  collapsed:: true
					- The common ones are:
						- weave
						  collapsed:: true
						  Overlay network portraying all containers on a single network.
							- weave: Weave creates a virtual network that connects each host machine together. This simplifies application routing as it gives the appearance of every container being plugged into a single network switch.
						- flannel
						  collapsed:: true
						  flannel: Overlay network providing each host with a separate subnet.
							- Developed by the CoreOS team, this project was initially developed to provide each host system with its own subnet of a shared network. This is a condition necessary for Google's kubernetes orchestration tool to function, but it is useful in other situations.
					- In terms of advanced networking, the following project aims to fill that vacancy by providing additional plumbing:
						- pipework
						  collapsed:: true
						  Advanced networking toolkit for arbitrarily advanced networking configurations.
							- pipework: Constructed as a stop-gap measure until Docker native networking becomes more advanced, this project allows for easy configuration of arbitrarily advanced networking configurations.
					- One relevant example of existing software co-opted to add functionality to Docker is:
						- tinc: Tinc is a lightweight VPN software that is implemented using tunnels and encryption. Tinc is a robust solution that can make the private network transparent to any applications.
				- https://www.digitalocean.com/community/tutorials/the-docker-ecosystem-networking-and-communication
			- Service discovery
				- Rancher solution
				  collapsed:: true
					- http://cdn.rancher.com/wp-content/uploads/2016/01/28101647/octoperf-service-discovery.png
					- Well, now that your containers are able to run on a variety of hardware and communicate with each other, how can they discover each other without messing with the configuration on each deployment?
					- Rancher includes a global, DNS-based service discovery function that allows containers to automatically register themselves as services, as well as services to dynamically discover each other over the network.
					- Service discovery is an essential feature when running services that need to communicate with each other on a cluster of machines. Of course, you could hard-code the service IPs / hostnames, but that’s the opposite of flexibility and resilience. Services in a cluster are moving parts that should be independent of the location where they run.
				- Service Discovery and Global Configuration Stores
				  collapsed:: true
					- Service discovery is one component of an overall strategy aimed at making container deployments scalable and flexible. Service discovery is used so that containers can find out about the environment they have been introduced to without administrator intervention. They can find connection information for the components they must interact with, and they can register themselves so that other tools know that they are available. These tools also typically function as globally distributed configuration stores where arbitrary config settings can be set for the services operating in your infrastructure.
					- https://assets.digitalocean.com/articles/docker_ecosystem/Discover-Flow.png
					- In the above image, you can see an example flow in which one application registers its connection information with the discovery service system. Once registered, other applications can query the discovery service to find out how to connect to the application.
					- These tools are often implemented as simple key-value stores that are distributed among the hosts in a clustered environment. Generally, the key-value stores provide an HTTP API for accessing and setting values. Some include additional security measures like encrypted entries or access control mechanisms. The distributed stores are essential for managing the clustered Docker hosts in addition to their primary function of providing self-configuration details for new containers.
					- Some of the responsibilities of service discovery stores are:
					  collapsed:: true
						- Allowing applications to obtain the data needed to connect with to the services they depend on.
						- Allowing services to register their connection information for the above purpose.
						- Providing a globally accessible location to store arbitrary configuration data.
						- Storing information about cluster members as needed by any cluster management software.
					- Some popular service discovery tools and related projects are:
					  collapsed:: true
						- etcd: service discovery / globally distributed key-value store
						- consul: service discovery / globally distributed key-value store
						- zookeeper: service discovery / globally distributed key-value store
						- crypt: project to encrypt etcd entries
						- confd: watches key-value store for changes and triggers reconfiguration of services with new values
					- To learn more about service discovery with Docker, visit our guide here.
					  https://www.digitalocean.com/community/tutorials/the-docker-ecosystem-service-discovery-and-distributed-configuration-stores
				- Service Discovery and Distributed Configuration Stores
				  collapsed:: true
					- One of the core technologies that many Docker environments rely on is service discovery. Service discovery allows an application or component to discover information about their environment and neighbors. This is usually implemented as a distributed key-value store, which can also serve as a more general location to dictate configuration details. Configuring a service discovery tool allows you to separate your runtime configuration from the actual container, which allows you to reuse the same image in a number of environments.
					- The basic idea behind service discovery is that any new instance of an application should be able to programmatically identify the details of its current environment. This is required in order for the new instance to be able to "plug in" to the existing application environment without manual intervention. Service discovery tools are generally implemented as a globally accessible registry that stores information about the instances or services that are currently operating. Most of the time, in order to make this configuration fault tolerant and scalable, the registry is distributed among the available hosts in the infrastructure.
				- Tools
				  collapsed:: true
					- Some of the most common service discovery tools are:
					  collapsed:: true
						- etcd: This tool was created by the makers of CoreOS to provide service discovery and globally distributed configuration to both containers and the host systems themselves. It implements an http API and has a command line client available on each host machine.
						- consul: This service discovery platform has many advanced features that make it stand out including configurable health checks, ACL functionality, HAProxy configuration, etc.
						- zookeeper: This example is a bit older than the previous two, providing a more mature platform at the expense of some newer features.
					- Some other projects that expand basic service discovery are:
					  collapsed:: true
						- crypt: Crypt allows components to protect the information they write using public key encryption. The components that are meant to read the data can be given the decryption key. All other parties will be unable to read the data.
						- confd: Confd is a project aimed at allowing dynamic reconfiguration of arbitrary applications based on changes in the service discovery portal. The system involves a tool to watch relevant endpoints for changes, a templating system to build new configuration files based on the information gathered, and the ability to reload affected applications.
						- vulcand: Vulcand serves as a load balancer for groups of components. It is etcd aware and modifies its configuration based on changes detected in the store.
						- marathon: While marathon is mainly a scheduler (covered later), it also implements a basic ability to reload HAProxy when changes are made to the available services it should be balancing between.
						- frontrunner: This project hooks into marathon to provide a more robust solution for updating HAProxy.
						- synapse: This project introduces an embedded HAProxy instance that can route traffic to components.
						- nerve: Nerve is used in conjunction with synapse to provide health checks for individual component instances. If the component becomes unavailable, nerve updates synapse to bring the component out of rotation.
				- More info
				  https://www.digitalocean.com/community/tutorials/the-docker-ecosystem-service-discovery-and-distributed-configuration-stores
			- Scheduling, Cluster Management, and Orchestration
			  collapsed:: true
				- Schedulers are responsible for starting containers on the available hosts.
				- https://assets.digitalocean.com/articles/docker_ecosystem/Example-Schedule-App-F.png
				- Some popular projects that function as schedulers and fleet management tools are:
					- fleet: scheduler and cluster management tool.
					- marathon: scheduler and service management tool.
					  Framework for Mesos
						- https://www.digitalocean.com/community/tutorials/an-introduction-to-mesosphere#a-basic-overview-of-marathon
					- Swarm: scheduler and service management tool.
						- Docker Swarm is native clustering for Docker. It turns a pool of Docker hosts into a single, virtual host.
						- It supports scheduling, service reconciliation, load balancing, service discovery, built-in certificate rotation, etc.
					- mesos: host abstraction service that consolidates host resources for the scheduler.
					- kubernetes: advanced scheduler capable of managing container groups.
					- compose: container orchestration tool for creating container groups.
					- marathon: Marathon is the scheduling and service management component of a Mesosphere installation. It works with mesos to control long-running services and provides a web UI for process and container management.
					- Swarm: Docker's Swarm is a scheduler that the Docker project announced in December 2014. It hopes to provide a robust scheduler that can spin up containers on hosts provisioned with Docker, using Docker-native syntax.
					- As part of the cluster management strategy, Mesosphere configurations rely on the following component:
						- mesos: Apache mesos is a tool that abstracts and manages the resources of all hosts in a cluster. It presents a collection of the resources available throughout the entire cluster to the components built on top of it (like marathon). It describes itself as analogous to a "kernel" for a clustered configurations.
					- In terms of advanced scheduling and controlling groups of containers as a single unit, the following projects are available:
						- kubernetes: Google's advanced scheduler, kubernetes allows much more control over the containers running on your infrastructure. Containers can be labeled, grouped, and given their own subnet for communication.
						- compose: Docker's compose project was created to allow group management of containers using declarative configuration files. It uses Docker links to learn about the dependency relationship between containers.
		- ((6463499c-2c88-4c36-ac5b-8e43a34669a5))
		- Handling stateful/persistent data
		  collapsed:: true
			- _Related: [Containers should be ephemeral](https://workflowy.com/s/ES1H.xQziZjtg5y#/56a3abb606da)_
			- _Best solutions_
			  collapsed:: true
				- EBS via
					- REX-Ray
					  intralink2:: https://workflowy.com/s/ES1H.xQziZjtg5y#/7159137e6f24
				- Convoy-NFS + one server just for NFS + ZFS
				  intralink2:: https://workflowy.com/s/ES1H.xQziZjtg5y#/fa243cc3d2ef
				- Use a server
				-
			- Data volumes
			  collapsed:: true
			  http://i.imgur.com/7y7ais7.png
				- https://docs.docker.com/engine/tutorials/dockervolumes/#data-volumes
				- Since the directory on the host is created outside of Docker Engine’s context, it is available even after removing every container or even stopping Docker Engine. Since this shared mount point is fully outside the control of Docker Engine’s storage backend, it is not part of the layered, union filesystem approach.
					- This technique is the most popular one used by DevOps teams. Referred to as data volumes in Docker, it offers the following benefits:
						- Data volumes can be shared and reused across multiple containers.
						- Changes made to a data volume are made directly, bypassing the engine’s storage backend image layers implementation.
						- Changes applied to a data volume will not be included when the image gets updated.
						- Data volumes are available even if the container itself is deleted.
				- Cons
					- one major drawback with them — they make the containers non-portable. The data residing on the host will not move along with the container, which creates a tight bond between the host and container.
						- Solution is
							- shared filesystems
							  intralink2:: https://workflowy.com/#/8281ea60abe9 e.g.  Ceph, GlusterFS, Network File System (NFS)
							- or volume plugins (3rd party storage hosts)
							  intralink2:: https://workflowy.com/#/9be12f48c793
			- Distributed Filesystems
			  collapsed:: true
				- _Distributed Filesystems_
					- Network File System (NFS)
					  e.g. Rancher-NFS via Convoy
					- GlusterFS for stateful containers
						- https://github.com/gluster/gluster-containers
						- Use replicated volume sub-type
						  https://gluster.readthedocs.io/en/latest/Quick-Start-Guide/Architecture/#types-of-volumes
						- https://www.gluster.org/
						- https://www.digitalocean.com/community/tutorials/how-to-create-a-redundant-storage-pool-using-glusterfs-on-ubuntu-servers
						- http://www.cloudten.com.au/glusterfs-in-aws/
						- Interface
							- http://blog.gluster.org/2016/02/interfaces-for-gluster-management/
							- https://github.com/gluster/gdeploy
							- Ovirt
								- http://www.ovirt.org/download/
								- http://www.ovirt.org/develop/release-management/features/storage/glusterfs-storage-domain/
							- Red Hat Storage
							- https://github.com/oss2016summer/gluster-web-interface
						- Replication
							- https://gluster.readthedocs.io/en/latest/Administrator%20Guide/Geo%20Replication/
						- Gluster on ZFS
							- https://gluster.readthedocs.io/en/latest/Administrator%20Guide/Gluster%20On%20ZFS/
					- Ceph
					  id:: 663a578c-4e87-4711-873e-a573b457046a
					- Torus
					  https://github.com/coreos/torus
					- ObjectiveFS
					  S3-based NFS-like
						- https://objectivefs.com/
				- _Distributed Block Storage_
					- REX-Ray
					  https://github.com/codedellemc/rexray
						- https://rexray.readthedocs.io/en/stable/
					- Convoy Longhorn (alpha - developed to allow snapshot, remote backup, revert)
					  https://github.com/rancher/longhorn | Cloud-agnostic EBS
						- Longhorn is lightweight, reliable, and easy-to-use. It is particularly suitable as persistent storage for containers. It supports snapshots, backups, and even allows you to schedule recurring snapshots and backups!
						- http://rancher.com/microservices-block-storage/
						- Limitations
							- Longhorn is narrowly focused on distributed block storage. Distributed file storage, on the other hand, is much harder to build. Software systems like Ceph, Gluster, Infinit (acquired by Docker), Quobyte, Portworx, and StorageOS, as well as storage systems from NetApp, EMC, etc., offer distributed file systems, a unified storage experience, enterprise data management, and many other enterprise-grade features not supported by Longhorn.
							- Longhorn requires an NFS share or S3-compatible object storage to store volume backups. It therefore works with network file storage from NetApp, EMC Isilon, or other vendors, as well as S3-compatible object storage endpoints from AWS S3, Minio, SwiftStack, Cloudian, etc.
							- Longhorn lacks enterprise-grade storage features such as deduplication, compression, and auto-tiering as well as the ability to stripe a large volume into smaller chunks. As such, Longhorn volumes are limited by the size and performance of an individual disk. The iSCSI target runs as a user-level process.  It lacks the performance, reliability, and multi-path support of the enterprise-grade iSCSI systems we see in distributed block storage products such as Dell EqualLogic, SolidFire, and Datera.
					- OpenEBS
					  https://github.com/openebs/openebs | Forked from Longhorn
				- _Distributed object storage_
				- _Comparison_
				  http://rancher.com/block-object-file-storage-containers/
				- _Related: _Scaling Routes
				  #CreateAWebsite https://workflowy.com/#/db8bdced740b
				- 1 Backlink
					- _Related: _[Distributed file systems](https://workflowy.com/#/8281ea60abe9)
					  #Software
			- Volume plugins
			  collapsed:: true
			  3rd party hosts mostly
				- https://docs.docker.com/engine/extend/legacy_plugins/#volume-plugins
				- Cloudstor (by Docker; on ((63a06e59-4078-4357-b478-dda42326daf4)) + EBS)
				  https://docs.docker.com/docker-for-aws/persistent-data-volumes/#what-is-cloudstor
				- Rancher Convoy - multiple backends
				  https://github.com/rancher/convoy
					- Supported backends
						- Device Mapper
						- Virtual File System(VFS) / Network File System (NFS)
						- Amazon Elastic Block Store(EBS)
					- http://rancher.com/docs/rancher/v1.2/en/rancher-services/storage-service/
				- Ceph
				  https://github.com/contiv/volplugin
				- Flocker
				   | Flocker lets you move a container and its volume together between hosts
					- https://github.com/ClusterHQ/flocker
					- Supported storage options
						- AWS Elastic Block Storage (EBS)
						- Google Persistent Disk
						- OpenStack Cinder with any supported backend
						- EMC ScaleIO, XtremeIO, VMAX, VNX/Unity
						- VMware vSphere and vSAN
						- NetApp OnTap
						- Dell Storage SC Series
						- HPE 3PAR StoreServ and StoreVirtual (with OpenStack only)
						- Pure Storage
						- Huawei OceanStor
						- Hedvig
						- NexentaEdge
						- ConvergeIO
						- Saratoga Speed
						- Tintri
						- Ceph (Expiremental)
				- Azure File Storage
				- Google Compute Engine persistent disks
				  https://github.com/mcuadros/gce-docker
				- NetApp Storage
				- vSphere
				- Portworx
				  https://github.com/portworx/px-docs
				- Infinit
				- https://huaminchen.wordpress.com/2015/10/22/list-of-docker-volume-drives/
			- How to use git with Docker
			  collapsed:: true
				- https://ryanfb.github.io/etc/2015/07/29/git_strategies_for_docker.html
				- http://blog.cloud66.com/how-to-get-code-into-a-docker-container/
				- https://www.airpair.com/docker/posts/efficiant-development-workfow-using-git-submodules-and-docker-compose
				- https://forums.docker.com/t/best-practices-for-getting-code-into-a-container-git-clone-vs-copy-vs-data-container/4077/5
				- https://stackoverflow.com/questions/27529191/how-to-update-code-from-git-to-a-docker-container
			- Or just pull the latest image on production
		- Where is Docker data stored
		  collapsed:: true
			- Locate Docker root dir
			  collapsed:: true
				- `docker info`
					- Docker Root Dir: /var/lib/docker
				- Contains network settings, volumes, images
				- 1 Backlink
					- See [Locate Docker root dir](https://workflowy.com/#/404a0160017a)
			- Checking Docker disk usage
			  collapsed:: true
				- See [Locate Docker root dir](https://workflowy.com/#/404a0160017a)
				- sudo su root
				- cd /var/lib/docker
				  See [Docker Root Dir: /var/lib/docker](https://workflowy.com/#/7048c9c0e4e9)
				- ncdu
			- Bind mounts rather than volumes
			  collapsed:: true
				- See [Making Docker filesystem accessible from host filesystem](https://workflowy.com/#/a2f1f1eba0c7)
			- 1 Backlink
			  collapsed:: true
				- See [Where is Docker data stored](https://workflowy.com/#/8aca70b2ce5e)
				  #Infrastructure-Containers
		- `.dockerignore`
			- It only worked for me when I placed it in `dir1` when running `docker compose -f dir1/.docker/docker-compose.yml build`, where the Dockerfile being run for each service is also in `dir1/.docker/Dockerfile.service1`
			- Example: `**/.venv/` = ensures you can `COPY` an entire directory into a Docker container and it'll not copy in the ignored directory
		- Container configuration
			- [Host networking](https://docs.docker.com/engine/network/drivers/host/)
			  `--net=host`
				- a networking mode in which a Docker container shares its network namespace with the host machine. This means that the container uses the host's network stack directly, allowing the application inside the container to be accessed using a port at the host’s IP address (e.g., port 80)
	- ## Commands
		- Sorted by importance
			- `docker ps -a` = see all containers including stopped ones
			- `docker container prune` = delete all containers(?)
			- `docker system prune` = remove layer FS cache, orphaned images, containers, etc
			- `docker ps -a` (to obtain the container ID) + `docker stop <container-id>` + `docker container prune` is useful for removing a container, especially relevant for dev containers which are hard to restart otherwise(?)
			- `docker rmi <image-id>` + `docker system prune` = remove the images
		- _By function_
			- Start
			  collapsed:: true
				- Working with Docker is a pain if your user is not configured correctly, so add your user to the docker group with the following command.
				  sudo usermod -aG docker $(whoami)
					- Log out and log in from your server to activate your new groups.
			- _Informational_
			  collapsed:: true
				- To view all commands
				  docker
				- To view system-wide information about Docker
				  docker info
			- Working with containers
			  collapsed:: true
				- Check for containers
					- Check what containers are running
					  `docker ps`
					- show your group of Docker containers (both stopped and currently running)
					  `docker-compose ps`
					- To view all containers — active and inactive, pass it the -a switch
					  `docker ps -a`
					- To view the latest container you created, pass it the -l switch
					  `docker ps -l`
				- Stopping, starting etc
					- Run the image "Hello World" in a new container (and it will download from Docker Cloud if it doesn't exist)
					  docker run hello-world
					- Stopping a running or active container
					  `docker stop container-id` E.G. `docker stop 94df4f0ce8a4`
					- Destroy container
					  `docker rm`
					- Docker Compose
						- Note: it's no longer `docker-compose` but instead `docker compose` since ~2023
						- First cd to the directory with the docker-compose.yml
							- Run Docker Compose like a debugging shell (terminates containers when exited)
							  docker-compose up
								- Don't worry about the No HTTP secret provided message. It's normal.
								- Docker Compose will by default stay waiting for your input forever, so go ahead and hit CTRL-C to shut down your X container.
							- Run Docker Compose like a background service
							  docker-compose up -d
						- To show your group of Docker containers (both stopped and currently running), use the following command:
						  `docker-compose ps`
						- Stop all containers in Docker Compose group
						  `docker-compose stop`
						- Force stop all containers in Docker Compose group
						  `docker-compose kill`
						- In some cases, Docker containers will store their old information in an internal volume. If you want to start from scratch you can use the rm command to fully delete all the containers that make up your container group
						  `docker-compose rm`
						- `mkdir ~/docker-registry/nginx`
				- _Accessing the Docker Container Filesystem (shell)_
					- Start a shell inside the container 'e90e12f70418'
						- `docker exec -it fa3f879ff5c6 /bin/bash`
							- The -t option opens up a terminal, and the -i option makes it interactive. The /bin/bash options opens a bash shell to the running container. Be sure to use the ID for your container.
					- The combination of the -i and -t switches gives you interactive shell access into the container
					  `docker run -it ubuntu`
						- `docker run -t -i [YOUR-DOMAIN]/test-image /bin/bash`
					- Leave shell access
					  `exit`
					- update the package database inside the container
					  `apt-get update`
					- interactive SQL session
						- To start an interactive SQL session, run this command:
							- `docker exec -tiu USERNAME CONTAINERNAME psql`
								- `CONTAINERNAME` = container name
								- -i, --interactive[=false]      Keep STDIN open even if not attached
								- -t, --tty[=false]      Allocate a pseudo-TTY
								- -u, --user=""      Username or UID (format: [:])
								- `USERNAME` = username. We want to run the command as the postgres user because the docker exec command defaults to using the root user and the root user does not have access to the database.
						- To end the session, press Ctrl+D or type \q (backslash Q) and press enter.
					- See [Functional, simple - use `](https://workflowy.com/#/19f8004861a7)<a href="https://workflowy.com/#/19f8004861a7">docker</a><a href="https://workflowy.com/#/19f8004861a7"> </a><a href="https://workflowy.com/#/19f8004861a7">cp</a><a href="https://workflowy.com/#/19f8004861a7">` (</a><a href="https://workflowy.com/#/19f8004861a7">Docker</a><a href="https://workflowy.com/#/19f8004861a7"> copy)</a>
				- Making Docker filesystem accessible from host filesystem
					- Where to Store Data
						- Important note: There are several ways to store data used by applications that run in Docker containers. We encourage users of the postgres images to familiarize themselves with the options available, including:
						  collapsed:: true
							- Let Docker manage the storage of your database data by writing the database files to disk on the host system using its own internal volume management. This is the default and is easy and fairly transparent to the user. The downside is that the files may be hard to locate for tools and applications that run directly on the host system, i.e. outside containers.
							- Create a data directory on the host system (outside the container) and mount this to a directory visible from inside the container. This places the database files in a known location on the host system, and makes it easy for tools and applications on the host system to access the files. The downside is that the user needs to make sure that the directory exists, and that e.g. directory permissions and other security mechanisms on the host system are set up correctly.
					- Use either
						- Volumes
						  collapsed:: true
						  [https://docs.docker.com/storage/volumes/#use-a-volume-with-docker-compose](https://docs.docker.com/storage/volumes/#use-a-volume-with-docker-compose)
							- Cons
							  collapsed:: true
								- [docker cp (Docker copy)](https://workflowy.com/#/19f8004861a7) is the only method of exporting data for backups, and it doesn't intelligently delete old/deleted data like rsync would. Better off using Bind mounts
						- Bind mounts
						  collapsed:: true
						  [https://docs.docker.com/storage/bind-mounts/](https://docs.docker.com/storage/bind-mounts/)
							- Bind mounts have been around since the early days of Docker. Bind mounts have limited functionality compared to volumes. When you use a bind mount, a file or directory on the host machine is mounted into a container. The file or directory is referenced by its absolute path on the host machine. By contrast, when you use a volume, a new directory is created within Docker’s storage directory on the host machine, and Docker manages that directory’s contents.
						- Comparison
						  collapsed:: true
							- Bind mounts require editing the docker-compose to add a `./` which then stores that "volume" data on host filesystem in any directory desired. Docker volumes on the other hand are stored in `/var/lib/docker/volumes/` and you have to use the Docker API to interact with them e.g. backing them up
							  collapsed:: true
								- Example1
								  collapsed:: true
									- _Volume-version_
									  collapsed:: true
										- volumes:
										  collapsed:: true
											- db_data:/var/lib/mysql
									- _Bind mount-version_
									  collapsed:: true
										- volumes:
										  collapsed:: true
											- ./db_data:/var/lib/mysql
							- Note: sometimes these directories are created without view permissions for any user except the owner. This can be fixed:
							  collapsed:: true
								- `ls -l` to view the permissions
								- `sudo chmod -R u=rwx,og=rx newdirectory`
								  collapsed:: true
								  Give permissions for home user to access directory via Dolphin
									- `-R`
									  Recursively change all files and dirs in that directory
									- `u` = owner
									- `o` = other users
									- `g` = group
						- Volumes are stored in a part of the host filesystem which is managed by Docker (/var/lib/docker/volumes/ on Linux). Non-Docker processes should not modify this part of the filesystem. Volumes are the best way to persist data in Docker.
						- Bind mounts may be stored anywhere on the host system. They may even be important system files or directories. Non-Docker processes on the Docker host or a Docker container can modify them at any time.
					- Backing up volumes
						- `docker cp` (Docker copy)
							- Generic
							  docker cp [OPTIONS] CONTAINER_ID:SRC_PATH DEST_PATH|-
								- OR
								  docker cp [OPTIONS] SRC_PATH CONTAINER_ID:DEST_PATH|-
							- Examples
								- One specific file can be copied TO the container like:
								  docker cp foo.txt container_id:/foo.txt
									-
								- One specific file can be copied FROM the container like:
								  docker cp container_id:/foo.txt foo.txt
							- My version
								- `docker cp tinytinyrss_backups_1:/backups ~/Documents/MUSEUM/Docker/TinyTinyRSS/Exports/backups`
									- `docker cp tinytinyrss_backups_1:/var/www/html ~/Documents/MUSEUM/Docker/TinyTinyRSS/Exports/html`
								- `docker cp tinytinyrss_db_1:/var/lib/postgresql/data ~/Documents/MUSEUM/Docker/TinyTinyRSS/Exports/db`
						- See [Making db folder accessible by other users (so it can be backed up)](https://workflowy.com/#/f629705deb28)
							- Making db folder accessible by other users (so it can be backed up)
							  [mirrored]
						- Method 2
							- `docker volume ls`
								- tinytinyrss_db
								- tinytinyrss_backups
							- rsync the volume
								- Note: volume shouldn't be attached to a container when syncing
						- Method 1
							- `docker volume ls` t
							- `docker ps` to get the name for the container which holds the chosen data volume
							  collapsed:: true
								-
								- Example
								  `docker run --rm --volumes-from dbstore -v $(pwd):/backup ubuntu tar cvf /backup/backup.tar /dbdata`
									- Breakdown of command
										- `docker run` - starts a container. Need to mount a volume to a container in order to access it
										- `--rm` so that when you stop the dummy container it will get removed automatically (it's a temporary container)
										- `-v` to mount the volume into the file system of the container. Choose any path that doesn't conflict with something in ubuntu. e.g.: /root
										- `ubuntu` - one of the lightest weight containers
									- Launch a new container and mount the volume from the `dbstore` container
									- Mount a local host directory as `/backup`
									- Pass a command that tars the contents of the `dbdata` volume to a `backup.tar` file inside our `/backup` directory.
									- When the command completes and the container stops, we are left with a backup of our dbdata volume
									-
								- Generic
								  `docker run --rm --volumes-from <existing_container_with_data_volume> -v $(pwd):/backup ubuntu tar cvf /backup/backup.tar /<data_volume_name>`
									- `<data_volume_name> is <service_name>_<volume_name>`
										- eg
										  tinytinyrss_db
								- My version
									- Container
									  tinytinyrss_db_1
									- `docker run --rm --volumes-from tinytinyrss_backups_1 -v $(pwd):/backup ubuntu tar cvf /backup/db-backup.tar “cd /backups && tar cvf /tt-rss_db.tar`
									- `docker run --rm --volumes-from tinytinyrss_backups_1 -v $(pwd):/backups ubuntu tar cvf /backups/backup.tar /tinytinyrss_db`
									- `docker run --rm --volumes-from tinytinyrss_backups_1 -v $(pwd):/backup ubuntu tar cvf /backup/db-backup.tar “cd /backups && tar cvf /tt-rss_db.tar`
									- `docker run --rm --volumes-from tinytinyrss_db_1 -v $(pwd):/home/boss/Mount ubuntu tar cvf /home/boss/Mount/backup.tar /tinytinyrss_db`
									- `docker run --rm --volumes-from tinytinyrss_db_1 -v $(pwd):/home/boss/Documents/MUSEUM/Docker/TinyTinyRSS/Backups ubuntu tar cvf /home/boss/Documents/MUSEUM/Docker/TinyTinyRSS/Backups/backup.tar /db`
									- Functional
										- `cd ~/Documents/MUSEUM/Docker/TinyTinyRSS/Backups && docker run --rm --volumes-from tinytinyrss_db_1 -v $(pwd):/backup ubuntu tar cvf /backup/db-backup.tar “cd /var/lib/postgresql/data && tar cvf /tt-rss_db.tar`
									-
									-
				- Images
				  collapsed:: true
					- Commit the changes to a new Docker image instance
					  collapsed:: true
						- Commit on container d9b100f2f636
						  docker commit d9b100f2f636
						- The -m switch is for the commit message that helps you and others know what changes you made, while -a is used to specify the author. The container ID is the one you noted earlier in the tutorial when you started the interactive docker session. Unless you created additional repositories on Docker Hub, the repository is usually your Docker Hub username:
						- docker commit -m "What did you do to the image" -a "Author Name" container-id repository/new_image_name
						- For example:
							- docker commit -m "added node.js" -a "Sunday Ogwu-Chinuwa" d9b100f2f636 finid/ubuntu-nodejs
						- Note: When you commit an image, the new image is saved locally, that is, on your computer. Later in this tutorial, you'll learn how to push an image to a Docker registry like Docker Hub so that it may be assessed and used by you and others.
					- See the images that have been downloaded to your computer
					  docker images
						- Use the docker images command with the -a flag to locate the ID of the images you want to remove. This will show you every image, including intermediate image layers.
						  docker images -a
					- Push images to a repository
						- Docker Cloud
							- Login to Docker Cloud first
							  docker login -u docker-registry-username
							- Push "docker-image-name" to Docker Cloud'
							  `docker push docker-registry-username/docker-image-name`
						- Own repo
							- Login to domain
							  docker login https://YOUR-DOMAIN
							- Docker has an unusual mechanism for specifying which registry to push to. You have to tag an image with the private registry's location in order to push to it. Let's tag our image to our private registry:
							- docker tag test-image [YOUR-DOMAIN]/test-image
							- Note that you are using the local name of the image first, then the tag you want to add to it. The tag does not use https://, just the domain, port, and image name.
							- Now we can push that image to our registry. This time we're using the tag name only:
							- docker push [YOUR-DOMAIN]/test-image
					- Pull images
						- docker pull [YOUR-DOMAIN]/test-image
					- Delete image APP1
					  docker rmi APP1
			- _Docker Cloud/Hub_
			  collapsed:: true
				- Run the image "Hello World" in a new container (and it will download from Docker Cloud if it doesn't exist)
				  docker run hello-world
				- Search Docker Cloud for an image named "ubuntu"
				  docker search ubuntu
				- Download the "ubuntu" image from Docker Cloud
				  docker pull ubuntu
				- See the images that have been downloaded to your computer
				  docker images
		- _All commands_
			- Syntax: docker [option] [command] [arguments]
			- attach    Attach to a running container
			  collapsed:: true
				- build     Build an image from a Dockerfile
				- commit    Create a new image from a container's changes
				- cp        Copy files/folders between a container and the local filesystem
				- create    Create a new container
				- diff      Inspect changes on a container's filesystem
				- events    Get real time events from the server
				- exec      Run a command in a running container
				- export    Export a container's filesystem as a tar archive
				- history   Show the history of an image
				- images    List images
				- import    Import the contents from a tarball to create a filesystem image
				- info      Display system-wide information
				- inspect   Return low-level information on a container or image
				- kill      Kill a running container
				- load      Load an image from a tar archive or STDIN
				- login     Log in to a Docker registry
				- logout    Log out from a Docker registry
				- logs      Fetch the logs of a container
				- network   Manage Docker networks
				- pause     Pause all processes within a container
				- port      List port mappings or a specific mapping for the CONTAINER
				- ps        List containers
				- pull      Pull an image or a repository from a registry
				- push      Push an image or a repository to a registry
				- rename    Rename a container
				- restart   Restart a container
				- rm        Remove one or more containers
				- rmi       Remove one or more images
				- run       Run a command in a new container
				- save      Save one or more images to a tar archive
				- search    Search the Docker Hub for images
				- start     Start one or more stopped containers
				- stats     Display a live stream of container(s) resource usage statistics
				- stop      Stop a running container
				- tag       Tag an image into a repository
				- top       Display the running processes of a container
				- unpause   Unpause all processes within a container
				- update    Update configuration of one or more containers
				- version   Show the Docker version information
				- volume    Manage Docker volumes
				- wait      Block until a container stops, then print its exit code
			- `docker run`
			  collapsed:: true
				- Pass environment variables in the following format:
					- ```docker
					  -e AWS_ACCESS_KEY=${aws_secret_access_key} -e AWS_ACCESS_KEY_ID=${aws_secret_access_key_id}
					  ```
						- `AWS_ACCESS_KEY` = the key of the environment variable to pass in
						- `${aws_secret_access_key}` = the key-value of the environment variable on the host machine, which will be used as the value in the Docker container
	- ## SOPs
		- How to save Docker image to a TAR and later load it
		  collapsed:: true
			- From `docker build` command remove `--output` flag + add `--tag tagname`
			- From Dockerfile remove `FROM scratch`
			- After building then use `docker save -o tagname.tar tagname` to save Docker image as a TAR
			- `docker load -i tagname.tar` i.e. `--input`
			- `docker run --entrypoint sleep tagname infinity`
		- Deterministic Dockerised Gradle dependency puller
		  collapsed:: true
			- Usage
				- `docker build -f <dockerfile-path> --build-arg GRADLE_PROJECT_DIR=<value> --build-arg GRADLE_VERSION=<value> --build-arg JAVA_VERSION=<value> --build-arg ANDROID_SDK_CMDLINE_TOOLS_BUILD_ID=<value> --build-arg ANDROID_SDK_BUILD_TOOLS_VERSION=<value> --build-arg ANDROID_SDK_PLATFORM_VERSION=value --output=<output dir path> --progress=plain <project-path>`
				- GRADLE_VERSION and JAVA_VERSION can be obtained from https://hub.docker.com/_/gradle
				- ANDROID_SDK_CMDLINE_TOOLS_BUILD_ID can be obtained from https://developer.android.com/studio#command-line-tools-only
				- Example last command: `docker build -f Dockerfile.gradle --build-arg GRADLE_PROJECT_DIR=gnirehtet --build-arg GRADLE_VERSION=8.14 --build-arg JAVA_VERSION=24 --build-arg ANDROID_SDK_CMDLINE_TOOLS_BUILD_ID=13114758 --build-arg ANDROID_SDK_BUILD_TOOLS_VERSION=36.0.0 --build-arg ANDROID_SDK_PLATFORM_VERSION=android-35-ext15 --output=output --progress=plain .`
			- `Dockerfile.gradle`
			  collapsed:: true
				- ```dockerfile
				  ARG GRADLE_VERSION
				  ARG JAVA_VERSION
				  
				  FROM gradle:${GRADLE_VERSION}-jdk${JAVA_VERSION} AS build
				  ARG ANDROID_SDK_CMDLINE_TOOLS_BUILD_ID
				  ARG GRADLE_PROJECT_DIR
				  ARG HOME
				  ARG ANDROID_SDK_BUILD_TOOLS_VERSION
				  ARG ANDROID_SDK_PLATFORM_VERSION
				  
				  # Install Android SDK
				  ENV ANDROID_HOME=/opt/Android/Sdk
				  ENV ANDROID_USER_HOME=${HOME}/.android
				  RUN mkdir -p ${ANDROID_HOME}
				  WORKDIR ${ANDROID_HOME}
				  RUN wget https://dl.google.com/android/repository/commandlinetools-linux-${ANDROID_SDK_CMDLINE_TOOLS_BUILD_ID}_latest.zip
				  ARG ANDROID_SDK_CMDLINE_TOOLS=${ANDROID_HOME}/cmdline-tools/latest
				  RUN mkdir -p ${ANDROID_SDK_CMDLINE_TOOLS}
				  RUN unzip commandlinetools-linux-${ANDROID_SDK_CMDLINE_TOOLS_BUILD_ID}_latest.zip -d ${ANDROID_SDK_CMDLINE_TOOLS}
				  # Next line could be made generic e.g. `..`
				  RUN mv ${ANDROID_SDK_CMDLINE_TOOLS}/cmdline-tools/* ${ANDROID_SDK_CMDLINE_TOOLS}
				  RUN rmdir ${ANDROID_SDK_CMDLINE_TOOLS}/cmdline-tools
				  ENV PATH ${PATH}:${ANDROID_SDK_CMDLINE_TOOLS}/bin
				  RUN sdkmanager --list
				  RUN sdkmanager "build-tools;${ANDROID_SDK_BUILD_TOOLS_VERSION}"
				  RUN sdkmanager "platforms:${ANDROID_SDK_PLATFORM_VERSION}"
				  RUN yes | sdkmanager --licenses
				  
				  # Compile Gradle project
				  WORKDIR /deps
				  COPY ${GRADLE_PROJECT_DIR} .
				  RUN gradle :app:build :app:test
				  
				  RUN tar -czf .gradle.tar.gz \
				  --mtime='UTC 1970-01-01' \
				  --sort='name' \
				  --owner=0 \
				  --group=0 \
				  --mode=774 \
				  -c ~/.gradle/caches/modules-2/files-2.1 \
				  
				  RUN sha256sum .gradle/* | sort > .gradle.sha256
				  
				  FROM scratch
				  COPY --from=build /deps/.gradle.tar.gz /deps/.gradle.sha256 /
				  ```
		- Wipe all Docker images
		  collapsed:: true
			- `docker rmi $(docker images -q) -f && docker system prune`
			- You can then run `docker compose build` after this and it'll rebuild from cache still
		- docker-in-docker is a common approach, but technically it runs the docker containers side-by-side.
		- Checking IP address
		  collapsed:: true
			- `ping` package can be installed via `apt install iputils-ping` on Ubuntu 22.04. Can be used to check if a specific IP address is accessible. To check a Docker IP address use `docker inspect <container-name-or-id>`
			- List the IP addresses of all running Docker containers
				- `docker ps -q | xargs docker inspect --format '{{.Name}} - {{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}'`
	- ## Best practices
		- Containers should be ephemeral
		  collapsed:: true
			- https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/#containers-should-be-ephemeral
			- You should not have to go into containers to run a git checkout incase code is updated. But instead, you should store your code in your image, and re-build it if your code base changes (docker hub can automate building images if code in github or bitbucket is updated
			- Plus ephemeral containers makes it easy to scale your resources horizontally. If you need to deploy on multiple nodes, these nodes only need to pull and run the image and you're good to go without interacting with the containers.
			- During development of your application, you should mount your local source code directly into your container. This allows you to actively develop without having to re-build your image for every change you make.
			- Pros
			- Cons
			- 1 Backlink
				- _Related: [Containers should be ephemeral](https://workflowy.com/s/ES1H.xQziZjtg5y#/56a3abb606da)_
		- Use Dockerfiles > image commits
		  collapsed:: true
			- [source]
				- https://stackoverflow.com/questions/26110828/should-i-use-dockerfiles-or-image-commits
				- https://stackoverflow.com/questions/23735149/docker-image-vs-container
			- https://stackoverflow.com/questions/19104847/how-to-generate-a-dockerfile-from-an-image
			-
		- With Docker you are able to leverage the Wordpress container and just have your theme and plugins in version control.
		- [https://www.devpatch.com/2015/07/13/Wordpress-Docker-Github/](https://www.devpatch.com/2015/07/13/Wordpress-Docker-Github/)
		- [Executing the Docker Command Without Sudo (Optional)](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)
		  id:: 63a9ac98-d8f1-4006-a1fd-6001dd842c97
		  collapsed:: true
			- `sudo usermod -aG docker ${USER}`
			  Add your username to the `docker` group
			- `su - ${USER}`
			  To apply the new group membership, log out of the server and back in, or use the above command
				- Alternatively use `login ${USER}`
			- `groups`
			  See that your user can now see the `docker` group
	- ## Troubleshooting
		- `service docker start` = use if Docker daemon isn't running
		- `service docker status` = check if Docker service is running
		- `service docker restart` = restart Docker
		  id:: 6737677c-0b4c-4cab-8cd7-372a54b8cacc
		- If Docker daemon doesn't appear to be running try ((6737677c-0b4c-4cab-8cd7-372a54b8cacc))
- # Ecosystem
	- ## Management GUIs
		- Kitematic (official desktop app)
		  collapsed:: true
			- https://kitematic.com/
		- Portainer (web app)
		  collapsed:: true
			- [[Page not found · GitHub](https://github.com/portainer/portainer](https://github.com/portainer/portainer))
			- http://portainer.io/
			- You can install and start it with:
				- docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
				- The -v flag isn’t mentioned by default, but you will need it to manage any local Docker containers. After creating a password and selecting the Docker instance to manage, you’re up and running.
			- Screenshots
				- https://1npo9l3lml0zvr6w62acc3t1-wpengine.netdna-ssl.com/wp-content/uploads/2017/07/dgi-portainer-overview.jpg
				- https://1npo9l3lml0zvr6w62acc3t1-wpengine.netdna-ssl.com/wp-content/uploads/2017/07/dgi-portainer-stats.jpg
				- Console
				  https://1npo9l3lml0zvr6w62acc3t1-wpengine.netdna-ssl.com/wp-content/uploads/2017/07/dgi-portainer-console.jpg
			- How to persist Portainer container data
			  https://portainer.readthedocs.io/en/latest/deployment.html#persist-portainer-data
			- 1 Backlink
				- See [Portainer (web app)](https://workflowy.com/#/09a61f515d85)
		- _Cluster-oriented web apps_
		  collapsed:: true
			- Rancher
			- Kubernetes
			- Mesos
- Templates
	- Nginx on Docker
	  collapsed:: true
		- https://www.digitalocean.com/community/tutorials/docker-explained-how-to-containerize-and-use-nginx-as-a-proxy
	- Varnish
	  collapsed:: true
		- http://blog.benhall.me.uk/2015/01/scaling-wordpress-varnish-docker/
- [Learning Resources]
  collapsed:: true
	- https://www.digitalocean.com/community/tutorial-series/the-docker-ecosystem 5-part series
	- https://learn.cantrill.io/p/docker-fundamentals
	-
	- https://docs.docker.com/get-started/#prerequisites
	- https://docs.docker.com/docker-cloud/
	- https://github.com/veggiemonk/awesome-docker
	- https://github.com/haiiiiiyun/awesome-docker-cn
	- https://github.com/wsargent/docker-cheat-sheet
	- https://docs.docker.com/
	- https://ejosh.co/de/2015/08/wordpress-and-docker-the-correct-way/
	- Dockerfiles
		- [Docker Explained: Using Dockerfiles to Automate Building of Images | DigitalOcean](https://www.digitalocean.com/community/tutorials/docker-explained-using-dockerfiles-to-automate-building-of-images)
	- Edit my configuration?
		- You can either enter your container and edit the config, mount the config file in a volume, or change your configuration and rebuild the container. I have found using a volume great for making many major configuration changes.
	- ZFS
		- https://docs.docker.com/engine/userguide/storagedriver/zfs-driver/
- {Archive}
  collapsed:: true
	- https://www.digitalocean.com/community/tutorial_series/the-docker-ecosystem
	- https://www.digitalocean.com/community/tags/docker?type=tutorials
- Related:
	- ((68022cfa-1c35-40a5-866a-c010d77b700c))
	- ((6463499c-d91d-42c9-b035-93b6bc153e41))