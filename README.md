Judicial Campaign Donations:
Individual and Corporate Lobbying (2012)

Problem Domain & Research Questions:
In the paper The Politics of Judicial Elections, 2017-18, it is stated that 82% of judicial campaign interest group donations were nontransparent. A 2015 John Oliver segment discussed the detrimental role donations play in judicial politics.  The DIME data set, supplied by Harvard Dataverse provides a record of judicial campaign donations from 1980 to 2012. The aim of the following paper is to outline how social network analysis can be applied to this data set, or others similar in nature, to unearth some of the questions posed by existing discussions on the topic. More specifically, can we use community detection, centrality analysis, and exponential random graph models to describe financial activity in judicial election cycles.  

While individual donations can be coordinated by an outside entity, the resolution of donating behavior is categorically different between people and corporations. For that reason, comparing and contrasting the two groups of contributors, individuals and corporations, can provide useful insights. If we believe that individuals donate in a more distributed manner as compared to corporations, we may expect to see differences in the donation networks between the two. Denoting the similarities and differences can help unearth the ontology of corporate judicial election spending. 

If there exists a better understanding with regards to how corporations donate, the level and nature of this influence can be assessed. Existing discussions regarding reform of the judiciary have comprised the question of what to do regarding electing judges for several years. Since many of these discussions acknowledge the distributed nature of election fundraising, network analysis is a strong candidate for analyzing existing data sets in this domain. Visualizing campaign donation information in a network format may help address questions that key decision makers have regarding how to proceed with managing this issue.  

Background Literature:
The implications of judicial campaign donations are being explored in public interest and public policy domains, among others. In 2015, Last Week Tonight with John Oliver released a 13-minute segment raising awareness of the issue in the public consciousness. Several years later, the Brennan Center released a report on judicial campaign financing focused on interest group spending. Both examples are archetypes of the discourse taking place in the domain, and neither portray financial influence in judicial elections positively. The election of judges initially started as a democratic reform measure aimed to give the populace more say. Proponents of the system cite this as a key reason for elections of the judiciary. Investigating similarities and differences between individual and corporate donation patterns in judicial election may elucidate whether the current paradigm achieves greater influence for the populace.

The John Oliver piece has been seen nearly 9 million times since 2015 on YouTube alone. The primary policy issues explored involved negative externalities regarding sentencing during election cycles, judicial campaign donation solicitation, and PAC involvement in the process. The segment states that there is a positive correlation between harsher sentences and election cycles. This should be as in incredibly concerning negative externality of judicial elections as it further undermines the ability for the justice system to approximate fairness. Instances of judicial candidates soliciting both law firms and social groups for donations were cited. The depths of corruption of this nature was not explored as much as its existence confirmed. Finally, PAC involvement was outlined. PACs are typically corporately funded; significant PAC involvement in judicial elections would also undermine the goal of judicial elections bringing more control to the populace. Both donations from law firms and social groups, as well as PAC contributions can be explored with the following network analysis. 

The Brennan Center released a report titled The politics of Judicial Elections 2017-18 that illustrates interest in this topic outside of general public opinion. While the aforementioned issues with judicial elections were explored in this report, most concerningly, the lack of transparency in donations amongst the largest spenders was discussed. The report states that 8 out of the 10 largest spenders did not denote the true source of funds; 82% of all spending was deemed nontransparent. This likely means that the dataset used for the analysis is incomplete of all transactions. If patterns exist in how funding is hidden, this may skew the dataset resulting in irrelevant observations. 

These two examples were chosen because they illustrate how discussions around judicial campaign donations are taking place in multiple spots in our society. The complexity and uncertainty around the topic will likely result in more questions from any new analysis. 

Data Set Description:
All analysis was run on four networks generated from two sets of adjacency matrices and node lists. These lists and matrices were constructed from judicial campaign donation information comprised in the Database on Ideology, Money in Politics, and Elections (DIME), found on the Harvard Dataverse. 

The judicial campaign data set spanned from 1980 to 2012. There were 51 attributes for over 1 million rows. Data was first separated by cycle year using pandas in Python. Names were standardized as all capitals. An edge list was made by concatenating the recipient’s state and party. This concatenation will be referred to as state party. Weights were determined by donation amount. Statistics on the various remaining attributes were run. Most attributes were discarded to decrease file size. Data was further split by contributor type: corporation and individual. 

All transactions below a $1000.00 threshold were removed. All repeating edges had their weights summed. After aggregating the remaining transaction data, the file was saved as an adjacency matrix. Attributes were saved in a node list. These data cleaning and formatting steps resulted in two adjacency matrix files of under 50KB a piece.

For the individual contributor’s adjacency matrix, there were 680 contributors and 27 state parties. The corporation’s adjacency matrix had 498 contributors and 23 state parties. Individual contributors have their node identified by their full name. Corporations are identified by their business name. 

State party is comprised of two recipient attribute values. Four possible values exist for a candidate’s party: 0 (unspecified), 100 (Republican), 200 (Democratic), and 328 (3rd Party). Only 23 states hold judicial elections, and of those that do, not all are partisan, or advertise party affiliation. Non-partisan states will have all candidates listed with a 0 party. Partisan state candidates may still have a 0 party if no affiliation is listed. There are 44 possible state parties, and over half receive donations by both corporations and individuals. 

The greatest amount spent by any one corporate contributor was $240,000. This was followed by 11 additional contributors above $20,000. Somewhat surprisingly the most donated by any single individual to a single state party was $250,100. This included 11 additional contributors who spent more than $20,000 as well. 

 
Network Visualizations:
Corporate Contributors (2012) ↓  
![image](https://user-images.githubusercontent.com/54888442/144695392-ae31afdd-a126-4962-89c2-bd2139b57370.png).    
Largest component in the corporate contributor’s projection. There are six communities detected by the cluster walktrap community detection method.  
![image](https://user-images.githubusercontent.com/54888442/144695330-f96ddfa1-8bf9-4289-8fee-a60a38cf27c9.png).  
2nd largest component in corporate contributors’ projection.  
Two Illinois parties are connected by multiple edges passing through the Threlkeld Investment Fund.   
![image](https://user-images.githubusercontent.com/54888442/144695332-5582e64b-64ee-4c67-a2df-6431a5d910e8.png).  
Largest Corporate Contributor Component    
Alternate Visualization.   
![image](https://user-images.githubusercontent.com/54888442/144695334-f41fbb3f-51d7-40d7-9aea-44715b3f6310.png).  
All Components Corporate Contributors.  
There are 14 components in the projection created by corporate contributors.   

Individual Contributors (2012) ↓.  
![image](https://user-images.githubusercontent.com/54888442/144695356-013cd4bf-4bd8-4508-9c9b-cfa041ffce45.png).  
Largest component in the individual contributor’s projection.  
There are three communities detected by the cluster walktrap community detection method.   
Other components and their communities.  
![image](https://user-images.githubusercontent.com/54888442/144695430-0a5d3c68-411f-44db-8571-259303a708c2.png).  
![image](https://user-images.githubusercontent.com/54888442/144695433-4921b80e-e5e2-4b4e-887c-c6d966ddacc3.png).  
![image](https://user-images.githubusercontent.com/54888442/144695438-57517de3-7eea-4826-b30d-d3c8f862a6c5.png).  
The remaining components produced less cohesive communities for the cluster walktrap method.   
(2nd, 5th, and 6th ).   
![image](https://user-images.githubusercontent.com/54888442/144695446-330487d5-8750-4ed5-9557-e39b6b74361a.png)
Largest Individual Contributor Component    
Alternate Visualization. Communities are connected by a single node.    

![image](https://user-images.githubusercontent.com/54888442/144695452-03e8936b-0edf-48b4-94a8-5a0b5b99025f.png)   
All Components Individual Contributors. 
There are 24 components in the projection created by individual contributors.  
  
 
Important Contributors ↓.  
Important contributors were identified by high eigenvalue centrality.  

[1] NORTH CAROLINA JUDICIAL CAMPAIGN REFORM PUBLIC FINANCING PROGRAM.  
[2] NC.0   
	
[3] TEXANS FOR LAWSUIT REFORM  	 
[4] OHIO REPUBLICAN PARTY	   
[5] VINSON & ELKINS (visualized).  
[6] OHIO DEMOCRATIC PARTY.  
[7] WESTSTAR BANK  	 
[8] TEXAS REPUBLICAN PARTY.  	
[9] BUTLER COUNTY REPUBLICAN PARTY     
[10] ANDREWS & KURTH.  
Corporate Contribution Sub-Graphs.   
 	 
![image](https://user-images.githubusercontent.com/54888442/144695489-346ef6aa-af79-487f-99a6-1933b95b9cc0.png).  
	 
Donations to Pennsylvania Republicans  
The Pennsylvanian Republican candidates have the 12th highest eigenvalue centrality. There are 15 total contributors. 	

![image](https://user-images.githubusercontent.com/54888442/144695499-d9fc9c7d-b69e-40e8-b991-f116e449f6e0.png).  

Donations to Alabama Republicans.  
Alabama Republicans received $220,100 from listed nodes. Democratic nominees received $38,500 that same year.   

![image](https://user-images.githubusercontent.com/54888442/144695505-1dfec016-189f-4f37-8148-621e649c873e.png).  
Donations to Non-Partisan Michiganders.   
There was $220,100 in donations from groups including the Michigan Republican Party and Progressive Women’s Alliance. Candidates do not specify a party. 25% of contributors identify as Republican. 	

![image](https://user-images.githubusercontent.com/54888442/144695515-2aaf8f96-19b1-43dc-ad05-c33ac118d56a.png).   

Vinson & Elkis (5th Most Influential)   
The contributors with the four highest centralities donate to a single state party. Vinson & Elkis donates Democratic, Republican, and independent candidates. Contributions were 3.7%, 87%, and 9.3% respectively.   


State Parties (2012) ↓ 

![image](https://user-images.githubusercontent.com/54888442/144695553-be257591-728b-4b66-bbc3-ffe1b94717e2.png)


Individual Contributors
Most state party nodes are isolated. The adjacent graph was generated by looking solely at individual contributors. This siloed state party effect is evidence that individuals typically have less diversified donation patterns. 

There is a connection between two Texas parties and two Illinois parties. Each is linking a third or unspecified party to a major party. The connection between the unspecified Illinois party to the Louisianian Republican party is likely spurious.

Diversified donation behavior likely reflects a diverse set of interests among individual contributors. 
 	
	
![image](https://user-images.githubusercontent.com/54888442/144695565-339b8c7b-29e1-4ad7-9907-85457779ff34.png)


Diversified donation behavior likely reflects a diverse set of interests among individual contributors. 
Corporate Contributors
There are many more connections between the state parties to which corporations donated. 

However, increased transitivity and density are the only factors relevant. While homophily and propinquity, represented by party affiliation and state respectively, do not predict edge presence. The AIC for a random model and one applying node and dyadic covariates is not lower. Furthermore, these covariates are not statistically significant predictors in and of themselves. 

While it does appear that there may exist some pattern related to party homophily and propinquity, more data is needed to determine if this is an accurate assessment.

 
Social Network Analysis:
The following social network analysis practices will be discussed in their application to the corporate and individual judicial donation data sets: five number summary, centrality analysis, community detection, and ERGM modeling.  

1.	Five Number Network Summaries:
The following terms give insight as to how large, dense, disconnected, and compact the following networks are. These terms are outlined in A User’s Guide to Network Analysis in R. 

![Screen Shot 2021-12-03 at 10 38 08 PM](https://user-images.githubusercontent.com/54888442/144695582-13193330-753f-4ab2-8162-05c60dd8a5c6.png)

Six networks are outlined below. Individual and corporate bipartite, and contributor projection, and state party projection networks are described. 

![Screen Shot 2021-12-03 at 10 38 41 PM](https://user-images.githubusercontent.com/54888442/144695597-2d08ba7a-d3d3-4a31-bee2-0131d099c030.png)

Higher density and fewer components can be observed within the corporate donation network. This reflects a higher average outdegree for contributor node types in the corporate bipartite network. 

2.	Centrality Analysis
Only corporations with high centrality will be listed for privacy reasons. What is observed is that for both renditions of the network, republican party contributors constitute 30% of the ten most central nodes. Democratic contributors are at 10%.

Eigenvalue Bipartite Corporation

[1] NORTH CAROLINA JUDICIAL CAMPAIGN REFORM PUBLIC FINANCING PROGRAM
	                                                    [2] NC.0 
	
[3] TEXANS FOR LAWSUIT REFORM  	
[4] OHIO REPUBLICAN PARTY	
[5] VINSON & ELKINS 

[6] OHIO DEMOCRATIC PARTY
	
[7] WESTSTAR BANK  	
[8] TEXAS REPUBLICAN PARTY	
[9] BUTLER COUNTY REPUBLICAN PARTY   
	
[10] ANDREWS & KURTH
Eigenvalue Projected Contributor Corporation

[1] NC.0
	                                                    [2] NORTH CAROLINA JUDICIAL CAMPAIGN REFORM PUBLIC FINANCING PROGRAM	
[3] TEXANS FOR LAWSUIT REFORM  	
[4] PENNSYLVANIA REPUBLICAN PARTY	
[5] OHIO REPUBLICAN PARTY

[6] VINSON & ELKINS 	
[7] SOUTHEAST WOOD TREATING	
[8] OHIO DEMOCRATIC PARTY	
[9] JACKSON PAC
	
[10] MICHIGAN REPUBLICAN PARTY

The centrality of the corporate and individual contributor projections is greatly different from one another. This is especially true for the largest component in each. The largest component can serve as a hypothesis of what subnetworks will look like when edges are removed. Centrality attributes may be exaggerated as a result. 

Corporations	Network Wide	Largest Component
Degree Centrality	0.173	0.307
Betweenness Centrality	0.155	0.446
Closeness Centrality	0.001567352	0.3743186
Eigenvalue Centrality	0.9805269	0.593444


Individuals	Network Wide	Largest Component
Degree Centrality	0.142	0
Betweenness Centrality	0.0219	0
Closeness Centrality	0.000248	0
Eigenvalue Centrality	0.9870198	1.869849e-16

The individual contributors have lower centrality as a whole than corporations do. This is further exaggerated when the largest component is observed in isolation. The centralities of the corporation’s largest component increase; the individual’s component decreases. This could suggest that the donating patterns of corporations have more structure than those of individuals. 
 
3.	Community Detection
Communities were detected by observing the largest component in each the corporate and individual’s contributor networks. Once a successful algorithm was determined, all subsequent components for said network were processed with that algorithm to generate additional community separated visualizations.

Corporate Communities. 
Algorithm	Communities	Modularity
Walktrap	6	0.50371
Edge-Betweenness	6	0.50371
Leading Eigenvector	5	0.50306
FastGreedy	2	-4.250073e-17
Spinglass	7	0.50001

Individual Communities.
Algorithm	Communities	Modularity
Walktrap	3	0.6038
Edge-Betweenness	3	0.6383
Leading Eigenvector	3	0.6049
Fast-Greedy	3	4.250073e-17
Spinglass	1	0

Modularity and the number of communities was relatively stable across all community detection methods. This lends further credence to the claim that these communities could be observed naturally. Using modeling techniques can help to discover what these characteristics may be.

4.	ERGM Modeling
Three ERGM models were ran against the corporate state party network. Individual state parties were excluded because of the low density in the network. Contributors were excluded because of issues around incomplete data.

Corporate State Parties.	Null	Homophily	Homophily & Propinquity
AIC	86.22	86.20	350.7
Significant Vars.	1	1	1
Improvement?	-	No	No

This analysis allows us to say while homophily and propinquity seem to be relevant in the observed edges between state parties in 2012, it is not statistically significant to say so. In addition, the ERGMs do not perform better with the addition of attribute related variables. 

In order to substantiate claims that corporations donate in ways guided by propinquity or homophily, more data is needed. Observing the state attribute of contributors would be a way to do this as well, although only for propinquity. 



Other Relevant Methodologies:
There are two primary ways that the analysis can be improved with greater time investment. The first deeper analysis with the four listed techniques. The second is by implementing multiple election cycles to observe, describe, and model network evolution. 

Expanding existing analysis:
The two areas that would likely yield the most interesting finds would involve further centrality analysis and more modeling. 

Observing the centrality in all 24 and 14 components for the individual and corporate donation networks respectively might create an interesting vector for gleaning insights on donation behavior. In addition, finding the most central node in each community within the most important components might be of interest. While all campaign contributions in the data set are only recorded if they exceed $1000.00, the range of donated values is wide. Centrality analysis helps identify key actors beyond an affiliated donation value. 

Ideally the data would be sufficiently cleaned and formatted such that more node attributes could be ascribed to contributor nodes. Individual state parties had too few edges to bother modeling; Corporate state party homophily and propinquity proved insignificant. Contributor node attribute information, particularly party affiliation (if available elsewhere), would allow for the same modeling techniques to be run on these networks.   

SIENA: 
Applying Siena to this data set is possible, if the remaining data set is used as well. While this is certainly possible, there are constraints that make this difficult. 

First, the full data set in csv format is large enough that numerous applications, including Microsoft Excel, cannot open the file. There are workarounds to this issue, but the size of the file does make processing the contents with R very slow without steps taken prior.  

Second, while state parties are likely to remain the same across the cycle years, there is no guarantee that contributors will exist in any more than one election. Prior to any analysis with Siena, viability must be determined. If contributor nodes do not exist from one year to the next, some other value must be substituted. Choosing a given derived value for contributor nodes to bolster continuity in the network may be difficult. 

Applying Siena to this data set would be incredibly interesting but would also involve a lot of addition dedication within the data cleaning and analysis domains. 

Discussion of Results:
The most salient finding of the network analysis is that more research needs to be done. Uncertainty, such as the type explored in the background literature, necessitates understanding more about the frame in which judicial elections reside. There are two primary questions that need clarifying: what are the rule differences between individual and corporate contributors, and what other resources exist for this transaction information. The first question is motivated by the fact that the largest corporate and individual contributors spent the same amount. Could there be corporate donations funneled through individuals? The second question aims to adjust for any potential data set skew caused by 82% nontransparent donations.

Based on the five-number summary, centrality analysis, community detection, and ERGM modeling, the statement that individuals and corporations donate differently can be justified. More specifically, we can say that the corporate donating network is more homogeneous. The fact that difference between corporations and individuals can be described solely by their donating patterns can motivate discussions regarding misalignment between corporate and individual political interests. Given judicial elections are aimed to benefit individuals, action can be taken to better achieve this end. 

All corporate networks had higher density and transitivity, and fewer components. These three metrics indicate greater connectivity between the nodes in the corporation donation network. This says nothing about how much was donated (although all contributions exceeded $1000.00), but rather that corporations are donating to the same state parties. When the graphs for both individual and corporate networks are observed, dense pockets of interconnected nodes are seen for individuals. Conversely, the entire corporate network is mostly connected. Greater interconnectivity in the corporate donation structure resulted in larger components which in turn had more communities. The communities in the components for individuals and corporate contributors are quite different. Corporations tend to have more uniform, highly defined, interconnected, small-world-esque communities within their components. Individuals had far lower modularity in their community detection scores beyond the first component. The global and community structural differences between individuals and corporations lends credence to the notion that donation patterns are substantively different. This can help direct reform efforts.

Centrality analysis can help illustrate who the most influential donators in any given campaign cycle are. Unfortunately, as the Brennan report stated, 8 out of the 10 top contributors had obfuscated donation histories. How and if these nontransparent donations appear on the Harvard Dataverse DIME data set is unclear. Assuming the data set is representative, three PACs (one specifically discussed by John Oliver), three explicitly Republican organizations, and one explicitly Democratic organization can be observed in the top 10 most central corporate contributors. Individual’s names will not be listed. While this may be concerning, we also observe greater overall centralization in the corporate donation network. This is exaggerated within each component in the corporate graph. The little centralization the individual network has in its entirety goes to zero within its components. These differences further motivate believe corporations and individuals donate differently. Centrality analysis also helps know who these corporations are. 

ERGM modeling proved the be the least fruitful analysis. No statistically significant relationship was found ideological homophily or propinquity for state party in the corporate donation network. More corporate donation data is likely to be required in order to be able to answer this question. Individual’s state party projection had nearly no edges between nodes.

There is reasonable evidence from a network analysis standpoint to say there is difference between how individuals and corporations donate. Given that judicial elections are meant to benefit the people, then ideally, we would like to see this reflected in donation structure, guidelines, or legislation. There are two main issues as it stands: corporate donations are more targeted and both individuals and corporations donate somewhat similar amounts. The result is that corporate donations have more cumulative influence on judicial elections. How can judicial campaign finance be reformed such that the individual is prioritized given existing network donation structure?
 
References:
2014. Database on Ideology, Money in Politics, and Elections (DIME). [CSV] Harvard Dataverse, Database on Ideology, Money in Politics, and Elections (DIME).

Keith, D., Berry, P. and Valesco, E., 2019. The Politics of Judicial Elections, 2017–18. Brennan Center, [online] pp.1-27. 

Luke, D., 2015. A user's guide to network analysis with R.

Elected Judges: Last Week Tonight with John Oliver. 2015. [video] Directed by J. Oliver. HBO: HBO.

![image](https://user-images.githubusercontent.com/54888442/144695317-e325f974-7ffd-4d62-8d31-4c48dcb3c758.png)
