<h1>E-commerce Backend Deployment on kubernetes</h1><br>

This project is about  kubernetes deployment for E-commerce backend.
The E-commerce backend project link (https://github.com/purbo75/E-Commerce-site-BackEnd-with-Node-js.git )
<br>
 
********
<h2>Tools</h2>
<ol>
	<li>Docker</li>
	<li>Kubernetes</li>
	<li>Minikube</li>
	
</ol>
*********
<p> To install minikube : </P><br>
	sudo apt-get update<br>
	curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 <br>
	sudo install minikube-linux-amd64 /usr/local/bin/minikube <br>
	minikube start
***********

	
The commands to run the deployment on Ubuntu - <br>

<ul>
	<li>
		To start minikube:
				minikube start
	</li>
	<li>
		To enable ingress-nginx:
				kubectl addon enable ingress-inginx
	</li>
	<li> 
		
			kubectl apply -f FileName
	 </li>
</ul><br>

**********

