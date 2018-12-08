#### Build a image

```
 docker build -t friendlyhello .
```

run the image

```
docker run -p 4000:80 friendlyhello
```

Run the app in background mode

```
docker run -d -p 4000:80 friendlyhello
```

Stop the container

```
docker container stop 1fa4ab2cf395

```


##### Docker Compose

Lets start stack service with docker.

Create docker-compose.yml

Create stack and deploy the compose.

```
docker stack deploy -c docker-compose.yml python-flask
```

Service running

```
docker stack ls

NAME                SERVICES            ORCHESTRATOR
python-flask        1                   Swarm
```

see the replicas 5 are runnning in different container.
```
docker service ps python-flask_web
or 
docker service ps <ServiceID> # docker service ls


ID                  NAME                 IMAGE                          NODE                    DESIRED STATE       CURRENT STATE           ERROR               PORTS
n9c2dcq1nogv        python-flask_web.1   kannansv/python-flask:latest   linuxkit-025000000001   Running             Running 2 minutes ago                       
o6n90afhm7o4        python-flask_web.2   kannansv/python-flask:latest   linuxkit-025000000001   Running             Running 2 minutes ago                       
ztlepx9otvk8        python-flask_web.3   kannansv/python-flask:latest   linuxkit-025000000001   Running             Running 2 minutes ago                       
ynr33prnkes9        python-flask_web.4   kannansv/python-flask:latest   linuxkit-025000000001   Running             Running 2 minutes ago                       
16zg10noi857        python-flask_web.5   kannansv/python-flask:latest   linuxkit-025000000001   Running             Running 2 minutes ago                       
```

See the site is up:

```
curl -4 http://localhost:4000

<h3>Hello World!</h3><b>Hostname:</b> d3f0b6b4c9c6<br/><b>Visits:</b> <i>cannot connect to Redis, counter disabled</i>%
```

Down the stack now.

```
docker stack rm python-flask

docker swarm leave --force
```

