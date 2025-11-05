# Citation Protocol

## Overview

This document defines the citation protocol for AxiomHive US Manufacturing Intelligence. Our system ensures that every data point, analysis, and insight can be traced back to its original source through a deterministic, transparent, and machine-readable citation system.

## Core Principles

### 1. Determinism
- Citations are generated using deterministic algorithms
- Same input data always produces same citation
- No random components in citation generation
- Version-specific references maintained

### 2. Transparency
- Full source information always visible
- Clear lineage from raw data to derived insights
- Transformation steps documented
- No hidden data processing

### 3. Machine-Readability
- Structured citation format (JSON, YAML)
- Programmatic access to citation metadata
- API endpoints for citation lookup
- Standard schema for all citations

### 4. Human-Readability
- Clear, understandable citation format
- Standard academic-style references available
- Plain language source descriptions
- Visual citation chains in reports

## Citation Structure

### Metadata Fields

Every data point in the system includes the following citation metadata:

```json
{
  "citation_id": "unique-identifier",
  "source": {
    "name": "Source Organization",
    "dataset": "Dataset Name",
    "url": "https://source.url/dataset",
    "access_date": "YYYY-MM-DD",
    "publication_date": "YYYY-MM-DD",
    "version": "version-identifier"
  },
  "data_point": {
    "field": "field-name",
    "value": "data-value",
    "timestamp": "YYYY-MM-DD HH:MM:SS",
    "location": "file-path or API-endpoint"
  },
  "lineage": [
    {
      "step": 1,
      "operation": "operation-name",
      "script": "script-path",
      "timestamp": "YYYY-MM-DD HH:MM:SS"
    }
  ],
  "verification": {
    "hash": "sha256-hash-of-source-data",
    "checksum": "md5-checksum",
    "signature": "digital-signature-if-available"
  }
}
```

### Citation ID Format

Citation IDs follow the format:
```
[SOURCE_CODE]-[DATASET_CODE]-[TIMESTAMP]-[RECORD_HASH]
```

Examples:
- `ISM-MFG-20240115-a7f3d9e2`
- `SP-MANU-20240120-b4e8c1a6`
- `FRB-INDPRO-20240201-c9d2e5f7`

## Data Source Citations

### ISM Manufacturing Index

**Format:**
```
Institute for Supply Management (ISM). "Manufacturing PMI". 
[Month Year]. Retrieved [Access Date] from https://www.ismworld.org/
```

**Structured Citation:**
```json
{
  "source_code": "ISM",
  "source_name": "Institute for Supply Management",
  "dataset": "Manufacturing PMI",
  "url": "https://www.ismworld.org/supply-management-news-and-reports/reports/ism-report-on-business/pmi/",
  "license": "Public Domain",
  "update_frequency": "Monthly"
}
```

### S&P Global Manufacturing PMI

**Format:**
```
S&P Global. "US Manufacturing PMI". 
[Month Year]. Retrieved [Access Date] from https://www.pmi.spglobal.com/
```

**Structured Citation:**
```json
{
  "source_code": "SP",
  "source_name": "S&P Global",
  "dataset": "US Manufacturing PMI",
  "url": "https://www.pmi.spglobal.com/Public/Home/PressRelease/",
  "license": "Publicly Available",
  "update_frequency": "Monthly"
}
```

### Federal Reserve Industrial Production

**Format:**
```
Board of Governors of the Federal Reserve System. "Industrial Production: Manufacturing". 
FRED, Federal Reserve Bank of St. Louis. Retrieved [Access Date] from https://fred.stlouisfed.org/
```

**Structured Citation:**
```json
{
  "source_code": "FRB",
  "source_name": "Federal Reserve",
  "dataset": "Industrial Production Index",
  "url": "https://fred.stlouisfed.org/series/IPMAN",
  "license": "Public Domain",
  "update_frequency": "Monthly"
}
```

## Citation Workflow

### Step 1: Data Ingestion

1. **Download/Fetch** raw data from source
2. **Record** exact timestamp of acquisition
3. **Calculate** cryptographic hash of source file
4. **Generate** citation ID
5. **Store** citation metadata alongside raw data

```python
import hashlib
from datetime import datetime

def create_citation(source_code, dataset_code, data_content):
    timestamp = datetime.now().strftime('%Y%m%d')
    record_hash = hashlib.sha256(data_content.encode()).hexdigest()[:8]
    citation_id = f"{source_code}-{dataset_code}-{timestamp}-{record_hash}"
    return citation_id
```

### Step 2: Data Transformation

1. **Log** every transformation operation
2. **Link** output to input citations
3. **Record** transformation code version
4. **Update** lineage chain
5. **Generate** new citation ID for derived data

```python
def add_lineage_step(citation, operation, script_path):
    lineage_entry = {
        "step": len(citation["lineage"]) + 1,
        "operation": operation,
        "script": script_path,
        "timestamp": datetime.now().isoformat(),
        "parent_citations": citation.get("parent_citations", [])
    }
    citation["lineage"].append(lineage_entry)
    return citation
```

### Step 3: Analysis & Reporting

1. **Include** citation metadata in all outputs
2. **Generate** human-readable references
3. **Provide** API access to full citation chain
4. **Display** visual lineage diagrams
5. **Export** citation data with analysis results

### Step 4: Citation Verification

1. **Verify** source data availability
2. **Check** hash matches against source
3. **Validate** lineage chain integrity
4. **Test** reproducibility of transformations
5. **Report** any discrepancies or changes

## Citation in Reports

### Format Requirements

**All reports must include:**

1. **Data Sources Section**: List all primary data sources with full citations
2. **Methodology Section**: Document all transformations with code references
3. **Footnotes/Endnotes**: Cite specific data points in text
4. **Appendix**: Full citation metadata in machine-readable format

### Example Report Citation

**In-Text Citation:**
```
The ISM Manufacturing PMI increased to 52.3 in January 2024 [ISM-MFG-20240115-a7f3d9e2],
while the S&P Manufacturing PMI reached 51.5 [SP-MANU-20240120-b4e8c1a6].
```

**Reference List:**
```
[ISM-MFG-20240115-a7f3d9e2] Institute for Supply Management. 
"Manufacturing PMI". January 2024. Retrieved February 1, 2024 from 
https://www.ismworld.org/supply-management-news-and-reports/reports/ism-report-on-business/pmi/january/

[SP-MANU-20240120-b4e8c1a6] S&P Global. "US Manufacturing PMI". 
January 2024. Retrieved February 1, 2024 from 
https://www.pmi.spglobal.com/Public/Home/PressRelease/c60e8e8a8e8
```

## API Integration

### Citation Lookup Endpoint

```
GET /api/v1/citation/{citation_id}
```

**Response:**
```json
{
  "citation_id": "ISM-MFG-20240115-a7f3d9e2",
  "source": {...},
  "data_point": {...},
  "lineage": [...],
  "verification": {...},
  "downloadable_source": "https://api.example.com/source/ISM-MFG-20240115-a7f3d9e2"
}
```

### Lineage Trace Endpoint

```
GET /api/v1/lineage/{citation_id}
```

**Response:**
```json
{
  "citation_id": "DERIVED-ANALYSIS-20240201-x9y8z7w6",
  "parent_citations": [
    "ISM-MFG-20240115-a7f3d9e2",
    "SP-MANU-20240120-b4e8c1a6"
  ],
  "lineage_chain": [...],
  "transformation_code": "https://github.com/.../analysis.py#v1.2.3"
}
```

## Validation & Testing

### Automated Citation Checks

1. **Schema Validation**: Verify all citations match schema
2. **Uniqueness Test**: Ensure no duplicate citation IDs
3. **Link Validation**: Verify all source URLs are accessible
4. **Hash Verification**: Check data integrity via stored hashes
5. **Reproducibility Test**: Re-run transformations to verify lineage

### Manual Review Process

1. **Quarterly Audit**: Review sample of citations for accuracy
2. **Source Verification**: Confirm sources are authoritative
3. **Documentation Review**: Check citation documentation completeness
4. **User Feedback**: Collect and address citation-related issues

## Best Practices

### For Data Engineers

1. Always capture citation metadata at ingestion
2. Never skip lineage recording for convenience
3. Use provided citation generation functions
4. Test citation integrity before committing data
5. Document any citation schema changes

### For Analysts

1. Include citations in all analysis outputs
2. Verify data provenance before using data
3. Document data transformations thoroughly
4. Use citation IDs in code comments
5. Report missing or incorrect citations

### For Report Authors

1. Cite all data sources explicitly
2. Use both human and machine-readable formats
3. Include full citation metadata in appendices
4. Provide links to raw data when possible
5. Update citations when data is refreshed

## Maintenance & Updates

### Version Control

- Citation protocol version: 1.0.0
- Last updated: 2024-01-15
- Next review: 2024-04-15
- Change log maintained in Git history

### Schema Evolution

- Backward compatibility required for all changes
- Deprecation warnings for 6 months minimum
- Migration scripts provided for major updates
- Community feedback incorporated quarterly

### Support & Questions

- Issues: GitHub Issues
- Discussions: GitHub Discussions
- Documentation: https://docs.example.com/citations
- Contact: data-team@example.com
