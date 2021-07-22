# Install cert-manager with helm
## source: https://cert-manager.io/docs/installation/kubernetes/
  
## Create a namespace
### $ kubectl create namespace cert-manager
  
## Add Jeststack repo
### $ helm repo add jetstack https://charts.jetstack.io
  
## update helm repos
### $ helm repo update
  
## Install cert-manager and CRDs from jetstack repo
### $ helm install cert-manager jetstack/cert-manager --namespace cert-manager --create-namespace --version v1.6.0 --set installCRDs=true
  
## Verify the installation
### $ kubectl get pods --namespace cert-manager
  
## to create a selfsigned certificate
### $ kubectl apply -f ./selfsigned/
  
## Verify the certificate
### $ kubectl -n cert-manager-test get certificate
### $ kubectl -n cert-manager-test get certificaterequest
### $ kubectl -n cert-manager-test get secret

