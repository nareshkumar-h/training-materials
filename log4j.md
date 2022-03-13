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
```
<?xml version="1.0" encoding="UTF-8"?>
<Configuration status="WARN">
    <Appenders>
        <Console name="Console" target="SYSTEM_OUT">
            <PatternLayout pattern="%d{HH:mm:ss.SSS} %-5level - %msg%n"/>
        </Console>
    </Appenders>
    <Loggers>
        <Root level="info">
            <AppenderRef ref="Console"/>
        </Root>
    </Loggers>
</Configuration>
```
