# CORS poc

Testing: curl --head -s 'http://example.com/api/v1/secret' -H 'Origin: http://evil.com'

Check to see what the server responds with in the Access-Control-Allow-Origin: (if anything) and if so, check if Access-Control-Allow-Credentials: true is present.

If it is trusting arbitrary origins with allow-credentials set to true, then host this HTML as a proof of concept.

# usage

open cors.html in your broswer

# everything you need to know about CORS

![IMG_20210702_133115](https://user-images.githubusercontent.com/83821864/124244349-7b6a0b00-db3c-11eb-88d3-bf53483e6331.jpg)


> what is CORS:     https://portswigger.net/web-security/cors

> how to hunt CORS: https://github.com/KathanP19/HowToHunt/tree/master/CORS

> CORS bypass:      https://book.hacktricks.xyz/pentesting-web/cors-bypass

> tools:            https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/CORS%20Misconfiguration

