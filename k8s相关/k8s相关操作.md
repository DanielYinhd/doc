kubectl get namespaces

expose端口
-n命名空间
--type=NodePort公网端口

### gateway层抛公网端口
```
kubectl expose -n ns-prod deployment prod-gw-oauth --port=3000 --type=NodePort
```

### bff层不需要抛公网端口
```
kubectl expose -n ns-prod deployment prod-bff-oauth --port=3101
```