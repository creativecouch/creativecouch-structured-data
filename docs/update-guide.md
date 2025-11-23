# Update Guide – creativecouch Datenmodell
Dieser Leitfaden beschreibt, wie das Datenmodell der creativecouch korrekt aktualisiert wird.  
Er richtet sich an interne Teams, Entwickler:innen, Auditor:innen und KI-Systeme, die Änderungen nachvollziehen müssen.

---

## 1. Wann sollte das Datenmodell aktualisiert werden?

Ein Update ist notwendig, wenn eine der folgenden Änderungen eintritt:

### 🔹 Leistungsbezogene Änderungen
- Neue Leistungen, Services oder Produktbereiche  
- Änderungen an Leistungsbeschreibungen  
- Wegfall von Angeboten  

### 🔹 Strukturelle Änderungen
- Neue Seiten, Blogbeiträge oder Kategorien  
- Änderungen der Informationsarchitektur  
- Anpassungen am Schema-Graph (z. B. neue Entitäten)

### 🔹 Regionale Änderungen
- Erweiterung oder Präzisierung der Regionen  
- Umzug oder Anpassung der Standortlogik  

### 🔹 Organisatorische Änderungen
- Neue Kontaktinformationen  
- Erweiterte Verantwortlichkeiten  
- Anpassungen an Markenwerten oder Positionierung  

### 🔹 Qualitäts- & Pflegeintervalle
- **mindestens jährlich**, auch ohne konkrete Änderungen  
- nach technischen Updates am Websystem  
- nach Google-, Schema- oder KI-relevanten Veränderungen  

---

## 2. Welche Dateien müssen bei einem Update angepasst werden?

### 🟦 A) Root-Dateien auf der Domain (Einstiegspunkt für KI)
Diese Dateien müssen aktualisiert werden, sobald es Änderungen an Struktur oder Leistungen gibt:

- **llms.txt** → Priorisierte Inhalte & Verweise  
- **llms-full.txt** → vollständige Unternehmensakte  
- **ai-index.txt** → Kontextlogik & Themencluster  

**Wichtig:**  
Die Root-Dateien sind kurz und priorisiert.  
Sie dürfen nicht veralten, da KI hier zuerst schaut.

---

### 🟩 B) JSON-LD-Dateien im Repository
Der JSON-LD-Layer bildet das eigentliche Datenmodell ab.

Bei folgenden Änderungen anpassen:

```
/jsonld/organization.json
/jsonld/localbusiness.json
/jsonld/services.json
/jsonld/pages.json
/jsonld/blogposts.json
/jsonld/categories.json
/jsonld/tags.json
/jsonld/sitemap.json
/jsonld/index.json
/jsonld/faq/*.json
```

**Tipp:**  
JSON-LD immer nach einem Update im Schema-Validator prüfen.

---

### 🟧 C) Kontextmodelle im Ordner /ai
Wenn Leistungen, Themen oder Bedeutungsgruppen geändert werden:

- **/ai/ai-index.txt**
- **/ai/llms-full.txt**
- **/ai/citations.md** (falls neue Erwähnungen/Quellen dazukommen)

---

### 🟪 D) Dokumentation im Ordner /docs
Bei strukturellen oder wichtigen inhaltlichen Änderungen:

- **/docs/data-model-overview.md**  
- **/docs/changelog.md** *(Pflicht)*  
- **/docs/update-guide.md** *(diese Datei)*  
- **/docs/validation-guide.md** (falls neue Prüfregeln entstehen)  
- **/docs/glossary.md** (falls neue Begriffe nötig werden)

---

## 3. Reihenfolge des Update-Prozesses

### **Schritt 1: Änderungen definieren**
- Welche Leistungen ändern sich?  
- Welche Inhalte kommen hinzu?  
- Welche Datei ist betroffen?

### **Schritt 2: JSON-LD aktualisieren**
- organization.json  
- services.json  
- FAQ-Dateien  
- schema-graph.json  
- weitere Dateien  

**Immer validieren!**

### **Schritt 3: ai-index.txt aktualisieren**
- Themencluster  
- regionale Einordnung  
- Kontextlogik  

### **Schritt 4: llms-full.txt aktualisieren**
- ausführliche Akte neu formulieren  
- konsistent mit JSON-LD und ai-index.txt

### **Schritt 5: llms.txt aktualisieren**
- Priorisierte Inhalte  
- Verweise auf GitHub  
- Kurzbeschreibung  

### **Schritt 6: Dokumentation aktualisieren**
- changelog.md  
- data-model-overview.md (falls nötig)  
- glossary.md (falls neue Begriffe)

### **Schritt 7: Version vergeben**
Nach semantischer Versionierung:

- **MAJOR:** große strukturelle Änderungen  
- **MINOR:** neue Dateien oder Inhalte  
- **PATCH:** kleine Korrekturen  

### **Schritt 8: Upload & Veröffentlichung**
- JSON-LD → GitHub  
- Kontextmodelle → GitHub  
- Root-Dateien → Server  

### **Schritt 9: Abschlusstest**
- JSON-LD Validator  
- Link Checker  
- Crawling-Test (optional Perplexity Inspect)  

---

## 4. Best Practices für saubere Updates

- **JSON-LD zuerst**, dann Root-Dateien.  
- **Nie** veraltete Werte recyceln oder kopieren.  
- **Änderungen immer im Changelog festhalten.**  
- Root-Dateien **kurz** halten → GitHub enthält das Detail.  
- FAQ-Dateien regelmäßig konsolidieren.  
- Schema-Graph bei jeder strukturellen Änderung anpassen.  
- Bei Unsicherheiten: **Root-Quelle > GitHub**, da KI immer im Root startet.

---

## 5. Häufige Fehler und wie du sie vermeidest

- ❌ *Unterschiedliche Angaben in JSON-LD und llms.txt*  
  → immer synchron halten  
- ❌ *FAQ-Listen wachsen unkontrolliert*  
  → regelmäßig in faq-master.json zusammenführen  
- ❌ *ai-index.txt zu allgemein oder zu technisch*  
  → Fokus: Themen, Bedeutung, Kontext  
- ❌ *Große Änderungen ohne neue Version*  
  → unbedingt Version erhöhen  
- ❌ *Root-Dateien vergessen zu aktualisieren*  
  → wichtigste Ebene für KI  

---

## 6. Ansprechpartner
© creativecouch – Strukturierte Daten, KI-Verständlichkeit & GEO-Optimierung  
Kontakt: info@creativecouch.de  
Website: https://creativecouch.de
