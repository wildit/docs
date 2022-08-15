# Webarchivierung

## Einführung

**Webarchivierung bezeichnt das Einsammeln und die Nutzbarhaltung von Netzpublikationen und Websites mit dem Ziel, diese oft flüchtigen Ressourcen langfristig zu erhalten.** Webarchivierung wird sowohl durch grosse Organisationen wie das Internet Archive oder Nationalbibliotheken, aber auch durch Kleinstorganisationen und Private betrieben, die sich auf einzelne Websites oder Themen konzentrieren.

### Drei Strategien

**Für die Datenakquisition kommen bei der Webarchivierung grundsätzlich drei Strategien zur Anwendung.** Bei der **Client-seitigen** Archivierung wird die Webseite so gespeichert, wie sie die Bernutzerin im Browser angezeigt bekommt. Bei der **transaktionsbasierte** Archivierung wird der ausgelieferte Datenstrom aufgezeichnet. Bei der **serverseitigen** Archivierung werden die Ressourcen im Content Management-System und auf den Datenbanken archviert, ohne dass sie über einen Webserver ausgeliefert werden.

![Clientseitige Archivierung (Masanès (2006), p. 23)](<../.gitbook/assets/image (14).png>)

Bei der **clientseitigen Archivierung** wird die Webseite so aufgezeichnet, wie sie der Betrachter in seinem Browser sieht. Es werden nur die Dokumente archviert, die auch tatsächlich über den Webserver ausgeliefert werden. Der Webserver kann seine Inhalte von verschiedenen anderen Servern beziehen (Dateiserver, Datenbankserver, Content Management-System), dies wird bei der Archivierung nicht berücksichtigt.&#x20;

![Transaktionsbaiserte Archivierung (Masanès (2006), p. 26)](<../.gitbook/assets/image (2).png>)

Bei der **transaktionsbasierten Archivierung** wird der Datenstrom zwischen Webserver und Benutzer aufgezeichnet, in manchen Fällen auch zwischen Benutzer und Webserver. Diese Vorgehensweise eignet sich besonders gut, um beispielsweise die Interaktion mit einer dynamischen Website zu dokumentieren. Diese Archivstrategie macht nachvollziehbar, wie eine Website benutzt wird. Allerdings werden nur Ressourcen archiviert, die bei der Archivierung auf tatsächlich aufgerufen werden.

![Transaktionsbaiserte Archivierung (Masanès (2006), p. 27)](<../.gitbook/assets/image (17).png>)

Bei der **serverseitigen Archivierung** werden die Ressourcen archiviert, noch bevor sie über den Webserver ausgeliefert werden. Bei deser Archivstrategie werden unterschiedliche Komponenten wie Datenbank, Dateiserver, Programmcode, HTML-Quellcode etc. einzeln archiviert. Der Vorteil dieser Methode ist, dass auch Ressourcen archiviert werden, die nicht verlinkt sind und nie über den Webserver ausgeliefert werden. Allerdings stellt die Wiederherstellung einer funktionierenden Kopie der Website eine grosse Herausforderung dar. Ein Vorgehen zur Nutzung der archivierten Website ist die Wiederherstellung der verschiedenen Server und der Netzwerktopologie in einer emulierte Serverumgebung.

## Webarchiv Schweiz

**In der Schweiz betreibt die Nationalbibliothek ein Webarchiv.** Die Nationalbibliothek hat den gesetzlichen Auftrag, Informationen über die Schweiz zu zu sammeln, aufzubewahren und dieses Wissen dauerhaft bereitzustellen. Websites sind ein Teil davon. Allerdings wird nicht die gesamte .ch-Domäne archiviert, sondern nur **ausgesuchte Websites.** Die Kantonsbibliotheken und einige Spezialbibliotheken treffen die Auswahl und melden sie der Nationalbibliothek. Diese führt das Harvesting und die Erschliessung durch, beides geschieht weitgehend automatisiert.

Das Webarchiv Schweiz ist über e-Helvetica Access, das **Zugriffssystem** für die digitalen Sammlungen an der Schweizerischen Nationalbibliothek, abfragbar und zugänglich. Der Einstieg in das Webarchiv Schweiz erfolgt über eine Collage:

{% embed url="https://www.e-helvetica.nb.admin.ch/collage/" %}

Allerdings ist die **Konsultation** der einzelnen Websites aus Copyright-Gründen nur an speziellen Infostationen vor Ort in der Nationalbibliothek oder in einer Kantonsbibliothek möglich.

{% embed url="https://www.youtube.com/watch?v=0OijAJ8YXxs&ab_channel=SwissNationalLibrary" %}

## Internet Archive

Der Zugriff auf die Websites erfolgt über die Wayback Machine. Wenn eine Website archiviert wurde, dann kann nachvollzogen werden, wie sie sich über die Jahre entwickelt hat.

## Werkzeuge für die Webarchivierung

Für das Harvesten (Einsammeln) von Webressourcen stehen Werkzeuge zur Verfügung, die diese Aufgabe mit unterschiedlichen Ansätzen erfüllen. Je nach Aufbau und technischer Umsetzung einer Website und auch je nach Sammlungsziel kommen unterschiedliche Werkzeuge zum Einsatz. Für unsere Übungen in LEZY2 verwenden wir zwei Werkzeuge, die unterschiedliche Vorgehensweisen repräsentieren: Wget ist ein Werkzeug zur clientseitigen Archivierung von Websites, Webrecorder verfolgt einen transaktionsbasierten Ansatz.

### wget

**Wget ist ein Werkzeug zum Herunterladen von Dateien von FTP- und Webservern, das sich sehr gut zur clientseitigen Archivierung gesamter Websites eignet.** Wget wird auf der Kommandozeile bedient. Das Werkzeug startet über einen Ausgangslink und lädt die verknüpften weiteren Seiten herunter. Das Resultat eines Crawls wird entweder in eine Ordnerstruktur geschrieben oder es kann auch eine WARC-Datei erstellt werden. Wenn ein Crawl aus irgendeinem Grund unterbrochen wird, dann kann er später an der abgebrochenen Stelle wieder aufgenommen werden.

Wget ist auf dem DPL vorinstalliert.

* Bedienung von wget: [https://wiki.ubuntuusers.de/wget/](https://wiki.ubuntuusers.de/wget/)&#x20;
* wget mit WARC-Output: [https://wiki.archiveteam.org/index.php/Wget\_with\_WARC\_output](https://wiki.archiveteam.org/index.php/Wget\_with\_WARC\_output)

### Webrecorder

**Webrecorder ist ein Werkzeug für transaktionsbasierte Archivierung von Websites.** Das Werkzeug eignet sich besonders für Webseiten, die dynamische Elemente beinhalten, die direkt auf den Benutzer zugeschnitten werden. Webrecorder wird eingesetzt, wenn die statischen Crawler wie Heritrix oder wget nur unbefriedigende Resultate liefern. Oder es wird komplementär zu diesen eingesetzt, um die Interaktion wie Suche, Eingaben, Abrufen von Tönen und Videos nachvollziehbar zu machen. Webrecorder erstellt keine kompletten Crawls von Websites, sondern dokumentiert das individuelle Benutzererlebnis beim Browsen auf einer Website.&#x20;

Webrecorder ist ein Browser-Plugin im Chrome- oder Chromium-Browser. Als Resultat werden WARC-Dateien erzielt. Das Plugin kann über den folgenden Link installiert werden: [https://chrome.google.com/webstore/detail/webrecorder-archivewebpag/fpeoodllldobpkbkabpblcfaogecpndd](https://chrome.google.com/webstore/detail/webrecorder-archivewebpag/fpeoodllldobpkbkabpblcfaogecpndd)

Zur Archivierung wird ein neues Archiv angelegt: "Create New Archive"

![](<../.gitbook/assets/image (16).png>)

{% embed url="https://jitp.commons.gc.cuny.edu/how-i-learned-how-to-stop-worrying-and-pickle-websites-the-art-of-fermenting-the-web-with-archive-it-and-webrecorder/" %}

![](<../.gitbook/assets/image (12).png>)



Die Aufzeichnung wird über den "Start"-Button ausgelöst. Nun klickt man sich als Benutzer durch die Website und Webrecorder zeichnet jeden Schritt auf. Es können auch interaktive Elemente wie die Suche benutzt werden:

![](<../.gitbook/assets/image (18).png>)

Der Crawl wird über den "Stop"-Button angehalten. Über "View Recorded Page" kann der Crawl zurückgespielt und die ganze Benutzerreise angezeigt werden:

![](<../.gitbook/assets/image (8).png>)

Zur offsite-Speicherung kann der Crawl dann auch als WARC-paket heruntergeladen werden:

![](<../.gitbook/assets/image (10).png>)



Quellen

* Nationalbibliothek, Grundlagenpapier Webarchiv Schweiz (2022): [https://www.nb.admin.ch/dam/snl/de/dokumente/e-helvetica/normen\_und\_regelwerke/webarchiv-schweiz-grundlagen.pdf.download.pdf/webarchiv-schweiz-grundlagen.pdf](https://www.nb.admin.ch/dam/snl/de/dokumente/e-helvetica/normen\_und\_regelwerke/webarchiv-schweiz-grundlagen.pdf.download.pdf/webarchiv-schweiz-grundlagen.pdf)
* Masanés, Julien. (2006). _Web Archiving_. Springer-Verlag Berlin Heidelberg. [https://doi.org/10.1007/978-3-540-46332-0](https://doi.org/10.1007/978-3-540-46332-0)
