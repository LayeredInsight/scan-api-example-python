# Scan client API scripts

This is a collection of python scripts leveraging our Swagger library
to interact with the Scan API server. They're intended to be an
example of what's possible, and a starting point..

## Usage
### We recommend using virtualenv with Python
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

### Install the Scan Python API library and dependencies
From this source directory, run

```
pip install layint_scan_api
pip install -r requirements.txt
```

### Set environment variables for your installation
```
export LI_API_KEY=ApiKey:demo:setanapikey
export LI_API_HOST=http://localhost/V0.0.1
```

### Finally, run the scripts
```
li_add_registry --name test2 --url=http://10.0.2.15:4000 --verbose
```

## Scripting
Where possible, we try to set exit codes in these scripts so they can be used in larger automation processes (such as CI builds). If a script is successful, it sets an exit code of **0**. For scripts that have an issue or failure, exit code is set to **1**.
