# 3 Auskoppeln, Web-Archivierung und Images

## Lernziele

* **Sie verfügen über die Daten, die Sie für Ihre Fallstudie benötigen.**
* Übernahmen bilden aus Web- und Cloud-basierten Systemen
* Images erstellen von mobilen Datenträgern

## Webarchivierung mit wget und Webrecorder

Webrecorder

wget

## Kopieren von Dateien mit rsnyc

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



Teracopy

dsf

{% embed url="https://www.dpconline.org/handbook/tool-demos/teracopy-demo" %}

## Anlegen von Images mit dd

Digitale Objekte werden oft auf transportablen Medien ans Archiv abgeliefert, beispielsweise auf USB-Sticks, CD, DVD oder auf älteren Medien, für die es kaum noch Lesegeräte gibt. Um die Daten im Archiv unter Kontrolle zu halten, müssen sie von diesen transportablen Medien ins Archiv überführt werden. Transportable Medien eignen sich grundsätzlich nicht als Speichersystem für digitale Archivierung, mit Ausnahme der Nutzung solcher Medien für Offline-/Offsite Backupkopien.



Blockbasierte Images&#x20;

Dateibasierte Images
