# Windows Enterprise Homelab

## Overview

Built a small enterprise-style homelab in VMware Workstation based on the responsibilities listed in the Help Desk Technician job description.

The purpose of the lab was to demonstrate hands-on experience with:

* Active Directory
* DNS
* Domain Controllers
* Domain joins
* Windows Server administration
* Group Policy
* Shared folder permissions
* Workstation support
* Enterprise troubleshooting workflows

---

# Environment Built

## Backend / Server Side

### DC01

* Windows Server 2022
* Active Directory Domain Services (AD DS)
* DNS Server
* Domain Controller for:

```text
corp.local
```

### Configurations Completed

* Installed AD DS and DNS
* Promoted server to Domain Controller
* Created domain:

```text
corp.local
```

* Created Organizational Units (OUs)
* Created domain users
* Created security groups
* Configured Group Policy
* Created shared folders and permissions

---

## Frontend / Workstation Side

### CLIENT01

* Windows 11 workstation VM
* Joined to:

```text
corp.local
```

* Authenticated using domain credentials

### Workstation Tasks Simulated

* Domain logins
* Group Policy updates
* Shared drive access testing
* User authentication testing
* Permissions testing
* Workstation/domain troubleshooting

---

# Troubleshooting Performed

## Issue Encountered

CLIENT01 could not contact the Domain Controller during domain join.

## Troubleshooting Steps

1. Used:

```cmd
ipconfig
```

and:

```cmd
ping
```

to test connectivity.

2. Identified that DC01 and CLIENT01 were on different VMware NAT subnets.

3. Verified VMware NAT configuration through Virtual Network Editor.

4. Corrected DC01 static IP configuration to match VMware NAT network.

5. Updated CLIENT01 DNS settings to point to the Domain Controller:

```text
192.168.56.10
```

6. Flushed DNS cache using:

```cmd
ipconfig /flushdns
```

7. Retested connectivity and successfully joined CLIENT01 to the domain.

---

# Active Directory Tasks Completed

* Created Organizational Units:

  * IT
  * HR
  * Finance
  * Users

* Created test users:

  * jsmith
  * adoe
  * slee

* Created security groups:

  * IT_Admins
  * HR_Users
  * VPN_Users

* Added users to appropriate groups.

---

# Shared Folder & Permissions Testing

Created shared folders and configured access using Active Directory security groups.

Example:

```text
\\DC01\ITShare
```

Tested:

* authorized access
* unauthorized access denial
* role-based access control behavior

---

# Group Policy Testing

Configured centralized workstation configuration management through Group Policy.

Examples:

* Desktop wallpaper policy
* Centralized policy deployment
* Forced policy updates using:

```cmd
gpupdate /force
```

---

# Skills Practiced

* VMware virtualization
* Windows Server administration
* Active Directory
* DNS configuration
* Domain joins
* Group Policy
* Shared folder permissions
* Role-based access control
* Windows troubleshooting
* Network troubleshooting
* Static IP configuration
* Command line troubleshooting
* Enterprise workstation support concepts

---

# Screenshots

Screenshots from the build and troubleshooting process will be uploaded throughout the repository.

---

# Goal of Lab

The goal of this lab was to simulate enterprise help desk and Windows administration workflows in a hands-on environment to strengthen practical experience with the technologies and responsibilities listed in the AMERICAN SYSTEMS Help Desk Technician I role.
