[![gabriellllo](https://circleci.com/gh/gabriellllo/devopsproj.svg?style=shield)](https://circleci.com/gh/gabriellllo/devopsproj)

## Project Overview

In this project it is demonstrated how to operationalize a Machine Learning Microservice API. 

We start from a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features. More info about the data, which was initially taken from Kaggle, can be found on [the data source site](https://www.kaggle.com/c/boston-housing). 

The predictions of the model are served through a Python flask app implemented in the file `app.py`, that responds to API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

## Setup the Environment

* Create a virtualenv and activate it, i.e. `python3 -m venv ~/.devops && source ~/.devops/bin/activate`
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Files in the repository

* the directory `.circleci` contains the configuration file for the continuous integration service CircleCI
* the directory `modeldata` contains the pretrained model and the input data used to train it in `csv` format
* the directory `output_txt_files` contains the output of the commands used when running the application in Docker or in Kubernetes
* `app.py` is the python Flask application
* `Dockerfile` contains the configuration to containerize the application
* `make_predictions.sh` is a bash script that makes call to the local API to test it
* `Makefile` is used to install dependencies of the project and lint the `Dockerfile` and the `app.py` file
* `README.md` is this readme file
* `requirements.txt` contains the required additional libraries for Python
* `run_docker.sh` is a bash script to build and execute the app locally in a Docker container
* `run_kubernetes.sh` is a bash script to execute the containerized app on a Kubernetes cluster
* `upload_docker.sh` is a bash script used to upload the containerized app on Docker Hub
