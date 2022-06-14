# Build
Maven basiert auf dem zentralen Konzept eines Build-Lebenszyklus. Das bedeutet, dass der Prozess zum Erstellen und Verteilen eines bestimmten Artefakts (Projekts) klar definiert ist.

Für die Person, die ein Projekt erstellt, bedeutet dies, dass es nur notwendig ist, einen kleinen Satz von Befehlen zu lernen, um ein beliebiges Maven-Projekt zu erstellen, und das POM stellt sicher, dass sie die gewünschten Ergebnisse erhält.

Der Build-Lebenszyklus wird durch eine Folge von Build-Phasen definiert, wobei eine Build-Phase eine Stufe im Lebenszyklus darstellt. Diese Lebenszyklusphasen werden nacheinander ausgeführt, um den Standardlebenszyklus abzuschließen.

Die folgenden Phasen sind Teil des Build-Lebenszyklus:
-   **validate**: validate the project is correct and all necessary information is available
-   **compile**: compile the source code of the project
-   **test**: test the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed
-   **package**: take the compiled code and package it in its distributable format, such as a JAR.
-   **integration-test**: process and deploy the package if necessary into an environment where integration tests can be run
-   **verify**: run any checks to verify the package is valid and meets quality criteria
-   **install**: install the package into the local repository, for use as a dependency in other projects locally
-   **deploy**: done in an integration or release environment, copies the final package to the remote repository for sharing with other developers and projects.
