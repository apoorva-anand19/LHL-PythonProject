# Final-Project-Statistical-Modelling-with-Python

## Project/Goals

To understand the process of retrieving data from API requests and perfom EDA on it using various Python tools.

## Process

1. Checked out the City Bikes API to find which city to filter.

2. Chose the city (Vancouver) and added that as a filter parameter in the request.

3. Received all the data for the bike share companies in Vancouver.

4. City Bikes API was pretty straight forward, as it was easy to transform 
    it to a DataFrame and needed only one normalize action.

5. Next, Foursquare API was accessed. Here, the filter used was the latitutde and logitude of
    every bike station in Vacnouver. Filteres for bars, restaurants and bookstores also.

6. After that, parsed through the data to pull out information pertaining to establishment name, 
    location and street adreess and distance. 

7. Pushed that into a pandas DataFrame and also created csv so it can be used between 
    multiple notebooks.

8. Similary, Yelp API was accessed and because of yelps requests per day condition,
    kept the request limit to 300. Used the lat-long from City Bikes to pass as a
    parameter filter here. Was onyl able to filter out bars and restaurants.

9. After that, parsed through the data and extracted the establishment name, reviews, 
    lat-long, street name, pricing, categories and also inserted a key which corresponds 
    with every bike location of city bikes. 

10. Put this data also into a pandas Dataframe and created a csv too.

11. Of the two APIs accessed, decided yelp data was more relevent and decided to go with that.

12. Kept tables seperate and didn't perform a traditional join as it wouldc cause too many
    duplicates or have a lot of loss of data. 

13. Instead, created a table where each City Bike station will have the JSON of the corresping
    POIs from yelp, which can be extraxted and normalized. 

14. For vizualization purpose, added some columns in City bikes DataFrame, with the aggregate
    values of count and mean for the bars and restaurants around each bike station. This can be
    used for better Visualization of the data and for Model building.

16. Generated a scatter plot of the City Bikes stations and all the POIs. This over lap maps gives a 
    an idea how the POIs are located and the dispersion of the bike stations and to find any pattern.
    More about this undeer the 'Results' heading.

17. Made databases of the three DataFrames using sqlite3 and saved them in the same repo.

18. In model building, generated a couple of regression models and some heatmaps to find any 
    significant relationships between the features. Details under the 'Redults' heading.


## Results

- From the scatter plot, it is seen that there isn't really any pattern between the dispersion of the
    bike stations and POIs. 

- The Regression models give us some insight on the features. One information gathered is that,
    there might be some relationship between stations having E-Bikes and POIs that are bars.
    There is enough significance to prove that it is not just a mere coincidence.

## Challenges 

- One of the main chalenges faced was extracting the data from the JSON. 
    They are so intricately nested among lists and dictionaries, it was also very
    interesting to dig into that rabbit hole and come out neatly without casuing a cave in!

## Future Goals

- With more time, it would be interesting to see if this data set can be tranformed 
    to a more categorial one to do some categorical regression, as I fell that might
    give us more significant results for relationships between the features.
