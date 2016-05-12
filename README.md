------------
Maven Setup
------------
* Download jdk and install 
	- default window path  = C:\Program Files\Java\jdk1.8.0_91\bin
	- Setup bin path in environment path 
	- Create JAVA_HOME=C:\Program Files\Java\jdk1.8.0_91
* Download maven and setup bin path in environment "path" variable  
	- default window path = C:\apache-maven-3.3.9\bin
	- https://maven.apache.org/

---------------
Build Lifecycle
---------------
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

--------------------
01-SimpleJavaProject
--------------------
* Demo of how to create basic java project.
* mvn archetype:generate -DgroupId=com.mycompany -DartifactId=01-SimpleJavaProject  -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
* Generates directory structure as below 
	01-SimpleJavaProject
		pom.xml
		--\src
			--\main\java\com\mycompany\App.java
			--\test\java\com\mycompany\AppTest.java
			--\target\01-SimpleJavaProject-1.0-SNAPSHOT.jar
	
* How to run compile file
	- java -cp target/01-SimpleJavaProject-1.0-SNAPSHOT.jar  com.mycompany.App	
