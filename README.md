# kubernetes

## Comandos Úteis

### Reiniciar todos os Pods

```bash
kubectl get pods -A | awk '{printf "kubectl delete pod -n %s %s\n",$1,$2}' | sh
```

```bash
kubectl get pods -A | awk '{print $2}' | xargs kubectl delete pod 
```

### Todos os Pods que rodam no Worker ( Node )
```bash
kubectl get pod --all-namespaces -o json | jq '.items[] | .spec.nodeName + " " + .metadata.name'  grep ip-10-100-100-100.sa-east-1.compute.internal
```
