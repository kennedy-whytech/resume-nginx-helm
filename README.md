
helm install resume-nginx-1 . --set servicePort=30001 --set nodePort=30001
helm install resume-nginx-2 . --set servicePort=30002 --set nodePort=30002