# Kilimo AI - Maize Yield Prediction Model

A machine learning project for predicting maize (corn) yield profitability using Decision Tree and Random Forest classifiers.

## 📋 Overview

**Kilimo** (Swahili for "agriculture") AI is a predictive model that classifies maize farm yields into three profit categories:
- **Low** - Yield below 33rd percentile
- **Medium** - Yield between 33rd and 67th percentile  
- **High** - Yield above 67th percentile

This tool helps farmers and agricultural planners make data-driven decisions about crop management and resource allocation.

---

## 🎯 Features

✅ **Comprehensive Data Pipeline**
- Data cleaning & missing value imputation
- Outlier detection & removal (1st-99th percentile)
- Categorical feature encoding
- Balanced target classes for fair classification

✅ **Two ML Models**
- **Decision Tree** - Interpretable, rule-based predictions
- **Random Forest** - Powerful ensemble with better generalization

✅ **Model Evaluation**
- Train/Test accuracy comparison
- Confusion matrices visualization
- Performance metrics (accuracy, precision, recall)

✅ **Farm Prediction**
- Real-world prediction example showing how to use the trained models
- Easy-to-use interface for new farm data

---

## 📊 Dataset

**Source:** Maize dataset (166,824 samples)

**Features:**
| Feature | Type | Description |
|---------|------|-------------|
| Soil_Type | Categorical | Type of soil (Clay, Silt, Sandy, etc.) |
| Rainfall_mm | Numeric | Annual rainfall in millimeters |
| Temperature_Celsius | Numeric | Average temperature in Celsius |
| Fertilizer_Used | Boolean | Whether fertilizer was applied |
| Irrigation_Used | Boolean | Whether irrigation was used |
| Days_to_Harvest | Numeric | Days from planting to harvest |

**Target:**
- `Yield_tons_per_hectare` → Profit_Category (Low/Medium/High)

---

## 🏆 Model Performance

### Decision Tree
- **Training Accuracy:** 84.85%
- **Testing Accuracy:** 83.18%

### Random Forest
- **Training Accuracy:** 89.96%
- **Testing Accuracy:** 83.68%

Both models show good generalization with minimal overfitting.

---

## 🚀 How to Use

### 1. Clone the Repository
```bash
git clone https://github.com/femyfede/kilimo_AI.git
cd kilimo_AI
```

### 2. Install Dependencies
```bash
pip install pandas numpy scikit-learn seaborn matplotlib jupyter
```

### 3. Run the Notebook
```bash
jupyter notebook model_kilimo.ipynb
```

### 4. Make Predictions
The notebook includes a prediction section for new farm data:

```python
# Example: Predict yield for a new farm
new_farm = pd.DataFrame({
    'Soil_Type': ['Clay'],
    'Rainfall_mm': [620.0],
    'Temperature_Celsius': [28.0],
    'Fertilizer_Used': [True],
    'Irrigation_Used': [1],
    'Days_to_Harvest': [90]
})

# Predictions
dt_pred = model_dt.predict(new_farm)  # Decision Tree
rf_pred = model_rf.predict(new_farm)  # Random Forest
```

---

## 📈 Key Insights

1. **Decision Tree** provides interpretable rules for understanding yield factors
2. **Random Forest** offers more accurate predictions with better generalization
3. Model performance is consistent between train and test sets (no major overfitting)
4. Both models achieve ~83-84% test accuracy - suitable for agricultural planning

---

## 🛠️ Project Structure

```
kilimo_logic/
├── model_kilimo.ipynb          # Main ML pipeline & analysis
├── README.md                    # This file
└── .gitignore                   # Git ignore file
```

---

## 📝 Notebook Sections

1. **Import Libraries** - All required ML and data science packages
2. **Load Dataset** - Read maize data from CSV
3. **Data Exploration** - Statistical summary and distribution analysis
4. **Data Cleaning** - Missing values, duplicates, outliers
5. **Feature Engineering** - Target variable creation (profit categories)
6. **EDA Visualizations** - Boxplots and distributions
7. **Prepare Features** - Extract X (features) and y (target)
8. **Encode Categorical Features** - Convert text to numbers
9. **Train-Test Split** - 80% train, 20% test split
10. **Train Models** - Fit Decision Tree and Random Forest
11. **Model Evaluation** - Confusion matrices and accuracy comparison
12. **Make Predictions** - Predict profitability for new farms

---

## 🔧 Hyperparameters

**Decision Tree:**
- `max_depth=10` - Prevents overfitting while maintaining accuracy
- `random_state=42` - Reproducible results

**Random Forest:**
- `n_estimators=100` - 100 trees for stable ensemble
- `max_depth=15` - Controlled depth per tree
- `random_state=42` - Reproducible results

---

## 💡 Future Improvements

- [ ] Add cross-validation for more robust performance estimates
- [ ] Implement hyperparameter tuning with GridSearchCV
- [ ] Add regression model for actual yield prediction (tons/hectare)
- [ ] Create web interface for farmer-friendly predictions
- [ ] Collect more diverse dataset samples
- [ ] Add seasonal/climate region specific models
- [ ] Deploy as REST API or mobile app

---

## 📚 Requirements

```
pandas>=1.3.0
numpy>=1.21.0
scikit-learn>=0.24.0
seaborn>=0.11.0
matplotlib>=3.4.0
jupyter>=1.0.0
```

---

## 📞 Author

**Fedelika Maxmus**  
Kilimo AI Project  
GitHub: [@femyfede](https://github.com/femyfede)

---

## 📄 License

This project is open source and available for educational and agricultural use.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to:
- Report bugs
- Suggest improvements
- Submit pull requests
- Share datasets

---

## 📧 Feedback

For questions, suggestions, or feedback about this project, feel free to open an issue on GitHub.

---

**Last Updated:** March 26, 2026
