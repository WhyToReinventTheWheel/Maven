--------------------
Get start with Maven
--------------------
* Setup 
	* https://maven.apache.org/
	* Download jdk and install 
		- default window path  = C:\Program Files\Java\jdk1.8.0_91\bin
		- Setup bin path in environment path 
		- Create JAVA_HOME=C:\Program Files\Java\jdk1.8.0_91
	* Download maven and setup bin path in environment "path" variable  
		- default window path = C:\apache-maven-3.3.9\bin
	
* https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html 
* https://maven.apache.org/guides/getting-started/index.html
	- What is Maven?
	- How can Maven benefit my development process?
	- How do I setup Maven?
	- How do I make my first Maven project?
	- How do I compile my application sources?
	- How do I compile my test sources and run my unit tests?
	- How do I create a JAR and install it in my local repository?
	- What is a SNAPSHOT version?
	- `How do I use plugins?` 
	- How do I add resources to my JAR?
	- `How do I filter resource files?`
	- `How do I use external dependencies?`
	- How do I deploy my jar in my remote repository?
	- How do I create documentation?
	- How do I build other types of projects?
	- How do I build more than one project at once?
* https://maven.apache.org/general.html
	- How do I prevent "[WARNING] Using platform encoding (Cp1252 actually) to copy filtered resources, i.e. build is platform dependent!"
	- How do I prevent including JARs in WEB-INF/lib? I need a "compile only" scope!
	- How do I list available plugins?
	- How do I determine what version of a plugin I am using?
	- `How do I set up Maven so it will compile with a target and source JVM of my choice?`
	- Is it possible to create my own directory structure?
	- Where is the source code? I couldn't seem to find a link anywhere on the Maven site.
	- Maven can't seem to download the dependencies. Is my installation correct?
	- I have a jar that I want to put into my local repository. How can I copy it in?
	- How do I unsubscribe from Maven mailing lists?
	- `How do I skip the tests?`
	- How can I run a single unit test?
	- Handle special characters in site
	- `How do I include tools.jar in my dependencies?`
	- Maven compiles my test classes but doesn't run them?
	- Where are Maven SNAPSHOT artifacts?
	- Where are the Maven XSD schemas?
	- Maven doesn't work, how do I get help?
	- How to produce execution debug output or error messages?
	- What is a Mojo?
	- How to find dependencies on public Maven repositories?

---------------
Build Lifecycle
---------------
https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html
* validate - validate the project is correct and all necessary information is available
* compile - compile the source code of the project
* test - test the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed
* package - take the compiled code and package it in its distributable format, such as a JAR.
* integration-test - process and deploy the package if necessary into an environment where integration tests can be run
* verify - run any checks to verify the package is valid and meets quality criteria
* install - install the package into the local repository, for use as a dependency in other projects locally
* deploy - done in an integration or release environment, copies the final package to the remote repository for sharing with other developers and projects.

--------------
Archetype List
--------------
* mvn archetype:generate	
* Archetype: what kind of project..Simple java,J2ee or spring application.

--------------------
01-SimpleJavaProject
--------------------
* https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html
* Demo of how to create basic java project.
* mvn archetype:generate -DgroupId=com.mycompany -DartifactId=01-SimpleJavaProject  -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
* Generates directory structure as below 
	- 01-SimpleJavaProject
		- pom.xml
		- --\src
			- --\main\java\com\mycompany\App.java
			- --\test\java\com\mycompany\AppTest.java
			- --\target\01-SimpleJavaProject-1.0-SNAPSHOT.jar
	
* How to run compile file
	- java -cp target/01-SimpleJavaProject-1.0-SNAPSHOT.jar  com.mycompany.App	

---------------
02-SimpleWebApp
---------------
 *  mvn archetype:generate -DgroupId=com.mk -DartifactId=02-SimpleWebApp -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false
	OR  
 * mvn archetype:generate and find  org.apache.maven.archetypes:maven-archetype-webapp
 	- Define value for property 'groupId': : com.mk
	- Define value for property 'artifactId': : 02-SimpleWebAp
	- Define value for property 'version':  1.0-SNAPSHOT: :
	- Define value for property 'package':  com.mk:
 * Add Tomcat Plugin 
 * mvn install 
 * mvn tomcat:run
 * http://localhost:8080/02-SimpleWebApp/
 
