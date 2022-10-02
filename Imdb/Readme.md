# IMDb Project Deliverables

•  Ingest initial datasets into ingestion schema (staging tables) <br />
•  Integrate data into integration schema(dimensional data model) <br />
•  Load data into BI schema to better answer BI questions <br />
•  Perform data consistency & cleansing processes as appropriate <br />
•  Design and create BI visualizations answering business questions <br />

## Data Integration <br />
### Ingest initial datasets into ingestion schema (staging tables) <br />
•  IMDb core data for Movies <br />
•  IMDb core data for TV <br />
•  IMDb Mojo data for Box Office, Brands, Franchises and Genes <br />
•  The Numbers data for movie box office <br />
•  MovieLens data for movie ratings <br />
•  ISO reference data for countries & languages <br />

### Integrate data into integration schema (dimensional data model) <br />
•  Dimensions: much of core data is dimensions <br />
•  Facts: examples are box office sales, ratings, budgets, etc. <br />

# IMDb Dimensional Model
![image](https://user-images.githubusercontent.com/71230572/193437914-993aab99-4124-430c-b601-1edde5384bb8.png)


•  Basic information about people in cast, crew, writers and directors <br />
•  Basic titles information <br />
•  Enhanced title information such as aliases, languages, countries <br />
•  Director and writer information for all the titles <br />
•  TV episodes information <br />
•  Principal cast/crew for titles <br />
•  Title Ratings <br />
•  Box Office revenue <br />
•  Movie franchises <br />
•  Movie brands <br />
•  These is also data about: Countries, Languages, Movie Genres, Job Categories, Types of Titles, Franchises, Brands <br />
•  All titles and names should have web urls as attributes in dimensional model <br />
   Example :
   > Title: https://www.imdb.com/title/ + tconst <br />
   > Person: https://www.imdb.com/name/ + nconst <br />

    

    
