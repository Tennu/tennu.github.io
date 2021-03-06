---
title: Message Properties
layout: document
---

## Message Properties

Note: If you would like to improve Tennu, adding message extensions is easy.

### All Messages

* prefix     - The prefix is either a hostmask of the format `nickname!username@hostname`, or the server you are connected to.
* command    - Message command type. For example, 'privmsg' or 'nick'.
* params     - Array of sent parameters.
* tags       - IRC3 tags sent with message.

### Messages With Hostmask Prefixes

If the message has a hostmask as a prefix, then the `hostmask` property will
be set to an object with three properties:

* nickname
* username
* hostname

Otherwise, this property will be null.

### `nickname` Property

Most messages have a `nickname` property.

For messages that have a hostmask as a prefix, the `nickname` is an alias to `message.hostmask.nickname`.

### `channel` Property

Messages that happen in a specific channel have a `channel` property.

The channel is normalized to lower case.

### `replyname` Property

Numerics that are listed on this article have this property. It is the name given to the numeric
by [alien.net.au](https:https://www.alien.net.au/irc/irc2numerics.html). These messages are also emitted
by the value of their reply name.

### PRIVMSG and NOTICE

* isQuery - Whether or not the message was sent directly to you, or to a channel.
* channel - In the case of a query, the channel is the nickname of the user who sent the message.
* message - The message, stripped of mIRC color codes and trimmed.

### JOIN

* No additional properties.

### PART and QUIT

* reason - The user-given reason for the action.

### KICK

* kicked - The user who was kicked.
* kicker - The user who performed the kick.

### NICK

* old - The nickname the user was using.
* new - The nickname the user is now using.


### MODE

* modestring - Unparsed mode changes without arguments.
* args - The arguments to modes that have arguments.
* modes - [**Unstable**] Semi-correct parsing of modes.

### 307

* replyname - RPL_WHOISREGNICK

### 310

* replyname - RPL_WHOISHELPOP

### 311

* replyname - RPL_WHOISUSER
* nickname - Nickname of user
* username - Username of user
* hostname - Hostname of user
* realname - Realname (or gecos) of user
* hostmask - Hostmask of user

Note: The prefix is the server you are on.

### 312

* replyname - RPL_WHOISSERVER
* server - Server that the user is on.
* serverInfo - Arbitrary information about the server.

### 313

* replyname - RPL_WHOISOPERATOR
* nickname - Nickname of user
* permissions - Arbitrary IRC OP permissions of user.

### 317

* replyname - RPL_WHOISIDLE
* seconds - Integral number of seconds since user went idle.
* since - Unix timestamp of last message sent by user


### 318

* replyname - RPL_ENDOFWHOIS

### 319

* replyname - RPL_WHOISCHANNELS

Note: There may eventually be a channels property. For now, you can
get them at message.params[2]. They have a format of:

```
<user power sigil>?<channel type sigil><channel name>
```

### 330

* replyname - RPL_WHOISLOGGEDIN
* identifiedas - Services nickname the user is identified to.

### 332

* replyname - RPL_TOPIC
* topic - The topic.

### 333

* replyname - RPL_TOPICWHOTIME
* who - Nickname of user who last set topic.
* timestamp - Unix timestamp of when the topic was last set.

### 335

* replyname - RPL_WHOISBOT

### 353

* replyname = RPL_NAMREPLY (not a typo)
* nicknames - [**Unstable**] Partial list of nicknames the user is in. May have prefix.

These get sent in batches. We do not currently use any IRCv3
extensions, so the prefix only shows the users highest mode.
This will eventually change to show all modes and the whole hostmask.

### 366

* replyname - RPL_ENDOFNAMES

### 378

* replyname - RPL_WHOISHOST
* hostmask - Unparsed hostmask of the user.
* ip - Unparsed IP of the user.

### 401

* replyname - ERR_NOSUCHNICK

### 403

* replyname - ERR_NOSUCHCHANNEL;

### 405

* replyname - ERR_TOOMANYCHANNELS;

### 421

* replyname - ERR_UNKNOWNCOMMAND;
* unknownCommand - Command name that the client tried to perform.

### 437

* replyname - ERR_UNAVAILRESOURCE
* channel - Resource that is unavailable.
* nickname - Resource that is unavailable.
* resource - Resource that is unavailable.

In the future, only one of `channel` or `nickname` will be set.

### 461

* replyname - ERR_NEEDMOREPARAMS;
* command - Command sent with insuffient parameters.

### 471

* replyname - ERR_CHANNELISFULL;

### 473

* replyname - ERR_INVITEONLYCHAN;

### 474

* replyname - ERR_BANNEDFROMCHAN;

### 475

* replyname - ERR_BADCHANNELKEY;

### 477

* replyname - ERR_NEEDREGGEDNICK;

### 489

* replyname - ERR_SECUREONLYCHAN;

### 520

* replyname - ERR_OPERONLY;

### 671

* replyname - RPL_WHOISSECURE
