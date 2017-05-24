---
layout: docs
title: Overview
headline: 'Documentation'
bodyclass: docs
type: markdown
---
The SPIFFE project is under active development, and is guided by a select [community]({{site.baseurl}}/community/) of developers who are currently facing the challenges SPIFFE attempts to tackle.

This page provides an index to various documents that have been proposed by these developers.

 - The [SPIFFE whitepaper](https://docs.google.com/document/d/1GjurNK2ROw4rXz-k-l68JtpGRkGj2fZcWqP6gksEriQ) is SPIFFE's original proposal, as first presented at [GlueCon 2016](http://gluecon.com).
     - **_(March 2016, not under active development)_**
     
 - The [SPIFFE VID (SVID)](https://github.com/spiffe/svid) is a detailed specification for the [SPIFFE Verifiable Identity Document]({{site.baseurl}}/docs/vsid/), which itself is a combination of naming format, X.509 certificate format, and set of trusted root bundles. This allows two (2) bundles with a common trust root to securely identify each other.
     - **_(May 2017, under active development)_**
     
- The [SPIFFE Workload API](https://docs.google.com/document/d/1iGuvDYh2534rnepSTkcKYpjFBAq5JrXmq6qdAP-8vyA) specification outlines the APIs that must be made available to a workload to be considered “SPIFFE-compatible.” The workload API includes the ability to provision SPIFFE SVIDs.
    - **_(May 2017, under active development, design-partner access only)_**
    
- The [SPIFFE Reference Implementation (SRI)](https://docs.google.com/document/d/1RZnBfj8I5xs8Yi_BPEKBRp0K3UnIJYTDg_31rfTt4j8) details an open-source software stack that allows for provisioning and managing SPIFFE identities across varying platforms. The SRI implements the SPIFFE Workload API.
    - **_March 2017; under active development, design-partner access only)_**

