# Baha/Archive

Ang archive ng mga lugar na binabaha \(tingnan ang dokumentasyon ng [Floods endpoint](floods.md)\), na ipinakita bilang pinakamataas na flood state na naitala para sa lahat ng mga apektadong lugar sa baha sa loob na tinukoy na panahon. Ang maximum na estado ay naitala kasabay ng area id. Gamitin ang Floods endpoint upang makakuha ng mga hangganan ng geospatial ng mga bawat lugar.

Sa kasuluuyan ang datos na ito ay  magagamit lamang para sa Quezon City at Pampanga.

## Format ng Kahilingan

| Query Parameter | Paglalarawan | Format | Required |
| :--- | :--- | :--- | :--- |
| start | Oras ng pagsisimula para sa panahon ng archive. | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |
| end | Pagtatapos ng oras para sa panahon ng archive | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |

Tandaan na ang time zone ay dapat na tinukoy bilang +/- ang UTC na mangangailangan ng pag-encode ng character na HTML \(hal. +0700 nagiging% 2B0700\).

## Kumuha /floods/archive

## KUMUHA /floods

Ilista ang lahat ng mga lugar na binabaha sa Jakarta na may flood gauge ng 1 o mas mataas.

```text
curl "https://data.petabencana.id/floods/archive?start=2017-06-07T00:00:00%2B0700&end=2017-06-08T23:00:00%2B0700"
```

Ang mga resulta ay ang mga sumusunod:

```javascript
    {
        "statusCode": 200,
        "result": [
            {
                "area_id": "509",
                "last_updated": "2017-11-03T22:57:01.387Z",
                "max_state": 1
            },
            {
                "area_id": "510",
                "last_updated": "2017-11-03T22:57:10.463Z",
                "max_state": 4
            }
        ]
    }
```

