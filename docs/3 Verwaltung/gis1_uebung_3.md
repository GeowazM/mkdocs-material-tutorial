CAS Geographische Informationssysteme

Modul: GIS 1

Bemerkungen zur Datenverwaltung 


??? abstract "Inhaltsverzeichnis"

    1   Datenorganisation

    1.1  Grundsätze

    1.2  Datenverwaltung auf Betriebssystemebene

        1.2.1  Gepackte Daten

        1.2.2  Fremde Daten

        1.2.3  Projektdaten

    1.3  Projektverwaltung ArcGIS Pro

        1.3.1  Katalog

        1.3.2  Dateibasierte Geodaten

        1.3.3  Datenbankbasierte Geodaten


??? abstract "Abbildungsverzeichnis"

    Abbildung 1: Vergleich ZIP-Dateien

    Abbildung 2: Beispielordner für Geodaten

    Abbildung 3: Projektordner

    Abbildung 4: ArcGIS Pro Projekt unter Windows

    Abbildung 5: Projekt erstellen

    Abbildung 6: Katalog mit Projektstruktur

    Abbildung 7: Shapefile Einzeldateien unter Windows

    Abbildung 8: Feature-Classes im Dataset


# Datenorganisation

Die Datenorganisation bei vielen Daten ist wichtig, um die Übersicht zu behalten und um Probleme zu vermeiden, wenn ein Projekt in ein anderes Verzeichnis oder auf einen anderen Rechner übertragen wird.

## Grundsätze

Geodaten sollten einen eigenen Ordner bekommen, am besten auf einer zweiten Festplatte oder einer zweiten Partition. Dies erleichtert auch das Backup. 
Sollte dies nicht möglich sein, und das Benutzer (user) Verzeichnis von Windows verwendet werden, sollte der Pfad als zusätzliches Wurzelverzeichnis nutzbar gemacht werden.

Dieser Ordner muss volle Zugangsrechte besitzen.

Nicht auf einer externen Festplatte oder gar auf einem Stick speichern! Externe Geräte nur zum Transport der Daten verwenden.

Pfade und Dateinamen sollten keine Umlaute, Sonderzeichen und Leerzeichen enthalten. Moderne Systeme können zwar damit umgehen, trotzdem kann es immer wieder vorkommen, in Vertiefungen dann bei Datenbanken oder Web-GIS, dass Probleme auftauchen.

Möglichst keine Redundanzen zulassen.

## Datenverwaltung auf Betriebssystemebene

Viele Daten kommen aus Downloads oder werden als ZIP bestellt und geliefert. Oft werden diese Basisdaten in mehreren Projekten verwendet.

### Gepackte Daten

Gepackte Daten werden entpackt, bevor sie in der Software verwendet werden. Bitte immer entpacken, auch wenn Sie im Katalog trotzdem angezeigt werden. Je nach Packprogramm kann eingestellt werden, dass die Daten aus dem ZIP jeweils in ein eigenes, neues Verzeichnis entpackt werden. Das ist sinnvoll, wenn zunächst viele ZIP-Dateien in einem Ordner liegen. 

Achtung: ZIP-Dateien enthalten manchmal noch einen oder mehrere Unterordner. Beim Entpacken werden diese Verzeichnisse dann mit angelegt. Siehe LGL BW Verwaltungseinheiten neu (mit Ordner), aber Verwaltungseinheiten alt (ohne Ordner).

Beispiel LGL: Links ohne Ordner, rechts mit Ordner!

Deshalb vor dem Entpacken in die ZIP „reinschauen“ und analysieren, wie die Struktur ist. Unter Windows kann mit einem Doppelklick die ZIP geöffnet werden.

### Fremde Daten

Fremde Daten, sowohl, Basisdaten, als auch Fachdaten, sollten in jeweils einem Ordner gespeichert werden, Extraktionen davon werden dann in den Projektordnern verwaltet. 

Alternativ können Extraktionen auch in entsprechenden Unterordnern gespeichert werden, beispielsweise, wenn grundsätzlich landesweite Daten auf Landkreise oder Gemarkungen zugeschnitten werden.

Sinnvoll ist z.B. die Daten der LUBW in einem Ordner „LUBW“ zu speichern, dort eventuell weitere Unterordner anlegen.



### Projektdaten

Spezielle projektbezogene Dateien kommen in den Projektordner, dort in einen eigenen Unterordner, beispielsweise „Eingang2022_05_23“, oder „EingangALKIS“

Diese Daten werden in der Regel nicht von anderen Projekten benötigt.


## Projektverwaltung ArcGIS Pro

ESRI hat mit der Software ArcGIS Pro die Projektverwaltung von GIS Projekten erweitert. Beim Erstellen von neuen Projekten mit Vorlage wird eine eigene Projektstruktur angelegt. 

Der Projektordner erhält neben dem Projektnamen „Projekt.aprx“ in seinem Stammordner:

eine Toolbox für eigene Werkzeuge, zunächst leer eine Geodatabase, zunächst leer. Im WIN-Explorer als Ordner dargestellt weitere Ordner für Backup, Import und Index


Am Beispiel in der Abbildung wurde in „Beispielordner“ das „Projekt3“ angelegt. Wichtig ist der Haken bei „Einen neuen Ordner... erstellen“

Ist „Projekt3“ als Ordner schon vorhanden, wird die ArcGIS Pro Struktur eingebunden.


### Katalog

Im Katalog von ArcGIS Pro erscheint „Projekt3“ als „Home“-Ordner, mit einem Logo für die „Home“-GDB und mit einem Logo für die „Home“ Toolbox. Toolbox und GDB sind nach Erstellung des Projektes noch leer.

Über einen Rechtsklick auf „Ordner“ können weiter Ordner von verfügbaren Festplatten oder anderen Orten, z.B. Clouds hinzugefügt werden. So kann schnell auf Daten außerhalb des Projektes zugegriffen werden, z.B. den Ordner für Basisdaten.


### Dateibasierte Geodaten

Shapefiles (SHP) ist ein dateibasiertes Geodatenformat. In einer SHP kann eine Featureclass eines Datentyps gespeichert werden. SHP sind weit verbreitet, deshalb gelten sie als „Standard“. Viele Datenprovider geben Ihre Daten als SHP ab. Leider besitzt das Format Restriktionen und ist nicht mehr zeitgemäß. Ein Shapefile besteht aus mehreren Einzeldateien, die im Windows-Explorer auch so angezeigt werden


Im Katalog von ArcGIS Pro wird dagegen nur eine Datei mit einem Symbol angezeigt.


### Datenbankbasierte Geodaten

Geodatabases (GDB), auch die File-GDB ist ein datenbankbasiertes Geodatenformat. Es ist modern, hat nicht mehr die Restriktionen, wie SHP und wird von ESRI empfohlen. In einer FGDB können viele Feature- Classes gespeichert werden. 

IN FGDB gibt es weitere „Container“, die Datasets, die zur Organisation bzw. Gliederung der Feature-Classes nutzbar sind. In Feature-Datasets werden Vektordaten gespeichert.

In den Datasets werden neue Feature-Classes erstellt oder externe Daten, z.B. SHP importiert.

Einem Dataset wird ein KBS zugeordnet, beim Import externer Daten wird gegebenenfalls in dieses KBS projiziert.

Im Katalog erscheint dann ein Symbol für die FGDB mit Symbolen für die Datasets und den Symbolen für die einzelnen Feature-Classes.

In einer FGDB können somit alle Projektdaten gespeichert werden. Thematisch kann innerhalb der FGDB mit Datasets zusätzlich eine Ordnungsstruktur erstellt werden.

Rasterdaten können ebenfalls in einer GDB gespeichert werden. Dazu ist eine intensive Kenntnis von Rasterdaten notwendig.

Für weitere Informationen zur Datenverwaltung in Geodatabases:

https://pro.arcgis.com/de/pro-app/latest/help/data/geodatabases/overview/what-is-a-geodatabase-.htm

