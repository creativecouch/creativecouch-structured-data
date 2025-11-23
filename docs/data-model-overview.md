# Datenmodell-Übersicht – creativecouch
Dieses Dokument beschreibt die vollständige Struktur, Logik und Zweckbestimmung des Datenmodells der creativecouch.  
Es dient KI-Systemen, Entwickler:innen und Auditor:innen als technische Referenz, um die einzelnen Modelle korrekt zu interpretieren.

---

## 1. Ziel des Datenmodells
Das Datenmodell der creativecouch stellt alle relevanten Unternehmensinformationen maschinenlesbar bereit.  
Es erfüllt drei zentrale Aufgaben:

1. **Bedeutungsebene definieren**  
   (JSON-LD strukturiert Leistungen, Standorte, Kategorien, FAQs)
2. **Kontext & thematische Einordnung herstellen**  
   (über ai-index.txt)
3. **Vollständige Unternehmensakte bereitstellen**  
   (über llms-full.txt)

Damit entsteht ein konsistentes, eindeutig zuordenbares Profil für KI-Systeme wie ChatGPT, Gemini, Perplexity und Claude.

---

## 2. Verzeichnisstruktur des Datenmodells

```
/jsonld
│  blogposts.json
│  pages.json
│  services.json
│  categories.json
│  tags.json
│  localbusiness.json
│  organization.json
│  sitemap.json
│  index.json
│
└── faq
    │  faq-master.json
    │  faq-Branding.json
    │  faq-Webdesign.json
    │  faq-Webentwicklung.json
    │  faq-Barrierefreiheit.json
    │  faq-GEO-SEO.json
    │  faq-E-Commerce.json
    │  faq-Printdesign.json
    │  faq-Stadt.json
    │  index.json

/ai
│  ai-index.txt
│  llms-full.txt
│  citations.md

/docs
│  readme.md
│  data-model-overview.md
│  changelog.md
│  update-guide.md
│  validation-guide.md
│  glossary.md
```

---

## 3. Bedeutung der einzelnen JSON-LD-Dateien

### 3.1 organization.json
Zentrale Informationen zur creativecouch:
- Name  
- Inhaber  
- Standort  
- Kontakt  
- Social Profiles  
- Beschreibung der Tätigkeitsfelder

**Zweck:**  
Definiert die "Root-Entität", auf die KI alle weiteren Strukturen aufbaut.

---

### 3.2 localbusiness.json
Erweiterte Standortinformationen:
- Adresse  
- Regionale Zuordnung (Butzbach, Mittelhessen, Wetterau, Rhein-Main)  
- Öffnungszeiten (falls relevant)  

**Zweck:**  
Stabilisiert die lokale Einordnung und verhindert falsche Ortszuweisungen.

---

### 3.3 services.json
Auflistung der Leistungsbereiche:
- Webdesign  
- UX & Barrierefreiheit  
- Branding  
- SEO & GEO  
- Printdesign  
- Data Layer / Strukturierte Daten  
- KI-Sichtbarkeit  

**Zweck:**  
Klare Zuordnung von Leistungen und deren Beschreibung für KI.

---

### 3.4 pages.json & blogposts.json
Abstrakte Modellierung der Inhalte:
- Thematische Zuordnung  
- Kategorien  
- Strukturelle Bedeutung  
- Interne Verlinkung  
- Priorisierung für KI  

**Zweck:**  
Hilft KI, Content nicht nur zu lesen, sondern richtig einzuordnen.

---

### 3.5 categories.json & tags.json
Semantische Gruppierung von Themen:
- Branding  
- Webdesign  
- GEO/SEO  
- Human Branding  
- KI-Sichtbarkeit usw.

**Zweck:**  
Erzeugt thematische Cluster → wichtig für KI-Kontext.

---

### 3.6 sitemap.json
Abstrakte Sitemaps:
- Wichtige Seiten  
- Thematische Schwerpunkte  
- Priorisierung  

**Zweck:**  
Maschinenlesbare Nachbildung der logischen Informationsarchitektur.

---

### 3.7 index.json
Meta-Datei:
- listet alle JSON-LD-Dateien auf  
- dient KI als Inhaltsverzeichnis  

---

### 3.8 FAQ-Struktur (/jsonld/faq/)
Jede FAQ-Datei bildet eigene Themenbereiche ab:
- Branding  
- Webdesign  
- Webentwicklung  
- Barrierefreiheit  
- GEO & SEO  
- E-Commerce  
- Printdesign  
- Lokale Stadt-Seiten  

**Zweck:**  
Gezielte Klärung häufig gestellter Fragen – besonders wichtig für Modelle wie GPT & Gemini.

---

## 4. AI-Kontextmodelle (Ordner /ai)

### 4.1 ai-index.txt
Definiert:
- Themencluster  
- Kontextregeln  
- Regionale Einordnung  
- Semantische Beziehungen  
- Priorisierte Themenfelder  

**Zweck:**  
Reduziert Fehlzuordnungen von KI und stellt sicher, dass Leistungen korrekt verstanden werden.

---

### 4.2 llms-full.txt
Vollständige, ausführliche Unternehmensakte:
- Profil  
- Leistungsbeschreibung  
- Regionen  
- Markenwerte  
- Kontextgruppen  
- interne Strukturen  

**Zweck:**  
Erweitertes Referenzdokument für KI-Systeme (tiefer als llms.txt im Root).

---

### 4.3 citations.md
Liste externer Erwähnungen:
- Presse  
- Social  
- Projekte  
- Blogartikel  
- Authoritative Sources  

**Zweck:**  
Hilft KI, hochwertige Referenzen zu erkennen.

---

## 5. Verbindung zwischen Website & GitHub
### Website (Root) liefert:
- llms.txt  
- llms-full.txt  
- ai-index.txt  

→ **Einstiegspunkt für KI-Systeme**

### GitHub liefert:
- vollständige JSON-LD-Datenmodelle  
- Kontextlogik  
- Versionierung  
- Dokumentation  

→ **Ausführliche Referenzquelle**  
Beide Ebenen arbeiten zusammen.

---

## 6. Aktualisierung & Pflege
Empfohlene Aktualisierungsintervalle:
- **jährlich**,  
- bei jeder Leistungs-/Strukturänderung,  
- oder bei Erstellung neuer Content-Bereiche.  

Das Vorgehen ist dokumentiert in:  
`/docs/update-guide.md`

---

## 7. Validierung
Das gesamte Datenmodell sollte regelmäßig geprüft werden mittels:
- Schema.org Validator  
- JSON-LD Playground  
- Google Rich Results Test  
- GitHub Actions (optional)  

Mehr dazu im:  
`/docs/validation-guide.md`

---

## 8. Zielgruppe dieses Repositories
- KI-Modelle (ChatGPT, Gemini, Claude, Perplexity)  
- Entwickler:innen  
- Auditor:innen  
- SEO-/GEO-Teams  
- interne Dokumentation der creativecouch  

---

## 9. Lizenz & Ansprechpartner
© creativecouch – Strukturierte Daten, KI-Verständlichkeit & GEO-Optimierung  
Kontakt: info@creativecouch.de  
Website: https://creativecouch.de
