# super-simple-helm
Very minimalistic helm chart to get started with 

```
helm create mychart
```

creates a chart with a lot of option like ingress, load balancer and service account etc. This one has been trimmed down to only a couple of option for a
101 demo.


### Linting 
```
helm lint ./supersimplechart
```

### Note this needs https://github.com/neilghosh/simple-springboot-k8s to be available in dockerhub

### Install 
```
helm install  ./supersimplechart --generate-name
```

### Install with service override 
```
helm install  ./supersimplechart --set service.type=NodePort --generate-name
```

### Install with custom image 

```
helm helm install  ./supersimplechart --set service.type=NodePort --generate-name --set image.repository=prydonius/todo --set image.tag=1.0.0
```

### Test 
```
helm test supersimplechart-1574596238
```