# semanticwebproject

Semantic Web Project for Year 4 of Software Development in GMIT by Andrew Sweeney

![Screenshot](http://puu.sh/lutuj/505553cf32.png)

# Contents

## The Project

* Project Outline
* Choosen Datasets
* Integration plan
* Things that changed and reflection

## Installation and Use

* Installation
* Api Use
* Summary
* References

# The Project

# Project Outline

The project was assigned as part of the Semantic Web Module for Dr Ian Mc'Loughlin in GMIT. This is a fourth year project showcasing use of Node.js, Javascript, Googlemaps and HTML skills.

I chose to focus this project on the Galway county and use datasets relating to possible tourist activities. My aim was to highlight the areas in Galway that could potentially be used to create excursions and other touristic activites. This is why I chose to deal specifically with geojson data.

* Create a GitHub repo (this one) with Readme file using MarkDown format. 
* Find two open datasets,describe the datasets, their use and upload them to the repo for reference.
* Create a set of urls for querying these data sets, make sure to account for the type of actions that will be carried out on this dataset, enable http requests other then GET and document all of this.
* Decide on the best way to store the information (what kind of database)
* Describe each function of the api and the type of data returned.
* Comment on all of the code clearly

# Chosen Datasets

Choosing from both of these datasets 

* [DataGov Link](https://data.gov.ie/data)
* [CSO](http://www.cso.ie/)

After checking over them all I decided to use the following three datasets

* [Galway County Scenic Routes](https://data.gov.ie/dataset/galway-county-scenic-routesf5940)
* [Public Visitor Attractions Open Data](https://data.gov.ie/dataset/galway-city-public-visitor-attractions)
* [Galway City Parks](http://opendata.galwaycity.opendata.arcgis.com/datasets/683ff500430447c985f4775a6b5dd112_0)
* [Galway Structures](http://opendata.galwaycity.opendata.arcgis.com/datasets/5aeadf7112614f11b712734f9f47dab6_0.geojson)
* [Recreation Data](http://data.galwaycoco.opendata.arcgis.com/datasets/35907ebb169c4ce8960fc4731c3d16ff_0.geojson)

The goal of combining these three datasets is to point out if public visitor attractions and Galway parks are close to each other. This kind of information can be used for

* Creating walking tours
* Creating bus tours around galway
* Guiding the flow of tourists through the cities

# Integration Plan

I plan on developing the api using Node.JS using the chosen data sets. To give the user a quick way of accessing all of the functions I'm adding to the API I wish to develop a webpage using a prebuilt bootstrap template but heavily editing it for my needs. 

Seeing the project will be using Node.js and be heavily reliant on Javascript I have chosen the Google Maps API for representing the data. Google Maps will let me overlay the GeoJSON polygon shape information on top of the map.

All of this information will be stored in an Sqlite3 database to store all of the information required for the API.

The user should be able to 

* View the different contrasts between the three datasets
* View information about the highlighted areas on the map
* Return json information on a selected area defined by the user
* Add their own points of interest

# Things that changed and reflection

After playing around with alot of different databases that Node.js could be implemented with I soon found Sqlite3 not to be ideal for what I was doing and pouchdb would be the better. It was easier to store geojson in pouchdb. There was very few geojson datasets out there for Galway so I took all that I could relating to tourism and ended up with the 5 mentioned. This resulted in a small dataset and this was another big reason for choosing pouchdb. 

# Installation and Use

For any missing or required please run the command

```npm install```

in the appropriate folder location.

To start the Node.js server run the command

```node runme```

runme.js is responsible for all of the function the application.

In the js folder the file "googlemaps.js" is responsible for displaying google maps.

Javascript on the html pages is responsible for some of the google maps displaying also.

# Api Use

| Request        | Description           | Example  | Example Parameters |
| ------------- |:-------------:| -----:|
|GET| Get the original Galway Attractions Data from FILE  | /GET_originaldata_galway_attactions | None |
|GET| Get the original Galway parks Data from FILE | /GET_originaldata_galway_parks | None |
|GET| Get the original Galway scenic Data from FILE | /GET_originaldata_galway_scenic  | None |
|GET| Get the original Galway structures Data from FILE | /GET_originaldata_galway_structures  | None |
|GET| Get the original Galway recreation strategy Data from FILE | /GET_originaldata_galway_recreationstrat | None |
|GET| All geojson data entries from database | /GET_allData  | None |
|DELETE| Clears the entire database. You will have to restart the server again to re-populate the pouchdb | /GET_allData  | None |
|GET| All a count of all entries currently in the database | /GET_COUNT | None |
|POST| Add an entry to the database | /GET_allData  | /POST_addEntry | /myname/category/mystreet/5000/900 |
|DELETE| Deletes an entry given the id | /GET_allData  | /DELETE_deleteEntry | /0 |
|GET| All the FIRST entry in the database | /GET_FIRST | None |
|GET| All LAST entry in the database | /GET_FIRST | None |
|GET| All FIRST available 10 entries in the database | /GET_HEAD| None |
|GET| All LAST available 10 entries in the database | /GET_TAIL | None |
|PATCH| Change a record in the database by a given id |  /PATCH_changeEntry | /012345/FFFF-FFFF-FFFF-FFFF/myname/category/mystreet/5000/900 |

# Extending the Api

# Summary

Node.js was quite enjoyable and easy to pick up and use. There is plenty of plugins out there to help you rapidly create your content. There was alot of Javascript and documents to read in the process of creating this API. I also found when dealing with a small amount of entries it's best to stick to a database suited for data that size instead of something potentially far bigger and un-needed.

The geojson around Galway wasn't as numerous as I thought it would be even though Galway has far more points of interest compared to the amount in the datasets supplied by the open data websites.

This kind of development is alot more different then creating something using PHP and a MySQL database in the background. Pouchdb and the other databases I experimented allowed for storing more then fields, they allowed for storing full json and even geojson objects.

Andrew Sweeney was the sole contributor on this project.

![Contributor](https://avatars1.githubusercontent.com/u/6676433?v=3&s=96)

# References

Links to resources
* [Node.js](https://nodejs.org/en/)
* [Sqlite3](https://www.npmjs.com/package/sqlite3)
* [Neo4j](https://www.npmjs.com/package/neo4j)
* [BootStrap Template](http://startbootstrap.com/template-overviews/sb-admin/)
* [Google Maps](https://developers.google.com/maps/?hl=en)
* [Pouchdb](http://pouchdb.com/learn.html)
* [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#tables)
* [DataGov](https://data.gov.ie/data)
* [Apps4Gaps](http://apps4gaps.ie/)




