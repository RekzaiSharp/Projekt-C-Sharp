# CICD Projekt 1 & 2
Unser Projekt wird mit der Hilfe der [CICD-Pipeline](CICD.md) und [Maven](Maven.md) compiled und getestet. 
Die CICD-Pipeline wird auf [GitLab](Tools/GitLab) über einen sogenannten [GitLab Runner](Wiki/GitLab/Runner) ausgeführt, dieser führt die von uns angegebenen Befehle innerhalb unserer [.yml](gitlab-ci.yml.md) Datei über einen [Docker](Docker.md) aus der auf einer [Virtuellen Maschiene](Virtual Machine) läuft.

**CICD Projekt 1 - Todo-List**
_Stages: build, test, sast, package, sca-package, publish, sca-container, dast, deploy, clean-storage_

**build:**                  [build](Wiki/CICD%20Jobs/todo%20list-Pipeline/1.%20build)
**test:**                    [unit test](Wiki/CICD%20Jobs/todo%20list-Pipeline/2.%20unit-test)
**test:**                    [integration test](Wiki/CICD%20Jobs/todo%20list-Pipeline/3.%20integration-test)
**sast:**                    [semgrep](Wiki/CICD%20Jobs/todo%20list-Pipeline/4.%20sast-semgrep)
**sast:**                    [gitleaks](Wiki/CICD%20Jobs/todo%20list-Pipeline/5.%20sast-gitleaks)
**package:**             [package-jar](Wiki/CICD%20Jobs/todo%20list-Pipeline/6.%20package-jar)
**sca-package:**      [sca-package-dependency-check](Wiki/CICD%20Jobs/todo%20list-Pipeline/7.%20sca-package-dependency-check)
**publish:**              [publish-package](Wiki/CICD%20Jobs/todo%20list-Pipeline/8.%20publish-package)
**publish:**              [publish-container](Wiki/CICD%20Jobs/todo%20list-Pipeline/9.%20publish-container)
**sca-container:**    [sca-container-trivy](Wiki/CICD%20Jobs/todo%20list-Pipeline/10.%20sca-container-trivy)
**dast:**                    [dast-zap](Wiki/CICD%20Jobs/todo%20list-Pipeline/11.%20dast-zap)
**deploy:**                [deploy](Wiki/CICD%20Jobs/todo%20list-Pipeline/12.%20deploy)
**clean-storage:**    [clean-storage](Wiki/CICD%20Jobs/todo%20list-Pipeline/13.%20clean-storage)


**CICD Projekt 2 - Juice Shop**
_Stages: packages, sast, sca-package, publish, sca-container, deploy, dast, clean-storage_

**package:**          [package](Wiki/CICD%20Jobs/Juice%20Shop-Pipeline/1.%20package)
**sast:**                  [semgrep](Wiki/CICD%20Jobs/Juice%20Shop-Pipeline/2.%20sast-semgrep)
**sast:**                  [gitleaks](Wiki/CICD%20Jobs/Juice%20Shop-Pipeline/3.%20sast-gitleaks)
**sca-package:**    [sca-package-dependency-check](Wiki/CICD%20Jobs/Juice%20Shop-Pipeline/4.%20sca-package-dependency-check)
**publish:**            [publish-container](Wiki/CICD%20Jobs/Juice%20Shop-Pipeline/5.%20publish-container)
**sca-container:**  [sca-container-trivy](Wiki/CICD%20Jobs/Juice%20Shop-Pipeline/6.%20sca-container-trivy)
**dast:**                 [dast-zap](Wiki/CICD%20Jobs/Juice%20Shop-Pipeline/7.%20dast-zap)
**deploy:**             [deploy](Wiki/CICD%20Jobs/Juice%20Shop-Pipeline/8.%20deploy)
**clean-storage:** [clean-storage](Wiki/CICD%20Jobs/Juice%20Shop-Pipeline/9.%20clean-storage)
