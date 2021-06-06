---
authors:
- Dezhi Fang
- Duen Horng (Polo) Chau
link:
tags:
- Computing Methodologies
- Machine Learning
- Operating Systems
- Contextual Software Domains
- Memory Management
- Software And Its Engineering
- Software Organization And Properties
- Virtual Memory
title: 'M3: Scaling Up Machine Learning via Memory Mapping.'
venue: SIGMOD Conference
year: 2016
---
To process data that do not fit in RAM, conventional wisdom would suggest using distributed approaches. However, recent research has demonstrated virtual memory's strong potential in scaling up graph mining algorithms on a single machine. We propose to use a similar approach for general machine learning. We contribute: (1) our latest finding that memory mapping is also a feasible technique for scaling up general machine learning algorithms like logistic regression and k-means, when data fits in or exceeds RAM (we tested datasets up to 190GB); (2) an approach, called M3, that enables existing machine learning algorithms to work with out-of-core datasets through memory mapping, achieving a speed that is significantly faster than a 4-instance Spark cluster, and comparable to an 8-instance cluster.