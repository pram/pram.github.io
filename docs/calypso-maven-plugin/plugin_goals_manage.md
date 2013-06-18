---
layout: docs
title: calypso:manage
prev_section: calypso-maven-plugin/index_plugin
next_section: calypso-maven-plugin/index_archetype
permalink: /docs/calypso-maven-plugin/plugin_goals_manage/
documentation: true
project: cmp
---

calypso:manage is a goal which allows Calypso process management

| Property        | Description           |
| ------------- |:-------------:|
|interactiveMode|User settings use to check the interactiveMode. Use <code>mvn -B calypso:manage</code> or <code>mvn --batch-mode calypso:manage</code>|
|processCatalog<code>default:ALL</code>|The process catalog to use to build the management list from and to let the user choose processes from. Should be defined at compile time by the calling project.|

