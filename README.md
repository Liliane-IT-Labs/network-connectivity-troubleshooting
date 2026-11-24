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

\#chatgpt-mermaid-\_r_14k\_{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:16px;fill:rgb(13, 13, 13);}@keyframes edge-animation-frame{from{stroke-dashoffset:0;}}@keyframes dash{to{stroke-dashoffset:0;}}#chatgpt-mermaid-\_r_14k\_ .edge-animation-slow{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 50s linear infinite;stroke-linecap:round;}#chatgpt-mermaid-\_r_14k\_ .edge-animation-fast{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 20s linear infinite;stroke-linecap:round;}#chatgpt-mermaid-\_r_14k\_ .error-icon{fill:rgb(243, 243, 243);}#chatgpt-mermaid-\_r_14k\_ .error-text{fill:rgb(13, 13, 13);stroke:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_14k\_ .edge-thickness-normal{stroke-width:1px;}#chatgpt-mermaid-\_r_14k\_ .edge-thickness-thick{stroke-width:3.5px;}#chatgpt-mermaid-\_r_14k\_ .edge-pattern-solid{stroke-dasharray:0;}#chatgpt-mermaid-\_r_14k\_ .edge-thickness-invisible{stroke-width:0;fill:none;}#chatgpt-mermaid-\_r_14k\_ .edge-pattern-dashed{stroke-dasharray:3;}#chatgpt-mermaid-\_r_14k\_ .edge-pattern-dotted{stroke-dasharray:2;}#chatgpt-mermaid-\_r_14k\_ .marker{fill:rgb(143, 143, 143);stroke:rgb(143, 143, 143);}#chatgpt-mermaid-\_r_14k\_ .marker.cross{stroke:rgb(143, 143, 143);}#chatgpt-mermaid-\_r_14k\_ svg{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:16px;}#chatgpt-mermaid-\_r_14k\_ p{margin:0;}#chatgpt-mermaid-\_r_14k\_ .label{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";color:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_14k\_ .cluster-label text{fill:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_14k\_ .cluster-label span{color:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_14k\_ .cluster-label span p{background-color:transparent;}#chatgpt-mermaid-\_r_14k\_ .label text,#chatgpt-mermaid-\_r_14k\_ span{fill:rgb(13, 13, 13);color:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_14k\_ .node rect,#chatgpt-mermaid-\_r_14k\_ .node circle,#chatgpt-mermaid-\_r_14k\_ .node ellipse,#chatgpt-mermaid-\_r_14k\_ .node polygon,#chatgpt-mermaid-\_r_14k\_ .node path{fill:rgb(222, 234, 251);stroke:rgb(83, 154, 248);stroke-width:1px;}#chatgpt-mermaid-\_r_14k\_ .rough-node .label text,#chatgpt-mermaid-\_r_14k\_ .node .label text,#chatgpt-mermaid-\_r_14k\_ .image-shape .label,#chatgpt-mermaid-\_r_14k\_ .icon-shape .label{text-anchor:middle;}#chatgpt-mermaid-\_r_14k\_ .node .katex path{fill:#000;stroke:#000;stroke-width:1px;}#chatgpt-mermaid-\_r_14k\_ .rough-node .label,#chatgpt-mermaid-\_r_14k\_ .node .label,#chatgpt-mermaid-\_r_14k\_ .image-shape .label,#chatgpt-mermaid-\_r_14k\_ .icon-shape .label{text-align:center;}#chatgpt-mermaid-\_r_14k\_ .node.clickable{cursor:pointer;}#chatgpt-mermaid-\_r_14k\_ .root .anchor path{fill:rgb(143, 143, 143)!important;stroke-width:0;stroke:rgb(143, 143, 143);}#chatgpt-mermaid-\_r_14k\_ .arrowheadPath{fill:rgb(143, 143, 143);}#chatgpt-mermaid-\_r_14k\_ .edgePath .path{stroke:rgb(143, 143, 143);stroke-width:1px;}#chatgpt-mermaid-\_r_14k\_ .flowchart-link{stroke:rgb(143, 143, 143);fill:none;}#chatgpt-mermaid-\_r_14k\_ .edgeLabel{background-color:rgb(252, 252, 252);text-align:center;}#chatgpt-mermaid-\_r_14k\_ .edgeLabel p{background-color:rgb(252, 252, 252);}#chatgpt-mermaid-\_r_14k\_ .edgeLabel rect{opacity:0.5;background-color:rgb(252, 252, 252);fill:rgb(252, 252, 252);}#chatgpt-mermaid-\_r_14k\_ .labelBkg{background-color:rgba(252, 252, 252, 0.5);}#chatgpt-mermaid-\_r_14k\_ .cluster rect{fill:rgb(243, 243, 243);stroke:rgba(0, 0, 0, 0.1);stroke-width:1px;}#chatgpt-mermaid-\_r_14k\_ .cluster text{fill:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_14k\_ .cluster span{color:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_14k\_ div.mermaidTooltip{position:absolute;text-align:center;max-width:200px;padding:2px;font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:12px;background:rgb(243, 243, 243);border:1px solid rgba(0, 0, 0, 0.1);border-radius:2px;pointer-events:none;z-index:100;}#chatgpt-mermaid-\_r_14k\_ .flowchartTitleText{text-anchor:middle;font-size:18px;fill:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_14k\_ rect.text{fill:none;stroke-width:0;}#chatgpt-mermaid-\_r_14k\_ .icon-shape,#chatgpt-mermaid-\_r_14k\_ .image-shape{background-color:rgb(252, 252, 252);text-align:center;}#chatgpt-mermaid-\_r_14k\_ .icon-shape p,#chatgpt-mermaid-\_r_14k\_ .image-shape p{background-color:rgb(252, 252, 252);padding:2px;}#chatgpt-mermaid-\_r_14k\_ .icon-shape .label rect,#chatgpt-mermaid-\_r_14k\_ .image-shape .label rect{opacity:0.5;background-color:rgb(252, 252, 252);fill:rgb(252, 252, 252);}#chatgpt-mermaid-\_r_14k\_ .label-icon{display:inline-block;height:1em;overflow:visible;vertical-align:-0.125em;}#chatgpt-mermaid-\_r_14k\_ .node .label-icon path{fill:currentColor;stroke:revert;stroke-width:revert;}#chatgpt-mermaid-\_r_14k\_ .node .neo-node{stroke:rgb(83, 154, 248);}#chatgpt-mermaid-\_r_14k\_ [data-look="neo"].node rect,#chatgpt-mermaid-\_r_14k\_ [data-look="neo"].cluster rect,#chatgpt-mermaid-\_r_14k\_ [data-look="neo"].node polygon{stroke:url(#chatgpt-mermaid-\_r_14k\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_14k\_ [data-look="neo"].swimlane.cluster rect{filter:none;}#chatgpt-mermaid-\_r_14k\_ [data-look="neo"].node path{stroke:url(#chatgpt-mermaid-\_r_14k\_-gradient);stroke-width:1px;}#chatgpt-mermaid-\_r_14k\_ [data-look="neo"].node .outer-path{filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_14k\_ [data-look="neo"].node .neo-line path{stroke:rgb(83, 154, 248);filter:none;}#chatgpt-mermaid-\_r_14k\_ [data-look="neo"].node circle{stroke:url(#chatgpt-mermaid-\_r_14k\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_14k\_ [data-look="neo"].node circle .state-start{fill:#000000;}#chatgpt-mermaid-\_r_14k\_ [data-look="neo"].icon-shape .icon{fill:url(#chatgpt-mermaid-\_r_14k\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_14k\_ [data-look="neo"].icon-shape .icon-neo path{stroke:url(#chatgpt-mermaid-\_r_14k\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_14k\_ .node text{font-size:14px;font-weight:600;letter-spacing:normal;fill:rgb(0, 79, 153);}#chatgpt-mermaid-\_r_14k\_ .edgeLabels text{font-size:13px;font-weight:600;letter-spacing:-0.08px;fill:rgb(0, 79, 153);}#chatgpt-mermaid-\_r_14k\_ .node tspan[font-weight="normal"],#chatgpt-mermaid-\_r_14k\_ .edgeLabels tspan[font-weight="normal"]{font-weight:600;}#chatgpt-mermaid-\_r_14k\_ .edgeLabel .label rect{opacity:1;rx:13px;ry:13px;fill:rgb(245, 250, 255);stroke:rgb(206, 219, 229);stroke-width:1px;}#chatgpt-mermaid-\_r_14k\_ .node rect,#chatgpt-mermaid-\_r_14k\_ .node circle,#chatgpt-mermaid-\_r_14k\_ .node ellipse,#chatgpt-mermaid-\_r_14k\_ .node polygon,#chatgpt-mermaid-\_r_14k\_ .node path{fill:rgb(229, 243, 255);stroke:rgba(0, 0, 0, 0.1);stroke-width:1px;}#chatgpt-mermaid-\_r_14k\_ .node rect{rx:16px;ry:16px;}#chatgpt-mermaid-\_r_14k\_ .mermaid-decision .label-container{fill:rgb(245, 250, 255);stroke:rgb(206, 219, 229);stroke-dasharray:2,2;}#chatgpt-mermaid-\_r_14k\_ .edgePaths .flowchart-link{stroke:rgb(143, 143, 143);stroke-width:1px;stroke-linecap:round;stroke-linejoin:round;}#chatgpt-mermaid-\_r_14k\_ .marker{fill:rgb(143, 143, 143);stroke:rgb(143, 143, 143);}#chatgpt-mermaid-\_r_14k\_ :root{--mermaid-font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";}Connectivity FailureInspect IP ConfigurationPerform Connectivity TestsCompare with HealthyEndpointIdentify Root CauseImplement TargetedRemediationValidate ConnectivityDocument Resolution

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

## **GitHub repository settings**

**Repository name**

`network-connectivity-restoration`

**Repository description**

Enterprise-style network troubleshooting project demonstrating TCP/IP diagnostics, endpoint fault isolation, static IPv4 remediation, root cause analysis, and connectivity validation in a Windows environment.

**GitHub topics**

`it-support` `help-desk` `networking` `tcp-ip` `windows-11` `network-troubleshooting` `root-cause-analysis` `incident-resolution` `network-administration` `technical-support` `it-portfolio`
