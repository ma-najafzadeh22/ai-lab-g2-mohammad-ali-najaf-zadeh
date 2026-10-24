#  PEAS Specification

Based on the nature of the **Handwritten Digit Recognition** problem, the PEAS components of our intelligent agent are defined as follows:

## 🏁 Performance Measure (معیار عملکرد)

- **Classification Accuracy:** Percentage of correctly predicted digit labels on the test set.
- **Inference Speed:** Computation time per image.

## 🌍 Environment (محیط)

- A dataset/stream of 2D grayscale images of handwritten digits (e.g., $28 \times 28$ pixel grids) collected from various writers.

## 🛞 Actuators (عملگرها)

- Outputting the predicted digit class label $\{0, 1, \dots, 9\}$ along with the probability distribution (confidence scores) over all 10 classes.

## 📡 Sensors (حسگرها)

- Digital image input reader that captures the 2D matrix of pixel intensity values, or a File I/O stream, or memory buffer.

---

## 🌐 Environment Properties (ویژگی‌های محیط مسئله)

| Property | Description |
|---|---|
| **Fully vs. Partially Observable** | Fully observable (the digit grid contains all available static information). |
| **Deterministic vs. Stochastic** | Deterministic (same image matrix input produces the same output). |
| **Episodic vs. Sequential** | Episodic (classifying image *N* does not influence image *N+1*). |
| **Static vs. Dynamic** | Static (the image does not change while the agent is inferring). |
| **Discrete vs. Continuous** | Discrete (fixed pixel grids and 10 discrete target classes). |