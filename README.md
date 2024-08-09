
# Spotify music analysis Dashboard

### Dashboard Link :https://app.powerbi.com/groups/me/reports/08b31b68-8eb5-4025-9198-b0ef3fb9fc87/abf01e3ab9a9f0de3d6d?experience=power-bi

## Problem Statement

In the ever-evolving landscape of music streaming, understanding song popularity trends is crucial for artists, industry professionals, and music enthusiasts. This project focuses on analyzing Spotify music data to identify trends in song popularity and to extract valuable musical information about each track.

Thus,this information will be useful for music industry professionals looking to make data-driven decisions and for enthusiasts interested in understanding the dynamics of popular music.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : In the report view, under the view tab, theme was selected.
- Step 5 : Since the data contains dates,months and years of songs released,thus in order to comibne them all, a new column was created of "ReleasedDate". 
-Step 6 : Also, one new table of dates and calendar was made to associate it with Spotify table. The one to many relation was made between both the tables.
- Step 7 : Visual filters (Slicers) were added for "Months", "Years", "Track name" and "Artist(s) name.
- Step 8 : The card visuals were added to the canvas, representing musical information of the songs & total streams of the songs.
- Step 9 : A bar chart was also added to the report design area representing the number of top 10 streams in the given period.
- Step 10 : The card visuals was used to represent different musical information mentioned below,

  (a)Danceability%

  (b)Acousticness%
  
  (c)Livness%
  
  (d)Energy%

  (e)Speechiness%
  
  (f)Valence%

- Step 11 : In the report view, under the insert tab, using shapes option from elements group a rectangle was inserted & similarly using image option spotify's logo was added to the report design area. 
- Step 12 : New table was created of date and calendae to make cardinality with spotify table.

for creating new table following DAX expression was written;
       
        Calendar = ADDCOLUMNS(CALENDAR(MIN('Spotify'[ReleaseDate]),MAX('Spotify'[ReleaseDate])),
     "Year", YEAR([Date]),
    "MonthName", FORMAT([Date], "MMMM"),
    "MonthNumber", MONTH([Date]),
    "Quarter", "Q" & FORMAT(QUARTER([Date]), "0"),
    "Day of Week", WEEKDAY([Date]), "DayName", FORMAT([Date], "dddd")


  snap of new calculate table,

![Picture1](https://github.com/user-attachments/assets/3bfcafdc-1461-4d77-bf2a-b8ca484c275a)
        
- Step 13 : New measure was created to combine date,month and year column

          ReleaseDate = DATE([released_year], [released_month], [released_day])

snap of new ReleaseDate ,

![image](https://github.com/user-attachments/assets/031cc67e-952a-4969-8261-4a23170e914e)

 Also, card visual of Total streams ,Average streams and Count of streams is represented in below snap,

![Picturee3](https://github.com/user-attachments/assets/456ce7b0-e04a-4d95-908b-4d2f99baf343)

 
 - Step 14 : The report was then published to Power BI Service.
 
# Snapshot of Dashboard (Power BI Service)

![Picture4](https://github.com/user-attachments/assets/5fe88c04-bc8c-4442-a40a-321b3022690e)

 # Report Snapshot (Power BI DESKTOP)

 
![Dashboard](https://github.com/user-attachments/assets/93c4efbb-add7-474e-96e7-187b12e6f235)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Total Number of Streams = 489bn
         Count of streams = 952
         Average streams = 514.14M
           
### [2] Sum of streams by ReleaseDate

   It can be concluded that more streams were released between 2010 and 2020 as compared to other periods.
  
  
  ### [3] Top 10 streamed songs

 ### [4] Some other insights
 
 ### Musical information of each song
 
 Each song has different pecentage of energy level , Liveness, Danceability and so on.
 People can choose genre according to their prefrence.
 
 ### Top 3 artists
         
### Tracks and streams for different months was calculated

September was witnessed with most number of average streams.

# Spotify music analysis-Dashboard.md.txt
Displaying #Spotify music analysis-Dashboard.md.txt.
