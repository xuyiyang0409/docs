## How Voting Works In the NEO Network

As NEO plans to [accelerate its decentralization](https://neo.org/blog/details/4125) in 2019 and beyond, there will be a few voting cycles on the NEO network that anyone who holds NEO can participate. This write-up compiles the relevant information that a NEO holder should know if they want to participate in voting. 

### How Many Votes Do You Have

Any node that holds NEO can vote for an unlimited number of candidates. The number of votes corresponds to the number of NEO held in the account. If NEO balance changes during the voting cycle, the candidate's votes will simultaneously be updated to reflect the change in balance.  

For Example, if there are 100 NEO in an account, and the account voted for 3 candidates, each candidate receives 100 votes. If NEO in the account is spent after the vote, the candidates' votes will simultaneously be decreased to the current NEO balance.

### How Are Consensus Nodes Selected

Once the votes are cast, the NEO network calculates the consensus nodes in real time, with the following methods: 

  - First, candidate nodes are sorted by the number of votes they receive. 

  - Then the network calculates *N*, which is how many top candidates in the sorted list are to be selected as consensus nodes: 

    1. Sort the number of candidates each account voted for by size. e.g. C1, C2, ..., Cn

       > *Note: Since each account can vote for an unlimited number of candidates, the number of candidates each account voted for (Cn) is almost certainly different from each other.*

    2. Remove the first 25% and the last 25% of the array. 

    3. Calculate the *weighted average*\* of the remaining 50% data, which is then determined as the number of consensus nodes to be selected, N. 

       > *\*: weighted average depends on the NEO held in each account. This means that accounts that hold more NEO contribute proportionally more to the average when calculating the number of consensus nodes to be selected.* 

  - Once N is determined, the top N candidates with the highest number of votes become the consensus nodes. 


**TL;DR**: The NEO network determines how many Consensus Nodes to select by calculating a weighted average of the middle 50% of the number of candidates that each account voted for. 

### How to Cast Your Vote

Before voting, you will need to know what candidates there are and the information on each candidate; all of which can be found on he NEO [Consensus Node page](https://neo.org/consensus). The page displays all candidate nodes that are registered on the NEO blockchain, and candidates themselves can modify the information of their corresponding node. 

Once you have found the candidate(s) that you wish to vote for, note down their *Public Key* as this will be needed during voting. 

Currently, the only way to vote is through the [NEO-GUI](http://docs.neo.org/en-us/node/gui/install.html). 

> *For first time users, as synchronizing the blockchain would take quite a long time, it is advised that you use the [offline synchronization package](http://docs.neo.org/en-us/network/syncblocks.html). You can export your WIF/private key from your current NEO wallet and follow [this guide](https://github.com/neo-project/neo/wiki/Guide:-How-to-Import-Private-Key-to-NEO-GUI#import-your-wallet-to-the-pc-client) to import your wallet to the GUI.* 

1. In NEO-GUI, open the wallet account to vote. 

2. Right-click on the account -> `Vote`.

3. In the Candidates field, enter the *Public Key*(found on the consensus node page) of the candidate to vote. You can enter multiple public keys separated by Line feeds. Note that each line cannot contain spaces, as shown in the following figure:

   <img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/votemulti-EN.png" width="725">
   *Example: giving three candidates each 100000000 votes.*

4. If the message of a transaction ID is displayed, then you have voted successfully. Again, you can check the number of votes for each candidate on the [consensus node page](https://neo.org/consensus). 