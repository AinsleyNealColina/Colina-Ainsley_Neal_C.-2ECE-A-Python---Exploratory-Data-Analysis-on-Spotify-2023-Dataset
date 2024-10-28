# Colina-Ainsley_Neal_C.-2ECE-A-Python---Exploratory-Data-Analysis-on-Spotify-2023-Dataset

This assignment examines the key factors driving music track popularity, focusing on streaming data, top performers, and temporal trends. Analyzing streams revealed central tendencies and helped identify high-performing tracks and artists. Correlations between attributes like bpm, danceability, and energy provided insights into characteristics boosting streams. Temporal trends highlighted seasonal release patterns, while advanced analyses uncovered patterns by musical key, genre, and artist presence in playlists. A comparison of Spotify and Apple playlists further details the differences between the platforms. Overall, 
this study offers a well-rounded view of what contributes to streaming success in music.

## The task we are given for this assignment is to:

## Find how many rows and columns does the dataset contain?

We can do this by importing pandas as pd then we can copy the path of our csv file then display and in the output we can see the rows and columns.

## What are the data types of each column? Are there any missing values?

The track_name,artist(s)_name,key, and mode are strings while the rest are int or numeric values.Yes, there are many missing values mostly associated with the track_name,and artist(s)_name because some of the letter it contains are ñ and other unique characters resulting in missing values.

## What are the mean, median, and standard deviation of the streams column?

To find the mean, median, and standard deviation first we have to ensure the values are integers or numeric to do input the code df['streams'] = pd.to_numeric(df['streams'], errors='coerce') then type mean= df['streams'].mean(), and do it to the rest, then change the last part whether it is median or std.

## What is the distribution of released_year and artist_count? Are there any noticeable trends or outliers?

To visualize the distribution of released year and artist count, we need to use Matploitlib and seaborn, a histogram for release years, which reveals trends in music releases from 2015 to 2024, and a boxplot for artist counts, highlighting any potential outliers and the overall spread, allowing us to identify patterns such as increases in releases or variations in the number of artists per track.

## Which track has the highest number of streams? Display the top 5 most streamed tracks.

To display the top 5 most streamed tracks first we need to make sure all of the values are integers,then add the function df.nlargest (5,'streams') the 5 is the indication to show the top 5.

## Who are the top 5 most frequent artists based on the number of tracks in the dataset?

To show this we need to put value_counts() to calculate how many times have the artist appeared in the csv or data then display the artist name and how many times they have appeared.

## Analyze the trends in the number of tracks released over time. Plot the number of tracks released per year.

To analyze the trend we need to use matploit for better visualization of the number of tracks released over time. To do this first we need to filter the dataset to include only tracks released between the years 2000 and 2023. It then counts the number of tracks released each year by using value_counts() on the released_year column and sorts the results in ascending order using sort_index(), creating a series where the index represents years and the values represent the count of tracks for those years.
Next, a plot is created to visualize the number of tracks released over time. The plt.figure() function sets the figure size, and plt.plot() is used to create a line plot with markers for each data point, connecting the number of tracks per year. The plot is titled "Number of Tracks Released over time (2000-2023)," and appropriate labels are added for the x-axis (Year) and y-axis (Number of Tracks Released). The x-tick labels are rotated for better readability, and a grid is added for easier visualization. Finally, plt.tight_layout() adjusts the layout to ensure everything fits well, and plt.show() displays the plot, allowing users to see trends in music releases over the specified period.

## Does the number of tracks released per month follow any noticeable patterns? Which month sees the most releases?

To see noticeable pattern over time we once again need to visualize it using a histograph.1st it needs to count the number of tracks released each month by using value_counts() on the released_month column and sorts the results in ascending order. It then creates a bar plot to visualize this data, setting the figure size and using sky blue bars to represent the track counts for each month. The plot includes a title, axis labels, and customized x-tick labels displaying abbreviated month names. Grid lines are added along the y-axis for clarity, and plt.tight_layout() ensures that everything fits well before displaying the plot with plt.show(). Additionally, the code identifies the month with the highest number of releases using idxmax() and max(), printing out which month had the most releases along with the corresponding count.

## Examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%. Which attributes seem to influence streams the most?

To examine the correlation between streams and musical attributes like bpm, danceability_%, and energy_%.
we need to visualize it for better understanding.First we once again need to convert it to integers to avoid errors,next step we need to convert it, then we need to select the streams,bpm,danceability,and energy because that is what we need to find, and we need to use matplotlib and seaborn for the heatmap to visualize the correlation matrix,and we need to identify the attributes with the highest correlation with streams, then print for the result.

## Is there a correlation between danceability_% and energy_%? How about valence_% and acousticness_%?

To find the correlation we need the function plt and sns for better visualization and understanding, the visualization we use is scatter plot.If the correlation coefficient is close to 1, it indicates a strong positive correlation, meaning that as danceability increases, energy tends to increase as well.If the coefficient is close to -1, it indicates a strong negative correlation, meaning that as danceability increases, energy tends to decrease.A coefficient close to 0 suggests little to no correlation between the two variables.

## How do the numbers of tracks in spotify_playlists, spotify_charts, and apple_playlists compare? Which platform seems to favor the most popular tracks?

To do this we need to convert first to numeric with pd.to_numeric(),second Fill Missing Values for Binary Columns.3rd track the count of the spotify_playlists, spotify_charts, and apple_playlists.4th create a bar plot for visualization.Then last add a print function calculating the number of tracks in spotify_playlists, spotify_charts, and apple_playlists for specific values

## Based on the streams data, can you identify any patterns among tracks with the same key or mode (Major vs. Minor)?

First we need to convert first to numeric with pd.to_numeric().Second we need to group the key mode using the df.groupby.Then lastly we need to use seaborn and matplotlib for visualization of the barplot.For better understanding and visualization(Yes, the average stream most likely wants the key with a major rather than a minor. The major has 8/11 more average streams than a minor with 3/11 average streams).

## Do certain genres or artists consistently appear in more playlists or charts? Perform an analysis to compare the most frequently appearing artists in playlists or charts.

To do this 1st we need to calculate the playlist counts and chart counts,2nd rename the columns for clarity.3rd we need to merge the dataframes the two DataFrames on the artist name, using an outer join to ensure all artists are included even if they don’t appear in either playlists or charts, and fills any resulting NaN values with 0. 4th Converting the count to integers: then it converts the playlist_count and chart_count columns to integer type for consistent formatting.Lastly sorting and displaying the top 10, it sorts the summary DataFrame by playlist and chart counts in descending order to prioritize artists with the most appearances and displays the top 10 artists by these counts.
