---
layout: default
---

## Improving Nmap's Performance while running it through Proxychains-ng

Traditionally, one would run nmpa through Proxychains-ng (or the original Proxychains) like so:

```
proxychains nmap -p 1-1000 -sT -Pn --open -n -T4 --min-parallelism 100 --min-rate 1 --oG proxychains_nmap_old --append-output <IP Address>
```

[back](/)
