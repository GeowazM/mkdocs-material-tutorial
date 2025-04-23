## Übung 4: Abfragen von Geodaten nach Attributen und Lage

**Modul:** GIS 1
**Software:** ArcGIS Pro
**Bearbeitungszeit:** 90 Minuten

---

### **Lernziele**

- Sie beherrschen die interaktive Auswahl von Geoobjekten/Features in ArcGIS Pro.
- Sie führen Abfragen nach Attributen (SQL) durch.
- Sie wenden lagebezogene Auswahlmethoden an.
- Sie berechnen Geometrien (Flächen) und verstehen Datentypen in Geodatabases.
- Sie speichern Abfrageergebnisse persistent.

---

### **Verwendete Daten**

- `/Geodaten/LUBW/BiotopeLandesweit/Offenlandkartierung_polygon.shp`
- `/Geodaten/LGL/OpenData/OD_AX_Alle_VerwaltungseinheitenBW/AX_Kommunales_Gebiet.shp`
- `/Geodaten/LGL/OpenData/OD_AX_Alle_VerwaltungseinheitenBW/AX_GebietKreis.shp`
- WMS-Dienste:
    - `http://ows.terrestris.de/osm/service?`
    - `https://owsproxy.lgl-bw.de/owsproxy/ows/WMS_Maps4BW?`
    - `http://sgx.geodatenzentrum.de/wms_topplus_open?`

---

### **Vorbereitung**

1. Entpacken Sie die Geodaten in Ihr Arbeitsverzeichnis.
2. Erstellen Sie ein neues ArcGIS Pro-Projekt ("Vektor\_Abfragen") und laden Sie die genannten Daten.
3. Fügen Sie eine Basiskarte (ESRI oder WMS) hinzu.
4. Stellen Sie das Koordinatensystem auf UTM 32N (EPSG:25832) ein.
5. Symbolisieren Sie die Biotope nach Kategorie ("BIOTOPTY02") und beschriften Sie sie nach Typ ("BIOTOPTYP\_").
6. Weisen Sie den LGL-Layern eine transparente Füllung und administrative Grenzen als Umriss zu.

> **Hinweis aus der Lernforschung:**
> Die Visualisierung der Daten (Schritte 5 und 6) fördert das räumliche Verständnis und erleichtert die spätere Interpretation der Abfrageergebnisse (vgl. Mayer, Multimedia Learning).

---

### **Aufgabenstellung**

#### **1. Interaktive Auswahl (ca. 10 Minuten)**

1. Lokalisieren Sie den Landkreis Tübingen (ggf. mit Hilfe des Layers "AX\_Gebiet\_Kreis" und Transparenz).
2. Wählen Sie im Inhaltsverzeichnis unter "Nach Auswahl auflisten" den Layer "AX\_KommunalesGebiet" als einzigen auswählbaren Layer aus.
3. Selektieren Sie mit der Maus alle Gemeinden im Landkreis Tübingen. Nutzen Sie die STRG-Taste zur Korrektur.

**Beispielbild: Interaktive Auswahl**
Interaktive Auswahl mit den Werkzeugen von ArcGIS Pro

> **Hinweis aus der Lernforschung:**
> Das Beschränken auf einen auswählbaren Layer reduziert die kognitive Belastung und hilft, sich auf die relevanten Features zu konzentrieren (Cognitive Load Theory).

---

#### **2. Auswahl nach Attributen (ca. 15 Minuten)**

1. Öffnen Sie die Abfragemaske (Karte > Auswahl > Nach Attributen auswählen).
2. Wählen Sie als Eingabe-Layer "AX\_Gebiet\_Kreis".
3. Fügen Sie die Klausel "Name" "ist gleich" "Tübingen" hinzu.
4. Führen Sie die Abfrage aus.

**Beispielbild: Abfrage nach Attributen**
Abfrage nach Attributen in ArcGIS Pro

> **Hinweis aus der Lernforschung:**
> Formulieren Sie die SQL-Abfrage zunächst in natürlicher Sprache, bevor Sie sie technisch umsetzen. Dies fördert das konzeptuelle Verständnis (vgl. Reigeluth, Elaboration Theory).

---

#### **3. Lagebezogene Auswahl (ca. 15 Minuten)**

1. Wählen Sie "Lagebezogen auswählen" (Karte > Auswahl > Lagebezogen auswählen).
2. Definieren Sie:
    - Beziehung: "Innerhalb"
    - Eingabe-Features: "AX\_Kommunales\_Gebiet"
    - Auswahl-Features: "AX\_Gebiet\_Kreis"
3. Führen Sie das Werkzeug aus.
4. Speichern Sie die Auswahl als neue Datei ("Gemeinden\_LK\_Tue" in der Projekt-GDB).

**Beispielbild: Lagebezogene Auswahl**
Lagebezogene Auswahl in ArcGIS Pro

> **Hinweis aus der Lernforschung:**
> Experimentieren Sie mit verschiedenen räumlichen Beziehungen ("Schneidet", "Berührt", "Enthält"). Dies vertieft das Verständnis für räumliche Zusammenhänge.

---

#### **4. Erweiterte Attributabfrage (ca. 20 Minuten)**

1. Wählen Sie aus "Offenlandkartierung\_polygon.shp" alle Features, deren Attribut "Biotop" die Zeichenfolge "Bach" (oder "bach") enthält.
2. Nutzen Sie ggf. die ArcGIS Pro-Hilfe oder diskutieren Sie in der Gruppe.
3. Wie viele Biotope werden gefunden? Sind sie alle gleichartig?

> **Hinweis aus der Lernforschung:**
> Die Zusammenarbeit und der Austausch mit anderen Studierenden fördern das Problemlösen und die Entwicklung unterschiedlicher Perspektiven (vgl. Vygotsky, Soziokulturelle Theorie).

---

#### **5. Feldberechnung (ca. 20 Minuten)**

1. Exportieren Sie die Auswahl aus Aufgabe 4 in eine neue Feature Class ("Biotope\_Bach\_Auswahl" in der Projekt-GDB).
2. Öffnen Sie die Attributtabelle.
3. Fügen Sie ein neues Feld "Flaeche" mit dem Datentyp "Double" hinzu.
4. Berechnen Sie die Geometrie:
    - Eingabe-Features: "Biotope\_Bach\_Auswahl"
    - Geometrieattribut: "Flaeche" = "Fläche"
    - Flächeneinheit: "Quadratmeter"
    - Koordinatensystem: "Aktuelle Karte"
5. Vergleichen Sie die berechnete Fläche mit der (ggf.) vorhandenen Spalte "Area". Was fällt auf?

**Beispielbild: Feldberechnung**
Feldberechnung in ArcGIS Pro

> **Hinweis aus der Lernforschung:**
> Reflektieren Sie die Wahl des Datentyps ("Double" für genaue Flächenangaben). Dies fördert das Verständnis für Datenstrukturen und numerische Genauigkeit.

---

### **Abgabe**

- Dokumentieren Sie Ihre Arbeitsschritte und fügen Sie Screenshots der wichtigsten Zwischenergebnisse (z.B. Abfragemasken, Attributtabellen, Kartenansichten) in eine Markdown-Datei ein.
- Beschreiben Sie kurz Ihre Erkenntnisse und Herausforderungen.
- Verwenden Sie für Bilder die Syntax `Bildbeschreibung`.

---

### **Bewertungskriterien**

- Korrekte Durchführung der Abfragen
- Nachvollziehbare Dokumentation
- Reflexion der Ergebnisse und Herausforderungen
- Anwendung von Best Practices (z.B. sinnvolle Dateinamen, nachvollziehbare Projektstruktur)

---

**Viel Erfolg bei der Bearbeitung!**

<div style="text-align: center">⁂</div>

[^1]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/62194985/023c7126-2d9b-468a-829d-2a138c0e7671/U_M1_04_Abfragen_20240506.docx

