CONTAINER=some-cockroachdb
IMAGE=cockroachdb/cockroach:latest
NETWORK=some-network

WORK_DIR ?= .

pull:
	docker pull ${IMAGE}

start:
	docker run \
		-d \
		--name ${CONTAINER} \
		--hostname ${CONTAINER} \
		-p 26257:26257 \
		-p 8080:8080 \
		${IMAGE} \
		start-single-node --insecure

stop:
	docker stop ${CONTAINER}
	docker rm ${CONTAINER}

shell:
	docker exec -it ${CONTAINER} bash

cli:
	docker exec -it ${CONTAINER} ./cockroach sql --insecure
