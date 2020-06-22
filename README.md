# weather_service(Back-end Only)
Free Public API to get all the weather of Indian states. This Project is made on GraphQL and NodeJS

## How to run the app
- 1.)  Either fork or clone
- 2.)  Run:- npm install
- 2b.) create a mongo db "weather" with collection "city" with required schema or __Use This__

- 3.)  In the weatherAPI_GQL_SERVER Directory run :- npm run devStart
- 4.)  In the weatherAPI_endpoints Directory run :- node app.js

### To Do
- [ ]  Handle Error Requests
- [ ]  Dockerise the project
- [ ]  Host it for free
- [x]  Update the Documentation

## How to use the app

1.) you can make a post request to ```/city/name```
__Ex:- /city/HR__

__Where the name are the abbreviation of the states in India__
__There are only the following abbreviation for now__

	
   - MP
   - TN
   - TG
   - HR
   - CT
   - MP
   - MH
   - TR
   - CH_TL
   - KA
   - KL
   - UT
   - AS
   - MH_2
   - WB
   - GJ
   - OR
   - RJ
   - HP
   - HR_2
 
 
# Output Format (When No body is passed)
```
 {
      getWeatherReport{
          lat,
          lon,
          current{
              dt
              sunrise
              sunset
              temp
              feels_like
              pressure
              humidity
              dew_point
              uvi
              clouds
              visibility
              wind_speed
              wind_deg,
              weather {
              id,
              main,
              description,
              icon
              }
          },
          hourly{
              dt
              sunrise
              sunset
              temp
              feels_like
              pressure
              humidity
              dew_point
              uvi
              clouds
              visibility
              wind_speed
              wind_deg,
              weather {
              id,
              main,
              description,
              icon
              }
          }
      }
  }
```

## Example Would be
```
{
  "data": {
    "getWeatherReport": [
      {
        "id": "5ee874c3f7bcbf5fec3bb79a",
        "lat": 29.24,
        "lon": 76.43,
        "current": {
          "dt": 1592206098,
          "sunrise": 1592178882,
          "sunset": 1592229299,
          "temp": 316.54,
          "feels_like": 311.83,
          "pressure": 997,
          "humidity": 8,
          "dew_point": 275.15,
          "uvi": 12.04,
          "clouds": 0,
          "visibility": null,
          "wind_speed": 4.32,
          "wind_deg": 329,
          "weather": [
            {
              "id": 800,
              "main": "Clear",
              "description": "clear sky",
              "icon": "01d"
            }
          ]
        },
        "hourly": [
          {
            "dt": 1592179200,
            "sunrise": null,
            "sunset": null,
            "temp": 305.62,
            "feels_like": 304.51,
            "pressure": 998,
            "humidity": 24,
            "dew_point": 282.46,
            "uvi": null,
            "clouds": 0,
            "visibility": null,
            "wind_speed": 1.37,
            "wind_deg": 51,
            "weather": null
          },
          .......
```

## For Just some Part of the Data you can throw in a body also.

```
{
	"lat": 1,
	"lon": 1,
	"current":{},
	"hourly":{}
}
```
