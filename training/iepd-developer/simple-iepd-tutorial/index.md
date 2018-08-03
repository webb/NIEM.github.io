---
title: Simple IEPD Tutorial
icon: fa-envelope-o
description: This tutorial shows you how to create a very simple IEPD. Once you are comfortable with the process and output, you can move on to [more complex](/training/iepd-developer/) IEPDs.
---

{{ page.description}}

### In the Beginning

You observe a person who displays superhuman powers (a superhero). You want to inform others of this person's presence and unique characteristics.

### Scenario Planning

<!--
You review background information related to your information exchange, assess resource impact, understand business context, and identify information exchange business scenarios.

sources:
IEPD Tutorials from /iepd-starter-kit/iepd-tutorials/
Dropbox (GaTech)/NIEM-FA807514D0018-0018/training/2010-05-18-walmsley-creating-a-niem-2.1-iepd/2010-05-18-walmsley-creating-a-niem-2.1-iepd.pdf
-->

You talk to personal and professional associates and decide the information should be distributed so that others may learn, or be able to add to the group's knowledge, about the superhero.

Determine the information that would be useful to gather and the resources needed to obtain and distribute the information. You decide that acquiring and distributing the person's name and appearance is enough. Develop a [Use Case, Business Process, or Sequence](/training/iepd-developer/scenario-planning/) diagram to graphically show the actors and information flow for your scenario. 

The NIEM data model is very large. It is highly likely that the type and format of the data you want to acquire and distribute is already defined. If not, then one of the several [NIEM Communities]({{ site.data.links.niem_communities }} "NIEM Communities") may have tackled a similar problem and developed an information exchange pacakage (IEP) that comes close to meeting your needs. A search through their published resources can help.

{:.example}
>

### Analyze Requirements


<!--

### Analyze Requirements

The selected information exchange scenario is further elaborated to understand and document the business context and data requirements.

### Map and Model

You begin the creation of IEPD components for your exchange content model based on your information exchange requirements.  You start with the mapping document, which matches your exchange data elements to the NIEM data model.

### Build and Validate

You create a set of exchange-specific, NIEM-conformant XML schemas that implement the exchange content model created for the exchange and validate them. Components in this phase also include other XML documents generated from NIEM tools (e.g., Wantlist).

### Assemble and Document

You prepare and package all related files for the IEPD into a single, self‐contained, self-documented, portable archive file. You then should perform a peer review to ensure artifact consistency within the IEPD and with other IEPDs.

### Publish and Implement

You implement the IEPD into production and publish the IEPD for search, discovery, and reuse.
-->