# Aqua Trivy

Trivy (<u>tri</u>gger en<u>vy</u>) ist ein Scanner-Tool  der Aqua Security zur Identifizierung von Vulnerabilities, Fehlkonfigurationen und geleakten Dingen, die nicht in die Öffentlichkeit gelangen sollen ("Secrets" wie Passwörter, Tokens etc.) in Containern (Docker, Kubernetes, Terraform).

Das Tool ist ein kostenfreies Open-Source-Projekt und auf GitHub verfügbar.

https://aquasecurity.github.io/trivy/v0.28.0/

## Installation
<u>APT-Installationsbefehl:</u>
```
sudo apt-get install wget apt-transport-https gnupg lsb-release
wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | sudo apt-key add -
echo deb https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main | sudo tee -a /etc/apt/sources.list.d/trivy.list
sudo apt-get update
sudo apt-get install trivy
```

<u>Binary (über GitHub)</u>
https://github.com/aquasecurity/trivy/releases/tag/v0.28.0

<u>Docker</u>

```
docker pull aquasec/trivy:0.28.0
```

```
docker run --rm -v [YOUR_CACHE_DIR]:/root/.cache/ aquasec/trivy:0.28.0 image [YOUR_IMAGE_NAME]
```

## Anwendung

Die folgenden Artefakte können von Trivy gescannt werden:

- Container Images und Kubernetes
- Dateisysteme und Rootfs
- Git-Repositories

Im Folgenden werden die Anwendungsfälle "nach Vulnerabilities scannen", "nach Miskonfigurationen scannen" und "nach Secrets scannen"


## Vulnerabilities

<b>Ein Image nach Vulnerabilities scannen:</b>

``$ trivy image [YOUR_IMAGE_NAME]

(Siehe hierzu auch: 
https://aquasecurity.github.io/trivy/v0.28.0/docs/vulnerability/scanning/image/)

<b>Einen Dateipfad scannen (file system)</b>

``$ trivy fs [Dateipfad]

<b>Trivy im Server Mode laufen lassen</b>

``$ trivy server

Anschließend mittels --server Trivy als Client über den Server laufen lassen, z.B.:

``$ trivy fs --server http://localhost:4954 --severity CRITICAL ./integration/testdata/fixtures/fs/pom/


## Misconfigurations