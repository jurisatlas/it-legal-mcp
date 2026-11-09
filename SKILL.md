---
name: it-legal-mcp-skill
description: Official Italy (IT) legislation, multi-tier court precedent research, and citation verification skill.
version: 2.0.0
author: JurisAtlas
license: MIT
---

# Italy Legal Research & Multi-Tier Case Law Skill (`it-legal-mcp`)

Use this skill whenever the user asks a legal question, drafts a pleading or contract, or researches case law across any judicial instance in **Italy (IT)**.

## Verification & Research Rules

1. **Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `ECLI:IT:CASS:2024:1234CIV or Legge 241/1990`).
2. **Multi-Tier Judicial Coverage:**
   - **First Instance (Trial / Municipal / District):** Tribunali Ordinari, Giudici di Pace & Tribunali Amministrativi Regionali (TAR across 20 Regions)
   - **Second Instance (Cantonal / Regional / Appellate):** 26 Corti d'Appello, Corti di Giustizia Tributaria di secondo grado & Consiglio di Giustizia Amministrativa
   - **Supreme & Constitutional Instance:** Corte Suprema di Cassazione, Consiglio di Stato & Corte Costituzionale
   - **Primary Tiered Database:** ItalgiureWeb / Banca Dati di Merito (Tribunali & Corti d'Appello), Giustizia Amministrativa (TAR/CdS) & Corte Costituzionale (`https://www.giustizia-amministrativa.it`)
