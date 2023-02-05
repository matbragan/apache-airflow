# apache-airflow

Up docker containers and use the airflow in [localhost:8080](http://localhost:8080/home)
```sh
docker-compose up -d
```

If the flower container don't up with the above command, use this command and up the flower in [localhost:5555](http://localhost:5555/)
```sh
docker-compose --profile flower up -d
```

<br><br>

Some useful commands in docker
```sh
docker-compose ps                      # list of containers with your health

docker-compose down                    # kill the containers

docker stats                           # container stats, CPU, memory, ...

docker exec -it <container> /bin/bash  # execute a container, entering it

docker kill $(docker ps -aq)           # kill all the containers, good for debug, but be careful
```

<br><br>

Test and debug of your dags and tasks from airflow, run the command inside the container (docker exec)
```sh
airflow dags test <dag_id>             # test all dag

airflow tasks test <dag_id> <task_id>  # test one task from dag
```

<br><br>

For problems with permission, maybe this command help you
```sh
sudo chown -R <username> <directory>
```

<br><br>

### Elastic Search
For the elastic search container you need the docker-compose-es.yaml
```sh
docker-compose -f docker-compose-es.yaml up -d
```
```sh
docker-compose -f docker-compose-es.yaml ps
```
