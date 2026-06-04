# Windows Firewall Configuration Lab

## Project Overview

This project demonstrates basic firewall administration using Windows Defender Firewall with Advanced Security.

The objective was to configure, verify, test, and remove a firewall rule to understand how network traffic filtering works on a Windows system.

---

## Objectives

- Review existing firewall rules.
- Create a custom inbound firewall rule.
- Block traffic on a specific port.
- Verify the rule configuration.
- Test the rule using Nmap.
- Remove the rule after testing.
- Understand firewall traffic filtering.

---

## Tools Used

- Windows Defender Firewall with Advanced Security
- Windows PowerShell
- Nmap

---

## Environment

- Operating System: Windows 11

---

## Procedure

### Step 1: Review Existing Firewall Rules

Opened Windows Defender Firewall with Advanced Security and reviewed existing inbound and outbound rules.

### Step 2: Create a New Firewall Rule

Created a new inbound firewall rule with the following settings:

- Rule Type: Port
- Protocol: TCP
- Local Port: 23
- Action: Block the connection
- Profiles: Domain, Private, Public
- Rule Name: Block Telnet Port 23

### Step 3: Verify Rule Creation

Verified that the firewall rule was successfully added to the Inbound Rules list.

### Step 4: Verify Rule Using PowerShell

Used the following command:

```powershell
Get-NetFirewallRule -DisplayName "Block Telnet Port 23"
```

The command confirmed that the rule was present and enabled.

### Step 5: Test the Rule Using Nmap

Executed the following command:

```bash
nmap -p 23 localhost
```

The scan showed that TCP port 23 was not accessible, confirming that the firewall rule was functioning as intended.

### Step 6: Remove the Rule

Deleted the firewall rule to restore the system to its original configuration.

---

## Firewall Traffic Filtering

A firewall monitors and controls network traffic entering and leaving a system.

Firewall rules can:

- Allow traffic
- Block traffic
- Restrict access based on ports
- Restrict access based on protocols
- Control application communication

In this lab, TCP port 23 (Telnet) was blocked to demonstrate how inbound traffic can be filtered.

---

## Skills Demonstrated

- Windows Firewall Administration
- Network Security
- Access Control
- PowerShell Usage
- Network Scanning with Nmap
- Security Documentation

---

## Screenshots

Screenshots documenting the configuration and testing process are included in the screenshots folder.

---

## Conclusion

This lab demonstrated how Windows Defender Firewall can be used to control network traffic through custom rules. The exercise provided hands-on experience with firewall management, rule verification, and network security testing.