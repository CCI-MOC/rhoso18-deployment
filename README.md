# RHOSO18 Deployment

The MOC 2.0 uses [RHOSO18](https://docs.redhat.com/en/documentation/red_hat_openstack_services_on_openshift/18.0) to manage bare metal hardware and switch configuration. The OpenStack services used are:

* Ironic
* Neutron

The RHOSO18 deployment is not exposed to the public, and relies upon the MOC firewall for DNS. It is only used by internal MOC 2.0 workflows involved in configuring bare metal.

## Deployment Process

We assume the deployment process can be run from the bastion host used by the [Open Accelerator Infrastructure environment](https://github.com/CCI-MOC/open-accelerator-infra).

1. Run `openshift-ip-install` scripts to install OpenShift 4.18 upon the identified hardware
2. Deploy RHOSO18 operators and configure RHOSO18 environment

## Hosts

### OpenShift Cluster Nodes

| Description         | Machine type | Count |
| ------------------- | ------------ | ----- |
| Control plane nodes | fc830        | 3     |

RHOSO18 requires a running OpenShift 4.18 cluster.

### Networker Nodes

| Description    | Machine type | Count |
| -------------- | ------------ | ----- |
| Networker node | fc830        | 2     |

The recommended RHOSO18 deployment involves two dedicated [networker nodes](https://docs.redhat.com/en/documentation/red_hat_openstack_services_on_openshift/18.0/html-single/configuring_networking_services/index#configure-networker-nodes_rhoso-cfgnet).