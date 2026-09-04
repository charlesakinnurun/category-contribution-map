# 📊 Technology Contribution Visualization

A simple Python data visualization project that uses **Polars** for data manipulation and **Matplotlib** to create a donut chart showing the contribution of different technology categories.

## 🚀 Overview

This project demonstrates how to:

* Create a dataset using **Polars**
* Perform column calculations
* Calculate percentage contributions
* Visualize categorical data with a **donut chart**
* Add percentage labels and a descriptive title using **Matplotlib**

The visualization represents technology categories such as:

* 🤖 AI
* 🌐 Web
* 📊 Data
* ☁️ Cloud

## 🛠️ Technologies Used

* **Python**
* **Polars** — DataFrame manipulation and data processing
* **Matplotlib** — Data visualization

## 📦 Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/technology-contribution.git
cd technology-contribution
```

Install the required dependencies:

```bash
pip install polars matplotlib
```

## 💻 Example

The project creates a Polars DataFrame containing technology categories and calculates their percentage contribution before visualizing the results.

```python
import polars as pl
import matplotlib.pyplot as plt

# Create dataset
df = pl.DataFrame({
    "Category": ["AI", "Web", "Data", "Cloud"],
    "Value": [40, 25, 20, 15]
})

# Calculate percentage share
df = df.with_columns(
    (pl.col("Value") / pl.col("Value").sum() * 100).alias("share")
)

# Create donut chart
plt.pie(
    df["share"],
    labels=df["Category"],
    autopct="%.0f%%",
    wedgeprops={"width": 0.4}
)

plt.title("Technology Contribution")
plt.show()
```

## 📈 Visualization

The resulting chart is a **donut chart** where each segment represents the percentage contribution of a technology category.

For example:

| Category | Contribution |
| -------- | -----------: |
| AI       |          40% |
| Web      |          25% |
| Data     |          20% |
| Cloud    |          15% |

## 🧠 Concepts Demonstrated

### Polars DataFrames

Polars provides a fast and expressive DataFrame API for creating and transforming structured data.

### Percentage Calculation

Each category's contribution is calculated using:

```text
Share = Value / Total Value × 100
```

### Donut Chart

Matplotlib's `wedgeprops` parameter is used to create a hole in the center of the pie chart, transforming it into a donut chart.

## 🎯 Learning Objectives

This project is useful for practicing:

* DataFrame operations
* Column expressions in Polars
* Aggregation
* Percentage calculations
* Categorical visualization
* Matplotlib customization

## 🔮 Possible Improvements

Future versions could include:

* Interactive Plotly visualizations
* Custom colors and themes
* Data loaded from CSV or Excel
* Dynamic user input
* Exporting charts as PNG/SVG
* Additional technology categories
* A dashboard using Streamlit

## 📄 License

This project is open source and available under the **MIT License**.
