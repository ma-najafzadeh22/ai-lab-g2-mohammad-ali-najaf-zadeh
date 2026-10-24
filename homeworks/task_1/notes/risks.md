# Digit Classifier: Evaluation Metrics and Project Risks

Evaluating a digit classifier requires measuring both **predictive fidelity** (especially on edge cases) and **system-level performance**.

---

## Evaluation Metrics

### 1. Statistical & Classification Metrics

**Top-1 Accuracy**
The default baseline metric. Effective when test classes are balanced (like MNIST, with ~1,000 samples per digit), but hides per-digit blind spots.

**Confusion Matrix**
Essential for identifying systematic error patterns (e.g., distinguishing how often 3↔8, 4↔9, or 1↔7).

**Per-Class Precision, Recall, and Macro-F1**
- *Recall* tells you which digit the model frequently misses or ignores.
- *Precision* tells you if the model is overly eager to predict a specific digit when uncertain.
- *Macro-averaged F1* balances class performance without letting dominant classes skew the score.


**Confidence Calibration & Expected Calibration Error (ECE)**

**Reject Rate / Coverage Curve**
### 2. Operational & Systems Metrics

**Inference Latency 

**Memory & Parameter Footprint**

---

## Project Risks and Failure Modes

| Risk Category                                | Specific Failure Mode                                                                                               | Impact & Mitigation                                                                                                                                                                                                                                                                                                    |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Out-of-Distribution (OOD) Overconfidence** | Feeding non-digit inputs (e.g., letters, blank frames, stray marks, smiley faces) into a standard 10-class softmax. | The model will assign 100% of its probability across digits 0–9, often predicting a digit with high confidence. **Mitigation:** Add an explicit 11th "background/reject" class or implement energy-based OOD detection.                                                                                                |
| **Preprocessing & Segmentation Fragility**   | MNIST digits are pre-centered, anti-aliased, and scaled inside a 28×28 bounding box by center-of-mass.              | Real-world input (from a camera or drawing canvas) often arrives off-center, fragmented, or with different stroke thicknesses, causing model accuracy to degrade sharply. **Mitigation:** Implement strict bounding-box normalization, aspect-ratio preservation, and affine augmentations (rotation, scaling, shear). |
| **Distribution Shift**                       | Performance degrades on real-world data that differs from the training data.                                        | **Mitigation:** Test on data representative of the deployment environment and periodically review performance. Compare metrics between the test set and real-world environment data.                                                                                                                                   |
