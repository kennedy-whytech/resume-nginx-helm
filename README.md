# A simple website to host my resume and deployed via K8S Helm. 
Host yours in no time to land your dream job by simply replacing it with your docker image!

## Prerequisite will be docker, helm and a k8s cluster e.g eks, on-prem cluster or just minikube e.g:
```
minikube start
```

Minkube Instllation:
https://minikube.sigs.k8s.io/docs/start/

## Deploy your resume:
```
helm install resume-nginx-1 . --set servicePort=30001 --set nodePort=30001
helm install resume-nginx-2 . --set servicePort=30002 --set nodePort=30002
```

## Feel free to replace the docker image with yours here:
https://github.com/kennedy-whytech/resume-nginx-helm/blob/be93e03a11a4e33b40e7b2708be5ab03aa01c33c/values.yaml#LL8C41-L9C1
