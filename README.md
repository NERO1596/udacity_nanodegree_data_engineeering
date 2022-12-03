# Udactity Data Engineer Nanodegree Project 1: Data Modeling with Postgres


### Introduction
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from sparkify and compare your results with their expected results.


### Project Description
In this project, you'll apply what you've learned on data modeling with Postgres and build an ETL pipeline using Python. To complete the project, you will need to define fact and dimension tables for a star schema for a particular analytic focus, and write an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

### Data Model
I have implemented a star model.

### Fact Table

**Table songsplay**

| COLUMN  	| TYPE  	| CONSTRAINT  	|
|---	|---	|---	|	
|   songplay_id	| SERIAL  	|   PRIMARY KEY	| 
|   start_time	|   bigint	|   NOT NULL	| 
|   user_id	|   int	|   NOT NULL	| 
|   level	|   varchar |   	| 
|   song_id	|   varchar	|   	| 
|   artist_id	|   varchar	|   	| 
|   session_id	|   int	|   	| 
|   location	|   text	|   	| 
|   user_agent	|   text	|   	| 

#### Dimensions Tables
 I've create one table for each dimension of the **Fact Table**
 
 **Table users**
 
 | COLUMN  	| TYPE  	| CONSTRAINT  	|
|---	|---	|---	|	
|   user_id	| int  	|   PRIMARY KEY	| 
|   first_name	|   varchar	|  	| 
|   last_name	|   varchar	|  	| 
|   gender	|   varchar(1) |   	| 
|   level	|   varchar	|   	| 



**Table songs**

 | COLUMN  	| TYPE  	| CONSTRAINT   	|
|---	|---	|---	|	
|   song_id	| varchar  	|   PRIMARY KEY	| 
|   title	|   text	|  	| 
|   artist_id	|   varchar	|   	| 
|   year	|   int |   	| 
|   duration	|   numeric	|   	| 


**Table artists**

 | COLUMN  	| TYPE  	| CONSTRAINT   	|
|---	|---	|---	|	
|   artist_id	| varchar  	|   PRIMARY KEY	| 
|   name	|   varchar	|   	| 
|   location	|   text	|   	| 
|   latitude	|   decimal	|   	| 
|   longitude	|   decimal |   	| 



**Table time**
 
 | COLUMN  	| TYPE  	| CONSTRAINT   	|
|---	|---	|---	|	
|   start_time	| bigint  	|   PRIMARY KEY	| 
|   hour	|   int	|   	| 
|   day	|   int	|   	| 
|   week	|   int	|   	| 
|   month	|   int	|   	| 
|   year	|   int	|   	| 
|   weekday	|   varchar	|   	| 

