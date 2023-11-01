---
title: "Bad memory"
weight: 7
---
## Bad memory

> A user came to us and said they forgot their password. Can you recover it? The flag is the MD5 hash of the recovered password wrapped in the proper flag format.

* Download the file and extract it and you get `image.bin`

    ```shell
    shanna@ubuntu:~/volatility3$ python3 vol.py -f ../Downloads/image.bin windows.info
    Volatility 3 Framework 2.5.2
    Progress:  100.00		PDB scanning finished                                                                                              
    Variable	Value

    Kernel Base	0xf8047e200000
    DTB	0x1aa000
    Symbols	file:///home/shanna/volatility3/volatility3/symbols/windows/ntkrnlmp.pdb/81BC5C377C525081645F9958F209C527-1.json.xz
    Is64Bit	True
    IsPAE	False
    layer_name	0 WindowsIntel32e
    memory_layer	1 FileLayer
    KdVersionBlock	0xf8047ee0f2a8
    Major/Minor	15.19041
    MachineType	34404
    KeNumberProcessors	1
    SystemTime	2020-10-03 11:45:39
    NtSystemRoot	C:\Windows
    NtProductType	NtProductWinNt
    NtMajorVersion	10
    NtMinorVersion	0
    PE MajorOperatingSystemVersion	10
    PE MinorOperatingSystemVersion	0
    PE Machine	34404
    PE TimeDateStamp	Sun Aug 11 05:47:24 2069

    shanna@ubuntu:~/volatility3$ python3 vol.py -f ../Downloads/image.bin windows.hashdump.Hashdump
    Volatility 3 Framework 2.5.2
    Progress:  100.00		PDB scanning finished                        
    User	rid	lmhash	nthash

    Administrator	500	aad3b435b51404eeaad3b435b51404ee	31d6cfe0d16ae931b73c59d7e0c089c0
    Guest	501	aad3b435b51404eeaad3b435b51404ee	31d6cfe0d16ae931b73c59d7e0c089c0
    DefaultAccount	503	aad3b435b51404eeaad3b435b51404ee	31d6cfe0d16ae931b73c59d7e0c089c0
    WDAGUtilityAccount	504	aad3b435b51404eeaad3b435b51404ee	4cff1380be22a7b2e12d22ac19e2cdc0
    congo	1001	aad3b435b51404eeaad3b435b51404ee	ab395607d3779239b83eed9906b4fb92
    ```

So now I needed to switch to my Windows host to run HashCat on the GPU.

    ```
    .\hashcat.exe -m 1000 ab395607d3779239b83eed9906b4fb92 .\rockyou.txt

    Dictionary cache built:
    * Filename..: .\rockyou.txt
    * Passwords.: 14344391
    * Bytes.....: 139921497
    * Keyspace..: 14344384
    * Runtime...: 1 sec

    ab395607d3779239b83eed9906b4fb92:goldfish#

    Session..........: hashcat
    Status...........: Cracked
    Hash.Mode........: 1000 (NTLM)
    Hash.Target......: ab395607d3779239b83eed9906b4fb92
    Time.Started.....: Mon Oct 30 18:50:01 2023 (0 secs)
    Time.Estimated...: Mon Oct 30 18:50:01 2023 (0 secs)
    Kernel.Feature...: Pure Kernel
    Guess.Base.......: File (.\rockyou.txt)
    Guess.Queue......: 1/1 (100.00%)
    Speed.#1.........: 26220.5 kH/s (3.06ms) @ Accel:2048 Loops:1 Thr:32 Vec:1
    Recovered........: 1/1 (100.00%) Digests (total), 1/1 (100.00%) Digests (new)
    Progress.........: 9175040/14344384 (63.96%)
    Rejected.........: 0/9175040 (0.00%)
    Restore.Point....: 7340032/14344384 (51.17%)
    Restore.Sub.#1...: Salt:0 Amplifier:0-1 Iteration:0-1
    Candidate.Engine.: Device Generator
    Candidates.#1....: ina&alessandro -> chautla
    Hardware.Mon.#1..: Temp: 55c Fan:  0% Util: 24% Core:1807MHz Mem:7300MHz Bus:8
    ```

Back to Linux to create the MD5 of the recovered password to submit the flag.
    ```shell
    echo -n 'goldfish#' | md5sum
    ```