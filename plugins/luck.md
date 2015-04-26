---
layout: plugin
title: Luck plugin
---

This plugin provides random-based functionality.

### Config

None

### Commands

#### !roll formula

Rolls the given formula. Has support for `+`, `*`, `/`, `-`, `d`, and parenthesis.

All other characters, and `d`s on the outside are ignored. This lets you do, e.g.

`!roll 4d6 for digging through the rock` will give you a number between 4 and 24.

The formula is evaluated through (`dados`)[https://npmjs.org/package/dados].

#### !which <option>..., !choose <option>...

Random chooses one of the one-word options.

`Ex: !choose A B C`
`bot: Choosing C.`

#### !sample <n> <option>...

Like !which, but selects `n` options.

#### !coin

Makes the bot say either "Heads" or "Tails".

### Exports

None

### Plugin Hooks

None