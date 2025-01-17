sudo apt-get update

sudo apt-get install docker.io docker-compose

docker-compose --version

sudo docker run hello-world

docker volume create n8n_data

docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n

You can then access n8n by opening: http://localhost:5678

docker ps -a

docker stop [container_id]

docker rm [container_id]

docker run --name=[container_name] [options] -d docker.n8n.io/n8nio/n8n


Docker Compose#
If you run n8n using a Docker Compose file, follow these steps to update n8n:

# Pull latest version
docker compose pull

# Stop and remove older version
docker compose down

# Start the container
docker compose up -d
