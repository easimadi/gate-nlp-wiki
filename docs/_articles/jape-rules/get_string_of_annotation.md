---
title: Get the String of the Annotation
Date: 2018-10-04 10:00:00 +0100
parmalink: /:path/
---


# Problem Statement
Get the string which an annotations spans. This is useful if the annotation doesn't have a `string` feature and we want to create one.


## API Signature 1
```java
Imports: {
        import static gate.Utils.*;
}

gate.Utils.stringFor(Document doc, AnnotationSet annset);
gate.Utils.stringFor(Document doc, Long startOffset, Long endOffset);
gate.Utils.stringFor(Document doc, SimpleAnnotation ann);
```

## Example
Extract the string and put it as a feature.

```java

Imports: {
        import static gate.Utils.*;
}

String str = gate.Utils.stringFor(doc, ann);

//print tthe string to believe :)

System.out.println(str);

// add it to a feature of the Annotation (ann)

ann.getFeatures().put("string", str)

```
