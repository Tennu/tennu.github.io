---
layout: document
title: Documentation
---

## Limitations

This is a list of things that Tennu cannot do, and won't be fixed in the near future. Workarounds
exist for them.

* Plugins are considered done loading after their `.init()` is called, so any async loading it does
  cannot be considered done by the time hooks, listeners, and export functions are called.
  If your plugin doesn't do any async loading, this isn't a problem.
** To fix this, `tennu-plugins` would have to return a promise, thus necessitating v.4.x.y of it.
* Plugins cannot be removed once started.
* Plugins cannot be how-swapped.