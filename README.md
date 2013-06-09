# servletbridge-felix

A ServletBridge based on Apache Felix and Apache Felix Webconsole to use an embedded OSGi container 
within a **W**eb **AR**chive.


## Motivation

When searching the web for an OSGi servletbridge implementation you will eventually get to 
https://felix.apache.org/documentation/subprojects/apache-felix-http-service.html#using-the-servlet-bridge. 
When taking a look at the Felix example project mentioned on this website you will possibly notice that the Felix 
version in question is quite old. I searched the web high and low to find an up2date project that is using
newer versions but could not fine one*. Therefore I decided to come up with my own project that will take 
care of this.

* Just in case that anyone of you does know of such a *working* project please let me know.


## Installation

The installation is based on Apache Maven and should work just out of the box.  All dependencies are proper OSGi
bundles, with the exception of [org.json](http://mvnrepository.com/artifact/org.json/json/20090211) and the
[asm libraries](http://mvnrepository.com/artifact/asm). Two wrapper projects take care of the transformation
into OSGi bundles so no manual work has to be done here. Based on your requirements you can now create either a
*minimal* or an *extended* version of the servletbridge.

#### *Minimal* version

The minimal version only contains the mandatory bundles to run a servletbridge with webconsole support. To create
such a servletbridge just clone the project  and navigate to the parent folder. Next run `mvn clean install` from the 
command line. This will create and fetch all the required artifacts to get a working war file. The following
screenshot shows the webconsole with all installed bundles.

![A minimal version of the servletbridge](https://raw.github.com/frieder/servletbridge-felix/master/webconsole_minimal.png "A minimal version of the servletbridge")

#### *Extended* version

The extended version does not only provide webconsole support but also comes with extended logging support via
[SLF4J](http://www.slf4j.org/) and [Logback](http://logback.qos.ch/), enhanced HTTP support via 
[Pax Web](https://ops4j1.jira.com/wiki/display/paxweb/Pax+Web) and a bunch of additional OSGi services and 
webconsole plugins. To create the extended servletbridge navigate to the parent folder and run 
`mvn clean install -Pextended` in the command line. As a result you will get a war file that contains all the bundles
shown in the following screenshot.

![An extended version of the servletbridge](https://raw.github.com/frieder/servletbridge-felix/master/webconsole_extended.png "An extended version of the servletbridge")

