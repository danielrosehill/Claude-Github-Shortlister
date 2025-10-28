You are helping the user analyze a list of GitHub repositories against their defined specifications.

## Your Task

1. **Read the Input Files**:
   - Read `repos.md` to extract the list of GitHub repository URLs
   - Read `spec.md` to understand the user's requirements, constraints, and evaluation criteria

2. **Gather Repository Information**:
   For each repository URL in `repos.md`, use the `gh` CLI tool to gather:
   - Repository name and description
   - Star count
   - Last update date
   - Primary programming language
   - License
   - README content (summary)
   - Recent activity indicators

   Use commands like:
   - `gh repo view <owner/repo> --json name,description,stargazerCount,updatedAt,primaryLanguage,licenseInfo`
   - `gh repo view <owner/repo> --json readme` (to extract README content)

3. **Create Analysis Directory**:
   - Create an `analysis/` directory if it doesn't exist
   - Name the analysis file with a timestamp: `analysis-YYYY-MM-DD-HHMMSS.md`

4. **Analyze Each Repository**:
   For each repository, evaluate:
   - How well it matches the user's spec requirements
   - Strengths and weaknesses relative to the spec
   - Maintenance status (recent updates, active development)
   - Community adoption (stars, activity)
   - Compatibility factors (language, license, dependencies)

5. **Generate Comprehensive Analysis Document**:

   Create a structured markdown document in `analysis/` with:

   **Executive Summary Section**:
   - Top 3 recommended repositories with brief rationale
   - Key decision factors

   **Detailed Analysis Section**:
   - For each repository, provide:
     - Repository name and URL
     - Star count and last update
     - Brief description
     - How it matches the spec (strengths/gaps)
     - Recommendation level (Highly Recommended / Recommended / Consider / Not Recommended)

   **Comparison Table**:
   - Sortable table with key metrics:
     - Name
     - Stars
     - Last Updated
     - Language
     - License
     - Spec Match Score (your assessment)

   **Sorting Options**:
   - Provide the table sorted by:
     1. Your recommendation (best fit first)
     2. Star count (highest first)
     3. Last update (most recent first)

6. **Handle Edge Cases**:
   - If a repository URL is invalid or inaccessible, note it in the analysis
   - If `gh` CLI is not available, inform the user and suggest alternatives
   - If repos.md or spec.md don't exist, guide the user to create them

## Output Format

The analysis document should be professional, clear, and actionable. Use markdown formatting with:
- Clear headings and sections
- Tables for comparison data
- Bullet points for pros/cons
- Bold text for emphasis on recommendations
- Links to repositories

## Example Analysis Structure

```markdown
# GitHub Repository Analysis
**Generated**: [timestamp]
**Spec**: [brief summary from spec.md]

## Executive Summary

Based on your requirements, here are the top 3 recommendations:

1. **[Repo Name]** - [One sentence why it's the best fit]
2. **[Repo Name]** - [One sentence why]
3. **[Repo Name]** - [One sentence why]

## Key Decision Factors
- [Factor 1]
- [Factor 2]

## Detailed Repository Analysis

### 1. [Repository Name]
- **URL**: [link]
- **Stars**: X | **Last Update**: YYYY-MM-DD | **Language**: [lang]
- **License**: [license]

**Description**: [brief description]

**Spec Match Analysis**:
-  Strength 1
-  Strength 2
-   Consideration 1
- L Gap 1

**Recommendation**: [Highly Recommended / Recommended / Consider / Not Recommended]

**Rationale**: [2-3 sentences]

---

[Repeat for each repository]

## Comparison Table

| Repository | Stars | Last Updated | Language | License | Spec Match | Recommendation |
|------------|-------|--------------|----------|---------|------------|----------------|
| [Repo 1]   | X     | YYYY-MM-DD   | Python   | MIT     | 95%        | Highly Rec.    |
| [Repo 2]   | X     | YYYY-MM-DD   | Go       | Apache  | 85%        | Recommended    |

## Next Steps

1. [Actionable recommendation based on analysis]
2. [Suggested follow-up]
```

## Important Notes

- Be objective in your analysis
- Consider both technical and practical factors
- If multiple repositories are equally good, explain the trade-offs
- Highlight any deal-breakers early (e.g., incompatible license, abandoned project)
- Make the analysis scannable - busy developers should be able to get value in 2 minutes
