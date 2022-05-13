---
layout: post
title:  "How To Use Alias Emails"
date:   2022-04-27 00:00:00 -0500
categories: privacy
author: Operation Privacy
image: img/blog/aliases.gif
featured: true
---
You should be very selective in using your true email address. Instead you should have a strategy of providing junk alias addresses that forward emails to your primary email address. You should be able to produce them quickly and you should not be logging into 10 places to manage your email strategy.

<br/>

**Consider this:** A hacker needs 2 pieces of information to login to any of your accounts. An email and a password. The email is easy to get for most people and we (should) be using password managers to create unique passwords for everything. But why not have a similar strategy to create unique emails for everything as well? This makes it harder for hackers to guess email address as they essentially have 2 unknown fields to start off with. 

<br/>

This will also make you more private, minimize and control spam and keep your exposure contained with data breaches.  
<br/>

### Glossary Of Terms Used

|   |   |
|---|---|
|**Alias**|An email address that does not have an inbox (or email account) associated with it. It simply forwards any email received to another email address|
|**Catch-All:**|Putting in any value before the "@" or your full domain in an email address and having it forward to your personal email|
|**Sub-domain**|The part before the domain. the "*mail*" in *mail.example.com*|
|**Name Server**|DNS or the service that provides translation to an IP address. It is usually the place that hosts your domain name but you can change it *(like CloudFlare, namecheap, goDaddy, Google Domains)*|
|-|-|

## Email Alias Guidlines.
1. Use a catch-all email address. (SimpleLogin.co). It's $2/m for unlimied email aliases. The free version is limited to 15 aliases.
1. Use a uniqe email address for each online service. For example, if your domain is JohnDoe.com, your aliases should look like:
    - `twitter@JohnDoe.com`
    - `linkedin@JohnDoe.com`
    - `github@JohnDoe.com` (GitHub does not allow the word "GitHub" in the email address. So use "git" instead)
1. A better strategy is to use a subdomain for aliases with the catch-all option.
    - `anything@mail.JohnDoe.com`
    - `anything@email.JohnDoe.com`
    - `spokeo1@optout.JohnDoe.com`

> Note: You can create unlimited subdomains with a paid simplelogin account.

> Alternatively, you can also create unlimited subdomains without simplelogin at your DNS provider. Nameservers like CloudFlare and NameCheap will allow free catch-all email forwarding of the domain or subdomain. But you will lose the ability to reply to that email and mask that alias with this option.

<br/>

## Long Term Email Guidlines

Here are some guidlines for long term email usage:
1. Your primary email address should be with a provider that offers end-to-end **encryption** (like ProtonMail).
1. You should **own** your own domain and use that as your primary email address (like: JohnSmith.com).
    - **Benefits:** This way you can always change your underlying provider (e.g. from gmail to protonmail), without changing your email address and letting everyone know your new email. You simply change your DNS MX records to point to the new email provider.
1. All websites that require an email to register should be provided with a **unique** alias that forwards to your primary account. This way you mask every service.
    - **Benefits:** If they spread your email address to their partners, you can always block that unique email address. If they get breached, then you only compromise one specific email alias. (e.g. If you start getting spam on instagram@mail.JohnDoe.com, you can be sure Instagram shared that email with their advertisers or they got breached. You can simply block that email alias without blocking email from any other service since each service has a unique email address)

<br/>

## Pulling The Trigger

As with every new technology strategy, ease yourself into this. Take your time. It took me about 2 years to fully adopt it.

1. Start with aquiring your personal domain name or any domain name.
1. Host it at a provider you trust (ProtonMail).
1. Set up email forwarding on a subdomain (SimpleLogin.co)
1. Start transitioning your friends, family and colleagues to your new primary email address.
1. Start changing the email address on all important accounts (Banks, gov, social media).
1. Every new service you open an account with, use your alias strategy (service.name123@mail.domain.com)
1. Save everything (email/password/other info) in your password manager.
1. Create a folder in your primary email address provider for the aliases so that they don't clutter the inbox. Create a rule that sends anything that ends with @mail.domain.com to your Alias folder *(optional)*  
<br/>

## Advanced Strategy
If you're in multiple data breaches and someone can identify one of your aliases, then with this strategy, you have created a pattern to identify the rest of your aliases. E.g. if I know git@mail.JohnDoe.com is your alias, then I can run a search for "`@mail.JohnDoe.com`" to possibly find "facebook`@mail.JohnDoe.com`" and know that's you as well.  
<br/>

So I will often use random aliases generated by SimpleLogin with their own domain endings to be completely random and anonymous for certain accounts. You can also buy multiple random but legit looking domain names for $8/y to mix it up.  
<br/>

---
<br/>
In time, this will clean up a lot of email clutter in your life while keeping you safe and private in public databases.