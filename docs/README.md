# SHIMA CYBER LAB — Documentation & Publishing Playbook

This repository is a record of real, authorised hands-on learning. Every project should make the following loop visible:

> **Learn → Build → Break → Secure → Document → Improve**

"Break" means testing only services, machines, accounts, and networks explicitly created or approved for this lab. Never include credentials, private IP details that identify a real network, personal data, exploit code intended for unauthorised use, or screenshots containing sensitive information.

## What a Finished Lab Proves

A completed project should demonstrate that you can:

1. Define an objective and scope.
2. Design and build a reproducible environment.
3. Test normal and security-relevant behaviour safely.
4. Identify a risk or improvement opportunity.
5. Apply and verify a control or remediation.
6. Explain the result to both technical and non-technical audiences.

## Recommended Project Layout

Create a project folder only when the work has actually begun:

```text
projects/
  01-network-fundamentals/
    README.md
    assets/
      topology.png
      packet-capture-summary.png
```

Number folders to keep the portfolio readable in learning order.

## Lab Report Template

Use the following structure in each project README.

```markdown
# Project title

## Status
Planned | In progress | Complete

## Objective
What practical capability is being developed?

## Scope and safe-use boundary
Which lab-owned systems, accounts, and networks are in scope?

## Environment and architecture
Virtualisation platform, operating systems, network segments, and a labelled topology diagram.

## Implementation
The meaningful configuration choices, commands, or steps. Explain why they were chosen.

## Validation
What was tested? Include expected and actual results. Screenshots or sanitised command output should support the claim.

## Security considerations
Attack surface, least privilege, network segmentation, logging, patching, backup, and monitoring considerations relevant to this project.

## Problem solving
Problem → diagnosis → solution → verification.

## Lessons learned
Three to five concrete takeaways.

## Next improvement
The one most valuable follow-up.
```

## Evidence Checklist

Before marking a project complete, verify that it includes:

- A short objective written in your own words.
- A topology or architecture diagram.
- Sanitised configuration evidence and tests.
- One or more security decisions explained with their trade-off.
- At least one lesson from a problem, failure, or correction.
- No secrets, keys, tokens, public IPs, or personal data.

## LinkedIn Post Workflow

Publish only after the project README is accurate. The post should tell a concise story; GitHub holds the technical detail.

```text
Hook: What practical problem did I solve or investigate?

Context: What was the lab environment and learning goal?

Action: What did I build, test, or secure? Keep it factual and high level.

Result: What did the validation show?

Lesson: What did I understand better after doing the work?

Portfolio link: Link to the GitHub project README.

#Cybersecurity #Homelab #Networking #BlueTeam
```

Never present a planned, copied, or tutorial-only result as completed work. Use your own screenshots, diagrams, and lessons.

## First Project: Network Fundamentals Lab

**Current status:** Planned — environment inventory required.

**Target outcome:** An isolated virtual network with a Linux VM, documented addressing and services, validated connectivity, and a small Wireshark capture that explains normal DNS and TCP traffic.

This foundation will directly support the later Linux, Windows Server, Active Directory, SOC/SIEM, vulnerability-management, and incident-response projects.
