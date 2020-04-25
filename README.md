# EATReview


##### Pau Pericàs
###### errorandtrial.com


### INTRODUCTION

The idea consist in creating a software platform to sort the result of a PubMed query according to a review strategy that could consist in different automatic or manual steps performed by multiple reviewers.
I've found a similar project based on a web platform. But as far as I know, it only classifies pubmed references in a single step. I liked its reviewing interface. Is similar to what I imagined. But I would like to have the classification tree in a side and put the paper in the end of the tree that corresponds to the current step.
You would be able to see how many papers are in every branch, how many are left to review and other statistics on ow the review is been performed. 
I would like to perform the distribution of work between the different reviewers in a distributed system, rather than in a server-client one. Among the reviewers, one of them could have higher authorization to organize and review the work of the reviewing team. 
From PubMed you can download the result o the query in a xml with all the indexed data, or as a PMID list, with wich the program can retrieve the rest of the information. 
For every paper reviewed the applications should show all the indexed information and if possible, the link to the full text. In the application database we only need to store the refference to the paper and the result of the classification. Probably its interesting to store who and when performed te review. 
The project should define the desition tree so the classification data stored with the paper reference makes sense. If the tree is properly defined, the classification result could be a bit array with te classification result at every step. 
For automated steps, there should be a way to filter the information indexed in the pubmed result. As an example, you should be able to filter the results by date, article type, references, journal... This filters can be defined in the PubMed query, but this way they would be represented in the report of the project.
At any point of the review process an automatic report should be available explaining all the process. 

When defining a manual step, it should be possible to add fields to those already in the PubMed index or in the application database with the data relevant to that step. As an example, if the papers must be classified depending on the n of the sample or on the age of the population studied. 

These extra fields could be used too to report on the selected papers after the review, so it could be the final result of the review and not only the result of the classification process. 

To validate the reviewing process, a certain number of papers should be reviewed by multiple reviewers, and then the team manager should decide if he review process is robust.

It should be possible to control each reviewer contribution to the process. When there are reviewers different contribuition and pace, there must be a defined policy to distribute the workload to avoid unwanted redundant work or subsets of data never analized. 
In a server-client architecture this would be a simple problem to resolve, but as what I'm trying to implement will consist in multiple computers using this program at different times and locations it may not be as simple. To be able to keep track of the global progress with these requirements there should be some sort of asynchronous comunications between the reviewers.
One way I see it could be solved is defining a sammple set size. The papers to review would be divided in n samples of that size asigned to each reviewer. Some of them may be redundant for the validation process. When a reviewer end a set, a signal may be sent to the other letting them know the result of the review and the next set in revision by that reviewer, so no other reviewer would review it too. 

### OBJECTIVES

#### Import de PubMed query result
##### Get all indexed data
#### Define the classification steps
##### Add columns to the model
##### Add reviewers to the process
###### Define each reviewer contribution
#### Distribute the work
##### Create redundant sample
#### Perform the manual steps
#### Generate report & subsets data
##### Export results

### SECUNDARY OBJECTIVES 
