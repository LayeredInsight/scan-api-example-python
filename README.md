# Scan client API scripts

This is a collection of python scripts leveraging our Swagger library to interact with the Scan API server.

## First, install virtualenv and create a virtual environemnt so you don't pollute your whole box.
* `pip install virtualenv`
    (cd to this directory, or wherever you want to store a virtual environment)
* `virtualenv venv`
* . venv/bin/activate

## Generate python client from swagger UI
* Download from https://gitlab.layeredinsight.net/backend/serve/-/jobs/artifacts/develop/download?job=swagger-client-codegen
* unzip it and cd into that directory
* run `pip install .`

## Also, install required libraries
* In this source directory, run
```
pip install -r requirements.txt
```

## Finally, run the scripts
```
export LI_API_KEY=ApiKey:demo:demoapikey
export LI_API_HOST=http://localhost:5000/V0.0.1
li_add_registry --name test2 --url=http://10.0.2.15:4000 --type dtr --verbose
```
