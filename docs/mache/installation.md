---
layout: docs
title: Installation
prev_section: mache/home
next_section: mache/usage
permalink: /docs/mache/installation/
documentation: true
project: mache
---

### Requirements

The following are required before MaCHe will run

- [Groovy](http://groovy.codehaus.org/) - at least version 2.0
- Linux, Unix, Mac OS X or Windows

### Getting Started

First clone the code from the repository as shown in the documentation [welcome](/docs/home) page and switch to the mache directory. Then run mache.groovy to confirm that everything is in place.

{% highlight bash %}
$ cd MaCHe/src/main/groovy
$ groovy mache.groovy
{% endhighlight %}

You should see the following if everything has installed correctly

{% highlight bash %}
usage: mache.groovy [settings] <jarfile>
Options:
 -c,--clean                        Clean working directory
 -d,--deploy                       Generate Deploy Script otherwise
                                   default to Install script
 -g,--groupName <groupName>        Add to the following group in the
                                   repository
 -h,--help                         Show usage information
 -l,--label <labelName>            Use the following label/version in
                                   Maven
 -p,--pom                          Generate dependencies pom fragment to
                                   copy into pom.xml
 -r,--repository <repositoryUrl>   Use the following Maven repository
 -t,--tempDir <tempDir>            Temp directory to for intermediate
                                   files
 -x,--execute                      Execute script to deploy to Maven
                                   repository
{% endhighlight %}                                  

