# ilivalidator-web-service

Verantwortlicher: Stefan Ziegler

## Beschreibung Funktionale Einheit
Der ilivalidator-web-service ist eine [Spring-Boot-Anwendung](https://spring.io/projects/spring-boot) und verwendet [ilivalidator](https://github.com/claeis/ilivalidator) für die Validierung der INTERLIS-Übertragungsdatei.

Der ilivalidator-web-service  stellt eine einfache Art dar INTERLIS-Daten gegenüber einem INTERLIS-Modell zu prüfen (= Modellkonformität). Die zu prüfenden INTERLIS-Daten werden mittels Webformular auf einen Server hochgeladen, wo sie anschliessend automatisch geprüft werden. Das Prüfresultat wird direkt im Browser angezeigt.
Für die Nutzungsplanung wurden spezielle Validierungsfunktionen implementiert. 

Die Programmbibliothek ilivalidator selbst ist nicht Bestandteil dieser funktionalen Einheit. 

### Funktionsweise
<Hier fehlt das Diagramm und die Erläterungen dazu>

## Benutzung
**Aufruf des ilivalidator-web-service:**

Produktion: https://geo.so.ch/ilivalidator

Integration: https://geo-i.so.ch/ilivalidator

Test: https://geo-t.so.ch/ilivalidator

### Benutzerhandbuch
Benutzerhandbuch zur Bedieung des Webservices: https://github.com/sogis/ilivalidator-web-service/blob/master/docs/user-manual-de.rst

## Konfiguration und Betrieb in der GDI
* **Template Openshift:** https://github.com/sogis/openshift-templates/tree/master/ilivalidator
* **Repo ilivalidator-web-service:** https://github.com/sogis/ilivalidator-web-service


