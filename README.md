# Winning Space Race with Data Science
***Advait Vinay Dhopeshwarkar<br/>***
***Dec, 2022***
## Outline
- Executive Summary
- Introduction
- Methodology
- Results
- Conclusion
- Appendix

## Executive Summary
- Summary of methodologies
- Summary of results

## Introduction
- Project background and context
- Problems you want to find answers to

## Methodologies
- Data collection method
- Data wrangling
- EDA visualization and SQL
- Interactive visual analytics with folium and plotly dash
- Predictive analysis with classification models

## Data Collection - SpaceX-API
#### [Github link](https://github.com/advaitvd/spacex_dashapp)
- The following url is used as a source of the spacex launch data.
```url = "https://api.spacexdata.com/v4/launches/past"```
- ```requests``` library is used to get the http response from the above url and the corresponding json is then converted to a pandas dataframe using  ```data = pd.json_normalize(response.json())``` 
- The obtained dataframe contains information regarding the rocket, payloads, launchpad, cores, flight_number, date_utc, etc. in the form of an API endpoint key which is used to obtain the required data for each of the data points. The functions ```getBoosterVersion(...), getLaunchSite(...), getPayloadData(...), getCoreData(...)``` achieve this for us.
```mermaid
graph TD;
  Program-->SpaceX_API;
  SpaceX_API-->launch_data;
  launch_data-->Program;
```
```mermaid
graph TD;
  getBoosterData-->SpaceX_API-->BoosterData-->getBoosterData;
  getLaunchSite-->SpaceX_API-->LaunchSite-->getLaunchSite;
  getPayloadData-->SpaceX_API-->PayloadData-->getPayloadData;
  getCoreData-->SpaceX_API-->CoreData-->getCoreData;
```
