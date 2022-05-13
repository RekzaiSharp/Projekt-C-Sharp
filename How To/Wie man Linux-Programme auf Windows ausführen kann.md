# Wie man Linux-Programme auf Windows ausführen kann

Autor: [[Stefan]]

Eins vorneweg: auf unserem GitLab-Server, auf dem wir auch unseren Runner laufen lassen, läuft bereits eine Linux-Distribution. Wenn man aber versucht, bestimmte Programme für unser Projekt auf dem eigenen Windows-Rechner laufen zu lassen, stößt schnell auf Probleme.
Zum Beispiel beim Versuch, semgrep laufen zu lassen, wird man unweigerlich auf folgende Fehlermeldung stoßen (zumindest war das bei mir so):

![[Pasted image 20220511155321.png]]
<font color="red">No module named 'resource' </font>
Okay, dann installiere ich einfach das Modul 'resource', oder?
![[Pasted image 20220511155439.png]]
<font color="red">Requirement already satisfied:</font>
Höh. So ein Mist.

Eine Recherche hat ergeben, dass dieses Modul <i>unbedingt</i> auf einem Linux-Betriebssystem ausgeführt werden muss, damit es funktioniert. Darum hier die Anleitung:

## 1. WLS installieren
Das Windows Subsystem for Linux sorgt dafür, dass man Linux-Applikationen auch auf einem Windows-Rechner ausgeführt werden können.

Die Installation erfolgt über folgenden Befehl in der Eingabeaufforderung bzw. dem Power-Shell-Terminal:
`wsl --install

Man kann über das Argument -d auch eine der folgenden Linux-Distributionen installieren:
- Ubuntu
- OpenSUSE Leap 42
- SUSE Linux Enterprise Server 12
- Kali Linux
- Debian GNU

`wsl --install -d <Name der Distribution>`

Für Ubuntu (das BS meiner Wahl) also:
`wsl --install -d Ubuntu

Okay, lassen wir den Rechner ein wenig arbeiten und es installieren.
Nach fertiger Installation erscheint im Startmenü das neue Betriebssystem als Applikation.
![[Pasted image 20220511160935.png]]

Im Explorer wird außerdem ein virtuelles Laufwerk angelegt.
![[Pasted image 20220511160744.png]]
(Docker hat anscheinend bereits eigene Linux-Distributionen angelegt.)

## 2. Das Betriebssystem einrichten
Nun lässt sich unser Linux-Betriebssystem durch Öffnen der neu angelegten Applikation starten.
Beim ersten Start muss erst einmal ein neuer Nutzer eingerichtet werden, mit Passwort etc. Es handelt sich NICHT um ein Betriebssystem mit graphischer Benutzeroberfläche, daher erfolgt alles in der Konsole (wie retro...).

Hat man sich einen neuen Benutzeraccount erstellt, fragt man sich:
<b>WO SIND MEINE DATEN?</b>

![[Pasted image 20220511162421.png]]

Antwort: Noch nicht da. Sie müssen mit dem Befehl
`cd /mnt/` (Achtung: cd nicht vergessen, / statt \; /mnt/ steht für "mount") 
in Linux eingebunden werden, bei jedem Start.

![[Pasted image 20220511162516.png]]
Die Festplatten sind nun mit dem Laufwerksbuchstaben erreichbar, z.B.
`cd c`
(Linux kennt normalerweise keine Laufwerkszuordnung über Buchstaben).

## 3. Mit WSL arbeiten
Jetzt kann man schön die Linuxkommandos nutzen. Um beispielsweise Semgrep zu installieren, geben wir ein:
`pip install semgrep

Und nachdem wir in den Ordner mit unseren Projektdateien gewechselt sind:
`semgrep --config auto

![[Pasted image 20220511163144.png]]

<b>Yippie! Es läuft!</b>

## Quelle und weiterführende Tipps:

https://www.freecodecamp.org/news/how-to-run-linux-apps-on-windows-10-11-using-wsl/