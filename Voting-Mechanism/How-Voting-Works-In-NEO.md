- ## How Voting Works In the NEO Network

  ##### How Many Votes Do You Have

  Any node that holds NEO can vote for an unlimited number of candidates. The number of votes corresponds to the number of NEO held in the account. If NEO balance changes during the voting cycle, the candidate's votes will simultaneously be updated to reflect the change in balance.  

  For Example, if there are 100 NEO in an account, and the account voted for 3 candidates, each candidate receives 100 votes. If NEO in the account is spent after the vote, the candidates' votes will simultaneously be decreased to the current NEO balance.

  ##### How Are Consensus Nodes Selected

  Once the votes are cast, the NEO network calculates the consensus nodes in real time, with the following methods: 

  - First, candidate nodes are sorted by the number of votes they receive. 

  - Then network calculates *N*, which is how many top candidates in the sorted list are to be selected as consensus nodes: 

    1. Sort the number of candidates each account voted for by size. e.g. C1, C2, ..., Cn

       > *Note: Since each account can vote for an unlimited number of candidates, the number of candidates each account voted for (Cn) is almost certainly different from each other.*

    2. Remove the first 25% and the last 25% of the array. 

    3. Calculate the *weighted average*\* of the remaining 50% data, which is then determined as the number of consensus nodes to be selected, N. 

       > *\*: weighted average depends on the NEO held in each account. This means that accounts that hold more NEO contribute proportionally more to the average when calculating the number of consensus nodes to be selected.* 

  - Once N is determined, the top N candidates with the highest number of votes become the consensus nodes. 

  ​
