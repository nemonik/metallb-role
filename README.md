# metallb Ansible role

An Ansible role for ensuring the configuration of a [metallb](https://metallb.universe.tf/).

## Requirements

Requires Docker, [K3s-server-role](https://github.com/nemonik/k3s-server-role) installed.

## Role Variables

| Variable                | Required | Default               | Choices             | Comments                                         |
|-------------------------|----------|-----------------------|---------------------|--------------------------------------------------|
| metallb_version         | yes      | v0.8.3                | matches release tag | metallb version to install                       |
| images_cache_path       | no       | /vagrant/cache/images | Path                | Path to folder used to cache saved Docker images |            

## Example Playbook

An example can be found used in my Hands-on DevOps course's [master-playbook.yml](https://github.com/nemonik/hands-on-DevOps/blob/master/ansible/master-playbook.yml).

```
- hosts: masters
  remote_user: vagrant
  roles:
    - common
    - k3s-server
    - metallb
```

For more information and to see this role put into action checkout my [Hands-on DevOps class](https://github.com/nemonik/hands-on-DevOps) project.

## License

3-Clause BSD License

## Author Information

Michael Joseph Walsh <mjwalsh@nemonik.com>