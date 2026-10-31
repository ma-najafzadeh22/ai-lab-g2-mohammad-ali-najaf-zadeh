## My task was finding a suitable dataset for this project.


# Dataset: MADBase (Arabic-Indic Handwritten Digits)

## Overview
- **What it is:** Handwritten digits 0-9 written in Arabic-Indic numerals (٠ ١ ٢ ٣ ٤ ٥ ٦ ٧ ٨ ٩).
- **Size:** 70,000 grayscale images of 28x28 pixels, written by 700 people. Official split: 60,000 train / 10,000 test.
- **Original source:** AUC (American University in Cairo) data center, https://datacenter.aucegypt.edu/shazeem/
- **Copy used:** Hugging Face mirror, https://huggingface.co/datasets/MagedSaeed/MADBase

## Why I chose it
- **Real handwriting:** Unlike synthetic or GAN-generated digit sets, the images come from real writers, so accuracy results are meaningful.
- **A standard scale:** The 28x28 grayscale format and 60k/10k split mean it trains in minutes on a laptop or a free Colab GPU.
- **Not MNIST, similar difficulty:** The digit shapes differ from Western digits, and some look alike (e.g. ٤ / ٣ / ٢), which makes it more interesting to analyse.


## Right of use
- **Terms:** The dataset card states it is "publicly available for research" and that any work using it must cite the original paper. No formal open-source license (e.g. MIT, CC-BY) is stated.
- **My use:** Non-commercial, educational use for a university class project, which falls within the stated research use.

- **Limits:** I will not redistribute the data as my own or use it commercially without checking the original terms with the authors.
- **Known issues:** The Hugging Face copy lists 69,998 rows instead of 70,000, and its dataset card is mostly empty. For this reason I cite the original source below.

## Citation
> El-Sherif, E. A., & Abdelazeem, S. (2007). A Two-Stage System for Arabic Handwritten Digit Recognition Tested on a New Large Database. *Artificial Intelligence and Pattern Recognition*, 237-242.

