# Error Codes

Sumusunod ang MapaKalamidad sa pamantayan ng HTTP Status Codes upang maghatid ng mga pagkakamali kasama ang isang mensahe na json formmatted na nagbibigay impormasyon ukol sa ugat ng pagkakamali. Ang mga pangunahing ginamit na codes ay ang sumusunod:

## 4xx Errors

Ipinapahiwatig ng mga pagkakamaling nagsisimula sa 4 ang mga isyu sa panig ng kliyente na dapat ma resolba bago muling magtanong ng serbisyo tulad ng:

* **400 Bad Request** - madalas sanhi ito ng isang maling query parameter tulad ng:`"child \"type\" fails because [\"type\" must be one of [floodgates, pumps, waterways]]"`
* **403 Forbidden** -  ****ang tanda ng pagpapatunay ay imbalido
* **404 Not Found** - hindi mahanap ang pinagkukunan, maari na ito ay nagpapahiwatig nang maling endpoint o sinusubukang mag rekord tulad ng isang report na hindi namamalagi.
* **409 Conflict** - tunay ang pinagkukunan subalit kapag pinayagan ang hiling, magkakaroon ng hindi pagkakasundo na mabubuo sa sistema, tulad ng pag-file ng ulat sa card kung saan ang ulat ay namamalagi.
* **415 Unsupported Media Type** - ang file na ini-upload ay hindi sinusuporta ng sistema - kadalasan ibig sabihin nito na may binary file tulad ng isang imahe ay ini-iupload subalit ang Content-Type header kasama ang nauugnay na MIME type \(e.g. ‘image/jpeg’\) ay hindi pa nabibigay.
* **429 Too Many Requests** - sumobra na ang quota ng mga hilig bawat segundo o bawat araw.

## 5xx Errors

Errors starting with a 5 generally indicate a server side fault and should be immediately:

Madalas ang mga pagkakamaling nagsisimula sa 5 ay nagpapahiwatig ng depekto sa server at dapat ma resolba agad-agad:

* **500 Internal Server Error** - isang pangkalahatang pagkakamali sa panig ng server. 
* **503 Service Unavailable** - bagsak ang serbisyo at hindi maka-responde sa mga hiling. 

