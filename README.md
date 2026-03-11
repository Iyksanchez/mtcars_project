# Mtcars Horsepower Data Cleaning and Outliers Detection Using Python

Mtcars Horsepower Analysis and Data Cleaning
Overview

This project performs data exploration, visualization, and cleaning on the Mtcars dataset, with a focus on the horsepower (hp) variable. The analysis identifies missing values and detects outliers using statistical methods, followed by cleaning the dataset to improve data quality.

The workflow demonstrates common data preprocessing techniques used in data science projects, including exploratory data analysis (EDA), visualization, and outlier removal.

## Objectives

The main goals of this project are to:

Load and inspect the Mtcars dataset

Check for missing values in the horsepower column

Identify duplicate records

Analyze the distribution and skewness of horsepower values

Detect outliers using the Interquartile Range (IQR) method

Remove detected outliers

Visualize horsepower distribution before and after cleaning

Dataset

The project uses the mtcars dataset, a well-known dataset that contains various attributes of automobiles such as:

* Miles per gallon (mpg)

* Cylinders (cyl)

* Horsepower (hp)

- Weight (wt)

* Transmission type

* And other performance characteristics

## Technologies Used

* Python

* Pandas

* NumPy

* Matplotlib

* Seaborn

* Jupyter Notebook

## Project Workflow
1. Data Loading

The dataset is imported using Pandas:

df = pd.read_csv('mtcars.csv')

2. Data Inspection

Basic dataset inspection is performed to understand the structure of the data.

df.info()
df.head()

Duplicate records are also checked:

df.duplicated().any()

3. Missing Value Detection

Checking for missing values in the horsepower column:

df['hp'].isnull().sum()

4. Distribution Analysis

The skewness of horsepower values is analyzed:

df['hp'].skew()

A boxplot visualization is used to examine the distribution and identify potential outliers.

5. Outlier Detection

Outliers are detected using the Interquartile Range (IQR) method:

Q1 = df['hp'].quantile(0.25)
Q3 = df['hp'].quantile(0.75)
IQR = Q3 - Q1

The lower and upper bounds are calculated as:

Lower_Bound = Q1 - 1.5 * IQR
Upper_Bound = Q3 + 1.5 * IQR

6. Outlier Removal

Rows containing horsepower values outside the calculated bounds are removed:

df = df[(df['hp'] >= Lower_Bound) & (df['hp'] <= Upper_Bound)]

7. Visualization

Boxplots are used to visualize the horsepower distribution before and after cleaning.

Project Structure
project-folder
│
├── Mtcars.ipynb
├── README.md
└── mtcars.csv

## Results

After removing outliers:

The horsepower distribution becomes more consistent

Extreme values that may skew analysis are eliminated

The dataset becomes more suitable for further analysis or modeling


Author
## Orji Ikechuckwu
