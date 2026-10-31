# ✍️ AI Lab Project: Handwritten Digit Recognition (تشخیص ارقام دست‌نویس)

This repository contains the documentation, environment checks, and source code for the **Artificial Intelligence Laboratory** course project, carried out over 10 steps.

* **Project Category:** 🖼️ Image Processing (پردازش تصویر)


---

## 👥 Group Information

* **Group Manager (نماینده گروه):** Mohammad Ali Najafzadeh

| Name                        | GitHub Repository                               |
| :-------------------------- | :---------------------------------------------- |
| **Mohammad Ali Najafzadeh** | [GitHub Link](https://github.com/ma-najafzadeh22/ai-lab-g2-mohammad-ali-najaf-zadeh/) |
| **Amir Hossein Hasani**     | [GitHub Link](https://github.com/rezolens/ai-lab-g3-step1-reza-dehghani/) |
| **Reza Dehghani**           | [GitHub Link](https://github.com/rezolens/ai-lab-all-step-reza-dehghani/tree/main) |
| **Amir Hossein Noruzi**     | [GitHub Link](https://github.com/nrzAmirHo3in/ai-lab-g3-step1-amirhossein-noroozi/) |


---

## 🎯 Step 1: Problem Definition & PEAS

### 1. Problem Definition
The objective of this project is to design, train, and evaluate an intelligent image classification agent capable of accurately recognizing handwritten digits (from `0` to `9`) from grayscale input images (such as the MNIST dataset) using Neural Networks in **PyTorch**.

### 2. PEAS Specification
Based on the nature of the **Handwritten Digit Recognition** problem, the PEAS components of our intelligent agent are defined as follows:

* **🏁 Performance Measure (معیار عملکرد):**
  * **Classification Accuracy:** Percentage of correctly predicted digit labels on the test set.
  *  **Inference Speed:** computation time per image.
* **🌍 Environment (محیط):**
  * A dataset/stream of 2D grayscale images of handwritten digits (e.g., $28 \times 28$ pixel grids) collected from various writers.
* **🛞 Actuators (عملگرها):**
  * Outputting the predicted digit class label $\ \{0, 1, \dots, 9\}$ along with the probability distribution (confidence scores ) over all 10 classes.
* **📡 Sensors (حسگرها):**
  * Digital image input reader that captures the 2D matrix of pixel intensity values or a File I/O stream or memory buffer

---

## 🌐 Environment Properties (ویژگی‌های محیط مسئله)

**Task Environment Properties:**

- **Fully vs. Partially Observable:** Fully observable (the digit grid contains all available static information).

- **Deterministic vs. Stochastic:** Deterministic (same image matrix input produces the same output).

- **Episodic vs. Sequential:** Episodic (classifying image *N* does not influence image *N+1*).

- **Static vs. Dynamic:** Static (the image does not change while the agent is inferring).

- **Discrete vs. Continuous:** Discrete (fixed pixel grids and 10 discrete target classes).
