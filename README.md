# DNDKL_DVAE_PVSK

Novelty Deep Kernel Learning Driven Autonomous Microscopy and Dual Variational Autoencoder Structure-Property Correlation Analysis

Self-driving AFM experiment and post-experiment analysis for perovskite (PVSK) IV curve mapping using image- and spectrum-novelty-guided Bayesian active learning, combined with im2spec variational autoencoder for structure–property relationship discovery.

This repository contains two Jupyter notebooks that together implement a complete autonomous scanning probe microscopy workflow on perovskite thin films:
--Autonomous Experiment Notebook: Runs on a live Asylum Cypher or VERO AFM. Autonomously selects measurement locations by combining a Deep Kernel Learning (DKL) Gaussian Process surrogate with dual novelty scores (image-structural and spectrum-anomaly), acquires IV curves in a closed loop, and saves the results.
--Post-Experiment Notebook: Loads the saved spectroscopy dataset and trains a Variational Autoencoder (im2spec) to learn a latent mapping from local image patches to IV curve manifolds, enabling dense structure–property correlation across the full field of view.
