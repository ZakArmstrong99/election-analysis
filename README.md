# election-analysis

## Overview of Election Audit:
The purpose of this analysis was to write python code in order to print election results of three counties and
candidates, along with the winner. The reason python was necessary was due to the fact the results were on 
a csv file that has over 300,000 rows, and python makes it efficient to retrieve this data. Not only does 
the code retrieve the data, but also does calculations that adds the total vote counts for each county and candidate.

## Election-Audit Results:

- In this congressional election, there were **369,711 total votes cast.** This was found by using the reader function.
  With this funciton it is possible to read through all the rows of the election results csv. Utilizing the reader function,
  I made an empty variable to hold the total votes and used a loop to add every vote to the variable.
- The votes for each county were **38,855 votes (10.5%) from Jefferson county, 306,055 votes (82.8%) from Denver county,
  and 24,801 votes (6.7%) from Arapahoe county.** This data was by looping through the election results csv. First I had to
  make an empty variable called county_name. Within the loop that goes through all the rows, the line county_name = row[1]
  adds the name of the county to the county name variable. To get all of the county names, an if statment was used that adds
  the county name to a list called counties and puts those counties into a dictionary, adding the amount of votes as the
  values for each county. To get the percentage of votes for each county, I used a formula that divides amount of votes for
  each county by the total votes multiplied by 100.
- The county with the most votes was **Denver, with 306,055 votes (82.8%)** This was determined by using an if else statement within
  a loop. What the if else statement does is adds the county and votes to variables that holds county with the most votes and the
  amount of votes. First, if the county_count variable is higher than the county_vote variable (This one holds the highest vote).
  The else part is important, as it tells the code to stop when it gets the highest vote count and pulls the name of the county
  that has these votes.
- The votes for each candidate were **85,213 votes (23.0%) for Charles Casper Stockham, 272,892 votes (73.8%) for Diana DeGette,
  and 11,606 votes (3.1%) for Raymon Anthony Doane.** The candidates were found in a similar way as the counties. Rather than pulling
  from the row that has counties in the loop, I used candidate_name = row[2]. An if statment was then used to add the candidates name to 
  a list of all candidates.
- The winner of the election is **Diana DeGette with 272,892 votes (73.8%)** To find the candidate with the most votes, an if statment
  was used which adds the values of the candidates votes and candidate name to variables containting the correct candidate. The same percentage
  formula was used as earlier, but using the candidate_name variable and votes for each candidate instead.

## Election-Audit Summary:
With some minor modification, this script could be used for any election. If the format of the csv containt election results follows the same
formating as the one used for this anaylsis, the code show accurately print out results similarly for this election. That being said, some minor tweaks
may be needed for it to work properly. An issue that comes to mind is the if else statement that finds the county with the most votes. Currently
the way the code works is that it gets the name of the winning county by moving back an index in the counties dictionary. The reason this works in this
analysis is that there are only three counties, and the winning county is the second to last index. If more counties were to be added, this part of the code may need to be adjusted. Other than that the code should work for every election. This code is very useful as it makes sorting through hundred of thousands rows efficienty and printing the results in a way that is easy to read.
