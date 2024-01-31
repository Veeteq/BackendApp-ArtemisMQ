# BackendApp-ArtemisMQ
Steps to configure Artemis Message Queue

```
docker run --detach --name artemismq \
-p 61616:61616 \
-p 8161:8161 \
--rm -e ARTEMIS_USER=<user> -e ARTEMIS_PASSWORD=<password> \
apache/activemq-artemis
```

# Connect to container
`docker exec -it artemismq bash`

# Connect to artemis console
`docker exec -it artemismq /var/lib/artemis-instance/bin/artemis shell --user <user> --password <password>`
