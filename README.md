# Malzoo Docker Container
### Description
A dockerized implementation of the [Malzoo static file analyzer project](https://github.com/nheijmans/malzoo/)
To get started with the Docker container, simply pull the image from the [Docker Hub](https://hub.docker.com/r/statixs/malzoo)
with the command 
```docker pull statixs/malzoo```

#### Persistent logs
If you want to have the logs persistently stored on the host OS, use the following command
```docker container run --detach --publish 127.0.0.1:1338:1338/tcp --name malzoo_engine --env-file env.list --rm --volume=./malzoo-logs:/home/malzoo/malzoo/logs/ malzoo:latest```

#### Persistent sample storage
Samples are stored by default in the **$HOME/malzoo/storage/** folder. If you want those to be persistent on the host OS, use the following command
```docker container run --detach --publish 127.0.0.1:1338:1338/tcp --name malzoo_engine --env-file env.list --rm --volume=./malzoo-samples:/home/malzoo/malzoo/storage/ malzoo:latest```

#### Environment list
The environment list contains two items that need to be included, in order for Malzoo to find the virtual environment of Python and to know where the library is for calculating the Fuzzy hashes. 

### Contribute
If you have a cool feature build for one of the workers or a new worker, feel free to submit a PR! Please include a good description on what is been added and how it benefits the platform :) 
