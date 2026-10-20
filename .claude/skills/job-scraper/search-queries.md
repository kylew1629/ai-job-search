# Search Queries for Job Scraper


## Installed portal CLIs (primary for `/scrape`)

`/scrape` discovers every portal skill under `.agents/skills/*/SKILL.md` and runs its CLI first. Shipped country-agnostic CLIs include `linkedin-search` and `freehire-search`; Danish demos and any skill you add with `/add-portal` are included the same way. You do **not** need a matching `site:` line below for those CLIs to run.

The `site:` query templates in this file are the **WebSearch fallback** — for portals without a CLI, company career pages, or when a CLI fails.

**Language scope:** write every query category in every language listed in your CLAUDE.md Languages table (typically 1-2, sometimes more). A posting requiring a language you have *not* declared, as a job condition, is excluded before scoring; a posting requiring a *higher level* than you declared in a language you *do* work in is flagged for your own judgment, not excluded — see `04-job-evaluation.md`'s Language Gate, the single source of truth for this rule. Translate each category's keywords rather than machine-translating word-for-word (e.g. "Frontend Developer" -> "Desarrollador Frontend", not a literal word-for-word translation) if you work in more than one language.

## Search Sites

Queries are written in **English only** (Kyle's Spanish is basic, not a working language).

Primary:
- **linkedin.com/jobs** - covered by the `linkedin-search` CLI. Use location "Houston, Texas, United States" plus a remote (United States) pass.
- **freehire** - covered by the `freehire-search` CLI (tech-leaning; useful for Priority 4).
- **indeed.com** - largest US general board (WebSearch fallback; consider `/add-portal` for it).
- **Danish portals** (jobindex, jobbank, jobdanmark, jobnet) - stay **disabled**; not Kyle's market.

Secondary (company career pages via `site:` queries):
- Utilities: centerpointenergy.com, entergy.com, ercot.com
- Equipment / automation: siemens.com, se.com (Schneider), abb.com, eaton.com, emerson.com, rockwellautomation.com
- EPC / design: burnsmcd.com, kiewit.com, bv.com (Black & Veatch), kbr.com, worley.com, jacobs.com, woodplc.com
- Other Houston engineering employers: NRG, Calpine, Quanta Services, Mitsubishi Power, GE Vernova, Baker Hughes, SLB, Halliburton (onshore/engineering roles only)

## Query Categories

Location terms: "Houston, TX" (and suburbs: Katy, Sugar Land, The Woodlands, Pasadena, Pearland, Cypress, Spring, Baytown) or "remote".

### Priority 1: Electrical design & power engineering (entry level)

Strongest and most desired direction: power, utilities, electrical/panel design.

```
site:linkedin.com/jobs "Electrical Engineer I" Houston
site:linkedin.com/jobs "entry level electrical engineer" Houston
site:linkedin.com/jobs "Electrical Design Engineer" Houston
site:linkedin.com/jobs "Power Systems Engineer" "new grad" OR "entry level" Houston
site:linkedin.com/jobs "Associate Electrical Engineer" Houston
"EIT" "electrical engineer" Houston "0-2 years"
```
Title variants: Electrical Engineer I, Junior Electrical Engineer, Associate Electrical Engineer, Electrical Engineer in Training (EIT), Electrical Design Engineer, Power Systems Engineer, Distribution Engineer, Substation Engineer, Protection & Controls Engineer (entry), Engineer Development Program.

### Priority 2: Controls, automation & industrial / power quality

Domain expertise: industrial panels, Modbus/metering, controls.

```
site:linkedin.com/jobs "Controls Engineer" entry level Houston
site:linkedin.com/jobs "Automation Engineer" Houston "new grad"
site:linkedin.com/jobs "Instrumentation and Controls" engineer Houston
site:linkedin.com/jobs "power quality" OR "metering" engineer Houston
site:linkedin.com/jobs "Test Engineer" electrical Houston
site:linkedin.com/jobs "Field Engineer" electrical Houston -offshore
```
Title variants: Controls Engineer, Automation Engineer, I&C Engineer, SCADA Engineer, Panel Design Engineer, Electrical Test Engineer, Commissioning Engineer, Field Service Engineer (check travel %), Metering Engineer.

### Priority 3: Applications / technical sales & embedded

Adjacent roles leveraging Hydraquip customer work and capstone.

```
site:linkedin.com/jobs "Applications Engineer" electrical Houston
site:linkedin.com/jobs "Sales Engineer" electrical Houston "entry level"
site:linkedin.com/jobs "Embedded" engineer Houston "entry level" ESP32 OR C++
site:linkedin.com/jobs "Hardware Engineer" Houston "new grad"
```

### Priority 4: EE-adjacent tech & data (wider net)

Data/tech roles where an EE background is an advantage. Prefer energy/industrial companies.

```
site:linkedin.com/jobs "Data Analyst" energy OR utility Houston
site:linkedin.com/jobs "Engineering Data Analyst" Houston
site:linkedin.com/jobs "OT" OR "SCADA" analyst Houston
site:linkedin.com/jobs "IoT engineer" OR "Python" "electrical" Houston
site:linkedin.com/jobs "Technical Analyst" energy Houston remote
```

## Location Filter

- **Ideal:** Houston city limits, Energy Corridor, Westchase, Greenway, Downtown/Midtown, Galleria; or fully remote (US)
- **Acceptable:** Katy, Sugar Land, Pasadena, Pearland, Bellaire, Spring, Cypress, Humble, Missouri City; hybrid roles anywhere in the metro
- **Borderline:** The Woodlands, Conroe, Baytown, La Porte, Deer Park, Freeport, Tomball (flag commute)
- **Too far:** outside the Houston metro unless fully remote (Austin, Dallas, San Antonio, Beaumont, etc.); any offshore assignment
- **Travel:** up to 35% OK; above 35% or rotational offshore = exclude

## Experience Filter

New grad (May 2026). Prefer "entry level", "new grad", "0-2 years", "EIT". Include "1-3 years" roles. Flag "3-5 years". Skip 5+ years.

## Language Filter

Your working languages and levels are in CLAUDE.md's Languages table. When filtering scraped results, apply `04-job-evaluation.md`'s Language Gate: a posting requiring a language you haven't declared at all is excluded; a posting requiring a higher level than you declared in a language you do work in is not excluded, flag it clearly instead (see `job-scraper/SKILL.md`'s Step 3 "Quick Fit Assessment" for how the flag surfaces in `/scrape` output). Postings simply *written* in a language you don't work in, that don't require it on the job, are fine.

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape [focus_area]" -> relevant category queries + custom focus-specific queries
