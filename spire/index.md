---
layout: community
group: 'navigation'
title: SPIRE
bodyclass: Community
headline: 'SPIRE'
type: markdown
---

# SPIRE

**NOTE:** SPIRE is still in its early implementation stages and not yet
ready for production deployment - you can help out by [contributing.](/community)

SPIRE (the SPIFFE Runtime Environment) is a software system that
exposes an API (the SPIFFE Workload API) to other running software
systems (workloads) so they can retrieve their identity, as well
as documents (SVIDs) to prove it to other workloads, at run-time.
This proof of identity can then be used as the primary authentication
mechanism for a workload when access other systems.

In similar fashion to the AWS EC2 Instance Metadata API, and the
Google GCE Instance Metadata API, the Workload API does not require
that a calling workload have any a priori knowledge of it’s own
identity, or possess any authentication token when calling the API.
This avoids the need to co-deploy any authentication secrets with
the workload.

Unlike these APIs however, the API exposed by SPIRE can (a) run on
and across multiple platforms, and (b) can identify running services
at a process level as well as a kernel level - making it suitable
for use with container schedulers such as Kubernetes.

In order to minimise exposure from a key being leaked or compromised,
all private keys (and corresponding certificates) are short lived,
rotated frequently and automatically. Workloads can request new
keys and trust bundles from the Workload API before the corresponding
key(s) expire.

Concretely, the workload API allows a workload to retrieve the following:
* Its identity, described as a SPIFFE ID.
* A private key tied to that ID that can be used to sign data on
  behalf of the workload.
* A corresponding X.509 certificate is also created, the X509-SVID.
  This can be used to establish mTLS, sign a JWT token, or otherwise
  authenticate to other workloads.
* A set of certificates that can be used by the workload to verify
  the identity of other workloads (a trust bundle.)

SPIRE consists of two components, an agent and a server.

The **server** provides a central registry of SPIFFE IDs, and the
attestation policies that describe which workloads are entitled to
assume those identities. Attestation policies describe the properties
that the workload must exhibit in order to be assigned an identity,
and are typically described as a mix of process attributes (such
as a Linux UID) and infrastructure attributes (such as running in
a VM that has a particular EC2 label).

The **agent** runs on any machine (or, more formally, any kernel) and
exposes the local workload API to any process that needs to retrieve
a SPIFFE ID, key, or trust bundle. On \*nix systems, the Workload
API is exposed locally through a Unix Domain Socket. By verifying
the attributes of a calling workload, the workload API avoids
requiring the workload to supply a secret to authenticate.

When the agent is started, it will connect to and authenticate with
a server. The server will verify the infrastructure the agent is
running on, a process called node attestation. SPIRE supports
multiple node attestation strategies depending the infrastructure
an agent is running on. Where possible, SPIRE encourages using
trusted mechanisms made available by the platform itself to verify
a node, such as the AWS Instance Identity Document or GCE Signed
Instance Metadata.

Following node attestation, the server will review the registry of
attestation policies and return to the agent a list of any SPIFFE
IDs that the agent is entitled to issue. When a workload process
calls the local Workload API, the agent will verify if that process
matches any of the attestation policies it was issued.

## SPIRE Resources

* [SPIRE Getting Started Guide](https://spiffe.netlify.com/spire/getting-started/)
* [The SPIRE repository on GitHub](https://github.com/spiffe/spire)
* [The original SRI (now SPIRE) design document](https://docs.google.com/document/d/1RZnBfj8I5xs8Yi_BPEKBRp0K3UnIJYTDg_31rfTt4j8)
