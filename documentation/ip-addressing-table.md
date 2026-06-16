# IP Addressing Table

| Device | Interface / VLAN | IP Address | Subnet Mask | Default Gateway | Purpose |
|---|---|---:|---:|---:|---|
| R1 | G0/0.10 | 192.168.10.1 | 255.255.255.0 | N/A | Admin VLAN gateway |
| R1 | G0/0.20 | 192.168.20.1 | 255.255.255.0 | N/A | Staff VLAN gateway |
| R1 | G0/0.30 | 192.168.30.1 | 255.255.255.0 | N/A | Guest VLAN gateway |
| R1 | G0/0.40 | 192.168.40.1 | 255.255.255.0 | N/A | Server VLAN gateway |
| R1 | G0/0.99 | 192.168.99.1 | 255.255.255.0 | N/A | Management VLAN gateway |
| R1 | G0/1 | 203.0.113.2 | 255.255.255.252 | 203.0.113.1 | WAN link to ISP |
| ISP | G0/0 | 203.0.113.1 | 255.255.255.252 | N/A | Link to R1 |
| ISP | G0/1 | 8.8.8.1 | 255.255.255.0 | N/A | Simulated internet network |
| SW1 | VLAN 99 | 192.168.99.2 | 255.255.255.0 | 192.168.99.1 | Switch management |
| Server | NIC | 192.168.40.10 | 255.255.255.0 | 192.168.40.1 | Internal server |
| Internet Server | NIC | 8.8.8.8 | 255.255.255.0 | 8.8.8.1 | Simulated public server |