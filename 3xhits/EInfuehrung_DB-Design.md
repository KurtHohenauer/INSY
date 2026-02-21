# Einführung in die Welt der Datenbanken
Stell dir vor, du baust das nächste Instagram oder Netflix. Wo speicherst du all die Benutzerprofile, Passwörter, Bilder und Likes? Wenn du sie einfach in einer Textdatei oder Excel-Tabelle speicherst, wird das System extrem langsam und fehleranfällig, sobald Millionen von Nutzern gleichzeitig darauf zugreifen.
Genau hier kommen Datenbanksysteme ins Spiel. Sie speichern Daten sicher, strukturiert und erlauben es, rasend schnell nach Informationen zu suchen.

### Welche Arten von Datenbanken gibt es?
Im Laufe der Zeit haben sich verschiedene Modelle entwickelt, je nachdem, welche Art von Daten gespeichert werden soll:

1. Relationale Datenbanken (Tabellen):<br> 
Das ist das bekannteste und am weitesten verbreitete Modell 6. Die Daten werden hier, ähnlich wie in Excel, in Tabellen (sogenannten Relationen) mit Zeilen und Spalten gespeichert. Sie sind perfekt für strukturierte Daten (z. B. Kunden, Bestellungen). Beispiele: MySQL, PostgreSQL, Oracle .

1. Dokumentenorientierte Datenbanken (NoSQL):<br> 
Hier werden Daten nicht in starren Tabellen gespeichert, sondern als flexible Text-Dokumente (oft im JSON-Format). Das ist super für Daten, die nicht immer gleich aufgebaut sind. Beispiel: MongoDB.

1. Graphen-Datenbanken:<br> 
Diese speichern Daten als Netzwerkknoten und deren Verbindungen. Sie sind ideal für soziale Netzwerke, um Fragen zu beantworten wie: "Wer folgt wem?" (z.B. bei Twitter oder Instagram).

1. Spaltenorientierte Datenbanken:<br> 
Sie speichern Daten nicht zeilen-, sondern spaltenweise. Das macht sie extrem schnell, wenn man riesige Datenmengen für Statistiken auswerten will .

### Wie entwirft man eine Datenbank? (Datenbank-Design)
Bevor man anfängt, am Computer Tabellen zu erstellen, muss man die Datenbank planen. Dieser Prozess nennt sich Datenbankentwurf und verläuft in mehreren Schritten.

1. Die Anforderungsanalyse (Was brauchen wir?)
Zuerst muss man herausfinden: Welche Daten müssen überhaupt gespeichert werden? Und was soll später damit gemacht werden? 14 Beispiel: Für eine Schulbibliothek brauchen wir Bücher und Schüler.

1. Der Konzeptionelle Entwurf (Das ER-Modell)
Jetzt wird ein Bauplan gezeichnet. Dafür nutzt man das sogenannte Entity-Relationship-Modell (ER-Modell oder ERM). Es ist das bekannteste Modell, um die reale Welt stark vereinfacht grafisch darzustellen.

    Es besteht aus drei Hauptbausteinen:
    1. Entitäten (Entities): Das sind die "Dinge" oder "Objekte", über die wir Daten speichern wollen (z. B. Schüler, Bücher). Sie werden als Rechtecke gezeichnet.
    1. Attribute: Das sind die Eigenschaften dieser Dinge (z. B. Vorname, Nachname beim Schüler; Titel beim Buch). Sie werden als Ellipsen (Ovale) an die Rechtecke gehängt.
    1. Beziehungen (Relationships): Sie zeigen, wie die Dinge miteinander zusammenhängen (z. B. "Schüler leiht Buch"). Sie werden als Rauten dargestellt.

![Ein einfaches ER-Diagramm (Chen-Notation)](images\DB_Design_easyER.png)
Ein einfaches ER-Diagramm (Chen-Notation)





## Schritt 3: Die Schlüsselverteilung (Identifikation)
Damit man nicht zwei Schüler mit dem Namen "Thomas Müller" verwechselt, braucht jedes Objekt ein eindeutiges Erkennungsmerkmal.
# Primärschlüssel (Primary Key): Das ist ein Attribut, das jeden Datensatz absolut einzigartig macht 23, 24. In der Schule ist das die Schülernummer, beim Buch die ISBN-Nummer 25. In der Grafik werden Primärschlüssel oft unterstrichen 22.
Fremdschlüssel (Foreign Key): Wenn ein Schüler ein Buch ausleiht, wird in der Ausleih-Tabelle die Schülernummer gespeichert. Diese Nummer "verweist" dann als Fremdschlüssel auf den echten Schüler 23, 26.
Schritt 4: Die Kardinalitäten (Wer mit wem und wie oft?)
Wir müssen festlegen, wie viele Objekte miteinander in Beziehung stehen können. Das nennt man Kardinalität 27, 28. Es gibt drei wichtige Arten 29, 30:
1:1-Beziehung: Jedem Objekt aus Menge A ist genau ein Objekt aus Menge B zugeordnet.
Beispiel: Jeder Mensch besitzt genau eine Nase, und jede Nase gehört zu genau einem Menschen 29.
1:n-Beziehung (Eins-zu-vielen): Ein Objekt aus Menge A steht mit vielen Objekten aus Menge B in Beziehung, aber jedes Objekt aus B gehört nur zu einem Objekt aus A 31.
Beispiel: Ein Kind hat genau eine leibliche Mutter, aber eine Mutter kann mehrere leibliche Kinder haben 29.
n:m-Beziehung (Viele-zu-vielen): Mehrere Objekte können mit mehreren Objekten verbunden sein 32.
Beispiel: Ein Autor kann mehrere Bücher schreiben, und ein Buch kann von mehreren Autoren geschrieben werden 29.
Grafik 2: Darstellung der Kardinalitäten
  1:1 Beziehung:
  [ MENSCH ] --- 1 --- < hat > --- 1 --- [ NASE ]


  1:n Beziehung:
  [ MUTTER ] --- 1 --- < hat > --- n --- [ KIND ]


  n:m Beziehung:
  [ AUTOR ]  --- n --- < schreibt > --- m --- [ BUCH ]
Schritt 5: Der Logische Entwurf und Normalisierung (Aufräumen)
Wenn der grafische Bauplan fertig ist, übersetzt man ihn in echte Tabellen (Logischer Entwurf) 33.Dabei macht man einen sogenannten Normalisierungsprozess. Das Ziel der Normalisierung ist es, die Datenbank sauber und fehlerfrei zu machen 30, 34. Man möchte:
Redundanzen vermeiden: Das bedeutet, dass man Daten nicht unnötig doppelt speichern will (z. B. sollte der Name eines Autors nicht in jeder Buchzeile neu hingeschrieben werden, sondern nur einmal in einer Autoren-Tabelle stehen) 30, 34.
Anomalien beheben: Wenn man den Namen eines Autors ändert, soll das nicht in 100 Zeilen manuell geändert werden müssen (Änderungs-Anomalie), sondern nur an genau einer Stelle 30, 35.
Wenn all diese Schritte durchdacht sind, kann man sich an den Computer setzen und die Datenbank mit der Sprache SQL (Structured Query Language) in die Tat umsetzen! 36, 37

