---
bodyclass: docs
headline: SPIFFE VSID
layout: docs
title: SPIFFE VSID
type: markdown
---

SPIFFE describes both a API specification for and a reference implementation of a software framework for issuing identities to workloads. A part of the SPIFFE specification must necessarily include (a) an agreed format for naming identities (the “SPIFFE name”), and (b) is a set of documents that may be issued by the SPIFFE framework that can subsequently be used by two independently hosted workloads to mutually verify each other’s identity without a third party. 

These are defined together as the “SPIFFE Verifiable Service Identity Document” (VSID) specification. In practice, the VSID specification describes how SPIFFE names are to be constructed and a specific subset of the X.509 (RFC 5280) specification that should be followed in order to properly encode a SPIFFE name into an X.509 certificate. A system that implements the SPIFFE VSIDs according to this specification is considered a “SPIFFE VSID provider”.

A set of SPIFFE VSID providers should be able to pre-negotiate mutual trust ahead of time, such that identities issued by any such provider can be verified by workloads supported by any other trusted VSID provider. Thus the specification thus also describes the set of root certificates that should be made available to a workload to allow it to verify any VSID issued by a mutually trusted provider. The VSID specification does not yet cover how such mutual trust is established between providers.

From the perspective of a workload, VSIDs allows an unambiguous and best-practice process for verifying the identity of another workload (even when at identity is issued by a different but trusted provider) that can be easily implemented by many existing PKI libraries and tools.

It should be noted that the VSID specification does not reason directly about how two services might exchange these documents (for example, as part of an mTLS handshake).

The SPIFFE VSID specification is published under active development but [published here](https://docs.google.com/document/d/1kP4Vm0_AJ4ZXPtmKH_nQNtvdydiKNDyX05gXM6fOHV0/view).