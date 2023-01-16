# app-maven-kpack-with-subpath

## Creating the Workload

```
tanzu apps workload create app-maven-kpack-with-subpath \
  --namespace dev \
  --git-branch main \
  --git-repo https://github.com/carto-run/app-maven-kpack-with-subpath \
  --label apps.tanzu.vmware.com/has-tests=true \
  --label app.kubernetes.io/part-of=app-maven-kpack-with-subpath \
  --type web \
  --sub-path my-subpath \
  --yes
```

## Logs

```
tanzu apps workload tail app-maven-kpack-with-subpath
```

## Configuration

| Item            | Config                                                                                |
| --------------- | ------------------------------------------------------------------------------------- |
| Scan Policy     | [default](resources/scan-policy.yaml)                                                 |
| Pipeline        | [developer-defined-tekton-pipeline](resources/developer-defined-tekton-pipeline.yaml) |
| tap-values.yaml | na                                                                                    |
| Supply Chain    | source-test-scan-to-url                                                               |

