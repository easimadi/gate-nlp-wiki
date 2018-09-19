---
title: Gate Annotation
---

Annotions are the markups on segements of the DocumentContent.

Printout of an Annotation.
```
[AnnotationImpl: id=0; type=html; features={lang=en}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=1; offset=2914]
```

# Annotation consist of:
* a type (String)
* a start and end node (gate.Node)
* features
* managed by the `annotation sets` (create, delete, modify)


## API Signature
```java
public String getType();
public Node getStartNode();
public Node getEndNode();
public FeatureMap getFeatures();
```
