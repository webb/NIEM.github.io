---
  title: NIEM Conformance
  short: Conformance
  icon: fa-sitemap
  description: Learn about the details of conformance to the NIEM standard.
---

Conformance to NIEM is defined in terms of the artifacts used within the model.
The idea of NIEM Conformance derives from three principle concepts under the
NIEM standard: Conformance Targets, Domains, and Model Package Descriptions (MPDs).

{:.note}
> NIEM-conformance does not imply compliance. Compliance implies enforcement
> and the existence of an offiial certifcation process that verifies conformance
> or level of conformance. NIEM does not currently define compliance.

## Definition of NIEM Conformance

NIEM defines various classes of artifacts - those documents and packages
involved in the modeling, development, and implementation of an exchange - on
which normative design rules apply. These artifacts are called *Conformance
Targets*. It is important to note that the whole of NIEM Conformance can be
understood through a detailed knowledge of its various conformance targets;
but, it is constructive to learn conformance as a schematic process of
derivation from particular Conformance Targets to MPDs.

In the definition of conformance, Systems, tools, and databases cannot conform to NIEM.
Only schema documents document sets, instance documents, MPDs, and other artifacts
defined through a valid NIEM conformance target can conform to NIEM. Internal names, or
usage of data, within a given system have absolutely no impact on the determination of
NIEM-conformance. Conformance is only about:

- Conformance Targets
- Schema documents and other document types with named Conformance Targets
- Schema document sets as a collection of NIEM-conformant schema documents
- NIEM MPDs as a collection of metadata, documentation, and a packaging of NIEM-conformant schema document sets
- Exchange data encapsulated in instance documents derived from, and validated by, a NIEM-conformant MPD

An artifact is NIEM-conformant if and only if:

1. Has a named Conformance Target
2. Adheres to all design and structural rules applicable to its Conformance Target
3. References the namespaces of any NIEM components used in its definition

System, tools or databases may have capabilities designed to specifically support the
development of NIEM-conformant artifacts, but those systems art not, themselves,
NIEM-conformant. Such tools or systems are considered considered NIEM-aware or
NIEM-supporting.

{% comment %}
## Conformance Concepts

The following links detail the various conformance concepts defining a
holistic view of NIEM Conformance:

{% include icon-list.html links=page.links %}
{% endcomment %}