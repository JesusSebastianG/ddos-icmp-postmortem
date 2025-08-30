# Scenario (exercise)

You are a cybersecurity analyst working for a multimedia company that provides web design, graphic design, and social media marketing solutions to small businesses. Your organization recently suffered a DDoS attack that impacted the internal network for two hours before it was resolved.

During the incident, the organization's network services suddenly stopped responding due to a flood of incoming ICMP packets. Normal internal network traffic could not access any network resources. The incident response team blocked incoming ICMP packets, took all non-critical network services offline, and restored critical network services.

An investigation by the security team revealed that a malicious actor sent a flood of ICMP pings to the company's network through a misconfigured firewall. This vulnerability allowed the attacker to overwhelm the company's network via a distributed denial of service (DDoS) attack.

To address the issue, the network security team implemented:
- A new firewall rule to rate-limit incoming ICMP packets.  
- Source IP verification on the firewall to check for spoofed IP addresses in incoming ICMP packets.  
- Network monitoring software to detect abnormal traffic patterns.  
- An IDS/IPS system to filter suspicious ICMP traffic.
