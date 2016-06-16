---
title: Shared Canvas Data Model
title_override: "Shared Canvas Data Model 2.0"
id: shared-canvas
layout: sub-page
categories: [specifications, presentation-api, spec-doc]
major: 2
minor: 0
patch: 0
pre: draft1
---

## Status of this Document
{:.no_toc}
__This Version:__ {{ page.major }}.{{ page.minor }}.{{ page.patch }}{% if page.pre != 'final' %}-{{ page.pre }}{% endif %}

__Latest Stable Version:__ [{{ site.shared_canvas.latest.major }}.{{ site.shared_canvas.latest.minor }}.{{ site.shared_canvas.latest.patch }}][stable-version]

__Previous Version:__ [1.0][prev-version]

**Editors**

  * **[Michael Appleby](https://orcid.org/0000-0002-1266-298X)** [![ORCID iD](/img/orcid_16x16.png)](https://orcid.org/0000-0002-1266-298X), [_Yale University_](http://www.yale.edu/)
  * **[Tom Crane](https://orcid.org/0000-0003-1881-243X)** [![ORCID iD](/img/orcid_16x16.png)](https://orcid.org/0000-0003-1881-243X), [_Digirati_](http://digirati.com/)
  * **[Robert Sanderson](https://orcid.org/0000-0003-4441-6852)** [![ORCID iD](/img/orcid_16x16.png)](https://orcid.org/0000-0003-4441-6852), [_J. Paul Getty Trust_](http://www.getty.edu/)
  * **[Jon Stroop](https://orcid.org/0000-0002-0367-1243)** [![ORCID iD](/img/orcid_16x16.png)](https://orcid.org/0000-0002-0367-1243), [_Princeton University Library_](https://library.princeton.edu/)
  * **[Simeon Warner](https://orcid.org/0000-0002-7970-7855)** [![ORCID iD](/img/orcid_16x16.png)](https://orcid.org/0000-0002-7970-7855), [_Cornell University_](https://www.cornell.edu/)
  {: .names}

{% include copyright.md %}

----

## Table of Contents
{:.no_toc}

* Table of Discontent (will be replaced by macro)
{:toc}

## 1. Introduction



## 2. Canvas

### 2.1. Classes

Canvas
Space

### 2.2. Relationships

Relationships from other ontologies

## 2.3. Use of Annotations

painting


## 3. Structure

### 3.1. Classes

Collection
Manifest
Sequence
Range

AnnotationList DEPRECATED --> AnnotationPage
Layer DEPRECATED --> AnnotationCollection
Zone DEPRECATED --> Canvas

# 3.2. Relationships

hasParts          d: *  r: rdf:List [of Collection, Range, Manifest]
hasSequences d: Manifest r: rdf:List [of Sequence] spo hasParts
hasCanvases   d: Sequence r: rdf:List [of Canvas] spo hasParts
hasImageAnnotations d: Canvas r: rdf:List [of Annotation, where body is a Image]
hasLists             d: U(Canvas, Layer)  r: rdf:List [of AnnotationList]

hasCollections  d: Collection r: rdf:List [of Collection] DEPRECATED
hasManifests    d: Collection r: rdf:List [of Manifest] DEPRECATED
hasRanges        d: Range r: rdf:List [of Range] DEPRECATED
hasAnnotations d: AnnotationList r: rdf:List [of Annotation] DEPRECATED

hasStartCanvas  d: U(Manifest, Sequence)   r: Canvas
hasContentLayer d: Range r: Layer

Plus relationships from other ontologies

## 4. Other Features

### 4.1. Classes

ViewingDirection
ViewingHint
MetadataPair

### 4.2. Relationships

metadataLabels d: *  r: List [of MetadataPair]
presentationDate d: U( ) r: xsd:dateTime
attributionLabel d: * r: xsd:string
viewingDirection d: U(Manifest, Sequence) r: ViewingDirection
viewingHint d: * r: ViewingHint

### 4.3. Instances

ViewingDirection
leftToRightDirection
rightToLeftDirection
topToBottomDirection
bottomToTopDirection

ViewingHint
pagedHint
nonPagedHint
continuousHint
individualsHint
topHint
multiPartHint
facingPagesHint


## 5. Examples

...


### A. Versioning

Starting with version 2.0, this specification follows [Semantic Versioning][semver]. See the note [Versioning of APIs][versioning] for details regarding how this is implemented.

### B. Acknowledgements

The production of this document was generously supported by a grant from the [Andrew W. Mellon Foundation][mellon].

Many thanks to the members of the [IIIF][iiif-community] for their continuous engagement, innovative ideas and feedback.

### C. Change Log

| Date       | Description           |
| ---------- | --------------------- |
| 2016-XX-YY | Version 2.0 () [View change log][change-log] |
| 2012-XX-YY | Version 1.0 (unnamed) |


[iiif-discuss]: mailto:iiif-discuss@googlegroups.com "Email Discussion List"
[iiif-community]: /community/ "IIIF Community"
[semver]: http://semver.org/spec/v2.0.0.html "Semantic Versioning 2.0.0"
[mellon]: http://www.mellon.org/ "The Andrew W. Mellon Foundation"
[versioning]: /api/annex/notes/semver/ "Versioning of APIs"
[icon-req]: /img/metadata-api/required.png "Required"
[icon-recc]: /img/metadata-api/recommended.png "Recommended"
[icon-opt]: /img/metadata-api/optional.png "Optional"
[icon-na]: /img/metadata-api/not_allowed.png "Not allowed"

{% include acronyms.md %}



