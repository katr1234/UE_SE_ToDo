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


#### Worin unterscheiden sich git diff und git diff --staged?


#### Warum sind aussagekräftige Commit-Nachrichten wichtig?






