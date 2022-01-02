# intellipaat_devops_module_9 - Kubernetes
#### Problem statement
Use this github https://github.com/hshar94/helloworld
1. Create a 3 node setup of kubernetes Master and slave
2. Use the docker image which you created in Docker 1 assignment
3. Deploy 2 pods with the same container but different index.html content, modify the content from the above github to the following:
Pod 1: "Welcome to Pod 1"
Pod 2: "Welcome to Pod 2"
4. Each pod should have 2 replicas
5. Create the desired services for these pods
6. Setup path based routing on these services, which can be accessed from the outside
"/pod1" --> service 1
"/pod2" --> service 2

#### Steps
1. Create 3 node k8s cluster
2. Code k8s manifest files and index.html files
3. Create config maps for index pages to be served by pods
   ```
   kubectl apply -f configmap/cm_web_one.yml
   kubectl apply -f configmap/cm_web_two.yml
   ```
4. Create deployments with 2 replicas
   ```
   kubectl apply -f deployment/deployment_one.yml
   kubectl apply -f deployment/deployment_two.yml
   ```
5. Create services
   ```
   kubectl apply -f service/svc_web_one.yml
   kubectl apply -f service/svc_web_two.yml
   ```
6. Deploy ingress controller - https://docs.nginx.com/nginx-ingress-controller/installation/installation-with-manifests/
7. Create ingress for services for path based routing
   ```
   kubectl apply -f ingress/ing_web.yml
   ```