# Postmortem — DDoS Incident (ICMP flood)

**Author:** Jesús Sebastián Galván Saavedra  
**Date:** 2025-08-29

## Context
A multimedia company that provides web design, graphic design, and social media marketing services experienced a distributed denial of service (DDoS) incident consisting of a flood of incoming ICMP packets.

## Summary
A flood of ICMP packets caused internal network services to become unresponsive. The incident rendered normal internal traffic unable to reach network resources. The incident impacted the internal network for two hours (per the scenario). The incident response team blocked incoming ICMP traffic, took non-critical services offline, and restored critical services.

## Identify
The security team investigated the event and determined the attack vector was an ICMP ping flood routed through a firewall that was not properly configured. This configuration allowed the malicious actor to overwhelm the company's internal network.

## Actions Taken (during the incident)
- Blocked incoming ICMP packets at the network boundary.  
- Temporarily stopped non-critical network services to preserve resources.  
- Restored critical network services once the network became stable.

## Measures Implemented (post-incident)
- Added a firewall rule to limit the rate of incoming ICMP packets.  
- Enabled source IP origin verification at the firewall to detect possible spoofed ICMP packets.  
- Deployed network monitoring software to detect abnormal traffic patterns.  
- Implemented an IDS/IPS to filter suspicious ICMP traffic characteristics.

## Impact
- Primary impact: temporary unavailability of internal network services (two hours per the scenario).  
- Affected operations: internal systems dependent on network connectivity could not access resources.

## Root cause (as described in scenario)
A misconfigured (or not properly configured) firewall allowed the flow of a large volume of ICMP pings, enabling the denial of service.

## Lessons learned
- Permissive firewall configuration can be a critical exploit vector for DDoS attacks.  
- Rapid application of mitigation steps (block, isolate, restore) helps reduce downtime.  
- The organization should formalize incident response procedures and review perimeter device configurations.

## Status and follow-up
Measures described above were implemented as part of the response. Formal documentation and additional procedural details are recommended to be drafted after the exercise.
