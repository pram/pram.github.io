---
layout: docs
title: Installation
prev_section: calypso-maven-plugin/home
next_section: calypso-maven-plugin/index_plugin
permalink: /docs/calypso-maven-plugin/installation/
documentation: true
project: cmp
---

### Requirements

- [Maven](https://maven.apache.org/) - at least version 3.0
- [data-exporter](https://code.google.com/p/data-exporter/) - v1.0.0
- [j-text-utils](https://code.google.com/p/j-text-utils/) - v0.3
- [MaCHe](/docs/mache/installation/)

Details of downloading and installing data-exporter and j-text-utils are in the main pom.xml file.

### Installation

First clone the code from the repository as shown in the documentation [welcome](/docs/home) page and switch to the calypso-maven-plugin directory.  
  
Once the dependencies are in place you run the standard installation command

{% highlight bash %}
$ cd calypso-maven-plugin
$ mvn install
{% endhighlight %}

This will install the plugin into your local .m2 repository. To make the release available to other developers consult the remote deployment documentation associated with your repository.


