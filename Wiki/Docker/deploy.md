# Deploy
In dieser Aufgabe wird das fertige Docker Image aus unserer Container Registry auf die virtuelle Maschine deployed, wo dieses in einem Container ausgeführt wird. Anschließend soll der Zugriff auf die Anwendung über einen Link möglich sein.

Die notwendigen Daten finden wir als Gruppenvariablen in unserem GitLab:
![[Pasted image 20220608193015.png]]
Ganz links ist der Typ der Variablen angegeben. Key ist der Name und unter Value können wir den Wert sehen, welcher standardmäßig ausgeblendet ist, aber mit einem Klick eingeblendet oder kopiert werden kann. Ist eine Variable protected, dann kann diese nur in protected branches oder tags verwendet werden. Relevant sind für uns die Variablen ID_SSH (SSH-Schlüssel), SERVER_ADDR (Adresse der virtuellen Maschine) & SERVER_USER (User auf dem Server). 

Schauen wir uns aber mal den Code in der .yml-Datei an:
![[Pasted image 20220608193721.png]]
Ganz unten unter dem Punkt environment wird die Umgebung erstellt. Eine Umgebung gibt an, wo die Anwendung deployed wird und zeigt alle deployments (Versionen der Anwendung). Jedes Durchlaufen der Pipeline erzeugt ein neues deployment, wodurch die Verwaltung der Versionen besonders leicht ist. Unter "name" wird der Name festgelegt und unter "url" der Link zum Server, wo die Anwendung deployed werden soll.

Unter Script findet das eigentliche deployen statt:
- chmod og= $ID_SSH: Entzieht dem privaten Schlüssel alle Berechtigungen für die Gruppe und andere, sodass nur der Eigentümer ihn verwenden kann. Dies ist eine Voraussetzung, da SSH sonst die Arbeit mit dem privaten Schlüssel verweigert.
- ssh -i $ID_RSA -o StrictHostKeyChecking=no $SERVER_USER @ $SERVER_IP "command": Die vier SSH Befehle folgen alle der obigen Vorlage. Lediglich der "command"-Abschnitt wird geändert.
	- -i: steht für identity file und ist unsere ID_SSH-Datei.
	- -o StrictHostKeyChecking=no: stellt sicher, dass die Frage "Trauen Sie dem remote host?" umgangen wird, da diese in einem nicht-interaktiven Kontext, wie der Pipeline, nicht beantwortet werden kann. 
	- $SERVER_USER & $SERVER_ADDR: Variablen siehe weiter oben, spezifieren den remote host und login user für die SSH-Verbindung.
	- command: Befehle die auf dem Server ausgeführt werden sollen
- docker login: Logt Docker in unserer Container Registry ein, siehe publish-container
- docker pull: Pullt das aktuellste Image aus der Container Registry
- docker container rm: Sollte ein Container mit dem gleichen Namen existieren, so wird dieser gelöscht. Wir stellen so sicher, dass wir nicht mehrere Container haben, sondern stets nur einen. Das "|| true" stellt sich sicher, dass der exit-code erfolgreich ist, wenn kein Container gefunden wurde.
- docker run: Der Command startet einen Container mit dem spezifierten Image. Mit --name und dem folgenden Wort wird der Name für den Container festgelegt. Mit -p binden wir den Port 80 vom Host an den Port 8080 vom Container. Mit -d wird der Container im detached mode gestartet, da die Pipeline sonst nicht beenden würde und solange laufen würde, wie der Container läuft. Mit dem letzten $IMAGE_TAG spezifieren das auszuführende Image.