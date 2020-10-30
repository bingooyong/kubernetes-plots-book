# HPA



```bash
kubectl run nginxtest --image=nginx:latest --requests=cpu=200m --expose --port=80
kubectl autoscale deployment nginxtest --cpu-percent=10 --min=1 --max=10
kubectl autoscale deployment nginxtest --cpu-percent=10 --min=1 --max=10
kubectl run nginxtest --image=nginx:latest --requests=cpu=200m --expose --port=80
kubectl autoscale deployment nginxtest --cpu-percent=10 --min=1 --max=10
kubectl get hpa -w
```





# 参考

[Kubernetes基于Metrics Server的HPA](https://www.linuxba.com/archives/8207)