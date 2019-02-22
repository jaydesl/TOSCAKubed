# TOSCAKubed
## A TOSCA-ADT to Kubernetes-manifest Translation Tool

### Reference for the TOSCA type *tosca.nodes.MiCADO.Container.Application.Docker*

## Supported field names for Docker Container Properties 

|Docker Runtime Option| 0.7.1 | 0.7.2 | Swarm Docker-Compose Name | Kubernetes Manifest (Pod.Spec.Container) Name | TOSCA ADT Name |
|--|:--:|:--:|--|--|--|
| Container Run Command | :heavy_check_mark: | :heavy_check_mark: | entrypoint  | command |*either*|
| Container Arguments | :heavy_check_mark: | :heavy_check_mark: |   command  | args |*either*|
| Container Name | :heavy_check_mark: | :heavy_check_mark: |  container_name  | name |*either*|
| Environment Variables | :heavy_check_mark: | :heavy_check_mark: | environment *(map)* | env *(list)* |*either*|
| Ports| :heavy_check_mark: | :heavy_check_mark: | ports | Service.Spec.ports | ports |
| Container Labels | :heavy_check_mark: | :heavy_check_mark: | labels| Pod.Spec.metadata.labels |*either*|
| Healthcheck | :heavy_check_mark: | :heavy_check_mark: | healthcheck | livenessProbe |livenessProbe|
| Host Network| :x: | :heavy_check_mark: | network_mode | Pod.Spec.hostNetwork |*either*|
| Host PID| :heavy_check_mark: | :heavy_check_mark: | pid | Pod.Spec.hostPID |*either*|
| Shutdown Grace Period | :heavy_check_mark: | :heavy_check_mark: | stop_grace_period | Pod.Spec. terminationGracePeriodSeconds |*either*|
| Allocate a TTY | :heavy_check_mark: | :heavy_check_mark: | tty | tty |*either*|
| Keep STDIN open | :heavy_check_mark: | :heavy_check_mark: | stdin_open | stdin |*either*|

## Supported field names for Kubernetes create interface inputs (Workload creation)

* [Deployment](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#deployment-v1-apps)
* [DaemonSet](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#daemonset-v1-apps)
* [StatefulSet (no volumeClaim functionality)](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#statefulset-v1-apps)
* [Job](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#job-v1-batch)
* [Pod](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#pod-v1-core)

## Supported field names for Kubernetes configure interface inputs (Pod configuration)

* [template.Spec](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.13/#podspec-v1-core)
