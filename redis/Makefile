CONTAINER=some-redis
IMAGE=redis

pull:
	docker pull ${IMAGE}

start:
	docker run --name ${CONTAINER} -p 6379:6370 --hostname $CONTAINER -d ${IMAGE}

stop:
	docker stop ${CONTAINER}
	docker rm ${CONTAINER}

local-cli:
	redis-cli

cli:
	docker exec -it ${CONTAINER} redis-cli

shell:
	docker exec -it ${CONTAINER} bash