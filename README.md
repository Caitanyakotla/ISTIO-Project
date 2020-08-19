# ISTIO-Project: ISTIO, Two Applications, GO AND jAVA APPLICATIONS. Splitted the n/w using  Istio service mesh.
Istio - An independent open source service mesh that facilitates the fundamentals needed to work successfully on a Microservice Architecture.

# Securing authentication
# Encrypting the communication among different microservices.
# Securing authorization factors.
  So it turns out to be very useful to develop application level security.
# We built Docker image, deployed it using Kubernetes, and queried our appllication. 

You will find two binaries, one Go based application, one Java-based application. Both are providing an HTTP service with the same endpoints: 
Description 
/ 	A static site. Should not appear in the final setup as it is but redirect to /hotels. 
/hotels 	 JSON object containing hotel search results 
/health 	 Exposes the health status of the application 
/ready 	   Readiness probe 
/metrics   Exposes metrics of the application 
  	 
My task is to provide a load balancer setup like the following: over view of the project.
  
 The traffic distribution should be as follows: 70% of the requests are going to the application written in Go, 30% of the requests are going to the application written in Java. 
The setup has to be containerized and available as Docker Compose File or Kubernetes 
Additional information: 
•	The applications were built using Go 1.12 (provided as Linux binary) and Java 11 
•	Both applications are binding to all interfaces on port 8080 
 
Cloud: Google Cloud Platform(GKE)
