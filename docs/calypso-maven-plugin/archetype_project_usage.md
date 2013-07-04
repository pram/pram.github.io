---
layout: docs
title: Project Usage
prev_section: calypso-maven-plugin/archetype_optional_code
next_section: calypso-maven-plugin/archetype_structure
permalink: /docs/calypso-maven-plugin/archetype_project_usage/
documentation: true
project: cmp
---

At this point you should be able to check the project into source control.

Once you have adjusted the project settings as desired you can go ahead and install the project jar

{% highlight bash %}
$ mvn install
{% endhighlight %}

Assuming that there are no errors you will find that the deployable release file will have been created in the folder 
`$PROJECT_HOME/releases/target`

You can now test that the deployment has been successfully created in the following ways.

{% highlight bash %}
$ mvn -P run-calypso -pl releases process-resources
{% endhighlight %}

The AppStarter application will start. Make sure that there are no exceptions when launched.

If you want to test the deployment itself then navigate to `releases\target\deployment\bin` and run the command (on Windows)

{% highlight bash %}
$ rj com.calypso.apps.startup.StartAppWindow
{% endhighlight %}

or on Unix

{% highlight bash %}
$ ./rj.sh com.calypso.apps.startup.StartAppWindow
{% endhighlight %}

The AppStarter window should now appear.

You are now ready to develop and deploy Calypso releases.