# Charakterisierung

## Einführung

Bei der Dateicharakterisierung werden möglichst viele Details zum Format und den Eigenschaften einer Datei ermittelt. Diese Metadaten geben Auskunft über den Charakter und die Qualität einer Datei un dienen auch als Grundlage für die&#x20;

Je nach Dateityp können folgende Charaktereigenschaften ermittelt werden (Auswahl):

* Dateiformat, Formatversion
* Kompressionsalgorithmen
* Auflösung
* Farbraum
* Eingebettete Schrifttypen
* Ersteller-Applikation

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

FFV1, unkomprimiert DPX

MP4, H.264



Quelle:

[http://nestor.sub.uni-goettingen.de/handbuch/artikel/nestor\_handbuch\_artikel\_350.pdf](http://nestor.sub.uni-goettingen.de/handbuch/artikel/nestor\_handbuch\_artikel\_350.pdf)
