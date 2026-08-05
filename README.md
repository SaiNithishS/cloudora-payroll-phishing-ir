# Cloudora Payroll Phishing Campaign — Incident Response Report

SOC/DFIR portfolio project by **Sai Nithish Sampath** — [GitHub](https://github.com/SaiNithishS) · [Portfolio](https://sainithishsampath.vercel.app)

## What this is

A full incident response investigation into a simulated payroll-themed phishing campaign, written up as a professional SOC report. I triaged a reported phishing email by hand (headers, authentication, infrastructure), then used Exchange Online message-trace and Microsoft Entra ID sign-in logs in KQL to scope the campaign and confirm who was compromised.

Cloudora is a fictional company used for training. The emails and logs came from a training data set — the investigation, analysis, and report are my own work.

## The incident

An attacker sent a "confirm your payroll details" phishing email to 40 staff, impersonating Cloudora HR, using two variants: one that spoofed the real Cloudora address and failed every authentication check, and one sent from the attacker's own lookalike domain that legitimately *passed* SPF/DKIM/DMARC — for the fake domain, not for Cloudora. Six people clicked, two entered their passwords, and the attacker used both stolen passwords the same day from an address in Amsterdam.

- **40** staff targeted, **2** accounts compromised
- One phishing variant passed every authentication check — proof that "passed" doesn't mean "safe"
- A reported marketing newsletter was investigated and correctly cleared as legitimate
- Both accounts contained and attacker infrastructure blocked the same day

## What's in this repo

| Folder | Contents |
|---|---|
| `report/` | The full report — **read the PDF first** |
| `evidence/` | The 6 raw phishing/legitimate emails, message-trace and sign-in log exports, and an IOC list |
| `detections/` | The KQL queries used in the investigation, the header-analysis checklist, and 1 new detection rule |

## Skills demonstrated

Email header and authentication analysis (SPF/DKIM/DMARC) · phishing infrastructure analysis · KQL log analysis · Exchange Online message trace · MITRE ATT&CK mapping · detection engineering · incident response reporting · user-facing security communications

## Credit

Scenario and source data: "Cloudora Payroll Phishing Campaign" training pack (MyFirstCyberJob). Investigation and report: my own work.
