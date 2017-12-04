# Docker with Apache Ubuntu PHP

commands:

		docker build -t my-apache-php .
		docker run -d -p 80:80 -v /data/server/app:/var/www/site/app --name app app
		docker exec -it app bash
		docker stop app
		docker rm app
		docker run -d -p 80:80 -v /data/server/app:/var/www/site/app -v /data/server/log:/var/log/apache2 --name app app 
