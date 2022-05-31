# .gitlab-ci.yml

Die Konfigurationsdatei, um die GitLab CI/CD-Pipeline tun zu lassen, was wir wollen.

Die Datei im aktuellen Zustand (31.05.22), kommentiert:
```
image: maven:latest
include:

  - template: Security/Secret-Detection.gitlab-ci.yml

stages: # legt die Stages für die CI/CD-Pipeline feset

    - build

    - test

    - release

  

build-job: # was wird im build-job erledigt

    stage: build

    script: # Skripte, die im Terminal ausgeführt werden

        - "cd todolist"

        - "mvn compile"

  

unit-test-job:

    stage: test

    script:

        - "cd todolist"

        - "mvn test"

  

integration-test-job:

    stage: test

    script:

        - "cd todolist"

        - "mvn verify"

  

static-application-secruity-test:

    image: returntocorp/semgrep

    stage: test

    script:

        - "cd todolist"

        - "semgrep ci --config=auto"

  

release-jar:

  stage: release

  script:

    - cd todolist

    - git checkout -B "$CI_BUILD_REF_NAME"

    - mvn -B -DtagNameFormat="@{project.artifactId}" -DscmCommentPrefix="[skip ci]" release:prepare release:perform
```

https://devsecops.emceeo.de/help/ci/yaml/index

## Fun facts über YAML
- YAML steht für "YAML Ain't A Markup Language". Es handelt sich um eine menschenlesbare Sprache zur Datenserialisierung
- Wie Python werden Abschnitte durch Einrückung untergliedert. 
- <b> DIE EINRÜCKUNGEN SOLLTEN NIEMALS MIT DER TABULATORTASTE ERFOLGEN, SIE MACHEN DIE DATEI IM SCHLIMMSTEN FALL UNBRAUCHBAR!</b>
- Kommentaren wird das '#' vorangestellt (ebenfalls wie in Python).