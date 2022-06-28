# election-analysis

## Overview of Election Audit:
The purpose of this analysis was to write python code in order to print election results of three counties and
candidates, along with the winner. The reason python was necessary was due to the fact the results were on 
a csv file that has over 300,000 rows, and python makes it efficient to retrieve this data. Not only does 
The code retrieves the data, but also does calculations that add the total vote counts for each county and candidate.

## Election-Audit Results:

- In this congressional election, there were **369,711 total votes cast.** This was found by using the reader function.
  With this function it is possible to read through all the rows of the election results csv. Utilizing the reader function,
  I made an empty variable to hold the total votes and used a loop to add every vote to the variable.
  
  ![csv_reader_row_loop](https://user-images.githubusercontent.com/107213807/176236067-e1423f72-b8c7-482e-ac8b-b00690d3462d.png)

- The votes for each county were **38,855 votes (10.5%) from Jefferson county, 306,055 votes (82.8%) from Denver county,
  and 24,801 votes (6.7%) from Arapahoe county.** This data was by looping through the election results csv. First I had to
  make an empty variable called county_name. Within the loop that goes through all the rows, the line county_name = row[1]
  adds the name of the county to the county name variable. 
  
  ![county_name_extraction](https://user-images.githubusercontent.com/107213807/176236144-70686b39-6834-4aa2-9fff-d9d6e9e6569c.png)

  To get all of the county names and votes, an if statement was used that adds the county name to a list called counties and puts those 
  counties into a dictionary, adding the amount of votes as the values for each county. 
  
  ![counties_list_dict_votes](https://user-images.githubusercontent.com/107213807/176236384-2f9bc72b-9c3f-4d48-8445-b90a98024315.png)

  To get the percentage of votes for each county, 
  I used a formula that divides the amount of votes for each county by the total votes multiplied by 100.
  
  ![county_percentage_formula](https://user-images.githubusercontent.com/107213807/176236398-730a156a-7540-48dd-abc1-32e3cd51d686.png)

- The county with the most votes was **Denver, with 306,055 votes (82.8%)** This was determined by using an if else statement within
  a loop. What the if else statement does is adds the county and votes to variables that holds county with the most votes and the
  amount of votes. First, if the county_count variable is higher than the county_vote variable (This one holds the highest vote).
  The else part is important, as it tells the code to stop when it gets the highest vote count and pulls the name of the county
  that has these votes.
  
  ![if_else_county](https://user-images.githubusercontent.com/107213807/176236472-bfce11c1-c2b3-4ce3-b9e9-8f76d91ffe7a.png)

- The votes for each candidate were **85,213 votes (23.0%) for Charles Casper Stockham, 272,892 votes (73.8%) for Diana DeGette,
  and 11,606 votes (3.1%) for Raymon Anthony Doane.** The candidates were found in a similar way as the counties. Rather than pulling
  from the row that has counties in the loop, I used candidate_name = row[2]. An if statement was then used to add the candidates name to 
  a list of all candidates.
  
  ![candidate_name_extraction](https://user-images.githubusercontent.com/107213807/176236519-2ba6f44a-95bf-48e8-936e-2e1ebb865941.png)

- The winner of the election is **Diana DeGette with 272,892 votes (73.8%)** To find the candidate with the most votes, an if statement
  was used which adds the values of the candidates votes and candidate name to variables containing the correct candidate. The same percentage
  formula was used as earlier, but using the candidate_name variable and votes for each candidate instead.
  
  ![candidate_list_dict_votes](https://user-images.githubusercontent.com/107213807/176236562-3713f611-5b9f-4b9f-93ae-d004b8f3fdb9.png)


## Election-Audit Summary:
With some minor modification, this script could be used for any election. If the format of the csv contains election results follows the same
formatting as the one used for this analysis, the code shows accurately print out results similarly for this election. That being said, some minor tweaks
may be needed for it to work properly. An issue that comes to mind is the if else statement that finds the county with the most votes. Currently
The way the code works is that it gets the name of the winning county by moving back an index in the counties dictionary. The reason this works in this
analysis is that there are only three counties, and the winning county is the second to last index. If more counties were to be added, this part of the code may need to be adjusted. Other than that the code should work for every election. This code is very useful as it makes sorting through hundreds of thousands rows efficiently and printing the results in a way that is easy to read.


