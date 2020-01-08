# docker101
basic docker commands

### ps - list containers
docker ps
docker ps -a

### Run - PORT mapping
docker run -d nginx
docker run -p 8080:80 -d nginx \\host port 8080; container port 80

### Run - Volume mapping
docker run -v /home/vagrant/nginx:/usr/share/nginx/html:ro -p 8080:80 -d nginx -> map "/home/vagrant/nginx" with container "/usr/share/nginx/html" foler
docker run --mount type=bind,source=/home/vagrant/nginx,target=/usr/share/nginx/html -p 8080:80 -d nginx 

### Inspect container
docker inspect confident_ellis

### Logs container
docker logs confident_ellis

### Build container
docker build Dockerfile -t fakrul/my-custom-container
docker push fakrul/my-custom-container
docker hisotry my-custom-container

### Docker Networking
docker run nginx --network=host

docker network create \
--driver bridge \
--subnet 182.18.0.0/16 
custom-isolated-network

docker network ls

### Docker CPU and Memory
docker run --cpus=.5 nginx -> .5 is 50% cpu
docker run --memory=1024m nginx
