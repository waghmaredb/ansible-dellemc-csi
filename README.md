# Deploy Multiple VMs, Configure Kubernetes and configure CSI

## Description

Playbook and role to deploy 
- multiple vSphere virtual machines from a template using Ansible. 
- Install and configure Kubernetes on deployed virtual machines
- Install and configure CSI plugin on Kubernetes cluster

## Requirements
* Python (≥ 2.6)
* Ansible (≥ 2.8)
* PyVmomi


## Configuration
The required files are:
```
.
├── ansible.cfg
├── answerfile.yml
├── deploy-kubernetes-prod.yml
├── pmcsi-answerfile.yml
├── README.md
├── roles
│   ├── configure-powermax-csi
│   │   └── tasks
│   │       └── main.yml
│   ├── deploy-k8s-cluster
│   │   └── tasks
│   │       └── main.yml
│   └── deploy-vsphere-template
│       └── tasks
│           └── main.yml
├── test.yml
└── vms-to-deploy

```

1. Edit the ```vms-to-deploy``` file to define the number of virtual machines you want to deploy, as well as their names, datastore, IP and notes.
2. Edit the ```answerfile.yml``` file to set the correct parameter for
    * the infrastructure (where to deploy)
    * the common options for the virtual machines
3. Edit the ```pmcsi-answerfile.yml``` file to set the correct PowerMax CSI parameter.


## Execution

```
ansible-playbook -i vms-to-deploy deploy-kubernetes-prod.yml
```

Enjoy! :)
