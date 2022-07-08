# k8s-app

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
