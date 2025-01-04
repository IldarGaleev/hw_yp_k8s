# Module 3

`kubectl get pod`

``` bash
NAME                           READY   STATUS    RESTARTS   AGE  
details-54cd5f87b4-n7j4d       1/1     Running   0          6m14s
details-54cd5f87b4-sk6bg       1/1     Running   0          6m14s
productpage-7d879f569d-52c5q   1/1     Running   0          6m15s
productpage-7d879f569d-nmqq2   1/1     Running   0          6m15s
ratings-cd557f6b4-lxmtn        1/1     Running   0          6m14s
ratings-cd557f6b4-mln7j        1/1     Running   0          6m14s
reviews-v1-69c9797f94-hjbbk    1/1     Running   0          6m13s
reviews-v2-7b96497584-2v2qs    1/1     Running   0          6m13s
reviews-v3-64fb5df4b-qtvbb     1/1     Running   0          6m12s
```

---

`kubectl get svc`

``` bash
NAME          TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE  
details       ClusterIP   10.96.144.240   <none>        9080/TCP   7m34s
productpage   ClusterIP   10.96.185.28    <none>        9080/TCP   7m34s
ratings       ClusterIP   10.96.164.195   <none>        9080/TCP   7m33s
reviews       ClusterIP   10.96.153.163   <none>        9080/TCP   5m9s 
reviews-v1    ClusterIP   10.96.151.230   <none>        9080/TCP   5m9s 
reviews-v2    ClusterIP   10.96.213.141   <none>        9080/TCP   5m9s 
reviews-v3    ClusterIP   10.96.191.130   <none>        9080/TCP   5m8s 
```