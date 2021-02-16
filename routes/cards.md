# Cards

Ang mga card report ng MapaKalamidad para sa mga kaganapan ng sakuna. Tandaan: Kinakailangan ang pagpapatunay \(authentication\) upang maka-update sa mga card.

## Format ng Kahilingan

| URL Parameter | Paglalarawan | Format | Required |
| :--- | :--- | :--- | :--- |
| cardId | Natatanging pagkakakilanlan ng card na nais naming gumana, nabubuo ito ng system kapag nilikha ang sinimulang card. \(Kinakailangan\) | String \(7 to 14 characters\) | Yes |

| Attribute | Paglalarawan | Format | Required |
| :--- | :--- | :--- | :--- |
| card\_data | Nakolekta ang datos ng gumagamit sa interface ng card | JSON | Yes |
| text | Paglalarawan ng kaganapan sa sakina | String | No |
| image\_id | Tukoy ng nauugnay na imahe ng card | String | No |
| created\_at | Petsa at oras ang card ay nilikha | Date \([ISO 8601](http://www.iso.org/iso/home/standards/iso8601.htm)\) | Yes |
| location | Lugar ng Heograpiya ng kaganapan sa sakuna | Lat/Long in [ESPG:4326](http://spatialreference.org/ref/epsg/wgs-84/) | Yes |

### Tanda sa card\_data

Kinakailangan ng Card data na ang object `report_type` ay umiiral. Kung saan `disaster_type` ay naka 'flood' at ang object `flood_depth` ay umiiral kasunod ang`report_type`.  Saan ang `disaster_type`  ay 'prep' pagkatapos ang`report_type` ay dapat isa sa mga tipo na nakalista sa server config.js   
  
Halimbawa ng isang card na may data ng pagbaha kasama ang flood \_depth:

```javascript
   "disaster_type": "flood",
   "card_data":{
    "report_type": "flood",
    "flood_depth": 50
  }
```

O kaya, isang card na may ulat ng data bago ang pagbaha tungkol sa isang kanal.

```javascript
  "disaster_type": "prep",
  "card_data":{
    "report_type":"drain"
  }
```

## KUMUHA/cards/:cardId

Kunin ang mga detalye ng isang card:

Narito ang isang simpleng halimbawa upang makakuha \(GET\) ng isang card:

```text
curl -X GET -H "X-Api-Key: API_KEY_GOES_HERE" "https://data.petabencana.id/cards/abcdefg"
```

Nahanap ang card:

```javascript
{
  "statusCode": 200,
  "result": {
    "pkey": "2",
    "card_id": "abcdefg",
    "username": "user",
    "network": "test",
    "language": "en",
    "received": true,
    "report_id": "1"
  }
}
```

Hindi umiiral ang card:

```javascript
{
  "statusCode": 404,
  "found": false,
  "result": null
}
```

## ILAGAY/cards/:cardId

I-update ang card kasama ang mga detalye tungkol sa isang ulat tungkol sa kalamidad:

Ito ay isang simpleng halimbawa paano ilagay \(PUT\) ang card:

```text
curl -X PUT -H "X-Api-Key: API_KEY_GOES_HERE" -d '{
    "text": "test card",
    "disaster_type": "flood"
    "card_data":
      {
        "report_type": "flood",
        "flood_depth": 101
      },
    "created_at":"2016-12-09T11:32:52.011Z",
    "location": {
        "lat": -6.149531,
        "lng": 106.869342
    }
}' "https://data.petabencana.id/cards/abcdefg"
```

Matagumpay nagawa ang card: 

```javascript
{
  "statusCode": 200,
  "cardId": "abcdefg",
  "created": true
}
```

Hindi umiiral ang card: 

```javascript
{
  "statusCode": 404,
  "cardId": "abcdefg",
  "message": "No card exists with id 'abcdefg'"
}
```

Mayroon nang ulat para sa card: 

```javascript
{
  "statusCode": 409,
  "cardId": "abcdefg",
  "message": "Report already received for card 'abcdefg'"
}
```

## KUMUHA/cards/:cardId/images

KUMUHA ng isang naka-sign na S3 URL upang mag-upload ng isang ulat sa card, dapat itong gawin pagkatapos malikha ang ulat ng card at isang imahe lamang ang maaring magkaroon para sa isang naibigay na card.

TANDAAN: Matapos isumite ang isang imahe sa servier-side ay pinapaliit ang imahe sa isang karaniwang sukat at maaaring mayroong kaunting lag ng ilang segundo bago ang imahe ay maging "live".

Narito ang isang simpleng halimbawa upang makakuha ng isang bagong naka-sign na S3 URL para sa pag-upload ng imahe: 

```text
curl -X GET \
  https://api-server-dev.riskmap.in/cards/HJID8CWN-/images
```

Matagumpay na nabuo ang naka-sign na S3 URL:

```javascript
{"signedRequest":"https://riskmap-image-uploads.s3.ap-south-1.amazonaws.com/originals/BJbTHR-Vb.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAJFMR3NR7BXZ5X7DA%2F20170629%2Fap-south-1%2Fs3%2Faws4_request&X-Amz-Date=20170629T012002Z&X-Amz-Expires=900&X-Amz-Signature=ad10a53555205fa18ecfa07da52eb0349ed1c8bda66fe2de0fa9c445c61b7c62&X-Amz-SignedHeaders=host","url":"https://s3.ap-south-1.amazonaws.com/riskmap-image-uploads/originals/BJbTHR-Vb.jpg"}
```

