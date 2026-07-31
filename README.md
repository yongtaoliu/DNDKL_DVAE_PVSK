# DNDKL_DVAE_PVSK

Novelty Deep Kernel Learning Driven Autonomous Microscopy and Dual Variational Autoencoder Structure-Property Correlation Analysis

Citation: If you use the approach in your work, please cite https://pubs.acs.org/ancac3/article/doi/10.1021/acsnano.6c04715/5237620/Accelerating-Structure-Property-Relationship

Self-driving AFM experiment and post-experiment analysis for perovskite (PVSK) IV curve mapping using image- and spectrum-novelty-guided Bayesian active learning, combined with im2spec variational autoencoder for structure–property relationship discovery.

This repository contains two Jupyter notebooks that together implement a complete autonomous scanning probe microscopy workflow on perovskite thin films:

--Autonomous Experiment Notebook: Runs on a live Asylum Cypher or VERO AFM. Autonomously selects measurement locations by combining a Deep Kernel Learning (DKL) Gaussian Process surrogate with dual novelty scores (image-structural and spectrum-anomaly), acquires IV curves in a closed loop, and saves the results. The goal of this novelty-driven search is to collect a diverse, representative dataset of (image patch, spectra) pairs across the sample under study — efficiently and autonomously, without exhaustive grid scanning. A random or grid-based survey would waste measurement budget on redundant locations. Instead, novelty-driven active learning steers the AFM tip toward locations that are both structurally distinct (different local morphology) and spectroscopically anomalous (unusual spectra behaviour), ensuring the collected dataset spans the full range of structure–property relationships present on the sample. This diversity is the key prerequisite for training a well-generalising im2spec in the analysis step.

--Post-Experiment Notebook: Loads the image patch-spectra pair dataset and trains a Variational Autoencoder (im2spec) to learn a latent mapping from local image patches to spectra manifolds, enabling dense structure–property correlation across the full field of view. Because the novelty active learning approach ensured broad coverage of the sample's structural and spectroscopic diversity, the (patch → spectrum) training pairs here are far more informative per measurement than a random sample of the same size would be. This notebook trains a Dual Variational Autoencoder (im2spec) on those pairs, exploiting the dataset to learn a generalisable structure–property mapping. 

