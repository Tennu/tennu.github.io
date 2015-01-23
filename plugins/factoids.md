---
layout: plugin
title: Factoids Plugin
---

This plugin adds a factoids system 

It has no required dependencies, but optionally depends on the <a href="admin">admin</a> role/plugin. Just make sure that you load the admin role/plugin before you load this plugin. If you just pass the plugin names to the configuration, make sure this plugin is after the admin role/plugin.

The database is a <a href="//npmjs.org/package/dirty">Dirty</a> db, choosen because it requires no binary parts or starting a remote server.

The bot will listen to private messages, and when it sees a private message that matches a factoid key, the bot will respond with the description that matches the key. You can add a trigger that must prefix the key with configuration.

## Configuration

<dl>
    <dt>factoids-database</dt>
    <dd><b>Required String</b>. A relative path from the current working directory to the location of the factoids database.</dd>

    <dt>factoids-trigger</dt>
    <dd>Optional String. Only private messages that start with the trigger will look up factoids.</dd>
</dl>

## Commands

<dl>
    <dt>!factoid &lt;factoid-name&gt;</dt>
    <dd>
        <p>Look up a factoid by the specified name.</p>

        <p>Failure to find a factoid will be reported.</p>
    </dd>

    <dt>!learn &lt;factiod-name&gt; = &lt;factoid-description&gt;</dt>
    <dd>
        <p>Learn a factoid by the name of the factoid. By default, "&lt;factoid-name&gt; is " is prefixed to the description. This will also add the time and hostmask of the editor to the database, though that's not accessible from the plugin directly.</p>

        <p>You can also prefix &lt;reply&gt; or &lt;action&gt; to the description to remove the prefix or make the bot respond with an action.</p>

        <p>If the factoid is locked, you must be an admin to be able to edit it.</p>
    </dd>

    <dt>!forget &lt;factoid-name&gt;</dt>
    <dd>
        <p>Removes the factoid from being able to be looked up. The editor and time of deletion are stored in the database.</p>

        <p>If the factoid is locked, you must be an admin to be able to forget it.</p>
    </dd>

    <dt>!lock &lt;factoid-name&gt;</dt>
    <dd>Locks a factoid so that only an admin can create and edit it. You must be an admin to use this command.</dd>

    <dt>!unlock &gt;factoid-name&gt;</dt>
    <dd>Removes a lock from a factoid. You must be an admin to use this command.</dd>
</dl>

## Exports

None

## Hooks

None