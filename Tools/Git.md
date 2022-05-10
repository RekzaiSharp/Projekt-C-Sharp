# Git

DAS Versionsverwaltungs- und Konfigurationsmanagement-Tool!

### git init

Initialisiert einen Ordner als lokales Git-Repository.

### git clone

"Klont" ein Remote Repository in den aktuellen Ordner. 
<b> Kann ausgeführt werden, ohne dass der Ordner als Git Repository angelegt wurde!</b>

### git fetch

### git pull

### git push

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
