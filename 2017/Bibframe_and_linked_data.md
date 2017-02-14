#BIBRFAME and linked data in bibliographic description 

#The aims of Bibframe
>- "…provides a foundation for the future of bibliographic description…"
>- "…a replacement for MARC…"
>- "…serves as a general model for expressing and >connecting bibliographic data…"
>- "… preserving a robust data exchange that has supported resource sharing and cataloging cost savings in recent decades…"
>
>From [https://www.loc.gov/bibframe/]

Bibframe is ambitious in its aims; it aims to provide *a foundation for the future of bibliographic description*, which is a grand aim in and of itself. Because it's a big thing, we'll jump over it in order to come back to it towards the end.

On face value, to create a MARC replacement, we need something that encodes data so that it can be exchanged between systems. This sounds simple enough. Reality is different.

MARC, [ISO 2709](###Link), allows bibliographic data to be represented as strings in various fields/indicators, using special characters in special positions. To understand MARC, you need to understand MARC. This isn't hard, MARC is actually technically easy and relatively smart. You can do a lot with MARC, even if very few actually do [reference]().

The question we need to ask is "Do we need a replacement for MARC?" & the answer should be "No". A MARC-replacement is unnecessary because MARC is absolutely fit for purpose — if the purpose is what MARC is designed to do, exchange data between systems that understand MARC. Whether the system is something that prints catalogue cards or a library management system should be irrelevant.

But, why does replacing MARC seem like a pressing concern? Typically, MARC is the only format a library management system can provide via its APIs and MARC is largely awful to work with unless you want a self-contained whistles-and-bells record designed for data exchange. So, if you want a representation of the title of a book and its authors, the data needs to be processed in a way that most API users aren't used to.

The issue runs deeper too; MARC (ISO 2709) is a serialisation, but it seems entwined with the the data because there is a very tight coupling between the the cataloguing rules and the data format. Cataloguing is typically done with absolute reference to fields in MARC; librarians — even the non-cataloguers — can easily run off a number of commonly used fields (100$a, 245$a, 691$a, etc.) and know that these mean something. In fact, MARC is so ingrained in cataloguing workflows that the job of bibliographic description is largely knowing MARC and cataloguing rules.

Deeper still, because of MARC's ingrained nature, even new library management systems have a physical data model that looks a lot like MARC. They may even have MARC stored as queryable data — in the form of MARCXML — in their database; this poses two questions: what is it about bibliographic data that is so difficult to align with relational databases and why would one use a data exchange format as a physical model?

The majority of data exchange protocols for bibliographic data — OAI, Z39.50, SRU — presume MARC — in the cases where it doesn't, the data is generated from some MARC-informed format that makes the auxiliary format MARC-ish. 

But MARC can live quite happily alongside another format designed for these new tasks. Legacy support should be the first to go.

You'll note that #Bibframe attempts to make explicit that which is implicit in MARC; entities like "Work", "Creator"

Where MARC puts these things with fields/indicators that a trained human can understand, #Bibframe makes them things in their own right

As I understand it, MARC is a syntax, more akin to a particular serialisation of RDF than to #bibframe, however, this doesn't feel quite right as MARC has multiple serialisations (ISO 2709 and MARCXML); MARC is a standard, ISO 2709, which defines the syntax and encoding of bibliographic data. MARCXML is simply a re-encoding of this. The "feeling" that MARC is more than this comes from the tight coupling between the MARC and rules for cataloguing, how we record data.

Experience from multiple projects aiming to convert MARC to other formats informs us that strings are bad representations for things. Identifiers are great, but library data is largely composed of strings or system-internal identifiers (and even these are only applied ad hoc).

While moving from MARC to RDF is simple, moving from MARC to something that works as RDF is a lot harder. The naïve approach to MARC-to-RDF conversion is characterised by properties, while an approach that more useable in real-world semantic architectures is characterised by classes. The latter is many times harder and is not, on the whole, do-able using standard mapping techniques. In fact, it seems it is moderately do-able using machines, but actually requires humans to fix the many, many edge cases.

Typically, BIBFRAME will have to represent data in a way that is useable in a MARC-oriented context, because the majority of systems will not use BIBFRAME as a core model, but simply convert existing MARC-oriented physical implementations to BIBFRAME. This maybe sounds fine until one considers that MARC is very stringy and bad RDF is also very stringy. It isn't simple mapping that is needed, it is more work than can be done by a machine to make sense of badly structured, human-oriented information — irrespective of the state of AI.

This sounds negative, but it should be a wake-up call. We're pretending that there is value in creating yet another format because it is intrinsically better. It isn't. In fact, it is less good than MARC because the usage of Bibframe isn't solidified with decades of practice (although, as Lukas Koster rightly pointed out, even this is so variable that MARC simply isn't very useable as a data exchange format). 

Making data more available is one common claim made for using linked data, but this smacks of library systems simply having bad APIs (which they do because we largely don't use these for anything except shuffling *records*). The fact is that a lot of the ambitious aims of Bibframe ignore the simple fact that it is more work to create richer data, the data doesn't and cannot exist given the current data. This is the case from experience, not theoretical assumption or naïve experimentation.

We also ignore the fact that linked data is harder to use than existing formats because of the data structure; triples, while simple structures, represent graphs which are not simple to work with using commonly known techniques. As I have said before, speed is always an issue in linked data and this is often because developers struggle to work with graphs. This is as true of "experts" who have worked with RDF since its inception to "experts" who claim database chops, but do not understand RDF. The proof, as always, is in the eating — if the system is slow, don't believe the programmer.

Maybe what you need is either better programmers or to create an API on MARC that does something better than spewing out MARC records.

Bibframe's aim to create a *…a general model for expressing and connecting bibliographic data…* is easier to understand as — simply by virtue of using linked data — it does this automatically. However, is another general model for bibliographic data really what we need? There are so many competing models! Each has its own use, but again, these seem to be wise choices for interoperability, but not as a physical model for an application. The ontology is a domain specification for an application; this isn't what Bibframe is aiming for — it has a higher, more complex aim, and not one we need necessarily in our systems.

This ties back into the aim to provide *a foundation for the future of bibliographic description…*; it is here that Bibframe really hits something. Here Bibframe sounds uncannily like FRBR, and should Bibframe want to avoid the fate of FRBR — an idea, a conceptual framework, but not something anyone pays very much attention to in practice (and here, I'm talking about real-world implementations, not quasi-implementations or, again, naïve experimentation).

Because of all of these things, it seems to me that Bibframe should stick to its aim of replacing MARC as an exchange format, simply because this is the overcomable aim. It maybe isn't necessary, but it might be something we can get on-board with as a step in the right direction. Overly ambitious attempts in a conservative domain are alas doomed to fail.

This motivation for the project skews Bibframe to be something else, to structure the work that is being done very differently. We need the pragmatism that was seen in Dublin Core, we need API specifications and we need to know that the data is as good as MARC without added complexity. Creating entities is a good aim, but I'm not sure that MARC is a good enough starting point for all but the most simple cases. We don't need to spend time on this now, we need a framework that can grow and be adjusted over time.

For those of us who grew up on [five star linked data](https://www.w3.org/DesignIssues/LinkedData.html), Bibframe is anathema because it doesn't follow the principle of re-use. While I understand something of the motivation, when Bibframe was first announced, this felt like the collective knowledge of the community was ignored. This is a really good way to get people's backs up; the backlash came in some of Rob Sanderson's comments on Bibframe that circulated a few years back.

Building a monolithic ontology before anyone has any practical idea about implementation sounds like the dreaded big-design-up-front and too-early standardisation rolled into one. Which is a really bad idea from a programmer's perspective.

I'm convinced that there is a benefit to using linked data in bibliographic description — I see this every day in my work — but I see no benefit in slow movements through stringy systems to more stringy systems; you can simply take the leap now — you don't need to wait. There are already library systems that are entirely based on linked data for their bibliographic description. The lessons learned from these show is that a new paradigm of description is hard on those that catalogue and poses new challenges just as it presents opportunities. Bibframe is offers none of these now, but the systems I'm talking about can already supply Bibframe — but to what purpose? They can supply standard linked data, or Schema.org or whatever else we can imagine. But why Bibframe? Is it something we can all get behind as a standard ontology for data exchange, or do we need to use other vocabularies as well (as one typically does in linked data)?

I recently laughed a hard laugh when a colleague mentioned the Current format > MARC21 > RDA > Linked data upgrade path. Strings to strings to strings to *magic* linked data. This describes the common misunderstandings I have been talking about throughout this document. If libraries and vendors can't understand the foolishness of this kind of thinking, we should pack our bags.

On what authority do I say this? You've never heard of me! I have worked with linked data and RDF for a few years and have created a few linked data applications. Take a look at [Oslo public library's catalogue](https://sok.deichman.no/work/wf8220ce955f4853499f7f6117abfe159) which is a linked-data-only application I work on at time of writing (February 2017). 