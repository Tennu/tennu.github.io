---
layout: document
title: Documentation
---

## Tennu Core

| Struct | Description |
| ------ | ----------- |
| [Tennu](tennu) | God object of an IRC connection. |
| [Configuration](configuration) | The base configuration structure passed to Tennu to create a Tennu object |
| [Configuration Extensions](configuration-extensions) | A comprehensive list of extra properties other plugins add to the configuration object. |
| [Message](message-properties) | The structure passed for each IRC message event. |
| [Command](command-properties) | The structure passed for each command. |
| [Response](response) | The return value of your handlers. |
| [Plugin Factory](plugin-factory) | The object used for creating plugins. Holds an init function that creates a plugin and static plugin metadata. |
| [Plugin](plugin) | The object returned by a plugin factory. |

## IRC

| Struct | Description |
| ------ | ----------- |
| ChannelName | An identifier of a channel. A case insensitive string that starts with a channel type character, generally a "#". Does not contain whitespace. |
| NickName | An identifier of a user. A case insensitive string. Does not contain whitespace or start with a number. |
| HostMask | An identifier of a user. A string of NickName!UserName@HostName.
| [Mode](mode) | A mode change of a user or channel. |
| [isupport](isupport) | A parsed 005 handler. |


## Per-Plugin

| Plugin | Struct | Description |
| ------ | ------ | ----------- |
| [Admin](./plugins/admin) | [Administrator](administrator) | Description of an admin for your bot, to be placed in the list of admins. |
| [Factoids](./plugins/factoids) | [Factoid](factoid) | Internal struct. |