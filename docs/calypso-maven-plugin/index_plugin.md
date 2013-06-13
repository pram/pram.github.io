---
layout: docs
title: Plugin Intro
prev_section: calypso-maven-plugin/installation
next_section: calypso-maven-plugin/plugin_goals
permalink: /docs/calypso-maven-plugin/index_plugin/
documentation: true
project: cmp
---

## Plugin usage

The plugin can be added to any existing pom file and can be used for various functions  
  
Simply insert the following code snippet into the pom file for your project in the location `/project/build/plugins/plugin`

{% highlight xml %}
<plugin>
    <groupId>com.naughtyzombie.calypso.maven</groupId>
    <artifactId>calypso-maven-plugin</artifactId>
    <version>${calypso.maven.plugin.version}</version>
</plugin>
{% endhighlight %}

Set the property `${calypso.maven.plugin.version}` to be the desired version of calypso-maven-plugin - Latest: <code>{{ site.cmp_latest_version }}</code>  
  

