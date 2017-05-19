---
layout: docs
title: Overview
headline: 'Documentation'
bodyclass: docs
type: markdown
---
**The SPIFFE project is under active development, guided by a [community of design partners](/community/).**

This page provides an index to the various whitepapers and design documents that have been proposed by the SPIFFE community.

 - [SPIFFE Whitepaper](https://docs.google.com/document/d/1GjurNK2ROw4rXz-k-l68JtpGRkGj2fZcWqP6gksEriQ/edit#heading=h.pq1kki84bhak) Joe Beda's original proposal for SPIFFE, presented at GlueCon 2016. See also this [slide deck with speaker notes](http://slides.eightypercent.net/spiffe-intro/index.html#p1)
 - [The SPIFFE VSID specification](https://docs.google.com/document/d/1kP4Vm0_AJ4ZXPtmKH_nQNtvdydiKNDyX05gXM6fOHV0/edit) (May 2017, under active development) - a detailed specification for the [Verifiable Service Identity Document]({{site.baseurl}}/docs/vsid/), a combination of naming format, X.509 certificate format and set of trusted root bundles. This allows two bundles with a common trust root to securely identify each other.
 - [The SPIFFE Workload API specification](https://docs.google.com/document/d/1iGuvDYh2534rnepSTkcKYpjFBAq5JrXmq6qdAP-8vyA/edit) (May 2017, under active development) - a detailed specification that outlines what APIs must be made available to a workload to be considered “spiffe compatible”. The workload API includes the ability to provision SPIFFE VSIDs. This document is currently limited to SPIFFE's design partners, but will be published here once finalized.
 - [The SPIFFE Reference Implementation (SRI) design doc](https://docs.google.com/document/d/1RZnBfj8I5xs8Yi_BPEKBRp0K3UnIJYTDg_31rfTt4j8/edit) (March 2017, under active development) - a detailed design doc for an open source software stack that allows for provisioning and managing SPIFFE identities across a range of platforms. The SRI implements the SPIFFE workload API specification. This document is currently limited to SPIFFE's design partners, but will be published here once finalized.