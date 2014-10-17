#Github project parent pom

Parent pom for github maven projects. It contains scm setup according to user and repository name

##Getting Started

1. Add this repository to your pom.xml:
    ```xml
    <repository>
        <id>thenewmotion</id>
        <name>The New Motion Repository</name>
        <url>http://nexus.thenewmotion.com/content/repositories/releases-public</url>
    </repository>
    ```

2. Add <parent> block to your pom.xml:
    ```xml
    <parent>
        <groupId>com.thenewmotion</groupId>
        <artifactId>github-parent-pom</artifactId>
        <version>1.7</version>
    </parent>
    ```

3. Define github.repository and github.user properties in your pom.xml:
    ```xml
    <properties>
        <github.user>your github user</github.user>
        <github.repository>your github repository (not override to use artificatId) </github.repository>
    </properties>
    ```

4. Put this scm block due to [maven bug](http://jira.codehaus.org/browse/MNG-3244)
    ```xml
    <scm>
        <url>${github.repository.url}</url>
        <connection>${github.connection}</connection>
        <developerConnection>${github.connection}</developerConnection>
    </scm>
    ```