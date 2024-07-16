# Netflix
A dynamic dashboard to give the insights of the Netflix content
Power BI Dashboard Projects
Link:https://app.powerbi.com/links/WF3VfyvpuU?ctid=7e2137dd-6ef9-46eb-974e-5086fd7cdd20&pbi_source=linkShare
1. NETFLIX
Project Objective
The objective of this project is to design and develop a comprehensive Netflix dashboard to analyze the performance of Netflix content (movies, tv series) in terms of views, ratings, votes , genre, contents as per the country , user engagement , recommendation effectiveness, competitor benchmarks, and marketing campaign impacts. This will provide actionable insights to optimize content strategy, enhance user experience, and drive business growth.

Import data to Power BI

1.	Prepare Excel file
2.	Import Excel file to Power BI
3.	Data cleaning
4.	Data Processing

DAX Queries
1.	Number of show title = DISTINCTCOUNT(Listings[Title])
2.	Number of Votes = sum(Listings[Votes])
3.	Average Rating = AVERAGE(Listings[Rating])
4.	votes per title = (divide([# Votes],[# title]))
5.	Total movies = CALCULATE([# title],FILTER(Listings,Listings[Listing type]="Movie"))
6.	Movie Average Rating = CALCULATE([Average Rating],FILTER(Listings,Listings[Listing type]="Movie"))
7.	Movie votes = CALCULATE([# Votes],FILTER(Listings,Listings[Listing type]="Movie"))
8.	% of movies vote labels = 
var _percentoftotal=round(DIVIDE(Movies[Movie votes],[# Votes]),2)*100
var _percentoftitle=FORMAT(ROUND(DIVIDE(Movies[Movie votes],[# Total movies]),0),"#,##")
RETURN
"(" & _percentoftotal &"%) | "& _percentoftitle & " votes per title" 
9.	Total TVshows = CALCULATE([# title],FILTER(Listings,Listings[Listing type]="television"))
10.	TV shows Average Rating = CALCULATE([Average Rating],FILTER(Listings,Listings[Listing type]="Television"))
11.	TVshow votes = CALCULATE([# Votes],FILTER(Listings,Listings[Listing type]="Television"))
12.	Listing type = 
13.	switch(
14.	    true(),
15.	    Listings[Type] in {"movie","tvMovie"},"Movie",
16.	    Listings[Type] in {"tvEpisode","tvMiniSeries","tvMovie","tvSeries","tvShort","tvSpecial"},"Television")
Project Insights
1. Total shows were 5,501 among which 2634 are movies and 2687 are TV shows.
2. Average rating is 6.7
3. The total user votes for the shows is more than 115 million among which 64% percent votes are for movie and 35 % votes are for tv shows.
4. Among the movies and shows the comedy genre has the highest number of the shows.
5. The War genre has the highest rating.
6. The United States has the highest number of content in the Netflix along with higher votes for the shows.
7. The Highest rated show in the Netflix is the TV series “Stranger things”



