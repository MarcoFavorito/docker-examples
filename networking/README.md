https://docs.docker.com/engine/tutorials/networkingcontainers/#launch-a-container-on-the-default-network

	docker network ls

	docker run -itd --name=networktest ubuntu
	docker network inspect bridge
	docker network disconnect bridge networktest

	#-d bridge: use the bridge driver
	docker network create -d bridge my_bridge
	
	#setup the network 
	docker run -d --net=my_bridge --name db training/postgres
	docker inspect --format='{{json .NetworkSettings.Networks}}'  db | json_pp

	docker run -d --name web training/webapp python app.py
	docker inspect --format='{{json .NetworkSettings.Networks}}'  web | json_pp

	#only IP addr
	docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' web

	sudo docker exec -it db bash
	# ping 172.17.0.2 ... not working
	
	docker network connect my_bridge web
	# ping 172.19.0.2 # working (take the ip through inspect)
	# ping web 	  # ... or by container name
