---
layout: docs
title: Optional Code
prev_section: calypso-maven-plugin/archetype_optional_modules
next_section: calypso-maven-plugin/archetype_structure
permalink: /docs/calypso-maven-plugin/archetype_optional_code/
documentation: true
project: cmp
---

Now, you can install the calypso jars into your Local or Remote repo

{% highlight bash %}
$ mvn -P initial process-resources
{% endhighlight %}

This will extract the embedded jars in the Calypso release and generate the installation and deployment scripts along with a dependency fragment of a pom file that can be copied into your main project pom file


{% highlight bash %}
$ ls -lart releases/target/mache/130007SP2/
# # #
# Many Many Jars from Calypso
# # #
-rw-rw-r-- 1 pram pram     45216 Jun 18 16:06 mvninstall.script
-rw-rw-r-- 1 pram pram     43632 Jun 18 16:06 mvndeploy.script
-rw-rw-r-- 1 pram pram     23577 Jun 18 16:06 pom.fragment
{% endhighlight %}

| Script Name        | Description           |
| ------------- |:-------------:|
|mvninstall.script|Script to install Calypso jars into Local repository. If your `M2_HOME` environment variable was set correctly, then this script is usually executable directly|
|mvndeploy.script|Script to install Calypso jars into a Remote repository. You will need to edit this file before it can be run. Specifically, you will have to search and replace all instances of `-Durl=dummy` with the correct url for your remote repository|
|pom.fragment|Fragment of pom file. This entire file can be cut and pasted into the main pom.xml for the project in the `<dependencies></dependencies>` section|

Once you have executed one or both of the scripts and copied the pom fragment into the project parent pom file, you can now run `mvn install` for the project and you should have a basic release file in the folder `releases/target`. It should be approximately the same size as the Calypso release file downloaded from the Calypso release web site.

