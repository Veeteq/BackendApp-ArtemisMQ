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
## Change the restart policy for an already running container named artemismq
`docker update --restart unless-stopped artemismq`

## Connect to container
`docker exec -it artemismq bash`

## Connect to artemis console
`docker exec -it artemismq /var/lib/artemis-instance/bin/artemis shell --user <user> --password <password>`

## Produce test messages (execute from artemis shell)
`producer --destination=myqueue --message-size 1024 --message-count 10`

## Consume test messages (execute from artemis shell)
`consumer --destination myqueue --message-count 10 --verbose`

### Install docker-compose
curl -L https://github.com/docker/compose/releases/download/v2.24.5/docker-compose-darwin-x86_64 -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose --version
