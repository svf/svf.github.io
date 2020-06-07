---
layout: default
---

## Getting Proxychains-ng to Run Well on MacOS

The default proxychains-ng binary in [Homebrew](https://brew.sh) didn't work for me. I found that by removing it and then telling [Homebrew] to compile from source, I was able to run arbitrary applications through a chain of proxies.

```sh
brew uninstall proxychains-ng

brew install proxychains-ng -s

Where the -s tells brew to compile from source.

Keep in mind that proxychains-ng doesn't seem to like the default curl installed on MacOS systems so you'll have to install [Homebrew's](https://brew.sh) version. I had brew compile from source. YMMV.

[back](/)
