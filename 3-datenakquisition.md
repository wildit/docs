---
description: Auskoppeln, Web-Archivierung und Images erstellen
---

# 3 Datenakquisition

## Einführung

**Wie gelangen die Daten ins Archiv?** Die Herausforderung scheint trivial: Für die Archivierung müssen die Daten aus Produktivsystemen ins Archiv übernommen werden. Produktivsysteme können sein: Dateiserver, Datenbanken, Applikationen, Cloudanwendungen, Webseiten, aber auch transportable Speichermedien. Für die nachhaltige Archivierung benötigt das Archiv Kontrolle über den Archivspeicher, die Struktur der Informationsobjekte und die Metadaten. Wenn die Daten zur Archivierung in Produktivsystemen verbleiben, welche über sogenannte "Archivfunktionalitäten" verfügen, dann ist nicht zu erwarten, dass langfristig eine applikationsunabhängige Nutzung der Daten möglich ist.

Die Herausforderung der Datenübernahme ist nur scheinbar trivial. Denn im Alltag der öffentlichen Verwaltung und privaten Unternehmen werden viele Systeme nicht mehr auf lokaler Infrastruktur betrieben, sondern als Dienst aus der Cloud bezogen. Dies nennt man ["Software as a Service"](https://de.wikipedia.org/wiki/Software\_as\_a\_Service) oder  "SaaS". Die Folge davon ist, dass die Daten nicht mehr auf Servern der Organisation liegen, sondern verstreut bei unterschiedlichen Clouddienstleistern. Für die Archivierung müssen sie über unterschiedliche Verfahren und Schnittstellen eingesammelt werden.&#x20;

Nicht nur aus Cloudsytemen, auch von internen Anwendungen, Servern und transportablen Medien müssen Daten ins Archiv übernommen werden. Diesen Vorgang nennt man Datenakquisition:

**Die Datenakquisition ist der Prozess, mit dem Daten aus Systemen innerhalb und ausserhalb der Organisation zur Archivierung übernommen werden.**

Dieses Kapitel behandelt zwei Szenarien von Datenakquisition, die in der Praxis häufig auftreten.

* Beim ersten Szenario geht es um die **Webarchivierung,** also die Übernahme von Webseiten von Behörden, Unternehmen, Verbänden oder sonstiger Organisationen ins Archiv.&#x20;
* Beim zweiten Szenario geht es um die **Datenübernahme von transportablen Medien** (DVD, CD, USB-Stick, Diskette) und die Erstellung von Images (Abbildern) dieser Medien für die Weiterverarbeitung im Archivprozess.

## Webarchivierung

### Grundlagen

Sammelstrategien

Webarchiv Schweiz der Nationalbibliothek

{% embed url="https://www.youtube.com/watch?v=0OijAJ8YXxs&ab_channel=SwissNationalLibrary" %}

### wget

### Webrecorder

## Images von transportablen Medien

### Erstellen eines dateibasierten Images mit rsync

Eine wichtige Aufgabe in jedem digitalen Archiv ist das Anfertigen von Kopien, sie zu kontrollieren und sie zu gegebener Zeit auf neue Systeme zu übertragen. Die **gute Nachricht** ist: Wenn es eine Sache gibt, in der Computertechnologien wirklich gut sind, dann ist es das Kopieren. Die **schlechte Nachricht** ist: Wenn beim Kopieren Fehler auftreten, dann werden die oft erst sehr viel später erkannt und ein Rückgriff auf die Originale ist vielleicht nicht mehr möglich. DIe digitalen Objekte sind dann unwiederruflich verloren. Auch wenn das Kopieren von Daten als triviale Aufgabe erscheint, so setzen wir uns hier bewusst damit auseinander. Wichtig ist der folgende Unterschied:

* **Kopieren (copy) =** Anlegen einer bitgenauen Kopie einer Datei oder eines gesamten Ordners. Die Speichermenge verdoppelt sich beim Kopieren.
* **Verschieben (move) =** umbenennen oder an einen anderen Ort verschieben einer Datei oder eines gesamten Ordners. Die Speichermenge verändert sich beim Verschieben nicht.

Ein wichtiges Programm, um Daten zu kopieren und dabei auch die Integrität der Kopie zu überprüfen ist **rsync.** Rsync ist ein unter Linux sehr häufig genutztes Werkzeug und wird hier in allen Details erklärt:

{% embed url="https://wiki.ubuntuusers.de/rsync/" %}

(Sie müssen diese Anleitung nicht im Detail durchlesen, wir werden sie in den Übungen aber als Nachschlagewerk nutzen)

**rsync** gleicht Dateien und Ordner zwischen einem Quellsystem und einem Zielsystem ab. Die Synchronisation findet immer von der Quelle zum Ziel statt. Rsync kann alle Daten kopieren oder bei einer älteren Kopien nur die neuen oder geänderten Daten ergänzen. Damit lässt sich mit rsync auch gut Backups machen.



**Syntax:**&#x20;

```shell
rsync [optionen] quelle ziel
```

### Erstellen eines bitgenauen Images mit dd

Digitale Objekte werden oft auf transportablen Medien ans Archiv abgeliefert, beispielsweise auf USB-Sticks, CD, DVD oder auf älteren Medien, für die es kaum noch Lesegeräte gibt. Um die Daten im Archiv unter Kontrolle zu halten, müssen sie von diesen transportablen Medien ins Archiv überführt werden. Transportable Medien eignen sich grundsätzlich nicht als Speichersystem für digitale Archivierung, mit Ausnahme der Nutzung solcher Medien für Offline-/Offsite Backupkopien.



Blockbasierte Images&#x20;

Dateibasierte Images
