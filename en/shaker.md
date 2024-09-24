---
title: Shaker
description: 
published: 1
date: 2024-09-11T05:20:46.199Z
tags: tools
editor: markdown
dateCreated: 2024-02-10T01:30:07.120Z
---

# Shaker

Shaker is a discord bot used to verify ownership of a Handshake domain.
This bot is managed by [Nathan.Woodburn/](/directors/nathanwoodburn) so please contact him if the bot has any issues.

## How to use
1. Run `/verify` and enter your domain
2. Follow the instructions the bot gives by adding the TXT record provided
3. Wait a few minutes and run `/verify` again with the same domain as before to get the bot to check you added the TXT record



## How to add to your own server
1. Invite the bot using [this link](https://discord.com/api/oauth2/authorize?client_id=1073940877984153692&permissions=402653184&scope=bot)
2. Create a Verified domain role (eg. the Namebase uses `Namer` and the HNSDNS server uses `Domainer`)
3. Tell the bot to assign verified users that role by using the `/setverifiedrole` command
