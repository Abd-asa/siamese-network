# Siamese Network for Face Verification

This project implements a **Siamese Neural Network** for image verification tasks, such as checking whether two images belong to the same class (e.g., face verification) using **TensorFlow** and **Keras**.

---

## 🚀 Features

- **Siamese Architecture** for comparison-based learning
- **Image Preprocessing** for resizing, augmentation, and normalization
- **Real-time Verification** using the webcam
- **Confusion Matrix, ROC Curve, Precision, Recall** metrics

---

## 📁 Project Structure

```
siamese-network/
├── code.ipynb                  # Main code file for training and verification
├── requirements.txt         # List of dependencies
├── README.md                # Project documentation
├── models/                  # Folder to store the trained model
└── media/                   # Output images
    ├── confusion_matrix.jpeg # Confusion Matrix plot
    └── roc_curve.jpeg       # ROC Curve plot
└── data/                    # Folder to store training images
    ├── positive/            # Folder for positive images
    ├── negative/            # Folder for negative images
    └── anchor/              # Folder for anchor images
```

---

## 🧠 High-Level Explanation of the Code

### **Training the Model:**

1. **Data Collection**:
   - **Anchors**: These are reference images that the model compares other images to.
   - **Positives**: Images from the same class as the anchor.
   - **Negatives**: Images from a different class than the anchor.

2. **Data Augmentation**:
   - To improve the model's robustness, **augmentation** techniques such as random brightness, contrast adjustments, and flipping are applied to the images.

3. **Model Architecture**:
   - The **Siamese Network** consists of two identical CNN branches that process the anchor and validation images. These branches extract feature embeddings, and the **distance** between the embeddings is calculated.
   - The model is trained to predict a `1` for positive pairs (same class) and a `0` for negative pairs (different class).

4. **Training Process**:
   - During training, the model learns from batches containing anchor, positive, and negative pairs. The **binary cross-entropy loss** function is used, and the model is updated using the **Adam optimizer**.

---

### **Verification Step:**

After training:

1. **Verification Using `input_image` and `verification_images`**:
   - During verification, the model takes the **`input_image`** and compares it against 50 **`verification_images`**. If the similarity score exceeds a set threshold, the images are considered a match.

2. **Real-time Verification**:
   - A real-time verification is done using the webcam. The **input image** is captured, and when 'v' is pressed, it is compared against the `verification_images`. The model will output whether the input image matches any of the verification images based on the similarity score.

---

## 📈 Results Preview

### ⏱ Model Performance Metrics

![Confusion Matrix](media/res_1.jpeg)

---

## ▶️ How to Run

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/siamese-network.git
cd siamese-network
```
### 2. Install dependencies
```bash
pip install -r requirements.txt
```
### 3. Launch Jupyter Notebook
#### If Jupyter is installed, you can launch the notebook with:

```bash
jupyter notebook
```

#### Then open the **siamese-network.ipynb** notebook from your browser.

---

## 👤 Author

**AbdelRahman A.**

- Computer Engineering graduate interested in Deep Learning, Computer Vision, and Autonomous Vehicles
- GitHub: [Abd-asa](https://github.com/Abd-asa)
- Email: [AbdelRahman.s.abdalla@gmail.com](mailto:AbdelRahman.s.abdalla@gmail.com)
