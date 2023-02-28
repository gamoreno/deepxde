# Running with Docker

This is based on the instructions found in https://deepxde.readthedocs.io/en/latest/user/installation.html

## Prerequisites
- install git (for Windows, it can be installed from the SEI Software Center)
- install [Docker Desktop](https://www.docker.com/get-started/)
  - make sure to follow the instructions for your OS (e.g., for Windows: https://docs.docker.com/desktop/install/windows-install/).
- for SEI users, set the proxy for Docker:
  - open Docker Desktop settings, go to Resources|Proxies, turn `Manual proxy configuration` on, and set 'HTTP' and 'HTTPS' to `http://cloudproxy.sei.cmu.edu:80`

## Building the Docker image
Use **our** fork of DeepXDE (for now, until the pull request to fix the Dockerfile is accepted):

```
git clone https://github.com/gamoreno/deepxde.git
cd deepxde/docker
docker build -f Dockerfile . -t deepxde
```

## Starting the Docker container
The following command will start a DeepXDE Docker container mapping your current working directory to the container. It is useful to CD into a directory where you want to have Jypiter notebooks and data files for DeepXDE first

```
docker run --rm -v $(pwd):/root/shared -w "/root/shared" -p 8888:8888 deepxde
```

Once it starts, open a web browser and go to the URL starting with `http://127.0.0.1:8888` shown in the instructions shown after starting the Docker container.




