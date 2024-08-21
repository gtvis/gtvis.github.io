---
authors:
- Fred Hohman
- Haekyu Park
- Caleb Robinson
- Duen Horng (Polo) Chau
link:
tags:
- Machine Learning Interpretability
- Deep Learning Visualization
- Activation Summarization
title: 'Summit: Scaling Deep Learning Interpretability by Visualizing Activation and Attribution Summarizations.'
venue: IEEE TVCG
year: 2019
---
Deep learning is increasingly used in decision-making tasks. However, understanding how neural networks produce final predictions remains a fundamental challenge. Existing work on interpreting neural network predictions for images often focuses on explaining predictions for single images or neurons. As predictions are often computed from millions of weights that are optimized over millions of images, such explanations can easily miss a bigger picture. We present Summit, an interactive system that scalably and systematically summarizes and visualizes what features a deep learning model has learned and how those features interact to make predictions. Summit introduces two new scalable summarization techniques: (1) activation aggregation discovers important neurons, and (2) neuron-influence aggregation identifies relationships among such neurons. Summit combines these techniques to create the novel attribution graph that reveals and summarizes crucial neuron associations and substructures that contribute to a model's outcomes. Summit scales to large data, such as the ImageNet dataset with 1.2M images, and leverages neural network feature visualization and dataset examples to help users distill large, complex neural network models into compact, interactive visualizations. We present neural network exploration scenarios where Summit helps us discover multiple surprising insights into a prevalent, large-scale image classifier's learned representations and informs future neural network architecture design. The Summit visualization runs in modern web browsers and is open-sourced.
