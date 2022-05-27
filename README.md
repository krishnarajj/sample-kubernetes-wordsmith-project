# sample-kubernetes-wordsmith-project

Wordsmith is the demo project shown at DockerCon EU 2017 and 2018.

The demo app runs across three containers:

db - a Postgres database which stores words

words - a Java REST API which serves words read from the database

web - a Go web application which calls the API and builds words into sentences:

# Build and Run in Docker Compose
The only requirement to build and run the app from source is Docker. Clone this repo and use Docker Compose to build all the images. You can use the new V2 Compose with docker compose or the classic docker-compose CLI:

docker compose up --build
Or you can pull pre-built images from Docker Hub using docker compose pull.

# Deploy Using a Kubernetes Manifest
You can deploy the same app to Kubernetes using the Kubernetes manifest. That describes the same application in terms of Kubernetes deployments, services and pod specifications.

Apply the manifest using kubectl:

kubectl create -f kube-deployment.yml
Your pods and services will be created . To see the website use minikube ip cmd which shows an ip address and then use the command kubectl describe svc web you can get the nodeport ip in which web app is running .Use the minikubeip:nodeport combination to see the website.


Docker Desktop includes Kuernetes and the kubectl command line, so you can work directly with the Kube cluster. Check the services are up, and you should see output like this:
![Screenshot 2022-05-27 132935](https://user-images.githubusercontent.com/96655654/170657209-cb6d9fad-0506-4edb-85c2-c756c842bd28.png)

Check the pods are running, and you should see one pod each for the database and web components, and five pods for the words API - which is specified as the replica count in the compose file:
![Screenshot 2022-05-27 133215](https://user-images.githubusercontent.com/96655654/170657734-b77ba65a-976e-45ac-9015-c32cf71e0f3d.png)

