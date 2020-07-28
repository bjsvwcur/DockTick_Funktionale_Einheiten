# Beschreibung zum Ablauf Erfassung eines neuen Layers

## 1. Layer neu
Beim neuen Layer liegen dessen Daten noch nicht in der Produktions-DB und ist daher noch nicht im AGDI erfasst

### *1.1 neu*
Der Auftraggeber erfasst im Ticketsystem ein neues Ticket im Projekt Tagesgeschäft oder im Projekt P_Ablösung SO!MAP Client. Im Tickets stehen die Details zum Auftrag und der Tracker wird auf "Layer Web GIS Client" gestellt.
Wichtig hierbei ist, dass noch keine Zielversion, sondern lediglich ein Abgabedatum erfasst wird. Das Ticket wird einer Person (nachfolgend Auftragnehmer) zugewiesen.
```
Tracker: Layer Web GIS Client
neuer Redminestatus: 	neu
Änderungstyp: 	Neuer Layer 
```
### *1.2 in Bearbeitung*
Der Auftragnehmer nimmt das Ticket entgegen und setzt den Redmine-Status auf "in Bearbeitung"
```
neuer Redminestatus: 	in Bearbeitung
```
### *1.3 GRETL-Job erstellen/anpassen*
Der Auftragnehmer erstellt einen Branch des [GRETL-Repositories](https://github.com/sogis/gretljobs) und erstellt gegebenenfalls einen neuen Ordner mit dem zukünftigen Schemenname der Tabelle. In diesem Ordner wird das SQL, welches die Daten aus der Erfassungs-DB selektiert, und das build.gradle, welches den Job definiert abgelegt.

Beim Erstellen des SQLs sollten undbedingt die SQL-Richtlinien beachtet werden: XXXXX

### *1.3 DDL-/Modell-Skript erstelle*
Existiert die Tabelle resp. das Schema noch nicht auf der Publikattions-DB, so muss ein entsprechendes SQL-Skript erstellt werden, welches das Schema resp. die Tabelle erstellt.

Siehe [Modelbasierte Datenerfassung](https://sogis.github.io/modellbasierte-datenerfassung-handbuch/#_publikationsmodell), Kapitel 3.4.

Die SQL-Skripts und das Bash-Skript gilt es dem Redmine-Ticket anzuhängen.

### *1.4 Pullrequest*
Wenn alles soweit vorbereitet ist und in der Entwicklungsumgebung einwandfrei läuft, kann ein Pullrequest erstellt werden. Auf https://github.com/sogis/gretljobs/branches beim entsprechenden Branch "New pull request" klicken und die GDI als Reviewer anwählen.
Der Link zum Pullrequest ist im Redmine-Ticket aufzuführen.
```
neuer Redminestatus: 	GRETL-Job bereit 
Zugewiesen an: 	GDI 
```
