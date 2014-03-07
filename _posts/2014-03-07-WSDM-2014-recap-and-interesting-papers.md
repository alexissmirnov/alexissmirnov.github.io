---
layout: post
title:  "WSDM 2014: Interesting papers"
date:   2014-03-07
categories: tech
---
A week ago I had a great pleasure to attend a few sessions of [WSDM 2014](www.wsdm-conference.org/2014) conference in New York. The acronym is Web Search and Data Mining, but the name of the conference is usually pronounced as "wisdom". Given interest in domain-specific (vertical) semantic search engines, there are several papers that caught my attention. 
## .


## 1. On Building Entity Recommender Systems Using User Click Log and Freebase Knowledge
This is a highly relevant paper that I've reviewed [here](http://weblog.smirnov.ca/tech/2014/03/06/Research-paper-review.-On-Building-Entity-Recommender-Systems-Using-User-Click-Log-and-Freebase-Knowledge.html).
## 2. Exploiting User Disagreement for Web Search Evaluation: an Experimental Approach
The key insight of this paper is that with a high disagreement amongst users, lower relevance levels might need to be promoted more than in the case where there is global consensus on the top results.

Read the paper [here](wwwhome.ewi.utwente.nl/~hiemstra/papers/wsdm2014.pdf).
## 3. Modelling Dwell Time to Predict Click-level Satisfaction
This paper shows that the topic of the page, its length and its readability are all critical in determining what dwell time threshold must be selected to indicate if a page click is associated with satisfaction, as oppose to a bounce-back. The authors propose a method to account these factors that significantly improves filtering out of noisy clicks (bounce-backs). 

For this paper to be relevant, your search engine must first leverage click-though data for relevance ranking (see [Implementing Click-through Relevance Ranking in Solr](http://www.slideshare.net/LucidImagination/bialecki-andrzej-clickthroughrelevancerankinginsolrlucidworksenterprise)). Once this is in place this paper describes a good improvement to the baseline.

Read the paper [here](http://research.microsoft.com/en-us/um/people/ryenw/papers/KimWSDM2014.pdf).
## 4. Lessons from the Journey: A Query Log Analysis of Within-Session Learning 
This paper looks at how user's knowledge grows during a search session and how to improve ranking and UI to optimize this dynamic.

The paper studies a query log dataset with knowledge seeking sessions for procedural and declarative knowledge. Such session take only 3% of all searches of a general-purpose engine like Bing. Procedural knowledge generally answers "how to" questions (eg. ehow.com) while declarative knowledge describes the facts (eg. wikipedia.org). The paper clearly shows that user's expertise evolves during the time of the session - their vocabulary increases, queries get longer and more complex, etc. People tend to learn new terms from pages they clicked on (or page snippets), and then use those terms in subsequent queries.

The paper also lists the document features that have the most knowledge acquisition potential. A document classifier based on these features is able to accurately predict the clicks, thus creates an opportunity to improve the user experience of the search session by surfacing the knowledge to the user and by improving the ranking.

Read the paper [here](http://research.microsoft.com/en-us/um/people/teevan/publications/papers/wsdm14.pdf).

## 5. Knowledge-based Graph Document Modelling
This paper proposes a new method for entity ranking and finding semantic similarities between documents. The method uses [DBpedia](www.dbpedia.org) entity graph, in order to provide a graph-based, representation of natural language texts. Thanks to an effective weighting of the semantic relations found within the semantic network, as well as a robust concept matching technique, we are able to achieve competitive performance, while providing an unsupervised model for both of these difficult tasks.

The paper states that authors are interested in applying their techniques within other verticals, presumably those that have a large entity graph to work with.

The paper was made available to WSDM attendees, but I wasn't able to find a public link to the paper. It is available for purchase on [ACM](http://dl.acm.org/citation.cfm?id=2556250&dl=ACM&coll=DL&CFID=293807221&CFTOKEN=56074720).

## Other papers
I haven't reviewed all the papers that seemed interested. Those building entity graphs and vertical semantic search engines, I invite you to read them and comment.

- [Social Collaborative Retrieval](http://web.eecs.umich.edu/~kulesza/pubs/social_wsdm14.pdf)
- [Adapting Deep RankNet for Personalized Search](research.microsoft.com/pubs/205161/wsdm233-song.pdf‎)
- [Taxonomy Discovery for Personalized Recommendation](www.cs.berkeley.edu/~yuczhang/files/wsdm14_taxonomy.pdf‎)
- [Entity Linking at the Tail: Sparse Signals, Unknown Entities, and Phrase Models](research.microsoft.com/pubs/205509/wsdm180-jin.pdf‎)
- [Going beyond Corr-LDA for Detecting Specific Comments on News & Blogs](http://mllab.csa.iisc.ernet.in/sctm/)
- Nonparametric Bayesian Upstream Supervised Multi-Modal Topic Models [ACM](dl.acm.org/citation.cfm?id=2556238‎)
- [WebChild: Harvesting and Organizing Commonsense Knowledge from the Web](gerard.demelo.org/papers/webchild.pdf‎)
- [Trust, but Verify: Predicting Contribution Quality for Knowledge Base Construction and Curation](www.ipeirotis.com/wp-content/uploads/2014/01/wsdm2014-cqual1.pdf‎)

## ~
In general, the conference was well organized and run. I liked the mix of academic and industry perspectives. I've enjoyed meeting lots of friendly people who were so open to share their expertise. I also realized how hard it is to present an academic paper in 10-20 minutes and make it clear and engaging - something I'll have to deal with soon (our paper was accepted to [Canadian AI 2014](https://cs.uwaterloo.ca/conferences/ai2014/program.html) coming in May). Most speakers did a fantastic job at it. Some resorted to condensing the paper into a dozen slides or so (with formulas and all) and then proceeded to read the slides to the audience - that's when I knew I wasn't fast enough to keep up. Perhaps this is too much to ask, but whenever a paper reports on an experiment it would be much more helpful if the dataset and the code would be made available.

