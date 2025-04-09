CONTAINER=some-timescaledb
IMAGE=timescale/timescaledb-ha:pg17

# https://hub.docker.com/r/timescale/timescaledb
# https://docs.timescale.com/self-hosted/latest/install/installation-docker/

pull:
	docker pull ${IMAGE}

start:
	docker run \
	    -p 5432:5432 \
		-e POSTGRES_PASSWORD=password \
	    -d \
		--name ${CONTAINER} \
		${IMAGE}

stop:
	docker stop ${CONTAINER}
	docker rm ${CONTAINER}

shell:
	docker exec -it ${CONTAINER} bash

cli:
	docker exec -it ${CONTAINER} psql
