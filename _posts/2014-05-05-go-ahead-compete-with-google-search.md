---
layout: post
title: Go ahead, compete with Google Search
categories: tech
published: true
---

Google’s mission is to organize the world’s information and make it universally accessible and useful. Google Search has become a shining example of progress towards accomplishing this mission.

Google Search is the best general-purpose search engine and it gets better all the time. Over the years it killed off most of it’s competitors.


Market share has been pretty stable since 2010. Since Yahoo Search is powered by Bing the there’s really only four general-purpose search engines -Google, Bing, Yandex and Baidu.
While there are a few smaller players in general-purpose search market such as Ask, DuckDuckGo, Blekko, it is hard to see how they will ever grow to overtake Google.

With this in mind, I would like to offer what may be a counter-intuitive idea: now more than ever, it is possible to compete and win against Google. In fact many companies do it today. To see it, we need to look at the technology and the market from a different perspective.

A 2013 study by Incapsula found that over 61% of the web traffic is generated by bots. Some of the bots are malicious, but the bulk of non-human traffic is attributed to all sorts of different web crawlers. There are more types of crawlers and they crawl the Web more frequently than before.


Bots make up over 61% of the traffic. Just non-malicious crawlers alone generate more traffic than people.
What is behind such huge growth? It comes from a growing set of services that (to borrow Google’s mission) organize world’s information to make it more accessible and useful. This realization is, of course, a complete contradiction to the conventional view that Web Search innovation have ended and that Google has won. The fact is, there’s growing number of successful Web Search Engines out-there.

Search engines are everywhere
To see just how prevalent web search engines are we need to look at specific industries, specific use-cases, specific domains of knowledge.

Here are just two examples of consumer services who don’t call themselves search engines, but that’s exactly what they are.


TripAdvisor is a search engine that also indexes multiple different sources of information. Just like Yelp, web isn’t the only source of it’s data. Its ranking algorithms rely on comments in a big way. The ranking on TripAdvisor is affected by quality, quantity and recency of comments authored by their users.


WebMD organizes medical knowledge from the web and applies a heavy doze of expert curation to make sure the content they index is accurate. Its ranking algorithms take into account semantics of the medical field such as relationships between symptoms and diseases.

## A search engine for technology support
Radialpoint’s mission is to make tech support awesome. What makes tech support interesting is that it is a $20B industry where support agents only manage to resolve less than half of customer’s issues. This massive inefficiency stems from lack of instant access to comprehensive knowledge about solutions.

Take a Netflix user who can’t stream & calls for support. Is the issue related to Netflix, XBox where the app is running, the Samsung TV, the Linksys wifi router, or the Comcast Internet connection?

Most support agents routinely use Google search along with their internal knowledge base. Yet, Google’s results are neither validated nor ranked based on the needs of tech support use-case.

Being a general-purpose search engine, Google does not fully understand the semantics of a technical support problem. And just like in travel, health or e-commerce, understanding of semantics and context is essential to effective search.

Radialpoint Reveal is a browser extension that improves Google search for tech support agents.
Reveal helps agents find the best tech support solutions from across the web and share them with across tech support knowledge network. When agents perform a Google search, the Reveal browser extension finds the most useful solutions found by their colleagues.

Reveal is Radialpoint’s first product that incorporates a search engine, but it won’t be the last. We’re just getting started. And in the process of building the search engine for tech support we tackle challenges that are similar to those seen in other verticals.

##Building a vertical search engine
At the highest level, vertical search engines have three big challenges in common.

First, is getting raw content. Unlike general-purpose engines like Google and Bing, vertical search engines need to organize a specific portion of the web and possibly include other sources of content beyond the Web. Filtering the Web is a challenge. The system will need to crawl the subset of the Web without actually having access to the entire Web. One of the resources that helps if CommonCrawl. Common Crawl builds and maintains on open crawl of the Web that can be accessed and analyzed by everyone.

At Radialpoint, we’re using CommonCrawl as a starting point, to find the most relevant parts of the web — tech support forums, knowledge bases, troubleshooting blog posts, etc. We train the classifier by observing what content tech support agents are using when they solve customer issues.

The second challenge is to structure the raw content. Vertical search engine can and should leverage the semantics of a given knowledge domain to find that structure. This is a key tactic how vertical search engine can compete and win against a general-purpose search engine. Extracting structure from messy unstructured text is not easy, but there are lots of tools that help with this task. In Radialpoint’s case we’re extracting entities like “devices” and “online services”, to uncover relationships between Xbox and Netflix entities.

When the most relevant content is structured and organized using semantics of a given vertical, a search engine needs to be able to process user’s query, to understand its intent and to add all available context. In our example, when the users says “I cannot watch Netflix on my TV” a search engine designed for tech support shouldn’t look at the query as a bunch of keywords. It should know that a use-case of streaming a movie requires working internet connectivity.

To sum up, the best way to compete against Google is not to build another general-purpose search engine. It is to build another vertical semantic search engine. The better engines understand the specific domain, the better chance they have to be better than Google.