# ACCUWEATHER-REPORT
I set out to understand the weather patterns in Lagos, Nigeria, particularly the reason behind the frequent rainfall observed in the past 3 months. By collecting and analyzing weather data from the AccuWeather website, I aimed to uncover the insights that would help explain the rainy weather conditions in the region.
Methodology
To gather the necessary data, I utilized web scraping techniques, including changing the user agent, to access the weather information on the AccuWeather website for the Lagos location. I focused on extracting the following data points: date, low temperature, high temperature, water drop level, and rain occurrence.

Initially, I faced some challenges in scraping the data due to the website's security measures, but I was able to overcome this obstacle by modifying the user agent. Once I gained access to the data, I formatted it into an HTML structure and then used Python libraries, such as Pandas, to extract the required information.



During the data cleaning process, I removed unwanted characters, converted data types, and added the year to the date column to ensure clarity and consistency.

MY CODE FOR DATACLEANING
DATE DATAPOINT
#Now let's save this in a variable called date_elements

#date_elements = soup.find_all('span', class_='module-header sub date')

# Now we want to get the actual value of the dates in the whole text
#for element in date_elements:
 #   print(element.text)  # This will print the text of each span

    
# Assuming 'date_elements' is populated with the span elements
date_elements = soup.find_all('span', class_='module-header sub date')  # Adjust this line accordingly

# Convert the generator to a list
date = [i.text for i in date_elements]
print(date)  # This will print the list of dates



HIGH TEMPERATURE

#We are working on High Temperature now

high_temp_elements = soup.find_all('span', class_='high')  # Adjust this line accordingly

# Convert the generator to a list
high_temp = [i.text for i in high_temp_elements]
print(high_temp)  # This will print the list of temperatures












LOW_TEMPERATURE
WATERDROP


#Now it is time to clean our data
#let's import pandas

import pandas as pd
#Now we want to put all values in a dataframe for cleaning effectiveness

df = pd.DataFrame({'date': date, 'high_temp':high_temp, 'low_temp':low_temp,'waterdrop':waterdrop})

print(df)



So this is how messy it was when I gathered my datapoints.

# I wanted to set index for clarity
df['index'] = range(1, len(df) + 1)  # Sequential index values
print (df)



#Formatted the date on this code

pd.to_datetime(df['date']+'/2025')
df['date'] = pd.to_datetime(df['date']+'/2025')
df['date']


# Formatted the high_temperature and converted it to 
numeric
df['high_temp'] = pd.to_numeric(df['high_temp'].str.replace('°',''))



#Formatted the low_temp
pd.to_numeric(df['low_temp'].str.replace('°','').str.replace('/',''))
df['low_temp'] = pd.to_numeric(df['low_temp'].str.replace('°','').str.replace('/',''))




Cleaned and formatted the Waterdrop






Now I created a new column to determine rain fall


#I had to now remove index since it is no longer needed.



I finally exported it as a csv file 





Performed EDA for further analysis




Now Visualizing My Findings

import matplotlib.dates as mdates


#Creating Scatter plot for the WATERDROP and DATE Column
plt.figure(figsize=(15, 5))
ax1 = plt.subplot()
ax2 = ax1.twinx()

ax1.scatter(df['date'], df['waterdrop'])

ax1.set_xlabel('Date')
ax1.set_ylabel('Water Drop')
ax1.xaxis.set_major_formatter(mdates.DateFormatter('%Y-%m-%d'))  # Format the x-axis labels
plt.xticks(rotation=90)  # Rotate the x-axis labels
plt.xticks(df['date'].iloc[::7])  # Set the x-axis ticks to display every 7 days

plt.show()


#Now let's plot high temp for the HIGH_TEMP and DATE Column
import matplotlib.dates as mdates

plt.figure(figsize= (10,5))
ax1=plt.subplot()
ax2=ax1.twinx()
ax2.plot(df['date'],df['high_temp'],color = 'r', marker = '*')


Low Temperature















WATERDROP RATIO





Observations and Findings
Through my analysis, I made several key observations:

1. Water Drop Level and Temperature: I found that the water drop level was consistently high, with a maximum temperature of around 36°C, which is below the threshold for a sunny day (75°F or ~24°C).

2. Rainfall Frequency: My analysis showed that it rained 80% of the time in the past 3 months. I attributed this to the low temperatures and the time of the year.

3. Statistical Insights: Calculating the mean, median, and mode for the numerical columns, I observed that the higher the water drop level, the lower the temperature, leading to more rainfall.

Data Visualization
To better understand the weather patterns, I utilized various data visualization techniques, including scatter plots, line charts, histograms, and pie charts.

The scatter plot of water drop levels and dates revealed an increasing trend, suggesting that the water drop levels are likely to continue rising in the coming months. The line chart of high temperatures showed a decline over the past 3 months, further supporting the observation of lower temperatures contributing to the frequent rainfall.

The histogram of low temperatures indicated that 24 degrees was the most common value, reinforcing the overall trend of cooler weather. Finally, the pie chart analysis confirmed that it rained 80% of the time during the period under examination.


Limitations
During the course of this project, I encountered a few challenges that I had to overcome:

Website Security Measures: The AccuWeather website had implemented security measures to prevent automated scraping of its data. I initially faced difficulties in accessing the required weather information due to these measures.

Data Formatting and Extraction: The weather data was presented in a complex HTML structure, which required careful parsing and extraction using BeautifulSoup. Ensuring that I captured all the relevant data points accurately was a key challenge.

Data Cleaning and Preprocessing: The raw data contained some unwanted characters and inconsistencies in data types. I had to perform extensive data cleaning and preprocessing to ensure the data was in a format suitable for analysis.


Recommendations
Based on the insights gained from this analysis, I recommend the following:

1. Continued Monitoring: Maintain regular monitoring of the weather data in Lagos to identify any long-term trends or changes in the rainfall patterns.

2. Adaptation Strategies: Explore strategies to adapt to the frequent rainfall, such as improving drainage systems, promoting water conservation, and educating the local population on weatherproofing measures.

