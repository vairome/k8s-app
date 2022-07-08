# PERN Stack K8s Application

The project consists of a simple CRUD using React App as a client created to send numbers to a PostgresDB using a Express.js REST Api server.

## To test the app locally, yo have to follow the next steps 

First we have to navigate to our k8s directory to apply all the yml files using the kubectl command line interface with the next command `kubectl apply -f k8s`
Note: You have to create the pgpassword in the default namespace, because this password is used to create the postgres database and is used to make the connection between the server and the database.

Next we have to install the Ingress Nginx controller with the next command  `kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.2.1/deploy/static/provider/cloud/deploy.yaml` this ingress gives you the possibility to access from the default port of your localhost.

![K8s App](/Pern.jpeg?raw=true "PERN Stack K8s App")

## Add the ArgoCD application
   
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl get pods n argocd
kubectl get svc -n argocd
kubectl port-forward -n argocd svc/argocd-server 8080:443
kubectl get secret argocd-initial-admin-secret -n argocd -o yaml
echo MXVHbnhHMG1Ya3B1RWc3bw== | base 64 --decode

### 🚀 Quick reference

•	Maintained by: Byron Murillo

•	Where go to get help: https://github.com/vairome/k8s-app/issues

### License

[MIT](https://choosealicense.com/licenses/mit/)
