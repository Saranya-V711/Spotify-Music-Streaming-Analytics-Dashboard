# Spotify-Music-Streaming-Analytics-Dashboard
Interactive Power BI dashboard analyzing Spotify streaming data using advanced DAX formulas to track user engagement, artist performance, and listening trends with actionable insights.

This repository presents a Power BI dashboard built to analyze and visualize Spotify streaming data, providing actionable insights into user listening behavior, artist popularity, and track performance. By leveraging advanced DAX formulas, the dashboard offers dynamic metrics, year-over-year comparisons, and user engagement patterns that can drive strategic decisions and improve content recommendations.

✅ Project Highlights

Designed a robust data model integrating Spotify streaming history with a date dimension, enabling time-based analysis and trend exploration.

Created over 20 custom DAX formulas to derive key metrics and calculated columns, allowing for in-depth analysis of listening patterns and artist performance.

📊 Key Metrics & DAX Implementations

Some of the significant formulas implemented include:

# Average Listening Time

Avg Listening Time = AVERAGE(SpotifyData[Minutes Listened])


Calculates the average minutes users listened to tracks.

# Track Frequency

Track Frequency = COUNTROWS(SpotifyData)


Measures how often each track was played.

# Distinct Artists Count

Distinct Artists = DISTINCTCOUNT(SpotifyData[Artist Name])


Counts the number of unique artists over a period.

# Year-over-Year (YoY) Listening Trend

YoY Listening = 
CALCULATE([Avg Listening Time], 
  SAMEPERIODLASTYEAR('Date'[Date]))


Compares average listening time with the previous year.

# Top Artists Highlight (Min-Max Logic)

Top Artist = 
IF([Avg Listening Time] = CALCULATE(MAX([Avg Listening Time]), ALL(SpotifyData)), "Top Artist", "Other")


Identifies artists with the highest listening times.

# Listening Pattern by Weekday

Avg Listening by Weekday = 
AVERAGEX(
  FILTER(SpotifyData, WEEKDAY(SpotifyData[Date]) = 3),
  SpotifyData[Minutes Listened]
)


Analyzes listening patterns specific to weekdays.

📂 Files Included

Complete Power BI report (.pbix file) with interactive visuals

Dataset used for streaming analysis with over 13,000 tracks and 4,000+ artists

Documentation of data modeling, relationships, and implemented DAX formulas

Sample reports demonstrating listening trends, artist comparisons, and user behavior patterns

🚀 Impact

* Revealed patterns such as higher listening activity on weekdays

* Enabled identification of top-performing artists and albums over time

* Provided year-over-year metrics to track audience growth and engagement trends

* Empowered stakeholders with data-backed recommendations to enhance user experience and content strategy

🛠 Technologies Used

* Power BI Desktop

* DAX (Data Analysis Expressions) for advanced calculations

* Data modeling and visualization best practices

This repository is a practical example of how structured data analysis using Power BI and DAX can transform raw streaming data into meaningful business insights.
