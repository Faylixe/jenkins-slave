# Jenkins-slave

Light container that aims to be used as a Jenkins slave node entry point.

The idea is to provide a fast and efficient way to run jenkins slave node using docker, where slave can also use docker (and will only do).

Built from following existing docker images:

* https://github.com/danielguerra69/alpine-sshd
* https://github.com/evarga/docker-images

This image is built using Alpine, and have SSH server, git, and docker binary. To start agent in a machine,
simply run the following command in the docker host machine that will run the slave agent :

```bash
docker run -p 69:22 -v /var/run/docker.sock:/var/run/docker.sock faylixe/jenkins-slave
```

Then register your node on Jenkins, with following credentials :

* User : jenkins
* Password : jenkins

## Future plan

* Integrate dynamic password parameter through docker run command.
