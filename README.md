Surfs_up
For learning Advanced Data Storage and Retrieval from Module 9

Project Overview
W. Avy likes the analysis, but he wants more information about temperature trends before opening the surf shop. Specifically, he wants temperature data for the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round.

Resources
sqlite, Anaconda, Jupyter notebook, Visual Code
data for tables from hawaii.sqlite
Challenge Overview
Prerequisite:

Download the SurfsUp_Challenge_starter_code.ipynb file
Deliverable 1: Determine the Summary Statistics for June
Follow the instructions below to complete Deliverable 1.

Write a query that filters the date column from the Measurement table to retrieve all the temperatures for the month of June.
Convert the June temperatures to a list.
Create a DataFrame from the list of temperatures for the month of June.
Generate the summary statistics for the June temperatures DataFrame.
Deliverable 2: Determine the Summary Statistics for December
Follow the instructions below to complete Deliverable 2.

Write a query that filters the date column from the Measurement table to retrieve all the temperatures for the month of December.
Convert the December temperatures to a list.
Create a DataFrame from the list of temperatures for the month of December.
Generate the summary statistics for the December temperatures DataFrame.
Surfs_up-Analysis Results
Image of summary statistics for the June temperatures image_name

Image of summary statistics for the December temperatures image_name

Image of summary statistics for the June precipitations image_name

Image of summary statistics for the December precipitations image_name

Surfs_up-Analysis Summary
Average June temperature is 75 and Average December temperature is 71, which is not bad considering december month is a winter month
In June also the minimum temperature is 64 only considering June is a Summer month. We might need to consider the precipitation also before staring an ice cream shop.
December maximumn temperature is 83 which is a good sign to start an ice cream shop.
Additional Queries:

June Precipitation statistics
-- Following code will give information about precipitation for the month of June

month_str = "06"

results = session.query(Measurement.prcp).filter(func.strftime("%m", Measurement.date) == month_str).all()

june_prcp = list(np.ravel(results))

June_Prcp_df = pd.DataFrame(june_prcp,columns=["June Prcps"])

June_Prcp_df.describe()

December Precipitation statistics
-- Following code will give information about precipitation for the month of December

month_str = "12"

results = session.query(Measurement.prcp).filter(func.strftime("%m", Measurement.date) == month_str).all()

december_prcp = list(np.ravel(results))

December_Prcp_df = pd.DataFrame(december_prcp,columns=["December Prcps"])

December_Prcp_df.describe()
