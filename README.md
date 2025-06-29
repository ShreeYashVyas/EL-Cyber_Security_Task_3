# EL-Cyber_Security_Task_3
# Task 3: Perform a Basic Vulnerability Scan on Your PC

## 📋 Objective
Use free vulnerability scanning tools to identify common security vulnerabilities on your computer and gain introductory experience in vulnerability assessment and risk evaluation.

## 🛠️ Tools Used
- **Primary**: OpenVAS Community Edition (Free vulnerability scanner)
- **Alternative**: Nessus Essentials (Free for personal use)
- **Additional**: Nmap for network discovery

## 📚 Key Concepts Covered
- Vulnerability scanning
- Risk assessment
- CVSS (Common Vulnerability Scoring System)
- Security remediation
- Vulnerability management
- False positive identification

## 🎯 Task Requirements

### Core Tasks:
1. Install vulnerability scanner (OpenVAS/Nessus)
2. Configure scan target (localhost/local IP)
3. Execute comprehensive vulnerability scan
4. Analyze scan results and severity ratings
5. Research remediation strategies
6. Document critical vulnerabilities
7. Take screenshots of findings

## 🚀 Implementation Guide

### Option A: OpenVAS Setup

#### Step 1: Installation (Linux - Ubuntu/Debian)
```bash
# Update system packages
sudo apt update && sudo apt upgrade -y

# Install OpenVAS
sudo apt install openvas -y

# Setup OpenVAS
sudo gvm-setup

# Start OpenVAS services
sudo gvm-start

# Create admin user
sudo runuser -u _gvm -- gvmd --create-user=admin --password=admin123
```

#### Step 2: Access Web Interface
```bash
# Check services status
sudo gvm-check-setup

# Access via browser
https://localhost:9392
```

#### Step 3: Configure Scan Target
1. Navigate to Configuration → Targets
2. Create new target with your local IP
3. Set scan methods and credentials if needed

### Option B: Nessus Essentials Setup

#### Step 1: Download and Install
```bash
# Download Nessus Essentials (register for free)
wget https://www.tenable.com/downloads/nessus

# Install (Ubuntu/Debian)
sudo dpkg -i Nessus-x.x.x-ubuntu1110_amd64.deb

# Start Nessus service
sudo systemctl start nessusd
sudo systemctl enable nessusd
```

#### Step 2: Initial Configuration
1. Navigate to https://localhost:8834
2. Register for Nessus Essentials (free)
3. Create admin account
4. Wait for plugin updates

### Step 3: Scan Configuration

#### Target Setup:
```
Target Name: Local PC Vulnerability Scan
IP Address: 127.0.0.1 or your local IP
Scan Type: Full System Scan
Credentials: Local account (optional but recommended)
```

#### Scan Policies:
- **Basic Network Scan**: Quick discovery
- **Full and Fast**: Comprehensive vulnerability detection
- **Discovery Scan**: Network mapping and service detection

### Step 4: Execute Vulnerability Scan

#### Pre-scan Checklist:
```bash
# Identify your local IP
ip addr show
# or
ifconfig

# Test connectivity
ping 127.0.0.1

# Check open ports
nmap -sS localhost
```

#### Starting the Scan:
1. Select configured target
2. Choose scan policy (Full and Fast recommended)
3. Start scan and monitor progress
4. Expected duration: 30-60 minutes

## 📊 Scan Results Analysis

### Vulnerability Severity Levels:
- **Critical (10.0-9.0)**: Immediate action required
- **High (8.9-7.0)**: High priority remediation
- **Medium (6.9-4.0)**: Moderate risk, plan remediation
- **Low (3.9-0.1)**: Informational, monitor
- **Info (0.0)**: No security impact

### Common PC Vulnerabilities Expected:

#### 1. Operating System Vulnerabilities
```
- Missing security patches
- Outdated system components
- Weak password policies
- Unnecessary services running
```

#### 2. Network Service Issues
```
- Open ports with vulnerable services
- Default credentials
- Unencrypted protocols
- Misconfigured services
```

#### 3. Application Vulnerabilities
```
- Outdated software versions
- Known CVE exposures
- Insecure configurations
- Missing security updates
```

## 🔍 Vulnerability Research and Remediation

### Research Process:
1. **CVE Lookup**: Search CVE database for vulnerability details
2. **CVSS Analysis**: Understand impact and exploitability scores
3. **Vendor Advisories**: Check official security bulletins
4. **Remediation Steps**: Identify patches and workarounds

### Example Critical Vulnerability Analysis:
```
Vulnerability: CVE-2024-XXXX
CVSS Score: 9.8 (Critical)
Description: Remote code execution in [Service]
Impact: Complete system compromise
Remediation: Apply security patch KB1234567
Priority: Immediate
```

## 📊 Results Documentation Template

### Executive Summary:
```
Scan Date: [Date]
Target: [IP/Hostname]
Scanner: [Tool Used]
Duration: [Time Taken]
Total Issues: [Count]
Critical: [Count] | High: [Count] | Medium: [Count] | Low: [Count]
```

### Top 5 Critical Vulnerabilities:
```
1. [CVE ID] - [Description] - CVSS: [Score]
   Impact: [Description]
   Remediation: [Steps]

2. [CVE ID] - [Description] - CVSS: [Score]
   Impact: [Description]
   Remediation: [Steps]
...
```

## 🔧 Troubleshooting Common Issues

### Installation Problems:
```bash
# OpenVAS service issues
sudo gvm-check-setup
sudo gvm-start

# Nessus service problems
sudo systemctl status nessusd
sudo systemctl restart nessusd
```

### Scan Issues:
- **Slow scans**: Reduce scan intensity
- **No vulnerabilities found**: Enable credentialed scanning
- **Scanner crashes**: Check system resources
- **Access denied**: Verify firewall settings


## 🛡️ Security Considerations

### Ethical Scanning Guidelines:
- **Only scan systems you own**
- **Inform stakeholders** about scanning activity
- **Use appropriate scan intensity**
- **Secure scan results** (contain sensitive information)
- **Follow responsible disclosure** if scanning external systems

### Data Protection:
- Encrypt vulnerability reports
- Limit access to scan results
- Secure scanner credentials
- Regular backup of scan data

## 🏆 Learning Outcomes

After completing this task, you will have:
- **Hands-on experience** with vulnerability scanners
- **Understanding** of common PC security weaknesses
- **Knowledge** of CVSS scoring system
- **Skills** in vulnerability prioritization
- **Experience** in security research and remediation
- **Documentation** abilities for security assessments

## 📝 Post-Scan Actions

### Immediate Steps:
1. **Address critical vulnerabilities** immediately
2. **Plan remediation** for high-severity issues
3. **Update software** and apply patches
4. **Review security configurations**
5. **Schedule regular scans**

### Long-term Security Improvements:
- Implement patch management process
- Enable automatic security updates
- Regular security awareness training
- Establish vulnerability management program
- Consider endpoint detection and response (EDR) tools

---

**Task Completed By**: [Shree Yash Vyas]    
**Scanner Used**: [OpenVAS]  
**System Scanned**: [Kali Linux]  
**Total Vulnerabilities Found**: [0]
