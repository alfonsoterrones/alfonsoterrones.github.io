---
layout: post
title: My first day with Docker!
---
![First Post](/images/docker.png "First Post")

This is my first blog post in english and its possibility that I have a lot of grammatical errors.

The Compose file is a YAML file defining services, networks and volumes. Our proyect have four services (web, mysql, selenium, sparql )

Services/Containers
The id of de containers can change but its alias never change.
Inside /lib is the works custom.

## Services
1. **Web:** this container organize service apache, Its directories and configurations.
1. **MySQL:** this container ornagaze service mysql, its directories and configurations.
1. **Sparql:** this container have a database MySQL that maneges all Drupal’s taxonomies, subthemes, configurations.

## Docker utility commands
1. **sudo chmod 666 /var/run/docker* *** -> permissions to the docker folder.
1. **docker-compose stop** -> stop docker and its services.
1. **docker-compose up -d** -> start docker and its services.
1. **docker ps** -> it shows the status of all running process along theirs ID’s.
1. **docker inspect** -> return slow-level information on Docker object, we get ip to proyect deploy.
1. **docker-compose exec web ./vendor/bin/run toolkit:install-clean** -> Eject “toolkit:install-clean” in “./vendor/bin/”, this command installs our Drupal.
1. **docker-compose exec web composer install** -> whithin the “Web” services we ejecute this command “composer install".
1. **docker-compose exec mysql /bin/bash** -> open prompt mysql.
1. **docker cp ./europass_dump.sql $IDCONTAINER:/tmp/** -> cp dump to Mysql services.
1. **docker-compose exec mysql mysql -u root -p** -> open Mysql
1. **docker system prune -f** ->  reset docker after "docker-compose stop"

## Files of interest
1. **.env** -> Enviroment variables, it values are availables to containers.
1. **./docker-compose.yml.** -> This is default path for a Compose file

