# NPM
Bei npm handelt es sich um einen Paketmanager für Softwarelösungen, der in der JavaScript-Laufzeit-Umgebung Node.js zum Einsatz kommt. Das zugehörige frei verfügbare Repository umfasst inzwischen mehrere Hunderttausend Einträge.

Die Buchstaben npm waren ursprünglich eine Abkürzung für „Node Package Manager“ – also für eine Lösung zum Packen von Software in der gleichnamigen JavaScript-Runtime-Umgebung. Allerdings prägte sich das Akronym derart ein, dass der ursprüngliche Name schließlich komplett aufgegeben wurde - die drei Buchstaben wurden zur offiziellen Bezeichnung.

# Die Funktionsweise von npm
Der zentrale Baustein von npm ist das Repository, die sogenannte „npm Registry“. Für eine professionelle Nutzung zum Zweck der Softwareentwicklung steht es unter einer freien Lizenz bereit. Für „private“ Projekte ist es auch möglich, auf eine kommerzielle Version zugreifen.
Ein Repository ist ein Verzeichnis von gespeicherten digitalen Objekten. Hier sind Code-Pakete zu finden. Diese stammen überwiegend von npm-Nutzern, die ihre eigene Software zur Verfügung stellen wollten. Sie mussten hierfür ihre Software mittels npm packen und übertragen.
Vereinfacht gesprochen ist npm also nichts weiter als ein automatisiertes und relativ intelligentes Verpackungssystem: Es erkennt, was verpackt werden soll, sucht die hierfür passende Verpackung aus und macht sich ans Werk. Anschließend wird ein Eintrag erstellt in der Bibliothek erstellt.

Der praktische Einsatz funktioniert über folgende Bausteine:
- Der CLI-Client gestattet den Download und die Installation der Software.
- Der Inhalt eines Pakets muss in JSON geschrieben sein
- "Name" und "Version" müssen in der Definitionsdatei vorhanden sein. Weitere zwingende Bedingungen gibt es nicht.
- Zudem bietet npm auch eine Abhängigkeitsverwaltung


[NPM](https://www.npmjs.com/) ist das Paket-Ökosystem von Node.js. Es ist das größte Ökosystem aller Open Source Bibliotheken der Welt, mit über 1 Million Paketen, Tendenz steigend. NPM ist kostenlos und tausende von Open Source Entwicklern tragen täglich dazu bei.

NPM wird mit einem Kommandozeilenprogramm ausgeliefert. Du kannst einfach auf der [Webseite von NPM](https://www.npmjs.com/search?q=keywords:packages) nach dem gewünschten Paket suchen und es mit einem einzigen Befehl installieren. Du kannst auch die Versionen deiner Pakete verwalten, Abhängigkeiten überprüfen und sogar eigene Skripte in deinen Projekten mit diesem Kommandozeilenprogramm einrichten. Ohne Zweifel ist NPM der beliebteste Besitz der Node.js-Community; Node.js zieht eine große Anzahl von Entwicklern vor allem wegen seines exzellenten Package Supports an.

### NPM-Pakete über CLI installieren
Wenn du Node.js installierst, wird NPM **automatisch mitinstalliert**. Wir haben in den vorherigen Abschnitten behandelt, wie man Node.js installiert, also lass uns jetzt einen Blick auf den Befehl werfen, um ein Paket mit NPM zu installieren:

> npm install package-name

Es können auch mehrere Pakete auf einmal installiert werden:

> npm install pk1 pk2 pk3

Sollte eine bestimme version installiert werden wollen kann das über folgenden Command erfolgen:

> npm install pk1@version
> npm install pk2:latest


<img src="https://kinsta.com/wp-content/uploads/2021/04/node-and-npm-version.png">

## <u>Nützliche Links:</u>

Hauptwebsite (Zum Suchen der Pakete): https://www.npmjs.com/
Command Cheat-Sheet: https://www.freecodecamp.org/news/npm-cheat-sheet-most-common-commands-and-nvm/