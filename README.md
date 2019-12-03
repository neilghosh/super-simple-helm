# super-simple-helm
Very minimalistic helm chart to get started with 

```
helm create mychart
```

creates a chart with a lot of option like ingress, load balancer and service account etc. This one has been trimmed down to only a couple of option for a
101 demo.

## Dry Run
```
helm install super-simple-svc ./supersimplechart --dry-run --debug
```

### Linting 
```
helm lint ./supersimplechart
```

### Note this needs https://github.com/neilghosh/simple-springboot-k8s to be available in dockerhub

### Install 
```
helm install super-simple-svc ./supersimplechart 
```

### Install with service override 
```
helm install super-simple-svc ./supersimplechart --set service.type=NodePort
```

### Install with custom image 

```
helm install super-simple-svc ./supersimplechart --set service.type=NodePort --set image.repository=neilghosh/super-simple-svc --set image.tag=v2
```

### Upgrade with new values 
```
helm upgrade super-simple-svc ./supersimplechart --set service.type=NodePort --set image.repository=neilghosh/super-simple-svc --set image.tag=v2
```

### package 
```
helm package supersimplechart
mv supersimplechart-0.1.0.tgz super-simple-chart
helm repo index supersimplechart/ --url https://neilghosh.github.io/super-simple-helm/
helm repo add super-simple-helm https://neilghosh.github.io/super-simple-helm/
helm repo list
helm install super-simple-svc-pkg super-simple-helm/supersimplechart
```

### Test 
```
helm test super-simple-svc
```