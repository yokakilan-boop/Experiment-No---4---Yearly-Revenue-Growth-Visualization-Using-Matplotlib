# DSWP-Experiment-4-Yearly-Revenue-Growth-Visualization-Using-Matplotlib

## Aim

To visualize the yearly trend of company revenue and expenses from 2017 to 2023 using Matplotlib by plotting multi-line charts with customized markers, labels, legends, gridlines, and point annotations.

## Algorithm

1. **Start** the program.
2. **Import Libraries**: Import `matplotlib.pyplot` as `plt` for plotting and `numpy` as `np` for numeric array generation and index lookup.
3. **Initialize Dataset**:
   * Generate an array `years` spanning `2017` to `2023` using `np.arange(2017, 2024)`.
   * Define lists `revenue` and `expenses` representing annual amounts in Lakhs.
4. **Configure Figure & Plot Lines**:
   * Initialize a figure canvas of size $8 \times 5$ inches using `plt.figure(figsize=(8, 5))`.
   * Plot `revenue` against `years` as a solid green line with circular markers (`marker='o'`).
   * Plot `expenses` against `years` as a dashed red line (`linestyle='--'`) with square markers (`marker='s'`).
5. **Format Chart Aesthetics**:
   * Add a bold chart title (`plt.title()`) and axis labels (`plt.xlabel()`, `plt.ylabel()`).
   * Enable dashed semi-transparent gridlines (`plt.grid()`) and place the legend in the upper-left corner (`plt.legend(loc='upper left')`).
6. **Annotate Peak Values**:
   * Find the indices of maximum revenue and maximum expenses using `np.argmax()`.
   * Highlight both peak data points on the chart with directional arrows and text callouts using `plt.annotate()`.
7. **Adjust Layout & Display**:
   * Prevent label clipping via `plt.tight_layout()` and render the final plot with `plt.show()`.
8. **Stop** the program.

## Functions and Methods Used

| Category | Function / Method | Purpose / Description |
| :--- | :--- | :--- |
| **Numerical Operations** | `np.arange()` | Generates evenly spaced integer years (`2017` through `2023`) |
| | `np.argmax()` | Returns the array index of the maximum revenue and expense values |
| **Line Plotting** | `plt.figure()` | Initializes a new figure window with custom dimensions |
| | `plt.plot()` | Draws line plots with customized markers, colors, line styles, and widths |
| **Chart Formatting** | `plt.title()`, `plt.xlabel()`, `plt.ylabel()` | Adds descriptive title and axis labels with custom font sizes |
| | `plt.grid()`, `plt.legend()` | Adds background gridlines and displays series labels in the upper left |
| **Annotations & Display** | `plt.annotate()` | Places text labels with arrows pointing to peak revenue and expense points |
| | `plt.tight_layout()`, `plt.show()` | Optimizes spacing to avoid overlapping elements and renders the figure |

## Program / Code
## Input 
```
# Company Revenue and Expense Visualization using Matplotlib

import matplotlib.pyplot as plt
import numpy as np

# Step 1: Create dataset
years = np.arange(2017, 2024)

revenue = [20, 25, 28, 35, 40, 45, 52]  # in lakhs

expenses = [15, 18, 22, 27, 30, 33, 38]  # in lakhs

# Step 2: Plot Revenue and Expenses
plt.figure(figsize=(8, 5))

plt.plot(years, revenue, marker='o', color='green',
         linewidth=2, label='Revenue')

plt.plot(years, expenses, marker='s', color='red',
         linestyle='--', linewidth=2, label='Expenses')

# Step 3: Add titles, labels, and grid
plt.title("Company Revenue and Expense Trends (2017 - 2023)",
          fontsize=13, fontweight="bold")

plt.xlabel("Year", fontsize=11)
plt.ylabel("Amount (in Lakhs)", fontsize=11)

plt.grid(True, linestyle='--', alpha=0.6)

# Step 4: Add legend
plt.legend(loc='upper left')

# Step 5: Annotate highest revenue and expense
max_rev_index = np.argmax(revenue)
max_exp_index = np.argmax(expenses)

plt.annotate(
    f"Highest Revenue: {revenue[max_rev_index]}L",
    xy=(years[max_rev_index], revenue[max_rev_index]),
    xytext=(years[max_rev_index]-0.5,
            revenue[max_rev_index]+2),
    arrowprops=dict(facecolor='black', arrowstyle='->')
)

plt.annotate(
    f"Highest Expense: {expenses[max_exp_index]}L",
    xy=(years[max_exp_index], expenses[max_exp_index]),
    xytext=(years[max_exp_index]-0.5,
            expenses[max_exp_index]+2),
    arrowprops=dict(facecolor='black', arrowstyle='->')
)

# Step 6: Show plot
plt.tight_layout()

plt.show()
```

## Output

<img width="786" height="490" alt="image" src="https://github.com/user-attachments/assets/77e36eef-b3fd-4832-907d-d477082413b4" />


## Result

The program successfully creates datasets for yearly company revenue and expenses and renders an annotated multi-line comparison chart using Matplotlib.
