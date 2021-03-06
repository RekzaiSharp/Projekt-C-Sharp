# Semgrep

Semgrep ist ein Tool zur semantischen Analyse des Codes auf Vulnerabilities und Secrets.

Die Reports dienen den Entwicklern als Hilfe zum Schließen von (oftmals unwissentlich implementierten) Sicherheitslücken.

## Implementierung in die CI/CD-Pipeline

Semgrep kann über einen Docker-Container aufgerufen werden:
--> https://hub.docker.com/r/returntocorp/semgrep
<b>Eine lokale Installation ist dabei unnötig!</b>

Für die Implementierung müssen daher folgenden Informationen in den Job der gitlab-ci.yml:
````
[JOB DESCRIPTION]
 image: returntocorp/semgrep #der Docker-Container!
 script:
   - "semgrep ci --config auto"
````
(https://semgrep.dev/docs/semgrep-ci/overview/)


## Lokale Installation

#### Ubuntu/WSL/Linux/macOS
``python3 -m pip install semgrep

#### Docker
``docker run --rm -v "${PWD}:/src" returntocorp/semgrep --config=auto

## Konfiguration .semgrepignore
In der Konfigurationsdatei .semgrepignore können Dateien angegeben werden, die von Semgrep ignoriert werden sollen. Die Konfiguration von .semgrepignore erfolgt dabei äquivalent zu .gitignore:

- Es können ganze Dateinamen und Verzeichnispfade angegeben werden, getrennt nach Zeilen.
- Ein vorangestellter Punkt erlaubt das Ignorieren bestimmter Dateiendungen.
- Verzeichnispfade können absolut (z.B. c/Users/user1/Documents/cicdprojekt1/todolist/src/main/java/th/ab/demo/todolist/) oder relativ zum Arbeitsverzeichnis angegeben werden (todolist/src/main/java/th/ab/de/demo/todolist/), wobei bevorzugt relative Pfade angegeben werden sollten (wir können schließlich nicht vorhersagen, wie die Verzeichnisse in einem Container oder auf dem Server aufgebaut sind). 
- Ein * bedeutet, dass an dieser Stelle eine beliebige Anzahl an beliebigen Zeichen stehen kann. Möchte man beispielsweise die Dateien "todolist-1.jar", "todolist-2.jar", "todolist-3.jar" usw. ignorieren, schreibt man "todolist-\*.jar", und alle Dateien in diesem Format werden ignoriert.
- \# führt einen Kommentar an (wie in Python).

 ### Beispieldatei:
```
#Common large paths
node_modules/
build/
dist/
vendor/
.env/
.venv/
.tox/
*.min.js

# Common test paths
test/
tests/
*_test.go

# Semgrep rules folder
.semgrep

# Semgrep-action log folder
.semgrep_logs/
```
Siehe auch: 
https://semgrep.dev/docs/ignoring-files-folders-code/

## Regeln definieren
Es lassen sich auf verschiedene Weisen Regeln definieren. Normalerweise kann man mit dem oben genannten `semgrep ci --config auto` automatisch Regeln für sich finden lassen, was meistens auch funktioniert. Für uns wäre höchstens noch die Regeldefinition durch eine YAML file interessant.
Als erstes muss eine `rule.yaml` Datei erstellt und gefüllt werden.

Beispiel YAML file:
```
rules:
- id: is-comparison
  languages:
    - python
  message: The operator 'is' is for reference equality, not value equality! Use
  `==` instead!
  pattern: $SOMEVAR is "..."
  severity: ERROR
```

Beim semgrep Aufruf in der CI/CD Pipeline kann man mit dem folgendem Kommando die erstellen Regeln ausführen:
`semgrep --config path/to/rule.yaml`

Es lassen sich auch mehrere Regeln gleichzeitig ausführen lassen:
`semgrep --config p/python --config myrules/myrule.yaml`


##  Beispiele für Reports

- <b>Warnung:</b> MD5 is a weak hash which is known to have collision. Use a strong hashing function.
 --> Lösung: Auf einen sichereren Algorithmus (z.B. SHA256) umstellen.
 
 - <b>Warnung:</b> crypto.pseudoRandomBytes()/Math.random() is a cryptographically weak random number generator.
 --> Der Pseudo-RNG ist nur das: Pseudo. Der Algorithmus bevorzugt bestimmte Zahlen, basierend auf dem Seed und der genutzten Funktion, und kann geknackt werden.
 --> Lösung: einen besseren Random Number Generator recherchieren. Der Security-Experte  des Unternehmens wäre eine gute Quellen für <u>zertifizierte</u> RNGs.
 
- <b>Warnung:</b> User controlled data in eval() or similar function may result in Code Injection
--> Über Nutzereingaben wie z.B. Formularfelder können (schädliche) Skripte ausgeführt werden! Dies muss über <u>Validierung</u> der Eingabe verhindert werden.
Beispielsweise kann die Eingabe auf Sonderzeichen und Keywords, die für JavaScript/Typescript, SQL oder PHP-Befehle typisch sind ('\<script>', 'DROP TABLE', $) überprüft werden und diese gegebenenfalls entfernen oder "escapen" (etwa mit '\\' Backslash).
