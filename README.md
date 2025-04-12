# Artistic Style Classification and Style Transfer

This project combines classical machine learning and deep learning techniques to perform **artistic style classification** and **neural style transfer**. It was created as an academic portfolio piece, practical studying and demonstration of applying computer vision to visual arts.

---

## Project Goals

- Build a robust image classifier that can distinguish between six different painting styles:
  - Baroque
  - Cubism
  - Impressionism
  - Northern Renaissance
  - Post-Impressionism
  - Romanticism

- Apply style transfer to real-world photos, recreating them in the style of one of the above artistic genres.
- Explore explainability techniques (e.g., Grad-CAM) to understand model predictions.

---

## Dataset

The dataset consists of thousands of paintings labeled with artist names and styles. To improve data quality:

- I filtered the dataset to only include artists with a single, dominant style.
- I selected the six most represented styles and balanced the dataset by limiting samples per class.
- Images were resized and organized into folders for training.

---

## Data Analysis and Preprocessing

- Exploratory Data Analysis (EDA) was performed to understand the distribution of artists, styles, and image availability.
- I visualized class imbalance, style frequency, and created a clean folder-based structure for classification.
- Applied basic augmentations and feature extraction (e.g., HOG) for traditional models.

---

## Models and Training

### Classical Models:
- Random Forest Regressor: ~42% accuracy
- SVM: ~43% accuracy

### Deep Learning Models:
- Custom CNN: ~59% accuracy
- ResNet18: **~75% accuracy**
- ResNet50: ~74%
- EfficientNetB2: ~75%

The best-performing model was **ResNet18**, which was saved and used for final inference.

---

## Explainability

To interpret the model's decisions, I implemented **Grad-CAM**, a technique that highlights the image regions the CNN focuses on during classification.

Example: On a graffiti photo, Grad-CAM showed attention on expressive regions, leading the model to (correctly) classify the style as **Post-Impressionism**.

---

## Neural Style Transfer

I implemented the original **Neural Style Transfer** algorithm (Gatys et al.) using a frozen VGG19 network. This allowed me to generate new images that preserve the structure of a photo while imitating the texture and color style of classical paintings.

Examples include:
- Graffiti stylized as Post-Impressionism

---

## Project Structure

art-style-classification/
├── images/
├── models/                  # Saved models (e.g., resnet18.pt)
├── notebooks/               # Jupyter notebooks for training & analysis
└── README.md


