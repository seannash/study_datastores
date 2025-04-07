CONTAINER=some-scylla
IMAGE=scylladb/scylla

pull:
	docker pull ${IMAGE}

start:
	docker run --name ${CONTAINER} --hostname $CONTAINER -d ${IMAGE}

stop:
	docker stop ${CONTAINER}
	docker rm ${CONTAINER}

cli:
	docker exec -it ${CONTAINER} cqlsh

shell:
	docker exec -it ${CONTAINER} bash