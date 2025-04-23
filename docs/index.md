# Wilkommen zu Modul GIS 1

## Zertifikatsstudium Geodatenmanager/-in
### CAS Geographische Informationssysteme
#### Modul: GIS 1

!!! tip "Inhaltsverzeichnis"

    Für mehr Informationen siehe [Zertifikatsstudium Geodatenmanager/-in Tübingen](https://www.geodatenmanagerin-tuebingen.de/weiterbildung-geodatenmanager-in/).


### Warum Geodaten & Geographische Informationssysteme?

<iframe width="640" src="https://www.youtube.com/embed/ZYfnekt9yKY" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" align-items="center" allowfullscreen></iframe>

[Hier gehts zu ILIAS](https://lms-ubinfo.uni-tuebingen.de/ilias3/ilias.php?baseClass=ilrepositorygui&reloadpublic=1&cmd=&ref_id=1){ .md-button }


---

**Autoren:** Dr. Gebhard Warth, Jörg Knödler & Mario Blersch

---

??? abstract "Inhaltsverzeichnis"

    1. Vorbemerkungen und Vorbereitungen

       1.1 Datenrecherche

       1.2 Kopieren der Übungsdaten

       1.3 Hilfe

       1.4 Terminologie

    2. Teil 1: Einführung in ArcGIS Pro

       2.1 Überblick

       2.2 Verwenden der Werkzeuge auf dem Menüband

       2.3 Öffnen und Verankern von Bereichen

       2.4 Erkunden von Ansichten

       2.5 Arbeiten mit kontextbezogenen Registerkarten

       2.6 Wechsel zum dunklen Design (optional)

    3. Teil 2: Projekterstellung mit ArcGIS Pro

       3.1 Arbeiten mit Vorlage

       3.2 Oberfläche
    
          3.2.1 Arbeiten mit dem Menüband

       3.3 Arbeiten ohne Vorlage (optional)

    4. Karten, Daten und Layer

       4.1 WMS hinzufügen

    5. Daten organisieren mit Katalog

       5.1 Analysieren der Daten im Katalog

       5.2 Ordnerverbindungen

       5.3 Eigenschaften von Dateien

       5.4 Metadaten

    6. Arbeiten in ArcGIS Pro

       6.1 Datei- und Projektformate

       6.2 Daten hinzufügen in ArcGIS Pro

       6.3 Erstellen eines Kartendokuments *.aprx

       6.4 Koordinatensystem einstellen

       6.5 Eigenschaften der Karte

       6.6 Hinzufügen einer Grundkarte (Basemap)

       6.7 Statusleiste

       6.8 Navigieren

       6.9 Tastenkombinationen

       6.10 Messen

       6.11 Darstellen von Daten am Bildschirm

       6.12 Layereigenschaften

          6.12.1 Allgemein

          6.12.2 Quelle

          6.12.3 Anzeige

       6.13 Symbole und Symbolisierung

          6.13.1 Symbolauswahl (Einzelsymbol)

          6.13.2 Symbolisierung (Thematische Karte)

       6.14 Beschriftungen

    7. Sonstige Darstellungsoptionen

       7.1 Ausblenden

       7.2 to be continued…

    8. Fazit

---

??? info "Abbildungsverzeichnis"

    - Abbildung 1: Beispiel Ordnerstruktur
    - Abbildung 2: Menüband
    - Abbildung 3: Katalog und Inhaltsverzeichnis
    - Abbildung 4: Katalog und Inhalt stapeln
    - Abbildung 5: Verankerungszielpfeile
    - Abbildung 6: 3D Ansicht Institut
    - Abbildung 7: Layer ausgewählt
    - Abbildung 8: Karte ausgewählt
    - Abbildung 9: Sachdatentabelle
    - Abbildung 10: Primäre Symbolisierung
    - Abbildung 11: Symbolauswahl
    - Abbildung 12: Starten von ArcGIS Pro
    - Abbildung 13: Projekt anlegen
    - Abbildung 14: Projekt anlegen
    - Abbildung 15: Oberfläche ArcGIS Pro
    - Abbildung 16: Menüband
    - Abbildung 17: Registerkarten "Feature Layer"
    - Abbildung 18: Koordinatensystem einstellen
    - Abbildung 19: Grundkarte von ESRI einfügen
    - Abbildung 20: Navigieren mit der Maus
    - Abbildung 21: Symbolisierungsmöglichkeiten

---

## Die Daten finden Sie [auf ILIAS](https://lms-ubinfo.uni-tuebingen.de/ilias3/ilias.php?baseClass=ilrepositorygui&reloadpublic=1&cmd=&ref_id=1)
- Fliessgewaessernetz.zip
- NaturdenkmaleENDFND.zip
- Naturschutzgebiete.zip
- Landschaftsschutzgebiete.zip
- FFH-Maehwiese.zip
- BiotopeLandesweit.zip
- tuebingen-regbez-latest-free.shp.zip

Die ZIP Dateien enthalten eine bzw. mehrere Shapefiles.

Ordner: Einführung_ArcGIS Pro
- LUBW
- LGL
- OSM

WMS
- http://ows.terrestris.de/osm/service?
- https://owsproxy.lgl-bw.de/owsproxy/ows/WMS_Maps4BW?
- http://sgx.geodatenzentrum.de/wms_topplus_open?

Informationen zu dieser Übung finden Sie in den Präsentationsfolien im ILIAS:
- P_CAS1_Einführung_GIS.PDF

---

## Vorbemerkungen und Vorbereitungen
Die Zertifikatslinie „CAS Geographische Informationssysteme“ behandelt in den ersten beiden Kursmodulen den Umgang mit räumlichen Daten anhand der Software ArcGIS Pro von ESRI. In dieser Übung werden folgende Inhalte vertieft:

- Arbeit mit Esri ArcGIS Pro
- Umgang mit Daten
- Kennenlernen der Programmoberfläche
- Symbolisierung
- Einstellungen zu Koordinatensystemen

### Datenrecherche
Die verwendeten Daten werden im ILIAS bereitgestellt. Es handelt sich um speziell vorbereitete Daten zu Tübingen. Später recherchieren Sie zu verschiedenen Geobasis- und Geofachdaten.

### Kopieren der Übungsdaten
Legen Sie auf Ihrem lokalen Laufwerk einen Ordner für die Übungsdaten an. Kopieren Sie den Ordner mit den Übungsdaten vom Austauschlaufwerk oder aus dem ILIAS bzw. dem bereitgestellten Stick in Ihren lokalen Ordner. Kontrollieren Sie im Windows Explorer, ob die Dateien schreibgeschützt sind. Falls dies zutrifft, heben Sie den Schreibschutz auf.

**Abbildung 1: Beispiel Ordnerstruktur**

Legen Sie für jede einzelne Übung einen Unterordner für die benötigten Daten an. Verwenden Sie diese Ordner jeweils als aktuelle Arbeitsverzeichnisse für die Übungen. Achten Sie beim Erstellen der Order darauf, dass keine Leerzeichen oder Umlaute, Sonderzeichen verwendet werden. Sie können zusätzlich für Ihre Ergebnisse einen eigenen Unterordner anlegen. Texte, Präsentationen usw. sollten in einem komplett anderen Ordner gespeichert werden.

### Hilfe
Beim Start von ArcGIS Pro finden Sie am Rechten Rand verschiedene Links zu Ressourcen von ESRI. Eine kurze Einführung finden Sie hier:

- [https://learn.arcgis.com/de/projects/get-started-with-arcgis-pro/](https://learnen Sie die Startseite der Online-Hilfe. Es existiert eine kontextsensitive Hilfe (Mouse Over):

- [https://pro.arcgis.com/de/pro-app/latest/get-started/help-within-the-app.htm](https://pro.arcgis.comm/de/pro-app/latest/get-started/introducing-arcgis-pro.htm](https://pro.arcgis.com/de/pro-app/latest/get-started/introducing-arcgisng Teil 1)

ArcGIS Pro vereint die zahlreichen Komponenten, die in ArcMap als einzelne Programme vorhanden waren. Die Datenverwaltung des ArcCatalog, 3D Funktionen und natürlich die Analyse und Darstellungsfunktionen werden nun zentral und teilweise über Vorlagen verwaltet.

### Terminologie
Viele bekannte Begriffe aus ArcMap sind nicht mehr gültig und neue sind hinzu gekommen. Um den Umstieg von ArcMap einfacher zu gestalten gibt es bei ESRI eine Liste mit gegenübergestellten Begriffen mit kurzen Beschreibungen:

- [https://pro.arcgis.com/de/pro-app/latest/get-started/migrate-to-arcgis-pro.htm](https://pro.arcgis.com/de/pro-app/latest/get-started/migrate-to-arcgis-probrary/brochures/pdfs/arcgis-pro-terminology-guide.pdf)
- Werkzeug
- Bereich
  - Inhalt
  - Katalog
  - Weitere kontextbezogene Fenster
- Karte
- Szene
- Kartenansicht
- Layout

---

Logo einfügen