# Einführung in die Welt der Datenbanken
Stell dir vor, du baust das nächste Instagram oder Netflix. Wo speicherst du all die Benutzerprofile, Passwörter, Bilder und Likes? Wenn du sie einfach in einer Textdatei oder Excel-Tabelle speicherst, wird das System extrem langsam und fehleranfällig, sobald Millionen von Nutzern gleichzeitig darauf zugreifen.
Genau hier kommen Datenbanksysteme ins Spiel. Sie speichern Daten sicher, strukturiert und erlauben es, rasend schnell nach Informationen zu suchen.

### Welche Arten von Datenbanken gibt es?
Im Laufe der Zeit haben sich verschiedene Modelle entwickelt, je nachdem, welche Art von Daten gespeichert werden soll, diese kann man grob in 3 Arten zusammenfassen:

* Relationale Datenbanken:<br> 
Das ist das bekannteste und am weitesten verbreitete Modell 6. Die Daten werden hier, ähnlich wie in Excel, in Tabellen (sogenannten Relationen) mit Zeilen und Spalten gespeichert. Sie sind perfekt für strukturierte Daten (z. B. Kunden, Bestellungen).<br> Beispiele: MySQL, PostgreSQL, Oracle .
![Hierarchische Datenbanken](./images/Einfuehrung_RElation.png)<br>

* NoSQL Datenbanken:<br>

    1. Dokumentenorientierte Datenbanken (NoSQL):<br> 
Hier werden Daten nicht in starren Tabellen gespeichert, sondern als flexible Text-Dokumente (oft im JSON-Format). Das ist super für Daten, die nicht immer gleich aufgebaut sind. Beispiel: MongoDB.

    1. Graphen-Datenbanken:<br> 
Diese speichern Daten als Netzwerkknoten und deren Verbindungen. Sie sind ideal für soziale Netzwerke, um Fragen zu beantworten wie: "Wer folgt wem?" (z.B. bei Twitter oder Instagram). Beispiel:  Neo4J.

    1. Spaltenorientierte Datenbanken:<br> 
Sie speichern Daten nicht zeilen-, sondern spaltenweise. Das macht sie extrem schnell, wenn man riesige Datenmengen für Statistiken auswerten will. Beispiele: Scylla, HBase und Kassandra

    1. Key-Value Datenbanken:<br>
Dieser DB-Typ speichert und liefert nur schnelles und unkompliziertes Wissen über Schlüssel-Wert-Paare. Dies ist eine einfache und unkomplizierte Möglichkeit, die Daten zu speichern und darauf zuzugreifen. Beispiele sind Amazon DynamoDB mit einem Redis.

* NewSQL Datenbanken: TODO

* Hierarchische Datenbanken:<br>
Wie der Name schon sagt, ähnelt eine hierarchische Datenbank sehr einem Stammbaum. Dieser in den 1960er Jahren entwickelte Typ strukturiert Daten mithilfe einer Eltern-Kind-Beziehung. Das bedeutet, dass jeder übergeordnete Datensatz einen oder mehrere untergeordnete Datensätze hat, aber jeder untergeordnete Datensatz nur mit einem übergeordneten Datensatz verknüpft ist.

    ![Hierarchische Datenbanken](./images/Einfuerhrung_hierarchie.png)<br>
    Hieratchische Datenbanken

    Beispiele: Windows-Registrierung, IBM Information Management System (IMS), Navigationsdateien, Sitemaps, XML, XAML usw.

* Objektorientierte Datenbanken<br>
In einer objektorientierten Datenbank speichert das System Informationen objektähnlich und basiert auf den Prinzipien der objektorientierten Programmierung. Diese Objekte enthalten Attribute (also die Daten) und Methoden (also die Funktionen), wodurch sie leicht referenziert und bearbeitet werden können.<br>
Beispiele ObjektDB, Db4o, Oracle-Datenbank, IBM DB2

* Netzwerkdatenbanken<br>
Die Datenbank ähnelt einer hierarchischen Datenbank, unterscheidet sich jedoch dadurch, dass sie den untergeordneten Datensatz mit verschiedenen übergeordneten Datensätzen verbindet und so bidirektionale Beziehungen ermöglicht. <br>Beispiele: Integrated Data Store (IDS), EDMS von Xerox usw.