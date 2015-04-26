---
layout: plugin
title: User Plugin
---

# User Plugin

This plugin is built-in.

This plugin provides utilities for determining information about users.

## Commands

None

## Exports

### isIdentifiedAs(nickname: string, accountname: string): Promise&lt;boolean&gt;

Determines whether the user at the specified nickname is identified to
the given account name.

This is true if one of the following is true:

1. The user is identified and the nickname they are using is registered to them.
2. The user is identified and the accountname is their accountname.

## Plugin Hooks

None