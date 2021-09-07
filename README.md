# renovate-helm-oci

There is a library chart which acts as a template chart for app1 and app2.

In the [Chart.yaml](https://github.com/ankitabhopatkar13/renovate-helm-oci/blob/main/app1/Chart.yaml#L26) of app1, I have added a dependency pointing to the OCI registry of Github. This package is private and in order to successfully fetch the dependency I perform a helm login command to that registry as pointed out [here](https://helm.sh/docs/topics/registries/#login).

But renovate fails to fetch the dependency from private registries. Is there a way in which we can login to helm private registries?


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
