# BackendApp-ArtemisMQ
Steps to configure Artemis Message Queue

```
docker run --detach \
--name artemismq \
--rm \
-p 61616:61616 \
-p 8161:8161 \
-e ARTEMIS_USER=<user> -e ARTEMIS_PASSWORD=<password> \
-v /root/docker/volumes/artemismq:/var/lib/artemis-instance/etc-override \
apache/activemq-artemis
```

# Connect to container
`docker exec -it artemismq bash`

# Connect to artemis console
`docker exec -it artemismq /var/lib/artemis-instance/bin/artemis shell --user <user> --password <password>`

# Produce test messages
producer --destination=myqueue --message-size 1024 --message-count 10

# Consume test messages
consumer --destination myqueue --message-count 10 --verbose
