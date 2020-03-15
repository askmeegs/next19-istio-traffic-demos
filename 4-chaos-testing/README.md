# fault injection 

```
kubectl apply -f .
```

### Open hisptershop in the browser

You should be able to see a list of products: (`frontend -> productcatalog`)

![normal-product-list](screenshots/normal-product-list.png)

But you should see an error on checkout (injected fault for `checkoutservice -> productcatalog` )

![fault-checkout](screenshots/fault-checkout.png)


