# Module 5

# Project: Applied Neural Networks, Computer Vision, NLP, and AI Solution Design

# 🧠 Part 1 — Neural Network Analysis for Customer Churn Prediction

A complete Deep Learning project focused on building, training, evaluating, and experimenting with a Feed-Forward Artificial Neural Network (ANN) for telecom customer churn prediction using TensorFlow and Keras.

---

# 📌 Project Objective

The main objective of this project is to:

- Understand customer churn behavior
- Perform dataset preprocessing
- Build a Feed-Forward Neural Network
- Train and evaluate the model
- Experiment with hyperparameters
- Analyze model stability and performance

The final model predicts whether a telecom customer is likely to:

- `0 → Remain Retained`
- `1 → Churn`

---

# 📂 Repository Structure

```text
part-1-neural-network-analysis/
│
├── README.md
├── notebook.ipynb
├── requirements.txt
└── results/
    ├── model_comparison_table.png
    └── evaluation_outputs.png
```

---

# 📁 File-by-File Explanation

## 📘 README.md
Contains the complete project explanation:
- project objective
- workflow
- dataset handling
- neural network architecture
- model evaluation
- repository structure
- setup instructions

This file is designed for both:
- technical reviewers
- non-technical readers

---

## 📓 notebook.ipynb
Main implementation notebook containing:

- data loading
- preprocessing
- feature encoding
- train-test split
- neural network construction
- compilation
- training
- evaluation
- hyperparameter experimentation
- result visualization

The notebook follows a step-by-step learning structure.

---

## 📄 requirements.txt
Contains all Python libraries required to run the project successfully. :contentReference[oaicite:0]{index=0}

Example libraries:
- TensorFlow
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

The notebook depends on these libraries for:
- data preprocessing
- model building
- visualization
- evaluation metrics

---

## 📂 results/
Stores generated output artifacts and evaluation visuals.

---

# 📊 Dataset Information

## Dataset Used
```text
customer_churn_nn.csv
```

## Dataset Reference File
```text
data_dictionary.md
```

Dataset reference details: :contentReference[oaicite:1]{index=1}

---

# 🎯 Dataset Goal

The dataset is used to train a neural network that predicts customer churn.

Target column:

```text
churn
```

Where:
- `1 = Customer Churned`
- `0 = Customer Retained`

---

# 📌 Dataset Features

## 🔹 Categorical Features
- region
- plan_type
- contract_type
- payment_method

## 🔹 Numerical Features
- tenure
- charges
- login_days
- tickets
- delays
- data_usage
- satisfaction
- complaint_recency
- discounts
- referrals

---

# 🚫 Excluded Feature

```text
customer_id
```

This field was treated as a unique identifier and intentionally excluded from model training because identifiers do not contribute meaningful predictive patterns.

---

# ⚙️ Dataset Handling Process

The dataset was handled completely within the notebook using Pandas and Scikit-learn.

---

## 1️⃣ Local Dataset Access

The dataset file was stored locally in the project directory and loaded using:

```python
pd.read_csv("customer_churn_nn.csv")
```

This approach was selected because it:
- simplifies execution
- avoids API dependency
- improves portability
- keeps the project beginner-friendly
- ensures GitHub reproducibility

---

## 2️⃣ Data Cleaning & Inspection

The notebook checks:
- dataset shape
- null values
- data types
- class distribution

This ensures data quality before training.

---

## 3️⃣ Categorical Encoding

Categorical columns were converted into numerical representations because neural networks only process numerical inputs.

Encoding was applied to:
- region
- plan_type
- contract_type
- payment_method

---

## 4️⃣ Feature Scaling

Numerical features were standardized/scaled to:
- improve gradient descent performance
- stabilize training
- accelerate convergence

---

## 5️⃣ Train-Test Split

The dataset was split into:
- Training Data
- Testing Data

This ensures unbiased model evaluation on unseen data.

---

# 🧠 Neural Network Architecture

The project uses a Feed-Forward Artificial Neural Network (ANN).

---

# 🔄 Model Flow

```text
Input Layer
   ↓
Hidden Layer 1 (16 neurons, ReLU)
   ↓
Hidden Layer 2 (8 neurons, ReLU)
   ↓
Output Layer (1 neuron, Sigmoid)
```

---

# ⚡ Activation Functions Used

## 🔹 ReLU (Hidden Layers)
Used because:
- computationally efficient
- avoids vanishing gradients
- improves deep learning performance

---

## 🔹 Sigmoid (Output Layer)
Used for:
- binary classification
- probability output between 0 and 1

---

# ⚙️ Model Compilation Parameters

| Component | Selection |
|---|---|
| Optimizer | Adam |
| Loss Function | Binary Crossentropy |
| Evaluation Metric | Accuracy |

---

# 📈 Why These Parameters Were Chosen

## 🔹 Adam Optimizer
Provides adaptive learning rates and stable convergence.

## 🔹 Binary Crossentropy
Best suited for binary classification problems like churn prediction.

## 🔹 Accuracy Metric
Measures prediction correctness on test data.

---

# 📊 Task 4 — Final Model Evaluation

The final model evaluation is visualized using a confusion matrix.

Generated output file:

```text
results/evaluation_outputs.png
```

---

# 🖼 evaluation_outputs.png

This image contains the confusion matrix generated after testing the final neural network model.

### Purpose
It helps analyze:
- correct predictions
- incorrect predictions
- churn detection performance

### Interpretation

| Actual | Predicted | Meaning |
|---|---|---|
| Retained → Retained | Correct |
| Retained → Churned | False Positive |
| Churned → Retained | False Negative |
| Churned → Churned | Correct |

The final model achieved extremely high prediction accuracy with very few incorrect classifications.

---

# 🧪 Task 5 — Hyperparameter Experimentation

The project includes hyperparameter experiments to compare:
- deeper architectures
- learning rate changes
- model stability

Generated output file:

```text
results/model_comparison_table.png
```

---

# 🖼 model_comparison_table.png

This image summarizes experimental configurations and performance comparisons.

### Experiments Performed

| Configuration | Purpose |
|---|---|
| Baseline Model | Original architecture |
| Deeper Network | More hidden layers |
| High Learning Rate | Faster but unstable learning |

---

# 📌 Key Findings

## ✅ Baseline Model
- Stable
- High accuracy
- Ideal fit

## ✅ Deeper Network
- Similar accuracy
- Stable learning behavior

## ⚠ High Learning Rate
- Reduced accuracy
- Overshooting instability
- Poor convergence

This demonstrates how hyperparameters directly affect neural network behavior.

---

# 📊 Output File Generation

The `.png` result files were generated programmatically inside the notebook using:

- Matplotlib
- Seaborn

Typical workflow:
1. Train model
2. Generate predictions
3. Create evaluation plots
4. Save visual outputs into `/results`

Example:

```python
plt.savefig("results/evaluation_outputs.png")
```

and

```python
plt.savefig("results/model_comparison_table.png")
```

---

# 📦 Dependency Management using requirements.txt

The notebook relies on the `requirements.txt` file to ensure all required libraries are installed consistently. :contentReference[oaicite:2]{index=2}

This improves:
- reproducibility
- portability
- environment consistency
- GitHub usability

Installation command:

```bash
pip install -r requirements.txt
```

Without these dependencies:
- TensorFlow models cannot run
- preprocessing utilities fail
- visualizations cannot be generated

---

# 🛠 Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming Language |
| Pandas | Dataset handling |
| NumPy | Numerical computing |
| Scikit-learn | Preprocessing & splitting |
| TensorFlow / Keras | Neural network implementation |
| Matplotlib | Plot generation |
| Seaborn | Confusion matrix visualization |

---

# ▶️ How to Run the Project

## Step 1 — Clone Repository

```bash
git clone <repository-link>
```

---

## Step 2 — Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Step 3 — Open Notebook

```bash
jupyter notebook
```

Run all notebook cells sequentially.

---

# 🎯 Learning Outcomes

This project demonstrates:

- Artificial Neural Networks
- Feed-Forward Architecture
- Data Preprocessing
- Feature Encoding
- Feature Scaling
- Binary Classification
- Hyperparameter Tuning
- Confusion Matrix Evaluation
- Model Stability Analysis

---

# ✅ Final Conclusion

This project successfully builds a complete neural network pipeline for telecom customer churn prediction.

The notebook demonstrates:
- structured dataset handling,
- ANN architecture design,
- compilation logic,
- evaluation techniques,
- and hyperparameter experimentation

using a beginner-friendly yet technically accurate deep learning workflow.

The project also emphasizes reproducibility through:
- organized repository structure,
- dependency management,
- generated evaluation artifacts,
- and clear documentation.

---