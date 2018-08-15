---
title: Simple IEPD Tutorial
short: Simple IEPD Tutorial
icon: fa-envelope-o
description: This tutorial shows you how to create a very simple IEPD. Once you are comfortable with the process and output, you can move on to more complex IEPDs.
---

{{ page.description}}

## In the Beginning

You observe a person who displays superhuman powers (a superhero). You want to inform others of this person's presence and unique characteristics.

## Scenario Planning

<!--
You review background information related to your information exchange, assess resource impact, understand business context, and identify information exchange business scenarios.

sources:
IEPD Tutorials from /iepd-starter-kit/iepd-tutorials/
Dropbox (GaTech)/NIEM-FA807514D0018-0018/training/2010-05-18-walmsley-creating-a-niem-2.1-iepd/2010-05-18-walmsley-creating-a-niem-2.1-iepd.pdf
-->

You talk to personal and professional associates and decide the information should be distributed so that others may learn, or be able to add to the group's knowledge, about the superhero.

Determine the information that would be useful to gather and the resources needed to obtain and distribute the information. You decide that acquiring and distributing the person's name and appearance is enough. Develop a [Use Case, Business Process, or Sequence](/training/iepd-developer/scenario-planning/) diagram to graphically show the actors and information flow for your scenario. A visual representation can be very useful especially if the scenario is complex.

The NIEM data model is very large. It is highly likely that the type and format of the data you want to acquire and distribute is already defined. If not, then one of the several [NIEM Communities]({{ site.data.links.niem_communities }} "NIEM Communities") may have tackled a similar problem and developed an information exchange package (IEP) that comes close to meeting your needs. A search through their published resources can help.

{:.example}
>Scenario Information Acquisition and Flow
>
>1. Witness sees Superhero display powers
>1. Witness obtains Superhero name
>1. Witness transmits information to Police
>1. Police transmit Superhero information to other Authorities

{:.quiz}
> Answer a few questions in a [short quiz](/training/iepd-developer/simple-iepd-tutorial/quiz-1).
<a name="quiz-1-return"/>

---

## Analyze Requirements

The information exchange scenario now needs to be broken down into finer detail to understand and document the business context and data requirements. There is no prescribed way to to do this, nor is the knowledge of NIEM or XML Schema required. The most important idea to keep in mind is that the subject matter experts capture the requirements and analysis with thorough detail.

The first item you need to determine is the single, main, focal point or purpose for the exchange. This is technically known as the root element. For this simple IEPD, that is the superhero.

{:.example}
> root element = `Person`. Assume the superhero is a human person.

The content portion of the requirements analysis can be done however you prefer: document, spreadsheet, or model diagram.  The kinds of information to capture include the following:

- Data elements – These are the data fields for the message.  For each field, the following information may or will be needed:
  - Element name – This is the name of the field or tag.  Examples include First Name, Last Name, Street Address, and Phone Number.
  - Data type – The structural representation or format of the element. Examples include string, date, integer, decimal, Boolean, state code set, person data type, location data type.
  - Definition – Descriptive definitions will be required for all components in the exchange. At this stage, the semantics need to be captured, but the wording does not have to be finalized or perfected. If you determine later that an element maps to NIEM, then the NIEM element will come with its own definition. The definition captured here should be sufficient enough so that the meaning is clear.
  - Occurrence constraints – The minimum and maximum number of times an element may appear in the instance. For example, Last Name may occur once only; Social Security Number (SSN) may occur 0 to 1 times; Phone Number may occur 0 to many times.

    Default occurrence constraints in NIEM are 0 to unbounded (with a few exceptions); the default in XML Schema is once only.  Without explicitly setting these occurrence constraints, the defaults mean that components reused from NIEM will be optional and the ones added locally will be required.
  - Source information – Optional. It may be useful or necessary in some cases to record the source of the requirement. Traceability information may seem very apparent at the time but can be difficult to reconstruct at a later date if needed.

{:.note}
>If a corresponding NIEM element is already known at this stage, then the NIEM values may be used in place of local ones for element name, data type, and definition.

- Objects and classes – These are the complex, reusable data structures where related elements are grouped together.  Examples include Person (with elements First Name, Last Name, SSN, and Phone) and Location (with elements Street Address, City, State, and Zip Code).
- Code sets – This is a list of allowable values, such as a state code list or an eye color list.  Code sets may come from a standard or may be custom-defined.
- Conditions and business rules – There may be certain restrictions on the content that need to be represented.  Examples include restrictions on individual values (such as a number that cannot be less than zero or a string that must have a certain number of characters) and conditional restraints (such as if the SSN is not provided, then Last Name and Birth Date are required), etc.

The other requirements of the exchange (e.g., technical, security and privacy, performance, reporting) should be described in this stage as well.

{:.quiz}
> Answer a few questions in a [short quiz](/training/iepd-developer/simple-iepd-tutorial/quiz-2).
<a name="quiz-2-return"/>

---

## Map and Model Requirements

You begin the creation of IEPD components for your exchange content model based on your information exchange requirements analysis.  A common way to start is to create a mapping document. This is typically a spreadsheet, which maps your local exchange data elements to the NIEM data model. You can [download a sample spreadsheet](/training/iepd-developer/map-and-model/assets/SampleEmptyMappingDocument.xlsx "Sample Mapping Document") and modify it to suit your requirements.

The [Schema Subset Generation Tool (SSGT)](/reference/tools/ssgt/ "Schema Subset Generation Tool (SSGT)") is a good tool to use to map your exchange to NIEM. If you are unfamiliar with the SSGT, refer to [Map and Model Training](/training/iepd-developer/map-and-model/ "Map and Model Training"), "What is a Mapping Document." The SSGT's advantage lies in that you can extract just what you need from NIEM, i.e., create a subset.

{:.tip}
>To find matches for your local components, use common words or acronyms in the search box.  Local names will be much less likely to return results.  A search term like "FirstName" or "First_Name" will return empty because these exact terms do not appear in any NIEM names or definitions; a search for "First Name" will return the matching component, `nc:PersonGivenName`, based on a match in the definition.

{:.example}
>
>- SSGT search results are sorted by namespace (e.g., hs:, j:, nc:, and so on) unless there is a likely one from NIEM core (nc:) which will appear at the top of the list.
>- SSGT search "Property" for "Person" shows `nc:Person` which is of `nc:PersonType`. Note that among the search results is `nc:PersonCapability` (this might be useful later).
>- Search "Property" for "Name" shows `nc:PersonGivenName` and `nc:PersonSurName`: both are `nc:PersonNameTextType`. Those look like they should fit with our model.

We have enough information from the preceding example, to begin [filling in a mapping document](/training/iepd-developer/map-and-model/). Make certain you have recorded your SSGT searches so you can begin to fill in the spreadsheet.

**Source Data Columns**

- Source Container Type - Person
- Source Element - Person, Name
- Source Data Type - string
- Source Element Definition - a superhero who is also a human being
- Source Element Cardinality - one person, one name

**NIEM Data Columns**

- NIEM Element - nc:Person, nc:PersonGivenName, nc:PersonSurName, nc:personNameInitialIndicator
- NIEM Element Path - nc:Person/nc:PersonName/nc:PersonFullName/nc:personNameInitialIndicator
- NIEM Type - nc:PersonType, nc:PersonNameType, nc:PersonNameTextType
- NIEM Element Definition - A human being
- NIEM Element Cardinality - 1:1 (at least one name, but no more than one name)

**Mapping Column**

- Mapping - Equivalent

{:.quiz}
> Answer a few questions in a [short quiz](/training/iepd-developer/simple-iepd-tutorial/quiz-3).
<a name="quiz-3-return"/>

---

<!--
### Build and Validate

You create a set of exchange-specific, NIEM-conformant XML schemas that implement the exchange content model created for the exchange and validate them. Components in this phase also include other XML documents generated from NIEM tools (e.g., Wantlist).

### Assemble and Document

You prepare and package all related files for the IEPD into a single, self‐contained, self-documented, portable archive file. You then should perform a peer review to ensure artifact consistency within the IEPD and with other IEPDs.

### Publish and Implement

You implement the IEPD into production and publish the IEPD for search, discovery, and reuse.
-->