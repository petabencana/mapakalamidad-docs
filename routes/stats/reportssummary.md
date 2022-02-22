# Stats - Reports Summary

Count of reports by source ( "grasp" being combined Twitter, Facebook , Telegram and Website), by default reports will be returned for the last 3 hours.

## Request Format

| Query Parameter | Description                                                                                                     | Format | Required |
| --------------- | --------------------------------------------------------------------------------------------------------------- | ------ | -------- |
| admin           | Which city do we wish to return infrastructure for? (one of [supported areas](../../general/supported-area.md)) | String | No       |
| timeperiod      | What time period (in seconds) to list reports for, must be strictly between 1 and 604800 (1 week)               | Number | No       |

## GET /stats/getReportsSummary

```
curl "https://data.mapakalmidad.ph/stats/reportsSummary?admin=PH-01"
```

Results are as follows:

```javascript
{
  "statusCode": 200,
  "result": {
    "type": "Topology",
    "objects": {
      "output": {
        "type": "GeometryCollection",
        "geometries": [
          {
            "type": "Point",
            "properties": {
              "pkey": "5519",
              "created_at": "2016-12-09T21:37:00.000Z",
              "source": "grasp",
              "status": "confirmed",
              "url": null,
              "image_url": "https://lh3.googleusercontent.com/ByClSrW6QhFkBxUhZo0rFt6eiVdvnEHisSzsgjaC9KxdGAQ6CYksTZRA1rcNP9cBGZiv6s4Vp5D8NzkAjPyrBs6c6R4h=s480-c",
              "disaster_type": "flood",
              "report_data": null,
              "tags": {
                "instance_region_code": "PH-01",
                "local_area_id": "350"
              },
              "title": " ",
              "text": "Flood report"
            },
            "coordinates": [
              0,
              0
            ]
          }
        ]
      }
    },
    "arcs": [],
    "transform": {
      "scale": [
        1,
        1
      ],
      "translate": [
        106.817276,
        -6.138229
      ]
    },
    "bbox": [
      106.817276,
      -6.138229,
      106.817276,
      -6.138229
    ]
  }
}
```
