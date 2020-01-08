# docker101
basic docker commands

### ps - list containers
<pre>docker ps
docker ps -a</pre>

### Run - PORT mapping
<pre>docker run -d nginx
docker run -p 8080:80 -d nginx -> host port 8080; container port 80</pre>

### Run - Volume mapping
<pre>docker run -v /home/vagrant/nginx:/usr/share/nginx/html:ro -p 8080:80 -d nginx -> map "/home/vagrant/nginx" with container "/usr/share/nginx/html" folder
docker run --mount type=bind,source=/home/vagrant/nginx,target=/usr/share/nginx/html -p 8080:80 -d nginx </pre>

### Inspect container
<pre>docker inspect confident_ellis</pre>

### Logs container
<pre>docker logs confident_ellis</pre>

### Build container
<pre>docker build Dockerfile -t fakrul/my-custom-container
docker push fakrul/my-custom-container
docker hisotry my-custom-container</pre>

### Docker Networking
<pre>docker run nginx --network=host

docker network create \
--driver bridge \
--subnet 182.18.0.0/16 
custom-isolated-network

docker network ls</pre>

### Docker CPU and Memory
<pre>docker run --cpus=.5 nginx -> .5 is 50% cpu
docker run --memory=1024m nginx</pre>
