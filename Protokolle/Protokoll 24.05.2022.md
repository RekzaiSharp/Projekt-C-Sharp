### Anwesenden
- [ ] Robin
- [ ] Max
- [ ] Nick
- [ ] Stefan
- [x] Daniel
- [ ] Kevin

### Agenda
- [x] Daily
- [x] Radiator
- [x] Gruppenarbeit
- [x] Mittag 11:45 - 12:45
- [x] Consulting 13:00 - 14:00 Uhr (echte Firma)
- [ ] Offizielles Ende 15:30

### Fürs Nächste mal
- [ ] 

# Mitschrift
![[Pasted image 20220524101914.png]]
![[Pasted image 20220524104935.png]]

Planning für das Meeting:
Wie können wir alte Pipelines automatisch löschen, um den belegten Speicher freizugeben? Aktuell: Clear runner caches + manuelle Deletion:
- artifakte expire (räumt nicht die builds)
- gitlab agents hinterlassen
	- volumes (repos) docker volume deleten zum freigeben
	- docker images
- eigene kleine Pipeline die genau diesen Befehl ausführt
- sceduels unter Github bsps

Sollen wir die ToDo Liste und den Juiceshop in jeweils eigenen Containern, oder direkt auf dem Runner laufen lassen:
- ????
- Dockerfile build
- können nebeneinander laufen

Tipps fürs Pipeline aufbauen:
- Welche Struktur hätte man gerne für die Pipeline? Am Anfang klären.
- Inspect in the Depth
- Erstmal zum laufen bringen, dann im Nachhinein fixen
- Tools abhängig vom basis image (Docker beste Quelle für images, wenn Docker nicht will, dann selber bauen) (LTS Versionen nutzen statt dauerhaftem Updaten)

Soucen für Fehlerquellen:
- Stackoverflow
- Back exchange
- Doku für die yml lesen, oft wertvolle Infos
- Reference Guides

Sceduling wann/wie oft:
- Kommt auf den branch / dasRisiko an
- teure (lange) Sachen nicht immer
- security tests müssen regelmäßig gemacht werden (1/Tag)

Wann und was cachen:
- Maven-repos local cached
- häufig verwendete Elemente
- sind NICHT für Datenaustausch

repository pom file distribution management:
- auf Git selber unter package registry
- ist für eigene packages!
- snapshot Versionen (darf man ändern) -> finales release (darf nicht mehr geändert werden)

Gitlab auto devops
- nicht empfehlenswert?

aws: lambda 
Google: cloud functions