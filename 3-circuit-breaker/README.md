# circuit breaker 

```
FORTIO_POD=$(kubectl get pod | grep fortio | awk '{ print $1 }')

kubectl exec -it $FORTIO_POD  -c fortio /usr/bin/fortio -- load -c 2 -qps 0 -n 100 -loglevel Warning http://frontend:80/


kubectl exec -it $FORTIO_POD  -c fortio /usr/bin/fortio -- load -c 3 -qps 0 -n 100 -loglevel Warning http://frontend:80/

kubectl exec -it $FORTIO_POD  -c fortio /usr/bin/fortio -- load -c 10 -qps 0 -n 100 -loglevel Warning http://frontend:80/

```


*observe the # of calls flagged for circuit breaking* 


```
kubectl exec -it $FORTIO_POD  -c istio-proxy  -- sh -c 'curl localhost:15000/stats' | grep frontend | grep pending
```