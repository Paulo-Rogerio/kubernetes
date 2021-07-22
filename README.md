# kubernetes

## Comandos Úteis

### Reiniciar todos os Pods

```bash
kubectl get pods -A | awk '{printf "kubectl delete pod -n %s %s\n",$1,$2}' | sh
```

```bash
kubectl get pods -A | awk '{print $2}' | xargs kubectl delete pod 
```
