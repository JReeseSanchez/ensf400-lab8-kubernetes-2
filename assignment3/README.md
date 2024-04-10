# Following the commands in the same directory as the files to run:

1. 
```bash
$ minikube start
```
2. 
```bash
$ minikube -p ensf400 addons enable ingress
```
3. 
```bash
$ kubectl apply -f .
```
4. 
```bash
$ curl http://$(minikube ip)/
```

**How I Met the Requirements**
1. I addressed the requirements specified in nginx-dep.yaml.
1. By incorporating details from nginx-config-map.yaml, I ensured the configuration map was properly mounted to the nginx configuration in nginx-dep.yaml.
1. In nginx-svc.yaml, I selected pods and exposed the service on port 80.
1. For request redirection to the "/" path to the nginx-svc, I configured nginx-ingress.yaml.
1. I fulfilled the requirements outlined in app-1-dep.yaml, app-1-svc.yaml, app-2-dep.yaml, and app-2-svc.yaml.
1. Utilizing a canary deployment strategy, app-1-ingress.yaml and app-2-ingress.yaml were set up to direct 70% of requests to app-1 and 30% to app-2.
