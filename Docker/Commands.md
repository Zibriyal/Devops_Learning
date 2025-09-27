## Images Commands

docker images

docker image ls

docker pull <image-name>

docker rmi <image-id>

docker build 


## Container Commands

docker ps     (list all running container)

docker ps -a  (list all running/stooped containers)

docker ps -aq  (List only ID)

docker rm <cont-id>

docker rm -f $(docker ps -aq)

docker run

	docker run -it <image-name> /bin/bash
 
	docker exec -it <cont-id> /bin/bash

docker stop <cont-id/name>

docker start <cont-id/name>
