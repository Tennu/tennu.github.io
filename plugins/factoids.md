---
layout: plugin
title: Factoids Plugin
---

This plugin adds a way of storing standard responses for common queries.

It has no required dependencies, but optionally depends on the <a href="admin">admin</a> role/plugin. Just make sure that you load the admin role/plugin before you load this plugin. If you just pass the plugin names to the configuration, make sure this plugin is after the admin role/plugin.

The database is a <a href="//npmjs.org/package/dirty">Dirty</a> db, choosen because it requires no binary parts or starting a remote server.

The bot will listen to private messages, and when it sees a private message that matches a factoid key, the bot will respond with the description that matches the key. You can add a trigger that must prefix the key with configuration.

## Configuration

<dl>
    <dt>factoids-database</dt>
    <dd><b>Required String</b>. A relative path from the current working directory to the location of the factoids database.</dd>

    <dt>factoids-trigger</dt>
    <dd>Optional String. Only messages that start with the trigger will look up factoids.</dd>
</dl>

## Commands

<dl>
    <dt>!factoid &lt;factoid-name&gt;</dt>
    <dd>
        <p>Look up a factoid by the specified name.</p>

        <p>Failure to find a factoid will be reported.</p>
    </dd>

    <dt>!learn &lt;factoid-name&gt; = &lt;factoid-description&gt;</dt>
    <dd>
        <p>Learn a factoid by the name of the factoid. By default, "&lt;factoid-name&gt; is " is prefixed to the description. This will also add the time and hostmask of the editor to the database, though that's not accessible from the plugin directly.</p>

        <p>You can also use other operators than just <code>=</code>.</p>

        <dl>
            <dt>!=</dt>
            <dd>
                <p>Make the factoid response an action.</p>
                <p>
                    Ex:<br>
<pre>[user] !learn dance != does a jig.
[bot] Learned factoid 'dance'.
[user] !dance
* bot does a jib</pre>
                </p>
            </dd>

            <dt>:=</dt>
            <dd>
                <p><i>Define</i> a term by prefixing the response with the key and the word is. The case of the key matters.</p>
                <p>
                    Ex:<br>
<pre>[user] !learn Moon := a place made out of cheese.
[bot] Learned factoid 'moon'.
[user] !moon
[bot] Moon is a place made out of cheese.</pre>
                </p>
            </dd>

            <dt>@=</dt>
            <dd>
                <p>Aliases the key on the left to the key on the right.</p>

                <p>Note: The alias is not smart, and if the key it aliases doesn't exist, it'll being aliasing nothing.</p>
                <p>Note: Modifying this factoid with `+=` or `~=` modifies what key this is aliasing, the the response itself.</p>
            </dd>

            <dt>+=</dt>
            <dd>
                <p>Appends more to the description of a factoid. The factoid must already exist.</p>

                <p>
                    Ex:<br>
<pre>[user] !math
[bot] 2 + 2 = 4. 2 * 3 = 6.
[user] !learn math += 10 - 7 = 3.
[bot] Successfully did replacement on 'math'
[user] !math
[bot] 2 + 2 = 4. 2 * 3 = 6. 10 - 7 = 3.</pre>
                </p>
            </dd>

            <dt>~= s/search/replace/</dt>
            <dd>
                <p>Does a sed-style search and replace on the description. The search is a JavaScript regular expression. The replace is a string. Currently, you may not include a "/" on either side. If you don't know regular expressions, you should not use this variant except for literal to literal translations using only alphanumeric, spaces, and periods.</p>
            </dd>
        </dl>

        <p>If the factoid is locked, you must be an admin to be able to edit it.</p>
    </dd>

    <dt>!forget &lt;factoid-name&gt;</dt>
    <dd>
        <p>Removes the factoid from being able to be looked up. The editor and time of deletion are stored in the database.</p>

        <p>If the factoid is locked, you must be an admin to be able to forget it.</p>
    </dd>

    <dt>!lock &lt;factoid-name&gt;</dt>
    <dd>Locks a factoid so that only an admin can create and edit it. You must be an admin to use this command.</dd>

    <dt>!unlock &lt;factoid-name&gt;</dt>
    <dd>Removes a lock from a factoid. You must be an admin to use this command.</dd>
</dl>

## Exports

None

## Hooks

None