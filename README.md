# Semaphore
### HELM CHART FOR USE TO KUBERNETES

## Sources

* https://docs.ansible-semaphore.com/
* https://github.com/ansible-semaphore/semaphore

### Before use HELM Chart you need to fill in Custom ConfigMap and Custom Secret on values.yaml

## Install HELM Chart Semaphore

#### Add repo semaphore
```bash
helm repo add semaphore https://raw.githubusercontent.com/mobiservice19/Semaphore/main/charts/semaphore-0.1.0.tgz
```

#### Pull default values from HELM Chart semaphore
```bash
helm show values semaphore > values.yaml
```

#### Install HELM Chart semaphore
```bash
helm install semaphore semaphore -f values.yaml
```

