---
author: "Shanna Daly"
date: 2023-11-05
linktitle: Leveraging SRUM for Incident Response

tags: [
    "forensics",
    "SRUM",
]
categories: [
    "Forensics",
    "Windows Artefacts",
]

menu:
  main:
    parent: tutorials
next: /tutorials/github-pages-blog
prev: /tutorials/automated-deployments
title: Leveraging SRUM for Incident Response
weight: 10
---

## Introduction

In the world of Incident Response (IR), challenges are a given. In this blog post, I'll take you through a recent case that presented a unique set of hurdles and how the unexpected hero, the SRUM database, came to the rescue.

## The Challenge: (Un)usual Incident Response Scenario

Have you ever found yourself in the following predicaments?

1. You're called in for an urgent incident, only to discover it happened a month ago.
2. The local IT admin attempted IR before you, leaving a trail of questions.
3. There are no event logs to work with.

![War story problem solving](../images/SRUM_8.png)

While these situations may seem daunting, they can also provide interesting case studies. Such was the case for me when I had to piece together a timeline involving an attacker who gained access to a network via RDP, ran Mimikatz on multiple systems, and unleashed Dharma ransomware.

![War story attack sequence](../images/SRUM_7.png)

## The Role of SRUM: A Hidden Gem in Forensics

When dealing with incident response, investigators often rely on a set of familiar tools and techniques. However, sometimes a lesser-known tool can prove to be the key to unlocking critical insights. One such tool that has emerged as a hidden gem in the world of digital forensics is the Windows System Resource Usage Monitor, or SRUM.

SRUM is a relatively obscure component that many users may not be familiar with, often accessible through the "App History" tab in Task Manager. It serves as a valuable forensic resource by maintaining a comprehensive record of every application that executes on a system, including those that may have been intentionally deleted. This record even includes details like the user's Security Identifier (SID) responsible for executing each program.

The information collected by SRUM is stored within the SRUDB.DAT file, which follows the Windows Extensible Storage Engine (ESE) database format. Introduced in Windows 8, SRUM is a part of the "Diagnostic Policy Service." Unlike more well-known artifacts like event logs, SRUM can provide insights into applications and executions that might otherwise be missed.

In essence, SRUM acts as a silent observer, meticulously cataloguing the activities of every application, whether legitimate or malicious, across the system. This includes actions taken by attackers, making it a goldmine of information for digital forensics investigators.

![Windows SRUM Overview](../images/SRUM_1.png)


## What's Inside the SRUM Database

While I won't delve into the technical details here, the SRUM database records crucial information like application execution history, user accounts, and network connections.

![Information in the SRUM DB](../images/SRUM_2.png)

## Understanding SRUM: Key Insights

The SRUM database retains 60 days of data and doesn't overwrite files, unlike prefetch files. It's written once every hour and during system shutdown. To access the SRUDB.DAT file, you need raw access or can retrieve it from a Volume Shadow copy.

![Information in the SRUM DB](../images/SRUM_3.png)

## How SRUM Saved the Day

In the case I mentioned earlier, scoping was a significant challenge due to limited logs, deleted files, offline systems, sporadic antivirus deployment, and the absence of an EDR tool. To overcome these obstacles, I decided to extract all available SRUDB.DAT files across the network, parse them, and search for known indicators of compromise (IOCs). This allowed us to identify systems with Mimikatz usage and access by the attacker, along with related activities.

![You can collect the SRUM using live response tools](../images/SRUM_4.png)

## Introducing SRUM-DUMP

I'm no SRUM expert, but I found SRUM-DUMP to be a valuable tool for parsing SRUDB.DAT files. This tool accepts inputs like the SRUDB.DAT file from the system you want to analyse and an Excel file that specifies the fields to extract and their format.

![workflow](../images/SRUM_9.png)

![SRUM-DUMP can parse the SRUDB file and export](../images/SRUM_5.png)

## Use Cases for SRUM in Incident Response

SRUM isn't just for piecing together timelines in IR; it has several other use cases:

1. **Data Exfiltration:** Track the bytes sent and received per application process to detect suspicious data transfers.
2. **Attacker Activity:** Identify what applications an attacker ran, mapped to their user SID.
3. **Network Connections:** Know which networks the system connected to, including data upload and download metrics.
4. **Deleted Artefact Tracking:** Even if an executable has been deleted, SRUM can reveal the application path, user, and data usage.

![Use cases](../images/SRUM_6.png)

## Conclusion

In the challenging world of Incident Response, having versatile tools like SRUM at your disposal can make all the difference. The SRUM database offers valuable insights into attacker activity, data exfiltration, and more, enabling investigators to build comprehensive cases even in the face of limited data.

**References:**
1. Microsoft. (n.d.). SRUM: System Resource Usage Monitor. [link](https://docs.microsoft.com/en-us/windows/privacy/srum-system-resource-usage-monitor)
2. Russinovich, M. E., Solomon, D. A., & Ionescu, A. (2017). Windows Internals, Part 1. Microsoft Press.
