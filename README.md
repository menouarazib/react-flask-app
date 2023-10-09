# Orchestra: A Tailored MLOps System

Orchestra is a specialized MLOps system, meticulously designed for the [**French National Data Center for Natural Plasmas of the Solar System (CDPP)**](https://cdpp.cnes.fr/). Its core function is to facilitate the installation, management, prediction, and monitoring of pre-existing machine learning models. These models are uniquely tailored for detecting events in space physics data. This innovative system significantly boosts the efficiency for generating catalogs of events in space physics, marking it as an indispensable asset in the realm of space research.

Each machine learning model is mandated to be implemented as a `python module` and must include a [metadata.json] file containing essential information. Orchestra expertly manages the installation of these models along with their requirements within a dedicated Docker container.

All models integrated within Orchestra are required to comply with these guidelines. This ensures a seamless process and effective management of resources within the system, thereby enhancing its overall performance.

# Installation of Orchestra

To install Orchestra, ensure that `docker` is installed on your machine, then clone this repository.

# Running Orchestra

## Dev Mode

To Run Orchestra in dev mode you just need to run:

- `docker-compose build`
- `docker-compose up`

## Production Mode

To Run Orchestra in prod mode you just need to run:

- `docker-compose -f docker-compose.prod.yml build`
- `docker-compose -f docker-compose.prod.yml up`

# Monitoring Orchestra

To monitor Orchestra you just need to open http://localhost:3000/:

- Installing a new module
- Rebuilding a module
- Trucking a running module for predictions

# Model Installation
To install a new ML model you need to go to the home page of Orchestra then import your Git Repository of your Machine Learning Model.

# Model Prediction
Once the model is installed it will be available in [CDPP-AMDA](http://amda.irap.omp.eu/) tools and ready to make prediction. For this you should have take into account how to access in you python module to AMDA data space physics.

## Docker
Orchestra uses docker to run predictions of each model in an isolated container, so in order to use it you should have installed docker in your machine.  

# Orchestra REST API endpoints

List of endpoints exposed by the REST API :

- `/modules` : retrieve a list of modules and associated metadata
- `/modules/<int:id>` : specific module metadata
- `/modules/<int:id>/run [args]` : request executing specified model with arguments supplied by user
- `/tasks` : retrieve list of tasks and associated metadata
- `/tasks/<int:id>` : specific task metadata (status, errors, output, ...)
- `/tasks/<int:id>/output` : download task output


