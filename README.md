# kubernetes juju deployment

These are my personal instructions for getting a Juju deployment of Charmed Kubernetes up and running, managed by Rancher 2.x.

## Get MAAS working.
Instructions here.

## Get Juju installed.
Instructions here.

### Modify Juju Constraints Manually:
* juju bootstrap --constraints "mem=3.5G cores=2 root-disk=16G" [controller_name_here]
* juju config kubernetes-worker allow-privileged=true
* juju config kubernetes-master allow-privileged=true
