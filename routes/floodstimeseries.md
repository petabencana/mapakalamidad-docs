# Baha/Timeseries

Serye ng oras ng mga lugar na binabaha \(tingnan ang dokumentasyon ng [Floods endpoint](floods.md)\), na itinanghal bilang bilang ng mga lugar na apektado ng baha bawat oras sa loob ng tinukoy na panahon. Ang bilang ay naitala kasama ang isang oras-oras na timestamp sa format na ISO8601 sa UTC + 0.

Sa kasuluuyan ang datos na ito ay magagamit lamang para sa Quezon City at Pampanga.

## Format ng Kahilingan

| Query Parameter | Paglalarawan | Format | Required |
| :--- | :--- | :--- | :--- |
| start | Oras ng pagsisimula para sa panahon ng serye ng oras. | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |
| end | Oras ng pagtatapos para sa panahon ng serye ng oras | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |

Tandaan na ang time zone ay dapat na tinukoy bilang +/- Ang offset ng UTC na mangangailangan ng pag-encode ng character na HTML \(hal. +0700 nagiging% 2B0700\).

## Kumuha /floods/timeseries

## KUMUHA /floods

Ilista ang lahat ng mga lugar na binabaha sa Quezon City at Pampanga na may flood gauge ng 1 o mas mataas

```text
curl "https://data.petabencana.id/floods/timeseries?start=2017-11-20T11%3A00%3A00-0500&end=2017-11-20T15%3A00%3A00-0500"
```

Ang mga resulta ay ang mga sumusnod:

```javascript
    {
        "statusCode": 200,
        "result": [
            {
                "ts": "2017-11-20T16:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T17:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T18:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T19:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T20:00:00.000Z",
                "count": "0"
            }
        ]
    }
```

