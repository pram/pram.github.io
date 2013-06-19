---
layout: docs
title: Optional Modules
prev_section: calypso-maven-plugin/archetype_install_jar
next_section: calypso-maven-plugin/archetype_optional_code
permalink: /docs/calypso-maven-plugin/archetype_optional_modules/
documentation: true
project: cmp
---

[Earlier](/docs/calypso-maven-plugin/archetype_initial) in the installation process you will have commented out the references to the web modules

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

###web

If you now uncomment the reference to `web` you can run the following command to build a jsp based web start application

{% highlight bash %}
$ mvn install -pl web
# # #
# Lots of Maven output
# # #
$ ls -lart web/target
drwxrwxr-x  4 pram pram      4096 Jun 19 11:33 unpack
drwxrwxr-x  2 pram pram      4096 Jun 19 11:33 dependency-maven-plugin-markers
drwxrwxr-x  2 pram pram      4096 Jun 19 11:33 antrun
drwxrwxr-x  3 pram pram      4096 Jun 19 11:33 maven-status
drwxrwxr-x  7 pram pram      4096 Jun 19 11:33 generated-sources
drwxrwxr-x  3 pram pram      4096 Jun 19 11:33 classes
drwxrwxr-x  5 pram pram      4096 Jun 19 11:35 ..
drwxrwxr-x  6 pram pram      4096 Jun 19 11:38 web-1.0-SNAPSHOT
drwxrwxr-x  2 pram pram      4096 Jun 19 11:38 maven-archiver
drwxrwxr-x 11 pram pram      4096 Jun 19 11:38 .
-rw-rw-r--  1 pram pram 220794971 Jun 19 11:38 web-1.0-SNAPSHOT.war
drwxrwxr-x  2 pram pram      4096 Jun 19 11:38 surefire
{% endhighlight %}

You will see that the web archive `web-1.0-SNAPSHOT.war` has been created. You can now deploy this into any JSP enabled application server (eg Tomcat or Jetty)

###web-static

If you now uncomment the reference to `web-static` you can run the following commands to build a web start application

{% highlight bash %}
$ mvn install -P initial -pl web-static
# # #
# Lots of Maven output
# # #
$ mvn install -pl web-static
# # #
# Lots of Maven output
# # #
{% endhighlight %}
