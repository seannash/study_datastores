CONTAINER=some-postgres
IMAGE=postgres
NETWORK=some-network

pull:
	docker pull ${IMAGE}

start:
	docker run --name ${CONTAINER} \
	           --hostname ${CONTAINER} \
			   -p 5432:5432 \
			   -e POSTGRES_USER=postgres \
			   -e POSTGRES_PASSWORD=mysecretpassword \
			   -d \
			   ${IMAGE}

stop:
	docker stop ${CONTAINER}
	docker rm ${CONTAINER}

cli:
	docker exec -it some-postgres psql -h 127.0.0.1 -p 5432 -U postgres

local-cli:
	PGPASSWORD=mysecretpassword psql -U postgres -h 127.0.0.1 -p 5432

shell:
	docker exec -it ${CONTAINER} bash