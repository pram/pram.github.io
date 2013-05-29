---
layout: docs
title: Usage (POM)
prev_section: mache/usage_d
next_section: mache/usage_maven
permalink: /docs/mache/usage_p/
documentation: true
project: mache
---

### -p,- -pom Flag Usage  
  
Running with the `-p` flag will generate a pom fragment that can be cut and pasted into a maven pom files dependencies section. These dependencies will resolve to the jar files that you have just uploaded into your [local](/docs/mache/usage) or [remote](/docs/mache/usage_d) repo.

{% highlight bash %}
#    
$ groovy -cp $MACHE_HOME $MACHE_HOME/mache.groovy -g com.blah.calypso -l 130007SP2 calypsorel130007SP2.jar
[unzip] Expanding: /home/pram/Downloads/mache/calypsorel130007SP2.jar into $/.MaCHe.temp
$ ls -a
.  ..  calypsorel130007SP2.jar  .MaCHe.temp
$ cd .MaCHe.temp
$/.MaCHe.temp ls -lrt
...
# List of  jar files contained within Calypso release
...
mvninstall.script
pom.fragment
{% endhighlight %}

Looking into the `pom.fragment` file shows multiple Maven dependency statements of the form

{% highlight xml %}
<dependency>
  <groupId>com.blah.calypso</groupId>
  <artifactId>jdom</artifactId>
  <version>130007SP2</version>
</dependency>
{% endhighlight %}

The contents of `pom.fragment` can be cut and pasted into a working pom.xml

{% highlight xml %}
<project xmlns="http://maven.apache.org/POM/4.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                      http://maven.apache.org/xsd/maven-4.0.0.xsd">
  
  <!-- Pom File start -->

  <dependencies><!-- INSERT FRAGMENT HERE --></dependencies>
  <parent>...</parent>
  <dependencyManagement>...</dependencyManagement>
  <modules>...</modules>
  <properties>...</properties>

  <!-- Pom file end -->
</project>
{% endhighlight %}

In order to validate, you can now run a Maven command and you should see the dependecies either downloaded from the remote repo, or confirmed that they exist in the correct place in the local repo.

{% highlight bash %}
$/some.maven.project mvn validate
#...
# Maven output followed by SUCCESS
#...
{% endhighlight %}