---
title:  JAPE Rules & Common Patterns
image: "atom.png"
description: "Understanding Jape Rules & Common Patterns"
parmalink: /:path/
date: 2018-09-20 17:36:00 +0100
---



```java
// Warning: spectacularly inefficient.
public static long fibonacci(int n) {
    if (n == 0) return 0;
    if (n == 1) return 1;
    return fibonacci(n-1) + fibonacci(n-2);
} 

```

<p>In this section we look at Jape rules and the common patterns in JAPE rules.<br></p>

<p>The JAPE Transducer is a component in GATE framework that enables creation of annotations using rules </p>

<strong>What you will learn.</strong>

<ul>
  <li>Overview of JAPE Rules</li>
  <li>Understanding Left Hand Side Patterns</li>
  <li>Understanding Right Hand Side Patterns</li>
  <li>Understanding Right Hand Side Java Patterns</li>
</ul>

