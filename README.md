# Ex.No: 02 LINEAR AND POLYNOMIAL TREND ESTIMATION
Date:25/08/2025
### AIM:
To Implement Linear and Polynomial Trend Estiamtion Using Python.

### ALGORITHM:
Import necessary libraries (NumPy, Matplotlib)

Load the dataset

Calculate the linear trend values using least square method

Calculate the polynomial trend values using least square method

End the program
### PROGRAM:
A - LINEAR TREND ESTIMATION
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

file_path = "Coffe_sales.xlsx"
df = pd.read_excel(file_path, sheet_name="index_1")

df_grouped = df.groupby("date")["money"].sum().reset_index()

x = np.arange(len(df_grouped))
y = df_grouped["money"].values

linear_coeffs = np.polyfit(x, y, 1)
linear_trend = np.polyval(linear_coeffs, x)

plt.figure(figsize=(10,6))
plt.plot(df_grouped["date"], y, label="Actual Sales", marker="o")
plt.plot(df_grouped["date"], linear_trend, label="Linear Trend", color="red")
plt.xticks(rotation=45)
plt.xlabel("Date")
plt.ylabel("Total Money")
plt.title("Coffee Sales with Linear Trend")
plt.legend()
plt.tight_layout()
plt.show()

```
B- POLYNOMIAL TREND ESTIMATION
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

file_path = "Coffe_sales.xlsx"
df = pd.read_excel(file_path, sheet_name="index_1")

df_grouped = df.groupby("date")["money"].sum().reset_index()

x = np.arange(len(df_grouped))
y = df_grouped["money"].values

poly_coeffs = np.polyfit(x, y, 4)
poly_trend = np.polyval(poly_coeffs, x)

plt.figure(figsize=(10,6))
plt.plot(df_grouped["date"], y, label="Actual Sales", marker="o")
plt.plot(df_grouped["date"], poly_trend, label="Polynomial Trend (deg=4)", color="purple")
plt.xticks(rotation=45)
plt.xlabel("Date")
plt.ylabel("Total Money")
plt.title("Coffee Sales with Ellipse-like Polynomial Trend")
plt.legend()
plt.tight_layout()
plt.show()

```
### OUTPUT
A - LINEAR TREND ESTIMATION
<img width="989" height="590" alt="linear trend" src="https://github.com/user-attachments/assets/7722821a-a85e-4a53-85dd-b876bdb5a41a" />


B- POLYNOMIAL TREND ESTIMATION
<img width="989" height="590" alt="polynomial trend" src="https://github.com/user-attachments/assets/5f576e0d-bca8-4504-881f-c3823d9f0d2d" />

### RESULT:
Thus the python program for linear and Polynomial Trend Estiamtion has been executed successfully.
