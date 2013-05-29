---
layout: docs
title: Usage
prev_section: mache/options
next_section: mache/usage_d
permalink: /docs/mache/usage/
documentation: true
project: mache
---

### Usage instructions

#### Download release

Download Calypso release from [web site](http://www.calypso.com). For this example we will be using version `130007SP2` as the reference version.  

You will now have a release file named `calypsorel130007SP2.jar`. Copy this into a working directory.  
  
<div class="note">
  <h5>MACHE_HOME</h5>
  <p>It would be a good idea to set up a `MACHE_HOME` environment variable to point to the location where you have the mache project installed</p>
</div>

{% highlight bash %}
#    
$ groovy -cp $MACHE_HOME $MACHE_HOME/mache.groovy -g com.blah.calypso -l 130007SP2 calypsorel130007SP2.jar
[unzip] Expanding: /home/pram/Downloads/mache/calypsorel130007SP2.jar into $/.MaCHe.temp
$ ls -a
.  ..  calypsorel130007SP2.jar  .MaCHe.temp
$ cd .MaCHe.temp
$/.MaCHe.temp ls -l
...
# List of  jar files contained within Calypso release
...
mvninstall.script
{% endhighlight %}

If you look at the contents of `mvninstall.script` you will see multiple Maven execution lines that install the Calypso libraries into your local Maven repo

{% highlight bash %}
$/.MaCHe.temp less mvninstall.script
$M2_HOME/bin/mvn install:install-file -DgroupId=com.blah.calypso -DartifactId=commons-net-2.2 -Dversion=130007SP2 -Dpackaging=jar -Dfile=/home/pram/Downloads/mache/.MaCHe.temp/commons-net-2.2.jar -DgeneratePom=true
#etc etc etc
{% endhighlight %}

This script is executable. Running this will store the Calypso release jars into your local repo.

{% highlight bash %}
$/.MaCHe.temp chmod a+x mvninstall.script
$/.MaCHe.temp ./mvninstall.script
#Maven output should indicate SUCCESS
{% endhighlight %}