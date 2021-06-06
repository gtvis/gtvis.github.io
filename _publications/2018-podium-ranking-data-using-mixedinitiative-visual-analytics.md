---
authors:
- Emily Wall
- Subhajit Das
- Ravish Chawla
- Bharath Kalidindi
- Eli T. Brown
- Alex Endert
link:
tags:
- Support Vector Machines
- Visual Analytics
- Data Visualization
- Computational Modeling
- Prototypes
- Data Models
title: 'Podium: Ranking Data Using Mixed-Initiative Visual Analytics.'
venue: IEEE Trans. Vis. Comput. Graph.
year: 2018
---
People often rank and order data points as a vital part of making decisions. Multi-attribute ranking systems are a common tool used to make these data-driven decisions. Such systems often take the form of a table-based visualization in which users assign weights to the attributes representing the quantifiable importance of each attribute to a decision, which the system then uses to compute a ranking of the data. However, these systems assume that users are able to quantify their conceptual understanding of how important particular attributes are to a decision. This is not always easy or even possible for users to do. Rather, people often have a more holistic understanding of the data. They form opinions that data point A is better than data point B but do not necessarily know which attributes are important. To address these challenges, we present a visual analytic application to help people rank multi-variate data points. We developed a prototype system, Podium, that allows users to drag rows in the table to rank order data points based on their perception of the relative value of the data. Podium then infers a weighting model using Ranking SVM that satisfies the user's data preferences as closely as possible. Whereas past systems help users understand the relationships between data points based on changes to attribute weights, our approach helps users to understand the attributes that might inform their understanding of the data. We present two usage scenarios to describe some of the potential uses of our proposed technique: (1) understanding which attributes contribute to a user's subjective preferences for data, and (2) deconstructing attributes of importance for existing rankings. Our proposed approach makes powerful machine learning techniques more usable to those who may not have expertise in these areas.