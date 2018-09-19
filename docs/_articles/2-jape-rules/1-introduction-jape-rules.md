---
title:  Introduction to JAPE Rules
image: "images/icons/emoji/octocat.png"
date:   2018-09-16 18:35:00 +0100
---



# Introduction to JAPE Rules
Components on JAPE. With JAPE you define Patterns on LHS and define behaviour when the patterns are matched on the RHS.

```java
Imports: { import static gate.Utils.*; }

Phase: Example
Input: Token // and any other input annotation types
Options: control = appelt

Rule: Example1
(
    // LHS code goes here
):label
-->
{
    // RHS code goes here and it could be JAVA
}


