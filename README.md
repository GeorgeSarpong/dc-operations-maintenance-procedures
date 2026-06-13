# Data Center Operations & Maintenance Procedures

![DC Operations](https://img.shields.io/badge/Domain-Data%20Center%20Operations-blue)
![Maintenance](https://img.shields.io/badge/Focus-Preventive%20Maintenance-green)
![ITIL](https://img.shields.io/badge/Framework-ITIL%20v4-green)
![Schneider DCCA](https://img.shields.io/badge/Cert-Schneider%20DCCA-orange)
![OSHA](https://img.shields.io/badge/Safety-OSHA%2030-green)
![NFPA](https://img.shields.io/badge/Safety-NFPA%2070E-red)

---

##  Project Overview

This project documents comprehensive enterprise data center preventive maintenance procedures — covering server hardware, UPS systems, cooling infrastructure, network equipment, environmental monitoring, and change management documentation aligned with industry best practices and safety standards.

Built to demonstrate operational readiness for:
- Data Center Operations Engineer roles
- Critical Infrastructure Engineer roles
- Facilities Engineer roles
- Data Center Technician roles

---

## Real World Foundation

This documentation is informed by direct hands-on experience managing:
- Dell PowerEdge R430 and R740 rack-mounted production servers
- UPS systems protecting mission-critical infrastructure
- Network switching infrastructure supporting nationwide operations
- Environmental monitoring across production server environments
- Preventive maintenance reducing equipment downtime by 20–30%

---

## Repository Structure
dc-operations-maintenance-procedures/

│

├── docs/

│   └── maintenance-overview.md            # Maintenance framework

│

├── server-maintenance/

│   ├── hardware-inspection.md             # Physical inspection SOP

│   ├── firmware-updates.md               # Firmware update procedure

│   ├── hard-drive-replacement.md         # HDD/SSD replacement

│   └── ram-replacement.md                # RAM replacement procedure

│

├── ups-maintenance/

│   ├── monthly-inspection.md             # Monthly UPS checks

│   ├── quarterly-testing.md              # Quarterly battery test

│   ├── battery-replacement.md            # Battery replacement SOP

│   └── annual-maintenance.md            # Annual full inspection

│

├── cooling-maintenance/

│   ├── crac-monthly.md                   # Monthly CRAC checks

│   ├── filter-replacement.md            # Filter replacement SOP

│   ├── refrigerant-check.md             # Refrigerant inspection

│   └── annual-inspection.md            # Annual cooling inspection

│

├── network-maintenance/

│   ├── switch-maintenance.md            # Switch maintenance SOP

│   ├── cable-management.md             # Cabling standards

│   └── port-documentation.md           # Port documentation

│

├── environmental-monitoring/

│   ├── sensor-calibration.md            # Sensor calibration

│   └── threshold-verification.md       # Alert threshold checks

│

├── change-management/

│   ├── change-request-template.md       # Change request form

│   ├── maintenance-window-procedure.md  # Maintenance windows

│   └── emergency-change-procedure.md   # Emergency changes

│

├── asset-management/

│   ├── asset-register-template.md       # Asset register

│   └── lifecycle-management.md         # Asset lifecycle

│

└── images/

└── README.md                         # Rack photos and diagrams

---

## 🔧 Preventive Maintenance Schedule

| Equipment | Daily | Weekly | Monthly | Quarterly | Annual |
|---|---|---|---|---|---|
| Server hardware | Visual check | Log review | Physical inspection | Firmware update | Full audit |
| UPS systems | Status check | Battery health | Load test | Full test | Vendor inspection |
| CRAC units | Temp check | Alert review | Filter check | Refrigerant | Full service |
| Network switches | Port status | Error counts | Config backup | Firmware | Full audit |
| Environmental sensors | Reading verify | Trend review | Calibration check | Full calibration | Replacement |
| Cable management | Visual | NA | Labeling check | Full audit | Documentation update |

---

## Server Hardware Maintenance Procedure

### Monthly Physical Inspection

```markdown
## Server Hardware Monthly Inspection Checklist

**Date:** _______________
**Engineer:** _______________
**Rack ID:** _______________

### Visual Inspection
- [ ] All server front panels showing green status LEDs
- [ ] No amber fault indicators on any server
- [ ] LCD panels showing normal status
- [ ] No physical damage to server chassis
- [ ] All drive bays properly seated
- [ ] All blank panels in place — no empty spaces
- [ ] Cable management tidy and not obstructing airflow

### Environmental Checks
- [ ] Inlet temperature within ASHRAE A2 range (10–35°C)
- [ ] Outlet temperature within acceptable range
- [ ] No unusual sounds from fans or drives
- [ ] No unusual smells (burning, chemical)

### iDRAC/iLO Remote Management
- [ ] iDRAC accessible for all servers
- [ ] No active alerts in iDRAC console
- [ ] System event log reviewed and cleared
- [ ] Fan speeds within normal range
- [ ] Power consumption within expected range

### Documentation
- [ ] Inspection logged in asset management system
- [ ] Any findings raised as work orders
- [ ] Next inspection scheduled

**Inspector Signature:** _______________
```

### Firmware Update Procedure

```markdown
## Server Firmware Update Procedure

**Risk Level:** Medium
**Change Type:** Standard
**Required Approval:** Change Advisory Board

### Pre-Update Requirements
- Change request approved minimum 5 days in advance
- Maintenance window communicated to stakeholders
- Backup of current firmware version confirmed
- Rollback procedure documented and tested
- Second engineer available for validation

### Safety Checks
- OSHA 30 compliance for working around live equipment
- NFPA 70E PPE requirements verified
- Lockout/Tagout procedure available if needed

### Update Steps
1. Download firmware from vendor site — verify checksum
2. Review release notes for known issues
3. Test on non-production server first
4. Schedule production update in approved window
5. Notify stakeholders 30 minutes before update
6. Apply firmware update via iDRAC/iLO
7. Monitor server during reboot
8. Verify all services restored post-update
9. Update asset management system with new firmware version
10. Document completion in change ticket
```

---

## UPS Maintenance Procedures

### Monthly UPS Inspection Checklist

```markdown
## UPS Monthly Inspection

**Date:** _______________
**UPS ID:** _______________
**Engineer:** _______________

### Safety — NFPA 70E Compliance
- [ ] Arc flash PPE worn — minimum Category 2
- [ ] Insulated tools in use
- [ ] Second person present for safety
- [ ] Emergency contacts confirmed accessible

### UPS Status Checks
- [ ] Input voltage within specification (208–240V)
- [ ] Output voltage within specification (208–240V)
- [ ] UPS load percentage below 80%
- [ ] Battery charge above 95%
- [ ] No active alarms on UPS display
- [ ] Bypass mode NOT active
- [ ] UPS cooling fans operating normally

### Battery Health
- [ ] Battery temperature within range (20–25°C)
- [ ] No battery swelling or leakage visible
- [ ] Battery age recorded — replacement due check
- [ ] Battery test scheduled if due

### Environmental
- [ ] UPS room temperature within specification
- [ ] Ventilation clear and unobstructed
- [ ] No unusual smells or sounds

### Documentation
- [ ] Inspection logged in maintenance system
- [ ] Battery health recorded
- [ ] Next inspection scheduled

**Inspector Signature:** _______________
```

### Quarterly Battery Load Test

```markdown
## UPS Battery Load Test Procedure

**Frequency:** Quarterly
**Duration:** 30 minutes
**Risk Level:** Medium — requires bypass path active

### Pre-Test Requirements
- Transfer load to bypass path verified
- All protected loads can run on bypass
- Generator available and fuelled
- Stakeholders notified of test window

### Test Steps
1. Verify bypass path available and healthy
2. Transfer load to bypass
3. Confirm all loads stable on bypass
4. Disconnect UPS from utility power
5. Monitor battery discharge rate
6. Record battery voltage every 5 minutes
7. Monitor runtime vs rated capacity
8. Restore utility power before battery reaches 20%
9. Transfer load back from bypass to UPS
10. Record all readings and compare with previous test

### Pass/Fail Criteria
- Pass: Battery delivers 90%+ of rated runtime
- Warning: Battery delivers 75–90% of rated runtime
- Fail: Battery delivers below 75% — replacement required

### Documentation
- Record all voltage readings
- Calculate capacity percentage
- Update battery health log
- Raise work order if replacement needed
```

---

## CRAC Monthly Maintenance Checklist

```markdown
## CRAC Unit Monthly Inspection

**Date:** _______________
**Unit ID:** _______________
**Engineer:** _______________

### Temperature Checks
- [ ] Supply air temperature within target (16–18°C)
- [ ] Return air temperature within range (24–30°C)
- [ ] No hot spots identified in aisle temperature scan

### CRAC Unit Status
- [ ] No active alarms on CRAC display
- [ ] Fan operation normal — no unusual sounds
- [ ] Filter condition — clean/needs replacement
- [ ] Condensate drain clear — no blockage
- [ ] Compressor operating normally
- [ ] Refrigerant pressure within specification

### Airflow Management
- [ ] Hot aisle/cold aisle containment intact
- [ ] No blanking panels missing from racks
- [ ] Cable management not blocking airflow
- [ ] Raised floor tiles properly positioned

### Documentation
- [ ] Inspection logged in maintenance system
- [ ] Filter replacement scheduled if needed
- [ ] Any findings raised as work orders

**Inspector Signature:** _______________
```

---

##  Asset Register Template

```markdown
## Data Center Asset Register

| Asset ID | Type | Make | Model | Serial | Location | Rack | Unit | Install Date | Warranty | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| SRV-001 | Server | Dell | PowerEdge R740 | 9Z8MMD4 | DC-01 | R01 | U20 | 2023-01 | 2026-01 | Active |
| SRV-002 | Server | Dell | PowerEdge R430 | 5B6ZMF2 | DC-01 | R01 | U15 | 2021-06 | 2024-06 | Active |
| SW-001 | Switch | D-Link | DGS-1210 | DLNK001 | DC-01 | R01 | U01 | 2022-03 | 2025-03 | Active |
| UPS-001 | UPS | APC | Smart-UPS | APC001 | DC-01 | Floor | NA | 2020-01 | 2023-01 | Active |

### Asset Lifecycle Status Definitions
- **Active** — In production use, fully operational
- **Maintenance** — Currently undergoing maintenance
- **End of Life** — Approaching or past warranty/support
- **Decommissioned** — Removed from service
- **Spare** — Available for hot-swap replacement
```

---

## Standards & Frameworks Referenced

- **Uptime Institute** — Tier standards and operational sustainability
- **ASHRAE TC 9.9** — Thermal guidelines
- **NFPA 70E** — Electrical safety in the workplace
- **OSHA 30** — General industry safety
- **IEC 62040** — UPS systems standards
- **ITIL v4** — Change and service management
- **Schneider Electric DCCA** — Data center operations best practices

---

## Tools & Technologies

![Dell PowerEdge](https://img.shields.io/badge/Dell-PowerEdge%20Servers-blue)
![iDRAC](https://img.shields.io/badge/Dell-iDRAC-blue)
![Schneider](https://img.shields.io/badge/Schneider-UPS%20Systems-green)
![DCIM](https://img.shields.io/badge/DCIM-Asset%20Management-blue)
![ITIL](https://img.shields.io/badge/ITIL%20v4-Change%20Management-green)
![OSHA](https://img.shields.io/badge/OSHA%2030-Safety%20Compliance-green)
![NFPA](https://img.shields.io/badge/NFPA%2070E-Electrical%20Safety-red)

---

## Author

**George Amankwaa Sarpong**
Data Center Operations Engineer | Critical Infrastructure
📍 Accra, Ghana 
🔗 [LinkedIn](https://linkedin.com/in/georgesarpong)
🌐 [GitHub Portfolio](https://github.com/GeorgeSarpong)

---

*This project is part of a broader portfolio demonstrating readiness for Data Center Operations Engineer and Critical Infrastructure Engineer roles in the US and global market.*
