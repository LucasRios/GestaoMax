# GestaoMax

> Auxiliary functions, SQL utilities, and geospatial data assets used across the GestaoMax platform — a multi-tenant SaaS for business management built in .NET and SQL Server.

---

## Overview

This repository contains shared resources that support the GestaoMax ecosystem:

- **SQL Server functions** — reusable T-SQL scalar functions for string manipulation, formatting, and statistical trend analysis
- **GeoJSON maps** — Brazilian municipal boundary data for all states, used in interactive map dashboards built with Google Charts and AmCharts

---

## Contents

### `SQL/` — T-SQL Utility Functions

| File | Description |
|---|---|
| `Função Retira Acento.txt` | Removes diacritics/accents from strings — used for normalization and search indexing |
| `Função Split.txt` | String split function — splits delimited strings into table rows |
| `Função UFirst.txt` | Capitalizes the first letter of each word (title case) |
| `Função formata números.txt` | Number formatting — applies locale-aware numeric masks |
| `Função só números.txt` | Strips all non-numeric characters from a string |
| `Função tendência MP.txt` | Moving average trend calculation for time-series data |
| `Função tendência RL.txt` | Linear regression trend line calculation for time-series data |
| `Importar_Planilha.txt` | Script for importing spreadsheet data into SQL Server tables |

### `Mapas/` — Brazilian GeoJSON Data

Municipal boundary polygons for all 26 Brazilian states + Federal District, formatted for use with mapping libraries.

| File pattern | Coverage |
|---|---|
| `{state_code}-mun.json` | All municipalities for the given state IBGE code |
| `100-mun.json` | All Brazilian municipalities (national dataset) |
| `SP-ZN.json` / `SP-ZN2.json` | São Paulo city — zone segmentation |
| `SP-subprefeitura.json` | São Paulo city — sub-prefecture boundaries |
| `geojs-35-mun.json` | São Paulo state — GeoJS-compatible format |

---

## Usage Context

These assets are consumed by the GestaoMax platform to:
- Normalize and process customer-submitted data through T-SQL pipelines
- Render interactive geographic dashboards showing business metrics by municipality, state, or region
- Support multi-tenant reporting with configurable geographic granularity

---

## Tech Stack

- **SQL Server** — T-SQL scalar functions, compatible with SQL Server 2012+
- **GeoJSON** — RFC 7946 compliant geographic data
- **Google Charts / AmCharts** — front-end map rendering consumers

---

## License

MIT
