---
layout: post
title: "Add Maven Plugin for Aspect"
date: 2016-05-18 11:33pm
---

Trying to add spring aop to my S2SH practice project. Somehow, my advice can't be called at all, though my configuration 
is totally correct.

After some googling finally find out need to add aspect plugin for maven and dependency. 

Dependency:

```xml
    <dependency>
      <groupId>org.aspectj</groupId>
      <artifactId>aspectjrt</artifactId>
      <version>1.8.7</version>
    </dependency>
```

Plugin:

```xml
      <plugin>
        <groupId>org.codehaus.mojo</groupId>
        <artifactId>aspectj-maven-plugin</artifactId>
        <version>1.8</version>
        <executions>
          <execution>
            <goals>
              <goal>compile</goal>       <!-- use this goal to weave all your main classes -->
              <goal>test-compile</goal>  <!-- use this goal to weave all your test classes -->
            </goals>
          </execution>
        </executions>
      </plugin>
```

Reference: [codehaus-mojo document](http://www.mojohaus.org/aspectj-maven-plugin/usage.html)
