# Project Overview --- Red Blood Cell Morphology Classification Using Deep Learning

## Project Goal

This project investigates whether deep-learning image classifiers can
distinguish red blood cells by morphology: **Circular**, **Elongated**,
and **Other**.

## Research Question

How accurately can image-classification models distinguish the three
morphology classes in erythrocytesIDB1?

## Project Workflow

1.  Data exploration
2.  Reproducible train/validation/test split
3.  Baseline CNN
4.  Baseline evaluation
5.  MobileNetV2 transfer learning
6.  Model comparison
7.  Error analysis
8.  Final interpretation

## Models and Results

  Model            Test Accuracy   Macro-F1
  -------------- --------------- ----------
  Baseline CNN             82.1%      0.819
  MobileNetV2              89.5%      0.894

## Reproducibility

Random seed 42; stratified 70% training, 15% validation, 15% test split;
same held-out test set for both models.

## Scope

Educational machine-learning research project; not a clinical diagnostic
system.
