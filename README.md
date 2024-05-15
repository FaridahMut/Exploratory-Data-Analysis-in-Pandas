# Exploratory-Data-Analysis-in-Pandas

## Introduction
This project explores a world population dataset using Pandas, a powerful Python library for data manipulation and analysis.

## Aim of the project
The main is to gain insights into global demographics and uncover interesting patterns and relationships within the world population data.

### Questions
1. Which countries have the highest and lowest world population percentage?
2. Which countries have the highest and lowest growth rate?
3. How does the population in various year correlate to each other?
4. Are there any continents that have growth faster and in which ways?
5. Are there any outliers in the dataset?

## Procedure used
1. The first steps in performing an EDA is to get an overall view of the data
   * Use **df.describe()** this gives you a quick summary of the columns including the count, mean, std, min and max values
   * Identify null values, because they can interfere with the overall analysis. use **df.isnull().sum()** to get a sum of the null values
   * Use** df.nunique()** to see the count of unique to make sure that looks ok. E.g. continent has 6 unique values 
3. Use the **df.sort_values(by="World Population Percentage").head(5)** to sort the data to answer question 1 and 2
4. Use the **df.corr()** function to see how the data correlates to each other. Display this in a hit map for a better visualization

## Findings 
1. Looking at the world population, the top 5 countries are; 
  * Highest population are; China, India, United States, Indonesia and Pakistan
  <img width="1579" alt="image" src="https://github.com/FaridahMut/Exploratory-Data-Analysis-in-Pandas/assets/160776452/c87b38e3-f66f-4b10-ac37-153ef0abb512">
  
  * Lowest population are; Liechtenstein, Jersey, Seychelles, Isle of Man and Sint Maarten
 <img width="1510" alt="image" src="https://github.com/FaridahMut/Exploratory-Data-Analysis-in-Pandas/assets/160776452/6a983058-5791-4563-8571-cb1da7c08e7e">

2. Looking at the Growth rate, the top 5 countries are;
   * Highest growth rate are; Moldova, Poland, Niger, Syria and Slovakia
     <img width="1652" alt="image" src="https://github.com/FaridahMut/Exploratory-Data-Analysis-in-Pandas/assets/160776452/e08937ac-369c-48eb-b1b1-a7c9c059bb6c">
   * Lowest growth rate are; Ukraine, Lebanon, American Samoa, Bulgaria and Lithuania
    <img width="1613" alt="image" src="https://github.com/FaridahMut/Exploratory-Data-Analysis-in-Pandas/assets/160776452/e40306ae-ed36-4e7a-83a8-fa372f90d17b">
    
3. Looking at the correlation in the data, we use a hitmap to have a clear visualization by using the function **sns.heatmap() **and edit the dimension of the hitmap by using **plt.rcParams['figure.figsize'] = (20,7)**
   * We can see the populations in different years and world population percentage are highly correlated
   * The other variables like density per km2 and growth rate are not correlated to the population
   * Area is somewhat correclated, which indicates that larger Area larger population
   
<img width="467" alt="image" src="https://github.com/FaridahMut/Exploratory-Data-Analysis-in-Pandas/assets/160776452/36bae5dc-36c7-414c-bf39-3c91c5146ae8">

4. To see which continents have the fastest growth rate, we will growth the data by continents and get the mean values and sort in descending order **df.groupby('Continent').mean().sort_values(by="2022 Population",ascending=False)**.
   * we also use the transpose function to switch the rows and columns before plotting the chart
   * We can see** Asia** has been in the lead from 1970s and has a **boom on early 2000s**
   * **Other continent**s have a **steady growth** 
   * **Africa's** population has **nearly doubled** in the last 50 years
   * **Oceania** remaining almost **the same**.
     <img width="601" alt="image" src="https://github.com/FaridahMut/Exploratory-Data-Analysis-in-Pandas/assets/160776452/9b4c571c-8b92-4a50-b9ce-edfe703158bc">

5. I used box plots to understand the distribution of the data and to find any outliers.
  * using the function **df.boxplot()** there are no outliers in the dataset

