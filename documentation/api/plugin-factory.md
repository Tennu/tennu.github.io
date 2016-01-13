---
title: Plugin Factory
layout: document
---

<p>The plugin factory structure is what <a href="https://npmjs.com/package/tennu-plugins"><code>tennu-plugins</code></a>, the plugin system for <code>tennu</code>, uses to install a plugin into a bot.</p>

<p>Do not be scared that this is called a factory. It's just an object that holds the real [plugin](plugin) constructor and static metadata.</p>

<h2>Properties</h2>

<p>The only required property to the Plugin factory object is the <code>init</code> method, though you should also include the <code>name</code>.</p>

| Property | Description |
| -------- | ----------- |
| `init`  | <small>(client: [Client](client), imports: \[Object<PluginName, PluginExportsObject>)]) -> [Plugin](plugin)</small> <br><br> The actual function that constructs an actual [Plugin](plugin). It takes as parameters the client the plugin will be installed into and a dictionary to the plugin exports of the plugins that the plugin depends on. |
| `name` | <small>String</small> <br><br> Usually inferred, this is required when installing a plugin via <span class="code">[Client](client)::initializePlugin</span>. Since <span class="code">[Client](client)::use</span> and the [configuration](configuration) object exist, you shouldn't need that method or this property. It exists for posterity's sake if somebody wants to use <a href="https://github.com/tennu/tennu-plugins">tennu-plugins</a> for their own framework without wanting the magic provided by its `use` method. |
| `role` | <small>String \| undefined</small> <br><br> The role that a plugin provides. Basically, if a plugin exports object has an interface, the name of that interface becomes the name of the role. One example is tennu-admin, which exports the [admin](admin) interface. |
| `requires` | <small>\[String] \| undefined</small> <br><br> The list of plugins that this plugin relies on by name. |
| `requiresRoles` | <small>\[String] \| undefined</small> <br><br> The list of roles that this plugin relies on by name. |

<h3>Static Hooks</h3>

<p>Just like a <a href="plugin"><code>Plugin</code></a> has hooks (such as e.g. <code>handlers</code>), a <code>PluginFactory</code> also has hooks. Hooks in the <code>PluginFactory</code> are called <i>Static Hooks</i> while hooks in the <code>Plugin</code> are called <i>Instance Hooks</i>.

<p>Right now, Tennu provides one static hook, <a href="/plugins/config#configDefaults"><code>configDefaults</code></a>, though other plugins can add more.</p>

<h2>Template</h2>

<p>For your convenience, here is a template for making plugins.</p>

<p>Things in <code>ALL CAPS</code> should be replaced, not kept in <code>ALL CAPS</code></p>

{% highlight javascript %}
const OTHER_MODULES = require("...");

// Constant definitions goes here.

const PLUGIN_NAME_FACTORY = {
    name: "PLUGIN_NAME",

    configDefaults: {
        "PLUGIN-FOO": undefined
    },

    init: function (client, imports) {
        // Pull imports into their own variables.
        const import = imports["import"];

        // Any per-instance initialization goes here.

        return {
            handlers: {
                privmsg: function (message) {

                },

                "!command": function (message) {

                }
            },

            help: {
                "command": [
                    "!command",
                    "",
                    "Help for !command"
                ]
            },

            commands: ["command"]
        };
    },

    role: undefined,
    requires: [],
    requiresRoles: []
};
{% endhighlight %}