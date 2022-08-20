# Charakterisierung

## Einführung

**Bei der Dateicharakterisierung werden Informationen zum Format und zu den Eigenschaften einer Datei ermittelt.** Diese Metadaten geben Auskunft über den Charakter und die Qualität einer Datei und dienen bei der Archivierung Grundlage für die Qualitätsprüfung beim Ingest, für das Preservation Planning (Erhaltungsplanung) und schliesslich für die Durchführung von Preservation Actions (bestandeserhaltende Massnahmen). Bei einem Grossteil der Metadaten handelt es sich um technisch/administrative Information, zum Teil fliessen sie aber auch in die inhaltliche Erschliessung ein.

Folgende typische Charaktereigenschaften können bei praktisch allen Dateitypen ermittelt werden:

* Dateiname (wird als Metadatum festgehalten, weil eine Änderung des Dateinamens keine Auswirkung auf die Checksumme hat).
* Dateipfad
* Erzeugungsdatum, Änderungsdaten
* Benutzerrechte (wer hat in welcher Rolle welche Rechte)
* Dateiformat, Formatversion, MIME-Type
* Dateigrösse
* Erzeugende Software
* Copyright, andere Rechte
* Art der Kompression (falls es sich um eine komprimierte Datei handelt)

Mit den im Folgenden angegeben Werkzeugen können grosse Mengen von technischen Metadaten ermittelt werden. Ziel für die Langzeitarchivierung ist es jedoch nicht, möglich viele Metadaten zu ermitteln, sondern es sollen genau die Metadaten gespeichert werden, die Rückschlüsse auf die Qualität und eine mögliche Obsoleszenz der Dateiformate geben. **Mit anderen Worten: Archive speichern soviel wie nötig und nicht soviel wie möglich technische Metadaten!**

## PDF

## Rasterbild

TIFF



### exiftool

**Exiftool ist ein Werkzeug zum Lesen und Schreiben der Metainformationen von Bild-, aber auch Audio- und Video-Dateien.** Es ist ein umfangreiches und zu empfehlende Werkzeug, wenn es um die Änderung von Metadaten der Formate Exif, IPTC/IIM und XMP in digitalen Bildern geht.

exiftool ist auf dem DPL vorinstalliert.

* Bedienung von exiftool: [ ](https://wiki.ubuntuusers.de/rsync/)[https://wiki.ubuntuusers.de/ExifTool/](https://wiki.ubuntuusers.de/ExifTool/)

Aus folgendem Bild sollen Metadaten ausgelesen werden:

![](<../.gitbook/assets/image (17).png>)

Befehl:

```bash
exiftool 067.jpg
```

Resultat:

```
ExifTool Version Number         : 12.40
File Name                       : 067.jpg
Directory                       : /home/vagrant
File Size                       : 675 KiB
File Modification Date/Time     : 2022:08:10 17:51:13+00:00
File Access Date/Time           : 2022:08:19 09:52:59+00:00
File Inode Change Date/Time     : 2022:08:19 09:52:59+00:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 300
Y Resolution                    : 300
Image Width                     : 2389
Image Height                    : 1703
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 1
Image Size                      : 2389x1703
Megapixels                      : 4.1
```



## Video

Video ist eine besonders anspruchsvolle Formatfamilie. Eine Videodatei setzt sich zusammen aus:

* dem Container
* dem Codec

Video ist in den meisten Fällen komprimiert. Die Kompression kann entweder einzelne Bilder (= Frames) betreffen, dann spricht man von Intraframe-Kompression. Oder sie kann über mehrere Bilder hinweg stattfinden, dann spricht man von Interframe-Kompression. Folgendes Video erklärt, wie Videodateien aufgebaut sind:&#x20;

{% embed url="https://www.youtube.com/watch?v=-4NXxY4maYc&ab_channel=ExplainingComputers" %}

FFV1, unkomprimiert DPX

MP4, H.264



Quelle:

[http://nestor.sub.uni-goettingen.de/handbuch/artikel/nestor\_handbuch\_artikel\_350.pdf](http://nestor.sub.uni-goettingen.de/handbuch/artikel/nestor\_handbuch\_artikel\_350.pdf)
