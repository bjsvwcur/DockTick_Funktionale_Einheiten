# QGIS Desktop
Verantwortlicher: Andreas Neumann

## Beschreibung Funktionale Einheit:
Das Amt für Geoinformation betreibt und supportet für seine Kunden das QGIS LTR. Ca. 130 Benutzer haben einen Zugang zur Software. Folgende Aufgaben sind Bestandteil für den Betrieb und den Support:
* Supportunterstützung First- und Second-Level
* Schulung
* Koordination von Updates und Upgrades 
* Koordination von Bugfixing mit externer Firma (Third-Level-Support)

## Benutzung:
Seit 01.09.2020 ist das QGIS LTR 3.10.7 produktiv geschaltet.
Die Anwendung ist im Desktop 2016 unter `Start/Alle Programme/Fachanwendungen/` zu finden. Das QGIS ist im Desktop 2016 nur für jene Benutzer ersichtlich, welche mittels einem Systemantrag beim AIO die Freigabe beantragt haben (Anwendung `GA_Xen_QGIS`).

### Anleitungen:
* AGI-Anleitungen: https://intraso.rootso.org/verwaltung/bau-und-justiz/amt-fuer-geoinformation/dokumente-und-grundlagen/qgis/
* QGIS 3.10 Benutzerhanduch: https://docs.qgis.org/3.10/de/docs/user_manual/index.html

### First- und Second-Level Support:
Die GIS Koordinatoren und weitere Benutzer haben Zugriff auf das Projekt «QGIS Support» im Ticketsystem Redmine und können Tickets erfassen. Die GDI Gruppe ist verantwortlich für die zeitnahe Bearbeitung der Tickets. 

Der Ablauf erfolgt gemäss folgendem Schema:

![](https://github.com/bjsvwcur/DockTick_Funktionale_Einheiten/blob/master/Documents/QGIS_Desktop/Support.png)

**Vorgehen:** Die Problemstellung erfolgt vorzugsweise über das Ticketsystem Redmine, kann aber auch per E-Mail oder Telefon entgegengenommen werden. Wenn das Problem per Mail oder Telefon direkt gelöst werden kann muss kein Ticket im Redmine erfasst werden. Je nach Schwierigkeit des Problems kann es vom First-Level-Support bereits gelöst werden, oder es wird an den Second-Level-Support weitergegeben. Beim erstellen eines Tickets ist folgendes zu beachten:

* Fehlerbeschreibung im Ticket muss Nachvollziehbar sein
* Beispieldaten oder Screens beifügen
* wer hat das Problem gemeldet 

Projekt «QGIS Support» Redmine: https://geoweb.rootso.org/redmine/projects/feedback-qgis/issues

## Betrieb:
### Third-Level-Support:
Im Third-Level-Support finden sich opengis.ch und das QGIS Issues Tracking https://issues.qgis.org/. Sie werden hinzugeholt bei neu auftretenden Problemen, deren Lösung die aufwändige, systematische Arbeit von Spezialisten oder spezialisierten Teams erfordert. An den Third-Level Support werden Probleme weitergegeben welche der Second-Level Support nicht lösen kann. Ebenfalls werden Bugs welche das Arbeiten mit QGIS beinträchtigen gemeldet.

Ticketsystem opengis.ch: https://app.hive.com/signin

Supportvertrag opengis.ch: https://www.pastel.io/users/sign_in

### Releasplanung:
Die Update-Zeitpunkte richten sich nach der Releaseplanung von QGIS. Das AGI führt ca. alle 4 Monate Updates durch. Das heisst, die neue LTR-Version wird mit dem Erscheinen von Version x.x.1 installiert. Ca. 4 Monate später wird die Bugfix-Version x.x.5 installiert, ca. 4 Monate später wird die Bugfix-Version x.x.9 installiert.

**Umgang mit Blocker-Bugs nach Inbetriebnahme**

Falls nach Inbetriebnahme Blocker-Bugs auftreten sollten, muss auf eine nachfolgende Bugfix-Version gewartet werden, in welcher der Fehler korrigiert ist. Im Ausnahmefall kann auf eine frühere Bugfix-Version zurückgegriffen und diese installiert werden.

**Umgang mit verspäteten Releases**

Falls sich ein Release von Seite QGIS her verzögern sollte, nimmt das AGI in Kauf, dass es eine Verzögerung des geplanten Update-Zeitpunkts geben kann.

AIO Releaseplanung: https://intraso.rootso.org/fileadmin/intranet/fd/fd-aio/fd-aio-allgemein/pdf/Releaseplanung.pdf

QGIS Releasplanung: https://qgis.org/en/site/getinvolved/development/roadmap.html?highlight=release


## Testing:
Bugfix-Versionen werden ca. zweimal pro Jahr installiert. Sie werden nur vom AGI getestet, da davon ausgegangen wird, dass sich mit den Bugfixes keine neuen Fehler in den Release schleichen. Falls sich das nicht bestätigt, wird die Installation von Bugfix-Versionen auf einmal pro Jahr reduziert, mit vorgängigen Tests durch das AGI und die Ämter.
Falls in der Testphase Blocker-Bugs festgestellt werden, werden diese dem Wartungspartner gemeldet. Das Update verschiebt sich entsprechend auf eine nachfolgende Bugfix-Version.

**Testkonzept:**

Testkonzept: `H:\BJSVW\Agi\Projekte\AGI\QGIS-LTR Update\Testkonzept_V02.docx`

**Vorlageprotokolle:**
Projekte: `H:\BJSVW\Agi\Projekte\AGI\QGIS-LTR Update\Vorlage_Testprotokoll_Projekte_V2.docx`

Werkzeuge: `H:\BJSVW\Agi\Projekte\AGI\QGIS-LTR Update\Vorlage_Testprotokoll_Werkzeuge_V2.docx`

