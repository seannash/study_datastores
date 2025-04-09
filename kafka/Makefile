CONTAINER=some-kafka
IMAGE=apache/kafka:latest

pull:
	docker pull ${IMAGE}

start:
	docker run --name ${CONTAINER} -p 9092:9092 --hostname ${CONTAINER} -d ${IMAGE}

stop:
	docker stop ${CONTAINER}
	docker rm ${CONTAINER}

shell:
	docker exec --workdir /opt/kafka/bin/ -it ${CONTAINER} sh