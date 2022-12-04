## Data Collection
- The following url is used as a source of the spacex launch data.
```url = "https://api.spacexdata.com/v4/launches/past"```
- ```requests``` library is used to get the http response from the above url and the corresponding json is then converted to a pandas dataframe using  ```data = pd.json_normalize(response.json())``` 
- The obtained dataframe contains information regarding the rocket, payloads, launchpad, cores, flight_number, date_utc, etc. in the form of an API endpoint key which is used to obtain the required data for each of the data points. The functions ```getBoosterVersion(...), getLaunchSite(...), getPayloadData(...), getCoreData(...)``` achieve this for us.
```mermaid
graph TD;
  Program-->SpaceX_API;
  SpaceX_API-->launch_data;
  launch_data-->Our_Program;
```
```mermaid
graph TD;
  Program-->getBoosterData;
  Program-->getLaunchSite;
  Program-->getPayloadData;
  Program-->getCoreData;
  getBoosterData-->SpaceX_API-->BoosterData-->getBoosterData-->Program;
  getLaunchSite-->SpaceX_API-->LaunchSite-->getLaunchSite-->Program;
  getPayloadData-->SpaceX_API-->PayloadData-->getPayloadData-->Program;
  getCoreData-->SpaceX_API-->CoreData-->getCoreData-->Program
```
