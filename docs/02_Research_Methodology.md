# Research Methodology

## Research Design

Supervised three-class image classification comparing a CNN trained from
scratch with MobileNetV2 transfer learning.

## Dataset

erythrocytesIDB1, obtained from its official distribution when access
permits.

## Data Split

Stratified **70% training / 15% validation / 15% test**, random seed 42.

## Preprocessing

Images are resized to 224 × 224, converted to PyTorch tensors,
normalized with ImageNet statistics, and modestly augmented during
training.

## Baseline CNN

Three convolutional blocks (32, 64, 128 channels), adaptive average
pooling, dropout, and a three-class classifier. Cross-entropy loss and
Adam optimization.

## MobileNetV2

ImageNet-pretrained weights; train the new classifier first, then
fine-tune upper feature layers using a smaller learning rate.

## Evaluation

Accuracy, precision, recall, F1, macro-F1, and confusion matrices.

  Model            Accuracy   Macro-F1
  -------------- ---------- ----------
  Baseline CNN        82.1%      0.819
  MobileNetV2         89.5%      0.894

## Error Analysis

Inspect high-confidence incorrect predictions, especially
Elongated-versus-Other errors.

## Interpretation

The experiment addresses machine-learning performance, not clinical
diagnostic validity.
