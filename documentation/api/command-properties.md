---
title: Command Properties
layout: document
---

## Command Properties

A `Command` is a `Message` with all PRIVMSG properties, with the 'command' property repurposed and an additional 'args' property.

* args     - Array of the words following the command. E.g., with `!foo x y z`, will be `["x", "y", "z"]`.
* channel  - In the case of a query, the channel is the nickname of the user who sent the message.
* command  - Message command type. For example, 'privmsg' or 'nick'.
* isQuery  - Whether or not the message was sent directly to you, or to a channel.
* message  - The message, stripped of mIRC color codes and trimmed.
* params   - Array of sent parameters.
* prefix   - The prefix is either a hostmask of the format "nickname!username@hostname", or the server you are connected to.
* tags     - IRC3 tags sent with message.