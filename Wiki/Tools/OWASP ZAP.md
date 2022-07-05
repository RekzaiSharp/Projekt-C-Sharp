# OWASP ZAP
--> **O**pen **W**eb **A**pplication **S**ecurity **P**roject - **Z**ed **A**ttack **P**roxy

## Website
https://www.zaproxy.org/

Ein Open-Source-Tool von OWASP, das einen dynamischen Penetration Test ("Pentest") von Webanwendungen ermöglicht.

Diese werden für gewöhnlich manuell durch einen Security-Experten ausgeführt, der auch die Expertise besitzt, den Zed Attack Proxy optimal zu konfigurieren (auf Basis der Business-Logik des Systems z.B.). Dies war auch das ursprüngliche Ziel für OWASP ZAP: ein Tool zur Unterstützung der Security-Experten bei ZAP-Tests. Die automatische Einbindung in eine CI/CD-Pipeline ist ein neueres Feature von OWASP ZAP.

ZAP funktioniert wie eine "Man-in-the-Middle"-Attack: es versucht als Proxy zwischen dem Browser und der Webapplikation Nachrichten abzufangen, ihre Inhalte auszulesen und zu modifizieren.

Das Tool ist als Desktop-Version verfügbar, lässt sich aber in die CI/CD-Pipeline einbinden (siehe "Anwendung").

## Installation

OWASP ZAP ist für verschieden Betriebssysteme und Docker verfügbar.
https://www.zaproxy.org/download/

Weitere Plugins und Addons können in der Applikation über den ZAP Marketplace heruntergeladen werden:
https://www.zaproxy.org/addons/

Der GitHub Marketplace enthält OWASP ZAP als vorgefertigte Actions:
https://github.com/marketplace?query=owasp+zap

## Anwendung

#### Desktop:
https://www.zaproxy.org/getting-started

#### Automatisierung mittels Docker-Container:
https://www.zaproxy.org/docs/docker/

#### Weitere Automatisierung über YAML-Datei:
https://www.zaproxy.org/docs/automate/automation-framework/

## Baseline Scan vs. Full Scan
Für OWASP ZAP sind zwei Modi verfügbar: Baseline Scan und Full Scan

### Baseline Scan
`` zap-baseline.py -t <target> [options]

Der Baseline Scan ist standardmäßig auf einen Scan durch die Spider auf eine Minute limitiert und führt <u>keine</u> Angriffe auf die Webanwendung aus, sondern sammelt nur die passiven Meldungen, die dabei entstehen.

Weitere  Informationen und Optionen siehe hier:
https://www.zaproxy.org/docs/docker/baseline-scan/

### Full Scan
``zap-full-scan.py -t <target> [options]

Im Gegensatz zum Baseline Scan versucht ZAP einen vollständigen, zeitlich unlimitierten (per Default) Penetration Test mit den folgenden Schritten:
1. Eine Spider crawlt über die angegebene Webanwendung (siehe "Spider").
2. Optional: Eine AJAX (*Asynchronous JavaScript and XML*) Spider versucht, weitere Schwachstellen der Webanwendung zu finden.
3. Die gefundenen Seiten werden einen vollständigen Scan unterzogen.
4. Ausgabe der Report-Datei.


Weitere  Informationen und Optionen siehe hier:
https://www.zaproxy.org/docs/docker/full-scan/

## Spider
Eine Spider ist ein Programm, die eine Webseite oder Webapplikation nach Links absucht und diese zur weiteren Verarbeitung/Untersuchung sichert (auch "Crawler" genannt).

## Wiki
Eine Wiki für OWASP ZAP ist auf GItHub verfügbar:
https://github.com/zaproxy/zaproxy/wiki


## Beispiele für Reports

- <b>Backup File Disclosure</b>
	--> Automatisch generierte Backup-Dateien werden oft mit Zeichen wie "dateiname1.xml" oder "dateiname.xml.bk" versehen. Diese sollten <u>unbedingt</u> gelöscht werden (gerne auch automatisiert), um externen Zugriff und Manipulation zu verhindern.
	--> Aus dem gleichen Grund sollten Backup-Dateien <u>nicht</u> von Hand auf dem Server ("in-situ") bearbeitet werden! Hierfür sollte die Deployment-Pipeline genutzt werden.
 