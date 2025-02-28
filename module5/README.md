# Module 5

`helm list`

```bash
NAME    NAMESPACE               REVISION        UPDATED                                 STATUS          CHART           APP VERSION
iruda   user6cukjd9p6rt3ad0     2               2025-01-22 20:02:16.3774182 +0700 +07   deployed        podinfo-1.0.0   6.6.3
```

`helm get values iruda`

```bash
USER-SUPPLIED VALUES:
redis:
  container:
    useConfigFile: false
```