# Azure CLI - Day 03

## What is Azure CLI?
Azure CLI is a command-line tool used to manage Azure resources using commands instead of the portal.

---

## Commands I Used

### Create Resource Group

az group create --name rg-cli-test --location centralindia

### List Resource Groups
az group list --output table


### Delete Resource Group
az group delete --name rg-cli-test --yes --no-wait
# Day 04 - Azure Storage (Blob Storage)

## What I Did

- Created a Storage Account:
  - Name: stzeyan01
  - Resource Group: rg-dev-mumbai-01
  - Region: Central India
  - Performance: Standard
  - Replication: LRS (Locally Redundant Storage)

- Used Blob Storage (Hot tier)

---

## Storage Types in Azure

### 1. Blob Storage
- Used for unstructured data
- Example: images, videos, backups

### 2. File Storage
- Managed file shares (like network drive)

### 3. Queue Storage
- Message queues (used in async processing)

### 4. Table Storage
- NoSQL key-value store

---

## Key Concepts

- Storage Account = container for all storage services
- Access tiers:
  - Hot → frequent access
  - Cool → less frequent
  - Archive → rarely used

---

## Real-World Use Case

- Store user uploads (images/videos)
- Backup application data
- Store logs

---

## Learnings

- Blob storage is most commonly used
- LRS is cheapest (good for learning)
- Storage is foundation of cloud apps

---

## Commands (CLI)



---

# 📂 **Week-01/Day-05/compute.md**

# Day 05 - Azure Compute (Virtual Machines)

## What I Tried

- Attempted to create a Virtual Machine
- Selected Ubuntu Server
- Tried multiple VM sizes:
  - B2ats_v2
  - B1s
  - B1ls

---

## Issues Faced

### 1. Quota Error
- Error: QuotaExceeded
- Reason:
  - New Azure accounts have limited CPU quota
  - My quota = 0 cores

---

### 2. Region Availability
- Some VM sizes not available in selected region

---

## Conclusion

- Could not create VM due to:
  - Quota restrictions
  - Region limitations

---

## Workaround Used

- Switched to **Azure Cloud Shell**
- Got Linux environment without needing VM

---

## Commands Executed

uname -a
uptime
df -h
Add Azure CLI Day 03 notes
---

# 📂 **Week-01/Day-06/networking.md**


# Day 06 - Azure Networking (VNet, Subnet, NSG)

## What I Built

### Virtual Network
- Name: vnet-dev
- Address space: 10.0.0.0/16

### Subnet
- Name: subnet-web
- Range: 10.0.1.0/24

### Network Security Group (NSG)
- Name: nsg-web

---

## NSG Rules Added

### Allow SSH
- Port: 22
- Protocol: TCP
- Action: Allow
- Priority: 1000

---

## Architecture

Internet → NSG → Subnet → VM (future)

---

## Key Concepts

### VNet
- Private network in Azure

### Subnet
- Logical division inside VNet

### NSG
- Firewall to control traffic

---

## Important Rule

NSG must be attached to:
- Subnet OR
- Network Interface

Otherwise:
- It does NOTHING

---

## Default Rules

- AllowVnetInBound
- AllowAzureLoadBalancer
- DenyAllInBound

---

## Real-World Learnings

- Security is critical
- Never open all ports
- Always use least privilege

---

## Mistakes to Avoid

- Creating NSG but not attaching it
- Allowing all traffic
- Ignoring priorities in rules

---

## Why This Matters

Networking controls:
- Who can access your system
- What traffic is allowed

---

## Interview Insight

Flow:

Internet → NSG → Subnet → VM
```bash
az group create --name rg-cli-test --location centralindia
