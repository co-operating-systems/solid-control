# Solid-Control and Solid Wallet

## Solid Control (2021-2022)

Solid-Control was a project funded by the European Union Next Generation Internet (NGI) Privacy and Trust Enhancing Technologies (PET) fund. From the [official nlnet page](https://nlnet.nl/project/SolidControl/):

> Solid-Control aims to enhance Tim Berners-Lee's Social Linked Data Project (Solid) with Attribute-Based Access Control. 

> By extending the Linked Data Platform (LDP) with WebID based authentication and Access Control Lists (ACL), Solid has enabled the emergence of new forms of Hyper-Apps. These apps can follow data from server to server, authenticate when needed and write to the user's Personal Online Data storage (Pod), creating a decentralized social web.

> With relation-based access control (friend of a friend, business network, etc.), Solid can be a full alternative to centralized social networks. We also want to allow authentication based on Verifiable Claims such as age. Solid-Control will work on developing the needed logic, verify protocols, write prototype implementations and contribute to the Solid Auth Community groups, which are developing specs for standardization.

The project interacts with several different repositories on GitHub and mailing lists. This repository collects the reports on the activity in the various forums.

## Solid Wallet (2022-2023)

Solid Wallet continues the Solid-Control project, and is funded by NGI Assure. From the [official nlnet page](https://nlnet.nl/project/SolidWallet/index.html):

> *Authorization reasoning, rule-based controls and fluid integration for Solid*

> Solid Apps display information collected by following linked data across the World Wide Web, writing changes to Solid Personal Online Data Stores (PODs). Following links can land an App on a protected resource somewhere on the Web, accessible only to a select group of actors specified in an associated Web Access Control Resource. Solid Wallet aims to build core libraries to reason over Solid Access Control Rules, limit access to what clients can request, publish keys and sign transactions. The same libraries will also be useable by servers to verify such claims. Finally, we will use these libraries to build a flexible prototype Wallet for Solid apps that run in the browser or server.


### Standards based work

The main repositories regarding standard-settings are:

* [Solid Authentication Panel](https://github.com/solid/authentication-panel) 
* [Solid Authorization Panel](https://github.com/solid/authorization-panel)
* [Solid Interoperatbility Panel](https://github.com/solid/data-interoperability-panel)
* [Solid Specification](https://github.com/solid/specification/)

Each milestone points to weekly reports from the panels.

###  Code repositories and artifacts 

Every code repository will produce artifacts stores as snapshots on Sonatype's maven servers
and after testing will be released to Maven Central. 

* [Reactive-Solid](https://github.com/co-operating-systems/Reactive-SoLiD) is the server implementation.
* [Banana-RDF](https://github.com/banana-rdf/banana-rdf) is an RDF library for Java and JavaScript in Scala. The Scala-3 branch is available directly at [bblfish/banana-rdf](https://github.com/bblfish/banana-rdf/). Artifacts are published in 
  * fir scala 2.13 and scala 3 in sonatype [net/bblfish/rdf](https://oss.sonatype.org/content/repositories/snapshots/net/bblfish/rdf/)
  * todo: publish final artifacts to Maven Central
  
Additional Code repositories that were created along the way as their final location is still to be decided:
 
* [bblfish/httpSig](https://github.com/bblfish/httpSig) repository for Scala(JS) implementation of IETF "Signing HTTP Messages". Artifacts published in
    * for Scala 3 on Sonatype [net/bblfish/crypto](https://oss.sonatype.org/content/repositories/snapshots/net/bblfish/crypto/)
    * todo: publish to maven central
* [bblfish/rdf-model-js](https://github.com/bblfish/rdf.scala.js) Scala JS facade for RDF.js interfaces. This is published as artifact [rdf-model-js](https://oss.sonatype.org/content/repositories/snapshots/net/bblfish/rdf/rdf-model-js_sjs1_3/)
* [bblfish/SolidCtrlApp](https://github.com/bblfish/SolidCtrlApp) client in browser Authentication libraries.
   * These are not yet published to sonatype or maven central

Other repositories being contributed to:
* [bblfish/bobcats](https://github.com/bblfish/bobcats) is a cryptographic library in Functional Scala(JS) that has forked the typelevel bobcats cryptographic repository. It is used by our implementation of IETF's "Signing HTTP Messages". Artifacts are published
    * for scala 2.12, 2.13, 3 on Sonatype in [net/bblfish/crypto](https://oss.sonatype.org/content/repositories/snapshots/net/bblfish/crypto/)
    * maven central (todo)

## Milestones 

### For Solid-Control

Reports for Milestones are available in the [milestones folder](milestones). 
The milestones are numbered after the original template, but were not always done in the estimated order.

 * 05 Jan - 21 Feb  2021 - [Milestone M1](milestones/M1/M1.md)
 * 22 Feb - 1 April 2021 - [Milestone M2](milestones/M2/M2.md)
 * 1 April - 11 June 2021 - [Milestone M3](milestones/M3/M3.md)
 * 12 June - 20 August 2021 - [Milestone M4](milestones/M4/M4.md)
 * 21 August 2021 - 21 Sept 2021 - [Milestone M6](milestones/M6/M6.md)
 * 21 Sept 2021 - 29 Oct 2021 - [Milestone M5](milestones/M5/M5.md)
 * 30 Oct 2021 - 22 Dec 2021 - [Milestone M7](milestones/M7/M7.md)
 * 23 Dec 2021 - 24 Jan 2022 - [Milestone M9](milestones/M9/M9.md)
 * 25 Jan 2022 - 28 Feb 2022 - [Milestone M10](milestones/M10/M10.md)
 * 1 March 2022 - 30 Oct 2022 - [Milestone M11](milestones/M11/M11.md)

### for Solid Wallet 

 * Nov 01 - Dec 30 2022 - [Milestone W1](milestones/W1/W1.md)
 * April 01 - June 6 2023 - [Milestone W2](milestones/W2/W2.md)
 * June 07 - August 24 2023 - [Milestone W3](milestones/W3/README.md)
