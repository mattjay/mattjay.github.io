---
layout: post
title: "Collaborative Incident Response Best Practices: Don't Rely on Superheroes"
date: 2023-04-04
author: Matt Johansen
tags: [incident-response, cybersecurity, SOAR, best-practices, resilience]
image: /images/superhero-culture.jpg
---

# **Collaborative Incident Response Best Practices: Don't Rely on Superheroes**

It's more important than ever for organizations to have an effective incident response team. However, many are relying on a few individuals with specialized knowledge who act as their rock stars when shit hits the fan. This approach is not sustainable nor effective. In this post, I’ll discuss the importance of collaborative incident response best practices and how to avoid a superhero-driven culture.

This post came to life from a twitter thread I wrote this week:

![Twitter Incident Response Thread](/images/twitter-incident-response.png)

## **Incident Response Team**

Collaborative incident response is a key best practice for effective incident management. What the hell does this mean? There needs to be a focus on creating a **team** of individuals who work together to handle critical incidents, rather than relying on a single person or a small group of your most senior talent. A well-organized incident response team can triage, contain, eradicate, and recover from incidents quickly and effectively. All the while focusing on documenting their efforts along the way.

## **Incident Response Playbooks**

To achieve this dream of collaborative incident response, it's critical to have a suite of well documented playbooks for different incident types. These playbooks should include detailed steps on how to declare an incident, what lines of communication need to be opened, how to quickly identify and contain what is going on, and finally how to eradicate the issue and recover. Without these playbooks, you’ll be stuck relying on historical knowledge from the team members who’ve been there done that. I’ve seen it too many times where the “new” team members have been there over a year and still need to call a single person because they never had to learn what that superhero handled for them. 

## **SOAR Automation**

Another tactic that is becoming a more crucial part of the incident response utility belt is Security Orchestration, Automation, and Response (SOAR) tools. These can help automate many of the repeatable actions that are required during an incident, freeing up the team to focus on more complex tasks. Some powerful examples I’ve seen are around killing sessions across multiple platforms for a compromised account. But I’ve also seen some gnarly If This Than That examples that can get very complicated and automate huge swaths of incident response away with the push of a button by any team member, not just an expert. SOAR automation can significantly reduce the burden on the incident response team and increase the efficiency of incident response processes.

## **Incident Response System of Record**

A pitfall I see plague many teams is that it very difficult to know what you’re running in your environment and where. If an incident is declared due to attack data or intel on a new vulnerability, you first need to identify if your org is running the thing that is vulnerable to this attack. Many times this requires deep digging, ad-hoc scans, specialized queries in bespoke systems, etc. All of these tasks are generally run by people who are intimately familiar with spelunking them and response efforts are held up waiting on this discovery exercise. What takes many teams hours, should take them minutes and anyone on the team should be able to look the info up without need for specialized superheroes.

This is actually super difficult but can be achieved through a few strategies getting enough attention and funding. When is the last CMDB you’ve seen done well, and kept real time? Once you crack that nut, another key is to ensure that all members of the team have access to this system and know how to use it effectively. In order for a system of record to be useful for incident response it needs to be easily searchable and up to date.

## **Conclusion**

Collaborative incident response is hard because it takes planning. A lot of orgs aren’t going to learn this lesson until the alternative has become too painful to continue. But, this approach also requires a well-organized incident response team, thoroughly documented playbooks, robust automation where possible, and an incident response worthy system of record. There is a roadmap here that can help organizations ensure that they are better equipped to handle incidents before they arise and not rely any single individual to fire fight. Don't be a superhero-driven culture; instead, focus on collaboration, documentation, and teamwork to build a resilient and effective incident response capability.