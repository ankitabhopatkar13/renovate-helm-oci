# renovate-helm-oci

There is a library chart which acts as a template chart for app1 and app2.

In the [Chart.yaml](https://github.com/ankitabhopatkar13/renovate-helm-oci/blob/main/app1/Chart.yaml#L26) of app1, I have added a dependency pointing to the OCI registry of Github. This package is private and in order to successfully fetch the dependency I perform a `helm registry login -u ankitabhopatkar13 -p $GITHUB_TOKEN ghcr.io/ankitabhopatkar13` command to that registry as pointed out [here](https://helm.sh/docs/topics/registries/#login).

Renovate fails to fetch the dependency for app1 from private registries with the following error - 

```
{
                     "topic": "dependency-name",
                     "message": "Failed to look up dependency dependency-name"
                   }
```

Is there a way in which we can login to helm private oci registries?


Dependencies are defined as -

```
dependencies:
- name: library
  version: 0.1.0
  repository: oci://ghcr.io/ankitabhopatkar13/library
  import-values:
    - defaults
```

Reference: https://helm.sh/docs/topics/registries/#login
