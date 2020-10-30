# Run Influxdb On Kubernetes



1. 添加helm仓库：

```bash
helm repo add influxdata https://helm.influxdata.com/
```

2. 安装：

```bash
helm upgrade --install my-release influxdata/influxdb
```

3. 安装结果：

```bash
[rancher@fs-192-168-108-3 ~]$ helm upgrade --install my-release influxdata/influxdb
Release "my-release" does not exist. Installing it now.
NAME:   my-release
LAST DEPLOYED: Wed Sep 30 11:20:59 2020
NAMESPACE: default
STATUS: DEPLOYED


RESOURCES:
==> v1/ConfigMap
NAME                 DATA  AGE
my-release-influxdb  1     1s


==> v1/Pod(related)
NAME                   READY  STATUS   RESTARTS  AGE
my-release-influxdb-0  0/1    Pending  0         1s


==> v1/Service
NAME                 TYPE       CLUSTER-IP    EXTERNAL-IP  PORT(S)            AGE
my-release-influxdb  ClusterIP  10.43.239.43  <none>       8086/TCP,8088/TCP  1s


==> v1/ServiceAccount
NAME                 SECRETS  AGE
my-release-influxdb  1        1s


==> v1/StatefulSet
NAME                 READY  AGE
my-release-influxdb  0/1    1s




NOTES:
InfluxDB can be accessed via port 8086 on the following DNS name from within your cluster:


  http://my-release-influxdb.default:8086


You can connect to the remote instance with the influx CLI. To forward the API port to localhost:8086, run the following:


  kubectl port-forward --namespace default $(kubectl get pods --namespace default -l app=my-release-influxdb -o jsonpath='{ .items[0].metadata.name }') 8086:8086


You can also connect to the influx CLI from inside the container. To open a shell session in the InfluxDB pod, run the following:


  kubectl exec -i -t --namespace default $(kubectl get pods --namespace default -l app=my-release-influxdb -o jsonpath='{.items[0].metadata.name}') /bin/sh


To view the logs for the InfluxDB pod, run the following:


  kubectl logs -f --namespace default $(kubectl get pods --namespace default -l app=my-release-influxdb -o jsonpath='{ .items[0].metadata.name }')
```

