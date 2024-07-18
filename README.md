# Data Science Experiment 1

This repository contains the code and dataset for Experiment 1 of the Data Science Fundamentals with Python course.

## Description

In this experiment, we:
- Loaded datasets from the UCI Machine Learning Repository.
- Merged the datasets.
- Performed basic data operations.

## Files

- `Experiment_1_AIDS_SUJAL_SOKANDE_23(DS).ipynb`: The Jupyter Notebook containing the experiment code.
- `merged_data.csv`: The merged dataset generated from the experiment (if applicable).

## Usage

To run the code, open the `Experiment_1_AIDS_SUJAL_SOKANDE_23(DS).ipynb` file in Google Colab or Jupyter Notebook.

## Steps to Reproduce

1. **Set up Google Colab**:
   - Open [Google Colab](https://colab.research.google.com/).
   - Create a new notebook.

2. **Import Necessary Libraries**:
   - Start by importing the required libraries.

    ```python
    import pandas as pd
    import numpy as np
    ```

3. **Load the Dataset**:
   - Use the URL of the dataset from the UCI ML repository. For this example, let's use the "Iris" dataset.

    ```python
    # Load Iris dataset
    url_iris = 'https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data'
    columns_iris = ['sepal_length', 'sepal_width', 'petal_length', 'petal_width', 'class']
    iris_data = pd.read_csv(url_iris, header=None, names=columns_iris)
    ```

4. **Display the Dataset**:
   - Show the first few rows of the dataset to verify it loaded correctly.

    ```python
    iris_data.head()
    ```

5. **Load Another Dataset (if needed for merging)**:
   - Let's load another example dataset. For this, we can use the "Wine" dataset.

    ```python
    # Load Wine dataset
    url_wine = 'https://archive.ics.uci.edu/ml/machine-learning-databases/wine/wine.data'
    columns_wine = ['class', 'alcohol', 'malic_acid', 'ash', 'alcalinity_of_ash', 'magnesium', 'total_phenols', 'flavanoids', 'nonflavanoid_phenols', 'proanthocyanins', 'color_intensity', 'hue', 'od280/od315_of_diluted_wines', 'proline']
    wine_data = pd.read_csv(url_wine, header=None, names=columns_wine)
    ```

6. **Display the Second Dataset**:
   - Show the first few rows of the second dataset.

    ```python
    wine_data.head()
    ```

7. **Merging Datasets**:
   - If the datasets have a common column or an index to merge on, you can merge them. For demonstration, we'll assume there's a common column 'class' for merging. Adjust accordingly for your actual datasets.

    ```python
    # Convert 'class' column in Wine dataset to object type
    wine_data['class'] = wine_data['class'].astype(str)

    # Convert 'class' column in Iris dataset to object type (for consistency, although it should already be object)
    iris_data['class'] = iris_data['class'].astype(str)

    # Merging Datasets
    merged_data = pd.merge(iris_data, wine_data, on='class', how='inner')
    ```

8. **Display the Merged Dataset**:
   - Show the first few rows of the merged dataset.

    ```python
    merged_data.head()
    ```

9. **Basic Data Operations**:
   - Perform some basic operations like checking for missing values, descriptive statistics, etc.

    ```python
    # Check for missing values
    merged_data.isnull().sum()

    # Descriptive statistics
    merged_data.describe()
    ```

10. **Save and Export the DataFrame**:
    - Save the DataFrame to a CSV file and download it locally.

    ```python
    merged_data.to_csv('merged_data.csv', index=False)
    ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
