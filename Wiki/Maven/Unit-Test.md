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

# Wie Implementiert man Unit-Tests?
![[Pasted image 20220608190647.png]]
Über den in Maven vorhandenen Command "mvn test" kann man [[2. unit-test]] ausführen. 

![[Pasted image 20220608191108.png]]
Um stattdessen einen [[3. integration-test]] durchzuführen, muss man nur "mvn test" mit "mvn verify" ersetzen.

Beide Befehle kann man ebenfalls mit dem Argument "Clean" erweitern, um die Zielablage zu leeren, bevor die Tests durchgeführt werden.

![[Pasted image 20220621110604.png]]



Source: https://jenkov.com/tutorials/maven/maven-commands.html