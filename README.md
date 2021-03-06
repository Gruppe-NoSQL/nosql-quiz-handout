# Gruppe 'NoSQL'-Handout
## Allgemeines:

- NoSQL: Not only SQL
- Viele Unterschiede die Abhängig vom DB-Modell sind
- NoSQL ist eine Sammelbezeichnung für nicht-relationale Datenbaken

#### SQL vs. NoSQL

- Einfügen neuer Attribute ist ohne Änderung der ganzen Struktur möglich
- Unterschied bei Schreib-und Leseanfragen, SQL wartet bis Anfragen abgeschlossen sind bevor weitere ausgeführt werden, NoSQL führt Anfragen gleichzeitig aus
- SQL: **A**tomic **C**onsistent **I**solated **D**urable
- NoSQL: **B**asic **A**vailibility **S**oftstate **E**ventual Consistency

## Graphdatenbanken:
- Knoten: Entität (eindeutig identifizierbares, einzelnes Informationsobjekt)
- Kanten: Relation zwischen Entitäten
- Eigenschaft: Knoten und Kanten können Eigenschaften haben

```
MATCH
   (s1:Stadt)-[:geburtsort_von]->(p1:Person {name: Max} )-[:wohnt_in]->(d1:Dorf)<-[:verbunden]-(s1)
WHERE
   s1.name=Ulm
RETURN
   d1
```

![Bild Graphdatenbanken](graph.png)

Gibt alle Dörfer aus, in denen ein Max wohnt, der in Ulm geboren wurde. Das Dorf muss zusätzlich auch eine Verbindung (Straße) nach Ulm haben.

## Key-Value Datenbank
- Unterteilt in collections (Sammlungen von Wertepaaren)
- Jedes Wertepaar besteht aus einem Key (Schlüssel) und einem Value (Wert)
- Durch Angabe des Keys kann der Value aus der Datenbank gezogen werden
- Der Value kann ein einfacher Wert (String, Number) oder ein Dokument (z.B: in JSON Format sein)


## Document-based Datenbank
- Unterteilt in collections (Sammlungen von Dokumenten)
- Dokumente folgen einem Schema, z.B. JSON
- Dokumente können aufeinander verweisen 
- Dokumente können über verschiedene query Spezifikationen gefunden werden 
z.B. Suche nach einem Dokument der collection „students“ mit dem Alter (age) 17
```
let result = db.students.findOne({
    "age":"17"
});
```

## Spaltendatenbanken
- Tabellen werden in Spalten aufgeteilt mit Zeilennummern je Eintrag
- Spalten werden in Spaltenfamilien (column families) gruppiert
- Spalten werden mit run-length-Einteilung speicheroptimiert

#### Codebeispiele:
- Aggregate, wie die Summe einer Spalte einfach und schnell:
```
SELECT SUM(columnName) FROM tableName;
```

- Änderungen ganzer Spalteneinträge ebeso:
```
UPDATE tableName SET columnName = columnName * 1.03;
```

## Anwendung von NoSQL-Datenbanken
#### Vorteile
- Datenbanksysteme sind häufig auf indiviudelle Anwendungsfälle abgestimmt
- Datenbanksysteme werden durch nützliche Zusatzfunktionen ergänzt
- Felxibilität im Datenbank-Schema erhöht Flexibilität von Projekten
- Starke Verbindung zwischen DB und Programmiersprachen - dadurch leichte Erlernbarkeit und beliebt bei Entwicklern

#### Weiteres
- [Sammlung von NoSQL-Datenbanken](https://hostingdata.co.uk/nosql-database/)

## Informationen zur Gruppe

#### Gruppenmitglieder
- Robin Reyer | 1275865
- Maik Kebernik | 6172455
- Fynn Weyrich | 9818779
- Matthias Biermanns | 2679565
- Florian Hase | 9444910


#### Links zu unseren Repositories und Aufteilung der Arbeit:
 - [Frontend](https://github.com/Gruppe-NoSQL/mongodb-quiz-frontend) - Matthias, Maik, Fynn
 - [Backend](https://github.com/Gruppe-NoSQL/mongodb-quiz-backend) - Robin, Florian, Fynn
 - [Hosting](https://github.com/Gruppe-NoSQL/mongodb-quiz-hosting) - Fynn