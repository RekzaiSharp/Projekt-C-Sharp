# Git

DAS Versionsverwaltungs- und Konfigurationsmanagement-Tool!

## Die wichtigsten Konsolen-Befehle:
### git init

Initialisiert einen Ordner als lokales Git-Repository.

### git clone

"Klont" ein Remote Repository in den aktuellen Ordner. 
<b> Kann ausgeführt werden, ohne dass der Ordner als Git Repository angelegt wurde!</b>
Das Repository wird direkt in das aktuelle Working Directory geklont.

### git fetch

### git pull
Holt sich die aktuellen Dateien von einem Repository.

### git add
Fügt eine Datei dem Git Repository hinzu, sodass 

### git rm


### git commit
Sichert den aktuellen Arbeitsfortschritt (working tree) in einem sogenannten Commit.

### git push
Lädt den aktuellen Commit in ein Repository.

### git branch

- <b>-v</b>

	Verbose = erweiterte Informationen:  Aktueller Commit und Commit- Message
	
	<font color="cyan">PS C:\Users\stefa\Documents\cicdprojekt1> git branch -v</font>
	* <font color="green">development</font> 8985075 Update .gitlab-ci.yml file
  main        688d2ee [behind 1] Update .gitlab-ci.yml file
	
- <b>-vv</b>

	"Ultra-Verbose": enthält auch Informationen zum getrackten Repository für jeden Branch
	
<font color="cyan">PS C:\Users\stefa\Documents\cicdprojekt1> git branch -vv</font>
	* <font color="green">development </font>8985075 [origin/development] Update .gitlab-ci.yml file
	main        688d2ee [origin/main: behind 1] Update .gitlab-ci.yml file

### git remote
Zeigt alle Remote Repositories an, die für dieses Git registriert worden sind.
Gleiche Funktion wie <font color="cyan">git branch -r</font>.
