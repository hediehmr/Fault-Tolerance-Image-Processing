# Fault-Tolerance-Image-Processing
# CNN-Based Fault Tolerance for Image Processing

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)](https://tensorflow.org/)
[![Status](https://img.shields.io/badge/Status-Research_Implementation-green.svg)]()

## 📌 Abstract
This repository contains the implementation of an **Approximation-based Fault Tolerance** mechanism for image processing applications. 

Traditional fault tolerance methods like **Duplication With Comparison (DWC)** impose a 100% overhead in execution time and energy, which is often too costly for real-time or resource-constrained systems. Furthermore, DWC is overly strict for image processing, where slight pixel-level variations are often acceptable to the human eye.

**Our Solution:** Instead of full duplication, we employ a lightweight **Convolutional Neural Network (CNN)** as a "Checker". This CNN predicts the expected output class/features. If the main processor's output diverges significantly from the CNN's prediction, a fault is detected. This approach distinguishes between *usable* and *unusable* images rather than just *exact* matches.

## 🚀 Key Results
Based on the experimental results presented in the project report:

- **Performance Gain:** Achieved approximately **30% reduction in execution time** compared to traditional DWC.
- **Reliability:** Maintained a high fault detection rate with **< 4% error rate** (misclassification of unusable images).
- **Efficiency:** Successfully trades off a negligible amount of accuracy for significant performance improvements using Approximate Computing principles.

## 🛠️ Methodology
The project implements the concepts from the paper *"Approximation-based Fault Tolerance in Image Processing Applications"* (Biasielli et al.).

1.  **Fault Injection:** Simulating hardware faults (bit-flips) during image processing.
2.  **CNN Checker:** A lightweight model trained to approximate the image processing task.
3.  **Decision Logic:** Comparing the faulty output with the CNN prediction to decide if the image is "Usable" or "Discarded".

## 📊 Evaluation
The system was tested under different fault injection rates ($d$) and usability thresholds ($U_{th}$).

| Metric | Traditional DWC | Our CNN-Based Approach |
| :--- | :---: | :---: |
| **Overhead** | ~100% (2x Compute) | Low (Inference Cost) |
| **Execution Time** | Baseline | **~30% Faster** |
| **Flexibility** | Rigid (Exact Match) | Flexible (Usability Metric) |

*(Note: Detailed charts regarding execution time and different configurations can be found in the report).*

## 💻 Installation & Usage

### Prerequisites
* Python 3.x
* TensorFlow / Keras
* NumPy
* OpenCV
* Matplotlib

### Running the Project
Since the core implementation is in a Jupyter Notebook:

1.  Clone the repo:
    ```bash
    git clone [https://github.com/hediehmr/Fault-Tolerance-Image-Processing.git](https://github.com/hediehmr/Fault-Tolerance-Image-Processing.git)
    ```
2.  Install dependencies:
    ```bash
    pip install notebook tensorflow numpy opencv-python matplotlib
    ```
3.  Open the notebook:
    ```bash
    jupyter notebook final_fault_project.ipynb
    ```

## 📄 References
This project is an implementation and analysis based on:
> *Matteo Biasielli, et al., "Approximation-based Fault Tolerance in Image Processing Applications"*

## 📧 Contact
**Hedieh Moftakhari Rostamkhani** ML Performance & Systems Engineer  
[hedieh.rm@gmail.com](mailto:hedieh.rm@gmail.com)
