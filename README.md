---------------------------------------------------------------|
-------------------- Add User Group Docker --------------------|
1. Create the docker group if it does not exist                |
$ sudo groupadd docker                                         |
                                                               |
2. Add your user to the docker group.                          |
$ sudo usermod -aG docker $USER                                |
                                                               |
3. Log in to the new docker group (to avoid having to          |
log out / log in again; but if not enough, try to reboot):     |
$ newgrp docker                                                |
                                                               |
4. Check if docker can be run without root                     |
$ docker run hello-world                                       |
5. Reboot if still got error                                   |
$ reboot                                                       |
                                                               |
---------------------------------------------------------------|

syntax docker

1. install docker

2. docker images (for looked image on docker)

3. docker container ls --all (for looked all container, even started container or stoped container)

4. docker container ls (for looked just started container)

5. docker build --tag "name for repository":"version tag" "location path dockerFile"(for build name repository)
   examp : docker build --tag learn-make-img-golang:1.0.0 /docker-app/image/learn-make-img-golang

6. docker container create --name "name container" -p "port":"port" "name images"(for create container on golang)
examp : docker container create --name app1 -p 8080:8080 learn-make-img-golang:1.0.0

7. docker container start "name container" (for start container)
examp : docker container start app1

8. docker stop "id container"(for stop container)
examp : docker stop er23dasfas34

9. docker rm "id container" (for rm container)
examp : docker rm er23dasfas34

10. docker image rm "name images":"tag version" (for rm images docker)
examp : docker image rm learn-make-img-golang:1.0.0 

11. docker push "name images":"tag version" (for push images)
examp : docker push learn-make-img-golang:1.0.0 

12. docker tag "name image":"tag version" "name image on docker hub":"tag version on docker hub" (like a copy image local for copying to docker hub)
examp : docker tag learn-make-img-golang:1.0.0 ivannofick/learn-make-img-golang:1.0.0

13. docker run --name "name container" -p 80:80 -d nginx:"tag version" (for run nginx on docker)
examp : docker run --name servernginx -p 80:80 -d nginx:alpine

14. docker start -ai "container name" (If you want to see the output)
examp : docker start -ai servernginx

15. docker start container_name(to start container)
examp : docker start servernginx

16. docker restart container_name(to restart container)
examp : docker restart servernginx

17. docker exec -it "name container" ls /usr/share/nginx/html (location default path docker for run application)
examp : docker exec -it nginx-server ls /usr/share/nginx/html

18. docker exec -it <container-id> //bin//sh (for use bash on conatiner)
examp : docker exec -it server-nginx //bin//sh

19. docker run --name "name container" -p "ports":"default-port" -e MYSQL_ROOT_PASSWORD="pwd" -d mysql:"version"  (runer mysql container docker)
examp : docker run --name mysql-server -p 33061:3306 -e MYSQL_ROOT_PASSWORD=123 -d mysql:8.0.31

20. docker exec -it "name container mysql" bash (using bash on container mysql)
examp : docker exec -it mysql-server bash

21. docker exec -i "name container" mysql -u"user" -p"pwd" "name db" < "db.sql" (import database mysql)
examp : docker exec -i mysql-server mysql -uroot -p123 dbrisk_docker < dbrisk_151122.sql

22. docker run --name redis-server -p "port":"default-port" -d redis:"version" (run redis)
   examp : docker run --name redis-server -p 63791:6379 -d redis:7.0.5

23. docker exec -it "name redis continaer" redis-cli (run redis-cli without run bash)
   examp : docker exec -it redis-server redis-cli
   
24. docker exec -it "name redis continaer" bash (run redis-cli using run bash)
   examp : docker exec -it redis-server bash

25. To delete all containers including its volumes use,
          docker rm -vf $(docker ps -aq)
26. To delete all the images,
          docker rmi -f $(docker images -aq)
