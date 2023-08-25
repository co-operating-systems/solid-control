# Example Access Control Rules and Reasoning

This Milestone documents interesting access control use cases for Solid. The aim is to see how these rules could be written out as an extension to [Solid WAC](https://solidproject.org/TR/wac), and the reasoning that would be needed by a client to work out if it can access a resource according to those rules and a guard to verify a proof sent to it. 

The use cases are all decentralised ones involving linked data, which is how this project differs from attempts to resolve this problem previously.
At the same time, the idea is to extend well-known access control logics to the Web, and to test those against the use cases.

The aim is also to use these to develop mini test-cases that we can then deploy on the solid server to test the Wallet.

I put together [a repository](https://github.com/co-operating-systems/PhD/) collecting both 
* information about the Access Control Logics for decentralised systems
* a set of use cases to test those Access Control Logics

The research led me to start working more closely with the [N3 Community Group](https://github.com/w3c/N3/), the [RDF Surfaces CG](https://github.com/w3c-cg/rdfsurfaces) and the [W3C Verifiable Credentials](https://github.com/w3c/vc-data-model/).


## 1. Logics

This section collects research on Logics for access control. The main logic is the "says" logic developed by Abadi, Needham, Burrows in the 1990s with some very interesting updates in 2009 by Deepak Garg. Furthermore in 2009 Dan Connolly also worked on mapping these to N3 at the W3C TAG. See [discussion in N3 issue 203](https://github.com/w3c/N3/issues/203), which lead to me writing up an argument on ACLsDont.

  * [RelBac](https://github.com/co-operating-systems/PhD/blob/main/Logic/RelBac.md) - a description logic for access control based on simple relations
  * [Says](https://github.com/co-operating-systems/PhD/blob/main/Logic/Says.md) - the basic modal logics of "Saying that" started in the early 1990s by Burrows, Abadi, Needham, Garg and others. 
  * [ACL](https://github.com/co-operating-systems/PhD/blob/main/Logic/ACL.md) - from Access Control Lists to Access Control Logics
  * [ACLsDon't](https://github.com/co-operating-systems/PhD/blob/main/Logic/ACLsDont.md) - an analysis of the argument against ACLs and in favor of capabilities. 
  I argue that the proof objects of AC Logic are the capabilities, and that can help understand the Confused Deputy Problem. 
  * [Verifiable Credentials](https://github.com/co-operating-systems/PhD/blob/main/Logic/VerifiableCredentials.md) - a description of the Verifiable Credentials Data Model, mapping the JsonLD examples to N3, and drawing them out as graphs, to make it clear who is saying what about whom. 
  Doing that led to [VC Data Model issue 1248](https://github.com/w3c/vc-data-model/issues/1248) where I argue that the model is placing the signature in a context whereas it should be placing the claim in the graph context. This makes the signature useless, as soon as the graph is merged with another one [as explained in my 3rd comment](https://github.com/w3c/vc-data-model/issues/1248#issuecomment-1691411099). The VC community is working on the VC Data Model and Vocabulary 2.0, so there is a chance to fix this for the next version.


## 2. Use Cases 

In this section, we explore important use cases of access control for Solid, and the type of reasoning that would be needed on the client and on the server for those to succeed. The idea is to see if one can think of intuitive reasoning strategies for individual cases, and then to see if there is a way to generalize those, by applying the says logic of the previous section. The use cases need not all be implemented immediately but are meant to push the design requirements as far as possible so that we can then choose the best logic and reasoning strategy for our needs.

A strong intuition of mine is that all interesting Access Control Use cases can be done by extending [Web Access Control](https://github.com/co-operating-systems/PhD/blob/main/) spec used by Solid (WAC+). 
This has the advantage that at its core WAC is very simple, so it is easy to reason about.
A few years ago we started on [a comparison with ACP](https://github.com/solid/authorization-panel/blob/ba23d0f1ebbc91b3f0c41306f44fd9cb84148615/proposals/evaluation/index.md), and this was looking good for WAC+.


* [Basic](https://github.com/co-operating-systems/PhD/blob/main/UseCases/Basic.md) looks at the basic authentication use cases using a public key and then extending it to a WebId to make it easier to maintain access control rules
* [Foaf](https://github.com/co-operating-systems/PhD/blob/main/UseCases/Foaf.md) explores the important social networking use cases that launched interest in this whole enterprise to start with. 
  We look at a simple friend network, followed by a friend of a friend of a friend. 
  This last one brings up an unavoidable scale problem: assume each person has 100 non-overlapping friends, we would end up creating a social network 100*100*100=1 000 000=1 million people large
* [Client Auth](https://github.com/co-operating-systems/PhD/blob/main/UseCases/ClientAuth.md) looks at the problem of limiting Apps.
   We distinguish two types of limitations from the client side and the server side. 
   We show how these map to ABNL logic.
* [Delegation](https://github.com/co-operating-systems/PhD/blob/main/UseCases/Delegation.md) looks at Delegation use cases
* [Deepak Garg's Phd](https://github.com/co-operating-systems/PhD/blob/main/UseCases/DeepakGargPhd.md) Deepak Garg's 2009 PhD built a detailed extension of the says logic for access control purposes with full proof-procedures. We want to see how far we can adapt those to the Web.
* [Verifiable Credentials](https://github.com/co-operating-systems/PhD/blob/main/UseCases/VerifiableCredentials.md) looks at how one can use W3C Verifiable Credentials standards for access control
* [WoN.md](https://github.com/co-operating-systems/PhD/blob/main/UseCases/WoN.md) the certificate-based examples will often require a Web of Nations infrastructure. We look at examples of these.

This will be ongoing work as the project proceeds and for the Ph.D.
