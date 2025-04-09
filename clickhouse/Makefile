CONTAINER=some-clickhouse
IMAGE=clickhouse/clickhouse-server

# https://hub.docker.com/r/clickhouse/clickhouse-server/

pull:
	docker pull ${IMAGE}

start:
	docker run \
	    -d \
		--name ${CONTAINER} \
		--ulimit nofile=262144:262144 \
		${IMAGE}


stop:
	docker stop ${CONTAINER}
	docker rm ${CONTAINER}

shell:
	docker exec -it ${CONTAINER} bash

cli:
	docker exec -it ${CONTAINER} clickhouse-client
