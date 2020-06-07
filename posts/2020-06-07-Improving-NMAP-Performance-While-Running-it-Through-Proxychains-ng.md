---
layout: default
---

## Improving Nmap's Performance while running it through Proxychains-ng

Traditionally, one would run nmpa through Proxychains-ng (or the original Proxychains) like so:

```
proxychains nmap -p 1-1000 -sT -Pn --open -n -T4 --min-parallelism 100 --min-rate 1 --oG proxychains_nmap_old --append-output <IP Address>
```

One can increase performance and quicken the scan by utilizing xargs to scan ports 1 through 1000 inclusively, like so:

```
seq 1 1000 | xargs -P 50 -I{} proxychains4 nmap -p {} -sT -Pn --open -n -T4 --min-parallelism 100 --min-rate 1 --oG proxychains_nmap --append-output <IP address>
```

And here's a similar method, using xargs to nmap scan a handful of ports on an entire range of hosts:

```
seq 1 254 | xargs -P 50 -I{} proxychains4 nmap -p 80,443,3389,445,22 -sT -Pn --open -n -T4 --min-parallelism 100 --min-rate 1 --oG proxychains_nmap --append-output 192.168.1.{}
```

[back](/)
