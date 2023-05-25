# A simple website to host my resume and deployed via K8S Helm. 
Host yours in no time to land your dream job by simply replacing it with your docker image!

## Prerequisite will be docker, helm and a k8s cluster e.g eks, on-prem cluster or just minikube e.g:
```
$ minikube start
```

Minkube Instllation:
https://minikube.sigs.k8s.io/docs/start/

## Deploy your resume:
```
$ helm install resume-nginx-1 . --set servicePort=30001 --set nodePort=30001
$ helm install resume-nginx-2 . --set servicePort=30002 --set nodePort=30002
```

## Validate if it has been deployed:

```
$ kubectl get pods
NAME                                        READY   STATUS    RESTARTS   AGE
resume-nginx-1-deployment-d76fc49c8-5k77c   1/1     Running   0          13s

$ kubectl get svc
NAME                     TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)           AGE
kubernetes               ClusterIP   10.96.0.1       <none>        443/TCP           4m4s
resume-nginx-1-service   NodePort    10.109.111.43   <none>        30001:30001/TCP   21s
```

## Visit the website via localhost:30001 accordingly, if you are using a linux machine like ubuntu
If you want to test it with a Mac and Minikube, start the cluster via:
```
$ minikube start --driver=docker
$ helm install resume-nginx-1 . --set servicePort=30001 --set nodePort=30001
$ minikube service resume-nginx-1-service --url
```
## Then, visit localhost:30001 or the output url

## Feel free to replace the docker image with yours here:
https://github.com/kennedy-whytech/resume-nginx-helm/blob/be93e03a11a4e33b40e7b2708be5ab03aa01c33c/values.yaml#LL8C41-L9C1
