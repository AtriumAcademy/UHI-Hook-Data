# UHI Hook Directory — Developer Data Export

This repository contains a PII-scrubbed export of the [Uniswap Hook Incubator (UHI) Hook Directory](https://hooks.atrium.academy), maintained by [Atrium Academy](https://atrium.academy).

It is intended for developers who want to explore, search, or build tools on top of the hook project data — including using AI tools, RAG pipelines, or custom scripts.

---

## Files

### `hook_directory_clean.csv`
A structured table of all **556 hook submissions** across cohorts UHI1–UHI8.

| Column | Description |
|---|---|
| `Name` | Project name |
| `Active?` | Whether the project is currently active |
| `Cohort` | Which UHI cohort the project was submitted in (UHI1–UHI8) |
| `Created` | Submission timestamp |
| `Date` | Project date (if provided) |
| `Description` | Short project description |
| `Integrations` | External protocols/tools integrated (e.g. Chainlink, EigenLayer) |
| `Prize` | Prize category targeted |
| `Submission Type` | Type of submission |
| `Tags` | Categorisation tags (e.g. DEX, DeFi, LP Fees, Security) |

Best for: filtering by cohort/tags, building spreadsheets, quick lookups, data analysis.

### `hook_directory_clean.md`
A combined Markdown file containing **562 entries** — one section per hook project — including full subpage content such as problem statements, impact descriptions, team bios, GitHub links, demo videos, and more.

Best for: feeding into AI tools, Claude Projects, RAG pipelines, semantic search, or any use case that benefits from rich prose context.

---

## Usage Examples

**Fetch the raw CSV directly:**
```bash
curl -O https://raw.githubusercontent.com/atriumacademy/hook-directory-data/main/hook_directory_clean.csv
```

**Load into Python:**
```python
import pandas as pd
df = pd.read_csv("https://raw.githubusercontent.com/atriumacademy/hook-directory-data/main/hook_directory_clean.csv")
print(df[df["Tags"].str.contains("Security", na=False)])
```

**Use with AI tools:**
Upload `hook_directory_clean.md` directly to a Claude Project, ChatGPT file upload, or any RAG tool to enable natural language search across all hook projects.

---

## Privacy

All personally identifiable information (PII) has been removed from this export, including:
- Email addresses
- Phone numbers
- "Created by" (Notion user identity) fields

The data reflects project-level information only.

---

## Data Source & Updates

This export is generated from the [UHI Hook Directory](https://hooks.atrium.academy) Notion database. It is updated manually when significant changes are made to the directory.

To submit your own hook project, visit: [hooks.atrium.academy](https://hooks.atrium.academy)

---

## Legal Disclaimer

Hook code referenced in this data is offered on an "as-is" basis and has not been audited for security, reliability, or compliance with any specific standards or regulations. Users are encouraged to review and test independently before deploying in any environment. See [Atrium Academy's full disclaimer](https://atrium.academy/terms-of-service#legal-disclaimer) for details.
