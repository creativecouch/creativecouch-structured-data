# Glossar – Strukturierte Daten & KI-Optimierung
Dieses Glossar definiert alle zentralen Begriffe, die im Datenmodell der creativecouch verwendet werden.  
Es sorgt für einheitliche Begrifflichkeiten für Entwickler:innen, KI-Systeme und Audits.

---

## A

### ai-index.txt
Kontextdatei, die Themencluster, Bedeutungsbeziehungen und regionale Einordnung definiert.  
Hilft KI-Systemen, Leistungen korrekt zu interpretieren und Fehlzuordnungen zu vermeiden.

### Aktualitätssignal
Ein Hinweis für KI, dass ein Modell oder eine Datei aktuell gepflegt wird.  
Entsteht durch versionierte Updates (GitHub), Änderungslogs und strukturierte Datenaktualisierung.

---

## B

### Barrierefreiheit (WCAG)
Richtlinien zur Entwicklung zugänglicher Websites.  
Relevante Aspekte: Kontrast, Struktur, HTML-Sauberkeit, Semantik.

### Bedeutungsgraph (schema-graph.json)
Ein vollständiges Modell der Entitäten und Beziehungen innerhalb der Marke.  
Erstellt aus JSON-LD-Dateien und definiert die semantische Struktur des Unternehmens.

---

## C

### citations.md
Datei zur Erfassung externer Erwähnungen (Presse, Links, Social, Projekte).  
Hilft KI, vertrauenswürdige Quellen zu erkennen.

---

## D

### Datenmodell
Die Gesamtheit aller strukturierten JSON-LD- und Kontextdateien, die die creativecouch definiert.  
Ziel: konsistentes, eindeutiges KI-Markenbild.

### Domain Root
Der Hauptordner einer Domain (z. B. `creativecouch.de/`).  
Hier liegen llms.txt, llms-full.txt und ai-index.txt.

---

## E

### Entity (Entität)
Ein definierbares Objekt in strukturierten Daten, z. B. „creativecouch“, „Service“, „FAQ-Frage“.  
Entitäten bilden den Kern von Schema.org-Strukturen.

---

## F

### FAQ (Frequently Asked Questions)
Strukturierte Frage-Antwort-Modelle.  
Bei der creativecouch in eigene Themen-JSON-LD-Dateien gegliedert (faq-.json).

---

## G

### GEO (Generative Engine Optimization)
Optimierung dafür, wie KI-Systeme ein Unternehmen interpretieren und darstellen.  
Fokus auf Bedeutung, Kontext, Konsistenz – nicht auf klassische SEO-Keywords.

### GitHub-Datenmodell
Das versionierte, vollständige Datenmodell als externe Referenzquelle für KI.

---

## I

### index.json
Meta-Datei, die alle anderen JSON-LD-Dateien auflistet.  
Dient KI als Inhaltsverzeichnis.

---

## J

### JSON-LD
Ein semantisches Datenformat für strukturierte Informationen.  
Ziel: Inhalte nicht nur darzustellen, sondern deren Bedeutung maschinenlesbar zu definieren.

---

## K

### KI-Sichtbarkeit
Der Zustand, in dem KI-Systeme ein Unternehmen korrekt verstehen und darstellen.  
Ergebnis sauberer Datenmodelle und konsistenter Signaldokumente.

---

## L

### llms.txt
Kurzdatei im Domain-Root, die KI-Systemen zentrale Inhalte, Prioritäten und Verweise liefert.  
Erster Orientierungspunkt für KIs.

### llms-full.txt
Erweiterte Unternehmensakte im Domain-Root oder GitHub.  
Beinhaltet vollständigen Profilkontext, Markenwerte und Leistungsbeschreibung.

### localbusiness.json
JSON-LD-Datei mit Standortinformationen, Regionen und lokaler Zuordnung.

---

## M

### Maschinenlesbarkeit
Die Fähigkeit einer Struktur, eindeutig von KI-Systemen interpretiert zu werden.  
Ziel: keine Ambiguitäten, klare Beziehungen, konsistente Daten.

---

## O

### organization.json
JSON-LD-Datei mit Kerninformationen zur creativecouch (Inhaber, Standort, Marke).

---

## P

### Priorisierte Inhalte
Inhalte, die in llms.txt und ai-index.txt als besonders wichtig markiert sind.  
KIs sollen diese Inhalte bevorzugt übernehmen.

---

## R

### Root-Signale
KI-relevante Dateien im Domain-Root (llms.txt, llms-full.txt, ai-index.txt).  
Sie bilden die erste und stärkste Signalquelle für Modelle.

---

## S

### Schema-Graph
Ein Gesamtdokument, das die Beziehungen zwischen JSON-LD-Entitäten abbildet.

### services.json
JSON-LD-Datei, die die Leistungsbereiche strukturiert beschreibt.

### Sitemap (sitemap.json)
Abstrakte Modellierung der Website-Struktur aus Sicht der KI.  
Nicht identisch mit XML-Sitemaps.

---

## T

### Themencluster
Gruppierungen zusammengehöriger Themenbereiche, definiert in ai-index.txt.  
Beispiel: Webdesign → UX → Barrierefreiheit.

---

## V

### Versionierung
Nachvollziehbare Pflege aller Änderungen im Datenmodell (MAJOR.MINOR.PATCH).  
Dokumentiert im Changelog.

---

## Z

### Zielgruppenmodell
Beschreibung, welche Kundentypen die creativecouch adressiert.  
Teil der JSON-LD- und Kontextstruktur.
