# Search Queries for Job Scraper

## Search Sites

Primary (US-focused):
- **linkedin.com/jobs** - LinkedIn job listings (filter: USA / Pacific Northwest / Remote)
- **indeed.com** - general job board
- Company career pages via Google `site:` searches for known target companies

Note: Brooks is US-based (Austin, TX), not Denmark - the Danish job portal CLIs (Jobindex, Jobnet, Jobdanmark, Jobbank) are not used.

A personal job-scoring agent already exists at `C:\Users\bkadu\Documents\jobhunt` (profile.yaml + scoring agent over an Obsidian vault) - it can be used as a reference for role/location priorities, but this skill's `/scrape` is for ad-hoc, conversational searches.

## Query Categories

### Priority 1: Protein Bioinformatics / Structural Biology

This is Brooks's strongest area and primary target - roles using AlphaFold2, protein structure prediction, structural biology pipelines, molecular dynamics, computational drug discovery, or protein design.

```
site:linkedin.com/jobs "protein structure prediction" OR AlphaFold
site:linkedin.com/jobs "computational biologist" structural biology
"bioinformatics scientist" AlphaFold OR "protein design" remote
site:linkedin.com/jobs "structural bioinformatics" OR "molecular dynamics"
```

### Priority 2: Genomics Bioinformatics

Roles using RNA-seq, WGS, single-cell, differential expression, or variant calling. Brooks has built pipelines for this but would need a few weeks to ramp up on role-specific tools.

```
site:linkedin.com/jobs "bioinformatics scientist" RNA-seq OR genomics
site:linkedin.com/jobs "computational biologist" "single-cell" OR "WGS"
"bioinformatics analyst" Snakemake OR Nextflow
```

### Priority 3: Data Analytics / Data Engineering

General data analyst, data scientist, or data engineer roles. Best fit when the domain involves biology or life sciences, but Brooks is open to other sectors - he has interviewed successfully for these (e.g. Data SEA Consulting, Toronto).

```
site:linkedin.com/jobs "data analyst" OR "data scientist" Python SQL life sciences
site:linkedin.com/jobs "data engineer" Python pipeline biotech
"data analyst" remote Python SQL
```

### Priority 4: Wet Lab / Molecular Biology

Research assistant or associate roles in protein biochemistry. Lower-paying but can be entry points into companies with computational groups. Score these higher only if based in Austin (zero living cost) or if the role offers a clear computational path.

```
site:linkedin.com/jobs "research assistant" OR "research associate" protein purification Austin
site:linkedin.com/jobs "research associate" biochemistry "computational"
```

## Location Filter

Score and flag results using these tiers (from Brooks's job search agent priorities):
- **Highest priority**: Vancouver, BC (requires employer sponsorship - flag explicitly), Seattle WA, Bellingham WA, Remote (treated as Pacific Northwest-equivalent), other Pacific Northwest cities (WA/OR)
- **Moderate priority**: Austin, TX (current location, zero housing cost - lower-paying roles more viable here); San Diego, CA (brother lives there - prefer higher-paying roles)
- **Lower priority but acceptable**: Anywhere else in the US, if the role is a strong match

## Date Filter

Only include jobs posted within the last 3 days where possible (entry-level roles fill quickly - Brooks needs to apply within 1-2 days of posting to be competitive). If posted more recently than 14 days, still include but flag if older than 3 days. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape [focus_area]" -> relevant category queries + custom focus-specific queries
