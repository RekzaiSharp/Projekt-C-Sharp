# Build
Maven basiert auf dem zentralen Konzept eines Build-Lebenszyklus. Das bedeutet, dass der Prozess zum Erstellen und Verteilen eines bestimmten Artefakts (Projekts) klar definiert ist.

Für die Person, die ein Projekt erstellt, bedeutet dies, dass es nur notwendig ist, einen kleinen Satz von Befehlen zu lernen und das Project Object Model (POM) stellt sicher, dass die Person die gewünschten Ergebnisse erhält.

Der Build-Lebenszyklus wird durch eine Folge von Build-Phasen definiert, wobei eine Build-Phase eine Stufe im Lebenszyklus darstellt. Diese Lebenszyklusphasen werden nacheinander ausgeführt, um den Standardlebenszyklus abzuschließen.

Die folgenden Phasen sind Teil des Standardlebenszyklus:
-   **validate**: validate the project is correct and all necessary information is available
-   **compile**: compile the source code of the project
-   **test**: test the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed
-   **package**: take the compiled code and package it in its distributable format, such as a JAR.
-   **integration-test**: process and deploy the package if necessary into an environment where integration tests can be run
-   **verify**: run any checks to verify the package is valid and meets quality criteria
-   **install**: install the package into the local repository, for use as a dependency in other projects locally
-   **deploy**: done in an integration or release environment, copies the final package to the remote repository for sharing with other developers and projects.

Um ein Projekt nun bauen zu können, müssen wir eine "pom.xml" Datei anlegen. Diese beinhaltet das POM und ist essenziell für die Arbeit mit Maven, da hier alle wichtigen Informationen über unser Projekt enthalten sind.
Schauen wir uns nun den grundlegenden Aufbau einer "pom.xml" Datei an:
```
1.  <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
2.    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
3.    <modelVersion>4.0.0</modelVersion>

5.    <groupId>th.ab.demo</groupId>
6.    <artifactId>todolist</artifactId>
7.    <version>0.0.1-SNAPSHOT</version>
8.    <description>A simple Todo-List </description>
9.    <name>todolist</name>

11.    <properties>
12.      <java.version>11</java.version>
13.    </properties>

15.    <dependencies>
16.      <dependency>
17.        <groupId>junit</groupId>
18.        <artifactId>junit</artifactId>
19.        <version>4.11</version>
20.        <scope>test</scope>
21.      </dependency>
22.         ... weitere Abhängigkeiten
23.    </dependencies>

25.    <build>
26.      <pluginManagement>
27.         ... hilfreiche Plugins
28.      </pluginManagement>
29.    </build>
30.  </project>
```

Das top-level Element in allen pom.xml Dateien ist das "project". Alle anderen Elemente sitzen innerhalb des project tags. 
Das Element "modelVersion" zeigt an, welche Version des object models die POM verwendet. 
Die "groupId" ist die ID der Gruppe oder der Organisation, die dieses Projekt erstellt hat.
Die "artifactId" ist ein Teil des Names für das primäre Artefakt, welches generiert wird. In unserem Falle ist das primäre Artefakt eine JAR Datei. 
Der zweite Teil des Namens ist die "version". Dieses Element gibt an, welche Version des Artefaktes generiert wird. Der einzigartige Name des primären Artefaktes setzt sich somit aus der "artifactId" und der "version" zusammen (z.B. todolist-0.0.1-SNAPSHOT.jar).
Das Element "name" ist der Anzeigename für das Projekt. Dieser wird in Dokumentationen verwendet, welche von Maven generiert werden.
Das Element "properties" enthält Platzhalter Werte, welche von überall in der POM erreichbar und verwendbar sind.
Die "dependencies" sind alle Abhängigkeiten, die das Projekt besitzt.
Das "build" Element kümmert sich um die Plugins und der Struktur des Projektverzeichnisses.