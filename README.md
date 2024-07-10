
## Example project configuration

*devenv.yml*

```yaml
project: "example-service"
default_env: "default"
envs:
  default:
    envvars:
      - ARTIFACTORY_USERNAME
      - ARTIFACTORY_SECRET_TOKEN
    scripts:
      cluster-create:
        description: "Create local kubernetes cluster"
      cluster-delete:
        description: "Delete local kubernetes cluster"
      helm-install:
        description: "Install service helm chart on local cluster"
      helm-uninstall:
        description: "Uninstall service helm chart on local cluster"
```

## Enable devenv

### Enable devenv from project

Enable default devenv

```
devenv enable
```

or enable a specific env

```
devenv enable default
```

### Enable devenv from anywhere else

Enable default devenv

```
devenv enable --remote example-service
```

or enable a specific env

```
devenv enable --remote example-service-default
```

## Define local secrets

```
devenv secret add artifactory.username foo
devenv secret add artifactory.password bar
```

## Map local secrets to project envvars

In project folder

```
devenv map-secret artifactory.username ARTIFACTORY_USERNAME
devenv map-secret artifactory.password ARTIFACTORY_PASSWORD
```
