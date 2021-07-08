# LV Einführung in SWE (KGB, BENG, VTC, MB) - Abschlussaufgabe

Mit dieser Aufgabe sollen Ihre Fähigkeiten beim objektorientierten Entwurf und einer entsprechenden C#-Implementierung überprüft werden.

Lösen Sie die Aufgabe zuzweit in einem GitHub-Projekt. Teilen Sie die Teilaufgaben gleichmäßig unter Projektteilnehmern auf. Der geleistete Beitrag jedes der beiden Teilnehmers soll dabei im Repository nachvollziehbar sein.

## Bearbeitungszeit

bis 27. Juli 2021

## Hinweise zur Realisierung

+ Der Projekt Maintainer entwirft zunächst ausgehend aus der vorhandenen Aufgabenstellung eine Klassenstruktur in UML mit PlantUML.
+ Halten Sie den Entwurf in einem Issue fest damit der Developer diese Klassenstruktur (zuerst nur die Struktur) in Csharp umsetzen kann. Die Klassen sollen dabei in einzelnen Dateien gespeichert werden.
+ Ordnen Sie über Issues die Zuständigkeiten bei der weiteren Implementierung, teilen Sie dabei die Teilaufgaben gleichmäßig unter beiden Projektteilnehmern auf.
+ Legen Sie Branches an, in denen Sie die Teilaufgaben realisieren und schließen Sie Issues nach dem Erledigen der Aufgabe. Denken Sie daran, die finale Version mit einem Release-Tag zu versehen.
+ Erstellen Sie abschließend ein UML Diagramm, das die Lösung mit allen Feldern und Methoden dokumentiert und veröffentlichen Sie Ihr Diagramm in Wiki.
+ Zum Erstellen von Diagrammen mit plantUML können Sie direkt den PlantUML-Online-Demo-Server ([https://plantuml.com](https://plantuml.com)) nutzen. Nach dem "Submit" wird das erstellte Diagramm unter dem für Sie generierten Link zur Verfügung stehen und kann in ein md-Dokument eingebunden werden, z.B.:
```
![UML Diagramm](http://www.plantuml.com/plantuml/png/SoWkIImgAStDuGf8BL6mgT7LLN3BBCxWSaZDIm6A0W00)
```

+ Die Dokumentation zu plantUML finden Sie ebenfalls unter ([https://plantuml.com](https://plantuml.com))

## Aufgabe

Schreiben Sie ein Programm, das in der Lage ist, eine Haustierverwaltung zu realisieren.

+ Erstellen Sie bitte zunächst eine abstrakte Klasse `Pet`, die als Basis der Klassenhierarchie dienen soll. Jedes Haustier hat einen Namen ( `get` -/ `set` -Property) und will gepflegt werden (abstrakte Methode `Attend()`).

Die Haustiere werden in Säugetiere (Klasse `Mammal`) und Fische (Klasse `Fish`) unterteilt.

+ Legen Sie bitte die entsprechenden Klassen an.
+ Säugetiere verfügen über eine Methode zur Fortbewegung ( `Move()` ), Fische analog über eine Methode zum Schwimmen ( `Swim()` ). Beide Methoden sind abstrakt.
+ Für alle Fische ist die Pflege einheitlich: Das Wasser muss gewechselt werden. Bitte implementieren Sie die Methode `Attend()` entsprechend (Konsolenausgabe).

Goldfische und Guppys sind spezielle Fische.

+ Legen Sie bitte die entsprechenden Klassen an.
+ Goldfische schwimmen bekanntermaßen immer im Kreis, Guppys nur vor und zurück. Bitte implementieren Sie passende `Swim()` -Methoden.

Katzen und Kaninchen sind spezielle Säugetiere.

+ Legen Sie bitte die entsprechenden Klassen an.
+ Zur Pflege von Katzen bürstet man ihr Fell. Kaninchen pflegt man durch Ausmisten ihres Stalls. Bitte implementieren Sie passende `Attend()` -Methoden.
+ Katzen bewegen sich fort, indem sie schleichen, während Kaninchen bevorzugt hoppeln. Bitte implementieren Sie passende `Move()` -Methoden.

Haustiere können einen Besitzer haben.

+ Fügen Sie der `Pet`-Klasse eine entsprechende String-Property (oder alternativ ein `public readonly` -Feld) hinzu.
+ Der Wert wird einmalig bei der Instanziierung festgelegt (bzw. auf `null` gesetzt) und kann anschließend nicht mehr geändert werden. Erstellen Sie einen passenden Konstruktor.
+ Fügen Sie den abgeleiteten Klassen ebenfalls Konstruktoren hinzu. Bitte beachten Sie dabei, dass
Katzen grundsätzlich keinen Besitzer haben ( `null` ).

Einige Haustiere lassen sich streicheln.

+ Erstellen Sie bitte zunächst ein Interface (z. B. `IStrokeable` ), mit dem sich streichelbare Haustiere auszeichnen lassen. Fügen Sie eine passende Methodendeklaration ( `Stroke()` ) hinzu.
+ Alle Säugetiere sowie Goldfische können gestreichelt werden.
+ Wenn man Katzen streichelt, schnurren sie. Leider beißen sie in einem von fünf Fällen anschließend grundlos zu. Bitte implementieren Sie dieses Verhalten.
+ Goldfische, die keinen Besitzer haben, schwimmen weg, wenn man sie streichelt.

Haustiere sollten auf einfache Weise mithilfe der Konsole ausgegeben werden können.

+ Überschreiben Sie die `ToString` -Methode in den vier nicht-abstrakten Tierklassen und geben Sie jeweils Art, Name und Besitzer (nicht bei Katzen) in einer formatierten Zeichenkette zurück.

Testen Sie Ihre Tierklassen in der Main -Methode.

+ Legen Sie einen Garten (Liste mit Säugetieren) und ein Aquarium (Liste mit Fischen) an. Füllen Sie sie mit Katzen, Kaninchen, Goldfischen und Guppys.
+ Geben Sie Ihre Haustiere auf der Konsole aus und lassen Sie sie schwimmen bzw. sich bewegen.
+ Kombinieren Sie Garten und Aquarium in einer `Pet` -Liste namens `Zoo`. Pflegen Sie den gesamten Zoo.
+ Streicheln Sie diejenigen Haustiere im Zoo, die das IStrokeable -Interface implementieren (Tipp: `as` -Operator nutzen).
+ Welches objektorientierte Konzept ermöglicht es, dass beim Zugriff über den Basisklassen-Typ die korrekten Methodenimplementierungen aus den Unterklassen aufgerufen werden?
