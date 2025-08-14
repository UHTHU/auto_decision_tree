# Auto Decision Tree Workbench (with Unicode helpers)

This project provides a Jupyter notebook (`auto_decision_tree_workbench.ipynb`) for training and using decision tree models on any CSV dataset that follows a simple column naming convention. It is especially useful for multilingual data, thanks to its Unicode-aware helpers.

## Features

- **Automatic column detection**: Finds predictors, features, and targets based on column name patterns.
- **Unicode translation option**: Converts non-ASCII strings to Unicode code points for robust handling of multilingual data.
- **Flexible task detection**: Automatically detects regression or classification based on target column types.
- **Preprocessing**: Handles missing values and encodes categorical features automatically.
- **Model training**: Trains a decision tree (classification or regression) using scikit-learn pipelines.
- **Visualization**: Plots the trained decision tree with feature names.
- **Batch and interactive prediction**: Supports batch predictions from a CSV and interactive predictions via the notebook, with Unicode-aware input/output.

## Column Naming Scheme

- `xxx_predictors1`, `xxx_predictors2`, ...  
  (Optional meta columns; not used directly by the model)
- `xxx_feature1_1`, `xxx_feature1_2`, `xxx_feature2_1`, ...  
  (Input features)
- `xxx_targets1`, `xxx_targets2`, ...  
  (One or more targets — can be numeric or categorical)

## Usage

1. **Prepare your CSV**  
   Ensure your data columns follow the naming scheme above.

2. **Configure settings**  
   At the top of the notebook, set:
   - `DATA_PATH` to your CSV file path.
   - `TRANSLATE_NON_ASCII_TO_UNICODE` to `True` if you want to encode non-ASCII strings.

3. **Run the notebook**  
   Execute all cells. The notebook will:
   - Load and preprocess your data.
   - Train a decision tree model.
   - Show evaluation metrics and a tree plot.
   - Save the trained model to disk.

4. **Make predictions**  
   - **Batch**: Set `PREDICT_CSV` to a CSV path and run the prediction cell to generate predictions for new data.
   - **Interactive**: Use the interactive cell to enter predictor values and see predictions, with Unicode decoding for string outputs.

## Requirements

- Python 3.7+
- pandas
- numpy
- scikit-learn
- matplotlib
- joblib

Install requirements with:

```
pip install pandas numpy scikit-learn matplotlib joblib
```

## Notes

- The Unicode helpers ensure that models can handle and predict non-English text robustly, especially for languages like Chinese.
- The notebook is designed to be generic and should work with any dataset that matches the column naming convention.

---

See [`auto_decision_tree_workbench.ipynb`](auto_decision_tree_workbench.ipynb) for details and usage
