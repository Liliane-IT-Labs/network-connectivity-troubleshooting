# network-connectivity-troubleshooting

# **Network Troubleshooting & Connectivity Restoration**

`Windows 11` `TCP/IP` `Network Troubleshooting` `IT Support` `Root Cause Analysis`

## **1. Project overview**

A corporate laptop was connected to a small office/home office (SOHO) network but was unable to access the internet, while other devices remained operational.

The objective of this project is to diagnose the connectivity failure, identify the root cause, implement a targeted solution, and verify full network functionality using a structured IT troubleshooting methodology.

## **2. Technical environment**

| Component           | Description                         |
| ------------------- | ----------------------------------- |
| Operating system    | Windows 11                          |
| Network environment | SOHO                                |
| Affected device     | Home-Laptop                         |
| Reference device    | Home-PC1                            |
| Additional device   | Home-PC2                            |
| Default gateway     | 192.168.1.1                         |
| Diagnostic tools    | Windows Network Settings, CLI, ICMP |
| IP assignment       | Static IPv4                         |

## **3. Troubleshooting methodology**

\#chatgpt-mermaid-\_r_11o\_{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:16px;fill:rgb(13, 13, 13);}@keyframes edge-animation-frame{from{stroke-dashoffset:0;}}@keyframes dash{to{stroke-dashoffset:0;}}#chatgpt-mermaid-\_r_11o\_ .edge-animation-slow{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 50s linear infinite;stroke-linecap:round;}#chatgpt-mermaid-\_r_11o\_ .edge-animation-fast{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 20s linear infinite;stroke-linecap:round;}#chatgpt-mermaid-\_r_11o\_ .error-icon{fill:rgb(243, 243, 243);}#chatgpt-mermaid-\_r_11o\_ .error-text{fill:rgb(13, 13, 13);stroke:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_11o\_ .edge-thickness-normal{stroke-width:1px;}#chatgpt-mermaid-\_r_11o\_ .edge-thickness-thick{stroke-width:3.5px;}#chatgpt-mermaid-\_r_11o\_ .edge-pattern-solid{stroke-dasharray:0;}#chatgpt-mermaid-\_r_11o\_ .edge-thickness-invisible{stroke-width:0;fill:none;}#chatgpt-mermaid-\_r_11o\_ .edge-pattern-dashed{stroke-dasharray:3;}#chatgpt-mermaid-\_r_11o\_ .edge-pattern-dotted{stroke-dasharray:2;}#chatgpt-mermaid-\_r_11o\_ .marker{fill:rgb(143, 143, 143);stroke:rgb(143, 143, 143);}#chatgpt-mermaid-\_r_11o\_ .marker.cross{stroke:rgb(143, 143, 143);}#chatgpt-mermaid-\_r_11o\_ svg{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:16px;}#chatgpt-mermaid-\_r_11o\_ p{margin:0;}#chatgpt-mermaid-\_r_11o\_ .label{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";color:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_11o\_ .cluster-label text{fill:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_11o\_ .cluster-label span{color:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_11o\_ .cluster-label span p{background-color:transparent;}#chatgpt-mermaid-\_r_11o\_ .label text,#chatgpt-mermaid-\_r_11o\_ span{fill:rgb(13, 13, 13);color:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_11o\_ .node rect,#chatgpt-mermaid-\_r_11o\_ .node circle,#chatgpt-mermaid-\_r_11o\_ .node ellipse,#chatgpt-mermaid-\_r_11o\_ .node polygon,#chatgpt-mermaid-\_r_11o\_ .node path{fill:rgb(222, 234, 251);stroke:rgb(83, 154, 248);stroke-width:1px;}#chatgpt-mermaid-\_r_11o\_ .rough-node .label text,#chatgpt-mermaid-\_r_11o\_ .node .label text,#chatgpt-mermaid-\_r_11o\_ .image-shape .label,#chatgpt-mermaid-\_r_11o\_ .icon-shape .label{text-anchor:middle;}#chatgpt-mermaid-\_r_11o\_ .node .katex path{fill:#000;stroke:#000;stroke-width:1px;}#chatgpt-mermaid-\_r_11o\_ .rough-node .label,#chatgpt-mermaid-\_r_11o\_ .node .label,#chatgpt-mermaid-\_r_11o\_ .image-shape .label,#chatgpt-mermaid-\_r_11o\_ .icon-shape .label{text-align:center;}#chatgpt-mermaid-\_r_11o\_ .node.clickable{cursor:pointer;}#chatgpt-mermaid-\_r_11o\_ .root .anchor path{fill:rgb(143, 143, 143)!important;stroke-width:0;stroke:rgb(143, 143, 143);}#chatgpt-mermaid-\_r_11o\_ .arrowheadPath{fill:rgb(143, 143, 143);}#chatgpt-mermaid-\_r_11o\_ .edgePath .path{stroke:rgb(143, 143, 143);stroke-width:1px;}#chatgpt-mermaid-\_r_11o\_ .flowchart-link{stroke:rgb(143, 143, 143);fill:none;}#chatgpt-mermaid-\_r_11o\_ .edgeLabel{background-color:rgb(252, 252, 252);text-align:center;}#chatgpt-mermaid-\_r_11o\_ .edgeLabel p{background-color:rgb(252, 252, 252);}#chatgpt-mermaid-\_r_11o\_ .edgeLabel rect{opacity:0.5;background-color:rgb(252, 252, 252);fill:rgb(252, 252, 252);}#chatgpt-mermaid-\_r_11o\_ .labelBkg{background-color:rgba(252, 252, 252, 0.5);}#chatgpt-mermaid-\_r_11o\_ .cluster rect{fill:rgb(243, 243, 243);stroke:rgba(0, 0, 0, 0.1);stroke-width:1px;}#chatgpt-mermaid-\_r_11o\_ .cluster text{fill:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_11o\_ .cluster span{color:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_11o\_ div.mermaidTooltip{position:absolute;text-align:center;max-width:200px;padding:2px;font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:12px;background:rgb(243, 243, 243);border:1px solid rgba(0, 0, 0, 0.1);border-radius:2px;pointer-events:none;z-index:100;}#chatgpt-mermaid-\_r_11o\_ .flowchartTitleText{text-anchor:middle;font-size:18px;fill:rgb(13, 13, 13);}#chatgpt-mermaid-\_r_11o\_ rect.text{fill:none;stroke-width:0;}#chatgpt-mermaid-\_r_11o\_ .icon-shape,#chatgpt-mermaid-\_r_11o\_ .image-shape{background-color:rgb(252, 252, 252);text-align:center;}#chatgpt-mermaid-\_r_11o\_ .icon-shape p,#chatgpt-mermaid-\_r_11o\_ .image-shape p{background-color:rgb(252, 252, 252);padding:2px;}#chatgpt-mermaid-\_r_11o\_ .icon-shape .label rect,#chatgpt-mermaid-\_r_11o\_ .image-shape .label rect{opacity:0.5;background-color:rgb(252, 252, 252);fill:rgb(252, 252, 252);}#chatgpt-mermaid-\_r_11o\_ .label-icon{display:inline-block;height:1em;overflow:visible;vertical-align:-0.125em;}#chatgpt-mermaid-\_r_11o\_ .node .label-icon path{fill:currentColor;stroke:revert;stroke-width:revert;}#chatgpt-mermaid-\_r_11o\_ .node .neo-node{stroke:rgb(83, 154, 248);}#chatgpt-mermaid-\_r_11o\_ [data-look="neo"].node rect,#chatgpt-mermaid-\_r_11o\_ [data-look="neo"].cluster rect,#chatgpt-mermaid-\_r_11o\_ [data-look="neo"].node polygon{stroke:url(#chatgpt-mermaid-\_r_11o\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_11o\_ [data-look="neo"].swimlane.cluster rect{filter:none;}#chatgpt-mermaid-\_r_11o\_ [data-look="neo"].node path{stroke:url(#chatgpt-mermaid-\_r_11o\_-gradient);stroke-width:1px;}#chatgpt-mermaid-\_r_11o\_ [data-look="neo"].node .outer-path{filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_11o\_ [data-look="neo"].node .neo-line path{stroke:rgb(83, 154, 248);filter:none;}#chatgpt-mermaid-\_r_11o\_ [data-look="neo"].node circle{stroke:url(#chatgpt-mermaid-\_r_11o\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_11o\_ [data-look="neo"].node circle .state-start{fill:#000000;}#chatgpt-mermaid-\_r_11o\_ [data-look="neo"].icon-shape .icon{fill:url(#chatgpt-mermaid-\_r_11o\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_11o\_ [data-look="neo"].icon-shape .icon-neo path{stroke:url(#chatgpt-mermaid-\_r_11o\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_11o\_ .node text{font-size:14px;font-weight:600;letter-spacing:normal;fill:rgb(0, 79, 153);}#chatgpt-mermaid-\_r_11o\_ .edgeLabels text{font-size:13px;font-weight:600;letter-spacing:-0.08px;fill:rgb(0, 79, 153);}#chatgpt-mermaid-\_r_11o\_ .node tspan[font-weight="normal"],#chatgpt-mermaid-\_r_11o\_ .edgeLabels tspan[font-weight="normal"]{font-weight:600;}#chatgpt-mermaid-\_r_11o\_ .edgeLabel .label rect{opacity:1;rx:13px;ry:13px;fill:rgb(245, 250, 255);stroke:rgb(206, 219, 229);stroke-width:1px;}#chatgpt-mermaid-\_r_11o\_ .node rect,#chatgpt-mermaid-\_r_11o\_ .node circle,#chatgpt-mermaid-\_r_11o\_ .node ellipse,#chatgpt-mermaid-\_r_11o\_ .node polygon,#chatgpt-mermaid-\_r_11o\_ .node path{fill:rgb(229, 243, 255);stroke:rgba(0, 0, 0, 0.1);stroke-width:1px;}#chatgpt-mermaid-\_r_11o\_ .node rect{rx:16px;ry:16px;}#chatgpt-mermaid-\_r_11o\_ .mermaid-decision .label-container{fill:rgb(245, 250, 255);stroke:rgb(206, 219, 229);stroke-dasharray:2,2;}#chatgpt-mermaid-\_r_11o\_ .edgePaths .flowchart-link{stroke:rgb(143, 143, 143);stroke-width:1px;stroke-linecap:round;stroke-linejoin:round;}#chatgpt-mermaid-\_r_11o\_ .marker{fill:rgb(143, 143, 143);stroke:rgb(143, 143, 143);}#chatgpt-mermaid-\_r_11o\_ :root{--mermaid-font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";}Identify Connectivity FailureInspect IP ConfigurationTest Network ConnectivityCompare with Working DeviceIdentify Root CauseCorrect IP ConfigurationVerify Network Functionality

## **4. Project implementation**

### **Step 1 — Inspect the affected device**

**Objective:** Identify potential network configuration issues before making changes.

On Home-Laptop:

1. Right-click **Home-Laptop** and select **Launch Windows**.
2. Check the network connection status in the system tray.
3. Navigate to **Settings → Network & Internet → Ethernet**.
4. Locate **IP assignment** and select **Edit**.
5. Examine the IPv4 address, subnet mask, default gateway, and DNS settings.
6. Select **Cancel** without modifying the configuration.

**CLI — Additional configuration inspection:**

```
ipconfig /all
```

**Screenshot:** `01-initial-ip-configuration.png`

### **Step 2 — Test network connectivity**

**Objective:** Identify the scope of the connectivity failure.

Right-click **Start → Terminal (Admin)** and execute the following commands on Home-Laptop:

```
ping Home-Laptop
ping Home-PC1
ping Home-PC2
ping 192.168.1.1
```

| Test            | Purpose                                        |
| --------------- | ---------------------------------------------- |
| Home-Laptop     | Verify local host communication                |
| Home-PC1        | Test communication with a network workstation  |
| Home-PC2        | Test communication with another network device |
| Default gateway | Verify router accessibility                    |

**Screenshot:** `02-initial-connectivity-tests.png`

### **Step 3 — Inspect a known-good device**

**Objective:** Establish a working network configuration for comparison.

Return to **Network Modeler** and launch Windows on Home-PC1.

Navigate to **Settings → Network & Internet → Ethernet → IP assignment → Edit**.

Examine and compare the network configuration with Home-Laptop.

**CLI — Additional configuration inspection:**

```
ipconfig /all
```

Compare the following parameters:

- IPv4 address
- Subnet mask
- Default gateway
- DNS servers

**Screenshot:** `03-working-device-configuration.png`

### **Step 4 — Test connectivity from the working device**

**Objective:** Determine whether the issue is device-specific or network-wide.

Open **Terminal (Admin)** on Home-PC1.

```
ping Home-Laptop
ping Home-PC1
ping Home-PC2
ping 192.168.1.1
```

Compare these results with the initial connectivity tests performed on Home-Laptop.

**Screenshot:** `04-reference-connectivity-tests.png`

### **Step 5 — Identify the root cause**

**Objective:** Establish the probable cause based on diagnostic evidence.

The network configuration comparison revealed a typographical error in Home-Laptop's static IPv4 address, placing the device on the wrong network.

| Finding              | Assessment                              |
| -------------------- | --------------------------------------- |
| Affected device      | Home-Laptop                             |
| Root cause           | Incorrect static IPv4 address           |
| Network impact       | Local and internet connectivity failure |
| Required remediation | Correct IPv4 configuration              |

The issue was related to the endpoint configuration rather than a network-wide infrastructure failure.

### **Step 6 — Implement the solution**

**Objective:** Restore network communication by correcting the IPv4 configuration.

On Home-Laptop:

1. Navigate to **Settings → Network & Internet → Ethernet**.
2. Locate **IP assignment**.
3. Select **Edit**.
4. Correct the IPv4 address to `192.168.1.20`.
5. Preserve the other valid network settings.
6. Select **Save**.

Verify the updated configuration:

```
ipconfig /all
```

**Screenshot:** `05-corrected-ip-configuration.png`

### **Step 7 — Verify full system functionality**

**Objective:** Confirm that the remediation resolved the original issue.

Verify that Home-Laptop is connected to HomeNet and displays internet connectivity.

Repeat the initial diagnostic commands:

```
ping Home-Laptop
ping Home-PC1
ping Home-PC2
ping 192.168.1.1
```

**Additional real-world verification (if supported by the lab):**

```
ping 8.8.8.8
nslookup google.com
```

The additional tests help distinguish external network connectivity from DNS resolution. Confirm internet access through a web browser when available.

**Screenshot:** `06-post-remediation-verification.png`

## **5. Expected project results**

| Metric                        | Before remediation | After remediation |
| ----------------------------- | ------------------ | ----------------- |
| IPv4 configuration            | Incorrect          | Corrected         |
| Local network connectivity    | Failed             | Restored          |
| Default gateway accessibility | Unavailable        | Available         |
| Internet connectivity         | Unavailable        | Restored          |
| Connectivity tests            | Failed tests       | 4/4 successful    |

**Root cause:** Static IPv4 misconfiguration.

**Resolution:** Corrected the laptop's IP address to `192.168.1.20`.

**Business impact:** Restored endpoint connectivity without unnecessary changes to the existing network infrastructure.

## **6. Technical skills demonstrated**

- TCP/IP troubleshooting
- Windows network administration
- IPv4 configuration management
- Command-line network diagnostics
- ICMP connectivity testing
- Root cause analysis
- Network fault isolation
- Post-remediation validation
- Technical documentation

## **7. Repository structure**

```
network-connectivity-troubleshooting/
│
├── README.md
└── screenshots/
    ├── 01-initial-ip-configuration.png
    ├── 02-initial-connectivity-tests.png
    ├── 03-working-device-configuration.png
    ├── 04-reference-connectivity-tests.png
    ├── 05-corrected-ip-configuration.png
    └── 06-post-remediation-verification.png
```

## **8. Conclusion**

This project demonstrates an evidence-based approach to network troubleshooting, from initial diagnosis through remediation and verification.

By comparing a faulty endpoint with a known-good device, the connectivity issue can be isolated and resolved without unnecessary changes to the network infrastructure.

**Effective IT support is not about making more changes. It is about making the right change and proving that it works.**

## **GitHub repository settings**

**Repository name:** `network-connectivity-troubleshooting`

**Description:**

Windows network troubleshooting project demonstrating TCP/IP diagnostics, static IPv4 remediation, root cause analysis, and endpoint connectivity restoration.

**Topics:**

`it-support` `networking` `windows-11` `tcp-ip` `help-desk` `network-troubleshooting` `root-cause-analysis` `comptia` `network-administration`
