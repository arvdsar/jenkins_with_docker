# jenkins_with_docker

Jenkins for Docker. Included in this container is its own install of Docker.

-v /docker_volumes/jenkins:/var/jenkins_home
-v /var/run/docker.sock:/var/run/docker.sock

I use this Jenkins install to build my Docker images. Jenkins is running in its own container. By mounting /var/run/docker.sock inside the jenkins container to the /var/run/docker.sock on the docker host, it is now possible to build on the docker host. 

Make sure your jenkins user is member of 'docker' group and has rights inside the container to write to the docker.sock (hopefully I can fix this by default in a new version)


