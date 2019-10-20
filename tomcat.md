
Based on ![tomcat context container documentation.](https://tomcat.apache.org/tomcat-7.0-doc/config/context.html)

The Context element represents a web application, which is run within a particular virtual host.

Each web application is based on a:
* WAR file
* or a corresponding directory.

The web application used to process each HTTP requests is selected by Catalina based:
* on __matching the longest possible prefix__ of the request URI against the **context path** of each defined **Context**.

Once a context is selected a servlet is selected to process incoming request according to servlet mapping defined by the web application deployment.

A **Context** **MUST** have a unique context name within a virtual host, the **context path** __does not need to be unique__ but not empty except for the default web application.

## Parallel deployment

Naming

```
foo##v123.war

context path /foo
context version v123
context name foo##v123
```

<table>
    <tr>
      <th>Context Path</th>
      <th>Context Version</th>
      <th>Context Name</th>
      <th>Base File Name</th>
      <th>Example File Names (.xml, .war, directory)</th>
    </tr>
    <tr>
      <td valign="top" bgcolor="#a0ddf0" align="left">/foo</td>
      <td valign="top" bgcolor="#a0ddf0" align="left"><i>None</i></td>
      <td valign="top" bgcolor="#a0ddf0" align="left">/foo</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">foo</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">foo.xml, foo.war, foo</td>
    </tr>
    <tr>
      <td valign="top" bgcolor="#a0ddf0" align="left">/foo/bar</td>
      <td valign="top" bgcolor="#a0ddf0" align="left"><i>None</i></td>
      <td valign="top" bgcolor="#a0ddf0" align="left">/foo/bar</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">foo#bar</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">foo#bar.xml, foo#bar.war, foo#bar</td>
    </tr>
    <tr>
      <td valign="top" bgcolor="#a0ddf0" align="left"><i>Empty String</i></td>
      <td valign="top" bgcolor="#a0ddf0" align="left"><i>None</i></td>
      <td valign="top" bgcolor="#a0ddf0" align="left"><i>Empty String</i></td>
      <td valign="top" bgcolor="#a0ddf0" align="left">ROOT</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">ROOT.xml, ROOT.war, ROOT</td>
    </tr>
    <tr>
      <td valign="top" bgcolor="#a0ddf0" align="left">/foo</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">42</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">/foo##42</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">foo##42</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">foo##42.xml, foo##42.war, foo##42</td>
    </tr>
    <tr>
      <td valign="top" bgcolor="#a0ddf0" align="left">/foo/bar</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">42</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">/foo/bar##42</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">foo#bar##42</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">foo#bar##42.xml, foo#bar##42.war, foo#bar##42</td>
    </tr>
    <tr>
      <td valign="top" bgcolor="#a0ddf0" align="left"><i>Empty String</i></td>
      <td valign="top" bgcolor="#a0ddf0" align="left">42</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">##42</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">ROOT##42</td>
      <td valign="top" bgcolor="#a0ddf0" align="left">ROOT##42.xml, ROOT##42.war, ROOT##42</td>
    </tr>
  </table>
  
To remove old versions

```
<Host undeployOldVersions="true" ...>...</Host>
```

