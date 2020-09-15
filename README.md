# rancher_ansible
## Forked from [tjayantha/rancher_ansible](https://github.com/tjayantha/rancher_ansible)
Ansible framework to deploy Rancher 2.X

## Prerequisite
Ansible >= 2.8 (Dependacies from modules added in 2.8 version)

## Quick Start
- Installation of Rancher 2.x
- Creation of your first cluster

## Local run
You can check these roles localy. [Vagrant](https://www.vagrantup.com/) and [Virtualbox](https://www.virtualbox.org/) required.
- Start with creating VMs:
    ```shell
    $ vagrant up
    ```
- Run ansible:
    ```
    $ ansible-playbook site.yml
    ```

## Resources
- [Rancher. Manual Quick Start](https://rancher.com/docs/rancher/v2.x/en/quick-start-guide/deployment/quickstart-manual-setup/)
- [Rancher. Deploying Workloads](https://rancher.com/docs/rancher/v2.x/en/quick-start-guide/workload/)
