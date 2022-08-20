# Formatvalidierung

**Die Formatvalidierung überprüft, ob eine Datei der Spezifikation ihres Formats entspricht.** Es geht darum die syntaktische Richtigkeit zu prüfen (eine inhaltliche Überprüfung findet nicht statt). Grundsätzlich muss jede einzelne der in der Formatspezifikation verlangte Charakteristik überprüft werden. Jedoch sind viele Formatspezifikationen so umfangreich, dass sich die Validierung oft auf ein bestimmtes Subset von Eigenschaften beschränkt.

Nur wenn alle Eigenschaften (oder das vorbestimmte Subset) erfüllt sind, ist die Datei valide. Wenn für ein Format kein Validator existiert, ist einzig eine näherungsweise Validierung möglich durch das Öffnen der Dateien in einem Viewer. Da Viewer in der Regel aber eine gewisse Fehlertoleranz haben, gibt allein die Tatsache, dass eine Datei ohne Fehlermeldung angezeigt werden kann, noch keine Gewissheit über ihre Validität.

### Einführung in die Formatvalidierung

Schauen Sie sich das folgende Webinar von nestor zum Thema Formatvalidierung an. Für die Validierung wird JHOVE verwendet, diese Software wird weiter unten noch detaillierter erläutert. Das Webinar startet mit theoretischen Überlegungen zur Formatvalidierung und zeigt dann praktische Beispiele aus der Archivpraxis.

{% embed url="https://www.youtube.com/watch?v=zCpq0sQPjmY&ab_channel=nestor-digitaleLangzeitarchivierung" %}

Die Slides der beiden Präsentationen können Sie unter folgendem Link herunterladen:

* [Alfred Wutschka. Dateivalidierung im Berufsalltag (PDF)](https://www.langzeitarchivierung.de/Webs/nestor/SharedDocs/Downloads/DE/praesentationen/2021DateivalidierungJHOVEWutschka.pdf?\_\_blob=publicationFile\&v=1)
* [Yvonne Tunnat: JHOVE in der Praxis (PDF)](https://www.langzeitarchivierung.de/Webs/nestor/SharedDocs/Downloads/DE/praesentationen/2021DateivalidierungJHOVETunnat.pdf?\_\_blob=publicationFile\&v=1)

Quelle: [https://www.langzeitarchivierung.de/Webs/nestor/DE/Veranstaltungen\_und\_Termine/2021DateivalidierungJHOVE.html](https://www.langzeitarchivierung.de/Webs/nestor/DE/Veranstaltungen\_und\_Termine/2021DateivalidierungJHOVE.html)

### JHOVE

[JHOVE](https://jhove.openpreservation.org/) ist ein weit verbreitetes Validierungswerkzeug, das in fast allen digitalen Archiven verwendet wird. JHOVE vereinigt [insgesamt zwölf Module](https://jhove.openpreservation.org/modules/) zur Validierung unterschiedlicher Dateiformatfamilien in einem einzigen Werkzeug, damit ist es sehr mächtig. Die wichtigsten Module dienen zur Validierung folgender Dateifamilien mit diversen Unterformaten:

* JPEG
* JPEG2000
* PDF
* TIFF
* WAVE

JHOVE ist in verschiedenen Versionen verfügbar, als Kommandozeilenwerzeug für die Einbindung in automatisierte Prozesse oder mit einer graphischen Oberfläche. Wir verwenden für die Übungen die Version mit graphischer Oberfläche. Im Terminal starten Sie JHOVE mit dem Befehl "jhove-gui":

`jhove-gui`

So öffnet sich die graphische Oberfläche und Sie können über "File" --> "Open file" eine Datei zur Validierung auswählen. Eine weiterführende Anleitung zum Gebraucht von JHOVE ist in der oben angegebenen Präsentation von Yvonne Tunnat enthalten.

