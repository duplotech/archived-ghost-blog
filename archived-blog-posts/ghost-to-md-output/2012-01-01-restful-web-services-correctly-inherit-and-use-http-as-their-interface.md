---
title: RESTful Web Services correctly inherit and use HTTP as their interface
slug: restful-web-services-correctly-inherit-and-use-http-as-their-interface
date_published: 2012-01-01T09:32:00.000Z
date_updated: 2016-02-02T00:50:08.000Z
---

*To new readers of my blog. This article was written many years ago, and is no longer the entirety or core of what I believe. It remains here as a historical stepping stone to newer ideas.*

There’s been a lot of buzz on RESTful Web Services [1] and yet there are still far too many developers that believe they may implement it by simply using a Rest class provided by their favourite framework.

I wonder if this has been helped by the obtuse or long-winded articles that are out there on the web and so here is my attempt at explaining the concept as concisely as possible:

Building a RESTful web service requires that you stop building the same concepts that already exist in HTTP as part of your API and instead build a uniform API [2] that inherits the HTTP Interface [3] by (a.) treating URLs as resources, (b.) implementing CRUD using the HTTP methods POST, GET, PUT, and DELETE; and additionally using POST for operations with side-effects such as financial transactions, (c.) using the HTTP response codes and header data correctly, and by (d.) identifying and interconnecting resources by URIs in the responses, hence being hypertext-driven (HATEOAS).

[1] [http://roy.gbiv.com/untangled/tag/rest](http://roy.gbiv.com/untangled/tag/rest)

[2] [http://news.ycombinator.com/item?id=2796371](http://news.ycombinator.com/item?id=2796371)

[3] [http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)
