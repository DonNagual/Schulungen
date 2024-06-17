# GitHub Schulung: Commits und Pull Requests

## 1. Einführung und Zielsetzung (5 Minuten)
- Vorstellung des Ablaufs und der Ziele der Schulung
- Ziel: Verbesserung der Commit-Qualität und effektiver Umgang mit Konflikten in Pull Requests

## 2. Best Practices für Commits (15 Minuten)
Commit-Nachrichten sind essenziell für die Verständlichkeit und Nachvollziehbarkeit der Änderungen im Code. Gute Commit-Nachrichten erleichtern die Zusammenarbeit im Team, die Code-Überprüfung und die Fehlersuche.

### Qualität der Commit-Nachrichten:
#### 2.1 Aussagekräftige und präzise Nachrichten

Die Commit-Nachricht sollte klar und präzise beschreiben, was und warum etwas geändert wurde. Vermeide allgemeine Nachrichten wie "Fixes" oder "Updates". Eine gute Nachricht hilft anderen Entwicklern zu verstehen, welche Änderungen vorgenommen wurden, ohne den gesamten Code durchsehen zu müssen.

#### 2.2 Struktur der Commit-Nachricht

Eine gute Commit-Nachricht sollte aus einer kurzen Zusammenfassung und einer detaillierten Beschreibung bestehen.

- Kurze Zusammenfassung:
  - Maximal 50 Zeichen
  - Verwendet den Imperativmodus (z.B. "Add", "Fix", "Remove")
  - Sollte auf den Punkt bringen, was der Commit bewirkt

- Detaillierte Beschreibung (optional):
  - Leerzeile nach der Zusammenfassung
  - Bis zu 72 Zeichen pro Zeile
  - Erläutert, warum die Änderungen vorgenommen wurden und zusätzliche Kontextinformationen

```Bash
Beispiel:
git add <datei>
git commit -m "Fix layout issue on homepage

This commit resolves the misalignment of elements on the homepage by adjusting the CSS flex properties.
It also includes minor changes to improve responsiveness."
```
#### 2.3 Thematisch abgeschlossene Commits

- Kleine und isolierte Commits:
  - Jeder Commit sollte eine abgeschlossene Einheit darstellen, die eine spezifische Änderung beinhaltet.
  - Vermeide es, verschiedene Änderungen in einem Commit zu kombinieren.

- Häufig committen:
  - Regelmäßiges Committen hilft dabei, Änderungen nachzuvollziehen und reduziert das Risiko von Konflikten.
  - Es ermöglicht zudem eine einfachere Code-Überprüfung und erleichtert das Zurückrollen von Änderungen bei Bedarf.

#### 2.4 Verwendung von Issue-Referenzen

Verlinke Commits mit den entsprechenden Issues, indem du die Issue-Nummer in der Commit-Nachricht erwähnst. Dies hilft, den Zusammenhang zwischen Änderungen und Anforderungen oder Fehlern nachzuvollziehen.

```Bash
git commit -m "Add user authentication feature

Implements user login, registration, and logout functionality. 
Closes #123"
```

#### 2.5 Verbesserung der Lesbarkeit

- Verwende Aufzählungszeichen, wenn mehrere Punkte erläutert werden.
- Achte auf eine saubere Formatierung und Rechtschreibung.

#### 2.6 Commit-Nachrichten für automatisierte Prozesse

- Nutze spezifische Schlüsselwörter für automatisierte Prozesse (z.B. Continuous Integration), die automatisch auf bestimmte Commit-Nachrichten reagieren können.


[Beispiel Commits](../Materialien/Commits.md)

## 3. Erstellen und Verwalten von Pull Requests (15 Minuten)

Pull Requests sind ein zentrales Element der Zusammenarbeit auf GitHub. Sie ermöglichen es, Änderungen vorzuschlagen, diese von anderen prüfen zu lassen und schließlich in das Haupt-Repository zu integrieren.

### 3.1 Richtlinien für Pull Requests

#### 3.1.1 Beschreibung des Problems und der Lösung:
- Jede PR sollte eine klare und detaillierte Beschreibung des Problems und der vorgeschlagenen Lösung enthalten.
- Erkläre, warum die Änderungen notwendig sind und wie sie das Problem lösen.

#### 3.1.2 Verknüpfung von Issues:
- Verlinke relevante Issues, indem du Keywords wie Closes #123 oder Fixes #456 verwendest.
- Dies sorgt für eine bessere Nachverfolgbarkeit und automatische Schließung der Issues bei der PR-Freigabe.

#### 3.1.3 Dokumentation der Änderungen:
- Liste alle Änderungen auf, die im Rahmen der PR vorgenommen wurden.
- Verwende eine klare und verständliche Sprache.

#### 3.1.4 Testanweisungen:
- Füge klare Anweisungen hinzu, wie die Änderungen getestet werden können.
- Dies hilft den Reviewern, die Änderungen nachzuvollziehen und zu überprüfen.


### Beispiel für eine Pull Request Beschreibung:

```Bash
# Title: Fix Layout Issue

## Description
This PR fixes the layout issue on the homepage by adjusting the CSS flex properties.
It also includes minor changes to improve responsiveness.

## Changes
- Adjusted CSS flex properties in `styles.css`
- Updated HTML structure in `index.html`

## Testing
- Open the homepage and check the alignment of elements
- Resize the browser window to test responsiveness
```
### 3.2 Best Practices für Pull Requests

#### 3.2.1 Kleine und überschaubare PRs:
- Große PRs sind schwer zu überprüfen und führen eher zu Fehlern. Teile große Änderungen in kleinere, thematisch abgeschlossene PRs auf.

#### 3.2.2 Regelmäßige und frühzeitige Reviews:
- Fordere frühzeitig Feedback an, um sicherzustellen, dass die Änderungen in die richtige Richtung gehen.
- Regelmäßige Reviews verhindern, dass sich viele Änderungen anhäufen, die dann schwer zu überprüfen sind.

#### 3.2.3 Klare Commit-Historie:
- Achte darauf, dass die Commit-Historie übersichtlich und nachvollziehbar bleibt. Nutze git rebase oder git squash um unnötige Commits zu reduzieren.
- Jeder Commit sollte eine abgeschlossene Einheit darstellen.

#### 3.2.4 Automatisierte Tests:
- Stelle sicher, dass alle relevanten automatisierten Tests erfolgreich durchlaufen, bevor du eine PR erstellst.
- Dies reduziert die Wahrscheinlichkeit von Fehlern und spart Zeit bei der Überprüfung.

#### 3.2.5 Konflikte frühzeitig lösen:
- Ziehe regelmäßig die neuesten Änderungen des Haupt-Branches (main oder master) in deinen Feature-Branch, um Konflikte frühzeitig zu erkennen und zu lösen.

### 3.3 Umgang mit Konflikten in PRs

#### 3.3.1 Erkennen von Konflikten:
- GitHub meldet automatisch Konflikte bei einem Merge-Versuch. Überprüfe regelmäßig den Status deiner PRs.

#### 3.3.2 Lösung von Konflikten:
- Ziehe die neuesten Änderungen vom Haupt-Branch und löse die Konflikte lokal:

```Bash
git checkout main
git pull origin main
git checkout feature/branch
git merge main
# Konflikte in den betroffenen Dateien lösen
git add <konflikt-dateien>
git commit -m "Resolve merge conflicts"
git push
```

#### 3.3.3 Kommunikation im Team:
- Kommuniziere Konflikte frühzeitig im Team und suche gemeinsam nach Lösungen, wenn nötig.

### Beispiel für den Umgang mit Konflikten:
```Bash
git checkout main
git pull origin main
git checkout feature/neues-feature
git merge main
# Konflikte auflösen in betroffenen Dateien
git add <konflikt-dateien>
git commit -m "Resolve merge conflicts in <dateien>"
git push
```

[Beispiel Konflikt](../Materialien/Pull-Request-Conflicts.md)

### Praktische Übung:
- Simulierte Konflikte erzeugen und gemeinsam lösen

## 4. Fragerunde und Problembehandlung (5 Minuten)
- Offene Fragen der Teilnehmer klären
- Beispiele aus der Praxis besprechen

## 5. Abschluss (5 Minuten)
### Zusammenfassung der wichtigsten Punkte

#### Eine gute Commit-Nachricht sollte:
- Kurz und prägnant sein
- Den Imperativmodus verwenden
- Eine klare Zusammenfassung und, falls nötig, eine detaillierte Beschreibung enthalten
- Thematisch abgeschlossen sein und kleine Änderungen umfassen
- Issue-Referenzen enthalten
- Lesbar und gut formatiert sein

#### Eine gute Pull Request sollte:
- Eine klare Beschreibung des Problems und der Lösung enthalten
- Relevante Issues verlinken
- Dokumentation der Änderungen und Testanweisungen umfassen
- Klein und thematisch abgeschlossen sein
- Frühzeitig Feedback einholen
- Eine übersichtliche Commit-Historie haben
- Automatisierte Tests bestehen
- Konflikte frühzeitig erkennen und lösen

### Ressourcen und weiterführende Informationen
  - Offizielle Git und GitHub Dokumentation
  - Interne Wiki-Seiten oder Tutorials

---

## Zusätzliche Ressourcen:
- Pro Git Book (englisch): https://git-scm.com/book/en/v2
- Atlassian Git Tutorials: https://www.atlassian.com/git/tutorials

