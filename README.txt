<div align="center">

# 🇵🇹 Portuguese Bank Marketing Project

### End-to-end data analysis · Customer subscription prediction · Marketing recommendations

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-F37626?logo=jupyter&logoColor=white)
![Project](https://img.shields.io/badge/Project-PRCP--1000-6C63FF)
![Status](https://img.shields.io/badge/Status-Ready%20to%20Run-2E8B57)

**A practical machine-learning project that helps a bank identify customers who may subscribe to a term deposit.**

[🚀 Quick Start](#-quick-start) · [📂 Project Structure](#-project-structure) · [🧠 Notebook Guide](#-notebook-guide) · [⚠️ Important Modeling Note](#️-important-modeling-note)

</div>

---

## 📌 Table of Contents

<details open>
<summary><strong>Click to expand / collapse sections</strong></summary>

1. [Project Overview](#-project-overview)
2. [Business Problem](#-business-problem)
3. [Project Objectives](#-project-objectives)
4. [Dataset Information](#-dataset-information)
5. [Project Structure](#-project-structure)
6. [Requirements](#-requirements)
7. [Quick Start](#-quick-start)
8. [Notebook Guide](#-notebook-guide)
9. [Machine-Learning Workflow](#-machine-learning-workflow)
10. [Evaluation Metrics](#-evaluation-metrics)
11. [Important Modeling Note](#️-important-modeling-note)
12. [Expected Outputs](#-expected-outputs)
13. [Troubleshooting](#-troubleshooting)
14. [Business Recommendations](#-business-recommendations)
15. [Project Limitations](#-project-limitations)

</details>

## 🎯 Project Overview

This project analyzes direct-marketing campaign data from a Portuguese banking institution. The bank contacted existing customers by telephone to promote **term-deposit subscriptions**.

The supplied dataset covers campaigns conducted from **May 2008 to November 2010**. The notebook explores customer and campaign characteristics, prepares the data, compares classification models, and demonstrates how customer subscription probabilities can support campaign planning.

> **Main question:** Based on information available before a marketing call, which customers are more likely to subscribe to a term deposit?

## 🏦 Business Problem

Calling every customer can consume time and marketing resources. The bank needs a data-supported way to prioritize its customer outreach.

This project uses historical campaign data to:

- Understand customer characteristics and campaign outcomes.
- Identify patterns associated with term-deposit subscriptions.
- Train models that estimate the probability of subscription.
- Compare model performance using metrics suitable for an imbalanced target.
- Translate analytical findings into practical marketing recommendations.

## ✅ Project Objectives

| Task | Objective | Deliverable |
|---|---|---|
| **Task 1 — Data analysis** | Inspect, clean, summarize and visualize the supplied data. | EDA tables, charts and observations |
| **Task 2 — Prediction** | Build a classification model to estimate whether a customer may subscribe. | Trained pipelines and model comparison |
| **Task 3 — Recommendations** | Suggest ways the bank marketing team can use the findings. | Business recommendations and threshold discussion |
| **Additional requirement** | Document model comparison and data challenges. | Evaluation report and challenge/solution table |

## 📊 Dataset Information

**Dataset file used by the notebook**

```text
PRCP-1000-ProtugeseBank/Data/bank-additional/bank-additional-full.csv
```

The dataset archive contains several CSV files. This project is configured to use **`bank-additional-full.csv`**, as specified in the project brief.

### Target variable

| Column | Meaning | Values |
|---|---|---|
| `y` | Whether the customer subscribed to a term deposit | `yes`, `no` |

### Input variables

The dataset includes customer profile, current campaign, previous campaign, and economic-context attributes.

| Category | Fields |
|---|---|
| Customer profile | `age`, `job`, `marital`, `education` |
| Financial status | `default`, `housing`, `loan` |
| Current contact | `contact`, `month`, `day_of_week`, `duration` |
| Campaign history | `campaign`, `pdays`, `previous`, `poutcome` |
| Economic context | `emp.var.rate`, `cons.price.idx`, `cons.conf.idx`, `euribor3m`, `nr.employed` |

**CSV format:** The notebook reads the dataset with `sep=';'`, which is required for this file.

## 📂 Project Structure

After extracting the project package, keep the notebook and supplied dataset ZIP in the same folder:

```text
Portuguese_Bank_Project/
│
├── README.md
├── Portuguese_Bank_Marketing_Project.ipynb
└── PRCP-1000-ProtugeseBank.zip
```

When the notebook runs, it checks whether the expected CSV is already available. If it is missing, the notebook extracts the dataset archive into the working folder.

The expected dataset location after extraction is:

```text
Portuguese_Bank_Project/
│
├── Portuguese_Bank_Marketing_Project.ipynb
├── PRCP-1000-ProtugeseBank.zip
└── PRCP-1000-ProtugeseBank/
    └── Data/
        └── bank-additional/
            └── bank-additional-full.csv
```

> **Important:** Do not rename the dataset archive unless you also update the ZIP path in the notebook.

## 💻 Requirements

### Software

- Python 3.9 or later recommended
- Jupyter Notebook or JupyterLab
- The notebook and dataset ZIP from this project package

### Python libraries

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning and analysis |
| `numpy` | Numerical operations |
| `matplotlib` | Charts and visualizations |
| `seaborn` | Statistical visualizations |
| `scikit-learn` | Preprocessing, model training and evaluation |
| `joblib` | Saving the trained model |

## 🚀 Quick Start

### Option A — Run with Jupyter Notebook

1. Download `Portuguese_Bank_Project_Full_Package.zip`.
2. Extract the package to a folder on your computer.
3. Open Anaconda Navigator, Jupyter Notebook, or JupyterLab.
4. Navigate to the extracted project folder.
5. Open `Portuguese_Bank_Marketing_Project.ipynb`.
6. Run the notebook from the first cell to the last cell.

### Option B — Run from a terminal

Open a terminal in the project folder and install the dependencies:

```bash
python -m pip install pandas numpy matplotlib seaborn scikit-learn joblib
```

Start Jupyter:

```bash
jupyter notebook
```

Then open `Portuguese_Bank_Marketing_Project.ipynb` in the browser and select **Run → Run All Cells**.

### Option C — Install dependencies inside the notebook

Run this in a notebook cell if the libraries are not installed:

```python
%pip install pandas numpy matplotlib seaborn scikit-learn joblib
```

After installation, restart the kernel if Jupyter asks you to, then run the notebook again.

### ▶️ Execution checklist

- [ ] Extract the project ZIP.
- [ ] Confirm the notebook and dataset ZIP are in the same folder.
- [ ] Install the required libraries.
- [ ] Open the `.ipynb` notebook.
- [ ] Select the correct Python kernel.
- [ ] Run all cells from top to bottom.
- [ ] Review the charts, model comparison and final observations.
- [ ] Check the generated `portuguese_bank_outputs` folder.

## 📓 Notebook Guide

The notebook is organized into the following stages:

| Stage | Notebook section | What happens |
|---:|---|---|
| 1 | Imports and reproducibility | Imports packages and sets up the analysis environment. |
| 2 | Locate, extract and load dataset | Finds the ZIP, extracts it when needed, and loads the specified CSV. |
| 3 | Data understanding and quality checks | Checks dimensions, data types, missing values and unique values. |
| 4 | Descriptive statistics and EDA | Summarizes variables and visualizes customer/campaign patterns. |
| 5 | Key observations | Calculates subscription rate and examines selected categories. |
| 6 | Data preparation and leakage prevention | Separates target and predictors and excludes `duration`. |
| 7 | Preprocessing and candidate models | Builds preprocessing pipelines and candidate classifiers. |
| 8 | Train and compare models | Fits models and compares their test-set metrics. |
| 9 | Select and evaluate candidate | Evaluates the leading model with classification metrics and curves. |
| 10 | Threshold analysis | Shows how changing the probability cutoff affects precision and recall. |
| 11 | Explain the selected model | Uses permutation importance to examine influential features. |
| 12 | Business recommendations | Connects the analysis to campaign-planning actions. |
| 13 | Challenges and techniques | Documents data challenges and the techniques used to address them. |
| 14 | Save model and outputs | Saves the fitted model and supporting outputs. |
| 15 | Score example customers | Demonstrates probability scoring for sample customer records. |
| 16 | Final conclusion | Summarizes the analysis and modeling workflow. |

## 🔄 Machine-Learning Workflow

```mermaid
flowchart TD
    A["Supplied dataset ZIP"] --> B["Extract bank-additional-full.csv"]
    B --> C["Data inspection and quality checks"]
    C --> D["Exploratory data analysis"]
    D --> E["Separate target y from input features"]
    E --> F["Remove duration to prevent leakage"]
    F --> G["Train/test split"]
    G --> H["Preprocessing pipeline"]
    H --> I["Train candidate classifiers"]
    I --> J["Compare PR-AUC, ROC-AUC, recall, precision and F1"]
    J --> K["Select candidate and review threshold"]
    K --> L["Explain feature importance"]
    L --> M["Save model and outputs"]
    M --> N["Score example customers"]
    N --> O["Marketing recommendations"]
```

## 📈 Evaluation Metrics

The target variable is imbalanced: subscription responses are less frequent than non-subscription responses. Therefore, accuracy alone should not be used to decide which model is best.

The notebook reports multiple metrics:

| Metric | What it tells us |
|---|---|
| **PR-AUC** | How well the model ranks the positive class across precision-recall trade-offs. |
| **ROC-AUC** | How well the model separates positive and negative cases across thresholds. |
| **Precision** | Of the customers predicted as subscribers, how many actually subscribed? |
| **Recall** | Of all actual subscribers, how many did the model identify? |
| **F1-score** | Harmonic balance between precision and recall. |
| **Confusion matrix** | Counts correct and incorrect predictions by class. |

**Primary model-ranking metric:** PR-AUC. The notebook uses it because the positive class (`yes`) is the minority class. The selected model should still be reviewed against business needs, especially the cost of missed subscribers versus unnecessary calls.

## ⚠️ Important Modeling Note

### Why `duration` is excluded

The `duration` column records how long the phone call lasted. It is only known after the call has taken place. Using it to predict subscription **before** a call would give the model information that the marketing team does not have at decision time.

This is a form of **data leakage**.

For that reason:

- `duration` is excluded from the production prediction features.
- The model is intended to estimate subscription likelihood before a call, using the other available input fields.
- Any benchmark that includes `duration` would answer a different question and should not be confused with realistic pre-call targeting.

### Special interpretation of `pdays`

The project brief explains that `pdays = 999` means the customer was not previously contacted in an earlier campaign. This is a special category/code, not an ordinary elapsed-day count. Interpret it accordingly when discussing results.

## 📁 Expected Outputs

After successful execution, the notebook creates:

```text
portuguese_bank_outputs/
│
├── best_portuguese_bank_model.joblib
└── [supporting outputs saved by the notebook]
```

The trained model is saved as a serialized scikit-learn pipeline. The pipeline includes the preprocessing and model steps needed to score new customer records with the same input feature structure.

**Note:** Model metrics, plots and final observations are calculated when you execute the notebook. They are not pre-filled as fixed results in this README.

## 🛠️ Troubleshooting

<details>
<summary><strong>1. FileNotFoundError: dataset CSV not found</strong></summary>

- Confirm that `PRCP-1000-ProtugeseBank.zip` is in the same folder as the notebook.
- Confirm the archive has not been renamed.
- Run the dataset-loading cell again.
- Verify the expected internal path:

```text
PRCP-1000-ProtugeseBank/Data/bank-additional/bank-additional-full.csv
```

</details>

<details>
<summary><strong>2. ModuleNotFoundError: No module named ...</strong></summary>

Install the missing packages:

```python
%pip install pandas numpy matplotlib seaborn scikit-learn joblib
```

Restart the notebook kernel and rerun the cells.

</details>

<details>
<summary><strong>3. The notebook is using the wrong Python environment</strong></summary>

In Jupyter, check **Kernel → Change Kernel** and select the environment where the dependencies were installed. If needed, install Jupyter and the dependencies in the same environment.

</details>

<details>
<summary><strong>4. CSV columns appear in one combined field</strong></summary>

This dataset uses semicolon-separated values. The expected loading method is:

```python
pd.read_csv(csv_path, sep=";")
```

Do not remove `sep=';'` unless the source file format has changed.

</details>

<details>
<summary><strong>5. Charts or model results do not appear</strong></summary>

- Run cells in order from top to bottom.
- Check whether an earlier cell raised an error.
- Confirm that the notebook kernel is still running.
- If necessary, use **Kernel → Restart Kernel and Run All Cells**.

</details>

## 💡 Business Recommendations

Use the actual outputs generated by the notebook to support decisions. Potential actions for the bank marketing team include:

1. **Prioritize customer outreach:** Rank customers by predicted subscription probability instead of contacting everyone in the same order.
2. **Choose a suitable threshold:** Balance the number of likely subscribers identified against the number of calls spent on customers who do not subscribe.
3. **Review campaign history:** Examine how previous campaign outcomes relate to current subscription behavior.
4. **Study customer segments:** Use the EDA results to identify segments with comparatively higher subscription rates.
5. **Monitor performance:** Track precision, recall and campaign conversion after deployment; retrain or recalibrate when customer behavior changes.
6. **Use responsible outreach:** Apply appropriate customer-contact permissions, privacy requirements and bank policies.

These are recommendations to investigate and validate—not guaranteed causes of subscription.

## 🔍 Project Limitations

- The dataset represents historical campaigns from 2008–2010; current customer behavior and economic conditions may differ.
- Predictive relationships do not prove that a particular customer attribute causes subscription.
- Model quality on a held-out test set does not guarantee the same performance in a live campaign.
- The best probability threshold depends on campaign capacity, contact costs and business priorities.
- Before real-world use, the model should undergo further validation, monitoring, fairness review, privacy review and approval under the bank's governance processes.

## 👤 Project Details

| Field | Details |
|---|---|
| Project name | Portuguese Bank Marketing Project |
| Project code | PRCP-1000-PortugeseBank |
| Domain | Finance / Banking |
| Main task | Term-deposit subscription prediction |
| Development environment | Python and Jupyter Notebook |
| Main deliverable | `Portuguese_Bank_Marketing_Project.ipynb` |

---

<div align="center">

### ⭐ Ready to explore the data?

**Open `Portuguese_Bank_Marketing_Project.ipynb` and run all cells from top to bottom.**

*Built for data analysis, machine-learning practice and business decision support.*

</div>
