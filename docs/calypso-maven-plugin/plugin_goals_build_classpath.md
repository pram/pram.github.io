---
layout: docs
title: calypso:build-classpath
prev_section: calypso-maven-plugin/index_plugin
next_section: calypso-maven-plugin/index_archetype
permalink: /docs/calypso-maven-plugin/plugin_goals_build_classpath/
documentation: true
project: cmp
---

This goal allows for the logical output of the classpath to be defined using the order of dependencies in the main pom file.

calypso:build-classpath has several properties


| Property        | Description           |
| ------------- |:-------------:|
|output| If specified, this parameter will cause the dependency tree to be written to the path specified, instead of writing to the console. |
|outputFile| If specified, this parameter will cause the dependency tree to be written to the file specified in the `output` folder, instead of writing to the console.     |
|outputType<code>default:text</code> | If specified, this parameter will cause the dependency tree to be written using the specified format. Currently supported format are <code>text, dot, graphml and tgf</code>. These formats can be plotted to image files. An example of how to plot a dot file using pygraphviz can be found <a href="http://networkx.lanl.gov/pygraphviz/tutorial.html#layout-and-drawing">here</a>      |
|scope|The scope to filter by when resolving the dependency tree, or <code>null</code> to include dependencies from all scopes.|
|verbose<code>default:false</code>|Whether to include omitted nodes in the serialized dependency tree|
|tokens<code>default:standard</code>|The token set name to use when outputting the dependency tree. Possible values are <code>whitespace</code>, <code>standard</code> or <code>extended</code>, which use whitespace, standard or extended ASCII sets respectively.|
|includes|A comma-separated list of artifacts to filter the serialized dependency tree by, or <code>null</code> not to filter the dependency tree. The artifact syntax is defined by <code>StrictPatternIncludesArtifactFilter</code>.|
|excludes|A comma-separated list of artifacts to filter from the serialized dependency tree, or <code>null</code> not to filter any artifacts from the dependency tree. The artifact syntax is defined by <code>StrictPatternExcludesArtifactFilter</code>.|

