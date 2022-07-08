# PERN Stack K8s Application

The project consists of a simple CRUD using React App as a client created to send numbers to a PostgresDB using a Express.js REST Api server.

![K8s App](/?raw=true "PERN Stack K8s App")

kubectl apply -f k8s
Kubectl get pods
Kubectl get services
Kubectl get secrets
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.2.1/deploy/static/provider/cloud/deploy.yaml
kubectl get pods --namespace=ingress-nginx    
kubectl create secret generic pgpassword --from-literal PGPASSWORD=admin2022
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl get pods n argocd
kubectl get svc -n argocd
kubectl port-forward -n argocd svc/argocd-server 8080:443
kubectl get secret argocd-initial-admin-secret -n argocd -o yaml
echo MXVHbnhHMG1Ya3B1RWc3bw== | base 64 --decode

To test the app locally, yo have to run 

### `docker compose up --build`

The Docker compose file, have an additional configuration for a Nginx server to deploy the React build into the port 80 as default to route the traffic more efficiently, and also have the configuration for the Postgres deploy, connected to the API to works correctly in a local environment.

## React App Client

The project consists of a simple React App created to send numbers to a PostgresDB using a Express.js REST Api.

Additionally, it has its respective Dockerfiles for its 3 environments, Prod, Dev and Stg. 

Which you can find in the following link with the respective instructions: https://hub.docker.com/repository/docker/vairome/pern-client

### 🚀 Quick reference

•	Maintained by: Byron Murillo

•	Where go to get help: https://github.com/vairome/k8s-app/issues

### How it works

This is a React App, which has port 3000 released to run the static website.

In addition, this image is linked to a GitHub Actions that updates the static content of the website which triggers on any change push or pull request events from the master branch. It also contains a gitHubb Actions workflow to build and push a docker image tho Docker Hub, updating the tags to maintain previous version of the image.

### How to use this React App

### Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

You may also see any lint errors in the console.


## Express.js REST API

The project consists of a REST API built with Express.js and Node.js to interact with a PostgresSQL database.

Additionally, it has its respective Dockerfiles for its 3 environments, Prod, Dev and Stg. 

Which you can find in the following link with the respective instructions: https://hub.docker.com/repository/docker/vairome/pern-server

### 🚀 Quick reference

•	Maintained by: Byron Murillo

•	Where go to get help: https://github.com/vairome/k8s-app/issues

### How it works

This is a Express.js API to connect to a Postgres DB, which has port 5000 released to run.

In addition, this image is linked to a GitHub Actions that updates the static content of the website which triggers on any change push or pull request events from the master branch. It also contains a gitHubb Actions workflow to build and push a docker image tho Docker Hub, updating the tags to maintain previous version of the image.

### How to use this API

### Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:5000) to view it in your browser.

You may also see any lint errors in the console.
### License

[MIT](https://choosealicense.com/licenses/mit/)
