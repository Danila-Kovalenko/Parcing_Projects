# Parsing Projects

Dieses Repository bündelt zwei Python-Projekte zum **Parsen von PEP-Dokumenten (Python Enhancement Proposals)**.  
Ziel ist es, den aktuellen Stand der PEPs automatisiert zu sammeln und als CSV-Ergebnisse abzulegen.

## Projektinhalt

### 1) Beautiful Soup Parser
Pfad: `Beautiful_Soup_Parser/Beautiful_Soup_Parser`

- Parser auf Basis von **Requests + BeautifulSoup**.
- Extrahiert Informationen zu PEPs und erzeugt Ergebnisdateien im CSV-Format.
- Enthält Unit-Tests (`pytest`) für zentrale Module.

### 2) Scrapy-basierter Parser
Pfad: `Scrapy_Based_Parser/Scrapy_Based_Parser`

- Crawler auf Basis von **Scrapy** (`pep_parse/spiders/pep.py`).
- Sammelt PEP-Daten, validiert/aggregiert Statusinformationen und schreibt Berichte nach `results/`.
- Ebenfalls mit Tests abgesichert.

## Schnellstart

> Voraussetzung: Python 3.9+ (empfohlen)

### A) Beautiful Soup Parser ausführen

```bash
cd Beautiful_Soup_Parser/Beautiful_Soup_Parser
python -m venv venv
source venv/bin/activate  # unter Windows: venv\Scripts\activate
pip install -r requirements.txt
python -m src.main
```

### B) Scrapy Parser ausführen

```bash
cd Scrapy_Based_Parser/Scrapy_Based_Parser
python -m venv venv
source venv/bin/activate  # unter Windows: venv\Scripts\activate
pip install -r requirements.txt
scrapy crawl pep
```

## Tests

In jedem Teilprojekt können die Tests separat ausgeführt werden:

```bash
pytest
```

## Ergebnis

Beide Implementierungen lösen die gleiche Kernaufgabe auf unterschiedliche Weise:

- **Beautiful Soup** für einen leichteren, direkten Ansatz.
- **Scrapy** für einen crawler-orientierten, erweiterbaren Ansatz.

So eignet sich das Repository sowohl zum Lernen als auch als Grundlage für eigenes Web-Scraping von PEP-Daten.
