# Job Evaluation Framework

<!-- SETUP: Skill match areas and career goals are personalized by running /setup -->

## Scoring Dimensions

Evaluate each job posting against these five dimensions:

### 1. Technical Skills Match (0-100)
How well do the required/preferred skills align with the candidate's capabilities?

| Score | Meaning |
|-------|---------|
| 80-100 | Core requirements are primary skills |
| 60-79 | Most requirements match, 1-2 gaps that are learnable |
| 40-59 | Partial match, significant upskilling needed |
| 0-39 | Fundamental mismatch |

**Strong match areas:** AlphaFold2, protein structure prediction, computational biology, Python pipeline development (Pandas, NumPy, PyTorch, Biopython), Snakemake, SLURM/HPC, Bash scripting, PyMOL, BioEmu, Git
**Moderate match areas:** RNA-seq/WGS/genomics, differential expression (DESeq2), single-cell analysis, BWA/STAR/GATK/SAMtools, Nextflow, SQL, general data analysis/data engineering, statistical modeling, R/ggplot2, D3.js
**Weak match areas:** Large-scale software engineering practices (CI/CD, cloud infrastructure at scale), enterprise data platforms, people management/leadership of large teams

### 2. Experience Match (0-100)
Does work history align with what they're looking for?

| Score | Meaning |
|-------|---------|
| 80-100 | Direct experience in the same domain and role type |
| 60-79 | Related experience, transferable skills clear |
| 40-59 | Adjacent experience, would need to make the case |
| 0-39 | Unrelated experience |

**Strong:** Protein structure prediction / structural biology pipelines, computational biology research (M.Sc. Gsponer Lab, published in Communications Chemistry)
**Moderate:** Genomics bioinformatics (RNA-seq, WGS, differential expression - has built pipelines but less depth than protein work), wet-lab molecular biology/biochemistry (protein purification, ITC, plasmid work), general data analytics (Python/SQL)
**Entry-level:** Industry (non-academic) bioinformatics or data roles generally - all professional bioinformatics experience to date is academic (UBC). AI/ML evaluation work (Mercor) and teaching (Eanes ISD) are recent and outside core bioinformatics.

### 3. Behavioral/Culture Fit (0-100)
Does the role and company culture match the behavioral profile?

| Score | Meaning |
|-------|---------|
| 80-100 | Culture strongly matches behavioral preferences |
| 60-79 | Mixed signals but mostly compatible |
| 40-59 | Some friction areas |
| 0-39 | Significant culture mismatch |

**Red flags to research:** Department disorganization, work dominated by maintenance over development, poor chemistry with leadership, culture mismatches. Check reviews, media coverage, LinkedIn connections, and network contacts for insider perspective.

### 4. Location & Logistics (Pass/Fail + Notes)
- Within commute range: PASS
- Remote with occasional office: PASS
- Requires relocation: FAIL (deal-breaker)
- Frequent international travel: FLAG (discuss with user)

### 5. Career Alignment & Motivation (0-100)
Does this role advance career goals and contain tasks that energize?

| Score | Meaning |
|-------|---------|
| 80-100 | Strongly aligned with career direction, clear growth path |
| 60-79 | Good role but only partially aligned with long-term goals |
| 40-59 | Decent job but doesn't build toward career goals |
| 0-39 | Dead end or backwards step |

**Career goals:**
- Build a career in computational/protein bioinformatics (AlphaFold2, structure prediction, protein design, computational drug discovery) - this is the strongest fit and primary target
- Gain industry (non-academic) experience to complement strong academic foundations - genomics bioinformatics and data analytics/data engineering roles are good secondary targets, especially in life sciences
- Move toward the Pacific Northwest over time (Seattle, Bellingham, remote, or Vancouver with sponsorship)

**Motivation filter:** Evaluate not just whether you *can* do the tasks, but whether the tasks will *energize* you. Consider:
- Tasks that energize: Applying ML/AlphaFold2-style models to real biological problems; building computational pipelines that turn raw data into clear, reproducible results; research that leads to publications or concrete deliverables
- Tasks that drain: Not yet well known - Brooks is early-career and open to learning what does and doesn't fit through varied roles. Avoid over-indexing here; do not assume any task type is draining without evidence.
- Non-task factors: Mission-driven, collaborative, low-friction team culture; some autonomy in how work gets done; openness to mentorship/learning

**Life situation alignment:** Consider personal constraints:
- **Security**: Currently living with parents in Austin, TX (zero housing cost), which makes lower-paying roles (e.g. academic research assistant positions) viable if based in Austin. Pharma/biotech industry roles are preferred over academia for pay, but Austin-based academic roles remain a reasonable fallback.
- **Flexibility**: Needs to apply within 1-2 days of a posting going live to stay competitive (entry-level roles fill quickly)
- **Professional development**: Prioritizes roles that build toward protein bioinformatics / structural biology specialization, or that offer a clear path into computational work from an adjacent role (e.g. wet-lab research associate with a computational group)

**Location-based scoring (from personal job search agent, `C:\Users\bkadu\Documents\jobhunt\profile.yaml`):**
- Vancouver, BC: highest personal priority (partner lives there) - requires employer sponsorship (LMIA or equivalent); flag sponsorship requirement explicitly
- Seattle, WA / Bellingham, WA / Remote / other Pacific Northwest: high priority, no sponsorship needed
- Austin, TX: moderate priority - currently based here, lower-paying roles are more viable due to zero housing cost
- San Diego, CA: moderate - brother lives there, prefer higher-paying roles to offset cost of living
- Anywhere else in the US: open but not preferred; needs to be a strong role match

**Calibration from past applications:**
- Was the top candidate at the Aparicio Lab (UBC) but lost out due to citizenship/sponsorship requirements - good signal of competitiveness for bioinformatics scientist roles when sponsorship isn't a barrier
- Interviewed well for a data analytics role (Data SEA Consulting, Toronto) - signal that data analytics/data engineering skills (Python, SQL) translate well outside life sciences

### 6. Salary Benchmark (Optional)

If the salary lookup tool is configured (`salary_data.json` exists), look up the company:
```
python salary_lookup.py "<Company Name>" --json
```

If a city is known from the posting, add `--city "<City>"` to narrow results.

Present findings as:
```
### Salary Benchmark
| Metric | Value |
|--------|-------|
| [Category] index | XX.X (+/-X.X% vs baseline) |
| Overall index | XX.X (+/-X.X% vs baseline) |
```

Interpret results relative to the baseline defined in the data file's metadata. For index-based data, higher typically means above-market compensation.

If the salary tool is not configured, skip this section.

## Output Format

Present the evaluation as:

```
## Job Fit Evaluation: [Role] at [Company]

| Dimension | Score | Notes |
|-----------|-------|-------|
| Technical Skills | XX/100 | [brief note] |
| Experience Match | XX/100 | [brief note] |
| Behavioral Fit | XX/100 | [brief note] |
| Location | PASS/FAIL | [brief note] |
| Career Alignment | XX/100 | [brief note] |

**Overall Score: XX/100** (weighted average of scored dimensions)

### Verdict: [Strong Fit / Good Fit / Moderate Fit / Weak Fit / Poor Fit]

### Key Strengths for This Role
- [bullet points]

### Gaps to Address
- [bullet points]

### Recommendation
[1-2 sentences: apply/skip/apply with caveats]

### Company Research Checklist
- [ ] Checked company website (mission, values, recent news)
- [ ] Checked review sites (Glassdoor, Jobindex, etc.)
- [ ] Checked LinkedIn for team size, recent hires, connections
- [ ] Checked media for restructuring, growth, or workplace issues
- [ ] Identified network contacts who may know the team/manager
```

## Weighting
- Technical Skills: 30%
- Experience Match: 25%
- Behavioral Fit: 15%
- Career Alignment: 30%

(Location is pass/fail, not weighted)

## Thresholds
- **Strong Fit** (75+): Definitely apply, tailor everything
- **Good Fit** (60-74): Apply, address gaps in cover letter
- **Moderate Fit** (45-59): Consider carefully, discuss with user
- **Weak Fit** (30-44): Probably skip unless strategic reasons
- **Poor Fit** (<30): Skip

## Pre-Application: Call the Employer (Best Practice)

Before writing the application, consider whether the candidate should call the contact person listed in the posting. **Only call if there are substantive questions** - never call just to "be remembered."

### When to Suggest Calling
- The posting has unclear or ambiguous requirements
- It's unclear which competencies are essential vs. nice-to-have
- The role description is vague about day-to-day tasks
- There's a named contact person who invites questions

### Good Questions to Ask
- "What are the primary challenges in this role?"
- "How is time typically divided across the listed responsibilities?"
- "Which competencies are most critical for success in this position?"
- "What does success look like in the first 6-12 months?"

### Rules for the Call
- Prepare a 30-second "elevator pitch" about your background in case they ask
- The call's purpose is **gathering information**, not delivering a pitch
- Take notes - use what you learn to tailor the application
- Reference the conversation naturally in the cover letter ("After speaking with [name], I was especially drawn to...")
