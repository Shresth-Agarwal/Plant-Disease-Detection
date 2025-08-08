# Plant Disease Detection Framework using YOLOv11

<img width="1918" height="851" alt="Screenshot 2025-08-06 204555" src="https://github.com/user-attachments/assets/75ed268b-1cb3-4f77-a435-68c0b3fb415d" />



This repository contains a complete, end-to-end framework for identifying diseases in plants using a custom-trained **YOLOv11** object detection model. The project features an interactive **Streamlit** dashboard that allows for both live diagnosis via webcam and detailed report generation from uploaded images.

The framework is designed to be plant-agnostic and its effectiveness has been demonstrated through an initial case study on **Plants**. This project showcases a full MLOps lifecycle, from data creation to a user-facing application.

**Explore the live website**: [Plant Disease Detector](https://plant-disease-detection-3j49.onrender.com/)

**Developed by:** [Shresth Agarwal](https://github.com/Shresth-Agarwal) and [K Advaith](https://github.com/KambhampatiAdvaith)

---
##  Project Motivation & Significance

This project was developed to address critical challenges in the cultivation of high-value plants.

*   **The Problem:** Traditional disease monitoring relies on manual inspection, which is slow, labor-intensive, requires expert knowledge, and is not scalable. This often leads to delayed treatment, significant crop loss, and inconsistent product quality.

*   **The Necessity:** There is an urgent need for an accessible, low-cost, and automated solution. This project provides a necessary framework that empowers farmers and researchers to perform rapid and consistent health assessments using simple camera technology.

*   **The Significance:** Solving this problem has a direct impact on:
    *   **Economic Stability:** Protecting crop yields and ensuring the livelihood of farmers.
    *   **Consumer Health:** Guaranteeing the quality and safety of the final therapeutic products.
    *   **Environmental Sustainability:** Enabling targeted treatments (precision agriculture) and reducing the overuse of chemical pesticides.

##  Key Features

- **Plant-Agnostic Framework:** The methodology is designed to be easily adapted to detect diseases in any plant species.
- **Interactive Web Dashboard:** A user-friendly interface built with **Streamlit** supporting two powerful modes:
    - **Image Upload & Report:** Analyze a static image to get a full diagnostic report in HTML and PDF formats.
    - **Live Webcam Detection:** Perform real-time disease detection using a live camera feed, a key add-on feature.
- **Professional Report Generation:** Automatically generates detailed reports including the annotated image, detected conditions, confidence levels, and practical care tips.
- **Custom Model Training:** The project was built on a custom-annotated dataset, demonstrating the full workflow from scratch.

---

## How to Clone and Run This Project

Follow these steps precisely to get the application running on your local machine.

### Prerequisites
- **Git** installed on your system.
- **Anaconda or Miniconda** installed to manage the Python environment.

### Clone the Repository
Open your terminal or command prompt and run the following commands to clone the project and navigate into the directory:
```bash
git clone https://github.com/Shresth-Agarwal/Plant-Disease-Detection.git
cd Plant-Disease-Detection

# Create a new environment named 'yolo_plants' with Python 3.9
conda create --name yolo_plants python=3.9 -y

# Activate the new environment
conda activate yolo_plants

streamlit run app.py --server.port 10000 --server.address 0.0.0.0

``` 

### Framework Methodology

This project can be used as a template to train a detector for any plant. The 3-step methodology is:

1.  **Custom Dataset Creation:** Source and organize images into `images/train` and `images/val` folders, then create corresponding `labels/train` and `labels/val` folders.
2.  **Annotation:** Use a tool like **LabelImg** to draw bounding boxes and save annotations in the `YOLO .txt` format.
3.  **Model Training:** Create a `.yaml` configuration file pointing to your dataset and run the `yolo train` command to create your own `best.pt` model weights.

### Future Work

- **Multi-Plant Model:** Combine the plants main dataset and other datasets to train a single, robust model capable of diagnosing diseases across multiple medicinal plant species.
- **Dataset Expansion:** Significantly enlarge the datasets for each plant to improve accuracy and generalization, particularly for fine-grained or subtle disease types.
- **Edge Deployment:** Optimize and deploy the trained models on low-cost edge devices like a Raspberry Pi or Jetson Nano for real-time, in-field analysis.
