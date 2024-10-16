# Ex.No: 08     MOVINTG AVERAGE MODEL AND EXPONENTIAL SMOOTHING
# DEVELOPED BY: AMURTHA VAAHINI KN
# REGISTER NO: 212222240008
### Date: 


### AIM:
To implement Moving Average Model and Exponential smoothing Using Python.
### ALGORITHM:
1. Import necessary libraries
2. Read the electricity time series data from a CSV file,Display the shape and the first 20 rows of
the dataset
3. Set the figure size for plots
4. Suppress warnings
5. Plot the first 50 values of the 'Value' column
6. Perform rolling average transformation with a window size of 5
7. Display the first 10 values of the rolling mean
8. Perform rolling average transformation with a window size of 10
9. Create a new figure for plotting,Plot the original data and fitted value
10. Show the plot
11. Also perform exponential smoothing and plot the graph
### PROGRAM:
# Import necessary libraries
```
import pandas as pd
import matplotlib.pyplot as plt
import warnings
```
# Read the electricity time series data from a CSV file
```
file_path = '/path_to_your_file/cinemaTicket_Ref.csv'
data = pd.read_csv(file_path)
```
# Display the shape and the first 20 rows of the dataset
```
print("Shape of the dataset:", data.shape)
print("First 20 rows of the dataset:")
print(data.head(20))
```
# Set the figure size for plots
```
plt.figure(figsize=(10, 6))
```
# Suppress warnings
```
warnings.filterwarnings("ignore")
```

# Plot the first 50 values of the 'total_sales' column
```
plt.plot(data['total_sales'][:50], label='Original Data')
plt.title('Original Data (First 50 Values)')
plt.xlabel('Index')
plt.ylabel('Total Sales')
plt.legend()
plt.show()
```
# Perform rolling average transformation with a window size of 5
```
rolling_mean_5 = data['total_sales'].rolling(window=5).mean()
```
# Display the first 10 values of the rolling mean (window size 5)
```
print("First 10 values of Rolling Mean (Window Size 5):")
print(rolling_mean_5.head(10))
```

# Perform rolling average transformation with a window size of 10
```
rolling_mean_10 = data['total_sales'].rolling(window=10).mean()
```

# Create a new figure for plotting
```
plt.figure(figsize=(10, 6))
```

# Plot the original data and fitted value (rolling mean with window 10)
```
plt.plot(data['total_sales'], label='Original Data')
plt.plot(rolling_mean_10, label='Rolling Mean (Window Size 10)', color='red')
plt.title('Original Data vs Rolling Mean (Window Size 10)')
plt.xlabel('Index')
plt.ylabel('Total Sales')
plt.legend()
plt.show()
```
# Perform Exponential Smoothing
```
exp_smooth = data['total_sales'].ewm(span=10, adjust=False).mean()
```
# Create a new figure for plotting
```
plt.figure(figsize=(10, 6))
```
# Plot the original data and exponential smoothing
```
plt.plot(data['total_sales'], label='Original Data')
plt.plot(exp_smooth, label='Exponential Smoothing', color='green')
plt.title('Original Data vs Exponential Smoothing')
plt.xlabel('Index')
plt.ylabel('Total Sales')
plt.legend()
plt.show()
```
### OUTPUT:
# FIRST 50:
![image](https://github.com/user-attachments/assets/05975f03-cc31-4095-baa5-c2f6f9092e5d)

# ROLLING MEAN:
![image](https://github.com/user-attachments/assets/28dae86d-eed5-44b2-aa86-4cfbb9ccf64b)

# Exponential Smoothing
![image](https://github.com/user-attachments/assets/56a37db5-c9f7-4d50-bb98-e6c874afd097)


### RESULT:
Thus we have successfully implemented the Moving Average Model and Exponential smoothing using python.
