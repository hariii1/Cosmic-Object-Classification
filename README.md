# Unveiling the Cosmos: Classifying Stars, Galaxies and Quasars

This project is a machine learning endeavor to automatically classify celestial objects (Stars, Galaxies, and Quasars) based on their observed properties. It leverages data from the Sloan Digital Sky Survey (SDSS) to train and evaluate various classification models.

## Project Overview

The core challenge addressed by this project is to build machine learning models that can accurately identify different celestial bodies from astronomical measurements. This automation significantly aids astronomers in understanding and categorizing the vastness of our universe more efficiently.

## Data Source

The dataset used is `star_classification.csv`, which is a rich collection of photometric measurements and metadata taken by powerful telescopes, notably the Sloan Digital Sky Survey.

Each row in the dataset represents a celestial object and includes features such as:
* **Brightness measurements:** In different light spectrums (u, g, r, i, z bands).
* **Celestial coordinates:** (alpha, delta) for object location.
* **Class:** The true classification of the object (GALAXY, STAR, or QSO/Quasar).

## Project Steps and Methodology

1.  **Data Loading and Initial Inspection:**
    * The `star_classification.csv` dataset is loaded using Pandas.
    * Initial steps include `df.head()`, `df.info()`, `df.isnull().sum()`, and `df.describe()` to understand the data structure, check for missing values, and gain statistical insights.
    * Value counts and a bar chart visualize the distribution of celestial object classes.

2.  **Data Preprocessing:**
    * Missing values (e.g., -9999.0) in 'u', 'g', 'z' bands are replaced with the median of their respective columns.
    * `LabelEncoder` is used to convert the categorical 'class' labels into numerical format for model training.
    * Irrelevant columns such as `obj_ID`, `rerun_ID`, `run_ID`, `cam_col`, `field_ID`, `spec_obj_ID`, `plate`, `MJD`, `fiber_ID` are dropped.
    * Features are scaled using `StandardScaler` to ensure optimal model performance.
    * The dataset is split into 80% training and 20% testing sets, maintaining class distribution using `stratify=y`.

3.  **Model Training and Evaluation:**

    * **Baseline Model (Logistic Regression):**
        * A `LogisticRegression` model is trained as a baseline to establish initial performance metrics.
        * Evaluated using `accuracy_score`, `classification_report`, and a `confusion_matrix` heatmap to visualize prediction performance.

    * **Automated Model Adaptation (Analogy to LLM Fine-tuning):**
        * The project explores the adaptation of three additional machine learning models:
            * `RandomForestClassifier`
            * `GradientBoostingClassifier`
            * `SVC` (Support Vector Classifier)
        * For each model, both un-adapted (default parameters) and adapted versions are evaluated.
        * **Hyperparameter Tuning:** `GridSearchCV` and `RandomizedSearchCV` are utilized for automated hyperparameter tuning to find the best settings that optimize model accuracy.
        * Each adapted model's performance is reported with its accuracy score, a detailed classification report (precision, recall, f1-score), and a confusion matrix.

## Evaluation Criteria

The models are evaluated based on standard classification metrics:
* **Accuracy Score:** Overall correctness of predictions.
* **Classification Report:** Provides precision, recall, and F1-score for each class, offering a deeper insight into model performance for imbalanced datasets.
* **Confusion Matrix:** A visual table showing the number of correct and incorrect predictions for each class, highlighting where the model might be confusing different celestial objects.

## How to Run the Code

This code was originally part of a Jupyter Notebook in Google Colab, and can be run in a similar environment.

1.  **Download the Code:**
    * Clone this repository:
        ```bash
        git clone [https://github.com/your-username/Cosmic-Object-Classification-ML.git](https://github.com/your-username/Cosmic-Object-Classification-ML.git)
        cd Cosmic-Object-Classification-ML
        ```
    * Or directly download the `machine_learning_final_project_(1).py` file.

2.  **Obtain the Dataset:**
    * Download the `star_classification.csv` dataset.
    * Place the dataset in a directory accessible by your Python script. If running in Google Colab, upload it to `/content/drive/MyDrive/dataset/` or adjust the `pd.read_csv()` path in the script to match your data's location.

3.  **Install Dependencies:**
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```

4.  **Execute the Script:**
    * If using Google Colab, upload the `.py` file and run the cells.
    * If running locally, execute from your terminal:
        ```bash
        python machine_learning_final_project_(1).py
        ```
    * Note: The plotting functions (`plt.show()`) will display the plots, and the print statements will output the evaluation reports to your console.

## Technologies Used

* Python
* Pandas: Data manipulation and analysis.
* NumPy: Numerical operations.
* Matplotlib: Data visualization.
* Seaborn: Enhanced data visualization.
* Scikit-learn: Machine learning models (Logistic Regression, RandomForestClassifier, GradientBoostingClassifier, SVC) and utilities (LabelEncoder, StandardScaler, train_test_split, GridSearchCV, RandomizedSearchCV, accuracy_score, classification_report, confusion_matrix).
* Google Colab (original environment, can be run locally)
