---
title: Plugin Factory
layout: document
---

The plugin factory structure is what `tennu-plugins`, the plugin system for `tennu`, takes to install a plugin into a bot.

Do not be scared that this is called a factory. It's just an object that holds the real [plugin](plugin) constructor and static metadata.

## Properties

The only required property to the Plugin factory object is the `init` method.

| Property | Description |
| -------- | ----------- |
| `init`  | <small>(client: [Client](client), imports: \[Object<PluginName, PluginExportsObject>)]) -> [Plugin](plugin)</small> <br><br> The actual function that constructs an actual [Plugin](plugin). It takes as parameters the client the plugin will be installed into and a dictionary to the plugin exports of the plugins that the plugin depends on. |
| `name` | <small>String</small> <br><br> Usually inferred, this is required when installing a plugin via <span class="code">[Client](client)::initializePlugin</span>. Since <span class="code">[Client](client)::use</span> and the [configuration](configuration) object exist, you shouldn't need that method or this property. It exists for posterity's sake if somebody wants to use <a href="https://github.com/tennu/tennu-plugins">tennu-plugins</a> for their own framework without wanting the magic provided by its `use` method. |
| `role` | <small>String \| undefined</small> <br><br> The role that a plugin provides. Basically, if a plugin exports object has an interface, the name of that interface becomes the name of the role. One example is tennu-admin, which exports the [admin](admin) interface. |
| `requires` | <small>\[String] \| undefined</small> <br><br> The list of plugins that this plugin relies on by name. |
| `requiresRoles` | <small>\[String] \| undefined</small> <br><br> The list of roles that this plugin relies on by name. |

## Template

For your convenience, here is a template for making plugins:

{% highlight javascript %}
var OTHER_MODULES = require("...");

// Constant definitions goes here.

module.exports = {
    init: function (client, imports) {
        // Pull imports into their own variables.
        var import = imports["import"];

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