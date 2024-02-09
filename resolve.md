---
title: Resolving Handshake Domains
description: 
published: 1
date: 2024-02-09T05:50:52.713Z
tags: 
editor: markdown
dateCreated: 2024-02-09T05:50:52.713Z
---

# Resolving Handshake Domains

Visiting HNS websites in your browser securely requires two pieces of software:

1. HNS Resolver: Looks up domain names and gets IP addresses for web servers to fetch website data. Also fetches DNSSEC data which are DNS records with cryptographic keys and signatures to ensure authenticity.
1. DANE Verifier: Relies on a secure HNS resolver to verify SSL certificates from web servers and establish secure HTTPS connections.

There are many methods to visit HNS websites on your computer and there are trade-offs for each method.

## Methods

### hsd full node + letsdane proxy

[hsd](https://github.com/handshake-org/hsd)
[letsdane](https://github.com/buffrr/letsdane)

>  Security: HIGH
>  Privacy: HIGH
>  Decentralization: HIGH
>  Convenience: MEDIUM
>  Complexity: HIGH
{.is-info}

hsd is the most bullet-proof piece of Handshake software available. It verifies every single transaction and every single block against every single protocol rule we have. It has the best security practices and the best privacy. It does complete recursive domain name resolution from the HNS root zone all the way down. letsdane is the best tool available for verifying DANE and establishing HTTPS connections to websites hosted on Handshake domains. It checks all DNSSEC records served by hsd and checks the certificate offered by the web server. Every cryptographic signature is verified. If a user installs both of these on the computer they are browsing from, there is very little surface for attack: your browsing history remains private and all data transmitted and received is private and secure.


### hsd SPV node / hnsd light client + letsdane proxy (Fingertip)
[Fingertip](https://impervious.com/fingertip)
[hsd](https://github.com/handshake-org/hsd)
[hnsd](https://github.com/handshake-org/hnsd)
[letsdane](https://github.com/buffrr/letsdane)

>  Security: HIGH
>  Privacy: MEDIUM
>  Decentralization: MEDIUM
>  Convenience: MEDIUM
>  Complexity: HIGH
{.is-info}

Users install and launch the software. The light client syncs the blockchain (may take one minute or more). User must add a locally-generated certificate to their browser's trusted certificate store. User then must configure their browser to proxy all HTTP requests through the proxy so that DANE can be verified. Can be configured for a single browser like Firefox or the entire operating system can be run through the software. Light clients rely on hsd full nodes on the Handshake p2p network for block headers. This means that only SOME of the HNS consensus protocol is verified, like proof-of-work. External full nodes are required to resolve top-level domains from the HNS root zone. All data is verified, but the hsd full nodes you connect to will learn the top-level domains you are looking up.

There are available guides for [connecting Fingertip to Firefox](https://gist.github.com/pinheadmz/264e360742e8b35798bf88005e77f2f8) and a video demonstration for [connecting Fingertip to Chrome or Safari using the operating-system level](https://vimeo.com/584892397).

### Beacon Web Browser
[Beacon Web Browser (currently only released for iOS)](https://impervious.com/beacon)

>  Security: HIGH
>  Privacy: LOW
>  Decentralization: MEDIUM
>  Convenience: LOW
>  Complexity: LOW
{.is-info}

Beacon is a web browser that works a lot like Fingertip but is self-contained. It is convenient since it requires no setup, but inconvenient since it requires a user to abandon their current default browser. The technical mechanism is similar to Fingertip but Beacon does not do recursive name resolution, meaning it relies on external DNS-over-HTTPS servers. It leaks domain names to those servers, but still verifies all data using the blockchain data it keeps internally from hnsd. If Chrome / Safari / Brave / Opera ever adopt Handshake in a meaningful way, this method will probably be the best we can hope for.

### Internal HNS resolver: hsd or hnsd without letsdane proxy
[hsd](https://github.com/handshake-org/hsd)
[hnsd](https://github.com/handshake-org/hnsd)

>  Security: LOW
>  Privacy: HIGH (hsd) / MEDIUM (hnsd)
>  Decentralization: HIGH (hsd) / MEDIUM (hnsd)
>  Convenience: MEDIUM
>  Complexity: HIGH
{.is-info}


A user can install their own HNS resolver but neglect to install the DANE verifying software. This user will be able to browse to websites hosted on HNS domain names BUT NEVER SECURELY. This user can not establish an HTTPS connection but can still "see" HNS websites, assuming the web server allows HTTP connections without requiring or enforcing security. A user can even run hsd on a server and connect to it remotely. This is technically an external resolver and will require additional security (SIG0) to ensure that the received data is authentic.


### External HNS resolver like hdns.io, NextDNS, resolvr, HandshakeNames
[hdns.io](https://hdns.io)
[NextDNS](https://nextdns.io/)
[resolvr](https://resolvr.info/)
[HandshakeNames](https://handshakenames.com/dns-resolver)

>  Security: LOW
>  Privacy: LOW
>  Decentralization: LOW
>  Convenience: HIGH
>  Complexity: LOW
{.is-info}

[Bob Wallet Chrome Extension](https://bobwallet.io/) is another example of this method. The most important thing to know about this method is that SOMEONE ELSE IS VERIFYING THE BLOCKCHAIN, NOT YOU. Since the blockchain is the root of all "trust" in this system, you are outsourcing absolutely everything including security and privacy. It may be possible to run a letsdane proxy in addition to these resolvers and establish a secure HTTPS connection between your browser and the web server. However, since the blockchain data is being served to you from some untrusted source we can not classify this method as truly secure. This is currently how Brave actually resolves "decentralized domain names" such as Unstoppable Domains and Ethereum Name Service.

### External proxy like hns.to
[hns.to](https://hns.to)

>  Security: LOW
>  Privacy: LOW
>  Decentralization: LOW
>  Convenience: EXTREMELY HIGH
>  Complexity: LOW
{.is-info}

Users are presented with an illusion that they can "see" websites hosted on HNS domains but really they are looking at a website hosted on legacy ICANN domain name. If there is any HTTPS security offered at all it is anchored in legacy certificate authority. The server knows the entire URL you are looking up and knows all data you send and receive to the web server. The proxy CAN ALTER DATA you send or receive to the web server, including links. This is currently how Puma browser resolves Handshake domains.


## Features and Rankings
### Security
Can you trust the authenticity of the content you see in the browser? Can you enter private, personal or sensitive data into a website? Most browsers offer a "lock" icon in the URL bar when an HTTPS connection is established, meaning the answer to both these questions is "yes". Eavesdropping on your connection is impossible and altering data to and from both you and the web server is impossible. It's important to remember that HTTPS requires proper configuration by the website and domain name owners as well. Just because you have set up the proper tools on your computer does not mean every website is secure.

- **HIGH**: Secure HTTPS is available. Domain name has been cryptographically verified and web server identity has been cryptographically identified.
- **LOW**: Secure HTTPS is not available. The chain of cryptographic verification is broken. Do not trust this content. Do not enter personal data into this website.

### Privacy
Do any other entities (besides your browser and the web server) know what websites you are visiting?

- **EXTREMELY HIGH**: Everything about your connection is completely encrypted and obfuscated. Only possible with networks like Tor and NOT Handshake. This level is listed only as a reference point.
- **HIGH**: Domain name lookups are done entirely on your own computer, no one else knows what domain names you are looking up.
- **MEDIUM**: Only the top-level domain is leaked to another entity. For example, some service may know the URL you are seeking ends in .com but they do not know you are looking up google.com.
- **LOW**: The entire URL is leaked to another entity. Someone out there knows exactly which websites you visit.

### Decentralization
How many other services do you rely on for this connection? How easy is it for your connection to get censored or terminated outside of your control?

- **EXTREMELY HIGH**: It is essentially impossible for any entity to prevent your browser from connecting to the web server. Only possible with networks like Tor and NOT Handshake. This level is listed only as a reference point.
- **HIGH**: You do not rely on any service or third party to connect to the web server. Everything about the connection is handled by your computer and the web server without any help.
- **MEDIUM**: Some outside service is required, but that service can be provided by anyone (even yourself if you run your own service). If one service provider fails, ANY other provider can be used.
- **LOW**: Your connection depends entirely on one single service. If they go down, you can not connect. If they decide to block you or ban you from their service, you can not connect.

### Convenience
How easy is it to configure your computer to use this method.

- **EXTREMELY HIGH**: User does nothing except buy a computer. This is how the legacy DNS and certificate authority systems work.
- **HIGH**: User changes some kind of setting in their operating system or in their browser's preferences, but otherwise doesn't have to do anything unusual.
- **MEDIUM**: User installs new software on their computer, but otherwise doesn't have to do anything unusual or anything outside their every-day internet usage behavior.
- **LOW**: User installs new software on their computer and has to change their ordinary behavior (like switching to a new browser).

### Complexity
Related to convenience. What percentage of the internet population is capable of executing all the necessary steps to correctly execute this method?

- **HIGH**: Requires command-line tools, installing dependencies, shared libraries or compilers.
- **MEDIUM**: Requires installing new software directly from a website or GitHub (i.e. not your device's "App Store").
- **LOW**: Nothing required, user does nothing they do not already do every day with their device. Includes changing settings in an application or operating system.


