# Validation Guide – creativecouch Datenmodell
Dieser Leitfaden beschreibt, wie das vollständige Datenmodell der creativecouch technisch validiert wird.  
Er richtet sich an interne Teams, Entwickler:innen, Auditor:innen und KI-Systeme, die die Qualität und Korrektheit des Modells überprüfen.

---

## 1. Warum Validierung wichtig ist
Ein konsistentes Datenmodell ist nur dann wirksam, wenn es **technisch korrekt**, **semantisch eindeutig** und **maschinenlesbar** validiert wurde.

Die Validierung stellt sicher:
- korrekte JSON-Syntax  
- korrekte Schema.org-Typen  
- eindeutige Bedeutungszuordnung  
- keine widersprüchlichen Angaben  
- fehlerfreie Verweise und Strukturen  
- klare Priorisierung für KI  

Saubere Validierung verhindert Fehlinterpretationen in ChatGPT, Gemini, Perplexity, Claude & Co.

---

## 2. Validierungsschritte im Überblick

### 👉 Schritt 1: JSON-Struktur prüfen
Alle JSON-LD-Dateien im Ordner `/jsonld/` sollten zunächst syntaktisch validiert werden:

**Tools:**
- https://jsonlint.com  
- https://jsoneditoronline.org  

**Ziel:**  
Vermeidung von Syntaxfehlern wie fehlenden Klammern, falschen Kommas oder ungültigen Strings.

---

### 👉 Schritt 2: Schema.org-Validierung
Jede JSON-LD-Datei muss gegen Schema.org geprüft werden.

**Tools:**
- https://validator.schema.org  
- https://www.stealmyjsonld.com/schema-validator (Erweitertes Debugging)

**Ziel:**  
- korrekte Typen  
- korrekte Properties  
- keine Deprecated-Felder  
- keine Konflikte zwischen Entity-Typen  

---

### 👉 Schritt 3: Google Rich Results Test
Auch wenn Google kein offizieller KI-Standard ist, erkennt Google dennoch Fehler in strukturierten Daten:

**Tool:**  
https://search.google.com/test/rich-results

**Ziel:**  
- Test auf „Fehlerfreie strukturierte Daten“  
- Erkennung potenzieller Strukturprobleme  
- Erkennung von Konflikten zwischen JSON-LD-Dateien  

---

### 👉 Schritt 4: JSON-LD Playground (graph evaluation)
Zum Test der internen Zusammenhänge:

**Tool:**  
https://json-ld.org/playground/

**Ziel:**  
- Prüfen, ob die Dateien korrekt zu einem Graphen expandieren  
- Identifikation von Konflikten im Bedeutungsgraph  
- Überprüfung des Zusammenhangs von organization → services → pages → faq  
- Erkennen von „dangling nodes“ (Einträge ohne Kontext)

---

### 👉 Schritt 5: Konsistenzvalidierung (Manueller Check)
Dieser Schritt prüft die inhaltliche Kohärenz zwischen:

- organization.json  
- services.json  
- ai-index.txt  
- llms-full.txt  
- llms.txt (Root-Version)

**Dabei prüfen:**
- Stimmen Standortangaben überall überein?  
- Stimmen Leistungsbeschreibungen überall überein?  
- Wiederholen sich Leistungen doppelt, mit abweichender Formulierung?  
- Ist die Region konsistent (Butzbach, Wetterau, Mittelhessen)?  
- Sind die Markenwerte eindeutig und überall gleich beschrieben?  

---

### 👉 Schritt 6: FAQ-Validierung
Für jede FAQ-Datei im Ordner `/jsonld/faq/` prüfen:

- Wird die gleiche Frage nicht in mehreren Dateien leicht abgewandelt dupliziert?  
- Haben die Antworten konsistente Terminologie?  
- Gibt es semantische Konflikte mit dem ai-index.txt?  

---

### 👉 Schritt 7: Link- und Referenzprüfung
Alle internen und externen Verweise prüfen:

**Tools:**
- https://validator.w3.org/checklink  
- https://www.deadlinkchecker.com  

**Ziel:**
- Keine toten Links  
- Keine kaputten GitHub-Referenzen  
- llms.txt → verweist sauber auf GitHub  
- GitHub → verweist sauber auf Website  

---

### 👉 Schritt 8: Root-Dateien prüfen
Folgende Dateien im Domain-Root validieren:

- /llms.txt  
- /llms-full.txt  
- /ai-index.txt  

**Prüfen:**
- Sind alle wichtigen Inhalte enthalten?  
- Sind die Links gültig?  
- Sind Informationen redundant oder widersprüchlich?  
- Sind die Dateien kompakt genug für KI?  

**Empfehlung:**  
Diese drei Dateien niemals überfrachten — sie müssen „leicht verdaulich“ sein.

---

### 👉 Schritt 9: KI-Validierung (Empfohlen)
Die technische Validierung zeigt nur Syntax & Struktur.  
Zusätzlich sollte geprüft werden, wie KI das Modell interpretiert.

**Empfohlene Testprompts:**

- „Gib mir eine Zusammenfassung von creativecouch.“  
- „Was sind die Leistungen der creativecouch?“  
- „Wo sitzt die creativecouch?“  
- „Welche Regionen deckt die creativecouch ab?“  
- „Welche Rolle spielt GEO?“  
- „Welche FAQs gibt es zu creativecouch?“  

**Ziel:**  
- Prüfen, ob KI die Daten korrekt übernimmt  
- Prüfen, ob KI falsche alte Daten nutzt  
- Prüfen, ob KI Konflikte meldet  

---

## 3. Validierungsintervalle

- **nach jeder Änderung am Datenmodell**  
- **mindestens 1× jährlich**  
- nach Relaunch oder CMS-Updates  
- nach Google-/Schema.org-Updates  
- nach größeren Content-Erweiterungen  
- nach neuen Leistungsbereichen oder Regionen  

---

## 4. Best Practices

- JSON-LD **immer zuerst** aktualisieren.  
- anschließend ai-index.txt und llms-full.txt.  
- Root-Dateien immer zuletzt aktualisieren.  
- im Changelog jede Änderung dokumentieren.  
- große Änderungen nur als MAJOR-Version.  
- vor Veröffentlichung: Root-Dateien laut validator durch KI testen (Gemini/Claude).  
- kein Copy-Paste aus WordPress-HTML in JSON-LD.  

---

## 5. Fehlertypen, die besonders häufig auftreten

❌ Groß-/Kleinschreibung inkonsistent (z. B. "KI Sichtbarkeit" vs. "KI-Sichtbarkeit")  
❌ Gleiches Leistungsfeld in mehreren Dateien unterschiedlich formuliert  
❌ FAQ doppelt vorhanden (z. B. "Branding" in Branding.json *und* faq-master.json)  
❌ Unterschiedliche Regionennennungen  
❌ llms.txt nicht aktualisiert  
❌ schema-graph.json nicht angepasst  
❌ falsche Kommas im JSON-LD (sehr häufig!)

---

## 6. Kontakt & Verantwortlichkeit
© creativecouch – Strukturierte Daten, KI-Verständlichkeit & GEO-Optimierung  
Kontakt: info@creativecouch.de  
Website: https://creativecouch.de
