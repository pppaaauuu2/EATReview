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


### OBJECTIVES


### SECUNDARY OBJECTIVES 
