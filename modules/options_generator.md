# Week 12 Group Reflection

## Group Members
- Panth  
> Working solo so please mark easy 😊 Thank you TAs.

---

## Set 1: Microsoft Copilot-Assisted Prompt Review

### Task 1.1 — Copilot review of one Travel Planner module
**Transcript Link:** PASTE_LINK_HERE

**Name of selected module:** modules/PASTE_MODULE_NAME.md

**100-word summary of improvements (paste here):**
[PASTE YOUR 100-WORD SUMMARY]

**Updated module:**
```markdown
# Module 2 — Options Generator

## Purpose
From a valid Module 1 JSON (city, days, theme, optional per-day budget and date window), produce **3 morning options** and **3 afternoon options** for **each day** that match the theme and are feasible.

## Expected Input (from Module 1)
```json
{
  "city": "Lisbon",
  "days": 4,
  "theme": "Coastal food and viewpoints",
  "perDayBudget": 0,               // number ≥ 0 (optional; if missing → treat as unlimited)
  "dateRange": "2025-06-10..2025-06-13",   // optional
  "weatherHint": "rain likely"     // optional
}
Required Output (strict)
A Markdown table with columns: Day | Morning Options | Afternoon Options.

Each Morning/Afternoon cell contains exactly 3 bullet points.

After those 3 bullets, add one final bullet labeled “Bad-weather backup:” with an indoor idea (free or low cost).

Each bullet includes: Name (venue/activity), ~cost (USD), indoor/outdoor, and a 1-line rationale.

Guardrails & Policies
Budget sanity:

If perDayBudget = 0 → prefer free options; list costs as $0 or $0–$5.

If perDayBudget is missing → proceed but avoid premium items; write “check budget” only if obviously pricey.

Feasibility: Avoid obviously closed venues; when unsure, append “(check hours)”.

Transit & walking: Prefer ≤ 2 transit hops per period; keep typical walks ≤ 30 minutes unless the walk is the activity.

No duplication: Do not repeat the same venue in the same day.

No bookings invented: If reservations likely, say “reservation recommended”.

No hallucinations: If any detail is uncertain, keep it generic (e.g., “riverside viewpoint walk”) rather than invent specifics.

Example (format only; not prescriptive)
Day	Morning Options	Afternoon Options
1	• Alfama viewpoint walk (~$0, outdoor) — panoramic overlooks; gentle route. • Time Out Market scout (~$0–$5, indoor) — sample and plan. • Tram 28 photo loop (~$3, mixed) — quick city overview. Bad-weather backup: Lisbon Story Centre (~$10, indoor).	• MAAT museum (~$11, indoor) — design/energy exhibits. • Belém riverside walk (~$0, outdoor) — monuments & views. • Pastéis de Belém tasting (~$5, indoor) — iconic bakery. Bad-weather backup: National Tile Museum (~$10, indoor).
