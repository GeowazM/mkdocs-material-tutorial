# Teil 2: Projekterstellung mit ArcGIS Pro

ArcGIS Pro dient der Erfassung, Analyse und Präsentation (Ausgabe) von Geodaten. Die Möglichkeiten von ArcGIS Pro können im Rahmen dieser Weiterbildung nicht vollumfänglich erlernt werden. Zur Vertiefung bietet ESRI eine Reihe von Kursen an, kostenfreie und kostenpflichtige. 

Siehe dazu auch die Hinweise auf den Präsentationsfolien. 

In diesem Teil der Übung arbeiten Sie mit externen Daten von verschiedenen Anbietern, die als SHP vorliegen.

Rufen Sie  ArcGIS Pro auf und und machen Sie sich mit der Oberfläche vertraut. 

Nach der Installation liegt auf Ihrem Desktop ein Icon mit dem Symbol oder Sie starten über den Windows-Button links unten am Desktop: Start-Alle Programme-ArcGIS. . Falls auf Ihrem Desktop keine Symbole liegen, senden Sie aus dem Programme-Ordner ArcGIS Verknüpfungen auf den Desktop.

ArcGIS Pro erfordert beim ersten Start eine Anmeldung auf Ihrem ESRI Konto. Danach erscheint die Oberfläche mit der Möglichkeit zuletzt verwendete Projekt zu öffnen oder ein neues Projekt mit oder ohne einer Vorlage zu öffnen. 


![Placeholder](uebung_1/teil2_img5.png){ align=center }

## Arbeiten mit Vorlage

Wählen Sie „Karte“ als Vorlage. ArcGIS schlägt nun einen Projektnamen und einen Speicherort vor. 

Verwenden Sie als Wurzelverzeichnis den Ordner für dieses Modul, siehe 1.2.

Anmerkung (aus der Hilfe von ESRI)

In ArcGIS Pro können Projekte nicht kopiert oder verschoben werden: Es gibt keine Befehle oder Werkzeuge zum Kopieren der Projektdatei und der zugehörigen Dateien wie etwa der Standard-Geodatabase und der Standard-Toolbox. Es ist jedoch möglich, die Projektdatei (.aprx) mit dem Befehl Speichern unter zu kopieren. Die kopierte Projektdatei enthält Kopien der darin gespeicherten Elemente wie etwa der Karten, der Layouts und der Berichte, und verfügt über dieselben Elementverbindungen. Wenn Sie die Projektdatei, die zugehörigen Elemente und die von Karten-Layern referenzierten Daten kopieren möchten, erstellen Sie ein Projektpaket. 

Empfehlung:

Auf einer zweiten Festplatte / Partition legen Sie einen Ordner an. Der Pfad sollte kurz sein, keine Leer und Sonderzeichen enthalten. Projekte kommen dann in jeweilige Unterordner.

Die in der folgenden Abbildung gezeigte Struktur ist nur ein Beispiel. Das neu zu erstellende Projekt könnte „BadenWuerttemberg“ sein. 



Beispiel für Pfad auf einer zweiten Festplatte:

D:\GIS\Projekte\Modul1



Es wird empfohlen, den Haken „Einen neuen Ordner erstellen“ zu setzen. Damit legt ArcGIS einen neuen Unterordner mit gleichem Namen, wie das Projekt an, zusätzlich weitere Unterordner, eine Toolbox und eine Geodatabase. Im Laufe der Übungen wird darauf weiter eingegangen.

Wenn Sie die Voreinstellungen von ESRI verwenden, kann es sein, dass Ihr Pfad und/oder Benutzername Leerzeichen enthält. IT Admins machen das gerne. Das kann jedoch zu unerwarteten Problemen führen

ArcGIS Pro öffnet mit einer Hintergrundkarte von Deutschland und deutscher Oberfläche, sofern bei der Installation das deutsche Sprachpaket mit installiert wurde.



## Oberfläche 

Abbildung 15: zeigt die wichtigsten Hauptbestandteile der Gesamtoberfläche:

Menüband mit Registerkarten

Bereiche 

Inhaltsverzeichnis 

Kartenfenster 

Katalog 

Abbildung 15: ist nur eine von vielen möglichen Arbeitsumgebungen. Die Einstellungen, welche Sie in ArcGIS Pro vornehmen (Aussehen der Benutzeroberfläche oder auch was Sie unterr Optionen einstellen, werden für jeden Benutzer am PC gesondert gespeichert und bei der Anmeldung geladen.

https://pro.arcgis.com/de/pro-app/latest/get-started/get-started.htm#ESRI_SECTION1_75CF36E07CE441BC9573B0EF5BDEB120

### Arbeiten mit dem Menüband

Für eine effektive Arbeit ist es wichtig, mit dem Menüband von ArcGIS Pro umgehen zu können. Das Angebot an Registerkarten variiert, je nachdem, wo Sie sich im Bereich Inhalt befinden. Beobachten Sie die Werkzeuge im Register „Karte“,  wenn Sie auf einen Layer, eine Gruppe oder den Datenrahmen (Karte) klicken.

Das Menüband ist dynamisch. Über die Registerkarten werden zugehörige Werkzeuge angeboten.

Im Bereich „Inhalt“ klicken Sie auf einen Layer.

Der ausgewählte Layer ist blau hervorgehoben. Nachdem er ausgewählt wurde, wird die Registerkartengruppe Feature-Layer auf dem Menüband angezeigt. Darunter befinden sich drei Registerkarten mit Werkzeugen, die speziell auf Feature-Layer abgestimmt sind.

In diesen 3 Registerkarten befinden sich die Werkzeuge für Vektordaten, beispielsweise die Attributtabelle oder Werkzeug zur Beschriftung oder zur Symbolisierung.

Die Maus funktioniert (ohne Infobutton, wie in ArcMap) als Zeiger für Pop-ups, falls das eingestellt ist. Ist kein anderes Werkzeug aktiv, können damit Informationen in der Karte abgefragt werden.

## Arbeiten ohne Vorlage (optional)

Diese Vorgehemsweise ist gedacht, wenn Sie sich nicht auf die Vorgaben von ESRI verlassen möchten. Stellen Sie dies bitte erst einmal zurück:

Wiederholen Sie die Erstellung eines Projektes, diesmal ohne eine Vorlage und beobachten Sie das Verhalten von ArcGIS Probleme

ArcGIS Pro öffnet ohne Hintergrundkarte und ohne ein spezielles Verzeichnis anzulegen. Im Katalog sehen Sie einen temporären Ordner.

Fügen Sie aus der Registerkarte „Einfügen“ eine neue Karte hinzu. und verbinden Sie den Ordner mit den bereitgestellten Daten über „Ordner hinzufügen“. Dieser Ordner erscheint nun rechts im Katalog.

Speichern Sie das Projekt unter dem Namen „Uebung1_ohneVorlage) im genannten Ordner. 

Anmerkung:

Es können mehrere Karten in einem Projekt geöffnet werden, ebenso Szenen. Diese lassen sich über Reiter oberhalb des Kartenfensters auswählen. Hier kommt auch später das Layout hinzu.

# Karten, Daten und Layer

https://pro.arcgis.com/de/pro-app/latest/help/mapping/introduction/maps-in-arcgis-pro.htm

Karten enthalten in ArcGIS Pro Layer, in denen wiederum räumliche Daten dargestellt werden können. 2D Daten werden Karten genannt, 3D Daten als Szenen bezeichnet.

Ein Layer ist eine Referenz / eine Verknüpfung zu Daten. Die Daten können auf der Festplatte bzw. auf einer Cloud liegen oder als Dienst von einem Server ausgeliefert werde.

Geodaten sind in der Regel Vektor- oder Rasterdaten. Tabellendaten können einen Raumbezug haben, dann können sie importiert werden. Tabellen ohne Raumbezug können über eine ID mit Vektordaten verknüpft werden.

Dienste sind meist als Grundkarten (aus Basiskarten oder Basemap genannt) im Projekt voerhanden, entweder die von ESRI zu Verfügung gestellten oder von verschiedenen Providern abfragbar.

WMS ist ein solcher Dienst, dieses Format ist weit verbreitet. Sehr viele Basisdaten und Fachdaten werden so bereitgestellt.  Sie werden in ArcGIS über ihre URL als Verbindung hinzugefügt.

## WMS hinzufügen

In der Registerkarte „Einfügen“ bei Verbindungen suchen Sie „Server – neuer WMS Server“ und fügen eine URL in das entprechende Feld ein. Verwenden Sie:

- http://sgx.geodatenzentrum.de/wms_topplus_open?

- 

- Im Katalog erscheint ein weiterer Eintrag “Server”, der diesen Dienst auflistet. Dienste können einen oder mehrere Layer enthalten, die über den kleinen Pfeil als Liste erscheinen. 

Mit einem Rechtsklick oder durch Ziehen mit der Maus wird ein solcher Layer in das Projekt geladen, aktuell in die aktive Karte. Laden Sie einen Graustufen und einen farbigen Layer ins Projekt.

Transparenz eines Layers wird über das Register „Aussehen“ eingestellt, ebenso der Sichtbarkeitsbereich in Abhängigkeit vom Maßstab.

Registrierte Dienste werden global für die Benutzer des  Rechners vorgehalten. Sie werden im Katalog unter dem Register „Favoriten“ bereitgestellt.

# Daten organisieren mit Katalog 

## Analysieren der Daten im Katalog

Bevor Sie Daten im GIS darstellen, kann es hilfreich sein, sich zunächst über sie zu informieren. Da Geodaten mitunter aus mehreren Teilen bestehen (Shapefiles), ist deren Organisation im Windows-Explorer nicht empfehlenswert. Der Katalog ist ein Browser für die Erkundung (Typ, Größe, Projektion…) und Verwaltung (Anlegen, Umbenennen, Verschieben…) von Geodaten. Darüber hinaus zur Erstellung von Metadaten.

Sollte der Reiter für den Katalog nicht vorhanden sein, finden Sie den Katalog in der Registerkarte „Ansicht“ und dort als „Bereich Katalog“. Nach dem Öffnen schieben Sie das Fenster mit der Maus auf den  Pfeil, der am Bildschirm erscheint (oder dort, wo sie Katalog haben möchten). Über den kleinen Pin können Sie einstellen, ob der Katalog automatisch ausgeblendet wird oder nicht.

## Ordnerverbindungen

Über einen Rechtsklick auf Ordner richten Sie die Projektumgebung ein. ArcGIS Pro bereitet zwar bei der Erstellung eines Projektes eine Struktur vor, es ist trotzdem ratsam diese zu erweitern.

Fügen Sie mittels Rechtsklick auf Ordner den Wurzelordner, welcher alle Übungsdaten enthält, zu Ihrer Arbeitsumgebung hinzu, sodass Sie später schnellen Zugriff auf diese haben.

Grundsätzlich gibt es Geodaten als Punkt-, Linien-, oder Polygonfeaturesets. Im Katalog werden die einzelnen Datentypen mit unterschiedlichen Symbolen angezeigt.

## Eigenschaften von Dateien

Ein Rechtsklick auf eine Datei ermöglicht über ein Kontextmenü diverse Aktionen, z.b. das Hinzufügen zur aktuellen Karte oder einen Export in diverse Datenformate.

Über Rechtsklick  Eigenschaften können Eigenschaften der Datei angeschaut werden, bevor Sie ins Projekt geladen werden. Wichtig könnte der Raumbezug oder die Ausdehnung der Datei sein.

## Metadaten

Wenn im Katalog eine gewünschte Datei mit der rechten Maustaste angeklickt wird, lässt sich über die Auswahlmöglichkeit Metadaten anzeigen ein erster Blick auf die erweiterten Informationen der Datei werfen. Sofern die Datei vom Herausgeber editiert wurde, können im Reiter Metadaten bearbeiten Informationen über den Verfasser, Anwendbarkeit und Beschreibung der Daten erweitert werden. 

Falls noch keine Informationen vorhanden sind, können Sie welche eingeben. 

# Arbeiten in ArcGIS Pro

Im Kartenfenster und im Inhalt ArcGIS Pro findet die überwiegende Arbeit statt. Für Darstellung und Verarbeitung der Daten gibt es eine Vielzahl von Werkzeugen und Einstellungen.

## Datei- und Projektformate

ArcGIS Pro kennt eine Vielzahl an Formaten, welche jedoch erst im Zusammenhang mit größeren Projekten relevant sind. Daher an dieser Stelle nur eine Übersicht über die Formate, die im Verlauf des Kurses verwendet werden:





https://pro.arcgis.com/de/pro-app/latest/help/projects/supported-data-types-and-items.htm

Wichtig ist hierbei, dass die Projektdatei *.aprx alle externen Daten und interne Einstellungen verwaltet.

## Daten hinzufügen in ArcGIS Pro

Aus dem Register „Karte“, dort Gruppe „Layer“    Daten hinzufügen aus dem Menüband oder über den Button mit der gelben Raute fügen Sie dem Inhaltsverzeichnis GIS-Daten (Geodaten) hinzu. Unter Ordnerverbindungen finden Sie ihre Verknüpfung zu den Übungsdaten. 

Es ist einfacher, Geodaten per Drag-And-Drop aus dem Katalog oder dem Explorer ins Kartenfenster ziehen. 

Tipp:

In den meisten Fällen ist die Arbeit mit dem Katalog zu empfehlen!

Im Katalog können Sie schnell auf Projektdaten zugreifen und ArcGIS Pro zeigt für die Datentypen spezielle Symbole zu Unterscheidung an.

Anmerkung:

Im Windows Explorer werden Shapefiles mit allen zugehörenden Dateien (dbf, shx, prj) angezeigt. Ziehen Sie mit der Maus nur die SHP ins Projekt.

Anmerkung

Geodatabases können nicht über den Windows Explorer verwaltet werden, da nur ein Verzeichnis mit vielen Tabellen sichtbar ist. Dieses Verzeichnis und die Tabellen dürfen nicht auf Windows Explorer Ebene verändert werden.

Eine hinzugefügte Datei wird als Layer dargestellt. Es handelt sich bei diesem Vorgang nicht um einen Import der Daten, sondern um einen Verweis zur Datei auf der Festplatte.

Fügen Sie Ihrem Projekt folgende Dateien aus dem Ordner „LUBW“ hinzu; notieren Sie den feature-class-Typ:

"Spielen" Sie im Inhalt mit den Daten:



Schalten Sie einzelne Layer an/aus.

Schalten Sie die Legenden an/aus (+/-).

Ändern Sie die Reihenfolge der Layer durch Verschieben (drag&drop).

## Erstellen eines Kartendokuments *.aprx

Falls das Projekt ohne Vorlage erstellt wurde, muss eine Projektdatei erstellt werden. Da in dieser mit Vorlage gearbeitet wird, reicht es, hin und wieder auf „Speichern“ zu klicken!

Um nicht alle Shapefiles oder andere Daten nach Beenden des Projekte erneut in ArcGIS Pro laden zu müssen, erstellen wir eine Projektdatei welches die Pfade der geladenen Dateien, sowie deren Einstellungen und Darstellungen speichert.

Anmerkung

Die Dateien können mit vollständigem Pfad auf der Festplatte gespeichert werden. Das nennt man absolute Speicherung. Beim Wechsel der Projektdatei auf einen anderen Rechner oder in ein anderes Verzeichnis findet ArcGIS Pro die Daten so eventuell nicht mehr. In den früheren Versionen ArcMap und in anderen GIS Programmen ist das noch relevant. ArcGIS Pro hat eine völlig anderes Speicherkonzept und als Standard relative Pfade eingestellt.

Speichern Sie die aktuelle Projektdatei unter einem geeigneten Namen (BW) in Ihrem Arbeitsverzeichnis.

 Tipp

Die Projektdatei speichert nur die Anordnung und Darstellung der im Projekt verwendeten Daten, nicht jedoch die Daten selbst. Die Projektdatei zeigt dem Programm lediglich an, wo auf der Festplatte sich die verwendeten Daten befinden

## Koordinatensystem einstellen

Für jede Karte in einem Projekt kann ein anderes Koordinatensystem definiert werden, welches die enthaltenen Geodaten On the Fly projiziert. In den ersten Übungen arbeiten wir mit dem amtlich empfohlenen UTM32N, das die EPSG Nummer 25832 besitzt.

Mit Rechtsklick auf „Karte“ gelangen Sie in die Eigenschaften dieses Datenrahmens und unter „Koordinatensysteme“ kann ein gewünschtes Koordinatensystem gesucht werden. Geben Sie die EPSG Nummer in die Suchmaske ein und bestätigen Sie mit „OK“.

Falls schon Daten im Projekt existieren, zeigt ArcGIS Pro deren KBS zur Auswahl an, zusätzlich das Gesuchte. Bestätigen Sie „ETRS...“ mit „OK“.

## Eigenschaften der Karte

Über  Rechtsklick auf „Karte“ im Inhaltsverzeichnis erreichen Sie das Dialogfenster Karteneigenschaften. Hier werden die grundlegenden Eigenschaften eines Datenrahmens festlegt. Im Datenrahmen werden bestimmte Eigenschaften z.B. das Koordinatensystem für die enthaltenen Layer verwaltet.





Informationen zu den in der Liste nicht erwähnten, weniger oft benötigten Optionen finden Sie in der Hilfe.

https://pro.arcgis.com/de/pro-app/latest/help/mapping/properties



## Hinzufügen einer Grundkarte (Basemap)

Zur besseren Orientierung und als Hintergrundinformation sind Grundkarten, oft auch Basemap genannt, hilfreich. ArcGIS Pro bietet eine Auswahl solcher Karten standardmäßig an. Grundkarten sind Online-Karten, deshalb benötigen Sie eine Internetverbindung. Bei der Projekterstellung wurde eine voreingestellte Basiskarte geladen, falls gewünscht, können weitere dazu geladen werden.

Im Register „Karte“ können über den Button „Grundkarte“ mit dem DropDown Pfeil verschiedene Basiskarten geladen werden. Diese Karten stellt ESRI zur Verfügung. Es handelt sich dabei um eine ähnliche Technik, wie bei WMS / WMTS Diensten von anderen Datenprovidern.

Interessant ist die Basemap mit Luftbildern.

Weitere Einstellung, wie Transparenz oder maßstabsabhängige Sichtbarkeit, stellen Sie über das Register „Aussehen“ ein.

## Statusleiste

In der Statusleiste finden Sie ganz rechts unten einen Button zum Aktualisieren der Ansicht. Beim Laden einer Ansicht dreht sich das Symbol und Sie sehen das ArcGIS Pro arbeitet. 

In der Mitte sehen Sie die Koordinate der aktuellen Mausposition im eingestellten KBS. Falls noch nicht eingestellt, stellen Sie die Anzeige auf Meter.

Ganz links in der Statuszeile kann ein Ansichtsmaßstab eingestellt werden, der sich beim Zoomen wieder anpasst.

## Navigieren

Zur ersten Erkundung der Daten, zum Vergrößern von Ausschnitten und für einfache Abfragen bietet der Bereich „Erkunden“ auf der Registerkarte „Karte“ entsprechende Werkzeuge an.

Zeigen Sie auf dem Menüband auf der Registerkarte Karte in der Gruppe Navigieren mit der Maus auf das Werkzeug Erkunden . 

Verwenden Sie die Maus mit den beschriebenen Funktionen zum Erkunden der Daten.

Das Navigieren erfordert etwas Übung, mit der Zeit können Sie alleine mit der Maus die wichtigsten Operationen durchführen.

In der Gruppe „Navigieren“ finden Sie weitere Werkzeuge, z.B. den „Zurück“ Befehl um zur vorherigen Ausdehnung zu gelangen.

Die kleine Weltkugel zoomt zur gesamten Ausdehnung der Karte, wenn eine Basemap im Projekt ist, wird auf deren Ausdehnung gezoomt.

Sollten Sie die Orientierung verloren haben, finden Sie auf Ihr Untersuchungsgebiet zurück, indem Sie auf einen Layer im Inhaltsverzeichnis rechtsklicken und im Kontext Auf Layer zoomen aufrufen.

https://pro.arcgis.com/de/pro-app/latest/get-started/navigate-your-data.htm

## Tastenkombinationen

Mit Tastenkombinationen lässt sich für Geübte viel Zeit sparen. Auf der Seite von ESRI finden Sie die wichtigsten Informationen dazu:

https://pro.arcgis.com/de/pro-app/latest/get-started/arcgis-pro-keyboard-shortcuts.htm

## Messen

Im Register „Karte“ bei der Gruppe „Abfrage“ befindet sich das Werkzeug zum Messen. Führen Sie ein paar Entfernungsmessungen und Flächenmessungen durch, um mit der Funktion vertraut zu werden.

Suchen  und Zoomen Sie nach Tübingen und zu Ihrem Heimatort.

Zoomen Sie die Darstellung wieder auf die ursprüngliche Größe zurück.

## Darstellen von Daten am Bildschirm

In dieser Lektion werden wir uns einen Teil der Übungsdaten genauer ansehen, die Darstellung ändern und einfache Abfragen durchführen.

Finden Sie den Landkreis Tübingen; wählen Sie einen Bildausschnitt, der den gewählten Landkreis darstellt

Öffnen Sie die Attributtabelle des Layers „Naturschutzgebiete“ und untersuchen Sie, seit wann die Gebiete existieren (VO_Datum“.

Messen Sie die Entfernung zwischen Paris und Berlin – worauf müssen Sie in diesem Fall achten?



## Layereigenschaften

Laden Sie aus dem Ordner LUBW die Fließgewässerdatei hinzu. 

Durch Rechtsklick auf eine Datei im Inhaltsverzeichnis gelangt man in ein Menü, in dem zahlreiche Funktionen bezüglich des gewählten Layers aufgerufen werden können.

Mit Rechtsklick auf diesen Layer können Sie auf seine räumliche Ausdehnung zoomen.

 Wählen Sie die Option „Eigenschaften“.

Auch hier stehen wieder verschiedene Optionen zur Auswahl; einige werden im Verlauf des Kurses ausführlicher behandelt, daher hier nur eine kurze Übersicht:



Anmerkung

Anders als in ArcMap findet sich bei den Eigenschaften kein Reiter für die Symbolisierung.

Über Rechtsklick auf einen Layer (Kontextmenü) erreichen Sie schnell die Symbolisierungseinstellungen und die Möglichkeit Daten zu exportieren.

Symbolisierungseinstellungen befinden sich auch im Menüband „Aussehen“ im Bereich „Symbolisierung“.

### Allgemein

Rechtsklicken Sie das Shapefile <Naturschutzgebiete> und wählen Sie Eigenschaften> Allgemein.

Ändern Sie den Namen auf "NSG", klicken sie auf OK. Schauen Sie im Katalog nach. Was fällt auf?

Wählen Sie als minimalen Maßstab 1:4000.000, als maximalen Maßstab 1:1.000. Betrachten Sie den Layer, zoomen Sie hinein und hinaus. Was fällt auf?

Die maßstabsabhängige Darstellung kann auch über das Menüband bei „Aussehen“ eingestellt werden.

Tipp: 

Sie können Layer-Namen auch über das Drücken der F2-Taste ändern

Tipp

Hier können nun auch Sonderzeichen eingegeben werden, die Angabe hat keinen Einfluss auf die Datei auf der Festplatte.

### Quelle

In diesem Reiter können Sie u..a. das Koordinatensystem der Datei kontrollieren und mit dem Datenrahmen vergleichen.

Änderungen des KBS sind hier nicht möglich.

### Anzeige

Rechtsklicken Sie das Shapefile <NSG> und wählen Sie EIGENSCHAFTEN > Anzeige.

Aktivieren Sie die Option "Map-Tips anzeigen"  . Klicken Sie OK. Verändern Sie das anzuzeigende Feld auf „Objekt“.

Schalten Sie die Transparenz auf 50% indem Sie die Einstellung im Menüband „Aussehen“ vornehmen.

Wie hat sich das Bild verändert? Wann kann diese Einstellung (Transparenz) Sinn machen? Was geschieht, wenn Sie mit dem Mauszeiger über die Karte fahren?

## Symbole und Symbolisierung

In der Kartenansicht können Sie die Daten darstellen, auf vielfältige Weise. Später werden diese Darstellungen ins Layout übernommen. Vertiefende Informationen erhalten Sie in der Hilfe:

https://pro.arcgis.com/de/pro-app/latest/help/mapping/layer-properties/symbolization.htm

### Symbolauswahl (Einzelsymbol)

Mit der Symbolisierung können Sie Ihren Objekten verschiedene Symbole zuordnen. Klicken Sie dazu einfach im Inhaltsverzeichnis auf das Symbol eines Objektes im vorhanden Layer, welches Sie ändern möchten. Wählen Sie nun ein Symbol aus. Unter Galerie finden Sie eine Vielzahl vordefinierter Symbole zu verschiedensten Thematiken. Unter  -Eigenschaften haben Sie die Möglichkeit neue Symbole zu entwickeln oder bestehende zu verändern.. 

Die Einstellungen nehmen Sie für die geladenen Layer entsprechend ihrer Bedeutung vor.

Weisen Sie den Naturdenkmalen, Einzelgebilde ein geeignetes Symbol zu. Beispielsweise „Park“ 

### Symbolisierung (Thematische Karte)

Anhand der Informationen aus den Sachdaten kann eine gestalterische Differenzierung eines Datensatzes eingestellt werden. Dazu werden die Werte der Tabellen abgefragt und die Darstellung (Farben, Linienart  und -stärke) danach definiert.

Es ist ratsam, zunächst die Inhalte der Sachdaten zu untersuchen. Dazu öffnen Sie die Attributtabelle über einen Rechtsklick auf den Layer. Die Tabelle kann geöffnet bleiben.

Durch eine Symbolisierung wird festgelegt, wie die Bestandteile eines Layers dargestellt werden. Da die Lesbarkeit einer Karte sehr stark von farblichen Gestaltung bzw. der Symbolvergabe abhängt, lohnt es, sich näher mit diesem Punkt zu beschäftigen!

Es existieren verschiedene Primäre Symbolisierungen (Darstellungsmethoden):

Informationen zu den in der Liste nicht erwähnten, weniger oft benötigten Optionen (Diagramme, Mehrfachattribute) finden Sie in der Hilfe:

https://pro.arcgis.com/de/pro-app/latest/help/mapping/layer-properties/symbolize-feature-layers.htm

Stellen Sie die Biotope nach „BIOTOPTY02“ durch kategorisierte Einzelwerte dar. Übernehmen Sie zunächst die zufällige Farbauswahl. Später können Sie für ein Layout mit den Farben experimentieren.



Stellen Sie die „Mähwiesen“ auf Grundlage der Fläche farblich differenziert dar. Teilen Sie die Mähwiesen dabei in 6 Klassen ein. Wählen Sie als statistisches Verfahren zur Klassifizierung "Natürliche Unterbrechungen“. Wählen Sie einen Farbverlauf von dunkelgrün nach hellgrün.

## Beschriftungen

Wählen Sie nochmals das Shapefile „NSG“ und aktivieren Sie Beschriftungen. ArcGIS Pro versucht automatisch in der Tabelle ein Feld zu finden, mit dem eine Standardbeschriftung eingestellt wird. Mit „Beschriftungseigenschaften kann festgelegt werden, mit welchem Attribut die Objekte des Layers beschriftet werden sollen. Die Formatierung der Beschriftung ist ähnlich, wie in Textverarbeitungen.

Wählen Sie nun die Registerkarte „Beschriftungen“, aktivieren Sie „Beschriftung“ und wählen Sie „Objekt“ als Feld. 

Detaillierte Eigenschaften können über einen Rechtsklick auf den Layer mit „Beschriftungseigenschaften“ eingestellt werden.

Dynamische Beschriftung, vor allem, wenn es sich um sehr viele Features handelt, kann eine Herausforderung sein. Das Programm biete eine Fülle von Optionen zur Platzierung, wir beschäftigen uns im Modul Kartographie damit. 

# Sonstige Darstellungsoptionen

Es gibt in ArcGIS Pro einige Hilfsmittel, die die Arbeit erleichtern können.

## Ausblenden

Oft kommt es vor, dass ein obenliegender Layer andere Daten überdeckt. Mit dem Werkzeug „Ausblenden“ kann ein verdeckter Layer sichtbar gemacht werden

## to be continued…

Sammeln Sie hier Werkzeuge, die Ihnen helfen, mit ArcGIS Pro komfortabler zu arbeiten.

Gerne dürfen Sie diese Tipps auch im Forum teilen.

# Fazit

Sie können nun ein Projekt erstellen, Daten laden und symbolisieren sowie Beschtiftungen definieren.

Im Folgenden geht es um die Arbeit mit Geodatabases (FGDB), Geoverarbeitung und um das Layout.

Mit diesen jeweiligen Übungen vertiefen Sie die Arbeit mit ArcGIS Pro.



Viel Spaß

--------------------------------------------------------------------------------------------------------------------------

Erstellt:

Jörg Knödler

erstellt: 30.04.2022

aktualisiert: 14.04.25

Jörg Knödler

Dateiname: M1_Einführung_ArcGIS_Pro2023-05-06.odt



