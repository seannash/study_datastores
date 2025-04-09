CONTAINER=some-mongo
IMAGE=mongo

# https://hub.docker.com/_/mysql

pull:
	docker pull ${IMAGE}

start:
	docker run \
	    -d \
		--name ${CONTAINER} \
		${IMAGE}

stop:
	docker stop ${CONTAINER}
	docker rm ${CONTAINER}

shell:
	docker exec -it ${CONTAINER} bash

cli:
	docker exec -it ${CONTAINER} mongosh
