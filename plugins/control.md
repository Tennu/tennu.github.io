---
layout: plugin
title: Control Plugin
---

This plugin lets you control your bots.

This bot requires the <a href="roles/admin">admin</a> plugin.

## Config

<p class="none">None</p>

## Commands

All of these commands require the user be an admin for them to perform.

<p>The <i>target</i> must be a nickname, channel, or one of <code>&lt;reply<&gt;</code> or <code>&lt;query&gt;</code>.</p>

<p><code>&lt;reply<&gt;</code> makes the bot's command happen where the command was given. <code>&lt;query&gt;</code> forces the command to happen specifically to the nickname that triggered the command. While not useful on their own, these are useful when combined with the <a href="dynamic-alias">dynamic-alias</a> plugin.</p>

<h3 id="!say">!say &lt;target&gt; &lt;message&gt;</h3>

<p>Has the bot say (via PRIVMSG) the message to the target.</p>

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