<h1>Hello with kubernetes</h1><br>

This project is about  kubernetes deployment for E-commerce backend.
The E-commerce backend project link (https://github.com/purbo75/E-Commerce-site-BackEnd-with-Node-js.git )
<br>

***********

Basically this is beginner level project for kubernetes.One can hello with kubernetes by doing this project.
 
********

<h2> About this project</h2>

This is a simple project where a docker image run from kubernetes. A docker image named purbo75/backend from dockerhub run on a deployment file(server-deployment.ymal)
.For this Deployment, A Service is exposed from server-cluster-service.yaml. To access this service, ingress-ngins is configured from ingress service.yaml.

<br>

To configured domain name edit /etc/hosts with the minikube ip.    

<br>

The docker image return a list of json product list(/api/products).

************

<h2>Tools</h2>
<ol>
	<li>Docker</li>
	<li>Kubernetes</li>
	<li>Minikube</li>
	
</ol>

********

<p> To install minikube : </P><br>

	sudo apt-get update

	curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

	sudo install minikube-linux-amd64 /usr/local/bin/minikube

	minikube start

***********

	
The commands to run the deployment on Ubuntu - <br>

To start minikube: 

	minikube start

To enable ingress-nginx:<br>

	kubectl addons enable ingress-nginx

or
	
	minikube addons enable ingress-nginx
		
	kubectl apply -f FileName

**********

kubectl command-<br>

To get the pods information<br>

	kubectl get pods

To get the service information<br>

	kubectl get services

To get all service regardless of all name-space

	kubectl get svc -A

To edit ingress-nginx service type

	kubectl edit service ingress-nginx-controller -n ingress-nginx

then edit the spec.type(as example one has to change it from Nodeport to Loadbalancer, just edit the type).<br>

To get the namespace information<br>

	kubectl get ns

To get the pod's  log<br>

	kubectl logs pod_name

To restart a pod:<br>
	
	kubectl rollout restart deployment pod_name

To get the logs of ingress- nginx controller: <br>

	kubectl logs  -n ingress-nginx  ingress-nginx-controller_name

To set service to a local port:<br>

	 kubectl port-forward service/server-cluster-ip-service local_port:service's port 

To execute command on pod's bash:<br>

	kubectl exec --stdin --tty pod_name  -- sh


