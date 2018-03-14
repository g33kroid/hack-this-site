# Fischer's Animal Products
the challenge is the following 
```text

From: SaveTheWhales

Message: Hello, I was referred to you by a friend who says you know how to hack into computers and web sites
well I was wondering if you could help me out here.
There's this local store who is killing hundreds of animals a day exclusively for the purpose of selling jackets and purses etc out of their skin! I have been to their website and they have an email list for their customers.
I was wondering if you could somehow hack in and send me every email address on that list?
I want to send them a message letting them know of the murder they are wearing.
Just reply to this message with a list of the email addresses.
Please? Their website is at http://www.hackthissite.org/missions/realistic/4/.
Thanks so much!!
```
so the platform is asking me to add my email to the email list 
when we don't pass any parameter it will give error below
```text
Error inserting into table "email"! Email not valid! Please contact an administrator of Fischer's
```
so its clear SQL injection :D lets try to add fake email and extract some data 
