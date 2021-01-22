ETL Read Me

Extract: the covid death data was available in csv format via the cdc.gov 

Transform: First was to ommit columns that didn't pertain to the objective or didn't even make sense. Once the correct columns were obtained, a rename of the current columns was performed. Next, since the data had repeated days where there were no new cases of covid, a removal of all rows until the first case was reported was performed. Lastly, a removal of any abbreviation in the 'State' column that was not one of the fifty states. 