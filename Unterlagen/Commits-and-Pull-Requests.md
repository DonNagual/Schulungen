# GitHub Schulung: Commits und Pull Requests

## 1. Einführung und Zielsetzung (5 Minuten)
- Vorstellung des Ablaufs und der Ziele der Schulung
- Ziel: Verbesserung der Commit-Qualität und effektiver Umgang mit Konflikten in Pull Requests

## 2. Best Practices für Commits (15 Minuten)
Commit-Nachrichten sind essenziell für die Verständlichkeit und Nachvollziehbarkeit der Änderungen im Code. Gute Commit-Nachrichten erleichtern die Zusammenarbeit im Team, die Code-Überprüfung und die Fehlersuche.

### Qualität der Commit-Nachrichten:
#### 2.1 Aussagekräftige und präzise Nachrichten

Die Commit-Nachricht sollte klar und präzise beschreiben, was und warum etwas geändert wurde. Vermeide allgemeine Nachrichten wie "Fixes" oder "Updates". Eine gute Nachricht hilft anderen Entwicklern zu verstehen, welche Änderungen vorgenommen wurden, ohne den gesamten Code durchsehen zu müssen.

### 2.2 Struktur der Commit-Nachricht

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
### 2.3 Thematisch abgeschlossene Commits

- Kleine und isolierte Commits:
  - Jeder Commit sollte eine abgeschlossene Einheit darstellen, die eine spezifische Änderung beinhaltet.
  - Vermeide es, verschiedene Änderungen in einem Commit zu kombinieren.

- Häufig committen:
  - Regelmäßiges Committen hilft dabei, Änderungen nachzuvollziehen und reduziert das Risiko von Konflikten.
  - Es ermöglicht zudem eine einfachere Code-Überprüfung und erleichtert das Zurückrollen von Änderungen bei Bedarf.

### 2.4 Verwendung von Issue-Referenzen

Verlinke Commits mit den entsprechenden Issues, indem du die Issue-Nummer in der Commit-Nachricht erwähnst. Dies hilft, den Zusammenhang zwischen Änderungen und Anforderungen oder Fehlern nachzuvollziehen.

```Bash
git commit -m "Add user authentication feature

Implements user login, registration, and logout functionality. 
Closes #123"
```

### 2.5 Verbesserung der Lesbarkeit

Verwende Aufzählungszeichen, wenn mehrere Punkte erläutert werden.
Achte auf eine saubere Formatierung und Rechtschreibung.

### 2.6 Commit-Nachrichten für automatisierte Prozesse

Nutze spezifische Schlüsselwörter für automatisierte Prozesse (z.B. Continuous Integration), die automatisch auf bestimmte Commit-Nachrichten reagieren können.


[Beispiel Commits](../Materialien/Commits.md)

## 3. Erstellen und Verwalten von Pull Requests (15 Minuten)
### Richtlinien für Pull Requests:
- Beschreibung des Problems, der Lösung und wie die Änderungen getestet wurden
- Verknüpfung von Issues (z.B. Closes #123)
- Überprüfung und Diskussion im Team

### Beispiel für eine Pull Request Beschreibung:

```Bash
# Title: Fix Layout Issue
## Description
This PR fixes the layout issue on the homepage by adjusting the CSS flex properties.
It also includes minor changes to improve responsiveness.

## Changes
- Adjusted CSS flex properties in styles.css
- Updated HTML structure in index.html

## Testing
- Open the homepage and check the alignment of elements
- Resize the browser window to test responsiveness
```

### Best Practices:
- Kleine und überschaubare PRs erstellen
- Regelmäßige Reviews und Feedback anfordern

## 4. Umgang mit Konflikten in Pull Requests (20 Minuten)
### Erkennen und Vermeiden von Konflikten:
- Regelmäßiges Pullen der neuesten Änderungen von main in den eigenen Branch
- Kleine, häufige PRs, um Konflikte zu minimieren

### Lösung von Konflikten:
- Schritt-für-Schritt-Anleitung zum Auflösen von Konflikten

[Beispiel Konflikt](../Materialien/Pull-Request-Conflicts.md)

```Bash
Beispiel:
git checkout main
git pull origin main
git checkout feature/neues-feature
git merge main
# Konflikte auflösen in betroffenen Dateien
git add <konflikt-dateien>
git commit -m "Resolve merge conflicts in <dateien>"
git push
```

### Praktische Übung:
- Simulierte Konflikte erzeugen und gemeinsam lösen

## 5. Fragerunde und Problembehandlung (5 Minuten)
- Offene Fragen der Teilnehmer klären
- Beispiele aus der Praxis besprechen

## 6. Abschluss (5 Minuten)
- Zusammenfassung der wichtigsten Punkte
- Ressourcen und weiterführende Informationen
  - Offizielle Git und GitHub Dokumentation
  - Interne Wiki-Seiten oder Tutorials

---

## Zusätzliche Ressourcen:
- Pro Git Book (englisch): https://git-scm.com/book/en/v2
- Atlassian Git Tutorials: https://www.atlassian.com/git/tutorials

