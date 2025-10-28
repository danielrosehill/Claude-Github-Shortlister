# Claude GitHub Shortlister - Context

## The Problem

Here's a common scenario for those building with generative AI:

You have a "problem" (something you need to solve).

You know there's a solution.

If it's an AI/code problem, GitHub is probably one of the first places you'll turn to.

You put in keywords.

Great! Results.

But wait... 100s of results!

Now you have a haystack. How do you find the needle?

## My Workflow

My idea for this repo is to create a pattern for this workflow that I run through all the time.

I will typically do something like this:

I'll create a scratchpad file called something like `repos.md`.

I'll jot down some promising links from GitHub as I find them.

But sometimes I'll leave it there. The reason: I don't have the time to check these projects out one by one to see which provides the best fit for what I'm trying to achieve.

## The Solution (Repo Template)

Here's the idea here - this will be a repo template:

1. Create a `repos.md` file with a placeholder list of potential repositories from GitHub
2. Create a `spec.md` file in which the user defines the spec and why they're looking for this solution

3. Create a slash command (commit `.claude/commands` so that the global gitignore gets overridden). Add the slash command to review the GitHub repos the user jotted down and then:
   - Create an analysis folder
   - Claude writes out an analysis document which considers the user's spec and reviews the various repos
   - It organizes them by star count and last update count and provides best-fit recommendations