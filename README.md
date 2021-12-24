# Movies-ETL

Extract, Transfer and Load Wikipedia data movies

### Overview of the analysis: Explain the purpose of the new analysis.

Amazing Prime loves the dataset and wants to keep it updated on a daily basis. we need to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. You’ll need to refactor the code from this module to create one function that takes in the three files—Wikipedia data, Kaggle metadata, and the MovieLens rating data—and performs the ETL process by adding the data to a PostgreSQL database.


### Results: Using images from the summary DataFrame and multiple-line chart.

- **Deliverable 1: Write an ETL Function to Read Three Data Files**

In Deliverable 1, we write a function that reads in the three data files and creates three separate DataFrames.

> the results for The wiki_movies_df DataFrame is

![This is an image](https://github.com/samiramghd/Movies-ETL/blob/main/Resources/wiki_movies_df.PNG)

> the results for The kaggle_metadata DataFrame is

![This is an image](https://github.com/samiramghd/Movies-ETL/blob/main/Resources/kaggle_metadata.PNG)

> the results for The ratings DataFrame is


![This is an image](https://github.com/samiramghd/Movies-ETL/blob/main/Resources/ratings.PNG)

- **Deliverable 2: Extract and Transform the Wikipedia Data**

In Deliverable 2 we extract and transform the Wikipedia data so we can merge it with the Kaggle metadata. While extracting the IMDb IDs using a regular expression string and dropping duplicates, use a try-except block to catch errors.

> the results for The wiki_movies_df DataFrame is

![This is an image](https://github.com/samiramghd/Movies-ETL/blob/main/Resources/wiki_movies_df2.PNG)


> the results for The the columns from wiki_movies_df DataFrame to a list is

![This is an image](https://github.com/samiramghd/Movies-ETL/blob/main/Resources/wiki_list.PNG)


- **Deliverable 3: Extract and Transform the Kaggle data**

In Deliverable 3 we extract and transform the Kaggle metadata and MovieLens rating data, then convert the transformed data into separate DataFrames. Then, we’ll merge the Kaggle metadata DataFrame with the Wikipedia movies DataFrame to create the movies_df DataFrame. Finally, we’ll merge the MovieLens rating data DataFrame with the movies_df DataFrame to create the movies_with_ratings_df.

> the results for The movies_with_ratings_df DataFrame is

![This is an image](https://github.com/samiramghd/Movies-ETL/blob/main/Resources/movies_ratings.PNG)


> the results for The movies_df DataFrame is

![This is an image](https://github.com/samiramghd/Movies-ETL/blob/main/Resources/movies_df.PNG)


- **Deliverable 4: Create the Movie Database**

In Deliverable 4 we need to add the movies_df DataFrame and MovieLens rating CSV data to a SQL database.
we run a query on the PostgreSQL database that retreives the number of rows for the movies and ratings tables which we can see in the pictures below.

![This is an image](https://github.com/samiramghd/Movies-ETL/blob/main/Resources/movies_query.PNG)

![This is an image](https://github.com/samiramghd/Movies-ETL/blob/main/Resources/ratings_query.PNG)

> After running the queries we confirm that the movies table has 6,052 rows and the ratings table has 26,024,289 rows.

### Summary:

In this project we also learn how to move the data from Pandas into a PostgreSQL database.
after we extract and transform our data, we load it into a SQL database. We create a new database and use the built-in **to_sql()** method in Pandas to create a table for our merged movie data and also import the ratings data into its own table.
