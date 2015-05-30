#Implementing PATCH for linked data

__Presenter:__ Rurik Thomas Greenall, Computas AS

__About the presenter(s):__ Rurik is a consultant and library technologist at Computas; he currently works at Oslo public library building a linked-data-based library platform.

__Intended audience:__ Software developers

__Abstract:__ It can be argued that HTTP-PATCH [1] is essential for read-write linked data; while this is the case — there is currently no clear-cut solution for this. Here, I present different alternatives for this and one implementation of HTTP-PATCH based on practical considerations from feature-driven development of a linked-data-based library platform at Oslo public library. 

I show how HTTP-PATCH can be implemented and used in everyday workflows and consider several aspects of specifications such as LD-PATCH [2], RDF-PATCH [3], particularly in light of existing efforts such as JSON-PATCH [4]. In the description of the implementation, I pay particular attention to the practical issues of using linked data in a REST-oriented architecture with hypermedia, formats that do not support hypermedia and blank nodes getting particular focus.

I provide some thoughts about how specifications like the linked data platform [5] can be reconciled with modern development techniques that largely shun specifications, and how we can create read-write interfaces for linked data.

[1] https://tools.ietf.org/html/rfc5789
[2] http://www.w3.org/TR/2014/WD-ldpatch-20140918/
[3] http://afs.github.io/rdf-patch/
[4] https://tools.ietf.org/html/rfc6902
[5] http://www.w3.org/TR/ldp/