docker build -t pankaj1998/green-maven-web-app .
docker run -d -p 8083:8080 pankaj1998/maven-web-app

kubectl delete deployment,svc --all 



kubectl apply -f blue-deployment.yml
kubectl apply -f live-service.yml
minikube service javawebapplivesvc --url

kubectl apply -f green-deployment.yml
kubectl apply -f pre-pod-service.yml
minikube service javawebappprepodsvc --url


now make green-deployment as live service

in live-service.yml change v1 to v2
selector:
    version: v1->v2
kubectl apply -f live-service.yml


docker system prune 
docker system prune --volumes -a -f



