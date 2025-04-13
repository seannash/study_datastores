CONTAINER=some-postgres
IMAGE=postgres
NETWORK=some-network
CONTAINER_WEB=pgadmin-container
IMAGE_WEB=dpage/pgadmin4

WORK_DIR ?= .

pull:
	docker pull ${IMAGE}
	docker pull ${IMAGE_WEB}

start:
	docker run --name ${CONTAINER} \
	           --hostname ${CONTAINER} \
			   --mount type=bind,src=${WORK_DIR},dst=/work \
			   -p 5432:5432 \
			   -e POSTGRES_USER=root \
			   -e POSTGRES_PASSWORD=mysecretpassword \
			   -d \
			   ${IMAGE}

stop:
	docker stop ${CONTAINER}
	docker rm ${CONTAINER}

shell:
	docker exec -it ${CONTAINER} bash

cli:
	docker exec -it ${CONTAINER} psql

start-web:
	docker run \
        --name ${CONTAINER_WEB} \
		-p 5050:80 \
		--mount source=pg_vol,target=/var/lib/postgresql/data \
		-e PGADMIN_DEFAULT_EMAIL=user@domain.com \
		-e PGADMIN_DEFAULT_PASSWORD=zook \
		-d dpage/pgadmin4
	echo http://localhost:5050/login?next=/browser/

stop-web:
	docker stop ${CONTAINER_WEB}
	docker rm ${CONTAINER_WEB}
