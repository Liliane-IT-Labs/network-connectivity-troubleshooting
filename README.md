# **Network Connectivity Restoration | TCP/IP Troubleshooting & Root Cause Analysis**

`Windows 11` `TCP/IP` `IT Support` `Network Administration` `Root Cause Analysis`

> **One incorrect IP address. One disconnected workstation. One targeted solution.**
>
> This project demonstrates how structured network diagnostics can isolate and resolve connectivity issues without unnecessary changes to network infrastructure.

## **1. Business scenario**

An employee connected a corporate laptop to a small office/home office (SOHO) network but was unable to access the internet. Other workstations on the same network remained fully operational.

As the IT Support Technician, my responsibility was to investigate the connectivity failure, identify the root cause, restore network access, and validate the effectiveness of the solution.

### **Project objectives**

- Diagnose the connectivity failure using Windows network tools.
- Determine whether the issue is endpoint-specific or network-wide.
- Identify and remediate the underlying IP misconfiguration.
- Verify connectivity and document the resolution.

## **2. Technical environment**

| Component              | Configuration                            |
| ---------------------- | ---------------------------------------- |
| Operating system       | Windows 11                               |
| Network                | Small Office/Home Office (SOHO)          |
| Affected endpoint      | Home-Laptop                              |
| Reference workstation  | Home-PC1                                 |
| Additional workstation | Home-PC2                                 |
| Default gateway        | `192.168.1.1`                            |
| IP assignment          | Static IPv4                              |
| Tools                  | Windows Network Settings, Terminal, ICMP |

## **3. Troubleshooting workflow**
Connectivity Failure → Inspect IP Configuration → Perform Connectivity Tests → Compare with Healthy Endpoint → Identify Root Cause → Implement Targeted Remediation → Validate Connectivity → Document Resolution

## **4. Phase I — Diagnosis & Root Cause Analysis**

### **Step 1 — Investigate the affected endpoint**

**Goal:** Establish the initial network configuration and identify potential abnormalities.

On **Home-Laptop**, launch Windows and navigate to:

**Settings → Network & Internet → Ethernet → IP assignment → Edit**

Inspect the IPv4 address, subnet mask, default gateway, and DNS servers without modifying the existing configuration.

**CLI:**

```
hostname
ipconfig /all
```

**Screenshot:** `01-initial-ip-configuration.png`
<img width="848" height="593" alt="image" src="https://github.com/user-attachments/assets/3eb74dab-1594-43d9-98df-91a3a5b16e04" />


**Why it matters:** Establishing a baseline before making changes preserves diagnostic evidence and prevents unnecessary configuration modifications.

### **Step 2 — Perform connectivity diagnostics**

**Goal:** Determine the scope of the network failure.

Open **Terminal (Admin)** on Home-Laptop and execute:

```
ping Home-Laptop
ping Home-PC1
ping Home-PC2
ping 192.168.1.1
```

| Diagnostic test | Purpose                              |
| --------------- | ------------------------------------ |
| Home-Laptop     | Test local host communication        |
| Home-PC1        | Test workstation connectivity        |
| Home-PC2        | Test additional network connectivity |
| Default gateway | Test router accessibility            |

**Screenshot:** `02-initial-connectivity-tests.png`
<img width="738" height="808" alt="image" src="https://github.com/user-attachments/assets/ae68479b-2ed9-4596-9555-9cf16edba211" />

**Why it matters:** Connectivity testing helps narrow the investigation and identify where communication is failing.

### **Step 3 — Establish a known-good configuration**

**Goal:** Compare the affected endpoint with a fully operational workstation.

Return to **Network Modeler** and launch Windows on **Home-PC1**.

Navigate to:

**Settings → Network & Internet → Ethernet → IP assignment → Edit**

**CLI:**

```
hostname
ipconfig /all
```

Compare the IPv4 configuration of both devices, focusing on the IP address, subnet mask, default gateway, and DNS servers.

**Screenshot:** `03-known-good-configuration.png`
<img width="710" height="417" alt="image" src="https://github.com/user-attachments/assets/64fa0dde-ca5e-4880-8b37-6e84d88af430" />

**Why it matters:** A working endpoint provides a reliable reference for identifying configuration discrepancies.

### **Step 4 — Isolate the network failure**

**Goal:** Determine whether the issue affects the entire network or only the laptop.

Execute the following commands on Home-PC1:

```
ping Home-Laptop
ping Home-PC1
ping Home-PC2
ping 192.168.1.1
```

Compare the results with the initial tests performed on Home-Laptop.

**Screenshot:** `04-network-fault-isolation.png`
<img width="646" height="815" alt="image" src="https://github.com/user-attachments/assets/e541b59e-42e3-4c70-a662-ab879883acab" />


**Why it matters:** Testing from a healthy workstation helps isolate the affected endpoint and avoid unnecessary infrastructure changes.

### **Step 5 — Identify the root cause**

**Goal:** Establish an evidence-based explanation for the connectivity failure.

The configuration comparison revealed a typographical error in Home-Laptop's static IPv4 address, placing the device on the wrong network.

| Root cause assessment           | Finding                       |
| ------------------------------- | ----------------------------- |
| Failure category                | Network configuration         |
| Affected component              | Endpoint TCP/IP settings      |
| Root cause                      | Incorrect static IPv4 address |
| Scope                           | Single endpoint               |
| Infrastructure changes required | None                          |
| Recommended solution            | Correct the IPv4 address      |

**Root cause confirmed:** Static IPv4 misconfiguration.

The issue originated from the endpoint configuration, not a network-wide infrastructure failure.
<img width="747" height="467" alt="image" src="https://github.com/user-attachments/assets/63cbe8cb-b351-482d-8153-5447b2cbbf62" />


## **5. Phase II — Remediation & Validation**

### **Step 6 — Implement targeted remediation**

**Goal:** Restore network communication while preserving valid configuration settings.

On Home-Laptop, navigate to:

**Settings → Network & Internet → Ethernet → IP assignment → Edit**

Correct the IPv4 address:

```
192.168.1.20
```

Preserve the remaining valid network settings and select **Save**.

Verify the updated configuration:

```
ipconfig /all
```

**Screenshot:** `05-corrected-ip-configuration.png`
<img width="857" height="526" alt="image" src="https://github.com/user-attachments/assets/f1beba7c-ad16-46f6-b1da-885718905b6f" />

**Why it matters:** Targeted remediation resolves the underlying issue while minimizing operational risk.


### **Step 7 — Validate network functionality**

**Goal:** Confirm that the solution resolved the original connectivity failure.

Repeat the initial diagnostic tests on Home-Laptop:

```
ping Home-Laptop
ping Home-PC1
ping Home-PC2
ping 192.168.1.1
```

Confirm that Windows displays connectivity to HomeNet and the internet.

For additional real-world verification, where supported:

```
ping 8.8.8.8
nslookup google.com
```

Verify external website accessibility using a web browser.

**Screenshot:** `06-post-remediation-validation.png`
<img width="592" height="776" alt="image" src="https://github.com/user-attachments/assets/f8ddef55-f7cc-4093-bfae-2b0e0545f5fc" />

**Why it matters:** Applying a fix does not complete the troubleshooting process. Successful verification provides evidence that the original problem has been resolved.

## **6. Project outcome**

Expected connectivity tests

# **4/4**

Successful

Infrastructure changes

# **0**

Required

Root causes identified

# **1**

IPv4 misconfiguration

Expected service outcome

# **Restored**

Network connectivity

| Validation criteria        | Before      | Expected after |
| -------------------------- | ----------- | -------------- |
| IPv4 configuration         | Incorrect   | Correct        |
| Local network connectivity | Unavailable | Restored       |
| Gateway communication      | Failed      | Successful     |
| Internet accessibility     | Unavailable | Restored       |
| Endpoint functionality     | Disrupted   | Operational    |

## **7. Business value**

This project demonstrates the operational value of structured IT troubleshooting:

- **Reduced downtime:** Isolate and resolve the affected endpoint.
- **Risk mitigation:** Avoid unnecessary network infrastructure changes.
- **Operational efficiency:** Apply an evidence-based solution rather than trial and error.
- **Service reliability:** Verify functionality before concluding remediation.
- **Knowledge management:** Document a repeatable troubleshooting procedure.

## **8. Technical competencies demonstrated**

| Competency              | Practical application                        |
| ----------------------- | -------------------------------------------- |
| Network troubleshooting | Diagnosing connectivity failures             |
| TCP/IP administration   | Inspecting and correcting IPv4 settings      |
| CLI diagnostics         | Executing and interpreting network commands  |
| Fault isolation         | Comparing healthy and affected endpoints     |
| Root cause analysis     | Identifying configuration discrepancies      |
| Incident resolution     | Implementing targeted remediation            |
| Quality assurance       | Performing post-remediation validation       |
| Technical documentation | Recording diagnostic evidence and resolution |

## **9. Repository structure**

```
network-connectivity-restoration/
│
├── README.md
│
└── screenshots/
    ├── 01-initial-ip-configuration.png
    ├── 02-initial-connectivity-tests.png
    ├── 03-known-good-configuration.png
    ├── 04-network-fault-isolation.png
    ├── 05-corrected-ip-configuration.png
    └── 06-post-remediation-validation.png
```

## **10. Key takeaway**

A connectivity failure does not necessarily indicate defective hardware, a failed router, or a major network outage.

In this lab scenario, a single incorrect IPv4 address was responsible for the entire connectivity issue.

The solution required systematic investigation, logical reasoning, targeted remediation, and technical verification.

> **The difference between fixing a problem and resolving an incident is the ability to identify the root cause, restore functionality, and prove that the solution works.**


