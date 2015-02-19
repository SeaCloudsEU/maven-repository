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

<!-- used by cloudfoundry-client-lib : temporary solution -->
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-webmvc</artifactId>
	<version>${spring.framework.version}</version>
</dependency>
<dependency>
	<groupId>org.springframework.security.oauth</groupId>
	<artifactId>spring-security-oauth2</artifactId>
	<version>${spring.security.oauth.version}</version>
	<exclusions>
		<exclusion>
			<groupId>org.springframework</groupId>
			<artifactId>spring-jdbc</artifactId>
		</exclusion>
	</exclusions>
</dependency>
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-test</artifactId>
	<version>${spring.framework.version}</version>
	<scope>test</scope>
</dependency>
<dependency>
	<groupId>org.apache.httpcomponents</groupId>
	<artifactId>httpclient</artifactId>
	<version>4.3.6</version>
</dependency>
<dependency>
	<groupId>com.fasterxml.jackson.core</groupId>
	<artifactId>jackson-databind</artifactId>
	<version>${jackson.version}</version>
</dependency>
<dependency>
	<groupId>com.google.protobuf</groupId>
	<artifactId>protobuf-java</artifactId>
	<version>2.6.1</version>
</dependency>
<dependency>
	<groupId>commons-io</groupId>
	<artifactId>commons-io</artifactId>
	<version>2.1</version>
</dependency>
<dependency>
	<groupId>com.esotericsoftware.yamlbeans</groupId>
	<artifactId>yamlbeans</artifactId>
	<version>1.06</version>
</dependency>
<dependency>
	<groupId>com.fasterxml.jackson.core</groupId>
	<artifactId>jackson-core</artifactId>
	<version>${jackson.version}</version>
</dependency>
<dependency>
	<groupId>org.apache.tomcat.embed</groupId>
	<artifactId>tomcat-embed-websocket</artifactId>
	<version>${tomcat.version}</version>
</dependency>
<dependency>
	<groupId>org.apache.tomcat</groupId>
	<artifactId>tomcat-juli</artifactId>
	<version>${tomcat.version}</version>
</dependency>
<dependency>
	<groupId>org.hamcrest</groupId>
	<artifactId>hamcrest-all</artifactId>
	<version>1.1</version>
	<scope>test</scope>
</dependency>
<dependency>
	<groupId>org.mockito</groupId>
	<artifactId>mockito-core</artifactId>
	<version>1.9.5</version>
	<scope>test</scope>
</dependency>
<dependency>
	<groupId>org.eclipse.jetty</groupId>
	<artifactId>jetty-server</artifactId>
	<version>${jetty.version}</version>
	<scope>test</scope>
</dependency>
<dependency>
	<groupId>org.eclipse.jetty</groupId>
	<artifactId>jetty-servlet</artifactId>
	<version>${jetty.version}</version>
	<scope>test</scope>
</dependency>
<dependency>
	<groupId>org.eclipse.jetty</groupId>
	<artifactId>jetty-servlets</artifactId>
	<version>${jetty.version}</version>
	<scope>test</scope>
</dependency>
<dependency>
	<groupId>log4j</groupId>
	<artifactId>log4j</artifactId>
	<version>1.2.14</version>
	<scope>test</scope>
</dependency>
<dependency>
	<groupId>org.jboss.byteman</groupId>
	<artifactId>byteman-bmunit</artifactId>
	<version>${byteman.version}</version>
	<scope>test</scope>
</dependency>


<properties>
	<spring.framework.version>4.0.5.RELEASE</spring.framework.version>
	<spring.security.oauth.version>2.0.4.RELEASE</spring.security.oauth.version>
	<jackson.version>2.3.3</jackson.version>
	<tomcat.version>8.0.15</tomcat.version>
	<jetty.version>8.1.12.v20130726</jetty.version>
	<byteman.version>2.1.3</byteman.version>
</properties>
```
	
	
