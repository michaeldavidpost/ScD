# ScD
ScD applications

# CTSES Scale Converter

## Description
This project transforms the College Teaching Self-Efficacy Scale (CTSES) data from its original 6-point Likert scale to a more granular 12-point scale. The tool helps researchers and educators analyze teaching confidence and frequency ratings with greater precision.

## Background
The College Teaching Self-Efficacy Scale (Prieto, 2006) measures two dimensions:
1. **Confidence** - How confident instructors are in their ability to perform teaching tasks
2. **Frequency** - How often instructors actually perform these teaching tasks

The original scale uses a 6-point Likert format. This conversion tool transforms the data into a 12-point scale using the formula `(original_rating * 2) - 1`, providing finer granularity for analysis.

## Features
- Loads CSV data containing 6-point scale CTSES responses
- Converts string representations of ratings to Python lists
- Transforms 6-point scale (1-6) to 12-point scale (1-11)
- Handles multiple ratings per item by averaging after conversion
- Creates separate items for confidence and frequency ratings
- Generates visualizations of rating distributions
- Analyzes gaps between confidence and frequency
- Groups items by category for thematic analysis

## Sample Visualizations
- Distribution histograms showing the spread of confidence and frequency ratings
- Scatter plot comparing confidence vs. frequency ratings
- Heatmap of ratings by teaching category

## Requirements
- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn (for heatmaps)

## Usage
1. Prepare your CTSES data in CSV format with the following columns:
   - Item: Question number (1-44)
   - Activity: Text of the teaching activity
   - Confidence_Ratings: List of ratings for confidence (e.g., "[4]" or "[3, 4]")
   - Frequency_Ratings: List of ratings for frequency (e.g., "[5]" or "[4, 5]")

2. Run the conversion script:
```python
import pandas as pd
import numpy as np
import ast
import matplotlib.pyplot as plt

# Load the CSV data
df = pd.read_csv('ctses-data.csv')

# Convert string representations of lists to actual Python lists
df['Confidence_Ratings'] = df['Confidence_Ratings'].apply(ast.literal_eval)
df['Frequency_Ratings'] = df['Frequency_Ratings'].apply(ast.literal_eval)

# Convert to 12-point scale
# See full code in the notebook for complete implementation
```

3. Analyze the results in the generated CSV files and visualization images

## Files Included
- `ctses_converter.ipynb`: Jupyter notebook with full conversion code
- `ctses-data.csv`: Sample input data in 6-point scale format
- `ctses_12point_likert.csv`: Converted data in 12-point scale format
- `ctses_confidence_frequency_comparison.csv`: Analysis of confidence vs. frequency
- Visualization files in PNG format

## Citation
When using this tool, please cite the original CTSES scale:
Prieto, L. (2006). College Teaching Self-Efficacy Scale.

## License
[Your chosen license]

## Contact
[Your contact information]
