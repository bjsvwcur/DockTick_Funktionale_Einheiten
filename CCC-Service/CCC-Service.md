# CCC-Service

Verantwortlicher: Oliver Jeker

## Beschreibung Funktionale Einheit:
Bilaterale Kommunikationsschnittstelle, mit welcher Fachapplikationen ohne GIS-Fähigkeiten die Karten- und Editierfunktionen der GDI nutzen können. Die Kommunikation erfolgt über Websocket.

### Funktionsweise:
![](https://github.com/sogis/ccc-service/raw/master/docs/res/overview.png)

Der CCC-Service verbindet als "Mittelsmann" GIS-unwillige Fachapplikationen mit den Kartenapplikationen des AGI.

Die Session stellt sicher, dass die Nachrichten für den Benutzer korrekt von der Fachapplikation an die Kartenapplikation des AGI weitergereicht wird.

### Repo und weitere Informationen:
ccc-service: https://github.com/sogis/ccc-service
