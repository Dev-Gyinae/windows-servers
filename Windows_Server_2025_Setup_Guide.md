# Windows Server 2025 Setup Guide (VirtualBox + Server Core)

This guide documents the process of installing **Windows Server 2025 (Server Core)** on VirtualBox, focusing on the exact issues and solutions encountered during installation.

---

## 1. Create the VirtualBox VM

### Recommended VM Settings

**General**
- OS Type: *Windows 2022 (64‑bit)*

**System → Motherboard**
- Chipset: **PIIX3**
- Enable I/O APIC: **ON**
- Enable EFI: **OFF** (EFI prevented the installer from booting)

**System → Processor**
- CPUs: **2+**
- Execution Cap: 100%
- PAE/NX: **ON**
- Nested Paging: **ON**
- Hyper‑V Paravirtualization: **ON**

**Storage**
- Controller: SATA (AHCI)
- Port 0: `WindowsServer2025.vhd` (VHD works more reliably than VDI)
- Port 1: Windows Server 2025 ISO

**Network**
- NAT or Bridged

---

## 2. Installation Issues & Fixes

### Issue: Disk Not Selectable During Install
If the installer shows:
- Disk 0 Partition 1 (greyed out)

**Fix:**
- Change disk format to **VHD** (VDI caused this issue)
- Confirm SATA controller is set to **AHCI**
- **Disable EFI**

---

## 3. After Installation: SConfig

Windows Server 2025 **Server Core** boots directly into **SConfig**.
This is normal — the GUI is not included.

---

## 4. Basic Networking Check

Use the correct `curl.exe` (only the System32 version works):

```cmd
C:\Windows\System32\curl.exe https://google.com
```

If this returns HTML, networking is functional.

---

## 5. (Removed) Tailscale Installation Section

This section has been removed as Tailscale installation is not functioning correctly on this Server Core build.

---

## Summary

✔ Use **VHD** instead of VDI  
✔ Disable EFI for installation  
✔ Server Core boots into SConfig — this is normal  
✔ Use `C:\Windows\System32\curl.exe` for network tests  

---

If you'd like, this guide can be expanded with:
- Domain controller setup
- Networking additions
- WinRM remote management
- Automation scripts
