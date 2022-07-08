# Express.js REST API

The project consists of a REST API built with Express.js and Node.js to interact with a PostgresSQL database.

Additionally, it has its respective Dockerfiles for its 3 environments, Prod, Dev and Stg. 

Which you can find in the following link with the respective instructions: https://hub.docker.com/repository/docker/vairome/pern-server

## 🚀 Quick reference

•	Maintained by: Byron Murillo

•	Where go to get help: https://github.com/vairome/k8s-app/issues

## How it works

This is a Express.js API to connect to a Postgres DB, which has port 5000 released to run.

In addition, this image is linked to a GitHub Actions that updates the static content of the website which triggers on any change push or pull request events from the master branch. It also contains a gitHubb Actions workflow to build and push a docker image tho Docker Hub, updating the tags to maintain previous version of the image.
## How to use this API

### How to test the API locally

## License

[MIT](https://choosealicense.com/licenses/mit/)

