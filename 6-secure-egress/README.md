# secure egressgateway for currency API 

# apply egress-gateway.yaml 

Gateway 

Dest Rule 

VS 


# verify that traffic is going through the egressgateway 

```
 stern -l istio=egressgateway -c istio-proxy -n istio-system
```
