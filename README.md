SeaClouds Maven repository
==================

![SeaClouds Project][SeaClouds-banner]
[SeaClouds-banner]: http://www.seaclouds-project.eu/img/header_test.jpg  "SeaClouds Project"

==================
How to use GitHub to host your own Maven repo
-------------------
http://kwebble.com/blog/2014/02/19/use-github-to-host-your-own-maven-repo

1. Clone
Clone the GitHub repository to your computer.

2. Install JAR
Place the JAR file in the local Git repository by letting Maven perform an install:
```
mvn install:install-file
 -DgroupId=[group-id]
 -DartifactId=[artifact-id]
 -Dversion=[version]
 -Dpackaging=[packaging-format]
 -Dfile=[path-to-file]
 -DlocalRepositoryPath=[path-to-git-repo]
```
[group-id], [artifact-id], [version] and [packaging-format] define the Maven properties of the file to install.
[path-to-file] is the path to the JAR file to install.
[path-to-git-repo] is the path to the local Git repository on your computer.

After successful execution of the command a folder structure is created in the local Git repository. This structure and the files in it make it usable as a Maven repo.

Commit & Publish
Commit the changes, that were made by executing the Maven install command, to the local Git repository.
Publish the updated repository to GitHub. The JAR file is now ready to be used in a Maven POM file.

cloudfoundry-client-lib usage
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
	
	
