+++
author = "Mark Smith"
categories = ["HMail"]
date = "2017-01-25T13:05:31+00:00"
draft = true
title = "Adding SSL to HMail with SSL For Free"

+++
# What is SSL For Free

I<span style="letter-spacing: 0.01em;"> run a private mail server on using a t1.micro Windows server on AWS using HMail as the mail server. This serves my @azert.co.uk emails and so far has proved to be extremely reliable, despite the small size of the server. I was running an m3.medium at one stage but it cost a fortune so that didn't last very long!</span>

One of the prerequisites for the mail server I had was SSL support, for obvious reasons of security, but I didn't want to spend even more money on certificates. This is where [SSL For Free](https://www.sslforfree.com/) comes in. SSL For Free is essentially a web interface over [Lets Encrypt](https://letsencrypt.org/) that simplifies creating SSL certificates somewhat. There is a bit of a catch though, while the certificates are free, you do need to renew them, currently this is every 90 days. When you setup an SSL For Free account they will email you in advance of the expiry, so you can take action, there are also programs available that will auto renew for you such as [LetsEncrypt Win Simple](https://github.com/Lone-Coder/letsencrypt-win-simple). Win Simple will also perform all certificate generation etc automatically, so if you can, I would advise using that, unfortunately I couldn't use this as my www.azert.co.uk address points to this site and I didn't want to pollute the site with ACME validation pages (more on this later).

# Setting Up SSL For Free

Firstly navigate to [SSL For Free](https://www.sslforfree.com/) and setup an account, this will then be used to email you for notifications of expiry & you can renew your existing certificates without having to repeat the below steps.

# Validating You Own The Domain

# Copying To Your Mail Server

Now you have your certificate & bundle files log into your mail server and save them somewhere HMail can access them

# Renewing

When you get the email advising you to renew, log into [SSL For Free](https://www.sslforfree.com/), you will then be taken to a page showing you existing certificates

![](/uploads/2017/01/25/SSL-certs.PNG)

Click renew and follow the steps taken earlier to validate your certificate, once re validated you won't need to take any more steps, if you have let it expire, you will need to follow the steps again to create the certificate chain and copy to your mail server.