---
title: "A Discussion on Privacy, DNA, and What it Means to Get Hacked"
description: "Should we give our DNA to private companies? Is credential stuffing a data breach?"
image: /images/dna.png
tags: [privacy, current-events]
---

There have been a ton of reports this week that 23andMe suffered a credential stuffing attack. The result of this was the attackers collected profile data about as many users as possible using a feature known as DNA Relatives.

Once they collected all this data they decided to start to leak parts of the list focusing specifically on Ashkenazi Jews. After that they started selling all of the data collected in data packs.

During all of this reporting on an obviously emotionally charged topic - 23andMe announced they had not been hacked. This was just users who reused their passwords from other sites and THOSE sites had been hacked.

Now your caught up and I’d like to have a discussion about this entire event and focus on a few questions:

- What is the threat of giving your DNA information to these private companies like 23andMe or Ancestry?
- Where do you personally draw your risk line between privacy and life enrichment?
- Is credential stuffing a data breach?

Remember the time when 23andMe was just a quirky startup offering insights into our ancestral past? But as recent events have shown, even our very DNA isn't safe from unwanted attention. And why should it be? After all, in this age of oversharing, why should our genetic code be any different?

Now, before you label me a Luddite, let me clarify. I, too, was once enamored by the allure of tracing my roots, hoping to find some long-lost royal lineage or, at the very least, an interesting anecdote for dinner parties. But the recent events surrounding 23andMe have served as a stark reminder of the implications of handing over our most intimate data on a silver platter.

## **Understanding Credential Stuffing:**

For those blissfully unaware (and I envy you), let's dissect this beast known as 'credential stuffing'. Sounds like something you'd do to a Thanksgiving turkey. But alas, it's far less festive.

![Credential Stuffing](/images/credential-stuffing.png "Source: Cloudflare Blog - https://www.cloudflare.com/learning/bots/what-is-credential-stuffing/"){:style="display:block; margin-left:auto; margin-right:auto"}

Credential stuffing, in its simplest form, is the act of using stolen username-password pairs to gain unauthorized access to user accounts. Think of it as the lazy hacker's method. Why bother crafting intricate hacking strategies when you can exploit human predictability? After all, JohnDoe1234 is such a _unique_ password, right?

Historically, this method isn't groundbreaking. It's as old as the first password ever created. But its success rate? Alarmingly high. And why? Because passwords are hard, and not everyone wants to use a manager.

Now, I'm not here to merely point fingers (though it's tempting). I've been guilty of password complacency myself. There was a time when my password strategy was akin to using the same key for every lock in my house. Convenient? Absolutely. Safe? Far from it.

But here's the silver lining. We can change. We can learn. It's a journey, one that I've personally traveled, and the rewards? Well, they're more valuable than any ancestral insight a swab test might offer.

## **The Threat of Sharing DNA Information:**

DNA, the very essence of our being, the code that makes us... well, us. But in the hands of malicious actors? It becomes a weapon, a tool for exploitation. Now, I'm not just spinning a tale from a dystopian novel. This is the reality we are facing.

Consider the value of DNA data. To you, it might reveal that you're 10% Scandinavian or have a predisposition to enjoy the taste of cilantro. Fascinating, right? But to a malicious actor, it's a goldmine. Your genetic code can be a gateway to identity theft, targeted attacks, and a plethora of other nefarious activities. Imagine a world where your DNA could be used against you, where your very essence is weaponized. Sounds like science fiction, but history has shown us it's closer to fact.

Remember the case in 2018 when a major DNA testing company inadvertently exposed the data of nearly a million users? Or the time when insurance companies were accused of using genetic data to adjust premiums? These aren't just isolated incidents; they're cautionary tales of a system that's flawed, of a society that's recklessly shared its most intimate details.

## **Balancing Privacy and Life Enrichment:**

Now, don't get me wrong. I'm not here to rain on your DNA parade. The allure of these tests is undeniable. Who wouldn't want to uncover ancient family secrets, trace their lineage back to some exotic locale, or discover they have a genetic predisposition to be a morning person? (Though, if you ask me, no DNA test is needed to confirm my aversion to early mornings.)

![Morning Person](/images/morning_person.gif){:style="display:block; margin-left:auto; margin-right:auto"}

But here's the crux: every swab sent, every sample given, is a piece of you that's now out in the ether. And the trade-offs? They're monumental. Sure, you gain insights, perhaps even a newfound appreciation for your heritage. But at what cost?

I remember the first time I considered taking a DNA test. The kit sat on my table for weeks, an unassuming box that held the promise of discovery. But with every passing day, I found myself questioning the implications. Was my curiosity worth the potential invasion of my privacy? In the end, I chose the path of caution, but not without a heavy dose of introspection.

The decision to share one's DNA is deeply personal, and there's no one-size-fits-all answer. But as we tread this path, let's do so with our eyes wide open, understanding the full spectrum of possibilities, both enchanting and eerie.

In this dance between privacy and discovery, it's crucial to be both the dancer and the critic, to embrace the allure while questioning the implications. After all, in the grand tapestry of life, it's not just about where we come from, but how we choose to navigate the journey.

## **Credential Stuffing: Is it a Data Breach? Or Just Another Day in the Digital Wild West?**

Let's play a game of semantics, shall we? 'Data breach' – a term that sends shivers down the spines of CEOs. It conjures images of shadowy figures, clandestine operations, and headlines screaming of millions of compromised accounts. But then there's 'credential stuffing', which, let's be honest, sounds more like a tech jargon-filled Thanksgiving dish than a cyber threat. But is there really a difference?

At its core, a data breach is an incident where unauthorized individuals access data, typically with malicious intent. It's the digital equivalent of a break-in. Credential stuffing, on the other hand, is more like someone trying every key on their keychain until they find one that works. Lazy? Absolutely. Effective? Unfortunately, yes.

Now, if we're splitting hairs (and who doesn't love a good hair-splitting session?), credential stuffing isn't a 'breach' in the traditional sense. No walls are broken down; no systems are infiltrated. But the end result? It's eerily similar. Unauthorized access, compromised data, and a whole lot of finger-pointing.

And let's not even get started on the legal and ethical quagmire this presents. Is a company responsible if their users' reused passwords lead to unauthorized access?

Responsible is something I’ll leave to the lawyers - but helpless? Absolutely not.

Some things that any company can do to protect their users from credential stuffing attacks:

- **Forced MFA on unrecognized devices** - You’ve seen this. You login to your bank from your partner’s laptop instead of your own like usual and they prompt you with “We don’t recognize this machine, how would you like to receive your MFA code?”
- **CAPTCHA** - credential stuffing takes a whole lot of login attempts - easy to throw a CAPTCHA on your login if it seems someone is botting it.
- **Credential Stuff Yourself First** - The data breaches that the attackers are using are generally attainable by anybody. Download it yourself and run it against your own database. Any hits on password reuse and you can lock the account and force a password reset. Send a notice out that says “We noticed your username and password was part of a recent data breach, you’ll have to make a new password to access your account again. We recommend you do this on any other site you used this password on as well.”
- **Geolocation oddities** - did someone login from a new country they’ve never been to? Or did they attempt logins from two locations in a timeframe that would be impossible to travel that distance? Possible signs of a compromised account and can lock it down or force an MFA push.

There are other options but I think I made my point that the company is not helpless.

So while this might not stand as a data breach, I certainly say you got hacked if your users accounts were compromised.

## **Protecting Yourself:**

Our entire lives can be accessed with a few keystrokes, and our most intimate details are protected by... 'FluffyBunny87'. Truly, we are the architects of our own demise.

But fear not, for all is not lost. There are ways to fortify.

First and foremost, let's talk passwords. And I don't mean your pet's name followed by your birth year. I mean complex, unique, and utterly unguessable strings of characters. And before you lament the impossibility of remembering such a monstrosity, let me introduce you to the magic of password managers. These handy tools not only store your passwords but can generate and remember complex ones for you. It's like having a digital bodyguard for your data.

And while we're on the topic of security, let's discuss two-factor authentication (2FA). Think of it as a double lock for your digital doors. Even if someone guesses your password, they'll need a second form of verification to access your account. It's an added layer of security that can make all the difference.

![Taylor Swift MFA](/images/taylor_mfa.png){:style="display:block; margin-left:auto; margin-right:auto"}

## **The Response of Companies to Such Attacks:**

A delightful dance of PR spins, carefully crafted statements, and, on occasion, a dash of genuine accountability. Let's take a moment to dissect 23andMe's response to the recent kerfuffle. Their claim? They hadn't been hacked. Oh no, it was merely users reusing passwords from other compromised sites. A classic case of "It's not us; it's you." How... reassuring.

But let's not single out 23andMe. The annals of corporate history are littered with companies fumbling their responses to cyberattacks. Some bury their heads in the sand, hoping the storm will pass. Others go on the offensive, blaming everyone but themselves. And then there are the rare few that actually own up, take responsibility, and vow to do better.

The crux of the matter is this: companies, especially those entrusted with our most intimate data, have a responsibility – nay, a duty – to protect it. And when they fail? They owe it to their users to be transparent, accountable, and proactive in their response.

---

**It's not about living in fear, but about understanding the landscape, recognizing the pitfalls, and making informed decisions.**
