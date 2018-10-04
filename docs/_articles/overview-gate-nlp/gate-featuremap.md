---
title: Gate FeatureMap
date: 2018-09-20 17:33:00 +0100
---

Feature maps extend Map data structure and hold metadata of the annotation. It enables us to attach arbituary key value pairs (metadata) to the annotation.

PrintOut of FeatureMap as part of an Annotation.

```
AnnotationImpl: id=5; type=script; features={id=twitter-wjs, src=./gate-sample-doc_files/widgets.js, isEmptyAndSpan=true}; start=NodeImpl: id=2; offset=25; end=NodeImpl: id=2; offset=25
```

# Feature Maps
* are Java Maps, with support for firing events
* used to store metadata on many GATE objects
* used to provide parameter values when creating creole resources

All GATE Resources are feature bearers [1]

Example
```java
FeatureMap feature = Factory.newFeatureMap();
feature.put("Date",new Date());
feature.put("Rule","myDateRule");

```
