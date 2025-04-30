# Zertifikatsstudium Geodatenmanager/-in

## CAS Geographische Informationssysteme

### Modul: GIS 1

#### Übung: Tabellen mit indirektem und direktem Raumbezug

##### Windkraft und Gesundheitsdaten


---

## Inhaltsverzeichnis

- [1. Verwendete Daten](#1-verwendete-daten)
- [2. Vorbemerkungen und Ziele](#2-vorbemerkungen-und-ziele)
    - [2.1 Daten mit räumlichem Bezug](#21-daten-mit-r%C3%A4umlichem-bezug)
    - [2.2 Daten ohne räumlichen Bezug](#22-daten-ohne-r%C3%A4umlichen-bezug)
    - [2.3 Ziele](#23-ziele)
- [3. Datenrecherche im Internet](#3-datenrecherche-im-internet)
    - [3.1 Mit Raumbezug](#31-mit-raumbezug)
    - [3.2 Ohne Raumbezug](#32-ohne-raumbezug)
- [4. Vektordatengenerierung aus tabellarischen Daten](#4-vektordatengenerierung-aus-tabellarischen-daten)
    - [4.1 Symbologie auf Grundlage der Attributeigenschaften einstellen](#41-symbologie-auf-grundlage-der-attributeigenschaften-einstellen)
- [5. Statistikdaten verbinden (Join)](#5-statistikdaten-verbinden-join)
    - [5.1 Gesundheitsamt](#51-gesundheitsamt)
    - [5.2 Symbolisierung](#52-symbolisierung)
- [6. Fazit](#6-fazit)
- [7. Anhang](#7-anhang)
    - [7.1 Hinweise zu DESTATIS](#71-hinweise-zu-destatis)
- [Abbildungsverzeichnis](#abbildungsverzeichnis)

---

## 1. Verwendete Daten

- Ordner: `\Tabellenimport_Windkraft\*.xlsx / *.csv`
- `\Tabellen_Join\DataView146_1`
- **WMS:**
    - http://ows.terrestris.de/osm/service?
    - https://sgx.geodatenzentrum.de/wms_basemapde?REQUEST=GetCapabilities\&Version=1.3.0
    - http://sgx.geodatenzentrum.de/wms_topplus_open?

**Abbildungen:**
Soweit nicht anders gekennzeichnet, handelt es sich bei den Abbildungen um Screenshots der aufgeführten Software oder sie wurden aus dem ESRI ArcGIS Ressource Center entnommen.

---

## 2. Vorbemerkungen und Ziele

In dieser Übung geht es um tabellarische Daten, die nicht in erster Linie als Geodaten gedacht waren. Es gibt:

- Tabellen mit Koordinaten (räumlicher Bezug)
- Tabellen ohne Raumbezug, die über eine ID mit Geodaten verknüpft werden können


### 2.1 Daten mit räumlichem Bezug

- Windkraftstandorte in Baden-Württemberg recherchieren und in ArcGIS Pro räumlich darstellen
- Geeignete Symbologie für die Leistung der Windkraftanlagen zuweisen

Die Landesanstalt für Umwelt, Messungen und Naturschutz Baden-Württemberg führt eine Tabelle mit allen installierten Windkraftanlagen in BW.

### 2.2 Daten ohne räumlichen Bezug

- Statistische Daten zur Bevölkerung und zum Gesundheitszustand aus Tabellen ohne Raumbezug mit Geobasisdaten verknüpfen
- Symbolisierung nach Werten aus den verknüpften Attributen

Tabellen werden über den Gesundheitsatlas BW bereitgestellt.

### 2.3 Ziele

- Datenrecherche im Internet
- Koordinatensystem einstellen
- Einbinden eines WebMapServices
- Vektordatengenerierung aus Tabellenimport
- Tabellen verbinden (Join)
- Attribute (Sachdaten) darstellen

---

## 3. Datenrecherche im Internet

Durch die Open-Data-Initiative werden viele Behördendaten frei zugänglich gemacht, darunter auch Windkraftdaten für Baden-Württemberg.

### 3.1 Mit Raumbezug

- Recherchieren Sie auf der Seite der LUBW nach Windkraftdaten und speichern Sie diese als Excel- und CSV-Datei.
    - [Windkraftdaten LUBW](https://udo.lubw.baden-wuerttemberg.de/public/q/4I1YIwOUEQ4SohAtpULORm)
- Prüfen Sie, ob die Tabelle Koordinaten enthält.


### 3.2 Ohne Raumbezug

- DESTATIS bietet umfangreiche Statistikdaten, z.B. Einwohnerzahlen mit PLZ und AGS:
    - [DESTATIS Gemeindeverzeichnis](https://www.destatis.de/DE/Themen/Laender-Regionen/Regionales/Gemeindeverzeichnis/_inhalt.html)
- Gesundheitsatlas BW mit entsprechenden Bevölkerungsdaten:
    - [Gesundheitsatlas BW](http://www.gesundheitsatlas-bw.de/)

---

## 4. Vektordatengenerierung aus tabellarischen Daten

- Neues Projekt anlegen, Koordinatensystem auf 25832 (UTM32N) einstellen, Basiskarte laden
- Tabellen mit Koordinaten können als Punktgeometrien importiert werden

**Hinweis:**
ArcGIS Pro benötigt ggf. einen Microsoft ACCESS Treiber für Excel-Dateien. Exportieren Sie daher Excel-Dateien in CSV, falls möglich.

**Tipp:**
Falls die CSV-Datei fehlerhaft ist (z.B. zusätzliche Kopfzeilen), löschen Sie die ersten Zeilen, sodass die erste Zeile die Spaltenüberschriften enthält.

- CSV-Datei als Standalone-Tabelle ins Projekt einfügen
- Mit Rechtsklick auf die Tabelle „XY Daten anzeigen“ wählen:
    - X-Feld: Ost
    - Y-Feld: Nord
    - Koordinatensystem: ETRS UTM 32N (EPSG: 25832)

**Anmerkung:**
Mit „XY Daten anzeigen“ wird die Tabelle in die Projekt-GDB geschrieben. Die Standalone-Tabelle wird danach nicht mehr benötigt.

**Optional:**
Im letzten Schritt kann die räumlich dargestellte Tabelle als Shape-Datei exportiert werden.

---

### 4.1 Symbologie auf Grundlage der Attributeigenschaften einstellen

- Im Register „Aussehen“ für „Windkraftstandorte_BW“ die primäre Symbolisierung als „Abgestufte Farben“ wählen
- Als Wert „Generatorleistung“ auswählen und passenden Farbverlauf bestimmen

Sie haben nun gelernt, wie Sie tabellarische Daten mit Raumbezug in ein GIS importieren und visualisieren.

---

## 5. Statistikdaten verbinden (Join)

Statistische Daten können über eine ID mit GIS-Daten verbunden werden (Join).

- Recherchieren Sie beim LGL nach Verwaltungsdaten im Vektorformat:
    - [LGL Open Data](https://www.lgl-bw.de/Produkte/Open-Data/)
- Zwei Datensätze zu Verwaltungsgrenzen verfügbar:
    - OD_AX_Verwaltungsgebiete_komplett.zip (neu, KBS 25832)
    - OD_AX_Alle_VerwaltungseinheitenBW.zip (alt, KBS 31467)

Die Gemeinde-ID entspricht dem AGS (amtlicher Gemeindeschlüssel).

**Hinweis:**
Falls Spaltennamen Umlaute enthalten, muss ggf. eine neue Spalte ohne Umlaute angelegt werden.

---

### 5.1 Gesundheitsamt

- Datei „Lebenserwartung für Landkreise“ im CSV-Format herunterladen:
    - [Gesundheitsatlas BW Dashboard](https://dashboards.instantatlas.com/viewer/report?appid=4c2f5a0aceae48d893d8768f6b907672)
- Prüfen Sie, ob eine ID für den Join vorhanden ist. Falls nicht, kann der Join über den Namen erfolgen (Achtung auf Schreibweisen).

**Tipp:**
Falls die Spalten für den Join unterschiedlich formatiert sind (Zahl vs. Text), muss eine zusätzliche Spalte mit passendem Format angelegt werden.

---

### 5.2 Symbolisierung

- Nach erfolgreichem Join können die Daten nach den verknüpften Attributen symbolisiert werden.

---

## 6. Fazit

Sie haben gelernt, wie Sie tabellarische Daten mit und ohne Raumbezug recherchieren, aufbereiten, ins GIS importieren, als Vektordaten visualisieren und mit weiteren Daten verknüpfen.

---

## 7. Anhang

### 7.1 Hinweise zu DESTATIS

- Daten von DESTATIS müssen ggf. angepasst werden (siehe Hinweise im Dokument).
- Weitere Informationen: [Amtlicher Gemeindeschlüssel](https://de.wikipedia.org/wiki/Amtlicher_Gemeindeschl%C3%BCssel)

---

## Abbildungsverzeichnis

- **Abbildung 1:** Tabelle mit räumlichem Bezug
- **Abbildung 2:** Feldrechner
- **Abbildung 3:** Verbindung (Join)
- **Abbildung 4:** Darstellung kategorisiert nach Farben

---

**Hinweis:**
Alle Abbildungen befinden sich im Ordner `bilder` und werden im Markdown-Dokument entsprechend referenziert.

---

**Ende des Dokuments**

<div style="text-align: center">⁂</div>

[^1]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/62194985/a76564ea-68cb-46f4-a344-3430ddae3163/U_M1_W1_Tabellen-einbinden_20240514.pdf

[^2]: https://pdf2md.morethan.io

[^3]: https://github.com/VikParuchuri/marker

[^4]: https://www.reddit.com/r/learnpython/comments/1ej02wh/what_is_the_best_way_to_convert_a_wellformatted/

[^5]: https://notegpt.io/pdf-to-markdown-converter

[^6]: https://www.tomarkdown.org/pdf-to-markdown

[^7]: https://pdf.wondershare.com/convert-pdf/pdf-to-markdown.html

[^8]: https://community.openai.com/t/converting-pdf-to-markdown-with-ocr/762476

[^9]: https://stackoverflow.com/questions/74092914/formatting-markdown-document-for-pdf

[^10]: https://github.com/laiso/pdf-to-markdown-gpt

[^11]: https://www.markdownguide.org/getting-started/

[^12]: https://openl.io/de/pdf-to-markdown

[^13]: https://github.com/cosmos/governance/issues/1

[^14]: https://rapidapi.com/arxivgpt-arxivgpt-default/api/pdf-to-markdown1

[^15]: https://bookdown.org/yihui/rmarkdown/pdf-document.html

[^16]: https://israelmitolu.hashnode.dev/markdown-for-technical-writers-tips-tricks-and-best-practices

[^17]: https://www.markdownguide.org/hacks/

[^18]: https://www.youtube.com/watch?v=7DJzHncUlpI

[^19]: https://www.reddit.com/r/pandoc/comments/1fmpl9u/best_practices_for_converting_pdfs_to_markdown/

