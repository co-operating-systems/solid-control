# Example Access Control Rules and Reasoning

This Milestone aims to document real access control use cases and the reasoning that would be needed for those to be viable, and to test those against access control logics for decentralized systems that are the most likely to work.  The aim is also to use these to develop mini test-cases that we can then deploy on the solid server to test the Wallet.

I put together a repository collecting both 
* information about the Access Control Logics available to us 
* a set of use cases to test those access control logics

The research lead me to start working more closely with the [N3 Community Group](https://github.com/w3c/N3/) and the [RDF Surfaces CG](https://github.com/w3c-cg/rdfsurfaces).  


## 1. Logics

This section collects research on Logics for access control. The main logic is the "says" logic developed by Abadi, Needham, Burrows in the 1990s with some very interesting updates in 2009 by Deepak Garg. Furthermore in 2009 Dan Connolly also worked on mapping these to N3 at the W3C TAG. See [discussion in N3 issue 203](https://github.com/w3c/N3/issues/203), which lead to me writing up an argument on ACLsDont.

  * [RelBac](https://github.com/co-operating-systems/PhD/blob/main/Logic/RelBac.md) - a description logic for access control based on simple relations
  * [Says](https://github.com/co-operating-systems/PhD/blob/main/Logic/Says.md) - the basic modal logics of "Saying that" started in the early 1990s by Burrows, Abadi, Needham, Garg and others. 
  * [ACL](https://github.com/co-operating-systems/PhD/blob/main/Logic/ACL.md) - from Access Control Lists to Access Control Logics
  * [ACLsDon't](https://github.com/co-operating-systems/PhD/blob/main/Logic/ACLsDont.md) - an analysis of the argument against ACLs and in favor of capabilities. 
  I argue that the proof objects of AC Logic are the capabilities, and that can help understand the Confused Deputy Problem. 
  * [Verifiable Credentials](https://github.com/co-operating-systems/PhD/blob/main/Logic/VerifiableCredentials.md) - a description of the Verifiable Credentials Data Model.


## 2. Use Cases 

In this section, we explore important use cases of access control for Solid, and the type of reasoning that would be needed on the client and on the server for those to succeed. The idea is to see if one can think of intuitive reasoning strategies for individual cases, and then to see if there is a way to generalize those, by applying the logics of the previous section. The use cases need not all be implemented immediately, but are meant to push the design requirements as far as possible so that we can then choose the best logic and reasoning strategy for our needs.

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
