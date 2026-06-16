# Troubleshooting Notes

## Issue 1: PCs Could Not Communicate Initially

### Problem

Initial ping tests failed because the PCs did not have IP addresses configured.

### Cause

The PCs were not manually configured and had not received DHCP addresses yet.

### Fix

Configured DHCP pools on R1 and set each PC to use DHCP.

### Verification

Used the following command on R1:

```bash
show ip dhcp binding
```

Result: Admin and Staff PCs received DHCP addresses successfully.

---

## Issue 2: Guest VLAN Could Not Reach Server

### Problem

Guest PC failed to ping the internal server at `192.168.40.10`.

### Cause

This was expected behavior because the Guest VLAN is restricted by an access control list.

### Verification

The Guest PC received the following reply from its default gateway:

```text
Reply from 192.168.30.1: Destination host unreachable.
```

This confirmed that Guest VLAN traffic was blocked from reaching the Server VLAN.

---

## Issue 3: Verified Trunk Configuration

### Problem

Needed to confirm that VLAN traffic was passing correctly between SW1 and R1.

### Verification

Used the following command on SW1:

```bash
show interfaces trunk
```

Result: `Fa0/1` was trunking and allowed VLANs `10, 20, 30, 40, and 99`.

---

## Issue 4: Verified NAT

### Problem

Needed to confirm that internal users were being translated when accessing the ISP/internet network.

### Verification

Used the following command on R1:

```bash
show ip nat translations
```

Result: Internal addresses such as `192.168.10.x` and `192.168.20.x` were translated to the WAN IP address `203.0.113.2`.

---

## Summary

These troubleshooting steps confirmed that VLANs, trunking, DHCP, ACL restrictions, routing, and NAT were working as expected. This documentation demonstrates that the network was not only configured, but also tested and verified.
