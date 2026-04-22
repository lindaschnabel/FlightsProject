# Flight Pattern Analysis in Europe
By Linda Schnabel


## Legend
This graph represents the daily flights on the eastern hemisphere. Each circle represents an airport. The flights are represented by the white lines. If there is a white line between two circles, it means there is a flight between those two airports. The bigger the circle, the higher the degree of that airport. The degree is determined by the amount of flight routes, or edges, the circle has. As the degree increases, the circles go from yellow to dark purple. Essentially, the more flights that an airport processes, the higher the degree.
## Findings
- Central Europe is very well connected through its flight patterns.
- Some regions of Europe have less active airports, but their degrees indicate that these airports serve as hubs.
- Asia’s airports are generally more dispersed with the exception of China. China has many airports that carry frequent flights within the country but not as many direct flights connecting to other countries.
- Western Europe has many flights that point beyond the map into America, indicating that it is common to fly out of Western Europe if travelling to or from America. 
- There is a notable lack of flight activity in the Middle East and Russia.
India has few airports, but two with high degrees that fly both to other airports with high degrees and directly into other regions like Western Europe and Southeast Asia.
 
## Data and Methods
### Data
The data comes from a dataset titled “Global Flights, Airports & Airlines” by DarkMatterNet on Kaggle. It contains three csv files: airports, routes, and airlines. The user collected this data from OurAirports and OpenFlights. This project only used the routes csv file since it contained all the flight routes along with airport ids which was sufficient for plotting the graph. The flights are all the flights that would happen on any given day, which means that some routes are repeated since there are multiple flights between the two airports in a day. 
### Methods
#### Data storage:
 	Each airport was stored in a dictionary titled airports. The airport’s IATA, an id for airports, functioned as the key with the values being its latitude and longitude. Each route was stored in a list called routes. The routes list consisted of each pair of airports that were connected by a flight which were identified by their IATA. 
#### Figure structure: 
Matplotlib was used to plot the figure itself and set the dimensions. “set_global” helped with making the map, “set_coastlines” plotted the borders of the continents, “set_extent” determined what parts of the global map would be displayed, and “add_feature” plotted each country’s borders. Some of these functions required ccrs which is part of the cartopy package. The cartopy package enabled the geographic aspects of the map such as the country borders to be plotted using matplot lib. 
#### Airports and Routes:
 The degree of each airport was determined by looping through routes and using Counter() to keep track of how many times each airport appeared in the routes file. 
Using for loops to iterate through each airport in the airports, 
Each airport was individually plotted on the map. Within the for loop, the degree of each airport would determine how it would be visualized. The degree would correspond with the plasma color map from matplotlib. The size of the circle was calculated using the following formula: degree[iata] * 0.06. The colors and sizes are meant to help visually understand the connectivity.
	Iterating through the routes list, I filtered out any routes including airports that were not featured in the airports dictionary and used the airports data’s longitude and latitude coordinates to plot lines between airports. 
 
## Importance of this project
	Understanding travel patterns provides insights into different fields. Airports with high degrees reflect that airline companies have found that the demand is high to fly into these areas. Having more people fly into your country is beneficial since it brings more people who can contribute to the country’s economy. People might fly in for tourism or for business. Overall, a country’s airport receiving lots of airplanes means people are very interested in visiting that country which means the country has influence. 
	Another application of this project is connecting it to epidemiology. If a disease breaks out in a certain country, understanding these flight patterns is key to keeping track of the spread. This is why airports had to shut down their travel so quickly during COVID. Being able to visually track not just which airports receive lots of people, but through which countries people are connecting to reach other destinations helps monitor where a disease may go next. 
	These flight patterns also reflect current issues. Notably, Russia has very few flights compared to its size and power as a country. This has to do with its restrictive government which makes it harder to go in and out of the country. On the other hand, you see many flights between European countries, a reflection of how the European Union makes it easier for its citizens to travel between countries without having to get a visa. 
	Monitoring these patterns helps understand how connected, or not, the world is to each other. This might open our eyes to seeing different parts of the world we don’t know as much about because we aren’t as exposed to them. I hope this project motivates people to go out of their way to learn more about the world. 



