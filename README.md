# dockerfiles

## install
### mac
https://github.com/katsudonik/knowledge/blob/master/mac/dev_env/docker.md

## commands

### check container name
```
$ docker-compose ps
      Name                    Command               State                     Ports                   
------------------------------------------------------------------------------------------------------
dcenv_app_1        php-fpm -F                       Up      9000/tcp, 0.0.0.0:9001->9001/tcp          
dcenv_kibana_1     /usr/local/bin/kibana-docker     Up      0.0.0.0:5601->5601/tcp                    
dcenv_logstash_1   /usr/local/bin/docker-entr ...   Up      0.0.0.0:5044->5044/tcp, 9600/tcp          
dcenv_nginx_1      nginx -g daemon off;             Up      0.0.0.0:80->80/tcp, 0.0.0.0:8000->8000/tcp
dcenv_redis_1      redis-server /etc/redis.conf     Up      0.0.0.0:6379->6379/tcp                    
elasticsearch      /usr/local/bin/docker-entr ...   Up      0.0.0.0:9200->9200/tcp, 9300/tcp          
mysql              docker-entrypoint.sh mysqld      Up      0.0.0.0:3306->3306/tcp, 33060/tcp         
```

- if use "docker", specify container name of "docker-compose ps"
- if use "docker-compose", specify container name of "docker-compose.yml"

### ssh in container
```
docker exec -it [container name of "docker-compose ps"] /bin/bash
```

### rebuild container
1. stop container
```
docker-compose stop [container name of docker-compose.yml]
```

2. remove container
```
docker-compose rm -f [container name of docker-compose.yml]
```

3. rebuild container
```
docker-compose build --no-cache [container name of docker-compose.yml]
```

4. up container
```
docker-compose up -d
```

### show log of container
```
docker-compose logs [container name of docker-compose.yml]
```

### scp
```
docker cp sample.txt [container name of "docker-compose ps"]:/tmp
```
