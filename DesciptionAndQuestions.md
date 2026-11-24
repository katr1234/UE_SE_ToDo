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
- Bereits mit ```git add``` vorgemerkte Änderungen bleiben erhalten.






