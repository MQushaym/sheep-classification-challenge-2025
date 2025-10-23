# Kaggle Competition: Sheep Classification Challenge 2025

This repository contains the code for my submission to the **[Sheep Classification Challenge 2025](https://www.kaggle.com/competitions/sheep-classification-challenge-2025)** on Kaggle.

The project is a complete PyTorch pipeline for a multi-class image classification problem, implementing training, validation (using Stratified K-Fold), and inference to produce a final submission file.

---

## 📊 Final Results

This solution achieved a **Private Score of 0.94826**.

The notebook submitted was "Version 5," which performed significantly better than the initial submission, demonstrating strong generalization to the private test set.

| Submission Version | Public Score | Private Score |
| :--- | :---: | :---: |
| **Version 5 (Final)** | 0.85587 | **0.94826** |
| Initial Submission | 0.82518 | 0.91549 |

---

## ⚙️ Methodology

The core of this project is a PyTorch-based training and inference pipeline.

1.  **Framework:** PyTorch
2.  **Model:** A pre-trained model from the `timm` (PyTorch Image Models) library was used as the backbone.
3.  **Validation Strategy:** **Stratified K-Fold** (with 5 splits) was used to ensure the model trains on all data and that the class distribution is maintained in each fold.
4.  **Data Augmentation:** The `albumentations` library was used to apply various transforms (e.g., Flips, Rotations) to the training data, preventing overfitting and improving model robustness.
5.  **Inference:**
    * The final prediction is an ensemble (average) of the predictions from the 5 models trained (one for each fold).
    * **Test Time Augmentation (TTA)** was applied during inference, where predictions are made on multiple augmented versions of each test image and then averaged. This further boosts the final accuracy.
6.  **Output:** The notebook generates a `submission.csv` file in the format required by the competition.

---

## 🛠️ Key Technologies Used

* **PyTorch** (Core deep learning framework)
* **timm** (For loading pre-trained SOTA models)
* **scikit-learn** (For `StratifiedKFold` and `f1_score`)
* **pandas** (For handling CSV files)
* **albumentations** (For advanced image augmentation)
* **OpenCV (cv2)** (For image loading)
* **Kaggle Notebooks** (Environment)

---

### 📞 Contact

* **Name:** Meshal AL-Qushaym
* **Email:** meshalqushim@outlook.com
* **Kaggle Profile:** [kaggle.com/meshalfalah](https://www.kaggle.com/meshalfalah)
