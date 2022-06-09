## Demo using the Trivy operator with FluxCD

To add Flux to your Kubernetes cluster:
```
flux bootstrap github \
  --owner=$GITHUB_USER \
  --repository=flux-example \
  --branch=main \
  --path=./clusters/my-cluster \
  --personal
```

Tell Flux about your app with the following manifests:
```
kubectl apply -f app/flux-resources.yaml
```

Add the observability stack:
```
kubectl apply -f observability
```

Add Trivy for security scanning:
```
kubectl apply -f security
```

Now you can access the Flux dashboard in Grafana 
```
kubectl port-forward 
```