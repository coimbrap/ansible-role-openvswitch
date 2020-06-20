# Ansible role OVS

Génère un fichier d'interface car les commandes ne sont pas bien supportées par PVE.

### host_vars/pve/ovs.yml
```yaml
#Sans loopback !!
interface_list: [eno1,eno2]

ovs_ports:
  - interface: eno1
    bridge: vmbr0

ovs_bridge:
  - name: vmbr0
    ipv4: '195.14.163.18/24'
    gw4: '195.14.163.1'
  - name: vmbr5
    ipv4: '195.4.163.18/24'
    gw4: '195.4.163.1'
    ipv6: 'fd2e:9d2b:16eb::10/64'
    gw6: 'fd2e:9d2b:16eb::beef'
  - name: vmbr6

ovs_intport:
  - name: opnwan
    bridge: vmbr1
    ipv4: '10.2.0.1/24'
    ipv6: 'fd2e:9d2b:16eb:30::10/64'
    vlan: 10
```

Licence GPLv3 - Auteur Pierre Coimbra pour Elukerio
