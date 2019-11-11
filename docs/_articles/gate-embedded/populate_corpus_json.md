---
title: Porpulate Corpus from JSON file
date: 2019-11-11 17:34:00 +0100
parmalink: /:path/
---


# Problem Statement
Given a twitter/JSON file we want to populate a GATE corpus.


## JSON File Format - A JSON Document.
The file usually contains multiple documents on a single new line.
Below is the content of a single document. it consist of `text` which is the content of the document and `entities` which is a Map of AnnotationType to an Array of features of that AnnotationType
```java
{
   "text":"Was professional and helpful ",
   "entities":{
      "AnnotationType1":[
         {
            "indices":[
               4,
               16
            ],
            "featurekey1":"",
            "termString":"professional",
            "rule":"none"
         },
         {
            "indices":[
               21,
               28
            ],
            "featurekey1":"",
            "termString":"helpful",
            "rule":"none"
         }
      ],
      "AnnotationType2":[
         {
            "indices":[
               4,
               16
            ],
            "string":"professional",
            "rule":"none"
         },
         {
            "indices":[
               21,
               28
            ],
            "string":"helpful",
            "rule":"none"
         }
      ]
   }
}
```

## JSON File Format - The JSON file
The file consist of multiple json documents on a line.
To create a sample of this and inspect, right-click on the corpus and `>> save as >> GATE JSON (.json)`

```java
doc1
doc2
doc2

```

## Populate a corpus from (twitter/json) file

```java
      Plugin twitterPlugin = new Plugin.Maven("uk.ac.gate.plugins","twitter","8.6");
      Gate.getCreoleRegister().registerPlugin(twitterPlugin);

      Plugin jsonPlugin = new Plugin.Maven("uk.ac.gate.plugins","format-json","8.6");
      Gate.getCreoleRegister().registerPlugin(jsonPlugin);

      Corpus corpus = Factory.newCorpus("aCorpus");
      InputStream in = new FileInputStream(new File("/path/to/file.json")); 

      ResourceHelper rh = (ResourceHelper)Gate.getCreoleRegister().getAllInstances("gate.gui.JsonCorpusPopulator").iterator().next();

      rh.call("populate",corpus,in,"text/x-json-twitter","/text");
```
