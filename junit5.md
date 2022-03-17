## JUnit 5

* Latest version of Junit is "5"
* Reference: https://junit.org/junit5/docs/current/user-guide/

#####  Add JUnit 5 Dependency

* Add Junit 5 jar
* Add surefire plugin

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>com.naresh</groupId>
	<artifactId>junit5-demo</artifactId>
	<version>0.0.1-SNAPSHOT</version>

	<properties>
		<maven.compiler.source>17</maven.compiler.source>
		<maven.compiler.target>17</maven.compiler.target>
	</properties>


	<dependencies>
		<dependency>
			<groupId>org.junit.jupiter</groupId>
			<artifactId>junit-jupiter-engine</artifactId>
			<version>5.8.2</version>
			<scope>test</scope>
		</dependency>

		<dependency>
			<groupId>org.junit.jupiter</groupId>
			<artifactId>junit-jupiter-api</artifactId>
			<version>5.8.2</version>
			<scope>test</scope>
		</dependency>

		<dependency>
			<groupId>org.junit.jupiter</groupId>
			<artifactId>junit-jupiter-params</artifactId>
			<version>5.8.2</version>
			<scope>test</scope>
		</dependency>

	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-surefire-plugin</artifactId>
				<version>2.22.0</version>
			</plugin>
		</plugins>
	</build>
</project>
```

##### Logic Class => Numbers.java
```java
package com.naresh;

public class Numbers {
	public static boolean isOdd(int number) {
		return number % 2 != 0;
	}
}
```


##### Test Case : TestNumbers.java

```java
import static org.junit.jupiter.api.Assertions.assertTrue;

import org.junit.jupiter.api.Test;
import org.junit.jupiter.params.ParameterizedTest;
import org.junit.jupiter.params.provider.ValueSource;

import com.naresh.Numbers;

public class TestNumbers {

	@Test
	public void testOddNumber() {
		assertTrue(Numbers.isOdd(3));
	}
	
	@ParameterizedTest
	@ValueSource(ints = {1, 3, 5, -3, 15}) 
	public void isOdd_ShouldReturnTrueForOddNumbers(int number) {
	    assertTrue(Numbers.isOdd(number));
	}

}
```
