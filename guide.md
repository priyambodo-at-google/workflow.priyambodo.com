
https://docs.n8n.io/hosting/installation/docker/

docker volume create n8n_data
docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n

To use n8n with Postgres, provide the corresponding:

docker volume create n8n_data
docker run -it --rm \
 --name n8n \
 -p 5678:5678 \
 -e DB_TYPE=postgresdb \
 -e DB_POSTGRESDB_DATABASE=<POSTGRES_DATABASE> \
 -e DB_POSTGRESDB_HOST=<POSTGRES_HOST> \
 -e DB_POSTGRESDB_PORT=<POSTGRES_PORT> \
 -e DB_POSTGRESDB_USER=<POSTGRES_USER> \
 -e DB_POSTGRESDB_SCHEMA=<POSTGRES_SCHEMA> \
 -e DB_POSTGRESDB_PASSWORD=<POSTGRES_PASSWORD> \
 -v n8n_data:/home/node/.n8n \
 docker.n8n.io/n8nio/n8n

docker volume create n8n_data
docker run -it --rm \
 --name n8n \
 -p 5678:5678 \
 -e GENERIC_TIMEZONE="Europe/Berlin" \
 -e TZ="Europe/Berlin" \
 -v n8n_data:/home/node/.n8n \
 docker.n8n.io/n8nio/n8n


--------------------------

# Pull latest (stable) version
docker pull docker.n8n.io/n8nio/n8n

# Pull specific version
docker pull docker.n8n.io/n8nio/n8n:0.220.1

# Pull next (unstable) version
docker pull docker.n8n.io/n8nio/n8n:next

----------------------------

# Get the container ID
docker ps -a

# Stop the container with ID container_id
docker stop [container_id]

# Remove the container with ID container_id
docker rm [container_id]

# Start the container
docker run --name=[container_name] [options] -d docker.n8n.io/n8nio/n8n

------------------------------

# Pull latest version
docker compose pull

# Stop and remove older version
docker compose down

# Start the container
docker compose up -d

-------------------------------

docker volume create n8n_data

docker run -it --rm \
 --name n8n \
 -p 5678:5678 \
 -v n8n_data:/home/node/.n8n \
 docker.n8n.io/n8nio/n8n \
 start --tunnel

------------------------------

