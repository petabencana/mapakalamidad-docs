# Crowdsourced Reports/Archive

Archive of flood reports (see [Reports endpoint](reports.md) documentation), presented as a JSON with all the flood reports received within the specified time period.

## Request Format

| Query Parameter | Description                                                                                                    | Format                                              | Required |
| --------------- | -------------------------------------------------------------------------------------------------------------- | --------------------------------------------------- | -------- |
| start           | Start time for archive period                                                                                  | String in ISO 8601 format (YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes      |
| end             | End time for archive period                                                                                    | String in ISO 8601 format (YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes      |
| admin           | Which city do we wish to return infrastructure for? (one of [supported areas](../general/supported-area.md)`)` | String                                              | No       |
| geoformat       | What format should geographic results use (one of `topojson`, `geojson` defaults to `topojson`)                | String                                              | No       |

Note that time zone must be specified as +/- UTC offset which will require HTML character encoding (e.g. +0700 becomes %2B0700).

## Get /reports/archive

Note : Please include a User-Agent header in all of your requests. The User-Agent header helps us identify your requests and troubleshoot any issues you may have. To set the User-Agent header, add the following line to your request headers:

List flood reports received within specified time window

```
curl --user-agent "YOUR-UA-STRING" "https://api.mapakalamidad.ph/reports/archive?start=2017-12-04T00%3A00%3A00%2B0700&end=2017-12-06T05%3A00%3A00%2B0700&geoformat=geojson"
```

Results are as follows:

```javascript
{
    "statusCode": 200,
    "result": {
        "type": "FeatureCollection",
        "features": [
            {
                "type": "Feature",
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        106.815842,
                        -6.183179
                    ]
                },
                "properties": {
                    "pkey": "0001",
                    "created_at": "2017-12-04T09:51:00.000Z",
                    "source": "qlue",
                    "status": "confirmed",
                    "url": null,
                    "image_url": null,
                    "disaster_type": "flood",
                    "report_data": null,
                    "tags": {
                        "instance_region_code": "jbd",
                        "local_area_id": "782"
                    },
                    "title": " ",
                    "text": "#flood report"
                }
            }
          ]
        }
      }
```
