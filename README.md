# Semaphore
###
![GitHub last commit](https://img.shields.io/github/last-commit/mobiservice19/Semaphore)
![GitHub repo size](https://img.shields.io/github/repo-size/mobiservice19/Semaphore)


### HELM CHART FOR USE TO KUBERNETES

## Sources

* https://docs.ansible-semaphore.com/
* https://github.com/ansible-semaphore/semaphore

### Before use HELM Chart you need to fill in Custom ConfigMap and Custom Secret on values.yaml

## Install HELM Chart Semaphore

#### Add repo semaphore
```bash
helm repo add semaphore https://raw.githubusercontent.com/mobiservice19/Semaphore/main/charts
```

#### HELM REPO UPDATE
```bash
helm repo update
```
#### HELM SEARCH
```bash
helm search repo | grep semaphore
```

#### Pull default values from HELM Chart semaphore
```bash
helm show values semaphore/semaphore > values.yaml
```

#### Install HELM Chart semaphore
```bash
helm upgrade semaphore semaphore/semaphore \
    --install \
    --atomic \
    --values values.yaml \
    --debug
```
