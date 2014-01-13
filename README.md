p2psearch
=========

p2psearch is a decentralized, anonymous, fully browser-based peer-to-peer search engine. 

The goal is to create a simple browser plugin that anyone with basic computer skills can install and use to perform searches through a decentralized search engine, as an alternative to corporate search engines that collaborate with intelligence/police agencies, store/sell our private data, and manipulate/censor search results.

Here's an excerpt <a href="https://cpunks.org//pipermail/cypherpunks/2013-December/002666.html">the original discussion</a> on the <a href="https://cpunks.org/">cypherpunks mailing list</a> that motivated this software:

>*Recently there has been a lot of focus on the importance of developing more secure alternatives to email, instant messaging, browsing, etc. ... but I've seen very little focus on the need for development of alternatives to corporate search engines.*

>*Corporate/state control of the Internet involves a three pronged strategy of: mass surveillance, censorship/criminalization of undesirable ideas, and traffic shaping (i.e. directing people away of things you don't want them to see, and towards things you do). Corporate search engines are implicated in all three of these, i.e. they:*

  > * <em> Monitor what we are searching for </em>
  > * <em> Censor websites by removing them from search engine indexes</em>
  > * <em> Shape traffic via non-transparent algorithms that can sort search results in a way that grants prominence to certain types of sites (corporate media, etc.), in order to suit the interests of multinational corporations and governments.</em>

>*... so obviously, developing alternatives to corporate search is every bit as crucial for protecting privacy and free speech as encrypting our emails/chats, and anonymizing our browsing ...*

>*But I've seen very little information about practical/simple options that are available for anonymous and decentralized Internet search software. I've only been able to find a few examples like YaCy, but they all seem overly complex and unusable by the vast majority of users. What are the major barriers to creating simple tools (e.g. a plugin for Firefox) that would enable users to perform anonymous, p2p web search (even if it's much slower than centralized search) and break away from using corporate search? Which current efforts to create decentralized search seem most promising to you from a privacy/security standpoint?*

>*[...] the speed advantage of centralized search will be a barrier to adoption of decentralized search. This is analogous to the difficulty getting people adopt systems like Tor because it is slow. But I think that as more people become aware of the extent of state/corporate surveillance, they will become more inclined to accept solutions that are slower in exchange for not having their search habits monitored, and also being able to receive uncensored search results. As long as decentralized search is (a) usable/simple and (b) provides quality results, I feel like speed is somewhat of a secondary concern. The key question to me is: "How do we build a search engine that is simple enough for Grandma to use, that produces quality results without massive centralized indexing servers?"*

>*Standalone P2P search applications (e.g. Yacy) don't really make sense from a usability perspective. It's unrealistic to expect hundreds of millions of users to download a standalone Java app, and configure a P2P search node. What would make more sense, and would lead to much more rapid/widespread adoption, is to use protocols like WebSockets / WebRTC to facilitate P2P connectivity in the web browser, so that everything can be done via a simple browser plugin that can be installed by anyone with few clicks, and would then just allow people to use the browser search bar as usual. This browser integration would also have the bonus of simplifying the choice of what to index -- it could just default to indexing bookmarked and frequently-visited pages, and then be optionally customized by more advanced users to create custom indexes (i.e. all of the complexity of setting up indexing could be hidden from the user, unless they choose to look for it).*

>*To help bootstrap the WebRTC nodes into the P2P network, and to deal with some of the instability inherent in P2P networks (i.e. by creating stable "super-peer" indexing nodes), I like cathalgarvey's suggestion of utilizing something like a Wordpress plugin that would use the same index/search standard as the WebRTC clients, but could additionally bootstrap the web-based clients.*

> <em><a href="http://www.interference.cc">Jesse Taylor</a> (jessetaylor84@riseup.net)</em>

===========

So with that in mind, here's some hand-waving regarding what I want to do (probably not starting in earnest until Summer 2014, unless someone else contacts me and expresses interest on starting sooner):

* Firefox/Chrome plugins
  * use WebRTC / Websockets to form P2P overlay
  * integrate with search bar
  * Create locally hosted index
    * defaults to using bookmarks and recently/frequently visited sites
      * What are privacy/security implications of indexing a user's bookmarks/history?
        * How could this be used to break anonymity? 
      * What if we defaulted to hosting the index of the super-peer we bootstrapped through, instead?
    * can be customized by users who want to specify other sites to index
  * Anonymization ...
  * Search algorithms ...
* Wordpress plugin for stable super-peer nodes that can be used to bootstrap WebRTC clients
  * These are also nodes in the overlay ... they also maintain an index and respond to queries using same protocol as normal nodes
