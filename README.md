SeaClouds Maven repository
==================

![SeaClouds Project][SeaClouds-banner]
[SeaClouds-banner]: http://www.seaclouds-project.eu/img/header_test.jpg  "SeaClouds Project"

==================
How to use GitHub to host your own Maven repo
-------------------
http://kwebble.com/blog/2014/02/19/use-github-to-host-your-own-maven-repo



Usage
-------------------

In pom file:
```
<repositories>
	<repository>
	    <id>git-SeaCloudsEU</id>
	    <name>SeaCloudsEU's Git based repo</name>
	    <url>https://github.com/SeaCloudsEU/maven-repository/raw/master/</url>
	</repository>
</repositories>
```

```
<dependency>
	<groupId>eu.seaclouds</groupId>
	<artifactId>cloudfoundry-client-lib</artifactId>
	<version>1.1.0</version>
</dependency>
```
	
	
