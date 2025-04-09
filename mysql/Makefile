CONTAINER=some-mysql
IMAGE=mysql

# https://hub.docker.com/_/mysql

pull:
	docker pull ${IMAGE}

start:
	docker run \
	    -d \
		--name ${CONTAINER} \
		-e MYSQL_ROOT_PASSWORD=pass \
		${IMAGE}

stop:
	docker stop ${CONTAINER}
	docker rm ${CONTAINER}

shell:
	docker exec -it ${CONTAINER} bash

cli:
	docker exec -it ${CONTAINER} mysql -ppass
