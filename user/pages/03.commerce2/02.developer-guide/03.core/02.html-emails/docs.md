---
title: Sending HTML emails
taxonomy:
    category: docs
---

! We need some screenshots for this section! Feel free to follow the *edit this page* link and contribute.

## Swift Mailer module

The [Swift Mailer](https://www.drupal.org/project/swiftmailer) module can be used with Commerce in order to send HTML emails. The Swift Mailer library has also been proposed to be added to core to deprecate most of Drupal core's mailsystem. More can be found https://www.drupal.org/node/1803948. Note that swiftmailer has been retired and is no longer supported. 

## Installation

Swift Mailer depends on the Mail System module.  Install both using Composer:

```
composer require drupal/swiftmailer
```

Then enable the Swift Mailer module.  This will automatically enable the Mail System module as well.

## Configuration

First, configure the Mail System module at `/admin/config/system/mailsystem`.

To have Swift Mailer handle all email for your site, set both the Formatter and Sender to "Swift Mailer."

Next, configure the Swift Mailer settings at `/admin/config/swiftmailer/transport`.

Be sure to select the mail transport mechanism to use.

For the highest mail delivery rate, consider using SMTP instead of the native PHP mail function.

Next, click the "Messages" tab.

Be sure to set the "Message format" to "HTML" and then click "Save configuration."  Adjust other settings as desired.

Now, click the "Test" tab.

Send yourself a test email to verify that everything is working.

## Debugging emails

The Drupal.org documentation handbook has a great article for working with email in a development and testing environment: [https://www.drupal.org/docs/develop/local-server-setup/managing-mail-handling-for-development-or-testing](https://www.drupal.org/docs/develop/local-server-setup/managing-mail-handling-for-development-or-testing)

The Drupal Commerce team recommends using [Mailhog](https://github.com/mailhog/MailHog) for local email testing and development. [DrupalVM will send emails to it by default](http://docs.drupalvm.com/en/latest/extras/mailhog/) and it is easily installed locally or through a [Docker container](https://hub.docker.com/r/mailhog/mailhog/).
