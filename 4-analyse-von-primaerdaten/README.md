# 4 Analyse von Primärdaten

## Einführung

**In diesem Bereich analysieren wir Primärdaten und befassen uns mit technischen und administrativen Metadaten, welche eine Grundlage für die Ehaltungsplanung (Preservation Planning) und die langfristige Nutzbarhaltung von Dateien bilden.**

Was ist überhaupt ein Dateiformat und warum ist die Wahl von archivtauglichen Dateiformaten so wichtig für die langfristige Nutzbarhaltung? Bereits in LEZY1 haben Sie einige Grundlagen dazu gelernt. Der folgende Film fasst aus der Sicht des Archivs die wichtigsten Punkte nochmals zusammen.

{% embed url="https://www.youtube.com/watch?v=eJfnuSo_lCQ&ab_channel=CouncilofStateArchivists" %}

## PREMIS Metadatenstandard

### Einführung

**PREMIS ist der wichtigste Metadatenstandard für die Speicherung technischer und administrativer Metadaten für die digitale Archivierung.** PREMIS nimmt die Informationen auf, die bei der Analyse von Dateien entstehen, also bei deren Identifikation, Validierung und Charakterisierung. PREMIS steht als Abkürzung für "Preservation Metadata Implementation Standard" und wird durch ein Editorial Committee gepflegt, das sich zusammensetzt aus ExpertInnen aus Archiven/Bibliotheken und der Softwareentwicklung.

PREMIS will bewusst nicht ein allumfassender Standard für alle möglichen technische Metadaten sein, sondern bildet die Teilmenge von Informationen ab, die für die langfristige Erhaltung  wichtig ist. Der Standard geht nicht in allen Bereichen detailliert in die Tiefe, dazu gibt es dann in jedem einzelnen Bereich spezifische weiterführende Metadatenstandards. PREMIS deckt die folgenden bereiche ab:

![PREMIS als eine Teilmenge der gesamten Langzeitarchivierungsmetadaten (https://www.loc.gov/standards/premis/understandingPREMIS\_german\_2021.pdf)](<../.gitbook/assets/image (12).png>)

### Entitäten

**PREMIS besteht aus vier Bereichen, sogenannten Entitäten.** Das Datenmodell sieht im Überblick wie folgt aus:

![Datenmodell von PREMIS (https://www.loc.gov/standards/premis/understandingPREMIS\_german\_2021.pdf)](<../.gitbook/assets/image (6).png>)

#### **Entität Objekt (Object)**

**Objekte sind das, was im digitalen Archiv tatsächlich gespeichert wird.** Im Modell von PREMIS gibt es mehrere Typen, respektive Abstraktionesbenen von Objekten:

* **Intellektuelle Entität:** Dient der Beschreibung und Identifizierung des Objekts als logische Einheit. Beispiele: Ein Computerspiel, eine Website, ein digitalisiertes Buch.&#x20;
* **Repräsentation:** Ist die technische Abbildung der intellektuellen Entität. Beispiele: Eine Website wird einmal durch eine Sammlung von html-Dateien und einmal durch einen WARC-Container abgebildet. Das sind zwei Repräsentationen der gleichen intellektuellen Einheit
* **Datei:** Repräsentationen setzen sich aus einer oder mehreren Dateien zusammen.
* **Bitstream:** Bitstream-Objekte sind Teilmengen von Dateien.

![Objektbeziehungen in PREMIS (https://www.loc.gov/standards/premis/understandingPREMIS\_german\_2021.pdf)](<../.gitbook/assets/image (3).png>)



#### **Entität Ereignis (Event)**

**In den Ereignissen werden die bestandeserhaltenden Massnahmen im Archiv dokumentiert.** Hier gehören Informationen wie:

* Typ der Massnahme (Erstellung, Virenprüfung, Checksummenprüfung, Formatidentifikation, Migration etc.)
* Detaillierte Beschreibung der Massnahme
* Ergebnis der Massnahme (erfolgreich/nicht erfolgreich)
* Verweis auf das Objekt (Repräsentation, Datei), das von der Massnahme betroffen ist
* Verweis auf den Akteur, der an der Massnahme beteiligt ist.
* Datum und Zeitpunkt (Timestamp)

#### **Entität Akteur (Agent)**

**Die Akteure sind Handelnde in Bezug auf die Objekte.** Sie spielen eine Rolle bei den Ereignissen (sind verantwortlich dafür, führen sie durch etc.) und haben einen Bezug zu den rechtlichen Grundlagen.

#### **Entität Rechte (Rights Statement)**

**In der Entität Rechte werden Informationen gespeichert zu rechtlichen Grundlagen und Erlaubnissen in Bezug auf die Objekte.** Die Informationen geben Auskunft auf die Frage: Was darf ein Akteur mit einem bestimmten Objekt im digitalen Archiv tun?

* Informationen über den urheberrechtlichen Status, Lizenz- oder gesetzliche Bestimmungen, sofern sie Anwendung finden,
* die Handlungen, die aufgrund der rechtlichen Angaben erlaubt sind
* Verweis auf die Grundlagen für die rechtliche Bestimmung (Gesetzestext, Verordnung, Lizenzbestimmung, Vertrag etc.)
* Zeitraum der Einräumung oder Beschränkung eines Rechts (z. B. Sperrfristen im Archiv)
* Verweis auf das Objekt, das von den rechtlichen Bestimmungen betroffen ist
* Verweis auf den Akteur, der eine Rolle in Bezug auf die rechtlichen Bestimmungen spielt.

### PREMIS Beispiel in XML

**PREMIS wird oft in XML dargestellt, vor allem wenn Objekte ausgetauscht werden.** Für PREMIS existiert aber auch eine Ontologie. Das folgende Beispiel zeigt in einer XML-Umetzung, welche Informationen in einem Archiv für eine Datei gespeichert werden. Diese Datei wurde ans Archiv abgeliefert, überprüft und ingestiert.

Im Folgenden sehen Sie die Informationen zu einer Datei, in der Sprache von PREMIS ein "Object" vom Typ "File".

* objectIdentifier: Identifier des Objekts
* objectCharacteristics, composition Level = 0 bedeutet, dass es sich um eine komplette, eigenständige Datei handelt.
* fxity: Die Checksumme im Format SHA-512
* formatDesignation: Dateiformat ausgeschrieben
* formatRegistry: Eindeutiger Identifier für das Format und die Format-Verision in der [PRONOM-Registry.](https://www.nationalarchives.gov.uk/PRONOM/)
* orignalName: Originaler Dateiname zum Zeitpunkt der Übernahme ins Archiv
* relationship: Es handelt sich hier um eine migrierte Datei und verwiesen wird auf die Originaldatei, die ebenfalls im Archiv gespeichert ist.&#x20;

```xml
<PREMIS:object xsi:type="PREMIS:file">
    <PREMIS:objectIdentifier>
        <PREMIS:objectIdentifierType>Docuteam</PREMIS:objectIdentifierType>
        <PREMIS:objectIdentifierValue>_20220628161542804</PREMIS:objectIdentifierValue>
    </PREMIS:objectIdentifier>
    <PREMIS:objectCharacteristics>
        <PREMIS:compositionLevel>0</PREMIS:compositionLevel>
        <PREMIS:fixity>
            <PREMIS:messageDigestAlgorithm>SHA-512</PREMIS:messageDigestAlgorithm>
            <PREMIS:messageDigest>02abbd930169232583ac4e7231b60681c96cc6e388ebd2b2557d995d8bff12a0dcb7e459701b70fb3de00a98d212110bfe7ad7054c5a6942b093bf720701c14d</PREMIS:messageDigest>
        </PREMIS:fixity>
        <PREMIS:size>2765158</PREMIS:size>
        <PREMIS:format>
            <PREMIS:formatDesignation>
                <PREMIS:formatName>Tagged Image File Format</PREMIS:formatName>
            </PREMIS:formatDesignation>
            <PREMIS:formatRegistry>
                <PREMIS:formatRegistryName>PRONOM</PREMIS:formatRegistryName>
                <PREMIS:formatRegistryKey>fmt/353</PREMIS:formatRegistryKey>
            </PREMIS:formatRegistry>
        </PREMIS:format>
    </PREMIS:objectCharacteristics>
    <PREMIS:originalName xlink:type="simple">shuttle.jpg</PREMIS:originalName>
    <PREMIS:relationship>
        <PREMIS:relationshipType>derivation</PREMIS:relationshipType>
        <PREMIS:relationshipSubType>derived from</PREMIS:relationshipSubType>
        <PREMIS:relatedObjectIdentification>
            <PREMIS:relatedObjectIdentifierType>Docuteam</PREMIS:relatedObjectIdentifierType>
            <PREMIS:relatedObjectIdentifierValue>_20220628152724383</PREMIS:relatedObjectIdentifierValue>
        </PREMIS:relatedObjectIdentification>
        <PREMIS:relatedEventIdentification>
            <PREMIS:relatedEventIdentifierType>Docuteam</PREMIS:relatedEventIdentifierType>
            <PREMIS:relatedEventIdentifierValue>_20220628161542866</PREMIS:relatedEventIdentifierValue>
        </PREMIS:relatedEventIdentification>
    </PREMIS:relationship>
</PREMIS:object>

```

Ein Ereignis (Event), das die Erstellung einer Datei im Archiv dokumentiert, umfasst folgende Informationen:

* eventIdentifier: Identifier des Events
* eventType: Typ der Massnahme (Creation, also Erstellung)
* eventDateTime: Zeitstempel des Events
* eventDetail: detaillierte Information, hier Verweis auf den Benutzer auf dem Server
* eventOutcome: Die Massnahme wurde erfolgreich durchgeführt
* linkingObject: Verweis auf das betroffene Objekt

```xml
<PREMIS:event>
    <PREMIS:eventIdentifier>
        <PREMIS:eventIdentifierType>Docuteam</PREMIS:eventIdentifierType>
        <PREMIS:eventIdentifierValue>_20220628161542835</PREMIS:eventIdentifierValue>
    </PREMIS:eventIdentifier>
    <PREMIS:eventType>Creation</PREMIS:eventType>
    <PREMIS:eventDateTime>2022-06-28T16:15:42</PREMIS:eventDateTime>
    <PREMIS:eventDetail>Performed by: 'VIRTSRVSII71$'</PREMIS:eventDetail>
    <PREMIS:eventOutcomeInformation>
        <PREMIS:eventOutcome>Success</PREMIS:eventOutcome>
    </PREMIS:eventOutcomeInformation>
    <PREMIS:linkingObjectIdentifier xlink:type="simple">
        <PREMIS:linkingObjectIdentifierType>Docuteam</PREMIS:linkingObjectIdentifierType>
        <PREMIS:linkingObjectIdentifierValue>_20220628161542804</PREMIS:linkingObjectIdentifierValue>
    </PREMIS:linkingObjectIdentifier>
</PREMIS:event>
```

