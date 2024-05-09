bracket website, wip

To start pocketbase, run these commands from the `towourney` parent directory:

```
docker build -f Dockerfile -t pocketbase .
docker run -d --name pocketbase -p 8090:8080 pocketbase
```

Note that this will create an image named pocketbase, then run said image in a container named pocketbase, mapping the container port
8080 to host port 8090.