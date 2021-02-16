# Ulat/Archive

Archive ng mga ulat sa baha \(tingnan ang Mga dokumentasyon ng  [Reports endpoint](reports.md)\), na ipinakita bilang isang JSON kasama ang lahat ng mga ulat sa pagbaha na natanggap sa loob ng tinukoy na tagal ng panahon.

Sa kasalukuyan ang mga datos na ito ay magagamit lamang para sa Quezon City at Pamapanga.

## Format ng Kahilingan

| Query Parameter | Paglalarawan | Format | Required |
| :--- | :--- | :--- | :--- |
| start | Oras ng pagsisimula para sa panahon ng archive | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |
| end | Pagtatapos ng oras para sa panahon ng archive | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |
| city | Aling lungsod ang nais nating ibalik ang mga imprastraktura? \(isa sa `bdg`, `jbd`, `sby`\) | String | No |
| geoformat | Anong format ang dapat gamitin ang mga resulta sa heyograpiya? \(isa sa `topojson`, `geojson` defaults to `topojson`\) | String | No |

Tandaan na ang time zone ay dapat na tinukoy bilang +/- Ang offset ng UTC na mangangailangan ng pag-encode ng character na HTML \(hal. +0700 nagiging% 2B0700\).

## Kumuha/reports/archive

## KUMUHA /reports

Ilista ang mga ulat sa pagbaha sa Quezon City at Pampanga na natanggap sa loob ng tinukoy na window ng oras:

```text
curl "https://data.petabencana.id/reports/archive?start=2017-12-04T00%3A00%3A00%2B0700&end=2017-12-06T05%3A00%3A00%2B0700&geoformat=geojson"
```

Ang mga resulta ay ang mga sumusunod:

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

