# Was ist CI/CD?

- CI = Continuous Integration
- CD = Continuous Delivery/Deployment
-> Eine Methode, um den Software-Entwicklungsprozess zu automatisieren

- Die Automatisierung beinhaltet u.a.:
	- Build (das "Zusammenstellen" der Software)
	- Testing
	- Deploy

- Die Schritte, die in den CI/CD-Prozess gehören, nennen sich <u>Stages</u>.
- Der gesammte CI/CD-Prozess ist zu einer <u>Pipeline</u> zusammengefasst, der die Stages in einer bestimmten Reihenfolge automatisch ausführt.

# CI/CD in GitLab
- In GitLab wird der CI/CD-Prozess mit Hilfe der Datei <font color= "yellow"> .gitlab-ci.yml </color> definiert. Sie kommt in das Hauptverzeichnis des GitLab-Repository.
	-> Die Dateiendung .yml verweist darauf, dass sie in der Auszeichnungssprache YAML geschrieben wird:
	https://de.wikipedia.org/wiki/YAML
	https://docs.gitlab.com/ee/ci/yaml/index.html
- Zur Ausführung der Pipeline benötigt man einen sog. Runner. Dieser lässt sich für das GitLab-Repository konfigurieren. <b> Aus Sicherheits- und Performancegründen sollte es aber auf einem anderen System laufen als das Repository.</b> (Ist hierfür der externe Server gedacht?) Der Runner muss also für das Repository registriert sein: https://docs.gitlab.com/runner/