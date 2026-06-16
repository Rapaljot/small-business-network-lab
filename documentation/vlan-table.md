# VLAN Table

| VLAN ID | VLAN Name | Subnet | Gateway | Assigned Ports | Purpose |
|---:|---|---:|---:|---|---|
| 10 | Admin | 192.168.10.0/24 | 192.168.10.1 | Fa0/2 - Fa0/3 | Admin users |
| 20 | Staff | 192.168.20.0/24 | 192.168.20.1 | Fa0/4 - Fa0/5 | Staff users |
| 30 | Guest | 192.168.30.0/24 | 192.168.30.1 | Fa0/6 - Fa0/7 | Guest users |
| 40 | Servers | 192.168.40.0/24 | 192.168.40.1 | Fa0/8 | Internal server |
| 99 | Management | 192.168.99.0/24 | 192.168.99.1 | SVI only | Device management |

## Trunk Port

| Switch | Port | Connected To | Mode | Allowed VLANs |
|---|---|---|---|---|
| SW1 | Fa0/1 | R1 G0/0 | 802.1Q trunk | 10, 20, 30, 40, 99 |