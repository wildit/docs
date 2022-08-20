# Formaterkennung

## **Einführung**

**Die Formaterkennung identifiziert das Format und die Formatversion einer Datei.** Sie stützt sich dabei auf besonders charakteristische Eigenschaften. In der Regel sind dies bestimmte Bytesequenzen innerhalb der Datei. Die verlässliche Formaterkennung ist im Rahmen der digitalen Archivierung eine wichtige Grundlage für die Erhaltungsplanung (Preservation Planning). Denn nur wenn bekannt ist, welche Formate im Archiv vorhanden sind, können auch Massnahmen zur Nutzbarhaltung ergriffen werden.

Der folgende Präsentation von Micky Lindlar (TIB Hannover) liefert Ihnen die Grundlagen zum Thema Formaterkennung:

{% embed url="https://www.youtube.com/watch?v=DlK_bCuz4OA&ab_channel=nestor-digitaleLangzeitarchivierung" %}

Inhalt:&#x20;

* WAS ist Dateiformatidentifizierung?
* WARUM überhaupt Dateiformatidentifizierung?
* WIE geht Dateiformatidentifizierung?&#x20;
* WOMIT kann ich Dateiformatidentifizierung durchführen?&#x20;
* Alles klar! Kann überhaupt noch was schieflaufens?

Die Slides der Präsentation können Sie unter folgendem Link herunterladen:

* [Micky Lindlar (2021). Dateiformatidentifizierung: Was, warum, wie, womit... (PDF)](https://www.langzeitarchivierung.de/Webs/nestor/SharedDocs/Downloads/DE/praesentationen/2021praktikertagLindlar.pdf?\_\_blob=publicationFile\&v=1)

## Magic Numbers



## Werkzeuge für die Formaterkennung

### Identifikation mit file

**file ist ein Kommandozeilenprogramm in Linux, welches das Format einer Datei erkennt.** Dies geschieht nicht anhand der Dateiendung, sondern file untersucht einen Teil des Inhalts der Datei, um den Dateityp zu bestimmen. File ist ein bereits ein sehr altes Programm, die erste UNIX-Version stammt aus dem Jahr 1973. Das Programm eignet sich sehr gut

file ist auf dem DPL vorinstalliert.

* Bedienung von file: [https://wiki.ubuntuusers.de/file/](https://wiki.ubuntuusers.de/file/)
* Tutorial mit Beispielen: [https://www.howtoforge.com/linux-file-command/](https://www.howtoforge.com/linux-file-command/)

Identifikation Dateiformat:

```bash
file test.docx
```

Resultat:

```
test.docx: Microsoft Word 2007+
```

In diesem Abschnitt befassen wir uns ausschliesslich mit der Formatidentifikation. file liefert z. B. bei jpg oder TIFF-Dateien auch zusätzliche charakterisierende Metadaten mit

&#x20;

MIME-Type anzeigen:

```bash
file -i test.jpg
```

Resultat:

```
test.jpg: image/jpeg; charset=binary
```

### Siegfried





Quelle:

[https://www.landesarchiv-bw.de/sixcms/media.php/120/59122/Roethlisberger-Jourdan\_Formaterkennung\_und\_Formativalidierung.pdf](https://www.landesarchiv-bw.de/sixcms/media.php/120/59122/Roethlisberger-Jourdan\_Formaterkennung\_und\_Formativalidierung.pdf)
