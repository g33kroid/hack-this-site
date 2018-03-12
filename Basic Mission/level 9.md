The Challenge is :

Network Security Sam is going down with the ship - he's determined to keep obscuring the password file, no matter how many times people manage to recover it. This time the file is saved in /var/www/hackthissite.org/html/missions/basic/9/.

In the last level, however, in my attempt to limit people to using server side includes to display the directory listing to level 8 only, I have mistakenly screwed up somewhere.. there is a way to get the obscured level 9 password. See if you can figure out how...

This level seems a lot trickier then it actually is, and it helps to have an understanding of how the script validates the user's input. The script finds the first occurance of '<--', and looks to see what follows directly after it. 

```html
<center>
<br><center><b>Level 9</b></center><br><br>Network Security Sam is going down with the ship - he's determined to keep obscuring the password file, no matter how many times people manage to recover it. This time the file is saved in /var/www/hackthissite.org/html/missions/basic/9/.
<br><br>In the last level, however, in my attempt to limit people to using server side includes to display the directory listing to level 8 only, I have mistakenly screwed up somewhere.. there is a way to get the obscured level 9 password. See if you can figure out how...
<br><br>This level seems a lot trickier then it actually is, and it helps to have an understanding of how the script validates the user's input. The script finds the first occurance of '<--', and looks to see what follows directly after it.
<br><br><center><b>Password:</b><br>
						 <form action="/missions/basic/9/index.php" method="post">
						 <input name="password" type="password"><br><br>
						 <input value="submit" type="submit"></form>
</center></center>
```
SO it mentioned there are some sort of filtering script but I don't see any textbox like level 8 but with a little hint that we can use level 8 to get level 9 password 

we can go back to level 8 execute the following command
```html
<!--#exec cmd="ls ../../9"-->
```
This will list the files in level 9 
```text
Hi, index.php p91e283zc3.php!

Your name contains 24 characters.
```
and our file is **p91e283zc3.php**
Now we can go back to level 9 challenge access this file from the browser and we have got our password 
