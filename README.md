Start the eksctl setup

curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
sudo mv /tmp/eksctl /usr/local/bin

or

curl --silent --location "https://github.com/weaveworks/eksctl/releases/download/v0.147.0/eksctl_Linux_amd64.tar.gz" | tar xz -C /tmp
sudo mv /tmp/eksctl /usr/local/bin


eksctl version

Create Cluster

eksctl create cluster --name my-eks-cluster  


kubectl get pod

kubectl get node

kubectl get deployments

kubectl get rs

kubectl get pods --show-labels

Let's update the nginx Pods to use the nginx:1.16.1 image instead of the nginx:1.14.2 image.

kubectl set image deployment.v1.apps/nginx-deployment nginx=nginx:1.16.1

or use the following command:

kubectl set image deployment/nginx-deployment nginx=nginx:1.16.1

kubectl exec -ti nginx-deployment-77d8468669-grz9l  -- bash

kubectl run my-nodejs-app --image=gokuljpk/mynodeapp --port=3000
kubectl run myapp --image=gokuljpk/myapp:v1 --port=3000

kubectl delete pod nginx-deployment-77d8468669-grz9l

kubectl run nginx-pod --image=nginx --restart=Never --port=80 -n default

kubectl expose deployment my-nodejs-app --type=LoadBalancer --port=80 --target-port=3000

kubectl expose deployment myapp --type=LoadBalancer --port=80 --target-port=3000

kubectl expose pod nginx-pod --type=LoadBalancer --port=12 --target-port=80

kubectl delete deployment <deployment-name>
