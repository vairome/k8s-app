# PERN Stack K8s Application

The project consists of a simple CRUD using React App as a client created to send numbers to a PostgresDB using a Express.js REST Api server, and also have a Nginx Ingress controller and ArgoCD deployment to monitor any changes.

## Docker Images
Docker Image client: https://hub.docker.com/repository/docker/vairome/pern-client
Docker Image server: https://hub.docker.com/repository/docker/vairome/pern-server

## Setup 

First we have to navigate to our k8s directory to apply all the yaml files using the kubectl command line interface with the next command

`kubectl apply -f k8s`

Note: You have to create the pgpassword in the default namespace, because this password is used to create the postgres database and is used to make the connection between the server and the database.

Next we have to install the Ingress Nginx controller with the following command

`kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.2.1/deploy/static/provider/cloud/deploy.yaml` 

this ingress gives you the possibility to access from the default port of your localhost.

![K8s App](/Pern.jpeg?raw=true "PERN Stack K8s App")

### Add the ArgoCD application

To add the ArgoCD to our application we have to install from the official documentation with the next command:

`kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml`

Next we have to make a port forward to our local host to gain access to the ArgoCD UI with the next command:

`kubectl port-forward -n argocd svc/argocd-server 8080:443`

Note: We have to get the secret for the admin user with the next two commands:

`kubectl get secret argocd-initial-admin-secret -n argocd -o yaml`

And pass it through a decode since this password is encrypted

`echo password | base 64 --decode`

When you gain access to the ArgoCD UI, we have to make a new application with the yaml located on the /argocd folder, the agent will be in charge of constantly monitoring any changes in the application and makes automatic deployments.

![Argo App](/argo.jpeg?raw=true "Argo App")

### 🚀 Quick reference

•	Maintained by: Byron Murillo

•	Where go to get help: https://github.com/vairome/k8s-app/issues

### License

[MIT](https://choosealicense.com/licenses/mit/)
