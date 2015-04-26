---
layout: plugin
title: Server Plugin
---

This plugin is built-in.

This plugin provides utilities for determining information about the server.

## Commands

None

## Exports

<dl>
  <dt>isupport</dt>
  <dd>
    <p>Object containing the capabilities of the server.</p>

    <h3>Example (for Mibbit network)</h3>
    {% highlight javascript %}
      {
        CMDS: 'KNOCK,MAP,DCCALLOW,USERIP',
        UHNAMES: true,
        NAMESX: true,
        SAFELIST: true,
        HCN: true,
        MAXCHANNELS: '40',
        CHANLIMIT: '#:40',
        MAXLIST: 'b:120,e:120,I:120',
        NICKLEN: '30',
        CHANNELLEN: '32',
        TOPICLEN: '307',
        KICKLEN: '307',
        AWAYLEN: '307',
        MAXTARGETS: '20',
        WALLCHOPS: true,
        WATCH: '128',
        WATCHOPTS: 'A',
        SILENCE: '15',
        MODES: '12',
        CHANTYPES: '#',
        PREFIX: '(qaohv)~&@%+',
        CHANMODES: 'beI,kfL,lj,psmntirRcOAQKVCuzNSMTG',
        NETWORK: 'Mibbit',
        CASEMAPPING: 'ascii',
        EXTBAN: '~,cqnr',
        ELIST: 'MNUCT',
        STATUSMSG: '~&@%+',
        EXCEPTS: true,
        INVEX: true
      }
    {% endhighlight %}
  </dd>
</dl>

## Plugin Hooks

None