---
title: Utility Methods
date: 2018-11-28 17:35:00 +0100
---

Here are some Utility methods for working with Documents and Annotations

## API
#### Access start and end offsets of `Document`, `AnnotationSet`, `Annotations`
```java
anAnnotationSet.start();

anAnnotation.end();

```
#### Access the string covered by `Annotation`(s)
```java
Document.stringFor(anAnnotation);

Document.stringFor(anAnnotationSet);

```

#### The Length of an `Annotation`
```java
public int length();
//e.g.
anAnnotation.length();

public long lengthLong();

```

#### Turn maps into FeatureMaps
```java
def params = [sourceUrl:’http://gate.ac.uk’, encoding:’UTF-8’].toFeatureMap()
```

#### Convert AnnotationSet to a list of ordered annotations.
For predictable iteration

#### Interesting Access
```java
// get all tokens in the set.
anAnnotationSet["Token"]

// get all annotions at the offsets
anAnnotationSet[8..15];

adocumentContent[4..13];
```
