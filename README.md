# Docker_simple_projects

Inside redis-image, to run a container that host a redis server, run :
docker build -t yourdockerid/nameofproject:latest . (gives a tag to your docker container when building it)
knowing :latest is optional, by default the latest is taken

it gives something like :
docker build -t odelalande/redis .

Inside simpleweb run :
docker build -t odelalande/simpleweb .

and then :
docker run -p 8080:8080 odelalande/simpleweb

first command builds your containers giving a tagname for it. Second command runs your container mapping ports so that your node
container knows on what port of container redirect calls, so when reaching localhost:8080 you see a page displayed, because a 
redirect to the port 8080 of the container is made, if this mapping isn't done you can't reach the node server hosted
in your container and can't see anything when reaching the web.

Inside visits run :

docker-compose up --build

This time the mapping is made with a docker-compose file, when reaching localhost:4001, you're in fact reaching port 8080
of your node container. In your index.js you have a client created so that your node and redis container can talk to each
other
