# newsroom

Schema for News Context and Authenticity

## Summary


News Authenticity needs to be restored.  For a time, our news was respected and viewed as the Fourth Estate of Democracy.  It was a pillar of political discourse and the unheiver of corruption.  Today it’s hard to believe anything.  It’s hard to know what is real, fake, opinion, or entertainment.

If a site claims to be news, it needs to adhere to a set of ethics or standards that should be reflected digitally in metadata, and unique visual interfaces. This is especially needed for interfaces that reach large audiences, e.g. google search, google news, facebook, twitter, etc.   We can call these interfaces, web pages, or applications that collect news, Aggregators. Moreover, Aggregates should be able to more easily distinguish/identify a variety of sources by their category; for example, news should be denoted as news, opinion pieces should be denoted as opinion pieces, satire as satire, entertainment as entertainment, etc. 

Additionally Aggregators should agree on a set of standards or ethics to require of articles representing in different categories.  If sources are deemed bad actors, and do not conform to the ethical standards of that category then we should discuss expected repercussions.

Finally, Articles that require more critical review might present interfaces that allow people to judge the bias, authenticity, accuracy, or objective nature of those articles, whereas, entertainment, opinion, and humor articles, might possess a more standard interface.


## Inspiration
“Real” news looks the same as any url listed in an aggregator, but not all links are the same.  Can meta data help inform aggregators, so that they can present different UI elements to help improve the authenticity of news?
http://www.theverge.com/2016/12/6/13850230/fake-news-sites-google-search-facebook-instant-articles

## Current Work
Currently, web pages contain meta data that inform Aggregators like Facebook and Google about a Title, Lead Image, and Page Type; however, there is no standard to inform Aggregators about the Article Type.

Some sites like the New Yorker, or New York Times do attempt to tag or identify news, opinion, or satire Articles, but they do not conform to a standard.  As a result it’s difficult to act on this meta data.

Web pages do use more detailed Metadata to inform these tools about Video Objects, their creators, and other content related details, but again, for articles there is little to no additional standard information provided other than the by-line, and date.


Wikipedia has a community enforced requirement to cite facts, and has additional elevated procedures for ‘controversial’ pages/ articles.  They also ban or block IPs from devices that constant violate these rules.


Furthermore, the Fairness Doctrine for mass media TV news was adopted in 1949 (https://en.wikipedia.org/wiki/Fairness_Doctrine), and was slowly dismantled in the mid to late 80s.  The result is that news has drifted from being objective, and instead opinion is being presented as fact.  Aggregators could do more to elevate the political discourse on the web.


## Recommendation
Create a specification to identify the type of article; ie. ( Humor, Entertainment, OpEd, Satire, News, Scientific, Research/Academic, Industry White Papers, etc… )  

Each article type would carry with it a set of design principles, and best practices for the aggregator. For example a ‘humor’ article might have a traditional interface on Facebook with likes and emojis, while a ‘News’ or ‘Scientific’ article might have a more objective interface, with the intent of assessing the quality of the work of an article instead of happy/sad emojis.

The interface for ‘News’ categories might warn the user of news that is not objective and contains a bias.  Other interfaces might prompt users to rate the authenticity of the article, or point out that the article has some unsubstantiated claims. The interface might also provide other articles that cite the same claims. Furthermore, an algorithm should be developed to measure the quality/authenticity of news sources, similar to google PageRank. 

The process and interface implementation details would be up to the aggregator to choose appropriate interfaces and processes for the application.  The goal of the spec is to standardise the meta data, and the content type expectations.

Additionally, Claims are information phrases that use metadata to cite a source.  Those Sources then might be peer reviewed and verified with cryptographic signatures.


### Article Types
The following article types would be a good start to ethical writing guidelines.  Each of these types could either be human curated along these guidelines, or machine curated in bulk with a human touch.  Machines are getting better at detecting word phrases that contain a bias to them.  Claims might be identified as well by machines looking for things that might require a citation, numbers are good candidates as low hanging fruit, but more sophisticated machine reading could be leveraged later on.  Some Aggregators might choose to keep their editorial process entirely human or again have a human touch.

Additionally it might be possible for Original Content to be reviewed and cryptographically signed by peer reviewers, or interviewees.


News ( breaking news, confirmed news )
* Objective, limited or no bias, limited use of emotional words
* Low number of Unsubstantiated Claim


Research ( Scientific, Academic, White Papers )
* Peer Reviewed
* Cryptographically signed by reviewer, and rated


Opinion ( OpEd, Editorial, book reviews, product reviews )
* Bias Allowed
* Low Number of Unsubstantiated Claims


Education ( Encyclopedia, Lesson, History )
* Cryptographically Reviewed and Signed
* No Unsubstantiated Claims


Lifestyle ( dwell, art, design, auto, gardening, cooking )
* Minimal Opinion


Biographical sketches ( Interviews )
* Maybe Cryptographically signed by the interviewee


Entertainment ( Humor, Gossip, Tabloid, Satire )
* Minimal substantiation


User Generated Content ( blogs, comments, personal views )


### Source Types
A source type can carry multiple Article Types, for example Vanity Fair might have both News and Lifestyle articles. 

Articles should be authenticated by article type, and not source type (though source type can inform an article ranking). 

### Aggregators
An Aggregator is an application or website that aggregates a set of web articles.  The articles may be selected by a search term or a social graph filter for that, or some other application specific means.  For example, RSS Readers require a user to subscribe to that source.


Common Aggregators 
- Browsers
- News Dashboards
-- Google News
-- Yahoo News
-- Bing News
Social Sites
-- Facebook.com
-- Twitter.com
-- Reddit.com
Search Engines
-- Google.com
-- Bing.com
-- DuckDuckGo.com
RSS Readers
-- Google News Reader
-- Mozilla Thunderbird News Reader
Homepages
-- Yahoo Homepage
Content Recommendation Engines
-- Boomtrain
-- Gravity
-- Taboola


Claim


A claim is written statement that can be cited back to a source and is identified by metadata.  The Source could carry with it authenticity and challenges to that authenticity. 


Unsubstantiated Claim - a claim that does not have a valid source, these can be identified and annotated by a 3rd party, either by machine or human editors.
Snopes identifies false claims on web pages, a few days to weeks after the article becomes popular
Google might be able to use Natural Language Processing to detect axioms or claims.  If they are not substantiated then they could be recorded as ‘unsubstantiated’ for the purposes of ranking the materials authenticity


### Substantiated Claim
Substantiated claims should gain in authenticity weight as they pass certain bars.
A link to Original Content
A link to Verified Content
Cryptographic Peer Review
Critical Editorial Review by 3rd party websites of Original or Verified Content ( ie. snopes, politifact, etc… )
Original Content


Original content is unverified and is not peer reviewed.  It can assert itself as any time of content but will represent as an unverified claim.


### Verified Content


Verified content is a claim that has been peer reviewed and signed validating it.


### Editorial Sites
Editorial sites, are like Snopes.com, but should provide a standard API spec.  Editorial sites will offer fact checking, and opinions on Original Content, Verified Content, and popular Articles.
A standard API will make it easier for Aggregators to integrate multiple Editorial Sites into the review process to provide better Authenticity to the results.


### Trusted News Network Graph
A trusted news network graph depicting reliability/trust value of sources, which can be used by Aggregators algorithmically to authenticate news sites and source links/articles. 

Such a graph could likely be generated based on the out-going links from a given News Source, but this only provides a positive view of sites.

Another option might be to create a spec for news sites to provide a ‘whitelist’ and ‘blacklist’ of trust.  No single news source would be authoritative on the whitelist or blacklist, and so an indexing platform would need to build the graph on a regular bases to determine which sites are good actors subscribing to the shared ethical contract and which ones are bad actors.  Some indexing sites could also combine this with a ‘pagerank’ style algorithm to more heavily rate better results opinions on authenticity vs. lower ranking sites opinions.


https://en.wikipedia.org/wiki/List_of_most_popular_websites






