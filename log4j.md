## Log4J

#### Task 1: Create a Maven Project and add log4j-core jar

* pom.xml
```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>com.naresh</groupId>
	<artifactId>log4j-demo</artifactId>
	<version>0.0.1-SNAPSHOT</version>

	<dependencies>
  
		<dependency>
			<groupId>org.apache.logging.log4j</groupId>
			<artifactId>log4j-core</artifactId>
			<version>2.11.2</version>
		</dependency>
    
	</dependencies>
</project>
```

#### Task 2: Create a class and use Logger methods

* Logger Methods - info, warn,error

```java
package com.naresh;

import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

public class LoggerDemo {

	private static Logger log = LogManager.getLogger(LoggerDemo.class);

	public static void main(String[] args) {
	  log.info("Send SMS Method is called !");
		log.warn("SMS is not sent");
		log.error("Unable to connect database");
	}

}
```

##### Task 3: Configure logger configuration
* resources/log4j2.xml
* Log files will be written to "project.log" 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<Configuration status="WARN">
    <Appenders>
        <Console name="Console" target="SYSTEM_OUT">
            <PatternLayout pattern="%d{HH:mm:ss.SSS} %-5level - %msg%n"/>
        </Console>
	<File name="MyFile" fileName="project.log" immediateFlush="false"
			append="false">
			<PatternLayout
				pattern="%d{yyy-MM-dd HH:mm:ss.SSS} [%t] %-5level %logger{36} - %msg%n" />
	</File>
    </Appenders>
    <Loggers>
        <Root level="info">
            <AppenderRef ref="Console"/>
	    <AppenderRef ref="MyFile"/>
        </Root>
    </Loggers>
</Configuration>
```

##### Task 4: Understand Levels

* Below are the Log4j log levels, in order of least to most restrictive:

* ALL => all levels
* DEBUG => designates fine-grained informational events that are most useful to debug an application
* INFO => informational messages that highlight the progress of the application at the coarse grained level
* WARN => designates potentially harmful situations
* ERROR => designates error events that might still allow the application to continue running
* FATAL => severe error events that presumably lead the application to abort
* OFF => highest possible level, intended to turn off logging

