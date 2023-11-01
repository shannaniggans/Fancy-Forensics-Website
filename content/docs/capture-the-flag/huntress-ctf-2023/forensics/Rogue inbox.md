---
title: "Rogue Inbox"
weight: 6
---
# Rogue inbox

> Challenge:  
> You've been asked to audit the Microsoft 365 activity for a recently onboarded as a customer of your MSP.
> Your new customer is afraid that Debra was compromised. We received logs exported from Purview... can you figure out what the threat actor did? It might take some clever log-fu!

I grabbed the csv file and opened in Timeline explorer (EZTools), I know we were interested in Debra and their inbox had funky things like new rules added. So I filtered the User Id column to contain `debra`.

Looking at the Audit Data column now I notice that all the New inbox rules contain the from value of `flag@ctf.com` so I filtered the Audit Data containing flag.

The next bit I found just by looking and seeing a distinct pattern ....

![Cheeky monkeys](../../images/rogue_inbox.png)

From there is transposed out the flag.

{{< expand "Flag" ">" >}}
flag{24c4230fa7d50eef392b2c850f74b0f6}
{{< /expand >}}