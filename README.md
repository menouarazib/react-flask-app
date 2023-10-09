# Orchestra

Orchestra is an MLOps system designed for the French National Data Center for Natural Plasmas of the Solar System (CDPP). It facilitates the installation, management, prediction, and monitoring of machine learning models. 

Each machine learning model is required to be implemented as a `python module` and should include a (metadata.json)[(https://github.com/menouarazib/orchestra/blob/master/metadata.json)] file with necessary information. Orchestra manages the installation of these models along with their requirements in a dedicated Docker container. 

All models installed within Orchestra are expected to adhere to these guidelines. This ensures a streamlined process and efficient management of resources within the system.


## Installation

### Docker

Orchestra uses docker to run predictions of each module in an isolated container, so in order to use it you should have installed docker in your machine.

### Run Orchestra

#### Dev Mode

To Run Orchestra in dev mode you just need to run:

- `docker-compose build`
- `docker-compose up`

#### Production Mode

To Run Orchestra in prod mode you just need to run:

- `docker-compose -f docker-compose.prod.yml build`
- `docker-compose -f docker-compose.prod.yml up`

## REST API endpoints

List of endpoints exposed by the REST API :

- `/modules` : retrieve a list of modules and associated metadata
- `/modules/<int:id>` : specific module metadata
- `/modules/<int:id>/run [args]` : request executing specified model with arguments supplied by user
- `/tasks` : retrieve list of tasks and associated metadata
- `/tasks/<int:id>` : specific task metadata (status, errors, output, ...)
- `/tasks/<int:id>/output` : download task output

## Monitoring Orchestra

To monitor Orchestra you just need to open http://localhost:3000/ :

- Installing a new module
- Rebuilding a module
- Trucking a running module for predictions
