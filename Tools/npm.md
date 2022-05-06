# Was ist npm?
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