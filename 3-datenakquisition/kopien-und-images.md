# Kopien und Images

## Einführung

**Digitale Objekte werden oft auf transportablen Medien ans Archiv abgeliefert, beispielsweise auf USB-Sticks, CD, DVD oder auf älteren Medien, für die es kaum noch Lesegeräte gibt.** Um die Daten im Archiv unter Kontrolle zu halten, müssen sie in einem ersten Schritt von diesen transportablen Medien ins Archiv überführt werden. Transportable Medien eignen sich grundsätzlich nicht als Speichersystem für digitale Archivierung, mit Ausnahme der Nutzung solcher Medien für Offline-/Offsite Backupkopien.

**Das Erstellen von Kopien von Datenträgern erscheint zunächst als triviale Aufgabe.** Erstens können aber zahlreiche Schwierigkeiten während dem Kopieren auftreten: für alte Datenträger müssen überhaupt noch Laufwerke vorhanden sein; auf einem alten Ursprungsdatenträger sind nicht mehr alle Blöcke lesbar; Dateinamen enthalten Sonderzeichen, so dass sie am Zielort nicht gespeichert werden können; der Kopiervorgang bricht aus irgendeinem Grund ab und muss wieder aufgenommen werden können. Zweitens ist der Kopiervorgang eine zentrale Etappe in der ganzen Kette der digitalen Archivierung. Wenn hier Fehler auftreten und die Kopiel nicht genau identisch mit dem Ausgangsmaterial sind, dann hat dies Auswirkungen auf sämtliche nachfolgenden Etappen der Archivierung. Der Schaden ist besonders gross, wenn Kopierfehler nicht sofort erkannt werden, sondern erst sehr viel später.

**Grundsätzlich gibt es zwei Möglichkeiten, um den Inhalt eines Speichermediums ins Archiv zu übernehmen.** Je nach Bestand und Preservation Intent wird die eine oder andere Variante verwendet:

* **Dateien kopieren:** Von den Dateien (oder je nachdem nur eine Auswahl) auf dem Speichermedium wird mit einem Kopierprogramm Kopien angefertigt. In einem zusätzlichen Schritt kann überprüft werden, ob die Kopien bitgenau identisch sind.
* **Image erstellen:** Ein forensisches Image ist die bitgenaue Kopie eines Datenträgers. Bei diesem Vorgang bleiben sämtliche Informationen des ursprünglichen Datenträgers erhalten, sofern sie vom Ursprungs-Datenträger extrahiert werden können.

Der Datei-basierte Ansatz kommt zur Anwendung, wenn einzelnen Dateien als Objekte erhalten werden sollen und der technische Kontext des Datenträgers keine archivrelevanten Informationen trägt. Beispielsweise werden Dossiers aus einem GEVER-System mit einem Dateibasierten Ansatz ins Archiv übernommen. Der Image-Ansatz kommt zur Anwendung, wenn ein komplexes digitales Objekt, ein gesamtes technisches System oder eine bestimmte Arbeitsweise archiviert und dokumentiert werden soll.

**Beispielsweise wurden die alten Laptops und Datenträger des Schriftstellers Salman Rushdie mit einem Image-Ansatz gesichert.** Der Autor verwendete zahlreiche farbcodierte "Sticky Notes" zum Anlegen von Notizen, "Sticky Notes" war ein Hilfsprogramm des damaligen Mac-Betriebssystems. Für die Archivierung sollten nicht einzelne isolierte Dateien wegkopiert werden, sondern die umfangreiche Post It-Sammlung als Ganzes erfahrbar gemacht werden. Dank der Erstellung eines Images der kompletten Harddisks von Rushdies Computer können diese im Lesesaal via Emulation den Nutzer\*innen zugänglich gemacht werden. So erfolgt der Zugang nicht auf die einzelnen Dateien, sondern es kann die spezielle Arbeitsweise des Autors erforscht und nachvollzogen werden.

![Laptops und Datenträger von Salman Rushdie (https://scholarblogs.emory.edu/woodruff/rose-library/do-it-yourself-digital-preservation)](<../.gitbook/assets/image (12) (2).png>)

Quelle zur Emulation der Rushdie-Laptops: [https://scholarblogs.emory.edu/woodruff/news/the-digital-archives-program-settles-in-to-marbl](https://scholarblogs.emory.edu/woodruff/news/the-digital-archives-program-settles-in-to-marbl)

## Schreibblocker

**Die zu archivierenden Datenträger dürfen mit dem Kpoiervorgang nicht verändert werden, vor allem nicht, wenn bitgenaue Images erstellt werden.** Wenn transportable Datenträger über einen USB-Port angeschlossen werden, dann schreibt das Betriebssystem Metadaten oder verborgene Dateien (z. B. Thumbnail-Dateien für Bilddateien) auf den Datenträger. Zudem besteht die Gefahr, dass Daten versehentlich verändert oder gelöscht werden.

**Um solche Veränderungen zu verhindern, werden Schreibblocker verwendet.** Das sind Mechanismen, die zwar den Lesezugriff auf Datenträger erlauben, aber das Schreiben verhindern. Solche Schreibblocker gibt es als Software oder als Hardware. Entwickelt wurden sie ursprünglich für die digitale Forensik, wenn im Rahmen von Ermittlungen oder Analysen Datenträger (beispielsweise Mobiltelefone) ausgelesen werden und nachgewiesen werden muss, dass keine Veränderung des Speichers stattgefunden hat. &#x20;

![Schreibblocker zwischen 2.5"-Harddisk und Computer](../.gitbook/assets/image.png)

Hier wird die Arbeitsweise von Schreibblockern demonstriert:

{% embed url="https://www.youtube.com/watch?v=Kmm8iaa76rQ&ab_channel=DFIRScience" %}

## Werkzeuge für Kopien und Images

### Dateien kopieren mit rsync

**rsync (Remote Synchronization) gleicht Dateien und Ordner zwischen einem Quellsystem und einem Zielsystem ab.** Die Synchronisation findet immer von der Quelle zum Ziel statt. Rsync kann alle Daten kopieren oder bei einer älteren Kopien nur die neuen oder geänderten Daten ergänzen. Damit lässt sich mit rsync auch gut für Backups verwenden. Rsync funktioniert sowohl für lokale Kopien wie auch über ein Netzwerk hinweg, beispielsweise bei der Übernahme von Daten aus entfernten Servern.

rsync ist auf dem DPL vorinstalliert.

* Bedienung von rsync: [ ](https://wiki.ubuntuusers.de/rsync/)[https://wiki.ubuntuusers.de/rsync/](https://wiki.ubuntuusers.de/rsync/)
* How To: [https://www.ostc.de/howtos/rsync-HOWTO.html](https://www.ostc.de/howtos/rsync-HOWTO.html)

**Syntax:**&#x20;

```shell
rsync [optionen] quelle ziel
```

### Bitgenaue Images erstellen mit dd

**dd (Disk Dump) dient zum bit-genauen Kopieren von Festplatten, Partitionen oder Dateien.** "Bit-genaues" Kopieren bedeutet, dass der Datenträger Bit-für-Bit bzw. Byte-für-Byte ausgelesen und beschrieben wird, unabhängig von dessen Inhalt und Belegung. dd ignoriert Dateisysteme und funktioniert mit allen blockorientierten Datenträgern, also auch mit Daten-CDs/DVDs.

dd ist auf dem DPL vorinstalliert.

* Bedienung von dd: [https://wiki.ubuntuusers.de/dd/](https://wiki.ubuntuusers.de/dd/)

