# How To Become A Consensus Node
*[中文版](如何成为共识节点.md)*

#### Table Of Contents
  * [Current Consensus Nodes](#current-consensus-nodes)
  * [1. Application](#1-application)
    + [1.1 Application Criteria](#11-application-criteria)
    + [1.2 Application Methods](#12-application-methods)
  * [2. Test-net Consensus Node](#2-test-net-consensus-node)
    + [2.1 Becoming a Candidate](#21-becoming-a-candidate)
    + [2.2 Maintaining the Consensus Node](#22-maintaining-the-consensus-node)
  * [3. Main-net Consensus Node](#3-main-net-consensus-node)
    + [3.1 Becoming A Candidate](#31-becoming-a-candidate)
    + [3.2 Voting](#32-voting)
      - [3.2.0 The Voting Mechanism\*](#320-the-voting-mechanism--)
      - [3.2.1 Voting NEO GUI](#321-voting-neo-gui)
      - [3.3 Gather Votes & Support](#33-gather-votes---support)
  * [Appendix 1. Checking Candidates and Votes using API](#appendix-1-checking-candidates-and-votes-using-api)
  * [Appendix 2. Add Candidate Info to Consensus Node Page](#appendix-2-add-candidate-info-to-consensus-node-page)

## Current Consensus Nodes

3 of them are being maintained by NEO Foundation, 1 by Neo Global Development, 3 by CityOfZion.

The NEO main-net currently has 7 consensus nodes. 

- NEO Foundation maintains 6 of the nodes. 
- CityOfZion maintains 1. 

The NEO test-net currently has 7 consensus nodes. 

- NEO Foundation maintians 3 of the nodes
- NEO Global Development maintains 1. 
- CityOfZion maintains 3. 

## 1. Application

> Please Note: the application process is not a mechanism of the NEO blockchain. Any node can spend gas to become a candidate node[(See 3. Main-net Consensus Node)](#3-main-net-consensus-node) without the application, and be voted by any NEO holders of the community. Those who do successfully apply will also receive votes from the NEO Foundation. 

### 1.1 Application Criteria

*Anyone who applies for becoming a consensus node candidate is advised to provide some, or all of the information listed below.*

- Applicant/Organization Information

  - A public website and social media account
  - Organization name and location
  - A list of at least 2/3 of the team with pictures and relevant background qualifications on each
  - Telegram account or other ways of contact

- Server type and specifications

- The applicant's solutions to

  - Safety & security of the node
  - Maintenance
  - Long term stability
  - Failure tolerance/recovery backup
  - Maintenance personnel
  - Budget

- Plans for potential hardware scaling/upgrading

- NEO Community participation/contribution *(if applicable)*

- Test-net consensus node name *(if applicable)*

**Recommended Minimum Hardware Specifications:**

- 4 Core CPU
- 8 GB RAM
- 10M Bandwidth
- 100G Hard Drive

### 1.2 Application Methods

#### E-mail Application

An application containing information listed in [1.1](#11-application-criteria) can be emailed to: 

foundation@neo.org

#### Website Application

> *The 'Apply to be Consensus Node Candidate' feature will be available on the [neo.org](neo.org) website soon.*

## 2. Test-net Consensus Node

If the application is successful, the applicant will start by running a consensus node on the Test-net. 
To become a consensus node on Test-net, they need to first become a candidate. 

### 2.1 Becoming a Candidate

> *The GUI operations of becoming a candidate and voting (Sections 4 and 5) are the same on both Test-net and Main-net. The difference is determined by which chain the GUI is synced to. To switch between test-net and main-net on GUI, see [this document](http://docs.neo.org/en-us/network/testnet.html).* 

Once the application is successful, you can use the NEO GUI to register as a candidate. Candidates will be voted by NEO token holders to determine how many nodes and which nodes will become the consensus node. 

1. In NEO-GUI, open a wallet. 

2. Select `Advanced` -> `Election` 

3. Select the public key of the account in the list and click `OK`. Note that 1000 GAS will be charged at this step.

   <img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/candidate-EN.png" width="725">

4. If the message of a transaction ID is displayed, then the transaction is constructed successfully. You can check if the candidate has been successfully registered by accessing the API. (See [Appendix 1](#appendix-1-checking-candidates-and-votes-using-api))

### 2.2 Maintaining the Consensus Node

Once the node has become a candidate, NEO Foundation will vote for the node so that it becomes a consensus node on test-net. 
If problem arises with the consensus node during this period, active communication and troubleshooting is expected. NGD will provide technical support if these situations arise. 
After 6 months of running the test-net, the applicant will be qualified to become a candidate for a consensus node on the main-net. 

## 3. Main-net Consensus Node

### 3.1 Becoming A Candidate

Use a GUI to connect to the main-net. Repeat steps in [2.1](#21-becoming-a-candidate)

### 3.2 Voting

#### 3.2.0 The Voting Mechanism\*

*\*: NEO3.0 will make adjustments to the voting mechanism. This section will be updated accordingly when 3.0 launches.*

Each NEO node can vote for the candidates. The number of NEO in the current voting account will be automatically calculated as the number of the candidate's votes. When voting for multiple candidates, each candidate gets the votes equal to the NEO number of the current voting account. For example, if there are 100 NEO in the current account and three candidates are voted for from this account, each candidate receives 100 votes. If NEO in the account is spent after the vote, the candidates' votes will simultaneously be decreased to the current NEO balance.

After voting, the NEO network calculates in real time based on the number of candidates cast by each account and determines the consensus nodes. The calculation method is:

1. Sort the number of the candidates each account voted for by size, e.g. C1, C2, ..., Cn
2. Remove the first 25% and the last 25% of the data in the array
3. Calculate the weighted average of the remaining 50% data, which is then determined as the current NEO consensus node number N
4. The top N candidates with the highest number of votes become consensus nodes

#### 3.2.1 Voting NEO GUI

Any nodes holding NEO can vote using the GUI. Candidates can vote for their own nodes. 

1. In NEO-GUI, open the wallet account to vote. 

2. Right-click on the account -> `Vote`.

3. In the Candidates field, enter the public key of the candidate to vote. You can enter multiple public keys separated by Line feeds. Note that each line cannot contain spaces, as shown in the following figure:

   <img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/votemulti-EN.png" width="725">
   *Example: giving three candidates each 100000000 votes.*

4. If the message of a transaction ID is displayed, then you have voted successfully. Youc an check the number of votes for each candidate by accessing the API. (See [Appendix 1](#appendix-1-checking-candidates-and-votes-using-api))

#### 3.3 Gather Votes & Support

NEO Foundation will vote for candidates who have completed sections [1](#1-application) and [2](#2test-net-consensus-node). All candidates are also able to gather votes from other NEO holders. 

Candidate information can be added to the [Consensus Nodes](http://neo.org/consensus) page on the NEO website. This can help voters know about the candidates and help candidates acquire potential votes. [See Appendix 2 for how to do it.](#appendix-2-add-candidate-info-to-consensus-node-page)

---


## Appendix 1. Checking Candidates and Votes using API

To check the number of votes on each candidate that has registered, you can use Postman or any other RPC program to access the API. (For instructions on how to, see [this document](Using RPC to Call NEO API.md))

As shown below, send a `getvalidators` request to the API. 

<img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/getvalidator2.png" width="725">

The node returns a json file containing public keys of candidates and the votes each one received. 

In the picture, the candidate with the public key `3076fc0ee6c6ccf3fb0c9b3ff9d0e3d9ba7ef97e54c77240991ec1dffa295503b` was given 100000000 votes. 

### Consensus Node Status

The **`active`** field in the returning json file indicates the status of the node. 

`false` means the node is a candidate node. 

`true` means the node is a consensus node. 

## Appendix 2. Add Candidate Info to Consensus Node Page

The [Consensus Nodes](neo.org/consensus) page can be used to track the status and number of votes for each candidate on the main-net. Clicking on the green arrow can expand and show more information for each node. 

<img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/consensusSited1-EN.png" width="755">

**To Add Candidate Info: **

1. Select <img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/consensusSited2-EN.png" width="220">, which opens the Candidate Info tab. 

2. Select the public key of your consensus node from the drop-down menu. Enter information about the candidate. 

3. Once the information is complete, select `Generate Hash`. Which will generate a hash string. 

   <img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/consensusSited3-EN.png" width="620">

4. Open NEO GUI, select `Advanced` -> `Sign Message...` (*Available only to 3.0 or above*)

   <img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/consensusSite4-EN.png" width="725">

5. Select the address of your candidate in `Address`, paste the hash string into the `Input` field and select `Sign`. 
   Copy the output signature. 

   <img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/consensusSite5-EN.png" width="725">

6. Return to the Candidate Info tab on the browser, paste the signature and select `Submit`. 

   <img src="https://raw.githubusercontent.com/taomo-eo/docs/master/Becoming_Consensus_Node/img/consensusSite6-EN.png" width="620">

   If the green arrow to the right of your node on the page is green and expandable,  then your candidate info is successfully submitted! 
