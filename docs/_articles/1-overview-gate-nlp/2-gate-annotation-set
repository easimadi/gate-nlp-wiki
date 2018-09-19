---
title: Gate Annotation Set
---

`AnnotationSet` like the name suggests is a set of `Annotations` - an extension of `Set<Annotation>`.
we talk of `annotation` in the next page - they are markups of the document implemented as an object with annotation `type`, 
`start` and `end offsets` and `features`.

- Annotation sets can be managed (create, delete, modified...) by the `Document` they belong to.

**PrintOut of an AnnotationSet**
```
{Original markups=[AnnotationImpl: id=0; type=html; features={lang=en}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=1; offset=2914
, AnnotationImpl: id=1; type=head; features={}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=2; offset=25
, AnnotationImpl: id=2; type=meta; features={http-equiv=Content-Type, content=text/html; charset=UTF-8}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=0; offset=0
, AnnotationImpl: id=3; type=title; features={}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=3; offset=23
....]
}
```

## API Signature
**Access Nodes in the set**

```java
// Get the node with the smallest offset.
public Node firstNode();
// Get the node with the largest offset.
public Node lastNode();
```

**New Annotations**
```java
// Create (and add) a new annotation
public Integer add(Long startOffset, Long endOffset,
String type, FeatureMap features);
// Create (and add) a new annotation
public Integer add(Node start, Node end,
String type, FeatureMap features)
```

**Getting Annotations by offsets**
```java
// Get annotations starting from
public AnnotationSet get(Long offset)

// Get all annotations that overlap/are between two offsets
public AnnotationSet get(Long startOffset, Long endOffset)

// Get all annotations within an interval.
public AnnotationSet getContained(Long startOffset, Long endOffset)

// Get all annotations covering an interval.
public AnnotationSet getCovering(String neededType, Long startOffset, Long endOffset)

// COMBINED CONSTRAINTS
// Get by type and feature constraints.
public AnnotationSet get(String type, FeatureMap constraints)

// Get by type, constraints and start position.
public AnnotationSet get(String type, FeatureMap constraints, Long startOffset)

// Get by type, and interval overlap.
public AnnotationSet get(String type, Long startOffset, Long endOffset)

// Get by type and feature presence
public AnnotationSet get(String type, Set featureNames)


```


Reference
Gate NLP Tutorial

