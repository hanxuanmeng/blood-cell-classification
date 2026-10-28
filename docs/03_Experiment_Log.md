# Experiment Log

**Project:** Red Blood Cell Morphology Classification\
**Framework:** PyTorch\
**Dataset:** erythrocytesIDB1\
**Classes:** Circular, Elongated, Other\
**Primary Metric:** Macro-F1

## Experiment 1 --- Dataset Exploration

**Question:** Is the dataset suitable for a three-class morphology
experiment?\
**Procedure:** Index images, count classes, and inspect representative
examples.\
**Observation:** Circular cells appear relatively distinct; Elongated
and Other include more visually similar examples.\
**Decision:** Preserve class proportions during splitting.

## Experiment 2 --- Data Preparation

**Procedure:** Random seed 42; stratified 70/15/15 split; resize to 224
× 224; modest training-only augmentation.\
**Decision:** Reuse the exact same split for both models.

## Experiment 3 --- Baseline CNN

**Architecture:** Three convolutional blocks (32, 64, 128 channels),
adaptive average pooling, dropout, three-class classifier.\
**Training:** Cross-entropy, Adam, learning rate 0.001, up to 30
epochs.\
**Result:** Accuracy **82.1%**; macro-F1 **0.819**.\
**Next Step:** Test transfer learning.

## Experiment 4 --- MobileNetV2 Transfer Learning

**Procedure:** ImageNet weights; train classifier first; then fine-tune
upper feature layers.\
**Stage 1 learning rate:** 0.001\
**Stage 2 learning rate:** 0.00001\
**Result:** Accuracy **89.5%**; macro-F1 **0.894**.

## Experiment 5 --- Model Comparison

  Model            Accuracy   Macro-F1
  -------------- ---------- ----------
  Baseline CNN        82.1%      0.819
  MobileNetV2         89.5%      0.894

**Difference:** +7.4 percentage points accuracy; +0.075 macro-F1.

## Experiment 6 --- Class-Level Performance

  Class         Precision   Recall     F1
  ----------- ----------- -------- ------
  Circular           0.93     0.94   0.94
  Elongated          0.87     0.84   0.85
  Other              0.89     0.90   0.90

## Experiment 7 --- Error Analysis

High-confidence errors concentrate around morphology boundaries,
especially Elongated versus Other. Possible factors include ambiguous
shape, overlap, cropping, lighting, and limited examples.

## Experiment 8 --- Final Interpretation

**Main Finding:** MobileNetV2 produces stronger overall performance.\
**Limitations:** Small dataset, no independent external test set,
possible label ambiguity, and no clinical validation.\
**Next Directions:** Multiple seeds, variability estimates, robustness
testing, explainability, and independent validation.
