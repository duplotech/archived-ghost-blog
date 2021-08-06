---
title: How to TDD effectively
slug: how-to-tdd-effectively
date_published: 2012-05-13T10:38:00.000Z
date_updated: 2016-02-02T00:48:07.000Z
---

*To new readers of my blog. This article was written many years ago, and is no longer the entirety or core of what I believe. It remains here as a historical stepping stone to newer ideas.*

1. Understand the overall functional behaviour of the system you must implement. It’s sensible to understand this from the perspective of why (e.g. a customer’s need fulfilment). These behaviours are often represented as user stories or business requirements and are the result of business-driven planning.  
2. Distinguish different behavioural domains as components and then define the scope of each of these. The scope of each component should describe the behaviour it must implement in a standardized format or ubiquitous language that is well-understood by everybody involved in the project (BDD). This is the result of joint business/technical planning.  
3. Ensure that larger components are broken into more manageable sub-components that are simpler to reason about. This is the result of technical planning.  
4. As a developer, start at the smallest component and for each: 

1. Carefully create a public interface [0]. Plan how to test each of these public methods [1] by writing documentation that explicitly describes each method’s usage and behaviour (defined at this point as: expected or unexpected responses) [2]. These are the things which you should think of:

1. What customer needs related to this were expressed in the ubiquitous language earlier?
2. How can it be used?
3. What behaviour does it provide?
4. What responses can it respond with and when?
5. What exceptions can be raised as a result of calling it and when?
6. What usage-behaviour mapping needs to exist for this behaviour to be represented and then tested?

2. Create tests for the interface previously created based on the documented behaviour, usage, responses, and errors. Until the methods of an interface are successfully implemented their tests will fail (TDD).
3. Implement the interfaces methods until they pass. (If an implementation requires growing the list of public methods contained by an interface then repeat the test planning process [3] for each of these.)
4. Check that business needs have been met as a result of the process.

[0] It’s worth noting that when I say “interface” I mean this in a generalised form. I mean the way of interacting with the component. I do not mean a particular programming language’s “Interface” language construct.

[1] We do not test private methods as they are implementation related and suspect to change often. However encapsulation is contextual. A public interface may be provided to other components in a system, yet there may be an underlying API that is private to external systems, but should be considered public to the components built on top of it — and therefore tested.

[2] In Python it is possible to do this using the [doctest](http://docs.python.org/library/doctest.html) module.

[3] ALWAYS use common sense.
