# covid_bed_Read
13-ETL-Project Lesson Plan

# To Do:
 Create tables in sql database (engine.execute())?
 Possible API integration with Census?
 
Covid Beds
- identfied data source, grabbed file
- extract CSV into DF
- dropped nonvalue add columns
- dropped rows of entries that were not states - Puerto Rico, Washington D.C., CW -unk
- Aggregated rows to get the last reported date for the 50 states, then left joined previous variable (fifty_states)
- Voila`



