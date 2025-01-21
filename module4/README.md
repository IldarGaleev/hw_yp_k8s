# Module 4
`kubectl get pod`

```
NAME                         READY   STATUS    RESTARTS   AGE  
nginx-cdn-5c477988cc-cx4jv   1/1     Running   0          8m34s
```
---
`kubectl events`

<details>
<summary>stdout</summary>

```
LAST SEEN               TYPE      REASON               OBJECT                                  MESSAGE
4m32s                   Normal    ScalingReplicaSet    Deployment/nginx-cdn                    Scaled up replica set nginx-cdn-5c477988cc to 1
4m32s                   Normal    SuccessfulCreate     ReplicaSet/nginx-cdn-5c477988cc         Created pod: nginx-cdn-5c477988cc-cx4jv
4m32s                   Normal    Scheduled            Pod/nginx-cdn-5c477988cc-cx4jv          Successfully assigned user6cukjd9p6rt3ad0/nginx-cdn-5c477988cc-cx4jv to cl1jepu1h9j5n3g00iug-ywol
4m31s                   Normal    Started              Pod/nginx-cdn-5c477988cc-cx4jv          Started container nginx-cdn-init
4m31s                   Normal    Created              Pod/nginx-cdn-5c477988cc-cx4jv          Created container nginx-cdn-init
4m31s                   Normal    Pulled               Pod/nginx-cdn-5c477988cc-cx4jv          Successfully pulled image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest" in 204ms (204ms including waiting). Image size: 36345415 bytes.
4m31s                   Normal    Pulling              Pod/nginx-cdn-5c477988cc-cx4jv          Pulling image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest"
4m30s                   Normal    Pulling              Pod/nginx-cdn-5c477988cc-cx4jv          Pulling image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest"
4m29s                   Normal    Started              Pod/nginx-cdn-5c477988cc-cx4jv          Started container nginx-cdn
4m29s                   Normal    Pulled               Pod/nginx-cdn-5c477988cc-cx4jv          Successfully pulled image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest" in 188ms (188ms including waiting). Image size: 36345415 bytes.
4m29s                   Normal    Created              Pod/nginx-cdn-5c477988cc-cx4jv          Created container nginx-cdn
4m19s                   Normal    CreateCertificate    Ingress/nginx-cdn                       Successfully created Certificate "nginx-cdn-secret"
4m18s                   Normal    cert-manager.io      CertificateRequest/nginx-cdn-secret-1   Certificate request has been approved by cert-manager.io
4m18s                   Normal    WaitingForApproval   CertificateRequest/nginx-cdn-secret-1   Not signing CertificateRequest until it is Approved
4m18s                   Normal    OrderCreated         CertificateRequest/nginx-cdn-secret-1   Created Order resource user6cukjd9p6rt3ad0/nginx-cdn-secret-1-620555128
4m18s                   Normal    WaitingForApproval   CertificateRequest/nginx-cdn-secret-1   Not signing CertificateRequest until it is Approved
4m18s                   Normal    Issuing              Certificate/nginx-cdn-secret            Issuing certificate as Secret does not exist
4m18s                   Normal    Generated            Certificate/nginx-cdn-secret            Stored new private key in temporary Secret resource "nginx-cdn-secret-mx47c"
4m18s                   Normal    Requested            Certificate/nginx-cdn-secret            Created new CertificateRequest resource "nginx-cdn-secret-1"
4m18s                   Normal    WaitingForApproval   CertificateRequest/nginx-cdn-secret-1   Not signing CertificateRequest until it is Approved
4m18s                   Normal    WaitingForApproval   CertificateRequest/nginx-cdn-secret-1   Not signing CertificateRequest until it is Approved
4m18s                   Normal    WaitingForApproval   CertificateRequest/nginx-cdn-secret-1   Not signing CertificateRequest until it is Approved
4m16s                   Normal    CertificateIssued    CertificateRequest/nginx-cdn-secret-1   Certificate fetched from issuer successfully
4m16s                   Normal    Issuing              Certificate/nginx-cdn-secret            The certificate has been successfully issued
4m16s                   Normal    Complete             Order/nginx-cdn-secret-1-620555128      Order completed successfully
4m11s (x2 over 4m19s)   Normal    Sync                 Ingress/nginx-cdn                       Scheduled for sync
4m11s (x2 over 4m19s)   Normal    Sync                 Ingress/nginx-cdn                       Scheduled for sync
4m11s (x2 over 4m19s)   Normal    Sync                 Ingress/nginx-cdn                       Scheduled for sync
4m11s (x2 over 4m19s)   Normal    Sync                 Ingress/nginx-cdn                       Scheduled for sync
```
</details>

---

`kubectl describe pod/nginx-cdn-5c477988cc-cx4jv`

<details>
<summary>stdout</summary>

```
Name:             nginx-cdn-5c477988cc-cx4jv
Namespace:        user6cukjd9p6rt3ad0
Priority:         0
Service Account:  default
Node:             cl1jepu1h9j5n3g00iug-ywol/10.129.0.25
Start Time:       Wed, 15 Jan 2025 11:24:48 +0700      
Labels:           app=nginx-cdn
                  pod-template-hash=5c477988cc
Annotations:      <none>
Status:           Running
IP:               10.112.134.50
IPs:
  IP:           10.112.134.50
Controlled By:  ReplicaSet/nginx-cdn-5c477988cc
Init Containers:
  nginx-cdn-init:
    Container ID:  containerd://61790316f97fc66d01a71281b58a212396fc94b18eb71e48a64eef1ae7fb4e11
    Image:         cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest
    Image ID:      cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn@sha256:689448a093acba97d4cdf8294acc14cc48af77a0a951972339787700023819b7
    Port:          <none>
    Host Port:     <none>
    Command:
      ./start.sh
    State:          Terminated
      Reason:       Completed
      Exit Code:    0
      Started:      Wed, 15 Jan 2025 11:24:49 +0700
      Finished:     Wed, 15 Jan 2025 11:24:50 +0700
    Ready:          True
    Restart Count:  0
    Limits:
      cpu:     500m
      memory:  128Mi
    Requests:
      cpu:     500m
      memory:  128Mi
    Environment:
      URL:  <set to the key 'fileUrl' of config map 'nginx-cdn-config'>  Optional: false
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-7khnb (ro)
      /var/www/html/ from shared-data (rw)
Containers:
  nginx-cdn:
    Container ID:  containerd://91aa610c6b8a7392445e53675d07a8215bf78429e8d1aefc26f0a003cb16b64d
    Image:         cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest
    Image ID:      cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn@sha256:689448a093acba97d4cdf8294acc14cc48af77a0a951972339787700023819b7
    Port:          80/TCP
    Host Port:     0/TCP
    Command:
      /usr/sbin/nginx
    Args:
      -g daemon off;
    State:          Running
      Started:      Wed, 15 Jan 2025 11:24:51 +0700
    Ready:          True
    Restart Count:  0
    Limits:
      cpu:     500m
      memory:  128Mi
    Requests:
      cpu:        500m
      memory:     128Mi
    Liveness:     http-get http://:80/ delay=0s timeout=1s period=10s #success=1 #failure=3
    Readiness:    http-get http://:80/.done delay=0s timeout=1s period=60s #success=1 #failure=5
    Environment:  <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-7khnb (ro)
      /var/www/html/ from shared-data (rw)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True
  Initialized                 True
  Ready                       True
  ContainersReady             True
  PodScheduled                True
Volumes:
  shared-data:
    Type:       EmptyDir (a temporary directory that shares a pod's lifetime)
    Medium:
    SizeLimit:  <unset>
  kube-api-access-7khnb:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   Guaranteed
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  14m   default-scheduler  Successfully assigned user6cukjd9p6rt3ad0/nginx-cdn-5c477988cc-cx4jv to cl1jepu1h9j5n3g00iug-ywol
  Normal  Pulling    14m   kubelet            Pulling image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest"
  Normal  Pulled     14m   kubelet            Successfully pulled image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest" in 204ms (204ms including waiting). Image size: 
36345415 bytes.
  Normal  Created    14m   kubelet            Created container nginx-cdn-init
  Normal  Started    14m   kubelet            Started container nginx-cdn-init
  Normal  Pulling    14m   kubelet            Pulling image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest"
  Normal  Pulled     14m   kubelet            Successfully pulled image "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest" in 188ms (188ms including waiting). Image size: 
36345415 bytes.
  Normal  Created    14m   kubelet            Created container nginx-cdn
  Normal  Started    14m   kubelet            Started container nginx-cdn
```
</details>

---

`kubectl get po nginx-cdn-5c477988cc-cx4jv -o json`

<details>
<summary>json</summary>

```json
{
    "apiVersion": "v1",
    "kind": "Pod",
    "metadata": {
        "creationTimestamp": "2025-01-15T04:24:48Z",
        "generateName": "nginx-cdn-5c477988cc-",
        "labels": {
            "app": "nginx-cdn",
            "pod-template-hash": "5c477988cc"
        },
        "name": "nginx-cdn-5c477988cc-cx4jv",
        "namespace": "user6cukjd9p6rt3ad0",
        "ownerReferences": [
            {
                "apiVersion": "apps/v1",
                "blockOwnerDeletion": true,
                "controller": true,
                "kind": "ReplicaSet",
                "name": "nginx-cdn-5c477988cc",
                "uid": "3dc1d27f-04cc-4d52-a818-233041ea384a"
            }
        ],
        "resourceVersion": "66318335",
        "uid": "faed78b7-3529-4b6b-b464-834cf3ae524d"
    },
    "spec": {
        "containers": [
            {
                "args": [
                    "-g daemon off;"
                ],
                "command": [
                    "/usr/sbin/nginx"
                ],
                "image": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest",
                "imagePullPolicy": "Always",
                "lifecycle": {
                    "preStop": {
                        "exec": {
                            "command": [
                                "/usr/sbin/nginx",
                                "-s",
                                "quit"
                            ]
                        }
                    }
                },
                "livenessProbe": {
                    "failureThreshold": 3,
                    "httpGet": {
                        "path": "/",
                        "port": 80,
                        "scheme": "HTTP"
                    },
                    "periodSeconds": 10,
                    "successThreshold": 1,
                    "timeoutSeconds": 1
                },
                "name": "nginx-cdn",
                "ports": [
                    {
                        "containerPort": 80,
                        "protocol": "TCP"
                    }
                ],
                "readinessProbe": {
                    "failureThreshold": 5,
                    "httpGet": {
                        "path": "/.done",
                        "port": 80,
                        "scheme": "HTTP"
                    },
                    "periodSeconds": 60,
                    "successThreshold": 1,
                    "timeoutSeconds": 1
                },
                "resources": {
                    "limits": {
                        "cpu": "500m",
                        "memory": "128Mi"
                    },
                    "requests": {
                        "cpu": "500m",
                        "memory": "128Mi"
                    }
                },
                "terminationMessagePath": "/dev/termination-log",
                "terminationMessagePolicy": "File",
                "volumeMounts": [
                    {
                        "mountPath": "/var/www/html/",
                        "name": "shared-data"
                    },
                    {
                        "mountPath": "/var/run/secrets/kubernetes.io/serviceaccount",
                        "name": "kube-api-access-7khnb",
                        "readOnly": true
                    }
                ]
            }
        ],
        "dnsPolicy": "ClusterFirst",
        "enableServiceLinks": true,
        "initContainers": [
            {
                "command": [
                    "./start.sh"
                ],
                "env": [
                    {
                        "name": "URL",
                        "valueFrom": {
                            "configMapKeyRef": {
                                "key": "fileUrl",
                                "name": "nginx-cdn-config"
                            }
                        }
                    }
                ],
                "image": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest",
                "imagePullPolicy": "Always",
                "name": "nginx-cdn-init",
                "resources": {
                    "limits": {
                        "cpu": "500m",
                        "memory": "128Mi"
                    },
                    "requests": {
                        "cpu": "500m",
                        "memory": "128Mi"
                    }
                },
                "terminationMessagePath": "/dev/termination-log",
                "terminationMessagePolicy": "File",
                "volumeMounts": [
                    {
                        "mountPath": "/var/www/html/",
                        "name": "shared-data"
                    },
                    {
                        "mountPath": "/var/run/secrets/kubernetes.io/serviceaccount",
                        "name": "kube-api-access-7khnb",
                        "readOnly": true
                    }
                ]
            }
        ],
        "nodeName": "cl1jepu1h9j5n3g00iug-ywol",
        "preemptionPolicy": "PreemptLowerPriority",
        "priority": 0,
        "restartPolicy": "Always",
        "schedulerName": "default-scheduler",
        "securityContext": {},
        "serviceAccount": "default",
        "serviceAccountName": "default",
        "terminationGracePeriodSeconds": 30,
        "tolerations": [
            {
                "effect": "NoExecute",
                "key": "node.kubernetes.io/not-ready",
                "operator": "Exists",
                "tolerationSeconds": 300
            },
            {
                "effect": "NoExecute",
                "key": "node.kubernetes.io/unreachable",
                "operator": "Exists",
                "tolerationSeconds": 300
            }
        ],
        "volumes": [
            {
                "emptyDir": {},
                "name": "shared-data"
            },
            {
                "name": "kube-api-access-7khnb",
                "projected": {
                    "defaultMode": 420,
                    "sources": [
                        {
                            "serviceAccountToken": {
                                "expirationSeconds": 3607,
                                "path": "token"
                            }
                        },
                        {
                            "configMap": {
                                "items": [
                                    {
                                        "key": "ca.crt",
                                        "path": "ca.crt"
                                    }
                                ],
                                "name": "kube-root-ca.crt"
                            }
                        },
                        {
                            "downwardAPI": {
                                "items": [
                                    {
                                        "fieldRef": {
                                            "apiVersion": "v1",
                                            "fieldPath": "metadata.namespace"
                                        },
                                        "path": "namespace"
                                    }
                                ]
                            }
                        }
                    ]
                }
            }
        ]
    },
    "status": {
        "conditions": [
            {
                "lastProbeTime": null,
                "lastTransitionTime": "2025-01-15T04:24:49Z",
                "status": "True",
                "type": "PodReadyToStartContainers"
            },
            {
                "lastProbeTime": null,
                "lastTransitionTime": "2025-01-15T04:24:50Z",
                "status": "True",
                "type": "Initialized"
            },
            {
                "lastProbeTime": null,
                "lastTransitionTime": "2025-01-15T04:24:52Z",
                "status": "True",
                "type": "Ready"
            },
            {
                "lastProbeTime": null,
                "lastTransitionTime": "2025-01-15T04:24:52Z",
                "status": "True",
                "type": "ContainersReady"
            },
            {
                "lastProbeTime": null,
                "lastTransitionTime": "2025-01-15T04:24:48Z",
                "status": "True",
                "type": "PodScheduled"
            }
        ],
        "containerStatuses": [
            {
                "containerID": "containerd://91aa610c6b8a7392445e53675d07a8215bf78429e8d1aefc26f0a003cb16b64d",
                "image": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest",
                "imageID": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn@sha256:689448a093acba97d4cdf8294acc14cc48af77a0a951972339787700023819b7",
                "lastState": {},
                "name": "nginx-cdn",
                "ready": true,
                "restartCount": 0,
                "started": true,
                "state": {
                    "running": {
                        "startedAt": "2025-01-15T04:24:51Z"
                    }
                }
            }
        ],
        "hostIP": "10.129.0.25",
        "hostIPs": [
            {
                "ip": "10.129.0.25"
            }
        ],
        "initContainerStatuses": [
            {
                "containerID": "containerd://61790316f97fc66d01a71281b58a212396fc94b18eb71e48a64eef1ae7fb4e11",
                "image": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn:latest",
                "imageID": "cr.yandex/crpcqt038mmskd2ime3g/nginx_cdn@sha256:689448a093acba97d4cdf8294acc14cc48af77a0a951972339787700023819b7",
                "lastState": {},
                "name": "nginx-cdn-init",
                "ready": true,
                "restartCount": 0,
                "started": false,
                "state": {
                    "terminated": {
                        "containerID": "containerd://61790316f97fc66d01a71281b58a212396fc94b18eb71e48a64eef1ae7fb4e11",
                        "exitCode": 0,
                        "finishedAt": "2025-01-15T04:24:50Z",
                        "reason": "Completed",
                        "startedAt": "2025-01-15T04:24:49Z"
                    }
                }
            }
        ],
        "phase": "Running",
        "podIP": "10.112.134.50",
        "podIPs": [
            {
                "ip": "10.112.134.50"
            }
        ],
        "qosClass": "Guaranteed",
        "startTime": "2025-01-15T04:24:48Z"
    }
}
```
</details>