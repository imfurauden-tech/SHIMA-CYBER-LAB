# 01 — Network Fundamentals Lab

## Status

**Preparation**

The lab will use **VMware Workstation Pro**. No virtual networks or virtual machines are claimed as configured until the validation evidence below is added.

## Objective

Build and document a small, isolated virtual network that makes IP addressing, routing, DNS, TCP, and packet capture observable. This becomes the foundation for later Linux, Windows Server, Active Directory, SOC/SIEM, and incident-response work.

## Scope and safe-use boundary

Only lab-owned virtual machines and a dedicated virtual network are in scope.

- Do not bridge vulnerable or experimental virtual machines to the home, school, work, or public network.
- Do not scan, test, or capture traffic from networks or systems outside the lab.
- Keep shared folders, drag-and-drop, clipboard sharing, USB passthrough, and host-device access disabled unless there is a documented need.
- Take a VMware snapshot before material configuration changes.

## Proposed Architecture

This is the target design, not evidence of a completed implementation.

```text
Host computer
  └── VMware Workstation Pro
        └── VMnet10 — shima-lab-internal
              Host-only network: 172.22.10.0/24
              VMware DHCP: disabled

              └── lab-linux-01
                    Ubuntu Server LTS
                    Planned static address: 172.22.10.10/24
```

A host-only network allows the host and lab VM to communicate without exposing the VM to the physical LAN or Internet. The subnet and adapter name may change if they conflict with an existing local network; record the final choice here before continuing.

## Build Checklist

### 1. Verify VMware readiness

- [ ] Record host operating-system version, available RAM, CPU cores, and free disk space.
- [ ] Confirm VMware Workstation Pro opens successfully.
- [ ] Confirm virtualisation is enabled in firmware if VMware reports an error.
- [ ] Choose a storage location for VM files and snapshots.

### 2. Create the isolated network

- [ ] Open **Edit → Virtual Network Editor** with administrator rights if prompted.
- [ ] Create or select an unused **host-only** adapter, proposed as `VMnet10`.
- [ ] Set the subnet to `172.22.10.0/24` unless it conflicts with another local route.
- [ ] Disable VMware DHCP so the lab addresses are deliberate and documented.
- [ ] Capture a sanitised screenshot of the final virtual-network settings.

### 3. Create the first VM

- [ ] Obtain an Ubuntu Server LTS ISO from the official Ubuntu source.
- [ ] Create `lab-linux-01`; start with conservative resources suited to the host.
- [ ] Attach its network adapter only to `shima-lab-internal` / `VMnet10`.
- [ ] Install and patch the operating system.
- [ ] Set the planned static IP address and record the exact configuration.
- [ ] Create a VMware snapshot named `baseline-patched`.

### 4. Validate and observe

- [ ] Record `ip addr` and `ip route` output after redacting anything outside the lab.
- [ ] Validate host-to-VM connectivity using the VM's lab address.
- [ ] Capture and explain one ICMP exchange and one TCP connection in Wireshark.
- [ ] Explain source IP, destination IP, protocol, ports, and TCP flags observed.
- [ ] Document one problem encountered and how it was resolved.

## Evidence to Add

| Evidence | Purpose |
|---|---|
| Sanitised topology diagram | Shows the isolation boundary and address plan. |
| VMware virtual-network screenshot | Proves the chosen network mode. |
| Guest IP and route output | Verifies addressing and routing. |
| Wireshark screenshots | Demonstrates packet-level understanding. |
| Snapshot name and baseline notes | Establishes a recoverable starting point. |

## Security Considerations

The first control is isolation. A host-only network deliberately prevents the lab VM from reaching the physical LAN and Internet by default. This reduces accidental exposure while still allowing controlled host-to-VM testing.

Before later projects introduce Windows Server, Active Directory, vulnerable services, or security tools, this network design must be reviewed and the scope updated.

## Next Milestone

Complete **Verify VMware readiness** and provide the host computer's available RAM, CPU cores, free disk space, and operating-system version. Resource sizing will then be chosen for `lab-linux-01` without guessing.
