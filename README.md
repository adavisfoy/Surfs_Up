# Surf n' Shake Surf Shop: Statistical Analysis of Proposed Location (Oahu, Hawaii)


## Overview of the statistical analysis:

The purpose of this statistical analysis was to help our client, W. Avy, better understand temperature trends in Oahu, Hawaii. The results of this statistical analysis will help him decide if Oahu is an ideal location for his Surf n' Shake shop and ensure that his combination business is sustainable year-round. 

## Results:

There is a bulleted list that addresses the three key differences in weather between June and December. (6 pt)


- 1
- 2
- 3

## Summary:

There is a high-level summary of the results and there are two additional queries to perform to gather more weather data for June and December. (5 pt)

## Additional Queries:

To provide W. Avy with additional information to help him confirm Oahu as an ideal location for his business, I wrote additional queries to evaluate the differences in precipitation amounts between the months of June and December. 

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
