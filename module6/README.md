# Module 5

Вывод `kubectl get events --field-selector involvedObject.kind=HorizontalPodAutoscaler --sort-by=.lastTimestamp`

```bash
LAST SEEN   TYPE     REASON              OBJECT                                 MESSAGE
22m         Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 3; reason: cpu resource utilization (percentage of request) above target
21m         Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 5; reason: cpu resource utilization (percentage of request) above target
17m         Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 6; reason: cpu resource utilization (percentage of request) above target
6m18s       Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 5; reason: All metrics below target
5m18s       Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 4; reason: All metrics below target
4m18s       Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 3; reason: All metrics below target
3m17s       Normal   SuccessfulRescale   horizontalpodautoscaler/test-app-hpa   New size: 2; reason: All metrics below target
```