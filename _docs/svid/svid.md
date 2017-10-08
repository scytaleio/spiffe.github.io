---
title: SVID
permalink: /docs/svid/
---
SPIFFE describes both an API specification for, and a reference implementation of a software framework for issuing identities to workloads. The specification must include (a) an agreed-upon format for naming identities (the “SPIFFE name”), and (b) a SPIFFE-issued document set that can subsequently be used by two (2) independently hosted workloads to mutually verify each other’s identity without a third party.

These are defined together as the “SPIFFE Verifiable Identity Document” (SVID) specification. In practice, the SVID specification describes 1) how SPIFFE names are to be constructed; and 2) a strict subset of the X.509 (RFC 5280) specification that should be used to properly encode a SPIFFE name into an X.509 certificate. A system that accordingly implements SVIDs is considered an “SVID provider.”

A set of SVID providers should be able to pre-negotiate mutual trust ahead of time, such that identities issued by any such provider can be verified by workloads supported by any other trusted SVID provider. Thus, the specification also describes the set of root certificates that should be made available to a workload to allow it to verify any SVID issued by a mutually trusted provider. The SVID specification does not yet detail how such mutual trust is established amongst providers.

From the workload's perspective, SVIDs allows an unambiguous and best-practice process for verifying the identity of another workload (even when an identity is issued by a different but trusted provider) that can be easily implemented by many existing PKI libraries and tools.

It should be noted that the SVID specification does not reason directly about how two (2) services might exchange these documents (for example, as part of an mTLS handshake).

While under active development, the SPIFFE SVID specification is [published here](https://github.com/spiffe/spiffe/tree/master/standards).
