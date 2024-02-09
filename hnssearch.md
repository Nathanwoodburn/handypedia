---
title: HNSSearch
description: 
published: 1
date: 2024-02-09T04:57:24.624Z
tags: 
editor: markdown
dateCreated: 2024-02-09T04:57:24.624Z
---

# HNSSearch

![hnssearch_logo.jpg](/hnssearch_logo.jpg){.align-right}
**HNSSearch** (Slogan: Your window into the dweb) is a search engine that exclusively indexes Handshake websites and that does not track any user or traffic information. The first beta went live in February 2021 with the official launch of Version 1 on the 28th of February. The shield in the logo of HNSSearch is a representation of the commitment to protect the privacy of its users by not gathering any information. Results are based on search queries and not previous searches.

## History

![hnssearch_frontpage.png](/hnssearch_frontpage.png){.align-right}
Version 1 of HNSSearch was released on the 28th of February after a two-week-long public beta and was meant to be a proof of concept. The design was a clone of Google with the addition of dark mode and additional features such as shortcuts.

V1 was well received by the community and received a lot of feedback and suggestions for improvements. The decision was made to not continue the development of V1, but to immediately start working on Version 2 that would have a new codebase as well as a new design and new functionalities. V1 was written mainly in PHP, used a MySQL Database, and was hosted on a conventional cloud provider.

LINDA (Living Indexer Navigating Decentralized Assets) is the crawler of HNSSearch and written in Python, the search engine itself is made by [MeiliSearch](https://github.com/meilisearch/MeiliSearch) and was written in Rust and the frontend is made with React. This new tech stack allowed for V2 to be hosted on dweb services such as [Akash](https://akash.network/) for the backend and [Sia Skynet](https://siasky.net/) for the frontend.


## Search results

With V2 HNSSearch introduced search as you type powered by [MeiliSearch](https://www.meilisearch.com/). This allows the search results to be displayed in real-time as the search term is entered and allows the user to narrow down their query and stop if they have found what they are looking for. MeiliSearch also brings typo tolerant search results and as such provides a natural query language experience. The search results are purely ranked by hits and accuracy and no other ranking takes place. Therefore, the results are independent of user preference and previous search queries.

## Shortcuts

Shortcuts were proposed by community members and are derived from the !Bang feature of [DuckDuckGo](https://duckduckgo.com/bang).

Shortcuts can be used by entering the shortcut followed by a space and the search query (for example !nb hnssearch). By then pressing enter, the search query will be sent to the desired website and a new tab opens.

Available shortcuts:

- !hn => hnsnetwork
- !nb => namebase
- !hm => handshake mercenary
- !sp => parking.sinpapeles
- !ni => niami
- !hf => e.hnsfans
- !sh => shakestats


## Specialty logos
For special occasions, the logo on the front page was changed to commemorate the special occasion and to show love to other dweb projects.

> ![hnssearch_handycon.png](/hnssearch_handycon.png)
	Handy Con 2021


> ![hnssearch_handyhost.png](/hnssearch_handyhost.png)
  Launch of HandyHost

> ![hnssearch_stpatrick.png](/hnssearch_stpatrick.png)
  Saint Patrick's Day 2021
  
## Future development
The beta of V2 ended on the 19th of December 2021 and the website was taken offline. Currently, the developers work on refining and finishing V2 to release it and to open-source the code.

## External links
- [Official Website (Handshake native)](http://hnssearch/)
- [Official Website (mirror)](https://hnssearch.io/)




