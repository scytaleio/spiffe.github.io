---
layout: community
group: 'navigation'
title: SPIFFE
bodyclass: Community
headline: 'SPIFFE'
type: markdown
---

# About

**SPIFFE (Secure Production Identity Framework For Everyone) is an
open-source framework that aims to provide a secure identity (and
a means to prove that identity) to every workload in a modern
production environment, no matter where it is running.**

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

The SPIFFE project will provide both a *specification* for, and
open-source *reference implementation* of a framework for bootstraping
and issuing identity to services accross a heterogeneous hosting
environment.

#### **Flexible bootstrap.**

Identity is about trust, and that trust must be bootstrapped. The
system should support multiple mechanisms as they make sense,
including hooking into hardware security mechanisms (such as <a
href="https://en.wikipedia.org/wiki/Trusted_Platform_Module"
target="_blank">trusted platform modules (TPMs)</a>).

#### **Easy to use.**

Cryptography is difficult to use and even more difficult to use
correctly. SPIFFE will provide automated, API-driven mechanisms for
automatically issuing, verifying, and rotating identity documents.

#### **Broad integration.**

The more frameworks and tools that build in support for SPIFFE, the
more useful it will be. Built-in support in RPC/micro-service
frameworks, storage systems, and orchestrators will multiply its
usefulness.

#### **Reliable.**

The <a href="https://en.wikipedia.org/wiki/Single_point_of_failure"
target="_blank">single points of failure (SPOF)</a> in the system
will be minimized, and the system will degrade gracefully when any
SPOF is down.  All “steady state” operations should not have
requirements from a specific node.  This precludes any centralized
signing/verification service.

#### **Scoped trust roots.**

While <a href="https://en.wikipedia.org/wiki/Public_key_infrastructure"
target="_blank">public key infrastructure</a> may used as part of
the solution, there will be no hardcoded, global trust roots as we
see in the web browser world. Users must explicitly decide which
roots to trust for which identities. Typically, these roots will
be set per organization.

#### **Federatable.**

Identity mechansims can be used across organizations. However,
federation trust must be explicitly configured.  The nitty gritty
of how to establish this trust may be out of scope for the first
cut of these specifications.

#### **Legacy friendly.**

SPIFFE can be applied without re-writing applications or moving
them to a new management system. It will be possible to adapt this
system as separable infrastructure to secure existing systems with
little or no code change.

#### **Container friendly.**

The system should work well in dynamically orchestrated container
environments.

#### **Minimal knowledge.**

A compromised host will only expose secrets for workloads running only on that host.

SPIFFE allows organizations to employ more robust secuity tooling
by ensuring all running workloads within an organization are issued
an identity and the means to prove that identity to other running
workloads.

SPIFFE's initial release focuses on issuing <a
href="{{site.baseurl}}/docs/svid">SPIFFE Verifiable Identity Documents
(SVID)</a>. In practice SVIDs are specially-formatted <a
href="https://en.wikipedia.org/wiki/X.509" target="_blank">X.509</a>
leaf certificates that allow a workload to assert identity, and set
of root or intermediate certificates to allow for third-party
verification.

**Examples of how SVIDs can be used:**

* Enable two (2) workloads to establish a mTLS connection
* Provide PKI certificates to be consumed by service proxies such as Envoy, Linkerd, and nginx
* Provide PKI certificates to allow a service to communicate with a central secret store (such as HashiCorp Vault)
* Audit exactly what systems are running on which nodes in a production infrastructure

SPIFFE's specification and reference implementation are being
developed by engineers from organizations such as Docker, Dropbox,
Google, and Twillio. Read  more on <a href="{{site.baseurl}}/docs/">current
docs and designs</a>, and <a href="{{site.baseurl}}/community/">learn
how to get involved</a>.
