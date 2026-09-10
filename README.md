#  Mobile Phone Price Prediction & Market Analysis

An interactive machine-learning dashboard that analyzes mobile phone specifications and predicts their **price category** using Decision Tree and Random Forest classification models.

The application combines machine learning, data preprocessing, feature engineering, statistical analysis, interactive visualizations, and real-time predictions into a single web dashboard.

##  Project Overview

The goal of this project is to investigate how mobile phone specifications relate to different market price categories and build machine-learning models capable of classifying a phone as:

* **Budget**
* **Mid-Range**
*  **Upper Mid-Range**
*  **Premium**

Users can explore the dataset, analyze hardware trends, compare machine-learning models, and enter phone specifications to receive a predicted price category with probability estimates.

##  Features

###  Mobile Price Predictor

Enter mobile phone specifications such as:

* RAM
* Internal storage
* Battery capacity
* Screen size
* Primary camera
* Front camera
* Processor speed
* Processor cores
* 5G support
* Dual SIM
* Fast charging

The application generates:

* Predicted price category
* Prediction confidence
* Probability distribution across all price categories
* Model used for prediction

###  Machine Learning

The application implements two classification algorithms:

**Decision Tree**

* Gini impurity-based splitting
* Configurable tree depth and minimum sample requirements
* Feature importance calculation

**Random Forest**

* Multiple decision trees
* Bootstrap sampling
* Random feature selection at each split
* Aggregated predictions
* Feature importance analysis

The models are trained using an **80/20 stratified train-test split**, ensuring each price category is represented in the test partition.

The best model is selected dynamically using weighted F1 score, with accuracy used as the secondary criterion when F1 scores are tied.

###  Feature Engineering

In addition to the original hardware specifications, the application derives additional features:

* **Memory Capacity Score**
* **Camera Capability Score**
* **CPU Processing Index**
* **Connectivity Score**
* **Hardware Feature Count**

These engineered features are calculated from hardware specifications without directly using the target price category.

###  Model Evaluation

The model-performance dashboard provides:

* Accuracy
* Macro precision
* Macro recall
* Macro F1
* Weighted precision
* Weighted recall
* Weighted F1
* Per-category metrics
* Multiclass confusion matrix
* Feature importance rankings

###  Mobile Market Analysis

The dashboard provides interactive analysis of:

* RAM distribution
* Internal storage distribution
* Battery capacity distribution
* Primary camera resolution
* 5G adoption
* Fast-charging adoption
* Price-category distribution
* Brand and hardware statistics

The application also generates automated insights from the dataset.

##  Project Structure

```text
src/
├── components/
│   ├── ChartCard.tsx
│   ├── ConfusionMatrix.tsx
│   ├── FeatureImportanceChart.tsx
│   ├── MobileDetailsModal.tsx
│   ├── MobileTable.tsx
│   ├── ModelMetricsTable.tsx
│   ├── PredictionResultCard.tsx
│   ├── PricePredictionForm.tsx
│   └── ...
│
├── ml/
│   ├── decisionTree.ts
│   ├── randomForest.ts
│   ├── modelTraining.ts
│   ├── preprocessing.ts
│   └── featureEngineering.ts
│
├── pages/
│   ├── Dashboard.tsx
│   ├── PricePredictor.tsx
│   ├── MobileAnalysis.tsx
│   └── ModelPerformance.tsx
│
├── services/
├── utils/
├── types.ts
├── App.tsx
└── main.tsx

public/
└── data/
    └── mobile_phones.csv
```

##  Machine Learning Pipeline

```text
Mobile Phone Dataset
        ↓
Data Cleaning
        ↓
Duplicate Removal
        ↓
Missing Value Imputation
        ↓
Feature Engineering
        ↓
Stratified 80/20 Train-Test Split
        ↓
┌───────────────────┐
│                   │
▼                   ▼
Decision Tree    Random Forest
│                   │
└─────────┬─────────┘
          ↓
    Test Predictions
          ↓
 Performance Metrics
          ↓
 Best Model Selection
          ↓
 Price Category Prediction
```

##  Data Preprocessing

The preprocessing pipeline performs several steps before model training:

1. Removes empty records.
2. Removes duplicate records based on brand, model, RAM and storage.
3. Converts numeric fields into usable numerical values.
4. Converts binary fields such as 5G, Dual SIM and fast charging into `0/1`.
5. Handles missing numerical values using dataset medians.
6. Validates and maps price-category labels.
7. Generates engineered features.

##  Tech Stack

### Frontend

* React
* TypeScript
* Vite
* Tailwind CSS
* Recharts
* Lucide React
* Motion

### Machine Learning

* Custom Decision Tree implementation
* Custom Random Forest implementation
* Custom feature engineering
* Custom classification metrics

### Data & Utilities

* PapaParse
* jsPDF
* html2canvas

##  Getting Started

### Prerequisites

* Node.js
* npm

### Installation

Clone the repository:

```bash
git clone <your-repository-url>
cd mobile-phone-price-prediction
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The application will be available through the local Vite development server.

### Production Build

```bash
npm run build
```

### Type Checking

```bash
npm run lint
```

##  Machine Learning Configuration

The current training configuration uses:

### Decision Tree

```text
Maximum depth: 5
Minimum samples split: 3
Minimum samples leaf: 2
```

### Random Forest

```text
Number of estimators: 18
Maximum depth: 5
Minimum samples split: 3
Minimum samples leaf: 2
```

The Random Forest also performs bootstrap sampling and feature subsampling at each tree split.

## Price Categories

| Category        | Description                  |
| --------------- | ---------------------------- |
| Budget          | Entry-level mobile phones    |
| Mid-Range       | Mainstream consumer devices  |
| Upper Mid-Range | Higher-specification devices |
| Premium         | High-end flagship devices    |

##  Project Goals

This project demonstrates how machine learning can be integrated into a modern interactive web application to:

* Analyze consumer electronics data
* Discover relationships between hardware specifications and price categories
* Compare classification algorithms
* Visualize model performance
* Generate data-driven insights
* Provide interactive predictions

## 🔬 Future Improvements

Potential improvements include:

* Add additional classification algorithms such as XGBoost or SVM
* Add hyperparameter tuning
* Add cross-validation
* Use a fixed random seed for reproducible results
* Add ROC-AUC and precision-recall curves
* Add model export/import
* Add historical model comparison
* Improve calibration of prediction probabilities
* Add automated dataset upload
* Deploy the application publicly

##  License

Add your preferred open-source license here, such as MIT.

---

###  Author

**Preksha K**

Built as a machine-learning and data-analysis project combining frontend development, data visualization, and classification modeling.
# mobile-price-prediction
# Mobile Phone Price Prediction &amp; Market Analysis  An interactive machine-learning dashboard that analyzes mobile phone specifications and predicts their **price category** using Decision Tree and Random Forest classification models.  The application combines machine learning, data preprocessing, feature engineering, statistical analysis
