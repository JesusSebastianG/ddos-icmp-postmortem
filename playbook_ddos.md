# Playbook — Responding to a DDoS (ICMP flood) — Scenario-based

**Author:** Jesús Sebastián Galván Saavedra  
**Date:** 2025-08-29

## Purpose
Provide concise steps to respond to an ICMP flood affecting internal network availability, based on the provided scenario.

## Activation
Trigger: detection of a sudden flood of ICMP traffic that causes network services to be unresponsive.

## Immediate actions (initial response)
1. Block incoming ICMP traffic at the network edge to mitigate the active vector.  
2. Stop non-critical network services temporarily to prioritize core/critical services.  
3. Restore critical services once network stability improves.

## Investigation steps (during/after mitigation)
1. Investigate traffic source and characteristics using available tools and logs.  
2. Confirm the attack traversed the perimeter firewall and that firewall configuration permitted the traffic (as per scenario).

## Post-incident measures
- Implement a firewall rate-limiting rule for ICMP traffic.  
- Enable verification of source IP addresses in firewall policies to detect spoofing.  
- Deploy or tune network monitoring to detect abnormal ICMP patterns.  
- Configure IDS/IPS rules to identify and mitigate suspicious ICMP floods.

## Closure
After restoring services and applying the measures above, document the incident and update internal response procedures. Note: this playbook is derived only from the exercise scenario; it does not include device-specific commands or timestamps.
