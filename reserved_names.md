---
title: Reserved names
description: 
published: 1
date: 2024-02-09T05:42:01.227Z
tags: 
editor: markdown
dateCreated: 2024-02-09T05:42:01.227Z
---

# Reserved name

Existing TLDs and over 100,000 Alexa websites are reserved on the Handshake blockchain. Upon removing collisions, generic, and exclusions (e.g. 1 or 2 character names), approximately 80,000 names remain. Using the root key and DNSSEC, domain owners can cryptographically prove ownership to the Handshake blockchain to claim names. 100,000 was chosen as a number which the ownership is clear and has already gone through policy and process.

## Existing TLDs
All existing [ICANN TLDs](https://github.com/handshake-org/hs-names/blob/master/names/tld.json) ([ccTLDs](https://github.com/handshake-org/hs-names/blob/master/names/cctld.json), [gTLDS](https://github.com/handshake-org/hs-names/blob/master/names/gtld.json), [rTLD](https://github.com/handshake-org/hs-names/blob/master/names/rtld.json)) are reserved and can't be opened at auction.

## Alexa
The Handshake blockchain pre-reserves the [top ~100,000 domain names](https://github.com/handshake-org/hs-names/blob/master/names/alexa.json) from the Alexa top 1 million domain names. Since the Handshake blockchain only thinks in terms of top-level domains, existing domains on the Alexa top 1 million are "converted" to TLDs.

For example:

`google.com` -> `google`
`bbc.co.uk` -> `bbc`

### Rules
In order to have your domain pre-reserved, there are a few rules implemented in generate.js that it must conform to:

- The domain's deepest subdomain must not be in the blacklist.
- The domain's deepest subdomain must not be a pseudo-TLD for an existing naming project.
- The domain's deepest subdomain must not be a trademarked name.
- The domain must not collide with an existing top-level domain in ICANN's root zone, as all existing TLDs are also pre-reserved. For example, `google.com` would lose to `google`.
- The domain must not collide with a higher-ranked domain. For example, `google.co.uk` would lose to `google.com`. Only the owner of the higher-ranked domain is able to redeem it.
- The domain must not be deeply nested. `bbc.co.uk` will work, but `jeffs-blog.wordpress.com` will not.
- The domain must abide by Handshake policy standards (no leading or trailing hyphens or underscores).
- The domain must not be a single letter.
- If the domain is ranked lower than 50,000, the domain must not be two letters.
- If the domain is ranked lower than 50,000, the domain must not be an [English word](https://raw.githubusercontent.com/handshake-org/hs-names/master/names/words.json).

## Blacklist
The following list is permanently reserved:

- `example`
- `invalid`
- `local`
- `localhost`
- `test`

## Late Additions
Names which were added *after* the final snapshot:

- `charity` - A new gTLD added on ICANN's system.
- `inc` - A new gTLD added on ICANN's system.
- `ss` - ccTLD for South Sudan.
- `xn--mgbah1a3hjkrd` - iccTLD for Mauritania.
- `cpa` - A new gTLD added on ICANN's system.
- `gay` - A new gTLD added on ICANN's system.
- `xn--qxa6a` - iccTLD for .eu in Greek.
- `llp` - A new gTLD added on ICANN's system.

Names which were *removed* after the final snapshot:

- `goodhands` - A gTLD removed from ICANN's system.
- `jlc` - A gTLD removed from ICANN's system.
- `panerai` - A gTLD removed from ICANN's system.
- `spiegel` - A gTLD removed from ICANN's system.
- `statoil` - A gTLD removed from ICANN's system.
- `telecity` - A gTLD removed from ICANN's system.
- `vista` - A gTLD removed from ICANN's system.
- `epost` - A gTLD removed from ICANN's system.
- `zippo` - A gTLD removed from ICANN's system.
- `blanco` - A gTLD removed from ICANN's system.
- `active` - A gTLD removed from ICANN's system.
- `bnl` - A gTLD removed from ICANN's system.
- `cartier` - A gTLD removed from ICANN's system.
- `chrysler` - A gTLD removed from ICANN's system.
- `dodge` - A gTLD removed from ICANN's system.
- `doha` - A gTLD removed from ICANN's system.
- `duns` - A gTLD removed from ICANN's system.
- `everbank` - A gTLD removed from ICANN's system.
- `honeywell` - A gTLD removed from ICANN's system.
- `iselect` - A gTLD removed from ICANN's system.
- `ladbrokes` - A gTLD removed from ICANN's system.
- `mobily` - A gTLD removed from ICANN's system.
- `mopar` - A gTLD removed from ICANN's system.
- `piaget` - A gTLD removed from ICANN's system.
- `srt` - A gTLD removed from ICANN's system.
- `starhub` - A gTLD removed from ICANN's system.
- `uconnect` - A gTLD removed from ICANN's system.
- `warman` - A gTLD removed from ICANN's system.
- `xn--mgbb9fbpob` - An iccTLD removed from ICANN's system.
- `lancome` - A gTLD removed from ICANN's system.
