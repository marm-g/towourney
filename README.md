# What the heck is this?
bracket website, wip


# Development

## Pocketbase

There are two methods for running the database backend solution, Pocketbase.

### Bare Metal

Obtain a pocketbase executable for your specific OS and architecture: https://pocketbase.io/docs/
Extract the executable, and place it in the `towourney/pb` directory.  From that directory, simply run `./pocketbase serve` and visit the Admin UI at `localhost:8090/_/` to get started.  Migrations can be created easily from this directory as well, see https://pocketbase.io/docs/js-migrations/ for examples and usage.

### Docker

Run these commands from the `towourney` parent directory:

```
docker build -f Dockerfile -t pocketbase .
docker run -d --name pocketbase -p 8090:8080 pocketbase
```

When the container is ran, whatever migrations were present in this repository will be copied over to the container and applied on startup.