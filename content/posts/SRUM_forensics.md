---
author: "Shanna Daly"
date: 2023-11-05
linktitle: SRUM Forensics
menu:
  main:
    parent: tutorials
next: /tutorials/github-pages-blog
prev: /tutorials/automated-deployments
title: Creating a New Theme
weight: 10
---

# Leveraging SRUM for Incident Response: A Valuable Forensic Tool

## Introduction

In the world of Incident Response (IR), challenges are a given. In this blog post, I'll take you through a recent case that presented a unique set of hurdles and how the unexpected hero, the SRUM database, came to the rescue.

## The Challenge: Unusual Incident Response Scenarios

Have you ever found yourself in the following predicaments?

1. You're called in for an urgent incident, only to discover it happened a month ago.
2. The local IT admin attempted IR before you, leaving a trail of questions.
3. There are no event logs to work with.

While these situations may seem daunting, they can also provide interesting case studies. Such was the case for me when I had to piece together a timeline involving an attacker who gained access to a network via RDP, ran Mimikatz on multiple systems, and unleashed Dharma ransomware.

## The Role of SRUM: A Hidden Gem in Forensics

Windows System Resource Usage Monitor (SRUM) might not be a household name, but it's a hidden gem in the world of digital forensics. It records every application executed on a system, even those that attackers or administrators deleted. This information, including the user's SID, is stored in the SRUDB.DAT file in the Windows ESE (Extensible Storage Engine) database format.

## What's Inside the SRUM Database

While I won't delve into the technical details here, the SRUM database records crucial information like application execution history, user accounts, and network connections.

## How SRUM Saved the Day

In the case I mentioned earlier, scoping was a significant challenge due to limited logs, deleted files, offline systems, sporadic antivirus deployment, and the absence of an EDR tool. To overcome these obstacles, I decided to extract all available SRUDB.DAT files across the network, parse them, and search for known indicators of compromise (IOCs). This allowed us to identify systems with Mimikatz usage and access by the attacker, along with related activities.

## Understanding SRUM: Key Insights

The SRUM database retains 60 days of data and doesn't overwrite files, unlike prefetch files. It's written once every hour and during system shutdown. To access the SRUDB.DAT file, you need raw access or can retrieve it from a Volume Shadow copy.

## Introducing SRUM-DUMP

I'm no SRUM expert, but I found SRUM-DUMP to be a valuable tool for parsing SRUDB.DAT files. This tool accepts inputs like the SRUDB.DAT file from the system you want to analyse and an Excel file that specifies the fields to extract and their format.

## Use Cases for SRUM in Incident Response

SRUM isn't just for piecing together timelines in IR; it has several other use cases:

1. **Data Exfiltration:** Track the bytes sent and received per application process to detect suspicious data transfers.
2. **Attacker Activity:** Identify what applications an attacker ran, mapped to their user SID.
3. **Network Connections:** Know which networks the system connected to, including data upload and download metrics.
4. **Deleted Artefact Tracking:** Even if an executable has been deleted, SRUM can reveal the application path, user, and data usage.

## Conclusion

In the challenging world of Incident Response, having versatile tools like SRUM at your disposal can make all the difference. The SRUM database offers valuable insights into attacker activity, data exfiltration, and more, enabling investigators to build comprehensive cases even in the face of limited data.
