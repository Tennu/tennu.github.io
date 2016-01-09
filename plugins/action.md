---
layout: plugin
title: Action Plugin
---

<p class="built-in">This plugin is built-in.</p>

This plugin provides ways to communicate with the server. All of its exports properties are available on the [Client](/documentation/api/client).

## Commands

None

## Exports

<dl>
    <dt>raw(message...: String)</dt>
    <dd>Send a raw message to the server. Useful for sending messages that don't have functions defined in this plugin. If there are multiple arguments, they'll be joined together with a space.</dd>

    <dt>rawf(format: String, args...: String)</dt>
    <dd>A convenience function for sending a [util formatted string](//nodejs.org/api/util.html#util_util_format_format).</dd>

    <dt>act(target: Target, action: String | [String])</dt>
    <dd>
        <p>Commit an action to the target. Basically what your client's <code>/me</code> does.</p>

        <p>Example: <code>client.act("#chan", "plays the ukelele.");</code></p>
    </dd>

    <dt>ctcp(target: Target, tag: CtcpTag, body: undefined | String| [String])</dt>
    <dd>[<b>Deprecated</b>] Send a CTCP request or response to the target.</dd>

    <dt>ctcpRequest(target: Target, tag: CtcpTag, body: undefined | String | [String])</dt>
    <dd>Send a CTCP request to the target.</dd>

    <dt>ctcpResponse(target: Nickname, type: CtcpTag, body: undefined | String | [String])</dt>
    <dd>Send a CTCP response to the target.</dd>

    <dt>join(channel: ChannelName): Promise&lt;JoinResponse></dt>
    <dd>Attempt to join channel. Returns a promise of the results, though the actually returned object is unstable.</dd>

    <dt>join(channel: ChannelName, password: String): Promise&lt;JoinResponse></dt>
    <dd>As prior, but sends the password to the channel for channels that have mode +k.</dd>

    <dt>kick(channel: ChanelName, nick: NickName)</dt>
    <dd>Attempt to kick user with specified nick from the channel.</dd>

    <dt>kick(channel: ChannelName, nick: NickName, reason: String)</dt>
    <dd>As prior, but kicks with the specified reason.</dd>

    <dt>mode(target: Target, plus: String, minus: String, params: [String])</dt>
    <dd>
        <p>Attempt to change modes on the target.</p>

        <p>Ex: <code>client.mode(client.nickname(), "B", "", [])</code></p>
    </dd>

    <dt>nick(newNick: NickName)</dt>
    <dd>Attempt to change the bots nickname.</dd>

    <dt id="command-notice">notice(target: Target, message: String | [String])</dt>
    <dd>Send a notice to the target.</dd>

    <dt>part(channel: ChannelName)</dt>
    <dd>Cause the bot to leave the channel.</dd>

    <dt>part(channel: ChannelName, reason: String)</dt>
    <dd>Cause the bot to leave the channel with the specified reason.</dd>

    <dt>quit()</dt>
    <dd>Cause the bot to quit.</dd>

    <dt>quit(reason: String)</dt>
    <dd>
        <p>Cause the bot to quit with the specified reason.</p>

        <p>Note: The reason is ignored on many servers if the bot quits within the first minute.</p>
    </dd>

    <dt>respond(<a href="http://tennu.github.io/documentation/api/response">response</a>, <a href="http://tennu.github.io/documentation/api/command-properties">command</a>)</dt>
    <dd>Send a response to the target</dd>
    <dd>command is required because sometimes a response will need more information to be usable (IE: the nickname or channel)</dd>

    <dt>say(target: Target, message: String | [String])</dt>
    <dd>Send a message to the target.</dd>

    <dt>userhost(user: Nickname)</dt>
    <dd>Gets the userhost of the user.</dd>

    <dt>userhost(users: [Nickname])</dt>
    <dd>Gets the userhosts of the users.</dd>

    <dt>who(channel: ChannelName)</dt>
    <dd>Get the <code>WHO</code> data of the channel.</dd>

    <dt>whois(user: NickName)</dt>
    <dd>Get the <code>WHOIS</code> data of the user.</dd>
</dl>

## Module Hooks

None