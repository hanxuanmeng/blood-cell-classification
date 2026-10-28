# Stage-by-Stage Research Summary

## Stage 1 --- Data Exploration

**What We Did:** Indexed the three morphology classes and displayed
examples.\
**Why It Matters:** Modeling should begin with understanding the data.\
**What We Learned:** Elongated and Other contain more visually similar
examples.

## Stage 2 --- Data Preparation

**What We Did:** Created a stratified 70/15/15 split and prepared
PyTorch tensors and augmentation.\
**Why It Matters:** Separate test data protects final evaluation.

## Stage 3 --- Baseline CNN

**What We Did:** Built a small CNN from scratch.\
**What We Learned:** Accuracy **82.1%**, macro-F1 **0.819**.

## Stage 4 --- Baseline Evaluation

**What We Did:** Evaluated accuracy, precision, recall, F1, macro-F1,
and confusion matrix.\
**What We Learned:** The baseline left room for improvement.

## Stage 5 --- MobileNetV2 Transfer Learning

**What We Did:** Trained and fine-tuned an ImageNet-pretrained
MobileNetV2.\
**What We Learned:** Accuracy **89.5%**, macro-F1 **0.894**.

## Stage 6 --- Model Comparison

MobileNetV2 improved accuracy by **7.4 percentage points** and macro-F1
by **0.075**.

## Stage 7 --- Error Analysis

Elongated was the most difficult class, with F1 **0.85**. Several
mistakes occurred near the Elongated/Other boundary.

## Stage 8 --- Final Interpretation

**Main Conclusion:** Transfer learning produced stronger performance
than the CNN trained from scratch.\
**Limitations:** Small dataset, no independent external test set,
possible label ambiguity, no clinical validation.\
**Next Step:** Multiple seeds, robustness testing, explainability, and
independent validation.
