# Surf n' Shake Surf Shop: Statistical Analysis of Proposed Location (Oahu, Hawaii)

## Process Overview: 
UPDATE THIS - Describe process of what we did: SQLite Database & queries within Python utilizing SQLAlchemy

## Overview of the Statistical Analysis:

The purpose of the requested statistical analysis was to help our client, W. Avy, better understand temperature trends in Oahu, Hawaii. 

In addition to the analysis requested by W. Avy, we decided to conduct an additional statistical analysis to evaluate precipitation amounts in Oahu in June versus December. See below for these additional queries. 

The results of these statistical analyses will help W. Avy decide if Oahu is an ideal location for his Surf n' Shake shop and ensure that his combination business is sustainable year-round.

### Temperature Observation Queries - June vs. December: 

To accomodate W. Avy's original request for a statistical analysis of temperature difference between June and December, we utilized the following queries: 

```
# 2. Convert the June temperatures to a list.
# Need to remove the date so have a list of only June temps
june_results = []
june_results = session.query(Measurement.tobs).filter(extract('month', Measurement.date) == 6).all()
print(june_results)
```

```
# 3. Create a DataFrame from the list of temperatures for the month of June. 
june_tobs_df = pd.DataFrame(june_results, columns=['temperatures'])
june_tobs_df.head(15)
```

```
# 4. Calculate and print out the summary statistics for the June temperature DataFrame.
june_tobs_df.describe()
```

```
# 7. Convert the December temperatures to a list.
december_results = []
december_results = session.query(Measurement.tobs).filter(extract('month', Measurement.date) == 12).all()
print(december_results)
```

```
# 8. Create a DataFrame from the list of temperatures for the month of December. 
december_tobs_df = pd.DataFrame(december_results, columns=['temperatures'])
december_tobs_df.head(15)
```

```
# 9. Calculate and print out the summary statistics for the Decemeber temperature DataFrame.
december_tobs_df.describe()
```

### Additional Queries - Precipitation - June vs. December:

To provide W. Avy with additional information to help him confirm Oahu as an ideal location for his business, I wrote additional queries to evaluate the differences in precipitation amounts between the months of June and December: 

```
# Convert the June precipitation amounts to a list.
june_prcp_results = []
june_prcp_results = session.query(Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()
print(june_prcp_results)
```

```
# Create a DataFrame from the list of precipitation amounts for the month of June. 
june_prcp_df = pd.DataFrame(june_prcp_results, columns=['precipitation'])
june_prcp_df.head(15)
```

```
# Summary statistics for precipitation in month of June.
june_prcp_df.describe()
```

```
# Convert the December precipitation amounts to a list.
december_prcp_results = []
december_prcp_results = session.query(Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()
print(december_prcp_results)
```

```
# Create a DataFrame from the list of precipitation amounts for the month of December. 
december_prcp_df = pd.DataFrame(december_prcp_results, columns=['precipitation'])
december_prcp_df.head(15)
```

```
# Summary statistics for precipitation in the month of December
december_prcp_df.describe()
```

## Descriptive Statistics: 

### June Temperature Observations:

![june_tobs.png](Resources/june_tobs.png)

### December Temperature Observations:

![december_tobs.png](Resources/december_tobs.png)

### June Precipitation Amounts:

![june_prcp.png](Resources/june_prcp.png)

### December Precipitation Amounts:

![december_prcp.png](Resources/december_prcp.png)


## Results: Oahu Key Weather Different (June vs. December)

The descriptive statistics hightlight three key differences in weather between June and December: 

- 1
- 2
- 3

## Summary:

There is a high-level summary of the results.

