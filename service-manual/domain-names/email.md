---
layout: category-index
title: Handling email
category: domain-names
type: category-index
audience:
  primary: service-managers, web-ops, tech-archs
  secondary: 
status: draft
phases:
  - discovery
  - alpha
  - beta
  - live
breadcrumbs:
  -
    title: Home
    url: /service-manual
  -
    title: Where services live on the web
    url: /service-manual/domain-names
---

## Handling email

Emails to users of your service should be sent from a human-monitored email address that originates from the
domain servicename.service.gov.uk (and not the dept/agency or any other domain name). Users are interacting
with the service and that is where they will expect communications to come from.

### Email security

Internet email provides a low level of confidentiality and integrity protection for communications. When planning to use 
email to communicate with users, it is important to think about the security requirements of your application and to 
consider the business risks inherent in transmitting information via email or assuming that an email originates from the 
sender address.

### Getting emails to users

In order to protect users from spam email providers put in place a variety of checks. It is often a good idea
to use a trusted specialist third-party to dispatch email as they will have tools and expertise to help ensure
that you pass those checks. As a minimum you should:

* ensure there is a [mail exchanger (MX) record](http://en.wikipedia.org/wiki/MX_record) set up for the domain from which you send email
* enable [Sender Policy Framework (SPF)](http://en.wikipedia.org/wiki/Sender_Policy_Framework) on the sending domain
* consider using [Domain Keys Identified Mail (DKIM)](http://en.wikipedia.org/wiki/DomainKeys_Identified_Mail) on the sending domain, it can provide additional guarantees about message delivery and help recipients to distinguish genuine mail from forgery

Before releasing your service you should test your email delivery. As a minimum you should use your service with
registered email addresses from a range of popular email providers and ensure that emails arrive as you expect.

If you created your own outbound mail infrastructure, you should also verify that you did not inadvertently enable it to 
receive email or configure it as an [open mail relay](http://en.wikipedia.org/wiki/Open_mail_relay). 

### Receiving email

Incoming emails to email addresses in the service domain will need to be received from the Internet and delivered to 
mailboxes where a human can read them.

Safe handling of inbound email requires expertise and careful configuration to avoid common mistakes. It is our recommendation that, 
when possible, you use a specialist supplier to accept email from the Internet. 

You should develop an email handling policy, including the following points:

* the receiving mail server must not be an open mail relay, which would allow it to be a conduit for [Spam email](http://en.wikipedia.org/wiki/Email_spam) and may result in the addition of your mail server to [blacklists](http://kb.mailchimp.com/article/what-are-blacklists)
* consider enabling automated rejection of malware and viruses
* consider performing DKIM and SPF validation on received emails to reduce the quantity of email received with forged sender addresses
* consider enabling the automated rejection of Spam emails

Although the final destination of the email may be on a server that you control, there are many services which can perform 
these types of automated filtering before the email arrives at your server.


