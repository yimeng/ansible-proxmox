# ansible-proxmox

## step 1
ansible-galaxy role install --force yimeng.proxmox
## step 2
1. cp hosts.template to hosts
2. edit hosts info
## step 3
edit proxmox.yml

## example
```
---
- hosts: proxmox
  remote_user: root
  roles:
  - {
      role: yimeng.proxmox,
      vm_id: 122,
      node_name: "home",
      cd_rom: '{"ide0":"local:iso/CentOS-7-x86_64-Minimal-1804.iso,media=cdrom"}',
      net_work: '{"net0":"virtio,bridge=vmbr0"}',
      hard_disk: '{"virtio0":"WD4T:200"}',
      cpu_cores: 1,
      cpu_vcpus: 2,
      is_update: no,
      state: present,
     }
  #default vars
  - {
      role: yimeng.proxmox,
      vm_id: 122,
      }

```

## enjoy it
