# World Population Evolution Visualization
### Data Visualization with D3 - Udacity's Data Analyst Nanodegree

Direct link to the visualization [bl.ocks.org](http://bl.ocks.org/altrome/raw/ae6d6aa352f08ea339300cd38f5a8c9d/)

## Summary

This project wants to show, in a visual and easy to understand way, how the world population has evolved since 1800. The dataset used, was extracted from gapminder's data repository [link](https://docs.google.com/spreadsheets/d/1IbDM8z5XicMIXgr93FPwjgwoTTKMuyLfzU6cQrGZzH8/pub?gid=0).

The process followed to deal with the dataset was:

1. Explore the CSV file with common tools like excel, to understand its structure and see if it was possible to add more information to enrich the visualization. 
2. I found that each line of the dataset, was referenced to the official name of the country, and I regarded that work with names, in some cases with spaces, would be a problem, so I started to find a way to work with some standard references, and I found that ISO maintains a list of ISO codes with 2 or 3 letters and 3 numbers [link](https://en.wikipedia.org/wiki/List_of_sovereign_states_and_dependent_territories_by_continent_(data_file)), so I decided to export these codes and merge with the original file. 
3. Working with R, the file was cleaned and reworked to meet the specifications I determined previously. The files with the R code and the original files exported from excel can be found at 'R_stuf' folder.
4. Once the file was completely defined, I decided to think how to show the information to the user in an attractive way and trying to put some gamification in the experience.

The overall process for explore and clean the data took me about 30 hours since I found the optimal solution.

## Design

This project was motivated by a post published at the Spanish version of "The Huffington Post" [link](http://www.huffingtonpost.es/ansgar-seyfferth/la-poblacion-mundial-crec_b_9605508.html?ncid=tweetlnkeshpmg00000001) that, despite being well documented, I think that an interactive visualization would improve the user engagement and compress the information shown to the user at the same time. The final design is structured in three main blocks:

1. Short presentation of the visualization, explaining the most important insights of the data to guide the user
2. A big world map used to let the user move the mouse over the countries and see their Population evolution line highlighted 
3. All the Countries population evolution lines plus the average population line to compare if a country is above or below the average

The design process was not easy, because I needed to understand how d3 works, and practice a lot. The map was the easiest part, because I used the code used in the course, but all the rest was fully coded from scratch. In addition, I'm not an expert in javascript, so I needed to refresh and/or learn some concepts.

The first visualization, was made with a linear Y axis, and countries like China or India have a population evolution line much greater than the rest of the countries, so I decided to use a logarithmic scale, maintaining the original linear scale in case someone wants to see the data that way.

Once the visualization was done, I started with the user interaction, and some problems appeared, but the most important was that the lines were plotted over the map, and some countries were unable to be selected. Searching over the net, I found some interesting posts to deal with that problem.

The final design took me about 30 hours, 15 of them, were used to solve interaction problems.

## Feedback

Some online and offline users gave me some feedback that I used to improve my design in some cases, and in other cases I was not able to implement the provided ideas. Here is a list of them and the action done:

* "Looks good, but there is an strange behavior when moving the mouse over a country with line over it." - As I mentioned above, this was one of the main challenges, because of the order of the SVG elements in the chart. Finally I solved it.
* "Some colors of the map merge with the lines and it's difficult to distinguish the evolution lines." - True... I search for an optimal color combination and played with opacities. 
* "Can the y-axis update itself when you choose a country such that the y-max value is lowered for smaller populations?" - Good idea, but After search a lot, I was not able to implement it... I'll continue searching
* "Would be cool if you could pick two or more countries at the same time to compare the populations." - True... but the main objective of the visualization is to show one country evolution and not to compare one with another, but I'll try to test it.

## Resources

http://www.nytimes.com/interactive/2013/03/29/sports/baseball/Strikeouts-Are-Still-Soaring.html?ref=baseball 
http://fiddle.jshell.net/4xZwb/4/
https://gist.github.com/phil-pedruco/10447085
http://stackoverflow.com/questions/14167863/how-can-i-bring-a-circle-to-the-front-with-d3
https://en.wikipedia.org/wiki/List_of_sovereign_states_and_dependent_territories_by_continent_(data_file)
https://vec.wikipedia.org/wiki/ISO_3166-1
https://github.com/mledoze/countries
https://docs.google.com/spreadsheets/d/1IbDM8z5XicMIXgr93FPwjgwoTTKMuyLfzU6cQrGZzH8/pub?gid=0