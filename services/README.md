https://docs.docker.com/get-started/part3/#run-your-new-load-balanced-app

This docker-compose.yml file tells Docker to do the following:

    - Pull the image we uploaded in step 2 from the registry.

    - Run 5 instances of that image as a service called web, limiting each one to use, at most, 10% of the CPU (across all cores), and 50MB of RAM.

    - Immediately restart containers if one fails.

    - Map port 80 on the host to web’s port 80.

    - Instruct web’s containers to share port 80 via a load-balanced network called webnet. (Internally, the containers themselves publish to web’s port 80 at an ephemeral port.)

    - Define the webnet network with the default settings (which is a load-balanced overlay network).


	docker swarm init

	docker stack deploy -c docker-compose.yml getstartedlab
	
	docker service ls
	docker service ps getstartedlab_web
	docker container ls -q

	docker stack deploy -c docker-compose.yml getstartedlab

	docker stack rm getstartedlab
	docker swarm leave --force
