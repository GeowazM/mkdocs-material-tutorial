# Übung Layout - Kartenerstellung

---

## Niederschlagskarte für Deutschland


---

# 1 Vorbemerkungen und Ziele

Karten sind allgegenwärtig und unabdingbar für die greifbare Darstellung von räumlichen Informationen und Zusammenhängen. GIS verfügen in der Regel über Werkzeuge, um räumliche Daten in Form von Karten präsentieren zu können. Für die Kartenerstellung werden keine räumlichen Analysewerkzeuge verwendet, sondern Grafikwerkzeuge, die eventuell schon aus Photoshop oder GIMP geläufig sind.

Zur Erstellung von veröffentlichungsfähigen Karten sind einige Kartenelemente unverzichtbar, wie beispielsweise Maßstab, Nordpfeil, Legende, Quellenangaben, Autorenangaben, Koordinatengitter usw.

**Abbildung 1:** Beispielhafte Kartenelemente für die Erstellung veröffentlichungsfähiger Karten.  
Quelle: www.spektrum.de/lexikon/kartographie-geomatik/kartenbestandteile/2573

Folgende Themen werden vertieft:  
- Erstellung einer ersten veröffentlichungsfähigen Karte

# 2 Verwendete Daten

**Ordner:** Uebung_Layout

- Gewaesser_Dtld_Clip.shp  
- DTLD_NUTS_annual_prec.shp  

**Abbildungen:**  
Soweit nicht anders gekennzeichnet, handelt es sich bei den Abbildungen in diesem Skript um Screenshots der aufgeführten Software oder sie wurden aus dem ESRI ArcGIS Resource Center entnommen.

---

# 3 Daten

Für die Erstellung der Karte wird ein Shapefile-Datensatz im Ordner „Karte“ verwendet. Dieser Datensatz stellt die Niederschlagsverteilung in der Bundesrepublik Deutschland dar. Auf Grundlage von Stationsdaten des Deutschen Wetterdienstes (DWD) wurde dieser Niederschlagsdatensatz erstellt. Die zugrunde liegenden Beobachtungsdaten können über folgende URL beim Climata Data Centre (CDC) heruntergeladen werden:  
https://cdc.dwd.de/portal/

Zudem wird zur Vereinfachung der Orientierung das Gewässernetz in Deutschland eingebunden. Dieser Datensatz stammt vom Eurostat und kann unter folgender URL bezogen werden:  
https://ec.europa.eu/eurostat/de/web/gisco/geodata/reference-data/elevation/eu-dem/hydrography-etrs1989

---

# 4 Vorbereitung des Niederschlagsdatensatzes

Bei der Erstellung von Karten im GIS gibt es eine empfehlenswerte Vorgehensweise: Zunächst werden in der Projektumgebung sämtliche Layer in der Anordnung und Symbologie vorbereitet. Sobald diese Karteninhalte vorbereitet sind, wird dann im zweiten Schritt das Kartenlayout gestaltet.

---

# 5 Layout-Legung der Karte

Zunächst werden die vorgesehenen Datensätze in ein neues Projekt geladen. Speichern Sie das Projekt unter „Layout“ ab.

Laden Sie die folgenden Datensätze aus dem Übungsordner „Layout“:  
- Gewaesser_Dtld_Clip.shp  
- DTLD_NUTS_annual_prec.shp

Bereits im Karten-Menü wird die Reihenfolge der einzelnen Layer und die Symbologie für die einzelnen Datensätze definiert.  
Bringen Sie die Layer in eine sinnvolle Reihenfolge und weisen Sie den Layern eine geeignete Symbologie zu. Die Symbologie, die Sie in diesem Schritt festlegen, wird später in der Karte dargestellt. Der Datensatz „1000_NUTS1.shp“ soll dazu dienen, die administrativen Grenzen der einzelnen Bundesländer zu verdeutlichen.

Achten Sie auf die Verwendung einer geeigneten Symbologie. Welche Farbverläufe werden mit Niederschlag assoziiert? Wird besser ein einfarbiger oder mehrfarbiger Farbverlauf verwendet?

---

## Wichtige Layout-Funktionen

- **Register Einfügen > Gruppe Projekt > Werkzeug Neues Layout** – Fügt neues Layout-Fenster hinzu (siehe Abbildung 2)

**Abbildung 2:** Initiierung eines neuen Kartenlayouts über "Neues Layout"

Im Layout-Menü:  
- Kartenrahmen – Fügt dem Layout die Kartenansicht hinzu  
- Nordpfeil  
- Maßstabsleiste  
- Legende  
- Dynamischer Text > Maßstab

**Abbildung 3:** Menü zum Einfügen von Kartenelementen zum Kartenlayout.

- **Register Layout > Gruppe Karte > Werkzeug Aktivieren** – Ermöglicht das Bearbeiten des angezeigten Kartenausschnitts, z.B. verschieben oder ändern des Maßstabs (siehe Abbildung 4)

**Abbildung 4:** Die "Aktivieren"-Funktion erlaubt die Anpassung des Karteninhalts.

- **Register Freigeben > Gruppe Ausgabe > Werkzeug Layout exportieren** – Export in die meisten gängigen Grafikformate wie JPG, PNG oder PDF (siehe Abbildung 5)

**Abbildung 5:** Über die Exportfunktion werden Kartenlayouts in Grafiken konvertiert.

---

Erstellen Sie nun eine veröffentlichungsfähige und ansehnliche Karte im DIN A4-Format. Bauen Sie dazu bitte folgende Kartenelemente in Ihr Layout ein:

- Titel  
- Maßstabsleiste  
- Maßstabszahl  
- Koordinatengitter  
- Nordpfeil  
- Legende  
- Autorenangaben, Quellenangaben  
- Projektionsinformationen  

Sie können jedes Kartenelement mit Rechtsklick anwählen und über die „Eigenschaften“ konfigurieren und an Ihr Layout anpassen.

Exportieren Sie die fertig gestellte Karte sowohl im PDF- als auch im JPG- oder PNG-Format. Können Sie Unterschiede in den Formaten erkennen?

---