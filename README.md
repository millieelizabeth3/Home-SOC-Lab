# Home-SOC-Lab

## Project Title: 
**(decide after completing)*

## Purpose: 
Build a mini SOC environment to be able to simulate actions of a Tier 1 SOC analyst

## Tools I will use:
- VMware
- Windows Event Logging
- Kali Linux VM
- Splunk VM

## What I Will Have When Finished
- built a security environment
- configure log collection
- Use Splunk
- Investigate real alerts
- write analyst report


## Phase 1: Verify Existing VMs/Foundation

### Step 1: Document Current Environment

* Host Machine Specs: 
* VMware Version: VMware Workstation Pro 25H2
* Network Type: Host-Only
* Existing VMs and IP addresses:
    - Windows IP: 192.168.199.133/24
    - Kali Linux IP: 192.168.199.129/24
    - Ubuntu IP: 192.168.199.131/24
* Successful ping of Kali to Windows (add ss)
* Successful ping of Windows to Kali (add ss)

### Step 2: Simple Network Diagram

Kali (Attacker) -> Windows 10 (Victim) -> Splunk SIEM

**INSERT IMAGE HERE**   *save as network_diagram.png*


## Phase 2: Create and Add SIEM

### Step 3: Install Splunk

* Create a new VM using Ubuntu
* Install Splunk

Tasks:
- download splunk
- install
- set admin account
- make sure I can access localhost:8000

### Step 4: Networking Check

Tasks:
- Windows VM can ping Splunk
- Kali can ping Windows
- all VMs are on same Host-Only subnet


## Phase 3: Turning Windows into a Log-Generating Machine/Logging Setup

### Step 5: Install Sysmon on Windows

Tasks:
- Download Sysmon and install with a standard configuration

*Example* sysmon -accepteula -i -sysmonconfig.xml - run as admin in PowerShell

- Verify logs appear in: /Event Viewer/Applications and Services/Microsoft/Sysmon

### Step 6: Install Splunk Universal Fowarder

On Windows:
* Install Splunk Forwarder
* Configure to send logs to Splunk server

Forward: 
* Security logs
* System logs
* Sysmon logs

### Step 7: Verify Logs in Splunk

In Splunk search index=main

*Note: confirm seeing Windows and Sysmon events*

* Install Sysmon on windows
* install splunk universal forwarder
* configure windows logs to be sent to splunk
* verify logs appear in splunk
By the end of this phase, I will have: sysmon installed on windows, splunk universal forwarder installed, windows logs being sent into splunk, and real security evening appearing in my SIEM dahsboard. --> where my lab becomes a real SOC environment.


## Phase 4: Attack Simulation

### From Kali VM:

Perform these controlled tests:
- ping sweeps
- nmap scans -> nmap -sV 192.168.199.XXX
- failed logins
- brute force attempts -> hydra -l admin -P passwords.txt smb:\\192.168.199.XXX
- create suspicious PowerShell activity

Goals
* generate realistic malicious activity from Kali
* detect it in Splunk
* practice analyzing like a SOC analyst

4 Mini Labs -> each one = a portfolio bullet point
* Network Recon Detection
* Brute Force Detection
* Suspicious PowerShell Activity
* Persistence / Process Investigation



## Phase 5: SOC Analyst Work
step 8: investigate in splunk, create searches like index=main with different event codes
step 9: build basic alerts -> create brute force alert, nmap detection alert, suspicious PowerShell alert
step 10: write an investigation report -> include: what happened, logs analyzed, timeline, evidence, conclusion

## Phase 6: Documentation
Organize repo
 ├── README.md
 ├── Network_Diagram.png
 ├── Setup_Guide.md
 ├── Splunk_Queries.md
 ├── Attack_Scenarios.md
 ├── Investigation_Report.md
 └── Screenshots/


Where to pick up: 
- 1/15/2026 completed phase 3
- start at phase 4 and reconnect to SIEM
