# Security Risk Management Project Report- Prototype

## 1. Business Description
### Company Profile: BlaBla Solutions
- **Industry**: Cloud-based HR Management Software
- **Company Size**: 150 employees
- **Annual Revenue**: SR12.5 million
- **Location**: Tabuk, Kingdom of Saudi Arabia
- **Business Model**: SaaS (Software as a Service) platform for mid-sized businesses

### Core Business Processes
1. Customer Relationship Management
2. Software Development
3. Cloud Service Delivery
4. Customer Support
5. Data Analytics and Reporting

## 2. Asset Identification and Cataloging

### Hardware Assets
| Asset ID | Asset Type | Quantity | Estimated Value | Location |
|----------|------------|----------|-----------------|----------|
| HW-01 | Servers (Primary Data Center) | 12 | SR180,000 | Main Office |
| HW-02 | Employee Workstations | 140 | SR280,000 | Various Locations |
| HW-03 | Network Infrastructure | 25 | SR95,000 | Main Office & Branch |

### Software Assets
| Asset ID | Software Name           | Type       | License Cost | Business Value | Critical Level |
|----------|-------------------------|------------|--------------|----------------|----------------|
| SW-01    | Customer Database       | Core App   | SR45,000     | SR250,000      | High           |
| SW-02    | Development Environment | Internal   | SR25,000     | SR150,000      | High           |
| SW-03    | Cloud Management        | Infrastructure | SR60,000 | SR500,000      | Critical       |

### Data Assets
| Asset ID | Data Type | Sensitivity | Estimated Value | Protection Required |
|----------|-----------|-------------|-----------------|---------------------|
| DA-01 | Customer Personal Information | High | SR500,000 | Encrypted, Access Controlled |
| DA-02 | Source Code Repositories | Critical | SR1,200,000 | Highly Restricted Access |
| DA-03 | Financial Records | High | SR350,000 | Encrypted, Audit Trail |

## 3. Risk Assessment Matrix

### Threat Identification
| Threat ID | Threat Description | Potential Impact | Likelihood | Severity |
|-----------|---------------------|------------------|------------|----------|
| T-01 | Data Breach | High Financial/Reputational Damage | Medium | High |
| T-02 | Ransomware Attack | System Disruption | Low | Critical |
| T-03 | Insider Threat | Unauthorized Data Access | Medium | High |
| T-04 | DDoS Attack | Service Interruption | Low | Medium |

### Risk Calculation Example
**Asset**: Customer Database System (SW-01)
- Asset Value: SR250,000
- Threat: Data Breach
- Vulnerability: Weak Access Controls
- SLE: SR250,000 × 0.15 = SR37,500 (detaild down)
- ALE: SR37,500 × 0.5 = SR18,750 (detaild down)

**Single Loss Expectancy (SLE) Calculation**:
- Probability of Breach: 15%
- Estimated Loss: SR250,000 * 0.15 = SR37,500
- **SLE**: SR37,500

**Annual Loss Expectancy (ALE) Calculation**:
- Estimated Occurrences per Year: 0.5
- **ALE**: SR37,500 * 0.5 = SR18,750

### Additional SLE/ALE Calculations
**Asset**: Source Code Repositories (DA-02)
- Asset Value: SR1,200,000
- Threat: Insider Threat
- Vulnerability: Lack of Code Access Monitoring
- **SLE**: SR1,200,000 × 0.10 (Probability) = SR120,000
- **ALE**: SR120,000 × 0.3 (Annual Rate) = SR36,000

**Asset**: Financial Records (DA-03)
- Asset Value: SR350,000
- Threat: Ransomware Attack
- Vulnerability: Unpatched Software
- **SLE**: SR350,000 × 0.25 = SR87,500
- **ALE**: SR87,500 × 0.2 = SR17,500

## 4. Incident Response Plan

### Incident Classification Levels
1. **Level 1 (Low)**: Minor security events, no immediate threat
2. **Level 2 (Medium)**: Potential security compromise
3. **Level 3 (High)**: Active security breach

### Response Workflow
1. **Detect**
   - SIEM alerts (Wazuh)
   - AWS GuardDuty monitoring
   - Employee reporting mechanisms

2. **Respond**
   - Contain: Isolate systems, revoke access
   - Eradicate: Remove malware, patch vulnerabilities

4. **Recovery**
   - System validation
   - Gradual service restoration
   - Comprehensive system checks

### Communication Protocol
- **Internal Notification**: Within 1 hour of confirmation
- **Customer Notification**: Within 24 hours of assessment
- **Regulatory Reporting**: As per GDPR/CCPA guidelines

### Incident Response Tools
- **Detection**: Wazuh SIEM, AWS GuardDuty
- **Containment**: Network isolation scripts (`/scripts/isolate_network.sh`)
- **Eradication**: Malware analysis toolkit (Volatility, YARA)
- **Recovery**: Automated backup validation (`/scripts/validate_backup.py`)

### Example Scenario: Ransomware Attack
1. **Detection**: SIEM alerts on encrypted files.
2. **Containment**: Disable affected user accounts; isolate VLAN.
3. **Eradication**: Identify ransomware variant; restore from clean backup.
4. **Recovery**: Deploy decryption tools if available; monitor for reinfection.

## 5. Disaster Recovery Plan

### Recovery Objectives
- **Recovery Time Objective (RTO)**: 4 hours for critical systems
- **Recovery Point Objective (RPO)**: Maximum 1-hour data loss

### Backup Strategy
1. **Primary Data Center Backup**
   - Location: Medina, Kingdom of Saudi Arabia
   - Frequency: Real-time incremental
   - Storage: Encrypted cloud storage

2. **Secondary Backup Site**
   - Location: Riyadh, Kingdom of Saudi Arabia
   - Synchronization: Daily full backup
   - Isolated network environment

### Recovery Procedures
1. **Immediate Switchover**
2. **Data Restoration**
3. **System Validation**
4. **Gradual Service Resumption**

### DRP Testing Schedule
| **Test Type**       | **Frequency** | **Responsible Team** |
|----------------------|---------------|-----------------------|
| Full System Failover | Quarterly     | Infrastructure Team   |
| Backup Restoration   | Monthly       | DevOps Team           |
| RTO Validation       | Bi-annually   | Security Team         |



## 6. Business Continuity Plan
### Critical Functions
1. **Customer portal**
2. **Billing systems**
3. **Development environments**

### Remote Work Setup
- VPN: OpenVPN with MFA
- Collaboration: Mattermost backup server
- MDM-enforced device encryption


## 7. NIST CSF Alignment

| Function  | Control          | Implementation               |
|-----------|------------------|------------------------------|
| Identify  | Asset Inventory  | Hardware/software catalog    |
| Protect   | MFA              | All admin accounts           |
| Detect    | SIEM             | Wazuh alerts                |
| Respond   | IR Plan          | Section 4 procedures        |
| Recover   | Backups          | Daily validation            |


## 8. Conclusion
1. Implement MFA everywhere
2. Quarterly penetration tests
3. Continuous staff training

### Appendices
**Task Allocation**

| Member       | Responsibility          | Deliverables                          |
|--------------|-------------------------|---------------------------------------|
| Sultan       | Asset Management        | Hardware/software catalog             |
| Mohammed     | Risk Assessment         | SLE/ALE calculations, Threat matrix   |
| Abdulaziz    | Incident Response       | IRP workflows, Tool configurations    |
| Abdulrahman  | Disaster Recovery       | DRP procedures, Cloud recovery scripts|
| Saud         | Business Continuity     | Remote work policies, Supplier agreements |

- Sultan
- Mohammed
- Abdulaziz
- Abdulrahman
- Saud
