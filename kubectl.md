# Kubectl Cheatsheet

>Disclaimer: This cheatsheet is summarized from personal experience and other online tutorials. It should not be considered as an official reference.

```bash
kubectl config view | grep current-context                                                                                      # Get current kubernetes context
kubectl exec -i [pod-name] -- psql -U [postgres-user] -d [database-name] < [database-dump-file]                                 # Import database from file into pod
kubectl exec [pod-name] -- bash -c "pg_dump -U [postgres-user] [database-name]" > [database-dump-file]                          # Export database from pod into file
kubectl delete po $(kubectl get pods | grep "name-of-cronjob" | awk '{print $1}')                                               # Batch delete pods
kubectl cp <some-namespace>/<some-pod>:/tmp/foo /tmp/bar                                                                        # Copy /tmp/foo from a remote pod to /tmp/bar locally
kubectl cp /tmp/foo <some-namespace>/<some-pod>:/tmp/bar                                                                        # Copy /tmp/foo local file to /tmp/bar in a remote pod in namespace
kubectl run -it --rm --image=mysql:5.7 --restart=Never mysql-client -- bash                                                     # Launch a MySQL pod with interactive bash shell that delets itself on exit
kubectl rollout undo deployment/nginx-deployment --to-revision=2                                                                # Rollback a deployment
kubectl rollout history deployment/eapi                                                                                         # View deployment history
kubectl patch cronjob icarasia-cms-generate-bg-img-cronjob -p '{"spec" : {"suspend" : true }}'                                  # Suspend a cronjob
for pod in $(kubectl get pods -n monitoring | grep Evicted | awk '{print $1}'); do kubectl delete pod $pod -n monitoring; done  # Loop through all pods with status Evicted and delete
kubectl patch deployment lapi-fresque -p '{"spec":{"template":{"metadata":{"labels":{"date":"1611115940"}}}}}'                  # Patch a deployment
kubectl rollout restart deployment capi                                                                                         # Restart all pods in a deployment
kubectl get pods --all-namespaces -o=json | jq -c '.items[] | {name: .metadata.name, namespace: .metadata.namespace, claimName: .spec |  select( has ("volumes") ).volumes[] | select( has ("persistentVolumeClaim") ).persistentVolumeClaim.claimName }'                                                                                             # Get all pods with a PVC attached
kubectl get po -o custom-columns="Name:metadata.name,CPU-limit:spec.containers[*].resources.limits.cpu"                         # Get cpu limits of all pods in default namespace
kubectl get pods -o=jsonpath='{range .items[*]}{.metadata.name}{"\t"}{.spec.containers[].resources.limits.cpu}{"\n"}{end}'      # Get cpu limits of all pods in default namespace
kubectl describe nodes | grep 'Name:\|  cpu\|  memory'                                                                          # Get current cpu and memory allocation from all nodes in cluter
kubectl get events --sort-by=.metadata.creationTimestamp                                                                        # Get events sorted by time stamp
```