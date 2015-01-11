---
title: Plugin Factory
layout: document
---

The plugin factory structure is what `tennu-plugins`, the plugin system for `tennu`, takes to install a plugin into a bot.

The only required property to the Plugin factory object is the `init` method.

| Property | Description |
| -------- | ----------- |
| `init`  | (client: [Client](client), imports: \[Object<PluginName, PluginExportsObject>)]) -> [Plugin](plugin) <br><br> The actual function that constructs an actual [Plugin](plugin). It takes as parameters the client the plugin will be installed into and a dictionary to the plugin
exports of the plugins that the plugin depends on. |
| `name` | String <br><br> Usually inferred, this is required when installing a plugin via `[Client](client)::initializePlugin`. Since `[Client](client)::use` and the [configuration](configuration) object exist, you shouldn't need that method or this property. It exists for posterity's sake if somebody wants to use <a href="https://github.com/tennu/tennu-plugins">tennu-plugins</a> for their own framework without wanting the magic provided by its `use` method. |
| `role` | String \| undefined <br><br> The role that a plugin provides. Basically, if a plugin exports object has an interface, the name of that
interface becomes the name of the role. One example is tennu-admin, which exports the [admin](admin) interface. |
| `requires` | \[String] \| undefined <br><br> The list of plugins that this plugin relies on by name. |
| `requiresRoles` | \[String] \| undefined <br><br> The list of roles that this plugin relies on by name. |

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