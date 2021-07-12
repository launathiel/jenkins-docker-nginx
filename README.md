# Jenkins-Docker-Nginx

in this time, I will show you simple CI/CD pipeline using jenkins that running on docker container. 

We will build a nginx webserver that contain custom html site.


## Deploy Jenkins on Docker
```bash
cd jenkins
docker-compose -f jenkins-compose.yml build
docker-compose -f jenkins-compose.yml up -d
```
the jenkins server will run on your host port 8083.

### Access jenkins UI 
```bash
http://$host:8083
```

you will see this started page and you'll be asked for lock password.

```bash
