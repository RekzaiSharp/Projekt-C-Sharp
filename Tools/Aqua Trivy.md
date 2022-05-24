# Aqua Trivy

Trivy (<u>tri</u>gger en<u>vy</u>) ist ein Scanner-Tool  der Aqua Security zur Identifizierung von Vulnerabilities, Fehlkonfigurationen und geleakten Dingen, die nicht in die Öffentlichkeit gelangen sollen ("Secrets" wie Passwörter, Tokens etc.) in Containern (Docker, Kubernetes, Terraform).

Das Tool ist ein kostenfreies Open-Source-Projekt und auf GitHub verfügbar.

https://aquasecurity.github.io/trivy/v0.28.0/

## Installation
<u>PT-Installationsbefehl:</u>
```
sudo apt-get install wget apt-transport-https gnupg lsb-release
wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | sudo apt-key add -
echo deb https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main | sudo tee -a /etc/apt/sources.list.d/trivy.list
sudo apt-get update
sudo apt-get install trivy
```

<u>Binary (über GitHub)</u>
https://github.com/aquasecurity/trivy/releases/tag/v0.28.0

## Anwendung

Die folgenden Artefakte können von Trivy gescannt werden:

- Container Images und Kubernetes
- Dateisysteme und Rootfs
- Git-Repositories

Mögliche Modi sind <u>Standalone</u> und <u>Client/Server</u>
