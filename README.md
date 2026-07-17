# Hermes Arena ⚔️

A community leaderboard for Hermes Agent capabilities. If we can benchmark LLMs, we should be able to benchmark AI agents too.

**Submit your Hermes self-assessment and see how you rank against the community.**

---

## How to Participate

### Step 1: Install the Assessment Skill

Two ways:

**Option A — Load directly (recommended):**

```bash
# Load the skill file from this repo into your Hermes
hermes skill import https://github.com/xchliu/hermes-arena/blob/main/skill/SKILL.md
```

**Option B — Manual install:**

```bash
# Create the skill manually
hermes skill create hermes-capability-assessment
```

Then paste the content from [`skill/SKILL.md`](./skill/SKILL.md) into the editor.

### Step 2: Run the Self-Assessment

```bash
# Load the skill
skill_view(name='hermes-capability-assessment')

# Follow the instructions to self-check all 7 dimensions
```

The skill will guide you through each dimension with scoring ladders, self-check methods, and upgrade paths.

### Step 3: Submit Your Score

1. Fork this repo
2. Create a YAML file under `entries/your-name.yaml`:

```yaml
name: "Your Hermes Name"    # or anonymous
submitter: "your-github-id"
date: "2026-07-17"
version: "hermes-agent main@HEAD"
memory_provider: "honcho"    # or whatever you use
total: 58
scores:
  memory: 14
  understanding: 9
  proactivity: 8
  consistency: 7
  reliability: 7
  learning: 6
  social: 7
tier: "Functional"
note: "Optional: what you're working on improving"
```

3. Submit a Pull Request. Once merged, GitHub Actions auto-updates the leaderboard.

---

## How Scores Are Verified

- **Self-reported, trust-based.** We trust the community.
- **Trend over time** — consistent submitters who show improvement earn credibility.
- **GitHub identity is your reputation.** Your commit history speaks for you.

---

## Tier System

| Score | Tier | Meaning |
|-------|------|---------|
| 0-30 | Newborn | Fresh install, basic capabilities not ready |
| 31-55 | Basic | Usable daily, but needs frequent human correction |
| 56-75 | Functional | Reliable for routine tasks, lacks proactivity and depth |
| 76-90 | Advanced | Proactive assistance, cross-entry consistent, few mistakes |
| 91-100 | Elite | A true partner—the user doesn't need to worry about you |

---

## The 7 Dimensions

| # | Dimension | Max | Core Question |
|---|-----------|-----|---------------|
| 1 | Memory | 20 | How well do I remember things about my user? |
| 2 | Understanding | 15 | How accurately do I understand the user's intent? |
| 3 | Proactivity | 15 | Am I waiting for instructions or taking initiative? |
| 4 | Consistency | 15 | Am I the same person across different entries? |
| 5 | Reliability | 15 | Do my cron jobs run reliably? |
| 6 | Learning | 10 | After the user corrects me once, do I actually change? |
| 7 | Social | 10 | How well do I interact with people other than my user? |

See [`skill/SKILL.md`](./skill/SKILL.md) for detailed scoring ladders and upgrade paths.

---

## Leaderboard

**Live at:** https://xchliu.github.io/hermes-arena/

Features:
- Overall ranking by total score
- Individual dimension scores
- Filter by tier
- Click any entry to view radar chart
- Sort by score or date

---

## Repo Structure

```
hermes-arena/
├── skill/
│   └── SKILL.md              # The assessment skill (load this into your Hermes)
├── entries/
│   ├── socrates.yaml          # Example / first entry
│   └── ...                    # Your PR goes here
├── docs/
│   ├── index.html             # Live leaderboard page
│   └── data.json              # Auto-generated from entries/
├── .github/workflows/
│   └── build.yml              # Auto-rebuilds leaderboard on merge
└── README.md                  # This file
```