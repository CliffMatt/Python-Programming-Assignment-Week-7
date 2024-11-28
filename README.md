# Python-Programming-Assignment-Week-7
Assignment
# Importing required libraries
import pandas as pd
import matplotlib.pyplot as plt

# Step 1: Load the Dataset
# Replace 'your_dataset.csv' with your dataset's filename
try:
    dataset = pd.read_csv('your_dataset.csv')
    print("Dataset successfully loaded.")
except FileNotFoundError:
    print("Error: Dataset file not found.")
    exit()

# Step 2: Explore the Data
# Display the first few rows of the dataset
print("First 5 rows of the dataset:")
print(dataset.head())

# Display basic information about the dataset
print("\nDataset Information:")
print(dataset.info())

# Check for missing values
print("\nMissing Values:")
print(dataset.isnull().sum())

# Display basic statistics
print("\nBasic Statistics:")
print(dataset.describe())

# Step 3: Basic Data Analysis
# Example: Analyzing the distribution of a specific column
if 'column_name' in dataset.columns:
    print("\nDistribution of 'column_name':")
    print(dataset['column_name'].value_counts())
else:
    print("\nColumn 'column_name' not found in the dataset. Update column names as needed.")

# Step 4: Data Visualization
# Example 1: Plotting a histogram of a numeric column
plt.figure(figsize=(8, 5))
plt.hist(dataset['numeric_column'], bins=10, color='skyblue', edgecolor='black')
plt.title('Distribution of Numeric Column')
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.show()

# Example 2: Plotting a bar chart for a categorical column
plt.figure(figsize=(8, 5))
dataset['categorical_column'].value_counts().plot(kind='bar', color='orange')
plt.title('Counts of Categories')
plt.xlabel('Category')
plt.ylabel('Count')
plt.show()

# Example 3: Scatter plot for two numerical columns
plt.figure(figsize=(8, 5))
plt.scatter(dataset['numeric_column_x'], dataset['numeric_column_y'], color='green')
plt.title('Scatter Plot of Numeric Columns')
plt.xlabel('Numeric Column X')
plt.ylabel('Numeric Column Y')
plt.show()

# Step 5: Findings and Observations
print("\nFindings and Observations:")
print("- The dataset contains X rows and Y columns.")
print("- Columns 'A', 'B', and 'C' are most frequently observed in 'categorical_column'.")
print("- The numeric column 'numeric_column' shows a normal-like distribution.")

# Save findings to a file
findings = """
Findings and Observations:
- The dataset contains X rows and Y columns.
- Columns 'A', 'B', and 'C' are most frequently observed in 'categorical_column'.
- The numeric column 'numeric_column' shows a normal-like distribution.
"""
with open("findings.txt", "w") as file:
    file.write(findings)
print("\nFindings saved to findings.txt")
