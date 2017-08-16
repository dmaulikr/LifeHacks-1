# How to use Docker 🐳

*just some notes. this might get omitted later*

## Notes from Docker.com

### Container

Containers are a way to package software in a format that can run isolated on a shared operating system. Unlike VMs, containers do not bundle a full operating system - only libraries and settings required to make the software work are needed. This makes for efficient, lightweight, self-contained systems and guarantees that software will always run the same, regardless of where it’s deployed.

### Docker For Developers

Docker automates the repetitive tasks of setting up and configuring development environments so that developers can focus on what matters: building great software.

![Docker Image][Docking]

[Docking]: https://www.docker.com/sites/default/files/group_5622_0.png

Developers using Docker don’t have to install and configure complex databases nor worry about switching between incompatible language toolchain versions. When an app is dockerized, that complexity is pushed into containers that are easily built, shared and run. Onboarding a co-worker to a new codebase no longer means hours spent installing software and explaining setup procedures. Code that ships with Dockerfiles is simpler to work on: Dependencies are pulled as neatly packaged Docker images and anyone with Docker and an editor installed can build and debug the app in minutes.

**ANY APP, LANGUAGE, OR STACK**

Build, test, debug and deploy Linux and Windows Server container apps written in any programming language without risk of incompatibilities or version conflicts.

**AWESOME DEVELOPER EXPERIENCE**

Reduce onboarding time by 65%: Quickly build, test and run complex multi-container apps and stop wasting time installing and maintaining software on servers and developer machines. All dependencies run in containers, eliminating “works on my machine” problems.

**BUILT-IN CONTAINER ORCHESTRATION**

Docker comes with built-in swarm clustering that’s easy to configure. Test and debug apps in environments that mimic production with minimal setup.

### One Journey, All Apps

Modernize applications without disruption. From developers to IT, Windows and Linux, x86 and mainframe, on-premises to cloud, Docker is the unifying platform to modernize all apps from commercial off the shelf, homegrown traditional and microservices. With Docker, organizations can modernize applications, infrastructure and operational models by bringing forward existing IT investments while integrating new technology at the rate of business.

![Docker Image][docker flow]

[docker flow]: https://www.docker.com/sites/default/files/app_modernization.png

### A brief explanation of containers

An **image** is a lightweight, stand-alone, executable package that includes everything needed to run a piece of software, including the code, a runtime, libraries, environment variables, and config files.

A **container** is a runtime instance of an image—what the image becomes in memory when actually executed. It runs completely isolated from the host environment by default, only accessing host files and ports if configured to do so.

Containers run apps natively on the host machine’s kernel. They have better performance characteristics than virtual machines that only get virtual access to host resources through a hypervisor. Containers can get native access, each one running in a discrete process, taking no more memory than any other executable.

### General Information

* Docker is similar to Heroku.
* Can be used as an ingredient on an existing plattform. 
* Docker is a static binary, you run it as a demon, you can use a client to give commands to it
* Docker has a processed oriented API
 
### Run a Docker Image 

**1.** docker images ubuntu // gives you all images with ubuntu in it's name

**2.** docker run -i -t ubuntu:12.10 /bin/bash  //creates a container for this image. **-i** is for input availability

### Some Notes from Twitter University

* You're not only forking the process but also forking the file-system.
* It's easy to throw away a setup and start a new one. *(alternative to a VM)*
* Go to [index.docker.io](index.docker.io) to see containers pushed to the public docker db. 
* A push uses the same versioning aka copy-and-write-mechanism as github uses. 

Wikipedia: [Docker](https://en.wikipedia.org/wiki/Docker_(software))

### Links

Introduction to Docker by Twitter University: [Link](https://www.youtube.com/watch?v=Q5POuMHxW-0)

[Docker: Get started](https://docs.docker.com/get-started/)
