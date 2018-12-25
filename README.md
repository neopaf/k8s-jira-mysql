# docker edge

https://docs.docker.com/docker-for-mac/edge-release-notes/
https://download.docker.com/mac/edge/24545/Docker.dmg
включить kubernetes

# kubectl 1.10

https://kubernetes.io/docs/imported/release/#client-binaries
(вместе с docker для mac идёт 1.9 версия, которая не умеет port-forward в service/ делать)

```bash
kubectl proxy &
```

## dashboard

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/recommended/kubernetes-dashboard.yaml
```
http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/

# namespace

```bash
kubectl apply --namespace jira -f mysql
```

# mysql

```bash
kubectl apply --namespace jira -f mysql

rualpe-ws:TeligentTestament paf$ pv mysql-paf-2.gz|gunzip -c |mysql -h0 -P30000 -ujiradb -pjellyfish jiradb
mysql: [Warning] Using a password on the command line interface can be insecure.
 180MiB 0:09:51 [ 312KiB/s] [==================================================================================================================================================================>] 100%            
rualpe-ws:TeligentTestament paf$ 

```
http://localhost:8080/swagger-ui.html

# jira

```bash
kubectl apply --namespace jira -f jira
kubectl patch --namespace jira statefulset jira -p "{\"spec\":{\"template\":{\"metadata\":{\"labels\":{\"date\":\"`date +'%s'`\"}}}}}"
```
