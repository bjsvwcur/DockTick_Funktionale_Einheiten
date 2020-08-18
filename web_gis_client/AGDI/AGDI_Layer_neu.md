# Beschreibung zum Ablauf "Erfassung eines neuen Layers"

Beim neuen Layer liegen dessen Daten noch nicht Produktions-DB der geodb und er ist daher noch nicht im AGDI erfasst

**neu**

Der Auftraggeber erfasst im Redmine ein neues Ticket im Projekt Tagesgeschäft oder im Projekt P_Ablösung SO!MAP Client. Im Tickets stehen die Details zum Auftrag und der Tracker wird auf "Layer Web GIS Client" gestellt.
Wichtig hierbei ist, dass noch keine Zielversion, sondern lediglich ein Abgabedatum erfasst wird. Das Ticket wird einer Person (nachfolgend Auftragnehmer) zugewiesen.
Tracker 	Layer Web GIS Client
neuer Redminestatus: 	neu
Änderungstyp 	"Neuer Layer"

**in Bearbeitung**

Der Auftragnehmer nimmt das Ticket entgegen und setzt den Redmine-Status auf "in Bearbeitung"
neuer Redminestatus: 	in Bearbeitung

**GRETL-Job erstellen/anpassen**

Der Auftragnehmer erstellt einen Branch des GRETL-Repositories und erstellt gegebenenfalls einen neuen Ordner mit dem zukünftigen Schemenname der Tabelle. In diesem Ordner wird das SQL, welches die Daten aus der Erfassungs-DB selektiert, und das build.gradle, welches den Job definiert abgelegt.

Beim Erstellen des SQLs sollten undbedingt die SQL-Richtlinien beachtet werden: H:\BJSVW\Agi\GDI\Richtlinien\SQL_Richtlinien.docx

**DDL-/Modell-Skript erstellen**

Existiert die Tabelle resp. das Schema noch nicht auf der Publikattions-DB, so muss ein entsprechendes SQL-Skript erstellt werden, welches das Schema resp. die Tabelle erstellt.

Beim Modell muss ein prescript.sql, in welchem die Rolle gesetzt wird, und ein postscript.sql in welchem die Rechte vergeben werden und den Kommentar auf das Schema setzt, sowie ein bash-Skript, welches mit ili2pg das Modell in der DB anlegt, erstellt werden.

Die SQL-Skripts und das Bash-Skript gilt es dem Redmine-Ticket anzuhängen.

**Pullrequest**

Wenn alles soweit vorbereitet ist und in der Entwicklungsumgebung einwandfrei läuft, kann ein Pullrequest erstellt werden. Auf https://github.com/sogis/gretljobs/branches beim entsprechenden Branch "New pull request" klicken und die GDI als Reviewer anwählen.
Der Link zum Pullrequest ist im Redmine-Ticket aufzuführen.
neuer Redminestatus: 	GRETL-Job bereit
Zugewiesen an: 	GDI

**Review (1)**

Jemand von der GDI reviewed den GRETL-Job (SQL-Files und build.gradle) und die DDL- respektive. Modell-Skripte. Sollten Anpassungen notwendig sein so müssen diese im Fall des GRETL-Jobs im github und im Fall der DDL-/Modell-Skripte im Redmine-Ticket vermerkt sein. Zudem erhält das Redmine-Ticket wieder der Status "in Bearbeitung" und wird dem Auftragnehmer zurückgewiesen.
neuer Redminestatus: 	in Bearbeitung
Zugewiesen an: 	Auftragnehmer

Sollte alles in Ordnung sein, so bleibt das Ticket bei der GDI und es folgt der Schritt "Merge von Pullrequest"

**Merge von Pullrequest**

Wenn beim Review alles in Ordnung war, kann der Branch in den Master gemerged werden. Im Anschluss an den Merge soll der Branch gelöscht werden.
neuer Redminestatus: 	reviewed GDI

**DDL/Modell in Integration-DB**

Mittels dem DDL-Skript respektive dem Modell und den Pre- und Postskripts wird das Schema und die Tabellen in der Integrations-DB angelegt.

**GRETL-Job ausführen (Integration)**

Um die Daten in die neuen Tabellen zu spielen muss der GRETL-Job in der Integrationsumgebung ausgeführt werden. Sollte dieser fehlschlagen, so ist dies im Redmine-Ticket zu vermerken, das Ticket wird dem Auftragnehmer zurückgewiesen und der Redmine-Status auf "in Bearbeitung" gesetzt.
neuer Redminestatus: 	in Bearbeitung
Zugewiesen an: 	Auftragnehmer

Sollte der GRETL-Job einwandfrei durchlaufen, so erhält das Ticket den Redmine-Status "vorbereitet Integrations-DB" und wird dem Auftragnehmer zugewiesen.
neuer Redminestatus: 	vorbereitet Integrations-DB
Zugewiesen an: 	Auftragnehmer

**Erfassung/Anpassung im AGDI**

Der Auftragnehmer erfasst den oder die Layer im AGDI als Dataset (evtl. auch als Productset). Wobei in jedem neu erfassten oder bearbeiteten Dataset in der Beschreibung der Begriff "Bearbeitung" auftauchen muss, damit die Layer nicht automatisch publiziert werden. Den Productsets sollte vor jedem Release die Flags bei "in WMS verfügbar" und "in WFS verfügbar" entfernt werden.
Sobald der Layer fertig erfasst ist, so erhält das Ticket den Redmine-Status "erfasst in AGDI" und geht an den Auftraggeber.
neuer Redminestatus: 	erfasst in AGDI
Zugewiesen an: 	Auftraggeber

**Review (2)**

Der Auftraggeber prüft, ob alles wunschgemäss ausgeführt wurde. Sollte etwas nicht wunschgemäss umgesetzt worden sein, so geht das Ticket zurück an den Auftragnehmer und erhält den Status "in Bearbeitung".
neuer Redminestatus: 	in Bearbeitung
Zugewiesen an: 	Auftragnehmer

Sollte aber alles zufriedenstellend ausgeführt worden sein, erhält das Ticket den Status "reviewed AG" und erhält eine Zielversion. Bei der Zielversion wird der Releasetermin ausgewählt an welchem der/die Layer ausgerollt werden sollen. Zudem wird das Ticket der GDI zugewiesen.
Zudem muss im AGDI in der Beschreibung der Layer das Wort "Bearbeitung" entfernt werden.
neuer Redminestatus: 	reviewed AG
Zugewiesen an: 	GDI
Zielversion: 	Releasetermin

**DDL/Modell ausrollen**

Am Release-Tag wird in der Produktionsumgebung das DDL-Skript laufen gelassen respektive das Modell mit dessen pre- und postskripts angelegt.

**GRETL-Job ausrollen & ausführen**

Am Release-Tag wird der GRETL-Job in der Produktionsumgebung laufen gelassen. Im Anschluss wird das Ticket wieder dem Auftraggeber zur Überprüfung übergeben.
neuer Redminestatus: 	ausgerollt
Zugewiesen an: 	Auftraggeber

**Überprüfung**

Der Auftraggeber überprüft in der Produktionsumgebung, ob alles wunschgemäss ausgeführt wurde. Sollte dem nicht der Fall sein muss das Ticket mit dem entsprechenden Hinweis an die entsprechende Person zugewiesen werden.

Wenn alles in Ordnung ist, so erhält das Ticket den Status "erledigt" und ist somit abgeschlossen.
neuer Redminestatus: 	erledigt 
