#### Protokoll zum Expertenmeeting am 14.06.

<u>C-Sharps</u> (Stefan)

1. Q: Die Jobs in Maven werden immer bis zum angegebenen Job ausgeführt. Haben Sie hierfür "Best Practices", die Sie uns mitgeben können?
	A: 
	- Die Maven Stages sind aufgrund ihrer Funktionalität an die Maven Jobs gebunden (ein Programm kann erst dynamisch getestet werden, nachdem es gebuildet wurde). 
	- Bei Anwendung auf einem <u>lokalen System</u> kann jede Stage einzeln ausgeführt werden (wichtig hierbei ist, dass der Fortschritt nicht durch das Argument "clean" zurückgesetzt wird)!
	- Das gilt leider nicht für die Anwendung von Maven in einer CI/CD-Pipeline. Hier können aber die Target-Ordner in die nächste Stage gepackt werden. Dies ist aber auch nicht immer sinnvoll.
	- --> Es gibt kein "Best Practice" beim Umgang mit den Maven Stages. Man versucht es, bestmöglich für sein Projekt zu konfigurieren.

2. Q: Können wir mit Hilfe des Caches die Ergebnisse eines Maven Jobs in den nächsten exportieren?
	A: Der Cache ist nicht persistent, daher sollte man das nicht machen. Ein besserer Weg ist es, die Artefakte in die nächste Stage zu übernehmen.

3. Q: Auf welche Secrets sollten wir noch achten, die nicht schon durch die Vorkonfiguration von Semgrep/ GitLeaks/ Trivy gesucht werden?
	A: 
	- Am besten ist es, solche Secrets gar nicht erst in die Projektdateien einzubauen. Ganz wichtig: was einmal in einem Git Commit gesichert wurde, lässt sich nur schwer wieder entfernen (die Vorgängerversionen jeder Datei sind in den Commits gesichert!).
	- "git pre-commit hooks" [Link zu einer Erklärung](https://githooks.com/) sind Tools, die einem helfen können, dass Secrets im lokalen Repository nicht ins Remote Repository gelangen.
	- Ansonsten kümmert sich die GitLab CI bereits gut darum, Secrets z.B. nicht in der Konsole anzuzeigen.
	- Bei Security gilt: nichts selbst basteln, fertige Krypto- und Rechtemodule verwenden (die Firma unseres Experten verwendet die Tools des Cloudproviders).

<u>Smary Pants</u> (Anabel)

1. Q: Bei der Ausführung des Schritts package-deploy des Juice Shops werden Verzeichnisse gesucht, die nicht existieren.
	A: 
	- Wurden alle Daten korrekt heruntergeladen?
	- Das Repository wurde mittels Argument "--depth=1" geklont. Möglicherweise ist das der Fehler?
	- Es kommt vor, dass Dependencies nicht korrekt heruntergeladen werden. Eine schlechte Internetverbindung zum Zeitpunkt der Pipeline ist eine Möglichkeit, wieso dies nicht funktioniert.
	- --> Bei uns hat sich der Fehler mittlerweile behoben und lässt sich nicht wiederherstellen.
2. Q: Fehler bei der Ausführung des Befehls "npm clean install".
	A:
	- Der Speicherplatz auf dem Server ist ausgegangen!
	- Docker Images sollten regelmäßig (durch den Scheduler oder nach jeder Pipeline) mittels "docker image prune" gelöscht werden, sonst sind die 32 GB des Servers schnell voll.

<u>EDLV</u> (Max R.)

1. Q: Welche Befehle verwendet man zum Herunterladen und Weiterreichen von Artefakten (Maven und npm Packages)?
	A: 
	- Sie lassen sich über die Package Registry in GitLab herunterladen.
	--> Wieso sollte man sie lokal herunterladen wollen?
		--> Die Gruppe möchte es lokal ausführen und die Test Outputs herunterladen.
			--> Test Outputs sind von GitLab aufbereitete Testauswertungen. Diese kosten aber Geld.

2. Q: Warum erhalten wir die Meldung "permission denied" in der sast-stage (Juice Shop)?
	A: Im "sast-gitleaks"-Job ist der Befehl "chmod ugo =$ID_SSH" hinterlegt. Das ergibt keinen Sinn für diese Stage, zumal der SSH-Key noch nicht generiert wurde.

<u>Error404</u> (Frank)
1. Q: Wie führe ich Docker in Docker aus?
	A: Die Stages bekommen normalerweise immer das Image mit. In diesem können wiederum Docker-Befehle ausgeführt werden. Der Tag hierfür lautet "dind" ("Docker in Docker").
	Siehe https://devopscube.com/run-docker-in-docker/.
2. Q: Beim Klonen des Juice Shops heißt es, die DockerFile "sqlite3" sei nicht vorhanden?
	A: Im Zweifelsfall manuell nachinstallieren.
		--> Laut Error404 geht das nicht mehr. Aber bei Fr. Oetzel schon.
3. Q: Der Build, der vom Juice Shop erstellt wurde, scheint anders zu sein als der originale Build?
	A: 
	- Bei der Build-Stage sollte unbedingt die Versionsnummer mit angegeben werden!
	- Der Build kann nicht kaputt sein, er existiert bereits fertig im Juice Shop Repository. Vielleicht das Repository nochmal frisch klonen?
	- Auch hier kann es sein, dass die Dependency-Updates misslungen sind. Am besten nochmal bei stabilem Internet ausprobieren.
4. Q: Wir haben Speicherprobleme.
	A: 
	- Die Artefakte liegen bei GitLab ewig herum, wenn sie nicht automatisch durch den Scheduler oder manuell gelöscht werden.
	- Der Speicher wurde von Fr. Oetzel von 16 GB auf 32 GB erhöht.
	--> Möglicherweise ein Speicherleck. Fr. Oetzel soll über das Tool MCDU die Ursache überprüfen.
5. Q: "dast-stage" greift nicht auf das Registry zu?
	A: Irgendwie startet dast-stage als Erstes? Diese Stage mal per "Docker in Docker" (siehe oben) starten.