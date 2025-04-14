CAS Geographische Informationssysteme

Modul: GIS 1

Übung Ü_M1_GDB_20240506.docx

File-GeoDataBase in ArcGIS Pro





Inhaltsverzeichnis

Verwendete Daten	2

Vorbemerkungen und Ziele	4

Zielsetzung	4

Vorbemerkungen	4

Vorbereitung	4

Basiskarte laden	5

Suche verwenden (Geocoding)	5

Erstellen einer File-Geodatabase	5

Neue FGDB	5

Feature-DataSet und Feature Klassen	6

Feature-Dataset erstellen	6

Feature-Klassen erstellen	6

Geodaten importieren	7

Digitalisieren	8

Editieren der Attributtabelle	8

Digitalisieren mit Snap-Funktionen	8

Ausblick	9



Abbildungsverzeichnis

 Abbildung 1: Datenstruktur der FGDB	5

 Abbildung 2: Feature erstellen	7

# 

# Verwendete Daten



Ordner: OSM/Buildings.shp

	Eigene Daten 

- WMS

- http://ows.terrestris.de/osm/service?

- https://owsproxy.lgl-bw.de/owsproxy/ows/WMS_Maps4BW?

- http://sgx.geodatenzentrum.de/wms_topplus_open?

- 

Informationen zu dieser Übung finden Sie in den Präsentationsfolien im ILIAS:

            P_CAS1_Einführung_GIS.PDF

Abbildungen:

Soweit nicht anders gekennzeichnet handelt es sich bei den Abbildungen in diesem Skript um Screenshots der aufgeführten Software, oder sie wurden aus dem ESRI ArcGIS Ressource Center entnommen:



# Vorbemerkungen und Ziele

In dieser Übung lernen Sie ein spezielles Geodatenbankformat von ESRI kennen. Diese Geodatabases sind in ArcGIS Pro implementiert und werden in Projekten automatisch integriert. Sie lernen eine File-Geodatabase anzulegen und darin DataSets und Feature-Klassen zu erstellen sowie vorhandene Daten in die FGDB zu importieren. Zur Vervollständigung werden weitere Features digitalisiert.

In dieser Übung wird in folgende Themen eingeführt: 

Arbeit mit File-Geodatabases

Import externer Daten

Digitalisierung Features

## Zielsetzung

In der ersten Übung sind Sie erstmals mit Geodatabases in Kontakt gekommen, da ESRI bei Arcgis Pro die Verwendung von FGDB stark favorisiert.

Beim Erstellen eines neuen Projektes legt ArcGIS Pro eine FGDB im Projektordner an, die zunächst leer ist. 

Schwerpunkt in dieser Übung ist die Erstellung verschiedener Feature-Klassen in einer FGDB für Bäume, Kanäle und Gebäude inklusive Attributen sowie das Importieren von bestehenden Daten in diese FGDB. Sie erhalten zum Import vorbereitete Datensätze aus OSM.

Das Projekt hat zum Ziel, in der Ortslage Tübingen Features zu ergänzen, die in einer zu importierenden Open Street Map (OSM) Datei noch fehlen. Es handelt sich dabei um ein fiktives Projekt, da vorab nicht bekannt ist, wie aktuell die OSM Daten sind. Vielleicht sind sie komplett.

## Vorbemerkungen

Viel wird in der GIS-Welt noch mit SHP- Daten gearbeitet, da recherchierte Daten oft als Shapefiles angeboten werden. SHP ist ein dateibasiertes Geodatenformat und gilt immer noch als Quasi Standard1. In einem Datenbankformat, wie GDB, lassen sich Geodaten effektiver speichern, diverse Restriktionen sind nicht mehr vorhanden. Das Format GeoDatabases von ESRI ist ein Datenbankformat von vielen, es ist proprietär1. Es gibt weitere, auch offene Datenbankformate, die in späteren Modulen behandelt werden.

GeoDatabases gibt es in drei Varianten, Personal-GDB, File-GDB und Personal ArcSDE-GDB. ESRI empfiehlt die Verwendung von FGDB.

Vor einigen Jahren wurde das Format offengelegt und mittlerweile kann es auch von OpenSource-Produkten verwendet werden.

# Vorbereitung

In dieser Übung arbeiten Sie mit Daten, die Sie in die FGDB importieren und als Hintergrundkarte mit einem WMS-Layer1. Zusätzlich digitalisieren Sie weitere Features.

Die Daten liegen vorbereitet im ILIAS Verzeichnis \Präsenztage\Daten.

Starten Sie wieder mit einem neuen Projekt:

Vorlage „Karte“

Name: Geodatabases_GDM (Vorschlag!)

Pfad: \GIS1

Haken bei „Einen neuen Ordner erstellen“

Sie können die OSM Daten auch herunterladen (das ist eine von mehreren Quellen für OSM):

http://download.geofabrik.de/europe/germany/baden-wuerttemberg/tuebingen-regbez.html

## Basiskarte laden

Zusätzlich besteht immer die Möglichkeit eine von den lokalen Behörden bereitgestellte Basiskarte zu laden, die in den örtlich gültigen Projektionen vorliegt. Wählen Sie einen der Dienste, wie unter „Verwendete Daten“ aufgeführt. Im Katalog unter „Favoriten“ finden Sie die bisher zu ArcGIS Pro hinzugefügten Dienste.

Dadurch wird eine Rasterkarte aus dem Internet in ArcGIS Pro geladen, die sich mit unterschiedlicher Auflösung und Detaillierung dem Zoom-Faktor anpasst.

Alternativ können Sie auch eine Basemap von ArcGIS Pro verwenden, die sind in der Regel aber langsamer.

Stellen Sie den richtigen Raumbezug her, UTM 32N, wie bisher auch. Die EPSG-Nr. Ist 25832. Dazu stellen Sie in den Eigenschaften der Karte(Datenrahmen) im Reiter „Koordinatensysteme“ dieses KBS ein.

## Suche verwenden (Geocoding)

In einer Karte ohne Daten können Sie sich schlecht orientieren. ArcGIS Pro hilft mit einer räumlichen Suche weiter.

Im Register „Karte“ bei „Abfrage“ klicken Sie auf „Suche“. In dem sich öffnenden Bereich tippen Sie „Tübingen“.

Der ArcGIS World Geocoding Service findet ein Ergebnis, setzt einen temporären Punkt und zoomt nach Tübingen.

# Erstellen einer File-Geodatabase

ArcGIS Pro erstellt für jedes neue Projekt eine FGDB im Projektordner. Das ist der Standard, den ESRI vorschlägt. In dieser Übung verwenden wir diese FGDB.

Nachfolgend wird beschrieben, wie abweichend von diesem Standard, eine andere bzw. eine zusätzliche GDB erstellt wird. 

## Neue FGDB

Eine Geodatabase wird in Catalog oder aus ArcGIS Pro heraus durch den Katalog erstellt. Erstellen Sie die FGDB in Ihrem Projektverzeichnis. 

Hinweis

Zur Projektverwaltung allgemein erfahren Sie in einem Webinar zusätzliche Information. Vielleicht entscheiden Sie sich danach einen anderen Speicherort zu wählen.

Öffnen Sie „Katalog“  von ArcGIS Pro . Wenn der „Katalog“ nicht sichtbar ist, kann er über das Menüband im Register „Ansicht“ geöffnet werden.

Der Katalog öffnet im Projekt-Ordner.  Auf diesen klicken Sie mit der rechten Maustaste und wählen „NeueFile-Geodatabase“. Geben Sie einen Namen z.B. „GDM_Geodatabases“ ein und erstellen Sie mit „OK“ die GDB.

In eine leere FGDB könnten neue Feature Klassen erstellt oder importiert werden.

Empfohlen wird von ESRI, zusätzlich sogenannte DataSets als Container anzulegen. In diese Datasets werden dann die Feature Klassen angelegt oder importiert. Die DataSets steuern diverse Einstellungen. So lassen sich innerhalb einer FGDB unterschiedliche Parameter der Daten organisieren.

## Feature-DataSet und Feature Klassen

Zunächst müssen Sie ein Feature-DataSet anlegen, in dem der Raumbezug definiert wird. 

Danach erstellen Sie in diesem Feature-Dataset je eine neue Feature Klasse für Punkt – Linie – Polygon). Vergeben Sie dabei für jede Feature-Klasse ein neues Attribut:

Für Baum: Art

Für Kanal: Querschnitt

Für Gebaeude: Typ

(alle als Text)

### Feature-Dataset erstellen

In der neuen, noch leeren FGDB erstellen Sie als Nächstes ein DataSet.

Rechts klicken Sie im Katalog auf Ihre Geodatabase. Wählen Sie Neu – Feature-Dataset. Geben Sie als  Name z.B. „GDM__Tuebingen“ ein. Ein Assistent führt Sie weiter durch die Erstellung. Bei Koordinatensystem geben Sie „25832 für UTM 32N“ ein (über die kleine Weltkugel können Sie nach der Nummer suchen).

Mit „Ausführen“ wird das DataSet angelegt und Sie können zurück in den Katalog. Dort enthält die GDB nun das Dataset.

In das leere Feature-DataSet können nun Daten in Form von Feature-Klassen oder Rasterdaten importiert oder neue erstellt werden.

### Feature-Klassen erstellen

Mit Rechtsklick auf das DataSet öffnet sich ein Assistent, der in 6 Schritten durch die Erstellung einer Feature-klasse führt. Fügen Sie dabei jeweils ein Feld, wie oben beschrieben hinzu. Achten Sie darauf den richtigen Feature Type einzustellen.

Die weiteren Einstellungen in den Schritten 4-6 übernehmen Sie als Standard.

Mit „Fertig“ wird die Featue-Klasse erstellt und als Layer ins Projekt hinzugefügt.

Anmerkung

Erstellen Sie diese Feature-Klassen im DataSet, nicht direkt in der FGDB.



Anmerkung: 

M- und Z- Werte werden nicht benötigt. Standard-Werte können übernommen werden.

Als Ergebnis erhalten Sie im Katalog unter Ihrem Verzeichnis eine ähnliche wie die abgebildete Struktur mit ArcGIS Pro-typischen Symbolen:



Sie haben nun 3 leere Feature-Klassen in einem DataSet innerhalb der File-Geodatabase.

## Geodaten importieren

Sehr viele Daten sind schon vorhanden, irgendwo im Netz. Deshalb ist es wichtig, vor Beginn einer Digitalisierung zu überprüfen, ob es die Daten schon gibt. Dann sollten besser vorhandene Daten importiert werden, statt viel Zeit in die eigene Erstellung zu investieren.

Sollten keine offiziellen Daten z.B. vom LGL  können beispielsweise OSM-Daten recherchiert werden. Unter dem o.g. Link finden Sie weltweite Daten. Entpacken Sie die ZIP aus dem ILIAS oder aus dem Internet in ein Verzeichnis „OSM“ im Projektordner. 

Bäume finden Sie in einer der beiden *natural*.shp-Dateien. Im Katalog wird der Feature Typ angezeigt, es gibt eine Punkt- und eine Liniendatei.

Die Gebäude sind in *buildings.shp enthalten.

Diese Daten wurden im KBS 4326 erstellt und müssen daher gesondert behandelt werden.
Hierbei zeigt sich ein Vorteil der GeoDataBase: Innerhalb der FGDB können verschiedene KBS verwaltet werden.

Für Datensätze mit unterschiedlichen KBS können jeweils entsprechende DataSets angelegt werden. Erstellen Sie daher ein neues DataSet z.B. „OSM“ in der FGDB „GDM_Geodatabases“ (Ihr jeweiliger FGDB-Name) und definieren Sie hierbei als Koordinatensystem WGS84 mit der Nummer 4326. Verfahren Sie wie in 3.2.1

Die genannten vorhandenen Dateien (oder auch andere) importieren Sie nun in dieses Dataset. 

Es gibt für den Import von großen Dateien in ein Projekt mehrere Strategien:

Import komplett in FGDB, dann Nachbearbeitung (z.B. Ausschneiden/Clip)

Laden als SHP, Nachbearbeitung, dann Export in FGDB

Strategie 2 wird empfohlen! Dabei werden eine Teilmenge (durch Auswahl) von Features in ein neues KBS in die FGDB gespeichert.

Laden Sie die beiden SHP ins Projekt. Wählen Sie jeweils Features mit der Maus im Stadtbereich Tübingen. 

Im Katalog klicken Sie auf Ihr DataSet innerhalb der Geodatabase (oder Sie erstellen vorab ein neues DataSet), wählen „importieren“ und „Feature Class“. 

Im Eingabefeld wählen Sie die gewünschte Shapedatei aus und geben als Ausgabe-Feature einen aussagekräftigen Namen an. Wählen Sie als Ausgabeverzeichnis die FGDB. 

Mit einem Klick auf OK wird die Datei importiert. ArcGIS Pro verwendet nur die ausgewählten Features der Eingabedatei.

Auf diese Weise importieren Sie die Shapefiles aus verschiedenen Quellen in eine Projektdatenbank. Es können gleichzeitig die Parameter geändert werden, z.B KBS oder nur eine bestimmte räumliche Auswahl. 

Sie könnten nun bei einem Rechnerwechsel die FGDB einfach mitnehmen, die enthaltenen Daten gehen mit.

## Digitalisieren

Grundsätzlich sind Geodaten in GIS-Software nicht bearbeitbar. Dazu muss eine sogenannte Editiersitzung geöffnet werden. In ArcGIS Pro gibt es keine Schaltflächen mehr, um eine solche Sitzung zu starten. Wenn mit Editieren begonnen wird, sei es durch das Erstellen oder das Ändern von Features, wird automatisch in den Editiermodus geschaltet. Durch Speichern der Änderung wird die Sitzung automatisch geschlossen.

Im Menüband, Register „Bearbeiten“ befinden sich die Werkzeuge zum Digitalisieren und andere Editiermöglichkeiten. Eine Übersicht finden Sie in der Hilfe von ESRI:

https://pro.arcgis.com/de/pro-app/latest/help/editing/a-quick-tour-of-editing.htm

In der Gruppe „Features“ klicken Sie das Werkzeug „Erstellen“, es öffnet sich das „Features erstellen“-Fenster. Wählen Sie den Datensatz „Baum“ durch Mausklick aus. 

Bei den Konstruktionswerkzeugen im unteren Bereich des Fensters ist nun „Punkt“ markiert. Nun können Sie mit der Maus die gewünschten Punkte setzen.

Finden Sie Bäume im Bereich der Tübinger Altstadt, die nicht in OSM enthalten sind und digitalisieren Sie die Standorte.

Sie können während des Digitalisierens bereits die Attributwerte vergeben, indem Sie entweder bei geöffneter Attributtabelle dort den Namen eingeben oder mit dem blauen Pfeil zwischen Features erstellen und Attribute wechseln.

Wenn Sie die Attributwerte nachträglich eingeben möchten, gehen Sie zum nächsten Abschnitt. Vergeben Sie fiktive Attributwerte, falls Sie die Bäume nicht erkennen.

## Editieren der Attributtabelle

Sobald Objekte digitalisiert sind, und damit in der Attributtabelle verfügbar, kann die Attributtabelle bearbeitet werden. Die Attributtabelle wurde bereits vorbereitet, indem eine neue Spalte „Art“ eingefügt wurde. Diese Spalte kann nun mit eigenen Informationen gefüllt werden, falls direkt bei der Erstellung der Features keine Werte eingetragen wurden.

## Digitalisieren mit Snap-Funktionen

Als Kanal können Sie Abschnitte des Ammerkanals digitalisieren. Sie finden auf folgender Seite den Verlauf des Ammerkanals:

http://www.tuepedia.de/wiki/Ammerkanal

Eine Linienfeature hat mehrere Klickpunkte (Vertex), dadurch ergibt sich die Struktur. Sie können versuchen, den gesamten Kanal als ein Feature zu digitalisieren oder Sie erfassen abschnittsweise. Das sollten Sie machen, wenn die Attribute sich im Verlauf ändern, z.B. die Strukturgüte eines Baches.

Falls Sie einzelne Abschnitte verbinden möchten, verwenden Sie die Fangfunktion. Sie befindet sich in der Statusleiste. Über Einstellungen öffnen sich weitere Optionen, in der Sie Einstellungen vornehmen können.

Als Polygonflächen digitalisieren Sie einige fehlende Gebäude, falls in OSM alle vorhanden sind, erstellen Sie (ohne Baugenehmigung) welche.

Bei aneinandergrenzenden Flächen schalten Sie die Fangfunktion ein. 

Mit den Fangfunktionen lassen sich, bei exakter Arbeit, Lücken oder Überlappungen zwischen Flächenobjekten, die eine gemeinsame Grenze besitzen, vermeiden. Verwenden Sie zunächst nur die Funktionen „Fangen an Punkt“ und experimentieren Sie anschließend mit den anderen Fangfunktionen.

So umfahren Sie Ihre Fläche und nach dem letzten gemeinsamen Vertex doppelklicken Sie zum Schließen der Fläche.

Sie können später mit weiteren Features fortfahren.

Digitalisierung kann eine anspruchsvolle Angelegenheit sein und erfordert einiges an Erfahrung. Sollte Interesse bestehen, kann in einem Webinar mit weiteren Funktionen und mit topologischer Funktion weitergearbeitet werden.

Anmerkung

Digitalisieren wird auch mit QGIS im Modul Open Source GIS behandelt. 

# Ausblick

Versuchen Sie sich mit einer freiwilligen Übung durch folgende Aufgabe.

Importieren Sie weitere Original-OSM Daten, beispielsweise Landuse, in die FGDB und schneiden Sie ebenfalls aus der großen Datei auf die Gemarkung zu und stellen Sie auf das Koordinatensystem UTM32N ein. Reduzieren Sie die Attributfelder auf ein absolut notwendiges Maß (ID und fclass).

Anmerkung

Ausschneiden/Clip ist ein Geoprozess, bei dem aus vorhandenen Daten ein neuer Datensatz erstellt wird. In weiteren Übungen im Rahmen der Weiterbildung lernen Sie die wichtigsten Werkzeuge kennen.

Ziehen Sie die Hilfe von ArcGIS Pro zu Rate. 

Sollten weitere Fragen auftauchen, diskutieren Sie im Forum mit der Gruppe und den Dozenten.



Viel Spaß

erstellt 22.11.16

aktualisiert: 14.04.25

Jörg Knödler



