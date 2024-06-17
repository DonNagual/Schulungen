# GitHub Schulung: Commits und Pull Requests

## 1. Einführung und Zielsetzung (5 Minuten)
- Vorstellung des Ablaufs und der Ziele der Schulung
- Ziel: Verbesserung der Commit-Qualität und effektiver Umgang mit Konflikten in Pull Requests

## 2. Best Practices für Commits (15 Minuten)
### Qualität der Commit-Nachrichten:
- Aussagekräftige und präzise Nachrichten
- Strukturierung nach dem Muster: kurze Zusammenfassung (50 Zeichen), Leerzeile, detaillierte Beschreibung (falls nötig, 72 Zeichen pro Zeile)
- Vermeidung von Nachrichten wie "Fixes" oder "Update"

```Bash
Beispiel:
git add <datei>
git commit -m "Fix layout issue on homepage

This commit resolves the misalignment of elements on the homepage by adjusting the CSS flex properties."
```

### Regelmäßige und thematisch abgeschlossene Commits:
- Commits sollten kleine, abgeschlossene Einheiten darstellen
- Häufig committen, um die Änderungen nachvollziehbar zu halten

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

