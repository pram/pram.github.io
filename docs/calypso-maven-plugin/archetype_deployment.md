---
layout: docs
title: Project Deployment
prev_section: calypso-maven-plugin/archetype_project_usage
next_section: calypso-maven-plugin/archetype_structure
permalink: /docs/calypso-maven-plugin/archetype_project_deployment/
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
