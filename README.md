# Election_Analysis
## Project Overview
Analysis for an election audit of the Colorado Board of Elections to determine the following tasks to complete the election audit of a recent local congressional election.

1. Calculate the total number of votes cast.
2. Get a complete list of candidates in the election.
3. Calculate the total number of votes received for each candidate. 
4. Calculate the percentage of votes won per candidates.
5. Determine the winner of the election.
6. Calculate the voter turnout for each county.
7. Calculate the percentage of votes from each county out of the total count.
8. Determine the county with the highest turnout.

## Resources
- Data Source: election_results.csv
- Software: Python 3.7.6, Visual Studio Code 1.66.2

## Election Audit Results
![Election Analysis](https://github.com/meliscelikay/Election_Analysis/blob/7c098700dc712796149a42219762cd38ce8a9868/Resources/election_analysis.png)

The analysis of the election indicates that:

- There were 369,711 votes cast in the election.

- The voter turnout for each county was:
    - Jefferson received 10.5% of voters, for a total of 38,855 voters.
    - Denver received 82.8% of voters, for a total of 306,055 voters.
    - Arapahoe received 6.7% of voters, for a total of 24,801 voters.

- The county with the largest voter turnout was:
    - Denver, which received 82.8% of voters, for a total of 306,055 voters.
    
- The detailed candidate results:
    - Charles Casper Stockham received 23.0% of the vote, for a total of  85,213 votes.
    - Diana DeGette received 73.8% of the vote, for a total of 272,892 votes.
    - Raymon Anthony Doane received 3.1% of the vote, for a total of 11,606 votes.

- The winner of the election:
    - Diana DeGette, who received 73.8% of the vote for a total of 272,892 votes.

### Looping through dictionaries and the lists to achieve the total number count.
    with open(file_to_load) as election_data:
    file_reader = csv.reader(election_data)   
    # Read and print the header row.
    headers = next(file_reader)
    # Print each row in the CSV file.
    for row in file_reader:
        # Add to the total vote count.
        total_votes += 1
        # Print the candidate name from each row
        candidate_name = row[2]

        # 3: Extract the county name from each row.
        county_name = row[1]

        # If the candidate does not match any existing candidate it to
        # the candidate list
        if candidate_name not in candidate_options:
            # Add the candidate name to the candidate list.
            candidate_options.append(candidate_name)          
            # And begin tracking that candidate's vote count.
            candidate_votes[candidate_name] = 0
        # Add a vote to that candidate's count.
        candidate_votes[candidate_name] += 1

        # 4a: Write an if statement that checks that the
        # county does not match any existing county in the county list.
        if county_name not in county_options:

## Election-Audit Summary
I found the code used to analyze election results to be sufficient and user friendly. The script is easy to adjust can be scaled up or down depending on data set. I would think this script can be used to analyze local or country wide elections, if needed, with slight modifications in code. It is also convenient enough to adjust for different candidates, states, cities, and counties with few adjustments. This script could also be used to show more in-depth details such as percentage of voters for specific candidates to gauge his/her popularity. We can also use voter turnout data and quantify it, it may help election boards spread out their resources more accurately and properly to handle the volume of voters on election days.
