# 2. Daten
In dieser Übung wird mit frei zugänglichen, behördlichen Daten gearbeitet. Bitte recherchieren laden Sie diese über die im Laufe der Seite aufgeführten Links. Die ebenfalls genannten Webmapservices werden nicht für die Analyse benötigt, geben aber als Hintergrundkarten räumliche Orientierung.

Ordner: /Geodaten 
/LUBW/BiotopeLandesweit/Offenlandkartierung_polygon.shp 
/LGL/OpenData/OD_AX_Alle_VerwaltungseinheitenBW/AX_Kommunales_Gebiet.shp 
/LGL/OpenData/OD_AX_Alle_VerwaltungseinheitenBW/AX_GebietKreis.shp 

**WMS** 
- http://ows.terrestris.de/osm/service?
- https://owsproxy.lgl-bw.de/owsproxy/ows/WMS_Maps4BW?
- http://sgx.geodatenzentrum.de/wms_topplus_open?
 
Informationen zu dieser Übung finden Sie in den Präsentationsfolien im ILIAS: 
            P_M1_RäumlicheAnalysen.PDF 


## 2.1 	Datenrecherche

Die in dieser Übung vorgesehenen Daten finden Sie beim Landesamt für Geoinformation und Landentwicklung (LGL) BW im OpenData-Bereich und bei der Landesanstalt für Umwelt (LUBW) zum Download.  
https://www.lgl-bw.de/Produkte/Open-Data/  
https://udo.lubw.baden-wuerttemberg.de/public/index.xhtml

## 2.2 	Workflow
1. Projekt erstellen 
2. Daten laden 
3. Abfrage nach Attributen 
4. Lagebezogene Abfrage durchführen 
5. Ergebnis speichern 

## 2.3 	Vorbereitung

-	Entpacken Sie die genannten Daten in Ihr Arbeitsverzeichnis
-	Erstellen Sie ein neues ArcGIS Pro Projekt mit dem Namen „Vektor_Abfragen“ und laden Sie sie die eingangs angegebenen Daten. Fügen Sie eine Basemap bzw. Basiskarte hinzu, damit Sie sich besser orientieren können. Sie können eine Basemap von ESRI hinzuladen oder einen der genannten WMS. 
-	Kontrollieren Sie den Raumbezug, resp. ob das richtige Koordinatensystem eingestellt ist (25832). 
-	Stellen Sie für die Biotope eine Symbolisierung nach Kategorie – BIOTOPTY02 und eine Beschriftung nach BIOTOPTYP_ ein. 
-	Die LGL Layer werden eine transparente Füllung zugewiesen und als Umring die administrativen Grenzen aus der Vorschlagsliste von ArcGIS Pro. 
-	Die Beschriftung können Sie später schnell über die Layereigenschaften aus/einstellen, wenn sie stört. 