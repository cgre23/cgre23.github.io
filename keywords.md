---
layout: post
title: Keyword Extraction from the OPEN-AIRE journal database
permalink: /keywords/
description: Natural Language Processing
tags: [Jekyll, theme, responsive, blog, template]
image:
  feature:
---
<br>**Project description**


<p align="justify"> Given a database of important keywords and a database of < 110 million publications, the task is to identify the occurrence of the keywords in all publications and store this information in a SQL database. The Aho-Corasick algorithm is used to identify patterns between the two databases, with challenges being punctuation, big/small capital letters, multiple-word keywords etc..
 </p> <br><br>


 <p align="justify"> Secondly, related keywords are identified using the MinHash technique. In computer science and data mining, MinHash (or the min-wise independent permutations locality sensitive hashing scheme) is a technique for quickly estimating how similar two sets are.
 The Jaccard similarity coefficient is a commonly used indicator of the similarity between two sets. Let U be a set and A and B be subsets of U, then the Jaccard index is defined to be the ratio of the number of elements of their intersection and the number of elements of their union:

    J ( A , B ) = | A ∩ B | | A ∪ B | . {\displaystyle J(A,B)={{|A\cap B|} \over {|A\cup B|}}.} J(A,B)={{|A\cap B|} \over {|A\cup B|}}.

This value is 0 when the two sets are disjoint, 1 when they are equal, and strictly between 0 and 1 otherwise. Two sets are more similar (i.e. have relatively more members in common) when their Jaccard index is closer to 1. The goal of MinHash is to estimate J(A,B) quickly, without explicitly computing the intersection and union.  
  </p> <br><br>
