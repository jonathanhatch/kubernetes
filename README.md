# kubernetes rancher deployment

These are my personal instructions for getting a Juju deployment of Charmed Kubernetes up and running, managed by Rancher 2.x.

## Get MAAS working.
Instructions here.

## Get Controller Prepared
1. Fresh instance of Ubuntu 18.04
2. Run ssh-keygen \ cat .ssh/id_rsa.pub
3. Import ssh key into MAAS

## Get nodes prepared
1. Check to make sure storage is setup properly (RAID in MAAS)
2. Create bridges on all nodes using static IP addresses (192.168.1.10, 192.168.1.11) and turn on STP / 0s Delay
3. Deploy machines
4. Run: sudo swapoff -a
5. Run: curl https://releases.rancher.com/install-docker/18.09.2.sh | sh
6. 

### Modify Juju Constraints Manually:
* juju bootstrap --constraints "mem=3.5G cores=2 root-disk=16G" [controller_name_here]
* juju config kubernetes-worker allow-privileged=true
* juju config kubernetes-master allow-privileged=true
