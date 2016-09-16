---
title: Simple Preventative Security Practices for Your Software Organization
date: 2015-06-16 5:00:00 -07:00
tags:
- security
- software
- management
description: A few simple and easy steps to take to improve the security of your team.
---

Your app is following best practices for security. But is your organization?
The following steps and practices should help limit the ways important data or
information could be compromised.

## No Duplicate Passwords

**Do not** use duplicate passwords. Not even for a couple of apps. This seems
like common sense, but just do not do it.

## Use a Password Manager

Instead of using duplicate passwords, use a password manager that can easily
handle generating, storing, and sharing secrets. This means instead of using
duplicate passwords for easy memorization, difficult to guess passwords can be
generated and recalled all from one place. It also means that when you need to
share the Twitter account with the marketing team, you can share the password
without sending it in plain text.

1Password and LastPass are solid options with support for teams.

## Audit Access

Does that contractor who worked on the app eight months ago really need GitHub
access? If not, remove them. It is easy enough to add them back if you need to.

Go through the critical services your software relies upon, and ensure that
only folks who **need** access have access. This means removing folks from
places like AWS, Heroku, GitHub, etc.

While folks may not have bad intentions, decreasing the number of possible
accounts that can be compromised that have access is a great preventative
measure.

## Use 2 Factor Authentication

Too many policies can be a bummer, but security should be taken seriously, and
I think a worthwhile policy is to ensure the folks that do have access to the
services your app relies upon are using 2 factor authentication. This means
that for someone to log into an account, they need the username, password, and
an ephemeral token generated via an authenticator app or sent via text message.

This extra layer of security means that if their password is compromised or
guessed, the attacker would need access to their phone or authentication
device.

Using a service that [does not support 2 factor
authentication](https://twofactorauth.org/)? Reach out and request it. Let them
know that it is important to your organization.

## Encrypt Hard Drives

On OS X this feature is called FileVault. Folks with sensitive information on
their computer’s storage should have it enabled. This means that the contents
of the storage cannot be accessed unless the encryption key is known.

## Conclusion

Take the time today, or this week, and work with your organization to setup
these tools and follow these practices. They are easy enough to do, and they
may save you some serious headaches in the future.
