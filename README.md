# Unveiling the Cosmos: Classifying Stars, Galaxies, and Quasars

This project embarks on a machine learning journey to automatically identify and classify different celestial objects observed in the night sky. Utilizing astronomical data, the goal is to distinguish between Stars, Galaxies, and Quasars using various machine learning models.

## Problem Statement

The challenge is to build Machine Learning models capable of automatically classifying celestial bodies (Stars, Galaxies, or Quasars) based on their light and other observed properties. This automation assists astronomers in understanding our universe more efficiently.

## Data Source

The dataset used is `star_classification.csv`, a comprehensive collection of measurements and observations captured by powerful telescopes like the Sloan Digital Sky Survey.

Each entry in the dataset provides detailed descriptions of a celestial object, including:
* **Brightness:** Measured in different colors of light (u, g, r, i, z bands).
* **Location:** Celestial coordinates (alpha, delta).
* **Class:** The actual classification of the object as a 'GALAXY', 'STAR', or 'QSO' (Quasar).

The project involves initial data inspection, checking for missing values, and statistical analysis to understand the dataset's characteristics.

## How to Run the Notebook

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/Cosmic-Object-Classification.git](https://github.com/your-username/Cosmic-Object-Classification.git)
    cd Cosmic-Object-Classification
    ```
2.  **Ensure you have Jupyter Notebook or JupyterLab installed.** If not, you can install it via pip:
    ```bash
    pip install notebook  # or pip install jupyterlab
    ```
3.  **Download the `star_classification.csv` dataset** and place it in the `/content/drive/MyDrive/dataset/` directory as referenced in the notebook, or update the `df = pd.read_csv(...)` path in the notebook to your local data location.
4.  **Open Jupyter Notebook/Lab and run the `Machine_Learning_Final_project (1).ipynb` file:**
    ```bash
    jupyter notebook "Machine_Learning_Final_project (1).ipynb"
    ```

## Technologies Used

* Python
* Pandas (for data manipulation and analysis)
* NumPy (for numerical operations)
* Matplotlib (for data visualization)
* Seaborn (for enhanced data visualization)
* Scikit-learn (expected for machine learning models, though not explicitly shown in the snippet)
* Jupyter Notebook / Google Colab
