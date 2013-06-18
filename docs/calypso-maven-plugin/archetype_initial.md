---
layout: docs
title: Archetype Initial Usage
prev_section: calypso-maven-plugin/index_archetype
next_section: calypso-maven-plugin/archetype_install_jar
permalink: /docs/calypso-maven-plugin/archetype_initial/
documentation: true
project: cmp
---

Now, you can use the archetype in a new project typing:

{% highlight bash %}
mvn archetype:generate -DarchetypeGroupId=com.naughtyzombie.calypso.maven -DarchetypeArtifactId=calypso-maven-plugin -DarchetypeVersion=1.0 -DgroupId=com.newinstall.calypso -DartifactId=calypsoexample -Dversion=1.0-SNAPSHOT
{% endhighlight %}

Replace the values for the parameters `groupID`, `artifactId` and `version` with your desired values. You will also be asked to enter the Calypso version that you will be working with. You can either add the following

    -DcalypsoVersion=XXxxxx[SPy]

to the archetype generation command above, or you will be asked to enter the version number interactively eg

    Define value for property 'calypsoVersion': : 130007SP2

Before you can start development you need to ensure that the Calypso libraries are in place in your repo. Download the relevant release from the [Calypso](http://www.calypso.com) web site and run the following command

{% highlight bash %}
mvn install:install-file -DgroupId=com.calypso.release -DartifactId=calypsorel -Dversion=130007SP2 -Dpackaging=jar -Dfile=/path/to/file
{% endhighlight %}

Where `-Dfile=/path/to/file` points to the file that you just downloaded. Also ensure that the version number matches that which you specified during the creation of the Archetype.

If preferred you can deploy the Calypso release into your remote repository.

Before we proceed we need to temporarily disable the building of the web modules.

{% highlight bash %}
$ cd calypsoexample
$ vi pom.xml
{% endhighlight %}

Find out comment out the references to the web modules at the bottom of the pom file

{% highlight xml %}
<modules>
    <module>hotfixes</module>
    <module>config</module>
    <module>custom</module>
    <module>scripts</module>
    <module>releases</module>
    <!-- Comment one or both web modules if WebStart deployment not needed-->
    <!--module>web</module>
    <module>web-static</module-->
  </modules>
</project>
{% endhighlight %}

You should now be able to run install using Maven

{% highlight bash %}
$ mvn install
# Several lines of Maven output
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary:
[INFO] 
[INFO] calypsoexample .................................... SUCCESS [0.297s]
[INFO] calypsoexample::hotfixes .......................... SUCCESS [2.620s]
[INFO] calypsoexample::config ............................ SUCCESS [2.046s]
[INFO] calypsoexample::custom ............................ SUCCESS [0.553s]
[INFO] calypsoexample::scripts ........................... SUCCESS [0.421s]
[INFO] calypsoexample::releases .......................... SUCCESS [1.207s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 7.429s
[INFO] Finished at: Tue Jun 18 15:23:08 BST 2013
[INFO] Final Memory: 28M/327M
[INFO] ------------------------------------------------------------------------
{% endhighlight %}

Now that you have confirmed that the project can be built you need to run a one off process to extract certain files from the Calypso release and load them into your Maven repo.
