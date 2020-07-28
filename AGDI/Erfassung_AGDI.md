# Erfassung im AGDI

## 1.	Arbeitsumgebungen – Was wird wo gemacht?

### 1.1.	Produktionsumgebung

Ca alle 2 Wochen wird der Stand der Integrationsumgebung auf die Produktionsumgebung gespielt (Termin für Rollout steht im Redmine). Es sollte hier keine Anpassungen vorgenommen werden

URL des WebGIS-Client:	
https://geo.so.ch/map 

### 1.2.	Integrationsumgebung

In der Integrationsumgebung können neue Layer erfasst werden oder bestehende geändert werden. Hier werden sie auch von den Ämtern geprüft und abgenommen. Ca alle 2 Wochen wird der Stand der Integrationsumgebung auf die Produktionsumgebung gespielt.

URL des WebGIS-Client:	https://geo-i.so.ch/map 

### 1.3.	Testumgebung

In der Testumgebung wird die Anwendung angepasst und getestet. Sie läuft daher nicht stabil.

URL des WebGIS-Client:	https://geo-t.so.ch/map 

## 2.	Schema und Tabellen anlegen
> Link auf Betrieb

## 3.	Gretljob im Jenkins anlegen

### 3.1.	Was sind Gretljobs?

Bei Gretljobs handelt es sich um Jobs, welche mittels Gretl vorgenommen werden. In diesem Fall, werden in den Jobs entweder die Daten aus dem Erfassungsmodell in der sogis-DB umgebaut und ins Publikationsmodell auf der pub-DB gespielt oder es werden die Daten mehr oder weniger direkt von der sogis-DB in die pub-DB gespielt.
Für jedes Schema gibt es einen eigenen Ordner unter https://github.com/sogis/gretljobs und in jedem dieser Order gibt es ein build.gradle-File («Job») und mehrere sql-Files.

### 3.2.	Neuer Gretljob oder bestehender Gretljob anpassen

Um einen neuen Gretljob anzulegen oder einen Gretljob anzupassen, muss das Repository geklont (nach lokal heruntergeladen) werden. Anschliessend können Änderungen/Ergänzungen in einem Branch vorgenommen und im Anschluss in den Master-Branch integriert werden.

### 3.2.1.	Gretljobs klonen

Falls nicht vorhanden, muss ein Login auf GitHub anlegen (Username frei wählbar, E-Mailadresse vom Kanton). Anschliessend muss die GDI benachrichtigt werden, damit der neue User in die Gruppe Contributors aufnimmt.
Mit git clone https://github.com/sogis/gretljobs.git das git-Repository lokal anlegen.

### 3.2.2.	Neuer Branch anlegen

Bevor ein neuer Branch angelegt wird, empfiehlt sich folgendes Vorgehen:
```
git checkout master
git pull
```
Anschliessend kann ein neuer Branch angelegt werden:
```
git checkout –b mein_neuer_branch
```
In diesem Branch können dann die Änderungen/Ergänzungen vorgenommen werden.

....
....

## 5.	Im AGDI erfassen

Damit Tabellen oder Datei im WebGIS-Client und/oder im WMS und/oder im WFS ersichtlich sind müssen sie als Datasets im AGDI erfasst sein.
Folgenden Sonderzeichen müssen in den Texten der Kartenkonfigurationen gemieden werden:
```
< & > " '
```
 ...
 ...

