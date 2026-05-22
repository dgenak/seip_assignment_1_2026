1)
   ## Clone the Repository
   To download the project, I executed: git clone https://github.com/dgenak/seip_assignment_1_2026.git to enter the folder: cd seip_assignment_1_2026
   
   ## Starting Minikube
   I started the Kubernetes cluster using the Docker driver:
   minikube start --driver=docker
   
   ## Manifests (Sequential)
   I applied the Kubernetes manifests in the correct order:
   ConfigMap
   kubectl apply -f k8s/configmap.yaml
   Secret
   kubectl apply -f k8s/secret.yaml
   Deployment
   kubectl apply -f k8s/deployment.yaml
   Service
   kubectl apply -f k8s/service.yaml
   
   ## Checking that the Pods are Running
   I waited to see that the 3 pods are running:
   kubectl get pods -n default
   
   ## Port Forwarding
   I connected the local port 8080 to the service:
   kubectl port-forward svc/echo-api-service 8080:80
   
   ## Testing the Endpoints
   Greeting Endpoint: curl http://localhost:8080/ 
   Secure Config Endpoint: curl http://localhost:8080/secure-config

2)
   I used port forwarding to map the ClusterIP service to localhost:
   kubectl port-forward svc/echo-api-service 8080:80
   This allowed me to access the application at http://localhost:8080

3)
   ## AI Integration
   I used AI in three specific areas:
   First, AI helped me translate the README to English. I needed the technical commands to be accurate and AI did that well.
   Second, AI helped me with the syntax of the YAML files. For example, I had wrong indentation in the deployment.yaml and AI spotted it and fixed it.
   Third, when I tried to create the .github/workflows folder on Windows, the mkdir command didn't work. AI told me to use New-Item instead and it worked immediately.
   ## Utility Analysis
   AI was most helpful with syntax debugging and YAML formatting. It caught indentation errors that would break the manifests and helped me understand how ConfigMap and          Secret fields need to match the application expectations.
   ## Friction Points
   AI had limitations with the Base64 encoding - it included a newline character that broke the secret. I had to manually test and use the correct echo command.
   ## Future Architectural Outlook
   If I had more time, I would add automated testing in the CI pipeline, create a simple monitoring dashboard to track pod health, and implement automated backups for the        cluster.
