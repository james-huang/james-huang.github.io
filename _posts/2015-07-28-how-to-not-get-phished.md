---
layout:     post
title:      How to not get phished
date:       2015-07-28
summary:    How a (self-proclaimed) seasoned veteran computer expert got phished.
categories: security programming
---


## What is a Phishing?

Phishing is when someone tries to trick you into given them some of your private information, which might include: credit cards, passwords, your social security number. If you have the mindset of “phishing won’t happen to me I am too smart for that nonsense”, think again . It happened to me, so it can happen to you too.

Your social security number and your credit card numbers are annoying to protect because you need to give them out in order to do things like purchasing books or renewing a driver’s license[^credit].
Passwords are also very annoying because you need to create different passwords for different services and they have different rules like there needs to be at least 8 characters and at least 1 symbol and at least 1 number and at least 1 capital letter[^webcomic] and sometimes services won’t support symbols and sometimes they will complain if you put more than 3 sequential numbers in a row and other times it will make your password case insensitive (I’m looking at you Charles Schwab).

This one time I registered an account(Newsflare) and they emailed me my password in plain text. This worries me because web services are supposed to [salt](https://en.wikipedia.org/wiki/Salt_(cryptography)) and [hash](https://en.wikipedia.org/wiki/Hash_function) your password, dropping the plaintext version as soon as they can.

Anyways, here I am with all this important information to protect and everyone else is making my life difficult.



## What does a regular request look like?

![Protectmyid information request](/images/2015-07-28-how-to-not-get-phished/identity-theft-protection.png)

It is hard to distinguish legitimate requests for your sensitive information with the phishing scams. I know for a fact that the above request was legitimate; because someone I know told me *in person* about this identity theft protection tool right before I got his email. I still felt weird giving up my social security number.

Remember: anyone can slap images of logos and locks and certifications onto their website.



## What does a phish look like?

I get an e-mail like this, and I don’t think much of it because I get a lot of confirmation emails about logging from different places or devices. I also recently signed up for a youtube partner account so I go ahead and click the link.

![Phising email](/images/2015-07-28-how-to-not-get-phished/phish-1.png){: style="border:1px solid gray"}

I also don’t think much of the sign in because I have a bunch of different google accounts and I can never keep track of what user Chrome thinks I have swapped to in order to access whatever Google Docs someone has shared.


![Phising site page 1](/images/2015-07-28-how-to-not-get-phished/phish-2.png){: style="border:1px solid gray"}

So I put in my email and password and my spidey senses start tingling as soon as I get to the next page. Phone recovery? What is that? Recovery email? Broken anchor tags? What was the host again? WEBSTYLISTE.SG?


{:.center}
<small>http://webstyliste.sg/youtube.com-gmail/support/5ebd5535d0aacd0674d55177be136d9b/E1.htm</small>
![Phising site page 2](/images/2015-07-28-how-to-not-get-phished/phish-3.png){: style="border:1px solid gray"}


<span class="red">Fuck.</span>

I go back to the previous page to put in my email and a bad password: it doesn't throw an error. I definitely got phished. I am not panicking because I have [two-factor authentication](https://en.wikipedia.org/wiki/Two-factor_authentication) turned on. However, I am very annoyed at the prospect of having to change my password. I really liked my old password because it was the perfect combination of 8 characters with at least 1 symbol and at least 1 number and at least 1 capital letter and it took me a long time to make that up and commit it to muscle memory[^makeup].



## Key takeaways:


### 1. Constant Vigilance

Don't slip up like I did. Always listen to your suspicious spidey senses.

### 2. Look at your domain name before entering sensitive information
* [http://store.steampowered.com/app/287540/](http://store.steampowered.com/app/287540/)
* <span class="blue">http://store.steempowered.com/app/287540/</span>
* <span class="blue">http://store.steampowared.com/app/287540/</span>

Which url will let you buy computer games and which will steal your credit card number?

### 3. Keep your email password unique
Go ahead and use ‘password1’ for both your neopets and reddit account. You don’t care if anyone hacks them and nobody is trying to hack them anyways. On the other hand, email is a gatekeeper to everything important. If you forget a password to another service it will email you a unique link to reset it. If someone compromises your email they have access to everything and you will lose *a lot* of money. By the way, if you are getting email on your phone, put a password on it.

### 4. Enable 2 factor authentication

2-factor authentication meant that some hacker who had my password for a brief moment in time was not able to get into my account because if they tried to log into my Gmail, Google would ask them for a second pin that could only be accessed from my phone.

### 5. Stop asking me to create a username

I get that web services need a unique way to identify who I am. Why can’t you just use my e-mail?  I have too many passwords to remember already, please don’t make me have to remember a bunch of usernames too. [^username]


<br/><br/><br/><br/>

[^credit]: If practice makes perfect then I am perfect at calling Chase to cancel my credit cards by now.
[^webcomic]: I get mad at having to use a symbol and a number and a capital letter because a [webcomic](https://xkcd.com/936/) once told me I didn’t need to.
[^makeup]: The only other equal waste of my time was probably when I was 7 years old and first asked to sign something, and upon realizing I didn’t have a signature, ran home and practiced writing my name in as messy and as unique a way as I could. The result is so messy that it could really be anyone’s signature, and is so unique that I cannot to this day come up with a pair of reasonably similar reproductions.
[^username]: If you are in charge of a company's registration, here is another thing to consider: less boxes to fill in equals more users.