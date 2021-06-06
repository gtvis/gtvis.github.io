---
authors:
- Nilaksh Das
- Madhuri Shanbhogue
- Shang-Tse Chen
- Fred Hohman
- Siwei Li
- Li Chen
- Michael E. Kounavis
- Duen Horng (Polo) Chau
link:
tags:
- Image Compression
- Computing Methodologies
- Computer Vision
- Machine Learning Approaches
- Machine Learning
- Neural Networks
- Artificial Intelligence
- Computer Graphics
title: 'SHIELD: Fast, Practical Defense and Vaccination for Deep Learning using JPEG
  Compression.'
venue: KDD
year: 2018
---
The rapidly growing body of research in adversarial machine learning has demonstrated that deep neural networks (DNNs) are highly vulnerable to adversarially generated images. This underscores the urgent need for practical defense techniques that can be readily deployed to combat attacks in real-time. Observing that many attack strategies aim to perturb image pixels in ways that are visually imperceptible, we place JPEG compression at the core of our proposed SHIELD defense framework, utilizing its capability to effectively "compress away" such pixel manipulation. To immunize a DNN model from artifacts introduced by compression, SHIELD "vaccinates" the model by retraining it with compressed images, where different compression levels are applied to generate multiple vaccinated models that are ultimately used together in an ensemble defense. On top of that, SHIELD adds an additional layer of protection by employing randomization at test time that compresses different regions of an image using random compression levels, making it harder for an adversary to estimate the transformation performed. This novel combination of vaccination, ensembling, and randomization makes SHIELD a fortified multi-pronged defense. We conducted extensive, large-scale experiments using the ImageNet dataset, and show that our approaches eliminate up to 98% of gray-box attacks delivered by strong adversarial techniques such as Carlini-Wagner's L2 attack and DeepFool. Our approaches are fast and work without requiring knowledge about the model.