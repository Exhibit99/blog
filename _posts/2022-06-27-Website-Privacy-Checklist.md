---
layout: post
title:  "Website Privacy Checklist"
date:   2023-06-29 01:09:00 -0500
categories: security
image: img/blog/scraping-protection.gif
author: Operation Privacy
---



# Email Protection



## Encoding
## Random Tag Insersion
## Reversing Characters


> Disclaimer: While all these techniques are well known and smart scrapers will pick these up easily, it still recommended to implement them for 2 reasons.
> 1. There are a lot of dumb scrapers out there
> 2. A combination of techniques often works, confuses bots or wastes their time



# Archive Protection


archive.org

```
User-agent: ia_archiver
Disallow: /
```


# Caching Prevention

google
bing

```
<meta name="robots" content="noindex,nofollow"/>
```


```
<html lang="en" translate="no"> 
```

# Web Application Firewall

# block bots

```
User-agent: ia_archiver
Disallow: /

User-agent: *
Disallow: /
```


# captcha


# Getting Back at Stubborn Scrapers

If you have an annoying bot or service continuously visting and scraping your website and you've done everything you can to mitigate it, you can try this technique.

Since it's downloading all your files, let it download something extremely huge. Like a 10 GB file over and over. It will waste it's bandwidth and space to a point that it will get noticed fairly quickly by the owner and they will remove your website from their list.

You may be thinking if someone is downloading a 10GB file from your site, it's also wasting your hosting bandwidth. Well, don't host it on your site. This is where the trick comes in.

A 301 redirect is when you instruct the user or browser that the link they are trying to access has temporarily or permanently moved to another location.

So when they scrape a certain link on your website like example.com/download , you can redirect it to a publically available file on the internet that is over 10GB in size.

You can do this on your firewall or WAF. Some scrapers ignore redirects (301/302) but a lot of them don't. It's worth a try. I've had many scrapers give up after I did that.

To find a large file, it needs to be downloaded with a single click and not behind a login or another redirect page. Search for something like "large file download test" and link one of those files in your redirect.


---

### Glossary Of Terms Used

|   |   |
|---|---|
|**WAF**|Web Application Firewall|
|**WAF**|Web Application Firewall|
|   |   |