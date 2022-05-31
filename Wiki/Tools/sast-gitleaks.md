# sast-gitleaks

(static application securit test - gitleaks)

Sorgt dafür, dass keine geheimen Informationen wie Passwörter, SSH-Keys, Nutzernamen etc. über Git an die Öffentlichkeit geraten.

https://github.com/zricethezav/gitleaks

Siehe auch [[gitleaks]].

## Ist das das richtige sast-gitleaks?
Das klingt zwar jetzt erst einmal doof, aber tatsächlich habe ich zwei Tools mit dem Namen gefunden: erst einmal das namensgebende sast-git-leaks:

https://github.com/leboncoin/sast-git-leaks

Allerdings hat dieses zwei Abhängigkeiten: gitleaks und shhgit:

https://github.com/zricethezav/gitleaks

https://github.com/eth0izzle/shhgit

Meine Vermutung ist, dass das gitleaks von "zrichethezav" (oben) das korrekte gitleaks ist. Wozu benötigt man sast-git-leaks, wenn dessen Zweck es ist, zwei ähnliche Tools miteinander zu vereinen? Soweit ich das sehe, handelt es sich "nur" um ein Python-Skript, dass einfach beide Tools (gitleaks und shhgit) ausführt.
Außerdem enthält "gitleaks" eine viel ausführlichere Anleitung zur Installation und Ausführung, z.B. in einem Docker-Container. 