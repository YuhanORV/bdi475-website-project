# Agent log

Add a dated entry each time you work with your AI coding agent, with the newest entry at the bottom. Each entry records what you asked the agent, what it produced, and what you checked or changed. Paste your key prompts in exactly as you typed them. Include at least one time the agent got something wrong, and how you caught it.

Copy this outline for each entry:

```markdown
## YYYY-MM-DD: What you worked on

- **Asked:** "Paste your prompt here."
- **Agent produced:** What it made or changed.
- **Checked or changed:** How you checked it, and what you fixed.
```
## 2026-11-12: Median sale price page

- **Asked:** "Read AGENTS.md and docs/data_description_sheet.md first. Then replace the placeholder index.html with a page that shows the median sale price for each city, computed from data/college_town_home_sales.csv. Leave out sales under $10,000 and state that rule on the page."
- **Agent produced:** Claude Code (web, Sonnet 5.5) replaced index.html with a page that reads the CSV in the browser and shows the median sale price for 18 cities, ranked highest to lowest, with the number of sales counted and a small bar for each. It states the $10,000 rule and a summary line (35,442 sales in the file, 40 left out, 35,402 counted). It did not change any files in data/.
- **Checked or changed:** The first push failed with a 403 error because the Claude GitHub App was not installed on my repository. I installed it and asked "I installed the Claude GitHub App, so try pushing again." and then "Yes, open a pull request". I reviewed Files changed in PR #1 (only index.html), merged it, waited for the green check in Actions, and confirmed the live site: Davis, CA is highest ($889,000) and Urbana, IL is lowest ($229,900). The agent noted that a few medians differ slightly from the data description sheet (for example Ann Arbor $572,000 vs. $571,000) because the sheet uses a $1,000 cutoff instead of $10,000.
- **What the agent got wrong:** It ranked Pittsboro, NC second even though it has only 92 sales, and it mixed the four small places (Savoy, Carrboro, Newberry, Pittsboro) in with the 14 main towns without any warning. The data description sheet lists those four separately. I caught this by comparing the "Sales counted" column, and I plan to ask the agent to mark those places in a later step.
