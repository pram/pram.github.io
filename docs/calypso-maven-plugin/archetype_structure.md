---
layout: docs
title: Archetype Structure
prev_section: calypso-maven-plugin/index_archetype
next_section: calypso-maven-plugin/archetype_initial
permalink: /docs/calypso-maven-plugin/archetype_structure/
documentation: true
project: cmp
---

You will now have a project with the following structure. The top level directory name is defined via the `-DartifactId=calypsoexample` property that was defined in the [archetype creation command](/docs/calypso-maven-plugin/archetype_initial/)

    calypsoexample
    |   pom.xml
    |
    +---config
    |   |   pom.xml
    |   |
    |   \---src
    |       \---main
    |           \---config
    |           \---resources
    |
    +---custom
    |   |   pom.xml
    |   |
    |   \---src
    |       \---main
    |           \---java
    +---hotfixes
    |   |   pom.xml
    |   |
    |   \---src
    |       \---main
    |           +---java
    |           \---resources
    +---releases
    |   |   pom.xml
    |   |
    |   \---src
    |       \---main
    |           \---resources
    \---scripts
        |   pom.xml
        |
        \---src
            \---main
                \---resources

