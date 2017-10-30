---
layout: community
group: 'navigation'
title: SPIFFE
bodyclass: Community
headline: 'SPIFFE'
type: markdown
---

# SPIFFE

Distributed design patterns and practices such as microservices,
container orchestrators, and cloud computing have led to production
environments that are increasingly dynamic and heterogenous.
Conventional security practices (such as network policies that only
allow traffic between particular IP addresses) struggle to scale
under this complexity. A first-class identity framework for workloads
in an organization becomes necessary.

Further, modern developers are expected to understand and play a
role in how applications are deployed and managed in production
environments. Operations teams require deeper visibility into the
applications they are managing. As we move to a more evolved security
stance, we must offer better tools to both teams so they can play
an active role in building secure, distributed applications.

The  Secure Production Identity Framework For Everyone (SPIFFE)
standard provides a specification for a framework capable of
bootstrapping and issuing identity to services across heterogeneous
environments and organizational boundaries. At its heart, SPIFFE
is:

* A standard defining how services identify themselves to each
  other. These are called SPIFFE IDs and are implemented as Uniform
  Resource Identifiers (URIs).

* A standard for encoding SPIFFE IDs
  in a cryptographically-verifiable document called a SPIFFE
  Verifiable Identity Document or SVIDs.

* An API specification for issuing and/or
  retrieving SVIDs. This is the Workload API.

## SPIFFE Standards

* [Secure Production Infrastructure Framework for Everyone (SPIFFE)](https://github.com/spiffe/spiffe/blob/master/standards/SPIFFE.md)
* [The SPIFFE Identity and Verifiable Identity Document](https://github.com/spiffe/spiffe/blob/master/standards/SPIFFE-ID.md)
* [The X.509 SPIFFE Verifiable Identity Document](https://github.com/spiffe/spiffe/blob/master/standards/X509-SVID.md)
* The Workload API (TBD)

