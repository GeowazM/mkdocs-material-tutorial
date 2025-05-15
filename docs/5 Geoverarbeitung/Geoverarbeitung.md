
**Abbildungen:**  
Soweit nicht anders gekennzeichnet, handelt es sich bei den Abbildungen in diesem Skript um Screenshots der aufgeführten Software oder sie wurden aus dem ESRI ArcGIS Resource Center entnommen.



# 1 Vorbemerkungen und Ziele

## 1.1. Vorbemerkungen

Die Erstellung von Karten über Ausgangszuständen steht oft am Beginn eines Planungsprojektes. In diesem Projekt dies am Beispiel der Windkraftthematik durchgeführt werden. Im Konkreten sollen Ausschlussflächen für Windkraftstandorte aus frei zugägnlichen Daten erarbeitet und dargestellt werden. Dabei sollen Sie dieses Projekt in Eigenarbeit unter Zuhilfenahme dieses Dokuments bearbeiten.

Aufbauend auf den Bestandsdaten von Schutzgebieten und weiteren Informationen werden Ausschlussflächen gebildet, auf denen die Windkraftnutzung ausgeschlossen ist. Dazu gibt es einen Kriterienkatalog, den wir vereinfacht anwenden:  
https://www.energieatlas-bw.de/wind/potenzialanalyse/berechnungsmethodik

## 1.2. Annahme

Am Albtrauf (Rand der Schwäbischen Alb) in der Nähe von Reutlingen kursieren Gerüchte über die Planung von Windkraftanlagen. Ein paar aufmerksame Menschen aus der Gegend fragen Sie als GIS-Experten, ob Ihre Gemeinden betroffen sein könnten und welche Auswirkung eine eventuelle Errichtung der WKA haben könnte.

Sie versprechen, aus kostenfreien Daten eine erste Ermittlung der Raumsituation zu erstellen. Sie brauchen Daten über die Nutzung und eventuell betroffene wertvolle, naturnahe Bereiche.

Besuchen Sie entweder das Geoportal BW oder den Kartendienst der LUBW, um eine Einschätzung der Schutzwürdigkeit des Projektgebiets zu bekommen. Lassen Sie sich dort alle Schutzgebiete anzeigen (siehe Abbildung 1).  
- https://udo.lubw.baden-wuerttemberg.de/public/index.xhtml  
- https://www.geoportal-bw.de/#I

**Abbildung 1:** Naturschutzgebiete dargestellt im Daten- und Kartendienst der LUBW (www.udo.lubw.badenwuerttemberg.de)

Sie entscheiden sich für eine Kombination aus Daten des Open Street Map-Projektes und den amtlichen Daten zur Biotopkartierung, die Sie zusammenführen. Zur Auswahl der richtigen Ausschnitte brauchen Sie noch OpenData des LGL.

## 1.3. Ziele dieser Übung

1. Selbstständige Datenrecherche
2. Selbstständige Projektbearbeitung unter Anwendung vorgeschlagener Geoverarbeitungswerkzeuge

- Siedlungsbestand aus Landnutzungsdaten erstellen  
- Bereiche wertvoller Biotopflächen ergänzen  
- Ausschlussflächen zu Siedlungen erstellen  
- Ausschlussflächen in der Landschaft ermitteln  

Aus den eingangs skizzierten Überlegungen wird nun eine Vorgehensweise definiert.

## 1.4. Vorgehensweise

- Daten recherchieren  
- Datensätze in einheitlichen Raumbezug überführen (UTM 32N, ESPG: 25832)  
- Puffer um Ortslage erstellen  
- Datensätze zuschneiden  
- Datensätze zusammenführen  
- Daten vereinheitlichen (Sachdaten)  
- Daten ergänzen  
- Wertvolle Bereiche ermitteln  

---
# 2 Verwendete Daten

Verwenden Sie für die Aufgabenbearbeitung möglicherweise bereits vorhandene Daten und recherchieren Sie weitere benötigte Daten:

**LGL BW:**
- AX_KommunalesGebiet.shp

**LUBW:**  
- Waldbiotopkartierung_polygon.shp  
- Offenlandkartierung_polygon.shp  

**OpenStreetmap:**
- gis_osm_buildings_a_free_1.shp  
- gis_osm_landuse_a_free_1.shp  


# 3 Vorbereitung

Um eine möglichst effiziente Projektbearbeitung zu ermöglichen, empfiehlt es sich, die benötigten Daten in eine Geodatabase zu überführen.  

    Erstellen Sie dazu eine neue Geodatabase für das aktuelle Projekt, bereiten Sie Feature-Datasets mit geeignetem Koordinatensystem vor. 

## 3.1 Datenrecherche

OpenStreetmap-Daten sind eine sehr wertvolle Datenquelle, zudem sind diese Daten kostenfrei zu erhalten. Jedoch weisen diese unterschiedliche Genauigkeiten und Vollständigkeiten auf. Alle möglichen räumlichen Themen werden von der Community erfasst. Für unser Projekt brauchen wir Nutzungsdaten, die bei OSM unter "Landuse" angeboten werden.

Bei der „Geofabrik" stehen die OpenStreetmap-Vektordaten zum kostenfreien Download zur Verfügung. Von der räumlichen Ausdehnung der Regierungsbezirke bis zur weltweiten Abdeckung können die Daten dort geladen werden.

    Geben Sie „OSM + download + geofabrik" in die Google-Suche ein! Finden Sie das Paket für das Regierungspräsidium Tübingen und laden Sie es herunter.

Geschützte Biotope fallen unter den Anhang der INSPIRE-Richtlinie und müssten bereits öffentlich zur Verfügung stehen. Versuchen Sie es:  

    Sie finden die Daten auch auf dem Kartenserver der LUBW im Verzeichnis Natur und Landschaft > Geschützte Biotope. Mit einem Klick auf den Download-Icon können Sie die gepackte Datei in Ihr Download-Verzeichnis speichern.

**Abbildung 2:** Downloadmöglichkeit für Biotopdaten beim Datendienst des LUBW.

Nun fehlen uns noch die administrativen Gebietseinheiten bzw. die Gemarkungsgrenzen, zumindest für unsere Gemeinden. Auch diese Daten fallen unter die INSPIRE-Konformität und müssten zu finden sein. Achten Sie darauf, dass Sie nach Vektordaten suchen.

**Suchen und laden Sie:** 
    „Gemarkungsgrenzen + BW + LGL+ shp + Download"

Wenn Sie alle diese Daten gefunden haben, brauchen Sie sie nicht herunterladen! Die Daten liegen vorbereitet auf dem Austauschlaufwerk bzw. ILIAS. Siehe „Verwendete Daten".

---

# 4 Daten laden

Laden Sie die aufgeführten Daten in ein neues Projekt:

- „AX_KommunalesGebiet.shp" (Gemeindegrenzen)  
- „Offenlandkartierung_polygon.shp"  
- „Waldbiotopkartierung_polygon.shp"  
- „gis_osm_landuse_a_free_1.shp"  
- „gis_osm_buildings_a_free_1.shp"  

---

# 5 Geoverarbeitung

Was muss wie verarbeitet werden, um das Ziel zu erreichen und welche Werkzeuge werden gebraucht? Die gesetzlichen Anforderungen an die Errichtung von WKA müssen nun umgesetzt werden. Dazu bietet ArcGIS Pro die benötigten Werkzeuge an, bzw. die meisten Anforderungen an WKA können über sogenannte Geoverarbeitungswerkzeuge und Abfragen bearbeitet werden.

- Abstand zu Gemeinden berechnen anhand von Puffern  
- Wertvolle Flächen finden über Abfragen  
- Unterschiedliche Daten zusammenbringen durch Vereinigung  
- Große Datensätze reduzieren durch Ausschneiden  

Geoverarbeitung ist eine wichtige Grundlage bei der Arbeit mit GIS. Dabei werden vorhandene Daten durch verschiedene Werkzeuge zu neuen Daten weiterverarbeitet. Die wichtigsten dieser Werkzeuge lernen Sie in dieser Übung praktisch kennen. Die wichtigsten Werkzeuge finden Sie in ArcGIS Pro zum Teil ganz einfach über den Tab Analyse > Werkzeuge (siehe Abbildung 3, roter Kasten). Die kompletten Geoverarbeitungswerkzeuge sind unter Analyse > Menü Geoverarbeitung > Werkzeuge (Abbildung 3, blauer Kasten) organisiert.

| Projekt | Einfügen | Analyse | Ansicht | Bearbeiten | Bilddaten | Freigeben | Aussehen | Beschriftung | Daten | Befehlssuche (Alt+Q) | ... |
|---------|----------|---------|---------|------------|-----------|-----------|----------|--------------|-------|---------------------|-----|
| ...     | ...      | ...     | ...     | ...        | ...       | ...       | ...      | ...          | ...   | ...                 | ... |

**Abbildung 3:** Organisation der Geoverarbeitungswerkzeuge in ArcGIS Pro.

Da in der „Werkzeugkiste“ (blauer Kasten) hunderte Werkzeuge organisiert sind, kann man über die Suchfunktion Stichworte für einzelne Werkzeuge eingeben.

Ein typischer, einfacher Workflow zur Geoverarbeitung könnte folgendermaßen aussehen:  
- Daten laden  
- Daten vorbereiten  
- Werkzeug aufrufen  
- Eingabeparameter festlegen  
- Geoverarbeitung durchführen  

Weitere Informationen finden Sie in der ArcGIS Pro Hilfe:  
https://pro.arcgis.com/de/pro-app/2.6/help/analysis/geoprocessing/basics/what-is-geoprocessing-.htm

---

## 5.1 Abfrage

In der Attributtabelle kann mit „Nach Attributen auswählen“ eine Auswahl an Elementen anhand der Attributinformation getroffen werden, um die zu bearbeitenden Datensätze in der Größe zu reduzieren. Bei der Anwendung von räumlichen Verarbeitungswerkzeugen werden diese in der Regel nur auf die selektierten Elemente angewandt. Oder Sie klicken einfach die Features mit der Maus an, das ist in diesem Fall schneller.

Die betroffenen Gemeinden sind Sonnenbühl, Lichtenstein, Engstingen.

**Abbildung 4:** Attributabfrage über das Symbol hinter dem roten Kästchen.

    Wählen Sie daher über die Attributtabelle der Datei „AX_KommunalesGebiet“ die gewünschten Features der Gemeinden Sonnenbühl, Lichtenstein, Engstingen aus. Siehe dazu die Übung „Abfragen“.

---

## 5.2 Clip - Ausschneiden

Oft werden Daten landesweit zur Verfügung gestellt, Sie brauchen aber oft nur einen Ausschnitt davon. Dazu können Sie dieses Werkzeug verwenden und schneiden den gewünschten Teil aus. Hier zahlt sich nun die vorab durchgeführte Selektion aus. Sie benötigen dazu Objekte, die sich in der Regel in einem anderen Dataset befinden. Das ist beispielsweise bei den landesweiten Biotopkartierungen der Fall.

**Ziel:** Erstellung jeweils einer Datei mit Biotopen und einer Datei mit Landnutzung, die sich auf den Gemarkungen der betroffenen Gemeinden befinden.

Entpacken Sie die Daten Waldbiotopkartierung_polygon.shp und Offenlandkartierung_polygon.shp in Ihr Projektverzeichnis, falls noch nicht geschehen. Es befinden sich nun Daten der Offenlandkartierung und der Waldbiotopkartierung im Verzeichnis.

Diese Daten laden Sie nun in Ihr vorbereitetes Projekt. Als Schnittlayer brauchen Sie noch die OpenData-Gemarkungsdaten (kommunaleGebiete.shp). Laden Sie die Daten ebenfalls ins Projekt.

Gruppieren Sie für eine bessere Übersichtlichkeit die Daten von verschiedenen Quellen in Layergruppen. Dazu markieren Sie mit der Maus die entsprechenden Layer und mit einem Rechtsklick darauf öffnet sich ein Kontextmenü. Die noch markierte, neue Gruppe kann umbenannt werden oder Sie benutzen dazu F2.

Mit den selektierten Gemarkungsflächen können nun die einzelnen Datensätze auf die interessanten Gebiete zugeschnitten werden.

Die Ausschneidewerkzeuge finden Sie unter Geoverarbeitungswerkzeuge > Analysis Tools > Extrahieren > Ausschneiden. Öffnen Sie das Werkzeug.

Schneiden Sie die Datensätze:  
- gis_osm_landuse_a_free_1.shp  
- gis_osm_buildings_a_free_1.shp  
- Offenlandkartierung_polygon.shp  
- Waldbiotopkartierung_polygon.shp  

aus und wählen Sie diese dementsprechend als Eingabe-Features aus.  
Geben Sie als Clip-Features den Datensatz „AX_KommunalesGebiet.shp“ ein, achten Sie bitte darauf, dass die drei Gemeinden ausgewählt sind.

Vergeben Sie folgende Ausgabenamen:  
- OSM_Landuse_clip  
- OSM_Gebaeude_clip  
- Offenlandkartierung_clip  
- Waldbiotopkartierung_clip  

Sie haben nun die Projektdateien in der gewünschten Ortslage erstellt. Die Ursprungsdatei können Sie nun ausschalten, um die Performance beim Zoomen in der Karte zu verbessern.

**Abbildung 5:** Ausgeschnittene Übungsdatensätze.

---

## 5.3 Buffer - Puffererstellung

Nachdem die Daten auf das Projektgebiet zugeschnitten wurden, fahren wir mit der Puffererstellung fort. Damit werden Abstandskriterien sehr einfach umgesetzt und dargestellt. Innerhalb des Abstandes von 700 m zu Siedlungsflächen besteht eine Ausschlussfläche nach dem Kriterienkatalog.

Puffer werden mit dem Werkzeug „Paarweise puffern“ aus dem Schnellzugriff (Abbildung 3, roter Kasten) im Toolset Analysis Tools > Nähe / Paarweise Überlagerung um bestehende Objekte gebildet. Diese Objekte können Polygon-Features, Linien-Features oder Punkt-Features sein. Das Ergebnis ist immer ein Polygon-Feature-Dataset.

**Ziel:** Erstellung eines Puffers (700 m) um die Gemeindeflächen.

Eine grobe Annäherung an den Ortsbereich bietet der Landuse-Datensatz von OpenStreetmap. Dieser Datensatz enthält eine Landnutzungsklasse „residential“, welche bebaute Gebiete als Polygone darstellt.

Da zunächst für die Abstandsanalyse nur Abstände zu bebauten Bereichen relevant sind, wird im ersten Schritt die Landnutzungsklasse „residential“ über eine Attributabfrage selektiert. Die Pufferberechnung wird im Folgenden nur auf selektierte Elemente angewandt.

Führen Sie eine Attribut-Selektion für die Wohngebiete durch. Wählen Sie dazu die Abfrage:  
`fclass = 'residential'`

Um die nun selektierten Wohngebiete werden die Puffer berechnet.  
Öffnen Sie ein Pufferwerkzeug und erstellen Sie die Puffer mit einer Distanz von 700 Metern.  
- Eingabedatensatz: gis_osm_landuse_a_free_1.shp  
- Ausgabedatensatz: Siedlung_Puffer_700m  
- Abstand: 700 Meter  
- Dissolve-Typ: Zusammenfassen zu einem Feature  

Belassen Sie die weiteren Einstellungen.

**Abbildung 6:** Eingabeoberfläche für die Pufferberechnung.

---

## 5.4 Union - Vereinigen verschiedener Datensätze

Im Unterschied zu „Merge“ vereinigt dieses Werkzeug auch Datensätze mit unterschiedlicher Sachdatenstruktur. Überlappungen werden verschnitten, d.h. es entstehen keine doppelten Flächen. Das Ergebnis hat dann Attributfelder aus allen Eingabelayern.

**Hinweis:** Überlegen Sie, ob alle Felder gebraucht werden.

Im Projekt existieren verschiedene Datensätze, die Informationen zur Landnutzung enthalten: die gepufferte Landuse, Offenlandbiotope und Waldbiotope, die
