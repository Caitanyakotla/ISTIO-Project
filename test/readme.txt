Step 1:
build docker images by bellow commands
docker build --file java-application/Dockerfile java-application --tag java-webserver:v1
docker build --file go-application/Dockerfile go-application --tag go-webserver:v2

step 2:
install istio and setup environment(istioctl binary included in bin directory version: istio-1.4.2)
export PATH=$PWD/bin:$PATH
istioctl manifest apply --set profile=demo

Also ensure corresponding Kubernetes pods are deployed and have a STATUS of Running:
kubectl get pods -n istio-system

When you deploy your application using kubectl apply, the Istio sidecar injector will automatically inject Envoy containers into your application pods if they are started in namespaces labeled with istio-injection=enabled:
kubectl label namespace default istio-injection=enabled

step 3:
kubectl apply -f gateway.yaml
kubectl apply -f deployment.yaml

Check LoadBalancer IP address:
kubectl get services  --all-namespaces  | grep istio-ingressgateway
use port 80 for send requests.
livenessProbe and readinessProbe also included to handle Error cases.

step 4:
delete testsetup by following commands
kubectl delete -f gateway.yaml
kubectl delete -f deployment.yaml
istioctl manifest generate --set profile=demo

		//Dynamic service discovery
		//Load balancing(some % based on on application)
		//TLS termination
		//HTTP/2 and gRPC proxies
		//Circuit breakers
		//Health checks(Liveness probe/ReadinessProbe)
		//Staged rollouts with %-based traffic split()
		//Fault injection
		//Rich metrics(Jaeger) Kiali by using this tool we can control the network.
