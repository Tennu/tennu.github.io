---
layout: plugin
title: Control Plugin
---

This plugin let's you control your bots.

This bot requires the <a href="roles/admin">admin</a> role.

## Config

<p class="none">None</p>

## Commands

All of these commands require the user be an admin for them to perform.

All of these commands require the user be an admin for them to perform.

### !say target message

Has the bot say (via PRIVMSG) the message to the target.

### !act target action

Has the bot act the action to the target.

### !notice target message

Has the bot send a notice to the target

### !ctcp target CtcpType CtcpMessage

Sends a CTCP to the target.

### !join &lt;channel&gt;

Has the bot join the channel. Does not currently work for channels with passwords.

### !part \[&lt;channel&gt;\]

If the channel is not given, the bot will part the current channel.

If you part in a query without giving a channel, the bot will instead
give you the help message for the command.

### !quit \[&lt;reason&gt;\]

Has the bot quit, possibly with the specified reason.

### !nick new-nick

Has the bot change its nickname to the specified nickname.

### !mode target +modes parameters

Has the bot perform the mode changes.

`target` can either be the bot's nickname or a channel.

Works exactly like `/mode` would in your IRC client.

## Exports

None

## Hooks

None