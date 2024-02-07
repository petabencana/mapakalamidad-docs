# Ulat

Ang mga ulat tungkol sa live na kalamidad, sa pamamagitan ng default na mga ulat ay ibabalik sa huling oras.

## Format ng Kahilingan

| Query Parameter | Paglalarawan | Format | Required |
| :--- | :--- | :--- | :--- |
| city | Aling lungsod ang nais nating ibalik ang mga imprastraktura? \(isa sa `bdg`, `jbd`, `sby`\) | String | No |
| format | Aling format ang dapat nating ibalik ang mga resulta? \(isa sa `json`, defaults to `json`\) | String | No |
| geoformat | Anong format ang dapat gamitin ang mga resulta sa heyograpiya? \(isa sa `topojson`, `geojson` defaults to `topojson`\) | String | No |
| timeperiod | Anong tagal ng panahon \(sa mga segundo\) upang ilista ang mga ulat para sa, mahigpit na karapat-dapat sa pagitan ng 1 at 604800 \(1 linggo\) | Number | No |

## KUMUHA /reports

Ilista ang lahat ng kasalukuyang ulat sa baha para sa Quezon City at Pampanga.

Note : Please include a User-Agent header in all of your requests. The User-Agent header helps us identify your requests and troubleshoot any issues you may have. To set the User-Agent header, add the following line to your request headers:

```text
curl --user-agent "YOUR-UA-STRING" "https://api.mapakalamidad.ph/reports?admin=PH-00"
```

Ang mga resulta ay ang mga sumusnod:

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
              "source": "qlue",
              "status": "confirmed",
              "url": null,
              "image_url": "https://lh3.googleusercontent.com/ByClSrW6QhFkBxUhZo0rFt6eiVdvnEHisSzsgjaC9KxdGAQ6CYksTZRA1rcNP9cBGZiv6s4Vp5D8NzkAjPyrBs6c6R4h=s480-c",
              "disaster_type": "flood",
              "report_data": null,
              "tags": {
                "instance_region_code": "jbd",
                "local_area_id": "350"
              },
              "title": " ",
              "text": "Perlu penataan dan dirapihkan @ahokbtp semoga bisa lbh baik, bersih dan teratur"
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

