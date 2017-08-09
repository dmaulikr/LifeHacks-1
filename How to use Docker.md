# How to use Docker 🐳

*just some notes. this might get omitted later*

### General Information

* Docker is similar to Heroku.
* Can be used as an ingredient on an existing plattform. 
* Docker is a static binary, you run it as a demon, you can use a client to give commands to it
* Docker has a processed oriented API
 
### Run a Docker Image 

**1.** docker images ubuntu // gives you all images with ubuntu in it's name
**2.** docker run -i -t ubuntu:12.10 /bin/bash  //creates a container for this image. **-i** is for input availability

### Some Notes

* You're not only forking the process but also forking the file-system.
* It's easy to throw away a setup and start a new one. *(alternative to a VM)*
* Go to [index.docker.io](index.docker.io) to see containers pushed to the public docker db. 
* A push uses the same versioning aka copy-and-write-mechanism as github uses. 

Wikipedia: [Docker](https://en.wikipedia.org/wiki/Docker_(software))

**Credits:** Notes were taken from this YouTube video here: [Link](https://www.youtube.com/watch?v=Q5POuMHxW-0)
