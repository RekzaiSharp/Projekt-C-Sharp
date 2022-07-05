# gitleaks

https://github.com/zricethezav/gitleaks

Ein SAST-Tool, dass die Öffentlichmachung von geheimen Informationen (Secrets) wie Passwörtern, API-Schlüsseln, Tokens etc. aufdeckt bzw. verhindert.

## Installation über DockerHub
```
docker pull zricethezav/gitleaks:latest
docker run -v ${path_to_host_folder_to_scan}:/path zricethezav/gitleaks:latest [COMMAND] --source="/path" [OPTIONS]
```
<b>ACHTUNG: Nicht Copy-Pasten! Siehe Kommados unten!</b>

## Kommandos
````
Usage:
  gitleaks [command]

Available Commands:
  completion  generate the autocompletion script for the specified shell
  detect      Detect secrets in code
  help        Help about any command
  protect     Protect secrets in code
  version     Display gitleaks version

Flags:
  -c, --config string          config file path
                               order of precedence:
                               1. --config/-c
                               2. env var GITLEAKS_CONFIG
                               3. (--source/-s)/.gitleaks.toml
                               If none of the three options are used, then gitleaks will use the default config
      --exit-code string       exit code when leaks have been encountered (default: 1)
  -h, --help                   help for gitleaks
  -l, --log-level string       log level (debug, info, warn, error, fatal) (default "info")
      --redact                 redact secrets from logs and stdout
  -f, --report-format string   output format (json, csv, sarif)
  -r, --report-path string     report file
  -s, --source string          path to source (git repo, directory, file)
  -v, --verbose                show verbose output from scan

Use "gitleaks [command] --help" for more information about a command.
````

## Detect und Protect

Die beiden Kommandos, mit denen Secrets gefunden werden können, sind "detect" und "protect".

### detect
Scannt ein Repository über dessen Output, der mittels ``git log -p`` ausgegeben wird.
Um einen Nicht-Git-Ordner zu scannen, benötigt man die Option ``--no-git``.

### protect
Wird auf Änderungen angewendet, die noch nicht committed wurden. Untersucht den Output des Befehls  ``git diff`` und kann nicht für Nicht-Git-Ordner verwendet werden.
(Für uns vermutlich uninteressant).

## Report: Generic API Keys

- Gitleaks zeigt viele der "generic-api-keys" an. Diese werden aber <u>nicht</u> an den "Kunden" ausgeliefert, und sind daher (zumindest für uns) uninteressant.

- Höchstens in einer Supply Chain Attack (siehe "3. Securing the Code") könnte ein offen auslesbarer API Key ein Sicherheitsproblem darstellen: hardgecodete Nutzernamen und Passwörter sind zwar komfortabel für Entwickler, ermöglichen aber einem Angreifer Vollzugriff, z.B. auf eine Datenbank.

- Man kann diese Warnungen zwar unterdrücken, aber selbst Fr. Prof. Oetzel hat das noch nicht geschafft...