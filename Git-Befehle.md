# Git Cheat Sheet

## Inhaltsverzeichnis

1. [Repository erstellen und kopieren](#1-repository-erstellen-und-kopieren)
2. [Änderungen verwalten](#2-%C3%A4nderungen-verwalten)
3. [Commits](#3-commits)
4. [Branches](#4-branches)
5. [Navigation](#5-navigation)
6. [Merge und Rebase](#6-merge-und-rebase)
7. [Commit-Historie](#7-commit-historie)
8. [Commits bearbeiten](#8-commits-bearbeiten)
9. [Tags](#9-tags)
10. [Remote Repositories](#10-remote-repositories)
11. [Synchronisation mit Remote Repositories](#11-synchronisation-mit-remote-repositories)
12. [Änderungen rückgängig machen](#12-%C3%A4nderungen-r%C3%BCckg%C3%A4ngig-machen)
13. [Relative Referenzen](#13-relative-referenzen)
14. [Typischer Git-Workflow](#14-typischer-git-workflow)

---

# 1. Repository erstellen und kopieren

| Befehl | Beschreibung |
|---------|-------------|
| `git init <directory>` | Erstellt ein neues Repository. |
| `git clone <repository-url>` | Kopiert ein bestehendes Repository. |

---

# 2. Änderungen verwalten

| Befehl | Beschreibung |
|---------|-------------|
| `git status` | Zeigt den aktuellen Zustand des Repositories an (geänderte Dateien, gestagte Dateien, aktuelle Branch). |
| `git add <datei>` | Fügt Änderungen zur Staging Area hinzu. |
| `git add .` | Fügt alle Änderungen im aktuellen Verzeichnis zur Staging Area hinzu. |
| `git rm <datei>` | Löscht eine Datei und markiert die Löschung für den nächsten Commit. |

---

# 3. Commits

| Befehl | Beschreibung |
|---------|-------------|
| `git commit` | Erstellt einen neuen Commit (Snapshot) der aktuell gestagten Änderungen. |
| `git commit -m "Nachricht"` | Erstellt einen Commit mit einer Commit-Nachricht. |
| `git commit --amend` | Ersetzt den letzten Commit durch einen neuen Commit mit zusätzlichen Änderungen oder einer neuen Nachricht. |

---

# 4. Branches

| Befehl | Beschreibung |
|---------|-------------|
| `git branch <name>` | Erstellt eine neue Branch. |
| `git branch` | Zeigt alle lokalen Branches an. |
| `git branch -u <branch-connection> [<branch>]` | Verbindet eine lokale Branch mit einer Remote-Branch. |
| `git branch -f <branch> <ziel-ort>` | Verschiebt eine Branch auf einen anderen Commit. |

---

# 5. Navigation

| Befehl | Beschreibung |
|---------|-------------|
| `git checkout <ort>` | Wechselt zu einer Branch oder einem Commit. |
| `git checkout -b <new-branch> [<start-point>]` | Erstellt eine neue Branch und wechselt direkt auf diese. |
| `git checkout -b <new-branch> <branch-connection>` | Erstellt eine lokale Branch basierend auf einer Remote-Branch und wechselt auf diese. |

---

# 6. Merge und Rebase

## Merge

| Befehl | Beschreibung |
|---------|-------------|
| `git merge <branch>` | Führt die angegebene Branch in die aktuelle HEAD-Branch zusammen. |

### Beispiel

```bash
git checkout main
git merge feature
```

Danach enthält `main` die Änderungen von `feature`.
`feature` bleibt unverändert.

---

## Rebase

| Befehl | Beschreibung |
|---------|-------------|
| `git rebase <ziel-branch> [<branch>]` | Verschiebt die aktuellen Commits auf die Ziel-Branch und erzeugt eine lineare Historie. |
| `git rebase -i <commit>` | Ermöglicht das Bearbeiten, Zusammenführen oder Umordnen von Commits. |

### Beispiel

```bash
git checkout feature
git rebase main
```

Die Commits von `feature` werden auf den neuesten Stand von `main` gesetzt.

---

# 7. Commit-Historie

| Befehl | Beschreibung |
|---------|-------------|
| `git log` | Zeigt die Commit-Historie inklusive Hash-Werten an. |
| `git describe <ref-name>` | Beschreibt den Abstand eines Commits zum nächsten Tag. |

---

# 8. Commits bearbeiten

| Befehl | Beschreibung |
|---------|-------------|
| `git cherry-pick <commit> [<commit> ...]` | Fügt ausgewählte Commits an den aktuellen HEAD an. |

---

# 9. Tags

| Befehl | Beschreibung |
|---------|-------------|
| `git tag <name> <commit>` | Erstellt einen festen Tag für einen Commit. |

---

# 10. Remote Repositories

| Befehl | Beschreibung |
|---------|-------------|
| `git remote -v` | Zeigt die verbundenen Remote-Repositories an. |

---

# 11. Synchronisation mit Remote Repositories

## Fetch

| Befehl | Beschreibung |
|---------|-------------|
| `git fetch` | Lädt Daten vom Remote Repository herunter und aktualisiert die Remote-Branches. |
| `git fetch <remote> <ort>` | Holt eine bestimmte Branch vom angegebenen Repository. |
| `git fetch <remote> <quelle>:<ziel>` | Quelle und Ziel können explizit angegeben werden. |

---

## Pull

| Befehl | Beschreibung |
|---------|-------------|
| `git pull` | Führt `git fetch` und anschließend `git merge` aus. |
| `git pull --rebase` | Führt `git fetch` und anschließend `git rebase` aus. |

---

## Push

| Befehl | Beschreibung |
|---------|-------------|
| `git push` | Überträgt lokale Änderungen auf das Remote Repository. |
| `git push <remote> <ort>` | Pusht eine bestimmte Branch auf ein bestimmtes Repository. |
| `git push <remote> <quelle>:<ziel>` | Quelle und Ziel können explizit angegeben werden. |

---

# 12. Änderungen rückgängig machen

| Befehl | Beschreibung |
|---------|-------------|
| `git reset <ort>` | Setzt die aktuelle Branch auf einen früheren Commit zurück. |
| `git revert <commit>` | Erstellt einen neuen Commit, der die Änderungen eines früheren Commits rückgängig macht. |

---

# 13. Relative Referenzen

Relative Referenzen ermöglichen die Navigation durch die Commit-Historie.

| Referenz | Bedeutung |
|-----------|-----------|
| `main^` | Ein Commit zurück |
| `main^^` | Zwei Commits zurück |
| `main~2` | Zwei Commits zurück |
| `main~3` | Drei Commits zurück |
| `HEAD^` | Vorgänger des aktuellen Commits |
| `HEAD~2` | Zwei Commits vor HEAD |

### Beispiele

```bash
git checkout main^
```

Wechselt zum Vorgänger von `main`.

```bash
git checkout HEAD~3
```

Wechselt drei Commits zurück.

---

# 14. Typischer Git-Workflow

## Neues Projekt erstellen

```bash
git init
git add .
git commit -m "Initial Commit"
```

---

## Bestehendes Projekt klonen

```bash
git clone <repository-url>
```

---

## Neue Funktion entwickeln

### 1. Neue Branch erstellen

```bash
git checkout -b feature-login
```

### 2. Änderungen vornehmen

Dateien bearbeiten.

### 3. Änderungen prüfen

```bash
git status
```

### 4. Änderungen zur Staging Area hinzufügen

```bash
git add .
```

### 5. Commit erstellen

```bash
git commit -m "Login-Funktion implementiert"
```

### 6. Änderungen hochladen

```bash
git push origin feature-login
```

---

## Änderungen vom Server holen

```bash
git pull
```

oder

```bash
git pull --rebase
```

---

## Feature in Main übernehmen

```bash
git checkout main
git merge feature-login
```

---

## Typische Befehlsfolge im Alltag

```bash
git status
git add .
git commit -m "Änderungen"
git pull --rebase
git push
```

Diese Befehlsfolge wird in der Praxis am häufigsten verwendet.

---

# Merksätze für die Prüfung

- `git add` → Änderungen vormerken
- `git commit` → Snapshot erstellen
- `git push` → Änderungen hochladen
- `git pull` → Änderungen herunterladen
- `git branch` → Branch erstellen
- `git checkout` → Branch wechseln
- `git merge` → Branches zusammenführen
- `git rebase` → Historie linear machen
- `git reset` → Branch zurücksetzen
- `git revert` → Änderungen rückgängig machen
- `git fetch` → Nur herunterladen, nichts zusammenführen
- `git clone` → Repository kopieren
