#docker compose is using to run multiple container using docker image
#so first we write a dockerfile
FROM httpd
COPY . /usr/local/apache2/htdocs
#like this
#after create index.html file
<h1>this is apache page updated code</h1>>
#like this
#then create a image using dockerfile
docker build -t apache:1 .
docker build -t apache:2 .
docker build -t apache:3 .
#after use docker-compose to run multiple containers
#so we create a docker-compose yaml file
compose.yaml
#like this
#creating compose yaml file after give the related of image
version: '3'
services: 
  web:
    image: apache:1
    ports: 
      - "80"
  app:
    image: apache:2
    ports: 
      - "80"
  web1:
    image: apache:3
    ports:
      - "80"
#like this
#then run the docker-compose to creating containers command
docker-compose -f compose.yaml up -d
#the containers will be created
