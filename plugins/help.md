---
layout: plugin
title: Help Plugin
---

<p class="built-in">This plugin is built-in.</p>

This plugin let's you administrate your bots.

## Config

### disable-help: boolean

[<b>Deprecated</b>] Use <code>"command-ignore-list": ["commands", "help"]</code> instead.

Disables the plugin.

## Commands

### !help &lt;topic&gt;

Gives the help information about that topic.

Can also search subtopics.

Should no topic be given, the help topic for the help command will be given.

In the case that there is no topic for the topic, the bot will respond with:

<pre>&gt; Help message for selected topic does not exist.</pre>

All responses will be in query.

### !commands

Lists the names of known commands.

## Exports

TBD

## Hooks

### help

The general form of the value is a dictionary of topics that take a
dictionary of subtopics along with an '\*' property for the help message
for that topic itself.

The help message may either be a string or an array of strings for
multiline messages.

For example, here is the help object for a time plugin:

{% highlight js %}
{
    time: {
        '*': [
            "The time plugin gives time information as requested.",
            "",
            "Subcommands: ",
            "!time at &lt;place&gt;",
            "!time zone &lt;place&gt;",
            "!time between &lt;place&gt; and &lt;place&gt;"
        ],
        
        // Help messages omitted for brevity.
        at: "...",
        zone: "...",
        between: "..."
    }
}
{% endhighlight %}

#### Simple Represenations ####

Should your topic not have any subtopics, you may use a string or array
directly.

Thus, the 'zone' property in the preceding example is equivalent to:
{% highlight js%}{ '*': "..." }{% endhighlight %}

Should your plugin only need to respond to the query that is the plugin's
name, the help value may be just a string or array.

#### Tip ####

The help object can be placed into a JSON file if it gets too long.

### commands

A list of command names that you want added to the output of !commands.