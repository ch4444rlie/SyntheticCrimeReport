# Synthetic Crime Data Generation Project

## Overview
This project is a hands-on exercise in generating synthetic crime data and structuring it as XML, while exploring government data standards through the **National Information Exchange Model (NIEM)**. NIEM is a U.S. framework for standardizing data tagging to ensure interoperability across agencies. In addition to creating synthetic crime reports, it also can convert real world crime data (Chicago crime report data) from JSON to XML using NIEM-inspired tags.
![chicago_niem_structure](https://github.com/user-attachments/assets/45bb63c9-26da-42f1-bb63-4cf50197251a)
## Purpose
The goal is to:
- **Generate Synthetic Data**: Create realistic, fictional crime reports for testing or analysis.
- **Explore Government Standards**: Understand NIEM’s standardized tagging for consistent data exchange.
- **Practice Data Structuring**: Learn to tag data in XML (e.g., `nc:Incident`, `nc:Person`) to align with government requirements.

By mimicking NIEM’s structure without strict validation, the project emphasizes data creation and tagging concepts.

## Features
- **Synthetic Data Generation**: Produces fictional crime reports with fields like Incident ID, Date, Crime Type, Location, Victim/Suspect Names, and Ages using `Faker`.
- **Real World Data Conversion**: Transforms Chicago crime JSON data (From CPD's CLEARMAP) into XML with NIEM-like tags.
- **NIEM-Inspired XML**: Uses NIEM namespaces (`nc:`, `j:`, `s:`) and elements like `nc:Incident` and `j:IncidentReportingOfficial`.
- **Well-Formed XML**: Ensures syntactically correct XML with proper character escaping.

## Project Structure
- **Input**:
  - Synthetic data: Generated using `Faker` and `pandas`.
  - Chicago data: JSON files in `chicago_report/` with fields like `report_number`, `date_time`, `offense`, etc.
- **Output**:
  - `synthetic_output/crime_reports.xml`: XML for synthetic crime reports.
  - `niem_chicago_output/[filename]_niem.xml`: XML for converted Chicago data.

## How It Works
1. **Synthetic Data Generation** (`Cell 2`):
   - Generates 10 fictional crime reports using `Faker`.
   - Stores data in a `pandas` DataFrame.
2. **XML Generation for Synthetic Data** (`Cell 3`):
   - Converts DataFrame to XML with `<IncidentCollection>` root.
   - Uses NIEM-inspired tags (e.g., `nc:Incident`, `nc:Person`).
   - Outputs to `synthetic_output/crime_reports.xml`.
3. **XML Generation for Chicago Data** (`Cell 6`):
   - Reads JSON from `chicago_report/`.
   - Maps fields to NIEM-like XML under `<nc:Incident>`.
   - Outputs to `niem_chicago_output/[filename]_niem.xml`.
4. **Well-Formedness Check** (`Cell 4`):
   - Verifies XML syntax using `xml.etree.ElementTree`, without NIEM validation.

## Why NIEM?
The **National Information Exchange Model (NIEM)** standardizes data sharing for U.S. agencies (e.g., law enforcement). It uses a common XML vocabulary to ensure interoperability. This project uses NIEM-inspired tags to:
- Practice standardized data structuring.
- Understand government requirements for data exchange.
- Simulate real-world tagging scenarios.



