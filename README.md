# MetalLB Ansible role

![Basic role syntax check](https://github.com/nemonik/metallb-role/workflows/Basic%20role%20syntax%20check/badge.svg)

An Ansible role for ensuring the configuration of [MetalLB](https://metallb.universe.tf/).

## Requirements

Requires Kubernetes installed.

## Role Variables

| Variable                | Required | Default               | Choices             | Comments                                         |
|-------------------------|----------|-----------------------|---------------------|--------------------------------------------------|
| metallb_version         | yes      | v0.8.3                | matches release tag | metallb version to install                       |
| images_cache_path       | no       | not defined           | Path                | Path to folder used to cache saved Docker images |            
| cache_container_timeout | no       | 300 seconds           | Integer value       | Number of seconds before Ansible times out       |

## Example Playbook

An example can be found used in my Hands-on DevOps course's [ansible/master-playbook.yml](https://github.com/nemonik/hands-on-DevOps/blob/master/ansible/master-playbook.yml).

```
- hosts: masters
  remote_user: vagrant
  roles:
    - common
    - docker
    - docker-compose
    - k3s-server
    - metallb
```

The above Ansible playbook uses my

- [Common role](https://github.com/nemonik/common-role) to configure the instance past the base CentOS 7, Alpine 3.10 or Ubuntu Bionic image
- [Docker role](https://github.com/nemonik/docker-role) to install and configure Docker
- [Docker-compose role](https://github.com/nemonik/docker-compose-role) to install Docker-compose
- [K3s-server role](https://github.com/nemonik/k3s-server-role) to install Lightweight Kubernetes (K3s)
- [This role](https://github.com/nemonik/metallb-role) to install MetalLB

For more information and to see this role put into action checkout my [Hands-on DevOps class](https://github.com/nemonik/hands-on-DevOps) project.

## License

3-Clause BSD License

## Author Information

Michael Joseph Walsh <mjwalsh@nemonik.com>
