# Flood Gauges

Ang mga live flood gauge reports, kadalasan, ay ibabalik sa huling oras.

## Format ng Kahilingan

| Query Parameter | Paglalarawan | Format | Required |
| :--- | :--- | :--- | :--- |
| city | Aling lungsod ang nais nating ibalik ang mga imprastraktura? \(isa sa `bdg`, `jbd`, `sby`\) | String | No |
| format | Aling format ang dapat nating ibalik? \(isa sa`json`, defaults to `json`\) | String | No |
| geoformat | Aling format ang dapat gamitin ang mga resulta sa heyograpiya? \(isa sa `topojson`, `geojson` defaults to `topojson`\) | String | No |

## KUMUHA /floodgauges

Ilista ang lahat ng kasalukuyang ulat sa gauge ng baha para sa Quezon CIty and Pampanga.

```text
curl "https://data.petabencana.id/floodgauges?city=jbd"
```

Ang mga resulta ay ang mga sumusunod:

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
              "gaugeid": "TMA00001",
              "gaugenameid": "Bendung Katulampa",
              "observations": [
                {
                  "f1": "2016-12-09T04:00:00+00:00",
                  "f2": 30,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T05:00:00+00:00",
                  "f2": 30,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T06:00:00+00:00",
                  "f2": 30,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T07:00:00+00:00",
                  "f2": 30,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T08:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T09:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T10:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T11:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T12:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T13:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                }
              ]
            },
            "coordinates": [
              6271,
              0
            ]
          },
          {
            "type": "Point",
            "properties": {
              "gaugeid": "TMA00002",
              "gaugenameid": "Pos Depok",
              "observations": [
                {
                  "f1": "2016-12-09T04:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T05:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T06:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T07:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T08:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T09:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T10:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T11:00:00+00:00",
                  "f2": 95,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T12:00:00+00:00",
                  "f2": 95,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T13:00:00+00:00",
                  "f2": 95,
                  "f3": 4,
                  "f4": "SIAGA IV "
                }
              ]
            },
            "coordinates": [
              5354,
              3943
            ]
          },
          // etc. etc. //
          {
            "type": "Point",
            "properties": {
              "gaugeid": "TMA00012",
              "gaugenameid": "Waduk Pluit",
              "observations": [
                {
                  "f1": "2016-12-09T04:00:00+00:00",
                  "f2": -165,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T05:00:00+00:00",
                  "f2": -170,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T06:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T07:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T08:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T09:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T10:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T11:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T12:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T13:00:00+00:00",
                  "f2": -170,
                  "f3": 4,
                  "f4": "SIAGA IV "
                }
              ]
            },
            "coordinates": [
              4559,
              9999
            ]
          }
        ]
      }
    },
    "arcs": [],
    "transform": {
      "scale": [
        0.00002272427242724299,
        0.000052198219821982215
      ],
      "translate": [
        106.69416,
        -6.63304
      ]
    },
    "bbox": [
      106.69416,
      -6.63304,
      106.92138,
      -6.11111
    ]
  }
}
```

