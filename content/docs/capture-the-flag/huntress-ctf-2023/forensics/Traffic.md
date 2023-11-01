---
title: "Traffic"
weight: 4
---
## Traffic

> We saw some communication to a sketchy site... here's an export of the network traffic. Can you track it down?
> Some tools like rita or zeek might help dig through all of this data!



```shell
git clone https://github.com/activecm/rita.git
cd rita
sudo ./install.sh
```

Downloaded and extracted the logs from traffic.7z and fed them into rita:

```shell
shanna@ubuntu:~/rita$ rita import ../Downloads/traffic/2021-09-08/ huntress_ctf_traffic

	[+] Importing [../Downloads/traffic/2021-09-08/]:
	[-] Verifying log files have not been previously parsed into the target dataset ... 
	[-] Processing batch 1 of 1
	[-] Parsing logs to: huntress_ctf_traffic ... 
	[-] Parsing ../Downloads/traffic/2021-09-08/http.00:00:00-01:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/ssl.00:00:00-01:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/conn.00:00:00-01:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/dns.00:00:00-01:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/conn.01:00:00-02:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/dns.01:00:00-02:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/http.01:00:00-02:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/ssl.01:00:00-02:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/ssl.02:00:00-02:01:50.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/conn.02:00:00-02:01:50.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/dns.02:00:00-02:01:50.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/http.02:15:51-03:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/conn.02:15:56-03:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/dns.02:15:46-03:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/http.03:00:00-03:53:19.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/ssl.02:15:47-03:00:00.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/ssl.03:00:00-03:53:19.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/conn.03:00:00-03:53:19.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/dns.03:00:00-03:53:19.log.gz -> huntress_ctf_traffic
	[-] Parsing ../Downloads/traffic/2021-09-08/conn.03:53:19-03:53:21.log.gz -> huntress_ctf_traffic
	[-] Finished parsing logs in 179ms
        [-] Host Analysis:            2658 / 2658  [==================] 100 %
        [-] Unique Connection Analysis: 2657 / 2657  [==================] 100 %
        [-] Unique Connection Aggregation: 1 / 1  [==================] 100 %
	[!] No Proxy Uconn data to analyze
        [-] SNI Connection Analysis:  1996 / 1996  [==================] 100 %
        [-] Exploded DNS Analysis:    1864 / 1864  [==================] 100 %
        [-] Hostname Analysis:        1864 / 1864  [==================] 100 %
        [-] Beacon Analysis:          2657 / 2657  [==================] 100 %
        [-] Beacon Aggregation:       1 / 1  [==================] 100 %
	[!] No Proxy Beacon data to analyze
        [-] SNI Beacon Analysis:      1996 / 1996  [==================] 100 %
        [-] SNI Beacon Aggregation:   1 / 1  [==================] 100 %
        [-] UserAgent Analysis:       6 / 6  [==================] 100 %
        [-] UserAgent Aggregation:    1 / 1  [==================] 100 %
        [-] Invalid Cert Analysis:    13 / 13  [==================] 100 %
	[-] Indexing log entries ... 
	[-] Updating metadatabase ... 
	[-] Done!
```

So I don't know what I'm doing with `rita` so I played around and looked at everything:

```
NAME:
   rita - Look for evil needles in big haystacks.

USAGE:
   rita [global options] command [command options] [arguments...]

VERSION:
   v4.8.0

COMMANDS:
     clean, clean-databases   Finds and removes broken databases. Prompts before deleting each database unless --force is provided.
     delete, delete-database  Delete imported database(s)
     import                   Import zeek logs into a target database
     html-report              Create an html report for an analyzed database
     show-beacons-proxy       Print hosts which show signs of C2 software (internal -> Proxy)
     show-beacons-sni         Print hosts which show signs of C2 software (SNI Analysis)
     show-beacons             Print hosts which show signs of C2 software
     show-bl-hostnames        Print blacklisted hostnames which received connections
     show-bl-source-ips       Print blacklisted IPs which initiated connections
     show-bl-dest-ips         Print blacklisted IPs which received connections
     list, show-databases     Print the databases currently stored
     show-exploded-dns        Print dns analysis. Exposes covert dns channels
     show-long-connections    Print long connections and relevant information
     show-open-connections    Print open connections and relevant information
     show-strobes             Print strobe information
     show-useragents          Print user agent information
     test-config              Check the configuration file for validity
     help, h                  Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --config CONFIG_FILE, -c CONFIG_FILE  Use a specific CONFIG_FILE when running this command
   --help, -h                            show help
   --version, -v                         print the version
```

`html-report` seems like a good place to start, run the following a browser window pops open.

```shell
shanna@ubuntu:~/rita$ rita html-report huntress_ctf_traffic
[-] Writing: /home/shanna/rita/huntress_ctf_traffic/huntress_ctf_traffic
[-] Wrote outputs, check /home/shanna/rita/huntress_ctf_traffic for files
```

Going through the tabs and remembering "sketchy site" as a clue from the description I see something ...

![show-beacons-sni](../../images/sketchy_site.png)

Go to that site and get the flag.

{{< expand "Flag" ">" >}}
flag{8626fe7dcd8d412a80d0b3f0e36afd4a}
{{< /expand >}}

# Resources
* Handy to watch the install process - https://youtu.be/mpCBOQSjbOA?si=ZgVXn1wZaWzjRZKz&t=985
* 