# CAS Geographische Informationssysteme
# Rasterdaten

## 3D-Modell des Hambacher Forsts


# 1. Vorbemerkungen und Ziele

Digitale Geländemodelle (DGM) sind für die Analyse geomorphologischer, hydrologischer und anderer räumlicher Prozesse eine essenzielle Datenquelle. Globale DGMs werden durch US-amerikanische Behörden kostenfrei zur Verfügung gestellt. Jedoch weisen diese DGMs eine räumliche Auflösung von 30m auf (SRTM). Dadurch können Details für kleinräumige Analysen nicht dargestellt werden. Um hoch- und höchstaufgelöste DGMs zu generieren, werden u.a. Laserscan-Daten herangezogen, die während Flugzeugbefliegungen erfasst werden. Durch die Laufzeit des Lasers zwischen Sensor, der reflektierenden Oberfläche und zurück zum Sensor kann auf die Geländehöhe geschlossen werden. Diese sogenannten LiDAR (Light Detection And Ranging)-Daten werden von den Landesämtern für Geoinformation in Textform zur Verfügung gestellt, mit einer räumlichen Auflösung von einem Höhenpunkt/m². Sie bekommen diese Daten im Original und als abgeleitete Produkte in verschiedenen Auflösungen von 1m bis 50m.

Um aus diesen Punktdaten flächenhafte DGMs als Rasterdaten zu erhalten, müssen Interpolationsverfahren angewandt werden. Diese Verfahren schätzen unbekannte Werte auf Grundlage der räumlichen Verteilung und Eigenschaften von bekannten Messpunkten.

Dies wird in der folgenden Übung anhand von Testdaten des Landesamtes für Geoinformation und Landentwicklung (LGL) durchgeführt, um weitere höhenabhängige Produkte aus dem DGM ableiten zu können.

In dieser Übung verwenden wir einen Datensatz mit **5m Auflösung**.

**Folgende Themen werden vertieft:**
- Datenrecherche Internet
- Vektordatengenerierung aus Tabellenimport
- Interpolation
- Isohypsen ableiten
- Schummerung erstellen
- Hangneigung berechnen
- Geländeexposition berechnen


# 2. Verwendete Daten

**Ordner:** Geodaten/LGL/3D

- DGM_5m_GRIDXYZ_UTM_xyz.zip (`DGM5_GRIDXYZ_UTM_DTMBIN1UTM_512800_5452000_dtm.xyz`)

**WMS:**
- <http://ows.terrestris.de/osm/service?>
- <https://owsproxy.lgl-bw.de/owsproxy/ows/WMS_Maps4BW?>
- <http://sgx.geodatenzentrum.de/wms_topplus_open?>

**Abbildungen:**  
Soweit nicht anders gekennzeichnet, handelt es sich bei den Abbildungen in diesem Skript um Screenshots der aufgeführten Software oder sie wurden aus dem ESRI ArcGIS Resource Center entnommen.

---


---

### Datenrecherche im Internet

Die jeweiligen Landesämter für Geoinformation stellen Laserscan-Höhenmodelle als Punktdaten zur Verfügung. Abhängig vom Bundesland werden die Höhenmodelle als Textdateien oder LAS-Datensätze ausgeliefert. Traditionellerweise werden hochpräzise Geländemodelle kommerziell vertrieben, im Rahmen der OpenData-Initiativen werden diese immer mehr kostenfrei zur Verfügung gestellt. Baden-Württemberg hinkt dieser Bewegung weit hinterher, aus diesem Grund werden Daten aus Nordrhein-Westfalen verwendet, wo sie landesweit kostenlos beziehbar sind. Unter anderem werden diese DGM-Daten auf der folgenden Website zum Download bereitgestellt:

- <https://www.geoportal.nrw/>

---

# 3. Vektordatengenerierung

Bei der Betrachtung des Datensatzes wird ersichtlich, wie die Datei strukturiert ist. Für jedes Koordinatenpaar wird ein Höhenwert angegeben.

> **Frage:**  
> Auf welches Koordinatensystem beziehen sich die angegebenen Koordinaten?

So wie der DGM-Datensatz entpackt wurde, ist er noch nicht in ArcMap verwendbar. Zum einen werden diese Formate durch das Programm nicht auf die übliche Weise erkannt und können daher nicht über den Katalog importiert werden.

---

# 4. LAS-Daten

Das LAS-Format ist Standard für die Bereitstellung von Laserscan-Daten bzw. dreidimensionalen Punktwolken. Im LAS-Format sind Höheninformationen als Punktinformationen vorgehalten, die durch X-, Y- und Z-Koordinaten definiert sind. Neben dem Koordinaten-Triple sind zusätzlich noch Attributinformationen zu jedem Höhenpunkt hinzugefügt (z.B. Reflektionsanzahl, Farbwerte, Konfidenzinformation, Einfallswinkel). Diese Informationen haben für die weitere Interpretierbarkeit der Daten erhebliche Relevanz.

Laserscandaten können beispielsweise die Vegetation durchdringen bzw. an verschiedenen Stellen in der Vegetation reflektiert werden, wodurch Informationen über Vegetationshöhen und tatsächliche Oberflächenhöhe abgeleitet werden können.

**Abbildung 1:** Lidar-Reflektionen an einem Baum.

- Aus den ersten Reflektionen werden sogenannte **Digitale Oberflächenmodelle (DOM)** abgeleitet, die die Höhen von Objekten über dem Bezugsellipsoiden darstellen.
- Aus der letzten Reflektion wird das **Digitale Höhenmodell (DHM)** abgeleitet, welches Bodenhöhen darstellt.

---

# 5. Daten hinzufügen

LAS-Daten werden über den Katalog durch Doppelklick oder per Drag&Drop dem Projekt hinzugefügt.

- Navigieren Sie im Catalog zum Datenverzeichnis der aktuellen Übung und fügen Sie wie oben beschrieben die beiden vorhandenen LAS-Datensätze dem Projekt hinzu.
- Erkunden Sie beide Datensätze. Können Sie Unterschiede in den Datensätzen erkennen?
- Beschreiben Sie, was Sie sehen.

**Abbildung 2:** Hambacher Tagebau dargestellt über einen LAS-Datensatz.

---

# 6. 3D-Visualisierung

ArcGIS Pro ist in der Lage, Punktwolken und andere räumliche Datensätze dreidimensional darzustellen. Im Kartenmenü werden Daten nur planar dargestellt, daher muss eine sogenannte „Szene“ erstellt werden. Im Szenenmodus kann die Perspektive frei geändert werden:

- Register Projekt > Gruppe Projekt > Werkzeug Neue Karte > Neue lokale Szene

Fügen Sie Ihrem Projekt eine neue lokale Szene hinzu.  
Die LAS-Datensätze werden nun per Drag-and-Drop aus Ihrem Projekt-Inhalt oder aus dem Katalog der Szene hinzugefügt.

Die Navigation im Szenenmodus erfolgt mit gedrücktem Mausrad zum Wechseln der Perspektive und mit gedrückter linker Maustaste zum Verschieben des Ausschnitts.

---

# 7. Rasterisierung

Höhenbasierte Bearbeitungsansätze beruhen auf Höhenmodellen, die im Rasterformat vorliegen. Um räumlich kontinuierliche Rasterdatensätze aus den Punktdaten zu erhalten, muss man sich Rasterisierungsmethoden bedienen, die meist auf Interpolationsansätzen beruhen. Diese schätzen unbekannte Werte auf Grundlage bekannter Einzelpunkte. ArcGIS Pro bietet dazu verschiedene Interpolationsmethoden an. Diese sind in der ArcToolbox unter Spatial Analyst Tools > Interpolation eingeordnet.

Zur Bearbeitung von LAS-Datensätzen stehen spezielle Werkzeuge zur Verfügung.

Wechseln Sie zurück in das Karten-Menü und öffnen Sie das Werkzeug **„LAS-Dataset in Raster“** in der Toolbox unter Conversion Tools > Punktwolke.  
Definieren Sie als Eingabedatensatz `LAS_Hambach_merge_last.las`, geben Sie als Ausgabedatensatz `Hambach_DHM` an. Vergewissern Sie sich, dass die Information **„Höhe“** interpoliert wird. Geben Sie nun noch unter Abtastwert **„2“** ein, um diesen Wert als räumliche Zielauflösung festzulegen.

> **Hinweis:**  
> Je nach Größe des Eingabedatensatzes und verwendeter Hardware kann die Prozessierung einige Minuten in Anspruch nehmen.

Das Interpolationsergebnis stellt nun ein Raster dar, in dem jede Rasterzelle einen Höhenwert beinhaltet.

**Abbildung 3:** Digitales Geländemodell als Interpolationsergebnis aus LAS-Daten.

---

## Rasteranalysen: Isohypsen

Für kartographische Darstellungen ist die Darstellung der Höheninformation häufig von sehr großer Bedeutung. Jedoch soll die Höheninformation keine Inhalte überdecken oder verdrängen. Daher werden Höheninformationen oft nicht direkt über DGM in ihrer Rohform transportiert, sondern über alternative Möglichkeiten. Ein Ansatz ist die Erstellung von Höhenlinien, den sogenannten **Isohypsen**. Dabei handelt es sich um Linien gleicher Höhe, die in einem definierten Intervall errechnet werden können. Sie kennen diese Darstellung aus Landkarten.

Unter Spatial Analyst Tools – Oberfläche sind Werkzeuge eingebunden, anhand derer Oberflächenanalysen durchgeführt werden können. Darunter ist auch das Tool **„Konturlinie“**, womit Isohypsen abgeleitet werden können.

Verwenden Sie für die weiteren Arbeitsschritte die Datei `Hambach_DHM`.  
Wählen Sie das Werkzeug **„Konturlinie“** aus. Im Dialog geben Sie als Eingaberaster die Datei `Hambach_DHM` an. Geben Sie als Ausgabedatei `DHM_Hambach_Isohypsen` in Ihrem Arbeitsverzeichnis ein. Hierbei wird ein Linien-Vektordatensatz erstellt.  
Als Konturintervall wird der Höhenabstand der Isohypsen definiert, in dieser Übung sollen die Höhenlinien einen Abstand von **25 Metern** haben. Die weiteren Angaben können übernommen werden.  
Führen Sie die Berechnung durch.

Isohypsen werden standardmäßig als reine Linien dargestellt. Diese sind zunächst noch sehr „wild“ und verrauscht dargestellt. Für kartographische Aspekte muss immer zwischen gestalterischer Ästhetik/Lesbarkeit und der Exaktheit der dargestellten Inhalte abgewägt werden. Vielleicht haben Sie dazu schon von dem Begriff **„Generalisierung“** gehört.

Im Folgenden sollen die Isohypsen geglättet werden, um ein schöneres Bild abzugeben. Dabei geht natürlich ein gewisser Grad an Exaktheit verloren. Hierfür bietet uns ArcGIS Pro das Werkzeug **„Linie glätten“** an, das in der Toolbox unter Cartography Tools > Generalisierung zu finden ist.

Glätten Sie die Isohypsen aus dem vorhergegangenen Bearbeitungsschritt. Verwenden Sie eine Glättungstoleranz von **50 Metern**.  
Weisen Sie einen Ausgabenamen Ihrer Wahl zu und führen Sie ohne weitere Anpassung der Parameter die Berechnung durch.

Öffnen Sie nun die Attributtabelle des erzeugten Datensatzes. Finden Sie die Spalte mit den Höhenangaben?

Für die kartographische Darstellung der Isohypsen wäre somit noch eine Beschriftung nötig.  
Dazu bietet ArcGIS Pro ein sehr übersichtliches Menü an. Selektieren Sie im Inhaltsverzeichnis den Isohypsen-Datensatz und wechseln Sie auf das **„Beschriftung“-Register**:

**Abbildung 4:** Label-Menü zum Definieren der Layerbeschriftungen.  
Im gelben Kasten wird das Labeling (de-)aktiviert, im dargestellten roten Kasten wird die Spalte der Attributtabelle ausgewählt, die als Beschriftungsgrundlage dient. Im blauen Bereich wird die Schriftart definiert. Im grünen Bereich wird die Positionierung der Label bestimmt.

Folgen Sie für die Übung den Hinweisen aus Abbildung 4.  
Aktivieren Sie die Beschriftung für den Höhenliniendatensatz und wählen Sie dazu die entsprechende Spalte mit den Höhenangaben der Attributtabelle aus.  
Wählen Sie die korrekte Platzierung für die Höhenlinien.  
Weisen Sie eine geeignete Schriftart und Schriftstil zu.

> **Weshalb ist die korrekte Platzierung der Höhenlinien von Bedeutung?**

**Abbildung 5:** Digitales Geländemodell mit gelabelten Isohypsen.

---

## Rasteranalyse: Schummerung

Eine zweite Möglichkeit, Höheninformationen kartographisch darzustellen, bietet die **Schummerung**. Bei der Schummerung wird eine Rasterdatei erzeugt, die eine Sonnenbeleuchtung der Geländeoberfläche simuliert und als Ergebnis Beleuchtungs- und Schattenverhältnisse darstellt, die sogenannte Schummerung.

ArcGIS Pro bietet zwei Optionen für die Erstellung der Schummerung an:
- Symbologieanpassung bei der Darstellung von digitalen Geländemodellen
- Berechnung der Schummerung als separaten Datensatz

**Erzeugung der Schummerung durch Symbologieanpassung:**  
ArcGIS Pro kann auf Basis von DGM „on the fly“ Schummerungsdaten darstellen. Dabei wird kein neuer Datensatz berechnet bzw. physikalisch erzeugt, sondern nur das DGM als Schummerung dargestellt.

Selektieren Sie im Inhaltsverzeichnis das DGM `Hambach_DHM` und wechseln Sie in das Symbologie-Menü. Wählen Sie als primäre Symbologie **„Geschummertes Relief“**, um die Schummerung zu erzeugen. Durch den Azimutwert wird der Sonnenstand definiert, über Höhe wird die Sonnenhöhe definiert.

Lassen Sie sich sowohl die traditionelle als auch die multidirektionale Schummerung ausgeben.

> **Wie unterscheiden sich beide Schummerungsarten?**

**Abbildung 7:** Schummerungsdarstellung des Hambacher Tagebaus in ArcGIS Pro.  
Links: Traditionelle Schummerung, rechts: multidirektionale Schummerung.

Die Darstellung der Schummerung kann wieder rückgängig gemacht werden, sodass der Ausgangszustand mit angezeigten Höhen wieder hergestellt wird.

**Berechnen der Schummerung:**  
Unter Spatial Analyst Tools > Oberfläche > Schummerung kann ein neuer Schummerungsdatensatz errechnet werden. Die Vorgehensweise ist identisch mit dem oben beschriebenen Ansatz der Schummerungsdarstellung, nur wird hier ein neuer Datensatz erzeugt.

Erstellen Sie einen Schummerungsdatensatz auf Basis des DGM `Hambach_DHM`. Modellieren Sie in diesem Fall bitte zusätzlich die Schatten. Benennen Sie den Ausgabedatensatz `Hambach_DHM_Schummerung_Schatten`.

Vergleichen Sie das errechnete Ergebnis mit einer Schummerung, die über die angepasste Symbologie erstellt wurde.  
> **Wie wirkt sich die Option „Schatten modellieren“ auf das Ergebnis aus?**

Das DGM und der erstellte Schummerungsdatensatz lassen sich kombiniert darstellen.  
Weisen Sie dem DGM zunächst einen geeigneten Farbverlauf zu.

Da grundsätzlich jedoch im Inhaltsverzeichnis oben liegende Layer darunter liegende Layer überdecken, muss hier mit Tricks gearbeitet werden. Die erste Möglichkeit ist die Zuweisung eines Transparenzfaktors für den oben liegenden Datensatz.

Vergewissern Sie sich, dass der Schummerungsdatensatz über dem DGM liegt. Sowohl DGM als auch Schummerung sollten aktiviert sein.

Selektieren Sie den Schummerungsdatensatz und wechseln Sie in das Register **Raster-Layer > Gruppe Effekte > Werkzeug Layer-Verschmelzung**. Dort finden Sie den Regler für die Transparenz des selektierten Datensatzes.  
Wählen Sie hier eine Transparenz, die eine angenehme Überlagerung von DGM und Schummerung ermöglicht.

Eine zweite Möglichkeit der kombinierten Darstellung von zwei Datensätzen wird durch sogenannte Überblendungsfunktionen ermöglicht. Diese Verfahren kommen aus der digitalen Bildverarbeitung und können über mathematische Operationen umgesetzt werden.

Setzen Sie die Transparenz zurück auf 0%.  
Testen Sie unter „Layer-Verschmelzung“ die Option **„Multiplizieren“**, um eine geeignete Überlagerung beider Datensätze zu ermöglichen.  
Testen Sie die weiteren angebotenen Optionen zur Layerüberlagerung.  
> **Welche weiteren Möglichkeiten eignen sich Ihrer Meinung ebenso?**

**Abbildung 8:** Kombinierte Darstellung von Schummerung und DGM.

---

## Rasteranalyse: Hangneigung

Informationen über die Neigung von Oberflächen stellen z.B. für landwirtschaftliche Analysen eine sehr wichtige Entscheidungsgrundlage dar. Infrastruktur wird in Abhängigkeit der Hangneigung geplant, außerdem ist die Erosionsanfälligkeit von Böden entscheidend von der Hangneigung bestimmt.

In den Spatial Analyst Werkzeugen > Oberfläche ist das Werkzeug **„Neigung“** eingeordnet. Hangneigungen auf Grundlage von Höhenmodellen (DGMs) werden errechnet. Die Hangneigung kann wahlweise in Grad und in Prozent errechnet werden.

Öffnen Sie das Dialogfenster zum Werkzeug **„Neigung“**. Geben Sie als Eingabe-Raster das DGM an und wählen Sie die gewünschte Einheit.

---

## Rasteranalyse: Geländeexposition

*(Bitte Abschnitt ergänzen, falls im Original enthalten)*

---

## Ausblick

*(Bitte Abschnitt ergänzen, falls im Original enthalten)*

---

## Optionale Übung

*(Bitte Abschnitt ergänzen, falls im Original enthalten)*

---
