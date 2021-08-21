#### POD ####
### Create Simple Pod
$ kubectl create <name_pod> --image=<image_name>:<tag_name> --port=<port_number>
### Get logs of Pod
$ kubectl logs -f <name_pod>
### Delete One Pod
$ kubectl delete pod <name_pod>
### List Pods
$ kubectl get pods
### List Pods Especific
$ kubectl get pod <name_pod>
### Describe One Pod
$ kubectl describe pod <name_pod>
### Output Pod format Json (Manifest)
$ kubectl get pod <name_pod> -o json
### Output Pod format Yaml (Manifest)
$ kubectl get pod <name_pod> -o yaml
### Port forward Pod
$ kubectl port-forward <name_pod> <port_host>:<port_container>
### Execute command inside Pod
$ kubectl exec -it <name_pod> (-- sh, /bin/bash, bash, sh)
### Get List of Resource API k8s
$ kubectl api-resources