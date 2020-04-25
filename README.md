# EATReview


##### Pau Pericàs
###### www.errorandtrial.com
###### errorandtrialweb@gmail.com

### INTRODUCTION

The idea consist in creating a software platform to sort the result of a PubMed query according to a review strategy that could consist in different automatic or manual steps performed by multiple reviewers.



I've found a similar project based on a web platform. But as far as I know, it only classifies pubmed references in a single step. I liked its reviewing interface. Is similar to what I imagined. But I would like to have the classification tree in a side and put the paper in the end of the tree that corresponds to the current step.

###### http://abstrackr.cebm.brown.edu/

###### If you use abstrackr for your project and subsequently publish, please consider citing us using the following citation:

###### Byron C. Wallace, Kevin Small, Carla E. Brodley, Joseph Lau and Thomas A. Trikalinos. Deploying an interactive machine learning system in an evidence-based practice center: abstrackr. In Proc. of the ACM International Health Informatics Symposium (IHI), p.819--824. 2012.

###### Questions, kudos and gripes should be sent to Byron Wallace (byron.wallace@gmail.com).

Users would be able to see how many papers are in every branch, how many are left to review and other statistics on ow the review is been performed. 

I would like to perform the distribution of work between the different reviewers in a distributed system, rather than in a server-client one. Among the reviewers, one of them could have higher authorization to organize and review the work of the reviewing team. 

From PubMed you can download the result of the query in a xml with all the indexed data, or as a PMID list, that the program can use to retrieve the rest of the information. 

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

To retrieve all the information from pubmed when te project is created and when a new computer joins te project, an Internet connection would be needed. During the rest of the review project, the transmission of the results would only require punctual asynchronous communications. 

This exchange could be done using email. This way, when defining a reviewer an email address would be associated. When the project is launched, an email could be sent to every reviewer with the data to set their computer with all the papers informations and with their share of the workload assigned. 
At that point, the reviewer could retrieve all the information in pubmed. 

Every time a certain amount of work is done or when the user choses to do that, a message is sent to the rest of the reviewers with an update on the work done so everyone can integrate that information with their local data.

### OBJECTIVES

#### Import de PubMed query result
##### -Get all indexed data
##### -Save all indexed data
As the data will be a colection of papers with a fixed set of attributes and some other attributes that may be added later, and with 
no need of big calculations accross the collection, Im thining in mongodb as a database manager.
The conversion from JSON to java object is easy and the implementation  of a data model would be completely under the program control.
#### Define the project
##### -Create the classification steps
##### -Add columns to the model
##### -Add reviewers to the process
###### --Define each reviewer contribution
#### Distribute the work
##### -Execute automated classification steps
##### -Divide remaining work 
##### -Create redundant sample
##### -Send project data to reviewers
#### Perform the manual steps
##### -Send updates
#### Generate report & subsets data
##### -Export results

### SECUNDARY OBJECTIVES 
