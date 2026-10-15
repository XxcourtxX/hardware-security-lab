# Local Lab Learning Notes

[Overview](README.md) · [DuckyScript example](examples/timing-demo.duck) · [Main homelab](https://github.com/XxcourtxX/Vulnerability-Assessment-Basics.github.io/blob/main/homelab.md)

## DuckyScript: timing and variable debugging
**Work reviewed:** a typed-text exercise with variables, a boolean switch, arithmetic, IF/ELSE branches, STRINGLN, DELAY, and button-controlled device modes.

**Problem:** a variable reference used $DELAY_TIME_TIME rather than the defined $DELAY_TIME.

**Correction:** align the reference with the declaration. Keep the initial wait value and the increment value distinct so the behavior is easier to explain.

**Concept:** increasing a wait value produces longer delays between later lines. Setting the wait and increment to zero disables those between-line delays. Device initialization time is separate.

**Published artifact:** a new three-line demo with original text. It is a reconstruction of the learning concept, not the original payload or a hardware-validated release. DuckyScript version and firmware support must match the target device.

## Wi-Fi Pineapple TETRA: Recon concepts
I reviewed using Recon to understand discovered network information, including SSIDs, BSSIDs, channels, signal strength, and client information. I also asked about retaining discovered SSIDs and how that differs from an exported survey report.

**Learning point:** a network name is not a unique device identifier; SSID, BSSID, channel, and signal represent different attributes. A reconnaissance discussion is not evidence of successful access or compromise.

**Evidence status:** learning discussion recorded; no sanitized, completed wireless assessment report is published here.

## Wi-Fi Pineapple Mark VII: capture interpretation
I discussed identifying collected handshakes and understanding what a BSSID tells me. This is wireless-protocol learning, not a claim of a recovered password or successful intrusion.

**Next documentation goal:** use a dedicated lab access point and client, record the agreed scope, and describe the metadata and observations without publishing private captures or third-party identifiers.

## Shark Jack: wired-network learning
Shark Jack is part of my learning toolkit. My earlier discussions included wired discovery, device connection/interface concepts, and how network observations could complement Wireshark and Nmap work.

**Evidence status:** no device-specific execution log or verified Shark Jack assessment result is included. My portfolio distinguishes owning/studying a tool from demonstrating a completed test with it.

## Local network discovery and service enumeration
I worked through identifying my network range using ip -4 route and the distinction between Nmap target listing and discovery:
- -sL lists targets; it may still perform DNS lookups.
- -sn performs host discovery without a port scan.
- Port scanning and service/version detection answer different questions from whether a host is present.

I also discussed reviewing services exposed by my own Jellyfin server before considering hardening. The discussion proposed a workflow; it does not establish that every subsequent tool or test was executed.

**Documentation still to add:** actual command, own-lab target description, timestamp, sanitized result, interpretation, and any remediation/retest. No vulnerability or compromise is claimed without that evidence.

## Skills demonstrated by this learning
- Breaking a script into initialization, conditionals, state updates, and output.
- Finding a misspelled variable reference and explaining the resulting behavior.
- Distinguishing device capability, reconnaissance, and verified findings.
- Understanding network scope and documenting limitations honestly.
- Connecting scripting and network fundamentals to defensive controls.

## Lab record template
| Field | Record for a future completed exercise |
| --- | --- |
| Objective | What question am I testing? |
| Scope | My lab target and permission boundary |
| Environment | Device, firmware, OS, and relevant configuration |
| Steps run | Exact steps actually executed |
| Expected / observed | Prediction compared with real output |
| Evidence | Sanitized captures or terminal output |
| Interpretation | What the evidence supports and what remains unknown |
| Defensive takeaway | Hardening or monitoring improvement |
| Retest | Whether the change worked |
