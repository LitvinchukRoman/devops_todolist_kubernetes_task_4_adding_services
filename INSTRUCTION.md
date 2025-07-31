To create pods/services/namespace you should firstly run command:
```
kubectl apply -f <fileanme>
```

Then depends on service type you should test it in different ways:

For ClusterIp:

1. After running pods and all manifests you connect to pod and run curl:
```
kubectl -n <namespace> exec -it <pod> -- sh
```
2. Run command in container:
```
curl http://<servicename>.<namespace>.svc.cluster.local
```
3. Aftervards you can find this query in pods logs using comand:
```
kubectl logs <selector of pods>
```
This will show us that traffic is balancing.

For NodePort:

1. You should enter the browser and type in line:
```
http://localhost:<NodePort>
```