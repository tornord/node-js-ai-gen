# Weather forecast page

## Overview

The Weather Page is a React component that displays weather information for a specific location.

## Weather svg icons

Create weather react svg components for weather types:

- Clear
- Clouds
- Drizzle
- Rain
- Snow

## SMHI API

Use SMHI API to get weather data. Use location Stokholm: 59.334591, 18.063240, set lat & lon as env variables.
Add an server endpoint `/api/forecast` that calls the SMHI API 

SMHI endpoint to use: [SMHI forecast](https://opendata-download-metfcst.smhi.se/api/category/pmp3g/version/2/geotype/point/lon/{lon}/lat/{lat}/data.json)

Documentation: [SMHI API](https://opendata-download-metfcst.smhi.se/metfcst/pmp/introduction)

The response data structure is:

```typescript
interface SmhiForecastResponse {
    approvedTime: string;
    referenceTime: string;
    geometry: {
        type: string;
        coordinates: number[][]; // Array of coordinates
    };
    timeSeries: Array<{
        validTime: string;
        parameters: Array<{
            name: string;
            levelType: string;
            level: number;
            unit: string;
            values: number[]; // Array of values
        }>;
    }>;
} 
```

Only keep these `parameters.name` values:

- "t" Air temperature
- "ws" Wind speed
- "wd" Wind direction
- "pcat" Precipitation category, can be 0=no precipitation (clear), 1=snow, 2=snow and rain, 3=rain, 4=drizzle, 5=freezing rain, 6=freezing drizzle
- "pmean" Mean precipitation intensity

Format the `validTime` to string `MMM d HH:mm`
Convert wind direction degrees to compass direction: N, NE, E, SE, S, SW, W, NW

## Weather page

Create a weather page component that displays the weather data. Show both 
- a table by time as rows and weather parameters as columns.
- a svg graph temperature by time.

## Testing

Create a mocking response from the SMHI API.
Create a server endpoint test for`/api/forecast` nock the smhi api with the mock response.
Create component unit tests for the weather page component.
Create stories for each weather svg component and the weather page component.
