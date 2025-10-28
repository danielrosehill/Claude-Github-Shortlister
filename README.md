# Claude GitHub Shortlister

[![Claude Code](https://img.shields.io/badge/Claude-Code-8A2BE2?logo=anthropic&logoColor=white)](https://claude.ai/code)
[![Claude Code Projects](https://img.shields.io/badge/Claude%20Code-Projects%20Index-blue?logo=github)](https://github.com/danielrosehill/Claude-Code-Repos-Index)
[![Master Index](https://img.shields.io/badge/GitHub-Master%20Index-green?logo=github)](https://github.com/danielrosehill/Github-Master-Index)

A template repository for efficiently evaluating and shortlisting GitHub repositories when searching for solutions to your development needs.

## Overview

When building with generative AI and searching GitHub for solutions, you often encounter hundreds of results. This template provides a structured workflow to help you:

- Collect promising GitHub repositories in an organized manner
- Define your requirements and evaluation criteria
- Automatically analyze and compare repositories
- Get AI-powered recommendations based on your specific needs

## The Problem

A common scenario when searching for code solutions:

1. You have a problem to solve
2. You search GitHub with keywords
3. You get hundreds of results
4. Now you face the challenge: which repository best fits your needs?

Without a systematic approach, you might create a scratchpad, jot down interesting links, but never get around to properly evaluating them.

## The Solution

This template repository provides a structured workflow powered by Claude Code:

### Files Structure

- **`repos.md`**: Your scratchpad for listing potential GitHub repositories
- **`spec.md`**: Define your requirements and why you're looking for this solution
- **`.claude/commands/`**: Custom slash command for automated analysis

### Workflow

1. **Collect**: Add potential repository links to `repos.md`
2. **Define**: Specify your requirements in `spec.md`
3. **Analyze**: Run the custom Claude Code slash command
4. **Review**: Get organized analysis with recommendations

### Analysis Features

The automated analysis will:

- Review each repository against your specifications
- Organize repositories by:
  - Star count
  - Last update date
  - Relevance to your requirements
- Provide best-fit recommendations
- Output results to an analysis folder for easy reference

## Getting Started

1. Use this template to create a new repository
2. Fill out `repos.md` with GitHub repository links you want to evaluate
3. Define your requirements in `spec.md`
4. Run the Claude Code slash command to generate analysis
5. Review recommendations in the analysis folder

## Use Cases

- Evaluating libraries for a new project
- Finding the best tool for a specific task
- Comparing similar solutions
- Researching before making technology decisions
- Keeping track of evaluation progress over multiple sessions

## Requirements

- [Claude Code](https://claude.ai/code) for running the analysis command
- GitHub account (for accessing repositories)

## Contributing

This is a template repository. Feel free to fork and customize for your own workflow needs.

 

## Author

Daniel Rosehill
