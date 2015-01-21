---
layout: plugin
title: Admin Plugin
---
# Admin Plugin

This plugin let's you administrate your bots.

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

## Commands

## Exports

### isAdmin(hostmask: Hostmask): boolean

Determines whether the user is an admin.

### requiresAdmin(fn: Function): Function

Wraps a function making it require admin priviledges to use.

In the case that the use is not an admin, the bot will say 'Permission denied.'.

## Hooks

None