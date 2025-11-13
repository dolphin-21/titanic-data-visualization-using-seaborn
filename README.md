# 🚢 Titanic Data Visualization using Seaborn & Matplotlib

This project explores the **Titanic dataset** using **Python**, **Seaborn**, and **Matplotlib**.  
It visualizes key relationships between passenger attributes like **age**, **fare**, **class**, **gender**, and **survival**.

---

## 📊 Project Overview

The Titanic dataset is one of the most popular datasets in data science, used to learn data analysis and visualization.  
In this project, we generate various plots to understand patterns in the data:

- Scatter plots (Age vs Fare)
- Line plot
- Box plot (Fare by Class)
- Histogram (Distribution of Age)
- Count plot (Survival count)
- Multi-feature visualization (by Sex & Class)

---

## 🧠 Skills & Libraries Used

- **Python**
- **Seaborn**
- **Matplotlib**
- **Pandas**

---

## 🧩 Code Overview

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Load dataset
titanic = sns.load_dataset('titanic')

# Display info
print(titanic.head())
print(titanic.info())
print(titanic.describe())

# Scatter plot
sns.relplot(x='age', y='fare', data=titanic)
plt.title('Age vs Fare (Scatter)')
plt.show()

# Line plot
sns.lineplot(x='age', y='fare', data=titanic)
plt.title("Lineplot: Age vs Fare")
plt.show()

# Scatterplot
sns.scatterplot(x='age', y='fare', data=titanic)
plt.title("Scatterplot: Age vs Fare")
plt.show()

# Scatter with hue (sex)
sns.relplot(x='age', y='fare', hue='sex', data=titanic)
plt.title('Age vs Fare (by Sex)')
plt.show()

# Scatter with style (class)
sns.relplot(x='age', y='fare', style='class', color='green', data=titanic)
plt.title('Age vs Fare by Class')
plt.show()

# Combined style and hue
sns.relplot(x='age', y='fare', hue='sex', style='class', data=titanic)
plt.title('Age vs Fare by Sex & Class')
plt.show()

# Histogram
plt.hist(titanic['age'].dropna(), bins=30, color='skyblue', edgecolor='black')
plt.title('Distribution of Passenger Age')
plt.xlabel('Age')
plt.ylabel('Count')
plt.show()

# Boxplot
sns.boxplot(x='class', y='fare', data=titanic)
plt.title('Boxplot of Fare by Class')
plt.show()

# Countplot
sns.countplot(x='survived', data=titanic)
plt.title('Count of Survival')
plt.show()
