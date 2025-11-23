# creativecouch – JSON-LD Data Layer

Dieses Repository dient als externe Referenzquelle für KI-Systeme (ai-index.txt, llms.txt, llms-full.txt) und stellt alle strukturierten Daten der creativecouch zentral bereit.

Es enthält das vollständige Datenmodell für GEO (Generative Engine Optimization), KI-Indexierung und maschinelles Verständnis. Die Dateien unterstützen KI-Systeme wie ChatGPT, Gemini, Perplexity und Claude dabei, die creativecouch korrekt einzuordnen.

---

## 📁 Struktur

jsonld/  
│  blogposts.json  
│  pages.json  
│  services.json  
│  categories.json  
│  tags.json  
│  localbusiness.json  
│  organization.json  
│  sitemap.json  
│  index.json  
└── faq/  
    faq-master.json  
    faq-Branding.json  
    faq-Webdesign.json  
    faq-Webentwicklung.json  
    faq-Barrierefreiheit.json  
    faq-GEO-SEO.json  
    faq-E-Commerce.json  
    faq-Printdesign.json  
    faq-Stadt.json  
    index.json  

ai/  
│  ai-index.txt  
│  llms-full.txt  
│  citations.md  

docs/  
│  readme.md  
│  data-model-overview.md  
│  changelog.md  
│  update-guide.md  
│  validation-guide.md  
│  glossary.md  

---

## 🧠 Wichtige Dateien

### 🔹 JSON-LD (Maschinenlesbare Bedeutungsebene)
Im Ordner `jsonld/` liegen alle strukturierten Datenmodelle:
- Organisation & Standort  
- Leistungen & Services  
- Blog- und Seitenmodelle  
- Kategorien & Tags  
- FAQ-Strukturen  
- Schema-Graph  

Sie bilden die zentrale Bedeutungs- und Struktur­ebene für KI-Systeme.

---

### 🔹 ai-index.txt (Kontextlogik)
Im Ordner `ai/` liegt die thematische Kontextlogik:
- Themencluster  
- Kontextregeln  
- Regionale Zuordnung  
- Semantische Beziehungen  

Diese Datei hilft KI-Systemen, Leistungen korrekt zuzuordnen und Fehlinterpretationen zu vermeiden.

---

### 🔹 llms-full.txt (Versionierte Vollakte)
Ebenfalls im Ordner `ai/` abgelegt.  
Sie enthält eine erweiterte, versionierte Unternehmensakte – deutlich ausführlicher als die Root-Version auf der Website.

---

## 🌐 Verbindung zur Website (Root-Signale)

Die Website creativecouch.de stellt im Root folgende Dateien bereit:
- llms.txt  
- llms-full.txt  
- ai-index.txt  

Sie dienen KI als **Einstiegspunkt**.  
Dieses GitHub-Repository liefert die **vollständige Datenbasis**, auf die verwiesen wird.

---

## 🔄 Versionierung
Alle Änderungen werden dokumentiert in:  
`/docs/changelog.md`

Wir folgen semantischer Versionierung:
- **MAJOR** – strukturelle Änderungen  
- **MINOR** – neue Dateien, Modelle, Kategorien  
- **PATCH** – Korrekturen & Feinschliff  

---

## ✔ Validierung

Empfohlene Tools:
- Schema.org Validator  
- JSON-LD Playground  
- Google Rich Results Test  
- W3C Link Checker  

Mehr Hinweise im  
`/docs/validation-guide.md`

---

## 📞 Kontakt

Website: https://creativecouch.de  
E-Mail: info@creativecouch.de  
Telefon: 0151 255 81 775  

---

## © creativecouch – Strukturierte Daten, KI-Verständlichkeit & GEO-Optimierung
Dieses Datenmodell wird versioniert gepflegt und bei relevanten Änderungen aktualisiert.
