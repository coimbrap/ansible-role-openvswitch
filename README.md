# Ansible Role - OpenvSwitch

Ansible role for OpenvSwitch setup in PVE

### Example
```yaml
#No loopback
interface_list: [eno1,eno2]

ovs_ports:
  - interface: eno1
    bridge: vmbr0

ovs_bridge:
  - name: vmbr0
    ipv4: '195.154.163.18/24'
    gw4: '195.154.163.1'
    ports: ['eno1']
  - name: vmbr1
    ports: ['dmz','fw']

ovs_intport:
  - name: fw
    bridge: vmbr1
    ipv4: '10.0.10.1/24'
    vlan: 10
  - name: dmz
    bridge: vmbr1
    ipv4: '10.0.20.1/24'
    vlan: 20
```

### License

GPLv3

### Author Information

Pierre Coimbra
