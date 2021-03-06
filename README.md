# Screeps Server

There are two different type how to start a screeps server.
* [without a world](#create-the-world)
* [with a world already created](#running-the-server)
Support platform
* amd64
* arm64
* arm v7

## Create the world
If you do not have an existing server directory, just start the Docker container with the command line argument `init`, and everything gets done for you.

```bash
docker run -it --rm -v $PWD:/screeps theadore/screeps_server:latest init
```
Now it's all set to run the Screeps server.

## Running the server
If you have already a server directory (from previous installations) follow the steps below.

1. Make sure you are in the server directory
2. Run the server
```bash
docker run -d --name screeps-server -v $PWD:/screeps -p 21025:21025 theadore/screeps_server
```

## Managing the server


### Mods
Mods can be installed by running:
```docker run --rm -v $PWD:/screeps theadore/screeps_server yarn add screepsmod-auth```

### CLI
The CLI can be accessed by running:
```docker exec -it screeps-server npx screeps cli```

## Stopping and starting the server
Stop:
```docker stop screeps-server```  
Start:
```docker start screeps-server```

## Updating

1. Stop the server:
  ```docker stop screeps-server```
2. Remove the server:
  ```docker rm screeps-server```
3. Follow [Running the server](#running-the-server)

