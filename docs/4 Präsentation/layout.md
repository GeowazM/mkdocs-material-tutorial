## Übungsaufgabe: Niederschlagskarte für Deutschland - Layoutgestaltung in ArcGIS Pro

**Modul:** GIS 1
**Thema:** Kartenerstellung und Layoutgestaltung
**Bearbeitungszeit:** 90 Minuten

---

### **Lernziele**

- Sie verstehen die Bedeutung von Karten als Kommunikationsmittel für räumliche Informationen.
- Sie beherrschen die grundlegenden Funktionen zur Layoutgestaltung in ArcGIS Pro.
- Sie können Kartenbestandteile (Legende, Maßstab, Nordpfeil, etc.) gezielt einsetzen.
- Sie sind in der Lage, Karten für verschiedene Ausgabemedien zu erstellen und zu exportieren.

---

### **Szenario**

Sie arbeiten als GIS-Experte und sollen eine ansprechende und informative Karte der jährlichen Niederschlagsverteilung in Deutschland erstellen. Die Karte soll sowohl für den Druck (z.B. in einem Bericht) als auch für die digitale Verbreitung (z.B. auf einer Webseite) geeignet sein.

### **Verwendete Daten**

Ordner: Uebung\_Layout

* Gewaesser\_Dtld\_Clip.shp (Gewässernetz Deutschlands, zugeschnitten)
* DTLD\_NUTS\_annual\_prec.shp (Jährliche Niederschlagsverteilung in Deutschland, NUTS1-Ebene)


### **Vorbereitung**

1. **Projekt erstellen:** Starten Sie ArcGIS Pro und erstellen Sie ein neues Projekt.
2. **Daten laden:** Laden Sie die Shapefiles "Gewaesser\_Dtld\_Clip.shp" und "DTLD\_NUTS\_annual\_prec.shp" in das Projekt.
3. **Reihenfolge anpassen:** Ordnen Sie die Layer im Inhaltsverzeichnis in einer sinnvollen Reihenfolge an (z.B. Gewässer unterhalb der Niederschlagsdaten).
4. **Symbologie festlegen:** Wählen Sie für die Niederschlagsdaten eine geeignete Symbologie aus. Verwenden Sie einen Farbverlauf, der mit Niederschlag assoziiert wird (z.B. von hellblau zu dunkelblau). Passen Sie die Klassifizierungsmethode und die Anzahl der Klassen an, um die Unterschiede in der Niederschlagsverteilung gut darzustellen.
5. **Gewässer symbolisieren:** Symbolisieren Sie die Gewässer mit einer blauen Farbe.
6. **Administrative Grenzen hervorheben:** Verwenden Sie für die administrativen Grenzen (DTLD\_NUTS\_annual\_prec.shp) eine dezente Linienfarbe, um die Bundesländer voneinander abzugrenzen.

> **Hinweis aus der Lernforschung:** Die Vorbereitung der Daten und die Festlegung einer geeigneten Symbologie sind entscheidend für die spätere Lesbarkeit und Verständlichkeit der Karte (vgl. Bertin, Semiology of Graphics).

---

### **Aufgabenstellung**

#### **1. Layout erstellen (20 Minuten)**

1. **Neues Layout:** Fügen Sie ein neues Layout im DIN A4-Format hinzu (Register "Einfügen" > Gruppe "Projekt" > "Neues Layout").
2. **Kartenrahmen einfügen:** Fügen Sie einen Kartenrahmen in das Layout ein (Register "Einfügen" > Gruppe "Kartenrahmen"). Wählen Sie die zuvor erstellte Kartenansicht aus.
3. **Kartenausschnitt anpassen:** Aktivieren Sie den Kartenrahmen (Register "Layout" > Gruppe "Karte" > "Aktivieren") und passen Sie den Kartenausschnitt und den Maßstab so an, dass Deutschland optimal dargestellt wird.

> **Hinweis aus der Lernforschung:** Experimentieren Sie mit verschiedenen Kartenausschnitten und Maßstäben, um ein Gefühl für die Wirkung unterschiedlicher Darstellungsweisen zu bekommen.

#### **2. Kartenelemente hinzufügen (30 Minuten)**

Fügen Sie die folgenden Kartenelemente hinzu und passen Sie sie an:

1. **Titel:** Fügen Sie einen Titel hinzu, der den Inhalt der Karte prägnant beschreibt (z.B. "Jährliche Niederschlagsverteilung in Deutschland").
2. **Legende:** Fügen Sie eine Legende hinzu, die die Symbole und Klassen der Niederschlagsdaten erklärt. Passen Sie die Beschriftung der Legende an, um sie verständlicher zu machen.
3. **Maßstabsleiste und Maßstabszahl:** Fügen Sie eine Maßstabsleiste und eine Maßstabszahl hinzu, um die räumlichen Dimensionen der Karte zu verdeutlichen.
4. **Nordpfeil:** Fügen Sie einen Nordpfeil hinzu, um die Orientierung der Karte anzuzeigen.
5. **Koordinatengitter:** Fügen Sie ein Koordinatengitter hinzu, um die geografische Lage der dargestellten Gebiete zu verdeutlichen. Passen Sie die Intervalle und die Beschriftung des Gitters an.
6. **Autoren- und Quellenangaben:** Fügen Sie einen Text hinzu, der die Autoren der Karte und die Quellen der verwendeten Daten angibt.
7. **Projektionsinformationen:** Fügen Sie einen Text hinzu, der die verwendete Kartenprojektion angibt.

> **Hinweis aus der Lernforschung:** Achten Sie auf eine ausgewogene Anordnung der Kartenelemente und auf eine klare und verständliche Beschriftung. Eine gute Gestaltung unterstützt die Wahrnehmung und Interpretation der Karteninhalte (vgl. Tufte, The Visual Display of Quantitative Information).

#### **3. Layout anpassen (20 Minuten)**

1. **Anordnung und Ausrichtung:** Ordnen Sie die Kartenelemente so an, dass ein harmonisches Gesamtbild entsteht. Achten Sie auf eine gute Ausrichtung und auf ausreichende Abstände zwischen den Elementen.
2. **Schriftarten und Farben:** Wählen Sie geeignete Schriftarten und Farben für die Kartenelemente aus. Achten Sie auf eine gute Lesbarkeit und auf eine konsistente Gestaltung.
3. **Hintergrund:** Fügen Sie dem Layout einen dezenten Hintergrund hinzu, um die Kartenelemente hervorzuheben.

> **Hinweis aus der Lernforschung:** Verwenden Sie Gestaltungsprinzipien wie Kontrast, Hierarchie und Balance, um die Aufmerksamkeit des Betrachters zu lenken und die wichtigsten Informationen hervorzuheben (vgl. Arnheim, Art and Visual Perception).

#### **4. Exportieren (20 Minuten)**

1. **PDF-Export:** Exportieren Sie das Layout als PDF-Datei (Register "Freigeben" > Gruppe "Ausgabe" > "Layout exportieren"). Wählen Sie eine geeignete Auflösung für den Druck.
2. **JPG/PNG-Export:** Exportieren Sie das Layout als JPG- oder PNG-Datei. Wählen Sie eine geeignete Auflösung für die digitale Verbreitung.
3. **Vergleich:** Vergleichen Sie die exportierten Dateien und beurteilen Sie die Qualität und Eignung für die verschiedenen Ausgabemedien.

> **Hinweis aus der Lernforschung:** Reflektieren Sie die Vor- und Nachteile der verschiedenen Dateiformate und wählen Sie das Format aus, das den Anforderungen des jeweiligen Ausgabemediums am besten entspricht.

---

### **Abgabe**

* Geben Sie die exportierten Karten (PDF und JPG/PNG) ab.
* Dokumentieren Sie Ihre Arbeitsschritte und Entscheidungen in einer kurzen Beschreibung (z.B. welche Symbologie Sie gewählt haben und warum, welche Kartenelemente Sie hinzugefügt haben und wie Sie sie angeordnet haben).

---

### **Bewertungskriterien**

* Gestaltung der Karte (Auswahl der Symbologie, Anordnung der Kartenelemente, Lesbarkeit)
* Vollständigkeit der Kartenelemente (Titel, Legende, Maßstab, Nordpfeil, etc.)
* Qualität des Exports (Auflösung, Dateiformat)
* Dokumentation der Arbeitsschritte und Entscheidungen

---

**Viel Erfolg bei der Bearbeitung!**

<div style="text-align: center">⁂</div>

[^1]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/62194985/16e7ed1f-4d6b-490d-ab0d-ceeef610c5b1/U_M1_06_Layout_20240506.pdf

