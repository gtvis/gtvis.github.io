---
authors:
- Hannah Kim
- Jaegul Choo
- Haesun Park
- Alex Endert
link:
tags:
- Visual Analytics
- Data Visualization
- Semantics
- Scalability
- Data Models
- Principal Component Analysis
title: 'InterAxis: Steering Scatterplot Axes via Observation-Level Interaction.'
venue: IEEE TVCG
year: 2016
---
Scatterplots are effective visualization techniques for multidimensional data that use two (or three) axes to visualize data items as a point at its corresponding x and y Cartesian coordinates. Typically, each axis is bound to a single data attribute. Interactive exploration occurs by changing the data attributes bound to each of these axes. In the case of using scatterplots to visualize the outputs of dimension reduction techniques, the x and y axes are combinations of the true, high-dimensional data. For these spatializations, the axes present usability challenges in terms of interpretability and interactivity. That is, understanding the axes and interacting with them to make adjustments can be challenging. In this paper, we present InterAxis, a visual analytics technique to properly interpret, define, and change an axis in a user-driven manner. Users are given the ability to define and modify axes by dragging data items to either side of the x or y axes, from which the system computes a linear combination of data attributes and binds it to the axis. Further, users can directly tune the positive and negative contribution to these complex axes by using the visualization of data attributes that correspond to each axis. We describe the details of our technique and demonstrate the intended usage through two scenarios.