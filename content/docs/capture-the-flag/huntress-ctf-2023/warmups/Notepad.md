---
title: "Notepad"
weight: 50
---
## Notepad

> Just a sanity check... you do know how to use a computer, right?

I think a demonstration is enough for this one.

```shell
shanna@DFIR-work:/mnt/c/Users/shanna/Downloads$ file notepad
notepad: Unicode text, UTF-8 text
shanna@DFIR-work:/mnt/c/Users/shanna/Downloads$ mv notepad notepad.txt
shanna@DFIR-work:/mnt/c/Users/shanna/Downloads$ cat notepad.txt
+------------------------------------------------------+
| [✖] [□] [▬]  Notepad                               -   |
| ------------------------------------------------------ |
| File   Edit   Format   View   Help                     |
| ------------------------------------------------------ |
|                                                        |
|                                                        |
| New Text Document - Notepad                            |
|                                                        |
| flag{2dd41e3da37ef1238954d8e7f3217cd8}                 |
|                                                        |
|                                                        |
|                                                        |
|                                                        |
|                                                        |
|                                                        |
|                                                        |
|                                                        |
|                                                        |
|                                                        |
+------------------------------------------------------+
| Ln 1, Col 40                                         |
+------------------------------------------------------+
```
{{< details "Flag" ">" >}}
flag{03e8ba07d1584c17e69ac95c341a2569}
{{< /details >}}