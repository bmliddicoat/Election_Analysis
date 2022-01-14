# Election_Analysis

## Overview of Election Audit

The clients, Seth and Tom, originally asked for the election audit of which would focus on the candidates and the results.  To achieve this, Python was used to analyze data from an excel document.  The areas of focus were the total number of votes, list of candidates who received votes, total number of votes each candidate received, percentage of votes won by each candidate and the winner of the election.  After submitting the report, the election commission requested additional data to complete the election audit. The election committee wants a report on voter turnout for each county, percentage of votes for each county out of total count and which county had the highest turnout.  Python will be used to discover the election committee's request.

## Election-Audit Results

! [alt txt] ()

* Total votes cast were 368,711. 
    * Code used: 
        * total votes = 0 which initialized a total vote counter
        * total_votes = total_votes + 1 which added to total vote count
        
* County Totals
    * Arapahoe: 6.7% of votes (24,801 votes)
    * Denver: 82.8% of votes (306,055 votes)
    * Jefferson: 10.5% of votes (38,855 votes)
    * Code used:
        * For loop to get the county from the county dictionary. 
        for county_name in county_options: 
        * Retrieve the county vote count.
        county_vote_count = county_votes[county_name]
        * Calculate the percentage of votes for the county.
        county_vote_percentage = float(county_vote_count) / float(total_votes) * 100
        * Compile data to on counties 
        county_results = (
        f"{county_name}: {county_vote_percentage:.1f}% ({county_vote_count:,})\n")
         

* Denver had largest number of votes at 306,055.  This amount of votes counted for 82.8% of total vote for the election.  
    * Code used:
        * An if statement to determine the winning county and get its vote count and percentage.
        if (county_vote_count>largest_county_vote) and (county_vote_percentage>largest_county_percentage):
            largest_county = county_name
            largest_county_vote = county_vote_count
            largest_vote_percentage = county_vote_percentage

* Canidate Totals
    * Charles Casper Stockham received 23.0% of total votes.  They had total of 85,213 votes cast.
    * Diana DeGette received 73.8% of the total votes.  They had a total of 272,892 votes cast.
    * Raymon Anthony Doane received 3.1% of the total votes.  They had a total of 11,606 votes cast.
    * Code used:
        * Save the final candidate vote count to the text file.
        for candidate_name in candidate_votes:
        * Retrieve vote count and percentage
        votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        * Complie data on canidates 
        candidate_results = (
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")

* Winner of Election was Diana DeGette.  Diana DeGette had a total of 272,892 votes out of 368,711 total votes cast.  This amount votes for Diana DeGette was 73.8% of total votes.  
    * Code Used:
        * Determine winning vote count, winning percentage, and candidate.
        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage

## Election-Audit Summary

Through this audit using Python, I was able to "read" an excel/csv.file to perform an analysis of your election.  It was determined that a total of 368,711 votes were casted for this election.  The highest turnout in the three counties was Denver.  Denver had number of votes at 306,055.  This number of votes counted for 82.8% of total vote for the election. Winner of election was Diana DeGette.  Diana DeGette had a total of 272,892 votes out of 368,711 total votes cast.  This amount votes for Diana DeGette were 73.8% of total votes. 

There are possibilities to expand the use of Python on future elections or past.  One example is to determine the actual turnout of voters compared to registered voters.  We would need the data on total population for eligible voters.  I would then use total votes cast divided by the eligible voter population.  This data could be vital.  It could help analyze participation within the community.  After this analyzation, data collection could be implemented on voters.  This data could help led to investigation if there are social determinants/disparities which could be causing areas of population to not vote.  Outliers within a group such as the elderly in rural communities could need assistance getting to polling places, education on mail-in ballots or polling place location added.  

The second possibility is use Python to audit ballot measures.  In replacing the candidates with yes or no for ballot measure in the formula, the results could be audited as the same as this audit.  It could be possible to use Boolean value of yes or no.  Boolean is a data type that represents one of two values.  An example is True or False.  I could create a code which analyzes all ballot measures.  I would continue the code for each measure.  Although, I would need to create a vote count as I did for total vote for each ballot measure.  This would be due to possibility that voters may have abstained on a measure.        

