# Verification Tests

| Test # | Test Description | Source | Destination | Expected Result | Actual Result |
|---:|---|---|---|---|---|
| 1 | Admin PC received DHCP address | Admin PC | DHCP Server on R1 | Success | Passed |
| 2 | Staff PC received DHCP address | Staff PC | DHCP Server on R1 | Success | Passed |
| 3 | Admin PC ping Staff PC | 192.168.10.21 | 192.168.20.21 | Success | Passed |
| 4 | Staff PC ping Admin PC | 192.168.20.21 | 192.168.10.21 | Success | Passed |
| 5 | Guest PC ping Server | 192.168.30.x | 192.168.40.10 | Fail / blocked | Passed |
| 6 | Admin PC ping ISP router | 192.168.10.21 | 203.0.113.1 | Success | Passed |
| 7 | Admin PC ping internet server | 192.168.10.21 | 8.8.8.8 | Success | Passed |
| 8 | NAT translations visible on R1 | R1 | show ip nat translations | Translations shown | Passed |
| 9 | Default route installed on R1 | R1 | show ip route | 0.0.0.0/0 via ISP | Passed |
| 10 | SSH to SW1 from Admin PC | Admin PC | 192.168.99.2 | Success | Passed |

## Verification Commands Used

```bash
show vlan brief
show interfaces trunk
show ip interface brief
show ip dhcp binding
show ip route
show ip nat translations
show access-lists