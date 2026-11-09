# Italy Legal Research MCP Server (`it-legal-mcp`)

**[Italiano](#lang-it) | [English Documentation](#english-documentation)**

---

<a id="lang-it"></a>
## Server MCP di Legislazione e Giurisprudenza (`it-legal-mcp`) — Italiano

### Informazioni su questo repository

Questo repository fornisce un server Model Context Protocol (MCP) che collega la vostra applicazione IA (Claude Desktop, Cursor, Windsurf, VS Code / Copilot, Cline, Continue.dev o Antigravity) direttamente ai portali legislativi ufficiali e alle banche dati giurisprudenziali per **Italy** (tribunali di primo grado, tribunali cantonali / corti d'appello e corti supreme o costituzionali).

### Installazione rapida (Selezione del client IA)

1. **Download:** Fare clic su **`<> Code` -> `Download ZIP`** ed estrarre la cartella sul computer.
2. **Avvio:** Fare doppio clic su **`Click_Here_To_Install_Windows.bat`** (Windows) o **`Click_Here_To_Install_Mac.command`** (macOS).
3. **Scelta dell'applicazione IA:** Selezionare i programmi IA utilizzati (Claude, Cursor, Windsurf, VS Code, Antigravity), avviare l'installazione e riavviare il client IA selezionato.

**Nota sulla sicurezza:** Lo strumento opera esclusivamente in sola lettura e non accede ai file personali presenti sul computer.

### Gradi di giudizio e fonti ufficiali

| Grado di giudizio | Organi giudiziari coperti |
|:---|:---|
| **Primo grado (Tribunali di prima istanza)** | Tribunali Ordinari, Giudici di Pace & Tribunali Amministrativi Regionali (TAR across 20 Regions) |
| **Secondo grado (Tribunali cantonali / Corti d'Appello)** | 26 Corti d'Appello, Corti di Giustizia Tributaria di secondo grado & Consiglio di Giustizia Amministrativa |
| **Corti Supreme e Costituzionali** | Corte Suprema di Cassazione, Consiglio di Stato & Corte Costituzionale |

- **Normattiva - Portale della Legge Vigente (normattiva.it):** [https://www.normattiva.it](https://www.normattiva.it) (`normattiva.it`, `gazzettaufficiale.it`, `brocardi.it`)
- **ItalgiureWeb / Banca Dati di Merito (Tribunali & Corti d'Appello), Giustizia Amministrativa (TAR/CdS) & Corte Costituzionale:** [https://www.giustizia-amministrativa.it](https://www.giustizia-amministrativa.it) (`cortecostituzionale.it`, `cortedicassazione.it`, `giustizia-amministrativa.it`, `brocardi.it`)

---

<a id="english-documentation"></a>
## English Documentation

Model Context Protocol (MCP) server providing live, read-only access to **Italy (IT)** legislation, official gazettes, multi-tier judicial decisions (First Instance, Regional/Cantonal/Appellate, and Supreme/Constitutional courts, including HTML and PDF full-text extraction), and statutory citation verification across all major AI clients (**ChatGPT Desktop, OpenAI Codex CLI, Claude Desktop, Claude Code CLI, Cursor, Windsurf, VS Code / GitHub Copilot / Cline / Roo Code, Google Antigravity / Gemini CLI, Perplexity, and Continue.dev**).

---

### Interactive Desktop Setup (Select Your AI Assistant)

This package includes a graphical installer for legal practitioners and non-technical users that lets you select which AI application(s) you use:

1. **Download:** Click **`<> Code`** at the top right of this repository, select **`Download ZIP`**, and extract the folder to your computer.
2. **Run the Setup Utility:**
   - **Windows:** Double-click `Click_Here_To_Install_Windows.bat`
   - **macOS:** Double-click `Click_Here_To_Install_Mac.command`
3. **Select Your AI Client(s) & Connect:** Check the box(es) for the AI assistant(s) installed on your computer (**ChatGPT Desktop & OpenAI Codex CLI**, **Claude Desktop & Claude Code CLI**, **Cursor**, **Windsurf**, **VS Code / GitHub Copilot / Cline / Roo Code**, **Google Antigravity / Gemini CLI**, or **Perplexity / Continue.dev**), click **Install to Selected AI Clients**, and restart your selected AI application.

**System Integrity Note:** The setup utility operates strictly in read-only mode with respect to your personal files and documents. It installs an isolated Python runtime inside the extracted folder and registers the server entry only in the AI client configuration files you select.

---

### Multi-Tier Judicial Hierarchy & Live Indexed National Archives

This server performs live queries across the full judicial hierarchy and official legal archives of **Italy**, extracting full text from both HTML pages and official court/gazette PDF judgments:

| Judicial Tier | Covered Courts & Tribunals |
|:---|:---|
| **Tier 1 — First Instance** | Tribunali Ordinari, Giudici di Pace & Tribunali Amministrativi Regionali (TAR across 20 Regions) |
| **Tier 2 — Regional / Cantonal / Appellate** | 26 Corti d'Appello, Corti di Giustizia Tributaria di secondo grado & Consiglio di Giustizia Amministrativa |
| **Tier 3 — Supreme & Constitutional** | Corte Suprema di Cassazione, Consiglio di Stato & Corte Costituzionale |

#### Official Portals & Live Indexed Domains

- **National Legislation & Official Gazette:** Normattiva - Portale della Legge Vigente (normattiva.it) — [https://www.normattiva.it](https://www.normattiva.it)
  - *Indexed Legislation Domains:* `normattiva.it`, `gazzettaufficiale.it`, `brocardi.it`
- **Court Decisions & Jurisprudence Archives:** ItalgiureWeb / Banca Dati di Merito (Tribunali & Corti d'Appello), Giustizia Amministrativa (TAR/CdS) & Corte Costituzionale — [https://www.giustizia-amministrativa.it](https://www.giustizia-amministrativa.it)
  - *Indexed Judicial & Open Case Law Domains:* `cortecostituzionale.it`, `cortedicassazione.it`, `giustizia-amministrativa.it`, `brocardi.it`

---

### Available MCP Tools

| Tool | Description |
|:---|:---|
| `search_legislation` | Searches enacted statutes, codes, decrees, and official gazette publications in Italy. |
| `search_case_law` | Searches national jurisprudence and open judicial archives for Italy. |
| `search_tiered_court_decisions` | Filters case law specifically by judicial instance (`first_instance`, `appellate_regional`, `supreme_constitutional`) or specific regional/cantonal/district court. |
| `list_court_hierarchy` | Returns the complete 3-tier court structure and supported regional court filters for Italy. |
| `get_legal_document_markdown` | Retrieves full statutory or judicial texts (both HTML and official `.pdf` court judgments) and converts them into clean Markdown. |
| `verify_citation` | Validates statutory and case law citations against official registries. |

---

<details>
<summary><b>Manual Configuration for Developers (Optional)</b></summary>

```json
{
  "mcpServers": {
    "it-legal-mcp": {
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/it-legal-mcp/archive/refs/heads/main.zip",
        "it-legal-mcp"
      ]
    }
  }
}
```
</details>
