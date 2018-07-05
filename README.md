[![Docker Pulls](https://img.shields.io/docker/pulls/layeredinsight/scan-python-client.svg?style=plastic)](https://hub.docker.com/r/layeredinsight/scan-python-client/)

# Scan client API scripts

This is a collection of python scripts leveraging our Swagger library
to interact with the Scan API server. They're intended to be an
example of what's possible, and a starting point..

## Usage
These scripts can either be downloaded and used on a local system, or via a docker contianer. Below we

### Local use - we recommend using virtualenv with Python
We're fans of not polluting our systems to install python libraries. [Virtualenv](https://virtualenv.pypa.io/en/stable/) helps with this:
```
pip install virtualenv
```
`cd` to this source directory, or wherever you want to store a virtual environment and initialize a new virtual Python environment with...

```
virtualenv venv
. venv/bin/activate
```
Now any libraries you install with pip will be local to this environment, accessible only after sourcing *venv/bin/activate*

#### Install the Scan Python API library and dependencies
From this source directory, run

```
pip install layint_scan_api
pip install -r requirements.txt
```

#### Set environment variables for your installation
```
export LI_API_KEY=ApiKey:demo:setanapikey
export LI_API_HOST=http://localhost/V0.0.1
```

#### Finally, run the scripts
```
li_add_registry --name test2 --url=internal-registry.corp --verbose
```

### Using the docker image
If you do not wish to set up this software locally, it can be run from a [docker image](https://hub.docker.com/r/layeredinsight/scan-python-client/):

```
$ docker run --rm -ti layeredinsight/scan-python-client
/ # export LI_API_KEY=ApiKey:username:yourapikeyvalue
/ # export LI_API_HOST=http://localhost:V0.0.1
/ # cd /layint
/layint # ./li_list_registries
 ID - Name - URL
 5abd7a3eea61520001308a76 - Docker Hub - docker.io
```

One trick: If you're repeatedly running the docker image, setting the environment variables from the `docker run` command can save some repititive work inside the container:

```
$ docker run --rm -ti -e LI_API_KEY=ApiKey:username:yourapikeyvalue -e LI_API_HOST=http://localhost:V0.0.1 layeredinsight/scan-python-client
```

## Scripting
Where possible, we try to set exit codes in these scripts so they can be used in larger automation processes (such as CI builds). If a script is successful, it sets an exit code of **0**. For scripts that have an issue or failure, exit code is set to **1**.
