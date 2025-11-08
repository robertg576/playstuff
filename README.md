# NetSapiens API Docs – Expanded (CloudWorxCX)

This folder contains machine-parsed, expanded documentation for the NetSapiens / CloudWorxCX APIs.

## Quick Stats
- **Pages collected:** 87
- **Total words:** 193639
- **Average words/page:** 2225
- **Endpoints discovered:** 30
  - Phones: 2
  - Numbers: 2
  - Domains: 20
  - Users: 10

## Key Artifacts
- `ns_api_docs_expanded.md` – Combined readable Markdown
- `ns_api_docs_summary.csv` – Per-page summary (title, counts)
- `endpoints_all.json` / `endpoints_all.csv` – Parsed HTTP method+path catalog
- `endpoints_phones.csv`, `endpoints_numbers.csv`, `endpoints_domains.csv`, `endpoints_users.csv`

> Large raw HTML pages are not stored in Git to keep the repo lean. If available,
> check the **Releases** tab for a downloadable tarball of HTML.

## Usage Examples
Search for all phone number endpoints:
```bash
grep -i "number" endpoints_all.csv | head
```

List the first 10 endpoints:
```bash
jq -r '.endpoints[0:10] | map([.method, .path, .title] | @tsv) | .[]' endpoints_all.json
```

Filter for domain-scoped calls:
```bash
awk -F, 'tolower($2) ~ /\/domains\// {print}' endpoints_all.csv | head
```

---

*Generated on 2025-11-08 03:26:31Z.*
