# ISTIO-Project
ISTIO, Two Applications, GO AND jAVA APPLICATIONS. Splitted the n/w using service mesh.


Please submit your results via the link provided in the email from your recruiter. There you can upload your files in a zip archive. 

You will find two binaries, one Go based application, one Java-based application. Both are providing an HTTP service with the same endpoints: 
Route 	Description 
/ 	A static site. Should not appear in the final setup as it is but redirect to /hotels. 
/hotels 	JSON object containing hotel search results 
/health 	Exposes the health status of the application 
/ready 	Readiness probe 
/metrics 	Exposes metrics of the application 
  	 
Your Task  
My task is to provide a load balancer setup like the following: 
  
 
The traffic distribution should be as follows: 70% of the requests are going to the application written in Go, 30% of the requests are going to the application written in Java. 
The setup has to be containerized and available as Docker Compose File or Kubernetes 
Additional information: 
•	The applications were built using Go 1.12 (provided as Linux binary) and Java 11 
•	Both applications are binding to all interfaces on port 8080 
•	You don’t have to upload the built Docker images to a registry, we will build them locally 
 
