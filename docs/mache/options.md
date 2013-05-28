---
layout: docs
title: Options
prev_section: mache/installation
next_section: mache/usage
permalink: /docs/mache/options/
documentation: true
project: mache
---

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>Option/Description</th>
      <th>Notes and <span class="output">Examples</span></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <p class='name'><strong>-c,--clean</strong></p>
        <p>Clean working directory.</p>
      </td>
      <td class='align-center'>
        <p>
         Deletes the intermediate directory
        </p>
        <p>
          <!--code class='output'>2008-11-17T13:07:54-08:00</code-->
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p class='name'><strong>-d,--deploy</strong></p>
        <p>Generate Deploy Script otherwise default to Install script</p>
      </td>
      <td class='align-center'>
        <p>
         Generate a script to deploy the Calypso files to a remote repo, otherwise create a script that deploys into a local repo.
        </p>
        <p>
          <!--code class='output'>2008-11-17T13:07:54-08:00</code-->
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p class='name'><strong>-g,--groupName</strong></p>
        <p>Add to the following group in the repository</p>
      </td>
      <td class='align-center'>
        <p>
         This is the group name used within Maven to store the artifacts from the Calypso release. Use something meaningful and relevant to the project.
        </p>
        <p>
          <code class='output'>com.naughtyzombie.calypso.release</code>
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p class='name'><strong>-h,--help</strong></p>
        <p>Show usage information</p>
      </td>
      <td class='align-center'>
        <p>
         Display this help section
        </p>
        <p>          
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p class='name'><strong>-l,--label</strong></p>
        <p>Use the following label/version in Maven</p>
      </td>
      <td class='align-center'>
        <p>
         Typically you would use the standard Calypso release code as the label for the libraries.
        </p>
        <p>
        	<code class='output'>130007SP2</code>          
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p class='name'><strong>-p,--pom</strong></p>
        <p>Generate dependencies pom fragment to copy into pom.xml</p>
      </td>
      <td class='align-center'>
        <p>
         Using this option generates a file whose contents can be pasted into the dependency section of a pom file
        </p>
        <p>
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p class='name'><strong>-r,--repository</strong></p>
        <p>Use the following Maven repository</p>
      </td>
      <td class='align-center'>
        <p>
         A fully qualified reference to a maven repo
        </p>
        <p>
        	<code class='output'>http://nexus.example.com/repositories/releases</code>
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p class='name'><strong>-t,--tempDir</strong></p>
        <p>Temp directory to for intermediate files</p>
      </td>
      <td class='align-center'>
        <p>
         Directory where all intermediate scripts and files are created
        </p>
        <p>
        	<code class='output'>~/.mache/build</code>
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p class='name'><strong>-x,--execute</strong></p>
        <p>Execute script to deploy to Maven repository</p>
      </td>
      <td class='align-center'>
        <p>
         Execute script to deploy to Maven repository or install to local directory. This can be run standalone once the scripts have been generated.
     	</p>
        <p>
        	<code class='output'>~/.mache/build</code>
        </p>
      </td>
    </tr>    
  </tbody>
</table>
</div>