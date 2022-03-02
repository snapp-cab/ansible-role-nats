# NATS Ansible Role

![GitHub Workflow Status](https://img.shields.io/github/workflow/status/snapp-incubator/ansible-role-nats/ci?label=ci&logo=github&style=flat-square)

NATS.io is a simple, secure, and high-performance open source messaging system for cloud-native applications, IoT messaging, and microservices architectures.
This ansible role installs it and then provide its configuration.

## Installation

```yaml
# requirments.yaml
- src: git@github.com:snapp-incubator/ansible-role-nats.git
  scm: git
  version: master
  name: nats
```

## Role Variables

```yaml
nats_version: "2.1.6"
nats_host_group: "core"

nats_gateway_host_groups: []

nats_exporter_enabled: "true"
nats_prometheus_exporter_version: "0.6.2"
```

Please note that this ansible provides a cluster installation of NATS so you must group your hosts into the cluster and `nats_host_group` specifies the cluster.

## Example Playbook

```yaml
- hosts: some_servers
  vars:
    nats_version: "2.1.6"
    nats_host_group: "some_servers"
    nats_exporter_enabled: "true"
    nats_prometheus_exporter_version: "0.6.2"
  roles:
    - nats
```
