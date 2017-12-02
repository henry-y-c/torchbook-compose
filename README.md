# Torchbook Compose

This is a simple docker compose setup to quickly start a local environment for learning and developing PyTorch with Jupyter notebook.

> **NOT FOR PRODUCTION**  
> To reduce overheads in local uses, passwords and tokens are disabled for jupyter notebook. It is not secure to use this for production.

## Features

Docker image: [henryc/pytorch-notebook](https://hub.docker.com/r/henryc/pytorch-notebook/)

* Debian v9.2
* Anaconda v5.0.1
* PyTorch v0.2.0
* No token nor password for Jupyter notebook

Docker compose:

* Map port 8888 from localhost to 8888 on container
* Mount ./notebooks from host to /opt/notebooks

Bash scripts:

* `up.sh` creates and starts a container in detached mode
* `down.sh` stops and removes the container and docker volume

## Usage

> Make sure you already have latest "Docker for X" installed. [Get Docker Community Edition](https://www.docker.com/community-edition#/download)

* To start the notebook, run:

    ``` sh
    $ bash up.sh
    ```

    Then open http://localhost:8888 in a Web browser on your host machine.

* To stop the notebook, run:

    ``` sh
    $ bash down.sh
    ```

* To view logs, first run:

    ``` sh
    $ docker ps
    # - or -
    $ docker container ls
    ```

    Find the container name or ID, for example `torchbookcompose_torchbook_1`, then run:

    ``` sh
    $ docker logs torchbookcompose_torchbook_1
    # - or -
    $ docker container logs torchbookcompose_torchbook_1
    ```
