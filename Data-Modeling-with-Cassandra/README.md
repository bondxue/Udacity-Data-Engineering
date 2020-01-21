# Song-Play-Analysis-with-Cassandra
Udacity Data Engineering ND project 2

[![Project passed](https://img.shields.io/badge/project-passed-success.svg)](https://img.shields.io/badge/project-passed-success.svg)

## Summary
* [Purpose of project](#Purpose-of-project)
* [Dataset](#Dataset)
* [Project structure](#Project-structure)
* [Quary example](#quary-example)

### Purpose of project
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. This project is trying to help them to build an **Apache Cassandra database** which can create queries to analysis song play data. 

### Dataset
The dataset is `event_data` which is under a directory of CSV files partitioned by date, e.g., 

```
event_data/2018-11-08-events.csv
event_data/2018-11-09-events.csv
```
Then Part I of `Project_1B_Project_Template.ipynb` creates a new CSV file based on `event_data` for the database: 
<img src="images/image_event_datafile_new.jpg">

### Project structure

* `Project_1B_Project_Template.ipynb` - contains the whole ETL pipeline

* `event_datafile_new.csv` - aggregated data file contains all `event_data`

### Quary example
*1. Give me the artist, song title and song's length in the music app history that was heard during  sessionId = 338, and itemInSession  = 4.*

For this quary, I create **music_library_by_session** table in which `PRIMARY KEY(session_id, item_in_session)`.

```SQL
SELECT * 
FROM music_library_by_session 
WHERE session_id=338 AND item_in_session=4
```
```
Output: 
Faithless Music Matters (Mark Knight Dub) 495.30731201171875 338 4
```


*2. Give me only the following: name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182*

For this quary, I create **music_library_by_user_session** table in which `PRIMARY KEY((user_id, session_id), item_in_session))`.

```SQL
SELECT * 
FROM music_library_by_user_session 
WHERE user_id=10 AND session_id=182
```

```
Output: 
Down To The Bone Keep On Keepin' On Sylvie Cruz 10 182 0
Three Drives Greece 2000 Sylvie Cruz 10 182 1
Sebastien Tellier Kilometer Sylvie Cruz 10 182 2
Lonnie Gordon Catch You Baby (Steve Pitron & Max Sanna Radio Edit) Sylvie Cruz 10 182 3
```

*3. Give me every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'*

For this quary, I create **user_table_by_song** table in which `PRIMARY KEY(song_name, user_id)`.

```SQL
SELECT * 
FROM user_table_by_song 
WHERE song_name='All Hands Against His Own'
```

```
Output:
Jacqueline Lynch 29 All Hands Against His Own
Tegan Levine 80 All Hands Against His Own
Sara Johnson 95 All Hands Against His Own
```

