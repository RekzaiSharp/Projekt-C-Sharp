# Semgrep

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
````
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
````
Siehe auch: 
https://semgrep.dev/docs/ignoring-files-folders-code/