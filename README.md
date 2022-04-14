# election analysis 2021 and 2022 the Hague

A notebook based analysis of the elections of 2021 (national) and 2022 (municipal) in the Hague. 

The data is collected in 01_webscraping, transformed in 02_transformation and analysed and visualized in 03_analysis. The shapefiles folder contain the output of geopandas, a Python library for GIS-analysis. 

## webscraping

scrape_results_election.ipynb scrapes the results of the 2021 and 2022 elections per neighborhood. 
scrape_stemwijzers.ipynb scrapes the national stemwijzer for 2021 and the stemwijzer 2022 the hague. 

## transformation

calculate_difference_volt_stemwijzer.ipynb creates a dataframe with that contains the difference in answers between volt and the other parties on statments in the stemwijzer. Agree is given a dummy variable of 1, neutral of 0 and disagree of -1 on the answers to statements in the stemwijzer. Therefore, the difference between agree and disagree is 2, and the difference between neutral and agree/disagree is 1. The sum is then calculated by adding the absolute differences. 

create_difference_per_neighborhood.ipynb aggregates this difference score per neighborhood by calculating the weighted averages per neighborhood, weighing the averages using the proportion of votes a party receives and multiplying this proportion with their difference score. 

## analysis

analysis_elections.ipynb contains  graphs about the elections, comparing 2021 and 2022. 
plot_geo.ipynb contains interactive two interactive geopandas plots based on the 