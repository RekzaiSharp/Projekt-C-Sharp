**Publish-Package** - In dieser Aufgabe wird das fertige Package von der CI/CD-Pipeline in die Package Registry von GitLab hochgeladen. Diese können dort veröffentlicht und geteilt werden, um in anderen Projekten als Abhängigkeit verwendet zu werden.

![[Pasted image 20220530142625.png]]

Wie oben auf dem Screenshot zu erkennen ist, wird eine weitere Datei namens "ci_settings.xml" benötigt. Außerdem müssen wir in der "pom.xml"-Datei das richtige Repository angeben. Die restlichen Schritte sind analog zu den anderen Schritten. Es wird zuerst in das Verzeichnis "todolist" gewechselt und anschließend wird der mvn-Befehl ausgeführt. Mit dem Attribut "only" legen wir fest, wann und welches Package in die Registry hochgeladen werden soll. Durch die aktuelle Einstellung wird nach jedem Commit im "development" Branch ein weiteres Package hochgeladen. Der "main" Branch wird dabei völlig ignoriert. 

Schauen wir uns jetzt den zugehörigen Abschnitt in der  "pom.xml"-Datei an.

![[Pasted image 20220530143748.png]]

In diesem Abschitt legen wir das Repository fest, indem die Packages gespeichert werden sollen. Die geschweiften Klammern repräsentieren predefinierte CI/CD-Variablen, welche die Adressen beinhalten. Alternativ können diese auch hard gecoded werden, was aber die Fehleranfälligkeit erhöhen würde und die Lesbarkeit verschlechtern würde. Für eine volle Liste aller CI/CD-Variablen könnt ihr auf den unteren Link klicken:
https://docs.gitlab.com/ee/ci/variables/predefined_variables.html

Damit wir auf das Registry zugreifen können, müssen wir uns authentifizieren. Dies erfolgt in der "ci_settings.xml"-Datei.

![[Pasted image 20220530144308.png]]

Unter Server wird die ID von der "pom.xml"-Datei aufgegriffen. Die Authentifizierung erfolgt durch einen "CI_JOB_TOKEN". Dieser wird verwendet, um sich an verschiedenen API Endpunkten zu authentifizieren. Der Token ist solange gültig, wie der Job läuft. Ist der Job abgeschlossen oder ähnliches, ist der Token nicht mehr gültig und wertlos.