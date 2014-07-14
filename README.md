H-Factor Hypermedia Client (Draft)
==================================
A simple Hypermedia client based on Mike Amundsens H-Factor. 

The H-Factor describes the global lexical categories (LE, LO, etc.) in a similar way natural languages do (nouns, verbs, articles, etc.)

Media types form a subset of the H-Factor. Again similar to natural languages that have a subset of lexical categories (e.g. some languages don't have articles).

By mapping each media type to the H-Factor ("normalization") a client only needs to understand and implement the lexical categories:

1. The client GET’s a resource;


2.The API returns a representation in format X and links telling where to find a format X to H-factor convertor for reading the structure;


3.The client downloads the parser in a sandboxed environment and uses it to convert format X to the H-factor;


4. Next the client can do whatever it wants. Build a presentation using the H-factor representation, convert it to another media type that allows to be read directly in a browser (control), etc.

when an API defines a media type (domain specific, generic, it doesn’t matter), the only thing it needs is a H-Factor mapping. This could be done by providing a link to some code-on-demand resource, but while writing this, maybe it can be even done using ALPS? Only instead of describing application semantics, it would require describing structure semantics…

