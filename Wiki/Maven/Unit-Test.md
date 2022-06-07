**Unit-Tests** sind premade Tests welche auf Source-Code-Level, die erstellten Funktionen überprüft. Sie sind nur für Funktionen ausgelegt, welche ein Ergebnis Returnen. Sollte eine Funktion kein return-value haben, muss diese in [[3. integration-test]]s oder [[System-Test]]s geprüft werden.

Merkmale für einen Unit-Test:

-   Er kommuniziert NICHT mit der Database
-   Er kommuniziert NICHT über ein Netzwerk
-   Er berührt NICHT das file-system
-   Er kann gleichzeitig mit anderen Unit-Tests laufen
-   Er benötigt keine speziellen Änderungen um aufgerufen zu werden (an der config file beispielsweise)
- Kontextlos, aka Schnittstellen durch Mock-ups ersetzen welche konstant sind
- Testet einzelne Funktionen ohne Gesamtüberblick

https://www.testim.io/blog/unit-test-vs-integration-test/