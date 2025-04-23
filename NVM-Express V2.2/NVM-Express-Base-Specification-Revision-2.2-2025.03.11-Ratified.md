# NVM Express® Base Specification, Revision 2.2

NVM Express® Base Specification, Revision 2.2, is available for download at https://nvmexpress.org. The NVM Express Base Specification, Revision 2.2, incorporates NVM Express Base Specification, Revision 2.1, TP4194 and ECN123 (refer to https://nvmexpress.org/specification/nvm-express-revision-changes/ for details).

## SPECIFICATION DISCLAIMER

### LEGAL NOTICE:
© Copyright 2008 to 2025 NVM Express, Inc. ALL RIGHTS RESERVED.

This NVM Express Base Specification, Revision 2.2 is proprietary to the NVM Express, Inc. (also referred to as "Company") and/or its successors and assigns.

### NOTICE TO USERS WHO ARE NVM EXPRESS, INC. MEMBERS:
Members of NVM Express, Inc. have the right to use and implement this NVM Express Base Specification, Revision 2.2 subject, however, to the Member's continued compliance with the Company's Intellectual Property Policy and Bylaws and the Member's Participation Agreement.

### NOTICE TO NON-MEMBERS OF NVM EXPRESS, INC.:
If you are not a Member of NVM Express, Inc. and you have obtained a copy of this document, you only have a right to review this document or make reference to or cite this document. Any such references or citations to this document must acknowledge NVM Express, Inc. copyright ownership of this document. The proper copyright citation or reference is as follows: "© 2008 to 2025 NVM Express, Inc. ALL RIGHTS RESERVED." When making any such citations or references to this document you are not permitted to revise, alter, modify, make any derivatives of, or otherwise amend the referenced portion of this document in any way without the prior express written permission of NVM Express, Inc. Nothing contained in this document shall be deemed as granting you any kind of license to implement or use this document or the specification described therein, or any of its contents, either expressly or impliedly, or to any intellectual property owned or controlled by NVM Express, Inc., including, without limitation, any trademarks of NVM Express, Inc.

### LEGAL DISCLAIMER:
THIS DOCUMENT AND THE INFORMATION CONTAINED HEREIN IS PROVIDED ON AN "AS IS" BASIS. TO THE MAXIMUM EXTENT PERMITTED BY APPLICABLE LAW, NVM EXPRESS, INC. (ALONG WITH THE CONTRIBUTORS TO THIS DOCUMENT) HEREBY DISCLAIM ALL REPRESENTATIONS, WARRANTIES AND/OR COVENANTS, EITHER EXPRESS OR IMPLIED, STATUTORY OR AT COMMON LAW, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, TITLE, VALIDITY, AND/OR NONINFRINGEMENT.

All product names, trademarks, registered trademarks, and/or servicemarks may be claimed as the property of their respective owners.

The NVM Express® design mark is a registered trademark of NVM Express, Inc.

PCI-SIG®, PCI Express®, and PCIe® are registered trademarks of PCI-SIG.

InfiniBand™ is a trademark and servicemark of the InfiniBand Trade Association.

Redfish® is a registered trademark of DMTF.

NVM Express Workgroup

c/o VTM, Inc.

3855 SW 153rd Drive

Beaverton, OR 97003 USA

info@nvmexpress.org

# NVM Express® Base Specification, Revision 2.2

## Table of Contents

### 1 INTRODUCTION
- 1.1 Overview - Page 1
  - 1.1.1 NVM Express® Specification Family - Page 1
- 1.2 Scope - Page 2
- 1.3 Outside of Scope - Page 2
- 1.4 Conventions - Page 2
  - 1.4.1 Keywords - Page 2
  - 1.4.2 Numerical Descriptions - Page 3
  - 1.4.3 Byte, Word, and Dword Relationships - Page 5
- 1.5 Definitions - Page 5
  - 1.5.1 admin label - Page 5
  - 1.5.2 admin label ASCII - Page 5
  - 1.5.3 admin label UTF - 8 - Page 6
  - 1.5.4 Admin Queue - Page 6
  - 1.5.5 Administrative controller - Page 6
  - 1.5.6 allocated namespace - Page 6
  - 1.5.7 Allowed Host List - Page 6
  - 1.5.8 arbitration burst - Page 6
  - 1.5.9 arbitration mechanism - Page 6
  - 1.5.10 association - Page 6
  - 1.5.11 audit - Page 6
  - 1.5.12 authentication commands - Page 6
  - 1.5.13 cache - Page 6
  - 1.5.14 candidate command - Page 6
  - 1.5.15 capsule - Page 7
  - 1.5.16 Centralized Discovery controller (CDC) - Page 7
  - 1.5.17 Channel - Page 7
  - 1.5.18 command completion - Page 7
  - 1.5.19 command submission - Page 7
  - 1.5.20 controller - Page 7
  - 1.5.21 Controller Reset - Page 7
  - 1.5.22 Directive - Page 7
  - 1.5.23 Direct Discovery controller (DDC) - Page 7
  - 1.5.24 Discovery controller - Page 8
  - 1.5.25 discovery information - Page 8
  - 1.5.26 Discovery Service - Page 8
  - 1.5.27 dispersed namespace - Page 8
  - 1.5.28 dynamic controller - Page 8
  - 1.5.29 Domain - Page 8
  - 1.5.30 embedded management controller - Page 8
  - 1.5.31 emulated controller - Page 8
  - 1.5.32 Endurance Group - Page 8
  - 1.5.33 Entry Key - Page 8
  - 1.5.34 Exported Namespace - Page 8
  - 1.5.35 Exported NVM Resources - Page 8
  - 1.5.36 Exported NVM Subsystem - Page 9
  - 1.5.37 Exported Port - Page 9
  - 1.5.38 Exported Port ID - Page 9
  - 1.5.39 fabric (network fabric) - Page 9
  - 1.5.40 Fabric Zoning - Page 9
  - 1.5.41 firmware/boot partition image update command sequence - Page 9
  - 1.5.42 firmware slot - Page 9
  - 1.5.43 host - Page 9
  - 1.5.44 host - accessible memory - Page 9
  - 1.5.45 host management agent - Page 9
  - 1.5.46 host memory - Page 9
  - 1.5.47 idempotent command - Page 9
  - 1.5.48 Identify Controller data structures - Page 10
  - 1.5.49 Identify Namespace data structures - Page 10

# NVM Express® Base Specification, Revision 2.2

## 1.5.50 - 1.5.99
| Section | Topic | Page |
| ---- | ---- | ---- |
| 1.5.50 | I/O command | 10 |
| 1.5.51 | I/O Completion Queue | 10 |
| 1.5.52 | I/O controller | 10 |
| 1.5.53 | I/O Submission Queue | 10 |
| 1.5.54 | Media Unit | 10 |
| 1.5.55 | memory-based controller | 10 |
| 1.5.56 | message-based controller | 10 |
| 1.5.57 | metadata | 10 |
| 1.5.58 | MMC | 10 |
| 1.5.59 | MMH | 10 |
| 1.5.60 | MMHD | 11 |
| 1.5.61 | MMHS | 11 |
| 1.5.62 | namespace | 11 |
| 1.5.63 | namespace ID (NSID) | 11 |
| 1.5.64 | NVM | 11 |
| 1.5.65 | NVM Set | 11 |
| 1.5.66 | NVM subsystem | 11 |
| 1.5.67 | NVM subsystem port | 11 |
| 1.5.68 | NVMe over Fabrics | 11 |
| 1.5.69 | NVMe Transport | 11 |
| 1.5.70 | NVMe Transport binding specification | 11 |
| 1.5.71 | participating NVM subsystem | 11 |
| 1.5.72 | physical fabric interface (physical ports) | 12 |
| 1.5.73 | Placement Handle | 12 |
| 1.5.74 | Placement Identifier | 12 |
| 1.5.75 | Port ID | 12 |
| 1.5.76 | Ports List | 12 |
| 1.5.77 | Power Loss Acknowledge (PLA) | 12 |
| 1.5.78 | Power Loss Notification (PLN) | 12 |
| 1.5.79 | primary controller | 12 |
| 1.5.80 | private namespace | 12 |
| 1.5.81 | property | 12 |
| 1.5.82 | Reclaim Group (RG) | 12 |
| 1.5.83 | Reclaim Unit (RU) | 12 |
| 1.5.84 | Reclaim Unit Handle (RUH) | 12 |
| 1.5.85 | rotational media | 13 |
| 1.5.86 | Runtime D3 (Power Removed) | 13 |
| 1.5.87 | sanitize operation | 13 |
| 1.5.88 | sanitization target | 13 |
| 1.5.89 | secondary controller | 13 |
| 1.5.90 | shared namespace | 13 |
| 1.5.91 | specified namespace | 13 |
| 1.5.92 | spindown | 13 |
| 1.5.93 | spinup | 13 |
| 1.5.94 | static controller | 13 |
| 1.5.95 | Underlying Namespace | 13 |
| 1.5.96 | Underlying Namespace List | 13 |
| 1.5.97 | Underlying NVM Subsystem | 14 |
| 1.5.98 | Underlying Port | 14 |
| 1.5.99 | user data | 14 |

## 1.6 - I/O Command Set specific definitions used in this specification
| Section | Topic | Page |
| ---- | ---- | ---- |
| 1.6.1 | Endurance Group Host Read Command | 14 |
| 1.6.2 | Format Index | 14 |
| 1.6.3 | SMART Data Units Read Command | 14 |
| 1.6.4 | SMART Host Read Command | 14 |
| 1.6.5 | User Data Format | 14 |
| 1.6.6 | User Data Out Command | 14 |

## 1.7 - NVM Command Set specific definitions used in this specification
| Section | Topic | Page |
| ---- | ---- | ---- |
| 1.7.1 | logical block | 14 |
| 1.7.2 | logical block address (LBA) | 14 |

## 1.8 - References
| Section | Topic | Page |
| ---- | ---- | ---- |
| 1.8 | References | 14 |

## 1.9 - References Under Development
| Section | Topic | Page |
| ---- | ---- | ---- |
| 1.9 | References Under Development | 16 |

# NVM Express® Base Specification, Revision 2.2

## 2 THEORY OF OPERATION
- **2.1 Memory-Based Transport Model (PCIe)**: Page 19
- **2.2 Message-Based Transport Model (Fabrics)**: Page 21
    - **2.2.1 Fabrics and Transports**: Page 21
    - **2.2.2 NVM Subsystem Ports for Fabrics**: Page 22
    - **2.2.3 Discovery Service**: Page 23
    - **2.2.4 Capsules and Data Transfer**: Page 23
    - **2.2.5 Authentication**: Page 24
- **2.3 NVM Storage Model**: Page 24
    - **2.3.1 Storage Entities**: Page 24
    - **2.3.2 I/O Command Sets**: Page 30
    - **2.3.3 NVM Subsystem Examples**: Page 30
- **2.4 Extended Capabilities Theory**: Page 32
    - **2.4.1 Multi-Path I/O and Namespace Sharing**: Page 32
    - **2.4.2 Asymmetric Controller Behavior**: Page 35

## 3 NVM EXPRESS ARCHITECTURE
- **3.1 NVM Controller Architecture**: Page 36
    - **3.1.1 Memory-Based Controller Architecture (PCIe)**: Page 36
    - **3.1.2 Message-Based Controller Architecture (Fabrics)**: Page 36
    - **3.1.3 Controller Types**: Page 37
    - **3.1.4 Controller Properties**: Page 48
- **3.2 NVM Subsystem Entities**: Page 74
    - **3.2.1 Namespaces**: Page 74
    - **3.2.2 NVM Sets**: Page 76
    - **3.2.3 Endurance Groups**: Page 78
    - **3.2.4 Reclaim Groups, Reclaim Unit Handles, and Reclaim Units**: Page 80
    - **3.2.5 Domains and Divisions**: Page 81
- **3.3 NVM Queue Models**: Page 84
    - **3.3.1 Memory-based Transport Queue Model (PCIe)**: Page 84
    - **3.3.2 Message-based Transport Queue Model (Fabrics)**: Page 87
    - **3.3.3 Queueing Attributes**: Page 96
- **3.4 Command Processing**: Page 97
    - **3.4.1 Command Ordering Requirements**: Page 97
    - **3.4.2 Fused Operations**: Page 97
    - **3.4.3 Atomic Operations**: Page 98
    - **3.4.4 Command Arbitration**: Page 98
    - **3.4.5 Outstanding Commands**: Page 100
- **3.5 Controller Initialization**: Page 101
    - **3.5.1 Memory-based Controller Initialization (PCIe)**: Page 101
    - **3.5.2 Message-based Controller Initialization (Fabrics)**: Page 102
    - **3.5.3 Controller Ready Modes During Initialization**: Page 105
    - **3.5.4 Controller Ready Timeouts During Initialization**: Page 107
- **3.6 Shutdown Processing**: Page 109
    - **3.6.1 Memory-based Controller Shutdown (PCIe)**: Page 110
    - **3.6.2 Message-based Controller Shutdown (Fabrics)**: Page 111
    - **3.6.3 NVM Subsystem Shutdown**: Page 112
- **3.7 Resets**: Page 115
    - **3.7.1 NVM Subsystem Reset**: Page 115
    - **3.7.2 Controller Level Reset**: Page 116
    - **3.7.3 Queue Level Reset**: Page 118
- **3.8 NVM Capacity Model**: Page 118
    - **3.8.1 Overview**: Page 118
    - **3.8.2 Media Unit Organization Examples**: Page 119
    - **3.8.3 Capacity Reporting**: Page 121
- **3.9 Keep Alive**: Page 122
    - **3.9.1 Keep Alive Timer Configuration**: Page 123
    - **3.9.2 Keep Alive Timer Activation**: Page 123
    - **3.9.3 Command Based Keep Alive**: Page 123

# NVM Express® Base Specification, Revision 2.2

## 3.9.4 Traffic Based Keep Alive
- Page: 125

## 3.9.5 Keep Alive Timeout Cleanup
- Page: 127

## 3.10 Privileged Actions
- Page: 128

## 3.11 Firmware Update Process
- Page: 128

## 4 DATA STRUCTURES
- Page: 131

### 4.1 Submission Queue Entry
- Page: 131

#### 4.1.1 Admin Command and I/O Command Common SQE
- Page: 131

#### 4.1.2 Fabrics Command Common SQE
- Page: 135

### 4.2 Completion Queue Entry
- Page: 136

#### 4.2.1 Admin Command and I/O Command Common CQE
- Page: 136

#### 4.2.2 Fabrics Command Common CQE
- Page: 137

#### 4.2.3 Status Field Definition
- Page: 137

#### 4.2.4 Phase Tag
- Page: 147

### 4.3 Data Pointer Layouts (PRPs and SGLs)
- Page: 149

#### 4.3.1 Physical Region Page Entry and List
- Page: 149

#### 4.3.2 Scatter Gather List (SGL)
- Page: 151

#### 4.3.3 Metadata Region (MR)
- Page: 157

### 4.4 Feature Values
- Page: 157

### 4.5 Identifier Format and Layout (Informative)
- Page: 160

#### 4.5.1 PCI Vendor ID (VID) and PCI Subsystem Vendor ID (SSVID)
- Page: 160

#### 4.5.2 Serial Number (SN) and Model Number (MN)
- Page: 160

#### 4.5.3 IEEE OUI Identifier (IEEE)
- Page: 160

#### 4.5.4 IEEE Extended Unique Identifier (EU164)
- Page: 161

#### 4.5.5 Namespace Globally Unique Identifier (NGUID)
- Page: 161

#### 4.5.6 Universally Unique Identifier (UUID)
- Page: 162

### 4.6 List Data Structures
- Page: 162

#### 4.6.1 Controller List
- Page: 162

#### 4.6.2 Namespace List
- Page: 163

### 4.7 NVMe Qualified Names
- Page: 163

#### 4.7.1 Unique Identifier
- Page: 164

### 4.8 UTF-8 String Processing
- Page: 165

## 5 ADMIN COMMAND SET
- Page: 167

### 5.1 Common Admin Commands
- Page: 169

#### 5.1.1 Abort command
- Page: 170

#### 5.1.2 Asynchronous Event Request command
- Page: 171

#### 5.1.3 Capacity Management command
- Page: 178

#### 5.1.4 Controller Data Queue command
- Page: 182

#### 5.1.5 Device Self-test command
- Page: 185

#### 5.1.6 Directive Receive command
- Page: 187

#### 5.1.7 Directive Send command
- Page: 188

#### 5.1.8 Firmware Commit command
- Page: 189

#### 5.1.9 Firmware Image Download command
- Page: 191

#### 5.1.10 Format NVM command
- Page: 192

#### 5.1.11 Get Features command
- Page: 195

#### 5.1.12 Get Log Page command
- Page: 198

#### 5.1.13 Identify command
- Page: 292

#### 5.1.14 Keep Alive command
- Page: 345

#### 5.1.15 Lockdown command
- Page: 345

#### 5.1.16 Migration Receive command
- Page: 347

#### 5.1.17 Migration Send command
- Page: 350

#### 5.1.18 NVMe-MI Receive command
- Page: 358

#### 5.1.19 NVMe-MI Send command
- Page: 358

#### 5.1.20 Namespace Attachment command
- Page: 358

#### 5.1.21 Namespace Management command
- Page: 360

#### 5.1.22 Sanitize command
- Page: 362

#### 5.1.23 Security Receive command
- Page: 365

#### 5.1.24 Security Send command
- Page: 366

#### 5.1.25 Set Features command
- Page: 367

# NVM Express® Base Specification, Revision 2.2

## 5.1.26 Track Receive command
Page: 408

## 5.1.27 Track Send command
Page: 411

## 5.2 Memory-Based Transport Admin Commands (PCIe)
Page: 415

### 5.2.1 Create I/O Completion Queue command
Page: 416

### 5.2.2 Create I/O Submission Queue command
Page: 417

### 5.2.3 Delete I/O Completion Queue command
Page: 419

### 5.2.4 Delete I/O Submission Queue command
Page: 419

### 5.2.5 Doorbell Buffer Config command
Page: 420

### 5.2.6 Virtualization Management command
Page: 421

## 5.3 Message-Based Transport Admin Commands (Fabrics)
Page: 423

### 5.3.1 Clear Exported NVM Resource Configuration command
Page: 423

### 5.3.2 Create Exported NVM Subsystem command
Page: 423

### 5.3.3 Discovery Information Management command
Page: 424

### 5.3.4 Fabric Zoning Lookup command
Page: 432

### 5.3.5 Fabric Zoning Receive command
Page: 432

### 5.3.6 Fabric Zoning Send command
Page: 434

### 5.3.7 Manage Exported Namespace command
Page: 435

### 5.3.8 Manage Exported NVM Subsystem command
Page: 437

### 5.3.9 Manage Exported Port command
Page: 441

### 5.3.10 Send Discovery Log Page command
Page: 444

## 6 FABRICS COMMAND SET
Page: 446

### 6.1 Authentication Receive Command and Response
Page: 446

### 6.2 Authentication Send Command and Response
Page: 447

### 6.3 Connect Command and Response
Page: 448

### 6.4 Disconnect Command and Response
Page: 453

### 6.5 Property Get Command and Response
Page: 454

### 6.6 Property Set Command and Response
Page: 455

## 7 I/O COMMANDS
Page: 456

### 7.1 Cancel command
Page: 456

#### 7.1.1 Command Completion
Page: 458

### 7.2 Flush command
Page: 459

#### 7.2.1 Command Completion
Page: 459

### 7.3 I/O Management Receive command
Page: 460

#### 7.3.1 I/O Management Receive Operations
Page: 460

#### 7.3.2 Command Completion
Page: 461

### 7.4 I/O Management Send command
Page: 461

#### 7.4.1 I/O Management Send Operations
Page: 462

#### 7.4.2 Command Completion
Page: 463

### 7.5 Reservation Acquire command
Page: 463

#### 7.5.1 Command Completion
Page: 464

### 7.6 Reservation Register command
Page: 464

#### 7.6.1 Command Completion
Page: 466

### 7.7 Reservation Release command
Page: 466

#### 7.7.1 Command Completion
Page: 467

### 7.8 Reservation Report command
Page: 467

#### 7.8.1 Command Completion
Page: 470

## 8 EXTENDED CAPABILITIES
Page: 471

### 8.1 Common Extended Capabilities
Page: 471

#### 8.1.1 Asymmetric Namespace Access Reporting
Page: 471

#### 8.1.2 Asymmetric Namespace Access Reporting – Host Considerations (Informative)
Page: 477

#### 8.1.3 Boot Partitions
Page: 479

#### 8.1.4 Capacity Management
Page: 487

#### 8.1.5 Command and Feature Lockdown
Page: 490

#### 8.1.6 Controller Data Queue
Page: 491

#### 8.1.7 Device Self-test Operations
Page: 492

#### 8.1.8 Directives
Page: 494

### NVM Express® Base Specification, Revision 2.2

#### 8.1.9 Dispersed Namespaces
- Page: 505

#### 8.1.10 Flexible Data Placement
- Page: 512

#### 8.1.11 Host-Initiated Refresh Operation
- Page: 517

#### 8.1.12 Host Managed Live Migration
- Page: 518

#### 8.1.13 Key Per I/O
- Page: 522

#### 8.1.14 Management Addresses
- Page: 523

#### 8.1.15 Namespace Management
- Page: 524

#### 8.1.16 Namespace Write Protection
- Page: 527

#### 8.1.17 Power Management
- Page: 530

#### 8.1.18 Predictable Latency Mode
- Page: 535

#### 8.1.19 Reachability Reporting architecture
- Page: 539

#### 8.1.20 Read Recovery Level
- Page: 542

#### 8.1.21 Replay Protected Memory Block
- Page: 543

#### 8.1.22 Reservations
- Page: 554

#### 8.1.23 Rotational Media
- Page: 562

#### 8.1.24 Sanitize Operations
- Page: 563

#### 8.1.25 Submission Queue (SQ) Associations
- Page: 577

#### 8.1.26 Standard Vendor Specific Command Format
- Page: 578

#### 8.1.27 Telemetry
- Page: 578

#### 8.1.28 Universally Unique Identifiers (UUIDs) for Vendor Specific Information
- Page: 582

#### 8.2 Memory-Based Transport Extended Capabilities (PCIe)
- Page: 585

#### 8.2.1 Controller Memory Buffer
- Page: 585

#### 8.2.2 Doorbell Stride for Software Emulation
- Page: 587

#### 8.2.3 Host Memory Buffer
- Page: 587

#### 8.2.4 Persistent Memory Region
- Page: 587

#### 8.2.5 Power Loss Signaling
- Page: 589

#### 8.2.6 Virtualization Enhancements
- Page: 596

#### 8.3 Message-Based Transport Extended Capabilities (Fabrics)
- Page: 600

#### 8.3.1 Automated Discovery of NVM-oF Discovery Controllers for IP Based Fabrics
- Page: 600

#### 8.3.2 Centralized Discovery for IP-based Fabrics
- Page: 606

#### 8.3.3 Exporting NVM Resources
- Page: 631

#### 8.3.4 NVMe over Fabrics Secure Channel and In-band Authentication
- Page: 635

### 9 ERROR REPORTING AND RECOVERY
- Page: 663

#### 9.1 Command and Queue Error Handling
- Page: 663

#### 9.2 Media and Data Error Handling
- Page: 663

#### 9.3 Memory Error Handling
- Page: 663

#### 9.4 Internal Controller Error Handling
- Page: 663

#### 9.5 Controller Fatal Status Condition
- Page: 663

#### 9.6 Communication Loss Handling
- Page: 664

#### 9.6.1 Host Communication Loss with a Controller
- Page: 664

#### 9.6.2 End of Controller Processing of Outstanding Commands
- Page: 665

#### 9.6.3 Command Retry After Communication Loss
- Page: 665

### ANNEX A. SANITIZE OPERATION CONSIDERATIONS (INFORMATIVE)
- Page: 669

#### A.1 Overview
- Page: 669

#### A.2 Hidden Storage (Overprovisioning)
- Page: 669

#### A.3 Integrity checks and No-Deallocate After Sanitize
- Page: 669

#### A.4 Bad Media and Vendor Specific NAND Use
- Page: 670

### ANNEX B. HOST CONSIDERATIONS (INFORMATIVE)
- Page: 671

#### B.1 Basic Steps when Building a Command
- Page: 671

#### B.2 Creating an I/O Submission Queue
- Page: 671

#### B.3 Executing a Fused Operation
- Page: 672

#### B.4 Asynchronous Event Request Host Software Recommendations
- Page: 674

#### B.5 Updating Controller Doorbell Properties using a Shadow Doorbell Buffer
- Page: 675

#### B.5.1 Shadow Doorbell Buffer Overview
- Page: 675

#### B.5.2 Example Algorithm for Controller Doorbell Property Updates
- Page: 675

#### B.6 Examples of Incorrect Command Retry Handling After Communication Loss
- Page: 675

### NVM Express® Base Specification, Revision 2.2

| Section | Title | Page |
| ---- | ---- | ---- |
| B.6.1 | Write after Write | 675 |
| B.6.2 | Non - Idempotent Command | 676 |
| B.6.3 | Retried Command Does Not Succeed | 677 |
| B.6.4 | Retried Command Affects Another Host | 678 |

**ANNEX C. POWER MANAGEMENT AND CONSUMPTION (INFORMATIVE)**................. 679

# NVM Express® Base Specification, Revision 2.2

## Table of Figures
| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 1 | NVMe Family of Specifications | 1 |
| Figure 2 | Decimal and Binary Units | 3 |
| Figure 3 | Byte, Word, and Dword Relationships | 5 |
| Figure 4 | Taxonomy of Transport Models | 18 |
| Figure 5 | Types of NVMe Command Sets | 19 |
| Figure 6 | Queue Pair Example, 1:1 Mapping | 20 |
| Figure 7 | Queue Pair Example, n:1 Mapping | 20 |
| Figure 8 | NVMe over Fabrics Layering | 22 |
| Figure 9 | Command Capsule Format | 23 |
| Figure 10 | Response Capsule Format | 24 |
| Figure 11 | Simple NVM Storage Hierarchy with NVM Sets | 25 |
| Figure 12 | Simple NVM Storage Hierarchy with One Reclaim Group | 26 |
| Figure 13 | Simple NVM Storage Hierarchy with Multiple Reclaim Groups | 27 |
| Figure 14 | Complex NVM Storage Hierarchy with NVM Sets | 28 |
| Figure 15 | Complex NVM Storage Hierarchy with Multiple Reclaim Groups | 29 |
| Figure 16 | Single - Namespace NVM Subsystem | 30 |
| Figure 17 | Two - Namespace NVM Subsystem | 31 |
| Figure 18 | Complex NVM Subsystem | 32 |
| Figure 19 | NVM Express Controller with Two Namespaces | 33 |
| Figure 20 | NVM Subsystem with Two Controllers and One Port | 33 |
| Figure 21 | NVM Subsystem with Two Controllers and Two Ports | 34 |
| Figure 22 | PCI Express Device Supporting Single Root I/O Virtualization (SR - IOV) | 35 |
| Figure 23 | Controller Types | 37 |
| Figure 24 | NVM Subsystem with Three I/O Controllers | 38 |
| Figure 25 | NVM Subsystem with One Administrative and Two I/O Controllers | 40 |
| Figure 26 | NVM Subsystem with One Administrative Controller | 40 |
| Figure 27 | Controller IDs FFh0 to FFFh | 42 |
| Figure 28 | Admin Command Support Requirements | 43 |
| Figure 29 | Fabrics Command Support Requirements | 44 |
| Figure 30 | Common I/O Command Support Requirements | 45 |
| Figure 31 | Log Page Support Requirements | 45 |
| Figure 32 | Feature Support Requirements | 47 |
| Figure 33 | Property Definition | 48 |
| Figure 34 | Memory - Based Property Definition | 50 |
| Figure 35 | Message - Based Property Definition | 50 |
| Figure 36 | Offset 0h: CAP – Controller Capabilities | 51 |
| Figure 37 | Specification Version Descriptor | 54 |
| Figure 38 | NVM Express Base Specification Version Property Reset Values | 54 |
| Figure 39 | Offset Ch: INTMS – Interrupt Mask Set | 55 |
| Figure 40 | Offset 10h: INTMC – Interrupt Mask Clear | 55 |
| Figure 41 | Offset 14h: CC – Controller Configuration | 56 |
| Figure 42 | Offset 1Ch: CSTS – Controller Status | 59 |
| Figure 43 | Offset 20h: NSSR – NVM Subsystem Reset | 62 |
| Figure 44 | Offset 24h: AQA – Admin Queue Attributes | 62 |
| Figure 45 | Offset 28h: ASQ – Admin Submission Queue Base Address | 62 |
| Figure 46 | Offset 30h: ACQ – Admin Completion Queue Base Address | 63 |
| Figure 47 | Offset 38h: CMBLOC – Controller Memory Buffer Location | 63 |
| Figure 48 | Offset 3Ch: CMBSZ – Controller Memory Buffer Size | 64 |
| Figure 49 | Offset 40h: BPINFO – Boot Partition Information | 65 |
| Figure 50 | Offset 44h: BPREL – Boot Partition Read Select | 65 |
| Figure 51 | Offset 48h: BPBML – Boot Partition Memory Buffer Location | 66 |
| Figure 52 | Offset 50h: CMBMSC – Controller Memory Buffer Memory Space Control | 66 |
| Figure 53 | Offset 58h: CMBCS – Controller Memory Buffer Status | 67 |
| Figure 54 | Offset 5Ch: CMBEBS – Controller Memory Buffer Elasticity Buffer Size | 67 |
| Figure 55 | Offset 60h: CMBSWTP – Controller Memory Buffer Sustained Write Throughput | 67 |
| Figure 56 | Offset 64h: NSSD – NVM Subsystem Shutdown | 68 |
| Figure 57 | Offset 68h: CRTO – Controller Ready Timeouts | 69 |
| Figure 58 | Offset E00h: PMRCAP – Persistent Memory Region Capabilities | 69 |
| Figure 59 | Offset E04h: PMRCTL – Persistent Memory Region Control | 70 |
| Figure 60 | Offset E08h: PMRSTS – Persistent Memory Region Status | 71 |
| Figure 61 | Offset E0Ch: PMREBS – Persistent Memory Region Elasticity Buffer Size | 72 |

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 62 | Offset E10h: PMRSWTP – Persistent Memory Region Sustained Write Throughput | 72 |
| Figure 63 | Offset E14h: PMRMSCL – Persistent Memory Region Memory Space Control Lower | 73 |
| Figure 64 | Offset E18h: PMRMSCU – Persistent Memory Region Memory Space Control Upper | 73 |
| Figure 65 | NSID Types and Relationship to Namespace | 74 |
| Figure 66 | NSID Types | 75 |
| Figure 67 | NVM Sets and Associated Namespaces | 77 |
| Figure 68 | NVM Set Aware Admin Commands | 77 |
| Figure 69 | NVM Sets and Associated Namespaces | 79 |
| Figure 70 | Flexible Data Placement Logical View of Non-Volatile Storage | 81 |
| Figure 71 | Example 1 Domain Structure | 82 |
| Figure 72 | Example 2 Domain Structure | 83 |
| Figure 73 | Empty Queue Definition | 86 |
| Figure 74 | Full Queue Definition | 87 |
| Figure 75 | Command Capsule | 88 |
| Figure 76 | Response Capsule | 88 |
| Figure 77 | Data and SGL Locations within a Command Capsule | 90 |
| Figure 78 | SGL Example Using Memory Transactions | 90 |
| Figure 79 | SGL Example Using in Capsule Data Transfer | 91 |
| Figure 80 | Round Robin Arbitration | 99 |
| Figure 81 | Weighted Round Robin with Urgent Priority Class Arbitration | 100 |
| Figure 82 | Queue Creation Flow | 103 |
| Figure 83 | Discovery Controller Initialization process flow | 105 |
| Figure 84 | Admin Commands Permitted to Return a Status Code of Admin Command Media Not Ready | 106 |
| Figure 85 | Shutdown Processing Interactions | 109 |
| Figure 86 | Simple NVM Subsystem | 119 |
| Figure 87 | Vertically-Organized NVM Subsystem | 120 |
| Figure 88 | Horizontally-Organized Dual NAND NVM Subsystem | 121 |
| Figure 89 | Capacity Information Field Usage | 122 |
| Figure 90 | Detecting Timeout Takes up to 2 * KATT | 126 |
| Figure 91 | Command Dword 0 | 131 |
| Figure 92 | Common Command Format | 132 |
| Figure 93 | Common Command Format – Vendor Specific Commands (Optional) | 135 |
| Figure 94 | Fabrics Command – Submission Queue Entry Format | 135 |
| Figure 95 | Fabrics Command – Command Dword 0 | 136 |
| Figure 96 | Common Completion Queue Entry Layout – Admin and All I/O Command Sets | 136 |
| Figure 97 | Completion Queue Entry: DW 2 | 136 |
| Figure 98 | Completion Queue Entry: DW 3 | 137 |
| Figure 99 | Fabrics Response – Completion Queue Entry Format | 137 |
| Figure 100 | Completion Queue Entry: Status Field | 137 |
| Figure 101 | Status Code – Status Code Type Values | 138 |
| Figure 102 | Status Code – Generic Command Status Values | 139 |
| Figure 103 | Status Code – Command Specific Status Values | 142 |
| Figure 104 | Status Code – Command Specific Status Values, I/O Commands | 144 |
| Figure 105 | Status Code – Command Specific Status Values, Fabrics Commands | 145 |
| Figure 106 | Status Code – Media and Data Integrity Error Values | 146 |
| Figure 107 | Status Code – Path Related Status Values | 146 |
| Figure 108 | Phase Tag bit Translation Example | 148 |
| Figure 109 | PRP Entry Layout | 149 |
| Figure 110 | PRP Entry – Page Base Address and Offset | 150 |
| Figure 111 | PRP List Layout for Physically Contiguous Memory Pages | 150 |
| Figure 112 | PRP List Layout for Physically Non-Contiguous Memory Pages | 150 |
| Figure 113 | SGL Validation Error Conditions | 152 |
| Figure 114 | SGL Segment | 152 |
| Figure 115 | Generic SGL Descriptor Format | 153 |
| Figure 116 | SGL Descriptor Type | 153 |
| Figure 117 | SGL Descriptor Sub-Type Values | 153 |
| Figure 118 | SGL Data Block descriptor | 154 |
| Figure 119 | SGL Bit Bucket descriptor | 154 |
| Figure 120 | SGL Segment descriptor | 155 |
| Figure 121 | SGL Last Segment descriptor | 155 |
| Figure 122 | Keyed SGL Data Block descriptor | 155 |
| Figure 123 | Transport SGL Data Block descriptor | 156 |

# NVM Express® Base Specification, Revision 2.2

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 124 | SGL Read Example | 157 |
| Figure 125 | Current Value after Reset with Scope of Entire NVM Subsystem | 158 |
| Figure 126 | Current Value after Reset with Scope of Subset of the NVM Subsystem | 159 |
| Figure 127 | PCI Vendor ID (VID) and PCI Subsystem Vendor ID (SSVID) | 160 |
| Figure 128 | Serial Number (SN) and Model Number (MN) | 160 |
| Figure 129 | IEEE OUI Identifier (IEEE) | 161 |
| Figure 130 | IEEE Extended Unique Identifier (EUI64), MA-L Format | 161 |
| Figure 131 | IEEE Extended Unique Identifier (EUI64), OUI Identifier | 161 |
| Figure 132 | IEEE Extended Unique Identifier (EUI64), Ext. ID (cont) | 161 |
| Figure 133 | MA-L similarity to WWN | 161 |
| Figure 134 | Namespace Globally Unique Identifier (NGUID) | 162 |
| Figure 135 | Namespace Globally Unique Identifier (NGUID), OUI | 162 |
| Figure 136 | Namespace Globally Unique Identifier (NGUID), Extension Identifier (continued) | 162 |
| Figure 137 | Namespace Globally Unique Identifier (NGUID), NGUID similarity to WWN | 162 |
| Figure 138 | Controller List Format | 163 |
| Figure 139 | Namespace List Format | 163 |
| Figure 140 | QNN Construction for Older NVM Subsystems | 165 |
| Figure 141 | UTF-8 Input Processing | 166 |
| Figure 142 | Opcodes for Admin Commands | 167 |
| Figure 143 | Sanitize Operations and Format NVM Command – Admin Commands Allowed | 169 |
| Figure 144 | Abort – Command Dword 10 | 170 |
| Figure 145 | Abort Command – Completion Queue Entry Dword 0 | 171 |
| Figure 146 | Abort – Command Specific Status Values | 171 |
| Figure 147 | Status Code – Command Specific Status Values | 173 |
| Figure 148 | Asynchronous Event Request – Completion Queue Entry Dword 0 | 173 |
| Figure 149 | Asynchronous Event Request – Completion Queue Entry Dword 1 | 173 |
| Figure 150 | Asynchronous Event Information – Error Status | 174 |
| Figure 151 | Asynchronous Event Information – SMART / Health Status | 174 |
| Figure 152 | Asynchronous Event Information – Notice | 175 |
| Figure 153 | Asynchronous Event Information – I/O Command Specific Status | 177 |
| Figure 154 | Asynchronous Event Information – Immediate | 178 |
| Figure 155 | Asynchronous Event Information – One Shot | 178 |
| Figure 156 | Controller Data Queue Tail Pointer – Event Specific Parameter | 178 |
| Figure 157 | Capacity Management – Command Dword 10 | 179 |
| Figure 158 | Capacity Management – Command Dword 11 | 179 |
| Figure 159 | Capacity Management – Command Dword 12 | 179 |
| Figure 160 | Capacity Management – Command Specific Status Values | 182 |
| Figure 161 | Capacity Management – Completion Queue Entry Dword 0 | 182 |
| Figure 162 | Controller Data Queue – Command Dword 10 | 182 |
| Figure 163 | Create Controller Data Queue – PRP Entry 1 | 183 |
| Figure 164 | Create Controller Data Queue – Command Dword 11 | 183 |
| Figure 165 | Create Queue – Command Dword 12 | 183 |
| Figure 166 | Create Controller Data Queue – Management Operation Specific | 184 |
| Figure 167 | User Data Migration Queue – Create Queue Specific | 184 |
| Figure 168 | Delete Controller Data Queue – Command Dword 11 | 184 |
| Figure 169 | Controller Data Queue – Completion Queue Entry Dword 0 | 185 |
| Figure 170 | Controller Data Queue – Command Specific Status Values | 185 |
| Figure 171 | Device Self-test Namespace Test Action | 185 |
| Figure 172 | Device Self-test – Command Dword 10 | 186 |
| Figure 173 | Device Self-test – Command Dword 15 | 186 |
| Figure 174 | Device Self-test – Command Processing | 186 |
| Figure 175 | Device Self-test – Command Specific Status Values | 187 |
| Figure 176 | Directive Receive – Data Pointer | 187 |
| Figure 177 | Directive Receive – Command Dword 10 | 188 |
| Figure 178 | Directive Receive – Command Dword 11 | 188 |
| Figure 179 | Directive Send – Data Pointer | 188 |
| Figure 180 | Directive Send – Command Dword 10 | 188 |
| Figure 181 | Directive Send – Command Dword 11 | 188 |
| Figure 182 | Firmware Commit – Command Dword 10 | 189 |
| Figure 183 | Firmware Commit – Completion Queue Entry Dword 0 | 190 |
| Figure 184 | Firmware Commit – Command Specific Status Values | 191 |
| Figure 185 | Firmware Image Download – Data Pointer | 192 |

# NVM Express® Base Specification, Revision 2.2

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 186 | Firmware Image Download – Command Dword 10 | 192 |
| Figure 187 | Firmware Image Download – Command Dword 11 | 192 |
| Figure 188 | Firmware Image Download – Command Specific Status Values | 192 |
| Figure 189 | Format NVM – Operation Scope | 193 |
| Figure 190 | Format NVM – Command Dword 10 | 194 |
| Figure 191 | Format NVM – Command Specific Status Values | 195 |
| Figure 192 | Get Features – Data Pointer | 196 |
| Figure 193 | Get Features – Command Dword 10 | 196 |
| Figure 194 | Get Features – Command Dword 14 | 196 |
| Figure 195 | Get Features – Feature Identifiers | 196 |
| Figure 196 | Completion Queue Entry Dword 0 when Select is set to 11b | 198 |
| Figure 197 | Get Log Page – Data Pointer | 199 |
| Figure 198 | Get Log Page – Command Dword 10 | 199 |
| Figure 199 | Get Log Page – Command Dword 11 | 199 |
| Figure 200 | Get Log Page – Command Dword 12 | 200 |
| Figure 201 | Get Log Page – Command Dword 13 | 200 |
| Figure 202 | Get Log Page – Command Dword 14 | 200 |
| Figure 203 | Get Log Page – Log Page Identifiers | 201 |
| Figure 204 | Supported Log Pages Log Page | 203 |
| Figure 205 | LID Supported and Effects Data Structure | 203 |
| Figure 206 | Error Information Log Entry Data Structure | 204 |
| Figure 207 | SMART / Health Information Log Page | 206 |
| Figure 208 | Temperature Sensor Data Structure | 209 |
| Figure 209 | Firmware Slot Information Log Page | 210 |
| Figure 210 | Commands Supported and Effects Log Page | 211 |
| Figure 211 | Commands Supported and Effects Data Structure | 212 |
| Figure 212 | Device Self-test Log Page | 214 |
| Figure 213 | Self-test Result Data Structure | 215 |
| Figure 214 | Telemetry Host-Initiated Log Specific Parameter Field | 216 |
| Figure 215 | Telemetry Host-Initiated Log Page | 218 |
| Figure 216 | Telemetry Host-Initiated Log Page – LID Specific Parameter Field | 219 |
| Figure 217 | Telemetry Controller-Initiated Log Page | 220 |
| Figure 218 | Endurance Group Identifier – Log Specific Identifier | 221 |
| Figure 219 | Endurance Group Information Log Page | 222 |
| Figure 220 | NVM Set Identifier – Log Specific Identifier | 223 |
| Figure 221 | Predictable Latency Per NVM Set Log Page | 224 |
| Figure 222 | Predictable Latency Event Aggregate Log Page | 225 |
| Figure 223 | Asymmetric Namespace Access Log Specific Parameter Field | 226 |
| Figure 224 | Asymmetric Namespace Access Log Page | 226 |
| Figure 225 | ANA Group Descriptor format | 227 |
| Figure 226 | Persistent Event Log Specific Parameter Field | 230 |
| Figure 227 | Persistent Event Log Page | 231 |
| Figure 228 | Persistent Event Format | 233 |
| Figure 229 | Persistent Event LID Specific Parameter Field | 235 |
| Figure 230 | Persistent Event Log Event Types | 235 |
| Figure 231 | SMART / Health Log Snapshot Format (Event Type 01h) | 236 |
| Figure 232 | Firmware Commit Event Data Format (Event Type 02h) | 236 |
| Figure 233 | Timestamp Change Event Format (Event Type 03h) | 236 |
| Figure 234 | Power-on or Reset Event (Event Type 04h) | 237 |
| Figure 235 | Controller Reset Information descriptor | 237 |
| Figure 236 | NVM Subsystem Hardware Error Event Format (Event Type 05h) | 238 |
| Figure 237 | NVM Subsystem Hardware Error Event Codes | 238 |
| Figure 238 | Additional Hardware Error Information for Unexpected Power Loss Errors | 240 |
| Figure 239 | Additional Hardware Error Information for correctable and uncorrectable PCIe errors | 240 |
| Figure 240 | Additional Hardware Error Information for Controller Ready Timeout Exceeded errors | 241 |
| Figure 241 | Change Namespace Event Data Format (Event Type 06h) | 241 |
| Figure 242 | Format NVM Start Event Data Format (Event Type 07h) | 243 |
| Figure 243 | Format NVM Completion Event Data Format (Event Type 08h) | 243 |
| Figure 244 | Sanitize Start Event Data Format (Event Type 09h) | 244 |
| Figure 245 | Sanitize Completion Event Data Format (Event Type 0Ah) | 244 |
| Figure 246 | Feature Persistent Event Logging Requirements | 245 |
| Figure 247 | Set Feature Event Data Format | 246 |

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 248 | Telemetry Log Create Event Data Format (Event Type 0Ch) | 247 |
| Figure 249 | Thermal Excursion Event Data Format (Event Type 0Dh) | 247 |
| Figure 250 | Vendor Specific Event Format (Event Type DEh) | 249 |
| Figure 251 | Vendor Specific Event Descriptor Format | 249 |
| Figure 252 | Vendor Specific Event Data Type Codes | 249 |
| Figure 253 | Endurance Group Event Aggregate Log Page | 250 |
| Figure 254 | Domain Identifier – Log Specific Identifier | 251 |
| Figure 255 | Media Unit Status Log Page | 251 |
| Figure 256 | Media Unit Status Descriptor | 252 |
| Figure 257 | Supported Capacity Configuration List Log Page | 253 |
| Figure 258 | Capacity Configuration Descriptor | 254 |
| Figure 259 | Endurance Group Configuration Descriptor | 254 |
| Figure 260 | Channel Configuration Descriptor | 255 |
| Figure 261 | Media Unit Configuration Descriptor | 256 |
| Figure 262 | Feature Identifiers Effects Log Page | 256 |
| Figure 263 | FID Supported and Effects Data Structure | 257 |
| Figure 264 | NVMe-MI Commands Supported and Effects Log Page | 258 |
| Figure 265 | NVMe-MI Commands Supported and Effects Data Structure | 259 |
| Figure 266 | Command and Feature Lockdown Log Specific Parameter Field | 260 |
| Figure 267 | Command and Feature Lockdown Log Page | 261 |
| Figure 268 | Boot Partition Log Specific Parameter Field | 262 |
| Figure 269 | Boot Partition Log Page | 262 |
| Figure 270 | Rotational Media Information Log Page | 262 |
| Figure 271 | Dispersed Namespace Participating NVM Subsystems Log Page | 263 |
| Figure 272 | Management Address List – Log Page | 264 |
| Figure 273 | Management Address Descriptor | 264 |
| Figure 274 | Reachability Groups Log Specific Parameter Field | 265 |
| Figure 275 | Reachability Groups Log Page | 265 |
| Figure 276 | Reachability Group Descriptor format | 266 |
| Figure 277 | Reachability Associations Log Specific Parameter Field | 267 |
| Figure 278 | Reachability Associations Log Page | 267 |
| Figure 279 | Reachability Association Descriptor format | 268 |
| Figure 280 | FDP Configurations Log Page | 269 |
| Figure 281 | FDP Configuration Descriptor | 269 |
| Figure 282 | Reclaim Unit Handle Descriptor | 270 |
| Figure 283 | Placement Identifier Format without Reclaim Group Identifier | 271 |
| Figure 284 | Placement Identifier Format with a non-zero RGF | 271 |
| Figure 285 | Reclaim Unit Handle Usage Log Page | 272 |
| Figure 286 | Reclaim Unit Handle Usage Descriptor | 272 |
| Figure 287 | FDP Statistics Log Page | 273 |
| Figure 288 | Command Dword 10 – Log Specific Field | 274 |
| Figure 289 | FDP Events Log Page | 274 |
| Figure 290 | FDP Event | 274 |
| Figure 291 | Reservation Notification Log Page | 277 |
| Figure 292 | Sanitize Status Log Page | 277 |
| Figure 293 | Discovery Log Page – LID Specific Parameter Field | 281 |
| Figure 294 | Discovery Log Specific Parameter Field | 283 |
| Figure 295 | Discovery Log Page Entry Data Structure | 283 |
| Figure 296 | Extended Discovery Log Page Entry | 286 |
| Figure 297 | Discovery Log Page | 286 |
| Figure 298 | Host Discovery – LID Specific Parameter Field | 288 |
| Figure 299 | Host Discovery Log Specific Parameter Field | 288 |
| Figure 300 | Host Extended Discovery Log Page Entry | 289 |
| Figure 301 | Host Discovery Log Page | 289 |
| Figure 302 | Get Log Page – AVE Discovery Log Page | 290 |
| Figure 303 | Get Log Page – AVE Discovery Log Page Entry | 291 |
| Figure 304 | AVE Transport Record | 291 |
| Figure 305 | Pull Model DDC Request Log Page | 292 |
| Figure 306 | Get Log Page – Command Specific Status Values | 292 |
| Figure 307 | Identify – Data Pointer | 292 |
| Figure 308 | Identify – Command Dword 10 | 293 |
| Figure 309 | Identify – Command Dword 11 | 293 |

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 310 | Identify - Command Dword 14 | 293 |
| Figure 311 | Identify - CNS Values | 294 |
| Figure 312 | Command Set Identifiers | 295 |
| Figure 313 | Identify - Identify Controller Data Structure, I/O Command Set Independent | 296 |
| Figure 314 | Identify - Power State Descriptor Data Structure | 325 |
| Figure 315 | Time Scale Values | 328 |
| Figure 316 | Identify - Namespace Identification Descriptor | 329 |
| Figure 317 | Command Dword 11 - CNS Specific Identifier | 330 |
| Figure 318 | NVM Set List | 330 |
| Figure 319 | Identify Attributes Entry | 330 |
| Figure 320 | Identify - I/O Command Set Independent Identify Namespace Data Structure | 332 |
| Figure 321 | UUID List | 337 |
| Figure 322 | UUID List Entry | 337 |
| Figure 323 | Command Dword 11 - CNS Specific Identifier | 337 |
| Figure 324 | Domain List | 337 |
| Figure 325 | Domain Attributes Entry | 338 |
| Figure 326 | Command Dword 11 - CNS Specific Identifier | 338 |
| Figure 327 | Endurance Group List | 338 |
| Figure 328 | Identify I/O Command Set Data Structure | 339 |
| Figure 329 | I/O Command Set Vector | 340 |
| Figure 330 | Supported Controller State Formats Data Structure | 340 |
| Figure 331 | Identity - Primary Controller Capabilities Structure | 341 |
| Figure 332 | Secondary Controller List | 343 |
| Figure 333 | Secondary Controller Entry | 343 |
| Figure 334 | Underlying Namespace List Data Structure | 343 |
| Figure 335 | Underlying Namespace Entry Data Structure | 344 |
| Figure 336 | Ports List Data Structure | 344 |
| Figure 337 | Underlying Fabrics Transport Entry Data Structure | 344 |
| Figure 338 | Lockdown - Command Dword 10 | 345 |
| Figure 339 | Lockdown - Command Dword 14 | 346 |
| Figure 340 | Lockdown - Command Specific Status Values | 347 |
| Figure 341 | Migration Receive - Command Dword 10 | 347 |
| Figure 342 | Migration Receive - Command Dword 12 | 347 |
| Figure 343 | Migration Receive - Command Dword 13 | 347 |
| Figure 344 | Migration Receive - Command Dword 14 | 348 |
| Figure 345 | Migration Receive - Command Dword 15 | 348 |
| Figure 346 | Get Controller State Management Operation - Management Operation Specific | 349 |
| Figure 347 | Get Controller State Management Operation - Command Dword 11 | 349 |
| Figure 348 | Get Controller State Management Operation - Completion Queue Entry Dword 0 | 349 |
| Figure 349 | Migration Receive - Command Specific Status Values | 350 |
| Figure 350 | Migration Send - Command Dword 10 | 350 |
| Figure 351 | Migration Send - Command Dword 14 | 350 |
| Figure 352 | Suspend - Command Dword 11 | 351 |
| Figure 353 | Resume - Command Dword 11 | 352 |
| Figure 354 | Set Controller State - Management Operation Specific Field | 354 |
| Figure 355 | Set Controller State - Command Dword 11 | 354 |
| Figure 356 | Set Controller State - Command Dword 12 | 354 |
| Figure 357 | Set Controller State - Command Dword 13 | 354 |
| Figure 358 | Set Controller State - Command Dword 15 | 354 |
| Figure 359 | Controller State Data Structure | 355 |
| Figure 360 | NVMe Controller State Data Structure | 356 |
| Figure 361 | I/O Submission Queue State Data Structure | 356 |
| Figure 362 | I/O Completion Queue State Data Structure | 357 |
| Figure 363 | Migration Send - Command Specific Status Values | 358 |
| Figure 364 | Namespace Attachment - Data Pointer | 359 |
| Figure 365 | Namespace Attachment - Command Dword 10 | 359 |
| Figure 366 | Namespace Attachment - Command Specific Status Values | 359 |
| Figure 367 | Namespace Management - Data Pointer | 360 |
| Figure 368 | Namespace Management - Command Dword 10 | 360 |
| Figure 369 | Namespace Management - Command Dword 11 | 361 |
| Figure 370 | Namespace Management - Data Structure for Create | 361 |
| Figure 371 | Namespace Management - Command Specific Status Values | 361 |

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 372 | Namespace Management – Completion Queue Entry Dword 0 | 362 |
| Figure 373 | Sanitize – Command Dword 10 | 364 |
| Figure 374 | Sanitize – Command Dword 11 | 365 |
| Figure 375 | Sanitize – Command Specific Status Values | 365 |
| Figure 376 | Security Receive – Data Pointer | 366 |
| Figure 377 | Security Receive – Command Dword 10 | 366 |
| Figure 378 | Security Receive – Command Dword 11 | 366 |
| Figure 379 | Security Protocol EAh – Security Protocol Specific Field Values | 367 |
| Figure 380 | Security Send – Data Pointer | 367 |
| Figure 381 | Security Send – Command Dword 10 | 367 |
| Figure 382 | Security Send – Command Dword 11 | 367 |
| Figure 383 | Set Features – Data Pointer | 368 |
| Figure 384 | Set Features – Command Dword 10 | 368 |
| Figure 385 | Set Features – Command Dword 14 | 368 |
| Figure 386 | Set Features – Feature Identifiers | 368 |
| Figure 387 | Arbitration & Command Processing – Command Dword 11 | 371 |
| Figure 388 | Power Management – Command Dword 11 | 371 |
| Figure 389 | Power Management – Completion Queue Entry Dword 0 | 371 |
| Figure 390 | Temperature Threshold – Command Dword 11 | 373 |
| Figure 391 | Volatile Write Cache – Command Dword 11 | 374 |
| Figure 392 | Asynchronous Event Configuration – Command Dword 11 | 374 |
| Figure 393 | Autonomous Power State Transition – Command Dword 11 | 376 |
| Figure 394 | Autonomous Power State Transition – Data Structure Entry | 376 |
| Figure 395 | Interactions between APSTE and NOPFME | 376 |
| Figure 396 | Timestamp – Data Structure for Set Features | 377 |
| Figure 397 | Timestamp – Data Structure for Get Features | 377 |
| Figure 398 | Keep Alive Timer – Command Dword 11 | 378 |
| Figure 399 | HCTM – Command Dword 11 | 379 |
| Figure 400 | Non-Operational Power State Config – Command Dword 11 | 379 |
| Figure 401 | Read Recovery Level Config – Command Dword 11 | 380 |
| Figure 402 | Read Recovery Level Config – Command Dword 12 | 380 |
| Figure 403 | Predictable Latency Mode Config – Command Dword 11 | 381 |
| Figure 404 | Predictable Latency Mode Config – Command Dword 12 | 381 |
| Figure 405 | Predictable Latency Mode – Deterministic Threshold Configuration Data Structure | 381 |
| Figure 406 | Predictable Latency Mode Window – Command Dword 11 | 382 |
| Figure 407 | Predictable Latency Mode Window – Command Dword 12 | 382 |
| Figure 408 | Host Behavior Support – Data Structure | 383 |
| Figure 409 | Sanitize Config – Command Dword 11 | 384 |
| Figure 410 | Asynchronous Event Configuration – Command Dword 11 | 385 |
| Figure 411 | I/O Command Set Profile – Command Dword 11 | 385 |
| Figure 412 | I/O Command Set Profile – Completion Queue Entry Dword 0 | 386 |
| Figure 413 | Spinup Control – Command Dword 11 | 386 |
| Figure 414 | Completion Queue Entry Dword 0 | 386 |
| Figure 415 | Power Loss Signaling Config – Command Dword 11 | 387 |
| Figure 416 | Flexible Data Placement – Command Dword 11 | 387 |
| Figure 417 | Flexible Data Placement – Command Dword 12 | 387 |
| Figure 418 | FDP Events – Completion Queue Entry Dword 0 | 388 |
| Figure 419 | FDP Events – Command Dword 11 | 388 |
| Figure 420 | Flexible Data Placement – Command Dword 12 | 388 |
| Figure 421 | FDP Events – Set Feature Data Structure | 389 |
| Figure 422 | FDP Events – Get Feature Data Structure | 389 |
| Figure 423 | Supported FDP Event Descriptor | 389 |
| Figure 424 | Namespace Admin Label – Data Structure | 390 |
| Figure 425 | Controller Data Queue – Command Dword 11 | 390 |
| Figure 426 | Controller Data Queue – Command Dword 12 | 391 |
| Figure 427 | Controller Data Queue – Command Dword 13 | 391 |
| Figure 428 | Controller Data Queue – Data Structure | 391 |
| Figure 429 | Set Features – Command Specific Status Values | 391 |
| Figure 430 | Host Management Agent Address | 392 |
| Figure 431 | Get Features – Command Dword 11 | 392 |
| Figure 432 | Set Features – Command Dword 11 | 393 |
| Figure 433 | Host Metadata Data Structure | 395 |

# NVM Express® Base Specification, Revision 2.2

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 434 | Metadata Element Descriptor | 395 |
| Figure 435 | Controller Metadata Element Types | 395 |
| Figure 436 | Namespace Metadata Element Types | 397 |
| Figure 437 | Software Progress Marker – Command Dword 11 | 397 |
| Figure 438 | Host Identifier – Command Dword 11 | 398 |
| Figure 439 | Host Identifier – Data Structure Entry | 398 |
| Figure 440 | Reservation Notification Configuration – Command Dword 11 | 399 |
| Figure 441 | Reservation Persistence Configuration – Command Dword 11 | 400 |
| Figure 442 | Write Protection – Command Dword 11 | 400 |
| Figure 443 | Boot Partition Write Protection Config – Command Dword 11 | 401 |
| Figure 444 | Number of Queues – Command Dword 11 | 402 |
| Figure 445 | Number of Queues – Completion Queue Entry Dword 0 | 403 |
| Figure 446 | Interrupt Coalescing – Command Dword 11 | 403 |
| Figure 447 | Interrupt Vector Configuration – Command Dword 11 | 404 |
| Figure 448 | Host Memory Buffer – Command Dword 11 | 405 |
| Figure 449 | Host Memory Buffer – Command Dword 12 | 406 |
| Figure 450 | Host Memory Buffer – Command Dword 13 | 406 |
| Figure 451 | Host Memory Buffer – Command Dword 14 | 406 |
| Figure 452 | Host Memory Buffer – Command Dword 15 | 406 |
| Figure 453 | Host Memory Buffer – Host Memory Descriptor List | 406 |
| Figure 454 | Host Memory Buffer – Host Memory Buffer Descriptor Entry | 407 |
| Figure 455 | Host Memory Buffer – Completion Queue Entry Dword 0 | 407 |
| Figure 456 | Host Memory Buffer – Attributes Data Structure | 407 |
| Figure 457 | Set Features – Command Specific Status Values | 408 |
| Figure 458 | Track Receive – Command Dword 10 | 408 |
| Figure 459 | Track Receive – Command Dword 12 | 408 |
| Figure 460 | Tracked Memory Changes – Command Dword 11 | 409 |
| Figure 461 | Tracked Memory Change Data Structure | 409 |
| Figure 462 | Tracked Memory Changed Descriptor | 410 |
| Figure 463 | Track Receive – Command Specific Status Values | 411 |
| Figure 464 | Track Send – Command Dword 10 | 411 |
| Figure 465 | Log User Data Changes – Management Operation Specific Field | 412 |
| Figure 466 | Log User Data Changes – Command Dword 11 | 412 |
| Figure 467 | Track Memory Changes – Management Operation Specific Field | 413 |
| Figure 468 | Track Memory Changes – Command Dword 11 | 413 |
| Figure 469 | Track Memory Changes Data Structure | 414 |
| Figure 470 | Memory Range Tracking Descriptor | 414 |
| Figure 471 | Track Memory Changes – Completion Queue Entry Dword 0 | 415 |
| Figure 472 | Track Memory Changes – Completion Queue Entry Dword 1 | 415 |
| Figure 473 | Track Send – Command Specific Status Values | 415 |
| Figure 474 | Create I/O Completion Queue – PRP Entry 1 | 416 |
| Figure 475 | Create I/O Completion Queue – Command Dword 10 | 416 |
| Figure 476 | Create I/O Completion Queue – Command Dword 11 | 416 |
| Figure 477 | Create I/O Completion Queue – Command Specific Status Values | 417 |
| Figure 478 | Create I/O Submission Queue – PRP Entry 1 | 417 |
| Figure 479 | Create I/O Submission Queue – Command Dword 10 | 417 |
| Figure 480 | Create I/O Submission Queue – Command Dword 11 | 418 |
| Figure 481 | Create I/O Submission Queue – Command Dword 12 | 418 |
| Figure 482 | Create I/O Submission Queue – Command Specific Status Values | 419 |
| Figure 483 | Delete I/O Completion Queue – Command Dword 10 | 419 |
| Figure 484 | Delete I/O Completion Queue – Command Specific Status Values | 419 |
| Figure 485 | Delete I/O Submission Queue – Command Dword 10 | 420 |
| Figure 486 | Delete I/O Submission Queue – Command Specific Status Values | 420 |
| Figure 487 | Doorbell Buffer Config – Shadow Doorbell and EventIdx | 420 |
| Figure 488 | Doorbell Buffer Config – PRP Entry 1 | 421 |
| Figure 489 | Doorbell Buffer Config – PRP Entry 2 | 421 |
| Figure 490 | Virtualization Management – Command Dword 10 | 422 |
| Figure 491 | Virtualization Management – Command Dword 11 | 422 |
| Figure 492 | Virtualization Management – Command Specific Status Values | 423 |
| Figure 493 | Virtualization Management – Completion Queue Entry Dword 0 | 423 |
| Figure 494 | Create Exported NVM Subsystem – Data Pointer | 424 |
| Figure 495 | Create Exported NVM Subsystem – Command Dword 10 | 424 |

# NVM Express® Base Specification, Revision 2.2

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 496 | Discovery Information Management – Data Pointer | 426 |
| Figure 497 | Discovery Information Management – Command Dword 10 | 426 |
| Figure 498 | Discovery Information Management – Data | 426 |
| Figure 499 | Extended Discovery Information Entry | 428 |
| Figure 500 | Extended Attribute | 430 |
| Figure 501 | Extended Discovery Information Entry – Applicable Fields | 431 |
| Figure 502 | Discovery Information Management – Command Specific Status Values | 432 |
| Figure 503 | Fabric Zoning Lookup (FZL) – Data Pointer | 432 |
| Figure 504 | Fabric Zoning Lookup (FZL) – Command Specific Status Values | 432 |
| Figure 505 | Fabric Zoning Lookup (FZL) – Completion Queue Entry Dword 0 | 432 |
| Figure 506 | Fabric Zoning Receive (FZR) – Data Pointer | 433 |
| Figure 507 | Fabric Zoning Receive (FZR) – Command Dword 10 | 433 |
| Figure 508 | Fabric Zoning Receive (FZR) – Command Dword 11 | 433 |
| Figure 509 | Fabric Zoning Receive (FZR) – Command Dword 12 | 433 |
| Figure 510 | Fabric Zoning Receive (FZR) – Command Specific Status Values | 433 |
| Figure 511 | Fabric Zoning Receive (FZR) – Completion Queue Entry Dword 0 | 434 |
| Figure 512 | Fabric Zoning Send (FZS) – Data Pointer | 434 |
| Figure 513 | Fabric Zoning Send (FZS) – Command Dword 10 | 434 |
| Figure 514 | Fabric Zoning Send (FZS) – Command Dword 11 | 434 |
| Figure 515 | Fabric Zoning Send (FZS) – Command Dword 12 | 434 |
| Figure 516 | Fabric Zoning Send (FZS) – Command Specific Status Values | 435 |
| Figure 517 | Manage Exported Namespace – Data Pointer | 435 |
| Figure 518 | Manage Exported Namespace – Command Dword 10 | 435 |
| Figure 519 | Associate Namespace Data Structure | 436 |
| Figure 520 | Disassociate Namespace Data Structure | 437 |
| Figure 521 | Manage Exported NVM Subsystem – Data Pointer | 437 |
| Figure 522 | Manage Exported NVM Subsystem – Command Dword 10 | 438 |
| Figure 523 | Management Operation Specific: Change Access Mode operation | 438 |
| Figure 524 | Subsystem Management Data Structure | 440 |
| Figure 525 | Host Entry Data Structure | 440 |
| Figure 526 | Exported NVM Subsystem Entry Data Structure | 440 |
| Figure 527 | Modify Host Access – Command Operation Specific Status Values | 441 |
| Figure 528 | Manage Exported Port – Data Pointer | 441 |
| Figure 529 | Manage Exported Port Data Structure – Command Dword 10 | 442 |
| Figure 530 | Management Operation Specific: Create operation | 442 |
| Figure 531 | Create Data Structure | 442 |
| Figure 532 | Create Completion Queue Entry Dword 0 Data Structure | 443 |
| Figure 533 | Delete Data Structure | 443 |
| Figure 534 | Send Discovery Log Page (SDLP) – Data Pointer | 444 |
| Figure 535 | Send Discovery Log Page (SDLP) – Command Dword 10 | 444 |
| Figure 536 | Send Discovery Log Page (SDLP) – Command Dword 11 | 444 |
| Figure 537 | Send Discovery Log Page (SDLP) – Command Dword 12 | 444 |
| Figure 538 | Send Discovery Log Page (SDLP) – Command Dword 13 | 444 |
| Figure 539 | Send Discovery Log Page (SDLP) – Allowed Log Page Identifiers | 445 |
| Figure 540 | Send Discovery Log Page (SDLP) – Completion Queue Entry Dword 0 | 445 |
| Figure 541 | Fabrics Command Type | 446 |
| Figure 542 | Authentication Receive Command – Submission Queue Entry | 446 |
| Figure 543 | Authentication Receive Response | 447 |
| Figure 544 | Authentication Send Command – Submission Queue Entry | 447 |
| Figure 545 | Authentication Send Response | 448 |
| Figure 546 | Connect Command – Submission Queue Entry | 450 |
| Figure 547 | Connect Command – Data | 451 |
| Figure 548 | Connect Response | 452 |
| Figure 549 | Connect Response – Dword 0 Value Based on Status Code | 452 |
| Figure 550 | Disconnect Command – Submission Queue Entry | 453 |
| Figure 551 | Disconnect Response | 454 |
| Figure 552 | Property Get Command – Submission Queue Entry | 454 |
| Figure 553 | Property Get Response | 454 |
| Figure 554 | Property Set Command – Submission Queue Entry | 455 |
| Figure 555 | Property Set Response | 455 |
| Figure 556 | Opcodes for I/O Commands | 456 |
| Figure 557 | Cancel – Command Dword 10 | 457 |

# NVM Express® Base Specification, Revision 2.2

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 558 | Cancel – Command Dword 11 | 458 |
| Figure 559 | Cancel – Command Specific Status Values | 458 |
| Figure 560 | Cancel – Completion Queue Entry Dword 0 | 459 |
| Figure 561 | I/O Management Receive – Data Pointer | 460 |
| Figure 562 | I/O Management Receive – Command Dword 10 | 460 |
| Figure 563 | I/O Management Receive – Command Dword 11 | 460 |
| Figure 564 | Reclaim Unit Handle Status | 461 |
| Figure 565 | I/O Management Send – Data Pointer | 461 |
| Figure 566 | I/O Management Send – Command Dword 10 | 461 |
| Figure 567 | Management Operation Specific – Reclaim Unit Handle Update Operation | 462 |
| Figure 568 | Reclaim Unit Handle Update – Data Buffer | 463 |
| Figure 569 | Reservation Acquire – Data Pointer | 463 |
| Figure 570 | Reservation Acquire – Command Dword 10 | 463 |
| Figure 571 | Reservation Acquire Data Structure | 464 |
| Figure 572 | Reservation Type Encoding | 464 |
| Figure 573 | Reservation Register – Data Pointer | 465 |
| Figure 574 | Reservation Register – Command Dword 10 | 465 |
| Figure 575 | Reservation Register Data Structure | 465 |
| Figure 576 | Reservation Release – Data Pointer | 466 |
| Figure 577 | Reservation Release – Command Dword 10 | 466 |
| Figure 578 | Reservation Release Data Structure | 467 |
| Figure 579 | Reservation Report – Data Pointer | 467 |
| Figure 580 | Reservation Report – Command Dword 10 | 467 |
| Figure 581 | Reservation Report – Command Dword 11 | 468 |
| Figure 582 | Reservation Status Data Structure | 468 |
| Figure 583 | Reservation Status Extended Data Structure | 469 |
| Figure 584 | Registered Controller Data Structure | 469 |
| Figure 585 | Registered Controller Extended Data Structure | 469 |
| Figure 586 | Namespace B and C optimized through Controller 2 | 472 |
| Figure 587 | Namespace B optimized through Controller 1 | 473 |
| Figure 588 | Multiple Namespace groups | 474 |
| Figure 589 | ANA effects on Command Processing | 476 |
| Figure 590 | Boot Partition Overview | 480 |
| Figure 591 | Set Features Boot Partition Write Protection State Machine Model | 482 |
| Figure 592 | Set Features Boot Partition Write Protection State Definitions | 483 |
| Figure 593 | RPMB Boot Partition Write Protection State Machine Model | 484 |
| Figure 594 | RPMB Boot Partition Write Protection State Definitions | 484 |
| Figure 595 | Boot Partition Write Protection State Machine Model | 486 |
| Figure 596 | Example Device Self-test Operation (Informative) | 493 |
| Figure 597 | Format NVM command Aborting a Device Self-Test Operation | 494 |
| Figure 598 | Directive Types | 495 |
| Figure 599 | Directive Specific Field Interpretation | 495 |
| Figure 600 | Identify Directive – Directive Operations | 496 |
| Figure 601 | Identify Directive – Return Parameters Data Structure | 496 |
| Figure 602 | Enable Directive – Command Dword 12 | 498 |
| Figure 603 | Enable Directive – Command Specific Status Values | 498 |
| Figure 604 | Directive Streams – Stream Alignment and Granularity | 498 |
| Figure 605 | Streams – Directive Operations | 499 |
| Figure 606 | Example Multi-Stream and NSSC | 500 |
| Figure 607 | Streams Directive – Command Specific Status Values | 501 |
| Figure 608 | Streams Directive – Return Parameters Data Structure | 502 |
| Figure 609 | Streams Directive – Get Status Data Structure | 504 |
| Figure 610 | Allocate Resources – Command Dword 12 | 504 |
| Figure 611 | Allocate Resources – Completion Queue Entry Dword 0 | 504 |
| Figure 612 | Online Data Migration | 506 |
| Figure 613 | Data Replication Example 1 | 507 |
| Figure 614 | Data Replication Example 2 | 507 |
| Figure 615 | Data Replication Example 3 | 508 |
| Figure 616 | Dispersed Namespaces Command Restrictions - Prohibited Admin Commands | 511 |
| Figure 617 | Flexible Data Placement Model | 514 |
| Figure 618 | Initially Isolated Reclaim Unit Handles | 515 |
| Figure 619 | Persistently Isolated Reclaim Unit Handle | 515 |

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 620 | Host Managed Live Migration Host and Controller Naming | 518 |
| Figure 621 | CETYPE Definition | 523 |
| Figure 622 | Namespace Write Protection State Definitions | 528 |
| Figure 623 | Namespace Write Protection State Machine Model | 528 |
| Figure 624 | Commands Allowed when Specifying a Write Protected NSID | 529 |
| Figure 625 | Dynamic Power Management | 530 |
| Figure 626 | Example Power State Descriptor Table | 530 |
| Figure 627 | Workload Hints | 533 |
| Figure 628 | HCTM Example | 535 |
| Figure 629 | Deterministic and Non-Deterministic Windows | 536 |
| Figure 630 | DTWIN Attributes and Estimates | 537 |
| Figure 631 | Typical and Reliable Estimate Example | 538 |
| Figure 632 | Reachability Associations Example | 541 |
| Figure 633 | Read Recovery Level Overview | 543 |
| Figure 634 | RPMB Device Configuration Block Data Structure | 544 |
| Figure 635 | RPMB Request and Response Message Types | 545 |
| Figure 636 | RPMB Operation Result | 546 |
| Figure 637 | RPMB Contents | 547 |
| Figure 638 | RPMB Data Frame | 547 |
| Figure 639 | RPMB – Authentication Key Data Flow | 548 |
| Figure 640 | RPMB – Read Write Counter Value Flow | 549 |
| Figure 641 | RPMB – Authenticated Data Write Flow | 551 |
| Figure 642 | RPMB – Authenticated Data Read Flow | 552 |
| Figure 643 | RPMB – Authenticated Device Configuration Block Write Flow | 553 |
| Figure 644 | RPMB – Authenticated Device Configuration Block Read Flow | 554 |
| Figure 645 | Example Multi-Host System | 555 |
| Figure 646 | Command Behavior in the Presence of a Reservation | 557 |
| Figure 647 | Command Behavior in the Presence of a Reservation | 557 |
| Figure 648 | Sanitize Operations – Overwrite Mechanism | 566 |
| Figure 649 | Sanitize Operation State Machine | 569 |
| Figure 650 | Idle State Transition Conditions | 570 |
| Figure 651 | Restricted Processing State Transition Conditions | 571 |
| Figure 652 | Restricted Failure State Transition Conditions | 572 |
| Figure 653 | Unrestricted Processing State Transition Conditions | 573 |
| Figure 654 | Unrestricted Failure State Transition Conditions | 574 |
| Figure 655 | Media Verification State Transition Conditions | 575 |
| Figure 656 | Post-Verification Deallocation State Transition Conditions | 575 |
| Figure 657 | Telemetry Log Example – All Data Areas Populated | 581 |
| Figure 658 | Telemetry Log Example – Data Area 2 Populated | 582 |
| Figure 659 | UUID Index Field | 583 |
| Figure 660 | Power Loss Signaling Variables | 589 |
| Figure 661 | Power Loss Signaling Processing State Machine | 591 |
| Figure 662 | PLS States | 592 |
| Figure 663 | PLS Not Ready State Transition Conditions | 592 |
| Figure 664 | PLS Ready State Transition Conditions | 592 |
| Figure 665 | FQ Processing State Transition Conditions | 593 |
| Figure 666 | FQ Complete State Transition Conditions | 593 |
| Figure 667 | EPF Processing Port Disabled State Transition Conditions | 594 |
| Figure 668 | EPF Complete Port Disabled State Transition Conditions | 594 |
| Figure 669 | EPF Processing Port Enabled State Transition Conditions | 594 |
| Figure 670 | EPF Complete Port Enabled State Transition Conditions | 594 |
| Figure 671 | Controller Resource Allocation | 597 |
| Figure 672 | Configuration A - Two IP Interfaces | 601 |
| Figure 673 | Configuration B – Multiple IP Interfaces without a CDC | 601 |
| Figure 674 | Configuration C – Multiple IP Interfaces with a CDC | 601 |
| Figure 675 | mDNS Protocol Field | 602 |
| Figure 676 | mDNS Subtype | 602 |
| Figure 677 | mDNS Domain | 602 |
| Figure 678 | Registration and Discovery Example | 606 |
| Figure 679 | Kickstart Discovery Request and Response Sequence | 611 |
| Figure 680 | Zoning DB Abstract Representation | 611 |
| Figure 681 | ZoneDBActive Abstract Representation | 612 |

# NVM Express® Base Specification, Revision 2.2

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 682 | ZoneDBConfig Abstract Representation | 612 |
| Figure 683 | ZoneGroup Detailed Representation | 612 |
| Figure 684 | Zone Detailed Representation | 613 |
| Figure 685 | Zone Member Types | 614 |
| Figure 686 | { (NQN, Role) Zone Member Format | 614 |
| Figure 687 | { (NQN+IP+Protocol), Role) Zone Member Format | 615 |
| Figure 688 | { (NQN+IP+Protocol+IP Protocol Port), Role) Zone Member Format | 615 |
| Figure 689 | { (NQN+IP+Protocol+IP Protocol Port+PortID), Role) Zone Member Format | 616 |
| Figure 690 | { (NQN+PortID), Role) Zone Member Format | 617 |
| Figure 691 | { (NQN+Protocol+PortID+ADRFAM), Role) Zone Member Format | 617 |
| Figure 692 | { (IP+Protocol), Role) Zone Member Format | 618 |
| Figure 693 | { (IP+Protocol+IP Protocol Port), Role) Zone Member Format | 619 |
| Figure 694 | { ZoneAlias) Zone Member Format | 619 |
| Figure 695 | Zone Property Types | 619 |
| Figure 696 | Fabric Enforced Zone Property Format | 620 |
| Figure 697 | ZoneAlias Detailed Representation | 620 |
| Figure 698 | GAZ for Push Model DDC | 621 |
| Figure 699 | FZL Data for GAZ | 621 |
| Figure 700 | FZR Data for GAZ | 622 |
| Figure 701 | AAZ for Push Model DDC | 623 |
| Figure 702 | FZL Data for AAZ | 623 |
| Figure 703 | FZS Data for AAZ | 623 |
| Figure 704 | RAZ for Push Model DDC | 624 |
| Figure 705 | FZL Data for RAZ | 624 |
| Figure 706 | GAZ for Pull Model DDC | 625 |
| Figure 707 | GAZ Operation Specific Parameters for Pull Model DDC Request Log Page | 625 |
| Figure 708 | FZS Data for Pull Model GAZ | 625 |
| Figure 709 | AAZ for Pull Model DDC | 627 |
| Figure 710 | AAZ Operation Specific Parameters for Pull Model DDC Request Log Page | 627 |
| Figure 711 | FZR Data for Pull Model AAZ | 628 |
| Figure 712 | FZS Data for Pull Model AAZ | 628 |
| Figure 713 | RAZ for Pull Model DDC | 629 |
| Figure 714 | RAZ Operation Specific Parameters for Pull Model DDC Request Log Page | 629 |
| Figure 715 | FZS Data for Pull Model RAZ | 629 |
| Figure 716 | Pull Model DDC Zoning Operations Status Values | 630 |
| Figure 717 | Log Page Request Operation | 630 |
| Figure 718 | Log Page Request Operation Specific Parameters for Pull Model DDC Request Log Page | 631 |
| Figure 719 | Example reference for retrieving Underlying Namespaces and Underlying Ports | 632 |
| Figure 720 | Example reference for retrieving Underlying Namespaces and Underlying Ports | 633 |
| Figure 721 | Example steps for retrieving underlying resources and configuring an Exported NVM Subsystem | 634 |
| Figure 722 | Example steps for restricting access to an Exported NVM Subsystem to specific hosts | 634 |
| Figure 723 | Example steps for revoking specific hosts access to an Exported NVM Subsystem | 635 |
| Figure 724 | Example steps for removing an Exported NVM Subsystem | 635 |
| Figure 725 | Example steps for clearing all Exported NVM Subsystems | 635 |
| Figure 726 | Example of TLS secure channel establishment | 636 |
| Figure 727 | Example of authentication transaction for NVMe/TCP | 637 |
| Figure 728 | Unique Discovery Service NQN retrieval for bidirectional authentication | 639 |
| Figure 729 | Mapping of authentication messages to the Authentication Send command | 639 |
| Figure 730 | Mapping of authentication messages to the Authentication Receive command | 640 |
| Figure 731 | Example of TLS secure channel concatenation with NVMe/TCP | 641 |
| Figure 732 | AUTH_Negotiate message format | 642 |
| Figure 733 | Secure channel protocol identifiers | 642 |
| Figure 734 | Authentication protocol identifiers | 643 |
| Figure 735 | AUTH_Failure1 and AUTH_Failure2 message format | 643 |
| Figure 736 | AUTH_Failure reason codes | 643 |
| Figure 737 | AUTH_Failure reason code explanations | 644 |
| Figure 738 | Example of DH-HMAC-CHAP authentication transaction | 645 |
| Figure 739 | Mathematical notations for DH-HMAC-CHAP | 645 |
| Figure 740 | Authentication protocol descriptor for DH-HMAC-CHAP | 647 |
| Figure 741 | DH-HMAC-CHAP hash function identifiers | 647 |
| Figure 742 | DH-HMAC-CHAP Diffie-Hellman group identifiers | 647 |
| Figure 743 | DH-HMAC-CHAP_Challenge message format | 648 |

| Figure Number | Figure Title | Page Number |
| ---- | ---- | ---- |
| Figure 744 | DH-HMAC-CHAP_Reply message format | 649 |
| Figure 745 | DH-HMAC-CHAP_Success1 message format | 651 |
| Figure 746 | DH-HMAC-CHAP_Success2 message format | 652 |
| Figure 747 | DH-HMAC-CHAP Configurations | 655 |
| Figure 748 | NVM Subsystem AUTHREQ Settings for DH-HMAC-CHAP | 655 |
| Figure 749 | DH-HMAC-CHAP Host Behavior | 655 |
| Figure 750 | DH-HMAC-CHAP NVM Subsystem Behavior | 656 |
| Figure 751 | DH-HMAC-CHAP with TLS Concatenation Configurations | 656 |
| Figure 752 | NVM Subsystem AUTHREQ Settings for DH-HMAC-CHAP with TLS Concatenation | 656 |
| Figure 753 | DH-HMAC-CHAP with TLS Concatenation Host Behavior | 657 |
| Figure 754 | DH-HMAC-CHAP with TLS Concatenation NVM Subsystem Behavior | 658 |
| Figure 755 | Example of DH-HMAC-CHAP authentication transaction with AVE | 659 |
| Figure 756 | DH-HMAC-CHAP_Access-Request PDU format | 660 |
| Figure 757 | DH-HMAC-CHAP_Access-Result PDU format | 662 |
| Figure 758 | PRP List Describing I/O Submission Queue | 672 |
| Figure 759 | PRP List Describing Data to Compare | 673 |
| Figure 760 | Write after Write | 676 |
| Figure 761 | Non-Idempotent Command | 677 |
| Figure 762 | Retried Command Does Not Succeed | 677 |
| Figure 763 | Retried Command Affects Another Host | 678 |

# 1 Introduction

## 1.1 Overview
The NVM Express® (NVMe®) interface allows host software to communicate with a non - volatile memory subsystem (NVM subsystem). This interface is optimized for all storage solutions, attached using a variety of transports including PCI Express®, Ethernet, InfiniBand™, and Fibre Channel. The mapping of extensions defined in this document to a specific NVMe Transport are defined in an NVMe Transport binding specification. The NVMe Transport binding specification for Fibre Channel is defined in INCITS 556 Fibre Channel – Non - Volatile Memory Express - 2 (FC - NVMe - 2).

For an overview of changes from revision 2.1 to revision 2.2, refer to https://nvmexpress.org/changes for a document that describes the new features, including mandatory requirements for a controller to comply with revision 2.2.

### 1.1.1 NVM Express® Specification Family
Figure 1 shows the relationship of the NVM Express specifications to each other within the NVMe® family of specifications.

| Figure 1: NVMe Family of Specifications |
| ---- |
| <img src="figure1.png" alt="NVMe Family of Specifications" width="800"> |

The NVM Express specification family structure shown in Figure 1 is intended to show the applicability of NVM Express specifications to each other, not a hierarchy, protocol stack, or system architecture.

The NVM Express Base Specification (i.e., this specification) defines a protocol for host software to communicate with an NVM subsystem over a variety of memory - based transports and message - based transports.

The NVM Express Management Interface (NVMe - MI) Specification defines an optional management interface for all NVM Express Subsystems.

NVM Express I/O Command Set specifications define data structures, features, log pages, commands, and status values that extend the NVM Express Base Specification.

NVM Express Transport specifications define the binding of the NVMe protocol including controller properties to a specific transport.

The NVM Express Boot Specification defines constructs and guidelines for booting from NVM Express interfaces.

### 1.2 Scope
This specification defines a set of properties and commands that comprise the interface required for communication with a controller in an NVM subsystem. These properties are to be implemented by an instance of a controller using a specific NVMe Transport. This specification also defines common aspects of the NVMe I/O Command Sets that may be supported by a controller.

There are three types of controllers with different capabilities (refer to section 3.1.3):
- a) I/O controllers;
- b) Discovery controllers; and
- c) Administrative controllers.

In this document the generic term controller is often used instead of enumerating specific controller types when applicable controller types may be determined from the context.

### 1.3 Outside of Scope
The property interface and command set are specified apart from any usage model for the NVM, but rather only specifies the communication interface to the NVM subsystem. Thus, this specification does not specify whether the NVM subsystem is used as a solid-state drive, a main memory, a cache memory, a backup memory, a redundant memory, etc. Specific usage models are outside the scope, optional, and not licensed.

This specification defines requirements and behaviors that are implementation agnostic. The implementation of these requirements and behaviors are outside the scope of this specification. For example, an NVM subsystem that follows this specification may be implemented by an SSD that attaches directly to a fabric, a device that translates between a fabric and a PCIe NVMe SSD, or software running on a general-purpose server.

This interface is specified above any non-volatile media management, like wear leveling. Erases and other management tasks for NVM technologies like NAND are abstracted.

This specification does not contain any information on caching algorithms or techniques.

The implementation or use of other published specifications referred to in this specification, even if required for compliance with the specification, are outside the scope of this specification (e.g., PCI, PCI Express, and PCI-X). This includes published specifications for fabrics and other technologies referred to by this document or any NVMe Transport binding specification.

### 1.4 Conventions
#### 1.4.1 Keywords
Several keywords are used to differentiate between different levels of requirements.

##### 1.4.1.1 mandatory
A keyword indicating items to be implemented as defined by this specification.

##### 1.4.1.2 may
A keyword that indicates flexibility of choice with no implied preference.

##### 1.4.1.3 obsolete
A keyword indicating functionality that was defined in a previous version of the NVM Express specification and that has been removed from this specification.

### 1.4.1.4 optional
A keyword that describes features that are not required by this specification. However, if any optional feature defined by the specification is implemented, the feature shall be implemented in the way defined by the specification.

### 1.4.1.5 R
"R" is used as an abbreviation for "reserved" when the figure or table does not provide sufficient space for the full word "reserved".

### 1.4.1.6 reserved
A keyword referring to bits, bytes, words, fields, and opcode values that are set - aside for future standardization. Their use and interpretation may be specified by future extensions to this or other specifications. A reserved bit, byte, word, field, property, or register shall be cleared to 0h, or in accordance with a future extension to this specification. The recipient of a command or a register write is not required to check reserved bits, bytes, words, or fields. Receipt of reserved coded values in defined fields in commands shall be reported as an error. Writing a reserved coded value into a controller property field produces undefined results.

### 1.4.1.7 shall
A keyword indicating a mandatory requirement. Designers are required to implement all such mandatory requirements to ensure interoperability with other products that conform to the specification.

### 1.4.1.8 should
A keyword indicating flexibility of choice with a strongly preferred alternative. Equivalent to the phrase "it is recommended".

### 1.4.2 Numerical Descriptions
A 0's based value is a numbering scheme in which the number 0h represents a value of 1h, 1h represents 2h, 2h represents 3h, etc. In this numbering scheme, there is no method to represent the value of 0h. Values in this specification are 1 - based (i.e., the number 1h represents a value of 1h, 2h represents 2h, etc.) unless otherwise specified.

Size values are shown in binary units or decimal units. The symbols used to represent these values are as shown in Figure 2.

| Decimal |  |  | Binary |  |
| ---- | ---- | ---- | ---- | ---- |
| Symbol | Power (base - 10) |  | Symbol | Power (base - 2) |
| kilo / k | \(10^{3}\) |  | kibi / Ki | \(2^{10}\) |
| mega / M | \(10^{6}\) |  | mebi / Mi | \(2^{20}\) |
| giga / G | \(10^{9}\) |  | gibi / Gi | \(2^{30}\) |
| tera / T | \(10^{12}\) |  | tebi / Ti | \(2^{40}\) |
| peta / P | \(10^{15}\) |  | pebi / Pi | \(2^{50}\) |
| exa / E | \(10^{18}\) |  | exbi / Ei | \(2^{60}\) |
| zetta / Z | \(10^{21}\) |  | zebi / Zi | \(2^{70}\) |
| yotta / Y | \(10^{24}\) |  | yobi / Yi | \(2^{80}\) |

The ^ operator is used to denote the power to which that number, symbol, or expression is to be raised.

Some parameters are defined as an ASCII string. ASCII strings shall contain only code values (i.e., byte values or octet values) 20h through 7Eh. For the string "Copyright", the character "C" is the first byte, the character "o" is the second byte, etc. ASCII strings are left justified. If padding is necessary, then the string shall be padded with spaces (i.e., ASCII character 20h) to the right unless the string is specified as null
terminated. 
Some parameters are defined as a UTF-8 string. UTF-8 strings shall contain only byte values (i.e., octet values) 20h through 7Eh, 80h through BFh, and C2h through F4h (refer to sections 1 to 3 of RFC 3629). 
For the string “Copyright”, the character “C” is the first byte, the character “o” is the second byte, etc. UTF-8 
strings are left justified. If padding is necessary, then the string shall be padded with spaces (i.e., ASCII character 20h, Unicode character U+0020) to the right unless the string is specified as null-terminated. 
If padding is necessary for a field that contains a null-terminated string then the field should be padded with nulls (i.e., ASCII character 00h, Unicode character U+0000) to the right of the string. 
A hexadecimal ASCII string is an ASCII string that uses a subset of the code values: “0” to “9”, “A” to “F” uppercase, and “a” to “f” lowercase. 
Hexadecimal (i.e., base 16) numbers are written with a lower case “h” suffix (e.g., 0FFFh, 80h). 
Hexadecimal numbers larger than eight digits are represented with an underscore character dividing each group of eight digits (e.g., 1E_DEADBEEFh). 
Binary (i.e., base 2) numbers are written with a lower case “b” suffix (e.g., 1001b, 10b). Binary numbers larger than four digits are written with an underscore character dividing each group of four digits (e.g., 1000_0101_0010b). 
All other numbers are decimal (i.e., base 10). A decimal number is represented in this specification by any sequence of digits consisting of only the Western-Arabic numerals 0 to 9 not immediately followed by a 
lower-case b or a lower-case h (e.g., 175). This specification uses the following conventions for representing decimal numbers: 
a) the decimal separator (i.e., separating the integer and fractional portions of the number) is a period; 
b) the thousands separator (i.e., separating groups of three decimal digits in a portion of the number) 
is a comma; 
c) the thousands separator is used in only the integer portion of a number and not the fractional portion 
of a number; and 
d) the decimal representation for a year does not include a comma (e.g., 2019 instead of 2,019).

### 1.4.3 Byte, Word, and Dword Relationships
Figure 3 illustrates the relationship between bytes, words and dwords. A qword (quadruple word) is a unit of data that is four times the size of a word; it is not illustrated due to space constraints. Unless otherwise specified, this specification specifies data in a little endian format.

**Figure 3: Byte, Word, and Dword Relationships**

- **Byte**: Represented with bits labeled 7 to 0.
- **Word**: Composed of two bytes (byte 1 and byte 0). The bit labeling shows a 16 - bit structure with higher bits (15 - 8) and lower bits (7 - 0).
- **Dword**: Composed of two words (word 1 and word 0) or four bytes (byte 3, byte 2, byte 1, byte 0). The bit labeling shows a 32 - bit structure with higher bits (31 - 16) and lower bits (15 - 0).

### 1.5 Definitions
#### 1.5.1 admin label
An admin label is an administratively configured ASCII or UTF - 8 string (refer to section 1.4.2) that may be used to help identify specific NVMe entities (i.e., Hosts, NVM subsystems and namespaces). An admin label is capable of describing the entity's physical location, DNS name or other information.

#### 1.5.2 admin label ASCII
An ASCII string. Refer to section 1.4.2 for ASCII string requirements. Refer to section 1.5.1 for admin label usage.

### 1.5.3 admin label UTF - 8
A UTF - 8 string. Refer to section 1.4.2 for UTF - 8 string requirements. Refer to section 1.5.1 for admin label usage.

### 1.5.4 Admin Queue
The Admin Queue is the Submission Queue and Completion Queue with identifier 0. The Admin Submission Queue and corresponding Admin Completion Queue are used to submit administrative commands and receive completions for those administrative commands, respectively.
The Admin Submission Queue is uniquely associated with the Admin Completion Queue.

### 1.5.5 Administrative controller
A controller that exposes capabilities that allow a host to manage an NVM subsystem. An Administrative controller does not implement I/O Queues, provide access to data or metadata associated with user data on a non - volatile storage medium, or support namespaces attached to the Administrative controller (i.e., there are never any active NSIDs).

### 1.5.6 allocated namespace
A namespace that is associated with an allocated NSID.

### 1.5.7 Allowed Host List
A list of hosts (identified by Host NQN and Host Identifier) present in each Exported NVM Subsystem that are granted access to the Exported NVM Subsystem via an Exported Port.

### 1.5.8 arbitration burst
The maximum number of commands that may be fetched by an arbitration mechanism at one time from a Submission Queue.

### 1.5.9 arbitration mechanism
The method used to determine which Submission Queue is selected next to fetch commands for execution by the controller. Refer to section 3.4.4.

### 1.5.10 association
An exclusive communication relationship between a particular controller and a particular host that encompasses the Admin Queue and all I/O Queues of that controller.

### 1.5.11 audit
The process of accessing media to determine correct operation of a sanitize operation. Refer to section 8.1.24 and to ISO/IEC 27040.

### 1.5.12 authentication commands
Used to refer to Fabrics Authentication Send or Authentication Receive commands.

### 1.5.13 cache
A data storage area used by the NVM subsystem, that is not accessible to a host, and that may contain a subset of user data stored in the non - volatile storage media or may contain user data that is not committed to non - volatile storage media.

### 1.5.14 candidate command
A candidate command is a submitted command which has been transferred into the controller and the controller deems ready for processing.

### NVM Express® Base Specification, Revision 2.2

#### 1.5.15 capsule
An NVMe unit of information exchange used in NVMe over Fabrics. A capsule contains a command or response and may optionally contain command/response data and SGLs.

#### 1.5.16 Centralized Discovery controller (CDC)
A Discovery controller that reports discovery information registered by Direct Discovery controllers and hosts.

#### 1.5.17 Channel
A Channel represents a communication path between the controller and one or more Media Units in an NVM subsystem.

#### 1.5.18 command completion
A command is completed when the controller has completed processing the command, has updated status information in the completion queue entry, and has posted the completion queue entry to the associated Completion Queue.

#### 1.5.19 command submission
For memory-based transport model (e.g., PCIe) implementations, a command is submitted when a Submission Queue Tail Doorbell write has completed that moves the Submission Queue Tail Pointer value past the Submission Queue slot in which the command was placed.  
For message-based transport model (e.g., NVMe over Fabrics) implementations, a command is submitted when a host adds a capsule to a Submission Queue.

#### 1.5.20 controller
A controller is the interface between a host and an NVM subsystem. There are three types of controllers:  
a) I/O controllers;  
b) Discovery controllers; and  
c) Administrative controllers.  
A controller executes commands submitted by a host on a Submission Queue and posts a completion on a Completion Queue. All controllers implement one Admin Submission Queue and one Admin Completion Queue. Depending on the controller type, a controller may also implement one or more I/O Submission Queues and I/O Completion Queues. When PCI Express is used as the transport, then a controller is a PCI Express function.

#### 1.5.21 Controller Reset
Host modification of the CC property that clears CC.EN from '1' to '0' (refer to section 3.7.2).

#### 1.5.22 Directive
A method of information exchange between a host and either an NVM subsystem or a controller. Information may be transmitted using the Directive Send and Directive Receive commands. A subset of I/O commands may include a Directive Type field and a Directive Specific field to communicate more information that is specific to the associated I/O command. Refer to section 8.1.8.

#### 1.5.23 Direct Discovery controller (DDC)
A Discovery controller that is capable of registering discovery information with a Centralized Discovery controller.

### 1.5.24 Discovery controller
A controller that exposes capabilities that allow a host to retrieve a Discovery Log Page. A Discovery controller does not implement I/O Queues or provide access to a non - volatile storage medium. Refer to section 3.1.3.3.

### 1.5.25 discovery information
Information about a host or NVM subsystem that is used for discovery (e.g., NVMe Transport address, NQN, etc.).

### 1.5.26 Discovery Service
An NVM subsystem that supports Discovery controllers only. A Discovery Service shall not support a controller that exposes namespaces.

### 1.5.27 dispersed namespace
A shared namespace that may be concurrently accessed by controllers in two or more NVM subsystems (refer to section 8.1.9).

### 1.5.28 dynamic controller
The controller is allocated on demand with no state (e.g., Feature settings) preserved from prior associations.

### 1.5.29 Domain
A domain is the smallest indivisible unit that shares state (e.g., power state, capacity information).

### 1.5.30 embedded management controller
An embedded management controller is a Management Controller (refer to the NVM Express Management Interface Specification) that provides an external management interface (e.g., Redfish®), typically implemented via commands to the Management Endpoint.

### 1.5.31 emulated controller
An NVM Express controller that is defined in software. An emulated controller may or may not have an underlying physical NVMe controller (e.g., physical PCIe function).

### 1.5.32 Endurance Group
A portion of non - volatile storage in the NVM subsystem whose endurance is managed as a group. Refer to section 3.2.3.

### 1.5.33 Entry Key
A set of discovery information entry fields that allow for the unique identification of each discovery information entry registered with the CDC or DDC. Refer to the Entry Key Type (EKTYPE) field.

### 1.5.34 Exported Namespace
A namespace in an Exported NVM Subsystem.

### 1.5.35 Exported NVM Resources
NVM resources created to enable remote access to physical NVM resources that includes:
- a) Exported NVM Subsystems;
- b) Exported Namespaces; and
- c) Exported Ports.

### NVM Express® Base Specification, Revision 2.2

#### 1.5.36 Exported NVM Subsystem
A logical NVM subsystem that exports underlying NVM resources and that:
- a) contains zero or more Exported Namespaces;
- b) contains zero or more controllers;
- c) contains zero or more Exported Ports; and
- d) may contain an Allowed Host List.

#### 1.5.37 Exported Port
A port used to export an NVMe subsystem over a specific fabrics transport and represented by an Exported Port ID.

#### 1.5.38 Exported Port ID
A port identifier used to specify an Exported Port.

#### 1.5.39 fabric (network fabric)
A network topology in which nodes pass data to each other.

#### 1.5.40 Fabric Zoning
A technique to specify access control configurations between hosts and NVM subsystems.

#### 1.5.41 firmware/boot partition image update command sequence
The sequence of one or more Firmware Image Download commands that download a firmware image or a boot partition image followed by a Firmware Commit command that commits that downloaded image to a firmware slot or a boot partition.

#### 1.5.42 firmware slot
A firmware slot is a location in a domain used to store a firmware image. The domain stores from one to seven firmware images. Controllers in the same domain share the same firmware slots.

#### 1.5.43 host
An entity that interfaces to an NVM subsystem through one or more controllers and submits commands to Submission Queues and retrieves command completions from Completion Queues.

#### 1.5.44 host-accessible memory
Memory that the host is able to access (e.g., host memory, Controller Memory Buffer (CMB), Persistent Memory Region (PMR)).

#### 1.5.45 host management agent
A host management agent is a part of the host that provides an external management interface (e.g., Redfish) to external managers, typically via Admin commands to the controller (refer to the NVM Express Management Interface Specification).

#### 1.5.46 host memory
Memory that may be read and written by both a host and a controller and that is not exposed by a controller (i.e., Controller Memory Buffer or Persistent Memory Region). Host memory may be implemented inside or outside a host (e.g., a memory region exposed by a device that is neither the host nor controller).

#### 1.5.47 idempotent command
A command that produces the same end state in the NVM subsystem and returns the same results if that command is resubmitted one or more times with no intervening commands. Refer to section 9.6.3.1.

### 1.5.48 Identify Controller data structures
All controller data structures that are able to be retrieved via the Identify command:
- Identify Controller data structure (i.e., CNS 01h); and
- each of the I/O Command Set specific Identify Controller data structure (i.e., CNS 06h).

### 1.5.49 Identify Namespace data structures
All namespace data structures that are able to be retrieved via the Identify command:
- Identify Namespace data structures (i.e., CNS 00h, CNS 09h, and CNS 11h);
- I/O Command Set Independent Identify Namespace data structures (i.e., CNS 08h and CNS 1Fh); and
- I/O Command Set specific Identify Namespace data structures (i.e., CNS 05h, CNS 0Ah, and CNS 1Bh).

### 1.5.50 I/O command
An I/O command is a command submitted to an I/O Submission Queue.

### 1.5.51 I/O Completion Queue
An I/O Completion Queue is a Completion Queue that is used to indicate command completions and is associated with one or more I/O Submission Queues.

### 1.5.52 I/O controller
A controller that implements I/O queues and is intended to be used to access a non-volatile storage medium.

### 1.5.53 I/O Submission Queue
An I/O Submission Queue is a Submission Queue that is used to submit I/O commands for execution by the controller (e.g., Read command and Write command for the NVM Command Set).

### 1.5.54 Media Unit
A Media Unit represents a component of the underlying media in an NVM subsystem. Endurance Groups are composed of Media Units.

### 1.5.55 memory-based controller
A controller that supports a memory-based transport model (e.g., a PCIe implementation).

### 1.5.56 message-based controller
A controller that supports a message-based transport model (e.g., a Fabrics implementation).

### 1.5.57 metadata
Metadata is contextual information related to formatted user data (e.g., a particular LBA of data as defined in the NVM Command Set Specification). The host may include metadata to be stored by the NVM subsystem if storage space is provided by the controller. Refer to the applicable I/O Command Set specification for details.

### 1.5.58 MMC
A Migration Management Controller. Refer to section 8.1.12.

### 1.5.59 MMH
A Migration Management Host. Refer to section 8.1.12.

### 1.5.60 MMHD
A Migration Management Host associated with a Migration Management Controller in a Destination NVM Subsystem. Refer to section 8.1.12.

### 1.5.61 MMHS
A Migration Management Host associated with a Migration Management Controller in a Source NVM Subsystem. Refer to section 8.1.12.

### 1.5.62 namespace
A set of resources that may be directly accessed by a host (e.g., formatted non - volatile storage).

### 1.5.63 namespace ID (NSID)
An identifier used by a controller to provide access to a namespace or the name of the field in the SQE that contains the namespace identifier (refer to Figure 92). Refer to section 3.2.1 for the definitions of valid NSID, invalid NSID, active NSID, inactive NSID, allocated NSID, and unallocated NSID.

### 1.5.64 NVM
NVM is an acronym for non - volatile memory.

### 1.5.65 NVM Set
A portion of NVM from an Endurance Group. Refer to section 3.2.2.

### 1.5.66 NVM subsystem
An NVM subsystem includes one or more domains, one or more controllers, zero or more namespaces, and one or more ports. An NVM subsystem may include a non - volatile storage medium and an interface between the controller(s) in the NVM subsystem and non - volatile storage medium.

### 1.5.67 NVM subsystem port
An NVMe over Fabrics protocol interface between an NVM subsystem and a fabric. An NVM subsystem port is a collection of one or more physical fabric interfaces that together act as a single interface.

### 1.5.68 NVMe over Fabrics
An implementation of the NVM Express interface that complies with either the message - only transport model or the message/memory transport model (refer to Figure 4 and section 2.2).

### 1.5.69 NVMe Transport
A protocol layer that provides reliable delivery of data, commands, and responses between a host and an NVM subsystem. The NVMe Transport layer is layered on top of the fabric. It is independent of the fabric physical interconnect and low - level fabric protocol layers.

### 1.5.70 NVMe Transport binding specification
A specification of reliable delivery of data, commands, and responses between a host and an NVM subsystem for an NVMe Transport. The binding may exclude or restrict functionality based on the NVMe Transport’s capabilities.

### 1.5.71 participating NVM subsystem
An NVM subsystem that participates in (i.e., contains controllers that provide access to) a dispersed namespace.

### 1.5.72 physical fabric interface (physical ports)
A physical connection between an NVM subsystem and a fabric.

### 1.5.73 Placement Handle
A namespace scoped handle that maps to an Endurance Group scoped Reclaim Unit Handle which references a Reclaim Unit in each Reclaim Group.

### 1.5.74 Placement Identifier
A data structure that specifies a Reclaim Group Identifier and a Placement Handle that references a Reclaim Unit. Refer to Figure 283 and Figure 284.

### 1.5.75 Port ID
An identifier that is associated with an NVM subsystem port. Refer to section 2.2.2.

### 1.5.76 Ports List
A list of ports that may be used to export an NVM subsystem. Entries in the Ports List are in the format specified by Underlying Fabrics Transport Entry data structure (refer to Figure 337).

### 1.5.77 Power Loss Acknowledge (PLA)
The transport-specific variable that is used by the controller to inform the host of the controller's current Power Loss Signaling processing (refer to section 8.2.5).

### 1.5.78 Power Loss Notification (PLN)
The transport-specific variable that is used to inform the controller that a main power loss event is expected to occur (refer to section 8.2.5).

### 1.5.79 primary controller
An NVM Express controller that supports the Virtualization Management command. An NVM subsystem may contain multiple primary controllers. Secondary controller(s) in an NVM subsystem depend on a primary controller for dynamic resource management (refer to section 8.2.6).
A PCI Express SR-IOV Physical Function that supports the NVM Express interface and the Virtualization Enhancements capability is an example of a primary controller (refer to section 8.2.6.4).

### 1.5.80 private namespace
A namespace that is only able to be attached to one controller at a time. Refer to the Namespace Multi-path I/O and Namespace Sharing Capabilities (NMIC) field in Figure 320.

### 1.5.81 property
The generalization of memory mapped controller registers defined for NVMe over PCIe. Properties are used to configure low level controller attributes and obtain low level controller status. Refer to section 3.1.4.

### 1.5.82 Reclaim Group (RG)
An entity that contains one or more Reclaim Units. Refer to section 3.2.4.

### 1.5.83 Reclaim Unit (RU)
A logical representation of non-volatile storage within a Reclaim Group that is able to be physically erased by the controller without disturbing any other Reclaim Units. Refer to section 3.2.4.

### 1.5.84 Reclaim Unit Handle (RUH)
A controller resource that references a Reclaim Unit in each Reclaim Group. Refer to section 3.2.4.

### NVM Express® Base Specification, Revision 2.2

#### 1.5.85 rotational media
Media that stores data on rotating platters (refer to section 8.1.23).

#### 1.5.86 Runtime D3 (Power Removed)
In Runtime D3 (RTD3) main power is removed from the controller. Auxiliary power may or may not be provided. For PCI Express, RTD3 is the D3<sub>cold</sub> power state (refer to section 8.1.17.4).

#### 1.5.87 sanitize operation
Process by which all user data in the NVM subsystem is altered such that recovery of the previous user data from any cache or the non-volatile storage media is infeasible for a given level of effort (refer to IEEE 2883™-2022).

#### 1.5.88 sanitization target
The target of a sanitize operation (i.e., an NVM subsystem).

#### 1.5.89 secondary controller
An NVM Express controller that depends on a primary controller in an NVM subsystem for management of some controller resources (refer to section 8.2.6).
A PCI Express SR-IOV Virtual Function that supports the NVM Express interface and receives resources from a primary controller is an example of a secondary controller (refer to section 8.2.6.4).

#### 1.5.90 shared namespace
A namespace that may be attached to two or more controllers in an NVM subsystem concurrently. Refer to the Namespace Multi-path I/O and Namespace Sharing Capabilities (NMIC) field in Figure 320.

#### 1.5.91 specified namespace
The namespace that is associated with the value specified by the Namespace Identifier (NSID) field in a command as defined by the Common Command Format (refer to Figure 92).

#### 1.5.92 spindown
The process of changing a spindle from an operational power state to a non-operational power state, for an Endurance Group that stores data on rotational media (refer to section 8.1.23).

#### 1.5.93 spinup
The process of changing a spindle from a non-operational power state to an operational power state, for an Endurance Group associated with rotational media (refer to section 8.1.23).

#### 1.5.94 static controller
The controller is pre-existing with a specific Controller ID and its state (e.g., Feature settings) is preserved from prior associations.

#### 1.5.95 Underlying Namespace
A namespace (defined in section 1.5.62) accessible through physical or virtual functions in an Underlying NVM Subsystem that may be used to associate with an Exported NVM Subsystem. Underlying Namespaces are identified by the Underlying Namespace Entry data structure (refer to Figure 335).

#### 1.5.96 Underlying Namespace List
A list of namespaces (refer to section 5.1.13.4.1) in all underlying NVM subsystems that may be used to create an Exported Namespace.

### 1.5.97 Underlying NVM Subsystem
Defined as NVM subsystem.

### 1.5.98 Underlying Port
A port through which an NVMe subsystem is attached to a transport (e.g., Ethernet, InfiniBand, Fibre Channel) (refer to section 1.5.72).

### 1.5.99 user data
Data stored in a namespace that is composed of data that the host may store and later retrieve including metadata if supported.

### 1.6 I/O Command Set specific definitions used in this specification
The following terms used in this specification are defined in each I/O Command Set specification.

#### 1.6.1 Endurance Group Host Read Command
An I/O Command Set specific command that results in the controller reading user data, but may or may not return the data to the host.

#### 1.6.2 Format Index
A value used to index into the I/O Command Set Specific Format table (i.e., the User Data Format number).

#### 1.6.3 SMART Data Units Read Command
An I/O Command Set specific command that results in the controller reading user data, but may or may not return the data to the host.

#### 1.6.4 SMART Host Read Command
An I/O Command Set specific command that results in the controller reading user data, but may or may not return the data to the host.

#### 1.6.5 User Data Format
An I/O Command Set specific format that describes the layout of the data on the NVM media.

#### 1.6.6 User Data Out Command
An I/O Command Set specific command that results in the controller writing user data, but may or may not transfer user data from the host to the controller.

### 1.7 NVM Command Set specific definitions used in this specification
The following terms used in this specification are defined in the NVM Command Set Specification. These terms are used throughout the document as examples for a specific I/O Command Set.

#### 1.7.1 logical block
The smallest addressable data unit for Read and Write commands.

#### 1.7.2 logical block address (LBA)
The address of a logical block, referred to commonly as LBA.

### 1.8 References
CNSA 1.0, "USE OF PUBLIC STANDARDS FOR SECURE INFORMATION SHARING", CNSSP 15 ANNEX B "NSA-APPROVED COMMERCIAL NATIONAL SECURITY ALGORITHM (CNSA) SUITE", 20 October 2016. Available from https://www.cnss.gov/CNSS/issuances/Policies.cfm.

### NVM Express® Base Specification, Revision 2.2

- **IEEE Std 2883™-2022**: IEEE Standard for Sanitizing Storage. Available from https://standards.ieee.org.
- **INCITS 502 - 2019**: Information Technology – SCSI Primary Commands - 5 (SPC - 5). Available from https://webstore.ansi.org.
- **INCITS 556 - 2020**: Information Technology – Non - Volatile Memory Express - 2 (FC - NVMe - 2). Available from https://webstore.ansi.org.
- **ISO 8601**: Data elements and interchange formats – Information interchange – Representations of dates and times. Available from https://www.iso.org.
- **ISO/IEC 27040:2024**: Information technology – Security techniques – Storage security. Available from https://www.iso.org.
- **JEDEC JESD218B - 02**: Solid State Drive (SSD) Requirements and Endurance Test Method standard. Available from https://www.jedec.org.
- **NVM Express Boot Specification, Revision 1.2**: Available from https://www.nvmexpress.org.
- **NVM Express Management Interface Specification, Revision 2.0**: Available from https://www.nvmexpress.org.
- **NVM Express NVM Command Set Specification, Revision 1.1**: Available from https://www.nvmexpress.org.
- **NVM Express Zoned Namespace Command Set Specification, Revision 1.3**: Available from https://www.nvmexpress.org.
- **NVM Express Key Value Command Set Specification, Revision 1.2**: Available from https://www.nvmexpress.org.
- **NVM Express NVMe over PCIe Transport Specification, Revision 1.2**: Available from https://www.nvmexpress.org.
- **NVM Express RDMA Transport Specification, Revision 1.1**: Available from https://www.nvmexpress.org.
- **NVM Express TCP Transport Specification, Revision 1.1**: Available from https://www.nvmexpress.org.
- **PCI - SIG PCI Express® Base Specification, Revision 6.2**: Available from https://www.pcisig.com.
- **RFC 1952**: P. Deutsch, "GZIP file format specification version 4.3", May 1996. Available from https://www.rfc - editor.org/info/rfc1952.
- **RFC 1994**: W. Simpson, "PPP Challenge Handshake Authentication Protocol (CHAP)", August 1996. Available from https://www.rfc - editor.org/info/rfc1994.
- **RFC 2104**: H. Krawczyk, M. Bellare, R. Canetti, "HMAC: Keyed - Hashing for Message Authentication", February 1997. Available from https://www.rfc - editor.org/info/rfc2104.
- **RFC 2631**: E. Rescorla, "Diffie - Hellman Key Agreement Method", June 1999. Available from https://www.rfc - editor.org/info/rfc2631.
- **RFC 3629**: F. Yergeau, "UTF - 8, a transformation format of ISO 10646", November 2003. Available from https://www.rfc - editor.org/info/rfc3629.
- **RFC 3986**: T. Berners - Lee, R. Fielding, L. Masinter, "Uniform Resource Identifier (URI): Generic Syntax", January 2005. Available from https://www.rfc - editor.org/info/rfc3986.
- **RFC 4086**: D. Eastlake 3rd, J. Schiller, S. Crocker, "Randomness Requirements for Security", June 2005. Available from https://www.rfc - editor.org/info/rfc4086.
- **RFC 4088**: D. Black, K. McCloghrie, J. Schoenwaelder, "Uniform Resource Identifier (URI) Scheme for the Simple Network Management Protocol (SNMP)", June 2005. Available from https://www.rfc - editor.org/info/rfc4088.
- **RFC 4301**: S. Kent, K. Seo, "Security Architecture for the Internet Protocol", December 2005. Available from https://www.rfc - editor.org/info/rfc4301.

### 1.9 References Under Development
None.

# NVM Express® Base Specification, Revision 2.2

## 2 Theory of Operation

The NVM Express scalable interface is designed to address the needs of storage systems that utilize PCI Express based solid state drives or fabric connected devices. The interface provides optimized command submission and completion paths. It includes support for parallel operation by supporting up to 65,535 I/O Queues with up to 65,535 outstanding commands per I/O Queue. Additionally, support has been added for many Enterprise capabilities like end-to-end data protection (compatible with SCSI Protection Information, commonly known as T10 DIF, and SNIA DIX standards), enhanced error reporting, and virtualization.

The interface has the following key attributes:
- Does not require uncacheable / MMIO register reads in the command submission or completion path;
- A maximum of one MMIO register write or one 64B message is necessary in the command submission path;
- Support for up to 65,535 I/O Queues, with each I/O Queue supporting up to 65,535 outstanding commands;
- Priority associated with each I/O Queue with well-defined arbitration mechanism;
- All information to complete a 4 KiB read request is included in the 64B command itself, ensuring efficient small I/O operation;
- Efficient and streamlined command set;
- Support for MSI/MSI-X and interrupt aggregation;
- Support for multiple namespaces;
- Efficient support for I/O virtualization architectures like SR-IOV;
- Robust error reporting and management capabilities; and
- Support for multi-path I/O and namespace sharing.

This specification defines a streamlined set of properties that are used to configure low level controller attributes and obtain low level controller status. These properties have a transport specific mechanism for defining access (e.g., memory-based transports use registers, whereas message-based transports use the Property Get and Property Set commands). The following are examples of functionality defined in properties:
- Indication of controller capabilities;
- Status for controller failures (command status is provided in a CQE);
- Admin Queue configuration (I/O Queue configuration processed via Admin commands); and
- Doorbell registers for a scalable number of Submission and Completion Queues.

There are two defined models for communication between the host and the NVM subsystem, a memory-based transport model and a message-based transport model. All NVM subsystems require the underlying NVMe Transport to provide reliable NVMe command and data delivery. An NVMe Transport is an abstract protocol layer independent of any physical interconnect properties. A taxonomy of NVMe Transports, along with examples, is shown in Figure 4. An NVMe Transport may expose a memory-based transport model or a message-based transport model. The message-based transport model has two subtypes: the message-only transport model and the message/memory transport model.

A memory-based transport model is one in which commands, responses, and data are transferred between a host and an NVM subsystem by performing explicit memory read and write operations (e.g., over PCIe).

A message-based transport model is one in which messages containing command capsules and response capsules are sent between a host and an NVM subsystem (e.g., over a fabric). The two subtypes of message-based transport models are differentiated by how data is sent between a host and an NVM subsystem. In the message-only transport model data is only sent between a host and an NVM subsystem using capsules or messages. The message/memory transport model uses a combination of messages and explicit memory read and write operations to transfer command capsules, response capsules and data between a host and an NVM subsystem. Data may optionally be included in command capsules and response capsules. Both the message-only transport model and the message/memory transport model are

### NVM Express® Base Specification, Revision 2.2

Referenced as message - based transport models throughout this specification when the description is applicable to both subtypes.

An NVM subsystem is made up of a single domain or multiple domains as described in section 3.2.5. An NVM subsystem may optionally include a non - volatile storage medium, and an interface between the controller(s) of the NVM subsystem and the non - volatile storage medium. Controllers expose this non - volatile storage medium to hosts through namespaces. An NVM subsystem is not required to have the same namespaces attached to all controllers. An NVM subsystem that supports a Discovery controller does not support any other controller type. A Discovery Service is an NVM subsystem that supports Discovery controllers only (refer to section 3.1).

#### Figure 4: Taxonomy of Transport Models
**NVMe Transport Models**
- **Memory**: Commands/Responses & Data use Shared Memory. Example Transport: PCI Express.
- **Message**: Commands/Responses use Capsules. Data may use Capsules or Messages. Example Transports: Fibre Channel, TCP.
- **Message/Memory**: Commands/Responses use Capsules. Data may use Capsules or Shared Memory. Example Transports: RDMA (InfiniBand, RoCE, iWARP).

The capabilities and settings that apply to an NVM Express controller are indicated in the Controller Capabilities (CAP) property and the Identity Controller data structure (refer to Figure 13).

A namespace is a set of resources (e.g., formatted non - volatile storage) that may be accessed by a host. A namespace has an associated namespace identifier that a host uses to access that namespace. The set of resources may consist of non - volatile storage and/or other resources.

Associated with each namespace is an I/O Command Set that operates on that namespace. An NVM Express controller may support multiple namespaces. Namespaces may be created and deleted using the Namespace Management command and Capacity Management command. The Identity Namespace data structures (refer to section 1.5.49) indicate capabilities and settings that are specific to a particular namespace.

The NVM Express interface is based on a paired Submission and Completion Queue mechanism. Commands are placed by host software into a Submission Queue. Completions are placed into the associated Completion Queue by the controller.

There are three types of commands that are defined in NVM Express: Admin commands, I/O commands, and Fabrics commands. Figure 5 shows these different command types.

### NVM Express® Base Specification, Revision 2.2

#### Figure 5: Types of NVMe Command Sets

| NVMe Command Sets |
| ---- |
| Admin Command Set |
| I/O Command Sets |
| Fabrics Command Set |

- **Admin Command Set**: An Admin Submission Queue and associated Completion Queue exist for controller management (e.g., creating/deleting I/O Queues, aborting commands). Only commands from this set or Fabrics Command Set can be submitted to the Admin Submission Queue.
- **I/O Command Sets**: Used with an I/O queue pair. Defines common I/O commands. Examples include NVM Command Set, Key Value Command Set, Zoned Namespace Command Set. Other sets like Computational Programs and SLM Command Sets also exist.
- **Fabrics Command Set**: NVMe over Fabrics specific. Used for operations like connection establishment, in - band authentication. Commands can be submitted on Admin or I/O Submission Queues. Processed by controller regardless of CC.EN state.

### 2.1 Memory - Based Transport Model (PCIe)

- **Queue Allocation**: In the memory - based model, Submission and Completion Queues are allocated in memory. Host software creates queues (up to controller - supported max). Number based on system config/workload. E.g., on a 4 - core processor system, may have a queue pair per core.
- **Queue Pair Mapping**: Figure 6 shows a 1:1 mapping between Submission and Completion Queues. Figure 7 shows multiple I/O Submission Queues using the same I/O Completion Queue (Core B). Always a 1:1 mapping between Admin Submission and Completion Queues.

### Figure 6: Queue Pair Example, 1:1 Mapping
- **Host**:
  - **Controller Mgmt**:
    - Admin Submission Queue
    - Admin Completion Queue
  - **Core 0**:
    - I/O Submission Queue 1
    - I/O Completion Queue 1
  - **Core 1**:
    - I/O Submission Queue 2
    - I/O Completion Queue 2
  - **Core N-1**:
    - I/O Submission Queue N
    - I/O Completion Queue N

### Figure 7: Queue Pair Example, n:1 Mapping
- **Host**:
  - **Controller Mgmt**:
    - Admin Submission Queue
    - Admin Completion Queue
  - **Core A**:
    - I/O Submission Queue M
    - I/O Completion Queue N
  - **Core B**:
    - I/O Submission Queue X
    - I/O Submission Queue Y
    - I/O Submission Queue Z
    - I/O Completion Queue W

### Submission Queue (SQ)
- A circular buffer with a fixed slot size.
- Host software uses it to submit commands for controller execution.
- Host updates SQ Tail doorbell register when new commands (1 to n) are ready.
- Controller fetches SQ entries in order.
- Each submission queue entry is 64 bytes.
- Physical memory locations for data transfers use Physical Region Page (PRP) entries or Scatter Gather Lists (SGL).
- Commands can have two PRP entries or one SGL segment. If more than two PRP entries are needed, a PRP List (list of PRP entries) is used. If more than one SGL segment is needed, SGL segments point to the next.

### Completion Queue (CQ)
- A circular buffer with a fixed slot size.
- Used to post status for completed commands.
- Completed command has a unique identifier (associated SQ identifier and command identifier assigned by host software).
- In memory - based transport model, multiple Submission Queues can be associated with a single Completion Queue.
- Configuration with a single Completion Queue can be used where a single worker thread processes all command completions (even from multiple Submission Queues).
- CQ Head pointer is updated by host software after processing completion queue entries (indicating last free).

### 2.2 Message-Based Transport Model (Fabrics)
The message-based transport model used for NVMe over Fabrics has the following differences from the memory-based transport model:
- There is a one-to-one mapping between I/O Submission Queues and I/O Completion Queues. NVMe over Fabrics does not support multiple I/O Submission Queues being mapped to a single I/O Completion Queue;
- NVMe over Fabrics does not define an interrupt mechanism that allows a controller to generate a host interrupt. It is the responsibility of the host fabric interface (e.g., Host Bus Adapter) to generate host interrupts;
- NVMe over Fabrics uses different mechanisms for I/O Submission Queue and I/O Completion Queue creation and deletion (refer to section 3.5);
- NVMe over Fabrics does not support transferring metadata from a separate buffer (e.g., does not support the Metadata Pointer field, refer to Figure 92);
- NVMe over Fabrics does not support PRPs but requires use of SGLs for Admin, I/O, and Fabrics commands. This differs from the memory-based transport model where SGLs are not supported for Admin commands and are optional for I/O commands;
- NVMe over Fabrics does not support Completion Queue flow control (refer to section 3.3.1.2.1). This requires that the host ensures there are available Completion Queue slots before submitting new commands; and
- NVMe over Fabrics allows Submission Queue flow control to be disabled if the host and controller agree to disable Submission Queue flow control. If Submission Queue flow control is disabled, the host is required to ensure that there are available Submission Queue slots before submitting new commands.

### 2.2.1 Fabrics and Transports
NVMe over Fabrics utilizes the protocol layering shown in Figure 8. This specification defines core aspects of the architecture that are independent of the NVMe Transport. An NVMe Transport binding specification is used to describe any NVMe Transport specific specialization as well as how the services required by the NVMe interface are mapped onto the corresponding NVMe Transport. The native fabric communication services and other functionality used by the NVMe interface and NVMe Transports (e.g., the Fabric Protocol and Fabric Physical layers in Figure 8) are outside the scope of the NVMe family of specifications.

### 2.2.2 NVM Subsystem Ports for Fabrics

An NVM subsystem presents a collection of one to (64Ki - 16) controllers which are used to access namespaces. The controllers may be associated with hosts through one to 64Ki NVM subsystem ports.

An NVM subsystem port is a protocol interface between an NVM subsystem and a fabric. An NVM subsystem port is a collection of one or more physical fabric interfaces that together act as a single protocol interface. When link aggregation (e.g., Ethernet) is used, the physical ports for the group of aggregated links constitute a single NVM subsystem port.

An NVM subsystem contains one or more NVM subsystem ports.

Each NVM subsystem port has a 16-bit port identifier (Port ID). An NVM subsystem port is identified by the NVM Subsystem NVMe Qualified Name (NQN) and Port ID. The NVM subsystem ports of an NVM subsystem may support different NVMe Transports. An NVM subsystem port may support multiple NVMe Transports if more than one NVMe Transport binding specifications exist for the underlying fabric (e.g., an NVM subsystem port identified by a Port ID may support both iWARP and RoCE). An NVM subsystem implementation may bind specific controllers to specific NVM subsystem ports or allow the flexible allocation of controllers between NVM subsystem ports, however, once connected, each specific controller is bound to a single NVM subsystem port.

#### Figure 8: NVMe over Fabrics Layering

| Layer Name | Description |
| ---- | ---- |
| NVMe over Fabrics (Message - based Model) | NVMe Architecture, Queuing Interface, Admin Command & I/O Command Sets, Properties |
| NVMe Transport Specification | Fabric Specific Properties, Transport Specific Features/Specialization |
| NVMe Transport | NVMe Transport Binding Services, NVMe Transport |
| Fabric | Fabric Protocol (may include multiple fabric protocol layers), Fabric Physical (e.g., Ethernet, InfiniBand, Fibre Channel) |

This figure illustrates the layering of NVMe over Fabrics. The top layer (NVMe over Fabrics) deals with the core NVMe architecture and commands. The NVMe Transport Specification layer adds fabric and transport - specific properties. The NVMe Transport layer has binding services and the transport itself. The Fabric layer includes the protocol (which can have multiple layers) and the physical fabric (like Ethernet etc.).

### 2.2.3 Discovery Service
NVMe over Fabrics defines a discovery mechanism for a host to determine accessible NVM subsystems. The Discovery Service offers:
- Ability to list accessible NVM subsystems.
- Find multiple paths to a subsystem.
- Discover statically configured controllers.
- Optionally establish persistent connections.
- Optionally receive asynchronous events.

A Discovery Service is an NVM subsystem with only Discovery controllers (section 3.1.3.3) and doesn't support other controller types. Hosts use configuration files, hypervisors, or OS properties to get initial Discovery Service info.

### 2.2.4 Capsules and Data Transfer
A capsule is an NVMe info - exchange unit in NVMe over Fabrics. Classified as command (contains a command, SGLs/data optional) or response (contains a response, data optional). Data is transferred at the NVMe layer (e.g., logical block data). Capsules are independent of the transport (e.g., packet, message).

**Command Capsules**:
- Transferred from host to subsystem.
- SQE has Admin, I/O, or Fabrics commands.
- Min size: NVMe Transport binding specific (≥64B).
- Max size: NVMe Transport binding specific.
- Format: Figure 9 (Command Capsule Format: Byte 0 - 63 is Submission Queue Entry; 64 - (N - 1) is Data or SGLs (if present); total size N Bytes).

**Response Capsules**:
- Transferred from subsystem to host.
- CQE linked to a previous command.
- Size: NVMe Transport binding specific (≥16B).
- Format: Figure 10 (not shown in text but implied similar structure description).

### NVM Express® Base Specification, Revision 2.2

#### Figure 10: Response Capsule Format
- **Byte 0**: Completion Queue Entry (orange section)
- **15 - 16 to (N - 1)**: Data (if present) (blue section)
- **Response Capsule of Size N Bytes**: Describes the structure of the response capsule used in NVM Express. NVMe Transports using message - only or message/memory transport models require SGLs (Scatter - Gather Lists) to be transferred within the command. NVMe over Fabrics requires SGLs for all commands (Fabrics, Admin, and I/O), and each transport defines SGL placement restrictions.

#### 2.2.5 Authentication
- **Fabric Secure Channel and In - band Authentication**: NVMe over Fabrics supports both. A controller associated with an NVM subsystem requiring a fabric secure channel will not accept commands until a secure channel is established. After a Connect command, a controller requiring in - band authentication will only accept commands created by that Connect command until authentication is complete (refer to section 8.3.4).

#### 2.3 NVM Storage Model
#### 2.3.1 Storage Entities
- **Entities in NVM Storage Model**:
  - NVM subsystems (refer to 1.5.66)
  - Domains (refer to section 3.2.5)
  - Endurance Groups (refer to section 3.2.3)
  - Reclaim Groups and Reclaim Units (refer to section 3.2.4)
  - NVM Sets (refer to section 3.2.2)
  - Namespaces (refer to section 3.2.1)
- **Containment Hierarchy**:
  - Each domain is in a single NVM subsystem.
  - Each Endurance Group is in a single domain and can contain:
    - One or more NVM Sets
    - One or more Reclaim Groups
  - Each NVM Set is in a single Endurance Group, each namespace is in a single NVM Set, each Media Unit is in a single Endurance Group.
  - Each Reclaim Group is in a single Endurance Group, each Reclaim Unit is in a Reclaim Group, and each namespace is in an Endurance Group within one or more Reclaim Units of the Reclaim Groups in that Endurance Group.

### NVM Express® Base Specification, Revision 2.2

Each Endurance Group is composed of storage media, which are termed Media Units (refer to section 8.1.4.2) or Reclaim Units (refer to section 3.2.4). Reclaim Unit Handles reference a Reclaim Unit in each Reclaim group for writing user data. For clarity, Media Units, Reclaim Unit Handles, and Reclaim Units are not shown in the examples in this section that follow.

Figure 11 shows the hierarchical relationships of these entities within a simple NVM subsystem, which has:
- one domain;
- one Endurance Group;
- one NVM Set; and
- one namespace.

**Figure 11: Simple NVM Storage Hierarchy with NVM Sets**

The figure is a diagram (not a table or a chart like bar/line/pie). It depicts a nested structure. At the outermost is the "NVM Subsystem". Inside it is "Domain 0". Inside "Domain 0" is "Endurance Group". Inside "Endurance Group" is "NVM Set". And inside "NVM Set" is "Namespace 1". This visual representation shows the containment hierarchy among these NVM - related entities.

### NVM Express® Base Specification, Revision 2.2

Figure 12 shows the hierarchical relationships in a simple NVM subsystem, which has:
- one domain;
- one Endurance Group;
- one Reclaim Group; and
- one namespace with user data written to the single Reclaim Group.

The placement (i.e., which Reclaim Group) of user data for a namespace is directed by each host write command to that namespace (refer to section 8.1.10).

#### Figure 12: Simple NVM Storage Hierarchy with One Reclaim Group

![Figure 12](Figure_12_Image_URL) (Replace with actual URL if available)

- The outermost layer is the "NVM Subsystem".
- Inside it is "Domain 0".
- Inside "Domain 0" is "Endurance Group 1".
- Inside "Endurance Group 1" is "Reclaim Group 0".
- Inside "Reclaim Group 0" is "Namespace 1".

Figure 13 shows the hierarchical relationships in a simple NVM subsystem, which has:
- one domain;
- one Endurance Group;
- four Reclaim Groups; and
- one namespace with user data written to each Reclaim Group.

The placement (i.e., which Reclaim Group) of user data for a namespace is directed by each host write command to that namespace (refer to section 8.1.10).

### NVM Express® Base Specification, Revision 2.2

#### Figure 13: Simple NVM Storage Hierarchy with Multiple Reclaim Groups

The figure depicts a hierarchical structure of an NVM subsystem. At the outermost layer is the "NVM Subsystem". Inside it is "Domain 0". Within "Domain 0" is "Endurance Group 1". "Endurance Group 1" contains four "Reclaim Groups" (Reclaim Group 0, Reclaim Group 1, Reclaim Group 2, Reclaim Group 3). There is also a "Namespace 1" that spans across part of the "Endurance Group 1".

Figure 14 (described in text) shows a more complex NVM subsystem with:
- multiple domains;
- multiple Endurance Groups per domain;
- multiple NVM Sets per Endurance Group; and
- multiple namespaces per NVM Set.

### NVM Express® Base Specification, Revision 2.2

#### Figure 14: Complex NVM Storage Hierarchy with NVM Sets

The figure depicts a hierarchical structure of an NVM subsystem. It shows two domains (Domain A and Domain D). Each domain contains multiple Endurance Groups (e.g., Endurance Group A1, A3 in Domain A; Endurance Group D1, D5 in Domain D). Each Endurance Group has multiple NVM Sets (e.g., NVM Set A1b, A1e in Endurance Group A1; NVM Set D1k, D1m in Endurance Group D1). Each NVM Set contains multiple namespaces (NS).

- **Entity naming key (Abc)**:
  - **A**: Domain (capital letter)
  - **b**: Endurance Group (digit)
  - **c**: NVM Set (lower case letter)

Figure 15 (not shown in the image but described) shows the relationships in a complex NVM subsystem with:
- multiple domains;
- multiple Endurance Groups per domain;
- multiple Reclaim Groups per Endurance Group; and
- multiple namespaces per Endurance Group.

The placement (i.e., which Reclaim Group) of user data for a namespace is directed by each host write command to that namespace (refer to section 8.1.10).

