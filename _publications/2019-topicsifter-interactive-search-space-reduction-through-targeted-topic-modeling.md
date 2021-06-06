---
authors:
- Hannah Kim
- Dongjin Choi
- Barry L. Drake
- Alex Endert
- Haesun Park
link:
tags:
- Retrieved Subset
- Computational Modeling
- Simple Keyword Matching Search
- Visual Analytics
- Large-scale Document Retrieval
- Document Collections
- Topicsifter
- Data Analysis
- Document Handling
- Missed Relevant Documents
- Query Processing
- Irrelevant Documents
- Keyword Queries
- Interactive Search Space Reduction
- Data Visualisation
- Negative Feedback
- Relevance Feedback
- Targeted Topic Modeling
- Buildings
- Matrix Decomposition
- Search Problems
title: 'TopicSifter: Interactive Search Space Reduction through Targeted Topic Modeling.'
venue: VAST
year: 2019
---
Topic modeling is commonly used to analyze and understand large document collections. However, in practice, users want to focus on specific aspects or “targets” rather than the entire corpus. For example, given a large collection of documents, users may want only a smaller subset which more closely aligns with their interests, tasks, and domains. In particular, our paper focuses on large-scale document retrieval with high recall where any missed relevant documents can be critical. A simple keyword matching search is generally not effective nor efficient as 1) it is difficult to find a list of keyword queries that can cover the documents of interest before exploring the dataset, 2) some documents may not contain the exact keywords of interest but may still be highly relevant, and 3) some words have multiple meanings, which would result in irrelevant documents included in the retrieved subset. In this paper, we present TopicSifter, a visual analytics system for interactive search space reduction. Our system utilizes targeted topic modeling based on nonnegative matrix factorization and allows users to give relevance feedback in order to refine their target and guide the topic modeling to the most relevant results.