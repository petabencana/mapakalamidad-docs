# Feeds

Gumagamit ang MapaKalamidad ng mga data feed mula sa mga iilang third party sources. Pinapayagan ng endpoint na ito ang paglikha ng data sa system para sa mga awtorisadong gumagamit. Tandaan: Kinakailangan ang [pagpapatunay ](https://docs.petabencana.id/general/authentication)upang ma-post ang data sa pamamagitan ng /feeds endpoint.

## POST /feeds/qlue

Magdagdag ng isang ulat sa system mula sa [Qlue](https://www.qlue.co.id/). Sinusuportahan ang mga sumusnod na katangian para sa mga ulat ng Qlue:

| Katangian | Paglalarawan | Format | Required |
| :--- | :--- | :--- | :--- |
| post\_id | Natatanging tagatukoy ng Qlue para sa ulat | Integer | Yes |
| created\_at | Petsa at oras ang card ay nilikha | Date \([ISO 8601](http://www.iso.org/iso/home/standards/iso8601.htm)\) | Yes |
| title | Ang Pamagat ng ulat na iniharap | String | No |
| text | Paglalarawan ng kaganapan sa kalamidad | String | No |
| image\_url | URL na nauugnay na imahe | String | No |
| qlue\_city | Mula sa aling lungsod ang nabuong ulat \(dapat ay isa sa`Quezon City, Pampanga` | String | Yes |
| disaster\_type | Anong uri ng sakuna ang naiuulat \(sa kasulukuyan`baha` lamang ang suportado\) | String | Yes |
| location | Lugar ng heograpiya ng kaganapan ng kalamidad | Lat/Long in [ESPG:4326](http://spatialreference.org/ref/epsg/wgs-84/) | Yes |

Here is a simple call to POST a new Qlue report:

```text
curl -X POST -H "X-Api-Key: API_KEY_GOES_HERE" -d '{
    "post_id":1234567802,
    "created_at":"2016-12-09T11:32:52.011Z",
    "image_url":"http://myimg",
    "qlue_city":"jabodetabek",
    "disaster_type":"flood",
    "text":"A big flood",
    "location": {
        "lat": -6.149531,
        "lng": 106.869342
    }
}' "https://data.petabencana.id/feeds/qlue"
```

Matagumpay na nagawa ang ulat:

```javascript
{
  "post_id": 1234567802,
  "created": true
}
```

Ang kahilingan ay matagumpay subalit mayroon nang ulat:

```javascript
{
  "post_id": 1234567802,
  "created": false,
  "message": "1234567802 already exists in reports table"
}
```

