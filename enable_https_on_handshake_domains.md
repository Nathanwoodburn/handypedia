---
title: Enable HTTPS on Handshake domains
description: 
published: 1
date: 2024-02-09T03:55:04.774Z
tags: 
editor: markdown
dateCreated: 2024-02-09T03:55:04.774Z
---

# Enable HTTPS on Handshake domains


**DNS-based Authentication of Named Entities (DANE)** is an [Internet Security](https://en.wikipedia.org/wiki/Internet_security) protocol to allow [X.509](https://en.wikipedia.org/wiki/X.509) [digital certificates](https://en.wikipedia.org/wiki/Digital_certificates), commonly used for [Transport Layer Security (TLS)](https://en.wikipedia.org/wiki/Transport_Layer_Security), to be bound to [domain names](https://en.wikipedia.org/wiki/Domain_name) using [Domain Name System Security Extensions (DNSSEC)](https://en.wikipedia.org/wiki/Domain_Name_System_Security_Extensions). TLS/SSL encryption is currently based on certificates issued by [certificate authorities](https://en.wikipedia.org/wiki/Certificate_authority) (CAs). Within the last few years, a number of CA providers suffered serious [security breaches](https://en.wikipedia.org/wiki/Certificate_authority#CA_compromise), allowing the issuance of certificates for well-known domains to those who don't own those domains. Trusting a large number of CAs might be a problem because any breached CA could issue a certificate for any domain name. DANE enables the administrator of a domain name to certify the keys used in that domain's TLS clients or servers by storing them in the Domain Name System (DNS). DANE needs the DNS records to be signed with DNSSEC for its security model to work. Additionally, DANE allows a domain owner to specify which CA is allowed to issue certificates for a particular resource, which solves the problem of any CA being able to issue certificates for any domain. [(Source: Wikipedia)](https://en.wikipedia.org/wiki/DNS-based_Authentication_of_Named_Entities)


## External Guides
There are many ways of enabling HTTPS on your site with DANE depending on your technical aptitude.

Beginners can try Handout, a combination webserver and nameserver with a single-command configuration script:

- [Handout guide](https://matthewzipkin.medium.com/building-a-secure-website-on-your-handshake-tld-a8922a950a4f)
- [Handout Github repo](https://github.com/pinheadmz/handout)

These are more technical and detailed methods for advanced developers:

- [Using Apache and NSD on OpenBSD](https://www.sebastianrasor.com/blog/hosting-a-secure-website-on-the-handshake-protocol-using-dane)
- [Using nginx and PowerDNS](https://blog.htools.work/posts/hns-pdns-nginx/)

To create a self-signed SSL cert and compute its TLSA record (for developers already running a nameserver and webserver):

- [Gist by buffrr](https://gist.github.com/buffrr/609285c952e9cb28f76da168ef8c2ca6)

## Configuring a secure webserver for both ICANN and HNS simultaneously
- [How To Configure Apache/NGINX for switching TLS certs by domain name for HNS + ICANN dual name support](https://sorablog.eu.org/apache-nginx-with-hns-icann-domain.html)

## Additional Guides on Creating Handshake Websites
These methods may not enforce https/DANE, and may have other security or centralization issues.

- [Namebase Guide on Creating Handshake Websites](https://learn.namebase.io/starting-from-zero/how-to-create-a-handshake-website)

## Accessing Handshake Domains Securely
See [Resolving Handshake Domains](/en/resolving)

## Testing Tools for Handshake SSL
- [Htools Site Check](https://sitecheck.htools.work/)
