#ACCUWEATHER REPORT 

I set out to understand the weather patterns in Lagos, Nigeria, particularly the reason behind the frequent rainfall observed in the past 3 months. By collecting and analyzing weather data from the AccuWeather website, I aimed to uncover the insights that would help explain the rainy weather conditions in the region.

Methodology
To gather the necessary data, I utilized web scraping techniques, including changing the user agent, to access the weather information on the AccuWeather website for the Lagos location. I focused on extracting the following data points: date, low temperature, high temperature, water drop level, and rain occurrence.

Initially, I faced some challenges in scraping the data due to the website's security measures, but I was able to overcome this obstacle by modifying the user agent. Once I gained access to the data, I formatted it into an HTML structure and then used Python libraries, such as Pandas, to extract the required information.


During the data cleaning process, I removed unwanted characters, converted data types, and added the year to the date column to ensure clarity and consistency.

Tools Used: 
1.Python: The primary programming language used for data scraping, cleaning, and analysis.
2.Requests: A Python library for making HTTP requests to the AccuWeather website.
3.BeautifulSoup: A Python library for parsing HTML and XML documents.
4.Pandas: A powerful data manipulation and analysis library in Python.
5.Matplotlib and Seaborn: Python data visualization libraries used for creating the various charts and plots.


#Code Implementation 
Here's the Python code I used to scrape and analyze the weather data:
https://github.com/calfav/ACCUWEATHER-REPORT/blob/main/CAPSTONE%20PROJECT%20-%20WEATHER%20REPORT.ipynb

#Observations and Findings
Through my analysis, I made several key observations:

1. Water Drop Level and Temperature: I found that the water drop level was consistently high, with a maximum temperature of around 36°C, which is below the threshold for a sunny day (75°F or ~24°C).
   

3. Rainfall Frequency: My analysis showed that it rained 80% of the time in the past 3 months. I attributed this to the low temperatures and the time of the year.

4. Statistical Insights: Calculating the mean, median, and mode for the numerical columns, I observed that the higher the water drop level, the lower the temperature, leading to more rainfall.

#Data Visualization
To better understand the weather patterns, I utilized various data visualization techniques, including scatter plots, line charts, histograms, and pie charts.

The scatter plot of water drop levels and dates revealed an increasing trend, suggesting that the water drop levels are likely to continue rising in the coming months. The line chart of high temperatures showed a decline over the past 3 months, further supporting the observation of lower temperatures contributing to the frequent rainfall.

 ![EXCEL PROJECT](https://github.com/calfav/ACCUWEATHER-REPORT/blob/main/SCATTER%20PLOT.PNG)

The histogram of low temperatures indicated that 24 degrees was the most common value, reinforcing the overall trend of cooler weather. Finally, the pie chart analysis confirmed that it rained 80% of the time during the period under examination.


#Limitations
During the course of this project, I encountered a few challenges that I had to overcome:

Website Security Measures: The AccuWeather website had implemented security measures to prevent automated scraping of its data. I initially faced difficulties in accessing the required weather information due to these measures.

Data Formatting and Extraction: The weather data was presented in a complex HTML structure, which required careful parsing and extraction using BeautifulSoup. Ensuring that I captured all the relevant data points accurately was a key challenge.

Data Cleaning and Preprocessing: The raw data contained some unwanted characters and inconsistencies in data types. I had to perform extensive data cleaning and preprocessing to ensure the data was in a format suitable for analysis.


#Recommendations
Based on the insights gained from this analysis, I recommend the following:

1. Continued Monitoring: Maintain regular monitoring of the weather data in Lagos to identify any long-term trends or changes in the rainfall patterns.

2. Adaptation Strategies: Explore strategies to adapt to the frequent rainfall, such as improving drainage systems, promoting water conservation, and educating the local population on weatherproofing measures.

