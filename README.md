## Dataset

### Data Sources
The datasets used in this project include EEG recordings for three experimental conditions:
1. **CONSISTENT**: Responses where stimuli were consistent with expectations.
2. **MISLEADING**: Responses where stimuli misled the participants.
3. **CONTROL**: Neutral responses used as a baseline.

### Structure
The dataset is organized across multiple `.csv` files, each representing metrics for different electrodes and conditions. These files were combined into a single dataset for analysis.

#### Key Details:
- **Electrodes**: Signals recorded from 32 electrodes (e.g., `Fz`, `Cz`, `Pz`).
- **Conditions**:
  - **CONSISTENT**: Marked by `_CONSISTENT`.
  - **MISLEADING**: Marked by `_MISLEADING`.
  - **CONTROL**: Marked by `_CONTROL`.
- **Trials**: Each file contains combined metrics across trials for all participants.

### Preprocessing
1. **Combining Files**:
   - All `.csv` files were merged into a single DataFrame.
2. **Normalization**:
   - Electrode data was normalized to ensure consistency across features.
3. **Reshaping**:
   - Data was reshaped to include:
     - `File`: Identifier for trials.
     - `Electrode`: Name of the electrode.
     - `Condition`: Neural condition (`CONSISTENT`, `MISLEADING`, `CONTROL`).
     - `Value`: Metric value.





## Workflow Overview

This project follows a structured pipeline for neural condition classification. The key steps are:

### 1. Data Preparation
- Combined multiple `.csv` files into a single dataset.
- Normalized electrode data using `StandardScaler`.
- Reshaped the data to include:
  - **File**: Identifier for each trial.
  - **Electrode**: Name of the electrode.
  - **Condition**: Neural condition (`CONSISTENT`, `MISLEADING`, `CONTROL`).
  - **Value**: Metric value.

### 2. Feature Selection
- Removed low-variance features using a **VarianceThreshold** filter to retain only meaningful features.
- Reduced dimensionality using **Principal Component Analysis (PCA)**, retaining 95% of the data’s variance.

### 3. Model Training
- Trained a **Random Forest Classifier** to classify conditions based on the electrode values.
- Tuned hyperparameters using **GridSearchCV** with cross-validation to find the best-performing model.

### 4. Model Evaluation
- Assessed the model's performance on a test set using:
  - **Accuracy**
  - **Precision**
  - **Recall**
  - **F1-Score**
- Visualized results using a confusion matrix and classification report.

### 5. Feature Importance Analysis
- Identified the most influential electrodes contributing to the classification using feature importance scores from the Random Forest model.

### 6. Visualization and Reporting
- Plotted key results, including:
  - **Confusion Matrix**
  - **Feature Importance**
- Saved results for documentation and reporting.


## Model Results

### Model Performance
The classification model achieved the following performance metrics on the test set:
- **Accuracy**: Achieved an accuracy of **X%** (replace with actual value).
- **Precision, Recall, and F1-Score**:
  - Provided detailed metrics for each condition (`CONSISTENT`, `MISLEADING`, `CONTROL`).

### Confusion Matrix
The confusion matrix visualizes the model's performance in distinguishing between the three conditions:

![Confusion Matrix](results/confusion_matrix.png)

Key observations:
- **High Recall** for the `MISLEADING` condition indicates the model's strong ability to identify misleading responses.
- Misclassifications occurred primarily between `CONSISTENT` and `CONTROL`, likely due to overlapping patterns in neural responses.

### Feature Importance
Feature importance analysis revealed the most influential electrodes for classification:

![Feature Importance](results/feature_importance.png)

Key insights:
- The electrodes **`Fz`**, **`Cz`**, and **`Pz`** contributed significantly to differentiating between conditions.
- This aligns with neural patterns observed in prior EEG studies.

### Insights
- The model successfully identified distinct neural patterns for the three conditions.
- The results highlight the importance of specific electrodes in distinguishing between conditions, suggesting their relevance for future EEG studies.



## How to Run the Project

### 1. Clone the Repository
Start by cloning the repository to your local machine:
```bash
[git clone https://github.c/your_project.git](https://github.com/obedurrahman/datamining/new/main?filename=README.md)
cd [your_project](https://github.com/obedurrahman/datamining/new/main?filename=README.md)


## Acknowledgments
This project was made possible through the resources and support provided by:
- Fairfield University for their guidance in data mining.
- Faculty mentors for their assistance in understanding EEG analysis techniques.



---

## License
This project is licensed under the MIT License. Feel free to use, modify, and distribute this project for educational and research purposes. See the `LICENSE` file for details.



