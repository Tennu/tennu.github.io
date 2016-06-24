---
layout: plugin
title: Admin Plugin
---

<p>This plugin let's you administrate your bots.</p>

<h2>Config</h2>

<h3>admins</h3>

<p>This configuration is an array of objects with any number of the following properties</p>

<ul>
    <li>nickname</li>
    <li>username</li>
    <li>hostname</li>
    <li>identifiedas</li>
</ul>

<p>The first three will be converted to a case-insensitive regular expression.</p>

<p>If a user matches the regex for the first three properties (of those that exist) and is
identified or authenticated under the nickname of the <code>identifiedas</code> property, the user
is considered an admin.</p>

<p>For example, <code>{"nickname": "^havvy$", "identifiedas": "havvy"}</code> will only consider a
user with the nickname of exactly <code>havvy</code> and identified to services as <code>havvy</code> is considered
an admin.</p>

<p>Multiple admin objects allow multiple admins. A user only has to match under one object
to be considered an admin.</p>

<h3>admin-commands</h3>

<p>A list of commands that you want to force to be only available for admins. E.g., to make <code>!learn</code> and <code>!forget</code> from the <a href="factoids">factoids</a> plugin only available to admins, you can have the value for this configuration property to be <code>["learn", "forget"]</code>.</p>

<h3>admin-failed-attempt-response</h3>

<p>The <a href="/documentation/api/response">Response</a> to show when a user without permission attempts to use an admin-only command.</p>

<p>Defaults to <code>"Permission Denied"</code>.</p>

<h2>Exports</h2>

<h3>isAdmin(hostmask: Hostmask, opts: optional Object) -> boolean</h3>

<p class="warning">In <code>v3.2</code> the signature was <code>isAdmin(hostmask: Hostmask, customAdmins: [Admin])</code>. In <code>v4.0</code> and higher, that is now <code>isAdmin(hostmask: Hostmask, {customAdmins: [Admin]})</code>

<p>Determines whether the user is an admin.</p>

<h4>Options</h4>

<dl>
    <dt>customAdmins</dt>
    <dd>A list of <code>Admin</code> objects to use as admins for this call (and only this call).</dd>

    <dt>memoizeOver</dt>
    <dd>An object used to memoize over whois requests. Should be something that is shortly lived, like a corresponding <a href="/documentation/api/message-properties">Message</a> that caused you to want to check if somebody is an admin.</dd>
</dl>

<h3>requiresAdmin(fn: Function) -> Function</h3>

<p>Wraps a function making it require admin priviledges to use.</p>

<p>In the case that the use is not an admin, the bot will respond with the <code>admin-failed-attempt-response</code>.</p>