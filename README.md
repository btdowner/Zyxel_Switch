[← Back to Home](https://github.com/btdowner)

---

# 🛠️ Zyxel GS2210-24HP Switch Restoration Project

---

## 📘 Project Overview
This project involved the successful restoration and hardware modification of a **Zyxel GS2210-24HP** enterprise managed PoE+ switch. Originally retailing for ~$570, I acquired this unit in a non-factory state for under $40. 

Through **serial console recovery** and a **custom silent fan modification**, I transformed a loud, decommissioned unit into a high-performance, whisper-quiet core switch for my CCNA home lab.

---

## 🧰 Project Financials & ROI
| Item | Cost | Notes |
| :--- | :--- | :--- |
| **Zyxel GS2210-24HP** | $37.74 | Acquired via eBay (Used) |
| **3x Noctua NF-A4x10 FLX Fans** | $47.85 | Upgraded for acoustic performance |
| **USB-to-DB9 Console Cable** | $9.99 | Required for CLI recovery |
| **Total Investment** | **$95.58** | **83% Savings vs. Retail ($571)** |

---

## 🌬️ Hardware Mod: The "Noctua Upgrade"
The factory fans were rated at ~35 dBA, making the switch too loud for an office environment. I replaced them with Noctua fans, reducing the noise floor to **17.9 dBA**.

### 🔧 The Re-Pinning Process
The Noctua fans required a custom pinout modification to match the Zyxel proprietary header. I performed a non-destructive de-pinning of the Molex connectors to align the wiring:

* **Factory Pinout:** Red (V+), Blue (Tach), Black (GND)
* **Noctua Pinout:** Black (GND), Red (V+), Yellow (Tach)

> [!IMPORTANT]
> By re-ordering the pins manually, I avoided cutting or soldering, maintaining a clean, professional internal build.

<p align="center">
  <img src="A20250711_161936.jpg" width="48%" alt="Internal Fan Wiring" />
  <img src="b20250711_142047.jpg" width="48%" alt="Finished Hardware Assembly" />
</p>

---

## 🧪 Recovery & Configuration
Since the previous owner’s IP was unknown and undiscoverable via `nmap` or packet sniffing, I performed a **factory reset via Serial Console**.

### Tools Used:
* **Hardware:** USB-to-Serial (Prolific Chipset)
* **Software:** PuTTY / Tera Term / Nmap
* **Method:** Intercepted boot sequence via console to trigger a factory wipe.

### Post-Reset Hardening:
* **IP Management:** Moved management interface to **VLAN 10** to resolve IP conflicts.
* **Security:** Enabled **SSH**, disabled insecure Telnet.
* **VLAN Trunking:** Configured 802.1Q trunks for **pfSense**, **Omada WAPs**, and **Proxmox**.
* **Port Security:** Disabled all unused ports and added detailed port descriptions.
* **Monitoring:** Enabled **SNMP** and **LLDP** for network mapping and Zabbix integration.

---

## 📦 Homelab Integration
This switch now serves as my **PoE+ Power House**, supporting:
* **Wireless Access Points:** Powering TP-Link Omada gear.
* **VLAN Segmentation:** Isolating IoT, Management, and Lab traffic.
* **CCNA Practice:** Serving as a live environment for LACP, Port Mirroring, and ACL testing.

---

## ✅ Key Skills Demonstrated
* **Layer 2 Networking:** VLAN tagging, Trunking, and SNMP.
* **Hardware Maintenance:** Thermal management and electronics modification.
* **Out-of-Band Management:** Troubleshooting via Serial/CLI when GUI access is unavailable.
* **Infrastructure Budgeting:** Cost-benefit analysis and enterprise hardware refurbishment.

---

## 🔗 LinkedIn
💼 [Connect with me on LinkedIn](https://www.linkedin.com/in/brandonthomasdowner)

@import "{{ site.theme }}";

/* Target the specific Midnight layout tags */
.wrapper, section, header {
  max-width: 95% !important;
  width: 95% !important;
  margin: 0 auto !important;
}

section {
  padding: 20px 0 !important;
}

pre, .highlight {
  width: 100% !important;
  box-sizing: border-box !important;
}
