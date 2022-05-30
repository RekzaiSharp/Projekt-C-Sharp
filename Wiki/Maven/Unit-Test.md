**Unit-Tests** sind premade Tests welche auf Source-Code-Level, die erstellten Funktionen überpruft. Sie sind nur für Funktionen ausgelegt, welche ein Ergebnis Returnen. Sollte eine Funktion kein return-value haben, muss diese in [[Integration-Test]]s oder [[System-Test]]s geprüft werden.

Merkmale für einen Unit-Test:

-   Er kommuniziert NICHT mit der Database
-   Er kommuniziert NICHT über ein Netzwerk
-   Er berührt NICHT das file-system
-   Er kann gleichzeitig mit anderen Unit-Tests laufen
-   Er benötigt keine speziellen Änderungen um aufgerufen zu werden (an der config file beispielsweise)
- Kontextlos, aka Schnittstellen durch Mock-ups ersetzen welche konstant sind
- Testet einzelne Funktionen ohne Gesamtüberblick

https://www.testim.io/blog/unit-test-vs-integration-test/?utm_source=google&utm_medium=cpc&utm_campaign=dsa&utm_campaign=dsa&utm_term=&utm_medium=cpc&utm_source=google&hsa_kw=&hsa_mt=&hsa_grp=135707775003&hsa_tgt=dsa-41848713900&hsa_net=adwords&hsa_cam=17072377435&hsa_ver=3&hsa_acc=6463132548&hsa_src=g&hsa_ad=595903593764&gclid=Cj0KCQjw1tGUBhDXARIsAIJx01n5pDtjD4SjZbGS530WhKZ2O941fENudfBcYqSmEfOy_YpTxo2d210aAuNwEALw_wcB