# Thoughtworks Assignment
[*Jyoti Bhanot*](mailto:jyoti.bhanot30@gmail.com)

#### Tools Environment
These tools are used to host, build, test and run the infrastructure components
- [Ubuntu Linux](http://www.ubuntu.com/)
  - Staging Amazon Web Services [EC2](https://aws.amazon.com/ec2/)
  - Production Amazon Web Services [EC2](https://aws.amazon.com/ec2/)
- [Docker Hub](https://hub.docker.com/) and [Docker Toolbox](https://www.docker.com/products/docker-toolbox) including 
  - [docker engine](https://www.docker.com) 
  - [docker-compose](https://www.docker.com/products/docker-compose) 
- [Apache Bench](http://httpd.apache.org/docs/2.2/en/programs/ab.html)  

#### Application Environment
These software components are used to logically run the application 

- [Alpine Linux 3.3](https://www.alpinelinux.org/)
- [NGINX 1.9.15](https://www.nginx.com/)
- [Oracle Jdk 8.77.03](https://mail-tp.fareoffice.com/java/)
- [HAProxy](http://www.haproxy.org/)
- [Apache Jetty](http://www.eclipse.org/jetty/)

#### Prerequisites: 
- Ubuntu 14.04
- AWS EC2 instance
- docker 18.06
- docker-compose 1.7
- Login Creds for https://hub.docker.com

#### Usage
The Main script is infraproject.sh whcih takes commandline arguments and performs actions accordingly.
 - cd infraproject [User must be in the root folder (infraproject/) in order to run commands.]
 - ./infraproject  [Without any arguments, the script would install the prerequisites - docker, docker-compose]

##### [Staging]
 - ./infraproject staging build [Builds docker images from dockerfiles placed in corresponding directories creating according to environment.]
 - ./infraproject staging up [Spawns containers for static and web components of the blog.]
 - ./infraproject staging down [Stops and removes all containers created for the environment.]
 
##### [Prod]
 - ./infraproject production build [Builds docker images from dockerfiles placed in corresponding directories creating according to environment.]
 - ./infraproject production up [Spawns containers for static and web components of the blog.]
 - ./infraproject production down [Stops and removes all containers created for the environment.]

##### [Testing]
 - ./infraproject test

##### [Benchmarking]
 - ./infraproject bench

### Running at scale
There are both commercial and open source tools available create and maintain a container based production environment at scale.
 - Amazon EC2 Container Service (ECS) is a highly scalable, fast, container management service that makes it easy to run, stop, and manage Docker containers on a cluster of Amazon EC2 instances
 - Kubernetes
 - Docker Ecosystem : Docker Swarm - Docker Compose - Docker Registry - Docker Engine


