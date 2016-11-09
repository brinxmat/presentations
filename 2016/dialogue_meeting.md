#About

I'm presenting a short response on behalf of my employer, Computas, at an RFI-type dialogue meeting here in Norway.

Three questions have been posed three questions:

- What will the library system of the future look like?
- What developments will occur in the next five-to-ten years?
- What are the benefits of choosing a collaborative system?

In order to understand the context of these questions, I think that it's important to understand some of the background to the questions in the specific case of Norway.

Most libraries in Norway use one of a handful of systems developed/adapted in Norway for local circumstances. These systems typically feature competent workflows adapted over the course of years to the situations libraries have found themselves in. Common business processes are embedded in these workflows, and these have through long-haul development and domain-related conceptualisations diverged from higher-level business processes developed in the institutions to which public libraries must answer. Examples of this are aquisitions processes that are disjoint to acquisitions processes in local government, which creates challenges in accounting and resource management.

National processes too have implications in the sector; using the local NORMARC dialect to facilitate distribution of metadata, integration in initiatives orchestrated by the National library, integration with common local government processes, and so on.

In many ways, Integrated library systems are clustered expert systems, combining multiple functions into one domain-capable package. Each new function is added — integration with new protocols (RFID, NCIP, …) — and more business logic is embedded into the system. This clustering creates some issues, especially in cases of conflicting interests (say, requirements for mercantile documentation of acquisitions contra descriptive metadata for acquired items) and modern development techniques which base themselves on modularisation and componentisation.

As is the case internationally, many of the systems we see today build on data models and integrations that pre-date the World wide web and support for any such functionality is not part of core architectures. This is becoming more apparent as the implications of relation-driven architectures are fully understood — even the simple mechanisms that the World wide web uses to relate documents are hard to implement in such systems, creating oft cited data silos.

A data silo need not be a bad thing, some data belongs together for business process reasons, however data should be available for use via application programming interfaces (APIs), where possible in standardised formats. The APIs should be available to the licensee for use and extension of these should be possible at a miminum via direct communication with the vendor. We have seen that such APIs are restricted to protocols and formats that are adequate for certain kinds of operations, but not integration with modern web applications. Furthermore, and perhaps more worryingly, restrictions have in the past been placed on usage rights to data from these APIs — not through any malicious action on the part of vendors, but in an attempt to protect performance in systems not specified for this kind of integration, to protect intellectual property interests in a hazy domain and often in plain legal misunderstanding of how, for example HTTP works in practice (here, I'm thinking specifically of forbidding caching of data).

Given this background, I can now look at what I consider the library system of the future to look like.

##What will the library system of the future look like?

The next generation of library systems should be intrinsically part of the Web; the architecture presents data for consumption by users whether they are humans or machines via web interfaces that function seamlessly with the rest of the web. The feeling a user gets is that there is no border between their point of entry, say Google or Yandex, and the system itself. Behaviour and performance of the application programming and user interfaces is equivalent to the expectations we have of every other kind of system — gone are multi-second wait times, gone are the mysterious incantations users need to interact with the interfaces.

This connectivity means that some of the functionality we see in systems today will be outside of the new system because interfaces allow business processes to be carried out in appropriate systems rather than forced together in one amorphous monolith. These integrations may come in the form of abstracted processes within a module or as an entirely external process that simply provides data back to the library processes that need them.

Of course, the game is already given away because the APIs mean that the system architecture will also differ greatly from current architectures in modularity and componentisation. Many commercial systems claim that they are modular in this way, and yet we see none in production that allow simple exchange of financial modules or acquisitions modules with alternatives from other vendors. But there is another reason for this kind of modularisation — performance. Modern system architectures are modularised for scalability; running multiple instances of a module when load is heavy and scaling back when the load is lighter. All of these things add up to modern architecture, which is not a slow monolith — easily identifiable by fact that it can be acquired and implemented as modules, its speed and its APIs.

We already see multiple open source alternatives that have gone live or are in development (LS.ext and Folio respectively) that demonstrably follow this pattern, and it's also clear that the way these services are provided will change; as software as a service or some other model, whereby scaling from the smallest institution to the largest will result in terms of service and remuneration for services rendered by way of extent of actual usage, not flat fees based on expected usage. Libraries may choose different suppliers for different processes and integrate these; they may choose to host something or everything themselves (in cloud based services or on local hardware).

Modern library systems can also be viewed in terms of the roadmap that they have regarding the coming features that customers want, changes in the way data is exchanged and coming web standards (before the standards are released); they can be judged by the maturity of the organisation behind the system; their openness and their ability to participate in web standards creation (not just library standards creation) and their willingness to implement these changes logically for customers independently of a product-release cycle, e.g. modern development.

The organisation behind library systems will likely change rapidly over time, as the insight that open source communities are of vastly greater importance than the software vendors that use open source software to create commercial products. Vendors are more likely to participate in open source where they have the opportunity and are not bound over by legal and shareholder concerns.

##What developments will occur in the next five-to-ten years?

The changes that come in the coming years can be viewed pessimistically as changes foisted upon libraries from outside — as things that add no value to systems in-and-of-themselves because they largely stand as requirements made in place of already existing and functional technology. Examples include the end of life of exchange formats that have been with us for many years in favour of a backwards-compatible MARC-in-RDF+JSON representation sponsored by OCLC and LoC. 

Additionally, requirements will come from local and national institutions that tend towards increased standardisation and decreased localisation; this trend can be seen in terms of the gradual disappearance of local MARC dialects in favour of MARC21 and AACR2 in favour of RDA. We already see a centralisation and standardisation of MARC-data provision from the National library and will likely be subject to requirements from local government that library systems provide data directly to municipal systems in addition to participating in standardised acquisitions/logistics processes and systems.

Viewing the same trends optimistically, we will see opportunities in moving away from copying data from one system to another, to one where data is shared using APIs among systems that have proper responsibility for maintaining the data and provide regular updates, removing the need for copying data between systems. It additionally means improved services for users, simpler management and better understanding of the needs of libraries and our users.

In terms of metadata, the current and obvious future is an exciting time; the idea of working with distributed data, where read/write bibliographic data is maintained by the National library in standardised formats, removing the necessity of wide-scale local clean-ups, giving cataloguers time to add real value to data that makes it possible to create innovative interfaces born of finding new relations between documents, people, places, events and topics.

In order for the optimistic outcome to happen, I believe that libraries have to sieze an active role in defining what needs to happen in which system and actively scoping the specification of the systems for their needs, rather than accepting a hodge-podge of library functions weighed down by absolutes set out by third parties with understanding of their domain, but nothing of libraries or their processes. An example here being acquisitions, where libraries have a need for identification on reciept that is not in place in traditional systems because libraries often base acquisitions on PDA.

We will see a move away from systems that store data in cousins of the MARC format; reflection around recent innovations in databases will make it possible to move on from the traditional limitations MARC-oriented systems have. This change will also allow technologists to properly assess what kinds of storage the data needs rather than assuming blankly that all data should be pressed into existing systesms. Another win for modularity. Another win for users. MARC may still be used, but as a convenience, an exchange format — its real intention.

We will see systems that treat non-monographs as first-class citizens because of the adoption of typed data and non-relational and schemaless storage; we will see an ability to search and present data in a way that is unlike flipping through pictures of a catalogue cards and is more like searching a well-structured card catalogue in milliseconds.

And all of this will be customisable because it is provided as modules with APIs. A standard package may be available, but this standard package is as likely to have been provided by an open source community, a service centre for a consortium as by a particular vendor.

##What are the benefits of choosing a collaborative system?

As I pointed out above, I'm already sure that the future is a collaborative system — one based on standards designed for collaboration, but what about specific collaborations?

Briefly, the benefits of collaboration are better interfaces for users, better data quality, more time for real service improvement and more traction in getting changes implemented. Undoubtedly, a consortium is stronger than a single library in terms of getting things developed or developing things themselves. A group of libraries with disparate resources pooled becomes a far bigger fish than when those same resources are not pooled. Pushing in the same direction for the benefit of users, having uniformity in the data or data model can only ever be a good thing.

The disadvantage can be that local colour has no place in collaborative systems based on traditional technologies and libraries can find themselves with multiple catalogues if they have, for example, special collections. Modern technologies provide solutions to these problems, but collaboration exacerbates them.

Collaborating nationally is a great idea, having a common read/write infrastructure for maintenance and delivery of metadata is the next big shift we really need to see. This is already underway at the National library and compatibility with current MARC-oriented systems is already in place as is — to some extent — compatibility with a modern RDF/linked data reality. But systems need to be able to make use of this data in a way that ensures that fresh updates are managed; simple import will not work, data must be systematically refreshed or be based on a technology that does this implicitly (like distributed linked data).

It seems desirable to have a collaboration regarding search technology related to metadata — this might be hosted nationally or in consortia dependent on the extent to which a national system can be all things to all people. It seems likely that smaller constellations delineated by public/academic roles will provide more fruitful collaboration as their needs are similar. 

Modifying existing systems to work together with a common catalogue (or discovery layer as it might be termed) is a possibility, here data quality is paramount, however, it makes sense to keep holdings and non-metadata processes outside the collaborative layer, even if holdings data is presented there. It also seems to make sense that collaborations among systems designed with modularity in mind could provide tighter integration even though the systems themselves were serviced by diverse providers. 

In reality, a collaboration in Norway among public libraries needs careful consideration — what needs *must* be serviced collaboratively; to what extent do libraries want to change to a modern system that they develop together (either with or without the help of a system provider); to what extent can we achieve the same benefits with adaptations to existing workflows and some layers on top from system providers such as the National library?

Choosing to implement a new system simply because it is multi-tenant does not necessarily provide any of the expected benefits — a view of what the reasons are for changing systems combined with knowing the expected outcome must inform any decision. There is a clear risk in the market that one simply carries over existing risks with no roadmap for moving forward.
