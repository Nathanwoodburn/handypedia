---
title: FAQ
description: 
published: 1
date: 2024-02-09T03:37:36.957Z
tags: 
editor: markdown
dateCreated: 2024-02-09T03:37:36.957Z
---

# FAQ

## How do I use Handshake domains?
See the [Getting Started guide](/en/getting-started)

Where can I buy?
You can buy Handshake coins on Namebase with Bitcoin, or USD if you verify your identity. Other exchanges can be found [here](https://www.coingecko.com/en/coins/handshake#markets). As of 12 Dec, 2021 that list includes:

[MXC (HNS/USDT)](https://www.mexc.com/exchange/HNS_USDT)

[Gate.io (HNS/BTC)](https://www.gate.io/trade/HNS_BTC) [(HNS/USDT)](https://www.gate.io/trade/hns_usdt)

[Bittrex (HNS/BTC)](https://bittrex.com/Market/Index?MarketName=BTC-HNS) [(HNS/USDT)](https://global.bittrex.com/Market/Index?MarketName=USDT-HNS) [(HNS/ETH)](https://global.bittrex.com/Market/Index?MarketName=ETH-HNS)

[Namebase (HNS/BTC)](https://www.namebase.io/pro)

[Coinex (HNS/USDT)](https://www.coinex.com/exchange?currency=usdt&dest=hns&tab=limit) [(HNS/BTC)](https://www.coinex.com/exchange?currency=btc&dest=hns&tab=limit)

[Hotbit.io (HNS/USDT)](https://www.hotbit.io/exchange?symbol=HNS_USDT) [(HNS/BTC)](https://www.hotbit.io/exchange?symbol=HNS_BTC)

[ZTB(HNS/USDT)](https://www.ztb.im/exchange?coin=HNS_USDT)

[BIT(HNS/USDT)](https://www.bitrue.com/trade/hns_usdt)


## How do I stake?
Handshake is not an ERC20 token on Ethereum and is not generally considered a "DeFi" asset.

You can earn money by selling subdomains within your TLDs by visiting the [Namebase Registry](https://www.namebase.io/registry) and entering your name. There is a one-time $100 staking fee (paid in HNS), though, on top of the other per-sale fees. This is not a decentralized service, it is a custodial service provided by Namebase. Any second-level domains purchased from a staked TLD are not ERC20 or any other kind of token.

You also have the choice of staking your names in a decentralized manner, with the possibility of doing so in a completely trustless manner. Check out [Badass Domains](https://badass.domains/) for more info on that.

## What wallet is there?

Currently there are two fully featured wallets, [Bob Wallet](https://bobwallet.io) and [Namebase](https://www.namebase.io). Bob Wallet is non-custodial software which can be used trustlessly, whereas Namebase is a custodial online wallet. You can not buy coins from Bob Wallet.

## What's with the @hns twitter?

The @HNS Twitter handle is a community-run account and periodically tweets/RTs relevant news, resources, and mentions of Handshake. The account was originally acquired by the project founders and has had its ups and downs of activity. There was a [long community discussion](https://github.com/handshake-org/handshake-web/issues/14) about how to use it going forward and it was decided that the best action was to effectively terminate the account and let the community speak for itself on twitter. Follow #HNS or $HNS to track actual community activity.

## Is there a roadmap?
No. There is no central HNS foundation, no marketing budget and no central development effort. Handshake is being built by a diverse group of contributors with their own personal road maps and funding.

## When Coinbase/Binance/Any other major exchange?
Since there's no central HNS foundation nor central development team, the communication with those exchanges lies on the individual members of the community. You, as a Handshake Director, can also help contacting those exchanges and promoting HNS. For technical questions on this topic, check the [Dev Chat on Telegram](https://t.me/hns_tech).

## Who should I talk to about listing fees or promotional services?
See above, there is no central foundation or marketing budget. There are a few decentralized fundraising efforts but they are focused on development and community building:

- [HNS Fund](https://hnsfund.titansofdata.org/)
- [Handshake Institute](https://handy.wiki/wiki/Handshake_Institute)
- [dWeb Foundation](https://www.decentralizedinter.net/)

## Can I use my current browser to visit Handshake websites?
Yes you can. See [Resolving Handshake Domains](#todo)

You can run an hsd full node with recursive resolver on a Raspberry Pi on your local network by following [this guide](https://gist.github.com/pinheadmz/a3e5ded7a4f0413e948a6a257c375891).

Note that while a resolver is the only component needed to browse HNS domains, security is a separate issue. At this time since no major browsers support DANE verification, an additional tool is necessary like [letsdane](https://github.com/buffrr/letsdane).

[Fingertip](https://impervious.com/fingertip.html) is a system extension that runs the hnsd light client and letsdane combined to enable trustless, private HNS name resolution and DANE-verified https for compatible browsers. There are available guides for [connecting Fingertip to Firefox](https://gist.github.com/pinheadmz/264e360742e8b35798bf88005e77f2f8) and a [video demonstration for connecting Fingertip to Chrome or Safari](https://vimeo.com/584892397).

[Beacon Web Browser](https://impervious.com/beacon) is an iOS app (Android, Desktop coming soon) that verifies DANE and can browse to Handshake websites natively and securely.

## What's this about reserved names? Can I get one?
A snapshot of Akexa's Top 100,000 sites from 2019 is included and these websites can claim their respective TLDs on Handshake (ex: namecheap.com can claim .namecheap). More information on proving ownership and claiming is available on [hsd-dev.org](https://hsd-dev.org/guides/claims.html).

ICANN TLDs (.com, .org, etc.) were also included in the snapshot and can be claimed by following the same process.

