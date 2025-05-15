## Übung 3: Datenorganisation und -verwaltung

**Modul:** GIS 1
**Thema:** Datenverwaltung und -organisation in Geographischen Informationssystemen


---

### **Lernziele**

- Sie verstehen die Grundsätze der Datenorganisation für GIS-Projekte.
- Sie können Daten auf Betriebssystemebene und in ArcGIS Pro sinnvoll strukturieren.
- Sie reflektieren die Vor- und Nachteile verschiedener Geodatenformate (Shapefile, File-Geodatabase).
- Sie wenden Best Practices der Datenverwaltung an, um Datenintegrität und Reproduzierbarkeit zu gewährleisten.

---

### **Aufgabenstellung**

#### **1. Analyse und Reflexion: Datenorganisation**

Lesen Sie den Abschnitt **1.1 Grundsätze** zur Datenorganisation.
    Beantworten Sie anschließend die folgenden Fragen schriftlich:

    - Welche Vorteile bietet es, Geodaten in einem eigenen Ordner auf einer separaten Festplatte oder Partition zu speichern?
    - Warum sollten Pfade und Dateinamen keine Umlaute, Sonderzeichen oder Leerzeichen enthalten?
    - Welche Risiken entstehen, wenn Daten auf externen Festplatten oder USB-Sticks gespeichert werden?

> **Hinweis aus der Lernforschung:**
> Schreiben Sie Ihre Antworten stichpunktartig und in eigenen Worten auf. Die aktive Verarbeitung und das Paraphrasieren fördern ein tieferes Verständnis und die langfristige Erinnerung (vgl. Effekte des aktiven Lernens).

---

#### **2. Praktische Übung: Datenverwaltung auf Betriebssystemebene**

Sie erhalten mehrere ZIP-Dateien mit Geodaten (z.B. von einer Landesbehörde).
Führen Sie folgende Schritte durch:

- Öffnen Sie eine ZIP-Datei und analysieren Sie die enthaltene Verzeichnisstruktur, bevor Sie sie entpacken.
- Entpacken Sie die Daten so, dass keine überflüssigen Unterordner entstehen und die Daten klar strukturiert sind.
- Legen Sie für „Fremde Daten“ und „Projektdaten“ jeweils einen eigenen Ordner an.
Benennen Sie die Ordner nach dem Muster:
    - Fremde Daten: `Datenquelle_Jahr` (z.B. `LUBW_2024`)
    - Projektdaten: `Projektname_Eingang_Datum` (z.B. `Stadtanalyse_Eingang_2024-05-06`)
- Dokumentieren Sie Ihre Vorgehensweise in einer kurzen Checkliste (max. 5 Schritte).

> **Hinweis aus der Lernforschung:**
> Visualisieren Sie Ihre Ordnerstruktur mit einer einfachen Skizze oder einem Screenshot. Die Kombination aus Text und Bild unterstützt die kognitive Verarbeitung (Dual Coding Theory).

---

#### **3. Vergleich: Dateibasierte vs. datenbankbasierte Geodatenformate (ca. 10 Minuten)**

    Vergleichen Sie die beiden Geodatenformate **Shapefile (SHP)** und **File-Geodatabase (FGDB)** anhand folgender Kriterien:

    - Anzahl und Organisation der enthaltenen Dateien
    - Möglichkeiten zur Speicherung mehrerer Feature-Classes
    - Unterstützung von Metadaten und Attributen
    - Einschränkungen und Vorteile im praktischen Einsatz

Erstellen Sie dazu eine Tabelle nach folgendem Muster:


| Kriterium | Shapefile (SHP) | File-Geodatabase (FGDB) |
| :-- | :-- | :-- |
| Anzahl Dateien |  |  |
| Mehrere Feature-Classes möglich? |  |  |
| Metadaten-Unterstützung |  |  |
| Einschränkungen |  |  |
| Vorteile |  |  |

> **Hinweis aus der Lernforschung:**
> Das Ausfüllen von Vergleichstabellen fördert das strukturierte Denken und unterstützt den Wissenstransfer auf neue Problemstellungen (Scaffolding).

---

#### **4. Reflexion: Best Practices und Fehlerquellen**

Reflektieren Sie abschließend:

- Welche typischen Fehler bei der Datenorganisation und -verwaltung könnten im GIS-Alltag auftreten?
- Welche Maßnahmen können Sie ergreifen, um diese Fehler zu vermeiden?

> **Hinweis aus der Lernforschung:**
> Die Reflexion eigener Erfahrungen und die Entwicklung von Strategien zur Fehlervermeidung fördern die Metakognition und erhöhen die Problemlösekompetenz.

---

### **Abgabe**

- Antworten und Dokumentation als Markdown-Datei (.md) einreichen.
- Screenshots bitte als Bilddateien anhängen und im Markdown referenzieren.

---

### **Weiterführende Ressourcen**

- [ArcGIS Pro Dokumentation: Was ist eine Geodatabase?](https://pro.arcgis.com/de/pro-app/latest/help/data/geodatabases/overview/what-is-a-geodatabase-.htm)

---

**Viel Erfolg bei der Bearbeitung!**

<div style="text-align: center">⁂</div>

[^1]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/62194985/df2756d0-4d65-4755-a105-383606f691b5/U_M1_03_Datenverwaltung_20240506.docx

[^2]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/62194985/e51ff131-7ff4-4bf8-935c-2e63de201b34/U_M1_03_Datenverwaltung_20240506.pdf

