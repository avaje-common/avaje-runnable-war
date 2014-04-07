avaje-runnable-war
==================

Provides a maven parent pom that uses maven overlay, jetty and avaje-jetty-runner to build runnable wars 


This uses the "maven overlay approach" to put jetty, logging, servlet api and avaje-jetty-runner
into the root path of the war and a manifest entry to point to the RunWar main method. The jars 
included in the overlays provide a set of system classes that boot and run the war.
   

Maven parent pom
----------------
In a maven project specify runnable-war as the parent pom.


```xml
  <parent>
    <groupId>org.avaje.jetty</groupId>
    <artifactId>runnable-war</artifactId>
    <version>1.0</version>
  </parent>
```  
