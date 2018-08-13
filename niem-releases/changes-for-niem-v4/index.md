---
title: Changes for NIEM v4
description: What was changed in the NIEM technical architecture from NIEM version 3 to version 4.
---

# NIEM v4.0 NDR

## page 1

* Updated version from 3.0 to 4.0, affecting:
  * Namespaces: structures, appinfo, NDR functions namespace
  * Conformance target identifiers: REF, EXT
* Now pointing to GitHub for:
  * Revisions/updates/errata: posted to the document repository
  * Comments/issues: posted as GitHub issues
* Grammar, spelling, and narrative improvements
* Moved content of the *Local Terminology* namespace (`term`) into the *Application Information* namespace (`appinfo`)
* Explicitly allow structures namespace to be subset

## page 2

* NDR Section 2.4.2 - Schematron updates
  * Eliminated warning rules (sch:report) that always fire
  * Added attribute (role="warning") to warning rules
  * Broke apart overly-large rule on standard opening phrases into smaller rules
* NDR Section 12 - Linked data approach
  * Added attribute structures:uri
  * Defined structures:id and structures:ref in terms of structures:uri (Appendix B)
  * Allow properties of objects to be distributed across multiple objects with the same identifier
    * Removed requirement that elements with structures:ref have no properties
  * Major rewrite to section 12.1, 12.2, addressing data's meaning, identity, and references

## page 3

* NDR Section 5 - RDF updates 
  * Simplified RDF representation
    * RDF is much simpler than v3, with direct properties instead of reification
    * Allows for more direct JSON representation via JSON-LD
  * Removed RDF representation for metadata types
* NDR Section 6 & 8 - XML processing and defaults (USMTF)
  * Improved discussion of infoset augmentation, fixed, and default
  * Allow use of fixed on attribute uses that are required in an instance
* NDR Section 10 & 11 - Naming
  * Relaxed rules on component naming from MUST to SHOULD (USMTF)
  * Allow all valid ASCII characters in component names
    * Allowed: "A"-"Z", "a"-"z", "0"-"9", "-", "_", "."

## page 4

* Codes
  * Updated NIEM Code Lists Specification for v4
    * Code lists may be managed via XML (Genericode) or spreadsheets/databases (CSV)
    * Code lists may be versioned separately from XML Schema-based vocabularies
    * Code lists may be identified at run time or at schema assembly time
    * Allow for more complex use cases
  * NDR Section 10 & 11:  Allow code elements and code types to be represented by methods other than enumerations
    * Described as correspondence to a list of conceptual entities
    * Relaxed rules for structure/content of code elements and types
    * Relaxed naming rules for code elements and types
