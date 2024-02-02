<div align="center">
      <h2> <img src="http://bytesofintelligences.com/wp-content/uploads/2023/03/Exploring-AIs-Secrets-1.png" width="300px"><br/> Fundamental Concepts and Architectures of Neural Network </h2>
     </div>

<body>
<p align="center">
  <a href="mailto:ahammadmejbah@gmail.com"><img src="https://img.shields.io/badge/Email-ahammadmejbah%40gmail.com-blue?style=flat-square&logo=gmail"></a>
  <a href="https://github.com/BytesOfIntelligences"><img src="https://img.shields.io/badge/GitHub-%40BytesOfIntelligences-lightgrey?style=flat-square&logo=github"></a>
  <a href="https://linkedin.com/in/ahammadmejbah"><img src="https://img.shields.io/badge/LinkedIn-Mejbah%20Ahammad-blue?style=flat-square&logo=linkedin"></a>
  <a href="https://bytesofintelligences.com/"><img src="https://img.shields.io/badge/Website-Bytes%20of%20Intelligence-lightgrey?style=flat-square&logo=google-chrome"></a>
  <a href="https://www.youtube.com/@BytesOfIntelligences"><img src="https://img.shields.io/badge/YouTube-BytesofIntelligence-red?style=flat-square&logo=youtube"></a>
  <a href="https://www.researchgate.net/profile/Mejbah-Ahammad-2"><img src="https://img.shields.io/badge/ResearchGate-Mejbah%20Ahammad-blue?style=flat-square&logo=researchgate"></a>
  <br>
  <img src="https://img.shields.io/badge/Phone-%2B8801874603631-green?style=flat-square&logo=whatsapp">
  <a href="https://www.hackerrank.com/profile/ahammadmejbah"><img src="https://img.shields.io/badge/Hackerrank-ahammadmejbah-green?style=flat-square&logo=hackerrank"></a>
</p>


#

# 1. Use Case: Sales Data Analysis for a Retail Store

A retail store has been tracking its sales data and wants to analyze this data to gain insights into its business performance. They have data for different products, including the number of units sold, unit price, and sales date.

#### Objective:
The store wants to understand which products are the best sellers and which days of the week see the highest sales. This information will help in inventory management and in planning marketing strategies.

#### Data Structure:
The data is stored in a tabular format with the following columns:
- `Product`: The name of the product.
- `Units Sold`: The number of units sold for each product.
- `Unit Price`: The price of one unit of the product.
- `Sale Date`: The date on which the sale occurred.

### Python Function: Sales Analysis

Now, based on this use case, I'll create a Python function that:
1. Generates random sales data.
2. Analyzes this data to find the best-selling products and the busiest sales days.

#### Function Steps:
1. **Data Generation**: Generate a random dataset with the specified columns.
2. **Data Analysis**:
   - Calculate total sales for each product.
   - Determine the busiest day of the week in terms of sales.

Let's start by coding the data generation part:

The `sales_data` function successfully created a sample dataset representing sales data. Here's a breakdown of the function:

1. **Function Definition**: `sales_data(num_entries=100)` - This function takes an optional parameter `num_entries` which specifies the number of data entries to generate. The default is set to 100.

2. **Setting up Random Seed**: `np.random.seed(0)` - This ensures that the random numbers generated are the same each time the function is run, making the results reproducible.

3. **Sample Data Creation**:
   - `products`: A list of product names.
   - `dates`: A list of dates, each representing a day in the past up to `num_entries` days.

4. **Generating Random Data**:
   - `Product`: Randomly selected from the `products` list.
   - `Units Sold`: Random integers between 1 and 20.
   - `Unit Price`: Random floating-point numbers between 10 and 100.
   - `Sale Date`: Randomly selected from the `dates` list.

5. **DataFrame Creation**: The generated data is compiled into a pandas DataFrame for easy manipulation and analysis.

6. **Function Output**: The function returns the created DataFrame.

Next, we'll develop the data analysis part of the function. This will include calculations to determine the best-selling products and the busiest sales days. Let's proceed with that:

The `sales_data` function has analyzed the generated sales data. Here's an overview of what this function does:

```python

import pandas as pd
import numpy as np
from datetime import datetime, timedelta

def sales_data(num_entries=100):
    # Random seed for reproducibility
    np.random.seed(0)

    # Sample data
    products = ['Product A', 'Product B', 'Product C', 'Product D', 'Product E']
    dates = [datetime.now() - timedelta(days=i) for i in range(num_entries)]

    # Random data
    data = {
        'Product': np.random.choice(products, num_entries),
        'Units Sold': np.random.randint(1, 20, num_entries),
        'Unit Price': np.random.uniform(10, 100, num_entries),
        'Sale Date': np.random.choice(dates, num_entries)
    }

    # Create DataFrame
    sales_df = pd.DataFrame(data)

    return sales_df

# Sample sales data
sales_data = sales_data()
sales_data.head()  # Display the first few rows of the generated data


```

1. **Total Sales Calculation**:
   - The function first calculates the total sales for each product by multiplying the 'Units Sold' by the 'Unit Price'.
   - It then groups the data by 'Product' and sums up the 'Total Sales' for each product.
   - The resulting series is sorted in descending order to show the products with the highest total sales first.

2. **Busiest Sales Day Determination**:
   - The 'Sale Date' column is converted to a pandas `datetime` object.
   - A new column 'Day of Week' is created, containing the name of the day of the week for each sale date.
   - The function then groups the data by 'Day of Week' and sums up the 'Units Sold' for each day.
   - This series is also sorted in descending order to identify the busiest sales day based on units sold.

The results from the analysis are:
- `product_sales`: A series showing total sales for each product, with 'Product D' being the top seller.
- `sales_day`: A series showing the total units sold for each day of the week, with 'Friday' being the busiest day.



# 2. Use Case: Weather Data Analysis for a City

#### Scenario:
A city's meteorological department wants to analyze weather data to understand local climate patterns. They are interested in temperature, humidity, and precipitation levels over a period of time.

#### Objective:
The goal is to identify trends and patterns in the weather data, such as average temperature variations, days with high humidity, and frequency of precipitation. This information can assist in planning city activities, agriculture, and preparing for extreme weather events.

#### Data Structure:
The data will have the following columns:
- `Date`: The date of the weather recording.
- `Temperature`: The average temperature of the day (in degrees Celsius).
- `Humidity`: The average humidity percentage of the day.
- `Precipitation`: The precipitation amount (in millimeters).

### Python Function: Weather Data Analysis

Based on this use case, I'll create a Python function that:
1. Generates random weather data.
2. Analyzes this data to find average temperature trends, days with high humidity, and precipitation patterns.

#### Function Steps:
1. **Data Generation**: Generate a random dataset with the specified columns.
2. **Data Analysis**:
   - Calculate the average temperature for each month.
   - Identify days with humidity above a certain threshold.
   - Summarize precipitation data to find rainy days.

```python

import pandas as pd
import numpy as np
from datetime import datetime, timedelta

def weather_data(num_days=365):
    # Random seed for reproducibility
    np.random.seed(0)

    # Dates for the past 'num_days' days
    end_date = datetime.now()
    start_date = end_date - timedelta(days=num_days)
    dates = pd.date_range(start=start_date, end=end_date, freq='D')

    # Random weather data
    data = {
        'Date': dates,
        # Temperatures between 15°C and 35°C
        'Temperature': np.random.uniform(15, 35, num_days),  
           # Humidity between 30% and 90%
        'Humidity': np.random.uniform(30, 90, num_days),  
        'Precipitation': np.random.choice([0, 0, 0, 1], 
        num_days) * np.random.uniform(0, 20, num_days)
        # Precipitation: 75% chance of 
        #no rain, and up to 20mm otherwise
    }

    # Create DataFrame
    weather_df = pd.DataFrame(data)

    return weather_df

# Sample weather data
weather_data = weather_data()
weather_data.head()  # Display the first few rows of the generated data


```

The `weather_data` function has successfully created a sample weather dataset. Let's go through the function step by step:

1. **Function Definition**: `weather_data(num_days=365)` - This function takes an optional parameter `num_days` which specifies the number of days of weather data to generate, with a default of 365 days (one year).

2. **Setting up Random Seed**: `np.random.seed(0)` - Ensures that the random numbers generated are consistent each time the function is run.

3. **Date Generation**:
   - Calculates `start_date` and `end_date` to cover the past `num_days`.
   - Generates a range of dates from `start_date` to `end_date` using `pd.date_range`.

4. **Random Weather Data Generation**:
   - `Temperature`: Random floating-point numbers between 15 and 35, representing degrees Celsius.
   - `Humidity`: Random floating-point numbers between 30% and 90%.
   - `Precipitation`: Simulates a 75% chance of no rain (zero precipitation) and up to 20mm of precipitation otherwise.

5. **DataFrame Creation**: Compiles the generated data into a pandas DataFrame.

6. **Function Output**: Returns the DataFrame containing the simulated weather data.

The DataFrame `weather_data` displays the first few rows, showing 'Date', 'Temperature', 'Humidity', and 'Precipitation' columns.

Next, I'll create the data analysis part of the function, focusing on monthly average temperature trends, days with high humidity, and precipitation patterns. Let's proceed with that:

The `weather_data` function has processed the generated weather data. Here's a breakdown of the function:

1. **Date Conversion**:
   - Converts the 'Date' column to a pandas `datetime` object for easier manipulation.

2. **Monthly Average Temperature**:
   - Adds a 'Month' column derived from the 'Date' column.
   - Groups data by 'Month' and calculates the average temperature for each month.

3. **High Humidity Days**:
   - The function filters days where the humidity is above a specified threshold (default is 75%).
   - This subset of the DataFrame lists days with high humidity levels.

4. **Precipitation Analysis**:
   - Considers a day with any non-zero precipitation as a rainy day.
   - Groups data by 'Month' and counts the number of rainy days per month.

```python

def analyze_weather_data(weather_df, humidity_threshold=75):
    # Convert 'Date' to datetime
    weather_df['Date'] = pd.to_datetime(weather_df['Date'])

    # Monthly Average Temperature
    weather_df['Month'] = weather_df['Date'].dt.to_period('M')
    avg_monthly_temp = weather_df.groupby('Month')['Temperature'].mean()

    # Days with High Humidity
    high_humidity_days = weather_df[weather_df['Humidity'] > humidity_threshold]

    # Precipitation Analysis
    # Considering a day with precipitation > 0 as a rainy day
    rainy_days_count = weather_df[weather_df['Precipitation'] > 0].groupby('Month').size()

    return avg_monthly_temp, high_humidity_days, rainy_days_count

# Analyze the generated weather data
avg_monthly_temp, high_humidity_days, rainy_days_count = weather_data(weather_data)
# Display the analysis results
(avg_monthly_temp.head(), high_humidity_days.head(), rainy_days_count)  



```

The results of the analysis are:
- `avg_monthly_temp`: A series showing the average temperature for each month.
- `high_humidity_days`: A DataFrame of days where the humidity was higher than the threshold, showing the date, temperature, humidity, and precipitation for those days.
- `rainy_days_count`: A series showing the count of rainy days in each month.




# 3. Use Case: Customer Feedback Analysis for a Restaurant

A restaurant has been collecting customer feedback on their dining experience. The feedback includes ratings for various aspects such as food quality, service, ambiance, and an overall rating.

#### Objective:
The restaurant wants to analyze this feedback to understand customer satisfaction and identify areas for improvement.

#### Data Structure:
The data will consist of the following columns:
- `Date`: The date when the feedback was given.
- `Food Quality Rating`: A rating out of 5 for food quality.
- `Service Rating`: A rating out of 5 for service.
- `Ambiance Rating`: A rating out of 5 for the ambiance.
- `Overall Rating`: A rating out of 5 for the overall dining experience.

### Python Function: Customer Feedback Analysis

The Python function will:
1. Generate random customer feedback data.
2. Perform analysis to calculate average ratings and identify trends.

#### Steps for the Function:
1. **Data Generation**: Creating a random dataset based on the structure.
2. **Data Analysis**:
   - Compute average ratings for food quality, service, ambiance, and overall experience.
   - Identify any notable trends or patterns in the ratings.

```python
import pandas as pd
import numpy as np
from datetime import datetime, timedelta

def feedback_data(num_entries=500):
    # Seed for reproducibility
    np.random.seed(0)

    # Generating dates for the past 'num_entries' days
    end_date = datetime.now()
    start_date = end_date - timedelta(days=num_entries)
    dates = pd.date_range(start=start_date, end=end_date, freq='D')

    # Random feedback data
    data = {
        'Date': np.random.choice(dates, num_entries),
        # Ratings between 1 and 5
        'Food Quality Rating': np.random.randint(1, 6, num_entries),  
        'Service Rating': np.random.randint(1, 6, num_entries),
        'Ambiance Rating': np.random.randint(1, 6, num_entries),
        'Overall Rating': np.random.randint(1, 6, num_entries)
    }

    # Create DataFrame
    feedback_df = pd.DataFrame(data)

    return feedback_df

# Sample feedback data
feedback_data = feedback_data()
# Display the first few rows of the generated data
feedback_data.head()  
```

1. **Function Definition**: `feedback_data(num_entries=500)` - This function generates a dataset with `num_entries` number of feedback entries, defaulting to 500.

2. **Random Seed Setup**: `np.random.seed(0)` - Ensures consistent results each time the function is run.

3. **Date Range Generation**:
   - Computes `start_date` and `end_date` to span the past `num_entries` days.
   - Creates a range of dates using `pd.date_range`.

4. **Random Feedback Data Generation**:
   - `Date`: Randomly selected dates from the generated range.
   - `Food Quality Rating`: Random integers between 1 and 5.
   - `Service Rating`: Random integers between 1 and 5.
   - `Ambiance Rating`: Random integers between 1 and 5.
   - `Overall Rating`: Random integers between 1 and 5.

5. **DataFrame Creation**: The function compiles the generated data into a pandas DataFrame.

6. **Function Output**: The DataFrame, `feedback_data`, contains the simulated customer feedback.



The `analyze_feedback_data` function has processed the generated customer feedback data. Let's examine the function:

1. **Date Conversion**:
   - Converts the 'Date' column to a pandas `datetime` object for easier manipulation.

2. **Average Ratings Calculation**:
   - Computes the average rating for each aspect: food quality, service, ambiance, and overall experience.

3. **Trends Analysis**:
   - Adds a 'Month' column derived from the 'Date' column, formatted as a period.
   - Groups the data by 'Month' and calculates the average ratings for each month.
   - This helps identify any trends over time in the customer feedback.

```python

def analyze_feedback_data(feedback_df):
    # Convert 'Date' to datetime for easier analysis
    feedback_df['Date'] = pd.to_datetime(feedback_df['Date'])

    # Calculate average ratings
    avg_ratings = feedback_df[['Food Quality Rating',
    'Service Rating', 'Ambiance Rating',
    'Overall Rating']].mean()

    # Trends Analysis
    # Group by month and compute average ratings per month to identify trends
    feedback_df['Month'] = feedback_df['Date'].dt.to_period('M')
    monthly_avg_ratings = feedback_df.groupby('Month')
    [['Food Quality Rating', 'Service Rating', 
    'Ambiance Rating', 'Overall Rating']].mean()

    return avg_ratings, monthly_avg_ratings

# Analyze the generated feedback data
avg_ratings, monthly_avg_ratings = analyze_feedback_data(feedback_data)
# Display the analysis results
(avg_ratings, monthly_avg_ratings.head())  


```

- `avg_ratings`: A Series showing the average ratings for food quality, service, ambiance, and overall experience.
- `monthly_avg_ratings`: A DataFrame showing the average ratings for each aspect per month, useful for spotting trends over time.

The average ratings give a quick snapshot of the restaurant's performance in different areas. The monthly averages help to understand how customer perceptions have changed over time, highlighting any improvements or declines in different aspects of the dining experience. This information is vital for the restaurant to identify areas needing improvement and to track the effectiveness of any changes made.
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
