
# Verkada NOC Simulator

An interactive browser-based NOC dashboard that simulates how a Verkada TSE diagnoses and resolves real site failures — built directly in response to networking depth feedback from my Verkada Round 3 TSE interview.

## Live Demo
👉 [sanjananuguri.github.io/verkada-noc-simulator](https://sanjananuguri.github.io/verkada-noc-simulator)

## Why I Built This

After my Round 3 Verkada TSE interview, the feedback I received was that my networking depth needed work. Instead of just studying theory, I built three hands-on projects in Verkada's specific context. This NOC simulator is the third — it ties together networking knowledge and TSE diagnostic thinking in one interactive tool.

## What It Does

A simulated Verkada site topology — router, firewall, PoE switch, AC43-G controller, NTP server, and three cameras — with four real-world failure scenarios a TSE would encounter:

**1. WAN Uplink Down**
Simulates primary fiber loss, detects missed heartbeat intervals, checks AC43-G cellular modem signal strength, and initiates automatic failover to cellular backup — mirroring Verkada's real AC43-G architecture.

**2. PoE Budget Exceeded**
Simulates a switch bank exceeding its 370W rated budget after a high-draw camera is added. Identifies the last-negotiated device as the one dropped and recommends port redistribution or PoE+ upgrade.

**3. NTP Drift / Certificate Failure**
Simulates clock drift of 340 seconds causing TLS certificate validation failures on the AC43-G controller. Traces root cause to NTP source losing upstream sync, resolves via secondary time source.

**4. VLAN Misconfiguration**
Simulates a camera going offline after a port was accidentally moved to the corporate VLAN during a desk move. Physical link shows green but device is invisible to Verkada Command — resolved by correcting the access VLAN assignment.

Each scenario generates a timestamped support ticket with full TSE diagnostic logic — showing not just what broke but how a TSE thinks through it step by step.

## Tech Stack
- HTML, CSS, JavaScript
- No frameworks — fully standalone, opens in any browser

## Related Projects
- [Verkada Device Health Monitor](https://github.com/Sanjananuguri/verkada-device-monitor) — Python/REST API
- [Network Segmentation & ACL Lab](https://github.com/Sanjananuguri/network-segmentation-lab) — Cisco Packet Tracer

## About Me
I'm Sanjana Nuguri — a cybersecurity professional with an MS in Cybersecurity from the University of North Texas. My background is in SOC analysis and incident response. These projects sit at the intersection of that background and a deep interest in how physical security infrastructure is deployed and supported at scale.

SC-200 | ISC2 CC

[LinkedIn](https://linkedin.com/in/sanjananuguri) | [GitHub](https://github.com/Sanjananuguri)
