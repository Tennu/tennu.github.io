---
layout: plugin
title: Admin Plugin
---

<p>This plugin let's you administrate your bots.</p>

## Config

### admins

This configuration is an array of objects with any number of the following properties:

* nickname
* username
* hostname
* identifiedas

The first three will be converted to a case-insensitive regular expression.

If a user matches the regex for the first three properties (of those that exist) and is
identified or authenticated under the nickname of the `identifiedas` property, the user
is considered an admin.

For example, `{"nickname": "^havvy$", "identifiedas": "havvy"}` will only consider a
user with the nickname of exactly 'havvy' and identified to services as havvy is considered
an admin.

Multiple admin objects allow multiple admins. A user only has to match under one object
to be considered an admin.

<h3>admin-commands</h3>

<p>A list of commands that you want to force to be only available for admins. E.g., to make <code>!learn</code> and <code>!forget</code> from the <a href="factoids">factoids</a> plugin only available to admins, you can have the value for this configuration property to be <code>["learn", "forget"]</code>.</p>

<h3>admin-failed-attempt-response</h3>

<p>The <a href="/documentation/api/response">Response</a> to show when a user without permission attempts to use an admin-only command.</p>

<p>Defaults to <code>"Permission Denied"</code>.</p>

## Exports

### isAdmin(hostmask: Hostmask): boolean

Determines whether the user is an admin.

### requiresAdmin(fn: Function): Function

Wraps a function making it require admin priviledges to use.

In the case that the use is not an admin, the bot will say 'Permission denied.'.