## Übungsaufgabe: Ausschlussflächenanalyse für Windkraftanlagen

**Modul:** GIS 1
**Thema:** Geoverarbeitung zur Ableitung von Ausschlussflächen für Windkraftanlagen
**Bearbeitungszeit:** 90 Minuten

---

### **Lernziele**

- Sie recherchieren und beschaffen Geodaten aus verschiedenen Quellen.
- Sie führen Geoverarbeitungsschritte wie Abfragen, Ausschneiden (Clip), Puffern und Vereinigen (Union) in ArcGIS Pro durch.
- Sie wenden Geoverarbeitungswerkzeuge zur Analyse von Ausschlussflächen an.
- Sie vereinheitlichen Datensätze und weisen ihnen eine geeignete Symbologie zu.

---

### **Szenario**

Am Albtrauf (Rand der Schwäbischen Alb) in der Nähe von Reutlingen gibt es Gerüchte über die Planung von Windkraftanlagen. Anwohner fragen Sie als GIS-Experten, ob ihre Gemeinden betroffen sein könnten und welche Auswirkungen eine eventuelle Errichtung der WKA haben könnte. Sie erstellen eine erste Ermittlung der Raumsituation mit frei verfügbaren Daten.

### **Verwendete Daten**

Ordner: Geoverarbeitung

* AX\_KommunalesGebiet.shp (Gemeindegrenzen)
* Waldbiotopkartierung\_polygon.shp
* Offenlandkartierung\_polygon.shp
* gis\_osm\_buildings\_a\_free\_1.shp
* gis\_osm\_landuse\_a\_free\_1.shp


### **Vorbereitung**

1. **Datenrecherche:**  Recherchieren Sie nach Geodaten, die für die Analyse relevant sind (z.B. OpenStreetMap-Daten, Biotopkartierungen, administrative Gebietseinheiten).
2. **Datenbeschaffung:** Laden Sie die genannten Daten aus dem bereitgestellten Ordner "Geoverarbeitung" in Ihr Arbeitsverzeichnis.
3. **Projekt einrichten:** Erstellen Sie ein neues ArcGIS Pro-Projekt und laden Sie die Geodaten.
4. **Raumbezug prüfen:** Stellen Sie sicher, dass das Koordinatensystem auf UTM 32N (EPSG:25832) eingestellt ist.
5. **Datenvisualisierung:**  Symbolisieren Sie die Biotope nach Kategorie (BIOTOPTY02) und beschriften Sie sie nach Typ (BIOTOPTYP\_). Weisen Sie den LGL-Layern eine transparente Füllung und administrative Grenzen als Umriss zu.

> **Hinweis aus der Lernforschung:** Die Visualisierung der Daten fördert das räumliche Verständnis und erleichtert die spätere Interpretation der Analyseergebnisse (vgl. Mayer, Multimedia Learning).

---

### **Aufgabenstellung**

#### **1.  Daten laden und vorbereiten (10 Minuten)**

Laden Sie die aufgeführten Daten in ein neues ArcGIS Pro-Projekt. Gruppieren Sie die Daten nach Datenquellen in Layergruppen (z.B. "OSM", "LUBW", "LGL"), um die Übersichtlichkeit zu erhöhen.

> **Hinweis aus der Lernforschung:** Eine klare Strukturierung der Daten in Layergruppen reduziert die kognitive Belastung und erleichtert die Navigation im Projekt (Cognitive Load Theory).

#### **2.  Ausschneiden (Clip) (20 Minuten)**

Schneiden Sie die landesweiten Datensätze (OSM Landuse, OSM Gebäude, Offenlandkartierung, Waldbiotopkartierung) auf den Bereich der Gemeinden Sonnenbühl, Lichtenstein und Engstingen zu.

1. **Selektion:** Wählen Sie in der Attributtabelle der Datei "AX\_KommunalesGebiet" die Gemeinden Sonnenbühl, Lichtenstein und Engstingen aus.
2. **Ausschneiden-Werkzeug:** Verwenden Sie das Werkzeug "Ausschneiden" (Geoverarbeitung > Analysis Tools > Extrahieren > Ausschneiden), um die Datensätze zuzuschneiden.
3. **Eingabe-Features:** Wählen Sie die zuzuschneidenden Datensätze (OSM Landuse, OSM Gebäude, Offenlandkartierung, Waldbiotopkartierung).
4. **Clip-Features:** Wählen Sie den Datensatz "AX\_KommunalesGebiet" mit den ausgewählten Gemeinden.
5. **Ausgabe-Namen:** Vergeben Sie aussagekräftige Namen für die Ausgabedateien (z.B. "OSM\_Landuse\_clip", "OSM\_Gebaeude\_clip").

> **Hinweis aus der Lernforschung:** Formulieren Sie vor der Anwendung des Werkzeugs das Ziel des Geoverarbeitungsschritts und die notwendigen Schritte in eigenen Worten. Dies fördert das konzeptuelle Verständnis (vgl. Reigeluth, Elaboration Theory).

#### **3.  Puffer erstellen (20 Minuten)**

Erstellen Sie einen Puffer von 700 Metern um die Siedlungsflächen, um den Abstand zu Siedlungsgebieten als Ausschlusskriterium für Windkraftanlagen abzubilden.

1. **Landnutzungsklasse "residential":** Wählen Sie im Datensatz "OSM\_Landuse\_clip" die Landnutzungsklasse "residential" aus (Abfrage nach Attributen).
2. **Puffer-Werkzeug:** Verwenden Sie das Werkzeug "Puffer" (Geoverarbeitung > Analysis Tools > Nähe > Puffer), um einen Puffer um die ausgewählten Siedlungsflächen zu erstellen.
3. **Eingabe-Features:** Wählen Sie den Datensatz "OSM\_Landuse\_clip" mit der ausgewählten Landnutzungsklasse "residential".
4. **Distanz:** Geben Sie einen Pufferabstand von 700 Metern ein.
5. **Ausgabe-Name:** Vergeben Sie einen aussagekräftigen Namen für die Ausgabedatei (z.B. "Siedlungsgebiete\_Puffer\_700m").

> **Hinweis aus der Lernforschung:** Visualisieren Sie den Puffer um die Siedlungsgebiete, um die räumliche Auswirkung des Abstandskriteriums zu verdeutlichen.

#### **4.  Biotope als Ausschlussflächen (15 Minuten)**

Identifizieren Sie wertvolle Biotope, die als Ausschlussflächen für Windkraftanlagen dienen sollen.

1. **Vereinigen (Union):** Führen Sie die Datensätze "Offenlandkartierung\_clip" und "Waldbiotopkartierung\_clip" mit dem Werkzeug "Vereinigen" (Geoverarbeitung > Analysis Tools > Überlagerung > Vereinigen) zu einem Datensatz "Biotope\_clip" zusammen.
2. **Abfrage:** Wählen Sie im Datensatz "Biotope\_clip" alle Biotope aus, die als "besonders wertvoll" oder "schutzwürdig" eingestuft sind (Abfrage nach Attributen, z.B. anhand des Attributs "BIOTOPTYP").

> **Hinweis aus der Lernforschung:** Diskutieren Sie in der Gruppe, welche Biotoptypen als Ausschlussflächen berücksichtigt werden sollen und wie die Kriterien für die Auswahl definiert werden können.

#### **5.  Vereinheitlichung und Symbologie (15 Minuten)**

Vereinheitlichen Sie die Datensätze und weisen Sie ihnen eine geeignete Symbologie zu, um die Ergebnisse der Analyse übersichtlich darzustellen.

1. **Felder hinzufügen:** Fügen Sie den Datensätzen ggf. fehlende Felder hinzu (z.B. ein Feld "Ausschlussgrund" mit dem Datentyp "Text").
2. **Feldberechnung:** Berechnen Sie die Werte für das Feld "Ausschlussgrund" basierend auf den Attributen der Datensätze (z.B. "Siedlungsgebiet" für den Puffer um Siedlungsgebiete, "Biotop" für die ausgewählten Biotope).
3. **Symbologie:** Weisen Sie den Ausschlussflächen eine einheitliche Symbologie zu (z.B. eine rote Füllfarbe mit Transparenz), um sie von anderen Flächen zu unterscheiden.

> **Hinweis aus der Lernforschung:** Erstellen Sie eine Legende, die die Symbologie der verschiedenen Ausschlussflächen erklärt.

---

### **Abgabe**

* Dokumentieren Sie Ihre Arbeitsschritte und fügen Sie Screenshots der wichtigsten Zwischenergebnisse (z.B. Abfragemasken, Geoverarbeitungswerkzeuge, Kartenansichten) in eine Markdown-Datei ein.
* Beschreiben Sie kurz Ihre Erkenntnisse und Herausforderungen.
* Diskutieren Sie die Ergebnisse der Analyse und bewerten Sie die Eignung der Fläche für Windkraftanlagen.
* Verwenden Sie für Bilder die Syntax `Bildbeschreibung`.

---

### **Bewertungskriterien**

* Korrekte Durchführung der Geoverarbeitungsschritte
* Nachvollziehbare Dokumentation
* Reflexion der Ergebnisse und Herausforderungen
* Anwendung von Best Practices (z.B. sinnvolle Dateinamen, nachvollziehbare Projektstruktur)
* Interpretation der Ergebnisse im Hinblick auf die Eignung für Windkraftanlagen

---

**Viel Erfolg bei der Bearbeitung!**

Die Platzhalter für die Bilder (`BILD-URL`) musst du natürlich noch durch passende Bild-URLs ersetzen.

<div style="text-align: center">⁂</div>

[^1]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/62194985/c4dcf932-c4f6-43e0-8717-6dba3773b628/U_M1_05_Geoverarbeitung_20240506.pdf

