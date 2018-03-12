So The Challenge is :
Sam decided to make a music site. Unfortunately he does not understand Apache. This mission is a bit harder than the other basics.
Now Thinking of directory traversal can be a good idea but not with a tool I spent quite sometime looking around for any possible wordlist to traverse the website
but nothing worked out 

Now there reason why is that the directories are custom made 

now if we check the output 
```html
I love my music!
"Restless " is the best!

<!--We even have our own collection - if you could find it!-->
```
Refresh one more time we have something different 
```html
I love my music!
"Empty Sky" is the best!

<!--We even have our own collection - if you could find it!-->
```
and so on but the most common this is that all the songs are by artist called **elton john** so maybe the directories are named after him
if we checked a directory called **e/** first letter of elton john 
we will find that there is a directory there and indexing is enabled when we reach the end the full path will be the following 

```html
https://www.hackthissite.org/missions/basic/11/e/l/t/o/n/
```
now the challenge says that SAM doesn't know apache so he probably missed something in .htaccess or .htpassword lets check them

```html
https://www.hackthissite.org/missions/basic/11/e/l/t/o/n/.htaccess
```
will have the output of 
```text
IndexIgnore DaAnswer.* .htaccess
<Files .htaccess>
order allow,deny
allow from all
</Files>
```
so there is a directory that wont be listed which is called **DaAnswer/**
lets see whats inside

```
https://www.hackthissite.org/missions/basic/11/e/l/t/o/n/DaAnswer
```
will have the output of 
```text
The answer is not here!
Just look a little harder.
```
Now lets see if we have something hidden , after quite sometime I figured out that the phrase 
```text
The answer is not here -> means password = not here
```
no we can go to https://www.hackthissite.org/missions/basic/11/index.php
and submit **not here** as password

