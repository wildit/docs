# Installation DPL

## Einleitung

Dieses Kapitel beschreibt die Installation des DPL (Digital Preservation Lab). Das DPL ist eine virtuelle Maschine (VM) mit allen Werkzeugen, die wir für LEZY2 benötigen.&#x20;

Die VM wird mit Hilfe eines Skripts automatisch installiert. Sie können sie jederzeit wieder löschen und neu aufsetzen lassen. Scheuen Sie sich also nicht, Dinge auszuprobieren. &#x20;

## Vorgehen

### Virtualbox installieren

Gehen Sie auf folgende Seite: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)&#x20;

Laden Sie sowohl das "Platform Package" für Ihr Betriebssystem wie auf das "Extension Pack" herunter.

Starten Sie den Installer und klicken Sie auf "Weiter", bis die Installation beginnt:

![](<.gitbook/assets/image (4) (1) (1).png>)

Nach der Installation starten Sie Virtualbox:

![](<.gitbook/assets/image (2) (1).png>)

Gehen Sie auf Datei --> Einstellungen und öffnen Sie den Reiter "Zusatzpakete":

![](<.gitbook/assets/image (3) (2).png>)

KIicken Sie rechts auf das "+"-Zeichen und wählen Sie die Extension-Datei aus, die Sie ebenfalls heruntergeladen haben. Das Extension Pack wird installiert:

![](<.gitbook/assets/image (3) (1) (1).png>)

Virtualbox ist nun bereit.

### Vagrant installieren

Gehen Sie auf folgende Seite: [https://www.vagrantup.com/downloads](https://www.vagrantup.com/downloads)

Laden Sie die aktuelle "Amd64"-Version herunter

Starten Sie den Installer, klicken Sie auf "Weiter", bis die Installation beginnt:

![](<.gitbook/assets/image (5).png>)

Die Installation dauert einige Minuten, danach muss der Computer neu gestartet werden.

### DPL installieren

Gehen Sie auf folgende Seite: [https://github.com/wildit/dpl-provision](https://github.com/wildit/dpl-provision)

Laden Sie das Git-Repository als ZIP-Datei herunter "Code" --> "Download ZIP"

![](<.gitbook/assets/image (6) (1).png>)

Entpacken Sie den ZIP-Container: Rechtsklick, "Alles entpacken" auswählen;

![](<.gitbook/assets/image (8) (1) (1).png>)

Legen Sie in Ihrem Home-Directory einen neuen Ordner "DPL" an

Kopieren Sie die Dateien "Vagrantfile" und "dpl\_provision.sh" in den Ordner "DPL".

Im Ordner "DPL": Rechtsklick und "In Terminal öffnen"

![](<.gitbook/assets/image (4) (1).png>)

Darauf öffnet sich die Windows Power Shell.

Tippen Sie den Befehl "vagrant up" ein:

![](<.gitbook/assets/image (2) (2).png>)

Nun wird die DPL-virtuelle Maschine aufgesetzt. In einem ersten Schritt wird eine Basis-Ubuntu-Maschine installiert. In einem zweiten Schritt werden per Skript alle Werkzeuge installiert.

### DPL starten und einloggen

Sie können die DPL-VM wahlweise mit "vagrant up" oder über die grafische Oberfläche von Virtualbox starten.

User = vagrant

Passwort = vagrant

![](<.gitbook/assets/image (1) (2).png>)

