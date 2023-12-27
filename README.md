# Docker
### Casual commands
```
docker exec -ti pihole ping 192.168.22.99
docker exec -t -i nginxproxy /bin/bash
```

### InfluxDB delete 
```
influx delete --org muh --bucket muh --start '1970-01-01T00:00:00Z' --stop $(date +"%Y-%m-%dT%H:%M:%SZ") --predicate '_measurement="temperature" AND node="101"' --token ''
```

### Nextcloud update
```
docker exec -it nextcloud updater.phar
```
### Nextcloud granting access
```
occ config:system:set overwriteprotocol --value="https"
```

### PostgreSQL create database
```
psql -U postgres -h localhost
CREATE database netbox;
```

### Clean all
```
docker system prune
docker network prune
```

### Create network
```
docker network create -d macvlan --subnet=192.168.22.0/24 --gateway=192.168.22.1 --ip-range=192.168.22.100/31 -o parent=eth0 mac0
docker network create -d macvlan --subnet=192.168.22.0/24 --gateway=192.168.22.1 --ip-range=192.168.22.100/31 -o parent=eno1 mac0
```

### Update & rebuild
```
docker compose pull
docker compose down && docker compose rm
docker compose up --build
```
