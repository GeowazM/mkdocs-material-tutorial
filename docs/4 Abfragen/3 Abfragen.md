# 3. Abfragen
Hinweise zu den Abfragen in ArcGIS Pro (gilt auch für andere GIS):
-	Manuelle Direktabfragen können mit dem Werkzeug Erkunden (Register Karte > Gruppe Navigieren) ausgeführt werden, indem Sie mit dem Werkzeug auf ein Feature klicken oder einen Rahmen mit der Maus aufziehen. 
-	Mit Auswählen (Register Karte > Gruppe Auswahl) können aus einer Feature Class einzelne Features ausgewählt und für weitere Prozesse als Einzelmenge zur Verfügung gestellt werden.  
In den folgenden Abschnitten lernen Sie die grundlegenden Methoden der räumlichen Auswahl kennen. 
## 3.1 Interaktive Auswahl
Die interaktive Auswahl erfolgt in der Regel mit der Maus und unterstützend mit der Tastatur (Shift-Taste), wie aus anderen Anwendungen bekannt. Die (beispielhafte) Aufgabe besteht nun darin, alle Features (Gemarkungen) im Layer „AX_KommunalesGebiet“ auszuwählen, die innerhalb des Landkreises Tübingen liegen. 
Vorüberlegung:  
Es gibt mehrere Layer im Projekt, bei sich überlagernden Features wird es schwierig die richtigen zu erwischen. ArcGIS Pro bietet verschiedene Möglichkeiten, damit umzugehen: Sie können Layer mit unterschiedlichen Hervorhebungsfarben (Highlight) einstellen: 

!!! note "Aufgabe 1 - Layereigenschaften für Auswahl vornehmen" 

    Wählen Sie in den **Layereigenschaften > Auswahl** und dort auf 
    - Alternative Farbe auswählen und 
    - stellen Sie unterschiedliche Farben für verwendete Layer ein.  
    - Sie können Layer zur Auswahl deaktivieren
    - Im Inhaltsverzeichnis können Sie im Reiter – „Nach Auswahl auflisten“ durch markierten Haken einstellen, welche Layer auswählbar sind und welche nicht. 

Sie können einen Layer zum einzig Auswählbaren machen:
Im Inhaltsverzeichnis im Reiter der Standarddarstellung (Darstellungsreihenfolge) können Sie mit Rechtsklick auf einen Layer das Kontextmenü öffnen und dort über Auswahl zu Als einzig auswählbare Layer festlegen navigieren. 
Als Erstes sollten Sie den Landkreis Tübingen lokalisieren, wenn Sie nicht von hier sind, wird das schwierig. Sie können sich auf der Basiskarte orientieren oder den Layer „AX_Gebiet_Kreis“ zu Hilfe nehmen. 
Stellen Sie dessen Transparenz auf ca. 50%, wenn Sie noch eine Flächenfüllung eingestellt haben! 
In den Layereigenschaften unter Ansicht können Sie den Wert eingeben. 
Oder: Stellen Sie die Farbfüllung aus.
 
Im Reiter „Symbolisierung“ auf „Symbol“ klicken, dort „ungefüllt“ eingeben. 
 
Sie können dann auch bei Flächen die darunterliegende Basemap sehen.

 
Abbildung 1: Interaktive Auswahl
 
Selektieren Sie nun mit der Maus mit einem der Auswahlwerkzeuge bis Sie alle Gemeinden-Features im Landkreis Tübingen gefunden haben. Mit gleichzeitig gedrückter STRG-Taste auf der Tastatur können Sie die Auswahl um das angeklickte Objekt reduzieren. 

Sie sehen, diese Methode ist mühsam und nervenaufreibend. 
Es gäbe auch noch die Möglichkeit, den Wert „Schluessel“ aus der Attributtabelle zu verwenden, wenn Sie sich mit dem AGS1 auskennen. 

## 3.2 Select by Attribute – Nach Attribut auswählen 
Eine effektivere Auswahlmethode ist die Auswahl nach Attributen. Oft stehen nutzbare Informationen in den Sachdaten und sind damit über verschiedene Argumente abfragbar. 

"Aufgabe 2" Untersuchen Sie die Sachdaten der Layer nach „Tübingen“.  

    Suchen Sie nun nach Features mit der Eigenschaft Tübingen. 
    
Leider ist diese nicht in den Sachdaten des Layers „AX_KommunalesGebiet“ enthalten, das wäre schön. 
Trotzdem ist die Abfrage hier hilfreich, wir wenden Sie auf den Layer „AX_Gebiet_Kreis“ an: 
    Öffnen Sie die Abfragemaske über das Menüband Karte > Gruppe Auswahl > Werkzeug Nach Attributen auswählen. 
    Als Eingabezeile wird hier der zu untersuchende Datensatz eingegeben. Wählen Sie aus dem Drop-Down-Menü „AX_Gebiet_Kreis“.
    Unter „Klausel hinzufügen“ wird die Bedingung für Abfrage eingegeben. Wählen Sie hier „Name“ mit „ist gleich“ und geben Sie „Tübingen“ als Bedingung ein (Abbildung 2). Mit „Übernehmen“ wird der Landkreis Tübingen in der Karte ausgewählt. 

 
Abbildung 2: Eingabemaske für die Abfrage nach Attributen.
 
Nun ist das Feature mit dem Wert „Tübingen“ im Layer „AX_Gebiet_Kreis“ markiert Abbildung 3. Dieses Polygon repräsentiert den Landkreis Tübingen und kann für die im nächsten Kapitel folgende Abfrage nach den darin liegenden Gemeinden verwendet werden. 
In 3.4 werden weitere Attribut-Abfragen bearbeitet. 
 
 
Abbildung 3: Selektierte Fläche des Landkreises Tübingen.

## 3.3 Select by Location – Lagebezogen auswählen 
Eine zuvor definierte Auswahl an Features kann auf einen anderen Layer angewendet werden, um gerade dort eine weitere Auswahl von Features auf Basis der räumlichen Lage auszulösen. 
Im aktuellen Fall sollen alle Gemeindegrenzen ausgewählt werden, die innerhalb des Landkreises Tübingen liegen. 
    Mit dem Werkzeug „Lagebezogen auswählen“ (Karte > Auswahl > Lagebezogen auswählen) können detaillierte Abfragen durchgeführt werden. 
    Selektieren Sie alle Gemeinden innerhalb des Landkreises Tübingen (Abbildung 4):
    Beziehung: Innerhalb 
    Eingabe-Features: „AX_Kommunales_Gebiet“ (Features, aus denen ausgewählt werden soll)
    Auswahl-Features: „AX_Gebiet_Kreis“ (Feature mit dem räumlichen Bezug)
    Führen Sie das Werkzeug aus.

 
Abbildung 4: Eingabemenü für die lagebezogene Auswahl.

Die Auswahlmethode hat einige Auswahloptionen zu bieten, testen Sie bei Gelegenheit (!) einige davon, besonders diejenigen, die ähnlich klingen.
Als Ergebnis erhalten Sie im Layer „AX_Kommunales_Gebiet“ alle Gemeindeflächen im Landkreis Tübingen (Abbildung 5). Kontrollieren Sie das in der Attributtabelle. 

 
Abbildung 5: Selektierte Gemeinden im Landkreis Tübingen.
Sie können diese Selektion als neue Datei abspeichern: 

    Rechtsklick auf den Layer „Kommunale Gebiete“ - Daten  - „ Features exportieren – Gemeinden_LK_Tue in die Projekt-GDB. 

## 3.4. Select by Attribut – Nach Attribut auswählen II 
Mit den ersten Fertigkeiten aus 3.3 versuchen Sie sich an folgendem Auftrag: 
    Wählen Sie aus der Datei „Offenlandkartierung_polygon.shp“ alle Features, die in der Spalte „Biotop“ die Zeichenfolge „Bach“ oder „bach“ enthalten. 
    Finden Sie dabei nur gleichartige Biotope? Wie viele insgesamt?

Ziehen Sie die Hilfe von ArcGIS Pro zu Rate, wenn Sie kein Ergebnis erhalten. Oder diskutieren Sie mit Ihren netten Nachbarn. 


# 4 Feldberechnung
## 4.1 Vorbereitung 
    Klicken Sie mit der rechten Maustaste (Kontextmenü) auf den Layer und exportieren Sie die Auswahl über Daten > Features exportieren… in eine neue Datei, beispielsweise „Biotope_Bach_Auswahl“. Achten Sie darauf, dass Sie in eine Geodatabase (GDB), exportieren. ArcGIS Pro speichert nur die Auswahl. 

## 4.2 Fläche berechnen
Die exportierte Datei wird in den Datenrahmen übernommen. 
    Ziel: Erstellen Sie eine neue Spalte/ein Feld und berechnen Sie die Fläche der Features in m². 
Vorüberlegung: Vielleicht haben Sie schon etwas über Datenbanken und Tabellen gehört, über Datentypen usw. Deshalb überlegen Sie, mit welchem Datentyp das neue Feld erstellt wird. 
 
    Öffnen Sie die Tabelle der neuen Datei und klicken Sie bei den Tabellenoptionen (links im Menü der Tabelle) auf „Feld hinzufügen“. 
    Geben Sie einen aussagekräftigen Namen z.B. „Flaeche“ ein und wählen Sie „Double“ als Datentyp (Abbildung 6).
    Schließen Sie das Fenster über das Kreuz und speichern Sie dabei die Eingaben. 

 
Abbildung 6: Anlegen einer neuen Attributspalte.

Das neue Feld bzw. die neue Spalte wird erstellt und die Flächenberechnung kann angewendet werden. GIS bieten die Möglichkeit an, geometrische Eigenschaften auf Grundlage der Vektorgeometrien zu berechnen. Das können einfach Koordinaten sein, aber auch Linienlängen, Umfänge oder Flächeninhalte. Dies wird nun für die Gemeinden durchgeführt.

    In der Attributtabelle klicken Sie im Spaltenkopf von „Flaeche“ mit Rechtsklick auf „Geometrie Berechnen“. Geben Sie folgende Angaben ein (Abbildung 7):
    - Eingabe-Features: Gemeinden_LKR_Tübingen
    - Geometrieattribute: Flaeche (Attributspalte) – Fläche (Eigenschaft)
    - Flächeneinheit: Hektar
    - Wählen Sie bei Koordinatensystem „aktuelle Karte“

 
Abbildung 7: Eingabemenü für die Geometrieberechnung.

    Die Spalte ist jetzt mit den Flächen der einzelnen Features gefüllt. Vergleichen Sie das mit der Spalte „Area“, die schon mal berechnet wurde. 
    Was fällt auf?