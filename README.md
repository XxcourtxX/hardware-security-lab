# Hardware Security & DuckyScript Learning Lab

**Cristian Luna** · Cybersecurity student, Chattahoochee Technical College  
[LinkedIn](https://www.linkedin.com/in/cristian-luna-234749287/) · [Main portfolio](https://github.com/XxcourtxX/Vulnerability-Assessment-Basics.github.io)

I am learning how USB input devices, wireless assessment tools, and network discovery work in a personal home lab. This repository documents my programming practice and technical understanding, with clear distinctions between exercises, device familiarity, and completed test results.

## What I have worked on
### DuckyScript programming and debugging
My earlier scripting exercise involved typed-text output, configurable delays, a true/false timing toggle, and progressively increasing delays between lines. I reviewed variable initialization, arithmetic, IF/ELSE flow, and a button-controlled mode change.

A concrete debugging lesson was correcting a reference to an undefined variable, **$DELAY_TIME_TIME**, to the intended **$DELAY_TIME**. I also worked through why initializing a value and updating it after each line are different operations.

The published demo uses original placeholder text instead of the song lyrics used in my earlier exercise. It demonstrates the timing concept without reproducing that content.

- [Harmless DuckyScript timing demo](examples/timing-demo.duck)
- [Local network and device learning notes](lab-notes.md)

### Personal network security learning
I have explored identifying my local subnet, discovering hosts, and distinguishing host discovery from port scanning with Nmap. I have also discussed service enumeration of my own homelab servers and how findings would guide hardening. This repository does not claim a completed professional penetration test or publish unverified vulnerabilities.

## What is BadUSB?
BadUSB describes a class of USB trust problems in which a device can present capabilities other than what a user expects. In my learning context, a programmable USB device can emulate a **Human Interface Device (HID)** such as a keyboard and send scripted keystrokes. The host can accept those inputs as if someone typed them.

A typing demo is not itself evidence that a system was compromised. The security lesson is that a USB device's appearance does not establish what interfaces or actions it can expose.

## Devices in my learning toolkit
| Device | Learning focus | Status represented here |
| --- | --- | --- |
| USB Rubber Ducky / BadUSB devices | HID behavior, scripted text, timing, variables, conditionals | Prior script-writing and debugging exercise; reconstructed demo included |
| Wi-Fi Pineapple Mark VII | Wireless assessment concepts and handshake/BSSID interpretation | Learning and discussion; no completed exploitation result claimed |
| Wi-Fi Pineapple TETRA | Recon, SSIDs, BSSIDs, channels, and signal information | Reviewed Recon and recording discovered network information |
| Shark Jack | Wired-network discovery and device/interface concepts | Toolkit familiarity and study; no verified device-specific assessment report yet |

Device support differs: DuckyScript 3 features are not automatically supported by every product advertised as BadUSB.

## Demo scope
The example expects a blank text editor to be opened and focused manually on a lab computer. It types three short lines with optional increasing delays. It does not open a terminal, fetch code, collect credentials, change system settings, or send data over a network. Hardware execution of this newly published reconstruction has not been verified.

## How I document a lab
For each future exercise, I aim to record the target I own, objective, device and firmware, steps actually run, expected versus observed behavior, evidence, and defensive takeaway. Private addresses, credentials, wireless identifiers, captures from other people's devices, and personal data are excluded from public write-ups.

## Next steps
- Compile and test the typing demo on the intended DuckyScript-compatible device.
- Record observed timing and correct any firmware-specific differences.
- Add sanitized evidence from scoped home-network discovery exercises.
- Document defensive controls such as USB device allowlisting and monitoring unexpected HID connections.

## References
- [Hak5 DuckyScript quick reference](https://docs.hak5.org/hak5-usb-rubber-ducky/duckyscript-tm-quick-reference)
- [Hak5 WiFi Pineapple Mark VII documentation](https://docs.hak5.org/wifi-pineapple/)
- [Hak5 NANO/TETRA Recon module documentation](https://docs.hak5.org/wifi-pineapple-6th-gen-nano-tetra/development/wifi-pineapple-nano-tetra-module-api-modules)
- [Hak5 Shark Jack basics](https://olddocs.hak5.org/shark-jack/getting-started/shark-jack-basics)

All testing is limited to systems and networks I own or have explicit authorization to assess.
