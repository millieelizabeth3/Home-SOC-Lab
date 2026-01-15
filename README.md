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



## Phase 1: Verify Existing VMs

### Windows IPv4: 
192.168.199.133/24

### Kali Linux IP
192.168.199.129/24

### Ubuntu IP
192.168.199.131/24

* Successful ping of Kali to Windows (add ss)
* Successful ping of Windows to Kali (add ss)

## Phase 2: Create SIEM Server

* create a new virtual machine: OS: Ubuntu Desktop, specs: 4GB Ram, 2 CPU, 60GB disk
* ping windows and kali to ubuntu server successfully


## Phase 3: Turning Windows into a Log-Generating Machine

* Install Sysmon on windows
* install splunk universal forwarder
* configure windows logs to be sent to splunk
* verify logs appear in splunk
By the end of this phase, I will have: sysmon installed on windows, splunk universal forwarder installed, windows logs being sent into splunk, and real security evening appearing in my SIEM dahsboard. --> where my lab becomes a real SOC environment.

## Phase 4: Attack + Detect + Investigate

*Note:* 
- cmd to get splunk forwarding running from Windows (sudo opt/splunk/bin/splunk start)
- or windows+r services.msc -> SplunkForwarder -> right click Running
Goals
* generate realistic malicious activity from Kali
* detect it in Splunk
* practice analyzing like a SOC analyst

4 Mini Labs -> each one = a portfolio bullet point
* Network Recon Detection
* Brute Force Detection
* Suspicious PowerShell Activity
* Persistence / Process Investigation
