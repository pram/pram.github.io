---
layout: docs
title: Maven Usage
prev_section: mache/usage_p
permalink: /docs/mache/usage_maven/
documentation: true
project: mache
---

### Usage with Maven

MaCHe can also be used as part of the [calypso-maven-plugin](/docs/calypso-maven-plugin/home).  
  
First you will have to add MaCHe into your local repo (or into your remote repo). Assuming that you are in the `$MACHE_HOME` directory

{% highlight bash %}
$ mvn clean install
#...
# Several lines of Maven output
#...
[INFO] -----------------------------------------
[INFO] BUILD SUCCESS
[INFO] -----------------------------------------
[INFO] Total time: 4.381s
[INFO] Finished at: Wed May 29 14:13:06 BST 2013
[INFO] Final Memory: 26M/332M
[INFO] -----------------------------------------
{% endhighlight %}

