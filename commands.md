#### POD | NIVEL: 1 ####
### Create Simple Pod
$ kubectl run <pod_name> --image=<image_name>:<tag_name> --port=<port_number>
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
### Go to a container especific inside Pod
$ kubectl exec -it <name_pod> -c <name_container> (-- sh, /bin/bash, bash, sh)
### Get logs a container especific inside Pod
$ kubectl logs -f <name_pod> -c <name_container>
### Filter pods with Labels
$ kubectl get pods -l name=<name_config_in_tag_label>

#### REPLICA SET | NIVEL : 2 ####
### DEPLOYMENT | NIVEL : 3 ####
### Get RollOut Deployment
$ kubectl rollout status deploy <name_deployment>
### Show Lables
$ kubectl get (pods, rs, deploy) --show-labels
### Show History Deployment
$ kubectl rollout history deploy <name_deployment>
### Show detail change-cause 
$ kubectl rollout history deploy <name_deployment> --revision=<number_revision>
### Rollback to version stable
$ kubectl rollout undo deploy <name_deployment> --to-revision=<number_revision>

#### SERVICE | NIVEL: 4 ####
### Port forward Service
$ kubectl port-forward (svc, service)/<name_service> <port_host>:<port_service>

#### Aditional ####
### curl not exists
$ apk add -U curl
### filter for custom column
$ kubectl get pods <name_pod> -o custom-columns=ANNOTATIONS:.metadata.annotations
### add command in apply in change-cause
$ kubectl apply -f <file_name.yaml> --record
### Show more details 
$ kubectl get <type_object> -o wide
### List Endpoints of Service
$ kubectl get endpoints -l app=<value_label>




#### Sugest
- Si el runtime de docker (por ejemplo), tiene muchos contenedores en [ps -a], hara que
cubra los gran parte de recursos y los pods quedaran en estado pending o cuando se levanta minikube en modo RBAC (dependera de los recursos de tu computador). Si eso ocurre, solucion a nivel local o prueba:
$ minikube stop && minikube delete
$ docker rm -f $(docker ps -aq)
$ reboot


### AWS CONFIG EKS
$ aws eks --region <region-code> update-kubeconfig --name <cluster_name> --profile <name_profile>