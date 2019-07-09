# Autodiscover settings hosted on the web

Autodiscover is a mechanism for automatic detection and setup of email server setup by Microsoft Exchange.
Even if you are not using Microsoft Exchange, you can set up for your owned domain by setting up based on DNS settings and Web server.
With Microsoft Exchange compatible email software, you can use this setting to configure your email software automatically.


Although this repository describes the setting of Gmail by Google G Suite,
you can change it to any setting according to the email vendor you use.

[Example of using Amazon Web Services](https://docs.aws.amazon.com/en_us/workmail/latest/adminguide/autodiscover.html)

# Web setup

Please put `autodiscover/autodiscover.xml` under the document root directory on your server.



# DNS setup

You also set up above DNS records

## A or CNAME records

You need to use the hostname of SMTP name, or specified hostname, likes an `autodiscover.yourdomain.com`.

```
autodiscover 300 IN A 127.0.0.1
# Noted: Replace your own server IP
```

OR

```
autodiscover 3600 IN CNAME autodiscover.netlify.com.
```

## SRV records
```
_autodiscover._tcp 3600 IN SRV 10 10 443 autodiscover.example.com.
```

# Enable SSL

You should prepare SSL for autodiscover hostname.


# More specs

Please check these documents for detailed specifications.

[Autodiscover service in Exchange Server (Microsoft Docs)](https://docs.microsoft.com/en-us/exchange/architecture/client-access/autodiscover?view=exchserver-2019)

