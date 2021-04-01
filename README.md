# my-helm-chart
---

## Pre-requisites:
- [helm 3.x installed](https://helm.sh/docs/intro/install/) - Happy helming!


## Considerations:
- default values are in ```./mychart/values.yaml```
- you could create your customize parameters ``` svc-a.values.yaml```

## Usage:

### Fisrt Deployment
```
#> kubectl config set-context --current --namespace=my-namespace
#> helm install -f [path-to-customize-values.yaml] [Release Name] ./mychart
```

### Update Deployment
- customize your values in your ```customize-values.yaml```
```
#> helm upgrade -f [path-to-customize-values.yaml] [Release Name] ./mychart
```
- or you could pass new parameter using the option ```--set foo=bar```
example:
```
#> helm upgrade [Release Name] ./mychart --set image.repository=redis
```


## Clean up

```
#> helm uninstall [deployment-name]
```

