---
layout: document
title: Documentation
---

## Built-in Plugins

<!-- This table is also in /plugins/index and any updates here should be updated there too. -->
<table>
  <tr>
    <th>Plugin</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><a href="action">action</a></td>
    <td>Command the Client to interact with the server.</td>
  </tr>
  <tr>
    <td><a href="channel">channel</a></td>
    <td>[<b>Stub</b>] Query information about channels.</td>
  </tr>
  <tr>
    <td><a href="commands">commands</a></td>
    <td>Parses commands from <code>privmsg</code>s and emits them as events.</td>
  </tr>
  <tr>
    <td><a href="config">config</a></td>
    <td>Configuration including <code>configDefaults</code> and the <code>config</code> method</td>
  </tr>
  <tr>
    <td><a href="ctcp">ctcp</a></td>
    <td>A plugin that does not currently exist, but will in the future. Handles the Client-to-Client-Protocol things, including providing a repsonse to the <code>version</code> ctcp request.</td>
  </tr>
  <tr>
    <td><a href="help">help</a></td>
    <td>Provides <code>!help</code> and <code>!commands</code></td>
  </tr>
  <tr>
    <td><a href="messages">messages</a></td>
    <td>Listens to the <code>IrcSocket</code>, turning each line into a <a href="/documentation/api/message-properties">message</a> event.</td>
  </tr>
  <tr>
    <td><a href="self">self</a></td>
    <td>Information about the client. Currently just the <code>nickname</code> function that is also accessible on the <code>Client</code>.</td>
  </tr>
  <tr>
    <td><a href="server">server</a></td>
    <td>Query information about the server. Currently just the <code>ISUPPORT</code> info.</td>
  </tr>
  <tr>
    <td><a href="subscriber">subscriber</a></td>
    <td>Provides the <code>handlers</code> plugin hook.</td>
  </tr>
  <tr>
    <td><a href="user">user</a></td>
    <td>[<b>Stub</b>] Query information about users. Currently just who a user is identifed as, if anybody.</td>
  </tr>
</table>

## Tennu Core

| Struct | Description |
| ------ | ----------- |
| [Client](client) | God object of an IRC connection. |
| [Configuration](configuration) | The base configuration structure passed to Tennu to create a Tennu object |
| [Logger](logger) | Object with various logging methods. |
| [Message](message-properties) | The structure passed for each IRC message event. |
| [Command](command-properties) | The structure passed for each command. |
| [Response](response) | The return value of your handlers. |
| [Plugin Factory](plugin-factory) | The object used for creating plugins. Holds an init function that creates a plugin plus static plugin metadata. |
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