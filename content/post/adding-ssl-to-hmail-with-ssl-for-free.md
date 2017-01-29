+++
author = "Mark Smith"
categories = ["HMail"]
date = "2017-01-25T13:05:31+00:00"
title = "Adding SSL to HMail with SSL For Free"

+++
# What is SSL For Free?

I<span style="letter-spacing: 0.01em;"> run a private mail server on using a t1.micro Windows server on AWS using HMail as the mail server. This serves my @azert.co.uk emails and so far has proved to be extremely reliable, despite the small size of the server. I was running an m3.medium at one stage but it cost a fortune so that didn't last very long!</span>

One of the prerequisites for the mail server I had was SSL support, for obvious reasons of security, but I didn't want to spend even more money on certificates. This is where [SSL For Free](https://www.sslforfree.com/) comes in. SSL For Free is essentially a web interface over [Lets Encrypt](https://letsencrypt.org/) that simplifies creating SSL certificates somewhat. There is a bit of a catch though, while the certificates are free, you do need to renew them, currently this is every 90 days. When you setup an SSL For Free account they will email you in advance of the expiry, so you can take action, there are also programs available that will auto renew for you such as [LetsEncrypt Win Simple](https://github.com/Lone-Coder/letsencrypt-win-simple). Win Simple will also perform all certificate generation etc automatically, so if you can, I would advise using that, unfortunately I couldn't use this as my www.azert.co.uk address points to this site and I didn't want to pollute the site with ACME validation pages (more on this later).

# Setting Up SSL For Free

Firstly navigate to [SSL For Free](https://www.sslforfree.com/) and setup an account, this will then be used to email you for notifications of expiry & you can renew your existing certificates without having to repeat the below steps.

Once you have an account, go to the homepage and enter the domain you wish to setup with SSL.

![](/uploads/2017/01/29/Setup-Domain.PNG)

# Validating You Own The Domain

![](/uploads/2017/01/29/Validation-options.PNG)

When you click 'Create Free SSL Certificate' you will be taken to the above page. There are 3 options available, each with a description. If you are able to use LetsEncrypt Win Simple then just ignore these steps and use it, it's by far the easiest option. For this guide I used the 3rd option as I couldn't use the manual verification option on my server and had access to the dns through Route 53, provided by Amazon.

![](/uploads/2017/01/29/Manually%20verify.PNG)

Once you have verified you own the domain carry on.

# Copying To Your Mail Server

Now you have verified you will be taken to a screen with 3 text areas, each representing a different certificate:

*   Certificate
*   Private Key
*   CA Bundle

On your Mail Server you will need to create 2 files:

*   private.key
*   bundle.crt

You can call them anything but this keeps their purpose clear.

In private.key copy the Private Key text area contents into the file and save.

In the bundle.crt you will need to copy the entire contents of the text areas in order, to create a [certificate chain](https://support.dnsimple.com/articles/what-is-ssl-certificate-chain/) without this chain of trust the LetsEcnrypt certificates will not validate. The order they should appear in bundle.crt is:

*   Private Key
*   Certificate
*   CA Bundle

The final step is to setup hMail to use these certificate files.

# hMail SSL Setup

![](/uploads/2017/01/29/SSLSetup.PNG)

Open hMail admin and go to Advanced -> SSL Certificates and create a new certificate giving it any name you wish. In the Certificate File field then select the bundle.crt file you created earlier. Then in the Private key file field select the private.key file you also created and click **Save**.

Now you will need to setup the Ports to reference the new Certificate you have created within hMail.

![](/uploads/2017/01/29/PortSetup.PNG)

Staying in the Advanced section, open **TCP/IP ports** and for each select SSL/TLS and choose the certifacte you have created. Click **Save** for each one.

THe final step is to test it, go to Utilities -> Diagnostics and ensure that connectivity can be achieved.

# Troubleshooting

To test your setup and where you may have gone wrong the following are some useful tools:

[MxLookup](http://mxtoolbox.com/) - used for testing your domain setup & forwarding etc is correct

[SSLChecker](https://www.sslshopper.com/ssl-checker.html) - to validate your ssl certs

[OpenSSL WIndows](http://slproweb.com/products/Win32OpenSSL.html) - diagnostics tool I found useful when diagnosing why the SSLForFree certificate wasn't validating (it needed the certificate chain)

# Renewing

When you get the email advising you to renew, log into [SSL For Free](https://www.sslforfree.com/), you will then be taken to a page showing you existing certificates

![](/uploads/2017/01/25/SSL-certs.PNG)

Click renew and follow the steps taken earlier to validate your certificate, once re validated you won't need to take any more steps, if you have let it expire, you will need to follow the steps again to create the certificate chain and copy to your mail server.

#Finally

If you found this useful or have any further points to add or if I've missed anything, leave a comment below and I'll get back to you.