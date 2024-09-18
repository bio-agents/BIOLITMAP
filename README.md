# BIOLITMAP: a web-based geolocated and temporal visualization of the evolution of bioinformatics publications

## Description

Code for the web-based geolocated and temporal visualization of bioinformatics research (BIOLITMAP): http://socialanalytics.bsc.es/biolitmap/.

Paper accepted to Oxford Bioinformatics.

## Directory structure

* In /data the export of the BIOLITMAP SQL database is stored, as it was in December 2017.
* In /scripts the agents used for the NLP tasks are stored
* /scripts/src stores the codes related to the NLP, Clustering, Topic Modeling and Perplexity Analysis tasks.
* /scripts/vis stores the visualization created using the final Latent Dirichlet Allocation model, by employing the pyLDAvis package.
* /API stores the source codes of the REST API.

## Getting the data from the REST API

We have deployed in our servers a REST API to gather the data from the map in JSON format, the following endpoints are available:

1) http://socialanalytics.bsc.es/biolitmap-api/biolitmap/list - To get the complete list of the data.
2) http://socialanalytics.bsc.es/biolitmap-api/biolitmap/filter/source/"journal" - To filter by source (e.g. Oxford Bioinformatics).
3) http://socialanalytics.bsc.es/biolitmap-api/biolitmap/filter/year/[+-]"year" - To filter by year (e.g. 2010), you can use the + and - symbols to query for greater-equal or less-equal, respectively (e.g. +2010 or -2010).
4) http://socialanalytics.bsc.es/biolitmap-api/biolitmap/filter/nameAffiliation/"institution" - To filter by research institution (e.g. University of Cambridge).
  
### Example output from the /list endpoint

<div style="text-align:center"><img src="https://i.imgur.com/rC8VHO9.png" /></div>


## Getting the raw source data from Scopus

In order to obtain the raw source data with which this application has been built on, the following steps need to be followed:

1) Access to the Scopus (www.scopus.com) document search agent
2) Search the documents by using the following query: 

``ISSN ( 'JOURNAL_ISSN' ) AND ( LIMIT-TO ( PUBYEAR , 2017 ) OR LIMIT-TO ( PUBYEAR , 2016 ) OR LIMIT-TO ( PUBYEAR , 2015 ) OR LIMIT-TO ( PUBYEAR , 2014 ) OR LIMIT-TO ( PUBYEAR , 2013 ) OR LIMIT-TO ( PUBYEAR , 2012 ) OR LIMIT-TO ( PUBYEAR , 2011 ) OR LIMIT-TO ( PUBYEAR , 2010 ) OR LIMIT-TO ( PUBYEAR , 2009 ) OR LIMIT-TO ( PUBYEAR , 2008 ) OR LIMIT-TO ( PUBYEAR , 2007 ) OR LIMIT-TO ( PUBYEAR , 2006 ) OR LIMIT-TO ( PUBYEAR , 2005 ) ) AND ( LIMIT-TO ( EXACTKEYWORD , "Article" ) )``

3) Export the documents in CSV format with the 'Export' option.

## Journals

In this first version of the application, the articles from the following journals are extracted:

1) Oxford Bioinformatics (ISSN 1460-2059)
2) Nucleic Acids Research (ISSN 1362-4962)
3) BMC Bioinformatics (ISSN 1471-2105)
4) BMC Genomics (ISSN 1471-2164)
5) PLoS Computational Biology (ISSN 1553-734X)

## Contact

You can contact the developers by sending an email to adrian.bazaga@bsc.es or maria.rementeria@bsc.es

## Preview

<div style="text-align:center"><img src="https://i.imgur.com/iIvs1P8.png" /></div>

