H-Factor Hypermedia Client (Draft)
==================================
A simple Hypermedia client based on Mike Amundsens H-Factor (http://amundsen.com/hypermedia/hfactor/). 

The H-Factor describes the global lexical categories (LE, LO, etc.) in a similar way natural languages do (nouns, verbs, articles, etc.)

Media types form a subset of the H-Factor. Again similar to natural languages that have a subset of lexical categories (e.g. some languages don't have articles).

By mapping each media type to the H-Factor ("normalization") a client only needs to understand and implement the lexical categories:

1. The client GET’s a resource;
2. The API returns a representation in format X and links telling where to find a format X to H-factor convertor for reading the structure;
3. The client downloads the parser in a sandboxed environment and uses it to convert format X to the H-factor;
4. Next the client can do whatever it wants. Build a presentation using the H-factor representation, convert it to another media type that allows to be read directly in a browser (control), etc.

When an API defines a media type (domain specific, generic, it doesn’t matter), the only thing it needs is a H-Factor mapping. This could be done by providing a link to some code-on-demand resource (or maybe even ALPS?). Only instead of describing application semantics, it would require describing structure semantics...

The demo is based on the code-on-demand approach and targets the Github API. It consists of three parts:

1. Github json converter (line 11-55), converts the json responses to H-factor. A lot of stuff is missing here of course, but it works for most links well enough to get the idea;
2. Client representation presentation (line 59-153), converts the H-Factor object to HTML;
3. Interface (line 156-172), the root uri and basic auth string, the data and H-Factor results.

Please use a base64 encoding on your Github username and password (<username>:<password>) when you’re starting to explore.

The demo is far from complete, but it should give insight in the general idea. For now it only supports LE, LO en LT. The LT still requires uri template parsing.
