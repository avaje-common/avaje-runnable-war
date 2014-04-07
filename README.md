avaje-runnable-war
==================

Provides a maven parent pom that uses maven overlay, jetty and avaje-jetty-runner to build runnable wars 


This uses the "maven overlay approach" to put jetty, logging, servlet api and avaje-jetty-runner
into the root path of the war and a manifest entry to point to the RunWar main method. The jars 
included in the overlays provide a set of system classes that boot and run the war.
   

1. Maven parent pom
-------------------
In a maven project specify runnable-war as the parent pom.


```xml
  <parent>
    <groupId>org.avaje.jetty</groupId>
    <artifactId>runnable-war</artifactId>
    <version>1.0</version>
  </parent>
```  

2. mvn clean package
-------------------
This builds the war and will insert the jetty + logging + avaje-jetty-runner classes into the root of the war.
It puts in a manifest entry to the avaje-jetty-runner RunWar.main() method.

Assumes logback is used for logging.


3. Run the war
--------------
Create a local logback.xml file and typically also a properties file.
```bsh
#!/bin/sh
java -Dlogback.configurationFile=logback.xml -jar target/example-1.1.1-SNAPSHOT.war

```

References:
-----------
http://jowisoftware.de/blog/archives/26-Creating-runnable-wars-with-Maven-and-Jetty.html

https://github.com/uoa-group-applications/common-runnable-war
