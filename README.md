# Azure VM Start/Stop Automation with PowerShell

## Overview
This project automates the starting and stopping of Azure virtual machines based on Azure tags using PowerShell.

It is useful for managing dev/test VMs that do not need to run 24/7, helping reduce cloud costs and manual effort.

---

## Features
- Start Azure VMs by tag
- Stop Azure VMs by tag
- Supports Azure tenant and subscription targeting
- Supports `-WhatIf` for safe dry-run testing
- Skips VMs that are already in the desired state
- Uses reusable parameters instead of hardcoded values

---

## Project Structure
```text
azure-vm-automation/
├── scripts/
│   ├── start-vms-by-tag.ps1
│   └── stop-vms-by-tag.ps1
└── README.md
```

---

## Prerequisites
Before running the scripts, ensure you have:

- PowerShell 7
- Azure PowerShell module installed (`Az`)
- An Azure account with access to the target subscription
- Azure VMs tagged appropriately

---

## Example Tag
```text
Tag Name: Environment
Tag Value: Dev
```

---

## Usage

### Stop VMs
```powershell
./stop-vms-by-tag.ps1 -TenantId "YOUR-TENANT-ID" -SubscriptionId "YOUR-SUBSCRIPTION-ID" -TagName "Environment" -TagValue "Dev"
```

### Stop VMs (Dry Run)
```powershell
./stop-vms-by-tag.ps1 -TenantId "YOUR-TENANT-ID" -SubscriptionId "YOUR-SUBSCRIPTION-ID" -TagName "Environment" -TagValue "Dev" -WhatIf
```

---

### Start VMs
```powershell
./start-vms-by-tag.ps1 -TenantId "YOUR-TENANT-ID" -SubscriptionId "YOUR-SUBSCRIPTION-ID" -TagName "Environment" -TagValue "Dev"
```

### Start VMs (Dry Run)
```powershell
./start-vms-by-tag.ps1 -TenantId "YOUR-TENANT-ID" -SubscriptionId "YOUR-SUBSCRIPTION-ID" -TagName "Environment" -TagValue "Dev" -WhatIf
```

---

## Notes
- Always use `-WhatIf` first to validate changes before execution
- Ensure correct tag values are applied to avoid unintended actions
- This script is designed for automation scenarios such as dev/test cost optimization

---

## Author
Built as part of a cloud automation learning project to improve Azure and PowerShell skills.