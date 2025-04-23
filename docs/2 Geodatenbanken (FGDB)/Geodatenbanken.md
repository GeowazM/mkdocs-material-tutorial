## Übung 2: Arbeiten mit der File-Geodatabase (FGDB)

**Modul:** GIS 1
**Software:** ArcGIS Pro
**Bearbeitungszeit:** 90 Minuten

---

### **Lernziele**

- Sie verstehen Aufbau und Vorteile der File-Geodatabase (FGDB) im Vergleich zu Shapefiles.
- Sie können eine FGDB anlegen, strukturieren und mit eigenen sowie importierten Daten füllen.
- Sie wenden grundlegende Digitalisierungs- und Editierfunktionen in ArcGIS Pro an.
- Sie reflektieren typische Fehlerquellen und Best Practices beim Arbeiten mit Geodatabases.

---

### **Verwendete Daten**

- OSM/Buildings.shp (Gebäude)
- OSM/natural.shp (Bäume, Linien)
- WMS-Dienste (Basiskarte)
- Projektordner: \GIS1\Geodatabases_GDM

---

### **Aufgabenstellung**

#### **1. Vorbereitung und Basiskarte laden**

- Legen Sie ein neues ArcGIS Pro-Projekt mit der Vorlage „Karte“ an und speichern Sie es im Ordner \GIS1.
- Laden Sie eine Basiskarte (WMS oder ArcGIS-Basemap) und stellen Sie das Koordinatensystem auf UTM 32N (EPSG:25832) ein.

**Beispielbild: Basiskarte in ArcGIS Pro**
Basiskarte

---

#### **2. Erstellen und Strukturieren einer File-Geodatabase**

- Öffnen Sie den Katalog in ArcGIS Pro.
- Erstellen Sie im Projektordner eine neue File-Geodatabase (z.B. „GDM_Geodatabases“).
- Legen Sie darin ein Feature-Dataset (z.B. „GDM_Tuebingen“) mit dem Koordinatensystem EPSG:25832 an.

**Beispielbild: Datenstruktur einer FGDB**
Datenstruktur FGDB

---

#### **3. Feature-Klassen erstellen**

- Erstellen Sie im Feature-Dataset drei Feature-Klassen:
    - **Bäume** (Punkte, Attribut: Art, Typ Text)
    - **Kanäle** (Linien, Attribut: Querschnitt, Typ Text)
    - **Gebäude** (Polygone, Attribut: Typ, Typ Text)
- Verwenden Sie für jede Feature-Klasse den Assistenten und achten Sie auf die richtigen Geometrietypen und Attribute.

---

#### **4. Import externer Geodaten**

- Entpacken Sie die vorbereiteten OSM-Daten in den Projektordner (\OSM).
- Legen Sie in Ihrer FGDB ein weiteres Feature-Dataset „OSM“ mit Koordinatensystem WGS84 (EPSG:4326) an.
- Importieren Sie die Shapefiles (z.B. buildings.shp, natural.shp) über „Importieren > Feature Class“ in das Dataset „OSM“.
- Wählen Sie beim Import nur die relevanten Features für den Bereich Tübingen aus (z.B. per Auswahlwerkzeug).

---

#### **5. Digitalisierung und Editieren**

- Digitalisieren Sie im Bereich der Tübinger Altstadt zusätzliche Bäume, Kanäle und Gebäude, die in OSM fehlen.
- Nutzen Sie das Werkzeug „Features erstellen“ und weisen Sie die passenden Attribute zu.
- Bearbeiten Sie ggf. die Attributtabelle nachträglich.

**Beispielbild: Feature digitalisieren in ArcGIS Pro**
Feature erstellen

---

#### **6. Arbeiten mit Snap-Funktionen**

- Aktivieren Sie die Fangfunktion („Snapping“) in der Statusleiste.
- Digitalisieren Sie Kanäle und Gebäude so, dass keine Lücken oder Überlappungen entstehen.
- Experimentieren Sie mit verschiedenen Fangoptionen (z.B. „Fangen an Punkt“).

---

#### **7. Reflexion: Vorteile und typische Fehlerquellen**

- Notieren Sie die Vorteile der FGDB gegenüber Shapefiles (z.B. Verwaltung mehrerer Feature-Klassen, keine Namensbeschränkungen, Speicherung verschiedener KBS).
- Reflektieren Sie typische Fehlerquellen (z.B. falsches KBS, fehlende Attribute, unsaubere Digitalisierung) und beschreiben Sie Maßnahmen zur Vermeidung.

---

### **Abgabe**

- Dokumentieren Sie Ihre Arbeitsschritte und fügen Sie Screenshots der wichtigsten Zwischenergebnisse (z.B. Struktur der FGDB, digitalisierte Features) in Ihre Markdown-Datei ein.
- Verwenden Sie folgende Syntax für Bilder:

```markdown
![Bildbeschreibung](BILD-URL)
```


---

### **Weiterführende Hinweise aus der Lernforschung**

- **Aktives Tun:** Durch das eigenständige Anlegen, Importieren und Digitalisieren wird das tiefe Verständnis für Datenstrukturen gefördert.
- **Visualisierung:** Nutzen Sie Skizzen und Screenshots, um komplexe Strukturen und Abläufe zu verdeutlichen (Dual Coding).
- **Reflexion:** Das schriftliche Festhalten von Fehlerquellen und Best Practices stärkt die Metakognition und nachhaltige Problemlösekompetenz.

---

**Viel Erfolg bei der Bearbeitung!**

<div style="text-align: center">⁂</div>

[^1]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/62194985/8e522078-98cf-4033-b043-5492e53b9588/U_M1_02_Geodatenbanken_20240506.docx

[^2]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/62194985/4fbf2150-d67e-4e41-9357-596d1d8c6544/U_M1_05_Geoverarbeitung_20240506.docx

