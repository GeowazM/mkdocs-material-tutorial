## Übungsaufgabe: 3D-Modellierung und Rasteranalyse des Hambacher Forsts

**Modul:** GIS 1
**Thema:** 3D-Visualisierung und Rasteranalyse von LiDAR-Daten
**Bearbeitungszeit:** 90 Minuten

---

### **Lernziele**

- Sie verstehen die Grundlagen von Digitalen Geländemodellen (DGM) und Digitalen Oberflächenmodellen (DOM).
- Sie können LiDAR-Daten (LAS-Format) in ArcGIS Pro importieren und visualisieren.
- Sie beherrschen die Rasterisierung von Punktwolken.
- Sie führen grundlegende Rasteranalysen durch (Isohypsen, Schummerung, Hangneigung, Geländeexposition).
- Sie wenden Geoverarbeitungswerkzeuge zur Analyse von Geländeoberflächen an.

---

### **Szenario**

Sie arbeiten als GIS-Analyst und sollen ein 3D-Modell des Hambacher Forsts erstellen und verschiedene Rasteranalysen durchführen, um die Geländeoberfläche zu charakterisieren. Die Ergebnisse sollen für die Planung von Renaturierungsmaßnahmen oder für die Visualisierung von Veränderungen durch den Tagebau genutzt werden.

### **Verwendete Daten**

Ordner: Geodaten/LGL/3D

* DGM\_5m\_GRIDXYZ\_UTM\_xyz.zip
(DGM5\_GRIDXYZ\_UTM\_DTMBIN1UTM\_512800\_5452000\_dtm.xyz)
* LAS-Datensätze (LAS\_Hambach\_merge\_first.las, LAS\_Hambach\_merge\_last.las)
* WMS-Dienste:
    * `http://ows.terrestris.de/osm/service?`
    * `https://owsproxy.lgl-bw.de/owsproxy/ows/WMS_Maps4BW?`
    * `http://sgx.geodatenzentrum.de/wms_topplus_open?`


### **Vorbereitung**

1. **Datenbeschaffung:** Laden Sie die genannten Daten aus dem bereitgestellten Ordner "Geodaten/LGL/3D" in Ihr Arbeitsverzeichnis.
2. **Projekt einrichten:** Erstellen Sie ein neues ArcGIS Pro-Projekt.
3. **Raumbezug prüfen:** Stellen Sie sicher, dass das Koordinatensystem auf UTM 32N (EPSG:25832) eingestellt ist.

> **Hinweis aus der Lernforschung:** Die Vorbereitung der Daten und die Festlegung eines geeigneten Koordinatensystems sind entscheidend für die Genauigkeit der späteren Analysen (vgl. Longley et al., Geographic Information Systems and Science).

---

### **Aufgabenstellung**

#### **1. Datenrecherche im Internet (10 Minuten)**

Recherchieren Sie im Internet nach Informationen über den Hambacher Forst, insbesondere über die Geologie, Topographie und die Auswirkungen des Tagebaus. Nutzen Sie Geoportale und andere Online-Ressourcen.

> **Hinweis aus der Lernforschung:** Die Recherche im Internet fördert die Informationskompetenz und das Verständnis für den Kontext der Aufgabe (vgl. Bransford et al., How People Learn).

#### **2. Vektordatengenerierung aus XYZ-Daten (15 Minuten)**

1. **XYZ-Daten importieren:** Entpacken Sie die Datei "DGM\_5m\_GRIDXYZ\_UTM\_xyz.zip". Importieren Sie die XYZ-Daten (DGM5\_GRIDXYZ\_UTM\_\*.xyz) als Punkt-Feature-Class in ArcGIS Pro (Geoverarbeitung > XY Tabelle nach Punkt).
2. **Koordinatensystem definieren:** Weisen Sie der Feature-Class das Koordinatensystem UTM 32N (EPSG:25832) zu.
3. **Visualisierung:** Visualisieren Sie die Punktwolke in der Kartenansicht.

> **Hinweis aus der Lernforschung:** Die Visualisierung der Punktwolke hilft, die räumliche Verteilung der Höhenpunkte zu verstehen (vgl. Ware, Information Visualization).

#### **3. 3D-Visualisierung von LAS-Daten (20 Minuten)**

1. **LAS-Daten hinzufügen:** Fügen Sie die LAS-Datensätze (LAS\_Hambach\_merge\_first.las, LAS\_Hambach\_merge\_last.las) dem Projekt hinzu (Katalog > Ordner > Zum Ordner verbinden).
2. **Neue Szene erstellen:** Erstellen Sie eine neue "Lokale Szene" (Register "Einfügen" > Gruppe "Projekt" > "Neue Karte" > "Neue lokale Szene").
3. **LAS-Daten in Szene laden:** Ziehen Sie die LAS-Datensätze aus dem Katalog in die Szene.
4. **Navigation:** Navigieren Sie in der 3D-Szene und erkunden Sie die Punktwolken. Verwenden Sie das Mausrad, um die Perspektive zu ändern, und die linke Maustaste, um den Ausschnitt zu verschieben.

> **Hinweis aus der Lernforschung:** Die 3D-Visualisierung ermöglicht ein besseres Verständnis der Geländeoberfläche und der räumlichen Beziehungen (vgl. Bishop, Developing Geographic Literacy).

#### **4. Rasterisierung von LAS-Daten (15 Minuten)**

1. **Werkzeug "LAS-Dataset in Raster":** Wechseln Sie zurück in die Kartenansicht. Öffnen Sie das Werkzeug "LAS-Dataset in Raster" (Geoverarbeitung > Conversion Tools > Punktwolke).
2. **Parameter festlegen:**
    * Eingabedatensatz: "LAS\_Hambach\_merge\_last.las"
    * Ausgabedatensatz: "Hambach\_DHM"
    * Wertfeld: "Höhe"
    * Abtastwert: "2" (für eine räumliche Auflösung von 2 Metern)
3. **Raster erzeugen:** Führen Sie das Werkzeug aus.

> **Hinweis aus der Lernforschung:** Die Wahl des Abtastwerts beeinflusst die Detailgenauigkeit des resultierenden Rasters. Experimentieren Sie mit verschiedenen Werten, um den optimalen Wert für die Analyse zu finden.

#### **5. Rasteranalysen (30 Minuten)**

Führen Sie die folgenden Rasteranalysen auf dem erzeugten DGM ("Hambach\_DHM") durch:

1. **Isohypsen:** Erstellen Sie Isohypsen (Höhenlinien) mit einem Höhenintervall von 25 Metern (Geoverarbeitung > Spatial Analyst Tools > Oberfläche > Konturlinie). Glätten Sie die Isohypsen anschließend mit dem Werkzeug "Linie glätten" (Geoverarbeitung > Cartography Tools > Generalisierung). Beschriften Sie die Isohypsen mit den Höhenangaben.
2. **Schummerung:** Erzeugen Sie eine Schummerung (Hillshade), um die Geländeoberfläche plastisch darzustellen (Geoverarbeitung > Spatial Analyst Tools > Oberfläche > Schummerung). Experimentieren Sie mit verschiedenen Azimut- und Höhenwerten, um die optimale Beleuchtung zu erzielen.
3. **Hangneigung:** Berechnen Sie die Hangneigung (Slope) des Geländes (Geoverarbeitung > Spatial Analyst Tools > Oberfläche > Hangneigung).
4. **Geländeexposition:** Berechnen Sie die Geländeexposition (Aspect), um die Ausrichtung der Hänge zu bestimmen (Geoverarbeitung > Spatial Analyst Tools > Oberfläche > Geländeexposition).

> **Hinweis aus der Lernforschung:** Die Kombination verschiedener Rasteranalysen ermöglicht eine umfassende Charakterisierung der Geländeoberfläche (vgl. De Smith et al., Geospatial Analysis).

---

### **Abgabe**

* Erstellen Sie eine Karte, die die Ergebnisse der Rasteranalysen (Isohypsen, Schummerung, Hangneigung, Geländeexposition) darstellt.
* Fügen Sie der Karte einen Titel, eine Legende, einen Maßstab und einen Nordpfeil hinzu.
* Beschreiben Sie kurz die Ergebnisse der Analysen und interpretieren Sie die Geländeoberfläche des Hambacher Forsts.
* Dokumentieren Sie Ihre Arbeitsschritte und Entscheidungen in einer kurzen Beschreibung.

---

### **Bewertungskriterien**

* Korrekte Durchführung der Geoverarbeitungsschritte
* Nachvollziehbare Dokumentation
* Qualität der Karte und der Visualisierung
* Interpretation der Ergebnisse

---

**Viel Erfolg bei der Bearbeitung!**

Die Platzhalter für die Bilder (`BILD-URL`) musst du natürlich noch durch passende Bild-URLs ersetzen.

<div style="text-align: center">⁂</div>

[^1]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/62194985/941182f3-e4ab-40ee-809d-b39a80498403/U_M1_07_Rasterdaten_20240506.pdf

