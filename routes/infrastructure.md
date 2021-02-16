# Imprastraktura

Ang mga lokasyon ng lokal na imprastraktura kabilang ang mga flood gates, bomba at daanan ng tubig.

## Format ng Kahilingan

| URL Parameter | Paglalarawan | Format | Required |
| :--- | :--- | :--- | :--- |
| type | Anong uri ng imprastraktura ang nais naming ilista?  \(isa sa`floodgates`, `pumps`, `waterways`\) | String | Yes |

| Query Parameter | Paglalarawan | Format | Required |
| :--- | :--- | :--- | :--- |
| city | Aling lungsod ang nais nating ibalik ang mga imprastraktura? \(isa sa `bdg`, `jbd`, `sby`\) | String | No |
| format | Aling format ang dapat nating ibalik? \(isa sa `json`, defaults to `json`\) | String | No |
| geoformat | Anong format ang dapat gamitin ng geographic results o ang resulta sa heyograpiya \(isa sa `topojson`, `geojson` defaults to `topojson`\) | String | No |

## KUMUHA /infrastructure/:type

Ibalik ang isang listahan ng mga bomba sa Quezon CIty at Pampanga. 

```text
curl "https://data.petabencana.id/infrastructure/pumps?city=jbd"
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
              "name": "PA Marina"
            },
            "coordinates": [
              7164,
              7352,
              0
            ]
          },
          {
            "type": "Point",
            "properties": {
              "name": "Pompa Waduk Setia Budi Barat"
            },
            "coordinates": [
              5312,
              5077,
              0
            ]
          },
          // etc. etc. //
          {
            "type": "Point",
            "properties": {
              "name": "Pompa UP Senen"
            },
            "coordinates": [
              6143,
              6544,
              0
            ]
          }
        ]
      }
    },
    "arcs": [],
    "transform": {
      "scale": [
        0.000020651319451945148,
        0.000020217245084508508
      ],
      "translate": [
        106.7188310623,
        -6.3060956581
      ]
    },
    "bbox": [
      106.7188310623,
      -6.3060956581,
      106.9253236055,
      -6.1039434245
    ]
  }
}
```

