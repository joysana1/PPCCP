# Privacy-Preserving Customer Churn Prediction (PPCCP)

This repository contains the implementation of our paper **"Privacy-Preserving Customer Churn Prediction Model in the Context of Telecommunication Industry"**.  
The framework combines **DP-WGAN** with **adaptive Weight of Evidence (aWOE)** to generate privacy-preserving synthetic data while improving predictive performance.  

---

## Repository Structure

├── data/ # Uploaded datasets (Dataset-2 and Dataset-3)
├── classifiers/ # Classifier training, validation, and evaluation scripts
│ ├── logistic_regression.py
│ ├── random_forest.py
│ ├── xgboost.py
│ └── ...
├── GAN_PRE_1_70per_training_30_per_original_testing-dataset-10000.ipynb
├── GAN_PRE_1_70per_training_30_per_original_testing_data_5000.ipynb
├── GAN_PRE_1_70per_training_30_per_original_testing_data_7043.ipynb
├── GAN_Training.ipynb
└── README.md


---

## Datasets

- **Dataset-1**: Not uploaded due to large volume (available upon request).  
- **Dataset-2 and Dataset-3**: Provided in the `data/` folder.  

---

## Usage

### 1. Data Preprocessing and Splitting
The following notebooks handle preprocessing and creating training/testing splits for different datasets:
- `GAN_PRE_1_70per_training_30_per_original_testing-dataset-10000.ipynb`  
- `GAN_PRE_1_70per_training_30_per_original_testing_data_5000.ipynb`  
- `GAN_PRE_1_70per_training_30_per_original_testing_data_7043.ipynb`  

Each notebook splits the dataset into **70% training** and **30% testing**.

---

### 2. Synthetic Data Generation
To generate synthetic data using DP-WGAN:
- Run `GAN_Training.ipynb`.  
- This notebook uses the [`private-data-generation`](https://github.com/joysana1/PPCCP/tree/main/private-data-generation) library to train the GAN under differential privacy.  

---

### 3. Model Training and Evaluation
The `classifiers/` folder contains scripts for training and evaluating different classifiers (e.g., Logistic Regression, Random Forest, XGBoost).  

Each script:
1. Loads either real or synthetic data.  
2. Trains the classifier.  
3. Reports evaluation metrics (Accuracy, Precision, Recall, F1-score, AUC, etc.).  

---

### 4. Reproducing Key Results
To reproduce the main results from the paper:

1. **Preprocess dataset-2 or dataset-3** using the corresponding preprocessing notebook.  
2. **Generate synthetic data** with `GAN_Training.ipynb`.  
3. **Train and evaluate classifiers** using the scripts in `classifiers/`.  
4. **Compare results** between real and synthetic data.  

---

## Requirements

Install dependencies with:  

```bash
pip install -r requirements.txt

Key libraries:

Python 3.8+

numpy, pandas, scikit-learn

torch, opacus

private-data-generation

matplotlib, seaborn


##Citation

If you use this repository in your research, please cite our paper:

@article{jdk_PPCCP_2025,
  title={Privacy-Preserving Customer Churn Prediction Model in the Context of Telecommunication Industry},
  author={Sana, Joydeb Kumar and Rahman,  M Sohel and Rahman, M Saifur},
  year={2025}
}


