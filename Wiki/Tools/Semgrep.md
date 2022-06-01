# Semgrep

## Implementierung in die CI/CD-Pipeline

Semgrep kann über einen Docker-Container aufgerufen werden:
--> https://hub.docker.com/r/returntocorp/semgrep
<b>Eine lokale Installation ist dabei unnötig!</b>

Für die Implementierung müssen daher folgenden Informationen in den Job der gitlab-ci.yml:
````
[JOB DESCRIPTION]
 image: returntocorp/semgrep #der Docker-Container!
 script:
   - "semgrep ci --config auto"
````
(https://semgrep.dev/docs/semgrep-ci/overview/)


## Lokale Installation

#### Ubuntu/WSL/Linux/macOS
``python3 -m pip install semgrep

#### Docker
``docker run --rm -v "${PWD}:/src" returntocorp/semgrep --config=auto

