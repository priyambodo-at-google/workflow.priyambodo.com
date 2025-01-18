# Running this in Virtual Machine using npm

sudo apt install nodejs npm

https://docs.n8n.io/hosting/installation/npm/

npm install n8n -g

n8n start

npm update -g n8n

n8n start --tunnel


# Running this in Google Kubernetes Engine

https://docs.n8n.io/hosting/installation/server-setups/google-cloud/#hosting-options


# Running this in Virtual Machine as Docker

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

#======================================================================

docker run -it --rm \
 --name n8n \
 -p 5678:5678 \
 -v n8n_data:/home/node/.n8n \
 docker.n8n.io/n8nio/n8n \
 start --tunnel
 
https://fzy1lnbattbeigng6dtfblye.hooks.n8n.cloud/

#======================================================================

# Create Reverse Proxy from port 80 or 443 to 5678

sudo apt update

sudo apt install nginx

sudo systemctl status nginx 

sudo systemctl start nginx

sudo systemctl enable nginx

sudo nano /etc/nginx/nginx.conf

server {
    listen 80;
    server_name your-domain.com;

    location / {
        proxy_pass http://localhost:5678; 
    }
}

server {
    listen 443 ssl;
    server_name your-domain.com;
    ssl_certificate /path/to/your/certificate.crt;
    ssl_certificate_key /path/to/your/key.key;

    location / {
        proxy_pass http://localhost:5678; 
    }
}


sudo systemctl restart nginx


