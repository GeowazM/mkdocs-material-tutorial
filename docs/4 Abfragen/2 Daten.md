# 2. Daten
Ordner: /Geodaten 
/LUBW/BiotopeLandesweit/Offenlandkartierung_polygon.shp 
/LGL/OpenData/OD_AX_Alle_VerwaltungseinheitenBW/AX_Kommunales_Gebiet.shp 
/LGL/OpenData/OD_AX_Alle_VerwaltungseinheitenBW/AX_GebietKreis.shp 

WMS 
[http://ows.terrestris.de/osm/service?]
[https://owsproxy.lgl-bw.de/owsproxy/ows/WMS_Maps4BW?]
[http://sgx.geodatenzentrum.de/wms_topplus_open?]
 
Informationen zu dieser Übung finden Sie in den Präsentationsfolien im ILIAS: 
            P_M1_RäumlicheAnalysen.PDF 


## 2.1 	Datenrecherche

Die verwendeten Daten finden Sie beim LGL BW unter OpenData und bei der Landesanstalt für Umwelt LUBW zum Download. 
https://www.lgl-bw.de/Produkte/Open-Data/
https://udo.lubw.baden-wuerttemberg.de/public/index.xhtml 

## 2.2 	Workflow
•	Projekt erstellen 
•	Daten laden 
•	Abfrage nach Attributen 
•	Lagebezogene Abfrage durchführen 
•	Ergebnis speichern 

## 2.3 	Vorbereitung

-	Entpacken Sie die genannten Daten in Ihr Arbeitsverzeichnis
-	Erstellen Sie ein neues ArcGIS Pro Projekt mit dem Namen „Vektor_Abfragen“ und laden Sie sie die eingangs angegebenen Daten. Fügen Sie eine Basemap bzw. Basiskarte hinzu, damit Sie sich besser orientieren können. Sie können eine Basemap von ESRI hinzuladen oder einen der genannten WMS. 
-	Kontrollieren Sie den Raumbezug, resp. ob das richtige Koordinatensystem eingestellt ist (25832). 
-	Stellen Sie für die Biotope eine Symbolisierung nach Kategorie – BIOTOPTY02 und eine Beschriftung nach BIOTOPTYP_ ein. 
-	Die LGL Layer werden eine transparente Füllung zugewiesen und als Umring die administrativen Grenzen aus der Vorschlagsliste von ArcGIS Pro. 
-	Die Beschriftung können Sie später schnell über die Layereigenschaften aus/einstellen, wenn sie stört. 