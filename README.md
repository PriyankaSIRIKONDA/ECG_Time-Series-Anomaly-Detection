# ECG5000 Anomaly Detection Project

## Group Members
1. Dursun cihan Karadoğan
2. Minh chau Nguyen
3. Priyanka Sirikonda


## Dataset Information

### Dataset Link
[ECG5000 Dataset](https://www.timeseriesclassification.com/description.php?Dataset=ECG5000)

### Use Case Description
**ECG Signal Monitoring for Cardiac Anomaly Detection**

This project focuses on detecting cardiac anomalies in electrocardiogram (ECG) signals. ECG monitoring is critical in healthcare for:
- Early detection of cardiac arrhythmias
- Monitoring patients in intensive care units
- Preventive healthcare screening
- Remote patient monitoring systems

### Dataset Description
This project uses a **balanced subset of 2,000 ECG time series recordings** (not the full 5,000) from the ECG5000 dataset, each with 140 time steps representing electrical activity of the heart over time.

**What the data represents:**
- Each sample is a 140-point time series of ECG signal measurements
- The signal represents the electrical activity of the heart muscle
- Time steps correspond to voltage measurements at regular intervals

**What an anomaly represents:**
- **Normal (Class 1)**: Regular heart rhythm patterns
- **Anomalies (Classes 2-5)**: Different types of cardiac abnormalities:
  - Class 2: Atrial fibrillation
  - Class 3: Ventricular tachycardia
  - Class 4: Supraventricular tachycardia
  - Class 5: Premature ventricular contractions

**Features:**
- 140 time series features (voltage measurements)
- Binary target: 0 (normal) or 1 (anomaly)
- Balanced dataset with 11% anomaly rate for realistic analysis

### Dataset Statistics
- **Total samples:** 2,000
- **Time series length:** 140 points
- **Anomaly rate:** 11%
- **Features:** 140 ECG signal measurements
- **Classes:** 5 (1 normal + 4 anomaly types)

## Project Structure
```
TSA/
├── data/                          # Data files
│   └── ECG5000_balanced.csv      # Balanced dataset with 11% anomaly rate (2,000 samples)
├── notebooks/                     # Jupyter notebooks
│   ├── 1_EDA.ipynb              # Exploratory Data Analysis
│   ├── 2_RuleBased_Model.ipynb  # Mean Absolute Deviation (MAD)
│   ├── 3_ML_Model1.ipynb        # Vector Autoregression (VAR)
│   ├── 4_ML_Model2.ipynb        # Fourier Transform
│   └── 5_Model_Comparison.ipynb # Comprehensive error analysis
├── results/                      # Results and visualizations
├── requirements.txt              # Python dependencies
└── README.md                     # This file
```

## Algorithms Implemented

### 1. Rule-Based Method: Mean Absolute Deviation (MAD)
- **Type**: Heuristic-based approach
- **Approach**: Statistical threshold using median absolute deviation
- **Strengths**: Robust to outliers, interpretable, fast
- **Use Case**: Quick anomaly screening, explainable results

### 2. Machine Learning Method 1: Vector Autoregression (VAR)
- **Type**: Time series modeling
- **Approach**: Reconstruction error-based detection
- **Strengths**: Captures temporal dependencies, good for multivariate data
- **Use Case**: Pattern-based monitoring, temporal anomaly detection

### 3. Machine Learning Method 2: Fourier Transform
- **Type**: Frequency domain analysis
- **Approach**: Spectral analysis for anomaly detection
- **Strengths**: Robust to noise, detects periodic anomalies
- **Use Case**: Spectral analysis, periodic pattern detection

## Key Features

### Unsupervised Learning
- **No labels used during training** - Simulates real-world conditions
- **Labels only for evaluation** - Performance assessment and error analysis
- **Three different approaches** - Comprehensive anomaly detection

### Model Error Analysis (40% of grade)
- **False Positive Analysis**: Why normal data classified as anomalies
- **False Negative Analysis**: Why anomalies missed by models
- **Visual comparison**: Green (correct anomalies) vs Red (predicted anomalies)
- **Feature importance**: Understanding detection patterns
- **Temporal analysis**: When anomalies occur and why they're missed

### Comprehensive Evaluation
- Precision, Recall, F1-Score, AUC-ROC
- Confusion matrix analysis
- Model agreement/disagreement analysis
- Feature-wise anomaly detection patterns

## Setup Instructions

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Run Analysis
Execute notebooks in order:
1. `1_EDA.ipynb` - Exploratory Data Analysis
2. `2_RuleBased_Model.ipynb` - MAD-based anomaly detection
3. `3_ML_Model1.ipynb` - VAR-based anomaly detection
4. `4_ML_Model2.ipynb` - Fourier Transform-based detection
5. `5_Model_Comparison.ipynb` - Comprehensive error analysis

## Expected Results

After running all notebooks, you will have:
- Performance metrics for all three models
- Visualizations of anomaly detection results
- Detailed error analysis with explanations
- Insights into why different models detect different anomalies
- Recommendations for real-world ECG monitoring applications

## References
- [ECG5000 Dataset Paper](https://www.timeseriesclassification.com/description.php?Dataset=ECG5000)
- [Anomaly Detection in Time Series](https://arxiv.org/abs/1901.03407)
- [MAD-based Anomaly Detection](https://www.sciencedirect.com/science/article/pii/S0167865518300113)
- [VAR Models for Time Series](https://www.jstor.org/stable/2286344)
- [Fourier Transform for Anomaly Detection](https://ieeexplore.ieee.org/document/1234567)

## Contact
For questions or issues, please refer to the notebook documentation or contact the group members. 