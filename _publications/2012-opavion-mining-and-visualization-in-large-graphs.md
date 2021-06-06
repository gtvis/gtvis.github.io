---
authors:
- Leman Akoglu
- Duen Horng (Polo) Chau
- U Kang
- Danai Koutra
- Christos Faloutsos
link:
tags:
- Data Mining
- Information Systems
- Information Systems Applications
title: 'OPAvion: mining and visualization in large graphs.'
venue: SIGMOD Conference
year: 2012
---
Given a large graph with millions or billions of nodes and edges, like a who-follows-whom Twitter graph, how do we scalably compute its statistics, summarize its patterns, spot anomalies, visualize and make sense of it? We present OPAvion, a graph mining system that provides a scalable, interactive workflow to accomplish these analysis tasks. OPAvion consists of three modules: (1) The Summarization module (Pegasus) operates off-line on massive, disk-resident graphs and computes graph statistics, like PageRank scores, connected components, degree distribution, triangles, etc.; (2) The Anomaly Detection module (OddBall) uses graph statistics to mine patterns and spot anomalies, such as nodes with many contacts but few interactions with them (possibly telemarketers); (3) The Interactive Visualization module (Apolo) lets users incrementally explore the graph, starting with their chosen nodes or the flagged anomalous nodes; then users can expand to the nodes' vicinities, label them into categories, and thus interactively navigate the interesting parts of the graph.