# Scan client API scripts

This is a collection of python scripts leveraging our Swagger library
to interact with the Scan API server. They're intended to be an
example of what's possible, and a starting point..

## We recommend using virtualenv with Python
We're fans of not polluting our systems to install python libraries. [Virtualenv](https://virtualenv.pypa.io/en/stable/) helps with this:
* `pip install virtualenv`
    (cd to this directory, or wherever you want to store a virtual environment)
* `virtualenv venv`
* . venv/bin/activate

## Install the Scan Python API library
* run `pip install layint_scan_api`

## Also, install required libraries
* In this source directory, run
```
pip install -r requirements.txt
```

## Set environment variables for your installation
```
export LI_API_KEY=ApiKey:demo:setanapikey
export LI_API_HOST=http://localhost/V0.0.1
```

## Finally, run the scripts
```
li_add_registry --name test2 --url=http://10.0.2.15:4000 --type dtr --verbose
```
