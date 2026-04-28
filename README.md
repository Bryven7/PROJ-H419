# PROJ-H419
Bring the student to develop his or her capacity to manage a personal project, integrating technical aspects related to his or her specialty as well as the transversal aspects of organization, communication and autonomy.

## Malaria Detection in Blood Cell Images using Deep Learning

### 📝 Project Overview
This project focuses on the design and implementation of a **Deep Learning** solution to automate the detection of malaria parasites in blood smear images. Using a Convolutional Neural Network (CNN), the system is trained to distinguish between infected and uninfected cells with high clinical reliability.

The work builds upon and improves an existing Kaggle project by introducing architectural refinements, advanced data augmentation, and systematic hyperparameter tuning monitored via TensorBoard.

### 🧬 Dataset & Pre-processing
* **Source**: NIH Malaria Dataset (27,558 cell images).
* **Target Classes**: Parasitized vs. Uninfected.
* **Image Resolution**: Evaluated multiple resolutions, with **128x128 pixels** providing the best balance between feature retention and computational efficiency.
* **Data Augmentation**: Implemented using the `Albumentations` library, including:
    * Vertical and Horizontal Flips
    * Rotations (up to 180°)
    * Gaussian Blur and Random Brightness/Contrast adjustments.

### 🏗️ Model Architecture
The final architecture follows an optimized "Information Bottleneck" design:
* **Convolutional Base**: 3 layers with $3 \times 3$ filters and **ReLU** activation.
* **Spatial Reduction**: Max-Pooling layers for feature aggregation.
* **Classifier**: Fully connected layers with **Dropout (0.5)** to prevent overfitting.
* **Optimization**: **Adam** optimizer with **Binary Cross-Entropy** loss function.

### 📊 Performance Results
The project compared over 160 model configurations. Two specific versions were highlighted:

| Metric | Model 2 (Precision Focus) | Model 10 (Recall Focus) |
| :--- | :---: | :---: |
| **Accuracy** | **96.17%** | 96.08% |
| **Precision** | **97.12%** | 96.57% |
| **Recall** | 95.28% | **95.68%** |
| **F1-Score** | **96.19%** | 96.12% |

*Note: **Model 10** is prioritized for medical screening to minimize False Negatives, ensuring fewer infected patients go undiagnosed.*

### 🛠️ Technologies Used
* **Language**: Python
* **Deep Learning**: TensorFlow / Keras
* **Tracking**: TensorBoard
* **Augmentation**: Albumentations
* **Data Management**: Custom `DataGenerator` for memory-efficient loading.

### 📂 Repository Content
* `detecting-malaria-cnn copy.ipynb`: The main Jupyter Notebook containing the data exploration, training pipeline, and performance analysis.
* `PROJMAST1.pdf`: Detailed project report.

---
**Author**: François Bryan