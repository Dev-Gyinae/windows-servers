# Installing Windows Server 2022 with Desktop Experience on VirtualBox

## Prerequisites
- VirtualBox installed
- Windows Server 2022 ISO file
- 4GB RAM for VM
- 50GB storage for VM

## Virtual Machine Setup

### Create VM
- **Name**: `Windows Server 2022`
- **Type**: Microsoft Windows
- **Version**: Windows 2019 (64-bit)
- **RAM**: 4096 MB

### Hard Disk
- **Create virtual hard disk now**
- **File type**: VHD (Virtual Hard Disk)
- **Storage**: Dynamically allocated
- **Size**: 50 GB

### Mount ISO
- Go to **Settings → Storage**
- Click **"Empty"** under Controller: IDE
- Click **CD icon** → **Choose a disk file**
- Select your **Windows Server 2022 ISO**

## Installation

### Boot & Install
1. **Start VM** - boots from ISO automatically
2. Click **"Install Now"**
3. Select **"Windows Server 2022 Standard (Desktop Experience)"**
4. Choose **"Custom: Install Windows only"**
5. Select the **50GB unallocated space**
6. Click **"Next"** - installation begins

### Final Setup
- Set **Administrator password** when prompted
- Login with your credentials
