# qqwry-java

[![Build Status](https://api.travis-ci.org/jarod/qqwry-java.svg?branch=master)](https://travis-ci.org/jarod/qqwry-java)
[![Javadocs](http://www.javadoc.io/badge/com.github.jarod/qqwry-java.svg)](http://www.javadoc.io/doc/com.github.jarod/qqwry-java/0.7.1)


### usage:

Code sample:
```java
QQWry qqwry = new QQWry(); // load qqwry.dat from classpath

QQWry qqwry = new QQWry(Paths.get("path/to/qqwry.dat")); // load qqwry.dat from java.nio.file.Path

byte[] data = Files.readAllBytes(Paths.get("path/to/qqwry.dat"));
QQWry qqwry = new QQWry(data); // create QQWry with provided data

String myIP = "127.0.0.1";
IPZone ipzone = qqwry.findIP(myIP);
System.out.printf("%s, %s", ipzone.getMainInfo(), ipzone.getSubInfo());
// IANA, 保留地址用于本地回送
```

Gradle:
```groovy
dependencies {
   compile(
     "com.github.jarod:qqwry-java:0.7.+",
   )
}
```

Maven:
```xml
<dependency>
  <groupId>com.github.jarod</groupId>
  <artifactId>qqwry-java</artifactId>
  <version>0.7.0</version>
</dependency>
```

### build:

```
# OPTIONAL To embed qqwry.dat in the jar file, copy qqwry.dat to src/main/resources/qqwry.dat
# jar file will out put as ./build/lib/qqwry-java-X.X.X.jar
./gradlew jar
```

[纯真IP数据库格式详解](https://www.cnblogs.com/kjcy8/p/5787723.html)
