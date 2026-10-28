# Deep Learning Classification of Red Blood Cell Morphology

## Abstract

This project compared a CNN trained from scratch with a pretrained
MobileNetV2 for classifying individual red blood cell images into
Circular, Elongated, and Other categories. A stratified 70%/15%/15%
split was used. The baseline CNN achieved **82.1%** test accuracy and
**0.819** macro-F1. MobileNetV2 achieved **89.5%** accuracy and
**0.894** macro-F1. Error analysis indicated that Elongated cells were
the most difficult class. The project is an educational machine-learning
study and not a clinical diagnostic system.

## 1. Introduction

The study asks how accurately deep-learning models can distinguish the
three erythrocytesIDB1 morphology classes.

### Hypothesis

A pretrained model will outperform a small CNN trained from scratch
because transfer learning can reuse general visual features.

## 2. Dataset and Preprocessing

Images are resized to 224 × 224. Random seed 42 creates a stratified 70%
training, 15% validation, and 15% test split. Training images receive
modest flips and rotations. Images are normalized using ImageNet
statistics.

## 3. Baseline CNN

The PyTorch baseline uses three convolutional blocks with 32, 64, and
128 channels, adaptive average pooling, dropout, and a three-class
classifier.

-   Test accuracy: **82.1%**
-   Macro-F1: **0.819**

## 4. MobileNetV2 Transfer Learning

MobileNetV2 begins with ImageNet-pretrained weights. The classifier is
trained first, followed by fine-tuning of upper feature layers.

-   Test accuracy: **89.5%**
-   Macro-F1: **0.894**

Improvement over baseline: **7.4 percentage points** accuracy and
**0.075** macro-F1.

## 5. Class-Level Results

  Class         Precision   Recall     F1
  ----------- ----------- -------- ------
  Circular           0.93     0.94   0.94
  Elongated          0.87     0.84   0.85
  Other              0.89     0.90   0.90

## 6. Error Analysis

Errors were concentrated around morphology boundaries, especially
Elongated versus Other. Potential factors include ambiguous morphology,
overlap, cropping, lighting, and limited examples.

## 7. Discussion

Both models learned useful visual patterns, but MobileNetV2 achieved
stronger overall performance. Macro-F1 and class-level metrics show that
performance is not identical across classes.

## 8. Limitations

-   Relatively small dataset.
-   No independent external test dataset.
-   Possible ambiguous morphology labels.
-   Dependence on image acquisition and preprocessing.
-   No clinical validation.

## 9. Future Work

Repeat experiments across multiple predefined seeds, report variability
and confidence intervals, test robustness to imaging variation,
investigate explainability, and validate on independent data.

## 10. Conclusion

The project developed a complete PyTorch workflow from data exploration
through error analysis. MobileNetV2 outperformed the CNN trained from
scratch, supporting transfer learning as a useful approach for this
small microscopy dataset.
