# Praktisches Arbeiten mit GIT

## Git Commands
| Command | Beschreibung |
| --- |---|
| git init | Erstellt ein neues lokales Git-Repository im aktuellen Verzeichnis. Ab diesem Zietpunkt können __Änderungen an Dateien mit Git versioniert__ werden. |
| git status | Zeigt den __aktuellen Zustand des Repositories__ an.  Man sieht, welche Dateien geändert, neu hinzugefügt oder für den nächsten Commit vorgemerkt wurden. |
| git add | Fügt Dateien zur __Staging Area__ hinzu. Damit werden Änderungen für den nächsten Commit vorgemerkt.  ```git add index.html``` oder ```git add .```|
| git commit | Speichert die __vorgemerkten Änderungen__ als neuen __Commit in der lokalen Versionshistorie__. Jeder Commit stellt einen nachvollziehbaren Entwicklungsstand dar. ```git commit -m "Login-Funktion hinzugefügt``` |
| git log | Zeigt die __bisherigen Commits__ mit Informationen wie Commit-ID, Autor, Datum und Commit-Nachricht an. |
| git diff | Zeigt die __Änderungen im Working Directory, die noch nicht mit git add vorgemerkt wurden__. |
| git diff --staged	| Zeigt die __Änderungen, die bereits mit git add in der Staging Area vorgemerkt wurden und im nächsten Commit enthalten sein werden.__ |
| git restore | Stellt eine __Datei im Working Directory auf den Stand der Staging Area zurück__. Nicht vorgemerkte Änderungen an dieser Datei werden __verworfen__. |
| git restore --staged | __Entfernt eine Datei aus der Staging Area, ohne die Änderungen im Working Directory zu löschen__.|
| git branch | Zeigt __alle lokalen Branches__ an. |
| git switch | __Wechselt zwischen bestehenden Branches.__ Mit -c kann ein neuer Branch erstellt und direkt zu diesem gewechselt werden. |
| git log --oneline --graph --all | Zeigt die __Commit-Historie aller Branches__ in einer kompakten, grafischen Darstellung.  |
| git merge | Führt die __Änderungen eines anderen Branches in den aktuell ausgecheckten Branch zusammen__. |
| git branch -d | __Löscht einen lokalen Branch__, sofern Git dessen Löschung als sicher einstuft. |
| git revert | Macht die __Änderungen eines bestimmten Commits rückgängig__, indem ein __neuer Commit erstellt__ wird. Die bisherige Versionshistorie bleibt erhalten. |
| git show | Zeigt __detaillierte Informationen und Änderungen eines bestimmten Commits an.__ |
| git stash | __Speichert lokale, noch nicht commitete Änderungen vorübergehend__ und __stellt das Arbeitsverzeichnis für die betroffenen Änderungen zurück.__ Git legt deine aktuellen Änderungen vorübergehend zur Seite, damit du später daran weiterarbeiten kannst. |
| git stash list | Zeigt __alle zwischengespeicherten Änderungen__ (Stashes) an. |
| git stash pop | __Holt die zuletzt zwischengespeicherten Änderungen zurück__ und __entfernt den Stash bei erfolgreicher Anwendung aus der Liste.__ |
| git remote add | Fügt eine __Verbindung zu einem Remote-Repository hinzu.__ |
| git remote -v	| Zeigt die konfigurierten Remote-Repositories und deren URLs an. |
| git push | Überträgt lokale Commits in ein Remote-Repository.|
| git fetch | Lädt neue Commits und Informationen vom Remote-Repository herunter, ohne sie in den aktuellen lokalen Branch zu übernehmen. |
| git pull | Lädt Änderungen vom Remote-Repository herunter und integriert sie in den aktuellen lokalen Branch. |


## Szenario 1: Ein neues Projekt erstellen

### Git Commands
| Command | Beschreibung |
| --- |---|
| git init | Erstellt ein neues lokales Git-Repository im aktuellen Verzeichnis. Ab diesem Zietpunkt können __Änderungen an Dateien mit Git versioniert__ werden. |
| git status | Zeigt den __aktuellen Zustand des Repositories__ an.  Man sieht, welche Dateien geändert, neu hinzugefügt oder für den nächsten Commit vorgemerkt wurden. |
| git add | Fügt Dateien zur __Staging Area__ hinzu. Damit werden Änderungen für den nächsten Commit vorgemerkt.  ```git add index.html``` oder ```git add .```|
| git commit | Speichert die __vorgemerkten Änderungen__ als neuen __Commit in der lokalen Versionshistorie__. Jeder Commit stellt einen nachvollziehbaren Entwicklungsstand dar. ```git commit -m "Login-Funktion hinzugefügt``` |
| git log | Zeigt die __bisherigen Commits__ mit Informationen wie Commit-ID, Autor, Datum und Commit-Nachricht an. |

### Fragen
#### Was ist der Unterschied zwischen Working Directory, Staging Area und Repository?
| Commands | Beschreibung |
| --- |---|
| Working Directory (Arbeitsverzeichnis) | Hier befinden sich die __Dateien, die aktuell bearbeitet werden__. Dateien können erstellt, bearbeitet oder gelöscht werden. |
| Staging Area | Hier werden Änderungen mit ```git add``` für den nächsten commit __vorgemerkt__ |
| Repository | Hier speichert Git die __Versionshistorie des Projektes__. Mit ```git commit``` werden die vorgemerkten Änderungen dauert in der lokalen Git-Historie festghalten. |

#### Warum müssen Dateien vor einem Commit mit git add vorgemerkt werden?
Mit ```git add``` wird festgelegt, __welche Änderungen im nächsten commit enthalten sind__.   
Dadurch kann man gezielt auswählen, __welche Änderungen zusammengehören__.

```git commit``` übernimmt die vorgemerkten Änderungen aus der Staging Area.


#### Welche Informationen werden in einem Commit gespeichert?
Ein Git-Commit enhtält folgende Informationen
- __Commit-ID (Hash):__ Eindeutige Kennung des Commits.
- __Autor:__ Person, die die Änderungen erstellt hat.
- __Datum und Uhrzeit:__ Zeitangaben zur Erstellung des Commits.
- __Commit-Nachricht:__ Beschreibung der vorgenommenen Änderungen.
- __Projektzustand (Snapshot):__ Gespeicherter Stand der versionierten Dateien.
- __Verweis auf vorherige Commits:__ Dadurch entsteht die Versionshistorie.

Wie kann ich mir den letzten commit anzeigen?
- ```git show```: Letzten Commit Anzeigen
- ```git log```: Alle bisherigen Commits anzeigen

## Szenario 2: Änderungen nachvollziehen
### Git Commands
| Commands | Beschreibung |
| --- |---|
| git status | Zeigt den __aktuellen Zustand des Repositories__ an.  Man sieht, welche Dateien geändert, neu hinzugefügt oder für den nächsten Commit vorgemerkt wurden. |
| git diff | Zeigt die __Änderungen im Working Directory, die noch nicht mit git add vorgemerkt wurden__. |
| git diff --staged	| Zeigt die __Änderungen, die bereits mit git add in der Staging Area vorgemerkt wurden und im nächsten Commit enthalten sein werden.__ |
| git add | Fügt Dateien zur __Staging Area__ hinzu. Damit werden Änderungen für den nächsten Commit vorgemerkt.  ```git add index.html``` oder ```git add .``` |
| git commit | Speichert die __vorgemerkten Änderungen__ als neuen __Commit in der lokalen Versionshistorie__. Jeder Commit stellt einen nachvollziehbaren Entwicklungsstand dar. ```git commit -m "Login-Funktion hinzugefügt``` |
| git log | Zeigt die __bisherigen Commits__ mit Informationen wie Commit-ID, Autor, Datum und Commit-Nachricht an. |


### Fragen
#### Was zeigt git diff an?
```git diff``` zeigt die __Unterschiede zwischen dem aktuellen Working Directory und der Staging Area__. Damit erkennt man, welche Änderungen an bereits versionierten Dateien noch nicht für den nächsten Commit vorgemerkt wurden.   

#### Worin unterscheiden sich git diff und git diff --staged?
```git diff```
- zeigt noch nicht vorgemerkte Änderungen
- Vergleicht Working Directory mit Staging Area

```git diff --staged```
- Zeigt bereits vorgemerkte Änderungen.
- Vergleicht Staging Area mit dem letzten Commit.

#### Warum sind aussagekräftige Commit-Nachrichten wichtig?
Damit __Änderungen in der Versionshistorie verständlich und nachvollziehbar__ bleiben.
- __Nachvollziehen__, was in einem Commit geändert wurde
- __Anforderungen bzw. Änderungen__ zu finden (z.B. Ref zum Ticket)
- Erleichterung bei der __Zusammenarbeit__ und bei Merge Request

## Szenario 3: Einen Fehler rückgängig machen
### Git Commands
| Commands | Beschreibung |
| --- |---|
| git diff | Zeigt die __Änderungen im Working Directory, die noch nicht mit git add vorgemerkt wurden__. |
| git restore | Stellt eine __Datei im Working Directory auf den Stand der Staging Area zurück__. Nicht vorgemerkte Änderungen an dieser Datei werden __verworfen__. |
| git restore --staged | __Entfernt eine Datei aus der Staging Area, ohne die Änderungen im Working Directory zu löschen__.|
| git status | Zeigt den __aktuellen Zustand des Repositories__ an.  Man sieht, welche Dateien geändert, neu hinzugefügt oder für den nächsten Commit vorgemerkt wurden. |

### Fragen
#### Was ist der Unterschied zwischen git restore und git restore --staged?
```git restore```
- stellt den __Inhalt einer Datei wieder her__
- Working Directory
- __nicht vorgemerkte Änderungen gehen verlogen__

```git restore --staged```
- macht das vormerken mit ```git add``` rückgängig
- betrifft die Staging Area
- __Änderungen im Working Directory bleiben erhalten__

#### Welche Änderungen gehen beim Wiederherstellen einer Datei verloren?
- Bei ```git restore <datei>``` gehen die __noch nicht in der Staging Area vorgemerkten Änderungen verloren__.
- Hinzugefügte, veränderte oder gelöschte Zeilen auf den Stand der Staging Area zurückgesetzt
- Bereits mit ```git add``` __vorgemerkte Änderungen bleiben erhalten__

## Szenario 4: Ein neues Feature entwickeln (Branching)
### Git Commands
| Commands | Beschreibung |
| --- |---|
| git branch | Zeigt __alle lokalen Branches__ an. |
| git switch | __Wechselt zwischen bestehenden Branches.__ Mit -c kann ein neuer Branch erstellt und direkt zu diesem gewechselt werden. |
| git log --oneline --graph --all | Zeigt die __Commit-Historie aller Branches__ in einer kompakten, grafischen Darstellung. |

### Fragen
#### Warum verwendet man Branches?
Um __verschiedene Entwicklungsstände unabhängig voneinander weiterzuentwickeln__ und __parallel an mehereren Features zu arbeiten__. Dadurch können __neue Funktionen entwickelt und Fehler behoben ohne den main direkt zu veränden__.

#### Was passiert mit den Dateien beim Wechsel zwischen Branches?
Die Working Directory wird an den __Stand des Zielbranches angepasst__.

#### Welche Vorteile bietet die Entwicklung neuer Funktionen in eigenen Branches?
- __Trennung der Entwicklung:__ Neue Funktionen können unabhängig vom Hauptbranch entwickelt werden.
- __Stabilität:__ Es gibt den Hauptbranch, der immer Kompeliert
- __Teamarbeit:__ Mehrere Entwickler können gleichzeitig an unterschiedlichen Funktionen arbeiten.
- __Einfacheres Testen:__ Neue Funktionen können überprüft werden, bevor sie in den Hauptbranch übernommen werden.
- __Nachvollziehbarkeit:__ Änderungen einer Funktion lassen sich leichter zuordnen.

## Szenario 5: Das neue Feature integrieren (Merge)
### Git Commands
| Commands | Beschreibung |
| --- |---|
| git merge | Führt die __Änderungen eines anderen Branches in den aktuell ausgecheckten Branch zusammen__.
| git branch -d | __Löscht einen lokalen Branch__, sofern Git dessen Löschung als sicher einstuft. |
| git log --graph --oneline --all | Zeigt die __Commit-Historie aller Branches__ in einer kompakten, grafischen Darstellung. |

### Fragen
#### Was passiert bei einem Merge?
Es werden die __Entwicklungsstände von zwei Branches zusammengeführt__.   
Dabei werden die __Änderungen eines Branches in den aktuell verwendeten Branch übernommen__.

#### Was versteht man unter einem Fast-Forward-Merge?
Ein __Fast-Forward-Merge__ ist eine __einfache Form__ des Merges, bei der Git __keinen zusätzlichen Merge-Commit__ erstellen muss.
Das funktioniert, wenn __seit der Verzweigung keine neuen Commits im Zielbranch entstanden__ sind.
__Git verschiebt dabei lediglich den Branch-Zeiger__ auf den neuesten Commit des anderen Branches.

#### Warum kann ein Branch nach einem erfolgreichen Merge gelöscht werden?
Die __Änderungen wurden bereits in den Zielbranch übernommen.__
Dadurch erhält man: 
- __Übersichtlichkeit:__ Nicht mehr benötigte Branches werden entfernt
- __Bessere Organisation:__ Es ist leichter zu erkennen, welche Funktionen noch entwickelt werden

## Szenario 6: Einen Merge-Konflikt lösen
| Command | Beschreibung |
| --- |---|
| git merge | Führt die __Änderungen eines anderen Branches in den aktuell ausgecheckten Branch zusammen__. |
| git status | Zeigt den __aktuellen Zustand des Repositories__ an.  Man sieht, welche Dateien geändert, neu hinzugefügt oder für den nächsten Commit vorgemerkt wurden. |
| git diff | Zeigt die __Änderungen im Working Directory, die noch nicht mit git add vorgemerkt wurden__. |
| git add | Fügt Dateien zur __Staging Area__ hinzu. Damit werden Änderungen für den nächsten Commit vorgemerkt.  ```git add index.html``` oder ```git add .```|
| git commit | Speichert die __vorgemerkten Änderungen__ als neuen __Commit in der lokalen Versionshistorie__. Jeder Commit stellt einen nachvollziehbaren Entwicklungsstand dar. ```git commit -m "Login-Funktion hinzugefügt``` |

### Fragen
#### Wann entsteht ein Merge-Konflikt?
Wenn __zwei Branches widersprüchliche Änderungen enthalten__ und __Git diese nicht automatisch zusammenführen kann.__    
Wenn beide Änderungen auf demselben ursprünglichen Stand basieren, kann Git beim Zusammenführen einen Konflikt melden, weil __nicht eindeutig ist, welche Änderung übernommen werden soll.__   
Merge-Konflikte können auch entstehen, wenn eine Datei in einem Branch gelöscht und im anderen bearbeitet wurde.

#### Wie kennzeichnet Git widersprüchliche Änderungen?
`<<<<<<<` HEAD	Beginn der Version des aktuellen Branches
`=======` Trennt die beiden widersprüchlichen Versionen
`>>>>>>>` neue-funktion	Ende der Version aus dem zusammenzuführenden Branch

#### Wie kann ein Merge-Konflikt aufgelöst werden?
Ein Merge-Konflikt muss __manuell__ bearbeitet werden, wenn Git die Änderungen nicht automatisch zusammenführen kann.

Schritte:
- `git merge neue-funktion`
- `git status`: sehen der betroffenen Dateien
- Konflikt beheben: Öffne die betroffene Datei und entscheide, welche Version übernommen werden soll.
- `git add index.html`: Dateien als gelöst merkieren.
- `git commit`: Merge abschließen
Konfliktdatei öffnen, gewünschte Änderungen auswählen oder kombinieren, Konfliktmarker entfernen, mit git add als gelöst markieren und den Merge mit git commit abschließen.

## Szenario 7: Einen Fehler in der Versionsgeschichte korrigieren
### Git Commands
| Commands | Beschreibung |
| --- |---|
| git log | Zeigt die __bisherigen Commits__ mit Informationen wie Commit-ID, Autor, Datum und Commit-Nachricht an.  |
| git revert | Macht die __Änderungen eines bestimmten Commits rückgängig__, indem ein __neuer Commit erstellt__ wird. Die bisherige Versionshistorie bleibt erhalten. |
| git show | Zeigt __detaillierte Informationen und Änderungen eines bestimmten Commits an.__ |

### Fragen
#### Wie funktioniert git revert?
`git revert` macht die __Änderungen eines bestimmten Commits rückgängig__, indem Git einen __neuen Commit__ mit den entgegengesetzten Änderungen erstellt.   
Der __ursprüngliche Commit bleibt dabei erhalten__.

Beispiel:
1. Commit A: Aufgabenverwaltung erstellt.
2. Commit B: Login-Funktion hinzugefügt.
3. Commit C: Login-Funktion durch git revert wieder entfernt.

#### Warum wird beim Revert ein neuer Commit erzeugt?
Damit die __Versionshistorie vollständig und nachvollziehbar__ bleibt.

__Dadurch kann man später erkennen:__
- Welche __Änderung ursprünglich durchgeführt__ wurde.
- __Wann und von wem sie rückgängig gemacht wurde.__
- __Warum__ eine bestimmte Funktion wieder entfernt wurde.
Das ist besonders bei der Zusammenarbeit im Team wichtig, weil die gemeinsame Commit-Historie nicht nachträglich umgeschrieben wird.

#### Was ist der Unterschied zwischen git revert und git reset?
Bei beiden werden Änderungen rückgängig gemacht.

| git revert | git reset |
| --- | --- |
|Erstellt einen neuen Commit, der frühere Änderungen rückgängig macht. | Verschiebt den aktuellen Branch-Zeiger auf einen anderen Commit. |
| Die bisherige Commit-Historie bleibt erhalten. | Commits können aus der aktuellen Branch-Historie entfernt werden. |
| Gut für bereits veröffentlichte Commits geeignet. |Eher für lokale, noch nicht veröffentlichte Commits geeignet. |
| Macht gezielt die Änderungen eines Commits rückgängig. |Setzt den Branch auf einen gewählten Entwicklungsstand zurück. |

## Szenario 8: Änderungen vorübergehend sichern (Stashing)
### Git Commands
| Commands | Beschreibung |
| --- |---|
| git stash | __Speichert lokale, noch nicht commitete Änderungen vorübergehend__ und __stellt das Arbeitsverzeichnis für die betroffenen Änderungen zurück.__ Git legt deine aktuellen Änderungen vorübergehend zur Seite, damit du später daran weiterarbeiten kannst. |
| git stash list | Zeigt __alle zwischengespeicherten Änderungen__ (Stashes) an. |
| git stash pop | __Holt die zuletzt zwischengespeicherten Änderungen zurück__ und __entfernt den Stash bei erfolgreicher Anwendung aus der Liste.__ |

### Fragen
#### Wozu dient git stash?
`git stash` dient dazu, __nicht commitete Änderungen vorübergehend zwischenzuspeichern__, __ohne einen neuen Commit erstellen__ zu müssen.  
Dadurch kann man die aktuelle Arbeit unterbrechen und später an derselben Stelle fortsetzen.  
Die Änderungen bleiben im Stash gespeichert, während das Arbeitsverzeichnis für andere Arbeiten vorbereitet wird.

#### Wann ist Stashing sinnvoll?
Stashing ist sinnvoll, wenn man seine aktuelle Arbeit unterbrechen muss, die Änderungen aber noch nicht fertig für einen Commit sind.

Beispiel:
- Man arbeitet an einer neuen Funktion und muss kurzfristig einen Fehler beheben.
- Man möchte vorübergehend mit einem sauberen Arbeitsverzeichnis arbeiten.
- Man möchte Änderungen später fortsetzen, ohne einen unfertigen Commit erstellen zu müssen.

Ansonsten müsste man dasselbe Projekt mehrmals clonen

#### Was ist der Unterschied zwischen git stash apply und git stash pop?
Beide Befehle stellen zwischengespeicherte Änderungen wieder her. 
Der Unterschied besteht darin, ob der Stash __anschließend gespeichert bleibt oder gelöscht wird.__


`git stash apply`
- Stellt zwischengespeicherte Änderungen wieder her.	
- Der Stash bleibt in der Stash-Liste erhalten.
- Sinnvoll, wenn man __denselben Stash mehrfach verwenden__ möchte.

`git stash pop`
- Stellt zwischengespeicherte Änderungen wieder her.
- Der Stash wird bei __erfolgreicher Anwendung aus der Liste entfernt.__
- Sinnvoll, wenn man die __Änderungen nur einmal zurückholen__ möchte.

## Szenario 9: Mit einem Remote-Repository arbeiten
### Git Commands
| Commands | Beschreibung |
| --- |---|
| git remote add | Fügt eine __Verbindung zu einem Remote-Repository hinzu.__ |
| git remote -v	| Zeigt die konfigurierten Remote-Repositories und deren URLs an. |
| git push | Überträgt lokale Commits in ein Remote-Repository.|
| git fetch | Lädt neue Commits und Informationen vom Remote-Repository herunter, ohne sie in den aktuellen lokalen Branch zu übernehmen. |
| git pull | Lädt Änderungen vom Remote-Repository herunter und integriert sie in den aktuellen lokalen Branch. |

### Fragen
#### Was ist der Unterschied zwischen einem lokalen und einem Remote-Repository?
__Lokales Repository__
- Befindet sich auf dem __eigenen Computer.__
- Hier wird __lokal entwickelt und committet.__	
- Kann auch ohne Internet verwendet werden.
- Änderungen werden mit git commit lokal gespeichert.


__Remote Repository__
- Befindet sich auf einem __anderen Computer oder Server__ beispielsweise GitHub.
- Dient zum __Austausch und zur gemeinsamen Verwaltung von Änderungen.__
- Für den Zugriff ist normalerweise eine Netzwerkverbindung erforderlich.
- Commits werden beispielsweise mit git push übertragen.

#### Worin unterscheiden sich git fetch und git pull?
Es werden Änderungen vom Remote-Repository heruntergeladen.    
Hauptunterschied: __ob Änderungungen automatisch in den aktuellen Branch integriert werden__

`git fetch`
- Lädt neue Commits herunter.
- Der __aktuelle lokale Branch bleibt unverändert.__
- __Änderungen können vor der Übernahme überprüft werden.__

`git pull`
- __Lädt neue Commits herunter und integriert sie.__
- Der aktuelle lokale Branch kann verändert werden.
- Änderungen werden direkt durch __Merge oder Rebase übernommen.__

#### Was passiert bei git push?
Lokale Commits an ein Remote-Repository übertragen.

## Szenario 10: Zusammenabreit im Team (Pull- bzw. Merge-Requests)
### Git Commands
| Commands | Beschreibung |
| --- |---|
| git clone | Erstellt eine __lokale Kopie__ eines bestehenden Remote-Repositories inklusive der Versionshistorie.
git branch | Zeigt __vorhandene lokale Branches__ an oder erstellt neue Branches. |
| git switch | Wechselt zwischen Branches oder erstellt mit -c einen neuen Branch und wechselt direkt dorthin. |
| git push | Überträgt lokale Commits in das Remote-Repository, beispielsweise auf GitHub. |
| git pull | Lädt Änderungen aus dem Remote-Repository herunter und integriert sie in den aktuellen lokalen Branch. |
| git fetch | Lädt neue Commits und Informationen vom Remote-Repository herunter, ohne sie in den aktuellen lokalen Branch zu übernehmen. |
| git merge | Führt die Änderungen eines anderen Branches in den aktuell verwendeten Branch zusammen. |


### Fragen
#### Wie können mehrere Entwickler gleichzeitig an einem Projekt arbeiten?
Durch verschiedene Branches kann gleichzeitig an einem Projekt gearbeitet werden. Durch Merges werden diese Änderungen dann zusammengefürht.

#### Welche Aufgaben haben Pull Requests bzw. Merge Requests
Es ist eine Anfrage, Änderungen aus einem Branch in einem anderen zu übernehmen.

Im Zuge dessen wird häufig eine Code-Review durchgeführt (Freigabe des Codes und Feedback).

#### Warum sollte der Hauptbranch möglichst stabil bleiben?
Der Main-Branch sollte nur einen funktionierenden, getesteten und gerieveten Code enthalten.
Von diesem aus wird häufig deployed und dient als Basis.
- Zuverlässigkeit: Aufbau von einer funktionsfähigen Version
- Weniger Fehler: Keine unfertigen Funktionen
- Bessere Auslieferung: Es gibt eine funktionierende Version


