
## frontend 


## rollout 

kubectl label namespace default istio-injection=enabled

kubectl apply -f ../hipstershop-default 

kubectl apply -f productcatalog-v2.yaml 

kubectl apply -f destinationrule.yaml 

kubectl apply -f vs-split-traffic.yaml 



## respy 

RESPY_POD=$(kubectl get pod  | grep respy | awk '{ print $1 }') 

kubectl exec -it $RESPY_POD -c respy /bin/sh

watch -n 1 ./respy --u http://frontend:80/version --c 10 --n 100 
