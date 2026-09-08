### Wie entwirft man eine Datenbank? (Datenbank-Design)
Bevor man anfängt, am Computer Tabellen zu erstellen, muss man die Datenbank planen. Dieser Prozess nennt sich Datenbankentwurf und verläuft in mehreren Schritten.

1. Die Anforderungsanalyse (Was brauchen wir?)<br>
Zuerst muss man herausfinden: Welche Daten müssen überhaupt gespeichert werden? Und was soll später damit gemacht werden? Beispiel: Für eine Schulbibliothek brauchen wir Bücher und Schüler.

2. Der Konzeptionelle Entwurf (Das ER-Modell)<br>
Jetzt wird ein Bauplan gezeichnet. Dafür nutzt man das sogenannte Entity-Relationship-Modell (ER-Modell oder ERM). Es ist das bekannteste Modell, um die reale Welt stark vereinfacht grafisch darzustellen.

    Es besteht aus drei Hauptbausteinen:
    1. Entitäten (Entities): Das sind die "Dinge" oder "Objekte", über die wir Daten speichern wollen (z. B. Schüler, Bücher). Sie werden als Rechtecke gezeichnet.
    1. Attribute: Das sind die Eigenschaften dieser Dinge (z. B. Vorname, Nachname beim Schüler; Titel beim Buch). Sie werden als Ellipsen (Ovale) an die Rechtecke gehängt.
    1. Beziehungen (Relationships): Sie zeigen, wie die Dinge miteinander zusammenhängen (z. B. "Schüler leiht Buch"). Sie werden als Rauten dargestellt.

    ![Ein einfaches ER-Diagramm (Chen-Notation)](./images/DB_Design_easyER.png)
    Ein einfaches ER-Diagramm (Chen-Notation)

2.1. Die Schlüsselverteilung (Identifikation)<br>
Damit man nicht zwei Schüler mit dem Namen "Thomas Müller" verwechselt, braucht jedes Objekt ein eindeutiges Erkennungsmerkmal.

    Primärschlüssel (Primary Key):
        Das ist ein Attribut, das jeden Datensatz absolut einzigartig macht. In der Schule ist das die Schülernummer, beim Buch die ISBN-Nummer. In der Grafik werden Primärschlüssel oft unterstrichen.

    Fremdschlüssel (Foreign Key):
        Wenn ein Schüler ein Buch ausleiht, wird in der Ausleih-Tabelle die Schülernummer gespeichert. Diese Nummer "verweist" dann als Fremdschlüssel auf den echten Schüler.

2.2. Die Kardinalitäten (Wer mit wem und wie oft?)

    Wir müssen festlegen, wie viele Objekte miteinander in Beziehung stehen können. Das nennt man Kardinalität 27, 28. Es gibt drei wichtige Arten 29, 30:
    1:1-Beziehung: Jedem Objekt aus Menge A ist genau ein Objekt aus Menge B zugeordnet.
    Beispiel: Jeder Mensch besitzt genau eine Nase, und jede Nase gehört zu genau einem Menschen 29.
    1:n-Beziehung (Eins-zu-vielen): Ein Objekt aus Menge A steht mit vielen Objekten aus Menge B in Beziehung, aber jedes Objekt aus B gehört nur zu einem Objekt aus A 31.
    Beispiel: Ein Kind hat genau eine leibliche Mutter, aber eine Mutter kann mehrere leibliche Kinder haben 29.
    n:m-Beziehung (Viele-zu-vielen): Mehrere Objekte können mit mehreren Objekten verbunden sein 32.
    Beispiel: Ein Autor kann mehrere Bücher schreiben, und ein Buch kann von mehreren Autoren geschrieben werden 29.
    ![Darstellung der Kardinalitäten](./images/DB_Design_easyKardinalitäten.png)
     Darstellung der Kardinalitäten
  
1. Der Logische Entwurf und Normalisierung (Aufräumen)
Wenn der grafische Bauplan fertig ist, übersetzt man ihn in echte Tabellen (Logischer Entwurf).Dabei macht man einen sogenannten Normalisierungsprozess.<br> 
Das Ziel der Normalisierung ist es, die Datenbank sauber und fehlerfrei zu machen.
    1. Redundanzen vermeiden: <br>Das bedeutet, dass man Daten nicht unnötig doppelt speichern will (z. B. sollte der Name eines Autors nicht in jeder Buchzeile neu hingeschrieben werden, sondern nur einmal in einer Autoren-Tabelle stehen).
    1. Anomalien beheben: <br>Wenn man den Namen eines Autors ändert, soll das nicht in 100 Zeilen manuell geändert werden müssen (Änderungs-Anomalie), sondern nur an genau einer Stelle.

Wenn all diese Schritte durchdacht sind, kann man sich an den Computer setzen und die Datenbank mit der Sprache SQL (Structured Query Language) in die Tat umsetzen!
