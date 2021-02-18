Welcome to the ETL Project!!

This script may require you to pip install two modules: pip install census pip install python-dotenv

State_Census_df:

Census API Extraction: In order to pull the general Census data, we utilized the Census API built for Python. The hardest part was pulling the correct parameters from the Census since it uses extremely specific formatting for its variables. We had to combine three different categories to get a total count of uninsured residents.

Census API Transformation: Once we determined the columns we wanted to keep and renamed them appropriately, we did some calculations and added poverty rate and unemployment rate. We then sort by state, reset the index, and export the CSV. If there is no API Key, then the program will automatically pull the most recent output file in the Transform Data Kernel.

CSV Transformation: After importing the CSV, we remove D.C .and Puerto Rico and re-map the States column to abbreviations using the created dictionary for consistency.

Covid_Beds_df:

identfied data source, grabbed file
extract CSV into DF
dropped nonvalue add columns
dropped rows of entries that were not states - Puerto Rico, Washington D.C., CW -unk
Aggregated rows to get the last reported date for the 50 states, then left joined previous variable (fifty_states)
Voila`
Covid_Deaths_df:

Extract: the covid death data was available in csv format via the cdc.gov

Transform: First was to ommit columns that didn't pertain to the objective or didn't even make sense. Once the correct columns were obtained, a rename of the current columns was performed. Next, since the data had repeated days where there were no new cases of covid, a removal of all rows until the first case was reported was performed. Lastly, a removal of any abbreviation in the 'State' column that was not one of the fifty states.

Database Load: we connect to the database via SQLAlchemy’s create_engine() method. We then use Pandas’ built in to_sql() method to export the DataFrames into a SQL database that has already been created and titled "covid_census_db".