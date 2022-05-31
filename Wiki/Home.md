# CICD Projekt 1 & 2
Unser Projekt wird mit der Hilfe der [CICD-Pipeline](CICD.md) und [Maven](Maven.md) compiled und getestet. 
Die CICD-Pipeline wird auf [GitLab](Tools/GitLab) über einen sogenannten [GitLab Runner](Wiki/GitLab/Runner) ausgeführt, dieser führt die von uns angegebenen Befehle innerhalb unserer [.yml](gitlab-ci.yml.md) Datei über einen [Docker](Docker.md) aus der auf einer [Virtuellen Maschiene](Virtual Machine) läuft.

**CICD Projekt 1 - Todo-List**
_Stages: Build, Testing, Deploy, Cleanup_

**Build:**       [Build Project using Maven](maven/Build)
**Testing:**   [Maven - Unit Test](Wiki/Maven/Unit-Test)
**Testing:**   [Maven - Integration Test](Wiki/Maven/Integration-Test)
**Testing:**   _Semgrep todo_
**Testing:**   _gitleaks todo_
**Deploy:**    _package todo_
**Deploy:**    _deploy package todo_
**Cleanup:**  _cleanup todo_


**CICD Projekt 2 - 🍆 Juice Shop**
_Stages: Todo_