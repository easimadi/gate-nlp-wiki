---
title: Gate Document
date: 2018-09-20 17:30:00 +0100
---


The GATE `Document` is the document or body of text to be annotated. A collections of documents make a `Corpus`

# A GATE Document consist of 
* a DocumentContent object
* a Default annotation set (which bears no name)
* zero or more named annotation sets.

### Because a Document is also a Resource, it also has
* a name
* features  

### API Signature.
```java
// Get the name of the Document
public String getName();

//get document content
public DocumentContent getContent();

// get the Default Annotation set
public AnnotationSet getAnnotations();  

// get a named Annotation set
public AnnotationSet getAnnotations(String name);  

// get all named Annotation sets
public Map<String, AnnotationSet> getNamedAnnotationSets();

// Get the names of the annotation sets
public Set<String> getAnnotationSetNames();

```

------

# Illustration
To illustrate these we load the GATE-NLP home page (`Document_url = https://gate.ac.uk/index.html`) as `Document`.
So the source document it the html page with all the markups at the above url.

**Example 1: Get document content**
```java
//assumes Document `doc` has been created.
DocumentContent content = doc.getContent()

System.out.println(content)
```
Output
[Image Docment Content]




**Example 2: Get a named Annotation set**


Example, since this document has no default annotation set lets use the apportunity to get "Original markups". which is the HTML tags of the input document.
```java
AnnotationSet originalMarkupSet = doc.getAnnotations("Original markups")
System.out.println(originalMarkupSet)
```
Output

```
[AnnotationImpl: id=0; type=html; features={lang=en}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=1; offset=2914
, AnnotationImpl: id=1; type=head; features={}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=2; offset=25
, AnnotationImpl: id=2; type=meta; features={http-equiv=Content-Type, content=text/html; charset=UTF-8}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=0; offset=0
, AnnotationImpl: id=3; type=title; features={}; start=NodeImpl: id=0; offset=0; end=NodeImpl: id=3; offset=23
, AnnotationImpl: id=4; type=meta; features={name=generator, content=cow}; start=NodeImpl: id=2; offset=25; end=NodeImpl: id=2; offset=25
, AnnotationImpl: id=5; type=script; features={id=twitter-wjs, src=./gate-sample-doc_files/widgets.js, isEmptyAndSpan=true}; start=NodeImpl: id=2; offset=25; end=NodeImpl: id=2; offset=25
, AnnotationImpl: id=6; type=script; features={type=text/javascript, src=./gate-sample-doc_files/gate.cow.gwt.NewPage.nocache.js, isEmptyAndSpan=true}; start=NodeImpl: id=2; offset=25;
......
]
```



