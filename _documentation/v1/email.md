---
title: Emails
description: Legacy documentation for Kimai 1
permalink: /v1/email.html
url_v2: /documentation/emails.html
slug: v1-email
layout: v1
---

Currently Kimai only uses email to send users an email if they have forgotten their password.  It is also currently only implemented for the kimai_auth authenticator.  This is reasonable as the other authentication methods do not allow Kimai to change passwords, e.g. LDAP user must go to the LDAP administrator if they forget their password.

## Configuration

Currently configuring email requires the use of the ``includes/autoconf.php`` file and the configuration is performed during installation.  The values can be changed there later if necessary. 

```php
$mail_transport = "sendmail";
$smtp_name = "smtp.example.org";
$smtp_host = "smtp.example.org";
$smtp_port = "465";
$smtp_auth = "login";
$smtp_user = "user@example.org";
$smtp_pass = "password";
$smtp_ssl = "ssl";
```

Set the parameters according to the email documentation below.

## Email Configuration

### Configuration-parameters

* **mail_transport:** This defines the Zend Mail transport mechanism used.  Default is **sendmail** (requires no further configuration).  **smtp** requires the following variables to be set as required by your smtp server
* **smtp_name:** The DNS name of your smtp server
* **smtp_host:** The DNS or IP address or your SMTP Server
* **smtp_port:** The port that your smtp server supports (examples: 25, 465, 587)
* **smtp_auth:** The authentication mechanism to use with the smtp server. **plain**, **login** or **crammd5**
* **smtp_user:** The user or account to authenticate to the smtp server
* **smtp_pass:** The passrord for the user account to authenticate to the smtp server
* **smtp_ssl:** SSL Support for the email server **ssl**: the connection is ssl from the start.  **tls**: the STARTTLS directive is sent to the smtp server after the connection is established

