---
layout: docs
title: Usage (Deploy)
prev_section: mache/usage
next_section: mache/usage_p
permalink: /docs/mache/usage_d/
documentation: true
project: mache
---

### -d,- -deploy Flag Usage

Following on from the [basic usage](/docs/mache/usage) instructions, you can also use MaCHe to generate the deployment script for deploying the Calypso release jars into a remote repository.  
  
In order to use the deploy flag you must also ensure that the `-r,--repository` flag is also set with the url for the location of your remote Maven repo.

{% highlight bash %}
#    
$ groovy -cp $MACHE_HOME $MACHE_HOME/mache.groovy -g com.blah.calypso -l 130007SP2 -d -r http://nexus.example.com/repo calypsorel130007SP2.jar
[unzip] Expanding: /home/pram/Downloads/mache/calypsorel130007SP2.jar into $/.MaCHe.temp
$ ls -a
.  ..  calypsorel130007SP2.jar  .MaCHe.temp
$ cd .MaCHe.temp
$/.MaCHe.temp ls -l
...
# List of  jar files contained within Calypso release
...
mvndeploy.script
{% endhighlight %}

If you look at the contents of `mvndeploy.script` you will see multiple Maven execution lines that install the Calypso libraries into your local Maven repo

{% highlight bash %}
$/.MaCHe.temp less mvndeploy.script
$M2_HOME/bin/mvn deploy:deploy-file -DgroupId=com.blah.calypso -DartifactId=commons-net-2.2 -Dversion=130
007SP2 -Dpackaging=jar -Dfile=$/.MaCHe.temp/commons-net-2.2.jar -Durl=http://nexus.example.com/
repo
#etc etc etc
{% endhighlight %}

This script is executable. Running this will store the Calypso release jars into your remote repo.

{% highlight bash %}
$/.MaCHe.temp chmod a+x mvndeploy.script
$/.MaCHe.temp ./mvndeploy.script
#Maven output should indicate SUCCESS
{% endhighlight %}