# Docker examples

This repo is a collection of Docker examples, typical use cases and Dockerfile.

## similar repos

- [dockerfile-examples](https://github.com/kstaken/dockerfile-examples)
- [docker-curriculum](https://github.com/prakhar1989/docker-curriculum)
- [docker-labs](https://github.com/docker/labs)

## other links

- [docker guides](https://docs.docker.com/get-started/)
- [docker samples](https://docs.docker.com/samples/)

## command examples

	docker run hello-world
	
	docker pull alpine
	docker images

	docker run alpine ls -l
	docker run alpine echo "hello from alpine"

	docker run alpine /bin/sh #does not work
	docker run -it alpine /bin/sh #-t pseudo-TTY; -i keep stdin open
	
	docker images
	docker ps -a
	
	docker stop 
	docker rm
	docker rm -f
	sudo docker rm -f $(sudo docker ps -q)
	
	
	# -d will create a container with the process detached from our terminal
	# -P will publish all the exposed container ports to random ports on the Docker host
	# -e is how you pass environment variables to the container
	# --name allows you to specify a container name
	# AUTHOR is the environment variable name and Your Name is the value that you can pass
	docker run --name static-site -e AUTHOR="Your Name" -d -P dockersamples/static-site
	
	docker port static-site
	
	docker run --name static-site-2 -e AUTHOR="Your Name" -d -p 8888:80 dockersamples/static-site


	# in a folder where there is a Dockerfile
	docker build -t <YOUR_USERNAME>/myfirstapp .
	docker run -p 8888:5000 --name myfirstapp YOUR_USERNAME/myfirstapp
	
	# to push to Docker Cloud account
	docker login
	docker tag image username/repository:tag
	docker push YOUR_USERNAME/myfirstapp
	
	
	#misc	
	docker exec -it <container-name> bash

	
