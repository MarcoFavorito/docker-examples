	
	docker build -t friendlyhello .
	docker images
	docker run -p 4000:80 friendlyhello
	
	# call from the port exposed
	curl http://localhost:4000	
	
	# in background
	docker run -d -p 4000:80 friendlyhello
	

	# tag the image
	# docker tag image username/repository:tag
	docker tag friendlyhello marcofavorito/docker-examples:master

	docker images ls	
