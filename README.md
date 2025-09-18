# 🗑️ Smart Waste Classification System (CNN)

This project implements a **Smart Waste Management System** using **Convolutional Neural Networks (CNNs)** and digital image processing. The goal is to classify waste items (e.g., plastic, paper, glass, metal, organic) based on images, generate statistics, and simulate sorting actions.

---

## 🚀 Features

* Image preprocessing & augmentation (OpenCV + Keras ImageDataGenerator)
* CNN-based classification (Transfer Learning with **MobileNetV2**)
* Training with callbacks: EarlyStopping, ModelCheckpoint, ReduceLROnPlateau
* Accuracy & loss plots, confusion matrix visualization
* Statistical logging (JSON/CSV reports of waste counts)
* Single-image prediction demo with OpenCV visualization
* Optional Raspberry Pi integration for actuator control (servo motor)

---

## 📂 Project Structure

```
├── dataset/               # Your dataset (one folder per class)
│   ├── plastic/
│   ├── paper/
│   ├── glass/
│   ├── metal/
│   └── organic/
├── models/                # Saved models (best_model.h5, final_model.h5)
├── outputs/               # Logs, plots, confusion matrix, stats
├── waste_classifier.py    # Main training/evaluation/prediction script
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation
```

---

## ⚙️ Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/your-username/smart-waste-classifier.git
   cd smart-waste-classifier
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

---

## 📊 Dataset

Prepare your dataset in this structure:

```
dataset/
  plastic/
    img001.jpg
    img002.jpg
  paper/
  glass/
  metal/
  organic/
```

* One object per image (requirement).
* At least \~100 images per class recommended.
* You can use the [TrashNet dataset](https://github.com/garythung/trashnet) or capture your own.

---

## 🏋️‍♂️ Training

Run training with default parameters:

```bash
python waste_classifier.py --mode train --dataset ./dataset --epochs 20 --batch_size 32
```

Models will be saved in `models/`, plots and stats in `outputs/`.

---

## 📈 Evaluation

Evaluate a trained model:

```bash
python waste_classifier.py --mode eval --dataset ./dataset --model models/best_model.h5
```

Generates:

* `outputs/stats.json` → validation accuracy & class counts
* `outputs/confusion_matrix.png`
* CSV with class distribution

---

## 🔍 Prediction Demo

Classify a single image:

```bash
python waste_classifier.py --mode predict --image path/to/image.jpg --model models/best_model.h5
```

An OpenCV window will show the image with predicted label & confidence.

---

## 🤝 Collaboration (GitHub Requirement)

* Each teammate should work on a **separate module** (preprocessing, classification, statistics, etc.).
* Use **branches & pull requests** for contributions.
* GitHub history will be used for grading.

---

## 🎯 Bonus Features (optional)

* Recyclability detection (recyclable vs non-recyclable)
* Deploying on **Raspberry Pi / Edge devices**
* Hardware sorting demo with **servo motors**

---

## 📜 License

This project is for academic purposes (University of Jaffna, EC9570 – Digital Image Processing assignment). You may adapt and extend it for further research.
