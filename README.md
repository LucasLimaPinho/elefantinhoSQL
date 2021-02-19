# SparkFy Database

It is extremely important to have a **data-driven** culture in nowadays organizations.<br>


This database supports decision-making inside **SparkFy** startup. It is possible to extract insights and determine trends related to style of music and artists that are being more listened, as well as patterns of public behavior with respect to time - it is possible to infer musical styles that are heard most during weekends, for example.<br>

### Database Schema

The database schema is structured like this:

#### Fact Table
- **songplays**: records in log data associated with song plays i.e. records with page NextSong
    * songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

#### Dimension Tables
- **users**: users in the app
    * user_id, first_name, last_name, gender, level
- **songs**: songs in music database
    * song_id, title, artist_id, year, duration
- **artists**: artists in music database
    * artist_id, name, location, latitude, longitude
- **time**: time - timestamps of records in songplays broken down into specific units
    * start_time, hour, day, week, month, year, weekday
<br>

The tables are structured in a **star schema** optimized for queries in song play analysis.<br>

### ETL Process

The **ETL Process** is performed with python scripts.

~~~bash

# Creates database
python create_tables.py

~~~~
