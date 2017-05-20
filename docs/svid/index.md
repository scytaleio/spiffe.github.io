---
bodyclass: docs
headline: SPIFFE SVID
layout: docs
title: SPIFFE SVID
type: markdown
---
SPIFFE describes both a API specification for and a reference implementation of a software framework for issuing identities to workloads. A part of the SPIFFE specification must necessarily include (a) an agreed format for naming identities (the “SPIFFE name”), and (b) is a set of documents that may be issued by the SPIFFE framework that can subsequently be used by two independently hosted workloads to mutually verify each other’s identity without a third party. 

These are defined together as the “SPIFFE Verifiable Identity Document” (SVID) specification. In practice, the SVID specification describes how SPIFFE names are to be constructed and a specific subset of the X.509 (RFC 5280) specification that should be followed in order to properly encode a SPIFFE name into an X.509 certificate. A system that implements the SPIFFE SVIDs according to this specification is considered a “SPIFFE SVID provider”.

A set of SPIFFE SVID providers should be able to pre-negotiate mutual trust ahead of time, such that identities issued by any such provider can be verified by workloads supported by any other trusted SVID provider. Thus the specification thus also describes the set of root certificates that should be made available to a workload to allow it to verify any SVID issued by a mutually trusted provider. The SVID specification does not yet cover how such mutual trust is established between providers.

From the perspective of a workload, SVIDs allows an unambiguous and best-practice process for verifying the identity of another workload (even when at identity is issued by a different but trusted provider) that can be easily implemented by many existing PKI libraries and tools.

It should be noted that the SVID specification does not reason directly about how two services might exchange these documents (for example, as part of an mTLS handshake).

The SPIFFE SVID specification is published under active development but [published here](https://github.com/spiffe/svid).