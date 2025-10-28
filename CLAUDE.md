# CLAUDE.md - Claude GitHub Shortlister

## Project Overview

This is a template repository designed to streamline the process of evaluating multiple GitHub repositories when searching for solutions to development problems. The goal is to help developers systematically analyze and compare potential solutions rather than manually reviewing hundreds of search results.

## User Intent and Vision

Daniel frequently encounters situations where searching GitHub yields overwhelming numbers of results. His typical workflow involves:

1. Creating a scratchpad file (usually `repos.md`)
2. Jotting down promising repository links
3. Often abandoning the evaluation due to time constraints

This template aims to automate the tedious manual evaluation process by leveraging Claude Code to analyze repositories against user-defined specifications.

## Project Requirements

### Core Files

1. **`repos.md`** - User's scratchpad containing:
   - List of GitHub repository URLs
   - Can include placeholder titles or brief notes
   - Format should be flexible (simple list or markdown links)

2. **`spec.md`** - User specification document containing:
   - Problem definition
   - Requirements and constraints
   - Evaluation criteria
   - Why the user is searching for this solution

3. **`.claude/commands/`** - Custom slash command directory:
   - Must be committed to override global gitignore
   - Contains command(s) to trigger automated analysis

4. **`analysis/`** - Output directory for:
   - Generated analysis documents
   - Repository comparisons
   - Recommendations

### Implementation Plan

#### Phase 1: Template Structure

- Create template files (`repos.md`, `spec.md`) with examples
- Set up `.claude/commands/` directory structure
- Create placeholder analysis directory

#### Phase 2: Slash Command Development

Create a slash command that:

1. **Reads Input Files**:
   - Parse `repos.md` to extract repository URLs
   - Parse `spec.md` to understand user requirements

2. **Repository Analysis**:
   - For each repository, gather:
     - Star count
     - Last update date/timestamp
     - README content
     - Primary language
     - License information
     - Activity metrics (if available via GitHub API)

3. **Evaluation Against Spec**:
   - Compare repository features against user requirements
   - Assess fit based on spec criteria
   - Identify strengths and weaknesses of each option

4. **Generate Analysis Document**:
   - Create organized comparison in `analysis/` folder
   - Sort repositories by:
     - Star count (popularity)
     - Last update (maintenance status)
     - Relevance to user spec
   - Provide clear recommendations with rationale

5. **Output Format**:
   - Structured markdown document
   - Summary section with top recommendations
   - Detailed analysis for each repository
   - Comparison table (if appropriate)

#### Phase 3: Enhancement

- Consider adding support for:
  - Multiple spec files for different use cases
  - Historical analysis tracking
  - Export formats (PDF, HTML)
  - Integration with GitHub CLI for richer data

## Technical Considerations

- Use `gh` CLI for GitHub API access when available
- Respect API rate limits
- Handle private vs public repository access
- Error handling for invalid URLs or inaccessible repos

## Usage Pattern

Expected user workflow:

1. User discovers repository needs solution
2. User searches GitHub, collects URLs in `repos.md`
3. User defines requirements in `spec.md`
4. User runs slash command (e.g., `/analyze-repos`)
5. Claude analyzes all repositories
6. User reviews analysis document in `analysis/` folder
7. User makes informed decision based on recommendations

## Success Criteria

The template is successful if it:

- Reduces time spent manually evaluating repositories
- Provides clear, actionable recommendations
- Scales to handle 10-100+ repositories
- Generates analysis that helps users make confident decisions
- Can be reused across different problem domains

## Important Context Reference

**Note**: This repository also contains a [CONTEXT.md](CONTEXT.md) file that provides Daniel's original vision and workflow description in his own words. Refer to CONTEXT.md when:

- You need deeper insight into user motivation
- The implementation requirements are ambiguous
- You want to understand the "why" behind design decisions
- You need examples of how Daniel currently approaches this problem

CONTEXT.md is the user's scratchpad and thinking-out-loud document, while this CLAUDE.md provides the structured implementation plan.

## Current Status

**Template Status**: Initial setup phase

**Next Steps**:
1. Create template files with examples
2. Implement basic slash command structure
3. Test with sample repositories
4. Iterate based on real-world usage
