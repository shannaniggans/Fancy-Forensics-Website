---
title: "Dumpster fire"
weight: 50
---
## Dumpster fire

> We found all this data in the dumpster! Can you find anything interesting in here, like any cool passwords or anything? Check it out quick before the foxes get to it!

Many clues here to lead us to this being a Firefox challenge and we are looking for passwords. Reviewing the directory structure, we can see `logins.json`. Firefox store passwords, encrypted, in this JSON text file, let's take a look:

```shell
shanna@DFIR-work:/mnt/c/Users/shanna/Downloads/dumpster_fire/home/challenge/.mozilla/firefox/bc1m1zlr.default-release$ cat logins.json
{"nextId":2,"logins":[{"id":1,"hostname":"http://localhost:31337","httpRealm":null,"formSubmitURL":"http://localhost:31337","usernameField":"username","passwordField":"password","encryptedUsername":"MDIEEPgAAAAAAAAAAAAAAAAAAAEwFAYIKoZIhvcNAwcECPs50spbp6eyBAi0aCUHIntLPA==","encryptedPassword":"MFIEEPgAAAAAAAAAAAAAAAAAAAEwFAYIKoZIhvcNAwcECEcjS+e6bXjFBCgCQ0p/1wCqPUmdgXdZWlohMXan4C3jD0bQgzsweyVEpAjJa+P9eOU4","guid":"{9a363712-620c-499a-bb7d-999b8b2515dc}","encType":1,"timeCreated":1604703907434,"timeLastUsed":1604703907434,"timePasswordChanged":1604703907434,"timesUsed":1}],"potentiallyVulnerablePasswords":[],"dismissedBreachAlertsByLoginGUID":{},"version":3}
```

From this the 3 interesting fields look to be:
```shell
"encryptedUsername":"MDIEEPgAAAAAAAAAAAAAAAAAAAEwFAYIKoZIhvcNAwcECPs50spbp6eyBAi0aCUHIntLPA=="
"encryptedPassword":"MFIEEPgAAAAAAAAAAAAAAAAAAAEwFAYIKoZIhvcNAwcECEcjS+e6bXjFBCgCQ0p/1wCqPUmdgXdZWlohMXan4C3jD0bQgzsweyVEpAjJa+P9eOU4"
"encType":1
```
There is a tool that can pull this information from Firefox profiles, so I grabbed it:
```shell
git clone https://github.com/unode/firefox_decrypt.git
```

I also needed to install libnss3

```shell
sudo apt install libnss3
cd firefox_decrypt
python3 firefox_decrypt.py ../dumpster_fire/home/challenge/.mozilla/firefox/bc1m1zlr.default-release/
```

Because i wanted to, i also used a second tool which shows the decrytpion process: 

```shell
git clone https://github.com/lclevy/firepwd.git
cd firepwd/
pip3 install -r requirements.txt
python3 firepwd.py -d ../dumpster_fire/home/challenge/.mozilla/firefox/bc1m1zlr.default-release/
```

Both tools worked to get me the flag.

{{< expand "Flag" ">" >}}
flag{35446041dc161cf5c9c325a3d28af3e3}
{{< /expand >}}

# Resources:
* Firefox decrypt - https://github.com/unode/firefox_decrypt
* A little bit about the logins.json and key4.db - https://wiki.mozilla.org/NSS_Shared_DB
* Firepwd - https://github.com/lclevy/firepwd
* This blog post shows how to take the steps manually to decrypt - https://apr4h.github.io/2019-12-20-Harvesting-Browser-Credentials/

# Output from `firepwd` for interest:

```shell
globalSalt: b'237366f42ee4865cb4fa8c6dedd52aad8a06d347'
 SEQUENCE {
   SEQUENCE {
     OBJECTIDENTIFIER 1.2.840.113549.1.5.13 pkcs5 pbes2
     SEQUENCE {
       SEQUENCE {
         OBJECTIDENTIFIER 1.2.840.113549.1.5.12 pkcs5 PBKDF2
         SEQUENCE {
           OCTETSTRING b'41e46e3be88af7938209072b83dbae9d7cd72e9879a4b24f2af9106ecad57e42'
           INTEGER b'01'
           INTEGER b'20'
           SEQUENCE {
             OBJECTIDENTIFIER 1.2.840.113549.2.9 hmacWithSHA256
           }
         }
       }
       SEQUENCE {
         OBJECTIDENTIFIER 2.16.840.1.101.3.4.1.42 aes256-CBC
         OCTETSTRING b'c448c9b84e50616687908f1cd025'
       }
     }
   }
   OCTETSTRING b'03d325071c986d531e958b3739e776d1'
 }
clearText b'70617373776f72642d636865636b0202'
password check? True
 SEQUENCE {
   SEQUENCE {
     OBJECTIDENTIFIER 1.2.840.113549.1.5.13 pkcs5 pbes2
     SEQUENCE {
       SEQUENCE {
         OBJECTIDENTIFIER 1.2.840.113549.1.5.12 pkcs5 PBKDF2
         SEQUENCE {
           OCTETSTRING b'30879ad30aac17c31dbba183c911e5ff628574270a207892f5ae1d118a38d0b6'
           INTEGER b'01'
           INTEGER b'20'
           SEQUENCE {
             OBJECTIDENTIFIER 1.2.840.113549.2.9 hmacWithSHA256
           }
         }
       }
       SEQUENCE {
         OBJECTIDENTIFIER 2.16.840.1.101.3.4.1.42 aes256-CBC
         OCTETSTRING b'63ac9bb8ac454c439885f95743a9'
       }
     }
   }
   OCTETSTRING b'e1f24c1b25c14fee5c008d58bc77d4ca7f8c720f8b2069352fcb153d1da1f9ee'
 }
clearText b'6d515b15e949fe85511680e634a25eab8f19ceba3254a4e60808080808080808'
decrypting login/password pairs
http://localhost:31337:b'flag',b'flag{35446041dc161cf5c9c325a3d28af3e3}'
```