# Ansible Role: Ceph Mon

This role bootstraps the Ceph cluster on the first monitor node and prepares the control plane.

## Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `ceph_cluster_network` | CIDR for OSD replication network | `10.10.10.0/24` |
| `ceph_public_network` | CIDR for Client network | `192.168.1.0/24` |
| `ceph_dashboard_user` | Initial Dashboard User | `admin` |
| `ceph_dashboard_password` | Initial Dashboard Password | `admin` |
| `ceph_mon_group` | Inventory group name for monitors | `mons` |

## Dependencies

- `ceph-prerequisites`

## Usage Example

```yaml
- hosts: mons
  roles:
    - role: ceph-mon
      vars:
        ceph_cluster_network: "192.168.100.0/24"
```
