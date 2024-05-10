# module-11-assignment
Module 11 Assignment
For the Module 11 assignment I will be using two websites.
For the first part I will be using this link: https://static.bc-edx.com/data/web/mars_news/index.html
And for the second part I will be using this link: https://static.bc-edx.com/data/web/mars_facts/temperature.html

For the first part of my data (part_1_mars_news) I created the BeautifulSoup object into a variable named 'mars_soup' and created the html.parser then printed a preview of this. I then extracted all the text elements by using the findall command and searching for the 'div' and the class of 'list_text'
I then created an empty list called 'mars_list' and then a for loop to extract the title and preview. I stored those into a dictionary and then appened the dictionary to the mars_list to then print out our results of the title and preview of the articles.

For the second part of my data (part_2_mars_news) I visited the website and then scraped the table by creating my html and Beautiful Soup object. I then extracted all the rows of data by using the find_all command to find all variables in the class of 'data-row'.
To store the data I created an empty list and then a for loop to append all data into our list. With our data, I then created a dataframe by first creating column names and then using pd.DataFrame. 
To prepare for data analysis I first used dtypes to find the types of each of my variables and then used pd.to_datetime and pd.to_numeric to change each variable accordingly. 
I then analyzed the data to answer the five questions presented:
1. How many months are there on Mars? To find this I used the group by method by grouping my dataframe by months and the count of months. I found that there were 12 months on Mars.
2. How many Martian days' worth of data are there? To find this I used the length function to find out how many data variables I had: 1867.
3. What is the average low temperature by month? To find this I used the groupby function on my dataframe again, grouping by the month, minimum temperature and then finding the mean (mars_df.groupby('month')['min_temp'].mean()).
   I then plotted this as a bar chart with the x-axis having the number of months and the y-axis containing the temperature.
   ![image](https://github.com/sophiagemanuel/module-11-assignment/assets/157437098/3b215250-0455-4393-b98b-d4dee14a2709)
  After, I replotted the chart to put it in ascending order, where we see that the coldest month is the third month and the hottest month is the eigth.
  ![image](https://github.com/sophiagemanuel/module-11-assignment/assets/157437098/2b363478-11d0-4012-812d-dfe4313bcd2a)
4. Average pressure by Martian month: To find this I again used the groupby method to find the pressure average per month (pressure = mars_df.groupby('month')['pressure'].mean()) and then plotting it with ascending values as a bar char. With this we find that on average the pressure is lowest on the sixth month and highest on the ninth month. 
  ![image](https://github.com/sophiagemanuel/module-11-assignment/assets/157437098/8602d1b0-33fb-4256-a49e-449c48548bfe)
5. How many terrestrial (earth) days are there in a Martian year? To start this out I created a first chart to get a glimpse of what I would be working with: 
  ![image](https://github.com/sophiagemanuel/module-11-assignment/assets/157437098/9973b92a-d8cd-42d8-9b0c-f44b3fa8322e)
  With this chart we see that the peaks would be a year for Mars, but for us it would be about two years. To find the amount of days is in a Martian year I first found the lowest solar longitude (ls) and the highest by sorting the dataframe by ls. With that I found that a martian year is a cycle of ls from 0 to 359. From that I found the list of dates from 0 ls by using the loc command and taking the first date (2013-08-01) and then using the loc command to find the date from the first date coming after our first date (2015-06-19). With this I used the datetime function to calculate the difference, giving us 685 days in a Martian year.
To finish my analysis out I added the column 'mars_days' and added the amount of days we had been on Mars into our dataframe. I then used this to plot the Days compared to the minimum temperature. 

For the last part I saved the dataframe into a CSV file named 'mars_data.csv'
