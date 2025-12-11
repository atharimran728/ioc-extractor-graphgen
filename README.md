# IOC Extractor & Graph Generator

A hardened IOC extraction utility built for analysts who want clean, noise-free indicators from malware samples, memory dumps, and sandbox outputs. The tool parses raw bytes, identifies domains across ASCII and UTF-16 contexts, filters garbage (e.g., `.exe`, `.tmp`, `.jpg` false positives), normalizes results, and generates SOC-ready intelligence outputs.

---

## Features
- Extracts domains from raw bytes, ASCII, and UTF-16LE strings  
- Strong validation to eliminate junk indicators  
- Automatic hashing (MD5, SHA1, SHA256)  
- Generates:
  - JSON output  
  - GraphML graph (for Maltego, Gephi, yEd)  
  - CSV node/edge files (SIEM/TI ingestion)  
- Creates file → hash → domain relationship graph  
- SOC-aligned design: fast triage, quick pivoting, reliable enrichment

---

## Use Cases
- Incident Response investigations  
- Malware reverse-engineering pipelines  
- Threat-intel enrichment  
- SOC triage automation  
- Cuckoo Sandbox post-processing  
- Memory/string extraction cleanup

---

## Usage
```bash
python ioc_extractor-graphing.py -f sample.bin --json --graphml --csv --show-count
```

Outputs are written to a directory named after the file.

## Output Structure
```
<filename>/
   ├── <filename>_json.json
   ├── <filename>_graph.graphml
   ├── <filename>_nodes.csv
   ├── <filename>_edges.csv
```

## Why This Matters for SOC Teams

It cuts junk domains, handles messy encodings, and produces relationship graphs analysts can pivot on immediately. Faster triage. Cleaner alerts. Better correlation.




`
