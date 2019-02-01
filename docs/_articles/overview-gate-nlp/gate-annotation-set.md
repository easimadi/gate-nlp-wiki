---
title: Gate Annotation Set
date: 2018-09-20 17:31:00 +0100
---

`AnnotationSet` like the name suggests is a set of `Annotations` - an extension of `Set<Annotation>`.
we talk of `annotation` in the next page - they are markups of the document implemented as an object with annotation `type`, 
`start` and `end offsets` and `features`.

# Annotation Set
- Annotation sets can be managed (create, delete, modified...) by the `Document` they belong to.



**PrintOut of an AnnotationSet**
```
{
Original markups=
[AnnotationImpl: id=0; type=html; features={lang=en}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=1; offset=2914
, AnnotationImpl: id=1; type=head; features={}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=2; offset=25
, AnnotationImpl: id=2; type=meta; features={http-equiv=Content-Type, content=text/html; charset=UTF-8}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=0; offset=0
, AnnotationImpl: id=3; type=title; features={}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=3; offset=23
....]
}
```

## API Signature
#### Access Nodes in the set

```java
// Get the node with the smallest offset.
public Node firstNode();
// Get the node with the largest offset.
public Node lastNode();
// Get Node with the next in the set relative to `node` provided.
public Node nextNode(Node node)
```

#### New Annotations
```java
//creating and adding a new annotation to a set  
public Integer add(Long startOffset, Long endOffset, String type, FeatureMap features);

//creating and adding a new annotation to a set   
public Integer add(Node start, Node end, String type, FeatureMap features);

//e.g.
outputAS.add(start, end, "newAnnotationType", features);
```

#### Getting Annotations by offsets
```java
//Get annotations starting from
public AnnotationSet get(Long offset);

//Get all annotations that overlap/are between two offsets
public AnnotationSet get(Long startOffset, Long endOffset);

// Get all annotations within an interval.
public AnnotationSet getContained(Long startOffset, Long endOffset);

// Get all annotations covering an interval.
public AnnotationSet getCovering(String neededType, Long startOffset, Long endOffset);

// COMBINED CONSTRAINTS
// Get by type and feature constraints.
public AnnotationSet get(String type, FeatureMap constraints);

// Get by type, constraints and start position.
public AnnotationSet get(String type, FeatureMap constraints, Long startOffset);


// Get by type, and interval overlap.
public AnnotationSet get(String type, Long startOffset, Long endOffset);
// e.g
inputAS.get("Tokens", start, end);

// Get by type and feature presence
public AnnotationSet get(String type, Set featureNames);

// Get the set of annotation types present in the set.
Set getAllTypes()
```

#### Get Annotations in Document Order (Sort)
When you bind to and access annotationSet in the RHS their order is not guaranteed.  
Here is how to order them.

```java
  AnnotationSet annSet = tagAnnots;
  List<Annotation> verbList = gate.Utils.inDocumentOrder(annSet);
  
  //access the first annotation
  verbList.get(0);
```

#### Removing Annotations
Sometimes you want to remove annotations from a set.

```java
public void remove(Object ann);

public boolean removeAll(Collection<?> annAS);

// example
inputAS.removeAll(annAS);
```


Reference  
[Gate NLP Tutorial](https://gate.ac.uk)

