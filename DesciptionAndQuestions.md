# Praktisches Arbeiten mit GIT

## Szenario 1: Ein neues Projekt erstellen

### Begriffsdefinitionen
| Begriff | Beschreibung |
| --- |---|
| git init | Erstellt ein neues lokales Git-Repository im aktuellen Verzeichnis. Ab diesem Zietpunkt können Änderungen an Dateien mit Git versioniert werden. |
| git status | Zeigt den aktuellen Zustand des Repositories an.  Man sieht, welche Dateien geändert, neu hinzugefügt oder für den nächsten Commit vorgemerkt wurden. |
| git add | Fügt Dateien zur Staging Area hinzu. Damit werden Änderungen für den nächsten Commit vorgemerkt.  ```git add index.html``` oder ```git add .```|
| git commit | Speichert die vorgemerkten Änderungen als neuen Commit in der lokalen Versionshistorie. Jeder Commit stellt einen nachvollziehbaren Entwicklungsstand dar. ```git commit -m "Login-Funktion hinzugefügt``` |
| git log | Zeigt die bisherigen Commits mit Informationen wie Commit-ID, Autor, Datum und Commit-Nachricht an. |

### Fragen
#### Was ist der Unterschied zwischen Working Directory, Staging Area und Repository?
| Begriff | Beschreibung |
| --- |---|
| Working Directory (Arbeitsverzeichnis) | Hier befinden sich die Dateien, die aktuell bearbeitet werden. Dateien können erstellt, bearbeitet oder gelöscht werden. |
| Staging Area | Hier werden Änderungen mit ```git add``` für den nächsten commit vorgemerkt |
| Repository |Hier speichert Git die Versionshistorie des Projektes. Mit ```git commit``` werden die vorgemerkten Änderungen dauert in der lokalen Git-Historie festghalten. |

#### Warum müssen Dateien vor einem Commit mit git add vorgemerkt werden?
Mit ```git add``` wird festgelegt, welche Änderungen im nächsten commit enthalten sind.   
Dadurch kann man gezielt auswählen, welche Änderungen zusammengehören. Nicht jede Änderung im Arbeitsverzeichnis muss sofort gespeichert werden.

```git commit``` übernimmt die vorgemerkten Änderungen aus der Staging Area.


#### Welche Informationen werden in einem Commit gespeichert?
Ein Git-Commit enhtält folgende Informationen
- Commit-ID (Hash): Eindeutige Kennung des Commits.
- Autor: Person, die die Änderungen erstellt hat.
- Datum und Uhrzeit: Zeitangaben zur Erstellung des Commits.
- Commit-Nachricht: Beschreibung der vorgenommenen Änderungen.
- Projektzustand (Snapshot): Gespeicherter Stand der versionierten Dateien.
- Verweis auf vorherige Commits: Dadurch entsteht die Versionshistorie.

Wie kann ich mir den letzten commit anzeigen?
- ```git show```: Letzten Commit Anzeigen
- ```git log```: Alle bisherigen Commits anzeigen

## Szenario 2: Änderungen nachvollziehen
### Begriffsdefinitionen
| Begriff | Beschreibung |
| --- |---|
| git status | Zeigt den aktuellen Zustand des Repositories. Man sieht, welche Dateien verändert, neu oder für einen Commit vorgemerkt sind. |
| git diff | Zeigt die Änderungen im Working Directory, die noch nicht mit git add vorgemerkt wurden. |
| git diff --staged	| Zeigt die Änderungen, die bereits mit git add in der Staging Area vorgemerkt wurden und im nächsten Commit enthalten sein werden. |
| git add |	Übernimmt ausgewählte Änderungen in die Staging Area und bereitet sie damit für den nächsten Commit vor. |
| git commit | Speichert die vorgemerkten Änderungen als neuen Commit im lokalen Repository. |
| git log | Zeigt die bisherige Commit-Historie mit Informationen wie Commit-ID, Autor, Datum und Commit-Nachricht. |


### Fragen
#### Was zeigt git diff an?
```git diff``` zeigt die Unterschiede zwischen dem aktuellen Working Directory und der Staging Area. Damit erkennt man, welche Änderungen an bereits versionierten Dateien noch nicht für den nächsten Commit vorgemerkt wurden.   
Standardmäßig werden beispielsweise hinzugefügte, entfernte und geänderte Codezeilen angezeigt.

#### Worin unterscheiden sich git diff und git diff --staged?
```git diff```
- zeigt noch nicht vorgemerkte Änderungen
- Vergleicht Working Directory mit Staging Area

```git diff --staged```
- Zeigt bereits vorgemerkte Änderungen.
- Vergleicht Staging Area mit dem letzten Commit.

#### Warum sind aussagekräftige Commit-Nachrichten wichtig?
Aussagekräftige Commit-Nachrichten sind wichtig, damit Änderungen in der Versionshistorie verständlich und nachvollziehbar bleiben.
- Nachvollziehen, was in einem Commit geändert wurde
- Anforderungen zu finden (z.B. Ref zum Ticket)
- Erleichterung bei der Zusammenarbeit und bei Merge Request
- Erleichtert das finden von früheren Änderungen

## Szenario 3: Einen Fehler rückgängig machen
### Begriffsdefinitionen
| Begriff | Beschreibung |
| --- |---|
| git diff | Zeigt die Änderungen an bereits versionierten Dateien, die noch nicht in der Staging Area vorgemerkt wurden. |
| git restore | Stellt eine Datei im Working Directory auf den Stand der Staging Area zurück. Nicht vorgemerkte Änderungen an dieser Datei werden verworfen. |
| git restore --staged | Entfernt eine Datei aus der Staging Area, ohne die Änderungen im Working Directory zu löschen.|
| git status | Zeigt den aktuellen Zustand des Repositories, insbesondere welche Dateien geändert, vorgemerkt oder noch nicht versioniert sind. |

### Fragen
#### Was ist der Unterschied zwischen git restore und git restore --staged?
```git restore```
- stellt den Inhalt einer Datei wieder her
- Working Directory
- nicht vorgemerkte Änderungen gehen verlogen

```git restore --staged```
- macht das vormerken mit ```git add``` rückgängig
- betrifft die staging area
- Änderungen im Working Directory bleiben erhalten

#### Welche Änderungen gehen beim Wiederherstellen einer Datei verloren?
- Bei ```git restore <datei>``` gehen die noch nicht in der Staging Area vorgemerkten Änderungen verloren.
- Hinzugefügte, veränderte oder gelöschte Zeilen auf den Stand der Staging Area zurückgesetzt
- Bereits mit ```git add``` vorgemerkte Änderungen bleiben erhalten

## Szenario 4: Ein neues Feature entwickeln (Branching)
### Begriffsdefinitionen
| Begriff | Beschreibung |
| --- |---|
| git branch | Zeigt alle lokalen Branches an. Mit zusätzlichen Argumenten können Branches erstellt oder gelöscht werden. |
| git switch |Wechselt zwischen bestehenden Branches. Mit -c kann ein neuer Branch erstellt und direkt zu diesem gewechselt werden. |
| git log --oneline --graph --all | Zeigt die Commit-Historie aller Branches in einer kompakten, grafischen Darstellung. |

### Fragen
#### Warum verwendet man Branches?
Branches werden verwendet, um verschiedene Entwicklungsstände unabhängig voneinander weiterzuentwickeln.

Dadurch können neue Funktionen entwickelt und Fehler behoben ohne den main direkt zu veränden.

#### Was passiert mit den Dateien beim Wechsel zwischen Branches?
Die Working Directory wird an den Stand des Zielbranches angepasst.

#### Welche Vorteile bietet die Entwicklung neuer Funktionen in eigenen Branches?
- Trennung der Entwicklung: Neue Funktionen können unabhängig vom Hauptbranch entwickelt werden.
- Stabilität: Es gibt den Hauptbranch, der immer Kompeliert
- Teamarbeit: Mehrere Entwickler können gleichzeitig an unterschiedlichen Funktionen arbeiten.
- Einfacheres Testen: Neue Funktionen können überprüft werden, bevor sie in den Hauptbranch übernommen werden.
- Nachvollziehbarkeit: Änderungen einer Funktion lassen sich leichter zuordnen.

## Szenario 5: Das neue Feature integrieren (Merge)
### Begriffsdefinitionen
| Begriff | Beschreibung |
| --- |---|
| git merge | Führt die Änderungen eines anderen Branches in den aktuell ausgecheckten Branch zusammen.
| git branch -d | Löscht einen lokalen Branch, sofern Git dessen Löschung als sicher einstuft. |
| git log --graph --oneline --all | Zeigt die Commit-Historie aller Branches in einer kompakten, grafischen Darstellung. |

### Fragen
#### Was passiert bei einem Merge?
Bei einem Merge werden die Entwicklungsstände von zwei Branches zusammengeführt.   
Dabei werden die Änderungen eines Branches in den aktuell verwendeten Branch übernommen.

#### Was versteht man unter einem Fast-Forward-Merge?
Ein Fast-Forward-Merge ist eine einfache Form des Merges, bei der Git keinen zusätzlichen Merge-Commit erstellen muss.
Das funktioniert, wenn seit der Verzweigung keine neuen Commits im Zielbranch entstanden sind.
Git verschiebt dabei lediglich den Branch-Zeiger auf den neuesten Commit des anderen Branches.

#### Warum kann ein Branch nach einem erfolgreichen Merge gelöscht werden?
Ein Branch kann nach einem erfolgreichen Merge gelöscht werden, weil seine Änderungen bereits in den Zielbranch übernommen wurden.
Dadurch erhält man: 
- Übersichtlichkeit: Nicht mehr benötigte Branches werden entfernt
- Bessere Organisation: Es ist leichter zu erkennen, welche Funktionen noch entwickelt werden

## Szenario 6: Einen Merge-Konflikt lösen
```git merge, git status, git diff, git add, git commi```

### Fragen
#### Wann entsteht ein Merge-Konflikt?
Ein Merge-Konflikt entsteht, wenn zwei Branches widersprüchliche Änderungen enthalten und Git diese nicht automatisch zusammenführen kann.   
Das passiert beispielsweise, wenn zwei Entwickler dieselbe Zeile einer Datei unterschiedlich verändern.   
Wenn beide Änderungen auf demselben ursprünglichen Stand basieren, kann Git beim Zusammenführen einen Konflikt melden, weil nicht eindeutig ist, welche Änderung übernommen werden soll.   
Merge-Konflikte können auch entstehen, wenn eine Datei in einem Branch gelöscht und im anderen bearbeitet wurde.

#### Wie kennzeichnet Git widersprüchliche Änderungen?
`<<<<<<<` HEAD	Beginn der Version des aktuellen Branches
`=======` Trennt die beiden widersprüchlichen Versionen
`>>>>>>>` neue-funktion	Ende der Version aus dem zusammenzuführenden Branch

#### Wie kann ein Merge-Konflikt aufgelöst werden?
Ein Merge-Konflikt muss manuell bearbeitet werden, wenn Git die Änderungen nicht automatisch zusammenführen kann.

Schritte:
- `git merge neue-funktion`
- `git status`: sehen der betroffenen Dateien
- Konflikt beheben: Öffne die betroffene Datei und entscheide, welche Version übernommen werden soll.
- `git add index.html`: Dateien als gelöst merkieren.
- `git commit`: Merge abschließen
Konfliktdatei öffnen, gewünschte Änderungen auswählen oder kombinieren, Konfliktmarker entfernen, mit git add als gelöst markieren und den Merge mit git commit abschließen.
