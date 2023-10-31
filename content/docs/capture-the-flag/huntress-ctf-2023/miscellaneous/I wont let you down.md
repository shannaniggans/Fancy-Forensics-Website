---
title: "I won't let you down"
weight: 50
---
## I won't let you down

> OK Go take a look at this IP:
> Connect here: http://155.138.162.158
> USING ANY OTHER TOOL OTHER THAN NMAP WILL DISQUALIFY YOU. DON'T USE BURPSUITE, DON'T USE DIRBUSTER. JUST PLAIN NMAP, NO FLAGS!

Obvious first thing is to go to the website and see what's there (and get rick rolled). 

Then it's practically impossible not to want to nmap scan the webserver:

```shell
shanna@ubuntu:~/rita$ nmap -A -T4 -F 155.138.162.158
Starting Nmap 7.80 ( https://nmap.org ) at 2023-10-25 22:56 PDT
Nmap scan report for 155.138.162.158.vultrusercontent.com (155.138.162.158)
Host is up (0.22s latency).
Not shown: 97 filtered ports
PORT     STATE SERVICE         VERSION
22/tcp   open  ssh             OpenSSH 9.0p1 Ubuntu 1ubuntu8.5 (Ubuntu Linux; protocol 2.0)
80/tcp   open  tcpwrapped
|_http-title: Hello World!
8888/tcp open  sun-answerbook?
| fingerprint-strings: 
|   GetRequest: 
|     We're no strangers to love
|     know the rules and so do I (do I)
|     full commitment's what I'm thinking of
|     wouldn't get this from any other guy
|     just wanna tell you how I'm feeling
|     Gotta make you understand
|     Never gonna give you up
|     Never gonna let you down
|     Never gonna run around and desert you
|     Never gonna make you cry
|     Never gonna say goodbye
|     Never gonna tell a lie and hurt you
|     We've known each other for so long
|     Your heart's been aching, but you're too shy to say it (say it)
|     Inside, we both know what's been going on (going on)
|     know the game and we're gonna play it
|     feeling
|     Don't tell me you're too blind to see
|     Never gonna give you up
|     Never gonna let you down
|     Never gonna run around and desert you
|     Never gonna make you cry
|     Never gonna say goodbye
|     Never gonna tell a lie and hurt you
|     Never gonna give you up
|     Never gonna let you down
|     Never gonna run around and dese
|   NULL: 
|     We're no strangers to love
|     know the rules and so do I (do I)
|     full commitment's what I'm thinking of
|     wouldn't get this from any other guy
|     just wanna tell you how I'm feeling
|     Gotta make you understand
|     Never gonna give you up
|     Never gonna let you down
|     Never gonna run around and desert you
|     Never gonna make you cry
|     Never gonna say goodbye
|     Never gonna tell a lie and hurt you
|     We've known each other for so long
|     Your heart's been aching, but you're too shy to say it (say it)
|     Inside, we both know what's been going on (going on)
|     know the game and we're gonna play it
|     feeling
|     Don't tell me you're too blind to see
|     Never gonna give you up
|_    Never gonna let you down
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port8888-TCP:V=7.80%I=7%D=10/25%Time=6539FFB0%P=x86_64-pc-linux-gnu%r(N
SF:ULL,2B9,"We're\x20no\x20strangers\x20to\x20love\nYou\x20know\x20the\x20
SF:rules\x20and\x20so\x20do\x20I\x20\(do\x20I\)\nA\x20full\x20commitment's
SF:\x20what\x20I'm\x20thinking\x20of\nYou\x20wouldn't\x20get\x20this\x20fr
SF:om\x20any\x20other\x20guy\nI\x20just\x20wanna\x20tell\x20you\x20how\x20
SF:I'm\x20feeling\nGotta\x20make\x20you\x20understand\nNever\x20gonna\x20g
SF:ive\x20you\x20up\nNever\x20gonna\x20let\x20you\x20down\nNever\x20gonna\
SF:x20run\x20around\x20and\x20desert\x20you\nNever\x20gonna\x20make\x20you
SF:\x20cry\nNever\x20gonna\x20say\x20goodbye\nNever\x20gonna\x20tell\x20a\
SF:x20lie\x20and\x20hurt\x20you\nWe've\x20known\x20each\x20other\x20for\x2
SF:0so\x20long\nYour\x20heart's\x20been\x20aching,\x20but\x20you're\x20too
SF:\x20shy\x20to\x20say\x20it\x20\(say\x20it\)\nInside,\x20we\x20both\x20k
SF:now\x20what's\x20been\x20going\x20on\x20\(going\x20on\)\nWe\x20know\x20
SF:the\x20game\x20and\x20we're\x20gonna\x20play\x20it\nAnd\x20if\x20you\x2
SF:0ask\x20me\x20how\x20I'm\x20feeling\nDon't\x20tell\x20me\x20you're\x20t
SF:oo\x20blind\x20to\x20see\nNever\x20gonna\x20give\x20you\x20up\nNever\x2
SF:0gonna\x20let\x20you\x20down\n")%r(GetRequest,4E4,"We're\x20no\x20stran
SF:gers\x20to\x20love\nYou\x20know\x20the\x20rules\x20and\x20so\x20do\x20I
SF:\x20\(do\x20I\)\nA\x20full\x20commitment's\x20what\x20I'm\x20thinking\x
SF:20of\nYou\x20wouldn't\x20get\x20this\x20from\x20any\x20other\x20guy\nI\
SF:x20just\x20wanna\x20tell\x20you\x20how\x20I'm\x20feeling\nGotta\x20make
SF:\x20you\x20understand\nNever\x20gonna\x20give\x20you\x20up\nNever\x20go
SF:nna\x20let\x20you\x20down\nNever\x20gonna\x20run\x20around\x20and\x20de
SF:sert\x20you\nNever\x20gonna\x20make\x20you\x20cry\nNever\x20gonna\x20sa
SF:y\x20goodbye\nNever\x20gonna\x20tell\x20a\x20lie\x20and\x20hurt\x20you\
SF:nWe've\x20known\x20each\x20other\x20for\x20so\x20long\nYour\x20heart's\
SF:x20been\x20aching,\x20but\x20you're\x20too\x20shy\x20to\x20say\x20it\x2
SF:0\(say\x20it\)\nInside,\x20we\x20both\x20know\x20what's\x20been\x20goin
SF:g\x20on\x20\(going\x20on\)\nWe\x20know\x20the\x20game\x20and\x20we're\x
SF:20gonna\x20play\x20it\nAnd\x20if\x20you\x20ask\x20me\x20how\x20I'm\x20f
SF:eeling\nDon't\x20tell\x20me\x20you're\x20too\x20blind\x20to\x20see\nNev
SF:er\x20gonna\x20give\x20you\x20up\nNever\x20gonna\x20let\x20you\x20down\
SF:nNever\x20gonna\x20run\x20around\x20and\x20desert\x20you\nNever\x20gonn
SF:a\x20make\x20you\x20cry\nNever\x20gonna\x20say\x20goodbye\nNever\x20gon
SF:na\x20tell\x20a\x20lie\x20and\x20hurt\x20you\nNever\x20gonna\x20give\x2
SF:0you\x20up\nNever\x20gonna\x20let\x20you\x20down\nNever\x20gonna\x20run
SF:\x20around\x20and\x20dese");
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 215.92 seconds
```

Alright so, no flag in that, but looks like 8888 is worth investigating more and seeing what happens:

```shell
shanna@ubuntu:~/rita$ telnet 155.138.162.158 8888
Trying 155.138.162.158...
Connected to 155.138.162.158.
Escape character is '^]'.
We're no strangers to love
You know the rules and so do I (do I)
A full commitment's what I'm thinking of
You wouldn't get this from any other guy
I just wanna tell you how I'm feeling
Gotta make you understand
Never gonna give you up
Never gonna let you down
Never gonna run around and desert you
Never gonna make you cry
Never gonna say goodbye
Never gonna tell a lie and hurt you
We've known each other for so long
Your heart's been aching, but you're too shy to say it (say it)
Inside, we both know what's been going on (going on)
We know the game and we're gonna play it
And if you ask me how I'm feeling
Don't tell me you're too blind to see
Never gonna give you up
Never gonna let you down
Never gonna run around and desert you
Never gonna make you cry
Never gonna say goodbye
Never gonna tell a lie and hurt you
Never gonna give you up
Never gonna let you down
Never gonna run around and desert you
Never gonna make you cry
Never gonna say goodbye
Never gonna tell a lie and hurt you
We've known each other for so long
Your heart's been aching, but you're too shy to say it (to say it)
Inside, we both know what's been going on (going on)
We know the game and we're gonna play it
I just wanna tell you how I'm feeling
Gotta make you understand
Never gonna give you up
Never gonna let you down
Never gonna run around and desert you
Never gonna make you cry
Never gonna say goodbye
Never gonna tell a lie and hurt you
Never gonna give you up
Never gonna let you down
Never gonna run around and desert you
Never gonna make you cry
Never gonna say goodbye
Never gonna tell a lie and hurt you
Never gonna give you up
Never gonna let you down
Never gonna run around and desert you
Never gonna make you cry
Never gonna say goodbye
Never gonna tell a lie and hurt you
flag{93671c2c38ee872508770361ace37b02}

Connection closed by foreign host.
```
{{< expand "Flag" ">" >}}
flag{93671c2c38ee872508770361ace37b02}
{{< /expand >}}

