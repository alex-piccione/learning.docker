# learning.docker
Personal study of Docker


## Courses

Pluralsight [Docker fundamentals for developer](https://app.pluralsight.com/paths/skill/docker-fundamentals-for-developers): [_____]


## Build an image

``docker image build`` or ``docker build``  
**By default the docker build command will look for a Dockerfile at the root of the build context. **  
use _-f <dockerfile>_ to specify a different Dockerfile

_docker image build -t {name}:{tag}_ {Dockerfile path
_docker image build -t {user_id/repository}:{image}_ {Dockerfile path}

``
# from webapp folder
docker image build -t alessandropiccione/test-webapp:3.1 .
docker image build -t alessandropiccione/test-webapp:latest .
# from root folder
docker image build -t alessandropiccione/test-webapp:3.1 ./webapp
``

## Publish an image
``docker image push {image:tag}``

``
docker image push alessandropiccione/test-webapp:3.1
docker image push alessandropiccione/test-webapp:latest

docker image push portfolio-app:latest
``

## Delete an image 
``docker image rm {image_name}``
``docker image rm {image_id}``

## Run a container
``docker container run``
- -d = run in the background (detached)
- --name {name}
- -p {local host}:{container host} port mapping

``
docker container run -d --name test_web -p 8006:8005 alessandropiccione/test-webapp:3
``

dockerhub is the default if we don't pass a URL registry. 

### Pass variables to the container
``--env``, ``--env-file``
--env-file=<file> works well with _.env_ files

## List containers
docker container ls -a

## Delete a container 
``docker container stop {container_id|container_name}`` to stop it
``docker container rm {container_id|container_name}``